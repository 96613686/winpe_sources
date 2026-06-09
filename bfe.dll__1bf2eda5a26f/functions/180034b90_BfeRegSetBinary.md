# BfeRegSetBinary

- ea: `0x180034b90`
- end: `0x180034c47`
- name: `BfeRegSetBinary`
- size: `183`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, DWORD, BYTE *lpData, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180034ae0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180034b90`
- `0x180035250`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034bca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034bca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034bdc`

## string_xrefs

- `0x180034c36`: `BfeRegSetBinary`
- `0x180034c25`: `RegSetValueExW`

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
0x180034b90  push    rbx
0x180034b92  push    rbp
0x180034b93  push    rsi
0x180034b94  push    rdi
0x180034b95  sub     rsp, 38h
0x180034b99  xor     ebx, ebx
0x180034b9b  xor     edi, edi
0x180034b9d  mov     [rsp+58h+arg_8], rbx
0x180034ba2  mov     esi, r9d
0x180034ba5  mov     rbp, r8
0x180034ba8  test    rdx, rdx
0x180034bab  jnz     short loc_180034BF3
0x180034bad  mov     rax, [rsp+58h+arg_20]
0x180034bb5  mov     r9d, 3; dwType
0x180034bbb  mov     [rsp+58h+cbData], esi; cbData
0x180034bbf  xor     r8d, r8d; Reserved
0x180034bc2  mov     rdx, rbp; lpValueName
0x180034bc5  mov     [rsp+58h+lpData], rax; lpData
0x180034bca  call    cs:__imp_RegSetValueExW
0x180034bd0  test    eax, eax
0x180034bd2  jnz     short loc_180034C22
0x180034bd4  test    rbx, rbx
0x180034bd7  jz      short loc_180034BE2
0x180034bd9  mov     rcx, rbx; hKey
0x180034bdc  call    cs:__imp_RegCloseKey
0x180034be2  test    rdi, rdi
0x180034be5  jnz     short loc_180034C36
0x180034be7  mov     rax, rdi
0x180034bea  add     rsp, 38h
0x180034bee  pop     rdi
0x180034bef  pop     rsi
0x180034bf0  pop     rbp
0x180034bf1  pop     rbx
0x180034bf2  retn
0x180034bf3  mov     r9, [rsp+58h+arg_28]
0x180034bfb  lea     rax, [rsp+58h+arg_8]
0x180034c00  mov     r8d, 2
0x180034c06  mov     [rsp+58h+lpData], rax
0x180034c0b  call    BfeRegCreateKey
0x180034c10  mov     rbx, [rsp+58h+arg_8]
0x180034c15  mov     rdi, rax
0x180034c18  test    rax, rax
0x180034c1b  jnz     short loc_180034BD4
0x180034c1d  mov     rcx, rbx
0x180034c20  jmp     short loc_180034BAD
0x180034c22  mov     r8d, eax
0x180034c25  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180034c2c  call    WfpReportSysErrorAsWinError
0x180034c31  mov     rdi, rax
0x180034c34  jmp     short loc_180034BD4
0x180034c36  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x180034c3d  mov     rcx, rdi
0x180034c40  call    WfpReportError
0x180034c45  jmp     short loc_180034BE7
```
