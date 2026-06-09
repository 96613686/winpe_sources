# Concurrency::agent::~agent(void)

- ea: `0x180003040`
- end: `0x180003053`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180167298`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_180167298((char *)this + 8);
}

```

## disassembly

```asm
0x180003040  lea     rax, ??_7exception@std@@6B@
0x180003047  mov     [rcx], rax
0x18000304a  add     rcx, 8
0x18000304e  jmp     sub_180167298
```
