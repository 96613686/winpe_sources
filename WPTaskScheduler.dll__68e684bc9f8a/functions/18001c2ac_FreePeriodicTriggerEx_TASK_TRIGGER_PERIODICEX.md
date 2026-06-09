# FreePeriodicTriggerEx(_TASK_TRIGGER_PERIODICEX *)

- ea: `0x18001c2ac`
- end: `0x18001c2d1`
- name: `?FreePeriodicTriggerEx@@YAXPEAU_TASK_TRIGGER_PERIODICEX@@@Z`
- size: `37`
- prototype: `void __fastcall(struct _TASK_TRIGGER_AGGREGATE **Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001c0e0`
- `0x18001c730`

## callees

- `0x18001c1a4`
- `0x18001c2ac`

## import_xrefs

- `msvcrt!free` at `0x18001c2c5`
- `msvcrt!free` at `0x18001c2c5`

## pseudocode

```c
void __fastcall FreePeriodicTriggerEx(struct _TASK_TRIGGER_AGGREGATE **Block)
{
  if ( Block )
  {
    FreeAggregateTrigger(Block[2]);
    free(Block);
  }
}

```

## disassembly

```asm
0x18001c2ac  test    rcx, rcx
0x18001c2af  jz      short locret_18001C2D0
0x18001c2b1  push    rbx
0x18001c2b2  sub     rsp, 20h
0x18001c2b6  mov     rbx, rcx
0x18001c2b9  mov     rcx, [rcx+10h]; Block
0x18001c2bd  call    ?FreeAggregateTrigger@@YAXPEAU_TASK_TRIGGER_AGGREGATE@@@Z; FreeAggregateTrigger(_TASK_TRIGGER_AGGREGATE *)
0x18001c2c2  mov     rcx, rbx; Block
0x18001c2c5  call    cs:__imp_free
0x18001c2cb  add     rsp, 20h
0x18001c2cf  pop     rbx
0x18001c2d0  retn
```
