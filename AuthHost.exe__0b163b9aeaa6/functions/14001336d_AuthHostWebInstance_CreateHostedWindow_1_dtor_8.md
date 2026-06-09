# _AuthHostWebInstance::CreateHostedWindow_::_1_::dtor$8

- ea: `0x14001336d`
- end: `0x140013379`
- name: `_AuthHostWebInstance::CreateHostedWindow_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004794`

## pseudocode

```c
_QWORD *__fastcall AuthHostWebInstance::CreateHostedWindow_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>((_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x14001336d  lea     rcx, [rdx+20h]
0x140013374  jmp     ??1?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowSizeChangedEventArgs@234@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>(void)
```
