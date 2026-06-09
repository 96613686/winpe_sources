# BfeRegOpenKey

- ea: `0x1800304c4`
- end: `0x1800305a4`
- name: `BfeRegOpenKey`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800302f4`
- `0x180057c0c`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800304c4`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030566`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180030521`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180030521`

## string_xrefs

- `0x180030573`: `RegOpenKeyExW`
- `0x18003059b`: `RegOpenKeyTransactedW`
- `0x18003058a`: `BfeRegOpenKey`

## pseudocode

```c
__int64 __fastcall BfeRegOpenKey(HKEY a1, const WCHAR *a2, REGSAM a3, void *a4, _QWORD *a5, _DWORD *a6)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rbx
  const char *v10; // rdx
  __int64 v11; // rax
  HKEY phkResult; // [rsp+40h] [rbp-28h] BYREF

  phkResult = 0;
  *a5 = 0;
  *a6 = 0;
  if ( a4 )
  {
    v6 = RegOpenKeyTransactedW(a1, a2, 0, a3, &phkResult, a4, 0);
    if ( (v6 & 0xFFFFFFFD) == 0 )
      goto LABEL_3;
    v10 = "RegOpenKeyTransactedW";
  }
  else
  {
    v6 = RegOpenKeyExW(a1, a2, 0, a3, &phkResult);
    if ( (v6 & 0xFFFFFFFD) == 0 )
    {
LABEL_3:
      v8 = 0;
      if ( v6 != 2 )
      {
        *a5 = phkResult;
        *a6 = 1;
      }
      return v8;
    }
    v10 = "RegOpenKeyExW";
  }
  v11 = WfpReportSysErrorAsWinError(v7, v10, v6);
  v8 = v11;
  if ( v11 )
    WfpReportError(v11, "BfeRegOpenKey");
  return v8;
}

```

## disassembly

```asm
0x1800304c4  mov     r11, rsp
0x1800304c7  push    rbx
0x1800304c8  push    rsi
0x1800304c9  push    rdi
0x1800304ca  sub     rsp, 50h
0x1800304ce  mov     rax, cs:__security_cookie
0x1800304d5  xor     rax, rsp
0x1800304d8  mov     [rsp+68h+var_20], rax
0x1800304dd  mov     rdi, [rsp+68h+arg_20]
0x1800304e5  lea     rax, [r11-28h]
0x1800304e9  mov     rsi, [rsp+68h+arg_28]
0x1800304f1  mov     qword ptr [r11-28h], 0
0x1800304f9  mov     qword ptr [rdi], 0
0x180030500  mov     dword ptr [rsi], 0
0x180030506  test    r9, r9
0x180030509  jz      short loc_18003055B
0x18003050b  mov     qword ptr [r11-38h], 0
0x180030513  mov     [r11-40h], r9
0x180030517  mov     r9d, r8d; samDesired
0x18003051a  xor     r8d, r8d; ulOptions
0x18003051d  mov     [r11-48h], rax
0x180030521  call    cs:__imp_RegOpenKeyTransactedW
0x180030527  test    eax, 0FFFFFFFDh
0x18003052c  jnz     short loc_18003059B
0x18003052e  xor     ebx, ebx
0x180030530  cmp     eax, 2
0x180030533  jz      short loc_180030543
0x180030535  mov     rax, [rsp+68h+var_28]
0x18003053a  mov     [rdi], rax
0x18003053d  mov     dword ptr [rsi], 1
0x180030543  mov     rax, rbx
0x180030546  mov     rcx, [rsp+68h+var_20]
0x18003054b  xor     rcx, rsp; StackCookie
0x18003054e  call    __security_check_cookie
0x180030553  add     rsp, 50h
0x180030557  pop     rdi
0x180030558  pop     rsi
0x180030559  pop     rbx
0x18003055a  retn
0x18003055b  mov     r9d, r8d; samDesired
0x18003055e  mov     [rsp+68h+phkResult], rax; phkResult
0x180030563  xor     r8d, r8d; ulOptions
0x180030566  call    cs:__imp_RegOpenKeyExW
0x18003056c  test    eax, 0FFFFFFFDh
0x180030571  jz      short loc_18003052E
0x180030573  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18003057a  mov     r8d, eax
0x18003057d  call    WfpReportSysErrorAsWinError
0x180030582  mov     rbx, rax
0x180030585  test    rax, rax
0x180030588  jz      short loc_180030543
0x18003058a  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180030591  mov     rcx, rax
0x180030594  call    WfpReportError
0x180030599  jmp     short loc_180030543
0x18003059b  lea     rdx, aRegopenkeytran_1; "RegOpenKeyTransactedW"
0x1800305a2  jmp     short loc_18003057A
```
