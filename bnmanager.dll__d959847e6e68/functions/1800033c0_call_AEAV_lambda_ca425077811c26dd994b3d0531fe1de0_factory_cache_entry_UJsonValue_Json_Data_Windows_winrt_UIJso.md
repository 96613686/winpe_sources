# ??$call@AEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@Z

- ea: `0x1800033c0`
- end: `0x180003555`
- name: `??$call@AEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@Z`
- size: `405`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800071ac`

## callees

- `0x1800023ad`
- `0x1800033c0`
- `0x180003b84`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800033ed`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800033ed`

## string_xrefs

- `0x180003402`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_ca425077811c26dd994b3d0531fe1de0_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  if ( aWindowsDataJso[27] )
    abort();
  v12[0] = 1;
  v12[1] = 27;
  v13 = L"Windows.Data.Json.JsonValue";
  v11 = v12;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v14, &v11);
  v5 = (signed __int64)v14;
  if ( !v14 || (v15 = 0, (**v14)(v14, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_180014788);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    v5 = 0;
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_180014788);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x1800033c0  mov     [rsp-18h+arg_8], rbx
0x1800033c5  mov     [rsp-18h+arg_10], rsi
0x1800033ca  mov     [rsp-18h+arg_0], rcx
0x1800033cf  push    rbp
0x1800033d0  push    rdi
0x1800033d1  push    r14
0x1800033d3  mov     rbp, rsp
0x1800033d6  sub     rsp, 70h
0x1800033da  mov     rsi, r8
0x1800033dd  mov     rbx, rdx
0x1800033e0  xor     r14d, r14d
0x1800033e3  cmp     word ptr cs:aWindowsDataJso+36h, r14w; ""
0x1800033eb  jz      short loc_1800033F4
0x1800033ed  call    cs:__imp_abort
0x1800033f4  mov     [rbp+var_20], 1
0x1800033fb  mov     [rbp+var_1C], 1Bh
0x180003402  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonValue"
0x180003409  mov     [rbp+var_10], rax
0x18000340d  lea     rax, [rbp+var_20]
0x180003411  mov     [rbp+var_28], rax
0x180003415  lea     rdx, [rbp+var_28]
0x180003419  lea     rcx, [rbp+arg_0]
0x18000341d  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180003422  nop
0x180003423  mov     rdi, [rbp+arg_0]
0x180003427  test    rdi, rdi
0x18000342a  jz      loc_1800034E8
0x180003430  mov     [rbp+arg_18], r14
0x180003434  mov     rax, [rdi]
0x180003437  lea     r8, [rbp+arg_18]
0x18000343b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180003442  mov     rcx, rdi
0x180003445  mov     rax, [rax]
0x180003448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344d  mov     rax, [rbp+arg_18]
0x180003451  mov     [rbp+arg_18], rax
0x180003455  test    rax, rax
0x180003458  jz      loc_1800034E8
0x18000345e  lea     rcx, [rbp+arg_18]
0x180003462  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003467  lea     rax, qword_180014788
0x18000346e  mov     [rbp+var_48], rax
0x180003472  lock inc cs:qword_180014788
0x18000347a  xor     eax, eax
0x18000347c  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180003485  jnz     short loc_1800034A1
0x180003487  mov     [rbp+arg_0], r14
0x18000348b  lea     rdx, ListEntry; ListEntry
0x180003492  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180003499  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000349e  mov     rdi, r14
0x1800034a1  mov     [rbp+arg_18], r14
0x1800034a5  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800034ac  mov     [rbp+var_40], r14d
0x1800034b0  xorps   xmm0, xmm0
0x1800034b3  movdqu  [rbp+var_38], xmm0
0x1800034b8  mov     rax, [rcx]
0x1800034bb  mov     rdx, [rsi]
0x1800034be  lea     r8, [rbp+arg_18]
0x1800034c2  mov     rdx, [rdx]
0x1800034c5  mov     rax, [rax+50h]
0x1800034c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ce  test    eax, eax
0x1800034d0  js      short loc_180003549
0x1800034d2  mov     rax, [rbp+arg_18]
0x1800034d6  mov     [rbx], rax
0x1800034d9  lock dec cs:qword_180014788
0x1800034e1  test    rdi, rdi
0x1800034e4  jz      short loc_180003525
0x1800034e6  jmp     short loc_18000351C
0x1800034e8  mov     [rbp+arg_18], r14
0x1800034ec  mov     [rbp+var_40], r14d
0x1800034f0  xorps   xmm0, xmm0
0x1800034f3  movdqu  [rbp+var_38], xmm0
0x1800034f8  mov     rax, [rdi]
0x1800034fb  mov     rdx, [rsi]
0x1800034fe  lea     r8, [rbp+arg_18]
0x180003502  mov     rdx, [rdx]
0x180003505  mov     rcx, rdi
0x180003508  mov     rax, [rax+50h]
0x18000350c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003511  test    eax, eax
0x180003513  js      short loc_18000353D
0x180003515  mov     rax, [rbp+arg_18]
0x180003519  mov     [rbx], rax
0x18000351c  lea     rcx, [rbp+arg_0]
0x180003520  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003525  mov     rax, rbx
0x180003528  lea     r11, [rsp+70h+var_s0]
0x18000352d  mov     rbx, [r11+28h]
0x180003531  mov     rsi, [r11+30h]
0x180003535  mov     rsp, r11
0x180003538  pop     r14
0x18000353a  pop     rdi
0x18000353b  pop     rbp
0x18000353c  retn
0x18000353d  lea     rdx, [rbp+var_40]
0x180003541  mov     ecx, eax
0x180003543  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180003549  lea     rdx, [rbp+var_40]
0x18000354d  mov     ecx, eax
0x18000354f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
