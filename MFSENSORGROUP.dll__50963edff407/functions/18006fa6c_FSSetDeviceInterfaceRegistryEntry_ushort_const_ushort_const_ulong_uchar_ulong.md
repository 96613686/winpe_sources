# FSSetDeviceInterfaceRegistryEntry(ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18006fa6c`
- end: `0x18006fb7a`
- name: `?FSSetDeviceInterfaceRegistryEntry@@YAJPEBG0KPEAEK@Z`
- size: `270`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180050310`

## callees

- `0x180005fa0`
- `0x180028d5c`
- `0x180028e5c`
- `0x18006fa6c`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006fac0`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006fac0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006fad1`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006fad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fb1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fb1c`

## pseudocode

```c
__int64 __fastcall FSSetDeviceInterfaceRegistryEntry(
        LPCWSTR pszDeviceInterface,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  signed int v6; // ebx
  CONFIGRET v7; // eax
  signed int v8; // eax
  __int64 v9; // rdx
  LSTATUS v10; // eax
  HKEY phkDeviceInterface; // [rsp+48h] [rbp+10h] BYREF

  phkDeviceInterface = 0;
  if ( !pszDeviceInterface )
  {
    v6 = -2147024809;
    goto LABEL_16;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkDeviceInterface,
    0);
  v7 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20006u, 1u, &phkDeviceInterface, 0);
  if ( v7 )
  {
    v8 = CM_MapCrToWin32Err(v7, 0xDu);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_16;
      v9 = 39;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v6);
      goto LABEL_16;
    }
  }
  v10 = RegSetValueExW(phkDeviceInterface, L"FSSensorGroupHashSalt", 0, 3u, a4, 8u);
  v6 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( v6 < 0 && g_wppLevels )
    {
      v9 = 40;
      goto LABEL_15;
    }
  }
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006fa6c  mov     [rsp+arg_0], rbx
0x18006fa71  mov     [rsp+phkDeviceInterface], rdx
0x18006fa76  push    rdi
0x18006fa77  sub     rsp, 30h
0x18006fa7b  mov     [rsp+38h+phkDeviceInterface], 0
0x18006fa84  mov     rdi, r9
0x18006fa87  mov     rbx, rcx
0x18006fa8a  test    rcx, rcx
0x18006fa8d  jnz     short loc_18006FA99
0x18006fa8f  mov     ebx, 80070057h
0x18006fa94  jmp     loc_18006FB63
0x18006fa99  xor     edx, edx
0x18006fa9b  lea     rcx, [rsp+38h+phkDeviceInterface]
0x18006faa0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006faa5  lea     r9, [rsp+38h+phkDeviceInterface]; phkDeviceInterface
0x18006faaa  mov     [rsp+38h+ulFlags], 0; ulFlags
0x18006fab2  mov     edx, 20006h; samDesired
0x18006fab7  mov     r8d, 1; Disposition
0x18006fabd  mov     rcx, rbx; pszDeviceInterface
0x18006fac0  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18006fac6  test    eax, eax
0x18006fac8  jz      short loc_18006FAFA
0x18006faca  mov     edx, 0Dh; DefaultErr
0x18006facf  mov     ecx, eax; CmReturnCode
0x18006fad1  call    cs:__imp_CM_MapCrToWin32Err
0x18006fad7  mov     ebx, eax
0x18006fad9  test    eax, eax
0x18006fadb  jle     short loc_18006FAE6
0x18006fadd  movzx   ebx, ax
0x18006fae0  or      ebx, 80070000h
0x18006fae6  test    ebx, ebx
0x18006fae8  jns     short loc_18006FAFA
0x18006faea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006faf1  jb      short loc_18006FB63
0x18006faf3  mov     edx, 27h ; '''
0x18006faf8  jmp     short loc_18006FB45
0x18006fafa  mov     rcx, [rsp+38h+phkDeviceInterface]; hKey
0x18006faff  lea     rdx, ValueName; "FSSensorGroupHashSalt"
0x18006fb06  mov     [rsp+38h+cbData], 8; cbData
0x18006fb0e  mov     r9d, 3; dwType
0x18006fb14  xor     r8d, r8d; Reserved
0x18006fb17  mov     qword ptr [rsp+38h+ulFlags], rdi; lpData
0x18006fb1c  call    cs:__imp_RegSetValueExW
0x18006fb22  mov     ebx, eax
0x18006fb24  test    eax, eax
0x18006fb26  jz      short loc_18006FB63
0x18006fb28  jle     short loc_18006FB33
0x18006fb2a  movzx   ebx, ax
0x18006fb2d  or      ebx, 80070000h
0x18006fb33  test    ebx, ebx
0x18006fb35  jns     short loc_18006FB63
0x18006fb37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fb3e  jb      short loc_18006FB63
0x18006fb40  mov     edx, 28h ; '('
0x18006fb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fb4c  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18006fb53  xor     r9d, r9d
0x18006fb56  mov     [rsp+38h+ulFlags], ebx
0x18006fb5a  mov     rcx, [rcx+10h]
0x18006fb5e  call    WPP_SF_qD
0x18006fb63  lea     rcx, [rsp+38h+phkDeviceInterface]
0x18006fb68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006fb6d  mov     eax, ebx
0x18006fb6f  mov     rbx, [rsp+38h+arg_0]
0x18006fb74  add     rsp, 30h
0x18006fb78  pop     rdi
0x18006fb79  retn
```
