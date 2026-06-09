# PrintCore::RevertToPrinterSelfHelper::RevertToPrinterSelfHelper(void)

- ea: `0x18003f92c`
- end: `0x18003fae5`
- name: `??0RevertToPrinterSelfHelper@PrintCore@@QEAA@XZ`
- size: `441`
- prototype: `PrintCore::RevertToPrinterSelfHelper *__fastcall(PrintCore::RevertToPrinterSelfHelper *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004be38`
- `0x18004c18c`

## callees

- `0x18003ae44`
- `0x18003f92c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003f9e0`
- `KERNEL32!GetProcAddress` at `0x18003fa27`
- `KERNEL32!GetProcAddress` at `0x18003f9e0`
- `KERNEL32!GetProcAddress` at `0x18003fa27`
- `KERNEL32!FreeLibrary` at `0x18003f98a`
- `KERNEL32!FreeLibrary` at `0x18003f98a`
- `KERNEL32!CloseHandle` at `0x18003fa8d`
- `KERNEL32!CloseHandle` at `0x18003fa8d`
- `KERNEL32!SetLastError` at `0x18003f998`
- `KERNEL32!SetLastError` at `0x18003fa9b`
- `KERNEL32!SetLastError` at `0x18003f998`
- `KERNEL32!SetLastError` at `0x18003fa9b`
- `KERNEL32!GetLastError` at `0x18003f979`
- `KERNEL32!GetLastError` at `0x18003fa7c`
- `KERNEL32!GetLastError` at `0x18003f979`
- `KERNEL32!GetLastError` at `0x18003fa7c`
- `KERNEL32!LoadLibraryExW` at `0x18003f961`
- `KERNEL32!LoadLibraryExW` at `0x18003f961`

## string_xrefs

- `0x18003f95a`: `spoolss.dll`
- `0x18003fa1c`: `ImpersonatePrinterClient`
- `0x18003f9ad`: `Failed to load library spoolss.dll`
- `0x18003faaf`: `Failed to get impersonation token`
- `0x18003fa3c`: `Failed to GetProcAddress of ImpersonatePrinterClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

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
    (void *)0xF,
    (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    -2147023739,
    (__int64)Library,
    (int)"Failed to load library spoolss.dll",
    -2);
  ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "RevertToPrinterSelf");
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    (void *)0x11,
    (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    -2147418113,
    (__int64)ProcAddress,
    (int)"Failed to GetProcAddress RevertToPrinterSelf");
  v6 = GetProcAddress(*((HMODULE *)this + 1), "ImpersonatePrinterClient");
  *((_QWORD *)this + 2) = v6;
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    (void *)0x13,
    (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    -2147418113,
    (__int64)v6,
    (int)"Failed to GetProcAddress of ImpersonatePrinterClient");
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
    (void *)0x17,
    (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\SpoolerUtils.h",
    -2147418113,
    v7,
    (int)"Failed to get impersonation token");
  return this;
}

```

## disassembly

```asm
0x18003f92c  mov     [rsp+arg_0], rcx
0x18003f931  push    rbx
0x18003f932  push    rbp
0x18003f933  push    rsi
0x18003f934  push    rdi
0x18003f935  sub     rsp, 48h
0x18003f939  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18003f942  mov     rdi, rcx
0x18003f945  xor     ebx, ebx
0x18003f947  mov     [rcx], rbx
0x18003f94a  mov     [rcx+8], rbx
0x18003f94e  mov     [rcx+10h], rbx
0x18003f952  xor     edx, edx; hFile
0x18003f954  mov     r8d, 800h; dwFlags
0x18003f95a  lea     rcx, aSpoolssDll; "spoolss.dll"
0x18003f961  call    cs:__imp_LoadLibraryExW
0x18003f968  nop     dword ptr [rax+rax+00h]
0x18003f96d  mov     rbp, rax
0x18003f970  mov     rsi, [rdi+8]
0x18003f974  test    rsi, rsi
0x18003f977  jz      short loc_18003F9A4
0x18003f979  call    cs:__imp_GetLastError
0x18003f980  nop     dword ptr [rax+rax+00h]
0x18003f985  mov     ebx, eax
0x18003f987  mov     rcx, rsi; hLibModule
0x18003f98a  call    cs:__imp_FreeLibrary
0x18003f991  nop     dword ptr [rax+rax+00h]
0x18003f996  mov     ecx, ebx; dwErrCode
0x18003f998  call    cs:__imp_SetLastError
0x18003f99f  nop     dword ptr [rax+rax+00h]
0x18003f9a4  mov     [rdi+8], rbp
0x18003f9a8  mov     rcx, [rsp+68h]
0x18003f9ad  lea     rax, aFailedToLoadLi; "Failed to load library spoolss.dll"
0x18003f9b4  mov     [rsp+68h+var_40], rax
0x18003f9b9  mov     [rsp+68h+var_48], rbp
0x18003f9be  mov     r9d, 80070485h
0x18003f9c4  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003f9cb  mov     edx, 0Fh
0x18003f9d0  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003f9d5  lea     rdx, aReverttoprinte; "RevertToPrinterSelf"
0x18003f9dc  mov     rcx, [rdi+8]; hModule
0x18003f9e0  call    cs:__imp_GetProcAddress
0x18003f9e7  nop     dword ptr [rax+rax+00h]
0x18003f9ec  mov     rbx, rax
0x18003f9ef  mov     rcx, [rsp+68h]
0x18003f9f4  lea     rax, aFailedToGetpro; "Failed to GetProcAddress RevertToPrinte"...
0x18003f9fb  mov     [rsp+68h+var_40], rax
0x18003fa00  mov     [rsp+68h+var_48], rbx
0x18003fa05  mov     r9d, 8000FFFFh
0x18003fa0b  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003fa12  mov     edx, 11h
0x18003fa17  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003fa1c  lea     rdx, aImpersonatepri; "ImpersonatePrinterClient"
0x18003fa23  mov     rcx, [rdi+8]; hModule
0x18003fa27  call    cs:__imp_GetProcAddress
0x18003fa2e  nop     dword ptr [rax+rax+00h]
0x18003fa33  mov     [rdi+10h], rax
0x18003fa37  mov     rcx, [rsp+68h]
0x18003fa3c  lea     rdx, aFailedToGetpro_0; "Failed to GetProcAddress of Impersonate"...
0x18003fa43  mov     [rsp+68h+var_40], rdx
0x18003fa48  mov     [rsp+68h+var_48], rax
0x18003fa4d  mov     r9d, 8000FFFFh
0x18003fa53  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003fa5a  mov     edx, 13h
0x18003fa5f  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003fa64  mov     rax, rbx
0x18003fa67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa6c  mov     rsi, rax
0x18003fa6f  mov     rbp, [rdi]
0x18003fa72  lea     rdx, [rbp-1]
0x18003fa76  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003fa7a  ja      short loc_18003FAA7
0x18003fa7c  call    cs:__imp_GetLastError
0x18003fa83  nop     dword ptr [rax+rax+00h]
0x18003fa88  mov     ebx, eax
0x18003fa8a  mov     rcx, rbp; hObject
0x18003fa8d  call    cs:__imp_CloseHandle
0x18003fa94  nop     dword ptr [rax+rax+00h]
0x18003fa99  mov     ecx, ebx; dwErrCode
0x18003fa9b  call    cs:__imp_SetLastError
0x18003faa2  nop     dword ptr [rax+rax+00h]
0x18003faa7  mov     [rdi], rsi
0x18003faaa  mov     rcx, [rsp+68h]
0x18003faaf  lea     rax, aFailedToGetImp; "Failed to get impersonation token"
0x18003fab6  mov     [rsp+68h+var_40], rax
0x18003fabb  mov     [rsp+68h+var_48], rsi
0x18003fac0  mov     r9d, 8000FFFFh
0x18003fac6  lea     r8, aOnecoreuapInte_13; "OneCoreUap\\Internal\\PrintScan\\inc\\S"...
0x18003facd  mov     edx, 17h
0x18003fad2  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003fad7  nop
0x18003fad8  mov     rax, rdi
0x18003fadb  add     rsp, 48h
0x18003fadf  pop     rdi
0x18003fae0  pop     rsi
0x18003fae1  pop     rbp
0x18003fae2  pop     rbx
0x18003fae3  retn
```
