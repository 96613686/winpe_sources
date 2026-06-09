# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000a0ec`
- end: `0x18000a0fd`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180006040`
- `0x180007aac`
- `0x18000a44c`
- `0x180011e20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a0f6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000a0ec  xor     r9d, r9d
0x18000a0ef  xor     r8d, r8d
0x18000a0f2  lea     edx, [r9+1]
0x18000a0f6  jmp     cs:__imp_RaiseException
```
