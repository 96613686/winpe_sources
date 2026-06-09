# winFullPathnameNoMutex

- ea: `0x1800a2e3c`
- end: `0x1800a2ff5`
- name: `winFullPathnameNoMutex`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a2de0`

## callees

- `0x180012470`
- `0x1800293d4`
- `0x1800299bc`
- `0x18003f650`
- `0x180041688`
- `0x1800a2e3c`
- `0x1800a33dc`
- `0x1800a4470`
- `0x1800a8010`

## string_xrefs

- `0x1800a2f15`: `winFullPathname1`
- `0x1800a2f9a`: `winFullPathname2`

## pseudocode

```c
__int64 __fastcall winFullPathnameNoMutex(__int64 a1, _BYTE *a2, int a3, __int64 a4)
{
  char v5; // r8
  _BYTE *v7; // rbx
  _BYTE *v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rdi
  int v14; // eax
  DWORD v15; // eax
  unsigned int v16; // ebp
  __int64 v17; // rsi
  DWORD v18; // eax
  __int64 v19; // rbx
  __int64 v20; // rcx

  v5 = 92;
  v7 = a2;
  if ( *a2 == 47
    && ((unsigned int)winIsDriveLetterAndColon(a2 + 1) || *v9 == v5 && v9[1] == v5 && v9[2] == 63 && v9[3] == v5) )
  {
    v7 = v9;
  }
  if ( sqlite3_data_directory && *v7 != 47 && *v7 != v5 && !(unsigned int)winIsDriveLetterAndColon(v7) )
  {
    v10 = *(unsigned int *)(a1 + 8);
    if ( a3 < (int)v10 )
      v10 = (unsigned int)a3;
    sqlite3_snprintf(v10, a4, "%s%c%s");
    return 0;
  }
  v12 = winUtf8ToUnicode(v7);
  v13 = v12;
  if ( !v12 )
    return 3082;
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))off_1800C40B0)(v12, 0, 0, 0);
  if ( v14 )
  {
    v16 = v14 + 3;
    v17 = sqlite3MallocZero(2LL * (unsigned int)(v14 + 3));
    if ( v17 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))off_1800C40B0)(v13, v16, v17, 0) )
      {
        sqlite3_free(v13);
        sqlite3_free(v17);
        v18 = off_1800C40C8();
        return winLogErrorAtLine(782, v18, (unsigned int)"winFullPathname2", (_DWORD)v7, 52385);
      }
      sqlite3_free(v13);
      v19 = winUnicodeToUtf8(v17);
      sqlite3_free(v17);
      if ( v19 )
      {
        v20 = *(unsigned int *)(a1 + 8);
        if ( a3 < (int)v20 )
          v20 = (unsigned int)a3;
        sqlite3_snprintf(v20, a4, "%s", v19);
        sqlite3_free(v19);
        return 0;
      }
    }
    else
    {
      sqlite3_free(v13);
    }
    return 3082;
  }
  sqlite3_free(v13);
  v15 = off_1800C40C8();
  return winLogErrorAtLine(782, v15, (unsigned int)"winFullPathname1", (_DWORD)v7, 52372);
}

```

## disassembly

```asm
0x1800a2e3c  push    rbx
0x1800a2e3e  push    rbp
0x1800a2e3f  push    rsi
0x1800a2e40  push    rdi
0x1800a2e41  push    r13
0x1800a2e43  push    r14
0x1800a2e45  push    r15
0x1800a2e47  sub     rsp, 30h
0x1800a2e4b  cmp     byte ptr [rdx], 2Fh ; '/'
0x1800a2e4e  mov     r14d, r8d
0x1800a2e51  mov     r8d, 5Ch ; '\'
0x1800a2e57  mov     r15, r9
0x1800a2e5a  mov     rbx, rdx
0x1800a2e5d  mov     r13, rcx
0x1800a2e60  jnz     short loc_1800A2E89
0x1800a2e62  lea     rcx, [rdx+1]
0x1800a2e66  call    winIsDriveLetterAndColon
0x1800a2e6b  test    eax, eax
0x1800a2e6d  jnz     short loc_1800A2E86
0x1800a2e6f  cmp     [rcx], r8b
0x1800a2e72  jnz     short loc_1800A2E89
0x1800a2e74  cmp     [rcx+1], r8b
0x1800a2e78  jnz     short loc_1800A2E89
0x1800a2e7a  cmp     byte ptr [rcx+2], 3Fh ; '?'
0x1800a2e7e  jnz     short loc_1800A2E89
0x1800a2e80  cmp     [rcx+3], r8b
0x1800a2e84  jnz     short loc_1800A2E89
0x1800a2e86  mov     rbx, rcx
0x1800a2e89  mov     r9, cs:sqlite3_data_directory
0x1800a2e90  test    r9, r9
0x1800a2e93  jz      short loc_1800A2ED6
0x1800a2e95  cmp     byte ptr [rbx], 2Fh ; '/'
0x1800a2e98  jz      short loc_1800A2ED6
0x1800a2e9a  cmp     [rbx], r8b
0x1800a2e9d  jz      short loc_1800A2ED6
0x1800a2e9f  mov     rcx, rbx
0x1800a2ea2  call    winIsDriveLetterAndColon
0x1800a2ea7  test    eax, eax
0x1800a2ea9  jnz     short loc_1800A2ED6
0x1800a2eab  mov     ecx, [r13+8]
0x1800a2eaf  mov     rdx, r15
0x1800a2eb2  cmp     r14d, ecx
0x1800a2eb5  mov     [rsp+68h+var_40], rbx
0x1800a2eba  mov     [rsp+68h+var_48], r8d
0x1800a2ebf  lea     r8, aSCS; "%s%c%s"
0x1800a2ec6  cmovl   ecx, r14d
0x1800a2eca  call    sqlite3_snprintf
0x1800a2ecf  xor     eax, eax
0x1800a2ed1  jmp     loc_1800A2F57
0x1800a2ed6  mov     rcx, rbx
0x1800a2ed9  call    winUtf8ToUnicode
0x1800a2ede  mov     rdi, rax
0x1800a2ee1  test    rax, rax
0x1800a2ee4  jz      short loc_1800A2F52
0x1800a2ee6  mov     rcx, rax
0x1800a2ee9  xor     r9d, r9d
0x1800a2eec  mov     rax, cs:off_1800C40B0
0x1800a2ef3  xor     r8d, r8d
0x1800a2ef6  xor     edx, edx
0x1800a2ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2efd  test    eax, eax
0x1800a2eff  jnz     short loc_1800A2F35
0x1800a2f01  mov     rcx, rdi
0x1800a2f04  call    sqlite3_free
0x1800a2f09  mov     rax, cs:off_1800C40C8
0x1800a2f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f15  lea     r8, aWinfullpathnam; "winFullPathname1"
0x1800a2f1c  mov     [rsp+68h+var_48], 0CC94h
0x1800a2f24  mov     r9, rbx
0x1800a2f27  mov     edx, eax
0x1800a2f29  mov     ecx, 30Eh
0x1800a2f2e  call    winLogErrorAtLine
0x1800a2f33  jmp     short loc_1800A2F57
0x1800a2f35  lea     ebp, [rax+3]
0x1800a2f38  mov     ecx, ebp
0x1800a2f3a  add     rcx, rcx; Size
0x1800a2f3d  call    sqlite3MallocZero
0x1800a2f42  mov     rsi, rax
0x1800a2f45  mov     rcx, rdi
0x1800a2f48  test    rax, rax
0x1800a2f4b  jnz     short loc_1800A2F66
0x1800a2f4d  call    sqlite3_free
0x1800a2f52  mov     eax, 0C0Ah
0x1800a2f57  add     rsp, 30h
0x1800a2f5b  pop     r15
0x1800a2f5d  pop     r14
0x1800a2f5f  pop     r13
0x1800a2f61  pop     rdi
0x1800a2f62  pop     rsi
0x1800a2f63  pop     rbp
0x1800a2f64  pop     rbx
0x1800a2f65  retn
0x1800a2f66  mov     rax, cs:off_1800C40B0
0x1800a2f6d  xor     r9d, r9d
0x1800a2f70  mov     r8, rsi
0x1800a2f73  mov     edx, ebp
0x1800a2f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f7a  mov     rcx, rdi
0x1800a2f7d  test    eax, eax
0x1800a2f7f  jnz     short loc_1800A2FAE
0x1800a2f81  call    sqlite3_free
0x1800a2f86  mov     rcx, rsi
0x1800a2f89  call    sqlite3_free
0x1800a2f8e  mov     rax, cs:off_1800C40C8
0x1800a2f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f9a  lea     r8, aWinfullpathnam_0; "winFullPathname2"
0x1800a2fa1  mov     [rsp+68h+var_48], 0CCA1h
0x1800a2fa9  jmp     loc_1800A2F24
0x1800a2fae  call    sqlite3_free
0x1800a2fb3  mov     rcx, rsi
0x1800a2fb6  call    winUnicodeToUtf8
0x1800a2fbb  mov     rcx, rsi
0x1800a2fbe  mov     rbx, rax
0x1800a2fc1  call    sqlite3_free
0x1800a2fc6  test    rbx, rbx
0x1800a2fc9  jz      short loc_1800A2F52
0x1800a2fcb  mov     ecx, [r13+8]
0x1800a2fcf  lea     r8, aS_10; "%s"
0x1800a2fd6  cmp     r14d, ecx
0x1800a2fd9  mov     r9, rbx
0x1800a2fdc  mov     rdx, r15
0x1800a2fdf  cmovl   ecx, r14d
0x1800a2fe3  call    sqlite3_snprintf
0x1800a2fe8  mov     rcx, rbx
0x1800a2feb  call    sqlite3_free
0x1800a2ff0  jmp     loc_1800A2ECF
```
