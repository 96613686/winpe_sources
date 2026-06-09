# Container::Manager::Core::Details::ResourceOperation::ExecuteFirstBootOperationsIfNeeded(Container::Manager::Core::Details::ContainerStorage *,utl::optional<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &)

- ea: `0x180059154`
- end: `0x180059f8f`
- name: `?ExecuteFirstBootOperationsIfNeeded@ResourceOperation@Details@Core@Manager@Container@@AEAAJPEAVContainerStorage@2345@AEAV?$optional@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@Z`
- size: `3643`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005dea4`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180005704`
- `0x1800069cf`
- `0x180007b48`
- `0x18000a10c`
- `0x18000da88`
- `0x18002bd50`
- `0x1800393cc`
- `0x18003d360`
- `0x18003db9c`
- `0x18003dbf8`
- `0x18003e50c`
- `0x18003e9f4`
- `0x18003eb28`
- `0x18003f7d8`
- `0x1800471dc`
- `0x180049918`
- `0x180049a0c`
- `0x18004e794`
- `0x18004feb4`
- `0x18005648c`
- `0x180059154`
- `0x18005a378`
- `0x18005bee8`
- `0x18008496c`
- `0x1800cb554`
- `0x1800dab74`
- `0x1800e388c`
- `0x1800e3ca8`
- `0x1800e4400`
- `0x1800e6bc0`
- `0x1800f171c`
- `0x1800f1ae8`
- `0x1800f1ea4`
- `0x1800f2ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800592ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800598b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800599bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ab2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059df2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800592ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800598b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800599bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ab2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059df2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059292`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800592ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005987a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059b57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059d26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059292`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800592ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005987a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059b57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059d26`

## string_xrefs

- `0x180059267`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800593da`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800595a4`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800595fe`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800596a1`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800597d5`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005989e`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800599a4`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059ae7`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059bde`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059c03`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059cdd`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059d45`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180059e2a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ResourceOperation::ExecuteFirstBootOperationsIfNeeded(
        __int64 a1,
        Container::Manager::Core::ResourceHandle *a2,
        __int64 a3)
{
  const struct Container::Manager::Core::Details::Layer *LeafLayerRecurse; // rax
  const struct Container::Manager::Core::Details::Layer *v7; // rsi
  bool v8; // r13
  int IsEdgeVersionCurrent; // ebx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  char v14; // r15
  const void *v15; // rax
  Container::Manager::Core::ResourceHandle *v16; // r14
  Container::Manager::Core::ResourceHandle *v17; // rax
  Container::Manager::Core::ResourceHandle *v18; // r14
  int Guid; // eax
  struct _GUID *v20; // rdx
  __int64 v21; // rdx
  GUID v22; // xmm6
  char v23; // r11
  int Resource; // eax
  bool v25; // zf
  __int64 v26; // rax
  int v27; // eax
  int v28; // esi
  void *v29; // rbx
  int *v30; // rbx
  void *v31; // rsi
  Container::Manager::Core::Details::SysprepOperation *v32; // rax
  Container::Manager::Core::Details::SysprepOperation *v33; // rsi
  int v34; // eax
  int v35; // r15d
  void *v36; // rbx
  const char *v37; // r9
  void *v38; // r15
  int v39; // ecx
  __int64 v40; // rdx
  int v41; // eax
  void *v42; // rbx
  void *v43; // rbx
  Container::Manager::Core::Details::SysprepOperation *v44; // rbx
  int *v45; // rbx
  void *v46; // rsi
  Container::Manager::Core::Details::SysprepOperation *v47; // rbx
  Container::Manager::Core::Details::FirstBootOperation *v48; // rsi
  void *v49; // rsi
  int v50; // eax
  const char *v51; // r9
  __int64 v52; // r9
  __int64 v53; // rdx
  int v54; // ecx
  __int64 v55; // rdx
  int v56; // eax
  Container::Manager::Core::Details::FirstBootOperation *v57; // rbx
  int *v58; // rbx
  Container::Manager::Core::ResourceHandle *v59; // rbx
  Container::Manager::Core::ResourceHandle *v60; // rbx
  int v61; // [rsp+28h] [rbp-E0h]
  int v62; // [rsp+28h] [rbp-E0h]
  char v63; // [rsp+48h] [rbp-C0h] BYREF
  void *v64[2]; // [rsp+50h] [rbp-B8h] BYREF
  utl::_RefCountBase *v65; // [rsp+60h] [rbp-A8h]
  Container::Manager::Core::ResourceHandle *Buf2; // [rsp+68h] [rbp-A0h] BYREF
  void *Buf2_8[2]; // [rsp+70h] [rbp-98h] BYREF
  utl::_RefCountBase *v68; // [rsp+80h] [rbp-88h]
  Container::Manager::Core::Details::FirstBootOperation *v69[2]; // [rsp+88h] [rbp-80h] BYREF
  _DWORD v70[2]; // [rsp+98h] [rbp-70h] BYREF
  GUID v71; // [rsp+A0h] [rbp-68h]
  __int64 v72; // [rsp+B0h] [rbp-58h]
  __int128 v73; // [rsp+B8h] [rbp-50h]
  void *v74[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v75; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v76; // [rsp+E8h] [rbp-20h]
  __int128 v77; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v78; // [rsp+108h] [rbp+0h] BYREF
  int v79; // [rsp+118h] [rbp+10h]
  int v80; // [rsp+11Ch] [rbp+14h]
  __int128 v81; // [rsp+120h] [rbp+18h]
  int v82; // [rsp+130h] [rbp+28h]
  __int64 v83; // [rsp+138h] [rbp+30h]
  _DWORD v84[2]; // [rsp+140h] [rbp+38h] BYREF
  GUID v85; // [rsp+148h] [rbp+40h]
  __int64 v86; // [rsp+158h] [rbp+50h]
  __int64 v87; // [rsp+160h] [rbp+58h]
  char v88; // [rsp+168h] [rbp+60h]
  int v89; // [rsp+169h] [rbp+61h]
  __int16 v90; // [rsp+16Dh] [rbp+65h]
  char v91; // [rsp+16Fh] [rbp+67h]
  char v92[40]; // [rsp+170h] [rbp+68h] BYREF
  char v93; // [rsp+198h] [rbp+90h]
  _BYTE v94[304]; // [rsp+1A0h] [rbp+98h] BYREF
  __int128 v95; // [rsp+2D0h] [rbp+1C8h]
  __int128 v96; // [rsp+2E0h] [rbp+1D8h]
  _OWORD v97[2]; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int128 v98; // [rsp+310h] [rbp+208h]
  __int128 v99; // [rsp+320h] [rbp+218h]
  __int128 v100; // [rsp+330h] [rbp+228h]
  wil::details::in1diag3 *retaddr; // [rsp+3A0h] [rbp+298h]

  Buf2 = a2;
  LeafLayerRecurse = Container::Manager::Core::Details::Resource::GetLeafLayerRecurse(*(const struct Container::Manager::Core::Details::Resource **)a1);
  v7 = LeafLayerRecurse;
  v8 = 0;
  if ( !*(_BYTE *)(a1 + 288) )
    __int2c();
  if ( *((_DWORD *)a2 + 4) != 2 )
    goto LABEL_168;
  v63 = 1;
  if ( *((_BYTE *)LeafLayerRecurse + 680) )
  {
    if ( (*((_BYTE *)LeafLayerRecurse + 228) & 8) != 0 )
    {
      IsEdgeVersionCurrent = Container::Manager::Core::Details::SpecializationLayer::IsEdgeVersionCurrent(
                               (const struct Container::Manager::Core::Details::Layer *)((char *)LeafLayerRecurse + 384),
                               (bool *)&v63);
      if ( IsEdgeVersionCurrent < 0 )
      {
        v10 = 1907;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)IsEdgeVersionCurrent,
          v61);
        v12 = 10286;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)IsEdgeVersionCurrent,
          v61);
        return (unsigned int)IsEdgeVersionCurrent;
      }
    }
  }
  if ( *((_BYTE *)v7 + 680) )
  {
    v11 = Container::Manager::Core::Details::Layer::RespecializeIfNeededInternal(v7);
    IsEdgeVersionCurrent = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v11,
        v61);
      v10 = 1910;
      goto LABEL_11;
    }
  }
  v14 = 0;
  AcquireSRWLockShared((PSRWLOCK)v7 + 34);
  v15 = (char *)v7 + 292;
  if ( v7 != (const struct Container::Manager::Core::Details::Layer *)-272LL )
  {
    ReleaseSRWLockShared((PSRWLOCK)v7 + 34);
    v15 = (char *)v7 + 292;
  }
  v16 = Buf2;
  if ( !memcmp_0(v15, Buf2, 0x10u) && *((_DWORD *)v7 + 56) )
    v14 = 1;
  AcquireSRWLockShared((PSRWLOCK)v7 + 34);
  if ( v7 != (const struct Container::Manager::Core::Details::Layer *)-272LL )
    ReleaseSRWLockShared((PSRWLOCK)v7 + 34);
  if ( !memcmp_0((char *)v7 + 292, v16, 0x10u) )
    v8 = *((_DWORD *)v7 + 33) != 0;
  if ( v14 || v8 )
  {
    v17 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      IsEdgeVersionCurrent = -2147024882;
      v12 = 10313;
      goto LABEL_12;
    }
    *(_QWORD *)v17 = (char *)v17 + 16;
    *((_QWORD *)v17 + 1) = (char *)v17 + 16;
    *((_WORD *)v17 + 8) = 0;
    *((_DWORD *)v17 + 8) = 0;
    *((_QWORD *)v17 + 5) = 0;
    *((_QWORD *)v17 + 8) = 0;
    *((_QWORD *)v17 + 9) = 0;
    *((_BYTE *)v17 + 80) = 0;
    *((_QWORD *)v17 + 6) = 0;
    *((_QWORD *)v17 + 7) = 0;
    Buf2 = v17;
    v69[0] = (Container::Manager::Core::Details::FirstBootOperation *)L"ResourceOperation_MaterializeStorage_FirstBoot";
    v69[1] = (Container::Manager::Core::Details::FirstBootOperation *)46;
    Guid = Container::Manager::Core::ResourceHandle::Initialize(v17, v69);
    IsEdgeVersionCurrent = Guid;
    if ( Guid < 0 )
    {
      v21 = 10316;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)Guid,
        v61);
LABEL_124:
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v18);
      operator delete(v18, (const struct std::nothrow_t *)0x58);
      return (unsigned int)IsEdgeVersionCurrent;
    }
    v77 = 0;
    Guid = Csl::CreateGuid((Csl *)&v77, v20);
    IsEdgeVersionCurrent = Guid;
    if ( Guid < 0 )
    {
      v21 = 10320;
      goto LABEL_30;
    }
    v70[0] = 0;
    v71 = GUID_NULL;
    v73 = 0;
    LOBYTE(v73) = 0;
    BYTE8(v73) = 0;
    *(_OWORD *)v74 = 0;
    v75 = 0;
    LOBYTE(v74[0]) = 0;
    v76 = 0;
    LODWORD(v72) = 1;
    BYTE4(v72) = 1;
    *(_WORD *)((char *)&v72 + 5) = *(_WORD *)((char *)&Buf2 + 5);
    HIBYTE(v72) = HIBYTE(Buf2);
    v70[1] = 2;
    v22 = *(GUID *)v7;
    v71 = *(GUID *)v7;
    v70[0] = 2;
    v81 = 0;
    LOBYTE(v81) = 0;
    v82 = 0;
    v83 = 0;
    memset_0(v84, 0, 0x60u);
    LOBYTE(v84[0]) = 0;
    v93 = 0;
    memset_0(v94, 0, sizeof(v94));
    v94[0] = 0;
    v94[296] = 0;
    v95 = 0;
    v96 = 0;
    LOBYTE(v95) = 0;
    BYTE12(v96) = 0;
    memset(v97, 0, 28);
    LOBYTE(v97[0]) = 0;
    BYTE8(v97[1]) = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    LOBYTE(v98) = 0;
    BYTE8(v100) = 0;
    v78 = v77;
    v79 = 1;
    v80 = 1;
    if ( v93 )
    {
      v84[0] = 2;
      v84[1] = 2;
      v85 = v22;
      v86 = v72;
      v87 = v73;
      v88 = 0;
      v89 = *(_DWORD *)((char *)&v73 + 9);
      v90 = *(_WORD *)((char *)&v73 + 13);
      v91 = HIBYTE(v73);
      utl::optional<Csl::Path>::operator=(v92, v74);
    }
    else
    {
      Container::Manager::Core::Details::ContainerStorageConfiguration::ContainerStorageConfiguration(v84, v70);
      v93 = v23;
    }
    Resource = Container::Manager::Core::Details::ResourceBroker::CreateResource(*(Container::Manager::Core::Details::ResourceBroker **)(a1 + 168));
    IsEdgeVersionCurrent = Resource;
    if ( Resource < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2864,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)Resource,
        v61);
      Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
      v25 = (_BYTE)v76 == 0;
      goto LABEL_121;
    }
    v26 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(v18);
    *(_OWORD *)v64 = 0;
    v65 = 0;
    v27 = Container::Manager::Core::Details::ContainerStorage::MaterializeAsync(v26, v64);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x286A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v27,
        v61);
      Csl::AsyncOperation<void>::Cleanup(v64);
      if ( v65 )
        utl::_RefCountBase::_DecStrong(v65);
      v29 = v64[0];
      if ( v64[0] )
      {
        Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v64[0]);
        operator delete(v29, (const struct std::nothrow_t *)0x30);
      }
      Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
      if ( (_BYTE)v76 && v74[0] != &v75 )
        operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
      IsEdgeVersionCurrent = v28;
      goto LABEL_124;
    }
    v30 = (int *)v64[1];
    if ( !(unsigned __int8)wil::slim_event_t<1>::wait((char *)v64[1] + 4) )
    {
      IsEdgeVersionCurrent = -2147023436;
      goto LABEL_48;
    }
    IsEdgeVersionCurrent = *v30;
    if ( IsEdgeVersionCurrent < 0 )
    {
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x286C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)IsEdgeVersionCurrent,
        v61);
      Csl::AsyncOperation<void>::Cleanup(v64);
      if ( v65 )
        utl::_RefCountBase::_DecStrong(v65);
      v31 = v64[0];
      if ( !v64[0] )
        goto LABEL_120;
LABEL_51:
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v64[0]);
      operator delete(v31, (const struct std::nothrow_t *)0x30);
LABEL_120:
      Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
      v25 = (_BYTE)v76 == 0;
      goto LABEL_121;
    }
    if ( v14 )
    {
      v32 = (Container::Manager::Core::Details::SysprepOperation *)operator new(
                                                                     0x1C8u,
                                                                     (const struct std::nothrow_t *)&std::nothrow);
      v33 = v32;
      if ( !v32 )
      {
        IsEdgeVersionCurrent = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2872,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)0x8007000ELL,
          v61);
        Csl::AsyncOperation<void>::Cleanup(v64);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        v49 = v64[0];
        if ( v64[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v64[0]);
          operator delete(v49, (const struct std::nothrow_t *)0x30);
        }
        goto LABEL_120;
      }
      *(_BYTE *)v32 = 0;
      *((_DWORD *)v32 + 1) = 0;
      *((_QWORD *)v32 + 1) = 0;
      *((_QWORD *)v32 + 2) = 0;
      *((_QWORD *)v32 + 3) = 0;
      *((_QWORD *)v32 + 4) = 0;
      *((_QWORD *)v32 + 5) = 0;
      *((_QWORD *)v32 + 6) = 0;
      *((_QWORD *)v32 + 7) = 0;
      *((_QWORD *)v32 + 8) = 0;
      *((_QWORD *)v32 + 9) = 0;
      *((_QWORD *)v32 + 10) = 0;
      *((_QWORD *)v32 + 11) = 0;
      *((_QWORD *)v32 + 12) = 0;
      *((_QWORD *)v32 + 13) = 0;
      *((_QWORD *)v32 + 14) = 0;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        (char *)v32 + 120,
        "SysprepOperation");
      *((_QWORD *)v33 + 15) = &CmTraceProvider::SysprepOperation::`vftable';
      v61 = a1 + 240;
      v34 = Container::Manager::Core::Details::SysprepOperation::Initialize(v33, v18, a1 + 192, a1 + 176);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2879,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)v34,
          v61);
        Container::Manager::Core::Details::SysprepOperation::~SysprepOperation(v33);
        operator delete(v33, (const struct std::nothrow_t *)0x1C8);
        Csl::AsyncOperation<void>::Cleanup(v64);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        v36 = v64[0];
        if ( v64[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v64[0]);
          operator delete(v36, (const struct std::nothrow_t *)0x30);
        }
        Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
        if ( (_BYTE)v76 && v74[0] != &v75 )
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        IsEdgeVersionCurrent = v35;
        goto LABEL_124;
      }
      *(_OWORD *)Buf2_8 = 0;
      v68 = 0;
      AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
      if ( *(_BYTE *)(a1 + 69) )
      {
        IsEdgeVersionCurrent = -2147023673;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2884,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)0x800704C7LL,
          v61);
        if ( a1 != -48 )
          ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
        Csl::AsyncOperation<void>::Cleanup(Buf2_8);
        if ( v68 )
          utl::_RefCountBase::_DecStrong(v68);
        v38 = Buf2_8[0];
        if ( Buf2_8[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)Buf2_8[0]);
          operator delete(v38, (const struct std::nothrow_t *)0x30);
        }
        Container::Manager::Core::Details::SysprepOperation::~SysprepOperation(v33);
        operator delete(v33, (const struct std::nothrow_t *)0x1C8);
        Csl::AsyncOperation<void>::Cleanup(v64);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        goto LABEL_73;
      }
      v39 = *(_DWORD *)(a1 + 304);
      if ( !v39 || (v40 = 1, v39 != 1) )
        v40 = 0;
      if ( !*((_QWORD *)v33 + 5) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x17F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\sysprepoperation.cpp",
          v37);
      Container::Manager::Core::Details::ComputeSystemOperation::SetPriority(*((_QWORD *)v33 + 4), v40);
      v41 = Container::Manager::Core::Details::SysprepOperation::Start(v33, Buf2_8);
      LODWORD(v69[0]) = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x288B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)v41,
          v61);
        if ( a1 != -48 )
          ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
        Csl::AsyncOperation<void>::Cleanup(Buf2_8);
        if ( v68 )
          utl::_RefCountBase::_DecStrong(v68);
        v42 = Buf2_8[0];
        if ( Buf2_8[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)Buf2_8[0]);
          operator delete(v42, (const struct std::nothrow_t *)0x30);
        }
        Container::Manager::Core::Details::SysprepOperation::~SysprepOperation(v33);
        operator delete(v33, (const struct std::nothrow_t *)0x1C8);
        Csl::AsyncOperation<void>::Cleanup(v64);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        v43 = v64[0];
        if ( v64[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v64[0]);
          operator delete(v43, (const struct std::nothrow_t *)0x30);
        }
        Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
        if ( (_BYTE)v76 && v74[0] != &v75 )
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        IsEdgeVersionCurrent = (int)v69[0];
        goto LABEL_124;
      }
      v44 = *(Container::Manager::Core::Details::SysprepOperation **)(a1 + 256);
      *(_QWORD *)(a1 + 256) = v33;
      if ( v44 )
      {
        Container::Manager::Core::Details::SysprepOperation::~SysprepOperation(v44);
        operator delete(v44, (const struct std::nothrow_t *)0x1C8);
      }
      if ( a1 != -48 )
        ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
      v45 = (int *)Buf2_8[1];
      if ( !(unsigned __int8)wil::slim_event_t<1>::wait((char *)Buf2_8[1] + 4) )
      {
        IsEdgeVersionCurrent = -2147023436;
LABEL_101:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2891,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)IsEdgeVersionCurrent,
          v61);
        Csl::AsyncOperation<void>::Cleanup(Buf2_8);
        if ( v68 )
          utl::_RefCountBase::_DecStrong(v68);
        v46 = Buf2_8[0];
        if ( Buf2_8[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)Buf2_8[0]);
          operator delete(v46, (const struct std::nothrow_t *)0x30);
        }
        Csl::AsyncOperation<void>::Cleanup(v64);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
LABEL_73:
        v31 = v64[0];
        if ( !v64[0] )
          goto LABEL_120;
        goto LABEL_51;
      }
      IsEdgeVersionCurrent = *v45;
      if ( IsEdgeVersionCurrent < 0 )
        goto LABEL_101;
      AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
      v47 = *(Container::Manager::Core::Details::SysprepOperation **)(a1 + 256);
      *(_QWORD *)(a1 + 256) = 0;
      if ( v47 )
      {
        Container::Manager::Core::Details::SysprepOperation::~SysprepOperation(v47);
        operator delete(v47, (const struct std::nothrow_t *)0x1C8);
      }
      if ( a1 != -48 )
        ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
      Csl::AsyncOperation<void>::~AsyncOperation<void>(Buf2_8);
    }
    if ( v8 )
    {
      wil::make_unique_nothrow<Container::Manager::Core::Details::FirstBootOperation,>(v69);
      v48 = v69[0];
      if ( !v69[0] )
      {
        IsEdgeVersionCurrent = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A1,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)0x8007000ELL,
          v61);
LABEL_148:
        Csl::AsyncOperation<void>::~AsyncOperation<void>(v64);
        Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
        v25 = (_BYTE)v76 == 0;
LABEL_121:
        if ( !v25 && v74[0] != &v75 )
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_124;
      }
      v62 = a1 + 240;
      v50 = Container::Manager::Core::Details::FirstBootOperation::Initialize(v69[0], v18, a1 + 192, a1 + 176);
      IsEdgeVersionCurrent = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A8,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)v50,
          v62);
LABEL_127:
        if ( v48 )
        {
          Container::Manager::Core::Details::FirstBootOperation::~FirstBootOperation(v48);
          operator delete(v48, (const struct std::nothrow_t *)0x1D8);
        }
        goto LABEL_148;
      }
      *(_OWORD *)Buf2_8 = 0;
      v68 = 0;
      AcquireSRWLockShared((PSRWLOCK)(a1 + 48));
      if ( *(_BYTE *)(a1 + 69) )
      {
        IsEdgeVersionCurrent = -2147023673;
        v52 = 2147943623LL;
        v53 = 10419;
LABEL_131:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v53,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)v52,
          v62);
        if ( a1 != -48 )
          ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
        Csl::AsyncOperation<void>::~AsyncOperation<void>(Buf2_8);
        goto LABEL_127;
      }
      v54 = *(_DWORD *)(a1 + 304);
      if ( !v54 || (v55 = 1, v54 != 1) )
        v55 = 0;
      if ( !*((_QWORD *)v48 + 5) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\firstbootoperation.cpp",
          v51);
      Container::Manager::Core::Details::ComputeSystemOperation::SetPriority(*((_QWORD *)v48 + 4), v55);
      v56 = Container::Manager::Core::Details::FirstBootOperation::Start(v48, Buf2_8);
      IsEdgeVersionCurrent = v56;
      if ( v56 < 0 )
      {
        v52 = (unsigned int)v56;
        v53 = 10426;
        goto LABEL_131;
      }
      v57 = *(Container::Manager::Core::Details::FirstBootOperation **)(a1 + 264);
      *(_QWORD *)(a1 + 264) = v48;
      if ( v57 )
      {
        Container::Manager::Core::Details::FirstBootOperation::~FirstBootOperation(v57);
        operator delete(v57, (const struct std::nothrow_t *)0x1D8);
      }
      if ( a1 != -48 )
        ReleaseSRWLockShared((PSRWLOCK)(a1 + 48));
      v58 = (int *)Buf2_8[1];
      if ( !(unsigned __int8)wil::slim_event_t<1>::wait((char *)Buf2_8[1] + 4) )
      {
        IsEdgeVersionCurrent = -2147023436;
LABEL_147:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28C0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)IsEdgeVersionCurrent,
          v62);
        Csl::AsyncOperation<void>::~AsyncOperation<void>(Buf2_8);
        goto LABEL_148;
      }
      IsEdgeVersionCurrent = *v58;
      if ( IsEdgeVersionCurrent < 0 )
        goto LABEL_147;
      Container::Manager::Core::Details::FirstBootOperation::CloseResourceHandles(*(Container::Manager::Core::Details::FirstBootOperation **)(a1 + 264));
      Csl::AsyncOperation<void>::~AsyncOperation<void>(Buf2_8);
    }
    if ( *(_BYTE *)(a3 + 8) )
    {
      wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::operator=(
        a3,
        &Buf2);
      v59 = Buf2;
    }
    else
    {
      v59 = 0;
      *(_QWORD *)a3 = v18;
      *(_BYTE *)(a3 + 8) = 1;
    }
    Csl::AsyncOperation<void>::~AsyncOperation<void>(v64);
    Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v78);
    if ( (_BYTE)v76 && v74[0] != &v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v59 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v59);
      operator delete(v59, (const struct std::nothrow_t *)0x58);
    }
  }
  else
  {
LABEL_168:
    if ( *(_BYTE *)(a3 + 8) )
    {
      v60 = *(Container::Manager::Core::ResourceHandle **)a3;
      *(_QWORD *)a3 = 0;
      if ( v60 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v60);
        operator delete(v60, (const struct std::nothrow_t *)0x58);
      }
      *(_BYTE *)(a3 + 8) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180059154  mov     rax, rsp
0x180059157  mov     [rax+10h], rbx
0x18005915b  push    rbp
0x18005915c  push    rsi
0x18005915d  push    rdi
0x18005915e  push    r12
0x180059160  push    r13
0x180059162  push    r14
0x180059164  push    r15
0x180059166  lea     rbp, [rax-298h]
0x18005916d  sub     rsp, 360h
0x180059174  movaps  xmmword ptr [rax-48h], xmm6
0x180059178  mov     rax, cs:__security_cookie
0x18005917f  xor     rax, rsp
0x180059182  mov     [rbp+290h+var_50], rax
0x180059189  mov     r12, r8
0x18005918c  mov     rbx, rdx
0x18005918f  mov     [rsp+390h+Buf2], rdx
0x180059194  mov     rdi, rcx
0x180059197  mov     rcx, [rcx]; struct Container::Manager::Core::Details::Resource *
0x18005919a  call    ?GetLeafLayerRecurse@Resource@Details@Core@Manager@Container@@CAPEBVLayer@2345@PEBV12345@@Z; Container::Manager::Core::Details::Resource::GetLeafLayerRecurse(Container::Manager::Core::Details::Resource const *)
0x18005919f  mov     rsi, rax
0x1800591a2  xor     r13d, r13d
0x1800591a5  cmp     [rdi+120h], r13b
0x1800591ac  jnz     short loc_1800591B0
0x1800591ae  int     2Ch; Windows NT - assertion failure
0x1800591b0  cmp     dword ptr [rbx+10h], 2
0x1800591b4  jnz     loc_180059F04
0x1800591ba  mov     r15d, 1
0x1800591c0  mov     byte ptr [rsp+390h+var_350], r15b
0x1800591c5  lea     r14, [rax+180h]
0x1800591cc  cmp     [r14+128h], r13b
0x1800591d3  jz      short loc_180059209
0x1800591d5  test    byte ptr [rax+0E4h], 8
0x1800591dc  jz      short loc_180059209
0x1800591de  lea     rdx, [rsp+390h+var_350]; bool *
0x1800591e3  mov     rcx, r14; this
0x1800591e6  call    ?IsEdgeVersionCurrent@SpecializationLayer@Details@Core@Manager@Container@@QEBAJAEA_N@Z; Container::Manager::Core::Details::SpecializationLayer::IsEdgeVersionCurrent(bool &)
0x1800591eb  mov     ebx, eax
0x1800591ed  test    eax, eax
0x1800591ef  jns     short loc_1800591FF
0x1800591f1  mov     edx, 773h
0x1800591f6  lea     rdi, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800591fd  jmp     short loc_180059250
0x1800591ff  cmp     byte ptr [rsp+390h+var_350], r13b
0x180059204  mov     r9b, r15b
0x180059207  jz      short loc_18005920C
0x180059209  mov     r9b, r13b
0x18005920c  cmp     [rsi+2A8h], r13b
0x180059213  jz      short loc_180059284
0x180059215  lea     r8, [rdi+0E0h]
0x18005921c  mov     rdx, r14
0x18005921f  mov     rcx, rsi; this
0x180059222  call    ?RespecializeIfNeededInternal@Layer@Details@Core@Manager@Container@@AEAAJAEAVSpecializationLayer@2345@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@utl@@_N@Z; Container::Manager::Core::Details::Layer::RespecializeIfNeededInternal(Container::Manager::Core::Details::SpecializationLayer &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &,bool)
0x180059227  mov     ebx, eax
0x180059229  test    eax, eax
0x18005922b  jns     short loc_180059284
0x18005922d  mov     rcx, [rbp+298h]; this
0x180059234  mov     r9d, eax; char *
0x180059237  lea     rdi, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005923e  mov     r8, rdi; unsigned int
0x180059241  mov     edx, 7B8h; void *
0x180059246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005924b  mov     edx, 776h; void *
0x180059250  mov     r9d, ebx; char *
0x180059253  mov     rcx, [rbp+298h]; this
0x18005925a  mov     r8, rdi; unsigned int
0x18005925d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059262  mov     edx, 282Eh; void *
0x180059267  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005926e  mov     r9d, ebx; char *
0x180059271  mov     rcx, [rbp+298h]; this
0x180059278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005927d  mov     eax, ebx
0x18005927f  jmp     loc_180059F34
0x180059284  movzx   r15d, r13b
0x180059288  lea     rbx, [rsi+110h]
0x18005928f  mov     rcx, rbx; SRWLock
0x180059292  call    cs:__imp_AcquireSRWLockShared
0x180059299  nop     dword ptr [rax+rax+00h]
0x18005929e  lea     rax, [rsi+124h]
0x1800592a5  test    rbx, rbx
0x1800592a8  jz      short loc_1800592C0
0x1800592aa  mov     rcx, rbx; SRWLock
0x1800592ad  call    cs:__imp_ReleaseSRWLockShared
0x1800592b4  nop     dword ptr [rax+rax+00h]
0x1800592b9  lea     rax, [rsi+124h]
0x1800592c0  mov     r8d, 10h; Size
0x1800592c6  mov     r14, [rsp+390h+Buf2]
0x1800592cb  mov     rdx, r14; Buf2
0x1800592ce  mov     rcx, rax; Buf1
0x1800592d1  call    memcmp_0
0x1800592d6  test    eax, eax
0x1800592d8  jnz     short loc_1800592EA
0x1800592da  cmp     [rsi+0E0h], r13d
0x1800592e1  mov     eax, 1
0x1800592e6  cmovnz  r15d, eax
0x1800592ea  mov     rcx, rbx; SRWLock
0x1800592ed  call    cs:__imp_AcquireSRWLockShared
0x1800592f4  nop     dword ptr [rax+rax+00h]
0x1800592f9  test    rbx, rbx
0x1800592fc  jz      short loc_18005930D
0x1800592fe  mov     rcx, rbx; SRWLock
0x180059301  call    cs:__imp_ReleaseSRWLockShared
0x180059308  nop     dword ptr [rax+rax+00h]
0x18005930d  mov     r8d, 10h; Size
0x180059313  mov     rdx, r14; Buf2
0x180059316  lea     rcx, [rsi+124h]; Buf1
0x18005931d  call    memcmp_0
0x180059322  xor     ebx, ebx
0x180059324  test    eax, eax
0x180059326  jnz     short loc_180059339
0x180059328  movzx   r13d, r13b
0x18005932c  cmp     [rsi+84h], ebx
0x180059332  lea     eax, [rbx+1]
0x180059335  cmovnz  r13d, eax
0x180059339  test    r15b, r15b
0x18005933c  jnz     short loc_180059347
0x18005933e  test    r13b, r13b
0x180059341  jz      loc_180059F01
0x180059347  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005934e  mov     ecx, 58h ; 'X'; unsigned __int64
0x180059353  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059358  mov     r14, rax
0x18005935b  test    rax, rax
0x18005935e  jz      loc_180059EF2
0x180059364  lea     rcx, [rax+10h]
0x180059368  mov     [rax], rcx
0x18005936b  mov     [rax+8], rcx
0x18005936f  mov     [rcx], bx
0x180059372  mov     [rax+20h], ebx
0x180059375  mov     [rax+28h], rbx
0x180059379  mov     [rax+40h], rbx
0x18005937d  mov     [rax+48h], rbx
0x180059381  mov     [rax+50h], bl
0x180059384  mov     [rax+30h], rbx
0x180059388  mov     [rax+38h], rbx
0x18005938c  mov     [rsp+390h+Buf2], rax
0x180059391  lea     rax, aResourceoperat_3; "ResourceOperation_MaterializeStorage_Fi"...
0x180059398  mov     [rbp+290h+var_310], rax
0x18005939c  mov     [rbp+290h+var_308], 2Eh ; '.'
0x1800593a4  lea     rdx, [rbp+290h+var_310]
0x1800593a8  mov     rcx, r14
0x1800593ab  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800593b0  mov     ebx, eax
0x1800593b2  test    eax, eax
0x1800593b4  jns     short loc_1800593BD
0x1800593b6  mov     edx, 284Ch
0x1800593bb  jmp     short loc_1800593DA
0x1800593bd  xorps   xmm0, xmm0
0x1800593c0  movups  [rbp+290h+var_2A0], xmm0
0x1800593c4  lea     rcx, [rbp+290h+var_2A0]; this
0x1800593c8  call    ?CreateGuid@Csl@@YAJAEAU_GUID@@@Z; Csl::CreateGuid(_GUID &)
0x1800593cd  mov     ebx, eax
0x1800593cf  xor     ecx, ecx
0x1800593d1  test    eax, eax
0x1800593d3  jns     short loc_1800593F5
0x1800593d5  mov     edx, 2850h; void *
0x1800593da  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800593e1  mov     r9d, eax; char *
0x1800593e4  mov     rcx, [rbp+298h]; this
0x1800593eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800593f0  jmp     loc_180059C76
0x1800593f5  mov     [rbp+290h+var_300], ecx
0x1800593f8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800593ff  movdqu  [rbp+290h+var_2F8], xmm0
0x180059404  xor     eax, eax
0x180059406  mov     [rbp+290h+var_2E8], rax
0x18005940a  xorps   xmm0, xmm0
0x18005940d  movups  [rbp+290h+var_2E0], xmm0
0x180059411  mov     byte ptr [rbp+290h+var_2E0], cl
0x180059414  mov     bl, cl
0x180059416  mov     byte ptr [rbp+290h+var_2E0+8], cl
0x180059419  movups  xmmword ptr [rbp+290h+var_2D0], xmm0
0x18005941d  movups  [rbp+290h+var_2C0], xmm0
0x180059421  mov     [rbp+290h+var_2B0], rax
0x180059425  mov     byte ptr [rbp+290h+var_2D0], cl
0x180059428  mov     byte ptr [rbp+290h+var_2B0], cl
0x18005942b  mov     eax, 1
0x180059430  mov     dword ptr [rbp+290h+var_2E8], eax
0x180059433  mov     byte ptr [rbp+290h+var_2E8+4], al
0x180059436  movzx   eax, word ptr [rsp+390h+Buf2+5]
0x18005943b  mov     word ptr [rbp+290h+var_2E8+5], ax
0x18005943f  mov     al, byte ptr [rsp+390h+Buf2+7]
0x180059443  mov     byte ptr [rbp+290h+var_2E8+7], al
0x180059446  mov     eax, 2
0x18005944b  mov     [rbp+290h+var_2FC], eax
0x18005944e  movups  xmm6, xmmword ptr [rsi]
0x180059451  movups  [rbp+290h+var_2F8], xmm6
0x180059455  mov     [rbp+290h+var_300], eax
0x180059458  xor     eax, eax
0x18005945a  movups  [rbp+290h+var_278], xmm0
0x18005945e  mov     [rbp+290h+var_268], eax
0x180059461  xor     esi, esi
0x180059463  mov     byte ptr [rbp+290h+var_278], sil
0x180059467  mov     byte ptr [rbp+290h+var_268], sil
0x18005946b  mov     [rbp+290h+var_260], rsi
0x18005946f  xor     edx, edx; Val
0x180059471  lea     r8d, [rax+60h]; Size
0x180059475  lea     rcx, [rbp+290h+var_258]; void *
0x180059479  call    memset_0
0x18005947e  mov     byte ptr [rbp+290h+var_258], sil
0x180059482  mov     [rbp+290h+var_200], sil
0x180059489  xor     edx, edx; Val
0x18005948b  mov     r8d, 130h; Size
0x180059491  lea     rcx, [rbp+290h+var_1F8]; void *
0x180059498  call    memset_0
0x18005949d  mov     [rbp+290h+var_1F8], sil
0x1800594a4  mov     [rbp+290h+var_D0], sil
0x1800594ab  xorps   xmm0, xmm0
0x1800594ae  movups  [rbp+290h+var_C8], xmm0
0x1800594b5  movups  [rbp+290h+var_B8], xmm0
0x1800594bc  mov     byte ptr [rbp+290h+var_C8], sil
0x1800594c3  mov     byte ptr [rbp+290h+var_B8+0Ch], sil
0x1800594ca  movups  [rbp+290h+var_A8], xmm0
0x1800594d1  movups  [rbp+290h+var_A8+0Ch], xmm0
0x1800594d8  mov     byte ptr [rbp+290h+var_A8], sil
0x1800594df  mov     [rbp+290h+var_90], sil
0x1800594e6  movups  [rbp+290h+var_88], xmm0
0x1800594ed  movups  [rbp+290h+var_78], xmm0
0x1800594f4  movups  [rbp+290h+var_68], xmm0
0x1800594fb  mov     byte ptr [rbp+290h+var_88], sil
0x180059502  mov     byte ptr [rbp+290h+var_68+8], sil
0x180059509  movups  xmm0, [rbp+290h+var_2A0]
0x18005950d  movdqu  [rbp+290h+var_290], xmm0
0x180059512  lea     r11d, [rsi+1]
0x180059516  mov     [rbp+290h+var_280], r11d
0x18005951a  mov     [rbp+290h+var_27C], r11d
0x18005951e  cmp     [rbp+290h+var_200], sil
0x180059525  jz      short loc_18005956B
0x180059527  lea     eax, [rsi+2]
0x18005952a  mov     [rbp+290h+var_258], eax
0x18005952d  mov     [rbp+290h+var_254], eax
0x180059530  movdqu  [rbp+290h+var_250], xmm6
0x180059535  mov     rax, [rbp+290h+var_2E8]
0x180059539  mov     [rbp+290h+var_240], rax
0x18005953d  mov     rax, qword ptr [rbp+290h+var_2E0]
0x180059541  mov     [rbp+290h+var_238], rax
0x180059545  mov     [rbp+290h+var_230], bl
0x180059548  mov     eax, dword ptr [rbp+290h+var_2E0+9]
0x18005954b  mov     [rbp+290h+var_22F], eax
0x18005954e  movzx   eax, word ptr [rbp+290h+var_2E0+0Dh]
0x180059552  mov     [rbp+290h+var_22B], ax
0x180059556  mov     al, byte ptr [rbp+290h+var_2E0+0Fh]
0x180059559  mov     [rbp+290h+var_229], al
0x18005955c  lea     rdx, [rbp+290h+var_2D0]
0x180059560  lea     rcx, [rbp+290h+var_228]
0x180059564  call    ??4?$optional@VPath@Csl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::optional<Csl::Path>::operator=(utl::optional<Csl::Path> &&)
0x180059569  jmp     short loc_18005957F
0x18005956b  lea     rdx, [rbp+290h+var_300]
0x18005956f  lea     rcx, [rbp+290h+var_258]
0x180059573  call    ??0ContainerStorageConfiguration@Details@Core@Manager@Container@@QEAA@$$QEAU01234@@Z; Container::Manager::Core::Details::ContainerStorageConfiguration::ContainerStorageConfiguration(Container::Manager::Core::Details::ContainerStorageConfiguration &&)
0x180059578  mov     [rbp+290h+var_200], r11b
0x18005957f  lea     r8, [rsp+390h+Buf2]
0x180059584  lea     rdx, [rbp+290h+var_290]
0x180059588  mov     rcx, [rdi+0A8h]
0x18005958f  call    ?CreateResource@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBUResourceConfiguration@2345@AEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ResourceBroker::CreateResource(Container::Manager::Core::Details::ResourceConfiguration const &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> &)
0x180059594  mov     ebx, eax
0x180059596  test    eax, eax
0x180059598  jns     short loc_1800595C7
0x18005959a  mov     rcx, [rbp+298h]; this
0x1800595a1  mov     r9d, eax; char *
0x1800595a4  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800595ab  mov     edx, 2864h; void *
0x1800595b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800595b5  lea     rcx, [rbp+290h+var_290]; this
0x1800595b9  call    ??1ResourceConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration(void)
0x1800595be  cmp     byte ptr [rbp+290h+var_2B0], sil
0x1800595c2  jmp     loc_180059C5B
0x1800595c7  mov     rcx, r14
0x1800595ca  call    ??$Get@VContainerStorage@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVContainerStorage@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(void)
0x1800595cf  xorps   xmm0, xmm0
0x1800595d2  movdqu  xmmword ptr [rsp+390h+var_350+8], xmm0
0x1800595d8  mov     [rsp+390h+var_338], rsi
0x1800595dd  lea     rdx, [rsp+390h+var_350+8]
0x1800595e2  mov     rcx, rax
0x1800595e5  call    ?MaterializeAsync@ContainerStorage@Details@Core@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Core::Details::ContainerStorage::MaterializeAsync(Csl::AsyncOperation<void> &)
0x1800595ea  mov     esi, eax
0x1800595ec  test    eax, eax
0x1800595ee  jns     loc_180059678
0x1800595f4  mov     rcx, [rbp+298h]; this
0x1800595fb  mov     r9d, eax; char *
0x1800595fe  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180059605  mov     edx, 286Ah; void *
0x18005960a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005960f  lea     rcx, [rsp+390h+var_350+8]
0x180059614  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x180059619  nop
0x18005961a  mov     rcx, [rsp+390h+var_338]; this
0x18005961f  test    rcx, rcx
0x180059622  jz      short loc_18005962A
0x180059624  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180059629  nop
0x18005962a  mov     rbx, [rsp+390h+var_350+8]
0x18005962f  test    rbx, rbx
0x180059632  jz      short loc_180059649
0x180059634  mov     rcx, rbx
0x180059637  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18005963c  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180059641  mov     rcx, rbx; void *
  ... truncated ...
```
