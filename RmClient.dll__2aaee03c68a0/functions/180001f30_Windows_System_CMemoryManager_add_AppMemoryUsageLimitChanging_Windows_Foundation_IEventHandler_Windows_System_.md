# Windows::System::CMemoryManager::add_AppMemoryUsageLimitChanging(Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *> *,EventRegistrationToken *)

- ea: `0x180001f30`
- end: `0x180001f61`
- name: `?add_AppMemoryUsageLimitChanging@CMemoryManager@System@Windows@@UEAAJPEAU?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@3@PEAUEventRegistrationToken@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x180001f30`
- `0x180002750`

## pseudocode

```c
__int64 __fastcall Windows::System::CMemoryManager::add_AppMemoryUsageLimitChanging(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // rcx

  result = Windows::System::CMemoryManager::Init();
  if ( (int)result >= 0 )
    return Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
             v6,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_0], rbx
0x180001f35  push    rdi
0x180001f36  sub     rsp, 20h
0x180001f3a  mov     rbx, r8
0x180001f3d  mov     rdi, rdx
0x180001f40  call    ?Init@CMemoryManager@System@Windows@@CAJXZ; Windows::System::CMemoryManager::Init(void)
0x180001f45  test    eax, eax
0x180001f47  jns     short loc_180001F54
0x180001f49  mov     rbx, [rsp+28h+arg_0]
0x180001f4e  add     rsp, 20h
0x180001f52  pop     rdi
0x180001f53  retn
0x180001f54  mov     r8, rbx
0x180001f57  mov     rdx, rdi
0x180001f5a  call    ?Add@?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *> *,EventRegistrationToken *)
0x180001f5f  jmp     short loc_180001F49
```
