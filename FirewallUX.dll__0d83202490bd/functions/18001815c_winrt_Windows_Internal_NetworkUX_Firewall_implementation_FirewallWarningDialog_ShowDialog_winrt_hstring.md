# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::ShowDialog(winrt::hstring)

- ea: `0x18001815c`
- end: `0x180018359`
- name: `?ShowDialog@FirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXUhstring@7@@Z`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180009f40`

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
- `0x18001815c`
- `0x180018360`
- `0x1800184dc`
- `0x180018648`
- `0x180019ec0`
- `0x180028fcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001833a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001833a`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x1800181f9`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x1800181f9`

## string_xrefs

- `0x180018347`: `shellcommon\shell\networkux\firewallux\lib\firewallwarningdialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::ShowDialog(
        wil *a1,
        wchar_t *a2)
{
  wchar_t *v4; // rax
  __int64 v5; // rcx
  wchar_t *v6; // rax
  volatile signed __int32 *v7; // rsi
  int v8; // edi
  HANDLE ProcessHeap; // rax
  wchar_t *v10[3]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[42]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v13[44]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v10[2] = a2;
  wil::WaitForDebuggerPresent(a1, (bool)a2);
  if ( !*(_QWORD *)a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallwarningdialog.cpp",
      (const char *)0x80070057LL,
      (int)v10[0]);
  v4 = *(wchar_t **)(*(_QWORD *)a2 + 16LL);
  v10[0] = v4;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v10[1] = (wchar_t *)v5;
  GetImageNameFromFullPath((__int64)v11, v10);
  FirewallUxTelemetry::WarningDialogParameters(v11);
  CoAddRefServerProcess();
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "DialogInitialize");
  v12[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  FirewallUxTelemetry::DialogInitialize::StartActivity((FirewallUxTelemetry::DialogInitialize *)v12, L"Notification");
  winrt::hstring::operator=((char *)a1 + 24, a2);
  *((_DWORD *)a1 + 20) = 1;
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v13,
    (__int64)v12,
    0);
  v13[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  FirewallUxTelemetry::DialogInitialize::operator=((char *)a1 + 96, v13);
  v13[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v13);
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v13);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(a1, 0);
  v12[0] = &FirewallUxTelemetry::DialogInitialize::`vftable';
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v12);
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v12);
  v6 = (wchar_t *)operator new(0x120u);
  v10[0] = v6;
  *((_QWORD *)v6 + 35) = a1;
  *(_QWORD *)v6 = winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::_ShowDialogInternal__ResumeCoro_1;
  *((_DWORD *)v6 + 2) = 65538;
  *((_BYTE *)v6 + 272) = 0;
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::_ShowDialogInternal__ResumeCoro_1((char *)v6);
  v7 = *(volatile signed __int32 **)a2;
  if ( *(_QWORD *)a2 )
  {
    v8 = _InterlockedDecrement(v7 + 6);
    if ( v8 )
    {
      if ( v8 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v7);
    }
    *(_QWORD *)a2 = 0;
  }
}

```

## disassembly

```asm
0x18001815c  mov     [rsp-8+arg_10], rbx
0x180018161  push    rbp
0x180018162  push    rsi
0x180018163  push    rdi
0x180018164  push    r14
0x180018166  push    r15
0x180018168  lea     rbp, [rsp-210h]
0x180018170  sub     rsp, 310h
0x180018177  mov     rax, cs:__security_cookie
0x18001817e  xor     rax, rsp
0x180018181  mov     [rbp+230h+var_30], rax
0x180018188  mov     rbx, rdx
0x18001818b  mov     rsi, rcx
0x18001818e  mov     [rsp+330h+var_300], rdx
0x180018193  call    ?WaitForDebuggerPresent@wil@@YAX_N@Z; wil::WaitForDebuggerPresent(bool)
0x180018198  mov     rdx, [rbx]
0x18001819b  xor     r15d, r15d
0x18001819e  test    rdx, rdx
0x1800181a1  setz    al
0x1800181a4  mov     rcx, [rbp+238h]; this
0x1800181ab  test    al, al
0x1800181ad  jnz     loc_180018341
0x1800181b3  test    rdx, rdx
0x1800181b6  jz      short loc_1800181BE
0x1800181b8  mov     rax, [rdx+10h]
0x1800181bc  jmp     short loc_1800181C5
0x1800181be  lea     rax, szFile
0x1800181c5  mov     [rsp+330h+var_310], rax
0x1800181ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800181ce  mov     rcx, rdi
0x1800181d1  inc     rcx
0x1800181d4  cmp     [rax+rcx*2], r15w
0x1800181d9  jnz     short loc_1800181D1
0x1800181db  mov     [rsp+330h+var_308], rcx
0x1800181e0  lea     rdx, [rsp+330h+var_310]
0x1800181e5  lea     rcx, [rsp+330h+var_2F8]
0x1800181ea  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x1800181ef  lea     rcx, [rsp+330h+var_2F8]
0x1800181f4  call    ?WarningDialogParameters@FirewallUxTelemetry@@SAXAEBV?$basic_zstring_view@G@wil@@@Z; FirewallUxTelemetry::WarningDialogParameters(wil::basic_zstring_view<ushort> const &)
0x1800181f9  call    cs:__imp_CoAddRefServerProcess
0x1800181ff  nop
0x180018200  lea     rdx, aDialoginitiali; "DialogInitialize"
0x180018207  lea     rcx, [rsp+330h+var_2E0]
0x18001820c  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018211  lea     r14, ??_7DialogInitialize@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::DialogInitialize::`vftable'
0x180018218  mov     [rsp+330h+var_2E0], r14
0x18001821d  lea     rdx, aNotification_0; "Notification"
0x180018224  lea     rcx, [rsp+330h+var_2E0]; this
0x180018229  call    ?StartActivity@DialogInitialize@FirewallUxTelemetry@@QEAAXPEBG@Z; FirewallUxTelemetry::DialogInitialize::StartActivity(ushort const *)
0x18001822e  nop
0x18001822f  lea     rcx, [rsi+18h]
0x180018233  mov     rdx, rbx
0x180018236  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18001823b  mov     dword ptr [rsi+50h], 1
0x180018242  xor     r8d, r8d
0x180018245  lea     rdx, [rsp+330h+var_2E0]
0x18001824a  lea     rcx, [rbp+230h+var_190]
0x180018251  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x180018256  mov     [rbp+230h+var_190], r14
0x18001825d  lea     rcx, [rsi+60h]
0x180018261  lea     rdx, [rbp+230h+var_190]
0x180018268  call    ??4DialogInitialize@FirewallUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; FirewallUxTelemetry::DialogInitialize::operator=(FirewallUxTelemetry::DialogInitialize &&)
0x18001826d  mov     [rbp+230h+var_190], r14
0x180018274  lea     rcx, [rbp+230h+var_190]
0x18001827b  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180018280  lea     rcx, [rbp+230h+var_190]
0x180018287  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001828c  xor     edx, edx; bool
0x18001828e  mov     rcx, rsi; this
0x180018291  call    ?CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)
0x180018296  nop
0x180018297  mov     [rsp+330h+var_2E0], r14
0x18001829c  lea     rcx, [rsp+330h+var_2E0]
0x1800182a1  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800182a6  lea     rcx, [rsp+330h+var_2E0]
0x1800182ab  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800182b0  mov     ecx, 120h; Size
0x1800182b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800182ba  mov     [rsp+330h+var_310], rax
0x1800182bf  mov     [rax+118h], rsi
0x1800182c6  lea     rcx, winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallWarningDialog___ShowDialogInternal$_ResumeCoro$1
0x1800182cd  mov     [rax], rcx
0x1800182d0  mov     dword ptr [rax+8], 10002h
0x1800182d7  xor     ecx, ecx
0x1800182d9  mov     [rax+110h], cl
0x1800182df  mov     rcx, rax; void *
0x1800182e2  call    winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallWarningDialog___ShowDialogInternal$_ResumeCoro$1
0x1800182e7  nop
0x1800182e8  mov     rsi, [rbx]
0x1800182eb  test    rsi, rsi
0x1800182ee  jz      short loc_180018310
0x1800182f0  lock xadd [rsi+18h], edi
0x1800182f5  sub     edi, 1
0x1800182f8  jnz     short loc_180018336
0x1800182fa  nop
0x1800182fb  call    WINRT_IMPL_GetProcessHeap
0x180018300  mov     rcx, rax; hHeap
0x180018303  mov     r8, rsi; lpMem
0x180018306  xor     edx, edx; dwFlags
0x180018308  call    WINRT_IMPL_HeapFree
0x18001830d  mov     [rbx], r15
0x180018310  mov     rcx, [rbp+230h+var_30]
0x180018317  xor     rcx, rsp; StackCookie
0x18001831a  call    __security_check_cookie
0x18001831f  mov     rbx, [rsp+330h+arg_10]
0x180018327  add     rsp, 310h
0x18001832e  pop     r15
0x180018330  pop     r14
0x180018332  pop     rdi
0x180018333  pop     rsi
0x180018334  pop     rbp
0x180018335  retn
0x180018336  test    edi, edi
0x180018338  jns     short loc_18001830D
0x18001833a  call    cs:__imp_abort
0x180018341  mov     r9d, 80070057h; char *
0x180018347  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\networkux\\firewall"...
0x18001834e  mov     edx, 1Eh; void *
0x180018353  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
