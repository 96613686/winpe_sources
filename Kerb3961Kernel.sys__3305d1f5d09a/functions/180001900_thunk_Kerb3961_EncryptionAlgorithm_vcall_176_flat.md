# [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}

- ea: `0x180001900`
- end: `0x18000190f`
- name: `??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028d4`
- `0x180003240`
- `0x180007338`
- `0x180007710`

## callees

- `0x180012240`

## pseudocode

```c
__int64 __fastcall  Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 176LL))(a1);
}

```

## disassembly

```asm
0x180001900  mov     rax, [rcx]
0x180001903  mov     rax, [rax+0B0h]
0x18000190a  jmp     _guard_dispatch_icall
```
