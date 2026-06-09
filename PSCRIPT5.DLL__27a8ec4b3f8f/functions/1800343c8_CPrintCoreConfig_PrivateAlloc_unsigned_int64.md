# CPrintCoreConfig::PrivateAlloc(unsigned __int64)

- ea: `0x1800343c8`
- end: `0x180034406`
- name: `?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z`
- size: `62`
- prototype: `void *__fastcall(CPrintCoreConfig *this, SIZE_T)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d9d0`
- `0x18002db10`
- `0x18002dbf0`
- `0x18002dcf0`
- `0x18002e0c0`
- `0x180032650`
- `0x1800327c4`
- `0x180032a24`
- `0x180032d10`
- `0x180032e50`
- `0x180033d58`

## callees

- `0x1800343c8`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800343fa`

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
0x1800343c8  push    rbx
0x1800343ca  sub     rsp, 20h
0x1800343ce  mov     rax, [rcx+8]
0x1800343d2  mov     rbx, rdx
0x1800343d5  mov     rcx, [rcx]
0x1800343d8  mov     rax, [rax+38h]
0x1800343dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343e1  test    rax, rax
0x1800343e4  jnz     short loc_1800343ED
0x1800343e6  add     rsp, 20h
0x1800343ea  pop     rbx
0x1800343eb  retn
0x1800343ed  mov     r8, rbx
0x1800343f0  xor     edx, edx
0x1800343f2  mov     rcx, rax
0x1800343f5  add     rsp, 20h
0x1800343f9  pop     rbx
0x1800343fa  jmp     cs:__imp_HeapAlloc
```
