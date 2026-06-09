# GetMachineIdInRemoteSessionFromRegistry(void)

- ea: `0x180072554`
- end: `0x180072746`
- name: `?GetMachineIdInRemoteSessionFromRegistry@@YA?AU_GUID@@XZ`
- size: `498`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800727e0`

## callees

- `0x180016c74`
- `0x18002cdf4`
- `0x180043680`
- `0x1800441ac`
- `0x180071bb8`
- `0x180071e18`
- `0x180072328`
- `0x180072554`
- `0x18007292c`
- `0x18007294c`
- `0x180072fc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800726d8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800726d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007260f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072649`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007260f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072649`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800725c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800725c0`

## string_xrefs

- `0x18007269a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactoryclassfactory.cpp`
- `0x1800726ec`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactoryclassfactory.cpp`

## pseudocode

```c
struct _GUID *__fastcall GetMachineIdInRemoteSessionFromRegistry(struct _GUID *__return_ptr retstr)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int ValueW; // eax
  unsigned int v5; // r8d
  int v6; // eax
  const OLECHAR *v7; // rcx
  HRESULT v8; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[232]; // [rsp+58h] [rbp-A8h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+140h] [rbp+40h] BYREF
  GUID pclsid; // [rsp+160h] [rbp+60h] BYREF
  _BYTE pvData[528]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\ControlSet001\\Control", 0, 0x20019u, &hkey);
  if ( v2 )
    wil::details::in1diag3::_FailFast_Win32(retaddr, (void *)0x3D, v3, (const char *)v2, phkResult);
  if ( RegGetValueW(hkey, 0, L"StaticContainerId", 2u, 0, pvData, &pcbData) )
  {
    ValueW = RegGetValueW(hkey, 0, L"ContainerId", 2u, 0, pvData, &pcbData);
    if ( ValueW )
      wil::details::in1diag3::_FailFast_Win32(retaddr, (void *)0x54, v5, (const char *)ValueW, phkResulta);
  }
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v14);
  lpsz[0] = (LPCOLESTR)v14;
  lpsz[1] = (LPCOLESTR)pvData;
  v6 = wil::ResultFromException__lambda_15281fa14afac7ac25c0fc12cb28b1fb___(lpsz);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactoryclassfactory.cpp",
      (const char *)(unsigned int)v6,
      phkResulta);
  pclsid = GUID_NULL;
  std::basic_stringbuf<unsigned short>::str(v15, lpsz);
  v7 = (const OLECHAR *)lpsz;
  if ( lpsz[3] > (LPCOLESTR)7 )
    v7 = lpsz[0];
  v8 = CLSIDFromString(v7, &pclsid);
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactoryclassfactory.cpp",
      (const char *)(unsigned int)v8,
      phkResulta);
  std::wstring::_Tidy_deallocate(lpsz);
  *retstr = pclsid;
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return retstr;
}

```

## disassembly

```asm
0x180072554  mov     [rsp-8+arg_0], rbx
0x180072559  push    rbp
0x18007255a  lea     rbp, [rsp-290h]
0x180072562  sub     rsp, 390h
0x180072569  mov     rax, cs:__security_cookie
0x180072570  xor     rax, rsp
0x180072573  mov     [rbp+290h+var_10], rax
0x18007257a  mov     rbx, rcx
0x18007257d  xor     edx, edx; Val
0x18007257f  mov     r8d, 208h; Size
0x180072585  lea     rcx, [rbp+290h+var_220]; void *
0x180072589  call    memset_0
0x18007258e  mov     [rsp+390h+var_350], 208h
0x180072596  mov     [rsp+390h+hkey], 0
0x18007259f  lea     rax, [rsp+390h+hkey]
0x1800725a4  mov     [rsp+390h+phkResult], rax; unsigned int
0x1800725a9  mov     r9d, 20019h; samDesired
0x1800725af  xor     r8d, r8d; ulOptions
0x1800725b2  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Control"
0x1800725b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800725c0  call    cs:__imp_RegOpenKeyExW
0x1800725c6  test    eax, eax
0x1800725c8  jz      short loc_1800725DF
0x1800725ca  mov     rcx, [rbp+298h]; this
0x1800725d1  mov     r9d, eax; char *
0x1800725d4  mov     edx, 3Dh ; '='; void *
0x1800725d9  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x1800725df  lea     rax, [rsp+390h+var_350]
0x1800725e4  mov     [rsp+390h+pcbData], rax; pcbData
0x1800725e9  lea     rax, [rbp+290h+var_220]
0x1800725ed  mov     [rsp+390h+pvData], rax; pvData
0x1800725f2  mov     [rsp+390h+phkResult], 0; int
0x1800725fb  mov     r9d, 2; dwFlags
0x180072601  lea     r8, Value; "StaticContainerId"
0x180072608  xor     edx, edx; lpSubKey
0x18007260a  mov     rcx, [rsp+390h+hkey]; hkey
0x18007260f  call    cs:__imp_RegGetValueW
0x180072615  test    eax, eax
0x180072617  jz      short loc_180072668
0x180072619  lea     rax, [rsp+390h+var_350]
0x18007261e  mov     [rsp+390h+pcbData], rax; pcbData
0x180072623  lea     rax, [rbp+290h+var_220]
0x180072627  mov     [rsp+390h+pvData], rax; pvData
0x18007262c  mov     [rsp+390h+phkResult], 0; unsigned int
0x180072635  mov     r9d, 2; dwFlags
0x18007263b  lea     r8, aContainerid; "ContainerId"
0x180072642  xor     edx, edx; lpSubKey
0x180072644  mov     rcx, [rsp+390h+hkey]; hkey
0x180072649  call    cs:__imp_RegGetValueW
0x18007264f  test    eax, eax
0x180072651  jz      short loc_180072668
0x180072653  mov     rcx, [rbp+298h]; this
0x18007265a  mov     r9d, eax; char *
0x18007265d  mov     edx, 54h ; 'T'; void *
0x180072662  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x180072668  lea     rcx, [rsp+390h+var_340]
0x18007266d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180072672  lea     rax, [rsp+390h+var_340]
0x180072677  mov     [rbp+290h+lpsz], rax
0x18007267b  lea     rax, [rbp+290h+var_220]
0x18007267f  mov     [rbp+290h+var_248], rax
0x180072683  lea     rcx, [rbp+290h+lpsz]
0x180072687  call    wil__ResultFromException__lambda_15281fa14afac7ac25c0fc12cb28b1fb___
0x18007268c  test    eax, eax
0x18007268e  jns     short loc_1800726AC
0x180072690  mov     rcx, [rbp+298h]; this
0x180072697  mov     r9d, eax; char *
0x18007269a  lea     r8, aOnecoreWindows_9; "onecore\\windows\\accessibletech\\uiama"...
0x1800726a1  mov     edx, 5Eh ; '^'; void *
0x1800726a6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800726ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800726b3  movdqu  xmmword ptr [rbp+290h+pclsid.Data1], xmm0
0x1800726b8  lea     rdx, [rbp+290h+lpsz]
0x1800726bc  lea     rcx, [rsp+390h+var_338]
0x1800726c1  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800726c6  lea     rcx, [rbp+290h+lpsz]
0x1800726ca  cmp     [rbp+290h+var_238], 7
0x1800726cf  cmova   rcx, [rbp+290h+lpsz]; lpsz
0x1800726d4  lea     rdx, [rbp+290h+pclsid]; pclsid
0x1800726d8  call    cs:__imp_CLSIDFromString
0x1800726de  test    eax, eax
0x1800726e0  jns     short loc_1800726FE
0x1800726e2  mov     rcx, [rbp+298h]; this
0x1800726e9  mov     r9d, eax; char *
0x1800726ec  lea     r8, aOnecoreWindows_9; "onecore\\windows\\accessibletech\\uiama"...
0x1800726f3  mov     edx, 61h ; 'a'; void *
0x1800726f8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800726fe  lea     rcx, [rbp+290h+lpsz]
0x180072702  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180072707  movups  xmm0, xmmword ptr [rbp+290h+pclsid.Data1]
0x18007270b  movdqu  xmmword ptr [rbx], xmm0
0x18007270f  lea     rcx, [rsp+390h+var_340]
0x180072714  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180072719  lea     rcx, [rsp+390h+hkey]
0x18007271e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072723  mov     rax, rbx
0x180072726  mov     rcx, [rbp+290h+var_10]
0x18007272d  xor     rcx, rsp; StackCookie
0x180072730  call    __security_check_cookie
0x180072735  mov     rbx, [rsp+390h+arg_0]
0x18007273d  add     rsp, 390h
0x180072744  pop     rbp
0x180072745  retn
```
