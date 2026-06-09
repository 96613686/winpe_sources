# CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::LockServer(int)

- ea: `0x180004df0`
- end: `0x180004e07`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004df0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180004df0  test    edx, edx
0x180004df2  jz      short loc_180004DFD
0x180004df4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004dfb  jmp     short loc_180004E04
0x180004dfd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004e04  xor     eax, eax
0x180004e06  retn
```
