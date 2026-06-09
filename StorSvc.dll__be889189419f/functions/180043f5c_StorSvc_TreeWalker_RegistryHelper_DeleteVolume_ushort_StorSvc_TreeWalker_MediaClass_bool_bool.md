# StorSvc::TreeWalker::RegistryHelper::DeleteVolume(ushort,StorSvc::TreeWalker::MediaClass,bool,bool)

- ea: `0x180043f5c`
- end: `0x1800442ee`
- name: `?DeleteVolume@RegistryHelper@TreeWalker@StorSvc@@CAJGW4MediaClass@23@_N1@Z`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
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
- `0x1800419c0`
- `0x180043f5c`
- `0x180045b18`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180043fd6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180043fd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004415d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004415d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180044228`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180044228`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800441a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800441a1`
- `RPCRT4!RpcRevertToSelf` at `0x1800441a9`
- `RPCRT4!RpcRevertToSelf` at `0x1800441a9`
- `RPCRT4!RpcImpersonateClient` at `0x18004407f`
- `RPCRT4!RpcImpersonateClient` at `0x18004407f`

## string_xrefs

- `0x180044205`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x180044280`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::DeleteVolume(__int16 a1, unsigned int a2, char a3)
{
  const WCHAR *v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rax
  int v19; // ebx
  const WCHAR *v20; // rax
  int v21; // eax
  int phkResult; // [rsp+20h] [rbp-308h]
  HKEY hKey; // [rsp+30h] [rbp-2F8h] BYREF
  _BYTE v24[8]; // [rsp+38h] [rbp-2F0h] BYREF
  _BYTE v25[16]; // [rsp+40h] [rbp-2E8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-2D8h]
  _BYTE v27[32]; // [rsp+60h] [rbp-2C8h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-2A8h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-288h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-268h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-248h] BYREF
  WCHAR szVolumeName[264]; // [rsp+100h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  try
  {
    hKey = 0;
    std::wstring::wstring((__int64)v27, (__int64)L"A:\\");
    std::wstring::wstring(v25);
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27) = a1;
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    if ( !GetVolumeNameForVolumeMountPointW(v6, szVolumeName, 0x104u) )
      goto LABEL_3;
    v10 = std::wstring::wstring((__int64)v30, (__int64)szVolumeName);
    v11 = std::wstring::substr(v10, v29, 10);
    std::wstring::operator=(v25, v11);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
    --v26;
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
    *(_WORD *)(v12 + 2 * v13) = 0;
    if ( RpcImpersonateClient(0) )
    {
LABEL_3:
      std::wstring::_Tidy_deallocate(v25);
      std::wstring::_Tidy_deallocate(v27);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
      result = 2147500037LL;
    }
    else
    {
      v14 = L"Rejections";
      if ( !a3 )
        v14 = L"Suggestions";
      v15 = StorSvc::TreeWalker::RegistryHelper::MediaString(v31, a2);
      v16 = std::operator+<unsigned short>(
              v29,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\SuggestedFolders\\",
              v15);
      v17 = std::operator+<unsigned short>(v30, v16, L"\\");
      std::operator+<unsigned short>(v28, v17, v14);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v31);
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v24);
        RegCloseKey(hKey);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
      }
      hKey = 0;
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
      v19 = RegOpenKeyExW(HKEY_CURRENT_USER, v18, 0, 0x3000Fu, &hKey);
      RpcRevertToSelf();
      if ( v19 != 2 )
      {
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        if ( v19 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
            (const char *)(unsigned int)v19,
            phkResult);
        v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
        v21 = RegDeleteTreeW(hKey, v20);
        if ( v21 != 2 )
        {
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          if ( v21 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CF,
              (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
              (const char *)(unsigned int)v21,
              phkResult);
        }
      }
      std::wstring::_Tidy_deallocate(v28);
      std::wstring::_Tidy_deallocate(v25);
      std::wstring::_Tidy_deallocate(v27);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1D3, v7, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180043f5c  mov     [rsp+arg_0], rbx
0x180043f61  mov     [rsp+arg_10], rsi
0x180043f66  push    rdi
0x180043f67  sub     rsp, 320h
0x180043f6e  mov     rax, cs:__security_cookie
0x180043f75  xor     rax, rsp
0x180043f78  mov     [rsp+328h+var_18], rax
0x180043f80  mov     dil, r8b
0x180043f83  mov     esi, edx
0x180043f85  movzx   ebx, cx
0x180043f88  mov     [rsp+328h+hKey], 0
0x180043f91  lea     rdx, aA; "A:\\"
0x180043f98  lea     rcx, [rsp+328h+var_2C8]
0x180043f9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043fa2  nop
0x180043fa3  lea     rcx, [rsp+328h+var_2E8]
0x180043fa8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043fad  nop
0x180043fae  lea     rcx, [rsp+328h+var_2C8]
0x180043fb3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043fb8  mov     [rax], bx
0x180043fbb  lea     rcx, [rsp+328h+var_2C8]
0x180043fc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043fc5  mov     rcx, rax; lpszVolumeMountPoint
0x180043fc8  mov     r8d, 104h; cchBufferLength
0x180043fce  lea     rdx, [rsp+328h+szVolumeName]; lpszVolumeName
0x180043fd6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180043fdc  test    eax, eax
0x180043fde  jnz     short loc_18004400A
0x180043fe0  lea     rcx, [rsp+328h+var_2E8]
0x180043fe5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043fea  nop
0x180043feb  lea     rcx, [rsp+328h+var_2C8]
0x180043ff0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043ff5  nop
0x180043ff6  lea     rcx, [rsp+328h+hKey]
0x180043ffb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x180044000  mov     eax, 80004005h
0x180044005  jmp     loc_1800442C8
0x18004400a  lea     rdx, [rsp+328h+szVolumeName]
0x180044012  lea     rcx, [rsp+328h+var_268]
0x18004401a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004401f  nop
0x180044020  or      r9, 0FFFFFFFFFFFFFFFFh
0x180044024  lea     r8d, [r9+0Bh]
0x180044028  lea     rdx, [rsp+328h+var_288]
0x180044030  mov     rcx, rax
0x180044033  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180044038  nop
0x180044039  mov     rdx, rax
0x18004403c  lea     rcx, [rsp+328h+var_2E8]
0x180044041  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044046  nop
0x180044047  lea     rcx, [rsp+328h+var_288]
0x18004404f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044054  nop
0x180044055  lea     rcx, [rsp+328h+var_268]
0x18004405d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044062  mov     rdx, [rsp+328h+var_2D8]
0x180044067  dec     rdx
0x18004406a  mov     [rsp+328h+var_2D8], rdx
0x18004406f  lea     rcx, [rsp+328h+var_2E8]
0x180044074  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044079  xor     ecx, ecx; BindingHandle
0x18004407b  mov     [rax+rdx*2], cx
0x18004407f  call    cs:__imp_RpcImpersonateClient
0x180044085  test    eax, eax
0x180044087  jz      short loc_1800440B3
0x180044089  lea     rcx, [rsp+328h+var_2E8]
0x18004408e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044093  nop
0x180044094  lea     rcx, [rsp+328h+var_2C8]
0x180044099  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004409e  nop
0x18004409f  lea     rcx, [rsp+328h+hKey]
0x1800440a4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800440a9  mov     eax, 80004005h
0x1800440ae  jmp     loc_1800442C8
0x1800440b3  lea     rax, aSuggestions; "Suggestions"
0x1800440ba  lea     rbx, aRejections; "Rejections"
0x1800440c1  test    dil, dil
0x1800440c4  cmovz   rbx, rax
0x1800440c8  mov     edx, esi
0x1800440ca  lea     rcx, [rsp+328h+var_248]
0x1800440d2  call    ?MediaString@RegistryHelper@TreeWalker@StorSvc@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MediaClass@23@@Z; StorSvc::TreeWalker::RegistryHelper::MediaString(StorSvc::TreeWalker::MediaClass)
0x1800440d7  nop
0x1800440d8  mov     r8, rax
0x1800440db  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800440e2  lea     rcx, [rsp+328h+var_288]
0x1800440ea  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800440ef  nop
0x1800440f0  lea     r8, asc_180092790; "\\"
0x1800440f7  mov     rdx, rax
0x1800440fa  lea     rcx, [rsp+328h+var_268]
0x180044102  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180044107  nop
0x180044108  mov     r8, rbx
0x18004410b  mov     rdx, rax
0x18004410e  lea     rcx, [rsp+328h+var_2A8]
0x180044116  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004411b  nop
0x18004411c  lea     rcx, [rsp+328h+var_268]
0x180044124  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044129  nop
0x18004412a  lea     rcx, [rsp+328h+var_288]
0x180044132  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044137  nop
0x180044138  lea     rcx, [rsp+328h+var_248]
0x180044140  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044145  mov     rbx, [rsp+328h+hKey]
0x18004414a  test    rbx, rbx
0x18004414d  jz      short loc_18004416E
0x18004414f  lea     rcx, [rsp+328h+var_2F0]; this
0x180044154  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044159  nop
0x18004415a  mov     rcx, rbx; hKey
0x18004415d  call    cs:__imp_RegCloseKey
0x180044163  nop
0x180044164  lea     rcx, [rsp+328h+var_2F0]; this
0x180044169  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004416e  mov     [rsp+328h+hKey], 0
0x180044177  lea     rcx, [rsp+328h+var_2A8]
0x18004417f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044184  mov     rdx, rax; lpSubKey
0x180044187  lea     rax, [rsp+328h+hKey]
0x18004418c  mov     qword ptr [rsp+328h+phkResult], rax; int
0x180044191  mov     r9d, 3000Fh; samDesired
0x180044197  xor     r8d, r8d; ulOptions
0x18004419a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800441a1  call    cs:__imp_RegOpenKeyExW
0x1800441a7  mov     ebx, eax
0x1800441a9  call    cs:__imp_RpcRevertToSelf
0x1800441af  cmp     ebx, 2
0x1800441b2  jnz     short loc_1800441E9
0x1800441b4  lea     rcx, [rsp+328h+var_2A8]
0x1800441bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441c1  nop
0x1800441c2  lea     rcx, [rsp+328h+var_2E8]
0x1800441c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441cc  nop
0x1800441cd  lea     rcx, [rsp+328h+var_2C8]
0x1800441d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441d7  nop
0x1800441d8  lea     rcx, [rsp+328h+hKey]
0x1800441dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800441e2  xor     eax, eax
0x1800441e4  jmp     loc_1800442C8
0x1800441e9  test    ebx, ebx
0x1800441eb  jle     short loc_1800441F6
0x1800441ed  movzx   ebx, bx
0x1800441f0  or      ebx, 80070000h
0x1800441f6  mov     rcx, [rsp+328h]; this
0x1800441fe  test    ebx, ebx
0x180044200  jns     short loc_180044216
0x180044202  mov     r9d, ebx; char *
0x180044205  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004420c  mov     edx, 1C6h; void *
0x180044211  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180044216  lea     rcx, [rsp+328h+var_2E8]
0x18004421b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044220  mov     rdx, rax; lpSubKey
0x180044223  mov     rcx, [rsp+328h+hKey]; hKey
0x180044228  call    cs:__imp_RegDeleteTreeW
0x18004422e  cmp     eax, 2
0x180044231  jnz     short loc_180044265
0x180044233  lea     rcx, [rsp+328h+var_2A8]
0x18004423b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044240  nop
0x180044241  lea     rcx, [rsp+328h+var_2E8]
0x180044246  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004424b  nop
0x18004424c  lea     rcx, [rsp+328h+var_2C8]
0x180044251  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044256  nop
0x180044257  lea     rcx, [rsp+328h+hKey]
0x18004425c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x180044261  xor     eax, eax
0x180044263  jmp     short loc_1800442C8
0x180044265  test    eax, eax
0x180044267  jle     short loc_180044271
0x180044269  movzx   eax, ax
0x18004426c  or      eax, 80070000h
0x180044271  mov     rcx, [rsp+328h]; this
0x180044279  test    eax, eax
0x18004427b  jns     short loc_180044292
0x18004427d  mov     r9d, eax; char *
0x180044280  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180044287  mov     edx, 1CFh; void *
0x18004428c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180044292  lea     rcx, [rsp+328h+var_2A8]
0x18004429a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004429f  nop
0x1800442a0  lea     rcx, [rsp+328h+var_2E8]
0x1800442a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800442aa  nop
0x1800442ab  lea     rcx, [rsp+328h+var_2C8]
0x1800442b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800442b5  nop
0x1800442b6  lea     rcx, [rsp+328h+hKey]
0x1800442bb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800442c0  xor     eax, eax
0x1800442c2  jmp     short loc_1800442C8
0x1800442c4  mov     eax, dword ptr [rsp+328h+hKey]
0x1800442c8  mov     rcx, [rsp+328h+var_18]
0x1800442d0  xor     rcx, rsp; StackCookie
0x1800442d3  call    __security_check_cookie
0x1800442d8  lea     r11, [rsp+328h+var_8]
0x1800442e0  mov     rbx, [r11+10h]
0x1800442e4  mov     rsi, [r11+20h]
0x1800442e8  mov     rsp, r11
0x1800442eb  pop     rdi
0x1800442ec  retn
```
