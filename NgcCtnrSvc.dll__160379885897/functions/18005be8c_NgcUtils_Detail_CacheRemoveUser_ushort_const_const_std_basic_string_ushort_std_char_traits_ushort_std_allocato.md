# NgcUtils::Detail::CacheRemoveUser(ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005be8c`
- end: `0x18005c021`
- name: `?CacheRemoveUser@Detail@NgcUtils@@YAJQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026e6c`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x180012300`
- `0x180018a9c`
- `0x1800199d8`
- `0x18001a77c`
- `0x180023278`
- `0x1800232a0`
- `0x1800264b8`
- `0x18002b0dc`
- `0x18002c640`
- `0x18005be8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bfcd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bfcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bf7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bf7d`

## string_xrefs

- `0x18005bee9`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005bf92`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::Detail::CacheRemoveUser(__int64 a1, const WCHAR *a2)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  HKEY *v6; // rax
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-50h]
  int phkResulta; // [rsp+20h] [rbp-50h]
  unsigned int phkResultb; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 v15[4]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *(_QWORD *)v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v15,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        v15,
                                        phkResult);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    std::wstring::wstring(lpSubKey, *(_QWORD *)v15);
    std::wstring::append(lpSubKey, L"\\");
    std::wstring::append(lpSubKey, a1);
    std::wstring::append(lpSubKey, L"\\");
    std::wstring::append(lpSubKey, L"UserNames");
    hKey = 0;
    v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v7 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v7 = lpSubKey[0];
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x2001Fu, v6);
    if ( v8 )
    {
      v9 = 1329;
    }
    else
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const WCHAR **)a2;
      v8 = RegDeleteTreeW(hKey, a2);
      if ( !v8 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        v5 = 0;
        goto LABEL_13;
      }
      v9 = 1334;
    }
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
           (const char *)v8,
           phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x522,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
  }
LABEL_13:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v15);
  return v5;
}

```

## disassembly

```asm
0x18005be8c  mov     [rsp-18h+arg_10], rbx
0x18005be91  push    rbp
0x18005be92  push    rsi
0x18005be93  push    rdi
0x18005be94  mov     rbp, rsp
0x18005be97  sub     rsp, 70h
0x18005be9b  mov     rax, cs:__security_cookie
0x18005bea2  xor     rax, rsp
0x18005bea5  mov     [rbp+var_10], rax
0x18005bea9  mov     rdi, rdx
0x18005beac  mov     rsi, rcx
0x18005beaf  mov     qword ptr [rbp+var_38], 0
0x18005beb7  xor     edx, edx
0x18005beb9  lea     rcx, [rbp+var_38]
0x18005bebd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005bec2  lea     r9, [rbp+var_38]; unsigned __int16 *
0x18005bec6  xor     r8d, r8d; unsigned __int16 *
0x18005bec9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005bed0  lea     rcx, aNgccredprov; "NgcCredprov"
0x18005bed7  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18005bedc  mov     ebx, eax
0x18005bede  test    eax, eax
0x18005bee0  jns     short loc_18005BEFF
0x18005bee2  mov     rcx, [rbp+18h]; this
0x18005bee6  mov     r9d, eax; char *
0x18005bee9  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005bef0  mov     edx, 522h; void *
0x18005bef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005befa  jmp     loc_18005BFF9
0x18005beff  mov     rdx, qword ptr [rbp+var_38]
0x18005bf03  lea     rcx, [rbp+lpSubKey]
0x18005bf07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bf0c  nop
0x18005bf0d  lea     rdx, asc_18008F0A4; "\\"
0x18005bf14  lea     rcx, [rbp+lpSubKey]
0x18005bf18  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005bf1d  mov     rdx, rsi
0x18005bf20  lea     rcx, [rbp+lpSubKey]
0x18005bf24  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005bf29  lea     rdx, asc_18008F0A4; "\\"
0x18005bf30  lea     rcx, [rbp+lpSubKey]
0x18005bf34  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005bf39  lea     rdx, aUsernames; "UserNames"
0x18005bf40  lea     rcx, [rbp+lpSubKey]
0x18005bf44  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005bf49  mov     [rbp+hKey], 0
0x18005bf51  lea     rcx, [rbp+hKey]
0x18005bf55  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005bf5a  lea     rdx, [rbp+lpSubKey]
0x18005bf5e  cmp     [rbp+var_18], 7
0x18005bf63  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18005bf68  mov     [rsp+70h+phkResult], rax; unsigned int
0x18005bf6d  mov     r9d, 2001Fh; samDesired
0x18005bf73  xor     r8d, r8d; ulOptions
0x18005bf76  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bf7d  call    cs:__imp_RegOpenKeyExW
0x18005bf84  nop     dword ptr [rax+rax+00h]
0x18005bf89  test    eax, eax
0x18005bf8b  jz      short loc_18005BFBC
0x18005bf8d  mov     edx, 531h; void *
0x18005bf92  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005bf99  mov     r9d, eax; char *
0x18005bf9c  mov     rcx, [rbp+18h]; this
0x18005bfa0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005bfa5  mov     ebx, eax
0x18005bfa7  lea     rcx, [rbp+hKey]
0x18005bfab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bfb0  nop
0x18005bfb1  lea     rcx, [rbp+lpSubKey]
0x18005bfb5  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005bfba  jmp     short loc_18005BFF9
0x18005bfbc  cmp     qword ptr [rdi+18h], 7
0x18005bfc1  jbe     short loc_18005BFC6
0x18005bfc3  mov     rdi, [rdi]
0x18005bfc6  mov     rdx, rdi; lpSubKey
0x18005bfc9  mov     rcx, [rbp+hKey]; hKey
0x18005bfcd  call    cs:__imp_RegDeleteTreeW
0x18005bfd4  nop     dword ptr [rax+rax+00h]
0x18005bfd9  test    eax, eax
0x18005bfdb  jz      short loc_18005BFE4
0x18005bfdd  mov     edx, 536h
0x18005bfe2  jmp     short loc_18005BF92
0x18005bfe4  lea     rcx, [rbp+hKey]
0x18005bfe8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bfed  nop
0x18005bfee  lea     rcx, [rbp+lpSubKey]
0x18005bff2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005bff7  xor     ebx, ebx
0x18005bff9  lea     rcx, [rbp+var_38]
0x18005bffd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005c002  mov     eax, ebx
0x18005c004  mov     rcx, [rbp+var_10]
0x18005c008  xor     rcx, rsp; StackCookie
0x18005c00b  call    __security_check_cookie
0x18005c010  mov     rbx, [rsp+70h+arg_10]
0x18005c018  add     rsp, 70h
0x18005c01c  pop     rdi
0x18005c01d  pop     rsi
0x18005c01e  pop     rbp
0x18005c01f  retn
```
