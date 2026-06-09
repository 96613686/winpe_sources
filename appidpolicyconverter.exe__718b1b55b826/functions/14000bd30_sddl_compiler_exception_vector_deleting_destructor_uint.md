# sddl_compiler_exception::`vector deleting destructor'(uint)

- ea: `0x14000bd30`
- end: `0x14000bd5f`
- name: `??_Esddl_compiler_exception@@UEAAPEAXI@Z`
- size: `47`
- prototype: `sddl_compiler_exception *__fastcall(sddl_compiler_exception *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000157c`
- `0x14000bd0c`
- `0x14000bd30`

## pseudocode

```c
sddl_compiler_exception *__fastcall sddl_compiler_exception::`vector deleting destructor'(
        sddl_compiler_exception *this,
        char a2)
{
  sddl_compiler_exception::~sddl_compiler_exception(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000bd30  mov     [rsp+arg_0], rbx
0x14000bd35  push    rdi
0x14000bd36  sub     rsp, 20h
0x14000bd3a  mov     ebx, edx
0x14000bd3c  mov     rdi, rcx
0x14000bd3f  call    ??1sddl_compiler_exception@@UEAA@XZ; sddl_compiler_exception::~sddl_compiler_exception(void)
0x14000bd44  test    bl, 1
0x14000bd47  jz      short loc_14000BD51
0x14000bd49  mov     rcx, rdi; Block
0x14000bd4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bd51  mov     rbx, [rsp+28h+arg_0]
0x14000bd56  mov     rax, rdi
0x14000bd59  add     rsp, 20h
0x14000bd5d  pop     rdi
0x14000bd5e  retn
```
