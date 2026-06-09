# _anonymous_namespace_::ActionEvent::_ActionEvent

- ea: `0x18000d150`
- end: `0x18000d1db`
- name: `_anonymous_namespace_::ActionEvent::_ActionEvent`
- size: `139`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d110`

## callees

- `0x18000d150`

## import_xrefs

- `UBPM!UbpmTriggerConsumerUnregister` at `0x18000d19c`
- `UBPM!UbpmTriggerConsumerUnregister` at `0x18000d19c`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18000d17d`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18000d17d`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18000d1a7`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18000d1a7`
- `msvcrt!free` at `0x18000d1b9`
- `msvcrt!free` at `0x18000d1b9`

## pseudocode

```c
void **__fastcall anonymous_namespace_::ActionEvent::_ActionEvent(_QWORD *a1)
{
  void *v2; // rcx
  void **result; // rax
  char v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  *a1 = &off_180023278;
  v6 = 0;
  v5 = 0;
  if ( !(unsigned int)UbpmOpenTriggerConsumer(a1 + 11, 0, &v6) )
  {
    v4 = 0;
    UbpmTriggerConsumerUnregister(v6, &v5, 0, 0, v4);
    UbpmCloseTriggerConsumer(v6);
  }
  v2 = (void *)a1[21];
  if ( v2 )
  {
    free(v2);
    a1[21] = 0;
  }
  result = &Action::`vftable';
  *a1 = &Action::`vftable';
  return result;
}

```

## disassembly

```asm
0x18000d150  mov     [rsp+arg_10], rbx
0x18000d155  push    rdi
0x18000d156  sub     rsp, 30h
0x18000d15a  lea     rax, off_180023278
0x18000d161  mov     rbx, rcx
0x18000d164  mov     [rcx], rax
0x18000d167  lea     r8, [rsp+38h+arg_8]
0x18000d16c  xor     edi, edi
0x18000d16e  add     rcx, 58h ; 'X'
0x18000d172  xor     edx, edx
0x18000d174  mov     [rsp+38h+arg_8], rdi
0x18000d179  mov     [rsp+38h+arg_0], edi
0x18000d17d  call    cs:__imp_UbpmOpenTriggerConsumer
0x18000d183  test    eax, eax
0x18000d185  jnz     short loc_18000D1AD
0x18000d187  mov     rcx, [rsp+38h+arg_8]
0x18000d18c  lea     rdx, [rsp+38h+arg_0]
0x18000d191  xor     r9d, r9d
0x18000d194  mov     [rsp+38h+var_18], dil
0x18000d199  xor     r8d, r8d
0x18000d19c  call    cs:__imp_UbpmTriggerConsumerUnregister
0x18000d1a2  mov     rcx, [rsp+38h+arg_8]
0x18000d1a7  call    cs:__imp_UbpmCloseTriggerConsumer
0x18000d1ad  mov     rcx, [rbx+0A8h]; Block
0x18000d1b4  test    rcx, rcx
0x18000d1b7  jz      short loc_18000D1C6
0x18000d1b9  call    cs:__imp_free
0x18000d1bf  mov     [rbx+0A8h], rdi
0x18000d1c6  lea     rax, ??_7Action@@6B@; const Action::`vftable'
0x18000d1cd  mov     [rbx], rax
0x18000d1d0  mov     rbx, [rsp+38h+arg_10]
0x18000d1d5  add     rsp, 30h
0x18000d1d9  pop     rdi
0x18000d1da  retn
```
