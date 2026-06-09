# winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator>::`vector deleting destructor'(uint)

- ea: `0x180014a60`
- end: `0x180014aa7`
- name: `??_E?$heap_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `71`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003914`
- `0x180014308`
- `0x180014a60`
- `0x18001a72c`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::heap_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator>::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  if ( Block[4] )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
  winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_0], rbx
0x180014a65  push    rdi
0x180014a66  sub     rsp, 20h
0x180014a6a  mov     rbx, rcx
0x180014a6d  mov     edi, edx
0x180014a6f  add     rcx, 20h ; ' '
0x180014a73  cmp     qword ptr [rcx], 0
0x180014a77  jz      short loc_180014A7E
0x180014a79  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180014a7e  mov     rcx, rbx
0x180014a81  call    ??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>(void)
0x180014a86  test    dil, 1
0x180014a8a  jz      short loc_180014A99
0x180014a8c  mov     edx, 38h ; '8'
0x180014a91  mov     rcx, rbx; Block
0x180014a94  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014a99  mov     rax, rbx
0x180014a9c  mov     rbx, [rsp+28h+arg_0]
0x180014aa1  add     rsp, 20h
0x180014aa5  pop     rdi
0x180014aa6  retn
```
