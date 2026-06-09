# EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults::~CustomAllDonePageResults(void)

- ea: `0x18004607c`
- end: `0x1800460f2`
- name: `??1CustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049b30`

## callees

- `0x18000db88`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800460d1`

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
0x18004607c  push    rbx
0x18004607e  sub     rsp, 20h
0x180046082  mov     rbx, rcx
0x180046085  mov     rcx, [rcx+58h]; string
0x180046089  call    cs:__imp_WindowsDeleteString
0x180046090  nop     dword ptr [rax+rax+00h]
0x180046095  mov     qword ptr [rbx+58h], 0
0x18004609d  mov     rcx, [rbx+50h]; string
0x1800460a1  call    cs:__imp_WindowsDeleteString
0x1800460a8  nop     dword ptr [rax+rax+00h]
0x1800460ad  mov     qword ptr [rbx+50h], 0
0x1800460b5  mov     rcx, [rbx+48h]; string
0x1800460b9  call    cs:__imp_WindowsDeleteString
0x1800460c0  nop     dword ptr [rax+rax+00h]
0x1800460c5  mov     qword ptr [rbx+48h], 0
0x1800460cd  mov     rcx, [rbx+40h]; string
0x1800460d1  call    cs:__imp_WindowsDeleteString
0x1800460d8  nop     dword ptr [rax+rax+00h]
0x1800460dd  mov     rcx, rbx
0x1800460e0  mov     qword ptr [rbx+40h], 0
0x1800460e8  add     rsp, 20h
0x1800460ec  pop     rbx
0x1800460ed  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
