# Container::Manager::Core::Details::ResourceBroker::RecreateLayerStorage(Container::Manager::Core::ResourceHandle const &)

- ea: `0x1800606e8`
- end: `0x180060e97`
- name: `?RecreateLayerStorage@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBVResourceHandle@345@@Z`
- size: `1967`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ResourceBroker *__hidden this, const struct Container::Manager::Core::ResourceHandle *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800d1e6c`
- `0x1800d2a68`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180005704`
- `0x18000da88`
- `0x180016718`
- `0x18002bd50`
- `0x1800329ec`
- `0x180032b24`
- `0x18003417c`
- `0x1800393cc`
- `0x18003943c`
- `0x18003d360`
- `0x18003e50c`
- `0x18003e9f4`
- `0x18004feb4`
- `0x18005648c`
- `0x18005bee8`
- `0x180060294`
- `0x1800606e8`
- `0x180062acc`
- `0x180087b80`
- `0x180087d88`
- `0x1800cc950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060ad9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060caa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060ad9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060caa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060b74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060cd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060b74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060cd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180060b19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180060b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180060b05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180060b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060ae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060cb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060ae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060cb6`

## string_xrefs

- `0x18006077b`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800609a0`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060a68`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060b55`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060c7a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060cec`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060df9`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060e1e`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180060974`: `ResourceBroker_RecreateLayerStorage_New`
- `0x180060a41`: `ResourceBroker_RecreateLayerStorage_Old`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ResourceBroker::RecreateLayerStorage(
        RTL_SRWLOCK *this,
        const struct Container::Manager::Core::ResourceHandle *a2)
{
  __int64 v3; // r12
  int Guid; // eax
  struct _GUID *v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  GUID v8; // xmm6
  Container::Manager::Core::ResourceHandle *v9; // rax
  Container::Manager::Core::ResourceHandle *v10; // rdi
  int Resource; // eax
  __int64 v12; // rdx
  Container::Manager::Core::ResourceHandle *v13; // rax
  Container::Manager::Core::ResourceHandle *v14; // rsi
  int v15; // eax
  bool v16; // zf
  void *v17; // rcx
  PSRWLOCK v18; // r14
  RTL_SRWLOCK *v19; // r13
  int v20; // eax
  int v21; // r15d
  __int64 v22; // rdx
  _OWORD *v23; // rbx
  RTL_SRWLOCK *v24; // rcx
  Container::Manager::Core::ResourceHandle *v25; // rbx
  int v27; // [rsp+28h] [rbp-E0h]
  int v28; // [rsp+28h] [rbp-E0h]
  Container::Manager::Core::Details::ContainerStorage *v29; // [rsp+38h] [rbp-D0h]
  __int16 v30; // [rsp+3Dh] [rbp-CBh]
  char v31; // [rsp+3Fh] [rbp-C9h]
  Container::Manager::Core::ResourceHandle *v32; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t *v34; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-B0h]
  __int128 v36; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+70h] [rbp-98h]
  RTL_SRWLOCK *v38; // [rsp+78h] [rbp-90h]
  int v39[4]; // [rsp+80h] [rbp-88h] BYREF
  char v40; // [rsp+98h] [rbp-70h]
  _DWORD v41[2]; // [rsp+A8h] [rbp-60h] BYREF
  GUID v42; // [rsp+B0h] [rbp-58h]
  __int64 v43; // [rsp+C0h] [rbp-48h]
  __int128 v44; // [rsp+C8h] [rbp-40h]
  void *v45[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-10h]
  struct _GUID v48; // [rsp+108h] [rbp+0h] BYREF
  struct _GUID v49; // [rsp+118h] [rbp+10h] BYREF
  int v50; // [rsp+128h] [rbp+20h]
  int v51; // [rsp+12Ch] [rbp+24h]
  __int128 v52; // [rsp+130h] [rbp+28h]
  int v53; // [rsp+140h] [rbp+38h]
  __int64 v54; // [rsp+148h] [rbp+40h]
  _DWORD v55[2]; // [rsp+150h] [rbp+48h] BYREF
  GUID v56; // [rsp+158h] [rbp+50h]
  __int64 v57; // [rsp+168h] [rbp+60h]
  __int64 v58; // [rsp+170h] [rbp+68h]
  char v59; // [rsp+178h] [rbp+70h]
  int v60; // [rsp+179h] [rbp+71h]
  __int16 v61; // [rsp+17Dh] [rbp+75h]
  char v62; // [rsp+17Fh] [rbp+77h]
  char v63[40]; // [rsp+180h] [rbp+78h] BYREF
  char v64; // [rsp+1A8h] [rbp+A0h]
  _BYTE v65[304]; // [rsp+1B0h] [rbp+A8h] BYREF
  __int128 v66; // [rsp+2E0h] [rbp+1D8h]
  __int128 v67; // [rsp+2F0h] [rbp+1E8h]
  _OWORD v68[2]; // [rsp+300h] [rbp+1F8h] BYREF
  __int128 v69; // [rsp+320h] [rbp+218h]
  __int128 v70; // [rsp+330h] [rbp+228h]
  __int128 v71; // [rsp+340h] [rbp+238h]
  wil::details::in1diag3 *retaddr; // [rsp+3B0h] [rbp+2A8h]

  v38 = this;
  v3 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(a2);
  v36 = 0;
  LOWORD(v37) = 0;
  Guid = Csl::DurableRegistryTransaction::Initialize(&v36);
  v6 = Guid;
  if ( Guid < 0 )
  {
    v7 = 4074;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)Guid,
      v27);
    goto LABEL_56;
  }
  v48 = 0;
  Guid = Csl::CreateGuid((Csl *)&v48, v5);
  v6 = Guid;
  if ( Guid < 0 )
  {
    v7 = 4078;
    goto LABEL_5;
  }
  v41[0] = 0;
  v42 = GUID_NULL;
  v47 = 0;
  *(_WORD *)((char *)&v43 + 5) = v30;
  v44 = 0;
  HIBYTE(v43) = v31;
  *(_OWORD *)v45 = 0;
  LOBYTE(v44) = 0;
  v46 = 0;
  BYTE8(v44) = 0;
  LOBYTE(v45[0]) = 0;
  LODWORD(v43) = 1;
  BYTE4(v43) = 1;
  v41[1] = 2;
  v8 = *(GUID *)v3;
  v52 = 0;
  v41[0] = 10;
  v42 = v8;
  LOBYTE(v52) = 0;
  v53 = 0;
  v54 = 0;
  memset_0(v55, 0, 0x60u);
  LOBYTE(v55[0]) = 0;
  v64 = 0;
  memset_0(v65, 0, sizeof(v65));
  v65[0] = 0;
  memset(v68, 0, 28);
  v65[296] = 0;
  LOBYTE(v68[0]) = 0;
  v66 = 0;
  LOBYTE(v66) = 0;
  v67 = 0;
  BYTE12(v67) = 0;
  v69 = 0;
  BYTE8(v68[1]) = 0;
  v71 = 0;
  LOBYTE(v69) = 0;
  v70 = 0;
  BYTE8(v71) = 0;
  v50 = 1;
  v51 = 1;
  v49 = v48;
  if ( v64 )
  {
    v57 = v43;
    v58 = v44;
    v60 = *(_DWORD *)((char *)&v44 + 9);
    v61 = *(_WORD *)((char *)&v44 + 13);
    v62 = HIBYTE(v44);
    v55[0] = 10;
    v55[1] = 2;
    v56 = v8;
    v59 = 0;
    utl::optional<Csl::Path>::operator=(v63, v45);
  }
  else
  {
    Container::Manager::Core::Details::ContainerStorageConfiguration::ContainerStorageConfiguration(v55, v41);
    v64 = 1;
  }
  v9 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFFF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      v27);
    goto LABEL_53;
  }
  *((_QWORD *)v9 + 5) = 0;
  *(_QWORD *)v9 = (char *)v9 + 16;
  *((_QWORD *)v9 + 1) = (char *)v9 + 16;
  *((_WORD *)v9 + 8) = 0;
  *((_DWORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 9) = 0;
  *((_BYTE *)v9 + 80) = 0;
  *((_QWORD *)v9 + 6) = 0;
  *((_QWORD *)v9 + 7) = 0;
  v34 = L"ResourceBroker_RecreateLayerStorage_New";
  v35 = 39;
  Resource = Container::Manager::Core::ResourceHandle::Initialize(v9, &v34);
  v6 = Resource;
  if ( Resource >= 0 )
  {
    Resource = Container::Manager::Core::Details::ResourceBroker::CreateResource((Container::Manager::Core::Details::ResourceBroker *)this);
    v6 = Resource;
    if ( Resource < 0 )
    {
      v12 = 4098;
      goto LABEL_12;
    }
    v29 = (Container::Manager::Core::Details::ContainerStorage *)Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(v10);
    v13 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( v13 )
    {
      *((_QWORD *)v13 + 5) = 0;
      *(_QWORD *)v13 = (char *)v13 + 16;
      *((_QWORD *)v13 + 1) = (char *)v13 + 16;
      *((_WORD *)v13 + 8) = 0;
      *((_DWORD *)v13 + 8) = 0;
      *((_QWORD *)v13 + 8) = 0;
      *((_QWORD *)v13 + 9) = 0;
      *((_BYTE *)v13 + 80) = 0;
      *((_QWORD *)v13 + 6) = 0;
      *((_QWORD *)v13 + 7) = 0;
      v32 = v13;
      v34 = L"ResourceBroker_RecreateLayerStorage_Old";
      v35 = 39;
      v15 = Container::Manager::Core::ResourceHandle::Initialize(v13, &v34);
      v6 = v15;
      if ( v15 >= 0 )
      {
        v18 = this + 2;
        AcquireSRWLockExclusive(this + 2);
        v19 = (RTL_SRWLOCK *)(v3 + 272);
        SRWLock = this + 2;
        LODWORD(this[3].Ptr) = GetCurrentThreadId();
        AcquireSRWLockShared((PSRWLOCK)(v3 + 272));
        if ( v3 != -272 )
          ReleaseSRWLockShared((PSRWLOCK)(v3 + 272));
        v34 = (wchar_t *)(v3 + 292);
        v20 = Container::Manager::Core::Details::ResourceBroker::OpenResourceLocked(this, v3 + 292, 1, &v32);
        v6 = v20;
        if ( v20 >= 0 )
        {
          if ( (*(_BYTE *)(v3 + 288) & 4) != 0
            || (v21 = Container::Manager::Core::Details::ContainerStorage::SetDeleteOnClose(
                        v29,
                        0,
                        *((void **)&v36 + 1)),
                v21 >= 0) )
          {
            v21 = Container::Manager::Core::Details::Layer::SetStorageId(
                    (Container::Manager::Core::Details::Layer *)v3,
                    &v48,
                    *((void **)&v36 + 1));
            if ( v21 >= 0 )
            {
              *(_OWORD *)v39 = 0;
              Csl::DurableRegistryTransaction::operator=(v39, &v36);
              v40 = 1;
              v21 = Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseResourceTreesLocked(
                      (int)v38,
                      (int)&SRWLock,
                      (Csl::DurableRegistryTransaction *)v39);
              if ( v21 >= 0 )
              {
                v24 = SRWLock;
                if ( SRWLock )
                {
                  LODWORD(SRWLock[1].Ptr) = 0;
                  ReleaseSRWLockExclusive(v24);
                }
                v25 = v32;
                if ( v32 )
                {
                  Container::Manager::Core::ResourceHandle::~ResourceHandle(v32);
                  operator delete(v25, (const struct std::nothrow_t *)0x58);
                }
                Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
                operator delete(v10, (const struct std::nothrow_t *)0x58);
                Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v49);
                if ( (_BYTE)v47 && v45[0] != &v46 )
                  operator delete(v45[0], (const struct std::nothrow_t *)&std::nothrow);
                v6 = 0;
                goto LABEL_56;
              }
              v14 = v32;
              v22 = 4142;
              v18 = SRWLock;
            }
            else
            {
              v22 = 4131;
            }
          }
          else
          {
            v22 = 4124;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v21,
            v27);
          if ( (*((_BYTE *)v29 + 272) & 2) == 0 )
            Container::Manager::Core::Details::ContainerStorage::SetDeleteOnCloseMemoryState(v29, 1);
          v23 = (_OWORD *)Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(v14);
          AcquireSRWLockExclusive(v19);
          *(_DWORD *)(v3 + 280) = GetCurrentThreadId();
          *(_OWORD *)v34 = *v23;
          *(_DWORD *)(v3 + 280) = 0;
          ReleaseSRWLockExclusive(v19);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x103B,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v21,
            v28);
          if ( v18 )
          {
            LODWORD(v18[1].Ptr) = 0;
            ReleaseSRWLockExclusive(v18);
          }
          if ( v14 )
          {
            Container::Manager::Core::ResourceHandle::~ResourceHandle(v14);
            operator delete(v14, (const struct std::nothrow_t *)0x58);
          }
          Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
          operator delete(v10, (const struct std::nothrow_t *)0x58);
          Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v49);
          if ( (_BYTE)v47 && v45[0] != &v46 )
            operator delete(v45[0], (const struct std::nothrow_t *)&std::nothrow);
          v6 = v21;
          goto LABEL_56;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1013,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)(unsigned int)v20,
          v27);
        LODWORD(this[3].Ptr) = 0;
        ReleaseSRWLockExclusive(this + 2);
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v14);
        operator delete(v14, (const struct std::nothrow_t *)0x58);
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
        operator delete(v10, (const struct std::nothrow_t *)0x58);
        Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v49);
        v16 = (_BYTE)v47 == 0;
        goto LABEL_19;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v15,
        v27);
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v14);
      operator delete(v14, (const struct std::nothrow_t *)0x58);
    }
    else
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1009,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        v27);
    }
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
    operator delete(v10, (const struct std::nothrow_t *)0x58);
    Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v49);
    v16 = (_BYTE)v47 == 0;
LABEL_19:
    if ( !v16 )
    {
      v17 = v45[0];
      if ( v45[0] != &v46 )
        goto LABEL_55;
    }
    goto LABEL_56;
  }
  v12 = 4096;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
    (const char *)(unsigned int)Resource,
    v27);
  Container::Manager::Core::ResourceHandle::~ResourceHandle(v10);
  operator delete(v10, (const struct std::nothrow_t *)0x58);
LABEL_53:
  Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration((Container::Manager::Core::Details::ResourceConfiguration *)&v49);
  if ( (_BYTE)v47 )
  {
    v17 = v45[0];
    if ( v45[0] != &v46 )
LABEL_55:
      operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
  }
LABEL_56:
  Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)&v36);
  return v6;
}

```

## disassembly

```asm
0x1800606e8  mov     rax, rsp
0x1800606eb  mov     [rax+18h], rbx
0x1800606ef  push    rbp
0x1800606f0  push    rsi
0x1800606f1  push    rdi
0x1800606f2  push    r12
0x1800606f4  push    r13
0x1800606f6  push    r14
0x1800606f8  push    r15
0x1800606fa  lea     rbp, [rax-2A8h]
0x180060701  sub     rsp, 370h
0x180060708  movaps  xmmword ptr [rax-48h], xmm6
0x18006070c  mov     rax, cs:__security_cookie
0x180060713  xor     rax, rsp
0x180060716  mov     [rbp+2A0h+var_50], rax
0x18006071d  mov     r15, rcx
0x180060720  mov     qword ptr [rsp+3A0h+var_330], rcx
0x180060725  mov     rcx, rdx
0x180060728  call    ??$Get@VLayer@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVLayer@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(void)
0x18006072d  xorps   xmm0, xmm0
0x180060730  lea     rcx, [rsp+3A0h+var_350+8]
0x180060735  xor     r14d, r14d
0x180060738  mov     r12, rax
0x18006073b  movdqu  [rsp+3A0h+var_350+8], xmm0
0x180060741  mov     word ptr [rsp+3A0h+var_338], r14w
0x180060747  call    ?Initialize@DurableRegistryTransaction@Csl@@QEAAJW4RegistryHive@2@@Z; Csl::DurableRegistryTransaction::Initialize(Csl::RegistryHive)
0x18006074c  mov     ebx, eax
0x18006074e  test    eax, eax
0x180060750  jns     short loc_180060759
0x180060752  mov     edx, 0FEAh
0x180060757  jmp     short loc_180060774
0x180060759  xorps   xmm0, xmm0
0x18006075c  lea     rcx, [rbp+2A0h+var_2A0]; this
0x180060760  movups  xmmword ptr [rbp+2A0h+var_2A0.Data1], xmm0
0x180060764  call    ?CreateGuid@Csl@@YAJAEAU_GUID@@@Z; Csl::CreateGuid(_GUID &)
0x180060769  mov     ebx, eax
0x18006076b  test    eax, eax
0x18006076d  jns     short loc_18006078F
0x18006076f  mov     edx, 0FEEh; void *
0x180060774  mov     rcx, [rbp+2A8h]; this
0x18006077b  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180060782  mov     r9d, eax; char *
0x180060785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006078a  jmp     loc_180060E5B
0x18006078f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180060796  xor     eax, eax
0x180060798  mov     [rbp+2A0h+var_300], r14d
0x18006079c  mov     [rbp+2A0h+var_2E8], rax
0x1800607a0  lea     rcx, [rbp+2A0h+var_258]; void *
0x1800607a4  mov     [rbp+2A0h+var_2B0], rax
0x1800607a8  mov     bl, r14b
0x1800607ab  movdqu  [rbp+2A0h+var_2F8], xmm0
0x1800607b0  lea     edi, [rax+1]
0x1800607b3  mov     byte ptr [rbp+2A0h+var_2B0], r14b
0x1800607b7  movzx   eax, word ptr [rsp+3A0h+var_370+5]
0x1800607bc  lea     r13d, [rdi+1]
0x1800607c0  xorps   xmm0, xmm0
0x1800607c3  mov     word ptr [rbp+2A0h+var_2E8+5], ax
0x1800607c7  mov     al, byte ptr [rsp+3A0h+var_370+7]
0x1800607cb  lea     esi, [rdi+9]
0x1800607ce  movups  [rbp+2A0h+var_2E0], xmm0
0x1800607d2  mov     byte ptr [rbp+2A0h+var_2E8+7], al
0x1800607d5  xor     eax, eax
0x1800607d7  movups  xmmword ptr [rbp+2A0h+var_2D0], xmm0
0x1800607db  mov     byte ptr [rbp+2A0h+var_2E0], r14b
0x1800607df  xor     edx, edx; Val
0x1800607e1  movups  [rbp+2A0h+var_2C0], xmm0
0x1800607e5  mov     byte ptr [rbp+2A0h+var_2E0+8], bl
0x1800607e8  lea     r8d, [rdi+5Fh]; Size
0x1800607ec  mov     byte ptr [rbp+2A0h+var_2D0], r14b
0x1800607f0  mov     dword ptr [rbp+2A0h+var_2E8], edi
0x1800607f3  mov     byte ptr [rbp+2A0h+var_2E8+4], dil
0x1800607f7  mov     [rbp+2A0h+var_2FC], r13d
0x1800607fb  movups  xmm6, xmmword ptr [r12]
0x180060800  mov     [rbp+2A0h+var_268], eax
0x180060803  movups  [rbp+2A0h+var_278], xmm0
0x180060807  mov     [rbp+2A0h+var_300], esi
0x18006080a  movups  [rbp+2A0h+var_2F8], xmm6
0x18006080e  mov     byte ptr [rbp+2A0h+var_278], r14b
0x180060812  mov     byte ptr [rbp+2A0h+var_268], r14b
0x180060816  mov     [rbp+2A0h+var_260], r14
0x18006081a  call    memset_0
0x18006081f  xor     edx, edx; Val
0x180060821  mov     byte ptr [rbp+2A0h+var_258], r14b
0x180060825  mov     r8d, 130h; Size
0x18006082b  mov     [rbp+2A0h+var_200], r14b
0x180060832  lea     rcx, [rbp+2A0h+var_1F8]; void *
0x180060839  call    memset_0
0x18006083e  xorps   xmm0, xmm0
0x180060841  mov     [rbp+2A0h+var_1F8], r14b
0x180060848  movups  [rbp+2A0h+var_A8], xmm0
0x18006084f  mov     [rbp+2A0h+var_D0], r14b
0x180060856  movups  [rbp+2A0h+var_A8+0Ch], xmm0
0x18006085d  mov     byte ptr [rbp+2A0h+var_A8], r14b
0x180060864  movups  [rbp+2A0h+var_C8], xmm0
0x18006086b  mov     byte ptr [rbp+2A0h+var_C8], r14b
0x180060872  movups  [rbp+2A0h+var_B8], xmm0
0x180060879  mov     byte ptr [rbp+2A0h+var_B8+0Ch], r14b
0x180060880  movups  [rbp+2A0h+var_88], xmm0
0x180060887  mov     [rbp+2A0h+var_90], r14b
0x18006088e  movups  [rbp+2A0h+var_68], xmm0
0x180060895  mov     byte ptr [rbp+2A0h+var_88], r14b
0x18006089c  movups  [rbp+2A0h+var_78], xmm0
0x1800608a3  mov     byte ptr [rbp+2A0h+var_68+8], r14b
0x1800608aa  movups  xmm0, xmmword ptr [rbp+2A0h+var_2A0.Data1]
0x1800608ae  mov     [rbp+2A0h+var_280], edi
0x1800608b1  mov     [rbp+2A0h+var_27C], edi
0x1800608b4  movdqu  [rbp+2A0h+var_290], xmm0
0x1800608b9  cmp     [rbp+2A0h+var_200], r14b
0x1800608c0  jz      short loc_180060904
0x1800608c2  mov     rax, [rbp+2A0h+var_2E8]
0x1800608c6  lea     rdx, [rbp+2A0h+var_2D0]
0x1800608ca  mov     [rbp+2A0h+var_240], rax
0x1800608ce  lea     rcx, [rbp+2A0h+var_228]
0x1800608d2  mov     rax, qword ptr [rbp+2A0h+var_2E0]
0x1800608d6  mov     [rbp+2A0h+var_238], rax
0x1800608da  mov     eax, dword ptr [rbp+2A0h+var_2E0+9]
0x1800608dd  mov     [rbp+2A0h+var_22F], eax
0x1800608e0  movzx   eax, word ptr [rbp+2A0h+var_2E0+0Dh]
0x1800608e4  mov     [rbp+2A0h+var_22B], ax
0x1800608e8  mov     al, byte ptr [rbp+2A0h+var_2E0+0Fh]
0x1800608eb  mov     [rbp+2A0h+var_229], al
0x1800608ee  mov     [rbp+2A0h+var_258], esi
0x1800608f1  mov     [rbp+2A0h+var_254], r13d
0x1800608f5  movdqu  [rbp+2A0h+var_250], xmm6
0x1800608fa  mov     [rbp+2A0h+var_230], bl
0x1800608fd  call    ??4?$optional@VPath@Csl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::optional<Csl::Path>::operator=(utl::optional<Csl::Path> &&)
0x180060902  jmp     short loc_180060918
0x180060904  lea     rdx, [rbp+2A0h+var_300]
0x180060908  lea     rcx, [rbp+2A0h+var_258]
0x18006090c  call    ??0ContainerStorageConfiguration@Details@Core@Manager@Container@@QEAA@$$QEAU01234@@Z; Container::Manager::Core::Details::ContainerStorageConfiguration::ContainerStorageConfiguration(Container::Manager::Core::Details::ContainerStorageConfiguration &&)
0x180060911  mov     [rbp+2A0h+var_200], dil
0x180060918  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006091f  mov     r13d, 58h ; 'X'
0x180060925  mov     rdx, rsi; struct std::nothrow_t *
0x180060928  mov     ecx, r13d; unsigned __int64
0x18006092b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180060930  mov     rdi, rax
0x180060933  test    rax, rax
0x180060936  jz      loc_180060E17
0x18006093c  lea     rdx, [rax+10h]
0x180060940  mov     [rax+28h], r14
0x180060944  mov     [rax], rdx
0x180060947  mov     rcx, rdi
0x18006094a  mov     [rax+8], rdx
0x18006094e  mov     [rdx], r14w
0x180060952  lea     rdx, [rsp+3A0h+var_358]
0x180060957  mov     [rax+20h], r14d
0x18006095b  mov     [rax+40h], r14
0x18006095f  mov     [rax+48h], r14
0x180060963  mov     [rax+50h], r14b
0x180060967  mov     [rax+30h], r14
0x18006096b  mov     [rax+38h], r14
0x18006096f  mov     [rsp+3A0h+var_370], rax
0x180060974  lea     rax, aResourcebroker_1; "ResourceBroker_RecreateLayerStorage_New"
0x18006097b  mov     [rsp+3A0h+var_358], rax
0x180060980  mov     qword ptr [rsp+3A0h+var_350], 27h ; '''
0x180060989  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18006098e  mov     ebx, eax
0x180060990  test    eax, eax
0x180060992  jns     short loc_1800609C7
0x180060994  mov     edx, 1000h; void *
0x180060999  mov     rcx, [rbp+2A8h]; this
0x1800609a0  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800609a7  mov     r9d, eax; char *
0x1800609aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800609af  mov     rcx, rdi; this
0x1800609b2  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800609b7  mov     rdx, r13; struct std::nothrow_t *
0x1800609ba  mov     rcx, rdi; void *
0x1800609bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800609c2  jmp     loc_180060E37
0x1800609c7  lea     r8, [rsp+3A0h+var_370]
0x1800609cc  mov     rcx, r15
0x1800609cf  lea     rdx, [rbp+2A0h+var_290]
0x1800609d3  call    ?CreateResource@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBUResourceConfiguration@2345@AEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ResourceBroker::CreateResource(Container::Manager::Core::Details::ResourceConfiguration const &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> &)
0x1800609d8  mov     ebx, eax
0x1800609da  test    eax, eax
0x1800609dc  jns     short loc_1800609E5
0x1800609de  mov     edx, 1002h
0x1800609e3  jmp     short loc_180060999
0x1800609e5  mov     rcx, rdi
0x1800609e8  call    ??$Get@VContainerStorage@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVContainerStorage@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(void)
0x1800609ed  mov     rdx, rsi; struct std::nothrow_t *
0x1800609f0  mov     [rsp+3A0h+var_370], rax
0x1800609f5  mov     rcx, r13; unsigned __int64
0x1800609f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800609fd  mov     rsi, rax
0x180060a00  test    rax, rax
0x180060a03  jz      loc_180060DF2
0x180060a09  lea     rdx, [rax+10h]
0x180060a0d  mov     [rax+28h], r14
0x180060a11  mov     [rax], rdx
0x180060a14  mov     rcx, rsi
0x180060a17  mov     [rax+8], rdx
0x180060a1b  mov     [rdx], r14w
0x180060a1f  lea     rdx, [rsp+3A0h+var_358]
0x180060a24  mov     [rax+20h], r14d
0x180060a28  mov     [rax+40h], r14
0x180060a2c  mov     [rax+48h], r14
0x180060a30  mov     [rax+50h], r14b
0x180060a34  mov     [rax+30h], r14
0x180060a38  mov     [rax+38h], r14
0x180060a3c  mov     [rsp+3A0h+var_368], rax
0x180060a41  lea     rax, aResourcebroker; "ResourceBroker_RecreateLayerStorage_Old"
0x180060a48  mov     [rsp+3A0h+var_358], rax
0x180060a4d  mov     qword ptr [rsp+3A0h+var_350], 27h ; '''
0x180060a56  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180060a5b  mov     ebx, eax
0x180060a5d  test    eax, eax
0x180060a5f  jns     short loc_180060AD2
0x180060a61  mov     rcx, [rbp+2A8h]; this
0x180060a68  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180060a6f  mov     r9d, eax; char *
0x180060a72  mov     edx, 100Ah; void *
0x180060a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060a7c  mov     rcx, rsi; this
0x180060a7f  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180060a84  mov     rdx, r13; struct std::nothrow_t *
0x180060a87  mov     rcx, rsi; void *
0x180060a8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060a8f  mov     rcx, rdi; this
0x180060a92  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180060a97  mov     rdx, r13; struct std::nothrow_t *
0x180060a9a  mov     rcx, rdi; void *
0x180060a9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060aa2  lea     rcx, [rbp+2A0h+var_290]; this
0x180060aa6  call    ??1ResourceConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration(void)
0x180060aab  cmp     byte ptr [rbp+2A0h+var_2B0], r14b
0x180060aaf  jz      loc_180060E5B
0x180060ab5  mov     rcx, [rbp+2A0h+var_2D0]
0x180060ab9  lea     rax, [rbp+2A0h+var_2C0]
0x180060abd  cmp     rcx, rax
0x180060ac0  jz      loc_180060E5B
0x180060ac6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180060acd  jmp     loc_180060E56
0x180060ad2  lea     r14, [r15+10h]
0x180060ad6  mov     rcx, r14; SRWLock
0x180060ad9  call    cs:__imp_AcquireSRWLockExclusive
0x180060ae0  nop     dword ptr [rax+rax+00h]
0x180060ae5  call    cs:__imp_GetCurrentThreadId
0x180060aec  nop     dword ptr [rax+rax+00h]
0x180060af1  lea     r13, [r12+110h]
0x180060af9  mov     [rsp+3A0h+SRWLock], r14
0x180060afe  mov     rcx, r13; SRWLock
0x180060b01  mov     [r14+8], eax
0x180060b05  call    cs:__imp_AcquireSRWLockShared
0x180060b0c  nop     dword ptr [rax+rax+00h]
0x180060b11  test    r13, r13
0x180060b14  jz      short loc_180060B25
0x180060b16  mov     rcx, r13; SRWLock
0x180060b19  call    cs:__imp_ReleaseSRWLockShared
0x180060b20  nop     dword ptr [rax+rax+00h]
0x180060b25  lea     rax, [r12+124h]
0x180060b2d  mov     r8d, 1
0x180060b33  mov     rdx, rax
0x180060b36  mov     [rsp+3A0h+var_358], rax
0x180060b3b  lea     r9, [rsp+3A0h+var_368]
0x180060b40  mov     rcx, r15
0x180060b43  call    ?OpenResourceLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@W4ResourceType@2345@AEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ResourceBroker::OpenResourceLocked(_GUID const &,Container::Manager::Core::Details::ResourceType,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> &)
0x180060b48  mov     ebx, eax
0x180060b4a  test    eax, eax
0x180060b4c  jns     short loc_180060BBC
0x180060b4e  mov     rcx, [rbp+2A8h]; this
0x180060b55  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180060b5c  mov     r9d, eax; char *
0x180060b5f  mov     edx, 1013h; void *
0x180060b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060b69  mov     rcx, r14; SRWLock
0x180060b6c  mov     dword ptr [r14+8], 0
0x180060b74  call    cs:__imp_ReleaseSRWLockExclusive
0x180060b7b  nop     dword ptr [rax+rax+00h]
0x180060b80  mov     rcx, rsi; this
0x180060b83  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180060b88  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x180060b8d  mov     rcx, rsi; void *
0x180060b90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060b95  mov     rcx, rdi; this
0x180060b98  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x180060b9d  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x180060ba2  mov     rcx, rdi; void *
0x180060ba5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060baa  lea     rcx, [rbp+2A0h+var_290]; this
0x180060bae  call    ??1ResourceConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceConfiguration::~ResourceConfiguration(void)
0x180060bb3  cmp     byte ptr [rbp+2A0h+var_2B0], 0
0x180060bb7  jmp     loc_180060AAF
0x180060bbc  test    byte ptr [r12+120h], 4
0x180060bc5  mov     rbx, [rsp+3A0h+var_370]
0x180060bca  jnz     short loc_180060BEF
0x180060bcc  mov     r8, [rsp+3A0h+var_340]; void *
0x180060bd1  xor     edx, edx; bool
0x180060bd3  mov     rcx, rbx; this
0x180060bd6  call    ?SetDeleteOnClose@ContainerStorage@Details@Core@Manager@Container@@AEAAJ_NPEAX@Z; Container::Manager::Core::Details::ContainerStorage::SetDeleteOnClose(bool,void *)
0x180060bdb  mov     r15d, eax
0x180060bde  test    eax, eax
0x180060be0  jns     short loc_180060BEF
0x180060be2  mov     edx, 101Ch
0x180060be7  xor     r12d, r12d
0x180060bea  jmp     loc_180060C73
0x180060bef  mov     r8, [rsp+3A0h+var_340]; void *
  ... truncated ...
```
