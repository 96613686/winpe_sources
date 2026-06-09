# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::~WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>(void)

- ea: `0x180012340`
- end: `0x180012345`
- name: `??1?$WindowsSoftwareUpdateVersion_base@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180028fa8`
- `0x180028fd0`
- `0x18002901c`
- `0x18002905a`
- `0x1800290f0`
- `0x180029486`
- `0x180029533`
- `0x1800296c2`
- `0x18002972a`
- `0x1800297b6`
- `0x18002a884`
- `0x18002a8ff`
- `0x18002ac8f`

## callees

- `0x18001234c`

## pseudocode

```c
// attributes: thunk
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::~WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>(
        __int64 a1)
{
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(a1);
}

```

## disassembly

```asm
0x180012340  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
```
