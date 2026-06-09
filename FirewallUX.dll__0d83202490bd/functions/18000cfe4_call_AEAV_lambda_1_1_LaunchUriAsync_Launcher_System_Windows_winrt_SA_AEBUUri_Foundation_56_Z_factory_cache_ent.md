# ??$call@AEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@winrt@@SA@AEBUUri@Foundation@56@@Z@@?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@2@SA@AEBUUri@Foundation@72@@Z@@Z

- ea: `0x18000cfe4`
- end: `0x18000d1a9`
- name: `??$call@AEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@winrt@@SA@AEBUUri@Foundation@56@@Z@@?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@2@SA@AEBUUri@Foundation@72@@Z@@Z`
- size: `453`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f46c`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000cfe4`
- `0x18000e70c`
- `0x18002d010`

## pseudocode

```c
signed __int64 *__fastcall ___call_AEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_winrt__SA_AEBUUri_Foundation_56__Z____factory_cache_entry_ULauncher_System_Windows_winrt__UILauncherStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_2_SA_AEBUUri_Foundation_72__Z__Z(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 23;
  v13 = L"Windows.System.Launcher";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    &winrt::impl::guid_v<winrt::Windows::System::ILauncherStatics>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 64LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_18003C258);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C260);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
                                                                    + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_18003C258);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18000cfe4  mov     [rsp-18h+arg_8], rbx
0x18000cfe9  mov     [rsp-18h+arg_0], rcx
0x18000cfee  push    rbp
0x18000cfef  push    rsi
0x18000cff0  push    rdi
0x18000cff1  mov     rbp, rsp
0x18000cff4  sub     rsp, 70h
0x18000cff8  mov     rsi, r8
0x18000cffb  mov     rdi, rdx
0x18000cffe  mov     [rbp+var_20], 1
0x18000d005  mov     [rbp+var_1C], 17h
0x18000d00c  lea     rax, aWindowsSystemL; "Windows.System.Launcher"
0x18000d013  mov     [rbp+var_10], rax
0x18000d017  lea     rax, [rbp+var_20]
0x18000d01b  mov     [rbp+var_28], rax
0x18000d01f  mov     [rbp+arg_18], 0
0x18000d027  mov     [rbp+var_40], 0
0x18000d02e  xorps   xmm0, xmm0
0x18000d031  movdqu  [rbp+var_38], xmm0
0x18000d036  lea     r9, [rbp+arg_18]
0x18000d03a  lea     r8, ??$guid_v@UILauncherStatics@System@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::System::ILauncherStatics>
0x18000d041  lea     rdx, [rbp+var_28]
0x18000d045  lea     rcx, [rbp+arg_0]
0x18000d049  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000d04e  mov     ecx, dword ptr [rbp+arg_0]
0x18000d051  test    ecx, ecx
0x18000d053  js      loc_18000D193
0x18000d059  mov     rbx, [rbp+arg_18]
0x18000d05d  mov     [rbp+arg_0], rbx
0x18000d061  test    rbx, rbx
0x18000d064  jz      loc_18000D130
0x18000d06a  mov     [rbp+arg_18], 0
0x18000d072  mov     rax, [rbx]
0x18000d075  lea     r8, [rbp+arg_18]
0x18000d079  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d080  mov     rcx, rbx
0x18000d083  mov     rax, [rax]
0x18000d086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08b  mov     rax, [rbp+arg_18]
0x18000d08f  mov     [rbp+arg_18], rax
0x18000d093  test    rax, rax
0x18000d096  jz      loc_18000D130
0x18000d09c  lea     rcx, [rbp+arg_18]
0x18000d0a0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d0a5  lea     rax, qword_18003C258
0x18000d0ac  mov     [rbp+var_48], rax
0x18000d0b0  lock inc cs:qword_18003C258
0x18000d0b8  xor     eax, eax
0x18000d0ba  lock cmpxchg cs:??$factory_cache_entry_v@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@3U?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@12@A, rbx; factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>::winrt::factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
0x18000d0c3  jnz     short loc_18000D0DE
0x18000d0c5  xor     ebx, ebx
0x18000d0c7  mov     [rbp+arg_0], rbx
0x18000d0cb  lea     rdx, stru_18003C260; ListEntry
0x18000d0d2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d0d9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d0de  mov     [rbp+arg_18], 0
0x18000d0e6  mov     rcx, cs:??$factory_cache_entry_v@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@3U?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@12@A; factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>::winrt::factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
0x18000d0ed  mov     [rbp+var_40], 0
0x18000d0f4  xorps   xmm0, xmm0
0x18000d0f7  movdqu  [rbp+var_38], xmm0
0x18000d0fc  mov     rax, [rcx]
0x18000d0ff  mov     rdx, [rsi]
0x18000d102  lea     r8, [rbp+arg_18]
0x18000d106  mov     rdx, [rdx]
0x18000d109  mov     rax, [rax+40h]
0x18000d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d112  test    eax, eax
0x18000d114  js      loc_18000D19D
0x18000d11a  mov     rax, [rbp+arg_18]
0x18000d11e  mov     [rdi], rax
0x18000d121  lock dec cs:qword_18003C258
0x18000d129  test    rbx, rbx
0x18000d12c  jz      short loc_18000D174
0x18000d12e  jmp     short loc_18000D16B
0x18000d130  mov     [rbp+arg_18], 0
0x18000d138  mov     [rbp+var_40], 0
0x18000d13f  xorps   xmm0, xmm0
0x18000d142  movdqu  [rbp+var_38], xmm0
0x18000d147  mov     rax, [rbx]
0x18000d14a  mov     rdx, [rsi]
0x18000d14d  lea     r8, [rbp+arg_18]
0x18000d151  mov     rdx, [rdx]
0x18000d154  mov     rcx, rbx
0x18000d157  mov     rax, [rax+40h]
0x18000d15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d160  test    eax, eax
0x18000d162  js      short loc_18000D187
0x18000d164  mov     rax, [rbp+arg_18]
0x18000d168  mov     [rdi], rax
0x18000d16b  lea     rcx, [rbp+arg_0]
0x18000d16f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d174  mov     rax, rdi
0x18000d177  mov     rbx, [rsp+70h+arg_8]
0x18000d17f  add     rsp, 70h
0x18000d183  pop     rdi
0x18000d184  pop     rsi
0x18000d185  pop     rbp
0x18000d186  retn
0x18000d187  lea     rdx, [rbp+var_40]
0x18000d18b  mov     ecx, eax
0x18000d18d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d193  lea     rdx, [rbp+var_40]
0x18000d197  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d19d  lea     rdx, [rbp+var_40]
0x18000d1a1  mov     ecx, eax
0x18000d1a3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
