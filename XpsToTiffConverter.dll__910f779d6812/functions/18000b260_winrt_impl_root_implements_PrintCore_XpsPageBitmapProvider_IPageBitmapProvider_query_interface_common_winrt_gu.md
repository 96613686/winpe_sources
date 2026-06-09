# winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000b260`
- end: `0x18000b398`
- name: `?query_interface_common@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a440`

## callees

- `0x180001af0`
- `0x180009ae0`
- `0x18000b16c`
- `0x18000b260`
- `0x18000e010`

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
0x18000b260  mov     [rsp+arg_0], rbx
0x18000b265  push    rdi
0x18000b266  sub     rsp, 20h
0x18000b26a  mov     rax, [rdx]
0x18000b26d  mov     rdi, r8
0x18000b270  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000b277  mov     rbx, rcx
0x18000b27a  jnz     short loc_18000B2AF
0x18000b27c  mov     rax, [rdx+8]
0x18000b280  cmp     rax, cs:qword_180010270
0x18000b287  jnz     short loc_18000B2AF
0x18000b289  mov     rax, [rcx]
0x18000b28c  mov     rax, [rax+18h]
0x18000b290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b295  mov     [rdi], rax
0x18000b298  mov     rax, [rbx+8]
0x18000b29c  test    rax, rax
0x18000b29f  js      short loc_18000B320
0x18000b2a1  lea     rcx, [rax+1]
0x18000b2a5  lock cmpxchg [rbx+8], rcx
0x18000b2ab  jnz     short loc_18000B29C
0x18000b2ad  jmp     short loc_18000B325
0x18000b2af  mov     rax, [rdx]
0x18000b2b2  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000b2b9  jnz     short loc_18000B2E1
0x18000b2bb  mov     rax, [rdx+8]
0x18000b2bf  cmp     rax, cs:qword_180010240
0x18000b2c6  jnz     short loc_18000B2E1
0x18000b2c8  call    ?make_weak_ref@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::make_weak_ref(void)
0x18000b2cd  mov     [rdi], rax
0x18000b2d0  neg     rax
0x18000b2d3  sbb     eax, eax
0x18000b2d5  not     eax
0x18000b2d7  and     eax, 8007000Eh
0x18000b2dc  jmp     loc_18000B38D
0x18000b2e1  mov     rax, [rdx]
0x18000b2e4  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000b2eb  jnz     short loc_18000B329
0x18000b2ed  mov     rax, [rdx+8]
0x18000b2f1  cmp     rax, cs:qword_180010260
0x18000b2f8  jnz     short loc_18000B329
0x18000b2fa  mov     rax, [rcx]
0x18000b2fd  mov     rax, [rax+18h]
0x18000b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b306  mov     [rdi], rax
0x18000b309  mov     rax, [rbx+8]
0x18000b30d  test    rax, rax
0x18000b310  js      short loc_18000B320
0x18000b312  lea     rcx, [rax+1]
0x18000b316  lock cmpxchg [rbx+8], rcx
0x18000b31c  jnz     short loc_18000B30D
0x18000b31e  jmp     short loc_18000B325
0x18000b320  lock inc dword ptr [rax+rax+18h]
0x18000b325  xor     eax, eax
0x18000b327  jmp     short loc_18000B38D
0x18000b329  mov     rax, [rdx]
0x18000b32c  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000b333  jnz     short loc_18000B382
0x18000b335  mov     rax, [rdx+8]
0x18000b339  cmp     rax, cs:qword_180010250
0x18000b340  jnz     short loc_18000B382
0x18000b342  mov     rax, [rcx]
0x18000b345  mov     rax, [rax+18h]
0x18000b349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b34e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b355  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b35a  mov     rbx, rax
0x18000b35d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b362  xor     edx, edx
0x18000b364  test    rax, rax
0x18000b367  jz      short loc_18000B377
0x18000b369  mov     rdx, rbx
0x18000b36c  mov     rcx, rax
0x18000b36f  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18000b374  mov     rdx, rax
0x18000b377  mov     [rdi], rdx
0x18000b37a  neg     rdx
0x18000b37d  jmp     loc_18000B2D3
0x18000b382  mov     rax, [rcx]
0x18000b385  mov     rax, [rax]
0x18000b388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38d  mov     rbx, [rsp+28h+arg_0]
0x18000b392  add     rsp, 20h
0x18000b396  pop     rdi
0x18000b397  retn
```
