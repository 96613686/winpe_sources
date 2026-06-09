# FreeCEAggregateTrigger(_TASK_TRIGGER_CEAGGREGATE *)

- ea: `0x18001c20c`
- end: `0x18001c27a`
- name: `?FreeCEAggregateTrigger@@YAXPEAU_TASK_TRIGGER_CEAGGREGATE@@@Z`
- size: `110`
- prototype: `void __fastcall(struct _TASK_TRIGGER_CEAGGREGATE *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001c0e0`
- `0x18001c4f0`

## callees

- `0x18001c0e0`
- `0x18001c20c`

## import_xrefs

- `msvcrt!free` at `0x18001c24c`
- `msvcrt!free` at `0x18001c264`
- `msvcrt!free` at `0x18001c24c`
- `msvcrt!free` at `0x18001c264`

## pseudocode

```c
void __fastcall FreeCEAggregateTrigger(struct _TASK_TRIGGER_CEAGGREGATE *Block)
{
  struct _TASK_TRIGGER *v1; // rdi
  unsigned int i; // esi

  if ( Block )
  {
    v1 = (struct _TASK_TRIGGER *)*((_QWORD *)Block + 2);
    if ( v1 )
    {
      for ( i = 0; i < *((_DWORD *)Block + 3); v1 = (struct _TASK_TRIGGER *)((char *)v1 + 16) )
      {
        Trigger::Free(v1, 0);
        ++i;
      }
      free(*((void **)Block + 2));
    }
    if ( *(_QWORD *)Block )
      Trigger::Free(*(struct _TASK_TRIGGER **)Block, 0);
    free(Block);
  }
}

```

## disassembly

```asm
0x18001c20c  test    rcx, rcx
0x18001c20f  jz      short locret_18001C279
0x18001c211  mov     [rsp+arg_0], rbx
0x18001c216  mov     [rsp+arg_8], rsi
0x18001c21b  push    rdi
0x18001c21c  sub     rsp, 20h
0x18001c220  mov     rdi, [rcx+10h]
0x18001c224  mov     rbx, rcx
0x18001c227  test    rdi, rdi
0x18001c22a  jz      short loc_18001C252
0x18001c22c  xor     esi, esi
0x18001c22e  cmp     [rcx+0Ch], esi
0x18001c231  jbe     short loc_18001C248
0x18001c233  xor     edx, edx; int
0x18001c235  mov     rcx, rdi; Block
0x18001c238  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x18001c23d  inc     esi
0x18001c23f  add     rdi, 10h
0x18001c243  cmp     esi, [rbx+0Ch]
0x18001c246  jb      short loc_18001C233
0x18001c248  mov     rcx, [rbx+10h]; Block
0x18001c24c  call    cs:__imp_free
0x18001c252  mov     rcx, [rbx]; Block
0x18001c255  test    rcx, rcx
0x18001c258  jz      short loc_18001C261
0x18001c25a  xor     edx, edx; int
0x18001c25c  call    ?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z; Trigger::Free(_TASK_TRIGGER *,int)
0x18001c261  mov     rcx, rbx; Block
0x18001c264  call    cs:__imp_free
0x18001c26a  mov     rbx, [rsp+28h+arg_0]
0x18001c26f  mov     rsi, [rsp+28h+arg_8]
0x18001c274  add     rsp, 20h
0x18001c278  pop     rdi
0x18001c279  retn
```
