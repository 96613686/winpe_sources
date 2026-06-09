# GetInstallLanguage

- ea: `0x180039390`
- end: `0x18003949a`
- name: `GetInstallLanguage`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800399f4`

## callees

- `0x180002300`
- `0x180003030`
- `0x180039390`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800393f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800393f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039420`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039420`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003942d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003942d`

## string_xrefs

- `0x1800393e2`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18005A0FC;
  hKey = 0;
  if ( !word_18005A0FC )
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
          if ( !wcsnicmp(&Data, (&off_180041BB0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_180041BB0 + 8 * (int)v1 + 4);
            word_18005A0FC = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18005A0FC;
  }
  return v0;
}

```

## disassembly

```asm
0x180039390  mov     r11, rsp
0x180039393  mov     [r11+8], rbx
0x180039397  mov     [r11+10h], rsi
0x18003939b  push    rdi
0x18003939c  sub     rsp, 50h
0x1800393a0  mov     rax, cs:__security_cookie
0x1800393a7  xor     rax, rsp
0x1800393aa  mov     [rsp+58h+var_10], rax
0x1800393af  movzx   ecx, cs:word_18005A0FC
0x1800393b6  xor     eax, eax
0x1800393b8  mov     qword ptr [r11-20h], 0
0x1800393c0  cmp     ax, cx
0x1800393c3  jnz     loc_18003947A
0x1800393c9  lea     rax, [r11-20h]
0x1800393cd  mov     [rsp+58h+cbData], 6
0x1800393d5  mov     r9d, 1; samDesired
0x1800393db  mov     [r11-38h], rax
0x1800393df  xor     r8d, r8d; ulOptions
0x1800393e2  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800393e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800393f0  call    cs:__imp_RegOpenKeyExW
0x1800393f6  test    eax, eax
0x1800393f8  jnz     short loc_180039473
0x1800393fa  mov     rcx, [rsp+58h+hKey]; hKey
0x1800393ff  lea     rax, [rsp+58h+cbData]
0x180039404  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180039409  lea     rdx, aLocale; "Locale"
0x180039410  lea     rax, [rsp+58h+Data]
0x180039415  xor     r9d, r9d; lpType
0x180039418  xor     r8d, r8d; lpReserved
0x18003941b  mov     [rsp+58h+lpData], rax; lpData
0x180039420  call    cs:__imp_RegQueryValueExW
0x180039426  mov     rcx, [rsp+58h+hKey]; hKey
0x18003942b  mov     ebx, eax
0x18003942d  call    cs:__imp_RegCloseKey
0x180039433  test    ebx, ebx
0x180039435  jnz     short loc_180039473
0x180039437  lea     rsi, off_180041BB0; "EN"
0x18003943e  cmp     ebx, 1Ch
0x180039441  jnb     short loc_180039473
0x180039443  movsxd  rdi, ebx
0x180039446  lea     rcx, [rsp+58h+Data]; String1
0x18003944b  add     rdi, rdi
0x18003944e  mov     r8d, 3; MaxCount
0x180039454  mov     rdx, [rsi+rdi*8]; String2
0x180039458  call    _wcsnicmp
0x18003945d  test    eax, eax
0x18003945f  jz      short loc_180039465
0x180039461  inc     ebx
0x180039463  jmp     short loc_18003943E
0x180039465  movzx   ecx, word ptr [rsi+rdi*8+8]
0x18003946a  mov     cs:word_18005A0FC, cx
0x180039471  jmp     short loc_18003947A
0x180039473  movzx   ecx, cs:word_18005A0FC
0x18003947a  movzx   eax, cx
0x18003947d  mov     rcx, [rsp+58h+var_10]
0x180039482  xor     rcx, rsp; StackCookie
0x180039485  call    __security_check_cookie
0x18003948a  mov     rbx, [rsp+58h+arg_0]
0x18003948f  mov     rsi, [rsp+58h+arg_8]
0x180039494  add     rsp, 50h
0x180039498  pop     rdi
0x180039499  retn
```
