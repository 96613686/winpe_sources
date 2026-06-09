# GetInstallLanguage

- ea: `0x14002b17c`
- end: `0x14002b286`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002b7e0`

## callees

- `0x1400030a0`
- `0x140003c14`
- `0x14002b17c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002b20c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002b20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b219`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002b219`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b1dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002b1dc`

## string_xrefs

- `0x14002b1ce`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_14006B864;
  hKey = 0;
  if ( !word_14006B864 )
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
          if ( !wcsnicmp(&Data, (&off_140051730)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_140051730 + 8 * (int)v1 + 4);
            word_14006B864 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_14006B864;
  }
  return v0;
}

```

## disassembly

```asm
0x14002b17c  mov     r11, rsp
0x14002b17f  mov     [r11+8], rbx
0x14002b183  mov     [r11+10h], rsi
0x14002b187  push    rdi
0x14002b188  sub     rsp, 50h
0x14002b18c  mov     rax, cs:__security_cookie
0x14002b193  xor     rax, rsp
0x14002b196  mov     [rsp+58h+var_10], rax
0x14002b19b  movzx   ecx, cs:word_14006B864
0x14002b1a2  xor     eax, eax
0x14002b1a4  mov     qword ptr [r11-20h], 0
0x14002b1ac  cmp     ax, cx
0x14002b1af  jnz     loc_14002B266
0x14002b1b5  lea     rax, [r11-20h]
0x14002b1b9  mov     [rsp+58h+cbData], 6
0x14002b1c1  mov     r9d, 1; samDesired
0x14002b1c7  mov     [r11-38h], rax
0x14002b1cb  xor     r8d, r8d; ulOptions
0x14002b1ce  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Active Setup\\Inst"...
0x14002b1d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002b1dc  call    cs:__imp_RegOpenKeyExW
0x14002b1e2  test    eax, eax
0x14002b1e4  jnz     short loc_14002B25F
0x14002b1e6  mov     rcx, [rsp+58h+hKey]; hKey
0x14002b1eb  lea     rax, [rsp+58h+cbData]
0x14002b1f0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14002b1f5  lea     rdx, aLocale; "Locale"
0x14002b1fc  lea     rax, [rsp+58h+Data]
0x14002b201  xor     r9d, r9d; lpType
0x14002b204  xor     r8d, r8d; lpReserved
0x14002b207  mov     [rsp+58h+lpData], rax; lpData
0x14002b20c  call    cs:__imp_RegQueryValueExW
0x14002b212  mov     rcx, [rsp+58h+hKey]; hKey
0x14002b217  mov     ebx, eax
0x14002b219  call    cs:__imp_RegCloseKey
0x14002b21f  test    ebx, ebx
0x14002b221  jnz     short loc_14002B25F
0x14002b223  lea     rsi, off_140051730; "EN"
0x14002b22a  cmp     ebx, 1Ch
0x14002b22d  jnb     short loc_14002B25F
0x14002b22f  movsxd  rdi, ebx
0x14002b232  lea     rcx, [rsp+58h+Data]; String1
0x14002b237  add     rdi, rdi
0x14002b23a  mov     r8d, 3; MaxCount
0x14002b240  mov     rdx, [rsi+rdi*8]; String2
0x14002b244  call    _wcsnicmp
0x14002b249  test    eax, eax
0x14002b24b  jz      short loc_14002B251
0x14002b24d  inc     ebx
0x14002b24f  jmp     short loc_14002B22A
0x14002b251  movzx   ecx, word ptr [rsi+rdi*8+8]
0x14002b256  mov     cs:word_14006B864, cx
0x14002b25d  jmp     short loc_14002B266
0x14002b25f  movzx   ecx, cs:word_14006B864
0x14002b266  movzx   eax, cx
0x14002b269  mov     rcx, [rsp+58h+var_10]
0x14002b26e  xor     rcx, rsp; StackCookie
0x14002b271  call    __security_check_cookie
0x14002b276  mov     rbx, [rsp+58h+arg_0]
0x14002b27b  mov     rsi, [rsp+58h+arg_8]
0x14002b280  add     rsp, 50h
0x14002b284  pop     rdi
0x14002b285  retn
```
