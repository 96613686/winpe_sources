# BfeCheckNameCacheEnableRegistry

- ea: `0x18004582c`
- end: `0x180045a29`
- name: `BfeCheckNameCacheEnableRegistry`
- size: `509`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180065b00`

## callees

- `0x1800039e4`
- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x18004582c`
- `0x180058b30`
- `0x1800669ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800458fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045960`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800458fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045960`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004588e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004588e`

## string_xrefs

- `0x18004589e`: `RegOpenKeyExW`
- `0x180045874`: `SYSTEM\CurrentControlSet\Services\BFE\Parameters`
- `0x1800459fc`: `BfeCheckNameCacheEnableRegistry`
- `0x1800458b2`: `BfeRegOpenKey`

## pseudocode

```c
__int64 BfeCheckNameCacheEnableRegistry()
{
  unsigned int v0; // r12d
  LPBYTE v1; // rsi
  int v2; // r14d
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  HKEY v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // rcx
  LPBYTE lpData; // [rsp+30h] [rbp-40h] BYREF
  LPBYTE v12; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h]
  DWORD lpcbData; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+58h] [rbp-18h] BYREF

  v0 = 0;
  cbData = 4;
  v1 = 0;
  Type = 0;
  lpcbData = 0;
  lpData = 0;
  v12 = 0;
  hKey = 0;
  v2 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\BFE\\Parameters", 0, 1u, &hKey);
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    v5 = WfpReportSysErrorAsWinError(v4, "RegOpenKeyExW", v3);
    v6 = v5;
    if ( v5 )
      WfpReportError(v5, "BfeRegOpenKey");
    v7 = 0;
  }
  else if ( v3 == 2 )
  {
    v7 = 0;
    v6 = 0;
  }
  else
  {
    v7 = hKey;
    lpcbData = cbData;
    v6 = WfpMemAlloc(cbData, 0);
    if ( !v6 )
    {
      v8 = RegQueryValueExW(v7, L"SetNameOnSecureSocket", 0, &Type, lpData, &lpcbData);
      if ( v8 != 2 && v8 != 234 )
      {
        if ( v8 )
        {
          v6 = WfpReportSysErrorAsWinError(v9, "RegQueryValueExW", v8);
        }
        else if ( Type == 4 && lpcbData == cbData )
        {
          v1 = lpData;
          v12 = lpData;
          lpData = 0;
          v2 = 1;
        }
      }
    }
  }
  WfpMemFree(&lpData);
  BfeRegCloseKey(v7);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryValue");
  }
  else if ( v2 )
  {
    v0 = *(_DWORD *)v1;
  }
  WfpMemFree(&v12);
  if ( v6 )
  {
    WfpReportError(v6, "BfeRegQueryDWord");
LABEL_24:
    WfpReportError(v6, "BfeCheckNameCacheEnableRegistry");
    return v6;
  }
  if ( v2 )
  {
    v6 = BfeNameCacheEnable(v0);
    if ( v6 )
      goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x18004582c  push    rbp
0x18004582e  push    rbx
0x18004582f  push    rsi
0x180045830  push    rdi
0x180045831  push    r12
0x180045833  push    r14
0x180045835  push    r15
0x180045837  mov     rbp, rsp
0x18004583a  sub     rsp, 70h
0x18004583e  mov     rax, cs:__security_cookie
0x180045845  xor     rax, rsp
0x180045848  mov     [rbp+var_10], rax
0x18004584c  xor     r12d, r12d
0x18004584f  mov     [rbp+cbData], 4
0x180045856  xor     esi, esi
0x180045858  mov     [rbp+Type], r12d
0x18004585c  lea     rax, [rbp+hKey]
0x180045860  mov     [rbp+var_28], r12d
0x180045864  xor     r8d, r8d; ulOptions
0x180045867  mov     [rbp+lpData], r12
0x18004586b  lea     r9d, [r12+1]; samDesired
0x180045870  mov     [rbp+var_38], rsi
0x180045874  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\BF"...
0x18004587b  mov     [rbp+hKey], rsi
0x18004587f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045886  mov     [rsp+70h+phkResult], rax; phkResult
0x18004588b  xor     r14d, r14d
0x18004588e  call    cs:__imp_RegOpenKeyExW
0x180045894  test    eax, 0FFFFFFFDh
0x180045899  jz      short loc_1800458C8
0x18004589b  mov     r8d, eax
0x18004589e  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800458a5  call    WfpReportSysErrorAsWinError
0x1800458aa  mov     rdi, rax
0x1800458ad  test    rax, rax
0x1800458b0  jz      short loc_1800458C1
0x1800458b2  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x1800458b9  mov     rcx, rax
0x1800458bc  call    WfpReportError
0x1800458c1  xor     ebx, ebx
0x1800458c3  jmp     loc_180045999
0x1800458c8  cmp     eax, 2
0x1800458cb  jz      loc_180045995
0x1800458d1  mov     eax, [rbp+cbData]
0x1800458d4  mov     rbx, [rbp+hKey]
0x1800458d8  test    eax, eax
0x1800458da  jnz     short loc_180045925
0x1800458dc  lea     rax, [rbp+cbData]
0x1800458e0  xor     r8d, r8d; lpReserved
0x1800458e3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800458e8  lea     r9, [rbp+Type]; lpType
0x1800458ec  lea     rdx, aSetnameonsecur; "SetNameOnSecureSocket"
0x1800458f3  mov     [rsp+70h+phkResult], rsi; lpData
0x1800458f8  mov     rcx, rbx; hKey
0x1800458fb  call    cs:__imp_RegQueryValueExW
0x180045901  cmp     eax, 2
0x180045904  jz      loc_180045997
0x18004590a  test    eax, eax
0x18004590c  jz      short loc_180045922
0x18004590e  mov     r8d, eax
0x180045911  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180045918  call    WfpReportSysErrorAsWinError
0x18004591d  mov     rdi, rax
0x180045920  jmp     short loc_180045999
0x180045922  mov     eax, [rbp+cbData]
0x180045925  mov     ecx, eax; dwBytes
0x180045927  lea     r8, [rbp+lpData]
0x18004592b  xor     edx, edx; dwFlags
0x18004592d  mov     [rbp+var_28], eax
0x180045930  call    WfpMemAlloc
0x180045935  mov     rdi, rax
0x180045938  test    rax, rax
0x18004593b  jnz     short loc_180045999
0x18004593d  mov     r15, [rbp+lpData]
0x180045941  lea     rax, [rbp+var_28]
0x180045945  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18004594a  lea     r9, [rbp+Type]; lpType
0x18004594e  xor     r8d, r8d; lpReserved
0x180045951  mov     [rsp+70h+phkResult], r15; lpData
0x180045956  lea     rdx, aSetnameonsecur; "SetNameOnSecureSocket"
0x18004595d  mov     rcx, rbx; hKey
0x180045960  call    cs:__imp_RegQueryValueExW
0x180045966  cmp     eax, 2
0x180045969  jz      short loc_180045999
0x18004596b  cmp     eax, 0EAh
0x180045970  jz      short loc_180045999
0x180045972  test    eax, eax
0x180045974  jnz     short loc_18004590E
0x180045976  cmp     [rbp+Type], 4
0x18004597a  jnz     short loc_180045999
0x18004597c  mov     eax, [rbp+cbData]
0x18004597f  cmp     [rbp+var_28], eax
0x180045982  jnz     short loc_180045999
0x180045984  mov     rsi, r15
0x180045987  mov     [rbp+var_38], r15
0x18004598b  mov     [rbp+lpData], r12
0x18004598f  lea     r14d, [rdi+1]
0x180045993  jmp     short loc_180045999
0x180045995  xor     ebx, ebx
0x180045997  xor     edi, edi
0x180045999  lea     rcx, [rbp+lpData]
0x18004599d  call    WfpMemFree
0x1800459a2  mov     rcx, rbx
0x1800459a5  call    BfeRegCloseKey
0x1800459aa  test    rdi, rdi
0x1800459ad  jz      short loc_1800459C0
0x1800459af  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x1800459b6  mov     rcx, rdi
0x1800459b9  call    WfpReportError
0x1800459be  jmp     short loc_1800459C8
0x1800459c0  test    r14d, r14d
0x1800459c3  jz      short loc_1800459C8
0x1800459c5  mov     r12d, [rsi]
0x1800459c8  lea     rcx, [rbp+var_38]
0x1800459cc  call    WfpMemFree
0x1800459d1  test    rdi, rdi
0x1800459d4  jz      short loc_1800459E7
0x1800459d6  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x1800459dd  mov     rcx, rdi
0x1800459e0  call    WfpReportError
0x1800459e5  jmp     short loc_1800459FC
0x1800459e7  test    r14d, r14d
0x1800459ea  jz      short loc_180045A0B
0x1800459ec  mov     ecx, r12d
0x1800459ef  call    BfeNameCacheEnable
0x1800459f4  mov     rdi, rax
0x1800459f7  test    rax, rax
0x1800459fa  jz      short loc_180045A0B
0x1800459fc  lea     rdx, aBfechecknameca; "BfeCheckNameCacheEnableRegistry"
0x180045a03  mov     rcx, rdi
0x180045a06  call    WfpReportError
0x180045a0b  mov     rax, rdi
0x180045a0e  mov     rcx, [rbp+var_10]
0x180045a12  xor     rcx, rsp; StackCookie
0x180045a15  call    __security_check_cookie
0x180045a1a  add     rsp, 70h
0x180045a1e  pop     r15
0x180045a20  pop     r14
0x180045a22  pop     r12
0x180045a24  pop     rdi
0x180045a25  pop     rsi
0x180045a26  pop     rbx
0x180045a27  pop     rbp
0x180045a28  retn
```
