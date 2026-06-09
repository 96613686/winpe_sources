# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800089ec`
- end: `0x1800089fd`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004930`
- `0x18000639c`
- `0x180008d4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800089f6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800089ec  xor     r9d, r9d
0x1800089ef  xor     r8d, r8d
0x1800089f2  lea     edx, [r9+1]
0x1800089f6  jmp     cs:__imp_RaiseException
```
