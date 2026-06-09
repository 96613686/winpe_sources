# Apx::ApfIpcIoLinkMgr::`vector deleting destructor'(uint)

- ea: `0x180025a70`
- end: `0x180025aa4`
- name: `??_EApfIpcIoLinkMgr@Apx@@EEAAPEAXI@Z`
- size: `52`
- prototype: `Apx::ApfIpcIoLinkMgr *__fastcall(Apx::ApfIpcIoLinkMgr *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x1800259d8`
- `0x180025a70`

## pseudocode

```c
Apx::ApfIpcIoLinkMgr *__fastcall Apx::ApfIpcIoLinkMgr::`vector deleting destructor'(
        Apx::ApfIpcIoLinkMgr *this,
        char a2)
{
  Apx::ApfIpcIoLinkMgr::~ApfIpcIoLinkMgr(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x280);
  return this;
}

```

## disassembly

```asm
0x180025a70  mov     [rsp+arg_0], rbx
0x180025a75  push    rdi
0x180025a76  sub     rsp, 20h
0x180025a7a  mov     ebx, edx
0x180025a7c  mov     rdi, rcx
0x180025a7f  call    ??1ApfIpcIoLinkMgr@Apx@@EEAA@XZ; Apx::ApfIpcIoLinkMgr::~ApfIpcIoLinkMgr(void)
0x180025a84  test    bl, 1
0x180025a87  jz      short loc_180025A96
0x180025a89  mov     edx, 280h; struct std::nothrow_t *
0x180025a8e  mov     rcx, rdi; void *
0x180025a91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025a96  mov     rbx, [rsp+28h+arg_0]
0x180025a9b  mov     rax, rdi
0x180025a9e  add     rsp, 20h
0x180025aa2  pop     rdi
0x180025aa3  retn
```
