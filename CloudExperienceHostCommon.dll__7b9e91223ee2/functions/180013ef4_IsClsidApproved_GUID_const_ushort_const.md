# IsClsidApproved(_GUID const &,ushort const *)

- ea: `0x180013ef4`
- end: `0x180014013`
- name: `?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z`
- size: `287`
- prototype: `bool __fastcall(IID *rclsid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180021f00`

## callees

- `0x180010c8c`
- `0x1800128a4`
- `0x180013c14`
- `0x180013ef4`
- `0x18001401c`
- `0x18001475c`
- `0x18001a540`
- `0x18001b004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013fd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013fd8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013f2f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013f2f`

## string_xrefs

- `0x180013f72`: `SOFTWARE\Microsoft\Windows\CurrentVersion\CloudExperienceHost\RegisteredClsids`
- `0x180013f44`: `onecoreuap\shell\cloudexperiencehost\onecore\inc\cloudexperiencehostbrokerhelpers.h`
- `0x180013f9e`: `onecoreuap\shell\cloudexperiencehost\onecore\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsClsidApproved(IID *rclsid, const unsigned __int16 *a2)
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
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v3 = StringFromCLSID(rclsid, &lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\inc\\cloudexperiencehostbrokerhelpers.h",
      (const char *)(unsigned int)v3,
      phkResult);
  memset_0(SubKey, 0, 0x208u);
  phkResulta = (int)lpsz;
  v4 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%s\\%s",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\RegisteredClsids");
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\inc\\cloudexperiencehostbrokerhelpers.h",
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
0x180013ef4  push    rbx
0x180013ef6  sub     rsp, 260h
0x180013efd  mov     rax, cs:__security_cookie
0x180013f04  xor     rax, rsp
0x180013f07  mov     [rsp+268h+var_18], rax
0x180013f0f  mov     rbx, rcx
0x180013f12  mov     [rsp+268h+lpsz], 0
0x180013f1b  xor     edx, edx
0x180013f1d  lea     rcx, [rsp+268h+lpsz]
0x180013f22  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013f27  lea     rdx, [rsp+268h+lpsz]; lplpsz
0x180013f2c  mov     rcx, rbx; rclsid
0x180013f2f  call    cs:__imp_StringFromCLSID
0x180013f35  mov     rcx, [rsp+268h]; this
0x180013f3d  test    eax, eax
0x180013f3f  jns     short loc_180013F56
0x180013f41  mov     r9d, eax; char *
0x180013f44  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudexperiencehost"...
0x180013f4b  mov     edx, 0Eh; void *
0x180013f50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013f56  xor     edx, edx; Val
0x180013f58  mov     r8d, 208h; Size
0x180013f5e  lea     rcx, [rsp+268h+SubKey]; void *
0x180013f63  call    memset_0
0x180013f68  mov     rax, [rsp+268h+lpsz]
0x180013f6d  mov     qword ptr [rsp+268h+phkResult], rax; int
0x180013f72  lea     r9, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013f79  lea     r8, aSS; "%s\\%s"
0x180013f80  mov     edx, 104h; unsigned __int64
0x180013f85  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x180013f8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013f8f  mov     rcx, [rsp+268h]; this
0x180013f97  test    eax, eax
0x180013f99  jns     short loc_180013FB0
0x180013f9b  mov     r9d, eax; char *
0x180013f9e  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudexperiencehost"...
0x180013fa5  mov     edx, 10h; void *
0x180013faa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013fb0  mov     [rsp+268h+var_230], 0
0x180013fb9  lea     rax, [rsp+268h+var_230]
0x180013fbe  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x180013fc3  mov     r9d, 20019h; samDesired
0x180013fc9  xor     r8d, r8d; ulOptions
0x180013fcc  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x180013fd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013fd8  call    cs:__imp_RegOpenKeyExW
0x180013fde  test    eax, eax
0x180013fe0  setz    bl
0x180013fe3  lea     rcx, [rsp+268h+var_230]
0x180013fe8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013fed  nop
0x180013fee  lea     rcx, [rsp+268h+lpsz]
0x180013ff3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180013ff8  mov     al, bl
0x180013ffa  mov     rcx, [rsp+268h+var_18]
0x180014002  xor     rcx, rsp; StackCookie
0x180014005  call    __security_check_cookie
0x18001400a  add     rsp, 260h
0x180014011  pop     rbx
0x180014012  retn
```
