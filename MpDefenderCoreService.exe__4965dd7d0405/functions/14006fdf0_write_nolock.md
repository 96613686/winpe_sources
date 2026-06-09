# _write_nolock

- ea: `0x14006fdf0`
- end: `0x14007011f`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x14006fcd0`
- `0x140077a64`

## callees

- `0x14004dd00`
- `0x14004f744`
- `0x14005afb4`
- `0x14006f40c`
- `0x14006f8a0`
- `0x14006f9a8`
- `0x14006fac4`
- `0x14006fdf0`
- `0x1400719d0`
- `0x140075694`
- `0x140075e70`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140070066`
- `KERNEL32!WriteFile` at `0x140070066`
- `KERNEL32!GetLastError` at `0x14006ffa0`
- `KERNEL32!GetLastError` at `0x140070070`
- `KERNEL32!GetLastError` at `0x14006ffa0`
- `KERNEL32!GetLastError` at `0x140070070`
- `KERNEL32!GetConsoleMode` at `0x14006ff0e`
- `KERNEL32!GetConsoleMode` at `0x14006ff0e`

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
0x14006fdf0  push    rbp
0x14006fdf2  push    rbx
0x14006fdf3  push    rsi
0x14006fdf4  push    rdi
0x14006fdf5  push    r12
0x14006fdf7  push    r13
0x14006fdf9  push    r14
0x14006fdfb  push    r15
0x14006fdfd  mov     rbp, rsp
0x14006fe00  sub     rsp, 68h
0x14006fe04  xor     edi, edi
0x14006fe06  mov     r14d, r8d
0x14006fe09  movsxd  r13, ecx
0x14006fe0c  mov     rbx, r9
0x14006fe0f  mov     rsi, rdx
0x14006fe12  test    r8d, r8d
0x14006fe15  jz      loc_14007010C
0x14006fe1b  test    rdx, rdx
0x14006fe1e  jnz     short loc_14006FE57
0x14006fe20  mov     byte ptr [r9+38h], 1
0x14006fe25  xor     r8d, r8d; FileName
0x14006fe28  mov     [r9+34h], edi
0x14006fe2c  xor     edx, edx; FunctionName
0x14006fe2e  mov     byte ptr [r9+30h], 1
0x14006fe33  xor     ecx, ecx; Expression
0x14006fe35  mov     dword ptr [r9+2Ch], 16h
0x14006fe3d  xor     r9d, r9d; LineNo
0x14006fe40  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x14006fe45  mov     [rsp+68h+var_48], rdi; uintptr_t
0x14006fe4a  call    _invalid_parameter_internal
0x14006fe4f  or      eax, 0FFFFFFFFh
0x14006fe52  jmp     loc_14007010E
0x14006fe57  mov     rax, r13
0x14006fe5a  lea     rcx, __pioinfo
0x14006fe61  and     eax, 3Fh
0x14006fe64  mov     r12, r13
0x14006fe67  sar     r12, 6
0x14006fe6b  lea     r15, [rax+rax*8]
0x14006fe6f  mov     rcx, [rcx+r12*8]
0x14006fe73  mov     al, [rcx+r15*8+39h]
0x14006fe78  mov     byte ptr [rbp+var_38], al
0x14006fe7b  dec     al
0x14006fe7d  cmp     al, 1
0x14006fe7f  ja      short loc_14006FE8A
0x14006fe81  mov     eax, r14d
0x14006fe84  not     eax
0x14006fe86  test    al, 1
0x14006fe88  jz      short loc_14006FE20
0x14006fe8a  test    byte ptr [rcx+r15*8+38h], 20h
0x14006fe90  jz      short loc_14006FEA0
0x14006fe92  xor     edx, edx
0x14006fe94  mov     ecx, r13d
0x14006fe97  lea     r8d, [rdx+2]
0x14006fe9b  call    _lseeki64_nolock_internal
0x14006fea0  mov     ecx, r13d; FileHandle
0x14006fea3  mov     [rbp+var_20], rdi
0x14006fea7  call    _isatty
0x14006feac  xor     ecx, ecx
0x14006feae  lea     r8, __pioinfo
0x14006feb5  test    eax, eax
0x14006feb7  jz      loc_14006FFD8
0x14006febd  mov     rax, [r8+r12*8]
0x14006fec1  cmp     [rax+r15*8+38h], cl
0x14006fec6  jge     loc_14006FFD8
0x14006fecc  cmp     [rbx+28h], cl
0x14006fecf  jnz     short loc_14006FEE2
0x14006fed1  mov     rcx, rbx; this
0x14006fed4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x14006fed9  xor     ecx, ecx
0x14006fedb  lea     r8, __pioinfo
0x14006fee2  mov     rax, [rbx+18h]
0x14006fee6  cmp     [rax+138h], rcx
0x14006feed  jnz     short loc_14006FEFE
0x14006feef  mov     rax, [r8+r12*8]
0x14006fef3  cmp     [rax+r15*8+39h], cl
0x14006fef8  jz      loc_14006FFD8
0x14006fefe  mov     [rbp+Mode], ecx
0x14006ff01  lea     rdx, [rbp+Mode]; lpMode
0x14006ff05  mov     rcx, [r8+r12*8]
0x14006ff09  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x14006ff0e  call    cs:__imp_GetConsoleMode
0x14006ff14  test    eax, eax
0x14006ff16  jz      loc_14006FFD1
0x14006ff1c  movsx   ecx, byte ptr [rbp+var_38]
0x14006ff20  test    ecx, ecx
0x14006ff22  jz      loc_14006FFAE
0x14006ff28  sub     ecx, 1
0x14006ff2b  jz      short loc_14006FF36
0x14006ff2d  cmp     ecx, 1
0x14006ff30  jnz     loc_140070086
0x14006ff36  lea     r12, [rsi+r14]
0x14006ff3a  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x14006ff3e  mov     r15, rsi
0x14006ff41  cmp     rsi, r12
0x14006ff44  jnb     loc_14007007C
0x14006ff4a  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x14006ff4e  movzx   eax, word ptr [r15]
0x14006ff52  movzx   ecx, ax; Character
0x14006ff55  mov     [rbp+var_38], ax
0x14006ff59  call    _putwch_nolock
0x14006ff5e  movzx   ecx, [rbp+var_38]
0x14006ff62  cmp     ax, cx
0x14006ff65  jnz     short loc_14006FFA0
0x14006ff67  add     r14d, 2
0x14006ff6b  mov     [rbp+NumberOfBytesWritten+4], r14d
0x14006ff6f  cmp     cx, 0Ah
0x14006ff73  jnz     short loc_14006FF92
0x14006ff75  mov     ecx, 0Dh; Character
0x14006ff7a  call    _putwch_nolock
0x14006ff7f  mov     ecx, 0Dh
0x14006ff84  cmp     ax, cx
0x14006ff87  jnz     short loc_14006FFA0
0x14006ff89  inc     r14d
0x14006ff8c  mov     [rbp+NumberOfBytesWritten+4], r14d
0x14006ff90  inc     edi
0x14006ff92  add     r15, 2
0x14006ff96  cmp     r15, r12
0x14006ff99  jb      short loc_14006FF4E
0x14006ff9b  jmp     loc_14007007C
0x14006ffa0  call    cs:__imp_GetLastError
0x14006ffa6  mov     [rbp+NumberOfBytesWritten], eax
0x14006ffa9  jmp     loc_14007007C
0x14006ffae  mov     r9d, r14d
0x14006ffb1  mov     [rsp+68h+var_48], rbx
0x14006ffb6  mov     r8, rsi
0x14006ffb9  lea     rcx, [rbp+NumberOfBytesWritten]
0x14006ffbd  mov     edx, r13d
0x14006ffc0  call    write_double_translated_ansi_nolock
0x14006ffc5  movsd   xmm0, qword ptr [rax]
0x14006ffc9  mov     edi, [rax+8]
0x14006ffcc  jmp     loc_140070081
0x14006ffd1  lea     r8, __pioinfo
0x14006ffd8  mov     rcx, r13
0x14006ffdb  mov     rax, r13
0x14006ffde  sar     rax, 6
0x14006ffe2  and     ecx, 3Fh
0x14006ffe5  mov     rdx, [r8+rax*8]
0x14006ffe9  lea     rcx, [rcx+rcx*8]
0x14006ffed  cmp     [rdx+rcx*8+38h], dil
0x14006fff2  jge     short loc_140070049
0x14006fff4  movsx   ecx, byte ptr [rbp+var_38]
0x14006fff8  test    ecx, ecx
0x14006fffa  jz      short loc_140070032
0x14006fffc  sub     ecx, 1
0x14006ffff  jz      short loc_14007001E
0x140070001  cmp     ecx, 1
0x140070004  jnz     loc_14007008D
0x14007000a  mov     r9d, r14d
0x14007000d  lea     rcx, [rbp+NumberOfBytesWritten]
0x140070011  mov     r8, rsi
0x140070014  mov     edx, r13d
0x140070017  call    write_text_utf16le_nolock
0x14007001c  jmp     short loc_14006FFC5
0x14007001e  mov     r9d, r14d
0x140070021  lea     rcx, [rbp+NumberOfBytesWritten]
0x140070025  mov     r8, rsi
0x140070028  mov     edx, r13d
0x14007002b  call    write_text_utf8_nolock
0x140070030  jmp     short loc_14006FFC5
0x140070032  mov     r9d, r14d
0x140070035  lea     rcx, [rbp+NumberOfBytesWritten]
0x140070039  mov     r8, rsi
0x14007003c  mov     edx, r13d
0x14007003f  call    write_text_ansi_nolock
0x140070044  jmp     loc_14006FFC5
0x140070049  mov     rcx, [rdx+rcx*8+28h]; hFile
0x14007004e  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x140070052  xor     eax, eax
0x140070054  mov     rdx, rsi; lpBuffer
0x140070057  and     [rsp+68h+var_48], rax
0x14007005c  mov     r8d, r14d; nNumberOfBytesToWrite
0x14007005f  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x140070063  mov     [rbp+var_28], eax
0x140070066  call    cs:__imp_WriteFile
0x14007006c  test    eax, eax
0x14007006e  jnz     short loc_140070079
0x140070070  call    cs:__imp_GetLastError
0x140070076  mov     [rbp+NumberOfBytesWritten], eax
0x140070079  mov     edi, [rbp+var_28]
0x14007007c  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x140070081  movsd   [rbp+var_20], xmm0
0x140070086  lea     r8, __pioinfo
0x14007008d  mov     rax, [rbp+var_20]
0x140070091  shr     rax, 20h
0x140070095  test    eax, eax
0x140070097  jnz     short loc_140070105
0x140070099  mov     eax, dword ptr [rbp+var_20]
0x14007009c  test    eax, eax
0x14007009e  jz      short loc_1400700CC
0x1400700a0  cmp     eax, 5
0x1400700a3  jnz     short loc_1400700BC
0x1400700a5  mov     byte ptr [rbx+30h], 1
0x1400700a9  mov     dword ptr [rbx+2Ch], 9
0x1400700b0  mov     byte ptr [rbx+38h], 1
0x1400700b4  mov     [rbx+34h], eax
0x1400700b7  jmp     loc_14006FE4F
0x1400700bc  mov     ecx, dword ptr [rbp+var_20]
0x1400700bf  mov     rdx, rbx
0x1400700c2  call    __acrt_errno_map_os_error_ptd
0x1400700c7  jmp     loc_14006FE4F
0x1400700cc  mov     rcx, r13
0x1400700cf  mov     rax, r13
0x1400700d2  sar     rax, 6
0x1400700d6  and     ecx, 3Fh
0x1400700d9  mov     rax, [r8+rax*8]
0x1400700dd  lea     rcx, [rcx+rcx*8]
0x1400700e1  test    byte ptr [rax+rcx*8+38h], 40h
0x1400700e6  jz      short loc_1400700ED
0x1400700e8  cmp     byte ptr [rsi], 1Ah
0x1400700eb  jz      short loc_14007010C
0x1400700ed  and     dword ptr [rbx+34h], 0
0x1400700f1  mov     byte ptr [rbx+30h], 1
0x1400700f5  mov     dword ptr [rbx+2Ch], 1Ch
0x1400700fc  mov     byte ptr [rbx+38h], 1
0x140070100  jmp     loc_14006FE4F
0x140070105  mov     eax, dword ptr [rbp+var_20+4]
0x140070108  sub     eax, edi
0x14007010a  jmp     short loc_14007010E
0x14007010c  xor     eax, eax
0x14007010e  add     rsp, 68h
0x140070112  pop     r15
0x140070114  pop     r14
0x140070116  pop     r13
0x140070118  pop     r12
0x14007011a  pop     rdi
0x14007011b  pop     rsi
0x14007011c  pop     rbx
0x14007011d  pop     rbp
0x14007011e  retn
```
