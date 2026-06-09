# GetAclRuleFromAclObject(wil::com_ptr_t<HNSObject,wil::err_exception_policy> const &,TierAclRulePolicy const *,std::shared_ptr<HNS::Service::Network::Endpoint>,AclRule &,AclRule &,bool &)

- ea: `0x180091b14`
- end: `0x180093051`
- name: `?GetAclRuleFromAclObject@@YAXAEBV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@PEBUTierAclRulePolicy@@V?$shared_ptr@VEndpoint@Network@Service@HNS@@@std@@AEAUAclRule@@3AEA_N@Z`
- size: `5437`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801df538`
- `0x1801fd9b8`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x180067c00`
- `0x18006c530`
- `0x1800776d8`
- `0x18007e864`
- `0x18007f05c`
- `0x18007f0fc`
- `0x18007f9e8`
- `0x18008c860`
- `0x18008efc0`
- `0x18009045c`
- `0x180091b14`
- `0x1800936b0`
- `0x180094780`
- `0x18019c5ec`
- `0x18019cd40`
- `0x18019dbb4`
- `0x18019dcb8`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092299`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009236c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800923e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800924bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009252f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800925a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092b6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092299`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009236c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800923e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800924bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009252f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800925a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092b6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180092a0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180092a0b`

## string_xrefs

- `0x180092a41`: `Protocol`
- `0x180092a8a`: `Protocol`
- `0x18009298a`: `Protocols`
- `0x1800929d3`: `Protocols`
- `0x18009242d`: `TierAclRuleAction`
- `0x180092483`: `TierAclRuleAction`
- `0x180092e3a`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092e69`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092e98`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092ec7`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092ef6`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092f25`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092f54`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092f83`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092fb2`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092fe1`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180093010`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x18009303f`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`
- `0x180092ebb`: `IpSet ID not supported for tier acl policy.`
- `0x180092eea`: `IpSet ID not supported for tier acl policy.`
- `0x180092e8c`: `Scope not supported for tier acl policy rule.`
- `0x180092e5d`: `Pass action not supported for acl policy.`
- `0x180092f19`: `Action not supported for tier acl policy.`
- `0x180092f48`: `Direction not supported for tier acl policy rule.`
- `0x180092f77`: `An invalid tier acl rule action was specified.`
- `0x180092fa6`: `LocalPort not supported for tier acl policy rule.`
- `0x180092fd5`: `RemotePort not supported for tier acl policy rule.`
- `0x180093033`: `RuleType not supported for tier acl policy rule.`
- `0x180093004`: `Protocol not supported for tier acl policy rule.`
- `0x180092e2e`: `ServiceName not supported for tier acl policy rule.`
- `0x180092c5e`: `ServiceName`
- `0x180092cab`: `ServiceName`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall GetAclRuleFromAclObject(__int64 *a1, __int64 a2, __int128 *a3, __int64 a4, __int64 a5, _BYTE *a6)
{
  char v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  unsigned int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // rbx
  const wchar_t **String; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rbx
  __int128 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  const wchar_t **v22; // rax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  unsigned int v26; // r14d
  __int128 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbx
  const wchar_t **v30; // rax
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  _QWORD *v33; // rbx
  __int128 *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rbx
  const wchar_t **v37; // rax
  const wchar_t *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rbx
  char v44; // al
  __int64 v45; // rbx
  _QWORD *v46; // rax
  int v47; // ebx
  __int64 v48; // rbx
  char v49; // al
  __int64 v50; // rbx
  _QWORD *v51; // rax
  __int64 v52; // rbx
  _QWORD *v53; // rax
  int v54; // ebx
  __int64 v55; // rbx
  int v56; // eax
  char v57; // bl
  __int64 v58; // rbx
  _QWORD *v59; // rax
  int v60; // ebx
  int v61; // eax
  __int64 v62; // rbx
  _QWORD *v63; // rax
  int v64; // ebx
  __int64 v65; // rbx
  _QWORD *v66; // rax
  int v67; // ebx
  __int64 v68; // rbx
  __int64 v69; // rbx
  const wchar_t *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rbx
  __int16 Integer; // bx
  _DWORD *v75; // rdx
  int v76; // eax
  _DWORD *v77; // rdx
  __int64 v78; // rbx
  __int64 v79; // rbx
  const wchar_t *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rbx
  __int16 v84; // bx
  _DWORD *v85; // rdx
  int v86; // eax
  _DWORD *v87; // rdx
  __int16 v88; // r14
  __int64 v89; // rbx
  __int64 v90; // r15
  __int64 v91; // rax
  __int64 v92; // rcx
  int v93; // ebx
  __int64 v94; // rbx
  __int64 v95; // rbx
  char v96; // al
  __int64 v97; // rbx
  _QWORD *v98; // rax
  int v99; // ebx
  __int64 v100; // rbx
  __int64 v101; // rbx
  __int64 v102; // rbx
  __int64 v103; // rbx
  __int64 v104; // rax
  __int64 v105; // rbx
  __int64 v106; // rbx
  __int64 v107; // rax
  volatile signed __int32 *v108; // rbx
  unsigned int v109; // eax
  unsigned int v110; // eax
  unsigned int v111; // eax
  unsigned int v112; // eax
  unsigned int v113; // eax
  unsigned int v114; // eax
  unsigned int v115; // eax
  unsigned int v116; // eax
  unsigned int v117; // eax
  unsigned int v118; // eax
  unsigned int v119; // eax
  unsigned int v120; // eax
  char *v121; // [rsp+28h] [rbp-D8h]
  HNSObject *v122[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v123; // [rsp+40h] [rbp-C0h] BYREF
  __int128 *v124; // [rsp+50h] [rbp-B0h]
  const wchar_t *v125; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v126; // [rsp+68h] [rbp-98h]
  const wchar_t *v127; // [rsp+70h] [rbp-90h] BYREF
  __int64 v128; // [rsp+78h] [rbp-88h]
  __int128 v129; // [rsp+90h] [rbp-70h] BYREF
  __int64 v130; // [rsp+A0h] [rbp-60h]
  __int128 *v131; // [rsp+A8h] [rbp-58h]
  __int128 v132; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v133; // [rsp+C0h] [rbp-40h]
  _BYTE Src[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v135; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v136; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v124 = a3;
  v130 = a2;
  v131 = a3;
  v8 = 0;
  LODWORD(v122[0]) = 0;
  *(_BYTE *)(a4 + 290) = a2 != 0;
  *(_DWORD *)(a4 + 280) = 0;
  v9 = *a1;
  v135 = 0;
  v136 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v135, L"Scope");
  LODWORD(v9) = HNSObject::PropertyExists(v9, &v135);
  std::wstring::~wstring(&v135);
  if ( !(_DWORD)v9 )
  {
    if ( *(_BYTE *)(a4 + 290) )
    {
      v111 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x651,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v111,
        (int)"Scope not supported for tier acl policy rule.",
        v121);
    }
    v10 = *a1;
    v135 = 0;
    v136 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v135, L"Scope");
    *(_DWORD *)(a4 + 280) = HNSObject::GetInteger(v10, &v135);
    std::wstring::~wstring(&v135);
  }
  *(_DWORD *)(a5 + 280) = *(_DWORD *)(a4 + 280);
  v11 = *a1;
  v135 = 0;
  v136 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v135, L"LocalAddresses");
  LODWORD(v11) = HNSObject::PropertyExists(v11, &v135);
  std::wstring::~wstring(&v135);
  if ( !(_DWORD)v11 )
  {
    v12 = *(_DWORD *)(a4 + 280);
    if ( HNS::Feature::m_npmPerfOptimizationEnabled )
    {
      v122[0] = (HNSObject *)&v129;
      v129 = 0;
      v13 = *((_QWORD *)v124 + 1);
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
      v129 = *v124;
      v14 = *a1;
      v135 = 0;
      v136 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v135, L"LocalAddresses");
      String = (const wchar_t **)HNSObject::GetString(v14, &v132, &v135);
      if ( (unsigned __int64)String[3] <= 7 )
        v16 = (const wchar_t *)String;
      else
        v16 = *String;
      *(_QWORD *)&v123 = L",";
      *((_QWORD *)&v123 + 1) = 1;
      v125 = v16;
      v126 = (__int64)String[2];
      v17 = StringSplit(&v127, &v125, &v123);
      v18 = (_QWORD *)(a5 + 224);
      SplitIpAddressAndSetId(v17, &v129, v12, a4 + 104, a5 + 224, a1);
      std::vector<std::wstring>::_Tidy(&v127);
      std::wstring::~wstring(&v132);
      std::wstring::~wstring(&v135);
    }
    else
    {
      v122[0] = 0;
      *(_QWORD *)&v129 = &v123;
      v123 = 0;
      v19 = v124;
      v20 = *((_QWORD *)v124 + 1);
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      v123 = *v19;
      v21 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"LocalAddresses");
      v22 = (const wchar_t **)HNSObject::GetString(v21, Src, &v132);
      if ( (unsigned __int64)v22[3] <= 7 )
        v23 = (const wchar_t *)v22;
      else
        v23 = *v22;
      v125 = L",";
      v126 = 1;
      v127 = v23;
      v128 = (__int64)v22[2];
      v24 = StringSplit(&v135, &v127, &v125);
      v18 = (_QWORD *)(a5 + 224);
      SplitIpAddressAndSetId(v24, &v123, v12, a4 + 104, a5 + 224, v122);
      std::vector<std::wstring>::_Tidy(&v135);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v132);
      if ( v122[0] )
        HNSObject::Release(v122[0]);
    }
    if ( *(_BYTE *)(a4 + 290) && *v18 != v18[1] )
    {
      v112 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x678,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v112,
        (int)"IpSet ID not supported for tier acl policy.",
        v121);
    }
    if ( *v18 != v18[1] )
      *a6 = 1;
  }
  v25 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemoteAddresses");
  LODWORD(v25) = HNSObject::PropertyExists(v25, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v25 )
  {
    v26 = *(_DWORD *)(a4 + 280);
    if ( HNS::Feature::m_npmPerfOptimizationEnabled )
    {
      *(_QWORD *)&v129 = &v123;
      v123 = 0;
      v27 = v124;
      v28 = *((_QWORD *)v124 + 1);
      if ( v28 )
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
      v123 = *v27;
      v29 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemoteAddresses");
      v30 = (const wchar_t **)HNSObject::GetString(v29, Src, &v132);
      if ( (unsigned __int64)v30[3] <= 7 )
        v31 = (const wchar_t *)v30;
      else
        v31 = *v30;
      v127 = L",";
      v128 = 1;
      v125 = v31;
      v126 = (__int64)v30[2];
      v32 = StringSplit(&v135, &v125, &v127);
      v33 = (_QWORD *)(a5 + 248);
      SplitIpAddressAndSetId(v32, &v123, v26, a4 + 136, a5 + 248, a1);
      std::vector<std::wstring>::_Tidy(&v135);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v132);
    }
    else
    {
      v122[0] = 0;
      *(_QWORD *)&v129 = &v123;
      v123 = 0;
      v34 = v124;
      v35 = *((_QWORD *)v124 + 1);
      if ( v35 )
        _InterlockedIncrement((volatile signed __int32 *)(v35 + 8));
      v123 = *v34;
      v36 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemoteAddresses");
      v37 = (const wchar_t **)HNSObject::GetString(v36, Src, &v132);
      if ( (unsigned __int64)v37[3] <= 7 )
        v38 = (const wchar_t *)v37;
      else
        v38 = *v37;
      v127 = L",";
      v128 = 1;
      v125 = v38;
      v126 = (__int64)v37[2];
      v39 = StringSplit(&v135, &v125, &v127);
      v33 = (_QWORD *)(a5 + 248);
      SplitIpAddressAndSetId(v39, &v123, v26, a4 + 136, a5 + 248, v122);
      std::vector<std::wstring>::_Tidy(&v135);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v132);
      if ( v122[0] )
        HNSObject::Release(v122[0]);
    }
    if ( *(_BYTE *)(a4 + 290) && *v33 != v33[1] )
    {
      v113 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x69C,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v113,
        (int)"IpSet ID not supported for tier acl policy.",
        v121);
    }
    if ( *v33 != v33[1] )
      *a6 = 1;
  }
  v40 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Id");
  LODWORD(v40) = HNSObject::PropertyExists(v40, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v40 )
  {
    v41 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Id");
    v42 = HNSObject::GetString(v41, Src, &v132);
    std::wstring::operator=(a4, v42);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    std::wstring::operator=(a5, a4);
  }
  v43 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Action");
  LODWORD(v43) = HNSObject::PropertyExists(v43, &v132);
  std::wstring::~wstring(&v132);
  v44 = *(_BYTE *)(a4 + 290);
  if ( (_DWORD)v43 )
  {
    if ( !v44
      || (v55 = *a1,
          v132 = 0,
          v133 = 0,
          std::wstring::_Construct<1,unsigned short const *>(&v132, L"TierAclRuleAction"),
          v8 = 1,
          v56 = HNSObject::PropertyExists(v55, &v132),
          v57 = 1,
          v56) )
    {
      v57 = 0;
    }
    if ( (v8 & 1) != 0 )
      std::wstring::~wstring(&v132);
    if ( v57 )
    {
      v58 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"TierAclRuleAction");
      v59 = (_QWORD *)HNSObject::GetString(v58, Src, &v132);
      if ( v59[3] > 7u )
        v59 = (_QWORD *)*v59;
      v60 = _o__wcsicmp(v59, L"Allow");
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v132);
      if ( v60 )
      {
        v62 = *a1;
        v132 = 0;
        v133 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v132, L"TierAclRuleAction");
        v63 = (_QWORD *)HNSObject::GetString(v62, Src, &v132);
        if ( v63[3] > 7u )
          v63 = (_QWORD *)*v63;
        v64 = _o__wcsicmp(v63, L"Block");
        std::wstring::~wstring(Src);
        std::wstring::~wstring(&v132);
        if ( v64 )
        {
          v65 = *a1;
          v132 = 0;
          v133 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v132, L"TierAclRuleAction");
          v66 = (_QWORD *)HNSObject::GetString(v65, Src, &v132);
          if ( v66[3] > 7u )
            v66 = (_QWORD *)*v66;
          v67 = _o__wcsicmp(v66, L"Pass");
          std::wstring::~wstring(Src);
          std::wstring::~wstring(&v132);
          if ( v67 )
          {
            v116 = wil::verify_hresult<long>(2151350285LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x6CF,
              (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
              (const char *)v116,
              (int)"An invalid tier acl rule action was specified.",
              v121);
          }
          *(_DWORD *)(a4 + 292) = 2;
          v61 = 2;
        }
        else
        {
          *(_DWORD *)(a4 + 292) = 1;
          v61 = 1;
        }
      }
      else
      {
        *(_DWORD *)(a4 + 292) = 0;
        v61 = 0;
      }
      *(_DWORD *)(a5 + 292) = v61;
    }
  }
  else
  {
    if ( v44 )
    {
      v114 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x6AF,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v114,
        (int)"Action not supported for tier acl policy.",
        v121);
    }
    *(_DWORD *)(a4 + 96) = 2;
    v45 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Action");
    v46 = (_QWORD *)HNSObject::GetString(v45, Src, &v132);
    if ( v46[3] > 7u )
      v46 = (_QWORD *)*v46;
    v47 = _o__wcsicmp(v46, L"Allow");
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    if ( v47 )
    {
      v52 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"Action");
      v53 = (_QWORD *)HNSObject::GetString(v52, Src, &v132);
      if ( v53[3] > 7u )
        v53 = (_QWORD *)*v53;
      v54 = _o__wcsicmp(v53, L"Pass");
      std::wstring::~wstring(Src);
      std::wstring::~wstring(&v132);
      if ( !v54 )
      {
        v110 = wil::verify_hresult<long>(2151350285LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x6B9,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
          (const char *)v110,
          (int)"Pass action not supported for acl policy.",
          v121);
      }
    }
    else
    {
      *(_DWORD *)(a4 + 96) = 3;
    }
    *(_DWORD *)(a5 + 96) = *(_DWORD *)(a4 + 96);
  }
  v48 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Direction");
  LODWORD(v48) = HNSObject::PropertyExists(v48, &v132);
  std::wstring::~wstring(&v132);
  v49 = *(_BYTE *)(a4 + 290);
  if ( (_DWORD)v48 )
  {
    if ( v49 )
      *(_DWORD *)(a4 + 100) = *(_DWORD *)(v130 + 32);
  }
  else
  {
    if ( v49 )
    {
      v115 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x6D9,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v115,
        (int)"Direction not supported for tier acl policy rule.",
        v121);
    }
    v50 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Direction");
    v51 = (_QWORD *)HNSObject::GetString(v50, Src, &v132);
    if ( v51[3] > 7u )
      v51 = (_QWORD *)*v51;
    *(_DWORD *)(a4 + 100) = ((unsigned int)_o__wcsicmp(v51, L"In") != 0) + 1;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    *(_DWORD *)(a5 + 100) = *(_DWORD *)(a4 + 100);
  }
  v68 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"LocalPorts");
  LODWORD(v68) = HNSObject::PropertyExists(v68, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v68 )
  {
    v69 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"LocalPorts");
    v70 = (const wchar_t *)HNSObject::GetString(v69, Src, &v132);
    v71 = *((_QWORD *)v70 + 2);
    if ( *((_QWORD *)v70 + 3) > 7u )
      v70 = *(const wchar_t **)v70;
    v127 = v70;
    v128 = v71;
    ParseFirewallPorts(&v127, a4 + 176);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    std::vector<HNS::Service::Helper::PortRange>::operator=(a5 + 176, a4 + 176);
  }
  v72 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"LocalPort");
  LODWORD(v72) = HNSObject::PropertyExists(v72, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v72 )
  {
    if ( *(_BYTE *)(a4 + 290) )
    {
      v117 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x6F6,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v117,
        (int)"LocalPort not supported for tier acl policy rule.",
        v121);
    }
    v73 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"LocalPort");
    Integer = HNSObject::GetInteger(v73, &v132);
    std::wstring::~wstring(&v132);
    if ( Integer )
    {
      LOWORD(v122[0]) = Integer;
      WORD1(v122[0]) = Integer;
      v75 = *(_DWORD **)(a4 + 184);
      if ( v75 == *(_DWORD **)(a4 + 192) )
      {
        std::vector<std::pair<unsigned short,unsigned short>>::_Emplace_reallocate<std::pair<unsigned short,unsigned short> &>(
          a4 + 176,
          v75,
          v122);
        v76 = (int)v122[0];
      }
      else
      {
        v76 = (int)v122[0];
        *v75 = v122[0];
        *(_QWORD *)(a4 + 184) += 4LL;
      }
      v77 = *(_DWORD **)(a5 + 184);
      if ( v77 == *(_DWORD **)(a5 + 192) )
      {
        std::vector<std::pair<unsigned short,unsigned short>>::_Emplace_reallocate<std::pair<unsigned short,unsigned short> &>(
          a5 + 176,
          v77,
          v122);
      }
      else
      {
        *v77 = v76;
        *(_QWORD *)(a5 + 184) += 4LL;
      }
    }
  }
  v78 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemotePorts");
  LODWORD(v78) = HNSObject::PropertyExists(v78, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v78 )
  {
    v79 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemotePorts");
    v80 = (const wchar_t *)HNSObject::GetString(v79, Src, &v132);
    v81 = *((_QWORD *)v80 + 2);
    if ( *((_QWORD *)v80 + 3) > 7u )
      v80 = *(const wchar_t **)v80;
    v127 = v80;
    v128 = v81;
    ParseFirewallPorts(&v127, a4 + 200);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    std::vector<HNS::Service::Helper::PortRange>::operator=(a5 + 200, a4 + 200);
  }
  v82 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemotePort");
  LODWORD(v82) = HNSObject::PropertyExists(v82, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v82 )
  {
    if ( *(_BYTE *)(a4 + 290) )
    {
      v118 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x70F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v118,
        (int)"RemotePort not supported for tier acl policy rule.",
        v121);
    }
    v83 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"RemotePort");
    v84 = HNSObject::GetInteger(v83, &v132);
    std::wstring::~wstring(&v132);
    if ( v84 )
    {
      LOWORD(v122[0]) = v84;
      WORD1(v122[0]) = v84;
      v85 = *(_DWORD **)(a4 + 208);
      if ( v85 == *(_DWORD **)(a4 + 216) )
      {
        std::vector<std::pair<unsigned short,unsigned short>>::_Emplace_reallocate<std::pair<unsigned short,unsigned short> &>(
          a4 + 200,
          v85,
          v122);
        v86 = (int)v122[0];
      }
      else
      {
        v86 = (int)v122[0];
        *v85 = v122[0];
        *(_QWORD *)(a4 + 208) += 4LL;
      }
      v87 = *(_DWORD **)(a5 + 208);
      if ( v87 == *(_DWORD **)(a5 + 216) )
      {
        std::vector<std::pair<unsigned short,unsigned short>>::_Emplace_reallocate<std::pair<unsigned short,unsigned short> &>(
          a5 + 200,
          v87,
          v122);
      }
      else
      {
        *v87 = v86;
        *(_QWORD *)(a5 + 208) += 4LL;
      }
    }
  }
  v88 = 256;
  *(_WORD *)(a4 + 168) = 256;
  v89 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Protocols");
  LODWORD(v89) = HNSObject::PropertyExists(v89, &v132);
  std::wstring::~wstring(&v132);
  v90 = *a1;
  v132 = 0;
  v133 = 0;
  if ( (_DWORD)v89 )
  {
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Protocol");
    v93 = HNSObject::PropertyExists(v90, &v132);
    std::wstring::~wstring(&v132);
    if ( !v93 )
    {
      if ( *(_BYTE *)(a4 + 290) )
      {
        v119 = wil::verify_hresult<long>(2151350285LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x727,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
          (const char *)v119,
          (int)"Protocol not supported for tier acl policy rule.",
          v121);
      }
      v94 = *a1;
      v132 = 0;
      v133 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v132, L"Protocol");
      *(_WORD *)(a4 + 168) = HNSObject::GetInteger(v94, &v132);
      std::wstring::~wstring(&v132);
    }
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Protocols");
    v91 = HNSObject::GetString(v90, Src, &v132);
    v92 = *(_QWORD *)(v91 + 16);
    if ( *(_QWORD *)(v91 + 24) > 7u )
      v91 = *(_QWORD *)v91;
    if ( v92 )
      v88 = wcstoul((const wchar_t *)v91, 0, 0);
    *(_WORD *)(a4 + 168) = v88;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
  }
  *(_WORD *)(a5 + 168) = *(_WORD *)(a4 + 168);
  v95 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"RuleType");
  LODWORD(v95) = HNSObject::PropertyExists(v95, &v132);
  std::wstring::~wstring(&v132);
  v96 = *(_BYTE *)(a4 + 290);
  if ( (_DWORD)v95 )
  {
    if ( v96 )
      *(_DWORD *)(a4 + 276) = 2;
  }
  else
  {
    if ( v96 )
    {
      v120 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x732,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v120,
        (int)"RuleType not supported for tier acl policy rule.",
        v121);
    }
    *(_DWORD *)(a4 + 276) = 2;
    v97 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"RuleType");
    v98 = (_QWORD *)HNSObject::GetString(v97, Src, &v132);
    if ( v98[3] > 7u )
      v98 = (_QWORD *)*v98;
    v99 = _o__wcsicmp(v98, L"Host");
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    if ( !v99 )
      *(_DWORD *)(a4 + 276) = 1;
    *(_DWORD *)(a5 + 276) = *(_DWORD *)(a4 + 276);
  }
  v100 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Priority");
  LODWORD(v100) = HNSObject::PropertyExists(v100, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v100 )
  {
    v101 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Priority");
    *(_WORD *)(a4 + 284) = HNSObject::GetInteger(v101, &v132);
    std::wstring::~wstring(&v132);
    *(_WORD *)(a5 + 284) = *(_WORD *)(a4 + 284);
  }
  v102 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"ServiceName");
  LODWORD(v102) = HNSObject::PropertyExists(v102, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v102 )
  {
    if ( *(_BYTE *)(a4 + 290) )
    {
      v109 = wil::verify_hresult<long>(2151350285LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x751,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\vfp\\src\\aclhelper.cpp",
        (const char *)v109,
        (int)"ServiceName not supported for tier acl policy rule.",
        v121);
    }
    v103 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"ServiceName");
    v104 = HNSObject::GetString(v103, Src, &v132);
    std::wstring::operator=(a4 + 32, v104);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(&v132);
    std::wstring::operator=(a5 + 32, a4 + 32);
  }
  v105 = *a1;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"Flags");
  LODWORD(v105) = HNSObject::PropertyExists(v105, &v132);
  std::wstring::~wstring(&v132);
  if ( !(_DWORD)v105 )
  {
    v106 = *a1;
    v132 = 0;
    v133 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v132, L"Flags");
    *(_WORD *)(a4 + 286) = HNSObject::GetInteger(v106, &v132);
    std::wstring::~wstring(&v132);
  }
  if ( !*(_QWORD *)(a4 + 16) )
  {
    v107 = FirewallOperation::BuildACLDescription(Src);
    std::wstring::operator=(a4, v107);
    std::wstring::~wstring(Src);
    std::wstring::operator=(a5, a4);
  }
  v108 = (volatile signed __int32 *)*((_QWORD *)v124 + 1);
  if ( v108 && _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v108)(v108);
    if ( !_InterlockedDecrement(v108 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v108 + 8LL))(v108);
  }
}

```

## disassembly

```asm
0x180091b14  mov     [rsp-8+arg_8], rbx
0x180091b19  push    rbp
0x180091b1a  push    rsi
0x180091b1b  push    rdi
0x180091b1c  push    r12
0x180091b1e  push    r13
0x180091b20  push    r14
0x180091b22  push    r15
0x180091b24  lea     rbp, [rsp-20h]
0x180091b29  sub     rsp, 120h
0x180091b30  mov     rax, cs:__security_cookie
0x180091b37  xor     rax, rsp
0x180091b3a  mov     [rbp+50h+var_40], rax
0x180091b3e  mov     rdi, r9
0x180091b41  mov     [rsp+150h+var_100], r8
0x180091b46  mov     [rbp+50h+var_B0], rdx
0x180091b4a  mov     rsi, rcx
0x180091b4d  mov     [rbp+50h+var_A8], r8
0x180091b51  mov     r13, [rbp+50h+arg_20]
0x180091b58  mov     r15, [rbp+50h+arg_28]
0x180091b5f  xor     r14d, r14d
0x180091b62  mov     r12d, r14d
0x180091b65  mov     dword ptr [rsp+150h+var_120], r14d
0x180091b6a  test    rdx, rdx
0x180091b6d  setnz   al
0x180091b70  mov     [r9+122h], al
0x180091b77  mov     [r9+118h], r14d
0x180091b7e  mov     rbx, [rcx]
0x180091b81  xorps   xmm0, xmm0
0x180091b84  movups  [rbp+50h+var_60], xmm0
0x180091b88  xorps   xmm1, xmm1
0x180091b8b  movdqu  [rbp+50h+var_50], xmm1
0x180091b90  lea     r8d, [r14+5]
0x180091b94  lea     rdx, aScope; "Scope"
0x180091b9b  lea     rcx, [rbp+50h+var_60]
0x180091b9f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091ba4  lea     rdx, [rbp+50h+var_60]
0x180091ba8  mov     rcx, rbx
0x180091bab  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x180091bb0  mov     ebx, eax
0x180091bb2  lea     rcx, [rbp+50h+var_60]; void *
0x180091bb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091bbb  test    ebx, ebx
0x180091bbd  jnz     short loc_180091C0E
0x180091bbf  cmp     [rdi+122h], r14b
0x180091bc6  jnz     loc_180092E7B
0x180091bcc  mov     rbx, [rsi]
0x180091bcf  xorps   xmm0, xmm0
0x180091bd2  movups  [rbp+50h+var_60], xmm0
0x180091bd6  xorps   xmm1, xmm1
0x180091bd9  movdqu  [rbp+50h+var_50], xmm1
0x180091bde  lea     r8d, [r14+5]
0x180091be2  lea     rdx, aScope; "Scope"
0x180091be9  lea     rcx, [rbp+50h+var_60]
0x180091bed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091bf2  nop
0x180091bf3  lea     rdx, [rbp+50h+var_60]
0x180091bf7  mov     rcx, rbx
0x180091bfa  call    ?GetInteger@HNSObject@@QEBAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::GetInteger(std::wstring const &)
0x180091bff  mov     [rdi+118h], eax
0x180091c05  lea     rcx, [rbp+50h+var_60]; void *
0x180091c09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091c0e  mov     eax, [rdi+118h]
0x180091c14  mov     [r13+118h], eax
0x180091c1b  mov     rbx, [rsi]
0x180091c1e  xorps   xmm0, xmm0
0x180091c21  movups  [rbp+50h+var_60], xmm0
0x180091c25  xorps   xmm1, xmm1
0x180091c28  movdqu  [rbp+50h+var_50], xmm1
0x180091c2d  mov     r8d, 0Eh
0x180091c33  lea     rdx, aLocaladdresses; "LocalAddresses"
0x180091c3a  lea     rcx, [rbp+50h+var_60]
0x180091c3e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091c43  lea     rdx, [rbp+50h+var_60]
0x180091c47  mov     rcx, rbx
0x180091c4a  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x180091c4f  mov     ebx, eax
0x180091c51  lea     rcx, [rbp+50h+var_60]; void *
0x180091c55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091c5a  test    ebx, ebx
0x180091c5c  jnz     loc_180091EAF
0x180091c62  cmp     cs:?m_npmPerfOptimizationEnabled@Feature@HNS@@3HA, r14d; int HNS::Feature::m_npmPerfOptimizationEnabled
0x180091c69  setnz   al
0x180091c6c  mov     r14d, [rdi+118h]
0x180091c73  test    al, al
0x180091c75  jz      loc_180091D76
0x180091c7b  lea     rax, [rbp+50h+var_C0]
0x180091c7f  mov     [rsp+150h+var_120], rax
0x180091c84  xorps   xmm0, xmm0
0x180091c87  movdqu  [rbp+50h+var_C0], xmm0
0x180091c8c  mov     rcx, [rsp+150h+var_100]
0x180091c91  mov     rax, [rcx+8]
0x180091c95  test    rax, rax
0x180091c98  jz      short loc_180091C9E
0x180091c9a  lock inc dword ptr [rax+8]
0x180091c9e  mov     rax, [rcx]
0x180091ca1  mov     qword ptr [rbp+50h+var_C0], rax
0x180091ca5  mov     rax, [rcx+8]
0x180091ca9  mov     qword ptr [rbp+50h+var_C0+8], rax
0x180091cad  mov     rbx, [rsi]
0x180091cb0  movups  [rbp+50h+var_60], xmm0
0x180091cb4  xorps   xmm1, xmm1
0x180091cb7  movdqu  [rbp+50h+var_50], xmm1
0x180091cbc  mov     r8d, 0Eh
0x180091cc2  lea     rdx, aLocaladdresses; "LocalAddresses"
0x180091cc9  lea     rcx, [rbp+50h+var_60]
0x180091ccd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091cd2  nop
0x180091cd3  lea     r8, [rbp+50h+var_60]
0x180091cd7  lea     rdx, [rbp+50h+var_A0]
0x180091cdb  mov     rcx, rbx
0x180091cde  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x180091ce3  nop
0x180091ce4  cmp     qword ptr [rax+18h], 7
0x180091ce9  jbe     short loc_180091CF0
0x180091ceb  mov     rcx, [rax]
0x180091cee  jmp     short loc_180091CF3
0x180091cf0  mov     rcx, rax
0x180091cf3  lea     rdx, asc_1802EB578; ","
0x180091cfa  mov     qword ptr [rsp+150h+var_110], rdx
0x180091cff  mov     qword ptr [rsp+150h+var_110+8], 1
0x180091d08  mov     [rsp+150h+var_F0], rcx
0x180091d0d  mov     rax, [rax+10h]
0x180091d11  mov     [rsp+150h+var_E8], rax
0x180091d16  lea     r8, [rsp+150h+var_110]
0x180091d1b  lea     rdx, [rsp+150h+var_F0]
0x180091d20  lea     rcx, [rsp+150h+var_E0]
0x180091d25  call    ?StringSplit@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@0@Z; StringSplit(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180091d2a  nop
0x180091d2b  lea     rbx, [r13+0E0h]
0x180091d32  lea     r9, [rdi+68h]
0x180091d36  mov     [rsp+150h+var_128], rsi
0x180091d3b  mov     qword ptr [rsp+150h+var_130], rbx
0x180091d40  mov     r8d, r14d
0x180091d43  lea     rdx, [rbp+50h+var_C0]
0x180091d47  mov     rcx, rax
0x180091d4a  call    ?SplitIpAddressAndSetId@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$shared_ptr@VEndpoint@Network@Service@HNS@@@2@W4FirewallRuleScope@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEAV?$vector@UIpSetInfo@@V?$allocator@UIpSetInfo@@@std@@@2@AEBV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@@Z; SplitIpAddressAndSetId(std::vector<std::wstring> const &,std::shared_ptr<HNS::Service::Network::Endpoint>,FirewallRuleScope,std::wstring &,std::vector<IpSetInfo> &,wil::com_ptr_t<HNSObject,wil::err_exception_policy> const &)
0x180091d4f  nop
0x180091d50  lea     rcx, [rsp+150h+var_E0]
0x180091d55  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180091d5a  nop
0x180091d5b  lea     rcx, [rbp+50h+var_A0]; void *
0x180091d5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091d64  nop
0x180091d65  lea     rcx, [rbp+50h+var_60]; void *
0x180091d69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091d6e  xor     r14d, r14d
0x180091d71  jmp     loc_180091E8C
0x180091d76  mov     [rsp+150h+var_120], 0
0x180091d7f  lea     rax, [rsp+150h+var_110]
0x180091d84  mov     qword ptr [rbp+50h+var_C0], rax
0x180091d88  xorps   xmm0, xmm0
0x180091d8b  movdqu  [rsp+150h+var_110], xmm0
0x180091d91  mov     rcx, [rsp+150h+var_100]
0x180091d96  mov     rax, [rcx+8]
0x180091d9a  test    rax, rax
0x180091d9d  jz      short loc_180091DA3
0x180091d9f  lock inc dword ptr [rax+8]
0x180091da3  mov     rax, [rcx]
0x180091da6  mov     qword ptr [rsp+150h+var_110], rax
0x180091dab  mov     rax, [rcx+8]
0x180091daf  mov     qword ptr [rsp+150h+var_110+8], rax
0x180091db4  mov     rbx, [rsi]
0x180091db7  movups  [rbp+50h+var_A0], xmm0
0x180091dbb  xorps   xmm1, xmm1
0x180091dbe  movdqu  [rbp+50h+var_90], xmm1
0x180091dc3  mov     r8d, 0Eh
0x180091dc9  lea     rdx, aLocaladdresses; "LocalAddresses"
0x180091dd0  lea     rcx, [rbp+50h+var_A0]
0x180091dd4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091dd9  nop
0x180091dda  lea     r8, [rbp+50h+var_A0]
0x180091dde  lea     rdx, [rbp+50h+Src]
0x180091de2  mov     rcx, rbx
0x180091de5  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x180091dea  nop
0x180091deb  cmp     qword ptr [rax+18h], 7
0x180091df0  jbe     short loc_180091DF7
0x180091df2  mov     rcx, [rax]
0x180091df5  jmp     short loc_180091DFA
0x180091df7  mov     rcx, rax
0x180091dfa  lea     rdx, asc_1802EB578; ","
0x180091e01  mov     [rsp+150h+var_F0], rdx
0x180091e06  mov     [rsp+150h+var_E8], 1
0x180091e0f  mov     [rsp+150h+var_E0], rcx
0x180091e14  mov     rax, [rax+10h]
0x180091e18  mov     [rsp+150h+var_D8], rax
0x180091e1d  lea     r8, [rsp+150h+var_F0]
0x180091e22  lea     rdx, [rsp+150h+var_E0]
0x180091e27  lea     rcx, [rbp+50h+var_60]
0x180091e2b  call    ?StringSplit@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@0@Z; StringSplit(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180091e30  nop
0x180091e31  lea     rbx, [r13+0E0h]
0x180091e38  lea     r9, [rdi+68h]
0x180091e3c  lea     rcx, [rsp+150h+var_120]
0x180091e41  mov     [rsp+150h+var_128], rcx; char *
0x180091e46  mov     qword ptr [rsp+150h+var_130], rbx
0x180091e4b  mov     r8d, r14d
0x180091e4e  lea     rdx, [rsp+150h+var_110]
0x180091e53  mov     rcx, rax
0x180091e56  call    ?SplitIpAddressAndSetId@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$shared_ptr@VEndpoint@Network@Service@HNS@@@2@W4FirewallRuleScope@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEAV?$vector@UIpSetInfo@@V?$allocator@UIpSetInfo@@@std@@@2@AEBV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@@Z; SplitIpAddressAndSetId(std::vector<std::wstring> const &,std::shared_ptr<HNS::Service::Network::Endpoint>,FirewallRuleScope,std::wstring &,std::vector<IpSetInfo> &,wil::com_ptr_t<HNSObject,wil::err_exception_policy> const &)
0x180091e5b  nop
0x180091e5c  lea     rcx, [rbp+50h+var_60]
0x180091e60  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180091e65  nop
0x180091e66  lea     rcx, [rbp+50h+Src]; void *
0x180091e6a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091e6f  nop
0x180091e70  lea     rcx, [rbp+50h+var_A0]; void *
0x180091e74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091e79  nop
0x180091e7a  mov     rcx, [rsp+150h+var_120]; this
0x180091e7f  xor     r14d, r14d
0x180091e82  test    rcx, rcx
0x180091e85  jz      short loc_180091E8C
0x180091e87  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180091e8c  cmp     [rdi+122h], r14b
0x180091e93  jz      short loc_180091EA2
0x180091e95  mov     rax, [rbx+8]
0x180091e99  cmp     [rbx], rax
0x180091e9c  jnz     loc_180092EAA
0x180091ea2  mov     rax, [rbx+8]
0x180091ea6  cmp     [rbx], rax
0x180091ea9  jz      short loc_180091EAF
0x180091eab  mov     byte ptr [r15], 1
0x180091eaf  mov     rbx, [rsi]
0x180091eb2  xorps   xmm0, xmm0
0x180091eb5  movups  [rbp+50h+var_A0], xmm0
0x180091eb9  xorps   xmm1, xmm1
0x180091ebc  movdqu  [rbp+50h+var_90], xmm1
0x180091ec1  mov     r8d, 0Fh
0x180091ec7  lea     rdx, aRemoteaddresse; "RemoteAddresses"
0x180091ece  lea     rcx, [rbp+50h+var_A0]
0x180091ed2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091ed7  lea     rdx, [rbp+50h+var_A0]
0x180091edb  mov     rcx, rbx
0x180091ede  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x180091ee3  mov     ebx, eax
0x180091ee5  lea     rcx, [rbp+50h+var_A0]; void *
0x180091ee9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180091eee  test    ebx, ebx
0x180091ef0  jnz     loc_18009214B
0x180091ef6  cmp     cs:?m_npmPerfOptimizationEnabled@Feature@HNS@@3HA, r14d; int HNS::Feature::m_npmPerfOptimizationEnabled
0x180091efd  setnz   al
0x180091f00  mov     r14d, [rdi+118h]
0x180091f07  test    al, al
0x180091f09  jz      loc_18009200F
0x180091f0f  lea     rax, [rsp+150h+var_110]
0x180091f14  mov     qword ptr [rbp+50h+var_C0], rax
0x180091f18  xorps   xmm0, xmm0
0x180091f1b  movdqu  [rsp+150h+var_110], xmm0
0x180091f21  mov     rcx, [rsp+150h+var_100]
0x180091f26  mov     rax, [rcx+8]
0x180091f2a  test    rax, rax
0x180091f2d  jz      short loc_180091F33
0x180091f2f  lock inc dword ptr [rax+8]
0x180091f33  mov     rax, [rcx]
0x180091f36  mov     qword ptr [rsp+150h+var_110], rax
0x180091f3b  mov     rax, [rcx+8]
0x180091f3f  mov     qword ptr [rsp+150h+var_110+8], rax
0x180091f44  mov     rbx, [rsi]
0x180091f47  movups  [rbp+50h+var_A0], xmm0
0x180091f4b  xorps   xmm1, xmm1
0x180091f4e  movdqu  [rbp+50h+var_90], xmm1
0x180091f53  mov     r8d, 0Fh
0x180091f59  lea     rdx, aRemoteaddresse; "RemoteAddresses"
0x180091f60  lea     rcx, [rbp+50h+var_A0]
0x180091f64  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180091f69  nop
0x180091f6a  lea     r8, [rbp+50h+var_A0]
0x180091f6e  lea     rdx, [rbp+50h+Src]
0x180091f72  mov     rcx, rbx
0x180091f75  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x180091f7a  nop
0x180091f7b  cmp     qword ptr [rax+18h], 7
0x180091f80  jbe     short loc_180091F87
0x180091f82  mov     rcx, [rax]
0x180091f85  jmp     short loc_180091F8A
0x180091f87  mov     rcx, rax
0x180091f8a  lea     rdx, asc_1802EB578; ","
0x180091f91  mov     [rsp+150h+var_E0], rdx
0x180091f96  mov     [rsp+150h+var_D8], 1
0x180091f9f  mov     [rsp+150h+var_F0], rcx
0x180091fa4  mov     rax, [rax+10h]
0x180091fa8  mov     [rsp+150h+var_E8], rax
0x180091fad  lea     r8, [rsp+150h+var_E0]
0x180091fb2  lea     rdx, [rsp+150h+var_F0]
0x180091fb7  lea     rcx, [rbp+50h+var_60]
0x180091fbb  call    ?StringSplit@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@0@Z; StringSplit(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180091fc0  nop
0x180091fc1  lea     rbx, [r13+0F8h]
0x180091fc8  lea     r9, [rdi+88h]
0x180091fcf  mov     [rsp+150h+var_128], rsi
0x180091fd4  mov     qword ptr [rsp+150h+var_130], rbx
0x180091fd9  mov     r8d, r14d
0x180091fdc  lea     rdx, [rsp+150h+var_110]
0x180091fe1  mov     rcx, rax
0x180091fe4  call    ?SplitIpAddressAndSetId@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$shared_ptr@VEndpoint@Network@Service@HNS@@@2@W4FirewallRuleScope@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEAV?$vector@UIpSetInfo@@V?$allocator@UIpSetInfo@@@std@@@2@AEBV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@@Z; SplitIpAddressAndSetId(std::vector<std::wstring> const &,std::shared_ptr<HNS::Service::Network::Endpoint>,FirewallRuleScope,std::wstring &,std::vector<IpSetInfo> &,wil::com_ptr_t<HNSObject,wil::err_exception_policy> const &)
0x180091fe9  nop
0x180091fea  lea     rcx, [rbp+50h+var_60]
  ... truncated ...
```
