# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x180017968`
- end: `0x180017ae7`
- name: `?query_interface_common@?$root_implements@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `383`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015130`
- `0x1800151c0`
- `0x180015250`

## callees

- `0x180002cf0`
- `0x1800121f8`
- `0x1800170cc`
- `0x180017968`
- `0x18002c010`

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
0x180017968  mov     [rsp+arg_0], rbx
0x18001796d  push    rdi
0x18001796e  sub     rsp, 20h
0x180017972  mov     rax, [rdx]
0x180017975  mov     rdi, r8
0x180017978  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18001797f  mov     rbx, rcx
0x180017982  jnz     short loc_1800179BE
0x180017984  mov     rax, [rdx+8]
0x180017988  cmp     rax, cs:qword_180031A80
0x18001798f  jnz     short loc_1800179BE
0x180017991  mov     rax, [rcx]
0x180017994  mov     rax, [rax+18h]
0x180017998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001799d  mov     [rdi], rax
0x1800179a0  mov     rax, [rbx+8]
0x1800179a4  test    rax, rax
0x1800179a7  js      loc_180017A6E
0x1800179ad  lea     rcx, [rax+1]
0x1800179b1  lock cmpxchg [rbx+8], rcx
0x1800179b7  jnz     short loc_1800179A4
0x1800179b9  jmp     loc_180017A73
0x1800179be  mov     rax, [rdx]
0x1800179c1  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x1800179c8  jnz     short loc_1800179FD
0x1800179ca  mov     rax, [rdx+8]
0x1800179ce  cmp     rax, cs:qword_180031A30
0x1800179d5  jnz     short loc_1800179FD
0x1800179d7  mov     rax, [rcx]
0x1800179da  mov     rax, [rax+38h]
0x1800179de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179e3  mov     [rdi], rax
0x1800179e6  mov     rax, [rbx+8]
0x1800179ea  test    rax, rax
0x1800179ed  js      short loc_180017A6E
0x1800179ef  lea     rcx, [rax+1]
0x1800179f3  lock cmpxchg [rbx+8], rcx
0x1800179f9  jnz     short loc_1800179EA
0x1800179fb  jmp     short loc_180017A73
0x1800179fd  mov     rax, [rdx]
0x180017a00  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x180017a07  jnz     short loc_180017A2F
0x180017a09  mov     rax, [rdx+8]
0x180017a0d  cmp     rax, cs:qword_180031A40
0x180017a14  jnz     short loc_180017A2F
0x180017a16  call    ?make_weak_ref@?$root_implements@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::WindowsUpdateGetAdministratorResult>::make_weak_ref(void)
0x180017a1b  mov     [rdi], rax
0x180017a1e  neg     rax
0x180017a21  sbb     eax, eax
0x180017a23  not     eax
0x180017a25  and     eax, 8007000Eh
0x180017a2a  jmp     loc_180017ADB
0x180017a2f  mov     rax, [rdx]
0x180017a32  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180017a39  jnz     short loc_180017A77
0x180017a3b  mov     rax, [rdx+8]
0x180017a3f  cmp     rax, cs:qword_180031F80
0x180017a46  jnz     short loc_180017A77
0x180017a48  mov     rax, [rcx]
0x180017a4b  mov     rax, [rax+18h]
0x180017a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a54  mov     [rdi], rax
0x180017a57  mov     rax, [rbx+8]
0x180017a5b  test    rax, rax
0x180017a5e  js      short loc_180017A6E
0x180017a60  lea     rcx, [rax+1]
0x180017a64  lock cmpxchg [rbx+8], rcx
0x180017a6a  jnz     short loc_180017A5B
0x180017a6c  jmp     short loc_180017A73
0x180017a6e  lock inc dword ptr [rax+rax+18h]
0x180017a73  xor     eax, eax
0x180017a75  jmp     short loc_180017ADB
0x180017a77  mov     rax, [rdx]
0x180017a7a  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180017a81  jnz     short loc_180017AD0
0x180017a83  mov     rax, [rdx+8]
0x180017a87  cmp     rax, cs:qword_180031A70
0x180017a8e  jnz     short loc_180017AD0
0x180017a90  mov     rax, [rcx]
0x180017a93  mov     rax, [rax+18h]
0x180017a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017aa3  mov     ecx, 20h ; ' '; unsigned __int64
0x180017aa8  mov     rbx, rax
0x180017aab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017ab0  xor     edx, edx
0x180017ab2  test    rax, rax
0x180017ab5  jz      short loc_180017AC5
0x180017ab7  mov     rdx, rbx
0x180017aba  mov     rcx, rax
0x180017abd  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180017ac2  mov     rdx, rax
0x180017ac5  mov     [rdi], rdx
0x180017ac8  neg     rdx
0x180017acb  jmp     loc_180017A21
0x180017ad0  mov     rax, [rcx]
0x180017ad3  mov     rax, [rax]
0x180017ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017adb  mov     rbx, [rsp+28h+arg_0]
0x180017ae0  add     rsp, 20h
0x180017ae4  pop     rdi
0x180017ae5  retn
```
