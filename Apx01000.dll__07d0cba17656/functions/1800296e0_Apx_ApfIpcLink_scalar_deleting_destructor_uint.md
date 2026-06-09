# Apx::ApfIpcLink::`scalar deleting destructor'(uint)

- ea: `0x1800296e0`
- end: `0x180029714`
- name: `??_GApfIpcLink@Apx@@MEAAPEAXI@Z`
- size: `52`
- prototype: `Apx::ApfIpcLink *__fastcall(Apx::ApfIpcLink *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x18002963c`
- `0x1800296e0`

## pseudocode

```c
Apx::ApfIpcLink *__fastcall Apx::ApfIpcLink::`scalar deleting destructor'(Apx::ApfIpcLink *this, char a2)
{
  Apx::ApfIpcLink::~ApfIpcLink(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x68);
  return this;
}

```

## disassembly

```asm
0x1800296e0  mov     [rsp+arg_0], rbx
0x1800296e5  push    rdi
0x1800296e6  sub     rsp, 20h
0x1800296ea  mov     ebx, edx
0x1800296ec  mov     rdi, rcx
0x1800296ef  call    ??1ApfIpcLink@Apx@@MEAA@XZ; Apx::ApfIpcLink::~ApfIpcLink(void)
0x1800296f4  test    bl, 1
0x1800296f7  jz      short loc_180029706
0x1800296f9  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x1800296fe  mov     rcx, rdi; void *
0x180029701  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029706  mov     rbx, [rsp+28h+arg_0]
0x18002970b  mov     rax, rdi
0x18002970e  add     rsp, 20h
0x180029712  pop     rdi
0x180029713  retn
```
