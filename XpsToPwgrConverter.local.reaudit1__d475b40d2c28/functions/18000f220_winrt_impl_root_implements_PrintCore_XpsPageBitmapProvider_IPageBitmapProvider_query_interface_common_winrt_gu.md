# winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000f220`
- end: `0x18000f358`
- name: `?query_interface_common@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ec20`

## callees

- `0x180001b6c`
- `0x18000df98`
- `0x18000f12c`
- `0x18000f220`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::query_interface_common(
        volatile signed __int64 *a1,
        _QWORD *a2,
        __int64 *a3)
{
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  __int64 weak_ref; // rax
  bool v8; // cf
  signed __int64 v10; // rtt
  __int64 v11; // rbx
  void *v12; // rax
  __int64 v13; // rdx

  if ( *a2 != winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> || a2[1] != 0x46000000000000C0LL )
  {
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
    {
      weak_ref = winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::make_weak_ref();
      *a3 = weak_ref;
      v8 = weak_ref != 0;
    }
    else
    {
      if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
      {
        *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
        v5 = *((_QWORD *)a1 + 1);
        while ( v5 >= 0 )
        {
          v10 = v5;
          v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
          if ( v10 == v5 )
            return 0;
        }
        goto LABEL_17;
      }
      if ( *a2 != winrt::impl::guid_v<winrt::impl::IMarshal> || a2[1] != 0x46000000000000C0LL )
        return (**(__int64 (__fastcall ***)(volatile signed __int64 *))a1)(a1);
      v11 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
      v12 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = 0;
      if ( v12 )
        v13 = `winrt::impl::make_marshaler'::`2'::marshaler::marshaler(v12, v11);
      *a3 = v13;
      v8 = v13 != 0;
    }
    return v8 ? 0 : 0x8007000E;
  }
  *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
  v5 = *((_QWORD *)a1 + 1);
  while ( v5 >= 0 )
  {
    v6 = v5;
    v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
    if ( v6 == v5 )
      return 0;
  }
LABEL_17:
  _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
  return 0;
}

```

## disassembly

```asm
0x18000f220  mov     [rsp+arg_0], rbx
0x18000f225  push    rdi
0x18000f226  sub     rsp, 20h
0x18000f22a  mov     rax, [rdx]
0x18000f22d  mov     rdi, r8
0x18000f230  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000f237  mov     rbx, rcx
0x18000f23a  jnz     short loc_18000F26F
0x18000f23c  mov     rax, [rdx+8]
0x18000f240  cmp     rax, cs:qword_180013B88
0x18000f247  jnz     short loc_18000F26F
0x18000f249  mov     rax, [rcx]
0x18000f24c  mov     rax, [rax+18h]
0x18000f250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f255  mov     [rdi], rax
0x18000f258  mov     rax, [rbx+8]
0x18000f25c  test    rax, rax
0x18000f25f  js      short loc_18000F2E0
0x18000f261  lea     rcx, [rax+1]
0x18000f265  lock cmpxchg [rbx+8], rcx
0x18000f26b  jnz     short loc_18000F25C
0x18000f26d  jmp     short loc_18000F2E5
0x18000f26f  mov     rax, [rdx]
0x18000f272  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000f279  jnz     short loc_18000F2A1
0x18000f27b  mov     rax, [rdx+8]
0x18000f27f  cmp     rax, cs:qword_180013B58
0x18000f286  jnz     short loc_18000F2A1
0x18000f288  call    ?make_weak_ref@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::make_weak_ref(void)
0x18000f28d  mov     [rdi], rax
0x18000f290  neg     rax
0x18000f293  sbb     eax, eax
0x18000f295  not     eax
0x18000f297  and     eax, 8007000Eh
0x18000f29c  jmp     loc_18000F34D
0x18000f2a1  mov     rax, [rdx]
0x18000f2a4  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f2ab  jnz     short loc_18000F2E9
0x18000f2ad  mov     rax, [rdx+8]
0x18000f2b1  cmp     rax, cs:qword_180013B78
0x18000f2b8  jnz     short loc_18000F2E9
0x18000f2ba  mov     rax, [rcx]
0x18000f2bd  mov     rax, [rax+18h]
0x18000f2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c6  mov     [rdi], rax
0x18000f2c9  mov     rax, [rbx+8]
0x18000f2cd  test    rax, rax
0x18000f2d0  js      short loc_18000F2E0
0x18000f2d2  lea     rcx, [rax+1]
0x18000f2d6  lock cmpxchg [rbx+8], rcx
0x18000f2dc  jnz     short loc_18000F2CD
0x18000f2de  jmp     short loc_18000F2E5
0x18000f2e0  lock inc dword ptr [rax+rax+18h]
0x18000f2e5  xor     eax, eax
0x18000f2e7  jmp     short loc_18000F34D
0x18000f2e9  mov     rax, [rdx]
0x18000f2ec  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000f2f3  jnz     short loc_18000F342
0x18000f2f5  mov     rax, [rdx+8]
0x18000f2f9  cmp     rax, cs:qword_180013B68
0x18000f300  jnz     short loc_18000F342
0x18000f302  mov     rax, [rcx]
0x18000f305  mov     rax, [rax+18h]
0x18000f309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f30e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f315  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f31a  mov     rbx, rax
0x18000f31d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f322  xor     edx, edx
0x18000f324  test    rax, rax
0x18000f327  jz      short loc_18000F337
0x18000f329  mov     rdx, rbx
0x18000f32c  mov     rcx, rax
0x18000f32f  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18000f334  mov     rdx, rax
0x18000f337  mov     [rdi], rdx
0x18000f33a  neg     rdx
0x18000f33d  jmp     loc_18000F293
0x18000f342  mov     rax, [rcx]
0x18000f345  mov     rax, [rax]
0x18000f348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f34d  mov     rbx, [rsp+28h+arg_0]
0x18000f352  add     rsp, 20h
0x18000f356  pop     rdi
0x18000f357  retn
```
