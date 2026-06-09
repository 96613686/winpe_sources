# DllCanUnloadNow

- ea: `0x1800327e0`
- end: `0x180032806`
- name: `DllCanUnloadNow`
- size: `38`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800327e0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800327f9`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_18009A8D0 || dword_18009A8D4 )
    return 1;
  else
    return NdrDllCanUnloadNow(&pPSFactoryBuffer);
}

```

## disassembly

```asm
0x1800327e0  cmp     cs:dword_18009A8D0, 0
0x1800327e7  jnz     short loc_180032800
0x1800327e9  cmp     cs:dword_18009A8D4, 0
0x1800327f0  jnz     short loc_180032800
0x1800327f2  lea     rcx, pPSFactoryBuffer
0x1800327f9  jmp     cs:NdrDllCanUnloadNow
0x180032800  mov     eax, 1
0x180032805  retn
```
