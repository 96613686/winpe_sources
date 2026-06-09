# ConvertDIS11HierarchyOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18001eb74`
- end: `0x18001ec4f`
- name: `?ConvertDIS11HierarchyOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `219`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006720`

## callees

- `0x18000b684`
- `0x180017308`
- `0x18001de80`
- `0x18001eb74`
- `0x180020f20`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eb94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eb94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ec08`

## pseudocode

```c
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
0x18001eb74  mov     [rsp-8+arg_0], rbx
0x18001eb79  mov     [rsp-8+arg_8], rdi
0x18001eb7e  push    rbp
0x18001eb7f  lea     rbp, [rsp-57h]
0x18001eb84  sub     rsp, 0B0h
0x18001eb8b  mov     rdi, rdx
0x18001eb8e  mov     rbx, rcx
0x18001eb91  mov     rcx, rdx; pvar
0x18001eb94  call    cs:__imp_PropVariantClear
0x18001eb9a  mov     [rbp+57h+var_88], 0
0x18001eba1  xorps   xmm0, xmm0
0x18001eba4  xor     eax, eax
0x18001eba6  movups  [rbp+57h+var_80], xmm0
0x18001ebaa  movups  [rbp+57h+var_70], xmm0
0x18001ebae  mov     [rbp+57h+var_60], rax
0x18001ebb2  mov     [rbp+57h+var_58], al
0x18001ebb5  movdqa  [rbp+57h+var_50], xmm0
0x18001ebba  mov     [rbp+57h+var_40], rax
0x18001ebbe  mov     [rbp+57h+var_38], eax
0x18001ebc1  movdqa  [rbp+57h+var_30], xmm0
0x18001ebc6  mov     [rbp+57h+var_20], rax
0x18001ebca  mov     [rbp+57h+var_18], eax
0x18001ebcd  mov     [rbp+57h+var_10], eax
0x18001ebd0  lea     rax, ??_7?$CComObject@VDIS11Keywords@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::DIS11Keywords>::`vftable'
0x18001ebd7  mov     [rbp+57h+var_90], rax
0x18001ebdb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ebe2  mov     rax, [rcx]
0x18001ebe5  mov     rax, [rax+8]
0x18001ebe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebee  nop
0x18001ebef  lea     rcx, [rbp+57h+var_88]; volatile int *
0x18001ebf3  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18001ebf8  cmp     word ptr [rbx], 1Fh
0x18001ebfc  jz      short loc_18001EC05
0x18001ebfe  mov     ebx, 80070057h
0x18001ec03  jmp     short loc_18001EC2F
0x18001ec05  mov     rcx, rdi; pvar
0x18001ec08  call    cs:__imp_PropVariantClear
0x18001ec0e  mov     rdx, [rbx+8]; unsigned __int16 *
0x18001ec12  lea     rcx, [rbp+57h+var_90]; this
0x18001ec16  call    ?Parse@DIS11Keywords@DIS11@@AEAAJPEBG@Z; DIS11::DIS11Keywords::Parse(ushort const *)
0x18001ec1b  mov     ebx, eax
0x18001ec1d  test    eax, eax
0x18001ec1f  js      short loc_18001EC2F
0x18001ec21  mov     rdx, rdi
0x18001ec24  lea     rcx, [rbp+57h+var_30]
0x18001ec28  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18001ec2d  mov     ebx, eax
0x18001ec2f  lea     rcx, [rbp+57h+var_90]; this
0x18001ec33  call    ??1?$CComObject@VDIS11Keywords@DIS11@@@ATL@@UEAA@XZ; ATL::CComObject<DIS11::DIS11Keywords>::~CComObject<DIS11::DIS11Keywords>(void)
0x18001ec38  mov     eax, ebx
0x18001ec3a  lea     r11, [rsp+0B0h+var_s0]
0x18001ec42  mov     rbx, [r11+10h]
0x18001ec46  mov     rdi, [r11+18h]
0x18001ec4a  mov     rsp, r11
0x18001ec4d  pop     rbp
0x18001ec4e  retn
```
