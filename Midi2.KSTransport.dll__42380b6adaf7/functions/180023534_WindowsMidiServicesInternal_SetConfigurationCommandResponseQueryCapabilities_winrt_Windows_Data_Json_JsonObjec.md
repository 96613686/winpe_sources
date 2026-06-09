# WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(winrt::Windows::Data::Json::JsonObject &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,bool>>> &)

- ea: `0x180023534`
- end: `0x1800236b2`
- name: `?SetConfigurationCommandResponseQueryCapabilities@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e38`

## callees

- `0x18000d1c0`
- `0x180021c3c`
- `0x180022080`
- `0x180023534`
- `0x1800237f4`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002361e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002361e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(
        __int64 **a1,
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

  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v18);
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
             a1,
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
0x180023534  mov     [rsp-18h+arg_0], rbx
0x180023539  push    rbp
0x18002353a  push    rsi
0x18002353b  push    rdi
0x18002353c  mov     rbp, rsp
0x18002353f  sub     rsp, 40h
0x180023543  mov     rbx, rdx
0x180023546  mov     rdi, rcx
0x180023549  lea     rcx, [rbp+arg_8]; this
0x18002354d  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180023552  nop
0x180023553  mov     rbx, [rbx]
0x180023556  mov     rbx, [rbx]
0x180023559  xor     esi, esi
0x18002355b  cmp     [rbx+19h], sil
0x18002355f  jnz     loc_180023625
0x180023565  mov     dl, [rbx+40h]
0x180023568  lea     rcx, [rbp+arg_10]; bool
0x18002356c  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180023571  mov     r8, rax
0x180023574  mov     rdx, [rbx+30h]
0x180023578  lea     rcx, [rbx+20h]
0x18002357c  cmp     qword ptr [rbx+38h], 7
0x180023581  jbe     short loc_180023586
0x180023583  mov     rcx, [rcx]
0x180023586  test    edx, edx
0x180023588  jnz     short loc_180023590
0x18002358a  mov     [rbp+var_20], rsi
0x18002358e  jmp     short loc_1800235B2
0x180023590  mov     eax, edx
0x180023592  cmp     [rcx+rax*2], si
0x180023596  jnz     loc_18002361E
0x18002359c  mov     [rbp+var_18], 1
0x1800235a3  mov     [rbp+var_14], edx
0x1800235a6  mov     [rbp+var_8], rcx
0x1800235aa  lea     rax, [rbp+var_18]
0x1800235ae  mov     [rbp+var_20], rax
0x1800235b2  lea     rdx, [rbp+var_20]
0x1800235b6  lea     rcx, [rbp+arg_8]
0x1800235ba  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800235bf  nop
0x1800235c0  cmp     [rbp+arg_10], rsi
0x1800235c4  jz      short loc_1800235CF
0x1800235c6  lea     rcx, [rbp+arg_10]
0x1800235ca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800235cf  mov     rcx, [rbx+10h]
0x1800235d3  cmp     [rcx+19h], sil
0x1800235d7  jz      short loc_1800235FA
0x1800235d9  mov     rax, [rbx+8]
0x1800235dd  jmp     short loc_1800235EC
0x1800235df  cmp     rbx, [rax+10h]
0x1800235e3  jnz     short loc_1800235F2
0x1800235e5  mov     rbx, rax
0x1800235e8  mov     rax, [rax+8]
0x1800235ec  cmp     [rax+19h], sil
0x1800235f0  jz      short loc_1800235DF
0x1800235f2  mov     rbx, rax
0x1800235f5  jmp     loc_18002355B
0x1800235fa  mov     rbx, rcx
0x1800235fd  mov     rcx, [rcx]
0x180023600  cmp     [rcx+19h], sil
0x180023604  jnz     loc_18002355B
0x18002360a  mov     rbx, rcx
0x18002360d  mov     rax, [rcx]
0x180023610  mov     rcx, rax
0x180023613  cmp     [rax+19h], sil
0x180023617  jz      short loc_18002360A
0x180023619  jmp     loc_18002355B
0x18002361e  call    cs:__imp_abort
0x180023625  mov     rcx, [rbp+arg_8]
0x180023629  mov     [rbp+arg_10], rsi
0x18002362d  test    rcx, rcx
0x180023630  jnz     short loc_180023637
0x180023632  mov     rbx, rsi
0x180023635  jmp     short loc_180023655
0x180023637  mov     rax, [rcx]
0x18002363a  lea     r8, [rbp+arg_10]
0x18002363e  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180023645  mov     rax, [rax]
0x180023648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002364d  mov     rbx, [rbp+arg_10]
0x180023651  mov     [rbp+arg_10], rbx
0x180023655  mov     [rbp+var_18], 1
0x18002365c  mov     [rbp+var_14], 11h
0x180023663  lea     rax, aQuerycapabilit; "queryCapabilities"
0x18002366a  mov     [rbp+var_8], rax
0x18002366e  lea     rax, [rbp+var_18]
0x180023672  mov     [rbp+var_20], rax
0x180023676  lea     r8, [rbp+arg_10]
0x18002367a  lea     rdx, [rbp+var_20]
0x18002367e  mov     rcx, rdi
0x180023681  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180023686  nop
0x180023687  test    rbx, rbx
0x18002368a  jz      short loc_180023696
0x18002368c  lea     rcx, [rbp+arg_10]
0x180023690  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023695  nop
0x180023696  cmp     [rbp+arg_8], rsi
0x18002369a  jz      short loc_1800236A5
0x18002369c  lea     rcx, [rbp+arg_8]
0x1800236a0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800236a5  mov     rbx, [rsp+40h+arg_0]
0x1800236aa  add     rsp, 40h
0x1800236ae  pop     rdi
0x1800236af  pop     rsi
0x1800236b0  pop     rbp
0x1800236b1  retn
```
