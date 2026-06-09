# winFullPathnameNoMutex

- ea: `0x1800649d8`
- end: `0x180064b91`
- name: `winFullPathnameNoMutex`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800968e0`

## callees

- `0x1800061e4`
- `0x18000aac0`
- `0x18000bd44`
- `0x18004e684`
- `0x180058b7c`
- `0x1800649d8`
- `0x180067b40`
- `0x180096cbc`
- `0x18009a010`

## string_xrefs

- `0x180064b36`: `winFullPathname2`
- `0x180064ab1`: `winFullPathname1`

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
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))off_1800B3060)(v12, 0, 0, 0);
  if ( v14 )
  {
    v16 = v14 + 3;
    v17 = sqlite3MallocZero(2LL * (unsigned int)(v14 + 3));
    if ( v17 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))off_1800B3060)(v13, v16, v17, 0) )
      {
        sqlite3_free(v13);
        sqlite3_free(v17);
        v18 = off_1800B3078();
        return winLogErrorAtLine(782, v18, (unsigned int)"winFullPathname2", (_DWORD)v7, 52481);
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
  v15 = off_1800B3078();
  return winLogErrorAtLine(782, v15, (unsigned int)"winFullPathname1", (_DWORD)v7, 52468);
}

```

## disassembly

```asm
0x1800649d8  push    rbx
0x1800649da  push    rbp
0x1800649db  push    rsi
0x1800649dc  push    rdi
0x1800649dd  push    r13
0x1800649df  push    r14
0x1800649e1  push    r15
0x1800649e3  sub     rsp, 30h
0x1800649e7  cmp     byte ptr [rdx], 2Fh ; '/'
0x1800649ea  mov     r14d, r8d
0x1800649ed  mov     r8d, 5Ch ; '\'
0x1800649f3  mov     r15, r9
0x1800649f6  mov     rbx, rdx
0x1800649f9  mov     r13, rcx
0x1800649fc  jnz     short loc_180064A25
0x1800649fe  lea     rcx, [rdx+1]
0x180064a02  call    winIsDriveLetterAndColon
0x180064a07  test    eax, eax
0x180064a09  jnz     short loc_180064A22
0x180064a0b  cmp     [rcx], r8b
0x180064a0e  jnz     short loc_180064A25
0x180064a10  cmp     [rcx+1], r8b
0x180064a14  jnz     short loc_180064A25
0x180064a16  cmp     byte ptr [rcx+2], 3Fh ; '?'
0x180064a1a  jnz     short loc_180064A25
0x180064a1c  cmp     [rcx+3], r8b
0x180064a20  jnz     short loc_180064A25
0x180064a22  mov     rbx, rcx
0x180064a25  mov     r9, cs:sqlite3_data_directory
0x180064a2c  test    r9, r9
0x180064a2f  jz      short loc_180064A72
0x180064a31  cmp     byte ptr [rbx], 2Fh ; '/'
0x180064a34  jz      short loc_180064A72
0x180064a36  cmp     [rbx], r8b
0x180064a39  jz      short loc_180064A72
0x180064a3b  mov     rcx, rbx
0x180064a3e  call    winIsDriveLetterAndColon
0x180064a43  test    eax, eax
0x180064a45  jnz     short loc_180064A72
0x180064a47  mov     ecx, [r13+8]
0x180064a4b  mov     rdx, r15
0x180064a4e  cmp     r14d, ecx
0x180064a51  mov     [rsp+68h+var_40], rbx
0x180064a56  mov     [rsp+68h+var_48], r8d
0x180064a5b  lea     r8, aSCS; "%s%c%s"
0x180064a62  cmovl   ecx, r14d
0x180064a66  call    sqlite3_snprintf
0x180064a6b  xor     eax, eax
0x180064a6d  jmp     loc_180064AF3
0x180064a72  mov     rcx, rbx
0x180064a75  call    winUtf8ToUnicode
0x180064a7a  mov     rdi, rax
0x180064a7d  test    rax, rax
0x180064a80  jz      short loc_180064AEE
0x180064a82  mov     rcx, rax
0x180064a85  xor     r9d, r9d
0x180064a88  mov     rax, cs:off_1800B3060
0x180064a8f  xor     r8d, r8d
0x180064a92  xor     edx, edx
0x180064a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a99  test    eax, eax
0x180064a9b  jnz     short loc_180064AD1
0x180064a9d  mov     rcx, rdi
0x180064aa0  call    sqlite3_free
0x180064aa5  mov     rax, cs:off_1800B3078
0x180064aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ab1  lea     r8, aWinfullpathnam; "winFullPathname1"
0x180064ab8  mov     [rsp+68h+var_48], 0CCF4h
0x180064ac0  mov     r9, rbx
0x180064ac3  mov     edx, eax
0x180064ac5  mov     ecx, 30Eh
0x180064aca  call    winLogErrorAtLine
0x180064acf  jmp     short loc_180064AF3
0x180064ad1  lea     ebp, [rax+3]
0x180064ad4  mov     ecx, ebp
0x180064ad6  add     rcx, rcx; Size
0x180064ad9  call    sqlite3MallocZero
0x180064ade  mov     rsi, rax
0x180064ae1  mov     rcx, rdi
0x180064ae4  test    rax, rax
0x180064ae7  jnz     short loc_180064B02
0x180064ae9  call    sqlite3_free
0x180064aee  mov     eax, 0C0Ah
0x180064af3  add     rsp, 30h
0x180064af7  pop     r15
0x180064af9  pop     r14
0x180064afb  pop     r13
0x180064afd  pop     rdi
0x180064afe  pop     rsi
0x180064aff  pop     rbp
0x180064b00  pop     rbx
0x180064b01  retn
0x180064b02  mov     rax, cs:off_1800B3060
0x180064b09  xor     r9d, r9d
0x180064b0c  mov     r8, rsi
0x180064b0f  mov     edx, ebp
0x180064b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b16  mov     rcx, rdi
0x180064b19  test    eax, eax
0x180064b1b  jnz     short loc_180064B4A
0x180064b1d  call    sqlite3_free
0x180064b22  mov     rcx, rsi
0x180064b25  call    sqlite3_free
0x180064b2a  mov     rax, cs:off_1800B3078
0x180064b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b36  lea     r8, aWinfullpathnam_0; "winFullPathname2"
0x180064b3d  mov     [rsp+68h+var_48], 0CD01h
0x180064b45  jmp     loc_180064AC0
0x180064b4a  call    sqlite3_free
0x180064b4f  mov     rcx, rsi
0x180064b52  call    winUnicodeToUtf8
0x180064b57  mov     rcx, rsi
0x180064b5a  mov     rbx, rax
0x180064b5d  call    sqlite3_free
0x180064b62  test    rbx, rbx
0x180064b65  jz      short loc_180064AEE
0x180064b67  mov     ecx, [r13+8]
0x180064b6b  lea     r8, aS_7; "%s"
0x180064b72  cmp     r14d, ecx
0x180064b75  mov     r9, rbx
0x180064b78  mov     rdx, r15
0x180064b7b  cmovl   ecx, r14d
0x180064b7f  call    sqlite3_snprintf
0x180064b84  mov     rcx, rbx
0x180064b87  call    sqlite3_free
0x180064b8c  jmp     loc_180064A6B
```
