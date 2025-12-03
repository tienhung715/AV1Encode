# AV1Encode

ffmpeg.exe -i "input.mkv" -map 0 -map_chapters -1 -c:v av1_nvenc -preset p6 -b:v 20M -bufsize 50M -color_primaries bt2020 -color_trc smpte2084 -colorspace bt2020nc -c:a copy -c:s copy "output.mkv"

ffmpeg.exe -i "input.mkv" -map 0:v -map 0:2 -map 0:4 -map 0:5 -map 0:s? -map_chapters -1 -vf "crop=3840:1608:0:276" -c:v av1_nvenc -preset p6 -b:v 20M -bufsize 50M -color_primaries bt2020 -color_trc smpte2084 -colorspace bt2020nc -c:a:0 eac3 -ac 6 -b:a:0 1024k -c:a:1 copy -c:a:2 copy -c:s copy "output.mkv"

ffmpeg.exe -i "input.mkv" -map 0:v -map 0:a -map 0:s? -map_chapters -1 -vf "crop=3840:1608:0:276" -c:v av1_nvenc -preset p4 -b:v 25M -minrate 25M -maxrate 30M -bufsize 30M -color_primaries bt2020 -color_trc smpte2084 -colorspace bt2020nc -c:a eac3 -ac 6 -b:a 1024k -c:s copy "output.mkv"
