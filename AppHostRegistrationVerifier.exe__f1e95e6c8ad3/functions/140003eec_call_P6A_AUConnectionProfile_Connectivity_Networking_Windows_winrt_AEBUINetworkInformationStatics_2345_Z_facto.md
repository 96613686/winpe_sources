# ??$call@P6A?AUConnectionProfile@Connectivity@Networking@Windows@winrt@@AEBUINetworkInformationStatics@2345@@Z@?$factory_cache_entry@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUConnectionProfile@Connectivity@Networking@Windows@2@AEBUINetworkInformationStatics@4562@@Z@Z

- ea: `0x140003eec`
- end: `0x140004005`
- name: `??$call@P6A?AUConnectionProfile@Connectivity@Networking@Windows@winrt@@AEBUINetworkInformationStatics@2345@@Z@?$factory_cache_entry@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUConnectionProfile@Connectivity@Networking@Windows@2@AEBUINetworkInformationStatics@4562@@Z@Z`
- size: `281`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005df4`

## callees

- `0x1400030c7`
- `0x140003eec`
- `0x14000400c`
- `0x140004bdc`
- `0x140007eec`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140003f11`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140003f11`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>::call<winrt::Windows::Networking::Connectivity::ConnectionProfile (*)(winrt::Windows::Networking::Connectivity::INetworkInformationStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+88h] [rbp+38h] BYREF

  v9 = a1;
  if ( aWindowsNetwork[50] )
    abort();
  v7[0] = 1;
  v7[1] = 50;
  v8 = L"Windows.Networking.Connectivity.NetworkInformation";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Networking::Connectivity::INetworkInformationStatics>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v10);
    v10 = &qword_14001B818;
    _InterlockedIncrement64(&qword_14001B818);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>);
    _InterlockedDecrement64(&qword_14001B818);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  winrt::Windows::Networking::Connectivity::IConnectionProfile::~IConnectionProfile((winrt::Windows::Networking::Connectivity::IConnectionProfile *)&v9);
  return a2;
}

```

## disassembly

```asm
0x140003eec  mov     [rsp-18h+arg_8], rbx
0x140003ef1  mov     [rsp-18h+arg_0], rcx
0x140003ef6  push    rbp
0x140003ef7  push    rsi
0x140003ef8  push    rdi
0x140003ef9  mov     rbp, rsp
0x140003efc  sub     rsp, 50h
0x140003f00  mov     rdi, r8
0x140003f03  mov     rbx, rdx
0x140003f06  xor     esi, esi
0x140003f08  cmp     word ptr cs:aWindowsNetwork+64h, si; ""
0x140003f0f  jz      short loc_140003F18
0x140003f11  call    cs:__imp_abort
0x140003f18  mov     [rbp+var_20], 1
0x140003f1f  mov     [rbp+var_1C], 32h ; '2'
0x140003f26  lea     rax, aWindowsNetwork; "Windows.Networking.Connectivity.Network"...
0x140003f2d  mov     [rbp+var_10], rax
0x140003f31  lea     rax, [rbp+var_20]
0x140003f35  mov     [rbp+var_28], rax
0x140003f39  lea     rdx, [rbp+var_28]
0x140003f3d  lea     rcx, [rbp+arg_0]
0x140003f41  call    ??$get_activation_factory@UINetworkInformationStatics@Connectivity@Networking@Windows@winrt@@@winrt@@YA?AUINetworkInformationStatics@Connectivity@Networking@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Networking::Connectivity::INetworkInformationStatics>(winrt::param::hstring const &)
0x140003f46  nop
0x140003f47  mov     rcx, [rbp+arg_0]
0x140003f4b  test    rcx, rcx
0x140003f4e  jz      loc_140003FDC
0x140003f54  mov     [rbp+arg_18], rsi
0x140003f58  mov     rax, [rcx]
0x140003f5b  lea     r8, [rbp+arg_18]
0x140003f5f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140003f66  mov     rax, [rax]
0x140003f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f6e  mov     rax, [rbp+arg_18]
0x140003f72  mov     [rbp+arg_18], rax
0x140003f76  test    rax, rax
0x140003f79  jz      short loc_140003FDC
0x140003f7b  lea     rcx, [rbp+arg_18]
0x140003f7f  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140003f84  lea     rax, qword_14001B818
0x140003f8b  mov     [rbp+arg_18], rax
0x140003f8f  lock inc cs:qword_14001B818
0x140003f97  mov     rcx, [rbp+arg_0]
0x140003f9b  xor     eax, eax
0x140003f9d  lock cmpxchg cs:??$factory_cache_entry_v@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>
0x140003fa6  jnz     short loc_140003FBF
0x140003fa8  mov     [rbp+arg_0], rsi
0x140003fac  lea     rdx, ListEntry; ListEntry
0x140003fb3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140003fba  call    WINRT_IMPL_InterlockedPushEntrySList
0x140003fbf  lea     rdx, ??$factory_cache_entry_v@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UNetworkInformation@Connectivity@Networking@Windows@winrt@@UINetworkInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Networking::Connectivity::NetworkInformation,winrt::Windows::Networking::Connectivity::INetworkInformationStatics>
0x140003fc6  mov     rcx, rbx
0x140003fc9  mov     rax, [rdi]
0x140003fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fd1  nop
0x140003fd2  lock dec cs:qword_14001B818
0x140003fda  jmp     short loc_140003FEC
0x140003fdc  lea     rdx, [rbp+arg_0]
0x140003fe0  mov     rcx, rbx
0x140003fe3  mov     rax, [rdi]
0x140003fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003feb  nop
0x140003fec  lea     rcx, [rbp+arg_0]; this
0x140003ff0  call    ??1IConnectionProfile@Connectivity@Networking@Windows@winrt@@QEAA@XZ; winrt::Windows::Networking::Connectivity::IConnectionProfile::~IConnectionProfile(void)
0x140003ff5  mov     rax, rbx
0x140003ff8  mov     rbx, [rsp+50h+arg_8]
0x140003ffd  add     rsp, 50h
0x140004001  pop     rdi
0x140004002  pop     rsi
0x140004003  pop     rbp
0x140004004  retn
```
