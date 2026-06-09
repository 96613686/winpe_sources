# winrt::impl::root_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000d310`
- end: `0x18000d48e`
- name: `?query_interface_common@?$root_implements@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@UITranscodeWallpaperStatics@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(volatile signed __int64 *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c950`

## callees

- `0x1800025a0`
- `0x18000c14c`
- `0x18000d13c`
- `0x18000d310`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::query_interface_common(
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
        weak_ref = winrt::impl::root_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::make_weak_ref();
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
0x18000d310  mov     [rsp+arg_0], rbx
0x18000d315  push    rdi
0x18000d316  sub     rsp, 20h
0x18000d31a  mov     rax, [rdx]
0x18000d31d  mov     rdi, r8
0x18000d320  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000d327  mov     rbx, rcx
0x18000d32a  jnz     short loc_18000D366
0x18000d32c  mov     rax, [rdx+8]
0x18000d330  cmp     rax, cs:qword_180011860
0x18000d337  jnz     short loc_18000D366
0x18000d339  mov     rax, [rcx]
0x18000d33c  mov     rax, [rax+18h]
0x18000d340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d345  mov     [rdi], rax
0x18000d348  mov     rax, [rbx+8]
0x18000d34c  test    rax, rax
0x18000d34f  js      loc_18000D416
0x18000d355  lea     rcx, [rax+1]
0x18000d359  lock cmpxchg [rbx+8], rcx
0x18000d35f  jnz     short loc_18000D34C
0x18000d361  jmp     loc_18000D41B
0x18000d366  mov     rax, [rdx]
0x18000d369  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18000d370  jnz     short loc_18000D3A5
0x18000d372  mov     rax, [rdx+8]
0x18000d376  cmp     rax, cs:qword_180011810
0x18000d37d  jnz     short loc_18000D3A5
0x18000d37f  mov     rax, [rcx]
0x18000d382  mov     rax, [rax+38h]
0x18000d386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d38b  mov     [rdi], rax
0x18000d38e  mov     rax, [rbx+8]
0x18000d392  test    rax, rax
0x18000d395  js      short loc_18000D416
0x18000d397  lea     rcx, [rax+1]
0x18000d39b  lock cmpxchg [rbx+8], rcx
0x18000d3a1  jnz     short loc_18000D392
0x18000d3a3  jmp     short loc_18000D41B
0x18000d3a5  mov     rax, [rdx]
0x18000d3a8  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000d3af  jnz     short loc_18000D3D7
0x18000d3b1  mov     rax, [rdx+8]
0x18000d3b5  cmp     rax, cs:qword_180011830
0x18000d3bc  jnz     short loc_18000D3D7
0x18000d3be  call    ?make_weak_ref@?$root_implements@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@UITranscodeWallpaperStatics@3456@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::make_weak_ref(void)
0x18000d3c3  mov     [rdi], rax
0x18000d3c6  neg     rax
0x18000d3c9  sbb     eax, eax
0x18000d3cb  not     eax
0x18000d3cd  and     eax, 8007000Eh
0x18000d3d2  jmp     loc_18000D483
0x18000d3d7  mov     rax, [rdx]
0x18000d3da  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d3e1  jnz     short loc_18000D41F
0x18000d3e3  mov     rax, [rdx+8]
0x18000d3e7  cmp     rax, cs:qword_180011850
0x18000d3ee  jnz     short loc_18000D41F
0x18000d3f0  mov     rax, [rcx]
0x18000d3f3  mov     rax, [rax+18h]
0x18000d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3fc  mov     [rdi], rax
0x18000d3ff  mov     rax, [rbx+8]
0x18000d403  test    rax, rax
0x18000d406  js      short loc_18000D416
0x18000d408  lea     rcx, [rax+1]
0x18000d40c  lock cmpxchg [rbx+8], rcx
0x18000d412  jnz     short loc_18000D403
0x18000d414  jmp     short loc_18000D41B
0x18000d416  lock inc dword ptr [rax+rax+18h]
0x18000d41b  xor     eax, eax
0x18000d41d  jmp     short loc_18000D483
0x18000d41f  mov     rax, [rdx]
0x18000d422  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000d429  jnz     short loc_18000D478
0x18000d42b  mov     rax, [rdx+8]
0x18000d42f  cmp     rax, cs:qword_180011840
0x18000d436  jnz     short loc_18000D478
0x18000d438  mov     rax, [rcx]
0x18000d43b  mov     rax, [rax+18h]
0x18000d43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d444  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d44b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d450  mov     rbx, rax
0x18000d453  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d458  xor     edx, edx
0x18000d45a  test    rax, rax
0x18000d45d  jz      short loc_18000D46D
0x18000d45f  mov     rdx, rbx
0x18000d462  mov     rcx, rax
0x18000d465  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18000d46a  mov     rdx, rax
0x18000d46d  mov     [rdi], rdx
0x18000d470  neg     rdx
0x18000d473  jmp     loc_18000D3C9
0x18000d478  mov     rax, [rcx]
0x18000d47b  mov     rax, [rax]
0x18000d47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d483  mov     rbx, [rsp+28h+arg_0]
0x18000d488  add     rsp, 20h
0x18000d48c  pop     rdi
0x18000d48d  retn
```
