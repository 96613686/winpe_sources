# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180004e44`
- end: `0x180004e55`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000226c`
- `0x180003558`
- `0x180003580`
- `0x180003a94`
- `0x180005e70`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180004e4e`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180004e44  xor     r9d, r9d
0x180004e47  xor     r8d, r8d
0x180004e4a  lea     edx, [r9+1]
0x180004e4e  jmp     cs:__imp_RaiseException
```
