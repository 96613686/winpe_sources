# winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180006c90`
- end: `0x180006f29`
- name: `?query_interface_common@?$root_implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `665`
- prototype: `__int64 __fastcall(volatile signed __int64 *, const void *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006550`
- `0x1800068f0`

## callees

- `0x180001dc0`
- `0x180006c90`
- `0x180006f30`
- `0x1800072dc`
- `0x18000b930`
- `0x18000c3f0`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::query_interface_common(
        volatile signed __int64 *a1,
        const void *a2,
        __int64 *a3)
{
  signed __int64 v6; // rax
  signed __int64 v7; // rtt
  __int64 result; // rax
  signed __int64 v9; // rtt
  signed __int64 v10; // rdi
  __int64 v11; // rdi
  unsigned __int64 v12; // rsi
  __int64 v13; // rax
  bool v14; // zf
  __int64 v15; // rax
  signed __int64 v16; // rtt
  int v17; // eax
  volatile signed __int64 v18; // r9
  __int64 v19; // rax
  unsigned __int64 v20; // [rsp+20h] [rbp-38h] BYREF

  if ( !memcmp(a2, &winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>, 0x10u) )
  {
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
    v6 = *((_QWORD *)a1 + 1);
    if ( v6 >= 0 )
    {
      while ( 1 )
      {
        v7 = v6;
        v6 = _InterlockedCompareExchange64(a1 + 1, v6 + 1, v6);
        if ( v7 == v6 )
          return 0;
        if ( v6 < 0 )
          goto LABEL_5;
      }
    }
LABEL_29:
    _InterlockedIncrement((volatile signed __int32 *)(2 * v6 + 24));
    return 0;
  }
  if ( !memcmp(a2, winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>, 0x10u) )
  {
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 56))(a1);
    v6 = *((_QWORD *)a1 + 1);
    if ( v6 >= 0 )
    {
      while ( 1 )
      {
        v9 = v6;
        v6 = _InterlockedCompareExchange64(a1 + 1, v6 + 1, v6);
        if ( v9 == v6 )
          break;
        if ( v6 < 0 )
        {
LABEL_5:
          _InterlockedIncrement((volatile signed __int32 *)(2 * v6 + 24));
          return 0;
        }
      }
      return 0;
    }
    goto LABEL_29;
  }
  if ( !memcmp(a2, &winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>, 0x10u) )
  {
    v10 = *((_QWORD *)a1 + 1);
    if ( v10 >= 0 )
    {
      v12 = (unsigned __int64)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
      if ( v12 )
      {
        v13 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v20 = v12;
        *(_QWORD *)(v12 + 8) = &winrt::impl::weak_source<1,1>::`vftable';
        *(_QWORD *)v12 = &winrt::impl::weak_ref<1,1>::`vftable';
        *(_QWORD *)(v12 + 16) = v13;
        *(_DWORD *)(v12 + 24) = v10;
        *(_DWORD *)(v12 + 28) = 1;
        while ( 1 )
        {
          v15 = _InterlockedCompareExchange64(a1 + 1, (v12 >> 1) | 0x8000000000000000uLL, v10);
          v14 = v10 == v15;
          v10 = v15;
          if ( v14 )
            break;
          if ( v15 < 0 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(2 * v15 + 24));
            winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(&v20);
            v11 = 2 * v10 + 8;
            goto LABEL_22;
          }
          _InterlockedExchange((volatile __int32 *)(v12 + 24), v15);
        }
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 24));
        v11 = v12 + 8;
      }
      else
      {
        v11 = 0;
      }
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(2 * v10 + 24));
      v11 = 2 * v10 + 8;
    }
LABEL_22:
    *a3 = v11;
    result = 2147942414LL;
    if ( v11 )
      return 0;
  }
  else
  {
    if ( !memcmp(a2, &winrt::impl::guid_v<winrt::impl::IAgileObject>, 0x10u) )
    {
      *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
      v6 = *((_QWORD *)a1 + 1);
      if ( v6 >= 0 )
      {
        while ( 1 )
        {
          v16 = v6;
          v6 = _InterlockedCompareExchange64(a1 + 1, v6 + 1, v6);
          if ( v16 == v6 )
            return 0;
          if ( v6 < 0 )
            goto LABEL_29;
        }
      }
      goto LABEL_29;
    }
    v17 = memcmp(a2, &winrt::impl::guid_v<winrt::impl::IMarshal>, 0x10u);
    v18 = *a1;
    if ( v17 )
    {
      return (*(__int64 (__fastcall **)(volatile signed __int64 *, const void *, __int64 *))v18)(a1, a2, a3);
    }
    else
    {
      v19 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(v18 + 24))(a1);
      return winrt::impl::make_marshaler(v19, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006c90  push    rbx
0x180006c92  push    rdi
0x180006c93  push    r14
0x180006c95  sub     rsp, 40h
0x180006c99  mov     rdi, rdx
0x180006c9c  mov     r14, r8
0x180006c9f  mov     rbx, rcx
0x180006ca2  lea     rdx, ??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x180006ca9  mov     rcx, rdi; Buf1
0x180006cac  mov     r8d, 10h; Size
0x180006cb2  call    memcmp
0x180006cb7  test    eax, eax
0x180006cb9  jnz     short loc_180006D05
0x180006cbb  mov     rax, [rbx]
0x180006cbe  mov     rcx, rbx
0x180006cc1  mov     rax, [rax+18h]
0x180006cc5  call    cs:__guard_dispatch_icall_fptr
0x180006ccb  mov     [r14], rax
0x180006cce  mov     rax, [rbx+8]
0x180006cd2  test    rax, rax
0x180006cd5  js      loc_180006EC5
0x180006cdb  nop     dword ptr [rax+rax+00h]
0x180006ce0  lea     rcx, [rax+1]
0x180006ce4  lock cmpxchg [rbx+8], rcx
0x180006cea  jz      loc_180006ECA
0x180006cf0  test    rax, rax
0x180006cf3  jns     short loc_180006CE0
0x180006cf5  lock inc dword ptr [rax+rax+18h]
0x180006cfa  xor     eax, eax
0x180006cfc  add     rsp, 40h
0x180006d00  pop     r14
0x180006d02  pop     rdi
0x180006d03  pop     rbx
0x180006d04  retn
0x180006d05  mov     r8d, 10h; Size
0x180006d0b  lea     rdx, ??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x180006d12  mov     rcx, rdi; Buf1
0x180006d15  call    memcmp
0x180006d1a  test    eax, eax
0x180006d1c  jnz     short loc_180006D65
0x180006d1e  mov     rax, [rbx]
0x180006d21  mov     rcx, rbx
0x180006d24  mov     rax, [rax+38h]
0x180006d28  call    cs:__guard_dispatch_icall_fptr
0x180006d2e  mov     [r14], rax
0x180006d31  mov     rax, [rbx+8]
0x180006d35  test    rax, rax
0x180006d38  js      loc_180006EC5
0x180006d3e  xchg    ax, ax
0x180006d40  lea     rcx, [rax+1]
0x180006d44  lock cmpxchg [rbx+8], rcx
0x180006d4a  jz      loc_180006ECA
0x180006d50  test    rax, rax
0x180006d53  jns     short loc_180006D40
0x180006d55  lock inc dword ptr [rax+rax+18h]
0x180006d5a  xor     eax, eax
0x180006d5c  add     rsp, 40h
0x180006d60  pop     r14
0x180006d62  pop     rdi
0x180006d63  pop     rbx
0x180006d64  retn
0x180006d65  mov     r8d, 10h; Size
0x180006d6b  lea     rdx, ??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x180006d72  mov     rcx, rdi; Buf1
0x180006d75  call    memcmp
0x180006d7a  test    eax, eax
0x180006d7c  jnz     loc_180006E7F
0x180006d82  mov     rdi, [rbx+8]
0x180006d86  mov     [rsp+58h+var_20], rbp
0x180006d8b  xor     ebp, ebp
0x180006d8d  test    rdi, rdi
0x180006d90  jns     short loc_180006DA4
0x180006d92  lock inc dword ptr [rdi+rdi+18h]
0x180006d97  lea     rdi, ds:8[rdi*2]
0x180006d9f  jmp     loc_180006E63
0x180006da4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006dab  mov     [rsp+58h+var_28], rsi
0x180006db0  mov     ecx, 20h ; ' '; unsigned __int64
0x180006db5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006dba  mov     rsi, rax
0x180006dbd  test    rax, rax
0x180006dc0  jz      loc_180006E5B
0x180006dc6  mov     rcx, [rbx]
0x180006dc9  mov     rax, [rcx+18h]
0x180006dcd  mov     rcx, rbx
0x180006dd0  call    cs:__guard_dispatch_icall_fptr
0x180006dd6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006ddd  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x180006de4  mov     [rsp+58h+var_38], rsi
0x180006de9  mov     [rsi+8], rcx
0x180006ded  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x180006df4  mov     [rsi], rcx
0x180006df7  mov     rcx, rsi
0x180006dfa  mov     [rsi+10h], rax
0x180006dfe  mov     rax, 8000000000000000h
0x180006e08  shr     rcx, 1
0x180006e0b  or      rcx, rax
0x180006e0e  mov     [rsi+18h], edi
0x180006e11  mov     dword ptr [rsi+1Ch], 1
0x180006e18  nop     dword ptr [rax+rax+00000000h]
0x180006e20  mov     rax, rdi
0x180006e23  lock cmpxchg [rbx+8], rcx
0x180006e29  mov     rdi, rax
0x180006e2c  jz      short loc_180006E51
0x180006e2e  test    rax, rax
0x180006e31  js      short loc_180006E38
0x180006e33  xchg    eax, [rsi+18h]
0x180006e36  jmp     short loc_180006E20
0x180006e38  lock inc dword ptr [rax+rax+18h]
0x180006e3d  lea     rcx, [rsp+58h+var_38]
0x180006e42  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x180006e47  lea     rdi, ds:8[rdi*2]
0x180006e4f  jmp     short loc_180006E5E
0x180006e51  lock inc dword ptr [rsi+18h]
0x180006e55  lea     rdi, [rsi+8]
0x180006e59  jmp     short loc_180006E5E
0x180006e5b  mov     rdi, rbp
0x180006e5e  mov     rsi, [rsp+58h+var_28]
0x180006e63  test    rdi, rdi
0x180006e66  mov     [r14], rdi
0x180006e69  mov     eax, 8007000Eh
0x180006e6e  cmovnz  eax, ebp
0x180006e71  mov     rbp, [rsp+58h+var_20]
0x180006e76  add     rsp, 40h
0x180006e7a  pop     r14
0x180006e7c  pop     rdi
0x180006e7d  pop     rbx
0x180006e7e  retn
0x180006e7f  mov     r8d, 10h; Size
0x180006e85  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x180006e8c  mov     rcx, rdi; Buf1
0x180006e8f  call    memcmp
0x180006e94  test    eax, eax
0x180006e96  jnz     short loc_180006ED5
0x180006e98  mov     rax, [rbx]
0x180006e9b  mov     rcx, rbx
0x180006e9e  mov     rax, [rax+18h]
0x180006ea2  call    cs:__guard_dispatch_icall_fptr
0x180006ea8  mov     [r14], rax
0x180006eab  mov     rax, [rbx+8]
0x180006eaf  test    rax, rax
0x180006eb2  js      short loc_180006EC5
0x180006eb4  lea     rcx, [rax+1]
0x180006eb8  lock cmpxchg [rbx+8], rcx
0x180006ebe  jz      short loc_180006ECA
0x180006ec0  test    rax, rax
0x180006ec3  jns     short loc_180006EB4
0x180006ec5  lock inc dword ptr [rax+rax+18h]
0x180006eca  xor     eax, eax
0x180006ecc  add     rsp, 40h
0x180006ed0  pop     r14
0x180006ed2  pop     rdi
0x180006ed3  pop     rbx
0x180006ed4  retn
0x180006ed5  mov     r8d, 10h; Size
0x180006edb  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x180006ee2  mov     rcx, rdi; Buf1
0x180006ee5  call    memcmp
0x180006eea  mov     r9, [rbx]
0x180006eed  mov     rcx, rbx
0x180006ef0  test    eax, eax
0x180006ef2  jnz     short loc_180006F11
0x180006ef4  mov     rax, [r9+18h]
0x180006ef8  call    cs:__guard_dispatch_icall_fptr
0x180006efe  mov     rcx, rax
0x180006f01  mov     rdx, r14
0x180006f04  add     rsp, 40h
0x180006f08  pop     r14
0x180006f0a  pop     rdi
0x180006f0b  pop     rbx
0x180006f0c  jmp     ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x180006f11  mov     rax, [r9]
0x180006f14  mov     r8, r14
0x180006f17  mov     rdx, rdi
0x180006f1a  add     rsp, 40h
0x180006f1e  pop     r14
0x180006f20  pop     rdi
0x180006f21  pop     rbx
0x180006f22  jmp     cs:__guard_dispatch_icall_fptr
```
