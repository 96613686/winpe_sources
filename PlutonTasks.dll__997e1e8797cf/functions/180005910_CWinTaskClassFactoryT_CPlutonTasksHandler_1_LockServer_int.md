# CWinTaskClassFactoryT<CPlutonTasksHandler,1>::LockServer(int)

- ea: `0x180005910`
- end: `0x180005917`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@UEAAJH@Z`
- size: `7`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180005920`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPlutonTasksHandler,1>::LockServer(__int64 a1, int a2)
{
  return CWinTaskHandler::LockServer(a2);
}

```

## disassembly

```asm
0x180005910  mov     ecx, edx; int
0x180005912  jmp     ?LockServer@CWinTaskHandler@@CAJH@Z; CWinTaskHandler::LockServer(int)
```
