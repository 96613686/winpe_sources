# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)

- ea: `0x180019f1c`
- end: `0x18001a008`
- name: `?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a268`

## callees

- `0x180003d6c`
- `0x180019f1c`
- `0x18001a744`
- `0x180021010`

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
0x180019f1c  mov     [rsp+arg_8], rbx
0x180019f21  mov     [rsp+arg_10], rsi
0x180019f26  push    rdi
0x180019f27  sub     rsp, 20h
0x180019f2b  mov     rbx, [rcx+8]
0x180019f2f  mov     rsi, rcx
0x180019f32  test    rbx, rbx
0x180019f35  jns     short loc_180019F49
0x180019f37  lock inc dword ptr [rbx+rbx+18h]
0x180019f3c  lea     rax, ds:8[rbx*2]
0x180019f44  jmp     loc_180019FF8
0x180019f49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019f50  mov     ecx, 20h ; ' '; unsigned __int64
0x180019f55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019f5a  mov     rdi, rax
0x180019f5d  test    rax, rax
0x180019f60  jz      loc_180019FED
0x180019f66  mov     rax, [rsi]
0x180019f69  mov     rcx, rsi
0x180019f6c  mov     rax, [rax+18h]
0x180019f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f75  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180019f7c  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x180019f83  mov     [rsp+28h+arg_0], rdi
0x180019f88  mov     [rdi+8], rcx
0x180019f8c  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x180019f93  mov     [rdi], rcx
0x180019f96  mov     rcx, rdi
0x180019f99  mov     [rdi+10h], rax
0x180019f9d  mov     rax, 8000000000000000h
0x180019fa7  shr     rcx, 1
0x180019faa  or      rcx, rax
0x180019fad  mov     [rdi+18h], ebx
0x180019fb0  mov     dword ptr [rdi+1Ch], 1
0x180019fb7  mov     rax, rbx
0x180019fba  lock cmpxchg [rsi+8], rcx
0x180019fc0  mov     rbx, rax
0x180019fc3  jz      short loc_180019FE3
0x180019fc5  test    rax, rax
0x180019fc8  js      short loc_180019FCF
0x180019fca  xchg    eax, [rdi+18h]
0x180019fcd  jmp     short loc_180019FB7
0x180019fcf  lock inc dword ptr [rax+rax+18h]
0x180019fd4  lea     rcx, [rsp+28h+arg_0]
0x180019fd9  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x180019fde  jmp     loc_180019F3C
0x180019fe3  lock inc dword ptr [rdi+18h]
0x180019fe7  lea     rax, [rdi+8]
0x180019feb  jmp     short loc_180019FF8
0x180019fed  mov     [rsp+28h+arg_0], 0
0x180019ff6  xor     eax, eax
0x180019ff8  mov     rbx, [rsp+28h+arg_8]
0x180019ffd  mov     rsi, [rsp+28h+arg_10]
0x18001a002  add     rsp, 20h
0x18001a006  pop     rdi
0x18001a007  retn
```
