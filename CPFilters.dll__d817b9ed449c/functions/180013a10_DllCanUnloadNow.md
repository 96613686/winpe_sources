# DllCanUnloadNow

- ea: `0x180013a10`
- end: `0x180013a35`
- name: `DllCanUnloadNow`
- size: `37`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013a10`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_180089858 > 0 || dword_180089860 )
    LODWORD(v0) = 1;
  else
    return dword_180089854 > 0;
  return v0;
}

```

## disassembly

```asm
0x180013a10  xor     ecx, ecx
0x180013a12  cmp     cs:dword_180089858, ecx
0x180013a18  jg      short loc_180013A2F
0x180013a1a  cmp     cs:dword_180089860, ecx
0x180013a20  jnz     short loc_180013A2F
0x180013a22  cmp     cs:dword_180089854, ecx
0x180013a28  mov     eax, ecx
0x180013a2a  setnle  al
0x180013a2d  retn
0x180013a2f  mov     eax, 1
0x180013a34  retn
```
