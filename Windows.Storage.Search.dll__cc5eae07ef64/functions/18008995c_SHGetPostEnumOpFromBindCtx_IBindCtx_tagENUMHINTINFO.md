# SHGetPostEnumOpFromBindCtx(IBindCtx *,tagENUMHINTINFO *)

- ea: `0x18008995c`
- end: `0x180089a59`
- name: `?SHGetPostEnumOpFromBindCtx@@YAJPEAUIBindCtx@@PEAUtagENUMHINTINFO@@@Z`
- size: `253`
- prototype: `int(struct IBindCtx *, struct tagENUMHINTINFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008b09c`

## callees

- `0x180006ca8`
- `0x180045fe0`
- `0x18008995c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180089a16`
- `SHCORE!IUnknown_Set` at `0x180089a24`
- `SHCORE!IUnknown_Set` at `0x180089a16`
- `SHCORE!IUnknown_Set` at `0x180089a24`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x1800899ca`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x1800899ee`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x1800899ca`
- `PROPSYS!PSPropertyBag_ReadUnknown` at `0x1800899ee`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180089a02`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180089a02`

## pseudocode

```c
__int64 __fastcall SHGetPostEnumOpFromBindCtx(struct IBindCtx *a1, struct tagENUMHINTINFO *a2)
{
  HRESULT ObjectFromBindCtx; // ebx
  IPropertyBag *propBag; // [rsp+58h] [rbp+38h] BYREF
  void *ppv; // [rsp+60h] [rbp+40h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp+48h] BYREF

  *(_DWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  propBag = 0;
  ObjectFromBindCtx = GetObjectFromBindCtx(
                        a1,
                        L"Post Enumeration Operation Hints",
                        &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                        (void **)&propBag);
  if ( ObjectFromBindCtx >= 0 )
  {
    ppv = 0;
    PSPropertyBag_ReadUnknown(propBag, L"Sort Columns", &GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54, &ppv);
    punk = 0;
    PSPropertyBag_ReadUnknown(propBag, L"Prop List", &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b, (void **)&punk);
    ObjectFromBindCtx = PSPropertyBag_ReadDWORD(propBag, L"Max Results", (DWORD *)a2);
    if ( ObjectFromBindCtx >= 0 )
    {
      IUnknown_Set((IUnknown **)a2 + 1, (IUnknown *)ppv);
      IUnknown_Set((IUnknown **)a2 + 2, punk);
    }
    SafeRelease<IShellItemArray>((__int64 *)&ppv);
    SafeRelease<IShellItemArray>((__int64 *)&punk);
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
  }
  return (unsigned int)ObjectFromBindCtx;
}

```

## disassembly

```asm
0x18008995c  push    rbp
0x18008995e  push    rbx
0x18008995f  push    rsi
0x180089960  push    rdi
0x180089961  push    r14
0x180089963  mov     rbp, rsp
0x180089966  sub     rsp, 20h
0x18008996a  mov     rdi, rdx
0x18008996d  mov     dword ptr [rdx], 0
0x180089973  mov     qword ptr [rdx+8], 0
0x18008997b  lea     r9, [rbp+propBag]; void **
0x18008997f  mov     qword ptr [rdx+10h], 0
0x180089987  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; struct _GUID *
0x18008998e  lea     rdx, aPostEnumeratio; "Post Enumeration Operation Hints"
0x180089995  mov     [rbp+propBag], 0
0x18008999d  call    ?GetObjectFromBindCtx@@YAJPEAUIBindCtx@@PEBGAEBU_GUID@@PEAPEAX@Z; GetObjectFromBindCtx(IBindCtx *,ushort const *,_GUID const &,void * *)
0x1800899a2  mov     ebx, eax
0x1800899a4  test    eax, eax
0x1800899a6  js      loc_180089A4C
0x1800899ac  mov     rcx, [rbp+propBag]; propBag
0x1800899b0  lea     r9, [rbp+ppv]; ppv
0x1800899b4  lea     r8, _GUID_6dfc60fb_f2e9_459b_beb5_288f1a7c7d54; riid
0x1800899bb  mov     [rbp+ppv], 0
0x1800899c3  lea     rdx, aSortColumns; "Sort Columns"
0x1800899ca  call    cs:__imp_PSPropertyBag_ReadUnknown
0x1800899d0  mov     rcx, [rbp+propBag]; propBag
0x1800899d4  lea     r9, [rbp+punk]; ppv
0x1800899d8  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b; riid
0x1800899df  mov     [rbp+punk], 0
0x1800899e7  lea     rdx, aPropList; "Prop List"
0x1800899ee  call    cs:__imp_PSPropertyBag_ReadUnknown
0x1800899f4  mov     rcx, [rbp+propBag]; propBag
0x1800899f8  lea     rdx, aMaxResults; "Max Results"
0x1800899ff  mov     r8, rdi; value
0x180089a02  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180089a08  mov     ebx, eax
0x180089a0a  test    eax, eax
0x180089a0c  js      short loc_180089A2A
0x180089a0e  mov     rdx, [rbp+ppv]; punk
0x180089a12  lea     rcx, [rdi+8]; ppunk
0x180089a16  call    cs:__imp_IUnknown_Set
0x180089a1c  mov     rdx, [rbp+punk]; punk
0x180089a20  lea     rcx, [rdi+10h]; ppunk
0x180089a24  call    cs:__imp_IUnknown_Set
0x180089a2a  lea     rcx, [rbp+ppv]
0x180089a2e  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180089a33  lea     rcx, [rbp+punk]
0x180089a37  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180089a3c  mov     rcx, [rbp+propBag]
0x180089a40  mov     rax, [rcx]
0x180089a43  mov     rax, [rax+10h]
0x180089a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a4c  mov     eax, ebx
0x180089a4e  add     rsp, 20h
0x180089a52  pop     r14
0x180089a54  pop     rdi
0x180089a55  pop     rsi
0x180089a56  pop     rbx
0x180089a57  pop     rbp
0x180089a58  retn
```
