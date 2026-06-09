# utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(void)

- ea: `0x140014490`
- end: `0x1400144e5`
- name: `?_Uninit@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@AEAAXXZ`
- size: `85`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140012c58`
- `0x140014360`

## callees

- `0x1400025a4`
- `0x140012420`
- `0x140014490`

## pseudocode

```c
void __fastcall utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // r8

  v2 = *(void **)a1;
  if ( v2 != (void *)-1LL )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v2;
    *(_QWORD *)(a1 + 8) = v2;
    utl::_RangeDestroyApc<utl::allocator<DeleteContext>>((__int64)v2, (__int64)v2, v3 / 24);
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x140014490  push    rbx
0x140014492  sub     rsp, 20h
0x140014496  mov     rbx, rcx
0x140014499  mov     rcx, [rcx]
0x14001449c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400144a0  jz      short loc_1400144DF
0x1400144a2  mov     r8, [rbx+8]
0x1400144a6  mov     rax, 2AAAAAAAAAAAAAABh
0x1400144b0  sub     r8, rcx
0x1400144b3  mov     [rbx+8], rcx
0x1400144b7  imul    r8
0x1400144ba  sar     rdx, 2
0x1400144be  mov     r8, rdx
0x1400144c1  shr     r8, 3Fh
0x1400144c5  add     r8, rdx
0x1400144c8  mov     rdx, rcx
0x1400144cb  call    ??$_RangeDestroyApc@V?$allocator@UDeleteContext@@@utl@@@utl@@YAXAEAV?$allocator@UDeleteContext@@@0@PEAUDeleteContext@@_K@Z; utl::_RangeDestroyApc<utl::allocator<DeleteContext>>(utl::allocator<DeleteContext> &,DeleteContext *,unsigned __int64)
0x1400144d0  mov     rcx, [rbx]; void *
0x1400144d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400144da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400144df  add     rsp, 20h
0x1400144e3  pop     rbx
0x1400144e4  retn
```
