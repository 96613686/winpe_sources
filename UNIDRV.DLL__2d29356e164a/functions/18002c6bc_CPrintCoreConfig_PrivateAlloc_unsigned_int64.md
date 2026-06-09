# CPrintCoreConfig::PrivateAlloc(unsigned __int64)

- ea: `0x18002c6bc`
- end: `0x18002c6f4`
- name: `?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z`
- size: `56`
- prototype: `void *__fastcall(CPrintCoreConfig *__hidden this, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002b9c0`
- `0x18002c1f0`
- `0x18004ed70`
- `0x18004ef38`
- `0x18004f184`
- `0x18004fa54`
- `0x180073a18`

## callees

- `0x18002c6bc`
- `0x180075010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002c6ed`

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
0x18002c6bc  push    rbx
0x18002c6be  sub     rsp, 20h
0x18002c6c2  mov     rax, [rcx+8]
0x18002c6c6  mov     rbx, rdx
0x18002c6c9  mov     rcx, [rcx]
0x18002c6cc  mov     rax, [rax+38h]
0x18002c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6d5  test    rax, rax
0x18002c6d8  jnz     short loc_18002C6E0
0x18002c6da  add     rsp, 20h
0x18002c6de  pop     rbx
0x18002c6df  retn
0x18002c6e0  mov     r8, rbx
0x18002c6e3  xor     edx, edx
0x18002c6e5  mov     rcx, rax
0x18002c6e8  add     rsp, 20h
0x18002c6ec  pop     rbx
0x18002c6ed  jmp     cs:__imp_HeapAlloc
```
