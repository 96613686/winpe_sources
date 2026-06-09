# Windows::Networking::UX::Internal::WlanInterface::_ContinueConnectionFlow(Windows::Networking::UX::IAvailableNetwork *)

- ea: `0x1800488a4`
- end: `0x180048d5d`
- name: `?_ContinueConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@@Z`
- size: `1209`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b2d8`

## callees

- `0x180003ed0`
- `0x1800043bc`
- `0x180008e30`
- `0x18000de4c`
- `0x180012178`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001b230`
- `0x18001d4d4`
- `0x18002f0dc`
- `0x180038c04`
- `0x180039acc`
- `0x18003a070`
- `0x18003a600`
- `0x18003ad84`
- `0x18003c294`
- `0x180044ee4`
- `0x180045228`
- `0x18004591c`
- `0x180045eb0`
- `0x180047680`
- `0x1800476bc`
- `0x180047a64`
- `0x1800488a4`
- `0x180048ee4`
- `0x18004a558`
- `0x18004ab7c`
- `0x18004c324`
- `0x1800663d0`
- `0x180066ec0`
- `0x180074714`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800489cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800489cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048cea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c52`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_ContinueConnectionFlow(
        Windows::Networking::UX::Internal::WlanInterface *this,
        struct Windows::Networking::UX::IAvailableNetwork *a2)
{
  int (__fastcall *v4)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  __int64 v5; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  bool IsProfileEAP; // al
  __int64 v8; // rax
  int inited; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  Windows::Networking::UX::Internal::WlanStateMachine *v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rax
  void *v21; // rcx
  int (__fastcall *v22)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  bool v23; // bl
  const unsigned __int16 *v24; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v27[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  void *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Networking::UX::IUserInputType *v32; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[20]; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+7Ch] [rbp-84h]
  struct _GUID v36; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[42]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[336]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v27[0] = 1;
  *((_BYTE *)this + 40) = 1;
  Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(this, &v36, a2);
  (*(void (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, unsigned __int8 *, _QWORD))(*(_QWORD *)a2 + 160LL))(
    a2,
    v27,
    0);
  if ( **((_DWORD **)this + 138) != 1 )
  {
    wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
    v37[0] = &NetworkUxTelemetry::WlanConnectionFlow::`vftable';
    NetworkUxTelemetry::WlanConnectionFlow::StartActivity((NetworkUxTelemetry::WlanConnectionFlow *)v37, &v36, 0);
    NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnect((NetworkUxTelemetry::WlanConnectionFlow *)v37, v27[0] != 0);
    string = 0;
    v4 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a2 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v4(a2, &string) >= 0 )
    {
      v5 = *((_QWORD *)this + 3);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      IsProfileEAP = Windows::Networking::UX::Internal::ProfileManager::IsProfileEAP(
                       (Windows::Networking::UX::Internal::ProfileManager *)(v5 + 656),
                       &v36,
                       StringRawBuffer);
      NetworkUxTelemetry::WlanConnectionFlow::SetEAPRequest((NetworkUxTelemetry::WlanConnectionFlow *)v37, IsProfileEAP);
    }
    v8 = NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(v37, v38);
    NetworkUxTelemetry::WlanConnectionFlow::operator=((char *)this + 832, v8);
    NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v38);
    WindowsDeleteString(string);
    string = 0;
    NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v37);
  }
  wil::EnterCriticalSection(v33, (char *)this + 752);
  if ( *((_QWORD *)this + 99)
    || (inited = Windows::Networking::UX::Internal::WlanInterface::_InitConnectionFlow(this), inited >= 0) )
  {
    inited = Windows::Networking::UX::Internal::WlanInterface::_SetupConnectionFlow(this, a2);
    if ( inited >= 0 )
    {
      v32 = 0;
      v12 = (Windows::Networking::UX::Internal::WlanStateMachine *)*((_QWORD *)this + 99);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32, v10, v11);
      v13 = Windows::Networking::UX::Internal::WlanStateMachine::ContinueFlow(v12, &v36, a2, v27[0], 1u, &v32);
      if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          238,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          (unsigned int)v13);
      pv = 0;
      *(_QWORD *)v34 = &pv;
      *(_QWORD *)&v34[8] = 0;
      v34[16] = 1;
      inited = Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(
                 *((const struct _L2_UI_REQUEST **)this + 92),
                 (struct _L2_UI_REQUEST **)&v34[8]);
      wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v34);
      if ( inited >= 0 )
      {
        v29 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v29 )
        {
          v16 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
                  &v30,
                  (__int64 *)&pv);
          v18 = Windows::Networking::UX::Internal::WlanUIRequestEvent::WlanUIRequestEvent(v17, (_OWORD *)this + 45, v16);
          v29 = (void *)v18;
          if ( v18 )
          {
            v29 = 0;
            v30 = v18;
            v19 = Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(*((_QWORD *)this + 99), &v30);
            inited = v19;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v19);
            if ( **((_DWORD **)this + 138) == 1 )
            {
              NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread((char *)this + 832, v37);
              NetworkUxTelemetry::WlanConnectionFlow::SetUserInputState(v37, 0, (unsigned int)inited);
              v20 = NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(v37, v38);
              NetworkUxTelemetry::WlanConnectionFlow::operator=((char *)this + 832, v20);
              NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v38);
              NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v37);
            }
          }
        }
        else
        {
          v29 = 0;
        }
        std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v29);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC36,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
          (const char *)(unsigned int)inited,
          v26);
      }
      v21 = pv;
      pv = 0;
      if ( v21 )
        CoTaskMemFree(v21);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32, v14, v15);
    }
  }
  string = 0;
  v22 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v22(a2, &string) >= 0 )
  {
    v23 = v27[0] != 0;
    v24 = WindowsGetStringRawBuffer(string, 0);
    *(_DWORD *)v34 = 13;
    *(struct _GUID *)&v34[4] = v36;
    v35 = 71;
    NetworkingTriageScenario::GetConnected::UXModelWiFiContinueConnectionAction(
      (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v34,
      v24,
      v23,
      inited);
  }
  if ( inited < 0 )
    Windows::Networking::UX::Internal::WlanInterface::CancelConnection(this);
  else
    *((_BYTE *)this + 34) = 1;
  WindowsDeleteString(string);
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v33);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      240,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800488a4  mov     [rsp-8+arg_10], rbx
0x1800488a9  mov     [rsp-8+arg_18], rsi
0x1800488ae  push    rbp
0x1800488af  push    rdi
0x1800488b0  push    r12
0x1800488b2  push    r14
0x1800488b4  push    r15
0x1800488b6  lea     rbp, [rsp-240h]
0x1800488be  sub     rsp, 340h
0x1800488c5  mov     rax, cs:__security_cookie
0x1800488cc  xor     rax, rsp
0x1800488cf  mov     [rbp+260h+var_30], rax
0x1800488d6  mov     r14, rdx
0x1800488d9  mov     rsi, rcx
0x1800488dc  lea     rax, WPP_GLOBAL_Control
0x1800488e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488ea  cmp     rcx, rax
0x1800488ed  jz      short loc_18004890A
0x1800488ef  test    byte ptr [rcx+1Ch], 8
0x1800488f3  jz      short loc_18004890A
0x1800488f5  mov     edx, 0EDh
0x1800488fa  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048901  mov     rcx, [rcx+10h]
0x180048905  call    WPP_SF_
0x18004890a  mov     [rsp+360h+var_330], 1
0x18004890f  mov     byte ptr [rsi+28h], 1
0x180048913  mov     r8, r14; struct Windows::Networking::UX::IAvailableNetwork *
0x180048916  lea     rdx, [rbp+260h+var_2E0]; retstr
0x18004891a  mov     rcx, rsi; this
0x18004891d  call    ?_GetNetworkInterfaceGuid@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AU_GUID@@PEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(Windows::Networking::UX::IAvailableNetwork *)
0x180048922  mov     rax, [r14]
0x180048925  xor     r8d, r8d
0x180048928  lea     rdx, [rsp+360h+var_330]
0x18004892d  mov     rcx, r14
0x180048930  mov     rax, [rax+0A0h]
0x180048937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004893c  lea     r15, [rsi+340h]
0x180048943  mov     rax, [r15+110h]
0x18004894a  xor     r12d, r12d
0x18004894d  cmp     dword ptr [rax], 1
0x180048950  jz      loc_180048A30
0x180048956  lea     rdx, aWlanconnection; "WlanConnectionFlow"
0x18004895d  lea     rcx, [rbp+260h+var_2D0]; struct wil::details::IFailureCallback *
0x180048961  call    ??0?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180048966  lea     rax, ??_7WlanConnectionFlow@NetworkUxTelemetry@@6B@; const NetworkUxTelemetry::WlanConnectionFlow::`vftable'
0x18004896d  mov     [rbp+260h+var_2D0], rax
0x180048971  xor     r8d, r8d; bool
0x180048974  lea     rdx, [rbp+260h+var_2E0]; struct _GUID *
0x180048978  lea     rcx, [rbp+260h+var_2D0]; this
0x18004897c  call    ?StartActivity@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXAEBU_GUID@@_N@Z; NetworkUxTelemetry::WlanConnectionFlow::StartActivity(_GUID const &,bool)
0x180048981  nop
0x180048982  cmp     [rsp+360h+var_330], r12b
0x180048987  setnz   dl; bool
0x18004898a  lea     rcx, [rbp+260h+var_2D0]; this
0x18004898e  call    ?SetAutoConnect@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnect(bool)
0x180048993  mov     [rsp+360h+string], r12
0x180048998  mov     rax, [r14]
0x18004899b  mov     rbx, [rax+30h]
0x18004899f  xor     ecx, ecx; string
0x1800489a1  call    cs:__imp_WindowsDeleteString
0x1800489a7  mov     [rsp+360h+string], r12
0x1800489ac  lea     rdx, [rsp+360h+string]
0x1800489b1  mov     rcx, r14
0x1800489b4  mov     rax, rbx
0x1800489b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489bc  test    eax, eax
0x1800489be  js      short loc_1800489EF
0x1800489c0  mov     rbx, [rsi+18h]
0x1800489c4  xor     edx, edx; length
0x1800489c6  mov     rcx, [rsp+360h+string]; string
0x1800489cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800489d1  mov     r8, rax; unsigned __int16 *
0x1800489d4  lea     rdx, [rbp+260h+var_2E0]; struct _GUID *
0x1800489d8  lea     rcx, [rbx+290h]; this
0x1800489df  call    ?IsProfileEAP@ProfileManager@Internal@UX@Networking@Windows@@QEAA_NPEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::IsProfileEAP(_GUID const *,ushort const *)
0x1800489e4  mov     dl, al; bool
0x1800489e6  lea     rcx, [rbp+260h+var_2D0]; this
0x1800489ea  call    ?SetEAPRequest@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetEAPRequest(bool)
0x1800489ef  lea     rdx, [rbp+260h+var_180]
0x1800489f6  lea     rcx, [rbp+260h+var_2D0]
0x1800489fa  call    ?TransferToMember@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(void)
0x1800489ff  mov     rdx, rax
0x180048a02  mov     rcx, r15
0x180048a05  call    ??4WlanConnectionFlow@NetworkUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; NetworkUxTelemetry::WlanConnectionFlow::operator=(NetworkUxTelemetry::WlanConnectionFlow &&)
0x180048a0a  lea     rcx, [rbp+260h+var_180]; this
0x180048a11  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x180048a16  nop
0x180048a17  mov     rcx, [rsp+360h+string]; string
0x180048a1c  call    cs:__imp_WindowsDeleteString
0x180048a22  mov     [rsp+360h+string], r12
0x180048a27  lea     rcx, [rbp+260h+var_2D0]; this
0x180048a2b  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x180048a30  lea     rdx, [rsi+2F0h]
0x180048a37  lea     rcx, [rsp+360h+var_300]
0x180048a3c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180048a41  nop
0x180048a42  cmp     [rsi+318h], r12
0x180048a49  jnz     short loc_180048A5D
0x180048a4b  mov     rcx, rsi; this
0x180048a4e  call    ?_InitConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJXZ; Windows::Networking::UX::Internal::WlanInterface::_InitConnectionFlow(void)
0x180048a53  mov     edi, eax
0x180048a55  test    eax, eax
0x180048a57  js      loc_180048C63
0x180048a5d  mov     rdx, r14; struct Windows::Networking::UX::IAvailableNetwork *
0x180048a60  mov     rcx, rsi; this
0x180048a63  call    ?_SetupConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_SetupConnectionFlow(Windows::Networking::UX::IAvailableNetwork *)
0x180048a68  mov     edi, eax
0x180048a6a  test    eax, eax
0x180048a6c  js      loc_180048C63
0x180048a72  mov     [rsp+360h+var_308], r12
0x180048a77  mov     rbx, [rsi+318h]
0x180048a7e  lea     rcx, [rsp+360h+var_308]
0x180048a83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048a88  lea     rax, [rsp+360h+var_308]
0x180048a8d  mov     [rsp+360h+var_338], rax; struct Windows::Networking::UX::IUserInputType **
0x180048a92  mov     [rsp+360h+var_340], 1; int
0x180048a97  mov     r9b, [rsp+360h+var_330]; unsigned __int8
0x180048a9c  mov     r8, r14; struct Windows::Networking::UX::IAvailableNetwork *
0x180048a9f  lea     rdx, [rbp+260h+var_2E0]; struct _GUID *
0x180048aa3  mov     rcx, rbx; this
0x180048aa6  call    ?ContinueFlow@WlanStateMachine@Internal@UX@Networking@Windows@@UEAAJAEBU_GUID@@PEAUIAvailableNetwork@345@EEPEAPEAUIUserInputType@345@@Z; Windows::Networking::UX::Internal::WlanStateMachine::ContinueFlow(_GUID const &,Windows::Networking::UX::IAvailableNetwork *,uchar,uchar,Windows::Networking::UX::IUserInputType * *)
0x180048aab  test    eax, eax
0x180048aad  jns     short loc_180048AE2
0x180048aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ab6  lea     rbx, WPP_GLOBAL_Control
0x180048abd  cmp     rcx, rbx
0x180048ac0  jz      short loc_180048AE9
0x180048ac2  test    byte ptr [rcx+1Ch], 2
0x180048ac6  jz      short loc_180048AE9
0x180048ac8  mov     edx, 0EEh
0x180048acd  mov     r9d, eax
0x180048ad0  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048ad7  mov     rcx, [rcx+10h]
0x180048adb  call    WPP_SF_d
0x180048ae0  jmp     short loc_180048AE9
0x180048ae2  lea     rbx, WPP_GLOBAL_Control
0x180048ae9  mov     [rsp+360h+pv], r12
0x180048aee  lea     rax, [rsp+360h+pv]
0x180048af3  mov     [rsp+360h+var_2F8], rax
0x180048af8  mov     [rsp+360h+var_2F8+8], r12
0x180048afd  mov     [rsp+360h+var_2E8], 1
0x180048b02  lea     rdx, [rsp+360h+var_2F8+8]; struct _L2_UI_REQUEST **
0x180048b07  mov     rcx, [rsi+2E0h]; Src
0x180048b0e  call    ?_CopyUIRequest@WlanInterface@Internal@UX@Networking@Windows@@KAJAEBU_L2_UI_REQUEST@@PEAPEAU6@@Z; Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(_L2_UI_REQUEST const &,_L2_UI_REQUEST * *)
0x180048b13  mov     edi, eax
0x180048b15  lea     rcx, [rsp+360h+var_2F8]
0x180048b1a  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180048b1f  mov     rcx, [rbp+268h]; this
0x180048b26  test    edi, edi
0x180048b28  jns     short loc_180048B43
0x180048b2a  mov     r9d, edi; char *
0x180048b2d  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180048b34  mov     edx, 0C36h; void *
0x180048b39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048b3e  jmp     loc_180048C43
0x180048b43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048b4a  mov     ecx, 28h ; '('; unsigned __int64
0x180048b4f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048b54  mov     r9, rax
0x180048b57  mov     [rsp+360h+var_320], rax
0x180048b5c  test    rax, rax
0x180048b5f  jz      loc_180048C33
0x180048b65  lea     rdx, [rsp+360h+pv]
0x180048b6a  lea     rcx, [rsp+360h+var_318]
0x180048b6f  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180048b74  lea     rdx, [rsi+2D0h]
0x180048b7b  mov     r8, rax
0x180048b7e  mov     rcx, r9
0x180048b81  call    ??0WlanUIRequestEvent@Internal@UX@Networking@Windows@@QEAA@AEBU_GUID@@V?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::WlanUIRequestEvent::WlanUIRequestEvent(_GUID const &,wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x180048b86  mov     [rsp+360h+var_320], rax
0x180048b8b  test    rax, rax
0x180048b8e  jz      loc_180048C38
0x180048b94  mov     [rsp+360h+var_320], r12
0x180048b99  mov     [rsp+360h+var_318], rax
0x180048b9e  lea     rdx, [rsp+360h+var_318]
0x180048ba3  mov     rcx, [rsi+318h]
0x180048baa  call    ?PostMediaEvent@WlanStateMachine@Internal@UX@Networking@Windows@@UEAAJV?$unique_ptr@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>)
0x180048baf  mov     edi, eax
0x180048bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bb8  cmp     rcx, rbx
0x180048bbb  jz      short loc_180048BDB
0x180048bbd  test    byte ptr [rcx+1Ch], 8
0x180048bc1  jz      short loc_180048BDB
0x180048bc3  mov     edx, 0EFh
0x180048bc8  mov     r9d, eax
0x180048bcb  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048bd2  mov     rcx, [rcx+10h]
0x180048bd6  call    WPP_SF_d
0x180048bdb  mov     rax, [rsi+450h]
0x180048be2  cmp     dword ptr [rax], 1
0x180048be5  jnz     short loc_180048C38
0x180048be7  lea     rdx, [rbp+260h+var_2D0]
0x180048beb  mov     rcx, r15
0x180048bee  call    ?TransferToCurrentThread@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(void)
0x180048bf3  mov     r8d, edi
0x180048bf6  xor     edx, edx
0x180048bf8  lea     rcx, [rbp+260h+var_2D0]
0x180048bfc  call    ?SetUserInputState@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXW4UserInputState@@J@Z; NetworkUxTelemetry::WlanConnectionFlow::SetUserInputState(UserInputState,long)
0x180048c01  lea     rdx, [rbp+260h+var_180]
0x180048c08  lea     rcx, [rbp+260h+var_2D0]
0x180048c0c  call    ?TransferToMember@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(void)
0x180048c11  mov     rdx, rax
0x180048c14  mov     rcx, r15
0x180048c17  call    ??4WlanConnectionFlow@NetworkUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; NetworkUxTelemetry::WlanConnectionFlow::operator=(NetworkUxTelemetry::WlanConnectionFlow &&)
0x180048c1c  lea     rcx, [rbp+260h+var_180]; this
0x180048c23  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x180048c28  lea     rcx, [rbp+260h+var_2D0]; this
0x180048c2c  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x180048c31  jmp     short loc_180048C38
0x180048c33  mov     [rsp+360h+var_320], r12
0x180048c38  lea     rcx, [rsp+360h+var_320]
0x180048c3d  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x180048c42  nop
0x180048c43  mov     rcx, [rsp+360h+pv]; pv
0x180048c48  mov     [rsp+360h+pv], r12
0x180048c4d  test    rcx, rcx
0x180048c50  jz      short loc_180048C59
0x180048c52  call    cs:__imp_CoTaskMemFree
0x180048c58  nop
0x180048c59  lea     rcx, [rsp+360h+var_308]
0x180048c5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c63  mov     [rsp+360h+string], r12
0x180048c68  mov     rax, [r14]
0x180048c6b  mov     rbx, [rax+30h]
0x180048c6f  xor     ecx, ecx; string
0x180048c71  call    cs:__imp_WindowsDeleteString
0x180048c77  mov     [rsp+360h+string], r12
0x180048c7c  lea     rdx, [rsp+360h+string]
0x180048c81  mov     rcx, r14
0x180048c84  mov     rax, rbx
0x180048c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c8c  test    eax, eax
0x180048c8e  js      short loc_180048CD2
0x180048c90  cmp     [rsp+360h+var_330], r12b
0x180048c95  setnz   bl
0x180048c98  xor     edx, edx; length
0x180048c9a  mov     rcx, [rsp+360h+string]; string
0x180048c9f  call    cs:__imp_WindowsGetStringRawBuffer
0x180048ca5  movaps  xmm0, xmmword ptr [rbp+260h+var_2E0.Data1]
0x180048ca9  mov     dword ptr [rsp+360h+var_2F8], 0Dh
0x180048cb1  movdqu  xmmword ptr [rsp+360h+var_2F8+4], xmm0
0x180048cb7  mov     [rsp+360h+var_2E4], 47h ; 'G'
0x180048cbf  mov     r9d, edi; int
0x180048cc2  mov     r8b, bl; bool
0x180048cc5  mov     rdx, rax; unsigned __int16 *
0x180048cc8  lea     rcx, [rsp+360h+var_2F8]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x180048ccd  call    ?UXModelWiFiContinueConnectionAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG_NJ@Z; NetworkingTriageScenario::GetConnected::UXModelWiFiContinueConnectionAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,bool,long)
0x180048cd2  test    edi, edi
0x180048cd4  js      short loc_180048CDC
0x180048cd6  mov     byte ptr [rsi+22h], 1
0x180048cda  jmp     short loc_180048CE5
0x180048cdc  mov     rcx, rsi; this
0x180048cdf  call    ?CancelConnection@WlanInterface@Internal@UX@Networking@Windows@@QEAAJXZ; Windows::Networking::UX::Internal::WlanInterface::CancelConnection(void)
0x180048ce4  nop
0x180048ce5  mov     rcx, [rsp+360h+string]; string
0x180048cea  call    cs:__imp_WindowsDeleteString
0x180048cf0  mov     [rsp+360h+string], r12
0x180048cf5  lea     rcx, [rsp+360h+var_300]
0x180048cfa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180048cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d06  lea     rax, WPP_GLOBAL_Control
0x180048d0d  cmp     rcx, rax
0x180048d10  jz      short loc_180048D30
0x180048d12  test    byte ptr [rcx+1Ch], 8
0x180048d16  jz      short loc_180048D30
0x180048d18  mov     edx, 0F0h
0x180048d1d  mov     r9d, edi
0x180048d20  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048d27  mov     rcx, [rcx+10h]
0x180048d2b  call    WPP_SF_d
0x180048d30  mov     eax, edi
0x180048d32  mov     rcx, [rbp+260h+var_30]
0x180048d39  xor     rcx, rsp; StackCookie
0x180048d3c  call    __security_check_cookie
0x180048d41  lea     r11, [rsp+360h+var_20]
0x180048d49  mov     rbx, [r11+40h]
0x180048d4d  mov     rsi, [r11+48h]
0x180048d51  mov     rsp, r11
0x180048d54  pop     r15
0x180048d56  pop     r14
0x180048d58  pop     r12
0x180048d5a  pop     rdi
0x180048d5b  pop     rbp
0x180048d5c  retn
```
