# PopupWindowBehavior::Show$_ResumeCoro$1

- ea: `0x18002adb0`
- end: `0x18002b300`
- name: `PopupWindowBehavior::Show$_ResumeCoro$1`
- size: `1360`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b39c`

## callees

- `0x180002b20`
- `0x180002b7c`
- `0x1800041c4`
- `0x1800049ac`
- `0x180006698`
- `0x1800088ac`
- `0x1800088e4`
- `0x1800089c0`
- `0x1800089e4`
- `0x180008a30`
- `0x180008c5c`
- `0x18000d670`
- `0x18001049c`
- `0x180017124`
- `0x18001e950`
- `0x180022024`
- `0x1800220c8`
- `0x180028008`
- `0x18002aa40`
- `0x18002adb0`
- `0x18005a010`

## import_xrefs

- `USER32!ShowWindow` at `0x18002b18c`
- `USER32!ShowWindow` at `0x18002b18c`
- `USER32!SetForegroundWindow` at `0x18002b170`
- `USER32!SetForegroundWindow` at `0x18002b251`
- `USER32!SetForegroundWindow` at `0x18002b170`
- `USER32!SetForegroundWindow` at `0x18002b251`
- `USER32!GetForegroundWindow` at `0x18002b239`
- `USER32!GetForegroundWindow` at `0x18002b239`
- `USER32!GetLastActivePopup` at `0x18002b230`
- `USER32!GetLastActivePopup` at `0x18002b248`
- `USER32!GetLastActivePopup` at `0x18002b230`
- `USER32!GetLastActivePopup` at `0x18002b248`

## string_xrefs

- `0x18002af71`: `pcshell\shell\uxframe\dll\PopupWindowBehavior.h`
- `0x18002afb3`: `pcshell\shell\uxframe\dll\PopupWindowBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PopupWindowBehavior::Show__ResumeCoro_1(char *Block)
{
  __int64 v2; // r14
  __int64 v3; // rcx
  __int64 v4; // rbx
  const char *v5; // r9
  _QWORD *v6; // r10
  __int64 v7; // r14
  const char *v8; // r9
  char v9; // al
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  HWND v13; // rbx
  HWND LastActivePopup; // rax
  __int64 v15; // [rsp+38h] [rbp-A0h]
  __int64 v16; // [rsp+38h] [rbp-A0h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  switch ( *((_WORD *)Block + 4) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_55;
    case 2:
      *((_QWORD *)Block + 3) = 0;
      v2 = *((_QWORD *)Block + 29);
      *((_QWORD *)Block + 2) = 0;
      *((_QWORD *)Block + 3) = 0;
      v3 = *(_QWORD *)(v2 + 16);
      if ( v3 )
      {
        *((_QWORD *)Block + 2) = *(_QWORD *)(v2 + 8);
        *((_QWORD *)Block + 3) = v3;
        _InterlockedAdd((volatile signed __int32 *)(v3 + 12), 1u);
      }
      v4 = *((_QWORD *)Block + 31);
      *((_DWORD *)Block + 8) = *(_DWORD *)v4;
      *((_DWORD *)Block + 9) = *(_DWORD *)(v4 + 4);
      *((_QWORD *)Block + 5) = *(_QWORD *)(v4 + 8);
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)(Block + 40));
      *((_QWORD *)Block + 6) = *(_QWORD *)(v4 + 16);
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)(Block + 48));
      *((_QWORD *)Block + 7) = v2 + 32;
      *((_DWORD *)Block + 16) = 0;
      *((_QWORD *)Block + 9) = 0;
      Block[80] = 0;
      *((_WORD *)Block + 4) = 4;
      `wil::resume_foreground<winrt::Windows::System::DispatcherQueue>'::`2'::awaitable::await_suspend(
        Block + 56,
        Block);
      return;
    case 4:
      `wil::resume_foreground<winrt::Windows::System::DispatcherQueue>'::`2'::awaitable::await_resume(Block + 56);
      *(_OWORD *)(Block + 88) = 0;
      std::weak_ptr<WindowingBehavior>::lock(Block + 16, Block + 88);
      if ( *v6 )
      {
        v7 = *((_QWORD *)Block + 29);
        if ( *(_BYTE *)(v7 + 228) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x1E2,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\PopupWindowBehavior.h",
            v5);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
        {
          if ( *(_DWORD *)(v7 + 68) || (v9 = 1, !*((_DWORD *)Block + 60)) )
            v9 = 0;
          if ( v9 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x1EB,
              (unsigned int)"pcshell\\shell\\uxframe\\dll\\PopupWindowBehavior.h",
              v8);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
          && *(_DWORD *)(v7 + 224) == 2 )
        {
          if ( *((_QWORD *)Block + 6) )
          {
            Block[104] = 1;
            v16 = winrt::box_value<bool,0>(Block + 112);
            winrt::param::hstring::hstring((winrt::param::hstring *)(Block + 120), L"HostHidingCancelled");
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              Block + 48,
              Block + 120,
              v16);
            if ( *((_QWORD *)Block + 14) )
              winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(Block + 112);
          }
          else
          {
            winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)(Block + 152));
            Block[160] = 1;
            v15 = winrt::box_value<bool,0>(Block + 168);
            winrt::param::hstring::hstring((winrt::param::hstring *)(Block + 176), L"HostHidingCancelled");
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              Block + 152,
              Block + 176,
              v15);
            if ( *((_QWORD *)Block + 21) )
              winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(Block + 168);
            winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)(Block + 48));
            winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)(Block + 152));
          }
        }
        if ( ((*(_DWORD *)(v7 + 224) - 1) & 0xFFFFFFFD) != 0 )
        {
          *(_BYTE *)(v7 + 228) = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
          {
            winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)(v7 + 56));
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 208) + 8LL))(*(_QWORD *)(v7 + 208), v7 + 56);
          }
          else
          {
            v10 = *(__int64 **)(v7 + 208);
            v11 = *v10;
            *((_QWORD *)Block + 26) = 0;
            (*(void (__fastcall **)(__int64 *, char *))(v11 + 8))(v10, Block + 208);
            winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)(Block + 208));
          }
          if ( (***(unsigned int (__fastcall ****)(_QWORD, char *))(v7 + 24))(*(_QWORD *)(v7 + 24), Block + 32) )
          {
            *(_DWORD *)(v7 + 224) = 3;
          }
          else if ( *((_DWORD *)Block + 60) > 1u
                 || SetForegroundWindow(*(HWND *)(v7 + 40))
                 || *((_DWORD *)Block + 60) == 1 )
          {
            ShowWindow(*(HWND *)(v7 + 40), 4);
            if ( *(_QWORD *)(v7 + 160) )
            {
              *((_DWORD *)Block + 54) = 0;
              winrt::impl::consume_WindowsUdk_UI_Shell_IShellViewCoordinator<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::ReportVisibility();
            }
            *(_DWORD *)(v7 + 224) = 1;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 24) + 8LL))(*(_QWORD *)(v7 + 24));
          }
          *(_BYTE *)(v7 + 228) = 0;
          if ( *((_QWORD *)Block + 12) )
            std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)Block + 12));
          ShowContext::~ShowContext((ShowContext *)(Block + 32));
          if ( *((_QWORD *)Block + 3) )
            std::_Ref_count_base::_Decwref(*((std::_Ref_count_base **)Block + 3));
        }
        else
        {
          v12 = *((_DWORD *)Block + 60);
          if ( !v12 || v12 == 1 && (v13 = GetLastActivePopup(*(HWND *)(v7 + 40)), GetForegroundWindow() != v13) )
          {
            LastActivePopup = GetLastActivePopup(*(HWND *)(v7 + 40));
            SetForegroundWindow(LastActivePopup);
          }
          if ( *((_QWORD *)Block + 12) )
            std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)Block + 12));
          ShowContext::~ShowContext((ShowContext *)(Block + 32));
          if ( *((_QWORD *)Block + 3) )
            std::_Ref_count_base::_Decwref(*((std::_Ref_count_base **)Block + 3));
        }
      }
      else
      {
        if ( *((_QWORD *)Block + 12) )
          std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)Block + 12));
        ShowContext::~ShowContext((ShowContext *)(Block + 32));
        if ( *((_QWORD *)Block + 3) )
          std::_Ref_count_base::_Decwref(*((std::_Ref_count_base **)Block + 3));
      }
      goto LABEL_55;
    case 5:
      ShowContext::~ShowContext((ShowContext *)(Block + 32));
      if ( *((_QWORD *)Block + 3) )
        std::_Ref_count_base::_Decwref(*((std::_Ref_count_base **)Block + 3));
LABEL_55:
      if ( *((_WORD *)Block + 5) )
        operator delete(Block);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18002adb0  mov     r11, rsp
0x18002adb3  mov     [r11+10h], rbx
0x18002adb7  mov     [r11+18h], rsi
0x18002adbb  mov     [r11+8], rcx
0x18002adbf  push    rdi
0x18002adc0  push    r12
0x18002adc2  push    r13
0x18002adc4  push    r14
0x18002adc6  push    r15
0x18002adc8  sub     rsp, 0B0h
0x18002adcf  mov     rax, cs:__security_cookie
0x18002add6  xor     rax, rsp
0x18002add9  mov     [rsp+0D8h+var_30], rax
0x18002ade1  mov     rdi, rcx
0x18002ade4  mov     [rsp+0D8h+var_B0], rcx
0x18002ade9  movzx   eax, word ptr [rdi+8]
0x18002aded  mov     [rsp+0D8h+var_B8], ax
0x18002adf2  mov     r15d, 1
0x18002adf8  add     ax, r15w
0x18002adfc  cmp     ax, 6; switch 7 cases
0x18002ae00  ja      def_18002AE1B; jumptable 000000018002AE1B default case, cases 1,2
0x18002ae06  movsx   rax, ax
0x18002ae0a  lea     rdx, __ImageBase
0x18002ae11  mov     ecx, ds:(jpt_18002AE1B - 180000000h)[rdx+rax*4]
0x18002ae18  add     rcx, rdx
0x18002ae1b  jmp     rcx; switch jump
0x18002ae1d  xor     esi, esi; jumptable 000000018002AE1B case 4
0x18002ae1f  jmp     loc_18002B29C
0x18002ae24  xor     esi, esi; jumptable 000000018002AE1B case 3
0x18002ae26  mov     [rdi+18h], rsi
0x18002ae2a  mov     r14, [rdi+0E8h]
0x18002ae31  mov     [rdi+10h], rsi
0x18002ae35  mov     [rdi+18h], rsi
0x18002ae39  mov     rcx, [r14+10h]
0x18002ae3d  test    rcx, rcx
0x18002ae40  jz      short loc_18002AE53
0x18002ae42  mov     rax, [r14+8]
0x18002ae46  mov     [rdi+10h], rax
0x18002ae4a  mov     [rdi+18h], rcx
0x18002ae4e  lock add [rcx+0Ch], r15d
0x18002ae53  mov     rbx, [rdi+0F8h]
0x18002ae5a  mov     eax, [rbx]
0x18002ae5c  mov     [rdi+20h], eax
0x18002ae5f  mov     eax, [rbx+4]
0x18002ae62  mov     [rdi+24h], eax
0x18002ae65  lea     rcx, [rdi+28h]; this
0x18002ae69  mov     rax, [rbx+8]
0x18002ae6d  mov     [rcx], rax
0x18002ae70  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18002ae75  lea     rcx, [rdi+30h]; this
0x18002ae79  mov     rax, [rbx+10h]
0x18002ae7d  mov     [rcx], rax
0x18002ae80  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18002ae85  nop
0x18002ae86  lea     rcx, [rdi+38h]
0x18002ae8a  lea     rax, [r14+20h]
0x18002ae8e  mov     [rcx], rax
0x18002ae91  mov     [rdi+40h], esi
0x18002ae94  mov     [rdi+48h], rsi
0x18002ae98  mov     [rdi+50h], sil
0x18002ae9c  mov     edx, 4
0x18002aea1  mov     [rdi+8], dx
0x18002aea5  mov     rdx, rdi
0x18002aea8  call    ?await_suspend@awaitable@?1???$resume_foreground@UDispatcherQueue@System@Windows@winrt@@@wil@@YA?A_PAEBUDispatcherQueue@System@Windows@winrt@@W4DispatcherQueuePriority@456@@Z@QEAAXU?$coroutine_handle@X@experimental@std@@@Z
0x18002aead  jmp     loc_18002B2B6
0x18002aeb2  lea     rcx, [rdi+20h]; jumptable 000000018002AE1B case 6
0x18002aeb6  call    ??1ShowContext@@QEAA@XZ; ShowContext::~ShowContext(void)
0x18002aebb  nop
0x18002aebc  mov     rax, [rdi+18h]
0x18002aec0  mov     [rsp+0D8h+var_98], rax
0x18002aec5  xor     esi, esi
0x18002aec7  test    rax, rax
0x18002aeca  jz      short loc_18002AEDB
0x18002aecc  mov     rcx, [rdi+18h]; this
0x18002aed0  mov     [rsp+0D8h+var_98], rcx
0x18002aed5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002aeda  nop
0x18002aedb  jmp     loc_18002B29C
0x18002aee0  lea     rcx, [rdi+38h]; jumptable 000000018002AE1B case 5
0x18002aee4  call    ?await_resume@awaitable@?1???$resume_foreground@UDispatcherQueue@System@Windows@winrt@@@wil@@YA?A_PAEBUDispatcherQueue@System@Windows@winrt@@W4DispatcherQueuePriority@456@@Z@QEBAXXZ
0x18002aee9  lea     r10, [rdi+58h]
0x18002aeed  xorps   xmm0, xmm0
0x18002aef0  movups  xmmword ptr [r10], xmm0
0x18002aef4  mov     rdx, r10
0x18002aef7  lea     rcx, [rdi+10h]
0x18002aefb  call    ?lock@?$weak_ptr@VWindowingBehavior@@@std@@QEBA?AV?$shared_ptr@VWindowingBehavior@@@2@XZ; std::weak_ptr<WindowingBehavior>::lock(void)
0x18002af00  nop
0x18002af01  mov     rax, [r10]
0x18002af04  mov     [rsp+0D8h+var_90], rax
0x18002af09  xor     esi, esi
0x18002af0b  test    rax, rax
0x18002af0e  jnz     short loc_18002AF59
0x18002af10  mov     rax, [rdi+60h]
0x18002af14  mov     [rsp+0D8h+var_88], rax
0x18002af19  test    rax, rax
0x18002af1c  jz      short loc_18002AF2D
0x18002af1e  mov     rcx, [rdi+60h]; this
0x18002af22  mov     [rsp+0D8h+var_88], rcx
0x18002af27  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002af2c  nop
0x18002af2d  lea     rcx, [rdi+20h]; this
0x18002af31  call    ??1ShowContext@@QEAA@XZ; ShowContext::~ShowContext(void)
0x18002af36  nop
0x18002af37  mov     rax, [rdi+18h]
0x18002af3b  mov     [rsp+0D8h+var_98], rax
0x18002af40  test    rax, rax
0x18002af43  jz      short loc_18002AF54
0x18002af45  mov     rcx, [rdi+18h]; this
0x18002af49  mov     [rsp+0D8h+var_98], rcx
0x18002af4e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002af53  nop
0x18002af54  jmp     loc_18002B29C
0x18002af59  mov     r14, [rdi+0E8h]
0x18002af60  mov     rcx, [rsp+0D8h]; this
0x18002af68  cmp     [r14+0E4h], sil
0x18002af6f  jz      short loc_18002AF83
0x18002af71  lea     r8, aPcshellShellUx_4; "pcshell\\shell\\uxframe\\dll\\PopupWind"...
0x18002af78  mov     edx, 1E2h; void *
0x18002af7d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002af83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18002af8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18002af8f  test    al, al
0x18002af91  jnz     short loc_18002AFC5
0x18002af93  cmp     [r14+44h], esi
0x18002af97  jnz     short loc_18002AFA4
0x18002af99  cmp     [rdi+0F0h], esi
0x18002af9f  mov     al, r15b
0x18002afa2  jnz     short loc_18002AFA7
0x18002afa4  mov     al, sil
0x18002afa7  mov     rcx, [rsp+0D8h]; this
0x18002afaf  test    al, al
0x18002afb1  jz      short loc_18002AFC5
0x18002afb3  lea     r8, aPcshellShellUx_4; "pcshell\\shell\\uxframe\\dll\\PopupWind"...
0x18002afba  mov     edx, 1EBh; void *
0x18002afbf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002afc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18002afcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18002afd1  test    al, al
0x18002afd3  jz      loc_18002B0D1
0x18002afd9  cmp     dword ptr [r14+0E0h], 2
0x18002afe1  jnz     loc_18002B0D1
0x18002afe7  mov     rax, [rdi+30h]
0x18002afeb  mov     [rsp+0D8h+var_70], rax
0x18002aff0  test    rax, rax
0x18002aff3  jnz     loc_18002B07B
0x18002aff9  lea     r15, [rdi+98h]
0x18002b000  mov     rcx, r15; this
0x18002b003  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x18002b008  nop
0x18002b009  lea     rdx, [rdi+0A0h]
0x18002b010  mov     byte ptr [rdx], 1
0x18002b013  lea     r12, [rdi+0A8h]
0x18002b01a  mov     rcx, r12
0x18002b01d  call    ??$box_value@_N$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEB_N@Z; winrt::box_value<bool,0>(bool const &)
0x18002b022  mov     [rsp+0D8h+var_A0], rax
0x18002b027  lea     rbx, [rdi+0B0h]
0x18002b02e  lea     rdx, aHosthidingcanc; "HostHidingCancelled"
0x18002b035  mov     rcx, rbx; this
0x18002b038  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18002b03d  mov     r8, [rsp+0D8h+var_A0]
0x18002b042  mov     rdx, rbx
0x18002b045  mov     rcx, r15
0x18002b048  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18002b04d  nop
0x18002b04e  mov     rax, [r12]
0x18002b052  mov     [rsp+0D8h+var_A8], rax
0x18002b057  test    rax, rax
0x18002b05a  jz      short loc_18002B064
0x18002b05c  mov     rcx, r12
0x18002b05f  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18002b064  mov     rdx, r15
0x18002b067  lea     rcx, [rdi+30h]; this
0x18002b06b  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x18002b070  nop
0x18002b071  mov     rcx, r15; this
0x18002b074  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002b079  jmp     short loc_18002B0CB
0x18002b07b  lea     rdx, [rdi+68h]
0x18002b07f  mov     [rdx], r15b
0x18002b082  lea     r15, [rdi+70h]
0x18002b086  mov     rcx, r15
0x18002b089  call    ??$box_value@_N$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEB_N@Z; winrt::box_value<bool,0>(bool const &)
0x18002b08e  mov     [rsp+0D8h+var_A0], rax
0x18002b093  lea     rdx, aHosthidingcanc; "HostHidingCancelled"
0x18002b09a  lea     rcx, [rdi+78h]; this
0x18002b09e  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18002b0a3  mov     r8, [rsp+0D8h+var_A0]
0x18002b0a8  lea     rdx, [rdi+78h]
0x18002b0ac  lea     rcx, [rdi+30h]
0x18002b0b0  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18002b0b5  nop
0x18002b0b6  mov     rax, [r15]
0x18002b0b9  mov     [rsp+0D8h+var_A8], rax
0x18002b0be  test    rax, rax
0x18002b0c1  jz      short loc_18002B0CB
0x18002b0c3  mov     rcx, r15
0x18002b0c6  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18002b0cb  mov     r15d, 1
0x18002b0d1  mov     eax, [r14+0E0h]
0x18002b0d8  sub     eax, r15d
0x18002b0db  test    eax, 0FFFFFFFDh
0x18002b0e0  jz      loc_18002B21D
0x18002b0e6  mov     [r14+0E4h], r15b
0x18002b0ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18002b0f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18002b0f9  test    al, al
0x18002b0fb  jz      short loc_18002B123
0x18002b0fd  lea     rdx, [rdi+30h]
0x18002b101  lea     rcx, [r14+38h]; this
0x18002b105  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x18002b10a  mov     rcx, [r14+0D0h]
0x18002b111  mov     rax, [rcx]
0x18002b114  lea     rdx, [r14+38h]
0x18002b118  mov     rax, [rax+8]
0x18002b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b121  jmp     short loc_18002B14C
0x18002b123  mov     rcx, [r14+0D0h]
0x18002b12a  mov     rax, [rcx]
0x18002b12d  lea     rbx, [rdi+0D0h]
0x18002b134  mov     [rbx], rsi
0x18002b137  mov     rdx, rbx
0x18002b13a  mov     rax, [rax+8]
0x18002b13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b143  nop
0x18002b144  mov     rcx, rbx; this
0x18002b147  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002b14c  mov     rcx, [r14+18h]
0x18002b150  mov     rax, [rcx]
0x18002b153  lea     rdx, [rdi+20h]
0x18002b157  mov     rax, [rax]
0x18002b15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b15f  test    eax, eax
0x18002b161  jnz     short loc_18002B1C5
0x18002b163  cmp     [rdi+0F0h], r15d
0x18002b16a  ja      short loc_18002B183
0x18002b16c  mov     rcx, [r14+28h]; hWnd
0x18002b170  call    cs:__imp_SetForegroundWindow
0x18002b176  test    eax, eax
0x18002b178  jnz     short loc_18002B183
0x18002b17a  cmp     [rdi+0F0h], r15d
0x18002b181  jnz     short loc_18002B1D0
0x18002b183  mov     edx, 4; nCmdShow
0x18002b188  mov     rcx, [r14+28h]; hWnd
0x18002b18c  call    cs:__imp_ShowWindow
0x18002b192  lea     rcx, [r14+0A0h]
0x18002b199  cmp     [rcx], rsi
0x18002b19c  jz      short loc_18002B1AC
0x18002b19e  lea     rdx, [rdi+0D8h]
0x18002b1a5  mov     [rdx], esi
0x18002b1a7  call    ?ReportVisibility@?$consume_WindowsUdk_UI_Shell_IShellViewCoordinator@UIShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBW4ViewVisibility@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShellViewCoordinator<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::ReportVisibility(winrt::WindowsUdk::UI::Shell::ViewVisibility const &)
0x18002b1ac  mov     [r14+0E0h], r15d
0x18002b1b3  mov     rcx, [r14+18h]
0x18002b1b7  mov     rax, [rcx]
0x18002b1ba  mov     rax, [rax+8]
0x18002b1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1c3  jmp     short loc_18002B1D0
0x18002b1c5  mov     dword ptr [r14+0E0h], 3
0x18002b1d0  mov     [r14+0E4h], sil
0x18002b1d7  mov     rax, [rdi+60h]
0x18002b1db  mov     [rsp+0D8h+var_88], rax
0x18002b1e0  test    rax, rax
0x18002b1e3  jz      short loc_18002B1F4
0x18002b1e5  mov     rcx, [rdi+60h]; this
0x18002b1e9  mov     [rsp+0D8h+var_88], rcx
0x18002b1ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b1f3  nop
0x18002b1f4  lea     rcx, [rdi+20h]; this
0x18002b1f8  call    ??1ShowContext@@QEAA@XZ; ShowContext::~ShowContext(void)
0x18002b1fd  nop
0x18002b1fe  mov     rax, [rdi+18h]
0x18002b202  mov     [rsp+0D8h+var_98], rax
0x18002b207  test    rax, rax
0x18002b20a  jz      short loc_18002B21B
0x18002b20c  mov     rcx, [rdi+18h]; this
0x18002b210  mov     [rsp+0D8h+var_98], rcx
0x18002b215  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002b21a  nop
0x18002b21b  jmp     short loc_18002B29C
0x18002b21d  mov     eax, [rdi+0F0h]
0x18002b223  test    eax, eax
0x18002b225  jz      short loc_18002B244
0x18002b227  cmp     eax, r15d
0x18002b22a  jnz     short loc_18002B258
0x18002b22c  mov     rcx, [r14+28h]; hWnd
0x18002b230  call    cs:__imp_GetLastActivePopup
0x18002b236  mov     rbx, rax
0x18002b239  call    cs:__imp_GetForegroundWindow
0x18002b23f  cmp     rax, rbx
0x18002b242  jz      short loc_18002B258
0x18002b244  mov     rcx, [r14+28h]; hWnd
0x18002b248  call    cs:__imp_GetLastActivePopup
0x18002b24e  mov     rcx, rax; hWnd
0x18002b251  call    cs:__imp_SetForegroundWindow
0x18002b257  nop
0x18002b258  mov     rax, [rdi+60h]
0x18002b25c  mov     [rsp+0D8h+var_88], rax
0x18002b261  test    rax, rax
0x18002b264  jz      short loc_18002B275
0x18002b266  mov     rcx, [rdi+60h]; this
0x18002b26a  mov     [rsp+0D8h+var_88], rcx
  ... truncated ...
```
