# ICondition_GetComparisonInfo_Proxy

- ea: `0x1800726b0`
- end: `0x18007276c`
- name: `ICondition_GetComparisonInfo_Proxy`
- size: `188`
- prototype: `HRESULT __stdcall(ICondition *This, LPWSTR *ppszPropertyName, CONDITION_OPERATION *pcop, PROPVARIANT *ppropvar)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800726b0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072744`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007274e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007274e`

## pseudocode

```c
HRESULT __stdcall ICondition_GetComparisonInfo_Proxy(
        ICondition *This,
        LPWSTR *ppszPropertyName,
        CONDITION_OPERATION *pcop,
        PROPVARIANT *ppropvar)
{
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetComparisonInfo)(ICondition *, LPWSTR *, CONDITION_OPERATION *, PROPVARIANT *); // rax
  HRESULT v9; // eax
  WCHAR *v10; // rcx
  HRESULT v11; // r14d
  void *v12; // xmm1_8
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-20h] BYREF
  void *v15; // [rsp+40h] [rbp-10h]
  CONDITION_OPERATION v16; // [rsp+70h] [rbp+20h] BYREF
  WCHAR *v17; // [rsp+78h] [rbp+28h] BYREF

  v17 = 0;
  v15 = 0;
  lpVtbl = This->lpVtbl;
  v16 = COP_IMPLICIT;
  GetComparisonInfo = lpVtbl->GetComparisonInfo;
  *(_OWORD *)pvar = 0;
  v9 = ((__int64 (__fastcall *)(ICondition *, WCHAR **, CONDITION_OPERATION *, PROPVARIANT *))GetComparisonInfo)(
         This,
         &v17,
         &v16,
         pvar);
  v10 = v17;
  v11 = v9;
  if ( ppszPropertyName )
  {
    *ppszPropertyName = v17;
    v10 = 0;
    v17 = 0;
  }
  if ( pcop )
    *pcop = v16;
  if ( ppropvar )
  {
    v12 = v15;
    *(_OWORD *)ppropvar = *(_OWORD *)pvar;
    v15 = 0;
    ppropvar[2] = v12;
    *(_OWORD *)pvar = 0;
  }
  CoTaskMemFree(v10);
  PropVariantClear(pvar);
  return v11;
}

```

## disassembly

```asm
0x1800726b0  mov     [rsp-18h+arg_10], rbx
0x1800726b5  mov     [rsp-18h+arg_18], rsi
0x1800726ba  push    rbp
0x1800726bb  push    rdi
0x1800726bc  push    r14
0x1800726be  mov     rbp, rsp
0x1800726c1  sub     rsp, 50h
0x1800726c5  xor     eax, eax
0x1800726c7  mov     [rbp+arg_8], 0
0x1800726cf  mov     [rbp+var_10], rax
0x1800726d3  mov     rbx, r9
0x1800726d6  mov     rax, [rcx]
0x1800726d9  lea     r9, [rbp+pvar]
0x1800726dd  mov     rdi, r8
0x1800726e0  mov     [rbp+arg_0], 0
0x1800726e7  mov     rsi, rdx
0x1800726ea  lea     r8, [rbp+arg_0]
0x1800726ee  xorps   xmm0, xmm0
0x1800726f1  lea     rdx, [rbp+arg_8]
0x1800726f5  mov     rax, [rax+50h]
0x1800726f9  movups  xmmword ptr [rbp+pvar], xmm0
0x1800726fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072702  mov     rcx, [rbp+arg_8]
0x180072706  mov     r14d, eax
0x180072709  test    rsi, rsi
0x18007270c  jz      short loc_180072717
0x18007270e  mov     [rsi], rcx
0x180072711  xor     ecx, ecx; pv
0x180072713  mov     [rbp+arg_8], rcx
0x180072717  test    rdi, rdi
0x18007271a  jz      short loc_180072721
0x18007271c  mov     eax, [rbp+arg_0]
0x18007271f  mov     [rdi], eax
0x180072721  test    rbx, rbx
0x180072724  jz      short loc_180072744
0x180072726  movups  xmm0, xmmword ptr [rbp+pvar]
0x18007272a  xor     eax, eax
0x18007272c  movsd   xmm1, [rbp+var_10]
0x180072731  movups  xmmword ptr [rbx], xmm0
0x180072734  mov     [rbp+var_10], rax
0x180072738  xorps   xmm0, xmm0
0x18007273b  movsd   qword ptr [rbx+10h], xmm1
0x180072740  movups  xmmword ptr [rbp+pvar], xmm0
0x180072744  call    cs:__imp_CoTaskMemFree
0x18007274a  lea     rcx, [rbp+pvar]; pvar
0x18007274e  call    cs:__imp_PropVariantClear
0x180072754  lea     r11, [rsp+50h+var_s0]
0x180072759  mov     eax, r14d
0x18007275c  mov     rbx, [r11+30h]
0x180072760  mov     rsi, [r11+38h]
0x180072764  mov     rsp, r11
0x180072767  pop     r14
0x180072769  pop     rdi
0x18007276a  pop     rbp
0x18007276b  retn
```
