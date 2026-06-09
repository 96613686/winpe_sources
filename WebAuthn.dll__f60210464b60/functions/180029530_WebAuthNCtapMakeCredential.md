# WebAuthNCtapMakeCredential

- ea: `0x180029530`
- end: `0x180029b6f`
- name: `WebAuthNCtapMakeCredential`
- size: `1599`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, struct _GUID *, void *, void *Src, __int64, __int64)`
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000af70`
- `0x18000c9d0`
- `0x18001687c`
- `0x180018d2c`
- `0x18001c0f4`
- `0x18001c400`
- `0x18001c760`
- `0x1800205e4`
- `0x180025880`
- `0x180027338`
- `0x180029530`
- `0x180029d5c`
- `0x180029f98`
- `0x18002a050`
- `0x18002a2f0`
- `0x18002a830`
- `0x18002f9b0`
- `0x180031708`
- `0x18004baa4`
- `0x1800537a4`
- `0x18006b9b0`
- `0x1800737bc`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029705`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002971c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029705`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002971c`
- `RPCRT4!UuidCreate` at `0x180029622`
- `RPCRT4!UuidCreate` at `0x180029622`

## string_xrefs

- `0x18002966d`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180029785`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18002999a`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180029b56`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
__int64 __fastcall WebAuthNCtapMakeCredential(
        void *a1,
        unsigned int a2,
        struct _WEBAUTHN_RP_ENTITY_INFORMATION *a3,
        struct _WEBAUTHN_USER_ENTITY_INFORMATION *a4,
        struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *a5,
        struct _WEBAUTHN_CLIENT_DATA *a6,
        struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *a7,
        struct _WEBAUTHN_CREDENTIAL_ATTESTATION **a8,
        struct _GUID *a9,
        void *a10,
        void *Src,
        _DWORD *a12,
        _DWORD *a13)
{
  struct _GUID *p_Uuid; // r15
  int v14; // r12d
  unsigned __int8 *v15; // r13
  __int64 v16; // rcx
  int v17; // esi
  int updated; // ebx
  __int64 *v19; // rdi
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  __int64 v23; // rdx
  void *v24; // rdi
  unsigned int v25; // r14d
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // edi
  int v29; // r14d
  __int64 v30; // rdi
  const unsigned __int16 *v31; // r10
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // rdx
  const unsigned __int16 *v34; // rcx
  unsigned int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+70h] [rbp-90h] BYREF
  struct _WEBAUTHN_CREDENTIAL_ATTESTATION **v39; // [rsp+78h] [rbp-88h]
  unsigned int v40; // [rsp+80h] [rbp-80h]
  void *p_hMem; // [rsp+88h] [rbp-78h] BYREF
  struct _CTAPCBOR_DEVICE_RESPONSE_INFO *v42; // [rsp+90h] [rbp-70h] BYREF
  char v43; // [rsp+98h] [rbp-68h]
  int v44; // [rsp+A0h] [rbp-60h] BYREF
  int v45; // [rsp+A4h] [rbp-5Ch] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v47; // [rsp+B0h] [rbp-50h] BYREF
  void *v48; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v49; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 *v50; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v51; // [rsp+D0h] [rbp-30h] BYREF
  struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *v52; // [rsp+D8h] [rbp-28h]
  struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *v53; // [rsp+E0h] [rbp-20h]
  struct _WEBAUTHN_RP_ENTITY_INFORMATION *v54; // [rsp+E8h] [rbp-18h]
  struct _WEBAUTHN_CLIENT_DATA *v55; // [rsp+F0h] [rbp-10h]
  struct _WEBAUTHN_USER_ENTITY_INFORMATION *v56; // [rsp+F8h] [rbp-8h]
  _DWORD *v57; // [rsp+100h] [rbp+0h]
  _DWORD *v58; // [rsp+108h] [rbp+8h]
  int v59; // [rsp+110h] [rbp+10h] BYREF
  __int64 v60; // [rsp+118h] [rbp+18h]
  int v61; // [rsp+120h] [rbp+20h]
  __int64 v62; // [rsp+128h] [rbp+28h]
  UUID Uuid; // [rsp+160h] [rbp+60h] BYREF
  int v64[144]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  p_Uuid = a9;
  v53 = a5;
  v55 = a6;
  v52 = a7;
  v57 = a12;
  v54 = a3;
  v40 = a2;
  v48 = a1;
  v58 = a13;
  v56 = a4;
  v39 = a8;
  memset_0(v64, 0, 0x238u);
  v14 = 0;
  v49 = 0;
  v51 = 0;
  v38 = 0;
  v15 = 0;
  v50 = 0;
  v47 = 0;
  Uuid = 0;
  hMem = 0;
  memset_0(&v59, 0, 0x48u);
  v44 = 0;
  v17 = 0;
  *a8 = 0;
  v45 = 0;
  if ( !a9 )
  {
    UuidCreate(&Uuid);
    p_Uuid = &Uuid;
  }
  if ( (Microsoft_Windows_WebAuthNEnableBits & 1) != 0 )
    McTemplateU0j_EventWriteTransfer(v16, EVENT_WEBAUTHN_CTAP_MAKE_CREDENTIAL_START, p_Uuid);
  if ( a10 )
  {
    if ( Src )
    {
      SecureZeroString(a10);
      SecureZeroString(Src);
      updated = -2146893785;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xA90,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)0x80090027LL,
        v35);
LABEL_8:
      v19 = (__int64 *)v39;
      goto LABEL_9;
    }
LABEL_29:
    v26 = 0;
    if ( a10 )
    {
      updated = CtapCborClientPinProtectString(a10);
      SecureZeroString(a10);
      if ( updated )
      {
        v23 = 2756;
LABEL_21:
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
          (const char *)(unsigned int)updated,
          v35);
        if ( updated > 0 )
          updated = (unsigned __int16)updated | 0x80070000;
        goto LABEL_8;
      }
      v24 = v48;
      v25 = v40;
      p_hMem = &hMem;
      v42 = 0;
      v43 = 1;
      updated = SelectDevice(v48, 0, p_Uuid, 0, 0, 0, (__int64)&v42);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( !hMem || (v26 = *((_QWORD *)hMem + 1)) == 0 || (v17 = *(_DWORD *)(v26 + 92), v17 != 1) )
      {
        if ( updated < 0 )
          goto LABEL_8;
LABEL_36:
        updated = -2147023570;
        goto LABEL_8;
      }
    }
    else
    {
      v24 = v48;
      v25 = v40;
    }
    goto LABEL_38;
  }
  if ( !Src )
    goto LABEL_29;
  updated = CtapCborClientPinProtectString(Src);
  SecureZeroString(Src);
  if ( updated )
  {
    v23 = 2717;
    goto LABEL_21;
  }
  v24 = v48;
  v25 = v40;
  p_hMem = &hMem;
  v42 = 0;
  v43 = 1;
  updated = UpdateSelectedDevice(
              (_DWORD)v48,
              0,
              v40,
              (_DWORD)p_Uuid,
              6,
              (__int64)&v59,
              0,
              (__int64)&v44,
              (__int64)&v45,
              (__int64)&v42);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( updated < 0 )
  {
    v17 = v44;
    v14 = v45;
    goto LABEL_8;
  }
  if ( !hMem || (v26 = *((_QWORD *)hMem + 1)) == 0 )
  {
    v17 = v44;
    v14 = v45;
    goto LABEL_36;
  }
  v59 = v61;
  v60 = v62;
  v61 = 0;
  v62 = 0;
LABEL_38:
  v43 = 1;
  p_hMem = &v51;
  v17 = 0;
  v42 = 0;
  updated = I_WebAuthNCtapEncodeMakeCredentialRpcRequest(
              p_Uuid,
              0,
              0x4000000u,
              v25,
              v54,
              v56,
              v53,
              v55,
              v52,
              (const struct _CTAPCBOR_DEVICE_INFO *)v26,
              (struct _WEBAUTHN_CTAP_RPC_PROTECTED *)&v59,
              (struct _CTAPCBOR_RPC_REQUEST *)v64,
              &v49,
              (unsigned __int8 **)&v42);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
  if ( updated < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAFC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)updated,
      v36);
    goto LABEL_8;
  }
  v27 = I_SendRpcRequest(v24, 0, (const struct _CTAPCBOR_RPC_REQUEST *)v64, v49, v51, 1u, &v38, &v50);
  v15 = v50;
  updated = v27;
  if ( v27 < 0 )
  {
    v28 = v38;
    if ( v38 )
    {
      v48 = 0;
      p_hMem = &v47;
      v38 = 0;
      v42 = 0;
      v43 = 1;
      v29 = CtapCborDecodeDeviceResponseInfo(v28, (_DWORD)v50, (unsigned int)&v42, (unsigned int)&v48, (__int64)&v38);
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( v29 )
      {
        EventWriteCborDecodeError(
          (_DWORD)p_Uuid,
          (unsigned int)"CtapCborDecodeDeviceResponseInfo",
          v29,
          v28,
          (__int64)v15,
          (__int64)v48,
          v38);
      }
      else
      {
        v30 = *((_QWORD *)v47 + 1);
        if ( v30 )
        {
          if ( (byte_1801AEA01 & 8) != 0 )
          {
            v31 = &dword_18015030C;
            v32 = &dword_18015030C;
            if ( *(_QWORD *)(v30 + 64) )
              v32 = *(const unsigned __int16 **)(v30 + 64);
            v33 = &dword_18015030C;
            v34 = &dword_18015030C;
            if ( *(_QWORD *)(v30 + 56) )
              v33 = *(const unsigned __int16 **)(v30 + 56);
            if ( *(_QWORD *)(v30 + 32) )
              v34 = *(const unsigned __int16 **)(v30 + 32);
            if ( *(_QWORD *)(v30 + 16) )
              v31 = *(const unsigned __int16 **)(v30 + 16);
            McTemplateU0jzzzzjt_EventWriteTransfer(
              (_DWORD)v34,
              (_DWORD)v33,
              (_DWORD)p_Uuid,
              (_DWORD)v31,
              (__int64)v34,
              (__int64)v33,
              (__int64)v32,
              v30 + 76,
              *(_DWORD *)(v30 + 24));
          }
          v17 = *(_DWORD *)(v30 + 92);
          v14 = *(_DWORD *)(v30 + 96);
        }
      }
    }
    goto LABEL_8;
  }
  v19 = (__int64 *)v39;
  p_hMem = &v47;
  v42 = 0;
  v43 = 1;
  updated = I_WebAuthNCtapDecodeMakeCredentialRpcResponse(
              p_Uuid,
              v38,
              v50,
              0,
              (struct _CTAPCBOR_RPC_REQUEST *)v64,
              &v42,
              v39);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3C,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)updated,
      v37);
LABEL_9:
  LogCtapMakeCredentialStopEvent(
    (_DWORD)p_Uuid,
    updated,
    v40,
    *((_QWORD *)v54 + 1),
    0,
    (__int64)v53,
    (__int64)v52,
    *v19,
    (__int64)v47);
  CtapCltFree(v15);
  FreeRpcProtected(&v59);
  if ( v57 )
    *v57 = v17;
  if ( v58 )
    *v58 = v14;
  v20 = hMem;
  hMem = 0;
  if ( v20 )
    LocalFree(v20);
  v21 = v47;
  v47 = 0;
  if ( v21 )
    LocalFree(v21);
  wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&v51, 0);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180029530  push    rbp
0x180029532  push    rbx
0x180029533  push    rsi
0x180029534  push    rdi
0x180029535  push    r12
0x180029537  push    r13
0x180029539  push    r14
0x18002953b  push    r15
0x18002953d  lea     rbp, [rsp-2C8h]
0x180029545  sub     rsp, 3C8h
0x18002954c  mov     rax, cs:__security_cookie
0x180029553  xor     rax, rsp
0x180029556  mov     [rbp+300h+var_50], rax
0x18002955d  mov     rax, [rbp+300h+arg_20]
0x180029564  mov     rbx, [rbp+300h+arg_38]
0x18002956b  mov     r15, [rbp+300h+arg_40]
0x180029572  mov     r14, [rbp+300h+arg_48]
0x180029579  mov     rdi, [rbp+300h+Src]
0x180029580  mov     [rbp+300h+var_320], rax
0x180029584  mov     rax, [rbp+300h+arg_28]
0x18002958b  mov     [rbp+300h+var_310], rax
0x18002958f  mov     rax, [rbp+300h+arg_30]
0x180029596  mov     [rbp+300h+var_328], rax
0x18002959a  mov     rax, [rbp+300h+arg_58]
0x1800295a1  mov     [rbp+300h+var_300], rax
0x1800295a5  mov     rax, [rbp+300h+arg_60]
0x1800295ac  mov     [rbp+300h+var_318], r8
0x1800295b0  mov     r8d, 238h; Size
0x1800295b6  mov     [rbp+300h+var_380], edx
0x1800295b9  xor     edx, edx; Val
0x1800295bb  mov     [rbp+300h+var_348], rcx
0x1800295bf  lea     rcx, [rbp+300h+var_290]; void *
0x1800295c3  mov     [rbp+300h+var_2F8], rax
0x1800295c7  mov     [rbp+300h+var_308], r9
0x1800295cb  mov     [rsp+400h+var_388], rbx
0x1800295d0  call    memset_0
0x1800295d5  xor     r12d, r12d
0x1800295d8  lea     rcx, [rbp+300h+var_2F0]; void *
0x1800295dc  xorps   xmm0, xmm0
0x1800295df  mov     [rbp+300h+var_340], r12d
0x1800295e3  xor     edx, edx; Val
0x1800295e5  mov     [rbp+300h+var_330], r12
0x1800295e9  mov     [rsp+400h+var_390], r12d
0x1800295ee  mov     r13d, r12d
0x1800295f1  lea     r8d, [r12+48h]; Size
0x1800295f6  mov     [rbp+300h+var_338], r12
0x1800295fa  mov     [rbp+300h+var_350], r12
0x1800295fe  movups  xmmword ptr [rbp+300h+Uuid.Data1], xmm0
0x180029602  mov     [rbp+300h+hMem], r12
0x180029606  call    memset_0
0x18002960b  mov     [rbp+300h+var_360], r12d
0x18002960f  mov     esi, r12d
0x180029612  mov     [rbx], rsi
0x180029615  mov     [rbp+300h+var_35C], r12d
0x180029619  test    r15, r15
0x18002961c  jnz     short loc_18002962C
0x18002961e  lea     rcx, [rbp+300h+Uuid]; Uuid
0x180029622  call    cs:__imp_UuidCreate
0x180029628  lea     r15, [rbp+300h+Uuid]
0x18002962c  test    cs:Microsoft_Windows_WebAuthNEnableBits, 1
0x180029633  jz      short loc_180029644
0x180029635  mov     r8, r15
0x180029638  lea     rdx, EVENT_WEBAUTHN_CTAP_MAKE_CREDENTIAL_START
0x18002963f  call    McTemplateU0j_EventWriteTransfer
0x180029644  test    r14, r14
0x180029647  jz      loc_180029752
0x18002964d  test    rdi, rdi
0x180029650  jz      loc_180029853
0x180029656  mov     rcx, r14
0x180029659  call    _SecureZeroString
0x18002965e  mov     rcx, rdi
0x180029661  call    _SecureZeroString
0x180029666  mov     rcx, [rbp+308h]; this
0x18002966d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180029674  mov     ebx, 80090027h
0x180029679  mov     edx, 0A90h; void *
0x18002967e  mov     r9d, ebx; char *
0x180029681  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180029686  mov     rdi, [rsp+400h+var_388]
0x18002968b  mov     rax, [rbp+300h+var_350]
0x18002968f  mov     edx, ebx
0x180029691  mov     r8d, [rbp+300h+var_380]
0x180029695  mov     rcx, r15
0x180029698  mov     [rsp+400h+var_3C0], rax
0x18002969d  mov     rax, [rdi]
0x1800296a0  mov     [rsp+400h+var_3C8], rax
0x1800296a5  mov     rax, [rbp+300h+var_328]
0x1800296a9  mov     [rsp+400h+var_3D0], rax
0x1800296ae  mov     rax, [rbp+300h+var_320]
0x1800296b2  mov     [rsp+400h+var_3D8], rax
0x1800296b7  mov     rax, [rbp+300h+var_318]
0x1800296bb  mov     dword ptr [rsp+400h+var_3E0], 0
0x1800296c3  mov     r9, [rax+8]
0x1800296c7  call    _LogCtapMakeCredentialStopEvent
0x1800296cc  mov     rcx, r13; lpMem
0x1800296cf  call    CtapCltFree
0x1800296d4  lea     rcx, [rbp+300h+var_2F0]
0x1800296d8  call    _FreeRpcProtected
0x1800296dd  mov     rax, [rbp+300h+var_300]
0x1800296e1  test    rax, rax
0x1800296e4  jz      short loc_1800296E8
0x1800296e6  mov     [rax], esi
0x1800296e8  mov     rax, [rbp+300h+var_2F8]
0x1800296ec  test    rax, rax
0x1800296ef  jz      short loc_1800296F4
0x1800296f1  mov     [rax], r12d
0x1800296f4  mov     rcx, [rbp+300h+hMem]; hMem
0x1800296f8  mov     [rbp+300h+hMem], 0
0x180029700  test    rcx, rcx
0x180029703  jz      short loc_18002970B
0x180029705  call    cs:__imp_LocalFree
0x18002970b  mov     rcx, [rbp+300h+var_350]; hMem
0x18002970f  mov     [rbp+300h+var_350], 0
0x180029717  test    rcx, rcx
0x18002971a  jz      short loc_180029722
0x18002971c  call    cs:__imp_LocalFree
0x180029722  xor     edx, edx
0x180029724  lea     rcx, [rbp+300h+var_330]
0x180029728  call    ?reset@?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>::reset(uchar *)
0x18002972d  mov     eax, ebx
0x18002972f  mov     rcx, [rbp+300h+var_50]
0x180029736  xor     rcx, rsp; StackCookie
0x180029739  call    __security_check_cookie
0x18002973e  add     rsp, 3C8h
0x180029745  pop     r15
0x180029747  pop     r14
0x180029749  pop     r13
0x18002974b  pop     r12
0x18002974d  pop     rdi
0x18002974e  pop     rsi
0x18002974f  pop     rbx
0x180029750  pop     rbp
0x180029751  retn
0x180029752  test    rdi, rdi
0x180029755  jz      loc_180029853
0x18002975b  lea     r8, [rbp+300h+var_2D8]
0x18002975f  mov     rcx, rdi; Src
0x180029762  lea     rdx, [rbp+300h+var_2E0]
0x180029766  call    CtapCborClientPinProtectString
0x18002976b  mov     rcx, rdi
0x18002976e  mov     ebx, eax
0x180029770  call    _SecureZeroString
0x180029775  test    ebx, ebx
0x180029777  jz      short loc_1800297AA
0x180029779  mov     edx, 0A9Dh; void *
0x18002977e  mov     rcx, [rbp+308h]; this
0x180029785  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002978c  mov     r9d, ebx; char *
0x18002978f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180029794  test    ebx, ebx
0x180029796  jle     loc_180029686
0x18002979c  movzx   ebx, bx
0x18002979f  or      ebx, 80070000h
0x1800297a5  jmp     loc_180029686
0x1800297aa  mov     rdi, [rbp+300h+var_348]
0x1800297ae  lea     rax, [rbp+300h+hMem]
0x1800297b2  mov     r14d, [rbp+300h+var_380]
0x1800297b6  mov     r9, r15
0x1800297b9  mov     [rbp+300h+var_378], rax
0x1800297bd  mov     r8d, r14d
0x1800297c0  lea     rax, [rbp+300h+var_370]
0x1800297c4  mov     [rbp+300h+var_370], rsi
0x1800297c8  mov     [rsp+400h+var_3B8], rax
0x1800297cd  xor     edx, edx
0x1800297cf  lea     rax, [rbp+300h+var_35C]
0x1800297d3  mov     [rbp+300h+var_368], 1
0x1800297d7  mov     [rsp+400h+var_3C0], rax
0x1800297dc  mov     rcx, rdi
0x1800297df  lea     rax, [rbp+300h+var_360]
0x1800297e3  mov     [rsp+400h+var_3C8], rax
0x1800297e8  lea     rax, [rbp+300h+var_2F0]
0x1800297ec  mov     [rsp+400h+var_3D0], rsi
0x1800297f1  mov     [rsp+400h+var_3D8], rax
0x1800297f6  mov     byte ptr [rsp+400h+var_3E0], 6
0x1800297fb  call    _UpdateSelectedDevice
0x180029800  lea     rcx, [rbp+300h+var_378]
0x180029804  mov     ebx, eax
0x180029806  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002980b  test    ebx, ebx
0x18002980d  js      short loc_180029847
0x18002980f  mov     rax, [rbp+300h+hMem]
0x180029813  test    rax, rax
0x180029816  jz      short loc_18002983B
0x180029818  mov     rcx, [rax+8]
0x18002981c  test    rcx, rcx
0x18002981f  jz      short loc_18002983B
0x180029821  mov     eax, [rbp+300h+var_2E0]
0x180029824  mov     [rbp+300h+var_2F0], eax
0x180029827  mov     rax, [rbp+300h+var_2D8]
0x18002982b  mov     [rbp+300h+var_2E8], rax
0x18002982f  mov     [rbp+300h+var_2E0], esi
0x180029832  mov     [rbp+300h+var_2D8], rsi
0x180029836  jmp     loc_180029909
0x18002983b  mov     esi, [rbp+300h+var_360]
0x18002983e  mov     r12d, [rbp+300h+var_35C]
0x180029842  jmp     loc_1800298F7
0x180029847  mov     esi, [rbp+300h+var_360]
0x18002984a  mov     r12d, [rbp+300h+var_35C]
0x18002984e  jmp     loc_180029686
0x180029853  xor     ecx, ecx
0x180029855  test    r14, r14
0x180029858  jz      loc_180029901
0x18002985e  lea     r8, [rbp+300h+var_2E8]
0x180029862  mov     rcx, r14; Src
0x180029865  lea     rdx, [rbp+300h+var_2F0]
0x180029869  call    CtapCborClientPinProtectString
0x18002986e  mov     rcx, r14
0x180029871  mov     ebx, eax
0x180029873  call    _SecureZeroString
0x180029878  test    ebx, ebx
0x18002987a  jz      short loc_180029886
0x18002987c  mov     edx, 0AC4h
0x180029881  jmp     loc_18002977E
0x180029886  mov     rdi, [rbp+300h+var_348]
0x18002988a  lea     rax, [rbp+300h+hMem]
0x18002988e  mov     r14d, [rbp+300h+var_380]
0x180029892  xor     r8d, r8d
0x180029895  mov     [rbp+300h+var_378], rax
0x180029899  mov     r9d, r14d
0x18002989c  lea     rax, [rbp+300h+var_370]
0x1800298a0  mov     [rbp+300h+var_370], rsi
0x1800298a4  mov     [rsp+400h+var_3C0], rax
0x1800298a9  xor     edx, edx
0x1800298ab  mov     [rsp+400h+var_3C8], rsi
0x1800298b0  mov     rcx, rdi
0x1800298b3  mov     dword ptr [rsp+400h+var_3D0], esi
0x1800298b7  mov     [rsp+400h+var_3D8], rsi
0x1800298bc  mov     [rsp+400h+var_3E0], r15
0x1800298c1  mov     [rbp+300h+var_368], 1
0x1800298c5  call    _SelectDevice
0x1800298ca  lea     rcx, [rbp+300h+var_378]
0x1800298ce  mov     ebx, eax
0x1800298d0  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800298d5  mov     rax, [rbp+300h+hMem]
0x1800298d9  test    rax, rax
0x1800298dc  jz      short loc_1800298EF
0x1800298de  mov     rcx, [rax+8]
0x1800298e2  test    rcx, rcx
0x1800298e5  jz      short loc_1800298EF
0x1800298e7  mov     esi, [rcx+5Ch]
0x1800298ea  cmp     esi, 1
0x1800298ed  jz      short loc_180029909
0x1800298ef  test    ebx, ebx
0x1800298f1  js      loc_180029686
0x1800298f7  mov     ebx, 8007052Eh
0x1800298fc  jmp     loc_180029686
0x180029901  mov     rdi, [rbp+300h+var_348]
0x180029905  mov     r14d, [rbp+300h+var_380]
0x180029909  lea     rax, [rbp+300h+var_330]
0x18002990d  mov     [rbp+300h+var_368], 1
0x180029911  mov     [rbp+300h+var_378], rax
0x180029915  xor     esi, esi
0x180029917  lea     rax, [rbp+300h+var_370]
0x18002991b  mov     [rbp+300h+var_370], rsi
0x18002991f  mov     [rsp+400h+var_398], rax; unsigned __int8 **
0x180029924  mov     r9d, r14d; unsigned int
0x180029927  lea     rax, [rbp+300h+var_340]
0x18002992b  xor     edx, edx; unsigned int
0x18002992d  mov     [rsp+400h+var_3A0], rax; unsigned int *
0x180029932  mov     r8d, 4000000h; unsigned int
0x180029938  lea     rax, [rbp+300h+var_290]
0x18002993c  mov     [rsp+400h+var_3A8], rax; struct _CTAPCBOR_RPC_REQUEST *
0x180029941  lea     rax, [rbp+300h+var_2F0]
0x180029945  mov     [rsp+400h+var_3B0], rax; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x18002994a  mov     rax, [rbp+300h+var_328]
0x18002994e  mov     [rsp+400h+var_3B8], rcx; struct _CTAPCBOR_DEVICE_INFO *
0x180029953  mov     rcx, r15; struct _GUID *
0x180029956  mov     [rsp+400h+var_3C0], rax; struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *
0x18002995b  mov     rax, [rbp+300h+var_310]
0x18002995f  mov     [rsp+400h+var_3C8], rax; struct _WEBAUTHN_CLIENT_DATA *
0x180029964  mov     rax, [rbp+300h+var_320]
0x180029968  mov     [rsp+400h+var_3D0], rax; struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *
0x18002996d  mov     rax, [rbp+300h+var_308]
0x180029971  mov     [rsp+400h+var_3D8], rax; struct _WEBAUTHN_USER_ENTITY_INFORMATION *
0x180029976  mov     rax, [rbp+300h+var_318]
0x18002997a  mov     [rsp+400h+var_3E0], rax; int
0x18002997f  call    ?I_WebAuthNCtapEncodeMakeCredentialRpcRequest@@YAJPEAU_GUID@@KKKPEBU_WEBAUTHN_RP_ENTITY_INFORMATION@@PEBU_WEBAUTHN_USER_ENTITY_INFORMATION@@PEBU_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS@@PEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS@@PEBU_CTAPCBOR_DEVICE_INFO@@PEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@PEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_WebAuthNCtapEncodeMakeCredentialRpcRequest(_GUID *,ulong,ulong,ulong,_WEBAUTHN_RP_ENTITY_INFORMATION const *,_WEBAUTHN_USER_ENTITY_INFORMATION const *,_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS const *,_CTAPCBOR_DEVICE_INFO const *,_WEBAUTHN_CTAP_RPC_PROTECTED *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x180029984  lea     rcx, [rbp+300h+var_378]
0x180029988  mov     ebx, eax
0x18002998a  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x18002998f  test    ebx, ebx
0x180029991  jns     short loc_1800299B3
0x180029993  mov     rcx, [rbp+308h]; this
0x18002999a  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800299a1  mov     r9d, ebx; char *
0x1800299a4  mov     edx, 0AFCh; void *
0x1800299a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800299ae  jmp     loc_180029686
0x1800299b3  mov     rax, [rbp+300h+var_330]
0x1800299b7  lea     rcx, [rbp+300h+var_338]
0x1800299bb  mov     r9d, [rbp+300h+var_340]; unsigned int
0x1800299bf  lea     r8, [rbp+300h+var_290]; struct _CTAPCBOR_RPC_REQUEST *
0x1800299c3  mov     [rsp+400h+var_3C8], rcx; unsigned __int8 **
0x1800299c8  xor     edx, edx; int
0x1800299ca  lea     rcx, [rsp+400h+var_390]
0x1800299cf  mov     [rsp+400h+var_3D0], rcx; unsigned int *
0x1800299d4  mov     rcx, rdi; void *
0x1800299d7  mov     dword ptr [rsp+400h+var_3D8], 1; unsigned int
0x1800299df  mov     [rsp+400h+var_3E0], rax; unsigned __int8 *
0x1800299e4  call    ?I_SendRpcRequest@@YAJPEAXHPEBU_CTAPCBOR_RPC_REQUEST@@KPEAEKPEAKPEAPEAE@Z; I_SendRpcRequest(void *,int,_CTAPCBOR_RPC_REQUEST const *,ulong,uchar *,ulong,ulong *,uchar * *)
  ... truncated ...
```
