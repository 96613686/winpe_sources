# registry_access_error::registry_access_error(long)

- ea: `0x18000e76c`
- end: `0x18000e7aa`
- name: `??0registry_access_error@@QEAA@J@Z`
- size: `62`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, int)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000e800`
- `0x18000e884`
- `0x18000eb70`
- `0x18000ecf8`
- `0x18000edd0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000e788`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000e788`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
registry_access_error *__fastcall registry_access_error::registry_access_error(registry_access_error *this, int a2)
{
  exception::exception(this, &std::_bad_alloc_Message, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *((_DWORD *)this + 6) = a2;
  return this;
}

```

## disassembly

```asm
0x18000e76c  mov     [rsp+arg_0], rbx
0x18000e771  push    rdi
0x18000e772  sub     rsp, 20h
0x18000e776  mov     ebx, edx
0x18000e778  mov     rdi, rcx
0x18000e77b  mov     r8d, 1
0x18000e781  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18000e788  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000e78e  nop
0x18000e78f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e796  mov     [rdi], rax
0x18000e799  mov     [rdi+18h], ebx
0x18000e79c  mov     rax, rdi
0x18000e79f  mov     rbx, [rsp+28h+arg_0]
0x18000e7a4  add     rsp, 20h
0x18000e7a8  pop     rdi
0x18000e7a9  retn
```
