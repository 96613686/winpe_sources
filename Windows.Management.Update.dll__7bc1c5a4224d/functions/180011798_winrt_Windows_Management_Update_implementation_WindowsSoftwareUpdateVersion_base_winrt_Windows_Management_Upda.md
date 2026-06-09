# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::~WindowsSoftwareUpdateVersion_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>(void)

- ea: `0x180011798`
- end: `0x18001179d`
- name: `??1?$WindowsSoftwareUpdateVersion_base@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180027a48`
- `0x180027a70`
- `0x180027abc`
- `0x180027afa`
- `0x180027bd2`
- `0x180027f5e`
- `0x180028147`
- `0x18002817c`
- `0x180028e14`

## callees

- `0x1800117a4`

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
0x180011798  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
```
