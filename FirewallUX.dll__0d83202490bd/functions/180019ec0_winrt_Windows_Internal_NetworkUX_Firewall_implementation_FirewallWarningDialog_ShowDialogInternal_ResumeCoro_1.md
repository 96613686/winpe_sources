# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::_ShowDialogInternal$_ResumeCoro$1

- ea: `0x180019ec0`
- end: `0x18001a190`
- name: `winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::_ShowDialogInternal$_ResumeCoro$1`
- size: `720`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001815c`

## callees

- `0x1800019dc`
- `0x1800025f8`
- `0x180002c10`
- `0x180005030`
- `0x18000514c`
- `0x180005cd8`
- `0x180008820`
- `0x18000aa30`
- `0x18000b5d0`
- `0x1800100cc`
- `0x180010430`
- `0x180013488`
- `0x1800148d0`
- `0x1800176e4`
- `0x1800179c8`
- `0x180019ec0`
- `0x18001a4ac`
- `0x180028fcc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a107`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a115`

## string_xrefs

- `0x18001a12d`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`
- `0x18001a018`: `shellcommon\shell\networkux\firewallux\lib\firewallwarningdialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::_ShowDialogInternal__ResumeCoro_1(
        char *a1)
{
  int v2; // ebx
  char *v3; // rcx
  unsigned int *v4; // rax
  char *v5; // rcx
  __int64 v6; // r14
  int v7; // eax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  HANDLE ProcessHeap; // rax
  char *v13; // [rsp+20h] [rbp-E8h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-C0h] BYREF
  const unsigned __int16 *v15; // [rsp+60h] [rbp-A8h]
  LPVOID v17; // [rsp+A0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = 1;
  switch ( *((_WORD *)a1 + 4) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_26;
    case 2:
      *((_QWORD *)a1 + 3) = winrt::impl::consume_Windows_UI_Xaml_IDependencyObject<winrt::Windows::UI::Xaml::Controls::TextBlock>::Dispatcher(
                              *((_QWORD *)a1 + 35) + 440LL,
                              a1 + 16);
      *((_DWORD *)a1 + 8) = 0;
      *((_QWORD *)a1 + 5) = 0;
      a1[48] = 0;
      *((_WORD *)a1 + 4) = 4;
      `wil::resume_foreground<winrt::Windows::UI::Core::CoreDispatcher>'::`2'::awaitable::await_suspend(a1 + 24, a1);
      return;
    case 4:
      if ( a1[48] )
      {
        winrt::impl::slim_source_location::current(a1 + 216);
        v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 208), -2147024469);
        winrt::hresult_error::hresult_error(pExceptionObject, *v4);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      v5 = a1 + 16;
      if ( *((_QWORD *)a1 + 2) )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v5);
      v6 = *((_QWORD *)a1 + 35);
      wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
        v6 + 96,
        (__int64)(a1 + 64));
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 432) + 272LL))(*(_QWORD *)(v6 + 432));
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x34,
          (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallwarningdialog.cpp",
          (const char *)(unsigned int)v7,
          (int)v13);
      v8 = FirewallUxTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v8 > 5u )
        tlgWriteTransfer_EventWriteTransfer((__int64)v8, byte_1800330F4, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)a1 + 15);
      wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        (_QWORD *)(v6 + 96),
        0);
      v9 = *(_QWORD *)(v6 + 24);
      if ( v9 )
        v10 = *(const wchar_t **)(v9 + 16);
      else
        v10 = &szFile;
      *((_QWORD *)a1 + 18) = v10;
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      *((_QWORD *)a1 + 19) = v11;
      GetImageNameFromFullPath((__int64)(a1 + 160), (wchar_t **)a1 + 18);
      if ( *(_DWORD *)(v6 + 80) )
      {
        if ( *(_DWORD *)(v6 + 80) != 1 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x3B,
            (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
            "Unexpected dialog type",
            v13);
      }
      else
      {
        v2 = 0;
      }
      *((_DWORD *)a1 + 50) = 16;
      *((_DWORD *)a1 + 51) = v2;
      v15 = (const unsigned __int16 *)*((_QWORD *)a1 + 20);
      NetworkingTriageScenario::FirewallUX::DialogVisible(
        (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)(a1 + 200),
        (const struct NetworkingTriageScenario::FirewallUX::NotificationFields *)(a1 + 176),
        v15);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 96));
      if ( a1[88] )
      {
        v17 = (LPVOID)*((_QWORD *)a1 + 10);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
      goto LABEL_26;
    case 5:
      v3 = a1 + 16;
      if ( *((_QWORD *)a1 + 2) )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v3);
LABEL_26:
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
0x180019ec0  mov     rax, rsp
0x180019ec3  mov     [rax+10h], rbx
0x180019ec7  mov     [rax+18h], rsi
0x180019ecb  mov     [rax+8], rcx
0x180019ecf  push    rdi
0x180019ed0  push    r14
0x180019ed2  push    r15
0x180019ed4  sub     rsp, 0F0h
0x180019edb  mov     rdi, rcx
0x180019ede  mov     [rsp+108h+var_C8], rcx
0x180019ee3  movzx   eax, word ptr [rdi+8]
0x180019ee7  mov     [rsp+108h+var_D8], ax
0x180019eec  mov     ebx, 1
0x180019ef1  add     ax, bx
0x180019ef4  cmp     ax, 6; switch 7 cases
0x180019ef8  ja      def_180019F13; jumptable 0000000180019F13 default case, cases 1,2
0x180019efe  movsx   rax, ax
0x180019f02  lea     rdx, __ImageBase
0x180019f09  mov     ecx, ds:(jpt_180019F13 - 180000000h)[rdx+rax*4]
0x180019f10  add     rcx, rdx
0x180019f13  jmp     rcx; switch jump
0x180019f15  xor     esi, esi; jumptable 0000000180019F13 case 4
0x180019f17  jmp     loc_18001A141
0x180019f1c  lea     rdx, [rdi+10h]; jumptable 0000000180019F13 case 3
0x180019f20  mov     rcx, [rdi+118h]
0x180019f27  add     rcx, 1B8h
0x180019f2e  call    ?Dispatcher@?$consume_Windows_UI_Xaml_IDependencyObject@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_IDependencyObject<winrt::Windows::UI::Xaml::Controls::TextBlock>::Dispatcher(void)
0x180019f33  nop
0x180019f34  lea     rcx, [rdi+18h]
0x180019f38  mov     [rcx], rax
0x180019f3b  xor     esi, esi
0x180019f3d  mov     [rdi+20h], esi
0x180019f40  mov     [rdi+28h], rsi
0x180019f44  mov     [rdi+30h], sil
0x180019f48  lea     eax, [rsi+4]
0x180019f4b  mov     [rdi+8], ax
0x180019f4f  mov     rdx, rdi
0x180019f52  call    ?await_suspend@awaitable@?1???$resume_foreground@UCoreDispatcher@Core@UI@Windows@winrt@@@wil@@YA?A_PAEBUCoreDispatcher@Core@UI@Windows@winrt@@W4CoreDispatcherPriority@4567@@Z@QEAAXU?$coroutine_handle@X@experimental@std@@@Z
0x180019f57  jmp     loc_18001A157
0x180019f5c  lea     rcx, [rdi+10h]; jumptable 0000000180019F13 case 6
0x180019f60  mov     rax, [rcx]
0x180019f63  mov     [rsp+108h+var_D0], rax
0x180019f68  xor     esi, esi
0x180019f6a  test    rax, rax
0x180019f6d  jz      short loc_180019F75
0x180019f6f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180019f74  nop
0x180019f75  jmp     loc_18001A141
0x180019f7a  mov     al, [rdi+30h]; jumptable 0000000180019F13 case 5
0x180019f7d  mov     [rsp+108h+var_80], al
0x180019f84  xor     esi, esi
0x180019f86  test    al, al
0x180019f88  jz      short loc_180019FC8
0x180019f8a  lea     rcx, [rdi+0D8h]
0x180019f91  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180019f96  mov     r8, rax
0x180019f99  lea     rcx, [rdi+0D0h]; this
0x180019fa0  mov     edx, 800701ABh; int
0x180019fa5  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180019faa  mov     edx, [rax]
0x180019fac  lea     rcx, [rsp+108h+pExceptionObject]
0x180019fb1  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x180019fb6  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180019fbd  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180019fc2  call    _CxxThrowException_0
0x180019fc8  lea     rcx, [rdi+10h]
0x180019fcc  mov     rax, [rcx]
0x180019fcf  mov     [rsp+108h+var_D0], rax
0x180019fd4  test    rax, rax
0x180019fd7  jz      short loc_180019FDE
0x180019fd9  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180019fde  mov     r14, [rdi+118h]
0x180019fe5  lea     rdx, [rdi+40h]
0x180019fe9  lea     rcx, [r14+60h]
0x180019fed  call    ?ContinueOnCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180019ff2  nop
0x180019ff3  mov     rcx, [r14+1B0h]
0x180019ffa  mov     rax, [rcx]
0x180019ffd  mov     rax, [rax+110h]
0x18001a004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a009  mov     rcx, [rsp+108h]; this
0x18001a011  test    eax, eax
0x18001a013  jns     short loc_18001A029
0x18001a015  mov     r9d, eax; char *
0x18001a018  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\networkux\\firewall"...
0x18001a01f  mov     edx, 34h ; '4'; void *
0x18001a024  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001a029  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18001a02e  mov     ecx, [rax]
0x18001a030  cmp     ecx, 5
0x18001a033  jbe     short loc_18001A05E
0x18001a035  lea     rdx, [rdi+0F0h]
0x18001a03c  mov     [rsp+108h+var_E0], rdx
0x18001a041  mov     dword ptr [rsp+108h+var_E8], 2; char *
0x18001a049  xor     r9d, r9d
0x18001a04c  xor     r8d, r8d
0x18001a04f  lea     rdx, byte_1800330F4
0x18001a056  mov     rcx, rax
0x18001a059  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a05e  xor     edx, edx
0x18001a060  lea     rcx, [r14+60h]
0x18001a064  call    ?Stop@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001a069  mov     rcx, [r14+18h]
0x18001a06d  test    rcx, rcx
0x18001a070  jz      short loc_18001A078
0x18001a072  mov     rcx, [rcx+10h]
0x18001a076  jmp     short loc_18001A07F
0x18001a078  lea     rcx, szFile
0x18001a07f  lea     rdx, [rdi+90h]
0x18001a086  mov     [rdx], rcx
0x18001a089  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a08d  inc     rax
0x18001a090  cmp     [rcx+rax*2], si
0x18001a094  jnz     short loc_18001A08D
0x18001a096  mov     [rdi+98h], rax
0x18001a09d  lea     r15, [rdi+0A0h]
0x18001a0a4  mov     rcx, r15
0x18001a0a7  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x18001a0ac  cmp     [r14+50h], esi
0x18001a0b0  jnz     short loc_18001A0B6
0x18001a0b2  mov     ebx, esi
0x18001a0b4  jmp     short loc_18001A0BC
0x18001a0b6  cmp     [r14+50h], ebx
0x18001a0ba  jnz     short loc_18001A11E
0x18001a0bc  lea     rcx, [rdi+0C8h]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18001a0c3  mov     dword ptr [rcx], 10h
0x18001a0c9  mov     [rdi+0CCh], ebx
0x18001a0cf  mov     r8, [r15]; unsigned __int16 *
0x18001a0d2  mov     [rsp+108h+var_A8], r8
0x18001a0d7  lea     rdx, [rdi+0B0h]; struct NetworkingTriageScenario::FirewallUX::NotificationFields *
0x18001a0de  call    ?DialogVisible@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@AEBUNotificationFields@12@PEBG@Z; NetworkingTriageScenario::FirewallUX::DialogVisible(NetworkingTriageScenario::FirewallUX::RequiredFields const &,NetworkingTriageScenario::FirewallUX::NotificationFields const &,ushort const *)
0x18001a0e3  nop
0x18001a0e4  lea     rcx, [rdi+60h]; this
0x18001a0e8  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001a0ed  mov     al, [rdi+58h]
0x18001a0f0  mov     [rsp+108h+var_60], al
0x18001a0f7  test    al, al
0x18001a0f9  jz      short loc_18001A11C
0x18001a0fb  mov     rbx, [rdi+50h]
0x18001a0ff  mov     [rsp+108h+var_68], rbx
0x18001a107  call    cs:__imp_GetProcessHeap
0x18001a10d  mov     r8, rbx; lpMem
0x18001a110  xor     edx, edx; dwFlags
0x18001a112  mov     rcx, rax; hHeap
0x18001a115  call    cs:__imp_HeapFree
0x18001a11b  nop
0x18001a11c  jmp     short loc_18001A141
0x18001a11e  mov     rcx, [rsp+108h]; this
0x18001a126  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x18001a12d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001a134  mov     edx, 3Bh ; ';'; void *
0x18001a139  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x18001a13f  xor     esi, esi; jumptable 0000000180019F13 case 0
0x18001a141  cmp     [rdi+0Ah], si
0x18001a145  jz      short loc_18001A157
0x18001a147  mov     edx, 120h; unsigned __int64
0x18001a14c  mov     rcx, rdi; void *
0x18001a14f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a154  jmp     short loc_18001A157
0x18001a156  int     3; Trap to Debugger
0x18001a157  lea     r11, [rsp+108h+var_18]
0x18001a15f  mov     rbx, [r11+28h]
0x18001a163  mov     rsi, [r11+30h]
0x18001a167  mov     rsp, r11
0x18001a16a  pop     r15
0x18001a16c  pop     r14
0x18001a16e  pop     rdi
0x18001a16f  retn
```
