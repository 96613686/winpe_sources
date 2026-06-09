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
  int v17; // esi
  _QWORD *System; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  int v25; // eax
  int v26; // eax
  const wchar_t *v27; // rdi
  __int128 *v28; // rax
  volatile signed __int32 *v29; // rdi
  volatile signed __int32 *v30; // rdi
  volatile signed __int32 *v31; // rdi
  volatile signed __int32 *v32; // rdi
  const struct _tlgProvider_t *v33; // rax
  int v34; // ebx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  _QWORD *v41; // rax
  int v42; // eax
  int v43; // eax
  const wchar_t *v44; // rdi
  volatile signed __int32 *v45; // rdi
  volatile signed __int32 *v46; // rdi
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  const struct _tlgProvider_t *v49; // rax
  int v50; // ebx
  _QWORD *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rax
  int v55; // eax
  int v56; // eax
  const wchar_t *v57; // rdi
  volatile signed __int32 *v58; // rdi
  volatile signed __int32 *v59; // rdi
  int v60; // ebx
  const wchar_t *v61; // rdx
  __int64 v62; // r8
  const struct _tlgProvider_t *v63; // rax
  __int64 v64; // rax
  const CHAR *v65; // rsi
  const OLECHAR *v66; // r13
  __int64 v67; // rax
  __int64 v68; // rcx
  _QWORD *v69; // rax
  int v70; // eax
  int v71; // eax
  const wchar_t *v72; // rdi
  const OLECHAR *v73; // r12
  const OLECHAR *v74; // r15
  __int64 v75; // r8
  int v76; // r9d
  __int64 v77; // rax
  int v78; // eax
  int v79; // ecx
  __int64 v80; // rax
  int v81; // eax
  __int64 v82; // rax
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rax
  int v86; // eax
  const OLECHAR *v87; // rdx
  __int64 v88; // rax
  volatile signed __int32 *v89; // rdi
  volatile signed __int32 *v90; // rdi
  char v91; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v92[3]; // [rsp+99h] [rbp-7Fh] BYREF
  DWORD CurrentThreadId; // [rsp+9Ch] [rbp-7Ch] BYREF
  __int64 v94; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v96; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v97; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v98; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v99; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v100; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v101; // [rsp+D8h] [rbp-40h] BYREF
  __int64 v102; // [rsp+E0h] [rbp-38h] BYREF
  _BYTE v103[8]; // [rsp+E8h] [rbp-30h] BYREF
  volatile signed __int32 *v104; // [rsp+F0h] [rbp-28h]
  _BYTE v105[8]; // [rsp+F8h] [rbp-20h] BYREF
  volatile signed __int32 *v106; // [rsp+100h] [rbp-18h]
  _BYTE pExceptionObject[24]; // [rsp+110h] [rbp-8h] BYREF
  __int64 v108; // [rsp+128h] [rbp+10h] BYREF
  _BYTE v109[8]; // [rsp+130h] [rbp+18h] BYREF
  volatile signed __int32 *v110; // [rsp+138h] [rbp+20h]
  _BYTE v111[8]; // [rsp+140h] [rbp+28h] BYREF
  volatile signed __int32 *v112; // [rsp+148h] [rbp+30h]
  _BYTE v113[32]; // [rsp+150h] [rbp+38h] BYREF
  _BYTE v114[32]; // [rsp+170h] [rbp+58h] BYREF
  __int128 v115; // [rsp+190h] [rbp+78h] BYREF
  __int128 v116; // [rsp+1A0h] [rbp+88h]
  struct _EVENT_DATA_DESCRIPTOR v117; // [rsp+1B8h] [rbp+A0h] BYREF
  __int64 *v118; // [rsp+1D8h] [rbp+C0h]
  __int64 v119; // [rsp+1E0h] [rbp+C8h]
  DWORD *p_CurrentThreadId; // [rsp+1E8h] [rbp+D0h]
  __int64 v121; // [rsp+1F0h] [rbp+D8h]
  const OLECHAR *v122; // [rsp+1F8h] [rbp+E0h]
  int v123; // [rsp+200h] [rbp+E8h]
  int v124; // [rsp+204h] [rbp+ECh]
  const OLECHAR *v125; // [rsp+208h] [rbp+F0h]
  int v126; // [rsp+210h] [rbp+F8h]
  int v127; // [rsp+214h] [rbp+FCh]
  const OLECHAR *v128; // [rsp+218h] [rbp+100h]
  int v129; // [rsp+220h] [rbp+108h]
  int v130; // [rsp+224h] [rbp+10Ch]
  char *v131; // [rsp+228h] [rbp+110h]
  __int64 v132; // [rsp+230h] [rbp+118h]
  _BYTE *v133; // [rsp+238h] [rbp+120h]
  __int64 v134; // [rsp+240h] [rbp+128h]
  const wchar_t *v135; // [rsp+248h] [rbp+130h]
  int v136; // [rsp+250h] [rbp+138h]
  int v137; // [rsp+254h] [rbp+13Ch]
  __int64 *v138; // [rsp+258h] [rbp+140h]
  __int64 v139; // [rsp+260h] [rbp+148h]
  const OLECHAR *v140; // [rsp+268h] [rbp+150h]
  int v141; // [rsp+270h] [rbp+158h]
  int v142; // [rsp+274h] [rbp+15Ch]
  const CHAR *v143; // [rsp+278h] [rbp+160h]
  int v144; // [rsp+280h] [rbp+168h]
  int v145; // [rsp+284h] [rbp+16Ch]
  const char *v146; // [rsp+288h] [rbp+170h]
  __int64 v147; // [rsp+290h] [rbp+178h]

  v101 = (__int64)a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v13 = a3 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)v105, "Unknown provider type");
          throw (std::logic_error *)v105;
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
    v115 = 0;
    v116 = 0;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    std::wstring::_Construct<1,wchar_t const *>(&v115, v14);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v16 = Windows::Telemetry::Base::Provider();
    v17 = (int)v16;
    if ( *(_DWORD *)v16 > 5u
      && (*((_QWORD *)v16 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v16 + 3) & 0x400000000000LL) == *((_QWORD *)v16 + 3) )
    {
      v101 = (__int64)"1507.2603.28012.0";
      System = (_QWORD *)SystemInterface::Providers::GetSystem(v105);
      v19 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 40LL))(*System, v103);
      v20 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v19 + 440LL))(*v19, v113);
      if ( v20[3] > 7u )
        v20 = (_QWORD *)*v20;
      v108 = (__int64)v20;
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v114);
      if ( v21[3] > 0xFu )
        v21 = (_QWORD *)*v21;
      v102 = (__int64)v21;
      v97 = *a9;
      CurrentThreadId = a8;
      v22 = SystemInterface::Providers::GetSystem(v111);
      v23 = *(_QWORD *)v22 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v22 + 8LL) + 4LL);
      v24 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v23 + 96LL))(v23, v109);
      v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v27 = L"Internet";
        }
        else
        {
          v27 = L"local only";
        }
      }
      else
      {
        v27 = L"none";
      }
      v98 = (__int64)v27;
      v91 = a6;
      v92[0] = a5;
      v99 = *a4;
      v28 = &v115;
      if ( *((_QWORD *)&v116 + 1) > 7u )
        v28 = (__int128 *)v115;
      v100 = (__int64)v28;
      v95 = *a2;
      LODWORD(v94) = GetCurrentThreadId();
      v96 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v17,
        (int)&dword_1404A011B,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v96,
        (__int64)&v94,
        (__int64)&v95,
        (__int64)&v100,
        (__int64)&v99,
        (__int64)v92,
        (__int64)&v91,
        (__int64)&v98,
        (__int64)&CurrentThreadId,
        (__int64)&v97,
        (__int64)&v102,
        (__int64)&v108,
        (__int64)&v101);
      v29 = v110;
      if ( v110 )
      {
        if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      v30 = v112;
      if ( v112 )
      {
        if ( _InterlockedExchangeAdd(v112 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
      std::string::_Tidy_deallocate(v114);
      std::wstring::~wstring(v113);
      v31 = v104;
      if ( v104 )
      {
        if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      v32 = v106;
      if ( v106 )
      {
        if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
    }
    if ( !*(_DWORD *)(a1 + 312) )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
LABEL_163:
    std::wstring::~wstring(&v115);
    return;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v60 = a3 - 1;
      if ( v60 )
      {
        if ( v60 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown provider type");
          throw (std::logic_error *)pExceptionObject;
        }
        v61 = L"Powershell";
      }
      else
      {
        v61 = L"Executable";
      }
    }
    else
    {
      v61 = L"WindowsUpdate";
    }
    v115 = 0;
    v116 = 0;
    v62 = -1;
    do
      ++v62;
    while ( v61[v62] );
    std::wstring::_Construct<1,wchar_t const *>(&v115, v61);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v63 = Windows::Telemetry::Base::Provider();
    v95 = (__int64)v63;
    if ( *(_DWORD *)v63 > 5u
      && (*((_QWORD *)v63 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v63 + 3) & 0x400000000000LL) == *((_QWORD *)v63 + 3) )
    {
      v64 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
      v65 = (const CHAR *)v64;
      if ( *(_QWORD *)(v64 + 24) > 0xFu )
        v65 = *(const CHAR **)v64;
      v66 = (const OLECHAR *)*a9;
      LODWORD(v94) = a8;
      v67 = SystemInterface::Providers::GetSystem(v103);
      v68 = *(_QWORD *)v67 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v67 + 8LL) + 4LL);
      v69 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v68 + 96LL))(v68, v105);
      v70 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v69 + 8LL))(*v69);
      if ( v70 )
      {
        v71 = v70 - 1;
        if ( v71 )
        {
          if ( v71 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v72 = L"Internet";
        }
        else
        {
          v72 = L"local only";
        }
      }
      else
      {
        v72 = L"none";
      }
      v92[0] = a6;
      v91 = a5;
      v73 = (const OLECHAR *)*a4;
      v74 = (const OLECHAR *)&v115;
      if ( *((_QWORD *)&v116 + 1) > 7u )
        v74 = (const OLECHAR *)v115;
      CurrentThreadId = GetCurrentThreadId();
      v96 = 0x1000000;
      v75 = *(_QWORD *)(a1 + 272);
      if ( !*(_BYTE *)(v75 + 4)
        || (v76 = v75 + 24, !*(_DWORD *)(v75 + 24))
        && !*(_DWORD *)(v75 + 28)
        && !*(_DWORD *)(v75 + 32)
        && !*(_DWORD *)(v75 + 36) )
      {
        v76 = 0;
      }
      v146 = "1507.2603.28012.0";
      v147 = 18;
      if ( v65 )
      {
        v77 = -1;
        do
          ++v77;
        while ( v65[v77] );
        v78 = v77 + 1;
      }
      else
      {
        v65 = &pszCabPath;
        v78 = 1;
      }
      v143 = v65;
      v144 = v78;
      v145 = 0;
      v79 = 2;
      if ( v66 )
      {
        v80 = -1;
        do
          ++v80;
        while ( v66[v80] );
        v81 = 2 * v80 + 2;
      }
      else
      {
        v66 = &psz;
        v81 = 2;
      }
      v140 = v66;
      v141 = v81;
      v142 = 0;
      v138 = &v94;
      v139 = 4;
      v82 = -1;
      do
        ++v82;
      while ( v72[v82] );
      v135 = v72;
      v136 = 2 * v82 + 2;
      v137 = 0;
      v133 = v92;
      v134 = 1;
      v131 = &v91;
      v132 = 1;
      if ( v73 )
      {
        v83 = -1;
        do
          ++v83;
        while ( v73[v83] );
        v84 = 2 * v83 + 2;
      }
      else
      {
        v73 = &psz;
        v84 = 2;
      }
      v128 = v73;
      v129 = v84;
      v130 = 0;
      if ( v74 )
      {
        v85 = -1;
        do
          ++v85;
        while ( v74[v85] );
        v86 = 2 * v85 + 2;
      }
      else
      {
        v74 = &psz;
        v86 = 2;
      }
      v125 = v74;
      v126 = v86;
      v127 = 0;
      v87 = *(const OLECHAR **)v101;
      if ( *(_QWORD *)v101 )
      {
        v88 = -1;
        do
          ++v88;
        while ( v87[v88] );
        v79 = 2 * v88 + 2;
      }
      else
      {
        v87 = &psz;
      }
      v122 = v87;
      v123 = v79;
      v124 = 0;
      p_CurrentThreadId = &CurrentThreadId;
      v121 = 4;
      v118 = &v96;
      v119 = 8;
      tlgWriteTransfer_EventWriteTransfer(v95, (int)&dword_1404A01E8, v75 + 8, v76, 0xEu, &v117);
      v89 = v106;
      if ( v106 )
      {
        if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
          if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
        }
      }
      v90 = v104;
      if ( v104 )
      {
        if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
          if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
        }
      }
      std::string::_Tidy_deallocate(v113);
    }
    if ( !*(_DWORD *)(a1 + 312) )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
    goto LABEL_163;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v33 = Windows::Telemetry::Base::Provider();
    v34 = (int)v33;
    if ( *(_DWORD *)v33 > 5u
      && (*((_QWORD *)v33 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v33 + 3) & 0x400000000000LL) == *((_QWORD *)v33 + 3) )
    {
      v96 = (__int64)"1507.2603.28012.0";
      v35 = (_QWORD *)SystemInterface::Providers::GetSystem(v109);
      v36 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v35 + 40LL))(*v35, v111);
      v37 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v36 + 440LL))(*v36, v114);
      if ( v37[3] > 7u )
        v37 = (_QWORD *)*v37;
      v95 = (__int64)v37;
      v38 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
      if ( v38[3] > 0xFu )
        v38 = (_QWORD *)*v38;
      v100 = (__int64)v38;
      v99 = *a9;
      LODWORD(v94) = a8;
      v39 = SystemInterface::Providers::GetSystem(v103);
      v40 = *(_QWORD *)v39 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v39 + 8LL) + 4LL);
      v41 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v40 + 96LL))(v40, v105);
      v42 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 8LL))(*v41);
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          if ( v43 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v44 = L"Internet";
        }
        else
        {
          v44 = L"local only";
        }
      }
      else
      {
        v44 = L"none";
      }
      v98 = (__int64)v44;
      v92[0] = a6;
      v91 = a5;
      v97 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v102 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v34,
        (int)&dword_14049FE75,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v102,
        (__int64)&CurrentThreadId,
        (__int64)&v97,
        (__int64)&v91,
        (__int64)v92,
        (__int64)&v98,
        (__int64)&v94,
        (__int64)&v99,
        (__int64)&v100,
        (__int64)&v95,
        (__int64)&v96);
      v45 = v106;
      if ( v106 )
      {
        if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
          if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
        }
      }
      v46 = v104;
      if ( v104 )
      {
        if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
      std::string::_Tidy_deallocate(v113);
      std::wstring::~wstring(v114);
      v47 = v112;
      if ( v112 )
      {
        if ( !_InterlockedDecrement(v112 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
          if ( !_InterlockedDecrement(v47 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
        }
      }
      v48 = v110;
      if ( v110 )
      {
        if ( !_InterlockedDecrement(v110 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
          if ( !_InterlockedDecrement(v48 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
        }
      }
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
    v49 = Windows::Telemetry::Base::Provider();
    v50 = (int)v49;
    if ( *(_DWORD *)v49 > 5u
      && (*((_QWORD *)v49 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v49 + 3) & 0x400000000000LL) == *((_QWORD *)v49 + 3) )
    {
      v96 = (__int64)"1507.2603.28012.0";
      v51 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v113);
      if ( v51[3] > 0xFu )
        v51 = (_QWORD *)*v51;
      v95 = (__int64)v51;
      v100 = *a9;
      LODWORD(v94) = a8;
      v52 = SystemInterface::Providers::GetSystem(v103);
      v53 = *(_QWORD *)v52 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v52 + 8LL) + 4LL);
      v54 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v53 + 96LL))(v53, v105);
      v55 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 8LL))(*v54);
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( v56 )
        {
          if ( v56 != 1 )
          {
            std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
            throw (std::logic_error *)pExceptionObject;
          }
          v57 = L"Internet";
        }
        else
        {
          v57 = L"local only";
        }
      }
      else
      {
        v57 = L"none";
      }
      v99 = (__int64)v57;
      v92[0] = a6;
      v91 = a5;
      v98 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v97 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v50,
        (int)&dword_14049FF23,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v97,
        (__int64)&CurrentThreadId,
        (__int64)&v98,
        (__int64)&v91,
        (__int64)v92,
        (__int64)&v99,
        (__int64)&v94,
        (__int64)&v100,
        (__int64)&v95,
        (__int64)&v96);
      v58 = v106;
      if ( v106 )
      {
        if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      v59 = v104;
      if ( v104 )
      {
        if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
          if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        }
      }
      std::string::_Tidy_deallocate(v113);
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
0x140272007  lea     rdx, dword_1404A011B; int
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
