# Broker::BILayer::Failure::~Failure(void)

- ea: `0x18001953c`
- end: `0x18001954f`
- name: `??1Failure@BILayer@Broker@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Broker::BILayer::Failure *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022ce0`
- `0x180022d00`
- `0x180023410`
- `0x180023660`
- `0x180023b80`
- `0x180023d70`
- `0x180023e40`
- `0x180023fc0`
- `0x180024240`
- `0x180024400`
- `0x180024bf5`

## callees

- `0x18001d8ba`

## pseudocode

```c
void __fastcall Broker::BILayer::Failure::~Failure(Broker::BILayer::Failure *this)
{
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy_0((char *)this + 8);
}

```

## disassembly

```asm
0x18001953c  lea     rax, ??_7exception@std@@6B@
0x180019543  mov     [rcx], rax
0x180019546  add     rcx, 8
0x18001954a  jmp     _o___std_exception_destroy_0
```
