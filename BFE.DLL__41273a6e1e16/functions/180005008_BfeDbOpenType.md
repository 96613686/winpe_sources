# BfeDbOpenType

- ea: `0x180005008`
- end: `0x1800051a5`
- name: `BfeDbOpenType`
- size: `413`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004f04`
- `0x18001ead0`
- `0x180068614`

## callees

- `0x180005008`
- `0x1800051f4`
- `0x180005238`
- `0x180012d8c`
- `0x1800197d0`
- `0x180034d48`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005151`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050d7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000509b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000509b`

## string_xrefs

- `0x180005191`: `BfeDbOpenType`
- `0x180005165`: `RegCreateKeyExW`
- `0x180005171`: `RegCreateKeyTransactedW`
- `0x18000517d`: `BfeRegCreateKey`

## pseudocode

```c
__int64 __fastcall BfeDbOpenType(HKEY hKey, unsigned int a2, HKEY *a3)
{
  HKEY v3; // rdi
  HKEY v6; // rbx
  void *hTransaction; // rbp
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v14; // rax
  const char *v15; // rdx
  HKEY phkResult; // [rsp+60h] [rbp-38h] BYREF

  v3 = 0;
  phkResult = 0;
  v6 = hKey;
  if ( !hKey )
  {
    v14 = BfeDbOpen(&phkResult);
    v3 = phkResult;
    v11 = v14;
    if ( v14 )
      goto LABEL_7;
    v6 = phkResult;
  }
  hTransaction = (void *)BfeCallGetSysTxn();
  v8 = (const WCHAR *)BfeObjectTypeIdToString(a2);
  phkResult = 0;
  *a3 = 0;
  if ( hTransaction )
  {
    v9 = RegCreateKeyTransactedW(v6, v8, 0, 0, 0, 3u, 0, &phkResult, 0, hTransaction, 0);
    if ( !v9 )
    {
LABEL_4:
      v11 = 0;
      *a3 = phkResult;
      goto LABEL_7;
    }
    v15 = "RegCreateKeyTransactedW";
  }
  else
  {
    v9 = RegCreateKeyExW(v6, v8, 0, 0, 0, 3u, 0, &phkResult, 0);
    if ( !v9 )
      goto LABEL_4;
    v15 = "RegCreateKeyExW";
  }
  v12 = WfpReportSysErrorAsWinError(v10, v15, v9);
  v11 = v12;
  if ( v12 )
    WfpReportError(v12, "BfeRegCreateKey");
LABEL_7:
  if ( v3 )
    RegCloseKey(v3);
  if ( v11 )
    WfpReportError(v11, "BfeDbOpenType");
  return v11;
}

```

## disassembly

```asm
0x180005008  push    rbx
0x18000500a  push    rbp
0x18000500b  push    rsi
0x18000500c  push    rdi
0x18000500d  push    r14
0x18000500f  sub     rsp, 70h
0x180005013  mov     rax, cs:__security_cookie
0x18000501a  xor     rax, rsp
0x18000501d  mov     [rsp+98h+var_30], rax
0x180005022  xor     edi, edi
0x180005024  mov     rsi, r8
0x180005027  mov     [rsp+98h+var_38], rdi
0x18000502c  mov     r14d, edx
0x18000502f  mov     rbx, rcx
0x180005032  test    rcx, rcx
0x180005035  jz      loc_180005108
0x18000503b  call    BfeCallGetSysTxn
0x180005040  mov     ecx, r14d
0x180005043  mov     rbp, rax
0x180005046  call    BfeObjectTypeIdToString
0x18000504b  xor     r9d, r9d; lpClass
0x18000504e  mov     [rsp+98h+var_38], 0
0x180005057  xor     r8d, r8d; Reserved
0x18000505a  mov     qword ptr [rsi], 0
0x180005061  lea     rcx, [rsp+98h+var_38]
0x180005066  mov     rdx, rax; lpSubKey
0x180005069  test    rbp, rbp
0x18000506c  jz      loc_180005127
0x180005072  mov     [rsp+98h+pExtendedParemeter], r8; pExtendedParemeter
0x180005077  mov     [rsp+98h+hTransaction], rbp; hTransaction
0x18000507c  mov     [rsp+98h+lpdwDisposition], r8; lpdwDisposition
0x180005081  mov     [rsp+98h+phkResult], rcx; phkResult
0x180005086  mov     rcx, rbx; hKey
0x180005089  mov     [rsp+98h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18000508e  mov     [rsp+98h+samDesired], 3; samDesired
0x180005096  mov     [rsp+98h+dwOptions], r8d; dwOptions
0x18000509b  call    cs:__imp_RegCreateKeyTransactedW
0x1800050a2  nop     dword ptr [rax+rax+00h]
0x1800050a7  test    eax, eax
0x1800050a9  jnz     loc_180005171
0x1800050af  mov     rax, [rsp+98h+var_38]
0x1800050b4  xor     ebx, ebx
0x1800050b6  mov     [rsi], rax
0x1800050b9  jmp     short loc_1800050CF
0x1800050bb  mov     r8d, eax
0x1800050be  call    WfpReportSysErrorAsWinError
0x1800050c3  mov     rbx, rax
0x1800050c6  test    rax, rax
0x1800050c9  jnz     loc_18000517D
0x1800050cf  test    rdi, rdi
0x1800050d2  jz      short loc_1800050E3
0x1800050d4  mov     rcx, rdi; hKey
0x1800050d7  call    cs:__imp_RegCloseKey
0x1800050de  nop     dword ptr [rax+rax+00h]
0x1800050e3  test    rbx, rbx
0x1800050e6  jnz     loc_180005191
0x1800050ec  mov     rax, rbx
0x1800050ef  mov     rcx, [rsp+98h+var_30]
0x1800050f4  xor     rcx, rsp; StackCookie
0x1800050f7  call    __security_check_cookie
0x1800050fc  add     rsp, 70h
0x180005100  pop     r14
0x180005102  pop     rdi
0x180005103  pop     rsi
0x180005104  pop     rbp
0x180005105  pop     rbx
0x180005106  retn
0x180005108  lea     rcx, [rsp+98h+var_38]
0x18000510d  call    BfeDbOpen
0x180005112  mov     rdi, [rsp+98h+var_38]
0x180005117  mov     rbx, rax
0x18000511a  test    rax, rax
0x18000511d  jnz     short loc_1800050CF
0x18000511f  mov     rbx, rdi
0x180005122  jmp     loc_18000503B
0x180005127  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x180005130  mov     [rsp+98h+phkResult], rcx; phkResult
0x180005135  mov     rcx, rbx; hKey
0x180005138  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180005141  mov     [rsp+98h+samDesired], 3; samDesired
0x180005149  mov     [rsp+98h+dwOptions], 0; dwOptions
0x180005151  call    cs:__imp_RegCreateKeyExW
0x180005158  nop     dword ptr [rax+rax+00h]
0x18000515d  test    eax, eax
0x18000515f  jz      loc_1800050AF
0x180005165  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18000516c  jmp     loc_1800050BB
0x180005171  lea     rdx, aRegcreatekeytr_0; "RegCreateKeyTransactedW"
0x180005178  jmp     loc_1800050BB
0x18000517d  lea     rdx, aBferegcreateke; "BfeRegCreateKey"
0x180005184  mov     rcx, rbx
0x180005187  call    WfpReportError
0x18000518c  jmp     loc_1800050CF
0x180005191  lea     rdx, aBfedbopentype; "BfeDbOpenType"
0x180005198  mov     rcx, rbx
0x18000519b  call    WfpReportError
0x1800051a0  jmp     loc_1800050EC
```
