# GetInstallLanguage

- ea: `0x140068d6c`
- end: `0x140068e76`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400693d0`

## callees

- `0x140005240`
- `0x1400061a4`
- `0x140068d6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140068e09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140068e09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140068dcc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140068dcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140068dfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140068dfc`

## string_xrefs

- `0x140068dbe`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1400984C4;
  hKey = 0;
  if ( !word_1400984C4 )
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
          if ( !wcsnicmp(&Data, (&off_1400733E0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_1400733E0 + 8 * (int)v1 + 4);
            word_1400984C4 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1400984C4;
  }
  return v0;
}

```

## disassembly

```asm
0x140068d6c  mov     r11, rsp
0x140068d6f  mov     [r11+8], rbx
0x140068d73  mov     [r11+10h], rsi
0x140068d77  push    rdi
0x140068d78  sub     rsp, 50h
0x140068d7c  mov     rax, cs:__security_cookie
0x140068d83  xor     rax, rsp
0x140068d86  mov     [rsp+58h+var_10], rax
0x140068d8b  movzx   ecx, cs:word_1400984C4
0x140068d92  xor     eax, eax
0x140068d94  mov     qword ptr [r11-20h], 0
0x140068d9c  cmp     ax, cx
0x140068d9f  jnz     loc_140068E56
0x140068da5  lea     rax, [r11-20h]
0x140068da9  mov     [rsp+58h+cbData], 6
0x140068db1  mov     r9d, 1; samDesired
0x140068db7  mov     [r11-38h], rax
0x140068dbb  xor     r8d, r8d; ulOptions
0x140068dbe  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Active Setup\\Inst"...
0x140068dc5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140068dcc  call    cs:__imp_RegOpenKeyExW
0x140068dd2  test    eax, eax
0x140068dd4  jnz     short loc_140068E4F
0x140068dd6  mov     rcx, [rsp+58h+hKey]; hKey
0x140068ddb  lea     rax, [rsp+58h+cbData]
0x140068de0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140068de5  lea     rdx, aLocale; "Locale"
0x140068dec  lea     rax, [rsp+58h+Data]
0x140068df1  xor     r9d, r9d; lpType
0x140068df4  xor     r8d, r8d; lpReserved
0x140068df7  mov     [rsp+58h+lpData], rax; lpData
0x140068dfc  call    cs:__imp_RegQueryValueExW
0x140068e02  mov     rcx, [rsp+58h+hKey]; hKey
0x140068e07  mov     ebx, eax
0x140068e09  call    cs:__imp_RegCloseKey
0x140068e0f  test    ebx, ebx
0x140068e11  jnz     short loc_140068E4F
0x140068e13  lea     rsi, off_1400733E0; "EN"
0x140068e1a  cmp     ebx, 1Ch
0x140068e1d  jnb     short loc_140068E4F
0x140068e1f  movsxd  rdi, ebx
0x140068e22  lea     rcx, [rsp+58h+Data]; String1
0x140068e27  add     rdi, rdi
0x140068e2a  mov     r8d, 3; MaxCount
0x140068e30  mov     rdx, [rsi+rdi*8]; String2
0x140068e34  call    _wcsnicmp
0x140068e39  test    eax, eax
0x140068e3b  jz      short loc_140068E41
0x140068e3d  inc     ebx
0x140068e3f  jmp     short loc_140068E1A
0x140068e41  movzx   ecx, word ptr [rsi+rdi*8+8]
0x140068e46  mov     cs:word_1400984C4, cx
0x140068e4d  jmp     short loc_140068E56
0x140068e4f  movzx   ecx, cs:word_1400984C4
0x140068e56  movzx   eax, cx
0x140068e59  mov     rcx, [rsp+58h+var_10]
0x140068e5e  xor     rcx, rsp; StackCookie
0x140068e61  call    __security_check_cookie
0x140068e66  mov     rbx, [rsp+58h+arg_0]
0x140068e6b  mov     rsi, [rsp+58h+arg_8]
0x140068e70  add     rsp, 50h
0x140068e74  pop     rdi
0x140068e75  retn
```
