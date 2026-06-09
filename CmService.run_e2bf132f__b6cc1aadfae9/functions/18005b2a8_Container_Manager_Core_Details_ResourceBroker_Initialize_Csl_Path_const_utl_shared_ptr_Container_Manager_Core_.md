# Container::Manager::Core::Details::ResourceBroker::Initialize(Csl::Path const &,utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &,utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> const &,utl::shared_ptr<Container::Manager::Core::Details::ConfigurationBuilder> const &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &,utl::shared_ptr<Container::Manager::Core::Details::LogManager> const &)

- ea: `0x18005b2a8`
- end: `0x18005b978`
- name: `?Initialize@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@AEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@9@AEBV?$shared_ptr@VConfigurationBuilder@Details@Core@Manager@Container@@@9@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@9@AEBV?$shared_ptr@VLogManager@Details@Core@Manager@Container@@@9@@Z`
- size: `1744`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180074f90`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x1800471dc`
- `0x180056330`
- `0x18005b2a8`
- `0x180083ea0`
- `0x1800c821c`
- `0x1800df82c`
- `0x1800eb50c`
- `0x1800ed98c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005b53d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005b53d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005b626`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005b82a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005b626`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005b82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b614`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b5dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b634`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b5dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b509`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b6f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b83e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b8e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b94e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b509`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b6f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b83e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b8e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b94e`

## string_xrefs

- `0x18005b301`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b36c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b3cc`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b43d`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b4ad`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b555`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b85b`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b8ce`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b917`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005b934`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 Container::Manager::Core::Details::ResourceBroker::Initialize(HKEY *pv, __int64 a2, __int64 a3, ...)
{
  HKEY v4; // rdi
  int v5; // eax
  unsigned int LastError; // ebx
  Container::Manager::Core::Details::BaseImageManager *v8; // rax
  const struct Path *v9; // rdx
  Container::Manager::Core::Details::BaseImageManager *v10; // r15
  int v11; // eax
  _QWORD *v12; // rax
  _QWORD *v13; // r12
  int v14; // eax
  HKEY v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // r13
  int v18; // eax
  utl::_RefCountBase *v19; // rcx
  _QWORD *v20; // rax
  const struct Path *v21; // rdx
  _QWORD *v22; // rsi
  int v23; // eax
  HKEY v24; // rcx
  utl::_RefCountBase *v25; // rcx
  HKEY v26; // rcx
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v28; // r9
  HKEY v29; // rcx
  utl::_RefCountBase *v30; // rcx
  HKEY *v31; // rax
  DWORD v32; // edi
  HKEY *v33; // rax
  DWORD v34; // esi
  Container::Manager::Core::Details::BaseImageManager *v35; // rax
  _QWORD *v36; // r15
  HKEY v37; // rcx
  _QWORD *v38; // r15
  utl::_RefCountBase *v39; // rcx
  _QWORD *v40; // r15
  HKEY v41; // rcx
  Container::Manager::Core::Details::PolicyManager *v42; // rcx
  utl::_RefCountBase *v43; // rax
  utl::_RefCountBase *v44; // rcx
  __int64 v45; // rcx
  utl::_RefCountBase *v46; // rax
  utl::_RefCountBase *v47; // rcx
  __int64 v48; // rcx
  utl::_RefCountBase *v49; // rax
  utl::_RefCountBase *v50; // rcx
  Container::Manager::Core::Details::SystemConfigurationManager *v51; // rcx
  utl::_RefCountBase *v52; // rax
  utl::_RefCountBase *v53; // rcx
  __int64 v54; // rcx
  utl::_RefCountBase *v55; // rax
  utl::_RefCountBase *v56; // rcx
  utl::_RefCountBase *v57; // rcx
  HKEY v58; // rcx
  HKEY v59; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  char v61; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  _QWORD *v63; // [rsp+90h] [rbp+50h]
  HKEY v64; // [rsp+98h] [rbp+58h] BYREF
  va_list va; // [rsp+98h] [rbp+58h]
  va_list va1; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v64 = va_arg(va1, HKEY);
  v4 = 0;
  hKey = 0;
  LOBYTE(v64) = 0;
  v5 = Csl::CreateRegistryKey(pv, Container::Manager::Core::g_registryRoot, 131097, &hKey);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBBE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v5,
      (int)va);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return LastError;
  }
  v8 = (Container::Manager::Core::Details::BaseImageManager *)operator new(
                                                                0x10u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
  v10 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC2,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      (int)va);
    goto LABEL_97;
  }
  *(_QWORD *)v8 = 0;
  *((_QWORD *)v8 + 1) = 0;
  v11 = Container::Manager::Core::Details::BaseImageManager::Initialize(v8, v9);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v11,
      (int)va);
LABEL_9:
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v10);
LABEL_10:
    operator delete(v10, (const struct std::nothrow_t *)0x10);
    goto LABEL_3;
  }
  v12 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      (int)va);
LABEL_94:
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v10);
LABEL_90:
    operator delete(v10, (const struct std::nothrow_t *)0x10);
LABEL_97:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  *(_BYTE *)v12 = 0;
  v12[1] = 0;
  v14 = Container::Manager::Core::Details::StorageManager::Initialize(
          (Container::Manager::Core::Details::StorageManager *)v12,
          (const struct Path *)&Container::Manager::Core::g_registryRoot);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v14,
      (int)va);
LABEL_14:
    v15 = (HKEY)v13[1];
    if ( v15 )
      RegCloseKey(v15);
    operator delete(v13, (const struct std::nothrow_t *)0x10);
    goto LABEL_9;
  }
  v16 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v16;
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      (int)va);
    v59 = (HKEY)v13[1];
    if ( v59 )
      RegCloseKey(v59);
    operator delete(v13, (const struct std::nothrow_t *)0x10);
    goto LABEL_94;
  }
  *v16 = 0;
  v16[1] = 0;
  v18 = Container::Manager::Core::Details::LayerManager::Initialize(
          (Container::Manager::Core::Details::LayerManager *)v16,
          (const struct Path *)&Container::Manager::Core::g_registryRoot);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v18,
      (int)va);
    v19 = (utl::_RefCountBase *)v17[1];
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    operator delete(v17, (const struct std::nothrow_t *)0x10);
    goto LABEL_14;
  }
  v20 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v20;
  v63 = v20;
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      (int)va);
    v57 = (utl::_RefCountBase *)v17[1];
    if ( v57 )
      utl::_RefCountBase::_DecStrong(v57);
    operator delete(v17, (const struct std::nothrow_t *)0x10);
    v58 = (HKEY)v13[1];
    if ( v58 )
      RegCloseKey(v58);
    operator delete(v13, (const struct std::nothrow_t *)0x10);
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v10);
    goto LABEL_90;
  }
  *(_BYTE *)v20 = 0;
  v20[1] = 0;
  v23 = Container::Manager::Core::Details::SnapshotManager::Initialize(
          (Container::Manager::Core::Details::SnapshotManager *)v20,
          v21);
  LastError = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v23,
      (int)va);
    v24 = (HKEY)v22[1];
    if ( v24 )
      RegCloseKey(v24);
    operator delete(v22, (const struct std::nothrow_t *)0x10);
    v25 = (utl::_RefCountBase *)v17[1];
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
LABEL_28:
    operator delete(v17, (const struct std::nothrow_t *)0x10);
    v26 = (HKEY)v13[1];
    if ( v26 )
      RegCloseKey(v26);
    operator delete(v13, (const struct std::nothrow_t *)0x10);
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v10);
    goto LABEL_10;
  }
  ThreadpoolWork = CreateThreadpoolWork(Container::Manager::Core::Details::ResourceBroker::CleanupWorkThread, pv, 0);
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBDE,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                  v28);
    v29 = (HKEY)v22[1];
    if ( v29 )
      RegCloseKey(v29);
    operator delete(v22, (const struct std::nothrow_t *)0x10);
    v30 = (utl::_RefCountBase *)v17[1];
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    goto LABEL_28;
  }
  v31 = pv + 1;
  if ( pv + 1 == &hKey )
  {
    v4 = hKey;
  }
  else
  {
    v64 = *v31;
    if ( v64 )
    {
      v32 = GetLastError();
      RegCloseKey(v64);
      SetLastError(v32);
      v31 = pv + 1;
      v4 = 0;
    }
    *v31 = hKey;
  }
  v33 = pv + 5;
  if ( pv + 5 != (HKEY *)&v61 )
  {
    v64 = *v33;
    if ( v64 )
    {
      v34 = GetLastError();
      CloseThreadpoolWork((PTP_WORK)v64);
      SetLastError(v34);
      v22 = v63;
      v33 = pv + 5;
    }
    *v33 = (HKEY)ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  v64 = pv[28];
  v35 = (Container::Manager::Core::Details::BaseImageManager *)v64;
  pv[28] = (HKEY)v10;
  if ( v35 )
  {
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v35);
    operator delete(v64, (const struct std::nothrow_t *)0x10);
  }
  v36 = pv[9];
  pv[9] = (HKEY)v13;
  if ( v36 )
  {
    v37 = (HKEY)v36[1];
    if ( v37 )
      RegCloseKey(v37);
    operator delete(v36, (const struct std::nothrow_t *)0x10);
  }
  v38 = pv[14];
  pv[14] = (HKEY)v17;
  if ( v38 )
  {
    v39 = (utl::_RefCountBase *)v38[1];
    if ( v39 )
      utl::_RefCountBase::_DecStrong(v39);
    operator delete(v38, (const struct std::nothrow_t *)0x10);
  }
  v40 = pv[19];
  pv[19] = (HKEY)v22;
  if ( v40 )
  {
    v41 = (HKEY)v40[1];
    if ( v41 )
      RegCloseKey(v41);
    operator delete(v40, (const struct std::nothrow_t *)0x10);
  }
  v42 = Container::Manager::Core::g_policyManager;
  v43 = qword_18021F478;
  if ( qword_18021F478 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F478 + 2);
  pv[33] = (HKEY)v42;
  v44 = (utl::_RefCountBase *)pv[34];
  pv[34] = (HKEY)v43;
  if ( v44 )
    utl::_RefCountBase::_DecStrong(v44);
  v45 = Container::Manager::Core::g_computeReaper;
  v46 = qword_18021F498;
  if ( qword_18021F498 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F498 + 2);
  pv[35] = (HKEY)v45;
  v47 = (utl::_RefCountBase *)pv[36];
  pv[36] = (HKEY)v46;
  if ( v47 )
    utl::_RefCountBase::_DecStrong(v47);
  v48 = Container::Manager::Core::g_configurationBuilder;
  v49 = qword_18021F4F8;
  if ( qword_18021F4F8 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F4F8 + 2);
  pv[37] = (HKEY)v48;
  v50 = (utl::_RefCountBase *)pv[38];
  pv[38] = (HKEY)v49;
  if ( v50 )
    utl::_RefCountBase::_DecStrong(v50);
  v51 = Container::Manager::Core::g_systemConfigurationManager;
  v52 = qword_18021F488;
  if ( qword_18021F488 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F488 + 2);
  pv[39] = (HKEY)v51;
  v53 = (utl::_RefCountBase *)pv[40];
  pv[40] = (HKEY)v52;
  if ( v53 )
    utl::_RefCountBase::_DecStrong(v53);
  v54 = Container::Manager::Core::g_logManager;
  v55 = qword_18021F538;
  if ( qword_18021F538 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F538 + 2);
  pv[41] = (HKEY)v54;
  v56 = (utl::_RefCountBase *)pv[42];
  pv[42] = (HKEY)v55;
  if ( v56 )
    utl::_RefCountBase::_DecStrong(v56);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( v4 )
    RegCloseKey(v4);
  return 0;
}

```

## disassembly

```asm
0x18005b2a8  mov     r11, rsp
0x18005b2ab  mov     [r11+8], rbx
0x18005b2af  mov     [r11+20h], r9
0x18005b2b3  mov     [r11+18h], r8
0x18005b2b7  push    rbp
0x18005b2b8  push    rsi
0x18005b2b9  push    rdi
0x18005b2ba  push    r12
0x18005b2bc  push    r13
0x18005b2be  push    r14
0x18005b2c0  push    r15
0x18005b2c2  mov     rbp, rsp
0x18005b2c5  sub     rsp, 40h
0x18005b2c9  mov     r14, rcx
0x18005b2cc  xor     edi, edi
0x18005b2ce  mov     [rbp+hKey], rdi
0x18005b2d2  mov     byte ptr [rbp+arg_18], dil
0x18005b2d6  lea     rax, [rbp+arg_18]
0x18005b2da  mov     [r11-58h], rax
0x18005b2de  lea     r9, [rbp+hKey]
0x18005b2e2  mov     r8d, 20019h
0x18005b2e8  mov     rdx, cs:?g_registryRoot@Core@Manager@Container@@3VPath@Csl@@A; Csl::Path Container::Manager::Core::g_registryRoot
0x18005b2ef  call    ?CreateRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@AEA_N@Z; Csl::CreateRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &,bool &)
0x18005b2f4  mov     ebx, eax
0x18005b2f6  test    eax, eax
0x18005b2f8  jns     short loc_18005B32E
0x18005b2fa  mov     rcx, [rbp+38h]; this
0x18005b2fe  mov     r9d, eax; char *
0x18005b301  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b308  mov     edx, 0BBEh; void *
0x18005b30d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b312  mov     rcx, [rbp+hKey]; hKey
0x18005b316  test    rcx, rcx
0x18005b319  jz      short loc_18005B327
0x18005b31b  call    cs:__imp_RegCloseKey
0x18005b322  nop     dword ptr [rax+rax+00h]
0x18005b327  mov     eax, ebx
0x18005b329  jmp     loc_18005B95F
0x18005b32e  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005b335  mov     rdx, r13; struct std::nothrow_t *
0x18005b338  mov     esi, 10h
0x18005b33d  mov     ecx, esi; unsigned __int64
0x18005b33f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b344  mov     r15, rax
0x18005b347  test    rax, rax
0x18005b34a  jz      loc_18005B92A
0x18005b350  mov     [rax], rdi
0x18005b353  mov     [rax+8], rdi
0x18005b357  mov     rcx, rax; pv
0x18005b35a  call    ?Initialize@BaseImageManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::BaseImageManager::Initialize(Csl::Path const &)
0x18005b35f  mov     ebx, eax
0x18005b361  test    eax, eax
0x18005b363  jns     short loc_18005B392
0x18005b365  mov     rcx, [rbp+38h]; this
0x18005b369  mov     r9d, eax; char *
0x18005b36c  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b373  mov     edx, 0BC4h; void *
0x18005b378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b37d  mov     rcx, r15; this
0x18005b380  call    ??1BaseImageManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(void)
0x18005b385  mov     rdx, rsi; struct std::nothrow_t *
0x18005b388  mov     rcx, r15; void *
0x18005b38b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b390  jmp     short loc_18005B312
0x18005b392  mov     rdx, r13; struct std::nothrow_t *
0x18005b395  mov     rcx, rsi; unsigned __int64
0x18005b398  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b39d  mov     r12, rax
0x18005b3a0  test    rax, rax
0x18005b3a3  jz      loc_18005B90D
0x18005b3a9  mov     [rax], dil
0x18005b3ac  mov     [rax+8], rdi
0x18005b3b0  lea     rdx, ?g_registryRoot@Core@Manager@Container@@3VPath@Csl@@A; struct Path *
0x18005b3b7  mov     rcx, rax; this
0x18005b3ba  call    ?Initialize@StorageManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::StorageManager::Initialize(Csl::Path const &)
0x18005b3bf  mov     ebx, eax
0x18005b3c1  test    eax, eax
0x18005b3c3  jns     short loc_18005B403
0x18005b3c5  mov     rcx, [rbp+38h]; this
0x18005b3c9  mov     r9d, eax; char *
0x18005b3cc  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b3d3  mov     edx, 0BCAh; void *
0x18005b3d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b3dd  mov     rcx, [r12+8]; hKey
0x18005b3e2  test    rcx, rcx
0x18005b3e5  jz      short loc_18005B3F3
0x18005b3e7  call    cs:__imp_RegCloseKey
0x18005b3ee  nop     dword ptr [rax+rax+00h]
0x18005b3f3  mov     rdx, rsi; struct std::nothrow_t *
0x18005b3f6  mov     rcx, r12; void *
0x18005b3f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b3fe  jmp     loc_18005B37D
0x18005b403  mov     rdx, r13; struct std::nothrow_t *
0x18005b406  mov     rcx, rsi; unsigned __int64
0x18005b409  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b40e  mov     r13, rax
0x18005b411  test    rax, rax
0x18005b414  jz      loc_18005B8C4
0x18005b41a  mov     [rax], rdi
0x18005b41d  mov     [rax+8], rdi
0x18005b421  lea     rdx, ?g_registryRoot@Core@Manager@Container@@3VPath@Csl@@A; struct Path *
0x18005b428  mov     rcx, rax; this
0x18005b42b  call    ?Initialize@LayerManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::LayerManager::Initialize(Csl::Path const &)
0x18005b430  mov     ebx, eax
0x18005b432  test    eax, eax
0x18005b434  jns     short loc_18005B46E
0x18005b436  mov     rcx, [rbp+38h]; this
0x18005b43a  mov     r9d, eax; char *
0x18005b43d  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b444  mov     edx, 0BD0h; void *
0x18005b449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b44e  nop
0x18005b44f  mov     rcx, [r13+8]; this
0x18005b453  test    rcx, rcx
0x18005b456  jz      short loc_18005B45E
0x18005b458  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005b45d  nop
0x18005b45e  mov     rdx, rsi; struct std::nothrow_t *
0x18005b461  mov     rcx, r13; void *
0x18005b464  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b469  jmp     loc_18005B3DD
0x18005b46e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b475  mov     rcx, rsi; unsigned __int64
0x18005b478  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005b47d  mov     rsi, rax
0x18005b480  mov     [rbp+arg_10], rax
0x18005b484  test    rax, rax
0x18005b487  jz      loc_18005B851
0x18005b48d  mov     [rax], dil
0x18005b490  mov     [rax+8], rdi
0x18005b494  mov     rcx, rax; this
0x18005b497  call    ?Initialize@SnapshotManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::SnapshotManager::Initialize(Csl::Path const &)
0x18005b49c  mov     ebx, eax
0x18005b49e  test    eax, eax
0x18005b4a0  jns     loc_18005B530
0x18005b4a6  mov     rcx, [rbp+38h]; this
0x18005b4aa  mov     r9d, eax; char *
0x18005b4ad  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b4b4  mov     edx, 0BD6h; void *
0x18005b4b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b4be  mov     rcx, [rsi+8]; hKey
0x18005b4c2  test    rcx, rcx
0x18005b4c5  jz      short loc_18005B4D3
0x18005b4c7  call    cs:__imp_RegCloseKey
0x18005b4ce  nop     dword ptr [rax+rax+00h]
0x18005b4d3  mov     r14d, 10h
0x18005b4d9  mov     edx, r14d; struct std::nothrow_t *
0x18005b4dc  mov     rcx, rsi; void *
0x18005b4df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b4e4  nop
0x18005b4e5  mov     rcx, [r13+8]; this
0x18005b4e9  test    rcx, rcx
0x18005b4ec  jz      short loc_18005B4F4
0x18005b4ee  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005b4f3  nop
0x18005b4f4  mov     rdx, r14; struct std::nothrow_t *
0x18005b4f7  mov     rcx, r13; void *
0x18005b4fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b4ff  mov     rcx, [r12+8]; hKey
0x18005b504  test    rcx, rcx
0x18005b507  jz      short loc_18005B515
0x18005b509  call    cs:__imp_RegCloseKey
0x18005b510  nop     dword ptr [rax+rax+00h]
0x18005b515  mov     rdx, r14; struct std::nothrow_t *
0x18005b518  mov     rcx, r12; void *
0x18005b51b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b520  mov     rcx, r15; this
0x18005b523  call    ??1BaseImageManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(void)
0x18005b528  mov     rdx, r14
0x18005b52b  jmp     loc_18005B388
0x18005b530  xor     r8d, r8d; pcbe
0x18005b533  mov     rdx, r14; pv
0x18005b536  lea     rcx, ?CleanupWorkThread@ResourceBroker@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005b53d  call    cs:__imp_CreateThreadpoolWork
0x18005b544  nop     dword ptr [rax+rax+00h]
0x18005b549  mov     rbx, rax
0x18005b54c  test    rax, rax
0x18005b54f  jnz     short loc_18005B5A3
0x18005b551  mov     rcx, [rbp+38h]; this
0x18005b555  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005b55c  mov     edx, 0BDEh; void *
0x18005b561  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005b566  mov     ebx, eax
0x18005b568  mov     rcx, [rsi+8]; hKey
0x18005b56c  test    rcx, rcx
0x18005b56f  jz      short loc_18005B57D
0x18005b571  call    cs:__imp_RegCloseKey
0x18005b578  nop     dword ptr [rax+rax+00h]
0x18005b57d  mov     r14d, 10h
0x18005b583  mov     edx, r14d; struct std::nothrow_t *
0x18005b586  mov     rcx, rsi; void *
0x18005b589  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b58e  nop
0x18005b58f  mov     rcx, [r13+8]; this
0x18005b593  test    rcx, rcx
0x18005b596  jz      short loc_18005B59E
0x18005b598  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005b59d  nop
0x18005b59e  jmp     loc_18005B4F4
0x18005b5a3  lea     rax, [r14+8]
0x18005b5a7  lea     rcx, [rbp+hKey]
0x18005b5ab  cmp     rax, rcx
0x18005b5ae  jz      short loc_18005B5F7
0x18005b5b0  mov     rcx, [rax]
0x18005b5b3  mov     [rbp+arg_18], rcx
0x18005b5b7  test    rcx, rcx
0x18005b5ba  jz      short loc_18005B5EE
0x18005b5bc  call    cs:__imp_GetLastError
0x18005b5c3  nop     dword ptr [rax+rax+00h]
0x18005b5c8  mov     edi, eax
0x18005b5ca  mov     rcx, [rbp+arg_18]; hKey
0x18005b5ce  call    cs:__imp_RegCloseKey
0x18005b5d5  nop     dword ptr [rax+rax+00h]
0x18005b5da  mov     ecx, edi; dwErrCode
0x18005b5dc  call    cs:__imp_SetLastError
0x18005b5e3  nop     dword ptr [rax+rax+00h]
0x18005b5e8  lea     rax, [r14+8]
0x18005b5ec  xor     edi, edi
0x18005b5ee  mov     rcx, [rbp+hKey]
0x18005b5f2  mov     [rax], rcx
0x18005b5f5  jmp     short loc_18005B5FB
0x18005b5f7  mov     rdi, [rbp+hKey]
0x18005b5fb  lea     rax, [r14+28h]
0x18005b5ff  lea     rcx, [rbp+var_8]
0x18005b603  cmp     rax, rcx
0x18005b606  jz      short loc_18005B64D
0x18005b608  mov     rcx, [rax]
0x18005b60b  mov     [rbp+arg_18], rcx
0x18005b60f  test    rcx, rcx
0x18005b612  jz      short loc_18005B648
0x18005b614  call    cs:__imp_GetLastError
0x18005b61b  nop     dword ptr [rax+rax+00h]
0x18005b620  mov     esi, eax
0x18005b622  mov     rcx, [rbp+arg_18]; pwk
0x18005b626  call    cs:__imp_CloseThreadpoolWork
0x18005b62d  nop     dword ptr [rax+rax+00h]
0x18005b632  mov     ecx, esi; dwErrCode
0x18005b634  call    cs:__imp_SetLastError
0x18005b63b  nop     dword ptr [rax+rax+00h]
0x18005b640  mov     rsi, [rbp+arg_10]
0x18005b644  lea     rax, [r14+28h]
0x18005b648  mov     [rax], rbx
0x18005b64b  xor     ebx, ebx
0x18005b64d  mov     rax, [r14+0E0h]
0x18005b654  mov     [rbp+arg_18], rax
0x18005b658  mov     [r14+0E0h], r15
0x18005b65f  test    rax, rax
0x18005b662  jz      short loc_18005B67A
0x18005b664  mov     rcx, rax; this
0x18005b667  call    ??1BaseImageManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(void)
0x18005b66c  mov     edx, 10h; struct std::nothrow_t *
0x18005b671  mov     rcx, [rbp+arg_18]; void *
0x18005b675  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b67a  mov     r15, [r14+48h]
0x18005b67e  mov     [r14+48h], r12
0x18005b682  test    r15, r15
0x18005b685  jz      short loc_18005B6AF
0x18005b687  mov     rcx, [r15+8]; hKey
0x18005b68b  test    rcx, rcx
0x18005b68e  jz      short loc_18005B69C
0x18005b690  call    cs:__imp_RegCloseKey
0x18005b697  nop     dword ptr [rax+rax+00h]
0x18005b69c  mov     r12d, 10h
0x18005b6a2  mov     edx, r12d; struct std::nothrow_t *
0x18005b6a5  mov     rcx, r15; void *
0x18005b6a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b6ad  jmp     short loc_18005B6B5
0x18005b6af  mov     r12d, 10h
0x18005b6b5  mov     r15, [r14+70h]
0x18005b6b9  mov     [r14+70h], r13
0x18005b6bd  test    r15, r15
0x18005b6c0  jz      short loc_18005B6DC
0x18005b6c2  mov     rcx, [r15+8]; this
0x18005b6c6  test    rcx, rcx
0x18005b6c9  jz      short loc_18005B6D1
0x18005b6cb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005b6d0  nop
0x18005b6d1  mov     rdx, r12; struct std::nothrow_t *
0x18005b6d4  mov     rcx, r15; void *
0x18005b6d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b6dc  mov     r15, [r14+98h]
0x18005b6e3  mov     [r14+98h], rsi
0x18005b6ea  test    r15, r15
0x18005b6ed  jz      short loc_18005B70F
0x18005b6ef  mov     rcx, [r15+8]; hKey
0x18005b6f3  test    rcx, rcx
0x18005b6f6  jz      short loc_18005B704
0x18005b6f8  call    cs:__imp_RegCloseKey
0x18005b6ff  nop     dword ptr [rax+rax+00h]
0x18005b704  mov     rdx, r12; struct std::nothrow_t *
0x18005b707  mov     rcx, r15; void *
0x18005b70a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b70f  mov     rcx, cs:?g_policyManager@Core@Manager@Container@@3V?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> Container::Manager::Core::g_policyManager
0x18005b716  mov     rax, cs:qword_18021F478
0x18005b71d  test    rax, rax
0x18005b720  jz      short loc_18005B726
0x18005b722  lock inc dword ptr [rax+8]
0x18005b726  mov     [r14+108h], rcx
0x18005b72d  mov     rcx, [r14+110h]; this
0x18005b734  mov     [r14+110h], rax
  ... truncated ...
```
