# ImpersonateAndSetProxyBlanketForCallback(IUnknown *)

- ea: `0x18000d284`
- end: `0x18000d383`
- name: `?ImpersonateAndSetProxyBlanketForCallback@@YAJPEAUIUnknown@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cd8c`

## callees

- `0x18000d284`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d2dd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d343`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d2dd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d343`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d35c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d35c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000d29f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000d29f`

## pseudocode

```c
__int64 __fastcall ImpersonateAndSetProxyBlanketForCallback(IUnknown *pProxy)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  IUnknown *pProxya; // [rsp+58h] [rbp+10h] BYREF

  pProxya = 0;
  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( v2 == -2147417833 )
      return 0;
  }
  else
  {
    v3 = CoSetProxyBlanket(
           pProxy,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           0,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x20u);
    if ( (unsigned int)(v3 + 2147467263) <= 1 )
    {
      v3 = 0;
    }
    else if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
             pProxy,
             &IID_IUnknown,
             &pProxya);
      if ( v3 >= 0 )
      {
        v3 = CoSetProxyBlanket(
               pProxya,
               0xFFFFFFFF,
               0xFFFFFFFF,
               (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
               0,
               0,
               (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
               0x20u);
        ((void (__fastcall *)(IUnknown *))pProxya->lpVtbl->Release)(pProxya);
      }
    }
    CoRevertToSelf();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000d284  mov     [rsp+arg_0], rbx
0x18000d289  mov     [rsp+arg_10], rbp
0x18000d28e  push    rdi
0x18000d28f  sub     rsp, 40h
0x18000d293  mov     rdi, rcx
0x18000d296  mov     [rsp+48h+pProxy], 0
0x18000d29f  call    cs:__imp_CoImpersonateClient
0x18000d2a5  mov     ebx, eax
0x18000d2a7  test    eax, eax
0x18000d2a9  js      loc_18000D378
0x18000d2af  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18000d2b7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000d2bb  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18000d2bf  mov     [rsp+48h+pAuthInfo], rbp; pAuthInfo
0x18000d2c4  mov     [rsp+48h+dwImpLevel], 0; dwImpLevel
0x18000d2cc  mov     r9, rbp; pServerPrincName
0x18000d2cf  or      edx, r8d; dwAuthnSvc
0x18000d2d2  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x18000d2da  mov     rcx, rdi; pProxy
0x18000d2dd  call    cs:__imp_CoSetProxyBlanket
0x18000d2e3  mov     ebx, eax
0x18000d2e5  add     eax, 7FFFBFFFh
0x18000d2ea  cmp     eax, 1
0x18000d2ed  jbe     loc_18000D374
0x18000d2f3  test    ebx, ebx
0x18000d2f5  js      short loc_18000D35C
0x18000d2f7  mov     rax, [rdi]
0x18000d2fa  lea     r8, [rsp+48h+pProxy]
0x18000d2ff  lea     rdx, IID_IUnknown
0x18000d306  mov     rcx, rdi
0x18000d309  mov     rax, [rax]
0x18000d30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d311  mov     ebx, eax
0x18000d313  test    eax, eax
0x18000d315  js      short loc_18000D35C
0x18000d317  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18000d31c  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18000d320  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18000d328  or      edx, r8d; dwAuthnSvc
0x18000d32b  mov     [rsp+48h+pAuthInfo], rbp; pAuthInfo
0x18000d330  mov     r9, rbp; pServerPrincName
0x18000d333  mov     [rsp+48h+dwImpLevel], 0; dwImpLevel
0x18000d33b  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x18000d343  call    cs:__imp_CoSetProxyBlanket
0x18000d349  mov     rcx, [rsp+48h+pProxy]
0x18000d34e  mov     ebx, eax
0x18000d350  mov     rax, [rcx]
0x18000d353  mov     rax, [rax+10h]
0x18000d357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d35c  call    cs:__imp_CoRevertToSelf
0x18000d362  mov     rbp, [rsp+48h+arg_10]
0x18000d367  mov     eax, ebx
0x18000d369  mov     rbx, [rsp+48h+arg_0]
0x18000d36e  add     rsp, 40h
0x18000d372  pop     rdi
0x18000d373  retn
0x18000d374  xor     ebx, ebx
0x18000d376  jmp     short loc_18000D35C
0x18000d378  cmp     eax, 80010117h
0x18000d37d  jnz     short loc_18000D362
0x18000d37f  xor     ebx, ebx
0x18000d381  jmp     short loc_18000D362
```
