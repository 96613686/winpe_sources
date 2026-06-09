# LoadProfileForDevice(ushort const *,CTUnkArray<IMFSensorProfileInternal> &)

- ea: `0x18000b248`
- end: `0x18000b4dd`
- name: `?LoadProfileForDevice@@YAJPEBGAEAV?$CTUnkArray@UIMFSensorProfileInternal@@@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b790`

## callees

- `0x180005fa0`
- `0x180007348`
- `0x180008f9c`
- `0x1800099b4`
- `0x18000b248`
- `0x180028e5c`
- `0x18003f1dc`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18000b339`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18000b339`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000b34e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18000b34e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b2dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b2dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b382`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b382`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b3f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000b3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4ae`

## pseudocode

```c
__int64 __fastcall LoadProfileForDevice(LPCWSTR pszDeviceInterface, __int64 *a2)
{
  signed int v4; // ebx
  CONFIGRET v5; // eax
  signed int v6; // eax
  LSTATUS v7; // eax
  DWORD i; // edi
  HKEY phkDeviceInterface; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  cbData = 4;
  hKey = 0;
  phkResult = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( (int)FSOpenDeviceInterfaceRegistryKey(pszDeviceInterface, 0, 0x20019u, &hKey) < 0 )
    goto LABEL_26;
  if ( RegQueryValueExW(hKey, L"OEMCameraProfileVersion", 0, &Type, Data, &cbData) )
    goto LABEL_26;
  if ( Type != 4 )
    goto LABEL_26;
  if ( *(_DWORD *)Data < 2u )
    goto LABEL_26;
  phkDeviceInterface = 0;
  if ( !pszDeviceInterface )
    goto LABEL_26;
  phkResult = 0;
  v4 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkDeviceInterface,
    0);
  v5 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
  if ( !v5 )
    goto LABEL_10;
  v6 = CM_MapCrToWin32Err(v5, 0xDu);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_10:
    v7 = RegOpenKeyExW(phkDeviceInterface, L"Profiles", 0, 0x20019u, &phkResult);
    if ( v7 > 0 )
    {
      v4 = (unsigned __int16)v7 | 0x80070000;
    }
    else if ( v7 )
    {
      v4 = v7;
    }
  }
  if ( phkDeviceInterface )
    RegCloseKey(phkDeviceInterface);
  if ( v4 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      phkDeviceInterface = 0;
      if ( RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0) == 259
        || ProcessProfile(phkResult, Name, (struct IMFSensorProfileInternal **)&phkDeviceInterface) < 0 )
      {
        break;
      }
      if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(a2, (__int64)phkDeviceInterface) )
      {
        v4 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            193,
            &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
            0,
            -2147024882);
        break;
      }
      if ( phkDeviceInterface )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkDeviceInterface + 16LL))(phkDeviceInterface);
    }
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&phkDeviceInterface);
  }
  else
  {
LABEL_26:
    v4 = -1072875818;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b248  mov     [rsp-8+arg_10], rbx
0x18000b24d  mov     [rsp-8+arg_18], rsi
0x18000b252  push    rbp
0x18000b253  push    rdi
0x18000b254  push    r14
0x18000b256  lea     rbp, [rsp-190h]
0x18000b25e  sub     rsp, 290h
0x18000b265  mov     rax, cs:__security_cookie
0x18000b26c  xor     rax, rsp
0x18000b26f  mov     [rbp+1A0h+var_20], rax
0x18000b276  xor     r14d, r14d
0x18000b279  mov     [rsp+2A0h+cbData], 4
0x18000b281  mov     rsi, rdx
0x18000b284  mov     [rsp+2A0h+hKey], r14
0x18000b289  xor     edx, edx; lpSubKey
0x18000b28b  mov     [rsp+2A0h+phkResult], r14
0x18000b290  lea     r9, [rsp+2A0h+hKey]; phkResult
0x18000b295  mov     dword ptr [rsp+2A0h+Data], r14d
0x18000b29a  mov     r8d, 20019h; samDesired
0x18000b2a0  mov     [rsp+2A0h+Type], r14d
0x18000b2a5  mov     rdi, rcx
0x18000b2a8  call    ?FSOpenDeviceInterfaceRegistryKey@@YAJPEBG0KPEAPEAUHKEY__@@@Z; FSOpenDeviceInterfaceRegistryKey(ushort const *,ushort const *,ulong,HKEY__ * *)
0x18000b2ad  test    eax, eax
0x18000b2af  js      loc_18000B48A
0x18000b2b5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000b2ba  lea     rax, [rsp+2A0h+cbData]
0x18000b2bf  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18000b2c4  lea     r9, [rsp+2A0h+Type]; lpType
0x18000b2c9  lea     rax, [rsp+2A0h+Data]
0x18000b2ce  xor     r8d, r8d; lpReserved
0x18000b2d1  lea     rdx, aOemcameraprofi_0; "OEMCameraProfileVersion"
0x18000b2d8  mov     [rsp+2A0h+lpData], rax; lpData
0x18000b2dd  call    cs:__imp_RegQueryValueExW
0x18000b2e3  test    eax, eax
0x18000b2e5  jnz     loc_18000B48A
0x18000b2eb  cmp     [rsp+2A0h+Type], 4
0x18000b2f0  jnz     loc_18000B48A
0x18000b2f6  cmp     dword ptr [rsp+2A0h+Data], 2
0x18000b2fb  jb      loc_18000B48A
0x18000b301  mov     [rsp+2A0h+phkDeviceInterface], r14
0x18000b306  test    rdi, rdi
0x18000b309  jz      loc_18000B48A
0x18000b30f  xor     edx, edx
0x18000b311  mov     [rsp+2A0h+phkResult], r14
0x18000b316  lea     rcx, [rsp+2A0h+phkDeviceInterface]
0x18000b31b  mov     ebx, r14d
0x18000b31e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000b323  lea     r9, [rsp+2A0h+phkDeviceInterface]; phkDeviceInterface
0x18000b328  mov     dword ptr [rsp+2A0h+lpData], r14d; ulFlags
0x18000b32d  mov     edx, 20019h; samDesired
0x18000b332  lea     r8d, [r14+1]; Disposition
0x18000b336  mov     rcx, rdi; pszDeviceInterface
0x18000b339  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18000b33f  mov     edi, 80070000h
0x18000b344  test    eax, eax
0x18000b346  jz      short loc_18000B363
0x18000b348  lea     edx, [r14+0Dh]; DefaultErr
0x18000b34c  mov     ecx, eax; CmReturnCode
0x18000b34e  call    cs:__imp_CM_MapCrToWin32Err
0x18000b354  mov     ebx, eax
0x18000b356  test    eax, eax
0x18000b358  jle     short loc_18000B35F
0x18000b35a  movzx   ebx, ax
0x18000b35d  or      ebx, edi
0x18000b35f  test    ebx, ebx
0x18000b361  js      short loc_18000B397
0x18000b363  mov     rcx, [rsp+2A0h+phkDeviceInterface]; hKey
0x18000b368  lea     rax, [rsp+2A0h+phkResult]
0x18000b36d  mov     r9d, 20019h; samDesired
0x18000b373  mov     [rsp+2A0h+lpData], rax; phkResult
0x18000b378  xor     r8d, r8d; ulOptions
0x18000b37b  lea     rdx, aProfiles; "Profiles"
0x18000b382  call    cs:__imp_RegOpenKeyExW
0x18000b388  test    eax, eax
0x18000b38a  jg      short loc_18000B392
0x18000b38c  jz      short loc_18000B397
0x18000b38e  mov     ebx, eax
0x18000b390  jmp     short loc_18000B397
0x18000b392  movzx   ebx, ax
0x18000b395  or      ebx, edi
0x18000b397  mov     rcx, [rsp+2A0h+phkDeviceInterface]; hKey
0x18000b39c  test    rcx, rcx
0x18000b39f  jz      short loc_18000B3A7
0x18000b3a1  call    cs:__imp_RegCloseKey
0x18000b3a7  test    ebx, ebx
0x18000b3a9  js      loc_18000B48A
0x18000b3af  mov     edi, r14d
0x18000b3b2  xor     edx, edx; Val
0x18000b3b4  lea     rcx, [rsp+2A0h+Name]; void *
0x18000b3b9  mov     r8d, 208h; Size
0x18000b3bf  call    memset_0
0x18000b3c4  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18000b3c9  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000b3ce  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000b3d3  lea     r8, [rsp+2A0h+Name]; lpName
0x18000b3d8  mov     [rsp+2A0h+lpcchClass], r14; lpcchClass
0x18000b3dd  mov     edx, edi; dwIndex
0x18000b3df  mov     [rsp+2A0h+lpcbData], r14; lpClass
0x18000b3e4  mov     [rsp+2A0h+lpData], r14; lpReserved
0x18000b3e9  mov     [rsp+2A0h+cchName], 104h
0x18000b3f1  mov     [rsp+2A0h+phkDeviceInterface], r14
0x18000b3f6  call    cs:__imp_RegEnumKeyExW
0x18000b3fc  cmp     eax, 103h
0x18000b401  jz      short loc_18000B47E
0x18000b403  mov     rcx, [rsp+2A0h+phkResult]; HKEY
0x18000b408  lea     r8, [rsp+2A0h+phkDeviceInterface]; struct IMFSensorProfileInternal **
0x18000b40d  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x18000b412  call    ?ProcessProfile@@YAJPEAUHKEY__@@PEBGPEAPEAUIMFSensorProfileInternal@@@Z; ProcessProfile(HKEY__ *,ushort const *,IMFSensorProfileInternal * *)
0x18000b417  test    eax, eax
0x18000b419  js      short loc_18000B47E
0x18000b41b  mov     rdx, [rsp+2A0h+phkDeviceInterface]
0x18000b420  mov     rcx, rsi
0x18000b423  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18000b428  test    eax, eax
0x18000b42a  jz      short loc_18000B44D
0x18000b42c  mov     rcx, [rsp+2A0h+phkDeviceInterface]
0x18000b431  inc     edi
0x18000b433  test    rcx, rcx
0x18000b436  jz      loc_18000B3B2
0x18000b43c  mov     rax, [rcx]
0x18000b43f  mov     rax, [rax+10h]
0x18000b443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b448  jmp     loc_18000B3B2
0x18000b44d  mov     ebx, 8007000Eh
0x18000b452  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b459  jb      short loc_18000B47E
0x18000b45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b462  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18000b469  mov     edx, 0C1h
0x18000b46e  mov     dword ptr [rsp+2A0h+lpData], ebx
0x18000b472  xor     r9d, r9d
0x18000b475  mov     rcx, [rcx+10h]
0x18000b479  call    WPP_SF_qD
0x18000b47e  lea     rcx, [rsp+2A0h+phkDeviceInterface]
0x18000b483  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18000b488  jmp     short loc_18000B48F
0x18000b48a  mov     ebx, 0C00D36D6h
0x18000b48f  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18000b494  test    rcx, rcx
0x18000b497  jz      short loc_18000B4A4
0x18000b499  call    cs:__imp_RegCloseKey
0x18000b49f  mov     [rsp+2A0h+phkResult], r14
0x18000b4a4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000b4a9  test    rcx, rcx
0x18000b4ac  jz      short loc_18000B4B4
0x18000b4ae  call    cs:__imp_RegCloseKey
0x18000b4b4  mov     eax, ebx
0x18000b4b6  mov     rcx, [rbp+1A0h+var_20]
0x18000b4bd  xor     rcx, rsp; StackCookie
0x18000b4c0  call    __security_check_cookie
0x18000b4c5  lea     r11, [rsp+2A0h+var_10]
0x18000b4cd  mov     rbx, [r11+30h]
0x18000b4d1  mov     rsi, [r11+38h]
0x18000b4d5  mov     rsp, r11
0x18000b4d8  pop     r14
0x18000b4da  pop     rdi
0x18000b4db  pop     rbp
0x18000b4dc  retn
```
