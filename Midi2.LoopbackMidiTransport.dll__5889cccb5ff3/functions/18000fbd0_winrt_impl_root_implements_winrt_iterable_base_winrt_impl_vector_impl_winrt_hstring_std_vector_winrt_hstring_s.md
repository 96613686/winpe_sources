# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>(void)

- ea: `0x18000fbd0`
- end: `0x18000fc50`
- name: `??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010130`
- `0x180010180`

## callees

- `0x1800041a4`
- `0x18000fbd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000fc49`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000fc49`

## pseudocode

```c
void __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>(
        __int64 a1)
{
  signed __int64 v1; // rax
  signed __int64 v2; // rtt
  volatile signed __int32 *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
    if ( v2 == v1 )
      goto LABEL_10;
  }
  v3 = (volatile signed __int32 *)(2 * v1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(2 * v1 + 24), 0xFFFFFFFF) == 1
    && _InterlockedExchangeAdd(v3 + 7, 0xFFFFFFFF) == 1
    && v3 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      goto LABEL_11;
    operator delete((void *)v3);
  }
LABEL_10:
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
LABEL_11:
    abort();
}

```

## disassembly

```asm
0x18000fbd0  push    rbx
0x18000fbd2  sub     rsp, 20h
0x18000fbd6  mov     rax, [rcx+8]
0x18000fbda  or      ebx, 0FFFFFFFFh
0x18000fbdd  test    rax, rax
0x18000fbe0  js      short loc_18000FBF0
0x18000fbe2  lea     rdx, [rax-1]
0x18000fbe6  lock cmpxchg [rcx+8], rdx
0x18000fbec  jnz     short loc_18000FBDA
0x18000fbee  jmp     short loc_18000FC31
0x18000fbf0  lea     rcx, [rax+rax]; Block
0x18000fbf4  mov     eax, ebx
0x18000fbf6  lock xadd [rcx+18h], eax
0x18000fbfb  cmp     eax, 1
0x18000fbfe  jnz     short loc_18000FC31
0x18000fc00  mov     eax, ebx
0x18000fc02  lock xadd [rcx+1Ch], eax
0x18000fc07  cmp     eax, 1
0x18000fc0a  jnz     short loc_18000FC31
0x18000fc0c  test    rcx, rcx
0x18000fc0f  jz      short loc_18000FC31
0x18000fc11  mov     eax, ebx
0x18000fc13  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000fc1b  sub     eax, 1
0x18000fc1e  jnz     short loc_18000FC23
0x18000fc20  nop
0x18000fc21  jmp     short loc_18000FC27
0x18000fc23  test    eax, eax
0x18000fc25  js      short loc_18000FC49
0x18000fc27  mov     edx, 20h ; ' '
0x18000fc2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc31  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000fc39  sub     ebx, 1
0x18000fc3c  jnz     short loc_18000FC45
0x18000fc3e  nop
0x18000fc3f  add     rsp, 20h
0x18000fc43  pop     rbx
0x18000fc44  retn
0x18000fc45  test    ebx, ebx
0x18000fc47  jns     short loc_18000FC3F
0x18000fc49  call    cs:__imp_abort
```
