# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_ShowDialogInternal$_ResumeCoro$1

- ea: `0x1800229a0`
- end: `0x180022dc0`
- name: `winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_ShowDialogInternal$_ResumeCoro$1`
- size: `1056`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ba40`

## callees

- `0x1800019dc`
- `0x1800025f8`
- `0x180002c10`
- `0x180005030`
- `0x18000514c`
- `0x180005cd8`
- `0x180008820`
- `0x180009fc8`
- `0x18000aa30`
- `0x18000b5d0`
- `0x1800100cc`
- `0x180010430`
- `0x180013488`
- `0x1800148d0`
- `0x1800176e4`
- `0x1800179c8`
- `0x18001bab8`
- `0x1800229a0`
- `0x180022ecc`
- `0x180028f60`
- `0x180028fcc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022d38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022d38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d46`

## string_xrefs

- `0x180022d5e`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`
- `0x180022a53`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`
- `0x180022be0`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_ShowDialogInternal__ResumeCoro_1(
        char *a1)
{
  int v2; // r14d
  __int64 v3; // rbx
  char *v4; // r14
  int v5; // eax
  char *v6; // rcx
  HANDLE v7; // rax
  unsigned int *v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  char *v16; // [rsp+20h] [rbp-E8h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-A8h] BYREF
  const unsigned __int16 *v18; // [rsp+78h] [rbp-90h]
  LPVOID v19; // [rsp+A0h] [rbp-68h]
  char v20; // [rsp+A8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = 1;
  switch ( *((_WORD *)a1 + 4) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_32;
    case 2:
      v3 = *((_QWORD *)a1 + 39);
      v4 = a1 + 16;
      wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
        v3 + 96,
        (__int64)(a1 + 16));
      *(_DWORD *)(v3 + 600) = GetCurrentFwConfig();
      winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_UpdateEffectiveProfiles((winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *)v3);
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v3 + 432) + 376LL))(*(_QWORD *)(v3 + 432), v3);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x67,
          (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
          (const char *)(unsigned int)v5,
          (int)v16);
      *((_QWORD *)a1 + 13) = winrt::impl::consume_Windows_UI_Xaml_IDependencyObject<winrt::Windows::UI::Xaml::Controls::TextBlock>::Dispatcher(
                               v3 + 440,
                               a1 + 96);
      *((_DWORD *)a1 + 28) = 0;
      *((_QWORD *)a1 + 15) = 0;
      a1[128] = 0;
      *((_QWORD *)a1 + 17) = v4;
      *((_QWORD *)a1 + 18) = a1 + 104;
      a1[152] = 0;
      *(_DWORD *)(a1 + 153) = 0;
      *(_WORD *)(a1 + 157) = 0;
      a1[159] = 0;
      *((_QWORD *)a1 + 20) = a1;
      *((_WORD *)a1 + 4) = 4;
      ___await_suspend_U__coroutine_handle_Upromise_type___coroutine_traits_Ufire_and_forget_winrt__PEAUFirewallNotificationDialog_implementation_Firewall_NetworkUX_Internal_Windows_2__experimental_std___experimental_std_____coroutine_withsuspend_awaiter_VActivityThreadWatcher_wil____QEAUawaitable__1____resume_foreground_UCoreDispatcher_Core_UI_Windows_winrt___2_YA_A_PAEBUCoreDispatcher_Core_UI_Windows_winrt__W4CoreDispatcherPriority_5678__Z__coro_details_wil__QEAA_A_P__QEAU__coroutine_handle_Upromise_type___coroutine_traits_Ufire_and_forget_winrt__PEAUFirewallNotificationDialog_implementation_Firewall_NetworkUX_Internal_Windows_2__experimental_std___experimental_std___Z(
        (__int64)(a1 + 136),
        (_QWORD *)a1 + 20);
      return;
    case 4:
      if ( a1[152] )
        wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(*((_QWORD *)a1 + 17) + 32LL));
      if ( *(_BYTE *)(*((_QWORD *)a1 + 18) + 24LL) )
      {
        winrt::impl::slim_source_location::current(a1 + 232);
        v8 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 256), -2147024469);
        winrt::hresult_error::hresult_error(pExceptionObject, *v8);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 96);
      v9 = *((_QWORD *)a1 + 39);
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 432) + 272LL))(*(_QWORD *)(v9 + 432));
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6B,
          (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
          (const char *)(unsigned int)v10,
          (int)v16);
      v11 = FirewallUxTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v11 > 5u )
        tlgWriteTransfer_EventWriteTransfer((__int64)v11, byte_1800330F4, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 264));
      wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        (_QWORD *)(v9 + 96),
        0);
      v12 = *(_QWORD *)(v9 + 24);
      if ( v12 )
        v13 = *(const wchar_t **)(v12 + 16);
      else
        v13 = &szFile;
      *((_QWORD *)a1 + 21) = v13;
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      *((_QWORD *)a1 + 22) = v14;
      GetImageNameFromFullPath((__int64)(a1 + 184), (wchar_t **)a1 + 21);
      *((_DWORD *)a1 + 50) = *(_DWORD *)(v9 + 504);
      *((_DWORD *)a1 + 51) = *(_DWORD *)(v9 + 508);
      *((_DWORD *)a1 + 52) = *(_DWORD *)(v9 + 512);
      *((_DWORD *)a1 + 53) = *(_DWORD *)(v9 + 516);
      *((_DWORD *)a1 + 54) = *(_DWORD *)(v9 + 520);
      a1[220] = *(_BYTE *)(v9 + 524);
      a1[221] = *(_BYTE *)(v9 + 525);
      a1[222] = *(_BYTE *)(v9 + 526);
      a1[223] = *(_BYTE *)(v9 + 527);
      if ( *(_DWORD *)(v9 + 80) )
      {
        if ( *(_DWORD *)(v9 + 80) != 1 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x3B,
            (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
            "Unexpected dialog type",
            v16);
      }
      else
      {
        v2 = 0;
      }
      *((_DWORD *)a1 + 56) = 16;
      *((_DWORD *)a1 + 57) = v2;
      v18 = (const unsigned __int16 *)*((_QWORD *)a1 + 23);
      NetworkingTriageScenario::FirewallUX::DialogVisible(
        (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)(a1 + 224),
        (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)(a1 + 200),
        v18);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 48));
      v20 = a1[40];
      if ( v20 )
      {
        v19 = (LPVOID)*((_QWORD *)a1 + 4);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      goto LABEL_32;
    case 5:
      v6 = a1 + 96;
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v6);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 48));
      v20 = a1[40];
      if ( v20 )
      {
        v19 = (LPVOID)*((_QWORD *)a1 + 4);
        v7 = GetProcessHeap();
        HeapFree(v7, 0, v19);
      }
LABEL_32:
      if ( *((_WORD *)a1 + 5) )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800229a0  mov     rax, rsp
0x1800229a3  mov     [rax+10h], rbx
0x1800229a7  mov     [rax+18h], rsi
0x1800229ab  mov     [rax+8], rcx
0x1800229af  push    rdi
0x1800229b0  push    r14
0x1800229b2  push    r15
0x1800229b4  sub     rsp, 0F0h
0x1800229bb  mov     rdi, rcx
0x1800229be  mov     [rsp+108h+var_C8], rcx
0x1800229c3  movzx   eax, word ptr [rdi+8]
0x1800229c7  mov     [rsp+108h+var_D8], ax
0x1800229cc  mov     r14d, 1
0x1800229d2  add     ax, r14w
0x1800229d6  cmp     ax, 6; switch 7 cases
0x1800229da  ja      def_1800229F5; jumptable 00000001800229F5 default case, cases 1,2
0x1800229e0  movsx   rax, ax
0x1800229e4  lea     rdx, __ImageBase
0x1800229eb  mov     ecx, ds:(jpt_1800229F5 - 180000000h)[rdx+rax*4]
0x1800229f2  add     rcx, rdx
0x1800229f5  jmp     rcx; switch jump
0x1800229f7  xor     esi, esi; jumptable 00000001800229F5 case 4
0x1800229f9  jmp     loc_180022D72
0x1800229fe  mov     rbx, [rdi+138h]; jumptable 00000001800229F5 case 3
0x180022a05  lea     r14, [rdi+10h]
0x180022a09  lea     rcx, [rbx+60h]
0x180022a0d  mov     rdx, r14
0x180022a10  call    ?ContinueOnCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180022a15  nop
0x180022a16  call    ?GetCurrentFwConfig@@YAKXZ; GetCurrentFwConfig(void)
0x180022a1b  mov     [rbx+258h], eax
0x180022a21  mov     rcx, rbx; this
0x180022a24  call    ?_UpdateEffectiveProfiles@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_UpdateEffectiveProfiles(void)
0x180022a29  mov     rcx, [rbx+1B0h]
0x180022a30  mov     rax, [rcx]
0x180022a33  mov     rdx, rbx
0x180022a36  mov     rax, [rax+178h]
0x180022a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a42  mov     rcx, [rsp+108h]; this
0x180022a4a  xor     esi, esi
0x180022a4c  test    eax, eax
0x180022a4e  jns     short loc_180022A62
0x180022a50  mov     r9d, eax; char *
0x180022a53  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x180022a5a  lea     edx, [rsi+67h]; void *
0x180022a5d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022a62  lea     rdx, [rdi+60h]
0x180022a66  lea     rcx, [rbx+1B8h]
0x180022a6d  call    ?Dispatcher@?$consume_Windows_UI_Xaml_IDependencyObject@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_IDependencyObject<winrt::Windows::UI::Xaml::Controls::TextBlock>::Dispatcher(void)
0x180022a72  nop
0x180022a73  lea     rdx, [rdi+68h]
0x180022a77  mov     [rdx], rax
0x180022a7a  mov     [rdi+70h], esi
0x180022a7d  mov     [rdi+78h], rsi
0x180022a81  mov     [rdi+80h], sil
0x180022a88  lea     rcx, [rdi+88h]
0x180022a8f  mov     [rcx], r14
0x180022a92  mov     [rdi+90h], rdx
0x180022a99  mov     [rdi+98h], sil
0x180022aa0  xor     eax, eax
0x180022aa2  mov     [rdi+99h], eax
0x180022aa8  mov     [rdi+9Dh], ax
0x180022aaf  mov     [rdi+9Fh], al
0x180022ab5  lea     rdx, [rdi+0A0h]
0x180022abc  mov     [rdx], rdi
0x180022abf  mov     eax, 4
0x180022ac4  mov     [rdi+8], ax
0x180022ac8  call    ??$await_suspend@U?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@2@@experimental@std@@@experimental@std@@@?$coroutine_withsuspend_awaiter@VActivityThreadWatcher@wil@@$$QEAUawaitable@?1???$resume_foreground@UCoreDispatcher@Core@UI@Windows@winrt@@@2@YA?A_PAEBUCoreDispatcher@Core@UI@Windows@winrt@@W4CoreDispatcherPriority@5678@@Z@@coro@details@wil@@QEAA?A_P$$QEAU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@2@@experimental@std@@@experimental@std@@@Z
0x180022acd  jmp     loc_180022D88
0x180022ad2  lea     rcx, [rdi+60h]; jumptable 00000001800229F5 case 6
0x180022ad6  mov     rax, [rcx]
0x180022ad9  mov     [rsp+108h+var_D0], rax
0x180022ade  xor     esi, esi
0x180022ae0  test    rax, rax
0x180022ae3  jz      short loc_180022AEB
0x180022ae5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180022aea  nop
0x180022aeb  lea     rcx, [rdi+30h]; this
0x180022aef  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180022af4  mov     al, [rdi+28h]
0x180022af7  mov     [rsp+108h+var_60], al
0x180022afe  test    al, al
0x180022b00  jz      short loc_180022B23
0x180022b02  mov     rbx, [rdi+20h]
0x180022b06  mov     [rsp+108h+var_68], rbx
0x180022b0e  call    cs:__imp_GetProcessHeap
0x180022b14  mov     r8, rbx; lpMem
0x180022b17  xor     edx, edx; dwFlags
0x180022b19  mov     rcx, rax; hHeap
0x180022b1c  call    cs:__imp_HeapFree
0x180022b22  nop
0x180022b23  jmp     loc_180022D72
0x180022b28  mov     al, [rdi+98h]; jumptable 00000001800229F5 case 5
0x180022b2e  mov     [rsp+108h+var_B0], al
0x180022b32  xor     esi, esi
0x180022b34  test    al, al
0x180022b36  jz      short loc_180022B4E
0x180022b38  mov     rcx, [rdi+88h]
0x180022b3f  mov     [rsp+108h+var_C0], rcx
0x180022b44  add     rcx, 20h ; ' '; this
0x180022b48  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180022b4d  nop
0x180022b4e  mov     rax, [rdi+90h]
0x180022b55  mov     [rsp+108h+var_B8], rax
0x180022b5a  cmp     [rax+18h], sil
0x180022b5e  jz      short loc_180022B9E
0x180022b60  lea     rcx, [rdi+0E8h]
0x180022b67  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180022b6c  mov     r8, rax
0x180022b6f  lea     rcx, [rdi+100h]; this
0x180022b76  mov     edx, 800701ABh; int
0x180022b7b  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180022b80  mov     edx, [rax]
0x180022b82  lea     rcx, [rsp+108h+pExceptionObject]
0x180022b87  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022b8c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180022b93  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180022b98  call    _CxxThrowException_0
0x180022b9e  lea     rcx, [rdi+60h]
0x180022ba2  mov     rax, [rcx]
0x180022ba5  mov     [rsp+108h+var_D0], rax
0x180022baa  test    rax, rax
0x180022bad  jz      short loc_180022BB4
0x180022baf  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180022bb4  mov     rbx, [rdi+138h]
0x180022bbb  mov     rcx, [rbx+1B0h]
0x180022bc2  mov     rax, [rcx]
0x180022bc5  mov     rax, [rax+110h]
0x180022bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bd1  mov     rcx, [rsp+108h]; this
0x180022bd9  test    eax, eax
0x180022bdb  jns     short loc_180022BF1
0x180022bdd  mov     r9d, eax; char *
0x180022be0  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x180022be7  mov     edx, 6Bh ; 'k'; void *
0x180022bec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022bf1  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180022bf6  mov     ecx, [rax]
0x180022bf8  cmp     ecx, 5
0x180022bfb  jbe     short loc_180022C26
0x180022bfd  lea     rcx, [rdi+108h]
0x180022c04  mov     [rsp+108h+var_E0], rcx
0x180022c09  mov     dword ptr [rsp+108h+var_E8], 2; char *
0x180022c11  xor     r9d, r9d
0x180022c14  xor     r8d, r8d
0x180022c17  lea     rdx, byte_1800330F4
0x180022c1e  mov     rcx, rax
0x180022c21  call    _tlgWriteTransfer_EventWriteTransfer
0x180022c26  lea     rcx, [rbx+60h]
0x180022c2a  xor     edx, edx
0x180022c2c  call    ?Stop@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180022c31  mov     rcx, [rbx+18h]
0x180022c35  test    rcx, rcx
0x180022c38  jz      short loc_180022C40
0x180022c3a  mov     rcx, [rcx+10h]
0x180022c3e  jmp     short loc_180022C47
0x180022c40  lea     rcx, szFile
0x180022c47  lea     rdx, [rdi+0A8h]
0x180022c4e  mov     [rdx], rcx
0x180022c51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022c55  inc     rax
0x180022c58  cmp     [rcx+rax*2], si
0x180022c5c  jnz     short loc_180022C55
0x180022c5e  mov     [rdi+0B0h], rax
0x180022c65  lea     r15, [rdi+0B8h]
0x180022c6c  mov     rcx, r15
0x180022c6f  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x180022c74  lea     rdx, [rdi+0C8h]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x180022c7b  mov     eax, [rbx+1F8h]
0x180022c81  mov     [rdx], eax
0x180022c83  mov     eax, [rbx+1FCh]
0x180022c89  mov     [rdi+0CCh], eax
0x180022c8f  mov     eax, [rbx+200h]
0x180022c95  mov     [rdi+0D0h], eax
0x180022c9b  mov     eax, [rbx+204h]
0x180022ca1  mov     [rdi+0D4h], eax
0x180022ca7  mov     eax, [rbx+208h]
0x180022cad  mov     [rdi+0D8h], eax
0x180022cb3  mov     al, [rbx+20Ch]
0x180022cb9  mov     [rdi+0DCh], al
0x180022cbf  mov     al, [rbx+20Dh]
0x180022cc5  mov     [rdi+0DDh], al
0x180022ccb  mov     al, [rbx+20Eh]
0x180022cd1  mov     [rdi+0DEh], al
0x180022cd7  mov     al, [rbx+20Fh]
0x180022cdd  mov     [rdi+0DFh], al
0x180022ce3  cmp     [rbx+50h], esi
0x180022ce6  jnz     short loc_180022CED
0x180022ce8  mov     r14d, esi
0x180022ceb  jmp     short loc_180022CF3
0x180022ced  cmp     [rbx+50h], r14d
0x180022cf1  jnz     short loc_180022D4F
0x180022cf3  lea     rcx, [rdi+0E0h]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x180022cfa  mov     dword ptr [rcx], 10h
0x180022d00  mov     [rdi+0E4h], r14d
0x180022d07  mov     r8, [r15]; unsigned __int16 *
0x180022d0a  mov     [rsp+108h+var_90], r8
0x180022d0f  call    ?DialogVisible@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogVisible(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x180022d14  nop
0x180022d15  lea     rcx, [rdi+30h]; this
0x180022d19  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180022d1e  mov     al, [rdi+28h]
0x180022d21  mov     [rsp+108h+var_60], al
0x180022d28  test    al, al
0x180022d2a  jz      short loc_180022D4D
0x180022d2c  mov     rbx, [rdi+20h]
0x180022d30  mov     [rsp+108h+var_68], rbx
0x180022d38  call    cs:__imp_GetProcessHeap
0x180022d3e  mov     r8, rbx; lpMem
0x180022d41  xor     edx, edx; dwFlags
0x180022d43  mov     rcx, rax; hHeap
0x180022d46  call    cs:__imp_HeapFree
0x180022d4c  nop
0x180022d4d  jmp     short loc_180022D72
0x180022d4f  mov     rcx, [rsp+108h]; this
0x180022d57  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x180022d5e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x180022d65  mov     edx, 3Bh ; ';'; void *
0x180022d6a  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180022d70  xor     esi, esi; jumptable 00000001800229F5 case 0
0x180022d72  cmp     [rdi+0Ah], si
0x180022d76  jz      short loc_180022D88
0x180022d78  mov     edx, 140h; unsigned __int64
0x180022d7d  mov     rcx, rdi; void *
0x180022d80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d85  jmp     short loc_180022D88
0x180022d87  int     3; Trap to Debugger
0x180022d88  lea     r11, [rsp+108h+var_18]
0x180022d90  mov     rbx, [r11+28h]
0x180022d94  mov     rsi, [r11+30h]
0x180022d98  mov     rsp, r11
0x180022d9b  pop     r15
0x180022d9d  pop     r14
0x180022d9f  pop     rdi
0x180022da0  retn
```
