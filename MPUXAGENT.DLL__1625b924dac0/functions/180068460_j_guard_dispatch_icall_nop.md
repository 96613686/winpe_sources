# j__guard_dispatch_icall_nop

- ea: `0x180068460`
- end: `0x180068466`
- name: `j__guard_dispatch_icall_nop`
- size: `6`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000fc08`
- `0x18001fce0`
- `0x180021cd4`
- `0x180021d08`
- `0x180021eac`
- `0x180022080`
- `0x180022928`
- `0x180022cec`
- `0x180022d24`
- `0x180022d60`
- `0x180025928`
- `0x180026450`
- `0x1800266ac`
- `0x180026708`
- `0x180026754`
- `0x180026824`
- `0x1800268b8`
- `0x180026930`
- `0x180026998`
- `0x180026a20`
- `0x180026b14`
- `0x18002b0e8`
- `0x18002b168`
- `0x18002b1e0`

## callees

- `0x180068420`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180068460  jmp     cs:__guard_dispatch_icall_fptr
```
