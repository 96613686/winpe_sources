# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::First(void * *)

- ea: `0x180015060`
- end: `0x180015121`
- name: `?First@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003940`
- `0x180015060`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::First(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx
  _DWORD *v4; // rdx
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  if ( !a1 || (v3 = a1 - 32, a1 == -8) )
    v3 = 0;
  try
  {
    v4 = operator new(0x38u);
    v4[6] = *(_DWORD *)(v3 + 40);
    *((_QWORD *)v4 + 2) = &winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_QWORD *)v4 + 1) = 1;
    *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable';
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = *(_QWORD *)(v3 + 48);
    *((_QWORD *)v4 + 6) = *(_QWORD *)(v3 + 56);
    if ( v3 )
    {
      *((_QWORD *)v4 + 4) = v3;
      v5 = *(_QWORD *)(v3 + 8);
      while ( v5 >= 0 )
      {
        v6 = v5;
        v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8), v5 + 1, v5);
        if ( v6 == v5 )
          goto LABEL_11;
      }
      _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
    }
LABEL_11:
    *(_QWORD *)v4 = &winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable';
    *a2 = v4 + 4;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x180015060  mov     [rsp+arg_8], rbx
0x180015065  push    rdi
0x180015066  sub     rsp, 20h
0x18001506a  mov     rdi, rdx
0x18001506d  mov     qword ptr [rdx], 0
0x180015074  test    rcx, rcx
0x180015077  jz      short loc_180015086
0x180015079  lea     rbx, [rcx-20h]
0x18001507d  lea     rax, [rbx+28h]
0x180015081  test    rax, rax
0x180015084  jnz     short loc_180015088
0x180015086  xor     ebx, ebx
0x180015088  mov     ecx, 38h ; '8'; Size
0x18001508d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015092  mov     rdx, rax
0x180015095  mov     ecx, [rbx+28h]
0x180015098  nop
0x180015099  mov     [rax+18h], ecx
0x18001509c  lea     r8, [rax+10h]
0x1800150a0  lea     rax, ??_7?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::`vftable'
0x1800150a7  mov     [r8], rax
0x1800150aa  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800150b1  mov     qword ptr [rdx+8], 1
0x1800150b9  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable'
0x1800150c0  mov     [rdx], rax
0x1800150c3  mov     qword ptr [rdx+20h], 0
0x1800150cb  mov     rax, [rbx+30h]
0x1800150cf  mov     [rdx+28h], rax
0x1800150d3  mov     rax, [rbx+38h]
0x1800150d7  mov     [rdx+30h], rax
0x1800150db  test    rbx, rbx
0x1800150de  jz      short loc_180015100
0x1800150e0  mov     [rdx+20h], rbx
0x1800150e4  mov     rax, [rbx+8]
0x1800150e8  test    rax, rax
0x1800150eb  js      short loc_1800150FB
0x1800150ed  lea     rcx, [rax+1]
0x1800150f1  lock cmpxchg [rbx+8], rcx
0x1800150f7  jnz     short loc_1800150E8
0x1800150f9  jmp     short loc_180015100
0x1800150fb  lock inc dword ptr [rax+rax+18h]
0x180015100  lea     rax, ??_7iterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@6B@; const winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator::`vftable'
0x180015107  mov     [rdx], rax
0x18001510a  mov     [rdi], r8
0x18001510d  xor     eax, eax
0x18001510f  jmp     short loc_180015115
0x180015111  mov     eax, [rsp+28h+arg_0]
0x180015115  mov     rbx, [rsp+28h+arg_8]
0x18001511a  add     rsp, 20h
0x18001511e  pop     rdi
0x18001511f  retn
```
