# NaturalAuthHelper::_anonymous_namespace_::GetSpecificDynamicLockPluginsPolicy

- ea: `0x180014918`
- end: `0x180014e74`
- name: `NaturalAuthHelper::_anonymous_namespace_::GetSpecificDynamicLockPluginsPolicy`
- size: `1372`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800146f4`

## callees

- `0x180004170`
- `0x18000aa80`
- `0x18000cab8`
- `0x18000d564`
- `0x18000d8c0`
- `0x18000d900`
- `0x18000d96c`
- `0x18000daac`
- `0x18000eca4`
- `0x18000f46c`
- `0x180010ba0`
- `0x180010dcc`
- `0x1800110ac`
- `0x180011a40`
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
- `0x180014918`
- `0x180019bbc`
- `0x18001a9a0`
- `0x18001aa2c`
- `0x18001b734`
- `0x18001c070`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x180014dd8`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x180014dd8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014a4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014aa2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014a4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014aa2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014a00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014a00`

## string_xrefs

- `0x180014a40`: `Plugins`
- `0x180014a94`: `Plugins`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NaturalAuthHelper::_anonymous_namespace_::GetSpecificDynamicLockPluginsPolicy(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  unsigned int ValueW; // ebx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v36[256]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+190h] [rbp+90h]
  __int64 v38; // [rsp+198h] [rbp+98h]
  HKEY *p_hkey; // [rsp+1A0h] [rbp+A0h] BYREF
  HKEY phkResult; // [rsp+1A8h] [rbp+A8h] BYREF
  char v41; // [rsp+1B0h] [rbp+B0h]
  _BYTE v42[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v43[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v44[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v45[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v46[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v47[40]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v48[40]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v49[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v50[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v51[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v52[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v53[128]; // [rsp+330h] [rbp+230h] BYREF

  v37 = a2;
  v38 = a4;
  hkey = 0;
  std::wstring::wstring(v44, a1);
  v8 = std::_WChar_traits<unsigned short>::length(L"\\");
  std::wstring::_Append<unsigned short>(v44, v9, v8);
  v10 = std::_WChar_traits<unsigned short>::length(L"DynamicLock");
  std::wstring::_Append<unsigned short>(v44, v11, v10);
  p_hkey = &hkey;
  phkResult = 0;
  v41 = 1;
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &phkResult);
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
        std::wstring::wstring(v49, pvData[0]);
        std::wstring::wstring(v45);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
          v36,
          v49);
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v53);
        while ( 1 )
        {
          v30 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v36, v45);
          if ( !(unsigned __int8)std::ios_base::operator bool(v30 + *(int *)(*(_QWORD *)v30 + 4LL)) )
            break;
          v14 = std::operator+<char>(v42, qword_18005F7C0, a2);
          std::operator+<char>(v43, v14, qword_18005F760);
          std::string::_Tidy_deallocate(v42);
          v15 = std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(
                  v35,
                  qword_18005F840,
                  1);
          v16 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
                  v53,
                  v50,
                  v45);
          std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(
            &p_hkey,
            v16,
            v15,
            v43);
          std::string::_Tidy_deallocate(v50);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v35);
          v17 = std::operator+<char>(v46, qword_18005F780, a4);
          v18 = std::operator+<char>(v42, v17, qword_18005F7A0);
          std::string::operator=(v43, v18);
          std::string::_Tidy_deallocate(v42);
          std::string::_Tidy_deallocate(v46);
          v19 = std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(
                  v47,
                  qword_18005F820,
                  1);
          v20 = std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(
                  v42,
                  &p_hkey,
                  v19,
                  v43);
          std::string::operator=(&p_hkey, v20);
          std::string::_Tidy_deallocate(v42);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v47);
          std::_Integral_to_string<char,unsigned long>(v42, a3);
          v21 = std::operator+<char>(v47);
          v22 = std::operator+<char>(v48, v21, qword_18005F800);
          v23 = std::operator+<char>(v52, v22, "\"");
          std::string::string(v46, v24, v23, v42);
          v25 = std::operator+<char>(v51, v46, "\"");
          std::string::operator=(v43, v25);
          std::string::_Tidy_deallocate(v51);
          std::string::_Tidy_deallocate(v46);
          std::string::_Tidy_deallocate(v52);
          std::string::_Tidy_deallocate(v48);
          std::string::_Tidy_deallocate(v47);
          std::string::_Tidy_deallocate(v42);
          v26 = std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(
                  v48,
                  qword_18005F7E0,
                  1);
          v27 = std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(
                  v47,
                  &p_hkey,
                  v26,
                  v43);
          std::string::operator=(&p_hkey, v27);
          std::string::_Tidy_deallocate(v47);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v48);
          v29 = *(_QWORD *)(a5 + 8);
          if ( v29 == *(_QWORD *)(a5 + 16) )
          {
            std::vector<std::string>::_Emplace_reallocate<std::string const &>(a5, v29, &p_hkey);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::string,void *>>>::construct<std::string,std::string const &>(
              v28,
              v29,
              &p_hkey);
            *(_QWORD *)(a5 + 8) += 32LL;
          }
          std::string::_Tidy_deallocate(&p_hkey);
          std::string::_Tidy_deallocate(v43);
        }
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v53);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v36);
        std::wstring::_Tidy_deallocate(v45);
        std::wstring::_Tidy_deallocate(v49);
        ValueW = 0;
      }
      std::vector<unsigned short>::_Tidy(pvData);
    }
  }
  std::wstring::_Tidy_deallocate(v44);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::string::_Tidy_deallocate(a2);
  std::string::_Tidy_deallocate(a4);
  return ValueW;
}

```

## disassembly

```asm
0x180014918  mov     [rsp-8+arg_10], rbx
0x18001491d  push    rbp
0x18001491e  push    rsi
0x18001491f  push    rdi
0x180014920  push    r14
0x180014922  push    r15
0x180014924  lea     rbp, [rsp-2C0h]
0x18001492c  sub     rsp, 3C0h
0x180014933  mov     rax, cs:__security_cookie
0x18001493a  xor     rax, rsp
0x18001493d  mov     [rbp+2E0h+var_30], rax
0x180014944  mov     rsi, r9
0x180014947  mov     r15d, r8d
0x18001494a  mov     rdi, rdx
0x18001494d  mov     [rbp+2E0h+var_250], rdx
0x180014954  mov     [rbp+2E0h+var_248], r9
0x18001495b  mov     r14, [rbp+2E0h+arg_20]
0x180014962  mov     [rsp+3E0h+hkey], 0
0x18001496b  mov     rdx, rcx
0x18001496e  lea     rcx, [rbp+2E0h+var_1E0]
0x180014975  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001497a  nop
0x18001497b  lea     rcx, asc_18004AA98; "\\"
0x180014982  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180014987  mov     r8, rax
0x18001498a  mov     rdx, rcx
0x18001498d  lea     rcx, [rbp+2E0h+var_1E0]
0x180014994  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180014999  lea     rcx, aDynamiclock; "DynamicLock"
0x1800149a0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800149a5  mov     r8, rax
0x1800149a8  mov     rdx, rcx
0x1800149ab  lea     rcx, [rbp+2E0h+var_1E0]
0x1800149b2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800149b7  lea     rax, [rsp+3E0h+hkey]
0x1800149bc  mov     [rbp+2E0h+var_240], rax
0x1800149c3  mov     [rbp+2E0h+var_238], 0
0x1800149ce  mov     [rbp+2E0h+var_230], 1
0x1800149d5  lea     rcx, [rbp+2E0h+var_1E0]
0x1800149dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800149e1  mov     rdx, rax; lpSubKey
0x1800149e4  lea     rax, [rbp+2E0h+var_238]
0x1800149eb  mov     [rsp+3E0h+phkResult], rax; phkResult
0x1800149f0  mov     r9d, 20019h; samDesired
0x1800149f6  xor     r8d, r8d; ulOptions
0x1800149f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014a00  call    cs:__imp_RegOpenKeyExW
0x180014a06  mov     ebx, eax
0x180014a08  lea     rcx, [rbp+2E0h+var_240]
0x180014a0f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180014a14  test    ebx, ebx
0x180014a16  jnz     loc_180014E23
0x180014a1c  mov     [rsp+3E0h+var_3A0], ebx
0x180014a20  lea     rax, [rsp+3E0h+var_3A0]
0x180014a25  mov     [rsp+3E0h+pcbData], rax; pcbData
0x180014a2a  mov     [rsp+3E0h+pvData], 0; pvData
0x180014a33  mov     [rsp+3E0h+phkResult], 0; pdwType
0x180014a3c  lea     r9d, [rbx+2]; dwFlags
0x180014a40  lea     r8, Value; "Plugins"
0x180014a47  xor     edx, edx; lpSubKey
0x180014a49  mov     rcx, [rsp+3E0h+hkey]; hkey
0x180014a4e  call    cs:__imp_RegGetValueW
0x180014a54  mov     ebx, eax
0x180014a56  test    eax, eax
0x180014a58  jnz     loc_180014E23
0x180014a5e  mov     edx, [rsp+3E0h+var_3A0]
0x180014a62  shr     rdx, 1
0x180014a65  inc     rdx
0x180014a68  lea     rcx, [rsp+3E0h+var_390]
0x180014a6d  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180014a72  nop
0x180014a73  mov     rax, [rsp+3E0h+var_390]
0x180014a78  lea     rcx, [rsp+3E0h+var_3A0]
0x180014a7d  mov     [rsp+3E0h+pcbData], rcx; pcbData
0x180014a82  mov     [rsp+3E0h+pvData], rax; pvData
0x180014a87  mov     [rsp+3E0h+phkResult], 0; pdwType
0x180014a90  lea     r9d, [rbx+2]; dwFlags
0x180014a94  lea     r8, Value; "Plugins"
0x180014a9b  xor     edx, edx; lpSubKey
0x180014a9d  mov     rcx, [rsp+3E0h+hkey]; hkey
0x180014aa2  call    cs:__imp_RegGetValueW
0x180014aa8  mov     ebx, eax
0x180014aaa  test    eax, eax
0x180014aac  jnz     loc_180014E18
0x180014ab2  mov     rdx, [rsp+3E0h+var_390]
0x180014ab7  lea     rcx, [rbp+2E0h+var_130]
0x180014abe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014ac3  nop
0x180014ac4  lea     rcx, [rbp+2E0h+var_1C0]
0x180014acb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014ad0  nop
0x180014ad1  lea     rdx, [rbp+2E0h+var_130]
0x180014ad8  lea     rcx, [rbp+2E0h+var_350]
0x180014adc  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring const &,int)
0x180014ae1  nop
0x180014ae2  lea     rcx, [rbp+2E0h+var_B0]
0x180014ae9  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180014aee  nop
0x180014aef  jmp     loc_180014DBE
0x180014af4  mov     r8, rdi
0x180014af7  lea     rdx, qword_18005F7C0
0x180014afe  lea     rcx, [rbp+2E0h+var_220]
0x180014b05  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@0@Z; std::operator+<char>(std::string const &,std::string const &)
0x180014b0a  nop
0x180014b0b  lea     r8, qword_18005F760
0x180014b12  mov     rdx, rax
0x180014b15  lea     rcx, [rbp+2E0h+var_200]
0x180014b1c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180014b21  nop
0x180014b22  lea     rcx, [rbp+2E0h+var_220]
0x180014b29  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014b2e  mov     r8d, 1
0x180014b34  lea     rdx, qword_18005F840
0x180014b3b  lea     rcx, [rsp+3E0h+var_378]
0x180014b40  call    ??$?0U?$char_traits@D@std@@V?$allocator@D@1@@?$basic_regex@DV?$regex_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(std::string const &,std::regex_constants::syntax_option_type)
0x180014b45  mov     rbx, rax
0x180014b48  lea     r8, [rbp+2E0h+var_1C0]
0x180014b4f  lea     rdx, [rbp+2E0h+var_110]
0x180014b56  lea     rcx, [rbp+2E0h+var_B0]
0x180014b5d  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(std::wstring const &)
0x180014b62  nop
0x180014b63  lea     r9, [rbp+2E0h+var_200]
0x180014b6a  mov     r8, rbx
0x180014b6d  mov     rdx, rax
0x180014b70  lea     rcx, [rbp+2E0h+var_240]
0x180014b77  call    ??$regex_replace@V?$regex_traits@D@std@@DU?$char_traits@D@2@V?$allocator@D@2@U32@V42@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@AEBV?$basic_regex@DV?$regex_traits@D@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(std::string const &,std::basic_regex<char,std::regex_traits<char>> const &,std::string const &,std::regex_constants::match_flag_type)
0x180014b7c  nop
0x180014b7d  lea     rcx, [rbp+2E0h+var_110]
0x180014b84  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014b89  nop
0x180014b8a  lea     rcx, [rsp+3E0h+var_378]
0x180014b8f  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180014b94  mov     r8, rsi
0x180014b97  lea     rdx, qword_18005F780
0x180014b9e  lea     rcx, [rbp+2E0h+var_1A0]
0x180014ba5  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@0@Z; std::operator+<char>(std::string const &,std::string const &)
0x180014baa  nop
0x180014bab  lea     r8, qword_18005F7A0
0x180014bb2  mov     rdx, rax
0x180014bb5  lea     rcx, [rbp+2E0h+var_220]
0x180014bbc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180014bc1  mov     rdx, rax
0x180014bc4  lea     rcx, [rbp+2E0h+var_200]
0x180014bcb  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180014bd0  lea     rcx, [rbp+2E0h+var_220]
0x180014bd7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014bdc  nop
0x180014bdd  lea     rcx, [rbp+2E0h+var_1A0]
0x180014be4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014be9  mov     r8d, 1
0x180014bef  lea     rdx, qword_18005F820
0x180014bf6  lea     rcx, [rbp+2E0h+var_180]
0x180014bfd  call    ??$?0U?$char_traits@D@std@@V?$allocator@D@1@@?$basic_regex@DV?$regex_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(std::string const &,std::regex_constants::syntax_option_type)
0x180014c02  nop
0x180014c03  lea     r9, [rbp+2E0h+var_200]
0x180014c0a  mov     r8, rax
0x180014c0d  lea     rdx, [rbp+2E0h+var_240]
0x180014c14  lea     rcx, [rbp+2E0h+var_220]
0x180014c1b  call    ??$regex_replace@V?$regex_traits@D@std@@DU?$char_traits@D@2@V?$allocator@D@2@U32@V42@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@AEBV?$basic_regex@DV?$regex_traits@D@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(std::string const &,std::basic_regex<char,std::regex_traits<char>> const &,std::string const &,std::regex_constants::match_flag_type)
0x180014c20  mov     rdx, rax
0x180014c23  lea     rcx, [rbp+2E0h+var_240]
0x180014c2a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180014c2f  lea     rcx, [rbp+2E0h+var_220]
0x180014c36  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014c3b  nop
0x180014c3c  lea     rcx, [rbp+2E0h+var_180]
0x180014c43  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180014c48  mov     edx, r15d
0x180014c4b  lea     rcx, [rbp+2E0h+var_220]
0x180014c52  call    ??$_Integral_to_string@DK@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@K@Z; std::_Integral_to_string<char,ulong>(ulong)
0x180014c57  nop
0x180014c58  lea     rcx, [rbp+2E0h+var_180]
0x180014c5f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180014c64  nop
0x180014c65  lea     r8, qword_18005F800
0x180014c6c  mov     rdx, rax
0x180014c6f  lea     rcx, [rbp+2E0h+var_158]
0x180014c76  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180014c7b  nop
0x180014c7c  lea     r8, asc_18004B49C; "\""
0x180014c83  mov     rdx, rax
0x180014c86  lea     rcx, [rbp+2E0h+var_D0]
0x180014c8d  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180014c92  nop
0x180014c93  lea     r9, [rbp+2E0h+var_220]
0x180014c9a  mov     r8, rax
0x180014c9d  lea     rcx, [rbp+2E0h+var_1A0]
0x180014ca4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180014ca9  nop
0x180014caa  lea     r8, asc_18004B49C; "\""
0x180014cb1  lea     rdx, [rbp+2E0h+var_1A0]
0x180014cb8  lea     rcx, [rbp+2E0h+var_F0]
0x180014cbf  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180014cc4  mov     rdx, rax
0x180014cc7  lea     rcx, [rbp+2E0h+var_200]
0x180014cce  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180014cd3  lea     rcx, [rbp+2E0h+var_F0]
0x180014cda  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014cdf  nop
0x180014ce0  lea     rcx, [rbp+2E0h+var_1A0]
0x180014ce7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014cec  nop
0x180014ced  lea     rcx, [rbp+2E0h+var_D0]
0x180014cf4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014cf9  nop
0x180014cfa  lea     rcx, [rbp+2E0h+var_158]
0x180014d01  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014d06  nop
0x180014d07  lea     rcx, [rbp+2E0h+var_180]
0x180014d0e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014d13  nop
0x180014d14  lea     rcx, [rbp+2E0h+var_220]
0x180014d1b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014d20  mov     r8d, 1
0x180014d26  lea     rdx, qword_18005F7E0
0x180014d2d  lea     rcx, [rbp+2E0h+var_158]
0x180014d34  call    ??$?0U?$char_traits@D@std@@V?$allocator@D@1@@?$basic_regex@DV?$regex_traits@D@std@@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<char,std::regex_traits<char>>::basic_regex<char,std::regex_traits<char>>(std::string const &,std::regex_constants::syntax_option_type)
0x180014d39  nop
0x180014d3a  lea     r9, [rbp+2E0h+var_200]
0x180014d41  mov     r8, rax
0x180014d44  lea     rdx, [rbp+2E0h+var_240]
0x180014d4b  lea     rcx, [rbp+2E0h+var_180]
0x180014d52  call    ??$regex_replace@V?$regex_traits@D@std@@DU?$char_traits@D@2@V?$allocator@D@2@U32@V42@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@AEBV?$basic_regex@DV?$regex_traits@D@std@@@0@0W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<char>,char,std::char_traits<char>,std::allocator<char>,std::char_traits<char>,std::allocator<char>>(std::string const &,std::basic_regex<char,std::regex_traits<char>> const &,std::string const &,std::regex_constants::match_flag_type)
0x180014d57  mov     rdx, rax
0x180014d5a  lea     rcx, [rbp+2E0h+var_240]
0x180014d61  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180014d66  lea     rcx, [rbp+2E0h+var_180]
0x180014d6d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014d72  nop
0x180014d73  lea     rcx, [rbp+2E0h+var_158]
0x180014d7a  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180014d7f  mov     rdx, [r14+8]
0x180014d83  lea     r8, [rbp+2E0h+var_240]
0x180014d8a  cmp     rdx, [r14+10h]
0x180014d8e  jz      short loc_180014D9C
0x180014d90  call    ??$construct@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@1@QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::string,void *>>>::construct<std::string,std::string const &>(std::allocator<std::_Tree_node<std::string,void *>> &,std::string * const,std::string const &)
0x180014d95  add     qword ptr [r14+8], 20h ; ' '
0x180014d9a  jmp     short loc_180014DA5
0x180014d9c  mov     rcx, r14
0x180014d9f  call    ??$_Emplace_reallocate@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@AEBV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string const &>(std::string * const,std::string const &)
0x180014da4  nop
0x180014da5  lea     rcx, [rbp+2E0h+var_240]
0x180014dac  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014db1  nop
0x180014db2  lea     rcx, [rbp+2E0h+var_200]
0x180014db9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014dbe  lea     rdx, [rbp+2E0h+var_1C0]
0x180014dc5  lea     rcx, [rbp+2E0h+var_350]
0x180014dc9  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x180014dce  mov     rcx, [rax]
0x180014dd1  movsxd  rcx, dword ptr [rcx+4]
0x180014dd5  add     rcx, rax
0x180014dd8  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x180014dde  test    al, al
0x180014de0  jnz     loc_180014AF4
0x180014de6  lea     rcx, [rbp+2E0h+var_B0]
0x180014ded  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180014df2  nop
0x180014df3  lea     rcx, [rbp+2E0h+var_350]
0x180014df7  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x180014dfc  nop
0x180014dfd  lea     rcx, [rbp+2E0h+var_1C0]
0x180014e04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014e09  nop
0x180014e0a  lea     rcx, [rbp+2E0h+var_130]
0x180014e11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014e16  xor     ebx, ebx
0x180014e18  lea     rcx, [rsp+3E0h+var_390]
0x180014e1d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180014e22  nop
0x180014e23  lea     rcx, [rbp+2E0h+var_1E0]
0x180014e2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014e2f  nop
0x180014e30  lea     rcx, [rsp+3E0h+hkey]
0x180014e35  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014e3a  nop
0x180014e3b  mov     rcx, rdi
0x180014e3e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014e43  nop
0x180014e44  mov     rcx, rsi
0x180014e47  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014e4c  mov     eax, ebx
0x180014e4e  mov     rcx, [rbp+2E0h+var_30]
0x180014e55  xor     rcx, rsp; StackCookie
0x180014e58  call    __security_check_cookie
0x180014e5d  mov     rbx, [rsp+3E0h+arg_10]
0x180014e65  add     rsp, 3C0h
0x180014e6c  pop     r15
0x180014e6e  pop     r14
0x180014e70  pop     rdi
0x180014e71  pop     rsi
0x180014e72  pop     rbp
0x180014e73  retn
```
