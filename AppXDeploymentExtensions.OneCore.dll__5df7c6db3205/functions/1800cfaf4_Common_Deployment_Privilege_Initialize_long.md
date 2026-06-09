# Common::Deployment::Privilege::Initialize(long)

- ea: `0x1800cfaf4`
- end: `0x1800cfbe4`
- name: `?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z`
- size: `240`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c148`
- `0x1800cf838`
- `0x18019bf50`
- `0x1801e6c58`

## callees

- `0x180098bf4`
- `0x1800a2854`
- `0x1800baaac`
- `0x1800bc4a0`
- `0x1800cfaf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfb95`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cfb25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cfb8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cfb25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cfb8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cfb10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cfb76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cfb10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cfb76`

## string_xrefs

- `0x1800cfb54`: `onecore\admin\appmodel\common\privilege.cpp`
- `0x1800cfba4`: `onecore\admin\appmodel\common\privilege.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::Privilege::Initialize(PHANDLE TokenHandle, int a2)
{
  void *v2; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE v9; // rax
  unsigned int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)a2;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      v6 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)(TokenHandle + 3));
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecore\\admin\\appmodel\\common\\privilege.cpp",
          (const char *)(unsigned int)v6,
          v10);
        return v7;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        TokenHandle,
        0);
      v9 = GetCurrentThread();
      if ( OpenThreadToken(v9, 0x28u, 1, TokenHandle) )
        goto LABEL_9;
      LastError = GetLastError();
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1A,
               (unsigned int)"onecore\\admin\\appmodel\\common\\privilege.cpp",
               (const char *)LastError,
               v10);
  }
LABEL_9:
  TokenHandle[1] = v2;
  return 0;
}

```

## disassembly

```asm
0x1800cfaf4  mov     [rsp+arg_8], rbx
0x1800cfaf9  mov     [rsp+arg_10], rsi
0x1800cfafe  push    rdi; unsigned int
0x1800cfaff  sub     rsp, 20h
0x1800cfb03  movsxd  rsi, edx
0x1800cfb06  mov     rdi, rcx
0x1800cfb09  xor     edx, edx
0x1800cfb0b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cfb10  call    cs:__imp_GetCurrentThread
0x1800cfb16  mov     edx, 28h ; '('; DesiredAccess
0x1800cfb1b  mov     r9, rdi; TokenHandle
0x1800cfb1e  mov     rcx, rax; ThreadHandle
0x1800cfb21  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800cfb25  call    cs:__imp_OpenThreadToken
0x1800cfb2b  test    eax, eax
0x1800cfb2d  jnz     loc_1800CFBBA
0x1800cfb33  call    cs:__imp_GetLastError
0x1800cfb39  cmp     eax, 3F0h
0x1800cfb3e  jnz     short loc_1800CFB9B
0x1800cfb40  lea     rcx, [rdi+18h]; this
0x1800cfb44  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x1800cfb49  mov     ebx, eax
0x1800cfb4b  test    eax, eax
0x1800cfb4d  jns     short loc_1800CFB6C
0x1800cfb4f  mov     rcx, [rsp+28h]; this
0x1800cfb54  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\privi"...
0x1800cfb5b  mov     r9d, eax; char *
0x1800cfb5e  mov     edx, 17h; void *
0x1800cfb63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfb68  mov     eax, ebx
0x1800cfb6a  jmp     short loc_1800CFBD4
0x1800cfb6c  xor     edx, edx
0x1800cfb6e  mov     rcx, rdi
0x1800cfb71  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cfb76  call    cs:__imp_GetCurrentThread
0x1800cfb7c  mov     edx, 28h ; '('; DesiredAccess
0x1800cfb81  mov     r9, rdi; TokenHandle
0x1800cfb84  mov     rcx, rax; ThreadHandle
0x1800cfb87  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800cfb8b  call    cs:__imp_OpenThreadToken
0x1800cfb91  test    eax, eax
0x1800cfb93  jnz     short loc_1800CFBBA
0x1800cfb95  call    cs:__imp_GetLastError
0x1800cfb9b  test    eax, eax
0x1800cfb9d  jz      short loc_1800CFBBA
0x1800cfb9f  mov     rcx, [rsp+28h]; this
0x1800cfba4  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\privi"...
0x1800cfbab  mov     r9d, eax; char *
0x1800cfbae  mov     edx, 1Ah; void *
0x1800cfbb3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cfbb8  jmp     short loc_1800CFBD4
0x1800cfbba  mov     rax, rsi
0x1800cfbbd  mov     dword ptr [rsp+28h+arg_0], eax
0x1800cfbc1  shr     rax, 20h
0x1800cfbc5  mov     dword ptr [rsp+28h+arg_0+4], eax
0x1800cfbc9  mov     rax, [rsp+28h+arg_0]
0x1800cfbce  mov     [rdi+8], rax
0x1800cfbd2  xor     eax, eax
0x1800cfbd4  mov     rbx, [rsp+28h+arg_8]
0x1800cfbd9  mov     rsi, [rsp+28h+arg_10]
0x1800cfbde  add     rsp, 20h
0x1800cfbe2  pop     rdi
0x1800cfbe3  retn
```
