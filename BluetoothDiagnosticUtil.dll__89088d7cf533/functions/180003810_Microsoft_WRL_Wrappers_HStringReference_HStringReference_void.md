# Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)

- ea: `0x180003810`
- end: `0x180003819`
- name: `??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a135`
- `0x18000a6c7`
- `0x18000a759`

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
0x180003810  mov     qword ptr [rcx+18h], 0
0x180003818  retn
```
