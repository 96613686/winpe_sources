# _write_nolock

- ea: `0x14001ab58`
- end: `0x14001ae87`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x14001aa38`

## callees

- `0x14000bea4`
- `0x14000c750`
- `0x140012094`
- `0x140019e10`
- `0x14001a20c`
- `0x14001a6a0`
- `0x14001a7a8`
- `0x14001a8c4`
- `0x14001ab58`
- `0x14001bd2c`
- `0x14001bf40`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14001adce`
- `KERNEL32!WriteFile` at `0x14001adce`
- `KERNEL32!GetLastError` at `0x14001ad08`
- `KERNEL32!GetLastError` at `0x14001add8`
- `KERNEL32!GetLastError` at `0x14001ad08`
- `KERNEL32!GetLastError` at `0x14001add8`
- `KERNEL32!GetConsoleMode` at `0x14001ac76`
- `KERNEL32!GetConsoleMode` at `0x14001ac76`

## pseudocode

```c
__int64 __fastcall write_nolock(int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  int v4; // edi
  __int64 v5; // r14
  __int64 v6; // r13
  __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // r15
  __int64 v13; // rcx
  wchar_t *v14; // r12
  wchar_t *v15; // r15
  DWORD v16; // r14d
  __int64 v17; // rax
  __int64 v18; // xmm0_8
  __int64 v19; // rdx
  void *v20; // rcx
  char v21; // [rsp+30h] [rbp-38h]
  wchar_t v22; // [rsp+30h] [rbp-38h]
  DWORD NumberOfBytesWritten[2]; // [rsp+38h] [rbp-30h] BYREF
  int v24; // [rsp+40h] [rbp-28h]
  __int64 v25; // [rsp+48h] [rbp-20h]
  DWORD Mode[4]; // [rsp+58h] [rbp-10h] BYREF

  v4 = 0;
  v5 = a3;
  v6 = a1;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v10 = a1 & 0x3F,
        v11 = (__int64)a1 >> 6,
        v12 = 9 * v10,
        v13 = _pioinfo[v11],
        v21 = *(_BYTE *)(v13 + 72 * v10 + 57),
        (unsigned __int8)(v21 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v13 + 72 * v10 + 56) & 0x20) != 0 )
    lseeki64_nolock_internal((unsigned int)v6, 0, 2);
  v25 = 0;
  if ( !isatty(v6) || *(char *)(_pioinfo[v11] + 8 * v12 + 56) >= 0 )
    goto LABEL_29;
  if ( !*(_BYTE *)(a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)a4);
  if ( !*(_QWORD *)(*(_QWORD *)(a4 + 24) + 312LL) && !*(_BYTE *)(_pioinfo[v11] + 8 * v12 + 57)
    || (Mode[0] = 0, !GetConsoleMode(*(HANDLE *)(_pioinfo[v11] + 8 * v12 + 40), Mode)) )
  {
LABEL_29:
    v19 = _pioinfo[v6 >> 6];
    if ( *(char *)(v19 + 72 * (v6 & 0x3F) + 56) >= 0 )
    {
      v20 = *(void **)(v19 + 72 * (v6 & 0x3F) + 40);
      *(_QWORD *)NumberOfBytesWritten = 0;
      v24 = 0;
      if ( !WriteFile(v20, a2, v5, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v4 = v24;
LABEL_39:
      v18 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_40;
    }
    if ( v21 )
    {
      if ( v21 == 1 )
      {
        v17 = write_text_utf8_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
      }
      else
      {
        if ( v21 != 2 )
          goto LABEL_41;
        v17 = write_text_utf16le_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
      }
    }
    else
    {
      v17 = write_text_ansi_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
    }
LABEL_28:
    v18 = *(_QWORD *)v17;
    v4 = *(_DWORD *)(v17 + 8);
LABEL_40:
    v25 = v18;
    goto LABEL_41;
  }
  if ( !v21 )
  {
    v17 = write_double_translated_ansi_nolock((__int64)NumberOfBytesWritten, v6, a2, v5, a4);
    goto LABEL_28;
  }
  if ( (unsigned int)(v21 - 1) <= 1 )
  {
    v14 = (wchar_t *)&a2[v5];
    *(_QWORD *)NumberOfBytesWritten = 0;
    v15 = (wchar_t *)a2;
    if ( a2 < &a2[v5] )
    {
      v16 = NumberOfBytesWritten[1];
      while ( 1 )
      {
        v22 = *v15;
        if ( putwch_nolock(*v15) != v22 )
          break;
        v16 += 2;
        NumberOfBytesWritten[1] = v16;
        if ( v22 == 10 )
        {
          if ( putwch_nolock(0xDu) != 13 )
            break;
          NumberOfBytesWritten[1] = ++v16;
          ++v4;
        }
        if ( ++v15 >= v14 )
          goto LABEL_39;
      }
      NumberOfBytesWritten[0] = GetLastError();
    }
    goto LABEL_39;
  }
LABEL_41:
  if ( HIDWORD(v25) )
    return (unsigned int)(HIDWORD(v25) - v4);
  if ( (_DWORD)v25 )
  {
    if ( (_DWORD)v25 == 5 )
    {
      *(_BYTE *)(a4 + 48) = 1;
      *(_DWORD *)(a4 + 44) = 9;
      *(_BYTE *)(a4 + 56) = 1;
      *(_DWORD *)(a4 + 52) = 5;
    }
    else
    {
      _acrt_errno_map_os_error_ptd((unsigned int)v25, a4, _pioinfo);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v6 >> 6] + 72 * (v6 & 0x3F) + 56) & 0x40) == 0 || *a2 != 26 )
  {
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 28;
    *(_BYTE *)(a4 + 56) = 1;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x14001ab58  push    rbp
0x14001ab5a  push    rbx
0x14001ab5b  push    rsi
0x14001ab5c  push    rdi
0x14001ab5d  push    r12
0x14001ab5f  push    r13
0x14001ab61  push    r14
0x14001ab63  push    r15
0x14001ab65  mov     rbp, rsp
0x14001ab68  sub     rsp, 68h
0x14001ab6c  xor     edi, edi
0x14001ab6e  mov     r14d, r8d
0x14001ab71  movsxd  r13, ecx
0x14001ab74  mov     rbx, r9
0x14001ab77  mov     rsi, rdx
0x14001ab7a  test    r8d, r8d
0x14001ab7d  jz      loc_14001AE74
0x14001ab83  test    rdx, rdx
0x14001ab86  jnz     short loc_14001ABBF
0x14001ab88  mov     byte ptr [r9+38h], 1
0x14001ab8d  xor     r8d, r8d; FileName
0x14001ab90  mov     [r9+34h], edi
0x14001ab94  xor     edx, edx; FunctionName
0x14001ab96  mov     byte ptr [r9+30h], 1
0x14001ab9b  xor     ecx, ecx; Expression
0x14001ab9d  mov     dword ptr [r9+2Ch], 16h
0x14001aba5  xor     r9d, r9d; LineNo
0x14001aba8  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x14001abad  mov     [rsp+68h+var_48], rdi; uintptr_t
0x14001abb2  call    _invalid_parameter_internal
0x14001abb7  or      eax, 0FFFFFFFFh
0x14001abba  jmp     loc_14001AE76
0x14001abbf  mov     rax, r13
0x14001abc2  lea     rcx, __pioinfo
0x14001abc9  and     eax, 3Fh
0x14001abcc  mov     r12, r13
0x14001abcf  sar     r12, 6
0x14001abd3  lea     r15, [rax+rax*8]
0x14001abd7  mov     rcx, [rcx+r12*8]
0x14001abdb  mov     al, [rcx+r15*8+39h]
0x14001abe0  mov     byte ptr [rbp+var_38], al
0x14001abe3  dec     al
0x14001abe5  cmp     al, 1
0x14001abe7  ja      short loc_14001ABF2
0x14001abe9  mov     eax, r14d
0x14001abec  not     eax
0x14001abee  test    al, 1
0x14001abf0  jz      short loc_14001AB88
0x14001abf2  test    byte ptr [rcx+r15*8+38h], 20h
0x14001abf8  jz      short loc_14001AC08
0x14001abfa  xor     edx, edx
0x14001abfc  mov     ecx, r13d
0x14001abff  lea     r8d, [rdx+2]
0x14001ac03  call    _lseeki64_nolock_internal
0x14001ac08  mov     ecx, r13d; FileHandle
0x14001ac0b  mov     [rbp+var_20], rdi
0x14001ac0f  call    _isatty
0x14001ac14  xor     ecx, ecx
0x14001ac16  lea     r8, __pioinfo
0x14001ac1d  test    eax, eax
0x14001ac1f  jz      loc_14001AD40
0x14001ac25  mov     rax, [r8+r12*8]
0x14001ac29  cmp     [rax+r15*8+38h], cl
0x14001ac2e  jge     loc_14001AD40
0x14001ac34  cmp     [rbx+28h], cl
0x14001ac37  jnz     short loc_14001AC4A
0x14001ac39  mov     rcx, rbx; this
0x14001ac3c  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x14001ac41  xor     ecx, ecx
0x14001ac43  lea     r8, __pioinfo
0x14001ac4a  mov     rax, [rbx+18h]
0x14001ac4e  cmp     [rax+138h], rcx
0x14001ac55  jnz     short loc_14001AC66
0x14001ac57  mov     rax, [r8+r12*8]
0x14001ac5b  cmp     [rax+r15*8+39h], cl
0x14001ac60  jz      loc_14001AD40
0x14001ac66  mov     [rbp+Mode], ecx
0x14001ac69  lea     rdx, [rbp+Mode]; lpMode
0x14001ac6d  mov     rcx, [r8+r12*8]
0x14001ac71  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x14001ac76  call    cs:__imp_GetConsoleMode
0x14001ac7c  test    eax, eax
0x14001ac7e  jz      loc_14001AD39
0x14001ac84  movsx   ecx, byte ptr [rbp+var_38]
0x14001ac88  test    ecx, ecx
0x14001ac8a  jz      loc_14001AD16
0x14001ac90  sub     ecx, 1
0x14001ac93  jz      short loc_14001AC9E
0x14001ac95  cmp     ecx, 1
0x14001ac98  jnz     loc_14001ADEE
0x14001ac9e  lea     r12, [rsi+r14]
0x14001aca2  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x14001aca6  mov     r15, rsi
0x14001aca9  cmp     rsi, r12
0x14001acac  jnb     loc_14001ADE4
0x14001acb2  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x14001acb6  movzx   eax, word ptr [r15]
0x14001acba  movzx   ecx, ax; Character
0x14001acbd  mov     [rbp+var_38], ax
0x14001acc1  call    _putwch_nolock
0x14001acc6  movzx   ecx, [rbp+var_38]
0x14001acca  cmp     ax, cx
0x14001accd  jnz     short loc_14001AD08
0x14001accf  add     r14d, 2
0x14001acd3  mov     [rbp+NumberOfBytesWritten+4], r14d
0x14001acd7  cmp     cx, 0Ah
0x14001acdb  jnz     short loc_14001ACFA
0x14001acdd  mov     ecx, 0Dh; Character
0x14001ace2  call    _putwch_nolock
0x14001ace7  mov     ecx, 0Dh
0x14001acec  cmp     ax, cx
0x14001acef  jnz     short loc_14001AD08
0x14001acf1  inc     r14d
0x14001acf4  mov     [rbp+NumberOfBytesWritten+4], r14d
0x14001acf8  inc     edi
0x14001acfa  add     r15, 2
0x14001acfe  cmp     r15, r12
0x14001ad01  jb      short loc_14001ACB6
0x14001ad03  jmp     loc_14001ADE4
0x14001ad08  call    cs:__imp_GetLastError
0x14001ad0e  mov     [rbp+NumberOfBytesWritten], eax
0x14001ad11  jmp     loc_14001ADE4
0x14001ad16  mov     r9d, r14d
0x14001ad19  mov     [rsp+68h+var_48], rbx
0x14001ad1e  mov     r8, rsi
0x14001ad21  lea     rcx, [rbp+NumberOfBytesWritten]
0x14001ad25  mov     edx, r13d
0x14001ad28  call    write_double_translated_ansi_nolock
0x14001ad2d  movsd   xmm0, qword ptr [rax]
0x14001ad31  mov     edi, [rax+8]
0x14001ad34  jmp     loc_14001ADE9
0x14001ad39  lea     r8, __pioinfo
0x14001ad40  mov     rcx, r13
0x14001ad43  mov     rax, r13
0x14001ad46  sar     rax, 6
0x14001ad4a  and     ecx, 3Fh
0x14001ad4d  mov     rdx, [r8+rax*8]
0x14001ad51  lea     rcx, [rcx+rcx*8]
0x14001ad55  cmp     [rdx+rcx*8+38h], dil
0x14001ad5a  jge     short loc_14001ADB1
0x14001ad5c  movsx   ecx, byte ptr [rbp+var_38]
0x14001ad60  test    ecx, ecx
0x14001ad62  jz      short loc_14001AD9A
0x14001ad64  sub     ecx, 1
0x14001ad67  jz      short loc_14001AD86
0x14001ad69  cmp     ecx, 1
0x14001ad6c  jnz     loc_14001ADF5
0x14001ad72  mov     r9d, r14d
0x14001ad75  lea     rcx, [rbp+NumberOfBytesWritten]
0x14001ad79  mov     r8, rsi
0x14001ad7c  mov     edx, r13d
0x14001ad7f  call    write_text_utf16le_nolock
0x14001ad84  jmp     short loc_14001AD2D
0x14001ad86  mov     r9d, r14d
0x14001ad89  lea     rcx, [rbp+NumberOfBytesWritten]
0x14001ad8d  mov     r8, rsi
0x14001ad90  mov     edx, r13d
0x14001ad93  call    write_text_utf8_nolock
0x14001ad98  jmp     short loc_14001AD2D
0x14001ad9a  mov     r9d, r14d
0x14001ad9d  lea     rcx, [rbp+NumberOfBytesWritten]
0x14001ada1  mov     r8, rsi
0x14001ada4  mov     edx, r13d
0x14001ada7  call    write_text_ansi_nolock
0x14001adac  jmp     loc_14001AD2D
0x14001adb1  mov     rcx, [rdx+rcx*8+28h]; hFile
0x14001adb6  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x14001adba  xor     eax, eax
0x14001adbc  mov     rdx, rsi; lpBuffer
0x14001adbf  and     [rsp+68h+var_48], rax
0x14001adc4  mov     r8d, r14d; nNumberOfBytesToWrite
0x14001adc7  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x14001adcb  mov     [rbp+var_28], eax
0x14001adce  call    cs:__imp_WriteFile
0x14001add4  test    eax, eax
0x14001add6  jnz     short loc_14001ADE1
0x14001add8  call    cs:__imp_GetLastError
0x14001adde  mov     [rbp+NumberOfBytesWritten], eax
0x14001ade1  mov     edi, [rbp+var_28]
0x14001ade4  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x14001ade9  movsd   [rbp+var_20], xmm0
0x14001adee  lea     r8, __pioinfo
0x14001adf5  mov     rax, [rbp+var_20]
0x14001adf9  shr     rax, 20h
0x14001adfd  test    eax, eax
0x14001adff  jnz     short loc_14001AE6D
0x14001ae01  mov     eax, dword ptr [rbp+var_20]
0x14001ae04  test    eax, eax
0x14001ae06  jz      short loc_14001AE34
0x14001ae08  cmp     eax, 5
0x14001ae0b  jnz     short loc_14001AE24
0x14001ae0d  mov     byte ptr [rbx+30h], 1
0x14001ae11  mov     dword ptr [rbx+2Ch], 9
0x14001ae18  mov     byte ptr [rbx+38h], 1
0x14001ae1c  mov     [rbx+34h], eax
0x14001ae1f  jmp     loc_14001ABB7
0x14001ae24  mov     ecx, dword ptr [rbp+var_20]
0x14001ae27  mov     rdx, rbx
0x14001ae2a  call    __acrt_errno_map_os_error_ptd
0x14001ae2f  jmp     loc_14001ABB7
0x14001ae34  mov     rcx, r13
0x14001ae37  mov     rax, r13
0x14001ae3a  sar     rax, 6
0x14001ae3e  and     ecx, 3Fh
0x14001ae41  mov     rax, [r8+rax*8]
0x14001ae45  lea     rcx, [rcx+rcx*8]
0x14001ae49  test    byte ptr [rax+rcx*8+38h], 40h
0x14001ae4e  jz      short loc_14001AE55
0x14001ae50  cmp     byte ptr [rsi], 1Ah
0x14001ae53  jz      short loc_14001AE74
0x14001ae55  and     dword ptr [rbx+34h], 0
0x14001ae59  mov     byte ptr [rbx+30h], 1
0x14001ae5d  mov     dword ptr [rbx+2Ch], 1Ch
0x14001ae64  mov     byte ptr [rbx+38h], 1
0x14001ae68  jmp     loc_14001ABB7
0x14001ae6d  mov     eax, dword ptr [rbp+var_20+4]
0x14001ae70  sub     eax, edi
0x14001ae72  jmp     short loc_14001AE76
0x14001ae74  xor     eax, eax
0x14001ae76  add     rsp, 68h
0x14001ae7a  pop     r15
0x14001ae7c  pop     r14
0x14001ae7e  pop     r13
0x14001ae80  pop     r12
0x14001ae82  pop     rdi
0x14001ae83  pop     rsi
0x14001ae84  pop     rbx
0x14001ae85  pop     rbp
0x14001ae86  retn
```
