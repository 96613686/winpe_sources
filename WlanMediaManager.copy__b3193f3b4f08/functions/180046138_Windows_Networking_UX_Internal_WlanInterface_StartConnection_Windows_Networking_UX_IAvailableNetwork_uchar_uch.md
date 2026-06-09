# Windows::Networking::UX::Internal::WlanInterface::StartConnection(Windows::Networking::UX::IAvailableNetwork *,uchar,uchar,unsigned __int64,Windows::Networking::UX::IUserInputType * *)

- ea: `0x180046138`
- end: `0x18004676d`
- name: `?StartConnection@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEAUIAvailableNetwork@345@EE_KPEAPEAUIUserInputType@345@@Z`
- size: `1589`
- prototype: `__int64 __usercall@<rax>(Windows::Networking::UX::Internal::WlanInterface *__hidden this@<rcx>, struct Windows::Networking::UX::IAvailableNetwork *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, unsigned __int64, struct Windows::Networking::UX::IUserInputType **)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180026df0`

## callees

- `0x180003ed0`
- `0x18000437c`
- `0x18000610c`
- `0x18000de4c`
- `0x180010c6c`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001b838`
- `0x18001caf8`
- `0x18001d4d4`
- `0x1800289dc`
- `0x180037578`
- `0x180038c04`
- `0x18003a158`
- `0x18003a600`
- `0x18003ad84`
- `0x18003c294`
- `0x180044ee4`
- `0x180044f54`
- `0x1800450c0`
- `0x180045228`
- `0x180045eb0`
- `0x180046138`
- `0x180047680`
- `0x1800476bc`
- `0x180047e34`
- `0x180048424`
- `0x18004a558`
- `0x18004ab7c`
- `0x18004c324`
- `0x180067fc0`
- `0x1800746b8`
- `0x180074714`
- `0x1800748ac`
- `0x18008941c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004627c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004627c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageId` at `0x1800463e5`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageId` at `0x1800463e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800462d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800464c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800464fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800466b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800462d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800464c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800464fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800466b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004621f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004648e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004655b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004621f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004648e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004655b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046742`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::StartConnection(
        Windows::Networking::UX::Internal::WlanInterface *this,
        struct Windows::Networking::UX::IAvailableNetwork *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        unsigned __int64 a5,
        struct Windows::Networking::UX::IUserInputType **a6)
{
  int (__fastcall *v9)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  bool v10; // di
  PCWSTR StringRawBuffer; // r15
  _QWORD *v12; // rdi
  _QWORD *i; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  const unsigned __int16 *v16; // rax
  bool IsProfileEAP; // bl
  const wchar_t **v18; // rdi
  BYTE *v19; // rbx
  LONG CurrentPackageId; // eax
  const struct std::nothrow_t *v21; // rdx
  __int64 v22; // rdx
  int (__fastcall *v23)(struct Windows::Networking::UX::IAvailableNetwork *, struct _FILETIME *); // rbx
  __int64 v24; // rbx
  const unsigned __int16 *v25; // rax
  __int64 v26; // rbx
  const unsigned __int16 *v27; // rax
  int v28; // eax
  int inited; // ebx
  __int64 v30; // rax
  int started; // eax
  const unsigned __int16 *v32; // rax
  char v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+31h] [rbp-CFh] BYREF
  unsigned __int8 v36; // [rsp+32h] [rbp-CEh]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 bufferLength; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h]
  struct Windows::Networking::UX::IUserInputType **v43; // [rsp+68h] [rbp-98h]
  struct _GUID v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v46; // [rsp+84h] [rbp-7Ch]
  int v47; // [rsp+94h] [rbp-6Ch]
  _QWORD v48[42]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v49[336]; // [rsp+1F0h] [rbp+F0h] BYREF

  v36 = a4;
  v43 = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  *a6 = 0;
  Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(this, &v44, a2);
  if ( **((_DWORD **)this + 138) == 1 )
  {
    NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread((char *)this + 832, v49);
    SystemTimeAsFileTime.dwLowDateTime = 2;
    NetworkUxTelemetry::WlanConnectionFlow::StopWithResult<enum ConnectionFlowResult>(v49, 0, &SystemTimeAsFileTime);
    NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v49);
  }
  string = 0;
  v9 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v9(a2, &string) < 0 )
  {
    IsProfileEAP = 0;
    v10 = 0;
  }
  else
  {
    v41 = *((_QWORD *)this + 170);
    v42 = *((_QWORD *)this + 171);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v40 = SystemTimeAsFileTime;
    v10 = 0;
    if ( v42 && v41 && v42 > v41 && v42 - v41 <= 300000000 && *(_QWORD *)&v40 - v42 <= 600000000 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = (_QWORD *)*((_QWORD *)this + 168);
      for ( i = (_QWORD *)*v12; i != v12; i = (_QWORD *)*i )
      {
        std::_WChar_traits<unsigned short>::length(StringRawBuffer);
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v14, i[4], StringRawBuffer) )
          break;
      }
      v10 = i == *((_QWORD **)this + 168);
    }
    v15 = *((_QWORD *)this + 3);
    v16 = WindowsGetStringRawBuffer(string, 0);
    IsProfileEAP = Windows::Networking::UX::Internal::ProfileManager::IsProfileEAP(
                     (Windows::Networking::UX::Internal::ProfileManager *)(v15 + 656),
                     &v44,
                     v16);
  }
  wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v48);
  v48[0] = &NetworkUxTelemetry::WlanConnectionFlow::`vftable';
  NetworkUxTelemetry::WlanConnectionFlow::StartActivity((NetworkUxTelemetry::WlanConnectionFlow *)v48, &v44, v10);
  NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnect((NetworkUxTelemetry::WlanConnectionFlow *)v48, a3 != 0);
  v18 = 0;
  v34 = 0;
  (*(void (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, _QWORD, char *))(*(_QWORD *)a2 + 160LL))(
    a2,
    0,
    &v34);
  NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnectVisiblity(
    (NetworkUxTelemetry::WlanConnectionFlow *)v48,
    v34 != 0);
  NetworkUxTelemetry::WlanConnectionFlow::SetEAPRequest((NetworkUxTelemetry::WlanConnectionFlow *)v48, IsProfileEAP);
  bufferLength = 0;
  v19 = 0;
  v40 = 0;
  while ( 1 )
  {
    CurrentPackageId = GetCurrentPackageId(&bufferLength, v19);
    if ( CurrentPackageId != 122 )
      break;
    v19 = (BYTE *)operator new[](bufferLength, (const struct std::nothrow_t *)&std::nothrow);
    v40 = (struct _FILETIME)v19;
    if ( v18 )
      operator delete(v18, v21);
    v18 = (const wchar_t **)v19;
  }
  if ( CurrentPackageId )
  {
    v22 = 0;
    if ( CurrentPackageId == 15700 )
      v22 = 2;
  }
  else
  {
    v22 = wcscmp_0(v18[2], L"windows.immersivecontrolpanel") == 0;
  }
  NetworkUxTelemetry::WlanConnectionFlow::SetConnectionFlowOrigin(v48, v22);
  v35 = 0;
  if ( (*(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, char *))(*(_QWORD *)a2 + 136LL))(
         a2,
         &v35) >= 0
    && v35 )
  {
    SystemTimeAsFileTime = 0;
    v23 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, struct _FILETIME *))(*(_QWORD *)a2 + 48LL);
    WindowsDeleteString(0);
    SystemTimeAsFileTime = 0;
    if ( v23(a2, &SystemTimeAsFileTime) >= 0 )
    {
      if ( v34 )
      {
        v24 = *((_QWORD *)this + 3);
        v25 = WindowsGetStringRawBuffer(*(HSTRING *)&SystemTimeAsFileTime, 0);
        if ( Windows::Networking::UX::Internal::ProfileManager::IsProfileAutoConnect(
               (Windows::Networking::UX::Internal::ProfileManager *)(v24 + 656),
               &v44,
               v25) != (a3 != 0) )
        {
          v26 = *((_QWORD *)this + 3);
          v27 = WindowsGetStringRawBuffer(*(HSTRING *)&SystemTimeAsFileTime, 0);
          v28 = Windows::Networking::UX::Internal::ProfileManager::SetProfileAutoConnect(
                  (Windows::Networking::UX::Internal::ProfileManager *)(v26 + 656),
                  &v44,
                  v27,
                  a3 != 0);
          if ( v28 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
              (unsigned int)v28);
        }
      }
    }
    WindowsDeleteString(*(HSTRING *)&SystemTimeAsFileTime);
  }
  wil::EnterCriticalSection(&v41, (char *)this + 752);
  if ( *((_QWORD *)this + 99) )
  {
    *((_OWORD *)this + 44) = *(_OWORD *)((char *)this + 680);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
    Windows::Networking::UX::Internal::WlanInterface::_CleanupConnectionFlow(this);
  }
  inited = Windows::Networking::UX::Internal::WlanInterface::_InitConnectionFlow(this);
  if ( inited < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)inited);
  v30 = NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(v48, v49);
  NetworkUxTelemetry::WlanConnectionFlow::operator=((char *)this + 832, v30);
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v49);
  if ( inited >= 0 )
  {
    inited = Windows::Networking::UX::Internal::WlanInterface::_SetupConnectionFlow(this, a2);
    if ( inited >= 0 )
    {
      *((_BYTE *)this + 34) = 1;
      started = Windows::Networking::UX::Internal::WlanStateMachine::StartFlow(
                  *((Windows::Networking::UX::Internal::WlanStateMachine **)this + 99),
                  &v44,
                  a2,
                  a3,
                  v36,
                  v43);
      inited = started;
      if ( started < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          (unsigned int)started);
    }
  }
  v32 = WindowsGetStringRawBuffer(string, 0);
  v45 = 13;
  v46 = v44;
  v47 = 71;
  NetworkingTriageScenario::GetConnected::UXModelWiFiStartConnectionAction(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v45,
    v32,
    a3 != 0,
    inited);
  if ( inited < 0 )
    Windows::Networking::UX::Internal::WlanInterface::CancelConnection(this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v41);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)inited);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v40);
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v48);
  WindowsDeleteString(string);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180046138  push    rbp
0x18004613a  push    rbx
0x18004613b  push    rsi
0x18004613c  push    rdi
0x18004613d  push    r12
0x18004613f  push    r13
0x180046141  push    r14
0x180046143  push    r15
0x180046145  lea     rbp, [rsp-258h]
0x18004614d  sub     rsp, 358h
0x180046154  mov     rax, cs:__security_cookie
0x18004615b  xor     rax, rsp
0x18004615e  mov     [rbp+290h+var_50], rax
0x180046165  mov     [rsp+390h+var_35E], r9b
0x18004616a  mov     r12b, r8b
0x18004616d  mov     r14, rdx
0x180046170  mov     rsi, rcx
0x180046173  mov     rbx, [rbp+290h+arg_28]
0x18004617a  mov     [rsp+390h+var_328], rbx
0x18004617f  lea     rax, WPP_GLOBAL_Control
0x180046186  mov     rcx, cs:WPP_GLOBAL_Control
0x18004618d  cmp     rcx, rax
0x180046190  jz      short loc_1800461AD
0x180046192  test    byte ptr [rcx+1Ch], 8
0x180046196  jz      short loc_1800461AD
0x180046198  mov     edx, 3Eh ; '>'
0x18004619d  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x1800461a4  mov     rcx, [rcx+10h]
0x1800461a8  call    WPP_SF_
0x1800461ad  mov     qword ptr [rbx], 0
0x1800461b4  mov     r8, r14; struct Windows::Networking::UX::IAvailableNetwork *
0x1800461b7  lea     rdx, [rsp+390h+var_320]; retstr
0x1800461bc  mov     rcx, rsi; this
0x1800461bf  call    ?_GetNetworkInterfaceGuid@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AU_GUID@@PEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(Windows::Networking::UX::IAvailableNetwork *)
0x1800461c4  lea     r13, [rsi+340h]
0x1800461cb  mov     rax, [r13+110h]
0x1800461d2  cmp     dword ptr [rax], 1
0x1800461d5  jnz     short loc_18004620D
0x1800461d7  lea     rdx, [rbp+290h+var_1A0]
0x1800461de  mov     rcx, r13
0x1800461e1  call    ?TransferToCurrentThread@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(void)
0x1800461e6  mov     [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], 2
0x1800461ee  lea     r8, [rsp+390h+SystemTimeAsFileTime]
0x1800461f3  xor     edx, edx
0x1800461f5  lea     rcx, [rbp+290h+var_1A0]
0x1800461fc  call    ??$StopWithResult@W4ConnectionFlowResult@@@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXJ$$QEAW4ConnectionFlowResult@@@Z; NetworkUxTelemetry::WlanConnectionFlow::StopWithResult<ConnectionFlowResult>(long,ConnectionFlowResult &&)
0x180046201  lea     rcx, [rbp+290h+var_1A0]; this
0x180046208  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18004620d  mov     [rsp+390h+string], 0
0x180046216  mov     rax, [r14]
0x180046219  mov     rbx, [rax+30h]
0x18004621d  xor     ecx, ecx; string
0x18004621f  call    cs:__imp_WindowsDeleteString
0x180046225  mov     [rsp+390h+string], 0
0x18004622e  lea     rdx, [rsp+390h+string]
0x180046233  mov     rcx, r14
0x180046236  mov     rax, rbx
0x180046239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004623e  test    eax, eax
0x180046240  js      loc_180046351
0x180046246  mov     eax, [rsi+554h]
0x18004624c  mov     dword ptr [rsp+390h+var_338+4], eax
0x180046250  mov     eax, [rsi+550h]
0x180046256  mov     dword ptr [rsp+390h+var_338], eax
0x18004625a  mov     eax, [rsi+55Ch]
0x180046260  mov     dword ptr [rsp+390h+var_330+4], eax
0x180046264  mov     eax, [rsi+558h]
0x18004626a  mov     dword ptr [rsp+390h+var_330], eax
0x18004626e  mov     qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180046277  lea     rcx, [rsp+390h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004627c  call    cs:__imp_GetSystemTimeAsFileTime
0x180046282  mov     eax, [rsp+390h+SystemTimeAsFileTime.dwHighDateTime]
0x180046286  mov     dword ptr [rsp+390h+var_340+4], eax
0x18004628a  mov     eax, [rsp+390h+SystemTimeAsFileTime.dwLowDateTime]
0x18004628e  mov     dword ptr [rsp+390h+var_340], eax
0x180046292  xor     dil, dil
0x180046295  mov     rax, [rsp+390h+var_330]
0x18004629a  test    rax, rax
0x18004629d  jz      loc_180046328
0x1800462a3  mov     rcx, [rsp+390h+var_338]
0x1800462a8  test    rcx, rcx
0x1800462ab  jz      short loc_180046328
0x1800462ad  cmp     rax, rcx
0x1800462b0  jle     short loc_180046328
0x1800462b2  mov     rdx, rax
0x1800462b5  sub     rdx, rcx
0x1800462b8  cmp     rdx, 11E1A300h
0x1800462bf  jg      short loc_180046328
0x1800462c1  mov     rcx, [rsp+390h+var_340]
0x1800462c6  sub     rcx, rax
0x1800462c9  cmp     rcx, 23C34600h
0x1800462d0  jg      short loc_180046328
0x1800462d2  xor     edx, edx; length
0x1800462d4  mov     rcx, [rsp+390h+string]; string
0x1800462d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800462df  mov     r15, rax
0x1800462e2  mov     rdi, [rsi+540h]
0x1800462e9  mov     rbx, [rdi]
0x1800462ec  cmp     rbx, rdi
0x1800462ef  jz      short loc_18004631D
0x1800462f1  mov     rcx, r15
0x1800462f4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800462f9  mov     r9, rax
0x1800462fc  lea     rcx, [rbx+10h]
0x180046300  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046305  mov     r8, r15
0x180046308  mov     rdx, [rbx+20h]
0x18004630c  mov     rcx, rax
0x18004630f  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180046314  test    al, al
0x180046316  jnz     short loc_18004631D
0x180046318  mov     rbx, [rbx]
0x18004631b  jmp     short loc_1800462EC
0x18004631d  cmp     rbx, [rsi+540h]
0x180046324  setz    dil
0x180046328  mov     rbx, [rsi+18h]
0x18004632c  xor     edx, edx; length
0x18004632e  mov     rcx, [rsp+390h+string]; string
0x180046333  call    cs:__imp_WindowsGetStringRawBuffer
0x180046339  mov     r8, rax; unsigned __int16 *
0x18004633c  lea     rdx, [rsp+390h+var_320]; struct _GUID *
0x180046341  lea     rcx, [rbx+290h]; this
0x180046348  call    ?IsProfileEAP@ProfileManager@Internal@UX@Networking@Windows@@QEAA_NPEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::IsProfileEAP(_GUID const *,ushort const *)
0x18004634d  mov     bl, al
0x18004634f  jmp     short loc_180046356
0x180046351  xor     bl, bl
0x180046353  xor     dil, dil
0x180046356  lea     rdx, aWlanconnection; "WlanConnectionFlow"
0x18004635d  lea     rcx, [rbp+290h+var_2F0]; struct wil::details::IFailureCallback *
0x180046361  call    ??0?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180046366  lea     rax, ??_7WlanConnectionFlow@NetworkUxTelemetry@@6B@; const NetworkUxTelemetry::WlanConnectionFlow::`vftable'
0x18004636d  mov     [rbp+290h+var_2F0], rax
0x180046371  mov     r8b, dil; bool
0x180046374  lea     rdx, [rsp+390h+var_320]; struct _GUID *
0x180046379  lea     rcx, [rbp+290h+var_2F0]; this
0x18004637d  call    ?StartActivity@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXAEBU_GUID@@_N@Z; NetworkUxTelemetry::WlanConnectionFlow::StartActivity(_GUID const &,bool)
0x180046382  nop
0x180046383  test    r12b, r12b
0x180046386  setnz   r15b
0x18004638a  mov     dl, r15b; bool
0x18004638d  lea     rcx, [rbp+290h+var_2F0]; this
0x180046391  call    ?SetAutoConnect@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnect(bool)
0x180046396  xor     edi, edi
0x180046398  mov     [rsp+390h+var_360], dil
0x18004639d  mov     rax, [r14]
0x1800463a0  lea     r8, [rsp+390h+var_360]
0x1800463a5  xor     edx, edx
0x1800463a7  mov     rcx, r14
0x1800463aa  mov     rax, [rax+0A0h]
0x1800463b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463b6  cmp     [rsp+390h+var_360], dil
0x1800463bb  setnz   dl; bool
0x1800463be  lea     rcx, [rbp+290h+var_2F0]; this
0x1800463c2  call    ?SetAutoConnectVisiblity@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetAutoConnectVisiblity(bool)
0x1800463c7  mov     dl, bl; bool
0x1800463c9  lea     rcx, [rbp+290h+var_2F0]; this
0x1800463cd  call    ?SetEAPRequest@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetEAPRequest(bool)
0x1800463d2  mov     [rsp+390h+bufferLength], edi
0x1800463d6  mov     ebx, edi
0x1800463d8  mov     [rsp+390h+var_340], rbx
0x1800463dd  mov     rdx, rbx; buffer
0x1800463e0  lea     rcx, [rsp+390h+bufferLength]; bufferLength
0x1800463e5  call    cs:__imp_GetCurrentPackageId
0x1800463eb  cmp     eax, 7Ah ; 'z'
0x1800463ee  jnz     short loc_18004641A
0x1800463f0  mov     ecx, [rsp+390h+bufferLength]; unsigned __int64
0x1800463f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800463fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180046400  mov     rbx, rax
0x180046403  mov     [rsp+390h+var_340], rax
0x180046408  test    rdi, rdi
0x18004640b  jz      short loc_180046415
0x18004640d  mov     rcx, rdi; void *
0x180046410  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180046415  mov     rdi, rbx
0x180046418  jmp     short loc_1800463DD
0x18004641a  test    eax, eax
0x18004641c  jnz     short loc_180046439
0x18004641e  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel"
0x180046425  mov     rcx, [rdi+10h]; String1
0x180046429  call    wcscmp_0
0x18004642e  xor     edi, edi
0x180046430  mov     edx, edi
0x180046432  test    eax, eax
0x180046434  setz    dl
0x180046437  jmp     short loc_180046448
0x180046439  xor     edi, edi
0x18004643b  mov     edx, edi
0x18004643d  cmp     eax, 3D54h
0x180046442  lea     eax, [rdi+2]
0x180046445  cmovz   edx, eax
0x180046448  lea     rcx, [rbp+290h+var_2F0]
0x18004644c  call    ?SetConnectionFlowOrigin@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXW4CFEConnectionFlowOrigin@@@Z; NetworkUxTelemetry::WlanConnectionFlow::SetConnectionFlowOrigin(CFEConnectionFlowOrigin)
0x180046451  mov     [rsp+390h+var_35F], dil
0x180046456  mov     rax, [r14]
0x180046459  lea     rdx, [rsp+390h+var_35F]
0x18004645e  mov     rcx, r14
0x180046461  mov     rax, [rax+88h]
0x180046468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004646d  test    eax, eax
0x18004646f  js      loc_180046563
0x180046475  cmp     [rsp+390h+var_35F], dil
0x18004647a  jz      loc_180046563
0x180046480  mov     qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180046485  mov     rax, [r14]
0x180046488  mov     rbx, [rax+30h]
0x18004648c  xor     ecx, ecx; string
0x18004648e  call    cs:__imp_WindowsDeleteString
0x180046494  mov     qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180046499  lea     rdx, [rsp+390h+SystemTimeAsFileTime]
0x18004649e  mov     rcx, r14
0x1800464a1  mov     rax, rbx
0x1800464a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464a9  test    eax, eax
0x1800464ab  js      loc_18004654F
0x1800464b1  cmp     [rsp+390h+var_360], dil
0x1800464b6  jz      loc_18004654F
0x1800464bc  mov     rbx, [rsi+18h]
0x1800464c0  xor     edx, edx; length
0x1800464c2  mov     rcx, qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime]; string
0x1800464c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800464cd  mov     r8, rax; unsigned __int16 *
0x1800464d0  lea     rdx, [rsp+390h+var_320]; struct _GUID *
0x1800464d5  lea     rcx, [rbx+290h]; this
0x1800464dc  call    ?IsProfileAutoConnect@ProfileManager@Internal@UX@Networking@Windows@@QEAA_NPEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::IsProfileAutoConnect(_GUID const *,ushort const *)
0x1800464e1  mov     ecx, edi
0x1800464e3  test    r12b, r12b
0x1800464e6  setnz   cl
0x1800464e9  movzx   eax, al
0x1800464ec  cmp     eax, ecx
0x1800464ee  jz      short loc_18004654F
0x1800464f0  mov     rbx, [rsi+18h]
0x1800464f4  xor     edx, edx; length
0x1800464f6  mov     rcx, qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime]; string
0x1800464fb  call    cs:__imp_WindowsGetStringRawBuffer
0x180046501  mov     r9b, r15b; bool
0x180046504  mov     r8, rax; unsigned __int16 *
0x180046507  lea     rdx, [rsp+390h+var_320]; struct _GUID *
0x18004650c  lea     rcx, [rbx+290h]; this
0x180046513  call    ?SetProfileAutoConnect@ProfileManager@Internal@UX@Networking@Windows@@QEAAJPEBU_GUID@@PEBG_N@Z; Windows::Networking::UX::Internal::ProfileManager::SetProfileAutoConnect(_GUID const *,ushort const *,bool)
0x180046518  test    eax, eax
0x18004651a  jns     short loc_18004654F
0x18004651c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046523  lea     rbx, WPP_GLOBAL_Control
0x18004652a  cmp     rcx, rbx
0x18004652d  jz      short loc_180046556
0x18004652f  test    byte ptr [rcx+1Ch], 2
0x180046533  jz      short loc_180046556
0x180046535  mov     edx, 3Fh ; '?'
0x18004653a  mov     r9d, eax
0x18004653d  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180046544  mov     rcx, [rcx+10h]
0x180046548  call    WPP_SF_d
0x18004654d  jmp     short loc_180046556
0x18004654f  lea     rbx, WPP_GLOBAL_Control
0x180046556  mov     rcx, qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime]; string
0x18004655b  call    cs:__imp_WindowsDeleteString
0x180046561  jmp     short loc_18004656A
0x180046563  lea     rbx, WPP_GLOBAL_Control
0x18004656a  lea     rdx, [rsi+2F0h]
0x180046571  lea     rcx, [rsp+390h+var_338]
0x180046576  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004657b  nop
0x18004657c  cmp     [rsi+318h], rdi
0x180046583  jz      short loc_1800465C7
0x180046585  lea     r9, [rsi+2C0h]
0x18004658c  movups  xmm0, xmmword ptr [rsi+2A8h]
0x180046593  movdqu  xmmword ptr [r9], xmm0
0x180046598  mov     rcx, cs:WPP_GLOBAL_Control
0x18004659f  cmp     rcx, rbx
0x1800465a2  jz      short loc_1800465BF
0x1800465a4  test    byte ptr [rcx+1Ch], 8
0x1800465a8  jz      short loc_1800465BF
0x1800465aa  mov     edx, 40h ; '@'
0x1800465af  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x1800465b6  mov     rcx, [rcx+10h]
0x1800465ba  call    WPP_SF__guid_
0x1800465bf  mov     rcx, rsi
0x1800465c2  call    ?_CleanupConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUwrite_lock_required@wil@@@Z; Windows::Networking::UX::Internal::WlanInterface::_CleanupConnectionFlow(wil::write_lock_required)
0x1800465c7  mov     rcx, rsi; this
0x1800465ca  call    ?_InitConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJXZ; Windows::Networking::UX::Internal::WlanInterface::_InitConnectionFlow(void)
0x1800465cf  mov     ebx, eax
0x1800465d1  test    eax, eax
0x1800465d3  jns     short loc_180046606
0x1800465d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465dc  lea     rax, WPP_GLOBAL_Control
0x1800465e3  cmp     rcx, rax
0x1800465e6  jz      short loc_180046606
0x1800465e8  test    byte ptr [rcx+1Ch], 2
0x1800465ec  jz      short loc_180046606
0x1800465ee  mov     edx, 41h ; 'A'
0x1800465f3  mov     r9d, ebx
0x1800465f6  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x1800465fd  mov     rcx, [rcx+10h]
0x180046601  call    WPP_SF_d
0x180046606  lea     rdx, [rbp+290h+var_1A0]
0x18004660d  lea     rcx, [rbp+290h+var_2F0]
0x180046611  call    ?TransferToMember@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(void)
0x180046616  mov     rdx, rax
0x180046619  mov     rcx, r13
  ... truncated ...
```
