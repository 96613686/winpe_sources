# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800068ac`
- end: `0x1800068bd`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004350`
- `0x180004e2c`
- `0x180006238`
- `0x180009300`
- `0x18000a10c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800068b6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800068ac  xor     r9d, r9d
0x1800068af  xor     r8d, r8d
0x1800068b2  lea     edx, [r9+1]
0x1800068b6  jmp     cs:__imp_RaiseException
```
