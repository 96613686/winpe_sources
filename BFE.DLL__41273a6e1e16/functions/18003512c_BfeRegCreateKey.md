# BfeRegCreateKey

- ea: `0x18003512c`
- end: `0x180035237`
- name: `BfeRegCreateKey`
- size: `267`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180034554`
- `0x180034628`
- `0x180034ab0`
- `0x180034d48`
- `0x180034da0`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18003512c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351f6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180035196`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180035196`

## string_xrefs

- `0x180035206`: `RegCreateKeyExW`
- `0x18003522e`: `RegCreateKeyTransactedW`
- `0x18003521d`: `BfeRegCreateKey`

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
0x18003512c  mov     r11, rsp
0x18003512f  push    rbx
0x180035130  push    rdi
0x180035131  sub     rsp, 78h
0x180035135  mov     rax, cs:__security_cookie
0x18003513c  xor     rax, rsp
0x18003513f  mov     [rsp+88h+var_20], rax
0x180035144  mov     rdi, [rsp+88h+arg_20]
0x18003514c  lea     rax, [r11-28h]
0x180035150  mov     qword ptr [r11-28h], 0
0x180035158  mov     qword ptr [rdi], 0
0x18003515f  test    r9, r9
0x180035162  jz      short loc_1800351CC
0x180035164  mov     qword ptr [r11-38h], 0
0x18003516c  mov     [r11-40h], r9
0x180035170  xor     r9d, r9d; lpClass
0x180035173  mov     qword ptr [r11-48h], 0
0x18003517b  mov     [r11-50h], rax
0x18003517f  mov     qword ptr [r11-58h], 0
0x180035187  mov     [r11-60h], r8d
0x18003518b  xor     r8d, r8d; Reserved
0x18003518e  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180035196  call    cs:__imp_RegCreateKeyTransactedW
0x18003519d  nop     dword ptr [rax+rax+00h]
0x1800351a2  test    eax, eax
0x1800351a4  jnz     loc_18003522E
0x1800351aa  mov     rax, [rsp+88h+var_28]
0x1800351af  xor     ebx, ebx
0x1800351b1  mov     [rdi], rax
0x1800351b4  mov     rax, rbx
0x1800351b7  mov     rcx, [rsp+88h+var_20]
0x1800351bc  xor     rcx, rsp; StackCookie
0x1800351bf  call    __security_check_cookie
0x1800351c4  add     rsp, 78h
0x1800351c8  pop     rdi
0x1800351c9  pop     rbx
0x1800351ca  retn
0x1800351cc  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800351d5  xor     r9d, r9d; lpClass
0x1800351d8  mov     [rsp+88h+phkResult], rax; phkResult
0x1800351dd  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800351e6  mov     [rsp+88h+samDesired], r8d; samDesired
0x1800351eb  xor     r8d, r8d; Reserved
0x1800351ee  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800351f6  call    cs:__imp_RegCreateKeyExW
0x1800351fd  nop     dword ptr [rax+rax+00h]
0x180035202  test    eax, eax
0x180035204  jz      short loc_1800351AA
0x180035206  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18003520d  mov     r8d, eax
0x180035210  call    WfpReportSysErrorAsWinError
0x180035215  mov     rbx, rax
0x180035218  test    rax, rax
0x18003521b  jz      short loc_1800351B4
0x18003521d  lea     rdx, aBferegcreateke; "BfeRegCreateKey"
0x180035224  mov     rcx, rax
0x180035227  call    WfpReportError
0x18003522c  jmp     short loc_1800351B4
0x18003522e  lea     rdx, aRegcreatekeytr_0; "RegCreateKeyTransactedW"
0x180035235  jmp     short loc_18003520D
```
