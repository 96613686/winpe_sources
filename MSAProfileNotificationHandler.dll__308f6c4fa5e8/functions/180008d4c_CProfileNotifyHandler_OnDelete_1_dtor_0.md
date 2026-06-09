# _CProfileNotifyHandler::OnDelete_::_1_::dtor$0

- ea: `0x180008d4c`
- end: `0x180008d58`
- name: `_CProfileNotifyHandler::OnDelete_::_1_::dtor$0`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002974`

## pseudocode

```c
int __fastcall CProfileNotifyHandler::OnDelete_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(a2 + 48);
}

```

## disassembly

```asm
0x180008d4c  lea     rcx, [rdx+30h]
0x180008d53  jmp     ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
```
