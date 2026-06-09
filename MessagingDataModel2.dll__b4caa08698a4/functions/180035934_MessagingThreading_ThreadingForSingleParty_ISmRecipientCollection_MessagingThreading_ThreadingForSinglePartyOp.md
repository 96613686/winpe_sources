# MessagingThreading::ThreadingForSingleParty(ISmRecipientCollection *,MessagingThreading::ThreadingForSinglePartyOptions,CAutoBlob &,ISmConversation * *)

- ea: `0x180035934`
- end: `0x180035e44`
- name: `?ThreadingForSingleParty@MessagingThreading@@QEAAJPEAUISmRecipientCollection@@W4ThreadingForSinglePartyOptions@1@AEAVCAutoBlob@@PEAPEAUISmConversation@@@Z`
- size: `1296`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000e7c0`
- `0x180032848`
- `0x180035448`

## callees

- `0x1800016a0`
- `0x180001838`
- `0x180005c50`
- `0x180008870`
- `0x180008898`
- `0x180012e34`
- `0x180017854`
- `0x1800178d8`
- `0x180017aa4`
- `0x1800332fc`
- `0x180033578`
- `0x180033bf0`
- `0x180033c28`
- `0x180034258`
- `0x180035934`
- `0x180035e70`
- `0x18003613c`
- `0x180037bbc`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## string_xrefs

- `0x18003597b`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800359be`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800359fc`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180035a4b`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180035c54`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180035dc8`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180035b67`: `[Threading] Creating new conversation for contact`
- `0x180035bf2`: `[Threading] created new virtual conversation thread by LinkId`
- `0x180035cd7`: `[Threading] Found SingleParty thread by raw address`
- `0x180035d80`: `[Threading] created SingleParty thread by raw address`

## pseudocode

```c
__int64 __fastcall MessagingThreading::ThreadingForSingleParty(
        struct IUnknown **a1,
        __int64 *a2,
        int a3,
        CAutoBlob *a4,
        struct ISmConversation **a5)
{
  struct IUnknown *v9; // rdx
  int started; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int BestConversation; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  struct ISmConversation *v18; // rdi
  struct IUnknown *v19; // rcx
  const unsigned __int16 *v20; // xmm0_8
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int NormalizedRawAddress; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r9
  struct IUnknown *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  struct ISmConversation *v33[2]; // [rsp+40h] [rbp-81h] BYREF
  const unsigned __int16 *v34; // [rsp+50h] [rbp-71h] BYREF
  int v35; // [rsp+58h] [rbp-69h]
  int v36; // [rsp+60h] [rbp-61h] BYREF
  unsigned __int8 *v37; // [rsp+68h] [rbp-59h] BYREF
  struct ISmRecipient *v38; // [rsp+70h] [rbp-51h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-49h] BYREF
  struct OLITEMID *v40[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v41; // [rsp+90h] [rbp-31h]
  unsigned __int8 *v42; // [rsp+98h] [rbp-29h] BYREF
  char *v43; // [rsp+A0h] [rbp-21h]
  __int16 v44; // [rsp+A8h] [rbp-19h] BYREF
  __int64 v45; // [rsp+AAh] [rbp-17h]
  int v46; // [rsp+B2h] [rbp-Fh]
  __int16 v47; // [rsp+B6h] [rbp-Bh]
  _QWORD v48[4]; // [rsp+B8h] [rbp-9h] BYREF

  if ( !a5 )
  {
    Log_AssertionEvent_13(a1, "onecoreuap\\base\\appmodel\\messagingom\\src\\threading.cpp", 166);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a5 = 0;
  v9 = *a1;
  v48[0] = &CSmStoreTransaction::`vftable';
  memset(&v48[1], 0, 24);
  started = CSmStoreTransaction::StartTransaction((CSmStoreTransaction *)v48, v9);
  v11 = started;
  if ( started < 0 )
  {
    Log_HREvent_14(started);
    goto LABEL_43;
  }
  v12 = *a2;
  v38 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct ISmRecipient **))(v12 + 48))(a2, 0, &v38);
  v11 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_14(v13);
LABEL_42:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    goto LABEL_43;
  }
  v41 = -1;
  *(__m128i *)v40 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( a3 != 2 )
  {
    v14 = MessagingThreading::ResolveRecipientToAggregate(a1[1], v38, v40);
    v11 = v14;
    if ( v14 < 0 )
    {
      Log_HREvent_14(v14);
LABEL_41:
      utl::vector<utl::pair<SlotId,enum SlotState>,utl::allocator<utl::pair<SlotId,enum SlotState>>>::_Uninit(v40);
      goto LABEL_42;
    }
  }
  v33[0] = 0;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((v40[1] - v40[0]) >> 2) )
  {
    BestConversation = MessagingThreading::_FindBestConversation((MessagingThreading *)a1);
    v11 = BestConversation;
    if ( BestConversation >= 0 )
    {
      BestConversation = MessagingThreading::UpgradeConversation((MessagingThreading *)a1, v38, v40[0], v33);
      v11 = BestConversation;
      if ( BestConversation >= 0 )
      {
        v18 = v33[0];
        if ( v33[0] || !a3 )
          goto LABEL_36;
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v39 = *((_DWORD *)v40[0] + 2);
          v36 = *((_DWORD *)v40[0] + 1);
          LODWORD(v37) = *(_DWORD *)v40[0];
          v34 = (const unsigned __int16 *)"[Threading] Creating new conversation for contact";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)v40[0],
            (int)byte_1800EA193,
            v16,
            v17,
            &v34,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v39);
        }
        v19 = *a1;
        LOBYTE(v16) = a3 == 2;
        v20 = *(const unsigned __int16 **)v40[0];
        v35 = *((_DWORD *)v40[0] + 2);
        v34 = v20;
        BestConversation = CSmConversation::CreateInstance(v19, a2, v16, 0, &v34, v33);
        v11 = BestConversation;
        if ( BestConversation >= 0 )
        {
          if ( (unsigned int)dword_1800FD5F0 > 4 )
          {
            v34 = L"[Threading] created new virtual conversation thread by LinkId";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v21,
              (int)&byte_1800EA14F,
              v22,
              v23,
              &v34);
          }
          v18 = v33[0];
LABEL_36:
          BestConversation = CSmStoreTransaction::EndTransaction((CSmStoreTransaction *)v48, 1);
          v11 = BestConversation;
          if ( BestConversation >= 0 )
          {
            v11 = 0;
            v33[0] = 0;
            *a5 = v18;
            if ( !v18 )
              v11 = -2147023728;
            goto LABEL_40;
          }
        }
      }
    }
    Log_HREvent_14(BestConversation);
    goto LABEL_40;
  }
  v42 = (unsigned __int8 *)&v44;
  v45 = 0;
  v43 = (char *)&v44;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  NormalizedRawAddress = GetNormalizedRawAddress(v38, &v42);
  v11 = NormalizedRawAddress;
  if ( NormalizedRawAddress < 0 )
    goto LABEL_22;
  NormalizedRawAddress = CAutoBlob::Set(a4, 2 * ((v43 - (char *)v42) >> 1), v42);
  v11 = NormalizedRawAddress;
  if ( NormalizedRawAddress < 0 )
    goto LABEL_22;
  if ( a3 == 2 )
  {
LABEL_31:
    v28 = *a1;
    v34 = 0;
    v35 = 0;
    LOBYTE(v25) = a3 == 2;
    NormalizedRawAddress = CSmConversation::CreateInstance(v28, a2, v25, 0, &v34, v33);
    v11 = NormalizedRawAddress;
    if ( NormalizedRawAddress >= 0 )
    {
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v34 = L"[Threading] created SingleParty thread by raw address";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v29,
          (int)&byte_1800EA0C7,
          v30,
          v31,
          &v34);
      }
      v18 = v33[0];
      goto LABEL_35;
    }
LABEL_22:
    Log_HREvent_14(NormalizedRawAddress);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v42);
LABEL_40:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v33);
    goto LABEL_41;
  }
  NormalizedRawAddress = MessagingThreading::FindConversation((MessagingThreading *)a1, a4, v33);
  v11 = NormalizedRawAddress;
  if ( NormalizedRawAddress < 0 )
    goto LABEL_22;
  v18 = v33[0];
  if ( !v33[0] )
  {
    if ( !a3 )
    {
LABEL_35:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v42);
      goto LABEL_36;
    }
    goto LABEL_31;
  }
  if ( (unsigned int)dword_1800FD5F0 > 4 )
  {
    v34 = L"[Threading] Found SingleParty thread by raw address";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v26,
      (int)byte_1800EA10B,
      v25,
      v27,
      &v34);
  }
  v33[0] = 0;
  *a5 = v18;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v33);
  utl::vector<utl::pair<SlotId,enum SlotState>,utl::allocator<utl::pair<SlotId,enum SlotState>>>::_Uninit(v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  v11 = 0;
LABEL_43:
  CSmStoreTransaction::~CSmStoreTransaction((CSmStoreTransaction *)v48);
  return v11;
}

```

## disassembly

```asm
0x180035934  mov     [rsp-8+arg_10], rbx
0x180035939  push    rbp
0x18003593a  push    rsi
0x18003593b  push    rdi
0x18003593c  push    r12
0x18003593e  push    r13
0x180035940  push    r14
0x180035942  push    r15
0x180035944  lea     rbp, [rsp-1Fh]
0x180035949  sub     rsp, 0E0h
0x180035950  mov     rax, cs:__security_cookie
0x180035957  xor     rax, rsp
0x18003595a  mov     [rbp+4Fh+var_38], rax
0x18003595e  mov     r15, [rbp+4Fh+arg_20]
0x180035962  xor     edi, edi
0x180035964  mov     r12, r9
0x180035967  mov     esi, r8d
0x18003596a  mov     r13, rdx
0x18003596d  mov     r14, rcx
0x180035970  test    r15, r15
0x180035973  jnz     short loc_18003598C
0x180035975  mov     r8d, 0A6h
0x18003597b  lea     rdx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180035982  call    Log_AssertionEvent_13
0x180035987  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003598c  mov     [r15], rdi
0x18003598f  lea     rax, ??_7CSmStoreTransaction@@6B@; const CSmStoreTransaction::`vftable'
0x180035996  mov     rdx, [r14]; struct ISmStore *
0x180035999  lea     rcx, [rbp+4Fh+var_58]; this
0x18003599d  mov     [rbp+4Fh+var_58], rax
0x1800359a1  mov     [rbp+4Fh+var_48], rdi
0x1800359a5  mov     [rbp+4Fh+var_50], rdi
0x1800359a9  mov     [rbp+4Fh+var_40], rdi
0x1800359ad  call    ?StartTransaction@CSmStoreTransaction@@QEAAJPEAUISmStore@@@Z; CSmStoreTransaction::StartTransaction(ISmStore *)
0x1800359b2  mov     ebx, eax
0x1800359b4  test    eax, eax
0x1800359b6  jns     short loc_1800359D6
0x1800359b8  mov     r9d, 0AAh
0x1800359be  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800359c5  mov     edx, 1
0x1800359ca  mov     ecx, eax; int
0x1800359cc  call    Log_HREvent_14
0x1800359d1  jmp     loc_180035E12
0x1800359d6  mov     rax, [r13+0]
0x1800359da  lea     r8, [rbp+4Fh+var_A0]
0x1800359de  xor     edx, edx
0x1800359e0  mov     [rbp+4Fh+var_A0], rdi
0x1800359e4  mov     rcx, r13
0x1800359e7  mov     rax, [rax+30h]
0x1800359eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359f0  mov     ebx, eax
0x1800359f2  test    eax, eax
0x1800359f4  jns     short loc_180035A14
0x1800359f6  mov     r9d, 0ADh
0x1800359fc  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180035a03  mov     edx, 1
0x180035a08  mov     ecx, eax; int
0x180035a0a  call    Log_HREvent_14
0x180035a0f  jmp     loc_180035E09
0x180035a14  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180035a1c  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFFh
0x180035a24  movdqu  xmmword ptr [rbp+4Fh+var_90], xmm0
0x180035a29  cmp     esi, 2
0x180035a2c  jz      short loc_180035A63
0x180035a2e  mov     rdx, [rbp+4Fh+var_A0]
0x180035a32  lea     r8, [rbp+4Fh+var_90]
0x180035a36  mov     rcx, [r14+8]
0x180035a3a  call    ?ResolveRecipientToAggregate@MessagingThreading@@SAJPEAUIPOutlookApp3@@PEAUISmRecipient@@PEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; MessagingThreading::ResolveRecipientToAggregate(IPOutlookApp3 *,ISmRecipient *,utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x180035a3f  mov     ebx, eax
0x180035a41  test    eax, eax
0x180035a43  jns     short loc_180035A63
0x180035a45  mov     r9d, 0B3h
0x180035a4b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180035a52  mov     edx, 1
0x180035a57  mov     ecx, eax; int
0x180035a59  call    Log_HREvent_14
0x180035a5e  jmp     loc_180035E00
0x180035a63  mov     rax, [rbp+4Fh+var_90+8]
0x180035a67  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180035a71  sub     rax, [rbp+4Fh+var_90]
0x180035a75  sar     rax, 2
0x180035a79  imul    rax, rcx
0x180035a7d  mov     [rsp+110h+var_D0], rdi
0x180035a82  test    rax, rax
0x180035a85  jz      loc_180035C1C
0x180035a8b  lea     r8, [rsp+110h+var_D0]
0x180035a90  mov     rcx, r14; this
0x180035a93  lea     rdx, [rbp+4Fh+var_90]
0x180035a97  call    ?_FindBestConversation@MessagingThreading@@AEAAJAEBV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@PEAPEAUISmConversation@@@Z; MessagingThreading::_FindBestConversation(utl::vector<OLITEMID,utl::allocator<OLITEMID>> const &,ISmConversation * *)
0x180035a9c  mov     ebx, eax
0x180035a9e  test    eax, eax
0x180035aa0  jns     short loc_180035AAD
0x180035aa2  mov     r9d, 0BBh
0x180035aa8  jmp     loc_180035DC8
0x180035aad  mov     rdi, [rsp+110h+var_D0]
0x180035ab2  test    rdi, rdi
0x180035ab5  jz      short loc_180035B04
0x180035ab7  mov     [rbp+4Fh+var_98], 0
0x180035abe  lea     r8, [rbp+4Fh+var_A8]
0x180035ac2  mov     [rbp+4Fh+var_A8], 0
0x180035aca  lea     rdx, [rbp+4Fh+var_98]
0x180035ace  mov     rax, [rdi]
0x180035ad1  mov     rcx, rdi
0x180035ad4  mov     rax, [rax+0F0h]
0x180035adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ae0  mov     r8, [rbp+4Fh+var_A8]; unsigned __int8 *
0x180035ae4  mov     rcx, r12; this
0x180035ae7  mov     edx, [rbp+4Fh+var_98]; unsigned int
0x180035aea  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x180035aef  mov     ebx, eax
0x180035af1  test    eax, eax
0x180035af3  jns     loc_180035DAE
0x180035af9  mov     r9d, 0C2h
0x180035aff  jmp     loc_180035DC8
0x180035b04  mov     r8, [rbp+4Fh+var_90]; struct OLITEMID *
0x180035b08  lea     r9, [rsp+110h+var_D0]; struct ISmConversation **
0x180035b0d  mov     rdx, [rbp+4Fh+var_A0]; struct ISmRecipient *
0x180035b11  mov     rcx, r14; this
0x180035b14  call    ?UpgradeConversation@MessagingThreading@@QEAAJPEAUISmRecipient@@AEBUOLITEMID@@PEAPEAUISmConversation@@@Z; MessagingThreading::UpgradeConversation(ISmRecipient *,OLITEMID const &,ISmConversation * *)
0x180035b19  mov     ebx, eax
0x180035b1b  test    eax, eax
0x180035b1d  jns     short loc_180035B2A
0x180035b1f  mov     r9d, 0C6h
0x180035b25  jmp     loc_180035DC8
0x180035b2a  mov     rdi, [rsp+110h+var_D0]
0x180035b2f  test    rdi, rdi
0x180035b32  jnz     loc_180035DAE
0x180035b38  test    esi, esi
0x180035b3a  jz      loc_180035DAE
0x180035b40  mov     eax, cs:dword_1800FD5F0
0x180035b46  cmp     eax, 4
0x180035b49  jbe     short loc_180035B9B
0x180035b4b  mov     rcx, [rbp+4Fh+var_90]
0x180035b4f  lea     rdx, byte_1800EA193
0x180035b56  mov     eax, [rcx+8]
0x180035b59  mov     [rbp+4Fh+var_98], eax
0x180035b5c  mov     eax, [rcx+4]
0x180035b5f  mov     [rbp+4Fh+var_B0], eax
0x180035b62  mov     eax, [rcx]
0x180035b64  mov     dword ptr [rbp+4Fh+var_A8], eax
0x180035b67  lea     rax, aThreadingCreat; "[Threading] Creating new conversation f"...
0x180035b6e  mov     [rbp+4Fh+var_C0], rax
0x180035b72  lea     rax, [rbp+4Fh+var_98]
0x180035b76  mov     [rsp+110h+var_D8], rax
0x180035b7b  lea     rax, [rbp+4Fh+var_B0]
0x180035b7f  mov     [rsp+110h+var_E0], rax
0x180035b84  lea     rax, [rbp+4Fh+var_A8]
0x180035b88  mov     [rsp+110h+var_E8], rax
0x180035b8d  lea     rax, [rbp+4Fh+var_C0]
0x180035b91  mov     [rsp+110h+var_F0], rax
0x180035b96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180035b9b  mov     rax, [rbp+4Fh+var_90]
0x180035b9f  cmp     esi, 2
0x180035ba2  mov     rcx, [r14]
0x180035ba5  mov     rdx, r13
0x180035ba8  setz    r8b
0x180035bac  xor     r9d, r9d
0x180035baf  movsd   xmm0, qword ptr [rax]
0x180035bb3  mov     eax, [rax+8]
0x180035bb6  mov     [rbp+4Fh+var_B8], eax
0x180035bb9  lea     rax, [rsp+110h+var_D0]
0x180035bbe  mov     [rsp+110h+var_E8], rax
0x180035bc3  lea     rax, [rbp+4Fh+var_C0]
0x180035bc7  mov     [rsp+110h+var_F0], rax
0x180035bcc  movsd   [rbp+4Fh+var_C0], xmm0
0x180035bd1  call    ?CreateInstance@CSmConversation@@SAJPEAUISmStorePriv@@PEAUISmRecipientCollection@@_N2UOLITEMID@@PEAPEAUISmConversation@@@Z; CSmConversation::CreateInstance(ISmStorePriv *,ISmRecipientCollection *,bool,bool,OLITEMID,ISmConversation * *)
0x180035bd6  mov     ebx, eax
0x180035bd8  test    eax, eax
0x180035bda  jns     short loc_180035BE7
0x180035bdc  mov     r9d, 0D5h
0x180035be2  jmp     loc_180035DC8
0x180035be7  mov     eax, cs:dword_1800FD5F0
0x180035bed  cmp     eax, 4
0x180035bf0  jbe     short loc_180035C12
0x180035bf2  lea     rax, aThreadingCreat_1; "[Threading] created new virtual convers"...
0x180035bf9  mov     [rbp+4Fh+var_C0], rax
0x180035bfd  lea     rdx, byte_1800EA14F
0x180035c04  lea     rax, [rbp+4Fh+var_C0]
0x180035c08  mov     [rsp+110h+var_F0], rax
0x180035c0d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035c12  mov     rdi, [rsp+110h+var_D0]
0x180035c17  jmp     loc_180035DAE
0x180035c1c  mov     rcx, [rbp+4Fh+var_A0]
0x180035c20  lea     rax, [rbp+4Fh+var_68]
0x180035c24  mov     [rbp+4Fh+var_78], rax
0x180035c28  lea     rdx, [rbp+4Fh+var_78]
0x180035c2c  lea     rax, [rbp+4Fh+var_68]
0x180035c30  mov     [rbp+4Fh+var_66], rdi
0x180035c34  mov     [rbp+4Fh+var_70], rax
0x180035c38  mov     [rbp+4Fh+var_5E], edi
0x180035c3b  mov     [rbp+4Fh+var_5A], di
0x180035c3f  mov     [rbp+4Fh+var_68], di
0x180035c43  call    ?GetNormalizedRawAddress@@YAJPEAUISmRecipient@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetNormalizedRawAddress(ISmRecipient *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180035c48  mov     ebx, eax
0x180035c4a  test    eax, eax
0x180035c4c  jns     short loc_180035C75
0x180035c4e  mov     r9d, 0E3h
0x180035c54  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180035c5b  mov     edx, 1
0x180035c60  mov     ecx, eax; int
0x180035c62  call    Log_HREvent_14
0x180035c67  lea     rcx, [rbp+4Fh+var_78]
0x180035c6b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180035c70  jmp     loc_180035DF6
0x180035c75  mov     r8, [rbp+4Fh+var_78]; unsigned __int8 *
0x180035c79  mov     rcx, r12; this
0x180035c7c  mov     rdx, [rbp+4Fh+var_70]
0x180035c80  sub     rdx, r8
0x180035c83  sar     rdx, 1
0x180035c86  add     edx, edx; unsigned int
0x180035c88  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x180035c8d  mov     ebx, eax
0x180035c8f  test    eax, eax
0x180035c91  jns     short loc_180035C9B
0x180035c93  mov     r9d, 0E5h
0x180035c99  jmp     short loc_180035C54
0x180035c9b  cmp     esi, 2
0x180035c9e  jz      loc_180035D33
0x180035ca4  lea     r8, [rsp+110h+var_D0]; struct ISmConversation **
0x180035ca9  mov     rdx, r12; struct _SQLCEBLOB *
0x180035cac  mov     rcx, r14; this
0x180035caf  call    ?FindConversation@MessagingThreading@@QEAAJPEBU_SQLCEBLOB@@PEAPEAUISmConversation@@@Z; MessagingThreading::FindConversation(_SQLCEBLOB const *,ISmConversation * *)
0x180035cb4  mov     ebx, eax
0x180035cb6  test    eax, eax
0x180035cb8  jns     short loc_180035CC2
0x180035cba  mov     r9d, 0EAh
0x180035cc0  jmp     short loc_180035C54
0x180035cc2  mov     rdi, [rsp+110h+var_D0]
0x180035cc7  test    rdi, rdi
0x180035cca  jz      short loc_180035D2F
0x180035ccc  mov     eax, cs:dword_1800FD5F0
0x180035cd2  cmp     eax, 4
0x180035cd5  jbe     short loc_180035CF7
0x180035cd7  lea     rax, aThreadingFound_2; "[Threading] Found SingleParty thread by"...
0x180035cde  mov     [rbp+4Fh+var_C0], rax
0x180035ce2  lea     rdx, byte_1800EA10B
0x180035ce9  lea     rax, [rbp+4Fh+var_C0]
0x180035ced  mov     [rsp+110h+var_F0], rax
0x180035cf2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035cf7  lea     rcx, [rbp+4Fh+var_78]
0x180035cfb  mov     [rsp+110h+var_D0], 0
0x180035d04  mov     [r15], rdi
0x180035d07  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180035d0c  lea     rcx, [rsp+110h+var_D0]
0x180035d11  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180035d16  lea     rcx, [rbp+4Fh+var_90]
0x180035d1a  call    ?_Uninit@?$vector@U?$pair@USlotId@@W4SlotState@@@utl@@V?$allocator@U?$pair@USlotId@@W4SlotState@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::pair<SlotId,SlotState>,utl::allocator<utl::pair<SlotId,SlotState>>>::_Uninit(void)
0x180035d1f  lea     rcx, [rbp+4Fh+var_A0]
0x180035d23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180035d28  xor     ebx, ebx
0x180035d2a  jmp     loc_180035E12
0x180035d2f  test    esi, esi
0x180035d31  jz      short loc_180035DA5
0x180035d33  mov     rcx, [r14]
0x180035d36  xor     eax, eax
0x180035d38  mov     [rbp+4Fh+var_C0], rax
0x180035d3c  cmp     esi, 2
0x180035d3f  mov     [rbp+4Fh+var_B8], eax
0x180035d42  mov     rdx, r13
0x180035d45  lea     rax, [rsp+110h+var_D0]
0x180035d4a  setz    r8b
0x180035d4e  mov     [rsp+110h+var_E8], rax
0x180035d53  xor     r9d, r9d
0x180035d56  lea     rax, [rbp+4Fh+var_C0]
0x180035d5a  mov     [rsp+110h+var_F0], rax
0x180035d5f  call    ?CreateInstance@CSmConversation@@SAJPEAUISmStorePriv@@PEAUISmRecipientCollection@@_N2UOLITEMID@@PEAPEAUISmConversation@@@Z; CSmConversation::CreateInstance(ISmStorePriv *,ISmRecipientCollection *,bool,bool,OLITEMID,ISmConversation * *)
0x180035d64  mov     ebx, eax
0x180035d66  test    eax, eax
0x180035d68  jns     short loc_180035D75
0x180035d6a  mov     r9d, 0FFh
0x180035d70  jmp     loc_180035C54
0x180035d75  mov     eax, cs:dword_1800FD5F0
0x180035d7b  cmp     eax, 4
0x180035d7e  jbe     short loc_180035DA0
0x180035d80  lea     rax, aThreadingCreat_0; "[Threading] created SingleParty thread "...
0x180035d87  mov     [rbp+4Fh+var_C0], rax
0x180035d8b  lea     rdx, byte_1800EA0C7
0x180035d92  lea     rax, [rbp+4Fh+var_C0]
0x180035d96  mov     [rsp+110h+var_F0], rax
0x180035d9b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035da0  mov     rdi, [rsp+110h+var_D0]
0x180035da5  lea     rcx, [rbp+4Fh+var_78]
0x180035da9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180035dae  mov     edx, 1; int
0x180035db3  lea     rcx, [rbp+4Fh+var_58]; this
0x180035db7  call    ?EndTransaction@CSmStoreTransaction@@QEAAJH@Z; CSmStoreTransaction::EndTransaction(int)
0x180035dbc  mov     ebx, eax
0x180035dbe  test    eax, eax
0x180035dc0  jns     short loc_180035DDD
0x180035dc2  mov     r9d, 109h
0x180035dc8  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180035dcf  mov     edx, 1
0x180035dd4  mov     ecx, eax; int
0x180035dd6  call    Log_HREvent_14
0x180035ddb  jmp     short loc_180035DF6
0x180035ddd  xor     ebx, ebx
0x180035ddf  mov     [rsp+110h+var_D0], 0
0x180035de8  test    rdi, rdi
0x180035deb  mov     [r15], rdi
0x180035dee  mov     eax, 80070490h
  ... truncated ...
```
