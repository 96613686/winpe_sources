# Windows::Networking::UX::CEthernetAuthConfig::~CEthernetAuthConfig(void)

- ea: `0x180007c94`
- end: `0x180007ce0`
- name: `??1CEthernetAuthConfig@UX@Networking@Windows@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008040`

## callees

- `0x180007c48`
- `0x18000955c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cbc`

## pseudocode

```c
void __fastcall Windows::Networking::UX::CEthernetAuthConfig::~CEthernetAuthConfig(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 9);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 6);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>((__int64)this);
}

```

## disassembly

```asm
0x180007c94  push    rbx
0x180007c96  sub     rsp, 20h
0x180007c9a  mov     rbx, rcx
0x180007c9d  add     rcx, 48h ; 'H'
0x180007ca1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007ca6  mov     rcx, [rbx+40h]; string
0x180007caa  call    cs:__imp_WindowsDeleteString
0x180007cb0  mov     qword ptr [rbx+40h], 0
0x180007cb8  mov     rcx, [rbx+38h]; string
0x180007cbc  call    cs:__imp_WindowsDeleteString
0x180007cc2  lea     rcx, [rbx+30h]
0x180007cc6  mov     qword ptr [rbx+38h], 0
0x180007cce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007cd3  mov     rcx, rbx
0x180007cd6  add     rsp, 20h
0x180007cda  pop     rbx
0x180007cdb  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIStaticIpConfig@UX@Networking@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IStaticIpConfig>(void)
```
