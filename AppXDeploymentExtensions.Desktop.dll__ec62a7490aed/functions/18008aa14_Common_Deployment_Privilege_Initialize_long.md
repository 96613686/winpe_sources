# Common::Deployment::Privilege::Initialize(long)

- ea: `0x18008aa14`
- end: `0x18008ab29`
- name: `?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z`
- size: `277`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066ce0`
- `0x1800685b8`
- `0x18008a774`
- `0x180185958`

## callees

- `0x18001adb4`
- `0x18004e96c`
- `0x180069eb4`
- `0x18008aa14`
- `0x18008ab30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aad3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008aa4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008aac3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008aa4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008aac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008aa30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008aaa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008aa30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008aaa8`

## string_xrefs

- `0x18008aa86`: `onecore\admin\appmodel\common\privilege.cpp`
- `0x18008aae8`: `onecore\admin\appmodel\common\privilege.cpp`

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
0x18008aa14  mov     [rsp+arg_8], rbx
0x18008aa19  mov     [rsp+arg_10], rsi
0x18008aa1e  push    rdi; unsigned int
0x18008aa1f  sub     rsp, 20h
0x18008aa23  movsxd  rsi, edx
0x18008aa26  mov     rdi, rcx
0x18008aa29  xor     edx, edx
0x18008aa2b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008aa30  call    cs:__imp_GetCurrentThread
0x18008aa37  nop     dword ptr [rax+rax+00h]
0x18008aa3c  mov     edx, 28h ; '('; DesiredAccess
0x18008aa41  mov     r9, rdi; TokenHandle
0x18008aa44  mov     rcx, rax; ThreadHandle
0x18008aa47  lea     r8d, [rdx-27h]; OpenAsSelf
0x18008aa4b  call    cs:__imp_OpenThreadToken
0x18008aa52  nop     dword ptr [rax+rax+00h]
0x18008aa57  test    eax, eax
0x18008aa59  jnz     loc_18008AAFE
0x18008aa5f  call    cs:__imp_GetLastError
0x18008aa66  nop     dword ptr [rax+rax+00h]
0x18008aa6b  cmp     eax, 3F0h
0x18008aa70  jnz     short loc_18008AADF
0x18008aa72  lea     rcx, [rdi+18h]; this
0x18008aa76  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x18008aa7b  mov     ebx, eax
0x18008aa7d  test    eax, eax
0x18008aa7f  jns     short loc_18008AA9E
0x18008aa81  mov     rcx, [rsp+28h]; this
0x18008aa86  lea     r8, aOnecoreAdminAp_33; "onecore\\admin\\appmodel\\common\\privi"...
0x18008aa8d  mov     r9d, eax; char *
0x18008aa90  mov     edx, 17h; void *
0x18008aa95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008aa9a  mov     eax, ebx
0x18008aa9c  jmp     short loc_18008AB18
0x18008aa9e  xor     edx, edx
0x18008aaa0  mov     rcx, rdi
0x18008aaa3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008aaa8  call    cs:__imp_GetCurrentThread
0x18008aaaf  nop     dword ptr [rax+rax+00h]
0x18008aab4  mov     edx, 28h ; '('; DesiredAccess
0x18008aab9  mov     r9, rdi; TokenHandle
0x18008aabc  mov     rcx, rax; ThreadHandle
0x18008aabf  lea     r8d, [rdx-27h]; OpenAsSelf
0x18008aac3  call    cs:__imp_OpenThreadToken
0x18008aaca  nop     dword ptr [rax+rax+00h]
0x18008aacf  test    eax, eax
0x18008aad1  jnz     short loc_18008AAFE
0x18008aad3  call    cs:__imp_GetLastError
0x18008aada  nop     dword ptr [rax+rax+00h]
0x18008aadf  test    eax, eax
0x18008aae1  jz      short loc_18008AAFE
0x18008aae3  mov     rcx, [rsp+28h]; this
0x18008aae8  lea     r8, aOnecoreAdminAp_33; "onecore\\admin\\appmodel\\common\\privi"...
0x18008aaef  mov     r9d, eax; char *
0x18008aaf2  mov     edx, 1Ah; void *
0x18008aaf7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008aafc  jmp     short loc_18008AB18
0x18008aafe  mov     rax, rsi
0x18008ab01  mov     dword ptr [rsp+28h+arg_0], eax
0x18008ab05  shr     rax, 20h
0x18008ab09  mov     dword ptr [rsp+28h+arg_0+4], eax
0x18008ab0d  mov     rax, [rsp+28h+arg_0]
0x18008ab12  mov     [rdi+8], rax
0x18008ab16  xor     eax, eax
0x18008ab18  mov     rbx, [rsp+28h+arg_8]
0x18008ab1d  mov     rsi, [rsp+28h+arg_10]
0x18008ab22  add     rsp, 20h
0x18008ab26  pop     rdi
0x18008ab27  retn
```
