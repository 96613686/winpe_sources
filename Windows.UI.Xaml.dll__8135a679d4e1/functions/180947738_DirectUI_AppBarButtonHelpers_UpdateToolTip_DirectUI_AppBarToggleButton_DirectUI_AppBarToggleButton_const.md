# DirectUI::AppBarButtonHelpers::UpdateToolTip<DirectUI::AppBarToggleButton>(DirectUI::AppBarToggleButton * const)

- ea: `0x180947738`
- end: `0x180947a22`
- name: `??$UpdateToolTip@VAppBarToggleButton@DirectUI@@@AppBarButtonHelpers@DirectUI@@SAJQEAVAppBarToggleButton@1@@Z`
- size: `746`
- prototype: `HRESULT __fastcall(DirectUI::AppBarToggleButton *const button)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18070a948`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x1800c41e0`
- `0x1800c4a74`
- `0x1800d4a38`
- `0x180101870`
- `0x1801df610`
- `0x1801e5458`
- `0x1803839c0`
- `0x1804d63a8`
- `0x18069f6ac`
- `0x18076e110`
- `0x18076f220`
- `0x180947738`
- `0x180ab78dc`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18094779f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1809477f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180947826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18094779f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1809477f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180947826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180947878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1809477cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1809477cc`

## pseudocode

```c
__int64 __fastcall DirectUI::AppBarButtonHelpers::UpdateToolTip<DirectUI::AppBarToggleButton>(
        DirectUI::AppBarToggleButton *const button)
{
  HRESULT KeyboardAcceleratorTextOverride; // eax
  unsigned int v3; // ebx
  HRESULT (__fastcall *get_Label)(Windows::UI::Xaml::Controls::IAppBarToggleButton *, HSTRING__ **); // rbx
  HRESULT v5; // eax
  DirectUI::DXamlCore *Current; // rbx
  HRESULT LocalizedResourceString; // eax
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v9; // rbx
  const wchar_t *v10; // rax
  HRESULT v11; // ecx
  HRESULT v12; // eax
  HRESULT v13; // eax
  IInspectable *ptr; // rbx
  const CDependencyProperty *v15; // rax
  const CDependencyProperty *DependencyPropertyByIndex; // rax
  unsigned __int8 useOverflowStyle[8]; // [rsp+30h] [rbp-D0h] BYREF
  Windows::Internal::String labelText; // [rsp+38h] [rbp-C8h] BYREF
  Windows::Internal::String toolTipFormatString; // [rsp+40h] [rbp-C0h] BYREF
  ctl::ComPtr<IInspectable> boxedToolTipString; // [rsp+48h] [rbp-B8h] BYREF
  Windows::Internal::String toolTipString; // [rsp+50h] [rbp-B0h] BYREF
  Windows::Internal::String keyboardAcceleratorText; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !button->m_ownsToolTip )
    return 0;
  useOverflowStyle[0] = 0;
  keyboardAcceleratorText._hstring = 0;
  KeyboardAcceleratorTextOverride = button->get_UseOverflowStyle(
                                      &button->Windows::UI::Xaml::Controls::ICommandBarOverflowElement,
                                      useOverflowStyle);
  v3 = KeyboardAcceleratorTextOverride;
  if ( KeyboardAcceleratorTextOverride < 0
    || (WindowsDeleteString(0),
        KeyboardAcceleratorTextOverride = DirectUI::AppBarToggleButtonGenerated::get_KeyboardAcceleratorTextOverride(
                                            button,
                                            &keyboardAcceleratorText._hstring),
        v3 = KeyboardAcceleratorTextOverride,
        KeyboardAcceleratorTextOverride < 0) )
  {
LABEL_24:
    OnFailure_2990_(KeyboardAcceleratorTextOverride);
    goto LABEL_25;
  }
  if ( useOverflowStyle[0] || WindowsIsStringEmpty(keyboardAcceleratorText._hstring) )
  {
    DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ToolTipService_ToolTip);
    KeyboardAcceleratorTextOverride = DirectUI::DependencyObject::ClearValue(button, DependencyPropertyByIndex);
    v3 = KeyboardAcceleratorTextOverride;
    if ( KeyboardAcceleratorTextOverride >= 0 )
      goto LABEL_22;
    goto LABEL_24;
  }
  labelText._hstring = 0;
  get_Label = button->get_Label;
  WindowsDeleteString(0);
  labelText._hstring = 0;
  v5 = get_Label(&button->Windows::UI::Xaml::Controls::IAppBarToggleButton, &labelText._hstring);
  v3 = v5;
  if ( v5 < 0 )
  {
    OnFailure_2990_(v5);
    goto LABEL_20;
  }
  Current = DirectUI::DXamlCore::GetCurrent();
  WindowsDeleteString(0);
  toolTipFormatString._hstring = 0;
  LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                              Current,
                              0x1428u,
                              &toolTipFormatString._hstring);
  v3 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
  {
    OnFailure_2990_(LocalizedResourceString);
LABEL_18:
    Windows::Internal::String::~String(&toolTipFormatString);
LABEL_20:
    Windows::Internal::String::~String(&labelText);
    goto LABEL_25;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(keyboardAcceleratorText._hstring, 0);
  v9 = WindowsGetStringRawBuffer(labelText._hstring, 0);
  v10 = WindowsGetStringRawBuffer(toolTipFormatString._hstring, 0);
  if ( swprintf_s(buffer, 0x400u, v10, v9, StringRawBuffer) >= 0 )
  {
    toolTipString._hstring = 0;
    v12 = Windows::Internal::String::_InitializeHelper(&toolTipString, buffer);
    v3 = v12;
    if ( v12 < 0 )
    {
      OnFailure_2990_(v12);
    }
    else
    {
      boxedToolTipString.ptr_ = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipString);
      v13 = DirectUI::PropertyValue::CreateFromString(toolTipString._hstring, &boxedToolTipString.ptr_);
      v3 = v13;
      if ( v13 >= 0 )
      {
        ptr = boxedToolTipString.ptr_;
        v15 = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ToolTipService_ToolTip);
        v13 = DirectUI::DependencyObject::SetValue(button, v15, ptr);
        v3 = v13;
        if ( v13 >= 0 )
        {
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipString);
          Windows::Internal::String::~String(&toolTipString);
          Windows::Internal::String::~String(&toolTipFormatString);
          Windows::Internal::String::~String(&labelText);
LABEL_22:
          button->m_ownsToolTip = 1;
          Windows::Internal::String::~String(&keyboardAcceleratorText);
          return 0;
        }
      }
      OnFailure_2990_(v13);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipString);
    }
    Windows::Internal::String::~String(&toolTipString);
    goto LABEL_18;
  }
  OnNewFailure_2955_(v11);
  Windows::Internal::String::~String(&toolTipFormatString);
  Windows::Internal::String::~String(&labelText);
  v3 = -2147418113;
LABEL_25:
  Windows::Internal::String::~String(&keyboardAcceleratorText);
  return v3;
}

```

## disassembly

```asm
0x180947738  push    rbp
0x18094773a  push    rbx
0x18094773b  push    rsi
0x18094773c  push    rdi
0x18094773d  lea     rbp, [rsp-778h]
0x180947745  sub     rsp, 878h
0x18094774c  mov     rax, cs:__security_cookie
0x180947753  xor     rax, rsp
0x180947756  mov     [rbp+790h+var_30], rax
0x18094775d  cmp     byte ptr [button+338h], 0
0x180947764  mov     rsi, button
0x180947767  jz      loc_1809479DE
0x18094776d  add     button, 2A0h
0x180947774  mov     [rsp+890h+useOverflowStyle], 0
0x180947779  lea     rdx, [rsp+890h+useOverflowStyle]
0x18094777e  mov     [rsp+890h+keyboardAcceleratorText._hstring], 0
0x180947787  mov     rax, [button]
0x18094778a  mov     rax, [rax+30h]
0x18094778e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180947793  mov     ebx, eax
0x180947795  test    eax, eax
0x180947797  js      loc_180947A0D
0x18094779d  xor     ecx, ecx; string
0x18094779f  call    cs:__imp_WindowsDeleteString
0x1809477a5  lea     rdx, [rsp+890h+keyboardAcceleratorText]; pValue
0x1809477aa  mov     button, rsi; this
0x1809477ad  call    ?get_KeyboardAcceleratorTextOverride@AppBarToggleButtonGenerated@DirectUI@@QEAAJPEAPEAUHSTRING__@@@Z; DirectUI::AppBarToggleButtonGenerated::get_KeyboardAcceleratorTextOverride(HSTRING__ * *)
0x1809477b2  mov     ebx, eax
0x1809477b4  test    eax, eax
0x1809477b6  js      loc_180947A04
0x1809477bc  cmp     [rsp+890h+useOverflowStyle], 0
0x1809477c1  jnz     loc_1809479B2
0x1809477c7  mov     button, [rsp+890h+keyboardAcceleratorText._hstring]; string
0x1809477cc  call    cs:__imp_WindowsIsStringEmpty
0x1809477d2  test    eax, eax
0x1809477d4  jnz     loc_1809479B2
0x1809477da  lea     rdi, [rsi+290h]
0x1809477e1  mov     [rsp+890h+labelText._hstring], 0
0x1809477ea  mov     rax, [rdi]
0x1809477ed  xor     ecx, ecx; string
0x1809477ef  mov     rbx, [rax+30h]
0x1809477f3  call    cs:__imp_WindowsDeleteString
0x1809477f9  lea     rdx, [rsp+890h+labelText]
0x1809477fe  mov     [rsp+890h+labelText._hstring], 0
0x180947807  mov     button, rdi
0x18094780a  mov     rax, rbx
0x18094780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180947812  mov     ebx, eax
0x180947814  test    eax, eax
0x180947816  js      loc_18094799F
0x18094781c  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180947821  xor     ecx, ecx; string
0x180947823  mov     rbx, rax
0x180947826  call    cs:__imp_WindowsDeleteString
0x18094782c  lea     r8, [rsp+890h+toolTipFormatString]; resourceString
0x180947831  mov     [rsp+890h+toolTipFormatString._hstring], 0
0x18094783a  mov     edx, 1428h; resourceStringID
0x18094783f  mov     button, rbx; this
0x180947842  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180947847  mov     ebx, eax
0x180947849  test    eax, eax
0x18094784b  js      loc_18094798C
0x180947851  mov     button, [rsp+890h+keyboardAcceleratorText._hstring]; string
0x180947856  xor     edx, edx; length
0x180947858  call    cs:__imp_WindowsGetStringRawBuffer
0x18094785e  mov     button, [rsp+890h+labelText._hstring]; string
0x180947863  xor     edx, edx; length
0x180947865  mov     rdi, rax
0x180947868  call    cs:__imp_WindowsGetStringRawBuffer
0x18094786e  mov     button, [rsp+890h+toolTipFormatString._hstring]; string
0x180947873  xor     edx, edx; length
0x180947875  mov     rbx, rax
0x180947878  call    cs:__imp_WindowsGetStringRawBuffer
0x18094787e  mov     r9, rbx
0x180947881  mov     [rsp+890h+var_870], rdi
0x180947886  mov     r8, rax; _Format
0x180947889  lea     button, [rsp+890h+buffer]; _Buffer
0x18094788e  mov     edx, 400h; _BufferCount
0x180947893  call    swprintf_s
0x180947898  test    eax, eax
0x18094789a  js      loc_180947969
0x1809478a0  lea     rdx, [rsp+890h+buffer]; str
0x1809478a5  mov     [rsp+890h+toolTipString._hstring], 0
0x1809478ae  lea     button, [rsp+890h+toolTipString]; this
0x1809478b3  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1809478b8  mov     ebx, eax
0x1809478ba  test    eax, eax
0x1809478bc  js      loc_180947956
0x1809478c2  lea     button, [rsp+890h+boxedToolTipString]; this
0x1809478c7  mov     [rsp+890h+boxedToolTipString.ptr_], 0
0x1809478d0  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809478d5  mov     button, [rsp+890h+toolTipString._hstring]; hString
0x1809478da  lea     rdx, [rsp+890h+boxedToolTipString]; ppValue
0x1809478df  call    ?CreateFromString@PropertyValue@DirectUI@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; DirectUI::PropertyValue::CreateFromString(HSTRING__ *,IInspectable * *)
0x1809478e4  mov     ebx, eax
0x1809478e6  test    eax, eax
0x1809478e8  js      short loc_180947943
0x1809478ea  mov     rbx, [rsp+890h+boxedToolTipString.ptr_]
0x1809478ef  mov     ecx, 3Bh ; ';'; ePropertyIndex
0x1809478f4  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x1809478f9  mov     r8, rbx; pValue
0x1809478fc  mov     rdx, rax; pDP
0x1809478ff  mov     button, rsi; this
0x180947902  call    ?SetValue@DependencyObject@DirectUI@@QEAAJPEBVCDependencyProperty@@PEAUIInspectable@@@Z; DirectUI::DependencyObject::SetValue(CDependencyProperty const *,IInspectable *)
0x180947907  mov     ebx, eax
0x180947909  test    eax, eax
0x18094790b  js      short loc_18094793A
0x18094790d  lea     button, [rsp+890h+boxedToolTipString]; this
0x180947912  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180947917  lea     button, [rsp+890h+toolTipString]; this
0x18094791c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947921  lea     button, [rsp+890h+toolTipFormatString]; this
0x180947926  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18094792b  lea     button, [rsp+890h+labelText]; this
0x180947930  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947935  jmp     loc_1809479CD
0x18094793a  mov     ecx, eax; failedFrameHR
0x18094793c  call    OnFailure_2990_
0x180947941  jmp     short loc_18094794A
0x180947943  mov     ecx, eax; failedFrameHR
0x180947945  call    OnFailure_2990_
0x18094794a  lea     button, [rsp+890h+boxedToolTipString]; this
0x18094794f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180947954  jmp     short loc_18094795D
0x180947956  mov     ecx, eax; failedFrameHR
0x180947958  call    OnFailure_2990_
0x18094795d  lea     button, [rsp+890h+toolTipString]; this
0x180947962  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947967  jmp     short loc_180947993
0x180947969  call    OnNewFailure_2955_
0x18094796e  lea     button, [rsp+890h+toolTipFormatString]; this
0x180947973  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947978  lea     button, [rsp+890h+labelText]; this
0x18094797d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947982  mov     ebx, 8000FFFFh
0x180947987  jmp     loc_180947A14
0x18094798c  mov     ecx, eax; failedFrameHR
0x18094798e  call    OnFailure_2990_
0x180947993  lea     button, [rsp+890h+toolTipFormatString]; this
0x180947998  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18094799d  jmp     short loc_1809479A6
0x18094799f  mov     ecx, eax; failedFrameHR
0x1809479a1  call    OnFailure_2990_
0x1809479a6  lea     button, [rsp+890h+labelText]; this
0x1809479ab  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1809479b0  jmp     short loc_180947A14
0x1809479b2  mov     ecx, 3Bh ; ';'; ePropertyIndex
0x1809479b7  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x1809479bc  mov     rdx, rax; pDP
0x1809479bf  mov     button, rsi; this
0x1809479c2  call    ?ClearValue@DependencyObject@DirectUI@@QEAAJPEBVCDependencyProperty@@@Z; DirectUI::DependencyObject::ClearValue(CDependencyProperty const *)
0x1809479c7  mov     ebx, eax
0x1809479c9  test    eax, eax
0x1809479cb  js      short loc_1809479FB
0x1809479cd  lea     button, [rsp+890h+keyboardAcceleratorText]; this
0x1809479d2  mov     byte ptr [rsi+338h], 1
0x1809479d9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1809479de  xor     eax, eax
0x1809479e0  mov     button, [rbp+790h+var_30]
0x1809479e7  xor     button, rsp; StackCookie
0x1809479ea  call    __security_check_cookie
0x1809479ef  add     rsp, 878h
0x1809479f6  pop     rdi
0x1809479f7  pop     rsi
0x1809479f8  pop     rbx
0x1809479f9  pop     rbp
0x1809479fa  retn
0x1809479fb  mov     ecx, eax; failedFrameHR
0x1809479fd  call    OnFailure_2990_
0x180947a02  jmp     short loc_180947A14
0x180947a04  mov     ecx, eax; failedFrameHR
0x180947a06  call    OnFailure_2990_
0x180947a0b  jmp     short loc_180947A14
0x180947a0d  mov     ecx, eax; failedFrameHR
0x180947a0f  call    OnFailure_2990_
0x180947a14  lea     button, [rsp+890h+keyboardAcceleratorText]; this
0x180947a19  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180947a1e  mov     eax, ebx
0x180947a20  jmp     short loc_1809479E0
```
