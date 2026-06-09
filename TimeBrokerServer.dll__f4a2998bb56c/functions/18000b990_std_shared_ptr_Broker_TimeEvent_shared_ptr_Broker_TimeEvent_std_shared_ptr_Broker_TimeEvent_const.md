# std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)

- ea: `0x18000b990`
- end: `0x18000b9b8`
- name: `??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005d10`
- `0x1800061e0`
- `0x180010f0c`
- `0x180014568`
- `0x18001579c`
- `0x18001bd50`

## callees

- `0x18000b990`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000b990  xor     eax, eax
0x18000b992  mov     [rcx], rax
0x18000b995  mov     [rcx+8], rax
0x18000b999  mov     rax, [rdx+8]
0x18000b99d  test    rax, rax
0x18000b9a0  jz      short loc_18000B9A6
0x18000b9a2  lock inc dword ptr [rax+8]
0x18000b9a6  mov     rax, [rdx]
0x18000b9a9  mov     [rcx], rax
0x18000b9ac  mov     rax, [rdx+8]
0x18000b9b0  mov     [rcx+8], rax
0x18000b9b4  mov     rax, rcx
0x18000b9b7  retn
```
