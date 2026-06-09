# DirectUI::AppBarButtonHelpers::UpdateToolTip<DirectUI::AppBarButton>(DirectUI::AppBarButton * const)

- ea: `0x1803859d4`
- end: `0x180385dd3`
- name: `??$UpdateToolTip@VAppBarButton@DirectUI@@@AppBarButtonHelpers@DirectUI@@SAJQEAVAppBarButton@1@@Z`
- size: `1023`
- prototype: `HRESULT __fastcall(DirectUI::AppBarButton *const button)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180385644`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x1800c41e0`
- `0x1800c4a74`
- `0x1800d4a38`
- `0x180101870`
- `0x1801df610`
- `0x1801e5458`
- `0x180348cfc`
- `0x1803839c0`
- `0x180384178`
- `0x1803859d4`
- `0x18069f6ac`
- `0x18076e110`
- `0x18076f220`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385a42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385a42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180385d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180385bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180385bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180385b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180385ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180385ad5`

## pseudocode

```c
__int64 __fastcall DirectUI::AppBarButtonHelpers::UpdateToolTip<DirectUI::AppBarButton>(
        DirectUI::AppBarButton *const button)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT KeyboardAcceleratorTextOverride; // eax
  HSTRING__ *hstring; // rbx
  const CDependencyProperty *DependencyPropertyByIndex; // rax
  HRESULT v7; // eax
  unsigned int v8; // edi
  HRESULT (__fastcall *get_Label)(Windows::UI::Xaml::Controls::IAppBarButton *, HSTRING__ **); // rdi
  HRESULT v11; // eax
  DirectUI::DXamlCore *Current; // rdi
  HRESULT LocalizedResourceString; // eax
  HRESULT v14; // r14d
  PCWSTR StringRawBuffer; // r14
  PCWSTR v16; // rax
  HSTRING__ *v17; // rsi
  PCWSTR v18; // rdi
  const wchar_t *v19; // rax
  HRESULT v20; // ecx
  unsigned __int64 v21; // rdx
  int v22; // eax
  HSTRING__ *v23; // rdi
  HRESULT v24; // eax
  IInspectable *ptr; // r14
  const CDependencyProperty *v26; // rax
  HRESULT v27; // eax
  IInspectable *v28; // rcx
  IInspectable *v29; // rcx
  unsigned __int8 useOverflowStyle[8]; // [rsp+30h] [rbp-D0h] BYREF
  ctl::ComPtr<IInspectable> boxedToolTipString; // [rsp+38h] [rbp-C8h] BYREF
  Windows::Internal::String labelText; // [rsp+40h] [rbp-C0h] BYREF
  Windows::Internal::String toolTipString; // [rsp+48h] [rbp-B8h] BYREF
  Windows::Internal::String keyboardAcceleratorText; // [rsp+50h] [rbp-B0h] BYREF
  Windows::Internal::String toolTipFormatString; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t buffer[1024]; // [rsp+70h] [rbp-90h] BYREF

  if ( !button->m_ownsToolTip )
    return 0;
  useOverflowStyle[0] = 0;
  v2 = button->get_UseOverflowStyle(&button->Windows::UI::Xaml::Controls::ICommandBarOverflowElement, useOverflowStyle);
  v3 = v2;
  if ( v2 < 0 )
  {
    OnFailure_2990_(v2);
    return v3;
  }
  WindowsDeleteString(0);
  keyboardAcceleratorText._hstring = 0;
  KeyboardAcceleratorTextOverride = DirectUI::AppBarButtonGenerated::get_KeyboardAcceleratorTextOverride(
                                      button,
                                      &keyboardAcceleratorText._hstring);
  v3 = KeyboardAcceleratorTextOverride;
  if ( KeyboardAcceleratorTextOverride < 0 )
  {
    OnFailure_2990_(KeyboardAcceleratorTextOverride);
    if ( keyboardAcceleratorText._hstring )
      WindowsDeleteString(keyboardAcceleratorText._hstring);
    return v3;
  }
  hstring = keyboardAcceleratorText._hstring;
  if ( useOverflowStyle[0] || WindowsIsStringEmpty(keyboardAcceleratorText._hstring) )
  {
    DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ToolTipService_ToolTip);
    v7 = DirectUI::DependencyObject::ClearValue(button, DependencyPropertyByIndex);
    v8 = v7;
    if ( v7 >= 0 )
    {
LABEL_6:
      button->m_ownsToolTip = 1;
      if ( hstring )
        WindowsDeleteString(hstring);
      return 0;
    }
    OnFailure_2990_(v7);
  }
  else
  {
    labelText._hstring = 0;
    get_Label = button->get_Label;
    WindowsDeleteString(0);
    labelText._hstring = 0;
    v11 = get_Label(&button->Windows::UI::Xaml::Controls::IAppBarButton, &labelText._hstring);
    v8 = v11;
    if ( v11 >= 0 )
    {
      Current = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      toolTipFormatString._hstring = 0;
      LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                  Current,
                                  0x1428u,
                                  &toolTipFormatString._hstring);
      v14 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
      {
        OnFailure_2990_(LocalizedResourceString);
        goto LABEL_33;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(hstring, 0);
      v16 = WindowsGetStringRawBuffer(labelText._hstring, 0);
      v17 = toolTipFormatString._hstring;
      v18 = v16;
      v19 = WindowsGetStringRawBuffer(toolTipFormatString._hstring, 0);
      if ( swprintf_s(buffer, 0x400u, v19, v18, StringRawBuffer) < 0 )
      {
        OnNewFailure_2955_(v20);
        v14 = -2147418113;
        goto LABEL_33;
      }
      toolTipString._hstring = 0;
      string = 0;
      v21 = -1;
      do
        ++v21;
      while ( buffer[v21] );
      if ( v21 > 0xFFFFFFFF )
      {
        v14 = -2147024362;
      }
      else
      {
        v22 = WindowsCreateString(buffer, v21, &string);
        v14 = v22;
        if ( v22 >= 0 )
        {
          v14 = Windows::Internal::String::FreeAndAssignOnSuccess(v22, string, &toolTipString._hstring);
          if ( v14 >= 0 )
          {
            boxedToolTipString.ptr_ = 0;
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipString);
            v23 = toolTipString._hstring;
            v24 = DirectUI::PropertyValue::CreateFromString(toolTipString._hstring, &boxedToolTipString.ptr_);
            v14 = v24;
            if ( v24 >= 0 )
            {
              ptr = boxedToolTipString.ptr_;
              v26 = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ToolTipService_ToolTip);
              v27 = DirectUI::DependencyObject::SetValue(button, v26, ptr);
              v14 = v27;
              if ( v27 >= 0 )
              {
                v28 = boxedToolTipString.ptr_;
                if ( boxedToolTipString.ptr_ )
                {
                  boxedToolTipString.ptr_ = 0;
                  v28->Release(v28);
                }
                if ( v23 )
                  WindowsDeleteString(v23);
                if ( v17 )
                  WindowsDeleteString(v17);
                if ( labelText._hstring )
                  WindowsDeleteString(labelText._hstring);
                goto LABEL_6;
              }
              OnFailure_2990_(v27);
              v29 = boxedToolTipString.ptr_;
              if ( boxedToolTipString.ptr_ )
              {
                boxedToolTipString.ptr_ = 0;
                v29->Release(v29);
              }
              if ( v23 )
                WindowsDeleteString(v23);
              if ( v17 )
                WindowsDeleteString(v17);
              if ( labelText._hstring )
                WindowsDeleteString(labelText._hstring);
              if ( hstring )
                WindowsDeleteString(hstring);
              return (unsigned int)v14;
            }
            OnFailure_2990_(v24);
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipString);
            goto LABEL_32;
          }
        }
      }
      OnFailure_2990_(v14);
LABEL_32:
      Windows::Internal::String::~String(&toolTipString);
LABEL_33:
      Windows::Internal::String::~String(&toolTipFormatString);
      Windows::Internal::String::~String(&labelText);
      Windows::Internal::String::~String(&keyboardAcceleratorText);
      return (unsigned int)v14;
    }
    OnFailure_2990_(v11);
    if ( labelText._hstring )
      WindowsDeleteString(labelText._hstring);
  }
  if ( hstring )
    WindowsDeleteString(hstring);
  return v8;
}

```

## disassembly

```asm
0x1803859d4  mov     [rsp-8+arg_8], rbx
0x1803859d9  mov     [rsp-8+arg_10], rsi
0x1803859de  push    rbp
0x1803859df  push    rdi
0x1803859e0  push    r12
0x1803859e2  push    r14
0x1803859e4  push    r15
0x1803859e6  lea     rbp, [rsp-780h]
0x1803859ee  sub     rsp, 880h
0x1803859f5  mov     rax, cs:__security_cookie
0x1803859fc  xor     rax, rsp
0x1803859ff  mov     [rbp+7A0h+var_30], rax
0x180385a06  xor     r12d, r12d
0x180385a09  mov     r15, button
0x180385a0c  cmp     [button+348h], r12b
0x180385a13  jz      loc_180385AA5
0x180385a19  add     button, 2A0h
0x180385a20  mov     [rsp+8A0h+useOverflowStyle], r12b
0x180385a25  lea     rdx, [rsp+8A0h+useOverflowStyle]
0x180385a2a  mov     rax, [button]
0x180385a2d  mov     rax, [rax+30h]
0x180385a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180385a36  mov     ebx, eax
0x180385a38  test    eax, eax
0x180385a3a  js      loc_180385CA1
0x180385a40  xor     ecx, ecx; string
0x180385a42  call    cs:__imp_WindowsDeleteString
0x180385a48  lea     rdx, [rsp+8A0h+keyboardAcceleratorText]; pValue
0x180385a4d  mov     [rsp+8A0h+keyboardAcceleratorText._hstring], r12
0x180385a52  mov     button, r15; this
0x180385a55  call    ?get_KeyboardAcceleratorTextOverride@AppBarButtonGenerated@DirectUI@@QEAAJPEAPEAUHSTRING__@@@Z; DirectUI::AppBarButtonGenerated::get_KeyboardAcceleratorTextOverride(HSTRING__ * *)
0x180385a5a  mov     ebx, eax
0x180385a5c  test    eax, eax
0x180385a5e  js      loc_180385D81
0x180385a64  mov     rbx, [rsp+8A0h+keyboardAcceleratorText._hstring]
0x180385a69  cmp     [rsp+8A0h+useOverflowStyle], r12b
0x180385a6e  jz      short loc_180385AD2
0x180385a70  mov     ecx, 3Bh ; ';'; ePropertyIndex
0x180385a75  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x180385a7a  mov     rdx, rax; pDP
0x180385a7d  mov     button, r15; this
0x180385a80  call    ?ClearValue@DependencyObject@DirectUI@@QEAAJPEBVCDependencyProperty@@@Z; DirectUI::DependencyObject::ClearValue(CDependencyProperty const *)
0x180385a85  mov     edi, eax
0x180385a87  test    eax, eax
0x180385a89  js      loc_180385D4C
0x180385a8f  mov     byte ptr [r15+348h], 1
0x180385a97  test    rbx, rbx
0x180385a9a  jz      short loc_180385AA5
0x180385a9c  mov     button, rbx; string
0x180385a9f  call    cs:__imp_WindowsDeleteString
0x180385aa5  xor     eax, eax
0x180385aa7  mov     button, [rbp+7A0h+var_30]
0x180385aae  xor     button, rsp; StackCookie
0x180385ab1  call    __security_check_cookie
0x180385ab6  lea     r11, [rsp+8A0h+var_20]
0x180385abe  mov     rbx, [r11+38h]
0x180385ac2  mov     rsi, [r11+40h]
0x180385ac6  mov     rsp, r11
0x180385ac9  pop     r15
0x180385acb  pop     r14
0x180385acd  pop     r12
0x180385acf  pop     rdi
0x180385ad0  pop     rbp
0x180385ad1  retn
0x180385ad2  mov     button, rbx; string
0x180385ad5  call    cs:__imp_WindowsIsStringEmpty
0x180385adb  test    eax, eax
0x180385add  jnz     short loc_180385A70
0x180385adf  lea     rsi, [r15+290h]
0x180385ae6  mov     [rsp+8A0h+labelText._hstring], r12
0x180385aeb  mov     rax, [rsi]
0x180385aee  xor     ecx, ecx; string
0x180385af0  mov     rdi, [rax+30h]
0x180385af4  call    cs:__imp_WindowsDeleteString
0x180385afa  lea     rdx, [rsp+8A0h+labelText]
0x180385aff  mov     [rsp+8A0h+labelText._hstring], r12
0x180385b04  mov     button, rsi
0x180385b07  mov     rax, rdi
0x180385b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180385b0f  mov     edi, eax
0x180385b11  test    eax, eax
0x180385b13  js      loc_180385D68
0x180385b19  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180385b1e  xor     ecx, ecx; string
0x180385b20  mov     rdi, rax
0x180385b23  call    cs:__imp_WindowsDeleteString
0x180385b29  lea     r8, [rsp+8A0h+toolTipFormatString]; resourceString
0x180385b2e  mov     [rsp+8A0h+toolTipFormatString._hstring], r12
0x180385b33  mov     edx, 1428h; resourceStringID
0x180385b38  mov     button, rdi; this
0x180385b3b  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180385b40  mov     r14d, eax
0x180385b43  test    eax, eax
0x180385b45  js      loc_180385DC7
0x180385b4b  xor     edx, edx; length
0x180385b4d  mov     button, rbx; string
0x180385b50  call    cs:__imp_WindowsGetStringRawBuffer
0x180385b56  mov     button, [rsp+8A0h+labelText._hstring]; string
0x180385b5b  xor     edx, edx; length
0x180385b5d  mov     r14, rax
0x180385b60  call    cs:__imp_WindowsGetStringRawBuffer
0x180385b66  mov     rsi, [rsp+8A0h+toolTipFormatString._hstring]
0x180385b6b  xor     edx, edx; length
0x180385b6d  mov     button, rsi; string
0x180385b70  mov     rdi, rax
0x180385b73  call    cs:__imp_WindowsGetStringRawBuffer
0x180385b79  mov     r9, rdi
0x180385b7c  mov     [rsp+8A0h+var_880], r14
0x180385b81  mov     r8, rax; _Format
0x180385b84  lea     button, [rsp+8A0h+buffer]; _Buffer
0x180385b89  mov     edx, 400h; _BufferCount
0x180385b8e  call    swprintf_s
0x180385b93  test    eax, eax
0x180385b95  js      loc_180385DB7
0x180385b9b  mov     [rsp+8A0h+toolTipString._hstring], r12
0x180385ba0  lea     rax, [rsp+8A0h+buffer]
0x180385ba5  mov     [rsp+8A0h+string], r12
0x180385baa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180385bae  inc     rdx; length
0x180385bb1  cmp     [rax+rdx*2], r12w
0x180385bb6  jnz     short loc_180385BAE
0x180385bb8  mov     eax, 0FFFFFFFFh
0x180385bbd  cmp     rdx, rax
0x180385bc0  ja      loc_180385CAF
0x180385bc6  lea     r8, [rsp+8A0h+string]; string
0x180385bcb  lea     button, [rsp+8A0h+buffer]; sourceString
0x180385bd0  call    cs:__imp_WindowsCreateString
0x180385bd6  mov     r14d, eax
0x180385bd9  test    eax, eax
0x180385bdb  js      loc_180385CB5
0x180385be1  mov     rdx, [rsp+8A0h+string]; newValue
0x180385be6  lea     r8, [rsp+8A0h+toolTipString]; target
0x180385beb  mov     ecx, eax; hr
0x180385bed  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180385bf2  mov     r14d, eax
0x180385bf5  test    eax, eax
0x180385bf7  js      loc_180385CB5
0x180385bfd  lea     button, [rsp+8A0h+boxedToolTipString]; this
0x180385c02  mov     [rsp+8A0h+boxedToolTipString.ptr_], r12
0x180385c07  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180385c0c  mov     rdi, [rsp+8A0h+toolTipString._hstring]
0x180385c11  lea     rdx, [rsp+8A0h+boxedToolTipString]; ppValue
0x180385c16  mov     button, rdi; hString
0x180385c19  call    ?CreateFromString@PropertyValue@DirectUI@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; DirectUI::PropertyValue::CreateFromString(HSTRING__ *,IInspectable * *)
0x180385c1e  mov     r14d, eax
0x180385c21  test    eax, eax
0x180385c23  js      loc_180385DA1
0x180385c29  mov     r14, [rsp+8A0h+boxedToolTipString.ptr_]
0x180385c2e  mov     ecx, 3Bh ; ';'; ePropertyIndex
0x180385c33  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x180385c38  mov     r8, r14; pValue
0x180385c3b  mov     rdx, rax; pDP
0x180385c3e  mov     button, r15; this
0x180385c41  call    ?SetValue@DependencyObject@DirectUI@@QEAAJPEBVCDependencyProperty@@PEAUIInspectable@@@Z; DirectUI::DependencyObject::SetValue(CDependencyProperty const *,IInspectable *)
0x180385c46  mov     r14d, eax
0x180385c49  test    eax, eax
0x180385c4b  js      loc_180385CED
0x180385c51  mov     button, [rsp+8A0h+boxedToolTipString.ptr_]
0x180385c56  test    button, button
0x180385c59  jz      short loc_180385C6C
0x180385c5b  mov     [rsp+8A0h+boxedToolTipString.ptr_], r12
0x180385c60  mov     rax, [button]
0x180385c63  mov     rax, [rax+10h]
0x180385c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180385c6c  test    rdi, rdi
0x180385c6f  jz      short loc_180385C7A
0x180385c71  mov     button, rdi; string
0x180385c74  call    cs:__imp_WindowsDeleteString
0x180385c7a  test    rsi, rsi
0x180385c7d  jz      short loc_180385C88
0x180385c7f  mov     button, rsi; string
0x180385c82  call    cs:__imp_WindowsDeleteString
0x180385c88  mov     button, [rsp+8A0h+labelText._hstring]; string
0x180385c8d  test    button, button
0x180385c90  jz      loc_180385A8F
0x180385c96  call    cs:__imp_WindowsDeleteString
0x180385c9c  jmp     loc_180385A8F
0x180385ca1  mov     ecx, ebx; failedFrameHR
0x180385ca3  call    OnFailure_2990_
0x180385ca8  mov     eax, ebx
0x180385caa  jmp     loc_180385AA7
0x180385caf  mov     r14d, 80070216h
0x180385cb5  mov     ecx, r14d; failedFrameHR
0x180385cb8  call    OnFailure_2990_
0x180385cbd  lea     button, [rsp+8A0h+toolTipString]; this
0x180385cc2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180385cc7  lea     button, [rsp+8A0h+toolTipFormatString]; this
0x180385ccc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180385cd1  lea     button, [rsp+8A0h+labelText]; this
0x180385cd6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180385cdb  lea     button, [rsp+8A0h+keyboardAcceleratorText]; this
0x180385ce0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180385ce5  mov     eax, r14d
0x180385ce8  jmp     loc_180385AA7
0x180385ced  mov     ecx, r14d; failedFrameHR
0x180385cf0  call    OnFailure_2990_
0x180385cf5  mov     button, [rsp+8A0h+boxedToolTipString.ptr_]
0x180385cfa  test    button, button
0x180385cfd  jz      short loc_180385D10
0x180385cff  mov     [rsp+8A0h+boxedToolTipString.ptr_], r12
0x180385d04  mov     rax, [button]
0x180385d07  mov     rax, [rax+10h]
0x180385d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180385d10  test    rdi, rdi
0x180385d13  jz      short loc_180385D1E
0x180385d15  mov     button, rdi; string
0x180385d18  call    cs:__imp_WindowsDeleteString
0x180385d1e  test    rsi, rsi
0x180385d21  jz      short loc_180385D2C
0x180385d23  mov     button, rsi; string
0x180385d26  call    cs:__imp_WindowsDeleteString
0x180385d2c  mov     button, [rsp+8A0h+labelText._hstring]; string
0x180385d31  test    button, button
0x180385d34  jz      short loc_180385D3C
0x180385d36  call    cs:__imp_WindowsDeleteString
0x180385d3c  test    rbx, rbx
0x180385d3f  jz      short loc_180385CE5
0x180385d41  mov     button, rbx; string
0x180385d44  call    cs:__imp_WindowsDeleteString
0x180385d4a  jmp     short loc_180385CE5
0x180385d4c  mov     ecx, edi; failedFrameHR
0x180385d4e  call    OnFailure_2990_
0x180385d53  test    rbx, rbx
0x180385d56  jz      short loc_180385D61
0x180385d58  mov     button, rbx; string
0x180385d5b  call    cs:__imp_WindowsDeleteString
0x180385d61  mov     eax, edi
0x180385d63  jmp     loc_180385AA7
0x180385d68  mov     ecx, edi; failedFrameHR
0x180385d6a  call    OnFailure_2990_
0x180385d6f  mov     button, [rsp+8A0h+labelText._hstring]; string
0x180385d74  test    button, button
0x180385d77  jz      short loc_180385D53
0x180385d79  call    cs:__imp_WindowsDeleteString
0x180385d7f  jmp     short loc_180385D53
0x180385d81  mov     ecx, ebx; failedFrameHR
0x180385d83  call    OnFailure_2990_
0x180385d88  mov     button, [rsp+8A0h+keyboardAcceleratorText._hstring]; string
0x180385d8d  test    button, button
0x180385d90  jz      loc_180385CA8
0x180385d96  call    cs:__imp_WindowsDeleteString
0x180385d9c  jmp     loc_180385CA8
0x180385da1  mov     ecx, eax; failedFrameHR
0x180385da3  call    OnFailure_2990_
0x180385da8  lea     button, [rsp+8A0h+boxedToolTipString]; this
0x180385dad  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180385db2  jmp     loc_180385CBD
0x180385db7  call    OnNewFailure_2955_
0x180385dbc  mov     r14d, 8000FFFFh
0x180385dc2  jmp     loc_180385CC7
0x180385dc7  mov     ecx, eax; failedFrameHR
0x180385dc9  call    OnFailure_2990_
0x180385dce  jmp     loc_180385CC7
```
