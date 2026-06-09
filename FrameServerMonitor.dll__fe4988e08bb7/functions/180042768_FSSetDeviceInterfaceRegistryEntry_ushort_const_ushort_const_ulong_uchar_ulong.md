# FSSetDeviceInterfaceRegistryEntry(ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x180042768`
- end: `0x180042893`
- name: `?FSSetDeviceInterfaceRegistryEntry@@YAJPEBG0KPEAEK@Z`
- size: `299`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004257c`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18000e6bc`
- `0x180017b98`
- `0x180042768`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800427e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800427e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042837`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042837`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800427f7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800427f7`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800427c1`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800427c1`

## pseudocode

```c
__int64 __fastcall FSSetDeviceInterfaceRegistryEntry(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  signed int v9; // ebx
  CONFIGRET v10; // eax
  signed int v11; // eax
  __int64 v12; // rdx
  LSTATUS v13; // eax
  HKEY phkDeviceInterface; // [rsp+60h] [rbp+8h] BYREF

  phkDeviceInterface = 0;
  if ( pszDeviceInterface && lpValueName )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkDeviceInterface,
      0);
    v10 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20006u, 1u, &phkDeviceInterface, 0);
    if ( v10 )
    {
      v11 = CM_MapCrToWin32Err(v10, 0xDu);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_21;
        v12 = 39;
LABEL_20:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v9);
        goto LABEL_21;
      }
    }
    else
    {
      v9 = 0;
    }
    if ( !lpData && !cbData )
    {
      RegDeleteValueW(phkDeviceInterface, lpValueName);
      goto LABEL_21;
    }
    v13 = RegSetValueExW(phkDeviceInterface, lpValueName, 0, dwType, lpData, cbData);
    v9 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      if ( v9 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 40;
        goto LABEL_20;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180042768  push    rbx
0x18004276a  push    rbp
0x18004276b  push    rsi
0x18004276c  push    rdi
0x18004276d  sub     rsp, 38h
0x180042771  mov     [rsp+58h+phkDeviceInterface], 0
0x18004277a  mov     rsi, r9
0x18004277d  mov     ebp, r8d
0x180042780  mov     rdi, rdx
0x180042783  mov     rbx, rcx
0x180042786  test    rcx, rcx
0x180042789  jnz     short loc_180042795
0x18004278b  mov     ebx, 80070057h
0x180042790  jmp     loc_18004287E
0x180042795  test    rdi, rdi
0x180042798  jz      short loc_18004278B
0x18004279a  xor     edx, edx
0x18004279c  lea     rcx, [rsp+58h+phkDeviceInterface]
0x1800427a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800427a6  lea     r9, [rsp+58h+phkDeviceInterface]; phkDeviceInterface
0x1800427ab  mov     [rsp+58h+ulFlags], 0; ulFlags
0x1800427b3  mov     edx, 20006h; samDesired
0x1800427b8  mov     r8d, 1; Disposition
0x1800427be  mov     rcx, rbx; pszDeviceInterface
0x1800427c1  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x1800427c7  test    eax, eax
0x1800427c9  jnz     short loc_1800427F0
0x1800427cb  xor     ebx, ebx
0x1800427cd  mov     eax, [rsp+58h+arg_20]
0x1800427d4  test    rsi, rsi
0x1800427d7  jnz     short loc_180042820
0x1800427d9  test    eax, eax
0x1800427db  jnz     short loc_180042820
0x1800427dd  mov     rcx, [rsp+58h+phkDeviceInterface]; hKey
0x1800427e2  mov     rdx, rdi; lpValueName
0x1800427e5  call    cs:__imp_RegDeleteValueW
0x1800427eb  jmp     loc_18004287E
0x1800427f0  mov     edx, 0Dh; DefaultErr
0x1800427f5  mov     ecx, eax; CmReturnCode
0x1800427f7  call    cs:__imp_CM_MapCrToWin32Err
0x1800427fd  mov     ebx, eax
0x1800427ff  test    eax, eax
0x180042801  jle     short loc_18004280C
0x180042803  movzx   ebx, ax
0x180042806  or      ebx, 80070000h
0x18004280c  test    ebx, ebx
0x18004280e  jns     short loc_1800427CD
0x180042810  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042815  cmp     al, 1
0x180042817  jb      short loc_18004287E
0x180042819  mov     edx, 27h ; '''
0x18004281e  jmp     short loc_180042860
0x180042820  mov     rcx, [rsp+58h+phkDeviceInterface]; hKey
0x180042825  mov     r9d, ebp; dwType
0x180042828  mov     [rsp+58h+cbData], eax; cbData
0x18004282c  xor     r8d, r8d; Reserved
0x18004282f  mov     rdx, rdi; lpValueName
0x180042832  mov     qword ptr [rsp+58h+ulFlags], rsi; lpData
0x180042837  call    cs:__imp_RegSetValueExW
0x18004283d  mov     ebx, eax
0x18004283f  test    eax, eax
0x180042841  jz      short loc_18004287E
0x180042843  jle     short loc_18004284E
0x180042845  movzx   ebx, ax
0x180042848  or      ebx, 80070000h
0x18004284e  test    ebx, ebx
0x180042850  jns     short loc_18004287E
0x180042852  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042857  cmp     al, 1
0x180042859  jb      short loc_18004287E
0x18004285b  mov     edx, 28h ; '('
0x180042860  mov     rcx, cs:WPP_GLOBAL_Control
0x180042867  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18004286e  xor     r9d, r9d
0x180042871  mov     [rsp+58h+ulFlags], ebx
0x180042875  mov     rcx, [rcx+10h]
0x180042879  call    WPP_SF_qD
0x18004287e  lea     rcx, [rsp+58h+phkDeviceInterface]
0x180042883  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042888  mov     eax, ebx
0x18004288a  add     rsp, 38h
0x18004288e  pop     rdi
0x18004288f  pop     rsi
0x180042890  pop     rbp
0x180042891  pop     rbx
0x180042892  retn
```
