# F12::GetInitialPluginInfo(PluginId &)

- ea: `0x18002fda4`
- end: `0x18002fe66`
- name: `?GetInitialPluginInfo@F12@@YAJAEAW4PluginId@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(F12 *__hidden this, enum PluginId *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f024`

## callees

- `0x18002fda4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002fe3e`
- `ADVAPI32!RegCloseKey` at `0x18002fe50`
- `ADVAPI32!RegCloseKey` at `0x18002fe3e`
- `ADVAPI32!RegCloseKey` at `0x18002fe50`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fdda`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fdda`
- `ADVAPI32!RegQueryValueExW` at `0x18002fe1f`
- `ADVAPI32!RegQueryValueExW` at `0x18002fe1f`

## string_xrefs

- `0x18002fdf2`: `lastselectedpluginid`

## pseudocode

```c
__int64 __fastcall F12::GetInitialPluginInfo(F12 *this, enum PluginId *a2)
{
  HKEY v3; // rbx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x20019u, &hKey) )
    return 2147500037LL;
  v3 = hKey;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"lastselectedpluginid", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    if ( v3 )
      RegCloseKey(v3);
    return 2147500037LL;
  }
  *(_DWORD *)this = Data;
  if ( v3 )
    RegCloseKey(v3);
  return 0;
}

```

## disassembly

```asm
0x18002fda4  mov     r11, rsp
0x18002fda7  mov     [r11+8], rbx
0x18002fdab  push    rdi
0x18002fdac  sub     rsp, 40h
0x18002fdb0  mov     rdi, rcx
0x18002fdb3  mov     qword ptr [r11-18h], 0
0x18002fdbb  lea     rax, [r11-18h]
0x18002fdbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002fdc6  mov     r9d, 20019h; samDesired
0x18002fdcc  mov     [r11-28h], rax
0x18002fdd0  xor     r8d, r8d; ulOptions
0x18002fdd3  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x18002fdda  call    cs:__imp_RegOpenKeyExW
0x18002fde0  test    eax, eax
0x18002fde2  jnz     short loc_18002FE56
0x18002fde4  mov     rbx, [rsp+48h+hKey]
0x18002fde9  lea     r9, [rsp+48h+Type]; lpType
0x18002fdee  mov     [rsp+48h+Data], eax
0x18002fdf2  lea     rdx, aLastselectedpl; "lastselectedpluginid"
0x18002fdf9  mov     [rsp+48h+Type], eax
0x18002fdfd  xor     r8d, r8d; lpReserved
0x18002fe00  lea     rax, [rsp+48h+cbData]
0x18002fe05  mov     [rsp+48h+cbData], 4
0x18002fe0d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002fe12  mov     rcx, rbx; hKey
0x18002fe15  lea     rax, [rsp+48h+Data]
0x18002fe1a  mov     [rsp+48h+lpData], rax; lpData
0x18002fe1f  call    cs:__imp_RegQueryValueExW
0x18002fe25  test    eax, eax
0x18002fe27  jnz     short loc_18002FE48
0x18002fe29  cmp     [rsp+48h+Type], 4
0x18002fe2e  jnz     short loc_18002FE48
0x18002fe30  mov     eax, [rsp+48h+Data]
0x18002fe34  mov     [rdi], eax
0x18002fe36  test    rbx, rbx
0x18002fe39  jz      short loc_18002FE44
0x18002fe3b  mov     rcx, rbx; hKey
0x18002fe3e  call    cs:__imp_RegCloseKey
0x18002fe44  xor     eax, eax
0x18002fe46  jmp     short loc_18002FE5B
0x18002fe48  test    rbx, rbx
0x18002fe4b  jz      short loc_18002FE56
0x18002fe4d  mov     rcx, rbx; hKey
0x18002fe50  call    cs:__imp_RegCloseKey
0x18002fe56  mov     eax, 80004005h
0x18002fe5b  mov     rbx, [rsp+48h+arg_0]
0x18002fe60  add     rsp, 40h
0x18002fe64  pop     rdi
0x18002fe65  retn
```
