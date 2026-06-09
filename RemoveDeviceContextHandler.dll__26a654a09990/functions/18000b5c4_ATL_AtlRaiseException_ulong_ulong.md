# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000b5c4`
- end: `0x18000b5d5`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006df4`
- `0x180006e1c`
- `0x180008ecc`
- `0x18000c0b0`
- `0x18000c668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b5ce`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000b5c4  xor     r9d, r9d
0x18000b5c7  xor     r8d, r8d
0x18000b5ca  lea     edx, [r9+1]
0x18000b5ce  jmp     cs:__imp_RaiseException
```
