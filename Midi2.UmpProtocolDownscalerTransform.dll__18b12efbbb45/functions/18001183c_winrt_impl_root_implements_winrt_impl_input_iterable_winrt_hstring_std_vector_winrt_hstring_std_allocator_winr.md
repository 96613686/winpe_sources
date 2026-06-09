# winrt::impl::root_implements<winrt::impl::input_iterable<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>>,winrt::non_agile,winrt::no_weak_ref,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18001183c`
- end: `0x1800118b4`
- name: `?query_interface_common@?$root_implements@U?$input_iterable@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@impl@winrt@@Unon_agile@3@Uno_weak_ref@3@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010030`

## callees

- `0x18001183c`
- `0x180013010`

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
0x18001183c  mov     [rsp+arg_0], rbx
0x180011841  push    rdi
0x180011842  sub     rsp, 20h
0x180011846  mov     rax, [rdx]
0x180011849  mov     rdi, r8
0x18001184c  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x180011853  mov     rbx, rcx
0x180011856  jnz     short loc_18001187C
0x180011858  mov     rax, [rdx+8]
0x18001185c  cmp     rax, cs:qword_1800166F0
0x180011863  jnz     short loc_18001187C
0x180011865  mov     rax, [rcx]
0x180011868  mov     rax, [rax+18h]
0x18001186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011871  mov     [rdi], rax
0x180011874  lock inc dword ptr [rbx+8]
0x180011878  xor     eax, eax
0x18001187a  jmp     short loc_1800118A9
0x18001187c  mov     rax, [rdx]
0x18001187f  sub     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180011886  jnz     short loc_180011893
0x180011888  mov     rax, [rdx+8]
0x18001188c  sub     rax, cs:qword_1800163E8
0x180011893  mov     r9, [rcx]
0x180011896  test    rax, rax
0x180011899  jnz     short loc_1800118A1
0x18001189b  mov     rax, [r9+38h]
0x18001189f  jmp     short loc_18001186C
0x1800118a1  mov     rax, [r9]
0x1800118a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a9  mov     rbx, [rsp+28h+arg_0]
0x1800118ae  add     rsp, 20h
0x1800118b2  pop     rdi
0x1800118b3  retn
```
