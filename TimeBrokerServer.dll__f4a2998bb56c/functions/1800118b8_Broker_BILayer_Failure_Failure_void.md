# Broker::BILayer::Failure::~Failure(void)

- ea: `0x1800118b8`
- end: `0x1800118cb`
- name: `??1Failure@BILayer@Broker@@UEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Broker::BILayer::Failure *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a160`
- `0x18001a172`
- `0x18001a190`
- `0x18001a2e0`
- `0x18001a420`
- `0x18001a960`
- `0x18001a9a0`
- `0x18001a9f0`
- `0x18001aa30`

## callees

- `0x180013882`

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
0x1800118b8  lea     rax, ??_7exception@std@@6B@
0x1800118bf  mov     [rcx], rax
0x1800118c2  add     rcx, 8
0x1800118c6  jmp     _o___std_exception_destroy_0
```
