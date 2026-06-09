# CapabilityConsentServer::~CapabilityConsentServer(void)

- ea: `0x18009803c`
- end: `0x1800980ca`
- name: `??1CapabilityConsentServer@@UEAA@XZ`
- size: `142`
- prototype: `void __fastcall(CapabilityConsentServer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800980d0`

## callees

- `0x18001f5f4`
- `0x180086d74`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009808b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800980af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009808b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800980af`

## pseudocode

```c
void __fastcall CapabilityConsentServer::~CapabilityConsentServer(CapabilityConsentServer *this)
{
  *(_QWORD *)this = &CapabilityConsentServer::`vftable'{for `Windows::Internal::CapabilityAccess::Management::ICapabilityConsent'};
  *((_QWORD *)this + 1) = &CapabilityConsentServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 72);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>(this);
}

```

## disassembly

```asm
0x18009803c  push    rbx
0x18009803e  sub     rsp, 20h
0x180098042  lea     rax, ??_7CapabilityConsentServer@@6BICapabilityConsent@Management@CapabilityAccess@Internal@Windows@@@; const CapabilityConsentServer::`vftable'{for `Windows::Internal::CapabilityAccess::Management::ICapabilityConsent'}
0x180098049  mov     rbx, rcx
0x18009804c  mov     [rcx], rax
0x18009804f  lea     rax, ??_7CapabilityConsentServer@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const CapabilityConsentServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x180098056  mov     [rcx+8], rax
0x18009805a  add     rcx, 48h ; 'H'
0x18009805e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180098063  mov     rcx, [rbx+40h]; string
0x180098067  call    cs:__imp_WindowsDeleteString
0x18009806d  mov     qword ptr [rbx+40h], 0
0x180098075  mov     rcx, [rbx+38h]; string
0x180098079  call    cs:__imp_WindowsDeleteString
0x18009807f  mov     qword ptr [rbx+38h], 0
0x180098087  mov     rcx, [rbx+30h]; string
0x18009808b  call    cs:__imp_WindowsDeleteString
0x180098091  mov     qword ptr [rbx+30h], 0
0x180098099  mov     rcx, [rbx+28h]; string
0x18009809d  call    cs:__imp_WindowsDeleteString
0x1800980a3  mov     qword ptr [rbx+28h], 0
0x1800980ab  mov     rcx, [rbx+20h]; string
0x1800980af  call    cs:__imp_WindowsDeleteString
0x1800980b5  mov     rcx, rbx
0x1800980b8  mov     qword ptr [rbx+20h], 0
0x1800980c0  add     rsp, 20h
0x1800980c4  pop     rbx
0x1800980c5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICapabilityConsentManager@Management@CapabilityAccess@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManager>(void)
```
