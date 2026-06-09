# XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)

- ea: `0x180012e20`
- end: `0x180013081`
- name: `?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z`
- size: `609`
- prototype: `int(XPerfCore::CFileMapping *__hidden this, const unsigned __int16 *, bool, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f5dc`
- `0x1800275f8`

## callees

- `0x180012e20`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012e68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012e68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012ebf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fae`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012f84`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012f84`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180012fd7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180012fd7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012f45`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012f45`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180012e76`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180012e76`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180012e8c`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180012e8c`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180012ed4`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180012ed4`

## string_xrefs

- `0x180012ef5`: `CreateFile failed: %d`
- `0x180012f66`: `CreateFileMapping failed: %d`

## pseudocode

```c
int __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly2(
        XPerfCore::CFileMapping *this,
        const unsigned __int16 *a2,
        char a3,
        struct XPerfCore::IErrorMessage *a4)
{
  HANDLE CurrentProcess; // rax
  void (*v9)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...); // rbx
  DWORD v10; // eax
  int result; // eax
  HANDLE FileMappingW; // rax
  void (__fastcall *v13)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD LastError; // eax
  const void *v15; // rcx
  void *v16; // rcx
  unsigned int *v17; // rcx
  void (__fastcall *v18)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD); // rbx
  DWORD v19; // eax
  __int64 v20; // rax
  unsigned int v21; // edx
  char *v22; // rcx
  PVOID OldValue; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL Wow64Process; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_OWORD *)this != 0xFFFFFFFFFFFFFFFFuLL || *((_QWORD *)this + 2) )
    return -2147483634;
  Wow64Process = 0;
  OldValue = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
    Wow64Process = Wow64DisableWow64FsRedirection(&OldValue);
  *(_QWORD *)this = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue);
  if ( *(_QWORD *)this != -1 )
  {
    FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, a3 != 0 ? 285212674 : 2, 0, 0, 0);
    *((_QWORD *)this + 1) = FileMappingW;
    if ( !FileMappingW )
    {
      if ( a4 )
      {
        v13 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        LastError = GetLastError();
        v13(a4, L"CreateFileMapping failed: %d", LastError);
      }
LABEL_16:
      v15 = (const void *)*((_QWORD *)this + 2);
      if ( v15 )
      {
        UnmapViewOfFile(v15);
        *((_QWORD *)this + 2) = 0;
      }
      v16 = (void *)*((_QWORD *)this + 1);
      if ( v16 )
      {
        CloseHandle(v16);
        *((_QWORD *)this + 1) = 0;
      }
      if ( *(_QWORD *)this != -1 )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = -1;
      }
      goto LABEL_11;
    }
    v17 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v17;
    if ( !v17 )
    {
      if ( a4 )
      {
        v18 = *(void (__fastcall **)(struct XPerfCore::IErrorMessage *, const wchar_t *, _QWORD))(*(_QWORD *)a4 + 8LL);
        v19 = GetLastError();
        v18(a4, L"MapViewOfFileEx failed: %d", v19);
      }
      goto LABEL_16;
    }
    if ( *(_WORD *)v17 == 23117 )
    {
      v20 = v17[15];
      if ( (v20 & 3) == 0 && (_DWORD)v20 != -1 )
      {
        v21 = ~(_DWORD)v20;
        if ( (unsigned int)~(_DWORD)v20 >= 0x1B )
        {
          v22 = (char *)v17 + v20;
          if ( *(_DWORD *)v22 == 17744 )
          {
            if ( *((_WORD *)v22 + 12) == 267 )
            {
              if ( v21 > 0xF8 )
              {
LABEL_36:
                *((_QWORD *)this + 3) = *((unsigned int *)v22 + 20);
                return 0;
              }
            }
            else if ( *((_WORD *)v22 + 12) == 523 && v21 > 0x108 )
            {
              goto LABEL_36;
            }
          }
        }
      }
    }
    v22 = 0;
    goto LABEL_36;
  }
  if ( a4 )
  {
    v9 = *(void (**)(struct XPerfCore::IErrorMessage *, const wchar_t *, ...))(*(_QWORD *)a4 + 8LL);
    v10 = GetLastError();
    v9(a4, L"CreateFile failed: %d", v10);
  }
LABEL_11:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180012e20  mov     rax, rsp
0x180012e23  mov     [rax+10h], rbx
0x180012e27  mov     [rax+18h], rbp
0x180012e2b  push    rsi
0x180012e2c  push    rdi
0x180012e2d  push    r14
0x180012e2f  sub     rsp, 50h
0x180012e33  mov     rsi, r9
0x180012e36  mov     bpl, r8b
0x180012e39  mov     rbx, rdx
0x180012e3c  mov     rdi, rcx
0x180012e3f  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180012e43  jnz     loc_180013067
0x180012e49  xor     r14d, r14d
0x180012e4c  cmp     [rcx+8], r14
0x180012e50  jnz     loc_180013067
0x180012e56  cmp     [rcx+10h], r14
0x180012e5a  jnz     loc_180013067
0x180012e60  mov     [rax+8], r14d
0x180012e64  mov     [rax-28h], r14
0x180012e68  call    cs:__imp_GetCurrentProcess
0x180012e6e  mov     rcx, rax; hProcess
0x180012e71  lea     rdx, [rsp+68h+Wow64Process]; Wow64Process
0x180012e76  call    cs:__imp_IsWow64Process
0x180012e7c  test    eax, eax
0x180012e7e  jz      short loc_180012E9B
0x180012e80  cmp     [rsp+68h+Wow64Process], 1
0x180012e85  jnz     short loc_180012E9B
0x180012e87  lea     rcx, [rsp+68h+OldValue]; OldValue
0x180012e8c  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180012e92  test    eax, eax
0x180012e94  jnz     short loc_180012E9B
0x180012e96  mov     [rsp+68h+Wow64Process], r14d
0x180012e9b  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180012ea0  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180012ea8  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180012eb0  xor     r9d, r9d; lpSecurityAttributes
0x180012eb3  mov     edx, 80000000h; dwDesiredAccess
0x180012eb8  lea     r8d, [r9+1]; dwShareMode
0x180012ebc  mov     rcx, rbx; lpFileName
0x180012ebf  call    cs:__imp_CreateFileW
0x180012ec5  mov     [rdi], rax
0x180012ec8  cmp     [rsp+68h+Wow64Process], r14d
0x180012ecd  jz      short loc_180012EDA
0x180012ecf  mov     rcx, [rsp+68h+OldValue]; OlValue
0x180012ed4  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180012eda  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180012ede  jnz     short loc_180012F22
0x180012ee0  test    rsi, rsi
0x180012ee3  jz      short loc_180012F07
0x180012ee5  mov     rax, [rsi]
0x180012ee8  mov     rbx, [rax+8]
0x180012eec  call    cs:__imp_GetLastError
0x180012ef2  mov     r8d, eax
0x180012ef5  lea     rdx, aCreatefileFail; "CreateFile failed: %d"
0x180012efc  mov     rcx, rsi
0x180012eff  mov     rax, rbx
0x180012f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f07  call    cs:__imp_GetLastError
0x180012f0d  test    eax, eax
0x180012f0f  jle     loc_18001306C
0x180012f15  movzx   eax, ax
0x180012f18  or      eax, 80070000h
0x180012f1d  jmp     loc_18001306C
0x180012f22  neg     bpl
0x180012f25  sbb     r8d, r8d
0x180012f28  and     r8d, 11000000h
0x180012f2f  add     r8d, 2; flProtect
0x180012f33  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpName
0x180012f38  mov     [rsp+68h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x180012f3d  xor     r9d, r9d; dwMaximumSizeHigh
0x180012f40  xor     edx, edx; lpFileMappingAttributes
0x180012f42  mov     rcx, [rdi]; hFile
0x180012f45  call    cs:__imp_CreateFileMappingW
0x180012f4b  mov     [rdi+8], rax
0x180012f4f  test    rax, rax
0x180012f52  jnz     short loc_180012FC0
0x180012f54  test    rsi, rsi
0x180012f57  jz      short loc_180012F7B
0x180012f59  mov     rax, [rsi]
0x180012f5c  mov     rbx, [rax+8]
0x180012f60  call    cs:__imp_GetLastError
0x180012f66  lea     rdx, aCreatefilemapp; "CreateFileMapping failed: %d"
0x180012f6d  mov     r8d, eax
0x180012f70  mov     rcx, rsi
0x180012f73  mov     rax, rbx
0x180012f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7b  mov     rcx, [rdi+10h]; lpBaseAddress
0x180012f7f  test    rcx, rcx
0x180012f82  jz      short loc_180012F8E
0x180012f84  call    cs:__imp_UnmapViewOfFile
0x180012f8a  mov     [rdi+10h], r14
0x180012f8e  mov     rcx, [rdi+8]; hObject
0x180012f92  test    rcx, rcx
0x180012f95  jz      short loc_180012FA1
0x180012f97  call    cs:__imp_CloseHandle
0x180012f9d  mov     [rdi+8], r14
0x180012fa1  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180012fa5  jz      loc_180012F07
0x180012fab  mov     rcx, [rdi]; hObject
0x180012fae  call    cs:__imp_CloseHandle
0x180012fb4  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180012fbb  jmp     loc_180012F07
0x180012fc0  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; lpBaseAddress
0x180012fc5  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x180012fca  xor     r9d, r9d; dwFileOffsetLow
0x180012fcd  xor     r8d, r8d; dwFileOffsetHigh
0x180012fd0  lea     edx, [r9+4]; dwDesiredAccess
0x180012fd4  mov     rcx, rax; hFileMappingObject
0x180012fd7  call    cs:__imp_MapViewOfFileEx
0x180012fdd  mov     rcx, rax
0x180012fe0  mov     [rdi+10h], rax
0x180012fe4  test    rax, rax
0x180012fe7  jnz     short loc_180013007
0x180012fe9  test    rsi, rsi
0x180012fec  jz      short loc_180012F7B
0x180012fee  mov     rax, [rsi]
0x180012ff1  mov     rbx, [rax+8]
0x180012ff5  call    cs:__imp_GetLastError
0x180012ffb  lea     rdx, aMapviewoffilee; "MapViewOfFileEx failed: %d"
0x180013002  jmp     loc_180012F6D
0x180013007  mov     eax, 5A4Dh
0x18001300c  cmp     [rcx], ax
0x18001300f  jnz     short loc_180013059
0x180013011  mov     eax, [rcx+3Ch]
0x180013014  test    al, 3
0x180013016  jnz     short loc_180013059
0x180013018  cmp     eax, 0FFFFFFFFh
0x18001301b  jnb     short loc_180013059
0x18001301d  mov     edx, eax
0x18001301f  not     edx
0x180013021  cmp     edx, 1Bh
0x180013024  jb      short loc_180013059
0x180013026  add     rcx, rax
0x180013029  cmp     dword ptr [rcx], 4550h
0x18001302f  jnz     short loc_180013059
0x180013031  mov     eax, 10Bh
0x180013036  cmp     [rcx+18h], ax
0x18001303a  jz      short loc_180013051
0x18001303c  mov     eax, 20Bh
0x180013041  cmp     [rcx+18h], ax
0x180013045  jnz     short loc_180013059
0x180013047  cmp     edx, 108h
0x18001304d  jbe     short loc_180013059
0x18001304f  jmp     short loc_18001305C
0x180013051  cmp     edx, 0F8h
0x180013057  ja      short loc_18001305C
0x180013059  mov     rcx, r14
0x18001305c  mov     eax, [rcx+50h]
0x18001305f  mov     [rdi+18h], rax
0x180013063  xor     eax, eax
0x180013065  jmp     short loc_18001306C
0x180013067  mov     eax, 8000000Eh
0x18001306c  lea     r11, [rsp+68h+var_18]
0x180013071  mov     rbx, [r11+28h]
0x180013075  mov     rbp, [r11+30h]
0x180013079  mov     rsp, r11
0x18001307c  pop     r14
0x18001307e  pop     rdi
0x18001307f  pop     rsi
0x180013080  retn
```
