# std::vector<_ChunkDescriptorType,std::allocator<_ChunkDescriptorType>>::_Reallocate(unsigned __int64)

- ea: `0x18000f598`
- end: `0x18000f645`
- name: `?_Reallocate@?$vector@U_ChunkDescriptorType@@V?$allocator@U_ChunkDescriptorType@@@std@@@std@@IEAAX_K@Z`
- size: `173`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f710`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18000ee20`
- `0x18000f598`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f616`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f616`

## pseudocode

```c
char *__fastcall std::vector<_ChunkDescriptorType>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // r14
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  void *v6; // rcx
  __int64 v7; // rsi
  char *result; // rax
  _OWORD *v9; // [rsp+68h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0x795CEB240795CELL || (v3 = 540 * a2, v4 = operator new(540 * a2), v5 = v4, (v9 = v4) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v5 = 0;
    v9 = 0;
    v3 = 0;
  }
  try
  {
    std::_Uninit_move<_ChunkDescriptorType *,_ChunkDescriptorType *,std::allocator<_ChunkDescriptorType>,_ChunkDescriptorType>(
      *(_OWORD **)a1,
      *(_OWORD **)(a1 + 8),
      v5);
    v6 = *(void **)a1;
    v7 = 0x1A8C536FE1A8C537LL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 2);
    if ( *(_QWORD *)a1 )
      operator delete(v6);
    *(_QWORD *)(a1 + 16) = (char *)v5 + v3;
    result = (char *)v5 + 540 * v7;
    *(_QWORD *)(a1 + 8) = result;
    *(_QWORD *)a1 = v5;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v6, v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000f598  push    rbx
0x18000f59a  push    rsi
0x18000f59b  push    rdi
0x18000f59c  push    r14
0x18000f59e  sub     rsp, 38h
0x18000f5a2  mov     rdi, rcx
0x18000f5a5  test    rdx, rdx
0x18000f5a8  jz      short loc_18000F5DB
0x18000f5aa  mov     rax, 795CEB240795CEh
0x18000f5b4  cmp     rdx, rax
0x18000f5b7  ja      loc_18000F63F
0x18000f5bd  imul    r14, rdx, 21Ch
0x18000f5c4  mov     rcx, r14; Size
0x18000f5c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f5cc  mov     rbx, rax
0x18000f5cf  mov     [rsp+58h+arg_8], rax
0x18000f5d4  test    rax, rax
0x18000f5d7  jz      short loc_18000F63F
0x18000f5d9  jmp     short loc_18000F5E5
0x18000f5db  xor     ebx, ebx
0x18000f5dd  mov     [rsp+58h+arg_8], rbx
0x18000f5e2  xor     r14d, r14d
0x18000f5e5  mov     r8, rbx
0x18000f5e8  mov     rdx, [rdi+8]
0x18000f5ec  mov     rcx, [rdi]
0x18000f5ef  call    ??$_Uninit_move@PEAU_ChunkDescriptorType@@PEAU1@V?$allocator@U_ChunkDescriptorType@@@std@@U1@@std@@YAPEAU_ChunkDescriptorType@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@U_ChunkDescriptorType@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<_ChunkDescriptorType *,_ChunkDescriptorType *,std::allocator<_ChunkDescriptorType>,_ChunkDescriptorType>(_ChunkDescriptorType *,_ChunkDescriptorType *,_ChunkDescriptorType *,std::_Wrap_alloc<std::allocator<_ChunkDescriptorType>> &,_ChunkDescriptorType *,std::_Nonscalar_ptr_iterator_tag)
0x18000f5f4  nop
0x18000f5f5  mov     rcx, [rdi]
0x18000f5f8  mov     rsi, [rdi+8]
0x18000f5fc  sub     rsi, rcx
0x18000f5ff  sar     rsi, 2
0x18000f603  mov     rax, 1A8C536FE1A8C537h
0x18000f60d  imul    rsi, rax
0x18000f611  test    rcx, rcx
0x18000f614  jz      short loc_18000F61C
0x18000f616  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f61c  lea     rax, [r14+rbx]
0x18000f620  mov     [rdi+10h], rax
0x18000f624  imul    rax, rsi, 21Ch
0x18000f62b  add     rax, rbx
0x18000f62e  mov     [rdi+8], rax
0x18000f632  mov     [rdi], rbx
0x18000f635  add     rsp, 38h
0x18000f639  pop     r14
0x18000f63b  pop     rdi
0x18000f63c  pop     rsi
0x18000f63d  pop     rbx
0x18000f63e  retn
0x18000f63f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
