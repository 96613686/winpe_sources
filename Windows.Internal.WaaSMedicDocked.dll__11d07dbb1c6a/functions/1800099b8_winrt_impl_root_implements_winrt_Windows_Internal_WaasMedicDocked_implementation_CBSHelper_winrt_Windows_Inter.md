# winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::CBSHelper>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x1800099b8`
- end: `0x180009b36`
- name: `?query_interface_common@?$root_implements@VCBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@U13456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008a30`
- `0x180008ad0`
- `0x180008b70`

## callees

- `0x1800019c0`
- `0x1800066b8`
- `0x180009558`
- `0x1800099b8`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::CBSHelper>::query_interface_common(
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
        weak_ref = winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::CBSHelper>::make_weak_ref();
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
0x1800099b8  mov     [rsp+arg_0], rbx
0x1800099bd  push    rdi
0x1800099be  sub     rsp, 20h
0x1800099c2  mov     rax, [rdx]
0x1800099c5  mov     rdi, r8
0x1800099c8  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x1800099cf  mov     rbx, rcx
0x1800099d2  jnz     short loc_180009A0E
0x1800099d4  mov     rax, [rdx+8]
0x1800099d8  cmp     rax, cs:qword_18000F4C0
0x1800099df  jnz     short loc_180009A0E
0x1800099e1  mov     rax, [rcx]
0x1800099e4  mov     rax, [rax+18h]
0x1800099e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ed  mov     [rdi], rax
0x1800099f0  mov     rax, [rbx+8]
0x1800099f4  test    rax, rax
0x1800099f7  js      loc_180009ABE
0x1800099fd  lea     rcx, [rax+1]
0x180009a01  lock cmpxchg [rbx+8], rcx
0x180009a07  jnz     short loc_1800099F4
0x180009a09  jmp     loc_180009AC3
0x180009a0e  mov     rax, [rdx]
0x180009a11  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180009a18  jnz     short loc_180009A4D
0x180009a1a  mov     rax, [rdx+8]
0x180009a1e  cmp     rax, cs:qword_18000F470
0x180009a25  jnz     short loc_180009A4D
0x180009a27  mov     rax, [rcx]
0x180009a2a  mov     rax, [rax+38h]
0x180009a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a33  mov     [rdi], rax
0x180009a36  mov     rax, [rbx+8]
0x180009a3a  test    rax, rax
0x180009a3d  js      short loc_180009ABE
0x180009a3f  lea     rcx, [rax+1]
0x180009a43  lock cmpxchg [rbx+8], rcx
0x180009a49  jnz     short loc_180009A3A
0x180009a4b  jmp     short loc_180009AC3
0x180009a4d  mov     rax, [rdx]
0x180009a50  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x180009a57  jnz     short loc_180009A7F
0x180009a59  mov     rax, [rdx+8]
0x180009a5d  cmp     rax, cs:qword_18000F490
0x180009a64  jnz     short loc_180009A7F
0x180009a66  call    ?make_weak_ref@?$root_implements@VCBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@U13456@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper,winrt::Windows::Internal::WaasMedicDocked::CBSHelper>::make_weak_ref(void)
0x180009a6b  mov     [rdi], rax
0x180009a6e  neg     rax
0x180009a71  sbb     eax, eax
0x180009a73  not     eax
0x180009a75  and     eax, 8007000Eh
0x180009a7a  jmp     loc_180009B2B
0x180009a7f  mov     rax, [rdx]
0x180009a82  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180009a89  jnz     short loc_180009AC7
0x180009a8b  mov     rax, [rdx+8]
0x180009a8f  cmp     rax, cs:qword_18000F4D0
0x180009a96  jnz     short loc_180009AC7
0x180009a98  mov     rax, [rcx]
0x180009a9b  mov     rax, [rax+18h]
0x180009a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa4  mov     [rdi], rax
0x180009aa7  mov     rax, [rbx+8]
0x180009aab  test    rax, rax
0x180009aae  js      short loc_180009ABE
0x180009ab0  lea     rcx, [rax+1]
0x180009ab4  lock cmpxchg [rbx+8], rcx
0x180009aba  jnz     short loc_180009AAB
0x180009abc  jmp     short loc_180009AC3
0x180009abe  lock inc dword ptr [rax+rax+18h]
0x180009ac3  xor     eax, eax
0x180009ac5  jmp     short loc_180009B2B
0x180009ac7  mov     rax, [rdx]
0x180009aca  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180009ad1  jnz     short loc_180009B20
0x180009ad3  mov     rax, [rdx+8]
0x180009ad7  cmp     rax, cs:qword_18000F4B0
0x180009ade  jnz     short loc_180009B20
0x180009ae0  mov     rax, [rcx]
0x180009ae3  mov     rax, [rax+18h]
0x180009ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009af3  mov     ecx, 20h ; ' '; unsigned __int64
0x180009af8  mov     rbx, rax
0x180009afb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b00  xor     edx, edx
0x180009b02  test    rax, rax
0x180009b05  jz      short loc_180009B15
0x180009b07  mov     rdx, rbx
0x180009b0a  mov     rcx, rax
0x180009b0d  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180009b12  mov     rdx, rax
0x180009b15  mov     [rdi], rdx
0x180009b18  neg     rdx
0x180009b1b  jmp     loc_180009A71
0x180009b20  mov     rax, [rcx]
0x180009b23  mov     rax, [rax]
0x180009b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b2b  mov     rbx, [rsp+28h+arg_0]
0x180009b30  add     rsp, 20h
0x180009b34  pop     rdi
0x180009b35  retn
```
