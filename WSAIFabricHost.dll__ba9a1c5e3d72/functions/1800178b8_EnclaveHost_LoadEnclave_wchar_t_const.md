# EnclaveHost::LoadEnclave(wchar_t const *)

- ea: `0x1800178b8`
- end: `0x180017a38`
- name: `?LoadEnclave@EnclaveHost@@QEAAXPEB_W@Z`
- size: `384`
- prototype: `void __fastcall(EnclaveHost *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800153b0`

## callees

- `0x180004ca0`
- `0x1800178b8`
- `0x18001899c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800179a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800179a0`
- `api-ms-win-core-enclave-l1-1-1!LoadEnclaveImageW` at `0x18001797c`
- `api-ms-win-core-enclave-l1-1-1!LoadEnclaveImageW` at `0x18001797c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18001795c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180017993`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18001795c`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180017993`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18001794c`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x18001794c`
- `api-ms-win-core-enclave-l1-1-0!CreateEnclave` at `0x180017932`
- `api-ms-win-core-enclave-l1-1-0!CreateEnclave` at `0x180017932`
- `api-ms-win-core-enclave-l1-1-0!InitializeEnclave` at `0x1800179b9`
- `api-ms-win-core-enclave-l1-1-0!InitializeEnclave` at `0x1800179b9`

## string_xrefs

- `0x18001796e`: `SFSEnclave.dll`

## pseudocode

```c
void __fastcall EnclaveHost::LoadEnclave(EnclaveHost *this, const wchar_t *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  const char *v4; // r9
  void *v5; // rbx
  HANDLE v6; // rax
  const char *v7; // r9
  DWORD dwNewMode; // [rsp+40h] [rbp+7h] BYREF
  DWORD v9[2]; // [rsp+48h] [rbp+Fh] BYREF
  DWORD *p_dwNewMode; // [rsp+50h] [rbp+17h]
  char v11; // [rsp+58h] [rbp+1Fh]
  _QWORD EnclaveInformation[4]; // [rsp+60h] [rbp+27h] BYREF
  int v13; // [rsp+80h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  memset(EnclaveInformation, 0, sizeof(EnclaveInformation));
  v13 = 0;
  v9[0] = 8;
  v9[1] = 1;
  CurrentProcess = GetCurrentProcess();
  g_enclaveHost = CreateEnclave(CurrentProcess, 0, 0x1000000u, 0, 0x10u, EnclaveInformation, 0x24u, 0);
  if ( !g_enclaveHost )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\SFSEnclave\\include\\enclaveinterface.h",
      v3);
  dwNewMode = GetThreadErrorMode();
  SetThreadErrorMode(dwNewMode | 1, 0);
  p_dwNewMode = &dwNewMode;
  v11 = 1;
  if ( !LoadEnclaveImageW(g_enclaveHost, L"SFSEnclave.dll") )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\SFSEnclave\\include\\enclaveinterface.h",
      v4);
  SetThreadErrorMode(dwNewMode, 0);
  v5 = (void *)g_enclaveHost;
  v6 = GetCurrentProcess();
  if ( !InitializeEnclave(v6, v5, v9, v9[0], 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\SFSEnclave\\include\\enclaveinterface.h",
      v7);
  (*(void (__fastcall **)(__int64 *, _QWORD))(*off_1800AE2F0 + 24))(off_1800AE2F0, g_enclaveHost);
}

```

## disassembly

```asm
0x1800178b8  mov     [rsp-8+arg_0], rbx
0x1800178bd  mov     [rsp-8+arg_8], rdi
0x1800178c2  push    rbp
0x1800178c3  lea     rbp, [rsp-57h]
0x1800178c8  sub     rsp, 90h
0x1800178cf  mov     rax, cs:__security_cookie
0x1800178d6  xor     rax, rsp
0x1800178d9  mov     [rbp+57h+var_8], rax
0x1800178dd  xor     edi, edi
0x1800178df  mov     [rbp+57h+EnclaveInformation], rdi
0x1800178e3  mov     [rbp+57h+var_28], rdi
0x1800178e7  mov     [rbp+57h+var_20], rdi
0x1800178eb  mov     [rbp+57h+var_18], rdi
0x1800178ef  mov     [rbp+57h+var_10], edi
0x1800178f2  mov     [rbp+57h+var_48], 8
0x1800178f9  mov     [rbp+57h+var_44], 1
0x180017900  call    cs:__imp_GetCurrentProcess
0x180017906  mov     rcx, rax; hProcess
0x180017909  mov     [rsp+90h+lpEnclaveError], rdi; lpEnclaveError
0x18001790e  mov     [rsp+90h+dwInfoLength], 24h ; '$'; dwInfoLength
0x180017916  lea     rax, [rbp+57h+EnclaveInformation]
0x18001791a  mov     [rsp+90h+lpEnclaveInformation], rax; lpEnclaveInformation
0x18001791f  mov     [rsp+90h+flEnclaveType], 10h; flEnclaveType
0x180017927  xor     r9d, r9d; dwInitialCommitment
0x18001792a  xor     edx, edx; lpAddress
0x18001792c  mov     r8d, 1000000h; dwSize
0x180017932  call    cs:__imp_CreateEnclave
0x180017938  mov     cs:?g_enclaveHost@@3UEnclaveHost@@A, rax; EnclaveHost g_enclaveHost
0x18001793f  mov     rcx, [rbp+5Fh]; this
0x180017943  test    rax, rax
0x180017946  jz      loc_180017A14
0x18001794c  call    cs:__imp_GetThreadErrorMode
0x180017952  mov     [rbp+57h+dwNewMode], eax
0x180017955  or      eax, 1
0x180017958  xor     edx, edx; lpOldMode
0x18001795a  mov     ecx, eax; dwNewMode
0x18001795c  call    cs:__imp_SetThreadErrorMode
0x180017962  lea     rax, [rbp+57h+dwNewMode]
0x180017966  mov     [rbp+57h+var_40], rax
0x18001796a  mov     [rbp+57h+var_38], 1
0x18001796e  lea     rdx, aSfsenclaveDll; "SFSEnclave.dll"
0x180017975  mov     rcx, cs:?g_enclaveHost@@3UEnclaveHost@@A; lpEnclaveAddress
0x18001797c  call    cs:__imp_LoadEnclaveImageW
0x180017982  mov     rcx, [rbp+5Fh]; this
0x180017986  test    eax, eax
0x180017988  jz      loc_180017A26
0x18001798e  xor     edx, edx; lpOldMode
0x180017990  mov     ecx, [rbp+57h+dwNewMode]; dwNewMode
0x180017993  call    cs:__imp_SetThreadErrorMode
0x180017999  mov     rbx, cs:?g_enclaveHost@@3UEnclaveHost@@A; EnclaveHost g_enclaveHost
0x1800179a0  call    cs:__imp_GetCurrentProcess
0x1800179a6  mov     qword ptr [rsp+90h+flEnclaveType], rdi; lpEnclaveError
0x1800179ab  mov     r9d, [rbp+57h+var_48]; dwInfoLength
0x1800179af  lea     r8, [rbp+57h+var_48]; lpEnclaveInformation
0x1800179b3  mov     rdx, rbx; lpAddress
0x1800179b6  mov     rcx, rax; hProcess
0x1800179b9  call    cs:__imp_InitializeEnclave
0x1800179bf  test    eax, eax
0x1800179c1  jz      short loc_1800179FE
0x1800179c3  mov     rcx, cs:off_1800AE2F0
0x1800179ca  mov     rax, [rcx]
0x1800179cd  mov     rdx, cs:?g_enclaveHost@@3UEnclaveHost@@A; EnclaveHost g_enclaveHost
0x1800179d4  mov     rax, [rax+18h]
0x1800179d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179dd  mov     rcx, [rbp+57h+var_8]
0x1800179e1  xor     rcx, rsp; StackCookie
0x1800179e4  call    __security_check_cookie
0x1800179e9  lea     r11, [rsp+90h+var_s0]
0x1800179f1  mov     rbx, [r11+10h]
0x1800179f5  mov     rdi, [r11+18h]
0x1800179f9  mov     rsp, r11
0x1800179fc  pop     rbp
0x1800179fd  retn
0x1800179fe  mov     rcx, [rbp+5Fh]; this
0x180017a02  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\SFS"...
0x180017a09  mov     edx, 90h; void *
0x180017a0e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017a14  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\SFS"...
0x180017a1b  mov     edx, 84h; void *
0x180017a20  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017a26  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\SFS"...
0x180017a2d  mov     edx, 8Ch; void *
0x180017a32  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
