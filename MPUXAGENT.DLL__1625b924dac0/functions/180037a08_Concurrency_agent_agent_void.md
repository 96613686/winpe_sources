# Concurrency::agent::~agent(void)

- ea: `0x180037a08`
- end: `0x180037a1b`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18006bdd2`

## callees

- `0x18000b7f0`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_18000B7F0((char *)this + 8);
}

```

## disassembly

```asm
0x180037a08  lea     rax, ??_7exception@std@@6B@
0x180037a0f  mov     [rcx], rax
0x180037a12  add     rcx, 8
0x180037a16  jmp     sub_18000B7F0
```
