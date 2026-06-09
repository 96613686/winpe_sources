# GetInstallLanguage

- ea: `0x180054638`
- end: `0x18005473a`
- name: `GetInstallLanguage`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180054cc8`

## callees

- `0x1800078b0`
- `0x180008550`
- `0x180054638`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800546c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800546c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800546d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800546d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054695`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054695`

## string_xrefs

- `0x180054687`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_1800A417C )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v0 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v0 )
      {
        while ( wcsnicmp(&Data, (&off_180061290)[2 * v0], 3u) )
        {
          if ( (unsigned int)++v0 >= 0x1C )
            return (unsigned __int16)word_1800A417C;
        }
        word_1800A417C = *((_WORD *)&off_180061290 + 8 * v0 + 4);
      }
    }
  }
  return (unsigned __int16)word_1800A417C;
}

```

## disassembly

```asm
0x180054638  mov     r11, rsp
0x18005463b  mov     [r11+8], rbx
0x18005463f  mov     [r11+10h], rsi
0x180054643  push    rdi
0x180054644  sub     rsp, 50h
0x180054648  mov     rax, cs:__security_cookie
0x18005464f  xor     rax, rsp
0x180054652  mov     [rsp+58h+var_10], rax
0x180054657  xor     eax, eax
0x180054659  mov     qword ptr [r11-20h], 0
0x180054661  cmp     ax, cs:word_1800A417C
0x180054668  jnz     loc_180054716
0x18005466e  lea     rax, [r11-20h]
0x180054672  mov     [rsp+58h+cbData], 6
0x18005467a  mov     r9d, 1; samDesired
0x180054680  mov     [r11-38h], rax
0x180054684  xor     r8d, r8d; ulOptions
0x180054687  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Active Setup\\Inst"...
0x18005468e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180054695  call    cs:__imp_RegOpenKeyExW
0x18005469b  test    eax, eax
0x18005469d  jnz     short loc_180054716
0x18005469f  mov     rcx, [rsp+58h+hKey]; hKey
0x1800546a4  lea     rax, [rsp+58h+cbData]
0x1800546a9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800546ae  lea     rdx, aLocale; "Locale"
0x1800546b5  lea     rax, [rsp+58h+Data]
0x1800546ba  xor     r9d, r9d; lpType
0x1800546bd  xor     r8d, r8d; lpReserved
0x1800546c0  mov     [rsp+58h+lpData], rax; lpData
0x1800546c5  call    cs:__imp_RegQueryValueExW
0x1800546cb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800546d0  mov     ebx, eax
0x1800546d2  call    cs:__imp_RegCloseKey
0x1800546d8  test    ebx, ebx
0x1800546da  jnz     short loc_180054716
0x1800546dc  lea     rsi, off_180061290; "EN"
0x1800546e3  movsxd  rdi, ebx
0x1800546e6  lea     rcx, [rsp+58h+Data]; String1
0x1800546eb  add     rdi, rdi
0x1800546ee  mov     r8d, 3; MaxCount
0x1800546f4  mov     rdx, [rsi+rdi*8]; String2
0x1800546f8  call    _wcsnicmp
0x1800546fd  test    eax, eax
0x1800546ff  jz      short loc_18005470A
0x180054701  inc     ebx
0x180054703  cmp     ebx, 1Ch
0x180054706  jb      short loc_1800546E3
0x180054708  jmp     short loc_180054716
0x18005470a  movzx   eax, word ptr [rsi+rdi*8+8]
0x18005470f  mov     cs:word_1800A417C, ax
0x180054716  movzx   eax, cs:word_1800A417C
0x18005471d  mov     rcx, [rsp+58h+var_10]
0x180054722  xor     rcx, rsp; StackCookie
0x180054725  call    __security_check_cookie
0x18005472a  mov     rbx, [rsp+58h+arg_0]
0x18005472f  mov     rsi, [rsp+58h+arg_8]
0x180054734  add     rsp, 50h
0x180054738  pop     rdi
0x180054739  retn
```
