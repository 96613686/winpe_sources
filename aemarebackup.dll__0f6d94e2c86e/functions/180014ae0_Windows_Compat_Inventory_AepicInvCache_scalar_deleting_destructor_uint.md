# Windows::Compat::Inventory::AepicInvCache::`scalar deleting destructor'(uint)

- ea: `0x180014ae0`
- end: `0x180014b52`
- name: `??_GAepicInvCache@Inventory@Compat@Windows@@UEAAPEAXI@Z`
- size: `114`
- prototype: `Windows::Compat::Inventory::AepicInvCache *__fastcall(Windows::Compat::Inventory::AepicInvCache *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000529c`
- `0x180014ae0`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b02`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b19`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b02`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180014b19`

## pseudocode

```c
Windows::Compat::Inventory::AepicInvCache *__fastcall Windows::Compat::Inventory::AepicInvCache::`scalar deleting destructor'(
        Windows::Compat::Inventory::AepicInvCache *this,
        char a2)
{
  *(_QWORD *)this = &Windows::Compat::Inventory::AepicInvCache::`vftable';
  if ( *((_QWORD *)this + 1) )
  {
    InvCacheCloseHandle();
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_QWORD *)this + 2) )
  {
    InvCacheCloseHandle();
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &Windows::Compat::Inventory::InventoryCache::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180014ae0  mov     [rsp+arg_0], rbx
0x180014ae5  push    rdi
0x180014ae6  sub     rsp, 20h
0x180014aea  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x180014af1  mov     rbx, rcx
0x180014af4  mov     [rcx], rax
0x180014af7  mov     edi, edx
0x180014af9  mov     rcx, [rcx+8]
0x180014afd  test    rcx, rcx
0x180014b00  jz      short loc_180014B10
0x180014b02  call    cs:__imp_InvCacheCloseHandle
0x180014b08  mov     qword ptr [rbx+8], 0
0x180014b10  mov     rcx, [rbx+10h]
0x180014b14  test    rcx, rcx
0x180014b17  jz      short loc_180014B27
0x180014b19  call    cs:__imp_InvCacheCloseHandle
0x180014b1f  mov     qword ptr [rbx+10h], 0
0x180014b27  lea     rax, ??_7InventoryCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InventoryCache::`vftable'
0x180014b2e  mov     [rbx], rax
0x180014b31  test    dil, 1
0x180014b35  jz      short loc_180014B44
0x180014b37  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180014b3c  mov     rcx, rbx; void *
0x180014b3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014b44  mov     rax, rbx
0x180014b47  mov     rbx, [rsp+28h+arg_0]
0x180014b4c  add     rsp, 20h
0x180014b50  pop     rdi
0x180014b51  retn
```
