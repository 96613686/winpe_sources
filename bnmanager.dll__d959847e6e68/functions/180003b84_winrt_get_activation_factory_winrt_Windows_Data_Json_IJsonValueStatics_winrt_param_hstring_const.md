# winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)

- ea: `0x180003b84`
- end: `0x180003bde`
- name: `??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z`
- size: `90`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800033c0`
- `0x180003730`

## callees

- `0x180003b84`
- `0x180004340`
- `0x18000bde4`

## pseudocode

```c
_QWORD *__fastcall winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(_QWORD *a1, __int64 a2)
{
  int v4; // [rsp+28h] [rbp-20h] BYREF
  __int128 v5; // [rsp+30h] [rbp-18h]
  int v6; // [rsp+60h] [rbp+18h] BYREF
  __int64 v7; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v4 = 0;
  v5 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v6,
    a2,
    winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>,
    &v7);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v4);
  *a1 = v7;
  return a1;
}

```

## disassembly

```asm
0x180003b84  mov     rax, rsp
0x180003b87  push    rbx
0x180003b88  sub     rsp, 40h
0x180003b8c  mov     rbx, rcx
0x180003b8f  mov     qword ptr [rax+20h], 0
0x180003b97  xorps   xmm0, xmm0
0x180003b9a  mov     dword ptr [rax-20h], 0
0x180003ba1  lea     rcx, [rax+18h]
0x180003ba5  lea     r9, [rax+20h]
0x180003ba9  lea     r8, ??$guid_v@UIJsonValueStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics>
0x180003bb0  movdqu  xmmword ptr [rax-18h], xmm0
0x180003bb5  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180003bba  mov     ecx, [rsp+48h+arg_10]
0x180003bbe  test    ecx, ecx
0x180003bc0  js      short loc_180003BD3
0x180003bc2  mov     rax, [rsp+48h+arg_18]
0x180003bc7  mov     [rbx], rax
0x180003bca  mov     rax, rbx
0x180003bcd  add     rsp, 40h
0x180003bd1  pop     rbx
0x180003bd2  retn
0x180003bd3  lea     rdx, [rsp+48h+var_20]
0x180003bd8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
