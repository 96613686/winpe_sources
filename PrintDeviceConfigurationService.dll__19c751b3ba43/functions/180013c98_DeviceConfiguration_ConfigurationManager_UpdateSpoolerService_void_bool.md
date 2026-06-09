# DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(void *,bool)

- ea: `0x180013c98`
- end: `0x180013e48`
- name: `?_UpdateSpoolerService@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z`
- size: `432`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, void *, char)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x180003621`
- `0x18000c158`
- `0x18000ea48`
- `0x180011adc`
- `0x180011bb4`
- `0x1800125bc`
- `0x1800138cc`
- `0x180013c98`
- `0x180014114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013dee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013dee`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013ce5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013ce5`

## string_xrefs

- `0x180013cd7`: `SYSTEM\CurrentControlSet\Services\Spooler`
- `0x180013de3`: `RequiredPrivileges`
- `0x180013cfe`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013e07`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013cf2`: `RegOpenKeyTransacted (Spooler Service) failed!`
- `0x180013dfb`: `RegSetValueEx (RequiredPrivileges) failed!`
- `0x180013d46`: `SeTcbPrivilege`
- `0x180013d3f`: `SeImpersonatePrivilege`
- `0x180013d82`: `SeTcbPrivilege`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_UpdateSpoolerService(
        DeviceConfiguration::ConfigurationManager *this,
        void *a2,
        char a3)
{
  unsigned int v4; // eax
  char IsEnabled; // al
  __int16 *v6; // r8
  const wchar_t *v7; // rdx
  char *v8; // rbx
  const BYTE *lpData; // rcx
  signed __int64 v10; // rax
  unsigned int v11; // eax
  const char *cbData; // [rsp+28h] [rbp-48h]
  const char *cbDataa; // [rsp+28h] [rbp-48h]
  void *v14[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]
  BYTE *v16[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v17; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF

  hKey = 0;
  v4 = RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\Spooler", 0, 2u, &hKey, a2, 0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x18C,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v4,
    (unsigned int)"RegOpenKeyTransacted (Spooler Service) failed!",
    cbData);
  *(_OWORD *)v16 = 0;
  v17 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl);
  v6 = &word_18001DD0E;
  if ( !IsEnabled )
    v6 = (__int16 *)&dword_18001DD94;
  v7 = L"SeTcbPrivilege";
  if ( !IsEnabled )
    v7 = L"SeImpersonatePrivilege";
  std::vector<unsigned short>::assign<unsigned short const *,0>(v16, v7, v6);
  *(_OWORD *)v14 = 0;
  v15 = 0;
  std::vector<unsigned short>::_Buy_raw(v14, 133);
  v8 = (char *)v14[0];
  memmove_0(v14[0], L"SeTcbPrivilege", 0x10Au);
  v14[1] = v8 + 266;
  v20 = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v20);
  if ( a3 )
  {
    lpData = v16[0];
    v10 = v16[1] - v16[0];
  }
  else
  {
    v10 = (char *)v14[1] - (char *)v14[0];
    lpData = (const BYTE *)v14[0];
  }
  v11 = RegSetValueExW(hKey, L"RequiredPrivileges", 0, 7u, lpData, 2 * (v10 >> 1));
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x1A0,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v11,
    (unsigned int)"RegSetValueEx (RequiredPrivileges) failed!",
    cbDataa);
  std::vector<unsigned short>::_Tidy(v14);
  std::vector<unsigned short>::_Tidy(v16);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180013c98  mov     r11, rsp
0x180013c9b  mov     [r11+10h], rbx
0x180013c9f  mov     [r11+18h], rdi
0x180013ca3  mov     [r11+8], rcx
0x180013ca7  push    rbp
0x180013ca8  mov     rbp, rsp
0x180013cab  sub     rsp, 70h
0x180013caf  mov     dil, r8b
0x180013cb2  mov     [rbp+hKey], 0
0x180013cba  mov     qword ptr [r11-48h], 0
0x180013cc2  mov     [r11-50h], rdx
0x180013cc6  lea     rax, [rbp+hKey]
0x180013cca  mov     [r11-58h], rax
0x180013cce  mov     r9d, 2; samDesired
0x180013cd4  xor     r8d, r8d; ulOptions
0x180013cd7  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Sp"...
0x180013cde  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013ce5  call    cs:__imp_RegOpenKeyTransactedW
0x180013ceb  mov     r9d, eax; char *
0x180013cee  mov     rcx, [rbp+8]; this
0x180013cf2  lea     rax, aRegopenkeytran_2; "RegOpenKeyTransacted (Spooler Service) "...
0x180013cf9  mov     [rsp+70h+lpData], rax; unsigned int
0x180013cfe  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013d05  mov     edx, 18Ch; void *
0x180013d0a  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013d0f  xorps   xmm0, xmm0
0x180013d12  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180013d17  mov     [rbp+var_8], 0
0x180013d1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180013d26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180013d2b  lea     rcx, dword_18001DD94
0x180013d32  lea     r8, word_18001DD0E
0x180013d39  test    al, al
0x180013d3b  cmovz   r8, rcx
0x180013d3f  lea     rcx, aSeimpersonatep; "SeImpersonatePrivilege"
0x180013d46  lea     rdx, aSetcbprivilege; "SeTcbPrivilege"
0x180013d4d  cmovz   rdx, rcx
0x180013d51  lea     rcx, [rbp+var_18]
0x180013d55  call    ??$assign@PEBG$0A@@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEBG0@Z; std::vector<ushort>::assign<ushort const *,0>(ushort const *,ushort const *)
0x180013d5a  xorps   xmm0, xmm0
0x180013d5d  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180013d62  mov     [rbp+var_20], 0
0x180013d6a  mov     edx, 85h
0x180013d6f  lea     rcx, [rbp+var_30]
0x180013d73  call    ?_Buy_raw@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Buy_raw(unsigned __int64)
0x180013d78  mov     rbx, [rbp+var_30]
0x180013d7c  mov     r8d, 10Ah; Size
0x180013d82  lea     rdx, aSetcbprivilege_0; "SeTcbPrivilege"
0x180013d89  mov     rcx, rbx; void *
0x180013d8c  call    memmove_0
0x180013d91  lea     rax, [rbx+10Ah]
0x180013d98  mov     [rbp+var_30+8], rax
0x180013d9c  mov     [rbp+arg_18], 0
0x180013da4  lea     rcx, [rbp+arg_18]
0x180013da8  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x180013dad  nop
0x180013dae  test    dil, dil
0x180013db1  jz      short loc_180013DC0
0x180013db3  mov     rax, [rbp+var_18+8]
0x180013db7  mov     rcx, [rbp+var_18]
0x180013dbb  sub     rax, rcx
0x180013dbe  jmp     short loc_180013DCC
0x180013dc0  mov     rax, [rbp+var_30+8]
0x180013dc4  sub     rax, [rbp+var_30]
0x180013dc8  mov     rcx, [rbp+var_30]
0x180013dcc  sar     rax, 1
0x180013dcf  add     eax, eax
0x180013dd1  mov     [rsp+70h+cbData], eax; char *
0x180013dd5  mov     [rsp+70h+lpData], rcx; lpData
0x180013dda  mov     r9d, 7; dwType
0x180013de0  xor     r8d, r8d; Reserved
0x180013de3  lea     rdx, aRequiredprivil; "RequiredPrivileges"
0x180013dea  mov     rcx, [rbp+hKey]; hKey
0x180013dee  call    cs:__imp_RegSetValueExW
0x180013df4  mov     r9d, eax; char *
0x180013df7  mov     rcx, [rbp+8]; this
0x180013dfb  lea     rax, aRegsetvalueexR; "RegSetValueEx (RequiredPrivileges) fail"...
0x180013e02  mov     [rsp+70h+lpData], rax; unsigned int
0x180013e07  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013e0e  mov     edx, 1A0h; void *
0x180013e13  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013e18  nop
0x180013e19  lea     rcx, [rbp+var_30]
0x180013e1d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180013e22  nop
0x180013e23  lea     rcx, [rbp+var_18]
0x180013e27  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180013e2c  nop
0x180013e2d  lea     rcx, [rbp+hKey]
0x180013e31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013e36  lea     r11, [rsp+70h+var_s0]
0x180013e3b  mov     rbx, [r11+18h]
0x180013e3f  mov     rdi, [r11+20h]
0x180013e43  mov     rsp, r11
0x180013e46  pop     rbp
0x180013e47  retn
```
