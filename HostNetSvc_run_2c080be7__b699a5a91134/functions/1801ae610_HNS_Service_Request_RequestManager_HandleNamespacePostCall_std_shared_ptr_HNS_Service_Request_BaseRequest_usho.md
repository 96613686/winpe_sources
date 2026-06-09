# HNS::Service::Request::RequestManager::HandleNamespacePostCall(std::shared_ptr<HNS::Service::Request::BaseRequest>,ushort const *,ushort const *)

- ea: `0x1801ae610`
- end: `0x1801aef1e`
- name: `?HandleNamespacePostCall@RequestManager@Request@Service@HNS@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VBaseRequest@Request@Service@HNS@@@6@PEBG1@Z`
- size: `2318`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801af278`

## callees

- `0x180001b68`
- `0x180001c08`
- `0x18000414c`
- `0x18005f0c0`
- `0x18005f59c`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x180069b04`
- `0x18006c530`
- `0x1800759d8`
- `0x18007e864`
- `0x18007f05c`
- `0x18007f0fc`
- `0x180087cc0`
- `0x1800bcae4`
- `0x1800bdd2c`
- `0x18010161c`
- `0x180102f78`
- `0x180115760`
- `0x1801a6760`
- `0x1801a6940`
- `0x1801a962c`
- `0x1801a9748`
- `0x1801a97e0`
- `0x1801a98b0`
- `0x1801a9ab0`
- `0x1801a9d54`
- `0x1801a9e18`
- `0x1801ae5d0`
- `0x1801ae610`
- `0x180240a24`
- `0x180240a98`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ae6ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ae6dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ae6ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ae6dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aeca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aeca9`

## string_xrefs

- `0x1801ae879`: `Query function not supported for HostComputeNamespace`
- `0x1801aeede`: `HandlePostcall via WcnAgent failed %ws %ws`
- `0x1801ae805`: `Close function not supported for HostComputeNamespace`
- `0x1801ae7bc`: `Open function not supported for HostComputeNamespace`
- `0x1801ae667`: `HNS::Service::Request::RequestManager::HandleNamespacePostCall`
- `0x1801ae7d4`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801aeeea`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 *__fastcall HNS::Service::Request::RequestManager::HandleNamespacePostCall(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        _WORD *a5)
{
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdi
  int v11; // r15d
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  const char *v17; // r12
  const char *v18; // rax
  int v19; // eax
  _DWORD *v20; // rdi
  _QWORD *v21; // r8
  int v22; // eax
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  int v26; // ebx
  _DWORD *v27; // rax
  __int64 v28; // rax
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rax
  __int64 *v32; // rax
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  unsigned int v36; // eax
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  const char *v42; // [rsp+30h] [rbp-D0h]
  const char *v43; // [rsp+30h] [rbp-D0h]
  const char *v44; // [rsp+30h] [rbp-D0h]
  const char *v45; // [rsp+30h] [rbp-D0h]
  __int64 *v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v49; // [rsp+58h] [rbp-A8h]
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v51[4]; // [rsp+70h] [rbp-90h] BYREF
  char v52; // [rsp+90h] [rbp-70h]
  __int128 v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  __int128 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+E0h] [rbp-20h]
  struct _GUID v61; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v62; // [rsp+100h] [rbp+0h] BYREF
  __int64 v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int64 v65; // [rsp+120h] [rbp+20h]
  int v66; // [rsp+128h] [rbp+28h]
  int v67; // [rsp+12Ch] [rbp+2Ch]
  _OWORD v68[3]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v69; // [rsp+160h] [rbp+60h]
  int v70; // [rsp+168h] [rbp+68h]
  _QWORD v71[4]; // [rsp+170h] [rbp+70h] BYREF
  char v72[8]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v73; // [rsp+198h] [rbp+98h] BYREF
  __int64 v74; // [rsp+1A8h] [rbp+A8h]
  __int64 v75; // [rsp+1B0h] [rbp+B0h]
  __int64 v76; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v77; // [rsp+1C0h] [rbp+C0h]
  __int128 v78; // [rsp+1D0h] [rbp+D0h]
  __int128 v79; // [rsp+1E0h] [rbp+E0h]
  int v80; // [rsp+1F0h] [rbp+F0h]
  char v81[8]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v82; // [rsp+208h] [rbp+108h] BYREF
  __int64 v83; // [rsp+218h] [rbp+118h]
  __int64 v84; // [rsp+220h] [rbp+120h]
  __int64 v85; // [rsp+228h] [rbp+128h] BYREF
  __int128 v86; // [rsp+230h] [rbp+130h]
  __int128 v87; // [rsp+240h] [rbp+140h]
  __int128 v88; // [rsp+250h] [rbp+150h]
  int v89; // [rsp+260h] [rbp+160h]
  _BYTE v90[488]; // [rsp+270h] [rbp+170h] BYREF
  int v91; // [rsp+458h] [rbp+358h]
  __int128 v92; // [rsp+45Ch] [rbp+35Ch]
  char v93; // [rsp+46Ch] [rbp+36Ch]
  int v94; // [rsp+470h] [rbp+370h]
  __int64 v95; // [rsp+478h] [rbp+378h] BYREF
  __int128 v96; // [rsp+480h] [rbp+380h]
  char v97; // [rsp+490h] [rbp+390h]
  LPVOID v98; // [rsp+4A0h] [rbp+3A0h] BYREF
  _DWORD *v99; // [rsp+4A8h] [rbp+3A8h]
  __int128 v100; // [rsp+4B0h] [rbp+3B0h]
  __int128 v101; // [rsp+4C0h] [rbp+3C0h]
  __int64 (__fastcall **v102)(); // [rsp+4D0h] [rbp+3D0h]
  int v103; // [rsp+4D8h] [rbp+3D8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v51[0] = a2;
  v51[1] = a3;
  LODWORD(v46) = 1;
  HNSTraceProvider::TraceEnter("HNS::Service::Request::RequestManager::HandleNamespacePostCall", 0xC4u);
  v61 = 0;
  if ( !*(_WORD *)a4
    || *(_WORD *)a4 == 47 && !*(_WORD *)(a4 + 2)
    || !RequestPathHelper::GetPathGuid((const unsigned __int16 *)a4, &v61)
    || (v9 = RequestPathHelper::Subpath((const unsigned __int16 *)a4), (v10 = v9) == 0)
    || (v11 = _o__wcsicmp(v9, L"/attach"), v12 = _o__wcsicmp(v10, L"/detach"), v11) && v12 )
  {
    v36 = wil::verify_hresult<long>(2151350293LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)v36,
      (int)"HandlePostcall via WcnAgent failed %ws %ws",
      (const char *)a4,
      a5);
  }
  v57 = 0;
  v58 = 0;
  v59 = 7;
  LOWORD(v57) = 0;
  v60 = 0;
  v14 = -1;
  do
    ++v14;
  while ( a5[v14] );
  pv[0] = a5;
  pv[1] = (LPVOID)v14;
  Marshal::FromJsonThrow<Config::Network::HNS::v2::NamespaceAttachDetachRequest,>(pv, &v57, v13, 2147942413LL);
  v47 = 0;
  HNS::Service::Request::RequestManager::GetWcnAgentManager(a1, &v48);
  v51[2] = &v47;
  v51[3] = &v48;
  v52 = 1;
  v17 = "Attach";
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    v18 = "Attach";
    if ( v11 )
      v18 = "Detach";
    pv[0] = (LPVOID)v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      qword_18039BB28,
      (unsigned int)&byte_18033F1EF,
      v15,
      v16,
      (__int64)pv);
  }
  LOBYTE(v37) = *(_QWORD *)(*(_QWORD *)(v48 + 128) + 96LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xE7,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v37,
    (bool)"Open function not supported for HostComputeNamespace",
    v42);
  LOBYTE(v38) = *(_QWORD *)(*(_QWORD *)(v48 + 128) + 128LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xEB,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v38,
    (bool)"Close function not supported for HostComputeNamespace",
    v43);
  LOBYTE(v39) = *(_QWORD *)(*(_QWORD *)(v48 + 128) + 104LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xEF,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v39,
    (bool)"Modify function not supported for Namespace",
    v44);
  LOBYTE(v40) = *(_QWORD *)(*(_QWORD *)(v48 + 128) + 112LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xF3,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v40,
    (bool)"Query function not supported for HostComputeNamespace",
    v45);
  v19 = HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeNamespace,void *>(
          v48,
          &v61,
          &v47);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)(unsigned int)v19,
      v41);
  v53 = 0;
  v54 = 0;
  v55 = 7;
  LOWORD(v53) = 0;
  v56 = 0;
  std::wstring::operator=(&v53, &v57);
  v62 = 0;
  v63 = 0;
  v64 = 7;
  LOWORD(v62) = 0;
  v65 = 0;
  v67 = 0;
  memset_0(v68, 0, 0x40u);
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  v70 = 0;
  v66 = 0;
  v20 = operator new(0x38u);
  pv[0] = v20;
  *(_OWORD *)v20 = 0;
  v20[2] = 1;
  v20[3] = 1;
  *(_QWORD *)v20 = &std::_Ref_count_obj2<HNS::Schema::Namespace::NamespaceContainerRequest const>::`vftable';
  std::wstring::wstring(v20 + 4, &v53);
  v20[12] = v56;
  v98 = v20 + 4;
  v99 = v20;
  v100 = 0;
  v101 = 0;
  v102 = Marshal::Details::JsonTypeInfo<HNS::Schema::Namespace::NamespaceContainerRequest,>::Value;
  v103 = 0;
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(v68, &v98);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v98);
  LODWORD(v65) = v11 != 0;
  Marshal::ToJson<HNS::Schema::Namespace::ModifyNamespaceSettingRequest &,>(v71, &v62);
  if ( *(_DWORD *)qword_18039BB28 > 4u )
    tlgWriteTransfer_EventWriteTransfer(qword_18039BB28, byte_18033F01B, 0, 0, 2, &v98);
  v21 = v71;
  if ( v71[3] > 7u )
    v21 = (_QWORD *)v71[0];
  v22 = HNS::Service::Core::WcnAgentManager::InvokeModifyFunction<HNS::Schema::HostComputeNamespace,void *>(
          v48,
          v47,
          v21);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)(unsigned int)v22,
      v41);
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  LODWORD(v46) = 3;
  if ( v11 )
  {
    v82 = 0;
    v83 = 0;
    v84 = 7;
    LOWORD(v82) = 0;
    memset_0(&v85, 0, 0x40u);
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    v81[0] = 1;
    v31 = Marshal::ToJson<Config::Network::HNS::Internal::Response &,>(&v98, v81);
    std::wstring::operator=(a2, v31);
    std::wstring::~wstring(&v98);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v85);
    std::wstring::~wstring(&v82);
  }
  else
  {
    pv[0] = 0;
    v23 = HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeNamespace,void *>(
            v48,
            v47,
            0,
            pv);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
        (const char *)(unsigned int)v23,
        v41);
    if ( *(_DWORD *)qword_18039BB28 > 4u )
      tlgWriteTransfer_EventWriteTransfer(qword_18039BB28, byte_18033F079, 0, 0, 2, &v98);
    HNS::Schema::Common::Base::Base((HNS::Schema::Common::Base *)v90);
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)pv[0] + v25) );
    v98 = pv[0];
    v99 = (_DWORD *)v25;
    Marshal::FromJsonThrow<HNS::Schema::HostComputeNamespace,>(&v98, v90, v24, 2147942413LL);
    v73 = 0;
    v74 = 0;
    v75 = 7;
    LOWORD(v73) = 0;
    memset_0(&v76, 0, 0x40u);
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v72[0] = 1;
    v26 = v91;
    v27 = operator new(0x18u);
    HIDWORD(v46) = HIDWORD(v27);
    *(_OWORD *)v27 = 0;
    v27[2] = 1;
    v27[3] = 1;
    *(_QWORD *)v27 = &std::_Ref_count_obj2<Config::Network::HNS::v2::NamespaceAttachResponse const>::`vftable';
    v27[4] = v26;
    LODWORD(v46) = 7;
    v98 = v27 + 4;
    v99 = v27;
    v100 = 0;
    v101 = 0;
    v102 = Marshal::Details::JsonTypeInfo<Config::Network::HNS::v2::NamespaceAttachResponse,>::Value;
    v103 = 0;
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(&v76, &v98);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v98);
    v28 = Marshal::ToJson<Config::Network::HNS::v2::Response &,>(&v98, v72);
    std::wstring::operator=(a2, v28);
    std::wstring::~wstring(&v98);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v76);
    std::wstring::~wstring(&v73);
    std::vector<HNS::Schema::Network::Endpoint::EndpointPolicy>::_Tidy(&v95);
    HNS::Schema::Common::Base::~Base((HNS::Schema::Common::Base *)v90);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
  }
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v32 = a2;
    else
      v32 = (__int64 *)*a2;
    v46 = v32;
    if ( v11 )
      v17 = "Detach";
    v51[0] = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)&byte_18033F0CF,
      v29,
      v30,
      (__int64)v51,
      (__int64)&v46);
  }
  std::wstring::~wstring(v71);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v68);
  std::wstring::~wstring(&v62);
  std::wstring::~wstring(&v53);
  if ( v47 && *(_QWORD *)(*(_QWORD *)(v48 + 128) + 128LL) )
    HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeNamespace,void *>();
  v33 = v49;
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  std::wstring::~wstring(&v57);
  v34 = *(volatile signed __int32 **)(a3 + 8);
  if ( v34 )
  {
    if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1801ae610  push    rbp
0x1801ae612  push    rbx
0x1801ae613  push    rsi
0x1801ae614  push    rdi
0x1801ae615  push    r12
0x1801ae617  push    r13
0x1801ae619  push    r14
0x1801ae61b  push    r15
0x1801ae61d  lea     rbp, [rsp-3F8h]
0x1801ae625  sub     rsp, 4F8h
0x1801ae62c  mov     rax, cs:__security_cookie
0x1801ae633  xor     rax, rsp
0x1801ae636  mov     [rbp+430h+var_50], rax
0x1801ae63d  mov     rbx, r9
0x1801ae640  mov     r13, r8
0x1801ae643  mov     rsi, rdx
0x1801ae646  mov     r12, rcx
0x1801ae649  mov     [rsp+530h+var_4C0], rdx
0x1801ae64e  mov     [rsp+530h+var_4B8], r8
0x1801ae653  mov     r14, [rbp+430h+arg_20]
0x1801ae65a  mov     dword ptr [rsp+530h+var_4F0], 1
0x1801ae662  mov     edx, 0C4h; unsigned int
0x1801ae667  lea     rcx, aHnsServiceRequ_7; "HNS::Service::Request::RequestManager::"...
0x1801ae66e  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801ae673  xorps   xmm0, xmm0
0x1801ae676  movups  xmmword ptr [rbp+430h+var_448.Data1], xmm0
0x1801ae67a  xor     r15d, r15d
0x1801ae67d  cmp     [rbx], r15w
0x1801ae681  jz      loc_1801AEEC0
0x1801ae687  cmp     word ptr [rbx], 2Fh ; '/'
0x1801ae68b  jnz     short loc_1801AE698
0x1801ae68d  cmp     [rbx+2], r15w
0x1801ae692  jz      loc_1801AEEC0
0x1801ae698  lea     rdx, [rbp+430h+var_448]; struct _GUID *
0x1801ae69c  mov     rcx, rbx; unsigned __int16 *
0x1801ae69f  call    ?GetPathGuid@RequestPathHelper@@SA_NPEBGPEAU_GUID@@@Z; RequestPathHelper::GetPathGuid(ushort const *,_GUID *)
0x1801ae6a4  test    al, al
0x1801ae6a6  jz      loc_1801AEEC0
0x1801ae6ac  mov     rcx, rbx; unsigned __int16 *
0x1801ae6af  call    ?Subpath@RequestPathHelper@@SAPEBGPEBG@Z; RequestPathHelper::Subpath(ushort const *)
0x1801ae6b4  mov     rdi, rax
0x1801ae6b7  test    rax, rax
0x1801ae6ba  jz      loc_1801AEEC0
0x1801ae6c0  lea     rdx, aAttach_0; "/attach"
0x1801ae6c7  mov     rcx, rax
0x1801ae6ca  call    cs:__imp__o__wcsicmp
0x1801ae6d0  mov     r15d, eax
0x1801ae6d3  lea     rdx, aDetach; "/detach"
0x1801ae6da  mov     rcx, rdi
0x1801ae6dd  call    cs:__imp__o__wcsicmp
0x1801ae6e3  test    r15d, r15d
0x1801ae6e6  jz      short loc_1801AE6F0
0x1801ae6e8  test    eax, eax
0x1801ae6ea  jnz     loc_1801AEEC0
0x1801ae6f0  xorps   xmm0, xmm0
0x1801ae6f3  movups  [rbp+430h+var_470], xmm0
0x1801ae6f7  xor     ebx, ebx
0x1801ae6f9  mov     [rbp+430h+var_460], rbx
0x1801ae6fd  mov     [rbp+430h+var_458], 7
0x1801ae705  mov     word ptr [rbp+430h+var_470], bx
0x1801ae709  mov     [rbp+430h+var_450], ebx
0x1801ae70c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ae710  inc     rax
0x1801ae713  cmp     [r14+rax*2], bx
0x1801ae718  jnz     short loc_1801AE710
0x1801ae71a  mov     [rsp+530h+pv], r14
0x1801ae71f  mov     [rsp+530h+var_4C8], rax
0x1801ae724  mov     r9d, 8007000Dh
0x1801ae72a  lea     rdx, [rbp+430h+var_470]
0x1801ae72e  lea     rcx, [rsp+530h+pv]
0x1801ae733  call    ??$FromJsonThrow@UNamespaceAttachDetachRequest@v2@HNS@Network@Config@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUNamespaceAttachDetachRequest@v2@HNS@Network@Config@@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<Config::Network::HNS::v2::NamespaceAttachDetachRequest,>(std::basic_string_view<ushort>,Config::Network::HNS::v2::NamespaceAttachDetachRequest *,Marshal::UnmarshalFlags,long)
0x1801ae738  mov     [rsp+530h+var_4E8], rbx
0x1801ae73d  lea     rdx, [rsp+530h+var_4E0]
0x1801ae742  mov     rcx, r12
0x1801ae745  call    ?GetWcnAgentManager@RequestManager@Request@Service@HNS@@QEAA?AV?$shared_ptr@VWcnAgentManager@Core@Service@HNS@@@std@@XZ; HNS::Service::Request::RequestManager::GetWcnAgentManager(void)
0x1801ae74a  nop
0x1801ae74b  lea     rax, [rsp+530h+var_4E8]
0x1801ae750  mov     [rbp+430h+var_4B0], rax
0x1801ae754  lea     rax, [rsp+530h+var_4E0]
0x1801ae759  mov     [rbp+430h+var_4A8], rax
0x1801ae75d  mov     [rbp+430h+var_4A0], 1
0x1801ae761  mov     rcx, cs:qword_18039BB28
0x1801ae768  mov     eax, [rcx]
0x1801ae76a  lea     rdx, aDetach_0; "Detach"
0x1801ae771  lea     r12, aAttach; "Attach"
0x1801ae778  cmp     eax, 4
0x1801ae77b  jbe     short loc_1801AE7A2
0x1801ae77d  mov     rax, r12
0x1801ae780  test    r15d, r15d
0x1801ae783  cmovnz  rax, rdx
0x1801ae787  mov     [rsp+530h+pv], rax
0x1801ae78c  lea     rax, [rsp+530h+pv]
0x1801ae791  mov     qword ptr [rsp+530h+var_510], rax
0x1801ae796  lea     rdx, byte_18033F1EF
0x1801ae79d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801ae7a2  mov     rax, [rsp+530h+var_4E0]
0x1801ae7a7  mov     rcx, [rax+80h]
0x1801ae7ae  cmp     [rcx+60h], rbx
0x1801ae7b2  setz    al
0x1801ae7b5  mov     rcx, [rbp+438h]; this
0x1801ae7bc  lea     rdx, aOpenFunctionNo; "Open function not supported for HostCom"...
0x1801ae7c3  mov     [rsp+530h+var_508], rdx; bool
0x1801ae7c8  mov     byte ptr [rsp+530h+var_510], al; int
0x1801ae7cc  mov     edi, 803B0015h
0x1801ae7d1  mov     r9d, edi; char *
0x1801ae7d4  lea     r14, aOnecoreVmDvNet_121; "onecore\\vm\\dv\\net\\hns\\service\\req"...
0x1801ae7db  mov     r8, r14; unsigned int
0x1801ae7de  mov     edx, 0E7h; void *
0x1801ae7e3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801ae7e8  mov     rax, [rsp+530h+var_4E0]
0x1801ae7ed  mov     rcx, [rax+80h]
0x1801ae7f4  cmp     [rcx+80h], rbx
0x1801ae7fb  setz    al
0x1801ae7fe  mov     rcx, [rbp+438h]; this
0x1801ae805  lea     rdx, aCloseFunctionN; "Close function not supported for HostCo"...
0x1801ae80c  mov     [rsp+530h+var_508], rdx; bool
0x1801ae811  mov     byte ptr [rsp+530h+var_510], al; int
0x1801ae815  mov     r9d, edi; char *
0x1801ae818  mov     r8, r14; unsigned int
0x1801ae81b  mov     edx, 0EBh; void *
0x1801ae820  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801ae825  mov     rax, [rsp+530h+var_4E0]
0x1801ae82a  mov     rcx, [rax+80h]
0x1801ae831  cmp     [rcx+68h], rbx
0x1801ae835  setz    al
0x1801ae838  mov     rcx, [rbp+438h]; this
0x1801ae83f  lea     rdx, aModifyFunction; "Modify function not supported for Names"...
0x1801ae846  mov     [rsp+530h+var_508], rdx; bool
0x1801ae84b  mov     byte ptr [rsp+530h+var_510], al; int
0x1801ae84f  mov     r9d, edi; char *
0x1801ae852  mov     r8, r14; unsigned int
0x1801ae855  mov     edx, 0EFh; void *
0x1801ae85a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801ae85f  mov     rax, [rsp+530h+var_4E0]
0x1801ae864  mov     rcx, [rax+80h]
0x1801ae86b  cmp     [rcx+70h], rbx
0x1801ae86f  setz    al
0x1801ae872  mov     rcx, [rbp+438h]; this
0x1801ae879  lea     rdx, aQueryFunctionN; "Query function not supported for HostCo"...
0x1801ae880  mov     [rsp+530h+var_508], rdx; bool
0x1801ae885  mov     byte ptr [rsp+530h+var_510], al; int
0x1801ae889  mov     r9d, edi; char *
0x1801ae88c  mov     r8, r14; unsigned int
0x1801ae88f  mov     edx, 0F3h; void *
0x1801ae894  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801ae899  lea     r8, [rsp+530h+var_4E8]
0x1801ae89e  lea     rdx, [rbp+430h+var_448]
0x1801ae8a2  mov     rcx, [rsp+530h+var_4E0]
0x1801ae8a7  call    ??$InvokeOpenFunction@UHostComputeNamespace@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJAEBU_GUID@@PEAPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeNamespace,void *>(_GUID const &,void * *)
0x1801ae8ac  mov     rcx, [rbp+438h]; this
0x1801ae8b3  test    eax, eax
0x1801ae8b5  js      loc_1801AEEFC
0x1801ae8bb  xorps   xmm0, xmm0
0x1801ae8be  movups  [rbp+430h+var_498], xmm0
0x1801ae8c2  mov     [rbp+430h+var_488], rbx
0x1801ae8c6  mov     edi, 7
0x1801ae8cb  mov     [rbp+430h+var_480], rdi
0x1801ae8cf  mov     word ptr [rbp+430h+var_498], bx
0x1801ae8d3  mov     [rbp+430h+var_478], rbx
0x1801ae8d7  lea     rdx, [rbp+430h+var_470]
0x1801ae8db  lea     rcx, [rbp+430h+var_498]
0x1801ae8df  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801ae8e4  xorps   xmm0, xmm0
0x1801ae8e7  movups  [rbp+430h+var_430], xmm0
0x1801ae8eb  mov     [rbp+430h+var_420], rbx
0x1801ae8ef  mov     [rbp+430h+var_418], rdi
0x1801ae8f3  mov     word ptr [rbp+430h+var_430], bx
0x1801ae8f7  mov     [rbp+430h+var_410], rbx
0x1801ae8fb  xor     eax, eax
0x1801ae8fd  mov     [rbp+430h+var_404], eax
0x1801ae900  xor     edx, edx; Val
0x1801ae902  lea     r8d, [rdi+39h]; Size
0x1801ae906  lea     rcx, [rbp+430h+var_400]; void *
0x1801ae90a  call    memset_0
0x1801ae90f  xorps   xmm0, xmm0
0x1801ae912  movdqa  [rbp+430h+var_400], xmm0
0x1801ae917  xorps   xmm1, xmm1
0x1801ae91a  movdqa  [rbp+430h+var_3F0], xmm1
0x1801ae91f  movdqa  [rbp+430h+var_3E0], xmm0
0x1801ae924  mov     [rbp+430h+var_3D0], rbx
0x1801ae928  mov     [rbp+430h+var_3C8], ebx
0x1801ae92b  mov     [rbp+430h+var_408], ebx
0x1801ae92e  lea     ecx, [rdi+31h]; Size
0x1801ae931  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801ae936  mov     rdi, rax
0x1801ae939  mov     [rsp+530h+pv], rax
0x1801ae93e  xorps   xmm0, xmm0
0x1801ae941  movups  xmmword ptr [rax], xmm0
0x1801ae944  mov     eax, 1
0x1801ae949  mov     [rdi+8], eax
0x1801ae94c  mov     [rdi+0Ch], eax
0x1801ae94f  lea     rax, ??_7?$_Ref_count_obj2@$$CBUNamespaceContainerRequest@Namespace@Schema@HNS@@@std@@6B@; const std::_Ref_count_obj2<HNS::Schema::Namespace::NamespaceContainerRequest const>::`vftable'
0x1801ae956  mov     [rdi], rax
0x1801ae959  lea     rbx, [rdi+10h]
0x1801ae95d  lea     rdx, [rbp+430h+var_498]
0x1801ae961  mov     rcx, rbx
0x1801ae964  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801ae969  mov     eax, dword ptr [rbp+430h+var_478]
0x1801ae96c  mov     [rbx+20h], eax
0x1801ae96f  mov     [rbp+430h+var_90], rbx
0x1801ae976  mov     [rbp+430h+var_88], rdi
0x1801ae97d  xorps   xmm0, xmm0
0x1801ae980  movdqu  [rbp+430h+var_80], xmm0
0x1801ae988  xorps   xmm1, xmm1
0x1801ae98b  movdqu  [rbp+430h+var_70], xmm1
0x1801ae993  lea     rax, ?Value@?$JsonTypeInfo@UNamespaceContainerRequest@Namespace@Schema@HNS@@$$V@Details@Marshal@@2UJsonTypeData@23@B; Marshal::Details::JsonTypeData const Marshal::Details::JsonTypeInfo<HNS::Schema::Namespace::NamespaceContainerRequest,>::Value
0x1801ae99a  mov     [rbp+430h+var_60], rax
0x1801ae9a1  xor     edi, edi
0x1801ae9a3  mov     [rbp+430h+var_58], edi
0x1801ae9a9  lea     rdx, [rbp+430h+var_90]
0x1801ae9b0  lea     rcx, [rbp+430h+var_400]
0x1801ae9b4  call    ??4?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAAAEAV01@$$QEAV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> &&)
0x1801ae9b9  lea     rcx, [rbp+430h+var_90]
0x1801ae9c0  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801ae9c5  mov     eax, edi
0x1801ae9c7  test    r15d, r15d
0x1801ae9ca  setnz   al
0x1801ae9cd  mov     dword ptr [rbp+430h+var_410], eax
0x1801ae9d0  lea     rdx, [rbp+430h+var_430]
0x1801ae9d4  lea     rcx, [rbp+430h+var_3C0]
0x1801ae9d8  call    ??$ToJson@AEAUModifyNamespaceSettingRequest@Namespace@Schema@HNS@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUModifyNamespaceSettingRequest@Namespace@Schema@HNS@@W4MarshalFlags@0@@Z; Marshal::ToJson<HNS::Schema::Namespace::ModifyNamespaceSettingRequest &,>(HNS::Schema::Namespace::ModifyNamespaceSettingRequest &,Marshal::MarshalFlags)
0x1801ae9dd  nop
0x1801ae9de  mov     rcx, cs:qword_18039BB28
0x1801ae9e5  mov     eax, [rcx]
0x1801ae9e7  cmp     eax, 4
0x1801ae9ea  jbe     short loc_1801AEA12
0x1801ae9ec  lea     rax, [rbp+430h+var_90]
0x1801ae9f3  mov     [rsp+530h+var_508], rax
0x1801ae9f8  mov     [rsp+530h+var_510], 2; int
0x1801aea00  xor     r9d, r9d
0x1801aea03  xor     r8d, r8d
0x1801aea06  lea     rdx, byte_18033F01B
0x1801aea0d  call    _tlgWriteTransfer_EventWriteTransfer
0x1801aea12  lea     r8, [rbp+430h+var_3C0]
0x1801aea16  cmp     [rbp+430h+var_3A8], 7
0x1801aea1e  cmova   r8, [rbp+430h+var_3C0]
0x1801aea23  mov     rdx, [rsp+530h+var_4E8]
0x1801aea28  mov     rcx, [rsp+530h+var_4E0]
0x1801aea2d  call    ??$InvokeModifyFunction@UHostComputeNamespace@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAXPEBG@Z; HNS::Service::Core::WcnAgentManager::InvokeModifyFunction<HNS::Schema::HostComputeNamespace,void *>(void *,ushort const *)
0x1801aea32  mov     rcx, [rbp+438h]; this
0x1801aea39  test    eax, eax
0x1801aea3b  js      loc_1801AEF0D
0x1801aea41  xorps   xmm0, xmm0
0x1801aea44  movups  xmmword ptr [rsi], xmm0
0x1801aea47  mov     [rsi+10h], rdi
0x1801aea4b  mov     ecx, 7
0x1801aea50  mov     [rsi+18h], rcx
0x1801aea54  mov     [rsi], di
0x1801aea57  lea     ebx, [rcx-4]
0x1801aea5a  mov     dword ptr [rsp+530h+var_4F0], ebx
0x1801aea5e  test    r15d, r15d
0x1801aea61  jnz     loc_1801AECB4
0x1801aea67  mov     [rsp+530h+pv], rdi
0x1801aea6c  lea     r9, [rsp+530h+pv]
0x1801aea71  xor     r8d, r8d
0x1801aea74  mov     rdx, [rsp+530h+var_4E8]
0x1801aea79  mov     rcx, [rsp+530h+var_4E0]
0x1801aea7e  call    ??$InvokeQueryFunction@UHostComputeNamespace@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAXPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeNamespace,void *>(void *,ushort const *,ushort * *)
0x1801aea83  mov     rcx, [rbp+438h]; this
0x1801aea8a  test    eax, eax
0x1801aea8c  js      loc_1801AEEAF
0x1801aea92  mov     rcx, cs:qword_18039BB28
0x1801aea99  mov     eax, [rcx]
0x1801aea9b  cmp     eax, 4
0x1801aea9e  jbe     short loc_1801AEAC6
0x1801aeaa0  lea     rax, [rbp+430h+var_90]
0x1801aeaa7  mov     [rsp+530h+var_508], rax
0x1801aeaac  mov     [rsp+530h+var_510], 2
0x1801aeab4  xor     r9d, r9d
0x1801aeab7  xor     r8d, r8d
0x1801aeaba  lea     rdx, byte_18033F079
0x1801aeac1  call    _tlgWriteTransfer_EventWriteTransfer
0x1801aeac6  lea     rcx, [rbp+430h+var_2C0]; this
0x1801aeacd  call    ??0Base@Common@Schema@HNS@@QEAA@XZ; HNS::Schema::Common::Base::Base(void)
0x1801aead2  mov     [rbp+430h+var_D8], edi
0x1801aead8  xorps   xmm2, xmm2
0x1801aeadb  movups  [rbp+430h+var_D4], xmm2
0x1801aeae2  mov     [rbp+430h+var_C4], dil
0x1801aeae9  mov     [rbp+430h+var_C0], edi
0x1801aeaef  mov     [rbp+430h+var_B8], rdi
0x1801aeaf6  xorps   xmm0, xmm0
0x1801aeaf9  movdqa  [rbp+430h+var_B0], xmm0
0x1801aeb01  mov     [rbp+430h+var_A0], dil
0x1801aeb08  mov     rcx, [rsp+530h+pv]
0x1801aeb0d  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801aeb11  mov     rax, r14
0x1801aeb14  inc     rax
0x1801aeb17  cmp     [rcx+rax*2], di
0x1801aeb1b  jnz     short loc_1801AEB14
0x1801aeb1d  mov     [rbp+430h+var_90], rcx
0x1801aeb24  mov     [rbp+430h+var_88], rax
0x1801aeb2b  mov     r9d, 8007000Dh
0x1801aeb31  lea     rdx, [rbp+430h+var_2C0]
0x1801aeb38  lea     rcx, [rbp+430h+var_90]
0x1801aeb3f  call    ??$FromJsonThrow@UHostComputeNamespace@Schema@HNS@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUHostComputeNamespace@Schema@HNS@@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<HNS::Schema::HostComputeNamespace,>(std::basic_string_view<ushort>,HNS::Schema::HostComputeNamespace *,Marshal::UnmarshalFlags,long)
0x1801aeb44  xorps   xmm0, xmm0
0x1801aeb47  movups  [rbp+430h+var_398], xmm0
0x1801aeb4e  mov     [rbp+430h+var_388], rdi
0x1801aeb55  mov     [rbp+430h+var_380], 7
0x1801aeb60  mov     word ptr [rbp+430h+var_398], di
  ... truncated ...
```
