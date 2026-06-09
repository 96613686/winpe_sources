# Windows::Networking::UX::WifiProfileInfo::~WifiProfileInfo(void)

- ea: `0x18002a43c`
- end: `0x18002a476`
- name: `??1WifiProfileInfo@UX@Networking@Windows@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Windows::Networking::UX::WifiProfileInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002a480`

## callees

- `0x18000bb9c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a45b`

## pseudocode

```c
void __fastcall Windows::Networking::UX::WifiProfileInfo::~WifiProfileInfo(HSTRING *this)
{
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(this);
}

```

## disassembly

```asm
0x18002a43c  push    rbx
0x18002a43e  sub     rsp, 20h
0x18002a442  mov     rbx, rcx
0x18002a445  mov     rcx, [rcx+28h]; string
0x18002a449  call    cs:__imp_WindowsDeleteString
0x18002a44f  mov     qword ptr [rbx+28h], 0
0x18002a457  mov     rcx, [rbx+20h]; string
0x18002a45b  call    cs:__imp_WindowsDeleteString
0x18002a461  mov     rcx, rbx
0x18002a464  mov     qword ptr [rbx+20h], 0
0x18002a46c  add     rsp, 20h
0x18002a470  pop     rbx
0x18002a471  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(void)
```
