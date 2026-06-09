# _anonymous_namespace_::ActionWNF::_ActionWNF

- ea: `0x180019ebc`
- end: `0x180019f47`
- name: `_anonymous_namespace_::ActionWNF::_ActionWNF`
- size: `139`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a000`

## callees

- `0x180019ebc`

## import_xrefs

- `UBPM!UbpmTriggerConsumerUnregister` at `0x180019f09`
- `UBPM!UbpmTriggerConsumerUnregister` at `0x180019f09`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180019eeb`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180019eeb`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180019f14`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180019f14`
- `msvcrt!free` at `0x180019f26`
- `msvcrt!free` at `0x180019f26`

## pseudocode

```c
void **__fastcall anonymous_namespace_::ActionWNF::_ActionWNF(_QWORD *a1)
{
  void *v2; // rcx
  void **result; // rax
  char v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  *a1 = &off_180023F48;
  v5 = 0;
  if ( !(unsigned int)UbpmOpenTriggerConsumer(a1 + 11, 0, &v6) )
  {
    v4 = 0;
    UbpmTriggerConsumerUnregister(v6, &v5, 0, 0, v4);
    UbpmCloseTriggerConsumer(v6);
  }
  v2 = (void *)a1[22];
  if ( v2 )
  {
    free(v2);
    a1[22] = 0;
  }
  result = &Action::`vftable';
  *a1 = &Action::`vftable';
  return result;
}

```

## disassembly

```asm
0x180019ebc  push    rbx
0x180019ebe  sub     rsp, 30h
0x180019ec2  lea     rax, off_180023F48
0x180019ec9  mov     [rsp+38h+arg_8], 0
0x180019ed2  mov     [rcx], rax
0x180019ed5  lea     r8, [rsp+38h+arg_8]
0x180019eda  mov     rbx, rcx
0x180019edd  mov     [rsp+38h+arg_0], 0
0x180019ee5  add     rcx, 58h ; 'X'
0x180019ee9  xor     edx, edx
0x180019eeb  call    cs:__imp_UbpmOpenTriggerConsumer
0x180019ef1  test    eax, eax
0x180019ef3  jnz     short loc_180019F1A
0x180019ef5  mov     rcx, [rsp+38h+arg_8]
0x180019efa  lea     rdx, [rsp+38h+arg_0]
0x180019eff  xor     r9d, r9d
0x180019f02  mov     [rsp+38h+var_18], al
0x180019f06  xor     r8d, r8d
0x180019f09  call    cs:__imp_UbpmTriggerConsumerUnregister
0x180019f0f  mov     rcx, [rsp+38h+arg_8]
0x180019f14  call    cs:__imp_UbpmCloseTriggerConsumer
0x180019f1a  mov     rcx, [rbx+0B0h]; Block
0x180019f21  test    rcx, rcx
0x180019f24  jz      short loc_180019F37
0x180019f26  call    cs:__imp_free
0x180019f2c  mov     qword ptr [rbx+0B0h], 0
0x180019f37  lea     rax, ??_7Action@@6B@; const Action::`vftable'
0x180019f3e  mov     [rbx], rax
0x180019f41  add     rsp, 30h
0x180019f45  pop     rbx
0x180019f46  retn
```
