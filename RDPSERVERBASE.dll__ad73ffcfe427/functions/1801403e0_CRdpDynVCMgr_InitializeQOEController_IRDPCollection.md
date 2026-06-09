# CRdpDynVCMgr::InitializeQOEController(IRDPCollection *)

- ea: `0x1801403e0`
- end: `0x18014069e`
- name: `?InitializeQOEController@CRdpDynVCMgr@@IEAAJPEAUIRDPCollection@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *__hidden this, struct IRDPCollection *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18013f3d0`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180001f84`
- `0x18002aafc`
- `0x18004f5bc`
- `0x1800ab6e0`
- `0x1800ac38c`
- `0x1800ac70c`
- `0x1801403e0`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180140416`
- `OLEAUT32!__imp_VariantInit` at `0x180140420`
- `OLEAUT32!__imp_VariantInit` at `0x180140416`
- `OLEAUT32!__imp_VariantInit` at `0x180140420`
- `OLEAUT32!__imp_VariantClear` at `0x180140670`
- `OLEAUT32!__imp_VariantClear` at `0x18014067a`
- `OLEAUT32!__imp_VariantClear` at `0x180140670`
- `OLEAUT32!__imp_VariantClear` at `0x18014067a`

## string_xrefs

- `0x1801404f2`: `ReverseConnectGatewayUri`
- `0x18014058f`: `ReverseConnectHostPoolArmPath`
- `0x1801404a9`: `Failed to create QOE Accumulator`
- `0x180140568`: `CRdpDynVCMgr::InitializeQOEController - Set reverse connect gateway URI for QOE Controller`
- `0x180140539`: `CRdpDynVCMgr::InitializeQOEController - Failed to set reverse connect gateway Uri`
- `0x180140603`: `CRdpDynVCMgr::InitializeQOEController - Set reverse connect hostpool ARM path for QOE Controller`
- `0x1801405d0`: `CRdpDynVCMgr::InitializeQOEController - Failed to set reverse connect hostpool arm path`

## pseudocode

```c
__int64 __fastcall CRdpDynVCMgr::InitializeQOEController(struct QOEAccumulator **this, struct IRDPCollection *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int Instance; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  struct QOEAccumulator *v18; // rax
  const char *v20; // [rsp+50h] [rbp-9h] BYREF
  const char *v21; // [rsp+58h] [rbp-1h] BYREF
  char *v22; // [rsp+60h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp+Fh] BYREF
  VARIANTARG v24; // [rsp+80h] [rbp+27h] BYREF
  const char *v25; // [rsp+C0h] [rbp+67h] BYREF
  const char *v26; // [rsp+D0h] [rbp+77h] BYREF
  const char *v27; // [rsp+D8h] [rbp+7Fh] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v24, 0, sizeof(v24));
  VariantInit(&pvarg);
  VariantInit(&v24);
  if ( (unsigned int)CallbackContext > 4 )
  {
    v25 = "CRdpDynVCMgr::InitializeQOEController - Initializing QOE Controller";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&byte_180294567,
      v5,
      v6,
      (__int64)&v25);
  }
  v22 = (char *)(this + 2504);
  CTSCriticalSection::Lock((CTSCriticalSection *)(this + 2504));
  Instance = QOEAccumulator_CreateInstance(this + 2506);
  v10 = Instance;
  if ( Instance >= 0 )
  {
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"ReverseConnectGatewayUri",
           &pvarg) >= 0
      && pvarg.vt == 8 )
    {
      v11 = QOEAccumulator::SetReverseConnGatewayUri(this[2506], pvarg.bstrVal);
      if ( v11 >= 0 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v25 = "CRdpDynVCMgr::InitializeQOEController - Set reverse connect gateway URI for QOE Controller";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v12,
            (unsigned int)word_180294542,
            v13,
            v14,
            (__int64)&v25);
        }
      }
      else if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v25) = v11;
        v26 = "CRdpDynVCMgr::InitializeQOEController - Failed to set reverse connect gateway Uri";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_180294515,
          v13,
          v14,
          (__int64)&v26,
          (__int64)&v25);
      }
    }
    v10 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 24LL))(
            a2,
            L"ReverseConnectHostPoolArmPath",
            &v24);
    if ( v10 >= 0 && v24.vt == 8 )
    {
      v10 = QOEAccumulator::SetReverseConnectHostPoolArmPath(this[2506], v24.bstrVal);
      if ( v10 >= 0 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v25 = "CRdpDynVCMgr::InitializeQOEController - Set reverse connect hostpool ARM path for QOE Controller";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v17,
            (unsigned int)qword_1802944F0,
            v15,
            v16,
            (__int64)&v25);
        }
      }
      else if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v25) = v10;
        v26 = "CRdpDynVCMgr::InitializeQOEController - Failed to set reverse connect hostpool arm path";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_1802944C3,
          v15,
          v16,
          (__int64)&v26,
          (__int64)&v25);
      }
    }
    v18 = this[2506];
    *((_DWORD *)v18 + 13730) = 1;
    *((_DWORD *)v18 + 27580) = 1;
    *((_DWORD *)v18 + 41430) = 1;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v25 = "CRdpDynVCMgr::InitializeQOEController - QOE Controller initialized successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        1,
        (unsigned int)&word_180294476,
        v15,
        v16,
        (__int64)&v25);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v25) = 7027;
    v27 = "InitializeQOEController";
    LODWORD(v26) = Instance;
    v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    v21 = "Failed to create QOE Accumulator";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)&dword_18029458C,
      v8,
      v9,
      (__int64)&v21,
      (__int64)&v26,
      (__int64)&v20,
      (__int64)&v25,
      (__int64)&v27);
  }
  VariantClear(&pvarg);
  VariantClear(&v24);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801403e0  mov     [rsp-8+arg_8], rbx
0x1801403e5  push    rbp
0x1801403e6  push    rsi
0x1801403e7  push    rdi
0x1801403e8  lea     rbp, [rsp-47h]
0x1801403ed  sub     rsp, 0A0h
0x1801403f4  xor     eax, eax
0x1801403f6  mov     rdi, rcx
0x1801403f9  xorps   xmm0, xmm0
0x1801403fc  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180140400  xorps   xmm1, xmm1
0x180140403  mov     qword ptr [rbp+57h+var_30+10h], rax
0x180140407  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18014040b  mov     rsi, rdx
0x18014040e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180140412  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x180140416  call    cs:__imp_VariantInit
0x18014041c  lea     rcx, [rbp+57h+var_30]; pvarg
0x180140420  call    cs:__imp_VariantInit
0x180140426  mov     eax, cs:CallbackContext
0x18014042c  cmp     eax, 4
0x18014042f  jbe     short loc_180140451
0x180140431  lea     rax, aCrdpdynvcmgrIn_13; "CRdpDynVCMgr::InitializeQOEController -"...
0x180140438  mov     [rbp+57h+arg_0], rax
0x18014043c  lea     rdx, byte_180294567
0x180140443  lea     rax, [rbp+57h+arg_0]
0x180140447  mov     [rsp+0B0h+var_90], rax
0x18014044c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180140451  lea     rcx, [rdi+4E40h]; this
0x180140458  mov     [rbp+57h+var_50], rcx
0x18014045c  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180140461  lea     rcx, [rdi+4E50h]; struct QOEAccumulator **
0x180140468  call    ?QOEAccumulator_CreateInstance@@YAJPEAPEAVQOEAccumulator@@@Z; QOEAccumulator_CreateInstance(QOEAccumulator * *)
0x18014046d  mov     ebx, eax
0x18014046f  test    eax, eax
0x180140471  jns     short loc_1801404EB
0x180140473  mov     ecx, cs:CallbackContext
0x180140479  cmp     ecx, 2
0x18014047c  jbe     loc_18014066C
0x180140482  lea     rax, aInitializeqoec; "InitializeQOEController"
0x180140489  mov     dword ptr [rbp+57h+arg_0], 1B73h
0x180140490  mov     [rbp+57h+arg_18], rax
0x180140494  lea     rdx, dword_18029458C
0x18014049b  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801404a2  mov     dword ptr [rbp+57h+arg_10], ebx
0x1801404a5  mov     [rbp+57h+var_60], rax
0x1801404a9  lea     rax, aFailedToCreate_97; "Failed to create QOE Accumulator"
0x1801404b0  mov     [rbp+57h+var_58], rax
0x1801404b4  lea     rax, [rbp+57h+arg_18]
0x1801404b8  mov     [rsp+0B0h+var_70], rax
0x1801404bd  lea     rax, [rbp+57h+arg_0]
0x1801404c1  mov     [rsp+0B0h+var_78], rax
0x1801404c6  lea     rax, [rbp+57h+var_60]
0x1801404ca  mov     [rsp+0B0h+var_80], rax
0x1801404cf  lea     rax, [rbp+57h+arg_10]
0x1801404d3  mov     [rsp+0B0h+var_88], rax
0x1801404d8  lea     rax, [rbp+57h+var_58]
0x1801404dc  mov     [rsp+0B0h+var_90], rax
0x1801404e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801404e6  jmp     loc_18014066C
0x1801404eb  mov     rax, [rsi]
0x1801404ee  lea     r8, [rbp+57h+pvarg]
0x1801404f2  lea     rdx, aReverseconnect_0; "ReverseConnectGatewayUri"
0x1801404f9  mov     rcx, rsi
0x1801404fc  mov     rax, [rax+18h]
0x180140500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140505  test    eax, eax
0x180140507  js      short loc_180140588
0x180140509  cmp     word ptr [rbp+57h+pvarg], 8
0x18014050e  jnz     short loc_180140588
0x180140510  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x180140514  mov     rcx, [rdi+4E50h]; this
0x18014051b  call    ?SetReverseConnGatewayUri@QOEAccumulator@@QEAAJPEAG@Z; QOEAccumulator::SetReverseConnGatewayUri(ushort *)
0x180140520  test    eax, eax
0x180140522  jns     short loc_18014055D
0x180140524  mov     ecx, cs:CallbackContext
0x18014052a  cmp     ecx, 3
0x18014052d  jbe     short loc_180140588
0x18014052f  mov     dword ptr [rbp+57h+arg_0], eax
0x180140532  lea     rdx, byte_180294515
0x180140539  lea     rax, aCrdpdynvcmgrIn_12; "CRdpDynVCMgr::InitializeQOEController -"...
0x180140540  mov     [rbp+57h+arg_10], rax
0x180140544  lea     rax, [rbp+57h+arg_0]
0x180140548  mov     [rsp+0B0h+var_88], rax
0x18014054d  lea     rax, [rbp+57h+arg_10]
0x180140551  mov     [rsp+0B0h+var_90], rax
0x180140556  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014055b  jmp     short loc_180140588
0x18014055d  mov     eax, cs:CallbackContext
0x180140563  cmp     eax, 4
0x180140566  jbe     short loc_180140588
0x180140568  lea     rax, aCrdpdynvcmgrIn_4; "CRdpDynVCMgr::InitializeQOEController -"...
0x18014056f  mov     [rbp+57h+arg_0], rax
0x180140573  lea     rdx, word_180294542
0x18014057a  lea     rax, [rbp+57h+arg_0]
0x18014057e  mov     [rsp+0B0h+var_90], rax
0x180140583  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180140588  mov     rax, [rsi]
0x18014058b  lea     r8, [rbp+57h+var_30]
0x18014058f  lea     rdx, aReverseconnect; "ReverseConnectHostPoolArmPath"
0x180140596  mov     rcx, rsi
0x180140599  mov     rax, [rax+18h]
0x18014059d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801405a2  mov     ebx, eax
0x1801405a4  test    eax, eax
0x1801405a6  js      short loc_180140623
0x1801405a8  cmp     word ptr [rbp+57h+var_30], 8
0x1801405ad  jnz     short loc_180140623
0x1801405af  mov     rdx, qword ptr [rbp+57h+var_30+8]; unsigned __int16 *
0x1801405b3  mov     rcx, [rdi+4E50h]; this
0x1801405ba  call    ?SetReverseConnectHostPoolArmPath@QOEAccumulator@@QEAAJPEAG@Z; QOEAccumulator::SetReverseConnectHostPoolArmPath(ushort *)
0x1801405bf  mov     ebx, eax
0x1801405c1  test    eax, eax
0x1801405c3  mov     eax, cs:CallbackContext
0x1801405c9  jns     short loc_1801405FE
0x1801405cb  cmp     eax, 3
0x1801405ce  jbe     short loc_180140623
0x1801405d0  lea     rax, aCrdpdynvcmgrIn_8; "CRdpDynVCMgr::InitializeQOEController -"...
0x1801405d7  mov     dword ptr [rbp+57h+arg_0], ebx
0x1801405da  mov     [rbp+57h+arg_10], rax
0x1801405de  lea     rdx, byte_1802944C3
0x1801405e5  lea     rax, [rbp+57h+arg_0]
0x1801405e9  mov     [rsp+0B0h+var_88], rax
0x1801405ee  lea     rax, [rbp+57h+arg_10]
0x1801405f2  mov     [rsp+0B0h+var_90], rax
0x1801405f7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801405fc  jmp     short loc_180140623
0x1801405fe  cmp     eax, 4
0x180140601  jbe     short loc_180140623
0x180140603  lea     rax, aCrdpdynvcmgrIn_3; "CRdpDynVCMgr::InitializeQOEController -"...
0x18014060a  mov     [rbp+57h+arg_0], rax
0x18014060e  lea     rdx, qword_1802944F0
0x180140615  lea     rax, [rbp+57h+arg_0]
0x180140619  mov     [rsp+0B0h+var_90], rax
0x18014061e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180140623  mov     rax, [rdi+4E50h]
0x18014062a  mov     ecx, 1
0x18014062f  mov     [rax+0D688h], ecx
0x180140635  mov     [rax+1AEF0h], ecx
0x18014063b  mov     [rax+28758h], ecx
0x180140641  mov     eax, cs:CallbackContext
0x180140647  cmp     eax, 4
0x18014064a  jbe     short loc_18014066C
0x18014064c  lea     rax, aCrdpdynvcmgrIn_10; "CRdpDynVCMgr::InitializeQOEController -"...
0x180140653  mov     [rbp+57h+arg_0], rax
0x180140657  lea     rdx, word_180294476
0x18014065e  lea     rax, [rbp+57h+arg_0]
0x180140662  mov     [rsp+0B0h+var_90], rax
0x180140667  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18014066c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180140670  call    cs:__imp_VariantClear
0x180140676  lea     rcx, [rbp+57h+var_30]; pvarg
0x18014067a  call    cs:__imp_VariantClear
0x180140680  lea     rcx, [rbp+57h+var_50]; this
0x180140684  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180140689  mov     eax, ebx
0x18014068b  mov     rbx, [rsp+0B0h+arg_8]
0x180140693  add     rsp, 0A0h
0x18014069a  pop     rdi
0x18014069b  pop     rsi
0x18014069c  pop     rbp
0x18014069d  retn
```
