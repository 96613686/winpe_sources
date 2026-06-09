# winFullPathnameNoMutex

- ea: `0x18004ab94`
- end: `0x18004ad88`
- name: `winFullPathnameNoMutex`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004b250`

## callees

- `0x180035784`
- `0x180036380`
- `0x1800375e4`
- `0x180041eb0`
- `0x18004909c`
- `0x18004ab94`
- `0x18004ae40`
- `0x1800a4ce8`
- `0x1800b0010`

## string_xrefs

- `0x18004ad31`: `winFullPathname1`
- `0x18004ad5b`: `winFullPathname2`

## pseudocode

```c
__int64 __fastcall winFullPathnameNoMutex(__int64 a1, _BYTE *a2, int a3, __int64 a4)
{
  char v5; // r8
  _BYTE *v7; // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  int v11; // eax
  unsigned int v12; // ebp
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rcx
  _BYTE *v18; // rcx
  __int64 v19; // rcx
  DWORD v20; // eax
  DWORD v21; // eax

  v5 = 92;
  v7 = a2;
  if ( *a2 == 47
    && ((unsigned int)winIsDriveLetterAndColon(a2 + 1) || *v18 == v5 && v18[1] == v5 && v18[2] == 63 && v18[3] == v5) )
  {
    v7 = v18;
  }
  if ( sqlite3_data_directory && *v7 != 47 && *v7 != v5 && !(unsigned int)winIsDriveLetterAndColon(v7) )
  {
    v19 = *(unsigned int *)(a1 + 8);
    if ( a3 < (int)v19 )
      v19 = (unsigned int)a3;
    sqlite3_snprintf(v19, a4, "%s%c%s");
    return 0;
  }
  v9 = winUtf8ToUnicode(v7);
  v10 = v9;
  if ( !v9 )
    return 3082;
  v11 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))off_1800CE060)(v9, 0, 0, 0);
  if ( v11 )
  {
    v12 = v11 + 3;
    v13 = sqlite3MallocZero(2LL * (unsigned int)(v11 + 3));
    v14 = v13;
    if ( !v13 )
    {
      sqlite3_free(v10);
      return 3082;
    }
    if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))off_1800CE060)(v10, v12, v13, 0) )
    {
      sqlite3_free(v10);
      v15 = winUnicodeToUtf8(v14);
      sqlite3_free(v14);
      if ( v15 )
      {
        v16 = *(unsigned int *)(a1 + 8);
        if ( a3 < (int)v16 )
          v16 = (unsigned int)a3;
        sqlite3_snprintf(v16, a4, "%s", v15);
        sqlite3_free(v15);
        return 0;
      }
      return 3082;
    }
    sqlite3_free(v10);
    sqlite3_free(v14);
    v21 = off_1800CE078();
    return winLogErrorAtLine(782, v21, (unsigned int)"winFullPathname2", (_DWORD)v7, 52480);
  }
  else
  {
    sqlite3_free(v10);
    v20 = off_1800CE078();
    return winLogErrorAtLine(782, v20, (unsigned int)"winFullPathname1", (_DWORD)v7, 52467);
  }
}

```

## disassembly

```asm
0x18004ab94  push    rbx
0x18004ab96  push    rbp
0x18004ab97  push    rsi
0x18004ab98  push    rdi
0x18004ab99  push    r13
0x18004ab9b  push    r14
0x18004ab9d  push    r15
0x18004ab9f  sub     rsp, 30h
0x18004aba3  cmp     byte ptr [rdx], 2Fh ; '/'
0x18004aba6  mov     r14d, r8d
0x18004aba9  mov     r8d, 5Ch ; '\'
0x18004abaf  mov     r15, r9
0x18004abb2  mov     rbx, rdx
0x18004abb5  mov     r13, rcx
0x18004abb8  jz      loc_18004AC96
0x18004abbe  mov     r9, cs:sqlite3_data_directory
0x18004abc5  test    r9, r9
0x18004abc8  jnz     loc_18004ACD2
0x18004abce  mov     rcx, rbx
0x18004abd1  call    winUtf8ToUnicode
0x18004abd6  mov     rdi, rax
0x18004abd9  test    rax, rax
0x18004abdc  jz      loc_18004AC8F
0x18004abe2  mov     rcx, rax
0x18004abe5  xor     r9d, r9d
0x18004abe8  mov     rax, cs:off_1800CE060
0x18004abef  xor     r8d, r8d
0x18004abf2  xor     edx, edx
0x18004abf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abf9  test    eax, eax
0x18004abfb  jz      loc_18004AD1D
0x18004ac01  lea     ebp, [rax+3]
0x18004ac04  mov     ecx, ebp
0x18004ac06  add     rcx, rcx; Size
0x18004ac09  call    sqlite3MallocZero
0x18004ac0e  mov     rsi, rax
0x18004ac11  mov     rcx, rdi
0x18004ac14  test    rax, rax
0x18004ac17  jz      loc_18004AD7E
0x18004ac1d  mov     r8, rax
0x18004ac20  xor     r9d, r9d
0x18004ac23  mov     rax, cs:off_1800CE060
0x18004ac2a  mov     edx, ebp
0x18004ac2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac31  mov     rcx, rdi
0x18004ac34  test    eax, eax
0x18004ac36  jz      loc_18004AD42
0x18004ac3c  call    sqlite3_free
0x18004ac41  mov     rcx, rsi
0x18004ac44  call    winUnicodeToUtf8
0x18004ac49  mov     rcx, rsi
0x18004ac4c  mov     rbx, rax
0x18004ac4f  call    sqlite3_free
0x18004ac54  test    rbx, rbx
0x18004ac57  jz      short loc_18004AC8F
0x18004ac59  mov     ecx, [r13+8]
0x18004ac5d  lea     r8, aS_7; "%s"
0x18004ac64  cmp     r14d, ecx
0x18004ac67  mov     r9, rbx
0x18004ac6a  mov     rdx, r15
0x18004ac6d  cmovl   ecx, r14d
0x18004ac71  call    sqlite3_snprintf
0x18004ac76  mov     rcx, rbx
0x18004ac79  call    sqlite3_free
0x18004ac7e  xor     eax, eax
0x18004ac80  add     rsp, 30h
0x18004ac84  pop     r15
0x18004ac86  pop     r14
0x18004ac88  pop     r13
0x18004ac8a  pop     rdi
0x18004ac8b  pop     rsi
0x18004ac8c  pop     rbp
0x18004ac8d  pop     rbx
0x18004ac8e  retn
0x18004ac8f  mov     eax, 0C0Ah
0x18004ac94  jmp     short loc_18004AC80
0x18004ac96  lea     rcx, [rdx+1]
0x18004ac9a  call    winIsDriveLetterAndColon
0x18004ac9f  test    eax, eax
0x18004aca1  jnz     short loc_18004ACCA
0x18004aca3  cmp     [rcx], r8b
0x18004aca6  jnz     loc_18004ABBE
0x18004acac  cmp     [rcx+1], r8b
0x18004acb0  jnz     loc_18004ABBE
0x18004acb6  cmp     byte ptr [rcx+2], 3Fh ; '?'
0x18004acba  jnz     loc_18004ABBE
0x18004acc0  cmp     [rcx+3], r8b
0x18004acc4  jnz     loc_18004ABBE
0x18004acca  mov     rbx, rcx
0x18004accd  jmp     loc_18004ABBE
0x18004acd2  cmp     byte ptr [rbx], 2Fh ; '/'
0x18004acd5  jz      loc_18004ABCE
0x18004acdb  cmp     [rbx], r8b
0x18004acde  jz      loc_18004ABCE
0x18004ace4  mov     rcx, rbx
0x18004ace7  call    winIsDriveLetterAndColon
0x18004acec  test    eax, eax
0x18004acee  jnz     loc_18004ABCE
0x18004acf4  mov     ecx, [r13+8]
0x18004acf8  mov     rdx, r15
0x18004acfb  cmp     r14d, ecx
0x18004acfe  mov     [rsp+68h+var_40], rbx
0x18004ad03  mov     [rsp+68h+var_48], r8d
0x18004ad08  lea     r8, aSCS; "%s%c%s"
0x18004ad0f  cmovl   ecx, r14d
0x18004ad13  call    sqlite3_snprintf
0x18004ad18  jmp     loc_18004AC7E
0x18004ad1d  mov     rcx, rdi
0x18004ad20  call    sqlite3_free
0x18004ad25  mov     rax, cs:off_1800CE078
0x18004ad2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad31  lea     r8, aWinfullpathnam; "winFullPathname1"
0x18004ad38  mov     [rsp+68h+var_48], 0CCF3h
0x18004ad40  jmp     short loc_18004AD6A
0x18004ad42  call    sqlite3_free
0x18004ad47  mov     rcx, rsi
0x18004ad4a  call    sqlite3_free
0x18004ad4f  mov     rax, cs:off_1800CE078
0x18004ad56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad5b  lea     r8, aWinfullpathnam_0; "winFullPathname2"
0x18004ad62  mov     [rsp+68h+var_48], 0CD00h
0x18004ad6a  mov     r9, rbx
0x18004ad6d  mov     edx, eax
0x18004ad6f  mov     ecx, 30Eh
0x18004ad74  call    winLogErrorAtLine
0x18004ad79  jmp     loc_18004AC80
0x18004ad7e  call    sqlite3_free
0x18004ad83  jmp     loc_18004AC8F
```
