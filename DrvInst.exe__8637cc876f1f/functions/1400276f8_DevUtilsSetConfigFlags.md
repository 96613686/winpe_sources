# DevUtilsSetConfigFlags

- ea: `0x1400276f8`
- end: `0x14002773f`
- name: `DevUtilsSetConfigFlags`
- size: `71`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001170c`
- `0x140014320`
- `0x14001c22c`
- `0x14001c718`
- `0x140027670`

## callees

- `0x1400276f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002772c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002772c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140027722`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140027722`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x140027713`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x140027713`

## pseudocode

```c
_BOOL8 __fastcall DevUtilsSetConfigFlags(DEVINST a1, int a2)
{
  DWORD v2; // ebx
  CONFIGRET v3; // eax
  int Buffer; // [rsp+48h] [rbp+10h] BYREF

  Buffer = a2;
  v2 = 0;
  v3 = CM_Set_DevNode_Registry_PropertyW(a1, 0xBu, &Buffer, 4u, 0);
  if ( v3 )
    v2 = CM_MapCrToWin32Err(v3, 0xDu);
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x1400276f8  mov     [rsp+Buffer], edx
0x1400276fc  push    rbx
0x1400276fd  sub     rsp, 30h
0x140027701  xor     ebx, ebx
0x140027703  lea     r8, [rsp+38h+Buffer]; Buffer
0x140027708  mov     [rsp+38h+ulFlags], ebx; ulFlags
0x14002770c  lea     r9d, [rbx+4]; ulLength
0x140027710  lea     edx, [rbx+0Bh]; ulProperty
0x140027713  call    cs:__imp_CM_Set_DevNode_Registry_PropertyW
0x140027719  test    eax, eax
0x14002771b  jz      short loc_14002772A
0x14002771d  lea     edx, [rbx+0Dh]; DefaultErr
0x140027720  mov     ecx, eax; CmReturnCode
0x140027722  call    cs:__imp_CM_MapCrToWin32Err
0x140027728  mov     ebx, eax
0x14002772a  mov     ecx, ebx; dwErrCode
0x14002772c  call    cs:__imp_SetLastError
0x140027732  xor     eax, eax
0x140027734  test    ebx, ebx
0x140027736  setz    al
0x140027739  add     rsp, 30h
0x14002773d  pop     rbx
0x14002773e  retn
```
