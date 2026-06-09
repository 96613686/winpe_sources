# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>(void)

- ea: `0x180014308`
- end: `0x180014388`
- name: `??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014a10`
- `0x180014a60`

## callees

- `0x180003914`
- `0x180014308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014381`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014381`

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
0x180014308  push    rbx
0x18001430a  sub     rsp, 20h
0x18001430e  mov     rax, [rcx+8]
0x180014312  or      ebx, 0FFFFFFFFh
0x180014315  test    rax, rax
0x180014318  js      short loc_180014328
0x18001431a  lea     rdx, [rax-1]
0x18001431e  lock cmpxchg [rcx+8], rdx
0x180014324  jnz     short loc_180014312
0x180014326  jmp     short loc_180014369
0x180014328  lea     rcx, [rax+rax]; Block
0x18001432c  mov     eax, ebx
0x18001432e  lock xadd [rcx+18h], eax
0x180014333  cmp     eax, 1
0x180014336  jnz     short loc_180014369
0x180014338  mov     eax, ebx
0x18001433a  lock xadd [rcx+1Ch], eax
0x18001433f  cmp     eax, 1
0x180014342  jnz     short loc_180014369
0x180014344  test    rcx, rcx
0x180014347  jz      short loc_180014369
0x180014349  mov     eax, ebx
0x18001434b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180014353  sub     eax, 1
0x180014356  jnz     short loc_18001435B
0x180014358  nop
0x180014359  jmp     short loc_18001435F
0x18001435b  test    eax, eax
0x18001435d  js      short loc_180014381
0x18001435f  mov     edx, 20h ; ' '
0x180014364  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014369  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180014371  sub     ebx, 1
0x180014374  jnz     short loc_18001437D
0x180014376  nop
0x180014377  add     rsp, 20h
0x18001437b  pop     rbx
0x18001437c  retn
0x18001437d  test    ebx, ebx
0x18001437f  jns     short loc_180014377
0x180014381  call    cs:__imp_abort
```
