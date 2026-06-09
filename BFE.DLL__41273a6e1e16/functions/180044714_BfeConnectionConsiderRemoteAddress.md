# BfeConnectionConsiderRemoteAddress

- ea: `0x180044714`
- end: `0x180044939`
- name: `BfeConnectionConsiderRemoteAddress`
- size: `549`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180057464`
- `0x180058fcc`

## callees

- `0x180004070`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x180044714`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800447ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800448d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800447ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800448d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044782`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044782`

## string_xrefs

- `0x180044763`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1800447e2`: `ConsiderRemoteAddress`
- `0x1800448c3`: `ConsiderRemoteAddress`
- `0x18004482e`: `RegOpenKeyExW`
- `0x1800448a2`: `BfeRegOpenKey`

## pseudocode

```c
__int64 __fastcall BfeConnectionConsiderRemoteAddress(__int64 a1)
{
  unsigned int v1; // esi
  LPBYTE v2; // r14
  unsigned int v3; // r13d
  int v4; // r12d
  unsigned int v5; // eax
  __int64 v6; // rcx
  HKEY v7; // rbx
  __int64 v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  LPBYTE lpData; // [rsp+30h] [rbp-48h] BYREF
  LPBYTE v14; // [rsp+38h] [rbp-40h] BYREF
  DWORD v15; // [rsp+40h] [rbp-38h]
  DWORD cbData; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD Type; // [rsp+58h] [rbp-20h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 8) == 2 )
  {
    v15 = 4;
    v2 = 0;
    v14 = 0;
    Type = 0;
    cbData = 0;
    lpData = 0;
    v3 = 0;
    hKey = 0;
    v4 = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
           0,
           1u,
           &hKey);
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      v11 = WfpReportSysErrorAsWinError(v6, "RegOpenKeyExW", v5);
      v8 = v11;
      if ( v11 )
        WfpReportError(v11, "BfeRegOpenKey");
      v7 = 0;
    }
    else if ( v5 == 2 )
    {
      v7 = 0;
      v8 = 0;
    }
    else
    {
      v7 = hKey;
      cbData = v15;
      v8 = WfpMemAlloc(v15, 0);
      if ( !v8 )
      {
        v9 = RegQueryValueExW(v7, L"ConsiderRemoteAddress", 0, &Type, lpData, &cbData);
        if ( v9 != 2 && v9 != 234 )
        {
          if ( v9 )
          {
            v8 = WfpReportSysErrorAsWinError(v10, "RegQueryValueExW", v9);
          }
          else if ( Type == 4 && cbData == v15 )
          {
            v2 = lpData;
            v14 = lpData;
            lpData = 0;
            v4 = 1;
          }
        }
      }
    }
    WfpMemFree(&lpData);
    BfeRegCloseKey(v7);
    if ( v8 )
    {
      WfpReportError(v8, "BfeRegQueryValue");
    }
    else if ( v4 )
    {
      v3 = *(_DWORD *)v2;
    }
    WfpMemFree(&v14);
    if ( v8 )
    {
      WfpReportError(v8, "BfeRegQueryDWord");
    }
    else
    {
      v1 = 1;
      if ( v4 )
        return v3;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180044714  push    rbp
0x180044716  push    rbx
0x180044717  push    rsi
0x180044718  push    rdi
0x180044719  push    r12
0x18004471b  push    r13
0x18004471d  push    r14
0x18004471f  push    r15
0x180044721  mov     rbp, rsp
0x180044724  sub     rsp, 78h
0x180044728  mov     rax, cs:__security_cookie
0x18004472f  xor     rax, rsp
0x180044732  mov     [rbp+var_18], rax
0x180044736  xor     esi, esi
0x180044738  cmp     dword ptr [rcx+8], 2
0x18004473c  jnz     loc_180044882
0x180044742  lea     rax, [rbp+hKey]
0x180044746  mov     [rbp+var_38], 4
0x18004474d  xor     r14d, r14d
0x180044750  mov     [rsp+78h+phkResult], rax; phkResult
0x180044755  lea     r9d, [rsi+1]; samDesired
0x180044759  mov     [rbp+var_40], r14
0x18004475d  xor     r8d, r8d; ulOptions
0x180044760  mov     [rbp+Type], esi
0x180044763  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\BF"...
0x18004476a  mov     [rbp+cbData], esi
0x18004476d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044774  mov     [rbp+lpData], rsi
0x180044778  xor     r13d, r13d
0x18004477b  mov     [rbp+hKey], rsi
0x18004477f  xor     r12d, r12d
0x180044782  call    cs:__imp_RegOpenKeyExW
0x180044789  nop     dword ptr [rax+rax+00h]
0x18004478e  test    eax, 0FFFFFFFDh
0x180044793  jnz     loc_18004482B
0x180044799  cmp     eax, 2
0x18004479c  jz      loc_18004490A
0x1800447a2  mov     eax, [rbp+var_38]
0x1800447a5  mov     rbx, [rbp+hKey]
0x1800447a9  test    eax, eax
0x1800447ab  jz      loc_1800448B3
0x1800447b1  mov     ecx, eax; dwBytes
0x1800447b3  lea     r8, [rbp+lpData]
0x1800447b7  xor     edx, edx; dwFlags
0x1800447b9  mov     [rbp+cbData], eax
0x1800447bc  call    WfpMemAlloc
0x1800447c1  mov     rdi, rax
0x1800447c4  test    rax, rax
0x1800447c7  jnz     short loc_180044844
0x1800447c9  mov     r15, [rbp+lpData]
0x1800447cd  lea     rax, [rbp+cbData]
0x1800447d1  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800447d6  lea     r9, [rbp+Type]; lpType
0x1800447da  xor     r8d, r8d; lpReserved
0x1800447dd  mov     [rsp+78h+phkResult], r15; lpData
0x1800447e2  lea     rdx, aConsiderremote; "ConsiderRemoteAddress"
0x1800447e9  mov     rcx, rbx; hKey
0x1800447ec  call    cs:__imp_RegQueryValueExW
0x1800447f3  nop     dword ptr [rax+rax+00h]
0x1800447f8  cmp     eax, 2
0x1800447fb  jz      short loc_180044844
0x1800447fd  cmp     eax, 0EAh
0x180044802  jz      short loc_180044844
0x180044804  test    eax, eax
0x180044806  jnz     loc_1800448F3
0x18004480c  cmp     [rbp+Type], 4
0x180044810  jnz     short loc_180044844
0x180044812  mov     eax, [rbp+var_38]
0x180044815  cmp     [rbp+cbData], eax
0x180044818  jnz     short loc_180044844
0x18004481a  mov     r14, r15
0x18004481d  mov     [rbp+var_40], r15
0x180044821  mov     [rbp+lpData], rsi
0x180044825  lea     r12d, [rdi+1]
0x180044829  jmp     short loc_180044844
0x18004482b  mov     r8d, eax
0x18004482e  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180044835  call    WfpReportSysErrorAsWinError
0x18004483a  mov     rdi, rax
0x18004483d  test    rax, rax
0x180044840  jnz     short loc_1800448A2
0x180044842  xor     ebx, ebx
0x180044844  lea     rcx, [rbp+lpData]
0x180044848  call    WfpMemFree
0x18004484d  mov     rcx, rbx
0x180044850  call    BfeRegCloseKey
0x180044855  test    rdi, rdi
0x180044858  jnz     loc_180044911
0x18004485e  test    r12d, r12d
0x180044861  jz      short loc_180044866
0x180044863  mov     r13d, [r14]
0x180044866  lea     rcx, [rbp+var_40]
0x18004486a  call    WfpMemFree
0x18004486f  test    rdi, rdi
0x180044872  jnz     loc_180044925
0x180044878  test    r12d, r12d
0x18004487b  lea     esi, [rdi+1]
0x18004487e  cmovnz  esi, r13d
0x180044882  mov     eax, esi
0x180044884  mov     rcx, [rbp+var_18]
0x180044888  xor     rcx, rsp; StackCookie
0x18004488b  call    __security_check_cookie
0x180044890  add     rsp, 78h
0x180044894  pop     r15
0x180044896  pop     r14
0x180044898  pop     r13
0x18004489a  pop     r12
0x18004489c  pop     rdi
0x18004489d  pop     rsi
0x18004489e  pop     rbx
0x18004489f  pop     rbp
0x1800448a0  retn
0x1800448a2  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x1800448a9  mov     rcx, rax
0x1800448ac  call    WfpReportError
0x1800448b1  jmp     short loc_180044842
0x1800448b3  lea     rax, [rbp+var_38]
0x1800448b7  xor     r8d, r8d; lpReserved
0x1800448ba  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800448bf  lea     r9, [rbp+Type]; lpType
0x1800448c3  lea     rdx, aConsiderremote; "ConsiderRemoteAddress"
0x1800448ca  mov     [rsp+78h+phkResult], rsi; lpData
0x1800448cf  mov     rcx, rbx; hKey
0x1800448d2  call    cs:__imp_RegQueryValueExW
0x1800448d9  nop     dword ptr [rax+rax+00h]
0x1800448de  cmp     eax, 2
0x1800448e1  jz      loc_18008D8AE
0x1800448e7  test    eax, eax
0x1800448e9  jnz     short loc_1800448F3
0x1800448eb  mov     eax, [rbp+var_38]
0x1800448ee  jmp     loc_1800447B1
0x1800448f3  mov     r8d, eax
0x1800448f6  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x1800448fd  call    WfpReportSysErrorAsWinError
0x180044902  mov     rdi, rax
0x180044905  jmp     loc_180044844
0x18004490a  xor     ebx, ebx
0x18004490c  jmp     loc_18008D8AE
0x180044911  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180044918  mov     rcx, rdi
0x18004491b  call    WfpReportError
0x180044920  jmp     loc_180044866
0x180044925  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18004492c  mov     rcx, rdi
0x18004492f  call    WfpReportError
0x180044934  jmp     loc_180044882
0x18008d8ae  xor     edi, edi
0x18008d8b0  jmp     loc_180044844
```
