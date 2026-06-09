# I_WebAuthNAuthenticatorMakeCredentialCtap(_GUID *,HWND__ *,_WEBAUTHN_RP_ENTITY_INFORMATION const *,_WEBAUTHN_USER_ENTITY_INFORMATION const *,_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS const *,_WEBAUTHN_CREDENTIAL_ATTESTATION * *)

- ea: `0x180069e50`
- end: `0x18006a337`
- name: `?I_WebAuthNAuthenticatorMakeCredentialCtap@@YAJPEAU_GUID@@PEAUHWND__@@PEBU_WEBAUTHN_RP_ENTITY_INFORMATION@@PEBU_WEBAUTHN_USER_ENTITY_INFORMATION@@PEBU_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS@@PEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS@@PEAPEAU_WEBAUTHN_CREDENTIAL_ATTESTATION@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(struct _GUID *, HWND, const struct _WEBAUTHN_RP_ENTITY_INFORMATION *, const struct _WEBAUTHN_USER_ENTITY_INFORMATION *, const struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *, const struct _WEBAUTHN_CLIENT_DATA *, const struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *, struct _WEBAUTHN_CREDENTIAL_ATTESTATION **)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a550`

## callees

- `0x18000af70`
- `0x18000c9d0`
- `0x18001687c`
- `0x18001c760`
- `0x1800205e4`
- `0x18002a2f0`
- `0x18002f9b0`
- `0x180031708`
- `0x180046768`
- `0x1800467e0`
- `0x18004baa4`
- `0x1800537a4`
- `0x180055188`
- `0x1800692d8`
- `0x180069e50`
- `0x18006b9b0`
- `0x18006c84c`
- `0x180095468`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a2f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a30c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a2f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a30c`
- `RPCRT4!UuidCreate` at `0x18006a0e0`
- `RPCRT4!UuidCreate` at `0x18006a0e0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18006a060`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18006a060`

## string_xrefs

- `0x18006a02c`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006a0bb`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006a0f6`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006a211`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18006a28e`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall I_WebAuthNAuthenticatorMakeCredentialCtap(
        struct _GUID *a1,
        HWND a2,
        const struct _WEBAUTHN_RP_ENTITY_INFORMATION *a3,
        const struct _WEBAUTHN_USER_ENTITY_INFORMATION *a4,
        const struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *a5,
        const struct _WEBAUTHN_CLIENT_DATA *a6,
        const struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *a7,
        struct _WEBAUTHN_CREDENTIAL_ATTESTATION **a8)
{
  unsigned __int8 *v10; // r13
  unsigned int v11; // esi
  int v12; // r12d
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rdx
  BOOL v16; // r15d
  int v17; // ecx
  int CredentialRpcRequest; // ebx
  struct _GUID *v19; // r12
  int updated; // eax
  unsigned int v21; // eax
  unsigned int v22; // r8d
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  _BYTE v32[4]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v34; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v35; // [rsp+7Ch] [rbp-84h] BYREF
  struct _GUID *v36; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v38; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v39; // [rsp+98h] [rbp-68h] BYREF
  struct _WEBAUTHN_CREDENTIAL_ATTESTATION **v40; // [rsp+A0h] [rbp-60h]
  HLOCAL *p_hMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _CTAPCBOR_DEVICE_RESPONSE_INFO *v42; // [rsp+B0h] [rbp-50h] BYREF
  char v43; // [rsp+B8h] [rbp-48h]
  struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *v44; // [rsp+C0h] [rbp-40h]
  struct _WEBAUTHN_RP_ENTITY_INFORMATION *v45; // [rsp+C8h] [rbp-38h]
  struct _WEBAUTHN_CLIENT_DATA *v46; // [rsp+D0h] [rbp-30h]
  struct _WEBAUTHN_USER_ENTITY_INFORMATION *v47; // [rsp+D8h] [rbp-28h]
  HWND v48; // [rsp+E0h] [rbp-20h] BYREF
  int v49; // [rsp+E8h] [rbp-18h]
  int v50; // [rsp+ECh] [rbp-14h]
  int v51; // [rsp+F0h] [rbp-10h]
  int v52; // [rsp+F4h] [rbp-Ch]
  int v53; // [rsp+F8h] [rbp-8h]
  int v54; // [rsp+FCh] [rbp-4h]
  UUID *p_Uuid; // [rsp+100h] [rbp+0h]
  _BYTE v57[64]; // [rsp+130h] [rbp+30h] BYREF
  HWND *v58; // [rsp+170h] [rbp+70h]
  UUID Uuid; // [rsp+180h] [rbp+80h] BYREF
  int v60[144]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+328h]

  v47 = a4;
  v45 = a3;
  v36 = a1;
  v44 = a5;
  v46 = a6;
  v40 = a8;
  memset_0(v60, 0, 0x238u);
  v10 = 0;
  v34 = 0;
  v38 = 0;
  hMem = 0;
  v11 = 0;
  v12 = 0;
  memset_0(v57, 0, 0x48u);
  memset_0(&v48, 0, 0x48u);
  Uuid = 0;
  v35 = 0;
  v39 = 0;
  v14 = 0;
  v32[0] = 0;
  *a8 = 0;
  v58 = &v48;
  v48 = a2;
  if ( (Microsoft_Windows_WebAuthNEnableBits & 1) != 0 )
    McTemplateU0j_EventWriteTransfer(v13, EVENT_WEBAUTHN_CTAP_MAKE_CREDENTIAL_START, a1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v16 = ShouldSendRequestToRemoteSession(0);
  }
  else
  {
    v16 = 0;
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v32) )
    {
      v16 = v32[0] != 0;
    }
  }
  if ( a7 )
  {
    v49 = *((_DWORD *)a7 + 10);
    v50 = *((_DWORD *)a7 + 11);
    v52 = *((_DWORD *)a7 + 12);
    v14 = *((_DWORD *)a7 + 13);
    v53 = v14;
    if ( *(_DWORD *)a7 )
    {
      v33 = 0;
      if ( (unsigned int)I_IsBooleanExtensionPresentInExtensionList((char *)a7 + 24, v15, &v33) )
      {
        if ( v33 )
          v12 = 0x4000000;
      }
    }
    if ( *(_DWORD *)a7 >= 2u )
      p_Uuid = (UUID *)*((_QWORD *)a7 + 8);
    v11 = *((_DWORD *)a7 + 14) & 0x40000000;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
      && (*((_DWORD *)a7 + 14) & 0x100000) != 0 )
    {
      v11 |= 0x100000u;
    }
    if ( *(_DWORD *)a7 >= 4u )
    {
      v54 = *((_DWORD *)a7 + 20);
      v51 = *((_DWORD *)a7 + 22);
      v17 = v50;
      if ( v51 )
        v17 = 1;
      v50 = v17;
      if ( *((_DWORD *)a7 + 21) )
      {
        if ( !*((_DWORD *)a7 + 11) )
        {
          CredentialRpcRequest = -2146893785;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x167D,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
            (const char *)0x80090027LL,
            v29);
LABEL_21:
          LODWORD(v19) = (_DWORD)v36;
          goto LABEL_41;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
    {
      if ( *(_DWORD *)a7 >= 8u )
      {
        updated = UpdateTransportHint(*((unsigned int *)a7 + 34), *((_QWORD *)a7 + 18), &v48);
        CredentialRpcRequest = updated;
        if ( updated < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1688,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
            (const char *)(unsigned int)updated,
            v29);
          goto LABEL_21;
        }
      }
    }
  }
  if ( !p_Uuid )
  {
    v21 = UuidCreate(&Uuid);
    CredentialRpcRequest = v21;
    if ( v21 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x168F,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)v21,
        v29);
      if ( CredentialRpcRequest > 0 )
        CredentialRpcRequest = (unsigned __int16)CredentialRpcRequest | 0x80070000;
      goto LABEL_21;
    }
    p_Uuid = &Uuid;
  }
  p_hMem = &v38;
  v42 = 0;
  v43 = 1;
  v22 = v12;
  v19 = v36;
  CredentialRpcRequest = I_WebAuthNCtapEncodeMakeCredentialRpcRequest(
                           v36,
                           5u,
                           v22,
                           v11,
                           v45,
                           v47,
                           v44,
                           v46,
                           a7,
                           0,
                           (struct _WEBAUTHN_CTAP_RPC_PROTECTED *)v57,
                           (struct _CTAPCBOR_RPC_REQUEST *)v60,
                           &v34,
                           (unsigned __int8 **)&v42);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v23 = retaddr;
  if ( CredentialRpcRequest < 0 )
  {
    v24 = 5793;
LABEL_40:
    wil::details::in1diag3::_Log_Hr(
      v23,
      (void *)v24,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)CredentialRpcRequest,
      v30);
    goto LABEL_41;
  }
  v25 = I_SendRpcRequest(0, v16, (const struct _CTAPCBOR_RPC_REQUEST *)v60, v34, (unsigned __int8 *)v38, 2u, &v35, &v39);
  CredentialRpcRequest = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16AB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)v25,
      v31);
    v10 = v39;
    goto LABEL_41;
  }
  p_hMem = &hMem;
  v42 = 0;
  v43 = 1;
  v10 = v39;
  CredentialRpcRequest = I_WebAuthNCtapDecodeMakeCredentialRpcResponse(
                           v19,
                           v35,
                           v39,
                           v14,
                           (struct _CTAPCBOR_RPC_REQUEST *)v60,
                           &v42,
                           v40);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v23 = retaddr;
  if ( CredentialRpcRequest < 0 )
  {
    v24 = 5812;
    goto LABEL_40;
  }
LABEL_41:
  LogCtapMakeCredentialStopEvent(
    (_DWORD)v19,
    CredentialRpcRequest,
    v11,
    *((_QWORD *)v45 + 1),
    1,
    (__int64)v44,
    (__int64)a7,
    (__int64)*v40,
    (__int64)hMem);
  CtapCltFree(v10);
  v26 = hMem;
  hMem = 0;
  if ( v26 )
    LocalFree(v26);
  v27 = v38;
  v38 = 0;
  if ( v27 )
    LocalFree(v27);
  return (unsigned int)CredentialRpcRequest;
}

```

## disassembly

```asm
0x180069e50  push    rbp
0x180069e52  push    rbx
0x180069e53  push    rsi
0x180069e54  push    rdi
0x180069e55  push    r12
0x180069e57  push    r13
0x180069e59  push    r14
0x180069e5b  push    r15
0x180069e5d  lea     rbp, [rsp-2E8h]
0x180069e65  sub     rsp, 3E8h
0x180069e6c  mov     rax, cs:__security_cookie
0x180069e73  xor     rax, rsp
0x180069e76  mov     [rbp+320h+var_50], rax
0x180069e7d  mov     [rbp+320h+var_348], r9
0x180069e81  mov     [rbp+320h+var_358], r8
0x180069e85  mov     rbx, rdx
0x180069e88  mov     r15, rcx
0x180069e8b  mov     [rbp+320h+var_3A0], rcx
0x180069e8f  mov     rdi, [rbp+320h+arg_30]
0x180069e96  mov     rax, [rbp+320h+arg_20]
0x180069e9d  mov     [rbp+320h+var_360], rax
0x180069ea1  mov     rax, [rbp+320h+arg_28]
0x180069ea8  mov     [rbp+320h+var_350], rax
0x180069eac  mov     rax, [rbp+320h+arg_38]
0x180069eb3  mov     [rbp+320h+var_380], rax
0x180069eb7  xor     edx, edx; Val
0x180069eb9  mov     r8d, 238h; Size
0x180069ebf  lea     rcx, [rbp+320h+var_290]; void *
0x180069ec6  call    memset_0
0x180069ecb  xor     r13d, r13d
0x180069ece  mov     [rsp+420h+var_3A8], r13d
0x180069ed3  mov     [rbp+320h+var_390], r13
0x180069ed7  mov     [rbp+320h+hMem], r13
0x180069edb  mov     esi, r13d
0x180069ede  mov     r12d, r13d
0x180069ee1  lea     r14d, [r13+48h]
0x180069ee5  mov     r8d, r14d; Size
0x180069ee8  xor     edx, edx; Val
0x180069eea  lea     rcx, [rbp+320h+var_2F0]; void *
0x180069eee  call    memset_0
0x180069ef3  mov     r8d, r14d; Size
0x180069ef6  xor     edx, edx; Val
0x180069ef8  lea     rcx, [rbp+320h+var_340]; void *
0x180069efc  call    memset_0
0x180069f01  xorps   xmm0, xmm0
0x180069f04  movups  xmmword ptr [rbp+320h+Uuid.Data1], xmm0
0x180069f0b  mov     [rsp+420h+var_3A4], r13d
0x180069f10  mov     [rbp+320h+var_388], r13
0x180069f14  xor     r14d, r14d
0x180069f17  mov     [rsp+420h+var_3B0], sil
0x180069f1c  mov     rax, [rbp+320h+var_380]
0x180069f20  mov     [rax], rsi
0x180069f23  lea     rax, [rbp+320h+var_340]
0x180069f27  mov     [rbp+320h+var_2B0], rax
0x180069f2b  mov     [rbp+320h+var_340], rbx
0x180069f2f  test    cs:Microsoft_Windows_WebAuthNEnableBits, 1
0x180069f36  jz      short loc_180069F47
0x180069f38  mov     r8, r15
0x180069f3b  lea     rdx, EVENT_WEBAUTHN_CTAP_MAKE_CREDENTIAL_START
0x180069f42  call    McTemplateU0j_EventWriteTransfer
0x180069f47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180069f4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180069f53  xor     ebx, ebx
0x180069f55  test    al, al
0x180069f57  jz      loc_18006A046
0x180069f5d  xor     ecx, ecx; unsigned __int8 *
0x180069f5f  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x180069f64  movzx   r15d, al
0x180069f68  mov     ecx, 1
0x180069f6d  test    rdi, rdi
0x180069f70  jz      loc_18006A0D3
0x180069f76  mov     eax, [rdi+28h]
0x180069f79  mov     [rbp+320h+var_338], eax
0x180069f7c  mov     eax, [rdi+2Ch]
0x180069f7f  mov     [rbp+320h+var_334], eax
0x180069f82  mov     eax, [rdi+30h]
0x180069f85  mov     [rbp+320h+var_32C], eax
0x180069f88  mov     r14d, [rdi+34h]
0x180069f8c  mov     [rbp+320h+var_328], r14d
0x180069f90  cmp     [rdi], ecx
0x180069f92  jb      short loc_180069FB7
0x180069f94  mov     [rsp+420h+var_3AC], ebx
0x180069f98  lea     rcx, [rdi+18h]
0x180069f9c  lea     r8, [rsp+420h+var_3AC]
0x180069fa1  call    I_IsBooleanExtensionPresentInExtensionList
0x180069fa6  test    eax, eax
0x180069fa8  jz      short loc_180069FB7
0x180069faa  mov     eax, 4000000h
0x180069faf  cmp     [rsp+420h+var_3AC], ebx
0x180069fb3  cmovnz  r12d, eax
0x180069fb7  cmp     dword ptr [rdi], 2
0x180069fba  jb      short loc_180069FC4
0x180069fbc  mov     rax, [rdi+40h]
0x180069fc0  mov     [rbp+320h+var_320], rax
0x180069fc4  mov     esi, [rdi+38h]
0x180069fc7  and     esi, 40000000h
0x180069fcd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x180069fd4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x180069fd9  test    al, al
0x180069fdb  jz      short loc_180069FE9
0x180069fdd  mov     eax, 100000h
0x180069fe2  test    [rdi+38h], eax
0x180069fe5  jz      short loc_180069FE9
0x180069fe7  or      esi, eax
0x180069fe9  cmp     dword ptr [rdi], 4
0x180069fec  jb      loc_18006A080
0x180069ff2  mov     eax, [rdi+50h]
0x180069ff5  mov     [rbp+320h+var_324], eax
0x180069ff8  mov     eax, [rdi+58h]
0x180069ffb  mov     [rbp+320h+var_330], eax
0x180069ffe  mov     ecx, [rbp+320h+var_334]
0x18006a001  test    eax, eax
0x18006a003  mov     eax, 1
0x18006a008  cmovnz  ecx, eax
0x18006a00b  mov     [rbp+320h+var_334], ecx
0x18006a00e  mov     eax, [rdi+54h]
0x18006a011  mov     [rbp+320h+var_318], eax
0x18006a014  test    eax, eax
0x18006a016  jz      short loc_18006A080
0x18006a018  cmp     [rdi+2Ch], ebx
0x18006a01b  jnz     short loc_18006A080
0x18006a01d  mov     ebx, 80090027h
0x18006a022  mov     rcx, [rbp+328h]; this
0x18006a029  mov     r9d, ebx; char *
0x18006a02c  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a033  mov     edx, 167Dh; void *
0x18006a038  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18006a03d  mov     r12, [rbp+320h+var_3A0]
0x18006a041  jmp     loc_18006A29A
0x18006a046  mov     r15d, ebx
0x18006a049  call    IsWinStationIsSessionRemoteablePresent
0x18006a04e  test    al, al
0x18006a050  jz      loc_180069F68
0x18006a056  lea     r8, [rsp+420h+var_3B0]
0x18006a05b  or      edx, 0FFFFFFFFh
0x18006a05e  xor     ecx, ecx
0x18006a060  call    cs:__imp_WinStationIsSessionRemoteable
0x18006a066  mov     ecx, 1
0x18006a06b  test    al, al
0x18006a06d  jz      loc_180069F6D
0x18006a073  cmp     [rsp+420h+var_3B0], bl
0x18006a077  cmovnz  r15d, ecx
0x18006a07b  jmp     loc_180069F6D
0x18006a080  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x18006a087  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x18006a08c  test    al, al
0x18006a08e  jz      short loc_18006A0D3
0x18006a090  cmp     dword ptr [rdi], 8
0x18006a093  jb      short loc_18006A0D3
0x18006a095  lea     r8, [rbp+320h+var_340]
0x18006a099  mov     rdx, [rdi+90h]
0x18006a0a0  mov     ecx, [rdi+88h]
0x18006a0a6  call    _UpdateTransportHint
0x18006a0ab  mov     ebx, eax
0x18006a0ad  mov     rcx, [rbp+328h]; this
0x18006a0b4  test    eax, eax
0x18006a0b6  jns     short loc_18006A0D1
0x18006a0b8  mov     r9d, eax; char *
0x18006a0bb  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a0c2  mov     edx, 1688h; void *
0x18006a0c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a0cc  jmp     loc_18006A03D
0x18006a0d1  xor     ebx, ebx
0x18006a0d3  cmp     [rbp+320h+var_320], rbx
0x18006a0d7  jnz     short loc_18006A12A
0x18006a0d9  lea     rcx, [rbp+320h+Uuid]; Uuid
0x18006a0e0  call    cs:__imp_UuidCreate
0x18006a0e6  mov     ebx, eax
0x18006a0e8  mov     rcx, [rbp+328h]; this
0x18006a0ef  test    eax, eax
0x18006a0f1  jz      short loc_18006A11D
0x18006a0f3  mov     r9d, eax; char *
0x18006a0f6  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a0fd  mov     edx, 168Fh; void *
0x18006a102  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18006a107  test    ebx, ebx
0x18006a109  jle     loc_18006A03D
0x18006a10f  movzx   ebx, bx
0x18006a112  or      ebx, 80070000h
0x18006a118  jmp     loc_18006A03D
0x18006a11d  lea     rax, [rbp+320h+Uuid]
0x18006a124  mov     [rbp+320h+var_320], rax
0x18006a128  xor     ebx, ebx
0x18006a12a  lea     rax, [rbp+320h+var_390]
0x18006a12e  mov     [rbp+320h+var_378], rax
0x18006a132  mov     [rbp+320h+var_370], rbx
0x18006a136  mov     [rbp+320h+var_368], 1
0x18006a13a  lea     rax, [rbp+320h+var_370]
0x18006a13e  mov     [rsp+420h+var_3B8], rax; unsigned __int8 **
0x18006a143  lea     rax, [rsp+420h+var_3A8]
0x18006a148  mov     [rsp+420h+var_3C0], rax; unsigned int *
0x18006a14d  lea     rax, [rbp+320h+var_290]
0x18006a154  mov     [rsp+420h+var_3C8], rax; struct _CTAPCBOR_RPC_REQUEST *
0x18006a159  lea     rax, [rbp+320h+var_2F0]
0x18006a15d  mov     [rsp+420h+var_3D0], rax; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x18006a162  mov     [rsp+420h+var_3D8], rbx; struct _CTAPCBOR_DEVICE_INFO *
0x18006a167  mov     [rsp+420h+var_3E0], rdi; struct _WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS *
0x18006a16c  mov     rax, [rbp+320h+var_350]
0x18006a170  mov     [rsp+420h+var_3E8], rax; struct _WEBAUTHN_CLIENT_DATA *
0x18006a175  mov     rax, [rbp+320h+var_360]
0x18006a179  mov     [rsp+420h+var_3F0], rax; struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *
0x18006a17e  mov     rax, [rbp+320h+var_348]
0x18006a182  mov     [rsp+420h+var_3F8], rax; struct _WEBAUTHN_USER_ENTITY_INFORMATION *
0x18006a187  mov     rax, [rbp+320h+var_358]
0x18006a18b  mov     [rsp+420h+var_400], rax; struct _WEBAUTHN_RP_ENTITY_INFORMATION *
0x18006a190  mov     r9d, esi; unsigned int
0x18006a193  mov     r8d, r12d; unsigned int
0x18006a196  mov     edx, 5; unsigned int
0x18006a19b  mov     r12, [rbp+320h+var_3A0]
0x18006a19f  mov     rcx, r12; struct _GUID *
0x18006a1a2  call    ?I_WebAuthNCtapEncodeMakeCredentialRpcRequest@@YAJPEAU_GUID@@KKKPEBU_WEBAUTHN_RP_ENTITY_INFORMATION@@PEBU_WEBAUTHN_USER_ENTITY_INFORMATION@@PEBU_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS@@PEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS@@PEBU_CTAPCBOR_DEVICE_INFO@@PEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@PEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_WebAuthNCtapEncodeMakeCredentialRpcRequest(_GUID *,ulong,ulong,ulong,_WEBAUTHN_RP_ENTITY_INFORMATION const *,_WEBAUTHN_USER_ENTITY_INFORMATION const *,_WEBAUTHN_COSE_CREDENTIAL_PARAMETERS const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_MAKE_CREDENTIAL_OPTIONS const *,_CTAPCBOR_DEVICE_INFO const *,_WEBAUTHN_CTAP_RPC_PROTECTED *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x18006a1a7  mov     ebx, eax
0x18006a1a9  lea     rcx, [rbp+320h+var_378]
0x18006a1ad  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006a1b2  mov     rcx, [rbp+328h]
0x18006a1b9  test    ebx, ebx
0x18006a1bb  jns     short loc_18006A1C7
0x18006a1bd  mov     edx, 16A1h
0x18006a1c2  jmp     loc_18006A28B
0x18006a1c7  mov     rax, [rbp+320h+var_390]
0x18006a1cb  lea     rcx, [rbp+320h+var_388]
0x18006a1cf  mov     [rsp+420h+var_3E8], rcx; unsigned __int8 **
0x18006a1d4  lea     rcx, [rsp+420h+var_3A4]
0x18006a1d9  mov     [rsp+420h+var_3F0], rcx; unsigned int *
0x18006a1de  mov     dword ptr [rsp+420h+var_3F8], 2; unsigned int
0x18006a1e6  mov     [rsp+420h+var_400], rax; int
0x18006a1eb  mov     r9d, [rsp+420h+var_3A8]; unsigned int
0x18006a1f0  lea     r8, [rbp+320h+var_290]; struct _CTAPCBOR_RPC_REQUEST *
0x18006a1f7  mov     edx, r15d; int
0x18006a1fa  xor     ecx, ecx; void *
0x18006a1fc  call    ?I_SendRpcRequest@@YAJPEAXHPEBU_CTAPCBOR_RPC_REQUEST@@KPEAEKPEAKPEAPEAE@Z; I_SendRpcRequest(void *,int,_CTAPCBOR_RPC_REQUEST const *,ulong,uchar *,ulong,ulong *,uchar * *)
0x18006a201  mov     ebx, eax
0x18006a203  mov     rcx, [rbp+328h]; this
0x18006a20a  test    eax, eax
0x18006a20c  jns     short loc_18006A228
0x18006a20e  mov     r9d, eax; char *
0x18006a211  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a218  mov     edx, 16ABh; void *
0x18006a21d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a222  mov     r13, [rbp+320h+var_388]
0x18006a226  jmp     short loc_18006A29A
0x18006a228  lea     rax, [rbp+320h+hMem]
0x18006a22c  mov     [rbp+320h+var_378], rax
0x18006a230  mov     [rbp+320h+var_370], 0
0x18006a238  mov     [rbp+320h+var_368], 1
0x18006a23c  mov     rax, [rbp+320h+var_380]
0x18006a240  mov     [rsp+420h+var_3F0], rax; struct _WEBAUTHN_CREDENTIAL_ATTESTATION **
0x18006a245  lea     rax, [rbp+320h+var_370]
0x18006a249  mov     [rsp+420h+var_3F8], rax; struct _CTAPCBOR_DEVICE_RESPONSE_INFO **
0x18006a24e  lea     rax, [rbp+320h+var_290]
0x18006a255  mov     [rsp+420h+var_400], rax; int
0x18006a25a  mov     r9d, r14d; unsigned int
0x18006a25d  mov     r13, [rbp+320h+var_388]
0x18006a261  mov     r8, r13; unsigned __int8 *
0x18006a264  mov     edx, [rsp+420h+var_3A4]; unsigned int
0x18006a268  mov     rcx, r12; struct _GUID *
0x18006a26b  call    ?I_WebAuthNCtapDecodeMakeCredentialRpcResponse@@YAJPEAU_GUID@@KPEAEKPEAU_CTAPCBOR_RPC_REQUEST@@PEAPEAU_CTAPCBOR_DEVICE_RESPONSE_INFO@@PEAPEAU_WEBAUTHN_CREDENTIAL_ATTESTATION@@@Z; I_WebAuthNCtapDecodeMakeCredentialRpcResponse(_GUID *,ulong,uchar *,ulong,_CTAPCBOR_RPC_REQUEST *,_CTAPCBOR_DEVICE_RESPONSE_INFO * *,_WEBAUTHN_CREDENTIAL_ATTESTATION * *)
0x18006a270  mov     ebx, eax
0x18006a272  lea     rcx, [rbp+320h+var_378]
0x18006a276  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006a27b  mov     rcx, [rbp+328h]; this
0x18006a282  test    ebx, ebx
0x18006a284  jns     short loc_18006A29A
0x18006a286  mov     edx, 16B4h; void *
0x18006a28b  mov     r9d, ebx; char *
0x18006a28e  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18006a295  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a29a  mov     rax, [rbp+320h+hMem]
0x18006a29e  mov     [rsp+420h+var_3E0], rax
0x18006a2a3  mov     rax, [rbp+320h+var_380]
0x18006a2a7  mov     rax, [rax]
0x18006a2aa  mov     [rsp+420h+var_3E8], rax
0x18006a2af  mov     [rsp+420h+var_3F0], rdi
0x18006a2b4  mov     rax, [rbp+320h+var_360]
0x18006a2b8  mov     [rsp+420h+var_3F8], rax
0x18006a2bd  mov     dword ptr [rsp+420h+var_400], 1
0x18006a2c5  mov     rax, [rbp+320h+var_358]
0x18006a2c9  mov     r9, [rax+8]
0x18006a2cd  mov     r8d, esi
0x18006a2d0  mov     edx, ebx
0x18006a2d2  mov     rcx, r12
0x18006a2d5  call    _LogCtapMakeCredentialStopEvent
0x18006a2da  mov     rcx, r13; lpMem
0x18006a2dd  call    CtapCltFree
0x18006a2e2  nop
0x18006a2e3  mov     rcx, [rbp+320h+hMem]; hMem
0x18006a2e7  mov     [rbp+320h+hMem], 0
0x18006a2ef  test    rcx, rcx
0x18006a2f2  jz      short loc_18006A2FB
0x18006a2f4  call    cs:__imp_LocalFree
0x18006a2fa  nop
0x18006a2fb  mov     rcx, [rbp+320h+var_390]; hMem
0x18006a2ff  mov     [rbp+320h+var_390], 0
0x18006a307  test    rcx, rcx
0x18006a30a  jz      short loc_18006A312
0x18006a30c  call    cs:__imp_LocalFree
0x18006a312  mov     eax, ebx
0x18006a314  mov     rcx, [rbp+320h+var_50]
0x18006a31b  xor     rcx, rsp; StackCookie
0x18006a31e  call    __security_check_cookie
  ... truncated ...
```
