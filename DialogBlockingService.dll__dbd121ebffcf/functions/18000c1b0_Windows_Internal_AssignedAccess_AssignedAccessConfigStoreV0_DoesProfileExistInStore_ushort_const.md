# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::DoesProfileExistInStore(ushort const *)

- ea: `0x18000c1b0`
- end: `0x18000c2aa`
- name: `?DoesProfileExistInStore@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@EEAA_NPEBG@Z`
- size: `250`
- prototype: `bool __fastcall(LPCWSTR *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000c1b0`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c248`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c29b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c248`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c29b`

## pseudocode

```c
bool __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::DoesProfileExistInStore(
        LPCWSTR *this,
        const unsigned __int16 *a2)
{
  bool IsValidProfile; // di
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *v7; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  IsValidProfile = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, this[1], 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    v6 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult);
    v5 = v6;
    if ( !v6 )
    {
      IsValidProfile = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(v7, phkResult);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      return IsValidProfile;
    }
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 < 0 )
    return 0;
  return IsValidProfile;
}

```

## disassembly

```asm
0x18000c1b0  mov     r11, rsp
0x18000c1b3  mov     [r11+10h], rbx
0x18000c1b7  mov     [r11+20h], rsi
0x18000c1bb  push    rdi
0x18000c1bc  sub     rsp, 30h
0x18000c1c0  mov     rsi, rdx
0x18000c1c3  xor     dil, dil
0x18000c1c6  mov     qword ptr [r11+8], 0
0x18000c1ce  lea     rax, [r11+8]
0x18000c1d2  mov     [r11-18h], rax
0x18000c1d6  mov     r9d, 20019h; samDesired
0x18000c1dc  xor     r8d, r8d; ulOptions
0x18000c1df  mov     rdx, [rcx+8]; lpSubKey
0x18000c1e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c1ea  call    cs:__imp_RegOpenKeyExW
0x18000c1f0  mov     ebx, eax
0x18000c1f2  test    eax, eax
0x18000c1f4  jz      short loc_18000C203
0x18000c1f6  jle     short loc_18000C24E
0x18000c1f8  movzx   ebx, ax
0x18000c1fb  or      ebx, 80070000h
0x18000c201  jmp     short loc_18000C24E
0x18000c203  mov     [rsp+38h+arg_10], 0
0x18000c20c  lea     rax, [rsp+38h+arg_10]
0x18000c211  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c216  mov     r9d, 20019h; samDesired
0x18000c21c  xor     r8d, r8d; ulOptions
0x18000c21f  mov     rdx, rsi; lpSubKey
0x18000c222  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c227  call    cs:__imp_RegOpenKeyExW
0x18000c22d  mov     ebx, eax
0x18000c22f  test    eax, eax
0x18000c231  jz      short loc_18000C274
0x18000c233  jle     short loc_18000C23E
0x18000c235  movzx   ebx, ax
0x18000c238  or      ebx, 80070000h
0x18000c23e  mov     rcx, [rsp+38h+arg_10]; hKey
0x18000c243  test    rcx, rcx
0x18000c246  jz      short loc_18000C24E
0x18000c248  call    cs:__imp_RegCloseKey
0x18000c24e  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c253  test    rcx, rcx
0x18000c256  jz      short loc_18000C25E
0x18000c258  call    cs:__imp_RegCloseKey
0x18000c25e  test    ebx, ebx
0x18000c260  jns     short loc_18000C2A1
0x18000c262  xor     al, al
0x18000c264  mov     rbx, [rsp+38h+arg_8]
0x18000c269  mov     rsi, [rsp+38h+arg_18]
0x18000c26e  add     rsp, 30h
0x18000c272  pop     rdi
0x18000c273  retn
0x18000c274  mov     rdx, [rsp+38h+arg_10]; HKEY
0x18000c279  call    ?IsValidProfile@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@AEAA_NPEAUHKEY__@@@Z; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(HKEY__ *)
0x18000c27e  mov     dil, al
0x18000c281  mov     rcx, [rsp+38h+arg_10]; hKey
0x18000c286  test    rcx, rcx
0x18000c289  jz      short loc_18000C291
0x18000c28b  call    cs:__imp_RegCloseKey
0x18000c291  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c296  test    rcx, rcx
0x18000c299  jz      short loc_18000C2A1
0x18000c29b  call    cs:__imp_RegCloseKey
0x18000c2a1  test    dil, dil
0x18000c2a4  jz      short loc_18000C262
0x18000c2a6  mov     al, 1
0x18000c2a8  jmp     short loc_18000C264
```
