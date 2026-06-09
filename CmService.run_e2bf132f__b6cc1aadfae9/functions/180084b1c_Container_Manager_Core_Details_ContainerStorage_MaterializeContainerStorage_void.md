# Container::Manager::Core::Details::ContainerStorage::MaterializeContainerStorage(void)

- ea: `0x180084b1c`
- end: `0x18008529b`
- name: `?MaterializeContainerStorage@ContainerStorage@Details@Core@Manager@Container@@AEAAJXZ`
- size: `1919`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerStorage *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800852b0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800103a4`
- `0x180016718`
- `0x180016774`
- `0x18002ed40`
- `0x18002fd88`
- `0x180032a48`
- `0x180032c70`
- `0x180032d0c`
- `0x1800335b8`
- `0x1800342b4`
- `0x180034674`
- `0x180034918`
- `0x18003e9f4`
- `0x1800471dc`
- `0x1800802f0`
- `0x180082270`
- `0x180084b1c`
- `0x180085380`
- `0x180085654`
- `0x180085e1c`
- `0x180088488`
- `0x1801094d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180084c04`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18008509a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800851aa`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180085257`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180084c04`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18008509a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800851aa`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180085257`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084efc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180084efc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008503e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008514e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800851fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008503e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008514e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800851fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180084bc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180084bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085125`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180084de4`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180084de4`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateEmptyGuestStateFile` at `0x180084dbc`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateEmptyGuestStateFile` at `0x180084dbc`

## string_xrefs

- `0x180084f87`: `EncryptionKeyPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Container::Manager::Core::Details::ContainerStorage::MaterializeContainerStorage(
        Container::Manager::Core::Details::ContainerStorage *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  int LastError; // ebx
  struct _SECURITY_ATTRIBUTES *v5; // r8
  const char *v6; // r9
  int DirectoryRecursive; // eax
  __int64 v8; // rdx
  utl::_RefCountBase *v9; // rcx
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  utl::_RefCountBase *v13; // rcx
  Container::Manager::Core::Details::BindingStore *v14; // rcx
  const WCHAR *v15; // r9
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  PCWSTR *v18; // rsi
  HRESULT EmptyGuestStateFile; // eax
  unsigned int v20; // r8d
  __int64 v21; // rdx
  const char *v22; // r9
  const struct Path *v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  RTL_SRWLOCK *v27; // rbx
  int v28; // eax
  __int64 v29; // r8
  int v30; // esi
  __int64 v31; // rdx
  int v33; // eax
  unsigned int v34; // edi
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-D8h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  utl::_RefCountBase *v38; // [rsp+38h] [rbp-C8h]
  void *v39; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v40; // [rsp+48h] [rbp-B8h]
  WCHAR ExistingFileName[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  _QWORD v45[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v46[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v2 = *((_DWORD *)this + 36);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "ContainerStorageMaterialize");
  v46[0] = &CmTraceProvider::ContainerStorageMaterialize::`vftable';
  CmTraceProvider::ContainerStorageMaterialize::StartActivity(
    (CmTraceProvider::ContainerStorageMaterialize *)v46,
    (const struct _GUID *)this,
    v2);
  v3 = Container::Manager::Core::Details::ContainerStorage::DeleteAllFilesystemArtifacts(this);
  LastError = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)v3,
      (int)hKey);
LABEL_78:
    v46[0] = &CmTraceProvider::ContainerStorageMaterialize::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v46);
    return (unsigned int)LastError;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:AI(A;OICIID;FA;;;SY)(A;OICIID;FA;;;BA)(A;OICIID;0x1200a9;;;BU)(A;OICIID;0x1200a9;;;WD)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x624,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
                  v6);
LABEL_5:
    if ( !SecurityDescriptor )
      goto LABEL_78;
    ObjectDescriptor = SecurityDescriptor;
LABEL_7:
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
    goto LABEL_78;
  }
  v45[0] = 24;
  v45[2] = 0;
  v45[1] = SecurityDescriptor;
  DirectoryRecursive = Csl::CreateDirectoryRecursive(
                         (Container::Manager::Core::Details::ContainerStorage *)((char *)this + 48),
                         (const struct Path *)v45,
                         v5);
  LastError = DirectoryRecursive;
  if ( DirectoryRecursive < 0 )
  {
    v8 = 1581;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)DirectoryRecursive,
      (int)hKey);
    goto LABEL_5;
  }
  *((_QWORD *)this + 40) = 0;
  v9 = (utl::_RefCountBase *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = 0;
  if ( v9 )
    utl::_RefCountBase::_DecStrong(v9);
  v10 = (__int64 *)utl::make_shared<Container::Manager::Core::Details::BindingStore,>(&ObjectDescriptor);
  v11 = *v10;
  v12 = v10[1];
  *v10 = 0;
  v10[1] = 0;
  *((_QWORD *)this + 40) = v11;
  v13 = (utl::_RefCountBase *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = v12;
  if ( v13 )
    utl::_RefCountBase::_DecStrong(v13);
  if ( v38 )
    utl::_RefCountBase::_DecStrong(v38);
  v14 = (Container::Manager::Core::Details::BindingStore *)*((_QWORD *)this + 40);
  if ( !v14 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x637,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)0x8007000ELL,
      (int)hKey);
LABEL_27:
    if ( !SecurityDescriptor )
      goto LABEL_78;
    ObjectDescriptor = SecurityDescriptor;
    goto LABEL_7;
  }
  DirectoryRecursive = Container::Manager::Core::Details::BindingStore::Initialize(
                         v14,
                         (Container::Manager::Core::Details::ContainerStorage *)((char *)this + 112));
  LastError = DirectoryRecursive;
  if ( DirectoryRecursive < 0 )
  {
    v8 = 1593;
    goto LABEL_10;
  }
  v15 = ExistingFileName;
  v39 = ExistingFileName;
  v16 = ExistingFileName;
  v40 = ExistingFileName;
  ExistingFileName[0] = 0;
  if ( *((_DWORD *)this + 4) == 1 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v39,
                             *(_QWORD *)(*((_QWORD *)this + 42) + 80LL),
                             (__int64)(*(_QWORD *)(*((_QWORD *)this + 42) + 88LL)
                                     - *(_QWORD *)(*((_QWORD *)this + 42) + 80LL)) >> 1) )
    {
      LastError = -2147024882;
      v17 = 1608;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)LastError,
        (int)hKey);
LABEL_25:
      if ( v39 != ExistingFileName )
        operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_27;
    }
    v16 = v40;
    v15 = (const WCHAR *)v39;
  }
  v18 = (PCWSTR *)((char *)this + 80);
  if ( v16 == v15 )
  {
    EmptyGuestStateFile = HcsCreateEmptyGuestStateFile(*v18);
    LastError = EmptyGuestStateFile;
    if ( EmptyGuestStateFile < 0 )
    {
      v21 = 1197;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)(unsigned int)EmptyGuestStateFile,
        (int)hKey);
      goto LABEL_41;
    }
  }
  else if ( !CopyFileW(v15, *v18, 1) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4B2,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                  v22);
    if ( LastError < 0 )
    {
LABEL_41:
      v17 = 1613;
      goto LABEL_24;
    }
    goto LABEL_35;
  }
  EmptyGuestStateFile = Csl::GrantVmGroupAccess(
                          (Container::Manager::Core::Details::ContainerStorage *)((char *)this + 80),
                          (const struct Path *)0x1201BF,
                          v20);
  LastError = EmptyGuestStateFile;
  if ( EmptyGuestStateFile < 0 )
  {
    v21 = 1207;
    goto LABEL_40;
  }
LABEL_35:
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( *((_DWORD *)this + 36) == 1 )
  {
    v26 = Container::Manager::Core::Details::ContainerStorage::MaterializeVhd(this, (__int64)v42, v23);
    LastError = v26;
    if ( v26 < 0 )
    {
      v25 = 1621;
      goto LABEL_46;
    }
  }
  else
  {
    if ( *((_DWORD *)this + 36) != 2 )
    {
      LastError = -2147418113;
      v24 = 2147549183LL;
      v25 = 1634;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)v24,
        (int)hKey);
      if ( (_BYTE)v44 && v42[0] != &v43 )
        operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_25;
    }
    v26 = Container::Manager::Core::Details::ContainerStorage::MaterializeStorageSpace(this, (__int64)v42);
    LastError = v26;
    if ( v26 < 0 )
    {
      v25 = 1627;
LABEL_46:
      v24 = (unsigned int)v26;
      goto LABEL_47;
    }
  }
  v27 = (RTL_SRWLOCK *)((char *)this + 232);
  AcquireSRWLockExclusive((PSRWLOCK)this + 29);
  if ( *((_DWORD *)this + 60) == 3 )
  {
    v34 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x6A0,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
            (const char *)0x12F,
            (unsigned int)hKey);
    if ( v27 )
      ReleaseSRWLockExclusive(v27);
    if ( (_BYTE)v44 && v42[0] != &v43 )
      operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v39 != ExistingFileName )
      operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
    if ( SecurityDescriptor )
    {
      ObjectDescriptor = SecurityDescriptor;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
    }
    v46[0] = &CmTraceProvider::ContainerStorageMaterialize::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v46);
    return v34;
  }
  else
  {
    ObjectDescriptor = 0;
    v28 = Csl::RegistryTransaction::Initialize((Csl::RegistryTransaction *)&ObjectDescriptor);
    v30 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x671,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v28,
        (int)hKey);
LABEL_68:
      Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&ObjectDescriptor);
      if ( this != (Container::Manager::Core::Details::ContainerStorage *)-232LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
      if ( (_BYTE)v44 && v42[0] != &v43 )
        operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v39 != ExistingFileName )
        operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
      if ( SecurityDescriptor )
      {
        hKey = (HKEY)SecurityDescriptor;
        DestroyPrivateObjectSecurity((PSECURITY_DESCRIPTOR *)&hKey);
      }
      LastError = v30;
      goto LABEL_78;
    }
    hKey = 0;
    v30 = Container::Manager::Core::Details::ContainerStorage::OpenBackingRegistryKeyTransacted(
            this,
            &ObjectDescriptor,
            v29,
            &hKey);
    if ( v30 < 0 )
    {
      v31 = 1656;
      goto LABEL_66;
    }
    if ( (*((_BYTE *)this + 272) & 1) != 0 )
    {
      if ( !(_BYTE)v44 )
        __int2c();
      v30 = Csl::RegistryKey::SetPathValue((Csl::RegistryKey *)&hKey, L"EncryptionKeyPath", (const struct Path *)v42);
      if ( v30 < 0 )
      {
        v31 = 1662;
        goto LABEL_66;
      }
    }
    v30 = Csl::RegistryKey::DeleteValue((Csl::RegistryKey *)&hKey, L"MaxSizeInBytes");
    if ( v30 < 0 )
    {
      v31 = 1668;
      goto LABEL_66;
    }
    v30 = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&hKey, L"State", 2u);
    if ( v30 < 0 )
    {
      v31 = 1672;
      goto LABEL_66;
    }
    v30 = Csl::RegistryTransaction::Commit((Csl::RegistryTransaction *)&ObjectDescriptor);
    if ( v30 < 0 )
    {
      v31 = 1675;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v30,
        (int)hKey);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_68;
    }
    if ( (*((_BYTE *)this + 272) & 2) == 0 )
    {
      v33 = Csl::RegistryKey::Flush((Csl::RegistryKey *)&hKey);
      if ( v33 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x692,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
          (const char *)(unsigned int)v33,
          (int)hKey);
    }
    *((_DWORD *)this + 60) = 2;
    if ( (*((_BYTE *)this + 272) & 1) != 0 )
      utl::optional<Csl::Path>::operator=((char *)this + 280, v42);
    if ( hKey )
      RegCloseKey(hKey);
    Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&ObjectDescriptor);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v46, 0);
    if ( this != (Container::Manager::Core::Details::ContainerStorage *)-232LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 29);
    if ( (_BYTE)v44 && v42[0] != &v43 )
      operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v39 != ExistingFileName )
      operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
    if ( SecurityDescriptor )
    {
      ObjectDescriptor = SecurityDescriptor;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
    }
    v46[0] = &CmTraceProvider::ContainerStorageMaterialize::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v46);
    return 0;
  }
}

```

## disassembly

```asm
0x180084b1c  push    rbp
0x180084b1e  push    rbx
0x180084b1f  push    rsi
0x180084b20  push    rdi
0x180084b21  push    r13
0x180084b23  push    r14
0x180084b25  lea     rbp, [rsp-108h]
0x180084b2d  sub     rsp, 208h
0x180084b34  mov     rax, cs:__security_cookie
0x180084b3b  xor     rax, rsp
0x180084b3e  mov     [rbp+130h+var_40], rax
0x180084b45  mov     rdi, rcx
0x180084b48  mov     ebx, [rcx+90h]
0x180084b4e  lea     rdx, aContainerstora_0; "ContainerStorageMaterialize"
0x180084b55  lea     rcx, [rbp+130h+var_190]
0x180084b59  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180084b5e  lea     r13, ??_7ContainerStorageMaterialize@CmTraceProvider@@6B@; const CmTraceProvider::ContainerStorageMaterialize::`vftable'
0x180084b65  mov     [rbp+130h+var_190], r13
0x180084b69  mov     r8d, ebx; unsigned int
0x180084b6c  mov     rdx, rdi; struct _GUID *
0x180084b6f  lea     rcx, [rbp+130h+var_190]; this
0x180084b73  call    ?StartActivity@ContainerStorageMaterialize@CmTraceProvider@@QEAAXAEBU_GUID@@K@Z; CmTraceProvider::ContainerStorageMaterialize::StartActivity(_GUID const &,ulong)
0x180084b78  nop
0x180084b79  mov     rcx, rdi; this
0x180084b7c  call    ?DeleteAllFilesystemArtifacts@ContainerStorage@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::ContainerStorage::DeleteAllFilesystemArtifacts(void)
0x180084b81  mov     ebx, eax
0x180084b83  xor     r14d, r14d
0x180084b86  test    eax, eax
0x180084b88  jns     short loc_180084BAA
0x180084b8a  mov     rcx, [rbp+138h]; this
0x180084b91  mov     r9d, eax; char *
0x180084b94  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084b9b  mov     edx, 61Ah; void *
0x180084ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084ba5  jmp     loc_1800850A8
0x180084baa  mov     [rsp+230h+SecurityDescriptor], r14
0x180084baf  xor     r9d, r9d; SecurityDescriptorSize
0x180084bb2  lea     r8, [rsp+230h+SecurityDescriptor]; SecurityDescriptor
0x180084bb7  lea     edx, [r9+1]; StringSDRevision
0x180084bbb  lea     rcx, aOSygSydAiAOici; "O:SYG:SYD:AI(A;OICIID;FA;;;SY)(A;OICIID"...
0x180084bc2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180084bc9  nop     dword ptr [rax+rax+00h]
0x180084bce  test    eax, eax
0x180084bd0  jnz     short loc_180084C15
0x180084bd2  mov     rcx, [rbp+138h]; this
0x180084bd9  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084be0  mov     edx, 624h; void *
0x180084be5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180084bea  mov     ebx, eax
0x180084bec  mov     rcx, [rsp+230h+SecurityDescriptor]
0x180084bf1  test    rcx, rcx
0x180084bf4  jz      loc_1800850A8
0x180084bfa  mov     [rsp+230h+ObjectDescriptor], rcx
0x180084bff  lea     rcx, [rsp+230h+ObjectDescriptor]; ObjectDescriptor
0x180084c04  call    cs:__imp_DestroyPrivateObjectSecurity
0x180084c0b  nop     dword ptr [rax+rax+00h]
0x180084c10  jmp     loc_1800850A8
0x180084c15  mov     [rbp+130h+var_1A8], 18h
0x180084c1d  mov     [rbp+130h+var_198], r14
0x180084c21  mov     rax, [rsp+230h+SecurityDescriptor]
0x180084c26  mov     [rbp+130h+var_1A0], rax
0x180084c2a  lea     rcx, [rdi+30h]; this
0x180084c2e  lea     rdx, [rbp+130h+var_1A8]; struct Path *
0x180084c32  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x180084c37  mov     ebx, eax
0x180084c39  test    eax, eax
0x180084c3b  jns     short loc_180084C5A
0x180084c3d  mov     edx, 62Dh; void *
0x180084c42  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084c49  mov     r9d, eax; char *
0x180084c4c  mov     rcx, [rbp+138h]; this
0x180084c53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084c58  jmp     short loc_180084BEC
0x180084c5a  mov     [rdi+140h], r14
0x180084c61  mov     rcx, [rdi+148h]; this
0x180084c68  mov     [rdi+148h], r14
0x180084c6f  test    rcx, rcx
0x180084c72  jz      short loc_180084C7A
0x180084c74  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180084c79  nop
0x180084c7a  lea     rcx, [rsp+230h+ObjectDescriptor]
0x180084c7f  call    ??$make_shared@VBindingStore@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@VBindingStore@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::BindingStore,>(void)
0x180084c84  mov     rcx, [rax]
0x180084c87  mov     rdx, [rax+8]
0x180084c8b  mov     [rax], r14
0x180084c8e  mov     [rax+8], r14
0x180084c92  mov     [rdi+140h], rcx
0x180084c99  mov     rcx, [rdi+148h]; this
0x180084ca0  mov     [rdi+148h], rdx
0x180084ca7  test    rcx, rcx
0x180084caa  jz      short loc_180084CB2
0x180084cac  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180084cb1  nop
0x180084cb2  mov     rcx, [rsp+230h+var_1F8]; this
0x180084cb7  test    rcx, rcx
0x180084cba  jz      short loc_180084CC2
0x180084cbc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180084cc1  nop
0x180084cc2  mov     rcx, [rdi+140h]; this
0x180084cc9  test    rcx, rcx
0x180084ccc  jnz     short loc_180084CF3
0x180084cce  mov     rcx, [rbp+138h]; this
0x180084cd5  mov     ebx, 8007000Eh
0x180084cda  mov     r9d, ebx; char *
0x180084cdd  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084ce4  mov     edx, 637h; void *
0x180084ce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084cee  jmp     loc_180084D8E
0x180084cf3  lea     rdx, [rdi+70h]; struct Path *
0x180084cf7  call    ?Initialize@BindingStore@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::BindingStore::Initialize(Csl::Path const &)
0x180084cfc  mov     ebx, eax
0x180084cfe  test    eax, eax
0x180084d00  jns     short loc_180084D0C
0x180084d02  mov     edx, 639h
0x180084d07  jmp     loc_180084C42
0x180084d0c  lea     r9, [rsp+230h+ExistingFileName]
0x180084d11  mov     [rsp+230h+var_1F0], r9
0x180084d16  lea     rcx, [rsp+230h+ExistingFileName]
0x180084d1b  mov     [rsp+230h+var_1E8], rcx
0x180084d20  mov     [rsp+230h+ExistingFileName], r14w
0x180084d26  cmp     dword ptr [rdi+10h], 1
0x180084d2a  jnz     loc_180084DB0
0x180084d30  mov     rax, [rdi+150h]
0x180084d37  mov     rdx, [rax+50h]
0x180084d3b  mov     r8, [rax+58h]
0x180084d3f  sub     r8, rdx
0x180084d42  sar     r8, 1
0x180084d45  lea     rcx, [rsp+230h+var_1F0]
0x180084d4a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180084d4f  test    al, al
0x180084d51  jnz     short loc_180084DA6
0x180084d53  mov     ebx, 8007000Eh
0x180084d58  mov     edx, 648h; void *
0x180084d5d  mov     r9d, ebx; char *
0x180084d60  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084d67  mov     rcx, [rbp+138h]; this
0x180084d6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084d73  lea     rax, [rsp+230h+ExistingFileName]
0x180084d78  mov     rcx, [rsp+230h+var_1F0]; void *
0x180084d7d  cmp     rcx, rax
0x180084d80  jz      short loc_180084D8E
0x180084d82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180084d89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180084d8e  mov     rax, [rsp+230h+SecurityDescriptor]
0x180084d93  test    rax, rax
0x180084d96  jz      loc_1800850A8
0x180084d9c  mov     [rsp+230h+ObjectDescriptor], rax
0x180084da1  jmp     loc_180084BFF
0x180084da6  mov     rcx, [rsp+230h+var_1E8]
0x180084dab  mov     r9, [rsp+230h+var_1F0]
0x180084db0  lea     rsi, [rdi+50h]
0x180084db4  cmp     rcx, r9
0x180084db7  jnz     short loc_180084DD8
0x180084db9  mov     rcx, [rsi]; guestStateFilePath
0x180084dbc  call    cs:__imp_HcsCreateEmptyGuestStateFile
0x180084dc3  nop     dword ptr [rax+rax+00h]
0x180084dc8  mov     ebx, eax
0x180084dca  test    eax, eax
0x180084dcc  jns     short loc_180084E44
0x180084dce  mov     edx, 4ADh
0x180084dd3  jmp     loc_180084E5C
0x180084dd8  mov     r8d, 1; bFailIfExists
0x180084dde  mov     rdx, [rsi]; lpNewFileName
0x180084de1  mov     rcx, r9; lpExistingFileName
0x180084de4  call    cs:__imp_CopyFileW
0x180084deb  nop     dword ptr [rax+rax+00h]
0x180084df0  test    eax, eax
0x180084df2  jnz     short loc_180084E44
0x180084df4  mov     rcx, [rbp+138h]; this
0x180084dfb  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180084e02  mov     edx, 4B2h; void *
0x180084e07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180084e0c  mov     ebx, eax
0x180084e0e  test    eax, eax
0x180084e10  js      short loc_180084E72
0x180084e12  xorps   xmm0, xmm0
0x180084e15  xor     eax, eax
0x180084e17  movups  xmmword ptr [rsp+230h+var_1D0], xmm0
0x180084e1c  movups  [rsp+230h+var_1C0], xmm0
0x180084e21  mov     [rbp+130h+var_1B0], rax
0x180084e25  mov     ecx, [rdi+90h]
0x180084e2b  sub     ecx, 1
0x180084e2e  jz      short loc_180084E96
0x180084e30  cmp     ecx, 1
0x180084e33  jz      short loc_180084E7C
0x180084e35  mov     ebx, 8000FFFFh
0x180084e3a  mov     r9d, ebx
0x180084e3d  mov     edx, 662h
0x180084e42  jmp     short loc_180084EB1
0x180084e44  mov     edx, 1201BFh; struct Path *
0x180084e49  mov     rcx, rsi; this
0x180084e4c  call    ?GrantVmGroupAccess@Csl@@YAJAEBVPath@1@K@Z; Csl::GrantVmGroupAccess(Csl::Path const &,ulong)
0x180084e51  mov     ebx, eax
0x180084e53  test    eax, eax
0x180084e55  jns     short loc_180084E12
0x180084e57  mov     edx, 4B7h; void *
0x180084e5c  mov     r9d, eax; char *
0x180084e5f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180084e66  mov     rcx, [rbp+138h]; this
0x180084e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084e72  mov     edx, 64Dh
0x180084e77  jmp     loc_180084D5D
0x180084e7c  lea     rdx, [rsp+230h+var_1D0]
0x180084e81  mov     rcx, rdi; this
0x180084e84  call    ?MaterializeStorageSpace@ContainerStorage@Details@Core@Manager@Container@@AEAAJAEAV?$optional@VPath@Csl@@@utl@@@Z; Container::Manager::Core::Details::ContainerStorage::MaterializeStorageSpace(utl::optional<Csl::Path> &)
0x180084e89  mov     ebx, eax
0x180084e8b  test    eax, eax
0x180084e8d  jns     short loc_180084EF2
0x180084e8f  mov     edx, 65Bh
0x180084e94  jmp     short loc_180084EAE
0x180084e96  lea     rdx, [rsp+230h+var_1D0]
0x180084e9b  mov     rcx, rdi; this
0x180084e9e  call    ?MaterializeVhd@ContainerStorage@Details@Core@Manager@Container@@AEAAJAEAV?$optional@VPath@Csl@@@utl@@@Z; Container::Manager::Core::Details::ContainerStorage::MaterializeVhd(utl::optional<Csl::Path> &)
0x180084ea3  mov     ebx, eax
0x180084ea5  test    eax, eax
0x180084ea7  jns     short loc_180084EF2
0x180084ea9  mov     edx, 655h; void *
0x180084eae  mov     r9d, eax; char *
0x180084eb1  mov     rcx, [rbp+138h]; this
0x180084eb8  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084ec4  cmp     byte ptr [rbp+130h+var_1B0], r14b
0x180084ec8  jz      loc_180084D73
0x180084ece  mov     rcx, [rsp+230h+var_1D0]; void *
0x180084ed3  lea     rax, [rsp+230h+var_1C0]
0x180084ed8  cmp     rcx, rax
0x180084edb  jz      loc_180084D73
0x180084ee1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180084ee8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180084eed  jmp     loc_180084D73
0x180084ef2  lea     rbx, [rdi+0E8h]
0x180084ef9  mov     rcx, rbx; SRWLock
0x180084efc  call    cs:__imp_AcquireSRWLockExclusive
0x180084f03  nop     dword ptr [rax+rax+00h]
0x180084f08  cmp     dword ptr [rdi+0F0h], 3
0x180084f0f  jz      loc_1800851D3
0x180084f15  mov     [rsp+230h+ObjectDescriptor], r14
0x180084f1a  lea     rcx, [rsp+230h+ObjectDescriptor]; this
0x180084f1f  call    ?Initialize@RegistryTransaction@Csl@@QEAAJXZ; Csl::RegistryTransaction::Initialize(void)
0x180084f24  mov     esi, eax
0x180084f26  test    eax, eax
0x180084f28  jns     short loc_180084F4A
0x180084f2a  mov     rcx, [rbp+138h]; this
0x180084f31  mov     r9d, eax; char *
0x180084f34  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180084f3b  mov     edx, 671h; void *
0x180084f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084f45  jmp     loc_18008502C
0x180084f4a  mov     [rsp+230h+hKey], r14; int
0x180084f4f  lea     r9, [rsp+230h+hKey]
0x180084f54  lea     rdx, [rsp+230h+ObjectDescriptor]
0x180084f59  mov     rcx, rdi
0x180084f5c  call    ?OpenBackingRegistryKeyTransacted@ContainerStorage@Details@Core@Manager@Container@@AEBAJAEBVRegistryTransaction@Csl@@W4RegistryKeyAccess@7@AEAVRegistryKey@7@@Z; Container::Manager::Core::Details::ContainerStorage::OpenBackingRegistryKeyTransacted(Csl::RegistryTransaction const &,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180084f61  mov     esi, eax
0x180084f63  test    eax, eax
0x180084f65  jns     short loc_180084F71
0x180084f67  mov     edx, 678h
0x180084f6c  jmp     loc_180085000
0x180084f71  test    byte ptr [rdi+110h], 1
0x180084f78  jz      short loc_180084FA5
0x180084f7a  cmp     byte ptr [rbp+130h+var_1B0], r14b
0x180084f7e  jnz     short loc_180084F82
0x180084f80  int     2Ch; Windows NT - assertion failure
0x180084f82  lea     r8, [rsp+230h+var_1D0]; struct Path *
0x180084f87  lea     rdx, aEncryptionkeyp; "EncryptionKeyPath"
0x180084f8e  lea     rcx, [rsp+230h+hKey]; this
0x180084f93  call    ?SetPathValue@RegistryKey@Csl@@QEAAJPEBGAEBVPath@2@@Z; Csl::RegistryKey::SetPathValue(ushort const *,Csl::Path const &)
0x180084f98  mov     esi, eax
0x180084f9a  test    eax, eax
0x180084f9c  jns     short loc_180084FA5
0x180084f9e  mov     edx, 67Eh
0x180084fa3  jmp     short loc_180085000
0x180084fa5  lea     rdx, aMaxsizeinbytes; "MaxSizeInBytes"
0x180084fac  lea     rcx, [rsp+230h+hKey]; this
0x180084fb1  call    ?DeleteValue@RegistryKey@Csl@@QEAAJPEBG@Z; Csl::RegistryKey::DeleteValue(ushort const *)
0x180084fb6  mov     esi, eax
0x180084fb8  test    eax, eax
0x180084fba  jns     short loc_180084FC3
0x180084fbc  mov     edx, 684h
0x180084fc1  jmp     short loc_180085000
0x180084fc3  mov     r8d, 2; unsigned int
0x180084fc9  lea     rdx, aState; "State"
0x180084fd0  lea     rcx, [rsp+230h+hKey]; this
0x180084fd5  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180084fda  mov     esi, eax
0x180084fdc  test    eax, eax
0x180084fde  jns     short loc_180084FE7
0x180084fe0  mov     edx, 688h
0x180084fe5  jmp     short loc_180085000
0x180084fe7  lea     rcx, [rsp+230h+ObjectDescriptor]; this
0x180084fec  call    ?Commit@RegistryTransaction@Csl@@QEAAJXZ; Csl::RegistryTransaction::Commit(void)
0x180084ff1  mov     esi, eax
0x180084ff3  test    eax, eax
0x180084ff5  jns     loc_1800850C5
0x180084ffb  mov     edx, 68Bh; void *
0x180085000  mov     r9d, esi; char *
0x180085003  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18008500a  mov     rcx, [rbp+138h]; this
0x180085011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085016  mov     rcx, [rsp+230h+hKey]; hKey
  ... truncated ...
```
