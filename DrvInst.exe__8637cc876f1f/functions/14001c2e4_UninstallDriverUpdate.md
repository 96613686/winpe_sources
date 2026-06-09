# UninstallDriverUpdate

- ea: `0x14001c2e4`
- end: `0x14001c4bf`
- name: `UninstallDriverUpdate`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001ae4c`

## callees

- `0x140014860`
- `0x14001bd7c`
- `0x14001c2e4`
- `0x140026994`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14001c3e6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14001c3e6`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001c3d2`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14001c3d2`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c33d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c380`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c411`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c47b`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c4a6`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c33d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c380`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c411`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c47b`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001c4a6`

## string_xrefs

- `0x14001c46d`: `Driver update needs reboot.`
- `0x14001c325`: `{Revert Driver Update - %ws}`
- `0x14001c3fa`: `Unable to open device '%ws'. Error = 0x%08X (0x%02X)`
- `0x14001c48d`: `{Revert Driver Update - exit(0x%08X)}`

## pseudocode

```c
__int64 __fastcall UninstallDriverUpdate(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, _DWORD *a6, __int64 a7)
{
  __int64 v7; // r14
  int v11; // esi
  int v12; // r12d
  int DriverPackageInfo; // eax
  unsigned int v14; // ebx
  __int64 v15; // r15
  __int64 i; // rdi
  CONFIGRET v17; // eax
  __int64 v19; // [rsp+28h] [rbp-30h]
  __int64 v20; // [rsp+30h] [rbp-28h]
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-18h] BYREF
  int v22[5]; // [rsp+44h] [rbp-14h] BYREF
  int v24; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+58h]
  int v26; // [rsp+B8h] [rbp+60h]

  v26 = a4;
  v25 = a3;
  v7 = a7;
  pdnDevInst = 0;
  v22[0] = 0;
  v24 = 0;
  a5 = 0;
  v11 = 0;
  v12 = 0;
  DevRtlWriteTextLog(a7, 1, 196612, "{Revert Driver Update - %ws}", a2);
  DriverPackageInfo = DrvUtilsGetDriverPackageInfo(0, a2, 9, 0, &v24);
  v14 = DriverPackageInfo;
  if ( DriverPackageInfo )
  {
    DevRtlWriteTextLog(v7, 1, 1, "Failed to get info for driver package '%ws'. Error = 0x%08X", a2, DriverPackageInfo);
    goto LABEL_16;
  }
  if ( v24 == 4 )
  {
    v14 = UninstallDriver(a1, a2, a4, &a5);
    if ( v14 )
      goto LABEL_16;
    v11 = a5;
  }
  else
  {
    v15 = a2 + 1600;
    for ( i = *(_QWORD *)(a2 + 1600); i != v15; i = *(_QWORD *)i )
    {
      v17 = CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)(i + 16), 1u);
      if ( v17 )
      {
        LODWORD(v20) = v17;
        LODWORD(v19) = CM_MapCrToWin32Err(v17, 0xE000020B);
        DevRtlWriteTextLog(v7, 1, 2, "Unable to open device '%ws'. Error = 0x%08X (0x%02X)", i + 16, v19, v20);
      }
      else
      {
        v14 = RevertDeviceDriverUpdate(a1, pdnDevInst, i, v25, v26, v22, v7);
        if ( v14 )
        {
          v14 = 0;
        }
        else
        {
          v11 |= v22[0];
          ++v12;
        }
      }
    }
  }
  if ( v11 )
    DevRtlWriteTextLog(v7, 1, 4, "Driver update needs reboot.");
LABEL_16:
  if ( a6 )
    *a6 = v12;
  DevRtlWriteTextLog(v7, 1, 327684, "{Revert Driver Update - exit(0x%08X)}", v14);
  return v14;
}

```

## disassembly

```asm
0x14001c2e4  mov     r11, rsp
0x14001c2e7  mov     [r11+20h], r9d
0x14001c2eb  mov     [r11+18h], r8
0x14001c2ef  mov     [r11+8], rcx
0x14001c2f3  push    rbp
0x14001c2f4  push    rbx
0x14001c2f5  push    rsi
0x14001c2f6  push    rdi
0x14001c2f7  push    r12
0x14001c2f9  push    r13
0x14001c2fb  push    r14
0x14001c2fd  push    r15
0x14001c2ff  mov     rbp, rsp
0x14001c302  sub     rsp, 58h
0x14001c306  mov     r14, [rbp+arg_30]
0x14001c30a  xor     eax, eax
0x14001c30c  mov     r15d, r9d
0x14001c30f  mov     [r11-78h], rdx
0x14001c313  mov     rdi, rdx
0x14001c316  mov     [rbp+pdnDevInst], eax
0x14001c319  mov     r13, rcx
0x14001c31c  mov     [rbp+var_14], eax
0x14001c31f  lea     edx, [rax+1]
0x14001c322  mov     [rbp+arg_8], eax
0x14001c325  lea     r9, aRevertDriverUp_0; "{Revert Driver Update - %ws}"
0x14001c32c  mov     [rbp+arg_20], eax
0x14001c32f  mov     r8d, 30004h
0x14001c335  mov     rcx, r14
0x14001c338  mov     esi, eax
0x14001c33a  mov     r12d, eax
0x14001c33d  call    cs:__imp_DevRtlWriteTextLog
0x14001c343  lea     rax, [rbp+arg_8]
0x14001c347  mov     r8d, 9
0x14001c34d  xor     r9d, r9d
0x14001c350  mov     [rsp+58h+var_38], rax
0x14001c355  mov     rdx, rdi
0x14001c358  xor     ecx, ecx
0x14001c35a  call    DrvUtilsGetDriverPackageInfo
0x14001c35f  mov     ebx, eax
0x14001c361  test    eax, eax
0x14001c363  jz      short loc_14001C38B
0x14001c365  mov     edx, 1
0x14001c36a  mov     dword ptr [rsp+58h+var_30], eax
0x14001c36e  mov     r8d, edx
0x14001c371  mov     [rsp+58h+var_38], rdi
0x14001c376  lea     r9, aFailedToGetInf; "Failed to get info for driver package '"...
0x14001c37d  mov     rcx, r14
0x14001c380  call    cs:__imp_DevRtlWriteTextLog
0x14001c386  jmp     loc_14001C481
0x14001c38b  cmp     [rbp+arg_8], 4
0x14001c38f  jnz     short loc_14001C3B5
0x14001c391  lea     r9, [rbp+arg_20]
0x14001c395  mov     r8d, r15d
0x14001c398  mov     rdx, rdi
0x14001c39b  mov     rcx, r13
0x14001c39e  call    UninstallDriver
0x14001c3a3  mov     ebx, eax
0x14001c3a5  test    eax, eax
0x14001c3a7  jnz     loc_14001C481
0x14001c3ad  mov     esi, [rbp+arg_20]
0x14001c3b0  jmp     loc_14001C464
0x14001c3b5  lea     r15, [rdi+640h]
0x14001c3bc  mov     rdi, [r15]
0x14001c3bf  jmp     loc_14001C45B
0x14001c3c4  lea     rdx, [rdi+10h]; pDeviceID
0x14001c3c8  mov     r8d, 1; ulFlags
0x14001c3ce  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x14001c3d2  call    cs:__imp_CM_Locate_DevNodeW
0x14001c3d8  mov     r13d, eax
0x14001c3db  test    eax, eax
0x14001c3dd  jz      short loc_14001C419
0x14001c3df  mov     edx, 0E000020Bh; DefaultErr
0x14001c3e4  mov     ecx, eax; CmReturnCode
0x14001c3e6  call    cs:__imp_CM_MapCrToWin32Err
0x14001c3ec  mov     edx, 1
0x14001c3f1  mov     dword ptr [rsp+58h+var_28], r13d
0x14001c3f6  mov     dword ptr [rsp+58h+var_30], eax
0x14001c3fa  lea     r9, aUnableToOpenDe; "Unable to open device '%ws'. Error = 0x"...
0x14001c401  lea     rax, [rdi+10h]
0x14001c405  mov     rcx, r14
0x14001c408  mov     [rsp+58h+var_38], rax
0x14001c40d  lea     r8d, [rdx+1]
0x14001c411  call    cs:__imp_DevRtlWriteTextLog
0x14001c417  jmp     short loc_14001C458
0x14001c419  mov     r9, [rbp+arg_10]
0x14001c41d  lea     rax, [rbp+var_14]
0x14001c421  mov     edx, [rbp+pdnDevInst]
0x14001c424  mov     r8, rdi
0x14001c427  mov     rcx, [rbp+arg_0]
0x14001c42b  mov     [rsp+58h+var_28], r14
0x14001c430  mov     [rsp+58h+var_30], rax
0x14001c435  mov     eax, [rbp+arg_18]
0x14001c438  mov     dword ptr [rsp+58h+var_38], eax
0x14001c43c  call    RevertDeviceDriverUpdate
0x14001c441  mov     ebx, eax
0x14001c443  cmp     eax, 0E000020Bh
0x14001c448  jnz     short loc_14001C44E
0x14001c44a  xor     ebx, ebx
0x14001c44c  jmp     short loc_14001C458
0x14001c44e  test    eax, eax
0x14001c450  jnz     short loc_14001C44A
0x14001c452  or      esi, [rbp+var_14]
0x14001c455  inc     r12d
0x14001c458  mov     rdi, [rdi]
0x14001c45b  cmp     rdi, r15
0x14001c45e  jnz     loc_14001C3C4
0x14001c464  test    esi, esi
0x14001c466  jz      short loc_14001C481
0x14001c468  mov     edx, 1
0x14001c46d  lea     r9, aDriverUpdateNe; "Driver update needs reboot."
0x14001c474  mov     rcx, r14
0x14001c477  lea     r8d, [rdx+3]
0x14001c47b  call    cs:__imp_DevRtlWriteTextLog
0x14001c481  mov     rax, [rbp+arg_28]
0x14001c485  test    rax, rax
0x14001c488  jz      short loc_14001C48D
0x14001c48a  mov     [rax], r12d
0x14001c48d  lea     r9, aRevertDriverUp; "{Revert Driver Update - exit(0x%08X)}"
0x14001c494  mov     dword ptr [rsp+58h+var_38], ebx
0x14001c498  mov     edx, 1
0x14001c49d  mov     r8d, 50004h
0x14001c4a3  mov     rcx, r14
0x14001c4a6  call    cs:__imp_DevRtlWriteTextLog
0x14001c4ac  mov     eax, ebx
0x14001c4ae  add     rsp, 58h
0x14001c4b2  pop     r15
0x14001c4b4  pop     r14
0x14001c4b6  pop     r13
0x14001c4b8  pop     r12
0x14001c4ba  pop     rdi
0x14001c4bb  pop     rsi
0x14001c4bc  pop     rbx
0x14001c4bd  pop     rbp
0x14001c4be  retn
```
