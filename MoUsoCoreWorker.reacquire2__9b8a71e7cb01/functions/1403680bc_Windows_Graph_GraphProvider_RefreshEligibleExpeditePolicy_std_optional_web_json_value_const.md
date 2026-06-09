# Windows::Graph::GraphProvider::RefreshEligibleExpeditePolicy(std::optional<web::json::value> const &)

- ea: `0x1403680bc`
- end: `0x1403692bf`
- name: `?RefreshEligibleExpeditePolicy@GraphProvider@Graph@Windows@@AEAAXAEBV?$optional@Vvalue@json@web@@@std@@@Z`
- size: `4611`
- prototype: `__int64 __fastcall(Windows::Graph::GraphProvider *this)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14036bf50`

## callees

- `0x140024de0`
- `0x140028864`
- `0x140040184`
- `0x140043284`
- `0x140043814`
- `0x1400447ac`
- `0x140045404`
- `0x14004621c`
- `0x140057a20`
- `0x1400771e8`
- `0x1400773b4`
- `0x14007741c`
- `0x1400a5368`
- `0x1400a5558`
- `0x1400a5688`
- `0x1400a7724`
- `0x1400a7ed0`
- `0x1400c74dc`
- `0x1400c75e4`
- `0x1400cf744`
- `0x1400dac9c`
- `0x1400dadf8`
- `0x14012d7d8`
- `0x1401a5228`
- `0x14036465c`
- `0x1403646c0`
- `0x140367110`
- `0x1403679cc`
- `0x1403680bc`
- `0x14036d540`
- `0x14036d5c4`
- `0x14036ddb8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14036907b`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14036907b`

## string_xrefs

- `0x14036924a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140369263`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140369282`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1403692ad`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140368c40`: `NonSecurityRelease`
- `0x14036819c`: `UpdateExpeditePayload`
- `0x140368219`: `UpdateExpeditePayload`
- `0x1403682d6`: `UpdateExpeditePayload`
- `0x14036847b`: `UpdateExpeditePayload`
- `0x140368554`: `UpdateExpeditePayload`
- `0x140368631`: `UpdateExpeditePayload`
- `0x14036870b`: `UpdateExpeditePayload`
- `0x14036880b`: `UpdateExpeditePayload`
- `0x140368c0b`: `UpdateExpeditePayload`
- `0x140368e0b`: `Expedite: policy is enabled, feature update blocked for 10 days`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
void __fastcall Windows::Graph::GraphProvider::RefreshEligibleExpeditePolicy(
        Windows::Graph::GraphProvider *this,
        _BYTE *a2)
{
  __int16 v4; // bx
  int v5; // edi
  _QWORD *v6; // rbx
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rbx
  _QWORD *v11; // rax
  char v12; // bl
  __int64 v13; // rbx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rbx
  _QWORD *v19; // rax
  unsigned int v20; // r13d
  __int64 v21; // rbx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rbx
  _QWORD *v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rbx
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int16 *traits_2_unsigned_short; // rax
  const char *v32; // r9
  __int64 v33; // r11
  __int64 v34; // rax
  __int64 v35; // r14
  __int64 System; // rax
  int v37; // edi
  __int64 v38; // rcx
  _QWORD *v39; // rax
  bool v40; // bl
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v49; // rbx
  __int64 v50; // rbx
  _QWORD *v51; // rax
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rax
  _QWORD *v59; // rcx
  int *v60; // rax
  const char *v61; // r9
  __int64 v62; // r11
  __int64 v63; // rax
  __int64 v64; // rdi
  __int16 *v65; // rax
  const char *v66; // r9
  __int64 v67; // r11
  __int64 v68; // rax
  wchar_t *v69; // rax
  const char *v70; // r9
  __int64 v71; // r11
  __int64 v72; // rax
  signed __int64 v73; // rdi
  signed __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rcx
  _QWORD *v77; // rax
  unsigned int v78; // eax
  char v79; // di
  __int128 v80; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v81; // [rsp+40h] [rbp-C0h]
  __int64 v82; // [rsp+48h] [rbp-B8h]
  __int128 v83; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v84; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v85; // [rsp+70h] [rbp-90h]
  __int64 v86; // [rsp+78h] [rbp-88h]
  __int128 v87; // [rsp+80h] [rbp-80h] BYREF
  __int64 v88; // [rsp+90h] [rbp-70h]
  __int64 v89; // [rsp+98h] [rbp-68h]
  __int128 v90; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h]
  __int64 v92; // [rsp+B8h] [rbp-48h]
  char v93; // [rsp+C0h] [rbp-40h]
  __int128 v94; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v95; // [rsp+E0h] [rbp-20h]
  __int64 v96; // [rsp+E8h] [rbp-18h]
  __int128 v97; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v98; // [rsp+100h] [rbp+0h]
  __int64 v99; // [rsp+108h] [rbp+8h]
  __int128 v100; // [rsp+110h] [rbp+10h] BYREF
  __int64 v101; // [rsp+120h] [rbp+20h]
  __int64 v102; // [rsp+128h] [rbp+28h]
  __int128 v103; // [rsp+130h] [rbp+30h] BYREF
  __int64 v104; // [rsp+140h] [rbp+40h]
  __int64 v105; // [rsp+148h] [rbp+48h]
  __int128 v106; // [rsp+150h] [rbp+50h] BYREF
  __int64 v107; // [rsp+160h] [rbp+60h]
  __int64 v108; // [rsp+168h] [rbp+68h]
  __int64 v109; // [rsp+170h] [rbp+70h] BYREF
  char v110; // [rsp+178h] [rbp+78h]
  _QWORD v111[4]; // [rsp+180h] [rbp+80h] BYREF
  char v112; // [rsp+1A0h] [rbp+A0h]
  char v113; // [rsp+1A8h] [rbp+A8h]
  _DWORD v114[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v115; // [rsp+1D0h] [rbp+D0h]
  char v116; // [rsp+1D8h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v4 = 0;
  LODWORD(v83) = 0;
  if ( a2[8] )
  {
    v90 = 0;
    v91 = 0;
    v92 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v90, L"Orchestrator");
    v5 = 1;
    LODWORD(v83) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, &v90) )
      goto LABEL_6;
    v103 = 0;
    v104 = 0;
    v105 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v103, L"Orchestrator");
    v6 = (_QWORD *)web::json::value::at(a2, &v103);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"UpdateExpeditePayload");
    v5 = 7;
    LODWORD(v83) = 7;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v6 + 8LL))(*v6, &v100) )
      goto LABEL_6;
    v106 = 0;
    v107 = 0;
    v108 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v106, L"Orchestrator");
    v7 = web::json::value::at(a2, &v106);
    v97 = 0;
    v98 = 0;
    v99 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v97, L"UpdateExpeditePayload");
    v8 = (_QWORD *)web::json::value::at(v7, &v97);
    v94 = 0;
    v95 = 0;
    v96 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v94, L"PolicyId");
    v5 = 63;
    LODWORD(v83) = 63;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v8 + 8LL))(*v8, &v94) )
      goto LABEL_6;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v80, L"Orchestrator");
    LODWORD(v83) = 127;
    v9 = web::json::value::at(a2, &v80);
    v87 = 0;
    v88 = 0;
    v89 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v87, L"UpdateExpeditePayload");
    LODWORD(v83) = 255;
    v10 = web::json::value::at(v9, &v87);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v84, L"PolicyId");
    v5 = 511;
    LODWORD(v83) = 511;
    v11 = (_QWORD *)web::json::value::at(v10, &v84);
    v12 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 88LL))(*v11) == 5 )
LABEL_6:
      v12 = 1;
    if ( (v5 & 0x100) != 0 )
    {
      v5 &= ~0x100u;
      std::wstring::~wstring(&v84);
    }
    if ( (v5 & 0x80u) != 0 )
    {
      v5 &= ~0x80u;
      std::wstring::~wstring(&v87);
    }
    if ( (v5 & 0x40) != 0 )
    {
      v5 &= ~0x40u;
      std::wstring::~wstring(&v80);
    }
    if ( (v5 & 0x20) != 0 )
    {
      v5 &= ~0x20u;
      std::wstring::~wstring(&v94);
    }
    if ( (v5 & 0x10) != 0 )
    {
      v5 &= ~0x10u;
      std::wstring::~wstring(&v97);
    }
    if ( (v5 & 8) != 0 )
    {
      v5 &= ~8u;
      std::wstring::~wstring(&v106);
    }
    if ( (v5 & 4) != 0 )
    {
      v5 &= ~4u;
      std::wstring::~wstring(&v100);
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      std::wstring::~wstring(&v103);
    }
    if ( (v5 & 1) != 0 )
    {
      v5 &= ~1u;
      std::wstring::~wstring(&v90);
    }
    if ( v12 )
    {
      Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
      return;
    }
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator");
    v13 = web::json::value::at(a2, &v100);
    v103 = 0;
    v104 = 0;
    v105 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v103, L"UpdateExpeditePayload");
    v14 = web::json::value::at(v13, &v103);
    v90 = 0;
    v91 = 0;
    v92 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v90, L"PolicyId");
    v15 = (_QWORD *)web::json::value::at(v14, &v90);
    v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 176LL))(*v15);
    std::wstring::wstring(v114, v16);
    std::wstring::~wstring(&v90);
    std::wstring::~wstring(&v103);
    std::wstring::~wstring(&v100);
    v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v80, L"Orchestrator");
    v17 = web::json::value::at(a2, &v80);
    v87 = 0;
    v88 = 0;
    v89 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v87, L"UpdateExpeditePayload");
    v18 = web::json::value::at(v17, &v87);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v84, L"UBR");
    v19 = (_QWORD *)web::json::value::at(v18, &v84);
    v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 128LL))(*v19);
    std::wstring::~wstring(&v84);
    std::wstring::~wstring(&v87);
    std::wstring::~wstring(&v80);
    v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v80, L"Orchestrator");
    v21 = web::json::value::at(a2, &v80);
    v87 = 0;
    v88 = 0;
    v89 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v87, L"UpdateExpeditePayload");
    v22 = web::json::value::at(v21, &v87);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v84, L"DaysUntilForcedReboot");
    v23 = (_QWORD *)web::json::value::at(v22, &v84);
    LODWORD(v97) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 128LL))(*v23);
    std::wstring::~wstring(&v84);
    std::wstring::~wstring(&v87);
    std::wstring::~wstring(&v80);
    v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v80, L"Orchestrator");
    v24 = web::json::value::at(a2, &v80);
    v87 = 0;
    v88 = 0;
    v89 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v87, L"UpdateExpeditePayload");
    v25 = web::json::value::at(v24, &v87);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v84, L"QUDeferral");
    v26 = (_QWORD *)web::json::value::at(v25, &v84);
    LODWORD(v106) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 128LL))(*v26);
    std::wstring::~wstring(&v84);
    std::wstring::~wstring(&v87);
    std::wstring::~wstring(&v80);
    v94 = 0;
    v95 = 0;
    v96 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v94, L"%Y-%m-%d", 8);
    v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v80, L"Orchestrator", 12);
    v27 = web::json::value::at(a2, &v80);
    v87 = 0;
    v88 = 0;
    v89 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v87, L"UpdateExpeditePayload", 21);
    v28 = web::json::value::at(v27, &v87);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v84, L"PolicyExpirationDate", 20);
    v29 = (_QWORD *)web::json::value::at(v28, &v84);
    v30 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 176LL))(*v29);
    Time::from_local_wstring(&v109, v30, &v94);
    std::wstring::~wstring(&v84);
    std::wstring::~wstring(&v87);
    std::wstring::~wstring(&v80);
    std::wstring::~wstring(&v94);
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"PolicyId",
                                           word_14040378A,
                                           0);
    if ( traits_2_unsigned_short == word_14040378A
      || (v34 = ((char *)traits_2_unsigned_short - (char *)L"PolicyId") >> 1, v35 = -1, v34 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v32);
    }
    *(_QWORD *)&v83 = L"PolicyId";
    *((_QWORD *)&v83 + 1) = v34;
    v80 = v83;
    UpdateDatabase::GetExpediteVariable(v33, v111, &v80);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)Time::IsPast(&v109) )
      {
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        *(_QWORD *)&v97 = L"Expedite: policy not applicable - policy expiration time: {}";
        *((_QWORD *)&v97 + 1) = 60;
        v80 = v97;
        SystemInterface::Log<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &>(
          &v80,
          &v109);
        goto LABEL_55;
      }
    }
    else
    {
      v40 = 1;
      if ( !(unsigned __int8)Time::IsPast(&v109) )
      {
        System = SystemInterface::Providers::GetSystem(&v94);
        v37 = v5 | 0x200;
        LODWORD(v83) = v37;
        v38 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v39 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v38 + 64LL))(v38, &v80);
        v5 = v37 | 0x400;
        LODWORD(v83) = v5;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 184LL))(*v39) < v20 )
          v40 = 0;
      }
      if ( (v5 & 0x400) != 0 )
      {
        LOWORD(v5) = v5 & 0xFBFF;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v80);
      }
      if ( (v5 & 0x200) != 0 )
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v94);
      if ( v40 )
      {
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        v41 = SystemInterface::Providers::GetSystem(&v106);
        v42 = *(_QWORD *)v41 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v41 + 8LL) + 4LL);
        v43 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v42 + 64LL))(v42, &v94);
        LODWORD(v83) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 184LL))(*v43);
        *(_QWORD *)&v97 = L"Expedite: policy not applicable - policy expiration time: {}, current UBR: {}";
        *((_QWORD *)&v97 + 1) = 77;
        v80 = v97;
        SystemInterface::Log<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,unsigned int>(
          &v80,
          &v109,
          &v83);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v94);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v106);
LABEL_55:
        if ( v113 && v112 != -1 && v112 && v112 != 1 && (unsigned __int64)(v112 - 2LL) >= 2 )
          std::wstring::~wstring(v111);
        v59 = v114;
        goto LABEL_62;
      }
    }
    v44 = *((_QWORD *)this + 1);
    std::wstring::wstring(&v90, v114);
    v93 = 4;
    v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"PolicyId");
    UpdateDatabase::SetExpediteVariable(v44, &v80, &v90);
    v45 = *((_QWORD *)this + 1);
    LODWORD(v90) = v20;
    v93 = 2;
    v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"UBR");
    UpdateDatabase::SetExpediteVariable(v45, &v80, &v90);
    v46 = *((_QWORD *)this + 1);
    LODWORD(v90) = v106;
    v93 = 2;
    v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"QUDeferralInDays");
    UpdateDatabase::SetExpediteVariable(v46, &v80, &v90);
    v47 = *((_QWORD *)this + 1);
    LODWORD(v90) = v97;
    v93 = 2;
    v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"DaysUntilForcedReboot");
    UpdateDatabase::SetExpediteVariable(v47, &v80, &v90);
    v48 = *((_QWORD *)this + 1);
    *(_QWORD *)&v90 = Time::to_ms(&v109);
    v93 = 3;
    v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"PolicyExpirationTime");
    UpdateDatabase::SetExpediteVariable(v48, &v80, &v90);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    v49 = web::json::value::at(a2, &v100);
    v103 = 0;
    v104 = 0;
    v105 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v103, L"UpdateExpeditePayload", 21);
    v50 = web::json::value::at(v49, &v103);
    v90 = 0;
    v91 = 0;
    v92 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v90, L"NonSecurityRelease", 18);
    v51 = (_QWORD *)web::json::value::at(v50, &v90);
    LODWORD(v50) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v51 + 128LL))(*v51);
    std::wstring::~wstring(&v90);
    std::wstring::~wstring(&v103);
    std::wstring::~wstring(&v100);
    if ( (_DWORD)v50 == 1 )
      Windows::Graph::GraphProvider::SetNonSecurityRelease(this, v20);
    if ( !v113 )
      goto LABEL_48;
    if ( v112 != 4 )
      std::_Throw_bad_variant_access();
    if ( !(unsigned __int8)std::operator==<wchar_t>(v111, v114) )
    {
LABEL_48:
      v52 = *((_QWORD *)this + 1);
      v53 = std::chrono::system_clock::now(&v97);
      *(_QWORD *)&v90 = Time::to_ms(v53);
      v93 = 3;
      v80 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v84, L"PolicyDiscoveryTime");
      UpdateDatabase::SetExpediteVariable(v52, &v80, &v90);
      v54 = SystemInterface::Providers::GetSystem(&v84);
      v55 = *(_QWORD *)v54 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v54 + 8LL) + 4LL);
      v56 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v55 + 32LL))(v55, &v87);
      *(_QWORD *)&v97 = *(_QWORD *)std::chrono::system_clock::now(&v106) + 8640000000000LL;
      v57 = -1;
      do
        ++v57;
      while ( SystemInterface::Registry::BLOCK_FEATUREUPDATES_UNTIL[v57] );
      *(_QWORD *)&v83 = SystemInterface::Registry::BLOCK_FEATUREUPDATES_UNTIL;
      *((_QWORD *)&v83 + 1) = v57;
      v58 = -1;
      do
        ++v58;
      while ( SystemInterface::Registry::OS_UPGRADE_ROOT[v58] );
      *(_QWORD *)&v94 = SystemInterface::Registry::OS_UPGRADE_ROOT;
      *((_QWORD *)&v94 + 1) = v58;
      *(_QWORD *)&v80 = SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID;
      do
        ++v35;
      while ( SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID[v35] );
      *((_QWORD *)&v80 + 1) = v35;
      SystemInterface::Registry::SetSystemTime(
        v56,
        (unsigned int)&v80,
        (unsigned int)&v94,
        (unsigned int)&v83,
        (__int64)&v97);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v87);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v84);
      *(_QWORD *)&v80 = L"Expedite: policy is enabled, feature update blocked for 10 days";
      *((_QWORD *)&v80 + 1) = 63;
      v84 = v80;
      SystemInterface::Log<>(&v84);
    }
    goto LABEL_55;
  }
  v60 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                 L"GraphProvider",
                 &dword_14048625C,
                 0);
  if ( v60 == &dword_14048625C || (v63 = ((char *)v60 - (char *)L"GraphProvider") >> 1, v63 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v61);
  *(_QWORD *)&v80 = L"GraphProvider";
  *((_QWORD *)&v80 + 1) = v63;
  v84 = v80;
  UpdateDatabase::GetScanSuccessTime(v62, &v109, &v84);
  v64 = *((_QWORD *)this + 1);
  v65 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"PolicyExpirationTime",
                     word_140486F9A,
                     0);
  if ( v65 == word_140486F9A || (v68 = ((__int64)v65 - v67) >> 1, v68 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v66);
  *(_QWORD *)&v80 = v67;
  *((_QWORD *)&v80 + 1) = v68;
  v84 = v80;
  UpdateDatabase::GetExpediteVariable(v64, v111, &v84);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::GetImpl'::`2'::impl) )
  {
    if ( !v110 )
      goto LABEL_73;
    v109 += 8640000000000LL;
    if ( (unsigned __int8)Time::IsPast(&v109) )
      goto LABEL_73;
    if ( v113 )
    {
      if ( v112 != 3 )
        std::_Throw_bad_variant_access();
      v109 = 10000LL * v111[0];
      if ( (unsigned __int8)Time::IsPast(&v109) )
      {
LABEL_73:
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        *(_QWORD *)&v80 = L"Expedite: no successful scans, clearing any active policy";
        *((_QWORD *)&v80 + 1) = 57;
        v84 = v80;
        SystemInterface::Log<>(&v84);
      }
    }
    goto LABEL_100;
  }
  v69 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"UBR",
                     L"OSMigrationDetection",
                     0);
  if ( v69 == L"OSMigrationDetection" || (v72 = v69 - L"UBR", v72 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v70);
  *(_QWORD *)&v80 = L"UBR";
  *((_QWORD *)&v80 + 1) = v72;
  v84 = v80;
  UpdateDatabase::GetExpediteVariable(v71, v114, &v84);
  if ( !v110 )
    goto LABEL_87;
  v73 = v109 + 8640000000000LL;
  v109 = 0;
  GetSystemTimePreciseAsFileTime(&v109);
  v74 = (unsigned int)v109 + ((unsigned __int64)HIDWORD(v109) << 32) - 116444736000000000LL;
  if ( v73 != v74 && v73 < v74 )
    goto LABEL_87;
  if ( v116 )
  {
    v75 = SystemInterface::Providers::GetSystem(&v87);
    LODWORD(v83) = 2048;
    v76 = *(_QWORD *)v75 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v75 + 8LL) + 4LL);
    v77 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v76 + 64LL))(v76, &v84);
    v4 = 6144;
    LODWORD(v83) = 6144;
    if ( !v116 )
      std::_Throw_bad_optional_access();
    if ( v115 != 2 )
      goto LABEL_112;
    v78 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v77 + 184LL))(*v77);
    if ( v78 >= v114[0] )
      goto LABEL_87;
  }
  if ( v113 )
  {
    if ( v112 == 3 )
    {
      v109 = 10000LL * v111[0];
      if ( !(unsigned __int8)Time::IsPast(&v109) )
        goto LABEL_86;
LABEL_87:
      v79 = 1;
      goto LABEL_88;
    }
LABEL_112:
    std::_Throw_bad_variant_access();
  }
LABEL_86:
  v79 = 0;
LABEL_88:
  if ( (v4 & 0x1000) != 0 )
  {
    v4 &= ~0x1000u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v84);
  }
  if ( (v4 & 0x800) != 0 )
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v87);
  if ( v79 )
  {
    Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
    *(_QWORD *)&v80 = L"Expedite: no successful scans, clearing any active policy";
    *((_QWORD *)&v80 + 1) = 57;
    v84 = v80;
    SystemInterface::Log<>(&v84);
  }
  if ( v116 && v115 != -1 && v115 && v115 != 1 && (unsigned __int64)(v115 - 2LL) >= 2 )
    std::wstring::~wstring(v114);
LABEL_100:
  if ( v113 && v112 != -1 && v112 && v112 != 1 && (unsigned __int64)(v112 - 2LL) >= 2 )
  {
    v59 = v111;
LABEL_62:
    std::wstring::~wstring(v59);
  }
}

```

## disassembly

```asm
0x1403680bc  mov     [rsp-8+arg_10], rbx
0x1403680c1  push    rbp
0x1403680c2  push    rsi
0x1403680c3  push    rdi
0x1403680c4  push    r12
0x1403680c6  push    r13
0x1403680c8  push    r14
0x1403680ca  push    r15
0x1403680cc  lea     rbp, [rsp-0F0h]
0x1403680d4  sub     rsp, 1F0h
0x1403680db  mov     rax, cs:__security_cookie
0x1403680e2  xor     rax, rsp
0x1403680e5  mov     [rbp+120h+var_40], rax
0x1403680ec  mov     r15, rdx
0x1403680ef  mov     rsi, rcx
0x1403680f2  xor     r14d, r14d
0x1403680f5  mov     ebx, r14d
0x1403680f8  mov     dword ptr [rsp+220h+var_1D0], ebx
0x1403680fc  cmp     [rdx+8], r14b
0x140368100  jz      loc_140368E83
0x140368106  xorps   xmm0, xmm0
0x140368109  movups  [rbp+120h+var_180], xmm0
0x14036810d  mov     [rbp+120h+var_170], r14
0x140368111  mov     [rbp+120h+var_168], r14
0x140368115  lea     r12d, [r14+0Ch]
0x140368119  mov     r8d, r12d
0x14036811c  lea     r13, aOrchestrator; "Orchestrator"
0x140368123  mov     rdx, r13
0x140368126  lea     rcx, [rbp+120h+var_180]
0x14036812a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036812f  nop
0x140368130  lea     edi, [r14+1]
0x140368134  mov     dword ptr [rsp+220h+var_1D0], edi
0x140368138  mov     rcx, [r15]
0x14036813b  mov     rax, [rcx]
0x14036813e  lea     rdx, [rbp+120h+var_180]
0x140368142  mov     rax, [rax+8]
0x140368146  call    _guard_dispatch_icall
0x14036814b  test    al, al
0x14036814d  jz      loc_140368353
0x140368153  xorps   xmm0, xmm0
0x140368156  movups  [rbp+120h+var_F0], xmm0
0x14036815a  mov     [rbp+120h+var_E0], r14
0x14036815e  mov     [rbp+120h+var_D8], r14
0x140368162  mov     r8d, r12d
0x140368165  mov     rdx, r13
0x140368168  lea     rcx, [rbp+120h+var_F0]
0x14036816c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140368171  nop
0x140368172  mov     dword ptr [rsp+220h+var_1D0], 3
0x14036817a  lea     rdx, [rbp+120h+var_F0]
0x14036817e  mov     rcx, r15
0x140368181  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140368186  mov     rbx, rax
0x140368189  xorps   xmm0, xmm0
0x14036818c  movups  [rbp+120h+var_110], xmm0
0x140368190  mov     [rbp+120h+var_100], r14
0x140368194  mov     [rbp+120h+var_F8], r14
0x140368198  lea     r8d, [r14+15h]
0x14036819c  lea     rdx, aUpdateexpedite; "UpdateExpeditePayload"
0x1403681a3  lea     rcx, [rbp+120h+var_110]
0x1403681a7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403681ac  nop
0x1403681ad  lea     edi, [r14+7]
0x1403681b1  mov     dword ptr [rsp+220h+var_1D0], edi
0x1403681b5  mov     rcx, [rbx]
0x1403681b8  mov     rax, [rcx]
0x1403681bb  lea     rdx, [rbp+120h+var_110]
0x1403681bf  mov     rax, [rax+8]
0x1403681c3  call    _guard_dispatch_icall
0x1403681c8  test    al, al
0x1403681ca  jz      loc_140368353
0x1403681d0  xorps   xmm0, xmm0
0x1403681d3  movups  [rbp+120h+var_D0], xmm0
0x1403681d7  mov     [rbp+120h+var_C0], r14
0x1403681db  mov     [rbp+120h+var_B8], r14
0x1403681df  mov     r8d, r12d
0x1403681e2  mov     rdx, r13
0x1403681e5  lea     rcx, [rbp+120h+var_D0]
0x1403681e9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403681ee  nop
0x1403681ef  mov     dword ptr [rsp+220h+var_1D0], 0Fh
0x1403681f7  lea     rdx, [rbp+120h+var_D0]
0x1403681fb  mov     rcx, r15
0x1403681fe  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140368203  mov     rbx, rax
0x140368206  xorps   xmm0, xmm0
0x140368209  movups  [rbp+120h+var_130], xmm0
0x14036820d  mov     [rbp+120h+var_120], r14
0x140368211  mov     [rbp+120h+var_118], r14
0x140368215  lea     r8d, [r14+15h]
0x140368219  lea     rdx, aUpdateexpedite; "UpdateExpeditePayload"
0x140368220  lea     rcx, [rbp+120h+var_130]
0x140368224  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140368229  nop
0x14036822a  mov     dword ptr [rsp+220h+var_1D0], 1Fh
0x140368232  lea     rdx, [rbp+120h+var_130]
0x140368236  mov     rcx, rbx
0x140368239  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14036823e  mov     rbx, rax
0x140368241  xorps   xmm0, xmm0
0x140368244  movups  [rbp+120h+var_150], xmm0
0x140368248  mov     [rbp+120h+var_140], r14
0x14036824c  mov     [rbp+120h+var_138], r14
0x140368250  lea     r8d, [r14+8]
0x140368254  lea     rdx, aPolicyid; "PolicyId"
0x14036825b  lea     rcx, [rbp+120h+var_150]
0x14036825f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140368264  nop
0x140368265  lea     edi, [r14+3Fh]
0x140368269  mov     dword ptr [rsp+220h+var_1D0], edi
0x14036826d  mov     rcx, [rbx]
0x140368270  mov     rax, [rcx]
0x140368273  lea     rdx, [rbp+120h+var_150]
0x140368277  mov     rax, [rax+8]
0x14036827b  call    _guard_dispatch_icall
0x140368280  test    al, al
0x140368282  jz      loc_140368353
0x140368288  xorps   xmm0, xmm0
0x14036828b  movups  [rsp+220h+var_1F0], xmm0
0x140368290  mov     [rsp+220h+var_1E0], r14
0x140368295  mov     [rsp+220h+var_1D8], r14
0x14036829a  mov     r8d, r12d
0x14036829d  mov     rdx, r13
0x1403682a0  lea     rcx, [rsp+220h+var_1F0]
0x1403682a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403682aa  nop
0x1403682ab  mov     dword ptr [rsp+220h+var_1D0], 7Fh
0x1403682b3  lea     rdx, [rsp+220h+var_1F0]
0x1403682b8  mov     rcx, r15
0x1403682bb  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1403682c0  mov     rbx, rax
0x1403682c3  xorps   xmm0, xmm0
0x1403682c6  movups  [rbp+120h+var_1A0], xmm0
0x1403682ca  mov     [rbp+120h+var_190], r14
0x1403682ce  mov     [rbp+120h+var_188], r14
0x1403682d2  lea     r8d, [r14+15h]
0x1403682d6  lea     rdx, aUpdateexpedite; "UpdateExpeditePayload"
0x1403682dd  lea     rcx, [rbp+120h+var_1A0]
0x1403682e1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403682e6  nop
0x1403682e7  mov     dword ptr [rsp+220h+var_1D0], 0FFh
0x1403682ef  lea     rdx, [rbp+120h+var_1A0]
0x1403682f3  mov     rcx, rbx
0x1403682f6  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1403682fb  mov     rbx, rax
0x1403682fe  xorps   xmm0, xmm0
0x140368301  movups  [rsp+220h+var_1C0], xmm0
0x140368306  mov     [rsp+220h+var_1B0], r14
0x14036830b  mov     [rsp+220h+var_1A8], r14
0x140368310  lea     r8d, [r14+8]
0x140368314  lea     rdx, aPolicyid; "PolicyId"
0x14036831b  lea     rcx, [rsp+220h+var_1C0]
0x140368320  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140368325  nop
0x140368326  mov     edi, 1FFh
0x14036832b  mov     dword ptr [rsp+220h+var_1D0], edi
0x14036832f  lea     rdx, [rsp+220h+var_1C0]
0x140368334  mov     rcx, rbx
0x140368337  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x14036833c  mov     rcx, [rax]
0x14036833f  mov     rax, [rcx]
0x140368342  mov     rax, [rax+58h]
0x140368346  call    _guard_dispatch_icall
0x14036834b  cmp     eax, 5
0x14036834e  mov     bl, r14b
0x140368351  jnz     short loc_140368355
0x140368353  mov     bl, 1
0x140368355  bt      edi, 8
0x140368359  jnb     short loc_14036836A
0x14036835b  btr     edi, 8
0x14036835f  lea     rcx, [rsp+220h+var_1C0]
0x140368364  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140368369  nop
0x14036836a  test    dil, dil
0x14036836d  jns     short loc_14036837D
0x14036836f  btr     edi, 7
0x140368373  lea     rcx, [rbp+120h+var_1A0]
0x140368377  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14036837c  nop
0x14036837d  test    dil, 40h
0x140368381  jz      short loc_140368391
0x140368383  and     edi, 0FFFFFFBFh
0x140368386  lea     rcx, [rsp+220h+var_1F0]
0x14036838b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140368390  nop
0x140368391  test    dil, 20h
0x140368395  jz      short loc_1403683A4
0x140368397  and     edi, 0FFFFFFDFh
0x14036839a  lea     rcx, [rbp+120h+var_150]
0x14036839e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403683a3  nop
0x1403683a4  test    dil, 10h
0x1403683a8  jz      short loc_1403683B7
0x1403683aa  and     edi, 0FFFFFFEFh
0x1403683ad  lea     rcx, [rbp+120h+var_130]
0x1403683b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403683b6  nop
0x1403683b7  test    dil, 8
0x1403683bb  jz      short loc_1403683CA
0x1403683bd  and     edi, 0FFFFFFF7h
0x1403683c0  lea     rcx, [rbp+120h+var_D0]
0x1403683c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403683c9  nop
0x1403683ca  test    dil, 4
0x1403683ce  jz      short loc_1403683DD
0x1403683d0  and     edi, 0FFFFFFFBh
0x1403683d3  lea     rcx, [rbp+120h+var_110]
0x1403683d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403683dc  nop
0x1403683dd  test    dil, 2
0x1403683e1  jz      short loc_1403683F0
0x1403683e3  and     edi, 0FFFFFFFDh
0x1403683e6  lea     rcx, [rbp+120h+var_F0]
0x1403683ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403683ef  nop
0x1403683f0  test    dil, 1
0x1403683f4  jz      short loc_140368402
0x1403683f6  and     edi, 0FFFFFFFEh
0x1403683f9  lea     rcx, [rbp+120h+var_180]
0x1403683fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140368402  test    bl, bl
0x140368404  jz      short loc_140368438
0x140368406  mov     rcx, rsi; this
0x140368409  call    ?ClearExpeditePolicy@GraphProvider@Graph@Windows@@AEAAXXZ; Windows::Graph::GraphProvider::ClearExpeditePolicy(void)
0x14036840e  mov     rcx, [rbp+120h+var_40]
0x140368415  xor     rcx, rsp; StackCookie
0x140368418  call    __security_check_cookie
0x14036841d  mov     rbx, [rsp+220h+arg_10]
0x140368425  add     rsp, 1F0h
0x14036842c  pop     r15
0x14036842e  pop     r14
0x140368430  pop     r13
0x140368432  pop     r12
0x140368434  pop     rdi
0x140368435  pop     rsi
0x140368436  pop     rbp
0x140368437  retn
0x140368438  xorps   xmm0, xmm0
0x14036843b  movups  [rbp+120h+var_110], xmm0
0x14036843f  mov     [rbp+120h+var_100], r14
0x140368443  mov     [rbp+120h+var_F8], r14
0x140368447  mov     r8, r12
0x14036844a  mov     rdx, r13
0x14036844d  lea     rcx, [rbp+120h+var_110]
0x140368451  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140368456  nop
0x140368457  lea     rdx, [rbp+120h+var_110]
0x14036845b  mov     rcx, r15
0x14036845e  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140368463  mov     rbx, rax
0x140368466  xorps   xmm0, xmm0
0x140368469  movups  [rbp+120h+var_F0], xmm0
0x14036846d  mov     [rbp+120h+var_E0], r14
0x140368471  mov     [rbp+120h+var_D8], r14
0x140368475  mov     r8d, 15h
0x14036847b  lea     rdx, aUpdateexpedite; "UpdateExpeditePayload"
0x140368482  lea     rcx, [rbp+120h+var_F0]
0x140368486  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036848b  nop
0x14036848c  lea     rdx, [rbp+120h+var_F0]
0x140368490  mov     rcx, rbx
0x140368493  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140368498  mov     rbx, rax
0x14036849b  xorps   xmm0, xmm0
0x14036849e  movups  [rbp+120h+var_180], xmm0
0x1403684a2  mov     [rbp+120h+var_170], r14
0x1403684a6  mov     [rbp+120h+var_168], r14
0x1403684aa  mov     r8d, 8
0x1403684b0  lea     rdx, aPolicyid; "PolicyId"
0x1403684b7  lea     rcx, [rbp+120h+var_180]
0x1403684bb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403684c0  nop
0x1403684c1  lea     rdx, [rbp+120h+var_180]
0x1403684c5  mov     rcx, rbx
0x1403684c8  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1403684cd  mov     rcx, [rax]
0x1403684d0  mov     rax, [rcx]
0x1403684d3  mov     rax, [rax+0B0h]
0x1403684da  call    _guard_dispatch_icall
0x1403684df  mov     rdx, rax
0x1403684e2  lea     rcx, [rbp+120h+var_70]
0x1403684e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1403684ee  nop
0x1403684ef  lea     rcx, [rbp+120h+var_180]
0x1403684f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403684f8  nop
0x1403684f9  lea     rcx, [rbp+120h+var_F0]
0x1403684fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140368502  nop
0x140368503  lea     rcx, [rbp+120h+var_110]
0x140368507  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14036850c  xorps   xmm0, xmm0
0x14036850f  movups  [rsp+220h+var_1F0], xmm0
0x140368514  mov     [rsp+220h+var_1E0], r14
0x140368519  mov     [rsp+220h+var_1D8], r14
0x14036851e  mov     r8, r12
0x140368521  mov     rdx, r13
0x140368524  lea     rcx, [rsp+220h+var_1F0]
0x140368529  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
  ... truncated ...
```
