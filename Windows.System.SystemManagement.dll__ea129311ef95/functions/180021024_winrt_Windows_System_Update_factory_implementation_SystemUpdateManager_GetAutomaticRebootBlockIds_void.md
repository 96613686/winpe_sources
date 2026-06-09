# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetAutomaticRebootBlockIds(void)

- ea: `0x180021024`
- end: `0x1800213a5`
- name: `?GetAutomaticRebootBlockIds@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AU?$IVectorView@Uhstring@winrt@@@Collections@Foundation@56@XZ`
- size: `897`
- prototype: `_QWORD *__fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *, _QWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020fd0`

## callees

- `0x180002dc0`
- `0x180002de4`
- `0x180004ad8`
- `0x180004b90`
- `0x180005954`
- `0x180005a1c`
- `0x180008a80`
- `0x180008adc`
- `0x180008cec`
- `0x18000ab28`
- `0x180013758`
- `0x18001cf78`
- `0x18001d034`
- `0x18001d318`
- `0x18001e5cc`
- `0x18001e708`
- `0x18001ed90`
- `0x18001ee7c`
- `0x18001eeac`
- `0x18001f378`
- `0x18001f6a8`
- `0x180021024`
- `0x180022ba4`
- `0x180023414`
- `0x1800242c0`
- `0x1800257c8`
- `0x1800257e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021189`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021189`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800210fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800210fa`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180021094`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180021094`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetAutomaticRebootBlockIds(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  bool IsSupported; // al
  _QWORD *result; // rax
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  DWORD i; // edi
  unsigned int v12; // eax
  unsigned int v13; // r8d
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  _QWORD *v16; // rdi
  _QWORD *v17; // r11
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-108h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-108h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-108h]
  _QWORD *v21; // [rsp+60h] [rbp-C8h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-C0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+70h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-B0h] BYREF
  char v26[8]; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+98h] [rbp-90h]
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v29; // [rsp+A8h] [rbp-80h]
  LPWSTR lpName[2]; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-68h]
  const wil::ResultException *v32; // [rsp+C8h] [rbp-60h] BYREF
  __int128 v33; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-48h]
  __int64 v35; // [rsp+E8h] [rbp-40h]
  _BYTE v36[32]; // [rsp+F0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v29 = a1;
  v21 = a2;
  IsSupported = winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(a1);
  try
  {
    if ( IsSupported )
    {
      *((_DWORD *)a1 + 14) = 0;
      phkResult = 0;
      v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AD0);
      v7 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v6, &phkResult);
      if ( v7 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x200, v8, (const char *)v7, lpcSubKeys);
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v9 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x205, v10, (const char *)v9, lpcSubKeysa);
      std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(&v27);
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen + 1;
        *(_OWORD *)lpName = 0;
        v31 = 0;
        std::vector<unsigned short>::_Construct_n<>(lpName, cbMaxSubKeyLen + 1);
        v12 = RegEnumKeyExW(phkResult, i, lpName[0], &cchName, 0, 0, 0, 0);
        if ( v12 )
          wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x20D, v13, (const char *)v12, lpcSubKeysb);
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v33, lpName[0], cchName);
        std::wstring::wstring(v36);
        if ( (unsigned __int8)winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::RemovePackageFromLock(
                                v14,
                                &v33,
                                v36) )
        {
          v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
          winrt::hstring::hstring((winrt::hstring *)&v21, v15);
          winrt::hstring::hstring((winrt::hstring *)v26, (const struct winrt::hstring *)&v21);
          if ( *((_QWORD *)&v27 + 1) == v28 )
            std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(&v27, *((_QWORD *)&v27 + 1), v26);
          else
            std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(
              &v27,
              v26);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v26);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v21);
        }
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(&v33);
        std::vector<unsigned short>::_Tidy(lpName);
      }
      v16 = operator new(0x48u);
      winrt::impl::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>(v16 + 2);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      std::atomic<unsigned __int64>::atomic<unsigned __int64>(v16 + 1);
      winrt::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>(v16 + 5);
      *v16 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
      std::vector<winrt::Windows::System::Update::SystemUpdateItem>::vector<winrt::Windows::System::Update::SystemUpdateItem>(
        v16 + 6,
        &v27);
      *v16 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
      v21 = v17;
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
        &v21,
        a2);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v21);
      if ( (_QWORD)v27 )
      {
        std::_Destroy_range<std::allocator<winrt::hstring>>(v27, *((_QWORD *)&v27 + 1));
        std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
        v27 = 0;
        v28 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      result = a2;
    }
    else
    {
      *a2 = 0;
      result = a2;
    }
  }
  catch ( const wil::ResultException *v32 )
  {
    *((_DWORD *)v29 + 14) = *((_DWORD *)v32 + 8);
    throw;
  }
  if ( IsSupported )
  {
    *((_DWORD *)a1 + 14) = 0;
    phkResult = 0;
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AD0);
    v7 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v6, &phkResult);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x200, v8, (const char *)v7, lpcSubKeys);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x205, v10, (const char *)v9, lpcSubKeysa);
    std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(&v27);
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen + 1;
      *(_OWORD *)lpName = 0;
      v31 = 0;
      std::vector<unsigned short>::_Construct_n<>(lpName, cbMaxSubKeyLen + 1);
      v12 = RegEnumKeyExW(phkResult, i, lpName[0], &cchName, 0, 0, 0, 0);
      if ( v12 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x20D, v13, (const char *)v12, lpcSubKeysb);
      v33 = 0;
      v34 = 0;
      v35 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v33, lpName[0], cchName);
      std::wstring::wstring(v36);
      if ( (unsigned __int8)winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::RemovePackageFromLock(
                              v14,
                              &v33,
                              v36) )
      {
        v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
        winrt::hstring::hstring((winrt::hstring *)&v21, v15);
        winrt::hstring::hstring((winrt::hstring *)v26, (const struct winrt::hstring *)&v21);
        if ( *((_QWORD *)&v27 + 1) == v28 )
          std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(&v27, *((_QWORD *)&v27 + 1), v26);
        else
          std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(
            &v27,
            v26);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v26);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v21);
      }
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(&v33);
      std::vector<unsigned short>::_Tidy(lpName);
    }
    v16 = operator new(0x48u);
    winrt::impl::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>(v16 + 2);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v16 + 1);
    winrt::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>(v16 + 5);
    *v16 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
    std::vector<winrt::Windows::System::Update::SystemUpdateItem>::vector<winrt::Windows::System::Update::SystemUpdateItem>(
      v16 + 6,
      &v27);
    *v16 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable';
    v21 = v17;
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
      &v21,
      a2);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v21);
    if ( (_QWORD)v27 )
    {
      std::_Destroy_range<std::allocator<winrt::hstring>>(v27, *((_QWORD *)&v27 + 1));
      std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
      v27 = 0;
      v28 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    result = a2;
  }
  else
  {
    *a2 = 0;
    result = a2;
  }
}

```

## disassembly

```asm
0x180021024  mov     [rsp+arg_10], rbx
0x180021029  mov     [rsp+arg_18], rsi
0x18002102e  push    rdi
0x18002102f  sub     rsp, 120h
0x180021036  mov     rax, cs:__security_cookie
0x18002103d  xor     rax, rsp
0x180021040  mov     [rsp+128h+var_18], rax
0x180021048  mov     rbx, rdx
0x18002104b  mov     rdi, rcx
0x18002104e  mov     [rsp+128h+var_80], rcx
0x180021056  mov     [rsp+128h+var_C8], rdx
0x18002105b  xor     esi, esi
0x18002105d  call    ?IsSupported@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsSupported(void)
0x180021062  test    al, al
0x180021064  jnz     short loc_180021071
0x180021066  mov     [rbx], rsi
0x180021069  mov     rax, rbx
0x18002106c  jmp     loc_18002137F
0x180021071  mov     [rdi+38h], esi
0x180021074  mov     [rsp+128h+phkResult], rsi
0x180021079  lea     rcx, qword_180042AD0
0x180021080  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021085  mov     rdx, rax; lpSubKey
0x180021088  lea     r8, [rsp+128h+phkResult]; phkResult
0x18002108d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021094  call    cs:__imp_RegCreateKeyW
0x18002109a  mov     rcx, [rsp+128h]; this
0x1800210a2  test    eax, eax
0x1800210a4  jz      short loc_1800210B3
0x1800210a6  mov     r9d, eax; char *
0x1800210a9  mov     edx, 200h; void *
0x1800210ae  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800210b3  mov     [rsp+128h+cSubKeys], esi
0x1800210b7  mov     [rsp+128h+cbMaxSubKeyLen], esi
0x1800210bb  mov     [rsp+128h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800210c0  mov     [rsp+128h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800210c5  mov     [rsp+128h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800210ca  mov     [rsp+128h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800210cf  mov     [rsp+128h+lpcValues], rsi; lpcValues
0x1800210d4  mov     [rsp+128h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800210d9  lea     rax, [rsp+128h+cbMaxSubKeyLen]
0x1800210de  mov     [rsp+128h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800210e3  lea     rax, [rsp+128h+cSubKeys]
0x1800210e8  mov     [rsp+128h+lpcSubKeys], rax; unsigned int
0x1800210ed  xor     r9d, r9d; lpReserved
0x1800210f0  xor     r8d, r8d; lpcchClass
0x1800210f3  xor     edx, edx; lpClass
0x1800210f5  mov     rcx, [rsp+128h+phkResult]; hKey
0x1800210fa  call    cs:__imp_RegQueryInfoKeyW
0x180021100  mov     rcx, [rsp+128h]; this
0x180021108  test    eax, eax
0x18002110a  jz      short loc_180021119
0x18002110c  mov     r9d, eax; char *
0x18002110f  mov     edx, 205h; void *
0x180021114  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180021119  lea     rcx, [rsp+128h+var_A0]
0x180021121  call    ??0?$vector@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@V?$allocator@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(void)
0x180021126  nop
0x180021127  mov     edi, esi
0x180021129  cmp     edi, [rsp+128h+cSubKeys]
0x18002112d  jnb     loc_1800212B3
0x180021133  mov     eax, [rsp+128h+cbMaxSubKeyLen]
0x180021137  inc     eax
0x180021139  mov     [rsp+128h+cchName], eax
0x18002113d  xorps   xmm0, xmm0
0x180021140  movdqu  xmmword ptr [rsp+128h+lpName], xmm0
0x180021149  mov     [rsp+128h+var_68], rsi
0x180021151  mov     edx, eax
0x180021153  lea     rcx, [rsp+128h+lpName]
0x18002115b  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x180021160  nop
0x180021161  mov     [rsp+128h+lpcValues], rsi; lpftLastWriteTime
0x180021166  mov     [rsp+128h+lpcbMaxClassLen], rsi; lpcchClass
0x18002116b  mov     [rsp+128h+lpcbMaxSubKeyLen], rsi; lpClass
0x180021170  mov     [rsp+128h+lpcSubKeys], rsi; unsigned int
0x180021175  lea     r9, [rsp+128h+cchName]; lpcchName
0x18002117a  mov     r8, [rsp+128h+lpName]; lpName
0x180021182  mov     edx, edi; dwIndex
0x180021184  mov     rcx, [rsp+128h+phkResult]; hKey
0x180021189  call    cs:__imp_RegEnumKeyExW
0x18002118f  mov     rcx, [rsp+128h]; this
0x180021197  test    eax, eax
0x180021199  jz      short loc_1800211A8
0x18002119b  mov     r9d, eax; char *
0x18002119e  mov     edx, 20Dh; void *
0x1800211a3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800211a8  xorps   xmm0, xmm0
0x1800211ab  movups  [rsp+128h+var_58], xmm0
0x1800211b3  mov     [rsp+128h+var_48], rsi
0x1800211bb  mov     [rsp+128h+var_40], rsi
0x1800211c3  mov     r8d, [rsp+128h+cchName]
0x1800211c8  mov     rdx, [rsp+128h+lpName]
0x1800211d0  lea     rcx, [rsp+128h+var_58]
0x1800211d8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800211dd  nop
0x1800211de  lea     rcx, [rsp+128h+var_38]
0x1800211e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800211eb  nop
0x1800211ec  lea     r8, [rsp+128h+var_38]
0x1800211f4  lea     rdx, [rsp+128h+var_58]
0x1800211fc  call    ?RemovePackageFromLock@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV78@@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::RemovePackageFromLock(std::wstring const &,std::wstring &)
0x180021201  test    al, al
0x180021203  jz      short loc_180021283
0x180021205  lea     rcx, [rsp+128h+var_38]
0x18002120d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021212  mov     rdx, rax; unsigned __int16 *
0x180021215  lea     rcx, [rsp+128h+var_C8]; this
0x18002121a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18002121f  nop
0x180021220  lea     rdx, [rsp+128h+var_C8]; struct winrt::hstring *
0x180021225  lea     rcx, [rsp+128h+var_A8]; this
0x18002122d  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180021232  nop
0x180021233  mov     rdx, qword ptr [rsp+128h+var_A0+8]
0x18002123b  lea     rcx, [rsp+128h+var_A0]
0x180021243  cmp     rdx, [rsp+128h+var_90]
0x18002124b  jz      short loc_18002125C
0x18002124d  lea     rdx, [rsp+128h+var_A8]
0x180021255  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@?$vector@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@V?$allocator@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &&)
0x18002125a  jmp     short loc_18002126A
0x18002125c  lea     r8, [rsp+128h+var_A8]
0x180021264  call    ??$_Emplace_reallocate@Uhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@$$QEAU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(winrt::hstring * const,winrt::hstring &&)
0x180021269  nop
0x18002126a  lea     rcx, [rsp+128h+var_A8]
0x180021272  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180021277  nop
0x180021278  lea     rcx, [rsp+128h+var_C8]
0x18002127d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180021282  nop
0x180021283  lea     rcx, [rsp+128h+var_38]
0x18002128b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021290  nop
0x180021291  lea     rcx, [rsp+128h+var_58]
0x180021299  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002129e  nop
0x18002129f  lea     rcx, [rsp+128h+lpName]
0x1800212a7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800212ac  inc     edi
0x1800212ae  jmp     loc_180021129
0x1800212b3  mov     ecx, 48h ; 'H'; Size
0x1800212b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800212bd  mov     rdi, rax
0x1800212c0  lea     r11, [rax+10h]
0x1800212c4  mov     rcx, r11
0x1800212c7  call    ??0?$producers_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@V?$tuple@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@U?$IVectorView@Uhstring@winrt@@@2345@U?$IIterable@Uhstring@winrt@@@2345@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>::producers_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,std::tuple<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>>(void)
0x1800212cc  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800212d3  lea     rcx, [rdi+8]
0x1800212d7  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1800212dc  lea     rcx, [rdi+28h]
0x1800212e0  call    ??0?$vector_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@@winrt@@QEAA@XZ; winrt::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>::vector_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring>(void)
0x1800212e5  lea     rcx, ??_7?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x1800212ec  mov     [rdi], rcx
0x1800212ef  lea     rcx, [rdi+30h]
0x1800212f3  lea     rdx, [rsp+128h+var_A0]
0x1800212fb  call    ??0?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<winrt::Windows::System::Update::SystemUpdateItem>::vector<winrt::Windows::System::Update::SystemUpdateItem>(std::vector<winrt::Windows::System::Update::SystemUpdateItem> &&)
0x180021300  lea     rcx, ??_7?$heap_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>>::`vftable'
0x180021307  mov     [rdi], rcx
0x18002130a  mov     [rsp+128h+var_C8], r11
0x18002130f  mov     rdx, rbx
0x180021312  lea     rcx, [rsp+128h+var_C8]
0x180021317  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(void)
0x18002131c  nop
0x18002131d  lea     rcx, [rsp+128h+var_C8]; this
0x180021322  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180021327  nop
0x180021328  mov     rcx, qword ptr [rsp+128h+var_A0]
0x180021330  test    rcx, rcx
0x180021333  jz      short loc_180021372
0x180021335  mov     rdx, qword ptr [rsp+128h+var_A0+8]
0x18002133d  call    ??$_Destroy_range@V?$allocator@Uhstring@winrt@@@std@@@std@@YAXPEAUhstring@winrt@@QEAU12@AEAV?$allocator@Uhstring@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::hstring>>(winrt::hstring *,winrt::hstring * const,std::allocator<winrt::hstring> &)
0x180021342  mov     rcx, qword ptr [rsp+128h+var_A0]
0x18002134a  mov     rdx, [rsp+128h+var_90]
0x180021352  sub     rdx, rcx
0x180021355  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180021359  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002135e  xorps   xmm0, xmm0
0x180021361  movdqu  [rsp+128h+var_A0], xmm0
0x18002136a  mov     [rsp+128h+var_90], rsi
0x180021372  lea     rcx, [rsp+128h+phkResult]
0x180021377  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002137c  mov     rax, rbx
0x18002137f  mov     rcx, [rsp+128h+var_18]
0x180021387  xor     rcx, rsp; StackCookie
0x18002138a  call    __security_check_cookie
0x18002138f  lea     r11, [rsp+128h+var_8]
0x180021397  mov     rbx, [r11+20h]
0x18002139b  mov     rsi, [r11+28h]
0x18002139f  mov     rsp, r11
0x1800213a2  pop     rdi
0x1800213a3  retn
```
