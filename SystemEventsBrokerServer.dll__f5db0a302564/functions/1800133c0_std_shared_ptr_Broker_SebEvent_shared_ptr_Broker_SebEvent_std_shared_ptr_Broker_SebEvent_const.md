# std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(std::shared_ptr<Broker::SebEvent> const &)

- ea: `0x1800133c0`
- end: `0x1800133e8`
- name: `??0?$shared_ptr@VSebEvent@Broker@@@std@@QEAA@AEBV01@@Z`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007880`
- `0x180012b8c`
- `0x180019b60`
- `0x18001ae14`
- `0x18001b378`
- `0x18001ecd0`
- `0x180020220`

## callees

- `0x1800133c0`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::SebEvent>::shared_ptr<Broker::SebEvent>(_QWORD *a1, _QWORD *a2)
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
0x1800133c0  xor     eax, eax
0x1800133c2  mov     [rcx], rax
0x1800133c5  mov     [rcx+8], rax
0x1800133c9  mov     rax, [rdx+8]
0x1800133cd  test    rax, rax
0x1800133d0  jz      short loc_1800133D6
0x1800133d2  lock inc dword ptr [rax+8]
0x1800133d6  mov     rax, [rdx]
0x1800133d9  mov     [rcx], rax
0x1800133dc  mov     rax, [rdx+8]
0x1800133e0  mov     [rcx+8], rax
0x1800133e4  mov     rax, rcx
0x1800133e7  retn
```
