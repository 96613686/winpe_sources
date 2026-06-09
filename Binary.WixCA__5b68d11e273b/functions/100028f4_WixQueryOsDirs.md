# WixQueryOsDirs

- ea: `0x100028f4`
- end: `0x10002c7b`
- name: `WixQueryOsDirs`
- size: `903`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100028f4`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000f0b5`
- `0x10010720`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x10002943`
- `SHELL32!SHGetFolderPathW` at `0x10002966`
- `SHELL32!SHGetFolderPathW` at `0x10002989`
- `SHELL32!SHGetFolderPathW` at `0x100029ac`
- `SHELL32!SHGetFolderPathW` at `0x100029cf`
- `SHELL32!SHGetFolderPathW` at `0x100029f2`
- `SHELL32!SHGetFolderPathW` at `0x10002a15`
- `SHELL32!SHGetFolderPathW` at `0x10002a38`
- `SHELL32!SHGetFolderPathW` at `0x10002a5b`
- `SHELL32!SHGetFolderPathW` at `0x10002a7e`
- `SHELL32!SHGetFolderPathW` at `0x10002aa1`
- `SHELL32!SHGetFolderPathW` at `0x10002ac3`
- `SHELL32!SHGetFolderPathW` at `0x10002ae6`
- `SHELL32!SHGetFolderPathW` at `0x10002b09`
- `SHELL32!SHGetFolderPathW` at `0x10002b2c`
- `SHELL32!SHGetFolderPathW` at `0x10002b4f`
- `SHELL32!SHGetFolderPathW` at `0x10002b72`
- `SHELL32!SHGetFolderPathW` at `0x10002b95`
- `SHELL32!SHGetFolderPathW` at `0x10002bb8`
- `SHELL32!SHGetFolderPathW` at `0x10002bdb`
- `SHELL32!SHGetFolderPathW` at `0x10002bfe`
- `SHELL32!SHGetFolderPathW` at `0x10002c21`
- `SHELL32!SHGetFolderPathW` at `0x10002c44`
- `SHELL32!SHGetFolderPathW` at `0x10002931`

## string_xrefs

- `0x100029b9`: `WIX_DIR_COMMON_ADMINTOOLS`
- `0x100029dc`: `WIX_DIR_COMMON_ALTSTARTUP`
- `0x100029ff`: `WIX_DIR_COMMON_DOCUMENTS`
- `0x10002a22`: `WIX_DIR_COMMON_FAVORITES`
- `0x10002a45`: `WIX_DIR_COMMON_MUSIC`
- `0x10002a68`: `WIX_DIR_COMMON_PICTURES`
- `0x10002a8b`: `WIX_DIR_COMMON_VIDEO`
- `0x10002b16`: `WIX_DIR_INTERNET_CACHE`

## pseudocode

```c
int __stdcall WixQueryOsDirs(MSIHANDLE hInstall)
{
  int v1; // esi
  int v2; // eax
  int v3; // ebx
  WCHAR pszPath[260]; // [esp+8h] [ebp-20Ch] BYREF

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQueryOsDirs");
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( !SHGetFolderPathW(0, 48, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_ADMINTOOLS", pszPath);
    if ( !SHGetFolderPathW(0, 29, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_ALTSTARTUP", pszPath);
    if ( !SHGetFolderPathW(0, 59, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_CDBURN_AREA", pszPath);
    if ( !SHGetFolderPathW(0, 47, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_ADMINTOOLS", pszPath);
    if ( !SHGetFolderPathW(0, 30, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_ALTSTARTUP", pszPath);
    if ( !SHGetFolderPathW(0, 46, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_DOCUMENTS", pszPath);
    if ( !SHGetFolderPathW(0, 31, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_FAVORITES", pszPath);
    if ( !SHGetFolderPathW(0, 53, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_MUSIC", pszPath);
    if ( !SHGetFolderPathW(0, 54, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_PICTURES", pszPath);
    if ( !SHGetFolderPathW(0, 55, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COMMON_VIDEO", pszPath);
    if ( !SHGetFolderPathW(0, 33, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_COOKIES", pszPath);
    if ( !SHGetFolderPathW(0, 0, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_DESKTOP", pszPath);
    if ( !SHGetFolderPathW(0, 34, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_HISTORY", pszPath);
    if ( !SHGetFolderPathW(0, 32, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_INTERNET_CACHE", pszPath);
    if ( !SHGetFolderPathW(0, 13, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_MYMUSIC", pszPath);
    if ( !SHGetFolderPathW(0, 39, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_MYPICTURES", pszPath);
    if ( !SHGetFolderPathW(0, 14, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_MYVIDEO", pszPath);
    if ( !SHGetFolderPathW(0, 19, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_NETHOOD", pszPath);
    if ( !SHGetFolderPathW(0, 5, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_PERSONAL", pszPath);
    if ( !SHGetFolderPathW(0, 27, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_PRINTHOOD", pszPath);
    if ( !SHGetFolderPathW(0, 40, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_PROFILE", pszPath);
    if ( !SHGetFolderPathW(0, 8, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_RECENT", pszPath);
    if ( !SHGetFolderPathW(0, 56, 0, 0, pszPath) )
      sub_1000F0B5(L"WIX_DIR_RESOURCES", pszPath);
  }
  else
  {
    sub_1000DA66(v2, "WixQueryOsDirs failed to initialize");
  }
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x100028f4  push    ebp
0x100028f5  mov     ebp, esp
0x100028f7  sub     esp, 20Ch
0x100028fd  mov     eax, ___security_cookie
0x10002902  xor     eax, ebp
0x10002904  mov     [ebp+var_4], eax
0x10002907  push    ebx
0x10002908  push    esi
0x10002909  push    offset aWixqueryosdirs_0; "WixQueryOsDirs"
0x1000290e  push    [ebp+hInstall]; hInstall
0x10002911  xor     esi, esi
0x10002913  call    sub_1000D51F
0x10002918  mov     ebx, eax
0x1000291a  test    ebx, ebx
0x1000291c  jns     short loc_10002930
0x1000291e  push    offset aWixqueryosdirs_1; "WixQueryOsDirs failed to initialize"
0x10002923  push    ebx
0x10002924  call    sub_1000DA66
0x10002929  pop     ecx
0x1000292a  pop     ecx
0x1000292b  jmp     loc_10002C5C
0x10002930  push    edi
0x10002931  mov     edi, ds:SHGetFolderPathW
0x10002937  lea     eax, [ebp+pszPath]
0x1000293d  push    eax; pszPath
0x1000293e  push    esi; dwFlags
0x1000293f  push    esi; hToken
0x10002940  push    30h ; '0'; csidl
0x10002942  push    esi; hwnd
0x10002943  call    edi ; SHGetFolderPathW
0x10002945  test    eax, eax
0x10002947  jnz     short loc_1000295A
0x10002949  lea     eax, [ebp+pszPath]
0x1000294f  push    eax; szValue
0x10002950  push    offset aWixDirAdmintoo; "WIX_DIR_ADMINTOOLS"
0x10002955  call    sub_1000F0B5
0x1000295a  lea     eax, [ebp+pszPath]
0x10002960  push    eax; pszPath
0x10002961  push    esi; dwFlags
0x10002962  push    esi; hToken
0x10002963  push    1Dh; csidl
0x10002965  push    esi; hwnd
0x10002966  call    edi ; SHGetFolderPathW
0x10002968  test    eax, eax
0x1000296a  jnz     short loc_1000297D
0x1000296c  lea     eax, [ebp+pszPath]
0x10002972  push    eax; szValue
0x10002973  push    offset aWixDirAltstart; "WIX_DIR_ALTSTARTUP"
0x10002978  call    sub_1000F0B5
0x1000297d  lea     eax, [ebp+pszPath]
0x10002983  push    eax; pszPath
0x10002984  push    esi; dwFlags
0x10002985  push    esi; hToken
0x10002986  push    3Bh ; ';'; csidl
0x10002988  push    esi; hwnd
0x10002989  call    edi ; SHGetFolderPathW
0x1000298b  test    eax, eax
0x1000298d  jnz     short loc_100029A0
0x1000298f  lea     eax, [ebp+pszPath]
0x10002995  push    eax; szValue
0x10002996  push    offset aWixDirCdburnAr; "WIX_DIR_CDBURN_AREA"
0x1000299b  call    sub_1000F0B5
0x100029a0  lea     eax, [ebp+pszPath]
0x100029a6  push    eax; pszPath
0x100029a7  push    esi; dwFlags
0x100029a8  push    esi; hToken
0x100029a9  push    2Fh ; '/'; csidl
0x100029ab  push    esi; hwnd
0x100029ac  call    edi ; SHGetFolderPathW
0x100029ae  test    eax, eax
0x100029b0  jnz     short loc_100029C3
0x100029b2  lea     eax, [ebp+pszPath]
0x100029b8  push    eax; szValue
0x100029b9  push    offset aWixDirCommonAd; "WIX_DIR_COMMON_ADMINTOOLS"
0x100029be  call    sub_1000F0B5
0x100029c3  lea     eax, [ebp+pszPath]
0x100029c9  push    eax; pszPath
0x100029ca  push    esi; dwFlags
0x100029cb  push    esi; hToken
0x100029cc  push    1Eh; csidl
0x100029ce  push    esi; hwnd
0x100029cf  call    edi ; SHGetFolderPathW
0x100029d1  test    eax, eax
0x100029d3  jnz     short loc_100029E6
0x100029d5  lea     eax, [ebp+pszPath]
0x100029db  push    eax; szValue
0x100029dc  push    offset aWixDirCommonAl; "WIX_DIR_COMMON_ALTSTARTUP"
0x100029e1  call    sub_1000F0B5
0x100029e6  lea     eax, [ebp+pszPath]
0x100029ec  push    eax; pszPath
0x100029ed  push    esi; dwFlags
0x100029ee  push    esi; hToken
0x100029ef  push    2Eh ; '.'; csidl
0x100029f1  push    esi; hwnd
0x100029f2  call    edi ; SHGetFolderPathW
0x100029f4  test    eax, eax
0x100029f6  jnz     short loc_10002A09
0x100029f8  lea     eax, [ebp+pszPath]
0x100029fe  push    eax; szValue
0x100029ff  push    offset aWixDirCommonDo; "WIX_DIR_COMMON_DOCUMENTS"
0x10002a04  call    sub_1000F0B5
0x10002a09  lea     eax, [ebp+pszPath]
0x10002a0f  push    eax; pszPath
0x10002a10  push    esi; dwFlags
0x10002a11  push    esi; hToken
0x10002a12  push    1Fh; csidl
0x10002a14  push    esi; hwnd
0x10002a15  call    edi ; SHGetFolderPathW
0x10002a17  test    eax, eax
0x10002a19  jnz     short loc_10002A2C
0x10002a1b  lea     eax, [ebp+pszPath]
0x10002a21  push    eax; szValue
0x10002a22  push    offset aWixDirCommonFa; "WIX_DIR_COMMON_FAVORITES"
0x10002a27  call    sub_1000F0B5
0x10002a2c  lea     eax, [ebp+pszPath]
0x10002a32  push    eax; pszPath
0x10002a33  push    esi; dwFlags
0x10002a34  push    esi; hToken
0x10002a35  push    35h ; '5'; csidl
0x10002a37  push    esi; hwnd
0x10002a38  call    edi ; SHGetFolderPathW
0x10002a3a  test    eax, eax
0x10002a3c  jnz     short loc_10002A4F
0x10002a3e  lea     eax, [ebp+pszPath]
0x10002a44  push    eax; szValue
0x10002a45  push    offset aWixDirCommonMu; "WIX_DIR_COMMON_MUSIC"
0x10002a4a  call    sub_1000F0B5
0x10002a4f  lea     eax, [ebp+pszPath]
0x10002a55  push    eax; pszPath
0x10002a56  push    esi; dwFlags
0x10002a57  push    esi; hToken
0x10002a58  push    36h ; '6'; csidl
0x10002a5a  push    esi; hwnd
0x10002a5b  call    edi ; SHGetFolderPathW
0x10002a5d  test    eax, eax
0x10002a5f  jnz     short loc_10002A72
0x10002a61  lea     eax, [ebp+pszPath]
0x10002a67  push    eax; szValue
0x10002a68  push    offset aWixDirCommonPi; "WIX_DIR_COMMON_PICTURES"
0x10002a6d  call    sub_1000F0B5
0x10002a72  lea     eax, [ebp+pszPath]
0x10002a78  push    eax; pszPath
0x10002a79  push    esi; dwFlags
0x10002a7a  push    esi; hToken
0x10002a7b  push    37h ; '7'; csidl
0x10002a7d  push    esi; hwnd
0x10002a7e  call    edi ; SHGetFolderPathW
0x10002a80  test    eax, eax
0x10002a82  jnz     short loc_10002A95
0x10002a84  lea     eax, [ebp+pszPath]
0x10002a8a  push    eax; szValue
0x10002a8b  push    offset aWixDirCommonVi; "WIX_DIR_COMMON_VIDEO"
0x10002a90  call    sub_1000F0B5
0x10002a95  lea     eax, [ebp+pszPath]
0x10002a9b  push    eax; pszPath
0x10002a9c  push    esi; dwFlags
0x10002a9d  push    esi; hToken
0x10002a9e  push    21h ; '!'; csidl
0x10002aa0  push    esi; hwnd
0x10002aa1  call    edi ; SHGetFolderPathW
0x10002aa3  test    eax, eax
0x10002aa5  jnz     short loc_10002AB8
0x10002aa7  lea     eax, [ebp+pszPath]
0x10002aad  push    eax; szValue
0x10002aae  push    offset aWixDirCookies; "WIX_DIR_COOKIES"
0x10002ab3  call    sub_1000F0B5
0x10002ab8  lea     eax, [ebp+pszPath]
0x10002abe  push    eax; pszPath
0x10002abf  push    esi; dwFlags
0x10002ac0  push    esi; hToken
0x10002ac1  push    esi; csidl
0x10002ac2  push    esi; hwnd
0x10002ac3  call    edi ; SHGetFolderPathW
0x10002ac5  test    eax, eax
0x10002ac7  jnz     short loc_10002ADA
0x10002ac9  lea     eax, [ebp+pszPath]
0x10002acf  push    eax; szValue
0x10002ad0  push    offset aWixDirDesktop; "WIX_DIR_DESKTOP"
0x10002ad5  call    sub_1000F0B5
0x10002ada  lea     eax, [ebp+pszPath]
0x10002ae0  push    eax; pszPath
0x10002ae1  push    esi; dwFlags
0x10002ae2  push    esi; hToken
0x10002ae3  push    22h ; '"'; csidl
0x10002ae5  push    esi; hwnd
0x10002ae6  call    edi ; SHGetFolderPathW
0x10002ae8  test    eax, eax
0x10002aea  jnz     short loc_10002AFD
0x10002aec  lea     eax, [ebp+pszPath]
0x10002af2  push    eax; szValue
0x10002af3  push    offset aWixDirHistory; "WIX_DIR_HISTORY"
0x10002af8  call    sub_1000F0B5
0x10002afd  lea     eax, [ebp+pszPath]
0x10002b03  push    eax; pszPath
0x10002b04  push    esi; dwFlags
0x10002b05  push    esi; hToken
0x10002b06  push    20h ; ' '; csidl
0x10002b08  push    esi; hwnd
0x10002b09  call    edi ; SHGetFolderPathW
0x10002b0b  test    eax, eax
0x10002b0d  jnz     short loc_10002B20
0x10002b0f  lea     eax, [ebp+pszPath]
0x10002b15  push    eax; szValue
0x10002b16  push    offset aWixDirInternet; "WIX_DIR_INTERNET_CACHE"
0x10002b1b  call    sub_1000F0B5
0x10002b20  lea     eax, [ebp+pszPath]
0x10002b26  push    eax; pszPath
0x10002b27  push    esi; dwFlags
0x10002b28  push    esi; hToken
0x10002b29  push    0Dh; csidl
0x10002b2b  push    esi; hwnd
0x10002b2c  call    edi ; SHGetFolderPathW
0x10002b2e  test    eax, eax
0x10002b30  jnz     short loc_10002B43
0x10002b32  lea     eax, [ebp+pszPath]
0x10002b38  push    eax; szValue
0x10002b39  push    offset aWixDirMymusic; "WIX_DIR_MYMUSIC"
0x10002b3e  call    sub_1000F0B5
0x10002b43  lea     eax, [ebp+pszPath]
0x10002b49  push    eax; pszPath
0x10002b4a  push    esi; dwFlags
0x10002b4b  push    esi; hToken
0x10002b4c  push    27h ; '''; csidl
0x10002b4e  push    esi; hwnd
0x10002b4f  call    edi ; SHGetFolderPathW
0x10002b51  test    eax, eax
0x10002b53  jnz     short loc_10002B66
0x10002b55  lea     eax, [ebp+pszPath]
0x10002b5b  push    eax; szValue
0x10002b5c  push    offset aWixDirMypictur; "WIX_DIR_MYPICTURES"
0x10002b61  call    sub_1000F0B5
0x10002b66  lea     eax, [ebp+pszPath]
0x10002b6c  push    eax; pszPath
0x10002b6d  push    esi; dwFlags
0x10002b6e  push    esi; hToken
0x10002b6f  push    0Eh; csidl
0x10002b71  push    esi; hwnd
0x10002b72  call    edi ; SHGetFolderPathW
0x10002b74  test    eax, eax
0x10002b76  jnz     short loc_10002B89
0x10002b78  lea     eax, [ebp+pszPath]
0x10002b7e  push    eax; szValue
0x10002b7f  push    offset aWixDirMyvideo; "WIX_DIR_MYVIDEO"
0x10002b84  call    sub_1000F0B5
0x10002b89  lea     eax, [ebp+pszPath]
0x10002b8f  push    eax; pszPath
0x10002b90  push    esi; dwFlags
0x10002b91  push    esi; hToken
0x10002b92  push    13h; csidl
0x10002b94  push    esi; hwnd
0x10002b95  call    edi ; SHGetFolderPathW
0x10002b97  test    eax, eax
0x10002b99  jnz     short loc_10002BAC
0x10002b9b  lea     eax, [ebp+pszPath]
0x10002ba1  push    eax; szValue
0x10002ba2  push    offset aWixDirNethood; "WIX_DIR_NETHOOD"
0x10002ba7  call    sub_1000F0B5
0x10002bac  lea     eax, [ebp+pszPath]
0x10002bb2  push    eax; pszPath
0x10002bb3  push    esi; dwFlags
0x10002bb4  push    esi; hToken
0x10002bb5  push    5; csidl
0x10002bb7  push    esi; hwnd
0x10002bb8  call    edi ; SHGetFolderPathW
0x10002bba  test    eax, eax
0x10002bbc  jnz     short loc_10002BCF
0x10002bbe  lea     eax, [ebp+pszPath]
0x10002bc4  push    eax; szValue
0x10002bc5  push    offset aWixDirPersonal; "WIX_DIR_PERSONAL"
0x10002bca  call    sub_1000F0B5
0x10002bcf  lea     eax, [ebp+pszPath]
0x10002bd5  push    eax; pszPath
0x10002bd6  push    esi; dwFlags
0x10002bd7  push    esi; hToken
0x10002bd8  push    1Bh; csidl
0x10002bda  push    esi; hwnd
0x10002bdb  call    edi ; SHGetFolderPathW
0x10002bdd  test    eax, eax
0x10002bdf  jnz     short loc_10002BF2
0x10002be1  lea     eax, [ebp+pszPath]
0x10002be7  push    eax; szValue
0x10002be8  push    offset aWixDirPrinthoo; "WIX_DIR_PRINTHOOD"
0x10002bed  call    sub_1000F0B5
0x10002bf2  lea     eax, [ebp+pszPath]
0x10002bf8  push    eax; pszPath
0x10002bf9  push    esi; dwFlags
0x10002bfa  push    esi; hToken
0x10002bfb  push    28h ; '('; csidl
0x10002bfd  push    esi; hwnd
0x10002bfe  call    edi ; SHGetFolderPathW
0x10002c00  test    eax, eax
0x10002c02  jnz     short loc_10002C15
0x10002c04  lea     eax, [ebp+pszPath]
0x10002c0a  push    eax; szValue
0x10002c0b  push    offset aWixDirProfile; "WIX_DIR_PROFILE"
0x10002c10  call    sub_1000F0B5
0x10002c15  lea     eax, [ebp+pszPath]
0x10002c1b  push    eax; pszPath
0x10002c1c  push    esi; dwFlags
0x10002c1d  push    esi; hToken
  ... truncated ...
```
