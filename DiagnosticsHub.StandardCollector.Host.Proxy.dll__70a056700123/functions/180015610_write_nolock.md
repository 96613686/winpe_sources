# _write_nolock

- ea: `0x180015610`
- end: `0x18001593f`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x1800154f0`

## callees

- `0x1800073e8`
- `0x180007740`
- `0x1800149cc`
- `0x180014ab0`
- `0x180015084`
- `0x18001518c`
- `0x1800152a8`
- `0x180015610`
- `0x180015ac4`
- `0x18001b184`
- `0x18001c098`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x18001572e`
- `KERNEL32!GetConsoleMode` at `0x18001572e`
- `KERNEL32!WriteFile` at `0x180015886`
- `KERNEL32!WriteFile` at `0x180015886`
- `KERNEL32!GetLastError` at `0x1800157c0`
- `KERNEL32!GetLastError` at `0x180015890`
- `KERNEL32!GetLastError` at `0x1800157c0`
- `KERNEL32!GetLastError` at `0x180015890`

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
      _acrt_errno_map_os_error_ptd((unsigned int)v25, a4);
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
0x180015610  push    rbp
0x180015612  push    rbx
0x180015613  push    rsi
0x180015614  push    rdi
0x180015615  push    r12
0x180015617  push    r13
0x180015619  push    r14
0x18001561b  push    r15
0x18001561d  mov     rbp, rsp
0x180015620  sub     rsp, 68h
0x180015624  xor     edi, edi
0x180015626  mov     r14d, r8d
0x180015629  movsxd  r13, ecx
0x18001562c  mov     rbx, r9
0x18001562f  mov     rsi, rdx
0x180015632  test    r8d, r8d
0x180015635  jz      loc_18001592C
0x18001563b  test    rdx, rdx
0x18001563e  jnz     short loc_180015677
0x180015640  mov     byte ptr [r9+38h], 1
0x180015645  xor     r8d, r8d; FileName
0x180015648  mov     [r9+34h], edi
0x18001564c  xor     edx, edx; FunctionName
0x18001564e  mov     byte ptr [r9+30h], 1
0x180015653  xor     ecx, ecx; Expression
0x180015655  mov     dword ptr [r9+2Ch], 16h
0x18001565d  xor     r9d, r9d; LineNo
0x180015660  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x180015665  mov     [rsp+68h+var_48], rdi; uintptr_t
0x18001566a  call    _invalid_parameter_internal
0x18001566f  or      eax, 0FFFFFFFFh
0x180015672  jmp     loc_18001592E
0x180015677  mov     rax, r13
0x18001567a  lea     rcx, __pioinfo
0x180015681  and     eax, 3Fh
0x180015684  mov     r12, r13
0x180015687  sar     r12, 6
0x18001568b  lea     r15, [rax+rax*8]
0x18001568f  mov     rcx, [rcx+r12*8]
0x180015693  mov     al, [rcx+r15*8+39h]
0x180015698  mov     byte ptr [rbp+var_38], al
0x18001569b  dec     al
0x18001569d  cmp     al, 1
0x18001569f  ja      short loc_1800156AA
0x1800156a1  mov     eax, r14d
0x1800156a4  not     eax
0x1800156a6  test    al, 1
0x1800156a8  jz      short loc_180015640
0x1800156aa  test    byte ptr [rcx+r15*8+38h], 20h
0x1800156b0  jz      short loc_1800156C0
0x1800156b2  xor     edx, edx
0x1800156b4  mov     ecx, r13d
0x1800156b7  lea     r8d, [rdx+2]
0x1800156bb  call    _lseeki64_nolock_internal
0x1800156c0  mov     ecx, r13d; FileHandle
0x1800156c3  mov     [rbp+var_20], rdi
0x1800156c7  call    _isatty
0x1800156cc  xor     ecx, ecx
0x1800156ce  lea     r8, __pioinfo
0x1800156d5  test    eax, eax
0x1800156d7  jz      loc_1800157F8
0x1800156dd  mov     rax, [r8+r12*8]
0x1800156e1  cmp     [rax+r15*8+38h], cl
0x1800156e6  jge     loc_1800157F8
0x1800156ec  cmp     [rbx+28h], cl
0x1800156ef  jnz     short loc_180015702
0x1800156f1  mov     rcx, rbx; this
0x1800156f4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800156f9  xor     ecx, ecx
0x1800156fb  lea     r8, __pioinfo
0x180015702  mov     rax, [rbx+18h]
0x180015706  cmp     [rax+138h], rcx
0x18001570d  jnz     short loc_18001571E
0x18001570f  mov     rax, [r8+r12*8]
0x180015713  cmp     [rax+r15*8+39h], cl
0x180015718  jz      loc_1800157F8
0x18001571e  mov     [rbp+Mode], ecx
0x180015721  lea     rdx, [rbp+Mode]; lpMode
0x180015725  mov     rcx, [r8+r12*8]
0x180015729  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x18001572e  call    cs:__imp_GetConsoleMode
0x180015734  test    eax, eax
0x180015736  jz      loc_1800157F1
0x18001573c  movsx   ecx, byte ptr [rbp+var_38]
0x180015740  test    ecx, ecx
0x180015742  jz      loc_1800157CE
0x180015748  sub     ecx, 1
0x18001574b  jz      short loc_180015756
0x18001574d  cmp     ecx, 1
0x180015750  jnz     loc_1800158A6
0x180015756  lea     r12, [rsi+r14]
0x18001575a  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x18001575e  mov     r15, rsi
0x180015761  cmp     rsi, r12
0x180015764  jnb     loc_18001589C
0x18001576a  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x18001576e  movzx   eax, word ptr [r15]
0x180015772  movzx   ecx, ax; Character
0x180015775  mov     [rbp+var_38], ax
0x180015779  call    _putwch_nolock
0x18001577e  movzx   ecx, [rbp+var_38]
0x180015782  cmp     ax, cx
0x180015785  jnz     short loc_1800157C0
0x180015787  add     r14d, 2
0x18001578b  mov     [rbp+NumberOfBytesWritten+4], r14d
0x18001578f  cmp     cx, 0Ah
0x180015793  jnz     short loc_1800157B2
0x180015795  mov     ecx, 0Dh; Character
0x18001579a  call    _putwch_nolock
0x18001579f  mov     ecx, 0Dh
0x1800157a4  cmp     ax, cx
0x1800157a7  jnz     short loc_1800157C0
0x1800157a9  inc     r14d
0x1800157ac  mov     [rbp+NumberOfBytesWritten+4], r14d
0x1800157b0  inc     edi
0x1800157b2  add     r15, 2
0x1800157b6  cmp     r15, r12
0x1800157b9  jb      short loc_18001576E
0x1800157bb  jmp     loc_18001589C
0x1800157c0  call    cs:__imp_GetLastError
0x1800157c6  mov     [rbp+NumberOfBytesWritten], eax
0x1800157c9  jmp     loc_18001589C
0x1800157ce  mov     r9d, r14d
0x1800157d1  mov     [rsp+68h+var_48], rbx
0x1800157d6  mov     r8, rsi
0x1800157d9  lea     rcx, [rbp+NumberOfBytesWritten]
0x1800157dd  mov     edx, r13d
0x1800157e0  call    write_double_translated_ansi_nolock
0x1800157e5  movsd   xmm0, qword ptr [rax]
0x1800157e9  mov     edi, [rax+8]
0x1800157ec  jmp     loc_1800158A1
0x1800157f1  lea     r8, __pioinfo
0x1800157f8  mov     rcx, r13
0x1800157fb  mov     rax, r13
0x1800157fe  sar     rax, 6
0x180015802  and     ecx, 3Fh
0x180015805  mov     rdx, [r8+rax*8]
0x180015809  lea     rcx, [rcx+rcx*8]
0x18001580d  cmp     [rdx+rcx*8+38h], dil
0x180015812  jge     short loc_180015869
0x180015814  movsx   ecx, byte ptr [rbp+var_38]
0x180015818  test    ecx, ecx
0x18001581a  jz      short loc_180015852
0x18001581c  sub     ecx, 1
0x18001581f  jz      short loc_18001583E
0x180015821  cmp     ecx, 1
0x180015824  jnz     loc_1800158AD
0x18001582a  mov     r9d, r14d
0x18001582d  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015831  mov     r8, rsi
0x180015834  mov     edx, r13d
0x180015837  call    write_text_utf16le_nolock
0x18001583c  jmp     short loc_1800157E5
0x18001583e  mov     r9d, r14d
0x180015841  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015845  mov     r8, rsi
0x180015848  mov     edx, r13d
0x18001584b  call    write_text_utf8_nolock
0x180015850  jmp     short loc_1800157E5
0x180015852  mov     r9d, r14d
0x180015855  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015859  mov     r8, rsi
0x18001585c  mov     edx, r13d
0x18001585f  call    write_text_ansi_nolock
0x180015864  jmp     loc_1800157E5
0x180015869  mov     rcx, [rdx+rcx*8+28h]; hFile
0x18001586e  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x180015872  xor     eax, eax
0x180015874  mov     rdx, rsi; lpBuffer
0x180015877  and     [rsp+68h+var_48], rax
0x18001587c  mov     r8d, r14d; nNumberOfBytesToWrite
0x18001587f  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x180015883  mov     [rbp+var_28], eax
0x180015886  call    cs:__imp_WriteFile
0x18001588c  test    eax, eax
0x18001588e  jnz     short loc_180015899
0x180015890  call    cs:__imp_GetLastError
0x180015896  mov     [rbp+NumberOfBytesWritten], eax
0x180015899  mov     edi, [rbp+var_28]
0x18001589c  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x1800158a1  movsd   [rbp+var_20], xmm0
0x1800158a6  lea     r8, __pioinfo
0x1800158ad  mov     rax, [rbp+var_20]
0x1800158b1  shr     rax, 20h
0x1800158b5  test    eax, eax
0x1800158b7  jnz     short loc_180015925
0x1800158b9  mov     eax, dword ptr [rbp+var_20]
0x1800158bc  test    eax, eax
0x1800158be  jz      short loc_1800158EC
0x1800158c0  cmp     eax, 5
0x1800158c3  jnz     short loc_1800158DC
0x1800158c5  mov     byte ptr [rbx+30h], 1
0x1800158c9  mov     dword ptr [rbx+2Ch], 9
0x1800158d0  mov     byte ptr [rbx+38h], 1
0x1800158d4  mov     [rbx+34h], eax
0x1800158d7  jmp     loc_18001566F
0x1800158dc  mov     ecx, dword ptr [rbp+var_20]
0x1800158df  mov     rdx, rbx
0x1800158e2  call    __acrt_errno_map_os_error_ptd
0x1800158e7  jmp     loc_18001566F
0x1800158ec  mov     rcx, r13
0x1800158ef  mov     rax, r13
0x1800158f2  sar     rax, 6
0x1800158f6  and     ecx, 3Fh
0x1800158f9  mov     rax, [r8+rax*8]
0x1800158fd  lea     rcx, [rcx+rcx*8]
0x180015901  test    byte ptr [rax+rcx*8+38h], 40h
0x180015906  jz      short loc_18001590D
0x180015908  cmp     byte ptr [rsi], 1Ah
0x18001590b  jz      short loc_18001592C
0x18001590d  and     dword ptr [rbx+34h], 0
0x180015911  mov     byte ptr [rbx+30h], 1
0x180015915  mov     dword ptr [rbx+2Ch], 1Ch
0x18001591c  mov     byte ptr [rbx+38h], 1
0x180015920  jmp     loc_18001566F
0x180015925  mov     eax, dword ptr [rbp+var_20+4]
0x180015928  sub     eax, edi
0x18001592a  jmp     short loc_18001592E
0x18001592c  xor     eax, eax
0x18001592e  add     rsp, 68h
0x180015932  pop     r15
0x180015934  pop     r14
0x180015936  pop     r13
0x180015938  pop     r12
0x18001593a  pop     rdi
0x18001593b  pop     rsi
0x18001593c  pop     rbx
0x18001593d  pop     rbp
0x18001593e  retn
```
