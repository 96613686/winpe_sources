# Windows::Networking::UX::Internal::CWiFiEapMethod::~CWiFiEapMethod(void)

- ea: `0x18003a298`
- end: `0x18003a2db`
- name: `??1CWiFiEapMethod@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CWiFiEapMethod *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003b5e0`

## callees

- `0x180008e30`
- `0x18000bb9c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2c0`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CWiFiEapMethod::~CWiFiEapMethod(
        HSTRING *this,
        __int64 a2,
        __int64 a3)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 7, a2, a3);
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(this);
}

```

## disassembly

```asm
0x18003a298  push    rbx
0x18003a29a  sub     rsp, 20h
0x18003a29e  mov     rbx, rcx
0x18003a2a1  add     rcx, 38h ; '8'
0x18003a2a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a2aa  mov     rcx, [rbx+30h]; string
0x18003a2ae  call    cs:__imp_WindowsDeleteString
0x18003a2b4  mov     qword ptr [rbx+30h], 0
0x18003a2bc  mov     rcx, [rbx+28h]; string
0x18003a2c0  call    cs:__imp_WindowsDeleteString
0x18003a2c6  mov     rcx, rbx
0x18003a2c9  mov     qword ptr [rbx+28h], 0
0x18003a2d1  add     rsp, 20h
0x18003a2d5  pop     rbx
0x18003a2d6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(void)
```
