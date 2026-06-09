# CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)

- ea: `0x1801a8b68`
- end: `0x1801a9cd0`
- name: `?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z`
- size: `4456`
- prototype: ``
- caller_count: `6`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c6e0`
- `0x1801a6c00`
- `0x1801a80b0`
- `0x1801a8b68`
- `0x1801b54c0`
- `0x1801b5b5c`

## callees

- `0x18000c62c`
- `0x180010b60`
- `0x180010cc0`
- `0x1800138b8`
- `0x18001d7f8`
- `0x18001de20`
- `0x1800217d8`
- `0x180023750`
- `0x18002573c`
- `0x1800261e0`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002b118`
- `0x1800345f0`
- `0x180051a7c`
- `0x1800658b8`
- `0x180068404`
- `0x180068b50`
- `0x180069710`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x180099f0c`
- `0x18009cf78`
- `0x1800a36d4`
- `0x1800a5934`
- `0x1800a6554`
- `0x1800a8678`
- `0x1800b980c`
- `0x1800eb920`
- `0x180129bdc`
- `0x1801a8b68`
- `0x1802d5010`

## string_xrefs

- `0x1801a8c31`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8dae`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8ede`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8fa3`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a92f5`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a934f`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9402`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9465`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a96a8`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9702`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9941`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a99ef`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9acb`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9b70`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9c1a`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9194`: `Unable to get selectability for Update: {}, skipping...`
- `0x1801a9098`: `Unable to get applicability for Update: {}, skipping...`
- `0x1801a9901`: `Failed to enumerate updates from child package`
- `0x1801a99af`: `Failed to open child package`
- `0x1801a93c2`: `Failed to create an instance of the update for public use.`
- `0x1801a92b5`: `Failed to retrieve the latest state for the update from Sessions.xml`

## pseudocode

```c
__int64 __fastcall CCbsPackage::InternalEnumerateUpdate(
        __int64 a1,
        struct CCbsSession *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        wchar_t *a7,
        int a8,
        __int64 a9,
        int a10,
        int a11,
        __int64 a12,
        __int64 a13)
{
  int UpdateStateFromSessionsXML; // edi
  __int64 v17; // rdx
  int SessionPackageState; // eax
  const wchar_t *v19; // r14
  unsigned __int64 i; // rbx
  __int64 v21; // rcx
  unsigned __int64 j; // rbx
  __int64 v23; // rcx
  int v24; // eax
  unsigned __int64 k; // rbx
  __int64 v26; // rcx
  int IsDelegated; // eax
  unsigned __int64 m; // rbx
  __int64 v29; // rcx
  __int64 *v30; // r15
  __int64 *v31; // r12
  wchar_t *v32; // rax
  __int64 v33; // rbx
  CCbsSession *v34; // rdi
  int Applicability; // eax
  const char *v36; // r8
  const wchar_t *v37; // rcx
  unsigned __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rcx
  struct CCbsPackage *v41; // rdi
  unsigned __int64 mm; // rbx
  const wchar_t *v43; // r8
  const wchar_t *v44; // rdx
  struct CCbsPublicUpdate **InitPointer; // rax
  __int64 v46; // rdx
  int v47; // eax
  unsigned __int64 kk; // rbx
  __int64 v49; // rcx
  unsigned __int64 n; // rbx
  __int64 v51; // rcx
  unsigned __int64 jj; // rbx
  __int64 v53; // rcx
  unsigned __int64 ii; // rbx
  __int64 v55; // rcx
  unsigned __int64 i7; // rbx
  __int64 v57; // rcx
  int v58; // eax
  int v59; // r14d
  __int64 v60; // rcx
  unsigned __int64 v61; // r8
  unsigned __int64 v62; // r14
  __int64 v63; // r15
  struct ICbsIdentity *v64; // rdx
  struct CCbsSession *v65; // r12
  struct CCbsIdentity *v66; // r8
  __int64 v67; // rdi
  wchar_t *FastCbsIdentityString; // rax
  unsigned int v69; // eax
  unsigned __int64 i4; // rbx
  __int64 v71; // rcx
  unsigned __int64 nn; // rbx
  __int64 v73; // rcx
  struct CCbsPackage **v74; // rax
  bool v75; // cl
  unsigned __int64 i6; // rbx
  __int64 v77; // rcx
  unsigned __int64 i5; // rbx
  __int64 v79; // rcx
  unsigned __int64 i3; // rbx
  __int64 v81; // rcx
  unsigned __int64 i2; // rbx
  __int64 v83; // rcx
  unsigned __int64 i1; // rbx
  __int64 v85; // rcx
  unsigned __int64 v86; // rbx
  __int64 v87; // rcx
  int v89; // [rsp+20h] [rbp-E0h]
  int v90; // [rsp+20h] [rbp-E0h]
  int v91[2]; // [rsp+70h] [rbp-90h] BYREF
  int v92[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v93; // [rsp+80h] [rbp-80h]
  __int64 v94; // [rsp+88h] [rbp-78h] BYREF
  int v95[2]; // [rsp+90h] [rbp-70h] BYREF
  struct CCbsSession *v96; // [rsp+98h] [rbp-68h]
  __int64 v97; // [rsp+A0h] [rbp-60h]
  _BYTE v98[24]; // [rsp+A8h] [rbp-58h] BYREF
  int v99; // [rsp+C0h] [rbp-40h] BYREF
  int v100; // [rsp+C4h] [rbp-3Ch] BYREF
  const wchar_t *v101; // [rsp+C8h] [rbp-38h] BYREF
  int v102; // [rsp+D0h] [rbp-30h] BYREF
  struct CCbsPackage *v103; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v104[24]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v105; // [rsp+F8h] [rbp-8h]
  __int64 v106; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *(_QWORD *)v95 = a12;
  v93 = a7;
  v97 = a13;
  v102 = a4;
  *(_QWORD *)v92 = a3;
  v96 = a2;
  *(_QWORD *)v91 = a9;
  if ( !a2 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v99 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session specified");
      *(_QWORD *)v91 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v91);
    }
    v17 = 585;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x80070057LL,
      v89);
    return (unsigned int)UpdateStateFromSessionsXML;
  }
  if ( !a3 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v99 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No visited packages specified");
      *(_QWORD *)v91 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v91);
    }
    v17 = 586;
    goto LABEL_5;
  }
  if ( !a9 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v99 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No enumeration object specified");
      *(_QWORD *)v91 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v91);
    }
    v17 = 587;
    goto LABEL_5;
  }
  CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(v104);
  v100 = 0;
  v103 = 0;
  SessionPackageState = CCbsSession::GetSessionPackageState(a2, (struct CCbsPackage *)a1, &v103, 0);
  UpdateStateFromSessionsXML = SessionPackageState;
  if ( SessionPackageState < 0 )
  {
    v99 = SessionPackageState;
    if ( LogAdapter::g_Logger )
    {
      v19 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 120) )
        v19 = *(const wchar_t **)(a1 + 120);
      *(_QWORD *)v91 = v19;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get per-session package state for package: {}",
        (__int64)v91);
      *(_QWORD *)v95 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v95);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v89);
    if ( v105 )
    {
      for ( i = 0; i < v105; ++i )
      {
        v21 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    goto LABEL_196;
  }
  v101 = (const wchar_t *)a1;
  v94 = 0xFFFFFFFFLL;
  if ( CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::FastFind(a3, &v101, &v94) != 0xFFFFFFFFLL )
  {
    if ( v105 )
    {
      for ( j = 0; j < v105; ++j )
      {
        v23 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * j) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    goto LABEL_195;
  }
  v101 = (const wchar_t *)a1;
  v24 = CCbsInterfaceArray<CCbsPackage *>::InsertAt(a3, &v101, v94);
  UpdateStateFromSessionsXML = v24;
  if ( v24 < 0 )
  {
    v99 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add package to the visited list");
      *(_QWORD *)v91 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v91);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v89);
    if ( v105 )
    {
      for ( k = 0; k < v105; ++k )
      {
        v26 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * k) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
    }
    goto LABEL_196;
  }
  IsDelegated = CCbsPackage::IsDelegated((CCbsPackage *)a1, a2, &v100);
  UpdateStateFromSessionsXML = IsDelegated;
  if ( IsDelegated < 0 )
  {
    v99 = IsDelegated;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get delegate state.");
      *(_QWORD *)v91 = &v99;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v91);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v89);
    if ( v105 )
    {
      for ( m = 0; m < v105; ++m )
      {
        v29 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * m) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
    goto LABEL_196;
  }
  if ( v100 && !a6 )
    goto LABEL_191;
  v30 = *(__int64 **)(a1 + 752);
  v31 = &v30[*(_QWORD *)(a1 + 736)];
  if ( v30 != v31 )
  {
    v32 = v93;
    do
    {
      v33 = *v30;
      v100 = 1;
      LODWORD(v101) = 4096;
      v99 = 1;
      if ( v32 && !(unsigned int)CCbsUpdate::MatchNameCaseInsensitive((CCbsUpdate *)v33, v32) )
        goto LABEL_55;
      v34 = v96;
      if ( v102 && v102 != 7 )
      {
        Applicability = CCbsUpdate::GetApplicability(
                          (CCbsUpdate *)v33,
                          v96,
                          (enum _CbsApplicability *)&v100,
                          (enum CbsState *)&v101);
        if ( Applicability < 0 )
        {
          v36 = "Unable to get applicability for Update: {}, skipping...";
LABEL_52:
          v37 = &qword_1802EB518;
          if ( *(_QWORD *)(v33 + 32) )
            v37 = *(const wchar_t **)(v33 + 32);
          v101 = v37;
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(1, (unsigned int)Applicability, v36, &v101);
LABEL_55:
          v32 = v93;
          goto LABEL_56;
        }
        if ( (v102 & v100) == 0 )
          goto LABEL_55;
      }
      if ( a5 && a5 != 31 )
      {
        Applicability = CCbsUpdate::GetSelectability((CCbsUpdate *)v33, (enum _CbsSelectability *)&v99);
        if ( Applicability < 0 )
        {
          v36 = "Unable to get selectability for Update: {}, skipping...";
          goto LABEL_52;
        }
        if ( (a5 & v99) == 0 )
          goto LABEL_55;
      }
      if ( a10 && !a11 )
      {
        v43 = &qword_1802EB518;
        v44 = &qword_1802EB518;
        if ( *(_QWORD *)(v33 + 32) )
          v43 = *(const wchar_t **)(v33 + 32);
        if ( *(_QWORD *)(a1 + 120) )
          v44 = *(const wchar_t **)(a1 + 120);
        UpdateStateFromSessionsXML = CCbsSession::GetUpdateStateFromSessionsXML(
                                       v34,
                                       v44,
                                       v43,
                                       (enum CbsState *)(v33 + 440));
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v101) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to retrieve the latest state for the update from Sessions.xml");
            *(_QWORD *)v91 = &v101;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v91);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AC,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v89);
          if ( v105 )
          {
            for ( n = 0; n < v105; ++n )
            {
              v51 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * n) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
            }
          }
          goto LABEL_196;
        }
      }
      v94 = 0;
      InitPointer = (struct CCbsPublicUpdate **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v94);
      UpdateStateFromSessionsXML = CCbsUpdate::CreatePublicInstance((CCbsUpdate *)v33, v96, InitPointer);
      if ( UpdateStateFromSessionsXML < 0 )
      {
        LODWORD(v101) = UpdateStateFromSessionsXML;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create an instance of the update for public use.");
          *(_QWORD *)v91 = &v101;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v91);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B6,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)UpdateStateFromSessionsXML,
          v89);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v94);
        if ( v105 )
        {
          for ( ii = 0; ii < v105; ++ii )
          {
            v55 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * ii) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          }
        }
        goto LABEL_196;
      }
      v46 = v94;
      if ( v94 )
        v46 = *(int *)(*(_QWORD *)(v94 + 8) + 4LL) + v94 + 8;
      v47 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(*(_QWORD *)v91, v46);
      UpdateStateFromSessionsXML = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B8,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v47,
          v89);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v94);
        if ( v105 )
        {
          for ( jj = 0; jj < v105; ++jj )
          {
            v53 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * jj) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          }
        }
        goto LABEL_196;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v94);
      v32 = v93;
      if ( v93 )
      {
        if ( v105 )
        {
          for ( kk = 0; kk < v105; ++kk )
          {
            v49 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * kk) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
        }
        goto LABEL_195;
      }
LABEL_56:
      ++v30;
    }
    while ( v30 != v31 );
  }
  if ( !a8 )
  {
LABEL_191:
    v61 = v105;
LABEL_192:
    if ( v61 )
    {
      v86 = 0;
      do
      {
        v87 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * v86) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
        ++v86;
      }
      while ( v86 < v105 );
    }
    goto LABEL_195;
  }
  CritSecLocker::CritSecLocker((CritSecLocker *)v98, (struct AutoCritSec *)(a1 + 1064), 1);
  if ( !*(_QWORD *)(a1 + 1208) )
  {
LABEL_64:
    v41 = v103;
    for ( mm = 0; mm < *((_QWORD *)v41 + 19); ++mm )
    {
      v58 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v104, *((_QWORD *)v41 + 21) + 8 * mm);
      v59 = v58;
      if ( v58 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D8,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v58,
          v89);
        CritSecLocker::~CritSecLocker((CritSecLocker *)v98);
        if ( v105 )
        {
          for ( nn = 0; nn < v105; ++nn )
          {
            v73 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * nn) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
          }
        }
        UpdateStateFromSessionsXML = v59;
        goto LABEL_196;
      }
      if ( mm >= *((_QWORD *)v41 + 19) )
        __fastfail(8u);
      v60 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v41 + 21) + 8 * mm) + 8LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v60);
    }
    CritSecLocker::~CritSecLocker((CritSecLocker *)v98);
    v61 = v105;
    v62 = 0;
    if ( !v105 )
    {
LABEL_195:
      UpdateStateFromSessionsXML = 0;
      goto LABEL_196;
    }
    while ( 1 )
    {
      v63 = *(_QWORD *)(v106 + 8 * v62);
      if ( *(int *)v63 >= 3 )
        break;
LABEL_157:
      if ( ++v62 >= v61 )
        goto LABEL_192;
    }
    v64 = *(struct ICbsIdentity **)(v63 + 8);
    if ( !v64 )
    {
      UpdateStateFromSessionsXML = -2146498560;
      v100 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Child package has no identity");
        *(_QWORD *)v92 = &v100;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v92);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)0x800F0800LL,
        v89);
      if ( v105 )
      {
        for ( i1 = 0; i1 < v105; ++i1 )
        {
          v85 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i1) + 8LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
        }
      }
      goto LABEL_196;
    }
    v100 = 0;
    v99 = 0;
    if ( v62 >= v61 )
      __fastfail(8u);
    v65 = v96;
    UpdateStateFromSessionsXML = CCbsSession::QueryPackageIntendedState(v96, v64, 0, 0, (enum CbsState *)&v100);
    if ( UpdateStateFromSessionsXML < 0 )
    {
      v102 = UpdateStateFromSessionsXML;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to query store state");
        *(_QWORD *)v92 = &v102;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v92);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F6,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)(unsigned int)UpdateStateFromSessionsXML,
        v89);
      if ( v105 )
      {
        for ( i2 = 0; i2 < v105; ++i2 )
        {
          v83 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i2) + 8LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        }
      }
      goto LABEL_196;
    }
    if ( v100 < 96 )
    {
      if ( v100 == 80 )
        goto LABEL_156;
      if ( v62 >= v105 )
        __fastfail(8u);
      UpdateStateFromSessionsXML = IsPackageActive(
                                     v65,
                                     *(struct CCbsIdentity **)(*(_QWORD *)(v106 + 8 * v62) + 8LL),
                                     &v99);
      if ( UpdateStateFromSessionsXML < 0 )
      {
        v99 = UpdateStateFromSessionsXML;
        if ( LogAdapter::g_Logger )
        {
          if ( v62 >= v105 )
            __fastfail(8u);
          *(_QWORD *)v92 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(*(_QWORD *)(v106 + 8 * v62) + 8LL));
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to check whether the package is active: {}",
            (__int64)v92);
          *(_QWORD *)v95 = &v99;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v95);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33D,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)UpdateStateFromSessionsXML,
          v89);
        if ( v105 )
        {
          for ( i3 = 0; i3 < v105; ++i3 )
          {
            v81 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i3) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
          }
        }
        goto LABEL_196;
      }
      if ( !v99 )
        goto LABEL_156;
      goto LABEL_151;
    }
    if ( *(_DWORD *)(v63 + 16) == -1 )
    {
      v66 = *(struct CCbsIdentity **)(v63 + 8);
      v99 = 0;
      UpdateStateFromSessionsXML = CCbsPackage::IsChild((CCbsPackage *)a1, v65, v66, &v99);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl'::`2'::impl) )
      {
        if ( UpdateStateFromSessionsXML < 0 )
        {
          if ( a10 )
          {
            if ( v97 )
              *(_DWORD *)v97 = UpdateStateFromSessionsXML;
            v67 = *(_QWORD *)v95;
            if ( *(_QWORD *)v95 )
            {
              FastCbsIdentityString = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v63 + 8));
              v69 = SczAllocFormatted(v67, L"%ws.mum", FastCbsIdentityString);
              LogAdapter::TraceAtLevelIfFailed<long,>(1, v69, "Unable to allocate string");
            }
            UpdateStateFromSessionsXML = 0;
          }
          if ( UpdateStateFromSessionsXML < 0 )
          {
LABEL_129:
            LODWORD(v101) = UpdateStateFromSessionsXML;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v92 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v63 + 8));
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to check whether this is the real child: {}",
                (__int64)v92);
              *(_QWORD *)v91 = &v101;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v91);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x321,
              (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
              (const char *)(unsigned int)UpdateStateFromSessionsXML,
              v89);
            if ( v105 )
            {
              for ( i4 = 0; i4 < v105; ++i4 )
              {
                v71 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i4) + 8LL);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              }
            }
            goto LABEL_196;
          }
        }
      }
      else if ( UpdateStateFromSessionsXML < 0 && !a10 )
      {
        goto LABEL_129;
      }
      if ( v99 )
      {
        *(_DWORD *)(v63 + 16) = 1;
LABEL_151:
        v103 = 0;
        v74 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v103);
        if ( v62 >= v105 )
          __fastfail(8u);
        UpdateStateFromSessionsXML = CCbsSession::ResolvePackage(
                                       v65,
                                       0,
                                       0,
                                       0,
                                       *(struct ICbsIdentity **)(*(_QWORD *)(v106 + 8 * v62) + 8LL),
                                       1,
                                       v74,
                                       0);
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v101) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open child package");
            *(_QWORD *)v92 = &v101;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v92);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34F,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v90);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v103);
          if ( v105 )
          {
            for ( i5 = 0; i5 < v105; ++i5 )
            {
              v79 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i5) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            }
          }
          goto LABEL_196;
        }
        v75 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl'::`2'::impl) != 0;
        UpdateStateFromSessionsXML = CCbsPackage::InternalEnumerateUpdate(
                                       (_DWORD)v103,
                                       (_DWORD)v65,
                                       v92[0],
                                       v102,
                                       a5,
                                       1,
                                       (__int64)v93,
                                       1,
                                       *(__int64 *)v91,
                                       a10,
                                       a11 & (unsigned int)-v75,
                                       *(_QWORD *)v95 & -(__int64)v75,
                                       v97 & -(__int64)v75);
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v101) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate updates from child package");
            *(_QWORD *)v92 = &v101;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v92);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x371,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v89);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v103);
          if ( v105 )
          {
            for ( i6 = 0; i6 < v105; ++i6 )
            {
              v77 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i6) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
            }
          }
          goto LABEL_196;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v103);
        goto LABEL_156;
      }
      *(_DWORD *)(v63 + 16) = 0;
    }
    else if ( *(_DWORD *)(v63 + 16) == 1 )
    {
      goto LABEL_151;
    }
LABEL_156:
    v61 = v105;
    goto LABEL_157;
  }
  v38 = 0;
  while ( 1 )
  {
    v39 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v104, *(_QWORD *)(a1 + 1224) + 8 * v38);
    UpdateStateFromSessionsXML = v39;
    if ( v39 < 0 )
      break;
    if ( v38 >= *(_QWORD *)(a1 + 1208) )
      __fastfail(8u);
    v40 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1224) + 8 * v38) + 8LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    if ( ++v38 >= *(_QWORD *)(a1 + 1208) )
      goto LABEL_64;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D0,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
    (const char *)(unsigned int)v39,
    v89);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v98);
  if ( v105 )
  {
    for ( i7 = 0; i7 < v105; ++i7 )
    {
      v57 = *(_QWORD *)(*(_QWORD *)(v106 + 8 * i7) + 8LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
  }
LABEL_196:
  CCbsArrayBase<CCbsUpdate *,CCbsArray<CCbsUpdate *>>::~CCbsArrayBase<CCbsUpdate *,CCbsArray<CCbsUpdate *>>(v104);
  return (unsigned int)UpdateStateFromSessionsXML;
}

```

## disassembly

```asm
0x1801a8b68  push    rbp
0x1801a8b6a  push    rbx
0x1801a8b6b  push    rsi
0x1801a8b6c  push    rdi
0x1801a8b6d  push    r12
0x1801a8b6f  push    r13
0x1801a8b71  push    r14
0x1801a8b73  push    r15
0x1801a8b75  lea     rbp, [rsp-38h]
0x1801a8b7a  sub     rsp, 138h
0x1801a8b81  mov     rax, cs:__security_cookie
0x1801a8b88  xor     rax, rsp
0x1801a8b8b  mov     [rbp+70h+var_50], rax
0x1801a8b8f  mov     rax, [rbp+70h+arg_58]
0x1801a8b96  mov     r13, rcx
0x1801a8b99  mov     rcx, [rbp+70h+arg_40]
0x1801a8ba0  mov     rsi, r8
0x1801a8ba3  mov     qword ptr [rbp+70h+var_E0], rax
0x1801a8ba7  mov     rbx, rdx
0x1801a8baa  mov     rax, [rbp+70h+arg_30]
0x1801a8bb1  mov     [rbp+70h+var_F0], rax
0x1801a8bb5  mov     rax, [rbp+70h+arg_60]
0x1801a8bbc  mov     [rbp+70h+var_D0], rax
0x1801a8bc0  mov     [rbp+70h+var_A0], r9d
0x1801a8bc4  mov     qword ptr [rsp+170h+var_F8], r8
0x1801a8bc9  mov     [rbp+70h+var_D8], rdx
0x1801a8bcd  mov     qword ptr [rsp+170h+var_100], rcx
0x1801a8bd2  test    rdx, rdx
0x1801a8bd5  jnz     short loc_1801A8C45
0x1801a8bd7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8bde  mov     edi, 80070057h
0x1801a8be3  mov     [rbp+70h+var_B0], edi
0x1801a8be6  test    rcx, rcx
0x1801a8be9  jz      short loc_1801A8C28
0x1801a8beb  lea     ebx, [rdx+3]
0x1801a8bee  mov     r8d, ebx
0x1801a8bf1  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1801a8bf8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8bfd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c04  lea     rax, [rbp+70h+var_B0]
0x1801a8c08  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8c0d  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8c14  lea     rax, [rsp+170h+var_100]
0x1801a8c19  mov     r8d, ebx
0x1801a8c1c  mov     dl, 1
0x1801a8c1e  mov     [rsp+170h+var_150], rax; int
0x1801a8c23  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8c28  mov     edx, 249h; void *
0x1801a8c2d  mov     rcx, [rbp+78h]; this
0x1801a8c31  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8c38  mov     r9d, edi; char *
0x1801a8c3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8c40  jmp     loc_1801A9CAD
0x1801a8c45  test    rsi, rsi
0x1801a8c48  jnz     short loc_1801A8CA4
0x1801a8c4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c51  mov     edi, 80070057h
0x1801a8c56  mov     [rbp+70h+var_B0], edi
0x1801a8c59  test    rcx, rcx
0x1801a8c5c  jz      short loc_1801A8C9D
0x1801a8c5e  lea     ebx, [rsi+3]
0x1801a8c61  xor     edx, edx
0x1801a8c63  mov     r8d, ebx
0x1801a8c66  lea     r9, aNoVisitedPacka; "No visited packages specified"
0x1801a8c6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8c72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c79  lea     rax, [rbp+70h+var_B0]
0x1801a8c7d  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8c82  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8c89  lea     rax, [rsp+170h+var_100]
0x1801a8c8e  mov     r8d, ebx
0x1801a8c91  mov     dl, 1
0x1801a8c93  mov     [rsp+170h+var_150], rax
0x1801a8c98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8c9d  mov     edx, 24Ah
0x1801a8ca2  jmp     short loc_1801A8C2D
0x1801a8ca4  test    rcx, rcx
0x1801a8ca7  jnz     short loc_1801A8D08
0x1801a8ca9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8cb0  mov     edi, 80070057h
0x1801a8cb5  mov     [rbp+70h+var_B0], edi
0x1801a8cb8  test    rcx, rcx
0x1801a8cbb  jz      short loc_1801A8CFE
0x1801a8cbd  mov     ebx, 3
0x1801a8cc2  lea     r9, aNoEnumerationO; "No enumeration object specified"
0x1801a8cc9  mov     r8d, ebx
0x1801a8ccc  xor     edx, edx
0x1801a8cce  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8cd3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8cda  lea     rax, [rbp+70h+var_B0]
0x1801a8cde  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8ce3  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8cea  lea     rax, [rsp+170h+var_100]
0x1801a8cef  mov     r8d, ebx
0x1801a8cf2  mov     dl, 1
0x1801a8cf4  mov     [rsp+170h+var_150], rax
0x1801a8cf9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8cfe  mov     edx, 24Bh
0x1801a8d03  jmp     loc_1801A8C2D
0x1801a8d08  lea     rcx, [rbp+70h+var_90]
0x1801a8d0c  call    ??0?$CCbsArray@U_DRIVER_UPDATE@@@@QEAA@XZ; CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(void)
0x1801a8d11  xor     r9d, r9d; unsigned __int64 *
0x1801a8d14  mov     [rbp+70h+var_AC], 0
0x1801a8d1b  lea     r8, [rbp+70h+var_98]; struct PerSessionPackageState **
0x1801a8d1f  mov     [rbp+70h+var_98], 0
0x1801a8d27  mov     rdx, r13; struct CCbsPackage *
0x1801a8d2a  mov     rcx, rbx; this
0x1801a8d2d  call    ?GetSessionPackageState@CCbsSession@@QEAAJPEAVCCbsPackage@@PEAPEAUPerSessionPackageState@@PEA_K@Z; CCbsSession::GetSessionPackageState(CCbsPackage *,PerSessionPackageState * *,unsigned __int64 *)
0x1801a8d32  mov     edi, eax
0x1801a8d34  test    eax, eax
0x1801a8d36  jns     loc_1801A8E06
0x1801a8d3c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8d43  mov     [rbp+70h+var_B0], eax
0x1801a8d46  test    rcx, rcx
0x1801a8d49  jz      short loc_1801A8DAA
0x1801a8d4b  cmp     qword ptr [r13+78h], 0
0x1801a8d50  lea     rax, [rsp+170h+var_100]
0x1801a8d55  lea     r14, qword_1802EB518
0x1801a8d5c  mov     [rsp+170h+var_150], rax
0x1801a8d61  cmovnz  r14, [r13+78h]
0x1801a8d66  lea     r9, aFailedToGetPer_1; "Failed to get per-session package state"...
0x1801a8d6d  mov     ebx, 3
0x1801a8d72  mov     qword ptr [rsp+170h+var_100], r14
0x1801a8d77  xor     edx, edx
0x1801a8d79  mov     r8d, ebx
0x1801a8d7c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801a8d81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8d88  lea     rax, [rbp+70h+var_B0]
0x1801a8d8c  mov     qword ptr [rbp+70h+var_E0], rax
0x1801a8d90  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8d97  lea     rax, [rbp+70h+var_E0]
0x1801a8d9b  mov     r8d, ebx
0x1801a8d9e  mov     dl, 1
0x1801a8da0  mov     [rsp+170h+var_150], rax; int
0x1801a8da5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8daa  mov     rcx, [rbp+78h]; this
0x1801a8dae  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8db5  mov     r9d, edi; char *
0x1801a8db8  mov     edx, 25Bh; void *
0x1801a8dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8dc2  mov     rax, [rbp+70h+var_78]
0x1801a8dc6  test    rax, rax
0x1801a8dc9  jz      loc_1801A9CA4
0x1801a8dcf  xor     ebx, ebx
0x1801a8dd1  lea     esi, [rbx+8]
0x1801a8dd4  cmp     rbx, rax
0x1801a8dd7  jb      short loc_1801A8DDD
0x1801a8dd9  mov     ecx, esi
0x1801a8ddb  int     29h; Win8: RtlFailFast(ecx)
0x1801a8ddd  mov     rax, [rbp+70h+var_68]
0x1801a8de1  mov     rcx, [rax+rbx*8]
0x1801a8de5  mov     rcx, [rcx+8]
0x1801a8de9  mov     rax, [rcx]
0x1801a8dec  mov     rax, [rax+10h]
0x1801a8df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8df5  mov     rax, [rbp+70h+var_78]
0x1801a8df9  inc     rbx
0x1801a8dfc  cmp     rbx, rax
0x1801a8dff  jb      short loc_1801A8DDD
0x1801a8e01  jmp     loc_1801A9CA4
0x1801a8e06  mov     edi, 0FFFFFFFFh
0x1801a8e0b  mov     [rbp+70h+var_A8], r13
0x1801a8e0f  lea     r8, [rbp+70h+var_E8]
0x1801a8e13  mov     [rbp+70h+var_E8], rdi
0x1801a8e17  lea     rdx, [rbp+70h+var_A8]
0x1801a8e1b  mov     rcx, rsi
0x1801a8e1e  call    ?FastFind@?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@QEBA_KAEBQEAVCCbsPackage@@PEA_KP6AH00@Z@Z; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::FastFind(CCbsPackage * const &,unsigned __int64 *,int (*)(CCbsPackage * const &,CCbsPackage * const &))
0x1801a8e23  cmp     rax, rdi
0x1801a8e26  jz      short loc_1801A8E6C
0x1801a8e28  mov     rax, [rbp+70h+var_78]
0x1801a8e2c  test    rax, rax
0x1801a8e2f  jz      loc_1801A9CA2
0x1801a8e35  xor     ebx, ebx
0x1801a8e37  lea     esi, [rbx+8]
0x1801a8e3a  cmp     rbx, rax
0x1801a8e3d  jb      short loc_1801A8E43
0x1801a8e3f  mov     ecx, esi
0x1801a8e41  int     29h; Win8: RtlFailFast(ecx)
0x1801a8e43  mov     rax, [rbp+70h+var_68]
0x1801a8e47  mov     rcx, [rax+rbx*8]
0x1801a8e4b  mov     rcx, [rcx+8]
0x1801a8e4f  mov     rax, [rcx]
0x1801a8e52  mov     rax, [rax+10h]
0x1801a8e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8e5b  mov     rax, [rbp+70h+var_78]
0x1801a8e5f  inc     rbx
0x1801a8e62  cmp     rbx, rax
0x1801a8e65  jb      short loc_1801A8E43
0x1801a8e67  jmp     loc_1801A9CA2
0x1801a8e6c  mov     r8, [rbp+70h+var_E8]
0x1801a8e70  lea     rdx, [rbp+70h+var_A8]
0x1801a8e74  mov     rcx, rsi
0x1801a8e77  mov     [rbp+70h+var_A8], r13
0x1801a8e7b  call    ?InsertAt@?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAAJAEBQEAVCCbsPackage@@_K@Z; CCbsInterfaceArray<CCbsPackage *>::InsertAt(CCbsPackage * const &,unsigned __int64)
0x1801a8e80  mov     edi, eax
0x1801a8e82  test    eax, eax
0x1801a8e84  jns     loc_1801A8F36
0x1801a8e8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8e91  mov     [rbp+70h+var_B0], eax
0x1801a8e94  test    rcx, rcx
0x1801a8e97  jz      short loc_1801A8EDA
0x1801a8e99  mov     ebx, 3
0x1801a8e9e  lea     r9, aFailedToAddPac_4; "Failed to add package to the visited li"...
0x1801a8ea5  mov     r8d, ebx
0x1801a8ea8  xor     edx, edx
0x1801a8eaa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8eaf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8eb6  lea     rax, [rbp+70h+var_B0]
0x1801a8eba  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8ebf  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8ec6  lea     rax, [rsp+170h+var_100]
0x1801a8ecb  mov     r8d, ebx
0x1801a8ece  mov     dl, 1
0x1801a8ed0  mov     [rsp+170h+var_150], rax; int
0x1801a8ed5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8eda  mov     rcx, [rbp+78h]; this
0x1801a8ede  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8ee5  mov     r9d, edi; char *
0x1801a8ee8  mov     edx, 268h; void *
0x1801a8eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8ef2  mov     rax, [rbp+70h+var_78]
0x1801a8ef6  test    rax, rax
0x1801a8ef9  jz      loc_1801A9CA4
0x1801a8eff  xor     ebx, ebx
0x1801a8f01  lea     esi, [rbx+8]
0x1801a8f04  cmp     rbx, rax
0x1801a8f07  jb      short loc_1801A8F0D
0x1801a8f09  mov     ecx, esi
0x1801a8f0b  int     29h; Win8: RtlFailFast(ecx)
0x1801a8f0d  mov     rax, [rbp+70h+var_68]
0x1801a8f11  mov     rcx, [rax+rbx*8]
0x1801a8f15  mov     rcx, [rcx+8]
0x1801a8f19  mov     rax, [rcx]
0x1801a8f1c  mov     rax, [rax+10h]
0x1801a8f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f25  mov     rax, [rbp+70h+var_78]
0x1801a8f29  inc     rbx
0x1801a8f2c  cmp     rbx, rax
0x1801a8f2f  jb      short loc_1801A8F0D
0x1801a8f31  jmp     loc_1801A9CA4
0x1801a8f36  lea     r8, [rbp+70h+var_AC]; int *
0x1801a8f3a  mov     rdx, rbx; struct CCbsSession *
0x1801a8f3d  mov     rcx, r13; this
0x1801a8f40  call    ?IsDelegated@CCbsPackage@@AEBAJPEAVCCbsSession@@PEAH@Z; CCbsPackage::IsDelegated(CCbsSession *,int *)
0x1801a8f45  mov     edi, eax
0x1801a8f47  test    eax, eax
0x1801a8f49  jns     loc_1801A8FFB
0x1801a8f4f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8f56  mov     [rbp+70h+var_B0], eax
0x1801a8f59  test    rcx, rcx
0x1801a8f5c  jz      short loc_1801A8F9F
0x1801a8f5e  mov     ebx, 3
0x1801a8f63  lea     r9, aFailedToGetDel; "Failed to get delegate state."
0x1801a8f6a  mov     r8d, ebx
0x1801a8f6d  xor     edx, edx
0x1801a8f6f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8f74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8f7b  lea     rax, [rbp+70h+var_B0]
0x1801a8f7f  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8f84  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8f8b  lea     rax, [rsp+170h+var_100]
0x1801a8f90  mov     r8d, ebx
0x1801a8f93  mov     dl, 1
0x1801a8f95  mov     [rsp+170h+var_150], rax; int
0x1801a8f9a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8f9f  mov     rcx, [rbp+78h]; this
0x1801a8fa3  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8faa  mov     r9d, edi; char *
0x1801a8fad  mov     edx, 26Fh; void *
0x1801a8fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8fb7  mov     rax, [rbp+70h+var_78]
0x1801a8fbb  test    rax, rax
0x1801a8fbe  jz      loc_1801A9CA4
0x1801a8fc4  xor     ebx, ebx
0x1801a8fc6  lea     esi, [rbx+8]
0x1801a8fc9  cmp     rbx, rax
0x1801a8fcc  jb      short loc_1801A8FD2
0x1801a8fce  mov     ecx, esi
0x1801a8fd0  int     29h; Win8: RtlFailFast(ecx)
0x1801a8fd2  mov     rax, [rbp+70h+var_68]
0x1801a8fd6  mov     rcx, [rax+rbx*8]
0x1801a8fda  mov     rcx, [rcx+8]
0x1801a8fde  mov     rax, [rcx]
0x1801a8fe1  mov     rax, [rax+10h]
0x1801a8fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8fea  mov     rax, [rbp+70h+var_78]
0x1801a8fee  inc     rbx
0x1801a8ff1  cmp     rbx, rax
0x1801a8ff4  jb      short loc_1801A8FD2
0x1801a8ff6  jmp     loc_1801A9CA4
0x1801a8ffb  cmp     [rbp+70h+var_AC], 0
0x1801a8fff  mov     esi, 8
0x1801a9004  jz      short loc_1801A9013
0x1801a9006  cmp     [rbp+70h+arg_28], 0
0x1801a900d  jz      loc_1801A9C69
0x1801a9013  mov     r15, [r13+2F0h]
0x1801a901a  mov     rax, [r13+2E0h]
0x1801a9021  lea     r12, [r15+rax*8]
0x1801a9025  cmp     r15, r12
0x1801a9028  jz      loc_1801A90D0
  ... truncated ...
```
