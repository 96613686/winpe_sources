# WindowsStorage::Utilities::Identity::_GetImpersonationTokenFromProcess(void *)

- ea: `0x1800142cc`
- end: `0x18001439d`
- name: `?_GetImpersonationTokenFromProcess@Identity@Utilities@WindowsStorage@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `209`
- prototype: `void **__fastcall(__int64, void **, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012b7c`

## callees

- `0x18000d4e0`
- `0x180010654`
- `0x1800142cc`
- `0x180014400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001430d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001430d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180014363`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180014363`

## pseudocode

```c
void **__fastcall WindowsStorage::Utilities::Identity::_GetImpersonationTokenFromProcess(
        __int64 a1,
        void **a2,
        void *a3)
{
  const char *v5; // r9
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  void **v10; // [rsp+58h] [rbp+10h]

  v10 = a2;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( !OpenProcessToken(a3, 0xEu, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
      v5);
  *a2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  if ( !DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
      v6);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return a2;
}

```

## disassembly

```asm
0x1800142cc  mov     rax, rsp
0x1800142cf  mov     [rax+18h], rbx
0x1800142d3  mov     [rax+10h], rdx
0x1800142d7  mov     [rax+8], rcx
0x1800142db  push    rdi
0x1800142dc  sub     rsp, 40h
0x1800142e0  mov     rbx, r8
0x1800142e3  mov     rdi, rdx
0x1800142e6  mov     dword ptr [rax-18h], 0
0x1800142ed  mov     qword ptr [rax+8], 0
0x1800142f5  xor     edx, edx
0x1800142f7  lea     rcx, [rax+8]
0x1800142fb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180014300  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180014305  mov     edx, 0Eh; DesiredAccess
0x18001430a  mov     rcx, rbx; ProcessHandle
0x18001430d  call    cs:__imp_OpenProcessToken
0x180014313  mov     rcx, [rsp+48h]; this
0x180014318  test    eax, eax
0x18001431a  jnz     short loc_18001432E
0x18001431c  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180014323  mov     edx, 117h; void *
0x180014328  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001432e  mov     qword ptr [rdi], 0
0x180014335  mov     [rsp+48h+var_18], 1
0x18001433d  xor     edx, edx
0x18001433f  mov     rcx, rdi
0x180014342  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180014347  mov     [rsp+48h+phNewToken], rdi; phNewToken
0x18001434c  mov     r9d, 2; ImpersonationLevel
0x180014352  mov     [rsp+48h+TokenType], r9d; TokenType
0x180014357  xor     r8d, r8d; lpTokenAttributes
0x18001435a  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18001435e  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x180014363  call    cs:__imp_DuplicateTokenEx
0x180014369  mov     rcx, [rsp+48h]; this
0x18001436e  test    eax, eax
0x180014370  jnz     short loc_180014384
0x180014372  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180014379  mov     edx, 11Ah; void *
0x18001437e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180014384  lea     rcx, [rsp+48h+TokenHandle]
0x180014389  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001438e  mov     rax, rdi
0x180014391  mov     rbx, [rsp+48h+arg_10]
0x180014396  add     rsp, 40h
0x18001439a  pop     rdi
0x18001439b  retn
```
