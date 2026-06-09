# DirectUI::MediaTransportControls::UpdatePositionUI(void)

- ea: `0x180385f74`
- end: `0x18038668c`
- name: `?UpdatePositionUI@MediaTransportControls@DirectUI@@AEAAJXZ`
- size: `1816`
- prototype: `HRESULT __fastcall(DirectUI::MediaTransportControls *this)`
- caller_count: `10`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004dd04`
- `0x180387a00`
- `0x18038aa20`
- `0x18062ee74`
- `0x18064aab0`
- `0x180b966f0`
- `0x180b96780`
- `0x180b96960`
- `0x180b96f80`
- `0x180bc0180`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18014cb6c`
- `0x1801df610`
- `0x180298b8c`
- `0x180298c4c`
- `0x1803839c0`
- `0x180384178`
- `0x1803848f8`
- `0x180385f74`
- `0x180386694`
- `0x1803871f0`
- `0x180387e5c`
- `0x180387f7c`
- `0x180701858`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180386536`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180386536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803861c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803861d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038654b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803865dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803861c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803861d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038654b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803865dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18038626d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18038626d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803860cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803860cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1803860ec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1803860ec`

## pseudocode

```c
__int64 __fastcall DirectUI::MediaTransportControls::UpdatePositionUI(DirectUI::MediaTransportControls *this)
{
  bool v2; // zf
  unsigned int v3; // ebx
  Windows::Foundation::TimeSpan *m_value; // rcx
  IUnknown *v5; // rax
  __int64 v6; // rcx
  HRESULT v7; // eax
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 v10; // r14
  HSTRING__ *hstring; // rcx
  HRESULT ActivationFactory; // eax
  DirectUI::MediaTransportControls *v13; // rcx
  HRESULT v14; // eax
  unsigned int v15; // eax
  DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *p_m_tpTimeElapsedElement; // rcx
  HRESULT v17; // eax
  void *v18; // rcx
  char v19; // al
  HSTRING__ *v20; // rcx
  char v22; // al
  DirectUI::MediaTransportControls *v23; // rcx
  HRESULT LocalizedResourceString; // eax
  HRESULT v25; // eax
  unsigned int v26; // eax
  DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *p_m_tpTimeRemainingElement; // rcx
  HRESULT v28; // eax
  HSTRING__ *v29; // rdi
  __int64 (__fastcall *v30)(HSTRING__ *, HSTRING__ *, ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> *); // rbx
  HRESULT v31; // eax
  Windows::Foundation::IPropertyValue *v32; // rcx
  void *v33; // rcx
  HRESULT v34; // eax
  HRESULT Position; // eax
  long double v36; // xmm6_8
  Windows::Foundation::IPropertyValue *ptr; // rcx
  Windows::Foundation::IPropertyValueStatics *v38; // rcx
  HRESULT v39; // eax
  HSTRING__ *v40; // rdi
  __int64 (__fastcall *v41)(HSTRING__ *, __int64, ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> *); // rbx
  Windows::Foundation::IPropertyValue *v42; // rcx
  IUnknown *v43; // rcx
  HRESULT v44; // eax
  DirectUI::DXamlCore *v45; // rbx
  DirectUI::DXamlCore *Current; // rbx
  ctl::ComPtr<Windows::Foundation::IPropertyValue> spContentAsPV; // [rsp+28h] [rbp-39h] BYREF
  ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> spPropertyValueFactory; // [rsp+30h] [rbp-31h] BYREF
  Windows::Internal::String strTimeRemainingText; // [rsp+38h] [rbp-29h] BYREF
  Windows::Internal::String strTimeElapsedText; // [rsp+40h] [rbp-21h] BYREF
  Windows::Foundation::TimeSpan currentMediaPosition; // [rsp+48h] [rbp-19h] BYREF
  Windows::Foundation::TimeSpan value; // [rsp+50h] [rbp-11h] BYREF
  HSTRING string; // [rsp+58h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-1h] BYREF

  v2 = (*((_BYTE *)this + 716) & 8) == 0;
  v3 = 0;
  strTimeRemainingText._hstring = 0;
  value.Duration = 0;
  currentMediaPosition.Duration = 0;
  strTimeElapsedText._hstring = 0;
  if ( v2 || !this->m_wrOwnerParent.ptr_ )
    goto LABEL_32;
  if ( (*((_BYTE *)this + 718) & 0x10) != 0 )
  {
    Position = DirectUI::MediaTransportControls::GetPosition(this, &value);
    v3 = Position;
    if ( Position < 0 )
    {
      OnFailure_2990_(Position);
      goto $Cleanup_2550;
    }
    if ( !DirectUI::MediaTransportControls::IsLiveContent(this) )
    {
      v36 = (double)SLODWORD(value.Duration)
          / (double)(int)this->m_naturalDuration.TimeSpan.Duration
          * (this->m_positionSliderMaximum - this->m_positionSliderMinimum)
          + this->m_positionSliderMinimum;
      if ( !DirectUI::DoubleUtil::IsNaN(v36) )
        DirectUI::DoubleUtil::IsInfinity(v36);
    }
  }
  m_value = (Windows::Foundation::TimeSpan *)this->m_tpMediaPositionSlider.m_trackerReference.m_value;
  if ( m_value )
  {
    *((_BYTE *)this + 718) |= 4u;
    m_value[66].Duration = value.Duration;
    m_value[67].Duration = (__int64)this->m_naturalDuration.TimeSpan;
    v5 = this->m_tpMediaPositionSlider.m_trackerReference.m_value;
    v6 = (__int64)&v5[-7];
    if ( !v5 )
      v6 = 536;
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 120LL))(v6);
    v3 = v7;
    if ( v7 < 0 )
    {
      OnFailure_2990_(v7);
      goto LABEL_32;
    }
    *((_BYTE *)this + 718) &= ~4u;
  }
  v8 = value.Duration / 10000000;
  if ( DirectUI::MediaTransportControls::IsLiveContent(this) )
    v10 = 0x7FFFFFFFFFFFFFFFLL;
  else
    v10 = ((unsigned __int64)(this->m_naturalDuration.TimeSpan.Duration
                            + ((unsigned __int128)(this->m_naturalDuration.TimeSpan.Duration * (__int128)v9) >> 64)) >> 63)
        + ((__int64)(this->m_naturalDuration.TimeSpan.Duration
                   + ((unsigned __int128)(this->m_naturalDuration.TimeSpan.Duration * (__int128)v9) >> 64)) >> 23)
        - v8;
  hstring = strTimeRemainingText._hstring;
  if ( strTimeRemainingText._hstring )
  {
    strTimeRemainingText._hstring = 0;
    (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)hstring + 16LL))(hstring);
  }
  if ( WindowsCreateStringReference(RuntimeClass_Windows_Foundation_PropertyValue, 0x20u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &strTimeRemainingText);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    OnFailure_2990_(ActivationFactory);
    goto LABEL_32;
  }
  if ( !this->m_tpTimeElapsedElement.m_trackerReference.m_value )
  {
LABEL_26:
    if ( !this->m_tpTimeRemainingElement.m_trackerReference.m_value )
      goto LABEL_27;
    v22 = *((_BYTE *)this + 718);
    if ( (v22 & 2) != 0 )
    {
      Current = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                  Current,
                                  0x13CDu,
                                  &strTimeElapsedText._hstring);
      v3 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
        goto LABEL_86;
    }
    else if ( (v22 & 0x10) == 0 || DirectUI::MediaTransportControls::IsLiveContent(this) )
    {
      spContentAsPV.ptr_ = 0;
      v25 = WindowsCreateString(&pressedKeys, 0, (HSTRING *)&spContentAsPV);
      Windows::Internal::String::FreeAndAssignOnSuccess(
        v25,
        (HSTRING__ *)spContentAsPV.ptr_,
        &strTimeElapsedText._hstring);
    }
    else
    {
      LocalizedResourceString = DirectUI::MediaTransportControls::ConvertSecondsToHString(
                                  v23,
                                  v10,
                                  &strTimeElapsedText._hstring);
      v3 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
      {
LABEL_86:
        OnFailure_2990_(LocalizedResourceString);
        goto $Cleanup_2550;
      }
    }
    v26 = ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>((Windows::UI::Xaml::IFrameworkElement *)this->m_tpTimeRemainingElement.m_trackerReference.m_value);
    spContentAsPV.ptr_ = 0;
    p_m_tpTimeRemainingElement = &this->m_tpTimeRemainingElement;
    if ( v26 )
    {
      spPropertyValueFactory.ptr_ = 0;
      v28 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::IContentControl>(
              p_m_tpTimeRemainingElement,
              (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IContentControl> >)&spContentAsPV);
      v3 = v28;
      if ( v28 < 0 )
      {
        OnFailure_2990_(v28);
        ptr = spContentAsPV.ptr_;
        if ( spContentAsPV.ptr_ )
        {
          spContentAsPV.ptr_ = 0;
          ptr->Release(ptr);
        }
        v38 = spPropertyValueFactory.ptr_;
        if ( spPropertyValueFactory.ptr_ )
        {
          spPropertyValueFactory.ptr_ = 0;
          v38->Release(v38);
        }
        goto $Cleanup_2550;
      }
      v29 = strTimeRemainingText._hstring;
      v30 = *(__int64 (__fastcall **)(HSTRING__ *, HSTRING__ *, ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> *))(*(_QWORD *)strTimeRemainingText._hstring + 144LL);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
      v31 = v30(v29, strTimeElapsedText._hstring, &spPropertyValueFactory);
      v3 = v31;
      if ( v31 < 0
        || (v31 = spContentAsPV.ptr_->get_IsNumericScalar(
                    spContentAsPV.ptr_,
                    (unsigned __int8 *)spPropertyValueFactory.ptr_),
            v3 = v31,
            v31 < 0) )
      {
        OnFailure_2990_(v31);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
        goto $Cleanup_2550;
      }
      v32 = spContentAsPV.ptr_;
      if ( spContentAsPV.ptr_ )
      {
        spContentAsPV.ptr_ = 0;
        v32->Release(v32);
      }
      v33 = spPropertyValueFactory.ptr_;
      if ( spPropertyValueFactory.ptr_ )
      {
        spPropertyValueFactory.ptr_ = 0;
LABEL_54:
        (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
      }
    }
    else
    {
      v34 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(
              p_m_tpTimeRemainingElement,
              (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> >)&spContentAsPV);
      v3 = v34;
      if ( v34 < 0
        || (v34 = ((__int64 (__fastcall *)(Windows::Foundation::IPropertyValue *, HSTRING__ *))spContentAsPV.ptr_->GetInt16Array)(
                    spContentAsPV.ptr_,
                    strTimeElapsedText._hstring),
            v3 = v34,
            v34 < 0) )
      {
        OnFailure_2990_(v34);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
        goto $Cleanup_2550;
      }
      v33 = spContentAsPV.ptr_;
      if ( spContentAsPV.ptr_ )
      {
        spContentAsPV.ptr_ = 0;
        goto LABEL_54;
      }
    }
LABEL_27:
    v19 = *((_BYTE *)this + 718);
    if ( (v19 & 0x10) != 0 && (v19 & 0x20) == 0 )
    {
      LocalizedResourceString = DirectUI::MediaTransportControls::UpdateTimeAutomationProperties(this);
      v3 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
        goto LABEL_86;
    }
$Cleanup_2550:
    if ( strTimeElapsedText._hstring )
      WindowsDeleteString(strTimeElapsedText._hstring);
    goto LABEL_30;
  }
  if ( (*((_BYTE *)this + 718) & 1) == 0 )
  {
    v14 = DirectUI::MediaTransportControls::ConvertSecondsToHString(v13, v8, (HSTRING__ **)&currentMediaPosition);
    v3 = v14;
    if ( v14 >= 0 )
      goto LABEL_19;
LABEL_75:
    OnFailure_2990_(v14);
    goto LABEL_30;
  }
  v45 = DirectUI::DXamlCore::GetCurrent();
  WindowsDeleteString(0);
  v14 = DirectUI::DXamlCore::GetLocalizedResourceString(v45, 0x13CCu, (HSTRING__ **)&currentMediaPosition);
  v3 = v14;
  if ( v14 < 0 )
    goto LABEL_75;
LABEL_19:
  v15 = ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>((Windows::UI::Xaml::IFrameworkElement *)this->m_tpTimeElapsedElement.m_trackerReference.m_value);
  spContentAsPV.ptr_ = 0;
  p_m_tpTimeElapsedElement = &this->m_tpTimeElapsedElement;
  if ( v15 )
  {
    spPropertyValueFactory.ptr_ = 0;
    v39 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::IContentControl>(
            p_m_tpTimeElapsedElement,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IContentControl> >)&spContentAsPV);
    v3 = v39;
    if ( v39 >= 0 )
    {
      v40 = strTimeRemainingText._hstring;
      v41 = *(__int64 (__fastcall **)(HSTRING__ *, __int64, ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> *))(*(_QWORD *)strTimeRemainingText._hstring + 144LL);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
      v39 = v41(v40, currentMediaPosition.Duration, &spPropertyValueFactory);
      v3 = v39;
      if ( v39 >= 0 )
      {
        v39 = spContentAsPV.ptr_->get_IsNumericScalar(
                spContentAsPV.ptr_,
                (unsigned __int8 *)spPropertyValueFactory.ptr_);
        v3 = v39;
        if ( v39 >= 0 )
        {
          v42 = spContentAsPV.ptr_;
          if ( spContentAsPV.ptr_ )
          {
            spContentAsPV.ptr_ = 0;
            v42->Release(v42);
          }
          v18 = spPropertyValueFactory.ptr_;
          if ( spPropertyValueFactory.ptr_ )
          {
            spPropertyValueFactory.ptr_ = 0;
            goto LABEL_24;
          }
LABEL_25:
          if ( (*((_BYTE *)this + 2832) & 8) != 0 )
          {
            v43 = this->m_tpTimeElapsedPreview.m_trackerReference.m_value;
            if ( v43 )
            {
              v44 = ((__int64 (__fastcall *)(IUnknown *, __int64))v43->__vftable[9].QueryInterface)(
                      v43,
                      currentMediaPosition.Duration);
              v3 = v44;
              if ( v44 < 0 )
              {
                OnFailure_2990_(v44);
                goto LABEL_30;
              }
            }
          }
          goto LABEL_26;
        }
      }
    }
    OnFailure_2990_(v39);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
  }
  else
  {
    v17 = DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(
            p_m_tpTimeElapsedElement,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> >)&spContentAsPV);
    v3 = v17;
    if ( v17 >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(Windows::Foundation::IPropertyValue *, __int64))spContentAsPV.ptr_->GetInt16Array)(
              spContentAsPV.ptr_,
              currentMediaPosition.Duration);
      v3 = v17;
      if ( v17 >= 0 )
      {
        v18 = spContentAsPV.ptr_;
        if ( spContentAsPV.ptr_ )
        {
          spContentAsPV.ptr_ = 0;
LABEL_24:
          (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
    }
    OnFailure_2990_(v17);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
  }
LABEL_30:
  if ( currentMediaPosition.Duration )
    WindowsDeleteString((HSTRING)currentMediaPosition.Duration);
LABEL_32:
  v20 = strTimeRemainingText._hstring;
  if ( strTimeRemainingText._hstring )
  {
    strTimeRemainingText._hstring = 0;
    (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return v3;
}

```

## disassembly

```asm
0x180385f74  mov     rax, rsp
0x180385f77  mov     [rax+10h], rbx
0x180385f7b  mov     [rax+18h], rsi
0x180385f7f  push    rbp
0x180385f80  push    rdi
0x180385f81  push    r12
0x180385f83  push    r14
0x180385f85  push    r15
0x180385f87  lea     rbp, [rax-5Fh]
0x180385f8b  sub     rsp, 90h
0x180385f92  movaps  xmmword ptr [rax-38h], xmm6
0x180385f96  mov     rax, cs:__security_cookie
0x180385f9d  xor     rax, rsp
0x180385fa0  mov     [rbp+57h+var_40], rax
0x180385fa4  xor     r12d, r12d
0x180385fa7  mov     rsi, this
0x180385faa  test    byte ptr [this+2CCh], 8
0x180385fb1  mov     ebx, r12d
0x180385fb4  mov     [rbp+57h+strTimeRemainingText._hstring], r12
0x180385fb8  mov     [rbp+57h+value.Duration], r12
0x180385fbc  mov     [rbp+57h+currentMediaPosition.Duration], r12
0x180385fc0  mov     [rbp+57h+strTimeElapsedText._hstring], r12
0x180385fc4  jz      loc_1803861D8
0x180385fca  cmp     [this+240h], r12
0x180385fd1  jz      loc_1803861D8
0x180385fd7  test    byte ptr [this+2CEh], 10h
0x180385fde  jnz     loc_18038638C
0x180385fe4  xorps   xmm6, xmm6
0x180385fe7  mov     this, [rsi+380h]
0x180385fee  test    this, this
0x180385ff1  jz      short loc_18038604A
0x180385ff3  or      byte ptr [rsi+2CEh], 4
0x180385ffa  mov     edx, 218h
0x180385fff  mov     rax, [rbp+57h+value.Duration]
0x180386003  movaps  xmm1, xmm6
0x180386006  mov     [this+210h], rax
0x18038600d  mov     rax, [rsi+2F8h]
0x180386014  mov     [this+218h], rax
0x18038601b  mov     rax, [rsi+380h]
0x180386022  test    rax, rax
0x180386025  lea     this, [rax-38h]
0x180386029  cmovz   this, rdx
0x18038602d  mov     rax, [this]
0x180386030  mov     rax, [rax+78h]
0x180386034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386039  mov     ebx, eax
0x18038603b  test    eax, eax
0x18038603d  js      loc_180386674
0x180386043  and     byte ptr [rsi+2CEh], 0FBh
0x18038604a  mov     r8, 0D6BF94D5E57A42BDh
0x180386054  mov     this, rsi; this
0x180386057  mov     rax, r8
0x18038605a  imul    [rbp+57h+value.Duration]
0x18038605e  mov     rdi, rdx
0x180386061  add     rdi, [rbp+57h+value.Duration]
0x180386065  sar     rdi, 17h
0x180386069  mov     rax, rdi
0x18038606c  shr     rax, 3Fh
0x180386070  add     rdi, rax
0x180386073  call    ?IsLiveContent@MediaTransportControls@DirectUI@@AEAAEXZ; DirectUI::MediaTransportControls::IsLiveContent(void)
0x180386078  test    al, al
0x18038607a  jnz     loc_18038644B
0x180386080  mov     this, [rsi+2F8h]
0x180386087  mov     rax, r8
0x18038608a  imul    this
0x18038608d  lea     r14, [this+rdx]
0x180386091  sar     r14, 17h
0x180386095  mov     rax, r14
0x180386098  shr     rax, 3Fh
0x18038609c  add     r14, rax
0x18038609f  sub     r14, rdi
0x1803860a2  mov     this, [rbp+57h+strTimeRemainingText._hstring]
0x1803860a6  test    this, this
0x1803860a9  jz      short loc_1803860BB
0x1803860ab  mov     [rbp+57h+strTimeRemainingText._hstring], r12
0x1803860af  mov     rax, [this]
0x1803860b2  mov     rax, [rax+10h]
0x1803860b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803860bb  lea     r9, [rbp+57h+string]; string
0x1803860bf  mov     edx, 20h ; ' '; length
0x1803860c4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1803860c8  lea     this, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; sourceString
0x1803860cf  call    cs:__imp_WindowsCreateStringReference
0x1803860d5  test    eax, eax
0x1803860d7  js      loc_180386527
0x1803860dd  mov     this, [rbp+57h+string]
0x1803860e1  lea     r8, [rbp+57h+strTimeRemainingText]
0x1803860e5  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1803860ec  call    cs:__imp_RoGetActivationFactory
0x1803860f2  mov     ebx, eax
0x1803860f4  test    eax, eax
0x1803860f6  js      loc_18038632E
0x1803860fc  lea     r15, [rsi+5C0h]
0x180386103  cmp     [r15], r12
0x180386106  jz      loc_1803861A0
0x18038610c  test    byte ptr [rsi+2CEh], 1
0x180386113  jnz     loc_180386541
0x180386119  lea     r8, [rbp+57h+currentMediaPosition]; pDisplayTime
0x18038611d  mov     rdx, rdi; totalSeconds
0x180386120  call    ?ConvertSecondsToHString@MediaTransportControls@DirectUI@@AEAAJ_JPEAPEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::ConvertSecondsToHString(__int64,HSTRING__ * *)
0x180386125  mov     ebx, eax
0x180386127  test    eax, eax
0x180386129  js      loc_1803865C6
0x18038612f  mov     this, [r15]; pInterface
0x180386132  call    ??$is@UIContentControl@Controls@Xaml@UI@Windows@@UIFrameworkElement@345@@ctl@@YAIPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(Windows::UI::Xaml::IFrameworkElement *)
0x180386137  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x18038613b  lea     rdx, [rbp+57h+spContentAsPV]; p
0x18038613f  mov     this, r15; this
0x180386142  test    eax, eax
0x180386144  jnz     loc_18038645A
0x18038614a  call    ??$As@UITextBlock@Controls@Xaml@UI@Windows@@@?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextBlock@Controls@Xaml@UI@Windows@@@ctl@@@Internal@ctl@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock>>)
0x18038614f  mov     ebx, eax
0x180386151  test    eax, eax
0x180386153  js      loc_1803865B1
0x180386159  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x18038615d  mov     rdx, [rbp+57h+currentMediaPosition.Duration]
0x180386161  mov     rax, [this]
0x180386164  mov     rax, [rax+0D8h]
0x18038616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386170  mov     ebx, eax
0x180386172  test    eax, eax
0x180386174  js      loc_1803865A8
0x18038617a  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x18038617e  test    this, this
0x180386181  jz      short loc_180386193
0x180386183  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x180386187  mov     rax, [this]
0x18038618a  mov     rax, [rax+10h]
0x18038618e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386193  test    byte ptr [rsi+0B10h], 8
0x18038619a  jnz     loc_1803864EE
0x1803861a0  lea     rdi, [rsi+5D8h]
0x1803861a7  cmp     [rdi], r12
0x1803861aa  jnz     short loc_180386220
0x1803861ac  mov     al, [rsi+2CEh]
0x1803861b2  test    al, 10h
0x1803861b4  jnz     loc_18038664E
0x1803861ba  mov     this, [rbp+57h+strTimeElapsedText._hstring]; string
0x1803861be  test    this, this
0x1803861c1  jz      short loc_1803861C9
0x1803861c3  call    cs:__imp_WindowsDeleteString
0x1803861c9  mov     this, [rbp+57h+currentMediaPosition.Duration]; string
0x1803861cd  test    this, this
0x1803861d0  jz      short loc_1803861D8
0x1803861d2  call    cs:__imp_WindowsDeleteString
0x1803861d8  mov     this, [rbp+57h+strTimeRemainingText._hstring]
0x1803861dc  test    this, this
0x1803861df  jz      short loc_1803861F1
0x1803861e1  mov     [rbp+57h+strTimeRemainingText._hstring], r12
0x1803861e5  mov     rax, [this]
0x1803861e8  mov     rax, [rax+10h]
0x1803861ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803861f1  mov     eax, ebx
0x1803861f3  mov     this, [rbp+57h+var_40]
0x1803861f7  xor     this, rsp; StackCookie
0x1803861fa  call    __security_check_cookie
0x1803861ff  lea     r11, [rsp+0B0h+var_20]
0x180386207  mov     rbx, [r11+38h]
0x18038620b  mov     rsi, [r11+40h]
0x18038620f  movaps  xmm6, xmmword ptr [r11-10h]
0x180386214  mov     rsp, r11
0x180386217  pop     r15
0x180386219  pop     r14
0x18038621b  pop     r12
0x18038621d  pop     rdi
0x18038621e  pop     rbp
0x18038621f  retn
0x180386220  mov     al, [rsi+2CEh]
0x180386226  test    al, 2
0x180386228  jnz     loc_1803865D2
0x18038622e  test    al, 10h
0x180386230  jz      short loc_18038625C
0x180386232  mov     this, rsi; this
0x180386235  call    ?IsLiveContent@MediaTransportControls@DirectUI@@AEAAEXZ; DirectUI::MediaTransportControls::IsLiveContent(void)
0x18038623a  test    al, al
0x18038623c  jnz     short loc_18038625C
0x18038623e  lea     r8, [rbp+57h+strTimeElapsedText]; pDisplayTime
0x180386242  mov     rdx, r14; totalSeconds
0x180386245  call    ?ConvertSecondsToHString@MediaTransportControls@DirectUI@@AEAAJ_JPEAPEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::ConvertSecondsToHString(__int64,HSTRING__ * *)
0x18038624a  mov     ebx, eax
0x18038624c  test    eax, eax
0x18038624e  jns     short loc_180386282
0x180386250  mov     ecx, eax; failedFrameHR
0x180386252  call    OnFailure_2990_
0x180386257  jmp     $Cleanup_2550
0x18038625c  lea     r8, [rbp+57h+spContentAsPV]; string
0x180386260  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x180386264  xor     edx, edx; length
0x180386266  lea     this, pressedKeys; sourceString
0x18038626d  call    cs:__imp_WindowsCreateString
0x180386273  mov     rdx, [rbp+57h+spContentAsPV.ptr_]; newValue
0x180386277  lea     r8, [rbp+57h+strTimeElapsedText]; target
0x18038627b  mov     ecx, eax; hr
0x18038627d  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180386282  mov     this, [rdi]; pInterface
0x180386285  call    ??$is@UIContentControl@Controls@Xaml@UI@Windows@@UIFrameworkElement@345@@ctl@@YAIPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; ctl::is<Windows::UI::Xaml::Controls::IContentControl,Windows::UI::Xaml::IFrameworkElement>(Windows::UI::Xaml::IFrameworkElement *)
0x18038628a  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x18038628e  lea     rdx, [rbp+57h+spContentAsPV]; p
0x180386292  mov     this, rdi; this
0x180386295  test    eax, eax
0x180386297  jz      loc_18038633A
0x18038629d  mov     [rbp+57h+spPropertyValueFactory.ptr_], r12
0x1803862a1  call    ??$As@UIContentControl@Controls@Xaml@UI@Windows@@@?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@QEBAJV?$ComPtrRef@V?$ComPtr@UIContentControl@Controls@Xaml@UI@Windows@@@ctl@@@Internal@ctl@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::IContentControl>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::IContentControl>>)
0x1803862a6  mov     ebx, eax
0x1803862a8  test    eax, eax
0x1803862aa  js      loc_180386409
0x1803862b0  mov     rdi, [rbp+57h+strTimeRemainingText._hstring]
0x1803862b4  lea     this, [rbp+57h+spPropertyValueFactory]; this
0x1803862b8  mov     rax, [rdi]
0x1803862bb  mov     rbx, [rax+90h]
0x1803862c2  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1803862c7  mov     rdx, [rbp+57h+strTimeElapsedText._hstring]
0x1803862cb  lea     r8, [rbp+57h+spPropertyValueFactory]
0x1803862cf  mov     this, rdi
0x1803862d2  mov     rax, rbx
0x1803862d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803862da  mov     ebx, eax
0x1803862dc  test    eax, eax
0x1803862de  js      loc_180386612
0x1803862e4  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x1803862e8  mov     rdx, [rbp+57h+spPropertyValueFactory.ptr_]
0x1803862ec  mov     rax, [this]
0x1803862ef  mov     rax, [rax+38h]
0x1803862f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803862f8  mov     ebx, eax
0x1803862fa  test    eax, eax
0x1803862fc  js      loc_180386609
0x180386302  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x180386306  test    this, this
0x180386309  jz      short loc_18038631B
0x18038630b  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x18038630f  mov     rax, [this]
0x180386312  mov     rax, [rax+10h]
0x180386316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038631b  mov     this, [rbp+57h+spPropertyValueFactory.ptr_]
0x18038631f  test    this, this
0x180386322  jz      loc_1803861AC
0x180386328  mov     [rbp+57h+spPropertyValueFactory.ptr_], r12
0x18038632c  jmp     short loc_18038637B
0x18038632e  mov     ecx, eax; failedFrameHR
0x180386330  call    OnFailure_2990_
0x180386335  jmp     loc_1803861D8
0x18038633a  call    ??$As@UITextBlock@Controls@Xaml@UI@Windows@@@?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextBlock@Controls@Xaml@UI@Windows@@@ctl@@@Internal@ctl@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0>::As<Windows::UI::Xaml::Controls::ITextBlock>(ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock>>)
0x18038633f  mov     ebx, eax
0x180386341  test    eax, eax
0x180386343  js      loc_180386639
0x180386349  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x18038634d  mov     rdx, [rbp+57h+strTimeElapsedText._hstring]
0x180386351  mov     rax, [this]
0x180386354  mov     rax, [rax+0D8h]
0x18038635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386360  mov     ebx, eax
0x180386362  test    eax, eax
0x180386364  js      loc_180386630
0x18038636a  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x18038636e  test    this, this
0x180386371  jz      loc_1803861AC
0x180386377  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x18038637b  mov     rax, [this]
0x18038637e  mov     rax, [rax+10h]
0x180386382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386387  jmp     loc_1803861AC
0x18038638c  lea     rdx, [rbp+57h+value]; value
0x180386390  call    ?GetPosition@MediaTransportControls@DirectUI@@AEAAJPEAUTimeSpan@Foundation@Windows@@@Z; DirectUI::MediaTransportControls::GetPosition(Windows::Foundation::TimeSpan *)
0x180386395  mov     ebx, eax
0x180386397  test    eax, eax
0x180386399  js      loc_180386680
0x18038639f  mov     this, rsi; this
0x1803863a2  call    ?IsLiveContent@MediaTransportControls@DirectUI@@AEAAEXZ; DirectUI::MediaTransportControls::IsLiveContent(void)
0x1803863a7  xorps   xmm6, xmm6
0x1803863aa  test    al, al
0x1803863ac  jnz     loc_180385FE7
0x1803863b2  cvtsi2sd xmm6, [rbp+57h+value.Duration]
0x1803863b8  movsd   xmm2, qword ptr [rsi+2D8h]
0x1803863c0  xorps   xmm0, xmm0
0x1803863c3  cvtsi2sd xmm0, qword ptr [rsi+2F8h]
0x1803863cc  movsd   xmm1, qword ptr [rsi+2E0h]
0x1803863d4  divsd   xmm6, xmm0
0x1803863d8  subsd   xmm1, xmm2
0x1803863dc  mulsd   xmm6, xmm1
0x1803863e0  addsd   xmm6, xmm2
0x1803863e4  movaps  xmm0, xmm6; value
0x1803863e7  call    ?IsNaN@DoubleUtil@DirectUI@@SA_NN@Z; DirectUI::DoubleUtil::IsNaN(double)
0x1803863ec  test    al, al
0x1803863ee  jnz     loc_180385FE4
0x1803863f4  movaps  xmm0, xmm6; value
0x1803863f7  call    ?IsInfinity@DoubleUtil@DirectUI@@SA_NN@Z; DirectUI::DoubleUtil::IsInfinity(double)
0x1803863fc  test    al, al
0x1803863fe  jz      loc_180385FE7
0x180386404  jmp     loc_180385FE4
0x180386409  mov     ecx, eax; failedFrameHR
0x18038640b  call    OnFailure_2990_
0x180386410  mov     this, [rbp+57h+spContentAsPV.ptr_]
0x180386414  test    this, this
0x180386417  jz      short loc_180386429
0x180386419  mov     [rbp+57h+spContentAsPV.ptr_], r12
0x18038641d  mov     rax, [this]
0x180386420  mov     rax, [rax+10h]
0x180386424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180386429  mov     this, [rbp+57h+spPropertyValueFactory.ptr_]
  ... truncated ...
```
