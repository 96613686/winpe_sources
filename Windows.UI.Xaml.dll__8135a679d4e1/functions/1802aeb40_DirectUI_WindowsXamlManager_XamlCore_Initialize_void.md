# DirectUI::WindowsXamlManager::XamlCore::Initialize(void)

- ea: `0x1802aeb40`
- end: `0x1802aeea3`
- name: `?Initialize@XamlCore@WindowsXamlManager@DirectUI@@QEAAJXZ`
- size: `867`
- prototype: `HRESULT __fastcall(DirectUI::WindowsXamlManager::XamlCore *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802ae470`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18004bfd0`
- `0x1801df610`
- `0x1801f2f30`
- `0x18027aaa0`
- `0x1802ae360`
- `0x1802aeb40`
- `0x18033d8a4`
- `0x180358780`
- `0x1804b4ed0`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180bbb388`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802aedd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802aee71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802aedd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802aee71`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802aee0a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802aee0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802aebf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802aece9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802aebf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802aece9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802aec1e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802aec1e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1802aed02`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1802aed02`

## string_xrefs

- `0x1802aece2`: `Cannot activate WindowsXamlManager. Previous instance is still closing, please drain the Dispatcher before continue. See: https://go.microsoft.com/fwlink/?linkid=875495`

## pseudocode

```c
__int64 __fastcall DirectUI::WindowsXamlManager::XamlCore::Initialize(DirectUI::WindowsXamlManager::XamlCore *this)
{
  __int64 v2; // rdx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  DirectUI::FrameworkApplication *CurrentNoRef; // rax
  HSTRING v6; // rbx
  HRESULT ActivationFactory; // eax
  Windows::ApplicationModel::Core::ICoreApplicationPrivate2 *v8; // rdi
  HRESULT (__fastcall *CreateNonImmersiveView)(Windows::ApplicationModel::Core::ICoreApplicationPrivate2 *, Windows::ApplicationModel::Core::ICoreApplicationView **); // rbx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate2 *v10; // rcx
  DirectUI::FrameworkApplication *v11; // rcx
  HRESULT v13; // ecx
  DirectUI::DXamlCore *Current; // rdi
  HRESULT v15; // eax
  FrameworkTheming *Myval2; // rbx
  Theming::Theme v17; // edx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate2 *v18; // rcx
  DirectUI::FrameworkApplication *v19; // rcx
  HRESULT v20; // eax
  DirectUI::FrameworkApplication *ptr; // rbx
  ctl::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate2> spCoreApp; // [rsp+20h] [rbp-50h] BYREF
  ctl::ComPtr<DirectUI::FrameworkApplication> frameworkApplication; // [rsp+28h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo> cStowedExceptions; // [rsp+30h] [rbp-40h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_BYTE *)(v2 + 24) )
  {
    if ( WindowsCreateStringReference(
           L"Cannot activate WindowsXamlManager. Previous instance is still closing, please drain the Dispatcher before co"
            "ntinue. See: https://go.microsoft.com/fwlink/?linkid=875495",
           0xA8u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = -2147418113;
    RoOriginateError(2147549183LL, string);
    OnFailure_3652_(v13);
    return v4;
  }
  if ( *(_BYTE *)(v2 + 25) )
  {
    OnFailure_3652_(tls_index);
    ppStowedExceptions = 0;
    LODWORD(cStowedExceptions.ptr_) = 0;
    TraceForFailFast(-2147418113);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(-2147418113, (unsigned int)cStowedExceptions.ptr_, ppStowedExceptions);
  }
  v3 = DirectUI::WindowsXamlManager::XamlCore::ConfigureCoreWindow(this);
  v4 = v3;
  if ( v3 < 0 )
  {
    OnFailure_2990_(v3);
    return v4;
  }
  CurrentNoRef = DirectUI::FrameworkApplication::GetCurrentNoRef();
  frameworkApplication.ptr_ = CurrentNoRef;
  if ( CurrentNoRef )
  {
    CurrentNoRef->AddRef(CurrentNoRef);
  }
  else
  {
    v20 = ctl::make<DirectUI::FrameworkApplication>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::FrameworkApplication> >)&frameworkApplication);
    v4 = v20;
    if ( v20 < 0 )
    {
      OnFailure_2990_(v20);
LABEL_37:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&frameworkApplication);
      return v4;
    }
    ptr = frameworkApplication.ptr_;
    if ( this->m_frameworkApplication.ptr_ != frameworkApplication.ptr_ )
    {
      cStowedExceptions.ptr_ = (Windows::ApplicationModel::Activation::ITileActivatedInfo *)frameworkApplication.ptr_;
      Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(&cStowedExceptions);
      cStowedExceptions.ptr_ = (Windows::ApplicationModel::Activation::ITileActivatedInfo *)this->m_frameworkApplication.ptr_;
      this->m_frameworkApplication.ptr_ = ptr;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&cStowedExceptions);
    }
  }
  spCoreApp.ptr_ = 0;
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_ApplicationModel_Core_CoreApplication,
         0x2Du,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCoreApp);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_6090202d_2843_4ba5_9b0d_fc88eecd9ce5, &spCoreApp);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0
    || (v8 = spCoreApp.ptr_,
        CreateNonImmersiveView = spCoreApp.ptr_->CreateNonImmersiveView,
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)this),
        ActivationFactory = CreateNonImmersiveView(v8, &this->m_spCoreAppView.ptr_),
        v4 = ActivationFactory,
        ActivationFactory < 0)
    || (ActivationFactory = frameworkApplication.ptr_->StartOnCurrentThread(
                              &frameworkApplication.ptr_->Windows::UI::Xaml::IFrameworkApplicationPrivate,
                              0),
        v4 = ActivationFactory,
        ActivationFactory < 0) )
  {
    OnFailure_2990_(ActivationFactory);
    v10 = spCoreApp.ptr_;
    if ( spCoreApp.ptr_ )
    {
      spCoreApp.ptr_ = 0;
      v10->Release(v10);
    }
    v11 = frameworkApplication.ptr_;
    if ( frameworkApplication.ptr_ )
    {
      frameworkApplication.ptr_ = 0;
      v11->Release(v11);
    }
    return v4;
  }
  Current = DirectUI::DXamlCore::GetCurrent();
  v15 = DirectUI::DXamlCore::EnsureCoreApplicationInitialized(Current);
  v4 = v15;
  if ( v15 < 0 )
    goto LABEL_36;
  if ( !XamlOneCoreTransforms::s_initialized )
    XamlOneCoreTransforms::s_initialized = 1;
  Myval2 = Current->m_hCore->m_spTheming._Mypair._Myval2;
  LOBYTE(v17) = DirectUI::FrameworkApplication::GetApplicationRequestedTheme();
  v15 = FrameworkTheming::SetRequestedTheme(Myval2, v17, 1);
  v4 = v15;
  if ( v15 < 0 )
  {
LABEL_36:
    OnFailure_2990_(v15);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCoreApp);
    goto LABEL_37;
  }
  v18 = spCoreApp.ptr_;
  DirectUI::DXamlCore::s_enableNotifyEndOfReferenceTrackingOnThread = 0;
  if ( spCoreApp.ptr_ )
  {
    spCoreApp.ptr_ = 0;
    v18->Release(v18);
  }
  v19 = frameworkApplication.ptr_;
  if ( frameworkApplication.ptr_ )
  {
    frameworkApplication.ptr_ = 0;
    v19->Release(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1802aeb40  mov     [rsp-18h+arg_8], rbx
0x1802aeb45  mov     [rsp-18h+arg_10], rsi
0x1802aeb4a  push    rbp
0x1802aeb4b  push    rdi
0x1802aeb4c  push    r14
0x1802aeb4e  mov     rbp, rsp
0x1802aeb51  sub     rsp, 70h
0x1802aeb55  mov     rax, cs:__security_cookie
0x1802aeb5c  xor     rax, rsp
0x1802aeb5f  mov     [rbp+var_10], rax
0x1802aeb63  mov     rax, gs:58h
0x1802aeb6c  mov     rsi, this
0x1802aeb6f  mov     ecx, cs:_tls_index; failedFrameHR
0x1802aeb75  xor     r14d, r14d
0x1802aeb78  mov     rdx, [rax+this*8]
0x1802aeb7c  mov     eax, 18h
0x1802aeb81  cmp     [rax+rdx], r14b
0x1802aeb85  jnz     loc_1802AECD5
0x1802aeb8b  mov     eax, 19h
0x1802aeb90  cmp     [rax+rdx], r14b
0x1802aeb94  jnz     loc_1802AEDDB
0x1802aeb9a  mov     this, rsi; this
0x1802aeb9d  call    ?ConfigureCoreWindow@XamlCore@WindowsXamlManager@DirectUI@@AEAAJXZ; DirectUI::WindowsXamlManager::XamlCore::ConfigureCoreWindow(void)
0x1802aeba2  mov     ebx, eax
0x1802aeba4  test    eax, eax
0x1802aeba6  js      loc_1802AED0F
0x1802aebac  call    ?GetCurrentNoRef@FrameworkApplication@DirectUI@@SAPEAV12@XZ; DirectUI::FrameworkApplication::GetCurrentNoRef(void)
0x1802aebb1  mov     [rbp+frameworkApplication.ptr_], rax
0x1802aebb5  test    rax, rax
0x1802aebb8  jz      loc_1802AEE15
0x1802aebbe  mov     this, [rax]
0x1802aebc1  mov     rdx, [this+8]
0x1802aebc5  mov     this, rax
0x1802aebc8  mov     rax, rdx
0x1802aebcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aebd0  mov     rax, [rbp+frameworkApplication.ptr_]
0x1802aebd4  test    rax, rax
0x1802aebd7  jz      loc_1802AEE15
0x1802aebdd  lea     r9, [rbp+string]; string
0x1802aebe1  mov     [rbp+spCoreApp.ptr_], r14
0x1802aebe5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1802aebe9  mov     edx, 2Dh ; '-'; length
0x1802aebee  lea     this, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; sourceString
0x1802aebf5  call    cs:__imp_WindowsCreateStringReference
0x1802aebfb  test    eax, eax
0x1802aebfd  js      loc_1802AEE62
0x1802aec03  mov     rbx, [rbp+string]
0x1802aec07  lea     this, [rbp+spCoreApp]; this
0x1802aec0b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1802aec10  lea     r8, [rbp+spCoreApp]
0x1802aec14  mov     this, rbx
0x1802aec17  lea     rdx, _GUID_6090202d_2843_4ba5_9b0d_fc88eecd9ce5
0x1802aec1e  call    cs:__imp_RoGetActivationFactory
0x1802aec24  mov     ebx, eax
0x1802aec26  test    eax, eax
0x1802aec28  js      loc_1802AEDA9
0x1802aec2e  mov     rdi, [rbp+spCoreApp.ptr_]
0x1802aec32  mov     this, rsi; this
0x1802aec35  mov     rax, [rdi]
0x1802aec38  mov     rbx, [rax+40h]
0x1802aec3c  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1802aec41  mov     rdx, rsi
0x1802aec44  mov     this, rdi
0x1802aec47  mov     rax, rbx
0x1802aec4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aec4f  mov     ebx, eax
0x1802aec51  test    eax, eax
0x1802aec53  js      loc_1802AEDB5
0x1802aec59  mov     this, [rbp+frameworkApplication.ptr_]
0x1802aec5d  xor     edx, edx
0x1802aec5f  add     this, 68h ; 'h'
0x1802aec63  mov     rax, [this]
0x1802aec66  mov     rax, [rax+30h]
0x1802aec6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aec6f  mov     ebx, eax
0x1802aec71  test    eax, eax
0x1802aec73  jns     loc_1802AED18
0x1802aec79  mov     ecx, eax; failedFrameHR
0x1802aec7b  call    OnFailure_2990_
0x1802aec80  mov     this, [rbp+spCoreApp.ptr_]
0x1802aec84  test    this, this
0x1802aec87  jz      short loc_1802AEC99
0x1802aec89  mov     [rbp+spCoreApp.ptr_], r14
0x1802aec8d  mov     rax, [this]
0x1802aec90  mov     rax, [rax+10h]
0x1802aec94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aec99  mov     this, [rbp+frameworkApplication.ptr_]
0x1802aec9d  test    this, this
0x1802aeca0  jz      short loc_1802AECB2
0x1802aeca2  mov     [rbp+frameworkApplication.ptr_], r14
0x1802aeca6  mov     rax, [this]
0x1802aeca9  mov     rax, [rax+10h]
0x1802aecad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aecb2  mov     eax, ebx
0x1802aecb4  mov     this, [rbp+var_10]
0x1802aecb8  xor     this, rsp; StackCookie
0x1802aecbb  call    __security_check_cookie
0x1802aecc0  lea     r11, [rsp+70h+var_s0]
0x1802aecc5  mov     rbx, [r11+28h]
0x1802aecc9  mov     rsi, [r11+30h]
0x1802aeccd  mov     rsp, r11
0x1802aecd0  pop     r14
0x1802aecd2  pop     rdi
0x1802aecd3  pop     rbp
0x1802aecd4  retn
0x1802aecd5  lea     r9, [rbp+string]; string
0x1802aecd9  mov     edx, 0A8h; length
0x1802aecde  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1802aece2  lea     this, aCannotActivate_0; "Cannot activate WindowsXamlManager. Pre"...
0x1802aece9  call    cs:__imp_WindowsCreateStringReference
0x1802aecef  test    eax, eax
0x1802aecf1  js      loc_1802AEDC1
0x1802aecf7  mov     rdx, [rbp+string]
0x1802aecfb  mov     ebx, 8000FFFFh
0x1802aed00  mov     ecx, ebx
0x1802aed02  call    cs:__imp_RoOriginateError
0x1802aed08  call    OnFailure_3652_
0x1802aed0d  jmp     short loc_1802AECB2
0x1802aed0f  mov     ecx, ebx; failedFrameHR
0x1802aed11  call    OnFailure_2990_
0x1802aed16  jmp     short loc_1802AECB2
0x1802aed18  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1802aed1d  mov     this, rax; this
0x1802aed20  mov     rdi, rax
0x1802aed23  call    ?EnsureCoreApplicationInitialized@DXamlCore@DirectUI@@QEAAJXZ; DirectUI::DXamlCore::EnsureCoreApplicationInitialized(void)
0x1802aed28  mov     ebx, eax
0x1802aed2a  test    eax, eax
0x1802aed2c  js      loc_1802AEE85
0x1802aed32  cmp     cs:?s_initialized@XamlOneCoreTransforms@@0_NA, r14b; bool XamlOneCoreTransforms::s_initialized
0x1802aed39  jnz     short loc_1802AED42
0x1802aed3b  mov     cs:?s_initialized@XamlOneCoreTransforms@@0_NA, 1; bool XamlOneCoreTransforms::s_initialized
0x1802aed42  mov     rax, [rdi+28h]
0x1802aed46  mov     rbx, [rax+698h]
0x1802aed4d  call    ?GetApplicationRequestedTheme@FrameworkApplication@DirectUI@@SA?AW4Theme@Theming@@XZ; DirectUI::FrameworkApplication::GetApplicationRequestedTheme(void)
0x1802aed52  mov     r8b, 1; doNotifyThemeChange
0x1802aed55  mov     dl, al; requestedTheme
0x1802aed57  mov     this, rbx; this
0x1802aed5a  call    ?SetRequestedTheme@FrameworkTheming@@QEAAJW4Theme@Theming@@_N@Z; FrameworkTheming::SetRequestedTheme(Theming::Theme,bool)
0x1802aed5f  mov     ebx, eax
0x1802aed61  test    eax, eax
0x1802aed63  js      loc_1802AEE7C
0x1802aed69  mov     this, [rbp+spCoreApp.ptr_]
0x1802aed6d  mov     cs:?s_enableNotifyEndOfReferenceTrackingOnThread@DXamlCore@DirectUI@@0_NA, r14b; bool DirectUI::DXamlCore::s_enableNotifyEndOfReferenceTrackingOnThread
0x1802aed74  test    this, this
0x1802aed77  jz      short loc_1802AED89
0x1802aed79  mov     [rbp+spCoreApp.ptr_], r14
0x1802aed7d  mov     rax, [this]
0x1802aed80  mov     rax, [rax+10h]
0x1802aed84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aed89  mov     this, [rbp+frameworkApplication.ptr_]
0x1802aed8d  test    this, this
0x1802aed90  jz      short loc_1802AEDA2
0x1802aed92  mov     [rbp+frameworkApplication.ptr_], r14
0x1802aed96  mov     rax, [this]
0x1802aed99  mov     rax, [rax+10h]
0x1802aed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aeda2  xor     eax, eax
0x1802aeda4  jmp     loc_1802AECB4
0x1802aeda9  mov     ecx, ebx; failedFrameHR
0x1802aedab  call    OnFailure_2990_
0x1802aedb0  jmp     loc_1802AEC80
0x1802aedb5  mov     ecx, ebx; failedFrameHR
0x1802aedb7  call    OnFailure_2990_
0x1802aedbc  jmp     loc_1802AEC80
0x1802aedc1  xor     r9d, r9d; lpArguments
0x1802aedc4  xor     r8d, r8d; nNumberOfArguments
0x1802aedc7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802aedcc  lea     edx, [r9+1]; dwExceptionFlags
0x1802aedd0  call    cs:__imp_RaiseException
0x1802aedd6  jmp     loc_1802AECF7
0x1802aeddb  call    OnFailure_3652_
0x1802aede0  mov     ebx, 8000FFFFh
0x1802aede5  mov     [rbp+ppStowedExceptions], r14
0x1802aede9  mov     ecx, ebx; errorCode
0x1802aedeb  mov     dword ptr [rbp+cStowedExceptions], r14d
0x1802aedef  call    TraceForFailFast
0x1802aedf4  lea     rdx, [rbp+cStowedExceptions]; pcStowedExceptions
0x1802aedf8  lea     this, [rbp+ppStowedExceptions]; pppStowedExceptions
0x1802aedfc  call    GetStowedExceptionsForFailFast
0x1802aee01  mov     r8, [rbp+ppStowedExceptions]
0x1802aee05  mov     ecx, ebx
0x1802aee07  mov     edx, dword ptr [rbp+cStowedExceptions]
0x1802aee0a  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1802aee10  jmp     loc_1802AEB9A
0x1802aee15  lea     this, [rbp+frameworkApplication]; ppNewInstance
0x1802aee19  call    ??$make@VFrameworkApplication@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VFrameworkApplication@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::FrameworkApplication>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::FrameworkApplication>>)
0x1802aee1e  mov     ebx, eax
0x1802aee20  test    eax, eax
0x1802aee22  js      short loc_1802AEE59
0x1802aee24  mov     rbx, [rbp+frameworkApplication.ptr_]
0x1802aee28  cmp     [rsi+8], rbx
0x1802aee2c  jz      loc_1802AEBDD
0x1802aee32  lea     this, [rbp+cStowedExceptions]; this
0x1802aee36  mov     [rbp+cStowedExceptions], rbx
0x1802aee3a  call    ?InternalAddRef@?$ComPtr@UICastingEventHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(void)
0x1802aee3f  mov     rax, [rsi+8]
0x1802aee43  lea     this, [rbp+cStowedExceptions]; this
0x1802aee47  mov     [rbp+cStowedExceptions], rax
0x1802aee4b  mov     [rsi+8], rbx
0x1802aee4f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1802aee54  jmp     loc_1802AEBDD
0x1802aee59  mov     ecx, eax; failedFrameHR
0x1802aee5b  call    OnFailure_2990_
0x1802aee60  jmp     short loc_1802AEE95
0x1802aee62  xor     r9d, r9d; lpArguments
0x1802aee65  xor     r8d, r8d; nNumberOfArguments
0x1802aee68  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802aee6d  lea     edx, [r9+1]; dwExceptionFlags
0x1802aee71  call    cs:__imp_RaiseException
0x1802aee77  jmp     loc_1802AEC03
0x1802aee7c  mov     ecx, eax; failedFrameHR
0x1802aee7e  call    OnFailure_2990_
0x1802aee83  jmp     short loc_1802AEE8C
0x1802aee85  mov     ecx, eax; failedFrameHR
0x1802aee87  call    OnFailure_2990_
0x1802aee8c  lea     this, [rbp+spCoreApp]; this
0x1802aee90  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1802aee95  lea     this, [rbp+frameworkApplication]; this
0x1802aee99  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1802aee9e  jmp     loc_1802AECB2
```
