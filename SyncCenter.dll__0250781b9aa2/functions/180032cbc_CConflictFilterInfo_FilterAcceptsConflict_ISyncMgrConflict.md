# CConflictFilterInfo::FilterAcceptsConflict(ISyncMgrConflict *)

- ea: `0x180032cbc`
- end: `0x180032dbd`
- name: `?FilterAcceptsConflict@CConflictFilterInfo@@QEAAHPEAUISyncMgrConflict@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, struct ISyncMgrConflict *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800375d0`
- `0x1800473b4`

## callees

- `0x18000a8ac`
- `0x180032cbc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032da8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032d18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032d5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032d18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032d5f`
- `PROPSYS!PropVariantToStringAlloc` at `0x180032d0e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180032d55`
- `PROPSYS!PropVariantToStringAlloc` at `0x180032d0e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180032d55`

## pseudocode

```c
__int64 __fastcall CConflictFilterInfo::FilterAcceptsConflict(PCNZWCH lpString1, struct ISyncMgrConflict *a2)
{
  struct ISyncMgrConflictVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetProperty)(ISyncMgrConflict *, const PROPERTYKEY *const, PROPVARIANT *); // rax
  struct ISyncMgrConflictVtbl *v6; // rax
  unsigned int v7; // ebx
  PROPVARIANT propvar[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h]
  PWSTR v11; // [rsp+60h] [rbp+20h] BYREF
  PWSTR ppszOut; // [rsp+68h] [rbp+28h] BYREF

  v10 = 0;
  lpVtbl = a2->lpVtbl;
  v11 = 0;
  ppszOut = 0;
  GetProperty = lpVtbl->GetProperty;
  *(_OWORD *)propvar = 0;
  if ( ((int (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))GetProperty)(
         a2,
         &PKEY_Sync_HandlerID,
         propvar) >= 0 )
  {
    PropVariantToStringAlloc(propvar, &ppszOut);
    PropVariantClear(propvar);
  }
  v11 = 0;
  v10 = 0;
  v6 = a2->lpVtbl;
  *(_OWORD *)propvar = 0;
  if ( ((int (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))v6->GetProperty)(
         a2,
         &PKEY_Sync_ItemID,
         propvar) >= 0 )
  {
    PropVariantToStringAlloc(propvar, &v11);
    PropVariantClear(propvar);
  }
  v7 = 1;
  if ( *lpString1 && !CSyncMgrID::s_AreIDStringsEqual(lpString1, ppszOut)
    || lpString1[64] && !CSyncMgrID::s_AreIDStringsEqual(lpString1 + 64, v11) )
  {
    v7 = 0;
  }
  CoTaskMemFree(ppszOut);
  CoTaskMemFree(v11);
  return v7;
}

```

## disassembly

```asm
0x180032cbc  mov     [rsp-18h+arg_10], rbx
0x180032cc1  push    rbp
0x180032cc2  push    rsi
0x180032cc3  push    rdi
0x180032cc4  mov     rbp, rsp
0x180032cc7  sub     rsp, 40h
0x180032ccb  xor     eax, eax
0x180032ccd  lea     r8, [rbp+propvar]
0x180032cd1  mov     [rbp+var_10], rax
0x180032cd5  mov     rbx, rdx
0x180032cd8  mov     rax, [rdx]
0x180032cdb  mov     rdi, rcx
0x180032cde  xor     esi, esi
0x180032ce0  lea     rdx, PKEY_Sync_HandlerID
0x180032ce7  xorps   xmm0, xmm0
0x180032cea  mov     [rbp+arg_0], rsi
0x180032cee  mov     rcx, rbx
0x180032cf1  mov     [rbp+ppszOut], rsi
0x180032cf5  mov     rax, [rax+18h]
0x180032cf9  movups  xmmword ptr [rbp+propvar], xmm0
0x180032cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d02  test    eax, eax
0x180032d04  js      short loc_180032D1E
0x180032d06  lea     rdx, [rbp+ppszOut]; ppszOut
0x180032d0a  lea     rcx, [rbp+propvar]; propvar
0x180032d0e  call    cs:__imp_PropVariantToStringAlloc
0x180032d14  lea     rcx, [rbp+propvar]; pvar
0x180032d18  call    cs:__imp_PropVariantClear
0x180032d1e  xor     eax, eax
0x180032d20  mov     [rbp+arg_0], rsi
0x180032d24  mov     [rbp+var_10], rax
0x180032d28  lea     r8, [rbp+propvar]
0x180032d2c  mov     rax, [rbx]
0x180032d2f  lea     rdx, PKEY_Sync_ItemID
0x180032d36  xorps   xmm0, xmm0
0x180032d39  mov     rcx, rbx
0x180032d3c  movups  xmmword ptr [rbp+propvar], xmm0
0x180032d40  mov     rax, [rax+18h]
0x180032d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d49  test    eax, eax
0x180032d4b  js      short loc_180032D65
0x180032d4d  lea     rdx, [rbp+arg_0]; ppszOut
0x180032d51  lea     rcx, [rbp+propvar]; propvar
0x180032d55  call    cs:__imp_PropVariantToStringAlloc
0x180032d5b  lea     rcx, [rbp+propvar]; pvar
0x180032d5f  call    cs:__imp_PropVariantClear
0x180032d65  mov     ebx, 1
0x180032d6a  cmp     [rdi], si
0x180032d6d  jz      short loc_180032D7F
0x180032d6f  mov     rdx, [rbp+ppszOut]; lpString2
0x180032d73  mov     rcx, rdi; lpString1
0x180032d76  call    ?s_AreIDStringsEqual@CSyncMgrID@@SA_NPEBG0@Z; CSyncMgrID::s_AreIDStringsEqual(ushort const *,ushort const *)
0x180032d7b  cmp     al, bl
0x180032d7d  jnz     short loc_180032D98
0x180032d7f  lea     rcx, [rdi+80h]; lpString1
0x180032d86  cmp     [rcx], si
0x180032d89  jz      short loc_180032D9A
0x180032d8b  mov     rdx, [rbp+arg_0]; lpString2
0x180032d8f  call    ?s_AreIDStringsEqual@CSyncMgrID@@SA_NPEBG0@Z; CSyncMgrID::s_AreIDStringsEqual(ushort const *,ushort const *)
0x180032d94  cmp     al, bl
0x180032d96  jz      short loc_180032D9A
0x180032d98  mov     ebx, esi
0x180032d9a  mov     rcx, [rbp+ppszOut]; pv
0x180032d9e  call    cs:__imp_CoTaskMemFree
0x180032da4  mov     rcx, [rbp+arg_0]; pv
0x180032da8  call    cs:__imp_CoTaskMemFree
0x180032dae  mov     eax, ebx
0x180032db0  mov     rbx, [rsp+40h+arg_10]
0x180032db5  add     rsp, 40h
0x180032db9  pop     rdi
0x180032dba  pop     rsi
0x180032dbb  pop     rbp
0x180032dbc  retn
```
