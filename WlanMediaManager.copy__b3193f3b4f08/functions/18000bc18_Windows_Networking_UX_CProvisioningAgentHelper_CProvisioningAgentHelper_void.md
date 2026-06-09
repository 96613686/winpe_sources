# Windows::Networking::UX::CProvisioningAgentHelper::~CProvisioningAgentHelper(void)

- ea: `0x18000bc18`
- end: `0x18000bc4a`
- name: `??1CProvisioningAgentHelper@UX@Networking@Windows@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Windows::Networking::UX::CProvisioningAgentHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x18000bb9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc2f`

## pseudocode

```c
void __fastcall Windows::Networking::UX::CProvisioningAgentHelper::~CProvisioningAgentHelper(
        Windows::Networking::UX::CProvisioningAgentHelper *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(this);
}

```

## disassembly

```asm
0x18000bc18  push    rbx
0x18000bc1a  sub     rsp, 20h
0x18000bc1e  mov     rbx, rcx
0x18000bc21  add     rcx, 30h ; '0'; lpCriticalSection
0x18000bc25  call    cs:__imp_DeleteCriticalSection
0x18000bc2b  mov     rcx, [rbx+20h]; string
0x18000bc2f  call    cs:__imp_WindowsDeleteString
0x18000bc35  mov     rcx, rbx
0x18000bc38  mov     qword ptr [rbx+20h], 0
0x18000bc40  add     rsp, 20h
0x18000bc44  pop     rbx
0x18000bc45  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@U_GUID@@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<_GUID,Windows::Networking::UX::IAvailableNetwork *>>(void)
```
