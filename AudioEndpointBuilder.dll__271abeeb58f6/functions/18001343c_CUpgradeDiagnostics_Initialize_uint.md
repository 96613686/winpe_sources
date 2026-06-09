# CUpgradeDiagnostics::Initialize(uint)

- ea: `0x18001343c`
- end: `0x1800137d8`
- name: `?Initialize@CUpgradeDiagnostics@@QEAAJI@Z`
- size: `924`
- prototype: `__int64 __fastcall(PTP_TIMER *pv, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000802c`

## callees

- `0x180012e80`
- `0x18001343c`
- `0x18001707c`
- `0x18001deb0`
- `0x180021060`
- `0x180035170`
- `0x18005a928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800134aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800134aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001345b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001345b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800136de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800136de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013737`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013737`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001362e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001362e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800135a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800135a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800134f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800134f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013497`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800137b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013497`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800137b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013538`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800136b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013538`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800136b1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013779`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013779`

## string_xrefs

- `0x180013481`: `Already initialized\n`
- `0x1800134da`: `UpgradeProcessingComplete`
- `0x180013768`: `UpgradeProcessingComplete`
- `0x180013741`: `No previous os data available, no work to do, migration diagnostics complete.\n`
- `0x180013618`: `Upgrade defaults copied to final destination, migration data deleted\n`
- `0x1800134e1`: `System\CurrentControlSet\Services\AudioEndpointBuilder\Upgrade`
- `0x18001376f`: `System\CurrentControlSet\Services\AudioEndpointBuilder\Upgrade`
- `0x1800135c1`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x1800135fe`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18001364b`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x180013794`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18001365c`: `Failed to delete upgrade defaults (0x%08x)\n`
- `0x18001360f`: `Failed to copy upgrade defaults (0x%08x)\n`
- `0x1800135d2`: `Unable to create key to copy upgrade defaults (0x%08x)\n`
- `0x18001367e`: `Upgrade defaults unavailable for copy, already copied, or not an upgrade. (0x%08x)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CUpgradeDiagnostics::Initialize(PTP_TIMER *pv, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v5; // eax
  bool v6; // sf
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  bool v14; // sf
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v16; // rbx
  const unsigned __int16 *v17; // rcx
  int v18; // eax
  int pdwType; // [rsp+20h] [rbp-50h]
  int pdwTypea; // [rsp+20h] [rbp-50h]
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(pv + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 2));
  v24 = v4;
  hKey = 0;
  Data = 0;
  pcbData = 4;
  if ( *((_BYTE *)pv + 9) )
  {
    AudMigLibSetupLog(L"Already initialized\r\n");
    if ( hKey )
      RegCloseKey(hKey);
    if ( v4 )
      LeaveCriticalSection(v4);
    return 0;
  }
  *((_BYTE *)pv + 9) = 1;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\AudioEndpointBuilder\\Upgrade",
         L"UpgradeProcessingComplete",
         0x10u,
         0,
         &Data,
         &pcbData)
    || !Data )
  {
    AudMigLibSetupLog(L"Initializing upgrade diagnostics for first run\r\n");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Upgrade\\Audio\\Defaults", 0, 0x20019u, &hKey);
    v6 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v6 = v5 < 0;
    }
    if ( v6 )
    {
      AudMigLibSetupLog(
        L"Upgrade defaults unavailable for copy, already copied, or not an upgrade. (0x%08x)\r\n",
        (unsigned int)v5);
    }
    else
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v7 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\Audio\\PreviousOs\\Defaults",
             0,
             0,
             0,
             0x20006u,
             0,
             &phkResult,
             0);
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
      {
        v9 = AudMigLibCopyRegistrySettings(hKey, phkResult, 1);
        v10 = v9;
        if ( v9 >= 0 )
        {
          AudMigLibSetupLog(L"Upgrade defaults copied to final destination, migration data deleted\r\n");
          v11 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Upgrade\\Audio\\Defaults");
          v12 = v11;
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          if ( (v12 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5AB,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
              (const char *)v12,
              pdwType);
            AudMigLibSetupLog(L"Failed to delete upgrade defaults (0x%08x)\r\n", v12);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5A7,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
            (const char *)(unsigned int)v9,
            pdwType);
          AudMigLibSetupLog(L"Failed to copy upgrade defaults (0x%08x)\r\n", v10);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5A4,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
          (const char *)v8,
          pdwType);
        AudMigLibSetupLog(L"Unable to create key to copy upgrade defaults (0x%08x)\r\n", v8);
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v13 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\Audio\\PreviousOs",
            0,
            0x20019u,
            &hKey);
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = v13 < 0;
    }
    if ( !v14 )
    {
      AudMigLibSetupLog(L"Enabling migration diagnostics\r\n");
      ThreadpoolTimer = CreateThreadpoolTimer(CUpgradeDiagnostics::TimerCallback, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        pv,
        ThreadpoolTimer);
      v16 = -18000000000LL;
      if ( a2 )
        v16 = -300000000;
      v23 = v16;
      v17 = L"Standard diagnostics timer enabled\r\n";
      if ( !a2 )
        v17 = L"No audio interfaces in the system, large diagnostics timer enabled\r\n";
      AudMigLibSetupLog(v17);
      phkResult = (HKEY)__PAIR64__(HIDWORD(v23), v16);
      SetThreadpoolTimer(*pv, (PFILETIME)&phkResult, 0, 0);
      goto LABEL_37;
    }
    AudMigLibSetupLog(
      L"No previous os data available, no work to do, migration diagnostics complete.\r\n",
      (unsigned int)v13);
    Data = 1;
    v18 = RegSetKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\AudioEndpointBuilder\\Upgrade",
            L"UpgradeProcessingComplete",
            4u,
            &Data,
            4u);
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
        (const char *)(unsigned int)v18,
        pdwTypea);
  }
  *((_BYTE *)pv + 8) = 1;
LABEL_37:
  if ( hKey )
    RegCloseKey(hKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x18001343c  mov     [rsp-28h+arg_8], rbx
0x180013441  push    rbp
0x180013442  push    rsi
0x180013443  push    rdi
0x180013444  push    r13
0x180013446  push    r15
0x180013448  mov     rbp, rsp
0x18001344b  sub     rsp, 70h
0x18001344f  mov     esi, edx
0x180013451  mov     rdi, rcx
0x180013454  lea     rbx, [rcx+10h]
0x180013458  mov     rcx, rbx; lpCriticalSection
0x18001345b  call    cs:__imp_EnterCriticalSection
0x180013461  mov     [rbp+var_10], rbx
0x180013465  mov     [rbp+hKey], 0
0x18001346d  mov     [rbp+Data], 0
0x180013474  mov     [rbp+arg_10], 4
0x18001347b  cmp     byte ptr [rdi+9], 0
0x18001347f  jz      short loc_1800134B5
0x180013481  lea     rcx, aAlreadyInitial; "Already initialized\r\n"
0x180013488  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18001348d  nop
0x18001348e  mov     rcx, [rbp+hKey]; hKey
0x180013492  test    rcx, rcx
0x180013495  jz      short loc_18001349E
0x180013497  call    cs:__imp_RegCloseKey
0x18001349d  nop
0x18001349e  test    rbx, rbx
0x1800134a1  jz      loc_1800137C2
0x1800134a7  mov     rcx, rbx; lpCriticalSection
0x1800134aa  call    cs:__imp_LeaveCriticalSection
0x1800134b0  jmp     loc_1800137C2
0x1800134b5  mov     byte ptr [rdi+9], 1
0x1800134b9  lea     rax, [rbp+arg_10]
0x1800134bd  mov     [rsp+70h+pcbData], rax; pcbData
0x1800134c2  lea     rax, [rbp+Data]
0x1800134c6  mov     [rsp+70h+pvData], rax; pvData
0x1800134cb  mov     [rsp+70h+pdwType], 0; pdwType
0x1800134d4  mov     r9d, 10h; dwFlags
0x1800134da  lea     r8, ValueName; "UpgradeProcessingComplete"
0x1800134e1  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Au"...
0x1800134e8  mov     r13, 0FFFFFFFF80000002h
0x1800134ef  mov     rcx, r13; hkey
0x1800134f2  call    cs:__imp_RegGetValueW
0x1800134f8  test    eax, eax
0x1800134fa  jnz     short loc_180013505
0x1800134fc  cmp     [rbp+Data], eax
0x1800134ff  ja      loc_1800137A5
0x180013505  lea     rcx, aInitializingUp; "Initializing upgrade diagnostics for fi"...
0x18001350c  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180013511  xor     edx, edx
0x180013513  lea     rcx, [rbp+hKey]
0x180013517  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001351c  lea     rax, [rbp+hKey]
0x180013520  mov     [rsp+70h+pdwType], rax; phkResult
0x180013525  mov     r9d, 20019h; samDesired
0x18001352b  xor     r8d, r8d; ulOptions
0x18001352e  lea     rdx, aSystemSetupUpg; "System\\Setup\\Upgrade\\Audio\\Defaults"
0x180013535  mov     rcx, r13; hKey
0x180013538  call    cs:__imp_RegOpenKeyExW
0x18001353e  mov     r15d, 80070000h
0x180013544  test    eax, eax
0x180013546  jle     short loc_180013550
0x180013548  movzx   eax, ax
0x18001354b  or      eax, r15d
0x18001354e  test    eax, eax
0x180013550  js      loc_18001367C
0x180013556  mov     [rbp+var_20], 0
0x18001355e  xor     edx, edx
0x180013560  lea     rcx, [rbp+var_20]
0x180013564  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013569  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180013572  lea     rax, [rbp+var_20]
0x180013576  mov     [rsp+70h+phkResult], rax; phkResult
0x18001357b  mov     [rsp+70h+pcbData], 0; lpSecurityAttributes
0x180013584  mov     dword ptr [rsp+70h+pvData], 20006h; samDesired
0x18001358c  mov     dword ptr [rsp+70h+pdwType], 0; int
0x180013594  xor     r9d, r9d; lpClass
0x180013597  xor     r8d, r8d; Reserved
0x18001359a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800135a1  mov     rcx, r13; hKey
0x1800135a4  call    cs:__imp_RegCreateKeyExW
0x1800135aa  mov     ebx, eax
0x1800135ac  test    eax, eax
0x1800135ae  jle     short loc_1800135B6
0x1800135b0  movzx   ebx, ax
0x1800135b3  or      ebx, r15d
0x1800135b6  mov     rcx, [rbp+28h]; this
0x1800135ba  test    ebx, ebx
0x1800135bc  jns     short loc_1800135DE
0x1800135be  mov     r9d, ebx; char *
0x1800135c1  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x1800135c8  mov     edx, 5A4h; void *
0x1800135cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800135d2  lea     rcx, aUnableToCreate; "Unable to create key to copy upgrade de"...
0x1800135d9  jmp     loc_180013663
0x1800135de  mov     r8d, 1; int
0x1800135e4  mov     rdx, [rbp+var_20]; HKEY
0x1800135e8  mov     rcx, [rbp+hKey]; HKEY
0x1800135ec  call    ?AudMigLibCopyRegistrySettings@@YAJPEAUHKEY__@@0H@Z; AudMigLibCopyRegistrySettings(HKEY__ *,HKEY__ *,int)
0x1800135f1  mov     ebx, eax
0x1800135f3  mov     rcx, [rbp+28h]; this
0x1800135f7  test    eax, eax
0x1800135f9  jns     short loc_180013618
0x1800135fb  mov     r9d, eax; char *
0x1800135fe  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180013605  mov     edx, 5A7h; void *
0x18001360a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001360f  lea     rcx, aFailedToCopyUp; "Failed to copy upgrade defaults (0x%08x"...
0x180013616  jmp     short loc_180013663
0x180013618  lea     rcx, aUpgradeDefault; "Upgrade defaults copied to final destin"...
0x18001361f  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180013624  lea     rdx, aSystemSetupUpg; "System\\Setup\\Upgrade\\Audio\\Defaults"
0x18001362b  mov     rcx, r13; hKey
0x18001362e  call    cs:__imp_RegDeleteTreeW
0x180013634  mov     ebx, eax
0x180013636  test    eax, eax
0x180013638  jle     short loc_180013640
0x18001363a  movzx   ebx, ax
0x18001363d  or      ebx, r15d
0x180013640  mov     rcx, [rbp+28h]; this
0x180013644  test    ebx, ebx
0x180013646  jns     short loc_18001366B
0x180013648  mov     r9d, ebx; char *
0x18001364b  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180013652  mov     edx, 5ABh; void *
0x180013657  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001365c  lea     rcx, aFailedToDelete; "Failed to delete upgrade defaults (0x%0"...
0x180013663  mov     edx, ebx
0x180013665  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18001366a  nop
0x18001366b  mov     rcx, [rbp+var_20]; hKey
0x18001366f  test    rcx, rcx
0x180013672  jz      short loc_18001368A
0x180013674  call    cs:__imp_RegCloseKey
0x18001367a  jmp     short loc_18001368A
0x18001367c  mov     edx, eax
0x18001367e  lea     rcx, aUpgradeDefault_0; "Upgrade defaults unavailable for copy, "...
0x180013685  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18001368a  xor     edx, edx
0x18001368c  lea     rcx, [rbp+hKey]
0x180013690  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013695  lea     rax, [rbp+hKey]
0x180013699  mov     [rsp+70h+pdwType], rax; phkResult
0x18001369e  mov     r9d, 20019h; samDesired
0x1800136a4  xor     r8d, r8d; ulOptions
0x1800136a7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800136ae  mov     rcx, r13; hKey
0x1800136b1  call    cs:__imp_RegOpenKeyExW
0x1800136b7  test    eax, eax
0x1800136b9  jle     short loc_1800136C3
0x1800136bb  movzx   eax, ax
0x1800136be  or      eax, r15d
0x1800136c1  test    eax, eax
0x1800136c3  js      short loc_18001373F
0x1800136c5  lea     rcx, aEnablingMigrat; "Enabling migration diagnostics\r\n"
0x1800136cc  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x1800136d1  xor     r8d, r8d; pcbe
0x1800136d4  mov     rdx, rdi; pv
0x1800136d7  lea     rcx, ?TimerCallback@CUpgradeDiagnostics@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800136de  call    cs:__imp_CreateThreadpoolTimer
0x1800136e4  mov     rdx, rax
0x1800136e7  mov     rcx, rdi
0x1800136ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800136ef  mov     rbx, 0FFFFFFFBCF1DCC00h
0x1800136f9  mov     rax, 0FFFFFFFFEE1E5D00h
0x180013700  test    esi, esi
0x180013702  cmovnz  rbx, rax
0x180013706  mov     [rbp+var_18], rbx
0x18001370a  lea     rax, aNoAudioInterfa; "No audio interfaces in the system, larg"...
0x180013711  lea     rcx, aStandardDiagno; "Standard diagnostics timer enabled\r\n"
0x180013718  cmovz   rcx, rax; unsigned __int16 *
0x18001371c  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180013721  mov     eax, dword ptr [rbp+var_18+4]
0x180013724  mov     dword ptr [rbp+var_20+4], eax
0x180013727  mov     dword ptr [rbp+var_20], ebx
0x18001372a  xor     r9d, r9d; msWindowLength
0x18001372d  xor     r8d, r8d; msPeriod
0x180013730  lea     rdx, [rbp+var_20]; pftDueTime
0x180013734  mov     rcx, [rdi]; pti
0x180013737  call    cs:__imp_SetThreadpoolTimer
0x18001373d  jmp     short loc_1800137A9
0x18001373f  mov     edx, eax
0x180013741  lea     rcx, aNoPreviousOsDa; "No previous os data available, no work "...
0x180013748  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18001374d  mov     [rbp+Data], 1
0x180013754  mov     r9d, 4; dwType
0x18001375a  mov     dword ptr [rsp+70h+pvData], r9d; cbData
0x18001375f  lea     rax, [rbp+Data]
0x180013763  mov     [rsp+70h+pdwType], rax; int
0x180013768  lea     r8, ValueName; "UpgradeProcessingComplete"
0x18001376f  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Au"...
0x180013776  mov     rcx, r13; hKey
0x180013779  call    cs:__imp_RegSetKeyValueW
0x18001377f  test    eax, eax
0x180013781  jle     short loc_180013789
0x180013783  movzx   eax, ax
0x180013786  or      eax, r15d
0x180013789  mov     rcx, [rbp+28h]; this
0x18001378d  test    eax, eax
0x18001378f  jns     short loc_1800137A5
0x180013791  mov     r9d, eax; char *
0x180013794  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18001379b  mov     edx, 5FFh; void *
0x1800137a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800137a5  mov     byte ptr [rdi+8], 1
0x1800137a9  mov     rcx, [rbp+hKey]; hKey
0x1800137ad  test    rcx, rcx
0x1800137b0  jz      short loc_1800137B9
0x1800137b2  call    cs:__imp_RegCloseKey
0x1800137b8  nop
0x1800137b9  lea     rcx, [rbp+var_10]
0x1800137bd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800137c2  xor     eax, eax
0x1800137c4  mov     rbx, [rsp+70h+arg_8]
0x1800137cc  add     rsp, 70h
0x1800137d0  pop     r15
0x1800137d2  pop     r13
0x1800137d4  pop     rdi
0x1800137d5  pop     rsi
0x1800137d6  pop     rbp
0x1800137d7  retn
```
