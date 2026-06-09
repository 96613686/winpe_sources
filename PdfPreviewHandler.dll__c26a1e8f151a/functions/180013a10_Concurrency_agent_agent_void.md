# Concurrency::agent::~agent(void)

- ea: `0x180013a10`
- end: `0x180013a23`
- name: `??1agent@Concurrency@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::agent *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800139e0`
- `0x180013d80`

## callees

- `0x18002c860`

## pseudocode

```c
void __fastcall Concurrency::agent::~agent(Concurrency::agent *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  _std_exception_destroy((char *)this + 8);
}

```

## disassembly

```asm
0x180013a10  lea     rax, ??_7exception@std@@6B@
0x180013a17  mov     [rcx], rax
0x180013a1a  add     rcx, 8
0x180013a1e  jmp     __std_exception_destroy
```
