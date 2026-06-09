# sddl_compiler_exception::sddl_compiler_exception(sddl_compiler_exception const &)

- ea: `0x14000bc88`
- end: `0x14000bcae`
- name: `??0sddl_compiler_exception@@QEAA@AEBV0@@Z`
- size: `38`
- prototype: `sddl_compiler_exception *__fastcall(sddl_compiler_exception *__hidden this, const struct sddl_compiler_exception *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009c08`

## pseudocode

```c
sddl_compiler_exception *__fastcall sddl_compiler_exception::sddl_compiler_exception(
        sddl_compiler_exception *this,
        const struct sddl_compiler_exception *a2)
{
  policy_model_exception::policy_model_exception(this, a2);
  *(_QWORD *)this = &sddl_compiler_exception::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000bc88  mov     [rsp+arg_0], rcx
0x14000bc8d  push    rbx
0x14000bc8e  sub     rsp, 20h
0x14000bc92  mov     rbx, rcx
0x14000bc95  call    ??0policy_model_exception@@QEAA@AEBV0@@Z; policy_model_exception::policy_model_exception(policy_model_exception const &)
0x14000bc9a  nop
0x14000bc9b  lea     rax, ??_7sddl_compiler_exception@@6B@; const sddl_compiler_exception::`vftable'
0x14000bca2  mov     [rbx], rax
0x14000bca5  mov     rax, rbx
0x14000bca8  add     rsp, 20h
0x14000bcac  pop     rbx
0x14000bcad  retn
```
