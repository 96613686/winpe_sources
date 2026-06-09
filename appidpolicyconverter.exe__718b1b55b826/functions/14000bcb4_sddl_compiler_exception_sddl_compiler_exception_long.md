# sddl_compiler_exception::sddl_compiler_exception(long)

- ea: `0x14000bcb4`
- end: `0x14000bcda`
- name: `??0sddl_compiler_exception@@QEAA@J@Z`
- size: `38`
- prototype: `sddl_compiler_exception *__fastcall(sddl_compiler_exception *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c308`

## callees

- `0x140009c34`

## pseudocode

```c
sddl_compiler_exception *__fastcall sddl_compiler_exception::sddl_compiler_exception(
        sddl_compiler_exception *this,
        int a2)
{
  policy_model_exception::policy_model_exception(this, a2);
  *(_QWORD *)this = &sddl_compiler_exception::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000bcb4  mov     [rsp+arg_0], rcx
0x14000bcb9  push    rbx
0x14000bcba  sub     rsp, 20h
0x14000bcbe  mov     rbx, rcx
0x14000bcc1  call    ??0policy_model_exception@@QEAA@J@Z; policy_model_exception::policy_model_exception(long)
0x14000bcc6  nop
0x14000bcc7  lea     rax, ??_7sddl_compiler_exception@@6B@; const sddl_compiler_exception::`vftable'
0x14000bcce  mov     [rbx], rax
0x14000bcd1  mov     rax, rbx
0x14000bcd4  add     rsp, 20h
0x14000bcd8  pop     rbx
0x14000bcd9  retn
```
