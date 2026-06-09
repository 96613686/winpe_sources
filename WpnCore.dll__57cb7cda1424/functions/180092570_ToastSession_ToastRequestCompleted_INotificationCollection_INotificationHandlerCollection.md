# ToastSession::ToastRequestCompleted(INotificationCollection *,INotificationHandlerCollection *)

- ea: `0x180092570`
- end: `0x180093452`
- name: `?ToastRequestCompleted@ToastSession@@UEAAJPEAUINotificationCollection@@PEAUINotificationHandlerCollection@@@Z`
- size: `3810`
- prototype: `__int64 __fastcall(ToastSession *__hidden this, struct INotificationCollection *, struct INotificationHandlerCollection *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x18000e5f4`
- `0x180011618`
- `0x1800117c0`
- `0x180013360`
- `0x180014120`
- `0x18001bf30`
- `0x18004187c`
- `0x180049644`
- `0x18004b4c4`
- `0x1800542a8`
- `0x18007162c`
- `0x180079d24`
- `0x180084690`
- `0x180085560`
- `0x180086414`
- `0x1800884e8`
- `0x18008a97c`
- `0x180092570`
- `0x180094814`
- `0x180094854`
- `0x18009487c`
- `0x1800b99f0`
- `0x1800ba0d0`
- `0x1800ec8dc`
- `0x180104628`
- `0x180104660`
- `0x1801048ec`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800925c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800925c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092a7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092a6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180092cd5`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ceb`
- `OLEAUT32!__imp_SysAllocString` at `0x180092dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ddc`
- `OLEAUT32!__imp_SysAllocString` at `0x180093028`
- `OLEAUT32!__imp_SysAllocString` at `0x180092cd5`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ceb`
- `OLEAUT32!__imp_SysAllocString` at `0x180092dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ddc`
- `OLEAUT32!__imp_SysAllocString` at `0x180093028`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180092a51`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180092a51`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180092a99`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180092a99`

## string_xrefs

- `0x180092d60`: `AdaptiveJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall ToastSession::ToastRequestCompleted(
        ToastSession *this,
        struct INotificationCollection *a2,
        OLECHAR *a3)
{
  struct INotificationCollection *v3; // r14
  ToastSession *v4; // r15
  char *v5; // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  unsigned int i; // r12d
  __int64 (__fastcall *v16)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **); // rbx
  int v17; // eax
  WpnDatabaseHelpers *v18; // rdi
  __int64 (__fastcall *v19)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  unsigned __int16 **v22; // r8
  int AppUserModelId; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  WpnDatabaseHelpers *v27; // rdi
  __int64 (__fastcall *v28)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v29; // eax
  WpnDatabaseHelpers *v30; // rdi
  __int64 (__fastcall *v31)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v32; // eax
  WpnDatabaseHelpers *v33; // rdi
  __int64 (__fastcall *v34)(WpnDatabaseHelpers *, IStream **); // rbx
  int v35; // eax
  HRESULT v36; // eax
  SIZE_T QuadPart; // rbx
  HANDLE ProcessHeap; // rax
  void *v39; // r13
  HRESULT v40; // eax
  WpnDatabaseHelpers *v41; // rdi
  __int64 (__fastcall *v42)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v43; // eax
  _QWORD *v44; // r14
  WpnDatabaseHelpers *v45; // rdi
  int (__fastcall *v46)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v47; // eax
  unsigned int j; // r12d
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, _QWORD, __int64 *, __int64 *); // rbx
  int v51; // eax
  __int64 v52; // rbx
  _QWORD *v53; // rax
  __int64 v54; // r9
  __int64 v55; // rdx
  BSTR v56; // r13
  int v57; // eax
  unsigned int k; // r14d
  __int64 (__fastcall *v59)(BSTR, _QWORD, _QWORD **); // rbx
  int v60; // eax
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, OLECHAR **); // rbx
  int v63; // eax
  int v64; // eax
  __int64 v65; // r8
  wil *v66; // rcx
  int v67; // r8d
  int v68; // r9d
  int v70; // [rsp+20h] [rbp-2E8h]
  int v71; // [rsp+20h] [rbp-2E8h]
  WpnDatabaseHelpers *v72; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned int v73; // [rsp+48h] [rbp-2C0h] BYREF
  char *v74; // [rsp+50h] [rbp-2B8h] BYREF
  _QWORD *v75; // [rsp+58h] [rbp-2B0h] BYREF
  __int64 v76; // [rsp+60h] [rbp-2A8h] BYREF
  int v77; // [rsp+68h] [rbp-2A0h]
  __int64 v78; // [rsp+70h] [rbp-298h] BYREF
  __int64 v79; // [rsp+78h] [rbp-290h] BYREF
  unsigned int v80; // [rsp+80h] [rbp-288h] BYREF
  int v81; // [rsp+84h] [rbp-284h] BYREF
  unsigned int v82; // [rsp+88h] [rbp-280h]
  unsigned int v83; // [rsp+8Ch] [rbp-27Ch] BYREF
  __int64 v84; // [rsp+90h] [rbp-278h] BYREF
  IStream *pstm; // [rsp+98h] [rbp-270h] BYREF
  BSTR v86; // [rsp+A0h] [rbp-268h] BYREF
  int v87[2]; // [rsp+A8h] [rbp-260h] BYREF
  OLECHAR *v88; // [rsp+B0h] [rbp-258h] BYREF
  __int64 v89; // [rsp+B8h] [rbp-250h]
  __int64 v90; // [rsp+C0h] [rbp-248h]
  ULARGE_INTEGER pui; // [rsp+C8h] [rbp-240h] BYREF
  __int128 v92; // [rsp+D0h] [rbp-238h] BYREF
  __int64 v93; // [rsp+E0h] [rbp-228h]
  ToastSession *v94; // [rsp+E8h] [rbp-220h] BYREF
  OLECHAR *psz; // [rsp+F0h] [rbp-218h] BYREF
  __int64 v96; // [rsp+F8h] [rbp-210h]
  __int64 v97; // [rsp+100h] [rbp-208h]
  int v98[4]; // [rsp+108h] [rbp-200h] BYREF
  __int64 v99; // [rsp+118h] [rbp-1F0h]
  __int64 v100; // [rsp+120h] [rbp-1E8h] BYREF
  __int64 v101; // [rsp+128h] [rbp-1E0h]
  __int64 v102; // [rsp+130h] [rbp-1D8h]
  OLECHAR *v103; // [rsp+138h] [rbp-1D0h] BYREF
  __int64 v104; // [rsp+140h] [rbp-1C8h]
  __int64 v105; // [rsp+148h] [rbp-1C0h]
  OLECHAR *v106; // [rsp+150h] [rbp-1B8h] BYREF
  __int64 v107; // [rsp+158h] [rbp-1B0h]
  __int64 v108; // [rsp+160h] [rbp-1A8h]
  __int128 v109; // [rsp+168h] [rbp-1A0h] BYREF
  __int64 v110; // [rsp+178h] [rbp-190h]
  __int64 v111; // [rsp+180h] [rbp-188h] BYREF
  __int64 v112; // [rsp+188h] [rbp-180h]
  __int64 v113; // [rsp+190h] [rbp-178h]
  __int128 v114; // [rsp+198h] [rbp-170h] BYREF
  __int64 v115; // [rsp+1A8h] [rbp-160h]
  struct INotificationCollection *v116; // [rsp+1B0h] [rbp-158h]
  _QWORD v117[2]; // [rsp+1B8h] [rbp-150h] BYREF
  _QWORD v118[2]; // [rsp+1C8h] [rbp-140h] BYREF
  char v119; // [rsp+1D8h] [rbp-130h]
  _QWORD v120[2]; // [rsp+1E0h] [rbp-128h] BYREF
  _QWORD v121[2]; // [rsp+1F0h] [rbp-118h] BYREF
  int v122; // [rsp+200h] [rbp-108h]
  int v123; // [rsp+204h] [rbp-104h]
  __int64 v124; // [rsp+208h] [rbp-100h]
  char *v125; // [rsp+210h] [rbp-F8h]
  void *v126; // [rsp+218h] [rbp-F0h]
  DWORD LowPart; // [rsp+220h] [rbp-E8h]
  int v128; // [rsp+224h] [rbp-E4h]
  __int64 v129; // [rsp+228h] [rbp-E0h]
  GUID v130; // [rsp+230h] [rbp-D8h]
  BSTR v131; // [rsp+240h] [rbp-C8h]
  BSTR v132; // [rsp+248h] [rbp-C0h]
  __int64 v133; // [rsp+250h] [rbp-B8h]
  __int64 v134; // [rsp+258h] [rbp-B0h]
  __int128 v135; // [rsp+260h] [rbp-A8h]
  int v136; // [rsp+270h] [rbp-98h]
  unsigned int v137; // [rsp+274h] [rbp-94h]
  __int64 v138; // [rsp+278h] [rbp-90h]
  __int128 v139; // [rsp+280h] [rbp-88h]
  __int128 v140; // [rsp+290h] [rbp-78h]
  _BYTE v141[32]; // [rsp+2A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v86 = a3;
  v3 = a2;
  v116 = a2;
  v4 = this;
  v94 = this;
  v78 = 0;
  v5 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v74 = v5;
  if ( !*((_QWORD *)v4 + 2) || !*((_DWORD *)v4 + 3) || (v6 = *((_QWORD *)v4 + 3)) == 0 )
  {
    v8 = -2147467259;
    v9 = 961;
    goto LABEL_66;
  }
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v6 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  v8 = v7(v6, *((unsigned int *)v4 + 3), &GUID_904a654e_bee8_4654_bbba_e78766776239, &v78);
  if ( v8 < 0 )
  {
    v9 = 965;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
      (const char *)(unsigned int)v8,
      v70);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v74);
    goto LABEL_67;
  }
  v77 = 0;
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v74);
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL, v10) )
  {
    v74 = (char *)*((_QWORD *)v4 + 7);
    *(_QWORD *)v87 = *((_QWORD *)v4 + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v11,
      (unsigned int)&byte_18013A99F,
      v12,
      v13,
      (__int64)v87,
      (__int64)&v74);
  }
  try
  {
    v114 = 0;
    v115 = 0;
    *(_OWORD *)v98 = 0;
    v99 = 0;
    v109 = 0;
    v110 = 0;
    v92 = 0;
    v93 = 0;
    v118[0] = &v114;
    v118[1] = v98;
    v119 = 1;
    v80 = 0;
    v14 = (*(__int64 (__fastcall **)(struct INotificationCollection *, unsigned int *))(*(_QWORD *)v3 + 32LL))(v3, &v80);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3EB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v14,
        v70);
    for ( i = 0; ; ++i )
    {
      v82 = i;
      if ( i >= v80 )
        break;
      v72 = 0;
      v16 = *(__int64 (__fastcall **)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **))(*(_QWORD *)v3 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v17 = v16(v3, i, &v72);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v17,
          v70);
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v18 = v72;
      v19 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v72 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v111);
      v112 = -1;
      v113 = -1;
      v20 = v19(v18, &v111);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v20,
          v70);
      v81 = 0;
      *(_QWORD *)v87 = 0;
      v74 = 0;
      psz = 0;
      v96 = 0;
      v97 = 0;
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v106 = 0;
      v107 = 0;
      v108 = 0;
      v103 = 0;
      v104 = 0;
      v105 = 0;
      v21 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v72 + 24LL))(v72, &v81);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v21,
          v70);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
      v96 = -1;
      v97 = -1;
      AppUserModelId = WpnDatabaseHelpers::GetAppUserModelId(v72, (struct IWpnNotification *)&psz, v22);
      if ( AppUserModelId < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)AppUserModelId,
          v70);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v88);
      v89 = -1;
      v90 = -1;
      v24 = ToastSession::PopulatePFN((ToastSession *)((char *)v4 - 8), psz, &v88);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v24,
          v70);
      v25 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v72 + 88LL))(v72, v87);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v25,
          v70);
      v26 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, char **))(*(_QWORD *)v72 + 72LL))(v72, &v74);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v26,
          v70);
      v27 = v72;
      v28 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v72 + 56LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v106);
      v107 = -1;
      v108 = -1;
      v29 = v28(v27, &v106);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v29,
          v70);
      v30 = v72;
      v31 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v72 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v103);
      v104 = -1;
      v105 = -1;
      v32 = v31(v30, &v103);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x400,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v32,
          v70);
      pui.QuadPart = 0;
      pstm = 0;
      v33 = v72;
      v34 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, IStream **))(*(_QWORD *)v72 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
      v35 = v34(v33, &pstm);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v35,
          v70);
      v36 = IStream_Size(pstm, &pui);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x406,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v36,
          v70);
      QuadPart = pui.QuadPart;
      ProcessHeap = GetProcessHeap();
      v39 = HeapAlloc(ProcessHeap, 0, QuadPart);
      v40 = IStream_Read(pstm, v39, pui.LowPart);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x40D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v40,
          v70);
      v100 = 0;
      v101 = 0;
      v102 = 0;
      v41 = v72;
      v42 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v72 + 120LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v100);
      v101 = -1;
      v102 = -1;
      v43 = v42(v41, &v100);
      if ( v43 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x410,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v43,
          v70);
      v84 = 0;
      v44 = 0;
      v75 = 0;
      v73 = 0;
      v45 = v72;
      v46 = *(int (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v72 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      if ( v46(v45, &v84) >= 0 && v84 )
      {
        v47 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v84 + 48LL))(v84, &v73);
        if ( v47 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x418,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v47,
            v70);
        if ( v73 )
        {
          v44 = operator new(0x18u);
          *v44 = 0;
          v44[1] = 0;
          v44[2] = 0;
          v76 = 0;
          v75 = v44;
          std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(&v76);
          std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::reserve(v44, v73);
          for ( j = 0; j < v73; ++j )
          {
            v76 = 0;
            v79 = 0;
            v49 = v84;
            v50 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v84 + 56LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v79,
              0);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v76,
              0);
            v51 = v50(v49, j, &v76, &v79);
            if ( v51 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x424,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
                (const char *)(unsigned int)v51,
                v70);
            v120[0] = v76;
            v120[1] = v79;
            std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::push_back(v44, v120);
            v117[0] = v76;
            v76 = 0;
            v117[1] = v79;
            v79 = 0;
            std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::push_back(
              &v109,
              v117);
            std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v117);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v79);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v76);
          }
          i = v82;
        }
      }
      v121[0] = SysAllocString(psz);
      v121[1] = SysAllocString(v88);
      v122 = v81;
      v123 = 0;
      v124 = *(_QWORD *)v87;
      v125 = v74;
      v126 = v39;
      LowPart = pui.LowPart;
      v52 = v100;
      v53 = (_QWORD *)std::wstring::wstring(v141, L"AdaptiveJson");
      v54 = -1;
      do
        ++v54;
      while ( *(_WORD *)(v52 + 2 * v54) );
      v55 = v53[2];
      if ( v53[3] > 7u )
        v53 = (_QWORD *)*v53;
      v128 = (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v53, v55, v52, v54);
      v129 = 0;
      v130 = GUID_NULL;
      v131 = SysAllocString(v106);
      v132 = SysAllocString(v103);
      v133 = 0;
      v134 = 0;
      v135 = 0;
      v136 = 0;
      v137 = v73;
      if ( v44 )
        v138 = *v44;
      else
        v138 = 0;
      v139 = 0;
      v140 = 0;
      std::vector<_WPN_TOAST_NOTIFICATION>::_Emplace_one_at_back<_WPN_TOAST_NOTIFICATION>(&v114, v121);
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v141);
      if ( v44 )
      {
        if ( *((_QWORD *)&v92 + 1) == v93 )
        {
          std::vector<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>::_Emplace_reallocate<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>(
            (__int64 *)&v92,
            *((__int64 *)&v92 + 1),
            (__int64 *)&v75);
        }
        else
        {
          v75 = 0;
          **((_QWORD **)&v92 + 1) = v44;
          *((_QWORD *)&v92 + 1) += 8LL;
        }
      }
      std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(&v75);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v100);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v103);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v106);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v88);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v111);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v3 = v116;
    }
    v83 = 0;
    v56 = v86;
    v57 = (*(__int64 (__fastcall **)(BSTR, unsigned int *))(*(_QWORD *)v86 + 32LL))(v86, &v83);
    if ( v57 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v57,
        v70);
    for ( k = 0; k < v83; ++k )
    {
      v75 = 0;
      v59 = *(__int64 (__fastcall **)(BSTR, _QWORD, _QWORD **))(*(_QWORD *)v56 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
      v60 = v59(v56, k, &v75);
      if ( v60 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x44E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v60,
          v70);
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v61 = (__int64)v75;
      v62 = *(__int64 (__fastcall **)(__int64, OLECHAR **))(*v75 + 24LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v88);
      v89 = -1;
      v90 = -1;
      v63 = v62(v61, &v88);
      if ( v63 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x451,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v63,
          v70);
      v86 = SysAllocString(v88);
      std::vector<unsigned short const *>::_Emplace_one_at_back<unsigned short const *>(v98, &v86);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v88);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    }
    v71 = v98[0];
    v64 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v78 + 48LL))(
            v78,
            *((unsigned int *)v4 + 2),
            v114,
            0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)&v114 + 1) - v114) >> 4));
    if ( v64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v64,
        v71);
    v119 = 0;
    lambda_817ee658191cb58eccb943418947fb1c_::operator()(v118);
    if ( (_QWORD)v92 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>>(
        v92,
        *((__int64 *)&v92 + 1));
      std::_Deallocate<16>((void *)v92, (v93 - v92) & 0xFFFFFFFFFFFFFFF8uLL);
      v92 = 0;
      v93 = 0;
    }
    if ( (_QWORD)v109 )
    {
      std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
        v109,
        *((__int64 *)&v109 + 1));
      std::_Deallocate<16>((void *)v109, (v110 - v109) & 0xFFFFFFFFFFFFFFF0uLL);
      v109 = 0;
      v110 = 0;
    }
    if ( *(_QWORD *)v98 )
    {
      std::_Deallocate<16>(*(void **)v98, (v99 - *(_QWORD *)v98) & 0xFFFFFFFFFFFFFFF8uLL);
      *(_OWORD *)v98 = 0;
      v99 = 0;
    }
    v66 = (wil *)v114;
    if ( (_QWORD)v114 )
      std::_Deallocate<16>((void *)v114, 16 * ((v115 - (__int64)v114) >> 4));
  }
  catch ( ... )
  {
    v77 = wil::ResultFromCaughtException(v66);
    v4 = v94;
  }
  v8 = v77;
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL, v65) )
  {
    v94 = (ToastSession *)*((_QWORD *)v4 + 7);
    v86 = (BSTR)*((_QWORD *)v4 + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v86,
      (unsigned int)byte_18013AAC1,
      v67,
      v68,
      (__int64)&v86,
      (__int64)&v94);
  }
LABEL_67:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180092570  push    rbx
0x180092572  push    rsi
0x180092573  push    rdi
0x180092574  push    r12
0x180092576  push    r13
0x180092578  push    r14
0x18009257a  push    r15
0x18009257c  sub     rsp, 2D0h
0x180092583  mov     rax, cs:__security_cookie
0x18009258a  xor     rax, rsp
0x18009258d  mov     [rsp+308h+var_48], rax
0x180092595  mov     [rsp+308h+var_268], r8
0x18009259d  mov     r14, rdx
0x1800925a0  mov     [rsp+308h+var_158], rdx
0x1800925a8  mov     r15, rcx
0x1800925ab  mov     [rsp+308h+var_220], rcx
0x1800925b3  xor     esi, esi
0x1800925b5  mov     [rsp+308h+var_298], rsi
0x1800925ba  lea     rbx, [rcx+58h]
0x1800925be  mov     rcx, rbx; lpCriticalSection
0x1800925c1  call    cs:__imp_EnterCriticalSection
0x1800925c7  mov     [rsp+308h+var_2B8], rbx
0x1800925cc  cmp     [r15+10h], rsi
0x1800925d0  jz      loc_180093259
0x1800925d6  cmp     [r15+0Ch], esi
0x1800925da  jz      loc_180093259
0x1800925e0  mov     rdi, [r15+18h]
0x1800925e4  test    rdi, rdi
0x1800925e7  jz      loc_180093259
0x1800925ed  mov     rax, [rdi]
0x1800925f0  mov     rbx, [rax+28h]
0x1800925f4  lea     rcx, [rsp+308h+var_298]
0x1800925f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800925fe  lea     r9, [rsp+308h+var_298]
0x180092603  lea     r8, _GUID_904a654e_bee8_4654_bbba_e78766776239
0x18009260a  mov     edx, [r15+0Ch]
0x18009260e  mov     rcx, rdi
0x180092611  mov     rax, rbx
0x180092614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092619  mov     ebx, eax
0x18009261b  test    eax, eax
0x18009261d  jns     short loc_180092629
0x18009261f  mov     edx, 3C5h
0x180092624  jmp     loc_180093263
0x180092629  mov     [rsp+308h+var_2A0], esi
0x18009262d  lea     rcx, [rsp+308h+var_2B8]; this
0x180092632  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180092637  mov     eax, cs:dword_18015C038
0x18009263d  cmp     eax, 5
0x180092640  jbe     short loc_180092695
0x180092642  mov     rdx, 200000000000h
0x18009264c  lea     rcx, dword_18015C038
0x180092653  call    _tlgKeywordOn
0x180092658  test    al, al
0x18009265a  jz      short loc_180092695
0x18009265c  mov     rax, [r15+38h]
0x180092660  mov     [rsp+308h+var_2B8], rax
0x180092665  mov     rax, [r15+20h]
0x180092669  mov     qword ptr [rsp+308h+var_260], rax
0x180092671  lea     rax, [rsp+308h+var_2B8]
0x180092676  mov     [rsp+308h+var_2E0], rax
0x18009267b  lea     rax, [rsp+308h+var_260]
0x180092683  mov     qword ptr [rsp+308h+var_2E8], rax; int
0x180092688  lea     rdx, byte_18013A99F
0x18009268f  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180092694  nop
0x180092695  xorps   xmm0, xmm0
0x180092698  movdqu  [rsp+308h+var_170], xmm0
0x1800926a1  mov     [rsp+308h+var_160], rsi
0x1800926a9  movdqu  xmmword ptr [rsp+308h+var_200], xmm0
0x1800926b2  mov     [rsp+308h+var_1F0], rsi
0x1800926ba  movdqu  [rsp+308h+var_1A0], xmm0
0x1800926c3  mov     [rsp+308h+var_190], rsi
0x1800926cb  movdqu  [rsp+308h+var_238], xmm0
0x1800926d4  mov     [rsp+308h+var_228], rsi
0x1800926dc  lea     rax, [rsp+308h+var_170]
0x1800926e4  mov     [rsp+308h+var_140], rax
0x1800926ec  lea     rax, [rsp+308h+var_200]
0x1800926f4  mov     [rsp+308h+var_138], rax
0x1800926fc  mov     [rsp+308h+var_130], 1
0x180092704  mov     [rsp+308h+var_288], esi
0x18009270b  mov     rax, [r14]
0x18009270e  lea     rdx, [rsp+308h+var_288]
0x180092716  mov     rcx, r14
0x180092719  mov     rax, [rax+20h]
0x18009271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092722  mov     rcx, [rsp+308h]; this
0x18009272a  test    eax, eax
0x18009272c  js      loc_1800932B5
0x180092732  mov     r12d, esi
0x180092735  mov     [rsp+308h+var_280], r12d
0x18009273d  cmp     r12d, [rsp+308h+var_288]
0x180092745  jnb     loc_180092F36
0x18009274b  mov     [rsp+308h+var_2C8], rsi
0x180092750  mov     rax, [r14]
0x180092753  mov     rbx, [rax+18h]
0x180092757  lea     rcx, [rsp+308h+var_2C8]
0x18009275c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092761  lea     r8, [rsp+308h+var_2C8]
0x180092766  mov     edx, r12d
0x180092769  mov     rcx, r14
0x18009276c  mov     rax, rbx
0x18009276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092774  mov     rcx, [rsp+308h]; this
0x18009277c  test    eax, eax
0x18009277e  js      loc_1800932CA
0x180092784  mov     [rsp+308h+var_188], rsi
0x18009278c  mov     [rsp+308h+var_180], rsi
0x180092794  mov     [rsp+308h+var_178], rsi
0x18009279c  mov     rdi, [rsp+308h+var_2C8]
0x1800927a1  mov     rax, [rdi]
0x1800927a4  mov     rbx, [rax+28h]
0x1800927a8  lea     rcx, [rsp+308h+var_188]
0x1800927b0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800927b5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800927b9  mov     [rsp+308h+var_180], r14
0x1800927c1  mov     [rsp+308h+var_178], r14
0x1800927c9  lea     rdx, [rsp+308h+var_188]
0x1800927d1  mov     rcx, rdi
0x1800927d4  mov     rax, rbx
0x1800927d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800927dc  mov     rcx, [rsp+308h]; this
0x1800927e4  test    eax, eax
0x1800927e6  js      loc_1800932DF
0x1800927ec  mov     [rsp+308h+var_284], esi
0x1800927f3  mov     qword ptr [rsp+308h+var_260], rsi
0x1800927fb  mov     [rsp+308h+var_2B8], rsi
0x180092800  mov     [rsp+308h+psz], rsi
0x180092808  mov     [rsp+308h+var_210], rsi
0x180092810  mov     [rsp+308h+var_208], rsi
0x180092818  mov     [rsp+308h+var_258], rsi
0x180092820  mov     [rsp+308h+var_250], rsi
0x180092828  mov     [rsp+308h+var_248], rsi
0x180092830  mov     [rsp+308h+var_1B8], rsi
0x180092838  mov     [rsp+308h+var_1B0], rsi
0x180092840  mov     [rsp+308h+var_1A8], rsi
0x180092848  mov     [rsp+308h+var_1D0], rsi
0x180092850  mov     [rsp+308h+var_1C8], rsi
0x180092858  mov     [rsp+308h+var_1C0], rsi
0x180092860  mov     rcx, [rsp+308h+var_2C8]
0x180092865  mov     rax, [rcx]
0x180092868  lea     rdx, [rsp+308h+var_284]
0x180092870  mov     rax, [rax+18h]
0x180092874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092879  mov     rcx, [rsp+308h]; this
0x180092881  test    eax, eax
0x180092883  js      loc_1800932F4
0x180092889  lea     rcx, [rsp+308h+psz]
0x180092891  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092896  mov     [rsp+308h+var_210], r14
0x18009289e  mov     [rsp+308h+var_208], r14
0x1800928a6  lea     rdx, [rsp+308h+psz]; struct IWpnNotification *
0x1800928ae  mov     rcx, [rsp+308h+var_2C8]; this
0x1800928b3  call    ?GetAppUserModelId@WpnDatabaseHelpers@@YAJPEAUIWpnNotification@@PEAPEAG@Z; WpnDatabaseHelpers::GetAppUserModelId(IWpnNotification *,ushort * *)
0x1800928b8  mov     rcx, [rsp+308h]; this
0x1800928c0  test    eax, eax
0x1800928c2  js      loc_180093308
0x1800928c8  lea     rcx, [rsp+308h+var_258]
0x1800928d0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800928d5  mov     [rsp+308h+var_250], r14
0x1800928dd  mov     [rsp+308h+var_248], r14
0x1800928e5  lea     rcx, [r15-8]; this
0x1800928e9  lea     r8, [rsp+308h+var_258]; unsigned __int16 **
0x1800928f1  mov     rdx, [rsp+308h+psz]; unsigned __int16 *
0x1800928f9  call    ?PopulatePFN@ToastSession@@AEAAJPEBGPEAPEAG@Z; ToastSession::PopulatePFN(ushort const *,ushort * *)
0x1800928fe  mov     rcx, [rsp+308h]; this
0x180092906  test    eax, eax
0x180092908  js      loc_18009331C
0x18009290e  mov     rcx, [rsp+308h+var_2C8]
0x180092913  mov     rax, [rcx]
0x180092916  lea     rdx, [rsp+308h+var_260]
0x18009291e  mov     rax, [rax+58h]
0x180092922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092927  mov     rcx, [rsp+308h]; this
0x18009292f  test    eax, eax
0x180092931  js      loc_180093330
0x180092937  mov     rcx, [rsp+308h+var_2C8]
0x18009293c  mov     rax, [rcx]
0x18009293f  lea     rdx, [rsp+308h+var_2B8]
0x180092944  mov     rax, [rax+48h]
0x180092948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009294d  mov     rcx, [rsp+308h]; this
0x180092955  test    eax, eax
0x180092957  js      loc_180093344
0x18009295d  mov     rdi, [rsp+308h+var_2C8]
0x180092962  mov     rax, [rdi]
0x180092965  mov     rbx, [rax+38h]
0x180092969  lea     rcx, [rsp+308h+var_1B8]
0x180092971  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092976  mov     [rsp+308h+var_1B0], r14
0x18009297e  mov     [rsp+308h+var_1A8], r14
0x180092986  lea     rdx, [rsp+308h+var_1B8]
0x18009298e  mov     rcx, rdi
0x180092991  mov     rax, rbx
0x180092994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092999  mov     rcx, [rsp+308h]; this
0x1800929a1  test    eax, eax
0x1800929a3  js      loc_180093358
0x1800929a9  mov     rdi, [rsp+308h+var_2C8]
0x1800929ae  mov     rax, [rdi]
0x1800929b1  mov     rbx, [rax+40h]
0x1800929b5  lea     rcx, [rsp+308h+var_1D0]
0x1800929bd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800929c2  mov     [rsp+308h+var_1C8], r14
0x1800929ca  mov     [rsp+308h+var_1C0], r14
0x1800929d2  lea     rdx, [rsp+308h+var_1D0]
0x1800929da  mov     rcx, rdi
0x1800929dd  mov     rax, rbx
0x1800929e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929e5  mov     rcx, [rsp+308h]; this
0x1800929ed  test    eax, eax
0x1800929ef  js      loc_18009336C
0x1800929f5  mov     qword ptr [rsp+308h+pui], rsi
0x1800929fd  mov     [rsp+308h+pstm], rsi
0x180092a05  mov     rdi, [rsp+308h+var_2C8]
0x180092a0a  mov     rax, [rdi]
0x180092a0d  mov     rbx, [rax+30h]
0x180092a11  lea     rcx, [rsp+308h+pstm]
0x180092a19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092a1e  lea     rdx, [rsp+308h+pstm]
0x180092a26  mov     rcx, rdi
0x180092a29  mov     rax, rbx
0x180092a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a31  mov     rcx, [rsp+308h]; this
0x180092a39  test    eax, eax
0x180092a3b  js      loc_180093381
0x180092a41  lea     rdx, [rsp+308h+pui]; pui
0x180092a49  mov     rcx, [rsp+308h+pstm]; pstm
0x180092a51  call    cs:__imp_IStream_Size
0x180092a57  mov     rcx, [rsp+308h]; this
0x180092a5f  test    eax, eax
0x180092a61  js      loc_180093395
0x180092a67  mov     rbx, qword ptr [rsp+308h+pui]
0x180092a6f  call    cs:__imp_GetProcessHeap
0x180092a75  mov     r8, rbx; dwBytes
0x180092a78  xor     edx, edx; dwFlags
0x180092a7a  mov     rcx, rax; hHeap
0x180092a7d  call    cs:__imp_HeapAlloc
0x180092a83  mov     r13, rax
0x180092a86  mov     r8d, dword ptr [rsp+308h+pui]; cb
0x180092a8e  mov     rdx, rax; pv
0x180092a91  mov     rcx, [rsp+308h+pstm]; pstm
0x180092a99  call    cs:__imp_IStream_Read
0x180092a9f  mov     rcx, [rsp+308h]; this
0x180092aa7  test    eax, eax
0x180092aa9  js      loc_1800933A9
0x180092aaf  mov     [rsp+308h+var_1E8], rsi
0x180092ab7  mov     [rsp+308h+var_1E0], rsi
0x180092abf  mov     [rsp+308h+var_1D8], rsi
0x180092ac7  mov     rdi, [rsp+308h+var_2C8]
0x180092acc  mov     rax, [rdi]
0x180092acf  mov     rbx, [rax+78h]
0x180092ad3  lea     rcx, [rsp+308h+var_1E8]
0x180092adb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092ae0  mov     [rsp+308h+var_1E0], r14
0x180092ae8  mov     [rsp+308h+var_1D8], r14
0x180092af0  lea     rdx, [rsp+308h+var_1E8]
0x180092af8  mov     rcx, rdi
0x180092afb  mov     rax, rbx
0x180092afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b03  mov     rcx, [rsp+308h]; this
0x180092b0b  test    eax, eax
0x180092b0d  js      loc_1800933BE
0x180092b13  mov     [rsp+308h+var_278], rsi
0x180092b1b  mov     r14, rsi
0x180092b1e  mov     [rsp+308h+var_2B0], rsi
0x180092b23  mov     [rsp+308h+var_2C0], esi
0x180092b27  mov     rdi, [rsp+308h+var_2C8]
0x180092b2c  mov     rax, [rdi]
0x180092b2f  mov     rbx, [rax+60h]
0x180092b33  lea     rcx, [rsp+308h+var_278]
0x180092b3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092b40  lea     rdx, [rsp+308h+var_278]
0x180092b48  mov     rcx, rdi
0x180092b4b  mov     rax, rbx
0x180092b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b53  test    eax, eax
0x180092b55  js      loc_180092CCD
0x180092b5b  mov     rcx, [rsp+308h+var_278]
0x180092b63  test    rcx, rcx
0x180092b66  jz      loc_180092CCD
0x180092b6c  mov     rax, [rcx]
0x180092b6f  lea     rdx, [rsp+308h+var_2C0]
0x180092b74  mov     rax, [rax+30h]
0x180092b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b7d  mov     rcx, [rsp+308h]; this
0x180092b85  test    eax, eax
0x180092b87  js      loc_1800933D3
0x180092b8d  cmp     [rsp+308h+var_2C0], esi
0x180092b91  jbe     loc_180092CCD
0x180092b97  mov     ecx, 18h; Size
0x180092b9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180092ba1  mov     r14, rax
0x180092ba4  mov     [rax], rsi
0x180092ba7  mov     [rax+8], rsi
0x180092bab  mov     [rax+10h], rsi
0x180092baf  mov     [rsp+308h+var_2A8], rsi
0x180092bb4  mov     [rsp+308h+var_2B0], rax
0x180092bb9  lea     rcx, [rsp+308h+var_2A8]
0x180092bbe  call    ??1?$unique_ptr@V?$vector@U_WPN_NOTIFICATION_METADATA_PAIR@@V?$allocator@U_WPN_NOTIFICATION_METADATA_PAIR@@@std@@@std@@U?$default_delete@V?$vector@U_WPN_NOTIFICATION_METADATA_PAIR@@V?$allocator@U_WPN_NOTIFICATION_METADATA_PAIR@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(void)
  ... truncated ...
```
