# ModernDeployment::Autopilot::Core::GetRegistrySettingStringOrDefault(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180147eac`
- end: `0x1801480f7`
- name: `?GetRegistrySettingStringOrDefault@Core@Autopilot@ModernDeployment@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `16`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180147020`
- `0x180147198`
- `0x180147224`
- `0x1801472b0`
- `0x18014733c`
- `0x180147464`
- `0x1801474f0`
- `0x18014757c`
- `0x180147608`
- `0x180147694`
- `0x1801477a8`
- `0x180147cbc`
- `0x1801481a0`
- `0x1801483dc`
- `0x180148468`
- `0x1801484f4`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080c10`
- `0x180084574`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x18008aea8`
- `0x18008af70`
- `0x18008d290`
- `0x1800a35f8`
- `0x180147eac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147fb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180148066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147fb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180148066`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147f3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147f3e`

## string_xrefs

- `0x180147ef4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`
- `0x180147f59`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`
- `0x18014800e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\autopilotconfig.cpp`

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
0x180147eac  mov     [rsp+arg_18], rbx
0x180147eb1  push    rsi
0x180147eb2  push    rdi
0x180147eb3  push    r14
0x180147eb5  sub     rsp, 70h
0x180147eb9  mov     rax, cs:__security_cookie
0x180147ec0  xor     rax, rsp
0x180147ec3  mov     [rsp+88h+var_20], rax
0x180147ec8  mov     rsi, r8
0x180147ecb  mov     rbx, rdx
0x180147ece  mov     rdi, rcx
0x180147ed1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180147ed8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180147edd  xor     r14d, r14d
0x180147ee0  test    al, al
0x180147ee2  jnz     short loc_180147F0C
0x180147ee4  mov     rcx, [rsp+88h]; this
0x180147eec  mov     ebx, 80004001h
0x180147ef1  mov     r9d, ebx; char *
0x180147ef4  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180147efb  mov     edx, 0C9h; void *
0x180147f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147f05  mov     eax, ebx
0x180147f07  jmp     loc_1801480D8
0x180147f0c  mov     [rsp+88h+hKey], r14
0x180147f11  xor     edx, edx
0x180147f13  lea     rcx, [rsp+88h+hKey]
0x180147f18  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180147f1d  lea     rax, [rsp+88h+hKey]
0x180147f22  mov     [rsp+88h+phkResult], rax; unsigned int
0x180147f27  mov     r9d, 20019h; samDesired
0x180147f2d  xor     r8d, r8d; ulOptions
0x180147f30  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x180147f37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180147f3e  call    cs:__imp_RegOpenKeyExW
0x180147f45  nop     dword ptr [rax+rax+00h]
0x180147f4a  test    eax, eax
0x180147f4c  jz      short loc_180147F7D
0x180147f4e  mov     rcx, [rsp+88h]; this
0x180147f56  mov     r9d, eax; char *
0x180147f59  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180147f60  mov     edx, 0CCh; void *
0x180147f65  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180147f6a  mov     ebx, eax
0x180147f6c  lea     rcx, [rsp+88h+hKey]
0x180147f71  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180147f76  mov     eax, ebx
0x180147f78  jmp     loc_1801480D8
0x180147f7d  mov     [rsp+88h+Type], 1
0x180147f85  mov     [rsp+88h+cbData], r14d
0x180147f8a  mov     rdx, rbx
0x180147f8d  lea     rcx, [rsp+88h+var_40]
0x180147f92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180147f97  nop
0x180147f98  lea     rax, [rsp+88h+cbData]
0x180147f9d  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180147fa2  mov     [rsp+88h+phkResult], r14; int
0x180147fa7  lea     r9, [rsp+88h+Type]; lpType
0x180147fac  xor     r8d, r8d; lpReserved
0x180147faf  mov     rdx, rdi; lpValueName
0x180147fb2  mov     rcx, [rsp+88h+hKey]; hKey
0x180147fb7  call    cs:__imp_RegQueryValueExW
0x180147fbe  nop     dword ptr [rax+rax+00h]
0x180147fc3  test    eax, eax
0x180147fc5  jle     short loc_180147FD1
0x180147fc7  movzx   eax, ax
0x180147fca  or      eax, 80070000h
0x180147fcf  test    eax, eax
0x180147fd1  js      loc_1801480AD
0x180147fd7  cmp     [rsp+88h+Type], 1
0x180147fdc  jnz     loc_1801480AD
0x180147fe2  mov     r8d, [rsp+88h+cbData]
0x180147fe7  xor     edx, edx
0x180147fe9  lea     rcx, [rsp+88h+lpData]
0x180147fee  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180147ff3  nop
0x180147ff4  mov     rbx, [rsp+88h+lpData]
0x180147ff9  test    rbx, rbx
0x180147ffc  jnz     short loc_180148047
0x180147ffe  mov     rcx, [rsp+88h]; this
0x180148006  mov     ebx, 8007000Eh
0x18014800b  mov     r9d, ebx; char *
0x18014800e  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\moderndeployment\\au"...
0x180148015  mov     edx, 0D5h; void *
0x18014801a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014801f  nop
0x180148020  lea     rcx, [rsp+88h+lpData]
0x180148025  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18014802a  nop
0x18014802b  lea     rcx, [rsp+88h+var_40]
0x180148030  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180148035  nop
0x180148036  lea     rcx, [rsp+88h+hKey]
0x18014803b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180148040  mov     eax, ebx
0x180148042  jmp     loc_1801480D8
0x180148047  lea     rax, [rsp+88h+cbData]
0x18014804c  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180148051  mov     [rsp+88h+phkResult], rbx; lpData
0x180148056  lea     r9, [rsp+88h+Type]; lpType
0x18014805b  xor     r8d, r8d; lpReserved
0x18014805e  mov     rdx, rdi; lpValueName
0x180148061  mov     rcx, [rsp+88h+hKey]; hKey
0x180148066  call    cs:__imp_RegQueryValueExW
0x18014806d  nop     dword ptr [rax+rax+00h]
0x180148072  test    eax, eax
0x180148074  jle     short loc_180148080
0x180148076  movzx   eax, ax
0x180148079  or      eax, 80070000h
0x18014807e  test    eax, eax
0x180148080  js      short loc_1801480A3
0x180148082  or      rax, 0FFFFFFFFFFFFFFFFh
0x180148086  inc     rax
0x180148089  cmp     [rbx+rax*2], r14w
0x18014808e  jnz     short loc_180148086
0x180148090  test    rax, rax
0x180148093  jz      short loc_1801480A3
0x180148095  mov     rdx, rbx
0x180148098  lea     rcx, [rsp+88h+var_40]
0x18014809d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801480a2  nop
0x1801480a3  lea     rcx, [rsp+88h+lpData]
0x1801480a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801480ad  lea     rdx, [rsp+88h+var_40]
0x1801480b2  mov     rcx, rsi
0x1801480b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801480ba  nop
0x1801480bb  lea     rcx, [rsp+88h+var_40]
0x1801480c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801480c5  nop
0x1801480c6  lea     rcx, [rsp+88h+hKey]
0x1801480cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801480d0  xor     eax, eax
0x1801480d2  jmp     short loc_1801480D8
0x1801480d4  mov     eax, [rsp+88h+Type]
0x1801480d8  mov     rcx, [rsp+88h+var_20]
0x1801480dd  xor     rcx, rsp; StackCookie
0x1801480e0  call    __security_check_cookie
0x1801480e5  mov     rbx, [rsp+88h+arg_18]
0x1801480ed  add     rsp, 70h
0x1801480f1  pop     r14
0x1801480f3  pop     rdi
0x1801480f4  pop     rsi
0x1801480f5  retn
```
