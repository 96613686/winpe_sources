# DirectUI::CommandingHelpers::BindToDescriptionPropertiesIfUnset(Windows::UI::Xaml::Input::IXamlUICommand *,DirectUI::DependencyObject *)

- ea: `0x18034ca9c`
- end: `0x18034cdd5`
- name: `?BindToDescriptionPropertiesIfUnset@CommandingHelpers@DirectUI@@YAJPEAUIXamlUICommand@Input@Xaml@UI@Windows@@PEAVDependencyObject@2@@Z`
- size: `825`
- prototype: `HRESULT __fastcall(Windows::UI::Xaml::Input::IXamlUICommand *uiCommand, DirectUI::DependencyObject *target)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18034b3c0`
- `0x18034bb68`
- `0x180b7a738`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005bcac`
- `0x18005e298`
- `0x18034ca9c`
- `0x18034d0d4`
- `0x18034d3ec`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18034cda4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18034cdbe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18034cda4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18034cdbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cafb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cbf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cafb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cbf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ccfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18034cb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18034cbbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18034cb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18034cbbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18034cc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18034cd57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18034cc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18034cd57`

## pseudocode

```c
__int64 __fastcall DirectUI::CommandingHelpers::BindToDescriptionPropertiesIfUnset(
        Windows::UI::Xaml::Input::IXamlUICommand *uiCommand,
        DirectUI::DependencyObject *target)
{
  Windows::UI::Xaml::Input::IXamlUICommand_vtbl *v2; // rax
  HRESULT (__fastcall *get_Description)(Windows::UI::Xaml::Input::IXamlUICommand *, HSTRING__ **); // rbx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  HRESULT ValueByKnownIndex; // eax
  HSTRING__ *hstring; // rbx
  HRESULT v10; // eax
  unsigned int v11; // edi
  HRESULT AttachedValueByKnown; // eax
  HRESULT StringFromObject; // eax
  IInspectable *v14; // rcx
  IInspectable *ptr; // rcx
  HSTRING__ *v17; // rdi
  ctl::ComPtr<IInspectable> localToolTipAsI; // [rsp+30h] [rbp-50h] BYREF
  Windows::Internal::String descriptionFromCommand; // [rsp+38h] [rbp-48h] BYREF
  Windows::Internal::String localHelpText; // [rsp+40h] [rbp-40h] BYREF
  Windows::Internal::String localToolTipAsString; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  v2 = uiCommand->__vftable;
  descriptionFromCommand._hstring = 0;
  get_Description = v2->get_Description;
  WindowsDeleteString(0);
  descriptionFromCommand._hstring = 0;
  v6 = get_Description(uiCommand, &descriptionFromCommand._hstring);
  v7 = v6;
  if ( v6 < 0 )
  {
    OnFailure_2990_(v6);
  }
  else
  {
    WindowsDeleteString(0);
    localHelpText._hstring = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          target,
                          AutomationProperties_HelpText,
                          &localHelpText._hstring);
    v7 = ValueByKnownIndex;
    if ( ValueByKnownIndex >= 0 )
    {
      hstring = localHelpText._hstring;
      if ( !localHelpText._hstring || WindowsIsStringEmpty(localHelpText._hstring) )
      {
        if ( WindowsCreateStringReference(L"Description", 0xBu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v10 = DirectUI::DXamlCore::SetBinding(uiCommand, string, target, AutomationProperties_HelpText, 0);
        v11 = v10;
        if ( v10 < 0 )
        {
          OnFailure_2990_(v10);
LABEL_34:
          if ( hstring )
            WindowsDeleteString(hstring);
          if ( descriptionFromCommand._hstring )
            WindowsDeleteString(descriptionFromCommand._hstring);
          return v11;
        }
      }
      localToolTipAsI.ptr_ = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&localToolTipAsI);
      AttachedValueByKnown = DirectUI::DependencyObject::GetAttachedValueByKnownIndex<IInspectable *>(
                               target,
                               ToolTipService_ToolTip,
                               &localToolTipAsI.ptr_);
      v11 = AttachedValueByKnown;
      if ( AttachedValueByKnown < 0 )
      {
        OnFailure_2990_(AttachedValueByKnown);
LABEL_32:
        ptr = localToolTipAsI.ptr_;
        if ( localToolTipAsI.ptr_ )
        {
          localToolTipAsI.ptr_ = 0;
          ptr->Release(ptr);
        }
        goto LABEL_34;
      }
      localToolTipAsString._hstring = 0;
      if ( !localToolTipAsI.ptr_ )
        goto LABEL_9;
      WindowsDeleteString(0);
      localToolTipAsString._hstring = 0;
      StringFromObject = DirectUI::FrameworkElement::GetStringFromObject(
                           localToolTipAsI.ptr_,
                           &localToolTipAsString._hstring);
      v11 = StringFromObject;
      if ( StringFromObject < 0 )
      {
LABEL_30:
        OnFailure_2990_(StringFromObject);
        if ( localToolTipAsString._hstring )
          WindowsDeleteString(localToolTipAsString._hstring);
        goto LABEL_32;
      }
      localHelpText._hstring = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&localHelpText);
      if ( localToolTipAsI.ptr_ )
        localToolTipAsI.ptr_->QueryInterface(
          localToolTipAsI.ptr_,
          &GUID_7de5d75f_4415_429f_b523_699bdb8c30db,
          (void **)&localHelpText);
      v17 = localHelpText._hstring;
      localHelpText._hstring = 0;
      if ( localToolTipAsString._hstring && !WindowsIsStringEmpty(localToolTipAsString._hstring) )
      {
        if ( !v17 )
        {
LABEL_12:
          if ( localToolTipAsString._hstring )
            WindowsDeleteString(localToolTipAsString._hstring);
          v14 = localToolTipAsI.ptr_;
          if ( localToolTipAsI.ptr_ )
          {
            localToolTipAsI.ptr_ = 0;
            v14->Release(v14);
          }
          if ( hstring )
            WindowsDeleteString(hstring);
          if ( descriptionFromCommand._hstring )
            WindowsDeleteString(descriptionFromCommand._hstring);
          return 0;
        }
      }
      else if ( !v17 )
      {
LABEL_9:
        if ( WindowsCreateStringReference(L"Description", 0xBu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        StringFromObject = DirectUI::DXamlCore::SetBinding(uiCommand, string, target, ToolTipService_ToolTip, 0);
        v11 = StringFromObject;
        if ( StringFromObject >= 0 )
          goto LABEL_12;
        goto LABEL_30;
      }
      (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_12;
    }
    OnFailure_2990_(ValueByKnownIndex);
    if ( localHelpText._hstring )
      WindowsDeleteString(localHelpText._hstring);
  }
  if ( descriptionFromCommand._hstring )
    WindowsDeleteString(descriptionFromCommand._hstring);
  return v7;
}

```

## disassembly

```asm
0x18034ca9c  mov     [rsp-28h+arg_10], rbx
0x18034caa1  push    rbp
0x18034caa2  push    rsi
0x18034caa3  push    rdi
0x18034caa4  push    r14
0x18034caa6  push    r15
0x18034caa8  mov     rbp, rsp
0x18034caab  sub     rsp, 80h
0x18034cab2  mov     rax, cs:__security_cookie
0x18034cab9  xor     rax, rsp
0x18034cabc  mov     [rbp+var_10], rax
0x18034cac0  mov     rax, [uiCommand]
0x18034cac3  mov     r14, uiCommand
0x18034cac6  xor     r15d, r15d
0x18034cac9  xor     ecx, ecx; string
0x18034cacb  mov     rsi, target
0x18034cace  mov     [rbp+descriptionFromCommand._hstring], r15
0x18034cad2  mov     rbx, [rax+68h]
0x18034cad6  call    cs:__imp_WindowsDeleteString
0x18034cadc  lea     target, [rbp+descriptionFromCommand]
0x18034cae0  mov     [rbp+descriptionFromCommand._hstring], r15
0x18034cae4  mov     uiCommand, r14
0x18034cae7  mov     rax, rbx
0x18034caea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034caef  mov     ebx, eax
0x18034caf1  test    eax, eax
0x18034caf3  js      loc_18034CC36
0x18034caf9  xor     ecx, ecx; string
0x18034cafb  call    cs:__imp_WindowsDeleteString
0x18034cb01  lea     edi, [r15+15h]
0x18034cb05  mov     [rbp+localHelpText._hstring], r15
0x18034cb09  mov     edx, edi; nPropertyIndex
0x18034cb0b  lea     r8, [rbp+localHelpText]; pValue
0x18034cb0f  mov     uiCommand, rsi; this
0x18034cb12  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x18034cb17  mov     ebx, eax
0x18034cb19  test    eax, eax
0x18034cb1b  js      loc_18034CC87
0x18034cb21  mov     rbx, [rbp+localHelpText._hstring]
0x18034cb25  test    rbx, rbx
0x18034cb28  jnz     loc_18034CC71
0x18034cb2e  lea     r9, [rbp+string]; string
0x18034cb32  mov     edx, 0Bh; length
0x18034cb37  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18034cb3b  lea     uiCommand, aDescription; "Description"
0x18034cb42  call    cs:__imp_WindowsCreateStringReference
0x18034cb48  test    eax, eax
0x18034cb4a  js      loc_18034CD95
0x18034cb50  mov     target, [rbp+string]; pathString
0x18034cb54  mov     r9d, edi; targetPropertyIndex
0x18034cb57  mov     r8, rsi; target
0x18034cb5a  mov     [rsp+80h+converter], r15; converter
0x18034cb5f  mov     uiCommand, r14; source
0x18034cb62  call    ?SetBinding@DXamlCore@DirectUI@@SAJPEAUIInspectable@@PEAUHSTRING__@@PEAUIDependencyObject@Xaml@UI@Windows@@W4KnownPropertyIndex@@PEAUIValueConverter@Data@678@@Z; DirectUI::DXamlCore::SetBinding(IInspectable *,HSTRING__ *,Windows::UI::Xaml::IDependencyObject *,KnownPropertyIndex,Windows::UI::Xaml::Data::IValueConverter *)
0x18034cb67  mov     edi, eax
0x18034cb69  test    eax, eax
0x18034cb6b  js      loc_18034CC9F
0x18034cb71  lea     uiCommand, [rbp+localToolTipAsI]; this
0x18034cb75  mov     [rbp+localToolTipAsI.ptr_], r15
0x18034cb79  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18034cb7e  mov     edx, 3Bh ; ';'; nPropertyIndex
0x18034cb83  lea     r8, [rbp+localToolTipAsI]; pValue
0x18034cb87  mov     uiCommand, rsi; pElement
0x18034cb8a  call    ??$GetAttachedValueByKnownIndex@PEAUIInspectable@@@DependencyObject@DirectUI@@SAJPEAV01@W4KnownPropertyIndex@@PEAPEAUIInspectable@@@Z; DirectUI::DependencyObject::GetAttachedValueByKnownIndex<IInspectable *>(DirectUI::DependencyObject *,KnownPropertyIndex,IInspectable * *)
0x18034cb8f  mov     edi, eax
0x18034cb91  test    eax, eax
0x18034cb93  js      loc_18034CD6C
0x18034cb99  mov     [rbp+localToolTipAsString._hstring], r15
0x18034cb9d  cmp     [rbp+localToolTipAsI.ptr_], r15
0x18034cba1  jnz     loc_18034CCFB
0x18034cba7  lea     r9, [rbp+string]; string
0x18034cbab  mov     edx, 0Bh; length
0x18034cbb0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18034cbb4  lea     uiCommand, aDescription; "Description"
0x18034cbbb  call    cs:__imp_WindowsCreateStringReference
0x18034cbc1  test    eax, eax
0x18034cbc3  js      loc_18034CDAF
0x18034cbc9  mov     target, [rbp+string]; pathString
0x18034cbcd  mov     r9d, 3Bh ; ';'; targetPropertyIndex
0x18034cbd3  mov     r8, rsi; target
0x18034cbd6  mov     [rsp+80h+converter], r15; converter
0x18034cbdb  mov     uiCommand, r14; source
0x18034cbde  call    ?SetBinding@DXamlCore@DirectUI@@SAJPEAUIInspectable@@PEAUHSTRING__@@PEAUIDependencyObject@Xaml@UI@Windows@@W4KnownPropertyIndex@@PEAUIValueConverter@Data@678@@Z; DirectUI::DXamlCore::SetBinding(IInspectable *,HSTRING__ *,Windows::UI::Xaml::IDependencyObject *,KnownPropertyIndex,Windows::UI::Xaml::Data::IValueConverter *)
0x18034cbe3  mov     edi, eax
0x18034cbe5  test    eax, eax
0x18034cbe7  js      loc_18034CDC9
0x18034cbed  mov     uiCommand, [rbp+localToolTipAsString._hstring]; string
0x18034cbf1  test    uiCommand, uiCommand
0x18034cbf4  jz      short loc_18034CBFC
0x18034cbf6  call    cs:__imp_WindowsDeleteString
0x18034cbfc  mov     uiCommand, [rbp+localToolTipAsI.ptr_]
0x18034cc00  test    uiCommand, uiCommand
0x18034cc03  jz      short loc_18034CC15
0x18034cc05  mov     [rbp+localToolTipAsI.ptr_], r15
0x18034cc09  mov     rax, [uiCommand]
0x18034cc0c  mov     rax, [rax+10h]
0x18034cc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034cc15  test    rbx, rbx
0x18034cc18  jz      short loc_18034CC23
0x18034cc1a  mov     uiCommand, rbx; string
0x18034cc1d  call    cs:__imp_WindowsDeleteString
0x18034cc23  mov     uiCommand, [rbp+descriptionFromCommand._hstring]; string
0x18034cc27  test    uiCommand, uiCommand
0x18034cc2a  jz      short loc_18034CC32
0x18034cc2c  call    cs:__imp_WindowsDeleteString
0x18034cc32  xor     eax, eax
0x18034cc34  jmp     short loc_18034CC4E
0x18034cc36  mov     ecx, ebx; failedFrameHR
0x18034cc38  call    OnFailure_2990_
0x18034cc3d  mov     uiCommand, [rbp+descriptionFromCommand._hstring]; string
0x18034cc41  test    uiCommand, uiCommand
0x18034cc44  jz      short loc_18034CC4C
0x18034cc46  call    cs:__imp_WindowsDeleteString
0x18034cc4c  mov     eax, ebx
0x18034cc4e  mov     uiCommand, [rbp+var_10]
0x18034cc52  xor     uiCommand, rsp; StackCookie
0x18034cc55  call    __security_check_cookie
0x18034cc5a  mov     rbx, [rsp+80h+arg_10]
0x18034cc62  add     rsp, 80h
0x18034cc69  pop     r15
0x18034cc6b  pop     r14
0x18034cc6d  pop     rdi
0x18034cc6e  pop     rsi
0x18034cc6f  pop     rbp
0x18034cc70  retn
0x18034cc71  mov     uiCommand, rbx; string
0x18034cc74  call    cs:__imp_WindowsIsStringEmpty
0x18034cc7a  test    eax, eax
0x18034cc7c  jz      loc_18034CB71
0x18034cc82  jmp     loc_18034CB2E
0x18034cc87  mov     ecx, ebx; failedFrameHR
0x18034cc89  call    OnFailure_2990_
0x18034cc8e  mov     uiCommand, [rbp+localHelpText._hstring]; string
0x18034cc92  test    uiCommand, uiCommand
0x18034cc95  jz      short loc_18034CC3D
0x18034cc97  call    cs:__imp_WindowsDeleteString
0x18034cc9d  jmp     short loc_18034CC3D
0x18034cc9f  mov     ecx, edi; failedFrameHR
0x18034cca1  call    OnFailure_2990_
0x18034cca6  jmp     short loc_18034CCD7
0x18034cca8  mov     ecx, edi; failedFrameHR
0x18034ccaa  call    OnFailure_2990_
0x18034ccaf  mov     uiCommand, [rbp+localToolTipAsString._hstring]; string
0x18034ccb3  test    uiCommand, uiCommand
0x18034ccb6  jz      short loc_18034CCBE
0x18034ccb8  call    cs:__imp_WindowsDeleteString
0x18034ccbe  mov     uiCommand, [rbp+localToolTipAsI.ptr_]
0x18034ccc2  test    uiCommand, uiCommand
0x18034ccc5  jz      short loc_18034CCD7
0x18034ccc7  mov     [rbp+localToolTipAsI.ptr_], r15
0x18034cccb  mov     rax, [uiCommand]
0x18034ccce  mov     rax, [rax+10h]
0x18034ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034ccd7  test    rbx, rbx
0x18034ccda  jz      short loc_18034CCE5
0x18034ccdc  mov     uiCommand, rbx; string
0x18034ccdf  call    cs:__imp_WindowsDeleteString
0x18034cce5  mov     uiCommand, [rbp+descriptionFromCommand._hstring]; string
0x18034cce9  test    uiCommand, uiCommand
0x18034ccec  jz      short loc_18034CCF4
0x18034ccee  call    cs:__imp_WindowsDeleteString
0x18034ccf4  mov     eax, edi
0x18034ccf6  jmp     loc_18034CC4E
0x18034ccfb  xor     ecx, ecx; string
0x18034ccfd  call    cs:__imp_WindowsDeleteString
0x18034cd03  mov     uiCommand, [rbp+localToolTipAsI.ptr_]; pObject
0x18034cd07  lea     target, [rbp+localToolTipAsString]; returnValue
0x18034cd0b  mov     [rbp+localToolTipAsString._hstring], r15
0x18034cd0f  call    ?GetStringFromObject@FrameworkElement@DirectUI@@SAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; DirectUI::FrameworkElement::GetStringFromObject(IInspectable *,HSTRING__ * *)
0x18034cd14  mov     edi, eax
0x18034cd16  test    eax, eax
0x18034cd18  js      short loc_18034CCA8
0x18034cd1a  lea     uiCommand, [rbp+localHelpText]; this
0x18034cd1e  mov     [rbp+localHelpText._hstring], r15
0x18034cd22  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18034cd27  mov     uiCommand, [rbp+localToolTipAsI.ptr_]
0x18034cd2b  test    uiCommand, uiCommand
0x18034cd2e  jz      short loc_18034CD46
0x18034cd30  mov     rax, [uiCommand]
0x18034cd33  lea     r8, [rbp+localHelpText]
0x18034cd37  lea     target, _GUID_7de5d75f_4415_429f_b523_699bdb8c30db
0x18034cd3e  mov     rax, [rax]
0x18034cd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034cd46  mov     uiCommand, [rbp+localToolTipAsString._hstring]; string
0x18034cd4a  mov     rdi, [rbp+localHelpText._hstring]
0x18034cd4e  mov     [rbp+localHelpText._hstring], r15
0x18034cd52  test    uiCommand, uiCommand
0x18034cd55  jz      short loc_18034CD61
0x18034cd57  call    cs:__imp_WindowsIsStringEmpty
0x18034cd5d  test    eax, eax
0x18034cd5f  jz      short loc_18034CD78
0x18034cd61  test    rdi, rdi
0x18034cd64  jz      loc_18034CBA7
0x18034cd6a  jmp     short loc_18034CD81
0x18034cd6c  mov     ecx, edi; failedFrameHR
0x18034cd6e  call    OnFailure_2990_
0x18034cd73  jmp     loc_18034CCBE
0x18034cd78  test    rdi, rdi
0x18034cd7b  jz      loc_18034CBED
0x18034cd81  mov     rax, [rdi]
0x18034cd84  mov     uiCommand, rdi
0x18034cd87  mov     rax, [rax+10h]
0x18034cd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034cd90  jmp     loc_18034CBED
0x18034cd95  xor     r9d, r9d; lpArguments
0x18034cd98  xor     r8d, r8d; nNumberOfArguments
0x18034cd9b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18034cda0  lea     edx, [r9+1]; dwExceptionFlags
0x18034cda4  call    cs:__imp_RaiseException
0x18034cdaa  jmp     loc_18034CB50
0x18034cdaf  xor     r9d, r9d; lpArguments
0x18034cdb2  xor     r8d, r8d; nNumberOfArguments
0x18034cdb5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18034cdba  lea     edx, [r9+1]; dwExceptionFlags
0x18034cdbe  call    cs:__imp_RaiseException
0x18034cdc4  jmp     loc_18034CBC9
0x18034cdc9  mov     ecx, edi; failedFrameHR
0x18034cdcb  call    OnFailure_2990_
0x18034cdd0  jmp     loc_18034CCAF
```
