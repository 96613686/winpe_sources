# SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)

- ea: `0x180013174`
- end: `0x18001328a`
- name: `?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z`
- size: `278`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000f838`
- `0x180026ca0`
- `0x18002bf60`
- `0x180049e54`
- `0x180049f10`

## callees

- `0x180002b20`
- `0x18000cea0`
- `0x18000e1c8`
- `0x18000e224`
- `0x18000fa10`
- `0x180013174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013237`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013227`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013227`

## pseudocode

```c
HKEY *__fastcall SingletonHelpers::details::GetSingletonSessionSubKey(HKEY *a1, __int64 *a2, HKEY *a3, REGSAM a4)
{
  __int64 v6; // rcx
  const wchar_t *v8; // [rsp+50h] [rbp+7h] BYREF
  __int64 v9; // [rsp+60h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+27h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+2Fh] BYREF

  v8 = (const wchar_t *)a1;
  phkResult = *a3;
  v9 = *a2;
  v8 = L"Singletons";
  lpSubKey = 0;
  wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const (&)[2],wchar_t const *,wchar_t const (&)[2],wchar_t const *>(
    (unsigned int)&lpSubKey,
    (unsigned int)&v8,
    (_DWORD)a3,
    (unsigned int)&v9);
  hKey = 0;
  if ( CreateShellSessionKey(v6, &hKey) < 0 )
  {
    *a1 = 0;
  }
  else
  {
    phkResult = 0;
    if ( (a4 & 6) != 0 )
      RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, a4, 0, &phkResult, 0);
    else
      RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
    *a1 = phkResult;
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x180013174  push    rbp
0x180013176  push    rbx
0x180013177  push    rdi
0x180013178  lea     rbp, [rsp-47h]
0x18001317d  sub     rsp, 90h
0x180013184  mov     rax, cs:__security_cookie
0x18001318b  xor     rax, rsp
0x18001318e  mov     [rbp+57h+var_20], rax
0x180013192  mov     [rbp+57h+var_50], rcx
0x180013196  mov     edi, r9d
0x180013199  mov     rax, [r8]
0x18001319c  lea     r9, [rbp+57h+var_40]
0x1800131a0  mov     [rbp+57h+var_38], rax
0x1800131a4  mov     rbx, rcx
0x1800131a7  mov     rax, [rdx]
0x1800131aa  lea     rcx, [rbp+57h+lpSubKey]
0x1800131ae  mov     [rbp+57h+var_40], rax
0x1800131b2  lea     rdx, [rbp+57h+var_50]
0x1800131b6  mov     rax, cs:off_18005F888; "Singletons"
0x1800131bd  mov     [rbp+57h+var_50], rax
0x1800131c1  lea     rax, [rbp+57h+var_38]
0x1800131c5  mov     qword ptr [rsp+0A0h+samDesired], rax
0x1800131ca  mov     [rbp+57h+lpSubKey], 0
0x1800131d2  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WAEAY01$$CB_WPEB_WAEAY01$$CB_WPEB_W@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@$$QEAPEB_WAEAY01$$CB_W010@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const (&)[2],wchar_t const *,wchar_t const (&)[2],wchar_t const *>(wchar_t const * &&,wchar_t const (&)[2],wchar_t const * &&,wchar_t const (&)[2],wchar_t const * &&)
0x1800131d7  lea     rdx, [rbp+57h+hKey]; HKEY *
0x1800131db  mov     [rbp+57h+hKey], 0
0x1800131e3  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x1800131e8  test    eax, eax
0x1800131ea  js      short loc_180013257
0x1800131ec  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800131f0  lea     rax, [rbp+57h+var_38]
0x1800131f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800131f8  xor     r8d, r8d; ulOptions
0x1800131fb  mov     [rbp+57h+var_38], 0
0x180013203  test    dil, 6
0x180013207  jz      short loc_18001322F
0x180013209  mov     [rsp+0A0h+lpdwDisposition], r8; lpdwDisposition
0x18001320e  xor     r9d, r9d; lpClass
0x180013211  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180013216  mov     [rsp+0A0h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18001321b  mov     [rsp+0A0h+samDesired], edi; samDesired
0x18001321f  mov     [rsp+0A0h+dwOptions], 1; dwOptions
0x180013227  call    cs:__imp_RegCreateKeyExW
0x18001322d  jmp     short loc_18001323D
0x18001322f  mov     r9d, edi; samDesired
0x180013232  mov     qword ptr [rsp+0A0h+dwOptions], rax; phkResult
0x180013237  call    cs:__imp_RegOpenKeyExW
0x18001323d  mov     rcx, [rbp+57h+var_38]
0x180013241  mov     [rbx], rcx
0x180013244  lea     rcx, [rbp+57h+var_38]
0x180013248  mov     [rbp+57h+var_38], 0
0x180013250  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013255  jmp     short loc_18001325E
0x180013257  mov     qword ptr [rbx], 0
0x18001325e  lea     rcx, [rbp+57h+hKey]
0x180013262  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013267  lea     rcx, [rbp+57h+lpSubKey]
0x18001326b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180013270  mov     rax, rbx
0x180013273  mov     rcx, [rbp+57h+var_20]
0x180013277  xor     rcx, rsp; StackCookie
0x18001327a  call    __security_check_cookie
0x18001327f  add     rsp, 90h
0x180013286  pop     rdi
0x180013287  pop     rbx
0x180013288  pop     rbp
0x180013289  retn
```
