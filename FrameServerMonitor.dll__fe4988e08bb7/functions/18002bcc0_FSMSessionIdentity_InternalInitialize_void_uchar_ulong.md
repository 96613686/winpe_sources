# FSMSessionIdentity::InternalInitialize(void *,uchar *,ulong)

- ea: `0x18002bcc0`
- end: `0x18002c8a7`
- name: `?InternalInitialize@FSMSessionIdentity@@MEAAJPEAXPEAEK@Z`
- size: `3047`
- prototype: `__int64 __fastcall(FSMSessionIdentity *__hidden this, RPC_BINDING_HANDLE BindingHandle, UINT8 *pBuf, UINT cbBufSize)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180002f90`
- `0x180003274`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x180006ffc`
- `0x180007040`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d208`
- `0x18000d240`
- `0x18000d330`
- `0x18000d594`
- `0x18000d62c`
- `0x18000d940`
- `0x18000e25c`
- `0x180011438`
- `0x180025bf0`
- `0x18002bcc0`
- `0x18002c8b0`
- `0x18002cb2c`
- `0x18002cebc`
- `0x18002cef0`
- `0x18002cfb8`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18002fd04`
- `0x18003ff38`
- `0x180041244`
- `0x1800416dc`
- `0x180041bc0`
- `0x180041ca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c61e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c61e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c752`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c2a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c2a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c290`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c01c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c33c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c35b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c01c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c33c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c35b`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002be58`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002be9d`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002be58`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002be9d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002c11c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002c12c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002c11c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002c12c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002c061`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002c072`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002c061`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002c072`
- `RPCRT4!RpcRevertToSelf` at `0x18002c859`
- `RPCRT4!RpcRevertToSelf` at `0x18002c859`
- `RPCRT4!RpcStringBindingParseW` at `0x18002bf48`
- `RPCRT4!RpcStringBindingParseW` at `0x18002bf9e`
- `RPCRT4!RpcStringBindingParseW` at `0x18002bf48`
- `RPCRT4!RpcStringBindingParseW` at `0x18002bf9e`
- `RPCRT4!RpcImpersonateClient` at `0x18002c248`
- `RPCRT4!RpcImpersonateClient` at `0x18002c255`
- `RPCRT4!RpcImpersonateClient` at `0x18002c248`
- `RPCRT4!RpcImpersonateClient` at `0x18002c255`
- `RPCRT4!RpcStringFreeW` at `0x18002be3b`
- `RPCRT4!RpcStringFreeW` at `0x18002be80`
- `RPCRT4!RpcStringFreeW` at `0x18002bf1a`
- `RPCRT4!RpcStringFreeW` at `0x18002bf70`
- `RPCRT4!RpcStringFreeW` at `0x18002be3b`
- `RPCRT4!RpcStringFreeW` at `0x18002be80`
- `RPCRT4!RpcStringFreeW` at `0x18002bf1a`
- `RPCRT4!RpcStringFreeW` at `0x18002bf70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c307`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c502`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c53e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c5c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c678`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c701`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c307`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c502`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c53e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c5c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c678`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c701`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c614`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c748`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c614`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c748`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002c15b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002c15b`
- `MFPlat!MFCreateAttributes` at `0x18002bdb6`
- `MFPlat!MFCreateAttributes` at `0x18002bdb6`
- `MFPlat!MFInitAttributesFromBlob` at `0x18002bdf6`
- `MFPlat!MFInitAttributesFromBlob` at `0x18002bdf6`

## pseudocode

```c
__int64 __fastcall FSMSessionIdentity::InternalInitialize(
        FSMSessionIdentity *this,
        RPC_BINDING_HANDLE BindingHandle,
        UINT8 *pBuf,
        UINT cbBufSize)
{
  int v5; // r13d
  signed int v9; // esi
  HRESULT v10; // eax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rbx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rbx
  unsigned __int16 *v16; // rbx
  int v17; // ebx
  GuidTrace *v18; // rax
  const char *v19; // rax
  int v20; // edx
  int v21; // r8d
  HANDLE v22; // rax
  HANDLE v23; // rbx
  signed int LastError; // eax
  const struct std::nothrow_t *v25; // rax
  unsigned __int16 *v26; // rdx
  __int64 v27; // rdx
  HANDLE *v28; // r12
  HANDLE CurrentThread; // rax
  signed int v30; // eax
  HANDLE v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r8
  bool v35; // al
  bool v36; // zf
  bool v37; // al
  __int64 v38; // rax
  bool v39; // al
  __int64 v40; // rcx
  __int128 v41; // rax
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r8
  HANDLE v44; // rcx
  HANDLE v45; // rcx
  const struct std::nothrow_t *unique; // rax
  PSID *v47; // rbx
  signed int v48; // eax
  signed int v49; // eax
  HANDLE v50; // rcx
  const struct std::nothrow_t *v51; // rax
  PSID *v52; // rbx
  signed int v53; // eax
  signed int v54; // eax
  char v55; // bl
  const char *v56; // rax
  __int64 v58; // [rsp+38h] [rbp-C8h]
  __int64 ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  RPC_WSTR v60; // [rsp+48h] [rbp-B8h] BYREF
  RPC_WSTR StringBinding; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v62; // [rsp+58h] [rbp-A8h]
  RPC_WSTR Protseq; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v66; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v67; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ProcessHandle; // [rsp+88h] [rbp-78h] BYREF
  void **v69; // [rsp+90h] [rbp-70h] BYREF
  __int128 v70; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h]
  _DWORD RpcCallAttributes[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v73[36]; // [rsp+B8h] [rbp-48h] BYREF
  int v74; // [rsp+DCh] [rbp-24h]
  int v75; // [rsp+11Ch] [rbp+1Ch]
  char *v76; // [rsp+120h] [rbp+20h]

  v5 = 0;
  v62 = 0;
  BYTE4(ReturnLength) = 0;
  ProcessHandle = 0;
  v66 = 0;
  TokenInformation = 0;
  v67 = 0;
  LODWORD(ReturnLength) = 0;
  StringBinding = 0;
  Protseq = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qqdqd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      14,
      &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
      this,
      BindingHandle,
      *((_DWORD *)this + 17),
      pBuf,
      cbBufSize,
      ReturnLength);
  if ( !BindingHandle )
  {
    v9 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
        this,
        -2147024809);
    goto LABEL_126;
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((char *)this + 280);
  v10 = MFCreateAttributes((IMFAttributes **)this + 35, 0);
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_125;
    v12 = 16;
    goto LABEL_9;
  }
  v9 = 0;
  if ( pBuf && cbBufSize )
  {
    v10 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 35), pBuf, cbBufSize);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( g_wppLevels )
      {
        v12 = 17;
LABEL_9:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids, this, v10);
        goto LABEL_125;
      }
      goto LABEL_125;
    }
    v9 = 0;
  }
  StringBinding = 0;
  if ( RpcBindingToStringBindingW(BindingHandle, &StringBinding) )
  {
    v13 = StringBinding;
    if ( StringBinding )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
      v60 = v13;
      RpcStringFreeW(&v60);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
    }
    StringBinding = 0;
    v9 = RpcBindingToStringBindingW(BindingHandle, &StringBinding) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_125;
    v14 = 18;
    goto LABEL_124;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      19,
      (unsigned int)&WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
      (_DWORD)this,
      (__int64)StringBinding);
  v15 = Protseq;
  if ( Protseq )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&String);
    v60 = v15;
    RpcStringFreeW(&v60);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&String);
  }
  Protseq = 0;
  if ( RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0) )
  {
    v16 = Protseq;
    if ( Protseq )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
      v60 = v16;
      RpcStringFreeW(&v60);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
    }
    Protseq = 0;
    v9 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_125;
    v14 = 20;
    goto LABEL_124;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      21,
      (unsigned int)&WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
      (_DWORD)this,
      (__int64)Protseq);
  if ( CompareStringOrdinal(Protseq, -1, L"ncacn_hvsocket", -1, 1) == 2 )
  {
    memset_0(v73, 0, 0x64u);
    RpcCallAttributes[0] = 3;
    v76 = (char *)this + 256;
    RpcCallAttributes[1] = 224;
    v75 = 16;
    if ( !RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes) )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v17 = *((_DWORD *)this + 61);
        v18 = GuidTrace::GuidTrace((GuidTrace *)&v69, (const struct _GUID *)this + 16);
        v19 = GuidTrace::GetString(v18);
        LODWORD(v58) = v74;
        WPP_SF_qsDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v20,
          v21,
          (_DWORD)this,
          (__int64)v19,
          v17,
          v73[32],
          v58,
          ReturnLength);
        v5 = 1;
        v62 = 1;
      }
      if ( (v5 & 1) != 0 )
      {
        v62 = v5 & 0xFFFFFFFE;
        FSString::~FSString((FSString *)&v69, v11);
      }
      goto LABEL_125;
    }
    v9 = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_125;
    v14 = 22;
    goto LABEL_124;
  }
  if ( I_RpcBindingInqLocalClientPID(BindingHandle, (unsigned int *)this + 61) )
  {
    v9 = I_RpcBindingInqLocalClientPID(BindingHandle, (unsigned int *)this + 61) | 0x80010000;
    if ( !g_wppLevels )
      goto LABEL_125;
    v14 = 24;
    goto LABEL_124;
  }
  v22 = OpenProcess(0x101000u, 0, *((_DWORD *)this + 61));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &ProcessHandle,
    v22);
  v23 = ProcessHandle;
  if ( !ProcessHandle )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( !g_wppLevels )
      goto LABEL_125;
    v14 = 25;
    goto LABEL_124;
  }
  LODWORD(String) = 0;
  if ( (int)FSGetProcessImageName(ProcessHandle, 0, 0, (unsigned int *)&String) < 0 )
  {
LABEL_57:
    if ( RpcImpersonateClient(BindingHandle) )
    {
      v9 = RpcImpersonateClient(BindingHandle) | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_125;
      v14 = 28;
      goto LABEL_124;
    }
    v28 = (HANDLE *)((char *)this + 272);
    BYTE4(ReturnLength) = 1;
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 272,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)this + 34) )
    {
      v30 = GetLastError();
      v9 = v30;
      if ( v30 > 0 )
        v9 = (unsigned __int16)v30 | 0x80070000;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_125;
        v14 = 29;
        goto LABEL_124;
      }
    }
    v31 = *v28;
    LODWORD(ReturnLength) = 0;
    GetTokenInformation(v31, TokenSessionId, (char *)this + 240, 4u, (PDWORD)&ReturnLength);
    if ( FSCreatePackageFamilyNameTag(v23, (unsigned __int16 *)this + 40, v32, &v66) >= 0 )
    {
      if ( CompareStringOrdinal(L"pfn:windows.immersivecontrolpanel_cw5n1h2txyewy", -1, (LPCWCH)this + 40, -1, 1) == 2
        || CompareStringOrdinal(L"pfn:BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy", -1, (LPCWCH)this + 40, -1, 1) == 2 )
      {
        v33 = 8;
      }
      else
      {
        v33 = 0;
      }
      *((_QWORD *)this + 9) &= ~8uLL;
      *((_QWORD *)this + 9) |= v33;
    }
    v34 = *((_QWORD *)this + 9);
    if ( !v34 )
    {
      v35 = FSIsAdmin(*v28);
      *((_QWORD *)this + 9) &= ~1uLL;
      v36 = (v35 | *((_QWORD *)this + 9)) == 0;
      *((_QWORD *)this + 9) |= v35;
      v34 = *((_QWORD *)this + 9);
      if ( v36 )
      {
        v37 = FSIsLocalSystem(*v28);
        *((_QWORD *)this + 9) &= ~2uLL;
        v38 = 2LL * v37;
        v36 = (v38 | *((_QWORD *)this + 9)) == 0;
        *((_QWORD *)this + 9) |= v38;
        v34 = *((_QWORD *)this + 9);
        if ( v36 )
        {
          v39 = FSIsFrameServerProcess(*v28);
          *((_QWORD *)this + 9) &= ~4uLL;
          *((_QWORD *)this + 9) |= 4LL * v39;
          v34 = *((_QWORD *)this + 9);
        }
      }
    }
    if ( *((_DWORD *)this + 17) == 4 && (v34 & 8) == 0 )
    {
      v40 = v34 & 3;
      v41 = -(__int128)(v34 & 3);
      v34 &= ~8uLL;
      v42 = v34 | BYTE8(v41) & 8;
      *((_QWORD *)this + 9) = v42;
      if ( !v40 )
      {
        v42 &= ~8uLL;
        *((_QWORD *)this + 9) = v42;
      }
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qddds(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          (v42 >> 3) & 1,
          (unsigned int)"false",
          (_DWORD)this,
          (v42 & 8) != 0,
          *((_DWORD *)this + 18) & 1,
          (v42 & 2) != 0,
          (__int64)"false");
    }
    if ( *((_DWORD *)this + 17) == 8 )
    {
      v43 = *((_QWORD *)this + 9) & 0xFFFFFFFFFFFFFFDFuLL
          | ((unsigned int)MFGetAttributeUINT32(
                             *((_QWORD *)this + 35),
                             MF_FRAMESERVER_ATTRIBUTE_ENABLE_SHARED_EXTENDED_OPERATIONS,
                             v34) != 0
           ? 0x20
           : 0);
      *((_QWORD *)this + 9) = v43;
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          31,
          &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
          this,
          (v43 >> 5) & 1,
          v43 & 1,
          (v43 >> 1) & 1);
    }
    v44 = *v28;
    LODWORD(ReturnLength) = 0;
    if ( GetTokenInformation(v44, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&ReturnLength) && TokenInformation )
    {
      v45 = *v28;
      *((_QWORD *)this + 9) |= 0x10uLL;
      LODWORD(ReturnLength) = 0;
      if ( !GetTokenInformation(v45, TokenAppContainerSid, 0, 0, (PDWORD)&ReturnLength)
        && GetLastError() == 122
        && (_DWORD)ReturnLength )
      {
        unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(
                                                  &v60,
                                                  (unsigned int)ReturnLength);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v67, unique);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v60);
        v47 = (PSID *)v67;
        if ( !v67 )
        {
          v9 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_126;
          v27 = (unsigned int)((_DWORD)v67 + 32);
          goto LABEL_52;
        }
        if ( !GetTokenInformation(*v28, TokenAppContainerSid, v67, ReturnLength, (PDWORD)&ReturnLength) )
        {
          v48 = GetLastError();
          v9 = v48;
          if ( v48 > 0 )
            v9 = (unsigned __int16)v48 | 0x80070000;
          if ( v9 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_125;
            v14 = 33;
            goto LABEL_124;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 232,
          0);
        if ( !ConvertSidToStringSidW(*v47, (LPWSTR *)this + 29) )
        {
          v49 = GetLastError();
          v9 = v49;
          if ( v49 > 0 )
            v9 = (unsigned __int16)v49 | 0x80070000;
          if ( v9 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_125;
            v14 = 34;
            goto LABEL_124;
          }
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 232,
          0);
      }
    }
    v50 = *v28;
    LODWORD(ReturnLength) = 0;
    if ( GetTokenInformation(v50, TokenUser, 0, 0, (PDWORD)&ReturnLength)
      || GetLastError() != 122
      || !(_DWORD)ReturnLength )
    {
      goto LABEL_125;
    }
    v51 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v60, (unsigned int)ReturnLength);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v67, v51);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v60);
    v52 = (PSID *)v67;
    if ( v67 )
    {
      if ( GetTokenInformation(*v28, TokenUser, v67, ReturnLength, (PDWORD)&ReturnLength) )
        goto LABEL_118;
      v53 = GetLastError();
      v9 = v53;
      if ( v53 > 0 )
        v9 = (unsigned __int16)v53 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_118:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 224,
          0);
        if ( ConvertSidToStringSidW(*v52, (LPWSTR *)this + 28) )
          goto LABEL_125;
        v54 = GetLastError();
        v9 = v54;
        if ( v54 > 0 )
          v9 = (unsigned __int16)v54 | 0x80070000;
        if ( v9 >= 0 )
          goto LABEL_128;
        if ( !g_wppLevels )
          goto LABEL_125;
        v14 = 37;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_125;
        v14 = 36;
      }
LABEL_124:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids, this, v9);
      goto LABEL_125;
    }
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_126;
    v27 = (unsigned int)((_DWORD)v67 + 35);
LABEL_52:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
      this,
      -2147024882);
    goto LABEL_126;
  }
  v25 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v60, (unsigned int)String);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 31, v25);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v60);
  v26 = (unsigned __int16 *)*((_QWORD *)this + 31);
  if ( !v26 )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_126;
    v27 = 26;
    goto LABEL_52;
  }
  v10 = FSGetProcessImageName(v23, v26, (unsigned int)String, (unsigned int *)&String);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v9 = 0;
    goto LABEL_57;
  }
  if ( g_wppLevels )
  {
    v12 = 27;
    goto LABEL_9;
  }
LABEL_125:
  if ( v9 < 0 )
  {
LABEL_126:
    FSMSessionIdentity::InternalReset(this);
    if ( byte_18005E5A5 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 38, &WPP_ece4d80bc92c354c149257d3891f069e_Traceguids, this, v9);
    goto LABEL_132;
  }
LABEL_128:
  v55 = v62;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v69 = &SensorGroupBlobHeaderTrace::`vftable';
    v71 = 0;
    v55 = v62 | 2;
    v70 = 0;
    FSMSessionIdentityTracer::SetInfo((FSMSessionIdentityTracer *)&v69, this);
    v56 = FSString::GetString((FSString *)&v70);
    WPP_SF_qDs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      39,
      (unsigned int)&WPP_ece4d80bc92c354c149257d3891f069e_Traceguids,
      (_DWORD)this,
      v9,
      (__int64)v56);
  }
  if ( (v55 & 2) != 0 )
  {
    v69 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)&v70, v11);
  }
LABEL_132:
  if ( BYTE4(ReturnLength) )
    RpcRevertToSelf();
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Protseq);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v67);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002bcc0  push    rbp
0x18002bcc2  push    rbx
0x18002bcc3  push    rsi
0x18002bcc4  push    rdi
0x18002bcc5  push    r12
0x18002bcc7  push    r13
0x18002bcc9  push    r14
0x18002bccb  push    r15
0x18002bccd  lea     rbp, [rsp-48h]
0x18002bcd2  sub     rsp, 148h
0x18002bcd9  mov     rax, cs:__security_cookie
0x18002bce0  xor     rax, rsp
0x18002bce3  mov     [rbp+80h+var_50], rax
0x18002bce7  xor     esi, esi
0x18002bce9  mov     edi, r9d
0x18002bcec  mov     r13d, esi
0x18002bcef  mov     [rsp+180h+var_128], esi
0x18002bcf3  mov     [rsp+180h+var_13C], sil
0x18002bcf8  mov     rbx, r8
0x18002bcfb  mov     [rbp+80h+ProcessHandle], rsi
0x18002bcff  mov     r12, rdx
0x18002bd02  mov     [rsp+180h+var_108], esi
0x18002bd06  mov     r14, rcx
0x18002bd09  mov     [rsp+180h+TokenInformation], esi
0x18002bd0d  mov     [rbp+80h+var_100], rsi
0x18002bd11  mov     [rsp+180h+ReturnLength], esi
0x18002bd15  mov     [rsp+180h+StringBinding], rsi
0x18002bd1a  mov     [rsp+180h+Protseq], rsi
0x18002bd1f  cmp     cs:byte_18005E5A5, 8
0x18002bd26  jb      short loc_18002BD5E
0x18002bd28  mov     eax, [rcx+44h]
0x18002bd2b  lea     edx, [rsi+0Eh]
0x18002bd2e  mov     dword ptr [rsp+180h+var_148], r9d
0x18002bd33  lea     r8, WPP_ece4d80bc92c354c149257d3891f069e_Traceguids
0x18002bd3a  mov     r9, rcx
0x18002bd3d  mov     [rsp+180h+var_150], rbx
0x18002bd42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd49  mov     dword ptr [rsp+180h+NetworkOptions], eax
0x18002bd4d  mov     [rsp+180h+Endpoint], r12
0x18002bd52  mov     rcx, [rcx+0D8h]
0x18002bd59  call    WPP_SF_qqdqd
0x18002bd5e  test    r12, r12
0x18002bd61  jnz     short loc_18002BDA2
0x18002bd63  mov     esi, 80070057h
0x18002bd68  lea     r15d, [r12+1]
0x18002bd6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002bd74  jb      loc_18002C798
0x18002bd7a  lea     edx, [r12+0Fh]
0x18002bd7f  mov     dword ptr [rsp+180h+Endpoint], esi
0x18002bd83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd8a  lea     r8, WPP_ece4d80bc92c354c149257d3891f069e_Traceguids
0x18002bd91  mov     r9, r14
0x18002bd94  mov     rcx, [rcx+10h]
0x18002bd98  call    WPP_SF_qD
0x18002bd9d  jmp     loc_18002C798
0x18002bda2  lea     r15, [r14+118h]
0x18002bda9  mov     rcx, r15
0x18002bdac  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18002bdb1  xor     edx, edx; cInitialSize
0x18002bdb3  mov     rcx, r15; ppMFAttributes
0x18002bdb6  call    cs:__imp_MFCreateAttributes
0x18002bdbc  mov     esi, eax
0x18002bdbe  test    eax, eax
0x18002bdc0  jns     short loc_18002BDE2
0x18002bdc2  mov     r15d, 1
0x18002bdc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002bdcf  jb      loc_18002C794
0x18002bdd5  lea     edx, [r15+0Fh]
0x18002bdd9  mov     dword ptr [rsp+180h+Endpoint], eax
0x18002bddd  jmp     loc_18002C77A
0x18002bde2  xor     esi, esi
0x18002bde4  test    rbx, rbx
0x18002bde7  jz      short loc_18002BE1D
0x18002bde9  test    edi, edi
0x18002bdeb  jz      short loc_18002BE1D
0x18002bded  mov     rcx, [r15]; pAttributes
0x18002bdf0  mov     r8d, edi; cbBufSize
0x18002bdf3  mov     rdx, rbx; pBuf
0x18002bdf6  call    cs:__imp_MFInitAttributesFromBlob
0x18002bdfc  mov     esi, eax
0x18002bdfe  test    eax, eax
0x18002be00  jns     short loc_18002BE1B
0x18002be02  mov     r15d, 1
0x18002be08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002be0f  jb      loc_18002C794
0x18002be15  lea     edx, [r15+10h]
0x18002be19  jmp     short loc_18002BDD9
0x18002be1b  xor     esi, esi
0x18002be1d  mov     rbx, [rsp+180h+StringBinding]
0x18002be22  test    rbx, rbx
0x18002be25  jz      short loc_18002BE4B
0x18002be27  lea     rcx, [rsp+180h+var_138]; this
0x18002be2c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002be31  lea     rcx, [rsp+180h+String]; String
0x18002be36  mov     [rsp+180h+String], rbx
0x18002be3b  call    cs:__imp_RpcStringFreeW
0x18002be41  lea     rcx, [rsp+180h+var_138]; this
0x18002be46  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002be4b  lea     rdx, [rsp+180h+StringBinding]; StringBinding
0x18002be50  mov     [rsp+180h+StringBinding], rsi
0x18002be55  mov     rcx, r12; Binding
0x18002be58  call    cs:__imp_RpcBindingToStringBindingW
0x18002be5e  test    eax, eax
0x18002be60  jz      short loc_18002BEC7
0x18002be62  mov     rbx, [rsp+180h+StringBinding]
0x18002be67  test    rbx, rbx
0x18002be6a  jz      short loc_18002BE90
0x18002be6c  lea     rcx, [rsp+180h+var_108]; this
0x18002be71  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002be76  lea     rcx, [rsp+180h+var_138]; String
0x18002be7b  mov     [rsp+180h+var_138], rbx
0x18002be80  call    cs:__imp_RpcStringFreeW
0x18002be86  lea     rcx, [rsp+180h+var_108]; this
0x18002be8b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002be90  lea     rdx, [rsp+180h+StringBinding]; StringBinding
0x18002be95  mov     [rsp+180h+StringBinding], rsi
0x18002be9a  mov     rcx, r12; Binding
0x18002be9d  call    cs:__imp_RpcBindingToStringBindingW
0x18002bea3  mov     esi, eax
0x18002bea5  or      esi, 80010000h
0x18002beab  mov     r15d, 1
0x18002beb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002beb8  jb      loc_18002C794
0x18002bebe  lea     edx, [r15+11h]
0x18002bec2  jmp     loc_18002C776
0x18002bec7  cmp     cs:byte_18005E5A5, 8
0x18002bece  jb      short loc_18002BEFC
0x18002bed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bed7  lea     r8, WPP_ece4d80bc92c354c149257d3891f069e_Traceguids
0x18002bede  mov     rax, [rsp+180h+StringBinding]
0x18002bee3  mov     edx, 13h
0x18002bee8  mov     r9, r14
0x18002beeb  mov     [rsp+180h+Endpoint], rax
0x18002bef0  mov     rcx, [rcx+0D8h]
0x18002bef7  call    WPP_SF_qS
0x18002befc  mov     rbx, [rsp+180h+Protseq]
0x18002bf01  test    rbx, rbx
0x18002bf04  jz      short loc_18002BF2A
0x18002bf06  lea     rcx, [rsp+180h+String]; this
0x18002bf0b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002bf10  lea     rcx, [rsp+180h+var_138]; String
0x18002bf15  mov     [rsp+180h+var_138], rbx
0x18002bf1a  call    cs:__imp_RpcStringFreeW
0x18002bf20  lea     rcx, [rsp+180h+String]; this
0x18002bf25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002bf2a  mov     rcx, [rsp+180h+StringBinding]; StringBinding
0x18002bf2f  lea     r8, [rsp+180h+Protseq]; Protseq
0x18002bf34  mov     [rsp+180h+NetworkOptions], rsi; NetworkOptions
0x18002bf39  xor     r9d, r9d; NetworkAddr
0x18002bf3c  xor     edx, edx; ObjUuid
0x18002bf3e  mov     [rsp+180h+Endpoint], rsi; Endpoint
0x18002bf43  mov     [rsp+180h+Protseq], rsi
0x18002bf48  call    cs:__imp_RpcStringBindingParseW
0x18002bf4e  test    eax, eax
0x18002bf50  jz      short loc_18002BFC8
0x18002bf52  mov     rbx, [rsp+180h+Protseq]
0x18002bf57  test    rbx, rbx
0x18002bf5a  jz      short loc_18002BF80
0x18002bf5c  lea     rcx, [rsp+180h+var_108]; this
0x18002bf61  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002bf66  lea     rcx, [rsp+180h+var_138]; String
0x18002bf6b  mov     [rsp+180h+var_138], rbx
0x18002bf70  call    cs:__imp_RpcStringFreeW
0x18002bf76  lea     rcx, [rsp+180h+var_108]; this
0x18002bf7b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002bf80  mov     rcx, [rsp+180h+StringBinding]; StringBinding
0x18002bf85  lea     r8, [rsp+180h+Protseq]; Protseq
0x18002bf8a  mov     [rsp+180h+NetworkOptions], rsi; NetworkOptions
0x18002bf8f  xor     r9d, r9d; NetworkAddr
0x18002bf92  xor     edx, edx; ObjUuid
0x18002bf94  mov     [rsp+180h+Endpoint], rsi; Endpoint
0x18002bf99  mov     [rsp+180h+Protseq], rsi
0x18002bf9e  call    cs:__imp_RpcStringBindingParseW
0x18002bfa4  mov     esi, eax
0x18002bfa6  or      esi, 80010000h
0x18002bfac  mov     r15d, 1
0x18002bfb2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002bfb9  jb      loc_18002C794
0x18002bfbf  lea     edx, [r15+13h]
0x18002bfc3  jmp     loc_18002C776
0x18002bfc8  cmp     cs:byte_18005E5A5, 8
0x18002bfcf  jb      short loc_18002BFFD
0x18002bfd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfd8  lea     r8, WPP_ece4d80bc92c354c149257d3891f069e_Traceguids
0x18002bfdf  mov     rax, [rsp+180h+Protseq]
0x18002bfe4  mov     edx, 15h
0x18002bfe9  mov     r9, r14
0x18002bfec  mov     [rsp+180h+Endpoint], rax
0x18002bff1  mov     rcx, [rcx+0D8h]
0x18002bff8  call    WPP_SF_qS
0x18002bffd  mov     rcx, [rsp+180h+Protseq]; lpString1
0x18002c002  lea     r8, Protseq; "ncacn_hvsocket"
0x18002c009  or      eax, 0FFFFFFFFh
0x18002c00c  mov     r15d, 1
0x18002c012  mov     r9d, eax; cchCount2
0x18002c015  mov     dword ptr [rsp+180h+Endpoint], r15d; bIgnoreCase
0x18002c01a  mov     edx, eax; cchCount1
0x18002c01c  call    cs:__imp_CompareStringOrdinal
0x18002c022  cmp     eax, 2
0x18002c025  jnz     loc_18002C10F
0x18002c02b  xor     edx, edx; Val
0x18002c02d  lea     r8d, [r15+63h]; Size
0x18002c031  lea     rcx, [rbp+80h+var_C8]; void *
0x18002c035  call    memset_0
0x18002c03a  lea     rdi, [r14+100h]
0x18002c041  mov     [rbp+80h+RpcCallAttributes], 3
0x18002c048  lea     rdx, [rbp+80h+RpcCallAttributes]; RpcCallAttributes
0x18002c04c  mov     [rbp+80h+var_60], rdi
0x18002c050  mov     rcx, r12; ClientBinding
0x18002c053  mov     [rbp+80h+var_CC], 0E0h
0x18002c05a  mov     [rbp+80h+var_64], 10h
0x18002c061  call    cs:__imp_RpcServerInqCallAttributesW
0x18002c067  test    eax, eax
0x18002c069  jz      short loc_18002C096
0x18002c06b  lea     rdx, [rbp+80h+RpcCallAttributes]; RpcCallAttributes
0x18002c06f  mov     rcx, r12; ClientBinding
0x18002c072  call    cs:__imp_RpcServerInqCallAttributesW
0x18002c078  mov     esi, eax
0x18002c07a  or      esi, 80010000h
0x18002c080  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002c087  jb      loc_18002C794
0x18002c08d  lea     edx, [r15+15h]
0x18002c091  jmp     loc_18002C776
0x18002c096  cmp     cs:byte_18005E5A5, 8
0x18002c09d  jb      short loc_18002C0EF
0x18002c09f  mov     ebx, [r14+0F4h]
0x18002c0a6  lea     rcx, [rbp+80h+var_F0]; this
0x18002c0aa  mov     rdx, rdi; struct _GUID *
0x18002c0ad  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18002c0b2  mov     rcx, rax; this
0x18002c0b5  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18002c0ba  mov     ecx, [rbp+80h+var_A4]
0x18002c0bd  mov     r9, r14
0x18002c0c0  mov     dword ptr [rsp+180h+var_148], ecx
0x18002c0c4  mov     ecx, [rbp+80h+var_A8]
0x18002c0c7  mov     dword ptr [rsp+180h+var_150], ecx
0x18002c0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0d2  mov     dword ptr [rsp+180h+NetworkOptions], ebx
0x18002c0d6  mov     [rsp+180h+Endpoint], rax
0x18002c0db  mov     rcx, [rcx+0D8h]
0x18002c0e2  call    WPP_SF_qsDDD
0x18002c0e7  mov     r13d, r15d
0x18002c0ea  mov     [rsp+180h+var_128], r15d
0x18002c0ef  test    r15b, r13b
0x18002c0f2  jz      loc_18002C794
0x18002c0f8  and     r13d, 0FFFFFFFEh
0x18002c0fc  lea     rcx, [rbp+80h+var_F0]; this
0x18002c100  mov     [rsp+180h+var_128], r13d
0x18002c105  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18002c10a  jmp     loc_18002C794
0x18002c10f  lea     rbx, [r14+0F4h]
0x18002c116  mov     rcx, r12; Binding
0x18002c119  mov     rdx, rbx; Pid
0x18002c11c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002c122  test    eax, eax
0x18002c124  jz      short loc_18002C151
0x18002c126  mov     rdx, rbx; Pid
0x18002c129  mov     rcx, r12; Binding
0x18002c12c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002c132  mov     esi, eax
0x18002c134  or      esi, 80010000h
0x18002c13a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002c141  jb      loc_18002C794
0x18002c147  mov     edx, 18h
0x18002c14c  jmp     loc_18002C776
0x18002c151  mov     r8d, [rbx]; dwProcessId
0x18002c154  xor     edx, edx; bInheritHandle
0x18002c156  mov     ecx, 101000h; dwDesiredAccess
0x18002c15b  call    cs:__imp_OpenProcess
0x18002c161  mov     rdx, rax
0x18002c164  lea     rcx, [rbp+80h+ProcessHandle]
0x18002c168  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002c16d  mov     rbx, [rbp+80h+ProcessHandle]
0x18002c171  test    rbx, rbx
0x18002c174  jnz     short loc_18002C1A2
0x18002c176  call    cs:__imp_GetLastError
0x18002c17c  mov     esi, eax
0x18002c17e  test    eax, eax
0x18002c180  jle     short loc_18002C18B
0x18002c182  movzx   esi, ax
0x18002c185  or      esi, 80070000h
0x18002c18b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18002c192  jb      loc_18002C794
0x18002c198  mov     edx, 19h
0x18002c19d  jmp     loc_18002C776
0x18002c1a2  lea     r9, [rsp+180h+String]; unsigned int *
0x18002c1a7  mov     dword ptr [rsp+180h+String], esi
0x18002c1ab  xor     r8d, r8d; unsigned int
0x18002c1ae  xor     edx, edx; unsigned __int16 *
0x18002c1b0  mov     rcx, rbx; ProcessHandle
0x18002c1b3  call    ?FSGetProcessImageName@@YAJPEAXPEAGKPEAK@Z; FSGetProcessImageName(void *,ushort *,ulong,ulong *)
0x18002c1b8  test    eax, eax
0x18002c1ba  js      loc_18002C245
0x18002c1c0  mov     edx, dword ptr [rsp+180h+String]
0x18002c1c4  lea     rcx, [rsp+180h+var_138]
0x18002c1c9  lea     rdi, [r14+0F8h]
0x18002c1d0  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18002c1d5  mov     rdx, rax
0x18002c1d8  mov     rcx, rdi
0x18002c1db  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
  ... truncated ...
```
