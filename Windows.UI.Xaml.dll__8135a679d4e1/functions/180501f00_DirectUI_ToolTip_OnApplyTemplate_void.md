# DirectUI::ToolTip::OnApplyTemplate(void)

- ea: `0x180501f00`
- end: `0x1805026bf`
- name: `?OnApplyTemplate@ToolTip@DirectUI@@MEAAJXZ`
- size: `1983`
- prototype: `HRESULT __fastcall(DirectUI::ToolTip *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x180079624`
- `0x180131190`
- `0x1801e5458`
- `0x18023eacc`
- `0x18023ef38`
- `0x1802490f0`
- `0x18024e464`
- `0x180501f00`
- `0x1805026c8`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805025e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805025e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18050217a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805022bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180502434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18050254c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18050217a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805022bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180502434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18050254c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1805021b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1805021b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180502051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180502051`

## string_xrefs

- `0x180502301`: `Opened`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall DirectUI::ToolTip::OnApplyTemplate(DirectUI::ToolTip *this)
{
  unsigned int v1; // esi
  Windows::UI::Xaml::IVisualState *v3; // r14
  HRESULT v4; // eax
  unsigned int v5; // ebx
  DirectUI::Control *v6; // r12
  HRESULT ChildrenCountStatic; // eax
  HRESULT v8; // eax
  DirectUI::VisualStateManagerFactory *v9; // rdi
  HRESULT (__fastcall *GetVisualStateGroups)(Windows::UI::Xaml::IVisualStateManagerStatics *, Windows::UI::Xaml::IFrameworkElement *, Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> **); // rbx
  HRESULT v11; // eax
  HRESULT v12; // eax
  unsigned int i; // r15d
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v14; // rdi
  HRESULT (__fastcall *GetAt)(Windows::Foundation::Collections::IVector_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Xaml::VisualStateGroup *,Windows::UI::Xaml::IVisualStateGroup *>,1> *, unsigned int, Windows::UI::Xaml::IVisualStateGroup **); // rbx
  HRESULT v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> > *); // rbx
  HRESULT v19; // eax
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> *v20; // rdi
  HRESULT (__fastcall *v21)(Windows::Foundation::Collections::IVector_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Xaml::VisualState *,Windows::UI::Xaml::IVisualState *>,1> *, unsigned int, Windows::UI::Xaml::IVisualState **); // rbx
  HRESULT v22; // eax
  Windows::UI::Xaml::IVisualState *v23; // rdi
  HRESULT (__fastcall *get_Name)(Windows::UI::Xaml::IVisualState *, HSTRING__ **); // rbx
  char *v25; // rbx
  char *FailFast; // rax
  char *v27; // r15
  char *v28; // r12
  Windows::UI::Xaml::IVisualState *v29; // rsi
  HRESULT (__fastcall *get_Storyboard)(Windows::UI::Xaml::IVisualState *, Windows::UI::Xaml::Media::Animation::IStoryboard **); // rdi
  HRESULT v31; // eax
  unsigned int v32; // edi
  Windows::UI::Xaml::Media::Animation::IStoryboard *v33; // rdx
  Windows::UI::Xaml::IVisualState *v34; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> *v35; // rcx
  Windows::UI::Xaml::IVisualStateGroup *v36; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v37; // rcx
  DirectUI::VisualStateManagerFactory *v38; // rcx
  HRESULT v39; // eax
  Windows::UI::Xaml::IDependencyObject *ptr; // rcx
  HRESULT v42; // eax
  Windows::UI::Xaml::Media::Animation::IStoryboard *v43; // rcx
  Windows::UI::Xaml::IVisualState *v44; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> *v45; // rcx
  Windows::UI::Xaml::IVisualStateGroup *v46; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v47; // rcx
  DirectUI::VisualStateManagerFactory *v48; // rcx
  Windows::UI::Xaml::IDependencyObject *v49; // rcx
  __int128 v50; // xmm0
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> *v51; // rcx
  Windows::UI::Xaml::IVisualStateGroup *v52; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> *v53; // rcx
  DirectUI::VisualStateManagerFactory *v54; // rcx
  Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> *v55; // rcx
  Windows::UI::Xaml::IVisualStateGroup *v56; // rcx
  ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualStateGroup *> > spChildVisualStateGroups; // [rsp+20h] [rbp-99h] BYREF
  ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> > spVisualStates; // [rsp+28h] [rbp-91h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IVisualStateGroup> spGroup; // [rsp+30h] [rbp-89h] BYREF
  ctl::ComPtr<DirectUI::VisualStateManagerFactory> spFactory; // [rsp+38h] [rbp-81h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IVisualState> spState; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int8 bIgnored[8]; // [rsp+48h] [rbp-71h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Media::Animation::IStoryboard> spStoryboard; // [rsp+50h] [rbp-69h] BYREF
  Windows::Internal::String strStateName; // [rsp+58h] [rbp-61h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spChild; // [rsp+60h] [rbp-59h] BYREF
  unsigned int nGroupCount; // [rsp+68h] [rbp-51h] BYREF
  unsigned int nStateCount; // [rsp+6Ch] [rbp-4Dh] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spChildAsFE; // [rsp+70h] [rbp-49h] BYREF
  __int128 spClosedStateStoryboardCompletedHandler; // [rsp+80h] [rbp-39h] OVERLAPPED BYREF
  ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated> *v70; // [rsp+90h] [rbp-29h]
  EventRegistrationToken closedStateStoryboardCompletedToken; // [rsp+98h] [rbp-21h] BYREF
  int v72; // [rsp+A4h] [rbp-15h]
  Windows::Internal::StringReference strClosedStateName; // [rsp+A8h] [rbp-11h] BYREF

  v1 = 0;
  spChild.ptr_ = 0;
  v3 = 0;
  spChildAsFE.ptr_ = 0;
  LODWORD(spStoryboard.ptr_) = 0;
  nGroupCount = 0;
  nStateCount = 0;
  closedStateStoryboardCompletedToken.value = 0;
  v4 = DirectUI::Control::OnApplyTemplate(this);
  v5 = v4;
  if ( v4 < 0 )
  {
    OnFailure_2990_(v4);
LABEL_51:
    ptr = spChild.ptr_;
    if ( spChild.ptr_ )
    {
      spChild.ptr_ = 0;
      ptr->Release(ptr);
    }
    return v5;
  }
  v6 = (DirectUI::ToolTip *)((char *)this - 360);
  v70 = &this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>;
  ChildrenCountStatic = DirectUI::VisualTreeHelper::GetChildrenCountStatic(
                          (DirectUI::ToolTip *)((char *)this - 360),
                          (int *)&spStoryboard);
  v5 = ChildrenCountStatic;
  if ( ChildrenCountStatic < 0 )
    goto LABEL_104;
  if ( !LODWORD(spStoryboard.ptr_) )
    goto LABEL_48;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChild);
  ChildrenCountStatic = DirectUI::VisualTreeHelper::GetChildStatic(
                          (DirectUI::ToolTip *)((char *)this - 360),
                          0,
                          &spChild.ptr_);
  v5 = ChildrenCountStatic;
  if ( ChildrenCountStatic < 0 )
  {
LABEL_104:
    OnFailure_2990_(ChildrenCountStatic);
    goto LABEL_105;
  }
  spState.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
  if ( spChild.ptr_ )
    spChild.ptr_->QueryInterface(spChild.ptr_, &GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf, (void **)&spState);
  v3 = spState.ptr_;
  spChildAsFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)spState.ptr_;
  if ( spState.ptr_ )
  {
    spFactory.ptr_ = 0;
    spChildVisualStateGroups.ptr_ = 0;
    v8 = ctl::make<DirectUI::VisualStateManagerFactory>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::VisualStateManagerFactory> >)&spFactory);
    v5 = v8;
    if ( v8 < 0 )
    {
      OnFailure_2990_(v8);
    }
    else
    {
      v9 = spFactory.ptr_;
      GetVisualStateGroups = spFactory.ptr_->GetVisualStateGroups;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChildVisualStateGroups);
      v11 = GetVisualStateGroups(
              &v9->Windows::UI::Xaml::IVisualStateManagerStatics,
              (Windows::UI::Xaml::IFrameworkElement *)v3,
              &spChildVisualStateGroups.ptr_);
      v5 = v11;
      if ( v11 >= 0 )
      {
        if ( spChildVisualStateGroups.ptr_ )
        {
          strStateName._hstring = 0;
          if ( WindowsCreateStringReference(L"Closed", 6u, &strClosedStateName._header, &strClosedStateName._hstring) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v12 = spChildVisualStateGroups.ptr_->get_Size(spChildVisualStateGroups.ptr_, &nGroupCount);
          v5 = v12;
          if ( v12 < 0 )
          {
            OnFailure_2990_(v12);
          }
          else
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= nGroupCount )
                goto LABEL_42;
              v14 = spChildVisualStateGroups.ptr_;
              spGroup.ptr_ = 0;
              spVisualStates.ptr_ = 0;
              GetAt = spChildVisualStateGroups.ptr_->GetAt;
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroup);
              v16 = GetAt(v14, i, &spGroup.ptr_);
              v5 = v16;
              if ( v16 < 0 )
              {
                OnFailure_2990_(v16);
                v51 = spVisualStates.ptr_;
                if ( spVisualStates.ptr_ )
                {
                  spVisualStates.ptr_ = 0;
                  v51->Release(v51);
                }
                v52 = spGroup.ptr_;
                if ( spGroup.ptr_ )
                {
                  spGroup.ptr_ = 0;
                  v52->Release(v52);
                }
                if ( strStateName._hstring )
                  WindowsDeleteString(strStateName._hstring);
                v53 = spChildVisualStateGroups.ptr_;
                if ( spChildVisualStateGroups.ptr_ )
                {
                  spChildVisualStateGroups.ptr_ = 0;
                  v53->Release(v53);
                }
                v54 = spFactory.ptr_;
                if ( spFactory.ptr_ )
                {
                  spFactory.ptr_ = 0;
                  v54->Release(v54);
                }
                goto LABEL_50;
              }
              v17 = (__int64)spGroup.ptr_;
              if ( !spGroup.ptr_ )
                v17 = 184;
              v18 = *(__int64 (__fastcall **)(__int64, ctl::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::VisualState *> > *))(*(_QWORD *)v17 + 64LL);
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spVisualStates);
              v19 = v18(v17, &spVisualStates);
              v5 = v19;
              if ( v19 < 0 )
                goto LABEL_95;
              if ( spVisualStates.ptr_ )
                break;
LABEL_89:
              v56 = spGroup.ptr_;
              if ( spGroup.ptr_ )
              {
                spGroup.ptr_ = 0;
                v56->Release(v56);
              }
            }
            v19 = spVisualStates.ptr_->get_Size(spVisualStates.ptr_, &nStateCount);
            v5 = v19;
            if ( v19 >= 0 )
            {
              while ( 1 )
              {
                if ( v1 >= nStateCount )
                {
                  v55 = spVisualStates.ptr_;
                  v1 = 0;
                  if ( spVisualStates.ptr_ )
                  {
                    spVisualStates.ptr_ = 0;
                    v55->Release(v55);
                  }
                  goto LABEL_89;
                }
                spState.ptr_ = 0;
                v20 = spVisualStates.ptr_;
                v21 = spVisualStates.ptr_->GetAt;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
                v22 = v21(v20, v1, &spState.ptr_);
                v5 = v22;
                if ( v22 < 0
                  || (v23 = spState.ptr_,
                      get_Name = spState.ptr_->get_Name,
                      WindowsDeleteString(strStateName._hstring),
                      strStateName._hstring = 0,
                      v22 = get_Name(v23, &strStateName._hstring),
                      v5 = v22,
                      v22 < 0) )
                {
                  OnFailure_2990_(v22);
                  goto LABEL_94;
                }
                LODWORD(spStoryboard.ptr_) = 0;
                WindowsCompareStringOrdinal(strStateName._hstring, strClosedStateName._hstring, (INT32 *)&spStoryboard);
                if ( !LODWORD(spStoryboard.ptr_) )
                  break;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
                ++v1;
              }
              v25 = 0;
              spStoryboard.ptr_ = 0;
              *(_QWORD *)&spClosedStateStoryboardCompletedHandler = 0;
              FailFast = (char *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
              v27 = FailFast;
              if ( FailFast )
              {
                DWORD2(spClosedStateStoryboardCompletedHandler) = 0;
                *(_QWORD *)&spClosedStateStoryboardCompletedHandler = DirectUI::ToolTip::ForceFinishClosing;
                HIDWORD(spClosedStateStoryboardCompletedHandler) = v72;
                v50 = spClosedStateStoryboardCompletedHandler;
                *(_QWORD *)FailFast = DirectUI::ClassMemberEventHandler<DirectUI::ToolTip,Windows::UI::Xaml::Controls::IToolTip,Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable>::`vftable';
                *((_DWORD *)FailFast + 2) = 1;
                *(_OWORD *)(FailFast + 24) = v50;
                ctl::as_weakref(
                  (IWeakReference **)FailFast + 2,
                  (IInspectable *)((unsigned __int64)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl3,DirectUI::ControlGenerated>
                                 & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64)));
                v25 = v27;
                v28 = v27;
                *(_QWORD *)&spClosedStateStoryboardCompletedHandler = v27;
              }
              else
              {
                v27 = 0;
                v28 = 0;
              }
              v29 = spState.ptr_;
              get_Storyboard = spState.ptr_->get_Storyboard;
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStoryboard);
              v31 = get_Storyboard(v29, &spStoryboard.ptr_);
              v32 = v31;
              if ( v31 < 0 )
              {
                OnFailure_2990_(v31);
                if ( v27 )
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v27 + 16LL))(v27);
                v43 = spStoryboard.ptr_;
                if ( spStoryboard.ptr_ )
                {
                  spStoryboard.ptr_ = 0;
                  v43->Release(v43);
                }
                v44 = spState.ptr_;
                if ( spState.ptr_ )
                {
                  spState.ptr_ = 0;
                  v44->Release(v44);
                }
                v45 = spVisualStates.ptr_;
                if ( spVisualStates.ptr_ )
                {
                  spVisualStates.ptr_ = 0;
                  v45->Release(v45);
                }
                v46 = spGroup.ptr_;
                if ( spGroup.ptr_ )
                {
                  spGroup.ptr_ = 0;
                  v46->Release(v46);
                }
                if ( strStateName._hstring )
                  WindowsDeleteString(strStateName._hstring);
                v47 = spChildVisualStateGroups.ptr_;
                if ( spChildVisualStateGroups.ptr_ )
                {
                  spChildVisualStateGroups.ptr_ = 0;
                  v47->Release(v47);
                }
                v48 = spFactory.ptr_;
                if ( spFactory.ptr_ )
                {
                  spFactory.ptr_ = 0;
                  v48->Release(v48);
                }
                v3->Release(v3);
                v49 = spChild.ptr_;
                if ( spChild.ptr_ )
                {
                  spChild.ptr_ = 0;
                  v49->Release(v49);
                }
                return v32;
              }
              v33 = spStoryboard.ptr_;
              if ( spStoryboard.ptr_ )
              {
                v42 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::Animation::IStoryboard *, char *, EventRegistrationToken *))spStoryboard.ptr_[-1].__vftable[1].Release)(
                        &spStoryboard.ptr_[-1],
                        v25,
                        &closedStateStoryboardCompletedToken);
                v5 = v42;
                if ( v42 < 0 )
                {
                  OnFailure_2990_(v42);
                  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spClosedStateStoryboardCompletedHandler);
                  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStoryboard);
LABEL_94:
                  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spState);
                  goto LABEL_96;
                }
                v33 = spStoryboard.ptr_;
              }
              if ( v28 )
              {
                (*(void (__fastcall **)(char *))(*(_QWORD *)v28 + 16LL))(v28);
                v33 = spStoryboard.ptr_;
              }
              if ( v33 )
              {
                spStoryboard.ptr_ = 0;
                v33->Release(v33);
              }
              v34 = spState.ptr_;
              if ( spState.ptr_ )
              {
                spState.ptr_ = 0;
                v34->Release(v34);
              }
              v35 = spVisualStates.ptr_;
              if ( spVisualStates.ptr_ )
              {
                spVisualStates.ptr_ = 0;
                v35->Release(v35);
              }
              v36 = spGroup.ptr_;
              if ( spGroup.ptr_ )
              {
                spGroup.ptr_ = 0;
                v36->Release(v36);
              }
              v6 = (DirectUI::Control *)v70;
LABEL_42:
              if ( strStateName._hstring )
                WindowsDeleteString(strStateName._hstring);
              goto LABEL_44;
            }
LABEL_95:
            OnFailure_2990_(v19);
LABEL_96:
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spVisualStates);
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spGroup);
          }
          Windows::Internal::String::~String(&strStateName);
          goto LABEL_101;
        }
LABEL_44:
        v37 = spChildVisualStateGroups.ptr_;
        if ( spChildVisualStateGroups.ptr_ )
        {
          spChildVisualStateGroups.ptr_ = 0;
          v37->Release(v37);
        }
        v38 = spFactory.ptr_;
        if ( spFactory.ptr_ )
        {
          spFactory.ptr_ = 0;
          v38->Release(v38);
        }
        goto LABEL_48;
      }
      OnFailure_2990_(v11);
    }
LABEL_101:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChildVisualStateGroups);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFactory);
LABEL_105:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChildAsFE);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChild);
    return v5;
  }
LABEL_48:
  bIgnored[0] = 0;
  v39 = DirectUI::Control::GoToState(v6, 0, L"Opened", bIgnored);
  v5 = v39;
  if ( v39 < 0 )
  {
    OnFailure_2990_(v39);
    if ( v3 )
LABEL_50:
      v3->Release(v3);
    goto LABEL_51;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChildAsFE);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spChild);
  return 0;
}

```

## disassembly

```asm
0x180501f00  push    rbp
0x180501f02  push    rbx
0x180501f03  push    rsi
0x180501f04  push    rdi
0x180501f05  push    r12
0x180501f07  push    r13
0x180501f09  push    r14
0x180501f0b  push    r15
0x180501f0d  lea     rbp, [rsp-1Fh]
0x180501f12  sub     rsp, 0D8h
0x180501f19  mov     rax, cs:__security_cookie
0x180501f20  xor     rax, rsp
0x180501f23  mov     [rbp+57h+var_48], rax
0x180501f27  xor     esi, esi
0x180501f29  mov     r13, this
0x180501f2c  mov     [rbp+57h+spChild.ptr_], rsi
0x180501f30  mov     r14d, esi
0x180501f33  mov     [rbp+57h+spChildAsFE.ptr_], rsi
0x180501f37  mov     dword ptr [rbp+57h+spStoryboard.ptr_], esi
0x180501f3a  mov     [rbp+57h+nGroupCount], esi
0x180501f3d  mov     [rbp+57h+nStateCount], esi
0x180501f40  mov     [rbp+57h+closedStateStoryboardCompletedToken.value], rsi
0x180501f44  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x180501f49  mov     ebx, eax
0x180501f4b  test    eax, eax
0x180501f4d  js      loc_1805024FA
0x180501f53  lea     r12, [r13-168h]
0x180501f5a  mov     this, r12; pReference
0x180501f5d  mov     [rbp+57h+var_80], r12
0x180501f61  lea     rdx, [rbp+57h+spStoryboard]; pnCount
0x180501f65  call    ?GetChildrenCountStatic@VisualTreeHelper@DirectUI@@SAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAH@Z; DirectUI::VisualTreeHelper::GetChildrenCountStatic(Windows::UI::Xaml::IDependencyObject *,int *)
0x180501f6a  mov     ebx, eax
0x180501f6c  test    eax, eax
0x180501f6e  js      loc_1805026A1
0x180501f74  cmp     dword ptr [rbp+57h+spStoryboard.ptr_], esi
0x180501f77  jz      loc_1805022F9
0x180501f7d  lea     this, [rbp+57h+spChild]; this
0x180501f81  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180501f86  lea     r8, [rbp+57h+spChild]; ppDO
0x180501f8a  xor     edx, edx; nChildIndex
0x180501f8c  mov     this, r12; pReference
0x180501f8f  call    ?GetChildStatic@VisualTreeHelper@DirectUI@@SAJPEAUIDependencyObject@Xaml@UI@Windows@@HPEAPEAU3456@@Z; DirectUI::VisualTreeHelper::GetChildStatic(Windows::UI::Xaml::IDependencyObject *,int,Windows::UI::Xaml::IDependencyObject * *)
0x180501f94  mov     ebx, eax
0x180501f96  test    eax, eax
0x180501f98  js      loc_18050267F
0x180501f9e  lea     this, [rbp+57h+spState]; this
0x180501fa2  mov     [rbp+57h+spState.ptr_], rsi
0x180501fa6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180501fab  mov     this, [rbp+57h+spChild.ptr_]
0x180501faf  test    this, this
0x180501fb2  jz      short loc_180501FCA
0x180501fb4  mov     rax, [this]
0x180501fb7  lea     r8, [rbp+57h+spState]
0x180501fbb  lea     rdx, _GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf
0x180501fc2  mov     rax, [rax]
0x180501fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180501fca  mov     r14, [rbp+57h+spState.ptr_]
0x180501fce  mov     [rbp+57h+spChildAsFE.ptr_], r14
0x180501fd2  test    r14, r14
0x180501fd5  jz      loc_1805022F9
0x180501fdb  lea     this, [rsp+110h+spFactory]; ppNewInstance
0x180501fe0  mov     [rsp+110h+spFactory.ptr_], rsi
0x180501fe5  mov     [rsp+110h+spChildVisualStateGroups.ptr_], rsi
0x180501fea  call    ??$make@VVisualStateManagerFactory@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VVisualStateManagerFactory@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::VisualStateManagerFactory>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::VisualStateManagerFactory>>)
0x180501fef  mov     ebx, eax
0x180501ff1  test    eax, eax
0x180501ff3  js      loc_180502662
0x180501ff9  mov     rdi, [rsp+110h+spFactory.ptr_]
0x180501ffe  lea     this, [rsp+110h+spChildVisualStateGroups]; this
0x180502003  mov     rax, [rdi+30h]
0x180502007  mov     rbx, [rax+30h]
0x18050200b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180502010  lea     r8, [rsp+110h+spChildVisualStateGroups]
0x180502015  mov     rdx, r14
0x180502018  lea     this, [rdi+30h]
0x18050201c  mov     rax, rbx
0x18050201f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502024  mov     ebx, eax
0x180502026  test    eax, eax
0x180502028  js      loc_180502659
0x18050202e  cmp     [rsp+110h+spChildVisualStateGroups.ptr_], rsi
0x180502033  jz      loc_1805022C3
0x180502039  lea     r9, [rbp+57h+strClosedStateName]; string
0x18050203d  mov     [rbp+57h+strStateName._hstring], rsi
0x180502041  lea     r8, [rbp+57h+strClosedStateName._header]; hstringHeader
0x180502045  mov     edx, 6; length
0x18050204a  lea     this, aClosed; "Closed"
0x180502051  call    cs:__imp_WindowsCreateStringReference
0x180502057  test    eax, eax
0x180502059  js      loc_1805025D1
0x18050205f  mov     this, [rsp+110h+spChildVisualStateGroups.ptr_]
0x180502064  lea     rdx, [rbp+57h+nGroupCount]
0x180502068  mov     rax, [this]
0x18050206b  mov     rax, [rax+38h]
0x18050206f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502074  mov     ebx, eax
0x180502076  test    eax, eax
0x180502078  js      loc_180502647
0x18050207e  mov     r15d, esi
0x180502081  cmp     r15d, [rbp+57h+nGroupCount]
0x180502085  jnb     loc_1805022B4
0x18050208b  mov     rdi, [rsp+110h+spChildVisualStateGroups.ptr_]
0x180502090  lea     this, [rsp+110h+spGroup]; this
0x180502095  mov     [rsp+110h+spGroup.ptr_], rsi
0x18050209a  mov     [rsp+110h+spVisualStates.ptr_], rsi
0x18050209f  mov     rax, [rdi]
0x1805020a2  mov     rbx, [rax+30h]
0x1805020a6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1805020ab  lea     r8, [rsp+110h+spGroup]
0x1805020b0  mov     edx, r15d
0x1805020b3  mov     this, rdi
0x1805020b6  mov     rax, rbx
0x1805020b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805020be  mov     ebx, eax
0x1805020c0  test    eax, eax
0x1805020c2  js      loc_180502506
0x1805020c8  mov     rdi, [rsp+110h+spGroup.ptr_]
0x1805020cd  lea     this, [rsp+110h+spVisualStates]; this
0x1805020d2  mov     eax, 0B8h
0x1805020d7  test    rdi, rdi
0x1805020da  cmovz   rdi, rax
0x1805020de  mov     rax, [rdi]
0x1805020e1  mov     rbx, [rax+40h]
0x1805020e5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1805020ea  lea     rdx, [rsp+110h+spVisualStates]
0x1805020ef  mov     this, rdi
0x1805020f2  mov     rax, rbx
0x1805020f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805020fa  mov     ebx, eax
0x1805020fc  test    eax, eax
0x1805020fe  js      loc_18050262A
0x180502104  mov     this, [rsp+110h+spVisualStates.ptr_]
0x180502109  test    this, this
0x18050210c  jz      loc_1805025AE
0x180502112  mov     rax, [this]
0x180502115  lea     rdx, [rbp+57h+nStateCount]
0x180502119  mov     rax, [rax+38h]
0x18050211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502122  mov     ebx, eax
0x180502124  test    eax, eax
0x180502126  js      loc_180502621
0x18050212c  xor     edi, edi
0x18050212e  cmp     esi, [rbp+57h+nStateCount]
0x180502131  jnb     loc_180502591
0x180502137  mov     [rbp+57h+spState.ptr_], rdi
0x18050213b  lea     this, [rbp+57h+spState]; this
0x18050213f  mov     rdi, [rsp+110h+spVisualStates.ptr_]
0x180502144  mov     rax, [rdi]
0x180502147  mov     rbx, [rax+30h]
0x18050214b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180502150  lea     r8, [rbp+57h+spState]
0x180502154  mov     edx, esi
0x180502156  mov     this, rdi
0x180502159  mov     rax, rbx
0x18050215c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502161  mov     ebx, eax
0x180502163  test    eax, eax
0x180502165  js      loc_18050260F
0x18050216b  mov     rdi, [rbp+57h+spState.ptr_]
0x18050216f  mov     this, [rbp+57h+strStateName._hstring]; string
0x180502173  mov     rax, [rdi]
0x180502176  mov     rbx, [rax+30h]
0x18050217a  call    cs:__imp_WindowsDeleteString
0x180502180  lea     rdx, [rbp+57h+strStateName]
0x180502184  mov     [rbp+57h+strStateName._hstring], 0
0x18050218c  mov     this, rdi
0x18050218f  mov     rax, rbx
0x180502192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502197  xor     edi, edi
0x180502199  mov     ebx, eax
0x18050219b  test    eax, eax
0x18050219d  js      loc_180502606
0x1805021a3  mov     rdx, [rbp+57h+strClosedStateName._hstring]; string2
0x1805021a7  lea     r8, [rbp+57h+spStoryboard]; result
0x1805021ab  mov     this, [rbp+57h+strStateName._hstring]; string1
0x1805021af  mov     dword ptr [rbp+57h+spStoryboard.ptr_], edi
0x1805021b2  call    cs:__imp_WindowsCompareStringOrdinal
0x1805021b8  cmp     dword ptr [rbp+57h+spStoryboard.ptr_], edi
0x1805021bb  jz      short loc_1805021CD
0x1805021bd  lea     this, [rbp+57h+spState]; this
0x1805021c1  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1805021c6  inc     esi
0x1805021c8  jmp     loc_18050212E
0x1805021cd  mov     rbx, rdi
0x1805021d0  mov     [rbp+57h+spStoryboard.ptr_], rdi
0x1805021d4  mov     ecx, 28h ; '('; cSize
0x1805021d9  mov     [rbp+57h+spClosedStateStoryboardCompletedHandler.ptr_], rbx
0x1805021dd  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1805021e2  mov     r15, rax
0x1805021e5  test    rax, rax
0x1805021e8  jnz     loc_18050249F
0x1805021ee  mov     r15, rdi
0x1805021f1  mov     r12, rdi
0x1805021f4  mov     rsi, [rbp+57h+spState.ptr_]
0x1805021f8  lea     this, [rbp+57h+spStoryboard]; this
0x1805021fc  mov     rax, [rsi]
0x1805021ff  mov     rdi, [rax+38h]
0x180502203  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180502208  lea     rdx, [rbp+57h+spStoryboard]
0x18050220c  mov     this, rsi
0x18050220f  mov     rax, rdi
0x180502212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502217  xor     esi, esi
0x180502219  mov     edi, eax
0x18050221b  test    eax, eax
0x18050221d  js      loc_1805023A8
0x180502223  mov     rdx, [rbp+57h+spStoryboard.ptr_]
0x180502227  test    rdx, rdx
0x18050222a  jnz     loc_180502372
0x180502230  test    r12, r12
0x180502233  jz      short loc_180502249
0x180502235  mov     rax, [r12]
0x180502239  mov     this, r12
0x18050223c  mov     rax, [rax+10h]
0x180502240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502245  mov     rdx, [rbp+57h+spStoryboard.ptr_]
0x180502249  test    rdx, rdx
0x18050224c  jz      short loc_180502261
0x18050224e  mov     [rbp+57h+spStoryboard.ptr_], rsi
0x180502252  mov     this, rdx
0x180502255  mov     rax, [rdx]
0x180502258  mov     rax, [rax+10h]
0x18050225c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502261  mov     this, [rbp+57h+spState.ptr_]
0x180502265  test    this, this
0x180502268  jz      short loc_18050227A
0x18050226a  mov     [rbp+57h+spState.ptr_], rsi
0x18050226e  mov     rax, [this]
0x180502271  mov     rax, [rax+10h]
0x180502275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050227a  mov     this, [rsp+110h+spVisualStates.ptr_]
0x18050227f  test    this, this
0x180502282  jz      short loc_180502295
0x180502284  mov     [rsp+110h+spVisualStates.ptr_], rsi
0x180502289  mov     rax, [this]
0x18050228c  mov     rax, [rax+10h]
0x180502290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502295  mov     this, [rsp+110h+spGroup.ptr_]
0x18050229a  test    this, this
0x18050229d  jz      short loc_1805022B0
0x18050229f  mov     [rsp+110h+spGroup.ptr_], rsi
0x1805022a4  mov     rax, [this]
0x1805022a7  mov     rax, [rax+10h]
0x1805022ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805022b0  mov     r12, [rbp+57h+var_80]
0x1805022b4  mov     this, [rbp+57h+strStateName._hstring]; string
0x1805022b8  test    this, this
0x1805022bb  jz      short loc_1805022C3
0x1805022bd  call    cs:__imp_WindowsDeleteString
0x1805022c3  mov     this, [rsp+110h+spChildVisualStateGroups.ptr_]
0x1805022c8  test    this, this
0x1805022cb  jz      short loc_1805022DE
0x1805022cd  mov     [rsp+110h+spChildVisualStateGroups.ptr_], rsi
0x1805022d2  mov     rax, [this]
0x1805022d5  mov     rax, [rax+10h]
0x1805022d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805022de  mov     this, [rsp+110h+spFactory.ptr_]
0x1805022e3  test    this, this
0x1805022e6  jz      short loc_1805022F9
0x1805022e8  mov     [rsp+110h+spFactory.ptr_], rsi
0x1805022ed  mov     rax, [this]
0x1805022f0  mov     rax, [rax+10h]
0x1805022f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805022f9  lea     r9, [rbp+57h+bIgnored]; pbReturnValue
0x1805022fd  mov     [rbp+57h+bIgnored], sil
0x180502301  lea     r8, aOpened; "Opened"
0x180502308  xor     edx, edx; bUseTransitions
0x18050230a  mov     this, r12; this
0x18050230d  call    ?GoToState@Control@DirectUI@@IEAAJ_NPEBGPEAE@Z; DirectUI::Control::GoToState(bool,ushort const *,uchar *)
0x180502312  mov     ebx, eax
0x180502314  test    eax, eax
0x180502316  jns     loc_180502688
0x18050231c  mov     ecx, eax; failedFrameHR
0x18050231e  call    OnFailure_2990_
0x180502323  test    r14, r14
0x180502326  jz      short loc_180502337
0x180502328  mov     rax, [r14]
0x18050232b  mov     this, r14
0x18050232e  mov     rax, [rax+10h]
0x180502332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502337  mov     this, [rbp+57h+spChild.ptr_]
0x18050233b  test    this, this
0x18050233e  jz      short loc_180502350
0x180502340  mov     [rbp+57h+spChild.ptr_], rsi
0x180502344  mov     rax, [this]
0x180502347  mov     rax, [rax+10h]
0x18050234b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180502350  mov     eax, ebx
0x180502352  mov     this, [rbp+57h+var_48]
0x180502356  xor     this, rsp; StackCookie
0x180502359  call    __security_check_cookie
0x18050235e  add     rsp, 0D8h
0x180502365  pop     r15
0x180502367  pop     r14
0x180502369  pop     r13
0x18050236b  pop     r12
0x18050236d  pop     rdi
0x18050236e  pop     rsi
0x18050236f  pop     rbx
0x180502370  pop     rbp
  ... truncated ...
```
