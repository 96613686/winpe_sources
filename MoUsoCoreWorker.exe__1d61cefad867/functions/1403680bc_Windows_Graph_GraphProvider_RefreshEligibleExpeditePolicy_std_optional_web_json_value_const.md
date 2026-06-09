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
  __int64 v6; // rdx
  _QWORD *v7; // rbx
  __int64 v8; // rbx
  _QWORD *v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  _QWORD *v12; // rax
  char v13; // bl
  __int64 v14; // rbx
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  unsigned int v24; // r13d
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rbx
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rbx
  __int64 v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rbx
  __int64 v41; // rbx
  _QWORD *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int16 *traits_2_unsigned_short; // rax
  const char *v49; // r9
  __int64 v50; // r11
  __int64 v51; // rax
  __int64 v52; // r14
  signed __int64 v53; // rdx
  __int64 System; // rax
  int v55; // edi
  __int64 v56; // rcx
  _QWORD *v57; // rax
  bool v58; // bl
  __int64 v59; // rax
  __int64 v60; // rcx
  _QWORD *v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rbx
  __int64 v64; // rbx
  __int64 v65; // rbx
  __int64 v66; // rbx
  __int64 v67; // rbx
  __int64 v68; // rbx
  _QWORD *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // rax
  __int64 v79; // rax
  _QWORD *v80; // rcx
  int *v81; // rax
  const char *v82; // r9
  __int64 v83; // r11
  __int64 v84; // rax
  __int64 v85; // rdi
  __int16 *v86; // rax
  const char *v87; // r9
  __int64 v88; // r11
  __int64 v89; // rax
  wchar_t *v90; // rax
  const char *v91; // r9
  __int64 v92; // r11
  __int64 v93; // rax
  signed __int64 v94; // rdi
  __int64 v95; // rax
  __int64 v96; // rcx
  _QWORD *v97; // rax
  unsigned int v98; // eax
  char v99; // di
  __int128 v100; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v101; // [rsp+40h] [rbp-C0h]
  __int64 v102; // [rsp+48h] [rbp-B8h]
  __int128 v103; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v104; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v105; // [rsp+70h] [rbp-90h]
  __int64 v106; // [rsp+78h] [rbp-88h]
  __int128 v107; // [rsp+80h] [rbp-80h] BYREF
  __int64 v108; // [rsp+90h] [rbp-70h]
  __int64 v109; // [rsp+98h] [rbp-68h]
  __int128 v110; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-50h]
  __int64 v112; // [rsp+B8h] [rbp-48h]
  char v113; // [rsp+C0h] [rbp-40h]
  __int128 v114; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v115; // [rsp+E0h] [rbp-20h]
  __int64 v116; // [rsp+E8h] [rbp-18h]
  __int128 v117; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v118; // [rsp+100h] [rbp+0h]
  __int64 v119; // [rsp+108h] [rbp+8h]
  __int128 v120; // [rsp+110h] [rbp+10h] BYREF
  __int64 v121; // [rsp+120h] [rbp+20h]
  __int64 v122; // [rsp+128h] [rbp+28h]
  __int128 v123; // [rsp+130h] [rbp+30h] BYREF
  __int64 v124; // [rsp+140h] [rbp+40h]
  __int64 v125; // [rsp+148h] [rbp+48h]
  __int128 v126; // [rsp+150h] [rbp+50h] BYREF
  __int64 v127; // [rsp+160h] [rbp+60h]
  __int64 v128; // [rsp+168h] [rbp+68h]
  __int64 v129; // [rsp+170h] [rbp+70h] BYREF
  char v130; // [rsp+178h] [rbp+78h]
  _QWORD v131[4]; // [rsp+180h] [rbp+80h] BYREF
  char v132; // [rsp+1A0h] [rbp+A0h]
  char v133; // [rsp+1A8h] [rbp+A8h]
  _DWORD v134[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v135; // [rsp+1D0h] [rbp+D0h]
  char v136; // [rsp+1D8h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v4 = 0;
  LODWORD(v103) = 0;
  if ( a2[8] )
  {
    v110 = 0;
    v111 = 0;
    v112 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v110, L"Orchestrator", 12);
    v5 = 1;
    LODWORD(v103) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, &v110) )
      goto LABEL_6;
    v123 = 0;
    v124 = 0;
    v125 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v123, L"Orchestrator", 12);
    v7 = (_QWORD *)web::json::value::at(a2, &v123);
    v120 = 0;
    v121 = 0;
    v122 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v120, L"UpdateExpeditePayload", 21);
    v5 = 7;
    LODWORD(v103) = 7;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v7 + 8LL))(*v7, &v120) )
      goto LABEL_6;
    v126 = 0;
    v127 = 0;
    v128 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v126, L"Orchestrator", 12);
    v8 = web::json::value::at(a2, &v126);
    v117 = 0;
    v118 = 0;
    v119 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v117, L"UpdateExpeditePayload", 21);
    v9 = (_QWORD *)web::json::value::at(v8, &v117);
    v114 = 0;
    v115 = 0;
    v116 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v114, L"PolicyId", 8);
    v5 = 63;
    LODWORD(v103) = 63;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v9 + 8LL))(*v9, &v114) )
      goto LABEL_6;
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    LODWORD(v103) = 127;
    v10 = web::json::value::at(a2, &v100);
    v107 = 0;
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v107, L"UpdateExpeditePayload", 21);
    LODWORD(v103) = 255;
    v11 = web::json::value::at(v10, &v107);
    v104 = 0;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v104, L"PolicyId", 8);
    v5 = 511;
    LODWORD(v103) = 511;
    v12 = (_QWORD *)web::json::value::at(v11, &v104);
    v13 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 88LL))(*v12) == 5 )
LABEL_6:
      v13 = 1;
    if ( (v5 & 0x100) != 0 )
    {
      v5 &= ~0x100u;
      std::wstring::~wstring(&v104, v6);
    }
    if ( (v5 & 0x80u) != 0 )
    {
      v5 &= ~0x80u;
      std::wstring::~wstring(&v107, v6);
    }
    if ( (v5 & 0x40) != 0 )
    {
      v5 &= ~0x40u;
      std::wstring::~wstring(&v100, v6);
    }
    if ( (v5 & 0x20) != 0 )
    {
      v5 &= ~0x20u;
      std::wstring::~wstring(&v114, v6);
    }
    if ( (v5 & 0x10) != 0 )
    {
      v5 &= ~0x10u;
      std::wstring::~wstring(&v117, v6);
    }
    if ( (v5 & 8) != 0 )
    {
      v5 &= ~8u;
      std::wstring::~wstring(&v126, v6);
    }
    if ( (v5 & 4) != 0 )
    {
      v5 &= ~4u;
      std::wstring::~wstring(&v120, v6);
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      std::wstring::~wstring(&v123, v6);
    }
    if ( (v5 & 1) != 0 )
    {
      v5 &= ~1u;
      std::wstring::~wstring(&v110, v6);
    }
    if ( v13 )
    {
      Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
      return;
    }
    v120 = 0;
    v121 = 0;
    v122 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v120, L"Orchestrator", 12);
    v14 = web::json::value::at(a2, &v120);
    v123 = 0;
    v124 = 0;
    v125 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v123, L"UpdateExpeditePayload", 21);
    v15 = web::json::value::at(v14, &v123);
    v110 = 0;
    v111 = 0;
    v112 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v110, L"PolicyId", 8);
    v16 = (_QWORD *)web::json::value::at(v15, &v110);
    v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 176LL))(*v16);
    std::wstring::wstring(v134, v17);
    std::wstring::~wstring(&v110, v18);
    std::wstring::~wstring(&v123, v19);
    std::wstring::~wstring(&v120, v20);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    v21 = web::json::value::at(a2, &v100);
    v107 = 0;
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v107, L"UpdateExpeditePayload", 21);
    v22 = web::json::value::at(v21, &v107);
    v104 = 0;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v104, L"UBR", 3);
    v23 = (_QWORD *)web::json::value::at(v22, &v104);
    v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 128LL))(*v23);
    std::wstring::~wstring(&v104, v25);
    std::wstring::~wstring(&v107, v26);
    std::wstring::~wstring(&v100, v27);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    v28 = web::json::value::at(a2, &v100);
    v107 = 0;
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v107, L"UpdateExpeditePayload", 21);
    v29 = web::json::value::at(v28, &v107);
    v104 = 0;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v104, L"DaysUntilForcedReboot", 21);
    v30 = (_QWORD *)web::json::value::at(v29, &v104);
    LODWORD(v117) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 128LL))(*v30);
    std::wstring::~wstring(&v104, v31);
    std::wstring::~wstring(&v107, v32);
    std::wstring::~wstring(&v100, v33);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    v34 = web::json::value::at(a2, &v100);
    v107 = 0;
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v107, L"UpdateExpeditePayload", 21);
    v35 = web::json::value::at(v34, &v107);
    v104 = 0;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v104, L"QUDeferral", 10);
    v36 = (_QWORD *)web::json::value::at(v35, &v104);
    LODWORD(v126) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 128LL))(*v36);
    std::wstring::~wstring(&v104, v37);
    std::wstring::~wstring(&v107, v38);
    std::wstring::~wstring(&v100, v39);
    v114 = 0;
    v115 = 0;
    v116 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v114, L"%Y-%m-%d", 8);
    v100 = 0;
    v101 = 0;
    v102 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v100, L"Orchestrator", 12);
    v40 = web::json::value::at(a2, &v100);
    v107 = 0;
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v107, L"UpdateExpeditePayload", 21);
    v41 = web::json::value::at(v40, &v107);
    v104 = 0;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v104, L"PolicyExpirationDate", 20);
    v42 = (_QWORD *)web::json::value::at(v41, &v104);
    v43 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 176LL))(*v42);
    Time::from_local_wstring(&v129, v43, &v114);
    std::wstring::~wstring(&v104, v44);
    std::wstring::~wstring(&v107, v45);
    std::wstring::~wstring(&v100, v46);
    std::wstring::~wstring(&v114, v47);
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"PolicyId",
                                           word_14040378A,
                                           0);
    if ( traits_2_unsigned_short == word_14040378A
      || (v51 = ((char *)traits_2_unsigned_short - (char *)L"PolicyId") >> 1, v52 = -1, v51 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v49);
    }
    *(_QWORD *)&v103 = L"PolicyId";
    *((_QWORD *)&v103 + 1) = v51;
    v100 = v103;
    UpdateDatabase::GetExpediteVariable(v50, v131, &v100);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)Time::IsPast(&v129) )
      {
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        *(_QWORD *)&v117 = L"Expedite: policy not applicable - policy expiration time: {}";
        *((_QWORD *)&v117 + 1) = 60;
        v100 = v117;
        SystemInterface::Log<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &>(
          &v100,
          &v129);
        goto LABEL_55;
      }
    }
    else
    {
      v58 = 1;
      if ( !(unsigned __int8)Time::IsPast(&v129) )
      {
        System = SystemInterface::Providers::GetSystem(&v114);
        v55 = v5 | 0x200;
        LODWORD(v103) = v55;
        v56 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
        v57 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v56 + 64LL))(v56, &v100);
        v5 = v55 | 0x400;
        LODWORD(v103) = v5;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v57 + 184LL))(*v57) < v24 )
          v58 = 0;
      }
      if ( (v5 & 0x400) != 0 )
      {
        LOWORD(v5) = v5 & 0xFBFF;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v100);
      }
      if ( (v5 & 0x200) != 0 )
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v114);
      if ( v58 )
      {
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        v59 = SystemInterface::Providers::GetSystem(&v126);
        v60 = *(_QWORD *)v59 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v59 + 8LL) + 4LL);
        v61 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v60 + 64LL))(v60, &v114);
        LODWORD(v103) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v61 + 184LL))(*v61);
        *(_QWORD *)&v117 = L"Expedite: policy not applicable - policy expiration time: {}, current UBR: {}";
        *((_QWORD *)&v117 + 1) = 77;
        v100 = v117;
        SystemInterface::Log<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,unsigned int>(
          &v100,
          &v129,
          &v103);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v114);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v126);
LABEL_55:
        if ( v133 && v132 != -1 && v132 && v132 != 1 && (unsigned __int64)(v132 - 2LL) >= 2 )
          std::wstring::~wstring(v131, v53);
        v80 = v134;
        goto LABEL_62;
      }
    }
    v62 = *((_QWORD *)this + 1);
    std::wstring::wstring(&v110, v134);
    v113 = 4;
    v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"PolicyId");
    UpdateDatabase::SetExpediteVariable(v62, &v100, &v110);
    v63 = *((_QWORD *)this + 1);
    LODWORD(v110) = v24;
    v113 = 2;
    v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"UBR");
    UpdateDatabase::SetExpediteVariable(v63, &v100, &v110);
    v64 = *((_QWORD *)this + 1);
    LODWORD(v110) = v126;
    v113 = 2;
    v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"QUDeferralInDays");
    UpdateDatabase::SetExpediteVariable(v64, &v100, &v110);
    v65 = *((_QWORD *)this + 1);
    LODWORD(v110) = v117;
    v113 = 2;
    v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"DaysUntilForcedReboot");
    UpdateDatabase::SetExpediteVariable(v65, &v100, &v110);
    v66 = *((_QWORD *)this + 1);
    *(_QWORD *)&v110 = Time::to_ms(&v129);
    v113 = 3;
    v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"PolicyExpirationTime");
    UpdateDatabase::SetExpediteVariable(v66, &v100, &v110);
    v120 = 0;
    v121 = 0;
    v122 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v120, L"Orchestrator", 12);
    v67 = web::json::value::at(a2, &v120);
    v123 = 0;
    v124 = 0;
    v125 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v123, L"UpdateExpeditePayload", 21);
    v68 = web::json::value::at(v67, &v123);
    v110 = 0;
    v111 = 0;
    v112 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v110, L"NonSecurityRelease", 18);
    v69 = (_QWORD *)web::json::value::at(v68, &v110);
    LODWORD(v68) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v69 + 128LL))(*v69);
    std::wstring::~wstring(&v110, v70);
    std::wstring::~wstring(&v123, v71);
    std::wstring::~wstring(&v120, v72);
    if ( (_DWORD)v68 == 1 )
      Windows::Graph::GraphProvider::SetNonSecurityRelease(this, v24);
    if ( !v133 )
      goto LABEL_48;
    if ( v132 != 4 )
      std::_Throw_bad_variant_access();
    if ( !(unsigned __int8)std::operator==<wchar_t>(v131, v134) )
    {
LABEL_48:
      v73 = *((_QWORD *)this + 1);
      v74 = std::chrono::system_clock::now(&v117);
      *(_QWORD *)&v110 = Time::to_ms(v74);
      v113 = 3;
      v100 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v104, L"PolicyDiscoveryTime");
      UpdateDatabase::SetExpediteVariable(v73, &v100, &v110);
      v75 = SystemInterface::Providers::GetSystem(&v104);
      v76 = *(_QWORD *)v75 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v75 + 8LL) + 4LL);
      v77 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v76 + 32LL))(v76, &v107);
      *(_QWORD *)&v117 = *(_QWORD *)std::chrono::system_clock::now(&v126) + 8640000000000LL;
      v78 = -1;
      do
        ++v78;
      while ( SystemInterface::Registry::BLOCK_FEATUREUPDATES_UNTIL[v78] );
      *(_QWORD *)&v103 = SystemInterface::Registry::BLOCK_FEATUREUPDATES_UNTIL;
      *((_QWORD *)&v103 + 1) = v78;
      v79 = -1;
      do
        ++v79;
      while ( SystemInterface::Registry::OS_UPGRADE_ROOT[v79] );
      *(_QWORD *)&v114 = SystemInterface::Registry::OS_UPGRADE_ROOT;
      *((_QWORD *)&v114 + 1) = v79;
      *(_QWORD *)&v100 = SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID;
      do
        ++v52;
      while ( SystemInterface::Registry::CURRENTVERSIONWU_REDIRECTION_ID[v52] );
      *((_QWORD *)&v100 + 1) = v52;
      SystemInterface::Registry::SetSystemTime(
        v77,
        (unsigned int)&v100,
        (unsigned int)&v114,
        (unsigned int)&v103,
        (__int64)&v117);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v107);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v104);
      *(_QWORD *)&v100 = L"Expedite: policy is enabled, feature update blocked for 10 days";
      *((_QWORD *)&v100 + 1) = 63;
      v104 = v100;
      SystemInterface::Log<>(&v104);
    }
    goto LABEL_55;
  }
  v81 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                 L"GraphProvider",
                 &dword_14048625C,
                 0);
  if ( v81 == &dword_14048625C || (v84 = ((char *)v81 - (char *)L"GraphProvider") >> 1, v84 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v82);
  *(_QWORD *)&v100 = L"GraphProvider";
  *((_QWORD *)&v100 + 1) = v84;
  v104 = v100;
  UpdateDatabase::GetScanSuccessTime(v83, &v129, &v104);
  v85 = *((_QWORD *)this + 1);
  v86 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"PolicyExpirationTime",
                     word_140486F9A,
                     0);
  if ( v86 == word_140486F9A || (v89 = ((__int64)v86 - v88) >> 1, v89 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v87);
  *(_QWORD *)&v100 = v88;
  *((_QWORD *)&v100 + 1) = v89;
  v104 = v100;
  UpdateDatabase::GetExpediteVariable(v85, v131, &v104);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ExpediteEvalBeforeScan>::GetImpl'::`2'::impl) )
  {
    if ( !v130 )
      goto LABEL_73;
    v129 += 8640000000000LL;
    if ( (unsigned __int8)Time::IsPast(&v129) )
      goto LABEL_73;
    if ( v133 )
    {
      if ( v132 != 3 )
        std::_Throw_bad_variant_access();
      v129 = 10000LL * v131[0];
      if ( (unsigned __int8)Time::IsPast(&v129) )
      {
LABEL_73:
        Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
        *(_QWORD *)&v100 = L"Expedite: no successful scans, clearing any active policy";
        *((_QWORD *)&v100 + 1) = 57;
        v104 = v100;
        SystemInterface::Log<>(&v104);
      }
    }
    goto LABEL_100;
  }
  v90 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"UBR",
                     L"OSMigrationDetection",
                     0);
  if ( v90 == L"OSMigrationDetection" || (v93 = v90 - L"UBR", v93 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v91);
  *(_QWORD *)&v100 = L"UBR";
  *((_QWORD *)&v100 + 1) = v93;
  v104 = v100;
  UpdateDatabase::GetExpediteVariable(v92, v134, &v104);
  if ( !v130 )
    goto LABEL_87;
  v94 = v129 + 8640000000000LL;
  v129 = 0;
  GetSystemTimePreciseAsFileTime(&v129);
  v53 = (unsigned int)v129 + ((unsigned __int64)HIDWORD(v129) << 32) - 116444736000000000LL;
  if ( v94 != v53 && v94 < v53 )
    goto LABEL_87;
  if ( v136 )
  {
    v95 = SystemInterface::Providers::GetSystem(&v107);
    LODWORD(v103) = 2048;
    v96 = *(_QWORD *)v95 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v95 + 8LL) + 4LL);
    v97 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v96 + 64LL))(v96, &v104);
    v4 = 6144;
    LODWORD(v103) = 6144;
    if ( !v136 )
      std::_Throw_bad_optional_access();
    if ( v135 != 2 )
      goto LABEL_112;
    v98 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v97 + 184LL))(*v97);
    if ( v98 >= v134[0] )
      goto LABEL_87;
  }
  if ( v133 )
  {
    if ( v132 == 3 )
    {
      v129 = 10000LL * v131[0];
      if ( !(unsigned __int8)Time::IsPast(&v129) )
        goto LABEL_86;
LABEL_87:
      v99 = 1;
      goto LABEL_88;
    }
LABEL_112:
    std::_Throw_bad_variant_access();
  }
LABEL_86:
  v99 = 0;
LABEL_88:
  if ( (v4 & 0x1000) != 0 )
  {
    v4 &= ~0x1000u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v104);
  }
  if ( (v4 & 0x800) != 0 )
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v107);
  if ( v99 )
  {
    Windows::Graph::GraphProvider::ClearExpeditePolicy(this);
    *(_QWORD *)&v100 = L"Expedite: no successful scans, clearing any active policy";
    *((_QWORD *)&v100 + 1) = 57;
    v104 = v100;
    SystemInterface::Log<>(&v104);
  }
  if ( v136 && v135 != -1 && v135 && v135 != 1 && (unsigned __int64)(v135 - 2LL) >= 2 )
    std::wstring::~wstring(v134, v53);
LABEL_100:
  if ( v133 && v132 != -1 && v132 && v132 != 1 && (unsigned __int64)(v132 - 2LL) >= 2 )
  {
    v80 = v131;
LABEL_62:
    std::wstring::~wstring(v80, v53);
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
