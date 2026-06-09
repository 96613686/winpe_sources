# HandleTaskRequest(TASK_REQUEST const *)

- ea: `0x140017d70`
- end: `0x14001800b`
- name: `?HandleTaskRequest@@YAHPEBUTASK_REQUEST@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, service_task`

## callers

- `0x140002b98`

## callees

- `0x14000a440`
- `0x14000b354`
- `0x14000b648`
- `0x140017d70`
- `0x140018014`
- `0x140018068`
- `0x1400180c8`
- `0x1400181e0`
- `0x140018288`
- `0x14001832c`
- `0x1400183b4`
- `0x1400185d0`
- `0x140018750`
- `0x1400188b0`
- `0x1400189ac`
- `0x140018a8c`
- `0x140018cfc`
- `0x140018ddc`
- `0x140018ebc`
- `0x140018fbc`
- `0x14001913c`
- `0x140019310`
- `0x140019498`
- `0x1400196d8`
- `0x140019804`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140017e74`
- `KERNEL32!LocalFree` at `0x140017e74`
- `KERNEL32!SleepEx` at `0x140017e6b`
- `KERNEL32!SleepEx` at `0x140017ec2`
- `KERNEL32!SleepEx` at `0x140017e6b`
- `KERNEL32!SleepEx` at `0x140017ec2`
- `KERNEL32!SetLastError` at `0x140017f57`
- `KERNEL32!SetLastError` at `0x140017f57`
- `KERNEL32!GetLastError` at `0x140017fab`
- `KERNEL32!GetLastError` at `0x140017fab`

## pseudocode

```c
__int64 __fastcall HandleTaskRequest(struct _GUID *a1)
{
  unsigned int v1; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  struct _SU_POOL_OBJECT *v11; // rsi
  int v12; // ebx
  int Pool; // eax
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  DWORD LastError; // eax
  struct _SU_POOL_OBJECT *v25; // [rsp+20h] [rbp-29h] BYREF
  struct _GUID v26; // [rsp+28h] [rbp-21h] BYREF
  struct _GUID v27; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v28[2]; // [rsp+48h] [rbp-1h] BYREF
  DWORD v29; // [rsp+58h] [rbp+Fh]
  __int128 v30; // [rsp+5Ch] [rbp+13h]
  int v31; // [rsp+6Ch] [rbp+23h]

  v1 = *(_DWORD *)a1->Data4;
  LODWORD(v25) = 0;
  v27 = GUID_NULL;
  v26 = GUID_NULL;
  if ( v1 > 9 )
  {
    v15 = v1 - 10;
    if ( !v15 )
    {
      v10 = HandleRenameSpaceRequest((const struct TASK_RENAME_SPACE_REQUEST *)a1);
      goto LABEL_53;
    }
    v16 = v15 - 1;
    if ( !v16 )
    {
      v10 = HandleReformatSpaceRequest((const struct TASK_REFORMAT_SPACE_REQUEST *)a1);
      goto LABEL_53;
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      v10 = HandleAttachSpaceRequest((const struct TASK_ATTACH_SPACE_REQUEST *)a1);
      goto LABEL_53;
    }
    v18 = v17 - 1;
    if ( !v18 )
    {
      v10 = HandleDetachSpaceRequest((const struct TASK_DETACH_SPACE_REQUEST *)a1);
      goto LABEL_53;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        v10 = HandleRemoveDriveRequest((const struct TASK_REMOVE_DRIVE_REQUEST *)a1);
        goto LABEL_53;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v10 = HandleEvacuateDriveRequest((const struct TASK_EVACUATE_DRIVE_REQUEST *)a1);
        goto LABEL_53;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v10 = HandleRenameDriveRequest((const struct TASK_RENAME_DRIVE_REQUEST *)a1);
        goto LABEL_53;
      }
      if ( v22 == 1 )
      {
        v10 = HandleResetDriveRequest((const struct TASK_RESET_DRIVE_REQUEST *)a1);
        goto LABEL_53;
      }
      goto LABEL_43;
    }
    v14 = HandleAddDrivesRequest((const struct TASK_ADD_DRIVES_REQUEST *)a1, (unsigned int *)&v25);
LABEL_29:
    if ( v14 )
    {
      v10 = IssueDriveFailuresResult((unsigned int)v25);
      goto LABEL_53;
    }
    goto LABEL_55;
  }
  if ( v1 == 9 )
  {
    v10 = HandleDestroySpaceRequest((const struct TASK_DESTROY_SPACE_REQUEST *)a1);
    goto LABEL_53;
  }
  if ( !v1 )
  {
    v10 = HandleOfflineDiskRequest((const struct TASK_OFFLINE_DISK_REQUEST *)a1);
    goto LABEL_53;
  }
  v3 = v1 - 1;
  if ( !v3 )
  {
    v10 = HandleOnlineDiskRequest((const struct TASK_ONLINE_DISK_REQUEST *)a1);
    goto LABEL_53;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    if ( !HandleCreatePoolRequest((const struct TASK_CREATE_POOL_REQUEST *)a1, &v27, (unsigned int *)&v25) )
      goto LABEL_55;
    v14 = IssueObjectIdentifierResult(&v27);
    goto LABEL_29;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = HandleDestroyPoolRequest((const struct TASK_DESTROY_POOL_REQUEST *)a1);
    goto LABEL_53;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
      v10 = HandleRenamePoolRequest((const struct TASK_RENAME_POOL_REQUEST *)a1);
      goto LABEL_53;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v10 = HandleStopPoolOptimizationRequest((const struct TASK_STOP_POOL_OPTIMIZATION_REQUEST *)a1);
      goto LABEL_53;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        if ( (unsigned int)HandleCreateSpaceRequest((const struct TASK_CREATE_SPACE_REQUEST *)a1, &v26) )
        {
          v10 = IssueObjectIdentifierResult(&v26);
LABEL_53:
          v12 = v10;
          goto LABEL_54;
        }
LABEL_55:
        LastError = GetLastError();
        goto LABEL_56;
      }
LABEL_43:
      SetLastError(0x16u);
      goto LABEL_55;
    }
    v11 = 0;
    v25 = 0;
    v12 = IssueProgressStringResult(32905);
    if ( v12 )
    {
      Pool = SiGetPool(a1 + 1, 0, &v25);
      v11 = v25;
      if ( Pool && (unsigned int)SuUpgradePool(v25) )
        SleepEx(0x3E8u, 0);
      else
        v12 = 0;
    }
    LocalFree(v11);
  }
  else
  {
    v12 = IssueProgressStringResult(32904);
    if ( v12 )
    {
      if ( (unsigned int)SuRebalancePool(a1 + 1) )
        SleepEx(0x3E8u, 0);
      else
        v12 = 0;
    }
  }
LABEL_54:
  LastError = 0;
  if ( !v12 )
    goto LABEL_55;
LABEL_56:
  v29 = LastError;
  v28[1] = 0;
  v31 = 0;
  v28[0] = 40;
  v30 = *(_OWORD *)&qword_140022CE0[2 * (unsigned int)(LastProgressStringIdentifier - 32880)];
  return IssueTaskResult((struct TASK_PAYLOAD *)v28);
}

```

## disassembly

```asm
0x140017d70  push    rbp
0x140017d72  push    rbx
0x140017d73  push    rsi
0x140017d74  push    rdi
0x140017d75  lea     rbp, [rsp-3Fh]
0x140017d7a  sub     rsp, 88h
0x140017d81  mov     rax, cs:__security_cookie
0x140017d88  xor     rax, rsp
0x140017d8b  mov     [rbp+57h+var_30], rax
0x140017d8f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140017d96  mov     eax, [rcx+8]
0x140017d99  mov     rdi, rcx
0x140017d9c  mov     dword ptr [rbp+57h+var_80], 0
0x140017da3  movdqu  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x140017da8  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x140017dad  cmp     eax, 9
0x140017db0  ja      loc_140017F25
0x140017db6  jz      loc_140017F1E
0x140017dbc  test    eax, eax
0x140017dbe  jz      loc_140017F14
0x140017dc4  sub     eax, 1
0x140017dc7  jz      loc_140017F0A
0x140017dcd  sub     eax, 1
0x140017dd0  jz      loc_140017ED7
0x140017dd6  sub     eax, 1
0x140017dd9  jz      loc_140017ECD
0x140017ddf  sub     eax, 1
0x140017de2  jz      loc_140017E93
0x140017de8  sub     eax, 1
0x140017deb  jz      loc_140017E89
0x140017df1  sub     eax, 1
0x140017df4  jz      loc_140017E7F
0x140017dfa  sub     eax, 1
0x140017dfd  jz      short loc_140017E27
0x140017dff  cmp     eax, 1
0x140017e02  jnz     loc_140017F52
0x140017e08  lea     rdx, [rbp+57h+var_78]; struct _GUID *
0x140017e0c  call    ?HandleCreateSpaceRequest@@YAHPEBUTASK_CREATE_SPACE_REQUEST@@PEAU_GUID@@@Z; HandleCreateSpaceRequest(TASK_CREATE_SPACE_REQUEST const *,_GUID *)
0x140017e11  test    eax, eax
0x140017e13  jz      loc_140017FAB
0x140017e19  lea     rcx, [rbp+57h+var_78]
0x140017e1d  call    IssueObjectIdentifierResult
0x140017e22  jmp     loc_140017FA3
0x140017e27  xor     esi, esi
0x140017e29  mov     ecx, 8089h
0x140017e2e  mov     [rbp+57h+var_80], rsi
0x140017e32  call    IssueProgressStringResult
0x140017e37  mov     ebx, eax
0x140017e39  test    eax, eax
0x140017e3b  jz      short loc_140017E71
0x140017e3d  lea     rcx, [rdi+10h]; struct _GUID *
0x140017e41  xor     edx, edx; unsigned int
0x140017e43  lea     r8, [rbp+57h+var_80]; struct _SU_POOL_OBJECT **
0x140017e47  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x140017e4c  mov     rsi, [rbp+57h+var_80]
0x140017e50  test    eax, eax
0x140017e52  jnz     short loc_140017E58
0x140017e54  xor     ebx, ebx
0x140017e56  jmp     short loc_140017E71
0x140017e58  mov     rcx, rsi; struct _SU_POOL_OBJECT *
0x140017e5b  call    ?SuUpgradePool@@YAHPEAU_SU_POOL_OBJECT@@@Z; SuUpgradePool(_SU_POOL_OBJECT *)
0x140017e60  test    eax, eax
0x140017e62  jz      short loc_140017E54
0x140017e64  xor     edx, edx; bAlertable
0x140017e66  mov     ecx, 3E8h; dwMilliseconds
0x140017e6b  call    cs:__imp_SleepEx
0x140017e71  mov     rcx, rsi; hMem
0x140017e74  call    cs:__imp_LocalFree
0x140017e7a  jmp     loc_140017FA5
0x140017e7f  call    ?HandleStopPoolOptimizationRequest@@YAHPEBUTASK_STOP_POOL_OPTIMIZATION_REQUEST@@@Z; HandleStopPoolOptimizationRequest(TASK_STOP_POOL_OPTIMIZATION_REQUEST const *)
0x140017e84  jmp     loc_140017FA3
0x140017e89  call    ?HandleRenamePoolRequest@@YAHPEBUTASK_RENAME_POOL_REQUEST@@@Z; HandleRenamePoolRequest(TASK_RENAME_POOL_REQUEST const *)
0x140017e8e  jmp     loc_140017FA3
0x140017e93  mov     ecx, 8088h
0x140017e98  call    IssueProgressStringResult
0x140017e9d  mov     ebx, eax
0x140017e9f  test    eax, eax
0x140017ea1  jz      loc_140017FA5
0x140017ea7  lea     rcx, [rdi+10h]; lpInBuffer
0x140017eab  call    ?SuRebalancePool@@YAHPEAU_GUID@@@Z; SuRebalancePool(_GUID *)
0x140017eb0  test    eax, eax
0x140017eb2  jnz     short loc_140017EBB
0x140017eb4  xor     ebx, ebx
0x140017eb6  jmp     loc_140017FA5
0x140017ebb  xor     edx, edx; bAlertable
0x140017ebd  mov     ecx, 3E8h; dwMilliseconds
0x140017ec2  call    cs:__imp_SleepEx
0x140017ec8  jmp     loc_140017FA5
0x140017ecd  call    ?HandleDestroyPoolRequest@@YAHPEBUTASK_DESTROY_POOL_REQUEST@@@Z; HandleDestroyPoolRequest(TASK_DESTROY_POOL_REQUEST const *)
0x140017ed2  jmp     loc_140017FA3
0x140017ed7  lea     r8, [rbp+57h+var_80]; unsigned int *
0x140017edb  lea     rdx, [rbp+57h+var_68]; struct _GUID *
0x140017edf  call    ?HandleCreatePoolRequest@@YAHPEBUTASK_CREATE_POOL_REQUEST@@PEAU_GUID@@PEAI@Z; HandleCreatePoolRequest(TASK_CREATE_POOL_REQUEST const *,_GUID *,uint *)
0x140017ee4  test    eax, eax
0x140017ee6  jz      loc_140017FAB
0x140017eec  lea     rcx, [rbp+57h+var_68]
0x140017ef0  call    IssueObjectIdentifierResult
0x140017ef5  test    eax, eax
0x140017ef7  jz      loc_140017FAB
0x140017efd  mov     ecx, dword ptr [rbp+57h+var_80]
0x140017f00  call    IssueDriveFailuresResult
0x140017f05  jmp     loc_140017FA3
0x140017f0a  call    ?HandleOnlineDiskRequest@@YAHPEBUTASK_ONLINE_DISK_REQUEST@@@Z; HandleOnlineDiskRequest(TASK_ONLINE_DISK_REQUEST const *)
0x140017f0f  jmp     loc_140017FA3
0x140017f14  call    ?HandleOfflineDiskRequest@@YAHPEBUTASK_OFFLINE_DISK_REQUEST@@@Z; HandleOfflineDiskRequest(TASK_OFFLINE_DISK_REQUEST const *)
0x140017f19  jmp     loc_140017FA3
0x140017f1e  call    ?HandleDestroySpaceRequest@@YAHPEBUTASK_DESTROY_SPACE_REQUEST@@@Z; HandleDestroySpaceRequest(TASK_DESTROY_SPACE_REQUEST const *)
0x140017f23  jmp     short loc_140017FA3
0x140017f25  sub     eax, 0Ah
0x140017f28  jz      short loc_140017F9E
0x140017f2a  sub     eax, 1
0x140017f2d  jz      short loc_140017F97
0x140017f2f  sub     eax, 1
0x140017f32  jz      short loc_140017F90
0x140017f34  sub     eax, 1
0x140017f37  jz      short loc_140017F89
0x140017f39  sub     eax, 1
0x140017f3c  jz      short loc_140017F7B
0x140017f3e  sub     eax, 1
0x140017f41  jz      short loc_140017F74
0x140017f43  sub     eax, 1
0x140017f46  jz      short loc_140017F6D
0x140017f48  sub     eax, 1
0x140017f4b  jz      short loc_140017F66
0x140017f4d  cmp     eax, 1
0x140017f50  jz      short loc_140017F5F
0x140017f52  mov     ecx, 16h; dwErrCode
0x140017f57  call    cs:__imp_SetLastError
0x140017f5d  jmp     short loc_140017FAB
0x140017f5f  call    ?HandleResetDriveRequest@@YAHPEBUTASK_RESET_DRIVE_REQUEST@@@Z; HandleResetDriveRequest(TASK_RESET_DRIVE_REQUEST const *)
0x140017f64  jmp     short loc_140017FA3
0x140017f66  call    ?HandleRenameDriveRequest@@YAHPEBUTASK_RENAME_DRIVE_REQUEST@@@Z; HandleRenameDriveRequest(TASK_RENAME_DRIVE_REQUEST const *)
0x140017f6b  jmp     short loc_140017FA3
0x140017f6d  call    ?HandleEvacuateDriveRequest@@YAHPEBUTASK_EVACUATE_DRIVE_REQUEST@@@Z; HandleEvacuateDriveRequest(TASK_EVACUATE_DRIVE_REQUEST const *)
0x140017f72  jmp     short loc_140017FA3
0x140017f74  call    ?HandleRemoveDriveRequest@@YAHPEBUTASK_REMOVE_DRIVE_REQUEST@@@Z; HandleRemoveDriveRequest(TASK_REMOVE_DRIVE_REQUEST const *)
0x140017f79  jmp     short loc_140017FA3
0x140017f7b  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x140017f7f  call    ?HandleAddDrivesRequest@@YAHPEBUTASK_ADD_DRIVES_REQUEST@@PEAI@Z; HandleAddDrivesRequest(TASK_ADD_DRIVES_REQUEST const *,uint *)
0x140017f84  jmp     loc_140017EF5
0x140017f89  call    ?HandleDetachSpaceRequest@@YAHPEBUTASK_DETACH_SPACE_REQUEST@@@Z; HandleDetachSpaceRequest(TASK_DETACH_SPACE_REQUEST const *)
0x140017f8e  jmp     short loc_140017FA3
0x140017f90  call    ?HandleAttachSpaceRequest@@YAHPEBUTASK_ATTACH_SPACE_REQUEST@@@Z; HandleAttachSpaceRequest(TASK_ATTACH_SPACE_REQUEST const *)
0x140017f95  jmp     short loc_140017FA3
0x140017f97  call    ?HandleReformatSpaceRequest@@YAHPEBUTASK_REFORMAT_SPACE_REQUEST@@@Z; HandleReformatSpaceRequest(TASK_REFORMAT_SPACE_REQUEST const *)
0x140017f9c  jmp     short loc_140017FA3
0x140017f9e  call    ?HandleRenameSpaceRequest@@YAHPEBUTASK_RENAME_SPACE_REQUEST@@@Z; HandleRenameSpaceRequest(TASK_RENAME_SPACE_REQUEST const *)
0x140017fa3  mov     ebx, eax
0x140017fa5  xor     eax, eax
0x140017fa7  test    ebx, ebx
0x140017fa9  jnz     short loc_140017FB1
0x140017fab  call    cs:__imp_GetLastError
0x140017fb1  mov     ecx, cs:LastProgressStringIdentifier
0x140017fb7  add     ecx, 0FFFF7F90h
0x140017fbd  mov     [rbp+57h+var_48], eax
0x140017fc0  add     rcx, rcx
0x140017fc3  mov     [rbp+57h+var_50], 0
0x140017fcb  lea     rax, qword_140022CE0
0x140017fd2  mov     [rbp+57h+var_34], 0
0x140017fd9  mov     [rbp+57h+var_58], 28h ; '('
0x140017fe1  movups  xmm0, xmmword ptr [rax+rcx*8]
0x140017fe5  lea     rcx, [rbp+57h+var_58]; struct TASK_PAYLOAD *
0x140017fe9  movdqu  [rbp+57h+var_44], xmm0
0x140017fee  call    IssueTaskResult
0x140017ff3  mov     rcx, [rbp+57h+var_30]
0x140017ff7  xor     rcx, rsp; StackCookie
0x140017ffa  call    __security_check_cookie
0x140017fff  add     rsp, 88h
0x140018006  pop     rdi
0x140018007  pop     rsi
0x140018008  pop     rbx
0x140018009  pop     rbp
0x14001800a  retn
```
