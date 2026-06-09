# DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180011174`
- end: `0x1800114a3`
- name: `?_PopulateInfoFromDeviceRegistry@DeviceManager@DeviceConfiguration@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@1@Z`
- size: `815`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000fbe0`

## callees

- `0x1800020c0`
- `0x18000aeac`
- `0x18000d89c`
- `0x18000ea48`
- `0x18000ea88`
- `0x18000eb80`
- `0x18000f32c`
- `0x18000f9ec`
- `0x18000fa2c`
- `0x180011174`
- `0x1800115a0`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180011432`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180011432`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800111da`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800111da`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180011259`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180011259`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x18001120a`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x18001120a`

## string_xrefs

- `0x18001122d`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x1800112cc`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x180011342`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x18001144f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x1800111ae`: `Attempting to retrieve printer name and port name information from the registry for device %ws`
- `0x1800111b5`: `DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry`
- `0x18001121d`: `SetupDiOpenDeviceInfo failed!`
- `0x1800112b6`: `Failed to get printer name from registry!`
- `0x18001132c`: `Failed to get port name from registry!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry(
        __int64 a1,
        const WCHAR *a2,
        __int64 *a3,
        __int64 *a4)
{
  const WCHAR *v6; // rdi
  const WCHAR *v7; // r8
  HDEVINFO DeviceInfoList; // rbx
  const WCHAR *v9; // rdx
  BOOL v10; // eax
  HKEY v11; // rbx
  __int64 v12; // r8
  __int64 StringValue; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int v16; // eax
  const char *samDesired; // [rsp+28h] [rbp-F0h]
  const char *samDesireda; // [rsp+28h] [rbp-F0h]
  char *v20; // [rsp+30h] [rbp-E8h]
  char *v21; // [rsp+30h] [rbp-E8h]
  HKEY v22; // [rsp+38h] [rbp-E0h] BYREF
  HKEY v23; // [rsp+40h] [rbp-D8h] BYREF
  HDEVINFO v24; // [rsp+48h] [rbp-D0h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+90h] [rbp-88h] BYREF
  int v28; // [rsp+A0h] [rbp-78h]
  int v29; // [rsp+A4h] [rbp-74h]
  __int64 v30; // [rsp+A8h] [rbp-70h]
  int v31; // [rsp+B0h] [rbp-68h]
  int v32; // [rsp+B4h] [rbp-64h]
  __int64 *v33; // [rsp+B8h] [rbp-60h]
  __int128 v34; // [rsp+C0h] [rbp-58h]
  int v35; // [rsp+D0h] [rbp-48h]
  int v36; // [rsp+D4h] [rbp-44h]
  __int64 v37; // [rsp+D8h] [rbp-40h]
  int v38; // [rsp+E0h] [rbp-38h]
  int v39; // [rsp+E4h] [rbp-34h]
  __int64 *v40; // [rsp+E8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v6 = a2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v7 = a2;
  else
    v7 = *(const WCHAR **)a2;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry",
    L"Attempting to retrieve printer name and port name information from the registry for device %ws",
    v7);
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  v24 = DeviceInfoList;
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v9 = v6;
  else
    v9 = *(const WCHAR **)v6;
  v10 = SetupDiOpenDeviceInfoW(DeviceInfoList, v9, 0, 0, &DeviceInfoData);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x2AB,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
    (const char *)!v10,
    (bool)"SetupDiOpenDeviceInfo failed!",
    samDesired);
  v11 = SetupDiOpenDevRegKey(DeviceInfoList, &DeviceInfoData, 1u, 0, 1u, 1u);
  v23 = v11;
  LOBYTE(v20) = 0;
  v22 = v11;
  StringValue = PrintCore::RegHelpers::GetStringValue(v26, &v22, v12, L"PrinterName");
  std::wstring::operator=(a3, StringValue);
  std::wstring::_Tidy_deallocate(v26);
  wil::details::in1diag3::Throw_Win32IfMsg(
    retaddr,
    (void *)0x2B1,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
    (const char *)2,
    1,
    (bool)"Failed to get printer name from registry!",
    v20);
  LOBYTE(v21) = 0;
  v22 = v11;
  v15 = PrintCore::RegHelpers::GetStringValue(v26, &v22, v14, L"PortName");
  std::wstring::operator=(a4, v15);
  std::wstring::_Tidy_deallocate(v26);
  wil::details::in1diag3::Throw_Win32IfMsg(
    retaddr,
    (void *)0x2B6,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
    (const char *)2,
    1,
    (bool)"Failed to get port name from registry!",
    v21);
  v27 = xmmword_18001CB78;
  v28 = 5;
  v29 = 0;
  v30 = 0;
  v31 = 18;
  v32 = 2 * *((_DWORD *)a3 + 4) + 2;
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v33 = a3;
  v34 = xmmword_18001CB60;
  v35 = 2;
  v36 = 0;
  v37 = 0;
  v38 = 18;
  v39 = 2 * *((_DWORD *)a4 + 4) + 2;
  if ( (unsigned __int64)a4[3] > 7 )
    a4 = (__int64 *)*a4;
  v40 = a4;
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(const WCHAR **)v6;
  v16 = DevSetObjectProperties(3, v6, 2, &v27);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2C8,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
    (const char *)v16,
    (int)"DevSetObjectProperties for printer name and port name failed!",
    samDesireda);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x180011174  mov     [rsp+arg_0], rbx
0x180011179  push    rsi
0x18001117a  push    rdi
0x18001117b  push    r14
0x18001117d  sub     rsp, 100h
0x180011184  mov     rax, cs:__security_cookie
0x18001118b  xor     rax, rsp
0x18001118e  mov     [rsp+118h+var_28], rax
0x180011196  mov     rsi, r9
0x180011199  mov     r14, r8
0x18001119c  mov     rdi, rdx
0x18001119f  cmp     qword ptr [rdx+18h], 7
0x1800111a4  jbe     short loc_1800111AB
0x1800111a6  mov     r8, [rdx]
0x1800111a9  jmp     short loc_1800111AE
0x1800111ab  mov     r8, rdi
0x1800111ae  lea     rdx, aAttemptingToRe; "Attempting to retrieve printer name and"...
0x1800111b5  lea     rcx, aDeviceconfigur_22; "DeviceConfiguration::DeviceManager::_Po"...
0x1800111bc  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800111c1  xorps   xmm0, xmm0
0x1800111c4  movups  xmmword ptr [rsp+118h+var_C8.cbSize], xmm0
0x1800111c9  movups  xmmword ptr [rsp+118h+var_C8.ClassGuid.Data4+4], xmm0
0x1800111ce  mov     [rsp+118h+var_C8.cbSize], 20h ; ' '
0x1800111d6  xor     edx, edx; hwndParent
0x1800111d8  xor     ecx, ecx; ClassGuid
0x1800111da  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800111e0  mov     rbx, rax
0x1800111e3  mov     [rsp+118h+var_D0], rax
0x1800111e8  cmp     qword ptr [rdi+18h], 7
0x1800111ed  jbe     short loc_1800111F4
0x1800111ef  mov     rdx, [rdi]
0x1800111f2  jmp     short loc_1800111F7
0x1800111f4  mov     rdx, rdi; DeviceInstanceId
0x1800111f7  lea     rax, [rsp+118h+var_C8]
0x1800111fc  mov     [rsp+118h+DeviceInfoData], rax; DeviceInfoData
0x180011201  xor     r9d, r9d; OpenFlags
0x180011204  xor     r8d, r8d; hwndParent
0x180011207  mov     rcx, rbx; DeviceInfoSet
0x18001120a  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180011210  test    eax, eax
0x180011212  setz    al
0x180011215  mov     rcx, [rsp+118h]; this
0x18001121d  lea     rdx, aSetupdiopendev_1; "SetupDiOpenDeviceInfo failed!"
0x180011224  mov     [rsp+118h+DeviceInfoData], rdx; bool
0x180011229  movzx   r9d, al; char *
0x18001122d  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180011234  mov     edx, 2ABh; void *
0x180011239  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001123e  mov     r8d, 1; Scope
0x180011244  mov     [rsp+118h+samDesired], r8d; samDesired
0x180011249  mov     dword ptr [rsp+118h+DeviceInfoData], r8d; KeyType
0x18001124e  xor     r9d, r9d; HwProfile
0x180011251  lea     rdx, [rsp+118h+var_C8]; DeviceInfoData
0x180011256  mov     rcx, rbx; DeviceInfoSet
0x180011259  call    cs:__imp_SetupDiOpenDevRegKey
0x18001125f  mov     rbx, rax
0x180011262  mov     [rsp+118h+var_D8], rax
0x180011267  mov     byte ptr [rsp+118h+var_E8], 0; char *
0x18001126c  mov     [rsp+118h+var_E0], rax
0x180011271  lea     rax, [rsp+118h+var_E8]
0x180011276  mov     qword ptr [rsp+118h+samDesired], rax
0x18001127b  lea     r9, aPrintername; "PrinterName"
0x180011282  lea     rdx, [rsp+118h+var_E0]
0x180011287  lea     rcx, [rsp+118h+var_A8]
0x18001128c  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x180011291  mov     rdx, rax
0x180011294  mov     rcx, r14
0x180011297  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001129c  lea     rcx, [rsp+118h+var_A8]
0x1800112a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112a6  cmp     byte ptr [rsp+118h+var_E8], 0
0x1800112ab  setz    al
0x1800112ae  mov     rcx, [rsp+118h]; this
0x1800112b6  lea     rdx, aFailedToGetPri; "Failed to get printer name from registr"...
0x1800112bd  mov     qword ptr [rsp+118h+samDesired], rdx; bool
0x1800112c2  mov     byte ptr [rsp+118h+DeviceInfoData], al; char
0x1800112c6  mov     r9d, 2; char *
0x1800112cc  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x1800112d3  mov     edx, 2B1h; void *
0x1800112d8  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x1800112dd  mov     byte ptr [rsp+118h+var_E8], 0; char *
0x1800112e2  mov     [rsp+118h+var_E0], rbx
0x1800112e7  lea     rax, [rsp+118h+var_E8]
0x1800112ec  mov     qword ptr [rsp+118h+samDesired], rax
0x1800112f1  lea     r9, aPortname; "PortName"
0x1800112f8  lea     rdx, [rsp+118h+var_E0]
0x1800112fd  lea     rcx, [rsp+118h+var_A8]
0x180011302  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x180011307  mov     rdx, rax
0x18001130a  mov     rcx, rsi
0x18001130d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011312  lea     rcx, [rsp+118h+var_A8]
0x180011317  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001131c  cmp     byte ptr [rsp+118h+var_E8], 0
0x180011321  setz    al
0x180011324  mov     rcx, [rsp+118h]; this
0x18001132c  lea     rdx, aFailedToGetPor; "Failed to get port name from registry!"
0x180011333  mov     qword ptr [rsp+118h+samDesired], rdx; char *
0x180011338  mov     byte ptr [rsp+118h+DeviceInfoData], al; char
0x18001133c  mov     r9d, 2; char *
0x180011342  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180011349  mov     edx, 2B6h; void *
0x18001134e  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x180011353  movups  xmm0, cs:xmmword_18001CB78
0x18001135a  movaps  [rsp+118h+var_88], xmm0
0x180011362  mov     eax, cs:dword_18001CB88
0x180011368  mov     [rsp+118h+var_78], eax
0x18001136f  mov     [rsp+118h+var_74], 0
0x18001137a  mov     [rsp+118h+var_70], 0
0x180011386  mov     ecx, 12h
0x18001138b  mov     [rsp+118h+var_68], ecx
0x180011392  mov     eax, [r14+10h]
0x180011396  lea     eax, ds:2[rax*2]
0x18001139d  mov     [rsp+118h+var_64], eax
0x1800113a4  cmp     qword ptr [r14+18h], 7
0x1800113a9  jbe     short loc_1800113AE
0x1800113ab  mov     r14, [r14]
0x1800113ae  mov     [rsp+118h+var_60], r14
0x1800113b6  movups  xmm0, cs:xmmword_18001CB60
0x1800113bd  movaps  [rsp+118h+var_58], xmm0
0x1800113c5  mov     eax, cs:dword_18001CB70
0x1800113cb  mov     [rsp+118h+var_48], eax
0x1800113d2  mov     [rsp+118h+var_44], 0
0x1800113dd  mov     [rsp+118h+var_40], 0
0x1800113e9  mov     [rsp+118h+var_38], ecx
0x1800113f0  mov     eax, [rsi+10h]
0x1800113f3  lea     eax, ds:2[rax*2]
0x1800113fa  mov     [rsp+118h+var_34], eax
0x180011401  cmp     qword ptr [rsi+18h], 7
0x180011406  jbe     short loc_18001140B
0x180011408  mov     rsi, [rsi]
0x18001140b  mov     [rsp+118h+var_30], rsi
0x180011413  cmp     qword ptr [rdi+18h], 7
0x180011418  jbe     short loc_18001141D
0x18001141a  mov     rdi, [rdi]
0x18001141d  lea     r9, [rsp+118h+var_88]
0x180011425  mov     r8d, 2
0x18001142b  mov     rdx, rdi
0x18001142e  lea     ecx, [r8+1]
0x180011432  call    cs:__imp_DevSetObjectProperties
0x180011438  mov     rcx, [rsp+118h]; this
0x180011440  lea     rdx, aDevsetobjectpr_3; "DevSetObjectProperties for printer name"...
0x180011447  mov     [rsp+118h+DeviceInfoData], rdx; int
0x18001144c  mov     r9d, eax; char *
0x18001144f  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180011456  mov     edx, 2C8h; void *
0x18001145b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011460  nop
0x180011461  lea     rcx, [rsp+118h+var_D8]
0x180011466  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001146b  nop
0x18001146c  lea     rcx, [rsp+118h+var_D0]
0x180011471  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011476  xor     eax, eax
0x180011478  jmp     short loc_18001147E
0x18001147a  mov     eax, dword ptr [rsp+118h+var_E0]
0x18001147e  mov     rcx, [rsp+118h+var_28]
0x180011486  xor     rcx, rsp; StackCookie
0x180011489  call    __security_check_cookie
0x18001148e  mov     rbx, [rsp+118h+arg_0]
0x180011496  add     rsp, 100h
0x18001149d  pop     r14
0x18001149f  pop     rdi
0x1800114a0  pop     rsi
0x1800114a1  retn
```
