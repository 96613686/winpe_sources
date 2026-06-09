# MappingExists(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180012d50`
- end: `0x180012e98`
- name: `?MappingExists@@YAHPEAUHKEY__@@PEBG11@Z`
- size: `328`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014440`

## callees

- `0x1800126c0`
- `0x180012d50`
- `0x18001b980`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180012df9`
- `KERNEL32!CompareStringW` at `0x180012df9`
- `ADVAPI32!RegQueryValueExW` at `0x180012e57`
- `ADVAPI32!RegQueryValueExW` at `0x180012e57`
- `ADVAPI32!RegCloseKey` at `0x180012e68`
- `ADVAPI32!RegCloseKey` at `0x180012e68`
- `ADVAPI32!RegOpenKeyExW` at `0x180012e28`
- `ADVAPI32!RegOpenKeyExW` at `0x180012e28`
- `ADVAPI32!RegEnumKeyW` at `0x180012db1`
- `ADVAPI32!RegEnumKeyW` at `0x180012db1`
- `SHLWAPI!StrChrW` at `0x180012dc7`
- `SHLWAPI!StrChrW` at `0x180012dc7`

## pseudocode

```c
__int64 __fastcall MappingExists(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v5; // ebx
  DWORD v6; // edi
  const WCHAR *v7; // rax
  HKEY phkResult; // [rsp+30h] [rbp-C8h] BYREF
  WCHAR Name[32]; // [rsp+40h] [rbp-B8h] BYREF
  WCHAR ValueName[32]; // [rsp+80h] [rbp-78h] BYREF

  v5 = 0;
  Convert2CRC(a2, a3, a4, ValueName, 0x20u);
  v6 = 0;
  do
  {
    if ( RegEnumKeyW(hKey, v6, Name, 0x20u) )
      break;
    v7 = StrChrW(Name, 0x2Eu);
    if ( v7 )
    {
      if ( CompareStringW(0x7Fu, 1u, v7, -1, L".map", -1) == 2 )
      {
        phkResult = 0;
        if ( !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &phkResult) )
        {
          if ( !RegQueryValueExW(phkResult, ValueName, 0, 0, 0, 0) )
            v5 = 1;
          RegCloseKey(phkResult);
        }
      }
    }
    ++v6;
  }
  while ( !v5 );
  return v5;
}

```

## disassembly

```asm
0x180012d50  push    rbx
0x180012d52  push    rsi
0x180012d53  push    rdi
0x180012d54  push    r14
0x180012d56  sub     rsp, 0D8h
0x180012d5d  mov     rax, cs:__security_cookie
0x180012d64  xor     rax, rsp
0x180012d67  mov     [rsp+0F8h+var_38], rax
0x180012d6f  mov     r11, r9
0x180012d72  mov     dword ptr [rsp+0F8h+lpString2], 20h ; ' '; unsigned int
0x180012d7a  mov     r10, r8
0x180012d7d  lea     r9, [rsp+0F8h+ValueName]; unsigned __int16 *
0x180012d85  mov     rax, rdx
0x180012d88  mov     rsi, rcx
0x180012d8b  mov     r8, r11; unsigned __int16 *
0x180012d8e  mov     rdx, r10; unsigned __int16 *
0x180012d91  mov     rcx, rax; unsigned __int16 *
0x180012d94  xor     ebx, ebx
0x180012d96  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x180012d9b  xor     edi, edi
0x180012d9d  lea     r14d, [rbx+1]
0x180012da1  mov     r9d, 20h ; ' '; cchName
0x180012da7  lea     r8, [rsp+0F8h+Name]; lpName
0x180012dac  mov     edx, edi; dwIndex
0x180012dae  mov     rcx, rsi; hKey
0x180012db1  call    cs:__imp_RegEnumKeyW
0x180012db7  test    eax, eax
0x180012db9  jnz     loc_180012E79
0x180012dbf  lea     edx, [rax+2Eh]; wMatch
0x180012dc2  lea     rcx, [rsp+0F8h+Name]; pszStart
0x180012dc7  call    cs:__imp_StrChrW
0x180012dcd  test    rax, rax
0x180012dd0  jz      loc_180012E6E
0x180012dd6  lea     rcx, aMap; ".map"
0x180012ddd  mov     [rsp+0F8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180012de5  mov     [rsp+0F8h+lpString2], rcx; lpString2
0x180012dea  or      r9d, 0FFFFFFFFh; cchCount1
0x180012dee  mov     ecx, 7Fh; Locale
0x180012df3  mov     r8, rax; lpString1
0x180012df6  mov     edx, r14d; dwCmpFlags
0x180012df9  call    cs:__imp_CompareStringW
0x180012dff  cmp     eax, 2
0x180012e02  jnz     short loc_180012E6E
0x180012e04  lea     rax, [rsp+0F8h+phkResult]
0x180012e09  mov     [rsp+0F8h+phkResult], 0
0x180012e12  mov     r9d, 2001Fh; samDesired
0x180012e18  mov     [rsp+0F8h+lpString2], rax; phkResult
0x180012e1d  xor     r8d, r8d; ulOptions
0x180012e20  lea     rdx, [rsp+0F8h+Name]; lpSubKey
0x180012e25  mov     rcx, rsi; hKey
0x180012e28  call    cs:__imp_RegOpenKeyExW
0x180012e2e  test    eax, eax
0x180012e30  jnz     short loc_180012E6E
0x180012e32  mov     rcx, [rsp+0F8h+phkResult]; hKey
0x180012e37  lea     rdx, [rsp+0F8h+ValueName]; lpValueName
0x180012e3f  mov     qword ptr [rsp+0F8h+cchCount2], 0; lpcbData
0x180012e48  xor     r9d, r9d; lpType
0x180012e4b  xor     r8d, r8d; lpReserved
0x180012e4e  mov     [rsp+0F8h+lpString2], 0; lpData
0x180012e57  call    cs:__imp_RegQueryValueExW
0x180012e5d  mov     rcx, [rsp+0F8h+phkResult]; hKey
0x180012e62  test    eax, eax
0x180012e64  cmovz   ebx, r14d
0x180012e68  call    cs:__imp_RegCloseKey
0x180012e6e  add     edi, r14d
0x180012e71  test    ebx, ebx
0x180012e73  jz      loc_180012DA1
0x180012e79  mov     eax, ebx
0x180012e7b  mov     rcx, [rsp+0F8h+var_38]
0x180012e83  xor     rcx, rsp; StackCookie
0x180012e86  call    __security_check_cookie
0x180012e8b  add     rsp, 0D8h
0x180012e92  pop     r14
0x180012e94  pop     rdi
0x180012e95  pop     rsi
0x180012e96  pop     rbx
0x180012e97  retn
```
