# TiCoreRegisterWinlogonNotification

- ea: `0x140016210`
- end: `0x14001654d`
- name: `TiCoreRegisterWinlogonNotification`
- size: `829`
- prototype: `__int64 __fastcall(int, char *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009b2c`
- `0x14000c144`
- `0x14000d5c8`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x140006344`
- `0x14000695c`
- `0x14001575c`
- `0x140015a38`
- `0x140016210`
- `0x1400165dc`
- `0x140017658`
- `0x140019878`
- `0x14001afa4`
- `0x14001cd14`
- `0x14001f0fc`
- `0x140021594`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400164bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400164bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016337`

## string_xrefs

- `0x1400162d5`: `system32\`
- `0x1400162ef`: `Failed getting system32 directory`
- `0x14001637c`: `Failed appending winlogon.exe to path`
- `0x140016303`: `Winlogon: Registering for CreateSession notifications`
- `0x140016329`: `System\CurrentControlSet\Control\Winlogon\Notifications\Components\TrustedInstaller`
- `0x14001634e`: `Failed to open online TrustedInstaller's winlogon notification key.`
- `0x1400163b7`: `CreateSession`
- `0x1400163d0`: `Failed to register for Winlogon Notifications: Events: CreateSession`
- `0x1400163e8`: `Winlogon: Loading SysNotify DLL`
- `0x140016407`: `Failed to load SysNtfy DLL, continuing without Winlogon Notification support.`
- `0x140016500`: `TrustedInstaller`

## pseudocode

```c
__int64 __fastcall TiCoreRegisterWinlogonNotification(int a1, char *a2)
{
  unsigned int v4; // ebx
  char v5; // r14
  bool v6; // dl
  __int64 v7; // rdx
  int WindowsDirectory; // eax
  LSTATUS v9; // eax
  unsigned int v10; // r8d
  const wchar_t *v11; // r9
  const char *v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  HINSTANCE *v16; // rcx
  int started; // eax
  unsigned int v19[2]; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  int v22; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall *v23)(); // [rsp+68h] [rbp-51h]

  v4 = 0;
  memset_0(&v22, 0, 0x80u);
  v19[0] = 0;
  hKey = 0;
  v5 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v20,
    (struct MonitoredCritSec *)&stru_1400406F8,
    1);
  if ( ++vcRegisterWinlogonNotifications > 1 )
  {
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v20);
    goto LABEL_28;
  }
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v20);
  WdsSetupInProgress(v19, v6);
  if ( v19[0] )
  {
    LOBYTE(v7) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl'::`2'::impl,
      v7);
    CBSWdsLogLight(0x4000000, 0, 0, "Winlogon: Running under Setup");
  }
  *(_QWORD *)v19 = 0;
  WindowsDirectory = PathGetWindowsDirectory((LPWSTR *)v19, (__int64)L"system32\\");
  if ( WindowsDirectory >= 0 )
  {
    v14 = SczAllocConcatSz(v19, L"winlogon.exe");
    if ( v14 >= 0 )
    {
      if ( !(unsigned int)DoesFileExist(*(const WCHAR **)v19) )
      {
        CBSWdsLogLight(0x4000000, 0, 0, "Winlogon: No winlogon available, skipping registration for Notifications");
        goto LABEL_28;
      }
    }
    else
    {
      CBSWdsLogLight(0x4000000, (unsigned int)v14, 1, "Failed appending winlogon.exe to path");
    }
  }
  else
  {
    CBSWdsLogLight(0x4000000, (unsigned int)WindowsDirectory, 1, "Failed getting system32 directory");
  }
  CBSWdsLogLight(0x4000000, 0, 0, "Winlogon: Registering for CreateSession notifications");
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Winlogon\\Notifications\\Components\\TrustedInstaller",
         0,
         0x2001Fu,
         &hKey);
  v4 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v12 = "Failed to open online TrustedInstaller's winlogon notification key.";
    goto LABEL_11;
  }
  v15 = CbsRegSetStringValue(hKey, 0, v10, v11, L"CreateSession");
  v4 = v15;
  if ( v15 < 0 )
  {
    v12 = "Failed to register for Winlogon Notifications: Events: CreateSession";
LABEL_19:
    v13 = (unsigned int)v15;
    goto LABEL_12;
  }
  if ( !hLibModule )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "Winlogon: Loading SysNotify DLL");
    v15 = SysNtfyLoad(v16);
    v4 = v15;
    if ( v15 < 0 )
    {
      v12 = "Failed to load SysNtfy DLL, continuing without Winlogon Notification support.";
      goto LABEL_19;
    }
  }
  _InterlockedExchange(&dword_14004084C, a1 != 0);
  if ( !vpvWinlogonNotificationContext )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "Winlogon: Starting notify server ");
    memset_0(&v22, 0, 0x80u);
    v23 = TiCoreOnCreateSession;
    v22 = 1;
    if ( vpfnSysNotifyStartServer )
    {
      started = vpfnSysNotifyStartServer(
                  "TrustedInstaller",
                  0x80u,
                  (const struct _SN_NOTIFY_FUNCTIONS *)&v22,
                  0,
                  &vpvWinlogonNotificationContext);
      v4 = started;
      if ( started )
      {
        if ( started > 0 )
          v4 = (unsigned __int16)started | 0x80070000;
        CBSWdsLogLight(0x4000000, v4, 1, "Failed registering for Winlogon notifications");
        if ( (v4 & 0x80000000) != 0 )
        {
          v12 = "Failed registering Winlogon notification";
LABEL_11:
          v13 = v4;
LABEL_12:
          CBSWdsLogLight(0x4000000, v13, 1, v12);
          goto LABEL_28;
        }
        goto LABEL_27;
      }
    }
    else
    {
      vpvWinlogonNotificationContext = 0;
    }
    v4 = 0;
  }
LABEL_27:
  _InterlockedExchange(&dword_140040838, a1 != 0);
  v5 = 1;
LABEL_28:
  if ( a2 )
    *a2 = v5;
  if ( (v4 & 0x80000000) != 0 && hLibModule )
  {
    CBSWdsLogLight(0x4000000, v4, 1, "Failed registration for Winlogon notification, continuing without it.");
    TiCoreSysNtfyFinalize();
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140016210  mov     [rsp-8+arg_0], rbx
0x140016215  mov     [rsp-8+arg_10], rsi
0x14001621a  push    rbp
0x14001621b  push    rdi
0x14001621c  push    r13
0x14001621e  push    r14
0x140016220  push    r15
0x140016222  lea     rbp, [rsp-37h]
0x140016227  sub     rsp, 0F0h
0x14001622e  mov     rax, cs:__security_cookie
0x140016235  xor     rax, rsp
0x140016238  mov     [rbp+57h+var_30], rax
0x14001623c  mov     r15, rdx
0x14001623f  mov     esi, ecx
0x140016241  xor     edx, edx; Val
0x140016243  lea     rcx, [rbp+57h+var_B0]; void *
0x140016247  mov     r8d, 80h; Size
0x14001624d  xor     ebx, ebx
0x14001624f  call    memset_0
0x140016254  lea     edi, [rbx+1]
0x140016257  mov     [rsp+110h+var_E0], ebx
0x14001625b  mov     r8b, dil; bool
0x14001625e  mov     [rbp+57h+hKey], rbx
0x140016262  lea     rdx, stru_1400406F8; struct MonitoredCritSec *
0x140016269  xor     r14b, r14b
0x14001626c  lea     rcx, [rsp+110h+var_D8]; this
0x140016271  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x140016276  mov     eax, cs:?vcRegisterWinlogonNotifications@@3JA; long vcRegisterWinlogonNotifications
0x14001627c  lea     rcx, [rsp+110h+var_D8]; this
0x140016281  add     eax, edi
0x140016283  mov     r13d, 4000000h
0x140016289  mov     cs:?vcRegisterWinlogonNotifications@@3JA, eax; long vcRegisterWinlogonNotifications
0x14001628f  cmp     eax, edi
0x140016291  jle     short loc_14001629D
0x140016293  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140016298  jmp     loc_140016485
0x14001629d  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x1400162a2  lea     rcx, [rsp+110h+var_E0]; unsigned int *
0x1400162a7  call    ?WdsSetupInProgress@@YAJPEAK_N@Z; WdsSetupInProgress(ulong *,bool)
0x1400162ac  cmp     [rsp+110h+var_E0], ebx
0x1400162b0  jz      short loc_1400162D5
0x1400162b2  mov     dl, dil
0x1400162b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl(void)'::`2'::impl
0x1400162bc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400162c1  lea     r9, aWinlogonRunnin; "Winlogon: Running under Setup"
0x1400162c8  xor     r8d, r8d
0x1400162cb  xor     edx, edx
0x1400162cd  mov     ecx, r13d
0x1400162d0  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400162d5  lea     rdx, aSystem32; "system32\\"
0x1400162dc  mov     qword ptr [rsp+110h+var_E0], rbx
0x1400162e1  lea     rcx, [rsp+110h+var_E0]
0x1400162e6  call    PathGetWindowsDirectory
0x1400162eb  test    eax, eax
0x1400162ed  jns     short loc_140016367
0x1400162ef  lea     r9, aFailedGettingS_0; "Failed getting system32 directory"
0x1400162f6  mov     r8d, edi
0x1400162f9  mov     edx, eax
0x1400162fb  mov     ecx, r13d
0x1400162fe  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016303  lea     r9, aWinlogonRegist; "Winlogon: Registering for CreateSession"...
0x14001630a  xor     r8d, r8d
0x14001630d  xor     edx, edx
0x14001630f  mov     ecx, r13d
0x140016312  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016317  lea     rax, [rbp+57h+hKey]
0x14001631b  mov     r9d, 2001Fh; samDesired
0x140016321  xor     r8d, r8d; ulOptions
0x140016324  mov     [rsp+110h+phkResult], rax; phkResult
0x140016329  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Win"...
0x140016330  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016337  call    cs:__imp_RegOpenKeyExW
0x14001633d  mov     ebx, eax
0x14001633f  test    eax, eax
0x140016341  jz      short loc_1400163B3
0x140016343  jle     short loc_14001634E
0x140016345  movzx   ebx, ax
0x140016348  or      ebx, 80070000h
0x14001634e  lea     r9, aFailedToOpenOn; "Failed to open online TrustedInstaller'"...
0x140016355  mov     edx, ebx
0x140016357  mov     r8d, edi
0x14001635a  mov     ecx, r13d
0x14001635d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016362  jmp     loc_140016485
0x140016367  lea     rdx, aWinlogonExe; "winlogon.exe"
0x14001636e  lea     rcx, [rsp+110h+var_E0]
0x140016373  call    SczAllocConcatSz
0x140016378  test    eax, eax
0x14001637a  jns     short loc_140016388
0x14001637c  lea     r9, aFailedAppendin; "Failed appending winlogon.exe to path"
0x140016383  jmp     loc_1400162F6
0x140016388  mov     rcx, qword ptr [rsp+110h+var_E0]
0x14001638d  call    DoesFileExist
0x140016392  test    eax, eax
0x140016394  jnz     loc_140016303
0x14001639a  lea     r9, aWinlogonNoWinl; "Winlogon: No winlogon available, skippi"...
0x1400163a1  xor     r8d, r8d
0x1400163a4  xor     edx, edx
0x1400163a6  mov     ecx, r13d
0x1400163a9  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400163ae  jmp     loc_140016485
0x1400163b3  mov     rcx, [rbp+57h+hKey]; hKey
0x1400163b7  lea     rax, aCreatesession; "CreateSession"
0x1400163be  xor     edx, edx; wchar_t *
0x1400163c0  mov     [rsp+110h+phkResult], rax; wchar_t *
0x1400163c5  call    ?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z; CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)
0x1400163ca  mov     ebx, eax
0x1400163cc  test    eax, eax
0x1400163ce  jns     short loc_1400163DE
0x1400163d0  lea     r9, aFailedToRegist_1; "Failed to register for Winlogon Notific"...
0x1400163d7  mov     edx, eax
0x1400163d9  jmp     loc_140016357
0x1400163de  cmp     cs:hLibModule, 0
0x1400163e6  jnz     short loc_140016410
0x1400163e8  lea     r9, aWinlogonLoadin; "Winlogon: Loading SysNotify DLL"
0x1400163ef  xor     r8d, r8d
0x1400163f2  xor     edx, edx
0x1400163f4  mov     ecx, r13d
0x1400163f7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400163fc  call    ?SysNtfyLoad@@YAJPEAPEAUHINSTANCE__@@@Z; SysNtfyLoad(HINSTANCE__ * *)
0x140016401  mov     ebx, eax
0x140016403  test    eax, eax
0x140016405  jns     short loc_140016410
0x140016407  lea     r9, aFailedToLoadSy_0; "Failed to load SysNtfy DLL, continuing "...
0x14001640e  jmp     short loc_1400163D7
0x140016410  xor     edi, edi
0x140016412  test    esi, esi
0x140016414  setnz   dil
0x140016418  mov     eax, edi
0x14001641a  xchg    eax, cs:dword_14004084C
0x140016420  cmp     cs:?vpvWinlogonNotificationContext@@3PEAXEA, 0; void * vpvWinlogonNotificationContext
0x140016428  jnz     short loc_140016477
0x14001642a  lea     r9, aWinlogonStarti; "Winlogon: Starting notify server "
0x140016431  xor     r8d, r8d
0x140016434  xor     edx, edx
0x140016436  mov     ecx, r13d
0x140016439  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001643e  mov     ebx, 80h
0x140016443  lea     rcx, [rbp+57h+var_B0]; void *
0x140016447  mov     r8d, ebx; Size
0x14001644a  xor     edx, edx; Val
0x14001644c  call    memset_0
0x140016451  lea     rax, TiCoreOnCreateSession
0x140016458  mov     [rbp+57h+var_A8], rax
0x14001645c  lea     esi, [rbx-7Fh]
0x14001645f  mov     rax, cs:?vpfnSysNotifyStartServer@@3P6AJPEBDKPEBU_SN_NOTIFY_FUNCTIONS@@PEAXPEAPEAX@ZEA; long (*vpfnSysNotifyStartServer)(char const *,ulong,_SN_NOTIFY_FUNCTIONS const *,void *,void * *)
0x140016466  mov     [rbp+57h+var_B0], esi
0x140016469  test    rax, rax
0x14001646c  jnz     short loc_1400164ED
0x14001646e  mov     cs:?vpvWinlogonNotificationContext@@3PEAXEA, rax; void * vpvWinlogonNotificationContext
0x140016475  xor     ebx, ebx
0x140016477  xchg    edi, cs:dword_140040838
0x14001647d  mov     edi, 1
0x140016482  mov     r14b, dil
0x140016485  test    r15, r15
0x140016488  jz      short loc_14001648D
0x14001648a  mov     [r15], r14b
0x14001648d  test    ebx, ebx
0x14001648f  jns     short loc_1400164B4
0x140016491  cmp     cs:hLibModule, 0
0x140016499  jz      short loc_1400164B4
0x14001649b  lea     r9, aFailedRegistra; "Failed registration for Winlogon notifi"...
0x1400164a2  mov     r8d, edi
0x1400164a5  mov     edx, ebx
0x1400164a7  mov     ecx, r13d
0x1400164aa  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400164af  call    TiCoreSysNtfyFinalize
0x1400164b4  mov     rcx, [rbp+57h+hKey]; hKey
0x1400164b8  test    rcx, rcx
0x1400164bb  jz      short loc_1400164C3
0x1400164bd  call    cs:__imp_RegCloseKey
0x1400164c3  mov     eax, ebx
0x1400164c5  mov     rcx, [rbp+57h+var_30]
0x1400164c9  xor     rcx, rsp; StackCookie
0x1400164cc  call    __security_check_cookie
0x1400164d1  lea     r11, [rsp+110h+var_20]
0x1400164d9  mov     rbx, [r11+30h]
0x1400164dd  mov     rsi, [r11+40h]
0x1400164e1  mov     rsp, r11
0x1400164e4  pop     r15
0x1400164e6  pop     r14
0x1400164e8  pop     r13
0x1400164ea  pop     rdi
0x1400164eb  pop     rbp
0x1400164ec  retn
0x1400164ed  lea     rcx, ?vpvWinlogonNotificationContext@@3PEAXEA; void * vpvWinlogonNotificationContext
0x1400164f4  xor     r9d, r9d
0x1400164f7  mov     [rsp+110h+phkResult], rcx
0x1400164fc  lea     r8, [rbp+57h+var_B0]
0x140016500  lea     rcx, aTrustedinstall_2; "TrustedInstaller"
0x140016507  mov     edx, ebx
0x140016509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001650e  mov     ebx, eax
0x140016510  test    eax, eax
0x140016512  jz      loc_140016475
0x140016518  jle     short loc_140016523
0x14001651a  movzx   ebx, ax
0x14001651d  or      ebx, 80070000h
0x140016523  lea     r9, aFailedRegister; "Failed registering for Winlogon notific"...
0x14001652a  mov     r8d, esi
0x14001652d  mov     edx, ebx
0x14001652f  mov     ecx, r13d
0x140016532  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016537  test    ebx, ebx
0x140016539  jns     loc_140016477
0x14001653f  lea     r9, aFailedRegister_0; "Failed registering Winlogon notificatio"...
0x140016546  mov     edi, esi
0x140016548  jmp     loc_140016355
```
