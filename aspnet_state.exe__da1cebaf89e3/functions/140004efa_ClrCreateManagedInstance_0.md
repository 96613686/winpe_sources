# ClrCreateManagedInstance_0

- ea: `0x140004efa`
- end: `0x140004f00`
- name: `ClrCreateManagedInstance_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c50`

## import_xrefs

- `mscoree!ClrCreateManagedInstance` at `0x140004efa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ClrCreateManagedInstance_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return ClrCreateManagedInstance(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004efa  jmp     cs:__imp_ClrCreateManagedInstance
```
