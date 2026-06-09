# I_WebAuthNAuthenticatorGetAssertionCtap(_GUID *,HWND__ *,ushort const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS const *,_WEBAUTHN_ASSERTION * *)

- ea: `0x180069a10`
- end: `0x180069e48`
- name: `?I_WebAuthNAuthenticatorGetAssertionCtap@@YAJPEAU_GUID@@PEAUHWND__@@PEBGPEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS@@PEAPEAU_WEBAUTHN_ASSERTION@@@Z`
- size: `1080`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, HWND@<rdx>, const unsigned __int16 *@<r8>, const struct _WEBAUTHN_CLIENT_DATA *@<r9>, const struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *, struct _WEBAUTHN_ASSERTION **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180079750`

## callees

- `0x18000af70`
- `0x18000c9d0`
- `0x18001687c`
- `0x1800205e4`
- `0x1800258b0`
- `0x180026e50`
- `0x18002737c`
- `0x18002a2f0`
- `0x180046768`
- `0x1800467e0`
- `0x18004baa4`
- `0x1800537a4`
- `0x180055188`
- `0x180069a10`
- `0x18006c84c`
- `0x180095468`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069e1d`
- `RPCRT4!UuidCreate` at `0x180069be9`
- `RPCRT4!UuidCreate` at `0x180069be9`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180069b1b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180069b1b`

## string_xrefs

- `0x180069bff`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180069cbd`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180069d1a`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall I_WebAuthNAuthenticatorGetAssertionCtap(
        struct _GUID *a1,
        HWND a2,
        unsigned __int16 *a3,
        const struct _WEBAUTHN_CLIENT_DATA *a4,
        const struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *a5,
        struct _WEBAUTHN_ASSERTION **a6)
{
  unsigned __int8 *v8; // r12
  _DWORD *v9; // r15
  __int64 v10; // rcx
  unsigned int v11; // esi
  BOOL v12; // r14d
  int updated; // eax
  int AssertionRpcRequest; // ebx
  wil::details::in1diag3 *v15; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int v18; // eax
  int v19; // eax
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  _BYTE v25[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v26; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v27; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v30; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL *p_hMem; // [rsp+98h] [rbp-68h] BYREF
  struct _CTAPCBOR_DEVICE_RESPONSE_INFO *v32; // [rsp+A0h] [rbp-60h] BYREF
  char v33; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v34; // [rsp+B0h] [rbp-50h]
  struct _WEBAUTHN_CLIENT_DATA *v35; // [rsp+B8h] [rbp-48h]
  struct _WEBAUTHN_ASSERTION **v36; // [rsp+C0h] [rbp-40h]
  HWND v37; // [rsp+D0h] [rbp-30h] BYREF
  int v38; // [rsp+D8h] [rbp-28h]
  int v39; // [rsp+E4h] [rbp-1Ch]
  UUID *p_Uuid; // [rsp+F0h] [rbp-10h]
  int v41; // [rsp+FCh] [rbp-4h]
  int v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  _BYTE v44[64]; // [rsp+120h] [rbp+20h] BYREF
  HWND *v45; // [rsp+160h] [rbp+60h]
  UUID Uuid; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v47[576]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+318h]

  v35 = a4;
  v34 = a3;
  v36 = a6;
  memset_0(v47, 0, 0x238u);
  v8 = 0;
  v26 = 0;
  v29 = 0;
  hMem = 0;
  v9 = 0;
  memset_0(v44, 0, 0x48u);
  memset_0(&v37, 0, 0x48u);
  Uuid = 0;
  v25[0] = 0;
  v27 = 0;
  v30 = 0;
  *a6 = 0;
  v45 = &v37;
  v37 = a2;
  v11 = 0x10000000;
  if ( (Microsoft_Windows_WebAuthNEnableBits & 1) != 0 )
    McTemplateU0j_EventWriteTransfer(v10, &EVENT_WEBAUTHN_CTAP_GET_ASSERTION_START, a1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v12 = ShouldSendRequestToRemoteSession(0);
  }
  else
  {
    v12 = 0;
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v25) )
    {
      v12 = v25[0] != 0;
    }
  }
  if ( a5 )
  {
    v38 = *((_DWORD *)a5 + 10);
    v39 = *((_DWORD *)a5 + 11);
    if ( *(_DWORD *)a5 >= 2u )
    {
      v9 = (_DWORD *)*((_QWORD *)a5 + 8);
      if ( v9 )
        *v9 = 0;
    }
    if ( *(_DWORD *)a5 >= 3u )
      p_Uuid = (UUID *)*((_QWORD *)a5 + 9);
    v11 = *((_DWORD *)a5 + 12) & 0x40000000 | 0x10100000;
    if ( (*((_DWORD *)a5 + 12) & 0x100000) == 0 )
      v11 = *((_DWORD *)a5 + 12) & 0x40000000 | 0x10000000;
    if ( *(_DWORD *)a5 >= 5u )
    {
      v41 = *((_DWORD *)a5 + 22);
      v42 = *((_DWORD *)a5 + 23);
      v43 = *((_QWORD *)a5 + 12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
    {
      if ( *(_DWORD *)a5 >= 8u )
      {
        updated = UpdateTransportHint(*((unsigned int *)a5 + 36), *((_QWORD *)a5 + 19), &v37);
        AssertionRpcRequest = updated;
        v15 = retaddr;
        if ( updated < 0 )
        {
          v16 = (unsigned int)updated;
          v17 = 6325;
LABEL_30:
          wil::details::in1diag3::_Log_Hr(
            v15,
            (void *)v17,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
            (const char *)v16,
            v23);
          goto LABEL_39;
        }
      }
    }
  }
  if ( !p_Uuid )
  {
    v18 = UuidCreate(&Uuid);
    AssertionRpcRequest = v18;
    if ( v18 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x18BC,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)v18,
        v23);
      if ( AssertionRpcRequest > 0 )
        AssertionRpcRequest = (unsigned __int16)AssertionRpcRequest | 0x80070000;
      goto LABEL_39;
    }
    p_Uuid = &Uuid;
  }
  p_hMem = &v29;
  v32 = 0;
  v33 = 1;
  AssertionRpcRequest = I_WebAuthNCtapEncodeGetAssertionRpcRequest(
                          a1,
                          5u,
                          0,
                          v11,
                          v34,
                          v35,
                          a5,
                          0,
                          (struct _WEBAUTHN_CTAP_RPC_PROTECTED *)v44,
                          0,
                          0,
                          (struct _CTAPCBOR_RPC_REQUEST *)v47,
                          &v26,
                          (unsigned __int8 **)&v32);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v15 = retaddr;
  if ( AssertionRpcRequest < 0 )
  {
    v17 = 6350;
LABEL_29:
    v16 = (unsigned int)AssertionRpcRequest;
    goto LABEL_30;
  }
  v19 = I_SendRpcRequest(0, v12, (const struct _CTAPCBOR_RPC_REQUEST *)v47, v26, (unsigned __int8 *)v29, 2u, &v27, &v30);
  AssertionRpcRequest = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x18D8,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)v19,
      v24);
    v8 = v30;
    goto LABEL_39;
  }
  p_hMem = &hMem;
  v32 = 0;
  v33 = 1;
  v8 = v30;
  AssertionRpcRequest = I_WebAuthNCtapDecodeGetAssertionRpcResponse(
                          a1,
                          v27,
                          v30,
                          1,
                          0,
                          0,
                          (struct _CTAPCBOR_RPC_REQUEST *)v47,
                          &v32,
                          v36);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v15 = retaddr;
  if ( AssertionRpcRequest < 0 )
  {
    v17 = 6371;
    goto LABEL_29;
  }
  if ( v9 && hMem && *(_DWORD *)(*((_QWORD *)hMem + 1) + 28LL) )
    *v9 = 1;
LABEL_39:
  LogCtapGetAssertionStopEvent((_DWORD)a1, AssertionRpcRequest, v11, (_DWORD)v34, 1, (__int64)a5, (__int64)hMem);
  CtapCltFree(v8);
  v20 = hMem;
  hMem = 0;
  if ( v20 )
    LocalFree(v20);
  v21 = v29;
  v29 = 0;
  if ( v21 )
    LocalFree(v21);
  return (unsigned int)AssertionRpcRequest;
}

```

## disassembly

```asm
0x180069a10  push    rbp
0x180069a12  push    rbx
0x180069a13  push    rsi
0x180069a14  push    rdi
0x180069a15  push    r12
0x180069a17  push    r13
0x180069a19  push    r14
0x180069a1b  push    r15
0x180069a1d  lea     rbp, [rsp-2D8h]
0x180069a25  sub     rsp, 3D8h
0x180069a2c  mov     rax, cs:__security_cookie
0x180069a33  xor     rax, rsp
0x180069a36  mov     [rbp+310h+var_50], rax
0x180069a3d  mov     [rbp+310h+var_358], r9
0x180069a41  mov     [rbp+310h+var_360], r8
0x180069a45  mov     rbx, rdx
0x180069a48  mov     r13, rcx
0x180069a4b  mov     rdi, [rbp+310h+arg_20]
0x180069a52  mov     rsi, [rbp+310h+arg_28]
0x180069a59  mov     [rbp+310h+var_350], rsi
0x180069a5d  xor     edx, edx; Val
0x180069a5f  mov     r8d, 238h; Size
0x180069a65  lea     rcx, [rbp+310h+var_290]; void *
0x180069a6c  call    memset_0
0x180069a71  xor     r12d, r12d
0x180069a74  mov     [rsp+410h+var_39C], r12d
0x180069a79  mov     [rbp+310h+var_388], r12
0x180069a7d  mov     [rbp+310h+hMem], r12
0x180069a81  mov     r15d, r12d
0x180069a84  lea     r14d, [r12+48h]
0x180069a89  mov     r8d, r14d; Size
0x180069a8c  xor     edx, edx; Val
0x180069a8e  lea     rcx, [rbp+310h+var_2F0]; void *
0x180069a92  call    memset_0
0x180069a97  mov     r8d, r14d; Size
0x180069a9a  xor     edx, edx; Val
0x180069a9c  lea     rcx, [rbp+310h+var_340]; void *
0x180069aa0  call    memset_0
0x180069aa5  xorps   xmm0, xmm0
0x180069aa8  movups  xmmword ptr [rbp+310h+Uuid.Data1], xmm0
0x180069aac  mov     [rsp+410h+var_3A0], r12b
0x180069ab1  mov     [rsp+410h+var_398], r12d
0x180069ab6  mov     [rbp+310h+var_380], r12
0x180069aba  mov     [rsi], r12
0x180069abd  lea     rax, [rbp+310h+var_340]
0x180069ac1  mov     [rbp+310h+var_2B0], rax
0x180069ac5  mov     [rbp+310h+var_340], rbx
0x180069ac9  mov     esi, 10000000h
0x180069ace  test    cs:Microsoft_Windows_WebAuthNEnableBits, 1
0x180069ad5  jz      short loc_180069AE6
0x180069ad7  mov     r8, r13
0x180069ada  lea     rdx, EVENT_WEBAUTHN_CTAP_GET_ASSERTION_START
0x180069ae1  call    McTemplateU0j_EventWriteTransfer
0x180069ae6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180069aed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180069af2  xor     ebx, ebx
0x180069af4  test    al, al
0x180069af6  jz      short loc_180069B05
0x180069af8  xor     ecx, ecx; unsigned __int8 *
0x180069afa  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x180069aff  movzx   r14d, al
0x180069b03  jmp     short loc_180069B32
0x180069b05  mov     r14d, ebx
0x180069b08  call    IsWinStationIsSessionRemoteablePresent
0x180069b0d  test    al, al
0x180069b0f  jz      short loc_180069B32
0x180069b11  lea     r8, [rsp+410h+var_3A0]
0x180069b16  or      edx, 0FFFFFFFFh
0x180069b19  xor     ecx, ecx
0x180069b1b  call    cs:__imp_WinStationIsSessionRemoteable
0x180069b21  test    al, al
0x180069b23  jz      short loc_180069B32
0x180069b25  cmp     [rsp+410h+var_3A0], bl
0x180069b29  mov     eax, 1
0x180069b2e  cmovnz  r14d, eax
0x180069b32  test    rdi, rdi
0x180069b35  jz      loc_180069BDF
0x180069b3b  mov     eax, [rdi+28h]
0x180069b3e  mov     [rbp+310h+var_338], eax
0x180069b41  mov     eax, [rdi+2Ch]
0x180069b44  mov     [rbp+310h+var_32C], eax
0x180069b47  cmp     dword ptr [rdi], 2
0x180069b4a  jb      short loc_180069B58
0x180069b4c  mov     r15, [rdi+40h]
0x180069b50  test    r15, r15
0x180069b53  jz      short loc_180069B58
0x180069b55  mov     [r15], ebx
0x180069b58  cmp     dword ptr [rdi], 3
0x180069b5b  jb      short loc_180069B65
0x180069b5d  mov     rax, [rdi+48h]
0x180069b61  mov     [rbp+310h+var_320], rax
0x180069b65  mov     ecx, [rdi+30h]
0x180069b68  and     ecx, 40000000h
0x180069b6e  or      ecx, esi
0x180069b70  mov     edx, 100000h
0x180069b75  mov     esi, ecx
0x180069b77  or      esi, edx
0x180069b79  test    [rdi+30h], edx
0x180069b7c  cmovz   esi, ecx
0x180069b7f  cmp     dword ptr [rdi], 5
0x180069b82  jb      short loc_180069B98
0x180069b84  mov     eax, [rdi+58h]
0x180069b87  mov     [rbp+310h+var_314], eax
0x180069b8a  mov     eax, [rdi+5Ch]
0x180069b8d  mov     [rbp+310h+var_310], eax
0x180069b90  mov     rax, [rdi+60h]
0x180069b94  mov     [rbp+310h+var_308], rax
0x180069b98  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x180069b9f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x180069ba4  test    al, al
0x180069ba6  jz      short loc_180069BDF
0x180069ba8  cmp     dword ptr [rdi], 8
0x180069bab  jb      short loc_180069BDF
0x180069bad  lea     r8, [rbp+310h+var_340]
0x180069bb1  mov     rdx, [rdi+98h]
0x180069bb8  mov     ecx, [rdi+90h]
0x180069bbe  call    _UpdateTransportHint
0x180069bc3  mov     ebx, eax
0x180069bc5  mov     rcx, [rbp+318h]
0x180069bcc  test    eax, eax
0x180069bce  jns     short loc_180069BDD
0x180069bd0  mov     r9d, eax
0x180069bd3  mov     edx, 18B5h
0x180069bd8  jmp     loc_180069CBD
0x180069bdd  xor     ebx, ebx
0x180069bdf  cmp     [rbp+310h+var_320], rbx
0x180069be3  jnz     short loc_180069C30
0x180069be5  lea     rcx, [rbp+310h+Uuid]; Uuid
0x180069be9  call    cs:__imp_UuidCreate
0x180069bef  mov     ebx, eax
0x180069bf1  mov     rcx, [rbp+318h]; this
0x180069bf8  test    eax, eax
0x180069bfa  jz      short loc_180069C26
0x180069bfc  mov     r9d, eax; char *
0x180069bff  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180069c06  mov     edx, 18BCh; void *
0x180069c0b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180069c10  test    ebx, ebx
0x180069c12  jle     loc_180069DC4
0x180069c18  movzx   ebx, bx
0x180069c1b  or      ebx, 80070000h
0x180069c21  jmp     loc_180069DC4
0x180069c26  lea     rax, [rbp+310h+Uuid]
0x180069c2a  mov     [rbp+310h+var_320], rax
0x180069c2e  xor     ebx, ebx
0x180069c30  lea     rax, [rbp+310h+var_388]
0x180069c34  mov     [rbp+310h+var_378], rax
0x180069c38  mov     [rbp+310h+var_370], rbx
0x180069c3c  mov     [rbp+310h+var_368], 1
0x180069c40  lea     rax, [rbp+310h+var_370]
0x180069c44  mov     [rsp+410h+var_3A8], rax; unsigned __int8 **
0x180069c49  lea     rax, [rsp+410h+var_39C]
0x180069c4e  mov     [rsp+410h+var_3B0], rax; unsigned int *
0x180069c53  lea     rax, [rbp+310h+var_290]
0x180069c5a  mov     [rsp+410h+var_3B8], rax; struct _CTAPCBOR_RPC_REQUEST *
0x180069c5f  mov     [rsp+410h+var_3C0], rbx; unsigned __int8 *
0x180069c64  mov     [rsp+410h+var_3C8], ebx; unsigned int
0x180069c68  lea     rax, [rbp+310h+var_2F0]
0x180069c6c  mov     [rsp+410h+var_3D0], rax; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x180069c71  mov     [rsp+410h+var_3D8], rbx; struct _CTAPCBOR_DEVICE_INFO *
0x180069c76  mov     [rsp+410h+var_3E0], rdi; struct _WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS *
0x180069c7b  mov     rax, [rbp+310h+var_358]
0x180069c7f  mov     [rsp+410h+var_3E8], rax; struct _WEBAUTHN_CLIENT_DATA *
0x180069c84  mov     rax, [rbp+310h+var_360]
0x180069c88  mov     [rsp+410h+var_3F0], rax; int
0x180069c8d  mov     r9d, esi; unsigned int
0x180069c90  xor     r8d, r8d; unsigned int
0x180069c93  lea     edx, [r8+5]; unsigned int
0x180069c97  mov     rcx, r13; struct _GUID *
0x180069c9a  call    ?I_WebAuthNCtapEncodeGetAssertionRpcRequest@@YAJPEAU_GUID@@KKKPEBGPEBU_WEBAUTHN_CLIENT_DATA@@PEBU_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS@@PEBU_CTAPCBOR_DEVICE_INFO@@PEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@KPEBEPEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_WebAuthNCtapEncodeGetAssertionRpcRequest(_GUID *,ulong,ulong,ulong,ushort const *,_WEBAUTHN_CLIENT_DATA const *,_WEBAUTHN_AUTHENTICATOR_GET_ASSERTION_OPTIONS const *,_CTAPCBOR_DEVICE_INFO const *,_WEBAUTHN_CTAP_RPC_PROTECTED *,ulong,uchar const *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x180069c9f  mov     ebx, eax
0x180069ca1  lea     rcx, [rbp+310h+var_378]
0x180069ca5  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180069caa  mov     rcx, [rbp+318h]; this
0x180069cb1  test    ebx, ebx
0x180069cb3  jns     short loc_180069CCE
0x180069cb5  mov     edx, 18CEh; void *
0x180069cba  mov     r9d, ebx; char *
0x180069cbd  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180069cc4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069cc9  jmp     loc_180069DC4
0x180069cce  mov     rax, [rbp+310h+var_388]
0x180069cd2  lea     rcx, [rbp+310h+var_380]
0x180069cd6  mov     [rsp+410h+var_3D8], rcx; unsigned __int8 **
0x180069cdb  lea     rcx, [rsp+410h+var_398]
0x180069ce0  mov     [rsp+410h+var_3E0], rcx; unsigned int *
0x180069ce5  mov     dword ptr [rsp+410h+var_3E8], 2; unsigned int
0x180069ced  mov     [rsp+410h+var_3F0], rax; int
0x180069cf2  mov     r9d, [rsp+410h+var_39C]; unsigned int
0x180069cf7  lea     r8, [rbp+310h+var_290]; struct _CTAPCBOR_RPC_REQUEST *
0x180069cfe  mov     edx, r14d; int
0x180069d01  xor     ecx, ecx; void *
0x180069d03  call    ?I_SendRpcRequest@@YAJPEAXHPEBU_CTAPCBOR_RPC_REQUEST@@KPEAEKPEAKPEAPEAE@Z; I_SendRpcRequest(void *,int,_CTAPCBOR_RPC_REQUEST const *,ulong,uchar *,ulong,ulong *,uchar * *)
0x180069d08  mov     ebx, eax
0x180069d0a  mov     rcx, [rbp+318h]; this
0x180069d11  xor     edx, edx
0x180069d13  test    eax, eax
0x180069d15  jns     short loc_180069D34
0x180069d17  mov     r9d, eax; char *
0x180069d1a  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180069d21  mov     edx, 18D8h; void *
0x180069d26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069d2b  mov     r12, [rbp+310h+var_380]
0x180069d2f  jmp     loc_180069DC4
0x180069d34  lea     rax, [rbp+310h+hMem]
0x180069d38  mov     [rbp+310h+var_378], rax
0x180069d3c  mov     [rbp+310h+var_370], rdx
0x180069d40  mov     ecx, 1
0x180069d45  mov     [rbp+310h+var_368], cl
0x180069d48  mov     rax, [rbp+310h+var_350]
0x180069d4c  mov     [rsp+410h+var_3D0], rax; struct _WEBAUTHN_ASSERTION **
0x180069d51  lea     rax, [rbp+310h+var_370]
0x180069d55  mov     [rsp+410h+var_3D8], rax; struct _CTAPCBOR_DEVICE_RESPONSE_INFO **
0x180069d5a  lea     rax, [rbp+310h+var_290]
0x180069d61  mov     [rsp+410h+var_3E0], rax; struct _CTAPCBOR_RPC_REQUEST *
0x180069d66  mov     [rsp+410h+var_3E8], rdx; unsigned __int8 *
0x180069d6b  mov     dword ptr [rsp+410h+var_3F0], edx; unsigned int
0x180069d6f  mov     r9d, ecx; int
0x180069d72  mov     r12, [rbp+310h+var_380]
0x180069d76  mov     r8, r12; unsigned __int8 *
0x180069d79  mov     edx, [rsp+410h+var_398]; unsigned int
0x180069d7d  mov     rcx, r13; struct _GUID *
0x180069d80  call    ?I_WebAuthNCtapDecodeGetAssertionRpcResponse@@YAJPEAU_GUID@@KPEAEHKPEBEPEAU_CTAPCBOR_RPC_REQUEST@@PEAPEAU_CTAPCBOR_DEVICE_RESPONSE_INFO@@PEAPEAU_WEBAUTHN_ASSERTION@@@Z; I_WebAuthNCtapDecodeGetAssertionRpcResponse(_GUID *,ulong,uchar *,int,ulong,uchar const *,_CTAPCBOR_RPC_REQUEST *,_CTAPCBOR_DEVICE_RESPONSE_INFO * *,_WEBAUTHN_ASSERTION * *)
0x180069d85  mov     ebx, eax
0x180069d87  lea     rcx, [rbp+310h+var_378]
0x180069d8b  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180069d90  mov     rcx, [rbp+318h]
0x180069d97  test    ebx, ebx
0x180069d99  jns     short loc_180069DA5
0x180069d9b  mov     edx, 18E3h
0x180069da0  jmp     loc_180069CBA
0x180069da5  test    r15, r15
0x180069da8  jz      short loc_180069DC4
0x180069daa  mov     rax, [rbp+310h+hMem]
0x180069dae  test    rax, rax
0x180069db1  jz      short loc_180069DC4
0x180069db3  mov     rdx, [rax+8]
0x180069db7  cmp     dword ptr [rdx+1Ch], 0
0x180069dbb  jz      short loc_180069DC4
0x180069dbd  mov     dword ptr [r15], 1
0x180069dc4  mov     rax, [rbp+310h+hMem]
0x180069dc8  mov     [rsp+410h+var_3E0], rax
0x180069dcd  mov     [rsp+410h+var_3E8], rdi
0x180069dd2  mov     dword ptr [rsp+410h+var_3F0], 1
0x180069dda  mov     r9, [rbp+310h+var_360]
0x180069dde  mov     r8d, esi
0x180069de1  mov     edx, ebx
0x180069de3  mov     rcx, r13
0x180069de6  call    _LogCtapGetAssertionStopEvent
0x180069deb  mov     rcx, r12; lpMem
0x180069dee  call    CtapCltFree
0x180069df3  nop
0x180069df4  mov     rcx, [rbp+310h+hMem]; hMem
0x180069df8  mov     [rbp+310h+hMem], 0
0x180069e00  test    rcx, rcx
0x180069e03  jz      short loc_180069E0C
0x180069e05  call    cs:__imp_LocalFree
0x180069e0b  nop
0x180069e0c  mov     rcx, [rbp+310h+var_388]; hMem
0x180069e10  mov     [rbp+310h+var_388], 0
0x180069e18  test    rcx, rcx
0x180069e1b  jz      short loc_180069E23
0x180069e1d  call    cs:__imp_LocalFree
0x180069e23  mov     eax, ebx
0x180069e25  mov     rcx, [rbp+310h+var_50]
0x180069e2c  xor     rcx, rsp; StackCookie
0x180069e2f  call    __security_check_cookie
0x180069e34  add     rsp, 3D8h
0x180069e3b  pop     r15
0x180069e3d  pop     r14
0x180069e3f  pop     r13
0x180069e41  pop     r12
0x180069e43  pop     rdi
0x180069e44  pop     rsi
0x180069e45  pop     rbx
0x180069e46  pop     rbp
0x180069e47  retn
```
