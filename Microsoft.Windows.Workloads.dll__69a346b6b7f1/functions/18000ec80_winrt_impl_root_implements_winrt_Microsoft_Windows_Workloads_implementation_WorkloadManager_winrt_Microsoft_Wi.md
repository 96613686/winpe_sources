# winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000ec80`
- end: `0x18000ef19`
- name: `?query_interface_common@?$root_implements@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@U13456@UIWorkloadManager2@3456@UIWorkloadManager3@3456@UIWorkloadManager4@3456@UIWorkloadManager5@3456@UIWorkloadManager6@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `665`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c650`
- `0x18000d160`
- `0x180018470`
- `0x180018730`
- `0x18001d320`
- `0x18002c4e0`
- `0x18002c5d0`

## callees

- `0x18000ec80`
- `0x18000f230`
- `0x1800107a0`
- `0x180035414`
- `0x18003bed0`
- `0x18003bf20`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(
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
0x18000ec80  push    rbx
0x18000ec82  push    rdi
0x18000ec83  push    r14
0x18000ec85  sub     rsp, 40h
0x18000ec89  mov     rdi, rdx
0x18000ec8c  mov     r14, r8
0x18000ec8f  mov     rbx, rcx
0x18000ec92  lea     rdx, ??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000ec99  mov     rcx, rdi; Buf1
0x18000ec9c  mov     r8d, 10h; Size
0x18000eca2  call    memcmp
0x18000eca7  test    eax, eax
0x18000eca9  jnz     short loc_18000ECF5
0x18000ecab  mov     rax, [rbx]
0x18000ecae  mov     rcx, rbx
0x18000ecb1  mov     rax, [rax+18h]
0x18000ecb5  call    cs:__guard_dispatch_icall_fptr
0x18000ecbb  mov     [r14], rax
0x18000ecbe  mov     rax, [rbx+8]
0x18000ecc2  test    rax, rax
0x18000ecc5  js      loc_18000EEB5
0x18000eccb  nop     dword ptr [rax+rax+00h]
0x18000ecd0  lea     rcx, [rax+1]
0x18000ecd4  lock cmpxchg [rbx+8], rcx
0x18000ecda  jz      loc_18000EEBA
0x18000ece0  test    rax, rax
0x18000ece3  jns     short loc_18000ECD0
0x18000ece5  lock inc dword ptr [rax+rax+18h]
0x18000ecea  xor     eax, eax
0x18000ecec  add     rsp, 40h
0x18000ecf0  pop     r14
0x18000ecf2  pop     rdi
0x18000ecf3  pop     rbx
0x18000ecf4  retn
0x18000ecf5  mov     r8d, 10h; Size
0x18000ecfb  lea     rdx, ??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000ed02  mov     rcx, rdi; Buf1
0x18000ed05  call    memcmp
0x18000ed0a  test    eax, eax
0x18000ed0c  jnz     short loc_18000ED55
0x18000ed0e  mov     rax, [rbx]
0x18000ed11  mov     rcx, rbx
0x18000ed14  mov     rax, [rax+38h]
0x18000ed18  call    cs:__guard_dispatch_icall_fptr
0x18000ed1e  mov     [r14], rax
0x18000ed21  mov     rax, [rbx+8]
0x18000ed25  test    rax, rax
0x18000ed28  js      loc_18000EEB5
0x18000ed2e  xchg    ax, ax
0x18000ed30  lea     rcx, [rax+1]
0x18000ed34  lock cmpxchg [rbx+8], rcx
0x18000ed3a  jz      loc_18000EEBA
0x18000ed40  test    rax, rax
0x18000ed43  jns     short loc_18000ED30
0x18000ed45  lock inc dword ptr [rax+rax+18h]
0x18000ed4a  xor     eax, eax
0x18000ed4c  add     rsp, 40h
0x18000ed50  pop     r14
0x18000ed52  pop     rdi
0x18000ed53  pop     rbx
0x18000ed54  retn
0x18000ed55  mov     r8d, 10h; Size
0x18000ed5b  lea     rdx, ??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000ed62  mov     rcx, rdi; Buf1
0x18000ed65  call    memcmp
0x18000ed6a  test    eax, eax
0x18000ed6c  jnz     loc_18000EE6F
0x18000ed72  mov     rdi, [rbx+8]
0x18000ed76  mov     [rsp+58h+var_20], rbp
0x18000ed7b  xor     ebp, ebp
0x18000ed7d  test    rdi, rdi
0x18000ed80  jns     short loc_18000ED94
0x18000ed82  lock inc dword ptr [rdi+rdi+18h]
0x18000ed87  lea     rdi, ds:8[rdi*2]
0x18000ed8f  jmp     loc_18000EE53
0x18000ed94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ed9b  mov     [rsp+58h+var_28], rsi
0x18000eda0  mov     ecx, 20h ; ' '; unsigned __int64
0x18000eda5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000edaa  mov     rsi, rax
0x18000edad  test    rax, rax
0x18000edb0  jz      loc_18000EE4B
0x18000edb6  mov     rcx, [rbx]
0x18000edb9  mov     rax, [rcx+18h]
0x18000edbd  mov     rcx, rbx
0x18000edc0  call    cs:__guard_dispatch_icall_fptr
0x18000edc6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000edcd  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x18000edd4  mov     [rsp+58h+var_38], rsi
0x18000edd9  mov     [rsi+8], rcx
0x18000eddd  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x18000ede4  mov     [rsi], rcx
0x18000ede7  mov     rcx, rsi
0x18000edea  mov     [rsi+10h], rax
0x18000edee  mov     rax, 8000000000000000h
0x18000edf8  shr     rcx, 1
0x18000edfb  or      rcx, rax
0x18000edfe  mov     [rsi+18h], edi
0x18000ee01  mov     dword ptr [rsi+1Ch], 1
0x18000ee08  nop     dword ptr [rax+rax+00000000h]
0x18000ee10  mov     rax, rdi
0x18000ee13  lock cmpxchg [rbx+8], rcx
0x18000ee19  mov     rdi, rax
0x18000ee1c  jz      short loc_18000EE41
0x18000ee1e  test    rax, rax
0x18000ee21  js      short loc_18000EE28
0x18000ee23  xchg    eax, [rsi+18h]
0x18000ee26  jmp     short loc_18000EE10
0x18000ee28  lock inc dword ptr [rax+rax+18h]
0x18000ee2d  lea     rcx, [rsp+58h+var_38]
0x18000ee32  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x18000ee37  lea     rdi, ds:8[rdi*2]
0x18000ee3f  jmp     short loc_18000EE4E
0x18000ee41  lock inc dword ptr [rsi+18h]
0x18000ee45  lea     rdi, [rsi+8]
0x18000ee49  jmp     short loc_18000EE4E
0x18000ee4b  mov     rdi, rbp
0x18000ee4e  mov     rsi, [rsp+58h+var_28]
0x18000ee53  test    rdi, rdi
0x18000ee56  mov     [r14], rdi
0x18000ee59  mov     eax, 8007000Eh
0x18000ee5e  cmovnz  eax, ebp
0x18000ee61  mov     rbp, [rsp+58h+var_20]
0x18000ee66  add     rsp, 40h
0x18000ee6a  pop     r14
0x18000ee6c  pop     rdi
0x18000ee6d  pop     rbx
0x18000ee6e  retn
0x18000ee6f  mov     r8d, 10h; Size
0x18000ee75  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000ee7c  mov     rcx, rdi; Buf1
0x18000ee7f  call    memcmp
0x18000ee84  test    eax, eax
0x18000ee86  jnz     short loc_18000EEC5
0x18000ee88  mov     rax, [rbx]
0x18000ee8b  mov     rcx, rbx
0x18000ee8e  mov     rax, [rax+18h]
0x18000ee92  call    cs:__guard_dispatch_icall_fptr
0x18000ee98  mov     [r14], rax
0x18000ee9b  mov     rax, [rbx+8]
0x18000ee9f  test    rax, rax
0x18000eea2  js      short loc_18000EEB5
0x18000eea4  lea     rcx, [rax+1]
0x18000eea8  lock cmpxchg [rbx+8], rcx
0x18000eeae  jz      short loc_18000EEBA
0x18000eeb0  test    rax, rax
0x18000eeb3  jns     short loc_18000EEA4
0x18000eeb5  lock inc dword ptr [rax+rax+18h]
0x18000eeba  xor     eax, eax
0x18000eebc  add     rsp, 40h
0x18000eec0  pop     r14
0x18000eec2  pop     rdi
0x18000eec3  pop     rbx
0x18000eec4  retn
0x18000eec5  mov     r8d, 10h; Size
0x18000eecb  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000eed2  mov     rcx, rdi; Buf1
0x18000eed5  call    memcmp
0x18000eeda  mov     r9, [rbx]
0x18000eedd  mov     rcx, rbx
0x18000eee0  test    eax, eax
0x18000eee2  jnz     short loc_18000EF01
0x18000eee4  mov     rax, [r9+18h]
0x18000eee8  call    cs:__guard_dispatch_icall_fptr
0x18000eeee  mov     rcx, rax
0x18000eef1  mov     rdx, r14
0x18000eef4  add     rsp, 40h
0x18000eef8  pop     r14
0x18000eefa  pop     rdi
0x18000eefb  pop     rbx
0x18000eefc  jmp     ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x18000ef01  mov     rax, [r9]
0x18000ef04  mov     r8, r14
0x18000ef07  mov     rdx, rdi
0x18000ef0a  add     rsp, 40h
0x18000ef0e  pop     r14
0x18000ef10  pop     rdi
0x18000ef11  pop     rbx
0x18000ef12  jmp     cs:__guard_dispatch_icall_fptr
```
