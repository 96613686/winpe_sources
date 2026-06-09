# Windows::Compat::Inventory::AepicInvCacheItem::`vector deleting destructor'(uint)

- ea: `0x180014b60`
- end: `0x180014bb3`
- name: `??_EAepicInvCacheItem@Inventory@Compat@Windows@@UEAAPEAXI@Z`
- size: `83`
- prototype: `Windows::Compat::Inventory::AepicInvCacheItem *__fastcall(Windows::Compat::Inventory::AepicInvCacheItem *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000529c`
- `0x180014b60`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b82`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b82`

## pseudocode

```c
Windows::Compat::Inventory::AepicInvCacheItem *__fastcall Windows::Compat::Inventory::AepicInvCacheItem::`vector deleting destructor'(
        Windows::Compat::Inventory::AepicInvCacheItem *this,
        char a2)
{
  *(_QWORD *)this = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
  if ( *((_QWORD *)this + 1) )
    InvCacheCloseHandle();
  *(_QWORD *)this = &Windows::Compat::Inventory::InventoryCacheItem::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x10);
  return this;
}

```

## disassembly

```asm
0x180014b60  mov     [rsp+arg_0], rbx
0x180014b65  push    rdi
0x180014b66  sub     rsp, 20h
0x180014b6a  lea     rax, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180014b71  mov     rbx, rcx
0x180014b74  mov     [rcx], rax
0x180014b77  mov     edi, edx
0x180014b79  mov     rcx, [rcx+8]
0x180014b7d  test    rcx, rcx
0x180014b80  jz      short loc_180014B88
0x180014b82  call    cs:__imp_InvCacheCloseHandle
0x180014b88  lea     rax, ??_7InventoryCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InventoryCacheItem::`vftable'
0x180014b8f  mov     [rbx], rax
0x180014b92  test    dil, 1
0x180014b96  jz      short loc_180014BA5
0x180014b98  mov     edx, 10h; struct std::nothrow_t *
0x180014b9d  mov     rcx, rbx; void *
0x180014ba0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014ba5  mov     rax, rbx
0x180014ba8  mov     rbx, [rsp+28h+arg_0]
0x180014bad  add     rsp, 20h
0x180014bb1  pop     rdi
0x180014bb2  retn
```
