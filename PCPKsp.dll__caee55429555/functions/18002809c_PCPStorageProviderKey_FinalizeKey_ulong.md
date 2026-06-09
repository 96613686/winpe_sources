# PCPStorageProviderKey::FinalizeKey(ulong)

- ea: `0x18002809c`
- end: `0x180028ba9`
- name: `?FinalizeKey@PCPStorageProviderKey@@QEAAJK@Z`
- size: `2829`
- prototype: `__int64 __fastcall(PCPStorageProviderKey *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180027cf0`

## callees

- `0x18000f240`
- `0x18000f858`
- `0x1800113f0`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180019ed4`
- `0x18002809c`
- `0x180028bb0`
- `0x180029a20`
- `0x1800528d0`
- `0x180061bac`
- `0x1800764d0`
- `0x1800768a0`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028b21`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028b21`
- `bcrypt!BCryptGenerateKeyPair` at `0x180028491`
- `bcrypt!BCryptGenerateKeyPair` at `0x1800287d0`
- `bcrypt!BCryptGenerateKeyPair` at `0x180028491`
- `bcrypt!BCryptGenerateKeyPair` at `0x1800287d0`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800284e3`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180028814`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800284e3`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180028814`
- `bcrypt!BCryptSetProperty` at `0x180028431`
- `bcrypt!BCryptSetProperty` at `0x180028431`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800283cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002877c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800283cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002877c`
- `bcrypt!BCryptExportKey` at `0x180028558`
- `bcrypt!BCryptExportKey` at `0x1800285e8`
- `bcrypt!BCryptExportKey` at `0x18002887b`
- `bcrypt!BCryptExportKey` at `0x1800288fd`
- `bcrypt!BCryptExportKey` at `0x180028558`
- `bcrypt!BCryptExportKey` at `0x1800285e8`
- `bcrypt!BCryptExportKey` at `0x18002887b`
- `bcrypt!BCryptExportKey` at `0x1800288fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall PCPStorageProviderKey::FinalizeKey(PCPStorageProviderKey *this, char a2)
{
  char v5; // di
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // ecx
  const wchar_t *v10; // rdi
  int v11; // eax
  unsigned int v12; // edi
  PUCHAR v13; // rdi
  int v14; // eax
  unsigned int v15; // esi
  const struct std::nothrow_t *v16; // rdx
  BCRYPT_HANDLE *v17; // rsi
  NTSTATUS v18; // eax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // ebx
  NTSTATUS v21; // eax
  BCRYPT_KEY_HANDLE *v22; // r14
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  const struct std::nothrow_t *v26; // rdx
  PUCHAR v27; // rsi
  NTSTATUS v28; // eax
  int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  unsigned int v31; // r14d
  const struct std::nothrow_t *v32; // rdx
  int Property; // eax
  unsigned int v34; // edi
  NTSTATUS v35; // eax
  unsigned int v36; // ebx
  BCRYPT_KEY_HANDLE *v37; // rsi
  NTSTATUS KeyPair; // eax
  unsigned int v39; // ebx
  NTSTATUS v40; // eax
  unsigned int v41; // ebx
  NTSTATUS v42; // eax
  unsigned int v43; // ebx
  NTSTATUS v44; // eax
  int v45; // eax
  int v46; // eax
  unsigned int v47; // edi
  const struct std::nothrow_t *v48; // rdx
  PUCHAR v49; // r8
  _DWORD *v50; // rdi
  const struct std::nothrow_t *v51; // rdx
  _BYTE *v52; // rax
  __int64 v53; // rcx
  int v54; // eax
  unsigned int v55; // edi
  const WCHAR *v56; // rcx
  const struct std::nothrow_t *v57; // rdx
  const char *v58; // r9
  unsigned int LastError; // ebx
  ULONG *dwFlags; // [rsp+20h] [rbp-98h]
  int dwFlagsa; // [rsp+20h] [rbp-98h]
  int dwFlagsb; // [rsp+20h] [rbp-98h]
  int dwFlagsc; // [rsp+20h] [rbp-98h]
  int *dwFlagsd; // [rsp+20h] [rbp-98h]
  ULONG cbOutput; // [rsp+40h] [rbp-78h] BYREF
  ULONG cbInput; // [rsp+44h] [rbp-74h] BYREF
  _BYTE v67[24]; // [rsp+48h] [rbp-70h] BYREF
  int v68; // [rsp+60h] [rbp-58h] BYREF
  int v69; // [rsp+64h] [rbp-54h] BYREF
  ULONG dwLength; // [rsp+68h] [rbp-50h] BYREF
  PUCHAR pbOutput; // [rsp+70h] [rbp-48h] BYREF
  PUCHAR pbInput; // [rsp+78h] [rbp-40h] BYREF
  __int128 v73; // [rsp+80h] [rbp-38h] BYREF
  int v74; // [rsp+90h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v67, L"PCPStorageProviderKey::FinalizeKey", 1);
  if ( *((_BYTE *)this + 708) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA0,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)0x80290414LL,
      (int)dwFlags);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
    return 2150171668LL;
  }
  v5 = *((_BYTE *)this + 736) | ((a2 & 0x40) != 0);
  *((_BYTE *)this + 736) = v5;
  v6 = *((_DWORD *)this + 188);
  if ( (v6 & 1) != 0 || (v7 = *((_QWORD *)this + 77)) != 0 && (unsigned int)(*(_DWORD *)(v7 + 4) - 1) <= 1 )
  {
    if ( (v6 & 0xA) == 0 )
    {
      if ( v5 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCAE,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x80090022LL,
          (int)dwFlags);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return 2148073506LL;
      }
      else
      {
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return 2148073518LL;
      }
    }
    v8 = *((_QWORD *)this + 77);
    if ( v8 )
    {
      if ( *(_DWORD *)(v8 + 4) == 2 )
      {
        KspDebugProvider::TraceLoggingInfo("UI policy set to high protection.");
        v73 = 0;
        v74 = 0;
        cbOutput = 0;
        dwFlags = &cbOutput;
        if ( (int)ProviderGetProperty(*((_QWORD *)this + 96), 87, &v73) >= 0 )
        {
          cbOutput = 0;
          v9 = 0;
          while ( !*((_BYTE *)&v73 + v9) )
          {
            cbOutput = ++v9;
            if ( v9 >= 0x14 )
            {
              if ( *((_QWORD *)this + 77) )
              {
                KspDebugProvider::TraceLoggingInfo("Authvalue is 0, removing UI flag.");
                *(_DWORD *)(*((_QWORD *)this + 77) + 4LL) = 0;
              }
              break;
            }
          }
        }
      }
    }
  }
  if ( (*((_BYTE *)this + 720) & 0xC) != 0 )
  {
    KspDebugProvider::TraceLoggingInfo("Key Archival requested.");
    dwLength = 0;
    v69 = 0;
    v10 = (const wchar_t *)*((_QWORD *)this + 89);
    if ( !wcscmp_0(L"RSA", v10) || !wcscmp_0(L"RSA_SIGN", v10) )
    {
      Property = ProviderGetProperty(*((_QWORD *)this + 96), 5, &dwLength);
      v34 = Property;
      if ( Property < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCE2,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)Property,
          (int)&v69);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v34;
      }
      v35 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 97, L"RSA", L"Microsoft Primitive Provider", 0);
      if ( v35 < 0 )
      {
        v36 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xCE7,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v35,
                (int)&v69);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v36;
      }
      v37 = (BCRYPT_KEY_HANDLE *)((char *)this + 784);
      KeyPair = BCryptGenerateKeyPair(*((BCRYPT_ALG_HANDLE *)this + 97), (BCRYPT_KEY_HANDLE *)this + 98, dwLength, 0);
      if ( KeyPair < 0 )
      {
        v39 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xCEB,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)KeyPair,
                (int)&v69);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v39;
      }
      v40 = BCryptFinalizeKeyPair(*v37, 0);
      if ( v40 < 0 )
      {
        v41 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xCEC,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v40,
                (int)&v69);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v41;
      }
      cbOutput = 0;
      v42 = BCryptExportKey(*v37, 0, L"RSAPRIVATEBLOB", 0, 0, &cbOutput, 0);
      if ( v42 < 0 )
      {
        v43 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xCF6,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v42,
                dwFlagsc);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v43;
      }
      wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, cbOutput);
      v13 = pbOutput;
      if ( !pbOutput )
        goto LABEL_63;
      v44 = BCryptExportKey(*v37, 0, L"RSAPRIVATEBLOB", pbOutput, cbOutput, &cbOutput, 0);
      if ( v44 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xCFE,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v44,
                (int)dwFlags);
        if ( v13 )
LABEL_77:
          operator delete(v13, v19);
LABEL_78:
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v20;
      }
      v45 = ProviderSetProperty(*((_QWORD *)this + 96), 12, v13, cbOutput);
      v15 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD03,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)v45,
          (int)dwFlags);
        if ( !v13 )
          goto LABEL_29;
        goto LABEL_28;
      }
    }
    else
    {
      if ( wcscmp_0(L"ECDH", v10) && wcscmp_0(L"ECDSA", v10) )
        goto LABEL_82;
      cbInput = 0;
      v11 = ProviderGetProperty(*((_QWORD *)this + 96), 32, 0);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD0D,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)v11,
          (int)&cbInput);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v12;
      }
      wil::make_unique_nothrow<unsigned char [0]>(&pbInput, cbInput);
      v13 = pbInput;
      if ( !pbInput )
        goto LABEL_63;
      v14 = ProviderGetProperty(*((_QWORD *)this + 96), 32, pbInput);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD13,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)v14,
          (int)&cbInput);
        if ( !v13 )
        {
LABEL_29:
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
          return v15;
        }
LABEL_28:
        operator delete(v13, v16);
        goto LABEL_29;
      }
      v17 = (BCRYPT_HANDLE *)((char *)this + 776);
      v18 = BCryptOpenAlgorithmProvider(
              (BCRYPT_ALG_HANDLE *)this + 97,
              *((LPCWSTR *)this + 89),
              L"Microsoft Primitive Provider",
              0);
      if ( v18 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD18,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v18,
                (int)&cbInput);
        if ( v13 )
          goto LABEL_77;
        goto LABEL_78;
      }
      v21 = BCryptSetProperty(*v17, L"ECCCurveName", v13, cbInput, 0);
      if ( v21 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD1D,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v21,
                dwFlagsa);
        if ( v13 )
          goto LABEL_77;
        goto LABEL_78;
      }
      v22 = (BCRYPT_KEY_HANDLE *)((char *)this + 784);
      v23 = BCryptGenerateKeyPair(*v17, (BCRYPT_KEY_HANDLE *)this + 98, 0, 0);
      if ( v23 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD21,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v23,
                dwFlagsa);
        if ( v13 )
          goto LABEL_77;
        goto LABEL_78;
      }
      v24 = BCryptFinalizeKeyPair(*v22, 0);
      if ( v24 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD22,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v24,
                dwFlagsa);
        if ( v13 )
          goto LABEL_77;
        goto LABEL_78;
      }
      cbOutput = 0;
      v25 = BCryptExportKey(*v22, 0, L"ECCPRIVATEBLOB", 0, 0, &cbOutput, 0);
      if ( v25 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD2C,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v25,
                dwFlagsb);
        if ( v13 )
          goto LABEL_77;
        goto LABEL_78;
      }
      wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, cbOutput);
      v27 = pbOutput;
      if ( !pbOutput )
      {
        if ( v13 )
          operator delete(v13, v26);
        goto LABEL_63;
      }
      v28 = BCryptExportKey(*v22, 0, L"ECCPRIVATEBLOB", pbOutput, cbOutput, &cbOutput, 0);
      if ( v28 < 0 )
      {
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xD34,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)v28,
                (int)dwFlags);
        if ( v27 )
          operator delete(v27, v19);
        if ( !v13 )
          goto LABEL_78;
        goto LABEL_77;
      }
      v29 = ProviderSetProperty(*((_QWORD *)this + 96), 3, v27, cbOutput);
      v31 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD39,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)v29,
          (int)dwFlags);
        if ( v27 )
          operator delete(v27, v32);
        if ( v13 )
          operator delete(v13, v32);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
        return v31;
      }
      if ( v27 )
        operator delete(v27, v30);
    }
    if ( v13 )
      operator delete(v13, v30);
  }
LABEL_82:
  v46 = ProviderFinalizeKeyPair(*((TpmObject **)this + 96));
  v47 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3E,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v46,
      (int)dwFlags);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
    return v47;
  }
  *((_BYTE *)this + 708) = 1;
  v68 = 0;
  dwFlagsd = &v68;
  if ( (int)ProviderGetProperty(*((_QWORD *)this + 96), 54, 0) < 0 )
    goto LABEL_92;
  operator delete(*((void **)this + 83), v48);
  *((_QWORD *)this + 83) = 0;
  wil::make_unique_nothrow<unsigned char [0]>(&pbOutput, (unsigned int)v68);
  v49 = pbOutput;
  if ( !pbOutput )
  {
LABEL_63:
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
    return 2147942408LL;
  }
  *((_QWORD *)this + 83) = pbOutput;
  v50 = (_DWORD *)((char *)this + 656);
  *((_DWORD *)this + 164) = v68;
  LODWORD(dwFlagsd) = (_DWORD)this + 656;
  if ( (int)ProviderGetProperty(*((_QWORD *)this + 96), 54, v49) < 0 )
  {
    v52 = (_BYTE *)*((_QWORD *)this + 83);
    if ( v52 )
    {
      v53 = (unsigned int)*v50;
      if ( *v50 )
      {
        do
        {
          *v52++ = 0;
          --v53;
        }
        while ( v53 );
      }
      operator delete(*((void **)this + 83), v51);
      *((_QWORD *)this + 83) = 0;
    }
    *v50 = 0;
  }
LABEL_92:
  v54 = PCPStorageProviderKey::StoreToContainer(this, 1, 0);
  v55 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD57,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v54,
      (int)dwFlagsd);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
    return v55;
  }
  v56 = (const WCHAR *)*((_QWORD *)this + 76);
  if ( v56 )
  {
    if ( !DeleteFileW(v56) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD5C,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v58);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
      return LastError;
    }
    operator delete(*((void **)this + 76), v57);
    *((_QWORD *)this + 76) = 0;
  }
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v67);
  return 0;
}

```

## disassembly

```asm
0x18002809c  mov     [rsp+arg_8], rbx
0x1800280a1  mov     [rsp+arg_10], rsi
0x1800280a6  push    rdi
0x1800280a7  push    r14
0x1800280a9  push    r15
0x1800280ab  sub     rsp, 0A0h
0x1800280b2  mov     rax, cs:__security_cookie
0x1800280b9  xor     rax, rsp
0x1800280bc  mov     [rsp+0B8h+var_20], rax
0x1800280c4  mov     edi, edx
0x1800280c6  mov     rbx, rcx
0x1800280c9  mov     r8b, 1; bool
0x1800280cc  lea     rdx, aPcpstorageprov_24; "PCPStorageProviderKey::FinalizeKey"
0x1800280d3  lea     rcx, [rsp+0B8h+var_70]; this
0x1800280d8  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800280dd  nop
0x1800280de  xor     r15d, r15d
0x1800280e1  cmp     [rbx+2C4h], r15b
0x1800280e8  jz      short loc_18002811D
0x1800280ea  mov     rcx, [rsp+0B8h]; this
0x1800280f2  mov     ebx, 80290414h
0x1800280f7  mov     r9d, ebx; char *
0x1800280fa  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028101  mov     edx, 0CA0h; void *
0x180028106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002810b  nop
0x18002810c  lea     rcx, [rsp+0B8h+var_70]; this
0x180028111  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028116  mov     eax, ebx
0x180028118  jmp     loc_180028B7F
0x18002811d  shr     edi, 6
0x180028120  and     dil, 1
0x180028124  or      dil, [rbx+2E0h]
0x18002812b  mov     [rbx+2E0h], dil
0x180028132  mov     ecx, [rbx+2F0h]
0x180028138  test    cl, 1
0x18002813b  jnz     short loc_18002815B
0x18002813d  mov     rax, [rbx+268h]
0x180028144  test    rax, rax
0x180028147  jz      loc_180028256
0x18002814d  mov     eax, [rax+4]
0x180028150  dec     eax
0x180028152  cmp     eax, 1
0x180028155  ja      loc_180028256
0x18002815b  test    cl, 0Ah
0x18002815e  jnz     short loc_1800281AC
0x180028160  test    dil, dil
0x180028163  jnz     short loc_180028179
0x180028165  lea     rcx, [rsp+0B8h+var_70]; this
0x18002816a  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002816f  mov     eax, 8009002Eh
0x180028174  jmp     loc_180028B7F
0x180028179  mov     rcx, [rsp+0B8h]; this
0x180028181  mov     ebx, 80090022h
0x180028186  mov     r9d, ebx; char *
0x180028189  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028190  mov     edx, 0CAEh; void *
0x180028195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002819a  nop
0x18002819b  lea     rcx, [rsp+0B8h+var_70]; this
0x1800281a0  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800281a5  mov     eax, ebx
0x1800281a7  jmp     loc_180028B7F
0x1800281ac  mov     rax, [rbx+268h]
0x1800281b3  test    rax, rax
0x1800281b6  jz      loc_180028256
0x1800281bc  cmp     dword ptr [rax+4], 2
0x1800281c0  jnz     loc_180028256
0x1800281c6  lea     rcx, aUiPolicySetToH; "UI policy set to high protection."
0x1800281cd  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x1800281d2  xorps   xmm0, xmm0
0x1800281d5  xor     eax, eax
0x1800281d7  movups  [rsp+0B8h+var_38], xmm0
0x1800281df  mov     [rsp+0B8h+var_28], eax
0x1800281e6  mov     [rsp+0B8h+cbOutput], r15d
0x1800281eb  lea     rax, [rsp+0B8h+cbOutput]
0x1800281f0  mov     qword ptr [rsp+0B8h+dwFlags], rax; int
0x1800281f5  mov     r9d, 14h
0x1800281fb  lea     r8, [rsp+0B8h+var_38]
0x180028203  lea     edx, [r9+43h]
0x180028207  mov     rcx, [rbx+300h]
0x18002820e  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180028213  test    eax, eax
0x180028215  js      short loc_180028256
0x180028217  mov     [rsp+0B8h+cbOutput], r15d
0x18002821c  mov     ecx, r15d
0x18002821f  mov     eax, ecx
0x180028221  cmp     byte ptr [rsp+rax+0B8h+var_38], r15b
0x180028229  jnz     short loc_180028256
0x18002822b  inc     ecx
0x18002822d  mov     [rsp+0B8h+cbOutput], ecx
0x180028231  cmp     ecx, 14h
0x180028234  jb      short loc_18002821F
0x180028236  cmp     [rbx+268h], r15
0x18002823d  jz      short loc_180028256
0x18002823f  lea     rcx, aAuthvalueIs0Re; "Authvalue is 0, removing UI flag."
0x180028246  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18002824b  mov     rax, [rbx+268h]
0x180028252  mov     [rax+4], r15d
0x180028256  test    byte ptr [rbx+2D0h], 0Ch
0x18002825d  jz      loc_1800289BE
0x180028263  lea     rcx, aKeyArchivalReq; "Key Archival requested."
0x18002826a  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x18002826f  mov     [rsp+0B8h+dwLength], r15d
0x180028274  mov     [rsp+0B8h+var_54], r15d
0x180028279  mov     rdi, [rbx+2C8h]
0x180028280  mov     rdx, rdi; String2
0x180028283  lea     rcx, aRsa; "RSA"
0x18002828a  call    wcscmp_0
0x18002828f  test    eax, eax
0x180028291  jz      loc_180028708
0x180028297  mov     rdx, rdi; String2
0x18002829a  lea     rcx, aRsaSign; "RSA_SIGN"
0x1800282a1  call    wcscmp_0
0x1800282a6  test    eax, eax
0x1800282a8  jz      loc_180028708
0x1800282ae  mov     rdx, rdi; String2
0x1800282b1  lea     rcx, aEcdh; "ECDH"
0x1800282b8  call    wcscmp_0
0x1800282bd  test    eax, eax
0x1800282bf  jz      short loc_1800282D8
0x1800282c1  mov     rdx, rdi; String2
0x1800282c4  lea     rcx, aEcdsa; "ECDSA"
0x1800282cb  call    wcscmp_0
0x1800282d0  test    eax, eax
0x1800282d2  jnz     loc_1800289BE
0x1800282d8  mov     [rsp+0B8h+cbInput], r15d
0x1800282dd  lea     rax, [rsp+0B8h+cbInput]
0x1800282e2  mov     qword ptr [rsp+0B8h+dwFlags], rax; int
0x1800282e7  xor     r9d, r9d
0x1800282ea  xor     r8d, r8d
0x1800282ed  lea     esi, [r9+20h]
0x1800282f1  mov     edx, esi
0x1800282f3  mov     rcx, [rbx+300h]
0x1800282fa  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x1800282ff  mov     edi, eax
0x180028301  test    eax, eax
0x180028303  jns     short loc_180028333
0x180028305  mov     rcx, [rsp+0B8h]; this
0x18002830d  mov     r9d, eax; char *
0x180028310  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028317  mov     edx, 0D0Dh; void *
0x18002831c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028321  nop
0x180028322  lea     rcx, [rsp+0B8h+var_70]; this
0x180028327  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002832c  mov     eax, edi
0x18002832e  jmp     loc_180028B7F
0x180028333  mov     edx, [rsp+0B8h+cbInput]
0x180028337  lea     rcx, [rsp+0B8h+pbInput]
0x18002833c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180028341  nop
0x180028342  mov     rdi, [rsp+0B8h+pbInput]
0x180028347  test    rdi, rdi
0x18002834a  jz      loc_1800286F4
0x180028350  lea     rax, [rsp+0B8h+cbInput]
0x180028355  mov     qword ptr [rsp+0B8h+dwFlags], rax; int
0x18002835a  mov     r9d, [rsp+0B8h+cbInput]
0x18002835f  mov     r8, rdi
0x180028362  mov     edx, esi
0x180028364  mov     rcx, [rbx+300h]
0x18002836b  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180028370  mov     esi, eax
0x180028372  test    eax, eax
0x180028374  jns     short loc_1800283B2
0x180028376  mov     rcx, [rsp+0B8h]; this
0x18002837e  mov     r9d, eax; char *
0x180028381  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028388  mov     edx, 0D13h; void *
0x18002838d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028392  nop
0x180028393  test    rdi, rdi
0x180028396  jz      short loc_1800283A1
0x180028398  mov     rcx, rdi; void *
0x18002839b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800283a0  nop
0x1800283a1  lea     rcx, [rsp+0B8h+var_70]; this
0x1800283a6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800283ab  mov     eax, esi
0x1800283ad  jmp     loc_180028B7F
0x1800283b2  lea     rsi, [rbx+308h]
0x1800283b9  xor     r9d, r9d; dwFlags
0x1800283bc  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800283c3  mov     rdx, [rbx+2C8h]; pszAlgId
0x1800283ca  mov     rcx, rsi; phAlgorithm
0x1800283cd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800283d4  nop     dword ptr [rax+rax+00h]
0x1800283d9  test    eax, eax
0x1800283db  jns     short loc_18002841A
0x1800283dd  mov     rcx, [rsp+0B8h]; this
0x1800283e5  mov     r9d, eax; char *
0x1800283e8  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800283ef  mov     edx, 0D18h; void *
0x1800283f4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800283f9  mov     ebx, eax
0x1800283fb  test    rdi, rdi
0x1800283fe  jz      short loc_180028409
0x180028400  mov     rcx, rdi; void *
0x180028403  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028408  nop
0x180028409  lea     rcx, [rsp+0B8h+var_70]; this
0x18002840e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028413  mov     eax, ebx
0x180028415  jmp     loc_180028B7F
0x18002841a  mov     [rsp+0B8h+dwFlags], r15d; int
0x18002841f  mov     r9d, [rsp+0B8h+cbInput]; cbInput
0x180028424  mov     r8, rdi; pbInput
0x180028427  lea     rdx, aEcccurvename; "ECCCurveName"
0x18002842e  mov     rcx, [rsi]; hObject
0x180028431  call    cs:__imp_BCryptSetProperty
0x180028438  nop     dword ptr [rax+rax+00h]
0x18002843d  test    eax, eax
0x18002843f  jns     short loc_18002847E
0x180028441  mov     rcx, [rsp+0B8h]; this
0x180028449  mov     r9d, eax; char *
0x18002844c  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028453  mov     edx, 0D1Dh; void *
0x180028458  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002845d  mov     ebx, eax
0x18002845f  test    rdi, rdi
0x180028462  jz      short loc_18002846D
0x180028464  mov     rcx, rdi; void *
0x180028467  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002846c  nop
0x18002846d  lea     rcx, [rsp+0B8h+var_70]; this
0x180028472  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028477  mov     eax, ebx
0x180028479  jmp     loc_180028B7F
0x18002847e  lea     r14, [rbx+310h]
0x180028485  xor     r9d, r9d; dwFlags
0x180028488  xor     r8d, r8d; dwLength
0x18002848b  mov     rdx, r14; phKey
0x18002848e  mov     rcx, [rsi]; hAlgorithm
0x180028491  call    cs:__imp_BCryptGenerateKeyPair
0x180028498  nop     dword ptr [rax+rax+00h]
0x18002849d  test    eax, eax
0x18002849f  jns     short loc_1800284DE
0x1800284a1  mov     rcx, [rsp+0B8h]; this
0x1800284a9  mov     r9d, eax; char *
0x1800284ac  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800284b3  mov     edx, 0D21h; void *
0x1800284b8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800284bd  mov     ebx, eax
0x1800284bf  test    rdi, rdi
0x1800284c2  jz      short loc_1800284CD
0x1800284c4  mov     rcx, rdi; void *
0x1800284c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800284cc  nop
0x1800284cd  lea     rcx, [rsp+0B8h+var_70]; this
0x1800284d2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800284d7  mov     eax, ebx
0x1800284d9  jmp     loc_180028B7F
0x1800284de  xor     edx, edx; dwFlags
0x1800284e0  mov     rcx, [r14]; hKey
0x1800284e3  call    cs:__imp_BCryptFinalizeKeyPair
0x1800284ea  nop     dword ptr [rax+rax+00h]
0x1800284ef  test    eax, eax
0x1800284f1  jns     short loc_180028530
0x1800284f3  mov     rcx, [rsp+0B8h]; this
0x1800284fb  mov     r9d, eax; char *
0x1800284fe  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028505  mov     edx, 0D22h; void *
0x18002850a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002850f  mov     ebx, eax
0x180028511  test    rdi, rdi
0x180028514  jz      short loc_18002851F
0x180028516  mov     rcx, rdi; void *
0x180028519  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002851e  nop
0x18002851f  lea     rcx, [rsp+0B8h+var_70]; this
0x180028524  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028529  mov     eax, ebx
0x18002852b  jmp     loc_180028B7F
0x180028530  mov     [rsp+0B8h+cbOutput], r15d
0x180028535  mov     [rsp+0B8h+var_88], r15d; dwFlags
0x18002853a  lea     rax, [rsp+0B8h+cbOutput]
0x18002853f  mov     [rsp+0B8h+pcbResult], rax; pcbResult
0x180028544  mov     [rsp+0B8h+dwFlags], r15d; int
0x180028549  xor     r9d, r9d; pbOutput
0x18002854c  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x180028553  xor     edx, edx; hExportKey
0x180028555  mov     rcx, [r14]; hKey
0x180028558  call    cs:__imp_BCryptExportKey
0x18002855f  nop     dword ptr [rax+rax+00h]
0x180028564  test    eax, eax
0x180028566  jns     short loc_1800285A5
0x180028568  mov     rcx, [rsp+0B8h]; this
0x180028570  mov     r9d, eax; char *
0x180028573  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002857a  mov     edx, 0D2Ch; void *
0x18002857f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180028584  mov     ebx, eax
0x180028586  test    rdi, rdi
0x180028589  jz      short loc_180028594
0x18002858b  mov     rcx, rdi; void *
0x18002858e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028593  nop
0x180028594  lea     rcx, [rsp+0B8h+var_70]; this
0x180028599  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002859e  mov     eax, ebx
  ... truncated ...
```
