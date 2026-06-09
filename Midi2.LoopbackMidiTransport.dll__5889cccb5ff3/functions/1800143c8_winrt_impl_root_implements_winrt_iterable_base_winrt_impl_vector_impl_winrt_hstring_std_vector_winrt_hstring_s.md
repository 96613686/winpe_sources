# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x1800143c8`
- end: `0x180014546`
- name: `?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012390`
- `0x180012410`
- `0x180012490`

## callees

- `0x18000499c`
- `0x18000f954`
- `0x18001407c`
- `0x1800143c8`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(
        volatile signed __int64 *a1,
        _QWORD *a2,
        __int64 *a3)
{
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  signed __int64 v7; // rtt
  __int64 weak_ref; // rax
  bool v9; // cf
  signed __int64 v11; // rtt
  __int64 v12; // rbx
  void *v13; // rax
  __int64 v14; // rdx

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
  {
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
    v5 = *((_QWORD *)a1 + 1);
    while ( v5 >= 0 )
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
      if ( v6 == v5 )
        return 0;
    }
  }
  else
  {
    if ( *a2 != winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable> || a2[1] != 0x901E1065AAD75A9CuLL )
    {
      if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
      {
        weak_ref = winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref();
        *a3 = weak_ref;
        v9 = weak_ref != 0;
      }
      else
      {
        if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
        {
          *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
          v5 = *((_QWORD *)a1 + 1);
          while ( v5 >= 0 )
          {
            v11 = v5;
            v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
            if ( v11 == v5 )
              return 0;
          }
          goto LABEL_23;
        }
        if ( *a2 != winrt::impl::guid_v<winrt::impl::IMarshal> || a2[1] != 0x46000000000000C0LL )
          return (**(__int64 (__fastcall ***)(volatile signed __int64 *))a1)(a1);
        v12 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
        v13 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        v14 = 0;
        if ( v13 )
          v14 = `winrt::impl::make_marshaler'::`2'::marshaler::marshaler(v13, v12);
        *a3 = v14;
        v9 = v14 != 0;
      }
      return v9 ? 0 : 0x8007000E;
    }
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 56))(a1);
    v5 = *((_QWORD *)a1 + 1);
    while ( v5 >= 0 )
    {
      v7 = v5;
      v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
      if ( v7 == v5 )
        return 0;
    }
  }
LABEL_23:
  _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
  return 0;
}

```

## disassembly

```asm
0x1800143c8  mov     [rsp+arg_0], rbx
0x1800143cd  push    rdi
0x1800143ce  sub     rsp, 20h
0x1800143d2  mov     rax, [rdx]
0x1800143d5  mov     rdi, r8
0x1800143d8  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x1800143df  mov     rbx, rcx
0x1800143e2  jnz     short loc_18001441E
0x1800143e4  mov     rax, [rdx+8]
0x1800143e8  cmp     rax, cs:qword_1800529C0
0x1800143ef  jnz     short loc_18001441E
0x1800143f1  mov     rax, [rcx]
0x1800143f4  mov     rax, [rax+18h]
0x1800143f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143fd  mov     [rdi], rax
0x180014400  mov     rax, [rbx+8]
0x180014404  test    rax, rax
0x180014407  js      loc_1800144CE
0x18001440d  lea     rcx, [rax+1]
0x180014411  lock cmpxchg [rbx+8], rcx
0x180014417  jnz     short loc_180014404
0x180014419  jmp     loc_1800144D3
0x18001441e  mov     rax, [rdx]
0x180014421  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180014428  jnz     short loc_18001445D
0x18001442a  mov     rax, [rdx+8]
0x18001442e  cmp     rax, cs:qword_180052940
0x180014435  jnz     short loc_18001445D
0x180014437  mov     rax, [rcx]
0x18001443a  mov     rax, [rax+38h]
0x18001443e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014443  mov     [rdi], rax
0x180014446  mov     rax, [rbx+8]
0x18001444a  test    rax, rax
0x18001444d  js      short loc_1800144CE
0x18001444f  lea     rcx, [rax+1]
0x180014453  lock cmpxchg [rbx+8], rcx
0x180014459  jnz     short loc_18001444A
0x18001445b  jmp     short loc_1800144D3
0x18001445d  mov     rax, [rdx]
0x180014460  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x180014467  jnz     short loc_18001448F
0x180014469  mov     rax, [rdx+8]
0x18001446d  cmp     rax, cs:qword_180052950
0x180014474  jnz     short loc_18001448F
0x180014476  call    ?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)
0x18001447b  mov     [rdi], rax
0x18001447e  neg     rax
0x180014481  sbb     eax, eax
0x180014483  not     eax
0x180014485  and     eax, 8007000Eh
0x18001448a  jmp     loc_18001453B
0x18001448f  mov     rax, [rdx]
0x180014492  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180014499  jnz     short loc_1800144D7
0x18001449b  mov     rax, [rdx+8]
0x18001449f  cmp     rax, cs:qword_180052AB8
0x1800144a6  jnz     short loc_1800144D7
0x1800144a8  mov     rax, [rcx]
0x1800144ab  mov     rax, [rax+18h]
0x1800144af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b4  mov     [rdi], rax
0x1800144b7  mov     rax, [rbx+8]
0x1800144bb  test    rax, rax
0x1800144be  js      short loc_1800144CE
0x1800144c0  lea     rcx, [rax+1]
0x1800144c4  lock cmpxchg [rbx+8], rcx
0x1800144ca  jnz     short loc_1800144BB
0x1800144cc  jmp     short loc_1800144D3
0x1800144ce  lock inc dword ptr [rax+rax+18h]
0x1800144d3  xor     eax, eax
0x1800144d5  jmp     short loc_18001453B
0x1800144d7  mov     rax, [rdx]
0x1800144da  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x1800144e1  jnz     short loc_180014530
0x1800144e3  mov     rax, [rdx+8]
0x1800144e7  cmp     rax, cs:qword_1800529D0
0x1800144ee  jnz     short loc_180014530
0x1800144f0  mov     rax, [rcx]
0x1800144f3  mov     rax, [rax+18h]
0x1800144f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014503  mov     ecx, 20h ; ' '; unsigned __int64
0x180014508  mov     rbx, rax
0x18001450b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014510  xor     edx, edx
0x180014512  test    rax, rax
0x180014515  jz      short loc_180014525
0x180014517  mov     rdx, rbx
0x18001451a  mov     rcx, rax
0x18001451d  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180014522  mov     rdx, rax
0x180014525  mov     [rdi], rdx
0x180014528  neg     rdx
0x18001452b  jmp     loc_180014481
0x180014530  mov     rax, [rcx]
0x180014533  mov     rax, [rax]
0x180014536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001453b  mov     rbx, [rsp+28h+arg_0]
0x180014540  add     rsp, 20h
0x180014544  pop     rdi
0x180014545  retn
```
