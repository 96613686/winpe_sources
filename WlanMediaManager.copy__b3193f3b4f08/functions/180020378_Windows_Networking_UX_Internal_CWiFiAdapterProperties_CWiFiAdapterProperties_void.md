# Windows::Networking::UX::Internal::CWiFiAdapterProperties::~CWiFiAdapterProperties(void)

- ea: `0x180020378`
- end: `0x1800203da`
- name: `??1CWiFiAdapterProperties@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CWiFiAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800209e0`

## callees

- `0x180008e30`
- `0x18000d5f0`
- `0x1800202c8`
- `0x180020378`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800203ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800203bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800203ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800203bf`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CWiFiAdapterProperties::~CWiFiAdapterProperties(
        Windows::Networking::UX::Internal::CWiFiAdapterProperties *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8

  if ( *((_QWORD *)this + 13) )
  {
    *((_QWORD *)this + 13) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::IMediaManager,Windows::Networking::UX::IWiFiSettings,Windows::Networking::UX::Internal::IProfileManagerNotificationClient,Windows::Networking::UX::Internal::INlmListener>::Release();
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 96,
    a2,
    a3);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 88,
    v4,
    v5);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<_GUID,Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *> *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<_GUID,Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *> *>>(this);
}

```

## disassembly

```asm
0x180020378  push    rbx
0x18002037a  sub     rsp, 20h
0x18002037e  mov     rbx, rcx
0x180020381  mov     rcx, [rcx+68h]
0x180020385  test    rcx, rcx
0x180020388  jz      short loc_180020397
0x18002038a  mov     qword ptr [rbx+68h], 0
0x180020392  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIMediaManager@Internal@UX@Networking@Windows@@UIWiFiSettings@678@VIProfileManagerNotificationClient@5678@VINlmListener@5678@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::IMediaManager,Windows::Networking::UX::IWiFiSettings,Windows::Networking::UX::Internal::IProfileManagerNotificationClient,Windows::Networking::UX::Internal::INlmListener>::Release(void)
0x180020397  lea     rcx, [rbx+60h]
0x18002039b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800203a0  lea     rcx, [rbx+58h]
0x1800203a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800203a9  mov     rcx, [rbx+40h]; string
0x1800203ad  call    cs:__imp_WindowsDeleteString
0x1800203b3  mov     qword ptr [rbx+40h], 0
0x1800203bb  mov     rcx, [rbx+38h]; string
0x1800203bf  call    cs:__imp_WindowsDeleteString
0x1800203c5  mov     rcx, rbx
0x1800203c8  mov     qword ptr [rbx+38h], 0
0x1800203d0  add     rsp, 20h
0x1800203d4  pop     rbx
0x1800203d5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMapView@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@567@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<_GUID,Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *> *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<_GUID,Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *> *>>(void)
```
