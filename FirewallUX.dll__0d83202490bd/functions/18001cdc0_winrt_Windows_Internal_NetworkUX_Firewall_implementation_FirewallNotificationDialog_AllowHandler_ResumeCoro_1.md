# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::AllowHandler$_ResumeCoro$1

- ea: `0x18001cdc0`
- end: `0x18001d560`
- name: `winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::AllowHandler$_ResumeCoro$1`
- size: `1952`
- prototype: `void __fastcall(char *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023310`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x1800025f8`
- `0x180003e69`
- `0x180003e75`
- `0x180004c90`
- `0x1800056ec`
- `0x180006b20`
- `0x180008820`
- `0x180009fc8`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000f3b0`
- `0x180010430`
- `0x180013488`
- `0x18001ab70`
- `0x18001baf4`
- `0x18001cdc0`
- `0x18001f178`
- `0x18001f27c`
- `0x180020088`
- `0x180022fd0`
- `0x180026784`
- `0x180028a94`
- `0x180028fcc`
- `0x180029734`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d158`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d472`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d158`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d472`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cec0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cec0`

## string_xrefs

- `0x18001d4df`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`
- `0x18001d336`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::AllowHandler__ResumeCoro_1(
        char *a1)
{
  __int64 v2; // r12
  int v3; // eax
  int v4; // eax
  __int64 v5; // rdx
  bool v6; // zf
  __int64 v7; // rcx
  int v8; // r13d
  __int64 v9; // rcx
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // edi
  unsigned int v13; // r13d
  const unsigned __int16 *v14; // rsi
  __int64 v15; // rdx
  __int64 *v16; // rbx
  __int64 *v17; // rsi
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  const struct _tlgProvider_t *v22; // rax
  unsigned int v23; // edi
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  unsigned int v25; // ebx
  const struct _tlgProvider_t *v26; // rax
  struct _RTL_CRITICAL_SECTION *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rsi
  int v30; // eax
  __int64 v31; // rdx
  __int64 *v32; // rbx
  __int64 *v33; // rsi
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  struct _RTL_CRITICAL_SECTION *v38; // rcx
  __int64 v39; // rcx
  char *v40; // [rsp+20h] [rbp-D8h]
  unsigned int v41; // [rsp+40h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    if ( (unsigned __int16)(*((_WORD *)a1 + 4) + 1) > 8u )
    {
LABEL_81:
      __debugbreak();
    }
    else
    {
      switch ( *((_WORD *)a1 + 4) )
      {
        case 0xFFFF:
        case 3:
          goto LABEL_79;
        case 0:
        case 1:
          goto LABEL_81;
        case 2:
          v2 = *((_QWORD *)a1 + 95);
          *((_QWORD *)a1 + 2) = 0;
          if ( v2 )
          {
            *((_QWORD *)a1 + 2) = v2;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
          }
          *((_QWORD *)a1 + 66) = 0;
          WINRT_IMPL_CoGetObjectContext(&winrt::impl::guid_v<winrt::impl::IContextCallback>, (LPVOID *)a1 + 66);
          *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 66);
          *((_DWORD *)a1 + 134) = 0;
          *((_DWORD *)a1 + 135) = 0;
          if ( WINRT_IMPL_CoGetApartmentType((APTTYPE *)a1 + 134, (APTTYPEQUALIFIER *)a1 + 135) )
            v3 = 1;
          else
            v3 = *((_DWORD *)a1 + 134);
          *((_DWORD *)a1 + 8) = v3;
          EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 552));
          *((_QWORD *)a1 + 5) = v2 + 552;
          v4 = 0;
          if ( *(_BYTE *)(v2 + 592) && (*(_DWORD *)(v2 + 504) & 4) != 0 )
            v4 = 4;
          if ( *(_BYTE *)(v2 + 593) && (*(_DWORD *)(v2 + 504) & 2) != 0 )
            v4 |= 2u;
          if ( *(_BYTE *)(v2 + 594) && (*(_DWORD *)(v2 + 504) & 1) != 0 )
            v4 |= 1u;
          v5 = (unsigned int)(*(_DWORD *)(v2 + 508) | *(_DWORD *)(v2 + 512));
          v6 = (v4 & ~(*(_DWORD *)(v2 + 508) | *(_DWORD *)(v2 + 512))) == 0;
          v7 = v4 & (unsigned int)~(*(_DWORD *)(v2 + 508) | *(_DWORD *)(v2 + 512));
          v41 = v7;
          *((_DWORD *)a1 + 12) = v7;
          if ( v6 )
          {
            *((_DWORD *)a1 + 13) = 0;
            v23 = 0;
            MicrosoftTelemetryAssertTriggeredNoArgs(v7, v5);
LABEL_58:
            *((_DWORD *)a1 + 122) = *((_DWORD *)a1 + 12);
            *((_DWORD *)a1 + 123) = *((_DWORD *)a1 + 13);
            v29 = *((_QWORD *)a1 + 95);
            if ( *(_DWORD *)(v29 + 80) )
            {
              if ( *(_DWORD *)(v29 + 80) != 1 )
                wil::details::in1diag3::FailFast_UnexpectedMsg(
                  retaddr,
                  (void *)0x3B,
                  (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
                  "Unexpected dialog type",
                  v40);
              v30 = 1;
            }
            else
            {
              v30 = 0;
            }
            *((_DWORD *)a1 + 124) = 16;
            *((_DWORD *)a1 + 125) = v30;
            NetworkingTriageScenario::FirewallUX::NotificationDialogAllowed(
              (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)(a1 + 496),
              (const struct NetworkingTriageScenario::FirewallUX::UnblockFields *)(a1 + 488),
              v23);
            a1[504] = v23 == -2147023673;
            FirewallUxTelemetry::AsyncRuleUpdateComplete<bool const &>(a1 + 504);
            if ( v23 != -2147023673 )
            {
              v39 = winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::operator->(v29 + 432);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 296LL))(v39);
              ExitComServerProcess();
            }
            v32 = *(__int64 **)(v29 + 472);
            v33 = *(__int64 **)(v29 + 480);
            while ( v32 != v33 )
            {
              v34 = *v32;
              *((_DWORD *)a1 + 174) = 0;
              *((_QWORD *)a1 + 88) = 0;
              *((_QWORD *)a1 + 89) = 0;
              LOBYTE(v31) = 1;
              v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 184LL))(v34, v31);
              if ( v35 < 0 )
                winrt::throw_hresult((unsigned int)v35, a1 + 696);
              ++v32;
            }
            v36 = *(_QWORD *)(*((_QWORD *)a1 + 95) + 496LL);
            *((_DWORD *)a1 + 180) = 0;
            *((_QWORD *)a1 + 91) = 0;
            *((_QWORD *)a1 + 92) = 0;
            v37 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 56LL))(v36, 0);
            if ( v37 < 0 )
              winrt::throw_hresult((unsigned int)v37, a1 + 720);
            v38 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 5);
            if ( v38 )
              LeaveCriticalSection(v38);
            if ( *((_QWORD *)a1 + 3) )
              winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 24);
            if ( *((_QWORD *)a1 + 2) )
              winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 16);
LABEL_79:
            if ( *((_WORD *)a1 + 5) )
              operator delete(a1);
          }
          else
          {
            v8 = *(_DWORD *)(v2 + 504) & ~(v5 | v7);
            *((_DWORD *)a1 + 136) = v8;
            v9 = *(_QWORD *)(v2 + 24);
            if ( v9 )
              v10 = *(const wchar_t **)(v9 + 16);
            else
              v10 = &szFile;
            *((_QWORD *)a1 + 7) = v10;
            v11 = -1;
            do
              ++v11;
            while ( v10[v11] );
            *((_QWORD *)a1 + 8) = v11;
            GetImageNameFromFullPath((__int64)(a1 + 72), (wchar_t **)a1 + 7);
            v12 = *(_DWORD *)(v2 + 520);
            v13 = *(_DWORD *)(v2 + 604) | v8;
            v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 9);
            wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
              a1 + 96,
              "AllowApplication");
            *((_QWORD *)a1 + 12) = &FirewallUxTelemetry::AllowApplication::`vftable';
            FirewallUxTelemetry::AllowApplication::StartActivity(
              (FirewallUxTelemetry::AllowApplication *)(a1 + 96),
              *(HWND *)(v2 + 88),
              v14,
              v41,
              v13,
              *(_BYTE *)(v2 + 526),
              v12);
            v16 = *(__int64 **)(v2 + 472);
            v17 = *(__int64 **)(v2 + 480);
            while ( v16 != v17 )
            {
              v18 = *v16;
              *((_DWORD *)a1 + 140) = 0;
              *((_QWORD *)a1 + 71) = 0;
              *((_QWORD *)a1 + 72) = 0;
              v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 184LL))(v18, 0);
              if ( v19 < 0 )
                winrt::throw_hresult((unsigned int)v19, a1 + 560);
              ++v16;
            }
            v20 = *(_QWORD *)(*((_QWORD *)a1 + 95) + 496LL);
            *((_DWORD *)a1 + 146) = 0;
            *((_QWORD *)a1 + 74) = 0;
            *((_QWORD *)a1 + 75) = 0;
            LOBYTE(v15) = 1;
            v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 56LL))(v20, v15);
            if ( v21 < 0 )
              winrt::throw_hresult((unsigned int)v21, a1 + 584);
            v22 = FirewallUxTraceLoggingProvider::Provider();
            if ( *(_DWORD *)v22 > 5u )
              tlgWriteTransfer_EventWriteTransfer(
                (__int64)v22,
                byte_1800335A1,
                0,
                0,
                2u,
                (PEVENT_DATA_DESCRIPTOR)a1 + 38);
            a1[432] = 0;
            *((_QWORD *)a1 + 55) = a1 + 96;
            *((_QWORD *)a1 + 56) = a1 + 432;
            a1[456] = 0;
            *(_DWORD *)(a1 + 457) = 0;
            *(_WORD *)(a1 + 461) = 0;
            a1[463] = 0;
            *((_QWORD *)a1 + 58) = a1;
            *((_WORD *)a1 + 4) = 4;
            ___await_suspend_U__coroutine_handle_Upromise_type___coroutine_traits_Ufire_and_forget_winrt__PEAUFirewallNotificationDialog_implementation_Firewall_NetworkUX_Internal_Windows_2_PEAUIPopupWindow__PEAUIPopupCommand___experimental_std___experimental_std_____coroutine_withsuspend_awaiter_VAllowApplication_FirewallUxTelemetry____QEAUawaitable__1__resume_background_winrt__YA_XZ__coro_details_wil__QEAA_A_P__QEAU__coroutine_handle_Upromise_type___coroutine_traits_Ufire_and_forget_winrt__PEAUFirewallNotificationDialog_implementation_Firewall_NetworkUX_Internal_Windows_2_PEAUIPopupWindow__PEAUIPopupCommand___experimental_std___experimental_std___Z(
              a1 + 440,
              (PVOID *)a1 + 58);
          }
          break;
        case 4:
          v25 = *((_DWORD *)a1 + 136);
          *((_DWORD *)a1 + 13) = v25;
          if ( a1[456] )
            wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(*((_QWORD *)a1 + 55) + 288LL));
          v26 = FirewallUxTraceLoggingProvider::Provider();
          if ( *(_DWORD *)v26 > 5u )
            tlgWriteTransfer_EventWriteTransfer((__int64)v26, byte_18003357E, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)a1 + 40);
          *((_DWORD *)a1 + 128) = AllowApplication(
                                    *(_QWORD *)(*((_QWORD *)a1 + 95) + 88LL),
                                    *((_QWORD *)a1 + 95) + 24LL,
                                    *((_DWORD *)a1 + 12),
                                    *(_DWORD *)(*((_QWORD *)a1 + 95) + 604LL) | v25,
                                    *(_BYTE *)(*((_QWORD *)a1 + 95) + 526LL),
                                    *(_DWORD *)(*((_QWORD *)a1 + 95) + 520LL));
          *((_QWORD *)a1 + 59) = a1 + 24;
          *((_QWORD *)a1 + 60) = 0;
          *((_WORD *)a1 + 4) = 6;
          if ( (unsigned __int8)winrt::impl::apartment_awaiter::await_suspend(a1 + 472, a1) )
            return;
          goto LABEL_55;
        case 5:
          *((_QWORD *)a1 + 12) = &FirewallUxTelemetry::AllowApplication::`vftable';
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy((_QWORD *)a1 + 12);
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)(a1 + 96));
          v24 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 5);
          if ( v24 )
            LeaveCriticalSection(v24);
          if ( *((_QWORD *)a1 + 3) )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 24);
          if ( *((_QWORD *)a1 + 2) )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 16);
          goto LABEL_79;
        case 6:
LABEL_55:
          *((_DWORD *)a1 + 168) = 0;
          *((_QWORD *)a1 + 85) = 0;
          *((_QWORD *)a1 + 86) = 0;
          v28 = *((unsigned int *)a1 + 120);
          if ( (int)v28 < 0 )
            winrt::throw_hresult(v28, a1 + 672);
          v23 = *((_DWORD *)a1 + 128);
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
            (_QWORD *)a1 + 12,
            v23);
          wil::details::in1diag3::Log_IfFailedWithExpected(
            retaddr,
            (void *)0x2AB,
            (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
            (const char *)v23,
            1,
            199);
          *((_QWORD *)a1 + 12) = &FirewallUxTelemetry::AllowApplication::`vftable';
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy((_QWORD *)a1 + 12);
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)(a1 + 96));
          goto LABEL_58;
        case 7:
          *((_QWORD *)a1 + 12) = &FirewallUxTelemetry::AllowApplication::`vftable';
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy((_QWORD *)a1 + 12);
          wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)(a1 + 96));
          v27 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 5);
          if ( v27 )
            LeaveCriticalSection(v27);
          if ( *((_QWORD *)a1 + 3) )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 24);
          if ( *((_QWORD *)a1 + 2) )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 16);
          goto LABEL_79;
      }
    }
  }
  catch ( ... )
  {
    *((_WORD *)a1 + 4) = -1;
    std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *>::promise_type::unhandled_exception();
  }
}

```

## disassembly

```asm
0x18001cdc0  mov     r11, rsp
0x18001cdc3  mov     [r11+10h], rbx
0x18001cdc7  mov     [r11+18h], rsi
0x18001cdcb  mov     [r11+8], rcx
0x18001cdcf  push    rdi
0x18001cdd0  push    r12
0x18001cdd2  push    r13
0x18001cdd4  push    r14
0x18001cdd6  push    r15
0x18001cdd8  sub     rsp, 0D0h
0x18001cddf  mov     rax, cs:__security_cookie
0x18001cde6  xor     rax, rsp
0x18001cde9  mov     [rsp+0F8h+var_38], rax
0x18001cdf1  mov     r14, rcx
0x18001cdf4  mov     [rsp+0F8h+var_A0], rcx
0x18001cdf9  movzx   eax, word ptr [r14+8]
0x18001cdfe  mov     [rsp+0F8h+var_B4], ax
0x18001ce03  mov     r13d, 1
0x18001ce09  add     ax, r13w
0x18001ce0d  lea     ecx, [r13+7]
0x18001ce11  cmp     ax, cx
0x18001ce14  ja      loc_18001D50A; jumptable 000000018001CE2F cases 1,2
0x18001ce1a  movsx   rax, ax
0x18001ce1e  lea     rdx, __ImageBase
0x18001ce25  mov     ecx, ds:(jpt_18001CE2F - 180000000h)[rdx+rax*4]; switch 9 cases
0x18001ce2c  add     rcx, rdx
0x18001ce2f  jmp     rcx; switch jump
0x18001ce31  xor     r15d, r15d; jumptable 000000018001CE2F case 4
0x18001ce34  jmp     loc_18001D4F4
0x18001ce39  xor     r15d, r15d; jumptable 000000018001CE2F case 3
0x18001ce3c  mov     r12, [r14+2F8h]
0x18001ce43  mov     [r14+10h], r15
0x18001ce47  test    r12, r12
0x18001ce4a  jz      short loc_18001CE61
0x18001ce4c  mov     [r14+10h], r12
0x18001ce50  mov     rax, [r12]
0x18001ce54  mov     rcx, r12
0x18001ce57  mov     rax, [rax+8]
0x18001ce5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce60  nop
0x18001ce61  lea     rdi, [r14+210h]
0x18001ce68  mov     [rdi], r15
0x18001ce6b  mov     rdx, rdi; ppv
0x18001ce6e  lea     rcx, ??$guid_v@UIContextCallback@impl@winrt@@@impl@winrt@@3Uguid@2@B; riid
0x18001ce75  call    WINRT_IMPL_CoGetObjectContext
0x18001ce7a  mov     rax, [rdi]
0x18001ce7d  mov     [rsp+0F8h+var_88], rax
0x18001ce82  mov     [r14+18h], rax
0x18001ce86  lea     rbx, [r14+218h]
0x18001ce8d  mov     [rbx], r15d
0x18001ce90  lea     rdx, [r14+21Ch]; pAptQualifier
0x18001ce97  mov     [rdx], r15d
0x18001ce9a  mov     rcx, rbx; pAptType
0x18001ce9d  call    WINRT_IMPL_CoGetApartmentType
0x18001cea2  test    eax, eax
0x18001cea4  jnz     short loc_18001CEAE
0x18001cea6  mov     eax, [rbx]
0x18001cea8  mov     [rsp+0F8h+var_B0], eax
0x18001ceac  jmp     short loc_18001CEB1
0x18001ceae  mov     eax, r13d
0x18001ceb1  mov     [r14+20h], eax
0x18001ceb5  lea     rbx, [r12+228h]
0x18001cebd  mov     rcx, rbx; lpCriticalSection
0x18001cec0  call    cs:__imp_EnterCriticalSection
0x18001cec6  mov     [r14+28h], rbx
0x18001ceca  mov     eax, r15d
0x18001cecd  cmp     [r12+250h], r15b
0x18001ced5  jz      short loc_18001CEE7
0x18001ced7  mov     ecx, 4
0x18001cedc  test    [r12+1F8h], ecx
0x18001cee4  cmovnz  eax, ecx
0x18001cee7  cmp     [r12+251h], r15b
0x18001ceef  jz      short loc_18001CF02
0x18001cef1  test    dword ptr [r12+1F8h], 2
0x18001cefd  jz      short loc_18001CF02
0x18001ceff  or      eax, 2
0x18001cf02  cmp     [r12+252h], r15b
0x18001cf0a  jz      short loc_18001CF19
0x18001cf0c  test    [r12+1F8h], r13d
0x18001cf14  jz      short loc_18001CF19
0x18001cf16  or      eax, r13d
0x18001cf19  mov     edx, [r12+200h]
0x18001cf21  or      edx, [r12+1FCh]
0x18001cf29  mov     ecx, edx
0x18001cf2b  not     ecx
0x18001cf2d  and     ecx, eax
0x18001cf2f  mov     [rsp+0F8h+var_B8], ecx
0x18001cf33  mov     [r14+30h], ecx
0x18001cf37  jz      loc_18001D116
0x18001cf3d  mov     r13d, ecx
0x18001cf40  or      r13d, edx
0x18001cf43  not     r13d
0x18001cf46  and     r13d, [r12+1F8h]
0x18001cf4e  mov     [r14+220h], r13d
0x18001cf55  mov     rcx, [r12+18h]
0x18001cf5a  test    rcx, rcx
0x18001cf5d  jz      short loc_18001CF65
0x18001cf5f  mov     rcx, [rcx+10h]
0x18001cf63  jmp     short loc_18001CF6C
0x18001cf65  lea     rcx, szFile
0x18001cf6c  lea     rdx, [r14+38h]
0x18001cf70  mov     [rdx], rcx
0x18001cf73  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cf77  inc     rax
0x18001cf7a  cmp     [rcx+rax*2], r15w
0x18001cf7f  jnz     short loc_18001CF77
0x18001cf81  mov     [r14+40h], rax
0x18001cf85  lea     rcx, [r14+48h]
0x18001cf89  call    ?GetImageNameFromFullPath@@YA?AV?$basic_zstring_view@G@wil@@AEBV12@@Z; GetImageNameFromFullPath(wil::basic_zstring_view<ushort> const &)
0x18001cf8e  mov     edi, [r12+208h]
0x18001cf96  or      r13d, [r12+25Ch]
0x18001cf9e  mov     rsi, [r14+48h]
0x18001cfa2  mov     [rsp+0F8h+var_80], rsi
0x18001cfa7  lea     rbx, [r14+60h]
0x18001cfab  lea     rdx, aAllowapplicati; "AllowApplication"
0x18001cfb2  mov     rcx, rbx
0x18001cfb5  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001cfba  lea     rax, ??_7AllowApplication@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::AllowApplication::`vftable'
0x18001cfc1  mov     [rbx], rax
0x18001cfc4  mov     [rsp+0F8h+var_C8], edi; unsigned int
0x18001cfc8  mov     al, [r12+20Eh]
0x18001cfd0  mov     [rsp+0F8h+var_D0], al; bool
0x18001cfd4  mov     dword ptr [rsp+0F8h+var_D8], r13d; unsigned int
0x18001cfd9  mov     r9d, [rsp+0F8h+var_B8]; unsigned int
0x18001cfde  mov     r8, rsi; unsigned __int16 *
0x18001cfe1  mov     rdx, [r12+58h]; HWND
0x18001cfe6  mov     rcx, rbx; this
0x18001cfe9  call    ?StartActivity@AllowApplication@FirewallUxTelemetry@@QEAAXPEAUHWND__@@PEBGKK_NK@Z; FirewallUxTelemetry::AllowApplication::StartActivity(HWND__ *,ushort const *,ulong,ulong,bool,ulong)
0x18001cfee  nop
0x18001cfef  mov     rbx, [r12+1D8h]
0x18001cff7  mov     rsi, [r12+1E0h]
0x18001cfff  cmp     rbx, rsi
0x18001d002  jz      short loc_18001D044
0x18001d004  mov     rcx, [rbx]
0x18001d007  lea     rdi, [r14+230h]
0x18001d00e  mov     [rdi], r15d
0x18001d011  mov     [r14+238h], r15
0x18001d018  mov     [r14+240h], r15
0x18001d01f  mov     rax, [rcx]
0x18001d022  xor     edx, edx
0x18001d024  mov     rax, [rax+0B8h]
0x18001d02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d030  test    eax, eax
0x18001d032  jns     short loc_18001D03E
0x18001d034  mov     rdx, rdi
0x18001d037  mov     ecx, eax
0x18001d039  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d03e  add     rbx, 8
0x18001d042  jmp     short loc_18001CFFF
0x18001d044  mov     rax, [r14+2F8h]
0x18001d04b  mov     rcx, [rax+1F0h]
0x18001d052  lea     rbx, [r14+248h]
0x18001d059  mov     [rbx], r15d
0x18001d05c  mov     [r14+250h], r15
0x18001d063  mov     [r14+258h], r15
0x18001d06a  mov     rax, [rcx]
0x18001d06d  mov     dl, 1
0x18001d06f  mov     rax, [rax+38h]
0x18001d073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d078  test    eax, eax
0x18001d07a  jns     short loc_18001D086
0x18001d07c  mov     rdx, rbx
0x18001d07f  mov     ecx, eax
0x18001d081  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d086  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18001d08b  mov     ecx, [rax]
0x18001d08d  cmp     ecx, 5
0x18001d090  jbe     short loc_18001D0BB
0x18001d092  lea     rcx, [r14+260h]
0x18001d099  mov     qword ptr [rsp+0F8h+var_D0], rcx
0x18001d09e  mov     dword ptr [rsp+0F8h+var_D8], 2
0x18001d0a6  xor     r9d, r9d
0x18001d0a9  xor     r8d, r8d
0x18001d0ac  lea     rdx, byte_1800335A1
0x18001d0b3  mov     rcx, rax
0x18001d0b6  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d0bb  lea     rdx, [r14+1B0h]
0x18001d0c2  mov     [rdx], r15b
0x18001d0c5  lea     rcx, [r14+1B8h]
0x18001d0cc  lea     rax, [r14+60h]
0x18001d0d0  mov     [rcx], rax
0x18001d0d3  mov     [r14+1C0h], rdx
0x18001d0da  mov     [r14+1C8h], r15b
0x18001d0e1  xor     eax, eax
0x18001d0e3  mov     [r14+1C9h], eax
0x18001d0ea  mov     [r14+1CDh], ax
0x18001d0f2  mov     [r14+1CFh], al
0x18001d0f9  lea     rdx, [r14+1D0h]
0x18001d100  mov     [rdx], r14
0x18001d103  lea     r8d, [rax+4]
0x18001d107  mov     [r14+8], r8w
0x18001d10c  call    ??$await_suspend@U?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@2@PEAUIPopupWindow@@PEAUIPopupCommand@@@experimental@std@@@experimental@std@@@?$coroutine_withsuspend_awaiter@VAllowApplication@FirewallUxTelemetry@@$$QEAUawaitable@?1??resume_background@winrt@@YA@XZ@@coro@details@wil@@QEAA?A_P$$QEAU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@2@PEAUIPopupWindow@@PEAUIPopupCommand@@@experimental@std@@@experimental@std@@@Z
0x18001d111  jmp     loc_18001D50B
0x18001d116  mov     [r14+34h], r15d
0x18001d11a  mov     edi, r15d
0x18001d11d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d122  mov     r12d, 800704C7h
0x18001d128  jmp     loc_18001D362
0x18001d12d  lea     rbx, [r14+60h]; jumptable 000000018001CE2F case 6
0x18001d131  lea     rax, ??_7AllowApplication@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::AllowApplication::`vftable'
0x18001d138  mov     [rbx], rax
0x18001d13b  mov     rcx, rbx
0x18001d13e  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001d143  mov     rcx, rbx
0x18001d146  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001d14b  nop
0x18001d14c  mov     rcx, [r14+28h]; lpCriticalSection
0x18001d150  xor     r15d, r15d
0x18001d153  test    rcx, rcx
0x18001d156  jz      short loc_18001D15F
0x18001d158  call    cs:__imp_LeaveCriticalSection
0x18001d15e  nop
0x18001d15f  lea     rcx, [r14+18h]
0x18001d163  mov     rax, [rcx]
0x18001d166  mov     [rsp+0F8h+var_98], rax
0x18001d16b  test    rax, rax
0x18001d16e  jz      short loc_18001D176
0x18001d170  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d175  nop
0x18001d176  lea     rcx, [r14+10h]
0x18001d17a  mov     rax, [rcx]
0x18001d17d  mov     [rsp+0F8h+var_A8], rax
0x18001d182  test    rax, rax
0x18001d185  jz      short loc_18001D18D
0x18001d187  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d18c  nop
0x18001d18d  jmp     loc_18001D4F4
0x18001d192  mov     ebx, [r14+220h]; jumptable 000000018001CE2F case 5
0x18001d199  mov     [r14+34h], ebx
0x18001d19d  mov     al, [r14+1C8h]
0x18001d1a4  mov     [rsp+0F8h+var_60], al
0x18001d1ab  xor     r15d, r15d
0x18001d1ae  test    al, al
0x18001d1b0  jz      short loc_18001D1CE
0x18001d1b2  mov     rcx, [r14+1B8h]
0x18001d1b9  mov     [rsp+0F8h+var_70], rcx
0x18001d1c1  add     rcx, 120h; this
0x18001d1c8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001d1cd  nop
0x18001d1ce  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x18001d1d3  mov     ecx, [rax]
0x18001d1d5  cmp     ecx, 5
0x18001d1d8  jbe     short loc_18001D203
0x18001d1da  lea     rcx, [r14+280h]
0x18001d1e1  mov     qword ptr [rsp+0F8h+var_D0], rcx
0x18001d1e6  mov     dword ptr [rsp+0F8h+var_D8], 2
0x18001d1ee  xor     r9d, r9d
0x18001d1f1  xor     r8d, r8d
0x18001d1f4  lea     rdx, byte_18003357E
0x18001d1fb  mov     rcx, rax
0x18001d1fe  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d203  mov     rcx, [r14+2F8h]
0x18001d20a  or      ebx, [rcx+25Ch]
0x18001d210  lea     rdx, [rcx+18h]
0x18001d214  mov     eax, [rcx+208h]
0x18001d21a  mov     dword ptr [rsp+0F8h+var_D0], eax
0x18001d21e  mov     al, [rcx+20Eh]
0x18001d224  mov     byte ptr [rsp+0F8h+var_D8], al
0x18001d228  mov     r9d, ebx
0x18001d22b  mov     r8d, [r14+30h]
0x18001d22f  mov     rcx, [rcx+58h]
0x18001d233  call    ?AllowApplication@@YAJPEAUHWND__@@AEBUhstring@winrt@@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@3@2_N2@Z; AllowApplication(HWND__ *,winrt::hstring const &,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes)
0x18001d238  mov     [r14+200h], eax
0x18001d23f  lea     rcx, [r14+1D8h]
0x18001d246  lea     rax, [r14+18h]
0x18001d24a  mov     [rcx], rax
0x18001d24d  mov     [r14+1E0h], r15
0x18001d254  mov     eax, 6
0x18001d259  mov     [r14+8], ax
0x18001d25e  mov     rdx, r14
0x18001d261  call    ?await_suspend@apartment_awaiter@impl@winrt@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::apartment_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18001d266  test    al, al
0x18001d268  jz      short loc_18001D2D7
0x18001d26a  jmp     loc_18001D50B
0x18001d26f  lea     rbx, [r14+60h]; jumptable 000000018001CE2F case 8
0x18001d273  lea     rax, ??_7AllowApplication@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::AllowApplication::`vftable'
0x18001d27a  mov     [rbx], rax
0x18001d27d  mov     rcx, rbx
0x18001d280  call    ?Destroy@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001d285  mov     rcx, rbx
0x18001d288  call    ??1?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001d28d  nop
0x18001d28e  mov     rcx, [r14+28h]; lpCriticalSection
0x18001d292  xor     r15d, r15d
0x18001d295  test    rcx, rcx
0x18001d298  jz      short loc_18001D2A1
0x18001d29a  call    cs:__imp_LeaveCriticalSection
0x18001d2a0  nop
0x18001d2a1  lea     rcx, [r14+18h]
0x18001d2a5  mov     rax, [rcx]
0x18001d2a8  mov     [rsp+0F8h+var_98], rax
0x18001d2ad  test    rax, rax
0x18001d2b0  jz      short loc_18001D2B8
0x18001d2b2  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001d2b7  nop
0x18001d2b8  lea     rcx, [r14+10h]
0x18001d2bc  mov     rax, [rcx]
0x18001d2bf  mov     [rsp+0F8h+var_A8], rax
0x18001d2c4  test    rax, rax
0x18001d2c7  jz      short loc_18001D2CF
  ... truncated ...
```
