# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180017f80`
- end: `0x180017ff7`
- name: `?QueryInterface@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180017f80`
- `0x18001a268`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::QueryInterface(
        unsigned __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  volatile signed __int64 *v5; // rbx
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v5 = (volatile signed __int64 *)((a1 - 32) & ((unsigned __int128)-(__int128)a1 >> 64));
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
0x180017f80  mov     [rsp+arg_0], rbx
0x180017f85  mov     [rsp+arg_8], rsi
0x180017f8a  push    rdi
0x180017f8b  sub     rsp, 20h
0x180017f8f  lea     rax, [rcx-20h]
0x180017f93  mov     rdi, r8
0x180017f96  neg     rcx
0x180017f99  mov     rsi, rdx
0x180017f9c  sbb     rbx, rbx
0x180017f9f  and     rbx, rax
0x180017fa2  mov     rcx, rbx
0x180017fa5  mov     rax, [rbx]
0x180017fa8  mov     rax, [rax+30h]
0x180017fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fb1  mov     [rdi], rax
0x180017fb4  test    rax, rax
0x180017fb7  jz      short loc_180017FD9
0x180017fb9  mov     rax, [rbx+8]
0x180017fbd  test    rax, rax
0x180017fc0  js      short loc_180017FD0
0x180017fc2  lea     rcx, [rax+1]
0x180017fc6  lock cmpxchg [rbx+8], rcx
0x180017fcc  jnz     short loc_180017FBD
0x180017fce  jmp     short loc_180017FD5
0x180017fd0  lock inc dword ptr [rax+rax+18h]
0x180017fd5  xor     eax, eax
0x180017fd7  jmp     short loc_180017FE7
0x180017fd9  mov     r8, rdi
0x180017fdc  mov     rdx, rsi
0x180017fdf  mov     rcx, rbx
0x180017fe2  call    ?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)
0x180017fe7  mov     rbx, [rsp+28h+arg_0]
0x180017fec  mov     rsi, [rsp+28h+arg_8]
0x180017ff1  add     rsp, 20h
0x180017ff5  pop     rdi
0x180017ff6  retn
```
