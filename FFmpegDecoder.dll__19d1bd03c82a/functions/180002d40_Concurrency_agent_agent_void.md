# Concurrency::agent::~agent(void)

- ea: `0x180002d40`
- end: `0x180002d53`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001a6bc`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  sub_18001A6BC((char *)this + 8);
}

```

## disassembly

```asm
0x180002d40  lea     rax, ??_7exception@std@@6B@
0x180002d47  mov     [rcx], rax
0x180002d4a  add     rcx, 8
0x180002d4e  jmp     sub_18001A6BC
```
