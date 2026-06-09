# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<winrt::hstring,ushort const * const *>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x1800118bc`
- end: `0x180011a3a`
- name: `?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$scoped_input_iterable@Uhstring@winrt@@PEBQEBG@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800100a0`

## callees

- `0x1800033bc`
- `0x18000ce6c`
- `0x1800114f0`
- `0x1800118bc`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<winrt::hstring,unsigned short const * const *>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(
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
        weak_ref = winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref();
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
        v13 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
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
0x1800118bc  mov     [rsp+arg_0], rbx
0x1800118c1  push    rdi
0x1800118c2  sub     rsp, 20h
0x1800118c6  mov     rax, [rdx]
0x1800118c9  mov     rdi, r8
0x1800118cc  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x1800118d3  mov     rbx, rcx
0x1800118d6  jnz     short loc_180011912
0x1800118d8  mov     rax, [rdx+8]
0x1800118dc  cmp     rax, cs:qword_1800166F0
0x1800118e3  jnz     short loc_180011912
0x1800118e5  mov     rax, [rcx]
0x1800118e8  mov     rax, [rax+18h]
0x1800118ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118f1  mov     [rdi], rax
0x1800118f4  mov     rax, [rbx+8]
0x1800118f8  test    rax, rax
0x1800118fb  js      loc_1800119C2
0x180011901  lea     rcx, [rax+1]
0x180011905  lock cmpxchg [rbx+8], rcx
0x18001190b  jnz     short loc_1800118F8
0x18001190d  jmp     loc_1800119C7
0x180011912  mov     rax, [rdx]
0x180011915  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18001191c  jnz     short loc_180011951
0x18001191e  mov     rax, [rdx+8]
0x180011922  cmp     rax, cs:qword_1800163E8
0x180011929  jnz     short loc_180011951
0x18001192b  mov     rax, [rcx]
0x18001192e  mov     rax, [rax+38h]
0x180011932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011937  mov     [rdi], rax
0x18001193a  mov     rax, [rbx+8]
0x18001193e  test    rax, rax
0x180011941  js      short loc_1800119C2
0x180011943  lea     rcx, [rax+1]
0x180011947  lock cmpxchg [rbx+8], rcx
0x18001194d  jnz     short loc_18001193E
0x18001194f  jmp     short loc_1800119C7
0x180011951  mov     rax, [rdx]
0x180011954  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18001195b  jnz     short loc_180011983
0x18001195d  mov     rax, [rdx+8]
0x180011961  cmp     rax, cs:qword_180016418
0x180011968  jnz     short loc_180011983
0x18001196a  call    ?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)
0x18001196f  mov     [rdi], rax
0x180011972  neg     rax
0x180011975  sbb     eax, eax
0x180011977  not     eax
0x180011979  and     eax, 8007000Eh
0x18001197e  jmp     loc_180011A2F
0x180011983  mov     rax, [rdx]
0x180011986  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001198d  jnz     short loc_1800119CB
0x18001198f  mov     rax, [rdx+8]
0x180011993  cmp     rax, cs:qword_180016700
0x18001199a  jnz     short loc_1800119CB
0x18001199c  mov     rax, [rcx]
0x18001199f  mov     rax, [rax+18h]
0x1800119a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a8  mov     [rdi], rax
0x1800119ab  mov     rax, [rbx+8]
0x1800119af  test    rax, rax
0x1800119b2  js      short loc_1800119C2
0x1800119b4  lea     rcx, [rax+1]
0x1800119b8  lock cmpxchg [rbx+8], rcx
0x1800119be  jnz     short loc_1800119AF
0x1800119c0  jmp     short loc_1800119C7
0x1800119c2  lock inc dword ptr [rax+rax+18h]
0x1800119c7  xor     eax, eax
0x1800119c9  jmp     short loc_180011A2F
0x1800119cb  mov     rax, [rdx]
0x1800119ce  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x1800119d5  jnz     short loc_180011A24
0x1800119d7  mov     rax, [rdx+8]
0x1800119db  cmp     rax, cs:qword_180016710
0x1800119e2  jnz     short loc_180011A24
0x1800119e4  mov     rax, [rcx]
0x1800119e7  mov     rax, [rax+18h]
0x1800119eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800119f7  mov     ecx, 20h ; ' '; unsigned __int64
0x1800119fc  mov     rbx, rax
0x1800119ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011a04  xor     edx, edx
0x180011a06  test    rax, rax
0x180011a09  jz      short loc_180011A19
0x180011a0b  mov     rdx, rbx
0x180011a0e  mov     rcx, rax
0x180011a11  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180011a16  mov     rdx, rax
0x180011a19  mov     [rdi], rdx
0x180011a1c  neg     rdx
0x180011a1f  jmp     loc_180011975
0x180011a24  mov     rax, [rcx]
0x180011a27  mov     rax, [rax]
0x180011a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a2f  mov     rbx, [rsp+28h+arg_0]
0x180011a34  add     rsp, 20h
0x180011a38  pop     rdi
0x180011a39  retn
```
