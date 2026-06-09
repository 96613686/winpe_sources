# Windows::System::CMemoryManager::remove_AppMemoryUsageIncreased(EventRegistrationToken)

- ea: `0x180019160`
- end: `0x18001916c`
- name: `?remove_AppMemoryUsageIncreased@CMemoryManager@System@Windows@@UEAAJUEventRegistrationToken@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(Windows::System::CMemoryManager *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180018ca0`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::remove_AppMemoryUsageIncreased(
        Windows::System::CMemoryManager *this,
        struct EventRegistrationToken a2)
{
  return Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
           (RTL_SRWLOCK *)&Windows::System::CMemoryManager::s_levelIncreasedEvent,
           (struct IUnknown *)a2.value);
}

```

## disassembly

```asm
0x180019160  lea     rcx, ?s_levelIncreasedEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_levelIncreasedEvent
0x180019167  jmp     ?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)
```
