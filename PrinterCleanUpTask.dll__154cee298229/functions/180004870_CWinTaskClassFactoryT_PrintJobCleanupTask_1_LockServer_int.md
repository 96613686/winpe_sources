# CWinTaskClassFactoryT<PrintJobCleanupTask,1>::LockServer(int)

- ea: `0x180004870`
- end: `0x180004877`
- name: `?LockServer@?$CWinTaskClassFactoryT@VPrintJobCleanupTask@@$00@@UEAAJH@Z`
- size: `7`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004880`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PrintJobCleanupTask,1>::LockServer(__int64 a1, int a2)
{
  return CWinTaskHandler::LockServer(a2);
}

```

## disassembly

```asm
0x180004870  mov     ecx, edx; int
0x180004872  jmp     ?LockServer@CWinTaskHandler@@CAJH@Z; CWinTaskHandler::LockServer(int)
```
