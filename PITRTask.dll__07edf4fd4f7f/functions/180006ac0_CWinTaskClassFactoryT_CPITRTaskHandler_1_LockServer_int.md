# CWinTaskClassFactoryT<CPITRTaskHandler,1>::LockServer(int)

- ea: `0x180006ac0`
- end: `0x180006ad7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006ac0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180006ac0  test    edx, edx
0x180006ac2  jz      short loc_180006ACD
0x180006ac4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180006acb  jmp     short loc_180006AD4
0x180006acd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180006ad4  xor     eax, eax
0x180006ad6  retn
```
