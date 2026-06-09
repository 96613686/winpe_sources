# CMapiSupport::GetProviderRule(ATL::CRegKey &,CMapiSupport::ProviderRuleT &)

- ea: `0x1800318c4`
- end: `0x180031bd6`
- name: `?GetProviderRule@CMapiSupport@@CAJAEAVCRegKey@ATL@@AEAUProviderRuleT@1@@Z`
- size: `786`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *this, struct CMapiSupport::ProviderRuleT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180031594`

## callees

- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x1800255fc`
- `0x180030bb8`
- `0x1800318c4`

## string_xrefs

- `0x180031950`: `DllVersionMax`
- `0x1800319bb`: `DllVersionMin`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiSupport::GetProviderRule(struct ATL::CRegKey *this, struct CMapiSupport::ProviderRuleT *a2)
{
  _QWORD *v4; // r13
  _QWORD *v5; // r15
  _QWORD *v6; // r12
  __int64 v7; // rdx
  volatile signed __int32 *v8; // rcx
  int *v9; // r14
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rcx
  int *v13; // r14
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rcx
  int *v17; // r14
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rdx
  volatile signed __int32 *v20; // rcx
  int *v21; // r14
  volatile signed __int32 *v22; // rbx
  __int64 v23; // rdx
  volatile signed __int32 *v24; // rcx
  int *v25; // r14
  volatile signed __int32 *v26; // rbx
  unsigned int v28; // [rsp+68h] [rbp+48h] BYREF
  __int64 v29; // [rsp+70h] [rbp+50h] BYREF

  v4 = (_QWORD *)((char *)a2 + 24);
  ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 24, &dword_1800444C4, 0);
  v5 = (_QWORD *)((char *)a2 + 16);
  ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 16, &dword_1800444C4, 0);
  ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 40, &dword_1800444C4, 0);
  *((_DWORD *)a2 + 12) = 0;
  v6 = (_QWORD *)((char *)a2 + 8);
  ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 8, &dword_1800444C4, 0);
  ATL::CSimpleStringT<wchar_t,0>::SetString(a2, &dword_1800444C4, 0);
  *((_DWORD *)a2 + 8) = 1;
  *((_DWORD *)a2 + 13) = 0;
  v7 = *(_QWORD *)CMapiSupport::GetCStringRegEntry(&v29, this, L"DllVersionMax");
  v8 = (volatile signed __int32 *)(v7 - 24);
  v9 = (int *)(*v4 - 24LL);
  if ( (int *)(v7 - 24) != v9 )
  {
    if ( v9[4] >= 0 && *(_QWORD *)v8 == *(_QWORD *)v9 )
    {
      v10 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v8);
      ATL::CStringData::Release((ATL::CStringData *)v9);
      *v4 = v10 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(v4, v7, *(unsigned int *)(v7 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  v11 = *(_QWORD *)CMapiSupport::GetCStringRegEntry(&v29, this, L"DllVersionMin");
  v12 = (volatile signed __int32 *)(v11 - 24);
  v13 = (int *)(*v5 - 24LL);
  if ( (int *)(v11 - 24) != v13 )
  {
    if ( v13[4] >= 0 && *(_QWORD *)v12 == *(_QWORD *)v13 )
    {
      v14 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v12);
      ATL::CStringData::Release((ATL::CStringData *)v13);
      *v5 = v14 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 16, v11, *(unsigned int *)(v11 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  v15 = *(_QWORD *)CMapiSupport::GetCStringRegEntry(&v29, this, L"OutlookVersionMax");
  v16 = (volatile signed __int32 *)(v15 - 24);
  v17 = (int *)(*v6 - 24LL);
  if ( (int *)(v15 - 24) != v17 )
  {
    if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
    {
      v18 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v16);
      ATL::CStringData::Release((ATL::CStringData *)v17);
      *v6 = v18 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 8, v15, *(unsigned int *)(v15 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  v19 = *(_QWORD *)CMapiSupport::GetCStringRegEntry(&v29, this, L"OutlookVersionMin");
  v20 = (volatile signed __int32 *)(v19 - 24);
  v21 = (int *)(*(_QWORD *)a2 - 24LL);
  if ( (int *)(v19 - 24) != v21 )
  {
    if ( v21[4] >= 0 && *(_QWORD *)v20 == *(_QWORD *)v21 )
    {
      v22 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v20);
      ATL::CStringData::Release((ATL::CStringData *)v21);
      *(_QWORD *)a2 = v22 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(a2, v19, *(unsigned int *)(v19 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  v23 = *(_QWORD *)CMapiSupport::GetCStringRegEntry(&v29, this, L"Message");
  v24 = (volatile signed __int32 *)(v23 - 24);
  v25 = (int *)(*((_QWORD *)a2 + 5) - 24LL);
  if ( (int *)(v23 - 24) != v25 )
  {
    if ( v25[4] >= 0 && *(_QWORD *)v24 == *(_QWORD *)v25 )
    {
      v26 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v24);
      ATL::CStringData::Release((ATL::CStringData *)v25);
      *((_QWORD *)a2 + 5) = v26 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString((char *)a2 + 40, v23, *(unsigned int *)(v23 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  v28 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue(this, L"TrustLevel", &v28) )
    *((_DWORD *)a2 + 8) = v28;
  if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue(this, L"UsePstProvider", &v28) )
    *((_DWORD *)a2 + 13) = v28;
  if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue(this, L"Notify", &v28) )
    *((_DWORD *)a2 + 12) = v28;
  return 0;
}

```

## disassembly

```asm
0x1800318c4  mov     [rsp-38h+arg_0], rbx
0x1800318c9  push    rbp
0x1800318ca  push    rsi
0x1800318cb  push    rdi
0x1800318cc  push    r12
0x1800318ce  push    r13
0x1800318d0  push    r14
0x1800318d2  push    r15
0x1800318d4  mov     rbp, rsp
0x1800318d7  sub     rsp, 20h
0x1800318db  mov     rdi, rdx
0x1800318de  mov     rsi, rcx
0x1800318e1  lea     r13, [rdx+18h]
0x1800318e5  xor     r8d, r8d
0x1800318e8  lea     rbx, dword_1800444C4
0x1800318ef  mov     rdx, rbx
0x1800318f2  mov     rcx, r13
0x1800318f5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800318fa  lea     r15, [rdi+10h]
0x1800318fe  xor     r8d, r8d
0x180031901  mov     rdx, rbx
0x180031904  mov     rcx, r15
0x180031907  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003190c  lea     rcx, [rdi+28h]
0x180031910  xor     r8d, r8d
0x180031913  mov     rdx, rbx
0x180031916  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003191b  mov     dword ptr [rdi+30h], 0
0x180031922  lea     r12, [rdi+8]
0x180031926  xor     r8d, r8d
0x180031929  mov     rdx, rbx
0x18003192c  mov     rcx, r12
0x18003192f  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031934  xor     r8d, r8d
0x180031937  mov     rdx, rbx
0x18003193a  mov     rcx, rdi
0x18003193d  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031942  mov     dword ptr [rdi+20h], 1
0x180031949  mov     dword ptr [rdi+34h], 0
0x180031950  lea     r8, aDllversionmax; "DllVersionMax"
0x180031957  mov     rdx, rsi
0x18003195a  lea     rcx, [rbp+arg_10]
0x18003195e  call    ?GetCStringRegEntry@CMapiSupport@@CA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@PEB_W@Z; CMapiSupport::GetCStringRegEntry(ATL::CRegKey &,wchar_t const *)
0x180031963  nop
0x180031964  mov     rdx, [rax]
0x180031967  lea     rcx, [rdx-18h]
0x18003196b  mov     r14, [r13+0]
0x18003196f  add     r14, 0FFFFFFFFFFFFFFE8h
0x180031973  cmp     rcx, r14
0x180031976  jz      short loc_1800319AE
0x180031978  cmp     dword ptr [r14+10h], 0
0x18003197d  jl      short loc_1800319A1
0x18003197f  mov     rax, [r14]
0x180031982  cmp     [rcx], rax
0x180031985  jnz     short loc_1800319A1
0x180031987  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18003198c  mov     rbx, rax
0x18003198f  mov     rcx, r14; this
0x180031992  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031997  lea     rax, [rbx+18h]
0x18003199b  mov     [r13+0], rax
0x18003199f  jmp     short loc_1800319AE
0x1800319a1  mov     r8d, [rdx-10h]
0x1800319a5  mov     rcx, r13
0x1800319a8  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800319ad  nop
0x1800319ae  mov     rcx, [rbp+arg_10]
0x1800319b2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800319b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800319bb  lea     r8, aDllversionmin; "DllVersionMin"
0x1800319c2  mov     rdx, rsi
0x1800319c5  lea     rcx, [rbp+arg_10]
0x1800319c9  call    ?GetCStringRegEntry@CMapiSupport@@CA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@PEB_W@Z; CMapiSupport::GetCStringRegEntry(ATL::CRegKey &,wchar_t const *)
0x1800319ce  nop
0x1800319cf  mov     rdx, [rax]
0x1800319d2  lea     rcx, [rdx-18h]
0x1800319d6  mov     r14, [r15]
0x1800319d9  add     r14, 0FFFFFFFFFFFFFFE8h
0x1800319dd  xor     r13d, r13d
0x1800319e0  cmp     rcx, r14
0x1800319e3  jz      short loc_180031A19
0x1800319e5  cmp     [r14+10h], r13d
0x1800319e9  jl      short loc_180031A0C
0x1800319eb  mov     rax, [r14]
0x1800319ee  cmp     [rcx], rax
0x1800319f1  jnz     short loc_180031A0C
0x1800319f3  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x1800319f8  mov     rbx, rax
0x1800319fb  mov     rcx, r14; this
0x1800319fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a03  lea     rax, [rbx+18h]
0x180031a07  mov     [r15], rax
0x180031a0a  jmp     short loc_180031A19
0x180031a0c  mov     r8d, [rdx-10h]
0x180031a10  mov     rcx, r15
0x180031a13  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031a18  nop
0x180031a19  mov     rcx, [rbp+arg_10]
0x180031a1d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031a21  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a26  lea     r8, aOutlookversion_0; "OutlookVersionMax"
0x180031a2d  mov     rdx, rsi
0x180031a30  lea     rcx, [rbp+arg_10]
0x180031a34  call    ?GetCStringRegEntry@CMapiSupport@@CA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@PEB_W@Z; CMapiSupport::GetCStringRegEntry(ATL::CRegKey &,wchar_t const *)
0x180031a39  nop
0x180031a3a  mov     rdx, [rax]
0x180031a3d  lea     rcx, [rdx-18h]
0x180031a41  mov     r14, [r12]
0x180031a45  add     r14, 0FFFFFFFFFFFFFFE8h
0x180031a49  cmp     rcx, r14
0x180031a4c  jz      short loc_180031A83
0x180031a4e  cmp     [r14+10h], r13d
0x180031a52  jl      short loc_180031A76
0x180031a54  mov     rax, [r14]
0x180031a57  cmp     [rcx], rax
0x180031a5a  jnz     short loc_180031A76
0x180031a5c  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180031a61  mov     rbx, rax
0x180031a64  mov     rcx, r14; this
0x180031a67  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a6c  lea     rax, [rbx+18h]
0x180031a70  mov     [r12], rax
0x180031a74  jmp     short loc_180031A83
0x180031a76  mov     r8d, [rdx-10h]
0x180031a7a  mov     rcx, r12
0x180031a7d  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031a82  nop
0x180031a83  mov     rcx, [rbp+arg_10]
0x180031a87  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031a8b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a90  lea     r8, aOutlookversion; "OutlookVersionMin"
0x180031a97  mov     rdx, rsi
0x180031a9a  lea     rcx, [rbp+arg_10]
0x180031a9e  call    ?GetCStringRegEntry@CMapiSupport@@CA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@PEB_W@Z; CMapiSupport::GetCStringRegEntry(ATL::CRegKey &,wchar_t const *)
0x180031aa3  nop
0x180031aa4  mov     rdx, [rax]
0x180031aa7  lea     rcx, [rdx-18h]
0x180031aab  mov     r14, [rdi]
0x180031aae  add     r14, 0FFFFFFFFFFFFFFE8h
0x180031ab2  cmp     rcx, r14
0x180031ab5  jz      short loc_180031AEB
0x180031ab7  cmp     [r14+10h], r13d
0x180031abb  jl      short loc_180031ADE
0x180031abd  mov     rax, [r14]
0x180031ac0  cmp     [rcx], rax
0x180031ac3  jnz     short loc_180031ADE
0x180031ac5  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180031aca  mov     rbx, rax
0x180031acd  mov     rcx, r14; this
0x180031ad0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031ad5  lea     rax, [rbx+18h]
0x180031ad9  mov     [rdi], rax
0x180031adc  jmp     short loc_180031AEB
0x180031ade  mov     r8d, [rdx-10h]
0x180031ae2  mov     rcx, rdi
0x180031ae5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031aea  nop
0x180031aeb  mov     rcx, [rbp+arg_10]
0x180031aef  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031af3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031af8  lea     r8, aMessage; "Message"
0x180031aff  mov     rdx, rsi
0x180031b02  lea     rcx, [rbp+arg_10]
0x180031b06  call    ?GetCStringRegEntry@CMapiSupport@@CA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@PEB_W@Z; CMapiSupport::GetCStringRegEntry(ATL::CRegKey &,wchar_t const *)
0x180031b0b  nop
0x180031b0c  mov     rdx, [rax]
0x180031b0f  lea     rcx, [rdx-18h]
0x180031b13  lea     r15, [rdi+28h]
0x180031b17  mov     r14, [r15]
0x180031b1a  add     r14, 0FFFFFFFFFFFFFFE8h
0x180031b1e  cmp     rcx, r14
0x180031b21  jz      short loc_180031B57
0x180031b23  cmp     [r14+10h], r13d
0x180031b27  jl      short loc_180031B4A
0x180031b29  mov     rax, [r14]
0x180031b2c  cmp     [rcx], rax
0x180031b2f  jnz     short loc_180031B4A
0x180031b31  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180031b36  mov     rbx, rax
0x180031b39  mov     rcx, r14; this
0x180031b3c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031b41  lea     rax, [rbx+18h]
0x180031b45  mov     [r15], rax
0x180031b48  jmp     short loc_180031B57
0x180031b4a  mov     r8d, [rdx-10h]
0x180031b4e  mov     rcx, r15
0x180031b51  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031b56  nop
0x180031b57  mov     rcx, [rbp+arg_10]
0x180031b5b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031b5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031b64  mov     [rbp+arg_8], r13d
0x180031b68  lea     r8, [rbp+arg_8]; unsigned int *
0x180031b6c  lea     rdx, aTrustlevel; "TrustLevel"
0x180031b73  mov     rcx, rsi; this
0x180031b76  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEB_WAEAK@Z; ATL::CRegKey::QueryDWORDValue(wchar_t const *,ulong &)
0x180031b7b  test    eax, eax
0x180031b7d  jnz     short loc_180031B85
0x180031b7f  mov     eax, [rbp+arg_8]
0x180031b82  mov     [rdi+20h], eax
0x180031b85  lea     r8, [rbp+arg_8]; unsigned int *
0x180031b89  lea     rdx, aUsepstprovider; "UsePstProvider"
0x180031b90  mov     rcx, rsi; this
0x180031b93  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEB_WAEAK@Z; ATL::CRegKey::QueryDWORDValue(wchar_t const *,ulong &)
0x180031b98  test    eax, eax
0x180031b9a  jnz     short loc_180031BA2
0x180031b9c  mov     eax, [rbp+arg_8]
0x180031b9f  mov     [rdi+34h], eax
0x180031ba2  lea     r8, [rbp+arg_8]; unsigned int *
0x180031ba6  lea     rdx, aNotify; "Notify"
0x180031bad  mov     rcx, rsi; this
0x180031bb0  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEB_WAEAK@Z; ATL::CRegKey::QueryDWORDValue(wchar_t const *,ulong &)
0x180031bb5  test    eax, eax
0x180031bb7  jnz     short loc_180031BBF
0x180031bb9  mov     eax, [rbp+arg_8]
0x180031bbc  mov     [rdi+30h], eax
0x180031bbf  xor     eax, eax
0x180031bc1  mov     rbx, [rsp+20h+arg_0]
0x180031bc6  add     rsp, 20h
0x180031bca  pop     r15
0x180031bcc  pop     r14
0x180031bce  pop     r13
0x180031bd0  pop     r12
0x180031bd2  pop     rdi
0x180031bd3  pop     rsi
0x180031bd4  pop     rbp
0x180031bd5  retn
```
