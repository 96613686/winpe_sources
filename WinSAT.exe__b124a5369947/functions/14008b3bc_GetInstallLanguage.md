# GetInstallLanguage

- ea: `0x14008b3bc`
- end: `0x14008b4c7`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14008ba20`

## callees

- `0x14008b3bc`
- `0x140113220`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14008b44c`
- `ADVAPI32!RegQueryValueExW` at `0x14008b44c`
- `ADVAPI32!RegOpenKeyExW` at `0x14008b41c`
- `ADVAPI32!RegOpenKeyExW` at `0x14008b41c`
- `ADVAPI32!RegCloseKey` at `0x14008b459`
- `ADVAPI32!RegCloseKey` at `0x14008b459`
- `msvcrt!_wcsnicmp` at `0x14008b484`
- `msvcrt!_wcsnicmp` at `0x14008b484`

## string_xrefs

- `0x14008b40e`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1401CBADC;
  hKey = 0;
  if ( !word_1401CBADC )
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
          if ( !_wcsnicmp(&Data, (&off_14011D9E0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_14011D9E0 + 8 * (int)v1 + 4);
            word_1401CBADC = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1401CBADC;
  }
  return v0;
}

```

## disassembly

```asm
0x14008b3bc  mov     r11, rsp
0x14008b3bf  mov     [r11+8], rbx
0x14008b3c3  mov     [r11+10h], rsi
0x14008b3c7  push    rdi
0x14008b3c8  sub     rsp, 50h
0x14008b3cc  mov     rax, cs:__security_cookie
0x14008b3d3  xor     rax, rsp
0x14008b3d6  mov     [rsp+58h+var_10], rax
0x14008b3db  movzx   ecx, cs:word_1401CBADC
0x14008b3e2  xor     eax, eax
0x14008b3e4  mov     qword ptr [r11-20h], 0
0x14008b3ec  cmp     ax, cx
0x14008b3ef  jnz     loc_14008B4A7
0x14008b3f5  lea     rax, [r11-20h]
0x14008b3f9  mov     [rsp+58h+cbData], 6
0x14008b401  mov     r9d, 1; samDesired
0x14008b407  mov     [r11-38h], rax
0x14008b40b  xor     r8d, r8d; ulOptions
0x14008b40e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Active Setup\\Inst"...
0x14008b415  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14008b41c  call    cs:__imp_RegOpenKeyExW
0x14008b422  test    eax, eax
0x14008b424  jnz     short loc_14008B4A0
0x14008b426  mov     rcx, [rsp+58h+hKey]; hKey
0x14008b42b  lea     rax, [rsp+58h+cbData]
0x14008b430  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14008b435  lea     rdx, aLocale; "Locale"
0x14008b43c  lea     rax, [rsp+58h+Data]
0x14008b441  xor     r9d, r9d; lpType
0x14008b444  xor     r8d, r8d; lpReserved
0x14008b447  mov     [rsp+58h+lpData], rax; lpData
0x14008b44c  call    cs:__imp_RegQueryValueExW
0x14008b452  mov     rcx, [rsp+58h+hKey]; hKey
0x14008b457  mov     ebx, eax
0x14008b459  call    cs:__imp_RegCloseKey
0x14008b45f  test    ebx, ebx
0x14008b461  jnz     short loc_14008B4A0
0x14008b463  lea     rsi, off_14011D9E0; "EN"
0x14008b46a  cmp     ebx, 1Ch
0x14008b46d  jnb     short loc_14008B4A0
0x14008b46f  movsxd  rdi, ebx
0x14008b472  lea     rcx, [rsp+58h+Data]; String1
0x14008b477  add     rdi, rdi
0x14008b47a  mov     r8d, 3; MaxCount
0x14008b480  mov     rdx, [rsi+rdi*8]; String2
0x14008b484  call    cs:__imp__wcsnicmp
0x14008b48a  test    eax, eax
0x14008b48c  jz      short loc_14008B492
0x14008b48e  inc     ebx
0x14008b490  jmp     short loc_14008B46A
0x14008b492  movzx   ecx, word ptr [rsi+rdi*8+8]
0x14008b497  mov     cs:word_1401CBADC, cx
0x14008b49e  jmp     short loc_14008B4A7
0x14008b4a0  movzx   ecx, cs:word_1401CBADC
0x14008b4a7  movzx   eax, cx
0x14008b4aa  mov     rcx, [rsp+58h+var_10]
0x14008b4af  xor     rcx, rsp; StackCookie
0x14008b4b2  call    __security_check_cookie
0x14008b4b7  mov     rbx, [rsp+58h+arg_0]
0x14008b4bc  mov     rsi, [rsp+58h+arg_8]
0x14008b4c1  add     rsp, 50h
0x14008b4c5  pop     rdi
0x14008b4c6  retn
```
