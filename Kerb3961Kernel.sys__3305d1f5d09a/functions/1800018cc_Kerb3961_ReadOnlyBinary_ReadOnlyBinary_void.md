# Kerb3961::ReadOnlyBinary::ReadOnlyBinary(void)

- ea: `0x1800018cc`
- end: `0x1800018df`
- name: `??0ReadOnlyBinary@Kerb3961@@QEAA@XZ`
- size: `19`
- prototype: `__int64 __fastcall(Kerb3961::ReadOnlyBinary *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015f0`
- `0x180001700`

## pseudocode

```c
Kerb3961::ReadOnlyBinary *__fastcall Kerb3961::ReadOnlyBinary::ReadOnlyBinary(Kerb3961::ReadOnlyBinary *this)
{
  Kerb3961::ReadOnlyBinary *result; // rax

  *(_QWORD *)this = 0;
  result = this;
  *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x1800018cc  mov     qword ptr [rcx], 0
0x1800018d3  mov     rax, rcx
0x1800018d6  mov     qword ptr [rcx+8], 0
0x1800018de  retn
```
