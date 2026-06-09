# CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus(void)

- ea: `0x180032a30`
- end: `0x180032afe`
- name: `?CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus@@YAJXZ`
- size: `206`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012750`

## callees

- `0x180032a30`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180032a90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180032a90`

## pseudocode

```c
__int64 CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus(void)
{
  HRESULT v1; // eax
  unsigned int v2; // edi
  IUnknown *pItf; // rbx
  MULTI_QI pResults; // [rsp+30h] [rbp-28h] BYREF
  __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  if ( dword_1800C2CC0 )
    return 0;
  v5 = 0;
  pResults.pIID = &GUID_0000015b_0000_0000_c000_000000000046;
  *(_OWORD *)&pResults.pItf = 0;
  v1 = CoCreateInstanceEx(&CLSID_GlobalOptions, 0, 1u, 0, 1u, &pResults);
  v2 = v1;
  if ( v1 == -2147221008 )
  {
    dword_1800C2CC0 = 2;
    return 0;
  }
  if ( v1 >= 0 )
  {
    pItf = pResults.pItf;
    ((void (__fastcall *)(IUnknown *, __int64, __int64 *))pResults.pItf->lpVtbl[1].AddRef)(pResults.pItf, 4, &v5);
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    dword_1800C2CC0 = 2 - ((v5 & 0x100) != 0);
  }
  return v2;
}

```

## disassembly

```asm
0x180032a30  mov     [rsp+arg_8], rbx
0x180032a35  push    rdi
0x180032a36  sub     rsp, 50h
0x180032a3a  mov     eax, cs:dword_1800C2CC0
0x180032a40  test    eax, eax
0x180032a42  jz      short loc_180032A51
0x180032a44  xor     eax, eax
0x180032a46  mov     rbx, [rsp+58h+arg_8]
0x180032a4b  add     rsp, 50h
0x180032a4f  pop     rdi
0x180032a50  retn
0x180032a51  lea     rax, _GUID_0000015b_0000_0000_c000_000000000046
0x180032a58  mov     [rsp+58h+arg_0], 0
0x180032a61  mov     [rsp+58h+var_28.pIID], rax
0x180032a66  lea     rcx, CLSID_GlobalOptions; Clsid
0x180032a6d  lea     rax, [rsp+58h+var_28]
0x180032a72  xorps   xmm0, xmm0
0x180032a75  mov     r8d, 1; dwClsCtx
0x180032a7b  mov     [rsp+58h+pResults], rax; pResults
0x180032a80  xor     r9d, r9d; pServerInfo
0x180032a83  mov     [rsp+58h+dwCount], r8d; dwCount
0x180032a88  xor     edx, edx; punkOuter
0x180032a8a  movdqu  xmmword ptr [rsp+58h+var_28.pItf], xmm0
0x180032a90  call    cs:__imp_CoCreateInstanceEx
0x180032a96  mov     edi, eax
0x180032a98  cmp     eax, 800401F0h
0x180032a9d  jz      short loc_180032AEF
0x180032a9f  test    eax, eax
0x180032aa1  js      short loc_180032AE8
0x180032aa3  mov     rbx, [rsp+58h+var_28.pItf]
0x180032aa8  lea     r8, [rsp+58h+arg_0]
0x180032aad  mov     edx, 4
0x180032ab2  mov     rcx, rbx
0x180032ab5  mov     rax, [rbx]
0x180032ab8  mov     rax, [rax+20h]
0x180032abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ac1  mov     rax, [rbx]
0x180032ac4  mov     rcx, rbx
0x180032ac7  mov     rax, [rax+10h]
0x180032acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ad0  mov     rax, [rsp+58h+arg_0]
0x180032ad5  and     eax, 100h
0x180032ada  neg     rax
0x180032add  sbb     ecx, ecx
0x180032adf  add     ecx, 2
0x180032ae2  mov     cs:dword_1800C2CC0, ecx
0x180032ae8  mov     eax, edi
0x180032aea  jmp     loc_180032A46
0x180032aef  mov     cs:dword_1800C2CC0, 2
0x180032af9  jmp     loc_180032A44
```
