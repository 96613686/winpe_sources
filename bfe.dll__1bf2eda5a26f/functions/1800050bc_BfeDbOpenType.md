# BfeDbOpenType

- ea: `0x1800050bc`
- end: `0x18000525c`
- name: `BfeDbOpenType`
- size: `416`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004fc0`
- `0x180044c80`
- `0x1800660fc`

## callees

- `0x1800050bc`
- `0x1800052ac`
- `0x18001236c`
- `0x180018b74`
- `0x180034e04`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800050f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800050f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000520e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000520e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005194`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000515e`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000515e`

## string_xrefs

- `0x180005248`: `BfeDbOpenType`
- `0x180005228`: `RegCreateKeyTransactedW`
- `0x180005234`: `BfeRegCreateKey`
- `0x18000521c`: `RegCreateKeyExW`

## pseudocode

```c
__int64 __fastcall BfeDbOpenType(HKEY hKey, unsigned int a2, HKEY *a3)
{
  HKEY v3; // rdi
  HKEY v6; // rsi
  _QWORD *Value; // rax
  void *hTransaction; // rbx
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v15; // rax
  const char *v16; // rdx
  HKEY phkResult; // [rsp+60h] [rbp-38h] BYREF

  v3 = 0;
  phkResult = 0;
  v6 = hKey;
  if ( !hKey )
  {
    v15 = BfeDbOpen(&phkResult);
    v3 = phkResult;
    v12 = v15;
    if ( v15 )
      goto LABEL_9;
    v6 = phkResult;
  }
  Value = TlsGetValue(gBfeContextComponent);
  if ( Value )
    hTransaction = (void *)Value[2];
  else
    hTransaction = 0;
  v9 = (const WCHAR *)BfeObjectTypeIdToString(a2);
  phkResult = 0;
  *a3 = 0;
  if ( hTransaction )
  {
    v10 = RegCreateKeyTransactedW(v6, v9, 0, 0, 0, 3u, 0, &phkResult, 0, hTransaction, 0);
    if ( !v10 )
    {
LABEL_6:
      v12 = 0;
      *a3 = phkResult;
      goto LABEL_9;
    }
    v16 = "RegCreateKeyTransactedW";
  }
  else
  {
    v10 = RegCreateKeyExW(v6, v9, 0, 0, 0, 3u, 0, &phkResult, 0);
    if ( !v10 )
      goto LABEL_6;
    v16 = "RegCreateKeyExW";
  }
  v13 = WfpReportSysErrorAsWinError(v11, v16, v10);
  v12 = v13;
  if ( v13 )
    WfpReportError(v13, "BfeRegCreateKey");
LABEL_9:
  if ( v3 )
    RegCloseKey(v3);
  if ( v12 )
    WfpReportError(v12, "BfeDbOpenType");
  return v12;
}

```

## disassembly

```asm
0x1800050bc  push    rbx
0x1800050be  push    rbp
0x1800050bf  push    rsi
0x1800050c0  push    rdi
0x1800050c1  push    r14
0x1800050c3  sub     rsp, 70h
0x1800050c7  mov     rax, cs:__security_cookie
0x1800050ce  xor     rax, rsp
0x1800050d1  mov     [rsp+98h+var_30], rax
0x1800050d6  xor     edi, edi
0x1800050d8  mov     r14, r8
0x1800050db  mov     [rsp+98h+var_38], rdi
0x1800050e0  mov     ebp, edx
0x1800050e2  mov     rsi, rcx
0x1800050e5  test    rcx, rcx
0x1800050e8  jz      loc_1800051C5
0x1800050ee  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800050f4  call    cs:__imp_TlsGetValue
0x1800050fa  test    rax, rax
0x1800050fd  jz      loc_1800051BE
0x180005103  mov     rbx, [rax+10h]
0x180005107  mov     ecx, ebp
0x180005109  call    BfeObjectTypeIdToString
0x18000510e  xor     r9d, r9d; lpClass
0x180005111  mov     [rsp+98h+var_38], 0
0x18000511a  xor     r8d, r8d; Reserved
0x18000511d  mov     qword ptr [r14], 0
0x180005124  lea     rcx, [rsp+98h+var_38]
0x180005129  mov     rdx, rax; lpSubKey
0x18000512c  test    rbx, rbx
0x18000512f  jz      loc_1800051E4
0x180005135  mov     [rsp+98h+pExtendedParemeter], r8; pExtendedParemeter
0x18000513a  mov     [rsp+98h+hTransaction], rbx; hTransaction
0x18000513f  mov     [rsp+98h+lpdwDisposition], r8; lpdwDisposition
0x180005144  mov     [rsp+98h+phkResult], rcx; phkResult
0x180005149  mov     rcx, rsi; hKey
0x18000514c  mov     [rsp+98h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180005151  mov     [rsp+98h+samDesired], 3; samDesired
0x180005159  mov     [rsp+98h+dwOptions], r8d; dwOptions
0x18000515e  call    cs:__imp_RegCreateKeyTransactedW
0x180005164  test    eax, eax
0x180005166  jnz     loc_180005228
0x18000516c  mov     rax, [rsp+98h+var_38]
0x180005171  xor     ebx, ebx
0x180005173  mov     [r14], rax
0x180005176  jmp     short loc_18000518C
0x180005178  mov     r8d, eax
0x18000517b  call    WfpReportSysErrorAsWinError
0x180005180  mov     rbx, rax
0x180005183  test    rax, rax
0x180005186  jnz     loc_180005234
0x18000518c  test    rdi, rdi
0x18000518f  jz      short loc_18000519A
0x180005191  mov     rcx, rdi; hKey
0x180005194  call    cs:__imp_RegCloseKey
0x18000519a  test    rbx, rbx
0x18000519d  jnz     loc_180005248
0x1800051a3  mov     rax, rbx
0x1800051a6  mov     rcx, [rsp+98h+var_30]
0x1800051ab  xor     rcx, rsp; StackCookie
0x1800051ae  call    __security_check_cookie
0x1800051b3  add     rsp, 70h
0x1800051b7  pop     r14
0x1800051b9  pop     rdi
0x1800051ba  pop     rsi
0x1800051bb  pop     rbp
0x1800051bc  pop     rbx
0x1800051bd  retn
0x1800051be  xor     ebx, ebx
0x1800051c0  jmp     loc_180005107
0x1800051c5  lea     rcx, [rsp+98h+var_38]
0x1800051ca  call    BfeDbOpen
0x1800051cf  mov     rdi, [rsp+98h+var_38]
0x1800051d4  mov     rbx, rax
0x1800051d7  test    rax, rax
0x1800051da  jnz     short loc_18000518C
0x1800051dc  mov     rsi, rdi
0x1800051df  jmp     loc_1800050EE
0x1800051e4  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x1800051ed  mov     [rsp+98h+phkResult], rcx; phkResult
0x1800051f2  mov     rcx, rsi; hKey
0x1800051f5  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800051fe  mov     [rsp+98h+samDesired], 3; samDesired
0x180005206  mov     [rsp+98h+dwOptions], 0; dwOptions
0x18000520e  call    cs:__imp_RegCreateKeyExW
0x180005214  test    eax, eax
0x180005216  jz      loc_18000516C
0x18000521c  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x180005223  jmp     loc_180005178
0x180005228  lea     rdx, aRegcreatekeytr_0; "RegCreateKeyTransactedW"
0x18000522f  jmp     loc_180005178
0x180005234  lea     rdx, aBferegcreateke; "BfeRegCreateKey"
0x18000523b  mov     rcx, rbx
0x18000523e  call    WfpReportError
0x180005243  jmp     loc_18000518C
0x180005248  lea     rdx, aBfedbopentype; "BfeDbOpenType"
0x18000524f  mov     rcx, rbx
0x180005252  call    WfpReportError
0x180005257  jmp     loc_1800051A3
```
