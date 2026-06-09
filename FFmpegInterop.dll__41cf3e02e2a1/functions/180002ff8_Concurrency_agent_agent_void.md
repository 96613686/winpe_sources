# Concurrency::agent::~agent(void)

- ea: `0x180002ff8`
- end: `0x18000300b`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18002a54c`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_18002A54C((char *)this + 8);
}

```

## disassembly

```asm
0x180002ff8  lea     rax, ??_7exception@std@@6B@
0x180002fff  mov     [rcx], rax
0x180003002  add     rcx, 8
0x180003006  jmp     sub_18002A54C
```
