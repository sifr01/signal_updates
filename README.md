# signal_updates
Signal messenger provides the apk to manually download the app along with the fingerprint to verify the download. This is how to verify the download's authenticity. This became a slightly more obscure process to carry out after apk version 3.

Download the apk from https://signal.org/android/apk/

Also copy the SHA256 fingerprint displayed on the page. Last time I looked, the SHA256 fingerprint was:
29:F3:4E:5F:27:F2:11:B4:24:BC:5B:F9:D6:71:62:C0:EA:FB:A2:DA:35:AF:35:C1:64:16:FC:44:62:76:BA:26

Next:

sudo apt update

sudo apt install apksigner

keytool -printcert -jarfile <Signal-website-download-file.apk> | grep SHA256

#now compare compare whether the two SHA256 fingerprints match
