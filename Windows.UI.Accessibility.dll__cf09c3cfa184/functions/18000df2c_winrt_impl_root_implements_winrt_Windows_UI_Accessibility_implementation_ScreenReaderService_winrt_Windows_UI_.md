# winrt::impl::root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>::~root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>(void)

- ea: `0x18000df2c`
- end: `0x18000df45`
- name: `??1?$root_implements@UScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e010`
- `0x18001328c`
- `0x18001375c`
- `0x180013d60`
- `0x1800196fc`
- `0x1800206c8`
- `0x180025bb0`
- `0x180025df0`
- `0x18002768c`
- `0x1800276b8`
- `0x180028f50`

## callees

- `0x180005cd4`
- `0x18000ef2c`

## pseudocode

```c
__int64 winrt::impl::root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>::~root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>()
{
  winrt::impl::root_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>::subtract_final_reference();
  return winrt::impl::atomic_ref_count::operator--(&`winrt::get_module_lock'::`2'::s_lock);
}

```

## disassembly

```asm
0x18000df2c  sub     rsp, 28h
0x18000df30  call    ?subtract_final_reference@?$root_implements@UFocusSessionThemeManager@factory_implementation@Shell@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@UIFocusSessionThemeManagerStatics@3456@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>::subtract_final_reference(void)
0x18000df35  lea     rcx, ?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000df3c  add     rsp, 28h
0x18000df40  jmp     ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
```
