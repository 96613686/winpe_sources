# Apx::ApfIpcLinkMgr::`vector deleting destructor'(uint)

- ea: `0x1800272f0`
- end: `0x180027324`
- name: `??_EApfIpcLinkMgr@Apx@@MEAAPEAXI@Z`
- size: `52`
- prototype: `Apx::ApfIpcLinkMgr *__fastcall(Apx::ApfIpcLinkMgr *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x180027250`
- `0x1800272f0`

## pseudocode

```c
Apx::ApfIpcLinkMgr *__fastcall Apx::ApfIpcLinkMgr::`vector deleting destructor'(Apx::ApfIpcLinkMgr *this, char a2)
{
  Apx::ApfIpcLinkMgr::~ApfIpcLinkMgr(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x48);
  return this;
}

```

## disassembly

```asm
0x1800272f0  mov     [rsp+arg_0], rbx
0x1800272f5  push    rdi
0x1800272f6  sub     rsp, 20h
0x1800272fa  mov     ebx, edx
0x1800272fc  mov     rdi, rcx
0x1800272ff  call    ??1ApfIpcLinkMgr@Apx@@MEAA@XZ; Apx::ApfIpcLinkMgr::~ApfIpcLinkMgr(void)
0x180027304  test    bl, 1
0x180027307  jz      short loc_180027316
0x180027309  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18002730e  mov     rcx, rdi; void *
0x180027311  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027316  mov     rbx, [rsp+28h+arg_0]
0x18002731b  mov     rax, rdi
0x18002731e  add     rsp, 20h
0x180027322  pop     rdi
0x180027323  retn
```
