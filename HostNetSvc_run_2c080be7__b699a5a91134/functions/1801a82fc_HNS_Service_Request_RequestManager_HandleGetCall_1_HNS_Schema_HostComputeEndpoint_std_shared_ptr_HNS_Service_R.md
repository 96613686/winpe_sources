# HNS::Service::Request::RequestManager::HandleGetCall<1,HNS::Schema::HostComputeEndpoint>(std::shared_ptr<HNS::Service::Request::BaseRequest>,ushort const *,ushort const *)

- ea: `0x1801a82fc`
- end: `0x1801a8942`
- name: `??$HandleGetCall@$00UHostComputeEndpoint@Schema@HNS@@@RequestManager@Request@Service@HNS@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VBaseRequest@Request@Service@HNS@@@5@PEBG1@Z`
- size: `1606`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801af278`

## callees

- `0x180001b68`
- `0x180001df8`
- `0x180002164`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x180069b04`
- `0x18006c530`
- `0x18006cc2c`
- `0x1800759d8`
- `0x1800776d8`
- `0x18007e864`
- `0x180087cc0`
- `0x1800bcae4`
- `0x1800bdd2c`
- `0x1801a4af8`
- `0x1801a4ca4`
- `0x1801a4ddc`
- `0x1801a6bf0`
- `0x1801a82fc`
- `0x1801a95d4`
- `0x1801a96b0`
- `0x1801a9778`
- `0x1801a9840`
- `0x1801a9e18`
- `0x1801ab518`
- `0x1801ae5d0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a8382`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a8382`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a881c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a881c`

## string_xrefs

- `0x1801a8408`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a890e`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a8356`: `HNS::Service::Request::RequestManager::HandleGetCall`
- `0x1801a8439`: `HandleGetCall - Open function not supported for object`
- `0x1801a8902`: `HandleGetCall via WcnAgent failed %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall HNS::Service::Request::RequestManager::HandleGetCall<1,HNS::Schema::HostComputeEndpoint>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // eax
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r14
  __m128i si128; // xmm6
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  _QWORD *v23; // rax
  __m128i *v24; // rdx
  int v25; // r8d
  int v26; // r9d
  _QWORD *v27; // rax
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  unsigned int v31; // eax
  int v32; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+28h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-E0h]
  const char *v37; // [rsp+38h] [rbp-D0h]
  const char *v38; // [rsp+38h] [rbp-D0h]
  const char *v39; // [rsp+38h] [rbp-D0h]
  const char *v40; // [rsp+38h] [rbp-D0h]
  int v41[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+58h] [rbp-B0h] BYREF
  volatile signed __int32 *v44; // [rsp+60h] [rbp-A8h]
  _WORD *v45; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v46[2]; // [rsp+70h] [rbp-98h] BYREF
  LPVOID v47; // [rsp+80h] [rbp-88h]
  _QWORD *v48; // [rsp+88h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-78h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-68h]
  _QWORD v51[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v52[5]; // [rsp+B8h] [rbp-50h] BYREF
  char v53; // [rsp+E0h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v55; // [rsp+F8h] [rbp-10h]
  _QWORD v56[4]; // [rsp+108h] [rbp+0h] BYREF
  char v57[8]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v58; // [rsp+130h] [rbp+28h] BYREF
  __int64 v59; // [rsp+140h] [rbp+38h]
  __int64 v60; // [rsp+148h] [rbp+40h]
  __int64 v61; // [rsp+150h] [rbp+48h] BYREF
  __int128 v62; // [rsp+158h] [rbp+50h]
  __int128 v63; // [rsp+168h] [rbp+60h]
  __int128 v64; // [rsp+178h] [rbp+70h]
  int v65; // [rsp+188h] [rbp+80h]
  _BYTE v66[64]; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]

  *(_QWORD *)&v54 = a2;
  v52[2] = a3;
  LODWORD(pv) = 1;
  HNSTraceProvider::TraceEnter("HNS::Service::Request::RequestManager::HandleGetCall", 0x13Cu);
  if ( *(_WORD *)a4 && (*(_WORD *)a4 != 47 || *(_WORD *)(a4 + 2)) && (unsigned int)_o__wcsicmp(L"/all", a4) )
  {
    v31 = wil::verify_hresult<long>(2151350293LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)v31,
      (int)"HandleGetCall via WcnAgent failed %ws %ws",
      (const char *)a4,
      a5);
  }
  if ( *(_DWORD *)qword_18039BB28 > 4u )
    tlgWriteTransfer_EventWriteTransfer(qword_18039BB28, word_18033EE42, 0, 0, 2, v66);
  HNS::Service::Request::RequestManager::GetWcnAgentManager(a1, &v43);
  LOBYTE(v32) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 136LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x14B,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v32,
    (bool)"HandleGetCall - Enumerate function not supported for object",
    v37);
  LOBYTE(v33) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 152LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x150,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v33,
    (bool)"HandleGetCall - Open function not supported for object",
    v38);
  LOBYTE(v34) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 184LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x155,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v34,
    (bool)"HandleGetCall - Close function not supported for object",
    v39);
  LOBYTE(v35) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 168LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x15A,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v35,
    (bool)"HandleGetCall - Query function not supported for object",
    v40);
  v45 = 0;
  v9 = HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeEndpoint>(v43, a5, &v45);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)(unsigned int)v9,
      v36);
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    *(_QWORD *)v41 = v45;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)&byte_18033F23F,
      v10,
      v11,
      (__int64)v41);
  }
  v49 = 0;
  v50 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v45[v12] );
  *(_QWORD *)&v54 = v45;
  *((_QWORD *)&v54 + 1) = v12;
  Marshal::FromJsonThrow<std::vector<_GUID>,>(&v54, &v49, v10, 2147942413LL);
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v14 = *((_QWORD *)&v49 + 1);
  v13 = v49;
  if ( (_QWORD)v49 != *((_QWORD *)&v49 + 1) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      *(_QWORD *)v41 = 0;
      v52[3] = v41;
      v52[4] = &v43;
      v53 = 1;
      v16 = HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeEndpoint,void *>(
              v43,
              v13,
              v41);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x174,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
          (const char *)(unsigned int)v16,
          v36);
      pv = 0;
      v17 = HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeEndpoint,void *>(
              v43,
              *(_QWORD *)v41,
              byte_1802E2A80,
              &pv);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
          (const char *)(unsigned int)v17,
          v36);
      v51[0] = pv;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)pv + v18) );
      v51[1] = v18;
      v19 = (_QWORD *)HNS::Schema::ConvertV2ToInternalSchema<1>(v66, v51);
      if ( v19[3] <= 7u )
        v20 = v19;
      else
        v20 = (_QWORD *)*v19;
      v52[0] = v20;
      v52[1] = v19[2];
      HNS::Schema::ConvertInternalToV1Schema<1>(v56, v52);
      std::wstring::~wstring(v66);
      if ( *(_DWORD *)qword_18039BB28 > 4u )
      {
        v23 = v56;
        if ( v56[3] > 7u )
          v23 = (_QWORD *)v56[0];
        v48 = v23;
        *(_QWORD *)&v54 = pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_18039BB28,
          (unsigned int)&unk_18033EF28,
          v21,
          v22,
          (__int64)&v54,
          (__int64)&v48);
      }
      std::wstring::wstring(&v54, v56);
      v24 = (__m128i *)v46[1];
      if ( v46[1] == v47 )
      {
        std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(v46, v46[1], &v54);
      }
      else
      {
        *(_OWORD *)v46[1] = v54;
        v24[1] = v55;
        v55 = si128;
        LOWORD(v54) = 0;
        v46[1] = (char *)v46[1] + 32;
      }
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(v56);
      if ( pv )
        CoTaskMemFree(pv);
      if ( *(_QWORD *)v41 )
        HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeEndpoint,void *>(v43);
      v13 += 16;
    }
    while ( v13 != v14 );
  }
  v58 = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  memset_0(&v61, 0, 0x40u);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v57[0] = 1;
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
    v66,
    v46);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(&v61, v66);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v66);
  Marshal::ToJson<Config::Network::HNS::v2::Response &,>(a2, v57);
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    if ( a2[3] <= 7u )
      v27 = a2;
    else
      v27 = (_QWORD *)*a2;
    *(_QWORD *)&v54 = v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)&word_18033EFA6,
      v25,
      v26,
      (__int64)&v54);
  }
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v61);
  std::wstring::~wstring(&v58);
  std::vector<std::wstring>::_Tidy(v46);
  std::vector<_GUID>::~vector<_GUID>(&v49);
  if ( v45 )
    CoTaskMemFree(v45);
  v28 = v44;
  if ( v44 )
  {
    if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  v29 = *(volatile signed __int32 **)(a3 + 8);
  if ( v29 )
  {
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
      if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1801a82fc  mov     rax, rsp
0x1801a82ff  push    rbp
0x1801a8300  push    rbx
0x1801a8301  push    rsi
0x1801a8302  push    rdi
0x1801a8303  push    r12
0x1801a8305  push    r13
0x1801a8307  push    r14
0x1801a8309  push    r15
0x1801a830b  lea     rbp, [rax-138h]
0x1801a8312  sub     rsp, 1F8h
0x1801a8319  movaps  xmmword ptr [rax-58h], xmm6
0x1801a831d  mov     rax, cs:__security_cookie
0x1801a8324  xor     rax, rsp
0x1801a8327  mov     [rbp+130h+var_60], rax
0x1801a832e  mov     rbx, r9
0x1801a8331  mov     r15, r8
0x1801a8334  mov     rdi, rdx
0x1801a8337  mov     rsi, rcx
0x1801a833a  mov     qword ptr [rbp+130h+var_150], rdx
0x1801a833e  mov     [rbp+130h+var_170], r8
0x1801a8342  mov     r12, [rbp+130h+arg_20]
0x1801a8349  mov     dword ptr [rsp+230h+pv], 1
0x1801a8351  mov     edx, 13Ch; unsigned int
0x1801a8356  lea     rcx, aHnsServiceRequ_3; "HNS::Service::Request::RequestManager::"...
0x1801a835d  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801a8362  xor     r13d, r13d
0x1801a8365  cmp     [rbx], r13w
0x1801a8369  jz      short loc_1801A8390
0x1801a836b  cmp     word ptr [rbx], 2Fh ; '/'
0x1801a836f  jnz     short loc_1801A8378
0x1801a8371  cmp     [rbx+2], r13w
0x1801a8376  jz      short loc_1801A8390
0x1801a8378  mov     rdx, rbx
0x1801a837b  lea     rcx, aAll_1; "/all"
0x1801a8382  call    cs:__imp__o__wcsicmp
0x1801a8388  test    eax, eax
0x1801a838a  jnz     loc_1801A88E4
0x1801a8390  mov     rcx, cs:qword_18039BB28
0x1801a8397  mov     eax, [rcx]
0x1801a8399  cmp     eax, 4
0x1801a839c  jbe     short loc_1801A83C4
0x1801a839e  lea     rax, [rbp+130h+var_A0]
0x1801a83a5  mov     [rsp+230h+var_208], rax
0x1801a83aa  mov     [rsp+230h+var_210], 2
0x1801a83b2  xor     r9d, r9d
0x1801a83b5  xor     r8d, r8d
0x1801a83b8  lea     rdx, word_18033EE42
0x1801a83bf  call    _tlgWriteTransfer_EventWriteTransfer
0x1801a83c4  lea     rdx, [rsp+230h+var_1E0]
0x1801a83c9  mov     rcx, rsi
0x1801a83cc  call    ?GetWcnAgentManager@RequestManager@Request@Service@HNS@@QEAA?AV?$shared_ptr@VWcnAgentManager@Core@Service@HNS@@@std@@XZ; HNS::Service::Request::RequestManager::GetWcnAgentManager(void)
0x1801a83d1  nop
0x1801a83d2  mov     rax, [rsp+230h+var_1E0]
0x1801a83d7  mov     rcx, [rax+80h]
0x1801a83de  cmp     [rcx+88h], r13
0x1801a83e5  setz    al
0x1801a83e8  mov     rcx, [rbp+138h]; this
0x1801a83ef  lea     rdx, aHandlegetcallE; "HandleGetCall - Enumerate function not "...
0x1801a83f6  mov     [rsp+230h+var_208], rdx; bool
0x1801a83fb  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a83ff  mov     r14d, 803B0015h
0x1801a8405  mov     r9d, r14d; char *
0x1801a8408  lea     rsi, aOnecoreVmDvNet_121; "onecore\\vm\\dv\\net\\hns\\service\\req"...
0x1801a840f  mov     r8, rsi; unsigned int
0x1801a8412  mov     edx, 14Bh; void *
0x1801a8417  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a841c  mov     rax, [rsp+230h+var_1E0]
0x1801a8421  mov     rcx, [rax+80h]
0x1801a8428  cmp     [rcx+98h], r13
0x1801a842f  setz    al
0x1801a8432  mov     rcx, [rbp+138h]; this
0x1801a8439  lea     rdx, aHandlegetcallO; "HandleGetCall - Open function not suppo"...
0x1801a8440  mov     [rsp+230h+var_208], rdx; bool
0x1801a8445  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a8449  mov     r9d, r14d; char *
0x1801a844c  mov     r8, rsi; unsigned int
0x1801a844f  mov     edx, 150h; void *
0x1801a8454  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8459  mov     rax, [rsp+230h+var_1E0]
0x1801a845e  mov     rcx, [rax+80h]
0x1801a8465  cmp     [rcx+0B8h], r13
0x1801a846c  setz    al
0x1801a846f  mov     rcx, [rbp+138h]; this
0x1801a8476  lea     rdx, aHandlegetcallC; "HandleGetCall - Close function not supp"...
0x1801a847d  mov     [rsp+230h+var_208], rdx; bool
0x1801a8482  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a8486  mov     r9d, r14d; char *
0x1801a8489  mov     r8, rsi; unsigned int
0x1801a848c  mov     edx, 155h; void *
0x1801a8491  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8496  mov     rax, [rsp+230h+var_1E0]
0x1801a849b  mov     rcx, [rax+80h]
0x1801a84a2  cmp     [rcx+0A8h], r13
0x1801a84a9  setz    al
0x1801a84ac  mov     rcx, [rbp+138h]; this
0x1801a84b3  lea     rdx, aHandlegetcallQ; "HandleGetCall - Query function not supp"...
0x1801a84ba  mov     [rsp+230h+var_208], rdx; bool
0x1801a84bf  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a84c3  mov     r9d, r14d; char *
0x1801a84c6  mov     r8, rsi; unsigned int
0x1801a84c9  mov     edx, 15Ah; void *
0x1801a84ce  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a84d3  nop
0x1801a84d4  mov     [rsp+230h+var_1D0], r13
0x1801a84d9  lea     r8, [rsp+230h+var_1D0]
0x1801a84de  mov     rdx, r12
0x1801a84e1  mov     rcx, [rsp+230h+var_1E0]
0x1801a84e6  call    ??$InvokeEnumerateFunction@UHostComputeEndpoint@Schema@HNS@@@WcnAgentManager@Core@Service@HNS@@QEBAJPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeEndpoint>(ushort const *,ushort * *)
0x1801a84eb  mov     rcx, [rbp+138h]; this
0x1801a84f2  test    eax, eax
0x1801a84f4  js      loc_1801A8920
0x1801a84fa  mov     rcx, cs:qword_18039BB28
0x1801a8501  mov     eax, [rcx]
0x1801a8503  cmp     eax, 4
0x1801a8506  jbe     short loc_1801A8528
0x1801a8508  mov     rax, [rsp+230h+var_1D0]
0x1801a850d  mov     qword ptr [rsp+230h+var_1F0], rax
0x1801a8512  lea     rax, [rsp+230h+var_1F0]
0x1801a8517  mov     qword ptr [rsp+230h+var_210], rax; int
0x1801a851c  lea     rdx, byte_18033F23F
0x1801a8523  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a8528  xorps   xmm0, xmm0
0x1801a852b  movdqu  [rbp+130h+var_1A8], xmm0
0x1801a8530  mov     [rbp+130h+var_198], r13
0x1801a8534  mov     rcx, [rsp+230h+var_1D0]
0x1801a8539  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a853d  mov     rax, r12
0x1801a8540  inc     rax
0x1801a8543  cmp     [rcx+rax*2], r13w
0x1801a8548  jnz     short loc_1801A8540
0x1801a854a  mov     qword ptr [rbp+130h+var_150], rcx
0x1801a854e  mov     qword ptr [rbp+130h+var_150+8], rax
0x1801a8552  mov     r9d, 8007000Dh
0x1801a8558  lea     rdx, [rbp+130h+var_1A8]
0x1801a855c  lea     rcx, [rbp+130h+var_150]
0x1801a8560  call    ??$FromJsonThrow@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<std::vector<_GUID>,>(std::basic_string_view<ushort>,std::vector<_GUID> *,Marshal::UnmarshalFlags,long)
0x1801a8565  xorps   xmm0, xmm0
0x1801a8568  movdqu  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x1801a856e  mov     [rsp+230h+var_1B8], r13
0x1801a8573  mov     rbx, qword ptr [rbp+130h+var_1A8]
0x1801a8577  mov     r14, qword ptr [rbp+130h+var_1A8+8]
0x1801a857b  cmp     rbx, r14
0x1801a857e  jz      loc_1801A872F
0x1801a8584  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801a858c  mov     qword ptr [rsp+230h+var_1F0], r13
0x1801a8591  lea     rax, [rsp+230h+var_1F0]
0x1801a8596  mov     [rbp+130h+var_168], rax
0x1801a859a  lea     rax, [rsp+230h+var_1E0]
0x1801a859f  mov     [rbp+130h+var_160], rax
0x1801a85a3  mov     [rbp+130h+var_158], 1
0x1801a85a7  lea     r8, [rsp+230h+var_1F0]
0x1801a85ac  mov     rdx, rbx
0x1801a85af  mov     rcx, [rsp+230h+var_1E0]
0x1801a85b4  call    ??$InvokeOpenFunction@UHostComputeEndpoint@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJAEBU_GUID@@PEAPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeEndpoint,void *>(_GUID const &,void * *)
0x1801a85b9  mov     rcx, [rbp+138h]; this
0x1801a85c0  test    eax, eax
0x1801a85c2  js      loc_1801A88D3
0x1801a85c8  mov     [rsp+230h+pv], r13
0x1801a85cd  lea     r9, [rsp+230h+pv]
0x1801a85d2  lea     r8, byte_1802E2A80
0x1801a85d9  mov     rdx, qword ptr [rsp+230h+var_1F0]
0x1801a85de  mov     rcx, [rsp+230h+var_1E0]
0x1801a85e3  call    ??$InvokeQueryFunction@UHostComputeEndpoint@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAXPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeEndpoint,void *>(void *,ushort const *,ushort * *)
0x1801a85e8  mov     rcx, [rbp+138h]; this
0x1801a85ef  test    eax, eax
0x1801a85f1  js      loc_1801A8931
0x1801a85f7  mov     rcx, [rsp+230h+pv]
0x1801a85fc  mov     [rbp+130h+var_190], rcx
0x1801a8600  mov     rax, r12
0x1801a8603  inc     rax
0x1801a8606  cmp     [rcx+rax*2], r13w
0x1801a860b  jnz     short loc_1801A8603
0x1801a860d  mov     [rbp+130h+var_188], rax
0x1801a8611  lea     rdx, [rbp+130h+var_190]
0x1801a8615  lea     rcx, [rbp+130h+var_A0]
0x1801a861c  call    ??$ConvertV2ToInternalSchema@$00@Schema@HNS@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; HNS::Schema::ConvertV2ToInternalSchema<1>(std::basic_string_view<ushort> const &)
0x1801a8621  nop
0x1801a8622  cmp     qword ptr [rax+18h], 7
0x1801a8627  jbe     short loc_1801A862E
0x1801a8629  mov     rcx, [rax]
0x1801a862c  jmp     short loc_1801A8631
0x1801a862e  mov     rcx, rax
0x1801a8631  mov     [rbp+130h+var_180], rcx
0x1801a8635  mov     rax, [rax+10h]
0x1801a8639  mov     [rbp+130h+var_178], rax
0x1801a863d  lea     rdx, [rbp+130h+var_180]
0x1801a8641  lea     rcx, [rbp+130h+var_130]
0x1801a8645  call    ??$ConvertInternalToV1Schema@$00@Schema@HNS@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; HNS::Schema::ConvertInternalToV1Schema<1>(std::basic_string_view<ushort> const &)
0x1801a864a  nop
0x1801a864b  lea     rcx, [rbp+130h+var_A0]; void *
0x1801a8652  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8657  nop
0x1801a8658  mov     rcx, cs:qword_18039BB28
0x1801a865f  mov     eax, [rcx]
0x1801a8661  cmp     eax, 4
0x1801a8664  jbe     short loc_1801A869F
0x1801a8666  lea     rax, [rbp+130h+var_130]
0x1801a866a  cmp     [rbp+130h+var_118], 7
0x1801a866f  cmova   rax, [rbp+130h+var_130]
0x1801a8674  mov     [rbp+130h+var_1B0], rax
0x1801a8678  mov     rax, [rsp+230h+pv]
0x1801a867d  mov     qword ptr [rbp+130h+var_150], rax
0x1801a8681  lea     rax, [rbp+130h+var_1B0]
0x1801a8685  mov     [rsp+230h+var_208], rax
0x1801a868a  lea     rax, [rbp+130h+var_150]
0x1801a868e  mov     qword ptr [rsp+230h+var_210], rax
0x1801a8693  lea     rdx, unk_18033EF28
0x1801a869a  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801a869f  lea     rdx, [rbp+130h+var_130]
0x1801a86a3  lea     rcx, [rbp+130h+var_150]
0x1801a86a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801a86ac  nop
0x1801a86ad  mov     rdx, [rsp+230h+var_1C0]
0x1801a86b2  cmp     rdx, [rsp+230h+var_1B8]
0x1801a86b7  jz      short loc_1801A86DA
0x1801a86b9  movups  xmm0, [rbp+130h+var_150]
0x1801a86bd  movups  xmmword ptr [rdx], xmm0
0x1801a86c0  movups  xmm1, [rbp+130h+var_140]
0x1801a86c4  movups  xmmword ptr [rdx+10h], xmm1
0x1801a86c8  movdqu  [rbp+130h+var_140], xmm6
0x1801a86cd  mov     word ptr [rbp+130h+var_150], r13w
0x1801a86d2  add     [rsp+230h+var_1C0], 20h ; ' '
0x1801a86d8  jmp     short loc_1801A86E9
0x1801a86da  lea     r8, [rbp+130h+var_150]
0x1801a86de  lea     rcx, [rsp+230h+var_1D0+8]
0x1801a86e3  call    ??$_Emplace_reallocate@URawJson@Marshal@@@?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@AEAAPEAURawJson@Marshal@@QEAU23@$$QEAU23@@Z; std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(Marshal::RawJson * const,Marshal::RawJson &&)
0x1801a86e8  nop
0x1801a86e9  lea     rcx, [rbp+130h+var_150]; void *
0x1801a86ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a86f2  nop
0x1801a86f3  lea     rcx, [rbp+130h+var_130]; void *
0x1801a86f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a86fc  nop
0x1801a86fd  mov     rcx, [rsp+230h+pv]; pv
0x1801a8702  test    rcx, rcx
0x1801a8705  jz      short loc_1801A870E
0x1801a8707  call    cs:__imp_CoTaskMemFree
0x1801a870d  nop
0x1801a870e  mov     rdx, qword ptr [rsp+230h+var_1F0]
0x1801a8713  test    rdx, rdx
0x1801a8716  jz      short loc_1801A8722
0x1801a8718  mov     rcx, [rsp+230h+var_1E0]
0x1801a871d  call    ??$InvokeCloseFunction@UHostComputeEndpoint@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeEndpoint,void *>(void *)
0x1801a8722  add     rbx, 10h
0x1801a8726  cmp     rbx, r14
0x1801a8729  jnz     loc_1801A858C
0x1801a872f  xorps   xmm0, xmm0
0x1801a8732  movups  [rbp+130h+var_108], xmm0
0x1801a8736  mov     [rbp+130h+var_F8], r13
0x1801a873a  mov     [rbp+130h+var_F0], 7
0x1801a8742  mov     word ptr [rbp+130h+var_108], r13w
0x1801a8747  xor     edx, edx; Val
0x1801a8749  lea     r8d, [rdx+40h]; Size
0x1801a874d  lea     rcx, [rbp+130h+var_E8]; void *
0x1801a8751  call    memset_0
0x1801a8756  mov     [rbp+130h+var_E8], r13
0x1801a875a  xorps   xmm0, xmm0
0x1801a875d  movdqa  [rbp+130h+var_E0], xmm0
0x1801a8762  xorps   xmm1, xmm1
0x1801a8765  movdqa  [rbp+130h+var_D0], xmm1
0x1801a876a  movdqa  [rbp+130h+var_C0], xmm0
0x1801a876f  mov     [rbp+130h+var_B0], r13d
0x1801a8776  mov     [rbp+130h+var_110], 1
0x1801a877a  lea     rdx, [rsp+230h+var_1D0+8]
0x1801a877f  lea     rcx, [rbp+130h+var_A0]
0x1801a8786  call    ??$?0AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(std::vector<Marshal::RawJson> &)
0x1801a878b  lea     rdx, [rbp+130h+var_A0]
0x1801a8792  lea     rcx, [rbp+130h+var_E8]
0x1801a8796  call    ??4?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAAAEAV01@$$QEAV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> &&)
0x1801a879b  lea     rcx, [rbp+130h+var_A0]
0x1801a87a2  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a87a7  lea     rdx, [rbp+130h+var_110]
0x1801a87ab  mov     rcx, rdi
0x1801a87ae  call    ??$ToJson@AEAUResponse@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUResponse@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::Response &,>(Config::Network::HNS::v2::Response &,Marshal::MarshalFlags)
0x1801a87b3  mov     rcx, cs:qword_18039BB28
0x1801a87ba  mov     eax, [rcx]
0x1801a87bc  cmp     eax, 4
0x1801a87bf  jbe     short loc_1801A87EA
0x1801a87c1  cmp     qword ptr [rdi+18h], 7
0x1801a87c6  jbe     short loc_1801A87CD
0x1801a87c8  mov     rax, [rdi]
0x1801a87cb  jmp     short loc_1801A87D0
0x1801a87cd  mov     rax, rdi
0x1801a87d0  mov     qword ptr [rbp+130h+var_150], rax
0x1801a87d4  lea     rax, [rbp+130h+var_150]
0x1801a87d8  mov     qword ptr [rsp+230h+var_210], rax
0x1801a87dd  lea     rdx, word_18033EFA6
0x1801a87e4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a87e9  nop
0x1801a87ea  lea     rcx, [rbp+130h+var_E8]
0x1801a87ee  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a87f3  lea     rcx, [rbp+130h+var_108]; void *
0x1801a87f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a87fc  nop
0x1801a87fd  lea     rcx, [rsp+230h+var_1D0+8]
0x1801a8802  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801a8807  nop
0x1801a8808  lea     rcx, [rbp+130h+var_1A8]
0x1801a880c  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
  ... truncated ...
```
