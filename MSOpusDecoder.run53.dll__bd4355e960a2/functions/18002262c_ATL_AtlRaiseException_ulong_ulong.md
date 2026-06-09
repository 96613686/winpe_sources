# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18002262c`
- end: `0x18002263d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800201a0`
- `0x180020b20`
- `0x180021e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022636`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18002262c  xor     r9d, r9d
0x18002262f  xor     r8d, r8d
0x180022632  lea     edx, [r9+1]
0x180022636  jmp     cs:__imp_RaiseException
```
