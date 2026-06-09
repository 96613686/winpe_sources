# Windows::Security::Authentication::Web::CWebAuthResult::CWebAuthResult(Windows::Security::Authentication::Web::WebAuthenticationStatus,uint)

- ea: `0x180016d68`
- end: `0x180016de5`
- name: `??0CWebAuthResult@Web@Authentication@Security@Windows@@QEAA@W4WebAuthenticationStatus@1234@I@Z`
- size: `125`
- prototype: `void __fastcall(Windows::Security::Authentication::Web::CWebAuthResult *this, Windows::Security::Authentication::Web::WebAuthenticationStatus status, unsigned int errorDetail)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ae0`

## callees

- `0x180006fac`
- `0x18000f404`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016dbd`

## pseudocode

```c
void __fastcall Windows::Security::Authentication::Web::CWebAuthResult::CWebAuthResult(
        Windows::Security::Authentication::Web::CWebAuthResult *this,
        Windows::Security::Authentication::Web::WebAuthenticationStatus status,
        unsigned int errorDetail)
{
  HRESULT v6; // eax
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  Microsoft::WRL::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>(this);
  string = 0;
  this->Microsoft::WRL::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IWeakReferenceSource,IInspectable>::Windows::Security::Authentication::Web::IWebAuthenticationResult::IInspectable::IUnknown::lpVtbl = (Windows::Security::Authentication::Web::CWebAuthResult_vtbl *)Windows::Security::Authentication::Web::CWebAuthResult::`vftable';
  this->Microsoft::WRL::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::IWeakReferenceSource::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>_vtbl *)Windows::Security::Authentication::Web::CWebAuthResult::`vftable'{for `IWeakReferenceSource'};
  this->Microsoft::WRL::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Security::Authentication::Web::IWebAuthenticationResult,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>::IInspectable::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>_vtbl *)Windows::Security::Authentication::Web::CWebAuthResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'};
  this->m_data._hstring = 0;
  v6 = WindowsCreateString(&source, 0, &string);
  Windows::Internal::String::FreeAndAssignOnSuccess(v6, string, &this->m_data._hstring);
  this->m_status = status;
  this->m_errorDetail = errorDetail;
}

```

## disassembly

```asm
0x180016d68  push    rbx
0x180016d6a  push    rbp
0x180016d6b  push    rsi
0x180016d6c  push    rdi
0x180016d6d  sub     rsp, 28h
0x180016d71  mov     ebp, errorDetail
0x180016d74  mov     edi, status
0x180016d76  mov     rsi, this
0x180016d79  call    ??0?$RuntimeClass@UIWebAuthenticationResult@Web@Authentication@Security@Windows@@UIInspectable@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>::RuntimeClass<Windows::Security::Authentication::Web::IWebAuthenticationResult,IInspectable>(void)
0x180016d7e  lea     rax, ??_7CWebAuthResult@Web@Authentication@Security@Windows@@6B@; const Windows::Security::Authentication::Web::CWebAuthResult::`vftable'
0x180016d85  mov     [rsp+48h+string], 0
0x180016d8e  mov     [rsi], rax
0x180016d91  lea     r8, [rsp+48h+string]; string
0x180016d96  lea     rax, ??_7CWebAuthResult@Web@Authentication@Security@Windows@@6BIWeakReferenceSource@@@; const Windows::Security::Authentication::Web::CWebAuthResult::`vftable'{for `IWeakReferenceSource'}
0x180016d9d  xor     status, status; length
0x180016d9f  mov     [rsi+8], rax
0x180016da3  lea     this, source; sourceString
0x180016daa  lea     rax, ??_7CWebAuthResult@Web@Authentication@Security@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const Windows::Security::Authentication::Web::CWebAuthResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'}
0x180016db1  mov     [rsi+10h], rax
0x180016db5  mov     qword ptr [rsi+28h], 0
0x180016dbd  call    cs:__imp_WindowsCreateString
0x180016dc3  mov     rdx, [rsp+48h+string]; newValue
0x180016dc8  lea     r8, [rsi+28h]; target
0x180016dcc  mov     ecx, eax; hr
0x180016dce  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180016dd3  mov     rax, rsi
0x180016dd6  mov     [rsi+30h], edi
0x180016dd9  mov     [rsi+34h], ebp
0x180016ddc  add     rsp, 28h
0x180016de0  pop     rdi
0x180016de1  pop     rsi
0x180016de2  pop     rbp
0x180016de3  pop     rbx
0x180016de4  retn
```
