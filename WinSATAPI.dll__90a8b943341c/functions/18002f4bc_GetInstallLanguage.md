# GetInstallLanguage

- ea: `0x18002f4bc`
- end: `0x18002f5f9`
- name: `GetInstallLanguage`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010ac8`

## callees

- `0x18002f4bc`
- `0x18002fb50`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002f59f`
- `msvcrt!_wcsnicmp` at `0x18002f59f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f56c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f56c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f559`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f559`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f51f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f51f`

## string_xrefs

- `0x18002f511`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  __int64 result; // rax
  LSTATUS v1; // ebx
  int v2; // edi
  const wchar_t **v3; // rsi
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  result = (unsigned __int16)word_180050644;
  hKey = 0;
  if ( !word_180050644 )
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
        v2 = 0;
        v3 = (const wchar_t **)&off_1800360E0;
        while ( (unsigned __int64)v2 < 0x1C )
        {
          if ( !_wcsnicmp(&Data, *v3, 3u) )
          {
            result = *((unsigned __int16 *)&off_1800360E0 + 8 * v2 + 4);
            word_180050644 = *((_WORD *)&off_1800360E0 + 8 * v2 + 4);
            return result;
          }
          ++v2;
          v3 += 2;
        }
      }
    }
    return (unsigned __int16)word_180050644;
  }
  return result;
}

```

## disassembly

```asm
0x18002f4bc  mov     r11, rsp
0x18002f4bf  mov     [r11+8], rbx
0x18002f4c3  mov     [r11+10h], rbp
0x18002f4c7  mov     [r11+18h], rsi
0x18002f4cb  mov     [r11+20h], rdi
0x18002f4cf  push    r14
0x18002f4d1  sub     rsp, 50h
0x18002f4d5  mov     rax, cs:__security_cookie
0x18002f4dc  xor     rax, rsp
0x18002f4df  mov     [rsp+58h+var_10], rax
0x18002f4e4  movzx   eax, cs:word_180050644
0x18002f4eb  xor     ebp, ebp
0x18002f4ed  mov     [r11-20h], rbp
0x18002f4f1  cmp     bp, ax
0x18002f4f4  jnz     loc_18002F5D0
0x18002f4fa  lea     rax, [r11-20h]
0x18002f4fe  mov     [rsp+58h+cbData], 6
0x18002f506  lea     r9d, [rbp+1]; samDesired
0x18002f50a  mov     [r11-38h], rax
0x18002f50e  xor     r8d, r8d; ulOptions
0x18002f511  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x18002f518  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f51f  call    cs:__imp_RegOpenKeyExW
0x18002f526  nop     dword ptr [rax+rax+00h]
0x18002f52b  test    eax, eax
0x18002f52d  jnz     loc_18002F5C9
0x18002f533  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f538  lea     rax, [rsp+58h+cbData]
0x18002f53d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002f542  lea     rdx, aLocale; "Locale"
0x18002f549  lea     rax, [rsp+58h+Data]
0x18002f54e  xor     r9d, r9d; lpType
0x18002f551  xor     r8d, r8d; lpReserved
0x18002f554  mov     [rsp+58h+lpData], rax; lpData
0x18002f559  call    cs:__imp_RegQueryValueExW
0x18002f560  nop     dword ptr [rax+rax+00h]
0x18002f565  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f56a  mov     ebx, eax
0x18002f56c  call    cs:__imp_RegCloseKey
0x18002f573  nop     dword ptr [rax+rax+00h]
0x18002f578  test    ebx, ebx
0x18002f57a  jnz     short loc_18002F5C9
0x18002f57c  lea     r14, off_1800360E0; "EN"
0x18002f583  mov     edi, ebp
0x18002f585  mov     rsi, r14
0x18002f588  movsxd  rbx, edi
0x18002f58b  cmp     rbx, 1Ch
0x18002f58f  jnb     short loc_18002F5C9
0x18002f591  mov     rdx, [rsi]; String2
0x18002f594  lea     rcx, [rsp+58h+Data]; String1
0x18002f599  mov     r8d, 3; MaxCount
0x18002f59f  call    cs:__imp__wcsnicmp
0x18002f5a6  nop     dword ptr [rax+rax+00h]
0x18002f5ab  test    eax, eax
0x18002f5ad  jz      short loc_18002F5B7
0x18002f5af  inc     edi
0x18002f5b1  add     rsi, 10h
0x18002f5b5  jmp     short loc_18002F588
0x18002f5b7  add     rbx, rbx
0x18002f5ba  movzx   eax, word ptr [r14+rbx*8+8]
0x18002f5c0  mov     cs:word_180050644, ax
0x18002f5c7  jmp     short loc_18002F5D0
0x18002f5c9  movzx   eax, cs:word_180050644
0x18002f5d0  mov     rcx, [rsp+58h+var_10]
0x18002f5d5  xor     rcx, rsp; StackCookie
0x18002f5d8  call    __security_check_cookie
0x18002f5dd  mov     rbx, [rsp+58h+arg_0]
0x18002f5e2  mov     rbp, [rsp+58h+arg_8]
0x18002f5e7  mov     rsi, [rsp+58h+arg_10]
0x18002f5ec  mov     rdi, [rsp+58h+arg_18]
0x18002f5f1  add     rsp, 50h
0x18002f5f5  pop     r14
0x18002f5f7  retn
```
