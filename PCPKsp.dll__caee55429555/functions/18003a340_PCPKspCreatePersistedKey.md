# PCPKspCreatePersistedKey

- ea: `0x18003a340`
- end: `0x18003a85f`
- name: `PCPKspCreatePersistedKey`
- size: `1311`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800133c4`
- `0x18001b860`
- `0x18001c308`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001edb0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f2f0`
- `0x18003a340`
- `0x18003a8b0`
- `0x18003ae74`
- `0x18003bcd8`
- `0x18003c1b4`
- `0x18003c5bc`
- `0x18004d528`
- `0x180058464`
- `0x1800764d0`
- `0x1800769bc`
- `0x18007704c`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a80e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a80e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a845`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a6ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a6ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a3b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a3b5`

## string_xrefs

- `0x18003a396`: `PCPKspCreatePersistedKey`
- `0x18003a644`: `PCPKspCreatePersistedKey`
- `0x18003a3c1`: `PCPKspCreatePersistedKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCPKspCreatePersistedKey(
        PCPStorageProvider *a1,
        PCPStorageProviderKey **a2,
        RTL_SRWLOCK *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int a6)
{
  int v10; // eax
  unsigned int v11; // ebx
  PCPStorageProviderKey *v12; // rax
  PCPStorageProviderKey *v13; // rax
  PCPStorageProviderKey *v14; // rbx
  const char *v15; // r9
  __int64 result; // rax
  int v17; // eax
  unsigned int v18; // edi
  int v19; // edi
  RTL_SRWLOCK *v20; // rbx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  const struct wil::FailureInfo *v24; // rdx
  unsigned int v25; // [rsp+20h] [rbp-298h]
  unsigned int v26; // [rsp+20h] [rbp-298h]
  int PersistedKey; // [rsp+30h] [rbp-288h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-280h] BYREF
  PCPStorageProvider *v29; // [rsp+40h] [rbp-278h] BYREF
  const unsigned __int16 *v30; // [rsp+48h] [rbp-270h] BYREF
  _QWORD v31[7]; // [rsp+50h] [rbp-268h] BYREF
  DWORD TickCount; // [rsp+88h] [rbp-230h]
  char v33; // [rsp+8Ch] [rbp-22Ch]
  _BYTE v34[160]; // [rsp+90h] [rbp-228h] BYREF
  _QWORD v35[34]; // [rsp+130h] [rbp-188h] BYREF
  __int64 v36; // [rsp+240h] [rbp-78h]
  unsigned __int64 v37; // [rsp+248h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  SRWLock = a3;
  v30 = a4;
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v35);
  v35[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  try
  {
    KspDebugProvider::KspDebugActivity::StartActivity(
      (KspDebugProvider::KspDebugActivity *)v35,
      "PCPKspCreatePersistedKey");
    PersistedKey = 0;
    v29 = a1;
    v31[0] = L"PCPKspCreatePersistedKey";
    v31[1] = &v29;
    v31[2] = a2;
    v31[3] = 0;
    v31[4] = &PersistedKey;
    v31[5] = &a6;
    v31[6] = a4;
    TickCount = GetTickCount();
    v33 = 2;
    if ( !a1 )
    {
      PersistedKey = -2146893786;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090026LL,
        v25);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
      return 2148073510LL;
    }
    if ( a2 && a3 && LOWORD(a3->Ptr) )
    {
      if ( !a4 )
      {
        KspDebugProvider::CreatePersistedKey<unsigned short const * &,unsigned long &>(&SRWLock, &a6);
        goto LABEL_8;
      }
      if ( wcscmp_0(a4, L"MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF-004E-4E2F-8A4D-0BF633DCB074") )
      {
        KspDebugProvider::CreatePersistedKeyNamed<unsigned short const * &,unsigned short const * &,unsigned long &>(
          &v30,
          &SRWLock,
          &a6);
LABEL_8:
        *a2 = 0;
        if ( a5 )
        {
          PersistedKey = -2146893783;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AF,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090029LL,
            v25);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
          return 2148073513LL;
        }
        else if ( (a6 & 0xFFFFFF1F) != 0 )
        {
          PersistedKey = -2146893815;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B4,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090009LL,
            v25);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
          return 2148073481LL;
        }
        else
        {
          v10 = PCPStorageProvider::ValidateObject(v29);
          v11 = v10;
          PersistedKey = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2B7,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v10,
              v25);
            KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
            KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
            return v11;
          }
          else
          {
            v12 = (PCPStorageProviderKey *)operator new(0x318u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v12
              && (v13 = PCPStorageProviderKey::PCPStorageProviderKey(v12), v14 = v13, (SRWLock = (PSRWLOCK)v13) != 0) )
            {
              *((_QWORD *)v13 + 6) = v29;
              PersistedKey = PCPStorageProviderKey::CreatePersistedKey(v13, (wchar_t *)a3, a4, 0, a6);
              v17 = SecurityStatusFromHResult(PersistedKey);
              v18 = v17;
              PersistedKey = v17;
              if ( v17 < 0 )
              {
                if ( v17 == -2146893809 )
                {
                  wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(
                    (__int64 *)&SRWLock,
                    0);
                  KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
                  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
                  return 2148073487LL;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2C3,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                    (const char *)(unsigned int)v17,
                    v26);
                  wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(
                    (__int64 *)&SRWLock,
                    0);
                  KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
                  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
                  return v18;
                }
              }
              else
              {
                *((_BYTE *)v14 + 736) |= *((_BYTE *)v29 + 92) | ((a6 & 0x40) != 0);
                *a2 = v14;
                KspDebugProvider::KeyHandle<unsigned __int64 &>(a2);
                v19 = PersistedKey;
                if ( v37 )
                {
                  v20 = (RTL_SRWLOCK *)(((v37 + 8) & ((unsigned __int128)-(__int128)v37 >> 64)) + 256);
                  AcquireSRWLockExclusive(v20);
                  v30 = 0;
                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
                }
                else
                {
                  SRWLock = 0;
                  v20 = 0;
                }
                v21 = v36;
                v22 = *(_DWORD *)(v36 + 248);
                if ( v22 < 1 )
                {
                  memset_0(v34, 0, 0x98u);
                  wil::details::WilFailFast((wil::details *)v34, v24);
                }
                if ( *(int *)(v36 + 72) >= 0 )
                  *(_DWORD *)(v36 + 72) = v19;
                *(_DWORD *)(v21 + 248) = v22 - 1;
                if ( v20 )
                  ReleaseSRWLockExclusive(v20);
                KspDebugProvider::KspDebugActivity::Stop(
                  (KspDebugProvider::KspDebugActivity *)v35,
                  "PCPKspCreatePersistedKey");
                v23 = PersistedKey;
                KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
                KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
                return v23;
              }
            }
            else
            {
              KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
              KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
              return 2147942408LL;
            }
          }
        }
      }
    }
    PersistedKey = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090027LL,
      v25);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v31);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v35);
    result = 2148073511LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2CF,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18003a340  push    rbx
0x18003a342  push    rsi
0x18003a343  push    rdi
0x18003a344  push    r14
0x18003a346  push    r15
0x18003a348  sub     rsp, 290h
0x18003a34f  mov     rax, cs:__security_cookie
0x18003a356  xor     rax, rsp
0x18003a359  mov     [rsp+2B8h+var_38], rax
0x18003a361  mov     rdi, r9
0x18003a364  mov     r14, r8
0x18003a367  mov     rsi, rdx
0x18003a36a  mov     rbx, rcx
0x18003a36d  mov     [rsp+2B8h+SRWLock], r8
0x18003a372  mov     [rsp+2B8h+var_270], r9
0x18003a377  xor     r15d, r15d
0x18003a37a  lea     rcx, [rsp+2B8h+var_188]
0x18003a382  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003a387  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x18003a38e  mov     [rsp+2B8h+var_188], rax
0x18003a396  lea     rdx, aPcpkspcreatepe_0; "PCPKspCreatePersistedKey"
0x18003a39d  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a3a5  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x18003a3aa  nop
0x18003a3ab  mov     [rsp+2B8h+var_288], r15d
0x18003a3b0  mov     [rsp+2B8h+var_278], rbx
0x18003a3b5  call    cs:__imp_GetTickCount
0x18003a3bc  nop     dword ptr [rax+rax+00h]
0x18003a3c1  lea     rcx, aPcpkspcreatepe; "PCPKspCreatePersistedKey"
0x18003a3c8  mov     [rsp+2B8h+var_268], rcx
0x18003a3cd  lea     rcx, [rsp+2B8h+var_278]
0x18003a3d2  mov     [rsp+2B8h+var_260], rcx
0x18003a3d7  mov     [rsp+2B8h+var_258], rsi
0x18003a3dc  mov     [rsp+2B8h+var_250], r15
0x18003a3e1  lea     rcx, [rsp+2B8h+var_288]
0x18003a3e6  mov     [rsp+2B8h+var_248], rcx
0x18003a3eb  lea     rcx, [rsp+2B8h+arg_28]
0x18003a3f3  mov     [rsp+2B8h+var_240], rcx
0x18003a3f8  mov     [rsp+2B8h+var_238], rdi
0x18003a400  mov     [rsp+2B8h+var_230], eax
0x18003a407  mov     [rsp+2B8h+var_22C], 2
0x18003a40f  test    rbx, rbx
0x18003a412  jz      loc_18003A695
0x18003a418  test    rsi, rsi
0x18003a41b  jz      loc_18003A53E
0x18003a421  test    r14, r14
0x18003a424  jz      loc_18003A53E
0x18003a42a  cmp     [r14], r15w
0x18003a42e  jz      loc_18003A53E
0x18003a434  test    rdi, rdi
0x18003a437  jnz     loc_18003A50F
0x18003a43d  lea     rdx, [rsp+2B8h+arg_28]
0x18003a445  lea     rcx, [rsp+2B8h+SRWLock]
0x18003a44a  call    ??$CreatePersistedKey@AEAPEBGAEAK@KspDebugProvider@@SAXAEAPEBGAEAK@Z; KspDebugProvider::CreatePersistedKey<ushort const * &,ulong &>(ushort const * &,ulong &)
0x18003a44f  mov     [rsi], r15
0x18003a452  cmp     [rsp+2B8h+arg_20], r15d
0x18003a45a  jnz     loc_18003A70F
0x18003a460  test    [rsp+2B8h+arg_28], 0FFFFFF1Fh
0x18003a46b  jnz     loc_18003A752
0x18003a471  mov     rcx, [rsp+2B8h+var_278]; this
0x18003a476  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x18003a47b  mov     ebx, eax
0x18003a47d  mov     [rsp+2B8h+var_288], eax
0x18003a481  test    eax, eax
0x18003a483  js      short loc_18003A4D5
0x18003a485  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a48c  mov     ecx, 318h; unsigned __int64
0x18003a491  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a496  test    rax, rax
0x18003a499  jz      short loc_18003A4B4
0x18003a49b  mov     rcx, rax; this
0x18003a49e  call    ??0PCPStorageProviderKey@@QEAA@XZ; PCPStorageProviderKey::PCPStorageProviderKey(void)
0x18003a4a3  mov     rbx, rax
0x18003a4a6  mov     [rsp+2B8h+SRWLock], rax
0x18003a4ab  test    rax, rax
0x18003a4ae  jnz     loc_18003A581
0x18003a4b4  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a4b9  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a4be  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a4c6  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a4cb  mov     eax, 80070008h
0x18003a4d0  jmp     loc_18003A675
0x18003a4d5  mov     rcx, [rsp+2B8h]; this
0x18003a4dd  mov     r9d, ebx; char *
0x18003a4e0  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a4e7  mov     edx, 2B7h; void *
0x18003a4ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a4f1  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a4f6  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a4fb  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a503  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a508  mov     eax, ebx
0x18003a50a  jmp     loc_18003A675
0x18003a50f  lea     rdx, aMicrosoftPcpKs; "MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF"...
0x18003a516  mov     rcx, rdi; String1
0x18003a519  call    wcscmp_0
0x18003a51e  test    eax, eax
0x18003a520  jz      short loc_18003A53E
0x18003a522  lea     r8, [rsp+2B8h+arg_28]
0x18003a52a  lea     rdx, [rsp+2B8h+SRWLock]
0x18003a52f  lea     rcx, [rsp+2B8h+var_270]
0x18003a534  call    ??$CreatePersistedKeyNamed@AEAPEBGAEAPEBGAEAK@KspDebugProvider@@SAXAEAPEBG0AEAK@Z; KspDebugProvider::CreatePersistedKeyNamed<ushort const * &,ushort const * &,ulong &>(ushort const * &,ushort const * &,ulong &)
0x18003a539  jmp     loc_18003A44F
0x18003a53e  mov     ebx, 80090027h
0x18003a543  mov     [rsp+2B8h+var_288], ebx
0x18003a547  mov     rcx, [rsp+2B8h]; this
0x18003a54f  mov     r9d, ebx; char *
0x18003a552  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a559  mov     edx, 2A1h; void *
0x18003a55e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a563  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a568  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a56d  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a575  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a57a  mov     eax, ebx
0x18003a57c  jmp     loc_18003A675
0x18003a581  mov     rcx, [rsp+2B8h+var_278]
0x18003a586  mov     [rax+30h], rcx
0x18003a58a  mov     ecx, [rsp+2B8h+arg_28]
0x18003a591  mov     [rsp+2B8h+var_298], ecx; int
0x18003a595  xor     r9d, r9d; unsigned int
0x18003a598  mov     r8, rdi; unsigned __int16 *
0x18003a59b  mov     rdx, r14; String1
0x18003a59e  mov     rcx, rbx; this
0x18003a5a1  call    ?CreatePersistedKey@PCPStorageProviderKey@@QEAAJPEBG0KK@Z; PCPStorageProviderKey::CreatePersistedKey(ushort const *,ushort const *,ulong,ulong)
0x18003a5a6  mov     [rsp+2B8h+var_288], eax
0x18003a5aa  mov     ecx, eax; int
0x18003a5ac  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18003a5b1  mov     edi, eax
0x18003a5b3  mov     [rsp+2B8h+var_288], eax
0x18003a5b7  test    eax, eax
0x18003a5b9  js      loc_18003A795
0x18003a5bf  mov     edx, [rsp+2B8h+arg_28]
0x18003a5c6  shr     edx, 6
0x18003a5c9  and     dl, 1
0x18003a5cc  mov     rax, [rsp+2B8h+var_278]
0x18003a5d1  or      dl, [rax+5Ch]
0x18003a5d4  or      [rbx+2E0h], dl
0x18003a5da  mov     [rsi], rbx
0x18003a5dd  mov     rcx, rsi
0x18003a5e0  call    ??$KeyHandle@AEA_K@KspDebugProvider@@SAXAEA_K@Z; KspDebugProvider::KeyHandle<unsigned __int64 &>(unsigned __int64 &)
0x18003a5e5  mov     edi, [rsp+2B8h+var_288]
0x18003a5e9  mov     rcx, [rsp+2B8h+var_70]
0x18003a5f1  test    rcx, rcx
0x18003a5f4  jnz     loc_18003A6D5
0x18003a5fa  lea     rax, [rsp+2B8h+SRWLock]
0x18003a5ff  mov     [rax], r15
0x18003a602  mov     rcx, [rsp+2B8h+SRWLock]; SRWLock
0x18003a607  test    rcx, rcx
0x18003a60a  jnz     loc_18003A80E
0x18003a610  mov     rbx, r15
0x18003a613  mov     rcx, [rsp+2B8h+var_78]
0x18003a61b  mov     eax, [rcx+0F8h]
0x18003a621  cmp     eax, 1
0x18003a624  jl      loc_18003A81F
0x18003a62a  cmp     [rcx+48h], r15d
0x18003a62e  jl      short loc_18003A633
0x18003a630  mov     [rcx+48h], edi
0x18003a633  dec     eax
0x18003a635  mov     [rcx+0F8h], eax
0x18003a63b  test    rbx, rbx
0x18003a63e  jnz     loc_18003A842
0x18003a644  lea     rdx, aPcpkspcreatepe_0; "PCPKspCreatePersistedKey"
0x18003a64b  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a653  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x18003a658  mov     ebx, [rsp+2B8h+var_288]
0x18003a65c  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a661  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a666  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a66e  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a673  mov     eax, ebx
0x18003a675  mov     rcx, [rsp+2B8h+var_38]
0x18003a67d  xor     rcx, rsp; StackCookie
0x18003a680  call    __security_check_cookie
0x18003a685  add     rsp, 290h
0x18003a68c  pop     r15
0x18003a68e  pop     r14
0x18003a690  pop     rdi
0x18003a691  pop     rsi
0x18003a692  pop     rbx
0x18003a693  retn
0x18003a695  mov     ebx, 80090026h
0x18003a69a  mov     [rsp+2B8h+var_288], ebx
0x18003a69e  mov     rcx, [rsp+2B8h]; this
0x18003a6a6  mov     r9d, ebx; char *
0x18003a6a9  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a6b0  mov     edx, 29Bh; void *
0x18003a6b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a6ba  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a6bf  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a6c4  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a6cc  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a6d1  mov     eax, ebx
0x18003a6d3  jmp     short loc_18003A675
0x18003a6d5  lea     rax, [rcx+8]
0x18003a6d9  neg     rcx
0x18003a6dc  sbb     rbx, rbx
0x18003a6df  and     rbx, rax
0x18003a6e2  add     rbx, 100h
0x18003a6e9  mov     rcx, rbx; SRWLock
0x18003a6ec  call    cs:__imp_AcquireSRWLockExclusive
0x18003a6f3  nop     dword ptr [rax+rax+00h]
0x18003a6f8  lea     rax, [rsp+2B8h+var_270]
0x18003a6fd  mov     [rax], r15
0x18003a700  lea     rcx, [rsp+2B8h+var_270]
0x18003a705  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003a70a  jmp     loc_18003A613
0x18003a70f  mov     ebx, 80090029h
0x18003a714  mov     [rsp+2B8h+var_288], ebx
0x18003a718  mov     rcx, [rsp+2B8h]; this
0x18003a720  mov     r9d, ebx; char *
0x18003a723  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a72a  mov     edx, 2AFh; void *
0x18003a72f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a734  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a739  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a73e  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a746  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a74b  mov     eax, ebx
0x18003a74d  jmp     loc_18003A675
0x18003a752  mov     ebx, 80090009h
0x18003a757  mov     [rsp+2B8h+var_288], ebx
0x18003a75b  mov     rcx, [rsp+2B8h]; this
0x18003a763  mov     r9d, ebx; char *
0x18003a766  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a76d  mov     edx, 2B4h; void *
0x18003a772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a777  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a77c  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a781  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a789  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a78e  mov     eax, ebx
0x18003a790  jmp     loc_18003A675
0x18003a795  mov     ebx, 8009000Fh
0x18003a79a  cmp     edi, ebx
0x18003a79c  jnz     short loc_18003A7C8
0x18003a79e  xor     edx, edx
0x18003a7a0  lea     rcx, [rsp+2B8h+SRWLock]
0x18003a7a5  call    ?reset@?$unique_ptr@VPCPStorageProviderKey@@U?$default_delete@VPCPStorageProviderKey@@@wistd@@@wistd@@QEAAXPEAVPCPStorageProviderKey@@@Z; wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(PCPStorageProviderKey *)
0x18003a7aa  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a7af  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a7b4  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a7bc  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a7c1  mov     eax, ebx
0x18003a7c3  jmp     loc_18003A675
0x18003a7c8  mov     rcx, [rsp+2B8h]; this
0x18003a7d0  mov     r9d, edi; char *
0x18003a7d3  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003a7da  mov     edx, 2C3h; void *
0x18003a7df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a7e4  xor     edx, edx
0x18003a7e6  lea     rcx, [rsp+2B8h+SRWLock]
0x18003a7eb  call    ?reset@?$unique_ptr@VPCPStorageProviderKey@@U?$default_delete@VPCPStorageProviderKey@@@wistd@@@wistd@@QEAAXPEAVPCPStorageProviderKey@@@Z; wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(PCPStorageProviderKey *)
0x18003a7f0  lea     rcx, [rsp+2B8h+var_268]; this
0x18003a7f5  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18003a7fa  lea     rcx, [rsp+2B8h+var_188]; this
0x18003a802  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18003a807  mov     eax, edi
0x18003a809  jmp     loc_18003A675
0x18003a80e  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a815  nop     dword ptr [rax+rax+00h]
0x18003a81a  jmp     loc_18003A610
0x18003a81f  xor     edx, edx; Val
0x18003a821  mov     r8d, 98h; Size
0x18003a827  lea     rcx, [rsp+2B8h+var_228]; void *
0x18003a82f  call    memset_0
0x18003a834  lea     rcx, [rsp+2B8h+var_228]; this
0x18003a83c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003a842  mov     rcx, rbx; SRWLock
0x18003a845  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a84c  nop     dword ptr [rax+rax+00h]
0x18003a851  jmp     loc_18003A644
0x18003a856  mov     eax, [rsp+2B8h+var_288]
0x18003a85a  jmp     loc_18003A675
```
