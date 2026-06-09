# [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}

- ea: `0x1800018e8`
- end: `0x1800018f7`
- name: `??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA`
- size: `15`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023e0`
- `0x1800028d4`
- `0x180002cc4`
- `0x180003020`
- `0x180003240`
- `0x180003590`
- `0x180007338`
- `0x180007710`

## callees

- `0x180012240`

## pseudocode

```c
__int64 __fastcall  Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
}

```

## disassembly

```asm
0x1800018e8  mov     rax, [rcx]
0x1800018eb  mov     rax, [rax+0A0h]
0x1800018f2  jmp     _guard_dispatch_icall
```
