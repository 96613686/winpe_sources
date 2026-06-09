# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1400062fc`
- end: `0x14000630d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003bb0`
- `0x1400048d0`
- `0x140005c54`
- `0x140011c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140006306`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1400062fc  xor     r9d, r9d
0x1400062ff  xor     r8d, r8d
0x140006302  lea     edx, [r9+1]
0x140006306  jmp     cs:__imp_RaiseException
```
