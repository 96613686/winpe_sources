# CWinTaskClassFactoryT<CWofTasksHandler,1>::LockServer(int)

- ea: `0x180003510`
- end: `0x180003527`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003510`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CWofTasksHandler,1>::LockServer(__int64 a1, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  else
    _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  return 0;
}

```

## disassembly

```asm
0x180003510  test    edx, edx
0x180003512  jz      short loc_18000351D
0x180003514  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000351b  jmp     short loc_180003524
0x18000351d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003524  xor     eax, eax
0x180003526  retn
```
