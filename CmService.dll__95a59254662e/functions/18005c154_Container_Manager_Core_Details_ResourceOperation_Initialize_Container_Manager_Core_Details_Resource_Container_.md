# Container::Manager::Core::Details::ResourceOperation::Initialize(Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::ResourceOperationConfiguration &,utl::vector<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>,utl::allocator<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>> const &,utl::optional<Container::Manager::Core::Details::MaterializeContext>)

- ea: `0x18005c154`
- end: `0x18005c977`
- name: `?Initialize@ResourceOperation@Details@Core@Manager@Container@@AEAAJPEAVResource@2345@AEAUResourceOperationConfiguration@2345@AEBV?$vector@V?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@V?$allocator@V?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@@2@@utl@@V?$optional@UMaterializeContext@Details@Core@Manager@Container@@@9@@Z`
- size: `2083`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, Container::Manager::Core::Details::MaterializeContext *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180050c7c`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x180016658`
- `0x180023b68`
- `0x1800262e4`
- `0x1800471dc`
- `0x1800492f0`
- `0x18004dddc`
- `0x18004e3d8`
- `0x18004e6c4`
- `0x18004f45c`
- `0x18004f52c`
- `0x18005094c`
- `0x18005c154`
- `0x180065c70`
- `0x1800662a0`
- `0x180066670`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005c751`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005c751`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c18c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c18c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c1fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c513`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c5a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c7c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c887`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c1fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c513`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c5a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c7c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005c887`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c72b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c72b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c766`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c766`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c789`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c789`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c707`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c611`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c7a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c874`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c7a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c82a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c874`

## string_xrefs

- `0x18005c1c9`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c399`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c42b`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c4af`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c544`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c7f1`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c84a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c8ad`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005c929`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ResourceOperation::Initialize(
        RTL_SRWLOCK *pv,
        void *a2,
        __int64 a3,
        RTL_SRWLOCK ***a4,
        Container::Manager::Core::Details::MaterializeContext *a5)
{
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v8; // r9
  int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // r8d
  const char *v12; // r9
  void *v14; // r13
  RTL_SRWLOCK **v15; // rdi
  RTL_SRWLOCK **v16; // rsi
  _QWORD *v17; // rax
  _QWORD *v18; // r12
  int v19; // eax
  unsigned int v20; // r15d
  RTL_SRWLOCK **v21; // rax
  RTL_SRWLOCK **v22; // r15
  RTL_SRWLOCK *v23; // rcx
  RTL_SRWLOCK *v24; // rax
  utl::_RefCountBase *v25; // rcx
  const char *v26; // r9
  Container::Manager::Core::Details::ResourceOperation::DependencyContext *v27; // r15
  Container::Manager::Core::Details::ResourceOperation::DependencyContext *v28; // rdi
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  struct _TP_WORK **v37; // rsi
  struct _TP_WORK *v38; // r15
  DWORD v39; // edi
  utl::_RefCountBase *Ptr; // rcx
  utl::_RefCountBase *v41; // rcx
  unsigned __int64 v42; // r15
  unsigned __int64 v43; // rsi
  unsigned __int64 *v44; // rdi
  unsigned __int64 *v45; // r12
  void *v46; // r13
  RTL_SRWLOCK *v47; // rsi
  __int64 i; // rdi
  __int64 v49; // r14
  __int64 v50; // r13
  __int64 v51; // rdx
  unsigned int v52; // r8d
  const char *v53; // r9
  unsigned int v54; // r8d
  const char *v55; // r9
  unsigned int v56; // r8d
  const char *v57; // r9
  unsigned int LastError; // ebx
  int v59; // [rsp+28h] [rbp-71h]
  HANDLE hObject; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v61; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v62; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int64 *v63; // [rsp+50h] [rbp-49h]
  unsigned __int64 *v64; // [rsp+58h] [rbp-41h]
  void *v65; // [rsp+60h] [rbp-39h]
  void *v66; // [rsp+68h] [rbp-31h] BYREF
  utl::_RefCountBase *v67; // [rsp+70h] [rbp-29h]
  void *v68; // [rsp+78h] [rbp-21h] BYREF
  utl::_RefCountBase *v69; // [rsp+80h] [rbp-19h]
  Container::Manager::Core::Details::ResourceOperation::DependencyContext *v70; // [rsp+88h] [rbp-11h] BYREF
  RTL_SRWLOCK *v71; // [rsp+90h] [rbp-9h] BYREF
  __int64 v72; // [rsp+98h] [rbp-1h] BYREF
  char v73; // [rsp+A0h] [rbp+7h]
  char v74; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]

  ThreadpoolWork = CreateThreadpoolWork(
                     Container::Manager::Core::Details::ResourceOperation::ResourceOperationThread,
                     pv,
                     0);
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2261,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                  v8);
    if ( *((_BYTE *)a5 + 120) )
      Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(a5);
    return LastError;
  }
  hObject = 0;
  v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hObject,
         1);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2264,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v9,
      v59);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( *((_BYTE *)a5 + 120) )
      Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(a5);
    return v10;
  }
  utl::make_shared<Csl::CompletionEvent<void>,>(&v68);
  v14 = v68;
  if ( !v68 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2267,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v59);
    if ( v69 )
      utl::_RefCountBase::_DecStrong(v69);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v56, v57);
    goto LABEL_97;
  }
  utl::make_shared<Csl::CompletionEvent<void>,>(&v66);
  if ( !v66 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v59);
    if ( v67 )
      utl::_RefCountBase::_DecStrong(v67);
    if ( v69 )
      utl::_RefCountBase::_DecStrong(v69);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v54, v55);
LABEL_97:
    CloseThreadpoolWork(ThreadpoolWork);
    if ( *((_BYTE *)a5 + 120) )
      Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(a5);
    return 2147942414LL;
  }
  v62 = (unsigned __int64)&v62;
  v63 = &v62;
  v64 = &v62;
  v65 = 0;
  v15 = *a4;
  v16 = a4[1];
  while ( v15 != v16 )
  {
    v17 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v61 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2274,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        v59);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v61, 0);
      utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&v62);
      if ( v67 )
        utl::_RefCountBase::_DecStrong(v67);
      if ( v69 )
        utl::_RefCountBase::_DecStrong(v69);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
      goto LABEL_97;
    }
    *v17 = 0;
    v17[1] = 0;
    v17[2] = 0;
    v61 = v17;
    v19 = Container::Manager::Core::Details::ResourceOperation::WatchForCompletion(*v15, v17);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2276,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v19,
        v59);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v61, 0);
      utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&v62);
      if ( v67 )
        utl::_RefCountBase::_DecStrong(v67);
      if ( v69 )
        utl::_RefCountBase::_DecStrong(v69);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( *((_BYTE *)a5 + 120) )
        Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(a5);
      return v20;
    }
    v21 = (RTL_SRWLOCK **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v22 = v21;
    if ( !v21 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        v59);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v61, 0);
      utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&v62);
      if ( v67 )
        utl::_RefCountBase::_DecStrong(v67);
      if ( v69 )
        utl::_RefCountBase::_DecStrong(v69);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      goto LABEL_97;
    }
    v21[1] = 0;
    v21[2] = 0;
    v21[3] = 0;
    v70 = (Container::Manager::Core::Details::ResourceOperation::DependencyContext *)v21;
    *v21 = pv;
    v23 = *v15;
    v24 = v15[1];
    if ( v24 )
      _InterlockedIncrement((volatile signed __int32 *)&v24[1]);
    v22[1] = v23;
    v25 = (utl::_RefCountBase *)v22[2];
    v22[2] = v24;
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
    v61 = 0;
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v22 + 3, v18);
    v71 = *v15;
    utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::emplace<Container::Manager::Core::Details::ResourceOperation *,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>,0>(
      &v62,
      &v72,
      &v71,
      &v70);
    if ( !v72 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2285,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        v59);
      v28 = v70;
      if ( v70 )
      {
        Container::Manager::Core::Details::ResourceOperation::DependencyContext::~DependencyContext(v70);
        operator delete(v28, (const struct std::nothrow_t *)0x20);
      }
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v61, 0);
      utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&v62);
      if ( v67 )
        utl::_RefCountBase::_DecStrong(v67);
      if ( v69 )
        utl::_RefCountBase::_DecStrong(v69);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      goto LABEL_97;
    }
    if ( !v73 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2288,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        v26);
    v27 = v70;
    if ( v70 )
    {
      Container::Manager::Core::Details::ResourceOperation::DependencyContext::~DependencyContext(v70);
      operator delete(v27, (const struct std::nothrow_t *)0x20);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v61, 0);
    v15 += 2;
  }
  pv->Ptr = a2;
  Container::Manager::Core::Details::ResourceOperationConfiguration::operator=(&pv[1], a3);
  LODWORD(pv[8].Ptr) = 1;
  v37 = (struct _TP_WORK **)&pv[10];
  if ( &pv[10] != (RTL_SRWLOCK *)&v74 )
  {
    v38 = *v37;
    if ( *v37 )
    {
      v39 = GetLastError();
      CloseThreadpoolWork(v38);
      SetLastError(v39);
    }
    *v37 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    &pv[11],
    &hObject);
  pv[12].Ptr = v14;
  Ptr = (utl::_RefCountBase *)pv[13].Ptr;
  pv[13].Ptr = v69;
  if ( Ptr )
    utl::_RefCountBase::_DecStrong(Ptr);
  pv[14].Ptr = v66;
  v41 = (utl::_RefCountBase *)pv[15].Ptr;
  pv[15].Ptr = v67;
  if ( v41 )
    utl::_RefCountBase::_DecStrong(v41);
  v42 = (unsigned __int64)&pv[16];
  v43 = v62;
  v44 = v63;
  v45 = v64;
  v46 = v65;
  v62 = (unsigned __int64)&v62;
  v63 = &v62;
  v64 = &v62;
  v65 = 0;
  utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&pv[16]);
  if ( v45 != &v62 )
  {
    *(_QWORD *)(v43 & 0xFFFFFFFFFFFFFFFEuLL) = v42 | 1;
    *(_QWORD *)v42 = v43;
    pv[17].Ptr = v44;
    pv[18].Ptr = v45;
    pv[19].Ptr = v46;
  }
  if ( *((_BYTE *)a5 + 120) )
  {
    utl::_OptionalData2<Container::Manager::Core::Details::MaterializeContext>::_AssignVal<Container::Manager::Core::Details::MaterializeContext>(
      &pv[21],
      a5);
  }
  else if ( LOBYTE(pv[36].Ptr) )
  {
    Container::Manager::Core::Details::MaterializeContext::~MaterializeContext((Container::Manager::Core::Details::MaterializeContext *)&pv[21]);
    LOBYTE(pv[36].Ptr) = 0;
  }
  v47 = pv + 6;
  AcquireSRWLockShared(pv + 6);
  for ( i = (__int64)pv[18].Ptr;
        i != v42;
        i = utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(
              i,
              v51) )
  {
    v49 = *(_QWORD *)(i + 32);
    v50 = **(_QWORD **)(v49 + 24);
    AcquireSRWLockExclusive((PSRWLOCK)(v50 + 8));
    *(_QWORD *)(v50 + 16) = Container::Manager::Core::Details::ResourceOperation::OnDependencyCompleted;
    *(_QWORD *)(v50 + 24) = v49;
    if ( *(_DWORD *)v50 == 2 )
      SubmitThreadpoolWork(*(PTP_WORK *)(v50 + 32));
    if ( v50 != -8 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v50 + 8));
    LOBYTE(v51) = 1;
  }
  if ( v47 )
    ReleaseSRWLockShared(v47);
  utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&v62);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v52, v53);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( *((_BYTE *)a5 + 120) )
    Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(a5);
  return 0;
}

```

## disassembly

```asm
0x18005c154  mov     rax, rsp
0x18005c157  mov     [rax+8], rbx
0x18005c15b  mov     [rax+18h], r8
0x18005c15f  mov     [rax+10h], rdx
0x18005c163  push    rbp
0x18005c164  push    rsi
0x18005c165  push    rdi
0x18005c166  push    r12
0x18005c168  push    r13
0x18005c16a  push    r14
0x18005c16c  push    r15
0x18005c16e  lea     rbp, [rax-57h]
0x18005c172  sub     rsp, 0B0h
0x18005c179  mov     rsi, r9
0x18005c17c  mov     r14, rcx
0x18005c17f  xor     r8d, r8d; pcbe
0x18005c182  mov     rdx, rcx; pv
0x18005c185  lea     rcx, ?ResourceOperationThread@ResourceOperation@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005c18c  call    cs:__imp_CreateThreadpoolWork
0x18005c193  nop     dword ptr [rax+rax+00h]
0x18005c198  mov     rbx, rax
0x18005c19b  xor     r12d, r12d
0x18005c19e  test    rax, rax
0x18005c1a1  jz      loc_18005C8A9
0x18005c1a7  mov     [rbp+4Fh+hObject], r12
0x18005c1ab  xor     r9d, r9d
0x18005c1ae  lea     edx, [r12+1]
0x18005c1b3  lea     rcx, [rbp+4Fh+hObject]
0x18005c1b7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005c1bc  mov     edi, eax
0x18005c1be  test    eax, eax
0x18005c1c0  jns     short loc_18005C21C
0x18005c1c2  mov     rcx, [rbp+57h]; this
0x18005c1c6  mov     r9d, eax; char *
0x18005c1c9  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005c1d0  mov     edx, 2264h; void *
0x18005c1d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c1da  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18005c1de  test    rcx, rcx
0x18005c1e1  jz      short loc_18005C1F7
0x18005c1e3  call    cs:__imp_CloseHandle
0x18005c1ea  nop     dword ptr [rax+rax+00h]
0x18005c1ef  test    eax, eax
0x18005c1f1  jz      loc_18005C91A
0x18005c1f7  mov     rcx, rbx; pwk
0x18005c1fa  call    cs:__imp_CloseThreadpoolWork
0x18005c201  nop     dword ptr [rax+rax+00h]
0x18005c206  mov     rcx, [rbp+4Fh+arg_20]; this
0x18005c20a  cmp     [rcx+78h], r12b
0x18005c20e  jz      short loc_18005C215
0x18005c210  call    ??1MaterializeContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(void)
0x18005c215  mov     eax, edi
0x18005c217  jmp     loc_18005C8D1
0x18005c21c  lea     rcx, [rbp+4Fh+var_70]
0x18005c220  call    ??$make_shared@V?$CompletionEvent@X@Csl@@$$V@utl@@YA?AV?$shared_ptr@V?$CompletionEvent@X@Csl@@@0@XZ; utl::make_shared<Csl::CompletionEvent<void>,>(void)
0x18005c225  mov     r13, [rbp+4Fh+var_70]
0x18005c229  test    r13, r13
0x18005c22c  jz      loc_18005C840
0x18005c232  lea     rcx, [rbp+4Fh+var_80]
0x18005c236  call    ??$make_shared@V?$CompletionEvent@X@Csl@@$$V@utl@@YA?AV?$shared_ptr@V?$CompletionEvent@X@Csl@@@0@XZ; utl::make_shared<Csl::CompletionEvent<void>,>(void)
0x18005c23b  cmp     [rbp+4Fh+var_80], r12
0x18005c23f  jz      loc_18005C7E7
0x18005c245  lea     rax, [rbp+4Fh+var_A0]
0x18005c249  mov     [rbp+4Fh+var_A0], rax
0x18005c24d  lea     rax, [rbp+4Fh+var_A0]
0x18005c251  mov     [rbp+4Fh+var_98], rax
0x18005c255  mov     [rbp+4Fh+var_90], rax
0x18005c259  mov     [rbp+4Fh+var_88], r12
0x18005c25d  mov     rdi, [rsi]
0x18005c260  mov     rsi, [rsi+8]
0x18005c264  cmp     rdi, rsi
0x18005c267  jz      loc_18005C5C1
0x18005c26d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005c274  mov     ecx, 18h; unsigned __int64
0x18005c279  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005c27e  mov     r12, rax
0x18005c281  xor     r15d, r15d
0x18005c284  test    rax, rax
0x18005c287  jz      loc_18005C536
0x18005c28d  mov     [rax], r15
0x18005c290  mov     [rax+8], r15
0x18005c294  mov     [rax+10h], r15
0x18005c298  mov     [rbp+4Fh+var_A8], rax
0x18005c29c  mov     rdx, rax
0x18005c29f  mov     rcx, [rdi]
0x18005c2a2  call    ?WatchForCompletion@ResourceOperation@Details@Core@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Core::Details::ResourceOperation::WatchForCompletion(Csl::AsyncOperation<void> &)
0x18005c2a7  mov     r15d, eax
0x18005c2aa  test    eax, eax
0x18005c2ac  js      loc_18005C4A8
0x18005c2b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005c2b9  mov     ecx, 20h ; ' '; unsigned __int64
0x18005c2be  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005c2c3  mov     r15, rax
0x18005c2c6  test    rax, rax
0x18005c2c9  jz      loc_18005C421
0x18005c2cf  mov     qword ptr [rax+8], 0
0x18005c2d7  mov     qword ptr [rax+10h], 0
0x18005c2df  mov     qword ptr [rax+18h], 0
0x18005c2e7  mov     [rbp+4Fh+var_60], rax
0x18005c2eb  mov     [rax], r14
0x18005c2ee  mov     rcx, [rdi]
0x18005c2f1  mov     rax, [rdi+8]
0x18005c2f5  test    rax, rax
0x18005c2f8  jz      short loc_18005C2FE
0x18005c2fa  lock inc dword ptr [rax+8]
0x18005c2fe  mov     [r15+8], rcx
0x18005c302  mov     rcx, [r15+10h]; this
0x18005c306  mov     [r15+10h], rax
0x18005c30a  test    rcx, rcx
0x18005c30d  jz      short loc_18005C315
0x18005c30f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c314  nop
0x18005c315  mov     [rbp+4Fh+var_A8], 0
0x18005c31d  lea     rcx, [r15+18h]
0x18005c321  mov     rdx, r12
0x18005c324  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c329  mov     rax, [rdi]
0x18005c32c  mov     [rbp+4Fh+var_58], rax
0x18005c330  lea     r9, [rbp+4Fh+var_60]
0x18005c334  lea     r8, [rbp+4Fh+var_58]
0x18005c338  lea     rdx, [rbp+4Fh+var_50]
0x18005c33c  lea     rcx, [rbp+4Fh+var_A0]
0x18005c340  call    ??$emplace@PEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@$0A@@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@_N@1@$$QEAPEAVResourceOperation@Details@Core@Manager@Container@@$$QEAV?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::emplace<Container::Manager::Core::Details::ResourceOperation *,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>,0>(Container::Manager::Core::Details::ResourceOperation * &&,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>> &&)
0x18005c345  xor     r12d, r12d
0x18005c348  mov     rcx, [rbp+57h]; this
0x18005c34c  cmp     [rbp+4Fh+var_50], r12
0x18005c350  jz      short loc_18005C393
0x18005c352  cmp     [rbp+4Fh+var_48], r12b
0x18005c356  setz    al
0x18005c359  test    al, al
0x18005c35b  jnz     loc_18005C929
0x18005c361  mov     r15, [rbp+4Fh+var_60]
0x18005c365  test    r15, r15
0x18005c368  jz      short loc_18005C37F
0x18005c36a  mov     rcx, r15; this
0x18005c36d  call    ??1DependencyContext@ResourceOperation@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceOperation::DependencyContext::~DependencyContext(void)
0x18005c372  lea     edx, [r12+20h]; struct std::nothrow_t *
0x18005c377  mov     rcx, r15; void *
0x18005c37a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005c37f  xor     edx, edx
0x18005c381  lea     rcx, [rbp+4Fh+var_A8]
0x18005c385  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c38a  add     rdi, 10h
0x18005c38e  jmp     loc_18005C264
0x18005c393  mov     r9d, 8007000Eh; char *
0x18005c399  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005c3a0  mov     edx, 2285h; void *
0x18005c3a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c3aa  mov     rdi, [rbp+4Fh+var_60]
0x18005c3ae  test    rdi, rdi
0x18005c3b1  jz      short loc_18005C3C8
0x18005c3b3  mov     rcx, rdi; this
0x18005c3b6  call    ??1DependencyContext@ResourceOperation@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceOperation::DependencyContext::~DependencyContext(void)
0x18005c3bb  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18005c3c0  mov     rcx, rdi; void *
0x18005c3c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005c3c8  xor     edx, edx
0x18005c3ca  lea     rcx, [rbp+4Fh+var_A8]
0x18005c3ce  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c3d3  lea     rcx, [rbp+4Fh+var_A0]
0x18005c3d7  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18005c3dc  nop
0x18005c3dd  mov     rcx, [rbp+4Fh+var_78]; this
0x18005c3e1  test    rcx, rcx
0x18005c3e4  jz      short loc_18005C3EC
0x18005c3e6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c3eb  nop
0x18005c3ec  mov     rcx, [rbp+4Fh+var_68]; this
0x18005c3f0  test    rcx, rcx
0x18005c3f3  jz      short loc_18005C3FB
0x18005c3f5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c3fa  nop
0x18005c3fb  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18005c3ff  test    rcx, rcx
0x18005c402  jz      loc_18005C884
0x18005c408  call    cs:__imp_CloseHandle
0x18005c40f  nop     dword ptr [rax+rax+00h]
0x18005c414  test    eax, eax
0x18005c416  jz      loc_18005C8FC
0x18005c41c  jmp     loc_18005C884
0x18005c421  mov     rcx, [rbp+57h]; this
0x18005c425  mov     r9d, 8007000Eh; char *
0x18005c42b  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005c432  mov     edx, 227Dh; void *
0x18005c437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c43c  xor     edx, edx
0x18005c43e  lea     rcx, [rbp+4Fh+var_A8]
0x18005c442  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c447  lea     rcx, [rbp+4Fh+var_A0]
0x18005c44b  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18005c450  nop
0x18005c451  mov     rcx, [rbp+4Fh+var_78]; this
0x18005c455  test    rcx, rcx
0x18005c458  jz      short loc_18005C460
0x18005c45a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c45f  nop
0x18005c460  mov     rcx, [rbp+4Fh+var_68]; this
0x18005c464  test    rcx, rcx
0x18005c467  jz      short loc_18005C46F
0x18005c469  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c46e  nop
0x18005c46f  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18005c473  test    rcx, rcx
0x18005c476  jz      short loc_18005C48C
0x18005c478  call    cs:__imp_CloseHandle
0x18005c47f  nop     dword ptr [rax+rax+00h]
0x18005c484  test    eax, eax
0x18005c486  jz      loc_18005C93B
0x18005c48c  mov     rcx, rbx; pwk
0x18005c48f  call    cs:__imp_CloseThreadpoolWork
0x18005c496  nop     dword ptr [rax+rax+00h]
0x18005c49b  mov     rcx, [rbp+4Fh+arg_20]
0x18005c49f  cmp     byte ptr [rcx+78h], 0
0x18005c4a3  jmp     loc_18005C89B
0x18005c4a8  mov     rcx, [rbp+57h]; this
0x18005c4ac  mov     r9d, r15d; char *
0x18005c4af  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005c4b6  mov     edx, 2276h; void *
0x18005c4bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c4c0  xor     edx, edx
0x18005c4c2  lea     rcx, [rbp+4Fh+var_A8]
0x18005c4c6  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c4cb  lea     rcx, [rbp+4Fh+var_A0]
0x18005c4cf  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18005c4d4  nop
0x18005c4d5  mov     rcx, [rbp+4Fh+var_78]; this
0x18005c4d9  test    rcx, rcx
0x18005c4dc  jz      short loc_18005C4E4
0x18005c4de  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c4e3  nop
0x18005c4e4  mov     rcx, [rbp+4Fh+var_68]; this
0x18005c4e8  test    rcx, rcx
0x18005c4eb  jz      short loc_18005C4F3
0x18005c4ed  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c4f2  nop
0x18005c4f3  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18005c4f7  test    rcx, rcx
0x18005c4fa  jz      short loc_18005C510
0x18005c4fc  call    cs:__imp_CloseHandle
0x18005c503  nop     dword ptr [rax+rax+00h]
0x18005c508  test    eax, eax
0x18005c50a  jz      loc_18005C94A
0x18005c510  mov     rcx, rbx; pwk
0x18005c513  call    cs:__imp_CloseThreadpoolWork
0x18005c51a  nop     dword ptr [rax+rax+00h]
0x18005c51f  mov     rcx, [rbp+4Fh+arg_20]; this
0x18005c523  cmp     byte ptr [rcx+78h], 0
0x18005c527  jz      short loc_18005C52E
0x18005c529  call    ??1MaterializeContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(void)
0x18005c52e  mov     eax, r15d
0x18005c531  jmp     loc_18005C8D1
0x18005c536  mov     [rbp+4Fh+var_A8], r15
0x18005c53a  mov     rcx, [rbp+57h]; this
0x18005c53e  mov     r9d, 8007000Eh; char *
0x18005c544  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005c54b  mov     edx, 2274h; void *
0x18005c550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c555  xor     edx, edx
0x18005c557  lea     rcx, [rbp+4Fh+var_A8]
0x18005c55b  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005c560  lea     rcx, [rbp+4Fh+var_A0]
0x18005c564  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18005c569  nop
0x18005c56a  mov     rcx, [rbp+4Fh+var_78]; this
0x18005c56e  test    rcx, rcx
0x18005c571  jz      short loc_18005C579
0x18005c573  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c578  nop
0x18005c579  mov     rcx, [rbp+4Fh+var_68]; this
0x18005c57d  test    rcx, rcx
0x18005c580  jz      short loc_18005C588
0x18005c582  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005c587  nop
0x18005c588  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18005c58c  test    rcx, rcx
0x18005c58f  jz      short loc_18005C5A5
0x18005c591  call    cs:__imp_CloseHandle
0x18005c598  nop     dword ptr [rax+rax+00h]
0x18005c59d  test    eax, eax
0x18005c59f  jz      loc_18005C959
0x18005c5a5  mov     rcx, rbx; pwk
0x18005c5a8  call    cs:__imp_CloseThreadpoolWork
0x18005c5af  nop     dword ptr [rax+rax+00h]
0x18005c5b4  mov     rcx, [rbp+4Fh+arg_20]
0x18005c5b8  cmp     [rcx+78h], r15b
0x18005c5bc  jmp     loc_18005C89B
0x18005c5c1  mov     rax, [rbp+4Fh+arg_8]
0x18005c5c5  mov     [r14], rax
0x18005c5c8  lea     rcx, [r14+8]
0x18005c5cc  mov     rdx, [rbp+4Fh+arg_10]
0x18005c5d0  call    ??4ResourceOperationConfiguration@Details@Core@Manager@Container@@QEAAAEAU01234@$$QEAU01234@@Z; Container::Manager::Core::Details::ResourceOperationConfiguration::operator=(Container::Manager::Core::Details::ResourceOperationConfiguration &&)
0x18005c5d5  mov     dword ptr [r14+40h], 1
0x18005c5dd  lea     rsi, [r14+50h]
0x18005c5e1  lea     rax, [rbp+4Fh+var_40]
0x18005c5e5  cmp     rsi, rax
0x18005c5e8  jz      short loc_18005C623
0x18005c5ea  mov     r15, [rsi]
0x18005c5ed  test    r15, r15
0x18005c5f0  jz      short loc_18005C61D
0x18005c5f2  call    cs:__imp_GetLastError
  ... truncated ...
```
