# Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MappedLayer>,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x18009f20c`
- end: `0x18009f70b`
- name: `?DereferenceMappedLayer@ContainerObject@Details@Core@Manager@Container@@AEAAXV?$shared_ptr@UMappedLayer@ContainerObject@Details@Core@Manager@Container@@@utl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `1279`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18009f20c`
- `0x18009fea8`
- `0x1800add38`
- `0x1800b9040`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18003c7d0`
- `0x180042b58`
- `0x1800471dc`
- `0x1800475c4`
- `0x1800785d4`
- `0x180080880`
- `0x180080980`
- `0x18009b018`
- `0x18009f20c`
- `0x1800ac950`
- `0x1800b73f4`
- `0x180101d74`
- `0x180125384`
- `0x180187228`
- `0x180198494`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f378`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f443`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f5de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f378`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f443`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f5de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f2dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f3ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f3cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f409`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f498`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f6b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f2dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f3ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f3cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f409`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f498`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f6b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f44f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f5ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f44f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f5ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(
        __int64 a1,
        _QWORD *a2,
        char *a3)
{
  _QWORD *v4; // rsi
  void *v6; // r14
  const char *v7; // r9
  _QWORD *v8; // rdi
  utl::_RefCountBase *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rsi
  volatile signed __int32 *v13; // r12
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  char v19; // r15
  __int64 v20; // rax
  utl::_RefCountBase *v21; // r14
  void **v22; // rax
  utl::_RefCountBase *v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  utl::_RefCountBase *v28; // rcx
  utl::_RefCountBase *v29; // rcx
  int v30; // [rsp+20h] [rbp-40h]
  int v31; // [rsp+20h] [rbp-40h]
  __int64 v32; // [rsp+28h] [rbp-38h] BYREF
  char v33; // [rsp+30h] [rbp-30h] BYREF
  char v34; // [rsp+38h] [rbp-28h] BYREF
  char v35; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v36[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  void *v38; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v39; // [rsp+A8h] [rbp+48h]
  int v40; // [rsp+B8h] [rbp+58h]

  v39 = a2;
  v4 = a2;
  v6 = (void *)(a1 + 1512);
  utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::find<void>(
    a1 + 1512,
    &v38,
    *a2);
  v8 = v38;
  if ( v38 == v6 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12E7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      v7);
  *v4 = 0;
  v9 = (utl::_RefCountBase *)v4[1];
  v4[1] = 0;
  if ( v9 )
    utl::_RefCountBase::_DecStrong(v9);
  v10 = v8[6];
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 8);
    LODWORD(v38) = 1;
    if ( v11 == 1 )
    {
      v12 = v8[5];
      v13 = (volatile signed __int32 *)v8[6];
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      if ( !*(_BYTE *)(v12 + 496) )
        *(_BYTE *)(v12 + 496) = 1;
      if ( *(_BYTE *)(v12 + 456) )
      {
        v14 = *(_QWORD *)a3;
        if ( *(_QWORD *)a3 )
        {
          *(_DWORD *)(v14 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v14);
          *(_QWORD *)a3 = 0;
        }
        if ( !*(_BYTE *)(v12 + 456) )
          __int2c();
        v15 = Container::Manager::Core::Details::Silo::RemoveSiloSettings(
                (Container::Manager::Core::Details::Silo *)(*(_QWORD *)(a1 + 1264) + 1528LL),
                (const struct Container::Manager::Core::Details::SiloSettings *)(v12 + 320));
        v40 = v15;
        if ( v15 < 0 )
        {
          LOBYTE(v38) = 0;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x130C,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)v15,
            v30);
        }
        else if ( *(_BYTE *)(v12 + 456) )
        {
          if ( *(_BYTE *)(v12 + 448) )
            Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::BindingSettings *)(v12 + 360));
          if ( *(_BYTE *)(v12 + 352) )
            utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(v12 + 328);
          *(_BYTE *)(v12 + 456) = 0;
        }
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
        *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
        if ( a3 == &v33 )
        {
          if ( a1 != -456 )
          {
            *(_DWORD *)(a1 + 464) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 456));
          }
        }
        else
        {
          v16 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3 )
          {
            *(_DWORD *)(v16 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v16);
          }
          *(_QWORD *)a3 = a1 + 456;
        }
      }
      else
      {
        v40 = 0;
      }
      if ( *(_BYTE *)(v12 + 312) )
      {
        Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
          a1,
          a3);
        v17 = *(_QWORD *)a3;
        if ( *(_QWORD *)a3 )
        {
          *(_DWORD *)(v17 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v17);
          *(_QWORD *)a3 = 0;
        }
        if ( !*(_BYTE *)(v12 + 312) )
          __int2c();
        v31 = Container::Manager::Hcs::ComputeSystem::UnmapSharedFolder(*(_QWORD *)(a1 + 1256), v12 + 32, 0);
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
        *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
        if ( a3 == &v34 )
        {
          if ( a1 != -456 )
          {
            *(_DWORD *)(a1 + 464) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 456));
          }
        }
        else
        {
          v18 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3 )
          {
            *(_DWORD *)(v18 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v18);
          }
          *(_QWORD *)a3 = a1 + 456;
        }
        Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)a1);
        if ( v31 < 0 )
        {
          v19 = 0;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x132F,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)v31,
            v31);
          goto LABEL_53;
        }
        if ( *(_BYTE *)(v12 + 312) )
        {
          Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v12 + 32));
          *(_BYTE *)(v12 + 312) = 0;
        }
      }
      v19 = (char)v38;
      if ( (_BYTE)v38 )
      {
        if ( *(_QWORD *)(v12 + 16) )
        {
          v20 = *(_QWORD *)(v12 + 24);
          v36[0] = *(_QWORD *)(v12 + 16);
          v36[1] = v20;
          *(_QWORD *)(v12 + 16) = 0;
          *(_QWORD *)(v12 + 24) = 0;
          Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(a1, v36, a3);
        }
        v12 = v8[5];
        v21 = (utl::_RefCountBase *)v8[6];
        v8[5] = 0;
        v8[6] = 0;
        if ( v13 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
        v22 = (void **)v8[2];
        if ( v22 == &utl::_TreeSentinel )
        {
          v25 = (_QWORD *)(*v8 & 0xFFFFFFFFFFFFFFFEuLL);
          if ( (_QWORD *)v25[2] == v8 && (_QWORD *)*v25 != v8 )
          {
            v26 = (_QWORD *)(*v25 & 0xFFFFFFFFFFFFFFFEuLL);
            if ( (_QWORD *)v26[2] == v25 && (_QWORD *)*v26 != v25 )
            {
              do
              {
                v27 = v26;
                v26 = (_QWORD *)(*v26 & 0xFFFFFFFFFFFFFFFEuLL);
              }
              while ( (_QWORD *)v26[2] == v27 );
            }
          }
        }
        else
        {
          if ( v8 == v22 )
            __int2c();
          while ( v22[1] != &utl::_TreeSentinel )
            v22 = (void **)v22[1];
        }
        utl::_TreeNodeHeader<Csl::Details::AsyncOperationImpl<void> *>::_HeadUnlinkNode(a1 + 1512, v8);
        --*(_QWORD *)(a1 + 1536);
        v28 = (utl::_RefCountBase *)v8[6];
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
        operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
LABEL_55:
        v32 = 0;
        if ( &v32 != (__int64 *)a3 )
        {
          v32 = *(_QWORD *)a3;
          *(_QWORD *)a3 = 0;
        }
        Container::Manager::Core::Details::ContainerObject::MappedLayer::StopOperation(v12, &v32);
        if ( v19 )
        {
          Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v12 + 472));
          v23 = v21;
          v21 = 0;
          if ( v23 )
            utl::_RefCountBase::_DecStrong(v23);
        }
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
        *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
        if ( a3 == &v35 )
        {
          if ( a1 != -456 )
          {
            *(_DWORD *)(a1 + 464) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 456));
          }
        }
        else
        {
          v24 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3 )
          {
            *(_DWORD *)(v24 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v24);
          }
          *(_QWORD *)a3 = a1 + 456;
        }
        if ( v21 )
          utl::_RefCountBase::_DecStrong(v21);
        v4 = v39;
        goto LABEL_80;
      }
LABEL_53:
      v21 = (utl::_RefCountBase *)v13;
      if ( v40 != -2147024846 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_55;
    }
  }
LABEL_80:
  v29 = (utl::_RefCountBase *)v4[1];
  if ( v29 )
    utl::_RefCountBase::_DecStrong(v29);
}

```

## disassembly

```asm
0x18009f20c  mov     [rsp-38h+arg_10], rbx
0x18009f211  mov     [rsp-38h+arg_8], rdx
0x18009f216  push    rbp
0x18009f217  push    rsi
0x18009f218  push    rdi
0x18009f219  push    r12
0x18009f21b  push    r13
0x18009f21d  push    r14
0x18009f21f  push    r15
0x18009f221  mov     rbp, rsp
0x18009f224  sub     rsp, 60h
0x18009f228  mov     rbx, r8
0x18009f22b  mov     rsi, rdx
0x18009f22e  mov     r13, rcx
0x18009f231  lea     r14, [rcx+5E8h]
0x18009f238  mov     r8, [rdx]
0x18009f23b  lea     rdx, [rbp+arg_0]
0x18009f23f  mov     rcx, r14
0x18009f242  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::find<void>(_GUID const &)
0x18009f247  mov     rdi, [rbp+arg_0]
0x18009f24b  cmp     rdi, r14
0x18009f24e  setz    al
0x18009f251  mov     rcx, [rbp+38h]; this
0x18009f255  test    al, al
0x18009f257  jnz     loc_18009F6F9
0x18009f25d  mov     qword ptr [rsi], 0
0x18009f264  mov     rcx, [rsi+8]; this
0x18009f268  mov     qword ptr [rsi+8], 0
0x18009f270  test    rcx, rcx
0x18009f273  jz      short loc_18009F27B
0x18009f275  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f27a  nop
0x18009f27b  mov     rax, [rdi+30h]
0x18009f27f  test    rax, rax
0x18009f282  jz      loc_18009F6D1
0x18009f288  mov     eax, [rax+8]
0x18009f28b  mov     r15d, 1
0x18009f291  mov     dword ptr [rbp+arg_0], r15d
0x18009f295  cmp     eax, r15d
0x18009f298  jnz     loc_18009F6D1
0x18009f29e  mov     rsi, [rdi+28h]
0x18009f2a2  mov     r12, [rdi+30h]
0x18009f2a6  test    r12, r12
0x18009f2a9  jz      short loc_18009F2B1
0x18009f2ab  lock inc dword ptr [r12+8]
0x18009f2b1  cmp     byte ptr [rsi+1F0h], 0
0x18009f2b8  jnz     short loc_18009F2C1
0x18009f2ba  mov     [rsi+1F0h], r15b
0x18009f2c1  cmp     byte ptr [rsi+1C8h], 0
0x18009f2c8  jz      loc_18009F3DB
0x18009f2ce  mov     rcx, [rbx]; SRWLock
0x18009f2d1  test    rcx, rcx
0x18009f2d4  jz      short loc_18009F2F0
0x18009f2d6  mov     dword ptr [rcx+8], 0
0x18009f2dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f2e4  nop     dword ptr [rax+rax+00h]
0x18009f2e9  mov     qword ptr [rbx], 0
0x18009f2f0  mov     rcx, [r13+4F0h]
0x18009f2f7  add     rcx, 5F8h; this
0x18009f2fe  lea     r14, [rsi+140h]
0x18009f305  cmp     byte ptr [r14+88h], 0
0x18009f30d  jnz     short loc_18009F311
0x18009f30f  int     2Ch; Windows NT - assertion failure
0x18009f311  mov     rdx, r14; struct Container::Manager::Core::Details::SiloSettings *
0x18009f314  call    ?RemoveSiloSettings@Silo@Details@Core@Manager@Container@@QEAAJAEBUSiloSettings@2345@@Z; Container::Manager::Core::Details::Silo::RemoveSiloSettings(Container::Manager::Core::Details::SiloSettings const &)
0x18009f319  mov     [rbp+arg_18], eax
0x18009f31c  test    eax, eax
0x18009f31e  js      short loc_18009F352
0x18009f320  cmp     byte ptr [r14+88h], 0
0x18009f328  jz      short loc_18009F36E
0x18009f32a  lea     rcx, [r14+28h]; this
0x18009f32e  cmp     byte ptr [rcx+58h], 0
0x18009f332  jz      short loc_18009F339
0x18009f334  call    ??1BindingSettings@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BindingSettings::~BindingSettings(void)
0x18009f339  lea     rcx, [r14+8]
0x18009f33d  cmp     byte ptr [rcx+18h], 0
0x18009f341  jz      short loc_18009F348
0x18009f343  call    ??1?$vector@UWcifsInstanceSettings@Details@Core@Manager@Container@@V?$allocator@UWcifsInstanceSettings@Details@Core@Manager@Container@@@utl@@@utl@@QEAA@XZ; utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(void)
0x18009f348  mov     byte ptr [r14+88h], 0
0x18009f350  jmp     short loc_18009F36E
0x18009f352  mov     byte ptr [rbp+arg_0], 0
0x18009f356  mov     rcx, [rbp+38h]; this
0x18009f35a  mov     r9d, eax; char *
0x18009f35d  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009f364  mov     edx, 130Ch; void *
0x18009f369  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18009f36e  lea     r14, [r13+1C8h]
0x18009f375  mov     rcx, r14; SRWLock
0x18009f378  call    cs:__imp_AcquireSRWLockExclusive
0x18009f37f  nop     dword ptr [rax+rax+00h]
0x18009f384  call    cs:__imp_GetCurrentThreadId
0x18009f38b  nop     dword ptr [rax+rax+00h]
0x18009f390  mov     [r14+8], eax
0x18009f394  lea     rax, [rbp+var_30]
0x18009f398  cmp     rbx, rax
0x18009f39b  jz      short loc_18009F3BD
0x18009f39d  mov     rcx, [rbx]; SRWLock
0x18009f3a0  test    rcx, rcx
0x18009f3a3  jz      short loc_18009F3B8
0x18009f3a5  mov     dword ptr [rcx+8], 0
0x18009f3ac  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f3b3  nop     dword ptr [rax+rax+00h]
0x18009f3b8  mov     [rbx], r14
0x18009f3bb  jmp     short loc_18009F3E2
0x18009f3bd  test    r14, r14
0x18009f3c0  jz      short loc_18009F3E2
0x18009f3c2  mov     dword ptr [r14+8], 0
0x18009f3ca  mov     rcx, r14; SRWLock
0x18009f3cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f3d4  nop     dword ptr [rax+rax+00h]
0x18009f3d9  jmp     short loc_18009F3E2
0x18009f3db  mov     [rbp+arg_18], 0
0x18009f3e2  cmp     byte ptr [rsi+138h], 0
0x18009f3e9  jz      loc_18009F4D0
0x18009f3ef  mov     rdx, rbx
0x18009f3f2  mov     rcx, r13
0x18009f3f5  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009f3fa  mov     rcx, [rbx]; SRWLock
0x18009f3fd  xor     r15d, r15d
0x18009f400  test    rcx, rcx
0x18009f403  jz      short loc_18009F418
0x18009f405  mov     [rcx+8], r15d
0x18009f409  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f410  nop     dword ptr [rax+rax+00h]
0x18009f415  mov     [rbx], r15
0x18009f418  cmp     [rsi+138h], r15b
0x18009f41f  jnz     short loc_18009F423
0x18009f421  int     2Ch; Windows NT - assertion failure
0x18009f423  xor     r8d, r8d
0x18009f426  lea     rdx, [rsi+20h]
0x18009f42a  mov     rcx, [r13+4E8h]
0x18009f431  call    ?UnmapSharedFolder@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVMappedFolderConfiguration@234@W4UnmapSharedFolderFlags@234@@Z; Container::Manager::Hcs::ComputeSystem::UnmapSharedFolder(Container::Manager::Hcs::MappedFolderConfiguration const &,Container::Manager::Hcs::UnmapSharedFolderFlags)
0x18009f436  mov     dword ptr [rbp+var_40], eax
0x18009f439  lea     r15, [r13+1C8h]
0x18009f440  mov     rcx, r15; SRWLock
0x18009f443  call    cs:__imp_AcquireSRWLockExclusive
0x18009f44a  nop     dword ptr [rax+rax+00h]
0x18009f44f  call    cs:__imp_GetCurrentThreadId
0x18009f456  nop     dword ptr [rax+rax+00h]
0x18009f45b  mov     [r15+8], eax
0x18009f45f  lea     rax, [rbp+var_28]
0x18009f463  cmp     rbx, rax
0x18009f466  jz      short loc_18009F488
0x18009f468  mov     rcx, [rbx]; SRWLock
0x18009f46b  test    rcx, rcx
0x18009f46e  jz      short loc_18009F483
0x18009f470  mov     dword ptr [rcx+8], 0
0x18009f477  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f47e  nop     dword ptr [rax+rax+00h]
0x18009f483  mov     [rbx], r15
0x18009f486  jmp     short loc_18009F4A4
0x18009f488  test    r15, r15
0x18009f48b  jz      short loc_18009F4A4
0x18009f48d  mov     dword ptr [r15+8], 0
0x18009f495  mov     rcx, r15; SRWLock
0x18009f498  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f49f  nop     dword ptr [rax+rax+00h]
0x18009f4a4  mov     rcx, r13; this
0x18009f4a7  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x18009f4ac  mov     eax, dword ptr [rbp+var_40]
0x18009f4af  test    eax, eax
0x18009f4b1  js      loc_18009F55B
0x18009f4b7  cmp     byte ptr [rsi+138h], 0
0x18009f4be  jz      short loc_18009F4D0
0x18009f4c0  lea     rcx, [rsi+20h]; this
0x18009f4c4  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x18009f4c9  mov     byte ptr [rsi+138h], 0
0x18009f4d0  mov     r15d, dword ptr [rbp+arg_0]
0x18009f4d4  test    r15b, r15b
0x18009f4d7  jz      loc_18009F576
0x18009f4dd  mov     rcx, [rsi+10h]
0x18009f4e1  test    rcx, rcx
0x18009f4e4  jz      short loc_18009F511
0x18009f4e6  mov     rax, [rsi+18h]
0x18009f4ea  mov     [rbp+var_18], rcx
0x18009f4ee  mov     [rbp+var_10], rax
0x18009f4f2  mov     qword ptr [rsi+10h], 0
0x18009f4fa  mov     qword ptr [rsi+18h], 0
0x18009f502  mov     r8, rbx
0x18009f505  lea     rdx, [rbp+var_18]
0x18009f509  mov     rcx, r13
0x18009f50c  call    ?DereferenceMappedLayer@ContainerObject@Details@Core@Manager@Container@@AEAAXV?$shared_ptr@UMappedLayer@ContainerObject@Details@Core@Manager@Container@@@utl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MappedLayer>,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009f511  mov     rsi, [rdi+28h]
0x18009f515  mov     r14, [rdi+30h]
0x18009f519  mov     qword ptr [rdi+28h], 0
0x18009f521  mov     qword ptr [rdi+30h], 0
0x18009f529  test    r12, r12
0x18009f52c  jz      short loc_18009F537
0x18009f52e  mov     rcx, r12; this
0x18009f531  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f536  nop
0x18009f537  mov     rax, [rdi+10h]
0x18009f53b  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18009f542  cmp     rax, rcx
0x18009f545  jz      loc_18009F635
0x18009f54b  cmp     rdi, rax
0x18009f54e  jnz     loc_18009F62D
0x18009f554  int     2Ch; Windows NT - assertion failure
0x18009f556  jmp     loc_18009F62D
0x18009f55b  xor     r15b, r15b
0x18009f55e  mov     rcx, [rbp+38h]; this
0x18009f562  mov     r9d, eax; char *
0x18009f565  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009f56c  mov     edx, 132Fh; void *
0x18009f571  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18009f576  mov     r14, r12
0x18009f579  cmp     [rbp+arg_18], 80070032h
0x18009f580  jz      short loc_18009F587
0x18009f582  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f587  mov     [rbp+var_38], 0
0x18009f58f  lea     rax, [rbp+var_38]
0x18009f593  cmp     rax, rbx
0x18009f596  jz      short loc_18009F5A6
0x18009f598  mov     rax, [rbx]
0x18009f59b  mov     [rbp+var_38], rax
0x18009f59f  mov     qword ptr [rbx], 0
0x18009f5a6  lea     rdx, [rbp+var_38]
0x18009f5aa  mov     rcx, rsi
0x18009f5ad  call    ?StopOperation@MappedLayer@ContainerObject@Details@Core@Manager@Container@@QEAAXV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::MappedLayer::StopOperation(Csl::SrwLock::ReleaseOnScopeExit<0>)
0x18009f5b2  test    r15b, r15b
0x18009f5b5  jz      short loc_18009F5D4
0x18009f5b7  lea     rcx, [rsi+1D8h]; this
0x18009f5be  call    ?WaitForRundownProtectionRelease@RundownReference@Csl@@QEAAXXZ; Csl::RundownReference::WaitForRundownProtectionRelease(void)
0x18009f5c3  mov     rcx, r14; this
0x18009f5c6  xor     r14d, r14d
0x18009f5c9  test    rcx, rcx
0x18009f5cc  jz      short loc_18009F5D4
0x18009f5ce  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f5d3  nop
0x18009f5d4  lea     rdi, [r13+1C8h]
0x18009f5db  mov     rcx, rdi; SRWLock
0x18009f5de  call    cs:__imp_AcquireSRWLockExclusive
0x18009f5e5  nop     dword ptr [rax+rax+00h]
0x18009f5ea  call    cs:__imp_GetCurrentThreadId
0x18009f5f1  nop     dword ptr [rax+rax+00h]
0x18009f5f6  mov     [rdi+8], eax
0x18009f5f9  lea     rax, [rbp+var_20]
0x18009f5fd  cmp     rbx, rax
0x18009f600  jz      loc_18009F6A3
0x18009f606  mov     rcx, [rbx]; SRWLock
0x18009f609  test    rcx, rcx
0x18009f60c  jz      short loc_18009F621
0x18009f60e  mov     dword ptr [rcx+8], 0
0x18009f615  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f61c  nop     dword ptr [rax+rax+00h]
0x18009f621  mov     [rbx], rdi
0x18009f624  jmp     loc_18009F6BF
0x18009f629  mov     rax, [rax+8]
0x18009f62d  cmp     [rax+8], rcx
0x18009f631  jnz     short loc_18009F629
0x18009f633  jmp     short loc_18009F669
0x18009f635  mov     rax, [rdi]
0x18009f638  and     rax, 0FFFFFFFFFFFFFFFEh
0x18009f63c  cmp     [rax+10h], rdi
0x18009f640  jnz     short loc_18009F669
0x18009f642  mov     rcx, [rax]
0x18009f645  cmp     rcx, rdi
0x18009f648  jz      short loc_18009F669
0x18009f64a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18009f64e  cmp     [rcx+10h], rax
0x18009f652  jnz     short loc_18009F669
0x18009f654  cmp     [rcx], rax
0x18009f657  jz      short loc_18009F669
0x18009f659  mov     rax, rcx
0x18009f65c  mov     rcx, [rcx]
0x18009f65f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18009f663  cmp     [rcx+10h], rax
0x18009f667  jz      short loc_18009F659
0x18009f669  mov     rdx, rdi
0x18009f66c  lea     r12, [r13+5E8h]
0x18009f673  mov     rcx, r12
0x18009f676  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@PEAV?$AsyncOperationImpl@X@Details@Csl@@@utl@@QEAAXPEAU?$_TreeNode@PEAV?$AsyncOperationImpl@X@Details@Csl@@@2@@Z; utl::_TreeNodeHeader<Csl::Details::AsyncOperationImpl<void> *>::_HeadUnlinkNode(utl::_TreeNode<Csl::Details::AsyncOperationImpl<void> *> *)
0x18009f67b  dec     qword ptr [r12+18h]
0x18009f680  mov     rcx, [rdi+30h]; this
0x18009f684  test    rcx, rcx
0x18009f687  jz      short loc_18009F68F
0x18009f689  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f68e  nop
0x18009f68f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009f696  mov     rcx, rdi; void *
0x18009f699  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009f69e  jmp     loc_18009F587
0x18009f6a3  test    rdi, rdi
0x18009f6a6  jz      short loc_18009F6BF
0x18009f6a8  mov     dword ptr [rdi+8], 0
0x18009f6af  mov     rcx, rdi; SRWLock
0x18009f6b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f6b9  nop     dword ptr [rax+rax+00h]
0x18009f6be  nop
0x18009f6bf  test    r14, r14
0x18009f6c2  jz      short loc_18009F6CD
0x18009f6c4  mov     rcx, r14; this
0x18009f6c7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f6cc  nop
0x18009f6cd  mov     rsi, [rbp+arg_8]
0x18009f6d1  mov     rcx, [rsi+8]; this
0x18009f6d5  test    rcx, rcx
0x18009f6d8  jz      short loc_18009F6E0
0x18009f6da  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009f6df  nop
  ... truncated ...
```
