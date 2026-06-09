# Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseMultipleLocked(utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>> const &,bool,bool,Csl::SrwLock::ReleaseOnScopeExit<0> &,utl::optional<Csl::DurableRegistryTransaction>)

- ea: `0x18006202c`
- end: `0x18006275c`
- name: `?SetDeleteOnCloseMultipleLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBV?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@_N1AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@V?$optional@VDurableRegistryTransaction@Csl@@@7@@Z`
- size: `1840`
- prototype: `__int64 __fastcall(int, int, int, int, int, Csl::DurableRegistryTransaction *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180062acc`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x1800069db`
- `0x18000a10c`
- `0x18000da88`
- `0x180016718`
- `0x1800329ec`
- `0x180032b24`
- `0x180032c1c`
- `0x180033568`
- `0x18003417c`
- `0x180042b58`
- `0x18005ce8c`
- `0x1800606ac`
- `0x180061c00`
- `0x18006202c`
- `0x180063c98`
- `0x180066000`
- `0x180087d88`
- `0x1800ea808`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062471`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062544`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062596`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006267c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062471`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062544`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062596`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006267c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006249e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006256f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800625d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006263d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006249e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006256f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800625d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006263d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006233a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800623a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006233a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800623a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800622a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800622a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800625a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800625a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062688`

## string_xrefs

- `0x1800620ff`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180062135`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180062380`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800623b3`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800623e0`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800624ca`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180062661`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180062738`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18006274a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseMultipleLocked(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4,
        char *a5,
        Csl::DurableRegistryTransaction *a6)
{
  __int64 v8; // rcx
  __int64 v9; // r12
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  char *v12; // rax
  __int64 v13; // r15
  __int64 v14; // rsi
  int v15; // eax
  unsigned int v16; // ebx
  int v18; // esi
  bool v19; // zf
  int v20; // edx
  void *v21; // r13
  struct Container::Manager::Core::Details::Resource **v22; // rdi
  __int64 v23; // rbx
  bool v24; // al
  __int64 v25; // r8
  const char *v26; // r9
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rsi
  char *v29; // rax
  void *v30; // rbx
  size_t v31; // r15
  char v32; // al
  int v33; // eax
  RTL_SRWLOCK *v34; // rbx
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  int v38; // eax
  int v39; // ecx
  unsigned __int64 v40; // r15
  _QWORD *v41; // r12
  __int64 v42; // rbx
  char v43; // al
  const char *v44; // r9
  char v45; // di
  __int64 v46; // rcx
  __int64 v47; // rbx
  int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rbx
  int v51; // eax
  unsigned int v52; // eax
  __int64 v53; // rbx
  int v54; // eax
  unsigned int v55; // eax
  void *v56; // rsi
  struct Container::Manager::Core::Details::Resource **i; // rbx
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  int v61; // [rsp+28h] [rbp-69h]
  int v62; // [rsp+28h] [rbp-69h]
  __int64 v63; // [rsp+38h] [rbp-59h]
  __int64 v64; // [rsp+40h] [rbp-51h]
  void *v65; // [rsp+48h] [rbp-49h]
  __int128 v66; // [rsp+50h] [rbp-41h] BYREF
  __int16 v67; // [rsp+60h] [rbp-31h]
  void *v68[2]; // [rsp+68h] [rbp-29h] BYREF
  __int64 v69; // [rsp+78h] [rbp-19h]
  __int64 v70; // [rsp+80h] [rbp-11h]
  char v71; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+4Fh]
  bool v76; // [rsp+100h] [rbp+6Fh]
  int v77; // [rsp+100h] [rbp+6Fh]
  int v78; // [rsp+110h] [rbp+7Fh]

  v67 = 0;
  v66 = 0;
  if ( *((_BYTE *)a6 + 24) )
  {
    Csl::DurableRegistryTransaction::operator=(&v66, a6);
  }
  else
  {
    v15 = Csl::DurableRegistryTransaction::Initialize(&v66);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1924,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v15,
        v61);
      Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)&v66);
      if ( *((_BYTE *)a6 + 24) )
        Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a6);
      return v16;
    }
  }
  v8 = a2[1];
  v9 = *a2;
  v10 = (v8 - *a2) >> 3;
  if ( v10 )
  {
    v11 = 8;
    if ( v10 > 8 )
    {
      if ( v10 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_13;
      v11 = (__int64)(a2[1] - *a2) >> 3;
    }
    v12 = (char *)operator new(v11, (const struct std::nothrow_t *)&std::nothrow);
    v13 = (__int64)v12;
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v8 = a2[1];
      v14 = (__int64)&v12[v11];
      v9 = *a2;
      v64 = (__int64)&v12[v11];
      goto LABEL_18;
    }
LABEL_13:
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v61);
    Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)&v66);
    v19 = *((_BYTE *)a6 + 24) == 0;
    goto LABEL_14;
  }
  v14 = -1;
  v64 = -1;
  v13 = -1;
LABEL_18:
  v70 = -1;
  v69 = -1;
  v20 = 0;
  v78 = 0;
  v21 = (void *)v13;
  v65 = (void *)v13;
  *(__m128i *)v68 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v22 = (struct Container::Manager::Core::Details::Resource **)v68[1];
  if ( !((v8 - v9) >> 3) )
  {
LABEL_49:
    v38 = Csl::DurableRegistryTransaction::Commit((Csl::DurableRegistryTransaction *)&v66);
    v18 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1960,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v38,
        v61);
      goto LABEL_51;
    }
    v56 = v68[0];
    for ( i = (struct Container::Manager::Core::Details::Resource **)v68[0]; i != v22; ++i )
      Container::Manager::Core::Details::ResourceBroker::QueueResourceForDeletionLocked(
        (Container::Manager::Core::Details::ResourceBroker *)a1,
        *i);
    Container::Manager::Core::Details::ResourceBroker::StartCleanupWorkIfNeededLocked((Container::Manager::Core::Details::ResourceBroker *)a1);
    v58 = *(_QWORD *)a5;
    if ( *(_QWORD *)a5 )
    {
      *(_DWORD *)(v58 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v58);
      *(_QWORD *)a5 = 0;
    }
    v59 = Csl::DurableRegistryTransaction::Flush((Csl::DurableRegistryTransaction *)&v66);
    if ( v59 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1994,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v59,
        v61);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    if ( a5 == &v71 )
    {
      if ( a1 != -16 )
      {
        *(_DWORD *)(a1 + 24) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
      }
    }
    else
    {
      v60 = *(_QWORD *)a5;
      if ( *(_QWORD *)a5 )
      {
        *(_DWORD *)(v60 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v60);
      }
      *(_QWORD *)a5 = a1 + 16;
    }
    if ( v56 != (void *)-1LL )
      operator delete(v56, (const struct std::nothrow_t *)&std::nothrow);
    if ( v21 != (void *)-1LL )
      operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
    Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)&v66);
    if ( *((_BYTE *)a6 + 24) )
      Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a6);
    return 0;
  }
  while ( 1 )
  {
    v23 = v20;
    v63 = v20;
    v24 = Container::Manager::Core::Details::Resource::IsDeleteOnClose(*(Container::Manager::Core::Details::Resource **)(v9 + 8LL * v20));
    v76 = v24;
    if ( v13 != v14 )
      goto LABEL_27;
    v27 = v14 - (_QWORD)v21;
    v28 = 7 * ((unsigned __int64)(v14 - (_QWORD)v21) >> 2) + 8;
    if ( v28 > 0x7FFFFFFFFFFFFFFFLL )
      v28 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v27 < v28 )
    {
      v29 = (char *)operator new(v28, (const struct std::nothrow_t *)&std::nothrow);
      v30 = v29;
      if ( (unsigned __int64)(v29 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v31 = v13 - (_QWORD)v21;
        v64 = (__int64)&v29[v28];
        memcpy_0(v29, v21, v31);
        v13 = (__int64)v30 + v31;
        if ( v21 != (void *)-1LL )
          operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
        v24 = v76;
        v21 = v30;
        v65 = v30;
        v23 = v63;
LABEL_27:
        *(_BYTE *)v13++ = v24;
        v32 = 0;
        goto LABEL_28;
      }
      v23 = v63;
    }
    v32 = 1;
LABEL_28:
    if ( v32 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1935,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        v26);
    LOBYTE(v26) = 1;
    LOBYTE(v25) = a3;
    v61 = (int)a5;
    v33 = Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseLocked(
            a1,
            *(_QWORD *)(v9 + 8 * v23),
            v25,
            v26);
    v18 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x1940,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v33,
        (int)a5);
      goto LABEL_51;
    }
    v34 = (RTL_SRWLOCK *)(*(_QWORD *)(v9 + 8 * v23) + 112LL);
    AcquireSRWLockShared(v34);
    v35 = *(_QWORD *)(v9 + 8 * v63);
    if ( !*(_QWORD *)(v35 + 152)
      && !*(_BYTE *)(v35 + 256)
      && Container::Manager::Core::Details::Resource::IsDeleteOnClose((Container::Manager::Core::Details::Resource *)v35) )
    {
      break;
    }
LABEL_40:
    if ( v34 )
      ReleaseSRWLockShared(v34);
    v20 = v78 + 1;
    v78 = v20;
    v9 = *a2;
    if ( v20 >= (unsigned __int64)((__int64)(a2[1] - *a2) >> 3) )
      goto LABEL_49;
    v14 = v64;
  }
  if ( v22 != (struct Container::Manager::Core::Details::Resource **)v70 )
  {
LABEL_39:
    *v22++ = *(struct Container::Manager::Core::Details::Resource **)(v9 + 8 * v63);
    v68[1] = v22;
    goto LABEL_40;
  }
  v36 = (signed __int64)(v70 - (unsigned __int64)v68[0]) >> 3;
  v37 = 7 * (v36 >> 2) + 8;
  if ( v37 > 0xFFFFFFFFFFFFFFFLL )
    v37 = 0xFFFFFFFFFFFFFFFLL;
  if ( v36 < v37
    && (unsigned __int8)utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(v68) )
  {
    v22 = (struct Container::Manager::Core::Details::Resource **)v68[1];
    v70 = v69;
    goto LABEL_39;
  }
  v18 = -2147024882;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x1955,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
    (const char *)0x8007000ELL,
    (int)a5);
  if ( v34 )
    ReleaseSRWLockShared(v34);
LABEL_51:
  v39 = 0;
  v77 = 0;
  v40 = v13 - (_QWORD)v21;
  if ( v40 )
  {
    v41 = a2;
    do
    {
      v42 = v39;
      v43 = Container::Manager::Core::Details::Resource::IsDeleteOnClose(*(Container::Manager::Core::Details::Resource **)(*v41 + 8LL * v39));
      v45 = *((_BYTE *)v21 + v42);
      if ( v43 != v45 )
      {
        v46 = *(_QWORD *)(*v41 + 8 * v42);
        switch ( *(_DWORD *)(v46 + 16) )
        {
          case 1:
            if ( !*(_BYTE *)(v46 + 40) )
              __int2c();
            Container::Manager::Core::Details::ContainerStorage::SetDeleteOnCloseMemoryState(
              *(Container::Manager::Core::Details::ContainerStorage **)(v46 + 32),
              *((_BYTE *)v21 + v42));
            break;
          case 2:
            if ( !*(_BYTE *)(v46 + 56) )
              __int2c();
            v53 = *(_QWORD *)(v46 + 48);
            AcquireSRWLockExclusive((PSRWLOCK)(v53 + 272));
            *(_DWORD *)(v53 + 280) = GetCurrentThreadId();
            v54 = *(_DWORD *)(v53 + 288);
            if ( v45 )
              v55 = v54 | 4;
            else
              v55 = v54 & 0xFFFFFFFB;
            *(_DWORD *)(v53 + 288) = v55;
            *(_DWORD *)(v53 + 280) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(v53 + 272));
            v21 = v65;
            break;
          case 3:
            if ( !*(_BYTE *)(v46 + 72) )
              __int2c();
            v50 = *(_QWORD *)(v46 + 64);
            AcquireSRWLockExclusive((PSRWLOCK)v50);
            v51 = *(_DWORD *)(v50 + 100);
            if ( v45 )
              v52 = v51 | 1;
            else
              v52 = v51 & 0xFFFFFFFE;
            *(_DWORD *)(v50 + 100) = v52;
            if ( v50 )
              ReleaseSRWLockExclusive((PSRWLOCK)v50);
            break;
          case 4:
            if ( !*(_BYTE *)(v46 + 88) )
              __int2c();
            Container::Manager::Core::Details::Zygote::SetDeleteOnClose(*(PSRWLOCK *)(v46 + 80), *((_BYTE *)v21 + v42));
            break;
          case 5:
            if ( !*(_BYTE *)(v46 + 104) )
              __int2c();
            v47 = *(_QWORD *)(v46 + 96);
            AcquireSRWLockExclusive((PSRWLOCK)(v47 + 128));
            v48 = *(_DWORD *)(v47 + 140);
            if ( v45 )
              v49 = v48 | 1;
            else
              v49 = v48 & 0xFFFFFFFE;
            *(_DWORD *)(v47 + 140) = v49;
            if ( v47 != -128 )
              ReleaseSRWLockExclusive((PSRWLOCK)(v47 + 128));
            v41 = a2;
            break;
          default:
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x859,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
              v44);
        }
      }
      v39 = ++v77;
    }
    while ( v77 < v40 );
  }
  if ( v18 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v18,
      v62);
  if ( v68[0] != (void *)-1LL )
    operator delete(v68[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v21 != (void *)-1LL )
    operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
  Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)&v66);
  v19 = *((_BYTE *)a6 + 24) == 0;
LABEL_14:
  if ( !v19 )
    Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a6);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18006202c  mov     rax, rsp
0x18006202f  mov     [rax+20h], r9b
0x180062033  mov     [rax+18h], r8b
0x180062037  mov     [rax+10h], rdx
0x18006203b  mov     [rax+8], rcx
0x18006203f  push    rbp
0x180062040  push    rbx
0x180062041  push    rsi
0x180062042  push    rdi
0x180062043  push    r12
0x180062045  push    r13
0x180062047  push    r14
0x180062049  push    r15
0x18006204b  lea     rbp, [rax-4Fh]
0x18006204f  sub     rsp, 98h
0x180062056  mov     r14, [rbp+47h+arg_28]
0x18006205a  lea     rcx, [rbp+47h+var_88]
0x18006205e  xor     r13d, r13d
0x180062061  xorps   xmm0, xmm0
0x180062064  mov     rdi, rdx
0x180062067  mov     [rbp+47h+var_78], r13w
0x18006206c  movdqu  [rbp+47h+var_88], xmm0
0x180062071  cmp     [r14+18h], r13b
0x180062075  jz      short loc_1800620F0
0x180062077  mov     rdx, r14
0x18006207a  call    ??4DurableRegistryTransaction@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::DurableRegistryTransaction::operator=(Csl::DurableRegistryTransaction &&)
0x18006207f  mov     rcx, [rdi+8]
0x180062083  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180062087  mov     r12, [rdi]
0x18006208a  mov     rax, rcx
0x18006208d  sub     rax, r12
0x180062090  mov     r8, 7FFFFFFFFFFFFFFFh
0x18006209a  sar     rax, 3
0x18006209e  test    rax, rax
0x1800620a1  jz      loc_18006216C
0x1800620a7  lea     ebx, [rdx+9]
0x1800620aa  cmp     rax, rbx
0x1800620ad  jbe     short loc_1800620BC
0x1800620af  cmp     rax, r8
0x1800620b2  ja      short loc_180062131
0x1800620b4  mov     rbx, rax
0x1800620b7  cmp     rax, rax
0x1800620ba  ja      short loc_180062131
0x1800620bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800620c3  mov     rcx, rbx; unsigned __int64
0x1800620c6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800620cb  mov     r15, rax
0x1800620ce  lea     rcx, [rax-1]
0x1800620d2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800620d6  ja      short loc_180062131
0x1800620d8  mov     rcx, [rdi+8]
0x1800620dc  lea     rsi, [rax+rbx]
0x1800620e0  mov     r12, [rdi]
0x1800620e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800620e7  mov     [rbp+47h+var_98], rsi
0x1800620eb  jmp     loc_180062176
0x1800620f0  call    ?Initialize@DurableRegistryTransaction@Csl@@QEAAJW4RegistryHive@2@@Z; Csl::DurableRegistryTransaction::Initialize(Csl::RegistryHive)
0x1800620f5  mov     ebx, eax
0x1800620f7  test    eax, eax
0x1800620f9  jns     short loc_18006207F
0x1800620fb  mov     rcx, [rbp+4Fh]; this
0x1800620ff  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180062106  mov     r9d, eax; char *
0x180062109  mov     edx, 1924h; void *
0x18006210e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062113  lea     rcx, [rbp+47h+var_88]; this
0x180062117  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x18006211c  cmp     [r14+18h], r13b
0x180062120  jz      short loc_18006212A
0x180062122  mov     rcx, r14; this
0x180062125  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x18006212a  mov     eax, ebx
0x18006212c  jmp     loc_18006271F
0x180062131  mov     rcx, [rbp+4Fh]; this
0x180062135  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006213c  mov     esi, 8007000Eh
0x180062141  mov     edx, 192Ch; void *
0x180062146  mov     r9d, esi; char *
0x180062149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006214e  lea     rcx, [rbp+47h+var_88]; this
0x180062152  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x180062157  cmp     [r14+18h], r13b
0x18006215b  jz      short loc_180062165
0x18006215d  mov     rcx, r14; this
0x180062160  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x180062165  mov     eax, esi
0x180062167  jmp     loc_18006271F
0x18006216c  mov     rsi, rdx
0x18006216f  mov     [rbp+47h+var_98], rdx
0x180062173  mov     r15, rdx
0x180062176  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006217e  sub     rcx, r12
0x180062181  sar     rcx, 3
0x180062185  mov     [rbp+47h+var_58], rdx
0x180062189  mov     [rbp+47h+var_60], rdx
0x18006218d  mov     edx, r13d
0x180062190  mov     dword ptr [rbp+47h+arg_28], edx
0x180062193  mov     r13, r15
0x180062196  mov     [rbp+47h+var_90], r15
0x18006219a  movdqu  xmmword ptr [rbp+47h+var_70], xmm0
0x18006219f  mov     rdi, [rbp+47h+var_70+8]
0x1800621a3  test    rcx, rcx
0x1800621a6  jz      loc_1800623C9
0x1800621ac  movsxd  rbx, edx
0x1800621af  mov     [rbp+47h+var_A0], rbx
0x1800621b3  mov     rcx, [r12+rbx*8]; this
0x1800621b7  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x1800621bc  mov     byte ptr [rbp+47h+arg_18], al
0x1800621bf  cmp     r15, rsi
0x1800621c2  jnz     loc_180062255
0x1800621c8  mov     rdx, rsi
0x1800621cb  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800621d5  sub     rdx, r13
0x1800621d8  mov     rcx, rdx
0x1800621db  shr     rcx, 2
0x1800621df  imul    rsi, rcx, 7
0x1800621e3  add     rsi, 8
0x1800621e7  cmp     rsi, rax
0x1800621ea  cmova   rsi, rax
0x1800621ee  cmp     rdx, rsi
0x1800621f1  jnb     loc_180062375
0x1800621f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800621fe  mov     rcx, rsi; unsigned __int64
0x180062201  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180062206  mov     rbx, rax
0x180062209  lea     rcx, [rax-1]
0x18006220d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180062211  ja      loc_180062371
0x180062217  add     rax, rsi
0x18006221a  sub     r15, r13
0x18006221d  mov     r8, r15; Size
0x180062220  mov     [rbp+47h+var_98], rax
0x180062224  mov     rdx, r13; Src
0x180062227  mov     rcx, rbx; void *
0x18006222a  call    memcpy_0
0x18006222f  add     r15, rbx
0x180062232  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180062236  jz      short loc_180062247
0x180062238  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006223f  mov     rcx, r13; void *
0x180062242  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180062247  mov     al, byte ptr [rbp+47h+arg_18]
0x18006224a  mov     r13, rbx
0x18006224d  mov     [rbp+47h+var_90], rbx
0x180062251  mov     rbx, [rbp+47h+var_A0]
0x180062255  mov     [r15], al
0x180062258  inc     r15
0x18006225b  xor     al, al
0x18006225d  mov     rcx, [rbp+4Fh]; this
0x180062261  test    al, al
0x180062263  jnz     loc_18006274A
0x180062269  mov     rax, qword ptr [rbp+47h+var_88+8]
0x18006226d  mov     r9b, 1
0x180062270  mov     r8b, [rbp+47h+arg_10]
0x180062274  mov     rdx, [r12+rbx*8]
0x180062278  mov     rcx, [rbp+47h+arg_0]
0x18006227c  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x180062281  mov     rax, [rbp+47h+arg_20]
0x180062285  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006228a  call    ?SetDeleteOnCloseLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBVResource@2345@_N1AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@PEAX@Z; Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseLocked(Container::Manager::Core::Details::Resource const &,bool,bool,Csl::SrwLock::ReleaseOnScopeExit<0> &,void *)
0x18006228f  mov     esi, eax
0x180062291  test    eax, eax
0x180062293  js      loc_1800623AF
0x180062299  mov     rbx, [r12+rbx*8]
0x18006229d  add     rbx, 70h ; 'p'
0x1800622a1  mov     rcx, rbx; SRWLock
0x1800622a4  call    cs:__imp_AcquireSRWLockShared
0x1800622ab  nop     dword ptr [rax+rax+00h]
0x1800622b0  mov     rsi, [rbp+47h+var_A0]
0x1800622b4  mov     rcx, [r12+rsi*8]; this
0x1800622b8  cmp     qword ptr [rcx+98h], 0
0x1800622c0  jnz     short loc_180062332
0x1800622c2  cmp     byte ptr [rcx+100h], 0
0x1800622c9  jnz     short loc_180062332
0x1800622cb  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x1800622d0  test    al, al
0x1800622d2  jz      short loc_180062332
0x1800622d4  mov     rcx, [rbp+47h+var_58]
0x1800622d8  cmp     rdi, rcx
0x1800622db  jnz     short loc_180062323
0x1800622dd  sub     rcx, [rbp+47h+var_70]
0x1800622e1  sar     rcx, 3
0x1800622e5  mov     rax, rcx
0x1800622e8  shr     rax, 2
0x1800622ec  imul    rdx, rax, 7
0x1800622f0  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800622fa  add     rdx, 8
0x1800622fe  cmp     rdx, rax
0x180062301  cmova   rdx, rax
0x180062305  cmp     rcx, rdx
0x180062308  jnb     short loc_18006237C
0x18006230a  lea     rcx, [rbp+47h+var_70]
0x18006230e  call    ?_SetCapacity@?$vector@PEAVResourceHandle@Core@Manager@Container@@V?$allocator@PEAVResourceHandle@Core@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(unsigned __int64)
0x180062313  test    al, al
0x180062315  jz      short loc_18006237C
0x180062317  mov     rax, [rbp+47h+var_60]
0x18006231b  mov     rdi, [rbp+47h+var_70+8]
0x18006231f  mov     [rbp+47h+var_58], rax
0x180062323  mov     rax, [r12+rsi*8]
0x180062327  mov     [rdi], rax
0x18006232a  add     rdi, 8
0x18006232e  mov     [rbp+47h+var_70+8], rdi
0x180062332  test    rbx, rbx
0x180062335  jz      short loc_180062346
0x180062337  mov     rcx, rbx; SRWLock
0x18006233a  call    cs:__imp_ReleaseSRWLockShared
0x180062341  nop     dword ptr [rax+rax+00h]
0x180062346  mov     rax, [rbp+47h+arg_8]
0x18006234a  mov     edx, dword ptr [rbp+47h+arg_28]
0x18006234d  inc     edx
0x18006234f  mov     dword ptr [rbp+47h+arg_28], edx
0x180062352  mov     r12, [rax]
0x180062355  mov     rcx, [rax+8]
0x180062359  sub     rcx, r12
0x18006235c  movsxd  rax, edx
0x18006235f  sar     rcx, 3
0x180062363  cmp     rax, rcx
0x180062366  jnb     short loc_1800623C9
0x180062368  mov     rsi, [rbp+47h+var_98]
0x18006236c  jmp     loc_1800621AC
0x180062371  mov     rbx, [rbp+47h+var_A0]
0x180062375  mov     al, 1
0x180062377  jmp     loc_18006225D
0x18006237c  mov     rcx, [rbp+4Fh]; this
0x180062380  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180062387  mov     esi, 8007000Eh
0x18006238c  mov     edx, 1955h; void *
0x180062391  mov     r9d, esi; char *
0x180062394  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180062399  test    rbx, rbx
0x18006239c  jz      short loc_1800623F4
0x18006239e  mov     rcx, rbx; SRWLock
0x1800623a1  call    cs:__imp_ReleaseSRWLockShared
0x1800623a8  nop     dword ptr [rax+rax+00h]
0x1800623ad  jmp     short loc_1800623F4
0x1800623af  mov     rcx, [rbp+4Fh]; this
0x1800623b3  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800623ba  mov     r9d, eax; char *
0x1800623bd  mov     edx, 1940h; void *
0x1800623c2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800623c7  jmp     short loc_1800623F4
0x1800623c9  lea     rcx, [rbp+47h+var_88]; this
0x1800623cd  call    ?Commit@DurableRegistryTransaction@Csl@@QEAAJXZ; Csl::DurableRegistryTransaction::Commit(void)
0x1800623d2  mov     esi, eax
0x1800623d4  test    eax, eax
0x1800623d6  jns     loc_180062604
0x1800623dc  mov     rcx, [rbp+4Fh]; this
0x1800623e0  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800623e7  mov     r9d, eax; char *
0x1800623ea  mov     edx, 1960h; void *
0x1800623ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800623f4  xor     ecx, ecx
0x1800623f6  mov     [rbp+47h+arg_18], ecx
0x1800623f9  sub     r15, r13
0x1800623fc  jz      loc_1800624C2
0x180062402  mov     r12, [rbp+47h+arg_8]
0x180062406  movsxd  rbx, ecx
0x180062409  mov     rcx, [r12]
0x18006240d  mov     rcx, [rcx+rbx*8]; this
0x180062411  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180062416  mov     dil, [rbx+r13]
0x18006241a  cmp     al, dil
0x18006241d  jz      loc_1800624AE
0x180062423  mov     rax, [r12]
0x180062427  mov     rcx, [rax+rbx*8]
0x18006242b  mov     edx, [rcx+10h]
0x18006242e  sub     edx, 1
0x180062431  jz      loc_1800625EB
0x180062437  sub     edx, 1
0x18006243a  jz      loc_180062580
0x180062440  sub     edx, 1
0x180062443  jz      loc_180062535
0x180062449  sub     edx, 1
0x18006244c  jz      loc_18006251C
0x180062452  cmp     edx, 1
0x180062455  jnz     loc_180062734
0x18006245b  cmp     byte ptr [rcx+68h], 0
0x18006245f  jnz     short loc_180062463
0x180062461  int     2Ch; Windows NT - assertion failure
0x180062463  mov     rbx, [rcx+60h]
0x180062467  lea     r12, [rbx+80h]
0x18006246e  mov     rcx, r12; SRWLock
0x180062471  call    cs:__imp_AcquireSRWLockExclusive
0x180062478  nop     dword ptr [rax+rax+00h]
0x18006247d  mov     eax, [rbx+8Ch]
0x180062483  test    dil, dil
0x180062486  jz      short loc_18006248D
0x180062488  or      eax, 1
0x18006248b  jmp     short loc_180062490
0x18006248d  and     eax, 0FFFFFFFEh
0x180062490  mov     [rbx+8Ch], eax
0x180062496  test    r12, r12
0x180062499  jz      short loc_1800624AA
0x18006249b  mov     rcx, r12; SRWLock
0x18006249e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800624a5  nop     dword ptr [rax+rax+00h]
0x1800624aa  mov     r12, [rbp+47h+arg_8]
0x1800624ae  mov     ecx, [rbp+47h+arg_18]
0x1800624b1  inc     ecx
0x1800624b3  movsxd  rax, ecx
  ... truncated ...
```
