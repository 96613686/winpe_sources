# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog(winrt::Windows::Internal::NetworkUX::Firewall::FirewallNotificationProperties const &,winrt::hstring)

- ea: `0x18001fd60`
- end: `0x180020080`
- name: `?ShowDialog@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXAEBUFirewallNotificationProperties@34567@Uhstring@7@@Z`
- size: `800`
- prototype: `int __fastcall(__int64, __int64, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009e90`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x180002d55`
- `0x180002d91`
- `0x180004c90`
- `0x1800056ec`
- `0x180006b20`
- `0x1800148d0`
- `0x18001584c`
- `0x180016c60`
- `0x180016dbc`
- `0x1800175c0`
- `0x180018360`
- `0x1800184dc`
- `0x18001ae24`
- `0x18001f6f4`
- `0x18001fd60`
- `0x180022974`
- `0x180028fcc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002000b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002000b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001ff65`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001ff65`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18001fe23`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18001fe23`
- `ntdll!RtlQueryElevationFlags` at `0x18001fe95`
- `ntdll!RtlQueryElevationFlags` at `0x18001fe95`
- `msvcp_win!_Thrd_detach` at `0x18001ff94`
- `msvcp_win!_Thrd_detach` at `0x18001ff94`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180020017`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180020028`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180020017`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180020028`

## string_xrefs

- `0x180020035`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x180020050`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x18002006b`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
int __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog(
        __int64 a1,
        __int64 a2,
        volatile signed __int32 **a3)
{
  volatile signed __int32 *v6; // rcx
  wil::details::in1diag3 *v7; // rax
  wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  char v13; // al
  _QWORD *v14; // rax
  int result; // eax
  volatile signed __int32 *v16; // rdi
  int v17; // esi
  HANDLE ProcessHeap; // rax
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _Thrd_t v21; // [rsp+40h] [rbp-C0h] BYREF
  _Thrd_t v22; // [rsp+50h] [rbp-B0h]
  _QWORD v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v24[42]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v25[42]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v23[2] = a3;
  wil::WaitForDebuggerPresent((wil *)a1, a2);
  v6 = *a3;
  if ( !*a3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      (const char *)0x80070057LL,
      v19);
  if ( !*(_DWORD *)a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      (const char *)0x80070057LL,
      v19);
  v7 = retaddr;
  if ( (*(_BYTE *)a2 & 7) == 0 )
LABEL_26:
    wil::details::in1diag3::_Throw_Hr(
      v7,
      (void *)0x3D,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
      (const char *)0x80070057LL,
      v19);
  if ( v6 )
    v8 = (wchar_t *)*((_QWORD *)v6 + 2);
  else
    v8 = (wchar_t *)&szFile;
  v21._Hnd = v8;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  *(_QWORD *)&v21._Id = v9;
  GetImageNameFromFullPath((__int64)v23, (wchar_t **)&v21);
  FirewallUxTelemetry::NotificationDialogParameters(a2, v23);
  CoAddRefServerProcess();
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v24,
    "DialogInitialize");
  v24[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  FirewallUxTelemetry::DialogInitialize::StartActivity((FirewallUxTelemetry::DialogInitialize *)v24, L"Notification");
  winrt::hstring::operator=(a1 + 24, a3);
  *(_DWORD *)(a1 + 80) = 0;
  *(_OWORD *)(a1 + 504) = *(_OWORD *)a2;
  *(_QWORD *)(a1 + 520) = *(_QWORD *)(a2 + 16);
  if ( !*(_BYTE *)(a1 + 525) )
  {
    LODWORD(v20) = 0;
    v10 = RtlQueryElevationFlags(&v20);
    if ( v10 >= 0 )
    {
      v13 = v20 & 1;
    }
    else
    {
      wil::details::in1diag3::_Log_NtStatus(retaddr, v11, v12, (const char *)(unsigned int)v10, v19);
      v13 = 0;
    }
    *(_BYTE *)(a1 + 525) = v13;
    FirewallUxTelemetry::OverrideShouldConfigureForUAC<bool &>((char *)(a1 + 525));
  }
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v25,
    (__int64)v24,
    0);
  v25[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  FirewallUxTelemetry::DialogInitialize::operator=(a1 + 96, v25);
  v25[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v25);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(
    (winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *)a1,
    1);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v23[0] = 0;
  v20 = a1;
  v14 = operator new(8u);
  v20 = 0;
  *v14 = a1;
  v21._Hnd = v14;
  v19 = 0;
  v22._Hnd = (void *)_o__beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke_std::tuple__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog_::_2_::_lambda_1____0_,
                       v14);
  if ( !v22._Hnd )
  {
LABEL_25:
    v22._Id = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_26;
  }
  if ( !v22._Id || (v21 = v22, _Thrd_detach(&v21)) )
  {
    std::_Throw_Cpp_error(1);
    goto LABEL_25;
  }
  v22 = 0;
  v24[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v24);
  result = wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v24);
  v16 = *a3;
  if ( *a3 )
  {
    v17 = _InterlockedDecrement(v16 + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v16);
    }
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001fd60  push    rbp
0x18001fd62  push    rbx
0x18001fd63  push    rsi
0x18001fd64  push    rdi
0x18001fd65  push    r12
0x18001fd67  push    r14
0x18001fd69  push    r15
0x18001fd6b  lea     rbp, [rsp-230h]
0x18001fd73  sub     rsp, 330h
0x18001fd7a  mov     rax, cs:__security_cookie
0x18001fd81  xor     rax, rsp
0x18001fd84  mov     [rbp+260h+var_40], rax
0x18001fd8b  mov     rbx, r8
0x18001fd8e  mov     r14, rdx
0x18001fd91  mov     rdi, rcx
0x18001fd94  mov     [rsp+360h+var_2F0], rbx
0x18001fd99  xor     r15d, r15d
0x18001fd9c  call    ?WaitForDebuggerPresent@wil@@YAX_N@Z; wil::WaitForDebuggerPresent(bool)
0x18001fda1  mov     rcx, [rbx]
0x18001fda4  test    rcx, rcx
0x18001fda7  setz    al
0x18001fdaa  mov     r10, [rbp+268h]
0x18001fdb1  test    al, al
0x18001fdb3  jnz     loc_18002004A
0x18001fdb9  mov     rax, [rbp+268h]
0x18001fdc0  cmp     [r14], r15d
0x18001fdc3  jz      loc_180020065
0x18001fdc9  mov     rax, [rbp+268h]
0x18001fdd0  test    byte ptr [r14], 7
0x18001fdd4  jz      loc_18002002F
0x18001fdda  test    rcx, rcx
0x18001fddd  jz      short loc_18001FDE5
0x18001fddf  mov     rcx, [rcx+10h]
0x18001fde3  jmp     short loc_18001FDEC
0x18001fde5  lea     rcx, szFile
0x18001fdec  mov     [rsp+360h+var_320._Hnd], rcx
0x18001fdf1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001fdf5  mov     rax, rsi
0x18001fdf8  inc     rax
0x18001fdfb  cmp     [rcx+rax*2], r15w
0x18001fe00  jnz     short loc_18001FDF8
0x18001fe02  mov     qword ptr [rsp+360h+var_320._Id], rax
0x18001fe07  lea     rdx, [rsp+360h+var_320]
0x18001fe0c  lea     rcx, [rsp+360h+var_300]
0x18001fe11  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x18001fe16  lea     rdx, [rsp+360h+var_300]
0x18001fe1b  mov     rcx, r14
0x18001fe1e  call    ?NotificationDialogParameters@FirewallUxTelemetry@@SAXAEBUFirewallNotificationProperties@Firewall@NetworkUX@Internal@Windows@winrt@@AEBV?$basic_zstring_view@G@wil@@@Z; FirewallUxTelemetry::NotificationDialogParameters(winrt::Windows::Internal::NetworkUX::Firewall::FirewallNotificationProperties const &,wil::basic_zstring_view<ushort> const &)
0x18001fe23  call    cs:__imp_CoAddRefServerProcess
0x18001fe29  nop
0x18001fe2a  lea     rdx, aDialoginitiali; "DialogInitialize"
0x18001fe31  lea     rcx, [rbp+260h+var_2E0]
0x18001fe35  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fe3a  lea     r12, ??_7DialogInitialize@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::DialogInitialize::`vftable'
0x18001fe41  mov     [rbp+260h+var_2E0], r12
0x18001fe45  lea     rdx, aNotification_0; "Notification"
0x18001fe4c  lea     rcx, [rbp+260h+var_2E0]; this
0x18001fe50  call    ?StartActivity@DialogInitialize@FirewallUxTelemetry@@QEAAXPEBG@Z; FirewallUxTelemetry::DialogInitialize::StartActivity(ushort const *)
0x18001fe55  nop
0x18001fe56  lea     rcx, [rdi+18h]
0x18001fe5a  mov     rdx, rbx
0x18001fe5d  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18001fe62  mov     [rdi+50h], r15d
0x18001fe66  movups  xmm0, xmmword ptr [r14]
0x18001fe6a  movups  xmmword ptr [rdi+1F8h], xmm0
0x18001fe71  movsd   xmm1, qword ptr [r14+10h]
0x18001fe77  movsd   qword ptr [rdi+208h], xmm1
0x18001fe7f  lea     r14, [rdi+20Dh]
0x18001fe86  cmp     [r14], r15b
0x18001fe89  jnz     short loc_18001FEC4
0x18001fe8b  mov     dword ptr [rsp+360h+var_330], r15d
0x18001fe90  lea     rcx, [rsp+360h+var_330]
0x18001fe95  call    cs:__imp_RtlQueryElevationFlags
0x18001fe9b  mov     rcx, [rbp+268h]; this
0x18001fea2  test    eax, eax
0x18001fea4  jns     short loc_18001FEB3
0x18001fea6  mov     r9d, eax; char *
0x18001fea9  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001feae  mov     al, r15b
0x18001feb1  jmp     short loc_18001FEB9
0x18001feb3  mov     al, byte ptr [rsp+360h+var_330]
0x18001feb7  and     al, 1
0x18001feb9  mov     [r14], al
0x18001febc  mov     rcx, r14
0x18001febf  call    ??$OverrideShouldConfigureForUAC@AEA_N@FirewallUxTelemetry@@SAXAEA_N@Z; FirewallUxTelemetry::OverrideShouldConfigureForUAC<bool &>(bool &)
0x18001fec4  xor     r8d, r8d
0x18001fec7  lea     rdx, [rbp+260h+var_2E0]
0x18001fecb  lea     rcx, [rbp+260h+var_190]
0x18001fed2  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18001fed7  mov     [rbp+260h+var_190], r12
0x18001fede  lea     rcx, [rdi+60h]
0x18001fee2  lea     rdx, [rbp+260h+var_190]
0x18001fee9  call    ??4DialogInitialize@FirewallUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; FirewallUxTelemetry::DialogInitialize::operator=(FirewallUxTelemetry::DialogInitialize &&)
0x18001feee  mov     [rbp+260h+var_190], r12
0x18001fef5  lea     rcx, [rbp+260h+var_190]
0x18001fefc  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ff01  lea     rcx, [rbp+260h+var_190]
0x18001ff08  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ff0d  mov     dl, 1; bool
0x18001ff0f  mov     rcx, rdi; this
0x18001ff12  call    ?CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)
0x18001ff17  mov     rax, [rdi]
0x18001ff1a  mov     rcx, rdi
0x18001ff1d  mov     rax, [rax+8]
0x18001ff21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff26  nop
0x18001ff27  mov     [rsp+360h+var_300], r15
0x18001ff2c  mov     [rsp+360h+var_330], rdi
0x18001ff31  mov     ecx, 8; Size
0x18001ff36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ff3b  mov     [rsp+360h+var_330], r15
0x18001ff40  mov     [rax], rdi
0x18001ff43  mov     [rsp+360h+var_320._Hnd], rax
0x18001ff48  lea     rcx, [rsp+360h+var_310+8]
0x18001ff4d  mov     [rsp+360h+var_338], rcx
0x18001ff52  mov     [rsp+360h+var_340], r15d; int
0x18001ff57  mov     r9, rax
0x18001ff5a  lea     r8, std__thread___Invoke_std__tuple__winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallNotificationDialog__ShowDialog____2____lambda_1____0_
0x18001ff61  xor     edx, edx
0x18001ff63  xor     ecx, ecx
0x18001ff65  call    cs:__imp__o__beginthreadex
0x18001ff6b  mov     qword ptr [rsp+360h+var_310], rax
0x18001ff70  test    rax, rax
0x18001ff73  jz      loc_18002001E
0x18001ff79  cmp     dword ptr [rsp+360h+var_310+8], r15d
0x18001ff7e  jz      loc_180020012
0x18001ff84  movaps  xmm0, [rsp+360h+var_310]
0x18001ff89  movdqa  xmmword ptr [rsp+360h+var_320._Hnd], xmm0
0x18001ff8f  lea     rcx, [rsp+360h+var_320]; _Thrd_t
0x18001ff94  call    cs:__imp__Thrd_detach
0x18001ff9a  test    eax, eax
0x18001ff9c  jnz     short loc_180020012
0x18001ff9e  xorps   xmm0, xmm0
0x18001ffa1  movdqa  [rsp+360h+var_310], xmm0
0x18001ffa7  mov     [rbp+260h+var_2E0], r12
0x18001ffab  lea     rcx, [rbp+260h+var_2E0]
0x18001ffaf  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ffb4  lea     rcx, [rbp+260h+var_2E0]
0x18001ffb8  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ffbd  nop
0x18001ffbe  mov     rdi, [rbx]
0x18001ffc1  test    rdi, rdi
0x18001ffc4  jz      short loc_18001FFE6
0x18001ffc6  lock xadd [rdi+18h], esi
0x18001ffcb  sub     esi, 1
0x18001ffce  jnz     short loc_180020007
0x18001ffd0  nop
0x18001ffd1  call    WINRT_IMPL_GetProcessHeap
0x18001ffd6  mov     rcx, rax; hHeap
0x18001ffd9  mov     r8, rdi; lpMem
0x18001ffdc  xor     edx, edx; dwFlags
0x18001ffde  call    WINRT_IMPL_HeapFree
0x18001ffe3  mov     [rbx], r15
0x18001ffe6  mov     rcx, [rbp+260h+var_40]
0x18001ffed  xor     rcx, rsp; StackCookie
0x18001fff0  call    __security_check_cookie
0x18001fff5  add     rsp, 330h
0x18001fffc  pop     r15
0x18001fffe  pop     r14
0x180020000  pop     r12
0x180020002  pop     rdi
0x180020003  pop     rsi
0x180020004  pop     rbx
0x180020005  pop     rbp
0x180020006  retn
0x180020007  test    esi, esi
0x180020009  jns     short loc_18001FFE3
0x18002000b  call    cs:__imp_abort
0x180020012  mov     ecx, 1
0x180020017  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002001d  nop
0x18002001e  mov     dword ptr [rsp+360h+var_310+8], r15d
0x180020023  mov     ecx, 6
0x180020028  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002002e  nop
0x18002002f  mov     r9d, 80070057h; char *
0x180020035  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x18002003c  mov     edx, 3Dh ; '='; void *
0x180020041  mov     rcx, rax; this
0x180020044  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002004a  mov     r9d, 80070057h; char *
0x180020050  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x180020057  mov     edx, 39h ; '9'; void *
0x18002005c  mov     rcx, r10; this
0x18002005f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020065  mov     r9d, 80070057h; char *
0x18002006b  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x180020072  mov     edx, 3Ah ; ':'; void *
0x180020077  mov     rcx, rax; this
0x18002007a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
