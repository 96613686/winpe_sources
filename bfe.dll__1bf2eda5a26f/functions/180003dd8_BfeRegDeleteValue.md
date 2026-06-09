# BfeRegDeleteValue

- ea: `0x180003dd8`
- end: `0x180003f1e`
- name: `BfeRegDeleteValue`
- size: `326`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, void *hTransaction)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004a20`
- `0x18003471c`

## callees

- `0x180003dd8`
- `0x18001236c`
- `0x180018b74`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003eba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003eba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e1c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e35`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180003e8a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180003e8a`

## string_xrefs

- `0x180003ef6`: `RegDeleteValueW`
- `0x180003ec7`: `RegOpenKeyExW`
- `0x180003ed3`: `RegOpenKeyTransactedW`
- `0x180003edf`: `BfeRegOpenKey`
- `0x180003f0a`: `BfeRegDeleteValue`

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
0x180003dd8  push    rbx
0x180003dda  push    rbp
0x180003ddb  push    rsi
0x180003ddc  push    rdi
0x180003ddd  sub     rsp, 58h
0x180003de1  mov     rax, cs:__security_cookie
0x180003de8  xor     rax, rsp
0x180003deb  mov     [rsp+78h+var_30], rax
0x180003df0  mov     rbp, r8
0x180003df3  test    rdx, rdx
0x180003df6  jnz     short loc_180003E5D
0x180003df8  xor     ebx, ebx
0x180003dfa  xor     edi, edi
0x180003dfc  jmp     short loc_180003E19
0x180003dfe  mov     r8d, eax
0x180003e01  call    WfpReportSysErrorAsWinError
0x180003e06  mov     rbx, rax
0x180003e09  test    rax, rax
0x180003e0c  jnz     loc_180003EDF
0x180003e12  mov     rcx, rdi; hKey
0x180003e15  test    esi, esi
0x180003e17  jz      short loc_180003E2D
0x180003e19  mov     rdx, rbp; lpValueName
0x180003e1c  call    cs:__imp_RegDeleteValueW
0x180003e22  test    eax, 0FFFFFFFDh
0x180003e27  jnz     loc_180003EF3
0x180003e2d  test    rdi, rdi
0x180003e30  jz      short loc_180003E3B
0x180003e32  mov     rcx, rdi; hKey
0x180003e35  call    cs:__imp_RegCloseKey
0x180003e3b  test    rbx, rbx
0x180003e3e  jnz     loc_180003F0A
0x180003e44  mov     rax, rbx
0x180003e47  mov     rcx, [rsp+78h+var_30]
0x180003e4c  xor     rcx, rsp; StackCookie
0x180003e4f  call    __security_check_cookie
0x180003e54  add     rsp, 58h
0x180003e58  pop     rdi
0x180003e59  pop     rsi
0x180003e5a  pop     rbp
0x180003e5b  pop     rbx
0x180003e5c  retn
0x180003e5d  xor     edi, edi
0x180003e5f  mov     [rsp+78h+var_38], 0
0x180003e68  xor     esi, esi
0x180003e6a  lea     rax, [rsp+78h+var_38]
0x180003e6f  xor     r8d, r8d; ulOptions
0x180003e72  test    r9, r9
0x180003e75  jz      short loc_180003EAF
0x180003e77  mov     [rsp+78h+pExtendedParemeter], rsi; pExtendedParemeter
0x180003e7c  mov     [rsp+78h+hTransaction], r9; hTransaction
0x180003e81  lea     r9d, [rdi+2]; samDesired
0x180003e85  mov     [rsp+78h+phkResult], rax; phkResult
0x180003e8a  call    cs:__imp_RegOpenKeyTransactedW
0x180003e90  test    eax, 0FFFFFFFDh
0x180003e95  jnz     short loc_180003ED3
0x180003e97  xor     ebx, ebx
0x180003e99  cmp     eax, 2
0x180003e9c  jz      loc_180003E12
0x180003ea2  mov     rdi, [rsp+78h+var_38]
0x180003ea7  lea     esi, [rbx+1]
0x180003eaa  jmp     loc_180003E12
0x180003eaf  mov     r9d, 2; samDesired
0x180003eb5  mov     [rsp+78h+phkResult], rax; phkResult
0x180003eba  call    cs:__imp_RegOpenKeyExW
0x180003ec0  test    eax, 0FFFFFFFDh
0x180003ec5  jz      short loc_180003E97
0x180003ec7  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180003ece  jmp     loc_180003DFE
0x180003ed3  lea     rdx, aRegopenkeytran_1; "RegOpenKeyTransactedW"
0x180003eda  jmp     loc_180003DFE
0x180003edf  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180003ee6  mov     rcx, rbx
0x180003ee9  call    WfpReportError
0x180003eee  jmp     loc_180003E2D
0x180003ef3  mov     r8d, eax
0x180003ef6  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x180003efd  call    WfpReportSysErrorAsWinError
0x180003f02  mov     rbx, rax
0x180003f05  jmp     loc_180003E2D
0x180003f0a  lea     rdx, aBferegdeleteva; "BfeRegDeleteValue"
0x180003f11  mov     rcx, rbx
0x180003f14  call    WfpReportError
0x180003f19  jmp     loc_180003E44
```
