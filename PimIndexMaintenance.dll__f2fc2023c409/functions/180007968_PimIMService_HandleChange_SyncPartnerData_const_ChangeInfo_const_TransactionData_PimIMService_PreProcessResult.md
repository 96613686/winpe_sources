# PimIMService::HandleChange(SyncPartnerData const &,ChangeInfo const &,TransactionData *,PimIMService::PreProcessResult &)

- ea: `0x180007968`
- end: `0x180008057`
- name: `?HandleChange@PimIMService@@AEAAJAEBUSyncPartnerData@@AEBUChangeInfo@@PEAUTransactionData@@AEAW4PreProcessResult@1@@Z`
- size: `1775`
- prototype: `__int64 __fastcall(MetadataUpdates **this, const struct SyncPartnerData *, const struct ChangeInfo *, struct TransactionData *, enum PimIMService::PreProcessResult *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000936c`

## callees

- `0x180002da8`
- `0x180003710`
- `0x180003900`
- `0x180003b04`
- `0x180003d38`
- `0x180003db0`
- `0x180003f90`
- `0x18000428c`
- `0x180004820`
- `0x18000502c`
- `0x180005e1c`
- `0x18000759c`
- `0x180007968`
- `0x1800086a0`
- `0x18000a15c`
- `0x18000c548`
- `0x18000c58c`
- `0x18000d63c`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180007b16`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180007b16`

## string_xrefs

- `0x1800079b0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800079c7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800079e4`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007ab8`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007b2b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007bcb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007c92`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007ce2`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007dd9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007e9a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007f18`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007f3b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180007fda`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::HandleChange(
        MetadataUpdates **this,
        const struct SyncPartnerData *a2,
        const struct ChangeInfo *a3,
        struct TransactionData *a4,
        enum PimIMService::PreProcessResult *a5)
{
  int v5; // r12d
  int v10; // eax
  PimIMService *v11; // rcx
  unsigned int v12; // ebx
  int v14; // eax
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rdx
  MetadataUpdates *v18; // rax
  __int64 (__fastcall *v19)(PimIMService *, __int64, void **, int *, enum PimIMService::PreProcessResult *); // rax
  __int128 v20; // xmm0
  int v21; // eax
  int v22; // eax
  MetadataUpdates *v23; // rax
  __int64 (__fastcall *v24)(PimIMService *, void **, int *, __int64 *, _BYTE *, unsigned int *, __int64 *); // rax
  int v25; // eax
  int v26; // esi
  MetadataUpdates *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rbx
  int MetadataUpdates; // eax
  MetadataUpdates *v31; // rcx
  __int64 v32; // r8
  char *v33; // rdi
  _OWORD *v34; // r15
  _OWORD *v35; // rdi
  __int64 v36; // r9
  unsigned int *v37; // rcx
  unsigned __int64 v38; // r15
  unsigned __int64 v39; // rdi
  MetadataUpdates *v40; // rax
  MetadataUpdates *v41; // rcx
  __int64 v42; // rdx
  _BYTE v43[16]; // [rsp+40h] [rbp-C0h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v45; // [rsp+60h] [rbp-A0h]
  unsigned int v46; // [rsp+70h] [rbp-90h] BYREF
  int v47; // [rsp+74h] [rbp-8Ch] BYREF
  struct IUnknown *v48; // [rsp+78h] [rbp-88h] BYREF
  __int128 v49; // [rsp+80h] [rbp-80h] BYREF
  _OWORD *v50; // [rsp+90h] [rbp-70h]
  _BYTE v51[24]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  int v53; // [rsp+C8h] [rbp-38h]
  __int64 v54; // [rsp+D0h] [rbp-30h] BYREF
  int v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+E0h] [rbp-20h]
  void *v57; // [rsp+E4h] [rbp-1Ch]
  int v58; // [rsp+ECh] [rbp-14h]
  int v59; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v60; // [rsp+F4h] [rbp-Ch]
  _BYTE v61[20]; // [rsp+104h] [rbp+4h]
  int v62; // [rsp+120h] [rbp+20h] BYREF
  void *v63; // [rsp+124h] [rbp+24h]
  int v64; // [rsp+12Ch] [rbp+2Ch]
  int v65; // [rsp+130h] [rbp+30h]
  __int128 v66; // [rsp+134h] [rbp+34h]
  __int128 v67; // [rsp+144h] [rbp+44h]
  int v68; // [rsp+154h] [rbp+54h]
  struct IUnknown *v69; // [rsp+158h] [rbp+58h] BYREF

  v5 = 0;
  if ( !*(_QWORD *)a2 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2065);
  if ( !a4 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2066);
  v10 = FailOnServiceShutdown((__int64)this, (__int64)a2, (__int64)a3);
  v12 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2068);
    return v12;
  }
  LODWORD(Block[0]) = 0;
  v50 = 0;
  v48 = 0;
  v49 = 0;
  v14 = PimIMService::ShouldHandleChange(
          v11,
          a2,
          a3,
          (struct IPOItemMetadata **)&v48,
          (struct _SQLCEPROPVAL *)&v49,
          (int *)Block);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 2081;
LABEL_13:
    Log_HREvent(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v15);
LABEL_85:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
    return v12;
  }
  if ( LODWORD(Block[0]) )
    goto LABEL_86;
  v16 = *((_DWORD *)a3 + 2);
  v17 = *((unsigned int *)a3 + 3);
  v57 = *(void **)a3;
  v58 = v16;
  LODWORD(Block[1]) = v16;
  v18 = *this;
  *(_OWORD *)v61 = 0;
  v56 = v17;
  v60 = 0;
  v19 = (__int64 (__fastcall *)(PimIMService *, __int64, void **, int *, enum PimIMService::PreProcessResult *))*((_QWORD *)v18 + 27);
  v20 = *((_OWORD *)a3 + 1);
  v59 = 0;
  Block[0] = v57;
  *(_OWORD *)&v61[4] = v20;
  v14 = v19((PimIMService *)this, v17, Block, &v59, a5);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 2095;
    goto LABEL_13;
  }
  if ( *(_DWORD *)a5 == 1 )
  {
LABEL_86:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
    return 0;
  }
  v21 = *((_DWORD *)a3 + 2);
  *(_QWORD *)v51 = *(_QWORD *)a3;
  v43[0] = 0;
  Block[0] = 0;
  *(_DWORD *)&v51[8] = v21;
  if ( PimIMService::GetWobTicket((__int64)this, v51, Block) )
  {
    v22 = RtlSetThreadWorkOnBehalfTicket(Block);
    if ( v22 < 0 )
      Log_HREvent(
        v22 | 0x10000000u,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        107);
    else
      v43[0] = 1;
  }
  v54 = 0;
  v55 = 0;
  v52 = 0;
  v53 = 0;
  *(_DWORD *)v51 = v59;
  *(_DWORD *)&v51[20] = *(_DWORD *)v61;
  v23 = *this;
  *(_OWORD *)&v51[4] = v60;
  v24 = (__int64 (__fastcall *)(PimIMService *, void **, int *, __int64 *, _BYTE *, unsigned int *, __int64 *))*((_QWORD *)v23 + 22);
  v47 = 0;
  v46 = 0;
  *(_OWORD *)Block = v49;
  v45 = v50;
  v25 = v24((PimIMService *)this, Block, &v47, &v54, v51, &v46, &v52);
  v26 = v25;
  if ( v25 < 0 )
  {
    Log_HREvent(
      (unsigned int)v25,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2124);
LABEL_21:
    AutoWobTicket::~AutoWobTicket((AutoWobTicket *)v43);
    v12 = v26;
    goto LABEL_85;
  }
  v62 = v56;
  v64 = v58;
  v63 = v57;
  v65 = v59;
  v68 = *(_DWORD *)&v61[16];
  v69 = 0;
  v67 = *(_OWORD *)v61;
  v66 = v60;
  if ( v48 )
    ATL::AtlComPtrAssign(&v69, v48);
  v27 = 0;
  Block[0] = 0;
  if ( !*((_DWORD *)a4 + 6) )
  {
    utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v51);
    v29 = *(_QWORD *)&v51[8];
    if ( *(_QWORD *)&v51[8] == *(_QWORD *)&v51[16]
      || !utl::allocator_traits<utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::construct<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
            v28,
            *(__int64 *)&v51[8],
            (__int64)&v62) )
    {
      if ( !utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_PushBackOne2<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
              (__int64 *)v51,
              (__int64)&v62) )
      {
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          2137);
        utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit((__int64)v51);
LABEL_84:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v69);
        AutoWobTicket::~AutoWobTicket((AutoWobTicket *)v43);
        v12 = -2147024882;
        goto LABEL_85;
      }
    }
    else
    {
      *(_QWORD *)&v51[8] = v29 + 64;
    }
    MetadataUpdates = MetadataUpdates::CreateMetadataUpdates((__int64)a2, v51, (MetadataUpdates **)Block);
    v26 = MetadataUpdates;
    if ( MetadataUpdates < 0 )
    {
      Log_HREvent(
        (unsigned int)MetadataUpdates,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2140);
      utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit((__int64)v51);
      v31 = (MetadataUpdates *)Block[0];
      if ( Block[0] )
LABEL_30:
        tlx::_delete<MetadataUpdates>(v31);
LABEL_31:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v69);
      goto LABEL_21;
    }
    utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit((__int64)v51);
    v27 = (MetadataUpdates *)Block[0];
  }
  utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(Block);
  if ( v47 )
  {
    v33 = (char *)Block[1];
    v34 = v45;
    *(_DWORD *)v51 = v47;
    *(_QWORD *)&v51[4] = v54;
    *(_DWORD *)&v51[12] = v55;
    if ( Block[1] == v45 )
    {
      if ( !(unsigned __int8)utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_PushBackOne2__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_const___(
                               Block,
                               v51) )
      {
        v36 = 2153;
        goto LABEL_82;
      }
      v34 = v45;
      v35 = Block[1];
    }
    else
    {
      *(_OWORD *)Block[1] = *(_OWORD *)v51;
      v35 = v33 + 16;
      Block[1] = v35;
    }
    if ( !v46 )
      goto LABEL_56;
    *(_QWORD *)&v51[4] = v52;
    *(_DWORD *)v51 = v46;
    *(_DWORD *)&v51[12] = v53;
    if ( v46 == 2 )
    {
      if ( !utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_InsertManyFillFn__lambda_c6ca038e7522b204bcd33104569c2333___(
              Block,
              Block[0],
              v32,
              v51) )
      {
        v36 = 2186;
        goto LABEL_82;
      }
      goto LABEL_55;
    }
    if ( v46 != 1 )
      Log_AssertionEvent(
        v46,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2191);
    if ( v35 == v34 )
    {
      if ( !(unsigned __int8)utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_PushBackOne2__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_const___(
                               Block,
                               v51) )
      {
        v36 = 2194;
        goto LABEL_82;
      }
      goto LABEL_55;
    }
LABEL_52:
    *v35++ = *(_OWORD *)v51;
    Block[1] = v35;
    goto LABEL_56;
  }
  if ( !v46 )
    goto LABEL_55;
  v35 = Block[1];
  *(_DWORD *)v51 = v46;
  *(_QWORD *)&v51[4] = v52;
  *(_DWORD *)&v51[12] = v53;
  if ( Block[1] != v45 )
    goto LABEL_52;
  if ( !(unsigned __int8)utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_PushBackOne2__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_const___(
                           Block,
                           v51) )
  {
    v36 = 2201;
LABEL_82:
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v36);
    utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_Uninit(Block);
    if ( v27 )
      tlx::_delete<MetadataUpdates>(v27);
    goto LABEL_84;
  }
LABEL_55:
  v35 = Block[1];
LABEL_56:
  v37 = (unsigned int *)Block[0];
  v38 = 0;
  v39 = ((char *)v35 - (char *)Block[0]) >> 4;
  while ( v38 < v39 )
  {
    if ( v38 == v39 - 1 )
    {
      v5 = 1;
      if ( this[36] )
      {
        Log_AssertionEvent(
          v37,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          2212);
        v37 = (unsigned int *)Block[0];
      }
      v40 = this[36];
      this[36] = v27;
      v27 = v40;
    }
    v26 = (*((__int64 (__fastcall **)(MetadataUpdates **, _QWORD, struct TransactionData *, unsigned int *))*this + 20))(
            this,
            v37[4 * v38],
            a4,
            &v37[4 * v38 + 1]);
    if ( v5 )
    {
      v41 = this[36];
      v5 = 0;
      if ( v41 )
        tlx::_delete<MetadataUpdates>(v41);
      this[36] = 0;
    }
    else
    {
      v5 = 0;
    }
    if ( this[36] )
      Log_AssertionEvent(
        v41,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2226);
    if ( v26 < 0 )
    {
      Log_HREvent(
        (unsigned int)v26,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2227);
      utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_Uninit(Block);
      if ( !v27 )
        goto LABEL_31;
      v31 = v27;
      goto LABEL_30;
    }
    v37 = (unsigned int *)Block[0];
    ++v38;
  }
  if ( *((_DWORD *)a4 + 6) )
  {
    v42 = *((_QWORD *)a4 + 5);
    if ( v42 == *((_QWORD *)a4 + 6)
      || !utl::allocator_traits<utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::construct<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
            (__int64)v37,
            v42,
            (__int64)&v62) )
    {
      if ( !utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_PushBackOne2<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
              (__int64 *)a4 + 4,
              (__int64)&v62) )
      {
        v36 = 2233;
        goto LABEL_82;
      }
    }
    else
    {
      *((_QWORD *)a4 + 5) += 64LL;
    }
  }
  utl::vector__PimIMService::HandleChange_::_2_::TranslatedChangeInfo_utl::allocator__PimIMService::HandleChange_::_2_::TranslatedChangeInfo___::_Uninit(Block);
  if ( v27 )
    tlx::_delete<MetadataUpdates>(v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v69);
  AutoWobTicket::~AutoWobTicket((AutoWobTicket *)v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180007968  push    rbp
0x18000796a  push    rbx
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  push    r12
0x18000796f  push    r13
0x180007971  push    r14
0x180007973  push    r15
0x180007975  lea     rbp, [rsp-78h]
0x18000797a  sub     rsp, 178h
0x180007981  mov     rax, cs:__security_cookie
0x180007988  xor     rax, rsp
0x18000798b  mov     [rbp+0B0h+var_50], rax
0x18000798f  mov     rsi, [rbp+0B0h+arg_20]
0x180007996  xor     r12d, r12d
0x180007999  mov     r13, r9
0x18000799c  mov     rdi, r8
0x18000799f  mov     r15, rdx
0x1800079a2  mov     r14, rcx
0x1800079a5  cmp     [rdx], r12
0x1800079a8  jnz     short loc_1800079BC
0x1800079aa  mov     r8d, 811h
0x1800079b0  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800079b7  call    Log_AssertionEvent
0x1800079bc  test    r13, r13
0x1800079bf  jnz     short loc_1800079D3
0x1800079c1  mov     r8d, 812h
0x1800079c7  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800079ce  call    Log_AssertionEvent
0x1800079d3  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x1800079d8  mov     ebx, eax
0x1800079da  test    eax, eax
0x1800079dc  jns     short loc_1800079FE
0x1800079de  mov     r9d, 814h
0x1800079e4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800079eb  mov     edx, 1
0x1800079f0  mov     ecx, eax
0x1800079f2  call    Log_HREvent
0x1800079f7  mov     eax, ebx
0x1800079f9  jmp     loc_180008037
0x1800079fe  xor     eax, eax
0x180007a00  mov     dword ptr [rsp+1B0h+Block], r12d
0x180007a05  mov     [rbp+0B0h+var_120], rax
0x180007a09  lea     r9, [rsp+1B0h+var_138]; struct IPOItemMetadata **
0x180007a0e  lea     rax, [rsp+1B0h+Block]
0x180007a13  mov     [rsp+1B0h+var_138], r12
0x180007a18  mov     [rsp+1B0h+var_188], rax; int *
0x180007a1d  xorps   xmm0, xmm0
0x180007a20  lea     rax, [rbp+0B0h+var_130]
0x180007a24  mov     r8, rdi; struct ChangeInfo *
0x180007a27  mov     rdx, r15; struct SyncPartnerData *
0x180007a2a  mov     [rsp+1B0h+var_190], rax; struct _SQLCEPROPVAL *
0x180007a2f  movups  [rbp+0B0h+var_130], xmm0
0x180007a33  call    ?ShouldHandleChange@PimIMService@@QEAAJAEBUSyncPartnerData@@AEBUChangeInfo@@PEAPEAUIPOItemMetadata@@AEAU_SQLCEPROPVAL@@AEAH@Z; PimIMService::ShouldHandleChange(SyncPartnerData const &,ChangeInfo const &,IPOItemMetadata * *,_SQLCEPROPVAL &,int &)
0x180007a38  mov     ebx, eax
0x180007a3a  test    eax, eax
0x180007a3c  jns     short loc_180007A46
0x180007a3e  mov     r9d, 821h
0x180007a44  jmp     short loc_180007AB8
0x180007a46  cmp     dword ptr [rsp+1B0h+Block], r12d
0x180007a4b  jnz     loc_18000802B
0x180007a51  mov     eax, [rdi+8]
0x180007a54  lea     r9, [rbp+0B0h+var_C0]
0x180007a58  movsd   xmm0, qword ptr [rdi]
0x180007a5c  lea     r8, [rsp+1B0h+Block]
0x180007a61  movsd   xmm1, qword ptr [rdi]
0x180007a65  mov     rcx, r14
0x180007a68  mov     edx, [rdi+0Ch]
0x180007a6b  movsd   [rbp+0B0h+var_CC], xmm0
0x180007a70  xorps   xmm0, xmm0
0x180007a73  mov     [rbp+0B0h+var_C4], eax
0x180007a76  mov     dword ptr [rsp+1B0h+Block+8], eax
0x180007a7a  mov     rax, [r14]
0x180007a7d  movups  [rbp+0B0h+var_AC], xmm0
0x180007a81  mov     [rbp+0B0h+var_D0], edx
0x180007a84  movups  [rbp+0B0h+var_BC], xmm0
0x180007a88  mov     rax, [rax+0D8h]
0x180007a8f  movups  xmm0, xmmword ptr [rdi+10h]
0x180007a93  mov     [rbp+0B0h+var_C0], r12d
0x180007a97  movsd   [rsp+1B0h+Block], xmm1
0x180007a9d  movdqu  [rbp+0B0h+var_AC+4], xmm0
0x180007aa2  mov     [rsp+1B0h+var_190], rsi
0x180007aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aac  mov     ebx, eax
0x180007aae  test    eax, eax
0x180007ab0  jns     short loc_180007AD0
0x180007ab2  mov     r9d, 82Fh
0x180007ab8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007abf  mov     edx, 1
0x180007ac4  mov     ecx, eax
0x180007ac6  call    Log_HREvent
0x180007acb  jmp     loc_18000801C
0x180007ad0  cmp     dword ptr [rsi], 1
0x180007ad3  jz      loc_18000802B
0x180007ad9  movsd   xmm0, qword ptr [rdi]
0x180007add  lea     r8, [rsp+1B0h+Block]
0x180007ae2  mov     eax, [rdi+8]
0x180007ae5  lea     rdx, [rbp+0B0h+var_110]
0x180007ae9  mov     rcx, r14
0x180007aec  movsd   qword ptr [rbp+0B0h+var_110], xmm0
0x180007af1  mov     [rsp+1B0h+var_170], r12b
0x180007af6  mov     [rsp+1B0h+Block], r12
0x180007afb  mov     dword ptr [rbp+0B0h+var_110+8], eax
0x180007afe  call    ?GetWobTicket@PimIMService@@AEAA_NUUSOID@@PEAU__MIDL___MIDL_itf_unistore_0000_0000_0005@@@Z; PimIMService::GetWobTicket(USOID,__MIDL___MIDL_itf_unistore_0000_0000_0005 *)
0x180007b03  test    al, al
0x180007b05  jz      short loc_180007B41
0x180007b07  mov     rax, [rsp+1B0h+Block]
0x180007b0c  lea     rcx, [rsp+1B0h+Block]
0x180007b11  mov     [rsp+1B0h+Block], rax
0x180007b16  call    cs:__imp_RtlSetThreadWorkOnBehalfTicket
0x180007b1c  test    eax, eax
0x180007b1e  js      short loc_180007B27
0x180007b20  mov     [rsp+1B0h+var_170], 1
0x180007b25  jmp     short loc_180007B41
0x180007b27  bts     eax, 1Ch
0x180007b2b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007b32  mov     ecx, eax
0x180007b34  mov     r9d, 6Bh ; 'k'
0x180007b3a  xor     edx, edx
0x180007b3c  call    Log_HREvent
0x180007b41  movups  xmm0, [rbp+0B0h+var_BC]
0x180007b45  lea     rcx, [rbp+0B0h+var_F0]
0x180007b49  xor     eax, eax
0x180007b4b  movsd   xmm1, [rbp+0B0h+var_120]
0x180007b50  lea     r9, [rbp+0B0h+var_E0]
0x180007b54  mov     [rsp+1B0h+var_180], rcx
0x180007b59  lea     r8, [rsp+1B0h+var_13C]
0x180007b5e  mov     [rbp+0B0h+var_E0], rax
0x180007b62  lea     rcx, [rsp+1B0h+var_140]
0x180007b67  mov     [rbp+0B0h+var_D8], eax
0x180007b6a  lea     rdx, [rsp+1B0h+Block]
0x180007b6f  mov     [rbp+0B0h+var_F0], rax
0x180007b73  mov     [rbp+0B0h+var_E8], eax
0x180007b76  mov     eax, [rbp+0B0h+var_C0]
0x180007b79  mov     dword ptr [rbp+0B0h+var_110], eax
0x180007b7c  mov     eax, dword ptr [rbp+0B0h+var_AC]
0x180007b7f  mov     [rsp+1B0h+var_188], rcx
0x180007b84  lea     rcx, [rbp+0B0h+var_110]
0x180007b88  mov     [rbp+0B0h+var_FC], eax
0x180007b8b  mov     rax, [r14]
0x180007b8e  movups  [rbp+0B0h+var_110+4], xmm0
0x180007b92  mov     [rsp+1B0h+var_190], rcx
0x180007b97  mov     rcx, r14
0x180007b9a  movups  xmm0, [rbp+0B0h+var_130]
0x180007b9e  mov     rax, [rax+0B0h]
0x180007ba5  mov     [rsp+1B0h+var_13C], r12d
0x180007baa  mov     [rsp+1B0h+var_140], r12d
0x180007baf  movaps  xmmword ptr [rsp+1B0h+Block], xmm0
0x180007bb4  movsd   [rsp+1B0h+var_150], xmm1
0x180007bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbf  mov     esi, eax
0x180007bc1  test    eax, eax
0x180007bc3  jns     short loc_180007BEF
0x180007bc5  mov     r9d, 84Ch
0x180007bcb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007bd2  mov     edx, 1
0x180007bd7  mov     ecx, eax
0x180007bd9  call    Log_HREvent
0x180007bde  lea     rcx, [rsp+1B0h+var_170]; this
0x180007be3  call    ??1AutoWobTicket@@QEAA@XZ; AutoWobTicket::~AutoWobTicket(void)
0x180007be8  mov     ebx, esi
0x180007bea  jmp     loc_18000801C
0x180007bef  mov     eax, [rbp+0B0h+var_D0]
0x180007bf2  movsd   xmm0, [rbp+0B0h+var_CC]
0x180007bf7  movups  xmm1, [rbp+0B0h+var_AC]
0x180007bfb  mov     rdx, [rsp+1B0h+var_138]; struct IUnknown *
0x180007c00  mov     [rbp+0B0h+var_90], eax
0x180007c03  mov     eax, [rbp+0B0h+var_C4]
0x180007c06  mov     [rbp+0B0h+var_84], eax
0x180007c09  mov     eax, [rbp+0B0h+var_C0]
0x180007c0c  movsd   [rbp+0B0h+var_8C], xmm0
0x180007c11  mov     [rbp+0B0h+var_80], eax
0x180007c14  mov     eax, [rbp+0B0h+var_9C]
0x180007c17  mov     [rbp+0B0h+var_5C], eax
0x180007c1a  mov     [rbp+0B0h+var_58], r12
0x180007c1e  movups  xmm0, [rbp+0B0h+var_BC]
0x180007c22  movups  [rbp+0B0h+var_6C], xmm1
0x180007c26  movups  [rbp+0B0h+var_7C], xmm0
0x180007c2a  test    rdx, rdx
0x180007c2d  jz      short loc_180007C38
0x180007c2f  lea     rcx, [rbp+0B0h+var_58]; struct IUnknown **
0x180007c33  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180007c38  mov     rbx, r12
0x180007c3b  mov     [rsp+1B0h+Block], rbx
0x180007c40  cmp     [r13+18h], r12d
0x180007c44  jnz     loc_180007D11
0x180007c4a  lea     rcx, [rbp+0B0h+var_110]
0x180007c4e  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x180007c53  mov     rbx, qword ptr [rbp+0B0h+var_110+8]
0x180007c57  cmp     rbx, [rbp-50h]
0x180007c5b  jz      short loc_180007CCB
0x180007c5d  lea     r8, [rbp+0B0h+var_90]
0x180007c61  mov     rdx, rbx
0x180007c64  call    ??$construct@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@AEBU12@@?$allocator_traits@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@1@PEAU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@1@AEBU31@@Z; utl::allocator_traits<utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::construct<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>> &,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> *,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &)
0x180007c69  test    al, al
0x180007c6b  jz      short loc_180007CCB
0x180007c6d  add     rbx, 40h ; '@'
0x180007c71  mov     qword ptr [rbp+0B0h+var_110+8], rbx
0x180007c75  lea     r8, [rsp+1B0h+Block]
0x180007c7a  mov     rcx, r15
0x180007c7d  lea     rdx, [rbp+0B0h+var_110]
0x180007c81  call    ?CreateMetadataUpdates@MetadataUpdates@@SAJAEBUSyncPartnerData@@AEAV?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAV?$auto_ptr@UMetadataUpdates@@$1??$_delete@UMetadataUpdates@@@tlx@@YAXPEAU1@@Z@tlx@@@Z; MetadataUpdates::CreateMetadataUpdates(SyncPartnerData const &,utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>> &,tlx::auto_ptr<MetadataUpdates,&tlx::_delete<MetadataUpdates>(MetadataUpdates *)> &)
0x180007c86  mov     esi, eax
0x180007c88  test    eax, eax
0x180007c8a  jns     short loc_180007D03
0x180007c8c  mov     r9d, 85Ch
0x180007c92  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007c99  mov     edx, 1
0x180007c9e  mov     ecx, eax
0x180007ca0  call    Log_HREvent
0x180007ca5  lea     rcx, [rbp+0B0h+var_110]
0x180007ca9  call    ?_Uninit@?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit(void)
0x180007cae  mov     rcx, [rsp+1B0h+Block]; Block
0x180007cb3  test    rcx, rcx
0x180007cb6  jz      short loc_180007CBD
0x180007cb8  call    ??$_delete@UMetadataUpdates@@@tlx@@YAXPEAUMetadataUpdates@@@Z; tlx::_delete<MetadataUpdates>(MetadataUpdates *)
0x180007cbd  lea     rcx, [rbp+0B0h+var_58]
0x180007cc1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007cc6  jmp     loc_180007BDE
0x180007ccb  lea     rdx, [rbp+0B0h+var_90]
0x180007ccf  lea     rcx, [rbp+0B0h+var_110]
0x180007cd3  call    ??$_PushBackOne2@AEBU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAA_NAEBU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@1@@Z; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_PushBackOne2<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &)
0x180007cd8  test    al, al
0x180007cda  jnz     short loc_180007C75
0x180007cdc  mov     r9d, 859h
0x180007ce2  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007ce9  xor     edx, edx
0x180007ceb  mov     ecx, 8007000Eh
0x180007cf0  call    Log_HREvent
0x180007cf5  lea     rcx, [rbp+0B0h+var_110]
0x180007cf9  call    ?_Uninit@?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit(void)
0x180007cfe  jmp     loc_180008004
0x180007d03  lea     rcx, [rbp+0B0h+var_110]
0x180007d07  call    ?_Uninit@?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_Uninit(void)
0x180007d0c  mov     rbx, [rsp+1B0h+Block]
0x180007d11  lea     rcx, [rsp+1B0h+Block]
0x180007d16  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x180007d1b  mov     ecx, [rsp+1B0h+var_13C]
0x180007d1f  test    ecx, ecx
0x180007d21  jz      loc_180007E07
0x180007d27  mov     rdi, [rsp+1B0h+Block+8]
0x180007d2c  mov     r15, [rsp+1B0h+var_150]
0x180007d31  movsd   xmm0, [rbp+0B0h+var_E0]
0x180007d36  mov     eax, [rbp+0B0h+var_D8]
0x180007d39  mov     dword ptr [rbp+0B0h+var_110], ecx
0x180007d3c  movsd   qword ptr [rbp+0B0h+var_110+4], xmm0
0x180007d41  mov     dword ptr [rbp+0B0h+var_110+0Ch], eax
0x180007d44  cmp     rdi, r15
0x180007d47  jz      short loc_180007D5C
0x180007d49  movups  xmm0, [rbp+0B0h+var_110]
0x180007d4d  movdqu  xmmword ptr [rdi], xmm0
0x180007d51  add     rdi, 10h
0x180007d55  mov     [rsp+1B0h+Block+8], rdi
0x180007d5a  jmp     short loc_180007D83
0x180007d5c  lea     rdx, [rbp+0B0h+var_110]
0x180007d60  lea     rcx, [rsp+1B0h+Block]
0x180007d65  call    utl__vector__PimIMService__HandleChange____2___TranslatedChangeInfo_utl__allocator__PimIMService__HandleChange____2___TranslatedChangeInfo______PushBackOne2__PimIMService__HandleChange____2___TranslatedChangeInfo_const___
0x180007d6a  test    al, al
0x180007d6c  jnz     short loc_180007D79
0x180007d6e  mov     r9d, 869h
0x180007d74  jmp     loc_180007FDA
0x180007d79  mov     r15, [rsp+1B0h+var_150]
0x180007d7e  mov     rdi, [rsp+1B0h+Block+8]
0x180007d83  mov     ecx, [rsp+1B0h+var_140]
0x180007d87  test    ecx, ecx
0x180007d89  jz      loc_180007E63
0x180007d8f  movsd   xmm0, [rbp+0B0h+var_F0]
0x180007d94  mov     eax, [rbp+0B0h+var_E8]
0x180007d97  movsd   qword ptr [rbp+0B0h+var_110+4], xmm0
0x180007d9c  mov     dword ptr [rbp+0B0h+var_110], ecx
0x180007d9f  mov     dword ptr [rbp+0B0h+var_110+0Ch], eax
0x180007da2  cmp     ecx, 2
0x180007da5  jnz     short loc_180007DCE
0x180007da7  mov     rdx, [rsp+1B0h+Block]
0x180007dac  lea     r9, [rbp+0B0h+var_110]
0x180007db0  lea     rcx, [rsp+1B0h+Block]
0x180007db5  call    utl__vector__PimIMService__HandleChange____2___TranslatedChangeInfo_utl__allocator__PimIMService__HandleChange____2___TranslatedChangeInfo______InsertManyFillFn__lambda_c6ca038e7522b204bcd33104569c2333___
0x180007dba  test    rax, rax
0x180007dbd  jnz     loc_180007E5E
0x180007dc3  mov     r9d, 88Ah
0x180007dc9  jmp     loc_180007FDA
0x180007dce  cmp     ecx, 1
0x180007dd1  jz      short loc_180007DE5
0x180007dd3  mov     r8d, 88Fh
0x180007dd9  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007de0  call    Log_AssertionEvent
0x180007de5  cmp     rdi, r15
0x180007de8  jnz     short loc_180007E2E
0x180007dea  lea     rdx, [rbp+0B0h+var_110]
0x180007dee  lea     rcx, [rsp+1B0h+Block]
0x180007df3  call    utl__vector__PimIMService__HandleChange____2___TranslatedChangeInfo_utl__allocator__PimIMService__HandleChange____2___TranslatedChangeInfo______PushBackOne2__PimIMService__HandleChange____2___TranslatedChangeInfo_const___
0x180007df8  test    al, al
0x180007dfa  jnz     short loc_180007E5E
0x180007dfc  mov     r9d, 892h
0x180007e02  jmp     loc_180007FDA
0x180007e07  mov     eax, [rsp+1B0h+var_140]
0x180007e0b  test    eax, eax
0x180007e0d  jz      short loc_180007E5E
0x180007e0f  mov     rdi, [rsp+1B0h+Block+8]
0x180007e14  movsd   xmm0, [rbp+0B0h+var_F0]
  ... truncated ...
```
