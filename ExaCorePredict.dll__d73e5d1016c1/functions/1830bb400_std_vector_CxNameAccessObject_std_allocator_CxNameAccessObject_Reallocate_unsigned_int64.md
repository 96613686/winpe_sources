# std::vector<CxNameAccessObject *,std::allocator<CxNameAccessObject *>>::_Reallocate(unsigned __int64)

- ea: `0x1830bb400`
- end: `0x1830bb48f`
- name: `?_Reallocate@?$vector@PEAVCxNameAccessObject@@V?$allocator@PEAVCxNameAccessObject@@@std@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1830bbaa0`
- `0x1830bd1e0`
- `0x1830bd2e0`

## callees

- `0x1815bbf10`
- `0x1830bb400`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830bb441`
- `VCRUNTIME140!memmove` at `0x1830bb441`

## pseudocode

```c
char *__fastcall std::vector<CxNameAccessObject *>::_Reallocate(CxVector *a1, __int64 a2)
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
0x1830bb400  push    rsi
0x1830bb402  push    rdi
0x1830bb403  push    r14
0x1830bb405  sub     rsp, 40h
0x1830bb409  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1830bb412  mov     [rsp+58h+arg_10], rbx
0x1830bb417  mov     r14, rdx
0x1830bb41a  mov     rbx, rcx
0x1830bb41d  mov     [rsp+58h+var_38], rcx
0x1830bb422  mov     [rsp+58h+var_30], rdx
0x1830bb427  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1830bb42c  mov     rsi, rax
0x1830bb42f  mov     [rsp+58h+var_28], rax
0x1830bb434  mov     r8, [rbx+8]
0x1830bb438  mov     rdx, [rbx]; Src
0x1830bb43b  sub     r8, rdx; Size
0x1830bb43e  mov     rcx, rax; void *
0x1830bb441  call    cs:__imp_memmove
0x1830bb447  nop
0x1830bb448  mov     rdx, [rbx]
0x1830bb44b  mov     rdi, [rbx+8]
0x1830bb44f  sub     rdi, rdx
0x1830bb452  sar     rdi, 3
0x1830bb456  test    rdx, rdx
0x1830bb459  jz      short loc_1830BB46E
0x1830bb45b  mov     r8, [rbx+10h]
0x1830bb45f  sub     r8, rdx
0x1830bb462  sar     r8, 3
0x1830bb466  mov     rcx, rbx
0x1830bb469  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1830bb46e  lea     rax, [rsi+r14*8]
0x1830bb472  mov     [rbx+10h], rax
0x1830bb476  lea     rax, [rsi+rdi*8]
0x1830bb47a  mov     [rbx+8], rax
0x1830bb47e  mov     [rbx], rsi
0x1830bb481  mov     rbx, [rsp+58h+arg_10]
0x1830bb486  add     rsp, 40h
0x1830bb48a  pop     r14
0x1830bb48c  pop     rdi
0x1830bb48d  pop     rsi
0x1830bb48e  retn
```
