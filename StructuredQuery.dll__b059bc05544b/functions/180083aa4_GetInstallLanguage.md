# GetInstallLanguage

- ea: `0x180083aa4`
- end: `0x180083bae`
- name: `GetInstallLanguage`
- size: `266`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008416c`

## callees

- `0x18005daf0`
- `0x18005e6e0`
- `0x180083aa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180083b34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180083b34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083b04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083b04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083b41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083b41`

## string_xrefs

- `0x180083af6`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1800B1424;
  hKey = 0;
  if ( !word_1800B1424 )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v1 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v1 )
      {
        while ( v1 < 0x1C )
        {
          if ( !wcsnicmp(&Data, (&off_180097BB0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_180097BB0 + 8 * (int)v1 + 4);
            word_1800B1424 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1800B1424;
  }
  return v0;
}

```

## disassembly

```asm
0x180083aa4  mov     r11, rsp
0x180083aa7  mov     [r11+8], rbx
0x180083aab  mov     [r11+10h], rsi
0x180083aaf  push    rdi
0x180083ab0  sub     rsp, 50h
0x180083ab4  mov     rax, cs:__security_cookie
0x180083abb  xor     rax, rsp
0x180083abe  mov     [rsp+58h+var_10], rax
0x180083ac3  movzx   ecx, cs:word_1800B1424
0x180083aca  xor     eax, eax
0x180083acc  mov     qword ptr [r11-20h], 0
0x180083ad4  cmp     ax, cx
0x180083ad7  jnz     loc_180083B8E
0x180083add  lea     rax, [r11-20h]
0x180083ae1  mov     [rsp+58h+cbData], 6
0x180083ae9  mov     r9d, 1; samDesired
0x180083aef  mov     [r11-38h], rax
0x180083af3  xor     r8d, r8d; ulOptions
0x180083af6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Active Setup\\Inst"...
0x180083afd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083b04  call    cs:__imp_RegOpenKeyExW
0x180083b0a  test    eax, eax
0x180083b0c  jnz     short loc_180083B87
0x180083b0e  mov     rcx, [rsp+58h+hKey]; hKey
0x180083b13  lea     rax, [rsp+58h+cbData]
0x180083b18  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180083b1d  lea     rdx, aLocale_0; "Locale"
0x180083b24  lea     rax, [rsp+58h+Data]
0x180083b29  xor     r9d, r9d; lpType
0x180083b2c  xor     r8d, r8d; lpReserved
0x180083b2f  mov     [rsp+58h+lpData], rax; lpData
0x180083b34  call    cs:__imp_RegQueryValueExW
0x180083b3a  mov     rcx, [rsp+58h+hKey]; hKey
0x180083b3f  mov     ebx, eax
0x180083b41  call    cs:__imp_RegCloseKey
0x180083b47  test    ebx, ebx
0x180083b49  jnz     short loc_180083B87
0x180083b4b  lea     rsi, off_180097BB0; "EN"
0x180083b52  cmp     ebx, 1Ch
0x180083b55  jnb     short loc_180083B87
0x180083b57  movsxd  rdi, ebx
0x180083b5a  lea     rcx, [rsp+58h+Data]; String1
0x180083b5f  add     rdi, rdi
0x180083b62  mov     r8d, 3; MaxCount
0x180083b68  mov     rdx, [rsi+rdi*8]; String2
0x180083b6c  call    _wcsnicmp
0x180083b71  test    eax, eax
0x180083b73  jz      short loc_180083B79
0x180083b75  inc     ebx
0x180083b77  jmp     short loc_180083B52
0x180083b79  movzx   ecx, word ptr [rsi+rdi*8+8]
0x180083b7e  mov     cs:word_1800B1424, cx
0x180083b85  jmp     short loc_180083B8E
0x180083b87  movzx   ecx, cs:word_1800B1424
0x180083b8e  movzx   eax, cx
0x180083b91  mov     rcx, [rsp+58h+var_10]
0x180083b96  xor     rcx, rsp; StackCookie
0x180083b99  call    __security_check_cookie
0x180083b9e  mov     rbx, [rsp+58h+arg_0]
0x180083ba3  mov     rsi, [rsp+58h+arg_8]
0x180083ba8  add     rsp, 50h
0x180083bac  pop     rdi
0x180083bad  retn
```
