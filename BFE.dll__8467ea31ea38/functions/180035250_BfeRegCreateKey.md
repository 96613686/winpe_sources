# BfeRegCreateKey

- ea: `0x180035250`
- end: `0x18003534a`
- name: `BfeRegCreateKey`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180034650`
- `0x18003471c`
- `0x180034b90`
- `0x180034e04`
- `0x180034e5c`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180035250`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003530f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003530f`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800352ba`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800352ba`

## string_xrefs

- `0x180035341`: `RegCreateKeyTransactedW`
- `0x180035330`: `BfeRegCreateKey`
- `0x180035319`: `RegCreateKeyExW`

## pseudocode

```c
__int64 __fastcall BfeRegCreateKey(HKEY a1, const WCHAR *a2, REGSAM samDesired, void *a4, _QWORD *a5)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  const char *v9; // rdx
  __int64 v10; // rax
  HKEY phkResult; // [rsp+60h] [rbp-28h] BYREF

  phkResult = 0;
  *a5 = 0;
  if ( a4 )
  {
    v5 = RegCreateKeyTransactedW(a1, a2, 0, 0, 0, samDesired, 0, &phkResult, 0, a4, 0);
    if ( !v5 )
    {
LABEL_3:
      v7 = 0;
      *a5 = phkResult;
      return v7;
    }
    v9 = "RegCreateKeyTransactedW";
  }
  else
  {
    v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, samDesired, 0, &phkResult, 0);
    if ( !v5 )
      goto LABEL_3;
    v9 = "RegCreateKeyExW";
  }
  v10 = WfpReportSysErrorAsWinError(v6, v9, v5);
  v7 = v10;
  if ( v10 )
    WfpReportError(v10, "BfeRegCreateKey");
  return v7;
}

```

## disassembly

```asm
0x180035250  mov     r11, rsp
0x180035253  push    rbx
0x180035254  push    rdi
0x180035255  sub     rsp, 78h
0x180035259  mov     rax, cs:__security_cookie
0x180035260  xor     rax, rsp
0x180035263  mov     [rsp+88h+var_20], rax
0x180035268  mov     rdi, [rsp+88h+arg_20]
0x180035270  lea     rax, [r11-28h]
0x180035274  mov     qword ptr [r11-28h], 0
0x18003527c  mov     qword ptr [rdi], 0
0x180035283  test    r9, r9
0x180035286  jz      short loc_1800352E5
0x180035288  mov     qword ptr [r11-38h], 0
0x180035290  mov     [r11-40h], r9
0x180035294  xor     r9d, r9d; lpClass
0x180035297  mov     qword ptr [r11-48h], 0
0x18003529f  mov     [r11-50h], rax
0x1800352a3  mov     qword ptr [r11-58h], 0
0x1800352ab  mov     [r11-60h], r8d
0x1800352af  xor     r8d, r8d; Reserved
0x1800352b2  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800352ba  call    cs:__imp_RegCreateKeyTransactedW
0x1800352c0  test    eax, eax
0x1800352c2  jnz     short loc_180035341
0x1800352c4  mov     rax, [rsp+88h+var_28]
0x1800352c9  xor     ebx, ebx
0x1800352cb  mov     [rdi], rax
0x1800352ce  mov     rax, rbx
0x1800352d1  mov     rcx, [rsp+88h+var_20]
0x1800352d6  xor     rcx, rsp; StackCookie
0x1800352d9  call    __security_check_cookie
0x1800352de  add     rsp, 78h
0x1800352e2  pop     rdi
0x1800352e3  pop     rbx
0x1800352e4  retn
0x1800352e5  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800352ee  xor     r9d, r9d; lpClass
0x1800352f1  mov     [rsp+88h+phkResult], rax; phkResult
0x1800352f6  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800352ff  mov     [rsp+88h+samDesired], r8d; samDesired
0x180035304  xor     r8d, r8d; Reserved
0x180035307  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18003530f  call    cs:__imp_RegCreateKeyExW
0x180035315  test    eax, eax
0x180035317  jz      short loc_1800352C4
0x180035319  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x180035320  mov     r8d, eax
0x180035323  call    WfpReportSysErrorAsWinError
0x180035328  mov     rbx, rax
0x18003532b  test    rax, rax
0x18003532e  jz      short loc_1800352CE
0x180035330  lea     rdx, aBferegcreateke; "BfeRegCreateKey"
0x180035337  mov     rcx, rax
0x18003533a  call    WfpReportError
0x18003533f  jmp     short loc_1800352CE
0x180035341  lea     rdx, aRegcreatekeytr_0; "RegCreateKeyTransactedW"
0x180035348  jmp     short loc_180035320
```
