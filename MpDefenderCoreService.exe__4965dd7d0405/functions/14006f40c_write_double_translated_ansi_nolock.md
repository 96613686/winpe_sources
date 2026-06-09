# write_double_translated_ansi_nolock

- ea: `0x14006f40c`
- end: `0x14006f89f`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14006fdf0`

## callees

- `0x14003a5c0`
- `0x14004dd00`
- `0x140068628`
- `0x140068bc0`
- `0x14006f40c`
- `0x140072e98`
- `0x1401662d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14006f768`
- `KERNEL32!WriteFile` at `0x14006f7ae`
- `KERNEL32!WriteFile` at `0x14006f768`
- `KERNEL32!WriteFile` at `0x14006f7ae`
- `KERNEL32!GetLastError` at `0x14006f86d`
- `KERNEL32!GetLastError` at `0x14006f86d`
- `KERNEL32!GetConsoleOutputCP` at `0x14006f48b`
- `KERNEL32!GetConsoleOutputCP` at `0x14006f48b`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  struct _Mbstatet *v12; // r10
  int v13; // ecx
  __int64 v14; // r11
  int v15; // edx
  unsigned int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // r8
  signed __int64 v22; // r9
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r9
  unsigned int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  wchar_t *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r10
  struct __crt_cached_ptd_host *v41; // [rsp+30h] [rbp-89h]
  __int16 v42[2]; // [rsp+48h] [rbp-71h] BYREF
  int v43; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-61h]
  struct _Mbstatet *v46; // [rsp+60h] [rbp-59h]
  unsigned __int64 v47; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v49; // [rsp+74h] [rbp-45h]
  _BYTE *v50; // [rsp+78h] [rbp-41h]
  __int64 v51; // [rsp+80h] [rbp-39h]
  unsigned __int64 v52; // [rsp+88h] [rbp-31h] BYREF
  wchar_t v53[4]; // [rsp+90h] [rbp-29h] BYREF
  wchar_t v54[4]; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h]
  __int64 v57; // [rsp+B0h] [rbp-9h]
  _BYTE v58[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v59[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v57 = -2;
  v5 = a3;
  v50 = a3;
  v6 = a2;
  v46 = (struct _Mbstatet *)a5;
  v8 = (__int64)a2 >> 6;
  v51 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(_pioinfo[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v45 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = (struct _Mbstatet *)a5;
  if ( !*(_BYTE *)(a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v46);
    v12 = v46;
  }
  v13 = *(_DWORD *)(*(_QWORD *)&v12[3] + 12LL);
  v49 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v50 < v10 )
  {
    v14 = v6 >> 6;
    v56 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v42[0]) = *v5;
      v43 = 0;
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
        do
        {
          if ( !*v19 )
            break;
          ++v17;
          ++v18;
          ++v19;
        }
        while ( v18 < 5 );
        if ( v18 <= 0 )
        {
          v26 = *((char *)lookuptrailbytes + (unsigned __int8)*v5);
          v27 = v45 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v51;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + _pioinfo[v39] + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v47 = 0;
          *(_QWORD *)v54 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v54,
                 (const char **)v28,
                 (unsigned __int64)&v47,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v51;
        }
        else
        {
          v20 = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v47) = v20 - v17;
          v21 = v45 - (_QWORD)v5;
          v22 = v20 - v17;
          if ( v22 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + 8 * v9 + _pioinfo[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
          do
            v58[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memmove(&v58[v18], v5, v22);
            v12 = v46;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + _pioinfo[v8] + 62) = 0;
          v52 = 0;
          *(_QWORD *)v53 = v58;
          v16 = (v20 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v53,
                 (const char **)v16,
                 (unsigned __int64)&v52,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += (int)v47 - 1;
        }
      }
      else
      {
        v29 = _pioinfo[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v59[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v59[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = (wchar_t *)v59;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**(_QWORD **)&v12[3] + 2 * v33) >= 0 )
        {
          v31 = 1;
          v32 = (wchar_t *)v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal((__crt_mbstring *)&v43, v32, (char *)v31, (__crt_cached_ptd_host *)v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v45 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(_pioinfo[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(
                             (__crt_mbstring *)&v43,
                             (wchar_t *)v5,
                             (char *)2,
                             (__crt_cached_ptd_host *)v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v43, v16, (unsigned int)Buffer, 5, 0, 0);
      v35 = v34;
      if ( !v34 )
        return a1;
      NumberOfBytesWritten = 0;
      v36 = hFile;
      if ( !WriteFile(hFile, Buffer, v34, &NumberOfBytesWritten, 0) )
      {
LABEL_48:
        *(_DWORD *)a1 = GetLastError();
        return a1;
      }
      v15 = (_DWORD)v5 + *(_DWORD *)(a1 + 8) - (_DWORD)v50;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v42[0]) == 10 )
      {
        v42[0] = 13;
        if ( !WriteFile(v36, v42, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v45 )
        return a1;
      v12 = v46;
      v14 = v56;
      v13 = v49;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14006f40c  mov     rax, rsp
0x14006f40f  push    rbp
0x14006f410  push    rsi
0x14006f411  push    rdi
0x14006f412  push    r12
0x14006f414  push    r13
0x14006f416  push    r14
0x14006f418  push    r15
0x14006f41a  lea     rbp, [rax-57h]
0x14006f41e  sub     rsp, 0D0h
0x14006f425  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x14006f42d  mov     [rax+8], rbx
0x14006f431  mov     rax, cs:__security_cookie
0x14006f438  xor     rax, rsp
0x14006f43b  mov     [rbp+4Fh+var_38], rax
0x14006f43f  mov     rsi, r8
0x14006f442  mov     [rbp+4Fh+var_90], r8
0x14006f446  movsxd  r14, edx
0x14006f449  mov     rbx, rcx
0x14006f44c  mov     rax, [rbp+4Fh+arg_20]
0x14006f450  mov     [rbp+4Fh+var_A8], rax
0x14006f454  mov     rax, r14
0x14006f457  mov     r13, r14
0x14006f45a  sar     r13, 6
0x14006f45e  mov     [rbp+4Fh+var_88], r13
0x14006f462  lea     rcx, cs:140000000h
0x14006f469  and     eax, 3Fh
0x14006f46c  lea     r15, [rax+rax*8]
0x14006f470  mov     rax, rva __pioinfo[rcx+r13*8]
0x14006f478  mov     rax, [rax+r15*8+28h]
0x14006f47d  mov     [rbp+4Fh+hFile], rax
0x14006f481  mov     r12d, r9d
0x14006f484  add     r12, r8
0x14006f487  mov     [rbp+4Fh+var_B0], r12
0x14006f48b  call    cs:__imp_GetConsoleOutputCP
0x14006f491  mov     [rbp+4Fh+var_98], eax
0x14006f494  xor     edi, edi
0x14006f496  mov     r10, [rbp+4Fh+var_A8]
0x14006f49a  cmp     [r10+28h], dil
0x14006f49e  jnz     short loc_14006F4AC
0x14006f4a0  mov     rcx, r10; this
0x14006f4a3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14006f4a8  mov     r10, [rbp+4Fh+var_A8]
0x14006f4ac  mov     rcx, [r10+18h]
0x14006f4b0  mov     ecx, [rcx+0Ch]
0x14006f4b3  mov     [rbp+4Fh+var_94], ecx
0x14006f4b6  xor     eax, eax
0x14006f4b8  mov     [rbx], rax
0x14006f4bb  mov     [rbx+8], eax
0x14006f4be  cmp     [rbp+4Fh+var_90], r12
0x14006f4c2  jnb     loc_14006F875
0x14006f4c8  mov     r11, r14
0x14006f4cb  sar     r11, 6
0x14006f4cf  mov     [rbp+4Fh+var_60], r11
0x14006f4d3  mov     edx, edi
0x14006f4d5  mov     al, [rsi]
0x14006f4d7  mov     byte ptr [rbp+4Fh+var_C0], al
0x14006f4da  mov     [rbp+4Fh+var_BC], edi
0x14006f4dd  mov     r12d, 1
0x14006f4e3  cmp     ecx, 0FDE9h
0x14006f4e9  jnz     loc_14006F67C
0x14006f4ef  mov     edx, edi
0x14006f4f1  mov     r14, rdi
0x14006f4f4  lea     r12, cs:140000000h
0x14006f4fb  lea     rcx, ds:3Eh[r15*8]
0x14006f503  add     rcx, rva __pioinfo[r12+r11*8]
0x14006f50b  cmp     [rcx], dil
0x14006f50e  jz      short loc_14006F51E
0x14006f510  inc     edx
0x14006f512  inc     r14
0x14006f515  inc     rcx
0x14006f518  cmp     r14, 5
0x14006f51c  jl      short loc_14006F50B
0x14006f51e  test    r14, r14
0x14006f521  jle     loc_14006F612
0x14006f527  mov     rax, rva __pioinfo[r12+r13*8]
0x14006f52f  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x14006f535  movsx   r12d, byte ptr [rcx+r12+1D8FB0h]
0x14006f53e  inc     r12d
0x14006f541  mov     eax, r12d
0x14006f544  sub     eax, edx
0x14006f546  mov     dword ptr [rbp+4Fh+var_A0], eax
0x14006f549  mov     r8, [rbp+4Fh+var_B0]
0x14006f54d  sub     r8, rsi
0x14006f550  movsxd  r9, eax
0x14006f553  cmp     r9, r8
0x14006f556  jg      loc_14006F7E9
0x14006f55c  mov     rcx, rdi
0x14006f55f  lea     r8, cs:140000000h
0x14006f566  lea     rdx, ds:3Eh[r15*8]
0x14006f56e  add     rdx, rva __pioinfo[r8+r11*8]
0x14006f576  mov     al, [rdx]
0x14006f578  mov     [rbp+rcx+4Fh+var_50], al
0x14006f57c  inc     rcx
0x14006f57f  inc     rdx
0x14006f582  cmp     rcx, r14
0x14006f585  jl      short loc_14006F576
0x14006f587  test    r9, r9
0x14006f58a  jle     short loc_14006F5A9
0x14006f58c  lea     rcx, [rbp+4Fh+var_50]
0x14006f590  add     rcx, r14; void *
0x14006f593  mov     r8, r9; Size
0x14006f596  mov     rdx, rsi; Src
0x14006f599  call    memmove
0x14006f59e  mov     r10, [rbp+4Fh+var_A8]
0x14006f5a2  lea     r8, cs:140000000h
0x14006f5a9  mov     rdx, rdi
0x14006f5ac  lea     rcx, [rdx+r15*8]
0x14006f5b0  mov     rax, rva __pioinfo[r8+r13*8]
0x14006f5b8  mov     [rcx+rax+3Eh], dil
0x14006f5bd  inc     rdx
0x14006f5c0  cmp     rdx, r14
0x14006f5c3  jl      short loc_14006F5AC
0x14006f5c5  mov     [rbp+4Fh+var_80], rdi
0x14006f5c9  lea     rax, [rbp+4Fh+var_50]
0x14006f5cd  mov     qword ptr [rbp+4Fh+var_78], rax
0x14006f5d1  mov     eax, edi
0x14006f5d3  cmp     r12d, 4
0x14006f5d7  setz    al
0x14006f5da  inc     eax
0x14006f5dc  mov     r12d, eax
0x14006f5df  mov     r8d, eax; char **
0x14006f5e2  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x14006f5e7  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x14006f5eb  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x14006f5ef  lea     rcx, [rbp+4Fh+var_BC]; this
0x14006f5f3  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x14006f5f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006f5fc  jz      loc_14006F875
0x14006f602  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x14006f605  dec     eax
0x14006f607  movsxd  rcx, eax
0x14006f60a  add     rsi, rcx
0x14006f60d  jmp     loc_14006F714
0x14006f612  movzx   eax, byte ptr [rsi]
0x14006f615  movsx   r13, byte ptr [rax+r12+1D8FB0h]
0x14006f61e  lea     ecx, [r13+1]
0x14006f622  mov     r9, [rbp+4Fh+var_B0]
0x14006f626  sub     r9, rsi
0x14006f629  movsxd  rax, ecx
0x14006f62c  cmp     rax, r9
0x14006f62f  jg      loc_14006F81F
0x14006f635  mov     [rbp+4Fh+var_A0], rdi
0x14006f639  mov     qword ptr [rbp+4Fh+var_70], rsi
0x14006f63d  mov     eax, edi
0x14006f63f  cmp     ecx, 4
0x14006f642  setz    al
0x14006f645  inc     eax
0x14006f647  mov     r14d, eax
0x14006f64a  mov     r8d, eax; char **
0x14006f64d  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x14006f652  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x14006f656  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x14006f65a  lea     rcx, [rbp+4Fh+var_BC]; this
0x14006f65e  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x14006f663  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006f667  jz      loc_14006F875
0x14006f66d  add     rsi, r13
0x14006f670  mov     r12d, r14d
0x14006f673  mov     r13, [rbp+4Fh+var_88]
0x14006f677  jmp     loc_14006F714
0x14006f67c  lea     r11, cs:140000000h
0x14006f683  mov     r8, rva __pioinfo[r11+r13*8]
0x14006f68b  mov     cl, [r8+r15*8+3Dh]
0x14006f690  test    cl, 4
0x14006f693  jz      short loc_14006F6B6
0x14006f695  mov     al, [r8+r15*8+3Eh]
0x14006f69a  mov     [rbp+4Fh+var_48], al
0x14006f69d  mov     al, [rsi]
0x14006f69f  mov     [rbp+4Fh+var_47], al
0x14006f6a2  and     cl, 0FBh
0x14006f6a5  mov     [r8+r15*8+3Dh], cl
0x14006f6aa  mov     r8d, 2
0x14006f6b0  lea     rdx, [rbp+4Fh+var_48]
0x14006f6b4  jmp     short loc_14006F6FF
0x14006f6b6  movzx   r9d, byte ptr [rsi]
0x14006f6ba  mov     rax, [r10+18h]
0x14006f6be  mov     rcx, [rax]
0x14006f6c1  cmp     [rcx+r9*2], di
0x14006f6c6  jge     short loc_14006F6F9
0x14006f6c8  lea     r14, [rsi+1]
0x14006f6cc  cmp     r14, [rbp+4Fh+var_B0]
0x14006f6d0  jnb     loc_14006F852
0x14006f6d6  mov     r9, r10; __crt_cached_ptd_host *
0x14006f6d9  mov     r8d, 2; char *
0x14006f6df  mov     rdx, rsi; wchar_t *
0x14006f6e2  lea     rcx, [rbp+4Fh+var_BC]; this
0x14006f6e6  call    _mbtowc_internal
0x14006f6eb  cmp     eax, 0FFFFFFFFh
0x14006f6ee  jz      loc_14006F875
0x14006f6f4  mov     rsi, r14
0x14006f6f7  jmp     short loc_14006F714
0x14006f6f9  mov     r8, r12; char *
0x14006f6fc  mov     rdx, rsi; wchar_t *
0x14006f6ff  mov     r9, r10; __crt_cached_ptd_host *
0x14006f702  lea     rcx, [rbp+4Fh+var_BC]; this
0x14006f706  call    _mbtowc_internal
0x14006f70b  cmp     eax, 0FFFFFFFFh
0x14006f70e  jz      loc_14006F875
0x14006f714  inc     rsi
0x14006f717  mov     [rsp+38h], rdi
0x14006f71c  mov     [rsp+100h+var_D0], rdi
0x14006f721  mov     dword ptr [rsp+100h+var_D8], 5
0x14006f729  lea     rax, [rbp+4Fh+Buffer]
0x14006f72d  mov     [rsp+100h+lpOverlapped], rax
0x14006f732  mov     r9d, r12d
0x14006f735  lea     r8, [rbp+4Fh+var_BC]
0x14006f739  xor     edx, edx
0x14006f73b  mov     ecx, [rbp+4Fh+var_98]
0x14006f73e  call    __acrt_WideCharToMultiByte
0x14006f743  mov     r14d, eax
0x14006f746  test    eax, eax
0x14006f748  jz      loc_14006F875
0x14006f74e  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x14006f751  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14006f756  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14006f75a  mov     r8d, eax; nNumberOfBytesToWrite
0x14006f75d  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x14006f761  mov     r12, [rbp+4Fh+hFile]
0x14006f765  mov     rcx, r12; hFile
0x14006f768  call    cs:__imp_WriteFile
0x14006f76e  test    eax, eax
0x14006f770  jz      loc_14006F86D
0x14006f776  mov     edx, [rbx+8]
0x14006f779  sub     edx, dword ptr [rbp+4Fh+var_90]
0x14006f77c  add     edx, esi
0x14006f77e  mov     [rbx+4], edx
0x14006f781  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14006f785  jb      loc_14006F875
0x14006f78b  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x14006f78f  jnz     short loc_14006F7CF
0x14006f791  mov     eax, 0Dh
0x14006f796  mov     [rbp+4Fh+var_C0], ax
0x14006f79a  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14006f79f  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14006f7a3  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x14006f7a7  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x14006f7ab  mov     rcx, r12; hFile
0x14006f7ae  call    cs:__imp_WriteFile
0x14006f7b4  test    eax, eax
0x14006f7b6  jz      loc_14006F86D
0x14006f7bc  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14006f7c0  jb      loc_14006F875
0x14006f7c6  inc     dword ptr [rbx+8]
0x14006f7c9  inc     dword ptr [rbx+4]
0x14006f7cc  mov     edx, [rbx+4]
0x14006f7cf  cmp     rsi, [rbp+4Fh+var_B0]
0x14006f7d3  jnb     loc_14006F875
0x14006f7d9  mov     r10, [rbp+4Fh+var_A8]
0x14006f7dd  mov     r11, [rbp+4Fh+var_60]
0x14006f7e1  mov     ecx, [rbp+4Fh+var_94]
0x14006f7e4  jmp     loc_14006F4D5
0x14006f7e9  test    r8, r8
0x14006f7ec  jle     short loc_14006F819
0x14006f7ee  sub     rsi, r14
0x14006f7f1  lea     r9, cs:140000000h
0x14006f7f8  lea     rdx, [r14+r15*8]
0x14006f7fc  mov     rcx, rva __pioinfo[r9+r13*8]
0x14006f804  mov     al, [rsi+r14]
0x14006f808  mov     [rdx+rcx+3Eh], al
0x14006f80c  inc     edi
0x14006f80e  inc     r14
0x14006f811  movsxd  rax, edi
0x14006f814  cmp     rax, r8
0x14006f817  jl      short loc_14006F7F8
0x14006f819  add     [rbx+4], r8d
0x14006f81d  jmp     short loc_14006F875
0x14006f81f  test    r9, r9
0x14006f822  jle     short loc_14006F84C
0x14006f824  mov     r8, rdi
0x14006f827  mov     r10, [rbp+4Fh+var_88]
0x14006f82b  lea     rdx, [r8+r15*8]
0x14006f82f  mov     rcx, rva __pioinfo[r12+r10*8]
0x14006f837  mov     al, [r8+rsi]
0x14006f83b  mov     [rdx+rcx+3Eh], al
0x14006f83f  inc     edi
0x14006f841  inc     r8
0x14006f844  movsxd  rax, edi
0x14006f847  cmp     rax, r9
0x14006f84a  jl      short loc_14006F82B
0x14006f84c  add     [rbx+4], r9d
0x14006f850  jmp     short loc_14006F875
0x14006f852  mov     [r8+r15*8+3Eh], r9b
0x14006f857  mov     rax, rva __pioinfo[r11+r13*8]
0x14006f85f  or      byte ptr [rax+r15*8+3Dh], 4
0x14006f865  lea     eax, [rdx+1]
0x14006f868  mov     [rbx+4], eax
0x14006f86b  jmp     short loc_14006F875
0x14006f86d  call    cs:__imp_GetLastError
0x14006f873  mov     [rbx], eax
0x14006f875  mov     rax, rbx
0x14006f878  mov     rcx, [rbp+4Fh+var_38]
0x14006f87c  xor     rcx, rsp; StackCookie
0x14006f87f  call    __security_check_cookie
0x14006f884  mov     rbx, [rsp+100h+arg_0]
0x14006f88c  add     rsp, 0D0h
0x14006f893  pop     r15
0x14006f895  pop     r14
0x14006f897  pop     r13
0x14006f899  pop     r12
  ... truncated ...
```
