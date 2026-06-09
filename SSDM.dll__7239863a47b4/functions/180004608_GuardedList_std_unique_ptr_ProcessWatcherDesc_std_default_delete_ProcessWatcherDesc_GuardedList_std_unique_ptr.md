# GuardedList<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>::~GuardedList<std::unique_ptr<ProcessWatcherDesc,std::default_delete<ProcessWatcherDesc>>>(void)

- ea: `0x180004608`
- end: `0x18000460d`
- name: `??1?$GuardedList@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ef57`

## callees

- `0x1800046f4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall GuardedList<std::unique_ptr<ProcessWatcherDesc>>::~GuardedList<std::unique_ptr<ProcessWatcherDesc>>(
        __int64 a1)
{
  return std::list<std::unique_ptr<ProcessWatcherDesc>>::~list<std::unique_ptr<ProcessWatcherDesc>>(a1);
}

```

## disassembly

```asm
0x180004608  jmp     ??1?$list@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<ProcessWatcherDesc>>::~list<std::unique_ptr<ProcessWatcherDesc>>(void)
```
