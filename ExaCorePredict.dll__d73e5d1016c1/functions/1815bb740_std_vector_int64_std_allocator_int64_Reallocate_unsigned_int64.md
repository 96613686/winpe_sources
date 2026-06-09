# std::vector<__int64,std::allocator<__int64>>::_Reallocate(unsigned __int64)

- ea: `0x1815bb740`
- end: `0x1815bb7cf`
- name: `?_Reallocate@?$vector@_JV?$allocator@_J@std@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1815ae310`
- `0x1815bb9e0`
- `0x1815bc380`
- `0x182fd2f70`
- `0x1830bff90`
- `0x1830c0090`

## callees

- `0x1815bb740`
- `0x1815bbf10`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815bb781`
- `VCRUNTIME140!memmove` at `0x1815bb781`

## pseudocode

```c
char *__fastcall std::vector<__int64>::_Reallocate(CxVector *a1, __int64 a2)
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
0x1815bb740  push    rsi
0x1815bb742  push    rdi
0x1815bb743  push    r14
0x1815bb745  sub     rsp, 40h
0x1815bb749  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1815bb752  mov     [rsp+58h+arg_10], rbx
0x1815bb757  mov     r14, rdx
0x1815bb75a  mov     rbx, rcx
0x1815bb75d  mov     [rsp+58h+var_38], rcx
0x1815bb762  mov     [rsp+58h+var_30], rdx
0x1815bb767  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1815bb76c  mov     rsi, rax
0x1815bb76f  mov     [rsp+58h+var_28], rax
0x1815bb774  mov     r8, [rbx+8]
0x1815bb778  mov     rdx, [rbx]; Src
0x1815bb77b  sub     r8, rdx; Size
0x1815bb77e  mov     rcx, rax; void *
0x1815bb781  call    cs:__imp_memmove
0x1815bb787  nop
0x1815bb788  mov     rdx, [rbx]
0x1815bb78b  mov     rdi, [rbx+8]
0x1815bb78f  sub     rdi, rdx
0x1815bb792  sar     rdi, 3
0x1815bb796  test    rdx, rdx
0x1815bb799  jz      short loc_1815BB7AE
0x1815bb79b  mov     r8, [rbx+10h]
0x1815bb79f  sub     r8, rdx
0x1815bb7a2  sar     r8, 3
0x1815bb7a6  mov     rcx, rbx
0x1815bb7a9  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1815bb7ae  lea     rax, [rsi+r14*8]
0x1815bb7b2  mov     [rbx+10h], rax
0x1815bb7b6  lea     rax, [rsi+rdi*8]
0x1815bb7ba  mov     [rbx+8], rax
0x1815bb7be  mov     [rbx], rsi
0x1815bb7c1  mov     rbx, [rsp+58h+arg_10]
0x1815bb7c6  add     rsp, 40h
0x1815bb7ca  pop     r14
0x1815bb7cc  pop     rdi
0x1815bb7cd  pop     rsi
0x1815bb7ce  retn
```
