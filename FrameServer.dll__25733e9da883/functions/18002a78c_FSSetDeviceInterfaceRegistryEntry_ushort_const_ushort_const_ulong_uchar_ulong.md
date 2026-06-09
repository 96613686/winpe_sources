# FSSetDeviceInterfaceRegistryEntry(ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18002a78c`
- end: `0x18002a8b7`
- name: `?FSSetDeviceInterfaceRegistryEntry@@YAJPEBG0KPEAEK@Z`
- size: `299`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a5a0`

## callees

- `0x180009608`
- `0x180026ecc`
- `0x18002a78c`
- `0x18002b510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a809`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a809`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a85b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a85b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002a81b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002a81b`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18002a7e5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18002a7e5`

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
        if ( !g_wppLevels )
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
      if ( v9 < 0 && g_wppLevels )
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
0x18002a78c  push    rbx
0x18002a78e  push    rbp
0x18002a78f  push    rsi
0x18002a790  push    rdi
0x18002a791  sub     rsp, 38h
0x18002a795  mov     [rsp+58h+phkDeviceInterface], 0
0x18002a79e  mov     rsi, r9
0x18002a7a1  mov     ebp, r8d
0x18002a7a4  mov     rdi, rdx
0x18002a7a7  mov     rbx, rcx
0x18002a7aa  test    rcx, rcx
0x18002a7ad  jnz     short loc_18002A7B9
0x18002a7af  mov     ebx, 80070057h
0x18002a7b4  jmp     loc_18002A8A2
0x18002a7b9  test    rdi, rdi
0x18002a7bc  jz      short loc_18002A7AF
0x18002a7be  xor     edx, edx
0x18002a7c0  lea     rcx, [rsp+58h+phkDeviceInterface]
0x18002a7c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a7ca  lea     r9, [rsp+58h+phkDeviceInterface]; phkDeviceInterface
0x18002a7cf  mov     [rsp+58h+ulFlags], 0; ulFlags
0x18002a7d7  mov     edx, 20006h; samDesired
0x18002a7dc  mov     r8d, 1; Disposition
0x18002a7e2  mov     rcx, rbx; pszDeviceInterface
0x18002a7e5  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18002a7eb  test    eax, eax
0x18002a7ed  jnz     short loc_18002A814
0x18002a7ef  xor     ebx, ebx
0x18002a7f1  mov     eax, [rsp+58h+arg_20]
0x18002a7f8  test    rsi, rsi
0x18002a7fb  jnz     short loc_18002A844
0x18002a7fd  test    eax, eax
0x18002a7ff  jnz     short loc_18002A844
0x18002a801  mov     rcx, [rsp+58h+phkDeviceInterface]; hKey
0x18002a806  mov     rdx, rdi; lpValueName
0x18002a809  call    cs:__imp_RegDeleteValueW
0x18002a80f  jmp     loc_18002A8A2
0x18002a814  mov     edx, 0Dh; DefaultErr
0x18002a819  mov     ecx, eax; CmReturnCode
0x18002a81b  call    cs:__imp_CM_MapCrToWin32Err
0x18002a821  mov     ebx, eax
0x18002a823  test    eax, eax
0x18002a825  jle     short loc_18002A830
0x18002a827  movzx   ebx, ax
0x18002a82a  or      ebx, 80070000h
0x18002a830  test    ebx, ebx
0x18002a832  jns     short loc_18002A7F1
0x18002a834  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002a83b  jb      short loc_18002A8A2
0x18002a83d  mov     edx, 27h ; '''
0x18002a842  jmp     short loc_18002A884
0x18002a844  mov     rcx, [rsp+58h+phkDeviceInterface]; hKey
0x18002a849  mov     r9d, ebp; dwType
0x18002a84c  mov     [rsp+58h+cbData], eax; cbData
0x18002a850  xor     r8d, r8d; Reserved
0x18002a853  mov     rdx, rdi; lpValueName
0x18002a856  mov     qword ptr [rsp+58h+ulFlags], rsi; lpData
0x18002a85b  call    cs:__imp_RegSetValueExW
0x18002a861  mov     ebx, eax
0x18002a863  test    eax, eax
0x18002a865  jz      short loc_18002A8A2
0x18002a867  jle     short loc_18002A872
0x18002a869  movzx   ebx, ax
0x18002a86c  or      ebx, 80070000h
0x18002a872  test    ebx, ebx
0x18002a874  jns     short loc_18002A8A2
0x18002a876  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002a87d  jb      short loc_18002A8A2
0x18002a87f  mov     edx, 28h ; '('
0x18002a884  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a88b  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18002a892  xor     r9d, r9d
0x18002a895  mov     [rsp+58h+ulFlags], ebx
0x18002a899  mov     rcx, [rcx+10h]
0x18002a89d  call    WPP_SF_qD
0x18002a8a2  lea     rcx, [rsp+58h+phkDeviceInterface]
0x18002a8a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a8ac  mov     eax, ebx
0x18002a8ae  add     rsp, 38h
0x18002a8b2  pop     rdi
0x18002a8b3  pop     rsi
0x18002a8b4  pop     rbp
0x18002a8b5  pop     rbx
0x18002a8b6  retn
```
