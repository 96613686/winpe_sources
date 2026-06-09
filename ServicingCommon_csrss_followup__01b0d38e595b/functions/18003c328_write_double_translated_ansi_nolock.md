# write_double_translated_ansi_nolock

- ea: `0x18003c328`
- end: `0x18003c817`
- name: `write_double_translated_ansi_nolock`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18003cd08`

## callees

- `0x180027840`
- `0x18002cc10`
- `0x18002d2b0`
- `0x18003b0d4`
- `0x18003b510`
- `0x18003c328`
- `0x1800981e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003c7e5`
- `KERNEL32!GetLastError` at `0x18003c7e5`
- `KERNEL32!WriteFile` at `0x18003c6a8`
- `KERNEL32!WriteFile` at `0x18003c6f6`
- `KERNEL32!WriteFile` at `0x18003c6a8`
- `KERNEL32!WriteFile` at `0x18003c6f6`
- `KERNEL32!GetConsoleOutputCP` at `0x18003c3ae`
- `KERNEL32!GetConsoleOutputCP` at `0x18003c3ae`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // rbx
  char v8; // r13
  __int64 v9; // r12
  __int64 v10; // rsi
  unsigned __int64 v11; // r15
  struct _Mbstatet *v12; // r11
  int v13; // ecx
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // esi
  __int64 v17; // r14
  int v18; // r15d
  __int64 v19; // r10
  signed __int64 v20; // r8
  unsigned int v21; // r9d
  __int64 v22; // r10
  int v23; // edx
  unsigned int v24; // r14d
  __int64 v25; // r15
  __int64 v26; // r9
  unsigned int v27; // esi
  __int64 v28; // rdx
  __int64 v29; // r8
  wchar_t *v30; // rdx
  __int64 v31; // r9
  DWORD v32; // esi
  HANDLE v33; // r14
  int v34; // r8d
  struct __crt_cached_ptd_host *v36; // [rsp+30h] [rbp-99h]
  __int16 v37[2]; // [rsp+48h] [rbp-81h] BYREF
  int v38; // [rsp+4Ch] [rbp-7Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-71h]
  struct _Mbstatet *v41; // [rsp+60h] [rbp-69h]
  unsigned __int64 v42; // [rsp+68h] [rbp-61h] BYREF
  UINT ConsoleOutputCP; // [rsp+74h] [rbp-55h]
  int v44; // [rsp+78h] [rbp-51h]
  __int64 v45; // [rsp+80h] [rbp-49h]
  __int64 v46; // [rsp+88h] [rbp-41h]
  __int64 v47; // [rsp+90h] [rbp-39h]
  unsigned __int64 v48; // [rsp+98h] [rbp-31h] BYREF
  wchar_t v49[4]; // [rsp+A0h] [rbp-29h] BYREF
  wchar_t v50[4]; // [rsp+A8h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp-19h]
  _BYTE *v52; // [rsp+B8h] [rbp-11h]
  __int64 v53; // [rsp+C0h] [rbp-9h]
  _BYTE v54[8]; // [rsp+C8h] [rbp-1h] BYREF
  _BYTE v55[8]; // [rsp+D0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+D8h] [rbp+Fh] BYREF

  v53 = -2;
  v5 = a3;
  v52 = a3;
  v6 = a2;
  v7 = a1;
  v45 = a1;
  v41 = (struct _Mbstatet *)a5;
  v8 = a2;
  v9 = (__int64)a2 >> 6;
  v10 = 9LL * (a2 & 0x3F);
  v46 = v10;
  hFile = *(HANDLE *)(_pioinfo[v9] + 72LL * (a2 & 0x3F) + 40);
  v11 = (unsigned __int64)&a3[a4];
  v40 = v11;
  ConsoleOutputCP = GetConsoleOutputCP();
  v12 = (struct _Mbstatet *)a5;
  if ( !*(_BYTE *)(a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v41);
    v12 = v41;
  }
  *(_QWORD *)v7 = 0;
  *(_DWORD *)(v7 + 8) = 0;
  v47 = (__int64)v5;
  if ( (unsigned __int64)v5 < v11 )
  {
    v13 = *(_DWORD *)(*(_QWORD *)&v12[3] + 12LL);
    v44 = v13;
    v14 = v6 >> 6;
    v47 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v37[0]) = *v5;
      v38 = 0;
      if ( v13 == 65001 )
      {
        v16 = 0;
        v17 = 72LL * (v8 & 0x3F);
        do
        {
          if ( !*(_BYTE *)(_pioinfo[v14] + (unsigned int)v16 + v17 + 62) )
            break;
          ++v16;
        }
        while ( v16 < 5 );
        if ( v16 )
        {
          LODWORD(v42) = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v9] + v17 + 62)) + 1;
          v18 = v42 - v16;
          v19 = v40 - (_QWORD)v5;
          v20 = (int)v42 - v16;
          v21 = 0;
          if ( v20 > (__int64)(v40 - (_QWORD)v5) )
          {
            if ( v19 > 0 )
            {
              do
              {
                *(_BYTE *)(v17 + (int)(v21 + v16) + _pioinfo[v9] + 62) = v5[v21];
                ++v21;
              }
              while ( (int)v21 < v19 );
              v7 = v45;
            }
            *(_DWORD *)(v7 + 4) += v19;
            return v7;
          }
          v22 = _pioinfo[v14];
          do
          {
            v54[v21] = *(_BYTE *)(v22 + v17 + v21 + 62);
            ++v21;
          }
          while ( (int)v21 < v16 );
          if ( v18 > 0 )
          {
            memmove(&v54[v16], v5, v20);
            v12 = v41;
          }
          v23 = 0;
          do
            *(_BYTE *)(v17 + v23++ + _pioinfo[v9] + 62) = 0;
          while ( v23 < v16 );
          v7 = v45;
          v48 = 0;
          *(_QWORD *)v49 = v54;
          v24 = ((_DWORD)v42 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v38,
                 v49,
                 (const char **)v24,
                 (unsigned __int64)&v48,
                 v12,
                 v36) == -1 )
            return v7;
          v5 += v18 - 1;
        }
        else
        {
          v25 = *((char *)lookuptrailbytes + (unsigned __int8)*v5);
          v26 = v40 - (_QWORD)v5;
          if ( (int)v25 + 1 > (__int64)(v40 - (_QWORD)v5) )
          {
            v34 = 0;
            if ( v26 > 0 )
            {
              do
              {
                *(_BYTE *)(v34 + _pioinfo[v9] + v17 + 62) = v5[v34];
                ++v34;
              }
              while ( v34 < v26 );
              v7 = v45;
            }
            *(_DWORD *)(v7 + 4) += v26;
            return v7;
          }
          v42 = 0;
          *(_QWORD *)v50 = v5;
          v27 = ((_DWORD)v25 == 3) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v38,
                 v50,
                 (const char **)v27,
                 (unsigned __int64)&v42,
                 v12,
                 v36) == -1 )
            return v7;
          v5 += v25;
          v24 = v27;
        }
        v11 = v40;
      }
      else
      {
        v24 = 1;
        v28 = _pioinfo[v9];
        if ( (*(_BYTE *)(v28 + 8 * v10 + 61) & 4) != 0 )
        {
          v55[0] = *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 62);
          v55[1] = *v5;
          *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 61) &= ~4u;
          v29 = 2;
          v30 = (wchar_t *)v55;
          goto LABEL_30;
        }
        v31 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**(_QWORD **)&v12[3] + 2 * v31) >= 0 )
        {
          v29 = 1;
          v30 = (wchar_t *)v5;
LABEL_30:
          if ( (unsigned int)mbtowc_internal((__crt_mbstring *)&v38, v30, (char *)v29, (__crt_cached_ptd_host *)v12) == -1 )
            return v7;
          goto LABEL_31;
        }
        if ( (unsigned __int64)(v5 + 1) >= v11 )
        {
          *(_BYTE *)(v28 + 72LL * (v8 & 0x3F) + 62) = v31;
          *(_BYTE *)(_pioinfo[v9] + 8 * v46 + 61) |= 4u;
          *(_DWORD *)(v7 + 4) = v15 + 1;
          return v7;
        }
        if ( (unsigned int)mbtowc_internal(
                             (__crt_mbstring *)&v38,
                             (wchar_t *)v5,
                             (char *)2,
                             (__crt_cached_ptd_host *)v12) == -1 )
          return v7;
        ++v5;
      }
LABEL_31:
      ++v5;
      v32 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v38, v24, (unsigned int)Buffer, 5, 0, 0);
      if ( !v32 )
        return v7;
      NumberOfBytesWritten = 0;
      v33 = hFile;
      if ( !WriteFile(hFile, Buffer, v32, &NumberOfBytesWritten, 0) )
      {
LABEL_49:
        *(_DWORD *)v7 = GetLastError();
        return v7;
      }
      v15 = (_DWORD)v5 + *(_DWORD *)(v7 + 8) - (_DWORD)v52;
      *(_DWORD *)(v7 + 4) = v15;
      if ( NumberOfBytesWritten < v32 )
        return v7;
      if ( LOBYTE(v37[0]) == 10 )
      {
        v37[0] = 13;
        if ( !WriteFile(v33, v37, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_49;
        if ( !NumberOfBytesWritten )
          return v7;
        ++*(_DWORD *)(v7 + 8);
        v15 = ++*(_DWORD *)(v7 + 4);
      }
      if ( (unsigned __int64)v5 >= v11 )
        return v7;
      v12 = v41;
      v10 = v46;
      v14 = v47;
      v13 = v44;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003c328  mov     rax, rsp
0x18003c32b  push    rbp
0x18003c32c  push    rsi
0x18003c32d  push    rdi
0x18003c32e  push    r12
0x18003c330  push    r13
0x18003c332  push    r14
0x18003c334  push    r15
0x18003c336  lea     rbp, [rax-57h]
0x18003c33a  sub     rsp, 0E0h
0x18003c341  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18003c349  mov     [rax+8], rbx
0x18003c34d  mov     rax, cs:__security_cookie
0x18003c354  xor     rax, rsp
0x18003c357  mov     [rbp+4Fh+var_38], rax
0x18003c35b  mov     rdi, r8
0x18003c35e  mov     [rbp+4Fh+var_60], r8
0x18003c362  movsxd  r14, edx
0x18003c365  mov     rbx, rcx
0x18003c368  mov     [rbp+4Fh+var_98], rcx
0x18003c36c  mov     rax, [rbp+4Fh+arg_20]
0x18003c370  mov     [rbp+4Fh+var_B8], rax
0x18003c374  mov     r13, r14
0x18003c377  mov     r12, r14
0x18003c37a  sar     r12, 6
0x18003c37e  lea     rcx, __ImageBase
0x18003c385  mov     eax, r14d
0x18003c388  and     eax, 3Fh
0x18003c38b  lea     rsi, [rax+rax*8]
0x18003c38f  mov     [rbp+4Fh+var_90], rsi
0x18003c393  mov     rax, rva __pioinfo[rcx+r12*8]
0x18003c39b  mov     rax, [rax+rsi*8+28h]
0x18003c3a0  mov     [rbp+4Fh+hFile], rax
0x18003c3a4  mov     r15d, r9d
0x18003c3a7  add     r15, r8
0x18003c3aa  mov     [rbp+4Fh+var_C0], r15
0x18003c3ae  call    cs:__imp_GetConsoleOutputCP
0x18003c3b4  mov     [rbp+4Fh+var_A4], eax
0x18003c3b7  xor     r10d, r10d
0x18003c3ba  mov     r11, [rbp+4Fh+var_B8]
0x18003c3be  cmp     [r11+28h], r10b
0x18003c3c2  jnz     short loc_18003C3D3
0x18003c3c4  mov     rcx, r11; this
0x18003c3c7  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18003c3cc  mov     r11, [rbp+4Fh+var_B8]
0x18003c3d0  xor     r10d, r10d
0x18003c3d3  xor     eax, eax
0x18003c3d5  mov     [rbx], rax
0x18003c3d8  mov     [rbx+8], eax
0x18003c3db  mov     [rbp+4Fh+var_88], rdi
0x18003c3df  cmp     rdi, r15
0x18003c3e2  jnb     loc_18003C7ED
0x18003c3e8  mov     rax, [r11+18h]
0x18003c3ec  mov     ecx, [rax+0Ch]
0x18003c3ef  mov     [rbp+4Fh+var_A0], ecx
0x18003c3f2  mov     rdx, r14
0x18003c3f5  sar     rdx, 6
0x18003c3f9  mov     [rbp+4Fh+var_88], rdx
0x18003c3fd  mov     r8d, r10d
0x18003c400  mov     al, [rdi]
0x18003c402  mov     byte ptr [rsp+110h+var_D0], al
0x18003c406  mov     [rbp+4Fh+var_CC], r10d
0x18003c40a  cmp     ecx, 0FDE9h
0x18003c410  jnz     loc_18003C5A9
0x18003c416  mov     esi, r10d
0x18003c419  mov     rax, r13
0x18003c41c  and     eax, 3Fh
0x18003c41f  lea     r14, [rax+rax*8]
0x18003c423  shl     r14, 3
0x18003c427  lea     r8, __ImageBase
0x18003c42e  mov     eax, esi
0x18003c430  add     rax, rva __pioinfo[r8+rdx*8]
0x18003c438  cmp     [rax+r14+3Eh], r10b
0x18003c43d  jz      short loc_18003C446
0x18003c43f  inc     esi
0x18003c441  cmp     esi, 5
0x18003c444  jl      short loc_18003C42E
0x18003c446  test    esi, esi
0x18003c448  jz      loc_18003C53F
0x18003c44e  mov     rax, rva __pioinfo[r8+r12*8]
0x18003c456  movzx   ecx, byte ptr [rax+r14+3Eh]
0x18003c45c  movsx   eax, byte ptr [rcx+r8+0D1B10h]
0x18003c465  inc     eax
0x18003c467  mov     dword ptr [rbp+4Fh+var_B0], eax
0x18003c46a  mov     r15d, eax
0x18003c46d  sub     r15d, esi
0x18003c470  mov     r10, [rbp+4Fh+var_C0]
0x18003c474  sub     r10, rdi
0x18003c477  movsxd  r8, r15d; Size
0x18003c47a  xor     eax, eax
0x18003c47c  mov     r9d, eax
0x18003c47f  cmp     r8, r10
0x18003c482  jg      loc_18003C738
0x18003c488  lea     r10, __ImageBase
0x18003c48f  mov     r10, rva __pioinfo[r10+rdx*8]
0x18003c497  mov     edx, r9d
0x18003c49a  lea     rax, [r10+r14]
0x18003c49e  mov     cl, [rax+rdx+3Eh]
0x18003c4a2  mov     [rbp+rdx+4Fh+var_50], cl
0x18003c4a6  inc     r9d
0x18003c4a9  cmp     r9d, esi
0x18003c4ac  jl      short loc_18003C497
0x18003c4ae  xor     r9d, r9d
0x18003c4b1  test    r15d, r15d
0x18003c4b4  jle     short loc_18003C4CE
0x18003c4b6  mov     eax, esi
0x18003c4b8  lea     rcx, [rbp+4Fh+var_50]
0x18003c4bc  add     rcx, rax; void *
0x18003c4bf  mov     rdx, rdi; Src
0x18003c4c2  call    memmove
0x18003c4c7  xor     r9d, r9d
0x18003c4ca  mov     r11, [rbp+4Fh+var_B8]
0x18003c4ce  mov     edx, r9d
0x18003c4d1  lea     rbx, __ImageBase
0x18003c4d8  movsxd  rcx, edx
0x18003c4db  add     rcx, r14
0x18003c4de  mov     rax, rva __pioinfo[rbx+r12*8]
0x18003c4e6  mov     [rcx+rax+3Eh], r9b
0x18003c4eb  inc     edx
0x18003c4ed  cmp     edx, esi
0x18003c4ef  jl      short loc_18003C4D8
0x18003c4f1  mov     rbx, [rbp+4Fh+var_98]
0x18003c4f5  mov     [rbp+4Fh+var_80], r9
0x18003c4f9  lea     rax, [rbp+4Fh+var_50]
0x18003c4fd  mov     qword ptr [rbp+4Fh+var_78], rax
0x18003c501  mov     eax, r9d
0x18003c504  cmp     dword ptr [rbp+4Fh+var_B0], 4
0x18003c508  setz    al
0x18003c50b  inc     eax
0x18003c50d  mov     r14d, eax
0x18003c510  mov     r8d, eax; char **
0x18003c513  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18003c518  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x18003c51c  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18003c520  lea     rcx, [rbp+4Fh+var_CC]; this
0x18003c524  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18003c529  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c52d  jz      loc_18003C7ED
0x18003c533  lea     eax, [r15-1]
0x18003c537  movsxd  rcx, eax
0x18003c53a  add     rdi, rcx
0x18003c53d  jmp     short loc_18003C5A0
0x18003c53f  movzx   eax, byte ptr [rdi]
0x18003c542  movsx   r15, byte ptr [rax+r8+0D1B10h]
0x18003c54b  lea     ecx, [r15+1]
0x18003c54f  mov     r9, [rbp+4Fh+var_C0]
0x18003c553  sub     r9, rdi
0x18003c556  movsxd  rax, ecx
0x18003c559  cmp     rax, r9
0x18003c55c  jg      loc_18003C776
0x18003c562  mov     [rbp+4Fh+var_B0], r10
0x18003c566  mov     qword ptr [rbp+4Fh+var_70], rdi
0x18003c56a  mov     eax, r10d
0x18003c56d  cmp     ecx, 4
0x18003c570  setz    al
0x18003c573  inc     eax
0x18003c575  mov     esi, eax
0x18003c577  mov     r8d, eax; char **
0x18003c57a  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18003c57f  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64
0x18003c583  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18003c587  lea     rcx, [rbp+4Fh+var_CC]; this
0x18003c58b  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18003c590  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c594  jz      loc_18003C7ED
0x18003c59a  add     rdi, r15
0x18003c59d  mov     r14d, esi
0x18003c5a0  mov     r15, [rbp+4Fh+var_C0]
0x18003c5a4  jmp     loc_18003C651
0x18003c5a9  mov     r14d, 1
0x18003c5af  lea     rax, __ImageBase
0x18003c5b6  mov     rdx, rva __pioinfo[rax+r12*8]
0x18003c5be  test    byte ptr [rdx+rsi*8+3Dh], 4
0x18003c5c3  jz      short loc_18003C5F4
0x18003c5c5  mov     rax, r13
0x18003c5c8  and     eax, 3Fh
0x18003c5cb  lea     rax, [rax+rax*8]
0x18003c5cf  mov     cl, [rdx+rax*8+3Eh]
0x18003c5d3  mov     [rbp+4Fh+var_48], cl
0x18003c5d6  mov     al, [rdi]
0x18003c5d8  mov     [rbp+4Fh+var_47], al
0x18003c5db  mov     eax, r13d
0x18003c5de  and     eax, 3Fh
0x18003c5e1  lea     rcx, [rax+rax*8]
0x18003c5e5  and     byte ptr [rdx+rcx*8+3Dh], 0FBh
0x18003c5ea  lea     r8d, [r14+1]
0x18003c5ee  lea     rdx, [rbp+4Fh+var_48]
0x18003c5f2  jmp     short loc_18003C63C
0x18003c5f4  movzx   r9d, byte ptr [rdi]
0x18003c5f8  mov     rax, [r11+18h]
0x18003c5fc  mov     rcx, [rax]
0x18003c5ff  cmp     [rcx+r9*2], r10w
0x18003c604  jge     short loc_18003C636
0x18003c606  lea     rsi, [rdi+1]
0x18003c60a  cmp     rsi, r15
0x18003c60d  jnb     loc_18003C7B0
0x18003c613  mov     r9, r11; __crt_cached_ptd_host *
0x18003c616  mov     r8d, 2; char *
0x18003c61c  mov     rdx, rdi; wchar_t *
0x18003c61f  lea     rcx, [rbp+4Fh+var_CC]; this
0x18003c623  call    _mbtowc_internal
0x18003c628  cmp     eax, 0FFFFFFFFh
0x18003c62b  jz      loc_18003C7ED
0x18003c631  mov     rdi, rsi
0x18003c634  jmp     short loc_18003C651
0x18003c636  mov     r8, r14; char *
0x18003c639  mov     rdx, rdi; wchar_t *
0x18003c63c  mov     r9, r11; __crt_cached_ptd_host *
0x18003c63f  lea     rcx, [rbp+4Fh+var_CC]; this
0x18003c643  call    _mbtowc_internal
0x18003c648  cmp     eax, 0FFFFFFFFh
0x18003c64b  jz      loc_18003C7ED
0x18003c651  inc     rdi
0x18003c654  xor     eax, eax
0x18003c656  mov     qword ptr [rsp+110h+var_D8], rax
0x18003c65b  mov     [rsp+110h+var_E0], rax
0x18003c660  mov     dword ptr [rsp+110h+var_E8], 5
0x18003c668  lea     rax, [rbp+4Fh+Buffer]
0x18003c66c  mov     [rsp+110h+lpOverlapped], rax
0x18003c671  mov     r9d, r14d
0x18003c674  lea     r8, [rbp+4Fh+var_CC]
0x18003c678  xor     edx, edx
0x18003c67a  mov     ecx, [rbp+4Fh+var_A4]
0x18003c67d  call    __acrt_WideCharToMultiByte
0x18003c682  mov     esi, eax
0x18003c684  xor     eax, eax
0x18003c686  test    esi, esi
0x18003c688  jz      loc_18003C7ED
0x18003c68e  mov     [rbp+4Fh+NumberOfBytesWritten], eax
0x18003c691  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x18003c696  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c69a  mov     r8d, esi; nNumberOfBytesToWrite
0x18003c69d  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x18003c6a1  mov     r14, [rbp+4Fh+hFile]
0x18003c6a5  mov     rcx, r14; hFile
0x18003c6a8  call    cs:__imp_WriteFile
0x18003c6ae  xor     r10d, r10d
0x18003c6b1  test    eax, eax
0x18003c6b3  jz      loc_18003C7E5
0x18003c6b9  mov     r8d, [rbx+8]
0x18003c6bd  sub     r8d, dword ptr [rbp+4Fh+var_60]
0x18003c6c1  add     r8d, edi
0x18003c6c4  mov     [rbx+4], r8d
0x18003c6c8  cmp     [rbp+4Fh+NumberOfBytesWritten], esi
0x18003c6cb  jb      loc_18003C7ED
0x18003c6d1  cmp     byte ptr [rsp+110h+var_D0], 0Ah
0x18003c6d6  jnz     short loc_18003C71B
0x18003c6d8  lea     eax, [r10+0Dh]
0x18003c6dc  mov     [rsp+110h+var_D0], ax
0x18003c6e1  mov     [rsp+110h+lpOverlapped], r10; lpOverlapped
0x18003c6e6  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c6ea  lea     r8d, [r10+1]; nNumberOfBytesToWrite
0x18003c6ee  lea     rdx, [rsp+110h+var_D0]; lpBuffer
0x18003c6f3  mov     rcx, r14; hFile
0x18003c6f6  call    cs:__imp_WriteFile
0x18003c6fc  xor     r10d, r10d
0x18003c6ff  test    eax, eax
0x18003c701  jz      loc_18003C7E5
0x18003c707  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x18003c70b  jb      loc_18003C7ED
0x18003c711  inc     dword ptr [rbx+8]
0x18003c714  inc     dword ptr [rbx+4]
0x18003c717  mov     r8d, [rbx+4]
0x18003c71b  cmp     rdi, r15
0x18003c71e  jnb     loc_18003C7ED
0x18003c724  mov     r11, [rbp+4Fh+var_B8]
0x18003c728  mov     rsi, [rbp+4Fh+var_90]
0x18003c72c  mov     rdx, [rbp+4Fh+var_88]
0x18003c730  mov     ecx, [rbp+4Fh+var_A0]
0x18003c733  jmp     loc_18003C400
0x18003c738  test    r10, r10
0x18003c73b  jle     short loc_18003C770
0x18003c73d  lea     rbx, __ImageBase
0x18003c744  movsxd  r8, r9d
0x18003c747  lea     eax, [r9+rsi]
0x18003c74b  movsxd  rdx, eax
0x18003c74e  add     rdx, r14
0x18003c751  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18003c759  mov     al, [r8+rdi]
0x18003c75d  mov     [rdx+rcx+3Eh], al
0x18003c761  inc     r9d
0x18003c764  movsxd  rax, r9d
0x18003c767  cmp     rax, r10
0x18003c76a  jl      short loc_18003C744
0x18003c76c  mov     rbx, [rbp+4Fh+var_98]
0x18003c770  add     [rbx+4], r10d
0x18003c774  jmp     short loc_18003C7ED
0x18003c776  mov     r8d, r10d
0x18003c779  test    r9, r9
0x18003c77c  jle     short loc_18003C7AA
0x18003c77e  lea     rbx, __ImageBase
0x18003c785  movsxd  rdx, r8d
0x18003c788  mov     rcx, rva __pioinfo[rbx+r12*8]
0x18003c790  add     rcx, rdx
0x18003c793  mov     al, [rdx+rdi]
0x18003c796  mov     [rcx+r14+3Eh], al
0x18003c79b  inc     r8d
0x18003c79e  movsxd  rax, r8d
0x18003c7a1  cmp     rax, r9
0x18003c7a4  jl      short loc_18003C785
  ... truncated ...
```
