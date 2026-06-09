# Container::Manager::Core::Details::Layer::SetDebugging(utl::optional<Container::Manager::Core::Details::DebugConfiguration>,bool)

- ea: `0x1800cba10`
- end: `0x1800cc219`
- name: `?SetDebugging@Layer@Details@Core@Manager@Container@@QEAAJV?$optional@UDebugConfiguration@Details@Core@Manager@Container@@@utl@@_N@Z`
- size: `2057`
- prototype: `__int64 __fastcall(struct Container::Manager::Core::Details::Layer *, Container::Manager::Core::Details::DebugConfiguration *this)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045784`
- `0x1800c467c`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x180032a48`
- `0x180032c70`
- `0x1800342b4`
- `0x18003d400`
- `0x18003e190`
- `0x1800471dc`
- `0x18007f8a4`
- `0x18008039c`
- `0x1800bf0e0`
- `0x1800bf158`
- `0x1800bfc60`
- `0x1800c6c38`
- `0x1800cb858`
- `0x1800cba10`
- `0x1800cc330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cba45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbad4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbd7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cc040`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cba45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbad4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbd7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cc040`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cba8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbb32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbe5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbf24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbf87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbfe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc0dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc1e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cba8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbb32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbe5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbf24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbf87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cbfe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc0dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cc1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cba51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cbae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cbd88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc04c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cba51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cbae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cbd88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc04c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::Layer::SetDebugging(
        struct Container::Manager::Core::Details::Layer *a1,
        Container::Manager::Core::Details::DebugConfiguration *this,
        char a3)
{
  char *v5; // rdi
  unsigned int v6; // esi
  __int64 v8; // r9
  __int64 v9; // rdx
  int ResourcePath; // eax
  unsigned int v11; // edi
  int v12; // eax
  Container::Manager::Core::Details::DebugConfigurationState *v13; // r15
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // r14d
  unsigned int v20; // r12d
  int v21; // eax
  int v22; // eax
  utl::_RefCountBase *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // r15d
  int v27; // eax
  utl::_RefCountBase *v28; // rcx
  __int128 v29; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v30; // [rsp+30h] [rbp-D0h] BYREF
  void *v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v32[8]; // [rsp+50h] [rbp-B0h] BYREF
  Container::Manager::Core::Details::DebugConfigurationState *v33; // [rsp+60h] [rbp-A0h] BYREF
  utl::_RefCountBase *v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[280]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]
  __int64 v40; // [rsp+1D8h] [rbp+D8h] BYREF

  v5 = (char *)a1 + 272;
  if ( a3 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 34);
    *((_DWORD *)v5 + 2) = GetCurrentThreadId();
    if ( *((_DWORD *)a1 + 28) != 3 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xB3B,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
             (const char *)0x139F,
             v29);
LABEL_4:
      *((_DWORD *)v5 + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v5);
LABEL_5:
      if ( *((_BYTE *)this + 216) )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(this);
      return v6;
    }
    *((_DWORD *)v5 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v5);
  }
  if ( !*((_BYTE *)this + 216) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v5);
    *((_DWORD *)v5 + 2) = GetCurrentThreadId();
    if ( *((_QWORD *)a1 + 46) )
    {
      v24 = *((_QWORD *)a1 + 47);
      if ( v24 && *(int *)(v24 + 8) >= 2 )
      {
        v8 = 32;
        v9 = 2959;
LABEL_12:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
               (const char *)v8,
               v29);
        if ( !v5 )
          goto LABEL_5;
        goto LABEL_4;
      }
      v40 = 0;
      v19 = Csl::RegistryTransaction::Initialize((Csl::RegistryTransaction *)&v40);
      if ( v19 < 0 )
      {
        v25 = 2963;
        goto LABEL_80;
      }
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v19 = Container::Manager::Core::Details::LayerStore::SetDebugConfiguration(*((_QWORD *)a1 + 32), a1, &v35, v40);
      if ( v19 < 0 )
      {
        v25 = 2967;
        goto LABEL_80;
      }
      v26 = *((_DWORD *)a1 + 72) & 0xFFFFFFFE;
      v19 = Container::Manager::Core::Details::LayerStore::SetFlags(*((_QWORD *)a1 + 32), a1, v26, v40);
      if ( v19 < 0 )
      {
        v25 = 2973;
        goto LABEL_80;
      }
      v19 = Csl::RegistryTransaction::Commit((Csl::RegistryTransaction *)&v40);
      if ( v19 < 0 )
      {
        v25 = 2976;
LABEL_80:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v19,
          v29);
        Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
        if ( v5 )
        {
          *((_DWORD *)v5 + 2) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v5);
        }
        goto LABEL_57;
      }
      v27 = Container::Manager::Core::Details::DebugConfigurationState::DisableDebugging(*((Container::Manager::Core::Details::DebugConfigurationState **)a1
                                                                                         + 46));
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBA4,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v27,
          v29);
      *((_DWORD *)a1 + 72) = v26;
      *((_QWORD *)a1 + 46) = 0;
      v28 = (utl::_RefCountBase *)*((_QWORD *)a1 + 47);
      *((_QWORD *)a1 + 47) = 0;
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
    }
    if ( v5 )
    {
      *((_DWORD *)v5 + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v5);
    }
    goto LABEL_95;
  }
  AcquireSRWLockExclusive((PSRWLOCK)v5);
  *((_DWORD *)v5 + 2) = GetCurrentThreadId();
  if ( *((_QWORD *)a1 + 46) )
  {
    v8 = 5023;
    v9 = 2889;
    goto LABEL_12;
  }
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v5);
  }
  v31[0] = v32;
  v31[1] = v32;
  v32[0] = 0;
  ResourcePath = Container::Manager::Core::Details::Layer::GetResourcePath(a1, 1, v31);
  v11 = ResourcePath;
  if ( ResourcePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)ResourcePath,
      v29);
LABEL_18:
    if ( v31[0] != v32 )
      operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( *((_BYTE *)this + 216) )
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(this);
    return v11;
  }
  *(_QWORD *)&v29 = &v30;
  *((_QWORD *)&v29 + 1) = &v30;
  LOWORD(v30) = 0;
  if ( !*((_BYTE *)this + 216) )
    __int2c();
  v12 = Csl::MarshalToJson<Container::Manager::Core::Details::DebugConfiguration>(this, &v29);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB54,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v12,
      v29);
LABEL_27:
    if ( (__int128 *)v29 != &v30 )
      operator delete((void *)v29, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_18;
  }
  utl::make_shared<Container::Manager::Core::Details::DebugConfigurationState,>(&v33);
  v13 = v33;
  if ( !v33 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB58,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)0x8007000ELL,
      v29);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_27;
  }
  if ( !*((_BYTE *)this + 216) )
    __int2c();
  v14 = Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(v38, this);
  v15 = Container::Manager::Core::Details::DebugConfigurationState::Initialize(v13, v14, v31);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v15,
      v29);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_27;
  }
  v16 = Container::Manager::Core::Details::DebugConfigurationState::EnableDebugging(v13, a1);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v16,
      v29);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_27;
  }
  v40 = 0;
  v17 = Csl::RegistryTransaction::Initialize((Csl::RegistryTransaction *)&v40);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB62,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v17,
      v29);
    Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_27;
  }
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 34);
  *((_DWORD *)a1 + 70) = GetCurrentThreadId();
  if ( (__int128 *)v29 == &v30 )
  {
    *(_QWORD *)&v35 = &v36;
    *((_QWORD *)&v35 + 1) = (char *)&v36 + 2 * ((*((_QWORD *)&v29 + 1) - (_QWORD)&v29 - 16LL) >> 1);
    v36 = v30;
  }
  else
  {
    v35 = v29;
    *(_QWORD *)&v36 = v30;
  }
  *(_QWORD *)&v29 = &v30;
  *((_QWORD *)&v29 + 1) = &v30;
  LOWORD(v30) = 0;
  LOBYTE(v37) = 1;
  v18 = Container::Manager::Core::Details::LayerStore::SetDebugConfiguration(*((_QWORD *)a1 + 32), a1, &v35, v40);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v18,
      v29);
    *((_DWORD *)a1 + 70) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 34);
    Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
LABEL_53:
    if ( (__int128 *)v29 != &v30 )
      operator delete((void *)v29, (const struct std::nothrow_t *)&std::nothrow);
    if ( v31[0] != v32 )
      operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_57:
    if ( *((_BYTE *)this + 216) )
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(this);
    return (unsigned int)v19;
  }
  v20 = *((_DWORD *)a1 + 72) | 1;
  v21 = Container::Manager::Core::Details::LayerStore::SetFlags(*((_QWORD *)a1 + 32), a1, v20, v40);
  v19 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB75,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v21,
      v29);
    *((_DWORD *)a1 + 70) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 34);
    Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_53;
  }
  v22 = Csl::RegistryTransaction::Commit((Csl::RegistryTransaction *)&v40);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB78,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v22,
      v29);
    *((_DWORD *)a1 + 70) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 34);
    Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
    if ( v34 )
      utl::_RefCountBase::_DecStrong(v34);
    goto LABEL_53;
  }
  *((_DWORD *)a1 + 72) = v20;
  *((_QWORD *)a1 + 46) = v13;
  v23 = (utl::_RefCountBase *)*((_QWORD *)a1 + 47);
  *((_QWORD *)a1 + 47) = v34;
  if ( v23 )
    utl::_RefCountBase::_DecStrong(v23);
  *((_DWORD *)a1 + 70) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)a1 + 34);
  Csl::RegistryTransaction::~RegistryTransaction((Csl::RegistryTransaction *)&v40);
  if ( (__int128 *)v29 != &v30 )
    operator delete((void *)v29, (const struct std::nothrow_t *)&std::nothrow);
  if ( v31[0] != v32 )
    operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_95:
  if ( *((_BYTE *)this + 216) )
    Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(this);
  return 0;
}

```

## disassembly

```asm
0x1800cba10  push    rbp
0x1800cba12  push    rbx
0x1800cba13  push    rsi
0x1800cba14  push    rdi
0x1800cba15  push    r12
0x1800cba17  push    r13
0x1800cba19  push    r14
0x1800cba1b  push    r15
0x1800cba1d  lea     rbp, [rsp-78h]
0x1800cba22  sub     rsp, 178h
0x1800cba29  mov     rbx, rdx
0x1800cba2c  mov     rsi, rcx
0x1800cba2f  lea     rdi, [rcx+110h]
0x1800cba36  xor     r13d, r13d
0x1800cba39  test    r8b, r8b
0x1800cba3c  jz      loc_1800CBAC4
0x1800cba42  mov     rcx, rdi; SRWLock
0x1800cba45  call    cs:__imp_AcquireSRWLockExclusive
0x1800cba4c  nop     dword ptr [rax+rax+00h]
0x1800cba51  call    cs:__imp_GetCurrentThreadId
0x1800cba58  nop     dword ptr [rax+rax+00h]
0x1800cba5d  mov     [rdi+8], eax
0x1800cba60  cmp     dword ptr [rsi+70h], 3
0x1800cba64  jz      short loc_1800CBAB1
0x1800cba66  mov     rcx, [rbp+0B8h]; this
0x1800cba6d  mov     r9d, 139Fh; char *
0x1800cba73  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cba7a  mov     edx, 0B3Bh; void *
0x1800cba7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cba84  mov     esi, eax
0x1800cba86  mov     [rdi+8], r13d
0x1800cba8a  mov     rcx, rdi; SRWLock
0x1800cba8d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cba94  nop     dword ptr [rax+rax+00h]
0x1800cba99  cmp     [rbx+0D8h], r13b
0x1800cbaa0  jz      short loc_1800CBAAA
0x1800cbaa2  mov     rcx, rbx; this
0x1800cbaa5  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x1800cbaaa  mov     eax, esi
0x1800cbaac  jmp     loc_1800CC204
0x1800cbab1  mov     [rdi+8], r13d
0x1800cbab5  mov     rcx, rdi; SRWLock
0x1800cbab8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cbabf  nop     dword ptr [rax+rax+00h]
0x1800cbac4  mov     rcx, rdi; SRWLock
0x1800cbac7  cmp     [rbx+0D8h], r13b
0x1800cbace  jz      loc_1800CC040
0x1800cbad4  call    cs:__imp_AcquireSRWLockExclusive
0x1800cbadb  nop     dword ptr [rax+rax+00h]
0x1800cbae0  call    cs:__imp_GetCurrentThreadId
0x1800cbae7  nop     dword ptr [rax+rax+00h]
0x1800cbaec  mov     [rdi+8], eax
0x1800cbaef  cmp     [rsi+170h], r13
0x1800cbaf6  jz      short loc_1800CBB26
0x1800cbaf8  mov     r9d, 139Fh; char *
0x1800cbafe  mov     edx, 0B49h; void *
0x1800cbb03  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbb0a  mov     rcx, [rbp+0B8h]; this
0x1800cbb11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cbb16  mov     esi, eax
0x1800cbb18  test    rdi, rdi
0x1800cbb1b  jz      loc_1800CBA99
0x1800cbb21  jmp     loc_1800CBA86
0x1800cbb26  test    rdi, rdi
0x1800cbb29  jz      short loc_1800CBB3E
0x1800cbb2b  mov     [rdi+8], r13d
0x1800cbb2f  mov     rcx, rdi; SRWLock
0x1800cbb32  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cbb39  nop     dword ptr [rax+rax+00h]
0x1800cbb3e  lea     rax, [rsp+1B0h+var_160]
0x1800cbb43  mov     [rsp+1B0h+var_170], rax
0x1800cbb48  lea     rax, [rsp+1B0h+var_160]
0x1800cbb4d  mov     [rsp+1B0h+var_168], rax
0x1800cbb52  mov     [rsp+1B0h+var_160], r13w
0x1800cbb58  lea     r8, [rsp+1B0h+var_170]
0x1800cbb5d  mov     edx, 1
0x1800cbb62  mov     rcx, rsi
0x1800cbb65  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800cbb6a  mov     edi, eax
0x1800cbb6c  test    eax, eax
0x1800cbb6e  jns     short loc_1800CBBBE
0x1800cbb70  mov     rcx, [rbp+0B8h]; this
0x1800cbb77  mov     r9d, eax; char *
0x1800cbb7a  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbb81  mov     edx, 0B4Fh; void *
0x1800cbb86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbb8b  lea     rax, [rsp+1B0h+var_160]
0x1800cbb90  mov     rcx, [rsp+1B0h+var_170]; void *
0x1800cbb95  cmp     rcx, rax
0x1800cbb98  jz      short loc_1800CBBA6
0x1800cbb9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbba1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cbba6  cmp     [rbx+0D8h], r13b
0x1800cbbad  jz      short loc_1800CBBB7
0x1800cbbaf  mov     rcx, rbx; this
0x1800cbbb2  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x1800cbbb7  mov     eax, edi
0x1800cbbb9  jmp     loc_1800CC204
0x1800cbbbe  lea     rax, [rsp+1B0h+var_180]
0x1800cbbc3  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x1800cbbc8  lea     rax, [rsp+1B0h+var_180]
0x1800cbbcd  mov     qword ptr [rsp+1B0h+var_190+8], rax
0x1800cbbd2  mov     word ptr [rsp+1B0h+var_180], r13w
0x1800cbbd8  cmp     [rbx+0D8h], r13b
0x1800cbbdf  jnz     short loc_1800CBBE3
0x1800cbbe1  int     2Ch; Windows NT - assertion failure
0x1800cbbe3  lea     rdx, [rsp+1B0h+var_190]
0x1800cbbe8  mov     rcx, rbx
0x1800cbbeb  call    ??$MarshalToJson@UDebugConfiguration@Details@Core@Manager@Container@@@Csl@@YAJAEBUDebugConfiguration@Details@Core@Manager@Container@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::MarshalToJson<Container::Manager::Core::Details::DebugConfiguration>(Container::Manager::Core::Details::DebugConfiguration const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800cbbf0  mov     edi, eax
0x1800cbbf2  test    eax, eax
0x1800cbbf4  jns     short loc_1800CBC35
0x1800cbbf6  mov     rcx, [rbp+0B8h]; this
0x1800cbbfd  mov     r9d, eax; char *
0x1800cbc00  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbc07  mov     edx, 0B54h; void *
0x1800cbc0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbc11  lea     rax, [rsp+1B0h+var_180]
0x1800cbc16  mov     rcx, qword ptr [rsp+1B0h+var_190]; void *
0x1800cbc1b  cmp     rcx, rax
0x1800cbc1e  jz      loc_1800CBB8B
0x1800cbc24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbc2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cbc30  jmp     loc_1800CBB8B
0x1800cbc35  lea     rcx, [rsp+1B0h+var_150]
0x1800cbc3a  call    ??$make_shared@VDebugConfigurationState@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@VDebugConfigurationState@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::DebugConfigurationState,>(void)
0x1800cbc3f  mov     r15, [rsp+1B0h+var_150]
0x1800cbc44  test    r15, r15
0x1800cbc47  jnz     short loc_1800CBC7C
0x1800cbc49  mov     rcx, [rbp+0B8h]; this
0x1800cbc50  mov     edi, 8007000Eh
0x1800cbc55  mov     r9d, edi; char *
0x1800cbc58  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbc5f  mov     edx, 0B58h; void *
0x1800cbc64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbc69  nop
0x1800cbc6a  mov     rcx, [rsp+1B0h+var_148]; this
0x1800cbc6f  test    rcx, rcx
0x1800cbc72  jz      short loc_1800CBC7A
0x1800cbc74  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800cbc79  nop
0x1800cbc7a  jmp     short loc_1800CBC11
0x1800cbc7c  cmp     [rbx+0D8h], r13b
0x1800cbc83  jnz     short loc_1800CBC87
0x1800cbc85  int     2Ch; Windows NT - assertion failure
0x1800cbc87  mov     rdx, rbx
0x1800cbc8a  lea     rcx, [rbp+0B0h+var_118]
0x1800cbc8e  call    ??0DebugConfiguration@Details@Core@Manager@Container@@QEAA@$$QEAU01234@@Z; Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(Container::Manager::Core::Details::DebugConfiguration &&)
0x1800cbc93  lea     r8, [rsp+1B0h+var_170]
0x1800cbc98  mov     rdx, rax
0x1800cbc9b  mov     rcx, r15
0x1800cbc9e  call    ?Initialize@DebugConfigurationState@Details@Core@Manager@Container@@QEAAJUDebugConfiguration@2345@AEBVPath@Csl@@@Z; Container::Manager::Core::Details::DebugConfigurationState::Initialize(Container::Manager::Core::Details::DebugConfiguration,Csl::Path const &)
0x1800cbca3  mov     edi, eax
0x1800cbca5  test    eax, eax
0x1800cbca7  jns     short loc_1800CBCDA
0x1800cbca9  mov     rcx, [rbp+0B8h]; this
0x1800cbcb0  mov     r9d, eax; char *
0x1800cbcb3  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbcba  mov     edx, 0B5Ch; void *
0x1800cbcbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbcc4  nop
0x1800cbcc5  mov     rcx, [rsp+1B0h+var_148]; this
0x1800cbcca  test    rcx, rcx
0x1800cbccd  jz      short loc_1800CBCD5
0x1800cbccf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800cbcd4  nop
0x1800cbcd5  jmp     loc_1800CBC11
0x1800cbcda  mov     rdx, rsi; struct Container::Manager::Core::Details::Layer *
0x1800cbcdd  mov     rcx, r15; this
0x1800cbce0  call    ?EnableDebugging@DebugConfigurationState@Details@Core@Manager@Container@@QEAAJAEAVLayer@2345@@Z; Container::Manager::Core::Details::DebugConfigurationState::EnableDebugging(Container::Manager::Core::Details::Layer &)
0x1800cbce5  mov     edi, eax
0x1800cbce7  test    eax, eax
0x1800cbce9  jns     short loc_1800CBD1C
0x1800cbceb  mov     rcx, [rbp+0B8h]; this
0x1800cbcf2  mov     r9d, eax; char *
0x1800cbcf5  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbcfc  mov     edx, 0B5Fh; void *
0x1800cbd01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbd06  nop
0x1800cbd07  mov     rcx, [rsp+1B0h+var_148]; this
0x1800cbd0c  test    rcx, rcx
0x1800cbd0f  jz      short loc_1800CBD17
0x1800cbd11  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800cbd16  nop
0x1800cbd17  jmp     loc_1800CBC11
0x1800cbd1c  mov     [rbp+0B0h+arg_18], r13
0x1800cbd23  lea     rcx, [rbp+0B0h+arg_18]; this
0x1800cbd2a  call    ?Initialize@RegistryTransaction@Csl@@QEAAJXZ; Csl::RegistryTransaction::Initialize(void)
0x1800cbd2f  mov     edi, eax
0x1800cbd31  test    eax, eax
0x1800cbd33  jns     short loc_1800CBD72
0x1800cbd35  mov     rcx, [rbp+0B8h]; this
0x1800cbd3c  mov     r9d, eax; char *
0x1800cbd3f  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbd46  mov     edx, 0B62h; void *
0x1800cbd4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbd50  lea     rcx, [rbp+0B0h+arg_18]; this
0x1800cbd57  call    ??1RegistryTransaction@Csl@@QEAA@XZ; Csl::RegistryTransaction::~RegistryTransaction(void)
0x1800cbd5c  nop
0x1800cbd5d  mov     rcx, [rsp+1B0h+var_148]; this
0x1800cbd62  test    rcx, rcx
0x1800cbd65  jz      short loc_1800CBD6D
0x1800cbd67  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800cbd6c  nop
0x1800cbd6d  jmp     loc_1800CBC11
0x1800cbd72  lea     rdi, [rsi+110h]
0x1800cbd79  mov     rcx, rdi; SRWLock
0x1800cbd7c  call    cs:__imp_AcquireSRWLockExclusive
0x1800cbd83  nop     dword ptr [rax+rax+00h]
0x1800cbd88  call    cs:__imp_GetCurrentThreadId
0x1800cbd8f  nop     dword ptr [rax+rax+00h]
0x1800cbd94  mov     [rdi+8], eax
0x1800cbd97  lea     rcx, [rsp+1B0h+var_180]
0x1800cbd9c  mov     rax, qword ptr [rsp+1B0h+var_190]
0x1800cbda1  cmp     rax, rcx
0x1800cbda4  jnz     short loc_1800CBDE1
0x1800cbda6  lea     rax, [rbp+0B0h+var_130]
0x1800cbdaa  mov     qword ptr [rsp+1B0h+var_140], rax
0x1800cbdaf  lea     rcx, [rsp+1B0h+var_190]
0x1800cbdb4  mov     rax, qword ptr [rsp+1B0h+var_190+8]
0x1800cbdb9  sub     rax, rcx
0x1800cbdbc  sub     rax, 10h
0x1800cbdc0  sar     rax, 1
0x1800cbdc3  lea     rax, [rbp+rax*2+0B0h+var_130]
0x1800cbdc8  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x1800cbdcd  mov     rax, qword ptr [rsp+1B0h+var_180]
0x1800cbdd2  mov     qword ptr [rbp+0B0h+var_130], rax
0x1800cbdd6  mov     rax, qword ptr [rsp+1B0h+var_180+8]
0x1800cbddb  mov     qword ptr [rbp+0B0h+var_130+8], rax
0x1800cbddf  jmp     short loc_1800CBDF9
0x1800cbde1  mov     qword ptr [rsp+1B0h+var_140], rax
0x1800cbde6  mov     rax, qword ptr [rsp+1B0h+var_190+8]
0x1800cbdeb  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x1800cbdf0  mov     rax, qword ptr [rsp+1B0h+var_180]
0x1800cbdf5  mov     qword ptr [rbp+0B0h+var_130], rax
0x1800cbdf9  lea     rax, [rsp+1B0h+var_180]
0x1800cbdfe  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x1800cbe03  lea     rax, [rsp+1B0h+var_180]
0x1800cbe08  mov     qword ptr [rsp+1B0h+var_190+8], rax
0x1800cbe0d  mov     word ptr [rsp+1B0h+var_180], r13w
0x1800cbe13  mov     byte ptr [rbp+0B0h+var_120], 1
0x1800cbe17  mov     r9, [rbp+0B0h+arg_18]
0x1800cbe1e  lea     r8, [rsp+1B0h+var_140]
0x1800cbe23  mov     rdx, rsi
0x1800cbe26  mov     rcx, [rsi+100h]
0x1800cbe2d  call    ?SetDebugConfiguration@LayerStore@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@V?$optional@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@PEAX@Z; Container::Manager::Core::Details::LayerStore::SetDebugConfiguration(_GUID const &,utl::optional<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,void *)
0x1800cbe32  mov     r14d, eax
0x1800cbe35  test    eax, eax
0x1800cbe37  jns     loc_1800CBED7
0x1800cbe3d  mov     rcx, [rbp+0B8h]; this
0x1800cbe44  mov     r9d, eax; char *
0x1800cbe47  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbe4e  mov     edx, 0B6Eh; void *
0x1800cbe53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbe58  mov     [rdi+8], r13d
0x1800cbe5c  mov     rcx, rdi; SRWLock
0x1800cbe5f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cbe66  nop     dword ptr [rax+rax+00h]
0x1800cbe6b  lea     rcx, [rbp+0B0h+arg_18]; this
0x1800cbe72  call    ??1RegistryTransaction@Csl@@QEAA@XZ; Csl::RegistryTransaction::~RegistryTransaction(void)
0x1800cbe77  nop
0x1800cbe78  mov     rcx, [rsp+1B0h+var_148]; this
0x1800cbe7d  test    rcx, rcx
0x1800cbe80  jz      short loc_1800CBE88
0x1800cbe82  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800cbe87  nop
0x1800cbe88  lea     rax, [rsp+1B0h+var_180]
0x1800cbe8d  mov     rcx, qword ptr [rsp+1B0h+var_190]; void *
0x1800cbe92  cmp     rcx, rax
0x1800cbe95  jz      short loc_1800CBEA3
0x1800cbe97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbe9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cbea3  lea     rax, [rsp+1B0h+var_160]
0x1800cbea8  mov     rcx, [rsp+1B0h+var_170]; void *
0x1800cbead  cmp     rcx, rax
0x1800cbeb0  jz      short loc_1800CBEBE
0x1800cbeb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbeb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cbebe  cmp     [rbx+0D8h], r13b
0x1800cbec5  jz      short loc_1800CBECF
0x1800cbec7  mov     rcx, rbx; this
0x1800cbeca  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x1800cbecf  mov     eax, r14d
0x1800cbed2  jmp     loc_1800CC204
0x1800cbed7  mov     r12d, [rsi+120h]
0x1800cbede  or      r12d, 1
0x1800cbee2  mov     r9, [rbp+0B0h+arg_18]
0x1800cbee9  mov     r8d, r12d
0x1800cbeec  mov     rdx, rsi
0x1800cbeef  mov     rcx, [rsi+100h]
0x1800cbef6  call    ?SetFlags@LayerStore@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@W4LayerFlags@2345@PEAX@Z; Container::Manager::Core::Details::LayerStore::SetFlags(_GUID const &,Container::Manager::Core::Details::LayerFlags,void *)
0x1800cbefb  mov     r14d, eax
0x1800cbefe  test    eax, eax
0x1800cbf00  jns     short loc_1800CBF52
0x1800cbf02  mov     rcx, [rbp+0B8h]; this
0x1800cbf09  mov     r9d, eax; char *
0x1800cbf0c  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800cbf13  mov     edx, 0B75h; void *
0x1800cbf18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbf1d  mov     [rdi+8], r13d
  ... truncated ...
```
