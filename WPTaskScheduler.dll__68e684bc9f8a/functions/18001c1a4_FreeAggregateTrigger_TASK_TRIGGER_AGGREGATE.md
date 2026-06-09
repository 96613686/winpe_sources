# FreeAggregateTrigger(_TASK_TRIGGER_AGGREGATE *)

- ea: `0x18001c1a4`
- end: `0x18001c203`
- name: `?FreeAggregateTrigger@@YAXPEAU_TASK_TRIGGER_AGGREGATE@@@Z`
- size: `95`
- prototype: `void __fastcall(struct _TASK_TRIGGER_AGGREGATE *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001c0e0`
- `0x18001c2ac`

## callees

- `0x18001c0e0`
- `0x18001c1a4`

## import_xrefs

- `msvcrt!free` at `0x18001c1e4`
- `msvcrt!free` at `0x18001c1ed`
- `msvcrt!free` at `0x18001c1e4`
- `msvcrt!free` at `0x18001c1ed`

## pseudocode

```c
void __fastcall FreeAggregateTrigger(struct _TASK_TRIGGER_AGGREGATE *Block)
{
  struct _TASK_TRIGGER *v1; // rdi
  unsigned int i; // esi

  if ( Block )
  {
    v1 = (struct _TASK_TRIGGER *)*((_QWORD *)Block + 1);
    if ( v1 )
    {
      for ( i = 0; i < *((_DWORD *)Block + 1); v1 = (struct _TASK_TRIGGER *)((char *)v1 + 16) )
      {
        Trigger::Free(v1, 0);
        ++i;
      }
      free(*((void **)Block + 1));
    }
    free(Block);
  }
}

```

## disassembly

```asm
0x18001c1a4  test    rcx, rcx
0x18001c1a7  jz      short locret_18001C202
0x18001c1a9  mov     [rsp+arg_0], rbx
0x18001c1ae  mov     [rsp+arg_8], rsi
0x18001c1b3  push    rdi
0x18001c1b4  sub     rsp, 20h
0x18001c1b8  mov     rdi, [rcx+8]
0x18001c1bc  mov     rbx, rcx
0x18001c1bf  test    rdi, rdi
0x18001c1c2  jz      short loc_18001C1EA
0x18001c1c4  xor     esi, esi
0x18001c1c6  cmp     [rcx+4], esi
0x18001c1c9  jbe     short loc_18001C1E0
0x18001c1cb  xor     edx, edx; int
0x18001c1cd  mov     rcx, rdi; Block
0x18001c1d0  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x18001c1d5  inc     esi
0x18001c1d7  add     rdi, 10h
0x18001c1db  cmp     esi, [rbx+4]
0x18001c1de  jb      short loc_18001C1CB
0x18001c1e0  mov     rcx, [rbx+8]; Block
0x18001c1e4  call    cs:__imp_free
0x18001c1ea  mov     rcx, rbx; Block
0x18001c1ed  call    cs:__imp_free
0x18001c1f3  mov     rbx, [rsp+28h+arg_0]
0x18001c1f8  mov     rsi, [rsp+28h+arg_8]
0x18001c1fd  add     rsp, 20h
0x18001c201  pop     rdi
0x18001c202  retn
```
