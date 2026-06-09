# CPrintCoreConfig::PrivateAlloc(unsigned __int64)

- ea: `0x180032d54`
- end: `0x180032d8c`
- name: `?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z`
- size: `56`
- prototype: `void *__fastcall(CPrintCoreConfig *__hidden this, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c5b0`
- `0x18002c6f0`
- `0x18002c7d0`
- `0x18002c8d0`
- `0x18002cca0`
- `0x18003100c`
- `0x180031170`
- `0x1800313d4`
- `0x1800316c0`
- `0x180031800`
- `0x1800326f8`

## callees

- `0x180032d54`
- `0x18005d010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180032d85`

## pseudocode

```c
void *__fastcall CPrintCoreConfig::PrivateAlloc(CPrintCoreConfig *this, SIZE_T a2)
{
  void *result; // rax

  result = (void *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 1) + 56LL))(*(_QWORD *)this);
  if ( result )
    return HeapAlloc(result, 0, a2);
  return result;
}

```

## disassembly

```asm
0x180032d54  push    rbx
0x180032d56  sub     rsp, 20h
0x180032d5a  mov     rax, [rcx+8]
0x180032d5e  mov     rbx, rdx
0x180032d61  mov     rcx, [rcx]
0x180032d64  mov     rax, [rax+38h]
0x180032d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d6d  test    rax, rax
0x180032d70  jnz     short loc_180032D78
0x180032d72  add     rsp, 20h
0x180032d76  pop     rbx
0x180032d77  retn
0x180032d78  mov     r8, rbx
0x180032d7b  xor     edx, edx
0x180032d7d  mov     rcx, rax
0x180032d80  add     rsp, 20h
0x180032d84  pop     rbx
0x180032d85  jmp     cs:__imp_HeapAlloc
```
