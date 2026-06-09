# PCPKspCreateClaim

- ea: `0x180050bb0`
- end: `0x180051612`
- name: `PCPKspCreateClaim`
- size: `2658`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, rsize_t, __int64, int)`
- caller_count: `0`
- callee_count: `19`
- tags: ``

## callees

- `0x1800113f0`
- `0x1800133c4`
- `0x18001b298`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001edb0`
- `0x18001f0f0`
- `0x18001f190`
- `0x18001f1cc`
- `0x18001f294`
- `0x18001f2c0`
- `0x180023894`
- `0x1800388a0`
- `0x180050bb0`
- `0x180051618`
- `0x180061b6c`
- `0x1800764d0`
- `0x180098970`
- `0x180099348`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180050c69`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180050c69`

## string_xrefs

- `0x180050c3a`: `PCPKspCreateClaim`
- `0x180051551`: `PCPKspCreateClaim`
- `0x180050c75`: `PCPKspCreateClaim`
- `0x180050f47`: `Buffer:PLATFORM_CLAIM_STATIC_CREATE wrong argument`
- `0x180050f14`: `Buffer:PLATFORM_CLAIM_CREATE_STATIC`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PCPKspCreateClaim(
        PCPStorageProvider *a1,
        PCPStorageProviderKey *a2,
        PCPStorageProviderKey *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int8 *a6,
        rsize_t a7,
        unsigned int *a8,
        int a9)
{
  _DWORD *v13; // rsi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int8 *v17; // r15
  __int64 v18; // rsi
  int v19; // ebx
  const char *v20; // rcx
  char v21; // di
  int v22; // eax
  unsigned int v23; // ebx
  char v24; // si
  unsigned __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  int PlatformClaim; // eax
  int ClaimWebAuthOnly; // eax
  int ClaimAuthorityAndSubject; // eax
  int ClaimSubjectOnly; // eax
  int ClaimAuthorityOnly; // eax
  rsize_t v33; // [rsp+20h] [rbp-278h]
  int v34; // [rsp+20h] [rbp-278h]
  int v35; // [rsp+20h] [rbp-278h]
  int v36; // [rsp+20h] [rbp-278h]
  int v37; // [rsp+20h] [rbp-278h]
  int v38; // [rsp+20h] [rbp-278h]
  const char *Destination; // [rsp+28h] [rbp-270h]
  rsize_t DestinationSize; // [rsp+30h] [rbp-268h]
  int v41; // [rsp+50h] [rbp-248h] BYREF
  PCPStorageProviderKey *v42; // [rsp+58h] [rbp-240h] BYREF
  PCPStorageProviderKey *v43; // [rsp+60h] [rbp-238h] BYREF
  rsize_t v44; // [rsp+68h] [rbp-230h]
  unsigned int v45; // [rsp+70h] [rbp-228h]
  int v46; // [rsp+74h] [rbp-224h]
  int v47; // [rsp+78h] [rbp-220h]
  int v48; // [rsp+7Ch] [rbp-21Ch]
  _QWORD v49[7]; // [rsp+80h] [rbp-218h] BYREF
  DWORD TickCount; // [rsp+B8h] [rbp-1E0h]
  char v51; // [rsp+BCh] [rbp-1DCh]
  PCPStorageProvider *v52; // [rsp+C0h] [rbp-1D8h] BYREF
  unsigned __int8 *v53; // [rsp+C8h] [rbp-1D0h]
  int v54[2]; // [rsp+D0h] [rbp-1C8h]
  int v55[2]; // [rsp+D8h] [rbp-1C0h]
  __int64 v56; // [rsp+E0h] [rbp-1B8h]
  _DWORD *v57; // [rsp+E8h] [rbp-1B0h]
  PCPStorageProviderKey *v58; // [rsp+F0h] [rbp-1A8h]
  int v59[2]; // [rsp+F8h] [rbp-1A0h]
  _QWORD v60[42]; // [rsp+100h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v45 = a4;
  *(_QWORD *)v54 = a3;
  v58 = a2;
  *(_QWORD *)v59 = a1;
  v13 = a5;
  v57 = a5;
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v60);
  v60[0] = &KspDebugProvider::KspDebugActivity::`vftable';
  KspDebugProvider::KspDebugActivity::StartActivity((KspDebugProvider::KspDebugActivity *)v60, "PCPKspCreateClaim");
  v41 = 0;
  v52 = a1;
  v42 = a2;
  v43 = a3;
  v49[0] = L"PCPKspCreateClaim";
  v49[1] = &v52;
  v49[2] = &v42;
  v49[3] = &v43;
  v49[4] = &v41;
  v49[5] = &a9;
  v49[6] = 0;
  TickCount = GetTickCount();
  v51 = 0;
  if ( !a1 )
  {
    v41 = -2146893786;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A7,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      v33);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
    return 2148073510LL;
  }
  v15 = PCPStorageProvider::ValidateObject(v52);
  v16 = v15;
  v41 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9AA,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v15,
      v33);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
    return v16;
  }
  if ( !a4
    || a6 && !(_DWORD)a7
    || !a8
    || a9
    || a2 == (PCPStorageProviderKey *)4294967281LL
    || a3 == (PCPStorageProviderKey *)4294967281LL )
  {
    v41 = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B2,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090027LL,
      v33);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
    return 2148073511LL;
  }
  v56 = 0;
  v48 = 0;
  v17 = 0;
  v53 = 0;
  v44 = 0;
  v47 = 0;
  *(_QWORD *)v55 = 0;
  v46 = 0;
  if ( a5 )
  {
    if ( *a5 )
    {
      v41 = -2146893785;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B8,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090027LL,
        v33);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
      return 2148073511LL;
    }
    while ( (unsigned int)v17 < v13[1] )
    {
      v18 = *((_QWORD *)v13 + 1);
      switch ( *(_DWORD *)(v18 + 16LL * (unsigned int)v17 + 4) )
      {
        case '0':
          KspDebugProvider::TraceLoggingInfo("Buffer:CLAIM_IDBINDING_NONCE", 0);
          v48 = *(_DWORD *)(v18 + 16LL * (unsigned int)v17);
          v56 = *(_QWORD *)(v18 + 16LL * (unsigned int)v17 + 8);
          break;
        case '1':
          KspDebugProvider::TraceLoggingInfo("Buffer:CLAIM_KEYATTESTATION_NONCE", 0);
          LODWORD(v44) = *(_DWORD *)(v18 + 16LL * (unsigned int)v17);
          v53 = *(unsigned __int8 **)(v18 + 16LL * (unsigned int)v17 + 8);
          break;
        case 'P':
          if ( *(_DWORD *)(v18 + 16LL * (unsigned int)v17) != 4 )
          {
            v41 = -2146893785;
            LODWORD(Destination) = *(_DWORD *)(v18 + 16LL * (unsigned int)v17);
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x9D5,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)0x80090027LL,
              (int)"Buffer:PLATFORM_CLAIM_PCR_MASK cb == %lu, should be %lu",
              Destination,
              4);
            KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
            KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
            return 2148073511LL;
          }
          KspDebugProvider::TraceLoggingInfo("Buffer:PLATFORM_CLAIM_PCR_MASK", 0);
          v47 = **(_DWORD **)(v18 + 16LL * (unsigned int)v17 + 8);
          break;
        case 'Q':
          KspDebugProvider::TraceLoggingInfo("Buffer:PLATFORM_CLAIM_NONCE", 0);
          v46 = *(_DWORD *)(v18 + 16LL * (unsigned int)v17);
          *(_QWORD *)v55 = *(_QWORD *)(v18 + 16LL * (unsigned int)v17 + 8);
          break;
        case 'R':
          if ( *(_DWORD *)(v18 + 16LL * (unsigned int)v17) == 4 )
          {
            v19 = **(_DWORD **)(v18 + 16LL * (unsigned int)v17 + 8);
          }
          else
          {
            if ( *(_DWORD *)(v18 + 16LL * (unsigned int)v17) != 1 )
            {
              v41 = -2146893785;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x9EF,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                (const char *)0x80090027LL,
                (int)"Buffer:PLATFORM_CLAIM_STATIC_CREATE wrong argument",
                Destination);
              KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
              KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
              return 2148073511LL;
            }
            v19 = **(unsigned __int8 **)(v18 + 16LL * (unsigned int)v17 + 8);
          }
          v20 = "Buffer:PLATFORM_CLAIM_CREATE_STATIC";
          if ( !v19 )
            v20 = "Buffer:PLATFORM_CLAIM_USE_STATIC";
          KspDebugProvider::TraceLoggingInfo(v20, 0);
          HIDWORD(v44) |= 2 - (v19 != 0);
          break;
        default:
          v41 = -2146893785;
          LODWORD(Destination) = *(_DWORD *)(v18 + 16LL * (unsigned int)v17 + 4);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xA00,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090027LL,
            (int)"Buffer:unknown type: %lu",
            Destination);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
          return 2148073511LL;
      }
      LODWORD(v17) = (_DWORD)v17 + 1;
      v13 = v57;
    }
    v17 = v53;
  }
  v21 = 0;
  if ( v58 )
  {
    v22 = PCPStorageProviderKey::ValidateObject(v42);
    v23 = v22;
    v41 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA09,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v22,
        v33);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
      return v23;
    }
    PCPStorageProviderKey::LockProvider(v42);
    v21 = 1;
  }
  v24 = 0;
  v25 = *(_QWORD *)v54;
  if ( *(_QWORD *)v54 )
  {
    v26 = PCPStorageProviderKey::ValidateObject(v43);
    v27 = v26;
    v41 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA17,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v26,
        v33);
      if ( v21 )
        PCPStorageProviderKey::UnLockProvider(v42);
LABEL_93:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
      return v27;
    }
    PCPStorageProviderKey::LockProvider(v43);
    v24 = 1;
    v25 = *(_QWORD *)v54;
  }
  switch ( v45 )
  {
    case 1u:
      ClaimAuthorityOnly = TpmCreateClaimAuthorityOnly(v25, *((_QWORD *)v42 + 96), (_DWORD)a6, a7, (__int64)a8);
      v27 = ClaimAuthorityOnly;
      v41 = ClaimAuthorityOnly;
      if ( ClaimAuthorityOnly < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA71,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)ClaimAuthorityOnly,
          v38);
        if ( v24 )
          PCPStorageProviderKey::UnLockProvider(v43);
        if ( v21 )
          PCPStorageProviderKey::UnLockProvider(v42);
        goto LABEL_93;
      }
      goto LABEL_89;
    case 2u:
      LODWORD(v33) = v44;
      ClaimSubjectOnly = TpmCreateClaimSubjectOnly(
                           *(_QWORD *)(*((_QWORD *)v42 + 6) + 136LL),
                           *((_QWORD *)v43 + 96),
                           *((_QWORD *)v42 + 96),
                           (int)v17,
                           v33,
                           (__int64)a6,
                           a7,
                           (__int64)a8,
                           2);
      v27 = ClaimSubjectOnly;
      v41 = ClaimSubjectOnly;
      if ( ClaimSubjectOnly < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA7,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)ClaimSubjectOnly,
          v37);
        if ( v24 )
          PCPStorageProviderKey::UnLockProvider(v43);
        if ( v21 )
          PCPStorageProviderKey::UnLockProvider(v42);
        goto LABEL_93;
      }
      goto LABEL_89;
    case 3u:
      LODWORD(Destination) = v44;
      ClaimAuthorityAndSubject = TpmCreateClaimAuthorityAndSubject(
                                   *(void **)(*((_QWORD *)v42 + 6) + 136LL),
                                   *((TpmObject **)v42 + 96),
                                   (__int64)v17,
                                   (rsize_t)Destination,
                                   (__int64)a6,
                                   a7,
                                   (__int64)a8);
      v27 = ClaimAuthorityAndSubject;
      v41 = ClaimAuthorityAndSubject;
      if ( ClaimAuthorityAndSubject < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA52,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)ClaimAuthorityAndSubject,
          v36);
        if ( v24 )
          PCPStorageProviderKey::UnLockProvider(v43);
        if ( v21 )
          PCPStorageProviderKey::UnLockProvider(v42);
        goto LABEL_93;
      }
      goto LABEL_89;
    case 0x102u:
    case 0x103u:
      ClaimWebAuthOnly = TpmCreateClaimWebAuthOnly(
                           *(void **)(*((_QWORD *)v42 + 6) + 136LL),
                           *((void **)v43 + 96),
                           *((void **)v42 + 96),
                           v17,
                           v44,
                           a6,
                           a7,
                           a8,
                           v45);
      v27 = ClaimWebAuthOnly;
      v41 = ClaimWebAuthOnly;
      if ( ClaimWebAuthOnly < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xACD,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)ClaimWebAuthOnly,
          v35);
        if ( v24 )
          PCPStorageProviderKey::UnLockProvider(v43);
        if ( v21 )
          PCPStorageProviderKey::UnLockProvider(v42);
        goto LABEL_93;
      }
      goto LABEL_89;
    case 0x10000u:
      LODWORD(DestinationSize) = a7;
      PlatformClaim = TpmCreatePlatformClaim(
                        *(unsigned __int64 *)v59,
                        v25,
                        v47,
                        *(unsigned __int8 **)v55,
                        v46,
                        (unsigned int *)a6,
                        DestinationSize,
                        a8,
                        SHIDWORD(v44));
      v27 = PlatformClaim;
      v41 = PlatformClaim;
      if ( PlatformClaim < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD9,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)PlatformClaim,
          v34);
        if ( v24 )
          PCPStorageProviderKey::UnLockProvider(v43);
        if ( v21 )
          PCPStorageProviderKey::UnLockProvider(v42);
        goto LABEL_93;
      }
LABEL_89:
      KspDebugProvider::KspDebugActivity::StopWithResult<char const (&)[21]>((KspDebugProvider::KspDebugActivity *)v60);
      v27 = v41;
      if ( v24 )
        PCPStorageProviderKey::UnLockProvider(v43);
      if ( v21 )
        PCPStorageProviderKey::UnLockProvider(v42);
      goto LABEL_93;
  }
  v41 = -2146893785;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xADD,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
    (const char *)0x80090027LL,
    v33);
  if ( v24 )
    PCPStorageProviderKey::UnLockProvider(v43);
  if ( v21 )
    PCPStorageProviderKey::UnLockProvider(v42);
  KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v49);
  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v60);
  return 2148073511LL;
}

```

## disassembly

```asm
0x180050bb0  push    rbx
0x180050bb2  push    rsi
0x180050bb3  push    rdi
0x180050bb4  push    r12
0x180050bb6  push    r13
0x180050bb8  push    r14
0x180050bba  push    r15
0x180050bbc  sub     rsp, 260h
0x180050bc3  mov     rax, cs:__security_cookie
0x180050bca  xor     rax, rsp
0x180050bcd  mov     [rsp+298h+var_48], rax
0x180050bd5  mov     r14d, r9d
0x180050bd8  mov     [rsp+298h+var_228], r9d
0x180050bdd  mov     r15, r8
0x180050be0  mov     qword ptr [rsp+298h+var_1C8], r8
0x180050be8  mov     rdi, rdx
0x180050beb  mov     [rsp+298h+var_1A8], rdx
0x180050bf3  mov     rbx, rcx
0x180050bf6  mov     qword ptr [rsp+298h+var_1A0], rcx
0x180050bfe  mov     rsi, [rsp+298h+arg_20]
0x180050c06  mov     [rsp+298h+var_1B0], rsi
0x180050c0e  mov     r12, [rsp+298h+arg_28]
0x180050c16  mov     r13, [rsp+298h+arg_38]
0x180050c1e  lea     rcx, [rsp+298h+var_198]
0x180050c26  call    ??0?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180050c2b  lea     rax, ??_7KspDebugActivity@KspDebugProvider@@6B@; const KspDebugProvider::KspDebugActivity::`vftable'
0x180050c32  mov     [rsp+298h+var_198], rax
0x180050c3a  lea     rdx, aPcpkspcreatecl; "PCPKspCreateClaim"
0x180050c41  lea     rcx, [rsp+298h+var_198]; this
0x180050c49  call    ?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::StartActivity(char const *)
0x180050c4e  nop
0x180050c4f  mov     [rsp+298h+var_248], 0
0x180050c57  mov     [rsp+298h+var_1D8], rbx
0x180050c5f  mov     [rsp+298h+var_240], rdi
0x180050c64  mov     [rsp+298h+var_238], r15
0x180050c69  call    cs:__imp_GetTickCount
0x180050c70  nop     dword ptr [rax+rax+00h]
0x180050c75  lea     rcx, aPcpkspcreatecl_0; "PCPKspCreateClaim"
0x180050c7c  mov     [rsp+298h+var_218], rcx
0x180050c84  lea     rcx, [rsp+298h+var_1D8]
0x180050c8c  mov     [rsp+298h+var_210], rcx
0x180050c94  lea     rcx, [rsp+298h+var_240]
0x180050c99  mov     [rsp+298h+var_208], rcx
0x180050ca1  lea     rcx, [rsp+298h+var_238]
0x180050ca6  mov     [rsp+298h+var_200], rcx
0x180050cae  lea     rcx, [rsp+298h+var_248]
0x180050cb3  mov     [rsp+298h+var_1F8], rcx
0x180050cbb  lea     rcx, [rsp+298h+arg_40]
0x180050cc3  mov     [rsp+298h+var_1F0], rcx
0x180050ccb  mov     [rsp+298h+var_1E8], 0
0x180050cd7  mov     [rsp+298h+var_1E0], eax
0x180050cde  mov     [rsp+298h+var_1DC], 0
0x180050ce6  test    rbx, rbx
0x180050ce9  jnz     short loc_180050D31
0x180050ceb  mov     ebx, 80090026h
0x180050cf0  mov     [rsp+298h+var_248], ebx
0x180050cf4  mov     rcx, [rsp+298h]; this
0x180050cfc  mov     r9d, ebx; char *
0x180050cff  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050d06  mov     edx, 9A7h; void *
0x180050d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050d10  lea     rcx, [rsp+298h+var_218]; this
0x180050d18  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180050d1d  lea     rcx, [rsp+298h+var_198]; this
0x180050d25  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180050d2a  mov     eax, ebx
0x180050d2c  jmp     loc_1800515EE
0x180050d31  mov     rcx, [rsp+298h+var_1D8]; this
0x180050d39  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x180050d3e  mov     ebx, eax
0x180050d40  mov     [rsp+298h+var_248], eax
0x180050d44  xor     edx, edx
0x180050d46  test    eax, eax
0x180050d48  jns     short loc_180050D87
0x180050d4a  mov     rcx, [rsp+298h]; this
0x180050d52  mov     r9d, eax; char *
0x180050d55  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050d5c  mov     edx, 9AAh; void *
0x180050d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050d66  lea     rcx, [rsp+298h+var_218]; this
0x180050d6e  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180050d73  lea     rcx, [rsp+298h+var_198]; this
0x180050d7b  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180050d80  mov     eax, ebx
0x180050d82  jmp     loc_1800515EE
0x180050d87  test    r14d, r14d
0x180050d8a  jz      loc_1800515A7
0x180050d90  mov     r14d, dword ptr [rsp+298h+arg_30]
0x180050d98  test    r12, r12
0x180050d9b  jz      short loc_180050DA6
0x180050d9d  test    r14d, r14d
0x180050da0  jz      loc_1800515A7
0x180050da6  test    r13, r13
0x180050da9  jz      loc_1800515A7
0x180050daf  cmp     [rsp+298h+arg_40], edx
0x180050db6  jnz     loc_1800515A7
0x180050dbc  mov     eax, 0FFFFFFF1h
0x180050dc1  cmp     rdi, rax
0x180050dc4  jz      loc_1800515A7
0x180050dca  cmp     r15, rax
0x180050dcd  jz      loc_1800515A7
0x180050dd3  mov     [rsp+298h+var_1B8], rdx
0x180050ddb  mov     [rsp+298h+var_21C], edx
0x180050ddf  mov     r15, rdx
0x180050de2  mov     [rsp+298h+var_1D0], rdx
0x180050dea  mov     dword ptr [rsp+298h+var_230], edx
0x180050dee  mov     [rsp+298h+var_220], edx
0x180050df2  mov     qword ptr [rsp+298h+var_1C0], rdx
0x180050dfa  mov     [rsp+298h+var_224], edx
0x180050dfe  mov     dword ptr [rsp+298h+var_230+4], edx
0x180050e02  test    rsi, rsi
0x180050e05  jz      loc_180051089
0x180050e0b  cmp     [rsi], edx
0x180050e0d  jz      short loc_180050E55
0x180050e0f  mov     ebx, 80090027h
0x180050e14  mov     [rsp+298h+var_248], ebx
0x180050e18  mov     rcx, [rsp+298h]; this
0x180050e20  mov     r9d, ebx; char *
0x180050e23  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050e2a  mov     edx, 9B8h; void *
0x180050e2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e34  lea     rcx, [rsp+298h+var_218]; this
0x180050e3c  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180050e41  lea     rcx, [rsp+298h+var_198]; this
0x180050e49  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180050e4e  mov     eax, ebx
0x180050e50  jmp     loc_1800515EE
0x180050e55  cmp     r15d, [rsi+4]
0x180050e59  jnb     loc_180051081
0x180050e5f  mov     edi, r15d
0x180050e62  add     rdi, rdi
0x180050e65  mov     rsi, [rsi+8]
0x180050e69  mov     ecx, [rsi+rdi*8+4]
0x180050e6d  sub     ecx, 30h ; '0'
0x180050e70  jz      loc_18005104F
0x180050e76  sub     ecx, 1
0x180050e79  jz      loc_18005102D
0x180050e7f  sub     ecx, 1Fh
0x180050e82  jz      loc_180050FAD
0x180050e88  sub     ecx, 1
0x180050e8b  jz      loc_180050F88
0x180050e91  cmp     ecx, 1
0x180050e94  jz      short loc_180050EF0
0x180050e96  mov     ebx, 80090027h
0x180050e9b  mov     [rsp+298h+var_248], ebx
0x180050e9f  mov     rcx, [rsp+298h]; this
0x180050ea7  mov     eax, [rsi+rdi*8+4]
0x180050eab  mov     dword ptr [rsp+298h+Destination], eax; char *
0x180050eaf  lea     rax, aBufferUnknownT; "Buffer:unknown type: %lu"
0x180050eb6  mov     [rsp+298h+var_278], rax; int
0x180050ebb  mov     r9d, ebx; char *
0x180050ebe  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050ec5  mov     edx, 0A00h; void *
0x180050eca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050ecf  lea     rcx, [rsp+298h+var_218]; this
0x180050ed7  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180050edc  lea     rcx, [rsp+298h+var_198]; this
0x180050ee4  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180050ee9  mov     eax, ebx
0x180050eeb  jmp     loc_1800515EE
0x180050ef0  cmp     dword ptr [rsi+rdi*8], 4
0x180050ef4  jnz     short loc_180050EFF
0x180050ef6  mov     rax, [rsi+rdi*8+8]
0x180050efb  mov     ebx, [rax]
0x180050efd  jmp     short loc_180050F0D
0x180050eff  cmp     dword ptr [rsi+rdi*8], 1
0x180050f03  jnz     short loc_180050F36
0x180050f05  mov     rax, [rsi+rdi*8+8]
0x180050f0a  movzx   ebx, byte ptr [rax]
0x180050f0d  lea     rax, aBufferPlatform; "Buffer:PLATFORM_CLAIM_USE_STATIC"
0x180050f14  lea     rcx, aBufferPlatform_2; "Buffer:PLATFORM_CLAIM_CREATE_STATIC"
0x180050f1b  test    ebx, ebx
0x180050f1d  cmovz   rcx, rax; char *
0x180050f21  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180050f26  neg     ebx
0x180050f28  sbb     eax, eax
0x180050f2a  add     eax, 2
0x180050f2d  or      dword ptr [rsp+298h+var_230+4], eax
0x180050f31  jmp     loc_18005106F
0x180050f36  mov     ebx, 80090027h
0x180050f3b  mov     [rsp+298h+var_248], ebx
0x180050f3f  mov     rcx, [rsp+298h]; this
0x180050f47  lea     rax, aBufferPlatform_4; "Buffer:PLATFORM_CLAIM_STATIC_CREATE wro"...
0x180050f4e  mov     [rsp+298h+var_278], rax; int
0x180050f53  mov     r9d, ebx; char *
0x180050f56  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050f5d  mov     edx, 9EFh; void *
0x180050f62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050f67  lea     rcx, [rsp+298h+var_218]; this
0x180050f6f  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180050f74  lea     rcx, [rsp+298h+var_198]; this
0x180050f7c  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180050f81  mov     eax, ebx
0x180050f83  jmp     loc_1800515EE
0x180050f88  lea     rcx, aBufferPlatform_0; "Buffer:PLATFORM_CLAIM_NONCE"
0x180050f8f  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180050f94  mov     eax, [rsi+rdi*8]
0x180050f97  mov     [rsp+298h+var_224], eax
0x180050f9b  mov     r9, [rsi+rdi*8+8]
0x180050fa0  mov     qword ptr [rsp+298h+var_1C0], r9
0x180050fa8  jmp     loc_18005106F
0x180050fad  cmp     dword ptr [rsi+rdi*8], 4
0x180050fb1  jz      short loc_180051014
0x180050fb3  mov     ebx, 80090027h
0x180050fb8  mov     [rsp+298h+var_248], ebx
0x180050fbc  mov     rcx, [rsp+298h]; this
0x180050fc4  mov     dword ptr [rsp+298h+DestinationSize], 4
0x180050fcc  mov     eax, [rsi+rdi*8]
0x180050fcf  mov     dword ptr [rsp+298h+Destination], eax; char *
0x180050fd3  lea     rax, aBufferPlatform_3; "Buffer:PLATFORM_CLAIM_PCR_MASK cb == %l"...
0x180050fda  mov     [rsp+298h+var_278], rax; int
0x180050fdf  mov     r9d, ebx; char *
0x180050fe2  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180050fe9  mov     edx, 9D5h; void *
0x180050fee  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050ff3  lea     rcx, [rsp+298h+var_218]; this
0x180050ffb  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180051000  lea     rcx, [rsp+298h+var_198]; this
0x180051008  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005100d  mov     eax, ebx
0x18005100f  jmp     loc_1800515EE
0x180051014  lea     rcx, aBufferPlatform_1; "Buffer:PLATFORM_CLAIM_PCR_MASK"
0x18005101b  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180051020  mov     rax, [rsi+rdi*8+8]
0x180051025  mov     eax, [rax]
0x180051027  mov     [rsp+298h+var_220], eax
0x18005102b  jmp     short loc_18005106F
0x18005102d  lea     rcx, aBufferClaimKey; "Buffer:CLAIM_KEYATTESTATION_NONCE"
0x180051034  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180051039  mov     eax, [rsi+rdi*8]
0x18005103c  mov     dword ptr [rsp+298h+var_230], eax
0x180051040  mov     rax, [rsi+rdi*8+8]
0x180051045  mov     [rsp+298h+var_1D0], rax
0x18005104d  jmp     short loc_18005106F
0x18005104f  lea     rcx, aBufferClaimIdb; "Buffer:CLAIM_IDBINDING_NONCE"
0x180051056  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18005105b  mov     eax, [rsi+rdi*8]
0x18005105e  mov     [rsp+298h+var_21C], eax
0x180051062  mov     rax, [rsi+rdi*8+8]
0x180051067  mov     [rsp+298h+var_1B8], rax
0x18005106f  inc     r15d
0x180051072  mov     rsi, [rsp+298h+var_1B0]
0x18005107a  xor     edx, edx
0x18005107c  jmp     loc_180050E55
0x180051081  mov     r15, [rsp+298h+var_1D0]
0x180051089  mov     dil, dl
0x18005108c  cmp     [rsp+298h+var_1A8], rdx
0x180051094  jz      short loc_1800510F6
0x180051096  mov     rcx, [rsp+298h+var_240]; this
0x18005109b  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x1800510a0  mov     ebx, eax
0x1800510a2  mov     [rsp+298h+var_248], eax
0x1800510a6  test    eax, eax
0x1800510a8  jns     short loc_1800510E7
0x1800510aa  mov     rcx, [rsp+298h]; this
0x1800510b2  mov     r9d, eax; char *
0x1800510b5  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800510bc  mov     edx, 0A09h; void *
0x1800510c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800510c6  lea     rcx, [rsp+298h+var_218]; this
0x1800510ce  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800510d3  lea     rcx, [rsp+298h+var_198]; this
0x1800510db  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x1800510e0  mov     eax, ebx
0x1800510e2  jmp     loc_1800515EE
0x1800510e7  mov     rcx, [rsp+298h+var_240]; this
0x1800510ec  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x1800510f1  mov     dil, 1
0x1800510f4  xor     edx, edx
0x1800510f6  mov     sil, dl
0x1800510f9  mov     rcx, qword ptr [rsp+298h+var_1C8]
0x180051101  test    rcx, rcx
0x180051104  jz      short loc_18005117B
0x180051106  mov     rcx, [rsp+298h+var_238]; this
0x18005110b  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x180051110  mov     ebx, eax
0x180051112  mov     [rsp+298h+var_248], eax
0x180051116  test    eax, eax
0x180051118  jns     short loc_180051166
0x18005111a  mov     rcx, [rsp+298h]; this
0x180051122  mov     r9d, eax; char *
0x180051125  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005112c  mov     edx, 0A17h; void *
0x180051131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051136  test    dil, dil
0x180051139  jz      short loc_180051145
0x18005113b  mov     rcx, [rsp+298h+var_240]; this
0x180051140  call    ?UnLockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::UnLockProvider(void)
0x180051145  lea     rcx, [rsp+298h+var_218]; this
0x18005114d  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180051152  lea     rcx, [rsp+298h+var_198]; this
0x18005115a  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18005115f  mov     eax, ebx
0x180051161  jmp     loc_1800515EE
0x180051166  mov     rcx, [rsp+298h+var_238]; this
0x18005116b  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x180051170  mov     sil, 1
0x180051173  mov     rcx, qword ptr [rsp+298h+var_1C8]
0x18005117b  mov     edx, [rsp+298h+var_228]
0x18005117f  mov     eax, edx
  ... truncated ...
```
