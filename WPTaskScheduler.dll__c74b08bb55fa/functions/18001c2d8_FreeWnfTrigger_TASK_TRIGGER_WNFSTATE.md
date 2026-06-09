# FreeWnfTrigger(_TASK_TRIGGER_WNFSTATE *)

- ea: `0x18001c2d8`
- end: `0x18001c303`
- name: `?FreeWnfTrigger@@YAXPEAU_TASK_TRIGGER_WNFSTATE@@@Z`
- size: `43`
- prototype: `void __fastcall(struct _TASK_TRIGGER_WNFSTATE *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001c0e0`
- `0x18001c280`
- `0x18001c890`

## callees

- `0x18001c2d8`

## import_xrefs

- `msvcrt!free` at `0x18001c2ee`
- `msvcrt!free` at `0x18001c2f7`
- `msvcrt!free` at `0x18001c2ee`
- `msvcrt!free` at `0x18001c2f7`

## pseudocode

```c
void __fastcall FreeWnfTrigger(struct _TASK_TRIGGER_WNFSTATE *Block)
{
  void *v2; // rcx

  if ( Block )
  {
    v2 = (void *)*((_QWORD *)Block + 2);
    if ( v2 )
      free(v2);
    free(Block);
  }
}

```

## disassembly

```asm
0x18001c2d8  test    rcx, rcx
0x18001c2db  jz      short locret_18001C302
0x18001c2dd  push    rbx
0x18001c2de  sub     rsp, 20h
0x18001c2e2  mov     rbx, rcx
0x18001c2e5  mov     rcx, [rcx+10h]; Block
0x18001c2e9  test    rcx, rcx
0x18001c2ec  jz      short loc_18001C2F4
0x18001c2ee  call    cs:__imp_free
0x18001c2f4  mov     rcx, rbx; Block
0x18001c2f7  call    cs:__imp_free
0x18001c2fd  add     rsp, 20h
0x18001c301  pop     rbx
0x18001c302  retn
```
