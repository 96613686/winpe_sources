# ??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z

- ea: `0x180003730`
- end: `0x1800038c5`
- name: `??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z`
- size: `405`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006920`

## callees

- `0x1800023ad`
- `0x180003730`
- `0x180003b84`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000375d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000375d`

## string_xrefs

- `0x180003772`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_fa5bfa998c3b0e5f1b75589fad572465_ &>(
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
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
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
                                                             + 48LL))(
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
0x180003730  mov     [rsp-18h+arg_8], rbx
0x180003735  mov     [rsp-18h+arg_10], rsi
0x18000373a  mov     [rsp-18h+arg_0], rcx
0x18000373f  push    rbp
0x180003740  push    rdi
0x180003741  push    r14
0x180003743  mov     rbp, rsp
0x180003746  sub     rsp, 70h
0x18000374a  mov     rsi, r8
0x18000374d  mov     rbx, rdx
0x180003750  xor     r14d, r14d
0x180003753  cmp     word ptr cs:aWindowsDataJso+36h, r14w; ""
0x18000375b  jz      short loc_180003764
0x18000375d  call    cs:__imp_abort
0x180003764  mov     [rbp+var_20], 1
0x18000376b  mov     [rbp+var_1C], 1Bh
0x180003772  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonValue"
0x180003779  mov     [rbp+var_10], rax
0x18000377d  lea     rax, [rbp+var_20]
0x180003781  mov     [rbp+var_28], rax
0x180003785  lea     rdx, [rbp+var_28]
0x180003789  lea     rcx, [rbp+arg_0]
0x18000378d  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180003792  nop
0x180003793  mov     rdi, [rbp+arg_0]
0x180003797  test    rdi, rdi
0x18000379a  jz      loc_180003858
0x1800037a0  mov     [rbp+arg_18], r14
0x1800037a4  mov     rax, [rdi]
0x1800037a7  lea     r8, [rbp+arg_18]
0x1800037ab  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800037b2  mov     rcx, rdi
0x1800037b5  mov     rax, [rax]
0x1800037b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bd  mov     rax, [rbp+arg_18]
0x1800037c1  mov     [rbp+arg_18], rax
0x1800037c5  test    rax, rax
0x1800037c8  jz      loc_180003858
0x1800037ce  lea     rcx, [rbp+arg_18]
0x1800037d2  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800037d7  lea     rax, qword_180014788
0x1800037de  mov     [rbp+var_48], rax
0x1800037e2  lock inc cs:qword_180014788
0x1800037ea  xor     eax, eax
0x1800037ec  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800037f5  jnz     short loc_180003811
0x1800037f7  mov     [rbp+arg_0], r14
0x1800037fb  lea     rdx, ListEntry; ListEntry
0x180003802  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180003809  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000380e  mov     rdi, r14
0x180003811  mov     [rbp+arg_18], r14
0x180003815  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x18000381c  mov     [rbp+var_40], r14d
0x180003820  xorps   xmm0, xmm0
0x180003823  movdqu  [rbp+var_38], xmm0
0x180003828  mov     rax, [rcx]
0x18000382b  mov     rdx, [rsi]
0x18000382e  lea     r8, [rbp+arg_18]
0x180003832  mov     rdx, [rdx]
0x180003835  mov     rax, [rax+30h]
0x180003839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383e  test    eax, eax
0x180003840  js      short loc_1800038B9
0x180003842  mov     rax, [rbp+arg_18]
0x180003846  mov     [rbx], rax
0x180003849  lock dec cs:qword_180014788
0x180003851  test    rdi, rdi
0x180003854  jz      short loc_180003895
0x180003856  jmp     short loc_18000388C
0x180003858  mov     [rbp+arg_18], r14
0x18000385c  mov     [rbp+var_40], r14d
0x180003860  xorps   xmm0, xmm0
0x180003863  movdqu  [rbp+var_38], xmm0
0x180003868  mov     rax, [rdi]
0x18000386b  mov     rdx, [rsi]
0x18000386e  lea     r8, [rbp+arg_18]
0x180003872  mov     rdx, [rdx]
0x180003875  mov     rcx, rdi
0x180003878  mov     rax, [rax+30h]
0x18000387c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003881  test    eax, eax
0x180003883  js      short loc_1800038AD
0x180003885  mov     rax, [rbp+arg_18]
0x180003889  mov     [rbx], rax
0x18000388c  lea     rcx, [rbp+arg_0]
0x180003890  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003895  mov     rax, rbx
0x180003898  lea     r11, [rsp+70h+var_s0]
0x18000389d  mov     rbx, [r11+28h]
0x1800038a1  mov     rsi, [r11+30h]
0x1800038a5  mov     rsp, r11
0x1800038a8  pop     r14
0x1800038aa  pop     rdi
0x1800038ab  pop     rbp
0x1800038ac  retn
0x1800038ad  lea     rdx, [rbp+var_40]
0x1800038b1  mov     ecx, eax
0x1800038b3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800038b9  lea     rdx, [rbp+var_40]
0x1800038bd  mov     ecx, eax
0x1800038bf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
