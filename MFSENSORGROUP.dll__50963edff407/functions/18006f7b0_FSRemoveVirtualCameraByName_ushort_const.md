# FSRemoveVirtualCameraByName(ushort const *)

- ea: `0x18006f7b0`
- end: `0x18006f9cc`
- name: `?FSRemoveVirtualCameraByName@@YAJPEBG@Z`
- size: `540`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180056590`

## callees

- `0x180005fa0`
- `0x18003b370`
- `0x180044f30`
- `0x180045900`
- `0x18006f7b0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x18006f957`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x18006f957`
- `api-ms-win-devices-config-l1-1-1!CM_Uninstall_DevNode` at `0x18006f965`
- `api-ms-win-devices-config-l1-1-1!CM_Uninstall_DevNode` at `0x18006f965`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18006f8bf`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18006f8bf`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f8d0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f97a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f99c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f8d0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f97a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006f99c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006f92d`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006f92d`

## pseudocode

```c
signed int __fastcall FSRemoveVirtualCameraByName(const unsigned __int16 *a1)
{
  signed int v2; // ebx
  signed int result; // eax
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v5; // eax
  __int64 v6; // rdx
  CONFIGRET v7; // eax
  CONFIGRET v8; // edi
  signed int v9; // eax
  DEVNODE pdnDevInst; // [rsp+30h] [rbp-D0h] BYREF
  ULONG PropertyBufferSize; // [rsp+34h] [rbp-CCh] BYREF
  DEVPROPTYPE PropertyType; // [rsp+38h] [rbp-C8h] BYREF
  _PNP_VETO_TYPE pVetoType; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR PropertyBuffer[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszVetoName[264]; // [rsp+460h] [rbp+360h] BYREF

  memset_0(pszDeviceInterface, 0, 0x208u);
  PropertyType = 0;
  memset_0(PropertyBuffer, 0, 0x208u);
  PropertyBufferSize = 0;
  pdnDevInst = 0;
  pVetoType = PNP_VetoTypeUnknown;
  memset_0(pszVetoName, 0, 0x208u);
  if ( !a1 )
    return -2147024809;
  v2 = FSGetAliasDeviceName2(0, a1, &GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8, pszDeviceInterface, 0x104u, 0);
  if ( v2 < 0 )
    return v2;
  PropertyBufferSize = 520;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 pszDeviceInterface,
                                 &DEVPKEY_Device_InstanceId,
                                 &PropertyType,
                                 (PBYTE)PropertyBuffer,
                                 &PropertyBufferSize,
                                 0);
  if ( Device_Interface_PropertyW )
  {
    v5 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( v2 < 0 )
    {
      if ( !g_wppLevels )
        return v2;
      v6 = 55;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v2);
      return v2;
    }
  }
  v7 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
  if ( v7 )
  {
    v9 = CM_MapCrToWin32Err(v7, 0xDu);
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    if ( v2 < 0 )
    {
      if ( !g_wppLevels )
        return v2;
      v6 = 56;
      goto LABEL_12;
    }
  }
  else
  {
    v2 = 0;
  }
  v8 = CM_Query_And_Remove_SubTreeW(pdnDevInst, &pVetoType, pszVetoName, 0x104u, 2u);
  CM_Uninstall_DevNode(pdnDevInst, 0);
  if ( !v8 )
    return v2;
  result = CM_MapCrToWin32Err(v8, 0xDu);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18006f7b0  mov     [rsp-8+arg_8], rbx
0x18006f7b5  mov     [rsp-8+arg_10], rdi
0x18006f7ba  push    rbp
0x18006f7bb  lea     rbp, [rsp-580h]
0x18006f7c3  sub     rsp, 680h
0x18006f7ca  mov     rax, cs:__security_cookie
0x18006f7d1  xor     rax, rsp
0x18006f7d4  mov     [rbp+580h+var_10], rax
0x18006f7db  mov     rbx, rcx
0x18006f7de  mov     edi, 208h
0x18006f7e3  mov     r8d, edi; Size
0x18006f7e6  lea     rcx, [rsp+680h+pszDeviceInterface]; void *
0x18006f7eb  xor     edx, edx; Val
0x18006f7ed  call    memset_0
0x18006f7f2  mov     r8d, edi; Size
0x18006f7f5  mov     [rsp+680h+PropertyType], 0
0x18006f7fd  xor     edx, edx; Val
0x18006f7ff  lea     rcx, [rbp+580h+PropertyBuffer]; void *
0x18006f806  call    memset_0
0x18006f80b  mov     r8d, edi; Size
0x18006f80e  mov     [rsp+680h+var_64C], 0
0x18006f816  xor     edx, edx; Val
0x18006f818  mov     [rsp+680h+pdnDevInst], 0
0x18006f820  lea     rcx, [rbp+580h+pszVetoName]; void *
0x18006f827  mov     [rsp+680h+pVetoType], 0
0x18006f82f  call    memset_0
0x18006f834  test    rbx, rbx
0x18006f837  jnz     short loc_18006F864
0x18006f839  mov     ebx, 80070057h
0x18006f83e  mov     eax, ebx
0x18006f840  mov     rcx, [rbp+580h+var_10]
0x18006f847  xor     rcx, rsp; StackCookie
0x18006f84a  call    __security_check_cookie
0x18006f84f  lea     r11, [rsp+680h+var_s0]
0x18006f857  mov     rbx, [r11+18h]
0x18006f85b  mov     rdi, [r11+20h]
0x18006f85f  mov     rsp, r11
0x18006f862  pop     rbp
0x18006f863  retn
0x18006f864  mov     qword ptr [rsp+680h+ulFlags], 0; unsigned int *
0x18006f86d  lea     r9, [rsp+680h+pszDeviceInterface]; unsigned __int16 *
0x18006f872  lea     r8, _GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8; struct _GUID *
0x18006f879  mov     dword ptr [rsp+680h+PropertyBufferSize], 104h; unsigned int
0x18006f881  mov     rdx, rbx; unsigned __int16 *
0x18006f884  xor     ecx, ecx; bool
0x18006f886  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x18006f88b  mov     ebx, eax
0x18006f88d  test    eax, eax
0x18006f88f  js      short loc_18006F83E
0x18006f891  lea     rax, [rsp+680h+var_64C]
0x18006f896  mov     [rsp+680h+ulFlags], 0; ulFlags
0x18006f89e  lea     r9, [rbp+580h+PropertyBuffer]; PropertyBuffer
0x18006f8a5  mov     [rsp+680h+PropertyBufferSize], rax; PropertyBufferSize
0x18006f8aa  lea     r8, [rsp+680h+PropertyType]; PropertyType
0x18006f8af  mov     [rsp+680h+var_64C], edi
0x18006f8b3  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x18006f8ba  lea     rcx, [rsp+680h+pszDeviceInterface]; pszDeviceInterface
0x18006f8bf  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18006f8c5  test    eax, eax
0x18006f8c7  jz      short loc_18006F91E
0x18006f8c9  mov     edx, 0Dh; DefaultErr
0x18006f8ce  mov     ecx, eax; CmReturnCode
0x18006f8d0  call    cs:__imp_CM_MapCrToWin32Err
0x18006f8d6  mov     ebx, eax
0x18006f8d8  test    eax, eax
0x18006f8da  jle     short loc_18006F8E5
0x18006f8dc  movzx   ebx, ax
0x18006f8df  or      ebx, 80070000h
0x18006f8e5  test    ebx, ebx
0x18006f8e7  jns     short loc_18006F91E
0x18006f8e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f8f0  jb      loc_18006F83E
0x18006f8f6  mov     edx, 37h ; '7'
0x18006f8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f902  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18006f909  xor     r9d, r9d
0x18006f90c  mov     dword ptr [rsp+680h+PropertyBufferSize], ebx
0x18006f910  mov     rcx, [rcx+10h]
0x18006f914  call    WPP_SF_qD
0x18006f919  jmp     loc_18006F83E
0x18006f91e  xor     r8d, r8d; ulFlags
0x18006f921  lea     rdx, [rbp+580h+PropertyBuffer]; pDeviceID
0x18006f928  lea     rcx, [rsp+680h+pdnDevInst]; pdnDevInst
0x18006f92d  call    cs:__imp_CM_Locate_DevNodeW
0x18006f933  test    eax, eax
0x18006f935  jnz     short loc_18006F995
0x18006f937  xor     ebx, ebx
0x18006f939  mov     ecx, [rsp+680h+pdnDevInst]; dnAncestor
0x18006f93d  lea     r8, [rbp+580h+pszVetoName]; pszVetoName
0x18006f944  mov     r9d, 104h; ulNameLength
0x18006f94a  mov     dword ptr [rsp+680h+PropertyBufferSize], 2; ulFlags
0x18006f952  lea     rdx, [rsp+680h+pVetoType]; pVetoType
0x18006f957  call    cs:__imp_CM_Query_And_Remove_SubTreeW
0x18006f95d  mov     ecx, [rsp+680h+pdnDevInst]; dnDevInst
0x18006f961  xor     edx, edx; ulFlags
0x18006f963  mov     edi, eax
0x18006f965  call    cs:__imp_CM_Uninstall_DevNode
0x18006f96b  test    edi, edi
0x18006f96d  jz      loc_18006F83E
0x18006f973  mov     edx, 0Dh; DefaultErr
0x18006f978  mov     ecx, edi; CmReturnCode
0x18006f97a  call    cs:__imp_CM_MapCrToWin32Err
0x18006f980  test    eax, eax
0x18006f982  jle     loc_18006F840
0x18006f988  movzx   eax, ax
0x18006f98b  or      eax, 80070000h
0x18006f990  jmp     loc_18006F840
0x18006f995  mov     edx, 0Dh; DefaultErr
0x18006f99a  mov     ecx, eax; CmReturnCode
0x18006f99c  call    cs:__imp_CM_MapCrToWin32Err
0x18006f9a2  mov     ebx, eax
0x18006f9a4  test    eax, eax
0x18006f9a6  jle     short loc_18006F9B1
0x18006f9a8  movzx   ebx, ax
0x18006f9ab  or      ebx, 80070000h
0x18006f9b1  test    ebx, ebx
0x18006f9b3  jns     short loc_18006F939
0x18006f9b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f9bc  jb      loc_18006F83E
0x18006f9c2  mov     edx, 38h ; '8'
0x18006f9c7  jmp     loc_18006F8FB
```
