# DllCanUnloadNow

- ea: `0x18000f950`
- end: `0x18000f962`
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
0x18000f950  xor     ecx, ecx
0x18000f952  xor     eax, eax
0x18000f954  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000f95c  mov     eax, ecx
0x18000f95e  setnz   al
0x18000f961  retn
```
