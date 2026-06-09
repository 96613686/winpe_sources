# EnterpriseDeviceManagement::Enrollment::DiscoverEndpointsResults::~DiscoverEndpointsResults(void)

- ea: `0x180024e3c`
- end: `0x180024e88`
- name: `??1DiscoverEndpointsResults@Enrollment@EnterpriseDeviceManagement@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Enrollment::DiscoverEndpointsResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029c70`

## callees

- `0x18000d69c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e6d`

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
0x180024e3c  push    rbx
0x180024e3e  sub     rsp, 20h
0x180024e42  mov     rbx, rcx
0x180024e45  mov     rcx, [rcx+58h]; string
0x180024e49  call    cs:__imp_WindowsDeleteString
0x180024e4f  mov     qword ptr [rbx+58h], 0
0x180024e57  mov     rcx, [rbx+50h]; string
0x180024e5b  call    cs:__imp_WindowsDeleteString
0x180024e61  mov     qword ptr [rbx+50h], 0
0x180024e69  mov     rcx, [rbx+48h]; string
0x180024e6d  call    cs:__imp_WindowsDeleteString
0x180024e73  mov     rcx, rbx
0x180024e76  mov     qword ptr [rbx+48h], 0
0x180024e7e  add     rsp, 20h
0x180024e82  pop     rbx
0x180024e83  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
