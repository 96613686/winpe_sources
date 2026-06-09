# PSUI::_BCopyCachedFile(PSUI::_COMMONINFO *,PSUI::_CACHEDFILE *)

- ea: `0x180138478`
- end: `0x18013868a`
- name: `?_BCopyCachedFile@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z`
- size: `530`
- prototype: `__int64 __fastcall(PSUI *__hidden this, struct PSUI::_COMMONINFO *, struct PSUI::_CACHEDFILE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180137dc4`

## callees

- `0x180107214`
- `0x180138380`
- `0x180138478`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18013854e`
- `KERNEL32!GetTempFileNameW` at `0x18013854e`
- `KERNEL32!WriteFile` at `0x1801385cc`
- `KERNEL32!WriteFile` at `0x1801385cc`
- `KERNEL32!CreateDirectoryW` at `0x1801384e9`
- `KERNEL32!CreateDirectoryW` at `0x1801384e9`
- `KERNEL32!DeleteFileW` at `0x18013861f`
- `KERNEL32!DeleteFileW` at `0x18013861f`
- `KERNEL32!ReadFile` at `0x1801385f2`
- `KERNEL32!ReadFile` at `0x1801385f2`
- `KERNEL32!CreateFileW` at `0x18013851c`
- `KERNEL32!CreateFileW` at `0x18013851c`
- `KERNEL32!CloseHandle` at `0x18013860c`
- `KERNEL32!CloseHandle` at `0x18013860c`
- `KERNEL32!GetLastError` at `0x180138652`
- `KERNEL32!GetLastError` at `0x180138652`
- `KERNEL32!LocalFree` at `0x18013862e`
- `KERNEL32!LocalFree` at `0x180138642`
- `KERNEL32!LocalFree` at `0x18013862e`
- `KERNEL32!LocalFree` at `0x180138642`
- `KERNEL32!MoveFileExW` at `0x18013856c`
- `KERNEL32!MoveFileExW` at `0x180138589`
- `KERNEL32!MoveFileExW` at `0x18013856c`
- `KERNEL32!MoveFileExW` at `0x180138589`
- `KERNEL32!LocalAlloc` at `0x1801384cb`
- `KERNEL32!LocalAlloc` at `0x1801384cb`

## string_xrefs

- `0x180138661`: `Couldn't copy remote NTF/FontInfo file: %d\n`
- `0x180138668`: `PSUI::_BCopyCachedFile`

## pseudocode

```c
__int64 __fastcall PSUI::_BCopyCachedFile(PSUI *this, struct PSUI::_COMMONINFO *a2, struct PSUI::_CACHEDFILE *a3)
{
  bool v3; // zf
  unsigned int v6; // esi
  WCHAR *v7; // rbp
  WCHAR *v8; // rbx
  HANDLE FileW; // r14
  int v10; // eax
  DWORD LastError; // eax
  PSUI *NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  v3 = *(_QWORD *)a2 == -1;
  LODWORD(NumberOfBytesWritten) = 0;
  if ( v3 )
    return 1;
  v6 = 0;
  v7 = PSUI::PConcatFilename(*((STRSAFE_LPCWSTR *)a2 + 2), *((wchar_t **)a2 + 3), (unsigned __int16 *)a3);
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
        if ( !GetTempFileNameW(*((LPCWSTR *)a2 + 2), L"NTF", 0, v8)
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
      "PSUI::_BCopyCachedFile",
      L"Couldn't copy remote NTF/FontInfo file: %d\n",
      LastError);
  }
  return v6;
}

```

## disassembly

```asm
0x180138478  mov     rax, rsp
0x18013847b  mov     [rax+10h], rbx
0x18013847f  mov     [rax+18h], rbp
0x180138483  mov     [rax+8], rcx
0x180138487  push    rsi
0x180138488  push    rdi
0x180138489  push    r14
0x18013848b  sub     rsp, 40h
0x18013848f  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180138493  mov     rdi, rdx
0x180138496  mov     dword ptr [rax+8], 0
0x18013849d  jnz     short loc_1801384A9
0x18013849f  mov     eax, 1
0x1801384a4  jmp     loc_180138676
0x1801384a9  mov     rdx, [rdx+18h]; Str
0x1801384ad  xor     esi, esi
0x1801384af  mov     rcx, [rdi+10h]; pszSrc
0x1801384b3  call    ?PConcatFilename@PSUI@@YAPEAGPEAG0@Z; PSUI::PConcatFilename(ushort *,ushort *)
0x1801384b8  mov     rbp, rax
0x1801384bb  test    rax, rax
0x1801384be  jz      loc_180138652
0x1801384c4  mov     edx, 1000h; uBytes
0x1801384c9  xor     ecx, ecx; uFlags
0x1801384cb  call    cs:__imp_LocalAlloc
0x1801384d2  nop     dword ptr [rax+rax+00h]
0x1801384d7  mov     rbx, rax
0x1801384da  test    rax, rax
0x1801384dd  jz      loc_18013862B
0x1801384e3  mov     rcx, [rdi+10h]; lpPathName
0x1801384e7  xor     edx, edx; lpSecurityAttributes
0x1801384e9  call    cs:__imp_CreateDirectoryW
0x1801384f0  nop     dword ptr [rax+rax+00h]
0x1801384f5  mov     dword ptr [rsp+58h+NumberOfBytesWritten], esi
0x1801384f9  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x1801384fe  xor     r9d, r9d; lpSecurityAttributes
0x180138501  mov     [rsp+58h+dwFlagsAndAttributes], 8100000h; dwFlagsAndAttributes
0x180138509  xor     r8d, r8d; dwShareMode
0x18013850c  mov     edx, 40000000h; dwDesiredAccess
0x180138511  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180138519  mov     rcx, rbp; lpFileName
0x18013851c  call    cs:__imp_CreateFileW
0x180138523  nop     dword ptr [rax+rax+00h]
0x180138528  mov     r14, rax
0x18013852b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013852f  jnz     loc_1801385DC
0x180138535  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x180138539  test    eax, eax
0x18013853b  jnz     short loc_1801385A1
0x18013853d  mov     rcx, [rdi+10h]; lpPathName
0x180138541  lea     rdx, aNtf; "NTF"
0x180138548  mov     r9, rbx; lpTempFileName
0x18013854b  xor     r8d, r8d; uUnique
0x18013854e  call    cs:__imp_GetTempFileNameW
0x180138555  nop     dword ptr [rax+rax+00h]
0x18013855a  test    eax, eax
0x18013855c  jz      loc_18013862B
0x180138562  lea     r8d, [r14+2]; dwFlags
0x180138566  mov     rdx, rbx; lpNewFileName
0x180138569  mov     rcx, rbp; lpExistingFileName
0x18013856c  call    cs:__imp_MoveFileExW
0x180138573  nop     dword ptr [rax+rax+00h]
0x180138578  test    eax, eax
0x18013857a  jz      loc_18013862B
0x180138580  xor     edx, edx; lpNewFileName
0x180138582  lea     r8d, [r14+5]; dwFlags
0x180138586  mov     rcx, rbx; lpExistingFileName
0x180138589  call    cs:__imp_MoveFileExW
0x180138590  nop     dword ptr [rax+rax+00h]
0x180138595  test    eax, eax
0x180138597  jz      loc_18013862B
0x18013859d  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x1801385a1  inc     eax
0x1801385a3  mov     dword ptr [rsp+58h+NumberOfBytesWritten], eax
0x1801385a7  cmp     eax, 2
0x1801385aa  jb      loc_1801384F9
0x1801385b0  jmp     short loc_18013862B
0x1801385b2  mov     r8d, dword ptr [rsp+58h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x1801385b7  test    r8d, r8d
0x1801385ba  jz      short loc_180138604
0x1801385bc  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801385c1  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x1801385c6  mov     rdx, rbx; lpBuffer
0x1801385c9  mov     rcx, r14; hFile
0x1801385cc  call    cs:__imp_WriteFile
0x1801385d3  nop     dword ptr [rax+rax+00h]
0x1801385d8  test    eax, eax
0x1801385da  jz      short loc_180138609
0x1801385dc  mov     rcx, [rdi]; hFile
0x1801385df  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x1801385e4  mov     r8d, 1000h; nNumberOfBytesToRead
0x1801385ea  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x1801385ef  mov     rdx, rbx; lpBuffer
0x1801385f2  call    cs:__imp_ReadFile
0x1801385f9  nop     dword ptr [rax+rax+00h]
0x1801385fe  test    eax, eax
0x180138600  jnz     short loc_1801385B2
0x180138602  jmp     short loc_180138609
0x180138604  mov     esi, 1
0x180138609  mov     rcx, r14; hObject
0x18013860c  call    cs:__imp_CloseHandle
0x180138613  nop     dword ptr [rax+rax+00h]
0x180138618  test    esi, esi
0x18013861a  jnz     short loc_18013862B
0x18013861c  mov     rcx, rbp; lpFileName
0x18013861f  call    cs:__imp_DeleteFileW
0x180138626  nop     dword ptr [rax+rax+00h]
0x18013862b  mov     rcx, rbp; hMem
0x18013862e  call    cs:__imp_LocalFree
0x180138635  nop     dword ptr [rax+rax+00h]
0x18013863a  test    rbx, rbx
0x18013863d  jz      short loc_18013864E
0x18013863f  mov     rcx, rbx; hMem
0x180138642  call    cs:__imp_LocalFree
0x180138649  nop     dword ptr [rax+rax+00h]
0x18013864e  test    esi, esi
0x180138650  jnz     short loc_180138674
0x180138652  call    cs:__imp_GetLastError
0x180138659  nop     dword ptr [rax+rax+00h]
0x18013865e  mov     r8d, eax
0x180138661  lea     rdx, aCouldnTCopyRem; "Couldn't copy remote NTF/FontInfo file:"...
0x180138668  lea     rcx, aPsuiBcopycache; "PSUI::_BCopyCachedFile"
0x18013866f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180138674  mov     eax, esi
0x180138676  mov     rbx, [rsp+58h+arg_8]
0x18013867b  mov     rbp, [rsp+58h+arg_10]
0x180138680  add     rsp, 40h
0x180138684  pop     r14
0x180138686  pop     rdi
0x180138687  pop     rsi
0x180138688  retn
```
