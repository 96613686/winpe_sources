# Windows::System::CMemoryManager::OnCommitLevelChangeRoutine(_RM_COMMIT_LEVEL_CHANGE_PAYLOAD *)

- ea: `0x18000f660`
- end: `0x18000f67c`
- name: `?OnCommitLevelChangeRoutine@CMemoryManager@System@Windows@@CAXPEAU_RM_COMMIT_LEVEL_CHANGE_PAYLOAD@@@Z`
- size: `28`
- prototype: `void __fastcall(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f660`
- `0x18000f684`

## pseudocode

```c
void __fastcall Windows::System::CMemoryManager::OnCommitLevelChangeRoutine(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *a1)
{
  bool v1; // cc
  __int64 *v2; // rcx

  v1 = *((_DWORD *)a1 + 1) <= *(_DWORD *)a1;
  v2 = &Windows::System::CMemoryManager::s_levelIncreasedEvent;
  if ( v1 )
    v2 = &Windows::System::CMemoryManager::s_levelDecreasedEvent;
  Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(v2);
}

```

## disassembly

```asm
0x18000f660  mov     eax, [rcx]
0x18000f662  cmp     [rcx+4], eax
0x18000f665  lea     rcx, ?s_levelIncreasedEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_levelIncreasedEvent
0x18000f66c  jle     short loc_18000F673
0x18000f66e  jmp     ??$InvokeAll@$$T$$T@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJ$$T0@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,std::nullptr_t>(std::nullptr_t,std::nullptr_t)
0x18000f673  lea     rcx, ?s_levelDecreasedEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_levelDecreasedEvent
0x18000f67a  jmp     short loc_18000F66E
```
