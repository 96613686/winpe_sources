# WixShellExecBinary

- ea: `0x100069b8`
- end: `0x10006bb7`
- name: `WixShellExecBinary`
- size: `511`
- prototype: `int __stdcall(DWORD NumberOfBytesWritten)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x1000660f`
- `0x10006753`
- `0x1000686b`
- `0x100069b8`
- `0x1000a19e`
- `0x1000a952`
- `0x1000ad15`
- `0x1000aeff`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e3bd`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10006b38`
- `KERNEL32!CloseHandle` at `0x10006b9b`
- `KERNEL32!CloseHandle` at `0x10006b38`
- `KERNEL32!CloseHandle` at `0x10006b9b`
- `KERNEL32!GetLastError` at `0x10006aa2`
- `KERNEL32!GetLastError` at `0x10006aff`
- `KERNEL32!GetLastError` at `0x10006aa2`
- `KERNEL32!GetLastError` at `0x10006aff`
- `KERNEL32!CreateFileW` at `0x10006a95`
- `KERNEL32!CreateFileW` at `0x10006a95`
- `KERNEL32!WriteFile` at `0x10006af5`
- `KERNEL32!WriteFile` at `0x10006af5`
- `KERNEL32!GetTempPathW` at `0x10006a40`
- `KERNEL32!GetTempPathW` at `0x10006a40`

## string_xrefs

- `0x10006ac6`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\shellexecca.cpp`
- `0x10006b23`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\shellexecca.cpp`
- `0x10006ad3`: `Failed to open new temp file: %ls`
- `0x10006b30`: `Failed to write data to new temp file: %ls`

## pseudocode

```c
int __stdcall WixShellExecBinary(DWORD NumberOfBytesWritten)
{
  int v1; // edi
  int FileW; // ebx
  signed int v3; // esi
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  bool v7; // sf
  DWORD nNumberOfBytesToWrite; // [esp+Ch] [ebp-10h] BYREF
  LPCVOID v10; // [esp+10h] [ebp-Ch] BYREF
  int v11; // [esp+14h] [ebp-8h] BYREF
  LPWSTR lpBuffer; // [esp+18h] [ebp-4h] BYREF

  v1 = 0;
  FileW = -1;
  v11 = 0;
  lpBuffer = 0;
  v10 = 0;
  nNumberOfBytesToWrite = 0;
  v3 = sub_1000D51F(NumberOfBytesWritten, (int)"WixShellExecBinary");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize");
    goto LABEL_26;
  }
  v3 = sub_1000E3BD(L"WixShellExecBinaryId", (int)&v11);
  if ( v3 < 0 )
    goto LABEL_25;
  sub_1000D9AB(1, "WixShellExecBinaryId is %ls");
  if ( !v11 || !*(_WORD *)v11 )
  {
    v3 = -2147024809;
LABEL_25:
    sub_1000DA66(v3, "failed to get WixShellExecBinaryId");
    goto LABEL_26;
  }
  __std_fs_create_symbolic_link(&lpBuffer, 260);
  GetTempPathW(0x104u, lpBuffer);
  v3 = sub_1000686B(lpBuffer, 260, v11);
  if ( v3 >= 0 )
  {
    v3 = sub_1000660F(v11, (int)&v10, &nNumberOfBytesToWrite);
    if ( v3 >= 0 )
    {
      FileW = (int)CreateFileW(lpBuffer, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
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
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\shellexecca.cpp", 195, v3);
        sub_1000DA66(v3, "Failed to open new temp file: %ls");
      }
      else
      {
        NumberOfBytesWritten = 0;
        if ( WriteFile((HANDLE)FileW, v10, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
        {
          CloseHandle((HANDLE)FileW);
          FileW = -1;
          v3 = sub_10006753(lpBuffer);
          if ( v3 < 0 )
            sub_1000DA66(v3, "failed to launch target: %ls");
        }
        else
        {
          v6 = GetLastError();
          v3 = v6;
          v7 = v6 < 0;
          if ( v6 > 0 )
          {
            v3 = (unsigned __int16)v6 | 0x80070000;
            v7 = 1;
          }
          if ( !v7 )
            v3 = -2147467259;
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\shellexecca.cpp", 201, v3);
          sub_1000DA66(v3, "Failed to write data to new temp file: %ls");
        }
      }
    }
    else
    {
      sub_1000DA66(v3, "failed to extract binary data");
    }
  }
  else
  {
    sub_1000DA66(v3, "Failed to append filename.");
  }
LABEL_26:
  if ( v11 )
    sub_1000A952(v11);
  if ( lpBuffer )
    sub_1000A952(lpBuffer);
  if ( v10 )
    sub_1000AEFF((LPVOID)v10);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x100069b8  push    ebp
0x100069b9  mov     ebp, esp
0x100069bb  sub     esp, 10h
0x100069be  push    ebx
0x100069bf  push    esi
0x100069c0  push    edi
0x100069c1  xor     edi, edi
0x100069c3  or      ebx, 0FFFFFFFFh
0x100069c6  push    offset aWixshellexecbi_0; "WixShellExecBinary"
0x100069cb  push    [ebp+NumberOfBytesWritten]; hInstall
0x100069ce  mov     [ebp+var_8], edi
0x100069d1  mov     [ebp+lpBuffer], edi
0x100069d4  mov     [ebp+var_C], edi
0x100069d7  mov     [ebp+nNumberOfBytesToWrite], edi
0x100069da  call    sub_1000D51F
0x100069df  mov     esi, eax
0x100069e1  test    esi, esi
0x100069e3  jns     short loc_100069EF
0x100069e5  push    offset aFailedToInitia_2; "failed to initialize"
0x100069ea  jmp     loc_10006B66
0x100069ef  lea     eax, [ebp+var_8]
0x100069f2  push    eax; int
0x100069f3  push    offset aWixshellexecbi_1; "WixShellExecBinaryId"
0x100069f8  call    sub_1000E3BD
0x100069fd  mov     esi, eax
0x100069ff  test    esi, esi
0x10006a01  js      loc_10006B61
0x10006a07  push    [ebp+var_8]
0x10006a0a  push    offset aWixshellexecbi_2; "WixShellExecBinaryId is %ls"
0x10006a0f  push    1
0x10006a11  call    sub_1000D9AB
0x10006a16  mov     eax, [ebp+var_8]
0x10006a19  add     esp, 0Ch
0x10006a1c  test    eax, eax
0x10006a1e  jz      loc_10006B5C
0x10006a24  cmp     [eax], di
0x10006a27  jz      loc_10006B5C
0x10006a2d  mov     esi, 104h
0x10006a32  lea     eax, [ebp+lpBuffer]
0x10006a35  push    esi
0x10006a36  push    eax
0x10006a37  call    ___std_fs_create_symbolic_link@8; __std_fs_create_symbolic_link(x,x)
0x10006a3c  push    [ebp+lpBuffer]; lpBuffer
0x10006a3f  push    esi; nBufferLength
0x10006a40  call    ds:GetTempPathW
0x10006a46  push    [ebp+var_8]
0x10006a49  push    esi
0x10006a4a  push    [ebp+lpBuffer]
0x10006a4d  call    sub_1000686B
0x10006a52  mov     esi, eax
0x10006a54  test    esi, esi
0x10006a56  jns     short loc_10006A62
0x10006a58  push    offset aFailedToAppend; "Failed to append filename."
0x10006a5d  jmp     loc_10006B66
0x10006a62  lea     eax, [ebp+nNumberOfBytesToWrite]
0x10006a65  push    eax; pcbDataBuf
0x10006a66  lea     eax, [ebp+var_C]
0x10006a69  push    eax; int
0x10006a6a  push    [ebp+var_8]; int
0x10006a6d  call    sub_1000660F
0x10006a72  mov     esi, eax
0x10006a74  test    esi, esi
0x10006a76  jns     short loc_10006A82
0x10006a78  push    offset aFailedToExtrac; "failed to extract binary data"
0x10006a7d  jmp     loc_10006B66
0x10006a82  push    edi; hTemplateFile
0x10006a83  push    80h; dwFlagsAndAttributes
0x10006a88  push    2; dwCreationDisposition
0x10006a8a  push    edi; lpSecurityAttributes
0x10006a8b  push    1; dwShareMode
0x10006a8d  push    40000000h; dwDesiredAccess
0x10006a92  push    [ebp+lpBuffer]; lpFileName
0x10006a95  call    ds:CreateFileW
0x10006a9b  mov     ebx, eax
0x10006a9d  cmp     ebx, 0FFFFFFFFh
0x10006aa0  jnz     short loc_10006AE6
0x10006aa2  call    ds:GetLastError
0x10006aa8  mov     esi, eax
0x10006aaa  test    esi, esi
0x10006aac  jle     short loc_10006AB9
0x10006aae  movzx   esi, si
0x10006ab1  or      esi, 80070000h
0x10006ab7  test    esi, esi
0x10006ab9  js      short loc_10006AC0
0x10006abb  mov     esi, 80004005h
0x10006ac0  push    esi
0x10006ac1  push    0C3h
0x10006ac6  push    offset aDAWork1SSrcExt_3; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006acb  call    nullsub_1
0x10006ad0  push    [ebp+lpBuffer]
0x10006ad3  push    offset aFailedToOpenNe; "Failed to open new temp file: %ls"
0x10006ad8  push    esi
0x10006ad9  call    sub_1000DA66
0x10006ade  add     esp, 0Ch
0x10006ae1  jmp     loc_10006B6E
0x10006ae6  push    edi; lpOverlapped
0x10006ae7  lea     eax, [ebp+NumberOfBytesWritten]
0x10006aea  mov     [ebp+NumberOfBytesWritten], edi
0x10006aed  push    eax; lpNumberOfBytesWritten
0x10006aee  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x10006af1  push    [ebp+var_C]; lpBuffer
0x10006af4  push    ebx; hFile
0x10006af5  call    ds:WriteFile
0x10006afb  test    eax, eax
0x10006afd  jnz     short loc_10006B37
0x10006aff  call    ds:GetLastError
0x10006b05  mov     esi, eax
0x10006b07  test    esi, esi
0x10006b09  jle     short loc_10006B16
0x10006b0b  movzx   esi, si
0x10006b0e  or      esi, 80070000h
0x10006b14  test    esi, esi
0x10006b16  js      short loc_10006B1D
0x10006b18  mov     esi, 80004005h
0x10006b1d  push    esi
0x10006b1e  push    0C9h
0x10006b23  push    offset aDAWork1SSrcExt_3; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006b28  call    nullsub_1
0x10006b2d  push    [ebp+lpBuffer]
0x10006b30  push    offset aFailedToWriteD; "Failed to write data to new temp file: "...
0x10006b35  jmp     short loc_10006AD8
0x10006b37  push    ebx; hObject
0x10006b38  call    ds:CloseHandle
0x10006b3e  push    [ebp+lpBuffer]; lpFile
0x10006b41  or      ebx, 0FFFFFFFFh
0x10006b44  call    sub_10006753
0x10006b49  mov     esi, eax
0x10006b4b  test    esi, esi
0x10006b4d  jns     short loc_10006B6E
0x10006b4f  push    [ebp+lpBuffer]
0x10006b52  push    offset aFailedToLaunch_0; "failed to launch target: %ls"
0x10006b57  jmp     loc_10006AD8
0x10006b5c  mov     esi, 80070057h
0x10006b61  push    offset aFailedToGetWix_0; "failed to get WixShellExecBinaryId"
0x10006b66  push    esi
0x10006b67  call    sub_1000DA66
0x10006b6c  pop     ecx
0x10006b6d  pop     ecx
0x10006b6e  cmp     [ebp+var_8], edi
0x10006b71  jz      short loc_10006B7B
0x10006b73  push    [ebp+var_8]
0x10006b76  call    sub_1000A952
0x10006b7b  cmp     [ebp+lpBuffer], edi
0x10006b7e  jz      short loc_10006B88
0x10006b80  push    [ebp+lpBuffer]
0x10006b83  call    sub_1000A952
0x10006b88  cmp     [ebp+var_C], edi
0x10006b8b  jz      short loc_10006B95
0x10006b8d  push    [ebp+var_C]; lpMem
0x10006b90  call    sub_1000AEFF
0x10006b95  cmp     ebx, 0FFFFFFFFh
0x10006b98  jz      short loc_10006BA1
0x10006b9a  push    ebx; hObject
0x10006b9b  call    ds:CloseHandle
0x10006ba1  test    esi, esi
0x10006ba3  jns     short loc_10006BAA
0x10006ba5  mov     edi, 643h
0x10006baa  push    edi
0x10006bab  call    sub_1000D4AE
0x10006bb0  pop     edi
0x10006bb1  pop     esi
0x10006bb2  pop     ebx
0x10006bb3  leave
0x10006bb4  retn    4
```
