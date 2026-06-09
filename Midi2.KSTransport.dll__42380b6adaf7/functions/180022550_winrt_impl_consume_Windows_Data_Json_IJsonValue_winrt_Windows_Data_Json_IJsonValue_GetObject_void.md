# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObject(void)

- ea: `0x180022550`
- end: `0x1800225b3`
- name: `?GetObject@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023ac0`
- `0x18002af94`

## callees

- `0x180015348`
- `0x180022550`
- `0x180041010`

## string_xrefs

- `0x18002255b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObject(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v7 = 548;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v10 = 0;
  v4 = *v2;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 96))(v2, &v10);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x180022550  mov     r11, rsp
0x180022553  push    rbx
0x180022554  sub     rsp, 40h
0x180022558  mov     rcx, [rcx]
0x18002255b  lea     rax, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022562  mov     [rsp+48h+var_20], 224h
0x18002256a  mov     rbx, rdx
0x18002256d  mov     [r11-18h], rax
0x180022571  lea     rdx, [r11+8]
0x180022575  mov     qword ptr [r11+8], 0
0x18002257d  mov     rax, [rcx]
0x180022580  mov     qword ptr [r11-10h], 0
0x180022588  mov     rax, [rax+60h]
0x18002258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022591  test    eax, eax
0x180022593  js      short loc_1800225A6
0x180022595  mov     rax, [rsp+48h+arg_0]
0x18002259a  mov     [rbx], rax
0x18002259d  mov     rax, rbx
0x1800225a0  add     rsp, 40h
0x1800225a4  pop     rbx
0x1800225a5  retn
0x1800225a6  lea     rdx, [rsp+48h+var_20]
0x1800225ab  mov     ecx, eax
0x1800225ad  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
