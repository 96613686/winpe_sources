# QueryStorageRegSetting(ushort const *,ulong,void *)

- ea: `0x18003f008`
- end: `0x18003f17f`
- name: `?QueryStorageRegSetting@@YAJPEBGKPEAX@Z`
- size: `375`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020c3c`
- `0x180023bac`
- `0x180037044`

## callees

- `0x18000d030`
- `0x18003f008`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18003f089`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003f089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f151`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f0f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f135`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f0f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f135`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18003f0ba`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18003f0ba`

## string_xrefs

- `0x18003f06d`: `StorageSenseParamsID`

## pseudocode

```c
__int64 __fastcall QueryStorageRegSetting(LPCWSTR lpValueName, int a2, BYTE *a3)
{
  int PersistedStateLocation; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  int v15[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  Type = 0;
  cbData = 0;
  v15[0] = 520;
  phkResult = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"StorageSenseParamsID",
                             0,
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters",
                             0,
                             SubKey,
                             520,
                             v15);
  v7 = PersistedStateLocation;
  if ( PersistedStateLocation > 0 )
    v7 = (unsigned __int16)PersistedStateLocation | 0x80070000;
  if ( v7 >= 0 )
  {
    v8 = RegOpenKeyW(HKEY_LOCAL_MACHINE, SubKey, &phkResult);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      v9 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, 0, &cbData);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v7 >= 0 )
      {
        if ( cbData == a2 )
        {
          v10 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, a3, &cbData);
          v7 = v10;
          if ( v10 > 0 )
            v7 = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          v7 = -2147024809;
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003f008  mov     [rsp-8+arg_8], rbx
0x18003f00d  push    rbp
0x18003f00e  push    rsi
0x18003f00f  push    rdi
0x18003f010  push    r12
0x18003f012  push    r14
0x18003f014  lea     rbp, [rsp-180h]
0x18003f01c  sub     rsp, 280h
0x18003f023  mov     rax, cs:__security_cookie
0x18003f02a  xor     rax, rsp
0x18003f02d  mov     [rbp+1A0h+var_30], rax
0x18003f034  mov     rdi, rcx
0x18003f037  mov     [rsp+2A0h+Type], 0
0x18003f03f  mov     ecx, 208h
0x18003f044  mov     [rsp+2A0h+cbData], 0
0x18003f04c  lea     rax, [rsp+2A0h+var_250]
0x18003f051  mov     [rsp+2A0h+var_250], ecx
0x18003f055  mov     [rsp+2A0h+var_270], rax
0x18003f05a  mov     r14, r8
0x18003f05d  mov     dword ptr [rsp+2A0h+lpcbData], ecx
0x18003f061  lea     rax, [rsp+2A0h+SubKey]
0x18003f066  mov     esi, edx
0x18003f068  mov     [rsp+2A0h+lpData], rax
0x18003f06d  lea     rcx, aStoragesensepa; "StorageSenseParamsID"
0x18003f074  mov     [rsp+2A0h+phkResult], 0
0x18003f07d  xor     r9d, r9d
0x18003f080  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003f087  xor     edx, edx
0x18003f089  call    cs:__imp_RtlGetPersistedStateLocation
0x18003f08f  mov     ebx, eax
0x18003f091  mov     r12d, 80070000h
0x18003f097  test    eax, eax
0x18003f099  jle     short loc_18003F0A1
0x18003f09b  movzx   ebx, ax
0x18003f09e  or      ebx, r12d
0x18003f0a1  test    ebx, ebx
0x18003f0a3  js      loc_18003F147
0x18003f0a9  lea     r8, [rsp+2A0h+phkResult]; phkResult
0x18003f0ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f0b5  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18003f0ba  call    cs:__imp_RegOpenKeyW
0x18003f0c0  mov     ebx, eax
0x18003f0c2  test    eax, eax
0x18003f0c4  jle     short loc_18003F0CC
0x18003f0c6  movzx   ebx, ax
0x18003f0c9  or      ebx, r12d
0x18003f0cc  test    ebx, ebx
0x18003f0ce  js      short loc_18003F147
0x18003f0d0  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18003f0d5  lea     rax, [rsp+2A0h+cbData]
0x18003f0da  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18003f0df  lea     r9, [rsp+2A0h+Type]; lpType
0x18003f0e4  xor     r8d, r8d; lpReserved
0x18003f0e7  mov     [rsp+2A0h+lpData], 0; lpData
0x18003f0f0  mov     rdx, rdi; lpValueName
0x18003f0f3  call    cs:__imp_RegQueryValueExW
0x18003f0f9  mov     ebx, eax
0x18003f0fb  test    eax, eax
0x18003f0fd  jle     short loc_18003F105
0x18003f0ff  movzx   ebx, ax
0x18003f102  or      ebx, r12d
0x18003f105  test    ebx, ebx
0x18003f107  js      short loc_18003F147
0x18003f109  cmp     [rsp+2A0h+cbData], esi
0x18003f10d  jz      short loc_18003F116
0x18003f10f  mov     ebx, 80070057h
0x18003f114  jmp     short loc_18003F147
0x18003f116  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18003f11b  lea     rax, [rsp+2A0h+cbData]
0x18003f120  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18003f125  lea     r9, [rsp+2A0h+Type]; lpType
0x18003f12a  xor     r8d, r8d; lpReserved
0x18003f12d  mov     [rsp+2A0h+lpData], r14; lpData
0x18003f132  mov     rdx, rdi; lpValueName
0x18003f135  call    cs:__imp_RegQueryValueExW
0x18003f13b  mov     ebx, eax
0x18003f13d  test    eax, eax
0x18003f13f  jle     short loc_18003F147
0x18003f141  movzx   ebx, ax
0x18003f144  or      ebx, r12d
0x18003f147  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x18003f14c  test    rcx, rcx
0x18003f14f  jz      short loc_18003F157
0x18003f151  call    cs:__imp_RegCloseKey
0x18003f157  mov     eax, ebx
0x18003f159  mov     rcx, [rbp+1A0h+var_30]
0x18003f160  xor     rcx, rsp; StackCookie
0x18003f163  call    __security_check_cookie
0x18003f168  mov     rbx, [rsp+2A0h+arg_8]
0x18003f170  add     rsp, 280h
0x18003f177  pop     r14
0x18003f179  pop     r12
0x18003f17b  pop     rdi
0x18003f17c  pop     rsi
0x18003f17d  pop     rbp
0x18003f17e  retn
```
