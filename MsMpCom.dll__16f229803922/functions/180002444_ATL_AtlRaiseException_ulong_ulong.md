# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180002444`
- end: `0x180002455`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002384`
- `0x180005c18`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000244e`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180002444  xor     r9d, r9d
0x180002447  xor     r8d, r8d
0x18000244a  lea     edx, [r9+1]
0x18000244e  jmp     cs:__imp_RaiseException
```
