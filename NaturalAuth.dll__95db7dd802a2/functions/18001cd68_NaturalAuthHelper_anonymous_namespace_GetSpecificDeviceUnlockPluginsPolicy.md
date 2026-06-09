# NaturalAuthHelper::_anonymous_namespace_::GetSpecificDeviceUnlockPluginsPolicy

- ea: `0x18001cd68`
- end: `0x18001d178`
- name: `NaturalAuthHelper::_anonymous_namespace_::GetSpecificDeviceUnlockPluginsPolicy`
- size: `1040`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cc54`

## callees

- `0x180004170`
- `0x18000cab8`
- `0x18000d564`
- `0x18000d8c0`
- `0x18000d900`
- `0x18000daac`
- `0x18000eca4`
- `0x180010ba0`
- `0x180010dcc`
- `0x1800110ac`
- `0x180011c8c`
- `0x180011cd0`
- `0x180011cf4`
- `0x180011e7c`
- `0x180011f44`
- `0x180012880`
- `0x180012a48`
- `0x180012b74`
- `0x180012ce0`
- `0x1800131b0`
- `0x180013584`
- `0x180019bbc`
- `0x18001a9a0`
- `0x18001aa2c`
- `0x18001b734`
- `0x18001c070`
- `0x18001cd68`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18001d0e5`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18001d0e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cee6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cee6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce44`

## string_xrefs

- `0x18001ce84`: `Plugins`
- `0x18001ced8`: `Plugins`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NaturalAuthHelper::_anonymous_namespace_::GetSpecificDeviceUnlockPluginsPolicy(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  unsigned int ValueW; // ebx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[256]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+190h] [rbp+90h]
  __int64 v30; // [rsp+198h] [rbp+98h]
  HKEY *p_hkey; // [rsp+1A0h] [rbp+A0h] BYREF
  HKEY phkResult; // [rsp+1A8h] [rbp+A8h] BYREF
  char v33; // [rsp+1B0h] [rbp+B0h]
  _BYTE v34[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v35[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v36[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v37[40]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v38[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v39[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v40[40]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v41[128]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v29 = a2;
  v30 = a3;
  hkey = 0;
  std::wstring::wstring(v34, a1);
  v7 = std::_WChar_traits<unsigned short>::length(L"\\");
  std::wstring::_Append<unsigned short>(v34, v8, v7);
  v9 = std::_WChar_traits<unsigned short>::length(L"DeviceUnlock");
  std::wstring::_Append<unsigned short>(v34, v10, v9);
  p_hkey = &hkey;
  phkResult = 0;
  v33 = 1;
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( !ValueW )
  {
    pcbData = 0;
    ValueW = RegGetValueW(hkey, 0, L"Plugins", 2u, 0, 0, &pcbData);
    if ( !ValueW )
    {
      std::vector<unsigned short>::vector<unsigned short>(pvData, ((unsigned __int64)pcbData >> 1) + 1);
      ValueW = RegGetValueW(hkey, 0, L"Plugins", 2u, 0, pvData[0], &pcbData);
      if ( !ValueW )
      {
        std::wstring::wstring(v39, pvData[0]);
        std::wstring::wstring(v36);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
          v28,
          v39);
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v41);
        while ( 1 )
        {
          v22 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v28, v36);
          if ( !(unsigned __int8)std::ios_base::operator bool(v22 + *(int *)(*(_QWORD *)v22 + 4LL)) )
            break;
          v13 = std::operator+<char>(v37, qword_18005F8E0, a2);
          std::operator+<char>(v35, v13, qword_18005F880);
          std::string::_Tidy_deallocate(v37);
          v14 = std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(
                  v27,
                  qword_18005F960,
                  1);
          v15 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
                  v41,
                  v40,
                  v36);
          std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(
            &p_hkey,
            v15,
            v14,
            v35);
          std::string::_Tidy_deallocate(v40);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v27);
          v16 = std::operator+<char>(v38, qword_18005F8A0, a3);
          v17 = std::operator+<char>(v37, v16, qword_18005F8C0);
          std::string::operator=(v35, v17);
          std::string::_Tidy_deallocate(v37);
          std::string::_Tidy_deallocate(v38);
          v18 = std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(
                  v37,
                  qword_18005F940,
                  1);
          v19 = std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(
                  v38,
                  &p_hkey,
                  v18,
                  v35);
          std::string::operator=(&p_hkey, v19);
          std::string::_Tidy_deallocate(v38);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v37);
          v21 = *(_QWORD *)(a4 + 8);
          if ( v21 == *(_QWORD *)(a4 + 16) )
          {
            std::vector<std::string>::_Emplace_reallocate<std::string const &>(a4, v21, &p_hkey);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::string,void *>>>::construct<std::string,std::string const &>(
              v20,
              v21,
              &p_hkey);
            *(_QWORD *)(a4 + 8) += 32LL;
          }
          std::string::_Tidy_deallocate(&p_hkey);
          std::string::_Tidy_deallocate(v35);
        }
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v41);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v28);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v39);
        ValueW = 0;
      }
      std::vector<unsigned short>::_Tidy(pvData);
    }
  }
  std::wstring::_Tidy_deallocate(v34);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::string::_Tidy_deallocate(a2);
  std::string::_Tidy_deallocate(a3);
  return ValueW;
}

```

## disassembly

```asm
0x18001cd68  push    rbp
0x18001cd6a  push    rbx
0x18001cd6b  push    rsi
0x18001cd6c  push    rdi
0x18001cd6d  push    r14
0x18001cd6f  lea     rbp, [rsp-240h]
0x18001cd77  sub     rsp, 340h
0x18001cd7e  mov     rax, cs:__security_cookie
0x18001cd85  xor     rax, rsp
0x18001cd88  mov     [rbp+260h+var_30], rax
0x18001cd8f  mov     r14, r9
0x18001cd92  mov     rsi, r8
0x18001cd95  mov     rdi, rdx
0x18001cd98  mov     [rbp+260h+var_1D0], rdx
0x18001cd9f  mov     [rbp+260h+var_1C8], r8
0x18001cda6  mov     [rsp+360h+hkey], 0
0x18001cdaf  mov     rdx, rcx
0x18001cdb2  lea     rcx, [rbp+260h+var_1A0]
0x18001cdb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001cdbe  nop
0x18001cdbf  lea     rcx, asc_18004AA98; "\\"
0x18001cdc6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001cdcb  mov     r8, rax
0x18001cdce  mov     rdx, rcx
0x18001cdd1  lea     rcx, [rbp+260h+var_1A0]
0x18001cdd8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001cddd  lea     rcx, aDeviceunlock; "DeviceUnlock"
0x18001cde4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001cde9  mov     r8, rax
0x18001cdec  mov     rdx, rcx
0x18001cdef  lea     rcx, [rbp+260h+var_1A0]
0x18001cdf6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001cdfb  lea     rax, [rsp+360h+hkey]
0x18001ce00  mov     [rbp+260h+var_1C0], rax
0x18001ce07  mov     [rbp+260h+var_1B8], 0
0x18001ce12  mov     [rbp+260h+var_1B0], 1
0x18001ce19  lea     rcx, [rbp+260h+var_1A0]
0x18001ce20  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ce25  mov     rdx, rax; lpSubKey
0x18001ce28  lea     rax, [rbp+260h+var_1B8]
0x18001ce2f  mov     [rsp+360h+phkResult], rax; phkResult
0x18001ce34  mov     r9d, 20019h; samDesired
0x18001ce3a  xor     r8d, r8d; ulOptions
0x18001ce3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ce44  call    cs:__imp_RegOpenKeyExW
0x18001ce4a  mov     ebx, eax
0x18001ce4c  lea     rcx, [rbp+260h+var_1C0]
0x18001ce53  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001ce58  test    ebx, ebx
0x18001ce5a  jnz     loc_18001D130
0x18001ce60  mov     [rsp+360h+var_320], ebx
0x18001ce64  lea     rax, [rsp+360h+var_320]
0x18001ce69  mov     [rsp+360h+pcbData], rax; pcbData
0x18001ce6e  mov     [rsp+360h+pvData], 0; pvData
0x18001ce77  mov     [rsp+360h+phkResult], 0; pdwType
0x18001ce80  lea     r9d, [rbx+2]; dwFlags
0x18001ce84  lea     r8, Value; "Plugins"
0x18001ce8b  xor     edx, edx; lpSubKey
0x18001ce8d  mov     rcx, [rsp+360h+hkey]; hkey
0x18001ce92  call    cs:__imp_RegGetValueW
0x18001ce98  mov     ebx, eax
0x18001ce9a  test    eax, eax
0x18001ce9c  jnz     loc_18001D130
0x18001cea2  mov     edx, [rsp+360h+var_320]
0x18001cea6  shr     rdx, 1
0x18001cea9  inc     rdx
0x18001ceac  lea     rcx, [rsp+360h+var_310]
0x18001ceb1  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001ceb6  nop
0x18001ceb7  mov     rax, [rsp+360h+var_310]
0x18001cebc  lea     rcx, [rsp+360h+var_320]
0x18001cec1  mov     [rsp+360h+pcbData], rcx; pcbData
0x18001cec6  mov     [rsp+360h+pvData], rax; pvData
0x18001cecb  mov     [rsp+360h+phkResult], 0; pdwType
0x18001ced4  lea     r9d, [rbx+2]; dwFlags
0x18001ced8  lea     r8, Value; "Plugins"
0x18001cedf  xor     edx, edx; lpSubKey
0x18001cee1  mov     rcx, [rsp+360h+hkey]; hkey
0x18001cee6  call    cs:__imp_RegGetValueW
0x18001ceec  mov     ebx, eax
0x18001ceee  test    eax, eax
0x18001cef0  jnz     loc_18001D125
0x18001cef6  mov     rdx, [rsp+360h+var_310]
0x18001cefb  lea     rcx, [rbp+260h+var_F8]
0x18001cf02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001cf07  nop
0x18001cf08  lea     rcx, [rbp+260h+var_160]
0x18001cf0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cf14  nop
0x18001cf15  lea     rdx, [rbp+260h+var_F8]
0x18001cf1c  lea     rcx, [rbp+260h+var_2D0]
0x18001cf20  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring const &,int)
0x18001cf25  nop
0x18001cf26  lea     rcx, [rbp+260h+var_B0]
0x18001cf2d  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001cf32  nop
0x18001cf33  jmp     loc_18001D0CB
0x18001cf38  mov     r8, rdi
0x18001cf3b  lea     rdx, qword_18005F8E0
0x18001cf42  lea     rcx, [rbp+260h+var_140]
0x18001cf49  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@0@Z; std::operator+<char>(std::string const &,std::string const &)
0x18001cf4e  nop
0x18001cf4f  lea     r8, qword_18005F880
0x18001cf56  mov     rdx, rax
0x18001cf59  lea     rcx, [rbp+260h+var_180]
0x18001cf60  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x18001cf65  nop
0x18001cf66  lea     rcx, [rbp+260h+var_140]
0x18001cf6d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001cf72  mov     r8d, 1
0x18001cf78  lea     rdx, qword_18005F960
0x18001cf7f  lea     rcx, [rsp+360h+var_2F8]
0x18001cf84  call    ??$?0U?$char_traits@D@std@@V?$allocator@D@1@@?$basic_regex@DV?$regex_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(std::string const &,std::regex_constants::syntax_option_type)
0x18001cf89  mov     rbx, rax
0x18001cf8c  lea     r8, [rbp+260h+var_160]
0x18001cf93  lea     rdx, [rbp+260h+var_D8]
0x18001cf9a  lea     rcx, [rbp+260h+var_B0]
0x18001cfa1  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(std::wstring const &)
0x18001cfa6  nop
0x18001cfa7  lea     r9, [rbp+260h+var_180]
0x18001cfae  mov     r8, rbx
0x18001cfb1  mov     rdx, rax
0x18001cfb4  lea     rcx, [rbp+260h+var_1C0]
0x18001cfbb  call    ??$regex_replace@V?$regex_traits@D@std@@DU?$char_traits@D@2@V?$allocator@D@2@U32@V42@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@AEBV?$basic_regex@DV?$regex_traits@D@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(std::string const &,std::basic_regex<char,std::regex_traits<char>> const &,std::string const &,std::regex_constants::match_flag_type)
0x18001cfc0  nop
0x18001cfc1  lea     rcx, [rbp+260h+var_D8]
0x18001cfc8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001cfcd  nop
0x18001cfce  lea     rcx, [rsp+360h+var_2F8]
0x18001cfd3  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18001cfd8  mov     r8, rsi
0x18001cfdb  lea     rdx, qword_18005F8A0
0x18001cfe2  lea     rcx, [rbp+260h+var_118]
0x18001cfe9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@0@Z; std::operator+<char>(std::string const &,std::string const &)
0x18001cfee  nop
0x18001cfef  lea     r8, qword_18005F8C0
0x18001cff6  mov     rdx, rax
0x18001cff9  lea     rcx, [rbp+260h+var_140]
0x18001d000  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x18001d005  mov     rdx, rax
0x18001d008  lea     rcx, [rbp+260h+var_180]
0x18001d00f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001d014  lea     rcx, [rbp+260h+var_140]
0x18001d01b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d020  nop
0x18001d021  lea     rcx, [rbp+260h+var_118]
0x18001d028  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d02d  mov     r8d, 1
0x18001d033  lea     rdx, qword_18005F940
0x18001d03a  lea     rcx, [rbp+260h+var_140]
0x18001d041  call    ??$?0U?$char_traits@D@std@@V?$allocator@D@1@@?$basic_regex@DV?$regex_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(std::string const &,std::regex_constants::syntax_option_type)
0x18001d046  nop
0x18001d047  lea     r9, [rbp+260h+var_180]
0x18001d04e  mov     r8, rax
0x18001d051  lea     rdx, [rbp+260h+var_1C0]
0x18001d058  lea     rcx, [rbp+260h+var_118]
0x18001d05f  call    ??$regex_replace@V?$regex_traits@D@std@@DU?$char_traits@D@2@V?$allocator@D@2@U32@V42@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@AEBV?$basic_regex@DV?$regex_traits@D@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(std::string const &,std::basic_regex<char,std::regex_traits<char>> const &,std::string const &,std::regex_constants::match_flag_type)
0x18001d064  mov     rdx, rax
0x18001d067  lea     rcx, [rbp+260h+var_1C0]
0x18001d06e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001d073  lea     rcx, [rbp+260h+var_118]
0x18001d07a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d07f  nop
0x18001d080  lea     rcx, [rbp+260h+var_140]
0x18001d087  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18001d08c  mov     rdx, [r14+8]
0x18001d090  lea     r8, [rbp+260h+var_1C0]
0x18001d097  cmp     rdx, [r14+10h]
0x18001d09b  jz      short loc_18001D0A9
0x18001d09d  call    ??$construct@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@1@QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::string,void *>>>::construct<std::string,std::string const &>(std::allocator<std::_Tree_node<std::string,void *>> &,std::string * const,std::string const &)
0x18001d0a2  add     qword ptr [r14+8], 20h ; ' '
0x18001d0a7  jmp     short loc_18001D0B2
0x18001d0a9  mov     rcx, r14
0x18001d0ac  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x18001d0b1  nop
0x18001d0b2  lea     rcx, [rbp+260h+var_1C0]
0x18001d0b9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d0be  nop
0x18001d0bf  lea     rcx, [rbp+260h+var_180]
0x18001d0c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d0cb  lea     rdx, [rbp+260h+var_160]
0x18001d0d2  lea     rcx, [rbp+260h+var_2D0]
0x18001d0d6  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x18001d0db  mov     rcx, [rax]
0x18001d0de  movsxd  rcx, dword ptr [rcx+4]
0x18001d0e2  add     rcx, rax
0x18001d0e5  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x18001d0eb  test    al, al
0x18001d0ed  jnz     loc_18001CF38
0x18001d0f3  lea     rcx, [rbp+260h+var_B0]
0x18001d0fa  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001d0ff  nop
0x18001d100  lea     rcx, [rbp+260h+var_2D0]
0x18001d104  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18001d109  nop
0x18001d10a  lea     rcx, [rbp+260h+var_160]
0x18001d111  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d116  nop
0x18001d117  lea     rcx, [rbp+260h+var_F8]
0x18001d11e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d123  xor     ebx, ebx
0x18001d125  lea     rcx, [rsp+360h+var_310]
0x18001d12a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001d12f  nop
0x18001d130  lea     rcx, [rbp+260h+var_1A0]
0x18001d137  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d13c  nop
0x18001d13d  lea     rcx, [rsp+360h+hkey]
0x18001d142  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001d147  nop
0x18001d148  mov     rcx, rdi
0x18001d14b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d150  nop
0x18001d151  mov     rcx, rsi
0x18001d154  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d159  mov     eax, ebx
0x18001d15b  mov     rcx, [rbp+260h+var_30]
0x18001d162  xor     rcx, rsp; StackCookie
0x18001d165  call    __security_check_cookie
0x18001d16a  add     rsp, 340h
0x18001d171  pop     r14
0x18001d173  pop     rdi
0x18001d174  pop     rsi
0x18001d175  pop     rbx
0x18001d176  pop     rbp
0x18001d177  retn
```
