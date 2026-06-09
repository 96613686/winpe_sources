# Concurrency::agent::~agent(void)

- ea: `0x180005808`
- end: `0x18000581b`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a94`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_180006A94((char *)this + 8);
}

```

## disassembly

```asm
0x180005808  lea     rax, ??_7exception@std@@6B@
0x18000580f  mov     [rcx], rax
0x180005812  add     rcx, 8
0x180005816  jmp     sub_180006A94
```
