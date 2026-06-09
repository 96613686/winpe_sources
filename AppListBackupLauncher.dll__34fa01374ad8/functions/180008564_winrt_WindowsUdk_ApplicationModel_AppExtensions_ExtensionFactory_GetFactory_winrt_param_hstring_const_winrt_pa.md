# winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(winrt::param::hstring const &,winrt::param::hstring const &)

- ea: `0x180008564`
- end: `0x180008606`
- name: `?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@0@Z`
- size: `162`
- prototype: `const struct winrt::param::hstring *__fastcall(const struct winrt::param::hstring *, const struct winrt::param::hstring *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000dfe0`

## callees

- `0x1800047c0`
- `0x180008564`
- `0x18000f214`
- `0x180012010`

## pseudocode

```c
const struct winrt::param::hstring *__fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(
        const struct winrt::param::hstring *a1,
        const struct winrt::param::hstring *a2,
        _QWORD *a3)
{
  int v4; // eax
  _QWORD *v6; // [rsp+38h] [rbp-20h] BYREF
  __int128 v7; // [rsp+40h] [rbp-18h]
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+70h] [rbp+18h]

  v6 = a2;
  *(_QWORD *)&v7 = a3;
  v9 = &qword_1800197C8;
  _InterlockedIncrement64(&qword_1800197C8);
  if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics> )
  {
    v8 = 0;
    LODWORD(v6) = 0;
    v7 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
                                                                       + 80LL))(
           winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>,
           *(_QWORD *)a2,
           *a3,
           &v8);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v6);
    *(_QWORD *)a1 = v8;
    _InterlockedDecrement64(&qword_1800197C8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1800197C8);
    winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>::call<_lambda_7b7c9298bfeaa6f21443744179c3c395_ &>(
      0,
      (signed __int64 *)a1,
      &v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180008564  mov     r11, rsp
0x180008567  push    rbx
0x180008568  sub     rsp, 50h
0x18000856c  mov     rbx, rcx
0x18000856f  mov     [r11-20h], rdx
0x180008573  mov     [r11-18h], r8
0x180008577  lea     rax, qword_1800197C8
0x18000857e  mov     [r11+18h], rax
0x180008582  lock inc cs:qword_1800197C8
0x18000858a  mov     rcx, cs:??$factory_cache_entry_v@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory,winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics>
0x180008591  test    rcx, rcx
0x180008594  jz      short loc_1800085DB
0x180008596  mov     qword ptr [r11+10h], 0
0x18000859e  mov     dword ptr [rsp+58h+var_20], 0
0x1800085a6  xorps   xmm0, xmm0
0x1800085a9  movdqu  [rsp+58h+var_18], xmm0
0x1800085af  mov     rax, [rcx]
0x1800085b2  lea     r9, [r11+10h]
0x1800085b6  mov     r8, [r8]
0x1800085b9  mov     rdx, [rdx]
0x1800085bc  mov     rax, [rax+50h]
0x1800085c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c5  test    eax, eax
0x1800085c7  js      short loc_1800085F9
0x1800085c9  mov     rax, [rsp+58h+arg_8]
0x1800085ce  mov     [rbx], rax
0x1800085d1  lock dec cs:qword_1800197C8
0x1800085d9  jmp     short loc_1800085F0
0x1800085db  lock dec cs:qword_1800197C8
0x1800085e3  lea     r8, [rsp+58h+var_20]
0x1800085e8  mov     rdx, rbx
0x1800085eb  call    ??$call@AEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@?$factory_cache_entry@UExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIExtensionFactoryStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_7b7c9298bfeaa6f21443744179c3c395_@@@Z
0x1800085f0  mov     rax, rbx
0x1800085f3  add     rsp, 50h
0x1800085f7  pop     rbx
0x1800085f8  retn
0x1800085f9  lea     rdx, [rsp+58h+var_20]
0x1800085fe  mov     ecx, eax
0x180008600  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
