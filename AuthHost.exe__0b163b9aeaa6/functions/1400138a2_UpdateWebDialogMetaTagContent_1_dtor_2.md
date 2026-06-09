# _UpdateWebDialogMetaTagContent_::_1_::dtor$2

- ea: `0x1400138a2`
- end: `0x1400138ae`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004794`

## pseudocode

```c
_QWORD *__fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>((_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x1400138a2  lea     rcx, [rdx+68h]
0x1400138a9  jmp     ??1?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowSizeChangedEventArgs@234@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>(void)
```
