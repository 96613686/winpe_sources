# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000883c`
- end: `0x18000884d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004790`
- `0x1800061fc`
- `0x180008b9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008846`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000883c  xor     r9d, r9d
0x18000883f  xor     r8d, r8d
0x180008842  lea     edx, [r9+1]
0x180008846  jmp     cs:__imp_RaiseException
```
