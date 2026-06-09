# std::vector<char *,std::allocator<char *>>::_Reallocate(unsigned __int64)

- ea: `0x1830bb370`
- end: `0x1830bb3ff`
- name: `?_Reallocate@?$vector@PEADV?$allocator@PEAD@std@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1830bcf50`
- `0x1830bd050`

## callees

- `0x1815bbf10`
- `0x1830bb370`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830bb3b1`
- `VCRUNTIME140!memmove` at `0x1830bb3b1`

## pseudocode

```c
char *__fastcall std::vector<char *>::_Reallocate(CxVector *a1, __int64 a2)
{
  char *v4; // rax
  char *v5; // rsi
  __int64 v6; // rdi
  char *result; // rax
  struct CxVector *Pointer; // rax
  char *v11; // [rsp+30h] [rbp-28h]

  v4 = (char *)std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(
                 a1,
                 a2);
  v5 = v4;
  v11 = v4;
  try
  {
    memmove(v4, *(const void **)a1, *((_QWORD *)a1 + 1) - *(_QWORD *)a1);
  }
  catch ( ... )
  {
    Pointer = CxVector::GetPointer(a1);
    std::_Wrap_alloc<std::allocator<CxWrapper<CxVarDescriptor>>>::deallocate(Pointer, v11, a2);
    throw;
  }
  v6 = (__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
    std::allocator<CxWrapper<CxComputation>>::deallocate(
      a1,
      *(_QWORD *)a1,
      (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 3);
  *((_QWORD *)a1 + 2) = &v5[8 * a2];
  result = &v5[8 * v6];
  *((_QWORD *)a1 + 1) = result;
  *(_QWORD *)a1 = v5;
  return result;
}

```

## disassembly

```asm
0x1830bb370  push    rsi
0x1830bb372  push    rdi
0x1830bb373  push    r14
0x1830bb375  sub     rsp, 40h
0x1830bb379  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1830bb382  mov     [rsp+58h+arg_10], rbx
0x1830bb387  mov     r14, rdx
0x1830bb38a  mov     rbx, rcx
0x1830bb38d  mov     [rsp+58h+var_38], rcx
0x1830bb392  mov     [rsp+58h+var_30], rdx
0x1830bb397  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1830bb39c  mov     rsi, rax
0x1830bb39f  mov     [rsp+58h+var_28], rax
0x1830bb3a4  mov     r8, [rbx+8]
0x1830bb3a8  mov     rdx, [rbx]; Src
0x1830bb3ab  sub     r8, rdx; Size
0x1830bb3ae  mov     rcx, rax; void *
0x1830bb3b1  call    cs:__imp_memmove
0x1830bb3b7  nop
0x1830bb3b8  mov     rdx, [rbx]
0x1830bb3bb  mov     rdi, [rbx+8]
0x1830bb3bf  sub     rdi, rdx
0x1830bb3c2  sar     rdi, 3
0x1830bb3c6  test    rdx, rdx
0x1830bb3c9  jz      short loc_1830BB3DE
0x1830bb3cb  mov     r8, [rbx+10h]
0x1830bb3cf  sub     r8, rdx
0x1830bb3d2  sar     r8, 3
0x1830bb3d6  mov     rcx, rbx
0x1830bb3d9  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1830bb3de  lea     rax, [rsi+r14*8]
0x1830bb3e2  mov     [rbx+10h], rax
0x1830bb3e6  lea     rax, [rsi+rdi*8]
0x1830bb3ea  mov     [rbx+8], rax
0x1830bb3ee  mov     [rbx], rsi
0x1830bb3f1  mov     rbx, [rsp+58h+arg_10]
0x1830bb3f6  add     rsp, 40h
0x1830bb3fa  pop     r14
0x1830bb3fc  pop     rdi
0x1830bb3fd  pop     rsi
0x1830bb3fe  retn
```
