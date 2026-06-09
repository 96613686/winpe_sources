# _write_nolock

- ea: `0x18003cd08`
- end: `0x18003d01a`
- name: `_write_nolock`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18003cbe0`

## callees

- `0x180027840`
- `0x180027bcc`
- `0x180027e60`
- `0x18003c328`
- `0x18003c820`
- `0x18003c934`
- `0x18003ca5c`
- `0x18003cd08`
- `0x18003d020`
- `0x18003ebd8`
- `0x18003ebe4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ceb5`
- `KERNEL32!GetLastError` at `0x18003cf72`
- `KERNEL32!GetLastError` at `0x18003ceb5`
- `KERNEL32!GetLastError` at `0x18003cf72`
- `KERNEL32!WriteFile` at `0x18003cf68`
- `KERNEL32!WriteFile` at `0x18003cf68`
- `KERNEL32!GetConsoleMode` at `0x18003ce30`
- `KERNEL32!GetConsoleMode` at `0x18003ce30`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, wchar_t *a2, unsigned int a3, __int64 dwErrCode)
{
  int v4; // r14d
  __int64 v5; // r12
  __int64 v10; // rax
  __int64 v11; // r13
  __int64 v12; // rdx
  DWORD LastError; // edi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int32 v17; // r15d
  wchar_t *v18; // r12
  wchar_t *v19; // rdi
  unsigned __int64 *v20; // rax
  __m128i v21; // xmm0
  __int64 v22; // rcx
  void *v23; // rcx
  char v24; // [rsp+30h] [rbp-48h]
  wchar_t v25; // [rsp+30h] [rbp-48h]
  __int64 v26; // [rsp+38h] [rbp-40h]
  __int32 v27; // [rsp+44h] [rbp-34h]
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-28h] BYREF
  int v29; // [rsp+58h] [rbp-20h]
  DWORD Mode[6]; // [rsp+60h] [rbp-18h] BYREF

  v4 = 0;
  v5 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v10 = a1 & 0x3F,
        v26 = (__int64)(int)a1 >> 6,
        v11 = 9 * v10,
        v12 = _pioinfo[v26],
        v24 = *(_BYTE *)(v12 + 72 * v10 + 57),
        (unsigned __int8)(v24 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, dwErrCode);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v12 + 72 * v10 + 56) & 0x20) != 0 )
    lseeki64_nolock_internal(a1, 0, 2);
  v27 = 0;
  LastError = 0;
  v14 = isatty(a1);
  v15 = v26;
  if ( v14 && *(char *)(_pioinfo[v26] + 8 * v11 + 56) < 0 )
  {
    if ( !*(_BYTE *)(dwErrCode + 40) )
    {
      __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)dwErrCode);
      v15 = v26;
    }
    if ( *(_QWORD *)(*(_QWORD *)(dwErrCode + 24) + 312LL) || *(_BYTE *)(_pioinfo[v15] + 8 * v11 + 57) )
    {
      v16 = _pioinfo[v15];
      Mode[0] = 0;
      if ( GetConsoleMode(*(HANDLE *)(v16 + 8 * v11 + 40), Mode) )
      {
        if ( v24 )
        {
          if ( (unsigned int)(v24 - 1) <= 1 )
          {
            v17 = 0;
            v18 = (wchar_t *)((char *)a2 + v5);
            v19 = a2;
            if ( a2 >= v18 )
            {
LABEL_24:
              LastError = 0;
            }
            else
            {
              while ( 1 )
              {
                v25 = *v19;
                if ( putwch_nolock(*v19) != v25 )
                  break;
                v17 += 2;
                if ( v25 == 10 )
                {
                  if ( putwch_nolock(0xDu) != 13 )
                    break;
                  ++v17;
                  ++v4;
                }
                if ( ++v19 >= v18 )
                  goto LABEL_24;
              }
              LastError = GetLastError();
            }
            v27 = v17;
          }
          goto LABEL_41;
        }
        v20 = (unsigned __int64 *)write_double_translated_ansi_nolock(
                                    (__int64)NumberOfBytesWritten,
                                    a1,
                                    a2,
                                    v5,
                                    dwErrCode);
        goto LABEL_28;
      }
      v15 = v26;
    }
  }
  v22 = _pioinfo[v15];
  if ( *(char *)(v22 + 8 * v11 + 56) >= 0 )
  {
    v23 = *(void **)(v22 + 8 * v11 + 40);
    *(_QWORD *)NumberOfBytesWritten = 0;
    v29 = 0;
    if ( !WriteFile(v23, a2, v5, &NumberOfBytesWritten[1], 0) )
      NumberOfBytesWritten[0] = GetLastError();
    v21 = (__m128i)*(unsigned __int64 *)NumberOfBytesWritten;
    v4 = v29;
    goto LABEL_40;
  }
  switch ( v24 )
  {
    case 0:
      v20 = (unsigned __int64 *)write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      goto LABEL_28;
    case 1:
      v20 = (unsigned __int64 *)write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      goto LABEL_28;
    case 2:
      v20 = (unsigned __int64 *)write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
LABEL_28:
      v21 = (__m128i)*v20;
      v4 = *((_DWORD *)v20 + 2);
LABEL_40:
      LastError = _mm_cvtsi128_si32(v21);
      v27 = v21.m128i_i32[1];
LABEL_41:
      v15 = v26;
      break;
  }
  if ( v27 )
    return (unsigned int)(v27 - v4);
  if ( LastError )
  {
    if ( LastError == 5 )
    {
      *(_BYTE *)(dwErrCode + 48) = 1;
      *(_DWORD *)(dwErrCode + 44) = 9;
      *(_BYTE *)(dwErrCode + 56) = 1;
      *(_DWORD *)(dwErrCode + 52) = 5;
    }
    else
    {
      _acrt_errno_map_os_error_ptd(LastError, dwErrCode, _pioinfo);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v15] + 8 * v11 + 56) & 0x40) == 0 || *(_BYTE *)a2 != 26 )
  {
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 28;
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x18003cd08  push    rbp
0x18003cd0a  push    rbx
0x18003cd0b  push    rsi
0x18003cd0c  push    rdi
0x18003cd0d  push    r12
0x18003cd0f  push    r13
0x18003cd11  push    r14
0x18003cd13  push    r15
0x18003cd15  mov     rbp, rsp
0x18003cd18  sub     rsp, 78h
0x18003cd1c  xor     r14d, r14d
0x18003cd1f  mov     r12d, r8d
0x18003cd22  movsxd  r15, ecx
0x18003cd25  mov     rbx, r9
0x18003cd28  mov     rsi, rdx
0x18003cd2b  test    r8d, r8d
0x18003cd2e  jz      loc_18003D007
0x18003cd34  test    rdx, rdx
0x18003cd37  jnz     short loc_18003CD70
0x18003cd39  mov     byte ptr [r9+38h], 1
0x18003cd3e  xor     r8d, r8d; FileName
0x18003cd41  mov     [r9+34h], r14d
0x18003cd45  xor     edx, edx; FunctionName
0x18003cd47  mov     byte ptr [r9+30h], 1
0x18003cd4c  xor     ecx, ecx; Expression
0x18003cd4e  mov     dword ptr [r9+2Ch], 16h
0x18003cd56  xor     r9d, r9d; LineNo
0x18003cd59  mov     qword ptr [rsp+78h+dwErrCode], rbx; dwErrCode
0x18003cd5e  mov     [rsp+78h+lpOverlapped], r14; uintptr_t
0x18003cd63  call    _invalid_parameter_internal
0x18003cd68  or      eax, 0FFFFFFFFh
0x18003cd6b  jmp     loc_18003D009
0x18003cd70  mov     eax, r15d
0x18003cd73  lea     rdx, __pioinfo
0x18003cd7a  and     eax, 3Fh
0x18003cd7d  mov     rcx, r15
0x18003cd80  sar     rcx, 6
0x18003cd84  mov     [rbp+var_40], rcx
0x18003cd88  lea     r13, [rax+rax*8]
0x18003cd8c  mov     rdx, [rdx+rcx*8]
0x18003cd90  mov     al, [rdx+r13*8+39h]
0x18003cd95  mov     byte ptr [rbp+var_48], al
0x18003cd98  dec     al
0x18003cd9a  cmp     al, 1
0x18003cd9c  ja      short loc_18003CDA4
0x18003cd9e  test    r12b, 1
0x18003cda2  jnz     short loc_18003CD39
0x18003cda4  test    byte ptr [rdx+r13*8+38h], 20h
0x18003cdaa  jz      short loc_18003CDBA
0x18003cdac  xor     edx, edx
0x18003cdae  mov     ecx, r15d
0x18003cdb1  lea     r8d, [rdx+2]
0x18003cdb5  call    _lseeki64_nolock_internal
0x18003cdba  mov     ecx, r15d; FileHandle
0x18003cdbd  mov     qword ptr [rbp+var_38], r14
0x18003cdc1  mov     edi, r14d
0x18003cdc4  call    _isatty
0x18003cdc9  mov     rdx, [rbp+var_40]
0x18003cdcd  lea     r8, __pioinfo
0x18003cdd4  test    eax, eax
0x18003cdd6  jz      loc_18003CEEE
0x18003cddc  mov     rax, [r8+rdx*8]
0x18003cde0  cmp     [rax+r13*8+38h], dil
0x18003cde5  jge     loc_18003CEEE
0x18003cdeb  cmp     [rbx+28h], dil
0x18003cdef  jnz     short loc_18003CE04
0x18003cdf1  mov     rcx, rbx; this
0x18003cdf4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18003cdf9  mov     rdx, [rbp+var_40]
0x18003cdfd  lea     r8, __pioinfo
0x18003ce04  mov     rax, [rbx+18h]
0x18003ce08  cmp     [rax+138h], rdi
0x18003ce0f  jnz     short loc_18003CE20
0x18003ce11  mov     rax, [r8+rdx*8]
0x18003ce15  cmp     [rax+r13*8+39h], dil
0x18003ce1a  jz      loc_18003CEEE
0x18003ce20  mov     rcx, [r8+rdx*8]
0x18003ce24  lea     rdx, [rbp+Mode]; lpMode
0x18003ce28  mov     [rbp+Mode], edi
0x18003ce2b  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x18003ce30  call    cs:__imp_GetConsoleMode
0x18003ce36  test    eax, eax
0x18003ce38  jz      loc_18003CEE3
0x18003ce3e  movsx   ecx, byte ptr [rbp+var_48]
0x18003ce42  test    ecx, ecx
0x18003ce44  jz      short loc_18003CEBF
0x18003ce46  sub     ecx, 1
0x18003ce49  jz      short loc_18003CE54
0x18003ce4b  cmp     ecx, 1
0x18003ce4e  jnz     loc_18003CF8D
0x18003ce54  xor     r15d, r15d
0x18003ce57  add     r12, rsi
0x18003ce5a  mov     rdi, rsi
0x18003ce5d  cmp     rsi, r12
0x18003ce60  jnb     short loc_18003CEA7
0x18003ce62  movzx   eax, word ptr [rdi]
0x18003ce65  movzx   ecx, ax; Character
0x18003ce68  mov     [rbp+var_48], ax
0x18003ce6c  call    _putwch_nolock
0x18003ce71  movzx   ecx, [rbp+var_48]
0x18003ce75  cmp     ax, cx
0x18003ce78  jnz     short loc_18003CEB5
0x18003ce7a  add     r15d, 2
0x18003ce7e  cmp     cx, 0Ah
0x18003ce82  jnz     short loc_18003CE9E
0x18003ce84  mov     ecx, 0Dh; Character
0x18003ce89  call    _putwch_nolock
0x18003ce8e  mov     ecx, 0Dh
0x18003ce93  cmp     ax, cx
0x18003ce96  jnz     short loc_18003CEB5
0x18003ce98  inc     r15d
0x18003ce9b  inc     r14d
0x18003ce9e  add     rdi, 2
0x18003cea2  cmp     rdi, r12
0x18003cea5  jb      short loc_18003CE62
0x18003cea7  xor     edi, edi
0x18003cea9  mov     [rbp+var_38], edi
0x18003ceac  mov     [rbp+var_38+4], r15d
0x18003ceb0  jmp     loc_18003CF8D
0x18003ceb5  call    cs:__imp_GetLastError
0x18003cebb  mov     edi, eax
0x18003cebd  jmp     short loc_18003CEA9
0x18003cebf  mov     r9d, r12d
0x18003cec2  mov     [rsp+78h+lpOverlapped], rbx
0x18003cec7  mov     r8, rsi
0x18003ceca  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003cece  mov     edx, r15d
0x18003ced1  call    write_double_translated_ansi_nolock
0x18003ced6  movsd   xmm0, qword ptr [rax]
0x18003ceda  mov     r14d, [rax+8]
0x18003cede  jmp     loc_18003CF84
0x18003cee3  mov     rdx, [rbp+var_40]
0x18003cee7  lea     r8, __pioinfo
0x18003ceee  mov     rcx, [r8+rdx*8]
0x18003cef2  cmp     [rcx+r13*8+38h], dil
0x18003cef7  jge     short loc_18003CF4B
0x18003cef9  movsx   ecx, byte ptr [rbp+var_48]
0x18003cefd  test    ecx, ecx
0x18003ceff  jz      short loc_18003CF37
0x18003cf01  sub     ecx, 1
0x18003cf04  jz      short loc_18003CF23
0x18003cf06  cmp     ecx, 1
0x18003cf09  jnz     loc_18003CF98
0x18003cf0f  mov     r9d, r12d
0x18003cf12  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003cf16  mov     r8, rsi
0x18003cf19  mov     edx, r15d
0x18003cf1c  call    write_text_utf16le_nolock
0x18003cf21  jmp     short loc_18003CED6
0x18003cf23  mov     r9d, r12d
0x18003cf26  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003cf2a  mov     r8, rsi
0x18003cf2d  mov     edx, r15d
0x18003cf30  call    write_text_utf8_nolock
0x18003cf35  jmp     short loc_18003CED6
0x18003cf37  mov     r9d, r12d
0x18003cf3a  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003cf3e  mov     r8, rsi
0x18003cf41  mov     edx, r15d
0x18003cf44  call    write_text_ansi_nolock
0x18003cf49  jmp     short loc_18003CED6
0x18003cf4b  mov     rcx, [rcx+r13*8+28h]; hFile
0x18003cf50  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18003cf54  xor     eax, eax
0x18003cf56  mov     r8d, r12d; nNumberOfBytesToWrite
0x18003cf59  mov     rdx, rsi; lpBuffer
0x18003cf5c  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x18003cf60  mov     [rbp+var_20], eax
0x18003cf63  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18003cf68  call    cs:__imp_WriteFile
0x18003cf6e  test    eax, eax
0x18003cf70  jnz     short loc_18003CF7B
0x18003cf72  call    cs:__imp_GetLastError
0x18003cf78  mov     [rbp+NumberOfBytesWritten], eax
0x18003cf7b  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18003cf80  mov     r14d, [rbp+var_20]
0x18003cf84  movd    edi, xmm0
0x18003cf88  movsd   qword ptr [rbp+var_38], xmm0
0x18003cf8d  mov     rdx, [rbp+var_40]
0x18003cf91  lea     r8, __pioinfo
0x18003cf98  mov     rax, qword ptr [rbp+var_38]
0x18003cf9c  shr     rax, 20h
0x18003cfa0  test    eax, eax
0x18003cfa2  jnz     short loc_18003CFFF
0x18003cfa4  test    edi, edi
0x18003cfa6  jz      short loc_18003CFD3
0x18003cfa8  cmp     edi, 5
0x18003cfab  jnz     short loc_18003CFC4
0x18003cfad  mov     byte ptr [rbx+30h], 1
0x18003cfb1  mov     dword ptr [rbx+2Ch], 9
0x18003cfb8  mov     byte ptr [rbx+38h], 1
0x18003cfbc  mov     [rbx+34h], edi
0x18003cfbf  jmp     loc_18003CD68
0x18003cfc4  mov     rdx, rbx
0x18003cfc7  mov     ecx, edi
0x18003cfc9  call    __acrt_errno_map_os_error_ptd
0x18003cfce  jmp     loc_18003CD68
0x18003cfd3  mov     rax, [r8+rdx*8]
0x18003cfd7  test    byte ptr [rax+r13*8+38h], 40h
0x18003cfdd  jz      short loc_18003CFE4
0x18003cfdf  cmp     byte ptr [rsi], 1Ah
0x18003cfe2  jz      short loc_18003D007
0x18003cfe4  mov     byte ptr [rbx+30h], 1
0x18003cfe8  mov     dword ptr [rbx+2Ch], 1Ch
0x18003cfef  mov     byte ptr [rbx+38h], 1
0x18003cff3  mov     dword ptr [rbx+34h], 0
0x18003cffa  jmp     loc_18003CD68
0x18003cfff  mov     eax, [rbp+var_38+4]
0x18003d002  sub     eax, r14d
0x18003d005  jmp     short loc_18003D009
0x18003d007  xor     eax, eax
0x18003d009  add     rsp, 78h
0x18003d00d  pop     r15
0x18003d00f  pop     r14
0x18003d011  pop     r13
0x18003d013  pop     r12
0x18003d015  pop     rdi
0x18003d016  pop     rsi
0x18003d017  pop     rbx
0x18003d018  pop     rbp
0x18003d019  retn
```
