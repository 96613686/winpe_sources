# ConvertDIS11HierarchyOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001fa00`
- end: `0x18001fae8`
- name: `?ConvertDIS11HierarchyOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `232`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007990`

## callees

- `0x18000bbe8`
- `0x180017d8c`
- `0x18001ec94`
- `0x18001fa00`
- `0x180021fac`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fa9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertDIS11HierarchyOnRead(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  int v4; // ebx
  void **v6; // [rsp+20h] [rbp-39h] BYREF
  int v7; // [rsp+28h] [rbp-31h] BYREF
  __int128 v8; // [rsp+30h] [rbp-29h]
  __int128 v9; // [rsp+40h] [rbp-19h]
  __int64 v10; // [rsp+50h] [rbp-9h]
  char v11; // [rsp+58h] [rbp-1h]
  __int128 v12; // [rsp+60h] [rbp+7h]
  __int64 v13; // [rsp+70h] [rbp+17h]
  int v14; // [rsp+78h] [rbp+1Fh]
  __int128 v15; // [rsp+80h] [rbp+27h] BYREF
  __int64 v16; // [rsp+90h] [rbp+37h]
  int v17; // [rsp+98h] [rbp+3Fh]
  int v18; // [rsp+A0h] [rbp+47h]

  PropVariantClear(a2);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v6 = &ATL::CComObject<DIS11::DIS11Keywords>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  ATL::SafeIncrementReferenceMultiThread(&v7);
  if ( a1->vt == 31 )
  {
    PropVariantClear(a2);
    v4 = DIS11::DIS11Keywords::Parse((DIS11::DIS11Keywords *)&v6, a1->bstrVal);
    if ( v4 >= 0 )
      v4 = ConvertStringArrayToPropVariantVector((__int64)&v15, a2);
  }
  else
  {
    v4 = -2147024809;
  }
  ATL::CComObject<DIS11::DIS11Keywords>::~CComObject<DIS11::DIS11Keywords>((DIS11::DIS11Keywords *)&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001fa00  mov     [rsp-8+arg_0], rbx
0x18001fa05  mov     [rsp-8+arg_8], rdi
0x18001fa0a  push    rbp
0x18001fa0b  lea     rbp, [rsp-57h]
0x18001fa10  sub     rsp, 0B0h
0x18001fa17  mov     rdi, rdx
0x18001fa1a  mov     rbx, rcx
0x18001fa1d  mov     rcx, rdx; pvar
0x18001fa20  call    cs:__imp_PropVariantClear
0x18001fa27  nop     dword ptr [rax+rax+00h]
0x18001fa2c  mov     [rbp+57h+var_88], 0
0x18001fa33  xorps   xmm0, xmm0
0x18001fa36  xor     eax, eax
0x18001fa38  movups  [rbp+57h+var_80], xmm0
0x18001fa3c  movups  [rbp+57h+var_70], xmm0
0x18001fa40  mov     [rbp+57h+var_60], rax
0x18001fa44  mov     [rbp+57h+var_58], al
0x18001fa47  movdqa  [rbp+57h+var_50], xmm0
0x18001fa4c  mov     [rbp+57h+var_40], rax
0x18001fa50  mov     [rbp+57h+var_38], eax
0x18001fa53  movdqa  [rbp+57h+var_30], xmm0
0x18001fa58  mov     [rbp+57h+var_20], rax
0x18001fa5c  mov     [rbp+57h+var_18], eax
0x18001fa5f  mov     [rbp+57h+var_10], eax
0x18001fa62  lea     rax, ??_7?$CComObject@VDIS11Keywords@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::DIS11Keywords>::`vftable'
0x18001fa69  mov     [rbp+57h+var_90], rax
0x18001fa6d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001fa74  mov     rax, [rcx]
0x18001fa77  mov     rax, [rax+8]
0x18001fa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa80  nop
0x18001fa81  lea     rcx, [rbp+57h+var_88]; volatile int *
0x18001fa85  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18001fa8a  cmp     word ptr [rbx], 1Fh
0x18001fa8e  jz      short loc_18001FA97
0x18001fa90  mov     ebx, 80070057h
0x18001fa95  jmp     short loc_18001FAC7
0x18001fa97  mov     rcx, rdi; pvar
0x18001fa9a  call    cs:__imp_PropVariantClear
0x18001faa1  nop     dword ptr [rax+rax+00h]
0x18001faa6  mov     rdx, [rbx+8]; unsigned __int16 *
0x18001faaa  lea     rcx, [rbp+57h+var_90]; this
0x18001faae  call    ?Parse@DIS11Keywords@DIS11@@AEAAJPEBG@Z; DIS11::DIS11Keywords::Parse(ushort const *)
0x18001fab3  mov     ebx, eax
0x18001fab5  test    eax, eax
0x18001fab7  js      short loc_18001FAC7
0x18001fab9  mov     rdx, rdi
0x18001fabc  lea     rcx, [rbp+57h+var_30]
0x18001fac0  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18001fac5  mov     ebx, eax
0x18001fac7  lea     rcx, [rbp+57h+var_90]; this
0x18001facb  call    ??1?$CComObject@VDIS11Keywords@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::DIS11Keywords>::~CComObject<DIS11::DIS11Keywords>(void)
0x18001fad0  mov     eax, ebx
0x18001fad2  lea     r11, [rsp+0B0h+var_s0]
0x18001fada  mov     rbx, [r11+10h]
0x18001fade  mov     rdi, [r11+18h]
0x18001fae2  mov     rsp, r11
0x18001fae5  pop     rbp
0x18001fae6  retn
```
