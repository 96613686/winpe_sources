# FveBackupMonitor::ShowPromptForCurrentUser(CNgscbToken const *,ulong)

- ea: `0x1800714cc`
- end: `0x1800716ee`
- name: `?ShowPromptForCurrentUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@K@Z`
- size: `546`
- prototype: `__int64 __fastcall(const struct CNgscbToken *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003b560`

## callees

- `0x1800016a4`
- `0x180001fe8`
- `0x180009f60`
- `0x180021d18`
- `0x180025ed4`
- `0x180026190`
- `0x18002f28c`
- `0x1800714cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800715a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800715a5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800715eb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800715eb`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::ShowPromptForCurrentUser(HANDLE *a1, unsigned int a2)
{
  LSTATUS ValueW; // esi
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  LSTATUS v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v13; // [rsp+48h] [rbp-28h] BYREF
  int v14; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  PSRWLOCK v16[3]; // [rsp+58h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+28h] BYREF
  char v18; // [rsp+A0h] [rbp+30h] BYREF
  int pvData; // [rsp+A8h] [rbp+38h] BYREF

  Data = a2;
  ValueW = 0;
  v18 = 0;
  pvData = 0;
  pcbData = 4;
  if ( a2 < 2 )
  {
    if ( !a1 )
      goto LABEL_11;
    v6 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)&v18, a1);
    v3 = v6;
    if ( !v6 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_929186be452536e5252128d48ffaedab_Traceguids, v6);
    if ( (v3 & 0x80000000) == 0 )
    {
LABEL_11:
      ValueW = RegGetValueW(
                 HKEY_CURRENT_USER,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\KeyBackupMonitor",
                 L"ShowRecoveryBackupPrompt",
                 0x10u,
                 0,
                 &pvData,
                 &pcbData);
      if ( ValueW || pvData != Data )
      {
        v7 = RegSetKeyValueW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\KeyBackupMonitor",
               L"ShowRecoveryBackupPrompt",
               4u,
               &Data,
               4u);
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
        if ( v3 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v5 = 27;
            goto LABEL_20;
          }
        }
      }
      else
      {
        v3 = 0;
      }
    }
  }
  else
  {
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v5 = 25;
LABEL_20:
      WPP_SF_d(v4[2], v5, WPP_929186be452536e5252128d48ffaedab_Traceguids, v3);
    }
  }
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v16,
    &g_hBackupMonitorProvider,
    &g_BackupMonitorProviderInitLock,
    &g_BackupMonitorProviderRefCount);
  if ( !ValueW && (unsigned int)dword_18009A510 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A510, 0x400000000000LL) )
  {
    v13 = Data;
    v14 = pvData;
    v15 = 0x1000000;
    v12 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_18009A510,
      (int)&unk_18008E980,
      v8,
      v9,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v15);
  }
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v16);
  CScopedImpersonation::Revert((CScopedImpersonation *)&v18);
  return v3;
}

```

## disassembly

```asm
0x1800714cc  mov     [rsp-18h+arg_0], rbx
0x1800714d1  mov     [rsp-18h+Data], edx
0x1800714d5  push    rbp
0x1800714d6  push    rsi
0x1800714d7  push    rdi
0x1800714d8  mov     rbp, rsp
0x1800714db  sub     rsp, 70h
0x1800714df  xor     esi, esi
0x1800714e1  mov     [rbp+arg_10], 0
0x1800714e5  mov     [rbp+arg_18], esi
0x1800714e8  mov     [rbp+var_30], 4
0x1800714ef  cmp     edx, 2
0x1800714f2  jb      short loc_180071520
0x1800714f4  lea     ebx, [rsi+57h]
0x1800714f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800714fe  lea     rdi, WPP_GLOBAL_Control
0x180071505  cmp     rcx, rdi
0x180071508  jz      loc_180071634
0x18007150e  test    byte ptr [rcx+1Ch], 40h
0x180071512  jz      loc_180071634
0x180071518  lea     edx, [rsi+19h]
0x18007151b  jmp     loc_180071621
0x180071520  lea     rdi, WPP_GLOBAL_Control
0x180071527  test    rcx, rcx
0x18007152a  jz      short loc_180071570
0x18007152c  mov     rdx, rcx; struct CNgscbToken *
0x18007152f  lea     rcx, [rbp+arg_10]; this
0x180071533  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x180071538  mov     ebx, eax
0x18007153a  test    eax, eax
0x18007153c  jz      short loc_180071570
0x18007153e  mov     rcx, cs:WPP_GLOBAL_Control
0x180071545  cmp     rcx, rdi
0x180071548  jz      short loc_180071568
0x18007154a  test    byte ptr [rcx+1Ch], 40h
0x18007154e  jz      short loc_180071568
0x180071550  mov     rcx, [rcx+10h]
0x180071554  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18007155b  mov     edx, 1Ah
0x180071560  mov     r9d, eax
0x180071563  call    WPP_SF_d
0x180071568  test    ebx, ebx
0x18007156a  js      loc_180071634
0x180071570  lea     rax, [rbp+var_30]
0x180071574  mov     rbx, 0FFFFFFFF80000001h
0x18007157b  mov     [rsp+70h+pcbData], rax; pcbData
0x180071580  lea     r8, aShowrecoveryba; "ShowRecoveryBackupPrompt"
0x180071587  lea     rax, [rbp+arg_18]
0x18007158b  mov     r9d, 10h; dwFlags
0x180071591  mov     [rsp+70h+pvData], rax; pvData
0x180071596  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007159d  mov     rcx, rbx; hkey
0x1800715a0  mov     [rsp+70h+pdwType], rsi; pdwType
0x1800715a5  call    cs:__imp_RegGetValueW
0x1800715ac  nop     dword ptr [rax+rax+00h]
0x1800715b1  mov     esi, eax
0x1800715b3  test    eax, eax
0x1800715b5  jnz     short loc_1800715C3
0x1800715b7  mov     ecx, [rbp+Data]
0x1800715ba  cmp     [rbp+arg_18], ecx
0x1800715bd  jnz     short loc_1800715C3
0x1800715bf  xor     ebx, ebx
0x1800715c1  jmp     short loc_180071634
0x1800715c3  lea     rax, [rbp+Data]
0x1800715c7  mov     dword ptr [rsp+70h+pvData], 4; cbData
0x1800715cf  mov     r9d, 4; dwType
0x1800715d5  mov     [rsp+70h+pdwType], rax; lpData
0x1800715da  lea     r8, aShowrecoveryba; "ShowRecoveryBackupPrompt"
0x1800715e1  mov     rcx, rbx; hKey
0x1800715e4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800715eb  call    cs:__imp_RegSetKeyValueW
0x1800715f2  nop     dword ptr [rax+rax+00h]
0x1800715f7  mov     ebx, eax
0x1800715f9  test    eax, eax
0x1800715fb  jle     short loc_180071606
0x1800715fd  movzx   ebx, ax
0x180071600  or      ebx, 80070000h
0x180071606  test    ebx, ebx
0x180071608  jz      short loc_180071634
0x18007160a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071611  cmp     rcx, rdi
0x180071614  jz      short loc_180071634
0x180071616  test    byte ptr [rcx+1Ch], 40h
0x18007161a  jz      short loc_180071634
0x18007161c  mov     edx, 1Bh
0x180071621  mov     rcx, [rcx+10h]
0x180071625  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18007162c  mov     r9d, ebx
0x18007162f  call    WPP_SF_d
0x180071634  lea     r9, ?g_BackupMonitorProviderRefCount@@3JC; volatile int *
0x18007163b  lea     r8, ?g_BackupMonitorProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180071642  lea     rdx, g_hBackupMonitorProvider; struct _tlgProvider_t **
0x180071649  lea     rcx, [rbp+var_18]; this
0x18007164d  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x180071652  test    esi, esi
0x180071654  jnz     short loc_1800716C9
0x180071656  mov     eax, cs:dword_18009A510
0x18007165c  cmp     eax, 5
0x18007165f  jbe     short loc_1800716C9
0x180071661  mov     rdx, 400000000000h
0x18007166b  lea     rcx, dword_18009A510
0x180071672  call    _tlgKeywordOn
0x180071677  test    al, al
0x180071679  jz      short loc_1800716C9
0x18007167b  mov     eax, [rbp+Data]
0x18007167e  lea     rdx, unk_18008E980
0x180071685  mov     [rbp+var_28], eax
0x180071688  lea     rcx, dword_18009A510
0x18007168f  mov     eax, [rbp+arg_18]
0x180071692  mov     [rbp+var_24], eax
0x180071695  lea     rax, [rbp+var_20]
0x180071699  mov     [rsp+70h+var_38], rax
0x18007169e  lea     rax, [rbp+var_2C]
0x1800716a2  mov     [rsp+70h+pcbData], rax
0x1800716a7  lea     rax, [rbp+var_28]
0x1800716ab  mov     [rsp+70h+pvData], rax
0x1800716b0  lea     rax, [rbp+var_24]
0x1800716b4  mov     [rsp+70h+pdwType], rax
0x1800716b9  mov     [rbp+var_20], 1000000h
0x1800716c1  mov     [rbp+var_2C], ebx
0x1800716c4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800716c9  lea     rcx, [rbp+var_18]; this
0x1800716cd  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800716d2  lea     rcx, [rbp+arg_10]; this
0x1800716d6  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x1800716db  mov     eax, ebx
0x1800716dd  mov     rbx, [rsp+70h+arg_0]
0x1800716e5  add     rsp, 70h
0x1800716e9  pop     rdi
0x1800716ea  pop     rsi
0x1800716eb  pop     rbp
0x1800716ec  retn
```
