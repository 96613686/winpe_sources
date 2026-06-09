# ModernDeployment::Autopilot::Core::GetRegistrySettingStringOrDefault(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180143e40`
- end: `0x180144079`
- name: `?GetRegistrySettingStringOrDefault@Core@Autopilot@ModernDeployment@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `16`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180142fc0`
- `0x180143138`
- `0x1801431c4`
- `0x180143250`
- `0x1801432dc`
- `0x180143404`
- `0x180143490`
- `0x18014351c`
- `0x1801435a8`
- `0x180143634`
- `0x180143748`
- `0x180143c5c`
- `0x180144120`
- `0x18014435c`
- `0x1801443e8`
- `0x180144474`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x1800801fc`
- `0x1800839bc`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x180089ff4`
- `0x18008a0a8`
- `0x18008c244`
- `0x1800a1fe4`
- `0x180143e40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180143f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180143fee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180143f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180143fee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180143ed2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180143ed2`

## string_xrefs

- `0x180143e88`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`
- `0x180143ee7`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`
- `0x180143f96`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::GetRegistrySettingStringOrDefault(
        LPCWSTR lpValueName,
        __int64 a2,
        __int64 a3)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  bool v10; // sf
  LPBYTE v11; // rbx
  LSTATUS v12; // eax
  bool v13; // sf
  __int64 v14; // rax
  int phkResult; // [rsp+20h] [rbp-68h]
  unsigned int phkResulta; // [rsp+20h] [rbp-68h]
  int phkResultb; // [rsp+20h] [rbp-68h]
  LPBYTE lpData; // [rsp+30h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-50h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-4Ch] BYREF
  HKEY hKey; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\autopilotconfig.cpp",
      (const char *)0x80004001LL,
      phkResult);
    return 2147500033LL;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Provisioning\\AutopilotSettings", 0, 0x20019u, &hKey);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xCC,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\autopilotconfig.cpp",
           (const char *)v7,
           phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v8;
  }
  Type = 1;
  cbData = 0;
  std::wstring::wstring(v22, a2);
  v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  if ( !v10 && Type == 1 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpData,
      0,
      cbData);
    v11 = lpData;
    if ( !lpData )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\autopilotconfig.cpp",
        (const char *)0x8007000ELL,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
      std::wstring::_Tidy_deallocate(v22);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942414LL;
    }
    v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    v13 = v12 < 0;
    if ( v12 > 0 )
      v13 = 1;
    if ( !v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&v11[2 * v14] );
      if ( v14 )
        std::wstring::assign(v22, v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
  }
  std::wstring::operator=(a3, v22);
  std::wstring::_Tidy_deallocate(v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180143e40  mov     [rsp+arg_18], rbx
0x180143e45  push    rsi
0x180143e46  push    rdi
0x180143e47  push    r14
0x180143e49  sub     rsp, 70h
0x180143e4d  mov     rax, cs:__security_cookie
0x180143e54  xor     rax, rsp
0x180143e57  mov     [rsp+88h+var_20], rax
0x180143e5c  mov     rsi, r8
0x180143e5f  mov     rbx, rdx
0x180143e62  mov     rdi, rcx
0x180143e65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180143e6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180143e71  xor     r14d, r14d
0x180143e74  test    al, al
0x180143e76  jnz     short loc_180143EA0
0x180143e78  mov     rcx, [rsp+88h]; this
0x180143e80  mov     ebx, 80004001h
0x180143e85  mov     r9d, ebx; char *
0x180143e88  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180143e8f  mov     edx, 0C9h; void *
0x180143e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143e99  mov     eax, ebx
0x180143e9b  jmp     loc_18014405A
0x180143ea0  mov     [rsp+88h+hKey], r14
0x180143ea5  xor     edx, edx
0x180143ea7  lea     rcx, [rsp+88h+hKey]
0x180143eac  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180143eb1  lea     rax, [rsp+88h+hKey]
0x180143eb6  mov     [rsp+88h+phkResult], rax; unsigned int
0x180143ebb  mov     r9d, 20019h; samDesired
0x180143ec1  xor     r8d, r8d; ulOptions
0x180143ec4  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x180143ecb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180143ed2  call    cs:__imp_RegOpenKeyExW
0x180143ed8  test    eax, eax
0x180143eda  jz      short loc_180143F0B
0x180143edc  mov     rcx, [rsp+88h]; this
0x180143ee4  mov     r9d, eax; char *
0x180143ee7  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180143eee  mov     edx, 0CCh; void *
0x180143ef3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180143ef8  mov     ebx, eax
0x180143efa  lea     rcx, [rsp+88h+hKey]
0x180143eff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180143f04  mov     eax, ebx
0x180143f06  jmp     loc_18014405A
0x180143f0b  mov     [rsp+88h+Type], 1
0x180143f13  mov     [rsp+88h+cbData], r14d
0x180143f18  mov     rdx, rbx
0x180143f1b  lea     rcx, [rsp+88h+var_40]
0x180143f20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180143f25  nop
0x180143f26  lea     rax, [rsp+88h+cbData]
0x180143f2b  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180143f30  mov     [rsp+88h+phkResult], r14; int
0x180143f35  lea     r9, [rsp+88h+Type]; lpType
0x180143f3a  xor     r8d, r8d; lpReserved
0x180143f3d  mov     rdx, rdi; lpValueName
0x180143f40  mov     rcx, [rsp+88h+hKey]; hKey
0x180143f45  call    cs:__imp_RegQueryValueExW
0x180143f4b  test    eax, eax
0x180143f4d  jle     short loc_180143F59
0x180143f4f  movzx   eax, ax
0x180143f52  or      eax, 80070000h
0x180143f57  test    eax, eax
0x180143f59  js      loc_18014402F
0x180143f5f  cmp     [rsp+88h+Type], 1
0x180143f64  jnz     loc_18014402F
0x180143f6a  mov     r8d, [rsp+88h+cbData]
0x180143f6f  xor     edx, edx
0x180143f71  lea     rcx, [rsp+88h+lpData]
0x180143f76  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180143f7b  nop
0x180143f7c  mov     rbx, [rsp+88h+lpData]
0x180143f81  test    rbx, rbx
0x180143f84  jnz     short loc_180143FCF
0x180143f86  mov     rcx, [rsp+88h]; this
0x180143f8e  mov     ebx, 8007000Eh
0x180143f93  mov     r9d, ebx; char *
0x180143f96  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180143f9d  mov     edx, 0D5h; void *
0x180143fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143fa7  nop
0x180143fa8  lea     rcx, [rsp+88h+lpData]
0x180143fad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180143fb2  nop
0x180143fb3  lea     rcx, [rsp+88h+var_40]
0x180143fb8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180143fbd  nop
0x180143fbe  lea     rcx, [rsp+88h+hKey]
0x180143fc3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180143fc8  mov     eax, ebx
0x180143fca  jmp     loc_18014405A
0x180143fcf  lea     rax, [rsp+88h+cbData]
0x180143fd4  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180143fd9  mov     [rsp+88h+phkResult], rbx; lpData
0x180143fde  lea     r9, [rsp+88h+Type]; lpType
0x180143fe3  xor     r8d, r8d; lpReserved
0x180143fe6  mov     rdx, rdi; lpValueName
0x180143fe9  mov     rcx, [rsp+88h+hKey]; hKey
0x180143fee  call    cs:__imp_RegQueryValueExW
0x180143ff4  test    eax, eax
0x180143ff6  jle     short loc_180144002
0x180143ff8  movzx   eax, ax
0x180143ffb  or      eax, 80070000h
0x180144000  test    eax, eax
0x180144002  js      short loc_180144025
0x180144004  or      rax, 0FFFFFFFFFFFFFFFFh
0x180144008  inc     rax
0x18014400b  cmp     [rbx+rax*2], r14w
0x180144010  jnz     short loc_180144008
0x180144012  test    rax, rax
0x180144015  jz      short loc_180144025
0x180144017  mov     rdx, rbx
0x18014401a  lea     rcx, [rsp+88h+var_40]
0x18014401f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180144024  nop
0x180144025  lea     rcx, [rsp+88h+lpData]
0x18014402a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18014402f  lea     rdx, [rsp+88h+var_40]
0x180144034  mov     rcx, rsi
0x180144037  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18014403c  nop
0x18014403d  lea     rcx, [rsp+88h+var_40]
0x180144042  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144047  nop
0x180144048  lea     rcx, [rsp+88h+hKey]
0x18014404d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180144052  xor     eax, eax
0x180144054  jmp     short loc_18014405A
0x180144056  mov     eax, [rsp+88h+Type]
0x18014405a  mov     rcx, [rsp+88h+var_20]
0x18014405f  xor     rcx, rsp; StackCookie
0x180144062  call    __security_check_cookie
0x180144067  mov     rbx, [rsp+88h+arg_18]
0x18014406f  add     rsp, 70h
0x180144073  pop     r14
0x180144075  pop     rdi
0x180144076  pop     rsi
0x180144077  retn
```
