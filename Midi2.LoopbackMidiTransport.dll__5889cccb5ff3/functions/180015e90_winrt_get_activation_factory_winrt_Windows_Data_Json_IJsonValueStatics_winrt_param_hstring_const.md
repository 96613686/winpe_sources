# winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)

- ea: `0x180015e90`
- end: `0x180015ef6`
- name: `??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014e40`
- `0x180014fec`

## callees

- `0x18000ea80`
- `0x1800145d8`
- `0x180015e90`

## pseudocode

```c
_QWORD *__fastcall winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(_QWORD *a1, _QWORD *a2)
{
  __int64 v3; // r8
  unsigned int v5; // [rsp+28h] [rbp-20h] BYREF
  const char *v6; // [rsp+30h] [rbp-18h]
  __int64 v7; // [rsp+38h] [rbp-10h]
  signed int v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v5 = 6172;
  v9 = 0;
  v6 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v7 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v8,
    a2,
    (__int64)winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>,
    (__int64)&v9);
  if ( v8 < 0 )
    winrt::throw_hresult(v8, &v5, v3);
  *a1 = v9;
  return a1;
}

```

## disassembly

```asm
0x180015e90  mov     r11, rsp
0x180015e93  push    rbx
0x180015e94  sub     rsp, 40h
0x180015e98  mov     rbx, rcx
0x180015e9b  mov     [rsp+48h+var_20], 181Ch
0x180015ea3  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180015eaa  mov     qword ptr [r11+20h], 0
0x180015eb2  lea     rcx, [r11+18h]
0x180015eb6  mov     [r11-18h], rax
0x180015eba  lea     r9, [r11+20h]
0x180015ebe  mov     qword ptr [r11-10h], 0
0x180015ec6  lea     r8, ??$guid_v@UIJsonValueStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>
0x180015ecd  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180015ed2  mov     ecx, [rsp+48h+arg_10]
0x180015ed6  test    ecx, ecx
0x180015ed8  js      short loc_180015EEB
0x180015eda  mov     rax, [rsp+48h+arg_18]
0x180015edf  mov     [rbx], rax
0x180015ee2  mov     rax, rbx
0x180015ee5  add     rsp, 40h
0x180015ee9  pop     rbx
0x180015eea  retn
0x180015eeb  lea     rdx, [rsp+48h+var_20]
0x180015ef0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
