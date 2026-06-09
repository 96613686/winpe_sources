# winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)

- ea: `0x18001176c`
- end: `0x180011833`
- name: `?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z`
- size: `199`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ffa0`
- `0x18000ffd0`
- `0x180010000`

## callees

- `0x1800033bc`
- `0x18000ce6c`
- `0x1800114dc`
- `0x18001176c`

## pseudocode

```c
__int64 __fastcall winrt::impl::implements_delegate_base::query_interface(
        winrt::impl::implements_delegate_base *a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4,
        _QWORD *a5)
{
  void *v8; // rcx
  __int64 v9; // rax

  if ( *a2 == *a5 && a2[1] == a5[1]
    || *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL
    || *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
  {
    *a3 = a4;
    winrt::impl::implements_delegate_base::increment_reference(a1);
    return 0;
  }
  else if ( *a2 == winrt::impl::guid_v<winrt::impl::IMarshal> && a2[1] == 0x46000000000000C0LL )
  {
    v8 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = 0;
    if ( v8 )
      v9 = `winrt::impl::make_marshaler'::`2'::marshaler::marshaler((__int64)v8, a4);
    *a3 = v9;
    return v9 == 0 ? 0x8007000E : 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18001176c  mov     [rsp+arg_0], rbx
0x180011771  push    rdi
0x180011772  sub     rsp, 20h
0x180011776  mov     rax, [rdx]
0x180011779  mov     rbx, r8
0x18001177c  mov     r8, [rsp+28h+arg_20]
0x180011781  mov     rdi, r9
0x180011784  cmp     rax, [r8]
0x180011787  jnz     short loc_180011793
0x180011789  mov     rax, [rdx+8]
0x18001178d  cmp     rax, [r8+8]
0x180011791  jz      short loc_1800117C5
0x180011793  mov     rax, [rdx]
0x180011796  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18001179d  jnz     short loc_1800117AC
0x18001179f  mov     rax, [rdx+8]
0x1800117a3  cmp     rax, cs:qword_1800166F0
0x1800117aa  jz      short loc_1800117C5
0x1800117ac  mov     rax, [rdx]
0x1800117af  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800117b6  jnz     short loc_1800117D1
0x1800117b8  mov     rax, [rdx+8]
0x1800117bc  cmp     rax, cs:qword_180016700
0x1800117c3  jnz     short loc_1800117D1
0x1800117c5  mov     [rbx], rdi
0x1800117c8  call    ?increment_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::increment_reference(void)
0x1800117cd  xor     eax, eax
0x1800117cf  jmp     short loc_180011828
0x1800117d1  mov     rax, [rdx]
0x1800117d4  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x1800117db  jnz     short loc_18001181E
0x1800117dd  mov     rax, [rdx+8]
0x1800117e1  cmp     rax, cs:qword_180016710
0x1800117e8  jnz     short loc_18001181E
0x1800117ea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800117f1  mov     ecx, 20h ; ' '; unsigned __int64
0x1800117f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800117fb  mov     rcx, rax
0x1800117fe  xor     eax, eax
0x180011800  test    rcx, rcx
0x180011803  jz      short loc_18001180D
0x180011805  mov     rdx, rdi
0x180011808  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18001180d  mov     [rbx], rax
0x180011810  neg     rax
0x180011813  sbb     eax, eax
0x180011815  not     eax
0x180011817  and     eax, 8007000Eh
0x18001181c  jmp     short loc_180011828
0x18001181e  xor     eax, eax
0x180011820  mov     [rbx], rax
0x180011823  mov     eax, 80004002h
0x180011828  mov     rbx, [rsp+28h+arg_0]
0x18001182d  add     rsp, 20h
0x180011831  pop     rdi
0x180011832  retn
```
