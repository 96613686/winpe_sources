# SharingPlatform::DeviceIdentifier::~DeviceIdentifier(void)

- ea: `0x180047d70`
- end: `0x180047db3`
- name: `??1DeviceIdentifier@SharingPlatform@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(SharingPlatform::DeviceIdentifier *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180048550`

## callees

- `0x180004928`
- `0x18001c480`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d98`

## pseudocode

```c
void __fastcall SharingPlatform::DeviceIdentifier::~DeviceIdentifier(HSTRING *this)
{
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(this + 8);
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceIdentifier,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceIdentifierInternal>,Microsoft::WRL::CloakedIid<SharingPlatform::ISerializable>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceIdentifier,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceIdentifierInternal>,Microsoft::WRL::CloakedIid<SharingPlatform::ISerializable>>(this);
}

```

## disassembly

```asm
0x180047d70  push    rbx
0x180047d72  sub     rsp, 20h
0x180047d76  mov     rbx, rcx
0x180047d79  add     rcx, 40h ; '@'
0x180047d7d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180047d82  mov     rcx, [rbx+38h]; string
0x180047d86  call    cs:__imp_WindowsDeleteString
0x180047d8c  mov     qword ptr [rbx+38h], 0
0x180047d94  mov     rcx, [rbx+30h]; string
0x180047d98  call    cs:__imp_WindowsDeleteString
0x180047d9e  mov     rcx, rbx
0x180047da1  mov     qword ptr [rbx+30h], 0
0x180047da9  add     rsp, 20h
0x180047dad  pop     rbx
0x180047dae  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceIdentifier@SharingPlatform@@U?$CloakedIid@UIDeviceIdentifierInternal@SharingPlatform@@@23@U?$CloakedIid@UISerializable@SharingPlatform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceIdentifier,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceIdentifierInternal>,Microsoft::WRL::CloakedIid<SharingPlatform::ISerializable>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceIdentifier,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceIdentifierInternal>,Microsoft::WRL::CloakedIid<SharingPlatform::ISerializable>>(void)
```
