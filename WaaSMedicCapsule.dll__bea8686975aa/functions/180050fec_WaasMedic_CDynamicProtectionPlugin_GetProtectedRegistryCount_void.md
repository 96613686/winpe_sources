# WaasMedic::CDynamicProtectionPlugin::GetProtectedRegistryCount(void)

- ea: `0x180050fec`
- end: `0x1800510c7`
- name: `?GetProtectedRegistryCount@CDynamicProtectionPlugin@WaasMedic@@SAKXZ`
- size: `219`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050b60`

## callees

- `0x18002543c`
- `0x180050fec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051085`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051085`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005102e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005102e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510b7`

## string_xrefs

- `0x180051042`: `Could not get handle to the registry store key. Error code: 0x%08x`
- `0x180051099`: `Could not get query the registry store key. Error code: 0x%08x`

## pseudocode

```c
__int64 WaasMedic::CDynamicProtectionPlugin::GetProtectedRegistryCount(void)
{
  int v0; // eax
  int v1; // eax
  DWORD cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  cSubKeys = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, &word_180098670, 0, 0, 0, 1u, 0, &hKey, 0);
  if ( v0 )
  {
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    LogLevelW(2u, L"Could not get handle to the registry store key. Error code: 0x%08x", (unsigned int)v0);
  }
  else
  {
    v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v1 )
    {
      if ( v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
      LogLevelW(2u, L"Could not get query the registry store key. Error code: 0x%08x", (unsigned int)v1);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return cSubKeys;
}

```

## disassembly

```asm
0x180050fec  mov     r11, rsp
0x180050fef  push    rbx
0x180050ff0  sub     rsp, 60h
0x180050ff4  xor     ebx, ebx
0x180050ff6  lea     rax, [r11+10h]
0x180050ffa  mov     [r11-28h], rbx
0x180050ffe  lea     rdx, word_180098670; lpSubKey
0x180051005  mov     [r11-30h], rax
0x180051009  xor     r9d, r9d; lpClass
0x18005100c  mov     [r11-38h], rbx
0x180051010  xor     r8d, r8d; Reserved
0x180051013  mov     [rsp+68h+samDesired], 1; samDesired
0x18005101b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051022  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x180051026  mov     [r11+10h], rbx
0x18005102a  mov     [rsp+68h+cSubKeys], ebx
0x18005102e  call    cs:__imp_RegCreateKeyExW
0x180051034  test    eax, eax
0x180051036  jz      short loc_18005104B
0x180051038  jle     short loc_180051042
0x18005103a  movzx   eax, ax
0x18005103d  or      eax, 80070000h
0x180051042  lea     rdx, aCouldNotGetHan; "Could not get handle to the registry st"...
0x180051049  jmp     short loc_1800510A0
0x18005104b  mov     rcx, [rsp+68h+hKey]; hKey
0x180051050  lea     rax, [rsp+68h+cSubKeys]
0x180051055  mov     [rsp+68h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18005105a  xor     r9d, r9d; lpReserved
0x18005105d  mov     [rsp+68h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180051062  xor     r8d, r8d; lpcchClass
0x180051065  mov     [rsp+68h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18005106a  xor     edx, edx; lpClass
0x18005106c  mov     [rsp+68h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180051071  mov     [rsp+68h+lpcValues], rbx; lpcValues
0x180051076  mov     [rsp+68h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18005107b  mov     qword ptr [rsp+68h+samDesired], rbx; lpcbMaxSubKeyLen
0x180051080  mov     qword ptr [rsp+68h+dwOptions], rax; lpcSubKeys
0x180051085  call    cs:__imp_RegQueryInfoKeyW
0x18005108b  test    eax, eax
0x18005108d  jz      short loc_1800510AD
0x18005108f  jle     short loc_180051099
0x180051091  movzx   eax, ax
0x180051094  or      eax, 80070000h
0x180051099  lea     rdx, aCouldNotGetQue; "Could not get query the registry store "...
0x1800510a0  mov     r8d, eax
0x1800510a3  mov     ecx, 2; unsigned __int8
0x1800510a8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800510ad  mov     rcx, [rsp+68h+hKey]; hKey
0x1800510b2  test    rcx, rcx
0x1800510b5  jz      short loc_1800510BD
0x1800510b7  call    cs:__imp_RegCloseKey
0x1800510bd  mov     eax, [rsp+68h+cSubKeys]
0x1800510c1  add     rsp, 60h
0x1800510c5  pop     rbx
0x1800510c6  retn
```
