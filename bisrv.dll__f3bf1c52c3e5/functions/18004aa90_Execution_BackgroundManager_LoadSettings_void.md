# Execution::BackgroundManager::LoadSettings(void)

- ea: `0x18004aa90`
- end: `0x18004ad3a`
- name: `?LoadSettings@BackgroundManager@Execution@@MEAAJXZ`
- size: `682`
- prototype: `__int64 __fastcall(Execution::BackgroundManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18004aa90`
- `0x18004ad40`
- `0x18006cf70`
- `0x180095010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18004ac8b`
- `ntdll!RtlIsMultiSessionSku` at `0x18004ac8b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004aae0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004aae0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ab4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ab8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004abc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ab4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ab8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004abc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ab06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ab06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac66`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundManager::LoadSettings(Execution::BackgroundManager *this)
{
  LSTATUS v2; // eax
  signed int SpecialResourcesPackageList; // ebx
  bool v4; // cc
  int v5; // ecx
  __int64 v6; // r9
  int v8; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  HKEY v11; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+28h] BYREF
  int Data; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  Type = 4;
  cbData = 4;
  v11 = 0;
  Data = 0;
  v8 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v8, 0);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel",
         0,
         0x20019u,
         &hKey);
  SpecialResourcesPackageList = v2;
  v4 = v2 <= 0;
  if ( v2 )
  {
LABEL_2:
    if ( !v4 )
      SpecialResourcesPackageList = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_27;
  }
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"DisableResourceManagement", 0, &Type, (LPBYTE)&Data, &cbData) )
    *((_DWORD *)this + 86) = Data == 0;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"TelemetryHelperWorkItemDelayThresholdHighPri", 0, &Type, (LPBYTE)&Data, &cbData) )
    *((_DWORD *)this + 168) = Data;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"TelemetryHelperWorkItemDelayThresholdLowPri", 0, &Type, (LPBYTE)&Data, &cbData) )
    *((_DWORD *)this + 169) = Data;
  Execution::BmHostInfoManager::ReadEmptyHostTimeoutValueFromRegistry(
    (Execution::BackgroundManager *)((char *)this + 520),
    hKey);
  v2 = RegOpenKeyExW(hKey, L"EventSettings", 0, 0x20019u, &phkResult);
  SpecialResourcesPackageList = v2;
  if ( v2 )
  {
    if ( v2 != 2 )
    {
LABEL_12:
      v4 = v2 <= 0;
      goto LABEL_2;
    }
  }
  else
  {
    SpecialResourcesPackageList = (*(__int64 (__fastcall **)(Execution::BackgroundManager *, HKEY, char *, _QWORD))(*(_QWORD *)this + 192LL))(
                                    this,
                                    phkResult,
                                    (char *)this + 504,
                                    0);
    if ( SpecialResourcesPackageList < 0 )
      goto LABEL_27;
  }
  v2 = RegOpenKeyExW(hKey, L"LegacyEventSettings", 0, 0x20019u, &v11);
  SpecialResourcesPackageList = v2;
  if ( !v2 )
  {
    v5 = v8;
    if ( ((v8 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v8 == 6 )
      {
        if ( (unsigned __int8)RtlIsMultiSessionSku() )
          goto LABEL_23;
        v5 = v8;
      }
      if ( v5 != 9 )
      {
        v6 = 0;
        goto LABEL_24;
      }
    }
LABEL_23:
    v6 = 1;
LABEL_24:
    SpecialResourcesPackageList = (*(__int64 (__fastcall **)(Execution::BackgroundManager *, HKEY, char *, __int64))(*(_QWORD *)this + 192LL))(
                                    this,
                                    v11,
                                    (char *)this + 352,
                                    v6);
    if ( SpecialResourcesPackageList < 0 )
      goto LABEL_27;
    goto LABEL_25;
  }
  if ( v2 != 2 )
    goto LABEL_12;
LABEL_25:
  SpecialResourcesPackageList = Execution::BackgroundManager::LoadSpecialResourcesPackageList(this);
  if ( SpecialResourcesPackageList >= 0 )
    SpecialResourcesPackageList = (*(__int64 (__fastcall **)(Execution::BackgroundManager *))(*(_QWORD *)this + 200LL))(this);
LABEL_27:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v11 )
  {
    RegCloseKey(v11);
    v11 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)SpecialResourcesPackageList;
}

```

## disassembly

```asm
0x18004aa90  mov     [rsp-18h+arg_0], rbx
0x18004aa95  push    rbp
0x18004aa96  push    rdi
0x18004aa97  push    r14
0x18004aa99  mov     rbp, rsp
0x18004aa9c  sub     rsp, 50h
0x18004aaa0  mov     rdi, rcx
0x18004aaa3  mov     [rbp+hKey], 0
0x18004aaab  mov     r14d, 4
0x18004aab1  mov     [rbp+var_10], 0
0x18004aab9  xor     ecx, ecx
0x18004aabb  mov     [rbp+Type], r14d
0x18004aabf  xor     r8d, r8d
0x18004aac2  mov     [rbp+cbData], r14d
0x18004aac6  lea     rdx, [rbp+var_20]
0x18004aaca  mov     [rbp+var_8], 0
0x18004aad2  mov     [rbp+Data], 0
0x18004aad9  mov     [rbp+var_20], 0
0x18004aae0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004aae6  lea     rax, [rbp+hKey]
0x18004aaea  mov     r9d, 20019h; samDesired
0x18004aaf0  xor     r8d, r8d; ulOptions
0x18004aaf3  mov     [rsp+50h+phkResult], rax; phkResult
0x18004aaf8  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004aaff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ab06  call    cs:__imp_RegOpenKeyExW
0x18004ab0c  mov     ebx, eax
0x18004ab0e  test    eax, eax
0x18004ab10  jz      short loc_18004AB26
0x18004ab12  jle     loc_18004ACED
0x18004ab18  movzx   ebx, ax
0x18004ab1b  or      ebx, 80070000h
0x18004ab21  jmp     loc_18004ACED
0x18004ab26  mov     rcx, [rbp+hKey]; hKey
0x18004ab2a  lea     rax, [rbp+cbData]
0x18004ab2e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004ab33  lea     r9, [rbp+Type]; lpType
0x18004ab37  lea     rax, [rbp+Data]
0x18004ab3b  mov     [rbp+cbData], r14d
0x18004ab3f  xor     r8d, r8d; lpReserved
0x18004ab42  mov     [rsp+50h+phkResult], rax; lpData
0x18004ab47  lea     rdx, aDisableresourc; "DisableResourceManagement"
0x18004ab4e  call    cs:__imp_RegQueryValueExW
0x18004ab54  test    eax, eax
0x18004ab56  jnz     short loc_18004AB64
0x18004ab58  cmp     [rbp+Data], eax
0x18004ab5b  setz    al
0x18004ab5e  mov     [rdi+158h], eax
0x18004ab64  mov     rcx, [rbp+hKey]; hKey
0x18004ab68  lea     rax, [rbp+cbData]
0x18004ab6c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004ab71  lea     r9, [rbp+Type]; lpType
0x18004ab75  lea     rax, [rbp+Data]
0x18004ab79  mov     [rbp+cbData], r14d
0x18004ab7d  xor     r8d, r8d; lpReserved
0x18004ab80  mov     [rsp+50h+phkResult], rax; lpData
0x18004ab85  lea     rdx, aTelemetryhelpe_0; "TelemetryHelperWorkItemDelayThresholdHi"...
0x18004ab8c  call    cs:__imp_RegQueryValueExW
0x18004ab92  test    eax, eax
0x18004ab94  jnz     short loc_18004AB9F
0x18004ab96  mov     eax, [rbp+Data]
0x18004ab99  mov     [rdi+2A0h], eax
0x18004ab9f  mov     rcx, [rbp+hKey]; hKey
0x18004aba3  lea     rax, [rbp+cbData]
0x18004aba7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18004abac  lea     r9, [rbp+Type]; lpType
0x18004abb0  lea     rax, [rbp+Data]
0x18004abb4  mov     [rbp+cbData], r14d
0x18004abb8  xor     r8d, r8d; lpReserved
0x18004abbb  mov     [rsp+50h+phkResult], rax; lpData
0x18004abc0  lea     rdx, aTelemetryhelpe; "TelemetryHelperWorkItemDelayThresholdLo"...
0x18004abc7  call    cs:__imp_RegQueryValueExW
0x18004abcd  test    eax, eax
0x18004abcf  jnz     short loc_18004ABDA
0x18004abd1  mov     eax, [rbp+Data]
0x18004abd4  mov     [rdi+2A4h], eax
0x18004abda  mov     rdx, [rbp+hKey]; HKEY
0x18004abde  lea     rcx, [rdi+208h]; this
0x18004abe5  call    ?ReadEmptyHostTimeoutValueFromRegistry@BmHostInfoManager@Execution@@QEAAXPEAUHKEY__@@@Z; Execution::BmHostInfoManager::ReadEmptyHostTimeoutValueFromRegistry(HKEY__ *)
0x18004abea  mov     rcx, [rbp+hKey]; hKey
0x18004abee  lea     rax, [rbp+var_10]
0x18004abf2  mov     r9d, 20019h; samDesired
0x18004abf8  mov     [rsp+50h+phkResult], rax; phkResult
0x18004abfd  xor     r8d, r8d; ulOptions
0x18004ac00  lea     rdx, aEventsettings; "EventSettings"
0x18004ac07  call    cs:__imp_RegOpenKeyExW
0x18004ac0d  mov     ebx, eax
0x18004ac0f  test    eax, eax
0x18004ac11  jz      short loc_18004AC1F
0x18004ac13  cmp     eax, 2
0x18004ac16  jz      short loc_18004AC49
0x18004ac18  test    eax, eax
0x18004ac1a  jmp     loc_18004AB12
0x18004ac1f  mov     rax, [rdi]
0x18004ac22  lea     r8, [rdi+1F8h]
0x18004ac29  mov     rdx, [rbp+var_10]
0x18004ac2d  xor     r9d, r9d
0x18004ac30  mov     rcx, rdi
0x18004ac33  mov     rax, [rax+0C0h]
0x18004ac3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac3f  mov     ebx, eax
0x18004ac41  test    eax, eax
0x18004ac43  js      loc_18004ACED
0x18004ac49  mov     rcx, [rbp+hKey]; hKey
0x18004ac4d  lea     rax, [rbp+var_8]
0x18004ac51  mov     r9d, 20019h; samDesired
0x18004ac57  mov     [rsp+50h+phkResult], rax; phkResult
0x18004ac5c  xor     r8d, r8d; ulOptions
0x18004ac5f  lea     rdx, aLegacyeventset; "LegacyEventSettings"
0x18004ac66  call    cs:__imp_RegOpenKeyExW
0x18004ac6c  mov     ebx, eax
0x18004ac6e  test    eax, eax
0x18004ac70  jz      short loc_18004AC79
0x18004ac72  cmp     eax, 2
0x18004ac75  jz      short loc_18004ACCB
0x18004ac77  jmp     short loc_18004AC18
0x18004ac79  mov     ecx, [rbp+var_20]
0x18004ac7c  lea     eax, [rcx-1]
0x18004ac7f  test    eax, 0FFFFFFFDh
0x18004ac84  jz      short loc_18004ACA2
0x18004ac86  cmp     ecx, 6
0x18004ac89  jnz     short loc_18004AC98
0x18004ac8b  call    cs:__imp_RtlIsMultiSessionSku
0x18004ac91  test    al, al
0x18004ac93  jnz     short loc_18004ACA2
0x18004ac95  mov     ecx, [rbp+var_20]
0x18004ac98  cmp     ecx, 9
0x18004ac9b  jz      short loc_18004ACA2
0x18004ac9d  xor     r9d, r9d
0x18004aca0  jmp     short loc_18004ACA8
0x18004aca2  mov     r9d, 1
0x18004aca8  mov     rax, [rdi]
0x18004acab  lea     r8, [rdi+160h]
0x18004acb2  mov     rdx, [rbp+var_8]
0x18004acb6  mov     rcx, rdi
0x18004acb9  mov     rax, [rax+0C0h]
0x18004acc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acc5  mov     ebx, eax
0x18004acc7  test    eax, eax
0x18004acc9  js      short loc_18004ACED
0x18004accb  mov     rcx, rdi; this
0x18004acce  call    ?LoadSpecialResourcesPackageList@BackgroundManager@Execution@@IEAAJXZ; Execution::BackgroundManager::LoadSpecialResourcesPackageList(void)
0x18004acd3  mov     ebx, eax
0x18004acd5  test    eax, eax
0x18004acd7  js      short loc_18004ACED
0x18004acd9  mov     rax, [rdi]
0x18004acdc  mov     rcx, rdi
0x18004acdf  mov     rax, [rax+0C8h]
0x18004ace6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aceb  mov     ebx, eax
0x18004aced  mov     rcx, [rbp+var_10]; hKey
0x18004acf1  test    rcx, rcx
0x18004acf4  jz      short loc_18004AD04
0x18004acf6  call    cs:__imp_RegCloseKey
0x18004acfc  mov     [rbp+var_10], 0
0x18004ad04  mov     rcx, [rbp+var_8]; hKey
0x18004ad08  test    rcx, rcx
0x18004ad0b  jz      short loc_18004AD1B
0x18004ad0d  call    cs:__imp_RegCloseKey
0x18004ad13  mov     [rbp+var_8], 0
0x18004ad1b  mov     rcx, [rbp+hKey]; hKey
0x18004ad1f  test    rcx, rcx
0x18004ad22  jz      short loc_18004AD2A
0x18004ad24  call    cs:__imp_RegCloseKey
0x18004ad2a  mov     eax, ebx
0x18004ad2c  mov     rbx, [rsp+50h+arg_0]
0x18004ad31  add     rsp, 50h
0x18004ad35  pop     r14
0x18004ad37  pop     rdi
0x18004ad38  pop     rbp
0x18004ad39  retn
```
