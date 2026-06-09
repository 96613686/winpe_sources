# OSIntegration::DEH::OnDemandHotspotExtensionHandler::_CleanupOdhNetworks(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009f090`
- end: `0x18009f471`
- name: `?_CleanupOdhNetworks@OnDemandHotspotExtensionHandler@DEH@OSIntegration@@AEAAJQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009ecb4`

## callees

- `0x18003193c`
- `0x180033ca0`
- `0x180061c78`
- `0x180063f20`
- `0x180064960`
- `0x180066780`
- `0x180069eb4`
- `0x18006d134`
- `0x180071178`
- `0x180072dcc`
- `0x180093e88`
- `0x1800982a8`
- `0x18009d978`
- `0x18009f090`
- `0x1800aed10`
- `0x1800af918`
- `0x180100e48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009f2c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009f2c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009f0e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009f0e6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009f15a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009f15a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009f193`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18009f193`

## string_xrefs

- `0x18009f1ae`: `onecore\admin\appmodel\osim\src\deh\ondemandhotspot\ondemandhotspotextensionhandler.cpp`
- `0x18009f1f3`: `onecore\admin\appmodel\osim\src\deh\ondemandhotspot\ondemandhotspotextensionhandler.cpp`
- `0x18009f344`: `onecore\admin\appmodel\osim\src\deh\ondemandhotspot\ondemandhotspotextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::OnDemandHotspotExtensionHandler::_CleanupOdhNetworks(
        __int64 a1,
        HKEY a2,
        __int64 a3)
{
  HKEY *v5; // rax
  DWORD i; // esi
  unsigned int v8; // eax
  LPCWSTR v9; // rbx
  LPCWSTR v10; // rdi
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  char *v14; // rdi
  signed __int64 v15; // rcx
  char *v16; // rax
  signed __int64 v17; // rbx
  unsigned int ValueW; // edi
  char *v19; // r14
  size_t v20; // rbx
  unsigned int v21; // ebx
  __int64 v22; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-2F8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-2F8h]
  DWORD cchName; // [rsp+40h] [rbp-2D8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-2D0h] BYREF
  PVOID pvData[2]; // [rsp+50h] [rbp-2C8h] BYREF
  _BYTE *v28; // [rsp+60h] [rbp-2B8h]
  DWORD pcbData; // [rsp+68h] [rbp-2B0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp-2A8h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-290h] BYREF
  _BYTE v32[40]; // [rsp+A8h] [rbp-270h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  hKey = 0;
  v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( RegOpenKeyExW(a2, L"Software\\Microsoft\\WcmSvc\\Tethering\\Devices\\AppInjected", 0, 0x20019u, v5) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(lpSubKey);
  for ( i = 0; ; ++i )
  {
    memset_0(Name, 0, 0x208u);
    cchName = 260;
    v8 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v8 == 259 )
    {
      v9 = lpSubKey[0];
      v10 = lpSubKey[1];
      while ( v9 != v10 )
      {
        if ( *((_QWORD *)v9 + 3) <= 7u )
          v11 = v9;
        else
          v11 = *(const WCHAR **)v9;
        v12 = RegDeleteKeyExW(hKey, v11, 0, 0);
        if ( v12 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0xA2,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\ondemandhotspot\\ondemandhotspotextensionhandler.cpp",
            (const char *)v12,
            phkResult);
        v9 += 16;
      }
      std::vector<std::wstring>::_Tidy(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    if ( v8 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x8A,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\ondemandhotspot\\ondemandhotspotextensionhandler.cpp",
              (const char *)v8,
              phkResult);
      std::vector<std::wstring>::_Tidy(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v13;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(pvData);
    pcbData = 0;
    v14 = (char *)pvData[1];
    v15 = (char *)pvData[1] - (char *)pvData[0];
    if ( (PVOID)((char *)pvData[1] - (char *)pvData[0]) <= (PVOID)1 )
    {
      if ( pvData[1] != pvData[0] )
        goto LABEL_23;
      if ( v28 == pvData[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pvData, 1);
        goto LABEL_23;
      }
      v17 = 1 - v15;
      memset_0(pvData[1], 0, 1 - v15);
      v16 = &v14[v17];
    }
    else
    {
      v16 = (char *)pvData[0] + 1;
    }
    pvData[1] = v16;
    do
    {
LABEL_23:
      ValueW = RegGetValueW(hKey, Name, L"AUMID", 2u, 0, pvData[0], &pcbData);
      v19 = (char *)pvData[1];
      if ( (PVOID)pcbData >= (PVOID)((char *)pvData[1] - (char *)pvData[0]) )
      {
        if ( (PVOID)pcbData > (PVOID)((char *)pvData[1] - (char *)pvData[0]) )
        {
          if ( pcbData <= (unsigned __int64)(v28 - (char *)pvData[0]) )
          {
            v20 = pcbData - (unsigned __int64)((char *)pvData[1] - (char *)pvData[0]);
            memset_0(pvData[1], 0, v20);
            pvData[1] = &v19[v20];
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pvData, pcbData);
          }
        }
      }
      else
      {
        pvData[1] = (char *)pvData[0] + pcbData;
      }
    }
    while ( ValueW == 234 );
    if ( ValueW )
      break;
    std::wstring::wstring(v31);
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)pvData[0] + v22) );
    std::wstring::_Assign<unsigned short>(v31);
    if ( std::wstring::find(v31, a3) != -1 )
    {
      std::wstring::wstring(v32, Name, cchName);
      std::vector<std::wstring>::push_back(lpSubKey, v32);
      std::wstring::_Tidy_deallocate(v32);
    }
    std::wstring::_Tidy_deallocate(v31);
    if ( pvData[0] )
      std::_Deallocate<16>(pvData[0], v28 - (char *)pvData[0]);
  }
  v21 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x94,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\ondemandhotspot\\ondemandhotspotextensionhandler.cpp",
          (const char *)ValueW,
          phkResulta);
  if ( pvData[0] )
  {
    std::_Deallocate<16>(pvData[0], v28 - (char *)pvData[0]);
    *(_OWORD *)pvData = 0;
    v28 = 0;
  }
  std::vector<std::wstring>::_Tidy(lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v21;
}

```

## disassembly

```asm
0x18009f090  mov     [rsp+arg_0], rbx
0x18009f095  push    rsi
0x18009f096  push    rdi
0x18009f097  push    r12
0x18009f099  push    r14
0x18009f09b  push    r15
0x18009f09d  sub     rsp, 2F0h
0x18009f0a4  mov     rax, cs:__security_cookie
0x18009f0ab  xor     rax, rsp
0x18009f0ae  mov     [rsp+318h+var_38], rax
0x18009f0b6  mov     r15, r8
0x18009f0b9  mov     rbx, rdx
0x18009f0bc  xor     r12d, r12d
0x18009f0bf  mov     [rsp+318h+hKey], r12
0x18009f0c4  lea     rcx, [rsp+318h+hKey]
0x18009f0c9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18009f0ce  mov     [rsp+318h+phkResult], rax; phkResult
0x18009f0d3  mov     r9d, 20019h; samDesired
0x18009f0d9  xor     r8d, r8d; ulOptions
0x18009f0dc  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\WcmSvc\\Tethering"...
0x18009f0e3  mov     rcx, rbx; hKey
0x18009f0e6  call    cs:__imp_RegOpenKeyExW
0x18009f0ed  nop     dword ptr [rax+rax+00h]
0x18009f0f2  test    eax, eax
0x18009f0f4  jz      short loc_18009F107
0x18009f0f6  lea     rcx, [rsp+318h+hKey]
0x18009f0fb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f100  xor     eax, eax
0x18009f102  jmp     loc_18009F448
0x18009f107  lea     rcx, [rsp+318h+lpSubKey]
0x18009f10c  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>> &&)
0x18009f111  nop
0x18009f112  mov     esi, r12d
0x18009f115  xor     edx, edx; Val
0x18009f117  mov     r8d, 208h; Size
0x18009f11d  lea     rcx, [rsp+318h+Name]; void *
0x18009f125  call    memset_0
0x18009f12a  mov     [rsp+318h+cchName], 104h
0x18009f132  mov     [rsp+318h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18009f137  mov     [rsp+318h+lpcchClass], r12; lpcchClass
0x18009f13c  mov     [rsp+318h+lpClass], r12; lpClass
0x18009f141  mov     [rsp+318h+phkResult], r12; unsigned int
0x18009f146  lea     r9, [rsp+318h+cchName]; lpcchName
0x18009f14b  lea     r8, [rsp+318h+Name]; lpName
0x18009f153  mov     edx, esi; dwIndex
0x18009f155  mov     rcx, [rsp+318h+hKey]; hKey
0x18009f15a  call    cs:__imp_RegEnumKeyExW
0x18009f161  nop     dword ptr [rax+rax+00h]
0x18009f166  cmp     eax, 103h
0x18009f16b  jnz     short loc_18009F1E4
0x18009f16d  mov     rbx, [rsp+318h+lpSubKey]
0x18009f172  mov     rdi, [rsp+318h+var_2A0]
0x18009f177  jmp     short loc_18009F1C3
0x18009f179  cmp     qword ptr [rbx+18h], 7
0x18009f17e  jbe     short loc_18009F185
0x18009f180  mov     rdx, [rbx]
0x18009f183  jmp     short loc_18009F188
0x18009f185  mov     rdx, rbx; lpSubKey
0x18009f188  xor     r9d, r9d; Reserved
0x18009f18b  xor     r8d, r8d; samDesired
0x18009f18e  mov     rcx, [rsp+318h+hKey]; hKey
0x18009f193  call    cs:__imp_RegDeleteKeyExW
0x18009f19a  nop     dword ptr [rax+rax+00h]
0x18009f19f  mov     rcx, [rsp+318h]; this
0x18009f1a7  test    eax, eax
0x18009f1a9  jz      short loc_18009F1BF
0x18009f1ab  mov     r9d, eax; char *
0x18009f1ae  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009f1b5  mov     edx, 0A2h; void *
0x18009f1ba  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18009f1bf  add     rbx, 20h ; ' '
0x18009f1c3  cmp     rbx, rdi
0x18009f1c6  jnz     short loc_18009F179
0x18009f1c8  lea     rcx, [rsp+318h+lpSubKey]
0x18009f1cd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009f1d2  nop
0x18009f1d3  lea     rcx, [rsp+318h+hKey]
0x18009f1d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f1dd  xor     eax, eax
0x18009f1df  jmp     loc_18009F448
0x18009f1e4  test    eax, eax
0x18009f1e6  jz      short loc_18009F222
0x18009f1e8  mov     rcx, [rsp+318h]; this
0x18009f1f0  mov     r9d, eax; char *
0x18009f1f3  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009f1fa  mov     edx, 8Ah; void *
0x18009f1ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009f204  mov     ebx, eax
0x18009f206  lea     rcx, [rsp+318h+lpSubKey]
0x18009f20b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009f210  nop
0x18009f211  lea     rcx, [rsp+318h+hKey]
0x18009f216  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f21b  mov     eax, ebx
0x18009f21d  jmp     loc_18009F448
0x18009f222  lea     rcx, [rsp+318h+pvData]
0x18009f227  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@V?$variant@VEntryTree@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>> &&)
0x18009f22c  nop
0x18009f22d  mov     [rsp+318h+pcbData], r12d
0x18009f232  mov     rdx, [rsp+318h+pvData]
0x18009f237  mov     rdi, [rsp+318h+pvData+8]
0x18009f23c  mov     rcx, rdi
0x18009f23f  sub     rcx, rdx
0x18009f242  cmp     rcx, 1
0x18009f246  jbe     short loc_18009F24E
0x18009f248  lea     rax, [rdx+1]
0x18009f24c  jmp     short loc_18009F288
0x18009f24e  jnb     short loc_18009F28D
0x18009f250  mov     rax, [rsp+318h+var_2B8]
0x18009f255  sub     rax, rdx
0x18009f258  cmp     rax, 1
0x18009f25c  jnb     short loc_18009F26F
0x18009f25e  mov     edx, 1
0x18009f263  lea     rcx, [rsp+318h+pvData]
0x18009f268  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18009f26d  jmp     short loc_18009F28D
0x18009f26f  mov     ebx, 1
0x18009f274  sub     rbx, rcx
0x18009f277  mov     r8, rbx; Size
0x18009f27a  xor     edx, edx; Val
0x18009f27c  mov     rcx, rdi; void *
0x18009f27f  call    memset_0
0x18009f284  lea     rax, [rbx+rdi]
0x18009f288  mov     [rsp+318h+pvData+8], rax
0x18009f28d  lea     rax, [rsp+318h+pcbData]
0x18009f292  mov     [rsp+318h+lpcchClass], rax; pcbData
0x18009f297  mov     rax, [rsp+318h+pvData]
0x18009f29c  mov     [rsp+318h+lpClass], rax; pvData
0x18009f2a1  mov     [rsp+318h+phkResult], r12; unsigned int
0x18009f2a6  mov     r9d, 2; dwFlags
0x18009f2ac  lea     r8, aAumid; "AUMID"
0x18009f2b3  lea     rdx, [rsp+318h+Name]; lpSubKey
0x18009f2bb  mov     rcx, [rsp+318h+hKey]; hkey
0x18009f2c0  call    cs:__imp_RegGetValueW
0x18009f2c7  nop     dword ptr [rax+rax+00h]
0x18009f2cc  mov     edi, eax
0x18009f2ce  mov     ebx, [rsp+318h+pcbData]
0x18009f2d2  mov     rdx, [rsp+318h+pvData]
0x18009f2d7  mov     r14, [rsp+318h+pvData+8]
0x18009f2dc  mov     rcx, r14
0x18009f2df  sub     rcx, rdx
0x18009f2e2  cmp     rbx, rcx
0x18009f2e5  jnb     short loc_18009F2F2
0x18009f2e7  lea     rcx, [rbx+rdx]
0x18009f2eb  mov     [rsp+318h+pvData+8], rcx
0x18009f2f0  jmp     short loc_18009F329
0x18009f2f2  jbe     short loc_18009F329
0x18009f2f4  mov     rax, [rsp+318h+var_2B8]
0x18009f2f9  sub     rax, rdx
0x18009f2fc  cmp     rbx, rax
0x18009f2ff  jbe     short loc_18009F310
0x18009f301  mov     rdx, rbx
0x18009f304  lea     rcx, [rsp+318h+pvData]
0x18009f309  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18009f30e  jmp     short loc_18009F329
0x18009f310  sub     rbx, rcx
0x18009f313  mov     r8, rbx; Size
0x18009f316  xor     edx, edx; Val
0x18009f318  mov     rcx, r14; void *
0x18009f31b  call    memset_0
0x18009f320  lea     rax, [rbx+r14]
0x18009f324  mov     [rsp+318h+pvData+8], rax
0x18009f329  cmp     edi, 0EAh
0x18009f32f  jz      loc_18009F28D
0x18009f335  test    edi, edi
0x18009f337  jz      short loc_18009F398
0x18009f339  mov     rcx, [rsp+318h]; this
0x18009f341  mov     r9d, edi; char *
0x18009f344  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009f34b  mov     edx, 94h; void *
0x18009f350  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009f355  mov     ebx, eax
0x18009f357  mov     rcx, [rsp+318h+pvData]
0x18009f35c  test    rcx, rcx
0x18009f35f  jz      short loc_18009F37C
0x18009f361  mov     rdx, [rsp+318h+var_2B8]
0x18009f366  sub     rdx, rcx
0x18009f369  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009f36e  xorps   xmm0, xmm0
0x18009f371  movdqu  xmmword ptr [rsp+318h+pvData], xmm0
0x18009f377  mov     [rsp+318h+var_2B8], r12
0x18009f37c  lea     rcx, [rsp+318h+lpSubKey]
0x18009f381  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18009f386  nop
0x18009f387  lea     rcx, [rsp+318h+hKey]
0x18009f38c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f391  mov     eax, ebx
0x18009f393  jmp     loc_18009F448
0x18009f398  lea     rcx, [rsp+318h+var_290]
0x18009f3a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009f3a5  nop
0x18009f3a6  mov     rdx, [rsp+318h+pvData]
0x18009f3ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009f3af  inc     r8
0x18009f3b2  cmp     [rdx+r8*2], r12w
0x18009f3b7  jnz     short loc_18009F3AF
0x18009f3b9  lea     rcx, [rsp+318h+var_290]
0x18009f3c1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009f3c6  mov     rdx, r15
0x18009f3c9  lea     rcx, [rsp+318h+var_290]
0x18009f3d1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18009f3d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009f3da  jz      short loc_18009F418
0x18009f3dc  mov     r8d, [rsp+318h+cchName]
0x18009f3e1  lea     rdx, [rsp+318h+Name]
0x18009f3e9  lea     rcx, [rsp+318h+var_270]
0x18009f3f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18009f3f6  nop
0x18009f3f7  lea     rdx, [rsp+318h+var_270]
0x18009f3ff  lea     rcx, [rsp+318h+lpSubKey]
0x18009f404  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18009f409  nop
0x18009f40a  lea     rcx, [rsp+318h+var_270]
0x18009f412  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f417  nop
0x18009f418  lea     rcx, [rsp+318h+var_290]
0x18009f420  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f425  nop
0x18009f426  mov     rcx, [rsp+318h+pvData]
0x18009f42b  test    rcx, rcx
0x18009f42e  jz      short loc_18009F43D
0x18009f430  mov     rdx, [rsp+318h+var_2B8]
0x18009f435  sub     rdx, rcx
0x18009f438  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009f43d  inc     esi
0x18009f43f  jmp     loc_18009F115
0x18009f444  mov     eax, [rsp+318h+cchName]
0x18009f448  mov     rcx, [rsp+318h+var_38]
0x18009f450  xor     rcx, rsp; StackCookie
0x18009f453  call    __security_check_cookie
0x18009f458  mov     rbx, [rsp+318h+arg_0]
0x18009f460  add     rsp, 2F0h
0x18009f467  pop     r15
0x18009f469  pop     r14
0x18009f46b  pop     r12
0x18009f46d  pop     rdi
0x18009f46e  pop     rsi
0x18009f46f  retn
```
