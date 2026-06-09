# _write_nolock

- ea: `0x18033ca10`
- end: `0x18033ccf1`
- name: `_write_nolock`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18033c924`

## callees

- `0x180334620`
- `0x180334700`
- `0x180334750`
- `0x180334770`
- `0x18033c384`
- `0x18033c58c`
- `0x18033c694`
- `0x18033c7b0`
- `0x18033ca10`
- `0x18033ce88`
- `0x180349414`
- `0x18034ee8c`
- `0x18034eeec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033cb93`
- `KERNEL32!GetLastError` at `0x18033cc4a`
- `KERNEL32!GetLastError` at `0x18033cb93`
- `KERNEL32!GetLastError` at `0x18033cc4a`
- `KERNEL32!GetConsoleMode` at `0x18033cb18`
- `KERNEL32!GetConsoleMode` at `0x18033cb18`
- `KERNEL32!WriteFile` at `0x18033cc40`
- `KERNEL32!WriteFile` at `0x18033cc40`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, const char *a2, unsigned int a3)
{
  DWORD v3; // edi
  __int64 v4; // r15
  __int64 v8; // r13
  unsigned __int64 v9; // r14
  __int64 v10; // rcx
  char v11; // bl
  const char *v12; // r12
  DWORD v13; // ebx
  wchar_t *v14; // r15
  wchar_t v15; // r13
  __int64 v16; // rax
  __int64 v17; // xmm0_8
  __int64 v18; // rcx
  void *v19; // rcx
  DWORD NumberOfBytesWritten[4]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+40h] [rbp-20h]
  __int64 v22; // [rsp+50h] [rbp-10h]
  DWORD Mode; // [rsp+58h] [rbp-8h] BYREF

  v3 = 0;
  v4 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v8 = (__int64)(int)a1 >> 6,
        v9 = (unsigned __int64)(a1 & 0x3F) << 6,
        v22 = v8,
        v10 = _pioinfo[v8],
        v11 = *(_BYTE *)(v10 + v9 + 57),
        (unsigned __int8)(v11 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v10 + v9 + 56) & 0x20) != 0 )
    lseeki64_nolock(a1, 0, 2);
  v21 = 0;
  if ( isatty(a1)
    && *(char *)(_pioinfo[v8] + v9 + 56) < 0
    && (*(_QWORD *)(*(_QWORD *)(_acrt_getptd() + 144) + 312LL) || *(_BYTE *)(_pioinfo[v8] + v9 + 57))
    && GetConsoleMode(*(HANDLE *)(_pioinfo[v8] + v9 + 40), &Mode) )
  {
    if ( v11 )
    {
      if ( (unsigned __int8)(v11 - 1) > 1u )
        goto LABEL_40;
      NumberOfBytesWritten[0] = 0;
      v12 = &a2[v4];
      v13 = 0;
      v14 = (wchar_t *)a2;
      NumberOfBytesWritten[1] = 0;
      if ( a2 < v12 )
      {
        while ( 1 )
        {
          v15 = *v14;
          if ( putwch_nolock(*v14) != v15 )
            break;
          v13 += 2;
          NumberOfBytesWritten[1] = v13;
          if ( v15 == 10 )
          {
            if ( putwch_nolock(0xDu) != 13 )
              break;
            NumberOfBytesWritten[1] = ++v13;
            ++v3;
          }
          if ( ++v14 >= (wchar_t *)v12 )
            goto LABEL_25;
        }
        NumberOfBytesWritten[0] = GetLastError();
LABEL_25:
        v8 = v22;
      }
      goto LABEL_38;
    }
    v16 = write_double_translated_ansi_nolock((__int64)NumberOfBytesWritten, a1, a2, v4);
  }
  else
  {
    v18 = _pioinfo[v8];
    if ( *(char *)(v18 + v9 + 56) >= 0 )
    {
      v19 = *(void **)(v18 + v9 + 40);
      memset(NumberOfBytesWritten, 0, 12);
      if ( !WriteFile(v19, a2, v4, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v3 = NumberOfBytesWritten[2];
LABEL_38:
      v17 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_39;
    }
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v16 = write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
      else
      {
        if ( v11 != 2 )
          goto LABEL_40;
        v16 = write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
    }
    else
    {
      v16 = write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
    }
  }
  v17 = *(_QWORD *)v16;
  v3 = *(_DWORD *)(v16 + 8);
LABEL_39:
  v21 = v17;
LABEL_40:
  if ( !HIDWORD(v21) )
  {
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
    }
    else
    {
      if ( (*(_BYTE *)(_pioinfo[v8] + v9 + 56) & 0x40) != 0 && *a2 == 26 )
        return 0;
      *errno() = 28;
      *_doserrno() = 0;
    }
    return 0xFFFFFFFFLL;
  }
  return HIDWORD(v21) - v3;
}

```

## disassembly

```asm
0x18033ca10  mov     [rsp-38h+arg_18], rbx
0x18033ca15  push    rbp
0x18033ca16  push    rsi
0x18033ca17  push    rdi
0x18033ca18  push    r12
0x18033ca1a  push    r13
0x18033ca1c  push    r14
0x18033ca1e  push    r15
0x18033ca20  mov     rbp, rsp
0x18033ca23  sub     rsp, 60h
0x18033ca27  xor     edi, edi
0x18033ca29  mov     r15d, r8d
0x18033ca2c  movsxd  r12, ecx
0x18033ca2f  mov     rsi, rdx
0x18033ca32  test    r8d, r8d
0x18033ca35  jnz     short loc_18033CA3E
0x18033ca37  xor     eax, eax
0x18033ca39  jmp     loc_18033CCD9
0x18033ca3e  test    rdx, rdx
0x18033ca41  jnz     short loc_18033CA62
0x18033ca43  call    __doserrno
0x18033ca48  mov     [rax], edi
0x18033ca4a  call    _errno
0x18033ca4f  mov     dword ptr [rax], 16h
0x18033ca55  call    _invalid_parameter_noinfo
0x18033ca5a  or      eax, 0FFFFFFFFh
0x18033ca5d  jmp     loc_18033CCD9
0x18033ca62  mov     r14, r12
0x18033ca65  lea     rax, __pioinfo
0x18033ca6c  and     r14d, 3Fh
0x18033ca70  mov     r13, r12
0x18033ca73  sar     r13, 6
0x18033ca77  shl     r14, 6
0x18033ca7b  mov     [rbp+var_10], r13
0x18033ca7f  mov     rcx, [rax+r13*8]
0x18033ca83  mov     bl, [rcx+r14+39h]
0x18033ca88  lea     eax, [rbx-1]
0x18033ca8b  cmp     al, 1
0x18033ca8d  ja      short loc_18033CA98
0x18033ca8f  mov     eax, r15d
0x18033ca92  not     eax
0x18033ca94  test    al, 1
0x18033ca96  jz      short loc_18033CA43
0x18033ca98  test    byte ptr [rcx+r14+38h], 20h
0x18033ca9e  jz      short loc_18033CAAE
0x18033caa0  xor     edx, edx
0x18033caa2  mov     ecx, r12d
0x18033caa5  lea     r8d, [rdx+2]
0x18033caa9  call    _lseeki64_nolock
0x18033caae  mov     ecx, r12d; FileHandle
0x18033cab1  mov     [rbp+var_20], rdi
0x18033cab5  call    _isatty
0x18033caba  test    eax, eax
0x18033cabc  jz      loc_18033CBC3
0x18033cac2  lea     rax, __pioinfo
0x18033cac9  mov     rax, [rax+r13*8]
0x18033cacd  test    byte ptr [rax+r14+38h], 80h
0x18033cad3  jz      loc_18033CBC3
0x18033cad9  call    __acrt_getptd
0x18033cade  mov     rcx, [rax+90h]
0x18033cae5  cmp     [rcx+138h], rdi
0x18033caec  jnz     short loc_18033CB04
0x18033caee  lea     rax, __pioinfo
0x18033caf5  mov     rax, [rax+r13*8]
0x18033caf9  cmp     [rax+r14+39h], dil
0x18033cafe  jz      loc_18033CBC3
0x18033cb04  lea     rax, __pioinfo
0x18033cb0b  mov     rcx, [rax+r13*8]
0x18033cb0f  lea     rdx, [rbp+Mode]; lpMode
0x18033cb13  mov     rcx, [rcx+r14+28h]; hConsoleHandle
0x18033cb18  call    cs:__imp_GetConsoleMode
0x18033cb1e  test    eax, eax
0x18033cb20  jz      loc_18033CBC3
0x18033cb26  test    bl, bl
0x18033cb28  jz      short loc_18033CBA5
0x18033cb2a  dec     bl
0x18033cb2c  cmp     bl, 1
0x18033cb2f  ja      loc_18033CC60
0x18033cb35  and     [rbp+NumberOfBytesWritten], edi
0x18033cb38  lea     r12, [rsi+r15]
0x18033cb3c  xor     ebx, ebx
0x18033cb3e  mov     r15, rsi
0x18033cb41  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18033cb44  cmp     rsi, r12
0x18033cb47  jnb     loc_18033CC56
0x18033cb4d  movzx   r13d, word ptr [r15]
0x18033cb51  movzx   ecx, r13w; Character
0x18033cb55  call    _putwch_nolock
0x18033cb5a  cmp     ax, r13w
0x18033cb5e  jnz     short loc_18033CB93
0x18033cb60  add     ebx, 2
0x18033cb63  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18033cb66  cmp     r13w, 0Ah
0x18033cb6b  jnz     short loc_18033CB88
0x18033cb6d  mov     r13d, 0Dh
0x18033cb73  mov     ecx, r13d; Character
0x18033cb76  call    _putwch_nolock
0x18033cb7b  cmp     ax, r13w
0x18033cb7f  jnz     short loc_18033CB93
0x18033cb81  inc     ebx
0x18033cb83  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18033cb86  inc     edi
0x18033cb88  add     r15, 2
0x18033cb8c  cmp     r15, r12
0x18033cb8f  jnb     short loc_18033CB9C
0x18033cb91  jmp     short loc_18033CB4D
0x18033cb93  call    cs:__imp_GetLastError
0x18033cb99  mov     [rbp+NumberOfBytesWritten], eax
0x18033cb9c  mov     r13, [rbp+var_10]
0x18033cba0  jmp     loc_18033CC56
0x18033cba5  mov     r9d, r15d
0x18033cba8  lea     rcx, [rbp+NumberOfBytesWritten]
0x18033cbac  mov     r8, rsi
0x18033cbaf  mov     edx, r12d
0x18033cbb2  call    write_double_translated_ansi_nolock
0x18033cbb7  movsd   xmm0, qword ptr [rax]
0x18033cbbb  mov     edi, [rax+8]
0x18033cbbe  jmp     loc_18033CC5B
0x18033cbc3  lea     rax, __pioinfo
0x18033cbca  mov     rcx, [rax+r13*8]
0x18033cbce  test    byte ptr [rcx+r14+38h], 80h
0x18033cbd4  jz      short loc_18033CC23
0x18033cbd6  movsx   ecx, bl
0x18033cbd9  test    bl, bl
0x18033cbdb  jz      short loc_18033CC0F
0x18033cbdd  sub     ecx, 1
0x18033cbe0  jz      short loc_18033CBFB
0x18033cbe2  cmp     ecx, 1
0x18033cbe5  jnz     short loc_18033CC60
0x18033cbe7  mov     r9d, r15d
0x18033cbea  lea     rcx, [rbp+NumberOfBytesWritten]
0x18033cbee  mov     r8, rsi
0x18033cbf1  mov     edx, r12d
0x18033cbf4  call    write_text_utf16le_nolock
0x18033cbf9  jmp     short loc_18033CBB7
0x18033cbfb  mov     r9d, r15d
0x18033cbfe  lea     rcx, [rbp+NumberOfBytesWritten]
0x18033cc02  mov     r8, rsi
0x18033cc05  mov     edx, r12d
0x18033cc08  call    write_text_utf8_nolock
0x18033cc0d  jmp     short loc_18033CBB7
0x18033cc0f  mov     r9d, r15d
0x18033cc12  lea     rcx, [rbp+NumberOfBytesWritten]
0x18033cc16  mov     r8, rsi
0x18033cc19  mov     edx, r12d
0x18033cc1c  call    write_text_ansi_nolock
0x18033cc21  jmp     short loc_18033CBB7
0x18033cc23  mov     rcx, [rcx+r14+28h]; hFile
0x18033cc28  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18033cc2c  and     [rbp+NumberOfBytesWritten], edi
0x18033cc2f  xor     eax, eax
0x18033cc31  and     [rsp+60h+var_40], rax
0x18033cc36  mov     r8d, r15d; nNumberOfBytesToWrite
0x18033cc39  mov     rdx, rsi; lpBuffer
0x18033cc3c  mov     qword ptr [rbp+NumberOfBytesWritten+4], rax
0x18033cc40  call    cs:__imp_WriteFile
0x18033cc46  test    eax, eax
0x18033cc48  jnz     short loc_18033CC53
0x18033cc4a  call    cs:__imp_GetLastError
0x18033cc50  mov     [rbp+NumberOfBytesWritten], eax
0x18033cc53  mov     edi, [rbp+NumberOfBytesWritten+8]
0x18033cc56  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18033cc5b  movsd   [rbp+var_20], xmm0
0x18033cc60  mov     rax, [rbp+var_20]
0x18033cc64  shr     rax, 20h
0x18033cc68  test    eax, eax
0x18033cc6a  jnz     short loc_18033CCD4
0x18033cc6c  mov     eax, dword ptr [rbp+var_20]
0x18033cc6f  test    eax, eax
0x18033cc71  jz      short loc_18033CCA0
0x18033cc73  cmp     eax, 5
0x18033cc76  jnz     short loc_18033CC93
0x18033cc78  call    _errno
0x18033cc7d  mov     dword ptr [rax], 9
0x18033cc83  call    __doserrno
0x18033cc88  mov     dword ptr [rax], 5
0x18033cc8e  jmp     loc_18033CA5A
0x18033cc93  mov     ecx, dword ptr [rbp+var_20]
0x18033cc96  call    __acrt_errno_map_os_error
0x18033cc9b  jmp     loc_18033CA5A
0x18033cca0  lea     rax, __pioinfo
0x18033cca7  mov     rax, [rax+r13*8]
0x18033ccab  test    byte ptr [rax+r14+38h], 40h
0x18033ccb1  jz      short loc_18033CCBC
0x18033ccb3  cmp     byte ptr [rsi], 1Ah
0x18033ccb6  jz      loc_18033CA37
0x18033ccbc  call    _errno
0x18033ccc1  mov     dword ptr [rax], 1Ch
0x18033ccc7  call    __doserrno
0x18033cccc  and     dword ptr [rax], 0
0x18033cccf  jmp     loc_18033CA5A
0x18033ccd4  mov     eax, dword ptr [rbp+var_20+4]
0x18033ccd7  sub     eax, edi
0x18033ccd9  mov     rbx, [rsp+60h+arg_18]
0x18033cce1  add     rsp, 60h
0x18033cce5  pop     r15
0x18033cce7  pop     r14
0x18033cce9  pop     r13
0x18033cceb  pop     r12
0x18033cced  pop     rdi
0x18033ccee  pop     rsi
0x18033ccef  pop     rbp
0x18033ccf0  retn
```
