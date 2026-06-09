# winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>>::`vector deleting destructor'(uint)

- ea: `0x180014a10`
- end: `0x180014a50`
- name: `??_E?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `64`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180003914`
- `0x180014308`
- `0x1800143b0`
- `0x180014a10`

## pseudocode

```c
char *__fastcall winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vector deleting destructor'(
        char *Block,
        char a2)
{
  std::vector<winrt::hstring>::~vector<winrt::hstring>(Block + 48);
  winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180014a10  mov     [rsp+arg_0], rbx
0x180014a15  push    rdi
0x180014a16  sub     rsp, 20h
0x180014a1a  mov     rdi, rcx
0x180014a1d  mov     ebx, edx
0x180014a1f  add     rcx, 30h ; '0'
0x180014a23  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x180014a28  mov     rcx, rdi
0x180014a2b  call    ??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>(void)
0x180014a30  test    bl, 1
0x180014a33  jz      short loc_180014A42
0x180014a35  mov     edx, 48h ; 'H'
0x180014a3a  mov     rcx, rdi; Block
0x180014a3d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014a42  mov     rbx, [rsp+28h+arg_0]
0x180014a47  mov     rax, rdi
0x180014a4a  add     rsp, 20h
0x180014a4e  pop     rdi
0x180014a4f  retn
```
