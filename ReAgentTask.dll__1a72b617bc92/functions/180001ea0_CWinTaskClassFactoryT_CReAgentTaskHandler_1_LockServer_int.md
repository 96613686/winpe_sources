# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::LockServer(int)

- ea: `0x180001ea0`
- end: `0x180001eb7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001ea0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180001ea0  test    edx, edx
0x180001ea2  jz      short loc_180001EAD
0x180001ea4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001eab  jmp     short loc_180001EB4
0x180001ead  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001eb4  xor     eax, eax
0x180001eb6  retn
```
