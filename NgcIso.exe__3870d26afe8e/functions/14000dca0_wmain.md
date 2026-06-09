# wmain

- ea: `0x14000dca0`
- end: `0x14000dfae`
- name: `wmain`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f4e0`

## callees

- `0x14000d37c`
- `0x14000dca0`
- `0x14000dfb4`
- `0x14000dfe0`
- `0x14000e0bc`
- `0x14000ec5c`
- `0x14000f6a0`
- `0x140010514`
- `0x14001194c`
- `0x140014bc0`
- `0x140015fa8`
- `0x1400162bc`
- `0x1400164b0`
- `0x140016d30`
- `0x140016e50`
- `0x140016eb8`
- `0x1400171cc`
- `0x140017278`
- `0x140017380`
- `0x14001810c`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ded4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ded4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000dcf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000dcf9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000de83`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000de83`
- `RPCRT4!RpcMgmtStopServerListening` at `0x14000df1e`
- `RPCRT4!RpcMgmtStopServerListening` at `0x14000df1e`
- `RPCRT4!RpcServerUnregisterIf` at `0x14000df3c`
- `RPCRT4!RpcServerUnregisterIf` at `0x14000df3c`

## string_xrefs

- `0x14000deed`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x14000de5c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\Server.h`
- `0x14000df4e`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 wmain()
{
  void *v0; // rdx
  HANDLE Event; // rbx
  unsigned int v2; // r8d
  const char *v3; // r9
  const struct wil::FailureInfo *v4; // rdx
  _QWORD *v5; // rbx
  ScopedRpcListener *v6; // rcx
  const char *v7; // r9
  int v8; // eax
  HANDLE v9; // rax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  wil::details *v13; // rbx
  void *v14; // rdx
  void *v15; // rdx
  DWORD v16; // eax
  const char *v17; // r9
  unsigned int v18; // eax
  __int64 v19; // rdx
  wil::details *v21; // [rsp+20h] [rbp-258h] BYREF
  _BYTE v22[160]; // [rsp+30h] [rbp-248h] BYREF
  _QWORD v23[7]; // [rsp+D0h] [rbp-1A8h] BYREF
  _QWORD *v24; // [rsp+108h] [rbp-170h]
  _QWORD v25[43]; // [rsp+110h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v25);
  v25[0] = &LogProvider::TrustletLifetime::`vftable';
  LogProvider::TrustletLifetime::StartActivity((LogProvider::TrustletLifetime *)v25);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v0, v2, v3);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &g_terminationEvent,
    Event);
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != LogProvider::FallbackTelemetryCallback )
  {
    memset_0(v22, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v22, v4);
  }
  try
  {
    wil::details::g_pfnTelemetryCallback = (__int64)LogProvider::FallbackTelemetryCallback;
    g_fpW8TpmSubmit = WinPlatformW8TbsSubmit;
    g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))WinPlatformGetRandom;
    g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))WinPlatformHash;
    g_fpRsaEncrypt = (int (*)(struct _BCRYPT_RSAKEY_BLOB *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int16, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *))WinPlatformRsaEncryptWorker;
    g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
    g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
    v23[0] = ___7___Func_impl_no_alloc_V_lambda_1___3__wmain__YAHXZ__NI_std__6B_;
    v24 = v23;
    v5 = (_QWORD *)((char *)VsmUtils::Velocity::Instance() + 24);
    if ( v5 != v23 )
    {
      std::_Func_class<bool,unsigned int>::_Tidy(v5);
      if ( v24 )
      {
        if ( v24 == v23 )
        {
          v5[7] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 8LL))(v24, v5);
          std::_Func_class<bool,unsigned int>::_Tidy(v23);
        }
        else
        {
          v5[7] = v24;
          v24 = 0;
        }
      }
    }
    std::_Func_class<bool,unsigned int>::_Tidy(v23);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\main.cpp",
      v7);
  }
  v8 = ScopedRpcListener::Listen(v6);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\Server.h",
      (const char *)(unsigned int)v8,
      (int)v21);
  v21 = 0;
  v9 = OpenEventW(2u, 0, L"Global\\NgcIsoTrustletStartedEvent_29D0924B-0E8D-456F-A46A-5391ACF15AD6");
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v10, v11, v12);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v21,
    v9);
  v13 = v21;
  wil::details::SetEvent(v21, v14);
  if ( v13 )
    wil::details::CloseHandle(v13, v15);
  LogProvider::TrustletLifetime::StartedEventSignaled((LogProvider::TrustletLifetime *)v25);
  v16 = WaitForSingleObjectEx(g_terminationEvent, 0xFFFFFFFF, 0);
  if ( v16 != 258 && v16 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v17);
  LogProvider::TrustletLifetime::StopEventSignaled((LogProvider::TrustletLifetime *)v25);
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, 0);
  v18 = RpcMgmtStopServerListening(0);
  if ( v18 )
  {
    v19 = 36;
LABEL_23:
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
      (const char *)v18,
      (unsigned int)v21);
    goto LABEL_24;
  }
  v18 = RpcServerUnregisterIf(qword_140076D30, 0, 1u);
  if ( v18 )
  {
    v19 = 41;
    goto LABEL_23;
  }
LABEL_24:
  LogProvider::TrustletLifetime::~TrustletLifetime((LogProvider::TrustletLifetime *)v25);
  return 0;
}

```

## disassembly

```asm
0x14000dca0  push    rbx
0x14000dca2  sub     rsp, 270h
0x14000dca9  mov     rax, cs:__security_cookie
0x14000dcb0  xor     rax, rsp
0x14000dcb3  mov     [rsp+278h+var_10], rax
0x14000dcbb  lea     rdx, aTrustletlifeti; "TrustletLifetime"
0x14000dcc2  lea     rcx, [rsp+278h+var_168]; struct wil::details::IFailureCallback *
0x14000dcca  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000dccf  lea     rax, ??_7TrustletLifetime@LogProvider@@6B@; const LogProvider::TrustletLifetime::`vftable'
0x14000dcd6  mov     [rsp+278h+var_168], rax
0x14000dcde  lea     rcx, [rsp+278h+var_168]; this
0x14000dce6  call    ?StartActivity@TrustletLifetime@LogProvider@@QEAAXXZ; LogProvider::TrustletLifetime::StartActivity(void)
0x14000dceb  nop
0x14000dcec  mov     r9d, 1F0003h; dwDesiredAccess
0x14000dcf2  xor     r8d, r8d; dwFlags
0x14000dcf5  xor     edx, edx; lpName
0x14000dcf7  xor     ecx, ecx; lpEventAttributes
0x14000dcf9  call    cs:__imp_CreateEventExW
0x14000dcff  mov     rbx, rax
0x14000dd02  test    rax, rax
0x14000dd05  jz      loc_14000DF82
0x14000dd0b  call    cs:__imp_GetLastError
0x14000dd11  mov     rdx, rbx
0x14000dd14  lea     rcx, ?g_terminationEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x14000dd1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000dd20  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000dd27  lea     rax, ?FallbackTelemetryCallback@LogProvider@@SAX_NAEBUFailureInfo@wil@@@Z; LogProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x14000dd2e  test    rcx, rcx
0x14000dd31  jz      short loc_14000DD54
0x14000dd33  cmp     rcx, rax
0x14000dd36  jz      short loc_14000DD54
0x14000dd38  xor     edx, edx; Val
0x14000dd3a  mov     r8d, 98h; Size
0x14000dd40  lea     rcx, [rsp+278h+var_248]; void *
0x14000dd45  call    memset_0
0x14000dd4a  lea     rcx, [rsp+278h+var_248]; this
0x14000dd4f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000dd54  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rax
0x14000dd5b  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x14000dd62  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x14000dd69  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x14000dd70  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x14000dd77  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14000dd7e  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14000dd85  lea     rax, ?WinPlatformRsaEncryptWorker@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@Z; WinPlatformRsaEncryptWorker(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x14000dd8c  mov     cs:?g_fpRsaEncrypt@@3P6AJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@ZEA, rax; long (*g_fpRsaEncrypt)(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x14000dd93  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14000dd9a  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14000dda1  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14000dda8  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x14000ddaf  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?3??wmain@@YAHXZ@_NI@std@@6B@; const std::_Func_impl_no_alloc<`wmain(void)'::`4'::_lambda_1_,bool,uint>::`vftable'
0x14000ddb6  mov     [rsp+278h+var_1A8], rax
0x14000ddbe  lea     rax, [rsp+278h+var_1A8]
0x14000ddc6  mov     [rsp+278h+var_170], rax
0x14000ddce  call    ?Instance@Velocity@VsmUtils@@CAAEAV12@XZ; VsmUtils::Velocity::Instance(void)
0x14000ddd3  lea     rbx, [rax+18h]
0x14000ddd7  lea     rax, [rsp+278h+var_1A8]
0x14000dddf  cmp     rbx, rax
0x14000dde2  jz      short loc_14000DE38
0x14000dde4  mov     rcx, rbx
0x14000dde7  call    ?_Tidy@?$_Func_class@_NI@std@@IEAAXXZ; std::_Func_class<bool,uint>::_Tidy(void)
0x14000ddec  mov     rcx, [rsp+278h+var_170]
0x14000ddf4  test    rcx, rcx
0x14000ddf7  jz      short loc_14000DE38
0x14000ddf9  lea     rax, [rsp+278h+var_1A8]
0x14000de01  cmp     rcx, rax
0x14000de04  jnz     short loc_14000DE28
0x14000de06  mov     rax, [rcx]
0x14000de09  mov     rdx, rbx
0x14000de0c  mov     rax, [rax+8]
0x14000de10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de15  mov     [rbx+38h], rax
0x14000de19  lea     rcx, [rsp+278h+var_1A8]
0x14000de21  call    ?_Tidy@?$_Func_class@_NI@std@@IEAAXXZ; std::_Func_class<bool,uint>::_Tidy(void)
0x14000de26  jmp     short loc_14000DE38
0x14000de28  mov     [rbx+38h], rcx
0x14000de2c  mov     [rsp+278h+var_170], 0
0x14000de38  lea     rcx, [rsp+278h+var_1A8]
0x14000de40  call    ?_Tidy@?$_Func_class@_NI@std@@IEAAXXZ; std::_Func_class<bool,uint>::_Tidy(void)
0x14000de45  nop
0x14000de46  jmp     short $+2
0x14000de48  call    ?Listen@ScopedRpcListener@@AEAAJXZ; ScopedRpcListener::Listen(void)
0x14000de4d  mov     rcx, [rsp+278h]; this
0x14000de55  test    eax, eax
0x14000de57  jns     short loc_14000DE6E
0x14000de59  mov     r9d, eax; char *
0x14000de5c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14000de63  mov     edx, 0Ch; void *
0x14000de68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000de6e  mov     [rsp+278h+var_258], 0; unsigned int
0x14000de77  lea     r8, Name; "Global\\NgcIsoTrustletStartedEvent_29D0"...
0x14000de7e  xor     edx, edx; bInheritHandle
0x14000de80  lea     ecx, [rdx+2]; dwDesiredAccess
0x14000de83  call    cs:__imp_OpenEventW
0x14000de89  test    rax, rax
0x14000de8c  jz      loc_14000DF74
0x14000de92  mov     rdx, rax
0x14000de95  lea     rcx, [rsp+278h+var_258]
0x14000de9a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000de9f  mov     rbx, [rsp+278h+var_258]
0x14000dea4  mov     rcx, rbx; this
0x14000dea7  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14000deac  nop
0x14000dead  test    rbx, rbx
0x14000deb0  jz      short loc_14000DEBA
0x14000deb2  mov     rcx, rbx; this
0x14000deb5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000deba  lea     rcx, [rsp+278h+var_168]; this
0x14000dec2  call    ?StartedEventSignaled@TrustletLifetime@LogProvider@@QEAAXXZ; LogProvider::TrustletLifetime::StartedEventSignaled(void)
0x14000dec7  xor     r8d, r8d; bAlertable
0x14000deca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000decd  mov     rcx, cs:?g_terminationEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hHandle
0x14000ded4  call    cs:__imp_WaitForSingleObjectEx
0x14000deda  cmp     eax, 102h
0x14000dedf  jz      short loc_14000DEFF
0x14000dee1  test    eax, eax
0x14000dee3  jz      short loc_14000DEFF
0x14000dee5  mov     rcx, [rsp+278h]; this
0x14000deed  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000def4  mov     edx, 0B0Fh; void *
0x14000def9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000deff  lea     rcx, [rsp+278h+var_168]; this
0x14000df07  call    ?StopEventSignaled@TrustletLifetime@LogProvider@@QEAAXXZ; LogProvider::TrustletLifetime::StopEventSignaled(void)
0x14000df0c  xor     edx, edx
0x14000df0e  lea     rcx, [rsp+278h+var_168]
0x14000df16  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000df1b  nop
0x14000df1c  xor     ecx, ecx; Binding
0x14000df1e  call    cs:__imp_RpcMgmtStopServerListening
0x14000df24  test    eax, eax
0x14000df26  jz      short loc_14000DF2F
0x14000df28  mov     edx, 24h ; '$'
0x14000df2d  jmp     short loc_14000DF4B
0x14000df2f  xor     edx, edx; MgrTypeUuid
0x14000df31  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x14000df35  lea     rcx, qword_140076D30; IfSpec
0x14000df3c  call    cs:__imp_RpcServerUnregisterIf
0x14000df42  test    eax, eax
0x14000df44  jz      short loc_14000DF63
0x14000df46  mov     edx, 29h ; ')'; void *
0x14000df4b  mov     r9d, eax; char *
0x14000df4e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14000df55  mov     rcx, [rsp+278h]; this
0x14000df5d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000df62  nop
0x14000df63  lea     rcx, [rsp+278h+var_168]; this
0x14000df6b  call    ??1TrustletLifetime@LogProvider@@QEAA@XZ; LogProvider::TrustletLifetime::~TrustletLifetime(void)
0x14000df70  xor     eax, eax
0x14000df72  jmp     short loc_14000DF94
0x14000df74  mov     rcx, [rsp+278h]; this
0x14000df7c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000df82  mov     rcx, [rsp+278h]; this
0x14000df8a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000df90  mov     eax, dword ptr [rsp+278h+var_258]
0x14000df94  mov     rcx, [rsp+278h+var_10]
0x14000df9c  xor     rcx, rsp; StackCookie
0x14000df9f  call    __security_check_cookie
0x14000dfa4  add     rsp, 270h
0x14000dfab  pop     rbx
0x14000dfac  retn
```
