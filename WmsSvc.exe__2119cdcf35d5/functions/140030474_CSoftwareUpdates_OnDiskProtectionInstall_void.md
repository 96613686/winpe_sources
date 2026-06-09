# CSoftwareUpdates::OnDiskProtectionInstall(void)

- ea: `0x140030474`
- end: `0x1400307db`
- name: `?OnDiskProtectionInstall@CSoftwareUpdates@@QEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(CSoftwareUpdates *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140009af0`

## callees

- `0x14002fad4`
- `0x140030474`
- `0x140030d94`
- `0x140031424`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400304e3`
- `ADVAPI32!RegGetValueW` at `0x1400304e3`
- `ADVAPI32!RegCloseKey` at `0x1400307c4`
- `ADVAPI32!RegCloseKey` at `0x1400307c4`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140030579`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140030579`
- `ADVAPI32!RegCreateKeyExW` at `0x14003065e`
- `ADVAPI32!RegCreateKeyExW` at `0x14003065e`
- `ADVAPI32!RegSetValueExW` at `0x1400306f6`
- `ADVAPI32!RegSetValueExW` at `0x1400306f6`
- `KERNEL32!IsDebuggerPresent` at `0x1400305ca`
- `KERNEL32!IsDebuggerPresent` at `0x1400306a2`
- `KERNEL32!IsDebuggerPresent` at `0x14003073a`
- `KERNEL32!IsDebuggerPresent` at `0x1400305ca`
- `KERNEL32!IsDebuggerPresent` at `0x1400306a2`
- `KERNEL32!IsDebuggerPresent` at `0x14003073a`

## string_xrefs

- `0x1400304ee`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400304a3`: `NoAutoUpdate`
- `0x140030504`: `WU No Auto Update setting not found -- exiting`
- `0x14003051d`: `CSoftwareUpdates::GetWindowsUpdateNoAutoUpdateSetting`
- `0x1400305ac`: `CSoftwareUpdates::OnDiskProtectionInstall`
- `0x14003067c`: `CSoftwareUpdates::OnDiskProtectionInstall`
- `0x140030714`: `CSoftwareUpdates::OnDiskProtectionInstall`
- `0x1400304d5`: `Software\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x140030552`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::OnDiskProtectionInstall(CSoftwareUpdates *this)
{
  unsigned int v2; // ebx
  LSTATUS ValueW; // eax
  int AutomaticMaintenanceSettings; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  CSoftwareUpdates *v8; // rcx
  unsigned int v9; // edx
  CSoftwareUpdates *v10; // rcx
  LPDWORD pcbData; // [rsp+30h] [rbp-30h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-30h]
  PHKEY phkResult; // [rsp+38h] [rbp-28h]
  int v15; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v18; // [rsp+B0h] [rbp+50h] BYREF
  DWORD v19; // [rsp+B8h] [rbp+58h] BYREF

  Data = 0;
  v18 = 3;
  v15 = 1;
  hKey = 0;
  v2 = 0;
  v19 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
             L"NoAutoUpdate",
             0x18u,
             0,
             &Data,
             &v19);
  if ( ValueW )
  {
    v2 = ValueW > 0 ? (unsigned __int16)ValueW | 0x80070000 : ValueW;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      310,
      L"CSoftwareUpdates::GetWindowsUpdateNoAutoUpdateSetting",
      L"WU No Auto Update setting not found -- exiting");
    if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147024894 )
    {
      AutomaticMaintenanceSettings = -2147467259;
      goto LABEL_35;
    }
  }
  if ( v2 == -2147024894 )
  {
    v5 = RegDeleteKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
           L"WuOriginalNotificationLevel");
    AutomaticMaintenanceSettings = v5;
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      if ( v5 > 0 )
        AutomaticMaintenanceSettings = (unsigned __int16)v5 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        0x17Fu,
        L"CSoftwareUpdates::OnDiskProtectionInstall",
        L"CBRAEx",
        L"(err == 0L) || (err == 2L)",
        AutomaticMaintenanceSettings);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          383,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"(err == 0L) || (err == 2L)",
          AutomaticMaintenanceSettings);
      }
      else
      {
        LODWORD(pcbData) = AutomaticMaintenanceSettings;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          383,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"(err == 0L) || (err == 2L)",
          pcbData);
      }
      goto LABEL_35;
    }
  }
  else
  {
    v6 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    AutomaticMaintenanceSettings = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        AutomaticMaintenanceSettings = (unsigned __int16)v6 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        0x184u,
        L"CSoftwareUpdates::OnDiskProtectionInstall",
        L"CBRAEx",
        L"err == 0L",
        AutomaticMaintenanceSettings);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = AutomaticMaintenanceSettings;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          388,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"err == 0L",
          phkResult);
      }
      else
      {
        LODWORD(pcbDataa) = AutomaticMaintenanceSettings;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          388,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"err == 0L",
          pcbDataa);
      }
      goto LABEL_35;
    }
    v7 = RegSetValueExW(hKey, L"WuOriginalNotificationLevel", 0, 4u, (const BYTE *)&Data, 4u);
    AutomaticMaintenanceSettings = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        AutomaticMaintenanceSettings = (unsigned __int16)v7 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        0x187u,
        L"CSoftwareUpdates::OnDiskProtectionInstall",
        L"CBRAEx",
        L"err == 0L",
        AutomaticMaintenanceSettings);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = AutomaticMaintenanceSettings;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          391,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"err == 0L",
          phkResult);
      }
      else
      {
        LODWORD(pcbDataa) = AutomaticMaintenanceSettings;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          391,
          L"CSoftwareUpdates::OnDiskProtectionInstall",
          L"CBRAEx",
          L"err == 0L",
          pcbDataa);
      }
      goto LABEL_35;
    }
  }
  v8 = this;
  if ( Data )
  {
    v9 = 0;
  }
  else
  {
    AutomaticMaintenanceSettings = CSoftwareUpdates::GetAutomaticMaintenanceSettings(this, &v18, &v15);
    if ( AutomaticMaintenanceSettings < 0 )
      goto LABEL_35;
    v9 = 2;
    v8 = this;
  }
  AutomaticMaintenanceSettings = CSoftwareUpdates::SetSettings((__int64)v8, v9, v18, 0, 15, 1u);
  if ( AutomaticMaintenanceSettings >= 0 )
    AutomaticMaintenanceSettings = CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(v10, 1u);
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)AutomaticMaintenanceSettings;
}

```

## disassembly

```asm
0x140030474  push    rbp
0x140030476  push    rbx
0x140030477  push    rsi
0x140030478  push    rdi
0x140030479  push    r12
0x14003047b  push    r13
0x14003047d  push    r14
0x14003047f  mov     rbp, rsp
0x140030482  sub     rsp, 60h
0x140030486  mov     r14d, 1
0x14003048c  mov     [rbp+Data], 0
0x140030493  lea     rax, [rbp+arg_18]
0x140030497  mov     [rbp+arg_10], 3
0x14003049e  mov     [rsp+60h+pcbData], rax; pcbData
0x1400304a3  lea     r8, aNoautoupdate; "NoAutoUpdate"
0x1400304aa  lea     rax, [rbp+Data]
0x1400304ae  mov     [rbp+var_10], r14d
0x1400304b2  mov     rdi, rcx
0x1400304b5  mov     [rsp+60h+pvData], rax; pvData
0x1400304ba  lea     r13d, [r14+3]
0x1400304be  mov     [rbp+hKey], 0
0x1400304c6  xor     ebx, ebx
0x1400304c8  mov     [rbp+arg_18], r13d
0x1400304cc  lea     r9d, [r14+17h]; dwFlags
0x1400304d0  mov     [rsp+60h+pdwType], rbx; pdwType
0x1400304d5  lea     rdx, ?s_szAutomaticUpdatesRegKey@CSoftwareUpdates@@0QBGB; "Software\\Policies\\Microsoft\\Windows"...
0x1400304dc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400304e3  call    cs:__imp_RegGetValueW
0x1400304e9  mov     esi, 80070000h
0x1400304ee  lea     r12, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400304f5  test    eax, eax
0x1400304f7  jz      short loc_140030552
0x1400304f9  jg      short loc_1400304FF
0x1400304fb  mov     ebx, eax
0x1400304fd  jmp     short loc_140030504
0x1400304ff  movzx   ebx, ax
0x140030502  or      ebx, esi
0x140030504  lea     rax, aWuNoAutoUpdate; "WU No Auto Update setting not found -- "...
0x14003050b  mov     r9d, 136h
0x140030511  mov     [rsp+60h+pvData], rax
0x140030516  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14003051d  lea     rax, aCsoftwareupdat_7; "CSoftwareUpdates::GetWindowsUpdateNoAut"...
0x140030524  mov     r8, r12
0x140030527  mov     ecx, r13d; unsigned __int8
0x14003052a  mov     [rsp+60h+pdwType], rax
0x14003052f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140030534  mov     ecx, 80000000h
0x140030539  lea     eax, [rbx+rcx]
0x14003053c  test    ecx, eax
0x14003053e  jnz     short loc_140030552
0x140030540  cmp     ebx, 80070002h
0x140030546  jz      short loc_140030552
0x140030548  mov     ebx, 80004005h
0x14003054d  jmp     loc_1400307BB
0x140030552  lea     rdx, ?s_szRegKey@CSoftwareUpdates@@0QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x140030559  mov     r13d, 2
0x14003055f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140030566  cmp     ebx, 80070002h
0x14003056c  jnz     loc_140030630
0x140030572  lea     r8, aWuoriginalnoti; "WuOriginalNotificationLevel"
0x140030579  call    cs:__imp_RegDeleteKeyValueW
0x14003057f  mov     ebx, eax
0x140030581  test    eax, 0FFFFFFFDh
0x140030586  jz      loc_14003076C
0x14003058c  test    eax, eax
0x14003058e  jle     short loc_140030595
0x140030590  movzx   ebx, ax
0x140030593  or      ebx, esi
0x140030595  lea     rax, aErr0lErr2l; "(err == 0L) || (err == 2L)"
0x14003059c  mov     dword ptr [rsp+60h+pvData], ebx; int
0x1400305a0  lea     rsi, aCbraex; "CBRAEx"
0x1400305a7  mov     [rsp+60h+pdwType], rax; unsigned __int16 *
0x1400305ac  lea     rdi, aCsoftwareupdat; "CSoftwareUpdates::OnDiskProtectionInsta"...
0x1400305b3  mov     r14d, 17Fh
0x1400305b9  mov     r9, rsi; unsigned __int16 *
0x1400305bc  mov     r8, rdi; unsigned __int16 *
0x1400305bf  mov     edx, r14d; unsigned int
0x1400305c2  mov     rcx, r12; unsigned __int16 *
0x1400305c5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400305ca  call    cs:__imp_IsDebuggerPresent
0x1400305d0  test    eax, eax
0x1400305d2  lea     rax, aErr0lErr2l; "(err == 0L) || (err == 2L)"
0x1400305d9  jz      short loc_140030608
0x1400305db  mov     dword ptr [rsp+60h+phkResult], ebx
0x1400305df  mov     r9d, r14d
0x1400305e2  mov     [rsp+60h+pcbData], rax
0x1400305e7  mov     [rsp+60h+pvData], rsi
0x1400305ec  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400305f3  mov     r8, r12
0x1400305f6  mov     [rsp+60h+pdwType], rdi
0x1400305fb  mov     ecx, r13d; unsigned __int8
0x1400305fe  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140030603  jmp     loc_1400307BB
0x140030608  mov     dword ptr [rsp+60h+pcbData], ebx
0x14003060c  mov     r8d, r14d
0x14003060f  mov     [rsp+60h+pvData], rax
0x140030614  mov     r9, rdi
0x140030617  mov     [rsp+60h+pdwType], rsi
0x14003061c  mov     rdx, r12
0x14003061f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140030626  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14003062b  jmp     loc_1400307BB
0x140030630  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x140030639  lea     rax, [rbp+hKey]
0x14003063d  mov     [rsp+60h+phkResult], rax; phkResult
0x140030642  xor     r9d, r9d; lpClass
0x140030645  mov     [rsp+60h+pcbData], 0; lpSecurityAttributes
0x14003064e  xor     r8d, r8d; Reserved
0x140030651  mov     dword ptr [rsp+60h+pvData], r13d; samDesired
0x140030656  mov     dword ptr [rsp+60h+pdwType], 0; dwOptions
0x14003065e  call    cs:__imp_RegCreateKeyExW
0x140030664  mov     ebx, eax
0x140030666  test    eax, eax
0x140030668  jz      short loc_1400306D4
0x14003066a  jle     short loc_140030671
0x14003066c  movzx   ebx, ax
0x14003066f  or      ebx, esi
0x140030671  lea     rsi, aCbraex; "CBRAEx"
0x140030678  mov     dword ptr [rsp+60h+pvData], ebx; int
0x14003067c  lea     rdi, aCsoftwareupdat; "CSoftwareUpdates::OnDiskProtectionInsta"...
0x140030683  mov     r9, rsi; unsigned __int16 *
0x140030686  lea     r14, aErr0l; "err == 0L"
0x14003068d  mov     r8, rdi; unsigned __int16 *
0x140030690  mov     edx, 184h; unsigned int
0x140030695  mov     [rsp+60h+pdwType], r14; unsigned __int16 *
0x14003069a  mov     rcx, r12; unsigned __int16 *
0x14003069d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400306a2  call    cs:__imp_IsDebuggerPresent
0x1400306a8  test    eax, eax
0x1400306aa  jz      short loc_1400306C0
0x1400306ac  mov     dword ptr [rsp+60h+phkResult], ebx
0x1400306b0  mov     r9d, 184h
0x1400306b6  mov     [rsp+60h+pcbData], r14
0x1400306bb  jmp     loc_1400305E7
0x1400306c0  mov     dword ptr [rsp+60h+pcbData], ebx
0x1400306c4  mov     r8d, 184h
0x1400306ca  mov     [rsp+60h+pvData], r14
0x1400306cf  jmp     loc_140030614
0x1400306d4  mov     rcx, [rbp+hKey]; hKey
0x1400306d8  lea     rax, [rbp+Data]
0x1400306dc  mov     r9d, 4; dwType
0x1400306e2  lea     rdx, aWuoriginalnoti; "WuOriginalNotificationLevel"
0x1400306e9  mov     dword ptr [rsp+60h+pvData], r9d; cbData
0x1400306ee  xor     r8d, r8d; Reserved
0x1400306f1  mov     [rsp+60h+pdwType], rax; lpData
0x1400306f6  call    cs:__imp_RegSetValueExW
0x1400306fc  mov     ebx, eax
0x1400306fe  test    eax, eax
0x140030700  jz      short loc_14003076C
0x140030702  jle     short loc_140030709
0x140030704  movzx   ebx, ax
0x140030707  or      ebx, esi
0x140030709  lea     rsi, aCbraex; "CBRAEx"
0x140030710  mov     dword ptr [rsp+60h+pvData], ebx; int
0x140030714  lea     rdi, aCsoftwareupdat; "CSoftwareUpdates::OnDiskProtectionInsta"...
0x14003071b  mov     r9, rsi; unsigned __int16 *
0x14003071e  lea     r14, aErr0l; "err == 0L"
0x140030725  mov     r8, rdi; unsigned __int16 *
0x140030728  mov     edx, 187h; unsigned int
0x14003072d  mov     [rsp+60h+pdwType], r14; unsigned __int16 *
0x140030732  mov     rcx, r12; unsigned __int16 *
0x140030735  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003073a  call    cs:__imp_IsDebuggerPresent
0x140030740  test    eax, eax
0x140030742  jz      short loc_140030758
0x140030744  mov     dword ptr [rsp+60h+phkResult], ebx
0x140030748  mov     r9d, 187h
0x14003074e  mov     [rsp+60h+pcbData], r14
0x140030753  jmp     loc_1400305E7
0x140030758  mov     dword ptr [rsp+60h+pcbData], ebx
0x14003075c  mov     r8d, 187h
0x140030762  mov     [rsp+60h+pvData], r14
0x140030767  jmp     loc_140030614
0x14003076c  cmp     [rbp+Data], 0
0x140030770  mov     rcx, rdi; this
0x140030773  jnz     short loc_140030790
0x140030775  lea     r8, [rbp+var_10]; int *
0x140030779  lea     rdx, [rbp+arg_10]; unsigned int *
0x14003077d  call    ?GetAutomaticMaintenanceSettings@CSoftwareUpdates@@AEAAJPEAKPEAH@Z; CSoftwareUpdates::GetAutomaticMaintenanceSettings(ulong *,int *)
0x140030782  mov     ebx, eax
0x140030784  test    eax, eax
0x140030786  js      short loc_1400307BB
0x140030788  mov     edx, r13d
0x14003078b  mov     rcx, rdi
0x14003078e  jmp     short loc_140030792
0x140030790  xor     edx, edx
0x140030792  mov     r8d, [rbp+arg_10]
0x140030796  xor     r9d, r9d
0x140030799  mov     dword ptr [rsp+60h+pvData], r14d
0x14003079e  mov     dword ptr [rsp+60h+pdwType], 0Fh
0x1400307a6  call    ?SetSettings@CSoftwareUpdates@@QEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0022@@KPEBGKW4__MIDL___MIDL_itf_wmssvc_0000_0000_0023@@@Z; CSoftwareUpdates::SetSettings(__MIDL___MIDL_itf_wmssvc_0000_0000_0022,ulong,ushort const *,ulong,__MIDL___MIDL_itf_wmssvc_0000_0000_0023)
0x1400307ab  mov     ebx, eax
0x1400307ad  test    eax, eax
0x1400307af  js      short loc_1400307BB
0x1400307b1  mov     edx, r14d; unsigned int
0x1400307b4  call    ?SetWindowsUpdateNoAutoUpdateSetting@CSoftwareUpdates@@AEAAJK@Z; CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(ulong)
0x1400307b9  mov     ebx, eax
0x1400307bb  mov     rcx, [rbp+hKey]; hKey
0x1400307bf  test    rcx, rcx
0x1400307c2  jz      short loc_1400307CA
0x1400307c4  call    cs:__imp_RegCloseKey
0x1400307ca  mov     eax, ebx
0x1400307cc  add     rsp, 60h
0x1400307d0  pop     r14
0x1400307d2  pop     r13
0x1400307d4  pop     r12
0x1400307d6  pop     rdi
0x1400307d7  pop     rsi
0x1400307d8  pop     rbx
0x1400307d9  pop     rbp
0x1400307da  retn
```
