# std::vector<unsigned __int64,std::allocator<unsigned __int64>>::_Reallocate(unsigned __int64)

- ea: `0x1815bb7d0`
- end: `0x1815bb85f`
- name: `?_Reallocate@?$vector@_KV?$allocator@_K@std@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1815ae3d0`
- `0x1815bba60`
- `0x1815bc3d0`
- `0x182fd3110`
- `0x18304a220`
- `0x1830c0220`

## callees

- `0x1815bb7d0`
- `0x1815bbf10`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815bb811`
- `VCRUNTIME140!memmove` at `0x1815bb811`

## pseudocode

```c
char *__fastcall std::vector<unsigned __int64>::_Reallocate(CxVector *a1, __int64 a2)
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
0x1815bb7d0  push    rsi
0x1815bb7d2  push    rdi
0x1815bb7d3  push    r14
0x1815bb7d5  sub     rsp, 40h
0x1815bb7d9  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x1815bb7e2  mov     [rsp+58h+arg_10], rbx
0x1815bb7e7  mov     r14, rdx
0x1815bb7ea  mov     rbx, rcx
0x1815bb7ed  mov     [rsp+58h+var_38], rcx
0x1815bb7f2  mov     [rsp+58h+var_30], rdx
0x1815bb7f7  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1815bb7fc  mov     rsi, rax
0x1815bb7ff  mov     [rsp+58h+var_28], rax
0x1815bb804  mov     r8, [rbx+8]
0x1815bb808  mov     rdx, [rbx]; Src
0x1815bb80b  sub     r8, rdx; Size
0x1815bb80e  mov     rcx, rax; void *
0x1815bb811  call    cs:__imp_memmove
0x1815bb817  nop
0x1815bb818  mov     rdx, [rbx]
0x1815bb81b  mov     rdi, [rbx+8]
0x1815bb81f  sub     rdi, rdx
0x1815bb822  sar     rdi, 3
0x1815bb826  test    rdx, rdx
0x1815bb829  jz      short loc_1815BB83E
0x1815bb82b  mov     r8, [rbx+10h]
0x1815bb82f  sub     r8, rdx
0x1815bb832  sar     r8, 3
0x1815bb836  mov     rcx, rbx
0x1815bb839  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1815bb83e  lea     rax, [rsi+r14*8]
0x1815bb842  mov     [rbx+10h], rax
0x1815bb846  lea     rax, [rsi+rdi*8]
0x1815bb84a  mov     [rbx+8], rax
0x1815bb84e  mov     [rbx], rsi
0x1815bb851  mov     rbx, [rsp+58h+arg_10]
0x1815bb856  add     rsp, 40h
0x1815bb85a  pop     r14
0x1815bb85c  pop     rdi
0x1815bb85d  pop     rsi
0x1815bb85e  retn
```
