# registry_access_error::registry_access_error(registry_access_error const &)

- ea: `0x18000e730`
- end: `0x18000e764`
- name: `??0registry_access_error@@QEAA@AEBV0@@Z`
- size: `52`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, const struct registry_access_error *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x18000e740`
- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x18000e740`

## pseudocode

```c
registry_access_error *__fastcall registry_access_error::registry_access_error(
        registry_access_error *this,
        const struct registry_access_error *a2)
{
  exception::exception(this, a2);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  return this;
}

```

## disassembly

```asm
0x18000e730  mov     [rsp+arg_0], rbx
0x18000e735  push    rdi
0x18000e736  sub     rsp, 20h
0x18000e73a  mov     rbx, rdx
0x18000e73d  mov     rdi, rcx
0x18000e740  call    cs:__imp_??0exception@@QEAA@AEBV0@@Z; exception::exception(exception const &)
0x18000e746  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e74d  mov     [rdi], rax
0x18000e750  mov     eax, [rbx+18h]
0x18000e753  mov     rbx, [rsp+28h+arg_0]
0x18000e758  mov     [rdi+18h], eax
0x18000e75b  mov     rax, rdi
0x18000e75e  add     rsp, 20h
0x18000e762  pop     rdi
0x18000e763  retn
```
