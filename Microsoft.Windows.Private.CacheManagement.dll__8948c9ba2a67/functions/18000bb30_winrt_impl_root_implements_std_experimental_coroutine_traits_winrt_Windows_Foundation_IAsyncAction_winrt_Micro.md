# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000bb30`
- end: `0x18000bdc9`
- name: `?query_interface_common@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `665`
- prototype: `__int64 __fastcall(volatile signed __int64 *, const void *, __int64 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005200`
- `0x1800087b0`
- `0x180008ad0`
- `0x180009d60`

## callees

- `0x18000bb30`
- `0x18000c050`
- `0x18000e5e0`
- `0x1800185b0`
- `0x18001cdf0`
- `0x18001ce40`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(
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
      v12 = (unsigned __int64)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
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
0x18000bb30  push    rbx
0x18000bb32  push    rdi
0x18000bb33  push    r14
0x18000bb35  sub     rsp, 40h
0x18000bb39  mov     rdi, rdx
0x18000bb3c  mov     r14, r8
0x18000bb3f  mov     rbx, rcx
0x18000bb42  lea     rdx, ??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000bb49  mov     rcx, rdi; Buf1
0x18000bb4c  mov     r8d, 10h; Size
0x18000bb52  call    memcmp
0x18000bb57  test    eax, eax
0x18000bb59  jnz     short loc_18000BBA5
0x18000bb5b  mov     rax, [rbx]
0x18000bb5e  mov     rcx, rbx
0x18000bb61  mov     rax, [rax+18h]
0x18000bb65  call    cs:__guard_dispatch_icall_fptr
0x18000bb6b  mov     [r14], rax
0x18000bb6e  mov     rax, [rbx+8]
0x18000bb72  test    rax, rax
0x18000bb75  js      loc_18000BD65
0x18000bb7b  nop     dword ptr [rax+rax+00h]
0x18000bb80  lea     rcx, [rax+1]
0x18000bb84  lock cmpxchg [rbx+8], rcx
0x18000bb8a  jz      loc_18000BD6A
0x18000bb90  test    rax, rax
0x18000bb93  jns     short loc_18000BB80
0x18000bb95  lock inc dword ptr [rax+rax+18h]
0x18000bb9a  xor     eax, eax
0x18000bb9c  add     rsp, 40h
0x18000bba0  pop     r14
0x18000bba2  pop     rdi
0x18000bba3  pop     rbx
0x18000bba4  retn
0x18000bba5  mov     r8d, 10h; Size
0x18000bbab  lea     rdx, ??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000bbb2  mov     rcx, rdi; Buf1
0x18000bbb5  call    memcmp
0x18000bbba  test    eax, eax
0x18000bbbc  jnz     short loc_18000BC05
0x18000bbbe  mov     rax, [rbx]
0x18000bbc1  mov     rcx, rbx
0x18000bbc4  mov     rax, [rax+38h]
0x18000bbc8  call    cs:__guard_dispatch_icall_fptr
0x18000bbce  mov     [r14], rax
0x18000bbd1  mov     rax, [rbx+8]
0x18000bbd5  test    rax, rax
0x18000bbd8  js      loc_18000BD65
0x18000bbde  xchg    ax, ax
0x18000bbe0  lea     rcx, [rax+1]
0x18000bbe4  lock cmpxchg [rbx+8], rcx
0x18000bbea  jz      loc_18000BD6A
0x18000bbf0  test    rax, rax
0x18000bbf3  jns     short loc_18000BBE0
0x18000bbf5  lock inc dword ptr [rax+rax+18h]
0x18000bbfa  xor     eax, eax
0x18000bbfc  add     rsp, 40h
0x18000bc00  pop     r14
0x18000bc02  pop     rdi
0x18000bc03  pop     rbx
0x18000bc04  retn
0x18000bc05  mov     r8d, 10h; Size
0x18000bc0b  lea     rdx, ??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000bc12  mov     rcx, rdi; Buf1
0x18000bc15  call    memcmp
0x18000bc1a  test    eax, eax
0x18000bc1c  jnz     loc_18000BD1F
0x18000bc22  mov     rdi, [rbx+8]
0x18000bc26  mov     [rsp+58h+var_20], rbp
0x18000bc2b  xor     ebp, ebp
0x18000bc2d  test    rdi, rdi
0x18000bc30  jns     short loc_18000BC44
0x18000bc32  lock inc dword ptr [rdi+rdi+18h]
0x18000bc37  lea     rdi, ds:8[rdi*2]
0x18000bc3f  jmp     loc_18000BD03
0x18000bc44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bc4b  mov     [rsp+58h+var_28], rsi
0x18000bc50  mov     ecx, 20h ; ' '; unsigned __int64
0x18000bc55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bc5a  mov     rsi, rax
0x18000bc5d  test    rax, rax
0x18000bc60  jz      loc_18000BCFB
0x18000bc66  mov     rcx, [rbx]
0x18000bc69  mov     rax, [rcx+18h]
0x18000bc6d  mov     rcx, rbx
0x18000bc70  call    cs:__guard_dispatch_icall_fptr
0x18000bc76  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000bc7d  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x18000bc84  mov     [rsp+58h+var_38], rsi
0x18000bc89  mov     [rsi+8], rcx
0x18000bc8d  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x18000bc94  mov     [rsi], rcx
0x18000bc97  mov     rcx, rsi
0x18000bc9a  mov     [rsi+10h], rax
0x18000bc9e  mov     rax, 8000000000000000h
0x18000bca8  shr     rcx, 1
0x18000bcab  or      rcx, rax
0x18000bcae  mov     [rsi+18h], edi
0x18000bcb1  mov     dword ptr [rsi+1Ch], 1
0x18000bcb8  nop     dword ptr [rax+rax+00000000h]
0x18000bcc0  mov     rax, rdi
0x18000bcc3  lock cmpxchg [rbx+8], rcx
0x18000bcc9  mov     rdi, rax
0x18000bccc  jz      short loc_18000BCF1
0x18000bcce  test    rax, rax
0x18000bcd1  js      short loc_18000BCD8
0x18000bcd3  xchg    eax, [rsi+18h]
0x18000bcd6  jmp     short loc_18000BCC0
0x18000bcd8  lock inc dword ptr [rax+rax+18h]
0x18000bcdd  lea     rcx, [rsp+58h+var_38]
0x18000bce2  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x18000bce7  lea     rdi, ds:8[rdi*2]
0x18000bcef  jmp     short loc_18000BCFE
0x18000bcf1  lock inc dword ptr [rsi+18h]
0x18000bcf5  lea     rdi, [rsi+8]
0x18000bcf9  jmp     short loc_18000BCFE
0x18000bcfb  mov     rdi, rbp
0x18000bcfe  mov     rsi, [rsp+58h+var_28]
0x18000bd03  test    rdi, rdi
0x18000bd06  mov     [r14], rdi
0x18000bd09  mov     eax, 8007000Eh
0x18000bd0e  cmovnz  eax, ebp
0x18000bd11  mov     rbp, [rsp+58h+var_20]
0x18000bd16  add     rsp, 40h
0x18000bd1a  pop     r14
0x18000bd1c  pop     rdi
0x18000bd1d  pop     rbx
0x18000bd1e  retn
0x18000bd1f  mov     r8d, 10h; Size
0x18000bd25  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000bd2c  mov     rcx, rdi; Buf1
0x18000bd2f  call    memcmp
0x18000bd34  test    eax, eax
0x18000bd36  jnz     short loc_18000BD75
0x18000bd38  mov     rax, [rbx]
0x18000bd3b  mov     rcx, rbx
0x18000bd3e  mov     rax, [rax+18h]
0x18000bd42  call    cs:__guard_dispatch_icall_fptr
0x18000bd48  mov     [r14], rax
0x18000bd4b  mov     rax, [rbx+8]
0x18000bd4f  test    rax, rax
0x18000bd52  js      short loc_18000BD65
0x18000bd54  lea     rcx, [rax+1]
0x18000bd58  lock cmpxchg [rbx+8], rcx
0x18000bd5e  jz      short loc_18000BD6A
0x18000bd60  test    rax, rax
0x18000bd63  jns     short loc_18000BD54
0x18000bd65  lock inc dword ptr [rax+rax+18h]
0x18000bd6a  xor     eax, eax
0x18000bd6c  add     rsp, 40h
0x18000bd70  pop     r14
0x18000bd72  pop     rdi
0x18000bd73  pop     rbx
0x18000bd74  retn
0x18000bd75  mov     r8d, 10h; Size
0x18000bd7b  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000bd82  mov     rcx, rdi; Buf1
0x18000bd85  call    memcmp
0x18000bd8a  mov     r9, [rbx]
0x18000bd8d  mov     rcx, rbx
0x18000bd90  test    eax, eax
0x18000bd92  jnz     short loc_18000BDB1
0x18000bd94  mov     rax, [r9+18h]
0x18000bd98  call    cs:__guard_dispatch_icall_fptr
0x18000bd9e  mov     rcx, rax
0x18000bda1  mov     rdx, r14
0x18000bda4  add     rsp, 40h
0x18000bda8  pop     r14
0x18000bdaa  pop     rdi
0x18000bdab  pop     rbx
0x18000bdac  jmp     ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x18000bdb1  mov     rax, [r9]
0x18000bdb4  mov     r8, r14
0x18000bdb7  mov     rdx, rdi
0x18000bdba  add     rsp, 40h
0x18000bdbe  pop     r14
0x18000bdc0  pop     rdi
0x18000bdc1  pop     rbx
0x18000bdc2  jmp     cs:__guard_dispatch_icall_fptr
```
