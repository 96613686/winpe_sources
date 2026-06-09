# BfeRegSetBinary

- ea: `0x180034ab0`
- end: `0x180034b77`
- name: `BfeRegSetBinary`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800349f8`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180034ab0`
- `0x18003512c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034aea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034b02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034b02`

## string_xrefs

- `0x180034b55`: `RegSetValueExW`
- `0x180034b66`: `BfeRegSetBinary`

## pseudocode

```c
__int64 __fastcall BfeRegSetBinary(HKEY a1, const WCHAR *a2, const WCHAR *a3, DWORD a4, BYTE *lpData, void *a6)
{
  HKEY v6; // rbx
  __int64 v7; // rdi
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v13; // rax
  HKEY v14; // [rsp+68h] [rbp+10h] BYREF

  v6 = 0;
  v7 = 0;
  v14 = 0;
  if ( a2 )
  {
    v13 = BfeRegCreateKey(a1, a2, 2u, a6, &v14);
    v6 = v14;
    v7 = v13;
    if ( v13 )
      goto LABEL_4;
    a1 = v14;
  }
  v10 = RegSetValueExW(a1, a3, 0, 3u, lpData, a4);
  if ( v10 )
    v7 = WfpReportSysErrorAsWinError(v11, "RegSetValueExW", v10);
LABEL_4:
  if ( v6 )
    RegCloseKey(v6);
  if ( v7 )
    WfpReportError(v7, "BfeRegSetBinary");
  return v7;
}

```

## disassembly

```asm
0x180034ab0  push    rbx
0x180034ab2  push    rbp
0x180034ab3  push    rsi
0x180034ab4  push    rdi
0x180034ab5  sub     rsp, 38h
0x180034ab9  xor     ebx, ebx
0x180034abb  xor     edi, edi
0x180034abd  mov     [rsp+58h+arg_8], rbx
0x180034ac2  mov     esi, r9d
0x180034ac5  mov     rbp, r8
0x180034ac8  test    rdx, rdx
0x180034acb  jnz     short loc_180034B20
0x180034acd  mov     rax, [rsp+58h+arg_20]
0x180034ad5  mov     r9d, 3; dwType
0x180034adb  mov     [rsp+58h+cbData], esi; cbData
0x180034adf  xor     r8d, r8d; Reserved
0x180034ae2  mov     rdx, rbp; lpValueName
0x180034ae5  mov     [rsp+58h+lpData], rax; lpData
0x180034aea  call    cs:__imp_RegSetValueExW
0x180034af1  nop     dword ptr [rax+rax+00h]
0x180034af6  test    eax, eax
0x180034af8  jnz     short loc_180034B52
0x180034afa  test    rbx, rbx
0x180034afd  jz      short loc_180034B0E
0x180034aff  mov     rcx, rbx; hKey
0x180034b02  call    cs:__imp_RegCloseKey
0x180034b09  nop     dword ptr [rax+rax+00h]
0x180034b0e  test    rdi, rdi
0x180034b11  jnz     short loc_180034B66
0x180034b13  mov     rax, rdi
0x180034b16  add     rsp, 38h
0x180034b1a  pop     rdi
0x180034b1b  pop     rsi
0x180034b1c  pop     rbp
0x180034b1d  pop     rbx
0x180034b1e  retn
0x180034b20  mov     r9, [rsp+58h+arg_28]
0x180034b28  lea     rax, [rsp+58h+arg_8]
0x180034b2d  mov     r8d, 2
0x180034b33  mov     [rsp+58h+lpData], rax
0x180034b38  call    BfeRegCreateKey
0x180034b3d  mov     rbx, [rsp+58h+arg_8]
0x180034b42  mov     rdi, rax
0x180034b45  test    rax, rax
0x180034b48  jnz     short loc_180034AFA
0x180034b4a  mov     rcx, rbx
0x180034b4d  jmp     loc_180034ACD
0x180034b52  mov     r8d, eax
0x180034b55  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180034b5c  call    WfpReportSysErrorAsWinError
0x180034b61  mov     rdi, rax
0x180034b64  jmp     short loc_180034AFA
0x180034b66  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x180034b6d  mov     rcx, rdi
0x180034b70  call    WfpReportError
0x180034b75  jmp     short loc_180034B13
```
