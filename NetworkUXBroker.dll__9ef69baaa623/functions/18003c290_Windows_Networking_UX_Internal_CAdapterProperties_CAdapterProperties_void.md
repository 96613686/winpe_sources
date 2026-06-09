# Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(void)

- ea: `0x18003c290`
- end: `0x18003c390`
- name: `??1CAdapterProperties@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `256`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c500`

## callees

- `0x180007c48`
- `0x18000955c`
- `0x180009588`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c33f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c33f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c375`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 17);
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 13);
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
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>((__int64)this);
}

```

## disassembly

```asm
0x18003c290  push    rbx
0x18003c292  sub     rsp, 20h
0x18003c296  mov     rbx, rcx
0x18003c299  add     rcx, 0A0h
0x18003c2a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c2a5  lea     rcx, [rbx+98h]
0x18003c2ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c2b1  lea     rcx, [rbx+90h]
0x18003c2b8  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003c2bd  lea     rcx, [rbx+88h]
0x18003c2c4  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003c2c9  mov     rcx, [rbx+80h]; string
0x18003c2d0  call    cs:__imp_WindowsDeleteString
0x18003c2d6  mov     qword ptr [rbx+80h], 0
0x18003c2e1  mov     rcx, [rbx+78h]; string
0x18003c2e5  call    cs:__imp_WindowsDeleteString
0x18003c2eb  lea     rcx, [rbx+70h]
0x18003c2ef  mov     qword ptr [rbx+78h], 0
0x18003c2f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c2fc  lea     rcx, [rbx+68h]
0x18003c300  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c305  mov     rcx, [rbx+60h]; string
0x18003c309  call    cs:__imp_WindowsDeleteString
0x18003c30f  mov     qword ptr [rbx+60h], 0
0x18003c317  mov     rcx, [rbx+58h]; string
0x18003c31b  call    cs:__imp_WindowsDeleteString
0x18003c321  mov     qword ptr [rbx+58h], 0
0x18003c329  mov     rcx, [rbx+50h]; string
0x18003c32d  call    cs:__imp_WindowsDeleteString
0x18003c333  mov     qword ptr [rbx+50h], 0
0x18003c33b  mov     rcx, [rbx+48h]; string
0x18003c33f  call    cs:__imp_WindowsDeleteString
0x18003c345  mov     qword ptr [rbx+48h], 0
0x18003c34d  mov     rcx, [rbx+40h]; string
0x18003c351  call    cs:__imp_WindowsDeleteString
0x18003c357  mov     qword ptr [rbx+40h], 0
0x18003c35f  mov     rcx, [rbx+38h]; string
0x18003c363  call    cs:__imp_WindowsDeleteString
0x18003c369  mov     qword ptr [rbx+38h], 0
0x18003c371  mov     rcx, [rbx+30h]; string
0x18003c375  call    cs:__imp_WindowsDeleteString
0x18003c37b  mov     rcx, rbx
0x18003c37e  mov     qword ptr [rbx+30h], 0
0x18003c386  add     rsp, 20h
0x18003c38a  pop     rbx
0x18003c38b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIStaticIpConfig@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>(void)
```
