# AipApplyAdminProcessPackageClaimsPolicy(void * *,void *,ulong)

- ea: `0x180019704`
- end: `0x180019803`
- name: `?AipApplyAdminProcessPackageClaimsPolicy@@YAKPEAPEAXPEAXK@Z`
- size: `255`
- prototype: `unsigned int __fastcall(void **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18003ac30`

## callees

- `0x18000c790`
- `0x18000f9e0`
- `0x1800168b0`
- `0x180019704`
- `0x18001980c`
- `0x1800296bc`
- `0x1800396ec`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180019771`
- `RPCRT4!RpcImpersonateClient` at `0x180019771`
- `RPCRT4!RpcRevertToSelf` at `0x1800197a2`
- `RPCRT4!RpcRevertToSelf` at `0x1800197a2`
- `ntdll!NtClose` at `0x1800197ce`
- `ntdll!NtClose` at `0x1800197ce`

## pseudocode

```c
RPC_STATUS __fastcall AipApplyAdminProcessPackageClaimsPolicy(void **a1, void *a2, char a3)
{
  int v6; // eax
  RPC_STATUS v8; // ebx
  LONG v9; // ebx
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
0x180019704  mov     [rsp-18h+arg_0], rbx
0x180019709  mov     [rsp-18h+arg_8], rsi
0x18001970e  push    rbp
0x18001970f  push    rdi
0x180019710  push    r14
0x180019712  mov     rbp, rsp
0x180019715  sub     rsp, 50h
0x180019719  and     [rbp+arg_18], 0
0x18001971d  lea     rax, [rbp+var_18]
0x180019721  and     [rbp+var_20], 0
0x180019726  lea     r9, [rbp+var_10]
0x18001972a  and     [rbp+var_18], 0
0x18001972f  mov     rsi, rdx
0x180019732  and     [rbp+var_10], 0
0x180019737  mov     r14d, r8d
0x18001973a  mov     rdi, rcx
0x18001973d  mov     [rsp+50h+var_30], rax
0x180019742  mov     rcx, rsi
0x180019745  lea     r8, [rbp+arg_18]
0x180019749  mov     edx, 23h ; '#'
0x18001974e  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x180019753  or      eax, 10000000h
0x180019758  jge     short loc_180019766
0x18001975a  mov     ecx, eax; int
0x18001975c  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180019761  jmp     loc_1800197EF
0x180019766  cmp     [rbp+arg_18], 230001h
0x18001976d  jnz     short loc_1800197E2
0x18001976f  xor     ecx, ecx; BindingHandle
0x180019771  call    cs:__imp_RpcImpersonateClient
0x180019778  nop     dword ptr [rax+rax+00h]
0x18001977d  mov     ebx, eax
0x18001977f  test    eax, eax
0x180019781  jnz     short loc_1800197E4
0x180019783  xor     edx, edx
0x180019785  lea     rcx, [rbp+var_20]
0x180019789  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001978e  mov     rcx, [rdi]; void *
0x180019791  lea     r9, [rbp+var_20]; void **
0x180019795  mov     r8d, r14d; unsigned int
0x180019798  mov     rdx, rsi; void *
0x18001979b  call    ?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z; AdjustActivationTokenToMatch(void *,void *,ulong,void * *)
0x1800197a0  mov     ebx, eax
0x1800197a2  call    cs:__imp_RpcRevertToSelf
0x1800197a9  nop     dword ptr [rax+rax+00h]
0x1800197ae  test    ebx, ebx
0x1800197b0  jz      short loc_1800197BD
0x1800197b2  mov     ecx, ebx; int
0x1800197b4  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x1800197b9  mov     ebx, eax
0x1800197bb  jmp     short loc_1800197E4
0x1800197bd  mov     rbx, [rbp+var_20]
0x1800197c1  lea     rax, [rbx-1]
0x1800197c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800197c9  ja      short loc_1800197E2
0x1800197cb  mov     rcx, [rdi]; Handle
0x1800197ce  call    cs:__imp_NtClose
0x1800197d5  nop     dword ptr [rax+rax+00h]
0x1800197da  and     [rbp+var_20], 0
0x1800197df  mov     [rdi], rbx
0x1800197e2  xor     ebx, ebx
0x1800197e4  lea     rcx, [rbp+var_20]
0x1800197e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800197ed  mov     eax, ebx
0x1800197ef  mov     rbx, [rsp+50h+arg_0]
0x1800197f4  mov     rsi, [rsp+50h+arg_8]
0x1800197f9  add     rsp, 50h
0x1800197fd  pop     r14
0x1800197ff  pop     rdi
0x180019800  pop     rbp
0x180019801  retn
```
