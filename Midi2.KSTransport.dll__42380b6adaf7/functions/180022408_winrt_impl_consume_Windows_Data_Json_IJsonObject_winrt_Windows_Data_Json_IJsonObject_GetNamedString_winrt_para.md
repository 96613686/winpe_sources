# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)

- ea: `0x180022408`
- end: `0x180022471`
- name: `?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800228d0`
- `0x18002af94`

## callees

- `0x180015348`
- `0x180022408`
- `0x180041010`

## string_xrefs

- `0x180022413`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  const char *v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v9 = 242;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v12 = 0;
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 80))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x180022408  mov     r11, rsp
0x18002240b  push    rbx
0x18002240c  sub     rsp, 40h
0x180022410  mov     rcx, [rcx]
0x180022413  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002241a  mov     r9, r8
0x18002241d  mov     [rsp+48h+var_20], 0F2h
0x180022425  mov     [r11-18h], rax
0x180022429  lea     r8, [r11+8]
0x18002242d  mov     qword ptr [r11+8], 0
0x180022435  mov     rbx, rdx
0x180022438  mov     rax, [rcx]
0x18002243b  mov     rdx, [r9]
0x18002243e  mov     qword ptr [r11-10h], 0
0x180022446  mov     rax, [rax+50h]
0x18002244a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002244f  test    eax, eax
0x180022451  js      short loc_180022464
0x180022453  mov     rax, [rsp+48h+arg_0]
0x180022458  mov     [rbx], rax
0x18002245b  mov     rax, rbx
0x18002245e  add     rsp, 40h
0x180022462  pop     rbx
0x180022463  retn
0x180022464  lea     rdx, [rsp+48h+var_20]
0x180022469  mov     ecx, eax
0x18002246b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
