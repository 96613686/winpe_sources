# Windows::System::CMemoryManager::add_AppMemoryUsageIncreased(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180001420`
- end: `0x180001456`
- name: `?add_AppMemoryUsageIncreased@CMemoryManager@System@Windows@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@3@PEAUEventRegistrationToken@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001420`
- `0x18000145c`
- `0x180002750`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::add_AppMemoryUsageIncreased(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = Windows::System::CMemoryManager::Init();
  if ( (int)result >= 0 )
    return Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
             (__int64)&Windows::System::CMemoryManager::s_levelIncreasedEvent,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180001420  mov     [rsp+arg_0], rbx
0x180001425  push    rdi
0x180001426  sub     rsp, 20h
0x18000142a  mov     rbx, r8
0x18000142d  mov     rdi, rdx
0x180001430  call    ?Init@CMemoryManager@System@Windows@@CAJXZ; Windows::System::CMemoryManager::Init(void)
0x180001435  test    eax, eax
0x180001437  js      short loc_18000144B
0x180001439  mov     r8, rbx
0x18000143c  lea     rcx, ?s_levelIncreasedEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_levelIncreasedEvent
0x180001443  mov     rdx, rdi
0x180001446  call    ?Add@?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)
0x18000144b  mov     rbx, [rsp+28h+arg_0]
0x180001450  add     rsp, 20h
0x180001454  pop     rdi
0x180001455  retn
```
