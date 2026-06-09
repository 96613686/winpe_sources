# PnpUtilsUpdateDeviceGroupUpdateStatus

- ea: `0x14002c774`
- end: `0x14002c94b`
- name: `PnpUtilsUpdateDeviceGroupUpdateStatus`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x14001ae4c`

## callees

- `0x1400271b8`
- `0x140029a3c`
- `0x14002c774`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c91a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002c91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c906`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c930`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c930`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14002c8d1`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14002c8d1`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14002c7dc`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14002c7dc`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x14002c8bc`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x14002c8bc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002c811`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002c811`
- `drvstore!DriverStoreOpenW` at `0x14002c855`
- `drvstore!DriverStoreOpenW` at `0x14002c855`
- `drvstore!DriverStoreClose` at `0x14002c928`
- `drvstore!DriverStoreClose` at `0x14002c928`

## pseudocode

```c
_BOOL8 __fastcall PnpUtilsUpdateDeviceGroupUpdateStatus(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _WORD *DeviceIdList; // rax
  void *v5; // rsi
  DWORD LastError; // ebx
  struct HDRIVERSTORE__ *v7; // rdi
  WCHAR *v8; // r14
  CONFIGRET DevNode_PropertyW; // eax
  DWORD v10; // eax
  __int64 v11; // rax
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-18h] BYREF
  int v14[5]; // [rsp+34h] [rbp-14h] BYREF
  BYTE PropertyBuffer; // [rsp+80h] [rbp+38h] BYREF
  BYTE v16; // [rsp+88h] [rbp+40h] BYREF
  DEVNODE pdnDevInst; // [rsp+90h] [rbp+48h] BYREF
  ULONG PropertyBufferSize; // [rsp+98h] [rbp+50h] BYREF

  v16 = -1;
  pdnDevInst = 0;
  PropertyBufferSize = 0;
  PropertyType = 0;
  PropertyBuffer = 0;
  DeviceIdList = (_WORD *)DevUtilsGetDeviceIdList(a1, a2, a3, a4);
  v5 = DeviceIdList;
  if ( !DeviceIdList )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
  v7 = 0;
  LastError = 0;
  v8 = DeviceIdList;
  if ( *DeviceIdList )
  {
    while ( 1 )
    {
      v14[0] = 1;
      if ( CM_Locate_DevNodeW(&pdnDevInst, v8, 1u) )
        goto LABEL_25;
      PropertyBufferSize = 1;
      DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                            pdnDevInst,
                            &DEVPKEY_Device_DriverInGroup,
                            &PropertyType,
                            &PropertyBuffer,
                            &PropertyBufferSize,
                            0);
      if ( DevNode_PropertyW == 37 )
        goto LABEL_25;
      if ( !DevNode_PropertyW && PropertyType == 17 && PropertyBufferSize == 1 )
        break;
      if ( !LastError )
      {
        if ( DevNode_PropertyW )
          goto LABEL_21;
        LastError = 13;
      }
LABEL_25:
      v11 = -1;
      do
        ++v11;
      while ( v8[v11] );
      v8 += v11 + 1;
      if ( !*v8 )
        goto LABEL_30;
    }
    if ( !PropertyBuffer )
      goto LABEL_25;
    if ( !v7 )
    {
      v7 = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
      if ( !v7 )
      {
        LastError = GetLastError();
        goto LABEL_30;
      }
    }
    if ( PnpUtilsDeviceRequiresGroupUpdate(v7, pdnDevInst, v14) )
    {
      if ( v14[0] )
        DevNode_PropertyW = CM_Set_DevNode_PropertyW(
                              pdnDevInst,
                              &DEVPKEY_Device_DriverNeedsGroupUpdate,
                              0x11u,
                              &v16,
                              1u,
                              0);
      else
        DevNode_PropertyW = CM_Set_DevNode_PropertyW(pdnDevInst, &DEVPKEY_Device_DriverNeedsGroupUpdate, 0, 0, 0, 0);
      if ( !DevNode_PropertyW || LastError )
        goto LABEL_25;
LABEL_21:
      v10 = CM_MapCrToWin32Err(DevNode_PropertyW, 0xDu);
    }
    else
    {
      if ( LastError )
        goto LABEL_25;
      v10 = GetLastError();
    }
    LastError = v10;
    goto LABEL_25;
  }
LABEL_30:
  HeapFree(hHeap, 0, v5);
  if ( v7 )
    DriverStoreClose(v7);
LABEL_32:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14002c774  push    rbp
0x14002c776  push    rbx
0x14002c777  push    rsi
0x14002c778  push    rdi
0x14002c779  push    r14
0x14002c77b  push    r15
0x14002c77d  mov     rbp, rsp
0x14002c780  sub     rsp, 48h
0x14002c784  xor     r15d, r15d
0x14002c787  mov     [rbp+arg_8], 0FFh
0x14002c78b  mov     [rbp+pdnDevInst], r15d
0x14002c78f  mov     [rbp+arg_18], r15d
0x14002c793  mov     [rbp+PropertyType], r15d
0x14002c797  mov     [rbp+PropertyBuffer], r15b
0x14002c79b  call    DevUtilsGetDeviceIdList
0x14002c7a0  mov     rsi, rax
0x14002c7a3  test    rax, rax
0x14002c7a6  jnz     short loc_14002C7B5
0x14002c7a8  call    cs:__imp_GetLastError
0x14002c7ae  mov     ebx, eax
0x14002c7b0  jmp     loc_14002C92E
0x14002c7b5  mov     rdi, r15
0x14002c7b8  mov     ebx, r15d
0x14002c7bb  mov     r14, rsi
0x14002c7be  cmp     [rax], r15w
0x14002c7c2  jz      loc_14002C90E
0x14002c7c8  mov     r8d, 1; ulFlags
0x14002c7ce  mov     [rbp+var_14], 1
0x14002c7d5  mov     rdx, r14; pDeviceID
0x14002c7d8  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x14002c7dc  call    cs:__imp_CM_Locate_DevNodeW
0x14002c7e2  test    eax, eax
0x14002c7e4  jnz     loc_14002C8E4
0x14002c7ea  mov     ecx, [rbp+pdnDevInst]; dnDevInst
0x14002c7ed  lea     rax, [rbp+arg_18]
0x14002c7f1  mov     [rsp+48h+ulFlags], r15d; ulFlags
0x14002c7f6  lea     r9, [rbp+PropertyBuffer]; PropertyBuffer
0x14002c7fa  lea     r8, [rbp+PropertyType]; PropertyType
0x14002c7fe  mov     [rsp+48h+PropertyBufferSize], rax; PropertyBufferSize
0x14002c803  lea     rdx, DEVPKEY_Device_DriverInGroup; PropertyKey
0x14002c80a  mov     [rbp+arg_18], 1
0x14002c811  call    cs:__imp_CM_Get_DevNode_PropertyW
0x14002c817  cmp     eax, 25h ; '%'
0x14002c81a  jz      loc_14002C8E4
0x14002c820  test    eax, eax
0x14002c822  jnz     loc_14002C8D9
0x14002c828  cmp     [rbp+PropertyType], 11h
0x14002c82c  jnz     loc_14002C8D9
0x14002c832  cmp     [rbp+arg_18], 1
0x14002c836  jnz     loc_14002C8D9
0x14002c83c  cmp     [rbp+PropertyBuffer], r15b
0x14002c840  jz      loc_14002C8E4
0x14002c846  test    rdi, rdi
0x14002c849  jnz     short loc_14002C867
0x14002c84b  xor     r9d, r9d
0x14002c84e  xor     r8d, r8d
0x14002c851  xor     edx, edx
0x14002c853  xor     ecx, ecx
0x14002c855  call    cs:__imp_DriverStoreOpenW
0x14002c85b  mov     rdi, rax
0x14002c85e  test    rax, rax
0x14002c861  jz      loc_14002C906
0x14002c867  mov     edx, [rbp+pdnDevInst]; dnDevInst
0x14002c86a  lea     r8, [rbp+var_14]; int *
0x14002c86e  mov     rcx, rdi; struct HDRIVERSTORE__ *
0x14002c871  call    ?PnpUtilsDeviceRequiresGroupUpdate@@YAHPEAUHDRIVERSTORE__@@KPEAH@Z; PnpUtilsDeviceRequiresGroupUpdate(HDRIVERSTORE__ *,ulong,int *)
0x14002c876  test    eax, eax
0x14002c878  jnz     short loc_14002C888
0x14002c87a  test    ebx, ebx
0x14002c87c  jnz     short loc_14002C8E4
0x14002c87e  call    cs:__imp_GetLastError
0x14002c884  mov     ebx, eax
0x14002c886  jmp     short loc_14002C8E4
0x14002c888  lea     rdx, DEVPKEY_Device_DriverNeedsGroupUpdate; PropertyKey
0x14002c88f  mov     ecx, [rbp+pdnDevInst]; dnDevInst
0x14002c892  mov     [rsp+48h+ulFlags], r15d; ulFlags
0x14002c897  cmp     [rbp+var_14], r15d
0x14002c89b  jz      short loc_14002C8B1
0x14002c89d  mov     dword ptr [rsp+48h+PropertyBufferSize], 1
0x14002c8a5  lea     r9, [rbp+arg_8]
0x14002c8a9  mov     r8d, 11h
0x14002c8af  jmp     short loc_14002C8BC
0x14002c8b1  xor     r9d, r9d; PropertyBuffer
0x14002c8b4  mov     dword ptr [rsp+48h+PropertyBufferSize], r15d; PropertyBufferSize
0x14002c8b9  xor     r8d, r8d; PropertyType
0x14002c8bc  call    cs:__imp_CM_Set_DevNode_PropertyW
0x14002c8c2  test    eax, eax
0x14002c8c4  jz      short loc_14002C8E4
0x14002c8c6  test    ebx, ebx
0x14002c8c8  jnz     short loc_14002C8E4
0x14002c8ca  mov     edx, 0Dh; DefaultErr
0x14002c8cf  mov     ecx, eax; CmReturnCode
0x14002c8d1  call    cs:__imp_CM_MapCrToWin32Err
0x14002c8d7  jmp     short loc_14002C884
0x14002c8d9  test    ebx, ebx
0x14002c8db  jnz     short loc_14002C8E4
0x14002c8dd  test    eax, eax
0x14002c8df  jnz     short loc_14002C8CA
0x14002c8e1  lea     ebx, [rax+0Dh]
0x14002c8e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002c8e8  inc     rax
0x14002c8eb  cmp     [r14+rax*2], r15w
0x14002c8f0  jnz     short loc_14002C8E8
0x14002c8f2  lea     r14, [r14+rax*2]
0x14002c8f6  add     r14, 2
0x14002c8fa  cmp     [r14], r15w
0x14002c8fe  jnz     loc_14002C7C8
0x14002c904  jmp     short loc_14002C90E
0x14002c906  call    cs:__imp_GetLastError
0x14002c90c  mov     ebx, eax
0x14002c90e  mov     rcx, cs:hHeap; hHeap
0x14002c915  mov     r8, rsi; lpMem
0x14002c918  xor     edx, edx; dwFlags
0x14002c91a  call    cs:__imp_HeapFree
0x14002c920  test    rdi, rdi
0x14002c923  jz      short loc_14002C92E
0x14002c925  mov     rcx, rdi
0x14002c928  call    cs:__imp_DriverStoreClose
0x14002c92e  mov     ecx, ebx; dwErrCode
0x14002c930  call    cs:__imp_SetLastError
0x14002c936  test    ebx, ebx
0x14002c938  mov     eax, r15d
0x14002c93b  setz    al
0x14002c93e  add     rsp, 48h
0x14002c942  pop     r15
0x14002c944  pop     r14
0x14002c946  pop     rdi
0x14002c947  pop     rsi
0x14002c948  pop     rbx
0x14002c949  pop     rbp
0x14002c94a  retn
```
