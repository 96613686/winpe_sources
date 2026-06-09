# DirectUI::CommandBar::SetOverflowStyleParams(void)

- ea: `0x18034798c`
- end: `0x180347f46`
- name: `?SetOverflowStyleParams@CommandBar@DirectUI@@AEAAJXZ`
- size: `1466`
- prototype: `HRESULT __fastcall(DirectUI::CommandBar *this)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180346500`
- `0x18036f074`
- `0x18037f9c0`
- `0x180612fa0`
- `0x180630bb0`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x1801e5458`
- `0x180346a54`
- `0x18034798c`
- `0x180348c2c`
- `0x180348cfc`
- `0x1809482a0`
- `0x180ab78dc`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347ab2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347ab2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180347de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180347ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180347c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180347ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180347c20`

## pseudocode

```c
__int64 __fastcall DirectUI::CommandBar::SetOverflowStyleParams(DirectUI::CommandBar *this)
{
  DirectUI::CommandBar *v1; // rdi
  DirectUI::CommandBarElementCollection *ActiveSecondaryCommands; // rax
  HRESULT v3; // eax
  unsigned int v4; // ebx
  bool v5; // r13
  bool v6; // r14
  bool v7; // r15
  unsigned int i; // r12d
  DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Controls::ICommandBarElement *> *v9; // rdi
  HRESULT (__fastcall *GetAt)(Windows::Foundation::Collections::IVectorView_impl<Windows::UI::Xaml::Controls::ICommandBarElement *,1> *, unsigned int, Windows::UI::Xaml::Controls::ICommandBarElement **); // rbx
  HRESULT v11; // eax
  Windows::UI::Xaml::Controls::IAppBarToggleButton *v12; // rsi
  HSTRING__ *hstring; // rdi
  Windows::UI::Xaml::Controls::IAppBarToggleButton *v14; // rbx
  HRESULT (__fastcall *v15)(Windows::UI::Xaml::Controls::IAppBarToggleButton *, Windows::UI::Xaml::Controls::IIconElement **); // rdi
  HRESULT v16; // eax
  unsigned int v17; // edi
  HRESULT v18; // eax
  Windows::UI::Xaml::Controls::IIconElement *v19; // rcx
  Windows::UI::Xaml::Controls::ICommandBarElement *v20; // rcx
  HRESULT (__fastcall *get_Icon)(Windows::UI::Xaml::Controls::IAppBarToggleButton *, Windows::UI::Xaml::Controls::IIconElement **); // rdi
  HRESULT KeyboardAcceleratorTextOverride; // eax
  Windows::UI::Xaml::Controls::IIconElement *v23; // rcx
  Windows::UI::Xaml::Controls::ICommandBarElement *v24; // rcx
  unsigned int j; // esi
  DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Controls::ICommandBarElement *> *v26; // rdi
  HRESULT (__fastcall *v27)(Windows::Foundation::Collections::IVectorView_impl<Windows::UI::Xaml::Controls::ICommandBarElement *,1> *, unsigned int, Windows::UI::Xaml::Controls::ICommandBarElement **); // rbx
  HRESULT v28; // eax
  Windows::UI::Xaml::Controls::IIconElement *v29; // rbx
  Windows::UI::Xaml::Controls::ICommandBarElement *v30; // rcx
  HRESULT v31; // eax
  Windows::UI::Xaml::Controls::IIconElement *v33; // rcx
  Windows::UI::Xaml::Controls::ICommandBarElement *v34; // rcx
  Windows::UI::Xaml::Controls::ICommandBarElement *ptr; // rcx
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *p_elementAsAppBarToggleButton; // rcx
  HRESULT v37; // eax
  Windows::Internal::String acceleratorText; // [rsp+20h] [rbp-28h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IAppBarToggleButton> elementAsAppBarToggleButton; // [rsp+28h] [rbp-20h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IAppBarButton> elementAsAppBarButton; // [rsp+30h] [rbp-18h] BYREF
  unsigned int itemCount; // [rsp+98h] [rbp+50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ICommandBarElement> element; // [rsp+A0h] [rbp+58h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IIconElement> icon; // [rsp+A8h] [rbp+60h] BYREF

  v1 = this;
  itemCount = 0;
  ActiveSecondaryCommands = DirectUI::CommandBar::GetActiveSecondaryCommands(this);
  v3 = ActiveSecondaryCommands->get_Size(
         &ActiveSecondaryCommands->DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Controls::ICommandBarElement *>,
         &itemCount);
  v4 = v3;
  if ( v3 < 0 )
  {
    OnFailure_2990_(v3);
    return v4;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= itemCount )
      goto LABEL_52;
    element.ptr_ = 0;
    v9 = &DirectUI::CommandBar::GetActiveSecondaryCommands(v1)->DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Controls::ICommandBarElement *>;
    GetAt = v9->GetAt;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&element);
    v11 = GetAt(v9, i, &element.ptr_);
    v4 = v11;
    if ( v11 < 0 )
    {
      OnFailure_2990_(v11);
      ptr = element.ptr_;
      if ( element.ptr_ )
      {
        element.ptr_ = 0;
        ptr->Release(ptr);
      }
      return v4;
    }
    if ( !element.ptr_ )
      goto LABEL_26;
    v12 = 0;
    hstring = 0;
    icon.ptr_ = 0;
    acceleratorText._hstring = 0;
    elementAsAppBarToggleButton.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&elementAsAppBarToggleButton);
    if ( element.ptr_ )
      element.ptr_->QueryInterface(
        element.ptr_,
        &GUID_4459a451_69e8_440c_9896_4bb4f5f642d1,
        (void **)&elementAsAppBarToggleButton);
    v14 = elementAsAppBarToggleButton.ptr_;
    elementAsAppBarButton.ptr_ = (Windows::UI::Xaml::Controls::IAppBarButton *)elementAsAppBarToggleButton.ptr_;
    if ( elementAsAppBarToggleButton.ptr_ )
      break;
    elementAsAppBarToggleButton.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&elementAsAppBarToggleButton);
    if ( element.ptr_ )
      element.ptr_->QueryInterface(
        element.ptr_,
        &GUID_2e914438_fd53_4b8d_858b_3644269f8e4d,
        (void **)&elementAsAppBarToggleButton);
    v12 = elementAsAppBarToggleButton.ptr_;
    if ( !elementAsAppBarToggleButton.ptr_ )
      goto LABEL_16;
    get_Icon = elementAsAppBarToggleButton.ptr_->get_Icon;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon);
    KeyboardAcceleratorTextOverride = get_Icon(v12, &icon.ptr_);
    v17 = KeyboardAcceleratorTextOverride;
    if ( KeyboardAcceleratorTextOverride < 0
      || (v6 || icon.ptr_ ? (v6 = 1) : (v6 = 0),
          WindowsDeleteString(0),
          KeyboardAcceleratorTextOverride = DirectUI::AppBarToggleButtonGenerated::get_KeyboardAcceleratorTextOverride(
                                              (DirectUI::AppBarToggleButtonGenerated *)&v12[-82],
                                              &acceleratorText._hstring),
          v17 = KeyboardAcceleratorTextOverride,
          KeyboardAcceleratorTextOverride < 0) )
    {
      OnFailure_2990_(KeyboardAcceleratorTextOverride);
      Windows::Internal::String::~String(&acceleratorText);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon);
      p_elementAsAppBarToggleButton = (ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&elementAsAppBarToggleButton;
LABEL_89:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(p_elementAsAppBarToggleButton);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&elementAsAppBarButton);
LABEL_91:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&element);
      return v17;
    }
    hstring = acceleratorText._hstring;
    v5 = 1;
    if ( !v7 && WindowsIsStringEmpty(acceleratorText._hstring) )
    {
LABEL_15:
      v7 = 0;
      goto LABEL_16;
    }
    v7 = 1;
LABEL_16:
    if ( v6 && v5 && v7 )
    {
      if ( hstring )
        WindowsDeleteString(hstring);
      v23 = icon.ptr_;
      if ( icon.ptr_ )
      {
        icon.ptr_ = 0;
        v23->Release(v23);
      }
      if ( v12 )
        v12->Release(v12);
      if ( v14 )
        v14->Release(v14);
      v24 = element.ptr_;
      if ( element.ptr_ )
      {
        element.ptr_ = 0;
        v24->Release(v24);
      }
      v1 = this;
LABEL_52:
      for ( j = 0; ; ++j )
      {
        if ( j >= itemCount )
          return 0;
        element.ptr_ = 0;
        v26 = &DirectUI::CommandBar::GetActiveSecondaryCommands(v1)->DirectUI::PresentationFrameworkCollectionTemplateBase<Windows::UI::Xaml::Controls::ICommandBarElement *>;
        v27 = v26->GetAt;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&element);
        v28 = v27(v26, j, &element.ptr_);
        v17 = v28;
        if ( v28 < 0 )
        {
          OnFailure_2990_(v28);
          goto LABEL_91;
        }
        if ( element.ptr_ )
        {
          icon.ptr_ = 0;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon);
          if ( element.ptr_ )
            element.ptr_->QueryInterface(element.ptr_, &GUID_4459a451_69e8_440c_9896_4bb4f5f642d1, (void **)&icon);
          v29 = icon.ptr_;
          elementAsAppBarButton.ptr_ = (Windows::UI::Xaml::Controls::IAppBarButton *)icon.ptr_;
          if ( icon.ptr_ )
          {
            v31 = DirectUI::AppBarButton::SetOverflowStyleParams((DirectUI::AppBarButton *)&icon.ptr_[-82], v6, v5, v7);
            v17 = v31;
            if ( v31 < 0 )
            {
              OnFailure_2990_(v31);
              v29->Release(v29);
              v34 = element.ptr_;
              if ( !element.ptr_ )
                return v17;
              element.ptr_ = 0;
LABEL_74:
              v34->Release(v34);
              return v17;
            }
            goto LABEL_66;
          }
          icon.ptr_ = 0;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon);
          if ( element.ptr_ )
            element.ptr_->QueryInterface(element.ptr_, &GUID_2e914438_fd53_4b8d_858b_3644269f8e4d, (void **)&icon);
          v29 = icon.ptr_;
          if ( icon.ptr_ )
          {
            v37 = DirectUI::AppBarToggleButton::SetOverflowStyleParams(
                    (DirectUI::AppBarToggleButton *)&icon.ptr_[-82],
                    v6,
                    v7);
            v17 = v37;
            if ( v37 < 0 )
            {
              OnFailure_2990_(v37);
              p_elementAsAppBarToggleButton = (ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon;
              goto LABEL_89;
            }
LABEL_66:
            v29->Release(v29);
          }
        }
        v30 = element.ptr_;
        if ( element.ptr_ )
        {
          element.ptr_ = 0;
          v30->Release(v30);
        }
        v1 = this;
      }
    }
    if ( hstring )
      WindowsDeleteString(hstring);
    v19 = icon.ptr_;
    if ( icon.ptr_ )
    {
      icon.ptr_ = 0;
      v19->Release(v19);
    }
    if ( v12 )
      v12->Release(v12);
    if ( v14 )
      v14->Release(v14);
LABEL_26:
    v20 = element.ptr_;
    if ( element.ptr_ )
    {
      element.ptr_ = 0;
      v20->Release(v20);
    }
    v1 = this;
  }
  v15 = elementAsAppBarToggleButton.ptr_->get_Icon;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&icon);
  v16 = v15(v14, &icon.ptr_);
  v17 = v16;
  if ( v16 < 0 )
  {
    OnFailure_2990_(v16);
    goto LABEL_70;
  }
  v6 = v6 || icon.ptr_;
  WindowsDeleteString(0);
  v18 = DirectUI::AppBarButtonGenerated::get_KeyboardAcceleratorTextOverride(
          (DirectUI::AppBarButtonGenerated *)&v14[-82],
          &acceleratorText._hstring);
  v17 = v18;
  if ( v18 >= 0 )
  {
    hstring = acceleratorText._hstring;
    if ( !v7 && WindowsIsStringEmpty(acceleratorText._hstring) )
      goto LABEL_15;
    v7 = 1;
    goto LABEL_16;
  }
  OnFailure_2990_(v18);
  if ( acceleratorText._hstring )
    WindowsDeleteString(acceleratorText._hstring);
LABEL_70:
  v33 = icon.ptr_;
  if ( icon.ptr_ )
  {
    icon.ptr_ = 0;
    v33->Release(v33);
  }
  v14->Release(v14);
  v34 = element.ptr_;
  if ( element.ptr_ )
  {
    element.ptr_ = 0;
    goto LABEL_74;
  }
  return v17;
}

```

## disassembly

```asm
0x18034798c  mov     [rsp-40h+arg_0], this
0x180347991  push    rbp
0x180347992  push    rbx
0x180347993  push    rsi
0x180347994  push    rdi
0x180347995  push    r12
0x180347997  push    r13
0x180347999  push    r14
0x18034799b  push    r15
0x18034799d  mov     rbp, rsp
0x1803479a0  sub     rsp, 48h
0x1803479a4  mov     rdi, this
0x1803479a7  mov     [rbp+itemCount], 0
0x1803479ae  call    ?GetActiveSecondaryCommands@CommandBar@DirectUI@@AEAAPEAVCommandBarElementCollection@2@XZ; DirectUI::CommandBar::GetActiveSecondaryCommands(void)
0x1803479b3  lea     rdx, [rbp+itemCount]
0x1803479b7  lea     this, [rax+8]
0x1803479bb  mov     rax, [this]
0x1803479be  mov     rax, [rax+38h]
0x1803479c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803479c7  mov     ebx, eax
0x1803479c9  test    eax, eax
0x1803479cb  js      loc_180347F3A
0x1803479d1  xor     r13b, r13b
0x1803479d4  xor     r14b, r14b
0x1803479d7  xor     r15b, r15b
0x1803479da  xor     r12d, r12d
0x1803479dd  cmp     r12d, [rbp+itemCount]
0x1803479e1  jnb     loc_180347E7F
0x1803479e7  mov     this, rdi; this
0x1803479ea  mov     [rbp+element.ptr_], 0
0x1803479f2  call    ?GetActiveSecondaryCommands@CommandBar@DirectUI@@AEAAPEAVCommandBarElementCollection@2@XZ; DirectUI::CommandBar::GetActiveSecondaryCommands(void)
0x1803479f7  lea     this, [rbp+element]; this
0x1803479fb  lea     rdi, [rax+8]
0x1803479ff  mov     rax, [rdi]
0x180347a02  mov     rbx, [rax+30h]
0x180347a06  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347a0b  lea     r8, [rbp+element]
0x180347a0f  mov     edx, r12d
0x180347a12  mov     this, rdi
0x180347a15  mov     rax, rbx
0x180347a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347a1d  mov     ebx, eax
0x180347a1f  test    eax, eax
0x180347a21  js      loc_180347E87
0x180347a27  cmp     [rbp+element.ptr_], 0
0x180347a2c  jz      loc_180347B54
0x180347a32  xor     esi, esi
0x180347a34  lea     this, [rbp+elementAsAppBarToggleButton]; this
0x180347a38  xor     edi, edi
0x180347a3a  mov     [rbp+icon.ptr_], rsi
0x180347a3e  mov     [rbp+acceleratorText._hstring], rdi
0x180347a42  mov     [rbp+elementAsAppBarToggleButton.ptr_], rsi
0x180347a46  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347a4b  mov     this, [rbp+element.ptr_]
0x180347a4f  test    this, this
0x180347a52  jz      short loc_180347A6A
0x180347a54  mov     rax, [this]
0x180347a57  lea     r8, [rbp+elementAsAppBarToggleButton]
0x180347a5b  lea     rdx, _GUID_4459a451_69e8_440c_9896_4bb4f5f642d1
0x180347a62  mov     rax, [rax]
0x180347a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347a6a  mov     rbx, [rbp+elementAsAppBarToggleButton.ptr_]
0x180347a6e  mov     [rbp+elementAsAppBarButton.ptr_], rbx
0x180347a72  test    rbx, rbx
0x180347a75  jz      loc_180347B7D
0x180347a7b  mov     rax, [rbx]
0x180347a7e  lea     this, [rbp+icon]; this
0x180347a82  mov     rdi, [rax+40h]
0x180347a86  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347a8b  lea     rdx, [rbp+icon]
0x180347a8f  mov     this, rbx
0x180347a92  mov     rax, rdi
0x180347a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347a9a  mov     edi, eax
0x180347a9c  test    eax, eax
0x180347a9e  js      loc_180347E3F
0x180347aa4  test    r14b, r14b
0x180347aa7  jz      loc_180347E48
0x180347aad  mov     r14b, 1
0x180347ab0  xor     ecx, ecx; string
0x180347ab2  call    cs:__imp_WindowsDeleteString
0x180347ab8  lea     this, [rbx-290h]; this
0x180347abf  lea     rdx, [rbp+acceleratorText]; pValue
0x180347ac3  call    ?get_KeyboardAcceleratorTextOverride@AppBarButtonGenerated@DirectUI@@QEAAJPEAPEAUHSTRING__@@@Z; DirectUI::AppBarButtonGenerated::get_KeyboardAcceleratorTextOverride(HSTRING__ * *)
0x180347ac8  mov     edi, eax
0x180347aca  test    eax, eax
0x180347acc  js      loc_180347DD5
0x180347ad2  mov     rdi, [rbp+acceleratorText._hstring]
0x180347ad6  test    r15b, r15b
0x180347ad9  jnz     loc_180347C36
0x180347adf  mov     this, rdi; string
0x180347ae2  call    cs:__imp_WindowsIsStringEmpty
0x180347ae8  test    eax, eax
0x180347aea  jz      loc_180347C36
0x180347af0  xor     r15b, r15b
0x180347af3  test    r14b, r14b
0x180347af6  jz      short loc_180347B01
0x180347af8  test    r13b, r13b
0x180347afb  jnz     loc_180347C3E
0x180347b01  test    rdi, rdi
0x180347b04  jz      short loc_180347B0F
0x180347b06  mov     this, rdi; string
0x180347b09  call    cs:__imp_WindowsDeleteString
0x180347b0f  mov     this, [rbp+icon.ptr_]
0x180347b13  test    this, this
0x180347b16  jz      short loc_180347B2C
0x180347b18  mov     [rbp+icon.ptr_], 0
0x180347b20  mov     rax, [this]
0x180347b23  mov     rax, [rax+10h]
0x180347b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347b2c  test    rsi, rsi
0x180347b2f  jz      short loc_180347B40
0x180347b31  mov     rax, [rsi]
0x180347b34  mov     this, rsi
0x180347b37  mov     rax, [rax+10h]
0x180347b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347b40  test    rbx, rbx
0x180347b43  jz      short loc_180347B54
0x180347b45  mov     rax, [rbx]
0x180347b48  mov     this, rbx
0x180347b4b  mov     rax, [rax+10h]
0x180347b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347b54  mov     this, [rbp+element.ptr_]
0x180347b58  test    this, this
0x180347b5b  jz      short loc_180347B71
0x180347b5d  mov     [rbp+element.ptr_], 0
0x180347b65  mov     rax, [this]
0x180347b68  mov     rax, [rax+10h]
0x180347b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347b71  mov     rdi, [rbp+arg_0]
0x180347b75  inc     r12d
0x180347b78  jmp     loc_1803479DD
0x180347b7d  lea     this, [rbp+elementAsAppBarToggleButton]; this
0x180347b81  mov     [rbp+elementAsAppBarToggleButton.ptr_], rsi
0x180347b85  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347b8a  mov     this, [rbp+element.ptr_]
0x180347b8e  test    this, this
0x180347b91  jz      short loc_180347BA9
0x180347b93  mov     rax, [this]
0x180347b96  lea     r8, [rbp+elementAsAppBarToggleButton]
0x180347b9a  lea     rdx, _GUID_2e914438_fd53_4b8d_858b_3644269f8e4d
0x180347ba1  mov     rax, [rax]
0x180347ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347ba9  mov     rsi, [rbp+elementAsAppBarToggleButton.ptr_]
0x180347bad  mov     [rbp+elementAsAppBarToggleButton.ptr_], rsi
0x180347bb1  test    rsi, rsi
0x180347bb4  jz      loc_180347AF3
0x180347bba  mov     rax, [rsi]
0x180347bbd  lea     this, [rbp+icon]; this
0x180347bc1  mov     rdi, [rax+40h]
0x180347bc5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347bca  lea     rdx, [rbp+icon]
0x180347bce  mov     this, rsi
0x180347bd1  mov     rax, rdi
0x180347bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347bd9  mov     edi, eax
0x180347bdb  test    eax, eax
0x180347bdd  js      loc_180347ECE
0x180347be3  test    r14b, r14b
0x180347be6  jz      loc_180347EB2
0x180347bec  mov     r14b, 1
0x180347bef  xor     ecx, ecx; string
0x180347bf1  call    cs:__imp_WindowsDeleteString
0x180347bf7  lea     this, [rsi-290h]; this
0x180347bfe  lea     rdx, [rbp+acceleratorText]; pValue
0x180347c02  call    ?get_KeyboardAcceleratorTextOverride@AppBarToggleButtonGenerated@DirectUI@@QEAAJPEAPEAUHSTRING__@@@Z; DirectUI::AppBarToggleButtonGenerated::get_KeyboardAcceleratorTextOverride(HSTRING__ * *)
0x180347c07  mov     edi, eax
0x180347c09  test    eax, eax
0x180347c0b  js      loc_180347EC5
0x180347c11  mov     rdi, [rbp+acceleratorText._hstring]
0x180347c15  mov     r13b, 1
0x180347c18  test    r15b, r15b
0x180347c1b  jnz     short loc_180347C2E
0x180347c1d  mov     this, rdi; string
0x180347c20  call    cs:__imp_WindowsIsStringEmpty
0x180347c26  test    eax, eax
0x180347c28  jnz     loc_180347AF0
0x180347c2e  mov     r15b, r13b
0x180347c31  jmp     loc_180347AF3
0x180347c36  mov     r15b, 1
0x180347c39  jmp     loc_180347AF3
0x180347c3e  test    r15b, r15b
0x180347c41  jz      loc_180347B01
0x180347c47  xor     r12d, r12d
0x180347c4a  test    rdi, rdi
0x180347c4d  jz      short loc_180347C58
0x180347c4f  mov     this, rdi; string
0x180347c52  call    cs:__imp_WindowsDeleteString
0x180347c58  mov     this, [rbp+icon.ptr_]
0x180347c5c  test    this, this
0x180347c5f  jz      short loc_180347C71
0x180347c61  mov     [rbp+icon.ptr_], r12
0x180347c65  mov     rax, [this]
0x180347c68  mov     rax, [rax+10h]
0x180347c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347c71  test    rsi, rsi
0x180347c74  jz      short loc_180347C85
0x180347c76  mov     rax, [rsi]
0x180347c79  mov     this, rsi
0x180347c7c  mov     rax, [rax+10h]
0x180347c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347c85  test    rbx, rbx
0x180347c88  jz      short loc_180347C99
0x180347c8a  mov     rax, [rbx]
0x180347c8d  mov     this, rbx
0x180347c90  mov     rax, [rax+10h]
0x180347c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347c99  mov     this, [rbp+element.ptr_]
0x180347c9d  test    this, this
0x180347ca0  jz      short loc_180347CB2
0x180347ca2  mov     [rbp+element.ptr_], r12
0x180347ca6  mov     rax, [this]
0x180347ca9  mov     rax, [rax+10h]
0x180347cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347cb2  mov     rdi, [rbp+arg_0]
0x180347cb6  mov     esi, r12d
0x180347cb9  cmp     esi, [rbp+itemCount]
0x180347cbc  jnb     loc_180347DD1
0x180347cc2  mov     this, rdi; this
0x180347cc5  mov     [rbp+element.ptr_], r12
0x180347cc9  call    ?GetActiveSecondaryCommands@CommandBar@DirectUI@@AEAAPEAVCommandBarElementCollection@2@XZ; DirectUI::CommandBar::GetActiveSecondaryCommands(void)
0x180347cce  lea     this, [rbp+element]; this
0x180347cd2  lea     rdi, [rax+8]
0x180347cd6  mov     rax, [rdi]
0x180347cd9  mov     rbx, [rax+30h]
0x180347cdd  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347ce2  lea     r8, [rbp+element]
0x180347ce6  mov     edx, esi
0x180347ce8  mov     this, rdi
0x180347ceb  mov     rax, rbx
0x180347cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347cf3  mov     edi, eax
0x180347cf5  test    eax, eax
0x180347cf7  js      loc_180347F08
0x180347cfd  cmp     [rbp+element.ptr_], r12
0x180347d01  jz      short loc_180347D7D
0x180347d03  mov     [rbp+icon.ptr_], r12
0x180347d07  lea     this, [rbp+icon]; this
0x180347d0b  mov     [rbp+icon.ptr_], r12
0x180347d0f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347d14  mov     this, [rbp+element.ptr_]
0x180347d18  test    this, this
0x180347d1b  jz      short loc_180347D33
0x180347d1d  mov     rax, [this]
0x180347d20  lea     r8, [rbp+icon]
0x180347d24  lea     rdx, _GUID_4459a451_69e8_440c_9896_4bb4f5f642d1
0x180347d2b  mov     rax, [rax]
0x180347d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347d33  mov     rbx, [rbp+icon.ptr_]
0x180347d37  mov     [rbp+elementAsAppBarButton.ptr_], rbx
0x180347d3b  test    rbx, rbx
0x180347d3e  jnz     short loc_180347DA1
0x180347d40  lea     this, [rbp+icon]; this
0x180347d44  mov     [rbp+icon.ptr_], r12
0x180347d48  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180347d4d  mov     this, [rbp+element.ptr_]
0x180347d51  test    this, this
0x180347d54  jz      short loc_180347D6C
0x180347d56  mov     rax, [this]
0x180347d59  lea     r8, [rbp+icon]
0x180347d5d  lea     rdx, _GUID_2e914438_fd53_4b8d_858b_3644269f8e4d
0x180347d64  mov     rax, [rax]
0x180347d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347d6c  mov     rbx, [rbp+icon.ptr_]
0x180347d70  mov     [rbp+icon.ptr_], rbx
0x180347d74  test    rbx, rbx
0x180347d77  jnz     loc_180347F1D
0x180347d7d  mov     this, [rbp+element.ptr_]
0x180347d81  test    this, this
0x180347d84  jz      short loc_180347D96
0x180347d86  mov     [rbp+element.ptr_], r12
0x180347d8a  mov     rax, [this]
0x180347d8d  mov     rax, [rax+10h]
0x180347d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347d96  mov     rdi, [rbp+arg_0]
0x180347d9a  inc     esi
0x180347d9c  jmp     loc_180347CB9
0x180347da1  lea     this, [rbx-290h]; this
0x180347da8  mov     r9b, r15b; hasKeyboardAcceleratorText
0x180347dab  mov     r8b, r13b; hasToggleButtons
0x180347dae  mov     dl, r14b; hasIcons
0x180347db1  call    ?SetOverflowStyleParams@AppBarButton@DirectUI@@QEAAJ_N00@Z; DirectUI::AppBarButton::SetOverflowStyleParams(bool,bool,bool)
0x180347db6  mov     edi, eax
0x180347db8  test    eax, eax
0x180347dba  js      loc_180347E5A
0x180347dc0  mov     rax, [rbx]
0x180347dc3  mov     this, rbx
0x180347dc6  mov     rax, [rax+10h]
0x180347dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180347dcf  jmp     short loc_180347D7D
0x180347dd1  xor     eax, eax
0x180347dd3  jmp     short loc_180347E2E
0x180347dd5  mov     ecx, edi; failedFrameHR
0x180347dd7  call    OnFailure_2990_
0x180347ddc  mov     this, [rbp+acceleratorText._hstring]; string
0x180347de0  test    this, this
0x180347de3  jz      short loc_180347DEB
0x180347de5  call    cs:__imp_WindowsDeleteString
0x180347deb  mov     this, [rbp+icon.ptr_]
0x180347def  test    this, this
  ... truncated ...
```
