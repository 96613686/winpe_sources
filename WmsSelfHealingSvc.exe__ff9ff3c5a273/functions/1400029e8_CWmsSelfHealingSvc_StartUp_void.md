# CWmsSelfHealingSvc::StartUp(void)

- ea: `0x1400029e8`
- end: `0x140002c02`
- name: `?StartUp@CWmsSelfHealingSvc@@AEAAJXZ`
- size: `538`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140002c94`

## callees

- `0x140001cb8`
- `0x1400024d4`
- `0x140002838`
- `0x1400029e8`
- `0x14000300c`
- `0x1400036a0`
- `0x140006e24`
- `0x140009344`
- `0x140009470`
- `0x140009f88`
- `0x14000a0c8`
- `0x14000a208`
- `0x14000a340`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140002ad1`
- `KERNEL32!WaitForSingleObject` at `0x140002ad1`
- `KERNEL32!SetEvent` at `0x140002bc6`
- `KERNEL32!SetEvent` at `0x140002bc6`
- `KERNEL32!CloseHandle` at `0x140002bdd`
- `KERNEL32!CloseHandle` at `0x140002bdd`

## string_xrefs

- `0x140002aa0`: `CWmsSelfHealingSvc::StartUp - VCF is currently uninstalling, not running self-healing.\n`
- `0x140002a35`: `Global\WmsSelfHealingSvcReadyEvent`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::StartUp(void **this)
{
  char *v1; // rsi
  int v3; // r15d
  int v4; // edi
  unsigned int v5; // ecx
  int *v6; // rdx
  int WmsNamedEvent; // ebx
  int *v8; // rdx
  int *v9; // rdx
  unsigned int v10; // ecx
  int v11; // eax
  CWmsSelfHealingSvc *v12; // rcx
  int v13; // r14d
  __int64 v14; // rdx
  PlatformUtils *v15; // rcx
  __int64 v16; // rcx
  CWmsSelfHealingSvc *v17; // rcx
  int started; // eax
  unsigned int v19; // edx
  unsigned int v20; // edx
  const unsigned __int16 *v21; // rcx
  unsigned int v22; // r8d
  int v24; // [rsp+20h] [rbp-20h] BYREF
  int v25; // [rsp+24h] [rbp-1Ch] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-18h] BYREF
  HANDLE *v27; // [rsp+30h] [rbp-10h]
  int v28; // [rsp+80h] [rbp+40h] BYREF
  int v29; // [rsp+88h] [rbp+48h] BYREF
  int v30; // [rsp+90h] [rbp+50h] BYREF
  int v31; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  v3 = 0;
  hHandle = 0;
  v4 = 0;
  v31 = 0;
  v24 = 0;
  v25 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  DEBUGMSG(L"CWmsSelfHealingSvc::StartUp\n");
  v27 = this + 107;
  WmsNamedEvent = CreateWmsNamedEvent(v5, L"Global\\WmsSelfHealingSvcReadyEvent", this + 107);
  if ( WmsNamedEvent < 0 )
    goto LABEL_35;
  WmsNamedEvent = PlatformSkuUtils::IsRole((PlatformSkuUtils *)&v29, v6);
  if ( WmsNamedEvent < 0
    || (WmsNamedEvent = PlatformSkuUtils::IsConnector((PlatformSkuUtils *)&v28, v8), WmsNamedEvent < 0) )
  {
    v4 = v29;
    goto LABEL_35;
  }
  v4 = v29;
  if ( v29 )
    goto LABEL_8;
  if ( !v28 )
  {
LABEL_6:
    WmsNamedEvent = 0;
    goto LABEL_35;
  }
  if ( v29 )
  {
LABEL_8:
    WmsNamedEvent = CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress(&v30);
    if ( WmsNamedEvent < 0 )
      goto LABEL_35;
    if ( v30 )
    {
      DEBUGMSG(L"CWmsSelfHealingSvc::StartUp - VCF is currently uninstalling, not running self-healing.\n");
      goto LABEL_6;
    }
    v11 = CreateWmsNamedEvent(v10, L"Global\\WmsShellStartingEvent", &hHandle);
    v1 = (char *)hHandle;
    WmsNamedEvent = v11;
    if ( v11 < 0 )
      goto LABEL_35;
    if ( !WaitForSingleObject(hHandle, 0) )
      goto LABEL_6;
  }
  WmsNamedEvent = PlatformUtils::HasOobeCompleted((PlatformUtils *)&v31, v9);
  if ( WmsNamedEvent < 0 )
    goto LABEL_35;
  v13 = 0;
  if ( !v31 )
  {
    if ( v4 )
    {
      WmsNamedEvent = CWmsSelfHealingSvc::DisplayStatusMessage(v12, 0x515u);
      if ( WmsNamedEvent < 0 )
        goto LABEL_35;
      v14 = 0;
    }
    else
    {
      v14 = 2;
    }
    WmsNamedEvent = CWmsSelfHealingSvc::RunSelfHealing(v12, v14, &v24);
    if ( WmsNamedEvent < 0 )
      goto LABEL_35;
    WmsNamedEvent = PlatformUtils::SetOobeCompleted(v15);
    if ( WmsNamedEvent < 0 )
      goto LABEL_35;
    v3 = v24;
    v13 = 1;
  }
  CWmsSelfHealingSvc::StartMonitoring(this, v4 != 0 ? 1 : 3);
  WmsNamedEvent = CWmsSelfHealingSvc::RunSelfHealing(v16, v4 != 0 ? 1 : 3, &v25);
  if ( WmsNamedEvent < 0 )
    goto LABEL_35;
  if ( v3 || v25 )
  {
    if ( !v13 || (v19 = 1302, !v4) )
      v19 = 1300;
    WmsNamedEvent = CWmsSelfHealingSvc::DisplayStatusMessage(v17, v19);
    if ( WmsNamedEvent >= 0 )
    {
      started = Reboot(v21, v20, v22);
      goto LABEL_28;
    }
  }
  else if ( v13 && v28 )
  {
    started = StartServiceIfNotRunningAndWait((const unsigned __int16 *)v17);
LABEL_28:
    WmsNamedEvent = started;
  }
LABEL_35:
  if ( *v27 )
    SetEvent(*v27);
  if ( v4 && (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
  DEBUGMSG(L"CWmsSelfHealingSvc::StartUp - hr = 0x%08x\n", (unsigned int)WmsNamedEvent);
  return (unsigned int)WmsNamedEvent;
}

```

## disassembly

```asm
0x1400029e8  push    rbp
0x1400029ea  push    rbx
0x1400029eb  push    rsi
0x1400029ec  push    rdi
0x1400029ed  push    r13
0x1400029ef  push    r14
0x1400029f1  push    r15
0x1400029f3  mov     rbp, rsp
0x1400029f6  sub     rsp, 40h
0x1400029fa  xor     esi, esi
0x1400029fc  mov     r13, rcx
0x1400029ff  xor     r15d, r15d
0x140002a02  mov     [rbp+hHandle], rsi
0x140002a06  xor     edi, edi
0x140002a08  mov     [rbp+arg_18], esi
0x140002a0b  lea     rcx, aCwmsselfhealin_8; "CWmsSelfHealingSvc::StartUp\n"
0x140002a12  mov     [rbp+var_20], r15d
0x140002a16  mov     [rbp+var_1C], esi
0x140002a19  mov     [rbp+arg_10], esi
0x140002a1c  mov     [rbp+arg_8], edi
0x140002a1f  mov     [rbp+arg_0], esi
0x140002a22  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002a27  lea     rax, [r13+358h]
0x140002a2e  mov     r8, rax; void **
0x140002a31  mov     [rbp+var_10], rax
0x140002a35  lea     rdx, aGlobalWmsselfh; "Global\\WmsSelfHealingSvcReadyEvent"
0x140002a3c  call    ?CreateWmsNamedEvent@@YAJKPEBGPEAPEAX@Z; CreateWmsNamedEvent(ulong,ushort const *,void * *)
0x140002a41  mov     ebx, eax
0x140002a43  test    eax, eax
0x140002a45  js      loc_140002BBA
0x140002a4b  lea     rcx, [rbp+arg_8]; this
0x140002a4f  call    ?IsRole@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsRole(int *)
0x140002a54  mov     ebx, eax
0x140002a56  test    eax, eax
0x140002a58  js      loc_140002BB7
0x140002a5e  lea     rcx, [rbp+arg_0]; this
0x140002a62  call    ?IsConnector@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsConnector(int *)
0x140002a67  mov     ebx, eax
0x140002a69  test    eax, eax
0x140002a6b  js      loc_140002BB7
0x140002a71  mov     edi, [rbp+arg_8]
0x140002a74  test    edi, edi
0x140002a76  jnz     short loc_140002A88
0x140002a78  cmp     [rbp+arg_0], esi
0x140002a7b  jnz     short loc_140002A84
0x140002a7d  xor     ebx, ebx
0x140002a7f  jmp     loc_140002BBA
0x140002a84  test    edi, edi
0x140002a86  jz      short loc_140002ADB
0x140002a88  lea     rcx, [rbp+arg_10]; int *
0x140002a8c  call    ?s_CheckDiskProtectionUninstallInProgress@CWmsSelfHealingSvc@@CAJPEAH@Z; CWmsSelfHealingSvc::s_CheckDiskProtectionUninstallInProgress(int *)
0x140002a91  mov     ebx, eax
0x140002a93  test    eax, eax
0x140002a95  js      loc_140002BBA
0x140002a9b  cmp     [rbp+arg_10], esi
0x140002a9e  jz      short loc_140002AAE
0x140002aa0  lea     rcx, aCwmsselfhealin_16; "CWmsSelfHealingSvc::StartUp - VCF is cu"...
0x140002aa7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002aac  jmp     short loc_140002A7D
0x140002aae  lea     r8, [rbp+hHandle]; void **
0x140002ab2  lea     rdx, aGlobalWmsshell; "Global\\WmsShellStartingEvent"
0x140002ab9  call    ?CreateWmsNamedEvent@@YAJKPEBGPEAPEAX@Z; CreateWmsNamedEvent(ulong,ushort const *,void * *)
0x140002abe  mov     rsi, [rbp+hHandle]
0x140002ac2  mov     ebx, eax
0x140002ac4  test    eax, eax
0x140002ac6  js      loc_140002BBA
0x140002acc  xor     edx, edx; dwMilliseconds
0x140002ace  mov     rcx, rsi; hHandle
0x140002ad1  call    cs:__imp_WaitForSingleObject
0x140002ad7  test    eax, eax
0x140002ad9  jz      short loc_140002A7D
0x140002adb  lea     rcx, [rbp+arg_18]; this
0x140002adf  call    ?HasOobeCompleted@PlatformUtils@@YAJPEAH@Z; PlatformUtils::HasOobeCompleted(int *)
0x140002ae4  mov     ebx, eax
0x140002ae6  test    eax, eax
0x140002ae8  js      loc_140002BBA
0x140002aee  xor     r14d, r14d
0x140002af1  cmp     [rbp+arg_18], r14d
0x140002af5  jnz     short loc_140002B44
0x140002af7  test    edi, edi
0x140002af9  jz      short loc_140002B13
0x140002afb  mov     edx, 515h; unsigned int
0x140002b00  call    ?DisplayStatusMessage@CWmsSelfHealingSvc@@AEAAJI@Z; CWmsSelfHealingSvc::DisplayStatusMessage(uint)
0x140002b05  mov     ebx, eax
0x140002b07  test    eax, eax
0x140002b09  js      loc_140002BBA
0x140002b0f  xor     edx, edx
0x140002b11  jmp     short loc_140002B18
0x140002b13  mov     edx, 2
0x140002b18  lea     r8, [rbp+var_20]
0x140002b1c  call    ?RunSelfHealing@CWmsSelfHealingSvc@@AEAAJW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@PEAH@Z; CWmsSelfHealingSvc::RunSelfHealing(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003,int *)
0x140002b21  mov     ebx, eax
0x140002b23  test    eax, eax
0x140002b25  js      loc_140002BBA
0x140002b2b  call    ?SetOobeCompleted@PlatformUtils@@YAJXZ; PlatformUtils::SetOobeCompleted(void)
0x140002b30  mov     ebx, eax
0x140002b32  test    eax, eax
0x140002b34  js      loc_140002BBA
0x140002b3a  mov     r15d, [rbp+var_20]
0x140002b3e  mov     r14d, 1
0x140002b44  mov     eax, edi
0x140002b46  mov     rcx, r13
0x140002b49  neg     eax
0x140002b4b  sbb     edx, edx
0x140002b4d  and     edx, 0FFFFFFFEh
0x140002b50  add     edx, 3
0x140002b53  call    ?StartMonitoring@CWmsSelfHealingSvc@@AEAAJW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@@Z; CWmsSelfHealingSvc::StartMonitoring(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003)
0x140002b58  mov     eax, edi
0x140002b5a  lea     r8, [rbp+var_1C]
0x140002b5e  neg     eax
0x140002b60  sbb     edx, edx
0x140002b62  and     edx, 0FFFFFFFEh
0x140002b65  add     edx, 3
0x140002b68  call    ?RunSelfHealing@CWmsSelfHealingSvc@@AEAAJW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@PEAH@Z; CWmsSelfHealingSvc::RunSelfHealing(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003,int *)
0x140002b6d  mov     ebx, eax
0x140002b6f  test    eax, eax
0x140002b71  js      short loc_140002BBA
0x140002b73  test    r15d, r15d
0x140002b76  jnz     short loc_140002B92
0x140002b78  cmp     [rbp+var_1C], r15d
0x140002b7c  jnz     short loc_140002B92
0x140002b7e  test    r14d, r14d
0x140002b81  jz      short loc_140002BBA
0x140002b83  cmp     [rbp+arg_0], r15d
0x140002b87  jz      short loc_140002BBA
0x140002b89  call    ?StartServiceIfNotRunningAndWait@@YAJPEBG@Z; StartServiceIfNotRunningAndWait(ushort const *)
0x140002b8e  mov     ebx, eax
0x140002b90  jmp     short loc_140002BBA
0x140002b92  test    r14d, r14d
0x140002b95  jz      short loc_140002BA0
0x140002b97  mov     edx, 516h
0x140002b9c  test    edi, edi
0x140002b9e  jnz     short loc_140002BA5
0x140002ba0  mov     edx, 514h; unsigned int
0x140002ba5  call    ?DisplayStatusMessage@CWmsSelfHealingSvc@@AEAAJI@Z; CWmsSelfHealingSvc::DisplayStatusMessage(uint)
0x140002baa  mov     ebx, eax
0x140002bac  test    eax, eax
0x140002bae  js      short loc_140002BBA
0x140002bb0  call    ?Reboot@@YAJPEBGKK@Z; Reboot(ushort const *,ulong,ulong)
0x140002bb5  jmp     short loc_140002B8E
0x140002bb7  mov     edi, [rbp+arg_8]
0x140002bba  mov     rcx, [rbp+var_10]
0x140002bbe  mov     rcx, [rcx]; hEvent
0x140002bc1  test    rcx, rcx
0x140002bc4  jz      short loc_140002BCC
0x140002bc6  call    cs:__imp_SetEvent
0x140002bcc  test    edi, edi
0x140002bce  jz      short loc_140002BE3
0x140002bd0  lea     rax, [rsi-1]
0x140002bd4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002bd8  ja      short loc_140002BE3
0x140002bda  mov     rcx, rsi; hObject
0x140002bdd  call    cs:__imp_CloseHandle
0x140002be3  mov     edx, ebx
0x140002be5  lea     rcx, aCwmsselfhealin_6; "CWmsSelfHealingSvc::StartUp - hr = 0x%0"...
0x140002bec  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002bf1  mov     eax, ebx
0x140002bf3  add     rsp, 40h
0x140002bf7  pop     r15
0x140002bf9  pop     r14
0x140002bfb  pop     r13
0x140002bfd  pop     rdi
0x140002bfe  pop     rsi
0x140002bff  pop     rbx
0x140002c00  pop     rbp
0x140002c01  retn
```
