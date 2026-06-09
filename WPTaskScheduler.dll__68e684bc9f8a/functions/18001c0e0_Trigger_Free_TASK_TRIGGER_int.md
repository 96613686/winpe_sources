# Trigger::Free(_TASK_TRIGGER *,int)

- ea: `0x18001c0e0`
- end: `0x18001c19e`
- name: `?Free@Trigger@@SAJPEAU_TASK_TRIGGER@@H@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct _TASK_TRIGGER *Block, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180017e48`
- `0x18001c1a4`
- `0x18001c20c`
- `0x18001c310`

## callees

- `0x18001c0e0`
- `0x18001c1a4`
- `0x18001c20c`
- `0x18001c280`
- `0x18001c2ac`
- `0x18001c2d8`

## import_xrefs

- `msvcrt!free` at `0x18001c151`
- `msvcrt!free` at `0x18001c17f`
- `msvcrt!free` at `0x18001c151`
- `msvcrt!free` at `0x18001c17f`

## pseudocode

```c
__int64 __fastcall Trigger::Free(struct _TASK_TRIGGER *Block, int a2)
{
  unsigned int v4; // edi
  void *v5; // rcx

  if ( !Block )
    return (unsigned int)-2147467261;
  v4 = 0;
  if ( *(_DWORD *)&Block->cbTriggerSize )
  {
    switch ( *(_DWORD *)&Block->cbTriggerSize )
    {
      case 1:
        FreeWnfTrigger(*(struct _TASK_TRIGGER_WNFSTATE **)&Block->wBeginDay);
        break;
      case 2:
        FreeAggregateTrigger(*(struct _TASK_TRIGGER_AGGREGATE **)&Block->wBeginDay);
        break;
      case 3:
        goto LABEL_12;
      case 4:
        FreeCEAggregateTrigger(*(struct _TASK_TRIGGER_CEAGGREGATE **)&Block->wBeginDay);
        break;
      case 5:
LABEL_12:
        v5 = *(void **)&Block->wBeginDay;
        if ( v5 )
          free(v5);
        break;
      case 6:
        FreePeriodicTriggerEx(*(struct _TASK_TRIGGER_PERIODICEX **)&Block->wBeginDay);
        break;
      default:
        v4 = -2100362983;
        break;
    }
  }
  else
  {
    FreePeriodicTrigger(*(struct _TASK_TRIGGER_PERIODIC **)&Block->wBeginDay);
  }
  if ( a2 )
    free(Block);
  return v4;
}

```

## disassembly

```asm
0x18001c0e0  mov     [rsp+arg_0], rbx
0x18001c0e5  mov     [rsp+arg_8], rsi
0x18001c0ea  push    rdi
0x18001c0eb  sub     rsp, 20h
0x18001c0ef  mov     esi, edx
0x18001c0f1  mov     rbx, rcx
0x18001c0f4  test    rcx, rcx
0x18001c0f7  jz      loc_18001C187
0x18001c0fd  mov     r8d, [rcx]
0x18001c100  xor     edi, edi
0x18001c102  test    r8d, r8d
0x18001c105  jz      short loc_18001C16F
0x18001c107  sub     r8d, 1
0x18001c10b  jz      short loc_18001C164
0x18001c10d  sub     r8d, 1
0x18001c111  jz      short loc_18001C159
0x18001c113  sub     r8d, 1
0x18001c117  jz      short loc_18001C148
0x18001c119  sub     r8d, 1
0x18001c11d  jz      short loc_18001C13D
0x18001c11f  sub     r8d, 1
0x18001c123  jz      short loc_18001C148
0x18001c125  cmp     r8d, 1
0x18001c129  jz      short loc_18001C132
0x18001c12b  mov     edi, 82CF0119h
0x18001c130  jmp     short loc_18001C178
0x18001c132  mov     rcx, [rcx+8]; Block
0x18001c136  call    ?FreePeriodicTriggerEx@@YAXPEAU_TASK_TRIGGER_PERIODICEX@@@Z; FreePeriodicTriggerEx(_TASK_TRIGGER_PERIODICEX *)
0x18001c13b  jmp     short loc_18001C178
0x18001c13d  mov     rcx, [rcx+8]; Block
0x18001c141  call    ?FreeCEAggregateTrigger@@YAXPEAU_TASK_TRIGGER_CEAGGREGATE@@@Z; FreeCEAggregateTrigger(_TASK_TRIGGER_CEAGGREGATE *)
0x18001c146  jmp     short loc_18001C178
0x18001c148  mov     rcx, [rcx+8]; Block
0x18001c14c  test    rcx, rcx
0x18001c14f  jz      short loc_18001C178
0x18001c151  call    cs:__imp_free
0x18001c157  jmp     short loc_18001C178
0x18001c159  mov     rcx, [rcx+8]; Block
0x18001c15d  call    ?FreeAggregateTrigger@@YAXPEAU_TASK_TRIGGER_AGGREGATE@@@Z; FreeAggregateTrigger(_TASK_TRIGGER_AGGREGATE *)
0x18001c162  jmp     short loc_18001C178
0x18001c164  mov     rcx, [rcx+8]; Block
0x18001c168  call    ?FreeWnfTrigger@@YAXPEAU_TASK_TRIGGER_WNFSTATE@@@Z; FreeWnfTrigger(_TASK_TRIGGER_WNFSTATE *)
0x18001c16d  jmp     short loc_18001C178
0x18001c16f  mov     rcx, [rcx+8]; Block
0x18001c173  call    ?FreePeriodicTrigger@@YAXPEAU_TASK_TRIGGER_PERIODIC@@@Z; FreePeriodicTrigger(_TASK_TRIGGER_PERIODIC *)
0x18001c178  test    esi, esi
0x18001c17a  jz      short loc_18001C18C
0x18001c17c  mov     rcx, rbx; Block
0x18001c17f  call    cs:__imp_free
0x18001c185  jmp     short loc_18001C18C
0x18001c187  mov     edi, 80004003h
0x18001c18c  mov     rbx, [rsp+28h+arg_0]
0x18001c191  mov     eax, edi
0x18001c193  mov     rsi, [rsp+28h+arg_8]
0x18001c198  add     rsp, 20h
0x18001c19c  pop     rdi
0x18001c19d  retn
```
