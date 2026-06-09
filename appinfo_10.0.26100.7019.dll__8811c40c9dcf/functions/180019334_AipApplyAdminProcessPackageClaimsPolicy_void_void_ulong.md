# AipApplyAdminProcessPackageClaimsPolicy(void * *,void *,ulong)

- ea: `0x180019334`
- end: `0x180019433`
- name: `?AipApplyAdminProcessPackageClaimsPolicy@@YAKPEAPEAXPEAXK@Z`
- size: `255`
- prototype: `unsigned int __fastcall(void **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180039cb0`

## callees

- `0x18000c790`
- `0x18000f8b0`
- `0x180016760`
- `0x180019334`
- `0x18001943c`
- `0x18002ac3c`
- `0x180038d0c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800193d2`
- `RPCRT4!RpcRevertToSelf` at `0x1800193d2`
- `RPCRT4!RpcImpersonateClient` at `0x1800193a1`
- `RPCRT4!RpcImpersonateClient` at `0x1800193a1`
- `ntdll!NtClose` at `0x1800193fe`
- `ntdll!NtClose` at `0x1800193fe`

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
0x180019334  mov     [rsp-18h+arg_0], rbx
0x180019339  mov     [rsp-18h+arg_8], rsi
0x18001933e  push    rbp
0x18001933f  push    rdi
0x180019340  push    r14
0x180019342  mov     rbp, rsp
0x180019345  sub     rsp, 50h
0x180019349  and     [rbp+arg_18], 0
0x18001934d  lea     rax, [rbp+var_18]
0x180019351  and     [rbp+var_20], 0
0x180019356  lea     r9, [rbp+var_10]
0x18001935a  and     [rbp+var_18], 0
0x18001935f  mov     rsi, rdx
0x180019362  and     [rbp+var_10], 0
0x180019367  mov     r14d, r8d
0x18001936a  mov     rdi, rcx
0x18001936d  mov     [rsp+50h+var_30], rax
0x180019372  mov     rcx, rsi
0x180019375  lea     r8, [rbp+arg_18]
0x180019379  mov     edx, 23h ; '#'
0x18001937e  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x180019383  or      eax, 10000000h
0x180019388  jge     short loc_180019396
0x18001938a  mov     ecx, eax; int
0x18001938c  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180019391  jmp     loc_18001941F
0x180019396  cmp     [rbp+arg_18], 230001h
0x18001939d  jnz     short loc_180019412
0x18001939f  xor     ecx, ecx; BindingHandle
0x1800193a1  call    cs:__imp_RpcImpersonateClient
0x1800193a8  nop     dword ptr [rax+rax+00h]
0x1800193ad  mov     ebx, eax
0x1800193af  test    eax, eax
0x1800193b1  jnz     short loc_180019414
0x1800193b3  xor     edx, edx
0x1800193b5  lea     rcx, [rbp+var_20]
0x1800193b9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800193be  mov     rcx, [rdi]; void *
0x1800193c1  lea     r9, [rbp+var_20]; void **
0x1800193c5  mov     r8d, r14d; unsigned int
0x1800193c8  mov     rdx, rsi; void *
0x1800193cb  call    ?AdjustActivationTokenToMatch@@YAJPEAX0KPEAPEAX@Z; AdjustActivationTokenToMatch(void *,void *,ulong,void * *)
0x1800193d0  mov     ebx, eax
0x1800193d2  call    cs:__imp_RpcRevertToSelf
0x1800193d9  nop     dword ptr [rax+rax+00h]
0x1800193de  test    ebx, ebx
0x1800193e0  jz      short loc_1800193ED
0x1800193e2  mov     ecx, ebx; int
0x1800193e4  call    ?WIN32_FROM_NTSTATUS@@YAKJ@Z; WIN32_FROM_NTSTATUS(long)
0x1800193e9  mov     ebx, eax
0x1800193eb  jmp     short loc_180019414
0x1800193ed  mov     rbx, [rbp+var_20]
0x1800193f1  lea     rax, [rbx-1]
0x1800193f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800193f9  ja      short loc_180019412
0x1800193fb  mov     rcx, [rdi]; Handle
0x1800193fe  call    cs:__imp_NtClose
0x180019405  nop     dword ptr [rax+rax+00h]
0x18001940a  and     [rbp+var_20], 0
0x18001940f  mov     [rdi], rbx
0x180019412  xor     ebx, ebx
0x180019414  lea     rcx, [rbp+var_20]
0x180019418  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001941d  mov     eax, ebx
0x18001941f  mov     rbx, [rsp+50h+arg_0]
0x180019424  mov     rsi, [rsp+50h+arg_8]
0x180019429  add     rsp, 50h
0x18001942d  pop     r14
0x18001942f  pop     rdi
0x180019430  pop     rbp
0x180019431  retn
```
