# UniDrvUI::_BCopyCachedFile(UniDrvUI::_COMMONINFO *,UniDrvUI::_CACHEDFILE *)

- ea: `0x18010b084`
- end: `0x18010b243`
- name: `?_BCopyCachedFile@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z`
- size: `447`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, struct UniDrvUI::_CACHEDFILE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18010a2fc`
- `0x180120e58`

## callees

- `0x180102674`
- `0x18010adb0`
- `0x18010b084`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18010b148`
- `KERNEL32!GetTempFileNameW` at `0x18010b148`
- `KERNEL32!WriteFile` at `0x18010b1b0`
- `KERNEL32!WriteFile` at `0x18010b1b0`
- `KERNEL32!CreateDirectoryW` at `0x18010b0ef`
- `KERNEL32!CreateDirectoryW` at `0x18010b0ef`
- `KERNEL32!DeleteFileW` at `0x18010b1f1`
- `KERNEL32!DeleteFileW` at `0x18010b1f1`
- `KERNEL32!ReadFile` at `0x18010b1d0`
- `KERNEL32!ReadFile` at `0x18010b1d0`
- `KERNEL32!CreateFileW` at `0x18010b11c`
- `KERNEL32!CreateFileW` at `0x18010b11c`
- `KERNEL32!CloseHandle` at `0x18010b1e4`
- `KERNEL32!CloseHandle` at `0x18010b1e4`
- `KERNEL32!GetLastError` at `0x18010b212`
- `KERNEL32!GetLastError` at `0x18010b212`
- `KERNEL32!LocalFree` at `0x18010b1fa`
- `KERNEL32!LocalFree` at `0x18010b208`
- `KERNEL32!LocalFree` at `0x18010b1fa`
- `KERNEL32!LocalFree` at `0x18010b208`
- `KERNEL32!MoveFileExW` at `0x18010b160`
- `KERNEL32!MoveFileExW` at `0x18010b177`
- `KERNEL32!MoveFileExW` at `0x18010b160`
- `KERNEL32!MoveFileExW` at `0x18010b177`
- `KERNEL32!LocalAlloc` at `0x18010b0d7`
- `KERNEL32!LocalAlloc` at `0x18010b0d7`

## string_xrefs

- `0x18010b21b`: `Couldn't copy remote NTF/FontInfo file: %d\n`
- `0x18010b222`: `UniDrvUI::_BCopyCachedFile`

## pseudocode

```c
__int64 __fastcall UniDrvUI::_BCopyCachedFile(
        UniDrvUI *this,
        struct UniDrvUI::_COMMONINFO *a2,
        struct UniDrvUI::_CACHEDFILE *a3)
{
  bool v3; // zf
  unsigned int v6; // esi
  WCHAR *v7; // rbp
  WCHAR *v8; // rbx
  HANDLE FileW; // r14
  int v10; // eax
  DWORD LastError; // eax
  UniDrvUI *NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  v3 = *(_QWORD *)a2 == -1;
  LODWORD(NumberOfBytesWritten) = 0;
  if ( v3 )
    return 1;
  v6 = 0;
  v7 = UniDrvUI::PConcatFilename(*((STRSAFE_LPCWSTR *)a2 + 2), *((wchar_t **)a2 + 3), (unsigned __int16 *)a3);
  if ( !v7 )
    goto LABEL_24;
  v8 = (WCHAR *)LocalAlloc(0, 0x1000u);
  if ( v8 )
  {
    CreateDirectoryW(*((LPCWSTR *)a2 + 2), 0);
    LODWORD(NumberOfBytesWritten) = 0;
    while ( 1 )
    {
      FileW = CreateFileW(v7, 0x40000000u, 0, 0, 2u, 0x8100000u, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      v10 = (int)NumberOfBytesWritten;
      if ( !(_DWORD)NumberOfBytesWritten )
      {
        if ( !GetTempFileNameW(*((LPCWSTR *)a2 + 2), L"FON", 0, v8)
          || !MoveFileExW(v7, v8, 1u)
          || !MoveFileExW(v8, 0, 4u) )
        {
          goto LABEL_21;
        }
        v10 = (int)NumberOfBytesWritten;
      }
      LODWORD(NumberOfBytesWritten) = v10 + 1;
      if ( (unsigned int)(v10 + 1) >= 2 )
        goto LABEL_21;
    }
    while ( ReadFile(*(HANDLE *)a2, v8, 0x1000u, (LPDWORD)&NumberOfBytesWritten, 0) )
    {
      if ( !(_DWORD)NumberOfBytesWritten )
      {
        v6 = 1;
        break;
      }
      if ( !WriteFile(FileW, v8, (DWORD)NumberOfBytesWritten, (LPDWORD)&NumberOfBytesWritten, 0) )
        break;
    }
    CloseHandle(FileW);
    if ( !v6 )
      DeleteFileW(v7);
  }
LABEL_21:
  LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  if ( !v6 )
  {
LABEL_24:
    LastError = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::_BCopyCachedFile",
      L"Couldn't copy remote NTF/FontInfo file: %d\n",
      LastError);
  }
  return v6;
}

```

## disassembly

```asm
0x18010b084  mov     rax, rsp
0x18010b087  mov     [rax+10h], rbx
0x18010b08b  mov     [rax+18h], rbp
0x18010b08f  mov     [rax+8], rcx
0x18010b093  push    rsi
0x18010b094  push    rdi
0x18010b095  push    r14
0x18010b097  sub     rsp, 40h
0x18010b09b  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18010b09f  mov     rdi, rdx
0x18010b0a2  mov     dword ptr [rax+8], 0
0x18010b0a9  jnz     short loc_18010B0B5
0x18010b0ab  mov     eax, 1
0x18010b0b0  jmp     loc_18010B230
0x18010b0b5  mov     rdx, [rdx+18h]; Str
0x18010b0b9  xor     esi, esi
0x18010b0bb  mov     rcx, [rdi+10h]; pszSrc
0x18010b0bf  call    ?PConcatFilename@UniDrvUI@@YAPEAGPEAG0@Z; UniDrvUI::PConcatFilename(ushort *,ushort *)
0x18010b0c4  mov     rbp, rax
0x18010b0c7  test    rax, rax
0x18010b0ca  jz      loc_18010B212
0x18010b0d0  mov     edx, 1000h; uBytes
0x18010b0d5  xor     ecx, ecx; uFlags
0x18010b0d7  call    cs:__imp_LocalAlloc
0x18010b0dd  mov     rbx, rax
0x18010b0e0  test    rax, rax
0x18010b0e3  jz      loc_18010B1F7
0x18010b0e9  mov     rcx, [rdi+10h]; lpPathName
0x18010b0ed  xor     edx, edx; lpSecurityAttributes
0x18010b0ef  call    cs:__imp_CreateDirectoryW
0x18010b0f5  mov     dword ptr [rsp+58h+NumberOfBytesWritten], esi
0x18010b0f9  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x18010b0fe  xor     r9d, r9d; lpSecurityAttributes
0x18010b101  mov     [rsp+58h+dwFlagsAndAttributes], 8100000h; dwFlagsAndAttributes
0x18010b109  xor     r8d, r8d; dwShareMode
0x18010b10c  mov     edx, 40000000h; dwDesiredAccess
0x18010b111  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x18010b119  mov     rcx, rbp; lpFileName
0x18010b11c  call    cs:__imp_CreateFileW
0x18010b122  mov     r14, rax
0x18010b125  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010b129  jnz     loc_18010B1BA
0x18010b12f  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x18010b133  test    eax, eax
0x18010b135  jnz     short loc_18010B185
0x18010b137  mov     rcx, [rdi+10h]; lpPathName
0x18010b13b  lea     rdx, aFon; "FON"
0x18010b142  mov     r9, rbx; lpTempFileName
0x18010b145  xor     r8d, r8d; uUnique
0x18010b148  call    cs:__imp_GetTempFileNameW
0x18010b14e  test    eax, eax
0x18010b150  jz      loc_18010B1F7
0x18010b156  lea     r8d, [r14+2]; dwFlags
0x18010b15a  mov     rdx, rbx; lpNewFileName
0x18010b15d  mov     rcx, rbp; lpExistingFileName
0x18010b160  call    cs:__imp_MoveFileExW
0x18010b166  test    eax, eax
0x18010b168  jz      loc_18010B1F7
0x18010b16e  xor     edx, edx; lpNewFileName
0x18010b170  lea     r8d, [r14+5]; dwFlags
0x18010b174  mov     rcx, rbx; lpExistingFileName
0x18010b177  call    cs:__imp_MoveFileExW
0x18010b17d  test    eax, eax
0x18010b17f  jz      short loc_18010B1F7
0x18010b181  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x18010b185  inc     eax
0x18010b187  mov     dword ptr [rsp+58h+NumberOfBytesWritten], eax
0x18010b18b  cmp     eax, 2
0x18010b18e  jb      loc_18010B0F9
0x18010b194  jmp     short loc_18010B1F7
0x18010b196  mov     r8d, dword ptr [rsp+58h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x18010b19b  test    r8d, r8d
0x18010b19e  jz      short loc_18010B1DC
0x18010b1a0  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18010b1a5  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x18010b1aa  mov     rdx, rbx; lpBuffer
0x18010b1ad  mov     rcx, r14; hFile
0x18010b1b0  call    cs:__imp_WriteFile
0x18010b1b6  test    eax, eax
0x18010b1b8  jz      short loc_18010B1E1
0x18010b1ba  mov     rcx, [rdi]; hFile
0x18010b1bd  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x18010b1c2  mov     r8d, 1000h; nNumberOfBytesToRead
0x18010b1c8  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x18010b1cd  mov     rdx, rbx; lpBuffer
0x18010b1d0  call    cs:__imp_ReadFile
0x18010b1d6  test    eax, eax
0x18010b1d8  jnz     short loc_18010B196
0x18010b1da  jmp     short loc_18010B1E1
0x18010b1dc  mov     esi, 1
0x18010b1e1  mov     rcx, r14; hObject
0x18010b1e4  call    cs:__imp_CloseHandle
0x18010b1ea  test    esi, esi
0x18010b1ec  jnz     short loc_18010B1F7
0x18010b1ee  mov     rcx, rbp; lpFileName
0x18010b1f1  call    cs:__imp_DeleteFileW
0x18010b1f7  mov     rcx, rbp; hMem
0x18010b1fa  call    cs:__imp_LocalFree
0x18010b200  test    rbx, rbx
0x18010b203  jz      short loc_18010B20E
0x18010b205  mov     rcx, rbx; hMem
0x18010b208  call    cs:__imp_LocalFree
0x18010b20e  test    esi, esi
0x18010b210  jnz     short loc_18010B22E
0x18010b212  call    cs:__imp_GetLastError
0x18010b218  mov     r8d, eax
0x18010b21b  lea     rdx, aCouldnTCopyRem; "Couldn't copy remote NTF/FontInfo file:"...
0x18010b222  lea     rcx, aUnidrvuiBcopyc; "UniDrvUI::_BCopyCachedFile"
0x18010b229  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010b22e  mov     eax, esi
0x18010b230  mov     rbx, [rsp+58h+arg_8]
0x18010b235  mov     rbp, [rsp+58h+arg_10]
0x18010b23a  add     rsp, 40h
0x18010b23e  pop     r14
0x18010b240  pop     rdi
0x18010b241  pop     rsi
0x18010b242  retn
```
