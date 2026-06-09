# BfeRegDeleteValue

- ea: `0x1800058c4`
- end: `0x180005a23`
- name: `BfeRegDeleteValue`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003dac`
- `0x180034628`

## callees

- `0x1800058c4`
- `0x180012d8c`
- `0x1800197d0`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005908`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005927`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005927`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180005983`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180005983`

## string_xrefs

- `0x1800059cc`: `RegOpenKeyExW`
- `0x1800059d8`: `RegOpenKeyTransactedW`
- `0x1800059e4`: `BfeRegOpenKey`
- `0x1800059fb`: `RegDeleteValueW`
- `0x180005a0f`: `BfeRegDeleteValue`

## pseudocode

```c
__int64 __fastcall BfeRegDeleteValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, void *hTransaction)
{
  __int64 v5; // rbx
  HKEY v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rcx
  int v11; // esi
  unsigned int v12; // eax
  __int64 v13; // rcx
  const char *v14; // rdx
  HKEY phkResult; // [rsp+40h] [rbp-38h] BYREF

  if ( a2 )
  {
    v6 = 0;
    phkResult = 0;
    v11 = 0;
    if ( hTransaction )
    {
      v12 = RegOpenKeyTransactedW(a1, a2, 0, 2u, &phkResult, hTransaction, 0);
      if ( (v12 & 0xFFFFFFFD) == 0 )
        goto LABEL_14;
      v14 = "RegOpenKeyTransactedW";
    }
    else
    {
      v12 = RegOpenKeyExW(a1, a2, 0, 2u, &phkResult);
      if ( (v12 & 0xFFFFFFFD) == 0 )
      {
LABEL_14:
        v5 = 0;
        if ( v12 != 2 )
        {
          v6 = phkResult;
          v11 = 1;
        }
LABEL_4:
        a1 = v6;
        if ( !v11 )
          goto LABEL_7;
        goto LABEL_5;
      }
      v14 = "RegOpenKeyExW";
    }
    v7 = WfpReportSysErrorAsWinError(v13, v14, v12);
    v5 = v7;
    if ( v7 )
    {
      WfpReportError(v7, "BfeRegOpenKey");
      goto LABEL_7;
    }
    goto LABEL_4;
  }
  v5 = 0;
  v6 = 0;
LABEL_5:
  v8 = RegDeleteValueW(a1, a3);
  if ( (v8 & 0xFFFFFFFD) != 0 )
    v5 = WfpReportSysErrorAsWinError(v9, "RegDeleteValueW", v8);
LABEL_7:
  if ( v6 )
    RegCloseKey(v6);
  if ( v5 )
    WfpReportError(v5, "BfeRegDeleteValue");
  return v5;
}

```

## disassembly

```asm
0x1800058c4  push    rbx
0x1800058c6  push    rbp
0x1800058c7  push    rsi
0x1800058c8  push    rdi
0x1800058c9  sub     rsp, 58h
0x1800058cd  mov     rax, cs:__security_cookie
0x1800058d4  xor     rax, rsp
0x1800058d7  mov     [rsp+78h+var_30], rax
0x1800058dc  mov     rbp, r8
0x1800058df  test    rdx, rdx
0x1800058e2  jnz     short loc_180005956
0x1800058e4  xor     ebx, ebx
0x1800058e6  xor     edi, edi
0x1800058e8  jmp     short loc_180005905
0x1800058ea  mov     r8d, eax
0x1800058ed  call    WfpReportSysErrorAsWinError
0x1800058f2  mov     rbx, rax
0x1800058f5  test    rax, rax
0x1800058f8  jnz     loc_1800059E4
0x1800058fe  mov     rcx, rdi; hKey
0x180005901  test    esi, esi
0x180005903  jz      short loc_18000591F
0x180005905  mov     rdx, rbp; lpValueName
0x180005908  call    cs:__imp_RegDeleteValueW
0x18000590f  nop     dword ptr [rax+rax+00h]
0x180005914  test    eax, 0FFFFFFFDh
0x180005919  jnz     loc_1800059F8
0x18000591f  test    rdi, rdi
0x180005922  jz      short loc_180005933
0x180005924  mov     rcx, rdi; hKey
0x180005927  call    cs:__imp_RegCloseKey
0x18000592e  nop     dword ptr [rax+rax+00h]
0x180005933  test    rbx, rbx
0x180005936  jnz     loc_180005A0F
0x18000593c  mov     rax, rbx
0x18000593f  mov     rcx, [rsp+78h+var_30]
0x180005944  xor     rcx, rsp; StackCookie
0x180005947  call    __security_check_cookie
0x18000594c  add     rsp, 58h
0x180005950  pop     rdi
0x180005951  pop     rsi
0x180005952  pop     rbp
0x180005953  pop     rbx
0x180005954  retn
0x180005956  xor     edi, edi
0x180005958  mov     [rsp+78h+var_38], 0
0x180005961  xor     esi, esi
0x180005963  lea     rax, [rsp+78h+var_38]
0x180005968  xor     r8d, r8d; ulOptions
0x18000596b  test    r9, r9
0x18000596e  jz      short loc_1800059AE
0x180005970  mov     [rsp+78h+pExtendedParemeter], rsi; pExtendedParemeter
0x180005975  mov     [rsp+78h+hTransaction], r9; hTransaction
0x18000597a  lea     r9d, [rdi+2]; samDesired
0x18000597e  mov     [rsp+78h+phkResult], rax; phkResult
0x180005983  call    cs:__imp_RegOpenKeyTransactedW
0x18000598a  nop     dword ptr [rax+rax+00h]
0x18000598f  test    eax, 0FFFFFFFDh
0x180005994  jnz     short loc_1800059D8
0x180005996  xor     ebx, ebx
0x180005998  cmp     eax, 2
0x18000599b  jz      loc_1800058FE
0x1800059a1  mov     rdi, [rsp+78h+var_38]
0x1800059a6  lea     esi, [rbx+1]
0x1800059a9  jmp     loc_1800058FE
0x1800059ae  mov     r9d, 2; samDesired
0x1800059b4  mov     [rsp+78h+phkResult], rax; phkResult
0x1800059b9  call    cs:__imp_RegOpenKeyExW
0x1800059c0  nop     dword ptr [rax+rax+00h]
0x1800059c5  test    eax, 0FFFFFFFDh
0x1800059ca  jz      short loc_180005996
0x1800059cc  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800059d3  jmp     loc_1800058EA
0x1800059d8  lea     rdx, aRegopenkeytran_1; "RegOpenKeyTransactedW"
0x1800059df  jmp     loc_1800058EA
0x1800059e4  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x1800059eb  mov     rcx, rbx
0x1800059ee  call    WfpReportError
0x1800059f3  jmp     loc_18000591F
0x1800059f8  mov     r8d, eax
0x1800059fb  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x180005a02  call    WfpReportSysErrorAsWinError
0x180005a07  mov     rbx, rax
0x180005a0a  jmp     loc_18000591F
0x180005a0f  lea     rdx, aBferegdeleteva; "BfeRegDeleteValue"
0x180005a16  mov     rcx, rbx
0x180005a19  call    WfpReportError
0x180005a1e  jmp     loc_18000593C
```
