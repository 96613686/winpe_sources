# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180018080`
- end: `0x1800180f7`
- name: `?QueryInterface@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180018080`
- `0x18001a268`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,void>::QueryInterface(
        unsigned __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  volatile signed __int64 *v5; // rbx
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v5 = (volatile signed __int64 *)((a1 - 24) & ((unsigned __int128)-(__int128)a1 >> 64));
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
0x180018080  mov     [rsp+arg_0], rbx
0x180018085  mov     [rsp+arg_8], rsi
0x18001808a  push    rdi
0x18001808b  sub     rsp, 20h
0x18001808f  lea     rax, [rcx-18h]
0x180018093  mov     rdi, r8
0x180018096  neg     rcx
0x180018099  mov     rsi, rdx
0x18001809c  sbb     rbx, rbx
0x18001809f  and     rbx, rax
0x1800180a2  mov     rcx, rbx
0x1800180a5  mov     rax, [rbx]
0x1800180a8  mov     rax, [rax+30h]
0x1800180ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180b1  mov     [rdi], rax
0x1800180b4  test    rax, rax
0x1800180b7  jz      short loc_1800180D9
0x1800180b9  mov     rax, [rbx+8]
0x1800180bd  test    rax, rax
0x1800180c0  js      short loc_1800180D0
0x1800180c2  lea     rcx, [rax+1]
0x1800180c6  lock cmpxchg [rbx+8], rcx
0x1800180cc  jnz     short loc_1800180BD
0x1800180ce  jmp     short loc_1800180D5
0x1800180d0  lock inc dword ptr [rax+rax+18h]
0x1800180d5  xor     eax, eax
0x1800180d7  jmp     short loc_1800180E7
0x1800180d9  mov     r8, rdi
0x1800180dc  mov     rdx, rsi
0x1800180df  mov     rcx, rbx
0x1800180e2  call    ?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)
0x1800180e7  mov     rbx, [rsp+28h+arg_0]
0x1800180ec  mov     rsi, [rsp+28h+arg_8]
0x1800180f1  add     rsp, 20h
0x1800180f5  pop     rdi
0x1800180f6  retn
```
