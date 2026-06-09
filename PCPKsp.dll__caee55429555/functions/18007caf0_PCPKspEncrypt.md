# PCPKspEncrypt

- ea: `0x18007caf0`
- end: `0x18007d5e8`
- name: `PCPKspEncrypt`
- size: `2808`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800133c4`
- `0x18001c308`
- `0x18001c980`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001f0f0`
- `0x18001f190`
- `0x18001f294`
- `0x18001f2c0`
- `0x180020454`
- `0x180037b20`
- `0x1800388a0`
- `0x180059b78`
- `0x180063c98`
- `0x180063cb8`
- `0x1800764d0`
- `0x18007704c`
- `0x18007caf0`
- `0x18007eebc`
- `0x18009948c`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007cb76`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007cb76`
- `bcrypt!BCryptImportKeyPair` at `0x18007d2b5`
- `bcrypt!BCryptImportKeyPair` at `0x18007d2b5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007d1c8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007d1c8`

## pseudocode

```c
__int64 __fastcall PCPKspEncrypt(
        PCPStorageProvider *a1,
        PCPStorageProviderKey *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int a9)
{
  unsigned __int8 *v10; // r15
  PCPStorageProvider *v13; // rcx
  unsigned int v14; // eax
  const char *v15; // r9
  __int64 result; // rax
  int v17; // eax
  unsigned int v18; // ebx
  unsigned __int8 *v19; // r9
  unsigned int v20; // ebx
  unsigned int v21; // r10d
  unsigned int i; // r11d
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // eax
  int v26; // eax
  unsigned int v27; // ebx
  const WCHAR *v28; // r15
  const WCHAR *v29; // rbx
  int v30; // eax
  int v31; // eax
  unsigned int v32; // ebx
  NTSTATUS v33; // eax
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // ebx
  unsigned int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  int pbInput; // [rsp+20h] [rbp-638h]
  int pbInputa; // [rsp+20h] [rbp-638h]
  int pbInputb; // [rsp+20h] [rbp-638h]
  int KeyProperty; // [rsp+50h] [rbp-608h] BYREF
  PCPStorageProviderKey *v47; // [rsp+58h] [rbp-600h] BYREF
  unsigned int v48; // [rsp+60h] [rbp-5F8h]
  unsigned int v49; // [rsp+64h] [rbp-5F4h] BYREF
  ULONG cbInput; // [rsp+68h] [rbp-5F0h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-5E8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp-5E0h] BYREF
  unsigned __int8 *v53; // [rsp+80h] [rbp-5D8h]
  PCPStorageProvider *v54; // [rsp+88h] [rbp-5D0h] BYREF
  _QWORD v55[7]; // [rsp+90h] [rbp-5C8h] BYREF
  DWORD TickCount; // [rsp+C8h] [rbp-590h]
  char v57; // [rsp+CCh] [rbp-58Ch]
  unsigned __int8 *v58; // [rsp+D0h] [rbp-588h]
  UCHAR v59[336]; // [rsp+E0h] [rbp-578h] BYREF
  UCHAR v60[464]; // [rsp+230h] [rbp-428h] BYREF
  wchar_t String1[264]; // [rsp+400h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+658h] [rbp+0h]

  v48 = a4;
  v10 = a3;
  v58 = a3;
  v53 = a6;
  KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(
    (KspDebugProvider::KspDebugActivity *)v59,
    "PCPKspEncrypt");
  KeyProperty = 0;
  v54 = a1;
  v47 = a2;
  v55[0] = L"PCPKspEncrypt";
  v55[1] = &v54;
  v55[2] = &v47;
  v55[3] = 0;
  v55[4] = &KeyProperty;
  v55[5] = &a9;
  v55[6] = 0;
  TickCount = GetTickCount();
  v57 = 0;
  if ( !a1 || !a2 )
  {
    KeyProperty = -2146893786;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B7,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073510LL;
    goto LABEL_90;
  }
  v13 = v54;
  v14 = a9;
  if ( !*((_DWORD *)v54 + 2) && (a9 & 0x1020) == 0 )
  {
    KeyProperty = -2146893771;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BC,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090035LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073525LL;
    goto LABEL_90;
  }
  if ( !a4 || !v10 || a7 && !v53 || !a8 )
  {
    KeyProperty = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C2,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090027LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073511LL;
    goto LABEL_90;
  }
  *a8 = 0;
  if ( (v14 & 0xFFFFEE88) != 0 )
  {
    KeyProperty = -2146893815;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CF,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090009LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073481LL;
    goto LABEL_90;
  }
  if ( (v14 & 0xFFFFEE99) != 0 )
  {
    KeyProperty = -2146893783;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D5,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090029LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073513LL;
    goto LABEL_90;
  }
  v17 = PCPStorageProvider::ValidateObject(v13);
  v18 = v17;
  KeyProperty = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D8,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v17,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = v18;
    goto LABEL_90;
  }
  if ( v47 != (PCPStorageProviderKey *)4294967281LL )
  {
    if ( (a9 & 0x100) == 0 )
    {
      v26 = PCPStorageProviderKey::ValidateObject(v47);
      v27 = v26;
      KeyProperty = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51C,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)v26,
          pbInput);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
        result = v27;
        goto LABEL_90;
      }
      PCPStorageProviderKey::LockProvider(v47);
      if ( (a9 & 0x20) != 0 )
      {
        memset_0(String1, 0, 0x208u);
        v49 = 520;
        memset_0(v60, 0, sizeof(v60));
        cbInput = 464;
        if ( !a5 || a5[1] != 51 )
        {
          KeyProperty = -2146893785;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x530,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090027LL,
            pbInput);
          PCPStorageProviderKey::UnLockProvider(v47);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
          result = 2148073511LL;
          goto LABEL_90;
        }
        v28 = L"RSAPUBLICBLOB";
        v29 = L"RSA";
        KeyProperty = PCPKspGetKeyProperty(a1, a2, L"Algorithm Name", String1, 520, &v49, 0);
        if ( KeyProperty >= 0 && !wcscmp_0(String1, L"ECDH") )
        {
          v29 = L"ECDH";
          v28 = L"ECCFULLPUBLICBLOB";
        }
        v30 = PCPKspExportKey(a1, a2, 0, v28);
        KeyProperty = v30;
        if ( v30 < 0 )
        {
          v31 = SecurityStatusFromHResult(v30);
          v32 = v31;
          KeyProperty = v31;
          if ( v31 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x54B,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v31,
              0);
          PCPStorageProviderKey::UnLockProvider(v47);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
          result = v32;
          goto LABEL_90;
        }
        phAlgorithm = 0;
        v33 = BCryptOpenAlgorithmProvider(&phAlgorithm, v29, 0, 0);
        if ( v33 )
        {
          if ( (v33 & 0xFFFF000) == 0x290000 )
          {
            v34 = v33 & 0xFFF | 0x80280000;
          }
          else if ( (v33 & 0xFFF0000) == 0x70000 )
          {
            v34 = (unsigned __int16)v33;
            if ( (_WORD)v33 )
              v34 = (unsigned __int16)v33 | 0x80070000;
          }
          else
          {
            v34 = v33 | 0x10000000;
          }
          KeyProperty = v34;
          if ( v34 < 0 )
          {
            v35 = SecurityStatusFromHResult(v34);
            v36 = v35;
            KeyProperty = v35;
            if ( v35 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x54F,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                (const char *)(unsigned int)v35,
                0);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            PCPStorageProviderKey::UnLockProvider(v47);
            KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
            KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
            result = v36;
            goto LABEL_90;
          }
        }
        else
        {
          KeyProperty = 0;
        }
        phKey = 0;
        v37 = BCryptImportKeyPair(phAlgorithm, 0, v28, &phKey, v60, cbInput, 0);
        v38 = v37;
        if ( v37 )
        {
          if ( (v37 & 0xFFFF000) == 0x290000 )
          {
            v38 = v37 & 0xFFF | 0x80280000;
          }
          else if ( (v37 & 0xFFF0000) == 0x70000 )
          {
            v38 = (unsigned __int16)v37;
            if ( (_WORD)v37 )
              v38 = (unsigned __int16)v37 | 0x80070000;
          }
          else
          {
            LODWORD(v38) = v37 | 0x10000000;
          }
          KeyProperty = v38;
          if ( (int)v38 < 0 )
          {
            v39 = SecurityStatusFromHResult(v38);
            v40 = v39;
            KeyProperty = v39;
            if ( v39 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x553,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                (const char *)(unsigned int)v39,
                pbInputb);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            PCPStorageProviderKey::UnLockProvider(v47);
            KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
            KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
            result = v40;
            goto LABEL_90;
          }
        }
        else
        {
          KeyProperty = 0;
        }
        pbInputa = (int)v58;
        KeyProperty = TpmGenerateAttestationChallenge(v38, phKey, *((_QWORD *)a5 + 1), *a5);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      }
      else
      {
        KeyProperty = PCPStorageProviderKey::Encrypt(v47, v10, v48, a5, v53, a7, a8, a9);
      }
      PCPStorageProviderKey::UnLockProvider(v47);
      v25 = KeyProperty;
      goto LABEL_83;
    }
LABEL_87:
    KeyProperty = -2146893815;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x518,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090009LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073481LL;
    goto LABEL_90;
  }
  if ( (a9 & 0x100) == 0 )
    goto LABEL_87;
  if ( !*((_DWORD *)v54 + 2) )
  {
    KeyProperty = -2146893771;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E3,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090035LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
    result = 2148073525LL;
    goto LABEL_90;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a5 )
    goto LABEL_41;
  for ( i = 0; i < a5[1]; ++i )
  {
    v23 = *((_QWORD *)a5 + 1);
    if ( *(_DWORD *)(v23 + 16LL * i + 4) == 70 )
    {
      if ( v19 )
      {
        KeyProperty = -2146893783;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4ED,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)0x80090029LL,
          pbInput);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
        result = 2148073513LL;
        goto LABEL_90;
      }
      goto LABEL_38;
    }
    if ( *(_DWORD *)(v23 + 16LL * i + 4) == 71 )
    {
      if ( v19 )
      {
        KeyProperty = -2146893783;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F5,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)0x80090029LL,
          pbInput);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
        result = 2148073513LL;
        goto LABEL_90;
      }
      v21 |= 0x10u;
LABEL_38:
      v20 = *(_DWORD *)(v23 + 16LL * i);
      v19 = *(unsigned __int8 **)(v23 + 16LL * i + 8);
      continue;
    }
    if ( *(_DWORD *)(v23 + 16LL * i + 4) != 73 )
    {
      KeyProperty = -2146893783;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090029LL,
        pbInput);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
      result = 2148073513LL;
      goto LABEL_90;
    }
    if ( *(_DWORD *)(v23 + 16LL * i) != 4 )
    {
      KeyProperty = -2146893785;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4FE,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090027LL,
        pbInput);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
      result = 2148073511LL;
      goto LABEL_90;
    }
    v24 = v21 | 1;
    if ( !**(_DWORD **)(v23 + 16LL * i + 8) )
      v24 = v21;
    v21 = v24;
  }
  v10 = v58;
LABEL_41:
  v25 = PCPStorageProvider::Seal(v54, v10, v48, v19, v20, v53, a7, a8, v21);
  KeyProperty = v25;
LABEL_83:
  v41 = SecurityStatusFromHResult(v25);
  v42 = v41;
  KeyProperty = v41;
  if ( v41 >= 0 )
  {
    KspDebugProvider::KspDebugActivity::StopWithResult<char const (&)[21]>((KspDebugProvider::KspDebugActivity *)v59);
    v42 = KeyProperty;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56D,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v41,
      pbInputa);
  }
  KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v55);
  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v59);
  result = v42;
LABEL_90:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v49 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x571,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              v15);
      result = v49;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18007caf0  push    rbx
0x18007caf2  push    rsi
0x18007caf3  push    rdi
0x18007caf4  push    r12
0x18007caf6  push    r13
0x18007caf8  push    r14
0x18007cafa  push    r15
0x18007cafc  sub     rsp, 620h
0x18007cb03  mov     rax, cs:__security_cookie
0x18007cb0a  xor     rax, rsp
0x18007cb0d  mov     [rsp+658h+var_48], rax
0x18007cb15  mov     ebx, r9d
0x18007cb18  mov     [rsp+658h+var_5F8], ebx
0x18007cb1c  mov     r15, r8
0x18007cb1f  mov     [rsp+658h+var_588], r8
0x18007cb27  mov     rsi, rdx
0x18007cb2a  mov     r14, rcx
0x18007cb2d  mov     rdi, [rsp+658h+arg_20]
0x18007cb35  mov     rax, [rsp+658h+arg_28]
0x18007cb3d  mov     [rsp+658h+var_5D8], rax
0x18007cb45  mov     r12, [rsp+658h+arg_38]
0x18007cb4d  lea     rdx, aPcpkspencrypt_0; "PCPKspEncrypt"
0x18007cb54  lea     rcx, [rsp+658h+var_578]; this
0x18007cb5c  call    ??$Start@AEAY0BG@$$CBD@KspDebugActivity@KspDebugProvider@@SA?AV01@AEAY0BG@$$CBD@Z; KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(char const (&)[22])
0x18007cb61  mov     [rsp+658h+var_608], 0
0x18007cb69  mov     [rsp+658h+var_5D0], r14
0x18007cb71  mov     [rsp+658h+var_600], rsi
0x18007cb76  call    cs:__imp_GetTickCount
0x18007cb7d  nop     dword ptr [rax+rax+00h]
0x18007cb82  lea     rcx, aPcpkspencrypt; "PCPKspEncrypt"
0x18007cb89  mov     [rsp+658h+var_5C8], rcx
0x18007cb91  lea     rcx, [rsp+658h+var_5D0]
0x18007cb99  mov     [rsp+658h+var_5C0], rcx
0x18007cba1  lea     rcx, [rsp+658h+var_600]
0x18007cba6  mov     [rsp+658h+var_5B8], rcx
0x18007cbae  xor     edx, edx
0x18007cbb0  mov     [rsp+658h+var_5B0], rdx
0x18007cbb8  lea     rcx, [rsp+658h+var_608]
0x18007cbbd  mov     [rsp+658h+var_5A8], rcx
0x18007cbc5  lea     rcx, [rsp+658h+arg_40]
0x18007cbcd  mov     [rsp+658h+var_5A0], rcx
0x18007cbd5  mov     [rsp+658h+var_598], rdx
0x18007cbdd  mov     [rsp+658h+var_590], eax
0x18007cbe4  mov     [rsp+658h+var_58C], dl
0x18007cbeb  test    r14, r14
0x18007cbee  jz      loc_18007D57D
0x18007cbf4  test    rsi, rsi
0x18007cbf7  jz      loc_18007D57D
0x18007cbfd  mov     rcx, [rsp+658h+var_5D0]; this
0x18007cc05  mov     eax, [rsp+658h+arg_40]
0x18007cc0c  cmp     [rcx+8], edx
0x18007cc0f  jnz     short loc_18007CC5E
0x18007cc11  test    eax, 1020h
0x18007cc16  jnz     short loc_18007CC5E
0x18007cc18  mov     ebx, 80090035h
0x18007cc1d  mov     [rsp+658h+var_608], ebx
0x18007cc21  mov     rcx, [rsp+658h]; this
0x18007cc29  mov     r9d, ebx; char *
0x18007cc2c  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cc33  mov     edx, 4BCh; void *
0x18007cc38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cc3d  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cc45  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cc4a  lea     rcx, [rsp+658h+var_578]; this
0x18007cc52  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cc57  mov     eax, ebx
0x18007cc59  jmp     loc_18007D5C4
0x18007cc5e  test    ebx, ebx
0x18007cc60  jz      loc_18007D53A
0x18007cc66  test    r15, r15
0x18007cc69  jz      loc_18007D53A
0x18007cc6f  mov     r13d, [rsp+658h+arg_30]
0x18007cc77  test    r13d, r13d
0x18007cc7a  jz      short loc_18007CC8A
0x18007cc7c  cmp     [rsp+658h+var_5D8], rdx
0x18007cc84  jz      loc_18007D53A
0x18007cc8a  test    r12, r12
0x18007cc8d  jz      loc_18007D53A
0x18007cc93  mov     [r12], edx
0x18007cc97  test    eax, 0FFFFEE88h
0x18007cc9c  jz      short loc_18007CCE4
0x18007cc9e  mov     ebx, 80090009h
0x18007cca3  mov     [rsp+658h+var_608], ebx
0x18007cca7  mov     rcx, [rsp+658h]; this
0x18007ccaf  mov     r9d, ebx; char *
0x18007ccb2  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007ccb9  mov     edx, 4CFh; void *
0x18007ccbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ccc3  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cccb  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007ccd0  lea     rcx, [rsp+658h+var_578]; this
0x18007ccd8  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007ccdd  mov     eax, ebx
0x18007ccdf  jmp     loc_18007D5C4
0x18007cce4  test    eax, 0FFFFEE99h
0x18007cce9  jz      short loc_18007CD31
0x18007cceb  mov     ebx, 80090029h
0x18007ccf0  mov     [rsp+658h+var_608], ebx
0x18007ccf4  mov     rcx, [rsp+658h]; this
0x18007ccfc  mov     r9d, ebx; char *
0x18007ccff  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cd06  mov     edx, 4D5h; void *
0x18007cd0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd10  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cd18  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cd1d  lea     rcx, [rsp+658h+var_578]; this
0x18007cd25  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cd2a  mov     eax, ebx
0x18007cd2c  jmp     loc_18007D5C4
0x18007cd31  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x18007cd36  mov     ebx, eax
0x18007cd38  mov     [rsp+658h+var_608], eax
0x18007cd3c  test    eax, eax
0x18007cd3e  jns     short loc_18007CD7D
0x18007cd40  mov     rcx, [rsp+658h]; this
0x18007cd48  mov     r9d, eax; char *
0x18007cd4b  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cd52  mov     edx, 4D8h; void *
0x18007cd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd5c  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cd64  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cd69  lea     rcx, [rsp+658h+var_578]; this
0x18007cd71  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cd76  mov     eax, ebx
0x18007cd78  jmp     loc_18007D5C4
0x18007cd7d  mov     eax, 0FFFFFFF1h
0x18007cd82  mov     rcx, [rsp+658h+var_600]; this
0x18007cd87  cmp     rcx, rax
0x18007cd8a  jnz     loc_18007CFD9
0x18007cd90  test    [rsp+658h+arg_40], 100h
0x18007cd9b  jz      loc_18007D4F4
0x18007cda1  mov     rsi, [rsp+658h+var_5D0]
0x18007cda9  xor     r14d, r14d
0x18007cdac  cmp     [rsi+8], r14d
0x18007cdb0  jnz     short loc_18007CDF8
0x18007cdb2  mov     ebx, 80090035h
0x18007cdb7  mov     [rsp+658h+var_608], ebx
0x18007cdbb  mov     rcx, [rsp+658h]; this
0x18007cdc3  mov     r9d, ebx; char *
0x18007cdc6  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cdcd  mov     edx, 4E3h; void *
0x18007cdd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cdd7  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cddf  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cde4  lea     rcx, [rsp+658h+var_578]; this
0x18007cdec  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cdf1  mov     eax, ebx
0x18007cdf3  jmp     loc_18007D5C4
0x18007cdf8  mov     r9, r14; unsigned __int8 *
0x18007cdfb  mov     ebx, r14d
0x18007cdfe  mov     r10d, r14d
0x18007ce01  test    rdi, rdi
0x18007ce04  jz      loc_18007CFA0
0x18007ce0a  mov     r11d, r14d
0x18007ce0d  cmp     r11d, [rdi+4]
0x18007ce11  jnb     loc_18007CF98
0x18007ce17  mov     ecx, r11d
0x18007ce1a  add     rcx, rcx
0x18007ce1d  mov     rdx, [rdi+8]
0x18007ce21  mov     r8d, [rdx+rcx*8+4]
0x18007ce26  sub     r8d, 46h ; 'F'
0x18007ce2a  jz      loc_18007CF3D
0x18007ce30  sub     r8d, 1
0x18007ce34  jz      loc_18007CEEC
0x18007ce3a  cmp     r8d, 2
0x18007ce3e  jz      short loc_18007CE86
0x18007ce40  mov     ebx, 80090029h
0x18007ce45  mov     [rsp+658h+var_608], ebx
0x18007ce49  mov     rcx, [rsp+658h]; this
0x18007ce51  mov     r9d, ebx; char *
0x18007ce54  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007ce5b  mov     edx, 506h; void *
0x18007ce60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ce65  lea     rcx, [rsp+658h+var_5C8]; this
0x18007ce6d  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007ce72  lea     rcx, [rsp+658h+var_578]; this
0x18007ce7a  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007ce7f  mov     eax, ebx
0x18007ce81  jmp     loc_18007D5C4
0x18007ce86  cmp     dword ptr [rdx+rcx*8], 4
0x18007ce8a  jz      short loc_18007CED2
0x18007ce8c  mov     ebx, 80090027h
0x18007ce91  mov     [rsp+658h+var_608], ebx
0x18007ce95  mov     rcx, [rsp+658h]; this
0x18007ce9d  mov     r9d, ebx; char *
0x18007cea0  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cea7  mov     edx, 4FEh; void *
0x18007ceac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ceb1  lea     rcx, [rsp+658h+var_5C8]; this
0x18007ceb9  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cebe  lea     rcx, [rsp+658h+var_578]; this
0x18007cec6  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cecb  mov     eax, ebx
0x18007cecd  jmp     loc_18007D5C4
0x18007ced2  mov     rax, [rdx+rcx*8+8]
0x18007ced7  mov     ecx, r10d
0x18007ceda  or      ecx, 1
0x18007cedd  cmp     [rax], r14d
0x18007cee0  cmovz   ecx, r10d
0x18007cee4  mov     r10d, ecx
0x18007cee7  jmp     loc_18007CF90
0x18007ceec  test    r9, r9
0x18007ceef  jz      short loc_18007CF37
0x18007cef1  mov     ebx, 80090029h
0x18007cef6  mov     [rsp+658h+var_608], ebx
0x18007cefa  mov     rcx, [rsp+658h]; this
0x18007cf02  mov     r9d, ebx; char *
0x18007cf05  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cf0c  mov     edx, 4F5h; void *
0x18007cf11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cf16  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cf1e  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cf23  lea     rcx, [rsp+658h+var_578]; this
0x18007cf2b  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cf30  mov     eax, ebx
0x18007cf32  jmp     loc_18007D5C4
0x18007cf37  or      r10d, 10h
0x18007cf3b  jmp     short loc_18007CF88
0x18007cf3d  test    r9, r9
0x18007cf40  jz      short loc_18007CF88
0x18007cf42  mov     ebx, 80090029h
0x18007cf47  mov     [rsp+658h+var_608], ebx
0x18007cf4b  mov     rcx, [rsp+658h]; this
0x18007cf53  mov     r9d, ebx; char *
0x18007cf56  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007cf5d  mov     edx, 4EDh; void *
0x18007cf62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cf67  lea     rcx, [rsp+658h+var_5C8]; this
0x18007cf6f  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007cf74  lea     rcx, [rsp+658h+var_578]; this
0x18007cf7c  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007cf81  mov     eax, ebx
0x18007cf83  jmp     loc_18007D5C4
0x18007cf88  mov     ebx, [rdx+rcx*8]
0x18007cf8b  mov     r9, [rdx+rcx*8+8]
0x18007cf90  inc     r11d
0x18007cf93  jmp     loc_18007CE0D
0x18007cf98  mov     r15, [rsp+658h+var_588]
0x18007cfa0  mov     [rsp+658h+var_618], r10d; unsigned int
0x18007cfa5  mov     [rsp+658h+var_620], r12; unsigned int *
0x18007cfaa  mov     [rsp+658h+dwFlags], r13d; unsigned int
0x18007cfaf  mov     rax, [rsp+658h+var_5D8]
0x18007cfb7  mov     qword ptr [rsp+658h+cbInput], rax; unsigned __int8 *
0x18007cfbc  mov     dword ptr [rsp+658h+pbInput], ebx; unsigned int
0x18007cfc0  mov     r8d, [rsp+658h+var_5F8]; unsigned int
0x18007cfc5  mov     rdx, r15; unsigned __int8 *
0x18007cfc8  mov     rcx, rsi; this
0x18007cfcb  call    ?Seal@PCPStorageProvider@@QEAAJPEAEK0K0KPEAKK@Z; PCPStorageProvider::Seal(uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,ulong)
0x18007cfd0  mov     [rsp+658h+var_608], eax
0x18007cfd4  jmp     loc_18007D46B
0x18007cfd9  test    [rsp+658h+arg_40], 100h
0x18007cfe4  jnz     loc_18007D4F4
0x18007cfea  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x18007cfef  mov     ebx, eax
0x18007cff1  mov     [rsp+658h+var_608], eax
0x18007cff5  test    eax, eax
0x18007cff7  jns     short loc_18007D036
0x18007cff9  mov     rcx, [rsp+658h]; this
0x18007d001  mov     r9d, eax; char *
0x18007d004  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007d00b  mov     edx, 51Ch; void *
0x18007d010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d015  lea     rcx, [rsp+658h+var_5C8]; this
0x18007d01d  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x18007d022  lea     rcx, [rsp+658h+var_578]; this
0x18007d02a  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18007d02f  mov     eax, ebx
0x18007d031  jmp     loc_18007D5C4
0x18007d036  mov     rcx, [rsp+658h+var_600]; this
0x18007d03b  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x18007d040  mov     ecx, [rsp+658h+arg_40]
0x18007d047  test    cl, 20h
0x18007d04a  jz      loc_18007D429
0x18007d050  mov     ebx, 208h
0x18007d055  mov     r8d, ebx; Size
0x18007d058  xor     edx, edx; Val
0x18007d05a  lea     rcx, [rsp+658h+String1]; void *
0x18007d062  call    memset_0
0x18007d067  mov     [rsp+658h+var_5F4], ebx
0x18007d06b  mov     ebx, 1D0h
0x18007d070  mov     r8d, ebx; Size
0x18007d073  xor     edx, edx; Val
0x18007d075  lea     rcx, [rsp+658h+var_428]; void *
0x18007d07d  call    memset_0
0x18007d082  mov     [rsp+658h+var_5F0], ebx
0x18007d086  test    rdi, rdi
0x18007d089  jz      loc_18007D3D9
0x18007d08f  cmp     dword ptr [rdi+4], 33h ; '3'
0x18007d093  jnz     loc_18007D3D9
0x18007d099  lea     r15, aRsapublicblob; "RSAPUBLICBLOB"
0x18007d0a0  lea     rbx, aRsa; "RSA"
0x18007d0a7  mov     [rsp+658h+dwFlags], 0
0x18007d0af  lea     rax, [rsp+658h+var_5F4]
0x18007d0b4  mov     qword ptr [rsp+658h+cbInput], rax
0x18007d0b9  mov     dword ptr [rsp+658h+pbInput], 208h
0x18007d0c1  lea     r9, [rsp+658h+String1]
0x18007d0c9  lea     r8, aAlgorithmName; "Algorithm Name"
0x18007d0d0  mov     rdx, rsi
0x18007d0d3  mov     rcx, r14
0x18007d0d6  call    PCPKspGetKeyProperty
  ... truncated ...
```
