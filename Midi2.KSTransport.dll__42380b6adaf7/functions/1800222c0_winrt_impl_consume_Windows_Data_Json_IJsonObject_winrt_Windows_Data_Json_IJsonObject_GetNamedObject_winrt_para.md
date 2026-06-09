# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)

- ea: `0x1800222c0`
- end: `0x180022329`
- name: `?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800230a0`
- `0x18002af94`

## callees

- `0x180015348`
- `0x1800222c0`
- `0x180041010`

## string_xrefs

- `0x1800222cb`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
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
  v9 = 206;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v12 = 0;
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 64))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x1800222c0  mov     r11, rsp
0x1800222c3  push    rbx
0x1800222c4  sub     rsp, 40h
0x1800222c8  mov     rcx, [rcx]
0x1800222cb  lea     rax, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800222d2  mov     r9, r8
0x1800222d5  mov     [rsp+48h+var_20], 0CEh
0x1800222dd  mov     [r11-18h], rax
0x1800222e1  lea     r8, [r11+8]
0x1800222e5  mov     qword ptr [r11+8], 0
0x1800222ed  mov     rbx, rdx
0x1800222f0  mov     rax, [rcx]
0x1800222f3  mov     rdx, [r9]
0x1800222f6  mov     qword ptr [r11-10h], 0
0x1800222fe  mov     rax, [rax+40h]
0x180022302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022307  test    eax, eax
0x180022309  js      short loc_18002231C
0x18002230b  mov     rax, [rsp+48h+arg_0]
0x180022310  mov     [rbx], rax
0x180022313  mov     rax, rbx
0x180022316  add     rsp, 40h
0x18002231a  pop     rbx
0x18002231b  retn
0x18002231c  lea     rdx, [rsp+48h+var_20]
0x180022321  mov     ecx, eax
0x180022323  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
