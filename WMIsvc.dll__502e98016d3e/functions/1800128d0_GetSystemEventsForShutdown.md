# GetSystemEventsForShutdown

- ea: `0x1800128d0`
- end: `0x180012c2b`
- name: `GetSystemEventsForShutdown`
- size: `859`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180006420`
- `0x18000c910`
- `0x18000c9bc`
- `0x1800128d0`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001290f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001290f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012956`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001297c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001298f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012956`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001297c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001298f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001293b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001291d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001291d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012b47`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012b78`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012b47`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012b78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800129dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800129dd`

## string_xrefs

- `0x180012908`: `Wevtapi.dll`
- `0x180012a25`: `<QueryList> <Query Id="0" Path="System"> <Select Path="System">*[System[Provider[@Name='eventlog'] and (EventID=6005 or EventID=6006)]]</Select> </Query></QueryList>`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall GetSystemEventsForShutdown(LPCWSTR lpFileName)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  signed int result; // eax
  FARPROC ProcAddress; // r12
  FARPROC v6; // r15
  FARPROC v7; // r14
  FARPROC v8; // rbx
  HANDLE FileW; // rax
  void *v10; // rsi
  signed int LastError; // eax
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rdi
  signed int v15; // eax
  size_t v16; // rbx
  signed int v17; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  size_t pcchLength; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t psz[1024]; // [rsp+D0h] [rbp-30h] BYREF

  Library = LoadLibraryExW(L"Wevtapi.dll", 0, 0);
  v3 = Library;
  if ( !Library )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  MakeGuard<int (*)(void *),void *>(v27, FreeLibrary, Library);
  ProcAddress = GetProcAddress(v3, "EvtRender");
  v6 = GetProcAddress(v3, "EvtNext");
  v7 = GetProcAddress(v3, "EvtClose");
  v8 = GetProcAddress(v3, "EvtQuery");
  if ( !v8 || !v7 || !v6 || !ProcAddress )
  {
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v27);
    return -2147217407;
  }
  FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0, 0);
  v10 = FileW;
  if ( lpFileName == (LPCWSTR)-1LL )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v27);
    return v12;
  }
  MakeGuard<int (*)(void *),void *>(v24, CloseHandle, FileW);
  v13 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, const wchar_t *, __int64))v8)(
          0,
          L"System",
          L"<QueryList> <Query Id=\"0\" Path=\"System\"> <Select Path=\"System\">*[System[Provider[@Name='eventlog'] and ("
           "EventID=6005 or EventID=6006)]]</Select> </Query></QueryList>",
          1);
  v14 = v13;
  if ( !v13 )
  {
    v15 = GetLastError();
    v12 = v15;
    if ( v15 > 0 )
      v12 = (unsigned __int16)v15 | 0x80070000;
LABEL_26:
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v24);
    goto LABEL_27;
  }
  MakeGuard<int (*)(void *),void *>(v26, v7, v13);
  v22 = 0;
  v19 = 0;
  NumberOfBytesWritten = 0;
  while ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _DWORD, int *))v6)(
            v14,
            1,
            &v22,
            5000,
            0,
            &v19) )
  {
    MakeGuard<int (*)(void *),void *>(v25, v7, v22);
    v21 = 0;
    v20 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64, wchar_t *, int *, int *))ProcAddress)(
            0,
            v22,
            1,
            2048,
            psz,
            &v21,
            &v20) )
      goto LABEL_23;
    pcchLength = 0;
    v12 = StringLengthWorkerW(psz, 0x400u, &pcchLength);
    if ( v12 < 0 )
      goto LABEL_25;
    v16 = pcchLength;
    if ( !WriteFile(v10, psz, 2 * pcchLength, &NumberOfBytesWritten, 0)
      || NumberOfBytesWritten != 2 * v16
      || !WriteFile(v10, L"\r\n\r\n", 8u, &NumberOfBytesWritten, 0)
      || NumberOfBytesWritten != 8 )
    {
LABEL_23:
      v17 = GetLastError();
      v12 = v17;
      if ( v17 > 0 )
        v12 = (unsigned __int16)v17 | 0x80070000;
LABEL_25:
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v25);
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v26);
      goto LABEL_26;
    }
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v25);
  }
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v26);
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v24);
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v27);
  return 0;
}

```

## disassembly

```asm
0x1800128d0  push    rbp
0x1800128d2  push    rbx
0x1800128d3  push    rsi
0x1800128d4  push    rdi
0x1800128d5  push    r12
0x1800128d7  push    r13
0x1800128d9  push    r14
0x1800128db  push    r15
0x1800128dd  lea     rbp, [rsp-7E8h]
0x1800128e5  sub     rsp, 8E8h
0x1800128ec  mov     rax, cs:__security_cookie
0x1800128f3  xor     rax, rsp
0x1800128f6  mov     [rbp+820h+var_50], rax
0x1800128fd  mov     rdi, rcx
0x180012900  xor     r13d, r13d
0x180012903  xor     r8d, r8d; dwFlags
0x180012906  xor     edx, edx; hFile
0x180012908  lea     rcx, LibFileName; "Wevtapi.dll"
0x18001290f  call    cs:__imp_LoadLibraryExW
0x180012915  mov     rbx, rax
0x180012918  test    rax, rax
0x18001291b  jnz     short loc_180012938
0x18001291d  call    cs:__imp_GetLastError
0x180012923  test    eax, eax
0x180012925  jle     loc_180012C08
0x18001292b  movzx   eax, ax
0x18001292e  or      eax, 80070000h
0x180012933  jmp     loc_180012C08
0x180012938  mov     r8, rbx
0x18001293b  mov     rdx, cs:__imp_FreeLibrary
0x180012942  lea     rcx, [rbp+820h+var_870]
0x180012946  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x18001294b  nop
0x18001294c  lea     rdx, aEvtrender; "EvtRender"
0x180012953  mov     rcx, rbx; hModule
0x180012956  call    cs:__imp_GetProcAddress
0x18001295c  mov     r12, rax
0x18001295f  lea     rdx, aEvtnext; "EvtNext"
0x180012966  mov     rcx, rbx; hModule
0x180012969  call    cs:__imp_GetProcAddress
0x18001296f  mov     r15, rax
0x180012972  lea     rdx, aEvtclose; "EvtClose"
0x180012979  mov     rcx, rbx; hModule
0x18001297c  call    cs:__imp_GetProcAddress
0x180012982  mov     r14, rax
0x180012985  lea     rdx, aEvtquery; "EvtQuery"
0x18001298c  mov     rcx, rbx; hModule
0x18001298f  call    cs:__imp_GetProcAddress
0x180012995  mov     rbx, rax
0x180012998  test    rax, rax
0x18001299b  jz      loc_180012BFA
0x1800129a1  test    r14, r14
0x1800129a4  jz      loc_180012BFA
0x1800129aa  test    r15, r15
0x1800129ad  jz      loc_180012BFA
0x1800129b3  test    r12, r12
0x1800129b6  jz      loc_180012BFA
0x1800129bc  mov     [rsp+920h+hTemplateFile], r13; hTemplateFile
0x1800129c1  mov     [rsp+920h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800129c6  mov     [rsp+920h+dwCreationDisposition], 2; dwCreationDisposition
0x1800129ce  xor     r9d, r9d; lpSecurityAttributes
0x1800129d1  mov     edx, 40000000h; dwDesiredAccess
0x1800129d6  lea     r8d, [r9+1]; dwShareMode
0x1800129da  mov     rcx, rdi; lpFileName
0x1800129dd  call    cs:__imp_CreateFileW
0x1800129e3  mov     rsi, rax
0x1800129e6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800129ea  jnz     short loc_180012A0A
0x1800129ec  call    cs:__imp_GetLastError
0x1800129f2  mov     ebx, eax
0x1800129f4  test    eax, eax
0x1800129f6  jle     loc_180012BCB
0x1800129fc  movzx   ebx, ax
0x1800129ff  or      ebx, 80070000h
0x180012a05  jmp     loc_180012BCB
0x180012a0a  mov     r8, rsi
0x180012a0d  mov     rdx, cs:__imp_CloseHandle
0x180012a14  lea     rcx, [rsp+920h+var_8C0]
0x180012a19  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x180012a1e  nop
0x180012a1f  mov     r9d, 1
0x180012a25  lea     r8, aQuerylistQuery_0; "<QueryList> <Query Id=\"0\" Path=\"Syst"...
0x180012a2c  lea     rdx, aSystem; "System"
0x180012a33  xor     ecx, ecx
0x180012a35  mov     rax, rbx
0x180012a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a3d  mov     rdi, rax
0x180012a40  test    rax, rax
0x180012a43  jnz     short loc_180012A63
0x180012a45  call    cs:__imp_GetLastError
0x180012a4b  mov     ebx, eax
0x180012a4d  test    eax, eax
0x180012a4f  jle     loc_180012BC0
0x180012a55  movzx   ebx, ax
0x180012a58  or      ebx, 80070000h
0x180012a5e  jmp     loc_180012BC0
0x180012a63  mov     r8, rdi
0x180012a66  mov     rdx, r14
0x180012a69  lea     rcx, [rbp+820h+var_888]
0x180012a6d  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x180012a72  nop
0x180012a73  mov     [rsp+920h+var_8D0], r13
0x180012a78  mov     [rsp+920h+var_8DC], r13d
0x180012a7d  mov     [rsp+920h+NumberOfBytesWritten], r13d
0x180012a82  lea     rax, [rsp+920h+var_8DC]
0x180012a87  mov     qword ptr [rsp+920h+dwFlagsAndAttributes], rax
0x180012a8c  mov     [rsp+920h+dwCreationDisposition], r13d
0x180012a91  mov     r9d, 1388h
0x180012a97  lea     r8, [rsp+920h+var_8D0]
0x180012a9c  mov     ebx, 1
0x180012aa1  mov     edx, ebx
0x180012aa3  mov     rcx, rdi
0x180012aa6  mov     rax, r15
0x180012aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aae  test    eax, eax
0x180012ab0  jz      loc_180012BD8
0x180012ab6  mov     r8, [rsp+920h+var_8D0]
0x180012abb  mov     rdx, r14
0x180012abe  lea     rcx, [rbp+820h+var_8A0]
0x180012ac2  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x180012ac7  nop
0x180012ac8  mov     [rsp+920h+var_8D4], r13d
0x180012acd  mov     [rsp+920h+var_8D8], r13d
0x180012ad2  lea     rax, [rsp+920h+var_8D8]
0x180012ad7  mov     [rsp+920h+hTemplateFile], rax
0x180012adc  lea     rax, [rsp+920h+var_8D4]
0x180012ae1  mov     qword ptr [rsp+920h+dwFlagsAndAttributes], rax
0x180012ae6  lea     rax, [rbp+820h+psz]
0x180012aea  mov     qword ptr [rsp+920h+dwCreationDisposition], rax
0x180012aef  mov     r9d, 800h
0x180012af5  mov     r8d, ebx
0x180012af8  mov     rdx, [rsp+920h+var_8D0]
0x180012afd  xor     ecx, ecx
0x180012aff  mov     rax, r12
0x180012b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b07  test    eax, eax
0x180012b09  jz      loc_180012B97
0x180012b0f  mov     [rsp+920h+pcchLength], r13
0x180012b14  lea     r8, [rsp+920h+pcchLength]; pcchLength
0x180012b19  mov     edx, 400h; cchMax
0x180012b1e  lea     rcx, [rbp+820h+psz]; psz
0x180012b22  call    StringLengthWorkerW
0x180012b27  mov     ebx, eax
0x180012b29  test    eax, eax
0x180012b2b  js      short loc_180012BAC
0x180012b2d  mov     rbx, [rsp+920h+pcchLength]
0x180012b32  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180012b36  mov     qword ptr [rsp+920h+dwCreationDisposition], r13; lpOverlapped
0x180012b3b  lea     r9, [rsp+920h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180012b40  lea     rdx, [rbp+820h+psz]; lpBuffer
0x180012b44  mov     rcx, rsi; hFile
0x180012b47  call    cs:__imp_WriteFile
0x180012b4d  test    eax, eax
0x180012b4f  jz      short loc_180012B97
0x180012b51  lea     rcx, [rbx+rbx]
0x180012b55  mov     eax, [rsp+920h+NumberOfBytesWritten]
0x180012b59  cmp     rax, rcx
0x180012b5c  jnz     short loc_180012B97
0x180012b5e  mov     qword ptr [rsp+920h+dwCreationDisposition], r13; lpOverlapped
0x180012b63  lea     r9, [rsp+920h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180012b68  mov     r8d, 8; nNumberOfBytesToWrite
0x180012b6e  lea     rdx, asc_180024C20; "\r\n\r\n"
0x180012b75  mov     rcx, rsi; hFile
0x180012b78  call    cs:__imp_WriteFile
0x180012b7e  test    eax, eax
0x180012b80  jz      short loc_180012B97
0x180012b82  cmp     [rsp+920h+NumberOfBytesWritten], 8
0x180012b87  jnz     short loc_180012B97
0x180012b89  lea     rcx, [rbp+820h+var_8A0]
0x180012b8d  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012b92  jmp     loc_180012A82
0x180012b97  call    cs:__imp_GetLastError
0x180012b9d  mov     ebx, eax
0x180012b9f  test    eax, eax
0x180012ba1  jle     short loc_180012BAC
0x180012ba3  movzx   ebx, ax
0x180012ba6  or      ebx, 80070000h
0x180012bac  lea     rcx, [rbp+820h+var_8A0]
0x180012bb0  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bb5  nop
0x180012bb6  lea     rcx, [rbp+820h+var_888]
0x180012bba  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bbf  nop
0x180012bc0  lea     rcx, [rsp+920h+var_8C0]
0x180012bc5  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bca  nop
0x180012bcb  lea     rcx, [rbp+820h+var_870]
0x180012bcf  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bd4  mov     eax, ebx
0x180012bd6  jmp     short loc_180012C08
0x180012bd8  lea     rcx, [rbp+820h+var_888]
0x180012bdc  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012be1  nop
0x180012be2  lea     rcx, [rsp+920h+var_8C0]
0x180012be7  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bec  nop
0x180012bed  lea     rcx, [rbp+820h+var_870]
0x180012bf1  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012bf6  xor     eax, eax
0x180012bf8  jmp     short loc_180012C08
0x180012bfa  lea     rcx, [rbp+820h+var_870]
0x180012bfe  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180012c03  mov     eax, 80041001h
0x180012c08  mov     rcx, [rbp+820h+var_50]
0x180012c0f  xor     rcx, rsp; StackCookie
0x180012c12  call    __security_check_cookie
0x180012c17  add     rsp, 8E8h
0x180012c1e  pop     r15
0x180012c20  pop     r14
0x180012c22  pop     r13
0x180012c24  pop     r12
0x180012c26  pop     rdi
0x180012c27  pop     rsi
0x180012c28  pop     rbx
0x180012c29  pop     rbp
0x180012c2a  retn
```
