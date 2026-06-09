# stdext::hash_set<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>>::~hash_set<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>>(void)

- ea: `0x180016044`
- end: `0x1800160b5`
- name: `??1?$hash_set@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@@stdext@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028bbf`

## callees

- `0x180016044`
- `0x1800268f4`

## pseudocode

```c
void __fastcall stdext::hash_set<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>>::~hash_set<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>>(
        __int64 a1)
{
  void *v2; // rcx
  _QWORD **v3; // rax
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = *(void **)(a1 + 40);
  if ( v2 )
    operator delete(v2);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v3 = *(_QWORD ***)(a1 + 16);
  v4 = *v3;
  *v3 = v3;
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v4 != *(_QWORD **)(a1 + 16) )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      operator delete(v4);
      v4 = v5;
    }
    while ( v5 != *(_QWORD **)(a1 + 16) );
  }
  operator delete(*(void **)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180016044  mov     [rsp+arg_0], rbx
0x180016049  push    rdi
0x18001604a  sub     rsp, 20h
0x18001604e  mov     rdi, rcx
0x180016051  mov     rcx, [rcx+28h]; Block
0x180016055  test    rcx, rcx
0x180016058  jz      short loc_18001605F
0x18001605a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001605f  and     qword ptr [rdi+28h], 0
0x180016064  and     qword ptr [rdi+30h], 0
0x180016069  and     qword ptr [rdi+38h], 0
0x18001606e  mov     rax, [rdi+10h]
0x180016072  mov     rcx, [rax]; Block
0x180016075  mov     [rax], rax
0x180016078  mov     rax, [rdi+10h]
0x18001607c  mov     [rax+8], rax
0x180016080  and     qword ptr [rdi+18h], 0
0x180016085  cmp     rcx, [rdi+10h]
0x180016089  jz      short loc_18001609C
0x18001608b  mov     rbx, [rcx]
0x18001608e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016093  mov     rcx, rbx
0x180016096  cmp     rbx, [rdi+10h]
0x18001609a  jnz     short loc_18001608B
0x18001609c  mov     rcx, [rdi+10h]; Block
0x1800160a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800160a5  and     qword ptr [rdi+10h], 0
0x1800160aa  mov     rbx, [rsp+28h+arg_0]
0x1800160af  add     rsp, 20h
0x1800160b3  pop     rdi
0x1800160b4  retn
```
