# Windows::Telemetry::UpdateManager::Scan::StartActivity(wil::basic_zstring_view<wchar_t>,ProviderType,wil::basic_zstring_view<wchar_t>,bool,bool,SystemInterface::Telemetry::CorrelationVector &,uint,wil::basic_zstring_view<wchar_t>)

- ea: `0x140271d18`
- end: `0x140272bc4`
- name: `?StartActivity@Scan@UpdateManager@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@W4ProviderType@@0_N2AEAVCorrelationVector@3SystemInterface@@I0@Z`
- size: `3756`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x14028e994`
- `0x14028eea0`

## callees

- `0x140001f74`
- `0x140007a7c`
- `0x140007cfc`
- `0x140007f08`
- `0x140021474`
- `0x14002a2a0`
- `0x14002cc08`
- `0x14002cd1c`
- `0x140040d18`
- `0x140043284`
- `0x140044f20`
- `0x140045404`
- `0x140045688`
- `0x14012d7d8`
- `0x140271d18`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140271f4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402722a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140272577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140272805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140271f4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402722a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140272577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140272805`

## string_xrefs

- `0x140271db5`: `WindowsUpdate`
- `0x1402726d1`: `WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall Windows::Telemetry::UpdateManager::Scan::StartActivity(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 *a4,
        char a5,
        char a6,
        __int64 a7,
        DWORD a8,
        __int64 *a9)
{
  int v13; // ebx
  const wchar_t *v14; // rdx
  __int64 v15; // r8
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // rdx
  int v18; // esi
  _QWORD *System; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rax
  int v26; // eax
  int v27; // eax
  const wchar_t *v28; // rdi
  __int128 *v29; // rax
  volatile signed __int32 *v30; // rdi
  volatile signed __int32 *v31; // rdi
  __int64 v32; // rdx
  volatile signed __int32 *v33; // rdi
  volatile signed __int32 *v34; // rdi
  const struct _tlgProvider_t *v35; // rax
  int v36; // ebx
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rax
  int v44; // eax
  int v45; // eax
  const wchar_t *v46; // rdi
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  __int64 v49; // rdx
  volatile signed __int32 *v50; // rdi
  volatile signed __int32 *v51; // rdi
  const struct _tlgProvider_t *v52; // rax
  int v53; // ebx
  _QWORD *v54; // rax
  __int64 v55; // rax
  __int64 v56; // rcx
  _QWORD *v57; // rax
  int v58; // eax
  int v59; // eax
  const wchar_t *v60; // rdi
  volatile signed __int32 *v61; // rdi
  volatile signed __int32 *v62; // rdi
  int v63; // ebx
  const wchar_t *v64; // rdx
  __int64 v65; // r8
  const struct _tlgProvider_t *v66; // rax
  __int64 v67; // rax
  const CHAR *v68; // rsi
  const OLECHAR *v69; // r13
  __int64 v70; // rax
  __int64 v71; // rcx
  _QWORD *v72; // rax
  int v73; // eax
  int v74; // eax
  const wchar_t *v75; // rdi
  const OLECHAR *v76; // r12
  const OLECHAR *v77; // r15
  __int64 v78; // r8
  int v79; // r9d
  __int64 v80; // rax
  int v81; // eax
  int v82; // ecx
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rax
  __int64 v86; // rax
  int v87; // eax
  __int64 v88; // rax
  int v89; // eax
  const OLECHAR *v90; // rdx
  __int64 v91; // rax
  volatile signed __int32 *v92; // rdi
  volatile signed __int32 *v93; // rdi
  char v94; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v95[3]; // [rsp+99h] [rbp-7Fh] BYREF
  DWORD CurrentThreadId; // [rsp+9Ch] [rbp-7Ch] BYREF
  __int64 v97; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v98; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v99; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v100; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v101; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v103; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v104; // [rsp+D8h] [rbp-40h] BYREF
  __int64 v105; // [rsp+E0h] [rbp-38h] BYREF
  _BYTE v106[8]; // [rsp+E8h] [rbp-30h] BYREF
  volatile signed __int32 *v107; // [rsp+F0h] [rbp-28h]
  _BYTE v108[8]; // [rsp+F8h] [rbp-20h] BYREF
  volatile signed __int32 *v109; // [rsp+100h] [rbp-18h]
  _BYTE pExceptionObject[24]; // [rsp+110h] [rbp-8h] BYREF
  __int64 v111; // [rsp+128h] [rbp+10h] BYREF
  _BYTE v112[8]; // [rsp+130h] [rbp+18h] BYREF
  volatile signed __int32 *v113; // [rsp+138h] [rbp+20h]
  _BYTE v114[8]; // [rsp+140h] [rbp+28h] BYREF
  volatile signed __int32 *v115; // [rsp+148h] [rbp+30h]
  _BYTE v116[32]; // [rsp+150h] [rbp+38h] BYREF
  _BYTE v117[32]; // [rsp+170h] [rbp+58h] BYREF
  __int128 v118; // [rsp+190h] [rbp+78h] BYREF
  __int128 v119; // [rsp+1A0h] [rbp+88h]
  struct _EVENT_DATA_DESCRIPTOR v120; // [rsp+1B8h] [rbp+A0h] BYREF
  __int64 *v121; // [rsp+1D8h] [rbp+C0h]
  __int64 v122; // [rsp+1E0h] [rbp+C8h]
  DWORD *p_CurrentThreadId; // [rsp+1E8h] [rbp+D0h]
  __int64 v124; // [rsp+1F0h] [rbp+D8h]
  const OLECHAR *v125; // [rsp+1F8h] [rbp+E0h]
  int v126; // [rsp+200h] [rbp+E8h]
  int v127; // [rsp+204h] [rbp+ECh]
  const OLECHAR *v128; // [rsp+208h] [rbp+F0h]
  int v129; // [rsp+210h] [rbp+F8h]
  int v130; // [rsp+214h] [rbp+FCh]
  const OLECHAR *v131; // [rsp+218h] [rbp+100h]
  int v132; // [rsp+220h] [rbp+108h]
  int v133; // [rsp+224h] [rbp+10Ch]
  char *v134; // [rsp+228h] [rbp+110h]
  __int64 v135; // [rsp+230h] [rbp+118h]
  _BYTE *v136; // [rsp+238h] [rbp+120h]
  __int64 v137; // [rsp+240h] [rbp+128h]
  const wchar_t *v138; // [rsp+248h] [rbp+130h]
  int v139; // [rsp+250h] [rbp+138h]
  int v140; // [rsp+254h] [rbp+13Ch]
  __int64 *v141; // [rsp+258h] [rbp+140h]
  __int64 v142; // [rsp+260h] [rbp+148h]
  const OLECHAR *v143; // [rsp+268h] [rbp+150h]
  int v144; // [rsp+270h] [rbp+158h]
  int v145; // [rsp+274h] [rbp+15Ch]
  const CHAR *v146; // [rsp+278h] [rbp+160h]
  int v147; // [rsp+280h] [rbp+168h]
  int v148; // [rsp+284h] [rbp+16Ch]
  const char *v149; // [rsp+288h] [rbp+170h]
  __int64 v150; // [rsp+290h] [rbp+178h]

  v104 = (__int64)a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v13 = a3 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)v108, "Unknown provider type");
          throw (std::logic_error *)v108;
        }
        v14 = L"Powershell";
      }
      else
      {
        v14 = L"Executable";
      }
    }
    else
    {
      v14 = L"WindowsUpdate";
    }
    v118 = 0;
    v119 = 0;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    std::wstring::_Construct<1,wchar_t const *>(&v118, v14, v15);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v16 = Windows::Telemetry::Base::Provider();
    v18 = (int)v16;
    if ( *(_DWORD *)v16 > 5u )
    {
      v17 = 0x400000000000LL;
      if ( (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v16 + 3) & 0x400000000000LL) == *((_QWORD *)v16 + 3) )
      {
        v104 = (__int64)"1507.2603.28012.0";
        System = (_QWORD *)SystemInterface::Providers::GetSystem(v108);
        v20 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 40LL))(*System, v106);
        v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v20 + 440LL))(*v20, v116);
        if ( v21[3] > 7u )
          v21 = (_QWORD *)*v21;
        v111 = (__int64)v21;
        v22 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v117);
        if ( v22[3] > 0xFu )
          v22 = (_QWORD *)*v22;
        v105 = (__int64)v22;
        v100 = *a9;
        CurrentThreadId = a8;
        v23 = SystemInterface::Providers::GetSystem(v114);
        v24 = *(_QWORD *)v23 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v23 + 8LL) + 4LL);
        v25 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 96LL))(v24, v112);
        v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            if ( v27 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v28 = L"Internet";
          }
          else
          {
            v28 = L"local only";
          }
        }
        else
        {
          v28 = L"none";
        }
        v101 = (__int64)v28;
        v94 = a6;
        v95[0] = a5;
        v102 = *a4;
        v29 = &v118;
        if ( *((_QWORD *)&v119 + 1) > 7u )
          v29 = (__int128 *)v118;
        v103 = (__int64)v29;
        v98 = *a2;
        LODWORD(v97) = GetCurrentThreadId();
        v99 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v18,
          (int)&byte_1404A011B,
          *(_QWORD *)(a1 + 272) + 8,
          (__int64)&v99,
          (__int64)&v97,
          (__int64)&v98,
          (__int64)&v103,
          (__int64)&v102,
          (__int64)v95,
          (__int64)&v94,
          (__int64)&v101,
          (__int64)&CurrentThreadId,
          (__int64)&v100,
          (__int64)&v105,
          (__int64)&v111,
          (__int64)&v104);
        v30 = v113;
        if ( v113 )
        {
          if ( _InterlockedExchangeAdd(v113 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        v31 = v115;
        if ( v115 )
        {
          if ( _InterlockedExchangeAdd(v115 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        std::string::_Tidy_deallocate(v117);
        std::wstring::~wstring(v116, v32);
        v33 = v107;
        if ( v107 )
        {
          if ( _InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
        v34 = v109;
        if ( v109 )
        {
          if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          }
        }
      }
    }
    if ( !*(_DWORD *)(a1 + 312) )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
LABEL_163:
    std::wstring::~wstring(&v118, v17);
    return;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v63 = a3 - 1;
      if ( v63 )
      {
        if ( v63 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown provider type");
          throw (std::logic_error *)pExceptionObject;
        }
        v64 = L"Powershell";
      }
      else
      {
        v64 = L"Executable";
      }
    }
    else
    {
      v64 = L"WindowsUpdate";
    }
    v118 = 0;
    v119 = 0;
    v65 = -1;
    do
      ++v65;
    while ( v64[v65] );
    std::wstring::_Construct<1,wchar_t const *>(&v118, v64, v65);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v66 = Windows::Telemetry::Base::Provider();
    v98 = (__int64)v66;
    if ( *(_DWORD *)v66 > 5u )
    {
      v17 = 0x400000000000LL;
      if ( (*((_QWORD *)v66 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v66 + 3) & 0x400000000000LL) == *((_QWORD *)v66 + 3) )
      {
        v67 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v116);
        v68 = (const CHAR *)v67;
        if ( *(_QWORD *)(v67 + 24) > 0xFu )
          v68 = *(const CHAR **)v67;
        v69 = (const OLECHAR *)*a9;
        LODWORD(v97) = a8;
        v70 = SystemInterface::Providers::GetSystem(v106);
        v71 = *(_QWORD *)v70 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v70 + 8LL) + 4LL);
        v72 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v71 + 96LL))(v71, v108);
        v73 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v72 + 8LL))(*v72);
        if ( v73 )
        {
          v74 = v73 - 1;
          if ( v74 )
          {
            if ( v74 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v75 = L"Internet";
          }
          else
          {
            v75 = L"local only";
          }
        }
        else
        {
          v75 = L"none";
        }
        v95[0] = a6;
        v94 = a5;
        v76 = (const OLECHAR *)*a4;
        v77 = (const OLECHAR *)&v118;
        if ( *((_QWORD *)&v119 + 1) > 7u )
          v77 = (const OLECHAR *)v118;
        CurrentThreadId = GetCurrentThreadId();
        v99 = 0x1000000;
        v78 = *(_QWORD *)(a1 + 272);
        if ( !*(_BYTE *)(v78 + 4)
          || (v79 = v78 + 24, !*(_DWORD *)(v78 + 24))
          && !*(_DWORD *)(v78 + 28)
          && !*(_DWORD *)(v78 + 32)
          && !*(_DWORD *)(v78 + 36) )
        {
          v79 = 0;
        }
        v149 = "1507.2603.28012.0";
        v150 = 18;
        if ( v68 )
        {
          v80 = -1;
          do
            ++v80;
          while ( v68[v80] );
          v81 = v80 + 1;
        }
        else
        {
          v68 = &pszCabPath;
          v81 = 1;
        }
        v146 = v68;
        v147 = v81;
        v148 = 0;
        v82 = 2;
        if ( v69 )
        {
          v83 = -1;
          do
            ++v83;
          while ( v69[v83] );
          v84 = 2 * v83 + 2;
        }
        else
        {
          v69 = &psz;
          v84 = 2;
        }
        v143 = v69;
        v144 = v84;
        v145 = 0;
        v141 = &v97;
        v142 = 4;
        v85 = -1;
        do
          ++v85;
        while ( v75[v85] );
        v138 = v75;
        v139 = 2 * v85 + 2;
        v140 = 0;
        v136 = v95;
        v137 = 1;
        v134 = &v94;
        v135 = 1;
        if ( v76 )
        {
          v86 = -1;
          do
            ++v86;
          while ( v76[v86] );
          v87 = 2 * v86 + 2;
        }
        else
        {
          v76 = &psz;
          v87 = 2;
        }
        v131 = v76;
        v132 = v87;
        v133 = 0;
        if ( v77 )
        {
          v88 = -1;
          do
            ++v88;
          while ( v77[v88] );
          v89 = 2 * v88 + 2;
        }
        else
        {
          v77 = &psz;
          v89 = 2;
        }
        v128 = v77;
        v129 = v89;
        v130 = 0;
        v90 = *(const OLECHAR **)v104;
        if ( *(_QWORD *)v104 )
        {
          v91 = -1;
          do
            ++v91;
          while ( v90[v91] );
          v82 = 2 * v91 + 2;
        }
        else
        {
          v90 = &psz;
        }
        v125 = v90;
        v126 = v82;
        v127 = 0;
        p_CurrentThreadId = &CurrentThreadId;
        v124 = 4;
        v121 = &v99;
        v122 = 8;
        tlgWriteTransfer_EventWriteTransfer(v98, (int)&unk_1404A01E8, v78 + 8, v79, 0xEu, &v120);
        v92 = v109;
        if ( v109 )
        {
          if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v92)(v92);
            if ( _InterlockedExchangeAdd(v92 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v92 + 8LL))(v92);
          }
        }
        v93 = v107;
        if ( v107 )
        {
          if ( _InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v93)(v93);
            if ( _InterlockedExchangeAdd(v93 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v93 + 8LL))(v93);
          }
        }
        std::string::_Tidy_deallocate(v116);
      }
    }
    if ( !*(_DWORD *)(a1 + 312) )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
    goto LABEL_163;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v35 = Windows::Telemetry::Base::Provider();
    v36 = (int)v35;
    if ( *(_DWORD *)v35 > 5u
      && (*((_QWORD *)v35 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v35 + 3) & 0x400000000000LL) == *((_QWORD *)v35 + 3) )
    {
      v99 = (__int64)"1507.2603.28012.0";
      v37 = (_QWORD *)SystemInterface::Providers::GetSystem(v112);
      v38 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v37 + 40LL))(*v37, v114);
      v39 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v38 + 440LL))(*v38, v117);
      if ( v39[3] > 7u )
        v39 = (_QWORD *)*v39;
      v98 = (__int64)v39;
      v40 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v116);
      if ( v40[3] > 0xFu )
        v40 = (_QWORD *)*v40;
      v103 = (__int64)v40;
      v102 = *a9;
      LODWORD(v97) = a8;
      v41 = SystemInterface::Providers::GetSystem(v106);
      v42 = *(_QWORD *)v41 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v41 + 8LL) + 4LL);
      v43 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v42 + 96LL))(v42, v108);
      v44 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
      if ( v44 )
      {
        v45 = v44 - 1;
        if ( v45 )
        {
          if ( v45 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v46 = L"Internet";
        }
        else
        {
          v46 = L"local only";
        }
      }
      else
      {
        v46 = L"none";
      }
      v101 = (__int64)v46;
      v95[0] = a6;
      v94 = a5;
      v100 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v105 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v36,
        (int)&byte_14049FE75,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v105,
        (__int64)&CurrentThreadId,
        (__int64)&v100,
        (__int64)&v94,
        (__int64)v95,
        (__int64)&v101,
        (__int64)&v97,
        (__int64)&v102,
        (__int64)&v103,
        (__int64)&v98,
        (__int64)&v99);
      v47 = v109;
      if ( v109 )
      {
        if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
          if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
        }
      }
      v48 = v107;
      if ( v107 )
      {
        if ( _InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
          if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
        }
      }
      std::string::_Tidy_deallocate(v116);
      std::wstring::~wstring(v117, v49);
      v50 = v115;
      if ( v115 )
      {
        if ( !_InterlockedDecrement(v115 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
          if ( !_InterlockedDecrement(v50 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
        }
      }
      v51 = v113;
      if ( v113 )
      {
        if ( !_InterlockedDecrement(v113 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
          if ( !_InterlockedDecrement(v51 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
        }
      }
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v52 = Windows::Telemetry::Base::Provider();
    v53 = (int)v52;
    if ( *(_DWORD *)v52 > 5u
      && (*((_QWORD *)v52 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v52 + 3) & 0x400000000000LL) == *((_QWORD *)v52 + 3) )
    {
      v99 = (__int64)"1507.2603.28012.0";
      v54 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v116);
      if ( v54[3] > 0xFu )
        v54 = (_QWORD *)*v54;
      v98 = (__int64)v54;
      v103 = *a9;
      LODWORD(v97) = a8;
      v55 = SystemInterface::Providers::GetSystem(v106);
      v56 = *(_QWORD *)v55 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v55 + 8LL) + 4LL);
      v57 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v56 + 96LL))(v56, v108);
      v58 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v57 + 8LL))(*v57);
      if ( v58 )
      {
        v59 = v58 - 1;
        if ( v59 )
        {
          if ( v59 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v60 = L"Internet";
        }
        else
        {
          v60 = L"local only";
        }
      }
      else
      {
        v60 = L"none";
      }
      v102 = (__int64)v60;
      v95[0] = a6;
      v94 = a5;
      v101 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v100 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v53,
        (int)&byte_14049FF23,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v100,
        (__int64)&CurrentThreadId,
        (__int64)&v101,
        (__int64)&v94,
        (__int64)v95,
        (__int64)&v102,
        (__int64)&v97,
        (__int64)&v103,
        (__int64)&v98,
        (__int64)&v99);
      v61 = v109;
      if ( v109 )
      {
        if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      v62 = v107;
      if ( v107 )
      {
        if ( _InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
          if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
        }
      }
      std::string::_Tidy_deallocate(v116);
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x140271d18  mov     rax, rsp
0x140271d1b  mov     [rax+10h], rbx
0x140271d1f  mov     [rax+18h], rsi
0x140271d23  mov     [rax+20h], rdi
0x140271d27  push    rbp
0x140271d28  push    r12
0x140271d2a  push    r13
0x140271d2c  push    r14
0x140271d2e  push    r15
0x140271d30  lea     rbp, [rax-1B8h]
0x140271d37  sub     rsp, 2A0h
0x140271d3e  mov     rax, cs:__security_cookie
0x140271d45  xor     rax, rsp
0x140271d48  mov     [rbp+1B0h+var_30], rax
0x140271d4f  mov     r12, r9
0x140271d52  mov     ebx, r8d
0x140271d55  mov     r15, rdx
0x140271d58  mov     [rbp+1B0h+var_1F0], rdx
0x140271d5c  mov     r14, rcx
0x140271d5f  mov     rdi, [rbp+1B0h+arg_30]
0x140271d66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x140271d6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x140271d72  xor     r13d, r13d
0x140271d75  test    al, al
0x140271d77  jz      loc_140272136
0x140271d7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x140271d84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x140271d89  test    al, al
0x140271d8b  jz      loc_140272136
0x140271d91  test    ebx, ebx
0x140271d93  jz      short loc_140271DB5
0x140271d95  sub     ebx, 1
0x140271d98  jz      short loc_140271DAC
0x140271d9a  cmp     ebx, 1
0x140271d9d  jnz     loc_140272B1F
0x140271da3  lea     rdx, aPowershell_0; "Powershell"
0x140271daa  jmp     short loc_140271DBC
0x140271dac  lea     rdx, aExecutable; "Executable"
0x140271db3  jmp     short loc_140271DBC
0x140271db5  lea     rdx, aWindowsupdate_0; "WindowsUpdate"
0x140271dbc  xorps   xmm0, xmm0
0x140271dbf  movups  [rbp+1B0h+var_138], xmm0
0x140271dc3  xorps   xmm1, xmm1
0x140271dc6  movdqu  [rbp+1B0h+var_128], xmm1
0x140271dce  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140271dd2  mov     r8, rbx
0x140271dd5  inc     r8
0x140271dd8  cmp     [rdx+r8*2], r13w
0x140271ddd  jnz     short loc_140271DD5
0x140271ddf  lea     rcx, [rbp+1B0h+var_138]
0x140271de3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140271de8  nop
0x140271de9  mov     rcx, r14
0x140271dec  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140271df1  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x140271df6  mov     rsi, rax
0x140271df9  cmp     dword ptr [rax], 5
0x140271dfc  jbe     loc_14027211E
0x140271e02  mov     rdx, 400000000000h
0x140271e0c  test    [rax+10h], rdx
0x140271e10  jz      loc_14027211E
0x140271e16  mov     rcx, [rax+18h]
0x140271e1a  and     rcx, rdx
0x140271e1d  cmp     rcx, [rax+18h]
0x140271e21  jnz     loc_14027211E
0x140271e27  lea     rax, a15072603280120; "1507.2603.28012.0"
0x140271e2e  mov     [rbp+1B0h+var_1F0], rax
0x140271e32  lea     rcx, [rbp+1B0h+var_1D0]
0x140271e36  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140271e3b  nop
0x140271e3c  mov     rcx, [rax]
0x140271e3f  mov     rax, [rcx]
0x140271e42  lea     rdx, [rbp+1B0h+var_1E0]
0x140271e46  mov     rax, [rax+28h]
0x140271e4a  call    _guard_dispatch_icall
0x140271e4f  nop
0x140271e50  mov     rcx, [rax]
0x140271e53  mov     rax, [rcx]
0x140271e56  lea     rdx, [rbp+1B0h+var_178]
0x140271e5a  mov     rax, [rax+1B8h]
0x140271e61  call    _guard_dispatch_icall
0x140271e66  nop
0x140271e67  cmp     qword ptr [rax+18h], 7
0x140271e6c  jbe     short loc_140271E71
0x140271e6e  mov     rax, [rax]
0x140271e71  mov     [rbp+1B0h+var_1A0], rax
0x140271e75  mov     rax, [rdi]
0x140271e78  lea     rdx, [rbp+1B0h+var_158]
0x140271e7c  mov     rcx, rdi
0x140271e7f  mov     rax, [rax+8]
0x140271e83  call    _guard_dispatch_icall
0x140271e88  nop
0x140271e89  cmp     qword ptr [rax+18h], 0Fh
0x140271e8e  jbe     short loc_140271E93
0x140271e90  mov     rax, [rax]
0x140271e93  mov     [rbp+1B0h+var_1E8], rax
0x140271e97  mov     rax, [rbp+1B0h+arg_40]
0x140271e9e  mov     rcx, [rax]
0x140271ea1  mov     [rbp+1B0h+var_210], rcx
0x140271ea5  mov     eax, [rbp+1B0h+arg_38]
0x140271eab  mov     dword ptr [rbp+1B0h+var_230+4], eax
0x140271eae  lea     rcx, [rbp+1B0h+var_188]
0x140271eb2  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140271eb7  nop
0x140271eb8  mov     rdx, [rax]
0x140271ebb  mov     rax, [rdx+8]
0x140271ebf  movsxd  rcx, dword ptr [rax+4]
0x140271ec3  add     rdx, 8
0x140271ec7  add     rcx, rdx
0x140271eca  mov     rax, [rcx]
0x140271ecd  lea     rdx, [rbp+1B0h+var_198]
0x140271ed1  mov     rax, [rax+60h]
0x140271ed5  call    _guard_dispatch_icall
0x140271eda  nop
0x140271edb  mov     rcx, [rax]
0x140271ede  mov     rax, [rcx]
0x140271ee1  mov     rax, [rax+8]
0x140271ee5  call    _guard_dispatch_icall
0x140271eea  test    eax, eax
0x140271eec  jz      short loc_140271F0E
0x140271eee  sub     eax, 1
0x140271ef1  jz      short loc_140271F05
0x140271ef3  cmp     eax, 1
0x140271ef6  jnz     loc_140272B40
0x140271efc  lea     rdi, aInternet; "Internet"
0x140271f03  jmp     short loc_140271F15
0x140271f05  lea     rdi, aLocalOnly; "local only"
0x140271f0c  jmp     short loc_140271F15
0x140271f0e  lea     rdi, aNone; "none"
0x140271f15  mov     [rbp+1B0h+var_208], rdi
0x140271f19  mov     al, [rbp+1B0h+arg_28]
0x140271f1f  mov     byte ptr [rbp+1B0h+var_230], al
0x140271f22  mov     al, [rbp+1B0h+arg_20]
0x140271f28  mov     byte ptr [rbp+1B0h+var_230+1], al
0x140271f2b  mov     rax, [r12]
0x140271f2f  mov     [rbp+1B0h+var_200], rax
0x140271f33  lea     rax, [rbp+1B0h+var_138]
0x140271f37  cmp     qword ptr [rbp+1B0h+var_128+8], 7
0x140271f3f  cmova   rax, qword ptr [rbp+1B0h+var_138]
0x140271f44  mov     [rbp+1B0h+var_1F8], rax
0x140271f48  mov     rax, [r15]
0x140271f4b  mov     [rbp+1B0h+var_220], rax
0x140271f4f  call    cs:__imp_GetCurrentThreadId
0x140271f55  mov     dword ptr [rbp+1B0h+var_228], eax
0x140271f58  mov     [rbp+1B0h+var_218], 1000000h
0x140271f60  mov     r8, [r14+110h]
0x140271f67  cmp     [r8+4], r13b
0x140271f6b  jz      short loc_140271F88
0x140271f6d  lea     r9, [r8+18h]
0x140271f71  cmp     [r9], r13d
0x140271f74  jnz     short loc_140271F8B
0x140271f76  cmp     [r9+4], r13d
0x140271f7a  jnz     short loc_140271F8B
0x140271f7c  cmp     [r9+8], r13d
0x140271f80  jnz     short loc_140271F8B
0x140271f82  cmp     [r9+0Ch], r13d
0x140271f86  jnz     short loc_140271F8B
0x140271f88  mov     r9, r13
0x140271f8b  add     r8, 8; int
0x140271f8f  lea     rax, [rbp+1B0h+var_1F0]
0x140271f93  mov     [rsp+2C0h+var_240], rax; __int64
0x140271f9b  lea     rax, [rbp+1B0h+var_1A0]
0x140271f9f  mov     [rsp+2C0h+var_248], rax; __int64
0x140271fa4  lea     rax, [rbp+1B0h+var_1E8]
0x140271fa8  mov     [rsp+2C0h+var_250], rax; __int64
0x140271fad  lea     rax, [rbp+1B0h+var_210]
0x140271fb1  mov     [rsp+2C0h+var_258], rax; __int64
0x140271fb6  lea     rax, [rbp+1B0h+var_230+4]
0x140271fba  mov     [rsp+2C0h+var_260], rax; __int64
0x140271fbf  lea     rax, [rbp+1B0h+var_208]
0x140271fc3  mov     [rsp+2C0h+var_268], rax; __int64
0x140271fc8  lea     rax, [rbp+1B0h+var_230]
0x140271fcc  mov     [rsp+2C0h+var_270], rax; __int64
0x140271fd1  lea     rax, [rbp+1B0h+var_230+1]
0x140271fd5  mov     [rsp+2C0h+var_278], rax; __int64
0x140271fda  lea     rax, [rbp+1B0h+var_200]
0x140271fde  mov     [rsp+2C0h+var_280], rax; __int64
0x140271fe3  lea     rax, [rbp+1B0h+var_1F8]
0x140271fe7  mov     [rsp+2C0h+var_288], rax; __int64
0x140271fec  lea     rax, [rbp+1B0h+var_220]
0x140271ff0  mov     [rsp+2C0h+var_290], rax; __int64
0x140271ff5  lea     rax, [rbp+1B0h+var_228]
0x140271ff9  mov     [rsp+2C0h+var_298], rax; __int64
0x140271ffe  lea     rax, [rbp+1B0h+var_218]
0x140272002  mov     qword ptr [rsp+2C0h+var_2A0], rax; __int64
0x140272007  lea     rdx, byte_1404A011B; int
0x14027200e  mov     rcx, rsi; int
0x140272011  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U3@U?$_tlgWrapperByVal@$00@@U4@U3@U2@U3@U?$_tlgWrapSz@D@@U3@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@55AEBU?$_tlgWrapperByVal@$00@@6545AEBU?$_tlgWrapSz@D@@57@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x140272016  nop
0x140272017  mov     rdi, [rbp+1B0h+var_190]
0x14027201b  test    rdi, rdi
0x14027201e  jz      short loc_140272054
0x140272020  mov     eax, ebx
0x140272022  lock xadd [rdi+8], eax
0x140272027  add     eax, ebx
0x140272029  jnz     short loc_140272054
0x14027202b  mov     rax, [rdi]
0x14027202e  mov     rcx, rdi
0x140272031  mov     rax, [rax]
0x140272034  call    _guard_dispatch_icall
0x140272039  mov     eax, ebx
0x14027203b  lock xadd [rdi+0Ch], eax
0x140272040  add     eax, ebx
0x140272042  jnz     short loc_140272054
0x140272044  mov     rax, [rdi]
0x140272047  mov     rcx, rdi
0x14027204a  mov     rax, [rax+8]
0x14027204e  call    _guard_dispatch_icall
0x140272053  nop
0x140272054  mov     rdi, [rbp+1B0h+var_180]
0x140272058  test    rdi, rdi
0x14027205b  jz      short loc_140272091
0x14027205d  mov     eax, ebx
0x14027205f  lock xadd [rdi+8], eax
0x140272064  add     eax, ebx
0x140272066  jnz     short loc_140272091
0x140272068  mov     rax, [rdi]
0x14027206b  mov     rcx, rdi
0x14027206e  mov     rax, [rax]
0x140272071  call    _guard_dispatch_icall
0x140272076  mov     eax, ebx
0x140272078  lock xadd [rdi+0Ch], eax
0x14027207d  add     eax, ebx
0x14027207f  jnz     short loc_140272091
0x140272081  mov     rax, [rdi]
0x140272084  mov     rcx, rdi
0x140272087  mov     rax, [rax+8]
0x14027208b  call    _guard_dispatch_icall
0x140272090  nop
0x140272091  lea     rcx, [rbp+1B0h+var_158]
0x140272095  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14027209a  nop
0x14027209b  lea     rcx, [rbp+1B0h+var_178]
0x14027209f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402720a4  nop
0x1402720a5  mov     rdi, [rbp+1B0h+var_1D8]
0x1402720a9  test    rdi, rdi
0x1402720ac  jz      short loc_1402720E2
0x1402720ae  mov     eax, ebx
0x1402720b0  lock xadd [rdi+8], eax
0x1402720b5  add     eax, ebx
0x1402720b7  jnz     short loc_1402720E2
0x1402720b9  mov     rax, [rdi]
0x1402720bc  mov     rcx, rdi
0x1402720bf  mov     rax, [rax]
0x1402720c2  call    _guard_dispatch_icall
0x1402720c7  mov     eax, ebx
0x1402720c9  lock xadd [rdi+0Ch], eax
0x1402720ce  add     eax, ebx
0x1402720d0  jnz     short loc_1402720E2
0x1402720d2  mov     rax, [rdi]
0x1402720d5  mov     rcx, rdi
0x1402720d8  mov     rax, [rax+8]
0x1402720dc  call    _guard_dispatch_icall
0x1402720e1  nop
0x1402720e2  mov     rdi, [rbp+1B0h+var_1C8]
0x1402720e6  test    rdi, rdi
0x1402720e9  jz      short loc_14027211E
0x1402720eb  mov     eax, ebx
0x1402720ed  lock xadd [rdi+8], eax
0x1402720f2  add     eax, ebx
0x1402720f4  jnz     short loc_14027211E
0x1402720f6  mov     rax, [rdi]
0x1402720f9  mov     rcx, rdi
0x1402720fc  mov     rax, [rax]
0x1402720ff  call    _guard_dispatch_icall
0x140272104  mov     eax, ebx
0x140272106  lock xadd [rdi+0Ch], eax
0x14027210b  add     eax, ebx
0x14027210d  jnz     short loc_14027211E
0x14027210f  mov     rax, [rdi]
0x140272112  mov     rcx, rdi
0x140272115  mov     rax, [rax+8]
0x140272119  call    _guard_dispatch_icall
0x14027211e  lea     rcx, [r14+120h]; this
0x140272125  cmp     [rcx+18h], r13d
0x140272129  jnz     short loc_140272131
0x14027212b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140272130  nop
0x140272131  jmp     loc_140272AC5
0x140272136  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x14027213d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x140272142  test    al, al
0x140272144  jnz     loc_1402726AD
0x14027214a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x140272151  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x140272156  mov     rcx, r14
0x140272159  test    al, al
0x14027215b  jz      loc_140272480
0x140272161  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140272166  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x14027216b  mov     rbx, rax
0x14027216e  cmp     dword ptr [rax], 5
0x140272171  jbe     loc_140272465
0x140272177  mov     rdx, 400000000000h
0x140272181  test    [rax+10h], rdx
0x140272185  jz      loc_140272465
0x14027218b  mov     rcx, [rax+18h]
0x14027218f  and     rcx, rdx
0x140272192  cmp     rcx, [rax+18h]
  ... truncated ...
```
