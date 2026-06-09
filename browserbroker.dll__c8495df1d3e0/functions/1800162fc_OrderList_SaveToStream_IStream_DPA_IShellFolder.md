# OrderList_SaveToStream(IStream *,_DPA *,IShellFolder *)

- ea: `0x1800162fc`
- end: `0x180016421`
- name: `?OrderList_SaveToStream@@YAJPEAUIStream@@PEAU_DPA@@PEAUIShellFolder@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct IStream *pstream, HDPA hdpa, struct IShellFolder *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016fa8`

## callees

- `0x18001547c`
- `0x1800162fc`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_DPA_Clone` at `0x180016324`
- `iertutil!__imp_DPA_Clone` at `0x180016324`
- `iertutil!__imp_DPA_Destroy` at `0x180016406`
- `iertutil!__imp_DPA_Destroy` at `0x180016406`
- `iertutil!__imp_DPA_SaveStream` at `0x1800163d5`
- `iertutil!__imp_DPA_SaveStream` at `0x1800163d5`
- `iertutil!__imp_DPA_Sort` at `0x18001637b`
- `iertutil!__imp_DPA_Sort` at `0x18001637b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180016399`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180016399`

## pseudocode

```c
__int64 __fastcall OrderList_SaveToStream(struct IStream *pstream, HDPA hdpa, struct IShellFolder *a3)
{
  HRESULT v5; // edi
  struct _DPA *v6; // rsi
  struct IShellFolder *v7; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-30h] BYREF
  struct IShellFolder *v10; // [rsp+28h] [rbp-28h]
  void *pvInstData[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  int pv; // [rsp+88h] [rbp+38h] BYREF
  int v14; // [rsp+8Ch] [rbp+3Ch]

  v5 = -2147024882;
  v6 = DPA_Clone(hdpa, 0);
  if ( v6 )
  {
    lParam = 0;
    v12 = 0;
    v10 = a3;
    *(_OWORD *)pvInstData = 0;
    if ( a3 )
      ((void (__fastcall *)(struct IShellFolder *))a3->lpVtbl->AddRef)(a3);
    LODWORD(lParam) = 0;
    DPA_Sort(v6, OrderItem_Compare, (LPARAM)&lParam);
    v14 = 2;
    pv = 8;
    v5 = IStream_Write(pstream, &pv, 8u);
    if ( v5 >= 0 )
    {
      if ( a3 )
        ((void (__fastcall *)(struct IShellFolder *, GUID *, void **))v10->lpVtbl->QueryInterface)(
          v10,
          &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
          pvInstData);
      v5 = DPA_SaveStream(v6, OrderItem_SaveToStream, pstream, pvInstData[0]);
      IUnknown_SafeReleaseAndNullPtr<IShellFolder2>(pvInstData);
    }
    v7 = v10;
    if ( v10 )
    {
      v10 = 0;
      ((void (__fastcall *)(struct IShellFolder *))v7->lpVtbl->Release)(v7);
    }
    DPA_Destroy(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800162fc  mov     [rsp-18h+arg_0], rbx
0x180016301  mov     [rsp-18h+arg_8], rsi
0x180016306  push    rbp
0x180016307  push    rdi
0x180016308  push    r14
0x18001630a  mov     rbp, rsp
0x18001630d  sub     rsp, 50h
0x180016311  mov     rax, rdx
0x180016314  mov     r14, rcx
0x180016317  mov     rcx, rax; hdpa
0x18001631a  xor     edx, edx; hdpaNew
0x18001631c  mov     rbx, r8
0x18001631f  mov     edi, 8007000Eh
0x180016324  call    cs:__imp_DPA_Clone
0x18001632a  mov     rsi, rax
0x18001632d  test    rax, rax
0x180016330  jz      loc_18001640C
0x180016336  mov     [rbp+lParam], 0
0x18001633e  xorps   xmm0, xmm0
0x180016341  mov     [rbp+var_10], 0
0x180016349  mov     [rbp+var_28], rbx
0x18001634d  movdqu  xmmword ptr [rbp+pvInstData], xmm0
0x180016352  test    rbx, rbx
0x180016355  jz      short loc_180016366
0x180016357  mov     rax, [rbx]
0x18001635a  mov     rcx, rbx
0x18001635d  mov     rax, [rax+8]
0x180016361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016366  lea     r8, [rbp+lParam]; lParam
0x18001636a  mov     dword ptr [rbp+lParam], 0
0x180016371  lea     rdx, ?OrderItem_Compare@@YAHPEAX0_J@Z; pfnCompare
0x180016378  mov     rcx, rsi; hdpa
0x18001637b  call    cs:__imp_DPA_Sort
0x180016381  mov     r8d, 8; cb
0x180016387  mov     [rbp+arg_1C], 2
0x18001638e  lea     rdx, [rbp+pv]; pv
0x180016392  mov     [rbp+pv], r8d
0x180016396  mov     rcx, r14; pstm
0x180016399  call    cs:__imp_IStream_Write
0x18001639f  mov     edi, eax
0x1800163a1  test    eax, eax
0x1800163a3  js      short loc_1800163E6
0x1800163a5  test    rbx, rbx
0x1800163a8  jz      short loc_1800163C4
0x1800163aa  mov     rcx, [rbp+var_28]
0x1800163ae  lea     r8, [rbp+pvInstData]
0x1800163b2  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800163b9  mov     rax, [rcx]
0x1800163bc  mov     rax, [rax]
0x1800163bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c4  mov     r9, [rbp+pvInstData]; pvInstData
0x1800163c8  lea     rdx, ?OrderItem_SaveToStream@@YAJPEAU_DPASTREAMINFO@@PEAUIStream@@PEAX@Z; pfn
0x1800163cf  mov     r8, r14; pstream
0x1800163d2  mov     rcx, rsi; hdpa
0x1800163d5  call    cs:__imp_DPA_SaveStream
0x1800163db  lea     rcx, [rbp+pvInstData]
0x1800163df  mov     edi, eax
0x1800163e1  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellFolder2@@@@YAXAEAPEAUIShellFolder2@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellFolder2>(IShellFolder2 * &)
0x1800163e6  mov     rcx, [rbp+var_28]
0x1800163ea  test    rcx, rcx
0x1800163ed  jz      short loc_180016403
0x1800163ef  mov     [rbp+var_28], 0
0x1800163f7  mov     rax, [rcx]
0x1800163fa  mov     rax, [rax+10h]
0x1800163fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016403  mov     rcx, rsi; hdpa
0x180016406  call    cs:__imp_DPA_Destroy
0x18001640c  mov     rbx, [rsp+50h+arg_0]
0x180016411  mov     eax, edi
0x180016413  mov     rsi, [rsp+50h+arg_8]
0x180016418  add     rsp, 50h
0x18001641c  pop     r14
0x18001641e  pop     rdi
0x18001641f  pop     rbp
0x180016420  retn
```
