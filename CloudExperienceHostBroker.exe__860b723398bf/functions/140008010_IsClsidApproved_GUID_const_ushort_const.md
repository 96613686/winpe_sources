# IsClsidApproved(_GUID const &,ushort const *)

- ea: `0x140008010`
- end: `0x14000811c`
- name: `?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z`
- size: `268`
- prototype: `bool __fastcall(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008ed0`

## callees

- `0x14000252f`
- `0x1400052c8`
- `0x140007488`
- `0x1400074a8`
- `0x140008010`
- `0x14000923c`
- `0x1400094d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000803c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000803c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400080e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400080e1`

## string_xrefs

- `0x140008051`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`
- `0x1400080a7`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
bool __fastcall IsClsidApproved(const struct _GUID *a1, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // eax
  bool v5; // bl
  int phkResult; // [rsp+20h] [rbp-248h]
  int phkResulta; // [rsp+20h] [rbp-248h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-238h] BYREF
  HKEY v10; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  lpsz = 0;
  v3 = StringFromCLSID(a1, &lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      (const char *)(unsigned int)v3,
      phkResult);
  memset_0(SubKey, 0, 0x208u);
  phkResulta = (int)lpsz;
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a2);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      (const char *)(unsigned int)v4,
      phkResulta);
  v10 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v10) == 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpsz);
  return v5;
}

```

## disassembly

```asm
0x140008010  push    rbx
0x140008012  sub     rsp, 260h
0x140008019  mov     rax, cs:__security_cookie
0x140008020  xor     rax, rsp
0x140008023  mov     [rsp+268h+var_18], rax
0x14000802b  mov     rbx, rdx
0x14000802e  mov     [rsp+268h+lpsz], 0
0x140008037  lea     rdx, [rsp+268h+lpsz]; lplpsz
0x14000803c  call    cs:__imp_StringFromCLSID
0x140008042  mov     rcx, [rsp+268h]; this
0x14000804a  test    eax, eax
0x14000804c  jns     short loc_140008063
0x14000804e  mov     r9d, eax; char *
0x140008051  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140008058  mov     edx, 0Eh; void *
0x14000805d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008063  xor     edx, edx; Val
0x140008065  mov     r8d, 208h; Size
0x14000806b  lea     rcx, [rsp+268h+SubKey]; void *
0x140008070  call    memset_0
0x140008075  mov     rax, [rsp+268h+lpsz]
0x14000807a  mov     qword ptr [rsp+268h+phkResult], rax; int
0x14000807f  mov     r9, rbx
0x140008082  lea     r8, aSS; "%s\\%s"
0x140008089  mov     edx, 104h; unsigned __int64
0x14000808e  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x140008093  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008098  mov     rcx, [rsp+268h]; this
0x1400080a0  test    eax, eax
0x1400080a2  jns     short loc_1400080B9
0x1400080a4  mov     r9d, eax; char *
0x1400080a7  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1400080ae  mov     edx, 10h; void *
0x1400080b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400080b9  mov     [rsp+268h+var_230], 0
0x1400080c2  lea     rax, [rsp+268h+var_230]
0x1400080c7  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x1400080cc  mov     r9d, 20019h; samDesired
0x1400080d2  xor     r8d, r8d; ulOptions
0x1400080d5  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x1400080da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400080e1  call    cs:__imp_RegOpenKeyExW
0x1400080e7  test    eax, eax
0x1400080e9  setz    bl
0x1400080ec  lea     rcx, [rsp+268h+var_230]
0x1400080f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400080f6  nop
0x1400080f7  lea     rcx, [rsp+268h+lpsz]
0x1400080fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140008101  mov     al, bl
0x140008103  mov     rcx, [rsp+268h+var_18]
0x14000810b  xor     rcx, rsp; StackCookie
0x14000810e  call    __security_check_cookie
0x140008113  add     rsp, 260h
0x14000811a  pop     rbx
0x14000811b  retn
```
