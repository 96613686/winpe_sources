# GetPerformanceRegKey

- ea: `0x140013360`
- end: `0x140013405`
- name: `GetPerformanceRegKey`
- size: `165`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013270`
- `0x140013410`

## callees

- `0x140013360`
- `0x1400137e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400133a1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400133c7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400133a1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400133c7`
- `ADVAPI32!RegCloseKey` at `0x1400133d4`
- `ADVAPI32!RegCloseKey` at `0x1400133d4`

## pseudocode

```c
__int64 __fastcall GetPerformanceRegKey(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  if ( !a2 )
    return 13;
  hKey = 0;
  if ( RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
    return 2;
  if ( !hKey )
    return 2;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, a3);
  RegCloseKey(hKey);
  if ( v5 || !*a3 )
    return 2;
  else
    return 0;
}

```

## disassembly

```asm
0x140013360  mov     [rsp+arg_18], rbx
0x140013365  push    rdi
0x140013366  sub     rsp, 40h
0x14001336a  mov     rax, cs:__security_cookie
0x140013371  xor     rax, rsp
0x140013374  mov     [rsp+48h+var_10], rax
0x140013379  mov     rdi, r8
0x14001337c  test    rdx, rdx
0x14001337f  jnz     short loc_140013386
0x140013381  lea     eax, [rdx+0Dh]
0x140013384  jmp     short loc_1400133ED
0x140013386  and     [rsp+48h+hKey], 0
0x14001338c  lea     rax, [rsp+48h+hKey]
0x140013391  mov     ebx, 20019h
0x140013396  mov     [rsp+48h+phkResult], rax; phkResult
0x14001339b  mov     r9d, ebx; samDesired
0x14001339e  xor     r8d, r8d; ulOptions
0x1400133a1  call    cs:__imp_RegOpenKeyExW
0x1400133a7  test    eax, eax
0x1400133a9  jnz     short loc_1400133E8
0x1400133ab  mov     rcx, [rsp+48h+hKey]; hKey
0x1400133b0  test    rcx, rcx
0x1400133b3  jz      short loc_1400133E8
0x1400133b5  mov     rdx, cs:lpSubKey; lpSubKey
0x1400133bc  mov     r9d, ebx; samDesired
0x1400133bf  xor     r8d, r8d; ulOptions
0x1400133c2  mov     [rsp+48h+phkResult], rdi; phkResult
0x1400133c7  call    cs:__imp_RegOpenKeyExW
0x1400133cd  mov     rcx, [rsp+48h+hKey]; hKey
0x1400133d2  mov     ebx, eax
0x1400133d4  call    cs:__imp_RegCloseKey
0x1400133da  test    ebx, ebx
0x1400133dc  jnz     short loc_1400133E8
0x1400133de  cmp     qword ptr [rdi], 0
0x1400133e2  jz      short loc_1400133E8
0x1400133e4  xor     eax, eax
0x1400133e6  jmp     short loc_1400133ED
0x1400133e8  mov     eax, 2
0x1400133ed  mov     rcx, [rsp+48h+var_10]
0x1400133f2  xor     rcx, rsp; StackCookie
0x1400133f5  call    __security_check_cookie
0x1400133fa  mov     rbx, [rsp+48h+arg_18]
0x1400133ff  add     rsp, 40h
0x140013403  pop     rdi
0x140013404  retn
```
