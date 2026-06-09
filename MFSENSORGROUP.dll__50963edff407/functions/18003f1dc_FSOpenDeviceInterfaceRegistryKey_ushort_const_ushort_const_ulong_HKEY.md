# FSOpenDeviceInterfaceRegistryKey(ushort const *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18003f1dc`
- end: `0x18003f304`
- name: `?FSOpenDeviceInterfaceRegistryKey@@YAJPEBG0KPEAPEAUHKEY__@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpSubKey, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b248`
- `0x18005b8d8`
- `0x18005baa8`

## callees

- `0x180028e5c`
- `0x18003f1dc`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18003f244`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18003f244`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003f259`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003f259`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f2e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f2e7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f2c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f2c7`

## pseudocode

```c
__int64 __fastcall FSOpenDeviceInterfaceRegistryKey(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        PHKEY phkResult)
{
  unsigned int v8; // ebx
  CONFIGRET v9; // eax
  signed int v10; // eax
  LSTATUS Key; // eax
  HKEY phkDeviceInterface; // [rsp+70h] [rbp+8h] BYREF

  phkDeviceInterface = 0;
  if ( pszDeviceInterface )
  {
    if ( phkResult )
    {
      v8 = 0;
      *phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkDeviceInterface,
        0);
      v9 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, samDesired, 1u, &phkDeviceInterface, 0);
      if ( !v9 )
        goto LABEL_9;
      v10 = CM_MapCrToWin32Err(v9, 0xDu);
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
      {
LABEL_9:
        if ( !lpSubKey )
        {
          *phkResult = phkDeviceInterface;
          return v8;
        }
        if ( samDesired == 131097 )
          Key = RegOpenKeyExW(phkDeviceInterface, lpSubKey, 0, 0x20019u, phkResult);
        else
          Key = RegCreateKeyExW(phkDeviceInterface, lpSubKey, 0, 0, 0, samDesired, 0, phkResult, 0);
        if ( Key > 0 )
        {
          v8 = (unsigned __int16)Key | 0x80070000;
        }
        else if ( Key )
        {
          v8 = Key;
        }
      }
      if ( phkDeviceInterface )
        RegCloseKey(phkDeviceInterface);
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x18003f1dc  mov     [rsp+arg_8], rbx
0x18003f1e1  mov     [rsp+arg_10], rbp
0x18003f1e6  push    rsi
0x18003f1e7  push    rdi
0x18003f1e8  push    r14
0x18003f1ea  sub     rsp, 50h
0x18003f1ee  mov     [rsp+68h+phkDeviceInterface], 0
0x18003f1f7  mov     rdi, r9
0x18003f1fa  mov     ebp, r8d
0x18003f1fd  mov     rsi, rdx
0x18003f200  mov     r14, rcx
0x18003f203  test    rcx, rcx
0x18003f206  jnz     short loc_18003F212
0x18003f208  mov     ebx, 80070057h
0x18003f20d  jmp     loc_18003F2ED
0x18003f212  test    rdi, rdi
0x18003f215  jnz     short loc_18003F221
0x18003f217  mov     ebx, 80004003h
0x18003f21c  jmp     loc_18003F2ED
0x18003f221  xor     ebx, ebx
0x18003f223  lea     rcx, [rsp+68h+phkDeviceInterface]
0x18003f228  xor     edx, edx
0x18003f22a  mov     [r9], rbx
0x18003f22d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003f232  lea     r9, [rsp+68h+phkDeviceInterface]; phkDeviceInterface
0x18003f237  mov     [rsp+68h+ulFlags], ebx; ulFlags
0x18003f23b  lea     r8d, [rbx+1]; Disposition
0x18003f23f  mov     edx, ebp; samDesired
0x18003f241  mov     rcx, r14; pszDeviceInterface
0x18003f244  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18003f24a  mov     r14d, 80070000h
0x18003f250  test    eax, eax
0x18003f252  jz      short loc_18003F26F
0x18003f254  lea     edx, [rbx+0Dh]; DefaultErr
0x18003f257  mov     ecx, eax; CmReturnCode
0x18003f259  call    cs:__imp_CM_MapCrToWin32Err
0x18003f25f  mov     ebx, eax
0x18003f261  test    eax, eax
0x18003f263  jle     short loc_18003F26B
0x18003f265  movzx   ebx, ax
0x18003f268  or      ebx, r14d
0x18003f26b  test    ebx, ebx
0x18003f26d  js      short loc_18003F2DD
0x18003f26f  test    rsi, rsi
0x18003f272  jnz     short loc_18003F27E
0x18003f274  mov     rax, [rsp+68h+phkDeviceInterface]
0x18003f279  mov     [rdi], rax
0x18003f27c  jmp     short loc_18003F2ED
0x18003f27e  mov     rcx, [rsp+68h+phkDeviceInterface]; hKey
0x18003f283  mov     r9d, 20019h; samDesired
0x18003f289  xor     r8d, r8d; Reserved
0x18003f28c  mov     rdx, rsi; lpSubKey
0x18003f28f  cmp     ebp, r9d
0x18003f292  jnz     short loc_18003F2A1
0x18003f294  mov     qword ptr [rsp+68h+ulFlags], rdi; phkResult
0x18003f299  call    cs:__imp_RegOpenKeyExW
0x18003f29f  jmp     short loc_18003F2CD
0x18003f2a1  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18003f2aa  xor     r9d, r9d; lpClass
0x18003f2ad  mov     [rsp+68h+phkResult], rdi; phkResult
0x18003f2b2  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003f2bb  mov     [rsp+68h+samDesired], ebp; samDesired
0x18003f2bf  mov     [rsp+68h+ulFlags], 0; dwOptions
0x18003f2c7  call    cs:__imp_RegCreateKeyExW
0x18003f2cd  test    eax, eax
0x18003f2cf  jg      short loc_18003F2D7
0x18003f2d1  jz      short loc_18003F2DD
0x18003f2d3  mov     ebx, eax
0x18003f2d5  jmp     short loc_18003F2DD
0x18003f2d7  movzx   ebx, ax
0x18003f2da  or      ebx, r14d
0x18003f2dd  mov     rcx, [rsp+68h+phkDeviceInterface]; hKey
0x18003f2e2  test    rcx, rcx
0x18003f2e5  jz      short loc_18003F2ED
0x18003f2e7  call    cs:__imp_RegCloseKey
0x18003f2ed  lea     r11, [rsp+68h+var_18]
0x18003f2f2  mov     eax, ebx
0x18003f2f4  mov     rbx, [r11+28h]
0x18003f2f8  mov     rbp, [r11+30h]
0x18003f2fc  mov     rsp, r11
0x18003f2ff  pop     r14
0x18003f301  pop     rdi
0x18003f302  pop     rsi
0x18003f303  retn
```
