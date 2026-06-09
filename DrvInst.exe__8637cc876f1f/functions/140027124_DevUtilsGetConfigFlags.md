# DevUtilsGetConfigFlags

- ea: `0x140027124`
- end: `0x1400271b0`
- name: `DevUtilsGetConfigFlags`
- size: `140`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001170c`
- `0x140013f6c`
- `0x140014320`
- `0x140016de0`
- `0x1400175fc`
- `0x14001c22c`
- `0x14001c718`
- `0x14002741c`
- `0x140027670`

## callees

- `0x140027124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002719d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002719d`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14002717c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14002717c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x14002716b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x14002716b`

## pseudocode

```c
_BOOL8 __fastcall DevUtilsGetConfigFlags(DEVINST a1, void *a2)
{
  DWORD v2; // ebx
  CONFIGRET DevNode_Registry_PropertyW; // eax
  ULONG pulLength; // [rsp+48h] [rbp+10h] BYREF
  ULONG pulRegDataType; // [rsp+50h] [rbp+18h] BYREF

  pulRegDataType = 0;
  pulLength = 0;
  if ( a2 )
  {
    pulLength = 4;
    DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(a1, 0xBu, &pulRegDataType, a2, &pulLength, 0);
    if ( DevNode_Registry_PropertyW )
    {
      v2 = CM_MapCrToWin32Err(DevNode_Registry_PropertyW, 0xDu);
    }
    else if ( pulRegDataType != 4 || (v2 = 0, pulLength != 4) )
    {
      v2 = 13;
    }
  }
  else
  {
    v2 = 87;
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x140027124  push    rbx
0x140027126  sub     rsp, 30h
0x14002712a  mov     [rsp+38h+pulRegDataType], 0
0x140027132  mov     [rsp+38h+arg_8], 0
0x14002713a  test    rdx, rdx
0x14002713d  jnz     short loc_140027144
0x14002713f  lea     ebx, [rdx+57h]
0x140027142  jmp     short loc_14002719B
0x140027144  lea     rax, [rsp+38h+arg_8]
0x140027149  mov     [rsp+38h+ulFlags], 0; ulFlags
0x140027151  mov     r9, rdx; Buffer
0x140027154  mov     [rsp+38h+pulLength], rax; pulLength
0x140027159  mov     edx, 0Bh; ulProperty
0x14002715e  mov     [rsp+38h+arg_8], 4
0x140027166  lea     r8, [rsp+38h+pulRegDataType]; pulRegDataType
0x14002716b  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x140027171  test    eax, eax
0x140027173  jz      short loc_140027186
0x140027175  mov     edx, 0Dh; DefaultErr
0x14002717a  mov     ecx, eax; CmReturnCode
0x14002717c  call    cs:__imp_CM_MapCrToWin32Err
0x140027182  mov     ebx, eax
0x140027184  jmp     short loc_14002719B
0x140027186  cmp     [rsp+38h+pulRegDataType], 4
0x14002718b  jnz     short loc_140027196
0x14002718d  xor     ebx, ebx
0x14002718f  cmp     [rsp+38h+arg_8], 4
0x140027194  jz      short loc_14002719B
0x140027196  mov     ebx, 0Dh
0x14002719b  mov     ecx, ebx; dwErrCode
0x14002719d  call    cs:__imp_SetLastError
0x1400271a3  xor     eax, eax
0x1400271a5  test    ebx, ebx
0x1400271a7  setz    al
0x1400271aa  add     rsp, 30h
0x1400271ae  pop     rbx
0x1400271af  retn
```
