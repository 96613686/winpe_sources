# DllCanUnloadNow

- ea: `0x18000b670`
- end: `0x18000b682`
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
0x18000b670  xor     ecx, ecx
0x18000b672  xor     eax, eax
0x18000b674  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000b67c  mov     eax, ecx
0x18000b67e  setnz   al
0x18000b681  retn
```
