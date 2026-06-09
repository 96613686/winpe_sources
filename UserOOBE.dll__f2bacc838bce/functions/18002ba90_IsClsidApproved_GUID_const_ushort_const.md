# IsClsidApproved(_GUID const &,ushort const *)

- ea: `0x18002ba90`
- end: `0x18002bbba`
- name: `?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z`
- size: `298`
- prototype: `bool __fastcall(IID *rclsid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bd20`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180007710`
- `0x18000a5c8`
- `0x18000e2bc`
- `0x18000e580`
- `0x180018c98`
- `0x18002ba90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002bad2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002bad2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bb77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bb77`

## string_xrefs

- `0x18002bae7`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`
- `0x18002bb3d`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
bool __fastcall IsClsidApproved(IID *rclsid, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  int v5; // eax
  bool v6; // bl
  int phkResult; // [rsp+20h] [rbp-248h]
  int phkResulta; // [rsp+20h] [rbp-248h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-238h] BYREF
  HKEY v11; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v4 = StringFromCLSID(rclsid, &lpsz);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      (const char *)(unsigned int)v4,
      phkResult);
  memset_0(SubKey, 0, 0x208u);
  phkResulta = (int)lpsz;
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a2);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      (const char *)(unsigned int)v5,
      phkResulta);
  v11 = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v11) == 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  return v6;
}

```

## disassembly

```asm
0x18002ba90  mov     [rsp+arg_10], rbx
0x18002ba95  push    rdi
0x18002ba96  sub     rsp, 260h
0x18002ba9d  mov     rax, cs:__security_cookie
0x18002baa4  xor     rax, rsp
0x18002baa7  mov     [rsp+268h+var_18], rax
0x18002baaf  mov     rdi, rdx
0x18002bab2  mov     rbx, rcx
0x18002bab5  mov     [rsp+268h+lpsz], 0
0x18002babe  xor     edx, edx
0x18002bac0  lea     rcx, [rsp+268h+lpsz]
0x18002bac5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002baca  lea     rdx, [rsp+268h+lpsz]; lplpsz
0x18002bacf  mov     rcx, rbx; rclsid
0x18002bad2  call    cs:__imp_StringFromCLSID
0x18002bad8  mov     rcx, [rsp+268h]; this
0x18002bae0  test    eax, eax
0x18002bae2  jns     short loc_18002BAF9
0x18002bae4  mov     r9d, eax; char *
0x18002bae7  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002baee  mov     edx, 0Eh; void *
0x18002baf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002baf9  xor     edx, edx; Val
0x18002bafb  mov     r8d, 208h; Size
0x18002bb01  lea     rcx, [rsp+268h+SubKey]; void *
0x18002bb06  call    memset_0
0x18002bb0b  mov     rax, [rsp+268h+lpsz]
0x18002bb10  mov     qword ptr [rsp+268h+phkResult], rax; int
0x18002bb15  mov     r9, rdi
0x18002bb18  lea     r8, aSS_0; "%s\\%s"
0x18002bb1f  mov     edx, 104h; unsigned __int64
0x18002bb24  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18002bb29  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb2e  mov     rcx, [rsp+268h]; this
0x18002bb36  test    eax, eax
0x18002bb38  jns     short loc_18002BB4F
0x18002bb3a  mov     r9d, eax; char *
0x18002bb3d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002bb44  mov     edx, 10h; void *
0x18002bb49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bb4f  mov     [rsp+268h+var_230], 0
0x18002bb58  lea     rax, [rsp+268h+var_230]
0x18002bb5d  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x18002bb62  mov     r9d, 20019h; samDesired
0x18002bb68  xor     r8d, r8d; ulOptions
0x18002bb6b  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002bb70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bb77  call    cs:__imp_RegOpenKeyExW
0x18002bb7d  test    eax, eax
0x18002bb7f  setz    bl
0x18002bb82  lea     rcx, [rsp+268h+var_230]
0x18002bb87  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002bb8c  nop
0x18002bb8d  lea     rcx, [rsp+268h+lpsz]
0x18002bb92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bb97  mov     al, bl
0x18002bb99  mov     rcx, [rsp+268h+var_18]
0x18002bba1  xor     rcx, rsp; StackCookie
0x18002bba4  call    __security_check_cookie
0x18002bba9  mov     rbx, [rsp+268h+arg_10]
0x18002bbb1  add     rsp, 260h
0x18002bbb8  pop     rdi
0x18002bbb9  retn
```
