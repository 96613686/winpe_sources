# GetInstallLanguage

- ea: `0x140025948`
- end: `0x140025a4b`
- name: `GetInstallLanguage`
- size: `259`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140026010`

## callees

- `0x140025948`
- `0x140026650`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140025a08`
- `msvcrt!_wcsnicmp` at `0x140025a08`
- `ADVAPI32!RegQueryValueExW` at `0x1400259d5`
- `ADVAPI32!RegQueryValueExW` at `0x1400259d5`
- `ADVAPI32!RegCloseKey` at `0x1400259e2`
- `ADVAPI32!RegCloseKey` at `0x1400259e2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400259a5`
- `ADVAPI32!RegOpenKeyExW` at `0x1400259a5`

## string_xrefs

- `0x140025997`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_14003F858 )
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
        while ( _wcsnicmp(&Data, (&off_1400281C0)[2 * v0], 3u) )
        {
          if ( (unsigned int)++v0 >= 0x1C )
            return (unsigned __int16)word_14003F858;
        }
        word_14003F858 = *((_WORD *)&off_1400281C0 + 8 * v0 + 4);
      }
    }
  }
  return (unsigned __int16)word_14003F858;
}

```

## disassembly

```asm
0x140025948  mov     r11, rsp
0x14002594b  mov     [r11+8], rbx
0x14002594f  mov     [r11+10h], rsi
0x140025953  push    rdi
0x140025954  sub     rsp, 50h
0x140025958  mov     rax, cs:__security_cookie
0x14002595f  xor     rax, rsp
0x140025962  mov     [rsp+58h+var_10], rax
0x140025967  xor     eax, eax
0x140025969  mov     qword ptr [r11-20h], 0
0x140025971  cmp     ax, cs:word_14003F858
0x140025978  jnz     loc_140025A27
0x14002597e  lea     rax, [r11-20h]
0x140025982  mov     [rsp+58h+cbData], 6
0x14002598a  mov     r9d, 1; samDesired
0x140025990  mov     [r11-38h], rax
0x140025994  xor     r8d, r8d; ulOptions
0x140025997  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x14002599e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400259a5  call    cs:__imp_RegOpenKeyExW
0x1400259ab  test    eax, eax
0x1400259ad  jnz     short loc_140025A27
0x1400259af  mov     rcx, [rsp+58h+hKey]; hKey
0x1400259b4  lea     rax, [rsp+58h+cbData]
0x1400259b9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1400259be  lea     rdx, ValueName; "Locale"
0x1400259c5  lea     rax, [rsp+58h+Data]
0x1400259ca  xor     r9d, r9d; lpType
0x1400259cd  xor     r8d, r8d; lpReserved
0x1400259d0  mov     [rsp+58h+lpData], rax; lpData
0x1400259d5  call    cs:__imp_RegQueryValueExW
0x1400259db  mov     rcx, [rsp+58h+hKey]; hKey
0x1400259e0  mov     ebx, eax
0x1400259e2  call    cs:__imp_RegCloseKey
0x1400259e8  test    ebx, ebx
0x1400259ea  jnz     short loc_140025A27
0x1400259ec  lea     rsi, off_1400281C0; "EN"
0x1400259f3  movsxd  rdi, ebx
0x1400259f6  lea     rcx, [rsp+58h+Data]; String1
0x1400259fb  add     rdi, rdi
0x1400259fe  mov     r8d, 3; MaxCount
0x140025a04  mov     rdx, [rsi+rdi*8]; String2
0x140025a08  call    cs:__imp__wcsnicmp
0x140025a0e  test    eax, eax
0x140025a10  jz      short loc_140025A1B
0x140025a12  inc     ebx
0x140025a14  cmp     ebx, 1Ch
0x140025a17  jb      short loc_1400259F3
0x140025a19  jmp     short loc_140025A27
0x140025a1b  movzx   eax, word ptr [rsi+rdi*8+8]
0x140025a20  mov     cs:word_14003F858, ax
0x140025a27  movzx   eax, cs:word_14003F858
0x140025a2e  mov     rcx, [rsp+58h+var_10]
0x140025a33  xor     rcx, rsp; StackCookie
0x140025a36  call    __security_check_cookie
0x140025a3b  mov     rbx, [rsp+58h+arg_0]
0x140025a40  mov     rsi, [rsp+58h+arg_8]
0x140025a45  add     rsp, 50h
0x140025a49  pop     rdi
0x140025a4a  retn
```
