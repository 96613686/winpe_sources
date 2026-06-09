# Container::Manager::Core::Details::Layer::Materialize(utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &)

- ea: `0x1800c9334`
- end: `0x1800ca2de`
- name: `?Materialize@Layer@Details@Core@Manager@Container@@QEAAJAEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@7@@Z`
- size: `4010`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::Layer *this)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d40c`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x180016774`
- `0x18002d070`
- `0x18002dc0c`
- `0x18002ed40`
- `0x18002fae4`
- `0x18002fd88`
- `0x18002ff9c`
- `0x180030200`
- `0x1800335b8`
- `0x18003dd20`
- `0x1800471dc`
- `0x1800802f0`
- `0x1800c1bd0`
- `0x1800c1e80`
- `0x1800c467c`
- `0x1800c58a8`
- `0x1800c5988`
- `0x1800c6c38`
- `0x1800c9334`
- `0x1800cb554`
- `0x1800cc8e8`
- `0x1800d98d4`
- `0x1801094d0`
- `0x180182a2c`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x1800c94bf`
- `ntdll!RtlDoesFileExists_U` at `0x1800c97e1`
- `ntdll!RtlDoesFileExists_U` at `0x1800c94bf`
- `ntdll!RtlDoesFileExists_U` at `0x1800c97e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c9ed7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c9ed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9f3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ca066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ca185`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9f3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ca066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ca185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9ee3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c96ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c96ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Container::Manager::Core::Details::Layer::Materialize(
        Container::Manager::Core::Details::Layer *this,
        const struct Container::Manager::Core::Details::PolicyManager **a2)
{
  int ResourcePath; // eax
  int v4; // edi
  void *v5; // rcx
  int DeploymentPath; // eax
  __int64 v8; // rdx
  struct _SECURITY_ATTRIBUTES *v9; // r8
  __int64 v10; // rdx
  Csl *i; // rbx
  const struct Path *v12; // rdx
  int BindingsPath; // eax
  struct Container::Manager::Core::Details::BindingStore *v14; // r12
  int v15; // eax
  Container::Manager::Core::Details::BindingStore *v16; // r13
  utl::_RefCountBase *v17; // rdi
  int v18; // eax
  unsigned int v19; // r14d
  __int64 v20; // rax
  int v21; // eax
  struct _SECURITY_ATTRIBUTES *v22; // r8
  int DirectoryRecursive; // eax
  const struct Path *v24; // r8
  int BaseHives; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  void **v29; // r9
  int v30; // eax
  unsigned int v31; // esi
  void *v32; // rcx
  bool v33; // zf
  int v34; // eax
  char *v35; // r14
  int v36; // eax
  unsigned int v37; // r15d
  int v38; // eax
  int v39; // r15d
  utl::_RefCountBase *v40; // rcx
  utl::_RefCountBase *v41; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  PCWSTR FileName; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v45; // [rsp+38h] [rbp-C8h]
  _WORD v46[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v47; // [rsp+50h] [rbp-B0h] BYREF
  char *v48; // [rsp+58h] [rbp-A8h]
  _WORD v49[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v50; // [rsp+70h] [rbp-90h] BYREF
  char *v51; // [rsp+78h] [rbp-88h]
  _WORD v52[8]; // [rsp+80h] [rbp-80h] BYREF
  struct Container::Manager::Core::Details::BindingStore *v53; // [rsp+90h] [rbp-70h] BYREF
  utl::_RefCountBase *v54; // [rsp+98h] [rbp-68h]
  void *v55[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v56[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v57[2]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v58[8]; // [rsp+D0h] [rbp-30h] BYREF
  void *v59[2]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v60[8]; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v61; // [rsp+100h] [rbp+0h] BYREF
  utl::_RefCountBase *v62; // [rsp+108h] [rbp+8h]
  PCWSTR v63[2]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v64[8]; // [rsp+120h] [rbp+20h] BYREF
  Csl *v65[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v66; // [rsp+140h] [rbp+40h]
  _QWORD v67[2]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v68[3]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v69[296]; // [rsp+170h] [rbp+70h] BYREF
  char v70; // [rsp+298h] [rbp+198h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v47 = v49;
  v48 = (char *)v49;
  v49[0] = 0;
  ResourcePath = Container::Manager::Core::Details::Layer::GetResourcePath(this, 0, &v47);
  v4 = ResourcePath;
  if ( ResourcePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)ResourcePath,
      bIgnoreCase);
    v5 = v47;
    if ( v47 == v49 )
      return (unsigned int)v4;
LABEL_3:
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v4;
  }
  FileName = v46;
  v45 = v46;
  v46[0] = 0;
  DeploymentPath = Container::Manager::Core::Details::_anonymous_namespace_::GetDeploymentPath(this, &FileName);
  v4 = DeploymentPath;
  if ( DeploymentPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)DeploymentPath,
      bIgnoreCase);
    goto LABEL_7;
  }
  v50 = v52;
  v51 = (char *)v52;
  v52[0] = 0;
  if ( (*((_BYTE *)this + 228) & 4) != 0 )
  {
    v4 = Container::Manager::Core::Details::Layer::GetResourcePath(this, 4, &v50);
    if ( v4 < 0 )
    {
      v8 = 488;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v4,
        bIgnoreCase);
LABEL_15:
      if ( v50 != v52 )
        operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
LABEL_7:
      if ( FileName != v46 )
        operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v47;
      if ( v47 == v49 )
        return (unsigned int)v4;
      goto LABEL_3;
    }
  }
  if ( RtlDoesFileExists_U(FileName) )
  {
    *(__m128i *)v65 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v66 = -1;
    v4 = Csl::EnumerateDirectory(&FileName, 1, v65, L"*");
    if ( v4 < 0 )
    {
      v10 = 502;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v4,
        bIgnoreCase);
      utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v65);
      goto LABEL_15;
    }
    for ( i = v65[0]; i != v65[1]; i = (Csl *)((char *)i + 32) )
    {
      v53 = (struct Container::Manager::Core::Details::BindingStore *)v47;
      v54 = (utl::_RefCountBase *)((v48 - (_BYTE *)v47) >> 1);
      v67[0] = *(_QWORD *)i;
      v67[1] = (__int64)(*((_QWORD *)i + 1) - v67[0]) >> 1;
      if ( !(unsigned __int8)Csl::StringEqualIgnoreCase(v67, &v53) )
      {
        v68[0] = v50;
        v68[1] = (v51 - (_BYTE *)v50) >> 1;
        v61 = *(const wchar_t **)i;
        v62 = (utl::_RefCountBase *)((__int64)(*((_QWORD *)i + 1) - (_QWORD)v61) >> 1);
        if ( !(unsigned __int8)Csl::StringEqualIgnoreCase(&v61, v68) )
        {
          v4 = Csl::DeletePath(i, v12);
          if ( v4 < 0 )
          {
            v10 = 509;
            goto LABEL_20;
          }
        }
      }
    }
    utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v65);
  }
  else
  {
    v4 = Csl::CreateDirectoryRecursive(&FileName, 0, v9);
    if ( v4 < 0 )
    {
      v8 = 516;
      goto LABEL_14;
    }
  }
  v55[0] = v56;
  v55[1] = v56;
  v56[0] = 0;
  BindingsPath = Container::Manager::Core::Details::_anonymous_namespace_::GetBindingsPath(&FileName, v55);
  v4 = BindingsPath;
  if ( BindingsPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)BindingsPath,
      bIgnoreCase);
LABEL_31:
    if ( v55[0] != v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_15;
  }
  utl::make_shared<Container::Manager::Core::Details::BindingStore,>(&v53);
  v14 = v53;
  if ( !v53 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_242;
  }
  v15 = Container::Manager::Core::Details::BindingStore::Initialize(v53, (const struct Path *)v55);
  v4 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v15,
      bIgnoreCase);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_31;
  }
  v16 = 0;
  v17 = 0;
  if ( CompareStringOrdinal(
         FileName,
         v45 - FileName,
         *((LPCWCH *)this + 2),
         (__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 1,
         1) != 2 )
  {
    v63[0] = v64;
    v63[1] = v64;
    v64[0] = 0;
    v18 = Container::Manager::Core::Details::_anonymous_namespace_::GetBindingsPath((char *)this + 16, v63);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCasea);
      if ( v63[0] != v64 )
        operator delete((void *)v63[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
LABEL_46:
      if ( v55[0] != v56 )
        operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v50 != v52 )
        operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
      if ( FileName != v46 )
        operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
      if ( v47 != v49 )
        operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
      return v19;
    }
    if ( RtlDoesFileExists_U(v63[0]) )
    {
      v20 = utl::make_shared<Container::Manager::Core::Details::BindingStore,>(&v61);
      v16 = *(Container::Manager::Core::Details::BindingStore **)v20;
      v17 = *(utl::_RefCountBase **)(v20 + 8);
      *(_QWORD *)v20 = 0;
      *(_QWORD *)(v20 + 8) = 0;
      if ( v62 )
        utl::_RefCountBase::_DecStrong(v62);
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCasea);
        if ( v63[0] != v64 )
          operator delete((void *)v63[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          utl::_RefCountBase::_DecStrong(v17);
        if ( v54 )
          utl::_RefCountBase::_DecStrong(v54);
        goto LABEL_242;
      }
      v21 = Container::Manager::Core::Details::BindingStore::Initialize(v16, (const struct Path *)v63);
      v19 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCasea);
        if ( v63[0] != v64 )
          operator delete((void *)v63[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          utl::_RefCountBase::_DecStrong(v17);
        if ( v54 )
          utl::_RefCountBase::_DecStrong(v54);
        goto LABEL_46;
      }
    }
    if ( v63[0] != v64 )
      operator delete((void *)v63[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  v57[0] = v58;
  v57[1] = v58;
  v58[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v57,
                           FileName,
                           v45 - FileName) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCasea);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
LABEL_242:
    if ( v55[0] != v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v50 != v52 )
      operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
    if ( FileName != v46 )
      operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47 != v49 )
      operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v61 = L"Hives";
  v62 = (utl::_RefCountBase *)5;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v57) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x228,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCasea);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_242;
  }
  DirectoryRecursive = Csl::CreateDirectoryRecursive((LPCWSTR *)v57, 0, v22);
  v19 = DirectoryRecursive;
  if ( DirectoryRecursive < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)DirectoryRecursive,
      bIgnoreCasea);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_46;
  }
  BaseHives = Container::Manager::Storage::CreateBaseHives(
                (Container::Manager::Storage *)&v47,
                (const struct Path *)v57,
                v24);
  v19 = BaseHives;
  if ( BaseHives < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)BaseHives,
      bIgnoreCasea);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_46;
  }
  v59[0] = v60;
  v59[1] = v60;
  v60[0] = 0;
  memset_0(v69, 0, 0x130u);
  if ( *((_DWORD *)this + 57) )
  {
    Container::Manager::Core::Details::SpecializationLayer::SpecializationLayer((Container::Manager::Core::Details::SpecializationLayer *)v69);
    v70 = 1;
    v26 = Container::Manager::Core::Details::SpecializationLayer::Initialize(
            (Container::Manager::Core::Details::SpecializationLayer *)v69,
            this);
    v19 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCasea);
      utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v57[0] != v58 )
        operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
        utl::_RefCountBase::_DecStrong(v17);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      goto LABEL_46;
    }
    if ( !v70 )
      __int2c();
    v27 = Container::Manager::Core::Details::Layer::RespecializeIfNeededInternal(this);
    v19 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x240,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v27,
        bIgnoreCasea);
      utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v57[0] != v58 )
        operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
        utl::_RefCountBase::_DecStrong(v17);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      goto LABEL_46;
    }
    v28 = Container::Manager::Core::Details::Layer::GetResourcePath(this, 3, v59);
    v19 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x245,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v28,
        bIgnoreCasea);
      utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v57[0] != v58 )
        operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
        utl::_RefCountBase::_DecStrong(v17);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      goto LABEL_46;
    }
    v29 = v59;
  }
  else
  {
    v29 = &v47;
  }
  v30 = Container::Manager::Core::Details::Layer::EnableDebugSettingsIfNeeded(this, *a2, v14, (const struct Path *)v29);
  v19 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x251,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v30,
      bIgnoreCasea);
    utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    goto LABEL_46;
  }
  if ( *((_BYTE *)this + 744) )
  {
    if ( *((_DWORD *)this + 175) != 1 )
    {
      v31 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x267,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)0x80004005LL,
        bIgnoreCasea);
      utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v57[0] != v58 )
        operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
        utl::_RefCountBase::_DecStrong(v17);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      if ( v55[0] != v56 )
        operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v50 != v52 )
        operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
      if ( FileName != v46 )
        operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
      v32 = v47;
      v33 = v47 == v49;
LABEL_170:
      if ( !v33 )
        operator delete(v32, (const struct std::nothrow_t *)&std::nothrow);
      return v31;
    }
    v34 = Csl::GrantVmGroupAccess(
            (Container::Manager::Core::Details::Layer *)((char *)this + 704),
            (const struct Path *)0x120089);
    v19 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x260,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v34,
        bIgnoreCasea);
      utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v57[0] != v58 )
        operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17 )
        utl::_RefCountBase::_DecStrong(v17);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      goto LABEL_46;
    }
  }
  v35 = (char *)this + 272;
  AcquireSRWLockExclusive((PSRWLOCK)this + 34);
  *((_DWORD *)this + 70) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 28) == 4 )
  {
    v31 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x285,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
            (const char *)0x12F,
            bIgnoreCasea);
    *((_DWORD *)v35 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v35);
    utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    if ( v55[0] != v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v50 != v52 )
      operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
    if ( FileName != v46 )
      operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
    v32 = v47;
    v33 = v47 == v49;
    goto LABEL_170;
  }
  v36 = Container::Manager::Core::Details::Layer::SetStateLocked(this, 3);
  v37 = v36;
  if ( v36 >= 0 )
  {
    if ( (*((_BYTE *)this + 288) & 4) == 0 )
    {
      v38 = Csl::RegistryKey::Flush((Csl::RegistryKey *)(*((_QWORD *)this + 32) + 8LL));
      v39 = v38;
      if ( v38 >= 0 )
        v39 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1060,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v38,
          bIgnoreCasea);
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x280,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v39,
          bIgnoreCasea);
    }
    *((_DWORD *)this + 70) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 34);
    *((_QWORD *)this + 41) = v14;
    v40 = (utl::_RefCountBase *)*((_QWORD *)this + 42);
    *((_QWORD *)this + 42) = v54;
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    *((_QWORD *)this + 39) = v16;
    v41 = (utl::_RefCountBase *)*((_QWORD *)this + 40);
    *((_QWORD *)this + 40) = v17;
    if ( v41 )
      utl::_RefCountBase::_DecStrong(v41);
    utl::optional<Container::Manager::Core::Details::SpecializationLayer>::operator=((char *)this + 384, v69);
    utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v55[0] != v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v50 != v52 )
      operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
    if ( FileName != v46 )
      operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47 != v49 )
      operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v36,
      bIgnoreCasea);
    *((_DWORD *)this + 70) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 34);
    utl::_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>::~_OptionalData1<Container::Manager::Core::Details::SpecializationLayer,0>(v69);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v57[0] != v58 )
      operator delete(v57[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( v54 )
      utl::_RefCountBase::_DecStrong(v54);
    if ( v55[0] != v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v50 != v52 )
      operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
    if ( FileName != v46 )
      operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47 != v49 )
      operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
    return v37;
  }
}

```

## disassembly

```asm
0x1800c9334  mov     [rsp-8+arg_8], rdx
0x1800c9339  push    rbp
0x1800c933a  push    rbx
0x1800c933b  push    rsi
0x1800c933c  push    rdi
0x1800c933d  push    r12
0x1800c933f  push    r13
0x1800c9341  push    r14
0x1800c9343  push    r15
0x1800c9345  lea     rbp, [rsp-1A8h]
0x1800c934d  sub     rsp, 2A8h
0x1800c9354  mov     r15, r8
0x1800c9357  mov     rsi, rcx
0x1800c935a  lea     rax, [rsp+2E0h+var_280]
0x1800c935f  mov     [rsp+2E0h+var_290], rax
0x1800c9364  lea     rax, [rsp+2E0h+var_280]
0x1800c9369  mov     [rsp+2E0h+var_288], rax
0x1800c936e  xor     eax, eax
0x1800c9370  mov     [rsp+2E0h+var_280], ax
0x1800c9375  lea     r8, [rsp+2E0h+var_290]
0x1800c937a  xor     edx, edx
0x1800c937c  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800c9381  mov     edi, eax
0x1800c9383  test    eax, eax
0x1800c9385  jns     short loc_1800C93C4
0x1800c9387  mov     rcx, [rbp+1E8h]; this
0x1800c938e  mov     r9d, eax; char *
0x1800c9391  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9398  mov     edx, 1DCh; void *
0x1800c939d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c93a2  mov     rcx, [rsp+2E0h+var_290]; void *
0x1800c93a7  lea     rax, [rsp+2E0h+var_280]
0x1800c93ac  cmp     rcx, rax
0x1800c93af  jz      short loc_1800C93BD
0x1800c93b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c93b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c93bd  mov     eax, edi
0x1800c93bf  jmp     loc_1800CA2C9
0x1800c93c4  lea     rax, [rsp+2E0h+var_2A0]
0x1800c93c9  mov     [rsp+2E0h+FileName], rax
0x1800c93ce  lea     rax, [rsp+2E0h+var_2A0]
0x1800c93d3  mov     [rsp+2E0h+var_2A8], rax
0x1800c93d8  xor     eax, eax
0x1800c93da  mov     [rsp+2E0h+var_2A0], ax
0x1800c93df  lea     rdx, [rsp+2E0h+FileName]
0x1800c93e4  mov     rcx, rsi
0x1800c93e7  call    Container__Manager__Core__Details___anonymous_namespace___GetDeploymentPath
0x1800c93ec  mov     edi, eax
0x1800c93ee  test    eax, eax
0x1800c93f0  jns     short loc_1800C9442
0x1800c93f2  mov     rcx, [rbp+1E8h]; this
0x1800c93f9  mov     r9d, eax; char *
0x1800c93fc  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9403  mov     edx, 1E0h; void *
0x1800c9408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c940d  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800c9414  lea     rax, [rsp+2E0h+var_2A0]
0x1800c9419  mov     rcx, [rsp+2E0h+FileName]; void *
0x1800c941e  cmp     rcx, rax
0x1800c9421  jz      short loc_1800C942B
0x1800c9423  mov     rdx, rbx; struct std::nothrow_t *
0x1800c9426  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c942b  mov     rcx, [rsp+2E0h+var_290]
0x1800c9430  lea     rax, [rsp+2E0h+var_280]
0x1800c9435  cmp     rcx, rax
0x1800c9438  jz      short loc_1800C93BD
0x1800c943a  mov     rdx, rbx
0x1800c943d  jmp     loc_1800C93B8
0x1800c9442  lea     rax, [rbp+1E0h+var_260]
0x1800c9446  mov     [rsp+2E0h+var_270], rax
0x1800c944b  lea     rax, [rbp+1E0h+var_260]
0x1800c944f  mov     [rsp+2E0h+var_268], rax
0x1800c9454  xor     eax, eax
0x1800c9456  mov     [rbp+1E0h+var_260], ax
0x1800c945a  test    byte ptr [rsi+0E4h], 4
0x1800c9461  jz      short loc_1800C94BA
0x1800c9463  lea     r8, [rsp+2E0h+var_270]
0x1800c9468  lea     edx, [rax+4]
0x1800c946b  mov     rcx, rsi
0x1800c946e  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800c9473  mov     edi, eax
0x1800c9475  test    eax, eax
0x1800c9477  jns     short loc_1800C94BA
0x1800c9479  mov     edx, 1E8h; void *
0x1800c947e  mov     r9d, edi; char *
0x1800c9481  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9488  mov     rcx, [rbp+1E8h]; this
0x1800c948f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9494  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800c949b  mov     rcx, [rsp+2E0h+var_270]; void *
0x1800c94a0  lea     rax, [rbp+1E0h+var_260]
0x1800c94a4  cmp     rcx, rax
0x1800c94a7  jz      loc_1800C9414
0x1800c94ad  mov     rdx, rbx; struct std::nothrow_t *
0x1800c94b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c94b5  jmp     loc_1800C9414
0x1800c94ba  mov     rcx, [rsp+2E0h+FileName]; FileName
0x1800c94bf  call    cs:__imp_RtlDoesFileExists_U
0x1800c94c6  nop     dword ptr [rax+rax+00h]
0x1800c94cb  lea     rcx, [rsp+2E0h+FileName]; this
0x1800c94d0  test    al, al
0x1800c94d2  jz      loc_1800C964F
0x1800c94d8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800c94e0  movdqu  xmmword ptr [rbp+1E0h+var_1B0], xmm0
0x1800c94e5  mov     [rbp+1E0h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x1800c94ed  lea     r9, asc_1801D183C; "*"
0x1800c94f4  lea     r8, [rbp+1E0h+var_1B0]
0x1800c94f8  mov     edx, 1
0x1800c94fd  call    ?EnumerateDirectory@Csl@@YAJAEBVPath@1@W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectory(Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x1800c9502  mov     edi, eax
0x1800c9504  test    eax, eax
0x1800c9506  jns     short loc_1800C9531
0x1800c9508  mov     edx, 1F6h; void *
0x1800c950d  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9514  mov     r9d, edi; char *
0x1800c9517  mov     rcx, [rbp+1E8h]; this
0x1800c951e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9523  lea     rcx, [rbp+1E0h+var_1B0]
0x1800c9527  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800c952c  jmp     loc_1800C9494
0x1800c9531  mov     rbx, [rbp+1E0h+var_1B0]
0x1800c9535  cmp     rbx, [rbp+1E0h+var_1B0+8]
0x1800c9539  jz      loc_1800C95DC
0x1800c953f  mov     rax, [rsp+2E0h+var_290]
0x1800c9544  mov     [rbp+1E0h+var_250], rax
0x1800c9548  mov     rcx, [rsp+2E0h+var_288]
0x1800c954d  sub     rcx, rax
0x1800c9550  sar     rcx, 1
0x1800c9553  mov     [rbp+1E0h+var_248], rcx
0x1800c9557  mov     rax, [rbx]
0x1800c955a  mov     [rbp+1E0h+var_198], rax
0x1800c955e  mov     rcx, [rbx+8]
0x1800c9562  sub     rcx, rax
0x1800c9565  sar     rcx, 1
0x1800c9568  mov     [rbp+1E0h+var_190], rcx
0x1800c956c  lea     rdx, [rbp+1E0h+var_250]
0x1800c9570  lea     rcx, [rbp+1E0h+var_198]
0x1800c9574  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800c9579  test    al, al
0x1800c957b  jnz     short loc_1800C95C9
0x1800c957d  mov     rax, [rsp+2E0h+var_270]
0x1800c9582  mov     [rbp+1E0h+var_188], rax
0x1800c9586  mov     rcx, [rsp+2E0h+var_268]
0x1800c958b  sub     rcx, rax
0x1800c958e  sar     rcx, 1
0x1800c9591  mov     [rbp+1E0h+var_180], rcx
0x1800c9595  mov     rax, [rbx]
0x1800c9598  mov     [rbp+1E0h+var_1E0], rax
0x1800c959c  mov     rcx, [rbx+8]
0x1800c95a0  sub     rcx, rax
0x1800c95a3  sar     rcx, 1
0x1800c95a6  mov     [rbp+1E0h+var_1D8], rcx
0x1800c95aa  lea     rdx, [rbp+1E0h+var_188]
0x1800c95ae  lea     rcx, [rbp+1E0h+var_1E0]
0x1800c95b2  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800c95b7  test    al, al
0x1800c95b9  jnz     short loc_1800C95C9
0x1800c95bb  mov     rcx, rbx; this
0x1800c95be  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x1800c95c3  mov     edi, eax
0x1800c95c5  test    eax, eax
0x1800c95c7  js      short loc_1800C95D2
0x1800c95c9  add     rbx, 20h ; ' '
0x1800c95cd  jmp     loc_1800C9535
0x1800c95d2  mov     edx, 1FDh
0x1800c95d7  jmp     loc_1800C950D
0x1800c95dc  lea     rcx, [rbp+1E0h+var_1B0]
0x1800c95e0  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800c95e5  lea     rax, [rbp+1E0h+var_230]
0x1800c95e9  mov     [rbp+1E0h+var_240], rax
0x1800c95ed  lea     rax, [rbp+1E0h+var_230]
0x1800c95f1  mov     [rbp+1E0h+var_238], rax
0x1800c95f5  xor     eax, eax
0x1800c95f7  mov     [rbp+1E0h+var_230], ax
0x1800c95fb  lea     rdx, [rbp+1E0h+var_240]
0x1800c95ff  lea     rcx, [rsp+2E0h+FileName]
0x1800c9604  call    Container__Manager__Core__Details___anonymous_namespace___GetBindingsPath
0x1800c9609  mov     edi, eax
0x1800c960b  test    eax, eax
0x1800c960d  jns     short loc_1800C9666
0x1800c960f  mov     rcx, [rbp+1E8h]; this
0x1800c9616  mov     r9d, eax; char *
0x1800c9619  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9620  mov     edx, 209h; void *
0x1800c9625  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c962a  mov     rcx, [rbp+1E0h+var_240]; void *
0x1800c962e  lea     rax, [rbp+1E0h+var_230]
0x1800c9632  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800c9639  cmp     rcx, rax
0x1800c963c  jz      loc_1800C949B
0x1800c9642  mov     rdx, rbx; struct std::nothrow_t *
0x1800c9645  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c964a  jmp     loc_1800C949B
0x1800c964f  xor     edx, edx; struct Path *
0x1800c9651  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x1800c9656  mov     edi, eax
0x1800c9658  test    eax, eax
0x1800c965a  jns     short loc_1800C95E5
0x1800c965c  mov     edx, 204h
0x1800c9661  jmp     loc_1800C947E
0x1800c9666  lea     rcx, [rbp+1E0h+var_250]
0x1800c966a  call    ??$make_shared@VBindingStore@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@VBindingStore@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::BindingStore,>(void)
0x1800c966f  mov     r12, [rbp+1E0h+var_250]
0x1800c9673  test    r12, r12
0x1800c9676  jz      loc_1800CA236
0x1800c967c  lea     rdx, [rbp+1E0h+var_240]; struct Path *
0x1800c9680  mov     rcx, r12; this
0x1800c9683  call    ?Initialize@BindingStore@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::BindingStore::Initialize(Csl::Path const &)
0x1800c9688  mov     edi, eax
0x1800c968a  test    eax, eax
0x1800c968c  jns     short loc_1800C96BE
0x1800c968e  mov     rcx, [rbp+1E8h]; this
0x1800c9695  mov     r9d, eax; char *
0x1800c9698  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c969f  mov     edx, 210h; void *
0x1800c96a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c96a9  nop
0x1800c96aa  mov     rcx, [rbp+1E0h+var_248]; this
0x1800c96ae  test    rcx, rcx
0x1800c96b1  jz      short loc_1800C96B9
0x1800c96b3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800c96b8  nop
0x1800c96b9  jmp     loc_1800C962A
0x1800c96be  xor     r13d, r13d
0x1800c96c1  xor     edi, edi
0x1800c96c3  lea     r14, [rsi+10h]
0x1800c96c7  mov     rcx, [rsp+2E0h+FileName]; lpString1
0x1800c96cc  mov     r9, [r14+8]
0x1800c96d0  sub     r9, [r14]
0x1800c96d3  sar     r9, 1; cchCount2
0x1800c96d6  mov     rdx, [rsp+2E0h+var_2A8]
0x1800c96db  sub     rdx, rcx
0x1800c96de  sar     rdx, 1; cchCount1
0x1800c96e1  mov     [rsp+2E0h+bIgnoreCase], 1; unsigned int
0x1800c96e9  mov     r8, [r14]; lpString2
0x1800c96ec  call    cs:__imp_CompareStringOrdinal
0x1800c96f3  nop     dword ptr [rax+rax+00h]
0x1800c96f8  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800c96ff  cmp     eax, 2
0x1800c9702  jz      loc_1800C990B
0x1800c9708  lea     rax, [rbp+1E0h+var_1C0]
0x1800c970c  mov     [rbp+1E0h+var_1D0], rax
0x1800c9710  lea     rax, [rbp+1E0h+var_1C0]
0x1800c9714  mov     [rbp+1E0h+var_1C8], rax
0x1800c9718  xor     eax, eax
0x1800c971a  mov     [rbp+1E0h+var_1C0], ax
0x1800c971e  lea     rdx, [rbp+1E0h+var_1D0]
0x1800c9722  mov     rcx, r14
0x1800c9725  call    Container__Manager__Core__Details___anonymous_namespace___GetBindingsPath
0x1800c972a  mov     r14d, eax
0x1800c972d  test    eax, eax
0x1800c972f  jns     loc_1800C97DD
0x1800c9735  mov     rcx, [rbp+1E8h]; this
0x1800c973c  mov     r9d, eax; char *
0x1800c973f  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800c9746  mov     edx, 21Ah; void *
0x1800c974b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9750  mov     rcx, [rbp+1E0h+var_1D0]; void *
0x1800c9754  lea     rax, [rbp+1E0h+var_1C0]
0x1800c9758  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800c975f  cmp     rcx, rax
0x1800c9762  jz      short loc_1800C976D
0x1800c9764  mov     rdx, rbx; struct std::nothrow_t *
0x1800c9767  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c976c  nop
0x1800c976d  mov     rcx, [rbp+1E0h+var_248]; this
0x1800c9771  test    rcx, rcx
0x1800c9774  jz      short loc_1800C977C
0x1800c9776  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800c977b  nop
0x1800c977c  lea     rax, [rbp+1E0h+var_230]
0x1800c9780  mov     rcx, [rbp+1E0h+var_240]; void *
0x1800c9784  cmp     rcx, rax
0x1800c9787  jz      short loc_1800C9791
0x1800c9789  mov     rdx, rbx; struct std::nothrow_t *
0x1800c978c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c9791  lea     rax, [rbp+1E0h+var_260]
0x1800c9795  mov     rcx, [rsp+2E0h+var_270]; void *
0x1800c979a  cmp     rcx, rax
0x1800c979d  jz      short loc_1800C97A7
0x1800c979f  mov     rdx, rbx; struct std::nothrow_t *
0x1800c97a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c97a7  lea     rax, [rsp+2E0h+var_2A0]
0x1800c97ac  mov     rcx, [rsp+2E0h+FileName]; void *
0x1800c97b1  cmp     rcx, rax
0x1800c97b4  jz      short loc_1800C97BE
0x1800c97b6  mov     rdx, rbx; struct std::nothrow_t *
0x1800c97b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c97be  mov     rcx, [rsp+2E0h+var_290]; void *
0x1800c97c3  lea     rax, [rsp+2E0h+var_280]
0x1800c97c8  cmp     rcx, rax
0x1800c97cb  jz      short loc_1800C97D5
0x1800c97cd  mov     rdx, rbx; struct std::nothrow_t *
0x1800c97d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c97d5  mov     eax, r14d
0x1800c97d8  jmp     loc_1800CA2C9
0x1800c97dd  mov     rcx, [rbp+1E0h+var_1D0]; FileName
0x1800c97e1  call    cs:__imp_RtlDoesFileExists_U
0x1800c97e8  nop     dword ptr [rax+rax+00h]
0x1800c97ed  test    al, al
  ... truncated ...
```
