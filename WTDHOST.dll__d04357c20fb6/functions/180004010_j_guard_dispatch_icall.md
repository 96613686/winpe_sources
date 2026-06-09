# j__guard_dispatch_icall

- ea: `0x180004010`
- end: `0x180004015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x180001238`
- `0x1800013c4`
- `0x180001754`
- `0x1800019e4`
- `0x180001a28`
- `0x180002ddc`

## callees

- `0x180002f30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180004010  jmp     _guard_dispatch_icall
```
