# VerifyAuthBrokerCallbackUri(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,_AUTH_BROKER_CLIENT_CONTEXT *,HSTRING__ * *,uint,int *)

- ea: `0x18000f568`
- end: `0x18000fa0f`
- name: `?VerifyAuthBrokerCallbackUri@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@0PEAU_AUTH_BROKER_CLIENT_CONTEXT@@PEAPEAUHSTRING__@@IPEAH@Z`
- size: `1191`
- prototype: `__int64 __fastcall(HSTRING__ *callbackUri, Windows::Foundation::IUriRuntimeClass *requestUri, _AUTH_BROKER_CLIENT_CONTEXT *clientContext, HSTRING__ **callbackAbsoluteUri, unsigned int brokerFlags, int *useSsoAppContainer)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017770`

## callees

- `0x1800035e0`
- `0x180004940`
- `0x180005000`
- `0x180006e5c`
- `0x18000737c`
- `0x1800073bc`
- `0x18000f42c`
- `0x18000f568`
- `0x1800113a8`
- `0x180011b30`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f72d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f7d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f72d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f7d1`
- `ntdll!_wcsnicmp` at `0x18000f650`
- `ntdll!_wcsnicmp` at `0x18000f6c3`
- `ntdll!_wcsnicmp` at `0x18000f6e4`
- `ntdll!_wcsnicmp` at `0x18000f650`
- `ntdll!_wcsnicmp` at `0x18000f6c3`
- `ntdll!_wcsnicmp` at `0x18000f6e4`

## pseudocode

```c
__int64 __fastcall VerifyAuthBrokerCallbackUri(
        HSTRING__ *callbackUri,
        Windows::Foundation::IUriRuntimeClass *requestUri,
        _AUTH_BROKER_CLIENT_CONTEXT *clientContext,
        HSTRING__ **callbackAbsoluteUri,
        unsigned int brokerFlags,
        int *useSsoAppContainer)
{
  int *v6; // rdi
  _AUTH_BROKER_CLIENT_CONTEXT *v7; // rbx
  int SsoCallbackUri; // eax
  signed int Lpcwstr; // esi
  unsigned int *p_flags; // r12
  WPP_PROJECT_CONTROL_BLOCK *v11; // rcx
  unsigned __int16 v12; // dx
  unsigned int v13; // r9d
  HSTRING__ *hstring; // rdi
  int v15; // esi
  void *tokenHandle; // rbx
  const wchar_t *StringRawBuffer; // rax
  Windows::Foundation::IUriRuntimeClass_vtbl *v18; // rax
  WPP_PROJECT_CONTROL_BLOCK *v19; // rcx
  unsigned __int16 v20; // dx
  void *v21; // rdi
  const wchar_t *v22; // rbx
  const wchar_t *v23; // rax
  WPP_PROJECT_CONTROL_BLOCK *v24; // rcx
  unsigned __int16 v25; // dx
  HSTRING__ *v26; // rax
  int v28; // [rsp+20h] [rbp-20h]
  int v29; // [rsp+24h] [rbp-1Ch]
  Windows::Internal::String host; // [rsp+28h] [rbp-18h] BYREF
  Windows::Internal::String callback; // [rsp+30h] [rbp-10h] BYREF
  HSTRING__ *v32; // [rsp+38h] [rbp-8h]
  Windows::Internal::String request; // [rsp+80h] [rbp+40h] BYREF
  Windows::Foundation::IUriRuntimeClass *v34; // [rsp+88h] [rbp+48h]
  _AUTH_BROKER_CLIENT_CONTEXT *v35; // [rsp+90h] [rbp+50h]
  HSTRING__ **v36; // [rsp+98h] [rbp+58h]

  v36 = callbackAbsoluteUri;
  v35 = clientContext;
  v34 = requestUri;
  request._hstring = callbackUri;
  v6 = useSsoAppContainer;
  *callbackAbsoluteUri = 0;
  v7 = clientContext;
  callback._hstring = 0;
  host._hstring = 0;
  *v6 = 0;
  if ( callbackUri )
  {
    Lpcwstr = (*(__int64 (__fastcall **)(HSTRING__ *, Windows::Internal::String *))(*(_QWORD *)callbackUri + 48LL))(
                callbackUri,
                &callback);
    if ( Lpcwstr < 0
      || (Lpcwstr = Windows::Internal::String::GetLpcwstr(&callback, (const wchar_t **)&host), Lpcwstr < 0) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_83;
      }
      v12 = 41;
      v13 = Lpcwstr;
LABEL_82:
      WPP_SF_d(v11[1].Control.Logger, v12, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v13);
      goto LABEL_83;
    }
    hstring = host._hstring;
    v28 = 0;
    v29 = 0;
    v15 = 0;
    v32 = host._hstring;
    if ( !_wcsnicmp((const wchar_t *)host._hstring, L"testsso.", 8u) )
    {
      do
      {
        v29 = 1;
        hstring += 4;
        if ( GetAuthHostRegDWORDValue(L"EnableTestSsoPrefix") )
        {
          v15 = 1;
        }
        else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
               && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
               && WPP_GLOBAL_Control[1].Control.Level >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x2Au, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
        }
      }
      while ( !_wcsnicmp((const wchar_t *)hstring, L"testsso.", 8u) );
      v28 = v15;
      v32 = hstring;
    }
    if ( _wcsnicmp((const wchar_t *)hstring, L"ms-app:", 7u) )
    {
LABEL_41:
      p_flags = &v7->flags;
      if ( (v7->flags & 2) == 0 )
      {
        if ( (brokerFlags & 0x20000) != 0 && !v15 )
        {
          Lpcwstr = -2147024809;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_83;
          }
          v25 = 46;
          goto LABEL_48;
        }
        if ( (brokerFlags & 0x80000) != 0 && !v15 )
        {
          Lpcwstr = -2147024809;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_83;
          }
          v25 = 47;
          goto LABEL_48;
        }
        if ( (brokerFlags & 0x100000) != 0 && !v15 )
        {
          Lpcwstr = -2147024809;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_83;
          }
          v25 = 48;
LABEL_48:
          WPP_SF_(v24[1].Control.Logger, v25, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
          goto LABEL_83;
        }
      }
      if ( v29 )
      {
        if ( hstring )
        {
          Lpcwstr = Windows::Internal::String::_InitializeHelper(&callback, (const wchar_t *)hstring);
          if ( Lpcwstr >= 0 )
            goto LABEL_68;
        }
        else
        {
          Lpcwstr = -2147467261;
        }
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Control.Logger,
            0x31u,
            WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
            Lpcwstr);
        }
        goto $Exit_7;
      }
LABEL_68:
      v26 = callback._hstring;
      Lpcwstr = 0;
      callback._hstring = 0;
      *v36 = v26;
      goto $Exit_7;
    }
    p_flags = &v7->flags;
    if ( (v7->flags & 2) != 0 )
    {
LABEL_40:
      v15 = 1;
      v28 = 1;
      goto LABEL_41;
    }
    host._hstring = 0;
    Lpcwstr = (*(__int64 (__fastcall **)(HSTRING__ *, Windows::Internal::String *))(*(_QWORD *)request._hstring + 88LL))(
                request._hstring,
                &host);
    if ( Lpcwstr >= 0 )
    {
      tokenHandle = v7->tokenHandle;
      StringRawBuffer = WindowsGetStringRawBuffer(host._hstring, 0);
      Lpcwstr = VerifySsoHost(StringRawBuffer, tokenHandle);
      if ( Lpcwstr >= 0 )
      {
LABEL_39:
        Windows::Internal::String::~String(&host);
        v7 = v35;
        goto LABEL_40;
      }
      v7 = v35;
    }
    if ( !v34 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x2Du, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, Lpcwstr);
      }
      goto LABEL_32;
    }
    v18 = v34->lpVtbl;
    request._hstring = 0;
    if ( v18->get_Host(v34, &request._hstring) < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_31;
      }
      v20 = 43;
LABEL_30:
      WPP_SF_d(v19[1].Control.Logger, v20, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, Lpcwstr);
LABEL_31:
      Windows::Internal::String::~String(&request);
LABEL_32:
      Windows::Internal::String::~String(&host);
$Exit_7:
      if ( !v28 )
        goto LABEL_83;
      v6 = useSsoAppContainer;
      goto LABEL_71;
    }
    v21 = v7->tokenHandle;
    v22 = WindowsGetStringRawBuffer(request._hstring, 0);
    v23 = WindowsGetStringRawBuffer(host._hstring, 0);
    if ( VerifyMDMAuthentication(v23, v22, v21) < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_31;
      }
      v20 = 44;
      goto LABEL_30;
    }
    Windows::Internal::String::~String(&request);
    hstring = v32;
    goto LABEL_39;
  }
  SsoCallbackUri = CreateSsoCallbackUri(clientContext->tokenHandle, callbackAbsoluteUri);
  Lpcwstr = SsoCallbackUri;
  if ( SsoCallbackUri < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_83;
    }
    v12 = 40;
    v13 = SsoCallbackUri;
    goto LABEL_82;
  }
  p_flags = &v7->flags;
LABEL_71:
  if ( (*(_BYTE *)p_flags & 4) == 0 )
    *v6 = 1;
LABEL_83:
  Windows::Internal::String::~String(&callback);
  return (unsigned int)Lpcwstr;
}

```

## disassembly

```asm
0x18000f568  mov     rax, rsp
0x18000f56b  mov     [rax+20h], callbackAbsoluteUri
0x18000f56f  mov     [rax+18h], clientContext
0x18000f573  mov     [rax+10h], requestUri
0x18000f577  mov     [rax+8], callbackUri
0x18000f57b  push    rbp
0x18000f57c  push    rbx
0x18000f57d  push    rsi
0x18000f57e  push    rdi
0x18000f57f  push    r12
0x18000f581  push    r13
0x18000f583  push    r15
0x18000f585  mov     rbp, rsp
0x18000f588  sub     rsp, 40h
0x18000f58c  mov     rdi, [rbp+arg_28]
0x18000f590  xor     r12d, r12d
0x18000f593  mov     [callbackAbsoluteUri], r12
0x18000f596  mov     rbx, clientContext
0x18000f599  mov     [rbp+callback._hstring], r12
0x18000f59d  mov     [rbp+host._hstring], r12
0x18000f5a1  mov     [rdi], r12d
0x18000f5a4  test    callbackUri, callbackUri
0x18000f5a7  jnz     short loc_18000F5FC
0x18000f5a9  mov     callbackUri, [clientContext+20h]; clientTokenHandle
0x18000f5ad  mov     requestUri, callbackAbsoluteUri; callbackAbsoluteUri
0x18000f5b0  call    ?CreateSsoCallbackUri@@YAJPEAXPEAPEAUHSTRING__@@@Z; CreateSsoCallbackUri(void *,HSTRING__ * *)
0x18000f5b5  mov     esi, eax
0x18000f5b7  test    eax, eax
0x18000f5b9  js      short loc_18000F5C4
0x18000f5bb  lea     r12, [rbx+4]
0x18000f5bf  jmp     loc_18000F97C
0x18000f5c4  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f5cb  lea     r15, WPP_GLOBAL_Control
0x18000f5d2  cmp     callbackUri, r15
0x18000f5d5  jz      loc_18000F9F5
0x18000f5db  test    byte ptr [callbackUri+44h], 8
0x18000f5df  jz      loc_18000F9F5
0x18000f5e5  cmp     byte ptr [callbackUri+41h], 2
0x18000f5e9  jb      loc_18000F9F5
0x18000f5ef  mov     edx, 28h ; '('
0x18000f5f4  mov     r9d, eax
0x18000f5f7  jmp     loc_18000F9E5
0x18000f5fc  mov     rax, [callbackUri]
0x18000f5ff  lea     requestUri, [rbp+callback]
0x18000f603  mov     rax, [rax+30h]
0x18000f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f60c  mov     esi, eax
0x18000f60e  test    eax, eax
0x18000f610  js      loc_18000F9BE
0x18000f616  lea     requestUri, [rbp+host]; ppsz
0x18000f61a  lea     callbackUri, [rbp+callback]; this
0x18000f61e  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x18000f623  mov     esi, eax
0x18000f625  test    eax, eax
0x18000f627  js      loc_18000F9BE
0x18000f62d  mov     rdi, [rbp+host._hstring]
0x18000f631  lea     requestUri, aTestsso; "testsso."
0x18000f638  mov     callbackUri, rdi; String1
0x18000f63b  mov     [rbp+var_20], r12d
0x18000f63f  mov     r8d, 8; MaxCount
0x18000f645  mov     [rbp+var_1C], r12d
0x18000f649  mov     esi, r12d
0x18000f64c  mov     [rbp+var_8], rdi
0x18000f650  call    cs:__imp__wcsnicmp
0x18000f656  lea     r15, WPP_GLOBAL_Control
0x18000f65d  lea     r13, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids
0x18000f664  test    eax, eax
0x18000f666  jnz     short loc_18000F6D4
0x18000f668  lea     callbackUri, aEnabletestssop; "EnableTestSsoPrefix"
0x18000f66f  mov     [rbp+var_1C], 1
0x18000f676  add     rdi, 10h
0x18000f67a  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x18000f67f  test    eax, eax
0x18000f681  jz      short loc_18000F68A
0x18000f683  mov     esi, 1
0x18000f688  jmp     short loc_18000F6B3
0x18000f68a  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f691  cmp     callbackUri, r15
0x18000f694  jz      short loc_18000F6B3
0x18000f696  test    byte ptr [callbackUri+44h], 8
0x18000f69a  jz      short loc_18000F6B3
0x18000f69c  cmp     byte ptr [callbackUri+41h], 3
0x18000f6a0  jb      short loc_18000F6B3
0x18000f6a2  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f6a6  mov     edx, 2Ah ; '*'; id
0x18000f6ab  mov     clientContext, r13; TraceGuid
0x18000f6ae  call    WPP_SF_
0x18000f6b3  mov     r8d, 8; MaxCount
0x18000f6b9  lea     requestUri, aTestsso; "testsso."
0x18000f6c0  mov     callbackUri, rdi; String1
0x18000f6c3  call    cs:__imp__wcsnicmp
0x18000f6c9  test    eax, eax
0x18000f6cb  jz      short loc_18000F668
0x18000f6cd  mov     [rbp+var_20], esi
0x18000f6d0  mov     [rbp+var_8], rdi
0x18000f6d4  mov     r8d, 7; MaxCount
0x18000f6da  lea     requestUri, aMsApp; "ms-app:"
0x18000f6e1  mov     callbackUri, rdi; String1
0x18000f6e4  call    cs:__imp__wcsnicmp
0x18000f6ea  test    eax, eax
0x18000f6ec  jnz     loc_18000F82A
0x18000f6f2  lea     r12, [rbx+4]
0x18000f6f6  test    byte ptr [r12], 2
0x18000f6fb  jnz     loc_18000F822
0x18000f701  mov     callbackUri, [rbp+request._hstring]
0x18000f705  lea     requestUri, [rbp+host]
0x18000f709  mov     [rbp+host._hstring], 0
0x18000f711  mov     rax, [callbackUri]
0x18000f714  mov     rax, [rax+58h]
0x18000f718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f71d  mov     esi, eax
0x18000f71f  test    eax, eax
0x18000f721  js      short loc_18000F74C
0x18000f723  mov     callbackUri, [rbp+host._hstring]; string
0x18000f727  xor     edx, edx; length
0x18000f729  mov     rbx, [rbx+20h]
0x18000f72d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f733  mov     callbackUri, rax; host
0x18000f736  mov     requestUri, rbx; clientTokenHandle
0x18000f739  call    _VerifySsoHost
0x18000f73e  mov     esi, eax
0x18000f740  test    eax, eax
0x18000f742  jns     loc_18000F815
0x18000f748  mov     rbx, [rbp+arg_10]
0x18000f74c  mov     callbackUri, [rbp+arg_8]
0x18000f750  test    callbackUri, callbackUri
0x18000f753  jz      loc_18000F889
0x18000f759  mov     rax, [callbackUri]
0x18000f75c  lea     requestUri, [rbp+request]
0x18000f760  mov     [rbp+request._hstring], 0
0x18000f768  mov     rax, [rax+58h]
0x18000f76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f771  test    eax, eax
0x18000f773  jns     short loc_18000F7B8
0x18000f775  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f77c  cmp     callbackUri, r15
0x18000f77f  jz      short loc_18000F7A1
0x18000f781  test    byte ptr [callbackUri+44h], 8
0x18000f785  jz      short loc_18000F7A1
0x18000f787  cmp     byte ptr [callbackUri+41h], 2
0x18000f78b  jb      short loc_18000F7A1
0x18000f78d  mov     edx, 2Bh ; '+'; id
0x18000f792  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f796  mov     r9d, esi; _a1
0x18000f799  mov     clientContext, r13; TraceGuid
0x18000f79c  call    WPP_SF_d
0x18000f7a1  lea     callbackUri, [rbp+request]; this
0x18000f7a5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000f7aa  lea     callbackUri, [rbp+host]; this
0x18000f7ae  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000f7b3  jmp     $Exit_7
0x18000f7b8  mov     callbackUri, [rbp+request._hstring]; string
0x18000f7bc  xor     edx, edx; length
0x18000f7be  mov     rdi, [rbx+20h]
0x18000f7c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f7c8  mov     callbackUri, [rbp+host._hstring]; string
0x18000f7cc  xor     edx, edx; length
0x18000f7ce  mov     rbx, rax
0x18000f7d1  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f7d7  mov     clientContext, rdi; clientTokenHandle
0x18000f7da  mov     requestUri, rbx; request
0x18000f7dd  mov     callbackUri, rax; host
0x18000f7e0  call    VerifyMDMAuthentication
0x18000f7e5  test    eax, eax
0x18000f7e7  jns     short loc_18000F808
0x18000f7e9  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f7f0  cmp     callbackUri, r15
0x18000f7f3  jz      short loc_18000F7A1
0x18000f7f5  test    byte ptr [callbackUri+44h], 8
0x18000f7f9  jz      short loc_18000F7A1
0x18000f7fb  cmp     byte ptr [callbackUri+41h], 2
0x18000f7ff  jb      short loc_18000F7A1
0x18000f801  mov     edx, 2Ch ; ','
0x18000f806  jmp     short loc_18000F792
0x18000f808  lea     callbackUri, [rbp+request]; this
0x18000f80c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000f811  mov     rdi, [rbp+var_8]
0x18000f815  lea     callbackUri, [rbp+host]; this
0x18000f819  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000f81e  mov     rbx, [rbp+arg_10]
0x18000f822  mov     esi, 1
0x18000f827  mov     [rbp+var_20], esi
0x18000f82a  lea     r12, [rbx+4]
0x18000f82e  test    byte ptr [r12], 2
0x18000f833  jnz     loc_18000F940
0x18000f839  mov     eax, [rbp+arg_20]
0x18000f83c  bt      eax, 11h
0x18000f840  jnb     loc_18000F8C6
0x18000f846  test    esi, esi
0x18000f848  jnz     short loc_18000F8C6
0x18000f84a  mov     esi, 80070057h
0x18000f84f  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f856  cmp     callbackUri, r15
0x18000f859  jz      loc_18000F9F5
0x18000f85f  test    byte ptr [callbackUri+44h], 8
0x18000f863  jz      loc_18000F9F5
0x18000f869  cmp     byte ptr [callbackUri+41h], 2
0x18000f86d  jb      loc_18000F9F5
0x18000f873  mov     edx, 2Eh ; '.'; id
0x18000f878  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f87c  mov     clientContext, r13; TraceGuid
0x18000f87f  call    WPP_SF_
0x18000f884  jmp     loc_18000F9F5
0x18000f889  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f890  cmp     callbackUri, r15
0x18000f893  jz      loc_18000F7AA
0x18000f899  test    byte ptr [callbackUri+44h], 8
0x18000f89d  jz      loc_18000F7AA
0x18000f8a3  cmp     byte ptr [callbackUri+41h], 2
0x18000f8a7  jb      loc_18000F7AA
0x18000f8ad  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f8b1  mov     edx, 2Dh ; '-'; id
0x18000f8b6  mov     r9d, esi; _a1
0x18000f8b9  mov     clientContext, r13; TraceGuid
0x18000f8bc  call    WPP_SF_d
0x18000f8c1  jmp     loc_18000F7AA
0x18000f8c6  bt      eax, 13h
0x18000f8ca  jnb     short loc_18000F903
0x18000f8cc  test    esi, esi
0x18000f8ce  jnz     short loc_18000F903
0x18000f8d0  mov     esi, 80070057h
0x18000f8d5  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f8dc  cmp     callbackUri, r15
0x18000f8df  jz      loc_18000F9F5
0x18000f8e5  test    byte ptr [callbackUri+44h], 8
0x18000f8e9  jz      loc_18000F9F5
0x18000f8ef  cmp     byte ptr [callbackUri+41h], 2
0x18000f8f3  jb      loc_18000F9F5
0x18000f8f9  mov     edx, 2Fh ; '/'
0x18000f8fe  jmp     loc_18000F878
0x18000f903  bt      eax, 14h
0x18000f907  jnb     short loc_18000F940
0x18000f909  test    esi, esi
0x18000f90b  jnz     short loc_18000F940
0x18000f90d  mov     esi, 80070057h
0x18000f912  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f919  cmp     callbackUri, r15
0x18000f91c  jz      loc_18000F9F5
0x18000f922  test    byte ptr [callbackUri+44h], 8
0x18000f926  jz      loc_18000F9F5
0x18000f92c  cmp     byte ptr [callbackUri+41h], 2
0x18000f930  jb      loc_18000F9F5
0x18000f936  mov     edx, 30h ; '0'
0x18000f93b  jmp     loc_18000F878
0x18000f940  cmp     [rbp+var_1C], 0
0x18000f944  jz      short loc_18000F95D
0x18000f946  test    rdi, rdi
0x18000f949  jz      short loc_18000F98B
0x18000f94b  mov     requestUri, rdi; str
0x18000f94e  lea     callbackUri, [rbp+callback]; this
0x18000f952  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18000f957  mov     esi, eax
0x18000f959  test    eax, eax
0x18000f95b  js      short loc_18000F990
0x18000f95d  mov     rax, [rbp+callback._hstring]
0x18000f961  xor     esi, esi
0x18000f963  mov     callbackUri, [rbp+arg_18]
0x18000f967  mov     [rbp+callback._hstring], 0
0x18000f96f  mov     [callbackUri], rax
0x18000f972  cmp     [rbp+var_20], 0
0x18000f976  jz      short loc_18000F9F5
0x18000f978  mov     rdi, [rbp+arg_28]
0x18000f97c  test    byte ptr [r12], 4
0x18000f981  jnz     short loc_18000F9F5
0x18000f983  mov     dword ptr [rdi], 1
0x18000f989  jmp     short loc_18000F9F5
0x18000f98b  mov     esi, 80004003h
0x18000f990  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f997  cmp     callbackUri, r15
0x18000f99a  jz      short $Exit_7
0x18000f99c  test    byte ptr [callbackUri+44h], 8
0x18000f9a0  jz      short $Exit_7
0x18000f9a2  cmp     byte ptr [callbackUri+41h], 2
0x18000f9a6  jb      short $Exit_7
0x18000f9a8  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f9ac  mov     edx, 31h ; '1'; id
0x18000f9b1  mov     r9d, esi; _a1
0x18000f9b4  mov     clientContext, r13; TraceGuid
0x18000f9b7  call    WPP_SF_d
0x18000f9bc  jmp     short $Exit_7
0x18000f9be  mov     callbackUri, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f9c5  lea     r15, WPP_GLOBAL_Control
0x18000f9cc  cmp     callbackUri, r15
0x18000f9cf  jz      short loc_18000F9F5
0x18000f9d1  test    byte ptr [callbackUri+44h], 8
0x18000f9d5  jz      short loc_18000F9F5
0x18000f9d7  cmp     byte ptr [callbackUri+41h], 2
0x18000f9db  jb      short loc_18000F9F5
0x18000f9dd  mov     edx, 29h ; ')'; id
0x18000f9e2  mov     r9d, esi; _a1
0x18000f9e5  mov     callbackUri, [callbackUri+38h]; Logger
0x18000f9e9  lea     clientContext, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000f9f0  call    WPP_SF_d
0x18000f9f5  lea     callbackUri, [rbp+callback]; this
0x18000f9f9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000f9fe  mov     eax, esi
0x18000fa00  add     rsp, 40h
0x18000fa04  pop     r15
0x18000fa06  pop     r13
0x18000fa08  pop     r12
  ... truncated ...
```
