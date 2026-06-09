# UniDrvUI::_BCopyCachedFile(UniDrvUI::_COMMONINFO *,UniDrvUI::_CACHEDFILE *)

- ea: `0x18010fcb8`
- end: `0x18010feca`
- name: `?_BCopyCachedFile@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z`
- size: `530`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, struct UniDrvUI::_CACHEDFILE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18010f0b4`
- `0x1801266a8`

## callees

- `0x180107214`
- `0x18010f97c`
- `0x18010fcb8`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18010fd8e`
- `KERNEL32!GetTempFileNameW` at `0x18010fd8e`
- `KERNEL32!WriteFile` at `0x18010fe0c`
- `KERNEL32!WriteFile` at `0x18010fe0c`
- `KERNEL32!CreateDirectoryW` at `0x18010fd29`
- `KERNEL32!CreateDirectoryW` at `0x18010fd29`
- `KERNEL32!DeleteFileW` at `0x18010fe5f`
- `KERNEL32!DeleteFileW` at `0x18010fe5f`
- `KERNEL32!ReadFile` at `0x18010fe32`
- `KERNEL32!ReadFile` at `0x18010fe32`
- `KERNEL32!CreateFileW` at `0x18010fd5c`
- `KERNEL32!CreateFileW` at `0x18010fd5c`
- `KERNEL32!CloseHandle` at `0x18010fe4c`
- `KERNEL32!CloseHandle` at `0x18010fe4c`
- `KERNEL32!GetLastError` at `0x18010fe92`
- `KERNEL32!GetLastError` at `0x18010fe92`
- `KERNEL32!LocalFree` at `0x18010fe6e`
- `KERNEL32!LocalFree` at `0x18010fe82`
- `KERNEL32!LocalFree` at `0x18010fe6e`
- `KERNEL32!LocalFree` at `0x18010fe82`
- `KERNEL32!MoveFileExW` at `0x18010fdac`
- `KERNEL32!MoveFileExW` at `0x18010fdc9`
- `KERNEL32!MoveFileExW` at `0x18010fdac`
- `KERNEL32!MoveFileExW` at `0x18010fdc9`
- `KERNEL32!LocalAlloc` at `0x18010fd0b`
- `KERNEL32!LocalAlloc` at `0x18010fd0b`

## string_xrefs

- `0x18010fea8`: `UniDrvUI::_BCopyCachedFile`
- `0x18010fea1`: `Couldn't copy remote NTF/FontInfo file: %d\n`

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
0x18010fcb8  mov     rax, rsp
0x18010fcbb  mov     [rax+10h], rbx
0x18010fcbf  mov     [rax+18h], rbp
0x18010fcc3  mov     [rax+8], rcx
0x18010fcc7  push    rsi
0x18010fcc8  push    rdi
0x18010fcc9  push    r14
0x18010fccb  sub     rsp, 40h
0x18010fccf  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18010fcd3  mov     rdi, rdx
0x18010fcd6  mov     dword ptr [rax+8], 0
0x18010fcdd  jnz     short loc_18010FCE9
0x18010fcdf  mov     eax, 1
0x18010fce4  jmp     loc_18010FEB6
0x18010fce9  mov     rdx, [rdx+18h]; Str
0x18010fced  xor     esi, esi
0x18010fcef  mov     rcx, [rdi+10h]; pszSrc
0x18010fcf3  call    ?PConcatFilename@UniDrvUI@@YAPEAGPEAG0@Z; UniDrvUI::PConcatFilename(ushort *,ushort *)
0x18010fcf8  mov     rbp, rax
0x18010fcfb  test    rax, rax
0x18010fcfe  jz      loc_18010FE92
0x18010fd04  mov     edx, 1000h; uBytes
0x18010fd09  xor     ecx, ecx; uFlags
0x18010fd0b  call    cs:__imp_LocalAlloc
0x18010fd12  nop     dword ptr [rax+rax+00h]
0x18010fd17  mov     rbx, rax
0x18010fd1a  test    rax, rax
0x18010fd1d  jz      loc_18010FE6B
0x18010fd23  mov     rcx, [rdi+10h]; lpPathName
0x18010fd27  xor     edx, edx; lpSecurityAttributes
0x18010fd29  call    cs:__imp_CreateDirectoryW
0x18010fd30  nop     dword ptr [rax+rax+00h]
0x18010fd35  mov     dword ptr [rsp+58h+NumberOfBytesWritten], esi
0x18010fd39  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x18010fd3e  xor     r9d, r9d; lpSecurityAttributes
0x18010fd41  mov     [rsp+58h+dwFlagsAndAttributes], 8100000h; dwFlagsAndAttributes
0x18010fd49  xor     r8d, r8d; dwShareMode
0x18010fd4c  mov     edx, 40000000h; dwDesiredAccess
0x18010fd51  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x18010fd59  mov     rcx, rbp; lpFileName
0x18010fd5c  call    cs:__imp_CreateFileW
0x18010fd63  nop     dword ptr [rax+rax+00h]
0x18010fd68  mov     r14, rax
0x18010fd6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010fd6f  jnz     loc_18010FE1C
0x18010fd75  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x18010fd79  test    eax, eax
0x18010fd7b  jnz     short loc_18010FDE1
0x18010fd7d  mov     rcx, [rdi+10h]; lpPathName
0x18010fd81  lea     rdx, aFon; "FON"
0x18010fd88  mov     r9, rbx; lpTempFileName
0x18010fd8b  xor     r8d, r8d; uUnique
0x18010fd8e  call    cs:__imp_GetTempFileNameW
0x18010fd95  nop     dword ptr [rax+rax+00h]
0x18010fd9a  test    eax, eax
0x18010fd9c  jz      loc_18010FE6B
0x18010fda2  lea     r8d, [r14+2]; dwFlags
0x18010fda6  mov     rdx, rbx; lpNewFileName
0x18010fda9  mov     rcx, rbp; lpExistingFileName
0x18010fdac  call    cs:__imp_MoveFileExW
0x18010fdb3  nop     dword ptr [rax+rax+00h]
0x18010fdb8  test    eax, eax
0x18010fdba  jz      loc_18010FE6B
0x18010fdc0  xor     edx, edx; lpNewFileName
0x18010fdc2  lea     r8d, [r14+5]; dwFlags
0x18010fdc6  mov     rcx, rbx; lpExistingFileName
0x18010fdc9  call    cs:__imp_MoveFileExW
0x18010fdd0  nop     dword ptr [rax+rax+00h]
0x18010fdd5  test    eax, eax
0x18010fdd7  jz      loc_18010FE6B
0x18010fddd  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x18010fde1  inc     eax
0x18010fde3  mov     dword ptr [rsp+58h+NumberOfBytesWritten], eax
0x18010fde7  cmp     eax, 2
0x18010fdea  jb      loc_18010FD39
0x18010fdf0  jmp     short loc_18010FE6B
0x18010fdf2  mov     r8d, dword ptr [rsp+58h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x18010fdf7  test    r8d, r8d
0x18010fdfa  jz      short loc_18010FE44
0x18010fdfc  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18010fe01  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x18010fe06  mov     rdx, rbx; lpBuffer
0x18010fe09  mov     rcx, r14; hFile
0x18010fe0c  call    cs:__imp_WriteFile
0x18010fe13  nop     dword ptr [rax+rax+00h]
0x18010fe18  test    eax, eax
0x18010fe1a  jz      short loc_18010FE49
0x18010fe1c  mov     rcx, [rdi]; hFile
0x18010fe1f  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x18010fe24  mov     r8d, 1000h; nNumberOfBytesToRead
0x18010fe2a  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x18010fe2f  mov     rdx, rbx; lpBuffer
0x18010fe32  call    cs:__imp_ReadFile
0x18010fe39  nop     dword ptr [rax+rax+00h]
0x18010fe3e  test    eax, eax
0x18010fe40  jnz     short loc_18010FDF2
0x18010fe42  jmp     short loc_18010FE49
0x18010fe44  mov     esi, 1
0x18010fe49  mov     rcx, r14; hObject
0x18010fe4c  call    cs:__imp_CloseHandle
0x18010fe53  nop     dword ptr [rax+rax+00h]
0x18010fe58  test    esi, esi
0x18010fe5a  jnz     short loc_18010FE6B
0x18010fe5c  mov     rcx, rbp; lpFileName
0x18010fe5f  call    cs:__imp_DeleteFileW
0x18010fe66  nop     dword ptr [rax+rax+00h]
0x18010fe6b  mov     rcx, rbp; hMem
0x18010fe6e  call    cs:__imp_LocalFree
0x18010fe75  nop     dword ptr [rax+rax+00h]
0x18010fe7a  test    rbx, rbx
0x18010fe7d  jz      short loc_18010FE8E
0x18010fe7f  mov     rcx, rbx; hMem
0x18010fe82  call    cs:__imp_LocalFree
0x18010fe89  nop     dword ptr [rax+rax+00h]
0x18010fe8e  test    esi, esi
0x18010fe90  jnz     short loc_18010FEB4
0x18010fe92  call    cs:__imp_GetLastError
0x18010fe99  nop     dword ptr [rax+rax+00h]
0x18010fe9e  mov     r8d, eax
0x18010fea1  lea     rdx, aCouldnTCopyRem; "Couldn't copy remote NTF/FontInfo file:"...
0x18010fea8  lea     rcx, aUnidrvuiBcopyc; "UniDrvUI::_BCopyCachedFile"
0x18010feaf  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010feb4  mov     eax, esi
0x18010feb6  mov     rbx, [rsp+58h+arg_8]
0x18010febb  mov     rbp, [rsp+58h+arg_10]
0x18010fec0  add     rsp, 40h
0x18010fec4  pop     r14
0x18010fec6  pop     rdi
0x18010fec7  pop     rsi
0x18010fec8  retn
```
