# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<__int64,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__int64>>>>,__int64,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<__int64>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180022448`
- end: `0x180022545`
- name: `?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$scoped_input_iterable@_JV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_J@std@@@std@@@std@@@impl@winrt@@_JUno_collection_version@23@@winrt@@U?$IIterator@_J@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800222d4`

## callees

- `0x18001fe38`
- `0x180021ddc`
- `0x180021e7c`
- `0x180022448`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<__int64,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__int64>>>>,__int64,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<__int64>>::query_interface_common(
        __int64 (***a1)(void),
        _QWORD *a2,
        __int64 *a3)
{
  __int64 (*v5)(void); // rax
  __int64 weak_ref; // rax
  __int64 v8; // rax
  __int64 (**v9)(void); // r9
  __int64 v10; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
    goto LABEL_3;
  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable> && a2[1] == 0x901E1065AAD75A9CuLL )
  {
    v5 = (*a1)[7];
    goto LABEL_4;
  }
  if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
  {
    weak_ref = winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<float,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<float>>>>,float,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<float>>::make_weak_ref();
    *a3 = weak_ref;
    return weak_ref == 0 ? 0x8007000E : 0;
  }
  else
  {
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
    {
LABEL_3:
      v5 = (*a1)[3];
LABEL_4:
      *a3 = v5();
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<__int64,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__int64>>>>,__int64,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<__int64>>::AddRef(a1);
      return 0;
    }
    v8 = *a2 - winrt::impl::guid_v<winrt::impl::IMarshal>;
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IMarshal> )
      v8 = a2[1] - 0x46000000000000C0LL;
    v9 = *a1;
    if ( v8 )
    {
      return (*v9)();
    }
    else
    {
      v10 = v9[3]();
      return winrt::impl::make_marshaler(v10, a3);
    }
  }
}

```

## disassembly

```asm
0x180022448  mov     [rsp+arg_0], rbx
0x18002244d  push    rdi
0x18002244e  sub     rsp, 20h
0x180022452  mov     rax, [rdx]
0x180022455  mov     rdi, r8
0x180022458  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18002245f  mov     rbx, rcx
0x180022462  jnz     short loc_18002248F
0x180022464  mov     rax, [rdx+8]
0x180022468  cmp     rax, cs:qword_180034E58
0x18002246f  jnz     short loc_18002248F
0x180022471  mov     rax, [rcx]
0x180022474  mov     rax, [rax+18h]
0x180022478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002247d  mov     rcx, rbx
0x180022480  mov     [rdi], rax
0x180022483  call    ?AddRef@?$root_implements@Uiterator@?$iterable_base@U?$scoped_input_iterable@_JV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_J@std@@@std@@@std@@@impl@winrt@@_JUno_collection_version@23@@winrt@@U?$IIterator@_J@Collections@Foundation@Windows@3@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<__int64,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__int64>>>>,__int64,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<__int64>>::AddRef(void)
0x180022488  xor     eax, eax
0x18002248a  jmp     loc_18002253A
0x18002248f  mov     rax, [rdx]
0x180022492  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180022499  jnz     short loc_1800224B1
0x18002249b  mov     rax, [rdx+8]
0x18002249f  cmp     rax, cs:qword_180034E48
0x1800224a6  jnz     short loc_1800224B1
0x1800224a8  mov     rax, [rcx]
0x1800224ab  mov     rax, [rax+38h]
0x1800224af  jmp     short loc_180022478
0x1800224b1  mov     rax, [rdx]
0x1800224b4  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x1800224bb  jnz     short loc_1800224E0
0x1800224bd  mov     rax, [rdx+8]
0x1800224c1  cmp     rax, cs:qword_180034E98
0x1800224c8  jnz     short loc_1800224E0
0x1800224ca  call    ?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$scoped_input_iterable@MV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@M@std@@@std@@@std@@@impl@winrt@@MUno_collection_version@23@@winrt@@U?$IIterator@M@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::scoped_input_iterable<float,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<float>>>>,float,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<float>>::make_weak_ref(void)
0x1800224cf  mov     [rdi], rax
0x1800224d2  neg     rax
0x1800224d5  sbb     eax, eax
0x1800224d7  not     eax
0x1800224d9  and     eax, 8007000Eh
0x1800224de  jmp     short loc_18002253A
0x1800224e0  mov     rax, [rdx]
0x1800224e3  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800224ea  jnz     short loc_1800224FD
0x1800224ec  mov     rax, [rdx+8]
0x1800224f0  cmp     rax, cs:qword_180034E68
0x1800224f7  jz      loc_180022471
0x1800224fd  mov     rax, [rdx]
0x180022500  sub     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180022507  jnz     short loc_180022514
0x180022509  mov     rax, [rdx+8]
0x18002250d  sub     rax, cs:qword_180034E78
0x180022514  mov     r9, [rcx]
0x180022517  test    rax, rax
0x18002251a  jnz     short loc_180022532
0x18002251c  mov     rax, [r9+18h]
0x180022520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022525  mov     rcx, rax
0x180022528  mov     rdx, rdi
0x18002252b  call    ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x180022530  jmp     short loc_18002253A
0x180022532  mov     rax, [r9]
0x180022535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002253a  mov     rbx, [rsp+28h+arg_0]
0x18002253f  add     rsp, 20h
0x180022543  pop     rdi
0x180022544  retn
```
