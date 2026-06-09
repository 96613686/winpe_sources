# std::default_delete<Broker::TimeEvent>::operator()(Broker::TimeEvent *)

- ea: `0x180011858`
- end: `0x18001187c`
- name: `??R?$default_delete@VTimeEvent@Broker@@@std@@QEBAXPEAVTimeEvent@Broker@@@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, __int64))`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a698`
- `0x18000d20c`
- `0x18000ef50`
- `0x180014c90`

## callees

- `0x180011858`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall std::default_delete<Broker::TimeEvent>::operator()(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  if ( a2 )
    return (**a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x180011858  sub     rsp, 28h
0x18001185c  mov     r8, rdx
0x18001185f  test    rdx, rdx
0x180011862  jz      short loc_180011877
0x180011864  mov     rax, [rdx]
0x180011867  mov     rcx, r8
0x18001186a  mov     edx, 1
0x18001186f  mov     rax, [rax]
0x180011872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011877  add     rsp, 28h
0x18001187b  retn
```
