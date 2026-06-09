# ScopedTaskCounter::~ScopedTaskCounter(void)

- ea: `0x18000cc60`
- end: `0x18000cc6f`
- name: `??1ScopedTaskCounter@@QEAA@XZ`
- size: `15`
- prototype: `void __fastcall(ScopedTaskCounter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001ef3f`
- `0x18001f18d`

## callees

- `0x180007bb4`

## pseudocode

```c
void __fastcall ScopedTaskCounter::~ScopedTaskCounter(ScopedTaskCounter *this)
{
  CTaskCounter::Decrement();
}

```

## disassembly

```asm
0x18000cc60  sub     rsp, 28h
0x18000cc64  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000cc69  nop
0x18000cc6a  add     rsp, 28h
0x18000cc6e  retn
```
