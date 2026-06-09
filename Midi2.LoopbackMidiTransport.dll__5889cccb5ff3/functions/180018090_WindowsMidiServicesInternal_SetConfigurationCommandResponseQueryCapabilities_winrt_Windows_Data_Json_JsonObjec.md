# WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(winrt::Windows::Data::Json::JsonObject &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,bool>>> &)

- ea: `0x180018090`
- end: `0x18001825c`
- name: `?SetConfigurationCommandResponseQueryCapabilities@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017c54`

## callees

- `0x180014974`
- `0x1800152f8`
- `0x180016638`
- `0x1800168a0`
- `0x180018090`
- `0x1800183a0`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800181c8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800181c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(
        __int64 *a1,
        __int64 ***a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rbx
  __int64 *v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 **v9; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v12; // rbx
  __int64 result; // rax
  int *v14; // [rsp+20h] [rbp-20h] BYREF
  int v15; // [rsp+28h] [rbp-18h] BYREF
  int v16; // [rsp+2Ch] [rbp-14h]
  const wchar_t *v17; // [rsp+38h] [rbp-8h]
  void (__fastcall ***v18)(__int64 *, __int64 *, char **); // [rsp+68h] [rbp+28h] BYREF
  char *v19; // [rsp+70h] [rbp+30h] BYREF

  v19 = (char *)&qword_18005FA88;
  _InterlockedIncrement64(&qword_18005FA88);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
      a1,
      &v18,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18005FA88);
  }
  else
  {
    _InterlockedDecrement64(&qword_18005FA88);
    v19 = (char *)`winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      (__int64)&v18,
      (void (__fastcall **)(__int64, __int64 *))&v19);
  }
  v5 = **a2;
  while ( !*((_BYTE *)v5 + 25) )
  {
    LOBYTE(v4) = *((_BYTE *)v5 + 64);
    v6 = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(&v19, v4);
    v7 = v5[6];
    v8 = v5 + 4;
    if ( (unsigned __int64)v5[7] > 7 )
      v8 = (_QWORD *)*v8;
    if ( (_DWORD)v7 )
    {
      if ( *((_WORD *)v8 + (unsigned int)v7) )
        abort();
      v15 = 1;
      v16 = v7;
      v17 = (const wchar_t *)v8;
      v14 = &v15;
    }
    else
    {
      v14 = 0;
    }
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      (__int64 **)&v18,
      (__int64 *)&v14,
      v6);
    if ( v19 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v19);
    v9 = (__int64 **)v5[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v5 = i;
      v5 = i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  v19 = 0;
  if ( v18 )
  {
    (**v18)((__int64 *)v18, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v19);
    v12 = v19;
  }
  else
  {
    v12 = 0;
  }
  v15 = 1;
  v16 = 17;
  v17 = L"queryCapabilities";
  v14 = &v15;
  result = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
             (__int64 **)a1,
             (__int64 *)&v14,
             (__int64 *)&v19);
  if ( v12 )
    result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v19);
  if ( v18 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v18);
  return result;
}

```

## disassembly

```asm
0x180018090  mov     [rsp-18h+arg_0], rbx
0x180018095  push    rbp
0x180018096  push    rsi
0x180018097  push    rdi
0x180018098  mov     rbp, rsp
0x18001809b  sub     rsp, 40h
0x18001809f  mov     rbx, rdx
0x1800180a2  mov     rdi, rcx
0x1800180a5  xor     esi, esi
0x1800180a7  lea     rax, qword_18005FA88
0x1800180ae  mov     [rbp+arg_10], rax
0x1800180b2  lock inc cs:qword_18005FA88
0x1800180ba  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rsi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1800180c1  jz      short loc_1800180DE
0x1800180c3  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1800180ca  lea     rdx, [rbp+arg_8]
0x1800180ce  call    ??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800180d3  nop
0x1800180d4  lock dec cs:qword_18005FA88
0x1800180dc  jmp     short loc_1800180FF
0x1800180de  lock dec cs:qword_18005FA88
0x1800180e6  lea     rax, ?_lambda_invoker_cdecl_@_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800180ed  mov     [rbp+arg_10], rax
0x1800180f1  lea     r8, [rbp+arg_10]
0x1800180f5  lea     rdx, [rbp+arg_8]
0x1800180f9  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800180fe  nop
0x1800180ff  mov     rbx, [rbx]
0x180018102  mov     rbx, [rbx]
0x180018105  cmp     [rbx+19h], sil
0x180018109  jnz     loc_1800181CF
0x18001810f  mov     dl, [rbx+40h]
0x180018112  lea     rcx, [rbp+arg_10]; bool
0x180018116  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18001811b  mov     r8, rax
0x18001811e  mov     rdx, [rbx+30h]
0x180018122  lea     rcx, [rbx+20h]
0x180018126  cmp     qword ptr [rbx+38h], 7
0x18001812b  jbe     short loc_180018130
0x18001812d  mov     rcx, [rcx]
0x180018130  test    edx, edx
0x180018132  jnz     short loc_18001813A
0x180018134  mov     [rbp+var_20], rsi
0x180018138  jmp     short loc_18001815C
0x18001813a  mov     eax, edx
0x18001813c  cmp     [rcx+rax*2], si
0x180018140  jnz     loc_1800181C8
0x180018146  mov     [rbp+var_18], 1
0x18001814d  mov     [rbp+var_14], edx
0x180018150  mov     [rbp+var_8], rcx
0x180018154  lea     rax, [rbp+var_18]
0x180018158  mov     [rbp+var_20], rax
0x18001815c  lea     rdx, [rbp+var_20]
0x180018160  lea     rcx, [rbp+arg_8]
0x180018164  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180018169  nop
0x18001816a  cmp     [rbp+arg_10], rsi
0x18001816e  jz      short loc_180018179
0x180018170  lea     rcx, [rbp+arg_10]
0x180018174  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018179  mov     rcx, [rbx+10h]
0x18001817d  cmp     [rcx+19h], sil
0x180018181  jz      short loc_1800181A4
0x180018183  mov     rax, [rbx+8]
0x180018187  jmp     short loc_180018196
0x180018189  cmp     rbx, [rax+10h]
0x18001818d  jnz     short loc_18001819C
0x18001818f  mov     rbx, rax
0x180018192  mov     rax, [rax+8]
0x180018196  cmp     [rax+19h], sil
0x18001819a  jz      short loc_180018189
0x18001819c  mov     rbx, rax
0x18001819f  jmp     loc_180018105
0x1800181a4  mov     rbx, rcx
0x1800181a7  mov     rcx, [rcx]
0x1800181aa  cmp     [rcx+19h], sil
0x1800181ae  jnz     loc_180018105
0x1800181b4  mov     rbx, rcx
0x1800181b7  mov     rax, [rcx]
0x1800181ba  mov     rcx, rax
0x1800181bd  cmp     [rax+19h], sil
0x1800181c1  jz      short loc_1800181B4
0x1800181c3  jmp     loc_180018105
0x1800181c8  call    cs:__imp_abort
0x1800181cf  mov     rcx, [rbp+arg_8]
0x1800181d3  mov     [rbp+arg_10], rsi
0x1800181d7  test    rcx, rcx
0x1800181da  jnz     short loc_1800181E1
0x1800181dc  mov     rbx, rsi
0x1800181df  jmp     short loc_1800181FF
0x1800181e1  mov     rax, [rcx]
0x1800181e4  lea     r8, [rbp+arg_10]
0x1800181e8  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x1800181ef  mov     rax, [rax]
0x1800181f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f7  mov     rbx, [rbp+arg_10]
0x1800181fb  mov     [rbp+arg_10], rbx
0x1800181ff  mov     [rbp+var_18], 1
0x180018206  mov     [rbp+var_14], 11h
0x18001820d  lea     rax, aQuerycapabilit; "queryCapabilities"
0x180018214  mov     [rbp+var_8], rax
0x180018218  lea     rax, [rbp+var_18]
0x18001821c  mov     [rbp+var_20], rax
0x180018220  lea     r8, [rbp+arg_10]
0x180018224  lea     rdx, [rbp+var_20]
0x180018228  mov     rcx, rdi
0x18001822b  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180018230  nop
0x180018231  test    rbx, rbx
0x180018234  jz      short loc_180018240
0x180018236  lea     rcx, [rbp+arg_10]
0x18001823a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001823f  nop
0x180018240  cmp     [rbp+arg_8], rsi
0x180018244  jz      short loc_18001824F
0x180018246  lea     rcx, [rbp+arg_8]
0x18001824a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001824f  mov     rbx, [rsp+40h+arg_0]
0x180018254  add     rsp, 40h
0x180018258  pop     rdi
0x180018259  pop     rsi
0x18001825a  pop     rbp
0x18001825b  retn
```
