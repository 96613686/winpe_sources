# _write_nolock

- ea: `0x180018960`
- end: `0x180018c43`
- name: `_write_nolock`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180018874`

## callees

- `0x18000be9c`
- `0x18000bf4c`
- `0x18000bf9c`
- `0x18000bfbc`
- `0x1800102a4`
- `0x1800168e0`
- `0x180017ff8`
- `0x1800184e4`
- `0x1800185e8`
- `0x180018704`
- `0x180018960`
- `0x180019978`
- `0x180019c84`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018aea`
- `KERNEL32!GetLastError` at `0x180018b9c`
- `KERNEL32!GetLastError` at `0x180018aea`
- `KERNEL32!GetLastError` at `0x180018b9c`
- `KERNEL32!WriteFile` at `0x180018b92`
- `KERNEL32!WriteFile` at `0x180018b92`
- `KERNEL32!GetConsoleMode` at `0x180018a60`
- `KERNEL32!GetConsoleMode` at `0x180018a60`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, _BYTE *a2, unsigned int a3)
{
  int v3; // ebx
  __int64 v4; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 v10; // rcx
  int v11; // esi
  _BYTE *v12; // r12
  _WORD *v13; // r14
  DWORD v14; // esi
  _QWORD *v15; // rax
  __int64 v16; // xmm0_8
  __int64 v17; // rcx
  void *v18; // rcx
  DWORD NumberOfBytesWritten[2]; // [rsp+30h] [rbp-30h] BYREF
  int v20; // [rsp+38h] [rbp-28h]
  __int64 v21; // [rsp+40h] [rbp-20h]
  DWORD Mode[4]; // [rsp+50h] [rbp-10h] BYREF

  v3 = 0;
  v4 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v8 = (__int64)(int)a1 >> 6,
        v9 = 9LL * (a1 & 0x3F),
        v10 = _pioinfo[v8],
        v11 = *(char *)(v10 + 72LL * (a1 & 0x3F) + 57),
        (unsigned __int8)(*(_BYTE *)(v10 + 72LL * (a1 & 0x3F) + 57) - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v10 + 72LL * (a1 & 0x3F) + 56) & 0x20) != 0 )
    lseeki64_nolock(a1, 0, 2);
  v21 = 0;
  if ( !isatty(a1)
    || *(char *)(_pioinfo[v8] + 72LL * (a1 & 0x3F) + 56) >= 0
    || !*(_QWORD *)(*(_QWORD *)(_acrt_getptd() + 144) + 312LL) && !*(_BYTE *)(_pioinfo[v8] + 72LL * (a1 & 0x3F) + 57)
    || !GetConsoleMode(*(HANDLE *)(_pioinfo[v8] + 72LL * (a1 & 0x3F) + 40), Mode) )
  {
    v17 = _pioinfo[v8];
    if ( *(char *)(v17 + 72LL * (a1 & 0x3F) + 56) >= 0 )
    {
      v18 = *(void **)(v17 + 72LL * (a1 & 0x3F) + 40);
      *(_QWORD *)NumberOfBytesWritten = 0;
      v20 = 0;
      if ( !WriteFile(v18, a2, v4, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v3 = v20;
LABEL_37:
      v16 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_38;
    }
    if ( (_BYTE)v11 )
    {
      if ( v11 == 1 )
      {
        v15 = (_QWORD *)write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
      else
      {
        if ( v11 != 2 )
          goto LABEL_39;
        v15 = (_QWORD *)write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
    }
    else
    {
      v15 = (_QWORD *)write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
    }
LABEL_26:
    v16 = *v15;
    v3 = *((_DWORD *)v15 + 2);
LABEL_38:
    v21 = v16;
    goto LABEL_39;
  }
  if ( !(_BYTE)v11 )
  {
    v15 = write_double_translated_ansi_nolock(NumberOfBytesWritten, a1, a2, v4);
    goto LABEL_26;
  }
  if ( (unsigned __int8)(v11 - 1) <= 1u )
  {
    v12 = &a2[v4];
    *(_QWORD *)NumberOfBytesWritten = 0;
    v13 = a2;
    if ( a2 < v12 )
    {
      v14 = NumberOfBytesWritten[1];
      while ( 1 )
      {
        LOWORD(Mode[0]) = *v13;
        if ( putwch_nolock(Mode[0]) != LOWORD(Mode[0]) )
          break;
        v14 += 2;
        NumberOfBytesWritten[1] = v14;
        if ( LOWORD(Mode[0]) == 10 )
        {
          if ( putwch_nolock(0xDu) != 13 )
            break;
          NumberOfBytesWritten[1] = ++v14;
          ++v3;
        }
        if ( ++v13 >= (_WORD *)v12 )
          goto LABEL_37;
      }
      NumberOfBytesWritten[0] = GetLastError();
    }
    goto LABEL_37;
  }
LABEL_39:
  if ( HIDWORD(v21) )
    return (unsigned int)(HIDWORD(v21) - v3);
  if ( (_DWORD)v21 )
  {
    if ( (_DWORD)v21 == 5 )
    {
      *errno() = 9;
      *_doserrno() = 5;
    }
    else
    {
      _acrt_errno_map_os_error((unsigned int)v21);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v8] + 8 * v9 + 56) & 0x40) == 0 || *a2 != 26 )
  {
    *errno() = 28;
    *_doserrno() = 0;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x180018960  mov     [rsp-38h+arg_18], rbx
0x180018965  push    rbp
0x180018966  push    rsi
0x180018967  push    rdi
0x180018968  push    r12
0x18001896a  push    r13
0x18001896c  push    r14
0x18001896e  push    r15
0x180018970  mov     rbp, rsp
0x180018973  sub     rsp, 60h
0x180018977  xor     ebx, ebx
0x180018979  mov     r14d, r8d
0x18001897c  movsxd  r12, ecx
0x18001897f  mov     rdi, rdx
0x180018982  test    r8d, r8d
0x180018985  jz      loc_180018C29
0x18001898b  test    rdx, rdx
0x18001898e  jnz     short loc_1800189AF
0x180018990  call    __doserrno
0x180018995  mov     [rax], ebx
0x180018997  call    _errno
0x18001899c  mov     dword ptr [rax], 16h
0x1800189a2  call    _invalid_parameter_noinfo
0x1800189a7  or      eax, 0FFFFFFFFh
0x1800189aa  jmp     loc_180018C2B
0x1800189af  mov     rax, r12
0x1800189b2  lea     rcx, __pioinfo
0x1800189b9  and     eax, 3Fh
0x1800189bc  mov     r13, r12
0x1800189bf  sar     r13, 6
0x1800189c3  lea     r15, [rax+rax*8]
0x1800189c7  mov     rcx, [rcx+r13*8]
0x1800189cb  movsx   esi, byte ptr [rcx+r15*8+39h]
0x1800189d1  lea     eax, [rsi-1]
0x1800189d4  cmp     al, 1
0x1800189d6  ja      short loc_1800189E1
0x1800189d8  mov     eax, r14d
0x1800189db  not     eax
0x1800189dd  test    al, 1
0x1800189df  jz      short loc_180018990
0x1800189e1  test    byte ptr [rcx+r15*8+38h], 20h
0x1800189e7  jz      short loc_1800189F7
0x1800189e9  xor     edx, edx
0x1800189eb  mov     ecx, r12d
0x1800189ee  lea     r8d, [rdx+2]
0x1800189f2  call    _lseeki64_nolock
0x1800189f7  mov     ecx, r12d; FileHandle
0x1800189fa  mov     [rbp+var_20], rbx
0x1800189fe  call    _isatty
0x180018a03  test    eax, eax
0x180018a05  jz      loc_180018B16
0x180018a0b  lea     rax, __pioinfo
0x180018a12  mov     rax, [rax+r13*8]
0x180018a16  cmp     [rax+r15*8+38h], bl
0x180018a1b  jge     loc_180018B16
0x180018a21  call    __acrt_getptd
0x180018a26  mov     rcx, [rax+90h]
0x180018a2d  cmp     [rcx+138h], rbx
0x180018a34  jnz     short loc_180018A4C
0x180018a36  lea     rax, __pioinfo
0x180018a3d  mov     rax, [rax+r13*8]
0x180018a41  cmp     [rax+r15*8+39h], bl
0x180018a46  jz      loc_180018B16
0x180018a4c  lea     rax, __pioinfo
0x180018a53  mov     rcx, [rax+r13*8]
0x180018a57  lea     rdx, [rbp+Mode]; lpMode
0x180018a5b  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x180018a60  call    cs:__imp_GetConsoleMode
0x180018a66  test    eax, eax
0x180018a68  jz      loc_180018B16
0x180018a6e  test    sil, sil
0x180018a71  jz      loc_180018AF8
0x180018a77  dec     sil
0x180018a7a  cmp     sil, 1
0x180018a7e  ja      loc_180018BB2
0x180018a84  lea     r12, [rdi+r14]
0x180018a88  mov     qword ptr [rbp+NumberOfBytesWritten], rbx
0x180018a8c  mov     r14, rdi
0x180018a8f  cmp     rdi, r12
0x180018a92  jnb     loc_180018BA8
0x180018a98  mov     esi, [rbp+NumberOfBytesWritten+4]
0x180018a9b  movzx   eax, word ptr [r14]
0x180018a9f  movzx   ecx, ax; Character
0x180018aa2  mov     word ptr [rbp+Mode], ax
0x180018aa6  call    _putwch_nolock
0x180018aab  movzx   ecx, word ptr [rbp+Mode]
0x180018aaf  cmp     ax, cx
0x180018ab2  jnz     short loc_180018AEA
0x180018ab4  add     esi, 2
0x180018ab7  mov     [rbp+NumberOfBytesWritten+4], esi
0x180018aba  cmp     cx, 0Ah
0x180018abe  jnz     short loc_180018ADB
0x180018ac0  mov     ecx, 0Dh; Character
0x180018ac5  call    _putwch_nolock
0x180018aca  mov     ecx, 0Dh
0x180018acf  cmp     ax, cx
0x180018ad2  jnz     short loc_180018AEA
0x180018ad4  inc     esi
0x180018ad6  mov     [rbp+NumberOfBytesWritten+4], esi
0x180018ad9  inc     ebx
0x180018adb  add     r14, 2
0x180018adf  cmp     r14, r12
0x180018ae2  jnb     loc_180018BA8
0x180018ae8  jmp     short loc_180018A9B
0x180018aea  call    cs:__imp_GetLastError
0x180018af0  mov     [rbp+NumberOfBytesWritten], eax
0x180018af3  jmp     loc_180018BA8
0x180018af8  mov     r9d, r14d
0x180018afb  lea     rcx, [rbp+NumberOfBytesWritten]
0x180018aff  mov     r8, rdi
0x180018b02  mov     edx, r12d
0x180018b05  call    write_double_translated_ansi_nolock
0x180018b0a  movsd   xmm0, qword ptr [rax]
0x180018b0e  mov     ebx, [rax+8]
0x180018b11  jmp     loc_180018BAD
0x180018b16  lea     rax, __pioinfo
0x180018b1d  mov     rcx, [rax+r13*8]
0x180018b21  cmp     [rcx+r15*8+38h], bl
0x180018b26  jge     short loc_180018B75
0x180018b28  mov     ecx, esi
0x180018b2a  test    sil, sil
0x180018b2d  jz      short loc_180018B61
0x180018b2f  sub     ecx, 1
0x180018b32  jz      short loc_180018B4D
0x180018b34  cmp     ecx, 1
0x180018b37  jnz     short loc_180018BB2
0x180018b39  mov     r9d, r14d
0x180018b3c  lea     rcx, [rbp+NumberOfBytesWritten]
0x180018b40  mov     r8, rdi
0x180018b43  mov     edx, r12d
0x180018b46  call    write_text_utf16le_nolock
0x180018b4b  jmp     short loc_180018B0A
0x180018b4d  mov     r9d, r14d
0x180018b50  lea     rcx, [rbp+NumberOfBytesWritten]
0x180018b54  mov     r8, rdi
0x180018b57  mov     edx, r12d
0x180018b5a  call    write_text_utf8_nolock
0x180018b5f  jmp     short loc_180018B0A
0x180018b61  mov     r9d, r14d
0x180018b64  lea     rcx, [rbp+NumberOfBytesWritten]
0x180018b68  mov     r8, rdi
0x180018b6b  mov     edx, r12d
0x180018b6e  call    write_text_ansi_nolock
0x180018b73  jmp     short loc_180018B0A
0x180018b75  mov     rcx, [rcx+r15*8+28h]; hFile
0x180018b7a  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x180018b7e  xor     eax, eax
0x180018b80  mov     r8d, r14d; nNumberOfBytesToWrite
0x180018b83  and     [rsp+60h+var_40], rax
0x180018b88  mov     rdx, rdi; lpBuffer
0x180018b8b  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x180018b8f  mov     [rbp+var_28], eax
0x180018b92  call    cs:__imp_WriteFile
0x180018b98  test    eax, eax
0x180018b9a  jnz     short loc_180018BA5
0x180018b9c  call    cs:__imp_GetLastError
0x180018ba2  mov     [rbp+NumberOfBytesWritten], eax
0x180018ba5  mov     ebx, [rbp+var_28]
0x180018ba8  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x180018bad  movsd   [rbp+var_20], xmm0
0x180018bb2  mov     rax, [rbp+var_20]
0x180018bb6  shr     rax, 20h
0x180018bba  test    eax, eax
0x180018bbc  jnz     short loc_180018C22
0x180018bbe  mov     eax, dword ptr [rbp+var_20]
0x180018bc1  test    eax, eax
0x180018bc3  jz      short loc_180018BF2
0x180018bc5  cmp     eax, 5
0x180018bc8  jnz     short loc_180018BE5
0x180018bca  call    _errno
0x180018bcf  mov     dword ptr [rax], 9
0x180018bd5  call    __doserrno
0x180018bda  mov     dword ptr [rax], 5
0x180018be0  jmp     loc_1800189A7
0x180018be5  mov     ecx, dword ptr [rbp+var_20]
0x180018be8  call    __acrt_errno_map_os_error
0x180018bed  jmp     loc_1800189A7
0x180018bf2  lea     rax, __pioinfo
0x180018bf9  mov     rax, [rax+r13*8]
0x180018bfd  test    byte ptr [rax+r15*8+38h], 40h
0x180018c03  jz      short loc_180018C0A
0x180018c05  cmp     byte ptr [rdi], 1Ah
0x180018c08  jz      short loc_180018C29
0x180018c0a  call    _errno
0x180018c0f  mov     dword ptr [rax], 1Ch
0x180018c15  call    __doserrno
0x180018c1a  and     dword ptr [rax], 0
0x180018c1d  jmp     loc_1800189A7
0x180018c22  mov     eax, dword ptr [rbp+var_20+4]
0x180018c25  sub     eax, ebx
0x180018c27  jmp     short loc_180018C2B
0x180018c29  xor     eax, eax
0x180018c2b  mov     rbx, [rsp+60h+arg_18]
0x180018c33  add     rsp, 60h
0x180018c37  pop     r15
0x180018c39  pop     r14
0x180018c3b  pop     r13
0x180018c3d  pop     r12
0x180018c3f  pop     rdi
0x180018c40  pop     rsi
0x180018c41  pop     rbp
0x180018c42  retn
```
