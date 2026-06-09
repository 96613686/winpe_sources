# Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(void)

- ea: `0x18004cbc4`
- end: `0x18004ccc4`
- name: `??1CAdapterProperties@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `256`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004ccd0`

## callees

- `0x180002150`
- `0x1800028d4`
- `0x1800263f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cca9`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::~CAdapterProperties(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(this + 17);
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 13);
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
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>(this);
}

```

## disassembly

```asm
0x18004cbc4  push    rbx
0x18004cbc6  sub     rsp, 20h
0x18004cbca  mov     rbx, rcx
0x18004cbcd  add     rcx, 0A0h
0x18004cbd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cbd9  lea     rcx, [rbx+98h]
0x18004cbe0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cbe5  lea     rcx, [rbx+90h]
0x18004cbec  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18004cbf1  lea     rcx, [rbx+88h]
0x18004cbf8  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18004cbfd  mov     rcx, [rbx+80h]; string
0x18004cc04  call    cs:__imp_WindowsDeleteString
0x18004cc0a  mov     qword ptr [rbx+80h], 0
0x18004cc15  mov     rcx, [rbx+78h]; string
0x18004cc19  call    cs:__imp_WindowsDeleteString
0x18004cc1f  lea     rcx, [rbx+70h]
0x18004cc23  mov     qword ptr [rbx+78h], 0
0x18004cc2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cc30  lea     rcx, [rbx+68h]
0x18004cc34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cc39  mov     rcx, [rbx+60h]; string
0x18004cc3d  call    cs:__imp_WindowsDeleteString
0x18004cc43  mov     qword ptr [rbx+60h], 0
0x18004cc4b  mov     rcx, [rbx+58h]; string
0x18004cc4f  call    cs:__imp_WindowsDeleteString
0x18004cc55  mov     qword ptr [rbx+58h], 0
0x18004cc5d  mov     rcx, [rbx+50h]; string
0x18004cc61  call    cs:__imp_WindowsDeleteString
0x18004cc67  mov     qword ptr [rbx+50h], 0
0x18004cc6f  mov     rcx, [rbx+48h]; string
0x18004cc73  call    cs:__imp_WindowsDeleteString
0x18004cc79  mov     qword ptr [rbx+48h], 0
0x18004cc81  mov     rcx, [rbx+40h]; string
0x18004cc85  call    cs:__imp_WindowsDeleteString
0x18004cc8b  mov     qword ptr [rbx+40h], 0
0x18004cc93  mov     rcx, [rbx+38h]; string
0x18004cc97  call    cs:__imp_WindowsDeleteString
0x18004cc9d  mov     qword ptr [rbx+38h], 0
0x18004cca5  mov     rcx, [rbx+30h]; string
0x18004cca9  call    cs:__imp_WindowsDeleteString
0x18004ccaf  mov     rcx, rbx
0x18004ccb2  mov     qword ptr [rbx+30h], 0
0x18004ccba  add     rsp, 20h
0x18004ccbe  pop     rbx
0x18004ccbf  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMbConnectionProfile@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IMbConnectionProfile>(void)
```
