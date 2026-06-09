# NetSetup2::Property::~Property(void)

- ea: `0x18000d7f0`
- end: `0x18000d7f9`
- name: `??1Property@NetSetup2@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(NetSetup2::Property *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180012a39`
- `0x180012a4b`
- `0x1800141ba`
- `0x18001421e`
- `0x180014268`

## callees

- `0x18000ec70`

## pseudocode

```c
void __fastcall NetSetup2::Property::~Property(NetSetup2::Property *this)
{
  std::vector<unsigned char>::_Tidy((char *)this + 24);
}

```

## disassembly

```asm
0x18000d7f0  add     rcx, 18h
0x18000d7f4  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
