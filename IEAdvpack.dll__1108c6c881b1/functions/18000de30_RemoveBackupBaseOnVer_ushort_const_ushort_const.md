# RemoveBackupBaseOnVer(ushort const *,ushort const *)

- ea: `0x18000de30`
- end: `0x18000e05a`
- name: `?RemoveBackupBaseOnVer@@YAHPEBG0@Z`
- size: `554`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpAppName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x180007454`
- `0x18000c99c`
- `0x18000de30`
- `0x180017d98`
- `0x180017f14`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000df34`
- `ADVAPI32!RegQueryValueExW` at `0x18000df34`
- `ADVAPI32!RegCloseKey` at `0x18000dfb8`
- `ADVAPI32!RegCloseKey` at `0x18000e010`
- `ADVAPI32!RegCloseKey` at `0x18000e022`
- `ADVAPI32!RegCloseKey` at `0x18000e02d`
- `ADVAPI32!RegCloseKey` at `0x18000dfb8`
- `ADVAPI32!RegCloseKey` at `0x18000e010`
- `ADVAPI32!RegCloseKey` at `0x18000e022`
- `ADVAPI32!RegCloseKey` at `0x18000e02d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dec7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000def1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dff0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dec7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000def1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dff0`

## string_xrefs

- `0x18000de68`: `ComponentName`
- `0x18000df04`: `ComponentVersion`
- `0x18000df68`: `ComponentVersion`

## pseudocode

```c
__int64 __fastcall RemoveBackupBaseOnVer(const unsigned __int16 *a1, LPCWSTR lpAppName)
{
  unsigned __int16 v4; // bx
  unsigned __int16 v5; // ax
  HKEY v6; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v11; // [rsp+48h] [rbp-B8h]
  wchar_t Data[259]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v13; // [rsp+256h] [rbp+156h]
  WCHAR SubKey[264]; // [rsp+260h] [rbp+160h] BYREF

  phkResult = 0;
  hKey = 0;
  cbData = 0;
  if ( (int)GetTranslatedString(a1, lpAppName, L"ComponentName", SubKey, 0x104u, 0) >= 0
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x2001Fu, &hKey) )
  {
    if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &phkResult) )
    {
      v13 = 0;
      cbData = 518;
      if ( RegQueryValueExW(phkResult, L"ComponentVersion", 0, 0, (LPBYTE)Data, &cbData) )
      {
        v4 = 0;
      }
      else
      {
        ConvertVersionString(Data);
        v4 = v11;
      }
      if ( (int)GetTranslatedString(a1, lpAppName, L"ComponentVersion", Data, 0x104u, 0) < 0 )
      {
        v5 = 0;
      }
      else
      {
        ConvertVersionString(Data);
        v5 = v11;
      }
      v6 = phkResult;
      if ( v5 > v4 )
      {
        DeleteOldBackupData(phkResult);
        RegCloseKey(phkResult);
        RegDeleteKeyRecursivelyW(hKey, SubKey);
        if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x20006u, &phkResult) )
        {
          RegDeleteKeyRecursivelyW(phkResult, SubKey);
          RegCloseKey(phkResult);
        }
        v6 = 0;
        phkResult = 0;
      }
      if ( v6 )
        RegCloseKey(v6);
    }
    RegCloseKey(hKey);
  }
  return 1;
}

```

## disassembly

```asm
0x18000de30  mov     [rsp-8+arg_10], rbx
0x18000de35  push    rbp
0x18000de36  push    rsi
0x18000de37  push    rdi
0x18000de38  lea     rbp, [rsp-380h]
0x18000de40  sub     rsp, 480h
0x18000de47  mov     rax, cs:__security_cookie
0x18000de4e  xor     rax, rsp
0x18000de51  mov     [rbp+390h+var_20], rax
0x18000de58  mov     [rsp+490h+lpcbData], 0; unsigned int *
0x18000de61  lea     r9, [rbp+390h+SubKey]; unsigned __int16 *
0x18000de68  lea     r8, KeyName; "ComponentName"
0x18000de6f  mov     dword ptr [rsp+490h+phkResult], 104h; unsigned int
0x18000de77  mov     rsi, rdx
0x18000de7a  mov     [rsp+490h+var_460], 0
0x18000de83  mov     rdi, rcx
0x18000de86  mov     [rsp+490h+hKey], 0
0x18000de8f  mov     [rsp+490h+cbData], 0
0x18000de97  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000de9c  test    eax, eax
0x18000de9e  js      loc_18000E033
0x18000dea4  lea     rax, [rsp+490h+hKey]
0x18000dea9  mov     ebx, 2001Fh
0x18000deae  mov     r9d, ebx; samDesired
0x18000deb1  mov     [rsp+490h+phkResult], rax; phkResult
0x18000deb6  xor     r8d, r8d; ulOptions
0x18000deb9  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000dec0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dec7  call    cs:__imp_RegOpenKeyExW
0x18000decd  test    eax, eax
0x18000decf  jnz     loc_18000E033
0x18000ded5  mov     rcx, [rsp+490h+hKey]; hKey
0x18000deda  lea     rax, [rsp+490h+var_460]
0x18000dedf  mov     r9d, ebx; samDesired
0x18000dee2  mov     [rsp+490h+phkResult], rax; phkResult
0x18000dee7  xor     r8d, r8d; ulOptions
0x18000deea  lea     rdx, [rbp+390h+SubKey]; lpSubKey
0x18000def1  call    cs:__imp_RegOpenKeyExW
0x18000def7  test    eax, eax
0x18000def9  jnz     loc_18000E028
0x18000deff  mov     rcx, [rsp+490h+var_460]; hKey
0x18000df04  lea     rdx, aComponentversi; "ComponentVersion"
0x18000df0b  mov     [rbp+390h+var_23A], ax
0x18000df12  xor     r9d, r9d; lpType
0x18000df15  lea     rax, [rsp+490h+cbData]
0x18000df1a  mov     [rsp+490h+cbData], 206h
0x18000df22  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18000df27  xor     r8d, r8d; lpReserved
0x18000df2a  lea     rax, [rsp+490h+Data]
0x18000df2f  mov     [rsp+490h+phkResult], rax; lpData
0x18000df34  call    cs:__imp_RegQueryValueExW
0x18000df3a  test    eax, eax
0x18000df3c  jnz     short loc_18000DF58
0x18000df3e  lea     r8d, [rax+2Eh]
0x18000df42  lea     rdx, [rsp+490h+var_448]
0x18000df47  lea     rcx, [rsp+490h+Data]; pszSrc
0x18000df4c  call    ConvertVersionString
0x18000df51  movzx   ebx, [rsp+490h+var_448]
0x18000df56  jmp     short loc_18000DF5A
0x18000df58  xor     ebx, ebx
0x18000df5a  mov     [rsp+490h+lpcbData], 0; unsigned int *
0x18000df63  lea     r9, [rsp+490h+Data]; unsigned __int16 *
0x18000df68  lea     r8, aComponentversi; "ComponentVersion"
0x18000df6f  mov     dword ptr [rsp+490h+phkResult], 104h; unsigned int
0x18000df77  mov     rdx, rsi; lpAppName
0x18000df7a  mov     rcx, rdi; unsigned __int16 *
0x18000df7d  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000df82  test    eax, eax
0x18000df84  js      short loc_18000DFA2
0x18000df86  mov     r8d, 2Eh ; '.'
0x18000df8c  lea     rdx, [rsp+490h+var_448]
0x18000df91  lea     rcx, [rsp+490h+Data]; pszSrc
0x18000df96  call    ConvertVersionString
0x18000df9b  movzx   eax, [rsp+490h+var_448]
0x18000dfa0  jmp     short loc_18000DFA4
0x18000dfa2  xor     eax, eax
0x18000dfa4  mov     rcx, [rsp+490h+var_460]; hKey
0x18000dfa9  cmp     ax, bx
0x18000dfac  jbe     short loc_18000E01D
0x18000dfae  call    ?DeleteOldBackupData@@YAXPEAUHKEY__@@@Z; DeleteOldBackupData(HKEY__ *)
0x18000dfb3  mov     rcx, [rsp+490h+var_460]; hKey
0x18000dfb8  call    cs:__imp_RegCloseKey
0x18000dfbe  mov     rcx, [rsp+490h+hKey]
0x18000dfc3  lea     rdx, [rbp+390h+SubKey]
0x18000dfca  call    RegDeleteKeyRecursivelyW
0x18000dfcf  lea     rax, [rsp+490h+var_460]
0x18000dfd4  mov     r9d, 20006h; samDesired
0x18000dfda  xor     r8d, r8d; ulOptions
0x18000dfdd  mov     [rsp+490h+phkResult], rax; phkResult
0x18000dfe2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000dfe9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000dff0  call    cs:__imp_RegOpenKeyExW
0x18000dff6  test    eax, eax
0x18000dff8  jnz     short loc_18000E016
0x18000dffa  mov     rcx, [rsp+490h+var_460]
0x18000dfff  lea     rdx, [rbp+390h+SubKey]
0x18000e006  call    RegDeleteKeyRecursivelyW
0x18000e00b  mov     rcx, [rsp+490h+var_460]; hKey
0x18000e010  call    cs:__imp_RegCloseKey
0x18000e016  xor     ecx, ecx; hKey
0x18000e018  mov     [rsp+490h+var_460], rcx
0x18000e01d  test    rcx, rcx
0x18000e020  jz      short loc_18000E028
0x18000e022  call    cs:__imp_RegCloseKey
0x18000e028  mov     rcx, [rsp+490h+hKey]; hKey
0x18000e02d  call    cs:__imp_RegCloseKey
0x18000e033  mov     eax, 1
0x18000e038  mov     rcx, [rbp+390h+var_20]
0x18000e03f  xor     rcx, rsp; StackCookie
0x18000e042  call    __security_check_cookie
0x18000e047  mov     rbx, [rsp+490h+arg_10]
0x18000e04f  add     rsp, 480h
0x18000e056  pop     rdi
0x18000e057  pop     rsi
0x18000e058  pop     rbp
0x18000e059  retn
```
