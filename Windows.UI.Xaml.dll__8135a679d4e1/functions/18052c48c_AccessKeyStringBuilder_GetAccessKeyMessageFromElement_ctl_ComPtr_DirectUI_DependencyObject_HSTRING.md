# AccessKeyStringBuilder::GetAccessKeyMessageFromElement(ctl::ComPtr<DirectUI::DependencyObject> &,HSTRING__ * *)

- ea: `0x18052c48c`
- end: `0x18052c796`
- name: `?GetAccessKeyMessageFromElement@AccessKeyStringBuilder@@YAJAEAV?$ComPtr@VDependencyObject@DirectUI@@@ctl@@PEAPEAUHSTRING__@@@Z`
- size: `778`
- prototype: `HRESULT __fastcall(ctl::ComPtr<DirectUI::DependencyObject> *spOwner, HSTRING__ **returnValue)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18052c2a0`
- `0x180bd4990`
- `0x180bd5a50`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000f70c`
- `0x180139ae8`
- `0x18052c48c`
- `0x18052c79c`
- `0x18052c958`
- `0x1806877a8`
- `0x180687890`
- `0x1806c1dc0`
- `0x1808735f8`
- `0x180b6a4d4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18052c614`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18052c614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c4c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c4c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c6fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18052c779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18052c50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18052c68e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18052c50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18052c68e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18052c6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18052c6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18052c4f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18052c4f0`

## pseudocode

```c
__int64 __fastcall AccessKeyStringBuilder::GetAccessKeyMessageFromElement(
        ctl::ComPtr<DirectUI::DependencyObject> *spOwner,
        HSTRING__ **returnValue)
{
  HRESULT AccessKeyFromOwner; // eax
  unsigned int v5; // ebx
  const wchar_t *StringRawBuffer; // r15
  int String; // eax
  Windows::UI::Xaml::Automation::Peers::IAutomationPeer *v8; // rbx
  HRESULT v9; // ecx
  Windows::UI::Xaml::IFrameworkElement *v10; // rdi
  HRESULT v11; // eax
  Windows::UI::Xaml::Documents::ITextElement *v12; // rdi
  HRESULT (__fastcall *GetAccessKey)(Windows::UI::Xaml::Automation::Peers::IAutomationPeer *, HSTRING__ **); // rdi
  int v14; // eax
  Windows::UI::Xaml::IDependencyObject *ptr; // rcx
  ctl::ComPtr<Windows::UI::Xaml::Automation::Peers::IAutomationPeer> automationPeer; // [rsp+20h] [rbp-40h] BYREF
  Microsoft::WRL::Wrappers::HString messageWithoutPrefix; // [rsp+28h] [rbp-38h] BYREF
  Microsoft::WRL::Wrappers::HString prefix; // [rsp+30h] [rbp-30h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> akScopeOwner; // [rsp+38h] [rbp-28h] BYREF
  Microsoft::WRL::Wrappers::HString accessKey; // [rsp+40h] [rbp-20h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Documents::ITextElement> akScopeOwnerAsTextElement; // [rsp+48h] [rbp-18h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> akScopeOwnerAsFrameworkElement; // [rsp+50h] [rbp-10h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+58h] [rbp-8h] BYREF
  unsigned int length; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int cStowedExceptions; // [rsp+A8h] [rbp+48h] BYREF

  prefix.hstr_ = 0;
  messageWithoutPrefix.hstr_ = 0;
  length = 0;
  akScopeOwner.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwner);
  WindowsDeleteString(0);
  accessKey.hstr_ = 0;
  AccessKeyFromOwner = GetAccessKeyFromOwner(spOwner, &accessKey.hstr_, &akScopeOwner.ptr_);
  v5 = AccessKeyFromOwner;
  if ( AccessKeyFromOwner < 0 )
  {
    OnFailure_2990_(AccessKeyFromOwner);
    ptr = akScopeOwner.ptr_;
    if ( akScopeOwner.ptr_ )
    {
      akScopeOwner.ptr_ = 0;
      ptr->Release(ptr);
    }
    goto LABEL_26;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(accessKey.hstr_, &length);
  if ( !length )
  {
    String = WindowsCreateString(&pressedKeys, 0, returnValue);
    v5 = String;
    if ( String < 0 )
      OnFailure_2990_(String);
    else
      v5 = 0;
    goto LABEL_23;
  }
  v8 = 0;
  automationPeer.ptr_ = 0;
  if ( !akScopeOwner.ptr_ )
    goto LABEL_17;
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject>::AsOrNull<Windows::UI::Xaml::IFrameworkElement>(
    (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IGrid,1,0> *)&akScopeOwner,
    &akScopeOwnerAsFrameworkElement);
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject>::AsOrNull<Windows::UI::Xaml::Documents::ITextElement>(
    &akScopeOwner,
    &akScopeOwnerAsTextElement);
  v10 = akScopeOwnerAsFrameworkElement.ptr_;
  if ( !akScopeOwnerAsFrameworkElement.ptr_ )
  {
    v12 = akScopeOwnerAsTextElement.ptr_;
    if ( !akScopeOwnerAsTextElement.ptr_ )
    {
      OnFailure_1169_(v9);
      ppStowedExceptions = 0;
      cStowedExceptions = 0;
      TraceForFailFast(-2147024809);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147024809, cStowedExceptions, ppStowedExceptions);
LABEL_14:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwnerAsTextElement);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwnerAsFrameworkElement);
      if ( v8 )
      {
        GetAccessKey = v8->GetAccessKey;
        WindowsDeleteString(prefix.hstr_);
        prefix.hstr_ = 0;
        v14 = GetAccessKey(v8, &prefix.hstr_);
        v5 = v14;
        if ( v14 < 0 )
          goto LABEL_21;
        goto LABEL_18;
      }
LABEL_17:
      WindowsDeleteString(prefix.hstr_);
      prefix.hstr_ = 0;
      v14 = WindowsCreateString(L"Alt", 3u, &prefix.hstr_);
      v5 = v14;
      if ( v14 < 0 )
      {
LABEL_21:
        OnFailure_2990_(v14);
        goto LABEL_22;
      }
LABEL_18:
      WindowsDeleteString(messageWithoutPrefix.hstr_);
      messageWithoutPrefix.hstr_ = 0;
      v14 = InterleaveStringWithDelimiters(StringRawBuffer, length, &messageWithoutPrefix.hstr_);
      v5 = v14;
      if ( v14 >= 0 )
      {
        v14 = WindowsConcatString(prefix.hstr_, messageWithoutPrefix.hstr_, returnValue);
        v5 = v14;
        if ( v14 >= 0 )
        {
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationPeer);
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwner);
          WindowsDeleteString(messageWithoutPrefix.hstr_);
          messageWithoutPrefix.hstr_ = 0;
          WindowsDeleteString(accessKey.hstr_);
          WindowsDeleteString(prefix.hstr_);
          return 0;
        }
      }
      goto LABEL_21;
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationPeer);
    v11 = DirectUI::TextElement::GetOrCreateAutomationPeer(
            (DirectUI::TextElement *)((unsigned __int64)&v12[-23] & -(__int64)(v12 != 0)),
            &automationPeer.ptr_);
    v5 = v11;
    if ( v11 < 0 )
      goto LABEL_9;
LABEL_12:
    v8 = automationPeer.ptr_;
    goto LABEL_14;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationPeer);
  v11 = DirectUI::UIElement::GetOrCreateAutomationPeer(
          (DirectUI::UIElement *)((unsigned __int64)&v10[-44] & -(__int64)(v10 != 0)),
          &automationPeer.ptr_);
  v5 = v11;
  if ( v11 >= 0 )
    goto LABEL_12;
LABEL_9:
  OnFailure_2990_(v11);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwnerAsTextElement);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwnerAsFrameworkElement);
LABEL_22:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationPeer);
LABEL_23:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&akScopeOwner);
LABEL_26:
  WindowsDeleteString(messageWithoutPrefix.hstr_);
  messageWithoutPrefix.hstr_ = 0;
  WindowsDeleteString(accessKey.hstr_);
  WindowsDeleteString(prefix.hstr_);
  return v5;
}

```

## disassembly

```asm
0x18052c48c  mov     [rsp-28h+arg_0], rbx
0x18052c491  push    rbp
0x18052c492  push    rdi
0x18052c493  push    r12
0x18052c495  push    r14
0x18052c497  push    r15
0x18052c499  mov     rbp, rsp
0x18052c49c  sub     rsp, 60h
0x18052c4a0  xor     r12d, r12d
0x18052c4a3  mov     rbx, spOwner
0x18052c4a6  lea     spOwner, [rbp+akScopeOwner]; this
0x18052c4aa  mov     [rbp+prefix.hstr_], r12
0x18052c4ae  mov     [rbp+messageWithoutPrefix.hstr_], r12
0x18052c4b2  mov     r14, returnValue
0x18052c4b5  mov     [rbp+length], r12d
0x18052c4b9  mov     [rbp+akScopeOwner.ptr_], r12
0x18052c4bd  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c4c2  xor     ecx, ecx; string
0x18052c4c4  call    cs:__imp_WindowsDeleteString
0x18052c4ca  lea     r8, [rbp+akScopeOwner]; scopeOwner
0x18052c4ce  mov     [rbp+accessKey.hstr_], r12
0x18052c4d2  lea     returnValue, [rbp+accessKey]; accessKey
0x18052c4d6  mov     spOwner, rbx; spOwner
0x18052c4d9  call    ?GetAccessKeyFromOwner@@YAJAEAV?$ComPtr@VDependencyObject@DirectUI@@@ctl@@PEAPEAUHSTRING__@@PEAPEAUIDependencyObject@Xaml@UI@Windows@@@Z; GetAccessKeyFromOwner(ctl::ComPtr<DirectUI::DependencyObject> &,HSTRING__ * *,Windows::UI::Xaml::IDependencyObject * *)
0x18052c4de  mov     ebx, eax
0x18052c4e0  test    eax, eax
0x18052c4e2  js      loc_18052C73D
0x18052c4e8  mov     spOwner, [rbp+accessKey.hstr_]; string
0x18052c4ec  lea     returnValue, [rbp+length]; length
0x18052c4f0  call    cs:__imp_WindowsGetStringRawBuffer
0x18052c4f6  mov     r15, rax
0x18052c4f9  cmp     [rbp+length], r12d
0x18052c4fd  jnz     short loc_18052C52B
0x18052c4ff  mov     r8, r14; string
0x18052c502  lea     spOwner, pressedKeys; sourceString
0x18052c509  xor     edx, edx; length
0x18052c50b  call    cs:__imp_WindowsCreateString
0x18052c511  mov     ebx, eax
0x18052c513  test    eax, eax
0x18052c515  js      short loc_18052C51F
0x18052c517  mov     ebx, r12d
0x18052c51a  jmp     loc_18052C732
0x18052c51f  mov     ecx, eax; failedFrameHR
0x18052c521  call    OnFailure_2990_
0x18052c526  jmp     loc_18052C732
0x18052c52b  mov     rbx, r12
0x18052c52e  mov     [rbp+automationPeer.ptr_], rbx
0x18052c532  cmp     [rbp+akScopeOwner.ptr_], r12
0x18052c536  jz      loc_18052C670
0x18052c53c  lea     returnValue, [rbp+akScopeOwnerAsFrameworkElement]; result
0x18052c540  lea     spOwner, [rbp+akScopeOwner]; this
0x18052c544  call    ??$AsOrNull@UIFrameworkElement@Xaml@UI@Windows@@@?$ComPtr@UIDependencyObject@Xaml@UI@Windows@@@ctl@@QEBA?AV?$ComPtr@UIFrameworkElement@Xaml@UI@Windows@@@1@XZ; ctl::ComPtr<Windows::UI::Xaml::IDependencyObject>::AsOrNull<Windows::UI::Xaml::IFrameworkElement>(void)
0x18052c549  lea     returnValue, [rbp+akScopeOwnerAsTextElement]; result
0x18052c54d  lea     spOwner, [rbp+akScopeOwner]; this
0x18052c551  call    ??$AsOrNull@UITextElement@Documents@Xaml@UI@Windows@@@?$ComPtr@UIDependencyObject@Xaml@UI@Windows@@@ctl@@QEBA?AV?$ComPtr@UITextElement@Documents@Xaml@UI@Windows@@@1@XZ; ctl::ComPtr<Windows::UI::Xaml::IDependencyObject>::AsOrNull<Windows::UI::Xaml::Documents::ITextElement>(void)
0x18052c556  mov     rdi, [rbp+akScopeOwnerAsFrameworkElement.ptr_]
0x18052c55a  test    rdi, rdi
0x18052c55d  jz      short loc_18052C5A5
0x18052c55f  lea     spOwner, [rbp+automationPeer]; this
0x18052c563  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c568  lea     rax, [rdi-160h]
0x18052c56f  neg     rdi
0x18052c572  lea     returnValue, [rbp+automationPeer]; ppAutomationPeer
0x18052c576  sbb     spOwner, spOwner
0x18052c579  and     spOwner, rax; this
0x18052c57c  call    ?GetOrCreateAutomationPeer@UIElement@DirectUI@@QEAAJPEAPEAUIAutomationPeer@Peers@Automation@Xaml@UI@Windows@@@Z; DirectUI::UIElement::GetOrCreateAutomationPeer(Windows::UI::Xaml::Automation::Peers::IAutomationPeer * *)
0x18052c581  mov     ebx, eax
0x18052c583  test    eax, eax
0x18052c585  jns     short loc_18052C5DF
0x18052c587  mov     ecx, eax; failedFrameHR
0x18052c589  call    OnFailure_2990_
0x18052c58e  lea     spOwner, [rbp+akScopeOwnerAsTextElement]; this
0x18052c592  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c597  lea     spOwner, [rbp+akScopeOwnerAsFrameworkElement]; this
0x18052c59b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c5a0  jmp     loc_18052C729
0x18052c5a5  mov     rdi, [rbp+akScopeOwnerAsTextElement.ptr_]
0x18052c5a9  test    rdi, rdi
0x18052c5ac  jz      short loc_18052C5E5
0x18052c5ae  lea     spOwner, [rbp+automationPeer]; this
0x18052c5b2  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c5b7  lea     rax, [rdi-0B8h]
0x18052c5be  neg     rdi
0x18052c5c1  lea     returnValue, [rbp+automationPeer]; ppAutomationPeer
0x18052c5c5  sbb     spOwner, spOwner
0x18052c5c8  and     spOwner, rax; this
0x18052c5cb  call    ?GetOrCreateAutomationPeer@TextElement@DirectUI@@QEAAJPEAPEAUIAutomationPeer@Peers@Automation@Xaml@UI@Windows@@@Z; DirectUI::TextElement::GetOrCreateAutomationPeer(Windows::UI::Xaml::Automation::Peers::IAutomationPeer * *)
0x18052c5d0  mov     ebx, eax
0x18052c5d2  test    eax, eax
0x18052c5d4  jns     short loc_18052C5DF
0x18052c5d6  mov     ecx, eax; failedFrameHR
0x18052c5d8  call    OnFailure_2990_
0x18052c5dd  jmp     short loc_18052C58E
0x18052c5df  mov     rbx, [rbp+automationPeer.ptr_]
0x18052c5e3  jmp     short loc_18052C61A
0x18052c5e5  call    OnFailure_1169_
0x18052c5ea  mov     edi, 80070057h
0x18052c5ef  mov     [rbp+ppStowedExceptions], r12
0x18052c5f3  mov     ecx, edi; errorCode
0x18052c5f5  mov     [rbp+cStowedExceptions], r12d
0x18052c5f9  call    TraceForFailFast
0x18052c5fe  lea     returnValue, [rbp+cStowedExceptions]; pcStowedExceptions
0x18052c602  lea     spOwner, [rbp+ppStowedExceptions]; pppStowedExceptions
0x18052c606  call    GetStowedExceptionsForFailFast
0x18052c60b  mov     r8, [rbp+ppStowedExceptions]
0x18052c60f  mov     ecx, edi
0x18052c611  mov     edx, [rbp+cStowedExceptions]
0x18052c614  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18052c61a  lea     spOwner, [rbp+akScopeOwnerAsTextElement]; this
0x18052c61e  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c623  lea     spOwner, [rbp+akScopeOwnerAsFrameworkElement]; this
0x18052c627  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c62c  test    rbx, rbx
0x18052c62f  jz      short loc_18052C670
0x18052c631  mov     spOwner, [rbp+prefix.hstr_]; string
0x18052c635  mov     eax, 0B8h
0x18052c63a  cmovz   rbx, rax
0x18052c63e  mov     rax, [rbx]
0x18052c641  mov     rdi, [rax+60h]
0x18052c645  call    cs:__imp_WindowsDeleteString
0x18052c64b  lea     returnValue, [rbp+prefix]
0x18052c64f  mov     [rbp+prefix.hstr_], r12
0x18052c653  mov     spOwner, rbx
0x18052c656  mov     rax, rdi
0x18052c659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052c65e  mov     ebx, eax
0x18052c660  test    eax, eax
0x18052c662  jns     short loc_18052C69E
0x18052c664  mov     ecx, eax; failedFrameHR
0x18052c666  call    OnFailure_2990_
0x18052c66b  jmp     loc_18052C729
0x18052c670  mov     spOwner, [rbp+prefix.hstr_]; string
0x18052c674  call    cs:__imp_WindowsDeleteString
0x18052c67a  lea     r8, [rbp+prefix]; string
0x18052c67e  mov     [rbp+prefix.hstr_], r12
0x18052c682  mov     edx, 3; length
0x18052c687  lea     spOwner, aAlt; "Alt"
0x18052c68e  call    cs:__imp_WindowsCreateString
0x18052c694  mov     ebx, eax
0x18052c696  test    eax, eax
0x18052c698  js      loc_18052C722
0x18052c69e  mov     spOwner, [rbp+messageWithoutPrefix.hstr_]; string
0x18052c6a2  call    cs:__imp_WindowsDeleteString
0x18052c6a8  mov     edx, [rbp+length]; length
0x18052c6ab  lea     r8, [rbp+messageWithoutPrefix]; interleavedString
0x18052c6af  mov     spOwner, r15; toInterleave
0x18052c6b2  mov     [rbp+messageWithoutPrefix.hstr_], r12
0x18052c6b6  call    ?InterleaveStringWithDelimiters@@YAJPEBGHPEAPEAUHSTRING__@@@Z; InterleaveStringWithDelimiters(ushort const *,int,HSTRING__ * *)
0x18052c6bb  mov     ebx, eax
0x18052c6bd  test    eax, eax
0x18052c6bf  js      short loc_18052C719
0x18052c6c1  mov     returnValue, [rbp+messageWithoutPrefix.hstr_]; string2
0x18052c6c5  mov     r8, r14; newString
0x18052c6c8  mov     spOwner, [rbp+prefix.hstr_]; string1
0x18052c6cc  call    cs:__imp_WindowsConcatString
0x18052c6d2  mov     ebx, eax
0x18052c6d4  test    eax, eax
0x18052c6d6  js      short loc_18052C710
0x18052c6d8  lea     spOwner, [rbp+automationPeer]; this
0x18052c6dc  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c6e1  lea     spOwner, [rbp+akScopeOwner]; this
0x18052c6e5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c6ea  mov     spOwner, [rbp+messageWithoutPrefix.hstr_]; string
0x18052c6ee  call    cs:__imp_WindowsDeleteString
0x18052c6f4  mov     spOwner, [rbp+accessKey.hstr_]; string
0x18052c6f8  mov     [rbp+messageWithoutPrefix.hstr_], r12
0x18052c6fc  call    cs:__imp_WindowsDeleteString
0x18052c702  mov     spOwner, [rbp+prefix.hstr_]; string
0x18052c706  call    cs:__imp_WindowsDeleteString
0x18052c70c  xor     eax, eax
0x18052c70e  jmp     short loc_18052C781
0x18052c710  mov     ecx, eax; failedFrameHR
0x18052c712  call    OnFailure_2990_
0x18052c717  jmp     short loc_18052C729
0x18052c719  mov     ecx, eax; failedFrameHR
0x18052c71b  call    OnFailure_2990_
0x18052c720  jmp     short loc_18052C729
0x18052c722  mov     ecx, eax; failedFrameHR
0x18052c724  call    OnFailure_2990_
0x18052c729  lea     spOwner, [rbp+automationPeer]; this
0x18052c72d  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c732  lea     spOwner, [rbp+akScopeOwner]; this
0x18052c736  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18052c73b  jmp     short loc_18052C75D
0x18052c73d  mov     ecx, ebx; failedFrameHR
0x18052c73f  call    OnFailure_2990_
0x18052c744  mov     spOwner, [rbp+akScopeOwner.ptr_]
0x18052c748  test    spOwner, spOwner
0x18052c74b  jz      short loc_18052C75D
0x18052c74d  mov     [rbp+akScopeOwner.ptr_], r12
0x18052c751  mov     rax, [spOwner]
0x18052c754  mov     rax, [rax+10h]
0x18052c758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052c75d  mov     spOwner, [rbp+messageWithoutPrefix.hstr_]; string
0x18052c761  call    cs:__imp_WindowsDeleteString
0x18052c767  mov     spOwner, [rbp+accessKey.hstr_]; string
0x18052c76b  mov     [rbp+messageWithoutPrefix.hstr_], r12
0x18052c76f  call    cs:__imp_WindowsDeleteString
0x18052c775  mov     spOwner, [rbp+prefix.hstr_]; string
0x18052c779  call    cs:__imp_WindowsDeleteString
0x18052c77f  mov     eax, ebx
0x18052c781  mov     rbx, [rsp+60h+arg_0]
0x18052c789  add     rsp, 60h
0x18052c78d  pop     r15
0x18052c78f  pop     r14
0x18052c791  pop     r12
0x18052c793  pop     rdi
0x18052c794  pop     rbp
0x18052c795  retn
```
