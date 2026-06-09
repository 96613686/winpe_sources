# CIPSecurity::GetTypeInfoCount(uint *)

- ea: `0x18000a810`
- end: `0x18000a81f`
- name: `?GetTypeInfoCount@CIPSecurity@@UEAAJPEAI@Z`
- size: `15`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIPSecurity::GetTypeInfoCount(CIPSecurity *this, unsigned int *a2)
{
  return (***((__int64 (__fastcall ****)(_QWORD, unsigned int *))this + 2))(*((_QWORD *)this + 2), a2);
}

```

## disassembly

```asm
0x18000a810  mov     rcx, [rcx+10h]
0x18000a814  mov     rax, [rcx]
0x18000a817  mov     rax, [rax]
0x18000a81a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
