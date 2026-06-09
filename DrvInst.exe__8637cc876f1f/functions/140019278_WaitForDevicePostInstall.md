# WaitForDevicePostInstall

- ea: `0x140019278`
- end: `0x1400196bf`
- name: `WaitForDevicePostInstall`
- size: `1095`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140018dc0`

## callees

- `0x140018dc0`
- `0x140019278`
- `0x14002102c`
- `0x140021204`
- `0x140021274`
- `0x1400270b4`
- `0x14002741c`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400194a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400194a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400195ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400195ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400195e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400195e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001969a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001969a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001932b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019365`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400194dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001957a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001959d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001960f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019637`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019657`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001932b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019365`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400194dd`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001957a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001959d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001960f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019637`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019657`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400192dc`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400192dc`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x14001953d`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQueryFromId` at `0x14001953d`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140019686`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x140019686`

## string_xrefs

- `0x140019314`: `Not waiting for device post-install to complete when reboot required.`
- `0x14001934e`: `Not waiting for device post-install to complete because device is disabled.`
- `0x1400194c6`: `Unable to create event for post-install operation. Error = 0x%08X`
- `0x140019563`: `Unable to create device query for post-install operation. Error = 0x%08X`
- `0x140019586`: `Waiting for device post-install to complete.`
- `0x1400195f8`: `Unable to wait for device post-install to complete. Error = 0x%08X`
- `0x140019620`: `Timed out waiting for device post-install to complete.`
- `0x140019640`: `Device post-install completed.`

## pseudocode

```c
__int64 __fastcall WaitForDevicePostInstall(DEVINST a1, __int64 a2)
{
  DWORD LastError; // [rsp+50h] [rbp-148h]
  char v4; // [rsp+54h] [rbp-144h] BYREF
  __int64 ThreadLogToken; // [rsp+58h] [rbp-140h]
  int v6; // [rsp+60h] [rbp-138h]
  DWORD v7; // [rsp+64h] [rbp-134h]
  HANDLE hHandle; // [rsp+68h] [rbp-130h]
  DWORD v9; // [rsp+70h] [rbp-128h]
  __int64 v10; // [rsp+78h] [rbp-120h] BYREF
  __int64 CurrentTickCount; // [rsp+80h] [rbp-118h]
  _QWORD v12[28]; // [rsp+90h] [rbp-108h] BYREF

  LastError = 0;
  v6 = 0;
  v4 = 0;
  CurrentTickCount = 0;
  hHandle = 0;
  v10 = 0;
  v9 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( !(unsigned int)IsDevicePostInstallInProgress(a1) )
  {
    LastError = 0;
    goto LABEL_19;
  }
  if ( (unsigned int)DevUtilsDeviceNeedsReboot(a1) )
  {
    DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Not waiting for device post-install to complete when reboot required.");
    LastError = 0;
    goto LABEL_19;
  }
  if ( (unsigned int)DevUtilsIsDeviceDisabled(a1) )
  {
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      4,
      "Not waiting for device post-install to complete because device is disabled.");
    LastError = 0;
    goto LABEL_19;
  }
  DrvInstActionCallback(0, 0);
  memset(v12, 0, sizeof(v12));
  LODWORD(v12[0]) = 3145728;
  LODWORD(v12[7]) = 2;
  qmemcpy(&v12[8], &DEVPKEY_Device_PostInstallInProgress, 0x14u);
  HIDWORD(v12[10]) = 0;
  v12[12] = 0x100000011LL;
  v12[13] = &v4;
  LODWORD(v12[14]) = 65537;
  qmemcpy(&v12[15], &DEVPKEY_Device_PostInstallInProgress, 0x14u);
  HIDWORD(v12[17]) = 0;
  LODWORD(v12[21]) = 0x400000;
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( !hHandle )
  {
    LastError = GetLastError();
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      2,
      "Unable to create event for post-install operation. Error = 0x%08X",
      LastError);
    goto LABEL_19;
  }
  v6 = DevCreateObjectQueryFromId(3, a2, 1, 0, 0, 4, v12, &WaitForDevicePostInstallCompleteCallback, hHandle, &v10);
  if ( v6 < 0 )
  {
    LastError = (unsigned __int16)v6;
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      2,
      "Unable to create device query for post-install operation. Error = 0x%08X",
      (unsigned __int16)v6);
    goto LABEL_19;
  }
  DevRtlWriteTextLog(ThreadLogToken, 1, 65540, "Waiting for device post-install to complete.");
  CurrentTickCount = GetCurrentTickCount();
  v9 = WaitForSingleObject(hHandle, 0x36EE8u);
  v7 = v9;
  if ( v9 )
  {
    if ( v7 == 258 )
    {
      LastError = 1460;
      DevRtlWriteTextLog(ThreadLogToken, 1, 65537, "Timed out waiting for device post-install to complete.");
      goto LABEL_17;
    }
    if ( v7 == -1 )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(
        ThreadLogToken,
        1,
        65538,
        "Unable to wait for device post-install to complete. Error = 0x%08X",
        LastError);
      goto LABEL_17;
    }
  }
  DevRtlWriteTextLog(ThreadLogToken, 1, 65540, "Device post-install completed.");
LABEL_17:
  if ( !LastError )
    LogDeviceStatus(a1);
LABEL_19:
  if ( v10 )
    DevCloseObjectQuery(v10);
  if ( hHandle )
    CloseHandle(hHandle);
  return LastError;
}

```

## disassembly

```asm
0x140019278  mov     [rsp+arg_10], r8
0x14001927d  mov     [rsp+arg_8], rdx
0x140019282  mov     [rsp+dnDevInst], ecx
0x140019286  push    rsi
0x140019287  push    rdi
0x140019288  sub     rsp, 188h
0x14001928f  mov     rax, cs:__security_cookie
0x140019296  xor     rax, rsp
0x140019299  mov     [rsp+198h+var_28], rax
0x1400192a1  mov     [rsp+198h+var_148], 0
0x1400192a9  mov     [rsp+198h+var_138], 0
0x1400192b1  mov     [rsp+198h+var_144], 0
0x1400192b6  mov     [rsp+198h+var_118], 0
0x1400192c2  mov     [rsp+198h+hHandle], 0
0x1400192cb  mov     [rsp+198h+var_120], 0
0x1400192d4  mov     [rsp+198h+var_128], 0
0x1400192dc  call    cs:__imp_DevRtlGetThreadLogToken
0x1400192e2  mov     [rsp+198h+var_140], rax
0x1400192e7  mov     ecx, [rsp+198h+dnDevInst]
0x1400192ee  call    IsDevicePostInstallInProgress
0x1400192f3  test    eax, eax
0x1400192f5  jnz     short loc_140019304
0x1400192f7  mov     [rsp+198h+var_148], 0
0x1400192ff  jmp     loc_140019679
0x140019304  mov     ecx, [rsp+198h+dnDevInst]
0x14001930b  call    DevUtilsDeviceNeedsReboot
0x140019310  test    eax, eax
0x140019312  jz      short loc_14001933E
0x140019314  lea     r9, aNotWaitingForD; "Not waiting for device post-install to "...
0x14001931b  mov     r8d, 2
0x140019321  mov     edx, 1
0x140019326  mov     rcx, [rsp+198h+var_140]
0x14001932b  call    cs:__imp_DevRtlWriteTextLog
0x140019331  mov     [rsp+198h+var_148], 0
0x140019339  jmp     loc_140019679
0x14001933e  mov     ecx, [rsp+198h+dnDevInst]
0x140019345  call    DevUtilsIsDeviceDisabled
0x14001934a  test    eax, eax
0x14001934c  jz      short loc_140019378
0x14001934e  lea     r9, aNotWaitingForD_0; "Not waiting for device post-install to "...
0x140019355  mov     r8d, 4
0x14001935b  mov     edx, 1
0x140019360  mov     rcx, [rsp+198h+var_140]
0x140019365  call    cs:__imp_DevRtlWriteTextLog
0x14001936b  mov     [rsp+198h+var_148], 0
0x140019373  jmp     loc_140019679
0x140019378  mov     r8, [rsp+198h+arg_10]
0x140019380  xor     edx, edx
0x140019382  xor     ecx, ecx
0x140019384  call    DrvInstActionCallback
0x140019389  lea     rax, [rsp+198h+var_108]
0x140019391  mov     rdi, rax
0x140019394  xor     eax, eax
0x140019396  mov     ecx, 0E0h
0x14001939b  rep stosb
0x14001939d  mov     eax, 38h ; '8'
0x1400193a2  imul    rax, 0
0x1400193a6  mov     [rsp+rax+198h+var_108], 300000h
0x1400193b1  mov     eax, 38h ; '8'
0x1400193b6  imul    rax, 1
0x1400193ba  mov     [rsp+rax+198h+var_108], 2
0x1400193c5  mov     eax, 38h ; '8'
0x1400193ca  imul    rax, 1
0x1400193ce  lea     rcx, DEVPKEY_Device_PostInstallInProgress
0x1400193d5  lea     rdi, [rsp+rax+198h+var_100]
0x1400193dd  mov     rsi, rcx
0x1400193e0  mov     ecx, 14h
0x1400193e5  rep movsb
0x1400193e7  mov     eax, 38h ; '8'
0x1400193ec  imul    rax, 1
0x1400193f0  mov     [rsp+rax+198h+var_EC], 0
0x1400193fb  mov     eax, 38h ; '8'
0x140019400  imul    rax, 1
0x140019404  mov     [rsp+rax+198h+var_E0], 11h
0x14001940f  mov     eax, 38h ; '8'
0x140019414  imul    rax, 1
0x140019418  mov     [rsp+rax+198h+var_DC], 1
0x140019423  mov     eax, 38h ; '8'
0x140019428  imul    rax, 1
0x14001942c  lea     rcx, [rsp+198h+var_144]
0x140019431  mov     [rsp+rax+198h+var_D8], rcx
0x140019439  mov     eax, 38h ; '8'
0x14001943e  imul    rax, 2
0x140019442  mov     [rsp+rax+198h+var_108], 10001h
0x14001944d  mov     eax, 38h ; '8'
0x140019452  imul    rax, 2
0x140019456  lea     rcx, DEVPKEY_Device_PostInstallInProgress
0x14001945d  lea     rdi, [rsp+rax+198h+var_100]
0x140019465  mov     rsi, rcx
0x140019468  mov     ecx, 14h
0x14001946d  rep movsb
0x14001946f  mov     eax, 38h ; '8'
0x140019474  imul    rax, 2
0x140019478  mov     [rsp+rax+198h+var_EC], 0
0x140019483  mov     eax, 38h ; '8'
0x140019488  imul    rax, 3
0x14001948c  mov     [rsp+rax+198h+var_108], 400000h
0x140019497  xor     r9d, r9d; lpName
0x14001949a  xor     r8d, r8d; bInitialState
0x14001949d  xor     edx, edx; bManualReset
0x14001949f  xor     ecx, ecx; lpEventAttributes
0x1400194a1  call    cs:__imp_CreateEventW
0x1400194a7  mov     [rsp+198h+hHandle], rax
0x1400194ac  cmp     [rsp+198h+hHandle], 0
0x1400194b2  jnz     short loc_1400194E9
0x1400194b4  call    cs:__imp_GetLastError
0x1400194ba  mov     [rsp+198h+var_148], eax
0x1400194be  mov     eax, [rsp+198h+var_148]
0x1400194c2  mov     dword ptr [rsp+198h+var_178], eax
0x1400194c6  lea     r9, aUnableToCreate_2; "Unable to create event for post-install"...
0x1400194cd  mov     r8d, 2
0x1400194d3  mov     edx, 1
0x1400194d8  mov     rcx, [rsp+198h+var_140]
0x1400194dd  call    cs:__imp_DevRtlWriteTextLog
0x1400194e3  nop
0x1400194e4  jmp     loc_140019679
0x1400194e9  lea     rax, [rsp+198h+var_120]
0x1400194ee  mov     [rsp+198h+var_150], rax
0x1400194f3  mov     rax, [rsp+198h+hHandle]
0x1400194f8  mov     [rsp+198h+var_158], rax
0x1400194fd  lea     rax, WaitForDevicePostInstallCompleteCallback
0x140019504  mov     [rsp+198h+var_160], rax
0x140019509  lea     rax, [rsp+198h+var_108]
0x140019511  mov     [rsp+198h+var_168], rax
0x140019516  mov     [rsp+198h+var_170], 4
0x14001951e  mov     [rsp+198h+var_178], 0
0x140019527  xor     r9d, r9d
0x14001952a  mov     r8d, 1
0x140019530  mov     rdx, [rsp+198h+arg_8]
0x140019538  mov     ecx, 3
0x14001953d  call    cs:__imp_DevCreateObjectQueryFromId
0x140019543  mov     [rsp+198h+var_138], eax
0x140019547  cmp     [rsp+198h+var_138], 0
0x14001954c  jge     short loc_140019586
0x14001954e  mov     eax, [rsp+198h+var_138]
0x140019552  and     eax, 0FFFFh
0x140019557  mov     [rsp+198h+var_148], eax
0x14001955b  mov     eax, [rsp+198h+var_148]
0x14001955f  mov     dword ptr [rsp+198h+var_178], eax
0x140019563  lea     r9, aUnableToCreate_0; "Unable to create device query for post-"...
0x14001956a  mov     r8d, 2
0x140019570  mov     edx, 1
0x140019575  mov     rcx, [rsp+198h+var_140]
0x14001957a  call    cs:__imp_DevRtlWriteTextLog
0x140019580  nop
0x140019581  jmp     loc_140019679
0x140019586  lea     r9, aWaitingForDevi; "Waiting for device post-install to comp"...
0x14001958d  mov     r8d, 10004h
0x140019593  mov     edx, 1
0x140019598  mov     rcx, [rsp+198h+var_140]
0x14001959d  call    cs:__imp_DevRtlWriteTextLog
0x1400195a3  call    GetCurrentTickCount
0x1400195a8  mov     [rsp+198h+var_118], rax
0x1400195b0  mov     edx, 36EE8h; dwMilliseconds
0x1400195b5  mov     rcx, [rsp+198h+hHandle]; hHandle
0x1400195ba  call    cs:__imp_WaitForSingleObject
0x1400195c0  mov     [rsp+198h+var_128], eax
0x1400195c4  mov     eax, [rsp+198h+var_128]
0x1400195c8  mov     [rsp+198h+var_134], eax
0x1400195cc  cmp     [rsp+198h+var_134], 0
0x1400195d1  jz      short loc_140019640
0x1400195d3  cmp     [rsp+198h+var_134], 102h
0x1400195db  jz      short loc_140019618
0x1400195dd  cmp     [rsp+198h+var_134], 0FFFFFFFFh
0x1400195e2  jz      short loc_1400195E6
0x1400195e4  jmp     short loc_140019640
0x1400195e6  call    cs:__imp_GetLastError
0x1400195ec  mov     [rsp+198h+var_148], eax
0x1400195f0  mov     eax, [rsp+198h+var_148]
0x1400195f4  mov     dword ptr [rsp+198h+var_178], eax
0x1400195f8  lea     r9, aUnableToWaitFo; "Unable to wait for device post-install "...
0x1400195ff  mov     r8d, 10002h
0x140019605  mov     edx, 1
0x14001960a  mov     rcx, [rsp+198h+var_140]
0x14001960f  call    cs:__imp_DevRtlWriteTextLog
0x140019615  nop
0x140019616  jmp     short loc_14001965E
0x140019618  mov     [rsp+198h+var_148], 5B4h
0x140019620  lea     r9, aTimedOutWaitin; "Timed out waiting for device post-insta"...
0x140019627  mov     r8d, 10001h
0x14001962d  mov     edx, 1
0x140019632  mov     rcx, [rsp+198h+var_140]
0x140019637  call    cs:__imp_DevRtlWriteTextLog
0x14001963d  nop
0x14001963e  jmp     short loc_14001965E
0x140019640  lea     r9, aDevicePostInst; "Device post-install completed."
0x140019647  mov     r8d, 10004h
0x14001964d  mov     edx, 1
0x140019652  mov     rcx, [rsp+198h+var_140]
0x140019657  call    cs:__imp_DevRtlWriteTextLog
0x14001965d  nop
0x14001965e  cmp     [rsp+198h+var_148], 0
0x140019663  jz      short loc_140019667
0x140019665  jmp     short loc_140019679
0x140019667  mov     rdx, [rsp+198h+var_140]
0x14001966c  mov     ecx, [rsp+198h+dnDevInst]; dnDevInst
0x140019673  call    LogDeviceStatus
0x140019678  nop
0x140019679  cmp     [rsp+198h+var_120], 0
0x14001967f  jz      short loc_14001968D
0x140019681  mov     rcx, [rsp+198h+var_120]
0x140019686  call    cs:__imp_DevCloseObjectQuery
0x14001968c  nop
0x14001968d  cmp     [rsp+198h+hHandle], 0
0x140019693  jz      short loc_1400196A1
0x140019695  mov     rcx, [rsp+198h+hHandle]; hObject
0x14001969a  call    cs:__imp_CloseHandle
0x1400196a0  nop
0x1400196a1  mov     eax, [rsp+198h+var_148]
0x1400196a5  mov     rcx, [rsp+198h+var_28]
0x1400196ad  xor     rcx, rsp; StackCookie
0x1400196b0  call    __security_check_cookie
0x1400196b5  add     rsp, 188h
0x1400196bc  pop     rdi
0x1400196bd  pop     rsi
0x1400196be  retn
```
