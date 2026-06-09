# FreePeriodicTrigger(_TASK_TRIGGER_PERIODIC *)

- ea: `0x18001c280`
- end: `0x18001c2a5`
- name: `?FreePeriodicTrigger@@YAXPEAU_TASK_TRIGGER_PERIODIC@@@Z`
- size: `37`
- prototype: `void __fastcall(struct _TASK_TRIGGER_WNFSTATE **Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001c0e0`
- `0x18001c650`

## callees

- `0x18001c280`
- `0x18001c2d8`

## import_xrefs

- `msvcrt!free` at `0x18001c299`
- `msvcrt!free` at `0x18001c299`

## pseudocode

```c
void __fastcall FreePeriodicTrigger(struct _TASK_TRIGGER_WNFSTATE **Block)
{
  if ( Block )
  {
    FreeWnfTrigger(Block[2]);
    free(Block);
  }
}

```

## disassembly

```asm
0x18001c280  test    rcx, rcx
0x18001c283  jz      short locret_18001C2A4
0x18001c285  push    rbx
0x18001c286  sub     rsp, 20h
0x18001c28a  mov     rbx, rcx
0x18001c28d  mov     rcx, [rcx+10h]; Block
0x18001c291  call    ?FreeWnfTrigger@@YAXPEAU_TASK_TRIGGER_WNFSTATE@@@Z; FreeWnfTrigger(_TASK_TRIGGER_WNFSTATE *)
0x18001c296  mov     rcx, rbx; Block
0x18001c299  call    cs:__imp_free
0x18001c29f  add     rsp, 20h
0x18001c2a3  pop     rbx
0x18001c2a4  retn
```
