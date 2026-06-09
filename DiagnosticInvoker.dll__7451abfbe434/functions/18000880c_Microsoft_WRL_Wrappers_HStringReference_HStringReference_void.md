# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x18000880c`
- end: `0x180008815`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010335`
- `0x180010359`
- `0x18001040d`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::~HStringReference(
        Microsoft::WRL::Wrappers::HStringReference *this)
{
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000880c  mov     qword ptr [rcx+18h], 0
0x180008814  retn
```
