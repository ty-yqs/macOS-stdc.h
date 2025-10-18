# macOS &lt;bits/stdc++.h&gt;

## Support for &lt;bits/stdc++.h&gt; in macOS

macOS ships by default with the LLVM/Clang compiler which does not
support GNU/GCC extensions such as the `bits/stdc++.h` header file that
every beginner tends to use in their C++ code.

This is a problem even when you use g++ in macOS, as Apple use g++ as a
front-end to clang++ for legacy reasons.

## Solution

### Solution 1

1.  command in the Terminal

    ```bash
    wget https://github.com/ty-yqs/macOS-stdc.h/raw/refs/heads/main/install.sh
    sudo bash ./install.sh
    ```

2.  You can now write and compile successfully:

    ``` cpp
    #include <bits/stdc++.h>
    ```

### Solution 2

1.  You need to create a directory ‘bits’ under the folder
    `/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include`. This can be done by running the following
    command in the Terminal:

    ``` bash
    mkdir /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/bits
    ```

2.  You need to copy the contents of the
    [stdc++.h](./bits/stdc++.h) file included in this repository
    into the newly created bits folder:

    ``` bash
    curl https://raw.githubusercontent.com/ty-yqs/macOS-stdc.h/refs/heads/main/bits/stdc%2B%2B.h > /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/bits/stdc++.h
    ```

3.  You can now write and compile successfully:

    ``` cpp
    #include <bits/stdc++.h>
    ```
