# ExecXmlFileRollback

- ea: `0x10007d8c`
- end: `0x10007ff5`
- name: `ExecXmlFileRollback`
- size: `617`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10007d8c`
- `0x1000a952`
- `0x1000ad15`
- `0x1000aeff`
- `0x1000b556`
- `0x1000b8d3`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e662`
- `0x1000ef44`
- `0x1000ef8f`
- `0x1000efcc`
- `0x10010509`
- `0x10010563`
- `0x10010583`
- `0x10010646`
- `0x10010671`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10007f6f`
- `KERNEL32!CloseHandle` at `0x10007fbd`
- `KERNEL32!CloseHandle` at `0x10007f6f`
- `KERNEL32!CloseHandle` at `0x10007fbd`
- `KERNEL32!GetLastError` at `0x10007eed`
- `KERNEL32!GetLastError` at `0x10007f3b`
- `KERNEL32!GetLastError` at `0x10007eed`
- `KERNEL32!GetLastError` at `0x10007f3b`
- `KERNEL32!CreateFileW` at `0x10007ee0`
- `KERNEL32!CreateFileW` at `0x10007ee0`
- `KERNEL32!WriteFile` at `0x10007f31`
- `KERNEL32!WriteFile` at `0x10007f31`

## string_xrefs

- `0x10007f11`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\xmlfile.cpp`
- `0x10007f5a`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\xmlfile.cpp`
- `0x10007e33`: `failed to read file name from custom action data`
- `0x10007d9a`: `ExecXmlFileRollback`
- `0x10007e19`: `failed to read component bitness from custom action data`
- `0x10007e51`: `failed to read file contents from custom action data`
- `0x10007e92`: `Custom action was told to rollback a 64-bit component, but the custom action process is not running in WOW.`
- `0x10007ea7`: `Custom action was told to rollback a 64-bit component, but was unable to Disable Filesystem Redirection through the Wow64 API.`
- `0x10007f1e`: `failed to open file: %ls`
- `0x10007f67`: `failed to write to file: %ls`

## pseudocode

```c
int __stdcall ExecXmlFileRollback(MSIHANDLE hInstall)
{
  int v1; // edi
  int FileW; // ebx
  signed int v3; // esi
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  bool v7; // sf
  struct _FILETIME LastWriteTime; // [esp+Ch] [ebp-24h] BYREF
  DWORD NumberOfBytesWritten; // [esp+14h] [ebp-1Ch] BYREF
  MSIHANDLE v11; // [esp+18h] [ebp-18h]
  DWORD nNumberOfBytesToWrite; // [esp+1Ch] [ebp-14h] BYREF
  LPCVOID lpBuffer; // [esp+20h] [ebp-10h] BYREF
  wchar_t SubStr[2]; // [esp+24h] [ebp-Ch] BYREF
  DWORD pcchValueBuf; // [esp+28h] [ebp-8h] BYREF
  LPCWSTR lpFileName; // [esp+2Ch] [ebp-4h] BYREF

  v1 = 0;
  FileW = -1;
  v11 = 0;
  pcchValueBuf = 0;
  *(_DWORD *)SubStr = 0;
  lpFileName = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v3 = sub_1000D51F(hInstall, (int)"ExecXmlFileRollback");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize");
    goto LABEL_35;
  }
  v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to get CustomActionData");
    goto LABEL_35;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v3 = sub_1000EF44((wchar_t)SubStr, (int)&hInstall);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read component bitness from custom action data");
    goto LABEL_35;
  }
  v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read file name from custom action data");
    goto LABEL_35;
  }
  v3 = sub_1000EF8F((wchar_t)SubStr, (int)&lpBuffer, (int)&nNumberOfBytesToWrite);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read file contents from custom action data");
    goto LABEL_35;
  }
  v11 = hInstall;
  if ( !hInstall )
    goto LABEL_20;
  v3 = sub_10010583();
  if ( v3 == 1 )
    v3 = -2147319761;
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize Wow64 API");
    goto LABEL_35;
  }
  if ( !sub_10010646() )
  {
    v3 = -2147467263;
    sub_1000DA66(
      -2147467263,
      "Custom action was told to rollback a 64-bit component, but the custom action process is not running in WOW.");
    goto LABEL_35;
  }
  v3 = sub_10010509();
  if ( v3 < 0 )
  {
    sub_1000DA66(
      v3,
      "Custom action was told to rollback a 64-bit component, but was unable to Disable Filesystem Redirection through the Wow64 API.");
  }
  else
  {
LABEL_20:
    v3 = sub_1000B556(lpFileName, 0, 0, &LastWriteTime);
    if ( v3 >= 0 )
    {
      FileW = (int)CreateFileW(lpFileName, 0x40000000u, 0, 0, 5u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        v5 = LastError < 0;
        if ( LastError > 0 )
        {
          v3 = (unsigned __int16)LastError | 0x80070000;
          v5 = 1;
        }
        if ( !v5 )
          v3 = -2147467259;
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\xmlfile.cpp", 917, v3);
        sub_1000DA66(v3, "failed to open file: %ls");
      }
      else
      {
        if ( WriteFile((HANDLE)FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          goto LABEL_33;
        v6 = GetLastError();
        v3 = v6;
        v7 = v6 < 0;
        if ( v6 > 0 )
        {
          v3 = (unsigned __int16)v6 | 0x80070000;
          v7 = 1;
        }
        if ( !v7 )
        {
LABEL_33:
          CloseHandle((HANDLE)FileW);
          FileW = -1;
          v3 = sub_1000B8D3(lpFileName, 0, 0, &LastWriteTime);
          if ( v3 < 0 )
            sub_1000DA66(v3, "Failed to set modified date of file %ls.");
        }
        else
        {
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\xmlfile.cpp", 921, v3);
          sub_1000DA66(v3, "failed to write to file: %ls");
        }
      }
    }
    else
    {
      sub_1000DA66(v3, "Failed to get modified date of file %ls.");
    }
  }
LABEL_35:
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v11 )
  {
    sub_10010671();
    sub_10010563();
  }
  if ( lpBuffer )
    sub_1000AEFF((LPVOID)lpBuffer);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10007d8c  push    ebp
0x10007d8d  mov     ebp, esp
0x10007d8f  sub     esp, 24h
0x10007d92  push    ebx
0x10007d93  push    esi
0x10007d94  push    edi
0x10007d95  xor     edi, edi
0x10007d97  or      ebx, 0FFFFFFFFh
0x10007d9a  push    offset aExecxmlfilerol_1; "ExecXmlFileRollback"
0x10007d9f  push    [ebp+hInstall]; hInstall
0x10007da2  mov     [ebp+var_18], edi
0x10007da5  mov     [ebp+pcchValueBuf], edi
0x10007da8  mov     dword ptr [ebp+SubStr], edi
0x10007dab  mov     [ebp+lpFileName], edi
0x10007dae  mov     [ebp+lpBuffer], edi
0x10007db1  mov     [ebp+nNumberOfBytesToWrite], edi
0x10007db4  mov     [ebp+NumberOfBytesWritten], edi
0x10007db7  call    sub_1000D51F
0x10007dbc  mov     esi, eax
0x10007dbe  test    esi, esi
0x10007dc0  jns     short loc_10007DD4
0x10007dc2  push    offset aFailedToInitia_2; "failed to initialize"
0x10007dc7  push    esi
0x10007dc8  call    sub_1000DA66
0x10007dcd  pop     ecx
0x10007dce  pop     ecx
0x10007dcf  jmp     loc_10007F9D
0x10007dd4  lea     eax, [ebp+pcchValueBuf]
0x10007dd7  push    eax; pcchValueBuf
0x10007dd8  push    offset aCustomactionda; "CustomActionData"
0x10007ddd  call    sub_1000E662
0x10007de2  mov     esi, eax
0x10007de4  test    esi, esi
0x10007de6  jns     short loc_10007DEF
0x10007de8  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10007ded  jmp     short loc_10007DC7
0x10007def  push    [ebp+pcchValueBuf]
0x10007df2  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10007df7  push    edi
0x10007df8  call    sub_1000D9AB
0x10007dfd  mov     eax, [ebp+pcchValueBuf]
0x10007e00  add     esp, 0Ch
0x10007e03  mov     dword ptr [ebp+SubStr], eax
0x10007e06  lea     eax, [ebp+hInstall]
0x10007e09  push    eax; int
0x10007e0a  lea     eax, [ebp+SubStr]
0x10007e0d  push    eax; SubStr
0x10007e0e  call    sub_1000EF44
0x10007e13  mov     esi, eax
0x10007e15  test    esi, esi
0x10007e17  jns     short loc_10007E20
0x10007e19  push    offset aFailedToReadCo; "failed to read component bitness from c"...
0x10007e1e  jmp     short loc_10007DC7
0x10007e20  lea     eax, [ebp+lpFileName]
0x10007e23  push    eax; int
0x10007e24  lea     eax, [ebp+SubStr]
0x10007e27  push    eax; SubStr
0x10007e28  call    sub_1000EFCC
0x10007e2d  mov     esi, eax
0x10007e2f  test    esi, esi
0x10007e31  jns     short loc_10007E3A
0x10007e33  push    offset aFailedToReadFi_0; "failed to read file name from custom ac"...
0x10007e38  jmp     short loc_10007DC7
0x10007e3a  lea     eax, [ebp+nNumberOfBytesToWrite]
0x10007e3d  push    eax; int
0x10007e3e  lea     eax, [ebp+lpBuffer]
0x10007e41  push    eax; int
0x10007e42  lea     eax, [ebp+SubStr]
0x10007e45  push    eax; SubStr
0x10007e46  call    sub_1000EF8F
0x10007e4b  mov     esi, eax
0x10007e4d  test    esi, esi
0x10007e4f  jns     short loc_10007E5B
0x10007e51  push    offset aFailedToReadFi_1; "failed to read file contents from custo"...
0x10007e56  jmp     loc_10007DC7
0x10007e5b  mov     eax, [ebp+hInstall]
0x10007e5e  mov     [ebp+var_18], eax
0x10007e61  test    eax, eax
0x10007e63  jz      short loc_10007EB1
0x10007e65  call    sub_10010583
0x10007e6a  mov     esi, eax
0x10007e6c  cmp     esi, 1
0x10007e6f  jnz     short loc_10007E76
0x10007e71  mov     esi, 8002802Fh
0x10007e76  test    esi, esi
0x10007e78  jns     short loc_10007E84
0x10007e7a  push    offset aFailedToInitia_11; "failed to initialize Wow64 API"
0x10007e7f  jmp     loc_10007DC7
0x10007e84  call    sub_10010646
0x10007e89  test    eax, eax
0x10007e8b  jnz     short loc_10007E9C
0x10007e8d  mov     esi, 80004001h
0x10007e92  push    offset aCustomActionWa_1; "Custom action was told to rollback a 64"...
0x10007e97  jmp     loc_10007DC7
0x10007e9c  call    sub_10010509
0x10007ea1  mov     esi, eax
0x10007ea3  test    esi, esi
0x10007ea5  jns     short loc_10007EB1
0x10007ea7  push    offset aCustomActionWa_2; "Custom action was told to rollback a 64"...
0x10007eac  jmp     loc_10007DC7
0x10007eb1  lea     eax, [ebp+LastWriteTime]
0x10007eb4  push    eax; lpLastWriteTime
0x10007eb5  push    edi; lpLastAccessTime
0x10007eb6  push    edi; lpCreationTime
0x10007eb7  push    [ebp+lpFileName]; lpFileName
0x10007eba  call    sub_1000B556
0x10007ebf  mov     esi, eax
0x10007ec1  test    esi, esi
0x10007ec3  jns     short loc_10007ED2
0x10007ec5  push    [ebp+lpFileName]
0x10007ec8  push    offset aFailedToGetMod_0; "Failed to get modified date of file %ls"...
0x10007ecd  jmp     loc_10007F94
0x10007ed2  push    edi; hTemplateFile
0x10007ed3  push    edi; dwFlagsAndAttributes
0x10007ed4  push    5; dwCreationDisposition
0x10007ed6  push    edi; lpSecurityAttributes
0x10007ed7  push    edi; dwShareMode
0x10007ed8  push    40000000h; dwDesiredAccess
0x10007edd  push    [ebp+lpFileName]; lpFileName
0x10007ee0  call    ds:CreateFileW
0x10007ee6  mov     ebx, eax
0x10007ee8  cmp     ebx, 0FFFFFFFFh
0x10007eeb  jnz     short loc_10007F25
0x10007eed  call    ds:GetLastError
0x10007ef3  mov     esi, eax
0x10007ef5  test    esi, esi
0x10007ef7  jle     short loc_10007F04
0x10007ef9  movzx   esi, si
0x10007efc  or      esi, 80070000h
0x10007f02  test    esi, esi
0x10007f04  js      short loc_10007F0B
0x10007f06  mov     esi, 80004005h
0x10007f0b  push    esi
0x10007f0c  push    395h
0x10007f11  push    offset aDAWork1SSrcExt_5; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10007f16  call    nullsub_1
0x10007f1b  push    [ebp+lpFileName]
0x10007f1e  push    offset aFailedToOpenFi; "failed to open file: %ls"
0x10007f23  jmp     short loc_10007F94
0x10007f25  push    edi; lpOverlapped
0x10007f26  lea     eax, [ebp+NumberOfBytesWritten]
0x10007f29  push    eax; lpNumberOfBytesWritten
0x10007f2a  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x10007f2d  push    [ebp+lpBuffer]; lpBuffer
0x10007f30  push    ebx; hFile
0x10007f31  call    ds:WriteFile
0x10007f37  test    eax, eax
0x10007f39  jnz     short loc_10007F6E
0x10007f3b  call    ds:GetLastError
0x10007f41  mov     esi, eax
0x10007f43  test    esi, esi
0x10007f45  jle     short loc_10007F52
0x10007f47  movzx   esi, si
0x10007f4a  or      esi, 80070000h
0x10007f50  test    esi, esi
0x10007f52  jns     short loc_10007F6E
0x10007f54  push    esi
0x10007f55  push    399h
0x10007f5a  push    offset aDAWork1SSrcExt_5; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10007f5f  call    nullsub_1
0x10007f64  push    [ebp+lpFileName]
0x10007f67  push    offset aFailedToWriteT; "failed to write to file: %ls"
0x10007f6c  jmp     short loc_10007F94
0x10007f6e  push    ebx; hObject
0x10007f6f  call    ds:CloseHandle
0x10007f75  lea     eax, [ebp+LastWriteTime]
0x10007f78  or      ebx, 0FFFFFFFFh
0x10007f7b  push    eax; lpLastWriteTime
0x10007f7c  push    edi; lpLastAccessTime
0x10007f7d  push    edi; lpCreationTime
0x10007f7e  push    [ebp+lpFileName]; lpFileName
0x10007f81  call    sub_1000B8D3
0x10007f86  mov     esi, eax
0x10007f88  test    esi, esi
0x10007f8a  jns     short loc_10007F9D
0x10007f8c  push    [ebp+lpFileName]
0x10007f8f  push    offset aFailedToSetMod_0; "Failed to set modified date of file %ls"...
0x10007f94  push    esi
0x10007f95  call    sub_1000DA66
0x10007f9a  add     esp, 0Ch
0x10007f9d  cmp     [ebp+pcchValueBuf], edi
0x10007fa0  jz      short loc_10007FAA
0x10007fa2  push    [ebp+pcchValueBuf]
0x10007fa5  call    sub_1000A952
0x10007faa  cmp     [ebp+lpFileName], edi
0x10007fad  jz      short loc_10007FB7
0x10007faf  push    [ebp+lpFileName]
0x10007fb2  call    sub_1000A952
0x10007fb7  cmp     ebx, 0FFFFFFFFh
0x10007fba  jz      short loc_10007FC3
0x10007fbc  push    ebx; hObject
0x10007fbd  call    ds:CloseHandle
0x10007fc3  cmp     [ebp+var_18], edi
0x10007fc6  jz      short loc_10007FD2
0x10007fc8  call    sub_10010671
0x10007fcd  call    sub_10010563
0x10007fd2  cmp     [ebp+lpBuffer], edi
0x10007fd5  jz      short loc_10007FDF
0x10007fd7  push    [ebp+lpBuffer]; lpMem
0x10007fda  call    sub_1000AEFF
0x10007fdf  test    esi, esi
0x10007fe1  jns     short loc_10007FE8
0x10007fe3  mov     edi, 643h
0x10007fe8  push    edi
0x10007fe9  call    sub_1000D4AE
0x10007fee  pop     edi
0x10007fef  pop     esi
0x10007ff0  pop     ebx
0x10007ff1  leave
0x10007ff2  retn    4
```
