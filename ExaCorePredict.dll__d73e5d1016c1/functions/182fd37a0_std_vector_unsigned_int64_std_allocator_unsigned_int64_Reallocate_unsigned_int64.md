# std::vector<unsigned __int64 *,std::allocator<unsigned __int64 *>>::_Reallocate(unsigned __int64)

- ea: `0x182fd37a0`
- end: `0x182fd382f`
- name: `?_Reallocate@?$vector@PEA_KV?$allocator@PEA_K@std@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x182fd3830`
- `0x1830bd470`
- `0x1830bd570`

## callees

- `0x1815bbf10`
- `0x182fd37a0`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182fd37e1`
- `VCRUNTIME140!memmove` at `0x182fd37e1`

## pseudocode

```c
char *__fastcall std::vector<unsigned __int64 *>::_Reallocate(CxVector *a1, __int64 a2)
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
0x182fd37a0  push    rsi
0x182fd37a2  push    rdi
0x182fd37a3  push    r14
0x182fd37a5  sub     rsp, 40h
0x182fd37a9  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x182fd37b2  mov     [rsp+58h+arg_10], rbx
0x182fd37b7  mov     r14, rdx
0x182fd37ba  mov     rbx, rcx
0x182fd37bd  mov     [rsp+58h+var_38], rcx
0x182fd37c2  mov     [rsp+58h+var_30], rdx
0x182fd37c7  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x182fd37cc  mov     rsi, rax
0x182fd37cf  mov     [rsp+58h+var_28], rax
0x182fd37d4  mov     r8, [rbx+8]
0x182fd37d8  mov     rdx, [rbx]; Src
0x182fd37db  sub     r8, rdx; Size
0x182fd37de  mov     rcx, rax; void *
0x182fd37e1  call    cs:__imp_memmove
0x182fd37e7  nop
0x182fd37e8  mov     rdx, [rbx]
0x182fd37eb  mov     rdi, [rbx+8]
0x182fd37ef  sub     rdi, rdx
0x182fd37f2  sar     rdi, 3
0x182fd37f6  test    rdx, rdx
0x182fd37f9  jz      short loc_182FD380E
0x182fd37fb  mov     r8, [rbx+10h]
0x182fd37ff  sub     r8, rdx
0x182fd3802  sar     r8, 3
0x182fd3806  mov     rcx, rbx
0x182fd3809  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x182fd380e  lea     rax, [rsi+r14*8]
0x182fd3812  mov     [rbx+10h], rax
0x182fd3816  lea     rax, [rsi+rdi*8]
0x182fd381a  mov     [rbx+8], rax
0x182fd381e  mov     [rbx], rsi
0x182fd3821  mov     rbx, [rsp+58h+arg_10]
0x182fd3826  add     rsp, 40h
0x182fd382a  pop     r14
0x182fd382c  pop     rdi
0x182fd382d  pop     rsi
0x182fd382e  retn
```
