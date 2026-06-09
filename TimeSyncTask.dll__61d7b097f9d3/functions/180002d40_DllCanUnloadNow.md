# DllCanUnloadNow

- ea: `0x180002d40`
- end: `0x180002d52`
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
0x180002d40  xor     ecx, ecx
0x180002d42  xor     eax, eax
0x180002d44  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002d4c  mov     eax, ecx
0x180002d4e  setnz   al
0x180002d51  retn
```
