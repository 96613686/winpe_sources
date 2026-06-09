# UpdateSSLProperty(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x1800293b0`
- end: `0x180029959`
- name: `?UpdateSSLProperty@@YAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `1449`
- prototype: `__int64 __fastcall(struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180013570`
- `0x180015880`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x18002735c`
- `0x1800273c4`
- `0x180027404`
- `0x18002787c`
- `0x180028654`
- `0x180028ab4`
- `0x1800293b0`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x18002991e`
- `HTTPAPI!HttpTerminate` at `0x18002991e`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x18002986f`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x18002986f`
- `HTTPAPI!HttpInitialize` at `0x180029465`
- `HTTPAPI!HttpInitialize` at `0x180029465`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x18002982d`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x18002982d`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180029537`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800295ba`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180029537`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800295ba`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002956f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002956f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180029588`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002960b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002965e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800296cb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180029788`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180029588`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002960b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002965e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800296cb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180029788`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002966c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029698`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800296a9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029755`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029768`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029778`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002966c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029698`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800296a9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029755`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029768`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029778`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180029556`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180029556`

## string_xrefs

- `0x18002984a`: `HttpDeleteServiceConfiguration failed err=%X\n`
- `0x1800295d8`: `HttpQueryServiceConfiguration failed err=%X\n`
- `0x1800298c7`: `HttpSetServiceConfiguration failed err=%X\n`

## pseudocode

```c
__int64 __fastcall UpdateSSLProperty(struct PROPERTY_ENTRY *a1, struct ABO_NODE *a2)
{
  int v2; // r13d
  struct addrinfoW **v4; // r15
  unsigned int v5; // r12d
  BUFFER *v7; // rsi
  unsigned int v8; // edx
  signed int v9; // eax
  signed int SecureBindings; // ebx
  int v11; // r14d
  ULONG OutputLength; // ecx
  signed int v13; // eax
  BUFFER *v14; // rax
  BUFFER *v15; // rax
  ULONG v16; // edi
  void *pOutput; // rax
  int v18; // edi
  void *Ptr; // rax
  int v20; // eax
  _DWORD *v21; // rax
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v24; // eax
  signed int v25; // eax
  signed int v26; // edi
  __int64 v27; // r8
  ULONG pReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  struct addrinfoW **Block; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v32; // [rsp+50h] [rbp-B0h]
  __int128 pInput; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h]
  struct PROPERTY_ENTRY *v35; // [rsp+70h] [rbp-90h]
  struct addrinfoW *v36; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+88h] [rbp-78h] BYREF
  void *v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+98h] [rbp-68h]
  unsigned __int16 *Str; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B4h] [rbp-4Ch]
  int v43; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v44; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+D0h] [rbp-30h]
  struct addrinfoW *pConfigInformation; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v48[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v49; // [rsp+F8h] [rbp-8h]
  _BYTE v50[56]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v51[48]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v52[56]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v53[56]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v54; // [rsp+218h] [rbp+118h]
  int v55; // [rsp+21Ch] [rbp+11Ch]
  int v56; // [rsp+220h] [rbp+120h]
  int v57; // [rsp+224h] [rbp+124h]
  int v58; // [rsp+228h] [rbp+128h]
  int v59; // [rsp+22Ch] [rbp+12Ch]

  v2 = 0;
  v35 = a1;
  Block = 0;
  v30 = 0;
  v4 = 0;
  v5 = 0;
  SSL_DATA::SSL_DATA((SSL_DATA *)v50);
  pReturnLength = 0;
  pConfigInformation = 0;
  v34 = 0;
  v7 = 0;
  pInput = 0;
  memset_0(v48, 0, 0x50u);
  v36 = 0;
  memset_0(&v37, 0, 0x50u);
  if ( !a1 || !a2 )
  {
    v11 = 0;
    SecureBindings = -2147024809;
    goto LABEL_67;
  }
  v9 = HttpInitialize(g_Version, 2u, 0);
  SecureBindings = v9;
  if ( v9 > 0 )
    SecureBindings = (unsigned __int16)v9 | 0x80070000;
  if ( SecureBindings < 0 )
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpInitialize failed err=%X\n", (unsigned int)SecureBindings);
    goto LABEL_73;
  }
  v11 = 1;
  SecureBindings = GetSecureBindings(a2, &Block, &v30);
  if ( SecureBindings < 0 || (SecureBindings = GetSSLProperties(a2, (struct SSL_DATA *)v50), SecureBindings < 0) )
  {
    v4 = Block;
    v5 = v30;
    goto LABEL_67;
  }
  v5 = v30;
  v4 = Block;
  OutputLength = 0;
  v32 = 0;
  if ( !v30 )
    goto LABEL_67;
  while ( 1 )
  {
    Block = (struct addrinfoW **)v4[v2];
    pInput = 0;
    v34 = 0;
    *((_QWORD *)&pInput + 1) = Block[4];
    v13 = HttpQueryServiceConfiguration(
            0,
            HttpServiceConfigSSLCertInfo,
            &pInput,
            0x18u,
            0,
            OutputLength,
            &pReturnLength,
            0);
    if ( v13 == 122 )
    {
      v14 = (BUFFER *)operator new(0x30u);
      if ( !v14 )
      {
        v7 = 0;
LABEL_58:
        SecureBindings = -2147024888;
        goto LABEL_67;
      }
      v15 = BUFFER::BUFFER(v14);
      v7 = v15;
      if ( !v15 || !BUFFER::Resize(v15, pReturnLength) )
        goto LABEL_58;
      v16 = pReturnLength;
      v32 = pReturnLength;
      pOutput = BUFFER::QueryPtr(v7);
      v13 = HttpQueryServiceConfiguration(
              0,
              HttpServiceConfigSSLCertInfo,
              &pInput,
              0x18u,
              pOutput,
              v16,
              &pReturnLength,
              0);
    }
    v18 = 1;
    if ( v13 )
    {
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpQueryServiceConfiguration failed err=%X\n", (unsigned int)v13);
      v18 = 0;
    }
    v36 = Block[4];
    v39 = xmmword_180034F38;
    if ( v18 )
    {
      Ptr = BUFFER::QueryPtr(v7);
      v37 = *((_DWORD *)Ptr + 2);
      v38 = (void *)*((_QWORD *)Ptr + 2);
      Str = (unsigned __int16 *)*((_QWORD *)Ptr + 5);
      v41 = *((_DWORD *)Ptr + 12);
      v42 = *((_DWORD *)Ptr + 13);
      v43 = *((_DWORD *)Ptr + 14);
      v44 = *((_QWORD *)Ptr + 8);
      v45 = *((_QWORD *)Ptr + 9);
      v20 = *((_DWORD *)Ptr + 20);
    }
    else
    {
      v37 = v59;
      v38 = BUFFER::QueryPtr((BUFFER *)v51);
      Str = STRU::QueryStr((STRU *)v50);
      v41 = v54;
      v42 = v57;
      v43 = v58;
      v44 = (unsigned __int64)STRU::QueryStr((STRU *)v52);
      v45 = (unsigned __int64)STRU::QueryStr((STRU *)v53);
      v20 = v56 | v55;
    }
    v46 = v20;
    v21 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v35 + 16));
    switch ( *v21 )
    {
      case 0x870:
        v41 = v54;
        break;
      case 0x871:
        v42 = v57;
        break;
      case 0x872:
        v43 = v58;
        break;
      case 0x1582:
        v38 = BUFFER::QueryPtr((BUFFER *)v51);
        v37 = v59;
        break;
      case 0x1587:
        Str = STRU::QueryStr((STRU *)v50);
        break;
      case 0x1588:
        v44 = (unsigned __int64)STRU::QueryStr((STRU *)v52);
        break;
      case 0x158D:
        v45 = (unsigned __int64)STRU::QueryStr((STRU *)v53);
        break;
      case 0x158F:
        v24 = v46 & 0xFFFFFFFE;
        v46 &= ~1u;
        if ( !v55 )
          break;
        v23 = v24 | 1;
        goto LABEL_35;
      case 0x1591:
        v22 = v46 & 0xFFFFFFFD;
        v46 &= ~2u;
        if ( v56 )
        {
          v23 = v22 | 2;
LABEL_35:
          v46 = v23;
        }
        break;
    }
    if ( v44 )
      v44 &= -(__int64)(*(_WORD *)v44 != 0);
    if ( v45 )
      v45 &= -(__int64)(*(_WORD *)v45 != 0);
    if ( v18 )
    {
      pConfigInformation = Block[4];
      v49 = xmmword_180034F38;
      v25 = HttpDeleteServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
      if ( v25 )
      {
        if ( v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpDeleteServiceConfiguration failed err=%X\n", (unsigned int)v25);
      }
    }
    v26 = HttpSetServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &v36, 0x58u, 0);
    if ( v26 )
      break;
    if ( v7 )
    {
      BUFFER::`scalar deleting destructor'(v7, v8);
      v7 = 0;
    }
    if ( ++v2 >= v5 )
      goto LABEL_67;
    OutputLength = v32;
  }
  if ( v26 > 0 )
    v27 = (unsigned __int16)v26 | 0x80070000;
  else
    v27 = (unsigned int)v26;
  ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpSetServiceConfiguration failed err=%X\n", v27);
  if ( v26 > 0 )
    SecureBindings = (unsigned __int16)v26 | 0x80070000;
  else
    SecureBindings = v26;
LABEL_67:
  if ( v4 )
    FreeSecureBindings(v4, v5);
  if ( v7 )
    BUFFER::`scalar deleting destructor'(v7, v8);
  if ( v11 )
    HttpTerminate(2u, 0);
LABEL_73:
  SSL_DATA::~SSL_DATA((SSL_DATA *)v50);
  return (unsigned int)SecureBindings;
}

```

## disassembly

```asm
0x1800293b0  mov     [rsp-8+arg_10], rbx
0x1800293b5  push    rbp
0x1800293b6  push    rsi
0x1800293b7  push    rdi
0x1800293b8  push    r12
0x1800293ba  push    r13
0x1800293bc  push    r14
0x1800293be  push    r15
0x1800293c0  lea     rbp, [rsp-140h]
0x1800293c8  sub     rsp, 240h
0x1800293cf  mov     rax, cs:__security_cookie
0x1800293d6  xor     rax, rsp
0x1800293d9  mov     [rbp+170h+var_40], rax
0x1800293e0  xor     r13d, r13d
0x1800293e3  mov     [rsp+270h+var_200], rcx
0x1800293e8  mov     rbx, rcx
0x1800293eb  mov     [rsp+270h+Block], r13
0x1800293f0  lea     rcx, [rbp+170h+var_130]; this
0x1800293f4  mov     [rsp+270h+var_22C], r13d
0x1800293f9  mov     r15d, r13d
0x1800293fc  mov     r12d, r13d
0x1800293ff  mov     rdi, rdx
0x180029402  call    ??0SSL_DATA@@QEAA@XZ; SSL_DATA::SSL_DATA(void)
0x180029407  xorps   xmm0, xmm0
0x18002940a  mov     [rsp+270h+var_230], r13d
0x18002940f  xor     eax, eax
0x180029411  mov     [rbp+170h+pConfigInformation], r13
0x180029415  lea     r14d, [r13+50h]
0x180029419  mov     [rsp+270h+var_208], rax
0x18002941e  mov     r8d, r14d; Size
0x180029421  lea     rcx, [rbp+170h+var_188]; void *
0x180029425  xor     edx, edx; Val
0x180029427  mov     esi, r13d
0x18002942a  movups  [rsp+270h+pInput], xmm0
0x18002942f  call    memset_0
0x180029434  mov     r8d, r14d; Size
0x180029437  mov     [rbp+170h+var_1F0], r13
0x18002943b  xor     edx, edx; Val
0x18002943d  lea     rcx, [rbp+170h+var_1E8]; void *
0x180029441  call    memset_0
0x180029446  test    rbx, rbx
0x180029449  jz      loc_1800298EF
0x18002944f  test    rdi, rdi
0x180029452  jz      loc_1800298EF
0x180029458  mov     ecx, dword ptr cs:?g_Version@@3U_HTTPAPI_VERSION@@A.HttpApiMajorVersion; Version
0x18002945e  lea     edx, [r13+2]; Flags
0x180029462  xor     r8d, r8d; pReserved
0x180029465  call    cs:__imp_HttpInitialize
0x18002946b  mov     ebx, eax
0x18002946d  test    eax, eax
0x18002946f  jle     short loc_18002947A
0x180029471  movzx   ebx, ax
0x180029474  or      ebx, 80070000h
0x18002947a  test    ebx, ebx
0x18002947c  jns     short loc_180029499
0x18002947e  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180029485  lea     rdx, aHttpinitialize; "HttpInitialize failed err=%X\n"
0x18002948c  mov     r8d, ebx
0x18002948f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180029494  jmp     loc_180029924
0x180029499  lea     r8, [rsp+270h+var_22C]; unsigned int *
0x18002949e  mov     rcx, rdi; struct ABO_NODE *
0x1800294a1  lea     rdx, [rsp+270h+Block]; struct addrinfoW ***
0x1800294a6  mov     r14d, 1
0x1800294ac  call    ?GetSecureBindings@@YAJPEAVABO_NODE@@PEAPEAPEAUaddrinfoW@@PEAK@Z; GetSecureBindings(ABO_NODE *,addrinfoW * * *,ulong *)
0x1800294b1  mov     ebx, eax
0x1800294b3  test    eax, eax
0x1800294b5  js      loc_1800298E3
0x1800294bb  lea     rdx, [rbp+170h+var_130]; struct SSL_DATA *
0x1800294bf  mov     rcx, rdi; struct ABO_NODE *
0x1800294c2  call    ?GetSSLProperties@@YAJPEAVABO_NODE@@PEAUSSL_DATA@@@Z; GetSSLProperties(ABO_NODE *,SSL_DATA *)
0x1800294c7  mov     ebx, eax
0x1800294c9  test    eax, eax
0x1800294cb  js      loc_1800298E3
0x1800294d1  mov     r12d, [rsp+270h+var_22C]
0x1800294d6  xor     edi, edi
0x1800294d8  mov     r15, [rsp+270h+Block]
0x1800294dd  mov     ecx, r13d
0x1800294e0  mov     [rsp+270h+var_220], ecx
0x1800294e4  test    r12d, r12d
0x1800294e7  jz      loc_1800298F7
0x1800294ed  xor     edx, edx
0x1800294ef  mov     [rsp+270h+pOverlapped], rdi; pOverlapped
0x1800294f4  xorps   xmm0, xmm0
0x1800294f7  mov     eax, r13d
0x1800294fa  lea     r8, [rsp+270h+pInput]; pInput
0x1800294ff  lea     r9d, [rdx+18h]; InputLength
0x180029503  mov     rax, [r15+rax*8]
0x180029507  mov     [rsp+270h+Block], rax
0x18002950c  movups  [rsp+270h+pInput], xmm0
0x180029511  mov     [rsp+270h+var_208], rdx
0x180029516  mov     edx, r14d; ConfigId
0x180029519  mov     rax, [rax+20h]
0x18002951d  mov     qword ptr [rsp+270h+pInput+8], rax
0x180029522  lea     rax, [rsp+270h+var_230]
0x180029527  mov     [rsp+270h+pReturnLength], rax; pReturnLength
0x18002952c  mov     [rsp+270h+OutputLength], ecx; OutputLength
0x180029530  xor     ecx, ecx; ServiceHandle
0x180029532  mov     [rsp+270h+pOutput], rdi; pOutput
0x180029537  call    cs:__imp_HttpQueryServiceConfiguration
0x18002953d  cmp     eax, 7Ah ; 'z'
0x180029540  jnz     short loc_1800295C0
0x180029542  lea     ecx, [rax-4Ah]; Size
0x180029545  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002954a  test    rax, rax
0x18002954d  jz      loc_18002989D
0x180029553  mov     rcx, rax
0x180029556  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18002955c  mov     rsi, rax
0x18002955f  test    rax, rax
0x180029562  jz      loc_1800298A3
0x180029568  mov     edx, [rsp+270h+var_230]
0x18002956c  mov     rcx, rax
0x18002956f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180029575  test    al, al
0x180029577  jz      loc_1800298A3
0x18002957d  mov     edi, [rsp+270h+var_230]
0x180029581  mov     rcx, rsi
0x180029584  mov     [rsp+270h+var_220], edi
0x180029588  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002958e  mov     [rsp+270h+pOverlapped], 0; pOverlapped
0x180029597  lea     rcx, [rsp+270h+var_230]
0x18002959c  mov     [rsp+270h+pReturnLength], rcx; pReturnLength
0x1800295a1  lea     r8, [rsp+270h+pInput]; pInput
0x1800295a6  mov     [rsp+270h+OutputLength], edi; OutputLength
0x1800295aa  xor     ecx, ecx; ServiceHandle
0x1800295ac  mov     r9d, 18h; InputLength
0x1800295b2  mov     [rsp+270h+pOutput], rax; pOutput
0x1800295b7  mov     edx, r14d; ConfigId
0x1800295ba  call    cs:__imp_HttpQueryServiceConfiguration
0x1800295c0  mov     edi, r14d
0x1800295c3  test    eax, eax
0x1800295c5  jz      short loc_1800295EB
0x1800295c7  jle     short loc_1800295D1
0x1800295c9  movzx   eax, ax
0x1800295cc  or      eax, 80070000h
0x1800295d1  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800295d8  lea     rdx, aHttpqueryservi; "HttpQueryServiceConfiguration failed er"...
0x1800295df  mov     r8d, eax
0x1800295e2  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800295e7  xor     ecx, ecx
0x1800295e9  mov     edi, ecx
0x1800295eb  mov     rax, [rsp+270h+Block]
0x1800295f0  movups  xmm0, cs:xmmword_180034F38
0x1800295f7  mov     rax, [rax+20h]
0x1800295fb  mov     [rbp+170h+var_1F0], rax
0x1800295ff  movdqu  [rbp+170h+var_1D8], xmm0
0x180029604  test    edi, edi
0x180029606  jz      short loc_180029651
0x180029608  mov     rcx, rsi
0x18002960b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180029611  mov     rdx, rax
0x180029614  mov     ecx, [rax+8]
0x180029617  mov     [rbp+170h+var_1E8], ecx
0x18002961a  mov     rcx, [rax+10h]
0x18002961e  mov     [rbp+170h+var_1E0], rcx
0x180029622  mov     rcx, [rax+28h]
0x180029626  mov     [rbp+170h+var_1C8], rcx
0x18002962a  mov     ecx, [rax+30h]
0x18002962d  mov     [rbp+170h+var_1C0], ecx
0x180029630  mov     ecx, [rax+34h]
0x180029633  mov     [rbp+170h+var_1BC], ecx
0x180029636  mov     ecx, [rax+38h]
0x180029639  mov     [rbp+170h+var_1B8], ecx
0x18002963c  mov     rcx, [rax+40h]
0x180029640  mov     [rbp+170h+var_1B0], rcx
0x180029644  mov     rax, [rax+48h]
0x180029648  mov     [rbp+170h+var_1A8], rax
0x18002964c  mov     eax, [rdx+50h]
0x18002964f  jmp     short loc_1800296BF
0x180029651  mov     eax, [rbp+170h+var_44]
0x180029657  lea     rcx, [rbp+170h+var_F8]
0x18002965b  mov     [rbp+170h+var_1E8], eax
0x18002965e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180029664  lea     rcx, [rbp+170h+var_130]
0x180029668  mov     [rbp+170h+var_1E0], rax
0x18002966c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180029672  mov     [rbp+170h+var_1C8], rax
0x180029676  lea     rcx, [rbp+170h+var_C8]
0x18002967d  mov     eax, [rbp+170h+var_58]
0x180029683  mov     [rbp+170h+var_1C0], eax
0x180029686  mov     eax, [rbp+170h+var_4C]
0x18002968c  mov     [rbp+170h+var_1BC], eax
0x18002968f  mov     eax, [rbp+170h+var_48]
0x180029695  mov     [rbp+170h+var_1B8], eax
0x180029698  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002969e  lea     rcx, [rbp+170h+var_90]
0x1800296a5  mov     [rbp+170h+var_1B0], rax
0x1800296a9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800296af  mov     [rbp+170h+var_1A8], rax
0x1800296b3  mov     eax, dword ptr [rbp+170h+var_54]
0x1800296b9  or      eax, dword ptr [rbp+170h+var_54+4]
0x1800296bf  mov     rcx, [rsp+270h+var_200]
0x1800296c4  add     rcx, 10h
0x1800296c8  mov     [rbp+170h+var_1A0], eax
0x1800296cb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800296d1  mov     edx, [rax]
0x1800296d3  sub     edx, 870h
0x1800296d9  jz      loc_1800297B3
0x1800296df  sub     edx, r14d
0x1800296e2  jz      loc_1800297A8
0x1800296e8  sub     edx, r14d
0x1800296eb  jz      loc_18002979D
0x1800296f1  sub     edx, 0D10h
0x1800296f7  jz      loc_180029784
0x1800296fd  sub     edx, 5
0x180029700  jz      short loc_180029774
0x180029702  sub     edx, r14d
0x180029705  jz      short loc_180029761
0x180029707  sub     edx, 5
0x18002970a  jz      short loc_18002974E
0x18002970c  sub     edx, 2
0x18002970f  jz      short loc_180029734
0x180029711  cmp     edx, 2
0x180029714  jnz     loc_1800297BC
0x18002971a  mov     eax, [rbp+170h+var_1A0]
0x18002971d  and     eax, 0FFFFFFFDh
0x180029720  cmp     dword ptr [rbp+170h+var_54+4], 0
0x180029727  mov     [rbp+170h+var_1A0], eax
0x18002972a  jz      loc_1800297BC
0x180029730  or      eax, edx
0x180029732  jmp     short loc_180029749
0x180029734  mov     eax, [rbp+170h+var_1A0]
0x180029737  and     eax, 0FFFFFFFEh
0x18002973a  cmp     dword ptr [rbp+170h+var_54], 0
0x180029741  mov     [rbp+170h+var_1A0], eax
0x180029744  jz      short loc_1800297BC
0x180029746  or      eax, r14d
0x180029749  mov     [rbp+170h+var_1A0], eax
0x18002974c  jmp     short loc_1800297BC
0x18002974e  lea     rcx, [rbp+170h+var_90]
0x180029755  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002975b  mov     [rbp+170h+var_1A8], rax
0x18002975f  jmp     short loc_1800297BC
0x180029761  lea     rcx, [rbp+170h+var_C8]
0x180029768  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002976e  mov     [rbp+170h+var_1B0], rax
0x180029772  jmp     short loc_1800297BC
0x180029774  lea     rcx, [rbp+170h+var_130]
0x180029778  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002977e  mov     [rbp+170h+var_1C8], rax
0x180029782  jmp     short loc_1800297BC
0x180029784  lea     rcx, [rbp+170h+var_F8]
0x180029788  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002978e  mov     [rbp+170h+var_1E0], rax
0x180029792  mov     eax, [rbp+170h+var_44]
0x180029798  mov     [rbp+170h+var_1E8], eax
0x18002979b  jmp     short loc_1800297BC
0x18002979d  mov     eax, [rbp+170h+var_48]
0x1800297a3  mov     [rbp+170h+var_1B8], eax
0x1800297a6  jmp     short loc_1800297BC
0x1800297a8  mov     eax, [rbp+170h+var_4C]
0x1800297ae  mov     [rbp+170h+var_1BC], eax
0x1800297b1  jmp     short loc_1800297BC
0x1800297b3  mov     eax, [rbp+170h+var_58]
0x1800297b9  mov     [rbp+170h+var_1C0], eax
0x1800297bc  mov     rax, [rbp+170h+var_1B0]
0x1800297c0  xor     ecx, ecx; ServiceHandle
0x1800297c2  test    rax, rax
0x1800297c5  jz      short loc_1800297DE
0x1800297c7  cmp     [rax], cx
0x1800297ca  jnz     short loc_1800297D0
0x1800297cc  mov     eax, ecx
0x1800297ce  jmp     short loc_1800297D5
0x1800297d0  sbb     eax, eax
0x1800297d2  or      eax, r14d
0x1800297d5  neg     eax
0x1800297d7  sbb     rax, rax
0x1800297da  and     [rbp+170h+var_1B0], rax
0x1800297de  mov     rax, [rbp+170h+var_1A8]
0x1800297e2  test    rax, rax
0x1800297e5  jz      short loc_1800297FE
0x1800297e7  cmp     [rax], cx
0x1800297ea  jnz     short loc_1800297F0
0x1800297ec  mov     eax, ecx
0x1800297ee  jmp     short loc_1800297F5
0x1800297f0  sbb     eax, eax
0x1800297f2  or      eax, r14d
0x1800297f5  neg     eax
0x1800297f7  sbb     rax, rax
0x1800297fa  and     [rbp+170h+var_1A8], rax
0x1800297fe  test    edi, edi
0x180029800  jz      short loc_18002985B
0x180029802  movups  xmm0, cs:xmmword_180034F38
0x180029809  mov     rax, [rsp+270h+Block]
0x18002980e  lea     r8, [rbp+170h+pConfigInformation]; pConfigInformation
0x180029812  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x180029818  mov     [rsp+270h+pOutput], rcx; pOverlapped
0x18002981d  mov     edx, r14d; ConfigId
0x180029820  mov     rax, [rax+20h]
0x180029824  mov     [rbp+170h+pConfigInformation], rax
0x180029828  movdqu  [rbp+170h+var_178], xmm0
0x18002982d  call    cs:__imp_HttpDeleteServiceConfiguration
0x180029833  xor     ecx, ecx
0x180029835  test    eax, eax
0x180029837  jz      short loc_18002985B
0x180029839  jle     short loc_180029843
0x18002983b  movzx   eax, ax
0x18002983e  or      eax, 80070000h
0x180029843  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
  ... truncated ...
```
