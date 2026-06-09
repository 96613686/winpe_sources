# DirectUI::MediaTransportControls::UpdateTimeAutomationProperties(void)

- ea: `0x180387f7c`
- end: `0x180388381`
- name: `?UpdateTimeAutomationProperties@MediaTransportControls@DirectUI@@AEAAJXZ`
- size: `1029`
- prototype: `HRESULT __fastcall(DirectUI::MediaTransportControls *this)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180385f74`
- `0x18038b080`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005e96c`
- `0x1801df610`
- `0x1801e5458`
- `0x1803839c0`
- `0x180384178`
- `0x180386694`
- `0x1803871f0`
- `0x180387f7c`
- `0x18066dd50`
- `0x180701858`
- `0x18070b468`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18038808f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18038808f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180387fd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038803b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038815f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180388172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803881db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038825c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180388358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180387fd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038803b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038815f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180388172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803881db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038825c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180388358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803880a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803880a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180388078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180388078`

## pseudocode

```c
__int64 __fastcall DirectUI::MediaTransportControls::UpdateTimeAutomationProperties(
        DirectUI::MediaTransportControls *this)
{
  HSTRING__ *hstring; // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *p_m_tpTimeElapsedElement; // r14
  Windows::UI::Xaml::IFrameworkElement *m_value; // rcx
  DirectUI::DXamlCore *Current; // rbx
  HRESULT LocalizedResourceString; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  Windows::UI::Xaml::Controls::ITextBlock *ptr; // rdi
  HRESULT (__fastcall *get_Text)(Windows::UI::Xaml::Controls::ITextBlock *, HSTRING__ **); // rbx
  HRESULT v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // edi
  Windows::UI::Xaml::Controls::ITextBlock *v15; // rcx
  Windows::Internal::String *p_strTimeElapsedText; // rcx
  Windows::UI::Xaml::IFrameworkElement *v17; // rcx
  DirectUI::DXamlCore *v18; // rdi
  HRESULT v19; // eax
  Windows::UI::Xaml::Controls::ITextBlock *v20; // rdi
  HRESULT (__fastcall *v21)(Windows::UI::Xaml::Controls::ITextBlock *, HSTRING__ **); // rbx
  const Windows::Internal::String *v22; // rax
  Windows::Internal::String strAutomationName; // [rsp+20h] [rbp-50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spTimeRemainingTextBlock; // [rsp+28h] [rbp-48h] BYREF
  Windows::Internal::String strTimeElapsedText; // [rsp+30h] [rbp-40h] BYREF
  Windows::Internal::String strTimeRemainingText; // [rsp+38h] [rbp-38h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spTimeElapsedTextBlock; // [rsp+40h] [rbp-30h] BYREF
  Windows::Internal::StringReference string; // [rsp+48h] [rbp-28h] BYREF

  hstring = 0;
  p_m_tpTimeElapsedElement = &this->m_tpTimeElapsedElement;
  strAutomationName._hstring = 0;
  m_value = (Windows::UI::Xaml::IFrameworkElement *)this->m_tpTimeElapsedElement.m_trackerReference.m_value;
  if ( m_value && !ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(m_value) )
  {
    Current = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(0);
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                Current,
                                0x1486u,
                                &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_37;
    if ( (*((_BYTE *)this + 718) & 0x30) == 0x10 )
    {
      strTimeElapsedText._hstring = 0;
      spTimeElapsedTextBlock.ptr_ = 0;
      v8 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(
             p_m_tpTimeElapsedElement,
             (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> >)&spTimeElapsedTextBlock);
      v7 = v8;
      if ( v8 < 0 )
        goto LABEL_21;
      ptr = spTimeElapsedTextBlock.ptr_;
      get_Text = spTimeElapsedTextBlock.ptr_->get_Text;
      WindowsDeleteString(strTimeElapsedText._hstring);
      strTimeElapsedText._hstring = 0;
      v8 = get_Text(ptr, &strTimeElapsedText._hstring);
      v7 = v8;
      if ( v8 < 0 )
        goto LABEL_21;
      if ( WindowsCreateStringReference(L" ", 1u, &string._header, &string._hstring) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      spTimeRemainingTextBlock.ptr_ = 0;
      v11 = WindowsConcatString(strAutomationName._hstring, string._hstring, (HSTRING *)&spTimeRemainingTextBlock);
      v12 = Windows::Internal::String::FreeAndAssignOnSuccess(
              v11,
              (HSTRING__ *)spTimeRemainingTextBlock.ptr_,
              &strAutomationName._hstring);
      v7 = v12;
      if ( v12 < 0 )
      {
        OnFailure_2990_(v12);
        v15 = spTimeElapsedTextBlock.ptr_;
        if ( spTimeElapsedTextBlock.ptr_ )
        {
          spTimeElapsedTextBlock.ptr_ = 0;
          v15->Release(v15);
        }
        if ( strTimeElapsedText._hstring )
          WindowsDeleteString(strTimeElapsedText._hstring);
        if ( strAutomationName._hstring )
          WindowsDeleteString(strAutomationName._hstring);
        return v7;
      }
      v8 = Windows::Internal::String::Concat(&strAutomationName, &strTimeElapsedText, &strAutomationName);
      v7 = v8;
      if ( v8 < 0 )
      {
LABEL_21:
        OnFailure_2990_(v8);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimeElapsedTextBlock);
        p_strTimeElapsedText = &strTimeElapsedText;
        goto LABEL_22;
      }
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimeElapsedTextBlock);
      Windows::Internal::String::~String(&strTimeElapsedText);
    }
    hstring = strAutomationName._hstring;
    v13 = DirectUI::DependencyObject::SetValueByKnownIndex(
            (DirectUI::DependencyObject *)((__int64)&p_m_tpTimeElapsedElement->m_trackerReference.m_value[-44]
                                         & -(__int64)(p_m_tpTimeElapsedElement->m_trackerReference.m_value != 0)),
            AutomationProperties_Name,
            strAutomationName._hstring);
    v14 = v13;
    if ( v13 < 0 )
    {
LABEL_13:
      OnFailure_2990_(v13);
      v7 = v14;
LABEL_38:
      Windows::Internal::String::~String(&strAutomationName);
      return v7;
    }
  }
  v17 = (Windows::UI::Xaml::IFrameworkElement *)this->m_tpTimeRemainingElement.m_trackerReference.m_value;
  if ( !v17 || ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(v17) )
    goto LABEL_40;
  v18 = DirectUI::DXamlCore::GetCurrent();
  WindowsDeleteString(hstring);
  strAutomationName._hstring = 0;
  LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v18, 0x1488u, &strAutomationName._hstring);
  v7 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
  {
LABEL_37:
    OnFailure_2990_(LocalizedResourceString);
    goto LABEL_38;
  }
  if ( (*((_BYTE *)this + 718) & 0x30) == 0x10 && !DirectUI::MediaTransportControls::IsLiveContent(this) )
  {
    strTimeRemainingText._hstring = 0;
    spTimeRemainingTextBlock.ptr_ = 0;
    v19 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(
            &this->m_tpTimeRemainingElement,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> >)&spTimeRemainingTextBlock);
    v7 = v19;
    if ( v19 >= 0 )
    {
      v20 = spTimeRemainingTextBlock.ptr_;
      v21 = spTimeRemainingTextBlock.ptr_->get_Text;
      WindowsDeleteString(strTimeRemainingText._hstring);
      strTimeRemainingText._hstring = 0;
      v19 = v21(v20, &strTimeRemainingText._hstring);
      v7 = v19;
      if ( v19 >= 0 )
      {
        Windows::Internal::StringReference::StringReference(&string, (const wchar_t (*)[2])L" ");
        v19 = Windows::Internal::String::Concat(&strAutomationName, v22, &strAutomationName);
        v7 = v19;
        if ( v19 >= 0 )
        {
          v19 = Windows::Internal::String::Concat(&strAutomationName, &strTimeRemainingText, &strAutomationName);
          v7 = v19;
          if ( v19 >= 0 )
          {
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimeRemainingTextBlock);
            Windows::Internal::String::~String(&strTimeRemainingText);
            goto LABEL_34;
          }
        }
      }
    }
    OnFailure_2990_(v19);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTimeRemainingTextBlock);
    p_strTimeElapsedText = &strTimeRemainingText;
LABEL_22:
    Windows::Internal::String::~String(p_strTimeElapsedText);
    goto LABEL_38;
  }
LABEL_34:
  hstring = strAutomationName._hstring;
  v13 = DirectUI::DependencyObject::SetValueByKnownIndex(
          (DirectUI::DependencyObject *)((__int64)&this->m_tpTimeRemainingElement.m_trackerReference.m_value[-44]
                                       & -(__int64)(this->m_tpTimeRemainingElement.m_trackerReference.m_value != 0)),
          AutomationProperties_Name,
          strAutomationName._hstring);
  v14 = v13;
  if ( v13 < 0 )
    goto LABEL_13;
LABEL_40:
  if ( hstring )
    WindowsDeleteString(hstring);
  return 0;
}

```

## disassembly

```asm
0x180387f7c  mov     [rsp-18h+arg_8], rbx
0x180387f81  mov     [rsp-18h+arg_10], rsi
0x180387f86  push    rbp
0x180387f87  push    rdi
0x180387f88  push    r14
0x180387f8a  mov     rbp, rsp
0x180387f8d  sub     rsp, 70h
0x180387f91  mov     rax, cs:__security_cookie
0x180387f98  xor     rax, rsp
0x180387f9b  mov     [rbp+var_8], rax
0x180387f9f  xor     ebx, ebx
0x180387fa1  lea     r14, [this+5C0h]
0x180387fa8  mov     rsi, this
0x180387fab  mov     [rbp+strAutomationName._hstring], rbx
0x180387faf  mov     this, [r14]; pInterface
0x180387fb2  test    this, this
0x180387fb5  jz      loc_1803881B0
0x180387fbb  call    ??$is@UIContentControl@Controls@Xaml@UI@Windows@@UIFrameworkElement@345@@ctl@@YAIPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(Windows::UI::Xaml::IFrameworkElement *)
0x180387fc0  test    eax, eax
0x180387fc2  jnz     loc_1803881B0
0x180387fc8  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180387fcd  xor     ecx, ecx; string
0x180387fcf  mov     rbx, rax
0x180387fd2  call    cs:__imp_WindowsDeleteString
0x180387fd8  lea     r8, [rbp+strAutomationName]; resourceString
0x180387fdc  mov     edx, 1486h; resourceStringID
0x180387fe1  mov     this, rbx; this
0x180387fe4  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180387fe9  mov     ebx, eax
0x180387feb  test    eax, eax
0x180387fed  js      loc_1803881A4
0x180387ff3  mov     al, [rsi+2CEh]
0x180387ff9  and     al, 30h
0x180387ffb  cmp     al, 10h
0x180387ffd  jnz     loc_1803880ED
0x180388003  lea     rdx, [rbp+spTimeElapsedTextBlock]; p
0x180388007  mov     [rbp+strTimeElapsedText._hstring], 0
0x18038800f  mov     this, r14; this
0x180388012  mov     [rbp+spTimeElapsedTextBlock.ptr_], 0
0x18038801a  call    ??$As@UITextBlock@Controls@Xaml@UI@Windows@@@?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextBlock@Controls@Xaml@UI@Windows@@@ctl@@@Internal@ctl@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock>>)
0x18038801f  mov     ebx, eax
0x180388021  test    eax, eax
0x180388023  js      loc_180388186
0x180388029  mov     rdi, [rbp+spTimeElapsedTextBlock.ptr_]
0x18038802d  mov     this, [rbp+strTimeElapsedText._hstring]; string
0x180388031  mov     rax, [rdi]
0x180388034  mov     rbx, [rax+0D0h]
0x18038803b  call    cs:__imp_WindowsDeleteString
0x180388041  lea     rdx, [rbp+strTimeElapsedText]
0x180388045  mov     [rbp+strTimeElapsedText._hstring], 0
0x18038804d  mov     this, rdi
0x180388050  mov     rax, rbx
0x180388053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180388058  mov     ebx, eax
0x18038805a  test    eax, eax
0x18038805c  js      loc_18038817D
0x180388062  mov     ebx, 1
0x180388067  lea     r9, [rbp+string]; string
0x18038806b  mov     edx, ebx; length
0x18038806d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180388071  lea     this, source; " "
0x180388078  call    cs:__imp_WindowsCreateStringReference
0x18038807e  test    eax, eax
0x180388080  jns     short loc_180388095
0x180388082  xor     r9d, r9d; lpArguments
0x180388085  xor     r8d, r8d; nNumberOfArguments
0x180388088  mov     edx, ebx; dwExceptionFlags
0x18038808a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18038808f  call    cs:__imp_RaiseException
0x180388095  mov     rdx, [rbp+string]; string2
0x180388099  lea     r8, [rbp+spTimeRemainingTextBlock]; newString
0x18038809d  mov     this, [rbp+strAutomationName._hstring]; string1
0x1803880a1  mov     [rbp+spTimeRemainingTextBlock.ptr_], 0
0x1803880a9  call    cs:__imp_WindowsConcatString
0x1803880af  mov     rdx, [rbp+spTimeRemainingTextBlock.ptr_]; newValue
0x1803880b3  lea     r8, [rbp+strAutomationName]; target
0x1803880b7  mov     ecx, eax; hr
0x1803880b9  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x1803880be  mov     ebx, eax
0x1803880c0  test    eax, eax
0x1803880c2  js      short loc_180388132
0x1803880c4  lea     r8, [rbp+strAutomationName]; newString
0x1803880c8  lea     rdx, [rbp+strTimeElapsedText]; string
0x1803880cc  lea     this, [rbp+strAutomationName]; this
0x1803880d0  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1803880d5  mov     ebx, eax
0x1803880d7  test    eax, eax
0x1803880d9  js      short loc_180388129
0x1803880db  lea     this, [rbp+spTimeElapsedTextBlock]; this
0x1803880df  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1803880e4  lea     this, [rbp+strTimeElapsedText]; this
0x1803880e8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1803880ed  mov     this, [r14]
0x1803880f0  mov     edx, 22h ; '"'; nPropertyIndex
0x1803880f5  mov     rbx, [rbp+strAutomationName._hstring]
0x1803880f9  mov     r8, rbx; value
0x1803880fc  lea     rax, [this-160h]
0x180388103  neg     this
0x180388106  sbb     this, this
0x180388109  and     this, rax; this
0x18038810c  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x180388111  mov     edi, eax
0x180388113  test    eax, eax
0x180388115  jns     loc_1803881B0
0x18038811b  mov     ecx, eax; failedFrameHR
0x18038811d  call    OnFailure_2990_
0x180388122  mov     ebx, edi
0x180388124  jmp     loc_180388343
0x180388129  mov     ecx, eax; failedFrameHR
0x18038812b  call    OnFailure_2990_
0x180388130  jmp     short loc_18038818D
0x180388132  mov     ecx, ebx; failedFrameHR
0x180388134  call    OnFailure_2990_
0x180388139  mov     this, [rbp+spTimeElapsedTextBlock.ptr_]
0x18038813d  test    this, this
0x180388140  jz      short loc_180388156
0x180388142  mov     [rbp+spTimeElapsedTextBlock.ptr_], 0
0x18038814a  mov     rax, [this]
0x18038814d  mov     rax, [rax+10h]
0x180388151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180388156  mov     this, [rbp+strTimeElapsedText._hstring]; string
0x18038815a  test    this, this
0x18038815d  jz      short loc_180388165
0x18038815f  call    cs:__imp_WindowsDeleteString
0x180388165  mov     this, [rbp+strAutomationName._hstring]; string
0x180388169  test    this, this
0x18038816c  jz      loc_18038834C
0x180388172  call    cs:__imp_WindowsDeleteString
0x180388178  jmp     loc_18038834C
0x18038817d  mov     ecx, eax; failedFrameHR
0x18038817f  call    OnFailure_2990_
0x180388184  jmp     short loc_18038818D
0x180388186  mov     ecx, eax; failedFrameHR
0x180388188  call    OnFailure_2990_
0x18038818d  lea     this, [rbp+spTimeElapsedTextBlock]; this
0x180388191  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180388196  lea     this, [rbp+strTimeElapsedText]; this
0x18038819a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18038819f  jmp     loc_180388343
0x1803881a4  mov     ecx, eax; failedFrameHR
0x1803881a6  call    OnFailure_2990_
0x1803881ab  jmp     loc_180388343
0x1803881b0  lea     r14, [rsi+5D8h]
0x1803881b7  mov     this, [r14]; pInterface
0x1803881ba  test    this, this
0x1803881bd  jz      loc_180388350
0x1803881c3  call    ??$is@UIContentControl@Controls@Xaml@UI@Windows@@UIFrameworkElement@345@@ctl@@YAIPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(Windows::UI::Xaml::IFrameworkElement *)
0x1803881c8  test    eax, eax
0x1803881ca  jnz     loc_180388350
0x1803881d0  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1803881d5  mov     this, rbx; string
0x1803881d8  mov     rdi, rax
0x1803881db  call    cs:__imp_WindowsDeleteString
0x1803881e1  lea     r8, [rbp+strAutomationName]; resourceString
0x1803881e5  mov     [rbp+strAutomationName._hstring], 0
0x1803881ed  mov     edx, 1488h; resourceStringID
0x1803881f2  mov     this, rdi; this
0x1803881f5  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1803881fa  mov     ebx, eax
0x1803881fc  test    eax, eax
0x1803881fe  js      loc_18038833C
0x180388204  mov     al, [rsi+2CEh]
0x18038820a  and     al, 30h
0x18038820c  cmp     al, 10h
0x18038820e  jnz     loc_1803882D2
0x180388214  mov     this, rsi; this
0x180388217  call    ?IsLiveContent@MediaTransportControls@DirectUI@@AEAAEXZ; DirectUI::MediaTransportControls::IsLiveContent(void)
0x18038821c  test    al, al
0x18038821e  jnz     loc_1803882D2
0x180388224  lea     rdx, [rbp+spTimeRemainingTextBlock]; p
0x180388228  mov     [rbp+strTimeRemainingText._hstring], 0
0x180388230  mov     this, r14; this
0x180388233  mov     [rbp+spTimeRemainingTextBlock.ptr_], 0
0x18038823b  call    ??$As@UITextBlock@Controls@Xaml@UI@Windows@@@?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextBlock@Controls@Xaml@UI@Windows@@@ctl@@@Internal@ctl@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock>>)
0x180388240  mov     ebx, eax
0x180388242  test    eax, eax
0x180388244  js      loc_180388323
0x18038824a  mov     rdi, [rbp+spTimeRemainingTextBlock.ptr_]
0x18038824e  mov     this, [rbp+strTimeRemainingText._hstring]; string
0x180388252  mov     rax, [rdi]
0x180388255  mov     rbx, [rax+0D0h]
0x18038825c  call    cs:__imp_WindowsDeleteString
0x180388262  lea     rdx, [rbp+strTimeRemainingText]
0x180388266  mov     [rbp+strTimeRemainingText._hstring], 0
0x18038826e  mov     this, rdi
0x180388271  mov     rax, rbx
0x180388274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180388279  mov     ebx, eax
0x18038827b  test    eax, eax
0x18038827d  js      loc_18038831A
0x180388283  lea     rdx, source; " "
0x18038828a  lea     this, [rbp+string]; this
0x18038828e  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x180388293  lea     r8, [rbp+strAutomationName]; newString
0x180388297  mov     rdx, rax; string
0x18038829a  lea     this, [rbp+strAutomationName]; this
0x18038829e  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1803882a3  mov     ebx, eax
0x1803882a5  test    eax, eax
0x1803882a7  js      short loc_180388311
0x1803882a9  lea     r8, [rbp+strAutomationName]; newString
0x1803882ad  lea     rdx, [rbp+strTimeRemainingText]; string
0x1803882b1  lea     this, [rbp+strAutomationName]; this
0x1803882b5  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1803882ba  mov     ebx, eax
0x1803882bc  test    eax, eax
0x1803882be  js      short loc_180388308
0x1803882c0  lea     this, [rbp+spTimeRemainingTextBlock]; this
0x1803882c4  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1803882c9  lea     this, [rbp+strTimeRemainingText]; this
0x1803882cd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1803882d2  mov     this, [r14]
0x1803882d5  mov     edx, 22h ; '"'; nPropertyIndex
0x1803882da  mov     rbx, [rbp+strAutomationName._hstring]
0x1803882de  mov     r8, rbx; value
0x1803882e1  lea     rax, [this-160h]
0x1803882e8  neg     this
0x1803882eb  sbb     this, this
0x1803882ee  and     this, rax; this
0x1803882f1  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x1803882f6  mov     edi, eax
0x1803882f8  test    eax, eax
0x1803882fa  jns     short loc_180388350
0x1803882fc  mov     ecx, eax; failedFrameHR
0x1803882fe  call    OnFailure_2990_
0x180388303  jmp     loc_180388122
0x180388308  mov     ecx, eax; failedFrameHR
0x18038830a  call    OnFailure_2990_
0x18038830f  jmp     short loc_18038832A
0x180388311  mov     ecx, eax; failedFrameHR
0x180388313  call    OnFailure_2990_
0x180388318  jmp     short loc_18038832A
0x18038831a  mov     ecx, eax; failedFrameHR
0x18038831c  call    OnFailure_2990_
0x180388321  jmp     short loc_18038832A
0x180388323  mov     ecx, eax; failedFrameHR
0x180388325  call    OnFailure_2990_
0x18038832a  lea     this, [rbp+spTimeRemainingTextBlock]; this
0x18038832e  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180388333  lea     this, [rbp+strTimeRemainingText]
0x180388337  jmp     loc_18038819A
0x18038833c  mov     ecx, eax; failedFrameHR
0x18038833e  call    OnFailure_2990_
0x180388343  lea     this, [rbp+strAutomationName]; this
0x180388347  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18038834c  mov     eax, ebx
0x18038834e  jmp     short loc_180388360
0x180388350  test    rbx, rbx
0x180388353  jz      short loc_18038835E
0x180388355  mov     this, rbx; string
0x180388358  call    cs:__imp_WindowsDeleteString
0x18038835e  xor     eax, eax
0x180388360  mov     this, [rbp+var_8]
0x180388364  xor     this, rsp; StackCookie
0x180388367  call    __security_check_cookie
0x18038836c  lea     r11, [rsp+70h+var_s0]
0x180388371  mov     rbx, [r11+28h]
0x180388375  mov     rsi, [r11+30h]
0x180388379  mov     rsp, r11
0x18038837c  pop     r14
0x18038837e  pop     rdi
0x18038837f  pop     rbp
0x180388380  retn
```
