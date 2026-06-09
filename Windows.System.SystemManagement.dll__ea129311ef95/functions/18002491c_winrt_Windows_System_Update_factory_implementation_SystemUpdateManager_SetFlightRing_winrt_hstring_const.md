# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetFlightRing(winrt::hstring const &)

- ea: `0x18002491c`
- end: `0x180024a98`
- name: `?SetFlightRing@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA_NAEBUhstring@6@@Z`
- size: `380`
- prototype: `char __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800248e0`

## callees

- `0x1800039d8`
- `0x180008a80`
- `0x180008e28`
- `0x18001f214`
- `0x18001f318`
- `0x18001f6a8`
- `0x180022cd0`
- `0x1800233a4`
- `0x18002491c`
- `0x1800257c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024a03`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024a03`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800249e2`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800249e2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800249a0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800249a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetFlightRing(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this,
        const struct winrt::hstring *a2)
{
  const WCHAR *v4; // rax
  __int64 v5; // r10
  LPCWSTR v6; // r8
  DWORD cbData; // r9d
  unsigned int v8; // eax
  unsigned int v9; // r8d
  const WCHAR *v10; // rax
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // r8d
  const struct winrt::impl::slim_source_location *v15; // rax
  unsigned int lpData; // [rsp+20h] [rbp-68h]
  unsigned int lpDataa; // [rsp+20h] [rbp-68h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v19[24]; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HKEY phkResult; // [rsp+A0h] [rbp+18h] BYREF

  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(this) )
  {
    winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported((winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject);
    throw (winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject;
  }
  if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(this) )
  {
    v15 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v20);
    winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v19, v15);
    throw (winrt::hresult_access_denied *)v19;
  }
  if ( *(_QWORD *)a2 && *(_DWORD *)(*(_QWORD *)a2 + 4LL) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A90);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A50);
    v8 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v4, v6, 1u, *(LPCVOID *)(v5 + 16), cbData);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x343, v9, (const char *)v8, lpDataa);
  }
  else
  {
    phkResult = 0;
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A50);
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, v10, &phkResult) )
    {
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042A90);
      v12 = RegDeleteValueW(phkResult, v11);
      if ( (v12 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x33D, v13, (const char *)v12, lpData);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  return 1;
}

```

## disassembly

```asm
0x18002491c  mov     [rsp+arg_8], rbx
0x180024921  mov     [rsp+arg_0], rcx
0x180024926  push    rdi
0x180024927  sub     rsp, 80h
0x18002492e  mov     rdi, rdx
0x180024931  mov     rbx, rcx
0x180024934  call    ?IsIotCoreEdition@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(void)
0x180024939  test    al, al
0x18002493b  jz      loc_180024A30
0x180024941  mov     rcx, rbx; this
0x180024944  call    ?HasSystemManagementCapability@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(void)
0x180024949  test    al, al
0x18002494b  jz      loc_180024A4B
0x180024951  mov     r10, [rdi]
0x180024954  test    r10, r10
0x180024957  jz      short loc_1800249B8
0x180024959  cmp     dword ptr [r10+4], 0
0x18002495e  jz      short loc_1800249B8
0x180024960  mov     r9d, [r10+4]
0x180024964  add     r9d, r9d
0x180024967  lea     rcx, qword_180042A90
0x18002496e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024973  mov     r8, rax
0x180024976  lea     rcx, qword_180042A50
0x18002497d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024982  mov     rdx, rax; lpSubKey
0x180024985  mov     [rsp+88h+cbData], r9d; cbData
0x18002498a  mov     rax, [r10+10h]
0x18002498e  mov     [rsp+88h+lpData], rax; unsigned int
0x180024993  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002499a  mov     r9d, 1; dwType
0x1800249a0  call    cs:__imp_RegSetKeyValueW
0x1800249a6  mov     rcx, [rsp+88h]; this
0x1800249ae  test    eax, eax
0x1800249b0  jnz     loc_180024A73
0x1800249b6  jmp     short loc_180024A1D
0x1800249b8  mov     [rsp+88h+phkResult], 0
0x1800249c4  lea     rcx, qword_180042A50
0x1800249cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800249d0  mov     rdx, rax; lpSubKey
0x1800249d3  lea     r8, [rsp+88h+phkResult]; phkResult
0x1800249db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800249e2  call    cs:__imp_RegOpenKeyW
0x1800249e8  test    eax, eax
0x1800249ea  jnz     short loc_180024A10
0x1800249ec  lea     rcx, qword_180042A90
0x1800249f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800249f8  mov     rdx, rax; lpValueName
0x1800249fb  mov     rcx, [rsp+88h+phkResult]; hKey
0x180024a03  call    cs:__imp_RegDeleteValueW
0x180024a09  test    eax, 0FFFFFFFDh
0x180024a0e  jnz     short loc_180024A81
0x180024a10  lea     rcx, [rsp+88h+phkResult]
0x180024a18  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180024a1d  mov     al, 1
0x180024a1f  mov     rbx, [rsp+88h+arg_8]
0x180024a27  add     rsp, 80h
0x180024a2e  pop     rdi
0x180024a2f  retn
0x180024a30  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180024a35  call    ??0hresult_not_supported@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported(void)
0x180024a3a  lea     rdx, _TI2?AUhresult_not_supported@factory_implementation@Update@System@Windows@winrt@@; pThrowInfo
0x180024a41  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180024a46  call    _CxxThrowException_0
0x180024a4b  lea     rcx, [rsp+88h+var_20]
0x180024a50  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180024a55  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180024a58  lea     rcx, [rsp+88h+var_38]; this
0x180024a5d  call    ??0hresult_access_denied@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::impl::slim_source_location const &)
0x180024a62  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180024a69  lea     rcx, [rsp+88h+var_38]; pExceptionObject
0x180024a6e  call    _CxxThrowException_0
0x180024a73  mov     r9d, eax; char *
0x180024a76  mov     edx, 343h; void *
0x180024a7b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180024a81  mov     rcx, [rsp+88h]; this
0x180024a89  mov     r9d, eax; char *
0x180024a8c  mov     edx, 33Dh; void *
0x180024a91  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
