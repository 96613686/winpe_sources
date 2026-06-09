# Concurrency::agent::~agent(void)

- ea: `0x18000fa0c`
- end: `0x18000fa1f`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005d22`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy((char *)this + 8);
}

```

## disassembly

```asm
0x18000fa0c  lea     rax, ??_7exception@std@@6B@
0x18000fa13  mov     [rcx], rax
0x18000fa16  add     rcx, 8
0x18000fa1a  jmp     _o___std_exception_destroy
```
