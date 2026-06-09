# DllCanUnloadNow

- ea: `0x180006410`
- end: `0x18000642b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006410`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_1800105B8 )
    LODWORD(v0) = 1;
  else
    return dword_1800105B4 != 0;
  return v0;
}

```

## disassembly

```asm
0x180006410  cmp     cs:dword_1800105B8, 0
0x180006417  jnz     short loc_180006425
0x180006419  xor     eax, eax
0x18000641b  cmp     cs:dword_1800105B4, eax
0x180006421  setnz   al
0x180006424  retn
0x180006425  mov     eax, 1
0x18000642a  retn
```
