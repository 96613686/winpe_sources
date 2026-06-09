# _anonymous_namespace_::ActionLaunch::_ActionLaunch

- ea: `0x180019e0c`
- end: `0x180019eb4`
- name: `_anonymous_namespace_::ActionLaunch::_ActionLaunch`
- size: `168`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019fc0`

## callees

- `0x180019e0c`

## import_xrefs

- `UBPM!UbpmTriggerConsumerUnregister` at `0x180019e59`
- `UBPM!UbpmTriggerConsumerUnregister` at `0x180019e59`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180019e3b`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180019e3b`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180019e64`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180019e64`
- `msvcrt!free` at `0x180019e76`
- `msvcrt!free` at `0x180019e93`
- `msvcrt!free` at `0x180019e76`
- `msvcrt!free` at `0x180019e93`

## pseudocode

```c
void **__fastcall anonymous_namespace_::ActionLaunch::_ActionLaunch(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void **result; // rax
  char v5; // [rsp+20h] [rbp-18h]
  int v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  *a1 = &off_180023F98;
  v6 = 0;
  if ( !(unsigned int)UbpmOpenTriggerConsumer(a1 + 11, 0, &v7) )
  {
    v5 = 0;
    UbpmTriggerConsumerUnregister(v7, &v6, 0, 0, v5);
    UbpmCloseTriggerConsumer(v7);
  }
  v2 = (void *)a1[20];
  if ( v2 )
  {
    free(v2);
    a1[20] = 0;
  }
  v3 = (void *)a1[21];
  if ( v3 )
  {
    free(v3);
    a1[21] = 0;
  }
  result = &Action::`vftable';
  *a1 = &Action::`vftable';
  return result;
}

```

## disassembly

```asm
0x180019e0c  push    rbx
0x180019e0e  sub     rsp, 30h
0x180019e12  lea     rax, off_180023F98
0x180019e19  mov     [rsp+38h+arg_8], 0
0x180019e22  mov     [rcx], rax
0x180019e25  lea     r8, [rsp+38h+arg_8]
0x180019e2a  mov     rbx, rcx
0x180019e2d  mov     [rsp+38h+arg_0], 0
0x180019e35  add     rcx, 58h ; 'X'
0x180019e39  xor     edx, edx
0x180019e3b  call    cs:__imp_UbpmOpenTriggerConsumer
0x180019e41  test    eax, eax
0x180019e43  jnz     short loc_180019E6A
0x180019e45  mov     rcx, [rsp+38h+arg_8]
0x180019e4a  lea     rdx, [rsp+38h+arg_0]
0x180019e4f  xor     r9d, r9d
0x180019e52  mov     [rsp+38h+var_18], al
0x180019e56  xor     r8d, r8d
0x180019e59  call    cs:__imp_UbpmTriggerConsumerUnregister
0x180019e5f  mov     rcx, [rsp+38h+arg_8]
0x180019e64  call    cs:__imp_UbpmCloseTriggerConsumer
0x180019e6a  mov     rcx, [rbx+0A0h]; Block
0x180019e71  test    rcx, rcx
0x180019e74  jz      short loc_180019E87
0x180019e76  call    cs:__imp_free
0x180019e7c  mov     qword ptr [rbx+0A0h], 0
0x180019e87  mov     rcx, [rbx+0A8h]; Block
0x180019e8e  test    rcx, rcx
0x180019e91  jz      short loc_180019EA4
0x180019e93  call    cs:__imp_free
0x180019e99  mov     qword ptr [rbx+0A8h], 0
0x180019ea4  lea     rax, ??_7Action@@6B@; const Action::`vftable'
0x180019eab  mov     [rbx], rax
0x180019eae  add     rsp, 30h
0x180019eb2  pop     rbx
0x180019eb3  retn
```
