# access_token_provider::capture_current(void)

- ea: `0x1800e0720`
- end: `0x1800e07eb`
- name: `?capture_current@access_token_provider@@SA?AU1@XZ`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e05ac`

## callees

- `0x18004b638`
- `0x18005e788`
- `0x1800e0720`
- `0x1800e95f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0788`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e0799`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e0799`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0736`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e074d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e074d`

## string_xrefs

- `0x1800e07a8`: `onecoreuap\base\appmodel\Search\common\include\access_token_provider.h`
- `0x1800e0769`: `onecoreuap\base\appmodel\Search\common\include\thread_impersonation_token.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall access_token_provider::capture_current(void **a1)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  void **v4; // rbx
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    *a1 = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\thread_impersonation_token.h",
        v3);
    v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, v4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\access_token_provider.h",
        v6);
    *a1 = TokenHandle;
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  return a1;
}

```

## disassembly

```asm
0x1800e0720  mov     [rsp+arg_0], rbx
0x1800e0725  push    rdi
0x1800e0726  sub     rsp, 30h
0x1800e072a  mov     rdi, rcx
0x1800e072d  mov     [rsp+38h+TokenHandle], 0
0x1800e0736  call    cs:__imp_GetCurrentThread
0x1800e073c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800e0741  mov     edx, 0Eh; DesiredAccess
0x1800e0746  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800e074a  mov     rcx, rax; ThreadHandle
0x1800e074d  call    cs:__imp_OpenThreadToken
0x1800e0753  test    eax, eax
0x1800e0755  jnz     short loc_1800E07D5
0x1800e0757  call    cs:__imp_GetLastError
0x1800e075d  cmp     eax, 3F0h
0x1800e0762  jz      short loc_1800E077B
0x1800e0764  mov     rcx, [rsp+38h]; this
0x1800e0769  lea     r8, aOnecoreuapBase_259; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e0770  mov     edx, 18h; void *
0x1800e0775  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e077b  lea     rcx, [rsp+38h+TokenHandle]
0x1800e0780  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800e0785  mov     rbx, rax
0x1800e0788  call    cs:__imp_GetCurrentProcess
0x1800e078e  mov     r8, rbx; TokenHandle
0x1800e0791  mov     edx, 0Ah; DesiredAccess
0x1800e0796  mov     rcx, rax; ProcessHandle
0x1800e0799  call    cs:__imp_OpenProcessToken
0x1800e079f  mov     rcx, [rsp+38h]; this
0x1800e07a4  test    eax, eax
0x1800e07a6  jnz     short loc_1800E07B8
0x1800e07a8  lea     r8, aOnecoreuapBase_165; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e07af  lea     edx, [rax+1Dh]; void *
0x1800e07b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e07b8  mov     rax, [rsp+38h+TokenHandle]
0x1800e07bd  mov     [rdi], rax
0x1800e07c0  mov     [rsp+38h+TokenHandle], 0
0x1800e07c9  lea     rcx, [rsp+38h+TokenHandle]
0x1800e07ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e07d3  jmp     short loc_1800E07DD
0x1800e07d5  mov     rax, [rsp+38h+TokenHandle]
0x1800e07da  mov     [rdi], rax
0x1800e07dd  mov     rax, rdi
0x1800e07e0  mov     rbx, [rsp+38h+arg_0]
0x1800e07e5  add     rsp, 30h
0x1800e07e9  pop     rdi
0x1800e07ea  retn
```
