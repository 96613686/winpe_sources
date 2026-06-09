# winrt::Windows::Foundation::GuidHelper::CreateNewGuid(void)

- ea: `0x18001cc70`
- end: `0x18001cd15`
- name: `?CreateNewGuid@GuidHelper@Foundation@Windows@winrt@@SA@XZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001c250`
- `0x18001cc70`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall winrt::Windows::Foundation::GuidHelper::CreateNewGuid(__int64 *a1)
{
  signed int v2; // eax
  __int64 v3; // r8
  void (__fastcall *v5)(__int64, __int64 *); // [rsp+20h] [rbp-28h] BYREF
  unsigned int v6; // [rsp+28h] [rbp-20h] BYREF
  const char *v7; // [rsp+30h] [rbp-18h]
  __int64 v8; // [rsp+38h] [rbp-10h]

  v5 = (void (__fastcall *)(__int64, __int64 *))&qword_18002DA08;
  _InterlockedIncrement64(&qword_18002DA08);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics> )
  {
    *(_OWORD *)a1 = 0;
    v6 = 453;
    v7 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.h";
    v8 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>
                                                       + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>,
           a1);
    if ( v2 < 0 )
      winrt::throw_hresult(v2, &v6, v3);
    _InterlockedDecrement64(&qword_18002DA08);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002DA08);
    v5 = (void (__fastcall *)(__int64, __int64 *))`winrt::Windows::Foundation::GuidHelper::CreateNewGuid'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::call<winrt::guid (*)(winrt::Windows::Foundation::IGuidHelperStatics const &)>(
      a1,
      (__int64)a1,
      &v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18001cc70  push    rbx
0x18001cc72  sub     rsp, 40h
0x18001cc76  mov     rbx, rcx
0x18001cc79  lea     rax, qword_18002DA08
0x18001cc80  mov     [rsp+48h+var_28], rax
0x18001cc85  lock inc cs:qword_18002DA08
0x18001cc8d  cmp     cs:??$factory_cache_entry_v@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@3U?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@12@A, 0; factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>
0x18001cc95  jz      short loc_18001CCDE
0x18001cc97  xorps   xmm0, xmm0
0x18001cc9a  movups  xmmword ptr [rcx], xmm0
0x18001cc9d  mov     rcx, cs:??$factory_cache_entry_v@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@3U?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::GuidHelper,winrt::Windows::Foundation::IGuidHelperStatics>
0x18001cca4  mov     [rsp+48h+var_20], 1C5h
0x18001ccac  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001ccb3  mov     [rsp+48h+var_18], rax
0x18001ccb8  mov     [rsp+48h+var_10], 0
0x18001ccc1  mov     rax, [rcx]
0x18001ccc4  mov     rdx, rbx
0x18001ccc7  mov     rax, [rax+30h]
0x18001cccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccd0  test    eax, eax
0x18001ccd2  js      short loc_18001CD08
0x18001ccd4  lock dec cs:qword_18002DA08
0x18001ccdc  jmp     short loc_18001CCFF
0x18001ccde  lock dec cs:qword_18002DA08
0x18001cce6  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1??CreateNewGuid@GuidHelper@Foundation@Windows@winrt@@SA@XZ@SA@AEBUIGuidHelperStatics@456@@Z; `winrt::Windows::Foundation::GuidHelper::CreateNewGuid(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IGuidHelperStatics const &)
0x18001cced  mov     [rsp+48h+var_28], rax
0x18001ccf2  lea     r8, [rsp+48h+var_28]
0x18001ccf7  mov     rdx, rbx
0x18001ccfa  call    ??$call@P6A?AUguid@winrt@@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@?$factory_cache_entry@UGuidHelper@Foundation@Windows@winrt@@UIGuidHelperStatics@234@@impl@winrt@@QEAA?A_P$$QEAP6A?AUguid@2@AEBUIGuidHelperStatics@Foundation@Windows@2@@Z@Z
0x18001ccff  mov     rax, rbx
0x18001cd02  add     rsp, 40h
0x18001cd06  pop     rbx
0x18001cd07  retn
0x18001cd08  lea     rdx, [rsp+48h+var_20]
0x18001cd0d  mov     ecx, eax
0x18001cd0f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
