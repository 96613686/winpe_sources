# DllCanUnloadNow

- ea: `0x1800563f0`
- end: `0x180056416`
- name: `DllCanUnloadNow`
- size: `38`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800563f0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180056409`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_18011CFAC || dword_18011CFA8 )
    return 1;
  else
    return NdrDllCanUnloadNow(&pPSFactoryBuffer);
}

```

## disassembly

```asm
0x1800563f0  cmp     cs:dword_18011CFAC, 0
0x1800563f7  jnz     short loc_180056410
0x1800563f9  cmp     cs:dword_18011CFA8, 0
0x180056400  jnz     short loc_180056410
0x180056402  lea     rcx, pPSFactoryBuffer
0x180056409  jmp     cs:NdrDllCanUnloadNow
0x180056410  mov     eax, 1
0x180056415  retn
```
