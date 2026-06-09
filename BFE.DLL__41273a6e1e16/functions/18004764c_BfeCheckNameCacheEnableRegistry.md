# BfeCheckNameCacheEnableRegistry

- ea: `0x18004764c`
- end: `0x18004785c`
- name: `BfeCheckNameCacheEnableRegistry`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18006800c`

## callees

- `0x180004070`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x18004764c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047721`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004778c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047721`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004778c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800476ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800476ae`

## string_xrefs

- `0x1800476c4`: `RegOpenKeyExW`
- `0x180047694`: `SYSTEM\CurrentControlSet\Services\BFE\Parameters`
- `0x180047817`: `BfeCheckNameCacheEnableRegistry`
- `0x1800476d8`: `BfeRegOpenKey`

## pseudocode

```c
__int64 BfeCheckNameCacheEnableRegistry()
{
  int v0; // r12d
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
    WfpReportError(v6, "BfeCheckNameCacheEnableRegistry");
  }
  else if ( v2 )
  {
    v6 = 0;
    dword_1800F5EE4 = v0 != 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18004764c  push    rbp
0x18004764e  push    rbx
0x18004764f  push    rsi
0x180047650  push    rdi
0x180047651  push    r12
0x180047653  push    r14
0x180047655  push    r15
0x180047657  mov     rbp, rsp
0x18004765a  sub     rsp, 70h
0x18004765e  mov     rax, cs:__security_cookie
0x180047665  xor     rax, rsp
0x180047668  mov     [rbp+var_10], rax
0x18004766c  xor     r12d, r12d
0x18004766f  mov     [rbp+cbData], 4
0x180047676  xor     esi, esi
0x180047678  mov     [rbp+Type], r12d
0x18004767c  lea     rax, [rbp+hKey]
0x180047680  mov     [rbp+var_28], r12d
0x180047684  xor     r8d, r8d; ulOptions
0x180047687  mov     [rbp+lpData], r12
0x18004768b  lea     r9d, [r12+1]; samDesired
0x180047690  mov     [rbp+var_38], rsi
0x180047694  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\BF"...
0x18004769b  mov     [rbp+hKey], rsi
0x18004769f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800476a6  mov     [rsp+70h+phkResult], rax; phkResult
0x1800476ab  xor     r14d, r14d
0x1800476ae  call    cs:__imp_RegOpenKeyExW
0x1800476b5  nop     dword ptr [rax+rax+00h]
0x1800476ba  test    eax, 0FFFFFFFDh
0x1800476bf  jz      short loc_1800476EE
0x1800476c1  mov     r8d, eax
0x1800476c4  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800476cb  call    WfpReportSysErrorAsWinError
0x1800476d0  mov     rdi, rax
0x1800476d3  test    rax, rax
0x1800476d6  jz      short loc_1800476E7
0x1800476d8  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x1800476df  mov     rcx, rax
0x1800476e2  call    WfpReportError
0x1800476e7  xor     ebx, ebx
0x1800476e9  jmp     loc_1800477CB
0x1800476ee  cmp     eax, 2
0x1800476f1  jz      loc_1800477C7
0x1800476f7  mov     eax, [rbp+cbData]
0x1800476fa  mov     rbx, [rbp+hKey]
0x1800476fe  test    eax, eax
0x180047700  jnz     short loc_180047751
0x180047702  lea     rax, [rbp+cbData]
0x180047706  xor     r8d, r8d; lpReserved
0x180047709  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18004770e  lea     r9, [rbp+Type]; lpType
0x180047712  lea     rdx, aSetnameonsecur; "SetNameOnSecureSocket"
0x180047719  mov     [rsp+70h+phkResult], rsi; lpData
0x18004771e  mov     rcx, rbx; hKey
0x180047721  call    cs:__imp_RegQueryValueExW
0x180047728  nop     dword ptr [rax+rax+00h]
0x18004772d  cmp     eax, 2
0x180047730  jz      loc_1800477C9
0x180047736  test    eax, eax
0x180047738  jz      short loc_18004774E
0x18004773a  mov     r8d, eax
0x18004773d  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180047744  call    WfpReportSysErrorAsWinError
0x180047749  mov     rdi, rax
0x18004774c  jmp     short loc_1800477CB
0x18004774e  mov     eax, [rbp+cbData]
0x180047751  mov     ecx, eax; dwBytes
0x180047753  lea     r8, [rbp+lpData]
0x180047757  xor     edx, edx; dwFlags
0x180047759  mov     [rbp+var_28], eax
0x18004775c  call    WfpMemAlloc
0x180047761  mov     rdi, rax
0x180047764  test    rax, rax
0x180047767  jnz     short loc_1800477CB
0x180047769  mov     r15, [rbp+lpData]
0x18004776d  lea     rax, [rbp+var_28]
0x180047771  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180047776  lea     r9, [rbp+Type]; lpType
0x18004777a  xor     r8d, r8d; lpReserved
0x18004777d  mov     [rsp+70h+phkResult], r15; lpData
0x180047782  lea     rdx, aSetnameonsecur; "SetNameOnSecureSocket"
0x180047789  mov     rcx, rbx; hKey
0x18004778c  call    cs:__imp_RegQueryValueExW
0x180047793  nop     dword ptr [rax+rax+00h]
0x180047798  cmp     eax, 2
0x18004779b  jz      short loc_1800477CB
0x18004779d  cmp     eax, 0EAh
0x1800477a2  jz      short loc_1800477CB
0x1800477a4  test    eax, eax
0x1800477a6  jnz     short loc_18004773A
0x1800477a8  cmp     [rbp+Type], 4
0x1800477ac  jnz     short loc_1800477CB
0x1800477ae  mov     eax, [rbp+cbData]
0x1800477b1  cmp     [rbp+var_28], eax
0x1800477b4  jnz     short loc_1800477CB
0x1800477b6  mov     rsi, r15
0x1800477b9  mov     [rbp+var_38], r15
0x1800477bd  mov     [rbp+lpData], r12
0x1800477c1  lea     r14d, [rdi+1]
0x1800477c5  jmp     short loc_1800477CB
0x1800477c7  xor     ebx, ebx
0x1800477c9  xor     edi, edi
0x1800477cb  lea     rcx, [rbp+lpData]
0x1800477cf  call    WfpMemFree
0x1800477d4  mov     rcx, rbx
0x1800477d7  call    BfeRegCloseKey
0x1800477dc  test    rdi, rdi
0x1800477df  jz      short loc_1800477F2
0x1800477e1  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x1800477e8  mov     rcx, rdi
0x1800477eb  call    WfpReportError
0x1800477f0  jmp     short loc_1800477FA
0x1800477f2  test    r14d, r14d
0x1800477f5  jz      short loc_1800477FA
0x1800477f7  mov     r12d, [rsi]
0x1800477fa  lea     rcx, [rbp+var_38]
0x1800477fe  call    WfpMemFree
0x180047803  test    rdi, rdi
0x180047806  jz      short loc_180047828
0x180047808  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18004780f  mov     rcx, rdi
0x180047812  call    WfpReportError
0x180047817  lea     rdx, aBfechecknameca; "BfeCheckNameCacheEnableRegistry"
0x18004781e  mov     rcx, rdi
0x180047821  call    WfpReportError
0x180047826  jmp     short loc_18004783D
0x180047828  test    r14d, r14d
0x18004782b  jz      short loc_18004783D
0x18004782d  xor     eax, eax
0x18004782f  test    r12d, r12d
0x180047832  setnz   al
0x180047835  xor     edi, edi
0x180047837  mov     cs:dword_1800F5EE4, eax
0x18004783d  mov     rax, rdi
0x180047840  mov     rcx, [rbp+var_10]
0x180047844  xor     rcx, rsp; StackCookie
0x180047847  call    __security_check_cookie
0x18004784c  add     rsp, 70h
0x180047850  pop     r15
0x180047852  pop     r14
0x180047854  pop     r12
0x180047856  pop     rdi
0x180047857  pop     rsi
0x180047858  pop     rbx
0x180047859  pop     rbp
0x18004785a  retn
```
