# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180016d10`
- end: `0x180016e8e`
- name: `?query_interface_common@?$root_implements@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800145a0`
- `0x180014620`
- `0x1800146a0`

## callees

- `0x180002d40`
- `0x180011644`
- `0x1800164cc`
- `0x180016d10`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::query_interface_common(
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
        weak_ref = winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::WindowsUpdateGetAdministratorResult>::make_weak_ref();
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
        v13 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
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
0x180016d10  mov     [rsp+arg_0], rbx
0x180016d15  push    rdi
0x180016d16  sub     rsp, 20h
0x180016d1a  mov     rax, [rdx]
0x180016d1d  mov     rdi, r8
0x180016d20  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x180016d27  mov     rbx, rcx
0x180016d2a  jnz     short loc_180016D66
0x180016d2c  mov     rax, [rdx+8]
0x180016d30  cmp     rax, cs:qword_18002F9C0
0x180016d37  jnz     short loc_180016D66
0x180016d39  mov     rax, [rcx]
0x180016d3c  mov     rax, [rax+18h]
0x180016d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d45  mov     [rdi], rax
0x180016d48  mov     rax, [rbx+8]
0x180016d4c  test    rax, rax
0x180016d4f  js      loc_180016E16
0x180016d55  lea     rcx, [rax+1]
0x180016d59  lock cmpxchg [rbx+8], rcx
0x180016d5f  jnz     short loc_180016D4C
0x180016d61  jmp     loc_180016E1B
0x180016d66  mov     rax, [rdx]
0x180016d69  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x180016d70  jnz     short loc_180016DA5
0x180016d72  mov     rax, [rdx+8]
0x180016d76  cmp     rax, cs:qword_18002F980
0x180016d7d  jnz     short loc_180016DA5
0x180016d7f  mov     rax, [rcx]
0x180016d82  mov     rax, [rax+38h]
0x180016d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d8b  mov     [rdi], rax
0x180016d8e  mov     rax, [rbx+8]
0x180016d92  test    rax, rax
0x180016d95  js      short loc_180016E16
0x180016d97  lea     rcx, [rax+1]
0x180016d9b  lock cmpxchg [rbx+8], rcx
0x180016da1  jnz     short loc_180016D92
0x180016da3  jmp     short loc_180016E1B
0x180016da5  mov     rax, [rdx]
0x180016da8  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x180016daf  jnz     short loc_180016DD7
0x180016db1  mov     rax, [rdx+8]
0x180016db5  cmp     rax, cs:qword_18002F9A0
0x180016dbc  jnz     short loc_180016DD7
0x180016dbe  call    ?make_weak_ref@?$root_implements@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::WindowsUpdateGetAdministratorResult>::make_weak_ref(void)
0x180016dc3  mov     [rdi], rax
0x180016dc6  neg     rax
0x180016dc9  sbb     eax, eax
0x180016dcb  not     eax
0x180016dcd  and     eax, 8007000Eh
0x180016dd2  jmp     loc_180016E83
0x180016dd7  mov     rax, [rdx]
0x180016dda  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180016de1  jnz     short loc_180016E1F
0x180016de3  mov     rax, [rdx+8]
0x180016de7  cmp     rax, cs:qword_18002FFE0
0x180016dee  jnz     short loc_180016E1F
0x180016df0  mov     rax, [rcx]
0x180016df3  mov     rax, [rax+18h]
0x180016df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dfc  mov     [rdi], rax
0x180016dff  mov     rax, [rbx+8]
0x180016e03  test    rax, rax
0x180016e06  js      short loc_180016E16
0x180016e08  lea     rcx, [rax+1]
0x180016e0c  lock cmpxchg [rbx+8], rcx
0x180016e12  jnz     short loc_180016E03
0x180016e14  jmp     short loc_180016E1B
0x180016e16  lock inc dword ptr [rax+rax+18h]
0x180016e1b  xor     eax, eax
0x180016e1d  jmp     short loc_180016E83
0x180016e1f  mov     rax, [rdx]
0x180016e22  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180016e29  jnz     short loc_180016E78
0x180016e2b  mov     rax, [rdx+8]
0x180016e2f  cmp     rax, cs:qword_18002F9B0
0x180016e36  jnz     short loc_180016E78
0x180016e38  mov     rax, [rcx]
0x180016e3b  mov     rax, [rax+18h]
0x180016e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e4b  mov     ecx, 20h ; ' '; unsigned __int64
0x180016e50  mov     rbx, rax
0x180016e53  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016e58  xor     edx, edx
0x180016e5a  test    rax, rax
0x180016e5d  jz      short loc_180016E6D
0x180016e5f  mov     rdx, rbx
0x180016e62  mov     rcx, rax
0x180016e65  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180016e6a  mov     rdx, rax
0x180016e6d  mov     [rdi], rdx
0x180016e70  neg     rdx
0x180016e73  jmp     loc_180016DC9
0x180016e78  mov     rax, [rcx]
0x180016e7b  mov     rax, [rax]
0x180016e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e83  mov     rbx, [rsp+28h+arg_0]
0x180016e88  add     rsp, 20h
0x180016e8c  pop     rdi
0x180016e8d  retn
```
