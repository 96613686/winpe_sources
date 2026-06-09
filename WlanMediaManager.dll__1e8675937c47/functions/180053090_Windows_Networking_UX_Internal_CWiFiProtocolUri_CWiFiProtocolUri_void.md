# Windows::Networking::UX::Internal::CWiFiProtocolUri::~CWiFiProtocolUri(void)

- ea: `0x180053090`
- end: `0x1800530e2`
- name: `??1CWiFiProtocolUri@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `82`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180053230`

## callees

- `0x180008e30`
- `0x180039f1c`
- `0x180053060`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800530b5`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::~CWiFiProtocolUri(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8

  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  std::_Tree<std::_Tmap_traits<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>((void **)this + 11);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 64,
    v2,
    v3);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IWiFiProfile,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IWiFiProfile,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180053090  push    rbx
0x180053092  sub     rsp, 20h
0x180053096  mov     rbx, rcx
0x180053099  mov     rcx, [rcx+80h]; string
0x1800530a0  call    cs:__imp_WindowsDeleteString
0x1800530a6  mov     qword ptr [rbx+80h], 0
0x1800530b1  mov     rcx, [rbx+78h]; string
0x1800530b5  call    cs:__imp_WindowsDeleteString
0x1800530bb  lea     rcx, [rbx+58h]
0x1800530bf  mov     qword ptr [rbx+78h], 0
0x1800530c7  call    ??1?$_Tree@V?$_Tmap_traits@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@7@V?$allocator@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>(void)
0x1800530cc  lea     rcx, [rbx+40h]
0x1800530d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800530d5  mov     rcx, rbx
0x1800530d8  add     rsp, 20h
0x1800530dc  pop     rbx
0x1800530dd  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWiFiProfile@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IWiFiProfile,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IWiFiProfile,Microsoft::WRL::FtmBase>(void)
```
