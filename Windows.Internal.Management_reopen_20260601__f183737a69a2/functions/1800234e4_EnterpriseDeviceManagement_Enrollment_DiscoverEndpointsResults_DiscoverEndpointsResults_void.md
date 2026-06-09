# EnterpriseDeviceManagement::Enrollment::DiscoverEndpointsResults::~DiscoverEndpointsResults(void)

- ea: `0x1800234e4`
- end: `0x180023542`
- name: `??1DiscoverEndpointsResults@Enrollment@EnterpriseDeviceManagement@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Enrollment::DiscoverEndpointsResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028510`

## callees

- `0x18000db88`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023521`

## pseudocode

```c
void __fastcall EnterpriseDeviceManagement::Enrollment::DiscoverEndpointsResults::~DiscoverEndpointsResults(
        HSTRING *this)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800234e4  push    rbx
0x1800234e6  sub     rsp, 20h
0x1800234ea  mov     rbx, rcx
0x1800234ed  mov     rcx, [rcx+58h]; string
0x1800234f1  call    cs:__imp_WindowsDeleteString
0x1800234f8  nop     dword ptr [rax+rax+00h]
0x1800234fd  mov     qword ptr [rbx+58h], 0
0x180023505  mov     rcx, [rbx+50h]; string
0x180023509  call    cs:__imp_WindowsDeleteString
0x180023510  nop     dword ptr [rax+rax+00h]
0x180023515  mov     qword ptr [rbx+50h], 0
0x18002351d  mov     rcx, [rbx+48h]; string
0x180023521  call    cs:__imp_WindowsDeleteString
0x180023528  nop     dword ptr [rax+rax+00h]
0x18002352d  mov     rcx, rbx
0x180023530  mov     qword ptr [rbx+48h], 0
0x180023538  add     rsp, 20h
0x18002353c  pop     rbx
0x18002353d  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
