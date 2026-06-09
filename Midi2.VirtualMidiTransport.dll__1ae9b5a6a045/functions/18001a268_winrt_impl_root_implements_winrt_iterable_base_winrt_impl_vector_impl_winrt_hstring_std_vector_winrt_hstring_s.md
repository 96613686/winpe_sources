# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18001a268`
- end: `0x18001a3e6`
- name: `?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017f80`
- `0x180018000`
- `0x180018080`

## callees

- `0x180003d6c`
- `0x18001408c`
- `0x180019f1c`
- `0x18001a268`
- `0x180021010`

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
0x18001a268  mov     [rsp+arg_0], rbx
0x18001a26d  push    rdi
0x18001a26e  sub     rsp, 20h
0x18001a272  mov     rax, [rdx]
0x18001a275  mov     rdi, r8
0x18001a278  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18001a27f  mov     rbx, rcx
0x18001a282  jnz     short loc_18001A2BE
0x18001a284  mov     rax, [rdx+8]
0x18001a288  cmp     rax, cs:qword_180024D20
0x18001a28f  jnz     short loc_18001A2BE
0x18001a291  mov     rax, [rcx]
0x18001a294  mov     rax, [rax+18h]
0x18001a298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a29d  mov     [rdi], rax
0x18001a2a0  mov     rax, [rbx+8]
0x18001a2a4  test    rax, rax
0x18001a2a7  js      loc_18001A36E
0x18001a2ad  lea     rcx, [rax+1]
0x18001a2b1  lock cmpxchg [rbx+8], rcx
0x18001a2b7  jnz     short loc_18001A2A4
0x18001a2b9  jmp     loc_18001A373
0x18001a2be  mov     rax, [rdx]
0x18001a2c1  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18001a2c8  jnz     short loc_18001A2FD
0x18001a2ca  mov     rax, [rdx+8]
0x18001a2ce  cmp     rax, cs:qword_180024CA0
0x18001a2d5  jnz     short loc_18001A2FD
0x18001a2d7  mov     rax, [rcx]
0x18001a2da  mov     rax, [rax+38h]
0x18001a2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2e3  mov     [rdi], rax
0x18001a2e6  mov     rax, [rbx+8]
0x18001a2ea  test    rax, rax
0x18001a2ed  js      short loc_18001A36E
0x18001a2ef  lea     rcx, [rax+1]
0x18001a2f3  lock cmpxchg [rbx+8], rcx
0x18001a2f9  jnz     short loc_18001A2EA
0x18001a2fb  jmp     short loc_18001A373
0x18001a2fd  mov     rax, [rdx]
0x18001a300  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18001a307  jnz     short loc_18001A32F
0x18001a309  mov     rax, [rdx+8]
0x18001a30d  cmp     rax, cs:qword_180024CB0
0x18001a314  jnz     short loc_18001A32F
0x18001a316  call    ?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)
0x18001a31b  mov     [rdi], rax
0x18001a31e  neg     rax
0x18001a321  sbb     eax, eax
0x18001a323  not     eax
0x18001a325  and     eax, 8007000Eh
0x18001a32a  jmp     loc_18001A3DB
0x18001a32f  mov     rax, [rdx]
0x18001a332  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001a339  jnz     short loc_18001A377
0x18001a33b  mov     rax, [rdx+8]
0x18001a33f  cmp     rax, cs:qword_180024E18
0x18001a346  jnz     short loc_18001A377
0x18001a348  mov     rax, [rcx]
0x18001a34b  mov     rax, [rax+18h]
0x18001a34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a354  mov     [rdi], rax
0x18001a357  mov     rax, [rbx+8]
0x18001a35b  test    rax, rax
0x18001a35e  js      short loc_18001A36E
0x18001a360  lea     rcx, [rax+1]
0x18001a364  lock cmpxchg [rbx+8], rcx
0x18001a36a  jnz     short loc_18001A35B
0x18001a36c  jmp     short loc_18001A373
0x18001a36e  lock inc dword ptr [rax+rax+18h]
0x18001a373  xor     eax, eax
0x18001a375  jmp     short loc_18001A3DB
0x18001a377  mov     rax, [rdx]
0x18001a37a  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18001a381  jnz     short loc_18001A3D0
0x18001a383  mov     rax, [rdx+8]
0x18001a387  cmp     rax, cs:qword_180024D30
0x18001a38e  jnz     short loc_18001A3D0
0x18001a390  mov     rax, [rcx]
0x18001a393  mov     rax, [rax+18h]
0x18001a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a39c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a3a3  mov     ecx, 20h ; ' '; unsigned __int64
0x18001a3a8  mov     rbx, rax
0x18001a3ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a3b0  xor     edx, edx
0x18001a3b2  test    rax, rax
0x18001a3b5  jz      short loc_18001A3C5
0x18001a3b7  mov     rdx, rbx
0x18001a3ba  mov     rcx, rax
0x18001a3bd  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18001a3c2  mov     rdx, rax
0x18001a3c5  mov     [rdi], rdx
0x18001a3c8  neg     rdx
0x18001a3cb  jmp     loc_18001A321
0x18001a3d0  mov     rax, [rcx]
0x18001a3d3  mov     rax, [rax]
0x18001a3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3db  mov     rbx, [rsp+28h+arg_0]
0x18001a3e0  add     rsp, 20h
0x18001a3e4  pop     rdi
0x18001a3e5  retn
```
