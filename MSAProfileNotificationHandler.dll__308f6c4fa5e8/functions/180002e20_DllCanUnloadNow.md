# DllCanUnloadNow

- ea: `0x180002e20`
- end: `0x180002e3b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002e20`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( g_cServerLocks )
    LODWORD(v0) = 1;
  else
    return g_cRefDll != 0;
  return v0;
}

```

## disassembly

```asm
0x180002e20  cmp     cs:?g_cServerLocks@@3JA, 0; long g_cServerLocks
0x180002e27  jnz     short loc_180002E35
0x180002e29  xor     eax, eax
0x180002e2b  cmp     cs:?g_cRefDll@@3JA, eax; long g_cRefDll
0x180002e31  setnz   al
0x180002e34  retn
0x180002e35  mov     eax, 1
0x180002e3a  retn
```
