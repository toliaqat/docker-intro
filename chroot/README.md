# chroot example
This is a basic example of chroot

## Requirements:
 * macOS

## Download the image
chroot image, we will be using, is availble in this same directory.

## Uncompress
First we need uncompress the tar file which comes alone with this repo.
This tar file has utilities and their dependencies.

```
  tar -xf new-root.tar
```

The above command will uncompress the tar file in new-root folder.

## Run the container/chroot
Run the following command for starting `bash` application in the
container/chroot.

```
sudo chroot new-root bash
```

## Exercise 1:
After running the `sudo chroot` command you will be inside the container.  Now
from inside the container, create a file /test.txt at root of the filesystem.

cat << EOF > /test.txt
Hello containers!
EOF

Run following command to see that file is present at the root. And then display
the contents of the file.

```
ls /
cat /test.txt
```

Now exit the chroot using `exit` command. And verify that if you run the `ls /`
command you will not see the test.txt file you made earlier. But that file can
be found in side ./new-root folder.
