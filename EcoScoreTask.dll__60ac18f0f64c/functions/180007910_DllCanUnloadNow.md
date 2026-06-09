# DllCanUnloadNow

- ea: `0x180007910`
- end: `0x180007922`
- name: `DllCanUnloadNow`
- size: `18`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) != 0;
}

```

## disassembly

```asm
0x180007910  xor     ecx, ecx
0x180007912  xor     eax, eax
0x180007914  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000791c  mov     eax, ecx
0x18000791e  setnz   al
0x180007921  retn
```
