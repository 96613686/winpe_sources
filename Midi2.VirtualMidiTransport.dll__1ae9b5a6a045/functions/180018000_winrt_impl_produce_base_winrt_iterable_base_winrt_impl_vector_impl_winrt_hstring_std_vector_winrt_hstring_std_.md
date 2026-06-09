# winrt::impl::produce_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180018000`
- end: `0x180018077`
- name: `?QueryInterface@?$produce_base@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180018000`
- `0x18001a268`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>,void>::QueryInterface(
        unsigned __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  volatile signed __int64 *v5; // rbx
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v5 = (volatile signed __int64 *)((a1 - 16) & ((unsigned __int128)-(__int128)a1 >> 64));
  v6 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*v5 + 48))(v5);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(
             v5,
             a2,
             a3);
  v7 = *((_QWORD *)v5 + 1);
  while ( v7 >= 0 )
  {
    v8 = v7;
    v7 = _InterlockedCompareExchange64(v5 + 1, v7 + 1, v7);
    if ( v8 == v7 )
      return 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
  return 0;
}

```

## disassembly

```asm
0x180018000  mov     [rsp+arg_0], rbx
0x180018005  mov     [rsp+arg_8], rsi
0x18001800a  push    rdi
0x18001800b  sub     rsp, 20h
0x18001800f  lea     rax, [rcx-10h]
0x180018013  mov     rdi, r8
0x180018016  neg     rcx
0x180018019  mov     rsi, rdx
0x18001801c  sbb     rbx, rbx
0x18001801f  and     rbx, rax
0x180018022  mov     rcx, rbx
0x180018025  mov     rax, [rbx]
0x180018028  mov     rax, [rax+30h]
0x18001802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018031  mov     [rdi], rax
0x180018034  test    rax, rax
0x180018037  jz      short loc_180018059
0x180018039  mov     rax, [rbx+8]
0x18001803d  test    rax, rax
0x180018040  js      short loc_180018050
0x180018042  lea     rcx, [rax+1]
0x180018046  lock cmpxchg [rbx+8], rcx
0x18001804c  jnz     short loc_18001803D
0x18001804e  jmp     short loc_180018055
0x180018050  lock inc dword ptr [rax+rax+18h]
0x180018055  xor     eax, eax
0x180018057  jmp     short loc_180018067
0x180018059  mov     r8, rdi
0x18001805c  mov     rdx, rsi
0x18001805f  mov     rcx, rbx
0x180018062  call    ?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)
0x180018067  mov     rbx, [rsp+28h+arg_0]
0x18001806c  mov     rsi, [rsp+28h+arg_8]
0x180018071  add     rsp, 20h
0x180018075  pop     rdi
0x180018076  retn
```
