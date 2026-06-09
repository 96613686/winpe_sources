# Broker::TimeEvent::NextPeriodicDueTime(__int64,__int64,__int64)

- ea: `0x18000a674`
- end: `0x18000a690`
- name: `?NextPeriodicDueTime@TimeEvent@Broker@@IEAA_J_J00@Z`
- size: `28`
- prototype: `__int64 __fastcall(Broker::TimeEvent *__hidden this, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008c70`
- `0x18000a100`
- `0x180016b40`

## callees

- `0x18000a674`

## pseudocode

```c
__int64 __fastcall Broker::TimeEvent::NextPeriodicDueTime(Broker::TimeEvent *this, __int64 a2, __int64 a3, __int64 a4)
{
  if ( a3 < a2 )
    return a2;
  else
    return a4 + a3 + (a2 - a3) % a4;
}

```

## disassembly

```asm
0x18000a674  cmp     r8, rdx
0x18000a677  jl      short loc_18000A68C
0x18000a679  sub     rdx, r8
0x18000a67c  mov     rax, rdx
0x18000a67f  cqo
0x18000a681  idiv    r9
0x18000a684  lea     rax, [r8+rdx]
0x18000a688  add     rax, r9
0x18000a68b  retn
0x18000a68c  mov     rax, rdx
0x18000a68f  retn
```
