# PSUI::_BCopyCachedFile(PSUI::_COMMONINFO *,PSUI::_CACHEDFILE *)

- ea: `0x1801324d0`
- end: `0x18013268f`
- name: `?_BCopyCachedFile@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_CACHEDFILE@1@@Z`
- size: `447`
- prototype: `__int64 __fastcall(PSUI *__hidden this, struct PSUI::_COMMONINFO *, struct PSUI::_CACHEDFILE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180131dcc`

## callees

- `0x180102674`
- `0x1801323f0`
- `0x1801324d0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x180132594`
- `KERNEL32!GetTempFileNameW` at `0x180132594`
- `KERNEL32!WriteFile` at `0x1801325fc`
- `KERNEL32!WriteFile` at `0x1801325fc`
- `KERNEL32!CreateDirectoryW` at `0x18013253b`
- `KERNEL32!CreateDirectoryW` at `0x18013253b`
- `KERNEL32!DeleteFileW` at `0x18013263d`
- `KERNEL32!DeleteFileW` at `0x18013263d`
- `KERNEL32!ReadFile` at `0x18013261c`
- `KERNEL32!ReadFile` at `0x18013261c`
- `KERNEL32!CreateFileW` at `0x180132568`
- `KERNEL32!CreateFileW` at `0x180132568`
- `KERNEL32!CloseHandle` at `0x180132630`
- `KERNEL32!CloseHandle` at `0x180132630`
- `KERNEL32!GetLastError` at `0x18013265e`
- `KERNEL32!GetLastError` at `0x18013265e`
- `KERNEL32!LocalFree` at `0x180132646`
- `KERNEL32!LocalFree` at `0x180132654`
- `KERNEL32!LocalFree` at `0x180132646`
- `KERNEL32!LocalFree` at `0x180132654`
- `KERNEL32!MoveFileExW` at `0x1801325ac`
- `KERNEL32!MoveFileExW` at `0x1801325c3`
- `KERNEL32!MoveFileExW` at `0x1801325ac`
- `KERNEL32!MoveFileExW` at `0x1801325c3`
- `KERNEL32!LocalAlloc` at `0x180132523`
- `KERNEL32!LocalAlloc` at `0x180132523`

## string_xrefs

- `0x180132667`: `Couldn't copy remote NTF/FontInfo file: %d\n`
- `0x18013266e`: `PSUI::_BCopyCachedFile`

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
0x1801324d0  mov     rax, rsp
0x1801324d3  mov     [rax+10h], rbx
0x1801324d7  mov     [rax+18h], rbp
0x1801324db  mov     [rax+8], rcx
0x1801324df  push    rsi
0x1801324e0  push    rdi
0x1801324e1  push    r14
0x1801324e3  sub     rsp, 40h
0x1801324e7  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1801324eb  mov     rdi, rdx
0x1801324ee  mov     dword ptr [rax+8], 0
0x1801324f5  jnz     short loc_180132501
0x1801324f7  mov     eax, 1
0x1801324fc  jmp     loc_18013267C
0x180132501  mov     rdx, [rdx+18h]; Str
0x180132505  xor     esi, esi
0x180132507  mov     rcx, [rdi+10h]; pszSrc
0x18013250b  call    ?PConcatFilename@PSUI@@YAPEAGPEAG0@Z; PSUI::PConcatFilename(ushort *,ushort *)
0x180132510  mov     rbp, rax
0x180132513  test    rax, rax
0x180132516  jz      loc_18013265E
0x18013251c  mov     edx, 1000h; uBytes
0x180132521  xor     ecx, ecx; uFlags
0x180132523  call    cs:__imp_LocalAlloc
0x180132529  mov     rbx, rax
0x18013252c  test    rax, rax
0x18013252f  jz      loc_180132643
0x180132535  mov     rcx, [rdi+10h]; lpPathName
0x180132539  xor     edx, edx; lpSecurityAttributes
0x18013253b  call    cs:__imp_CreateDirectoryW
0x180132541  mov     dword ptr [rsp+58h+NumberOfBytesWritten], esi
0x180132545  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x18013254a  xor     r9d, r9d; lpSecurityAttributes
0x18013254d  mov     [rsp+58h+dwFlagsAndAttributes], 8100000h; dwFlagsAndAttributes
0x180132555  xor     r8d, r8d; dwShareMode
0x180132558  mov     edx, 40000000h; dwDesiredAccess
0x18013255d  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180132565  mov     rcx, rbp; lpFileName
0x180132568  call    cs:__imp_CreateFileW
0x18013256e  mov     r14, rax
0x180132571  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180132575  jnz     loc_180132606
0x18013257b  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x18013257f  test    eax, eax
0x180132581  jnz     short loc_1801325D1
0x180132583  mov     rcx, [rdi+10h]; lpPathName
0x180132587  lea     rdx, aNtf; "NTF"
0x18013258e  mov     r9, rbx; lpTempFileName
0x180132591  xor     r8d, r8d; uUnique
0x180132594  call    cs:__imp_GetTempFileNameW
0x18013259a  test    eax, eax
0x18013259c  jz      loc_180132643
0x1801325a2  lea     r8d, [r14+2]; dwFlags
0x1801325a6  mov     rdx, rbx; lpNewFileName
0x1801325a9  mov     rcx, rbp; lpExistingFileName
0x1801325ac  call    cs:__imp_MoveFileExW
0x1801325b2  test    eax, eax
0x1801325b4  jz      loc_180132643
0x1801325ba  xor     edx, edx; lpNewFileName
0x1801325bc  lea     r8d, [r14+5]; dwFlags
0x1801325c0  mov     rcx, rbx; lpExistingFileName
0x1801325c3  call    cs:__imp_MoveFileExW
0x1801325c9  test    eax, eax
0x1801325cb  jz      short loc_180132643
0x1801325cd  mov     eax, dword ptr [rsp+58h+NumberOfBytesWritten]
0x1801325d1  inc     eax
0x1801325d3  mov     dword ptr [rsp+58h+NumberOfBytesWritten], eax
0x1801325d7  cmp     eax, 2
0x1801325da  jb      loc_180132545
0x1801325e0  jmp     short loc_180132643
0x1801325e2  mov     r8d, dword ptr [rsp+58h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x1801325e7  test    r8d, r8d
0x1801325ea  jz      short loc_180132628
0x1801325ec  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801325f1  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x1801325f6  mov     rdx, rbx; lpBuffer
0x1801325f9  mov     rcx, r14; hFile
0x1801325fc  call    cs:__imp_WriteFile
0x180132602  test    eax, eax
0x180132604  jz      short loc_18013262D
0x180132606  mov     rcx, [rdi]; hFile
0x180132609  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesRead
0x18013260e  mov     r8d, 1000h; nNumberOfBytesToRead
0x180132614  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOverlapped
0x180132619  mov     rdx, rbx; lpBuffer
0x18013261c  call    cs:__imp_ReadFile
0x180132622  test    eax, eax
0x180132624  jnz     short loc_1801325E2
0x180132626  jmp     short loc_18013262D
0x180132628  mov     esi, 1
0x18013262d  mov     rcx, r14; hObject
0x180132630  call    cs:__imp_CloseHandle
0x180132636  test    esi, esi
0x180132638  jnz     short loc_180132643
0x18013263a  mov     rcx, rbp; lpFileName
0x18013263d  call    cs:__imp_DeleteFileW
0x180132643  mov     rcx, rbp; hMem
0x180132646  call    cs:__imp_LocalFree
0x18013264c  test    rbx, rbx
0x18013264f  jz      short loc_18013265A
0x180132651  mov     rcx, rbx; hMem
0x180132654  call    cs:__imp_LocalFree
0x18013265a  test    esi, esi
0x18013265c  jnz     short loc_18013267A
0x18013265e  call    cs:__imp_GetLastError
0x180132664  mov     r8d, eax
0x180132667  lea     rdx, aCouldnTCopyRem; "Couldn't copy remote NTF/FontInfo file:"...
0x18013266e  lea     rcx, aPsuiBcopycache; "PSUI::_BCopyCachedFile"
0x180132675  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013267a  mov     eax, esi
0x18013267c  mov     rbx, [rsp+58h+arg_8]
0x180132681  mov     rbp, [rsp+58h+arg_10]
0x180132686  add     rsp, 40h
0x18013268a  pop     r14
0x18013268c  pop     rdi
0x18013268d  pop     rsi
0x18013268e  retn
```
