# Windows::System::CMemoryManager::remove_AppMemoryUsageLimitChanging(EventRegistrationToken)

- ea: `0x180019180`
- end: `0x180019185`
- name: `?remove_AppMemoryUsageLimitChanging@CMemoryManager@System@Windows@@UEAAJUEventRegistrationToken@@@Z`
- size: `5`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::EventTargetArray *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180018e18`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::System::CMemoryManager::remove_AppMemoryUsageLimitChanging(
        Microsoft::WRL::Details::EventTargetArray *this,
        struct IUnknown *a2)
{
  return Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
           this,
           a2);
}

```

## disassembly

```asm
0x180019180  jmp     ?Remove@?$EventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
```
