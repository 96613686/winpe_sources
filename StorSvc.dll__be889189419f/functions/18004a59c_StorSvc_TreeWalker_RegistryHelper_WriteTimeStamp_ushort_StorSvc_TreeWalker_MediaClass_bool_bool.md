# StorSvc::TreeWalker::RegistryHelper::WriteTimeStamp(ushort,StorSvc::TreeWalker::MediaClass,bool,bool)

- ea: `0x18004a59c`
- end: `0x18004a91b`
- name: `?WriteTimeStamp@RegistryHelper@TreeWalker@StorSvc@@CAJGW4MediaClass@23@_N1@Z`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180049a08`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180019bc4`
- `0x180019d34`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x180039f6c`
- `0x18003c1c0`
- `0x18003d054`
- `0x18004196c`
- `0x1800419c0`
- `0x180045b18`
- `0x18004a59c`
- `0x18004b84c`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004a617`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004a617`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a840`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a840`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a8b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a8b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a7dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a7dd`
- `RPCRT4!RpcRevertToSelf` at `0x18004a862`
- `RPCRT4!RpcRevertToSelf` at `0x18004a862`
- `RPCRT4!RpcImpersonateClient` at `0x18004a6c3`
- `RPCRT4!RpcImpersonateClient` at `0x18004a6c3`

## string_xrefs

- `0x18004a877`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::WriteTimeStamp(__int16 a1, unsigned int a2)
{
  const WCHAR *v4; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rax
  LSTATUS v18; // eax
  signed int v19; // ebx
  LSTATUS v20; // eax
  unsigned int v21; // ebx
  int dwOptions; // [rsp+20h] [rbp-378h]
  HKEY hKey; // [rsp+50h] [rbp-348h] BYREF
  _BYTE v24[8]; // [rsp+58h] [rbp-340h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-338h] BYREF
  _BYTE v26[16]; // [rsp+68h] [rbp-330h] BYREF
  __int64 v27; // [rsp+78h] [rbp-320h]
  _BYTE v28[32]; // [rsp+88h] [rbp-310h] BYREF
  _BYTE v29[32]; // [rsp+A8h] [rbp-2F0h] BYREF
  _BYTE v30[32]; // [rsp+C8h] [rbp-2D0h] BYREF
  _BYTE v31[32]; // [rsp+E8h] [rbp-2B0h] BYREF
  _BYTE v32[32]; // [rsp+108h] [rbp-290h] BYREF
  _BYTE v33[32]; // [rsp+128h] [rbp-270h] BYREF
  _BYTE v34[40]; // [rsp+148h] [rbp-250h] BYREF
  WCHAR szVolumeName[264]; // [rsp+170h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  try
  {
    hKey = 0;
    std::wstring::wstring((__int64)v28, (__int64)L"A:\\");
    std::wstring::wstring(v26);
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28) = a1;
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    if ( !GetVolumeNameForVolumeMountPointW(v4, szVolumeName, 0x104u) )
      goto LABEL_3;
    v8 = std::wstring::wstring((__int64)v30, (__int64)szVolumeName);
    v9 = std::wstring::substr(v8, v29, 10);
    std::wstring::operator=(v26, v9);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
    --v27;
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    *(_WORD *)(v10 + 2 * v11) = 0;
    if ( RpcImpersonateClient(0) )
    {
LABEL_3:
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
      result = 2147500037LL;
    }
    else
    {
      v12 = StorSvc::TreeWalker::RegistryHelper::MediaString(v34, a2);
      v13 = std::operator+<unsigned short>(
              v33,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\SuggestedFolders\\",
              v12);
      v14 = std::operator+<unsigned short>(v32, v13, L"\\");
      v15 = std::operator+<unsigned short>(v31, v14, L"Suggestions");
      v16 = std::operator+<unsigned short>(v30, v15, L"\\");
      std::operator+<unsigned short>(v29, v16, v26);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v31);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v33);
      std::wstring::_Tidy_deallocate(v34);
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v24);
        RegCloseKey(hKey);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
      }
      hKey = 0;
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      v18 = RegCreateKeyExW(HKEY_CURRENT_USER, v17, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      std::wstring::_Tidy_deallocate(v29);
      RpcRevertToSelf();
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x241,
          (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
          (const char *)(unsigned int)v19,
          dwOptions);
      *(_QWORD *)Data = time((time_t *const)retaddr);
      v20 = RegSetValueExW(hKey, L"timeStamp", 0, 0xBu, Data, 8u);
      v21 = v20;
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
      result = v21;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x246, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x18004a59c  mov     [rsp+arg_0], rbx
0x18004a5a1  push    rdi
0x18004a5a2  sub     rsp, 390h
0x18004a5a9  mov     rax, cs:__security_cookie
0x18004a5b0  xor     rax, rsp
0x18004a5b3  mov     [rsp+398h+var_18], rax
0x18004a5bb  mov     edi, edx
0x18004a5bd  movzx   ebx, cx
0x18004a5c0  mov     [rsp+398h+hKey], 0
0x18004a5c9  lea     rdx, aA; "A:\\"
0x18004a5d0  lea     rcx, [rsp+398h+var_310]
0x18004a5d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004a5dd  nop
0x18004a5de  lea     rcx, [rsp+398h+var_330]
0x18004a5e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004a5e8  nop
0x18004a5e9  lea     rcx, [rsp+398h+var_310]
0x18004a5f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a5f6  mov     [rax], bx
0x18004a5f9  lea     rcx, [rsp+398h+var_310]
0x18004a601  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a606  mov     rcx, rax; lpszVolumeMountPoint
0x18004a609  mov     r8d, 104h; cchBufferLength
0x18004a60f  lea     rdx, [rsp+398h+szVolumeName]; lpszVolumeName
0x18004a617  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004a61d  test    eax, eax
0x18004a61f  jnz     short loc_18004A64E
0x18004a621  lea     rcx, [rsp+398h+var_330]
0x18004a626  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a62b  nop
0x18004a62c  lea     rcx, [rsp+398h+var_310]
0x18004a634  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a639  nop
0x18004a63a  lea     rcx, [rsp+398h+hKey]
0x18004a63f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x18004a644  mov     eax, 80004005h
0x18004a649  jmp     loc_18004A8F9
0x18004a64e  lea     rdx, [rsp+398h+szVolumeName]
0x18004a656  lea     rcx, [rsp+398h+var_2D0]
0x18004a65e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004a663  nop
0x18004a664  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004a668  lea     r8d, [r9+0Bh]
0x18004a66c  lea     rdx, [rsp+398h+var_2F0]
0x18004a674  mov     rcx, rax
0x18004a677  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18004a67c  nop
0x18004a67d  mov     rdx, rax
0x18004a680  lea     rcx, [rsp+398h+var_330]
0x18004a685  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004a68a  nop
0x18004a68b  lea     rcx, [rsp+398h+var_2F0]
0x18004a693  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a698  nop
0x18004a699  lea     rcx, [rsp+398h+var_2D0]
0x18004a6a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a6a6  mov     rdx, [rsp+398h+var_320]
0x18004a6ab  dec     rdx
0x18004a6ae  mov     [rsp+398h+var_320], rdx
0x18004a6b3  lea     rcx, [rsp+398h+var_330]
0x18004a6b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a6bd  xor     ecx, ecx; BindingHandle
0x18004a6bf  mov     [rax+rdx*2], cx
0x18004a6c3  call    cs:__imp_RpcImpersonateClient
0x18004a6c9  test    eax, eax
0x18004a6cb  jz      short loc_18004A6FA
0x18004a6cd  lea     rcx, [rsp+398h+var_330]
0x18004a6d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a6d7  nop
0x18004a6d8  lea     rcx, [rsp+398h+var_310]
0x18004a6e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a6e5  nop
0x18004a6e6  lea     rcx, [rsp+398h+hKey]
0x18004a6eb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x18004a6f0  mov     eax, 80004005h
0x18004a6f5  jmp     loc_18004A8F9
0x18004a6fa  mov     edx, edi
0x18004a6fc  lea     rcx, [rsp+398h+var_250]
0x18004a704  call    ?MediaString@RegistryHelper@TreeWalker@StorSvc@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MediaClass@23@@Z; StorSvc::TreeWalker::RegistryHelper::MediaString(StorSvc::TreeWalker::MediaClass)
0x18004a709  nop
0x18004a70a  mov     r8, rax
0x18004a70d  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004a714  lea     rcx, [rsp+398h+var_270]
0x18004a71c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18004a721  nop
0x18004a722  lea     r8, asc_180092790; "\\"
0x18004a729  mov     rdx, rax
0x18004a72c  lea     rcx, [rsp+398h+var_290]
0x18004a734  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004a739  nop
0x18004a73a  lea     r8, aSuggestions; "Suggestions"
0x18004a741  mov     rdx, rax
0x18004a744  lea     rcx, [rsp+398h+var_2B0]
0x18004a74c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004a751  nop
0x18004a752  lea     r8, asc_180092790; "\\"
0x18004a759  mov     rdx, rax
0x18004a75c  lea     rcx, [rsp+398h+var_2D0]
0x18004a764  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004a769  nop
0x18004a76a  lea     r8, [rsp+398h+var_330]
0x18004a76f  mov     rdx, rax
0x18004a772  lea     rcx, [rsp+398h+var_2F0]
0x18004a77a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004a77f  nop
0x18004a780  lea     rcx, [rsp+398h+var_2D0]
0x18004a788  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a78d  nop
0x18004a78e  lea     rcx, [rsp+398h+var_2B0]
0x18004a796  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a79b  nop
0x18004a79c  lea     rcx, [rsp+398h+var_290]
0x18004a7a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a7a9  nop
0x18004a7aa  lea     rcx, [rsp+398h+var_270]
0x18004a7b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a7b7  nop
0x18004a7b8  lea     rcx, [rsp+398h+var_250]
0x18004a7c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a7c5  mov     rbx, [rsp+398h+hKey]
0x18004a7ca  test    rbx, rbx
0x18004a7cd  jz      short loc_18004A7EE
0x18004a7cf  lea     rcx, [rsp+398h+var_340]; this
0x18004a7d4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004a7d9  nop
0x18004a7da  mov     rcx, rbx; hKey
0x18004a7dd  call    cs:__imp_RegCloseKey
0x18004a7e3  nop
0x18004a7e4  lea     rcx, [rsp+398h+var_340]; this
0x18004a7e9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004a7ee  mov     [rsp+398h+hKey], 0
0x18004a7f7  lea     rcx, [rsp+398h+var_2F0]
0x18004a7ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a804  mov     rdx, rax; lpSubKey
0x18004a807  mov     [rsp+398h+lpdwDisposition], 0; lpdwDisposition
0x18004a810  lea     rax, [rsp+398h+hKey]
0x18004a815  mov     [rsp+398h+phkResult], rax; phkResult
0x18004a81a  mov     [rsp+398h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004a823  mov     [rsp+398h+samDesired], 20006h; samDesired
0x18004a82b  mov     [rsp+398h+dwOptions], 0; int
0x18004a833  xor     r9d, r9d; lpClass
0x18004a836  xor     r8d, r8d; Reserved
0x18004a839  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004a840  call    cs:__imp_RegCreateKeyExW
0x18004a846  mov     ebx, eax
0x18004a848  test    eax, eax
0x18004a84a  jle     short loc_18004A855
0x18004a84c  movzx   ebx, ax
0x18004a84f  or      ebx, 80070000h
0x18004a855  lea     rcx, [rsp+398h+var_2F0]
0x18004a85d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a862  call    cs:__imp_RpcRevertToSelf
0x18004a868  mov     rcx, [rsp+398h]; this
0x18004a870  test    ebx, ebx
0x18004a872  jns     short loc_18004A888
0x18004a874  mov     r9d, ebx; char *
0x18004a877  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004a87e  mov     edx, 241h; void *
0x18004a883  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004a888  call    time
0x18004a88d  mov     qword ptr [rsp+398h+Data], rax
0x18004a892  mov     [rsp+398h+samDesired], 8; cbData
0x18004a89a  lea     rax, [rsp+398h+Data]
0x18004a89f  mov     qword ptr [rsp+398h+dwOptions], rax; lpData
0x18004a8a4  mov     r9d, 0Bh; dwType
0x18004a8aa  xor     r8d, r8d; Reserved
0x18004a8ad  lea     rdx, aTimestamp; "timeStamp"
0x18004a8b4  mov     rcx, [rsp+398h+hKey]; hKey
0x18004a8b9  call    cs:__imp_RegSetValueExW
0x18004a8bf  mov     ebx, eax
0x18004a8c1  test    eax, eax
0x18004a8c3  jle     short loc_18004A8CE
0x18004a8c5  movzx   ebx, ax
0x18004a8c8  or      ebx, 80070000h
0x18004a8ce  lea     rcx, [rsp+398h+var_330]
0x18004a8d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a8d8  nop
0x18004a8d9  lea     rcx, [rsp+398h+var_310]
0x18004a8e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a8e6  nop
0x18004a8e7  lea     rcx, [rsp+398h+hKey]
0x18004a8ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x18004a8f1  mov     eax, ebx
0x18004a8f3  jmp     short loc_18004A8F9
0x18004a8f5  mov     eax, dword ptr [rsp+398h+hKey]
0x18004a8f9  mov     rcx, [rsp+398h+var_18]
0x18004a901  xor     rcx, rsp; StackCookie
0x18004a904  call    __security_check_cookie
0x18004a909  mov     rbx, [rsp+398h+arg_0]
0x18004a911  add     rsp, 390h
0x18004a918  pop     rdi
0x18004a919  retn
```
