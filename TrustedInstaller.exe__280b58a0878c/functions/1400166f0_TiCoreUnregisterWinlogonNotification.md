# TiCoreUnregisterWinlogonNotification

- ea: `0x1400166f0`
- end: `0x140016813`
- name: `TiCoreUnregisterWinlogonNotification`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c3b4`
- `0x14000d5c8`
- `0x14001681c`

## callees

- `0x140006344`
- `0x14000695c`
- `0x140015a38`
- `0x1400166f0`
- `0x140017658`
- `0x14001afa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400167b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400167b0`

## string_xrefs

- `0x1400167db`: `System\CurrentControlSet\Control\Winlogon\Notifications\Components\TrustedInstaller`
- `0x14001675e`: `Winlogon: Simplifying Winlogon CreateSession notifications`
- `0x1400167ba`: `Winlogon: Deregistering for CreateSession notifications`

## pseudocode

```c
__int64 __fastcall TiCoreUnregisterWinlogonNotification(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned __int8 a6)
{
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  const wchar_t *v12; // r9
  int v13; // eax
  _BYTE v15[72]; // [rsp+30h] [rbp-48h] BYREF

  v9 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v15,
    (struct MonitoredCritSec *)&stru_1400406F8,
    1);
  if ( !a1 )
  {
    if ( !--vcRegisterWinlogonNotifications )
      goto LABEL_6;
LABEL_4:
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v15);
    return v9;
  }
  if ( !vcRegisterWinlogonNotifications )
    goto LABEL_4;
  vcRegisterWinlogonNotifications = 0;
LABEL_6:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v15);
  if ( hLibModule )
  {
    CBSWdsLogLight(0x4000000u, 0, 0, "Winlogon: Simplifying Winlogon CreateSession notifications");
    dword_140040858 = a2;
    LOBYTE(v10) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl'::`2'::impl,
      v10);
    _InterlockedExchange(&dword_140040844, a5);
    _InterlockedExchange(&dword_140040848, a6);
    _InterlockedExchange(&dword_14004084C, 0);
    SetEvent(hObject);
    if ( a3 )
    {
      CBSWdsLogLight(0x4000000u, 0, 0, "Winlogon: Deregistering for CreateSession notifications");
      v13 = CbsRegSetStringValue(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Winlogon\\Notifications\\Components\\TrustedInstaller",
              v11,
              v12,
              (BYTE *)&qword_1400353C0);
      v9 = v13;
      if ( v13 < 0 )
        CBSWdsLogLight(0x4000000u, (unsigned int)v13, (size_t *)1, "Failed static unregister for winlogon notification");
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1400166f0  push    rbx
0x1400166f2  push    rbp
0x1400166f3  push    rsi
0x1400166f4  push    rdi
0x1400166f5  sub     rsp, 58h
0x1400166f9  mov     esi, r8d
0x1400166fc  mov     ebp, edx
0x1400166fe  mov     ebx, ecx
0x140016700  lea     rdx, stru_1400406F8; struct MonitoredCritSec *
0x140016707  mov     r8b, 1; bool
0x14001670a  lea     rcx, [rsp+78h+var_48]; this
0x14001670f  xor     edi, edi
0x140016711  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x140016716  test    ebx, ebx
0x140016718  jz      short loc_140016739
0x14001671a  cmp     cs:?vcRegisterWinlogonNotifications@@3JA, edi; long vcRegisterWinlogonNotifications
0x140016720  jz      short loc_14001672A
0x140016722  mov     cs:?vcRegisterWinlogonNotifications@@3JA, edi; long vcRegisterWinlogonNotifications
0x140016728  jmp     short loc_140016742
0x14001672a  lea     rcx, [rsp+78h+var_48]; this
0x14001672f  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140016734  jmp     loc_140016808
0x140016739  sub     cs:?vcRegisterWinlogonNotifications@@3JA, 1; long vcRegisterWinlogonNotifications
0x140016740  jnz     short loc_14001672A
0x140016742  lea     rcx, [rsp+78h+var_48]; this
0x140016747  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14001674c  cmp     cs:hLibModule, rdi
0x140016753  jz      loc_140016808
0x140016759  mov     ebx, 4000000h
0x14001675e  lea     r9, aWinlogonSimpli; "Winlogon: Simplifying Winlogon CreateSe"...
0x140016765  mov     ecx, ebx
0x140016767  xor     r8d, r8d
0x14001676a  xor     edx, edx
0x14001676c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016771  mov     cs:dword_140040858, ebp
0x140016777  mov     dl, 1
0x140016779  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl(void)'::`2'::impl
0x140016780  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140016785  movzx   eax, [rsp+78h+arg_20]
0x14001678d  xchg    eax, cs:dword_140040844
0x140016793  movzx   ecx, [rsp+78h+arg_28]
0x14001679b  xor     eax, eax
0x14001679d  xchg    ecx, cs:dword_140040848
0x1400167a3  xchg    eax, cs:dword_14004084C
0x1400167a9  mov     rcx, cs:hObject; hEvent
0x1400167b0  call    cs:__imp_SetEvent
0x1400167b6  test    esi, esi
0x1400167b8  jz      short loc_140016808
0x1400167ba  lea     r9, aWinlogonDeregi; "Winlogon: Deregistering for CreateSessi"...
0x1400167c1  xor     r8d, r8d
0x1400167c4  xor     edx, edx
0x1400167c6  mov     ecx, ebx
0x1400167c8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400167cd  lea     rax, qword_1400353C0
0x1400167d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400167db  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Win"...
0x1400167e2  mov     [rsp+78h+var_58], rax; wchar_t *
0x1400167e7  call    ?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z; CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)
0x1400167ec  mov     edi, eax
0x1400167ee  test    eax, eax
0x1400167f0  jns     short loc_140016808
0x1400167f2  lea     r9, aFailedStaticUn; "Failed static unregister for winlogon n"...
0x1400167f9  mov     r8d, 1
0x1400167ff  mov     edx, eax
0x140016801  mov     ecx, ebx
0x140016803  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016808  mov     eax, edi
0x14001680a  add     rsp, 58h
0x14001680e  pop     rdi
0x14001680f  pop     rsi
0x140016810  pop     rbp
0x140016811  pop     rbx
0x140016812  retn
```
