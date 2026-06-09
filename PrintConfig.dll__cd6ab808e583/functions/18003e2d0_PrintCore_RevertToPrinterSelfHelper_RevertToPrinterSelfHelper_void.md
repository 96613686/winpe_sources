# PrintCore::RevertToPrinterSelfHelper::RevertToPrinterSelfHelper(void)

- ea: `0x18003e2d0`
- end: `0x18003e452`
- name: `??0RevertToPrinterSelfHelper@PrintCore@@QEAA@XZ`
- size: `386`
- prototype: `PrintCore::RevertToPrinterSelfHelper *__fastcall(PrintCore::RevertToPrinterSelfHelper *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180049f58`
- `0x18004a2a4`

## callees

- `0x180039880`
- `0x18003e2d0`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003e36c`
- `KERNEL32!GetProcAddress` at `0x18003e3ad`
- `KERNEL32!GetProcAddress` at `0x18003e36c`
- `KERNEL32!GetProcAddress` at `0x18003e3ad`
- `KERNEL32!FreeLibrary` at `0x18003e322`
- `KERNEL32!FreeLibrary` at `0x18003e322`
- `KERNEL32!CloseHandle` at `0x18003e407`
- `KERNEL32!CloseHandle` at `0x18003e407`
- `KERNEL32!SetLastError` at `0x18003e32a`
- `KERNEL32!SetLastError` at `0x18003e40f`
- `KERNEL32!SetLastError` at `0x18003e32a`
- `KERNEL32!SetLastError` at `0x18003e40f`
- `KERNEL32!GetLastError` at `0x18003e317`
- `KERNEL32!GetLastError` at `0x18003e3fc`
- `KERNEL32!GetLastError` at `0x18003e317`
- `KERNEL32!GetLastError` at `0x18003e3fc`
- `KERNEL32!LoadLibraryExW` at `0x18003e305`
- `KERNEL32!LoadLibraryExW` at `0x18003e305`

## string_xrefs

- `0x18003e2fe`: `spoolss.dll`
- `0x18003e3a2`: `ImpersonatePrinterClient`
- `0x18003e3bc`: `Failed to GetProcAddress of ImpersonatePrinterClient`
- `0x18003e339`: `Failed to load library spoolss.dll`
- `0x18003e41d`: `Failed to get impersonation token`

## pseudocode

```c
PrintCore::RevertToPrinterSelfHelper *__fastcall PrintCore::RevertToPrinterSelfHelper::RevertToPrinterSelfHelper(
        PrintCore::RevertToPrinterSelfHelper *this)
{
  HMODULE Library; // rbp
  HMODULE v3; // rsi
  DWORD LastError; // ebx
  __int64 (*ProcAddress)(void); // rbx
  FARPROC v6; // rax
  __int64 v7; // rsi
  void *v8; // rbp
  DWORD v9; // ebx
  void *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  Library = LoadLibraryExW(L"spoolss.dll", 0, 0x800u);
  v3 = (HMODULE)*((_QWORD *)this + 1);
  if ( v3 )
  {
    LastError = GetLastError();
    FreeLibrary(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = Library;
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    15,
    "OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    2147943557LL,
    Library,
    "Failed to load library spoolss.dll");
  ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "RevertToPrinterSelf");
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    17,
    "OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    2147549183LL,
    ProcAddress,
    "Failed to GetProcAddress RevertToPrinterSelf");
  v6 = GetProcAddress(*((HMODULE *)this + 1), "ImpersonatePrinterClient");
  *((_QWORD *)this + 2) = v6;
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    19,
    "OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    2147549183LL,
    v6,
    "Failed to GetProcAddress of ImpersonatePrinterClient");
  v7 = ProcAddress();
  v8 = *(void **)this;
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = GetLastError();
    CloseHandle(v8);
    SetLastError(v9);
  }
  *(_QWORD *)this = v7;
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    23,
    "OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    2147549183LL,
    v7,
    "Failed to get impersonation token");
  return this;
}

```

## disassembly

```asm
0x18003e2d0  mov     [rsp+arg_0], rcx
0x18003e2d5  push    rbx
0x18003e2d6  push    rbp
0x18003e2d7  push    rsi
0x18003e2d8  push    rdi
0x18003e2d9  sub     rsp, 48h
0x18003e2dd  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18003e2e6  mov     rdi, rcx
0x18003e2e9  xor     ebx, ebx
0x18003e2eb  mov     [rcx], rbx
0x18003e2ee  mov     [rcx+8], rbx
0x18003e2f2  mov     [rcx+10h], rbx
0x18003e2f6  xor     edx, edx; hFile
0x18003e2f8  mov     r8d, 800h; dwFlags
0x18003e2fe  lea     rcx, aSpoolssDll; "spoolss.dll"
0x18003e305  call    cs:__imp_LoadLibraryExW
0x18003e30b  mov     rbp, rax
0x18003e30e  mov     rsi, [rdi+8]
0x18003e312  test    rsi, rsi
0x18003e315  jz      short loc_18003E330
0x18003e317  call    cs:__imp_GetLastError
0x18003e31d  mov     ebx, eax
0x18003e31f  mov     rcx, rsi; hLibModule
0x18003e322  call    cs:__imp_FreeLibrary
0x18003e328  mov     ecx, ebx; dwErrCode
0x18003e32a  call    cs:__imp_SetLastError
0x18003e330  mov     [rdi+8], rbp
0x18003e334  mov     rcx, [rsp+68h]
0x18003e339  lea     rax, aFailedToLoadLi; "Failed to load library spoolss.dll"
0x18003e340  mov     [rsp+68h+var_40], rax
0x18003e345  mov     [rsp+68h+var_48], rbp
0x18003e34a  mov     r9d, 80070485h
0x18003e350  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003e357  mov     edx, 0Fh
0x18003e35c  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e361  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x18003e368  mov     rcx, [rdi+8]; hModule
0x18003e36c  call    cs:__imp_GetProcAddress
0x18003e372  mov     rbx, rax
0x18003e375  mov     rcx, [rsp+68h]
0x18003e37a  lea     rax, aFailedToGetpro; "Failed to GetProcAddress RevertToPrinte"...
0x18003e381  mov     [rsp+68h+var_40], rax
0x18003e386  mov     [rsp+68h+var_48], rbx
0x18003e38b  mov     r9d, 8000FFFFh
0x18003e391  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003e398  mov     edx, 11h
0x18003e39d  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e3a2  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x18003e3a9  mov     rcx, [rdi+8]; hModule
0x18003e3ad  call    cs:__imp_GetProcAddress
0x18003e3b3  mov     [rdi+10h], rax
0x18003e3b7  mov     rcx, [rsp+68h]
0x18003e3bc  lea     rdx, aFailedToGetpro_0; "Failed to GetProcAddress of Impersonate"...
0x18003e3c3  mov     [rsp+68h+var_40], rdx
0x18003e3c8  mov     [rsp+68h+var_48], rax
0x18003e3cd  mov     r9d, 8000FFFFh
0x18003e3d3  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003e3da  mov     edx, 13h
0x18003e3df  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e3e4  mov     rax, rbx
0x18003e3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3ec  mov     rsi, rax
0x18003e3ef  mov     rbp, [rdi]
0x18003e3f2  lea     rdx, [rbp-1]
0x18003e3f6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003e3fa  ja      short loc_18003E415
0x18003e3fc  call    cs:__imp_GetLastError
0x18003e402  mov     ebx, eax
0x18003e404  mov     rcx, rbp; hObject
0x18003e407  call    cs:__imp_CloseHandle
0x18003e40d  mov     ecx, ebx; dwErrCode
0x18003e40f  call    cs:__imp_SetLastError
0x18003e415  mov     [rdi], rsi
0x18003e418  mov     rcx, [rsp+68h]
0x18003e41d  lea     rax, aFailedToGetImp; "Failed to get impersonation token"
0x18003e424  mov     [rsp+68h+var_40], rax
0x18003e429  mov     [rsp+68h+var_48], rsi
0x18003e42e  mov     r9d, 8000FFFFh
0x18003e434  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003e43b  mov     edx, 17h
0x18003e440  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e445  nop
0x18003e446  mov     rax, rdi
0x18003e449  add     rsp, 48h
0x18003e44d  pop     rdi
0x18003e44e  pop     rsi
0x18003e44f  pop     rbp
0x18003e450  pop     rbx
0x18003e451  retn
```
