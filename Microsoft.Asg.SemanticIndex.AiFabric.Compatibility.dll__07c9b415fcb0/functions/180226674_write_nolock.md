# _write_nolock

- ea: `0x180226674`
- end: `0x1802269a3`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180226554`

## callees

- `0x180206de4`
- `0x180207000`
- `0x18020b7f0`
- `0x1802250dc`
- `0x180225d28`
- `0x1802261bc`
- `0x1802262c4`
- `0x1802263e0`
- `0x180226674`
- `0x180226a54`
- `0x1802285ec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180226824`
- `KERNEL32!GetLastError` at `0x1802268f4`
- `KERNEL32!GetLastError` at `0x180226824`
- `KERNEL32!GetLastError` at `0x1802268f4`
- `KERNEL32!GetConsoleMode` at `0x180226792`
- `KERNEL32!GetConsoleMode` at `0x180226792`
- `KERNEL32!WriteFile` at `0x1802268ea`
- `KERNEL32!WriteFile` at `0x1802268ea`

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
0x180226674  push    rbp
0x180226676  push    rbx
0x180226677  push    rsi
0x180226678  push    rdi
0x180226679  push    r12
0x18022667b  push    r13
0x18022667d  push    r14
0x18022667f  push    r15
0x180226681  mov     rbp, rsp
0x180226684  sub     rsp, 68h
0x180226688  xor     edi, edi
0x18022668a  mov     r14d, r8d
0x18022668d  movsxd  r13, ecx
0x180226690  mov     rbx, r9
0x180226693  mov     rsi, rdx
0x180226696  test    r8d, r8d
0x180226699  jz      loc_180226990
0x18022669f  test    rdx, rdx
0x1802266a2  jnz     short loc_1802266DB
0x1802266a4  mov     byte ptr [r9+38h], 1
0x1802266a9  xor     r8d, r8d; FileName
0x1802266ac  mov     [r9+34h], edi
0x1802266b0  xor     edx, edx; FunctionName
0x1802266b2  mov     byte ptr [r9+30h], 1
0x1802266b7  xor     ecx, ecx; Expression
0x1802266b9  mov     dword ptr [r9+2Ch], 16h
0x1802266c1  xor     r9d, r9d; LineNo
0x1802266c4  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x1802266c9  mov     [rsp+68h+var_48], rdi; uintptr_t
0x1802266ce  call    _invalid_parameter_internal
0x1802266d3  or      eax, 0FFFFFFFFh
0x1802266d6  jmp     loc_180226992
0x1802266db  mov     rax, r13
0x1802266de  lea     rcx, __pioinfo
0x1802266e5  and     eax, 3Fh
0x1802266e8  mov     r12, r13
0x1802266eb  sar     r12, 6
0x1802266ef  lea     r15, [rax+rax*8]
0x1802266f3  mov     rcx, [rcx+r12*8]
0x1802266f7  mov     al, [rcx+r15*8+39h]
0x1802266fc  mov     byte ptr [rbp+var_38], al
0x1802266ff  dec     al
0x180226701  cmp     al, 1
0x180226703  ja      short loc_18022670E
0x180226705  mov     eax, r14d
0x180226708  not     eax
0x18022670a  test    al, 1
0x18022670c  jz      short loc_1802266A4
0x18022670e  test    byte ptr [rcx+r15*8+38h], 20h
0x180226714  jz      short loc_180226724
0x180226716  xor     edx, edx
0x180226718  mov     ecx, r13d
0x18022671b  lea     r8d, [rdx+2]
0x18022671f  call    _lseeki64_nolock_internal
0x180226724  mov     ecx, r13d; FileHandle
0x180226727  mov     [rbp+var_20], rdi
0x18022672b  call    _isatty
0x180226730  xor     ecx, ecx
0x180226732  lea     r8, __pioinfo
0x180226739  test    eax, eax
0x18022673b  jz      loc_18022685C
0x180226741  mov     rax, [r8+r12*8]
0x180226745  cmp     [rax+r15*8+38h], cl
0x18022674a  jge     loc_18022685C
0x180226750  cmp     [rbx+28h], cl
0x180226753  jnz     short loc_180226766
0x180226755  mov     rcx, rbx; this
0x180226758  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18022675d  xor     ecx, ecx
0x18022675f  lea     r8, __pioinfo
0x180226766  mov     rax, [rbx+18h]
0x18022676a  cmp     [rax+138h], rcx
0x180226771  jnz     short loc_180226782
0x180226773  mov     rax, [r8+r12*8]
0x180226777  cmp     [rax+r15*8+39h], cl
0x18022677c  jz      loc_18022685C
0x180226782  mov     [rbp+Mode], ecx
0x180226785  lea     rdx, [rbp+Mode]; lpMode
0x180226789  mov     rcx, [r8+r12*8]
0x18022678d  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x180226792  call    cs:__imp_GetConsoleMode
0x180226798  test    eax, eax
0x18022679a  jz      loc_180226855
0x1802267a0  movsx   ecx, byte ptr [rbp+var_38]
0x1802267a4  test    ecx, ecx
0x1802267a6  jz      loc_180226832
0x1802267ac  sub     ecx, 1
0x1802267af  jz      short loc_1802267BA
0x1802267b1  cmp     ecx, 1
0x1802267b4  jnz     loc_18022690A
0x1802267ba  lea     r12, [rsi+r14]
0x1802267be  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x1802267c2  mov     r15, rsi
0x1802267c5  cmp     rsi, r12
0x1802267c8  jnb     loc_180226900
0x1802267ce  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x1802267d2  movzx   eax, word ptr [r15]
0x1802267d6  movzx   ecx, ax; Character
0x1802267d9  mov     [rbp+var_38], ax
0x1802267dd  call    _putwch_nolock
0x1802267e2  movzx   ecx, [rbp+var_38]
0x1802267e6  cmp     ax, cx
0x1802267e9  jnz     short loc_180226824
0x1802267eb  add     r14d, 2
0x1802267ef  mov     [rbp+NumberOfBytesWritten+4], r14d
0x1802267f3  cmp     cx, 0Ah
0x1802267f7  jnz     short loc_180226816
0x1802267f9  mov     ecx, 0Dh; Character
0x1802267fe  call    _putwch_nolock
0x180226803  mov     ecx, 0Dh
0x180226808  cmp     ax, cx
0x18022680b  jnz     short loc_180226824
0x18022680d  inc     r14d
0x180226810  mov     [rbp+NumberOfBytesWritten+4], r14d
0x180226814  inc     edi
0x180226816  add     r15, 2
0x18022681a  cmp     r15, r12
0x18022681d  jb      short loc_1802267D2
0x18022681f  jmp     loc_180226900
0x180226824  call    cs:__imp_GetLastError
0x18022682a  mov     [rbp+NumberOfBytesWritten], eax
0x18022682d  jmp     loc_180226900
0x180226832  mov     r9d, r14d
0x180226835  mov     [rsp+68h+var_48], rbx
0x18022683a  mov     r8, rsi
0x18022683d  lea     rcx, [rbp+NumberOfBytesWritten]
0x180226841  mov     edx, r13d
0x180226844  call    write_double_translated_ansi_nolock
0x180226849  movsd   xmm0, qword ptr [rax]
0x18022684d  mov     edi, [rax+8]
0x180226850  jmp     loc_180226905
0x180226855  lea     r8, __pioinfo
0x18022685c  mov     rcx, r13
0x18022685f  mov     rax, r13
0x180226862  sar     rax, 6
0x180226866  and     ecx, 3Fh
0x180226869  mov     rdx, [r8+rax*8]
0x18022686d  lea     rcx, [rcx+rcx*8]
0x180226871  cmp     [rdx+rcx*8+38h], dil
0x180226876  jge     short loc_1802268CD
0x180226878  movsx   ecx, byte ptr [rbp+var_38]
0x18022687c  test    ecx, ecx
0x18022687e  jz      short loc_1802268B6
0x180226880  sub     ecx, 1
0x180226883  jz      short loc_1802268A2
0x180226885  cmp     ecx, 1
0x180226888  jnz     loc_180226911
0x18022688e  mov     r9d, r14d
0x180226891  lea     rcx, [rbp+NumberOfBytesWritten]
0x180226895  mov     r8, rsi
0x180226898  mov     edx, r13d
0x18022689b  call    write_text_utf16le_nolock
0x1802268a0  jmp     short loc_180226849
0x1802268a2  mov     r9d, r14d
0x1802268a5  lea     rcx, [rbp+NumberOfBytesWritten]
0x1802268a9  mov     r8, rsi
0x1802268ac  mov     edx, r13d
0x1802268af  call    write_text_utf8_nolock
0x1802268b4  jmp     short loc_180226849
0x1802268b6  mov     r9d, r14d
0x1802268b9  lea     rcx, [rbp+NumberOfBytesWritten]
0x1802268bd  mov     r8, rsi
0x1802268c0  mov     edx, r13d
0x1802268c3  call    write_text_ansi_nolock
0x1802268c8  jmp     loc_180226849
0x1802268cd  mov     rcx, [rdx+rcx*8+28h]; hFile
0x1802268d2  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x1802268d6  xor     eax, eax
0x1802268d8  mov     rdx, rsi; lpBuffer
0x1802268db  and     [rsp+68h+var_48], rax
0x1802268e0  mov     r8d, r14d; nNumberOfBytesToWrite
0x1802268e3  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x1802268e7  mov     [rbp+var_28], eax
0x1802268ea  call    cs:__imp_WriteFile
0x1802268f0  test    eax, eax
0x1802268f2  jnz     short loc_1802268FD
0x1802268f4  call    cs:__imp_GetLastError
0x1802268fa  mov     [rbp+NumberOfBytesWritten], eax
0x1802268fd  mov     edi, [rbp+var_28]
0x180226900  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x180226905  movsd   [rbp+var_20], xmm0
0x18022690a  lea     r8, __pioinfo
0x180226911  mov     rax, [rbp+var_20]
0x180226915  shr     rax, 20h
0x180226919  test    eax, eax
0x18022691b  jnz     short loc_180226989
0x18022691d  mov     eax, dword ptr [rbp+var_20]
0x180226920  test    eax, eax
0x180226922  jz      short loc_180226950
0x180226924  cmp     eax, 5
0x180226927  jnz     short loc_180226940
0x180226929  mov     byte ptr [rbx+30h], 1
0x18022692d  mov     dword ptr [rbx+2Ch], 9
0x180226934  mov     byte ptr [rbx+38h], 1
0x180226938  mov     [rbx+34h], eax
0x18022693b  jmp     loc_1802266D3
0x180226940  mov     ecx, dword ptr [rbp+var_20]
0x180226943  mov     rdx, rbx
0x180226946  call    __acrt_errno_map_os_error_ptd
0x18022694b  jmp     loc_1802266D3
0x180226950  mov     rcx, r13
0x180226953  mov     rax, r13
0x180226956  sar     rax, 6
0x18022695a  and     ecx, 3Fh
0x18022695d  mov     rax, [r8+rax*8]
0x180226961  lea     rcx, [rcx+rcx*8]
0x180226965  test    byte ptr [rax+rcx*8+38h], 40h
0x18022696a  jz      short loc_180226971
0x18022696c  cmp     byte ptr [rsi], 1Ah
0x18022696f  jz      short loc_180226990
0x180226971  and     dword ptr [rbx+34h], 0
0x180226975  mov     byte ptr [rbx+30h], 1
0x180226979  mov     dword ptr [rbx+2Ch], 1Ch
0x180226980  mov     byte ptr [rbx+38h], 1
0x180226984  jmp     loc_1802266D3
0x180226989  mov     eax, dword ptr [rbp+var_20+4]
0x18022698c  sub     eax, edi
0x18022698e  jmp     short loc_180226992
0x180226990  xor     eax, eax
0x180226992  add     rsp, 68h
0x180226996  pop     r15
0x180226998  pop     r14
0x18022699a  pop     r13
0x18022699c  pop     r12
0x18022699e  pop     rdi
0x18022699f  pop     rsi
0x1802269a0  pop     rbx
0x1802269a1  pop     rbp
0x1802269a2  retn
```
