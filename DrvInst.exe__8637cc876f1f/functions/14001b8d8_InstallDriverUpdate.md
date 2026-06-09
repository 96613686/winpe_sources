# InstallDriverUpdate

- ea: `0x14001b8d8`
- end: `0x14001bbd1`
- name: `InstallDriverUpdate`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14001ae4c`

## callees

- `0x1400109b0`
- `0x140010a88`
- `0x140013e14`
- `0x14001992c`
- `0x14001a9f0`
- `0x14001b8d8`
- `0x140026994`
- `0x1400271b8`
- `0x14002bd44`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ba1f`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001ba43`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001ba43`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001b970`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001b9c9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001baaa`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bb34`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bb59`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bba6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001b970`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001b9c9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001baaa`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bb34`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bb59`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001bba6`

## string_xrefs

- `0x14001b939`: `{Install Driver Update - %ws}`
- `0x14001baa0`: `Installing device '%ws' due to match on device ID '%ws'.`
- `0x14001bb22`: `No devices need driver update.`
- `0x14001bb4b`: `Driver update needs reboot.`
- `0x14001bb8d`: `{Install Driver Update - exit(0x%08X)}`

## pseudocode

```c
__int64 __fastcall InstallDriverUpdate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        struct _DRVUTILS_UPDATE_INFO *a5,
        _DWORD *a6,
        _DWORD *a7,
        unsigned __int64 a8)
{
  int v10; // r13d
  int v11; // r14d
  __int64 v12; // r12
  DWORD DriverPackageInfo; // ebx
  int v14; // eax
  int *DeviceIdList; // rsi
  DWORD v16; // eax
  __int64 v17; // rax
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  struct _DRVUTILS_UPDATE_INFO *v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  _DWORD *v26; // [rsp+68h] [rbp-98h]
  _DWORD *v27; // [rsp+70h] [rbp-90h]
  _BYTE v28[528]; // [rsp+80h] [rbp-80h] BYREF

  v24 = a5;
  v10 = 0;
  v11 = 0;
  v22 = a4;
  v25 = a3;
  v26 = a6;
  v27 = a7;
  v21 = 0;
  pdnDevInst = 0;
  LODWORD(v23) = 0;
  v20 = 0;
  DevRtlWriteTextLog(a8, 1, 196612, "{Install Driver Update - %ws}", a2);
  v12 = pSetupStringTableInitialize();
  if ( !v12 )
  {
    DriverPackageInfo = 14;
    goto LABEL_30;
  }
  DriverPackageInfo = DrvUtilsGetDriverPackageInfo(0, a2, 9, v12, &v21);
  v14 = 0;
  if ( DriverPackageInfo )
  {
    DevRtlWriteTextLog(a8, 1, 1, "Failed to build list of device IDs in '%ws'. Error = 0x%08X", a2, DriverPackageInfo);
    goto LABEL_30;
  }
  if ( v21 == 4 )
  {
    DriverPackageInfo = InstallDriver(a1, a2, (unsigned int)v22, &v20);
    if ( !DriverPackageInfo )
    {
      v11 = v20;
      goto LABEL_26;
    }
    goto LABEL_30;
  }
  LOBYTE(v14) = v21 == 2;
  v20 = v14;
  DeviceIdList = (int *)DevUtilsGetDeviceIdList();
  if ( !DeviceIdList )
  {
    DriverPackageInfo = GetLastError();
    goto LABEL_30;
  }
  while ( *(_WORD *)DeviceIdList )
  {
    if ( !CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)DeviceIdList, 1u) )
    {
      if ( v24 )
      {
        if ( (unsigned int)PnpUtilsDriverUpdateAppliesToDevNode(pdnDevInst) )
        {
          DevRtlWriteTextLog(a8, 1, 4, "Installing device '%ws' due to match on device ID '%ws'.", DeviceIdList, v28);
LABEL_17:
          v16 = InstallDeviceDriverUpdate(pdnDevInst, DeviceIdList, a2, v25, v22, v24, (int *)&v23, a8);
          DriverPackageInfo = v16;
          if ( v16 == -536870389 )
          {
            DriverPackageInfo = 0;
          }
          else
          {
            if ( v16 )
              goto LABEL_30;
            v11 |= v23;
            ++v10;
          }
        }
      }
      else if ( (unsigned int)DeviceMatchesDeviceId(pdnDevInst) )
      {
        goto LABEL_17;
      }
    }
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)DeviceIdList + v17) );
    DeviceIdList = (int *)((char *)DeviceIdList + 2 * v17 + 2);
    if ( !DeviceIdList )
      break;
  }
  if ( !v10 )
    DevRtlWriteTextLog(a8, 1, 4, "No devices need driver update.");
LABEL_26:
  *(_DWORD *)(a2 + 1584) |= 2u;
  if ( v11 )
  {
    DevRtlWriteTextLog(a8, 1, 4, "Driver update needs reboot.");
    *(_DWORD *)(a2 + 1584) |= 4u;
  }
  if ( v26 )
    *v26 = v11;
LABEL_30:
  if ( v27 )
    *v27 = v10;
  if ( v12 )
    pSetupStringTableDestroy(v12);
  DevRtlWriteTextLog(a8, 1, 327684, "{Install Driver Update - exit(0x%08X)}", DriverPackageInfo);
  return DriverPackageInfo;
}

```

## disassembly

```asm
0x14001b8d8  push    rbp
0x14001b8da  push    rbx
0x14001b8db  push    rsi
0x14001b8dc  push    rdi
0x14001b8dd  push    r12
0x14001b8df  push    r13
0x14001b8e1  push    r14
0x14001b8e3  push    r15
0x14001b8e5  lea     rbp, [rsp-1A8h]
0x14001b8ed  sub     rsp, 2A8h
0x14001b8f4  mov     rax, cs:__security_cookie
0x14001b8fb  xor     rax, rsp
0x14001b8fe  mov     [rbp+1E0h+var_50], rax
0x14001b905  mov     rax, [rbp+1E0h+arg_20]
0x14001b90c  xor     ebx, ebx
0x14001b90e  mov     r15, [rbp+1E0h+arg_38]
0x14001b915  mov     rsi, rcx
0x14001b918  mov     rcx, [rbp+1E0h+arg_28]
0x14001b91f  mov     rdi, rdx
0x14001b922  mov     [rsp+2E0h+var_288], rax
0x14001b927  mov     r13d, ebx
0x14001b92a  mov     rax, [rbp+1E0h+arg_30]
0x14001b931  mov     r14d, ebx
0x14001b934  mov     [rsp+2E0h+var_294], r9d
0x14001b939  lea     r9, aInstallDriverU_0; "{Install Driver Update - %ws}"
0x14001b940  mov     [rsp+2E0h+var_280], r8
0x14001b945  mov     r8d, 30004h
0x14001b94b  mov     [rsp+2E0h+var_278], rcx
0x14001b950  mov     rcx, r15
0x14001b953  mov     qword ptr [rsp+2E0h+var_2C0], rdx
0x14001b958  lea     edx, [rbx+1]
0x14001b95b  mov     [rsp+2E0h+var_270], rax
0x14001b960  mov     [rsp+2E0h+var_298], ebx
0x14001b964  mov     [rsp+2E0h+pdnDevInst], ebx
0x14001b968  mov     dword ptr [rsp+2E0h+var_290], ebx
0x14001b96c  mov     [rsp+2E0h+var_29C], ebx
0x14001b970  call    cs:__imp_DevRtlWriteTextLog
0x14001b976  call    pSetupStringTableInitialize
0x14001b97b  mov     r12, rax
0x14001b97e  test    rax, rax
0x14001b981  jnz     short loc_14001B98B
0x14001b983  lea     ebx, [rax+0Eh]
0x14001b986  jmp     loc_14001BB73
0x14001b98b  lea     rax, [rsp+2E0h+var_298]
0x14001b990  mov     r8d, 9
0x14001b996  mov     r9, r12
0x14001b999  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x14001b99e  mov     rdx, rdi
0x14001b9a1  xor     ecx, ecx
0x14001b9a3  call    DrvUtilsGetDriverPackageInfo
0x14001b9a8  mov     ebx, eax
0x14001b9aa  xor     eax, eax
0x14001b9ac  test    ebx, ebx
0x14001b9ae  jz      short loc_14001B9D4
0x14001b9b0  lea     edx, [rax+1]
0x14001b9b3  mov     dword ptr [rsp+2E0h+var_2B8], ebx
0x14001b9b7  mov     r8d, edx
0x14001b9ba  mov     qword ptr [rsp+2E0h+var_2C0], rdi
0x14001b9bf  lea     r9, aFailedToBuildL; "Failed to build list of device IDs in '"...
0x14001b9c6  mov     rcx, r15
0x14001b9c9  call    cs:__imp_DevRtlWriteTextLog
0x14001b9cf  jmp     loc_14001BB73
0x14001b9d4  cmp     [rsp+2E0h+var_298], 4
0x14001b9d9  jnz     short loc_14001BA04
0x14001b9db  mov     r8d, [rsp+2E0h+var_294]
0x14001b9e0  lea     r9, [rsp+2E0h+var_29C]
0x14001b9e5  mov     rdx, rdi
0x14001b9e8  mov     rcx, rsi
0x14001b9eb  call    InstallDriver
0x14001b9f0  mov     ebx, eax
0x14001b9f2  test    eax, eax
0x14001b9f4  jnz     loc_14001BB73
0x14001b9fa  mov     r14d, [rsp+2E0h+var_29C]
0x14001b9ff  jmp     loc_14001BB3A
0x14001ba04  cmp     [rsp+2E0h+var_298], 2
0x14001ba09  setz    al
0x14001ba0c  mov     [rsp+2E0h+var_29C], eax
0x14001ba10  call    DevUtilsGetDeviceIdList
0x14001ba15  mov     rsi, rax
0x14001ba18  xor     eax, eax
0x14001ba1a  test    rsi, rsi
0x14001ba1d  jnz     short loc_14001BA2C
0x14001ba1f  call    cs:__imp_GetLastError
0x14001ba25  mov     ebx, eax
0x14001ba27  jmp     loc_14001BB73
0x14001ba2c  cmp     [rsi], ax
0x14001ba2f  jz      loc_14001BB1D
0x14001ba35  mov     r8d, 1; ulFlags
0x14001ba3b  lea     rcx, [rsp+2E0h+pdnDevInst]; pdnDevInst
0x14001ba40  mov     rdx, rsi; pDeviceID
0x14001ba43  call    cs:__imp_CM_Locate_DevNodeW
0x14001ba49  xor     ecx, ecx
0x14001ba4b  test    eax, eax
0x14001ba4d  jnz     loc_14001BB00
0x14001ba53  mov     rax, [rsp+2E0h+var_288]
0x14001ba58  mov     ecx, [rsp+2E0h+pdnDevInst]; dnDevInst
0x14001ba5c  test    rax, rax
0x14001ba5f  jnz     short loc_14001BA79
0x14001ba61  mov     edx, [rsp+2E0h+var_29C]
0x14001ba65  mov     r8, r12
0x14001ba68  call    DeviceMatchesDeviceId
0x14001ba6d  xor     ecx, ecx
0x14001ba6f  test    eax, eax
0x14001ba71  jz      loc_14001BB00
0x14001ba77  jmp     short loc_14001BAB0
0x14001ba79  lea     r8, [rbp+1E0h+var_260]
0x14001ba7d  mov     rdx, rax
0x14001ba80  call    PnpUtilsDriverUpdateAppliesToDevNode
0x14001ba85  xor     ecx, ecx
0x14001ba87  test    eax, eax
0x14001ba89  jz      short loc_14001BB00
0x14001ba8b  lea     rax, [rbp+1E0h+var_260]
0x14001ba8f  lea     edx, [rcx+1]
0x14001ba92  mov     [rsp+2E0h+var_2B8], rax
0x14001ba97  lea     r8d, [rcx+4]
0x14001ba9b  mov     qword ptr [rsp+2E0h+var_2C0], rsi
0x14001baa0  lea     r9, aInstallingDevi; "Installing device '%ws' due to match on"...
0x14001baa7  mov     rcx, r15
0x14001baaa  call    cs:__imp_DevRtlWriteTextLog
0x14001bab0  mov     r9, [rsp+2E0h+var_280]
0x14001bab5  lea     rax, [rsp+2E0h+var_290]
0x14001baba  mov     ecx, [rsp+2E0h+pdnDevInst]; int
0x14001babe  mov     r8, rdi
0x14001bac1  mov     [rsp+2E0h+var_2A8], r15; unsigned __int64
0x14001bac6  mov     rdx, rsi; int
0x14001bac9  mov     [rsp+2E0h+var_2B0], rax; __int64
0x14001bace  mov     rax, [rsp+2E0h+var_288]
0x14001bad3  mov     [rsp+2E0h+var_2B8], rax; struct _DRVUTILS_UPDATE_INFO *
0x14001bad8  mov     eax, [rsp+2E0h+var_294]
0x14001badc  mov     [rsp+2E0h+var_2C0], eax; int
0x14001bae0  call    InstallDeviceDriverUpdate
0x14001bae5  xor     ecx, ecx
0x14001bae7  mov     ebx, eax
0x14001bae9  cmp     eax, 0E000020Bh
0x14001baee  jnz     short loc_14001BAF4
0x14001baf0  mov     ebx, ecx
0x14001baf2  jmp     short loc_14001BB00
0x14001baf4  test    eax, eax
0x14001baf6  jnz     short loc_14001BB73
0x14001baf8  or      r14d, dword ptr [rsp+2E0h+var_290]
0x14001bafd  inc     r13d
0x14001bb00  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bb04  inc     rax
0x14001bb07  cmp     [rsi+rax*2], cx
0x14001bb0b  jnz     short loc_14001BB04
0x14001bb0d  lea     rsi, [rsi+rax*2]
0x14001bb11  xor     eax, eax
0x14001bb13  add     rsi, 2
0x14001bb17  jnz     loc_14001BA2C
0x14001bb1d  test    r13d, r13d
0x14001bb20  jnz     short loc_14001BB3A
0x14001bb22  lea     r9, aNoDevicesNeedD; "No devices need driver update."
0x14001bb29  mov     rcx, r15
0x14001bb2c  lea     edx, [r13+1]
0x14001bb30  lea     r8d, [r13+4]
0x14001bb34  call    cs:__imp_DevRtlWriteTextLog
0x14001bb3a  or      dword ptr [rdi+630h], 2
0x14001bb41  test    r14d, r14d
0x14001bb44  jz      short loc_14001BB66
0x14001bb46  mov     edx, 1
0x14001bb4b  lea     r9, aDriverUpdateNe; "Driver update needs reboot."
0x14001bb52  mov     rcx, r15
0x14001bb55  lea     r8d, [rdx+3]
0x14001bb59  call    cs:__imp_DevRtlWriteTextLog
0x14001bb5f  or      dword ptr [rdi+630h], 4
0x14001bb66  mov     rax, [rsp+2E0h+var_278]
0x14001bb6b  test    rax, rax
0x14001bb6e  jz      short loc_14001BB73
0x14001bb70  mov     [rax], r14d
0x14001bb73  mov     rax, [rsp+2E0h+var_270]
0x14001bb78  test    rax, rax
0x14001bb7b  jz      short loc_14001BB80
0x14001bb7d  mov     [rax], r13d
0x14001bb80  test    r12, r12
0x14001bb83  jz      short loc_14001BB8D
0x14001bb85  mov     rcx, r12
0x14001bb88  call    pSetupStringTableDestroy
0x14001bb8d  lea     r9, aInstallDriverU; "{Install Driver Update - exit(0x%08X)}"
0x14001bb94  mov     [rsp+2E0h+var_2C0], ebx
0x14001bb98  mov     edx, 1
0x14001bb9d  mov     r8d, 50004h
0x14001bba3  mov     rcx, r15
0x14001bba6  call    cs:__imp_DevRtlWriteTextLog
0x14001bbac  mov     eax, ebx
0x14001bbae  mov     rcx, [rbp+1E0h+var_50]
0x14001bbb5  xor     rcx, rsp; StackCookie
0x14001bbb8  call    __security_check_cookie
0x14001bbbd  add     rsp, 2A8h
0x14001bbc4  pop     r15
0x14001bbc6  pop     r14
0x14001bbc8  pop     r13
0x14001bbca  pop     r12
0x14001bbcc  pop     rdi
0x14001bbcd  pop     rsi
0x14001bbce  pop     rbx
0x14001bbcf  pop     rbp
0x14001bbd0  retn
```
