# Windows::Networking::UX::Internal::WlanInterface::Connect(Windows::Networking::UX::IAvailableNetwork *,bool,HSTRING__ *,_WLAN_PRECONNECT_INPUT_RESPONSE const *)

- ea: `0x18003cc80`
- end: `0x18003ce4a`
- name: `?Connect@WlanInterface@Internal@UX@Networking@Windows@@UEAAJPEAUIAvailableNetwork@345@_NPEAUHSTRING__@@PEBU_WLAN_PRECONNECT_INPUT_RESPONSE@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *, bool, HSTRING, const struct _WLAN_PRECONNECT_INPUT_RESPONSE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x1800121e8`
- `0x180013738`
- `0x1800141a0`
- `0x18001d4d4`
- `0x18003a600`
- `0x18003ad84`
- `0x18003cc80`
- `0x1800453dc`
- `0x1800460c8`
- `0x180047680`
- `0x1800476bc`
- `0x18004a558`
- `0x18004c514`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cda5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cda5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ce10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cd77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ce10`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::Connect(
        Windows::Networking::UX::Internal::WlanClient **this,
        struct Windows::Networking::UX::IAvailableNetwork *a2,
        bool a3,
        HSTRING a4,
        const struct _WLAN_PRECONNECT_INPUT_RESPONSE *a5)
{
  char *v9; // r14
  __int64 v10; // rdx
  unsigned int v11; // edi
  int (__fastcall *v12)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v14; // rax
  char v16; // [rsp+30h] [rbp-D0h]
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 length; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v19; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[336]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[336]; // [rsp+1B0h] [rbp+B0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v9 = (char *)(this + 104);
  NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(this + 104, v20);
  Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(
    (Windows::Networking::UX::Internal::WlanInterface *)this,
    &v19,
    a2);
  wil::EnterCriticalSection(&length, this + 163);
  LOBYTE(v10) = v16;
  Windows::Networking::UX::Internal::WlanInterface::_SetupPasskeyMismatchAcmFlags(this, v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&length);
  v11 = Windows::Networking::UX::Internal::WlanClient::Connect(this[3], &v19, a2, a3, a4, a5);
  NetworkUxTelemetry::WlanConnectionFlow::StartConnection((NetworkUxTelemetry::WlanConnectionFlow *)v20, v11);
  string = 0;
  v12 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v12(a2, &string) >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    NetworkUxTelemetry::WlanConnectionFlow::SetNetworkSSID(
      (NetworkUxTelemetry::WlanConnectionFlow *)v20,
      StringRawBuffer);
  }
  v14 = NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(v20, v21);
  NetworkUxTelemetry::WlanConnectionFlow::operator=(v9, v14);
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v21);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v11);
  WindowsDeleteString(string);
  string = 0;
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v20);
  return v11;
}

```

## disassembly

```asm
0x18003cc80  push    rbp
0x18003cc82  push    rbx
0x18003cc83  push    rsi
0x18003cc84  push    rdi
0x18003cc85  push    r12
0x18003cc87  push    r13
0x18003cc89  push    r14
0x18003cc8b  push    r15
0x18003cc8d  lea     rbp, [rsp-218h]
0x18003cc95  sub     rsp, 318h
0x18003cc9c  mov     rax, cs:__security_cookie
0x18003cca3  xor     rax, rsp
0x18003cca6  mov     [rbp+250h+var_50], rax
0x18003ccad  mov     r15, r9
0x18003ccb0  mov     dil, r8b
0x18003ccb3  mov     rsi, rdx
0x18003ccb6  mov     rbx, rcx
0x18003ccb9  mov     r12, [rbp+250h+arg_20]
0x18003ccc0  lea     r13, WPP_GLOBAL_Control
0x18003ccc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ccce  cmp     rcx, r13
0x18003ccd1  jz      short loc_18003CCEE
0x18003ccd3  test    byte ptr [rcx+1Ch], 8
0x18003ccd7  jz      short loc_18003CCEE
0x18003ccd9  mov     edx, 0B0h
0x18003ccde  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003cce5  mov     rcx, [rcx+10h]
0x18003cce9  call    WPP_SF_
0x18003ccee  lea     r14, [rbx+340h]
0x18003ccf5  lea     rdx, [rsp+350h+var_2F0]
0x18003ccfa  mov     rcx, r14
0x18003ccfd  call    ?TransferToCurrentThread@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(void)
0x18003cd02  nop
0x18003cd03  mov     r8, rsi; struct Windows::Networking::UX::IAvailableNetwork *
0x18003cd06  lea     rdx, [rsp+350h+var_308]; retstr
0x18003cd0b  mov     rcx, rbx; this
0x18003cd0e  call    ?_GetNetworkInterfaceGuid@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AU_GUID@@PEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(Windows::Networking::UX::IAvailableNetwork *)
0x18003cd13  lea     rdx, [rbx+518h]
0x18003cd1a  lea     rcx, [rsp+350h+length]
0x18003cd1f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003cd24  mov     dl, [rsp+350h+var_320]
0x18003cd28  mov     rcx, rbx
0x18003cd2b  call    ?_SetupPasskeyMismatchAcmFlags@WlanInterface@Internal@UX@Networking@Windows@@IEAAXUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::WlanInterface::_SetupPasskeyMismatchAcmFlags(wil::write_lock_required)
0x18003cd30  lea     rcx, [rsp+350h+length]
0x18003cd35  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003cd3a  mov     [rsp+350h+var_328], r12; struct _WLAN_PRECONNECT_INPUT_RESPONSE *
0x18003cd3f  mov     [rsp+350h+var_330], r15; HSTRING
0x18003cd44  mov     r9b, dil; bool
0x18003cd47  mov     r8, rsi; struct Windows::Networking::UX::IAvailableNetwork *
0x18003cd4a  lea     rdx, [rsp+350h+var_308]; struct _GUID *
0x18003cd4f  mov     rcx, [rbx+18h]; this
0x18003cd53  call    ?Connect@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUIAvailableNetwork@345@_NPEAUHSTRING__@@PEBU_WLAN_PRECONNECT_INPUT_RESPONSE@@@Z; Windows::Networking::UX::Internal::WlanClient::Connect(_GUID const &,Windows::Networking::UX::IAvailableNetwork *,bool,HSTRING__ *,_WLAN_PRECONNECT_INPUT_RESPONSE const *)
0x18003cd58  mov     edi, eax
0x18003cd5a  mov     edx, eax; int
0x18003cd5c  lea     rcx, [rsp+350h+var_2F0]; this
0x18003cd61  call    ?StartConnection@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXJ@Z; NetworkUxTelemetry::WlanConnectionFlow::StartConnection(long)
0x18003cd66  xor     r15d, r15d
0x18003cd69  mov     [rsp+350h+string], r15
0x18003cd6e  mov     rdx, [rsi]
0x18003cd71  mov     rbx, [rdx+30h]
0x18003cd75  xor     ecx, ecx; string
0x18003cd77  call    cs:__imp_WindowsDeleteString
0x18003cd7d  mov     [rsp+350h+string], r15
0x18003cd82  lea     rdx, [rsp+350h+string]
0x18003cd87  mov     rcx, rsi
0x18003cd8a  mov     rax, rbx
0x18003cd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd92  test    eax, eax
0x18003cd94  js      short loc_18003CDB8
0x18003cd96  mov     [rsp+350h+length], r15d
0x18003cd9b  lea     rdx, [rsp+350h+length]; length
0x18003cda0  mov     rcx, [rsp+350h+string]; string
0x18003cda5  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cdab  mov     rdx, rax; unsigned __int16 *
0x18003cdae  lea     rcx, [rsp+350h+var_2F0]; this
0x18003cdb3  call    ?SetNetworkSSID@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXPEBG@Z; NetworkUxTelemetry::WlanConnectionFlow::SetNetworkSSID(ushort const *)
0x18003cdb8  lea     rdx, [rbp+250h+var_1A0]
0x18003cdbf  lea     rcx, [rsp+350h+var_2F0]
0x18003cdc4  call    ?TransferToMember@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(void)
0x18003cdc9  mov     rdx, rax
0x18003cdcc  mov     rcx, r14
0x18003cdcf  call    ??4WlanConnectionFlow@NetworkUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; NetworkUxTelemetry::WlanConnectionFlow::operator=(NetworkUxTelemetry::WlanConnectionFlow &&)
0x18003cdd4  lea     rcx, [rbp+250h+var_1A0]; this
0x18003cddb  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18003cde0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cde7  cmp     rcx, r13
0x18003cdea  jz      short loc_18003CE0B
0x18003cdec  test    byte ptr [rcx+1Ch], 8
0x18003cdf0  jz      short loc_18003CE0B
0x18003cdf2  mov     edx, 0B1h
0x18003cdf7  mov     r9d, edi
0x18003cdfa  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003ce01  mov     rcx, [rcx+10h]
0x18003ce05  call    WPP_SF_d
0x18003ce0a  nop
0x18003ce0b  mov     rcx, [rsp+350h+string]; string
0x18003ce10  call    cs:__imp_WindowsDeleteString
0x18003ce16  mov     [rsp+350h+string], r15
0x18003ce1b  lea     rcx, [rsp+350h+var_2F0]; this
0x18003ce20  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18003ce25  mov     eax, edi
0x18003ce27  mov     rcx, [rbp+250h+var_50]
0x18003ce2e  xor     rcx, rsp; StackCookie
0x18003ce31  call    __security_check_cookie
0x18003ce36  add     rsp, 318h
0x18003ce3d  pop     r15
0x18003ce3f  pop     r14
0x18003ce41  pop     r13
0x18003ce43  pop     r12
0x18003ce45  pop     rdi
0x18003ce46  pop     rsi
0x18003ce47  pop     rbx
0x18003ce48  pop     rbp
0x18003ce49  retn
```
