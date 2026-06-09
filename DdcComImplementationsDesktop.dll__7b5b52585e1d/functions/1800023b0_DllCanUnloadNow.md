# DllCanUnloadNow

- ea: `0x1800023b0`
- end: `0x1800023c2`
- name: `DllCanUnloadNow`
- size: `18`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return _InterlockedCompareExchange(&g_cInstances, 0, 0) != 0;
}

```

## disassembly

```asm
0x1800023b0  xor     ecx, ecx
0x1800023b2  xor     eax, eax
0x1800023b4  lock cmpxchg cs:?g_cInstances@@3JC, ecx; long volatile g_cInstances
0x1800023bc  mov     eax, ecx
0x1800023be  setnz   al
0x1800023c1  retn
```
