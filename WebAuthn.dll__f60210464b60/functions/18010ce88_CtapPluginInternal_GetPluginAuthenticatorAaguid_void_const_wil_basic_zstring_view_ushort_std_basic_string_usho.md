# CtapPluginInternal::GetPluginAuthenticatorAaguid(void * const,wil::basic_zstring_view<ushort>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18010ce88`
- end: `0x18010d0b1`
- name: `?GetPluginAuthenticatorAaguid@CtapPluginInternal@@YAJQEAXV?$basic_zstring_view@G@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `553`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033970`
- `0x1800a1d08`
- `0x1800a5de4`
- `0x1800a645c`

## callees

- `0x1800328b8`
- `0x180036da4`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x18007e064`
- `0x18010bfa8`
- `0x18010ce88`
- `0x18011c42c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010cf8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d011`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010cf8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010d011`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010cf09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010cf09`

## string_xrefs

- `0x18010cebd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cf1b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cf9c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d023`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CtapPluginInternal::GetPluginAuthenticatorAaguid(__int64 a1, LPCWSTR *a2, __int64 a3)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  HKEY *v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int ValueW; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  int phkResult; // [rsp+20h] [rbp-58h]
  unsigned int phkResulta; // [rsp+20h] [rbp-58h]
  unsigned int phkResultb; // [rsp+20h] [rbp-58h]
  unsigned int phkResultc; // [rsp+20h] [rbp-58h]
  HKEY hkey; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD pcbData; // [rsp+98h] [rbp+20h] BYREF

  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&hKey);
  v6 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey >= 0 )
  {
    hkey = 0;
    v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    v9 = RegOpenKeyExW(hKey, *a2, 0, 0xF003Fu, v8);
    if ( v9 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE88,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v9,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v10;
    }
    else
    {
      pcbData = 0;
      ValueW = RegGetValueW(hkey, 0, L"AaGuid", 2u, 0, 0, &pcbData);
      if ( ValueW )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xE8B,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)ValueW,
                phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v12;
      }
      else
      {
        try
        {
          std::vector<unsigned short>::vector<unsigned short>(&pvData, (unsigned __int64)pcbData >> 1);
          v13 = RegGetValueW(hkey, 0, L"AaGuid", 2u, 0, pvData, &pcbData);
          if ( v13 )
          {
            v14 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xE8E,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)v13,
                    phkResultc);
            std::vector<unsigned short>::_Tidy(&pvData);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            result = v14;
          }
          else
          {
            std::wstring::_Assign<unsigned short>(a3, pvData);
            std::vector<unsigned short>::_Tidy(&pvData);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            result = 0;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0xE93,
                                 (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                 v15);
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE85,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18010ce88  mov     rax, rsp
0x18010ce8b  mov     [rax+8], rbx
0x18010ce8f  mov     [rax+10h], rsi
0x18010ce93  push    rdi
0x18010ce94  sub     rsp, 70h
0x18010ce98  mov     rdi, r8
0x18010ce9b  mov     rsi, rdx
0x18010ce9e  mov     qword ptr [rax-30h], 0
0x18010cea6  lea     rdx, [rax-30h]
0x18010ceaa  call    GetUserPluginAuthenticatorsRegKey
0x18010ceaf  mov     ebx, eax
0x18010ceb1  test    eax, eax
0x18010ceb3  jns     short loc_18010CEE0
0x18010ceb5  mov     rcx, [rsp+78h]; this
0x18010ceba  mov     r9d, eax; char *
0x18010cebd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cec4  mov     edx, 0E85h; void *
0x18010cec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cece  nop
0x18010cecf  lea     rcx, [rsp+78h+hKey]
0x18010ced4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010ced9  mov     eax, ebx
0x18010cedb  jmp     loc_18010D09E
0x18010cee0  mov     [rsp+78h+hkey], 0
0x18010cee9  lea     rcx, [rsp+78h+hkey]
0x18010ceee  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010cef3  mov     [rsp+78h+phkResult], rax; unsigned int
0x18010cef8  mov     r9d, 0F003Fh; samDesired
0x18010cefe  xor     r8d, r8d; ulOptions
0x18010cf01  mov     rdx, [rsi]; lpSubKey
0x18010cf04  mov     rcx, [rsp+78h+hKey]; hKey
0x18010cf09  call    cs:__imp_RegOpenKeyExW
0x18010cf0f  test    eax, eax
0x18010cf11  jz      short loc_18010CF4A
0x18010cf13  mov     rcx, [rsp+78h]; this
0x18010cf18  mov     r9d, eax; char *
0x18010cf1b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cf22  mov     edx, 0E88h; void *
0x18010cf27  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010cf2c  mov     ebx, eax
0x18010cf2e  lea     rcx, [rsp+78h+hkey]
0x18010cf33  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010cf38  nop
0x18010cf39  lea     rcx, [rsp+78h+hKey]
0x18010cf3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010cf43  mov     eax, ebx
0x18010cf45  jmp     loc_18010D09E
0x18010cf4a  mov     [rsp+78h+arg_18], 0
0x18010cf55  lea     rax, [rsp+78h+arg_18]
0x18010cf5d  mov     [rsp+78h+pcbData], rax; pcbData
0x18010cf62  mov     [rsp+78h+pvData], 0; pvData
0x18010cf6b  mov     [rsp+78h+phkResult], 0; unsigned int
0x18010cf74  mov     ebx, 2
0x18010cf79  mov     r9d, ebx; dwFlags
0x18010cf7c  lea     r8, aAaguid; "AaGuid"
0x18010cf83  xor     edx, edx; lpSubKey
0x18010cf85  mov     rcx, [rsp+78h+hkey]; hkey
0x18010cf8a  call    cs:__imp_RegGetValueW
0x18010cf90  test    eax, eax
0x18010cf92  jz      short loc_18010CFCB
0x18010cf94  mov     rcx, [rsp+78h]; this
0x18010cf99  mov     r9d, eax; char *
0x18010cf9c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cfa3  mov     edx, 0E8Bh; void *
0x18010cfa8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010cfad  mov     ebx, eax
0x18010cfaf  lea     rcx, [rsp+78h+hkey]
0x18010cfb4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010cfb9  nop
0x18010cfba  lea     rcx, [rsp+78h+hKey]
0x18010cfbf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010cfc4  mov     eax, ebx
0x18010cfc6  jmp     loc_18010D09E
0x18010cfcb  mov     edx, [rsp+78h+arg_18]
0x18010cfd2  shr     rdx, 1
0x18010cfd5  lea     rcx, [rsp+78h+var_28]
0x18010cfda  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18010cfdf  nop
0x18010cfe0  mov     rax, [rsp+78h+var_28]
0x18010cfe5  lea     rcx, [rsp+78h+arg_18]
0x18010cfed  mov     [rsp+78h+pcbData], rcx; pcbData
0x18010cff2  mov     [rsp+78h+pvData], rax; pvData
0x18010cff7  mov     [rsp+78h+phkResult], 0; unsigned int
0x18010d000  mov     r9d, ebx; dwFlags
0x18010d003  lea     r8, aAaguid; "AaGuid"
0x18010d00a  xor     edx, edx; lpSubKey
0x18010d00c  mov     rcx, [rsp+78h+hkey]; hkey
0x18010d011  call    cs:__imp_RegGetValueW
0x18010d017  test    eax, eax
0x18010d019  jz      short loc_18010D05A
0x18010d01b  mov     rcx, [rsp+78h]; this
0x18010d020  mov     r9d, eax; char *
0x18010d023  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d02a  mov     edx, 0E8Eh; void *
0x18010d02f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010d034  mov     ebx, eax
0x18010d036  lea     rcx, [rsp+78h+var_28]
0x18010d03b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18010d040  nop
0x18010d041  lea     rcx, [rsp+78h+hkey]
0x18010d046  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d04b  nop
0x18010d04c  lea     rcx, [rsp+78h+hKey]
0x18010d051  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d056  mov     eax, ebx
0x18010d058  jmp     short loc_18010D09E
0x18010d05a  mov     rdx, [rsp+78h+var_28]
0x18010d05f  mov     r8, [rsp+78h+var_20]
0x18010d064  sub     r8, rdx
0x18010d067  sar     r8, 1
0x18010d06a  mov     rcx, rdi
0x18010d06d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18010d072  nop
0x18010d073  lea     rcx, [rsp+78h+var_28]
0x18010d078  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18010d07d  nop
0x18010d07e  lea     rcx, [rsp+78h+hkey]
0x18010d083  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d088  nop
0x18010d089  lea     rcx, [rsp+78h+hKey]
0x18010d08e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d093  xor     eax, eax
0x18010d095  jmp     short loc_18010D09E
0x18010d097  mov     eax, [rsp+78h+arg_18]
0x18010d09e  lea     r11, [rsp+78h+var_8]
0x18010d0a3  mov     rbx, [r11+10h]
0x18010d0a7  mov     rsi, [r11+18h]
0x18010d0ab  mov     rsp, r11
0x18010d0ae  pop     rdi
0x18010d0af  retn
```
