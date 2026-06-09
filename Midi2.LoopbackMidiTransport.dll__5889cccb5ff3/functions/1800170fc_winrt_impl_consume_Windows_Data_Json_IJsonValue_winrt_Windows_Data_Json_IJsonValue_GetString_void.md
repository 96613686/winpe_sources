# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetString(void)

- ea: `0x1800170fc`
- end: `0x18001715f`
- name: `?GetString@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018710`

## callees

- `0x1800145d8`
- `0x1800170fc`
- `0x180032010`

## string_xrefs

- `0x180017107`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetString(
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
  v7 = 476;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
  v10 = 0;
  v4 = *v2;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 64))(v2, &v10);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x1800170fc  mov     r11, rsp
0x1800170ff  push    rbx
0x180017100  sub     rsp, 40h
0x180017104  mov     rcx, [rcx]
0x180017107  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001710e  mov     [rsp+48h+var_20], 1DCh
0x180017116  mov     rbx, rdx
0x180017119  mov     [r11-18h], rax
0x18001711d  lea     rdx, [r11+8]
0x180017121  mov     qword ptr [r11+8], 0
0x180017129  mov     rax, [rcx]
0x18001712c  mov     qword ptr [r11-10h], 0
0x180017134  mov     rax, [rax+40h]
0x180017138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001713d  test    eax, eax
0x18001713f  js      short loc_180017152
0x180017141  mov     rax, [rsp+48h+arg_0]
0x180017146  mov     [rbx], rax
0x180017149  mov     rax, rbx
0x18001714c  add     rsp, 40h
0x180017150  pop     rbx
0x180017151  retn
0x180017152  lea     rdx, [rsp+48h+var_20]
0x180017157  mov     ecx, eax
0x180017159  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
