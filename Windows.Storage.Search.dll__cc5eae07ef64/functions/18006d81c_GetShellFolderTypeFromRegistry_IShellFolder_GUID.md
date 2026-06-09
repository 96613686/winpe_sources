# GetShellFolderTypeFromRegistry(IShellFolder *,_GUID *)

- ea: `0x18006d81c`
- end: `0x18006d93e`
- name: `?GetShellFolderTypeFromRegistry@@YAJPEAUIShellFolder@@PEAU_GUID@@@Z`
- size: `290`
- prototype: `int(struct IShellFolder *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bc310`

## callees

- `0x18006d81c`
- `0x180071dc0`

## import_xrefs

- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18006d894`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18006d894`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18006d857`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18006d857`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x18006d905`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x18006d905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d912`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006d8d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006d8d9`

## pseudocode

```c
__int64 __fastcall GetShellFolderTypeFromRegistry(struct IShellFolder *a1, struct _GUID *a2)
{
  int ClassID; // ebx
  bool v4; // sf
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v8; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR psz[264]; // [rsp+60h] [rbp-A0h] BYREF

  v8 = 0;
  ClassID = IUnknown_GetClassID(a1, &v8);
  if ( ClassID < 0 )
    return (unsigned int)ClassID;
  hkey = 0;
  ClassID = SHRegGetCLSIDKey(&v8, L"ShellFolder", 0, 0, 1, &hkey);
  if ( ClassID < 0 )
    return (unsigned int)ClassID;
  pcbData = 520;
  ClassID = RegGetValueW(hkey, 0, L"FolderType", 2u, 0, psz, &pcbData);
  if ( !ClassID )
    goto LABEL_6;
  psz[0] = 0;
  v4 = ClassID < 0;
  if ( ClassID > 0 )
  {
    ClassID = (unsigned __int16)ClassID | 0x80070000;
LABEL_6:
    v4 = ClassID < 0;
  }
  if ( !v4 )
    ClassID = SHCLSIDFromString(psz, a2);
  RegCloseKey(hkey);
  return (unsigned int)ClassID;
}

```

## disassembly

```asm
0x18006d81c  mov     [rsp-8+arg_10], rbx
0x18006d821  mov     [rsp-8+arg_18], rdi
0x18006d826  push    rbp
0x18006d827  lea     rbp, [rsp-180h]
0x18006d82f  sub     rsp, 280h
0x18006d836  mov     rax, cs:__security_cookie
0x18006d83d  xor     rax, rsp
0x18006d840  mov     [rbp+180h+var_10], rax
0x18006d847  mov     rdi, rdx
0x18006d84a  xorps   xmm0, xmm0
0x18006d84d  lea     rdx, [rsp+280h+var_230]
0x18006d852  movups  [rsp+280h+var_230], xmm0
0x18006d857  call    cs:__imp_IUnknown_GetClassID
0x18006d85d  mov     ebx, eax
0x18006d85f  test    eax, eax
0x18006d861  js      loc_18006D918
0x18006d867  lea     rax, [rsp+280h+hkey]
0x18006d86c  mov     [rsp+280h+hkey], 0
0x18006d875  mov     [rsp+280h+pvData], rax
0x18006d87a  lea     rdx, aShellfolder; "ShellFolder"
0x18006d881  xor     r9d, r9d
0x18006d884  mov     dword ptr [rsp+280h+pdwType], 1
0x18006d88c  xor     r8d, r8d
0x18006d88f  lea     rcx, [rsp+280h+var_230]
0x18006d894  call    cs:__imp_SHRegGetCLSIDKey
0x18006d89a  mov     ebx, eax
0x18006d89c  test    eax, eax
0x18006d89e  js      short loc_18006D918
0x18006d8a0  mov     rcx, [rsp+280h+hkey]; hkey
0x18006d8a5  lea     rax, [rsp+280h+var_240]
0x18006d8aa  mov     [rsp+280h+pcbData], rax; pcbData
0x18006d8af  lea     r8, aFoldertype; "FolderType"
0x18006d8b6  lea     rax, [rsp+280h+psz]
0x18006d8bb  mov     [rsp+280h+var_240], 208h
0x18006d8c3  mov     [rsp+280h+pvData], rax; pvData
0x18006d8c8  mov     r9d, 2; dwFlags
0x18006d8ce  xor     edx, edx; lpSubKey
0x18006d8d0  mov     [rsp+280h+pdwType], 0; pdwType
0x18006d8d9  call    cs:__imp_RegGetValueW
0x18006d8df  mov     ebx, eax
0x18006d8e1  test    eax, eax
0x18006d8e3  jz      short loc_18006D8F9
0x18006d8e5  xor     eax, eax
0x18006d8e7  mov     [rsp+280h+psz], ax
0x18006d8ec  test    ebx, ebx
0x18006d8ee  jle     short loc_18006D8FB
0x18006d8f0  movzx   ebx, bx
0x18006d8f3  or      ebx, 80070000h
0x18006d8f9  test    ebx, ebx
0x18006d8fb  js      short loc_18006D90D
0x18006d8fd  mov     rdx, rdi; pclsid
0x18006d900  lea     rcx, [rsp+280h+psz]; psz
0x18006d905  call    cs:__imp_SHCLSIDFromString
0x18006d90b  mov     ebx, eax
0x18006d90d  mov     rcx, [rsp+280h+hkey]; hKey
0x18006d912  call    cs:__imp_RegCloseKey
0x18006d918  mov     eax, ebx
0x18006d91a  mov     rcx, [rbp+180h+var_10]
0x18006d921  xor     rcx, rsp; StackCookie
0x18006d924  call    __security_check_cookie
0x18006d929  lea     r11, [rsp+280h+var_s0]
0x18006d931  mov     rbx, [r11+20h]
0x18006d935  mov     rdi, [r11+28h]
0x18006d939  mov     rsp, r11
0x18006d93c  pop     rbp
0x18006d93d  retn
```
