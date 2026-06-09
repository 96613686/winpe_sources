# Windows::Internal::Storage::Cloud::CloudStore::OldSave(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Internal::Storage::Cloud::SaveOptions,unsigned __int64,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer *,Windows::Internal::Storage::Cloud::ICloudStoreSaveResult * *)

- ea: `0x1800608ac`
- end: `0x180061bd8`
- name: `?OldSave@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJW4PartitionKind@2345@PEAUHSTRING__@@11W4SaveOptions@2345@_KPEAUIBuffer@Streams@35@34PEAPEAUICloudStoreSaveResult@2345@@Z`
- size: `4908`
- prototype: `__int64 __fastcall(__int64, unsigned int, HSTRING, HSTRING, HSTRING, unsigned int, unsigned __int64, CloudStoreUtilities *, unsigned __int64, CloudStoreUtilities *, __int64 *)`
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18016ebd0`

## callees

- `0x18000e84c`
- `0x18000f4b4`
- `0x180010688`
- `0x1800122f4`
- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180023fd4`
- `0x180024020`
- `0x180024fd0`
- `0x18002570c`
- `0x18003a428`
- `0x18003a478`
- `0x18003b170`
- `0x180047904`
- `0x18004f58c`
- `0x18005b244`
- `0x18005b770`
- `0x18005ba64`
- `0x18005babc`
- `0x18005d4b8`
- `0x18005de38`
- `0x18005ded4`
- `0x18005e4a0`
- `0x18005f34c`
- `0x18005f7bc`
- `0x18005f914`
- `0x1800608ac`
- `0x180061be0`
- `0x180062040`
- `0x1800621f4`
- `0x1800626e8`
- `0x180062868`
- `0x180091548`
- `0x1800a5320`
- `0x1800aee5c`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1800e93e0`
- `0x18010d418`
- `0x1801201a0`
- `0x1801236bc`
- `0x1801667e0`
- `0x180168920`
- `0x18016b818`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060ad3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060ad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006130a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061323`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061353`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006160d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006130a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061323`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061353`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006160d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006097a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006098d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800609a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061af0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006097a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006098d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800609a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180060bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061af0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006110a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006111a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800612a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800612b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006137b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006138b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060a78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006110a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006111a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800612a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800612b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006137b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006138b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800614ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061b45`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::OldSave(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        unsigned int a6,
        unsigned __int64 a7,
        CloudStoreUtilities *a8,
        unsigned __int64 a9,
        CloudStoreUtilities *a10,
        __int64 *a11)
{
  int v13; // r14d
  const char *v14; // r9
  struct Windows::Storage::Streams::IBuffer *v15; // rdx
  struct Windows::Storage::Streams::IBuffer *v16; // rdx
  unsigned int BufferSizeForTelemetry; // r13d
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v19; // rdi
  PCWSTR v20; // rbx
  const unsigned __int16 *v21; // r9
  unsigned int v22; // ebx
  const char *v23; // r9
  __int64 v25; // r9
  int EffectivePartition; // eax
  unsigned int v27; // ebx
  HSTRING v28; // r13
  int v29; // eax
  unsigned int v30; // ebx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, struct Windows::Storage::Streams::IBuffer **); // rdi
  __int64 (__fastcall *v32)(_QWORD, GUID *, struct Windows::Storage::Streams::IBuffer **); // rbx
  int v33; // eax
  int v34; // eax
  struct Windows::Storage::Streams::IBuffer *v35; // rcx
  const unsigned __int16 *v36; // r13
  const char *v37; // r9
  char v38; // al
  unsigned __int64 v39; // r12
  int v40; // eax
  int v41; // ebx
  int BufferBytesNoCopyIfPossible; // eax
  __int64 v43; // r8
  const char *v44; // r9
  unsigned int v45; // ebx
  unsigned __int64 i; // rcx
  char v47; // al
  int RootFromAttribute; // ebx
  struct Windows::Storage::Streams::IBuffer *v49; // rcx
  void *v50; // rdx
  const char *v51; // r9
  __int64 result; // rax
  int v53; // eax
  unsigned int v54; // ebx
  int v55; // eax
  unsigned int v56; // ebx
  HSTRING v57; // rsi
  unsigned int v58; // ebx
  const char *v59; // rax
  int v60; // edx
  __int64 v61; // rcx
  __int64 v62; // rcx
  int v63; // ebx
  struct Windows::Storage::Streams::IBuffer *v64; // rcx
  void *v65; // rdx
  struct Windows::Storage::Streams::IBuffer *v66; // rbx
  const char *v67; // r9
  int v68; // eax
  unsigned int v69; // ebx
  struct Windows::Storage::Streams::IBuffer *v70; // rcx
  struct Windows::Storage::Streams::IBuffer *v71; // rcx
  __int64 v72; // rdx
  struct Windows::Storage::Streams::IBuffer *v73; // rcx
  void *v74; // rdx
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v75; // rbx
  Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v76; // rax
  struct Windows::Storage::Streams::IBuffer *v77; // rcx
  void *v78; // rdx
  int v79; // eax
  unsigned int v80; // ebx
  struct Windows::Storage::Streams::IBuffer *v81; // rcx
  void *v82; // rdx
  __int64 v83; // rax
  struct Windows::Storage::Streams::IBuffer *v84; // rcx
  void *v85; // rdx
  bool v86; // zf
  _QWORD *v87; // rax
  __int64 v88; // rcx
  int v89; // eax
  const char *v90; // r9
  unsigned int v91; // edi
  int v92; // [rsp+20h] [rbp-318h]
  int *v93; // [rsp+20h] [rbp-318h]
  int v94; // [rsp+20h] [rbp-318h]
  int v95; // [rsp+20h] [rbp-318h]
  struct Windows::Storage::Streams::IBuffer *v96; // [rsp+60h] [rbp-2D8h] BYREF
  HSTRING v97; // [rsp+68h] [rbp-2D0h] BYREF
  HSTRING v98; // [rsp+70h] [rbp-2C8h]
  struct Windows::Storage::Streams::IBuffer *v99; // [rsp+78h] [rbp-2C0h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-2B8h] BYREF
  unsigned int v101; // [rsp+88h] [rbp-2B0h]
  int v102; // [rsp+8Ch] [rbp-2ACh]
  LPVOID pv; // [rsp+90h] [rbp-2A8h] BYREF
  unsigned __int64 p_pv; // [rsp+98h] [rbp-2A0h] BYREF
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v105; // [rsp+A0h] [rbp-298h] BYREF
  char v106; // [rsp+A8h] [rbp-290h]
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v107; // [rsp+B0h] [rbp-288h] BYREF
  __int64 v108; // [rsp+B8h] [rbp-280h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-278h]
  struct Windows::Storage::Streams::IBuffer *v110; // [rsp+C8h] [rbp-270h] BYREF
  unsigned __int8 *v111; // [rsp+D0h] [rbp-268h] BYREF
  HSTRING v112; // [rsp+D8h] [rbp-260h]
  HSTRING v113; // [rsp+E0h] [rbp-258h]
  __int64 *v114; // [rsp+E8h] [rbp-250h]
  __int128 v115; // [rsp+F0h] [rbp-248h] BYREF
  _QWORD v116[3]; // [rsp+100h] [rbp-238h] BYREF
  unsigned __int64 v117; // [rsp+118h] [rbp-220h]
  _BYTE v118[32]; // [rsp+120h] [rbp-218h] BYREF
  _QWORD v119[42]; // [rsp+140h] [rbp-1F8h] BYREF
  int v120; // [rsp+290h] [rbp-A8h] BYREF
  const char *v121; // [rsp+2A0h] [rbp-98h]
  __int64 v122; // [rsp+2A8h] [rbp-90h]
  const char *v123; // [rsp+2B0h] [rbp-88h]
  int v124; // [rsp+2B8h] [rbp-80h]
  int v125; // [rsp+2BCh] [rbp-7Ch]
  unsigned __int64 *p_p_pv; // [rsp+2C0h] [rbp-78h]
  __int64 v127; // [rsp+2C8h] [rbp-70h]
  struct Windows::Storage::Streams::IBuffer **v128; // [rsp+2D0h] [rbp-68h]
  __int64 v129; // [rsp+2D8h] [rbp-60h]
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v130; // [rsp+2E0h] [rbp-58h]
  int v131; // [rsp+2E8h] [rbp-50h]
  int v132; // [rsp+2ECh] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v112 = a4;
  v113 = a3;
  v101 = a2;
  v110 = a8;
  string = a5;
  v114 = a11;
  v13 = 0;
  LODWORD(v96) = 0;
  try
  {
    if ( Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(
           (Windows::Internal::Storage::Cloud::CloudStore *)a1,
           a4) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x50F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v14);
    }
    *a11 = 0;
    EffectiveUserContext::Impersonate((void ***)(a1 + 200), &hObject);
    LODWORD(v96) = CloudStoreUtilities::GetBufferSizeForTelemetry(a10, v15);
    BufferSizeForTelemetry = CloudStoreUtilities::GetBufferSizeForTelemetry(a8, v16);
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    v19 = WindowsGetStringRawBuffer(string, 0);
    v20 = WindowsGetStringRawBuffer(v113, 0);
    wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v119,
      "SaveActivity");
    v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
    v21 = v20;
    v22 = v101;
    Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::StartActivity(
      (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119,
      byte_1802299F5,
      v101,
      v21,
      &LocaleName,
      v19,
      StringRawBuffer,
      a6,
      a7,
      BufferSizeForTelemetry,
      a9,
      (unsigned int)v96);
    v102 = a6 & 7;
    if ( (a6 & 7) != 0 && (((a6 & 7) - 1LL) & a6 & 7) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x51F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v23);
    WindowsDeleteString(0);
    v97 = 0;
    LOBYTE(v25) = 1;
    EffectivePartition = Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(a1, v22, v113, v25);
    v27 = EffectivePartition;
    if ( EffectivePartition < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x522,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)EffectivePartition,
        (int)&v97);
      WindowsDeleteString(v97);
      v97 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v27;
    }
    v115 = 0;
    p_pv = 0;
    v99 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 344));
    v108 = a1 + 344;
    WindowsDeleteString(0);
    v28 = v97;
    v98 = 0;
    v29 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)a1);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1111,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v29,
        (int)&v97);
    }
    else
    {
      v96 = 0;
      v31 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::Storage::Streams::IBuffer **))(a1 + 480);
      v32 = **v31;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
      v33 = v32(v31, &GUID_3f14a274_31fe_4e07_b3fb_6830cde1bfe0, &v96);
      v30 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1114,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v33,
          (int)&v97);
        v71 = v96;
        if ( v96 )
        {
          v96 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v71 + 16LL))(v71);
        }
      }
      else
      {
        v92 = (int)string;
        v34 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, _QWORD, HSTRING, HSTRING))(*(_QWORD *)v96 + 48LL))(
                v96,
                v101,
                v28,
                v112);
        v30 = v34;
        if ( v34 >= 0 )
        {
          v35 = v96;
          if ( v96 )
          {
            v96 = 0;
            (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = WindowsGetStringRawBuffer(v98, 0);
          if ( !IsValidBuffer(a10) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x530,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              v37);
          if ( (a6 & 0x10) != 0 || (v86 = !IsASTAOrMainSTA(), v38 = 1, v86) )
            v38 = 0;
          if ( v38 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x531,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)0x8001010ELL,
              v92);
          if ( !a9 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x532,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              v37);
          if ( (a6 & 8) != 0 )
          {
            if ( v110 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x538,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                v37);
            if ( a7 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x539,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                v37);
            if ( v99 != a10 )
            {
              v96 = a10;
              Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::InternalAddRef(&v96);
              v96 = v99;
              v99 = a10;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
            }
            v39 = a9;
          }
          else
          {
            v66 = v110;
            if ( !IsValidBuffer(v110) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x53F,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                v67);
            v96 = 0;
            v110 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
            v68 = Windows::Internal::Storage::Cloud::CloudStore::LoadAndResolveInternal(
                    (Windows::Internal::Storage::Cloud::CloudStore *)a1,
                    v36,
                    v66,
                    a7,
                    a10,
                    a9,
                    &v96,
                    (unsigned __int64 *)&v110,
                    &v99,
                    &p_pv);
            v69 = v68;
            if ( v68 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x54C,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                (const char *)(unsigned int)v68,
                v92);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v108);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
              WindowsDeleteString(v98);
              v98 = 0;
              WindowsDeleteString(v97);
              v97 = 0;
              Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
              return v69;
            }
            v70 = v96;
            if ( v96 )
            {
              v96 = 0;
              (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v70 + 16LL))(v70);
            }
            v39 = p_pv;
          }
          v40 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)a1);
          v41 = v40;
          if ( v40 < 0 )
          {
            v72 = 4511;
          }
          else
          {
            v40 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *))(**(_QWORD **)(a1 + 480)
                                                                                          + 32LL))(
                    *(_QWORD *)(a1 + 480),
                    v36,
                    &v115);
            v41 = v40;
            if ( v40 >= 0 )
            {
              v41 = 0;
              goto LABEL_27;
            }
            v72 = 4512;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v72,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v40,
            v92);
LABEL_27:
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x54F,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v41,
              v92);
            if ( a1 != -344 )
              ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 344));
            v73 = v99;
            if ( v99 )
            {
              v99 = 0;
              (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v73 + 16LL))(v73);
            }
            WindowsDeleteString(v98);
            v98 = 0;
            WindowsDeleteString(v97);
            v97 = 0;
            v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
            wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
            wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
            if ( hObject != (HANDLE)-1LL )
              wil::details::RevertImpersonateToken(hObject, v74);
            return (unsigned int)v41;
          }
          v111 = 0;
          LODWORD(v96) = 0;
          BufferBytesNoCopyIfPossible = GetBufferBytesNoCopyIfPossible(
                                          (__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *))v99,
                                          &v111,
                                          (unsigned int *)&v96);
          v45 = BufferBytesNoCopyIfPossible;
          if ( BufferBytesNoCopyIfPossible < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x553,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)BufferBytesNoCopyIfPossible,
              v92);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v108);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
            WindowsDeleteString(v98);
            v98 = 0;
            WindowsDeleteString(v97);
            v97 = 0;
            Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
            return v45;
          }
          if ( (_DWORD)v96 )
          {
            if ( (unsigned int)v96 < 4uLL )
            {
LABEL_117:
              v47 = 1;
LABEL_36:
              if ( v47 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x554,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                  v44);
              pv = 0;
              p_pv = (unsigned __int64)&pv;
              v105 = 0;
              v106 = 1;
              RootFromAttribute = CloudStoreUtilities::GetRootFromAttribute(a1 + 232, (unsigned int)v115, v43, &v105);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
              if ( RootFromAttribute >= 0 )
              {
                v53 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache((Windows::Internal::Storage::Cloud::CloudStore *)a1);
                v54 = v53;
                if ( v53 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x559,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                    (const char *)(unsigned int)v53,
                    v92);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v108);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
                  WindowsDeleteString(v98);
                  v98 = 0;
                  WindowsDeleteString(v97);
                  v97 = 0;
                  Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
                  return v54;
                }
                LODWORD(v93) = (_DWORD)v111;
                v55 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, LPVOID, const unsigned __int16 *))(**(_QWORD **)(a1 + 496) + 48LL))(
                        *(_QWORD *)(a1 + 496),
                        v36,
                        pv,
                        L"Current");
                v56 = v55;
                if ( v55 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x55A,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                    (const char *)(unsigned int)v55,
                    (int)v93);
                  if ( pv )
                    CoTaskMemFree(pv);
                  if ( a1 != -344 )
                    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 344));
                  v81 = v99;
                  if ( v99 )
                  {
                    v99 = 0;
                    (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v81 + 16LL))(v81);
                  }
                  WindowsDeleteString(v98);
                  v98 = 0;
                  WindowsDeleteString(v97);
                  v97 = 0;
                  v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
                  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
                  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
                  if ( hObject != (HANDLE)-1LL )
                    wil::details::RevertImpersonateToken(hObject, v82);
                  return v56;
                }
                else
                {
                  if ( pv )
                    CoTaskMemFree(pv);
                  if ( a1 != -344 )
                    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 344));
                  v57 = v112;
                  if ( (_DWORD)v115 == 1 )
                  {
                    LODWORD(v93) = (_DWORD)string;
                    Windows::Internal::Storage::Cloud::CloudStore::AddToSystemPartitionIndexIfNeeded(
                      a1,
                      v101,
                      v97,
                      v112);
                  }
                  DebugLogObject::DebugLogObject((DebugLogObject *)&p_pv, v99);
                  v58 = 2;
                  if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
                  {
                    std::wstring::wstring(v116);
                    LODWORD(v96) = 1;
                    v59 = (const char *)WideStringToUtf8String(v118, v116);
                    v13 = 3;
                    v60 = p_pv;
                    if ( *((_QWORD *)v59 + 3) > 0xFu )
                      v59 = *(const char **)v59;
                    LODWORD(v96) = p_pv;
                    p_pv = v39;
                    v121 = byte_1802299F5;
                    v122 = 1;
                    if ( v59 )
                    {
                      v61 = -1;
                      do
                        ++v61;
                      while ( v59[v61] );
                      v62 = (unsigned int)(v61 + 1);
                    }
                    else
                    {
                      v59 = "NULL";
                      v62 = 5;
                    }
                    v123 = v59;
                    v124 = v62;
                    v125 = 0;
                    p_p_pv = &p_pv;
                    v127 = 8;
                    v128 = &v96;
                    v129 = 4;
                    v130 = v105;
                    v131 = v60;
                    v132 = 0;
                    v93 = &v120;
                    McGenEventWrite_EventWriteTransfer(v62, Debug_Saved, v105, 6);
                  }
                  if ( (v13 & 2) != 0 )
                  {
                    v13 &= ~2u;
                    std::string::_Tidy_deallocate(v118);
                  }
                  if ( (v13 & 1) != 0 )
                  {
                    v13 &= ~1u;
                    if ( v117 > 7 )
                      std::_Deallocate<16>(v116[0], 2 * v117 + 2);
                  }
                  if ( (_DWORD)v115 == 1 )
                  {
                    WindowsGetStringRawBuffer(v57, 0);
                    v89 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStorage((Windows::Internal::Storage::Cloud::CloudStore *)a1);
                    v91 = v89;
                    if ( v89 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x569,
                        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                        (const char *)(unsigned int)v89,
                        (int)v93);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
                      WindowsDeleteString(v98);
                      v98 = 0;
                      WindowsDeleteString(v97);
                      v97 = 0;
                      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
                      return v91;
                    }
                    if ( v102 )
                    {
                      switch ( v102 )
                      {
                        case 1:
                          v58 = 0;
                          break;
                        case 2:
                          v58 = 1;
                          break;
                        case 4:
                          break;
                        default:
                          wil::details::in1diag3::_FailFast_Unexpected(
                            retaddr,
                            (void *)0x11B3,
                            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                            v90);
                      }
                    }
                    else
                    {
                      v58 = HIDWORD(v115);
                    }
                    v79 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**(_QWORD **)(a1 + 488)
                                                                                              + 32LL))(
                            *(_QWORD *)(a1 + 488),
                            v36,
                            v58);
                    v80 = v79;
                    if ( v79 < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x56E,
                        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                        (const char *)(unsigned int)v79,
                        (int)v93);
                      if ( (Microsoft_Windows_CloudStoreEnableBits & 4) != 0 )
                      {
                        std::wstring::wstring(v116);
                        v13 |= 4u;
                        LODWORD(v96) = v13;
                        v87 = (_QWORD *)WideStringToUtf8String(v118, v116);
                        LOBYTE(v13) = v13 | 8;
                        if ( v87[3] > 0xFu )
                          v87 = (_QWORD *)*v87;
                        McTemplateU0sq_EventWriteTransfer(v88, UploadFailed, v87, v80);
                      }
                      if ( (v13 & 8) != 0 )
                      {
                        LOBYTE(v13) = v13 & 0xF7;
                        std::string::_Tidy_deallocate(v118);
                      }
                      if ( (v13 & 4) != 0 )
                        std::wstring::~wstring(v116);
                    }
                  }
                  v107 = 0;
                  p_pv = (unsigned __int64)&v107;
                  v105 = 0;
                  v106 = 1;
                  v63 = Windows::Internal::Storage::Cloud::CloudStore::CloudStoreData_OldCreateInstance(
                          (Windows::Internal::Storage::Cloud::CloudStore *)a1,
                          v113,
                          v57,
                          string,
                          v99,
                          v39,
                          &v105);
                  if ( v106 )
                    wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
                      p_pv,
                      v105);
                  if ( v63 >= 0 )
                  {
                    v75 = v107;
                    v76 = (Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)operator new(
                                                                                       0x50u,
                                                                                       (const struct std::nothrow_t *)std::nothrow);
                    if ( v76
                      && (v83 = Windows::Internal::Storage::Cloud::CloudStoreSaveResult::CloudStoreSaveResult(v76, v75)) != 0 )
                    {
                      *v114 = v83;
                      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
                        v119,
                        0);
                      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::Stop(
                        (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119,
                        byte_1802299F5,
                        v39,
                        &GUID_NULL,
                        1);
                      if ( v107 )
                        (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreData *))(*(_QWORD *)v107 + 16LL))(v107);
                      v84 = v99;
                      if ( v99 )
                      {
                        v99 = 0;
                        (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v84 + 16LL))(v84);
                      }
                      WindowsDeleteString(v98);
                      v98 = 0;
                      WindowsDeleteString(v97);
                      v97 = 0;
                      v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
                      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
                      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
                      if ( hObject != (HANDLE)-1LL )
                        wil::details::RevertImpersonateToken(hObject, v85);
                      return 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x57A,
                        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                        (const char *)0x8007000ELL,
                        v94);
                      if ( v107 )
                        (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreData *))(*(_QWORD *)v107 + 16LL))(v107);
                      v77 = v99;
                      if ( v99 )
                      {
                        v99 = 0;
                        (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v77 + 16LL))(v77);
                      }
                      WindowsDeleteString(v98);
                      v98 = 0;
                      WindowsDeleteString(v97);
                      v97 = 0;
                      v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
                      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
                      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
                      if ( hObject != (HANDLE)-1LL )
                        wil::details::RevertImpersonateToken(hObject, v78);
                      return 2147942414LL;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x578,
                      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                      (const char *)(unsigned int)v63,
                      v94);
                    if ( v107 )
                      (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreData *))(*(_QWORD *)v107 + 16LL))(v107);
                    v64 = v99;
                    if ( v99 )
                    {
                      v99 = 0;
                      (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v64 + 16LL))(v64);
                    }
                    WindowsDeleteString(v98);
                    v98 = 0;
                    WindowsDeleteString(v97);
                    v97 = 0;
                    v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
                    wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
                    wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
                    if ( hObject != (HANDLE)-1LL )
                      wil::details::RevertImpersonateToken(hObject, v65);
                    return (unsigned int)v63;
                  }
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x557,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                  (const char *)(unsigned int)RootFromAttribute,
                  v92);
                if ( pv )
                  CoTaskMemFree(pv);
                if ( a1 != -344 )
                  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 344));
                v49 = v99;
                if ( v99 )
                {
                  v99 = 0;
                  (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v49 + 16LL))(v49);
                }
                WindowsDeleteString(v98);
                v98 = 0;
                WindowsDeleteString(v97);
                v97 = 0;
                v119[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable';
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v119);
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v119);
                if ( hObject != (HANDLE)-1LL )
                  wil::details::RevertImpersonateToken(hObject, v50);
                return (unsigned int)RootFromAttribute;
              }
            }
            for ( i = 0; i < 4; ++i )
            {
              if ( v111[i] != *((_BYTE *)&qword_18022A7F0 + i) )
                goto LABEL_117;
            }
          }
          v47 = 0;
          goto LABEL_36;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1115,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v34,
          v92);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52D,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)v30,
      v95);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v108);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
    WindowsDeleteString(v98);
    v98 = 0;
    WindowsDeleteString(v97);
    v97 = 0;
    Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::~SaveActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity *)v119);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
    result = v30;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x57F,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v51);
  }
  return result;
}

```

## disassembly

```asm
0x1800608ac  push    rbx
0x1800608ae  push    rsi
0x1800608af  push    rdi
0x1800608b0  push    r12
0x1800608b2  push    r13
0x1800608b4  push    r14
0x1800608b6  push    r15
0x1800608b8  sub     rsp, 300h
0x1800608bf  mov     rax, cs:__security_cookie
0x1800608c6  xor     rax, rsp
0x1800608c9  mov     [rsp+338h+var_48], rax
0x1800608d1  mov     rdi, r9
0x1800608d4  mov     [rsp+338h+var_260], r9
0x1800608dc  mov     [rsp+338h+var_258], r8
0x1800608e4  mov     [rsp+338h+var_2B0], edx
0x1800608eb  mov     r15, rcx
0x1800608ee  mov     rbx, [rsp+338h+arg_38]
0x1800608f6  mov     [rsp+338h+var_270], rbx
0x1800608fe  mov     rax, [rsp+338h+arg_20]
0x180060906  mov     [rsp+338h+string], rax
0x18006090e  mov     r12, [rsp+338h+arg_48]
0x180060916  mov     rsi, [rsp+338h+arg_50]
0x18006091e  mov     [rsp+338h+var_250], rsi
0x180060926  xor     r14d, r14d
0x180060929  mov     dword ptr [rsp+338h+var_2D8], r14d
0x18006092e  mov     rdx, r9; HSTRING
0x180060931  call    ?ShouldUseActivityFeedForSync@CloudStore@Cloud@Storage@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(HSTRING__ *)
0x180060936  mov     rcx, [rsp+338h]; this
0x18006093e  test    al, al
0x180060940  jnz     loc_1800613E2
0x180060946  mov     [rsi], r14
0x180060949  lea     rcx, [r15+0C8h]
0x180060950  lea     rdx, [rsp+338h+hObject]
0x180060958  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18006095d  nop
0x18006095e  mov     rcx, r12; this
0x180060961  call    ?GetBufferSizeForTelemetry@CloudStoreUtilities@@YAIPEAUIBuffer@Streams@Storage@Windows@@@Z; CloudStoreUtilities::GetBufferSizeForTelemetry(Windows::Storage::Streams::IBuffer *)
0x180060966  mov     dword ptr [rsp+338h+var_2D8], eax
0x18006096a  mov     rcx, rbx; this
0x18006096d  call    ?GetBufferSizeForTelemetry@CloudStoreUtilities@@YAIPEAUIBuffer@Streams@Storage@Windows@@@Z; CloudStoreUtilities::GetBufferSizeForTelemetry(Windows::Storage::Streams::IBuffer *)
0x180060972  mov     r13d, eax
0x180060975  xor     edx, edx; length
0x180060977  mov     rcx, rdi; string
0x18006097a  call    cs:__imp_WindowsGetStringRawBuffer
0x180060980  mov     rsi, rax
0x180060983  xor     edx, edx; length
0x180060985  mov     rcx, [rsp+338h+string]; string
0x18006098d  call    cs:__imp_WindowsGetStringRawBuffer
0x180060993  mov     rdi, rax
0x180060996  xor     edx, edx; length
0x180060998  mov     rcx, [rsp+338h+var_258]; string
0x1800609a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800609a6  mov     rbx, rax
0x1800609a9  lea     rdx, aSaveactivity; "SaveActivity"
0x1800609b0  lea     rcx, [rsp+338h+var_1F8]
0x1800609b8  call    ??0?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800609bd  lea     rax, ??_7SaveActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable'
0x1800609c4  mov     [rsp+338h+var_1F8], rax
0x1800609cc  mov     eax, dword ptr [rsp+338h+var_2D8]
0x1800609d0  mov     [rsp+338h+var_2E0], eax; unsigned int
0x1800609d4  mov     rax, [rsp+338h+arg_40]
0x1800609dc  mov     [rsp+338h+var_2E8], rax; unsigned __int64
0x1800609e1  mov     dword ptr [rsp+338h+var_2F0], r13d; unsigned int
0x1800609e6  mov     rax, [rsp+338h+arg_30]
0x1800609ee  mov     [rsp+338h+var_2F8], rax; unsigned __int64
0x1800609f3  mov     r13d, [rsp+338h+arg_28]
0x1800609fb  mov     dword ptr [rsp+338h+var_300], r13d; unsigned int
0x180060a00  mov     [rsp+338h+var_308], rsi; unsigned __int16 *
0x180060a05  mov     [rsp+338h+var_310], rdi; unsigned __int16 *
0x180060a0a  lea     rax, LocaleName
0x180060a11  mov     [rsp+338h+var_318], rax; unsigned __int16 *
0x180060a16  mov     r9, rbx; unsigned __int16 *
0x180060a19  mov     ebx, [rsp+338h+var_2B0]
0x180060a20  mov     r8d, ebx; unsigned int
0x180060a23  lea     rdx, byte_1802299F5; char *
0x180060a2a  lea     rcx, [rsp+338h+var_1F8]; this
0x180060a32  call    ?StartActivity@SaveActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBDIPEBG111I_KI2I@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::StartActivity(char const *,uint,ushort const *,ushort const *,ushort const *,ushort const *,uint,unsigned __int64,uint,unsigned __int64,uint)
0x180060a37  nop
0x180060a38  mov     eax, r13d
0x180060a3b  xor     edi, edi
0x180060a3d  and     eax, 7
0x180060a40  mov     [rsp+338h+var_2AC], eax
0x180060a47  jz      loc_1800613DA
0x180060a4d  mov     ecx, eax
0x180060a4f  test    eax, eax
0x180060a51  jz      short loc_180060A5F
0x180060a53  dec     rax
0x180060a56  test    rcx, rax
0x180060a59  jz      loc_1800613DA
0x180060a5f  mov     al, 1
0x180060a61  mov     rcx, [rsp+338h]; this
0x180060a69  test    al, al
0x180060a6b  jnz     loc_1800613F4
0x180060a71  mov     [rsp+338h+var_2D0], rdi
0x180060a76  xor     ecx, ecx; string
0x180060a78  call    cs:__imp_WindowsDeleteString
0x180060a7e  mov     [rsp+338h+var_2D0], rdi
0x180060a83  lea     rax, [rsp+338h+var_2D0]
0x180060a88  mov     [rsp+338h+var_318], rax; int
0x180060a8d  mov     r9b, 1
0x180060a90  mov     r8, [rsp+338h+var_258]
0x180060a98  mov     edx, ebx
0x180060a9a  mov     rcx, r15
0x180060a9d  call    ?GetEffectivePartition@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@_NPEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,bool,HSTRING__ * *)
0x180060aa2  mov     ebx, eax
0x180060aa4  test    eax, eax
0x180060aa6  js      loc_180061823
0x180060aac  xorps   xmm0, xmm0
0x180060aaf  movups  [rsp+338h+var_248], xmm0
0x180060ab7  mov     [rsp+338h+var_2A0], rdi
0x180060abf  mov     [rsp+338h+var_2C8], rdi
0x180060ac4  mov     [rsp+338h+var_2C0], rdi
0x180060ac9  lea     rsi, [r15+158h]
0x180060ad0  mov     rcx, rsi; SRWLock
0x180060ad3  call    cs:__imp_AcquireSRWLockExclusive
0x180060ad9  mov     [rsp+338h+var_280], rsi
0x180060ae1  mov     rcx, [rsp+338h+var_2C8]; string
0x180060ae6  call    cs:__imp_WindowsDeleteString
0x180060aec  mov     r13, [rsp+338h+var_2D0]
0x180060af1  mov     [rsp+338h+var_2C8], rdi
0x180060af6  mov     rcx, r15; this
0x180060af9  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x180060afe  mov     ebx, eax
0x180060b00  test    eax, eax
0x180060b02  js      loc_180061872
0x180060b08  mov     [rsp+338h+var_2D8], rdi
0x180060b0d  mov     rdi, [r15+1E0h]
0x180060b14  mov     rax, [rdi]
0x180060b17  mov     rbx, [rax]
0x180060b1a  lea     rcx, [rsp+338h+var_2D8]
0x180060b1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060b24  lea     r8, [rsp+338h+var_2D8]
0x180060b29  lea     rdx, _GUID_3f14a274_31fe_4e07_b3fb_6830cde1bfe0
0x180060b30  mov     rcx, rdi
0x180060b33  mov     rax, rbx
0x180060b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b3b  mov     ebx, eax
0x180060b3d  xor     edi, edi
0x180060b3f  test    eax, eax
0x180060b41  js      loc_180061235
0x180060b47  mov     rcx, [rsp+338h+var_2D8]
0x180060b4c  mov     rax, [rcx]
0x180060b4f  lea     rdx, [rsp+338h+var_2C8]
0x180060b54  mov     [rsp+338h+var_310], rdx
0x180060b59  mov     rdx, [rsp+338h+string]
0x180060b61  mov     [rsp+338h+var_318], rdx; int
0x180060b66  mov     r9, [rsp+338h+var_260]
0x180060b6e  mov     r8, r13
0x180060b71  mov     edx, [rsp+338h+var_2B0]
0x180060b78  mov     rax, [rax+30h]
0x180060b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b81  mov     ebx, eax
0x180060b83  test    eax, eax
0x180060b85  js      loc_180061893
0x180060b8b  mov     rcx, [rsp+338h+var_2D8]
0x180060b90  test    rcx, rcx
0x180060b93  jz      short loc_180060BA7
0x180060b95  mov     [rsp+338h+var_2D8], rdi
0x180060b9a  mov     rax, [rcx]
0x180060b9d  mov     rax, [rax+10h]
0x180060ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ba6  nop
0x180060ba7  xor     edx, edx; length
0x180060ba9  mov     rcx, [rsp+338h+var_2C8]; string
0x180060bae  call    cs:__imp_WindowsGetStringRawBuffer
0x180060bb4  mov     r13, rax
0x180060bb7  mov     rcx, r12; struct Windows::Storage::Streams::IBuffer *
0x180060bba  call    ?IsValidBuffer@@YA_NPEAUIBuffer@Streams@Storage@Windows@@@Z; IsValidBuffer(Windows::Storage::Streams::IBuffer *)
0x180060bbf  mov     rcx, [rsp+338h]; this
0x180060bc7  test    al, al
0x180060bc9  jz      loc_180061406
0x180060bcf  mov     ebx, [rsp+338h+arg_28]
0x180060bd6  test    bl, 10h
0x180060bd9  jz      loc_180061780
0x180060bdf  mov     al, dil
0x180060be2  mov     rcx, [rsp+338h]; this
0x180060bea  test    al, al
0x180060bec  jnz     loc_1800618BF
0x180060bf2  mov     rcx, [rsp+338h]; this
0x180060bfa  mov     rdi, [rsp+338h+arg_40]
0x180060c02  test    rdi, rdi
0x180060c05  jz      loc_180061418
0x180060c0b  test    bl, 8
0x180060c0e  jz      loc_180061169
0x180060c14  mov     rcx, [rsp+338h]; this
0x180060c1c  xor     edi, edi
0x180060c1e  cmp     [rsp+338h+var_270], rdi
0x180060c26  jnz     loc_18006143C
0x180060c2c  mov     rcx, [rsp+338h]; this
0x180060c34  cmp     [rsp+338h+arg_30], rdi
0x180060c3c  jnz     loc_18006144E
0x180060c42  cmp     [rsp+338h+var_2C0], r12
0x180060c47  jnz     loc_1800618D7
0x180060c4d  mov     r12, [rsp+338h+arg_40]
0x180060c55  mov     rcx, r15; this
0x180060c58  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x180060c5d  mov     ebx, eax
0x180060c5f  test    eax, eax
0x180060c61  js      loc_180061986
0x180060c67  mov     rcx, [r15+1E0h]
0x180060c6e  mov     rax, [rcx]
0x180060c71  lea     r8, [rsp+338h+var_248]
0x180060c79  mov     rdx, r13
0x180060c7c  mov     rax, [rax+20h]
0x180060c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c85  mov     ebx, eax
0x180060c87  test    eax, eax
0x180060c89  js      loc_1800612E6
0x180060c8f  mov     ebx, edi
0x180060c91  test    ebx, ebx
0x180060c93  js      loc_18006132E
0x180060c99  mov     [rsp+338h+var_268], rdi
0x180060ca1  mov     dword ptr [rsp+338h+var_2D8], edi
0x180060ca5  lea     r8, [rsp+338h+var_2D8]; unsigned int *
0x180060caa  lea     rdx, [rsp+338h+var_268]; unsigned __int8 **
0x180060cb2  mov     rcx, [rsp+338h+var_2C0]; struct Windows::Storage::Streams::IBuffer *
0x180060cb7  call    ?GetBufferBytesNoCopyIfPossible@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAPEAEPEAI@Z; GetBufferBytesNoCopyIfPossible(Windows::Storage::Streams::IBuffer *,uchar * *,uint *)
0x180060cbc  mov     ebx, eax
0x180060cbe  test    eax, eax
0x180060cc0  js      loc_180061990
0x180060cc6  mov     edi, dword ptr [rsp+338h+var_2D8]
0x180060cca  mov     eax, edi
0x180060ccc  test    edi, edi
0x180060cce  jz      short loc_180060D02
0x180060cd0  cmp     rax, 4
0x180060cd4  jb      loc_1800615D0
0x180060cda  xor     ecx, ecx
0x180060cdc  mov     rdx, [rsp+338h+var_268]
0x180060ce4  cmp     rcx, 4
0x180060ce8  jnb     short loc_180060D02
0x180060cea  lea     rax, qword_18022A7F0
0x180060cf1  mov     al, [rcx+rax]
0x180060cf4  cmp     [rcx+rdx], al
0x180060cf7  jnz     loc_1800615D0
0x180060cfd  inc     rcx
0x180060d00  jmp     short loc_180060CE4
0x180060d02  xor     al, al
0x180060d04  mov     rcx, [rsp+338h]; this
0x180060d0c  test    al, al
0x180060d0e  jnz     loc_18006142A
0x180060d14  mov     [rsp+338h+pv], 0
0x180060d20  lea     rax, [rsp+338h+pv]
0x180060d28  mov     [rsp+338h+var_2A0], rax
0x180060d30  mov     [rsp+338h+var_298], 0
0x180060d3c  mov     [rsp+338h+var_290], 1
0x180060d44  lea     rcx, [r15+0E8h]
0x180060d4b  lea     r9, [rsp+338h+var_298]
0x180060d53  mov     edx, dword ptr [rsp+338h+var_248]
0x180060d5a  call    ?GetRootFromAttribute@CloudStoreUtilities@@YAJAEBVEffectiveWebAccountContext@@W4ScopeValue@@W4TRIBIT@@PEAPEAG@Z; CloudStoreUtilities::GetRootFromAttribute(EffectiveWebAccountContext const &,ScopeValue,TRIBIT,ushort * *)
0x180060d5f  mov     ebx, eax
0x180060d61  lea     rcx, [rsp+338h+var_2A0]
0x180060d69  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060d6e  test    ebx, ebx
0x180060d70  jns     loc_180060E4D
0x180060d76  mov     rcx, [rsp+338h]; this
0x180060d7e  mov     r9d, ebx; char *
0x180060d81  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180060d88  mov     edx, 557h; void *
0x180060d8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060d92  nop
0x180060d93  mov     rcx, [rsp+338h+pv]; pv
0x180060d9b  xor     edi, edi
0x180060d9d  test    rcx, rcx
0x180060da0  jnz     loc_180061315
0x180060da6  test    rsi, rsi
0x180060da9  jnz     loc_180061307
0x180060daf  mov     rcx, [rsp+338h+var_2C0]
0x180060db4  test    rcx, rcx
0x180060db7  jz      short loc_180060DCB
0x180060db9  mov     [rsp+338h+var_2C0], rdi
0x180060dbe  mov     rax, [rcx]
0x180060dc1  mov     rax, [rax+10h]
0x180060dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dca  nop
0x180060dcb  mov     rcx, [rsp+338h+var_2C8]; string
0x180060dd0  call    cs:__imp_WindowsDeleteString
0x180060dd6  mov     [rsp+338h+var_2C8], rdi
0x180060ddb  mov     rcx, [rsp+338h+var_2D0]; string
0x180060de0  call    cs:__imp_WindowsDeleteString
0x180060de6  mov     [rsp+338h+var_2D0], rdi
0x180060deb  lea     rax, ??_7SaveActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity::`vftable'
0x180060df2  mov     [rsp+338h+var_1F8], rax
0x180060dfa  lea     rcx, [rsp+338h+var_1F8]
0x180060e02  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180060e07  lea     rcx, [rsp+338h+var_1F8]
0x180060e0f  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180060e14  nop
0x180060e15  mov     rcx, [rsp+338h+hObject]; hObject
0x180060e1d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180060e21  jz      short loc_180060E28
0x180060e23  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180060e28  mov     eax, ebx
0x180060e2a  mov     rcx, [rsp+338h+var_48]
0x180060e32  xor     rcx, rsp; StackCookie
0x180060e35  call    __security_check_cookie
0x180060e3a  add     rsp, 300h
0x180060e41  pop     r15
0x180060e43  pop     r14
0x180060e45  pop     r13
0x180060e47  pop     r12
  ... truncated ...
```
