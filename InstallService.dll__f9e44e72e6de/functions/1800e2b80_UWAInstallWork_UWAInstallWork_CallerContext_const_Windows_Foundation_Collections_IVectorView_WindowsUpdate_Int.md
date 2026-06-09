# UWAInstallWork::UWAInstallWork(CallerContext const &,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,WindowsUpdate::Internal::InstallType,ulong,WindowsUpdate::Internal::InstallWorkStatus const *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,HSTRING__ *,bool,int)

- ea: `0x1800e2b80`
- end: `0x1800e3e0e`
- name: `??0UWAInstallWork@@QEAA@AEBVCallerContext@@PEAU?$IVectorView@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@W4InstallType@Internal@WindowsUpdate@@KPEBUInstallWorkStatus@78@PEAUHSTRING__@@44PEAUIBuffer@Streams@Storage@5@4_NH@Z`
- size: `4750`
- prototype: ``
- caller_count: `1`
- callee_count: `57`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e15c`

## callees

- `0x180009ea0`
- `0x18000ad30`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c108`
- `0x18001c144`
- `0x18001c414`
- `0x18001c844`
- `0x18001c964`
- `0x18001cce0`
- `0x180020368`
- `0x1800213dc`
- `0x1800222d8`
- `0x180022374`
- `0x180028cd4`
- `0x18002c310`
- `0x18002ec2c`
- `0x18002ec4c`
- `0x18002f214`
- `0x180038580`
- `0x18003ecf8`
- `0x180042b9c`
- `0x180044bc0`
- `0x180044c3c`
- `0x180044fc4`
- `0x1800450f0`
- `0x180047a88`
- `0x180052268`
- `0x180059528`
- `0x18005bdd8`
- `0x180062e20`
- `0x1800636d8`
- `0x180064008`
- `0x18006687c`
- `0x18006c688`
- `0x180071dcc`
- `0x180073470`
- `0x180074d24`
- `0x180074de8`
- `0x180076e48`
- `0x180077fd8`
- `0x18007fcd0`
- `0x1800df960`
- `0x1800e071c`
- `0x1800e2900`
- `0x1800e2948`
- `0x1800e29d0`
- `0x1800e2b80`
- `0x1800e4c70`
- `0x1800e4e34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800e311b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800e311b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e2ecd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e302b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e3038`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e2ecd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e302b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800e3038`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800e3099`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800e3099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ade`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ade`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e3a77`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e3a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e32e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e352f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e32e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e352f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e338b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e33bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e35e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e373f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e37ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e37d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e38ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e393f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e394e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3c84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e338b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e33bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e35e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e373f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e37ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e37d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e38ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e393f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e394e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3c84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800e355d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800e355d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e37a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e3913`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e37a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e3913`

## string_xrefs

- `0x1800e3d75`: `onecore\internal\sdk\inc\wil\opensource/wil/wrl.h`
- `0x1800e350d`: `Update;`
- `0x1800e316f`: `UWAInstallWork::UWAInstallWork`
- `0x1800e33ea`: `UWAInstallWork::UWAInstallWork`
- `0x1800e3492`: `UWAInstallWork::UWAInstallWork`
- `0x1800e3763`: `UWAInstallWork::UWAInstallWork`
- `0x1800e38cf`: `UWAInstallWork::UWAInstallWork`
- `0x1800e3a43`: `UWAInstallWork::UWAInstallWork`
- `0x1800e3aac`: `UWAInstallWork::UWAInstallWork`
- `0x1800e3cbc`: `UWAInstallWork::UWAInstallWork`
- `0x1800e312e`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800e36d5`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800e39cb`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800e374f`: `Requested Offline WU scan. Attempting to get updatecollection`
- `0x1800e38bb`: `Requested Offline WU scan. Attempting to get updatecollection`
- `0x1800e3a3c`: `GetPackageFullNamesFromCollection(_updateCollection.get(), _pkgFullNames.GetAddressOf())`
- `0x1800e3aa5`: `GetUniqueIdFromCollection(_updateCollection.get(), &bstrUpdateId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=51
UWAInstallWork *__fastcall UWAInstallWork::UWAInstallWork(
        UWAInstallWork *this,
        __int64 a2,
        OLECHAR *a3,
        int a4,
        int a5,
        __int64 a6,
        HSTRING a7,
        HSTRING a8,
        HSTRING a9,
        void *a10,
        HSTRING a11,
        char a12,
        int a13)
{
  UWAInstallWork *v15; // r14
  unsigned int v16; // edi
  _QWORD *v17; // rbx
  struct IUpdateCollection **v18; // r12
  char *v19; // r13
  PCWSTR StringRawBuffer; // rax
  const char *v21; // r9
  TraceLoggingCorrelationVector *v22; // rcx
  int i; // eax
  const wchar_t *v24; // rbx
  int v25; // eax
  BSTR v26; // rdi
  __int64 (__fastcall *v27)(BSTR, char *); // rbx
  int v28; // eax
  BSTR *v29; // rdx
  __int64 v30; // rdi
  PCWSTR v31; // rax
  PCWSTR v32; // rbx
  const unsigned __int16 *v33; // rax
  const unsigned __int16 *v34; // rax
  const wchar_t *v35; // rax
  __int64 v36; // rax
  HRESULT v37; // eax
  int v38; // eax
  int v39; // eax
  int PdcActivation; // eax
  PCWSTR v41; // rax
  _QWORD *v42; // rax
  __int64 *v43; // r8
  __int64 v44; // rdx
  char v45; // bl
  __int64 v46; // rax
  __int64 v47; // rax
  const unsigned __int16 *v48; // rax
  HRESULT Instance; // eax
  void *UserHandleOrNullIfLocalSystem; // rax
  int updated; // eax
  __int64 v52; // rax
  const unsigned __int16 *v53; // rax
  HRESULT v54; // eax
  void *v55; // rax
  int v56; // eax
  int *v57; // rdi
  HSTRING *v58; // rbx
  int PackageFullNamesFromCollection; // eax
  BSTR *v60; // rbx
  int UniqueIdFromCollection; // eax
  _DWORD *v62; // r9
  _DWORD *v63; // r10
  _DWORD *v64; // r11
  _QWORD *v65; // r12
  _QWORD *v66; // rbx
  int v67; // edx
  int v68; // eax
  unsigned __int64 v69; // rax
  const unsigned __int16 *v70; // rax
  int v71; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-2F8h]
  LPVOID *ppva; // [rsp+20h] [rbp-2F8h]
  LPVOID *ppvb; // [rsp+20h] [rbp-2F8h]
  int ppvc; // [rsp+20h] [rbp-2F8h]
  int ppvd; // [rsp+20h] [rbp-2F8h]
  int ppve; // [rsp+20h] [rbp-2F8h]
  int v79; // [rsp+28h] [rbp-2F0h]
  int v80; // [rsp+28h] [rbp-2F0h]
  char *v81; // [rsp+30h] [rbp-2E8h]
  BSTR bstrString; // [rsp+70h] [rbp-2A8h] BYREF
  HSTRING v83; // [rsp+78h] [rbp-2A0h] BYREF
  int v84; // [rsp+80h] [rbp-298h] BYREF
  HSTRING *v85; // [rsp+88h] [rbp-290h]
  HSTRING string; // [rsp+90h] [rbp-288h] BYREF
  LPVOID v87; // [rsp+98h] [rbp-280h] BYREF
  int v88; // [rsp+A0h] [rbp-278h]
  int v89; // [rsp+A4h] [rbp-274h]
  UWAInstallWork *v90; // [rsp+A8h] [rbp-270h]
  struct IUpdateCollection **v91; // [rsp+B0h] [rbp-268h]
  char *v92; // [rsp+B8h] [rbp-260h]
  TraceLoggingCorrelationVector **v93; // [rsp+C0h] [rbp-258h]
  const wchar_t *v94; // [rsp+C8h] [rbp-250h] BYREF
  _DWORD *v95; // [rsp+D0h] [rbp-248h]
  int *v96; // [rsp+D8h] [rbp-240h]
  BSTR v97; // [rsp+E0h] [rbp-238h] BYREF
  int v98; // [rsp+E8h] [rbp-230h]
  __int64 v99; // [rsp+F0h] [rbp-228h] BYREF
  HSTRING string2; // [rsp+F8h] [rbp-220h]
  HSTRING v101; // [rsp+100h] [rbp-218h] BYREF
  int *v102; // [rsp+108h] [rbp-210h]
  HSTRING *v103; // [rsp+110h] [rbp-208h]
  BSTR *v104; // [rsp+118h] [rbp-200h]
  _DWORD *v105; // [rsp+120h] [rbp-1F8h]
  _DWORD *v106; // [rsp+128h] [rbp-1F0h]
  _DWORD *v107; // [rsp+130h] [rbp-1E8h]
  _QWORD *v108; // [rsp+138h] [rbp-1E0h]
  _QWORD *v109; // [rsp+140h] [rbp-1D8h]
  int *v110; // [rsp+148h] [rbp-1D0h]
  _QWORD *v111; // [rsp+150h] [rbp-1C8h]
  _DWORD *v112; // [rsp+158h] [rbp-1C0h]
  bool *v113; // [rsp+160h] [rbp-1B8h]
  const wchar_t *v114; // [rsp+168h] [rbp-1B0h] BYREF
  char v115[16]; // [rsp+170h] [rbp-1A8h] BYREF
  _BYTE v116[32]; // [rsp+180h] [rbp-198h] BYREF
  char v117[8]; // [rsp+1A0h] [rbp-178h] BYREF
  int v118; // [rsp+1A8h] [rbp-170h]
  char v119[16]; // [rsp+1B0h] [rbp-168h] BYREF
  char v120[16]; // [rsp+1C0h] [rbp-158h] BYREF
  __int128 v121; // [rsp+1D0h] [rbp-148h]
  __int128 v122; // [rsp+1E0h] [rbp-138h]
  __int128 v123; // [rsp+1F0h] [rbp-128h]
  __int128 v124; // [rsp+200h] [rbp-118h]
  __int128 v125; // [rsp+210h] [rbp-108h]
  __int128 v126; // [rsp+220h] [rbp-F8h]
  __int128 v127; // [rsp+230h] [rbp-E8h]
  char v128; // [rsp+240h] [rbp-D8h]
  char Str[144]; // [rsp+250h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v89 = a4;
  bstrString = a3;
  v15 = this;
  v90 = this;
  v83 = a7;
  v101 = a8;
  string2 = a9;
  v87 = a10;
  string = a11;
  v16 = 0;
  v84 = 0;
  v17 = (_QWORD *)((char *)this + 8);
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>((char *)this + 8);
  *((_QWORD *)v15 + 8) = 1;
  *(_QWORD *)v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `WindowsUpdate::Internal::IInstallWork'};
  *v17 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v15 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'};
  *((_QWORD *)v15 + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v15 = &UWAInstallWork::`vftable'{for `WindowsUpdate::Internal::IInstallWork'};
  *v17 = &UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v15 + 2) = &UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'};
  *((_QWORD *)v15 + 3) = &UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)v15 + 9) = 0;
  *((_QWORD *)v15 + 10) = 0;
  *((_QWORD *)v15 + 11) = 0;
  v103 = (HSTRING *)((char *)v15 + 96);
  *((_QWORD *)v15 + 12) = 0;
  v18 = (struct IUpdateCollection **)((char *)v15 + 104);
  v91 = (struct IUpdateCollection **)((char *)v15 + 104);
  *((_QWORD *)v15 + 13) = 0;
  *((_QWORD *)v15 + 14) = 0;
  *((_QWORD *)v15 + 15) = 0;
  *((_DWORD *)v15 + 32) = a4;
  *(_OWORD *)((char *)v15 + 132) = 0;
  CallerContext::copy(a2, (char *)v15 + 152);
  v93 = (TraceLoggingCorrelationVector **)((char *)v15 + 296);
  *((_QWORD *)v15 + 37) = 0;
  v19 = (char *)v15 + 304;
  v92 = (char *)v15 + 304;
  memset_0((char *)v15 + 304, 0, 0x81u);
  *((_QWORD *)v15 + 55) = 0;
  *((_QWORD *)v15 + 56) = 0;
  if ( qword_1802E6610 )
    _InterlockedIncrement((volatile signed __int32 *)qword_1802E6610 + 2);
  *((_QWORD *)v15 + 55) = InstallAgentPdcManager::_pdcManager;
  *((_QWORD *)v15 + 56) = qword_1802E6610;
  *((_QWORD *)v15 + 57) = 0;
  *((_QWORD *)v15 + 58) = 0;
  v85 = (HSTRING *)((char *)v15 + 472);
  *((_QWORD *)v15 + 59) = 0;
  *((_QWORD *)v15 + 60) = 0;
  *((_QWORD *)v15 + 61) = 0;
  v104 = (BSTR *)((char *)v15 + 496);
  *((_QWORD *)v15 + 62) = 0;
  *((_BYTE *)v15 + 504) = a12;
  *((_QWORD *)v15 + 64) = 0;
  *((_QWORD *)v15 + 65) = 0;
  *((_QWORD *)v15 + 66) = 0;
  *((_QWORD *)v15 + 67) = 0;
  *((_QWORD *)v15 + 68) = 0;
  *((_QWORD *)v15 + 69) = 0;
  *((_QWORD *)v15 + 70) = 0;
  *((_QWORD *)v15 + 71) = 0;
  *((_QWORD *)v15 + 72) = 0;
  *((_QWORD *)v15 + 73) = 0;
  *((_QWORD *)v15 + 74) = 0;
  *((_QWORD *)v15 + 75) = 0;
  *((_QWORD *)v15 + 76) = 0;
  std::set<std::wstring>::set<std::wstring>((char *)v15 + 616);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>((char *)v15 + 632);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>((char *)v15 + 696);
  std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>((char *)v15 + 760);
  std::wstring::wstring((char *)v15 + 824);
  std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>((char *)v15 + 856);
  *((_QWORD *)v15 + 115) = 0;
  *((_QWORD *)v15 + 116) = 0;
  *((_QWORD *)v15 + 117) = 0;
  *((_QWORD *)v15 + 118) = 0;
  std::wstring::wstring((char *)v15 + 952);
  *((_WORD *)v15 + 492) = 0;
  *((_BYTE *)v15 + 986) = 0;
  *((_DWORD *)v15 + 247) = 0;
  *((_DWORD *)v15 + 248) = -2147467259;
  *((_DWORD *)v15 + 249) = -2147467259;
  *((_QWORD *)v15 + 125) = 0;
  std::wstring::wstring((char *)v15 + 1008);
  *((_QWORD *)v15 + 130) = 0;
  InitializeSRWLock((PSRWLOCK)v15 + 131);
  v95 = (_DWORD *)((char *)v15 + 1056);
  *((_DWORD *)v15 + 264) = a5;
  v110 = (int *)((char *)v15 + 1060);
  *((_DWORD *)v15 + 265) = 0;
  *((_DWORD *)v15 + 266) = 0;
  v105 = (_DWORD *)((char *)v15 + 1068);
  *((_DWORD *)v15 + 267) = 0;
  *((_DWORD *)v15 + 268) = 0;
  v96 = (int *)((char *)v15 + 1076);
  *((_DWORD *)v15 + 269) = 0;
  v102 = (int *)((char *)v15 + 1080);
  *((_DWORD *)v15 + 270) = 0;
  *((_BYTE *)v15 + 1084) = 1;
  v106 = (_DWORD *)((char *)v15 + 1088);
  *((_DWORD *)v15 + 272) = 0;
  v107 = (_DWORD *)((char *)v15 + 1092);
  *((_DWORD *)v15 + 273) = 0;
  v108 = (_QWORD *)((char *)v15 + 1096);
  *((_QWORD *)v15 + 137) = 0;
  v111 = (_QWORD *)((char *)v15 + 1104);
  *((_QWORD *)v15 + 138) = 0;
  v109 = (_QWORD *)((char *)v15 + 1112);
  *((_QWORD *)v15 + 139) = 0;
  *((_BYTE *)v15 + 1120) = 0;
  *((_DWORD *)v15 + 281) = -2147483638;
  *((_BYTE *)v15 + 1128) = 0;
  v113 = (bool *)v15 + 1129;
  *((_BYTE *)v15 + 1129) = 0;
  v112 = (_DWORD *)((char *)v15 + 1132);
  *((_DWORD *)v15 + 283) = 0;
  *((_DWORD *)v15 + 284) = 0;
  *((_QWORD *)v15 + 143) = 0;
  *((_QWORD *)v15 + 144) = 0;
  *((_QWORD *)v15 + 145) = 0;
  *((_QWORD *)v15 + 146) = 0;
  *((_QWORD *)v15 + 147) = 0;
  *((_QWORD *)v15 + 148) = 0;
  *((_QWORD *)v15 + 149) = 0;
  *((_QWORD *)v15 + 150) = 0;
  *((_QWORD *)v15 + 151) = 0;
  *((_QWORD *)v15 + 152) = 0;
  InitializeSRWLock((PSRWLOCK)v15 + 153);
  InitializeSRWLock((PSRWLOCK)v15 + 154);
  OpaqueTokenEncoder::OpaqueTokenEncoder((UWAInstallWork *)((char *)v15 + 1240));
  *((_DWORD *)v15 + 318) = 0;
  *((_QWORD *)v15 + 160) = 0;
  *((_DWORD *)v15 + 322) = 0;
  *((_QWORD *)v15 + 162) = 0;
  *((_DWORD *)v15 + 326) = 0;
  *(_OWORD *)((char *)v15 + 1340) = 0;
  *(_OWORD *)((char *)v15 + 1356) = 0;
  *(_OWORD *)((char *)v15 + 1372) = 0;
  EventActivityIdControl(1u, (LPGUID)((char *)v15 + 132));
  if ( (*(_BYTE *)v95 & 0x10) == 0 && *((_DWORD *)v15 + 32) == 1 )
  {
    if ( (*v95 & 0x20000) == 0
      || (*(_BYTE *)v95 & 1) == 0
      && (v84 = 0,
          GetAutoUpdateState((enum WindowsUpdate::Internal::AutoUpdateState *)&v84),
          ((v84 - 1) & 0xFFFFFFFD) != 0) )
    {
      *((_DWORD *)v15 + 265) = 7;
    }
  }
  CallerContext::SetAutoReleaseOnLogoff((UWAInstallWork *)((char *)v15 + 152));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  _o_wcstombs(Str, StringRawBuffer, 129);
  if ( !TraceLoggingCorrelationVector::Validate(Str) )
  {
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x9Cu,
      "UWAInstallWork::UWAInstallWork",
      -1,
      L"Assert (%s): %s",
      0,
      0);
    __int2c();
  }
  string = (HSTRING)TraceLoggingCorrelationVector::Set(Str, 0);
  std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(
    v93,
    &string);
  std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(&string);
  v22 = *v93;
  if ( !*v93 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      v21);
  string = (HSTRING)((char *)v15 + 472);
  TraceLoggingCorrelationVector::ToStringImpl(
    v22,
    _InterlockedExchangeAdd64((volatile signed __int64 *)v22 + 17, 0),
    (char *)v15 + 304);
  *(_OWORD *)((char *)v15 + 1308) = 0;
  *(_OWORD *)((char *)v15 + 1324) = 0;
  v97 = bstrString;
  v98 = 0;
  v99 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
    &bstrString,
    v117);
  for ( i = v98; i != v118; i = ++v98 )
  {
    v24 = *(const wchar_t **)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v97);
    v94 = v24;
    if ( v24 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v24 + 8LL))(v24);
    v114 = v24;
    bstrString = 0;
    v84 = v16 | 2;
    v88 = v16 | 2;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
    v25 = Microsoft::WRL::Details::MakeAndInitialize<WindowsUpdate::Internal::FulfillmentDataInfo,WindowsUpdate::Internal::FulfillmentDataInfo,WindowsUpdate::Internal::IFulfillmentDataInfo *>(
            &bstrString,
            &v114);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/wrl.h",
        (const char *)(unsigned int)v25,
        ppvc);
    v26 = bstrString;
    v27 = *(__int64 (__fastcall **)(BSTR, char *))(*(_QWORD *)bstrString + 168LL);
    WindowsDeleteString(*((HSTRING *)v15 + 15));
    *((_QWORD *)v15 + 15) = 0;
    v28 = v27(v26, (char *)v15 + 120);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)0x803FB105LL,
      v28 < 0,
      (bool)"Cannot find a WUCategoryId",
      v81);
    v29 = (BSTR *)*((_QWORD *)v15 + 147);
    if ( v29 == *((BSTR **)v15 + 148) )
    {
      std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo> const &>(
        (char *)v15 + 1168,
        v29,
        &bstrString);
    }
    else
    {
      *v29 = bstrString;
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(v29);
      *((_QWORD *)v15 + 147) += 8LL;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
    {
      v30 = *((_QWORD *)bstrString + 29);
      v31 = WindowsGetStringRawBuffer(*((HSTRING *)bstrString + 30), 0);
      v32 = v31;
      if ( v31 && *v31 && v30 )
      {
        v33 = WindowsGetStringRawBuffer(*v85, 0);
        LogMessage(
          4u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0xB1u,
          "UWAInstallWork::UWAInstallWork",
          -1,
          L"Processing fulfillment data: PackageRank=%llu, PackageFullName=%s",
          (const char *)v15 + 304,
          v33);
        std::wstring::wstring(v116, v32);
        *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring,>(
                                 (char *)v15 + 760,
                                 v115,
                                 v116)
                  + 48LL) = v30;
        std::wstring::_Tidy_deallocate(v116);
      }
      else
      {
        v34 = WindowsGetStringRawBuffer(*v85, 0);
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0xB7u,
          "UWAInstallWork::UWAInstallWork",
          -1,
          L"Skipping fulfillment data map entry: PackageRank=%llu, PackageFullName=%s",
          (const char *)v15 + 304,
          v34);
      }
    }
    v16 = v88 & 0xFFFFFFFD;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v94);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v119);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v99);
  UWAInstallWork::_UpdateIntentStrings(v15);
  v35 = L"Update;";
  if ( v89 != 1 )
    v35 = L"Acquisition;";
  v94 = v35;
  WindowsDeleteString(*((HSTRING *)v15 + 14));
  *((_QWORD *)v15 + 14) = 0;
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v116, &v94);
  v37 = WindowsConcatString(*(HSTRING *)(v36 + 24), string2, (HSTRING *)v15 + 14);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)v37,
      ppvc);
  v38 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v15 + 10, &v101);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)v38,
      ppvc);
  v39 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v15 + 9, &v83);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)v39,
      ppvc);
  PdcActivation = UWAInstallWork::_GetPdcActivation(v15);
  if ( PdcActivation < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)PdcActivation,
      ppvc);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl'::`2'::impl) )
  {
    v41 = WindowsGetStringRawBuffer(*((HSTRING *)v15 + 14), 0);
    std::wstring::wstring(v116, v41);
    if ( !GetPreSearchUpdatePackageEnabledFromOneSettings() )
      goto LABEL_42;
    v42 = (_QWORD *)std::wstring::substr(v116, v117, 0, qword_1802CB020);
    LOBYTE(v16) = v16 | 1;
    v43 = &INSTALL_CALL_FROM_STORE;
    if ( (unsigned __int64)qword_1802CB028 > 7 )
      v43 = (__int64 *)INSTALL_CALL_FROM_STORE;
    v44 = v42[2];
    if ( v42[3] > 7u )
      v42 = (_QWORD *)*v42;
    v45 = 1;
    if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v42, v44, v43, qword_1802CB020) )
LABEL_42:
      v45 = 0;
    if ( (v16 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v117);
    if ( v45 )
    {
      try
      {
        if ( v87 )
        {
          v46 = DeserializeUpdates(&v83, v87);
          wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::operator=((char *)v15 + 104, v46);
          wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&v83);
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtExceptionMsg(
          retaddr,
          (void *)0xDF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          "Failure to Load Initial UpdateCollection.",
          (const char *)ppvb);
        v19 = v92;
        v18 = v91;
        v15 = v90;
        v85 = (HSTRING *)string;
      }
    }
    else
    {
      try
      {
        if ( v87 )
        {
          v47 = DeserializeUpdates(&v83, v87);
          wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::operator=((char *)v15 + 104, v47);
          wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&v83);
        }
        else if ( !a12 )
        {
          v48 = WindowsGetStringRawBuffer(*v85, 0);
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            0xEBu,
            "UWAInstallWork::UWAInstallWork",
            -1,
            L"Requested Offline WU scan. Attempting to get updatecollection",
            (const char *)v15 + 304,
            v48);
          bstrString = 0;
          Instance = CoCreateInstance(
                       &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
                       0,
                       1u,
                       &GUID_816858a4_260d_4260_933a_2585f1abc76b,
                       (LPVOID *)&bstrString);
          if ( Instance < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xED,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)Instance,
              ppvd);
          wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::reset((char *)v15 + 104);
          WindowsGetStringRawBuffer(*((HSTRING *)v15 + 14), 0);
          v83 = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)v15 + 15), 0);
          UserHandleOrNullIfLocalSystem = CallerContext::GetUserHandleOrNullIfLocalSystem((UWAInstallWork *)((char *)v15 + 152));
          LOBYTE(v79) = 0;
          updated = SearchUpdatePackages(UserHandleOrNullIfLocalSystem, v83, 0, 0);
          if ( updated < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xFC,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)updated,
              0);
          wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&bstrString);
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtExceptionMsg(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          "Failure to Load Initial UpdateCollection. Online Scan will be required",
          (const char *)ppva);
        v19 = v92;
        v18 = v91;
        v15 = v90;
        v85 = (HSTRING *)string;
      }
    }
    std::wstring::_Tidy_deallocate(v116);
  }
  else
  {
    try
    {
      if ( v87 )
      {
        v52 = DeserializeUpdates(&v83, v87);
        wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::operator=((char *)v15 + 104, v52);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&v83);
      }
      else if ( !a12 )
      {
        v53 = WindowsGetStringRawBuffer(*v85, 0);
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0x10Cu,
          "UWAInstallWork::UWAInstallWork",
          -1,
          L"Requested Offline WU scan. Attempting to get updatecollection",
          (const char *)v15 + 304,
          v53);
        v87 = 0;
        v54 = CoCreateInstance(
                &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
                0,
                1u,
                &GUID_816858a4_260d_4260_933a_2585f1abc76b,
                &v87);
        if ( v54 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            (const char *)(unsigned int)v54,
            ppve);
        wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::reset((char *)v15 + 104);
        WindowsGetStringRawBuffer(*((HSTRING *)v15 + 14), 0);
        v83 = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)v15 + 15), 0);
        v55 = CallerContext::GetUserHandleOrNullIfLocalSystem((UWAInstallWork *)((char *)v15 + 152));
        LOBYTE(v79) = 0;
        v56 = SearchUpdatePackages(v55, v83, 0, 0);
        if ( v56 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x11D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            (const char *)(unsigned int)v56,
            0);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&v87);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        "Failure to Load Initial UpdateCollection. Online Scan will be required",
        (const char *)ppv);
      v85 = (HSTRING *)string;
      v15 = v90;
      v18 = v91;
      v19 = v92;
    }
  }
  v57 = v102;
  if ( *v18 )
  {
    UWAInstallWork::_DetermineCollectionTypeIfNeeded(v15, *v18);
    v58 = v103;
    WindowsDeleteString(*v103);
    *v58 = 0;
    PackageFullNamesFromCollection = GetPackageFullNamesFromCollection(*v18, v58);
    TraceHR(
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x125u,
      "UWAInstallWork::UWAInstallWork",
      "GetPackageFullNamesFromCollection(_updateCollection.get(), _pkgFullNames.GetAddressOf())",
      PackageFullNamesFromCollection,
      v79);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::GetImpl'::`2'::impl) )
    {
      v60 = v104;
      if ( !*v104 || !SysStringLen(*v104) )
      {
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const unsigned __int16 *)&dword_18023C12C);
        UniqueIdFromCollection = GetUniqueIdFromCollection(*v18, &bstrString);
        if ( (int)TraceHR(
                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                    0x12Bu,
                    "UWAInstallWork::UWAInstallWork",
                    "GetUniqueIdFromCollection(_updateCollection.get(), &bstrUpdateId)",
                    UniqueIdFromCollection,
                    v80) >= 0
          && bstrString )
        {
          ATL::CComBSTR::operator=(v60, &bstrString);
        }
        SysFreeString(bstrString);
      }
    }
  }
  if ( a6 )
  {
    v62 = v105;
    v63 = v106;
    v64 = v107;
    v65 = v108;
    v66 = v109;
    v67 = *(_DWORD *)(a6 + 4);
    if ( v67 == 13 || (unsigned int)(v67 - 1) <= 1 )
    {
      v67 = 0;
    }
    else if ( v67 == 14 || v67 == 3 )
    {
      v67 = 8;
    }
    *v110 = v67;
    *v96 = *(_DWORD *)(a6 + 48);
    *v57 = *(_DWORD *)(a6 + 52);
    if ( v67 == 12 )
      v68 = *(_DWORD *)(a6 + 40);
    else
      v68 = 0;
    *v62 = v68;
    *v63 = *(_DWORD *)(a6 + 32);
    *v64 = *(_DWORD *)(a6 + 36);
    *v65 = *(_QWORD *)(a6 + 8);
    *v111 = *(_QWORD *)(a6 + 16);
    *v66 = *(_QWORD *)(a6 + 24);
    *v112 = *(_DWORD *)(a6 + 60);
    *v113 = *(_BYTE *)(a6 + 68) != 0;
    v69 = *(_QWORD *)(a6 + 16);
    if ( v69 && v69 >= *(_QWORD *)(a6 + 8) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
      {
        *(_OWORD *)v120 = *(_OWORD *)v19;
        v121 = *((_OWORD *)v19 + 1);
        v122 = *((_OWORD *)v19 + 2);
        v123 = *((_OWORD *)v19 + 3);
        v124 = *((_OWORD *)v19 + 4);
        v125 = *((_OWORD *)v19 + 5);
        v126 = *((_OWORD *)v19 + 6);
        v127 = *((_OWORD *)v19 + 7);
        v128 = v19[128];
      }
      else
      {
        TraceLoggingCorrelationVector::ToStringImpl(
          *v93,
          _InterlockedExchangeAdd64((volatile signed __int64 *)*v93 + 17, 0),
          v120);
      }
      v70 = WindowsGetStringRawBuffer(*v85, 0);
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x150u,
        "UWAInstallWork::UWAInstallWork",
        -1,
        L"Assert (%s): Failed",
        v120,
        v70,
        L"status->autoDownloadSize == 0 || (status->autoDownloadSize < status->downloadSize)");
      __int2c();
    }
    if ( *v66 > *v65 )
      *v66 = *v65;
  }
  else
  {
    v71 = *v95 & 1;
    *v96 = v71;
    *v57 = v71 ^ 1;
  }
  if ( ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::GetImpl'::`2'::impl)
     || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::GetImpl'::`2'::impl))
    && a13 > 0 )
  {
    *v57 = a13;
  }
  return v15;
}

```

## disassembly

```asm
0x1800e2b80  mov     r11, rsp
0x1800e2b83  mov     [r11+18h], rbx
0x1800e2b87  mov     [r11+20h], rsi
0x1800e2b8b  push    rdi
0x1800e2b8c  push    r12
0x1800e2b8e  push    r13
0x1800e2b90  push    r14
0x1800e2b92  push    r15
0x1800e2b94  sub     rsp, 2F0h
0x1800e2b9b  mov     rax, cs:__security_cookie
0x1800e2ba2  xor     rax, rsp
0x1800e2ba5  mov     [rsp+318h+var_38], rax
0x1800e2bad  mov     r13d, r9d
0x1800e2bb0  mov     [rsp+318h+var_274], r9d
0x1800e2bb8  mov     [rsp+318h+bstrString], r8
0x1800e2bbd  mov     r15, rdx
0x1800e2bc0  mov     r14, rcx
0x1800e2bc3  mov     [r11-270h], rcx
0x1800e2bca  mov     rax, [rsp+318h+arg_30]
0x1800e2bd2  mov     [rsp+318h+var_2A0], rax
0x1800e2bd7  mov     rax, [rsp+318h+arg_38]
0x1800e2bdf  mov     [r11-218h], rax
0x1800e2be6  mov     rax, [rsp+318h+arg_40]
0x1800e2bee  mov     [rsp+318h+string2], rax
0x1800e2bf6  mov     rax, [rsp+318h+arg_48]
0x1800e2bfe  mov     [rsp+318h+var_280], rax
0x1800e2c06  mov     rax, [rsp+318h+arg_50]
0x1800e2c0e  mov     [rsp+318h+string], rax
0x1800e2c16  xor     esi, esi
0x1800e2c18  mov     edi, esi
0x1800e2c1a  mov     [rsp+318h+var_298], esi
0x1800e2c21  lea     rbx, [rcx+8]
0x1800e2c25  mov     rcx, rbx
0x1800e2c28  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>(void)
0x1800e2c2d  mov     qword ptr [r14+40h], 1
0x1800e2c35  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInstallWork@Internal@WindowsUpdate@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6BIInstallWork@Internal@WindowsUpdate@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `WindowsUpdate::Internal::IInstallWork'}
0x1800e2c3c  mov     [r14], rax
0x1800e2c3f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInstallWork@Internal@WindowsUpdate@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'}
0x1800e2c46  mov     [rbx], rax
0x1800e2c49  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInstallWork@Internal@WindowsUpdate@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'}
0x1800e2c50  mov     [r14+10h], rax
0x1800e2c54  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInstallWork@Internal@WindowsUpdate@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,WindowsUpdate::Internal::IInstallWork,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800e2c5b  mov     [r14+18h], rax
0x1800e2c5f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800e2c66  test    rcx, rcx
0x1800e2c69  jz      short loc_1800E2C78
0x1800e2c6b  mov     rax, [rcx]
0x1800e2c6e  mov     rax, [rax+8]
0x1800e2c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2c77  nop
0x1800e2c78  lea     rax, ??_7UWAInstallWork@@6BIInstallWork@Internal@WindowsUpdate@@@; const UWAInstallWork::`vftable'{for `WindowsUpdate::Internal::IInstallWork'}
0x1800e2c7f  mov     [r14], rax
0x1800e2c82  lea     rax, ??_7UWAInstallWork@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>'}
0x1800e2c89  mov     [rbx], rax
0x1800e2c8c  lea     rax, ??_7UWAInstallWork@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAgileObject@@@Details@WRL@Microsoft@@@; const UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAgileObject>'}
0x1800e2c93  mov     [r14+10h], rax
0x1800e2c97  lea     rax, ??_7UWAInstallWork@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const UWAInstallWork::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800e2c9e  mov     [r14+18h], rax
0x1800e2ca2  mov     [r14+48h], rsi
0x1800e2ca6  mov     [r14+50h], rsi
0x1800e2caa  mov     [r14+58h], rsi
0x1800e2cae  lea     rbx, [r14+60h]
0x1800e2cb2  mov     [rsp+318h+var_208], rbx
0x1800e2cba  mov     [rbx], rsi
0x1800e2cbd  lea     r12, [r14+68h]
0x1800e2cc1  mov     [rsp+318h+var_268], r12
0x1800e2cc9  mov     [r12], rsi
0x1800e2ccd  mov     [r14+70h], rsi
0x1800e2cd1  mov     [r14+78h], rsi
0x1800e2cd5  mov     [r14+80h], r13d
0x1800e2cdc  xorps   xmm0, xmm0
0x1800e2cdf  movups  xmmword ptr [r14+84h], xmm0
0x1800e2ce7  lea     rdx, [r14+98h]
0x1800e2cee  mov     rcx, r15
0x1800e2cf1  call    ?copy@CallerContext@@QEBA?AV1@XZ; CallerContext::copy(void)
0x1800e2cf6  nop
0x1800e2cf7  lea     rax, [r14+128h]
0x1800e2cfe  mov     [rsp+318h+var_258], rax
0x1800e2d06  mov     [rax], rsi
0x1800e2d09  lea     r13, [r14+130h]
0x1800e2d10  mov     [rsp+318h+var_260], r13
0x1800e2d18  xor     edx, edx; Val
0x1800e2d1a  mov     r8d, 81h; Size
0x1800e2d20  mov     rcx, r13; void *
0x1800e2d23  call    memset_0
0x1800e2d28  mov     [r14+1B8h], rsi
0x1800e2d2f  mov     [r14+1C0h], rsi
0x1800e2d36  mov     rax, cs:qword_1802E6610
0x1800e2d3d  test    rax, rax
0x1800e2d40  jz      short loc_1800E2D46
0x1800e2d42  lock inc dword ptr [rax+8]
0x1800e2d46  mov     rax, cs:?_pdcManager@InstallAgentPdcManager@@0V?$shared_ptr@VInstallAgentPdcManager@@@std@@A; std::shared_ptr<InstallAgentPdcManager> InstallAgentPdcManager::_pdcManager
0x1800e2d4d  mov     [r14+1B8h], rax
0x1800e2d54  mov     rax, cs:qword_1802E6610
0x1800e2d5b  mov     [r14+1C0h], rax
0x1800e2d62  mov     [r14+1C8h], rsi
0x1800e2d69  mov     [r14+1D0h], rsi
0x1800e2d70  lea     rbx, [r14+1D8h]
0x1800e2d77  mov     [rsp+318h+var_290], rbx
0x1800e2d7f  mov     [rbx], rsi
0x1800e2d82  mov     [r14+1E0h], rsi
0x1800e2d89  mov     [r14+1E8h], rsi
0x1800e2d90  lea     rax, [r14+1F0h]
0x1800e2d97  mov     [rsp+318h+var_200], rax
0x1800e2d9f  mov     [rax], rsi
0x1800e2da2  mov     al, [rsp+318h+arg_58]
0x1800e2da9  mov     [r14+1F8h], al
0x1800e2db0  mov     [r14+200h], rsi
0x1800e2db7  mov     [r14+208h], rsi
0x1800e2dbe  mov     [r14+210h], rsi
0x1800e2dc5  mov     [r14+218h], rsi
0x1800e2dcc  mov     [r14+220h], rsi
0x1800e2dd3  mov     [r14+228h], rsi
0x1800e2dda  mov     [r14+230h], rsi
0x1800e2de1  mov     [r14+238h], rsi
0x1800e2de8  mov     [r14+240h], rsi
0x1800e2def  mov     [r14+248h], rsi
0x1800e2df6  mov     [r14+250h], rsi
0x1800e2dfd  mov     [r14+258h], rsi
0x1800e2e04  mov     [r14+260h], rsi
0x1800e2e0b  lea     rcx, [r14+268h]
0x1800e2e12  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800e2e17  nop
0x1800e2e18  lea     rcx, [r14+278h]
0x1800e2e1f  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x1800e2e24  nop
0x1800e2e25  lea     rcx, [r14+2B8h]
0x1800e2e2c  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x1800e2e31  nop
0x1800e2e32  lea     rcx, [r14+2F8h]
0x1800e2e39  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>(void)
0x1800e2e3e  nop
0x1800e2e3f  lea     rcx, [r14+338h]
0x1800e2e46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e2e4b  nop
0x1800e2e4c  lea     rcx, [r14+358h]
0x1800e2e53  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>(void)
0x1800e2e58  nop
0x1800e2e59  mov     [r14+398h], rsi
0x1800e2e60  mov     [r14+3A0h], rsi
0x1800e2e67  mov     [r14+3A8h], rsi
0x1800e2e6e  mov     [r14+3B0h], rsi
0x1800e2e75  lea     rcx, [r14+3B8h]
0x1800e2e7c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e2e81  nop
0x1800e2e82  mov     [r14+3D8h], si
0x1800e2e8a  mov     [r14+3DAh], sil
0x1800e2e91  mov     [r14+3DCh], esi
0x1800e2e98  mov     eax, 80004005h
0x1800e2e9d  mov     [r14+3E0h], eax
0x1800e2ea4  mov     [r14+3E4h], eax
0x1800e2eab  mov     [r14+3E8h], rsi
0x1800e2eb2  lea     rcx, [r14+3F0h]
0x1800e2eb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e2ebe  nop
0x1800e2ebf  mov     [r14+410h], rsi
0x1800e2ec6  lea     rcx, [r14+418h]; SRWLock
0x1800e2ecd  call    cs:__imp_InitializeSRWLock
0x1800e2ed3  lea     rcx, [r14+420h]
0x1800e2eda  mov     [rsp+318h+var_248], rcx
0x1800e2ee2  mov     eax, [rsp+318h+arg_20]
0x1800e2ee9  mov     [rcx], eax
0x1800e2eeb  lea     r15, [r14+424h]
0x1800e2ef2  mov     [rsp+318h+var_1D0], r15
0x1800e2efa  mov     [r15], esi
0x1800e2efd  mov     [r14+428h], esi
0x1800e2f04  lea     rax, [r14+42Ch]
0x1800e2f0b  mov     [rsp+318h+var_1F8], rax
0x1800e2f13  mov     [rax], esi
0x1800e2f15  mov     [r14+430h], esi
0x1800e2f1c  lea     rax, [r14+434h]
0x1800e2f23  mov     [rsp+318h+var_240], rax
0x1800e2f2b  mov     [rax], esi
0x1800e2f2d  lea     rax, [r14+438h]
0x1800e2f34  mov     [rsp+318h+var_210], rax
0x1800e2f3c  mov     [rax], esi
0x1800e2f3e  mov     byte ptr [r14+43Ch], 1
0x1800e2f46  lea     rax, [r14+440h]
0x1800e2f4d  mov     [rsp+318h+var_1F0], rax
0x1800e2f55  mov     [rax], esi
0x1800e2f57  lea     rax, [r14+444h]
0x1800e2f5e  mov     [rsp+318h+var_1E8], rax
0x1800e2f66  mov     [rax], esi
0x1800e2f68  lea     rax, [r14+448h]
0x1800e2f6f  mov     [rsp+318h+var_1E0], rax
0x1800e2f77  mov     [rax], rsi
0x1800e2f7a  lea     rax, [r14+450h]
0x1800e2f81  mov     [rsp+318h+var_1C8], rax
0x1800e2f89  mov     [rax], rsi
0x1800e2f8c  lea     rax, [r14+458h]
0x1800e2f93  mov     [rsp+318h+var_1D8], rax
0x1800e2f9b  mov     [rax], rsi
0x1800e2f9e  mov     [r14+460h], sil
0x1800e2fa5  mov     dword ptr [r14+464h], 8000000Ah
0x1800e2fb0  mov     [r14+468h], sil
0x1800e2fb7  lea     rax, [r14+469h]
0x1800e2fbe  mov     [rsp+318h+var_1B8], rax
0x1800e2fc6  mov     [rax], sil
0x1800e2fc9  lea     rax, [r14+46Ch]
0x1800e2fd0  mov     [rsp+318h+var_1C0], rax
0x1800e2fd8  mov     [rax], esi
0x1800e2fda  mov     [r14+470h], esi
0x1800e2fe1  mov     [r14+478h], rsi
0x1800e2fe8  mov     [r14+480h], rsi
0x1800e2fef  mov     [r14+488h], rsi
0x1800e2ff6  lea     rax, [r14+490h]
0x1800e2ffd  mov     [rax], rsi
0x1800e3000  mov     [rax+8], rsi
0x1800e3004  mov     [rax+10h], rsi
0x1800e3008  mov     [r14+4A8h], rsi
0x1800e300f  mov     [r14+4B0h], rsi
0x1800e3016  mov     [r14+4B8h], rsi
0x1800e301d  mov     [r14+4C0h], rsi
0x1800e3024  lea     rcx, [r14+4C8h]; SRWLock
0x1800e302b  call    cs:__imp_InitializeSRWLock
0x1800e3031  lea     rcx, [r14+4D0h]; SRWLock
0x1800e3038  call    cs:__imp_InitializeSRWLock
0x1800e303e  nop
0x1800e303f  lea     rcx, [r14+4D8h]; this
0x1800e3046  call    ??0OpaqueTokenEncoder@@QEAA@XZ; OpaqueTokenEncoder::OpaqueTokenEncoder(void)
0x1800e304b  nop
0x1800e304c  mov     [r14+4F8h], esi
0x1800e3053  mov     [r14+500h], rsi
0x1800e305a  mov     [r14+508h], esi
0x1800e3061  mov     [r14+510h], rsi
0x1800e3068  mov     [r14+518h], esi
0x1800e306f  xorps   xmm0, xmm0
0x1800e3072  movups  xmmword ptr [r14+53Ch], xmm0
0x1800e307a  xorps   xmm1, xmm1
0x1800e307d  movups  xmmword ptr [r14+54Ch], xmm1
0x1800e3085  movups  xmmword ptr [r14+55Ch], xmm0
0x1800e308d  lea     rdx, [r14+84h]; ActivityId
0x1800e3094  mov     ecx, 1; ControlCode
0x1800e3099  call    cs:__imp_EventActivityIdControl
0x1800e309f  mov     rax, [rsp+318h+var_248]
0x1800e30a7  test    byte ptr [rax], 10h
0x1800e30aa  jnz     short loc_1800E30EE
0x1800e30ac  cmp     dword ptr [r14+80h], 1
0x1800e30b4  jnz     short loc_1800E30EE
0x1800e30b6  test    dword ptr [rax], 20000h
0x1800e30bc  jz      short loc_1800E30E7
0x1800e30be  test    byte ptr [rax], 1
0x1800e30c1  jnz     short loc_1800E30EE
0x1800e30c3  mov     [rsp+318h+var_298], esi
0x1800e30ca  lea     rcx, [rsp+318h+var_298]; enum WindowsUpdate::Internal::AutoUpdateState *
0x1800e30d2  call    ?GetAutoUpdateState@@YAJPEAW4AutoUpdateState@Internal@WindowsUpdate@@@Z; GetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState *)
0x1800e30d7  mov     eax, [rsp+318h+var_298]
0x1800e30de  dec     eax
0x1800e30e0  test    eax, 0FFFFFFFDh
0x1800e30e5  jz      short loc_1800E30EE
0x1800e30e7  mov     dword ptr [r15], 7
0x1800e30ee  lea     rcx, [r14+98h]; this
0x1800e30f5  call    ?SetAutoReleaseOnLogoff@CallerContext@@QEAAXXZ; CallerContext::SetAutoReleaseOnLogoff(void)
0x1800e30fa  xor     edx, edx; length
0x1800e30fc  mov     rcx, [rsp+318h+string]; string
0x1800e3104  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e310a  mov     rdx, rax
0x1800e310d  mov     r8d, 81h
0x1800e3113  lea     rcx, [rsp+318h+Str]
0x1800e311b  call    cs:__imp__o_wcstombs
0x1800e3121  lea     rcx, [rsp+318h+Str]; char *
0x1800e3129  call    ?Validate@TraceLoggingCorrelationVector@@SA_NPEBD@Z; TraceLoggingCorrelationVector::Validate(char const *)
0x1800e312e  lea     r15, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800e3135  test    al, al
0x1800e3137  jnz     short loc_1800E318B
0x1800e3139  lea     rax, aFailed_1; "Failed"
0x1800e3140  mov     [rsp+318h+var_2D0], rax
0x1800e3145  lea     rax, aTraceloggingco; "TraceLoggingCorrelationVector::Validate"...
0x1800e314c  mov     [rsp+318h+var_2D8], rax
0x1800e3151  mov     [rsp+318h+var_2E0], rsi; unsigned __int16 *
0x1800e3156  mov     [rsp+318h+var_2E8], rsi; char *
0x1800e315b  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800e3162  mov     [rsp+318h+var_2F0], rax; unsigned __int16 *
0x1800e3167  mov     dword ptr [rsp+318h+ppv], 0FFFFFFFFh; int
0x1800e316f  lea     r9, aUwainstallwork_32; "UWAInstallWork::UWAInstallWork"
0x1800e3176  mov     r8d, 9Ch; unsigned int
0x1800e317c  mov     rdx, r15; char *
0x1800e317f  mov     ecx, 1; unsigned int
0x1800e3184  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800e3189  int     2Ch; Windows NT - assertion failure
0x1800e318b  xor     edx, edx; bool
0x1800e318d  lea     rcx, [rsp+318h+Str]; Str
0x1800e3195  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1800e319a  mov     [rsp+318h+string], rax
0x1800e31a2  lea     rdx, [rsp+318h+string]
0x1800e31aa  mov     rcx, [rsp+318h+var_258]
0x1800e31b2  call    ??$?4U?$default_delete@VTraceLoggingCorrelationVector@@@std@@$0A@@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(std::unique_ptr<TraceLoggingCorrelationVector> &&)
0x1800e31b7  lea     rcx, [rsp+318h+string]
0x1800e31bf  call    ??1?$_Temporary_owner@VTraceLoggingCorrelationVector@@@std@@QEAA@XZ; std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(void)
0x1800e31c4  mov     rax, [rsp+318h]
0x1800e31cc  mov     rcx, [rsp+318h+var_258]
0x1800e31d4  mov     rcx, [rcx]; this
0x1800e31d7  test    rcx, rcx
0x1800e31da  jz      loc_1800E3D61
0x1800e31e0  mov     [rsp+318h+string], rbx
0x1800e31e8  mov     rdx, rsi
0x1800e31eb  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800e31f4  mov     r8, r13; char *
0x1800e31f7  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800e31fc  xorps   xmm0, xmm0
  ... truncated ...
```
