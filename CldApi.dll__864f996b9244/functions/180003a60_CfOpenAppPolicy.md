# CfOpenAppPolicy

- ea: `0x180003a60`
- end: `0x180003aea`
- name: `CfOpenAppPolicy`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ad7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ad7`

## pseudocode

```c
__int64 __fastcall CfOpenAppPolicy(int a1, HKEY *a2)
{
  signed int v2; // ebx
  LSTATUS v4; // eax
  HKEY v5; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  hKey = 0;
  *a2 = 0;
  if ( a1 == 1 )
  {
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Policies\\Microsoft\\CloudFiles\\BlockedApps", 0, 8u, &hKey);
    v2 = v4;
    if ( v4 == 2 )
    {
      v2 = 0;
    }
    else if ( v4 > 0 )
    {
      v2 = (unsigned __int16)v4 | 0x80070000;
    }
    if ( v2 < 0 )
    {
      v5 = hKey;
    }
    else
    {
      v5 = 0;
      *a2 = hKey;
      hKey = 0;
    }
    if ( v5 )
      RegCloseKey(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003a60  mov     r11, rsp
0x180003a63  mov     [r11+8], rbx
0x180003a67  push    rdi
0x180003a68  sub     rsp, 30h
0x180003a6c  xor     ebx, ebx
0x180003a6e  mov     rdi, rdx
0x180003a71  mov     [r11+10h], rbx
0x180003a75  mov     [rdx], rbx
0x180003a78  cmp     ecx, 1
0x180003a7b  jnz     short loc_180003ADD
0x180003a7d  lea     rax, [r11+10h]
0x180003a81  xor     r8d, r8d; ulOptions
0x180003a84  lea     r9d, [rbx+8]; samDesired
0x180003a88  mov     [r11-18h], rax
0x180003a8c  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x180003a93  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180003a9a  call    cs:__imp_RegOpenKeyExW
0x180003aa0  mov     ebx, eax
0x180003aa2  cmp     eax, 2
0x180003aa5  jnz     short loc_180003AAB
0x180003aa7  xor     ebx, ebx
0x180003aa9  jmp     short loc_180003AB8
0x180003aab  test    eax, eax
0x180003aad  jle     short loc_180003AB8
0x180003aaf  movzx   ebx, ax
0x180003ab2  or      ebx, 80070000h
0x180003ab8  test    ebx, ebx
0x180003aba  js      short loc_180003ACD
0x180003abc  mov     rax, [rsp+38h+hKey]
0x180003ac1  xor     ecx, ecx
0x180003ac3  mov     [rdi], rax
0x180003ac6  mov     [rsp+38h+hKey], rcx
0x180003acb  jmp     short loc_180003AD2
0x180003acd  mov     rcx, [rsp+38h+hKey]; hKey
0x180003ad2  test    rcx, rcx
0x180003ad5  jz      short loc_180003ADD
0x180003ad7  call    cs:__imp_RegCloseKey
0x180003add  mov     eax, ebx
0x180003adf  mov     rbx, [rsp+38h+arg_0]
0x180003ae4  add     rsp, 30h
0x180003ae8  pop     rdi
0x180003ae9  retn
```
