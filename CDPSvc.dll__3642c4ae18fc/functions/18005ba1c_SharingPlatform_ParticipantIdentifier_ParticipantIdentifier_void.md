# SharingPlatform::ParticipantIdentifier::~ParticipantIdentifier(void)

- ea: `0x18005ba1c`
- end: `0x18005ba7a`
- name: `??1ParticipantIdentifier@SharingPlatform@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(SharingPlatform::ParticipantIdentifier *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005bac0`

## callees

- `0x180004928`
- `0x18001bcfc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ba5f`

## pseudocode

```c
void __fastcall SharingPlatform::ParticipantIdentifier::~ParticipantIdentifier(HSTRING *this)
{
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(this + 11);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(this + 10);
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>(this);
}

```

## disassembly

```asm
0x18005ba1c  push    rbx
0x18005ba1e  sub     rsp, 20h
0x18005ba22  mov     rbx, rcx
0x18005ba25  add     rcx, 58h ; 'X'
0x18005ba29  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ba2e  lea     rcx, [rbx+50h]
0x18005ba32  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ba37  mov     rcx, [rbx+48h]; string
0x18005ba3b  call    cs:__imp_WindowsDeleteString
0x18005ba41  mov     qword ptr [rbx+48h], 0
0x18005ba49  mov     rcx, [rbx+40h]; string
0x18005ba4d  call    cs:__imp_WindowsDeleteString
0x18005ba53  mov     qword ptr [rbx+40h], 0
0x18005ba5b  mov     rcx, [rbx+38h]; string
0x18005ba5f  call    cs:__imp_WindowsDeleteString
0x18005ba65  mov     rcx, rbx
0x18005ba68  mov     qword ptr [rbx+38h], 0
0x18005ba70  add     rsp, 20h
0x18005ba74  pop     rbx
0x18005ba75  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceSessionBinaryChannel@SharingPlatform@@U?$CloakedIid@UIDeviceSessionChannelCallback@SharingPlatform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>(void)
```
