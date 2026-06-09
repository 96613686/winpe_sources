# Apx::ApfIpcIoLink::`vector deleting destructor'(uint)

- ea: `0x180027660`
- end: `0x180027694`
- name: `??_EApfIpcIoLink@Apx@@EEAAPEAXI@Z`
- size: `52`
- prototype: `Apx::ApfIpcIoLink *__fastcall(Apx::ApfIpcIoLink *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x180027520`
- `0x180027660`

## pseudocode

```c
Apx::ApfIpcIoLink *__fastcall Apx::ApfIpcIoLink::`vector deleting destructor'(Apx::ApfIpcIoLink *this, char a2)
{
  Apx::ApfIpcIoLink::~ApfIpcIoLink(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x1B8);
  return this;
}

```

## disassembly

```asm
0x180027660  mov     [rsp+arg_0], rbx
0x180027665  push    rdi
0x180027666  sub     rsp, 20h
0x18002766a  mov     ebx, edx
0x18002766c  mov     rdi, rcx
0x18002766f  call    ??1ApfIpcIoLink@Apx@@EEAA@XZ; Apx::ApfIpcIoLink::~ApfIpcIoLink(void)
0x180027674  test    bl, 1
0x180027677  jz      short loc_180027686
0x180027679  mov     edx, 1B8h; struct std::nothrow_t *
0x18002767e  mov     rcx, rdi; void *
0x180027681  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027686  mov     rbx, [rsp+28h+arg_0]
0x18002768b  mov     rax, rdi
0x18002768e  add     rsp, 20h
0x180027692  pop     rdi
0x180027693  retn
```
