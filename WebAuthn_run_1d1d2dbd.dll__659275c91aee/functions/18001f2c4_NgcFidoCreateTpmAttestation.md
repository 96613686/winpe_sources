# _NgcFidoCreateTpmAttestation

- ea: `0x18001f2c4`
- end: `0x18001f8d4`
- name: `_NgcFidoCreateTpmAttestation`
- size: `1552`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180089b74`

## callees

- `0x18001687c`
- `0x18001d8f4`
- `0x18001f2c4`
- `0x1800205c4`
- `0x1800205e4`
- `0x18002a2f0`
- `0x18002bbf4`
- `0x180031708`
- `0x180036dc8`
- `0x18004bcf0`
- `0x1800537a4`
- `0x18007c3ac`
- `0x180081470`
- `0x1800ca4e4`
- `0x1800d3418`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f63f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f655`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f66b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f87d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f893`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f63f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f655`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f66b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f87d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f893`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8a9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001f601`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001f601`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f685`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f685`
- `CRYPT32!CertGetCertificateChain` at `0x18001f712`
- `CRYPT32!CertGetCertificateChain` at `0x18001f712`
- `CRYPT32!CertCreateCertificateContext` at `0x18001f5a6`
- `CRYPT32!CertCreateCertificateContext` at `0x18001f5a6`
- `popkeycli!NgcRenewKeyAttestation` at `0x18001f69b`
- `popkeycli!NgcRenewKeyAttestation` at `0x18001f69b`

## string_xrefs

- `0x18001f3ab`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18001f404`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18001f4ea`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18001f612`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18001f736`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18001f835`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcFidoCreateTpmAttestation(
        __int64 a1,
        const WCHAR *a2,
        HWND a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _QWORD *a8,
        _DWORD *a9)
{
  const CERT_CONTEXT *v13; // rbx
  __int64 v14; // rcx
  __int64 PublicKeyInfoByCoseAlg; // rsi
  int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // eax
  wil::details::in1diag3 *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // ecx
  __int64 v22; // r8
  char *v23; // r10
  unsigned int v24; // ecx
  __int64 v25; // r9
  char *v26; // r8
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  const char *v29; // r9
  unsigned int v30; // ebx
  BYTE *v31; // rcx
  HLOCAL v32; // rcx
  HLOCAL v33; // rcx
  __int64 v35; // rdx
  int NonzeroLastError; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // r8
  _QWORD *v42; // r9
  unsigned int v43; // r10d
  __int64 v44; // r11
  __int64 v45; // rcx
  int v46; // ebx
  HLOCAL v47; // rax
  BYTE *v48; // rcx
  HLOCAL v49; // rcx
  HLOCAL v50; // rcx
  int pChainPara; // [rsp+20h] [rbp-E0h]
  int pChainParaa; // [rsp+20h] [rbp-E0h]
  int pChainParab; // [rsp+20h] [rbp-E0h]
  DWORD cbCertEncoded[2]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v55; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *pbCertEncoded; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v58; // [rsp+60h] [rbp-A0h] BYREF
  int v59; // [rsp+64h] [rbp-9Ch] BYREF
  const CERT_CONTEXT *v60; // [rsp+68h] [rbp-98h] BYREF
  __int128 v61; // [rsp+70h] [rbp-90h] BYREF
  void *p_pbCertEncoded; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v63; // [rsp+88h] [rbp-78h] BYREF
  char v64; // [rsp+90h] [rbp-70h]
  struct _BCryptBufferDesc v65; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v66; // [rsp+A8h] [rbp-58h]
  _QWORD *v67; // [rsp+B0h] [rbp-50h]
  _DWORD v68[6]; // [rsp+C0h] [rbp-40h] BYREF
  char *v69; // [rsp+D8h] [rbp-28h]
  int v70; // [rsp+E0h] [rbp-20h]
  int *v71; // [rsp+E8h] [rbp-18h]
  const wchar_t *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  char *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  char *v76; // [rsp+110h] [rbp+10h]
  struct _CERT_CHAIN_PARA v77; // [rsp+120h] [rbp+20h] BYREF
  int v78; // [rsp+158h] [rbp+58h]
  SYSTEMTIME SystemTime; // [rsp+180h] [rbp+80h] BYREF
  char v80; // [rsp+190h] [rbp+90h]
  int v81; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v82[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v83; // [rsp+1D8h] [rbp+D8h]
  char v84; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v67 = a8;
  v66 = a9;
  v59 = 0;
  v55 = 0;
  v58 = 0;
  hMem = 0;
  cbCertEncoded[0] = 0;
  pbCertEncoded = 0;
  v13 = 0;
  v60 = 0;
  LODWORD(v61) = 0;
  memset((char *)&v61 + 4, 0, 12);
  v65 = 0;
  memset_0(v68, 0, 0x58u);
  v81 = 0;
  memset(v82, 0, sizeof(v82));
  v83 = 0;
  PublicKeyInfoByCoseAlg = CtapCborFindPublicKeyInfoByCoseAlg(4294901761LL);
  if ( !PublicKeyInfoByCoseAlg )
  {
    v16 = -2146893783;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x4A2,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090029LL,
      pChainPara);
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v60);
    v48 = pbCertEncoded;
    pbCertEncoded = 0;
    if ( v48 )
      LocalFree(v48);
    v49 = hMem;
    hMem = 0;
    if ( v49 )
      LocalFree(v49);
    v50 = v55;
    v55 = 0;
    if ( v50 )
      LocalFree(v50);
    return (unsigned int)v16;
  }
  v17 = CtapCborHashAuthenticatorDataAndClientDataHashSignature(v14, PublicKeyInfoByCoseAlg, a5, a4);
  v16 = v17;
  if ( v17 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v17,
      a7);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_49;
  }
  v18 = *(_DWORD *)(PublicKeyInfoByCoseAlg + 48);
  if ( v18 > 0x40 )
    v18 = 64;
  *((_QWORD *)&v61 + 1) = &v84;
  *(_QWORD *)&v61 = v18 | 0x3100000000LL;
  v65.ulVersion = 0;
  v65.cBuffers = 1;
  v65.pBuffers = (PBCryptBuffer)&v61;
  p_pbCertEncoded = &pbCertEncoded;
  v63 = 0;
  v64 = 1;
  *(_QWORD *)&SystemTime.wYear = &hMem;
  *(_QWORD *)&SystemTime.wHour = 0;
  v80 = 1;
  v16 = WebAuthNGetKeyAttestationForUserIdKey(a2, a3, &v65, (HLOCAL *)&SystemTime.wHour, &v58, &v63, cbCertEncoded);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&SystemTime);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pbCertEncoded);
  v19 = retaddr;
  if ( v16 < 0 )
  {
    v20 = 1215;
LABEL_10:
    wil::details::in1diag3::_Log_Hr(
      v19,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)v16,
      pChainParaa);
    goto LABEL_49;
  }
  v68[0] = 1;
  v68[4] = -65535;
  v72 = L"2.0";
  if ( v58 < 0x18 || *((_DWORD *)hMem + 2) > v58 )
    goto LABEL_30;
  v21 = v58 - *((_DWORD *)hMem + 2);
  if ( v16 )
    goto LABEL_31;
  v22 = *((unsigned int *)hMem + 3);
  if ( v21 < (unsigned int)v22 )
    goto LABEL_30;
  v23 = (char *)hMem + *((unsigned int *)hMem + 2);
  v73 = *((_DWORD *)hMem + 3);
  v74 = v23;
  v24 = v21 - v22;
  v25 = *((unsigned int *)hMem + 4);
  if ( v24 < (unsigned int)v25
    || (v26 = &v23[v22], v68[5] = *((_DWORD *)hMem + 4), v69 = v26, v24 - (unsigned int)v25 < *((_DWORD *)hMem + 5)) )
  {
LABEL_30:
    v16 = -2146893819;
    goto LABEL_31;
  }
  v75 = *((_DWORD *)hMem + 5);
  v76 = &v26[v25];
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded[0]);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
    &v60,
    CertificateContext);
  v13 = v60;
  if ( !v60 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
  }
  *(_QWORD *)cbCertEncoded = 0;
  *(_DWORD *)&SystemTime.wYear = 526309;
  *(_QWORD *)&SystemTime.wDayOfWeek = 1310725;
  *(_DWORD *)&SystemTime.wSecond = 0;
  if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)cbCertEncoded) )
  {
    if ( CompareFileTime(&v13->pCertInfo->NotBefore, (const FILETIME *)cbCertEncoded) < 0 )
    {
      NgcRenewKeyAttestation(*(_QWORD *)(a1 + 8), 0, 0, 0);
      v16 = -2146885616;
    }
LABEL_31:
    v19 = retaddr;
    if ( v16 < 0 )
    {
      v20 = 1312;
      goto LABEL_10;
    }
    memset_0(&v77, 0, 0x60u);
    v77.cbSize = 96;
    v78 = 5000;
    *(_QWORD *)cbCertEncoded = 0;
    if ( !CertGetCertificateChain((HCERTCHAINENGINE)1, v13, 0, 0, &v77, 0, 0, (PCCERT_CHAIN_CONTEXT *)cbCertEncoded) )
    {
      NonzeroLastError = _GetNonzeroLastError();
      v16 = NonzeroLastError;
      if ( NonzeroLastError > 0 )
        v16 = (unsigned __int16)NonzeroLastError | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x534,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)v16,
        pChainParab);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>(
        cbCertEncoded,
        v37,
        v38,
        v39);
      goto LABEL_49;
    }
    v40 = *(_QWORD *)(*(_QWORD *)cbCertEncoded + 16LL);
    v41 = *(unsigned int *)(*(_QWORD *)v40 + 12LL);
    v42 = (_QWORD *)(*(_QWORD *)v40 + 16LL);
    if ( (unsigned int)v41 > 1 )
    {
      v35 = (unsigned int)(v41 - 1);
      if ( (*(_BYTE *)(*(_QWORD *)(*v42 + 8 * v35) + 20LL) & 8) == 0 )
        v35 = (unsigned int)v41;
      v41 = 4;
      if ( (unsigned int)v35 > 4 )
      {
        v43 = 0;
        goto LABEL_44;
      }
      v41 = (unsigned int)v35;
    }
    v43 = 0;
    if ( !(_DWORD)v41 )
    {
LABEL_46:
      v70 = v41;
      v71 = &v81;
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&void CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>(
        cbCertEncoded,
        v35,
        v41,
        v42);
      p_pbCertEncoded = &v55;
      v63 = 0;
      v64 = 1;
      v46 = CtapCborEncodeCommonAttestation(v68, &v59, &v63, cbCertEncoded);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pbCertEncoded);
      if ( v46 )
      {
        v16 = -2147418113;
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x55B,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          (const char *)0x8000FFFFLL,
          pChainParab);
      }
      else
      {
        *v66 = v59;
        v47 = v55;
        v55 = 0;
        *v67 = v47;
      }
      goto LABEL_49;
    }
LABEL_44:
    v44 = 0;
    do
    {
      v35 = *(_QWORD *)(*(_QWORD *)(*v42 + 8 * v44) + 8LL);
      v45 = v44;
      LODWORD(v82[v45]) = *(_DWORD *)(v35 + 16);
      *(_QWORD *)&v82[v45] = *(_QWORD *)(v35 + 8);
      ++v43;
      ++v44;
    }
    while ( v43 < (unsigned int)v41 );
    goto LABEL_46;
  }
  v30 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x50E,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          v29);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v60);
  v31 = pbCertEncoded;
  pbCertEncoded = 0;
  if ( v31 )
    LocalFree(v31);
  v32 = hMem;
  hMem = 0;
  if ( v32 )
    LocalFree(v32);
  v33 = v55;
  v55 = 0;
  if ( v33 )
    LocalFree(v33);
  return v30;
}

```

## disassembly

```asm
0x18001f2c4  push    rbp
0x18001f2c6  push    rbx
0x18001f2c7  push    rsi
0x18001f2c8  push    rdi
0x18001f2c9  push    r12
0x18001f2cb  push    r13
0x18001f2cd  push    r14
0x18001f2cf  push    r15
0x18001f2d1  lea     rbp, [rsp-138h]
0x18001f2d9  sub     rsp, 238h
0x18001f2e0  mov     rax, cs:__security_cookie
0x18001f2e7  xor     rax, rsp
0x18001f2ea  mov     [rbp+170h+var_50], rax
0x18001f2f1  mov     rdi, r9
0x18001f2f4  mov     r12, r8
0x18001f2f7  mov     r15, rdx
0x18001f2fa  mov     r13, rcx
0x18001f2fd  mov     r14, [rbp+170h+arg_28]
0x18001f304  mov     rax, [rbp+170h+arg_38]
0x18001f30b  mov     [rbp+170h+var_1C0], rax
0x18001f30f  mov     rax, [rbp+170h+arg_40]
0x18001f316  mov     [rbp+170h+var_1C8], rax
0x18001f31a  xor     esi, esi
0x18001f31c  mov     [rsp+270h+var_20C], esi
0x18001f320  mov     [rsp+270h+var_228], rsi
0x18001f325  mov     [rsp+270h+var_210], esi
0x18001f329  mov     [rsp+270h+hMem], rsi
0x18001f32e  mov     [rsp+270h+cbCertEncoded], esi
0x18001f332  mov     [rsp+270h+pbCertEncoded], rsi
0x18001f337  mov     ebx, esi
0x18001f339  mov     [rsp+270h+var_208], rbx
0x18001f33e  mov     [rsp+270h+var_200], esi
0x18001f342  xor     eax, eax
0x18001f344  mov     [rsp+270h+var_1FC], rax
0x18001f349  mov     [rsp+270h+var_1F4], eax
0x18001f34d  xorps   xmm0, xmm0
0x18001f350  movups  xmmword ptr [rbp+170h+var_1D8.ulVersion], xmm0
0x18001f354  xor     edx, edx; Val
0x18001f356  lea     r8d, [rsi+58h]; Size
0x18001f35a  lea     rcx, [rbp+170h+var_1B0]; void *
0x18001f35e  call    memset_0
0x18001f363  mov     [rbp+170h+var_D0], esi
0x18001f369  xorps   xmm0, xmm0
0x18001f36c  xor     eax, eax
0x18001f36e  movups  [rbp+170h+var_C8], xmm0
0x18001f375  movups  [rbp+170h+var_B8], xmm0
0x18001f37c  movups  [rbp+170h+var_A8], xmm0
0x18001f383  mov     [rbp+170h+var_98], rax
0x18001f38a  mov     ecx, 0FFFF0001h
0x18001f38f  call    CtapCborFindPublicKeyInfoByCoseAlg
0x18001f394  mov     rsi, rax
0x18001f397  test    rax, rax
0x18001f39a  jnz     short loc_18001F3C4
0x18001f39c  mov     edi, 80090029h
0x18001f3a1  mov     rcx, [rbp+178h]; this
0x18001f3a8  mov     r9d, edi; char *
0x18001f3ab  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f3b2  mov     edx, 4A2h; void *
0x18001f3b7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001f3bc  xor     r14d, r14d
0x18001f3bf  jmp     loc_18001F863
0x18001f3c4  lea     rax, [rbp+170h+var_90]
0x18001f3cb  mov     [rsp+270h+pvReserved], rax
0x18001f3d0  mov     qword ptr [rsp+270h+dwFlags], r14
0x18001f3d5  mov     eax, [rbp+170h+arg_30]
0x18001f3db  mov     dword ptr [rsp+270h+pChainPara], eax; unsigned int
0x18001f3df  mov     r9, rdi
0x18001f3e2  mov     r8d, [rbp+170h+arg_20]
0x18001f3e9  mov     rdx, rsi
0x18001f3ec  call    CtapCborHashAuthenticatorDataAndClientDataHashSignature
0x18001f3f1  mov     edi, eax
0x18001f3f3  mov     rcx, [rbp+178h]; this
0x18001f3fa  xor     r14d, r14d
0x18001f3fd  test    eax, eax
0x18001f3ff  jz      short loc_18001F42B
0x18001f401  mov     r9d, eax; char *
0x18001f404  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f40b  mov     edx, 4ABh; void *
0x18001f410  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001f415  test    edi, edi
0x18001f417  jle     loc_18001F863
0x18001f41d  movzx   edi, di
0x18001f420  or      edi, 80070000h
0x18001f426  jmp     loc_18001F863
0x18001f42b  mov     eax, [rsi+30h]
0x18001f42e  mov     ecx, 40h ; '@'
0x18001f433  cmp     eax, ecx
0x18001f435  cmova   eax, ecx
0x18001f438  mov     dword ptr [rsp+270h+var_1FC], 31h ; '1'
0x18001f440  lea     rcx, [rbp+170h+var_90]
0x18001f447  mov     [rsp+270h+var_1FC+4], rcx
0x18001f44c  mov     [rsp+270h+var_200], eax
0x18001f450  mov     [rbp+170h+var_1D8.ulVersion], r14d
0x18001f454  mov     [rbp+170h+var_1D8.cBuffers], 1
0x18001f45b  lea     rax, [rsp+270h+var_200]
0x18001f460  mov     [rbp+170h+var_1D8.pBuffers], rax
0x18001f464  lea     rax, [rsp+270h+pbCertEncoded]
0x18001f469  mov     [rbp+170h+var_1F0], rax
0x18001f46d  mov     [rbp+170h+var_1E8], r14
0x18001f471  mov     [rbp+170h+var_1E0], 1
0x18001f475  lea     rax, [rsp+270h+hMem]
0x18001f47a  mov     qword ptr [rbp+170h+SystemTime.wYear], rax
0x18001f481  mov     qword ptr [rbp+170h+SystemTime.wHour], r14
0x18001f488  mov     [rbp+170h+var_E0], 1
0x18001f48f  lea     rax, [rsp+270h+cbCertEncoded]
0x18001f494  mov     [rsp+270h+pvReserved], rax; unsigned int *
0x18001f499  lea     rax, [rbp+170h+var_1E8]
0x18001f49d  mov     qword ptr [rsp+270h+dwFlags], rax; unsigned __int8 **
0x18001f4a2  lea     rax, [rsp+270h+var_210]
0x18001f4a7  mov     [rsp+270h+pChainPara], rax; int
0x18001f4ac  lea     r9, [rbp+170h+SystemTime.wHour]; unsigned __int8 **
0x18001f4b3  lea     r8, [rbp+170h+var_1D8]; struct _BCryptBufferDesc *
0x18001f4b7  mov     rdx, r12; HWND
0x18001f4ba  mov     rcx, r15; pszKeyName
0x18001f4bd  call    ?WebAuthNGetKeyAttestationForUserIdKey@@YAJPEBGPEAUHWND__@@PEAU_BCryptBufferDesc@@PEAPEAEPEAK34@Z; WebAuthNGetKeyAttestationForUserIdKey(ushort const *,HWND__ *,_BCryptBufferDesc *,uchar * *,ulong *,uchar * *,ulong *)
0x18001f4c2  mov     edi, eax
0x18001f4c4  lea     rcx, [rbp+170h+SystemTime]
0x18001f4cb  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f4d0  nop
0x18001f4d1  lea     rcx, [rbp+170h+var_1F0]
0x18001f4d5  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f4da  mov     rcx, [rbp+178h]; this
0x18001f4e1  test    edi, edi
0x18001f4e3  jns     short loc_18001F4FE
0x18001f4e5  mov     edx, 4BFh; void *
0x18001f4ea  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f4f1  mov     r9d, edi; char *
0x18001f4f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f4f9  jmp     loc_18001F863
0x18001f4fe  mov     r15d, 1
0x18001f504  mov     [rbp+170h+var_1B0], r15d
0x18001f508  mov     [rbp+170h+var_1A0], 0FFFF0001h
0x18001f50f  lea     rax, a20; "2.0"
0x18001f516  mov     [rbp+170h+var_180], rax
0x18001f51a  mov     esi, 80070000h
0x18001f51f  lea     r12d, [r15+7]
0x18001f523  mov     ecx, [rsp+270h+var_210]
0x18001f527  cmp     ecx, 18h
0x18001f52a  jb      loc_18001F6A8
0x18001f530  mov     rdx, [rsp+270h+hMem]
0x18001f535  cmp     [rdx+8], ecx
0x18001f538  ja      loc_18001F6A8
0x18001f53e  sub     ecx, [rdx+8]
0x18001f541  test    edi, edi
0x18001f543  jnz     loc_18001F6AD
0x18001f549  mov     r8d, [rdx+0Ch]
0x18001f54d  cmp     ecx, r8d
0x18001f550  jb      loc_18001F6A8
0x18001f556  mov     r10d, [rdx+8]
0x18001f55a  add     r10, rdx
0x18001f55d  mov     [rbp+170h+var_178], r8d
0x18001f561  mov     [rbp+170h+var_170], r10
0x18001f565  sub     ecx, r8d
0x18001f568  mov     r9d, [rdx+10h]
0x18001f56c  cmp     ecx, r9d
0x18001f56f  jb      loc_18001F6A8
0x18001f575  add     r8, r10
0x18001f578  mov     [rbp+170h+var_19C], r9d
0x18001f57c  mov     [rbp+170h+var_198], r8
0x18001f580  mov     eax, [rdx+14h]
0x18001f583  sub     ecx, r9d
0x18001f586  cmp     ecx, eax
0x18001f588  jb      loc_18001F6A8
0x18001f58e  mov     [rbp+170h+var_168], eax
0x18001f591  lea     rax, [r8+r9]
0x18001f595  mov     [rbp+170h+var_160], rax
0x18001f599  mov     r8d, [rsp+270h+cbCertEncoded]; cbCertEncoded
0x18001f59e  mov     rdx, [rsp+270h+pbCertEncoded]; pbCertEncoded
0x18001f5a3  mov     ecx, r15d; dwCertEncodingType
0x18001f5a6  call    cs:__imp_CertCreateCertificateContext
0x18001f5ac  mov     rdx, rax
0x18001f5af  lea     rcx, [rsp+270h+var_208]
0x18001f5b4  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x18001f5b9  mov     rbx, [rsp+270h+var_208]
0x18001f5be  test    rbx, rbx
0x18001f5c1  jnz     short loc_18001F5D4
0x18001f5c3  call    cs:__imp_GetLastError
0x18001f5c9  mov     edi, eax
0x18001f5cb  test    eax, eax
0x18001f5cd  jle     short loc_18001F5D4
0x18001f5cf  movzx   edi, ax
0x18001f5d2  or      edi, esi
0x18001f5d4  mov     qword ptr [rsp+270h+cbCertEncoded], r14
0x18001f5d9  mov     dword ptr [rbp+170h+SystemTime.wYear], 807E5h
0x18001f5e3  mov     qword ptr [rbp+170h+SystemTime.wDayOfWeek], 140005h
0x18001f5ee  mov     dword ptr [rbp+170h+SystemTime.wSecond], r14d
0x18001f5f5  lea     rdx, [rsp+270h+cbCertEncoded]; lpFileTime
0x18001f5fa  lea     rcx, [rbp+170h+SystemTime]; lpSystemTime
0x18001f601  call    cs:__imp_SystemTimeToFileTime
0x18001f607  test    eax, eax
0x18001f609  jnz     short loc_18001F678
0x18001f60b  mov     rcx, [rbp+178h]; this
0x18001f612  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f619  mov     edx, 50Eh; void *
0x18001f61e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f623  mov     ebx, eax
0x18001f625  lea     rcx, [rsp+270h+var_208]
0x18001f62a  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18001f62f  nop
0x18001f630  mov     rcx, [rsp+270h+pbCertEncoded]; hMem
0x18001f635  mov     [rsp+270h+pbCertEncoded], r14
0x18001f63a  test    rcx, rcx
0x18001f63d  jz      short loc_18001F646
0x18001f63f  call    cs:__imp_LocalFree
0x18001f645  nop
0x18001f646  mov     rcx, [rsp+270h+hMem]; hMem
0x18001f64b  mov     [rsp+270h+hMem], r14
0x18001f650  test    rcx, rcx
0x18001f653  jz      short loc_18001F65C
0x18001f655  call    cs:__imp_LocalFree
0x18001f65b  nop
0x18001f65c  mov     rcx, [rsp+270h+var_228]; hMem
0x18001f661  mov     [rsp+270h+var_228], r14
0x18001f666  test    rcx, rcx
0x18001f669  jz      short loc_18001F671
0x18001f66b  call    cs:__imp_LocalFree
0x18001f671  mov     eax, ebx
0x18001f673  jmp     loc_18001F8B1
0x18001f678  mov     rcx, [rbx+18h]
0x18001f67c  add     rcx, 40h ; '@'; lpFileTime1
0x18001f680  lea     rdx, [rsp+270h+cbCertEncoded]; lpFileTime2
0x18001f685  call    cs:__imp_CompareFileTime
0x18001f68b  test    eax, eax
0x18001f68d  jns     short loc_18001F6AD
0x18001f68f  xor     r9d, r9d
0x18001f692  xor     r8d, r8d
0x18001f695  xor     edx, edx
0x18001f697  mov     rcx, [r13+8]
0x18001f69b  call    cs:__imp_NgcRenewKeyAttestation
0x18001f6a1  mov     edi, 80092010h
0x18001f6a6  jmp     short loc_18001F6AD
0x18001f6a8  mov     edi, 80090005h
0x18001f6ad  mov     rcx, [rbp+178h]
0x18001f6b4  test    edi, edi
0x18001f6b6  jns     short loc_18001F6C2
0x18001f6b8  mov     edx, 520h
0x18001f6bd  jmp     loc_18001F4EA
0x18001f6c2  mov     r14d, 60h ; '`'
0x18001f6c8  mov     r8d, r14d; Size
0x18001f6cb  xor     edx, edx; Val
0x18001f6cd  lea     rcx, [rbp+170h+var_150]; void *
0x18001f6d1  call    memset_0
0x18001f6d6  mov     [rbp+170h+var_150.cbSize], r14d
0x18001f6da  mov     [rbp+170h+var_118], 1388h
0x18001f6e1  xor     r14d, r14d
0x18001f6e4  mov     qword ptr [rsp+270h+cbCertEncoded], r14
0x18001f6e9  lea     rax, [rsp+270h+cbCertEncoded]
0x18001f6ee  mov     [rsp+270h+ppChainContext], rax; ppChainContext
0x18001f6f3  mov     [rsp+270h+pvReserved], r14; pvReserved
0x18001f6f8  mov     [rsp+270h+dwFlags], r14d; dwFlags
0x18001f6fd  lea     rax, [rbp+170h+var_150]
0x18001f701  mov     [rsp+270h+pChainPara], rax; int
0x18001f706  xor     r9d, r9d; hAdditionalStore
0x18001f709  xor     r8d, r8d; pTime
0x18001f70c  mov     rdx, rbx; pCertContext
0x18001f70f  mov     rcx, r15; hChainEngine
0x18001f712  call    cs:__imp_CertGetCertificateChain
0x18001f718  test    eax, eax
0x18001f71a  jnz     short loc_18001F756
0x18001f71c  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18001f721  mov     edi, eax
0x18001f723  test    eax, eax
0x18001f725  jle     short loc_18001F72C
0x18001f727  movzx   edi, ax
0x18001f72a  or      edi, esi
0x18001f72c  mov     rcx, [rbp+178h]; this
0x18001f733  mov     r9d, edi; char *
0x18001f736  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001f73d  mov     edx, 534h; void *
0x18001f742  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001f747  lea     rcx, [rsp+270h+cbCertEncoded]
0x18001f74c  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CHAIN_CONTEXT@@P6AXPEBU1@@Z$1?CertFreeCertificateChain@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CHAIN_CONTEXT const *,void (*)(_CERT_CHAIN_CONTEXT const *),&CertFreeCertificateChain(_CERT_CHAIN_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,0,std::nullptr_t>>(void)
0x18001f751  jmp     loc_18001F863
0x18001f756  mov     rax, qword ptr [rsp+270h+cbCertEncoded]
0x18001f75b  mov     rcx, [rax+10h]
0x18001f75f  mov     rax, [rcx]
0x18001f762  mov     r8d, [rax+0Ch]
0x18001f766  lea     r9, [rax+10h]
0x18001f76a  cmp     r8d, r15d
0x18001f76d  jbe     short loc_18001F799
0x18001f76f  lea     edx, [r8-1]
0x18001f773  mov     rax, [r9]
0x18001f776  mov     rcx, [rax+rdx*8]
0x18001f77a  mov     eax, [rcx+14h]
0x18001f77d  and     eax, r12d
0x18001f780  test    al, al
0x18001f782  cmovz   edx, r8d
0x18001f786  mov     r8d, 4
0x18001f78c  cmp     edx, r8d
0x18001f78f  jbe     short loc_18001F796
0x18001f791  mov     r10d, r14d
0x18001f794  jmp     short loc_18001F7A1
0x18001f796  mov     r8d, edx
0x18001f799  mov     r10d, r14d
0x18001f79c  test    r8d, r8d
0x18001f79f  jz      short loc_18001F7D6
0x18001f7a1  mov     r11, r14
0x18001f7a4  mov     rax, [r9]
0x18001f7a7  mov     rcx, [rax+r11*8]
0x18001f7ab  mov     rdx, [rcx+8]
  ... truncated ...
```
