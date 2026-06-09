# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)

- ea: `0x18001407c`
- end: `0x180014168`
- name: `?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800143c8`

## callees

- `0x18000499c`
- `0x18001407c`
- `0x180014920`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rbx
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rax
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 1);
  if ( v1 >= 0 )
  {
    v4 = (unsigned __int64)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
      v5 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v8 = v4;
      *(_QWORD *)(v4 + 8) = &winrt::impl::weak_source<1,1>::`vftable';
      *(_QWORD *)v4 = &winrt::impl::weak_ref<1,1>::`vftable';
      *(_QWORD *)(v4 + 16) = v5;
      *(_DWORD *)(v4 + 24) = v1;
      *(_DWORD *)(v4 + 28) = 1;
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(a1 + 1, (v4 >> 1) | 0x8000000000000000uLL, v1);
        v6 = v1 == v7;
        v1 = v7;
        if ( v6 )
          break;
        if ( v7 < 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
          winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(&v8);
          return 2 * v1 + 8;
        }
        _InterlockedExchange((volatile __int32 *)(v4 + 24), v7);
      }
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 24));
      return v4 + 8;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(2 * v1 + 24));
    return 2 * v1 + 8;
  }
}

```

## disassembly

```asm
0x18001407c  mov     [rsp+arg_8], rbx
0x180014081  mov     [rsp+arg_10], rsi
0x180014086  push    rdi
0x180014087  sub     rsp, 20h
0x18001408b  mov     rbx, [rcx+8]
0x18001408f  mov     rsi, rcx
0x180014092  test    rbx, rbx
0x180014095  jns     short loc_1800140A9
0x180014097  lock inc dword ptr [rbx+rbx+18h]
0x18001409c  lea     rax, ds:8[rbx*2]
0x1800140a4  jmp     loc_180014158
0x1800140a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800140b0  mov     ecx, 20h ; ' '; unsigned __int64
0x1800140b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800140ba  mov     rdi, rax
0x1800140bd  test    rax, rax
0x1800140c0  jz      loc_18001414D
0x1800140c6  mov     rax, [rsi]
0x1800140c9  mov     rcx, rsi
0x1800140cc  mov     rax, [rax+18h]
0x1800140d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d5  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800140dc  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x1800140e3  mov     [rsp+28h+arg_0], rdi
0x1800140e8  mov     [rdi+8], rcx
0x1800140ec  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x1800140f3  mov     [rdi], rcx
0x1800140f6  mov     rcx, rdi
0x1800140f9  mov     [rdi+10h], rax
0x1800140fd  mov     rax, 8000000000000000h
0x180014107  shr     rcx, 1
0x18001410a  or      rcx, rax
0x18001410d  mov     [rdi+18h], ebx
0x180014110  mov     dword ptr [rdi+1Ch], 1
0x180014117  mov     rax, rbx
0x18001411a  lock cmpxchg [rsi+8], rcx
0x180014120  mov     rbx, rax
0x180014123  jz      short loc_180014143
0x180014125  test    rax, rax
0x180014128  js      short loc_18001412F
0x18001412a  xchg    eax, [rdi+18h]
0x18001412d  jmp     short loc_180014117
0x18001412f  lock inc dword ptr [rax+rax+18h]
0x180014134  lea     rcx, [rsp+28h+arg_0]
0x180014139  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x18001413e  jmp     loc_18001409C
0x180014143  lock inc dword ptr [rdi+18h]
0x180014147  lea     rax, [rdi+8]
0x18001414b  jmp     short loc_180014158
0x18001414d  mov     [rsp+28h+arg_0], 0
0x180014156  xor     eax, eax
0x180014158  mov     rbx, [rsp+28h+arg_8]
0x18001415d  mov     rsi, [rsp+28h+arg_10]
0x180014162  add     rsp, 20h
0x180014166  pop     rdi
0x180014167  retn
```
