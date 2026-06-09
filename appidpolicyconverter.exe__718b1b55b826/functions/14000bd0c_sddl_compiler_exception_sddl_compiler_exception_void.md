# sddl_compiler_exception::~sddl_compiler_exception(void)

- ea: `0x14000bd0c`
- end: `0x14000bd28`
- name: `??1sddl_compiler_exception@@UEAA@XZ`
- size: `28`
- prototype: `void __fastcall(sddl_compiler_exception *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bd30`

## callees

- `0x14000a010`

## pseudocode

```c
void __fastcall sddl_compiler_exception::~sddl_compiler_exception(sddl_compiler_exception *this)
{
  *(_QWORD *)this = &sddl_compiler_exception::`vftable';
  policy_model_exception::~policy_model_exception(this);
}

```

## disassembly

```asm
0x14000bd0c  mov     [rsp+arg_0], rcx
0x14000bd11  sub     rsp, 28h
0x14000bd15  lea     rax, ??_7sddl_compiler_exception@@6B@; const sddl_compiler_exception::`vftable'
0x14000bd1c  mov     [rcx], rax
0x14000bd1f  add     rsp, 28h
0x14000bd23  jmp     ??1policy_model_exception@@UEAA@XZ; policy_model_exception::~policy_model_exception(void)
```
