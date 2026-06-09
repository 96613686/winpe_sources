# CCbsPackage::EnumerateUpdates(CCbsSession *,_CbsApplicability,_CbsSelectability,IEnumCbsUpdate * *)

- ea: `0x1801a6c00`
- end: `0x1801a7b1e`
- name: `?EnumerateUpdates@CCbsPackage@@QEAAJPEAVCCbsSession@@W4_CbsApplicability@@W4_CbsSelectability@@PEAPEAUIEnumCbsUpdate@@@Z`
- size: `3870`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b9a14`
- `0x1801bab24`

## callees

- `0x18000d910`
- `0x180010cc0`
- `0x180013250`
- `0x180023f30`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002b118`
- `0x18002c34c`
- `0x180066c28`
- `0x180068404`
- `0x180093c4c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a2d68`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800ed7d4`
- `0x1800eeafc`
- `0x18013c7f0`
- `0x1801a5494`
- `0x1801a63dc`
- `0x1801a6854`
- `0x1801a688c`
- `0x1801a6c00`
- `0x1801a8b68`
- `0x1801aa788`
- `0x1801aa82c`
- `0x1801aaab4`
- `0x1801b54c0`
- `0x1801b5b5c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a76d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a76fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a78c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a78dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7a0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a76d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a76fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a78c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a78dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a7a0c`

## string_xrefs

- `0x1801a6fcc`: `Enumeration failed due to CBS package store corruption, hence falling back to DeviceInventory.xml for update enumeration`
- `0x1801a7202`: `Failed to enumerate using sessions.xml`
- `0x1801a6ddd`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a6e76`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a6ec0`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a6f6d`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a703e`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a7246`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a7393`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a73e6`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a7483`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a752c`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a7810`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a78a3`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a78f9`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a79ef`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a6c85`: `No update list result specified`
- `0x1801a6d99`: `Cannot enumerate updates in a dead package.`
- `0x1801a6d03`: `Invalid update enumeration request from package read only session: {}, client: {}`
- `0x1801a74ee`: `Enumeration failed due to CBS package store corruption, hence falling back to Sessions.xml for update enumeration`
- `0x1801a7354`: `Failed to enumerate all updates.`
- `0x1801a77cc`: `Failed to enumerate all updates.`
- `0x1801a785f`: `Failed getting update CbsUpdatePropertyName property`
- `0x1801a79ab`: `Failed getting update CbsUpdatePropertyName property`

## pseudocode

```c
__int64 __fastcall CCbsPackage::EnumerateUpdates(__int64 a1, struct CCbsSession *a2, int a3, int a4, _QWORD *a5)
{
  __int64 v8; // r10
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int IsFullyInitialized; // eax
  _QWORD *v13; // rax
  __int64 v14; // rcx
  void (*v15)(void); // rax
  char *v16; // r15
  unsigned int v17; // r14d
  char *v18; // rcx
  char *v19; // rbx
  int v20; // r14d
  char *v21; // rcx
  __int64 v22; // rcx
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rax
  unsigned int v26; // eax
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // rcx
  char *v29; // rcx
  char *v30; // rcx
  _QWORD *v31; // r13
  char *v32; // rcx
  char *v33; // rcx
  char *v34; // rax
  unsigned __int64 v35; // r13
  struct CCbsSession *v36; // rsi
  __int64 v37; // rcx
  _QWORD *v38; // rdi
  __int64 v39; // rcx
  char *v40; // rcx
  _QWORD *v41; // rbx
  int v42; // eax
  unsigned __int64 v43; // rsi
  int v44; // r15d
  __int64 v45; // r15
  __int64 (__fastcall *v46)(__int64, __int64, __int64); // rsi
  __int64 InitPointer; // rax
  unsigned __int64 v48; // rdx
  bool v49; // zf
  __int64 v50; // r15
  __int64 (__fastcall *v51)(__int64, __int64, __int64); // rsi
  __int64 v52; // rax
  unsigned __int64 v53; // rsi
  int v54; // eax
  unsigned __int64 v55; // rdx
  __int64 v56; // rcx
  char *v57; // rcx
  char *v58; // rcx
  char *v59; // rcx
  char *v60; // rcx
  unsigned __int64 v61; // rcx
  char *v62; // rcx
  char *v63; // rcx
  int v64; // [rsp+20h] [rbp-E0h]
  int v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  int v69[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  int v71; // [rsp+80h] [rbp-80h]
  _QWORD *v72; // [rsp+88h] [rbp-78h]
  _BYTE v73[24]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v74; // [rsp+A8h] [rbp-58h] BYREF
  char v75; // [rsp+B0h] [rbp-50h]
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  struct CCbsSession *v77[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v78[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v79[56]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v80; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)v69 = a1;
  v72 = a5;
  v70 = 0;
  pv = 0;
  v71 = a4;
  LODWORD(v74) = a3;
  v77[0] = a2;
  CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v78);
  if ( !v8 )
  {
    v9 = -2147467261;
    LODWORD(v74) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update list result specified");
      *(_QWORD *)v69 = &v74;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v69);
    }
    v10 = 36;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)v9,
      v64);
LABEL_18:
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
    return v9;
  }
  if ( *(_DWORD *)(*((_QWORD *)a2 + 85) + 52LL) == 1 )
  {
    v9 = -2146498557;
    LODWORD(v74) = -2146498557;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v69 = *((_QWORD *)a2 + 81);
      v70 = *((_QWORD *)a2 + 80);
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Invalid update enumeration request from package read only session: {}, client: {}",
        (__int64)&v70,
        (__int64)v69);
      pv = &v74;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&pv);
    }
    v10 = 47;
    goto LABEL_17;
  }
  CritSecLocker::CritSecLocker((CritSecLocker *)v73, (struct AutoCritSec *)(a1 + 1064), 1);
  if ( *(_DWORD *)(a1 + 88) )
  {
    v9 = -2146498537;
    LODWORD(v74) = -2146498537;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot enumerate updates in a dead package.");
      *(_QWORD *)v69 = &v74;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v69);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x800F0817LL,
      v64);
    CritSecLocker::~CritSecLocker((CritSecLocker *)v73);
    goto LABEL_18;
  }
  CritSecLocker::~CritSecLocker((CritSecLocker *)v73);
  IsFullyInitialized = CCbsPackage::MakeSurePackageIsFullyInitialized((CCbsPackage *)a1, a2);
  v9 = IsFullyInitialized;
  if ( IsFullyInitialized < 0 )
  {
    LODWORD(v74) = IsFullyInitialized;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Delay Initialization Failed");
      *(_QWORD *)v69 = &v74;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v69);
    }
    v10 = 59;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl'::`2'::impl) )
  {
    if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&v70) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)0x8007000ELL,
        v64);
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
      v13 = (_QWORD *)v70;
LABEL_22:
      if ( v13 )
      {
        v14 = (__int64)v13 + *(int *)(v13[1] + 4LL) + 8;
LABEL_24:
        v15 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
LABEL_88:
        v15();
        return 2147942414LL;
      }
      return 2147942414LL;
    }
    v35 = v70;
    v36 = v77[0];
    if ( (int)CCbsPackage::InternalEnumerateUpdate(a1, v77[0], (unsigned int)v78, a3, v71, 0, 0, 1, v70, 0, 0, 0, 0) < 0 )
    {
      CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v79);
      v70 = 0;
      if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&v70) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)0x8007000ELL,
          v67);
        if ( v70 )
        {
          v37 = v70 + 8 + *(int *)(*(_QWORD *)(v70 + 8) + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v79);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        if ( !v35 )
          return 2147942414LL;
        v14 = v35 + *(int *)(*(_QWORD *)(v35 + 8) + 4LL) + 8LL;
        goto LABEL_24;
      }
      LogAdapter::TraceAtLevel<>(
        1,
        "Enumeration failed due to CBS package store corruption, hence falling back to Sessions.xml for update enumeration");
      v38 = (_QWORD *)v70;
      CCbsSession::ProcessSessionsXML(v36);
      v70 = 0;
      if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&v70) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)0x8007000ELL,
          v67);
        if ( v70 )
        {
          v39 = v70 + 8 + *(int *)(*(_QWORD *)(v70 + 8) + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
        if ( v38 )
        {
          v40 = (char *)v38 + *(int *)(v38[1] + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))(v40);
        }
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v79);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        if ( !v35 )
          return 2147942414LL;
        v15 = *(void (**)(void))(*(_QWORD *)(v35 + *(int *)(*(_QWORD *)(v35 + 8) + 4LL) + 8LL) + 16LL);
        goto LABEL_88;
      }
      v41 = (_QWORD *)v70;
      v42 = CCbsPackage::InternalEnumerateUpdate(
              v69[0],
              (_DWORD)v36,
              (unsigned int)v79,
              a3,
              v71,
              0,
              0,
              1,
              v70,
              1,
              0,
              0,
              0);
      v43 = 0;
      v44 = v42;
      v70 = 0;
      if ( v38[6] )
      {
        while ( 1 )
        {
          v77[0] = 0;
          if ( v43 >= v38[6] )
            __fastfail(8u);
          v45 = *(_QWORD *)(v38[8] + 8 * v43);
          v46 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v45 + 24LL);
          InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v77);
          v44 = v46(v45, 1, InitPointer);
          if ( v44 < 0 )
            break;
          v48 = 0;
          v74 = 0;
          v49 = v41[6] == 0;
          if ( v41[6] )
          {
            while ( 1 )
            {
              pv = 0;
              if ( v48 >= v41[6] )
                __fastfail(8u);
              v50 = *(_QWORD *)(v41[8] + 8 * v48);
              v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v50 + 24LL);
              v52 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
              v44 = v51(v50, 1, v52);
              if ( v44 < 0 )
                break;
              if ( (unsigned __int8)StringsAreEqual(v77[0], pv, 1) )
              {
                if ( pv )
                  CoTaskMemFree(pv);
                v48 = v74;
LABEL_106:
                v49 = v48 == v41[6];
                goto LABEL_107;
              }
              if ( pv )
                CoTaskMemFree(pv);
              v48 = v74 + 1;
              v74 = v48;
              if ( v48 >= v41[6] )
                goto LABEL_106;
            }
            LODWORD(v74) = v44;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting update CbsUpdatePropertyName property");
              *(_QWORD *)v69 = &v74;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v69);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
              (const char *)(unsigned int)v44,
              v68);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v77[0] )
            {
              CoTaskMemFree(v77[0]);
              v77[0] = 0;
            }
            goto LABEL_137;
          }
LABEL_107:
          v53 = v70;
          if ( v49 )
          {
            if ( v70 >= v38[6] )
              __fastfail(8u);
            v54 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(
                    v41,
                    *(_QWORD *)(v38[8] + 8 * v70));
            LODWORD(v74) = v54;
            if ( v54 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC3,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
                (const char *)(unsigned int)v54,
                v68);
              if ( v77[0] )
              {
                CoTaskMemFree(v77[0]);
                v77[0] = 0;
              }
              v59 = (char *)v41 + *(int *)(v41[1] + 4LL) + 8;
              (*(void (__fastcall **)(char *))(*(_QWORD *)v59 + 16LL))(v59);
              v60 = (char *)v38 + *(int *)(v38[1] + 4LL) + 8;
              (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
              CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v79);
              CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
              if ( v35 )
              {
                v61 = v35 + *(int *)(*(_QWORD *)(v35 + 8) + 4LL) + 8LL;
                (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v61 + 16LL))(v61);
              }
              return (unsigned int)v74;
            }
          }
          if ( v77[0] )
            CoTaskMemFree(v77[0]);
          v43 = v53 + 1;
          v70 = v43;
          if ( v43 >= v38[6] )
            goto LABEL_114;
        }
        LODWORD(v74) = v44;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting update CbsUpdatePropertyName property");
          *(_QWORD *)v69 = &v74;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v69);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v44,
          v68);
        if ( v77[0] )
        {
          CoTaskMemFree(v77[0]);
          v77[0] = 0;
        }
        if ( v41 )
        {
LABEL_137:
          v62 = (char *)v41 + *(int *)(v41[1] + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v62 + 16LL))(v62);
        }
        v63 = (char *)v38 + *(int *)(v38[1] + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v63 + 16LL))(v63);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v79);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        if ( !v35 )
          return (unsigned int)v44;
        v58 = (char *)(v35 + *(int *)(*(_QWORD *)(v35 + 8) + 4LL) + 8LL);
        goto LABEL_140;
      }
LABEL_114:
      v55 = v35;
      v35 = (unsigned __int64)v41;
      if ( v55 )
      {
        v56 = v55 + 8 + *(int *)(*(_QWORD *)(v55 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = (char *)v38 + *(int *)(v38[1] + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v57 + 16LL))(v57);
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v79);
      if ( v44 < 0 )
      {
        LODWORD(v74) = v44;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate all updates.");
          *(_QWORD *)v69 = &v74;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v69);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v44,
          v68);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        if ( !v41 )
          return (unsigned int)v44;
        v58 = (char *)v41 + *(int *)(v41[1] + 4LL) + 8;
LABEL_140:
        (*(void (__fastcall **)(char *))(*(_QWORD *)v58 + 16LL))(v58);
        return (unsigned int)v44;
      }
    }
    if ( v35 )
    {
      v34 = (char *)(v35 + *(int *)(*(_QWORD *)(v35 + 8) + 4LL) + 8LL);
      goto LABEL_144;
    }
    goto LABEL_71;
  }
  if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&pv) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x8007000ELL,
      v64);
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
    v13 = pv;
    goto LABEL_22;
  }
  v16 = (char *)pv;
  v17 = v74;
  if ( (int)CCbsPackage::InternalEnumerateUpdate(
              a1,
              (_DWORD)a2,
              (unsigned int)v78,
              v74,
              v71,
              0,
              0,
              1,
              (__int64)pv,
              0,
              0,
              0,
              0) >= 0 )
    goto LABEL_70;
  pv = 0;
  if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&pv) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x8007000ELL,
      v65);
    if ( !pv )
      goto LABEL_30;
    v18 = (char *)pv + *(int *)(*((_QWORD *)pv + 1) + 4LL) + 8;
    goto LABEL_29;
  }
  v75 = 0;
  LogAdapter::TraceAtLevel<>(
    1,
    "Enumeration failed due to CBS package store corruption, hence falling back to DeviceInventory.xml for update enumeration");
  v19 = (char *)pv;
  v66 = (int)pv;
  v20 = CCbsPackage::InternalEnumerateUpdatesUsingDeviceInventory(a1, a2, v17, (unsigned int)v71);
  if ( v20 >= 0 )
  {
    v21 = v16;
    v16 = v19;
    v19 = v21;
  }
  if ( !v75 )
  {
LABEL_64:
    if ( v19 )
    {
      v33 = &v19[*(int *)(*((_QWORD *)v19 + 1) + 4LL) + 8];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    if ( v20 < 0 )
    {
      LODWORD(v74) = v20;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate all updates.");
        *(_QWORD *)v69 = &v74;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v69);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)(unsigned int)v20,
        v66);
      goto LABEL_58;
    }
LABEL_70:
    if ( v16 )
    {
      v34 = &v16[*(int *)(*((_QWORD *)v16 + 1) + 4LL) + 8];
      goto LABEL_144;
    }
LABEL_71:
    v34 = 0;
LABEL_144:
    *v72 = v34;
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
    return 0;
  }
  pv = 0;
  LODWORD(v77[0]) = 0;
  v70 = 0;
  if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>((__int64)&v70) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x8007000ELL,
      v66);
    if ( v70 )
    {
      v22 = v70 + 8 + *(int *)(*(_QWORD *)(v70 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&pv);
    if ( !v19 )
    {
LABEL_30:
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
      if ( v16 )
      {
        v14 = (__int64)&v16[*(int *)(*((_QWORD *)v16 + 1) + 4LL) + 8];
        goto LABEL_24;
      }
      return 2147942414LL;
    }
    v18 = &v19[*(int *)(*((_QWORD *)v19 + 1) + 4LL) + 8];
LABEL_29:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
    goto LABEL_30;
  }
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>>(v79);
  v23 = v70;
  v20 = CCbsPackage::EnumerateUpdatesUsingSessionsXML(
          *(_QWORD *)v69,
          a2,
          (unsigned int)v74,
          (unsigned int)v71,
          v70,
          &pv,
          v77);
  if ( v20 >= 0 )
  {
    v24 = v80;
    *(_QWORD *)v69 = v80;
    v70 = v80;
    if ( v80 )
      _InterlockedAdd((volatile signed __int32 *)(v80 + 280), 1u);
    tip2::details::shared_data<1,0,0>::begin_update(v24 + 8);
    *(_BYTE *)(*(_QWORD *)v69 + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>::~test_data_control<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>(&v70);
  }
  v25 = v80;
  *(_QWORD *)v69 = v80;
  v70 = v80;
  if ( v80 )
    _InterlockedAdd((volatile signed __int32 *)(v80 + 280), 1u);
  tip2::details::shared_data<1,0,0>::begin_update(v25 + 8);
  *(_DWORD *)(*(_QWORD *)v69 + 276LL) = v20;
  tip2::test_data_control<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>::~test_data_control<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>(&v70);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::GetImpl'::`2'::impl) )
  {
    v26 = CbsReportSessionsXMLUsageTelemetry(a2, v20, (int)v77[0], (wchar_t *)pv, v20 == 0);
    LogAdapter::TraceAtLevelIfFailed<long,>(
      1,
      v26,
      "Failure in sending telemetry data for FOD/LP Enumeration Hardening.");
  }
  else
  {
    CbsReportSessionsXMLUsageTelemetry(a2, v20, (int)v77[0], (wchar_t *)pv, v20 == 0);
  }
  v27 = v80;
  wil::EnterCriticalSection(v69, v80 + 200);
  *(_DWORD *)(v27 + 72) |= 0x300u;
  if ( *(_QWORD *)(v27 + 248) )
    tip2::details::shared_data<1,0,0>::complete_helper(v27 + 8, 2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v69);
  if ( v20 >= 0 )
  {
    v31 = v16;
    v16 = (char *)v23;
    tip2::test_watcher<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>::~test_watcher<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>(v79);
    if ( v31 )
    {
      v32 = (char *)v31 + *(int *)(v31[1] + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&pv);
    goto LABEL_64;
  }
  LODWORD(v74) = v20;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate using sessions.xml");
    *(_QWORD *)v69 = &v74;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v69);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x84,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
    (const char *)(unsigned int)v20,
    v66);
  tip2::test_watcher<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>::~test_watcher<tip2::details::merged_data<_tip_SessionsXMLUsageForOcEnum,_tip_SessionsXMLUsageForOcEnum>>(v79);
  if ( v23 )
  {
    v28 = v23 + *(int *)(*(_QWORD *)(v23 + 8) + 4LL) + 8LL;
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&pv);
  if ( v19 )
  {
    v29 = &v19[*(int *)(*((_QWORD *)v19 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
  }
LABEL_58:
  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
  if ( v16 )
  {
    v30 = &v16[*(int *)(*((_QWORD *)v16 + 1) + 4LL) + 8];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1801a6c00  push    rbp
0x1801a6c02  push    rbx
0x1801a6c03  push    rsi
0x1801a6c04  push    rdi
0x1801a6c05  push    r12
0x1801a6c07  push    r13
0x1801a6c09  push    r14
0x1801a6c0b  push    r15
0x1801a6c0d  lea     rbp, [rsp-68h]
0x1801a6c12  sub     rsp, 168h
0x1801a6c19  mov     rax, cs:__security_cookie
0x1801a6c20  xor     rax, rsp
0x1801a6c23  mov     [rbp+0A0h+var_50], rax
0x1801a6c27  mov     r10, [rbp+0A0h+arg_20]
0x1801a6c2e  mov     rdi, rcx
0x1801a6c31  mov     qword ptr [rsp+1A0h+var_130], rcx
0x1801a6c36  xor     esi, esi
0x1801a6c38  xor     r14d, r14d
0x1801a6c3b  mov     [rbp+0A0h+var_118], r10
0x1801a6c3f  lea     rcx, [rbp+0A0h+var_D0]
0x1801a6c43  mov     [rsp+1A0h+var_128], rsi
0x1801a6c48  mov     [rbp+0A0h+pv], r14
0x1801a6c4c  mov     r15d, r8d
0x1801a6c4f  mov     [rbp+0A0h+var_120], r9d
0x1801a6c53  mov     r13, rdx
0x1801a6c56  mov     dword ptr [rbp+0A0h+var_F8], r8d
0x1801a6c5a  mov     [rbp+0A0h+var_E0], rdx
0x1801a6c5e  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801a6c63  test    r10, r10
0x1801a6c66  jnz     short loc_1801A6CC7
0x1801a6c68  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6c6f  mov     ebx, 80004003h
0x1801a6c74  mov     dword ptr [rbp+0A0h+var_F8], ebx
0x1801a6c77  test    rcx, rcx
0x1801a6c7a  jz      short loc_1801A6CBD
0x1801a6c7c  lea     esi, [r10+3]
0x1801a6c80  xor     edx, edx
0x1801a6c82  mov     r8d, esi
0x1801a6c85  lea     r9, aNoUpdateListRe; "No update list result specified"
0x1801a6c8c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a6c91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6c98  lea     rax, [rbp+0A0h+var_F8]
0x1801a6c9c  mov     qword ptr [rsp+1A0h+var_130], rax
0x1801a6ca1  lea     r9, asc_1802EE7AC; ": {}"
0x1801a6ca8  lea     rax, [rsp+1A0h+var_130]
0x1801a6cad  mov     r8d, esi
0x1801a6cb0  lea     edx, [rsi-2]
0x1801a6cb3  mov     qword ptr [rsp+1A0h+var_180], rax
0x1801a6cb8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a6cbd  mov     edx, 24h ; '$'
0x1801a6cc2  jmp     loc_1801A6E6F
0x1801a6cc7  mov     rax, [r13+2A8h]
0x1801a6cce  mov     r12d, 1
0x1801a6cd4  cmp     [rax+34h], r12d
0x1801a6cd8  jnz     loc_1801A6D68
0x1801a6cde  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6ce5  mov     ebx, 800F0803h
0x1801a6cea  mov     dword ptr [rbp+0A0h+var_F8], ebx
0x1801a6ced  test    rcx, rcx
0x1801a6cf0  jz      short loc_1801A6D5E
0x1801a6cf2  mov     rax, [r13+288h]
0x1801a6cf9  lea     esi, [r12+2]
0x1801a6cfe  mov     qword ptr [rsp+1A0h+var_130], rax
0x1801a6d03  lea     r9, aInvalidUpdateE; "Invalid update enumeration request from"...
0x1801a6d0a  mov     rax, [r13+280h]
0x1801a6d11  mov     r8d, esi
0x1801a6d14  mov     [rsp+1A0h+var_128], rax
0x1801a6d19  xor     edx, edx
0x1801a6d1b  lea     rax, [rsp+1A0h+var_130]
0x1801a6d20  mov     [rsp+1A0h+var_178], rax
0x1801a6d25  lea     rax, [rsp+1A0h+var_128]
0x1801a6d2a  mov     qword ptr [rsp+1A0h+var_180], rax
0x1801a6d2f  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801a6d34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6d3b  lea     rax, [rbp+0A0h+var_F8]
0x1801a6d3f  mov     [rbp+0A0h+pv], rax
0x1801a6d43  lea     r9, asc_1802EE7AC; ": {}"
0x1801a6d4a  lea     rax, [rbp+0A0h+pv]
0x1801a6d4e  mov     r8d, esi
0x1801a6d51  mov     dl, r12b
0x1801a6d54  mov     qword ptr [rsp+1A0h+var_180], rax
0x1801a6d59  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a6d5e  mov     edx, 2Fh ; '/'
0x1801a6d63  jmp     loc_1801A6E6F
0x1801a6d68  lea     rdx, [rdi+428h]; struct AutoCritSec *
0x1801a6d6f  mov     r8b, r12b; bool
0x1801a6d72  lea     rcx, [rbp+0A0h+var_110]; this
0x1801a6d76  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801a6d7b  cmp     [rdi+58h], esi
0x1801a6d7e  jz      short loc_1801A6DFF
0x1801a6d80  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6d87  mov     ebx, 800F0817h
0x1801a6d8c  mov     dword ptr [rbp+0A0h+var_F8], ebx
0x1801a6d8f  test    rcx, rcx
0x1801a6d92  jz      short loc_1801A6DD6
0x1801a6d94  mov     esi, 3
0x1801a6d99  lea     r9, aCannotEnumerat; "Cannot enumerate updates in a dead pack"...
0x1801a6da0  mov     r8d, esi
0x1801a6da3  xor     edx, edx
0x1801a6da5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a6daa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6db1  lea     rax, [rbp+0A0h+var_F8]
0x1801a6db5  mov     qword ptr [rsp+1A0h+var_130], rax
0x1801a6dba  lea     r9, asc_1802EE7AC; ": {}"
0x1801a6dc1  lea     rax, [rsp+1A0h+var_130]
0x1801a6dc6  mov     r8d, esi
0x1801a6dc9  mov     dl, r12b
0x1801a6dcc  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x1801a6dd1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a6dd6  mov     rcx, [rbp+0A8h]; this
0x1801a6ddd  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a6de4  mov     r9d, ebx; char *
0x1801a6de7  mov     edx, 37h ; '7'; void *
0x1801a6dec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6df1  lea     rcx, [rbp+0A0h+var_110]; this
0x1801a6df5  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801a6dfa  jmp     loc_1801A6E85
0x1801a6dff  lea     rcx, [rbp+0A0h+var_110]; this
0x1801a6e03  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801a6e08  mov     rdx, r13; struct CCbsSession *
0x1801a6e0b  mov     rcx, rdi; this
0x1801a6e0e  call    ?MakeSurePackageIsFullyInitialized@CCbsPackage@@QEAAJPEAVCCbsSession@@@Z; CCbsPackage::MakeSurePackageIsFullyInitialized(CCbsSession *)
0x1801a6e13  mov     ebx, eax
0x1801a6e15  test    eax, eax
0x1801a6e17  jns     short loc_1801A6E95
0x1801a6e19  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6e20  mov     dword ptr [rbp+0A0h+var_F8], eax
0x1801a6e23  test    rcx, rcx
0x1801a6e26  jz      short loc_1801A6E6A
0x1801a6e28  mov     esi, 3
0x1801a6e2d  lea     r9, aDelayInitializ; "Delay Initialization Failed"
0x1801a6e34  mov     r8d, esi
0x1801a6e37  xor     edx, edx
0x1801a6e39  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a6e3e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a6e45  lea     rax, [rbp+0A0h+var_F8]
0x1801a6e49  mov     qword ptr [rsp+1A0h+var_130], rax
0x1801a6e4e  lea     r9, asc_1802EE7AC; ": {}"
0x1801a6e55  lea     rax, [rsp+1A0h+var_130]
0x1801a6e5a  mov     r8d, esi
0x1801a6e5d  mov     dl, r12b
0x1801a6e60  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x1801a6e65  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a6e6a  mov     edx, 3Bh ; ';'; void *
0x1801a6e6f  mov     rcx, [rbp+0A8h]; this
0x1801a6e76  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a6e7d  mov     r9d, ebx; char *
0x1801a6e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6e85  lea     rcx, [rbp+0A0h+var_D0]
0x1801a6e89  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801a6e8e  mov     eax, ebx
0x1801a6e90  jmp     loc_1801A7AFD
0x1801a6e95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements> `wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl(void)'::`2'::impl
0x1801a6e9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(void)
0x1801a6ea1  xor     ebx, ebx
0x1801a6ea3  test    al, al
0x1801a6ea5  jz      loc_1801A73D0
0x1801a6eab  lea     rcx, [rbp+0A0h+pv]
0x1801a6eaf  call    ??$AllocateWithNew@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@$$V@?$AutoComPtr@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Windows@@QEAAPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@XZ; Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>,>(void)
0x1801a6eb4  test    rax, rax
0x1801a6eb7  jnz     short loc_1801A6F06
0x1801a6eb9  mov     rcx, [rbp+0A8h]; this
0x1801a6ec0  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a6ec7  mov     r9d, 8007000Eh; char *
0x1801a6ecd  lea     edx, [rbx+3Fh]; void *
0x1801a6ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6ed5  lea     rcx, [rbp+0A0h+var_D0]
0x1801a6ed9  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801a6ede  mov     rax, [rbp+0A0h+pv]
0x1801a6ee2  test    rax, rax
0x1801a6ee5  jz      loc_1801A75BA
0x1801a6eeb  mov     rcx, [rax+8]
0x1801a6eef  add     rax, 8
0x1801a6ef3  movsxd  rcx, dword ptr [rcx+4]
0x1801a6ef7  add     rcx, rax
0x1801a6efa  mov     rax, [rcx]
0x1801a6efd  mov     rax, [rax+10h]
0x1801a6f01  jmp     loc_1801A75B5
0x1801a6f06  mov     eax, [rbp+0A0h+var_120]
0x1801a6f09  lea     r8, [rbp+0A0h+var_D0]
0x1801a6f0d  mov     r15, [rbp+0A0h+pv]
0x1801a6f11  mov     rdx, r13
0x1801a6f14  mov     r14d, dword ptr [rbp+0A0h+var_F8]
0x1801a6f18  mov     rcx, rdi
0x1801a6f1b  mov     [rsp+1A0h+var_140], rbx
0x1801a6f20  mov     r9d, r14d
0x1801a6f23  mov     [rsp+1A0h+var_148], rbx
0x1801a6f28  mov     [rsp+1A0h+var_150], ebx
0x1801a6f2c  mov     [rsp+1A0h+var_158], ebx
0x1801a6f30  mov     [rsp+1A0h+var_160], r15
0x1801a6f35  mov     [rsp+1A0h+var_168], r12d
0x1801a6f3a  mov     [rsp+1A0h+var_170], rbx
0x1801a6f3f  mov     dword ptr [rsp+1A0h+var_178], ebx
0x1801a6f43  mov     [rsp+1A0h+var_180], eax; int
0x1801a6f47  call    ?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z; CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)
0x1801a6f4c  test    eax, eax
0x1801a6f4e  jns     loc_1801A73AC
0x1801a6f54  lea     rcx, [rbp+0A0h+pv]
0x1801a6f58  mov     [rbp+0A0h+pv], rbx
0x1801a6f5c  call    ??$AllocateWithNew@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@$$V@?$AutoComPtr@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Windows@@QEAAPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@XZ; Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>,>(void)
0x1801a6f61  test    rax, rax
0x1801a6f64  jnz     short loc_1801A6FCC
0x1801a6f66  mov     rcx, [rbp+0A8h]; this
0x1801a6f6d  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a6f74  mov     r9d, 8007000Eh; char *
0x1801a6f7a  lea     edx, [rax+47h]; void *
0x1801a6f7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6f82  mov     rax, [rbp+0A0h+pv]
0x1801a6f86  test    rax, rax
0x1801a6f89  jz      short loc_1801A6FA6
0x1801a6f8b  mov     rcx, [rax+8]
0x1801a6f8f  add     rax, 8
0x1801a6f93  movsxd  rcx, dword ptr [rcx+4]
0x1801a6f97  add     rcx, rax
0x1801a6f9a  mov     rax, [rcx]
0x1801a6f9d  mov     rax, [rax+10h]
0x1801a6fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a6fa6  lea     rcx, [rbp+0A0h+var_D0]
0x1801a6faa  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801a6faf  test    r15, r15
0x1801a6fb2  jz      loc_1801A75BA
0x1801a6fb8  mov     rax, [r15+8]
0x1801a6fbc  movsxd  rcx, dword ptr [rax+4]
0x1801a6fc0  add     rcx, 8
0x1801a6fc4  add     rcx, r15
0x1801a6fc7  jmp     loc_1801A6EFA
0x1801a6fcc  lea     rdx, aEnumerationFai; "Enumeration failed due to CBS package s"...
0x1801a6fd3  mov     [rbp+0A0h+var_F0], bl
0x1801a6fd6  mov     ecx, r12d
0x1801a6fd9  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801a6fde  mov     rbx, [rbp+0A0h+pv]
0x1801a6fe2  lea     rax, [rbp+0A0h+var_F0]
0x1801a6fe6  mov     r9d, [rbp+0A0h+var_120]
0x1801a6fea  mov     r8d, r14d
0x1801a6fed  mov     [rsp+1A0h+var_178], rax
0x1801a6ff2  mov     rdx, r13
0x1801a6ff5  mov     rcx, rdi
0x1801a6ff8  mov     qword ptr [rsp+1A0h+var_180], rbx; int
0x1801a6ffd  call    ?InternalEnumerateUpdatesUsingDeviceInventory@CCbsPackage@@AEAAJPEAVCCbsSession@@W4_CbsApplicability@@W4_CbsSelectability@@PEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@PEA_N@Z; CCbsPackage::InternalEnumerateUpdatesUsingDeviceInventory(CCbsSession *,_CbsApplicability,_CbsSelectability,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,bool *)
0x1801a7002  mov     r14d, eax
0x1801a7005  test    eax, eax
0x1801a7007  js      short loc_1801A7012
0x1801a7009  mov     rcx, r15
0x1801a700c  mov     r15, rbx
0x1801a700f  mov     rbx, rcx
0x1801a7012  cmp     [rbp+0A0h+var_F0], sil
0x1801a7016  jz      loc_1801A7315
0x1801a701c  lea     rcx, [rsp+1A0h+var_128]
0x1801a7021  mov     [rbp+0A0h+pv], rsi
0x1801a7025  mov     dword ptr [rbp+0A0h+var_E0], esi
0x1801a7028  mov     [rsp+1A0h+var_128], rsi
0x1801a702d  call    ??$AllocateWithNew@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@$$V@?$AutoComPtr@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Windows@@QEAAPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@XZ; Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>,>(void)
0x1801a7032  test    rax, rax
0x1801a7035  jnz     short loc_1801A709E
0x1801a7037  mov     rcx, [rbp+0A8h]; this
0x1801a703e  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a7045  mov     r9d, 8007000Eh; char *
0x1801a704b  lea     edx, [rax+60h]; void *
0x1801a704e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a7053  mov     rax, [rsp+1A0h+var_128]
0x1801a7058  test    rax, rax
0x1801a705b  jz      short loc_1801A7078
0x1801a705d  mov     rcx, [rax+8]
0x1801a7061  add     rax, 8
0x1801a7065  movsxd  rcx, dword ptr [rcx+4]
0x1801a7069  add     rcx, rax
0x1801a706c  mov     rax, [rcx]
0x1801a706f  mov     rax, [rax+10h]
0x1801a7073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7078  lea     rcx, [rbp+0A0h+pv]
0x1801a707c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801a7081  test    rbx, rbx
0x1801a7084  jz      loc_1801A6FA6
0x1801a708a  mov     rax, [rbx+8]
0x1801a708e  movsxd  rcx, dword ptr [rax+4]
0x1801a7092  add     rcx, 8
0x1801a7096  add     rcx, rbx
0x1801a7099  jmp     loc_1801A6F9A
0x1801a709e  lea     rcx, [rbp+0A0h+var_90]
0x1801a70a2  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_SessionsXMLUsageForOcEnum@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1801a70a7  mov     rdi, [rsp+1A0h+var_128]
0x1801a70ac  lea     rax, [rbp+0A0h+var_E0]
0x1801a70b0  mov     r9d, [rbp+0A0h+var_120]
0x1801a70b4  mov     rdx, r13
0x1801a70b7  mov     r8d, dword ptr [rbp+0A0h+var_F8]
0x1801a70bb  mov     rcx, qword ptr [rsp+1A0h+var_130]
0x1801a70c0  mov     [rsp+1A0h+var_170], rax
0x1801a70c5  lea     rax, [rbp+0A0h+pv]
0x1801a70c9  mov     [rsp+1A0h+var_178], rax
0x1801a70ce  mov     qword ptr [rsp+1A0h+var_180], rdi
0x1801a70d3  call    ?EnumerateUpdatesUsingSessionsXML@CCbsPackage@@AEAAJPEAVCCbsSession@@W4_CbsApplicability@@W4_CbsSelectability@@PEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@PEAPEA_WPEAJ@Z; CCbsPackage::EnumerateUpdatesUsingSessionsXML(CCbsSession *,_CbsApplicability,_CbsSelectability,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,wchar_t * *,long *)
0x1801a70d8  mov     r14d, eax
0x1801a70db  test    eax, eax
0x1801a70dd  js      short loc_1801A7119
0x1801a70df  mov     rax, [rbp+0A0h+var_58]
0x1801a70e3  mov     qword ptr [rsp+1A0h+var_130], rax
0x1801a70e8  mov     [rsp+1A0h+var_128], rax
0x1801a70ed  test    rax, rax
0x1801a70f0  jz      short loc_1801A70FA
0x1801a70f2  lock add [rax+118h], r12d
  ... truncated ...
```
