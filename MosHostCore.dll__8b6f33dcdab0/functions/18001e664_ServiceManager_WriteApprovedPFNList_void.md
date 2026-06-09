# ServiceManager::WriteApprovedPFNList(void)

- ea: `0x18001e664`
- end: `0x18001e80e`
- name: `?WriteApprovedPFNList@ServiceManager@@AEAAJXZ`
- size: `426`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016b60`

## callees

- `0x180003410`
- `0x1800079d4`
- `0x180008110`
- `0x18000816c`
- `0x18000b5d8`
- `0x180011610`
- `0x1800171d0`
- `0x18001e664`
- `0x1800211f4`
- `0x180022be8`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e78b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e6cd`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e6cd`
- `MapConfiguration!ConfigurationManager_GetLocaleMapConfiguration` at `0x18001e730`
- `MapConfiguration!ConfigurationManager_GetLocaleMapConfiguration` at `0x18001e730`

## string_xrefs

- `0x18001e6c6`: `ServiceManager::WriteApprovedPFNList`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ServiceManager::WriteApprovedPFNList(ServiceManager *this)
{
  int SystemLocaleInfo; // eax
  int v3; // r8d
  int v4; // ecx
  unsigned int v5; // ebx
  char v6; // di
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  int v14; // ebx
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  __int64 v17; // [rsp+28h] [rbp-61h] BYREF
  const WCHAR *v18; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-31h] BYREF
  HSTRING_HEADER v21; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER v22; // [rsp+98h] [rbp+Fh] BYREF

  string = 0;
  std::wstring::wstring((__int64)v20);
  std::wstring::wstring((__int64)v19);
  v17 = 0;
  SystemLocaleInfo = MapPlatformConfig::GetSystemLocaleInfo((__int64)v19, (__int64)v20);
  if ( SystemLocaleInfo < 0 )
  {
    v3 = 4177;
LABEL_3:
    v4 = SystemLocaleInfo;
    goto LABEL_4;
  }
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v17);
  v6 = *((_BYTE *)this + 4317);
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v21, &v18)[1].Reserved.Reserved1;
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v22, &v18);
  LOBYTE(v9) = v6;
  SystemLocaleInfo = ConfigurationManager_GetLocaleMapConfiguration(v8[1].Reserved.Reserved1, Reserved1, v9, &v17);
  if ( SystemLocaleInfo < 0 )
  {
    v3 = 4183;
    goto LABEL_3;
  }
  v10 = v17;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v17 + 48LL);
  WindowsDeleteString(string);
  string = 0;
  SystemLocaleInfo = v11(v10, 316, &string);
  if ( SystemLocaleInfo < 0 )
  {
    v3 = 4187;
    goto LABEL_3;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(&v21, StringRawBuffer);
  v14 = RegUtils::SetMapsPersistedRegString(v13, L"ApprovedPFNList", (__int64)&v21);
  std::wstring::_Tidy_deallocate((__int64)&v21);
  if ( v14 >= 0 )
  {
    v5 = 0;
    goto LABEL_12;
  }
  v3 = 4190;
  v4 = v14;
LABEL_4:
  v5 = ZTraceReportPropagation(v4, "ServiceManager::WriteApprovedPFNList", v3, this);
LABEL_12:
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v17);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v20);
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18001e664  push    rbp
0x18001e666  push    rbx
0x18001e667  push    rsi
0x18001e668  push    rdi
0x18001e669  lea     rbp, [rsp-3Fh]
0x18001e66e  sub     rsp, 0C8h
0x18001e675  mov     rax, cs:__security_cookie
0x18001e67c  xor     rax, rsp
0x18001e67f  mov     [rbp+57h+var_28], rax
0x18001e683  mov     rsi, rcx
0x18001e686  mov     [rbp+57h+string], 0
0x18001e68e  lea     rcx, [rbp+57h+var_88]
0x18001e692  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e697  nop
0x18001e698  lea     rcx, [rbp+57h+var_A8]
0x18001e69c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e6a1  nop
0x18001e6a2  mov     [rbp+57h+var_B8], 0
0x18001e6aa  lea     rdx, [rbp+57h+var_88]
0x18001e6ae  lea     rcx, [rbp+57h+var_A8]
0x18001e6b2  call    ?GetSystemLocaleInfo@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapPlatformConfig::GetSystemLocaleInfo(std::wstring *,std::wstring *)
0x18001e6b7  test    eax, eax
0x18001e6b9  jns     short loc_18001E6DA
0x18001e6bb  mov     r8d, 1051h
0x18001e6c1  mov     ecx, eax
0x18001e6c3  mov     r9, rsi
0x18001e6c6  lea     rdx, aServicemanager_37; "ServiceManager::WriteApprovedPFNList"
0x18001e6cd  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e6d3  mov     ebx, eax
0x18001e6d5  jmp     loc_18001E7CC
0x18001e6da  lea     rcx, [rbp+57h+var_B8]
0x18001e6de  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x18001e6e3  mov     dil, [rsi+10DDh]
0x18001e6ea  lea     rcx, [rbp+57h+var_A8]
0x18001e6ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e6f3  mov     [rbp+57h+var_B0], rax
0x18001e6f7  lea     rdx, [rbp+57h+var_B0]
0x18001e6fb  lea     rcx, [rbp+57h+var_68]
0x18001e6ff  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e704  mov     rbx, [rax+18h]
0x18001e708  lea     rcx, [rbp+57h+var_88]
0x18001e70c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e711  mov     [rbp+57h+var_B0], rax
0x18001e715  lea     rdx, [rbp+57h+var_B0]
0x18001e719  lea     rcx, [rbp+57h+var_48]
0x18001e71d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e722  lea     r9, [rbp+57h+var_B8]
0x18001e726  mov     r8b, dil
0x18001e729  mov     rdx, rbx
0x18001e72c  mov     rcx, [rax+18h]
0x18001e730  call    cs:__imp_ConfigurationManager_GetLocaleMapConfiguration
0x18001e736  test    eax, eax
0x18001e738  jns     short loc_18001E745
0x18001e73a  mov     r8d, 1057h
0x18001e740  jmp     loc_18001E6C1
0x18001e745  mov     rdi, [rbp+57h+var_B8]
0x18001e749  mov     rax, [rdi]
0x18001e74c  mov     rbx, [rax+30h]
0x18001e750  mov     rcx, [rbp+57h+string]; string
0x18001e754  call    cs:__imp_WindowsDeleteString
0x18001e75a  mov     [rbp+57h+string], 0
0x18001e762  lea     r8, [rbp+57h+string]
0x18001e766  mov     edx, 13Ch
0x18001e76b  mov     rcx, rdi
0x18001e76e  mov     rax, rbx
0x18001e771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e776  test    eax, eax
0x18001e778  jns     short loc_18001E785
0x18001e77a  mov     r8d, 105Bh
0x18001e780  jmp     loc_18001E6C1
0x18001e785  xor     edx, edx; length
0x18001e787  mov     rcx, [rbp+57h+string]; string
0x18001e78b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e791  mov     rdx, rax
0x18001e794  lea     rcx, [rbp+57h+var_68]
0x18001e798  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e79d  nop
0x18001e79e  lea     r8, [rbp+57h+var_68]
0x18001e7a2  lea     rdx, aApprovedpfnlis; "ApprovedPFNList"
0x18001e7a9  call    ?SetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::SetMapsPersistedRegString(MapsRegKeys,ushort const *,std::wstring const &)
0x18001e7ae  mov     ebx, eax
0x18001e7b0  lea     rcx, [rbp+57h+var_68]
0x18001e7b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e7b9  test    ebx, ebx
0x18001e7bb  jns     short loc_18001E7CA
0x18001e7bd  mov     r8d, 105Eh
0x18001e7c3  mov     ecx, ebx
0x18001e7c5  jmp     loc_18001E6C3
0x18001e7ca  xor     ebx, ebx
0x18001e7cc  lea     rcx, [rbp+57h+var_B8]
0x18001e7d0  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x18001e7d5  nop
0x18001e7d6  lea     rcx, [rbp+57h+var_A8]
0x18001e7da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e7df  nop
0x18001e7e0  lea     rcx, [rbp+57h+var_88]
0x18001e7e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e7e9  nop
0x18001e7ea  mov     rcx, [rbp+57h+string]; string
0x18001e7ee  call    cs:__imp_WindowsDeleteString
0x18001e7f4  mov     eax, ebx
0x18001e7f6  mov     rcx, [rbp+57h+var_28]
0x18001e7fa  xor     rcx, rsp; StackCookie
0x18001e7fd  call    __security_check_cookie
0x18001e802  add     rsp, 0C8h
0x18001e809  pop     rdi
0x18001e80a  pop     rsi
0x18001e80b  pop     rbx
0x18001e80c  pop     rbp
0x18001e80d  retn
```
