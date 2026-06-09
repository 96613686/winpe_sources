# CPrintCoreConfig::PrivateAlloc(unsigned __int64)

- ea: `0x18002cf24`
- end: `0x18002cf62`
- name: `?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z`
- size: `62`
- prototype: `void *__fastcall(CPrintCoreConfig *this, SIZE_T)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c1f0`
- `0x18002ca40`
- `0x1800504b0`
- `0x180050688`
- `0x1800508d4`
- `0x1800511a8`
- `0x180075ae8`

## callees

- `0x18002cf24`
- `0x180077010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002cf56`

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
0x18002cf24  push    rbx
0x18002cf26  sub     rsp, 20h
0x18002cf2a  mov     rax, [rcx+8]
0x18002cf2e  mov     rbx, rdx
0x18002cf31  mov     rcx, [rcx]
0x18002cf34  mov     rax, [rax+38h]
0x18002cf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf3d  test    rax, rax
0x18002cf40  jnz     short loc_18002CF49
0x18002cf42  add     rsp, 20h
0x18002cf46  pop     rbx
0x18002cf47  retn
0x18002cf49  mov     r8, rbx
0x18002cf4c  xor     edx, edx
0x18002cf4e  mov     rcx, rax
0x18002cf51  add     rsp, 20h
0x18002cf55  pop     rbx
0x18002cf56  jmp     cs:__imp_HeapAlloc
```
