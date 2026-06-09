# Concurrency::agent::~agent(void)

- ea: `0x18013e17c`
- end: `0x18013e18f`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180180328`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_180180328((char *)this + 8);
}

```

## disassembly

```asm
0x18013e17c  lea     rax, ??_7exception@std@@6B@
0x18013e183  mov     [rcx], rax
0x18013e186  add     rcx, 8
0x18013e18a  jmp     sub_180180328
```
