# Windows::Networking::UX::Internal::MBAdapterProperties::~MBAdapterProperties(void)

- ea: `0x18002341c`
- end: `0x1800234a7`
- name: `??1MBAdapterProperties@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `139`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800233e0`

## callees

- `0x180002150`
- `0x1800234b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002347a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002348c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002347a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002348c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBAdapterProperties::~MBAdapterProperties(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 15);
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<enum Windows::Networking::UX::NetworkMediaType>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<enum Windows::Networking::UX::NetworkMediaType>>(this);
}

```

## disassembly

```asm
0x18002341c  push    rbx
0x18002341e  sub     rsp, 20h
0x180023422  mov     rbx, rcx
0x180023425  add     rcx, 78h ; 'x'
0x180023429  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002342e  mov     rcx, [rbx+70h]; string
0x180023432  call    cs:__imp_WindowsDeleteString
0x180023438  mov     qword ptr [rbx+70h], 0
0x180023440  mov     rcx, [rbx+68h]; string
0x180023444  call    cs:__imp_WindowsDeleteString
0x18002344a  mov     qword ptr [rbx+68h], 0
0x180023452  mov     rcx, [rbx+60h]; string
0x180023456  call    cs:__imp_WindowsDeleteString
0x18002345c  mov     qword ptr [rbx+60h], 0
0x180023464  mov     rcx, [rbx+58h]; string
0x180023468  call    cs:__imp_WindowsDeleteString
0x18002346e  mov     qword ptr [rbx+58h], 0
0x180023476  mov     rcx, [rbx+48h]; string
0x18002347a  call    cs:__imp_WindowsDeleteString
0x180023480  mov     qword ptr [rbx+48h], 0
0x180023488  mov     rcx, [rbx+38h]; string
0x18002348c  call    cs:__imp_WindowsDeleteString
0x180023492  mov     rcx, rbx
0x180023495  mov     qword ptr [rbx+38h], 0
0x18002349d  add     rsp, 20h
0x1800234a1  pop     rbx
0x1800234a2  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@W4NetworkMediaType@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@W4NetworkMediaType@UX@Networking@Windows@@@567@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::NetworkMediaType>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::NetworkMediaType>>(void)
```
