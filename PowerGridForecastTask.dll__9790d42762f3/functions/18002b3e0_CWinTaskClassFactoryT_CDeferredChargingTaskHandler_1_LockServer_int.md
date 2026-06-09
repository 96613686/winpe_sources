# CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::LockServer(int)

- ea: `0x18002b3e0`
- end: `0x18002b3f7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002b3e0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x18002b3e0  test    edx, edx
0x18002b3e2  jz      short loc_18002B3ED
0x18002b3e4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18002b3eb  jmp     short loc_18002B3F4
0x18002b3ed  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18002b3f4  xor     eax, eax
0x18002b3f6  retn
```
