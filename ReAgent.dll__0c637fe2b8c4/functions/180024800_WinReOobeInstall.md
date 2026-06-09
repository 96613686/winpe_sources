# WinReOobeInstall

- ea: `0x180024800`
- end: `0x1800249fe`
- name: `WinReOobeInstall`
- size: `510`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x1800193e8`
- `0x18001dc60`
- `0x180024800`
- `0x180026670`
- `0x1800295a0`
- `0x180029f28`
- `0x180030b98`
- `0x180032924`
- `0x180032e98`
- `0x18003307c`
- `0x1800331a8`
- `0x18004e104`
- `0x1800502e0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800248de`
- `KERNEL32!GetLastError` at `0x1800248de`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180024867`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180024867`

## string_xrefs

- `0x18002483b`: `Enter WinReOobeInstall`
- `0x1800248e4`: `WinReOobeInstall GetSystemWindowsDirectory failed, error 0X%X`
- `0x180024892`: `WinReOobeInstall Target drive (%s) is not a valid drive letter`
- `0x1800248cc`: `WinReOobeInstall PBRSucceed event was scheduled`
- `0x1800248fe`: `WinReOobeInstall Checking if install is needed`
- `0x180024962`: `WinReOobeInstall WinRE install succeeded`
- `0x18002496d`: `WinReOobeInstall WinRE install did not succeed`
- `0x180024985`: `WinReOobeInstall Resetting WinRE recovery action`
- `0x1800249a7`: `WinReOobeInstall Resealing volume if necessary`
- `0x1800249bf`: `WinReOobeInstall WinRE installation in OOBE completed`
- `0x1800249d0`: `Exit WinReOobeInstall return value: %d`

## pseudocode

```c
__int64 WinReOobeInstall()
{
  unsigned int v0; // ebx
  DWORD LastError; // eax
  WCHAR Buffer; // [rsp+60h] [rbp-228h] BYREF
  _BYTE v4[2]; // [rsp+62h] [rbp-226h] BYREF
  __int16 v5; // [rsp+64h] [rbp-224h]

  Buffer = 0;
  memset_0(v4, 0, 0x206u);
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReOobeInstall");
  winreSetRecoveryTimestamp();
  winreSetDriverEpoch();
  winreSetRecoveryDirectorySecurity();
  winreTraceHostInstallType();
  if ( GetSystemWindowsDirectoryW(&Buffer, 0x104u) - 1 > 0x103 )
  {
    v0 = 0;
    LastError = GetLastError();
    UnattendLogW(0, L"WinReOobeInstall GetSystemWindowsDirectory failed, error 0X%X", LastError);
  }
  else
  {
    v5 = 0;
    if ( (unsigned int)Utils::IsDriveLetter(&Buffer) )
    {
      v0 = 1;
      if ( (unsigned int)CheckRegKey(L"SYSTEM\\Setup", L"PushButtonReset")
        && (unsigned int)SchedulePBRSuccessTask(&Buffer) )
      {
        UnattendLogW(0, L"WinReOobeInstall PBRSucceed event was scheduled");
      }
    }
    else
    {
      v0 = 0;
      UnattendLogW(0, L"WinReOobeInstall Target drive (%s) is not a valid drive letter", &Buffer);
    }
  }
  if ( (unsigned int)winreIsServerSku() )
  {
    UnattendLogW(0, L"WinReOobeInstall Checking if install is needed");
    if ( (unsigned int)WinReInstallOnTargetOSInternal(0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0) || !v0 )
    {
      v0 = 0;
      UnattendLogW(0, L"WinReOobeInstall WinRE install did not succeed");
    }
    else
    {
      v0 = 1;
      UnattendLogW(0, L"WinReOobeInstall WinRE install succeeded");
    }
  }
  winreConfigureValidationTask(1);
  UnattendLogW(0, L"WinReOobeInstall Resetting WinRE recovery action");
  WinReSetRecoveryAction(5, 0, 0, 0);
  if ( v0 )
  {
    UnattendLogW(0, L"WinReOobeInstall Resealing volume if necessary");
    CFveUtil::ResealVolumeIfNeeded(&Buffer);
  }
  UnattendLogW(0, L"WinReOobeInstall WinRE installation in OOBE completed");
  UnattendLogW(0, L"Exit WinReOobeInstall return value: %d", v0);
  UnattendFinalizeLog();
  return v0;
}

```

## disassembly

```asm
0x180024800  push    rbx
0x180024802  sub     rsp, 280h
0x180024809  mov     rax, cs:__security_cookie
0x180024810  xor     rax, rsp
0x180024813  mov     [rsp+288h+var_18], rax
0x18002481b  xor     eax, eax
0x18002481d  lea     rcx, [rsp+288h+var_226]; void *
0x180024822  xor     edx, edx; Val
0x180024824  mov     [rsp+288h+Buffer], ax
0x180024829  mov     r8d, 206h; Size
0x18002482f  call    memset_0
0x180024834  xor     ecx, ecx
0x180024836  call    UnattendInitializeLogEx2
0x18002483b  lea     rdx, aEnterWinreoobe; "Enter WinReOobeInstall"
0x180024842  xor     ecx, ecx
0x180024844  call    UnattendLogW
0x180024849  call    winreSetRecoveryTimestamp
0x18002484e  call    winreSetDriverEpoch
0x180024853  call    winreSetRecoveryDirectorySecurity
0x180024858  call    winreTraceHostInstallType
0x18002485d  mov     edx, 104h; uSize
0x180024862  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x180024867  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002486d  dec     eax
0x18002486f  cmp     eax, 103h
0x180024874  ja      short loc_1800248DC
0x180024876  xor     eax, eax
0x180024878  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x18002487d  mov     [rsp+288h+var_224], ax
0x180024882  call    ?IsDriveLetter@Utils@@SAHPEBG@Z; Utils::IsDriveLetter(ushort const *)
0x180024887  test    eax, eax
0x180024889  jnz     short loc_1800248A2
0x18002488b  xor     ebx, ebx
0x18002488d  lea     r8, [rsp+288h+Buffer]
0x180024892  lea     rdx, aWinreoobeinsta_6; "WinReOobeInstall Target drive (%s) is n"...
0x180024899  xor     ecx, ecx
0x18002489b  call    UnattendLogW
0x1800248a0  jmp     short loc_1800248F5
0x1800248a2  lea     rdx, aPushbuttonrese; "PushButtonReset"
0x1800248a9  mov     ebx, 1
0x1800248ae  lea     rcx, aSystemSetup; "SYSTEM\\Setup"
0x1800248b5  call    CheckRegKey
0x1800248ba  test    eax, eax
0x1800248bc  jz      short loc_1800248F5
0x1800248be  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x1800248c3  call    ?SchedulePBRSuccessTask@@YAHPEBG@Z; SchedulePBRSuccessTask(ushort const *)
0x1800248c8  test    eax, eax
0x1800248ca  jz      short loc_1800248F5
0x1800248cc  lea     rdx, aWinreoobeinsta_7; "WinReOobeInstall PBRSucceed event was s"...
0x1800248d3  xor     ecx, ecx
0x1800248d5  call    UnattendLogW
0x1800248da  jmp     short loc_1800248F5
0x1800248dc  xor     ebx, ebx
0x1800248de  call    cs:__imp_GetLastError
0x1800248e4  lea     rdx, aWinreoobeinsta_0; "WinReOobeInstall GetSystemWindowsDirect"...
0x1800248eb  xor     ecx, ecx
0x1800248ed  mov     r8d, eax
0x1800248f0  call    UnattendLogW
0x1800248f5  call    winreIsServerSku
0x1800248fa  test    eax, eax
0x1800248fc  jz      short loc_18002497B
0x1800248fe  lea     rdx, aWinreoobeinsta_1; "WinReOobeInstall Checking if install is"...
0x180024905  xor     ecx, ecx
0x180024907  call    UnattendLogW
0x18002490c  mov     [rsp+288h+var_238], 0
0x180024915  xor     r9d, r9d
0x180024918  mov     [rsp+288h+var_240], 0
0x180024921  xor     r8d, r8d
0x180024924  mov     [rsp+288h+var_248], 0
0x18002492d  xor     edx, edx
0x18002492f  mov     [rsp+288h+var_250], 0
0x180024937  xor     ecx, ecx
0x180024939  mov     [rsp+288h+var_258], 0
0x180024941  mov     [rsp+288h+var_260], 0
0x180024949  mov     [rsp+288h+var_268], 0
0x180024952  call    ?WinReInstallOnTargetOSInternal@@YAKHPEAHPEAU_GUID@@HPEBGHKW4_WINRE_PARTITION_LOCATION@@20PEAUPartitionNode@@@Z; WinReInstallOnTargetOSInternal(int,int *,_GUID *,int,ushort const *,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,int *,PartitionNode *)
0x180024957  test    eax, eax
0x180024959  jnz     short loc_18002496B
0x18002495b  test    ebx, ebx
0x18002495d  jz      short loc_18002496B
0x18002495f  lea     ebx, [rax+1]
0x180024962  lea     rdx, aWinreoobeinsta_8; "WinReOobeInstall WinRE install succeede"...
0x180024969  jmp     short loc_180024974
0x18002496b  xor     ebx, ebx
0x18002496d  lea     rdx, aWinreoobeinsta_2; "WinReOobeInstall WinRE install did not "...
0x180024974  xor     ecx, ecx
0x180024976  call    UnattendLogW
0x18002497b  mov     ecx, 1
0x180024980  call    winreConfigureValidationTask
0x180024985  lea     rdx, aWinreoobeinsta_3; "WinReOobeInstall Resetting WinRE recove"...
0x18002498c  xor     ecx, ecx
0x18002498e  call    UnattendLogW
0x180024993  xor     edx, edx
0x180024995  xor     r9d, r9d
0x180024998  xor     r8d, r8d
0x18002499b  lea     ecx, [rdx+5]
0x18002499e  call    WinReSetRecoveryAction
0x1800249a3  test    ebx, ebx
0x1800249a5  jz      short loc_1800249BF
0x1800249a7  lea     rdx, aWinreoobeinsta_5; "WinReOobeInstall Resealing volume if ne"...
0x1800249ae  xor     ecx, ecx
0x1800249b0  call    UnattendLogW
0x1800249b5  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x1800249ba  call    ?ResealVolumeIfNeeded@CFveUtil@@SAKPEBG@Z; CFveUtil::ResealVolumeIfNeeded(ushort const *)
0x1800249bf  lea     rdx, aWinreoobeinsta_4; "WinReOobeInstall WinRE installation in "...
0x1800249c6  xor     ecx, ecx
0x1800249c8  call    UnattendLogW
0x1800249cd  mov     r8d, ebx
0x1800249d0  lea     rdx, aExitWinreoobei; "Exit WinReOobeInstall return value: %d"
0x1800249d7  xor     ecx, ecx
0x1800249d9  call    UnattendLogW
0x1800249de  call    UnattendFinalizeLog
0x1800249e3  mov     eax, ebx
0x1800249e5  mov     rcx, [rsp+288h+var_18]
0x1800249ed  xor     rcx, rsp; StackCookie
0x1800249f0  call    __security_check_cookie
0x1800249f5  add     rsp, 280h
0x1800249fc  pop     rbx
0x1800249fd  retn
```
