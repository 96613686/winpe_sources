# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000fd08`
- end: `0x18000fe05`
- name: `?query_interface_common@?$root_implements@Uiterator@?$iterable_base@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(__int64 (***)(void), _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fb94`

## callees

- `0x18000b008`
- `0x18000f8bc`
- `0x18000f95c`
- `0x18000fd08`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::query_interface_common(
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
    weak_ref = winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref();
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
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::AddRef(a1);
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
0x18000fd08  mov     [rsp+arg_0], rbx
0x18000fd0d  push    rdi
0x18000fd0e  sub     rsp, 20h
0x18000fd12  mov     rax, [rdx]
0x18000fd15  mov     rdi, r8
0x18000fd18  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000fd1f  mov     rbx, rcx
0x18000fd22  jnz     short loc_18000FD4F
0x18000fd24  mov     rax, [rdx+8]
0x18000fd28  cmp     rax, cs:qword_18001B408
0x18000fd2f  jnz     short loc_18000FD4F
0x18000fd31  mov     rax, [rcx]
0x18000fd34  mov     rax, [rax+18h]
0x18000fd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd3d  mov     rcx, rbx
0x18000fd40  mov     [rdi], rax
0x18000fd43  call    ?AddRef@?$root_implements@Uiterator@?$iterable_base@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::AddRef(void)
0x18000fd48  xor     eax, eax
0x18000fd4a  jmp     loc_18000FDFA
0x18000fd4f  mov     rax, [rdx]
0x18000fd52  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18000fd59  jnz     short loc_18000FD71
0x18000fd5b  mov     rax, [rdx+8]
0x18000fd5f  cmp     rax, cs:qword_18001B230
0x18000fd66  jnz     short loc_18000FD71
0x18000fd68  mov     rax, [rcx]
0x18000fd6b  mov     rax, [rax+38h]
0x18000fd6f  jmp     short loc_18000FD38
0x18000fd71  mov     rax, [rdx]
0x18000fd74  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000fd7b  jnz     short loc_18000FDA0
0x18000fd7d  mov     rax, [rdx+8]
0x18000fd81  cmp     rax, cs:qword_18001B250
0x18000fd88  jnz     short loc_18000FDA0
0x18000fd8a  call    ?make_weak_ref@?$root_implements@Uiterator@?$iterable_base@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Uhstring@3@Uno_collection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::hstring,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::make_weak_ref(void)
0x18000fd8f  mov     [rdi], rax
0x18000fd92  neg     rax
0x18000fd95  sbb     eax, eax
0x18000fd97  not     eax
0x18000fd99  and     eax, 8007000Eh
0x18000fd9e  jmp     short loc_18000FDFA
0x18000fda0  mov     rax, [rdx]
0x18000fda3  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000fdaa  jnz     short loc_18000FDBD
0x18000fdac  mov     rax, [rdx+8]
0x18000fdb0  cmp     rax, cs:qword_18001A768
0x18000fdb7  jz      loc_18000FD31
0x18000fdbd  mov     rax, [rdx]
0x18000fdc0  sub     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000fdc7  jnz     short loc_18000FDD4
0x18000fdc9  mov     rax, [rdx+8]
0x18000fdcd  sub     rax, cs:qword_18001B3B8
0x18000fdd4  mov     r9, [rcx]
0x18000fdd7  test    rax, rax
0x18000fdda  jnz     short loc_18000FDF2
0x18000fddc  mov     rax, [r9+18h]
0x18000fde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde5  mov     rcx, rax
0x18000fde8  mov     rdx, rdi
0x18000fdeb  call    ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x18000fdf0  jmp     short loc_18000FDFA
0x18000fdf2  mov     rax, [r9]
0x18000fdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdfa  mov     rbx, [rsp+28h+arg_0]
0x18000fdff  add     rsp, 20h
0x18000fe03  pop     rdi
0x18000fe04  retn
```
