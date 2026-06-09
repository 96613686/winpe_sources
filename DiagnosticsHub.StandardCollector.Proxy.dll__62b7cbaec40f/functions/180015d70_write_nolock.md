# _write_nolock

- ea: `0x180015d70`
- end: `0x18001609f`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180015c50`

## callees

- `0x180007b48`
- `0x180007ea0`
- `0x18001512c`
- `0x180015210`
- `0x1800157e4`
- `0x1800158ec`
- `0x180015a08`
- `0x180015d70`
- `0x180016224`
- `0x18001b8e4`
- `0x18001c7f8`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x180015e8e`
- `KERNEL32!GetConsoleMode` at `0x180015e8e`
- `KERNEL32!WriteFile` at `0x180015fe6`
- `KERNEL32!WriteFile` at `0x180015fe6`
- `KERNEL32!GetLastError` at `0x180015f20`
- `KERNEL32!GetLastError` at `0x180015ff0`
- `KERNEL32!GetLastError` at `0x180015f20`
- `KERNEL32!GetLastError` at `0x180015ff0`

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
0x180015d70  push    rbp
0x180015d72  push    rbx
0x180015d73  push    rsi
0x180015d74  push    rdi
0x180015d75  push    r12
0x180015d77  push    r13
0x180015d79  push    r14
0x180015d7b  push    r15
0x180015d7d  mov     rbp, rsp
0x180015d80  sub     rsp, 68h
0x180015d84  xor     edi, edi
0x180015d86  mov     r14d, r8d
0x180015d89  movsxd  r13, ecx
0x180015d8c  mov     rbx, r9
0x180015d8f  mov     rsi, rdx
0x180015d92  test    r8d, r8d
0x180015d95  jz      loc_18001608C
0x180015d9b  test    rdx, rdx
0x180015d9e  jnz     short loc_180015DD7
0x180015da0  mov     byte ptr [r9+38h], 1
0x180015da5  xor     r8d, r8d; FileName
0x180015da8  mov     [r9+34h], edi
0x180015dac  xor     edx, edx; FunctionName
0x180015dae  mov     byte ptr [r9+30h], 1
0x180015db3  xor     ecx, ecx; Expression
0x180015db5  mov     dword ptr [r9+2Ch], 16h
0x180015dbd  xor     r9d, r9d; LineNo
0x180015dc0  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x180015dc5  mov     [rsp+68h+var_48], rdi; uintptr_t
0x180015dca  call    _invalid_parameter_internal
0x180015dcf  or      eax, 0FFFFFFFFh
0x180015dd2  jmp     loc_18001608E
0x180015dd7  mov     rax, r13
0x180015dda  lea     rcx, __pioinfo
0x180015de1  and     eax, 3Fh
0x180015de4  mov     r12, r13
0x180015de7  sar     r12, 6
0x180015deb  lea     r15, [rax+rax*8]
0x180015def  mov     rcx, [rcx+r12*8]
0x180015df3  mov     al, [rcx+r15*8+39h]
0x180015df8  mov     byte ptr [rbp+var_38], al
0x180015dfb  dec     al
0x180015dfd  cmp     al, 1
0x180015dff  ja      short loc_180015E0A
0x180015e01  mov     eax, r14d
0x180015e04  not     eax
0x180015e06  test    al, 1
0x180015e08  jz      short loc_180015DA0
0x180015e0a  test    byte ptr [rcx+r15*8+38h], 20h
0x180015e10  jz      short loc_180015E20
0x180015e12  xor     edx, edx
0x180015e14  mov     ecx, r13d
0x180015e17  lea     r8d, [rdx+2]
0x180015e1b  call    _lseeki64_nolock_internal
0x180015e20  mov     ecx, r13d; FileHandle
0x180015e23  mov     [rbp+var_20], rdi
0x180015e27  call    _isatty
0x180015e2c  xor     ecx, ecx
0x180015e2e  lea     r8, __pioinfo
0x180015e35  test    eax, eax
0x180015e37  jz      loc_180015F58
0x180015e3d  mov     rax, [r8+r12*8]
0x180015e41  cmp     [rax+r15*8+38h], cl
0x180015e46  jge     loc_180015F58
0x180015e4c  cmp     [rbx+28h], cl
0x180015e4f  jnz     short loc_180015E62
0x180015e51  mov     rcx, rbx; this
0x180015e54  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180015e59  xor     ecx, ecx
0x180015e5b  lea     r8, __pioinfo
0x180015e62  mov     rax, [rbx+18h]
0x180015e66  cmp     [rax+138h], rcx
0x180015e6d  jnz     short loc_180015E7E
0x180015e6f  mov     rax, [r8+r12*8]
0x180015e73  cmp     [rax+r15*8+39h], cl
0x180015e78  jz      loc_180015F58
0x180015e7e  mov     [rbp+Mode], ecx
0x180015e81  lea     rdx, [rbp+Mode]; lpMode
0x180015e85  mov     rcx, [r8+r12*8]
0x180015e89  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x180015e8e  call    cs:__imp_GetConsoleMode
0x180015e94  test    eax, eax
0x180015e96  jz      loc_180015F51
0x180015e9c  movsx   ecx, byte ptr [rbp+var_38]
0x180015ea0  test    ecx, ecx
0x180015ea2  jz      loc_180015F2E
0x180015ea8  sub     ecx, 1
0x180015eab  jz      short loc_180015EB6
0x180015ead  cmp     ecx, 1
0x180015eb0  jnz     loc_180016006
0x180015eb6  lea     r12, [rsi+r14]
0x180015eba  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x180015ebe  mov     r15, rsi
0x180015ec1  cmp     rsi, r12
0x180015ec4  jnb     loc_180015FFC
0x180015eca  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x180015ece  movzx   eax, word ptr [r15]
0x180015ed2  movzx   ecx, ax; Character
0x180015ed5  mov     [rbp+var_38], ax
0x180015ed9  call    _putwch_nolock
0x180015ede  movzx   ecx, [rbp+var_38]
0x180015ee2  cmp     ax, cx
0x180015ee5  jnz     short loc_180015F20
0x180015ee7  add     r14d, 2
0x180015eeb  mov     [rbp+NumberOfBytesWritten+4], r14d
0x180015eef  cmp     cx, 0Ah
0x180015ef3  jnz     short loc_180015F12
0x180015ef5  mov     ecx, 0Dh; Character
0x180015efa  call    _putwch_nolock
0x180015eff  mov     ecx, 0Dh
0x180015f04  cmp     ax, cx
0x180015f07  jnz     short loc_180015F20
0x180015f09  inc     r14d
0x180015f0c  mov     [rbp+NumberOfBytesWritten+4], r14d
0x180015f10  inc     edi
0x180015f12  add     r15, 2
0x180015f16  cmp     r15, r12
0x180015f19  jb      short loc_180015ECE
0x180015f1b  jmp     loc_180015FFC
0x180015f20  call    cs:__imp_GetLastError
0x180015f26  mov     [rbp+NumberOfBytesWritten], eax
0x180015f29  jmp     loc_180015FFC
0x180015f2e  mov     r9d, r14d
0x180015f31  mov     [rsp+68h+var_48], rbx
0x180015f36  mov     r8, rsi
0x180015f39  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015f3d  mov     edx, r13d
0x180015f40  call    write_double_translated_ansi_nolock
0x180015f45  movsd   xmm0, qword ptr [rax]
0x180015f49  mov     edi, [rax+8]
0x180015f4c  jmp     loc_180016001
0x180015f51  lea     r8, __pioinfo
0x180015f58  mov     rcx, r13
0x180015f5b  mov     rax, r13
0x180015f5e  sar     rax, 6
0x180015f62  and     ecx, 3Fh
0x180015f65  mov     rdx, [r8+rax*8]
0x180015f69  lea     rcx, [rcx+rcx*8]
0x180015f6d  cmp     [rdx+rcx*8+38h], dil
0x180015f72  jge     short loc_180015FC9
0x180015f74  movsx   ecx, byte ptr [rbp+var_38]
0x180015f78  test    ecx, ecx
0x180015f7a  jz      short loc_180015FB2
0x180015f7c  sub     ecx, 1
0x180015f7f  jz      short loc_180015F9E
0x180015f81  cmp     ecx, 1
0x180015f84  jnz     loc_18001600D
0x180015f8a  mov     r9d, r14d
0x180015f8d  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015f91  mov     r8, rsi
0x180015f94  mov     edx, r13d
0x180015f97  call    write_text_utf16le_nolock
0x180015f9c  jmp     short loc_180015F45
0x180015f9e  mov     r9d, r14d
0x180015fa1  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015fa5  mov     r8, rsi
0x180015fa8  mov     edx, r13d
0x180015fab  call    write_text_utf8_nolock
0x180015fb0  jmp     short loc_180015F45
0x180015fb2  mov     r9d, r14d
0x180015fb5  lea     rcx, [rbp+NumberOfBytesWritten]
0x180015fb9  mov     r8, rsi
0x180015fbc  mov     edx, r13d
0x180015fbf  call    write_text_ansi_nolock
0x180015fc4  jmp     loc_180015F45
0x180015fc9  mov     rcx, [rdx+rcx*8+28h]; hFile
0x180015fce  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x180015fd2  xor     eax, eax
0x180015fd4  mov     rdx, rsi; lpBuffer
0x180015fd7  and     [rsp+68h+var_48], rax
0x180015fdc  mov     r8d, r14d; nNumberOfBytesToWrite
0x180015fdf  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x180015fe3  mov     [rbp+var_28], eax
0x180015fe6  call    cs:__imp_WriteFile
0x180015fec  test    eax, eax
0x180015fee  jnz     short loc_180015FF9
0x180015ff0  call    cs:__imp_GetLastError
0x180015ff6  mov     [rbp+NumberOfBytesWritten], eax
0x180015ff9  mov     edi, [rbp+var_28]
0x180015ffc  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x180016001  movsd   [rbp+var_20], xmm0
0x180016006  lea     r8, __pioinfo
0x18001600d  mov     rax, [rbp+var_20]
0x180016011  shr     rax, 20h
0x180016015  test    eax, eax
0x180016017  jnz     short loc_180016085
0x180016019  mov     eax, dword ptr [rbp+var_20]
0x18001601c  test    eax, eax
0x18001601e  jz      short loc_18001604C
0x180016020  cmp     eax, 5
0x180016023  jnz     short loc_18001603C
0x180016025  mov     byte ptr [rbx+30h], 1
0x180016029  mov     dword ptr [rbx+2Ch], 9
0x180016030  mov     byte ptr [rbx+38h], 1
0x180016034  mov     [rbx+34h], eax
0x180016037  jmp     loc_180015DCF
0x18001603c  mov     ecx, dword ptr [rbp+var_20]
0x18001603f  mov     rdx, rbx
0x180016042  call    __acrt_errno_map_os_error_ptd
0x180016047  jmp     loc_180015DCF
0x18001604c  mov     rcx, r13
0x18001604f  mov     rax, r13
0x180016052  sar     rax, 6
0x180016056  and     ecx, 3Fh
0x180016059  mov     rax, [r8+rax*8]
0x18001605d  lea     rcx, [rcx+rcx*8]
0x180016061  test    byte ptr [rax+rcx*8+38h], 40h
0x180016066  jz      short loc_18001606D
0x180016068  cmp     byte ptr [rsi], 1Ah
0x18001606b  jz      short loc_18001608C
0x18001606d  and     dword ptr [rbx+34h], 0
0x180016071  mov     byte ptr [rbx+30h], 1
0x180016075  mov     dword ptr [rbx+2Ch], 1Ch
0x18001607c  mov     byte ptr [rbx+38h], 1
0x180016080  jmp     loc_180015DCF
0x180016085  mov     eax, dword ptr [rbp+var_20+4]
0x180016088  sub     eax, edi
0x18001608a  jmp     short loc_18001608E
0x18001608c  xor     eax, eax
0x18001608e  add     rsp, 68h
0x180016092  pop     r15
0x180016094  pop     r14
0x180016096  pop     r13
0x180016098  pop     r12
0x18001609a  pop     rdi
0x18001609b  pop     rsi
0x18001609c  pop     rbx
0x18001609d  pop     rbp
0x18001609e  retn
```
