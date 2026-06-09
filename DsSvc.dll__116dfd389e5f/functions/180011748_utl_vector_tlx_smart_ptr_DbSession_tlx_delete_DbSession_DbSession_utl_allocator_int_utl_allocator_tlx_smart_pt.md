# utl::vector<tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>>>::_Uninit(void)

- ea: `0x180011748`
- end: `0x180011783`
- name: `?_Uninit@?$vector@V?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@AEAAXXZ`
- size: `59`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010148`
- `0x180010190`
- `0x1800111c0`
- `0x180011620`

## callees

- `0x180002bac`
- `0x18000ffe0`
- `0x180011748`

## pseudocode

```c
void __fastcall utl::vector<tlx::smart_ptr<DbSession,&void tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<DbSession,&void tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>>>::_Uninit(
        __int64 a1)
{
  void *v1; // rdx
  __int64 v3; // r8

  v1 = *(void **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    utl::_RangeDestroyApc<utl::allocator<tlx::smart_ptr<DbSession,&void tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>>>(
      a1,
      v1,
      v3 >> 4);
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x180011748  push    rbx
0x18001174a  sub     rsp, 20h
0x18001174e  mov     rdx, [rcx]
0x180011751  mov     rbx, rcx
0x180011754  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180011758  jz      short loc_18001177D
0x18001175a  mov     r8, [rcx+8]
0x18001175e  sub     r8, rdx
0x180011761  mov     [rcx+8], rdx
0x180011765  sar     r8, 4
0x180011769  call    ??$_RangeDestroyApc@V?$allocator@V?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@YAXAEAV?$allocator@V?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@0@PEAV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@_K@Z; utl::_RangeDestroyApc<utl::allocator<tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>>>(utl::allocator<tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>>> &,tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> *,unsigned __int64)
0x18001176e  mov     rcx, [rbx]; void *
0x180011771  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011778  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001177d  add     rsp, 20h
0x180011781  pop     rbx
0x180011782  retn
```
