# _write_nolock

- ea: `0x180038df8`
- end: `0x18003910a`
- name: `_write_nolock`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180038cd0`

## callees

- `0x180023930`
- `0x180023cbc`
- `0x180023f50`
- `0x180038418`
- `0x180038910`
- `0x180038a24`
- `0x180038b4c`
- `0x180038df8`
- `0x180039110`
- `0x18003acc8`
- `0x18003acd4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038fa5`
- `KERNEL32!GetLastError` at `0x180039062`
- `KERNEL32!GetLastError` at `0x180038fa5`
- `KERNEL32!GetLastError` at `0x180039062`
- `KERNEL32!WriteFile` at `0x180039058`
- `KERNEL32!WriteFile` at `0x180039058`
- `KERNEL32!GetConsoleMode` at `0x180038f20`
- `KERNEL32!GetConsoleMode` at `0x180038f20`

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
0x180038df8  push    rbp
0x180038dfa  push    rbx
0x180038dfb  push    rsi
0x180038dfc  push    rdi
0x180038dfd  push    r12
0x180038dff  push    r13
0x180038e01  push    r14
0x180038e03  push    r15
0x180038e05  mov     rbp, rsp
0x180038e08  sub     rsp, 78h
0x180038e0c  xor     r14d, r14d
0x180038e0f  mov     r12d, r8d
0x180038e12  movsxd  r15, ecx
0x180038e15  mov     rbx, r9
0x180038e18  mov     rsi, rdx
0x180038e1b  test    r8d, r8d
0x180038e1e  jz      loc_1800390F7
0x180038e24  test    rdx, rdx
0x180038e27  jnz     short loc_180038E60
0x180038e29  mov     byte ptr [r9+38h], 1
0x180038e2e  xor     r8d, r8d; FileName
0x180038e31  mov     [r9+34h], r14d
0x180038e35  xor     edx, edx; FunctionName
0x180038e37  mov     byte ptr [r9+30h], 1
0x180038e3c  xor     ecx, ecx; Expression
0x180038e3e  mov     dword ptr [r9+2Ch], 16h
0x180038e46  xor     r9d, r9d; LineNo
0x180038e49  mov     qword ptr [rsp+78h+dwErrCode], rbx; dwErrCode
0x180038e4e  mov     [rsp+78h+lpOverlapped], r14; uintptr_t
0x180038e53  call    _invalid_parameter_internal
0x180038e58  or      eax, 0FFFFFFFFh
0x180038e5b  jmp     loc_1800390F9
0x180038e60  mov     eax, r15d
0x180038e63  lea     rdx, __pioinfo
0x180038e6a  and     eax, 3Fh
0x180038e6d  mov     rcx, r15
0x180038e70  sar     rcx, 6
0x180038e74  mov     [rbp+var_40], rcx
0x180038e78  lea     r13, [rax+rax*8]
0x180038e7c  mov     rdx, [rdx+rcx*8]
0x180038e80  mov     al, [rdx+r13*8+39h]
0x180038e85  mov     byte ptr [rbp+var_48], al
0x180038e88  dec     al
0x180038e8a  cmp     al, 1
0x180038e8c  ja      short loc_180038E94
0x180038e8e  test    r12b, 1
0x180038e92  jnz     short loc_180038E29
0x180038e94  test    byte ptr [rdx+r13*8+38h], 20h
0x180038e9a  jz      short loc_180038EAA
0x180038e9c  xor     edx, edx
0x180038e9e  mov     ecx, r15d
0x180038ea1  lea     r8d, [rdx+2]
0x180038ea5  call    _lseeki64_nolock_internal
0x180038eaa  mov     ecx, r15d; FileHandle
0x180038ead  mov     qword ptr [rbp+var_38], r14
0x180038eb1  mov     edi, r14d
0x180038eb4  call    _isatty
0x180038eb9  mov     rdx, [rbp+var_40]
0x180038ebd  lea     r8, __pioinfo
0x180038ec4  test    eax, eax
0x180038ec6  jz      loc_180038FDE
0x180038ecc  mov     rax, [r8+rdx*8]
0x180038ed0  cmp     [rax+r13*8+38h], dil
0x180038ed5  jge     loc_180038FDE
0x180038edb  cmp     [rbx+28h], dil
0x180038edf  jnz     short loc_180038EF4
0x180038ee1  mov     rcx, rbx; this
0x180038ee4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180038ee9  mov     rdx, [rbp+var_40]
0x180038eed  lea     r8, __pioinfo
0x180038ef4  mov     rax, [rbx+18h]
0x180038ef8  cmp     [rax+138h], rdi
0x180038eff  jnz     short loc_180038F10
0x180038f01  mov     rax, [r8+rdx*8]
0x180038f05  cmp     [rax+r13*8+39h], dil
0x180038f0a  jz      loc_180038FDE
0x180038f10  mov     rcx, [r8+rdx*8]
0x180038f14  lea     rdx, [rbp+Mode]; lpMode
0x180038f18  mov     [rbp+Mode], edi
0x180038f1b  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x180038f20  call    cs:__imp_GetConsoleMode
0x180038f26  test    eax, eax
0x180038f28  jz      loc_180038FD3
0x180038f2e  movsx   ecx, byte ptr [rbp+var_48]
0x180038f32  test    ecx, ecx
0x180038f34  jz      short loc_180038FAF
0x180038f36  sub     ecx, 1
0x180038f39  jz      short loc_180038F44
0x180038f3b  cmp     ecx, 1
0x180038f3e  jnz     loc_18003907D
0x180038f44  xor     r15d, r15d
0x180038f47  add     r12, rsi
0x180038f4a  mov     rdi, rsi
0x180038f4d  cmp     rsi, r12
0x180038f50  jnb     short loc_180038F97
0x180038f52  movzx   eax, word ptr [rdi]
0x180038f55  movzx   ecx, ax; Character
0x180038f58  mov     [rbp+var_48], ax
0x180038f5c  call    _putwch_nolock
0x180038f61  movzx   ecx, [rbp+var_48]
0x180038f65  cmp     ax, cx
0x180038f68  jnz     short loc_180038FA5
0x180038f6a  add     r15d, 2
0x180038f6e  cmp     cx, 0Ah
0x180038f72  jnz     short loc_180038F8E
0x180038f74  mov     ecx, 0Dh; Character
0x180038f79  call    _putwch_nolock
0x180038f7e  mov     ecx, 0Dh
0x180038f83  cmp     ax, cx
0x180038f86  jnz     short loc_180038FA5
0x180038f88  inc     r15d
0x180038f8b  inc     r14d
0x180038f8e  add     rdi, 2
0x180038f92  cmp     rdi, r12
0x180038f95  jb      short loc_180038F52
0x180038f97  xor     edi, edi
0x180038f99  mov     [rbp+var_38], edi
0x180038f9c  mov     [rbp+var_38+4], r15d
0x180038fa0  jmp     loc_18003907D
0x180038fa5  call    cs:__imp_GetLastError
0x180038fab  mov     edi, eax
0x180038fad  jmp     short loc_180038F99
0x180038faf  mov     r9d, r12d
0x180038fb2  mov     [rsp+78h+lpOverlapped], rbx
0x180038fb7  mov     r8, rsi
0x180038fba  lea     rcx, [rbp+NumberOfBytesWritten]
0x180038fbe  mov     edx, r15d
0x180038fc1  call    write_double_translated_ansi_nolock
0x180038fc6  movsd   xmm0, qword ptr [rax]
0x180038fca  mov     r14d, [rax+8]
0x180038fce  jmp     loc_180039074
0x180038fd3  mov     rdx, [rbp+var_40]
0x180038fd7  lea     r8, __pioinfo
0x180038fde  mov     rcx, [r8+rdx*8]
0x180038fe2  cmp     [rcx+r13*8+38h], dil
0x180038fe7  jge     short loc_18003903B
0x180038fe9  movsx   ecx, byte ptr [rbp+var_48]
0x180038fed  test    ecx, ecx
0x180038fef  jz      short loc_180039027
0x180038ff1  sub     ecx, 1
0x180038ff4  jz      short loc_180039013
0x180038ff6  cmp     ecx, 1
0x180038ff9  jnz     loc_180039088
0x180038fff  mov     r9d, r12d
0x180039002  lea     rcx, [rbp+NumberOfBytesWritten]
0x180039006  mov     r8, rsi
0x180039009  mov     edx, r15d
0x18003900c  call    write_text_utf16le_nolock
0x180039011  jmp     short loc_180038FC6
0x180039013  mov     r9d, r12d
0x180039016  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003901a  mov     r8, rsi
0x18003901d  mov     edx, r15d
0x180039020  call    write_text_utf8_nolock
0x180039025  jmp     short loc_180038FC6
0x180039027  mov     r9d, r12d
0x18003902a  lea     rcx, [rbp+NumberOfBytesWritten]
0x18003902e  mov     r8, rsi
0x180039031  mov     edx, r15d
0x180039034  call    write_text_ansi_nolock
0x180039039  jmp     short loc_180038FC6
0x18003903b  mov     rcx, [rcx+r13*8+28h]; hFile
0x180039040  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x180039044  xor     eax, eax
0x180039046  mov     r8d, r12d; nNumberOfBytesToWrite
0x180039049  mov     rdx, rsi; lpBuffer
0x18003904c  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x180039050  mov     [rbp+var_20], eax
0x180039053  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180039058  call    cs:__imp_WriteFile
0x18003905e  test    eax, eax
0x180039060  jnz     short loc_18003906B
0x180039062  call    cs:__imp_GetLastError
0x180039068  mov     [rbp+NumberOfBytesWritten], eax
0x18003906b  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x180039070  mov     r14d, [rbp+var_20]
0x180039074  movd    edi, xmm0
0x180039078  movsd   qword ptr [rbp+var_38], xmm0
0x18003907d  mov     rdx, [rbp+var_40]
0x180039081  lea     r8, __pioinfo
0x180039088  mov     rax, qword ptr [rbp+var_38]
0x18003908c  shr     rax, 20h
0x180039090  test    eax, eax
0x180039092  jnz     short loc_1800390EF
0x180039094  test    edi, edi
0x180039096  jz      short loc_1800390C3
0x180039098  cmp     edi, 5
0x18003909b  jnz     short loc_1800390B4
0x18003909d  mov     byte ptr [rbx+30h], 1
0x1800390a1  mov     dword ptr [rbx+2Ch], 9
0x1800390a8  mov     byte ptr [rbx+38h], 1
0x1800390ac  mov     [rbx+34h], edi
0x1800390af  jmp     loc_180038E58
0x1800390b4  mov     rdx, rbx
0x1800390b7  mov     ecx, edi
0x1800390b9  call    __acrt_errno_map_os_error_ptd
0x1800390be  jmp     loc_180038E58
0x1800390c3  mov     rax, [r8+rdx*8]
0x1800390c7  test    byte ptr [rax+r13*8+38h], 40h
0x1800390cd  jz      short loc_1800390D4
0x1800390cf  cmp     byte ptr [rsi], 1Ah
0x1800390d2  jz      short loc_1800390F7
0x1800390d4  mov     byte ptr [rbx+30h], 1
0x1800390d8  mov     dword ptr [rbx+2Ch], 1Ch
0x1800390df  mov     byte ptr [rbx+38h], 1
0x1800390e3  mov     dword ptr [rbx+34h], 0
0x1800390ea  jmp     loc_180038E58
0x1800390ef  mov     eax, [rbp+var_38+4]
0x1800390f2  sub     eax, r14d
0x1800390f5  jmp     short loc_1800390F9
0x1800390f7  xor     eax, eax
0x1800390f9  add     rsp, 78h
0x1800390fd  pop     r15
0x1800390ff  pop     r14
0x180039101  pop     r13
0x180039103  pop     r12
0x180039105  pop     rdi
0x180039106  pop     rsi
0x180039107  pop     rbx
0x180039108  pop     rbp
0x180039109  retn
```
