# BfeRegOpenKey

- ea: `0x180031df8`
- end: `0x180031ee5`
- name: `BfeRegOpenKey`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180031c1c`
- `0x180059b3c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180031df8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031ea1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031ea1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180031e55`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180031e55`

## string_xrefs

- `0x180031eb4`: `RegOpenKeyExW`
- `0x180031edc`: `RegOpenKeyTransactedW`
- `0x180031ecb`: `BfeRegOpenKey`

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
0x180031df8  mov     r11, rsp
0x180031dfb  push    rbx
0x180031dfc  push    rsi
0x180031dfd  push    rdi
0x180031dfe  sub     rsp, 50h
0x180031e02  mov     rax, cs:__security_cookie
0x180031e09  xor     rax, rsp
0x180031e0c  mov     [rsp+68h+var_20], rax
0x180031e11  mov     rdi, [rsp+68h+arg_20]
0x180031e19  lea     rax, [r11-28h]
0x180031e1d  mov     rsi, [rsp+68h+arg_28]
0x180031e25  mov     qword ptr [r11-28h], 0
0x180031e2d  mov     qword ptr [rdi], 0
0x180031e34  mov     dword ptr [rsi], 0
0x180031e3a  test    r9, r9
0x180031e3d  jz      short loc_180031E96
0x180031e3f  mov     qword ptr [r11-38h], 0
0x180031e47  mov     [r11-40h], r9
0x180031e4b  mov     r9d, r8d; samDesired
0x180031e4e  xor     r8d, r8d; ulOptions
0x180031e51  mov     [r11-48h], rax
0x180031e55  call    cs:__imp_RegOpenKeyTransactedW
0x180031e5c  nop     dword ptr [rax+rax+00h]
0x180031e61  test    eax, 0FFFFFFFDh
0x180031e66  jnz     short loc_180031EDC
0x180031e68  xor     ebx, ebx
0x180031e6a  cmp     eax, 2
0x180031e6d  jz      short loc_180031E7D
0x180031e6f  mov     rax, [rsp+68h+var_28]
0x180031e74  mov     [rdi], rax
0x180031e77  mov     dword ptr [rsi], 1
0x180031e7d  mov     rax, rbx
0x180031e80  mov     rcx, [rsp+68h+var_20]
0x180031e85  xor     rcx, rsp; StackCookie
0x180031e88  call    __security_check_cookie
0x180031e8d  add     rsp, 50h
0x180031e91  pop     rdi
0x180031e92  pop     rsi
0x180031e93  pop     rbx
0x180031e94  retn
0x180031e96  mov     r9d, r8d; samDesired
0x180031e99  mov     [rsp+68h+phkResult], rax; phkResult
0x180031e9e  xor     r8d, r8d; ulOptions
0x180031ea1  call    cs:__imp_RegOpenKeyExW
0x180031ea8  nop     dword ptr [rax+rax+00h]
0x180031ead  test    eax, 0FFFFFFFDh
0x180031eb2  jz      short loc_180031E68
0x180031eb4  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180031ebb  mov     r8d, eax
0x180031ebe  call    WfpReportSysErrorAsWinError
0x180031ec3  mov     rbx, rax
0x180031ec6  test    rax, rax
0x180031ec9  jz      short loc_180031E7D
0x180031ecb  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x180031ed2  mov     rcx, rax
0x180031ed5  call    WfpReportError
0x180031eda  jmp     short loc_180031E7D
0x180031edc  lea     rdx, aRegopenkeytran_1; "RegOpenKeyTransactedW"
0x180031ee3  jmp     short loc_180031EBB
```
