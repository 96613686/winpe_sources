# EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults::~CustomAllDonePageResults(void)

- ea: `0x18004641c`
- end: `0x18004647a`
- name: `??1CustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800499c0`

## callees

- `0x18000d69c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004643b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004644d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004645f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004643b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004644d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004645f`

## pseudocode

```c
void __fastcall EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults::~CustomAllDonePageResults(
        HSTRING *this)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18004641c  push    rbx
0x18004641e  sub     rsp, 20h
0x180046422  mov     rbx, rcx
0x180046425  mov     rcx, [rcx+58h]; string
0x180046429  call    cs:__imp_WindowsDeleteString
0x18004642f  mov     qword ptr [rbx+58h], 0
0x180046437  mov     rcx, [rbx+50h]; string
0x18004643b  call    cs:__imp_WindowsDeleteString
0x180046441  mov     qword ptr [rbx+50h], 0
0x180046449  mov     rcx, [rbx+48h]; string
0x18004644d  call    cs:__imp_WindowsDeleteString
0x180046453  mov     qword ptr [rbx+48h], 0
0x18004645b  mov     rcx, [rbx+40h]; string
0x18004645f  call    cs:__imp_WindowsDeleteString
0x180046465  mov     rcx, rbx
0x180046468  mov     qword ptr [rbx+40h], 0
0x180046470  add     rsp, 20h
0x180046474  pop     rbx
0x180046475  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
