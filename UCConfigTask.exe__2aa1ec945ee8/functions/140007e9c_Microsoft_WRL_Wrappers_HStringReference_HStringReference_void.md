# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x140007e9c`
- end: `0x140007ea5`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400088b4`
- `0x1400088fc`
- `0x14000890e`
- `0x14000898c`

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
0x140007e9c  mov     qword ptr [rcx+18h], 0
0x140007ea4  retn
```
