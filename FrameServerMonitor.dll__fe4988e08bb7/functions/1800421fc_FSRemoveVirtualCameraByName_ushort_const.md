# FSRemoveVirtualCameraByName(ushort const *)

- ea: `0x1800421fc`
- end: `0x180042418`
- name: `?FSRemoveVirtualCameraByName@@YAJPEBG@Z`
- size: `540`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180008d7c`
- `0x180024b00`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x1800060f8`
- `0x180006a98`
- `0x1800403e4`
- `0x1800421fc`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18004231c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800423c6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800423e8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18004231c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800423c6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800423e8`
- `api-ms-win-devices-config-l1-1-1!CM_Uninstall_DevNode` at `0x1800423b1`
- `api-ms-win-devices-config-l1-1-1!CM_Uninstall_DevNode` at `0x1800423b1`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x1800423a3`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x1800423a3`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180042379`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180042379`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18004230b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18004230b`

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
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
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
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
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
0x1800421fc  mov     [rsp-8+arg_8], rbx
0x180042201  mov     [rsp-8+arg_10], rdi
0x180042206  push    rbp
0x180042207  lea     rbp, [rsp-580h]
0x18004220f  sub     rsp, 680h
0x180042216  mov     rax, cs:__security_cookie
0x18004221d  xor     rax, rsp
0x180042220  mov     [rbp+580h+var_10], rax
0x180042227  mov     rbx, rcx
0x18004222a  mov     edi, 208h
0x18004222f  mov     r8d, edi; Size
0x180042232  lea     rcx, [rsp+680h+pszDeviceInterface]; void *
0x180042237  xor     edx, edx; Val
0x180042239  call    memset_0
0x18004223e  mov     r8d, edi; Size
0x180042241  mov     [rsp+680h+PropertyType], 0
0x180042249  xor     edx, edx; Val
0x18004224b  lea     rcx, [rbp+580h+PropertyBuffer]; void *
0x180042252  call    memset_0
0x180042257  mov     r8d, edi; Size
0x18004225a  mov     [rsp+680h+var_64C], 0
0x180042262  xor     edx, edx; Val
0x180042264  mov     [rsp+680h+pdnDevInst], 0
0x18004226c  lea     rcx, [rbp+580h+pszVetoName]; void *
0x180042273  mov     [rsp+680h+pVetoType], 0
0x18004227b  call    memset_0
0x180042280  test    rbx, rbx
0x180042283  jnz     short loc_1800422B0
0x180042285  mov     ebx, 80070057h
0x18004228a  mov     eax, ebx
0x18004228c  mov     rcx, [rbp+580h+var_10]
0x180042293  xor     rcx, rsp; StackCookie
0x180042296  call    __security_check_cookie
0x18004229b  lea     r11, [rsp+680h+var_s0]
0x1800422a3  mov     rbx, [r11+18h]
0x1800422a7  mov     rdi, [r11+20h]
0x1800422ab  mov     rsp, r11
0x1800422ae  pop     rbp
0x1800422af  retn
0x1800422b0  mov     qword ptr [rsp+680h+ulFlags], 0; unsigned int *
0x1800422b9  lea     r9, [rsp+680h+pszDeviceInterface]; unsigned __int16 *
0x1800422be  lea     r8, _GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8; struct _GUID *
0x1800422c5  mov     dword ptr [rsp+680h+PropertyBufferSize], 104h; unsigned int
0x1800422cd  mov     rdx, rbx; unsigned __int16 *
0x1800422d0  xor     ecx, ecx; bool
0x1800422d2  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x1800422d7  mov     ebx, eax
0x1800422d9  test    eax, eax
0x1800422db  js      short loc_18004228A
0x1800422dd  lea     rax, [rsp+680h+var_64C]
0x1800422e2  mov     [rsp+680h+ulFlags], 0; ulFlags
0x1800422ea  lea     r9, [rbp+580h+PropertyBuffer]; PropertyBuffer
0x1800422f1  mov     [rsp+680h+PropertyBufferSize], rax; PropertyBufferSize
0x1800422f6  lea     r8, [rsp+680h+PropertyType]; PropertyType
0x1800422fb  mov     [rsp+680h+var_64C], edi
0x1800422ff  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180042306  lea     rcx, [rsp+680h+pszDeviceInterface]; pszDeviceInterface
0x18004230b  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180042311  test    eax, eax
0x180042313  jz      short loc_18004236A
0x180042315  mov     edx, 0Dh; DefaultErr
0x18004231a  mov     ecx, eax; CmReturnCode
0x18004231c  call    cs:__imp_CM_MapCrToWin32Err
0x180042322  mov     ebx, eax
0x180042324  test    eax, eax
0x180042326  jle     short loc_180042331
0x180042328  movzx   ebx, ax
0x18004232b  or      ebx, 80070000h
0x180042331  test    ebx, ebx
0x180042333  jns     short loc_18004236A
0x180042335  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004233a  cmp     al, 1
0x18004233c  jb      loc_18004228A
0x180042342  mov     edx, 37h ; '7'
0x180042347  mov     rcx, cs:WPP_GLOBAL_Control
0x18004234e  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180042355  xor     r9d, r9d
0x180042358  mov     dword ptr [rsp+680h+PropertyBufferSize], ebx
0x18004235c  mov     rcx, [rcx+10h]
0x180042360  call    WPP_SF_qD
0x180042365  jmp     loc_18004228A
0x18004236a  xor     r8d, r8d; ulFlags
0x18004236d  lea     rdx, [rbp+580h+PropertyBuffer]; pDeviceID
0x180042374  lea     rcx, [rsp+680h+pdnDevInst]; pdnDevInst
0x180042379  call    cs:__imp_CM_Locate_DevNodeW
0x18004237f  test    eax, eax
0x180042381  jnz     short loc_1800423E1
0x180042383  xor     ebx, ebx
0x180042385  mov     ecx, [rsp+680h+pdnDevInst]; dnAncestor
0x180042389  lea     r8, [rbp+580h+pszVetoName]; pszVetoName
0x180042390  mov     r9d, 104h; ulNameLength
0x180042396  mov     dword ptr [rsp+680h+PropertyBufferSize], 2; ulFlags
0x18004239e  lea     rdx, [rsp+680h+pVetoType]; pVetoType
0x1800423a3  call    cs:__imp_CM_Query_And_Remove_SubTreeW
0x1800423a9  mov     ecx, [rsp+680h+pdnDevInst]; dnDevInst
0x1800423ad  xor     edx, edx; ulFlags
0x1800423af  mov     edi, eax
0x1800423b1  call    cs:__imp_CM_Uninstall_DevNode
0x1800423b7  test    edi, edi
0x1800423b9  jz      loc_18004228A
0x1800423bf  mov     edx, 0Dh; DefaultErr
0x1800423c4  mov     ecx, edi; CmReturnCode
0x1800423c6  call    cs:__imp_CM_MapCrToWin32Err
0x1800423cc  test    eax, eax
0x1800423ce  jle     loc_18004228C
0x1800423d4  movzx   eax, ax
0x1800423d7  or      eax, 80070000h
0x1800423dc  jmp     loc_18004228C
0x1800423e1  mov     edx, 0Dh; DefaultErr
0x1800423e6  mov     ecx, eax; CmReturnCode
0x1800423e8  call    cs:__imp_CM_MapCrToWin32Err
0x1800423ee  mov     ebx, eax
0x1800423f0  test    eax, eax
0x1800423f2  jle     short loc_1800423FD
0x1800423f4  movzx   ebx, ax
0x1800423f7  or      ebx, 80070000h
0x1800423fd  test    ebx, ebx
0x1800423ff  jns     short loc_180042385
0x180042401  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042406  cmp     al, 1
0x180042408  jb      loc_18004228A
0x18004240e  mov     edx, 38h ; '8'
0x180042413  jmp     loc_180042347
```
