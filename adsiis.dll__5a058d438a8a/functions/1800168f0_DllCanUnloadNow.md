# DllCanUnloadNow

- ea: `0x1800168f0`
- end: `0x18001690d`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800168f0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // edx

  v0 = 1;
  if ( !ModuleCount::m_Count )
    return g_ulObjCount != 0;
  return v0;
}

```

## disassembly

```asm
0x1800168f0  cmp     cs:?m_Count@ModuleCount@@0JA, 0; long ModuleCount::m_Count
0x1800168f7  mov     edx, 1
0x1800168fc  jnz     short loc_18001690A
0x1800168fe  mov     eax, cs:?g_ulObjCount@@3KA; ulong g_ulObjCount
0x180016904  neg     eax
0x180016906  sbb     ecx, ecx
0x180016908  and     edx, ecx
0x18001690a  mov     eax, edx
0x18001690c  retn
```
