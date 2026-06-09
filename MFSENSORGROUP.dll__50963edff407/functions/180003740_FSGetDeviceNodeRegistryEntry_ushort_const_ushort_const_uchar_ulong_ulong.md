# FSGetDeviceNodeRegistryEntry(ushort const *,ushort const *,uchar *,ulong,ulong *)

- ea: `0x180003740`
- end: `0x180003aab`
- name: `?FSGetDeviceNodeRegistryEntry@@YAJPEBG0PEAEKPEAK@Z`
- size: `875`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpValueName, LPBYTE lpData, ULONG, unsigned int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002474`
- `0x180026170`
- `0x1800544c4`
- `0x1800553d8`
- `0x180057220`

## callees

- `0x180003740`
- `0x180005fa0`
- `0x180031920`
- `0x18003491c`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180003863`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18000398c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180003863`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18000398c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800037ff`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800037ff`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000399e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800039d6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800039ff`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000399e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800039d6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800039ff`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000381a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000381a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a96`

## pseudocode

```c
__int64 __fastcall FSGetDeviceNodeRegistryEntry(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        ULONG a4,
        unsigned int *a5)
{
  CONFIGRET Device_Interface_PropertyW; // eax
  CONFIGRET v10; // eax
  HKEY v11; // rbx
  CONFIGRET v12; // eax
  LSTATUS v13; // eax
  signed int v14; // ebx
  ULONG v15; // eax
  LSTATUS v16; // eax
  HKEY v18; // rbx
  signed int v19; // eax
  __int64 v20; // rdx
  signed int v21; // eax
  signed int v22; // eax
  ULONG cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkDevice; // [rsp+38h] [rbp-C8h] BYREF
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DEVPROPTYPE PropertyType; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v28[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+60h] [rbp-A0h] BYREF

  phkDevice = 0;
  Type = 0;
  memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
  PropertyType = 0;
  pdnDevInst = 0;
  if ( !pszDeviceInterface || !lpValueName )
    return (unsigned int)-2147024809;
  if ( !a5 )
    return (unsigned int)-2147467261;
  *a5 = 0;
  cbData = 400;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 pszDeviceInterface,
                                 &DEVPKEY_Device_InstanceId,
                                 &PropertyType,
                                 (PBYTE)PropertyBuffer,
                                 &cbData,
                                 0);
  if ( Device_Interface_PropertyW )
  {
    v21 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
    v14 = v21;
    if ( v21 > 0 )
      v14 = (unsigned __int16)v21 | 0x80070000;
    if ( v14 < 0 )
      goto LABEL_19;
  }
  v10 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
  if ( v10 )
  {
    v19 = CM_MapCrToWin32Err(v10, 0xDu);
    v14 = v19;
    if ( v19 > 0 )
      v14 = (unsigned __int16)v19 | 0x80070000;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_19;
      v20 = 58;
LABEL_42:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v14);
      goto LABEL_19;
    }
  }
  v11 = phkDevice;
  if ( phkDevice )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v28);
    RegCloseKey(v11);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
  }
  phkDevice = 0;
  v12 = CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, &phkDevice, 0);
  if ( v12 == 46 )
  {
    v18 = phkDevice;
    if ( phkDevice )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v28);
      RegCloseKey(v18);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
    }
    phkDevice = 0;
    v12 = CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, &phkDevice, 1u);
  }
  if ( v12 )
  {
    v22 = CM_MapCrToWin32Err(v12, 0xDu);
    v14 = v22;
    if ( v22 > 0 )
      v14 = (unsigned __int16)v22 | 0x80070000;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_19;
      v20 = 59;
      goto LABEL_42;
    }
  }
  cbData = 0;
  v13 = RegQueryValueExW(phkDevice, lpValueName, 0, &Type, 0, &cbData);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v14 < 0 )
      goto LABEL_19;
  }
  v15 = cbData;
  *a5 = cbData;
  if ( v15 > a4 )
  {
    v14 = -1072860816;
  }
  else
  {
    cbData = a4;
    v16 = RegQueryValueExW(phkDevice, lpValueName, 0, &Type, lpData, &cbData);
    v14 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v14 = (unsigned __int16)v16 | 0x80070000;
      if ( v14 < 0 )
        goto LABEL_19;
    }
    else
    {
      v14 = 0;
    }
    *a5 = cbData;
  }
LABEL_19:
  if ( phkDevice )
    RegCloseKey(phkDevice);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180003740  push    rbp
0x180003742  push    rbx
0x180003743  push    rsi
0x180003744  push    r12
0x180003746  push    r14
0x180003748  push    r15
0x18000374a  lea     rbp, [rsp-108h]
0x180003752  sub     rsp, 208h
0x180003759  mov     rax, cs:__security_cookie
0x180003760  xor     rax, rsp
0x180003763  mov     [rbp+130h+var_40], rax
0x18000376a  mov     rsi, [rbp+130h+arg_20]
0x180003771  mov     r12, r8
0x180003774  mov     r14, rdx
0x180003777  mov     [rsp+230h+phkDevice], 0
0x180003780  mov     rbx, rcx
0x180003783  mov     [rsp+230h+Type], 0
0x18000378b  xor     edx, edx; Val
0x18000378d  lea     rcx, [rsp+230h+PropertyBuffer]; void *
0x180003792  mov     r8d, 190h; Size
0x180003798  mov     r15d, r9d
0x18000379b  call    memset_0
0x1800037a0  mov     [rsp+230h+PropertyType], 0
0x1800037a8  mov     [rsp+230h+pdnDevInst], 0
0x1800037b0  test    rbx, rbx
0x1800037b3  jz      loc_180003940
0x1800037b9  test    r14, r14
0x1800037bc  jz      loc_180003940
0x1800037c2  test    rsi, rsi
0x1800037c5  jz      loc_180003A5D
0x1800037cb  lea     rax, [rsp+230h+cbData]
0x1800037d0  mov     [rsp+230h+ulFlags], 0; ulFlags
0x1800037d8  lea     r9, [rsp+230h+PropertyBuffer]; PropertyBuffer
0x1800037dd  mov     [rsp+230h+PropertyBufferSize], rax; PropertyBufferSize
0x1800037e2  lea     r8, [rsp+230h+PropertyType]; PropertyType
0x1800037e7  mov     dword ptr [rsi], 0
0x1800037ed  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800037f4  mov     [rsp+230h+cbData], 190h
0x1800037fc  mov     rcx, rbx; pszDeviceInterface
0x1800037ff  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180003805  test    eax, eax
0x180003807  jnz     loc_1800039CF
0x18000380d  xor     r8d, r8d; ulFlags
0x180003810  lea     rdx, [rsp+230h+PropertyBuffer]; pDeviceID
0x180003815  lea     rcx, [rsp+230h+pdnDevInst]; pdnDevInst
0x18000381a  call    cs:__imp_CM_Locate_DevNodeW
0x180003820  test    eax, eax
0x180003822  jnz     loc_180003997
0x180003828  mov     rbx, [rsp+230h+phkDevice]
0x18000382d  test    rbx, rbx
0x180003830  jnz     loc_180003A67
0x180003836  mov     ecx, [rsp+230h+pdnDevInst]; dnDevNode
0x18000383a  lea     rax, [rsp+230h+phkDevice]
0x18000383f  mov     [rsp+230h+ulFlags], 0; ulFlags
0x180003847  mov     r9d, 1; Disposition
0x18000384d  xor     r8d, r8d; ulHardwareProfile
0x180003850  mov     [rsp+230h+PropertyBufferSize], rax; phkDevice
0x180003855  mov     edx, 20019h; samDesired
0x18000385a  mov     [rsp+230h+phkDevice], 0
0x180003863  call    cs:__imp_CM_Open_DevNode_Key
0x180003869  cmp     eax, 2Eh ; '.'
0x18000386c  jz      loc_180003951
0x180003872  test    eax, eax
0x180003874  jnz     loc_1800039F8
0x18000387a  mov     rcx, [rsp+230h+phkDevice]; hKey
0x18000387f  lea     rax, [rsp+230h+cbData]
0x180003884  mov     qword ptr [rsp+230h+ulFlags], rax; lpcbData
0x180003889  lea     r9, [rsp+230h+Type]; lpType
0x18000388e  xor     r8d, r8d; lpReserved
0x180003891  mov     [rsp+230h+PropertyBufferSize], 0; lpData
0x18000389a  mov     rdx, r14; lpValueName
0x18000389d  mov     [rsp+230h+cbData], 0
0x1800038a5  call    cs:__imp_RegQueryValueExW
0x1800038ab  mov     ebx, eax
0x1800038ad  test    eax, eax
0x1800038af  jz      short loc_1800038C0
0x1800038b1  jle     short loc_1800038BC
0x1800038b3  movzx   ebx, ax
0x1800038b6  or      ebx, 80070000h
0x1800038bc  test    ebx, ebx
0x1800038be  js      short loc_18000390E
0x1800038c0  mov     eax, [rsp+230h+cbData]
0x1800038c4  mov     [rsi], eax
0x1800038c6  cmp     eax, r15d
0x1800038c9  ja      loc_180003A48
0x1800038cf  mov     rcx, [rsp+230h+phkDevice]; hKey
0x1800038d4  lea     rax, [rsp+230h+cbData]
0x1800038d9  mov     qword ptr [rsp+230h+ulFlags], rax; lpcbData
0x1800038de  lea     r9, [rsp+230h+Type]; lpType
0x1800038e3  xor     r8d, r8d; lpReserved
0x1800038e6  mov     [rsp+230h+PropertyBufferSize], r12; lpData
0x1800038eb  mov     rdx, r14; lpValueName
0x1800038ee  mov     [rsp+230h+cbData], r15d
0x1800038f3  call    cs:__imp_RegQueryValueExW
0x1800038f9  mov     ebx, eax
0x1800038fb  test    eax, eax
0x1800038fd  jz      short loc_180003947
0x1800038ff  jle     short loc_18000390A
0x180003901  movzx   ebx, ax
0x180003904  or      ebx, 80070000h
0x18000390a  test    ebx, ebx
0x18000390c  jns     short loc_180003949
0x18000390e  mov     rcx, [rsp+230h+phkDevice]; hKey
0x180003913  test    rcx, rcx
0x180003916  jz      short loc_18000391E
0x180003918  call    cs:__imp_RegCloseKey
0x18000391e  mov     eax, ebx
0x180003920  mov     rcx, [rbp+130h+var_40]
0x180003927  xor     rcx, rsp; StackCookie
0x18000392a  call    __security_check_cookie
0x18000392f  add     rsp, 208h
0x180003936  pop     r15
0x180003938  pop     r14
0x18000393a  pop     r12
0x18000393c  pop     rsi
0x18000393d  pop     rbx
0x18000393e  pop     rbp
0x18000393f  retn
0x180003940  mov     ebx, 80070057h
0x180003945  jmp     short loc_18000391E
0x180003947  xor     ebx, ebx
0x180003949  mov     ecx, [rsp+230h+cbData]
0x18000394d  mov     [rsi], ecx
0x18000394f  jmp     short loc_18000390E
0x180003951  mov     rbx, [rsp+230h+phkDevice]
0x180003956  test    rbx, rbx
0x180003959  jnz     loc_180003A89
0x18000395f  mov     ecx, [rsp+230h+pdnDevInst]; dnDevNode
0x180003963  lea     rax, [rsp+230h+phkDevice]
0x180003968  mov     [rsp+230h+ulFlags], 1; ulFlags
0x180003970  mov     r9d, 1; Disposition
0x180003976  xor     r8d, r8d; ulHardwareProfile
0x180003979  mov     [rsp+230h+PropertyBufferSize], rax; phkDevice
0x18000397e  mov     edx, 20019h; samDesired
0x180003983  mov     [rsp+230h+phkDevice], 0
0x18000398c  call    cs:__imp_CM_Open_DevNode_Key
0x180003992  jmp     loc_180003872
0x180003997  mov     edx, 0Dh; DefaultErr
0x18000399c  mov     ecx, eax; CmReturnCode
0x18000399e  call    cs:__imp_CM_MapCrToWin32Err
0x1800039a4  mov     ebx, eax
0x1800039a6  test    eax, eax
0x1800039a8  jle     short loc_1800039B3
0x1800039aa  movzx   ebx, ax
0x1800039ad  or      ebx, 80070000h
0x1800039b3  test    ebx, ebx
0x1800039b5  jns     loc_180003828
0x1800039bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800039c2  jb      loc_18000390E
0x1800039c8  mov     edx, 3Ah ; ':'
0x1800039cd  jmp     short loc_180003A25
0x1800039cf  mov     edx, 0Dh; DefaultErr
0x1800039d4  mov     ecx, eax; CmReturnCode
0x1800039d6  call    cs:__imp_CM_MapCrToWin32Err
0x1800039dc  mov     ebx, eax
0x1800039de  test    eax, eax
0x1800039e0  jle     short loc_1800039EB
0x1800039e2  movzx   ebx, ax
0x1800039e5  or      ebx, 80070000h
0x1800039eb  test    ebx, ebx
0x1800039ed  jns     loc_18000380D
0x1800039f3  jmp     loc_18000390E
0x1800039f8  mov     edx, 0Dh; DefaultErr
0x1800039fd  mov     ecx, eax; CmReturnCode
0x1800039ff  call    cs:__imp_CM_MapCrToWin32Err
0x180003a05  mov     ebx, eax
0x180003a07  test    eax, eax
0x180003a09  jg      short loc_180003A52
0x180003a0b  test    ebx, ebx
0x180003a0d  jns     loc_18000387A
0x180003a13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003a1a  jb      loc_18000390E
0x180003a20  mov     edx, 3Bh ; ';'
0x180003a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a2c  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180003a33  xor     r9d, r9d
0x180003a36  mov     dword ptr [rsp+230h+PropertyBufferSize], ebx
0x180003a3a  mov     rcx, [rcx+10h]
0x180003a3e  call    WPP_SF_qD
0x180003a43  jmp     loc_18000390E
0x180003a48  mov     ebx, 0C00D7170h
0x180003a4d  jmp     loc_18000390E
0x180003a52  movzx   ebx, ax
0x180003a55  or      ebx, 80070000h
0x180003a5b  jmp     short loc_180003A0B
0x180003a5d  mov     ebx, 80004003h
0x180003a62  jmp     loc_18000391E
0x180003a67  lea     rcx, [rsp+230h+var_1E0]; this
0x180003a6c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180003a71  mov     rcx, rbx; hKey
0x180003a74  call    cs:__imp_RegCloseKey
0x180003a7a  lea     rcx, [rsp+230h+var_1E0]; this
0x180003a7f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180003a84  jmp     loc_180003836
0x180003a89  lea     rcx, [rsp+230h+var_1E0]; this
0x180003a8e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180003a93  mov     rcx, rbx; hKey
0x180003a96  call    cs:__imp_RegCloseKey
0x180003a9c  lea     rcx, [rsp+230h+var_1E0]; this
0x180003aa1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180003aa6  jmp     loc_18000395F
```
