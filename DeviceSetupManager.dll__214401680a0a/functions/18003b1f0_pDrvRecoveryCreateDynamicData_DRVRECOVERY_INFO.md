# pDrvRecoveryCreateDynamicData(_DRVRECOVERY_INFO *)

- ea: `0x18003b1f0`
- end: `0x18003b3ed`
- name: `?pDrvRecoveryCreateDynamicData@@YAHPEAU_DRVRECOVERY_INFO@@@Z`
- size: `509`
- prototype: `_BOOL8 __fastcall(struct _DRVRECOVERY_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003b940`

## callees

- `0x18001af70`
- `0x18001ba48`
- `0x180037354`
- `0x18003b1f0`
- `0x18003de08`
- `0x18003df84`
- `0x1800403e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b308`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b24a`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b337`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b3b3`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b24a`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b337`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003b3b3`
- `drvstore!DriverStoreFindW` at `0x18003b2b3`
- `drvstore!DriverStoreFindW` at `0x18003b2b3`

## pseudocode

```c
_BOOL8 __fastcall pDrvRecoveryCreateDynamicData(struct _DRVRECOVERY_INFO *a1)
{
  __int64 v2; // rcx
  __int64 UpdateInfo; // rax
  DWORD v4; // ebx
  _WORD *i; // rbx
  const wchar_t *v6; // rax
  DWORD LastError; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v12; // [rsp+28h] [rbp-510h]
  __int128 v13; // [rsp+40h] [rbp-4F8h] BYREF
  _BYTE v14[172]; // [rsp+50h] [rbp-4E8h] BYREF
  __int16 v15; // [rsp+FCh] [rbp-43Ch] BYREF
  WCHAR v16[264]; // [rsp+310h] [rbp-228h] BYREF

  memset_0(v14, 0, 0x2B8u);
  v2 = *((_QWORD *)a1 + 70);
  v13 = 0;
  DevRtlWriteTextLog(v2, 512, 131076, "{Identify Recovery Targets}");
  UpdateInfo = DrvUtilsCreateUpdateInfo();
  *((_QWORD *)a1 + 67) = UpdateInfo;
  if ( UpdateInfo )
  {
    for ( i = (_WORD *)((char *)a1 + 690); *i; i += v8 + 1 )
    {
      if ( (unsigned int)DriverStoreFindW(*((_QWORD *)a1 + 1), i, 0xFFFF, 0, 2, v16, 260, v14)
        && DrvUtilsAppendUpdateInfo(*((_QWORD *)a1 + 1), *((_DWORD **)a1 + 67), v16) )
      {
        v6 = (const wchar_t *)&v15;
        if ( !v15 )
          v6 = L"Unpublished";
        DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Driver package: %ws (%ws)", i, v6);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError != 1168 )
        {
          LODWORD(v12) = LastError;
          DevRtlWriteTextLog(
            *((_QWORD *)a1 + 70),
            512,
            2,
            "Unable to add driver package %ws to recovery data. Error = 0x%08X",
            i,
            v12);
        }
      }
      v8 = -1;
      do
        ++v8;
      while ( i[v8] );
    }
    v9 = pSetupStringTableInitializeEx();
    *((_QWORD *)a1 + 68) = v9;
    if ( !v9 )
    {
      v4 = 8;
      goto LABEL_19;
    }
    *(_QWORD *)&v13 = a1;
    if ( (unsigned int)DrvRecoveryEnumImpactedDevices(a1, v10, &pDrvRecoveryEnumImpactedDeviceCallback, &v13) )
    {
      v4 = DWORD2(v13);
      goto LABEL_19;
    }
  }
  v4 = GetLastError();
LABEL_19:
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 262148, "{Identify Recovery Targets - exit(0x%08X)}", v4);
  SetLastError(v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x18003b1f0  mov     [rsp+arg_8], rbx
0x18003b1f5  mov     [rsp+arg_10], rsi
0x18003b1fa  push    rdi
0x18003b1fb  sub     rsp, 530h
0x18003b202  mov     rax, cs:__security_cookie
0x18003b209  xor     rax, rsp
0x18003b20c  mov     [rsp+538h+var_18], rax
0x18003b214  mov     rdi, rcx
0x18003b217  xor     edx, edx; Val
0x18003b219  lea     rcx, [rsp+538h+var_4E8]; void *
0x18003b21e  mov     r8d, 2B8h; Size
0x18003b224  call    memset_0
0x18003b229  mov     rcx, [rdi+230h]
0x18003b230  lea     r9, aIdentifyRecove; "{Identify Recovery Targets}"
0x18003b237  xorps   xmm0, xmm0
0x18003b23a  mov     edx, 200h
0x18003b23f  mov     r8d, 20004h
0x18003b245  movups  [rsp+538h+var_4F8], xmm0
0x18003b24a  call    cs:__imp_DevRtlWriteTextLog
0x18003b250  call    DrvUtilsCreateUpdateInfo
0x18003b255  xor     esi, esi
0x18003b257  mov     [rdi+218h], rax
0x18003b25e  test    rax, rax
0x18003b261  jnz     short loc_18003B270
0x18003b263  call    cs:__imp_GetLastError
0x18003b269  mov     ebx, eax
0x18003b26b  jmp     loc_18003B396
0x18003b270  lea     rbx, [rdi+2B2h]
0x18003b277  jmp     loc_18003B352
0x18003b27c  mov     rcx, [rdi+8]
0x18003b280  lea     rax, [rsp+538h+var_4E8]
0x18003b285  mov     [rsp+538h+var_500], rax
0x18003b28a  mov     r8d, 0FFFFh
0x18003b290  lea     rax, [rsp+538h+var_228]
0x18003b298  mov     [rsp+538h+var_508], 104h
0x18003b2a0  mov     [rsp+538h+var_510], rax
0x18003b2a5  xor     r9d, r9d
0x18003b2a8  mov     rdx, rbx
0x18003b2ab  mov     dword ptr [rsp+538h+var_518], 2
0x18003b2b3  call    cs:__imp_DriverStoreFindW
0x18003b2b9  test    eax, eax
0x18003b2bb  jz      short loc_18003B308
0x18003b2bd  mov     rdx, [rdi+218h]
0x18003b2c4  lea     r8, [rsp+538h+var_228]
0x18003b2cc  mov     rcx, [rdi+8]
0x18003b2d0  call    DrvUtilsAppendUpdateInfo
0x18003b2d5  test    eax, eax
0x18003b2d7  jz      short loc_18003B308
0x18003b2d9  cmp     [rsp+538h+var_43C], si
0x18003b2e1  lea     rax, [rsp+538h+var_43C]
0x18003b2e9  lea     rcx, aUnpublished; "Unpublished"
0x18003b2f0  mov     r8d, 4
0x18003b2f6  cmovz   rax, rcx
0x18003b2fa  lea     r9, aDriverPackageW_2; "Driver package: %ws (%ws)"
0x18003b301  mov     [rsp+538h+var_510], rax
0x18003b306  jmp     short loc_18003B326
0x18003b308  call    cs:__imp_GetLastError
0x18003b30e  cmp     eax, 490h
0x18003b313  jz      short loc_18003B33D
0x18003b315  mov     dword ptr [rsp+538h+var_510], eax
0x18003b319  lea     r9, aUnableToAddDri; "Unable to add driver package %ws to rec"...
0x18003b320  mov     r8d, 2
0x18003b326  mov     rcx, [rdi+230h]
0x18003b32d  mov     edx, 200h
0x18003b332  mov     [rsp+538h+var_518], rbx
0x18003b337  call    cs:__imp_DevRtlWriteTextLog
0x18003b33d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b341  inc     rax
0x18003b344  cmp     [rbx+rax*2], si
0x18003b348  jnz     short loc_18003B341
0x18003b34a  lea     rbx, [rbx+rax*2]
0x18003b34e  add     rbx, 2
0x18003b352  cmp     [rbx], si
0x18003b355  jnz     loc_18003B27C
0x18003b35b  call    pSetupStringTableInitializeEx
0x18003b360  mov     [rdi+220h], rax
0x18003b367  test    rax, rax
0x18003b36a  jnz     short loc_18003B371
0x18003b36c  lea     ebx, [rax+8]
0x18003b36f  jmp     short loc_18003B396
0x18003b371  lea     r9, [rsp+538h+var_4F8]
0x18003b376  mov     qword ptr [rsp+538h+var_4F8], rdi
0x18003b37b  lea     r8, ?pDrvRecoveryEnumImpactedDeviceCallback@@YAHPEBGW4_DRVRECOVERY_DEVICE_FLAG@@_J@Z; pDrvRecoveryEnumImpactedDeviceCallback(ushort const *,_DRVRECOVERY_DEVICE_FLAG,__int64)
0x18003b382  mov     rcx, rdi
0x18003b385  call    ?DrvRecoveryEnumImpactedDevices@@YAHPEAU_DRVRECOVERY_INFO@@W4_DRVRECOVERY_ENUM_IMPACTED_DEVICE_FLAG@@P6AHPEBGW4_DRVRECOVERY_DEVICE_FLAG@@_J@Z4@Z; DrvRecoveryEnumImpactedDevices(_DRVRECOVERY_INFO *,_DRVRECOVERY_ENUM_IMPACTED_DEVICE_FLAG,int (*)(ushort const *,_DRVRECOVERY_DEVICE_FLAG,__int64),__int64)
0x18003b38a  test    eax, eax
0x18003b38c  jz      loc_18003B263
0x18003b392  mov     ebx, dword ptr [rsp+538h+var_4F8+8]
0x18003b396  mov     rcx, [rdi+230h]
0x18003b39d  lea     r9, aIdentifyRecove_0; "{Identify Recovery Targets - exit(0x%08"...
0x18003b3a4  mov     edx, 200h
0x18003b3a9  mov     dword ptr [rsp+538h+var_518], ebx
0x18003b3ad  mov     r8d, 40004h
0x18003b3b3  call    cs:__imp_DevRtlWriteTextLog
0x18003b3b9  mov     ecx, ebx; dwErrCode
0x18003b3bb  call    cs:__imp_SetLastError
0x18003b3c1  test    ebx, ebx
0x18003b3c3  mov     eax, esi
0x18003b3c5  setz    al
0x18003b3c8  mov     rcx, [rsp+538h+var_18]
0x18003b3d0  xor     rcx, rsp; StackCookie
0x18003b3d3  call    __security_check_cookie
0x18003b3d8  lea     r11, [rsp+538h+var_8]
0x18003b3e0  mov     rbx, [r11+18h]
0x18003b3e4  mov     rsi, [r11+20h]
0x18003b3e8  mov     rsp, r11
0x18003b3eb  pop     rdi
0x18003b3ec  retn
```
