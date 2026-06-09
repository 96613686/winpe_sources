# DllCanUnloadNow

- ea: `0x1800090f0`
- end: `0x180009108`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800090f0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 0;
  if ( fLocked || uUseCount )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800090f0  xor     eax, eax
0x1800090f2  cmp     cs:fLocked, eax
0x1800090f8  jnz     short loc_180009102
0x1800090fa  cmp     cs:uUseCount, eax
0x180009100  jz      short locret_180009107
0x180009102  mov     eax, 1
0x180009107  retn
```
