# DllCanUnloadNow

- ea: `0x1800b7ab0`
- end: `0x1800b7ac8`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800b7ab0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 0;
  if ( dword_1800D90B0 || dword_1800E6940 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800b7ab0  xor     eax, eax
0x1800b7ab2  cmp     cs:dword_1800D90B0, eax
0x1800b7ab8  jnz     short loc_1800B7AC2
0x1800b7aba  cmp     cs:dword_1800E6940, eax
0x1800b7ac0  jz      short locret_1800B7AC7
0x1800b7ac2  mov     eax, 1
0x1800b7ac7  retn
```
