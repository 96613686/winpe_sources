# AuthHostWebInstance::~AuthHostWebInstance(void)

- ea: `0x1400047f4`
- end: `0x1400048ef`
- name: `??1AuthHostWebInstance@@UEAA@XZ`
- size: `251`
- prototype: `void __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004960`

## callees

- `0x140003a8c`
- `0x1400048f8`
- `0x14000d288`
- `0x140011784`

## import_xrefs

- `urlmon!UnregisterWebPlatformPermanentSecurityManager` at `0x140004849`
- `urlmon!UnregisterWebPlatformPermanentSecurityManager` at `0x140004849`

## pseudocode

```c
void __fastcall AuthHostWebInstance::~AuthHostWebInstance(AuthHostWebInstance *this)
{
  *(_QWORD *)this = &AuthHostWebInstance::`vftable';
  *((_QWORD *)this + 1) = &AuthHostWebInstance::`vftable'{for `IWebPlatformNavigationEvents'};
  *((_QWORD *)this + 2) = &AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>'};
  *((_QWORD *)this + 3) = &AuthHostWebInstance::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 4) = &AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>'};
  *((_QWORD *)this + 5) = &AuthHostWebInstance::`vftable'{for `IWebPlatformPermanentSecurityManager'};
  *((_QWORD *)this + 6) = &AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformVisualViewportEvents>'};
  UnregisterWebPlatformPermanentSecurityManager();
  ClearWebDialogMetaTagContent((AuthHostWebInstance *)((char *)this + 176));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 704);
  CLoginForm::~CLoginForm((AuthHostWebInstance *)((char *)this + 544));
  Windows::Internal::String::~String((HSTRING *)this + 67);
  Windows::Internal::String::~String((HSTRING *)this + 66);
  Windows::Internal::String::~String((HSTRING *)this + 65);
  Windows::Internal::String::~String((HSTRING *)this + 60);
  Windows::Internal::String::~String((HSTRING *)this + 15);
  Windows::Internal::String::~String((HSTRING *)this + 14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
  *((_DWORD *)this + 15) = -1073741823;
}

```

## disassembly

```asm
0x1400047f4  push    rbx
0x1400047f6  sub     rsp, 20h
0x1400047fa  lea     rax, ??_7AuthHostWebInstance@@6B@; const AuthHostWebInstance::`vftable'
0x140004801  mov     rbx, rcx
0x140004804  mov     [rcx], rax
0x140004807  lea     rax, ??_7AuthHostWebInstance@@6BIWebPlatformNavigationEvents@@@; const AuthHostWebInstance::`vftable'{for `IWebPlatformNavigationEvents'}
0x14000480e  mov     [rcx+8], rax
0x140004812  lea     rax, ??_7AuthHostWebInstance@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@@; const AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>'}
0x140004819  mov     [rcx+10h], rax
0x14000481d  lea     rax, ??_7AuthHostWebInstance@@6BIServiceProvider@@@; const AuthHostWebInstance::`vftable'{for `IServiceProvider'}
0x140004824  mov     [rcx+18h], rax
0x140004828  lea     rax, ??_7AuthHostWebInstance@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@@; const AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>'}
0x14000482f  mov     [rcx+20h], rax
0x140004833  lea     rax, ??_7AuthHostWebInstance@@6BIWebPlatformPermanentSecurityManager@@@; const AuthHostWebInstance::`vftable'{for `IWebPlatformPermanentSecurityManager'}
0x14000483a  mov     [rcx+28h], rax
0x14000483e  lea     rax, ??_7AuthHostWebInstance@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@@; const AuthHostWebInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformVisualViewportEvents>'}
0x140004845  mov     [rcx+30h], rax
0x140004849  call    cs:__imp_UnregisterWebPlatformPermanentSecurityManager
0x14000484f  lea     rcx, [rbx+0B0h]; struct _WEB_DIALOG_META_TAG_CONTENT *
0x140004856  call    ?ClearWebDialogMetaTagContent@@YAXPEAU_WEB_DIALOG_META_TAG_CONTENT@@@Z; ClearWebDialogMetaTagContent(_WEB_DIALOG_META_TAG_CONTENT *)
0x14000485b  lea     rcx, [rbx+2C0h]
0x140004862  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004867  lea     rcx, [rbx+220h]; this
0x14000486e  call    ??1CLoginForm@@UEAA@XZ; CLoginForm::~CLoginForm(void)
0x140004873  lea     rcx, [rbx+218h]; this
0x14000487a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14000487f  lea     rcx, [rbx+210h]; this
0x140004886  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14000488b  lea     rcx, [rbx+208h]; this
0x140004892  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140004897  lea     rcx, [rbx+1E0h]; this
0x14000489e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1400048a3  lea     rcx, [rbx+78h]; this
0x1400048a7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1400048ac  lea     rcx, [rbx+70h]; this
0x1400048b0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1400048b5  lea     rcx, [rbx+68h]
0x1400048b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400048be  lea     rcx, [rbx+60h]
0x1400048c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400048c7  lea     rcx, [rbx+58h]
0x1400048cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400048d0  lea     rcx, [rbx+50h]
0x1400048d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400048d9  lea     rcx, [rbx+48h]
0x1400048dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400048e2  mov     dword ptr [rbx+3Ch], 0C0000001h
0x1400048e9  add     rsp, 20h
0x1400048ed  pop     rbx
0x1400048ee  retn
```
