# CheckLicenseForActivation(ushort const *)

- ea: `0x18008f044`
- end: `0x18008f13d`
- name: `?CheckLicenseForActivation@@YAKPEBG@Z`
- size: `249`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008f1e4`

## callees

- `0x18000cbc0`
- `0x18000cbe4`
- `0x180027ce8`
- `0x18005b3c4`
- `0x18007638c`
- `0x18008f044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008f065`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f07b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008f07b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f0cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f0cf`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18008f0fd`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18008f0fd`

## string_xrefs

- `0x18008f085`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18008f0dd`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckLicenseForActivation(const unsigned __int16 *a1)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  const char *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rcx
  void *Block; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int TokenInformation; // [rsp+68h] [rbp+28h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
      v3);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, (__int64)TokenHandle);
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
      v4);
  v5 = EnsureStoreLicenseForPackageActivation(a1, TokenInformation, *(_QWORD *)Block, 0);
  v6 = v5;
  if ( v5 < 0 && (v5 & 0x20000000) != 0 )
    v6 = v5 & 0xDFFFFFFF;
  v7 = Block;
  Block = 0;
  if ( v7 )
    operator delete(v7);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18008f044  push    rbp
0x18008f046  push    rbx
0x18008f047  push    rdi
0x18008f048  mov     rbp, rsp
0x18008f04b  sub     rsp, 40h
0x18008f04f  mov     rdi, rcx
0x18008f052  mov     [rbp+TokenHandle], 0
0x18008f05a  xor     edx, edx
0x18008f05c  lea     rcx, [rbp+TokenHandle]
0x18008f060  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008f065  call    cs:__imp_GetCurrentProcess
0x18008f06b  mov     rbx, [rbp+18h]
0x18008f06f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18008f073  mov     edx, 20008h; DesiredAccess
0x18008f078  mov     rcx, rax; ProcessHandle
0x18008f07b  call    cs:__imp_OpenProcessToken
0x18008f081  test    eax, eax
0x18008f083  jnz     short loc_18008F098
0x18008f085  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008f08c  lea     edx, [rax+49h]; void *
0x18008f08f  mov     rcx, rbx; this
0x18008f092  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008f098  mov     rdx, [rbp+TokenHandle]
0x18008f09c  lea     rcx, [rbp+Block]
0x18008f0a0  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18008f0a5  nop
0x18008f0a6  mov     [rbp+TokenInformation], 0
0x18008f0ad  mov     [rbp+arg_10], 0
0x18008f0b4  lea     rax, [rbp+arg_10]
0x18008f0b8  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18008f0bd  mov     r9d, 4; TokenInformationLength
0x18008f0c3  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18008f0c7  lea     edx, [r9+8]; TokenInformationClass
0x18008f0cb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18008f0cf  call    cs:__imp_GetTokenInformation
0x18008f0d5  mov     rcx, [rbp+18h]; this
0x18008f0d9  test    eax, eax
0x18008f0db  jnz     short loc_18008F0ED
0x18008f0dd  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008f0e4  lea     edx, [rax+4Eh]; void *
0x18008f0e7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008f0ed  xor     r9d, r9d
0x18008f0f0  mov     r8, [rbp+Block]
0x18008f0f4  mov     r8, [r8]
0x18008f0f7  mov     edx, [rbp+TokenInformation]
0x18008f0fa  mov     rcx, rdi
0x18008f0fd  call    cs:__imp_EnsureStoreLicenseForPackageActivation
0x18008f103  mov     ebx, eax
0x18008f105  test    eax, eax
0x18008f107  jns     short loc_18008F113
0x18008f109  bt      eax, 1Dh
0x18008f10d  jnb     short loc_18008F113
0x18008f10f  btr     ebx, 1Dh
0x18008f113  mov     rcx, [rbp+Block]; Block
0x18008f117  mov     [rbp+Block], 0
0x18008f11f  test    rcx, rcx
0x18008f122  jz      short loc_18008F12A
0x18008f124  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008f129  nop
0x18008f12a  lea     rcx, [rbp+TokenHandle]
0x18008f12e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008f133  mov     eax, ebx
0x18008f135  add     rsp, 40h
0x18008f139  pop     rdi
0x18008f13a  pop     rbx
0x18008f13b  pop     rbp
0x18008f13c  retn
```
