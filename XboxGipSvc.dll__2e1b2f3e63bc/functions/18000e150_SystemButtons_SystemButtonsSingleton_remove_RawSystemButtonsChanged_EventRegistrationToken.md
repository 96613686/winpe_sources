# SystemButtons::SystemButtonsSingleton::remove_RawSystemButtonsChanged(EventRegistrationToken)

- ea: `0x18000e150`
- end: `0x18000e159`
- name: `?remove_RawSystemButtonsChanged@SystemButtonsSingleton@SystemButtons@@UEAAJUEventRegistrationToken@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(SystemButtons::SystemButtonsSingleton *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000da00`

## pseudocode

```c
__int64 __fastcall SystemButtons::SystemButtonsSingleton::remove_RawSystemButtonsChanged(
        SystemButtons::SystemButtonsSingleton *this,
        struct EventRegistrationToken a2)
{
  return Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(
           (__int64)this + 72,
           a2.value);
}

```

## disassembly

```asm
0x18000e150  add     rcx, 48h ; 'H'
0x18000e154  jmp     ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(EventRegistrationToken)
```
