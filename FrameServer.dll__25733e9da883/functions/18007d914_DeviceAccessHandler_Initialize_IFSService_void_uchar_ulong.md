# DeviceAccessHandler::Initialize(IFSService *,void *,uchar *,ulong)

- ea: `0x18007d914`
- end: `0x18007e945`
- name: `?Initialize@DeviceAccessHandler@@AEAAJPEAUIFSService@@PEAXPEAEK@Z`
- size: `4145`
- prototype: `__int64 __fastcall(DeviceAccessHandler *this, struct IFSService *, unsigned __int16 *, unsigned __int8 *, UINT cbBufSize)`
- caller_count: `1`
- callee_count: `43`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007c6f4`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180005b94`
- `0x180005e78`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x180009b5c`
- `0x18000a620`
- `0x18000a648`
- `0x180017ab8`
- `0x180017f60`
- `0x180024200`
- `0x18002763c`
- `0x1800284d0`
- `0x180028c44`
- `0x180029c24`
- `0x180029d78`
- `0x18002a058`
- `0x18002a2e0`
- `0x18002b654`
- `0x18004d714`
- `0x18004da70`
- `0x18005696c`
- `0x18007c074`
- `0x18007c828`
- `0x18007c880`
- `0x18007ca2c`
- `0x18007cb94`
- `0x18007d68c`
- `0x18007d914`
- `0x18007e94c`
- `0x18007fd50`
- `0x18008009c`
- `0x180080344`
- `0x1800805c0`
- `0x180080920`
- `0x1800809ec`
- `0x1800e3b40`
- `0x1800e3e1c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007dc48`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007dc48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dde7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dde7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfb4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007dfaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007dfaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007ddc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007ddc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007dddd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007dddd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007e253`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007e253`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007dc8c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007dc9d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007de8d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007de9e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007dc8c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007dc9d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007de8d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007de9e`
- `RPCRT4!RpcStringBindingParseW` at `0x18007db9b`
- `RPCRT4!RpcStringBindingParseW` at `0x18007dbe9`
- `RPCRT4!RpcStringBindingParseW` at `0x18007db9b`
- `RPCRT4!RpcStringBindingParseW` at `0x18007dbe9`
- `RPCRT4!RpcImpersonateClient` at `0x18007dd58`
- `RPCRT4!RpcImpersonateClient` at `0x18007dd65`
- `RPCRT4!RpcImpersonateClient` at `0x18007dd58`
- `RPCRT4!RpcImpersonateClient` at `0x18007dd65`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007e1f3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007e47f`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007e1f3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18007e47f`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18007dabe`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18007dafc`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18007dabe`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18007dafc`
- `RPCRT4!RpcStringFreeW` at `0x18007daa4`
- `RPCRT4!RpcStringFreeW` at `0x18007dae2`
- `RPCRT4!RpcStringFreeW` at `0x18007db71`
- `RPCRT4!RpcStringFreeW` at `0x18007dbbf`
- `RPCRT4!RpcStringFreeW` at `0x18007daa4`
- `RPCRT4!RpcStringFreeW` at `0x18007dae2`
- `RPCRT4!RpcStringFreeW` at `0x18007db71`
- `RPCRT4!RpcStringFreeW` at `0x18007dbbf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e0cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e0eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e3df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e0cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e0eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e3df`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007df00`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007df00`
- `MFPlat!MFCreateAttributes` at `0x18007d9db`
- `MFPlat!MFCreateAttributes` at `0x18007d9db`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007da35`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007da35`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::Initialize(
        DeviceAccessHandler *this,
        struct IFSService *a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        UINT cbBufSize)
{
  UINT8 *NetworkOptions; // rdi
  RPC_WSTR v6; // r13
  char v8; // r12
  HRESULT v9; // eax
  signed int v10; // r14d
  __int64 v11; // rdx
  IMFAttributes **v12; // r14
  HRESULT v13; // eax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rbx
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rbx
  __int64 v18; // rdx
  int v19; // eax
  char v20; // bl
  GuidTrace *v21; // rax
  const char *v22; // rax
  char v23; // al
  void *v24; // rcx
  bool v25; // al
  void *v26; // rcx
  bool v27; // al
  void *v28; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  _QWORD *v31; // rdi
  __int64 v32; // rdx
  DWORD v33; // r8d
  HANDLE v34; // rax
  HANDLE v35; // rbx
  bool v36; // sf
  bool v37; // sf
  int UserSidString; // eax
  const WCHAR *v39; // r13
  unsigned int v40; // r8d
  int v41; // eax
  char v42; // al
  struct IFSService *v43; // r14
  __int64 (__fastcall *v44)(struct IFSService *, GUID *, GUID *, RPC_WSTR *); // rbx
  int v45; // eax
  unsigned int v46; // ebx
  int PackageSidString; // eax
  int inited; // eax
  __int64 *v49; // rax
  bool v50; // cf
  __int64 v51; // rcx
  __int64 v52; // rdx
  unsigned __int8 v53; // al
  __int64 v54; // rdi
  int (__fastcall *v55)(__int64, const IID *, LPCWSTR *, int *); // rbx
  const WCHAR *v56; // rbx
  int v57; // eax
  const char *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // r8
  int Usage; // eax
  _WORD *v62; // rdi
  const char *v63; // r15
  char v64; // di
  GuidTrace *v65; // rax
  const char *v66; // rax
  bool v67; // zf
  const char *v68; // r15
  char v69; // bl
  GuidTrace *v70; // rax
  const char *v71; // rax
  const char *v72; // r15
  char v73; // bl
  GuidTrace *v74; // rax
  const char *v75; // rax
  const char *v76; // r15
  char v77; // bl
  GuidTrace *v78; // rax
  const char *v79; // rax
  RPC_WSTR *Endpoint; // [rsp+20h] [rbp-F0h]
  char v82; // [rsp+90h] [rbp-80h]
  unsigned int pvData; // [rsp+94h] [rbp-7Ch] BYREF
  HANDLE ProcessHandle; // [rsp+98h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+A0h] [rbp-70h] BYREF
  RPC_WSTR StringBinding; // [rsp+A8h] [rbp-68h] BYREF
  RPC_WSTR Protseq; // [rsp+B0h] [rbp-60h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp-58h] BYREF
  struct IFSService *v89; // [rsp+C0h] [rbp-50h] BYREF
  LPCWSTR pszDeviceInterface; // [rsp+C8h] [rbp-48h] BYREF
  RPC_WSTR v91; // [rsp+D0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+D8h] [rbp-38h] BYREF
  int v93; // [rsp+DCh] [rbp-34h] BYREF
  _BYTE v94[32]; // [rsp+E0h] [rbp-30h] BYREF
  int RpcCallAttributes; // [rsp+100h] [rbp-10h] BYREF
  int v96; // [rsp+104h] [rbp-Ch]
  _BYTE v97[56]; // [rsp+108h] [rbp-8h] BYREF
  DWORD dwProcessId; // [rsp+140h] [rbp+30h]
  int v99; // [rsp+16Ch] [rbp+5Ch]
  char *v100; // [rsp+170h] [rbp+60h]

  v91 = a3;
  v89 = a2;
  NetworkOptions = a4;
  v82 = 0;
  v6 = a3;
  StringBinding = 0;
  Protseq = 0;
  v8 = 0;
  pszDeviceInterface = 0;
  v93 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_149;
    v11 = 27;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v9);
    goto LABEL_149;
  }
  if ( !a4 )
  {
    if ( !cbBufSize )
      goto LABEL_8;
LABEL_12:
    v9 = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_149;
    v11 = 28;
    goto LABEL_4;
  }
  if ( !cbBufSize )
    goto LABEL_12;
LABEL_8:
  v12 = (IMFAttributes **)((char *)this + 264);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 264);
  v9 = MFCreateAttributes(v12, 1u);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_149;
    v11 = 29;
    goto LABEL_4;
  }
  if ( NetworkOptions )
  {
    v13 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 33), NetworkOptions, cbBufSize);
    NetworkOptions = 0;
    v10 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v13);
        v8 = 0;
      }
      goto LABEL_149;
    }
  }
  if ( (unsigned int)IsSKUHeadless() )
    *((_BYTE *)this + 236) = 1;
  v14 = StringBinding;
  if ( StringBinding )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&ProcessHandle);
    String = v14;
    RpcStringFreeW(&String);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&ProcessHandle);
  }
  StringBinding = (RPC_WSTR)NetworkOptions;
  if ( !RpcBindingToStringBindingW(v6, &StringBinding) )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        32,
        &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
        StringBinding);
    v16 = Protseq;
    if ( Protseq )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&ProcessHandle);
      String = v16;
      RpcStringFreeW(&String);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&ProcessHandle);
    }
    Protseq = (RPC_WSTR)NetworkOptions;
    if ( RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, (RPC_WSTR *)NetworkOptions, (RPC_WSTR *)NetworkOptions) )
    {
      v17 = Protseq;
      if ( Protseq )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v89);
        v91 = v17;
        RpcStringFreeW(&v91);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v89);
      }
      Protseq = (RPC_WSTR)NetworkOptions;
      v10 = RpcStringBindingParseW(
              StringBinding,
              0,
              &Protseq,
              0,
              (RPC_WSTR *)NetworkOptions,
              (RPC_WSTR *)NetworkOptions)
          | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_148;
      v18 = 33;
      goto LABEL_36;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 34, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, Protseq);
    if ( !(unsigned int)_o__wcsicmp(Protseq, L"ncacn_hvsocket") )
    {
      memset_0(v97, 0, 0x64u);
      RpcCallAttributes = 3;
      v100 = (char *)this + 240;
      v96 = 224;
      v99 = 16;
      if ( RpcServerInqCallAttributesW(v6, &RpcCallAttributes) )
      {
        v10 = RpcServerInqCallAttributesW(v6, &RpcCallAttributes) | 0x80010000;
        if ( !g_wppLevels )
          goto LABEL_148;
        v18 = 35;
LABEL_36:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v10);
LABEL_148:
        v8 = v82;
        goto LABEL_149;
      }
      v19 = MFGetAttributeUINT32(*((_QWORD *)this + 33), MF_FRAMESERVER_CLIENTCONTEXT_CLIENTPID, 0);
      v20 = v19;
      *((_DWORD *)this + 58) = v19;
      if ( (unsigned __int8)byte_18010EC4D < 8u )
      {
        v23 = 0;
      }
      else
      {
        v21 = GuidTrace::GuidTrace((GuidTrace *)v94, (const struct _GUID *)this + 15);
        v22 = GuidTrace::GetString(v21);
        WPP_SF_qsDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          36,
          (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
          (_DWORD)this,
          (__int64)v22,
          v20,
          v97[32],
          v97[36]);
        v23 = 1;
        v82 = 1;
      }
      if ( (v23 & 1) != 0 )
      {
        v82 = v23 & 0xFE;
        FSString::~FSString((FSString *)v94);
      }
      LODWORD(NetworkOptions) = 0;
    }
    if ( RpcImpersonateClient(v6) )
    {
      v10 = RpcImpersonateClient(v6) | 0x80010000;
      if ( !g_wppLevels )
        goto LABEL_148;
      v18 = 37;
      goto LABEL_36;
    }
    v25 = FSIsFSMonitorProcess(v24);
    *((_BYTE *)this + 288) = v25;
    if ( !v25 )
    {
      v27 = FSIsAdmin(v26);
      *((_BYTE *)this + 289) = v27;
      if ( !v27 )
        *((_BYTE *)this + 290) = FSIsLocalSystem(v28);
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 256,
      0);
    CurrentThread = GetCurrentThread();
    v10 = (int)NetworkOptions;
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)this + 32) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v10);
        goto LABEL_106;
      }
    }
    v31 = (_QWORD *)((char *)this + 240);
    if ( *((_QWORD *)this + 30) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      && *((_QWORD *)this + 31) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      v10 = 0;
      RpcCallAttributes = 2;
      ProcessHandle = 0;
      TokenHandle = 0;
      v96 = 16;
      memset_0(v97, 0, 0x68u);
      if ( RpcServerInqCallAttributesW(v6, &RpcCallAttributes) )
      {
        v10 = RpcServerInqCallAttributesW(v6, &RpcCallAttributes) | 0x80010000;
        if ( !g_wppLevels )
        {
LABEL_67:
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
LABEL_106:
          RpcRevertToSelfEx(v6);
          goto LABEL_148;
        }
        v32 = 39;
LABEL_66:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v10);
        goto LABEL_67;
      }
      v33 = dwProcessId;
      *((_DWORD *)this + 58) = dwProcessId;
      v34 = OpenProcess(0x400u, 0, v33);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &ProcessHandle,
        v34);
      v35 = ProcessHandle;
      if ( !ProcessHandle )
      {
        if ( GetLastError() == 5 )
        {
          if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 40, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this);
          DeviceAccessHandler::ExtractUserSidString(this, (void *)0xFFFFFFFFFFFFFFFBLL);
          goto LABEL_67;
        }
        v10 = GetLastError();
        v36 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v36 = v10 < 0;
        }
        if ( v36 )
        {
          if ( !g_wppLevels )
            goto LABEL_67;
          v32 = 41;
          goto LABEL_66;
        }
      }
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      if ( !OpenProcessToken(v35, 0xEu, &TokenHandle) )
      {
        v10 = GetLastError();
        v37 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v37 = v10 < 0;
        }
        if ( v37 )
        {
          if ( !g_wppLevels )
            goto LABEL_67;
          v32 = 42;
          goto LABEL_66;
        }
      }
      DeviceAccessHandler::ExtractIsAppContainer(this, TokenHandle);
      UserSidString = DeviceAccessHandler::ExtractUserSidString(this, TokenHandle);
      v10 = UserSidString;
      if ( UserSidString < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            UserSidString);
        goto LABEL_67;
      }
      DeviceAccessHandler::ExtractProcessNameAndSessionId(this, v35);
      v39 = (const WCHAR *)((char *)this + 88);
      v41 = FSCreatePackageFamilyNameTag(v35, (unsigned __int16 *)this + 44, v40, (unsigned int *)this + 57);
      if ( v41 >= 0 )
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            45,
            (unsigned int)&WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            (_DWORD)this,
            (__int64)this + 88);
        if ( CompareStringOrdinal(L"pfn:windows.immersivecontrolpanel_cw5n1h2txyewy", -1, (LPCWCH)this + 44, -1, 1) == 2
          || (v67 = CompareStringOrdinal(
                      L"pfn:BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy",
                      -1,
                      (LPCWCH)this + 44,
                      -1,
                      1) == 2,
              v42 = 0,
              v67) )
        {
          v42 = 1;
        }
      }
      else
      {
        *((_DWORD *)this + 57) = 0;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          LODWORD(Endpoint) = v41;
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            44,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            Endpoint,
            *((_DWORD *)this + 58));
        }
        v42 = 0;
      }
      *((_BYTE *)this + 291) = v42;
      v43 = v89;
      String = 0;
      v44 = *(__int64 (__fastcall **)(struct IFSService *, GUID *, GUID *, RPC_WSTR *))(*(_QWORD *)v89 + 120LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&String);
      v45 = v44(v43, &GUID_00000000_0000_0000_0000_000000000000, &GUID_82fc34df_7f60_4751_bffd_2aa1f8b269fc, &String);
      v46 = 0;
      if ( v45 >= 0 )
        (*(void (__fastcall **)(RPC_WSTR, _QWORD))(*(_QWORD *)String + 56LL))(String, *((_QWORD *)this + 9));
      if ( *((_DWORD *)this + 14) )
      {
        PackageSidString = DeviceAccessHandler::ExtractPackageSidString(this, TokenHandle);
        if ( PackageSidString < 0 && (unsigned __int8)byte_18010EC4D >= 8u )
        {
          LODWORD(Endpoint) = PackageSidString;
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            46,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            Endpoint,
            *((_DWORD *)this + 58));
        }
      }
      inited = DeviceAccessHandler::InitSidCategoryBasedFlags(this);
      v10 = inited;
      if ( inited < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            inited);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&String);
        wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
        v6 = v91;
        goto LABEL_106;
      }
      if ( *v31 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
        && *((_QWORD *)this + 31) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
      {
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer",
                L"EnableVAILTestMode",
                0xFFFFu,
                0,
                &pvData,
                &pcbData) )
        {
          if ( pvData )
            v46 = pvData;
        }
      }
      v49 = &qword_1800FCBC0;
      if ( *((_BYTE *)this + 292) )
        v50 = v46 < 2;
      else
        v50 = v46 == 0;
      v51 = *((_QWORD *)this + 33);
      if ( v50 )
        v49 = (__int64 *)((char *)this + 240);
      *(_OWORD *)v31 = *(_OWORD *)v49;
      *((_BYTE *)this + 293) = (unsigned int)MFGetAttributeUINT32(
                                               v51,
                                               MF_FRAMESERVER_ATTRIBUTE_ENABLE_SHARED_EXTENDED_OPERATIONS,
                                               0) != 0;
      LOBYTE(v52) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CCW>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CCW>::GetImpl'::`2'::impl,
        v52);
      v53 = *((_BYTE *)this + 293);
      if ( !v53 )
      {
        if ( *((_DWORD *)this + 57) )
        {
          v53 = FSIsSettingsLikeAppPFN((LPCWCH)this + 44);
          *((_BYTE *)this + 293) = v53;
        }
        else
        {
          v53 = 0;
        }
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 48, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v53);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&String);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
    }
    else
    {
      v39 = (const WCHAR *)((char *)this + 88);
    }
    v54 = *((_QWORD *)this + 33);
    v55 = *(int (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v54 + 104LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &pszDeviceInterface,
      0);
    if ( v55(v54, &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK, &pszDeviceInterface, &v93) >= 0 )
    {
      if ( *v39 )
      {
        memset_0(&RpcCallAttributes, 0, 0x84u);
        pvData = 0;
        v56 = FSGetPfnFromTaggedPfn(v39);
        if ( v56 )
        {
          if ( (int)FSGetDeviceInterfaceProperty(
                      pszDeviceInterface,
                      (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn,
                      (PBYTE)&RpcCallAttributes,
                      0x82u,
                      &pvData) >= 0
            && pvData > 2 )
          {
            v57 = CompareStringOrdinal(v56, -1, (LPCWCH)&RpcCallAttributes, -1, 1);
            *((_BYTE *)this + 294) = v57 == 2;
            if ( (unsigned __int8)byte_18010EC4D >= 8u )
            {
              v58 = "deferred";
              if ( v57 != 2 )
                v58 = "not_deferred";
              WPP_SF_qSs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)&RpcCallAttributes, (__int64)v58);
            }
          }
        }
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 272);
        DeviceAccessHandler::InternalLoadDeviceConfiguration(
          this,
          v89,
          pszDeviceInterface,
          *((const unsigned __int16 **)this + 10),
          v39,
          (struct IMFAttributes **)this + 34);
      }
      else
      {
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 272);
        DeviceAccessHandler::InternalLoadDeviceConfiguration(
          this,
          v89,
          pszDeviceInterface,
          *((const unsigned __int16 **)this + 10),
          0,
          (struct IMFAttributes **)this + 34);
      }
    }
    RpcRevertToSelfEx(v91);
    if ( !*((_BYTE *)this + 236) && !*((_BYTE *)this + 294) )
    {
      if ( (int)FSCamGetAppsCapabilityAccess(L"webcam") < 0
        || ((pvData = 0,
             (*(int (__fastcall **)(_QWORD, const struct _GUID *, unsigned int *))(**((_QWORD **)this + 33) + 88LL))(
               *((_QWORD *)this + 33),
               &MF_DEVSOURCE_ATTRIBUTE_SOURCE_XADDRESS,
               &pvData) >= 0)
         || (*(int (__fastcall **)(_QWORD, const struct _GUID *, unsigned int *))(**((_QWORD **)this + 33) + 88LL))(
              *((_QWORD *)this + 33),
              &MF_DEVSOURCE_ATTRIBUTE_SOURCE_STREAM_URL,
              &pvData) >= 0)
        && (int)FSCamGetAppsCapabilityAccess(L"internetClient") < 0
        && (int)FSCamGetAppsCapabilityAccess(L"internetClientServer") < 0 )
      {
        *((_DWORD *)this + 13) = 0;
      }
      if ( *((_DWORD *)this + 13) == 1 )
      {
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 280);
        Usage = FSCamCreateUsage(v59, *((unsigned int *)this + 58), v60, (char *)this + 280);
        v10 = Usage;
        if ( Usage < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
              this,
              Usage);
        }
      }
    }
    goto LABEL_148;
  }
  v15 = StringBinding;
  if ( StringBinding )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v89);
    v91 = v15;
    RpcStringFreeW(&v91);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v89);
  }
  StringBinding = (RPC_WSTR)NetworkOptions;
  v10 = RpcBindingToStringBindingW(v6, &StringBinding) | 0x80010000;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v10);
LABEL_149:
  v62 = (_WORD *)((char *)this + 88);
  if ( v10 >= 0 )
  {
    if ( *v62 )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v76 = L"<nullptr>";
        v77 = *((_BYTE *)this + 292);
        if ( *((_QWORD *)this + 9) )
          v76 = (const char *)*((_QWORD *)this + 9);
        v8 |= 0x10u;
        v78 = GuidTrace::GuidTrace((GuidTrace *)v94, (const struct _GUID *)this + 15);
        v79 = GuidTrace::GetString(v78);
        WPP_SF_qDDdSddddddsSd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v10,
          *((_DWORD *)this + 58),
          *((_DWORD *)this + 14),
          (__int64)this + 88,
          *((_BYTE *)this + 236),
          *((_BYTE *)this + 294),
          *((_DWORD *)this + 13),
          *((_BYTE *)this + 289),
          *((_BYTE *)this + 290),
          *((_BYTE *)this + 288),
          (__int64)v79,
          (__int64)v76,
          v77);
      }
      v67 = (v8 & 0x10) == 0;
    }
    else
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v72 = L"<nullptr>";
        v73 = *((_BYTE *)this + 292);
        if ( *((_QWORD *)this + 9) )
          v72 = (const char *)*((_QWORD *)this + 9);
        v8 |= 8u;
        v74 = GuidTrace::GuidTrace((GuidTrace *)v94, (const struct _GUID *)this + 15);
        v75 = GuidTrace::GetString(v74);
        WPP_SF_qDDdddddddsSd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v10,
          *((_DWORD *)this + 58),
          *((_DWORD *)this + 14),
          *((_BYTE *)this + 236),
          *((_BYTE *)this + 294),
          *((_DWORD *)this + 13),
          *((_BYTE *)this + 289),
          *((_BYTE *)this + 290),
          *((_BYTE *)this + 288),
          (__int64)v75,
          (__int64)v72,
          v73);
      }
      v67 = (v8 & 8) == 0;
    }
  }
  else if ( *v62 )
  {
    if ( byte_18010EC4D )
    {
      v68 = L"<nullptr>";
      v69 = *((_BYTE *)this + 292);
      if ( *((_QWORD *)this + 9) )
        v68 = (const char *)*((_QWORD *)this + 9);
      v8 |= 4u;
      v70 = GuidTrace::GuidTrace((GuidTrace *)v94, (const struct _GUID *)this + 15);
      v71 = GuidTrace::GetString(v70);
      WPP_SF_qDDdSddddddsSd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v10,
        *((_DWORD *)this + 58),
        *((_DWORD *)this + 14),
        (__int64)this + 88,
        *((_BYTE *)this + 236),
        *((_BYTE *)this + 294),
        *((_DWORD *)this + 13),
        *((_BYTE *)this + 289),
        *((_BYTE *)this + 290),
        *((_BYTE *)this + 288),
        (__int64)v71,
        (__int64)v68,
        v69);
    }
    v67 = (v8 & 4) == 0;
  }
  else
  {
    if ( byte_18010EC4D )
    {
      v63 = L"<nullptr>";
      v64 = *((_BYTE *)this + 292);
      if ( *((_QWORD *)this + 9) )
        v63 = (const char *)*((_QWORD *)this + 9);
      v8 |= 2u;
      v65 = GuidTrace::GuidTrace((GuidTrace *)v94, (const struct _GUID *)this + 15);
      v66 = GuidTrace::GetString(v65);
      WPP_SF_qDDdddddddsSd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v10,
        *((_DWORD *)this + 58),
        *((_DWORD *)this + 14),
        *((_BYTE *)this + 236),
        *((_BYTE *)this + 294),
        *((_DWORD *)this + 13),
        *((_BYTE *)this + 289),
        *((_BYTE *)this + 290),
        *((_BYTE *)this + 288),
        (__int64)v66,
        (__int64)v63,
        v64);
    }
    v67 = (v8 & 2) == 0;
  }
  if ( !v67 )
    FSString::~FSString((FSString *)v94);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszDeviceInterface);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Protseq);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007d914  push    rbp
0x18007d916  push    rbx
0x18007d917  push    rsi
0x18007d918  push    rdi
0x18007d919  push    r12
0x18007d91b  push    r13
0x18007d91d  push    r14
0x18007d91f  push    r15
0x18007d921  lea     rbp, [rsp-98h]
0x18007d929  sub     rsp, 1A8h
0x18007d930  mov     rax, cs:__security_cookie
0x18007d937  xor     rax, rsp
0x18007d93a  mov     [rbp+0D0h+var_50], rax
0x18007d941  xor     r14d, r14d
0x18007d944  mov     [rbp+0D0h+var_110], r8
0x18007d948  mov     [rbp+0D0h+var_120], rdx
0x18007d94c  mov     rdi, r9
0x18007d94f  mov     [rbp+0D0h+var_150], r14d
0x18007d953  mov     r13, r8
0x18007d956  mov     [rbp+0D0h+StringBinding], r14
0x18007d95a  mov     rsi, rcx
0x18007d95d  mov     [rbp+0D0h+Protseq], r14
0x18007d961  mov     r12d, r14d
0x18007d964  mov     [rbp+0D0h+pszDeviceInterface], r14
0x18007d968  mov     [rbp+0D0h+var_104], r14d
0x18007d96c  test    rdx, rdx
0x18007d96f  jnz     short loc_18007D9B1
0x18007d971  mov     eax, 80070057h
0x18007d976  mov     r14d, eax
0x18007d979  lea     r15d, [rdx+1]
0x18007d97d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007d984  jb      loc_18007E595
0x18007d98a  lea     edx, [r15+1Ah]
0x18007d98e  mov     dword ptr [rsp+1E0h+Endpoint], eax
0x18007d992  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d999  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007d9a0  mov     r9, rsi
0x18007d9a3  mov     rcx, [rcx+10h]
0x18007d9a7  call    WPP_SF_qD
0x18007d9ac  jmp     loc_18007E595
0x18007d9b1  mov     ebx, [rbp+0D0h+cbBufSize]
0x18007d9b7  test    rdi, rdi
0x18007d9ba  jnz     short loc_18007D9FB
0x18007d9bc  test    ebx, ebx
0x18007d9be  jnz     short loc_18007D9FF
0x18007d9c0  lea     r14, [rcx+108h]
0x18007d9c7  mov     rcx, r14
0x18007d9ca  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007d9cf  mov     r15d, 1
0x18007d9d5  mov     rcx, r14; ppMFAttributes
0x18007d9d8  mov     edx, r15d; cInitialSize
0x18007d9db  call    cs:__imp_MFCreateAttributes
0x18007d9e1  mov     r14d, eax
0x18007d9e4  test    eax, eax
0x18007d9e6  jns     short loc_18007DA23
0x18007d9e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007d9ef  jb      loc_18007E595
0x18007d9f5  lea     edx, [r15+1Ch]
0x18007d9f9  jmp     short loc_18007D98E
0x18007d9fb  test    ebx, ebx
0x18007d9fd  jnz     short loc_18007D9C0
0x18007d9ff  mov     eax, 80070057h
0x18007da04  mov     r14d, eax
0x18007da07  mov     r15d, 1
0x18007da0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007da14  jb      loc_18007E595
0x18007da1a  lea     edx, [r15+1Bh]
0x18007da1e  jmp     loc_18007D98E
0x18007da23  test    rdi, rdi
0x18007da26  jz      short loc_18007DA7A
0x18007da28  mov     rcx, [rsi+108h]; pAttributes
0x18007da2f  mov     r8d, ebx; cbBufSize
0x18007da32  mov     rdx, rdi; pBuf
0x18007da35  call    cs:__imp_MFInitAttributesFromBlob
0x18007da3b  xor     edi, edi
0x18007da3d  mov     r14d, eax
0x18007da40  test    eax, eax
0x18007da42  jns     short loc_18007DA7A
0x18007da44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007da4b  jb      loc_18007E595
0x18007da51  mov     rcx, cs:WPP_GLOBAL_Control
0x18007da58  lea     edx, [rdi+1Eh]
0x18007da5b  mov     r9, rsi
0x18007da5e  mov     dword ptr [rsp+1E0h+Endpoint], eax
0x18007da62  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007da69  mov     rcx, [rcx+10h]
0x18007da6d  call    WPP_SF_qD
0x18007da72  mov     r12d, edi
0x18007da75  jmp     loc_18007E595
0x18007da7a  call    ?IsSKUHeadless@@YAHXZ; IsSKUHeadless(void)
0x18007da7f  test    eax, eax
0x18007da81  jz      short loc_18007DA8A
0x18007da83  mov     [rsi+0ECh], r15b
0x18007da8a  mov     rbx, [rbp+0D0h+StringBinding]
0x18007da8e  test    rbx, rbx
0x18007da91  jz      short loc_18007DAB3
0x18007da93  lea     rcx, [rbp+0D0h+ProcessHandle]; this
0x18007da97  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007da9c  lea     rcx, [rbp+0D0h+String]; String
0x18007daa0  mov     [rbp+0D0h+String], rbx
0x18007daa4  call    cs:__imp_RpcStringFreeW
0x18007daaa  lea     rcx, [rbp+0D0h+ProcessHandle]; this
0x18007daae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007dab3  lea     rdx, [rbp+0D0h+StringBinding]; StringBinding
0x18007dab7  mov     [rbp+0D0h+StringBinding], rdi
0x18007dabb  mov     rcx, r13; Binding
0x18007dabe  call    cs:__imp_RpcBindingToStringBindingW
0x18007dac4  test    eax, eax
0x18007dac6  jz      short loc_18007DB28
0x18007dac8  mov     rbx, [rbp+0D0h+StringBinding]
0x18007dacc  test    rbx, rbx
0x18007dacf  jz      short loc_18007DAF1
0x18007dad1  lea     rcx, [rbp+0D0h+var_120]; this
0x18007dad5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007dada  lea     rcx, [rbp+0D0h+var_110]; String
0x18007dade  mov     [rbp+0D0h+var_110], rbx
0x18007dae2  call    cs:__imp_RpcStringFreeW
0x18007dae8  lea     rcx, [rbp+0D0h+var_120]; this
0x18007daec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007daf1  lea     rdx, [rbp+0D0h+StringBinding]; StringBinding
0x18007daf5  mov     [rbp+0D0h+StringBinding], rdi
0x18007daf9  mov     rcx, r13; Binding
0x18007dafc  call    cs:__imp_RpcBindingToStringBindingW
0x18007db02  mov     r14d, eax
0x18007db05  or      r14d, 80010000h
0x18007db0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007db13  jb      loc_18007E595
0x18007db19  mov     edx, 1Fh
0x18007db1e  mov     dword ptr [rsp+1E0h+Endpoint], r14d
0x18007db23  jmp     loc_18007D992
0x18007db28  cmp     cs:byte_18010EC4D, 8
0x18007db2f  lea     r12, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007db36  jb      short loc_18007DB57
0x18007db38  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db3f  mov     edx, 20h ; ' '
0x18007db44  mov     r9, [rbp+0D0h+StringBinding]
0x18007db48  mov     r8, r12
0x18007db4b  mov     rcx, [rcx+0D8h]
0x18007db52  call    WPP_SF_S
0x18007db57  mov     rbx, [rbp+0D0h+Protseq]
0x18007db5b  test    rbx, rbx
0x18007db5e  jz      short loc_18007DB80
0x18007db60  lea     rcx, [rbp+0D0h+ProcessHandle]; this
0x18007db64  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007db69  lea     rcx, [rbp+0D0h+String]; String
0x18007db6d  mov     [rbp+0D0h+String], rbx
0x18007db71  call    cs:__imp_RpcStringFreeW
0x18007db77  lea     rcx, [rbp+0D0h+ProcessHandle]; this
0x18007db7b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007db80  mov     rcx, [rbp+0D0h+StringBinding]; StringBinding
0x18007db84  lea     r8, [rbp+0D0h+Protseq]; Protseq
0x18007db88  mov     [rsp+1E0h+NetworkOptions], rdi; NetworkOptions
0x18007db8d  xor     r9d, r9d; NetworkAddr
0x18007db90  xor     edx, edx; ObjUuid
0x18007db92  mov     [rsp+1E0h+Endpoint], rdi; Endpoint
0x18007db97  mov     [rbp+0D0h+Protseq], rdi
0x18007db9b  call    cs:__imp_RpcStringBindingParseW
0x18007dba1  test    eax, eax
0x18007dba3  jz      short loc_18007DC15
0x18007dba5  mov     rbx, [rbp+0D0h+Protseq]
0x18007dba9  test    rbx, rbx
0x18007dbac  jz      short loc_18007DBCE
0x18007dbae  lea     rcx, [rbp+0D0h+var_120]; this
0x18007dbb2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007dbb7  lea     rcx, [rbp+0D0h+var_110]; String
0x18007dbbb  mov     [rbp+0D0h+var_110], rbx
0x18007dbbf  call    cs:__imp_RpcStringFreeW
0x18007dbc5  lea     rcx, [rbp+0D0h+var_120]; this
0x18007dbc9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007dbce  mov     rcx, [rbp+0D0h+StringBinding]; StringBinding
0x18007dbd2  lea     r8, [rbp+0D0h+Protseq]; Protseq
0x18007dbd6  mov     [rsp+1E0h+NetworkOptions], rdi; NetworkOptions
0x18007dbdb  xor     r9d, r9d; NetworkAddr
0x18007dbde  xor     edx, edx; ObjUuid
0x18007dbe0  mov     [rsp+1E0h+Endpoint], rdi; Endpoint
0x18007dbe5  mov     [rbp+0D0h+Protseq], rdi
0x18007dbe9  call    cs:__imp_RpcStringBindingParseW
0x18007dbef  mov     r14d, eax
0x18007dbf2  or      r14d, 80010000h
0x18007dbf9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007dc00  jb      loc_18007E591
0x18007dc06  mov     edx, 21h ; '!'
0x18007dc0b  mov     dword ptr [rsp+1E0h+Endpoint], r14d
0x18007dc10  jmp     loc_18007E57B
0x18007dc15  cmp     cs:byte_18010EC4D, 8
0x18007dc1c  jb      short loc_18007DC3D
0x18007dc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc25  mov     edx, 22h ; '"'
0x18007dc2a  mov     r9, [rbp+0D0h+Protseq]
0x18007dc2e  mov     r8, r12
0x18007dc31  mov     rcx, [rcx+0D8h]
0x18007dc38  call    WPP_SF_S
0x18007dc3d  mov     rcx, [rbp+0D0h+Protseq]
0x18007dc41  lea     rdx, Protseq; "ncacn_hvsocket"
0x18007dc48  call    cs:__imp__o__wcsicmp
0x18007dc4e  test    eax, eax
0x18007dc50  jnz     loc_18007DD55
0x18007dc56  xor     edx, edx; Val
0x18007dc58  lea     r8d, [rax+64h]; Size
0x18007dc5c  lea     rcx, [rbp+0D0h+var_D8]; void *
0x18007dc60  call    memset_0
0x18007dc65  lea     rdi, [rsi+0F0h]
0x18007dc6c  mov     [rbp+0D0h+RpcCallAttributes], 3
0x18007dc73  lea     rdx, [rbp+0D0h+RpcCallAttributes]; RpcCallAttributes
0x18007dc77  mov     [rbp+0D0h+var_70], rdi
0x18007dc7b  mov     rcx, r13; ClientBinding
0x18007dc7e  mov     [rbp+0D0h+var_DC], 0E0h
0x18007dc85  mov     [rbp+0D0h+var_74], 10h
0x18007dc8c  call    cs:__imp_RpcServerInqCallAttributesW
0x18007dc92  test    eax, eax
0x18007dc94  jz      short loc_18007DCC4
0x18007dc96  lea     rdx, [rbp+0D0h+RpcCallAttributes]; RpcCallAttributes
0x18007dc9a  mov     rcx, r13; ClientBinding
0x18007dc9d  call    cs:__imp_RpcServerInqCallAttributesW
0x18007dca3  mov     r14d, eax
0x18007dca6  or      r14d, 80010000h
0x18007dcad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007dcb4  jb      loc_18007E591
0x18007dcba  mov     edx, 23h ; '#'
0x18007dcbf  jmp     loc_18007DC0B
0x18007dcc4  mov     rcx, [rsi+108h]
0x18007dccb  lea     rdx, MF_FRAMESERVER_CLIENTCONTEXT_CLIENTPID
0x18007dcd2  xor     r8d, r8d
0x18007dcd5  call    MFGetAttributeUINT32
0x18007dcda  mov     ebx, eax
0x18007dcdc  mov     [rsi+0E8h], eax
0x18007dce2  cmp     cs:byte_18010EC4D, 8
0x18007dce9  jb      short loc_18007DD3C
0x18007dceb  mov     rdx, rdi; struct _GUID *
0x18007dcee  lea     rcx, [rbp+0D0h+var_100]; this
0x18007dcf2  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18007dcf7  mov     rcx, rax; this
0x18007dcfa  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18007dcff  mov     ecx, [rbp+0D0h+var_B4]
0x18007dd02  mov     edx, 24h ; '$'
0x18007dd07  mov     dword ptr [rsp+1E0h+var_1A8], ecx
0x18007dd0b  mov     r9, rsi
0x18007dd0e  mov     ecx, [rbp+0D0h+var_B8]
0x18007dd11  mov     r8, r12
0x18007dd14  mov     dword ptr [rsp+1E0h+pcbData], ecx
0x18007dd18  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd1f  mov     dword ptr [rsp+1E0h+NetworkOptions], ebx
0x18007dd23  mov     [rsp+1E0h+Endpoint], rax
0x18007dd28  mov     rcx, [rcx+0D8h]
0x18007dd2f  call    WPP_SF_qsDDD
0x18007dd34  mov     eax, r15d
0x18007dd37  mov     [rbp+0D0h+var_150], eax
0x18007dd3a  jmp     short loc_18007DD3F
0x18007dd3c  mov     eax, [rbp+0D0h+var_150]
0x18007dd3f  test    r15b, al
0x18007dd42  jz      short loc_18007DD53
0x18007dd44  and     eax, 0FFFFFFFEh
0x18007dd47  lea     rcx, [rbp+0D0h+var_100]; this
0x18007dd4b  mov     [rbp+0D0h+var_150], eax
0x18007dd4e  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18007dd53  xor     edi, edi
0x18007dd55  mov     rcx, r13; BindingHandle
0x18007dd58  call    cs:__imp_RpcImpersonateClient
0x18007dd5e  test    eax, eax
0x18007dd60  jz      short loc_18007DD8C
0x18007dd62  mov     rcx, r13; BindingHandle
0x18007dd65  call    cs:__imp_RpcImpersonateClient
0x18007dd6b  mov     r14d, eax
0x18007dd6e  or      r14d, 80010000h
0x18007dd75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007dd7c  jb      loc_18007E591
0x18007dd82  mov     edx, 25h ; '%'
0x18007dd87  jmp     loc_18007DC0B
0x18007dd8c  call    ?FSIsFSMonitorProcess@@YA_NPEAX@Z; FSIsFSMonitorProcess(void *)
0x18007dd91  mov     [rsi+120h], al
0x18007dd97  test    al, al
0x18007dd99  jnz     short loc_18007DDB5
0x18007dd9b  call    ?FSIsAdmin@@YA_NPEAX@Z; FSIsAdmin(void *)
0x18007dda0  mov     [rsi+121h], al
0x18007dda6  test    al, al
0x18007dda8  jnz     short loc_18007DDB5
0x18007ddaa  call    ?FSIsLocalSystem@@YA_NPEAX@Z; FSIsLocalSystem(void *)
0x18007ddaf  mov     [rsi+122h], al
0x18007ddb5  lea     rbx, [rsi+100h]
0x18007ddbc  xor     edx, edx
0x18007ddbe  mov     rcx, rbx
0x18007ddc1  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007ddc6  call    cs:__imp_GetCurrentThread
0x18007ddcc  mov     r9, rbx; TokenHandle
0x18007ddcf  mov     r8d, r15d; OpenAsSelf
0x18007ddd2  mov     rcx, rax; ThreadHandle
0x18007ddd5  mov     edx, 0F01FFh; DesiredAccess
0x18007ddda  mov     r14d, edi
0x18007dddd  call    cs:__imp_OpenThreadToken
0x18007dde3  test    eax, eax
0x18007dde5  jnz     short loc_18007DE36
0x18007dde7  call    cs:__imp_GetLastError
0x18007dded  mov     r14d, eax
0x18007ddf0  test    eax, eax
0x18007ddf2  jle     short loc_18007DDFF
0x18007ddf4  movzx   r14d, ax
0x18007ddf8  or      r14d, 80070000h
0x18007ddff  test    r14d, r14d
0x18007de02  jns     short loc_18007DE36
0x18007de04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
  ... truncated ...
```
