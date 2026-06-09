# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)

- ea: `0x180015248`
- end: `0x1800152e2`
- name: `?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180015130`
- `0x1800151c0`

## callees

- `0x1800046b8`
- `0x180013ed0`
- `0x180015248`
- `0x1800194c8`

## pseudocode

```c
_QWORD *__fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3)
{
  __int64 v4; // r10
  __int64 v5; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  int v11; // [rsp+28h] [rbp-40h] BYREF
  const char *v12; // [rsp+30h] [rbp-38h]
  __int64 v13; // [rsp+38h] [rbp-30h]
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-28h] BYREF

  v4 = a3;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 56;
  v7 = a1 + 8;
  v8 = *(_QWORD *)v5;
  if ( !a1 )
    v7 = 48;
  if ( (unsigned int)v4 >= (unsigned int)((v8 - *(_QWORD *)v7) >> 3) )
  {
    v11 = 1639;
    v12 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
    v13 = 0;
    winrt::hresult_out_of_bounds::hresult_out_of_bounds(
      (winrt::hresult_out_of_bounds *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)&v11);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v9 = a1 + 8;
  if ( !a1 )
    v9 = 48;
  *a2 = winrt::impl::duplicate_hstring(
          *(winrt::impl **)(*(_QWORD *)v9 + 8 * v4),
          (struct winrt::impl::hstring_header *)0x30);
  return a2;
}

```

## disassembly

```asm
0x180015248  push    rbx
0x18001524a  sub     rsp, 60h
0x18001524e  mov     r9, rcx
0x180015251  mov     r10d, r8d
0x180015254  test    r9, r9
0x180015257  lea     rax, [rcx+10h]
0x18001525b  mov     ecx, 38h ; '8'
0x180015260  mov     rbx, rdx
0x180015263  cmovz   rax, rcx
0x180015267  lea     r8, [r9+8]
0x18001526b  lea     edx, [rcx-8]; struct winrt::impl::hstring_header *
0x18001526e  mov     rax, [rax]
0x180015271  cmovz   r8, rdx
0x180015275  sub     rax, [r8]
0x180015278  sar     rax, 3
0x18001527c  cmp     r10d, eax
0x18001527f  jnb     short loc_1800152A4
0x180015281  test    r9, r9
0x180015284  lea     rcx, [r9+8]
0x180015288  cmovz   rcx, rdx
0x18001528c  mov     rcx, [rcx]
0x18001528f  mov     rcx, [rcx+r10*8]; this
0x180015293  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180015298  mov     [rbx], rax
0x18001529b  mov     rax, rbx
0x18001529e  add     rsp, 60h
0x1800152a2  pop     rbx
0x1800152a3  retn
0x1800152a4  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800152ab  mov     [rsp+68h+var_40], 667h
0x1800152b3  lea     rdx, [rsp+68h+var_40]; struct winrt::impl::slim_source_location *
0x1800152b8  mov     [rsp+68h+var_38], rax
0x1800152bd  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800152c2  mov     [rsp+68h+var_30], 0
0x1800152cb  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800152d0  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800152d7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800152dc  call    _CxxThrowException_0
```
