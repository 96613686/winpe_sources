# Broker::TimeEvent::GetWakeEnabled(void)

- ea: `0x180017910`
- end: `0x18001792f`
- name: `?GetWakeEnabled@TimeEvent@Broker@@UEAA_NXZ`
- size: `31`
- prototype: `bool __fastcall(Broker::TimeEvent *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800109bc`

## callees

- `0x18000c500`
- `0x180017910`

## pseudocode

```c
bool __fastcall Broker::TimeEvent::GetWakeEnabled(Broker::TimeEvent *this)
{
  bool result; // al

  result = Broker::TimeEvent::GetOnLockScreen(this);
  if ( result )
    return *((_BYTE *)this + 21) != 0;
  return result;
}

```

## disassembly

```asm
0x180017910  push    rbx
0x180017912  sub     rsp, 20h
0x180017916  mov     rbx, rcx
0x180017919  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x18001791e  test    al, al
0x180017920  jz      short loc_180017929
0x180017922  cmp     byte ptr [rbx+15h], 0
0x180017926  setnz   al
0x180017929  add     rsp, 20h
0x18001792d  pop     rbx
0x18001792e  retn
```
