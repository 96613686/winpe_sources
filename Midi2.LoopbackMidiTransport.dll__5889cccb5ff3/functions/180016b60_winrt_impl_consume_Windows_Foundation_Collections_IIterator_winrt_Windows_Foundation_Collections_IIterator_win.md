# winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Data::Json::IJsonValue>::Current(void)

- ea: `0x180016b60`
- end: `0x180016bc9`
- name: `?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800176ec`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180016b60`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Data::Json::IJsonValue>::Current(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  signed int v4; // eax
  __int64 v5; // r8
  unsigned int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]

  *a2 = 0;
  v3 = *a1;
  v7 = 46;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v7, v5);
  return a2;
}

```

## disassembly

```asm
0x180016b60  mov     rax, rsp
0x180016b63  mov     [rax+10h], rdx
0x180016b67  push    rbx
0x180016b68  sub     rsp, 40h
0x180016b6c  mov     rbx, rdx
0x180016b6f  mov     dword ptr [rax-28h], 0
0x180016b76  mov     qword ptr [rdx], 0
0x180016b7d  mov     dword ptr [rax-28h], 1
0x180016b84  mov     rcx, [rcx]
0x180016b87  mov     dword ptr [rax-20h], 2Eh ; '.'
0x180016b8e  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016b95  mov     [rsp+48h+var_18], rax
0x180016b9a  mov     [rsp+48h+var_10], 0
0x180016ba3  mov     rax, [rcx]
0x180016ba6  mov     rax, [rax+30h]
0x180016baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016baf  test    eax, eax
0x180016bb1  js      short loc_180016BBC
0x180016bb3  mov     rax, rbx
0x180016bb6  add     rsp, 40h
0x180016bba  pop     rbx
0x180016bbb  retn
0x180016bbc  lea     rdx, [rsp+48h+var_20]
0x180016bc1  mov     ecx, eax
0x180016bc3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
