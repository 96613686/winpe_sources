# std::vector<_ChunkDescriptorType,std::allocator<_ChunkDescriptorType>>::resize(unsigned __int64)

- ea: `0x18000f710`
- end: `0x18000f825`
- name: `?resize@?$vector@U_ChunkDescriptorType@@V?$allocator@U_ChunkDescriptorType@@@std@@@std@@QEAAX_K@Z`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f1d8`

## callees

- `0x18000cd9c`
- `0x18000eddc`
- `0x18000f598`
- `0x18000f710`

## pseudocode

```c
__int64 __fastcall std::vector<_ChunkDescriptorType>::resize(__int64 a1, unsigned __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rdx
  __int64 result; // rax

  v4 = *(_QWORD *)a1;
  v5 = 0x1A8C536FE1A8C537LL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 2);
  if ( a2 >= v5 )
  {
    if ( a2 > v5 )
    {
      if ( 0x1A8C536FE1A8C537LL * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 2) < a2 - v5 )
      {
        if ( 0x795CEB240795CELL - v5 < a2 - v5 )
          std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
        v7 = 0x1A8C536FE1A8C537LL * ((*(_QWORD *)(a1 + 16) - v4) >> 2);
        v8 = 0;
        if ( 0x795CEB240795CELL - (v7 >> 1) >= v7 )
          v8 = v7 + (v7 >> 1);
        if ( v8 < a2 )
          v8 = a2;
        std::vector<_ChunkDescriptorType>::_Reallocate(a1, v8);
      }
      try
      {
        std::_Uninit_def_fill_n<_ChunkDescriptorType *,unsigned __int64,std::allocator<_ChunkDescriptorType>,_ChunkDescriptorType>(
          *(char **)(a1 + 8),
          a2 - 0x1A8C536FE1A8C537LL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 2));
        result = 540 * (a2 - 0x1A8C536FE1A8C537LL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 2));
        *(_QWORD *)(a1 + 8) += result;
      }
      catch ( ... )
      {
        __1__vector_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBW4FilterType__V__unique_ptr_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std__U__default_delete_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std___2__std___std___std___std___std__U___Wrap_alloc_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBW4FilterType__V__unique_ptr_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std__U__default_delete_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std___2__std___std___std___std___std___std___2__std__QEAA_XZ(a1);
        throw;
      }
    }
  }
  else
  {
    v6 = v4 + 540 * a2;
    if ( v6 == v4 )
    {
      *(_QWORD *)(a1 + 8) = v4;
    }
    else if ( v6 != *(_QWORD *)(a1 + 8) )
    {
      *(_QWORD *)(a1 + 8) = v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f710  mov     [rsp+arg_8], rbx
0x18000f715  mov     [rsp+arg_10], rsi
0x18000f71a  mov     [rsp+arg_0], rcx
0x18000f71f  push    rdi
0x18000f720  sub     rsp, 30h
0x18000f724  mov     rdi, rdx
0x18000f727  mov     rbx, rcx
0x18000f72a  mov     rdx, [rcx]
0x18000f72d  mov     rcx, [rcx+8]
0x18000f731  sub     rcx, rdx
0x18000f734  sar     rcx, 2
0x18000f738  mov     rsi, 1A8C536FE1A8C537h
0x18000f742  imul    rcx, rsi
0x18000f746  cmp     rdi, rcx
0x18000f749  jnb     short loc_18000F77A
0x18000f74b  imul    rcx, rdi, 21Ch
0x18000f752  add     rcx, rdx
0x18000f755  cmp     rcx, rdx
0x18000f758  jnz     short loc_18000F76E
0x18000f75a  mov     [rbx+8], rdx
0x18000f75e  mov     rbx, [rsp+38h+arg_8]
0x18000f763  mov     rsi, [rsp+38h+arg_10]
0x18000f768  add     rsp, 30h
0x18000f76c  pop     rdi
0x18000f76d  retn
0x18000f76e  cmp     rcx, [rbx+8]
0x18000f772  jz      short loc_18000F75E
0x18000f774  mov     [rbx+8], rcx
0x18000f778  jmp     short loc_18000F75E
0x18000f77a  jbe     short loc_18000F75E
0x18000f77c  mov     r8, rdi
0x18000f77f  sub     r8, rcx
0x18000f782  mov     r9, [rbx+10h]
0x18000f786  mov     rax, r9
0x18000f789  sub     rax, [rbx+8]
0x18000f78d  sar     rax, 2
0x18000f791  imul    rax, rsi
0x18000f795  cmp     rax, r8
0x18000f798  jnb     short loc_18000F7DF
0x18000f79a  mov     r10, 795CEB240795CEh
0x18000f7a4  mov     rax, r10
0x18000f7a7  sub     rax, rcx
0x18000f7aa  cmp     rax, r8
0x18000f7ad  jb      short loc_18000F81F
0x18000f7af  sub     r9, rdx
0x18000f7b2  sar     r9, 2
0x18000f7b6  imul    r9, rsi
0x18000f7ba  mov     rax, r9
0x18000f7bd  shr     rax, 1
0x18000f7c0  sub     r10, rax
0x18000f7c3  add     rax, r9
0x18000f7c6  xor     edx, edx
0x18000f7c8  cmp     r10, r9
0x18000f7cb  cmovnb  rdx, rax
0x18000f7cf  cmp     rdx, rdi
0x18000f7d2  cmovb   rdx, rdi
0x18000f7d6  mov     rcx, rbx
0x18000f7d9  call    ?_Reallocate@?$vector@U_ChunkDescriptorType@@V?$allocator@U_ChunkDescriptorType@@@std@@@std@@IEAAX_K@Z; std::vector<_ChunkDescriptorType>::_Reallocate(unsigned __int64)
0x18000f7de  nop
0x18000f7df  mov     rcx, [rbx+8]
0x18000f7e3  mov     rax, rcx
0x18000f7e6  sub     rax, [rbx]
0x18000f7e9  sar     rax, 2
0x18000f7ed  imul    rax, rsi
0x18000f7f1  mov     rdx, rdi
0x18000f7f4  sub     rdx, rax
0x18000f7f7  call    ??$_Uninit_def_fill_n@PEAU_ChunkDescriptorType@@_KV?$allocator@U_ChunkDescriptorType@@@std@@U1@@std@@YAXPEAU_ChunkDescriptorType@@_KAEAU?$_Wrap_alloc@V?$allocator@U_ChunkDescriptorType@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_def_fill_n<_ChunkDescriptorType *,unsigned __int64,std::allocator<_ChunkDescriptorType>,_ChunkDescriptorType>(_ChunkDescriptorType *,unsigned __int64,std::_Wrap_alloc<std::allocator<_ChunkDescriptorType>> &,_ChunkDescriptorType *,std::_Nonscalar_ptr_iterator_tag)
0x18000f7fc  nop
0x18000f7fd  mov     rax, [rbx+8]
0x18000f801  sub     rax, [rbx]
0x18000f804  sar     rax, 2
0x18000f808  imul    rax, rsi
0x18000f80c  sub     rdi, rax
0x18000f80f  imul    rax, rdi, 21Ch
0x18000f816  add     [rbx+8], rax
0x18000f81a  jmp     loc_18000F75E
0x18000f81f  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
