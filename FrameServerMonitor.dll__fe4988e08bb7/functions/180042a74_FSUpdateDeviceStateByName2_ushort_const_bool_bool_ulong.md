# FSUpdateDeviceStateByName2(ushort const *,bool,bool,ulong *)

- ea: `0x180042a74`
- end: `0x180042d9b`
- name: `?FSUpdateDeviceStateByName2@@YAJPEBG_N1PEAK@Z`
- size: `807`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, char, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1800124f4`
- `0x180042da4`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180006a98`
- `0x18000d154`
- `0x180040240`
- `0x180040d88`
- `0x180041b00`
- `0x180042420`
- `0x180042a74`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042b47`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042c86`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042d45`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042b47`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042c86`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042d45`
- `api-ms-win-devices-config-l1-1-1!CM_Disable_DevNode` at `0x180042cfa`
- `api-ms-win-devices-config-l1-1-1!CM_Disable_DevNode` at `0x180042cfa`
- `api-ms-win-devices-config-l1-1-1!CM_Enable_DevNode` at `0x180042ce8`
- `api-ms-win-devices-config-l1-1-1!CM_Enable_DevNode` at `0x180042ce8`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180042c51`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180042c51`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180042b36`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180042b36`

## pseudocode

```c
__int64 __fastcall FSUpdateDeviceStateByName2(const unsigned __int16 *a1, char a2, char a3, unsigned int *a4)
{
  int v8; // edi
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  void **i; // rbx
  CONFIGRET v14; // ebx
  signed int v15; // eax
  CONFIGRET v16; // eax
  int v17; // edi
  CONFIGRET v18; // ebx
  signed int v19; // eax
  unsigned __int8 v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  DEVNODE pdnDevInst; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  ULONG PropertyBufferSize; // [rsp+44h] [rbp-BCh] BYREF
  DEVPROPTYPE PropertyType; // [rsp+48h] [rbp-B8h] BYREF
  void **v28[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
  pdnDevInst = 0;
  PropertyType = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  *a4 = 0;
  PropertyBufferSize = 400;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 a1,
                                 &DEVPKEY_Device_InstanceId,
                                 &PropertyType,
                                 (PBYTE)PropertyBuffer,
                                 &PropertyBufferSize,
                                 0);
  if ( Device_Interface_PropertyW )
  {
    v10 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        return (unsigned int)v8;
      v11 = 51;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
      return (unsigned int)v8;
    }
  }
  if ( a3 && !a2 && !FSIsDeviceInterfaceConfigured(a1) )
  {
    v21[0] = -1;
    v28[0] = (void **)v28;
    v28[2] = 0;
    v28[1] = (void **)v28;
    v8 = FSFindInterfacesWithMatchingInstanceId(PropertyBuffer, v12, (__int64)v28);
    if ( v8 < 0 )
    {
LABEL_16:
      utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v28);
      return (unsigned int)v8;
    }
    for ( i = v28[0]; i != (void **)v28; i = (void **)*i )
    {
      v8 = FSSetDeviceInterfaceAndAllKnownAliasesProperty(
             (const unsigned __int16 *)i[2],
             &DEVPKEY_DeviceInterface_CameraSettings_Configured,
             0x11u,
             v21,
             1u);
      if ( v8 < 0 )
        goto LABEL_16;
    }
    utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v28);
  }
  v14 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
  if ( (int)FSGetDeviceStateByHDevInst(pdnDevInst, &v23, &v24, &v25) >= 0 )
    *a4 = v23;
  if ( v14 )
  {
    v15 = CM_MapCrToWin32Err(v14, 0xDu);
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        return (unsigned int)v8;
      v11 = 52;
      goto LABEL_11;
    }
  }
  if ( v24 )
  {
    v8 = v24 | 0x10000000;
    if ( (v24 & 0x80000000) != 0 )
    {
      if ( !g_wppLevels )
        return (unsigned int)v8;
      v11 = 53;
      goto LABEL_11;
    }
  }
  if ( a2 )
  {
    v16 = CM_Enable_DevNode(pdnDevInst, 0);
    v17 = 256;
  }
  else
  {
    v16 = CM_Disable_DevNode(pdnDevInst, 0xCu);
    v17 = 8448;
  }
  v18 = v16;
  if ( !v16 )
    return 0;
  if ( (int)FSGetDeviceStateByHDevInst(pdnDevInst, &v23, &v24, &v25) >= 0 )
  {
    *a4 = v23;
    if ( (v24 & v17) == v17 )
      return (unsigned int)-2147021886;
  }
  v19 = CM_MapCrToWin32Err(v18, 0xDu);
  v8 = v19;
  if ( v19 > 0 )
    v8 = (unsigned __int16)v19 | 0x80070000;
  if ( v8 < 0 && g_wppLevels )
  {
    v11 = 54;
    goto LABEL_11;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180042a74  mov     [rsp-8+arg_8], rbx
0x180042a79  push    rbp
0x180042a7a  push    rsi
0x180042a7b  push    rdi
0x180042a7c  push    r14
0x180042a7e  push    r15
0x180042a80  lea     rbp, [rsp-110h]
0x180042a88  sub     rsp, 210h
0x180042a8f  mov     rax, cs:__security_cookie
0x180042a96  xor     rax, rsp
0x180042a99  mov     [rbp+130h+var_30], rax
0x180042aa0  mov     r14b, r8b
0x180042aa3  mov     r15b, dl
0x180042aa6  mov     rbx, rcx
0x180042aa9  mov     edi, 190h
0x180042aae  mov     r8d, edi; Size
0x180042ab1  lea     rcx, [rsp+230h+PropertyBuffer]; void *
0x180042ab6  xor     edx, edx; Val
0x180042ab8  mov     rsi, r9
0x180042abb  call    memset_0
0x180042ac0  mov     [rsp+230h+pdnDevInst], 0
0x180042ac8  mov     [rsp+230h+PropertyType], 0
0x180042ad0  mov     [rsp+230h+var_1F8], 0
0x180042ad8  mov     [rsp+230h+var_1F4], 0
0x180042ae0  mov     [rsp+230h+var_1F0], 0
0x180042ae8  test    rbx, rbx
0x180042aeb  jnz     short loc_180042AF7
0x180042aed  mov     edi, 80070057h
0x180042af2  jmp     loc_180042D73
0x180042af7  test    rsi, rsi
0x180042afa  jnz     short loc_180042B06
0x180042afc  mov     edi, 80004003h
0x180042b01  jmp     loc_180042D73
0x180042b06  lea     rax, [rsp+230h+var_1EC]
0x180042b0b  mov     [rsp+230h+ulFlags], 0; ulFlags
0x180042b13  lea     r9, [rsp+230h+PropertyBuffer]; PropertyBuffer
0x180042b18  mov     [rsp+230h+PropertyBufferSize], rax; PropertyBufferSize
0x180042b1d  lea     r8, [rsp+230h+PropertyType]; PropertyType
0x180042b22  mov     dword ptr [rsi], 0
0x180042b28  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180042b2f  mov     [rsp+230h+var_1EC], edi
0x180042b33  mov     rcx, rbx; pszDeviceInterface
0x180042b36  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180042b3c  test    eax, eax
0x180042b3e  jz      short loc_180042B95
0x180042b40  mov     edx, 0Dh; DefaultErr
0x180042b45  mov     ecx, eax; CmReturnCode
0x180042b47  call    cs:__imp_CM_MapCrToWin32Err
0x180042b4d  mov     edi, eax
0x180042b4f  test    eax, eax
0x180042b51  jle     short loc_180042B5C
0x180042b53  movzx   edi, ax
0x180042b56  or      edi, 80070000h
0x180042b5c  test    edi, edi
0x180042b5e  jns     short loc_180042B95
0x180042b60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042b67  jb      loc_180042D73
0x180042b6d  mov     edx, 33h ; '3'
0x180042b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b79  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180042b80  xor     r9d, r9d
0x180042b83  mov     dword ptr [rsp+230h+PropertyBufferSize], edi
0x180042b87  mov     rcx, [rcx+10h]
0x180042b8b  call    WPP_SF_qD
0x180042b90  jmp     loc_180042D73
0x180042b95  test    r14b, r14b
0x180042b98  jz      loc_180042C44
0x180042b9e  test    r15b, r15b
0x180042ba1  jnz     loc_180042C44
0x180042ba7  mov     rcx, rbx; unsigned __int16 *
0x180042baa  call    ?FSIsDeviceInterfaceConfigured@@YA_NPEBG@Z; FSIsDeviceInterfaceConfigured(ushort const *)
0x180042baf  test    al, al
0x180042bb1  jnz     loc_180042C44
0x180042bb7  lea     rax, [rsp+230h+var_1E0]
0x180042bbc  mov     [rsp+230h+var_200], 0FFh
0x180042bc1  mov     [rsp+230h+var_1E0], rax
0x180042bc6  lea     r8, [rsp+230h+var_1E0]
0x180042bcb  lea     rax, [rsp+230h+var_1E0]
0x180042bd0  mov     [rsp+230h+var_1D0], 0
0x180042bd9  lea     rcx, [rsp+230h+PropertyBuffer]; lpString2
0x180042bde  mov     [rsp+230h+var_1D8], rax
0x180042be3  call    ?FSFindInterfacesWithMatchingInstanceId@@YAJPEBGAEBU_GUID@@AEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSFindInterfacesWithMatchingInstanceId(ushort const *,_GUID const &,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180042be8  mov     edi, eax
0x180042bea  test    eax, eax
0x180042bec  jns     short loc_180042BFD
0x180042bee  lea     rcx, [rsp+230h+var_1E0]
0x180042bf3  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180042bf8  jmp     loc_180042D73
0x180042bfd  mov     rbx, [rsp+230h+var_1E0]
0x180042c02  lea     rax, [rsp+230h+var_1E0]
0x180042c07  cmp     rbx, rax
0x180042c0a  jz      short loc_180042C3A
0x180042c0c  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180042c10  lea     r9, [rsp+230h+var_200]; unsigned __int8 *
0x180042c15  mov     r8d, 11h; unsigned int
0x180042c1b  mov     dword ptr [rsp+230h+PropertyBufferSize], 1; unsigned int
0x180042c23  lea     rdx, DEVPKEY_DeviceInterface_CameraSettings_Configured; struct _DEVPROPKEY *
0x180042c2a  call    ?FSSetDeviceInterfaceAndAllKnownAliasesProperty@@YAJPEBGPEBU_DEVPROPKEY@@KPEAEK@Z; FSSetDeviceInterfaceAndAllKnownAliasesProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar *,ulong)
0x180042c2f  mov     edi, eax
0x180042c31  test    eax, eax
0x180042c33  js      short loc_180042BEE
0x180042c35  mov     rbx, [rbx]
0x180042c38  jmp     short loc_180042C02
0x180042c3a  lea     rcx, [rsp+230h+var_1E0]
0x180042c3f  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180042c44  xor     r8d, r8d; ulFlags
0x180042c47  lea     rdx, [rsp+230h+PropertyBuffer]; pDeviceID
0x180042c4c  lea     rcx, [rsp+230h+pdnDevInst]; pdnDevInst
0x180042c51  call    cs:__imp_CM_Locate_DevNodeW
0x180042c57  mov     ecx, [rsp+230h+pdnDevInst]; dnDevInst
0x180042c5b  lea     r9, [rsp+230h+var_1F0]; unsigned int *
0x180042c60  lea     r8, [rsp+230h+var_1F4]; unsigned int *
0x180042c65  mov     ebx, eax
0x180042c67  lea     rdx, [rsp+230h+var_1F8]; unsigned int *
0x180042c6c  call    ?FSGetDeviceStateByHDevInst@@YAJKPEAK00@Z; FSGetDeviceStateByHDevInst(ulong,ulong *,ulong *,ulong *)
0x180042c71  test    eax, eax
0x180042c73  js      short loc_180042C7B
0x180042c75  mov     ecx, [rsp+230h+var_1F8]
0x180042c79  mov     [rsi], ecx
0x180042c7b  test    ebx, ebx
0x180042c7d  jz      short loc_180042CB6
0x180042c7f  mov     edx, 0Dh; DefaultErr
0x180042c84  mov     ecx, ebx; CmReturnCode
0x180042c86  call    cs:__imp_CM_MapCrToWin32Err
0x180042c8c  mov     edi, eax
0x180042c8e  test    eax, eax
0x180042c90  jle     short loc_180042C9B
0x180042c92  movzx   edi, ax
0x180042c95  or      edi, 80070000h
0x180042c9b  test    edi, edi
0x180042c9d  jns     short loc_180042CB6
0x180042c9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042ca6  jb      loc_180042D73
0x180042cac  mov     edx, 34h ; '4'
0x180042cb1  jmp     loc_180042B72
0x180042cb6  mov     edi, [rsp+230h+var_1F4]
0x180042cba  test    edi, edi
0x180042cbc  jz      short loc_180042CDD
0x180042cbe  or      edi, 10000000h
0x180042cc4  jge     short loc_180042CDD
0x180042cc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042ccd  jb      loc_180042D73
0x180042cd3  mov     edx, 35h ; '5'
0x180042cd8  jmp     loc_180042B72
0x180042cdd  mov     ecx, [rsp+230h+pdnDevInst]; dnDevInst
0x180042ce1  test    r15b, r15b
0x180042ce4  jz      short loc_180042CF5
0x180042ce6  xor     edx, edx; ulFlags
0x180042ce8  call    cs:__imp_CM_Enable_DevNode
0x180042cee  mov     edi, 100h
0x180042cf3  jmp     short loc_180042D05
0x180042cf5  mov     edx, 0Ch; ulFlags
0x180042cfa  call    cs:__imp_CM_Disable_DevNode
0x180042d00  mov     edi, 2100h
0x180042d05  mov     ebx, eax
0x180042d07  test    eax, eax
0x180042d09  jz      short loc_180042D71
0x180042d0b  mov     ecx, [rsp+230h+pdnDevInst]; dnDevInst
0x180042d0f  lea     r9, [rsp+230h+var_1F0]; unsigned int *
0x180042d14  lea     r8, [rsp+230h+var_1F4]; unsigned int *
0x180042d19  lea     rdx, [rsp+230h+var_1F8]; unsigned int *
0x180042d1e  call    ?FSGetDeviceStateByHDevInst@@YAJKPEAK00@Z; FSGetDeviceStateByHDevInst(ulong,ulong *,ulong *,ulong *)
0x180042d23  test    eax, eax
0x180042d25  js      short loc_180042D3E
0x180042d27  mov     eax, [rsp+230h+var_1F8]
0x180042d2b  mov     [rsi], eax
0x180042d2d  mov     eax, edi
0x180042d2f  and     eax, [rsp+230h+var_1F4]
0x180042d33  cmp     eax, edi
0x180042d35  jnz     short loc_180042D3E
0x180042d37  mov     edi, 80070BC2h
0x180042d3c  jmp     short loc_180042D73
0x180042d3e  mov     edx, 0Dh; DefaultErr
0x180042d43  mov     ecx, ebx; CmReturnCode
0x180042d45  call    cs:__imp_CM_MapCrToWin32Err
0x180042d4b  mov     edi, eax
0x180042d4d  test    eax, eax
0x180042d4f  jle     short loc_180042D5A
0x180042d51  movzx   edi, ax
0x180042d54  or      edi, 80070000h
0x180042d5a  test    edi, edi
0x180042d5c  jns     short loc_180042D73
0x180042d5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042d65  jb      short loc_180042D73
0x180042d67  mov     edx, 36h ; '6'
0x180042d6c  jmp     loc_180042B72
0x180042d71  xor     edi, edi
0x180042d73  mov     eax, edi
0x180042d75  mov     rcx, [rbp+130h+var_30]
0x180042d7c  xor     rcx, rsp; StackCookie
0x180042d7f  call    __security_check_cookie
0x180042d84  mov     rbx, [rsp+230h+arg_8]
0x180042d8c  add     rsp, 210h
0x180042d93  pop     r15
0x180042d95  pop     r14
0x180042d97  pop     rdi
0x180042d98  pop     rsi
0x180042d99  pop     rbp
0x180042d9a  retn
```
