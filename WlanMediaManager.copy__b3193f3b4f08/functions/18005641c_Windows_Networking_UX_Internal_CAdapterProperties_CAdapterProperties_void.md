# Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(void)

- ea: `0x18005641c`
- end: `0x18005651c`
- name: `??1CAdapterProperties@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `256`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180056570`

## callees

- `0x180008e30`
- `0x18000bb9c`
- `0x180056b9c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005645c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056471`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005645c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056471`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800564ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056501`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(
        HSTRING *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 20, a2, a3);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 19, v4, v5);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 17);
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 14, v6, v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13, v8, v9);
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(this);
}

```

## disassembly

```asm
0x18005641c  push    rbx
0x18005641e  sub     rsp, 20h
0x180056422  mov     rbx, rcx
0x180056425  add     rcx, 0A0h
0x18005642c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056431  lea     rcx, [rbx+98h]
0x180056438  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005643d  lea     rcx, [rbx+90h]
0x180056444  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180056449  lea     rcx, [rbx+88h]
0x180056450  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180056455  mov     rcx, [rbx+80h]; string
0x18005645c  call    cs:__imp_WindowsDeleteString
0x180056462  mov     qword ptr [rbx+80h], 0
0x18005646d  mov     rcx, [rbx+78h]; string
0x180056471  call    cs:__imp_WindowsDeleteString
0x180056477  lea     rcx, [rbx+70h]
0x18005647b  mov     qword ptr [rbx+78h], 0
0x180056483  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056488  lea     rcx, [rbx+68h]
0x18005648c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056491  mov     rcx, [rbx+60h]; string
0x180056495  call    cs:__imp_WindowsDeleteString
0x18005649b  mov     qword ptr [rbx+60h], 0
0x1800564a3  mov     rcx, [rbx+58h]; string
0x1800564a7  call    cs:__imp_WindowsDeleteString
0x1800564ad  mov     qword ptr [rbx+58h], 0
0x1800564b5  mov     rcx, [rbx+50h]; string
0x1800564b9  call    cs:__imp_WindowsDeleteString
0x1800564bf  mov     qword ptr [rbx+50h], 0
0x1800564c7  mov     rcx, [rbx+48h]; string
0x1800564cb  call    cs:__imp_WindowsDeleteString
0x1800564d1  mov     qword ptr [rbx+48h], 0
0x1800564d9  mov     rcx, [rbx+40h]; string
0x1800564dd  call    cs:__imp_WindowsDeleteString
0x1800564e3  mov     qword ptr [rbx+40h], 0
0x1800564eb  mov     rcx, [rbx+38h]; string
0x1800564ef  call    cs:__imp_WindowsDeleteString
0x1800564f5  mov     qword ptr [rbx+38h], 0
0x1800564fd  mov     rcx, [rbx+30h]; string
0x180056501  call    cs:__imp_WindowsDeleteString
0x180056507  mov     rcx, rbx
0x18005650a  mov     qword ptr [rbx+30h], 0
0x180056512  add     rsp, 20h
0x180056516  pop     rbx
0x180056517  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(void)
```
