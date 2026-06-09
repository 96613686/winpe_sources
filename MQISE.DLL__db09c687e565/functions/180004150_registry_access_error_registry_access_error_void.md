# registry_access_error::~registry_access_error(void)

- ea: `0x180004150`
- end: `0x180004161`
- name: `??1registry_access_error@@UEAA@XZ`
- size: `17`
- prototype: `void __fastcall(registry_access_error *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000415a`

## pseudocode

```c
void __fastcall registry_access_error::~registry_access_error(registry_access_error *this)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  exception::~exception(this);
}

```

## disassembly

```asm
0x180004150  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180004157  mov     [rcx], rax
0x18000415a  jmp     cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
```
