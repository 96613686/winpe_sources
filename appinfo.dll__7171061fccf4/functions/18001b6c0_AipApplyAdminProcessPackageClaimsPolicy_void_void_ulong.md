# AipApplyAdminProcessPackageClaimsPolicy(void * *,void *,ulong)

- ea: `0x18001b6c0`
- end: `0x18001b7b8`
- name: `?AipApplyAdminProcessPackageClaimsPolicy@@YAKPEAPEAXPEAXK@Z`
- size: `248`
- prototype: `RPC_STATUS __fastcall(void **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18003d070`

## callees

- `0x18000bde0`
- `0x18000c410`
- `0x180011ffc`
- `0x18001b6c0`
- `0x18001b7c0`
- `0x18002d2d4`
- `0x18003bb18`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001b736`
- `RPCRT4!RpcImpersonateClient` at `0x18001b736`
- `RPCRT4!RpcRevertToSelf` at `0x18001b761`
- `RPCRT4!RpcRevertToSelf` at `0x18001b761`
- `ntdll!NtClose` at `0x18001b787`
- `ntdll!NtClose` at `0x18001b787`

## pseudocode

```c
RPC_STATUS __fastcall AipApplyAdminProcessPackageClaimsPolicy(void **a1, void *a2, unsigned int a3)
{
  int v6; // eax
  RPC_STATUS v8; // ebx
  int v9; // ebx
  void *v10; // rbx
  void *v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v6 = AppModelPolicy_GetPolicy_Internal(a2, 35, &v14, &v13, &v12) | 0x10000000;
  if ( v6 < 0 )
    return WIN32_FROM_HRESULT(v6);
  if ( v14 != 2293761 )
    goto LABEL_9;
  v8 = RpcImpersonateClient(0);
  if ( !v8 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v11,
      0);
    v9 = AdjustActivationTokenToMatch(*a1, a2, a3, &v11);
    RpcRevertToSelf();
    if ( v9 )
    {
      v8 = WIN32_FROM_NTSTATUS(v9);
      goto LABEL_10;
    }
    v10 = v11;
    if ( (char *)v11 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      NtClose(*a1);
      v11 = 0;
      *a1 = v10;
    }
LABEL_9:
    v8 = 0;
  }
LABEL_10:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return v8;
}

```

## disassembly

```asm
0x18001b6c0  mov     [rsp-18h+arg_0], rbx
0x18001b6c5  mov     [rsp-18h+arg_8], rsi
0x18001b6ca  push    rbp
0x18001b6cb  push    rdi
0x18001b6cc  push    r14
0x18001b6ce  mov     rbp, rsp
0x18001b6d1  sub     rsp, 50h
0x18001b6d5  mov     rsi, rdx
0x18001b6d8  mov     [rbp+arg_18], 0
0x18001b6df  mov     r14d, r8d
0x18001b6e2  mov     [rbp+var_20], 0
0x18001b6ea  mov     rdi, rcx
0x18001b6ed  mov     [rbp+var_18], 0
0x18001b6f5  lea     rax, [rbp+var_18]
0x18001b6f9  mov     [rbp+var_10], 0
0x18001b701  mov     rcx, rsi
0x18001b704  mov     [rsp+50h+var_30], rax
0x18001b709  lea     r9, [rbp+var_10]
0x18001b70d  mov     edx, 23h ; '#'
0x18001b712  lea     r8, [rbp+arg_18]
0x18001b716  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18001b71b  or      eax, 10000000h
0x18001b720  jge     short loc_18001B72B
0x18001b722  mov     ecx, eax; int
0x18001b724  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001b729  jmp     short loc_18001B7A5
0x18001b72b  cmp     [rbp+arg_18], 230001h
0x18001b732  jnz     short loc_18001B798
0x18001b734  xor     ecx, ecx; BindingHandle
0x18001b736  call    cs:__imp_RpcImpersonateClient
0x18001b73c  mov     ebx, eax
0x18001b73e  test    eax, eax
0x18001b740  jnz     short loc_18001B79A
0x18001b742  xor     edx, edx
0x18001b744  lea     rcx, [rbp+var_20]
0x18001b748  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001b74d  mov     rcx, [rdi]; void *
0x18001b750  lea     r9, [rbp+var_20]; void **
0x18001b754  mov     r8d, r14d; unsigned int
0x18001b757  mov     rdx, rsi; void *
0x18001b75a  call    ?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z; AdjustActivationTokenToMatch(void *,void *,ulong,void * *)
0x18001b75f  mov     ebx, eax
0x18001b761  call    cs:__imp_RpcRevertToSelf
0x18001b767  test    ebx, ebx
0x18001b769  jz      short loc_18001B776
0x18001b76b  mov     ecx, ebx; int
0x18001b76d  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x18001b772  mov     ebx, eax
0x18001b774  jmp     short loc_18001B79A
0x18001b776  mov     rbx, [rbp+var_20]
0x18001b77a  lea     rax, [rbx-1]
0x18001b77e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b782  ja      short loc_18001B798
0x18001b784  mov     rcx, [rdi]; Handle
0x18001b787  call    cs:__imp_NtClose
0x18001b78d  mov     [rbp+var_20], 0
0x18001b795  mov     [rdi], rbx
0x18001b798  xor     ebx, ebx
0x18001b79a  lea     rcx, [rbp+var_20]
0x18001b79e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b7a3  mov     eax, ebx
0x18001b7a5  mov     rbx, [rsp+50h+arg_0]
0x18001b7aa  mov     rsi, [rsp+50h+arg_8]
0x18001b7af  add     rsp, 50h
0x18001b7b3  pop     r14
0x18001b7b5  pop     rdi
0x18001b7b6  pop     rbp
0x18001b7b7  retn
```
