# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180016334`
- end: `0x1800163c4`
- name: `??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018550`

## callees

- `0x180001894`
- `0x180016334`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  _QWORD **v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD **)v1[1];
    *v2[1] = 0;
    v3 = *v2;
    if ( v3 )
    {
      do
      {
        v4 = (_QWORD *)*v3;
        operator delete(v3);
        v3 = v4;
      }
      while ( v4 );
    }
    *(_QWORD *)v1[1] = v1[1];
    *(_QWORD *)(v1[1] + 8) = v1[1];
    v1[2] = 0;
    v5 = (void *)v1[3];
    v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
    if ( (unsigned __int64)v5 > v1[4] )
      v6 = 0;
    if ( v6 )
      memset64(v5, v1[1], v6);
  }
}

```

## disassembly

```asm
0x180016334  mov     [rsp+arg_0], rbx
0x180016339  push    rdi
0x18001633a  sub     rsp, 20h
0x18001633e  mov     rbx, [rcx]
0x180016341  test    rbx, rbx
0x180016344  jz      short loc_1800163B9
0x180016346  cmp     qword ptr [rbx+10h], 0
0x18001634b  jz      short loc_1800163B9
0x18001634d  mov     rcx, [rbx+8]
0x180016351  mov     rax, [rcx+8]
0x180016355  mov     qword ptr [rax], 0
0x18001635c  mov     rcx, [rcx]; Block
0x18001635f  test    rcx, rcx
0x180016362  jz      short loc_180016379
0x180016364  mov     rdi, [rcx]
0x180016367  mov     edx, 18h
0x18001636c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016371  mov     rcx, rdi
0x180016374  test    rdi, rdi
0x180016377  jnz     short loc_180016364
0x180016379  mov     rax, [rbx+8]
0x18001637d  xor     edx, edx
0x18001637f  mov     [rax], rax
0x180016382  mov     rax, [rbx+8]
0x180016386  mov     [rax+8], rax
0x18001638a  mov     qword ptr [rbx+10h], 0
0x180016392  mov     rdi, [rbx+18h]
0x180016396  mov     rcx, [rbx+20h]
0x18001639a  sub     rcx, rdi
0x18001639d  add     rcx, 7
0x1800163a1  shr     rcx, 3
0x1800163a5  cmp     rdi, [rbx+20h]
0x1800163a9  cmova   rcx, rdx
0x1800163ad  test    rcx, rcx
0x1800163b0  jz      short loc_1800163B9
0x1800163b2  mov     rax, [rbx+8]
0x1800163b6  rep stosq
0x1800163b9  mov     rbx, [rsp+28h+arg_0]
0x1800163be  add     rsp, 20h
0x1800163c2  pop     rdi
0x1800163c3  retn
```
