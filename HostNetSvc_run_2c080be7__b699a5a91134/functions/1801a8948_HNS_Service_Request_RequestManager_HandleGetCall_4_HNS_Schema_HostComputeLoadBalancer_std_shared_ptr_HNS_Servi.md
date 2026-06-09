# HNS::Service::Request::RequestManager::HandleGetCall<4,HNS::Schema::HostComputeLoadBalancer>(std::shared_ptr<HNS::Service::Request::BaseRequest>,ushort const *,ushort const *)

- ea: `0x1801a8948`
- end: `0x1801a8f8e`
- name: `??$HandleGetCall@$03UHostComputeLoadBalancer@Schema@HNS@@@RequestManager@Request@Service@HNS@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VBaseRequest@Request@Service@HNS@@@5@PEBG1@Z`
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
- `0x180067c00`
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
- `0x1801a4e8c`
- `0x1801a6bf0`
- `0x1801a8948`
- `0x1801a9600`
- `0x1801a96e4`
- `0x1801a97ac`
- `0x1801a9878`
- `0x1801a9e18`
- `0x1801ab518`
- `0x1801ae5d0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a89ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a89ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8e68`

## string_xrefs

- `0x1801a8a54`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a8f5a`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a89a2`: `HNS::Service::Request::RequestManager::HandleGetCall`
- `0x1801a8a85`: `HandleGetCall - Open function not supported for object`
- `0x1801a8f4e`: `HandleGetCall via WcnAgent failed %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall HNS::Service::Request::RequestManager::HandleGetCall<4,HNS::Schema::HostComputeLoadBalancer>(
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
  _QWORD *v20; // rdx
  int v21; // r8d
  int v22; // r9d
  __int128 *v23; // rax
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
  __int128 *v48; // [rsp+88h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-78h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-68h]
  _QWORD v51[5]; // [rsp+A8h] [rbp-60h] BYREF
  char v52; // [rsp+D0h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v54; // [rsp+E8h] [rbp-20h]
  __int128 v55; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v56; // [rsp+108h] [rbp+0h]
  char v57[8]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v58; // [rsp+120h] [rbp+18h] BYREF
  __int64 v59; // [rsp+130h] [rbp+28h]
  __int64 v60; // [rsp+138h] [rbp+30h]
  __int64 v61; // [rsp+140h] [rbp+38h] BYREF
  __int128 v62; // [rsp+148h] [rbp+40h]
  __int128 v63; // [rsp+158h] [rbp+50h]
  __int128 v64; // [rsp+168h] [rbp+60h]
  int v65; // [rsp+178h] [rbp+70h]
  _BYTE v66[64]; // [rsp+188h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+230h] [rbp+128h]

  *(_QWORD *)&v53 = a2;
  v51[2] = a3;
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
    tlgWriteTransfer_EventWriteTransfer(qword_18039BB28, &dword_18033EF7C, 0, 0, 2, v66);
  HNS::Service::Request::RequestManager::GetWcnAgentManager(a1, &v43);
  LOBYTE(v32) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 192LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x14B,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v32,
    (bool)"HandleGetCall - Enumerate function not supported for object",
    v37);
  LOBYTE(v33) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 208LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x150,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v33,
    (bool)"HandleGetCall - Open function not supported for object",
    v38);
  LOBYTE(v34) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 240LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x155,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v34,
    (bool)"HandleGetCall - Close function not supported for object",
    v39);
  LOBYTE(v35) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 224LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x15A,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v35,
    (bool)"HandleGetCall - Query function not supported for object",
    v40);
  v45 = 0;
  v9 = HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeLoadBalancer>(v43, a5, &v45);
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
      (unsigned int)&unk_18033EFE0,
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
  *(_QWORD *)&v53 = v45;
  *((_QWORD *)&v53 + 1) = v12;
  Marshal::FromJsonThrow<std::vector<_GUID>,>(&v53, &v49, v10, 2147942413LL);
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
      v51[3] = v41;
      v51[4] = &v43;
      v52 = 1;
      v16 = HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeLoadBalancer,void *>(
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
      v17 = HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeLoadBalancer,void *>(
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
      v19 = (_QWORD *)HNS::Schema::ConvertV2ToInternalSchema<4>(v66, v51);
      if ( v19[3] <= 7u )
        v20 = v19;
      else
        v20 = (_QWORD *)*v19;
      v55 = 0;
      v56 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v55, v20);
      std::wstring::~wstring(v66);
      if ( *(_DWORD *)qword_18039BB28 > 4u )
      {
        v23 = &v55;
        if ( *((_QWORD *)&v56 + 1) > 7u )
          v23 = (__int128 *)v55;
        v48 = v23;
        *(_QWORD *)&v53 = pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_18039BB28,
          (unsigned int)byte_18033F19B,
          v21,
          v22,
          (__int64)&v53,
          (__int64)&v48);
      }
      std::wstring::wstring(&v53, &v55);
      v24 = (__m128i *)v46[1];
      if ( v46[1] == v47 )
      {
        std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(v46, v46[1], &v53);
      }
      else
      {
        *(_OWORD *)v46[1] = v53;
        v24[1] = v54;
        v54 = si128;
        LOWORD(v53) = 0;
        v46[1] = (char *)v46[1] + 32;
      }
      std::wstring::~wstring(&v53);
      std::wstring::~wstring(&v55);
      if ( pv )
        CoTaskMemFree(pv);
      if ( *(_QWORD *)v41 )
        HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeLoadBalancer,void *>(v43);
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
    *(_QWORD *)&v53 = v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)byte_18033F161,
      v25,
      v26,
      (__int64)&v53);
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
0x1801a8948  mov     rax, rsp
0x1801a894b  push    rbp
0x1801a894c  push    rbx
0x1801a894d  push    rsi
0x1801a894e  push    rdi
0x1801a894f  push    r12
0x1801a8951  push    r13
0x1801a8953  push    r14
0x1801a8955  push    r15
0x1801a8957  lea     rbp, [rax-128h]
0x1801a895e  sub     rsp, 1E8h
0x1801a8965  movaps  xmmword ptr [rax-58h], xmm6
0x1801a8969  mov     rax, cs:__security_cookie
0x1801a8970  xor     rax, rsp
0x1801a8973  mov     [rbp+120h+var_60], rax
0x1801a897a  mov     rbx, r9
0x1801a897d  mov     r15, r8
0x1801a8980  mov     rdi, rdx
0x1801a8983  mov     rsi, rcx
0x1801a8986  mov     qword ptr [rbp+120h+var_150], rdx
0x1801a898a  mov     [rbp+120h+var_170], r8
0x1801a898e  mov     r12, [rbp+120h+arg_20]
0x1801a8995  mov     dword ptr [rsp+220h+pv], 1
0x1801a899d  mov     edx, 13Ch; unsigned int
0x1801a89a2  lea     rcx, aHnsServiceRequ_3; "HNS::Service::Request::RequestManager::"...
0x1801a89a9  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801a89ae  xor     r13d, r13d
0x1801a89b1  cmp     [rbx], r13w
0x1801a89b5  jz      short loc_1801A89DC
0x1801a89b7  cmp     word ptr [rbx], 2Fh ; '/'
0x1801a89bb  jnz     short loc_1801A89C4
0x1801a89bd  cmp     [rbx+2], r13w
0x1801a89c2  jz      short loc_1801A89DC
0x1801a89c4  mov     rdx, rbx
0x1801a89c7  lea     rcx, aAll_1; "/all"
0x1801a89ce  call    cs:__imp__o__wcsicmp
0x1801a89d4  test    eax, eax
0x1801a89d6  jnz     loc_1801A8F30
0x1801a89dc  mov     rcx, cs:qword_18039BB28
0x1801a89e3  mov     eax, [rcx]
0x1801a89e5  cmp     eax, 4
0x1801a89e8  jbe     short loc_1801A8A10
0x1801a89ea  lea     rax, [rbp+120h+var_A0]
0x1801a89f1  mov     [rsp+220h+var_1F8], rax
0x1801a89f6  mov     [rsp+220h+var_200], 2
0x1801a89fe  xor     r9d, r9d
0x1801a8a01  xor     r8d, r8d
0x1801a8a04  lea     rdx, dword_18033EF7C
0x1801a8a0b  call    _tlgWriteTransfer_EventWriteTransfer
0x1801a8a10  lea     rdx, [rsp+220h+var_1D0]
0x1801a8a15  mov     rcx, rsi
0x1801a8a18  call    ?GetWcnAgentManager@RequestManager@Request@Service@HNS@@QEAA?AV?$shared_ptr@VWcnAgentManager@Core@Service@HNS@@@std@@XZ; HNS::Service::Request::RequestManager::GetWcnAgentManager(void)
0x1801a8a1d  nop
0x1801a8a1e  mov     rax, [rsp+220h+var_1D0]
0x1801a8a23  mov     rcx, [rax+80h]
0x1801a8a2a  cmp     [rcx+0C0h], r13
0x1801a8a31  setz    al
0x1801a8a34  mov     rcx, [rbp+128h]; this
0x1801a8a3b  lea     rdx, aHandlegetcallE; "HandleGetCall - Enumerate function not "...
0x1801a8a42  mov     [rsp+220h+var_1F8], rdx; bool
0x1801a8a47  mov     byte ptr [rsp+220h+var_200], al; int
0x1801a8a4b  mov     r14d, 803B0015h
0x1801a8a51  mov     r9d, r14d; char *
0x1801a8a54  lea     rsi, aOnecoreVmDvNet_121; "onecore\\vm\\dv\\net\\hns\\service\\req"...
0x1801a8a5b  mov     r8, rsi; unsigned int
0x1801a8a5e  mov     edx, 14Bh; void *
0x1801a8a63  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8a68  mov     rax, [rsp+220h+var_1D0]
0x1801a8a6d  mov     rcx, [rax+80h]
0x1801a8a74  cmp     [rcx+0D0h], r13
0x1801a8a7b  setz    al
0x1801a8a7e  mov     rcx, [rbp+128h]; this
0x1801a8a85  lea     rdx, aHandlegetcallO; "HandleGetCall - Open function not suppo"...
0x1801a8a8c  mov     [rsp+220h+var_1F8], rdx; bool
0x1801a8a91  mov     byte ptr [rsp+220h+var_200], al; int
0x1801a8a95  mov     r9d, r14d; char *
0x1801a8a98  mov     r8, rsi; unsigned int
0x1801a8a9b  mov     edx, 150h; void *
0x1801a8aa0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8aa5  mov     rax, [rsp+220h+var_1D0]
0x1801a8aaa  mov     rcx, [rax+80h]
0x1801a8ab1  cmp     [rcx+0F0h], r13
0x1801a8ab8  setz    al
0x1801a8abb  mov     rcx, [rbp+128h]; this
0x1801a8ac2  lea     rdx, aHandlegetcallC; "HandleGetCall - Close function not supp"...
0x1801a8ac9  mov     [rsp+220h+var_1F8], rdx; bool
0x1801a8ace  mov     byte ptr [rsp+220h+var_200], al; int
0x1801a8ad2  mov     r9d, r14d; char *
0x1801a8ad5  mov     r8, rsi; unsigned int
0x1801a8ad8  mov     edx, 155h; void *
0x1801a8add  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8ae2  mov     rax, [rsp+220h+var_1D0]
0x1801a8ae7  mov     rcx, [rax+80h]
0x1801a8aee  cmp     [rcx+0E0h], r13
0x1801a8af5  setz    al
0x1801a8af8  mov     rcx, [rbp+128h]; this
0x1801a8aff  lea     rdx, aHandlegetcallQ; "HandleGetCall - Query function not supp"...
0x1801a8b06  mov     [rsp+220h+var_1F8], rdx; bool
0x1801a8b0b  mov     byte ptr [rsp+220h+var_200], al; int
0x1801a8b0f  mov     r9d, r14d; char *
0x1801a8b12  mov     r8, rsi; unsigned int
0x1801a8b15  mov     edx, 15Ah; void *
0x1801a8b1a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a8b1f  nop
0x1801a8b20  mov     [rsp+220h+var_1C0], r13
0x1801a8b25  lea     r8, [rsp+220h+var_1C0]
0x1801a8b2a  mov     rdx, r12
0x1801a8b2d  mov     rcx, [rsp+220h+var_1D0]
0x1801a8b32  call    ??$InvokeEnumerateFunction@UHostComputeLoadBalancer@Schema@HNS@@@WcnAgentManager@Core@Service@HNS@@QEBAJPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeLoadBalancer>(ushort const *,ushort * *)
0x1801a8b37  mov     rcx, [rbp+128h]; this
0x1801a8b3e  test    eax, eax
0x1801a8b40  js      loc_1801A8F6C
0x1801a8b46  mov     rcx, cs:qword_18039BB28
0x1801a8b4d  mov     eax, [rcx]
0x1801a8b4f  cmp     eax, 4
0x1801a8b52  jbe     short loc_1801A8B74
0x1801a8b54  mov     rax, [rsp+220h+var_1C0]
0x1801a8b59  mov     qword ptr [rsp+220h+var_1E0], rax
0x1801a8b5e  lea     rax, [rsp+220h+var_1E0]
0x1801a8b63  mov     qword ptr [rsp+220h+var_200], rax; int
0x1801a8b68  lea     rdx, unk_18033EFE0
0x1801a8b6f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a8b74  xorps   xmm0, xmm0
0x1801a8b77  movdqu  [rbp+120h+var_198], xmm0
0x1801a8b7c  mov     [rbp+120h+var_188], r13
0x1801a8b80  mov     rcx, [rsp+220h+var_1C0]
0x1801a8b85  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a8b89  mov     rax, r12
0x1801a8b8c  inc     rax
0x1801a8b8f  cmp     [rcx+rax*2], r13w
0x1801a8b94  jnz     short loc_1801A8B8C
0x1801a8b96  mov     qword ptr [rbp+120h+var_150], rcx
0x1801a8b9a  mov     qword ptr [rbp+120h+var_150+8], rax
0x1801a8b9e  mov     r9d, 8007000Dh
0x1801a8ba4  lea     rdx, [rbp+120h+var_198]
0x1801a8ba8  lea     rcx, [rbp+120h+var_150]
0x1801a8bac  call    ??$FromJsonThrow@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<std::vector<_GUID>,>(std::basic_string_view<ushort>,std::vector<_GUID> *,Marshal::UnmarshalFlags,long)
0x1801a8bb1  xorps   xmm0, xmm0
0x1801a8bb4  movdqu  xmmword ptr [rsp+220h+var_1C0+8], xmm0
0x1801a8bba  mov     [rsp+220h+var_1A8], r13
0x1801a8bbf  mov     rbx, qword ptr [rbp+120h+var_198]
0x1801a8bc3  mov     r14, qword ptr [rbp+120h+var_198+8]
0x1801a8bc7  cmp     rbx, r14
0x1801a8bca  jz      loc_1801A8D7E
0x1801a8bd0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801a8bd8  mov     qword ptr [rsp+220h+var_1E0], r13
0x1801a8bdd  lea     rax, [rsp+220h+var_1E0]
0x1801a8be2  mov     [rbp+120h+var_168], rax
0x1801a8be6  lea     rax, [rsp+220h+var_1D0]
0x1801a8beb  mov     [rbp+120h+var_160], rax
0x1801a8bef  mov     [rbp+120h+var_158], 1
0x1801a8bf3  lea     r8, [rsp+220h+var_1E0]
0x1801a8bf8  mov     rdx, rbx
0x1801a8bfb  mov     rcx, [rsp+220h+var_1D0]
0x1801a8c00  call    ??$InvokeOpenFunction@UHostComputeLoadBalancer@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJAEBU_GUID@@PEAPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeLoadBalancer,void *>(_GUID const &,void * *)
0x1801a8c05  mov     rcx, [rbp+128h]; this
0x1801a8c0c  test    eax, eax
0x1801a8c0e  js      loc_1801A8F1F
0x1801a8c14  mov     [rsp+220h+pv], r13
0x1801a8c19  lea     r9, [rsp+220h+pv]
0x1801a8c1e  lea     r8, byte_1802E2A80
0x1801a8c25  mov     rdx, qword ptr [rsp+220h+var_1E0]
0x1801a8c2a  mov     rcx, [rsp+220h+var_1D0]
0x1801a8c2f  call    ??$InvokeQueryFunction@UHostComputeLoadBalancer@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAXPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeLoadBalancer,void *>(void *,ushort const *,ushort * *)
0x1801a8c34  mov     rcx, [rbp+128h]; this
0x1801a8c3b  test    eax, eax
0x1801a8c3d  js      loc_1801A8F7D
0x1801a8c43  mov     rcx, [rsp+220h+pv]
0x1801a8c48  mov     [rbp+120h+var_180], rcx
0x1801a8c4c  mov     rax, r12
0x1801a8c4f  inc     rax
0x1801a8c52  cmp     [rcx+rax*2], r13w
0x1801a8c57  jnz     short loc_1801A8C4F
0x1801a8c59  mov     [rbp+120h+var_178], rax
0x1801a8c5d  lea     rdx, [rbp+120h+var_180]
0x1801a8c61  lea     rcx, [rbp+120h+var_A0]
0x1801a8c68  call    ??$ConvertV2ToInternalSchema@$03@Schema@HNS@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; HNS::Schema::ConvertV2ToInternalSchema<4>(std::basic_string_view<ushort> const &)
0x1801a8c6d  nop
0x1801a8c6e  cmp     qword ptr [rax+18h], 7
0x1801a8c73  jbe     short loc_1801A8C7A
0x1801a8c75  mov     rdx, [rax]
0x1801a8c78  jmp     short loc_1801A8C7D
0x1801a8c7a  mov     rdx, rax
0x1801a8c7d  mov     r8, [rax+10h]
0x1801a8c81  xorps   xmm0, xmm0
0x1801a8c84  movups  [rbp+120h+var_130], xmm0
0x1801a8c88  xorps   xmm1, xmm1
0x1801a8c8b  movdqu  [rbp+120h+var_120], xmm1
0x1801a8c90  lea     rcx, [rbp+120h+var_130]
0x1801a8c94  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a8c99  nop
0x1801a8c9a  lea     rcx, [rbp+120h+var_A0]; void *
0x1801a8ca1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8ca6  nop
0x1801a8ca7  mov     rcx, cs:qword_18039BB28
0x1801a8cae  mov     eax, [rcx]
0x1801a8cb0  cmp     eax, 4
0x1801a8cb3  jbe     short loc_1801A8CEE
0x1801a8cb5  lea     rax, [rbp+120h+var_130]
0x1801a8cb9  cmp     qword ptr [rbp+120h+var_120+8], 7
0x1801a8cbe  cmova   rax, qword ptr [rbp+120h+var_130]
0x1801a8cc3  mov     [rbp+120h+var_1A0], rax
0x1801a8cc7  mov     rax, [rsp+220h+pv]
0x1801a8ccc  mov     qword ptr [rbp+120h+var_150], rax
0x1801a8cd0  lea     rax, [rbp+120h+var_1A0]
0x1801a8cd4  mov     [rsp+220h+var_1F8], rax
0x1801a8cd9  lea     rax, [rbp+120h+var_150]
0x1801a8cdd  mov     qword ptr [rsp+220h+var_200], rax
0x1801a8ce2  lea     rdx, byte_18033F19B
0x1801a8ce9  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801a8cee  lea     rdx, [rbp+120h+var_130]
0x1801a8cf2  lea     rcx, [rbp+120h+var_150]
0x1801a8cf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801a8cfb  nop
0x1801a8cfc  mov     rdx, [rsp+220h+var_1B0]
0x1801a8d01  cmp     rdx, [rsp+220h+var_1A8]
0x1801a8d06  jz      short loc_1801A8D29
0x1801a8d08  movups  xmm0, [rbp+120h+var_150]
0x1801a8d0c  movups  xmmword ptr [rdx], xmm0
0x1801a8d0f  movups  xmm1, [rbp+120h+var_140]
0x1801a8d13  movups  xmmword ptr [rdx+10h], xmm1
0x1801a8d17  movdqu  [rbp+120h+var_140], xmm6
0x1801a8d1c  mov     word ptr [rbp+120h+var_150], r13w
0x1801a8d21  add     [rsp+220h+var_1B0], 20h ; ' '
0x1801a8d27  jmp     short loc_1801A8D38
0x1801a8d29  lea     r8, [rbp+120h+var_150]
0x1801a8d2d  lea     rcx, [rsp+220h+var_1C0+8]
0x1801a8d32  call    ??$_Emplace_reallocate@URawJson@Marshal@@@?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@AEAAPEAURawJson@Marshal@@QEAU23@$$QEAU23@@Z; std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(Marshal::RawJson * const,Marshal::RawJson &&)
0x1801a8d37  nop
0x1801a8d38  lea     rcx, [rbp+120h+var_150]; void *
0x1801a8d3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8d41  nop
0x1801a8d42  lea     rcx, [rbp+120h+var_130]; void *
0x1801a8d46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8d4b  nop
0x1801a8d4c  mov     rcx, [rsp+220h+pv]; pv
0x1801a8d51  test    rcx, rcx
0x1801a8d54  jz      short loc_1801A8D5D
0x1801a8d56  call    cs:__imp_CoTaskMemFree
0x1801a8d5c  nop
0x1801a8d5d  mov     rdx, qword ptr [rsp+220h+var_1E0]
0x1801a8d62  test    rdx, rdx
0x1801a8d65  jz      short loc_1801A8D71
0x1801a8d67  mov     rcx, [rsp+220h+var_1D0]
0x1801a8d6c  call    ??$InvokeCloseFunction@UHostComputeLoadBalancer@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeLoadBalancer,void *>(void *)
0x1801a8d71  add     rbx, 10h
0x1801a8d75  cmp     rbx, r14
0x1801a8d78  jnz     loc_1801A8BD8
0x1801a8d7e  xorps   xmm0, xmm0
0x1801a8d81  movups  [rbp+120h+var_108], xmm0
0x1801a8d85  mov     [rbp+120h+var_F8], r13
0x1801a8d89  mov     [rbp+120h+var_F0], 7
0x1801a8d91  mov     word ptr [rbp+120h+var_108], r13w
0x1801a8d96  xor     edx, edx; Val
0x1801a8d98  lea     r8d, [rdx+40h]; Size
0x1801a8d9c  lea     rcx, [rbp+120h+var_E8]; void *
0x1801a8da0  call    memset_0
0x1801a8da5  mov     [rbp+120h+var_E8], r13
0x1801a8da9  xorps   xmm0, xmm0
0x1801a8dac  movdqa  [rbp+120h+var_E0], xmm0
0x1801a8db1  xorps   xmm1, xmm1
0x1801a8db4  movdqa  [rbp+120h+var_D0], xmm1
0x1801a8db9  movdqa  [rbp+120h+var_C0], xmm0
0x1801a8dbe  mov     [rbp+120h+var_B0], r13d
0x1801a8dc2  mov     [rbp+120h+var_110], 1
0x1801a8dc6  lea     rdx, [rsp+220h+var_1C0+8]
0x1801a8dcb  lea     rcx, [rbp+120h+var_A0]
0x1801a8dd2  call    ??$?0AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(std::vector<Marshal::RawJson> &)
0x1801a8dd7  lea     rdx, [rbp+120h+var_A0]
0x1801a8dde  lea     rcx, [rbp+120h+var_E8]
0x1801a8de2  call    ??4?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAAAEAV01@$$QEAV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> &&)
0x1801a8de7  lea     rcx, [rbp+120h+var_A0]
0x1801a8dee  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a8df3  lea     rdx, [rbp+120h+var_110]
0x1801a8df7  mov     rcx, rdi
0x1801a8dfa  call    ??$ToJson@AEAUResponse@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUResponse@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::Response &,>(Config::Network::HNS::v2::Response &,Marshal::MarshalFlags)
0x1801a8dff  mov     rcx, cs:qword_18039BB28
0x1801a8e06  mov     eax, [rcx]
0x1801a8e08  cmp     eax, 4
0x1801a8e0b  jbe     short loc_1801A8E36
0x1801a8e0d  cmp     qword ptr [rdi+18h], 7
0x1801a8e12  jbe     short loc_1801A8E19
0x1801a8e14  mov     rax, [rdi]
0x1801a8e17  jmp     short loc_1801A8E1C
0x1801a8e19  mov     rax, rdi
0x1801a8e1c  mov     qword ptr [rbp+120h+var_150], rax
0x1801a8e20  lea     rax, [rbp+120h+var_150]
0x1801a8e24  mov     qword ptr [rsp+220h+var_200], rax
0x1801a8e29  lea     rdx, byte_18033F161
0x1801a8e30  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a8e35  nop
0x1801a8e36  lea     rcx, [rbp+120h+var_E8]
0x1801a8e3a  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a8e3f  lea     rcx, [rbp+120h+var_108]; void *
0x1801a8e43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8e48  nop
0x1801a8e49  lea     rcx, [rsp+220h+var_1C0+8]
0x1801a8e4e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801a8e53  nop
0x1801a8e54  lea     rcx, [rbp+120h+var_198]
  ... truncated ...
```
