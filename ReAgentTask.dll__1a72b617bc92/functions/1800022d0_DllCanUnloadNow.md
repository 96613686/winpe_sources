# DllCanUnloadNow

- ea: `0x1800022d0`
- end: `0x1800022e2`
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
0x1800022d0  xor     ecx, ecx
0x1800022d2  xor     eax, eax
0x1800022d4  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800022dc  mov     eax, ecx
0x1800022de  setnz   al
0x1800022e1  retn
```
