# winrt::impl::root_implements<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>,winrt::non_agile,winrt::no_weak_ref,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000fc88`
- end: `0x18000fd00`
- name: `?query_interface_common@?$root_implements@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Unon_agile@3@Uno_weak_ref@3@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(volatile signed __int32 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fb3c`

## callees

- `0x18000fc88`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring>>,winrt::non_agile,winrt::no_weak_ref,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::query_interface_common(
        volatile signed __int32 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 (*v4)(void); // rax
  __int64 v6; // rax
  __int64 (**v7)(void); // r9

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
  {
    v4 = *(__int64 (**)(void))(*(_QWORD *)a1 + 24LL);
LABEL_4:
    *a3 = v4();
    _InterlockedIncrement(a1 + 2);
    return 0;
  }
  v6 = *a2 - winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>;
  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable> )
    v6 = a2[1] + 0x6FE1EF9A5528A564LL;
  v7 = *(__int64 (***)(void))a1;
  if ( !v6 )
  {
    v4 = v7[7];
    goto LABEL_4;
  }
  return (*v7)();
}

```

## disassembly

```asm
0x18000fc88  mov     [rsp+arg_0], rbx
0x18000fc8d  push    rdi
0x18000fc8e  sub     rsp, 20h
0x18000fc92  mov     rax, [rdx]
0x18000fc95  mov     rdi, r8
0x18000fc98  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000fc9f  mov     rbx, rcx
0x18000fca2  jnz     short loc_18000FCC8
0x18000fca4  mov     rax, [rdx+8]
0x18000fca8  cmp     rax, cs:qword_18001B408
0x18000fcaf  jnz     short loc_18000FCC8
0x18000fcb1  mov     rax, [rcx]
0x18000fcb4  mov     rax, [rax+18h]
0x18000fcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcbd  mov     [rdi], rax
0x18000fcc0  lock inc dword ptr [rbx+8]
0x18000fcc4  xor     eax, eax
0x18000fcc6  jmp     short loc_18000FCF5
0x18000fcc8  mov     rax, [rdx]
0x18000fccb  sub     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18000fcd2  jnz     short loc_18000FCDF
0x18000fcd4  mov     rax, [rdx+8]
0x18000fcd8  sub     rax, cs:qword_18001B230
0x18000fcdf  mov     r9, [rcx]
0x18000fce2  test    rax, rax
0x18000fce5  jnz     short loc_18000FCED
0x18000fce7  mov     rax, [r9+38h]
0x18000fceb  jmp     short loc_18000FCB8
0x18000fced  mov     rax, [r9]
0x18000fcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf5  mov     rbx, [rsp+28h+arg_0]
0x18000fcfa  add     rsp, 20h
0x18000fcfe  pop     rdi
0x18000fcff  retn
```
