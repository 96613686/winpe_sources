# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::LaunchSettingsUIForPrinterAsync$_ResumeCoro$1

- ea: `0x18002b7c0`
- end: `0x18002bfe0`
- name: `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::LaunchSettingsUIForPrinterAsync$_ResumeCoro$1`
- size: `2080`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c044`

## callees

- `0x180003ca0`
- `0x180003cc4`
- `0x180010f00`
- `0x1800127a4`
- `0x180012940`
- `0x1800129dc`
- `0x180012b10`
- `0x1800147dc`
- `0x1800147fc`
- `0x180014868`
- `0x1800166a8`
- `0x180017b20`
- `0x18001cd64`
- `0x18001da30`
- `0x18002546c`
- `0x180027618`
- `0x18002762c`
- `0x1800284b8`
- `0x180028a08`
- `0x180028a44`
- `0x180029208`
- `0x180029b10`
- `0x180029e58`
- `0x180029ec8`
- `0x18002a560`
- `0x18002adc0`
- `0x18002b194`
- `0x18002b778`
- `0x18002b7c0`
- `0x18002c660`
- `0x18002c6bc`
- `0x18002c714`
- `0x18002c8dc`
- `0x18002c8fc`
- `0x18002c930`
- `0x18002c97c`
- `0x18002ce9c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bc27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bc27`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18002bbf1`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18002bd5b`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18002bbf1`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x18002bd5b`

## string_xrefs

- `0x18002b92c`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b9c3`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002b9fc`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002ba40`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002bb45`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002bc3c`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`
- `0x18002bcf2`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::LaunchSettingsUIForPrinterAsync__ResumeCoro_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rcx
  _QWORD *v8; // r13
  __int64 v9; // r14
  char v10; // al
  LPVOID **v11; // r13
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  _QWORD *v17; // rax
  int v18; // eax
  __int64 v19; // rax
  winrt::impl::signal_awaiter *v20; // rbx
  __int64 *v21; // rbx
  HRESULT Instance; // eax
  winrt::hstring *ExecutablePath; // rax
  const unsigned __int16 *v24; // rax
  __int64 v25; // r8
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rbx
  void *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  int ppv; // [rsp+20h] [rbp-158h]
  LPVOID *ppva; // [rsp+20h] [rbp-158h]
  int ppvb; // [rsp+20h] [rbp-158h]
  __int64 (__fastcall *v38)(__int64, const unsigned __int16 *, __int64, const WCHAR *); // [rsp+60h] [rbp-118h]
  __int64 v39; // [rsp+68h] [rbp-110h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_65;
    case 2:
      winrt::implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_strong(
        *(_QWORD *)(a1 + 328),
        a1 + 16);
      *(_QWORD *)(a1 + 256) = a1 - 112;
      *(_BYTE *)(a1 + 24) = 0;
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(
        a1 - 112,
        a1 + 24);
      *(_WORD *)v5 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v6, a1);
      return;
    case 4:
      *(_QWORD *)(a1 + 32) = winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(
                               *(_QWORD *)(a1 + 256),
                               *(_QWORD *)(a1 + 328) + 72LL);
      *(_QWORD *)(a1 + 40) = 0;
      *(_WORD *)v5 = 6;
      if ( (unsigned __int8)winrt::impl::apartment_awaiter::await_suspend(a1 + 32, a1) )
        return;
      goto LABEL_11;
    case 5:
      v7 = a1 + 16;
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(
          v7,
          &_ImageBase,
          a3,
          a4);
      goto LABEL_65;
    case 6:
LABEL_11:
      winrt::impl::apartment_awaiter::await_resume((winrt::impl::apartment_awaiter *)(a1 + 32));
      v8 = (_QWORD *)(v5 + 320);
      v9 = *(_QWORD *)(v5 + 320);
      v10 = *(_BYTE *)(v9 + 216);
      *(_BYTE *)(v9 + 216) = 1;
      if ( v10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
          (const char *)0x8000000ELL,
          ppv);
      if ( winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::IsCentennialApp((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *)v9) )
      {
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetActivationEventArgs(
          v9,
          a1 + 224);
        if ( *(_BYTE *)(v9 + 128) )
          EnableWindow(*(HWND *)(v9 + 120), 0);
        *(_QWORD *)(a1 + 232) = v9;
        *(_BYTE *)(a1 + 240) = 1;
        v21 = (__int64 *)(a1 + 248);
        *(_QWORD *)(a1 + 248) = 0;
        Instance = CoCreateInstance(
                     &GUID_168eb462_775f_42ae_9111_d714b2306c2e,
                     0,
                     1u,
                     &GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a,
                     (LPVOID *)(a1 + 248));
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC6,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
            (const char *)(unsigned int)Instance,
            ppvb);
        *(_QWORD *)(a1 + 272) = 0;
        v39 = *v21;
        v38 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, const WCHAR *))(*(_QWORD *)*v21
                                                                                                  + 40LL);
        ExecutablePath = (winrt::hstring *)winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetExecutablePath(
                                             v9,
                                             a1 + 280);
        winrt::hstring::c_str(ExecutablePath);
        v24 = winrt::hstring::c_str((winrt::hstring *)(v9 + 168));
        v26 = v38(v39, v24, v25, &sourceString);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
            (const char *)(unsigned int)v26,
            6176);
        winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 280);
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::WaitForViewCloseOrProcessExit(
          v9,
          a1 + 272);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a1 + 272);
        if ( *v21 )
          winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 248);
        if ( *(_BYTE *)(v9 + 128) )
          EnableWindow(*(HWND *)(v9 + 120), 1);
        v27 = a1 + 224;
        if ( *(_QWORD *)(a1 + 224) )
LABEL_61:
          winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(v27);
      }
      else
      {
        *(_QWORD *)(a1 + 72) = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)(a1 + 48),
          L"Windows.PrintSupportSettingsUI",
          0x1Fu,
          0x1Eu);
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetModalExperienceManager(
          v9,
          a1 + 80);
        v11 = (LPVOID **)(a1 + 88);
        *(_QWORD *)(a1 + 88) = 0;
        *(_QWORD *)(a1 + 120) = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)(a1 + 96),
          L"Windows.Internal.Shell.ModalExperience.ModalExperienceOptions",
          0x3Eu,
          0x3Du);
        v12 = Windows::Foundation::ActivateInstance<Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions>(
                *(_QWORD *)(a1 + 120),
                a1 + 88);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
            (const char *)(unsigned int)v12,
            ppv);
        LOBYTE(v13) = 1;
        v14 = (*((__int64 (__fastcall **)(LPVOID *, __int64))**v11 + 10))(*v11, v13);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8E,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
            (const char *)(unsigned int)v14,
            ppv);
        if ( !*(_BYTE *)(v9 + 128) )
        {
          LOBYTE(v15) = 1;
          v16 = (*((__int64 (__fastcall **)(LPVOID *, __int64))**v11 + 18))(*v11, v15);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x91,
              (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
              (const char *)(unsigned int)v16,
              ppv);
        }
        winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(
          v9,
          a1 + 128);
        *(_QWORD *)(a1 + 136) = *(_QWORD *)(a1 + 128);
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a1 + 136);
        v17 = (_QWORD *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager___Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs___::___Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager___Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager___Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs_____lambda_76d5fc6f04ecbed9c09eea01318e1c43___1_Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager___Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs_____lambda_76d5fc6f04ecbed9c09eea01318e1c43___(
                          a1 + 296,
                          a1 + 136);
        *(_QWORD *)(a1 + 144) = *v17;
        *v17 = 0;
        if ( *(_QWORD *)(a1 + 296) )
        {
          *(_QWORD *)(a1 + 296) = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *,Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs *>>::Release();
        }
        lambda_df897e6668674d5dce194a7e6d974069_::__lambda_df897e6668674d5dce194a7e6d974069_(a1 + 136);
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetActivationEventArgs(
          v9,
          a1 + 152);
        ppva = *v11;
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 80) + 56LL))(
                *(_QWORD *)(a1 + 80),
                *(_QWORD *)(v9 + 168));
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
            (const char *)(unsigned int)v18,
            (int)ppva);
        _InterlockedExchange((volatile __int32 *)(v9 + 144), 1);
        v19 = *(_QWORD *)(v9 + 64);
        *(_QWORD *)(a1 + 160) = 0;
        *(_QWORD *)(a1 + 168) = 0;
        *(_QWORD *)(a1 + 176) = 0;
        *(_QWORD *)(a1 + 184) = v19;
        *(_DWORD *)(a1 + 192) = 0;
        *(_QWORD *)(a1 + 200) = 0;
        *(_DWORD *)(a1 + 208) = 0;
        v20 = (winrt::impl::signal_awaiter *)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(
                                               *(_QWORD *)(a1 + 256),
                                               a1 + 160);
        *(_QWORD *)(a1 + 304) = v20;
        if ( !winrt::impl::signal_awaiter::await_ready(v20) )
        {
          *(_WORD *)v5 = 8;
          winrt::impl::signal_awaiter::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type>(
            v20,
            a1);
          return;
        }
LABEL_52:
        winrt::impl::signal_awaiter::await_resume(*(winrt::impl::signal_awaiter **)(a1 + 304));
        winrt::impl::signal_awaiter::~signal_awaiter((winrt::impl::signal_awaiter *)(a1 + 160));
        v8 = (_QWORD *)(v5 + 320);
        v29 = *(_QWORD *)(v5 + 320);
        _InterlockedExchange((volatile __int32 *)(v29 + 144), 0);
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::UnregisterFromModalExperienceEvents((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *)v29);
        wil::details::SetEvent(*(wil::details **)(v29 + 152), v30);
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::TryTerminatingSettingsProcess(
          v29,
          a1 + 216);
        if ( *(_QWORD *)(a1 + 152) )
          winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 152);
        v31 = *(_QWORD *)(a1 + 144);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( *(_QWORD *)(a1 + 128) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
        if ( *(_QWORD *)(a1 + 88) )
          winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 88);
        v27 = a1 + 80;
        if ( *(_QWORD *)(a1 + 80) )
          goto LABEL_61;
      }
      winrt::Windows::Foundation::IUnknown::operator=(*(_QWORD *)(a1 + 256) + 104LL, *v8 + 56LL);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(
          a1 + 16,
          v32,
          v33,
          v34);
      *(_QWORD *)(a1 + 288) = a1 - 112;
      *(_WORD *)v5 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(
                               a1 + 288,
                               v32,
                               v33,
                               v34) )
      {
LABEL_65:
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type::~promise_type(a1 - 112);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x1C0u);
      }
      return;
    case 7:
      if ( *(_QWORD *)(a1 + 16) )
        ((void (*)(void))winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref)();
      goto LABEL_65;
    case 8:
      goto LABEL_52;
    case 9:
      winrt::impl::signal_awaiter::~signal_awaiter((winrt::impl::signal_awaiter *)(a1 + 160));
      if ( *(_QWORD *)(a1 + 152) )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 152);
      v28 = *(_QWORD *)(a1 + 144);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( *(_QWORD *)(a1 + 128) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
      if ( *(_QWORD *)(a1 + 88) )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 88);
      if ( *(_QWORD *)(a1 + 80) )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 80);
      *(_QWORD *)(a1 + 72) = 0;
      if ( *(_QWORD *)(a1 + 16) )
        ((void (*)(void))winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref)();
      goto LABEL_65;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18002b7c0  mov     r11, rsp
0x18002b7c3  mov     [r11+10h], rbx
0x18002b7c7  mov     [r11+18h], rsi
0x18002b7cb  mov     [r11+8], rcx
0x18002b7cf  push    rdi
0x18002b7d0  push    r12
0x18002b7d2  push    r13
0x18002b7d4  push    r14
0x18002b7d6  push    r15
0x18002b7d8  sub     rsp, 150h
0x18002b7df  mov     rax, cs:__security_cookie
0x18002b7e6  xor     rax, rsp
0x18002b7e9  mov     [rsp+178h+var_30], rax
0x18002b7f1  mov     rdi, rcx
0x18002b7f4  mov     [rsp+178h+var_F0], rcx
0x18002b7fc  lea     r15, [rdi+8]
0x18002b800  mov     [rsp+178h+var_E8], r15
0x18002b808  movzx   eax, word ptr [r15]
0x18002b80c  mov     [rsp+178h+var_100], ax
0x18002b811  mov     r12d, 1
0x18002b817  add     ax, r12w
0x18002b81b  cmp     ax, 0Ah; switch 11 cases
0x18002b81f  ja      def_18002B83A; jumptable 000000018002B83A default case, case 1
0x18002b825  movsx   rax, ax
0x18002b829  lea     rdx, __ImageBase
0x18002b830  mov     ecx, ds:(jpt_18002B83A - 180000000h)[rdx+rax*4]
0x18002b837  add     rcx, rdx
0x18002b83a  jmp     rcx; switch jump
0x18002b83c  xor     esi, esi; jumptable 000000018002B83A case 4
0x18002b83e  jmp     loc_18002BF63
0x18002b843  xor     esi, esi; jumptable 000000018002B83A case 3
0x18002b845  lea     rdx, [rdi+10h]
0x18002b849  mov     rcx, [r15+140h]
0x18002b850  call    ?get_strong@?$implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@winrt@@QEAA?AU?$com_ptr@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_strong(void)
0x18002b855  nop
0x18002b856  lea     rcx, [rdi-70h]
0x18002b85a  mov     [rdi+100h], rcx
0x18002b861  lea     rdx, [rdi+18h]
0x18002b865  mov     [rdx], sil
0x18002b868  call    ??$await_transform@AEAUapartment_context@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAAEAUapartment_context@2@AEAU32@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(winrt::apartment_context &)
0x18002b86d  lea     eax, [rsi+4]
0x18002b870  mov     [r15], ax
0x18002b874  mov     rdx, rdi
0x18002b877  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18002b87c  nop
0x18002b87d  jmp     loc_18002BF83
0x18002b882  lea     rcx, [rdi+10h]; jumptable 000000018002B83A case 6
0x18002b886  mov     rax, [rcx]
0x18002b889  mov     [rsp+178h+var_120], rax
0x18002b88e  xor     esi, esi
0x18002b890  test    rax, rax
0x18002b893  jz      short loc_18002B89B
0x18002b895  call    ?unconditional_release_ref@?$com_ptr@UPrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(void)
0x18002b89a  nop
0x18002b89b  jmp     loc_18002BF63
0x18002b8a0  mov     rdx, [r15+140h]; jumptable 000000018002B83A case 5
0x18002b8a7  add     rdx, 48h ; 'H'
0x18002b8ab  mov     rcx, [rdi+100h]
0x18002b8b2  call    ??$await_transform@AEAUapartment_context@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAAEAUapartment_context@2@AEAU32@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(winrt::apartment_context &)
0x18002b8b7  lea     rcx, [rdi+20h]
0x18002b8bb  mov     [rcx], rax
0x18002b8be  xor     esi, esi
0x18002b8c0  mov     [rdi+28h], rsi
0x18002b8c4  lea     eax, [rsi+6]
0x18002b8c7  mov     [r15], ax
0x18002b8cb  mov     rdx, rdi
0x18002b8ce  call    ?await_suspend@apartment_awaiter@impl@winrt@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::apartment_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18002b8d3  test    al, al
0x18002b8d5  jz      short loc_18002B8FC
0x18002b8d7  jmp     loc_18002BF83
0x18002b8dc  lea     rcx, [rdi+10h]; jumptable 000000018002B83A case 8
0x18002b8e0  mov     rax, [rcx]
0x18002b8e3  mov     [rsp+178h+var_120], rax
0x18002b8e8  xor     esi, esi
0x18002b8ea  test    rax, rax
0x18002b8ed  jz      short loc_18002B8F5
0x18002b8ef  call    ?unconditional_release_ref@?$com_ptr@UPrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(void)
0x18002b8f4  nop
0x18002b8f5  jmp     loc_18002BF63
0x18002b8fa  xor     esi, esi; jumptable 000000018002B83A case 7
0x18002b8fc  lea     rcx, [rdi+20h]; this
0x18002b900  call    ?await_resume@apartment_awaiter@impl@winrt@@QEBAXXZ; winrt::impl::apartment_awaiter::await_resume(void)
0x18002b905  lea     r13, [r15+140h]
0x18002b90c  mov     r14, [r13+0]
0x18002b910  mov     eax, r12d
0x18002b913  xchg    al, [r14+0D8h]
0x18002b91a  mov     rcx, [rsp+178h]; this
0x18002b922  test    al, al
0x18002b924  jz      short loc_18002B93D
0x18002b926  mov     r9d, 8000000Eh; char *
0x18002b92c  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b933  mov     edx, 83h; void *
0x18002b938  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b93d  mov     rcx, r14; this
0x18002b940  call    ?IsCentennialApp@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::IsCentennialApp(void)
0x18002b945  test    al, al
0x18002b947  jnz     loc_18002BBD2
0x18002b94d  mov     [rdi+48h], rsi
0x18002b951  lea     rcx, [rdi+30h]; hstringHeader
0x18002b955  mov     r9d, 1Eh; unsigned int
0x18002b95b  lea     r8d, [r9+1]; unsigned int
0x18002b95f  lea     rdx, aWindowsPrintsu_0; "Windows.PrintSupportSettingsUI"
0x18002b966  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b96b  nop
0x18002b96c  lea     rdx, [rdi+50h]
0x18002b970  mov     rcx, r14
0x18002b973  call    ?GetModalExperienceManager@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AU?$com_ptr@UIModalWindowExperienceManager@ModalExperience@Shell@Internal@Windows@@@8@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetModalExperienceManager(void)
0x18002b978  nop
0x18002b979  lea     r13, [rdi+58h]
0x18002b97d  mov     [r13+0], rsi
0x18002b981  mov     [rdi+78h], rsi
0x18002b985  lea     rcx, [rdi+60h]; hstringHeader
0x18002b989  mov     r9d, 3Dh ; '='; unsigned int
0x18002b98f  lea     r8d, [r9+1]; unsigned int
0x18002b993  lea     rdx, ?RuntimeClass_Windows_Internal_Shell_ModalExperience_ModalExperienceOptions@@3QBGB; "Windows.Internal.Shell.ModalExperience."...
0x18002b99a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b99f  nop
0x18002b9a0  mov     rcx, [rdi+78h]
0x18002b9a4  mov     [rsp+178h+var_C8], rcx
0x18002b9ac  mov     rdx, r13
0x18002b9af  call    ??$ActivateInstance@UIModalExperienceDefaultOptions@ModalExperience@Shell@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIModalExperienceDefaultOptions@ModalExperience@Shell@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions>(HSTRING__ *,Windows::Internal::Shell::ModalExperience::IModalExperienceDefaultOptions * *)
0x18002b9b4  mov     rcx, [rsp+178h]; this
0x18002b9bc  test    eax, eax
0x18002b9be  jns     short loc_18002B9D5
0x18002b9c0  mov     r9d, eax; char *
0x18002b9c3  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b9ca  mov     edx, 8Dh; void *
0x18002b9cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b9d5  mov     rcx, [r13+0]
0x18002b9d9  mov     [rsp+178h+var_128], rcx
0x18002b9de  mov     rax, [rcx]
0x18002b9e1  mov     dl, r12b
0x18002b9e4  mov     rax, [rax+50h]
0x18002b9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9ed  mov     rcx, [rsp+178h]; this
0x18002b9f5  test    eax, eax
0x18002b9f7  jns     short loc_18002BA0D
0x18002b9f9  mov     r9d, eax; char *
0x18002b9fc  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002ba03  mov     edx, 8Eh; void *
0x18002ba08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba0d  cmp     [r14+80h], sil
0x18002ba14  jnz     short loc_18002BA51
0x18002ba16  mov     rcx, [r13+0]
0x18002ba1a  mov     [rsp+178h+var_128], rcx
0x18002ba1f  mov     rax, [rcx]
0x18002ba22  mov     dl, r12b
0x18002ba25  mov     rax, [rax+90h]
0x18002ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba31  mov     rcx, [rsp+178h]; this
0x18002ba39  test    eax, eax
0x18002ba3b  jns     short loc_18002BA51
0x18002ba3d  mov     r9d, eax; char *
0x18002ba40  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002ba47  mov     edx, 91h; void *
0x18002ba4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba51  lea     rdx, [rdi+80h]
0x18002ba58  mov     rcx, r14
0x18002ba5b  call    ??$get_weak@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@?$root_implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@impl@winrt@@IEAA?AU?$weak_ref@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_weak<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession>(void)
0x18002ba60  nop
0x18002ba61  lea     rbx, [rdi+88h]
0x18002ba68  mov     rax, [rdi+80h]
0x18002ba6f  mov     [rsp+178h+var_110], rax
0x18002ba74  mov     [rbx], rax
0x18002ba77  mov     rcx, rbx
0x18002ba7a  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002ba7f  lea     rcx, [rdi+128h]
0x18002ba86  mov     rdx, rbx
0x18002ba89  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Internal__Shell__ModalExperience__IModalWindowExperienceManager___Windows__Internal__Shell__ModalExperience__IModalExperienceEventArgs________Windows__Internal__Shell__ModalExperience__IModalWindowExperienceManager___Windows__Internal__Shell__ModalExperience__IModalExperienceEventArgs______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Internal__Shell__ModalExperience__IModalWindowExperienceManager___Windows__Internal__Shell__ModalExperience__IModalExperienceEventArgs_____lambda_76d5fc6f04ecbed9c09eea01318e1c43___1_Windows__Internal__Shell__ModalExperience__IModalWindowExperienceManager___Windows__Internal__Shell__ModalExperience__IModalExperienceEventArgs_____lambda_76d5fc6f04ecbed9c09eea01318e1c43___
0x18002ba8e  mov     rcx, [rax]
0x18002ba91  mov     [rsp+178h+var_120], rcx
0x18002ba96  mov     [rdi+90h], rcx
0x18002ba9d  mov     [rax], rsi
0x18002baa0  lea     rax, [rdi+128h]
0x18002baa7  mov     rcx, [rax]
0x18002baaa  mov     [rsp+178h+var_F8], rcx
0x18002bab2  test    rcx, rcx
0x18002bab5  jz      short loc_18002BAC0
0x18002bab7  mov     [rax], rsi
0x18002baba  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAUIModalWindowExperienceManager@ModalExperience@Shell@Internal@Windows@@PEAUIModalExperienceEventArgs@2345@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::ModalExperience::IModalWindowExperienceManager *,Windows::Internal::Shell::ModalExperience::IModalExperienceEventArgs *>>::Release(void)
0x18002babf  nop
0x18002bac0  mov     rcx, rbx
0x18002bac3  call    _lambda_df897e6668674d5dce194a7e6d974069_____lambda_df897e6668674d5dce194a7e6d974069_
0x18002bac8  lea     rdx, [rdi+98h]
0x18002bacf  mov     rcx, r14
0x18002bad2  call    ?GetActivationEventArgs@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AU?$com_ptr@UIInspectable@@@8@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetActivationEventArgs(void)
0x18002bad7  nop
0x18002bad8  mov     rcx, [rdi+50h]
0x18002badc  mov     [rsp+178h+var_108], rcx
0x18002bae1  mov     rax, [rcx]
0x18002bae4  mov     r11d, [r14+78h]
0x18002bae8  mov     rbx, [r13+0]
0x18002baec  mov     [rsp+178h+var_128], rbx
0x18002baf1  mov     r9, [rdi+98h]
0x18002baf8  mov     [rsp+178h+var_118], r9
0x18002bafd  mov     rdx, [r14+0A8h]
0x18002bb04  mov     r8, [rdi+48h]
0x18002bb08  mov     [rsp+178h+var_A8], r8
0x18002bb10  lea     r10, [r14+20h]
0x18002bb14  mov     [rsp+178h+var_140], r10
0x18002bb19  mov     r10, [rsp+178h+var_120]
0x18002bb1e  mov     [rsp+178h+var_148], r10
0x18002bb23  mov     [rsp+178h+var_150], r11d
0x18002bb28  mov     [rsp+178h+ppv], rbx; int
0x18002bb2d  mov     rax, [rax+38h]
0x18002bb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb36  mov     rcx, [rsp+178h]; this
0x18002bb3e  test    eax, eax
0x18002bb40  jns     short loc_18002BB56
0x18002bb42  mov     r9d, eax; char *
0x18002bb45  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002bb4c  mov     edx, 0A5h; void *
0x18002bb51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bb56  xchg    r12d, [r14+90h]
0x18002bb5d  mov     rax, [r14+40h]
0x18002bb61  lea     rdx, [rdi+0A0h]
0x18002bb68  mov     [rdx], rsi
0x18002bb6b  mov     [rdi+0A8h], rsi
0x18002bb72  mov     [rdi+0B0h], rsi
0x18002bb79  mov     [rdi+0B8h], rax
0x18002bb80  mov     [rdi+0C0h], esi
0x18002bb86  mov     [rdi+0C8h], rsi
0x18002bb8d  mov     [rdi+0D0h], esi
0x18002bb93  mov     rcx, [rdi+100h]
0x18002bb9a  call    ??$await_transform@AEAUapartment_context@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAAEAUapartment_context@2@AEAU32@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::await_transform<winrt::apartment_context &>(winrt::apartment_context &)
0x18002bb9f  mov     rbx, rax
0x18002bba2  mov     [rdi+130h], rax
0x18002bba9  mov     rcx, rax; this
0x18002bbac  call    ?await_ready@signal_awaiter@impl@winrt@@QEBA_NXZ; winrt::impl::signal_awaiter::await_ready(void)
0x18002bbb1  test    al, al
0x18002bbb3  jnz     loc_18002BE33
0x18002bbb9  mov     eax, 8
0x18002bbbe  mov     [r15], ax
0x18002bbc2  mov     rdx, rdi
0x18002bbc5  mov     rcx, rbx
0x18002bbc8  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@@experimental@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type>)
0x18002bbcd  jmp     loc_18002B87D
0x18002bbd2  lea     rdx, [rdi+0E0h]
0x18002bbd9  mov     rcx, r14
0x18002bbdc  call    ?GetActivationEventArgs@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AU?$com_ptr@UIInspectable@@@8@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetActivationEventArgs(void)
0x18002bbe1  nop
0x18002bbe2  cmp     [r14+80h], sil
0x18002bbe9  jz      short loc_18002BBF7
0x18002bbeb  xor     edx, edx; bEnable
0x18002bbed  mov     rcx, [r14+78h]; hWnd
0x18002bbf1  call    cs:__imp_EnableWindow
0x18002bbf7  mov     [rdi+0E8h], r14
0x18002bbfe  mov     [rdi+0F0h], r12b
0x18002bc05  lea     rbx, [rdi+0F8h]
0x18002bc0c  mov     [rbx], rsi
0x18002bc0f  mov     [rsp+178h+ppv], rbx; int
0x18002bc14  lea     r9, _GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a; riid
0x18002bc1b  mov     r8d, r12d; dwClsContext
0x18002bc1e  xor     edx, edx; pUnkOuter
0x18002bc20  lea     rcx, _GUID_168eb462_775f_42ae_9111_d714b2306c2e; rclsid
0x18002bc27  call    cs:__imp_CoCreateInstance
0x18002bc2d  mov     rcx, [rsp+178h]; this
0x18002bc35  test    eax, eax
0x18002bc37  jns     short loc_18002BC4D
0x18002bc39  mov     r9d, eax; char *
0x18002bc3c  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002bc43  mov     edx, 0C6h; void *
0x18002bc48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bc4d  mov     [rdi+110h], rsi
0x18002bc54  mov     rax, [rbx]
0x18002bc57  mov     [rsp+178h+var_110], rax
0x18002bc5c  mov     [rsp+178h+var_128], rax
0x18002bc61  mov     rax, [rax]
0x18002bc64  mov     rax, [rax+28h]
0x18002bc68  mov     [rsp+178h+var_118], rax
0x18002bc6d  mov     rax, [rdi+0E0h]
0x18002bc74  mov     [rsp+178h+var_108], rax
0x18002bc79  mov     [rsp+178h+var_F8], rax
0x18002bc81  lea     rdx, [rdi+118h]
0x18002bc88  mov     rcx, r14
0x18002bc8b  call    ?GetExecutablePath@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::GetExecutablePath(void)
0x18002bc90  nop
0x18002bc91  mov     rcx, rax; this
0x18002bc94  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002bc99  mov     r8, rax
0x18002bc9c  lea     rcx, [r14+0A8h]; this
0x18002bca3  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002bca8  lea     rcx, [rdi+110h]
0x18002bcaf  mov     [rsp+178h+var_140], rcx
0x18002bcb4  mov     rcx, [rsp+178h+var_108]
0x18002bcb9  mov     [rsp+178h+var_148], rcx
0x18002bcbe  mov     [rsp+178h+var_150], esi
0x18002bcc2  mov     dword ptr [rsp+178h+ppv], 1820h; int
0x18002bcca  lea     r9, sourceString
0x18002bcd1  mov     rdx, rax
0x18002bcd4  mov     rcx, [rsp+178h+var_110]
0x18002bcd9  mov     rax, [rsp+178h+var_118]
0x18002bcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bce3  mov     rcx, [rsp+178h]; this
0x18002bceb  test    eax, eax
0x18002bced  jns     short loc_18002BD04
0x18002bcef  mov     r9d, eax; char *
0x18002bcf2  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002bcf9  mov     edx, 0CCh; void *
0x18002bcfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
