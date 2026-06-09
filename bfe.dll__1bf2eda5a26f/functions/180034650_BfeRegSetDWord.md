# BfeRegSetDWord

- ea: `0x180034650`
- end: `0x180034715`
- name: `BfeRegSetDWord`
- size: `197`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004c910`
- `0x1800656b0`
- `0x180065808`
- `0x1800674b0`
- `0x180068574`
- `0x180068980`

## callees

- `0x1800039e4`
- `0x18001236c`
- `0x180018b74`
- `0x180034650`
- `0x180035250`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346c5`

## string_xrefs

- `0x1800346d2`: `RegSetValueExW`
- `0x1800346ee`: `BfeRegSetDWord`

## pseudocode

```c
__int64 __fastcall BfeRegSetDWord(__int64 a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  int Data; // [rsp+38h] [rbp-30h] BYREF

  v4 = 0;
  Data = a4;
  v12 = 0;
  v6 = -2147483646;
  if ( a2 )
  {
    v7 = BfeRegCreateKey(HKEY_LOCAL_MACHINE, a2, 2u, 0, &v12);
    v4 = v12;
    v8 = v7;
    if ( v7 )
      goto LABEL_7;
    v6 = v12;
  }
  else
  {
    v8 = 0;
  }
  v9 = RegSetValueExW((HKEY)v6, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v9 )
    v8 = WfpReportSysErrorAsWinError(v10, "RegSetValueExW", v9);
LABEL_7:
  BfeRegCloseKey(v4);
  if ( v8 )
    WfpReportError(v8, "BfeRegSetDWord");
  return v8;
}

```

## disassembly

```asm
0x180034650  mov     r11, rsp
0x180034653  push    rbx
0x180034654  push    rsi
0x180034655  push    rdi
0x180034656  sub     rsp, 50h
0x18003465a  mov     rax, cs:__security_cookie
0x180034661  xor     rax, rsp
0x180034664  mov     [rsp+68h+var_28], rax
0x180034669  xor     edi, edi
0x18003466b  mov     [r11-30h], r9d
0x18003466f  mov     [r11-38h], rdi
0x180034673  mov     rsi, r8
0x180034676  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003467d  test    rdx, rdx
0x180034680  jz      short loc_1800346A8
0x180034682  lea     rax, [r11-38h]
0x180034686  xor     r9d, r9d
0x180034689  lea     r8d, [rdi+2]
0x18003468d  mov     [r11-48h], rax
0x180034691  call    BfeRegCreateKey
0x180034696  mov     rdi, [rsp+68h+var_38]
0x18003469b  mov     rbx, rax
0x18003469e  test    rax, rax
0x1800346a1  jnz     short loc_1800346E1
0x1800346a3  mov     rcx, rdi
0x1800346a6  jmp     short loc_1800346AA
0x1800346a8  xor     ebx, ebx
0x1800346aa  mov     r9d, 4; dwType
0x1800346b0  lea     rax, [rsp+68h+Data]
0x1800346b5  mov     [rsp+68h+cbData], r9d; cbData
0x1800346ba  xor     r8d, r8d; Reserved
0x1800346bd  mov     rdx, rsi; lpValueName
0x1800346c0  mov     [rsp+68h+lpData], rax; lpData
0x1800346c5  call    cs:__imp_RegSetValueExW
0x1800346cb  test    eax, eax
0x1800346cd  jz      short loc_1800346E1
0x1800346cf  mov     r8d, eax
0x1800346d2  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x1800346d9  call    WfpReportSysErrorAsWinError
0x1800346de  mov     rbx, rax
0x1800346e1  mov     rcx, rdi
0x1800346e4  call    BfeRegCloseKey
0x1800346e9  test    rbx, rbx
0x1800346ec  jz      short loc_1800346FD
0x1800346ee  lea     rdx, aBferegsetdword; "BfeRegSetDWord"
0x1800346f5  mov     rcx, rbx
0x1800346f8  call    WfpReportError
0x1800346fd  mov     rax, rbx
0x180034700  mov     rcx, [rsp+68h+var_28]
0x180034705  xor     rcx, rsp; StackCookie
0x180034708  call    __security_check_cookie
0x18003470d  add     rsp, 50h
0x180034711  pop     rdi
0x180034712  pop     rsi
0x180034713  pop     rbx
0x180034714  retn
```
