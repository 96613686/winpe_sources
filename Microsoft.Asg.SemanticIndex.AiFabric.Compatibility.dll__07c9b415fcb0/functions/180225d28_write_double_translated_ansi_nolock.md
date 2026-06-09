# write_double_translated_ansi_nolock

- ea: `0x180225d28`
- end: `0x1802261bb`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180226674`

## callees

- `0x1801f7110`
- `0x18020b7f0`
- `0x18021a7c0`
- `0x18021ac1c`
- `0x18021f770`
- `0x180225d28`
- `0x1802421a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180226189`
- `KERNEL32!GetLastError` at `0x180226189`
- `KERNEL32!GetConsoleOutputCP` at `0x180225da7`
- `KERNEL32!GetConsoleOutputCP` at `0x180225da7`
- `KERNEL32!WriteFile` at `0x180226084`
- `KERNEL32!WriteFile` at `0x1802260ca`
- `KERNEL32!WriteFile` at `0x180226084`
- `KERNEL32!WriteFile` at `0x1802260ca`

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
0x180225d28  mov     rax, rsp
0x180225d2b  push    rbp
0x180225d2c  push    rsi
0x180225d2d  push    rdi
0x180225d2e  push    r12
0x180225d30  push    r13
0x180225d32  push    r14
0x180225d34  push    r15
0x180225d36  lea     rbp, [rax-57h]
0x180225d3a  sub     rsp, 0D0h
0x180225d41  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180225d49  mov     [rax+8], rbx
0x180225d4d  mov     rax, cs:__security_cookie
0x180225d54  xor     rax, rsp
0x180225d57  mov     [rbp+4Fh+var_38], rax
0x180225d5b  mov     rsi, r8
0x180225d5e  mov     [rbp+4Fh+var_90], r8
0x180225d62  movsxd  r14, edx
0x180225d65  mov     rbx, rcx
0x180225d68  mov     rax, [rbp+4Fh+arg_20]
0x180225d6c  mov     [rbp+4Fh+var_A8], rax
0x180225d70  mov     rax, r14
0x180225d73  mov     r13, r14
0x180225d76  sar     r13, 6
0x180225d7a  mov     [rbp+4Fh+var_88], r13
0x180225d7e  lea     rcx, cs:180000000h
0x180225d85  and     eax, 3Fh
0x180225d88  lea     r15, [rax+rax*8]
0x180225d8c  mov     rax, rva __pioinfo[rcx+r13*8]
0x180225d94  mov     rax, [rax+r15*8+28h]
0x180225d99  mov     [rbp+4Fh+hFile], rax
0x180225d9d  mov     r12d, r9d
0x180225da0  add     r12, r8
0x180225da3  mov     [rbp+4Fh+var_B0], r12
0x180225da7  call    cs:__imp_GetConsoleOutputCP
0x180225dad  mov     [rbp+4Fh+var_98], eax
0x180225db0  xor     edi, edi
0x180225db2  mov     r10, [rbp+4Fh+var_A8]
0x180225db6  cmp     [r10+28h], dil
0x180225dba  jnz     short loc_180225DC8
0x180225dbc  mov     rcx, r10; this
0x180225dbf  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180225dc4  mov     r10, [rbp+4Fh+var_A8]
0x180225dc8  mov     rcx, [r10+18h]
0x180225dcc  mov     ecx, [rcx+0Ch]
0x180225dcf  mov     [rbp+4Fh+var_94], ecx
0x180225dd2  xor     eax, eax
0x180225dd4  mov     [rbx], rax
0x180225dd7  mov     [rbx+8], eax
0x180225dda  cmp     [rbp+4Fh+var_90], r12
0x180225dde  jnb     loc_180226191
0x180225de4  mov     r11, r14
0x180225de7  sar     r11, 6
0x180225deb  mov     [rbp+4Fh+var_60], r11
0x180225def  mov     edx, edi
0x180225df1  mov     al, [rsi]
0x180225df3  mov     byte ptr [rbp+4Fh+var_C0], al
0x180225df6  mov     [rbp+4Fh+var_BC], edi
0x180225df9  mov     r12d, 1
0x180225dff  cmp     ecx, 0FDE9h
0x180225e05  jnz     loc_180225F98
0x180225e0b  mov     edx, edi
0x180225e0d  mov     r14, rdi
0x180225e10  lea     r12, cs:180000000h
0x180225e17  lea     rcx, ds:3Eh[r15*8]
0x180225e1f  add     rcx, rva __pioinfo[r12+r11*8]
0x180225e27  cmp     [rcx], dil
0x180225e2a  jz      short loc_180225E3A
0x180225e2c  inc     edx
0x180225e2e  inc     r14
0x180225e31  inc     rcx
0x180225e34  cmp     r14, 5
0x180225e38  jl      short loc_180225E27
0x180225e3a  test    r14, r14
0x180225e3d  jle     loc_180225F2E
0x180225e43  mov     rax, rva __pioinfo[r12+r13*8]
0x180225e4b  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x180225e51  movsx   r12d, byte ptr [rcx+r12+33C1D0h]
0x180225e5a  inc     r12d
0x180225e5d  mov     eax, r12d
0x180225e60  sub     eax, edx
0x180225e62  mov     dword ptr [rbp+4Fh+var_A0], eax
0x180225e65  mov     r8, [rbp+4Fh+var_B0]
0x180225e69  sub     r8, rsi
0x180225e6c  movsxd  r9, eax
0x180225e6f  cmp     r9, r8
0x180225e72  jg      loc_180226105
0x180225e78  mov     rcx, rdi
0x180225e7b  lea     r8, cs:180000000h
0x180225e82  lea     rdx, ds:3Eh[r15*8]
0x180225e8a  add     rdx, rva __pioinfo[r8+r11*8]
0x180225e92  mov     al, [rdx]
0x180225e94  mov     [rbp+rcx+4Fh+var_50], al
0x180225e98  inc     rcx
0x180225e9b  inc     rdx
0x180225e9e  cmp     rcx, r14
0x180225ea1  jl      short loc_180225E92
0x180225ea3  test    r9, r9
0x180225ea6  jle     short loc_180225EC5
0x180225ea8  lea     rcx, [rbp+4Fh+var_50]
0x180225eac  add     rcx, r14; void *
0x180225eaf  mov     r8, r9; Size
0x180225eb2  mov     rdx, rsi; Src
0x180225eb5  call    memmove
0x180225eba  mov     r10, [rbp+4Fh+var_A8]
0x180225ebe  lea     r8, cs:180000000h
0x180225ec5  mov     rdx, rdi
0x180225ec8  lea     rcx, [rdx+r15*8]
0x180225ecc  mov     rax, rva __pioinfo[r8+r13*8]
0x180225ed4  mov     [rcx+rax+3Eh], dil
0x180225ed9  inc     rdx
0x180225edc  cmp     rdx, r14
0x180225edf  jl      short loc_180225EC8
0x180225ee1  mov     [rbp+4Fh+var_80], rdi
0x180225ee5  lea     rax, [rbp+4Fh+var_50]
0x180225ee9  mov     qword ptr [rbp+4Fh+var_78], rax
0x180225eed  mov     eax, edi
0x180225eef  cmp     r12d, 4
0x180225ef3  setz    al
0x180225ef6  inc     eax
0x180225ef8  mov     r12d, eax
0x180225efb  mov     r8d, eax; char **
0x180225efe  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180225f03  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x180225f07  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x180225f0b  lea     rcx, [rbp+4Fh+var_BC]; this
0x180225f0f  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180225f14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180225f18  jz      loc_180226191
0x180225f1e  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x180225f21  dec     eax
0x180225f23  movsxd  rcx, eax
0x180225f26  add     rsi, rcx
0x180225f29  jmp     loc_180226030
0x180225f2e  movzx   eax, byte ptr [rsi]
0x180225f31  movsx   r13, byte ptr [rax+r12+33C1D0h]
0x180225f3a  lea     ecx, [r13+1]
0x180225f3e  mov     r9, [rbp+4Fh+var_B0]
0x180225f42  sub     r9, rsi
0x180225f45  movsxd  rax, ecx
0x180225f48  cmp     rax, r9
0x180225f4b  jg      loc_18022613B
0x180225f51  mov     [rbp+4Fh+var_A0], rdi
0x180225f55  mov     qword ptr [rbp+4Fh+var_70], rsi
0x180225f59  mov     eax, edi
0x180225f5b  cmp     ecx, 4
0x180225f5e  setz    al
0x180225f61  inc     eax
0x180225f63  mov     r14d, eax
0x180225f66  mov     r8d, eax; char **
0x180225f69  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180225f6e  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x180225f72  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x180225f76  lea     rcx, [rbp+4Fh+var_BC]; this
0x180225f7a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180225f7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180225f83  jz      loc_180226191
0x180225f89  add     rsi, r13
0x180225f8c  mov     r12d, r14d
0x180225f8f  mov     r13, [rbp+4Fh+var_88]
0x180225f93  jmp     loc_180226030
0x180225f98  lea     r11, cs:180000000h
0x180225f9f  mov     r8, rva __pioinfo[r11+r13*8]
0x180225fa7  mov     cl, [r8+r15*8+3Dh]
0x180225fac  test    cl, 4
0x180225faf  jz      short loc_180225FD2
0x180225fb1  mov     al, [r8+r15*8+3Eh]
0x180225fb6  mov     [rbp+4Fh+var_48], al
0x180225fb9  mov     al, [rsi]
0x180225fbb  mov     [rbp+4Fh+var_47], al
0x180225fbe  and     cl, 0FBh
0x180225fc1  mov     [r8+r15*8+3Dh], cl
0x180225fc6  mov     r8d, 2
0x180225fcc  lea     rdx, [rbp+4Fh+var_48]
0x180225fd0  jmp     short loc_18022601B
0x180225fd2  movzx   r9d, byte ptr [rsi]
0x180225fd6  mov     rax, [r10+18h]
0x180225fda  mov     rcx, [rax]
0x180225fdd  cmp     [rcx+r9*2], di
0x180225fe2  jge     short loc_180226015
0x180225fe4  lea     r14, [rsi+1]
0x180225fe8  cmp     r14, [rbp+4Fh+var_B0]
0x180225fec  jnb     loc_18022616E
0x180225ff2  mov     r9, r10; __crt_cached_ptd_host *
0x180225ff5  mov     r8d, 2; char *
0x180225ffb  mov     rdx, rsi; wchar_t *
0x180225ffe  lea     rcx, [rbp+4Fh+var_BC]; this
0x180226002  call    _mbtowc_internal
0x180226007  cmp     eax, 0FFFFFFFFh
0x18022600a  jz      loc_180226191
0x180226010  mov     rsi, r14
0x180226013  jmp     short loc_180226030
0x180226015  mov     r8, r12; char *
0x180226018  mov     rdx, rsi; wchar_t *
0x18022601b  mov     r9, r10; __crt_cached_ptd_host *
0x18022601e  lea     rcx, [rbp+4Fh+var_BC]; this
0x180226022  call    _mbtowc_internal
0x180226027  cmp     eax, 0FFFFFFFFh
0x18022602a  jz      loc_180226191
0x180226030  inc     rsi
0x180226033  mov     [rsp+38h], rdi
0x180226038  mov     [rsp+100h+var_D0], rdi
0x18022603d  mov     dword ptr [rsp+100h+var_D8], 5
0x180226045  lea     rax, [rbp+4Fh+Buffer]
0x180226049  mov     [rsp+100h+lpOverlapped], rax
0x18022604e  mov     r9d, r12d
0x180226051  lea     r8, [rbp+4Fh+var_BC]
0x180226055  xor     edx, edx
0x180226057  mov     ecx, [rbp+4Fh+var_98]
0x18022605a  call    __acrt_WideCharToMultiByte
0x18022605f  mov     r14d, eax
0x180226062  test    eax, eax
0x180226064  jz      loc_180226191
0x18022606a  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x18022606d  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x180226072  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180226076  mov     r8d, eax; nNumberOfBytesToWrite
0x180226079  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x18022607d  mov     r12, [rbp+4Fh+hFile]
0x180226081  mov     rcx, r12; hFile
0x180226084  call    cs:__imp_WriteFile
0x18022608a  test    eax, eax
0x18022608c  jz      loc_180226189
0x180226092  mov     edx, [rbx+8]
0x180226095  sub     edx, dword ptr [rbp+4Fh+var_90]
0x180226098  add     edx, esi
0x18022609a  mov     [rbx+4], edx
0x18022609d  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x1802260a1  jb      loc_180226191
0x1802260a7  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x1802260ab  jnz     short loc_1802260EB
0x1802260ad  mov     eax, 0Dh
0x1802260b2  mov     [rbp+4Fh+var_C0], ax
0x1802260b6  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1802260bb  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802260bf  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x1802260c3  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x1802260c7  mov     rcx, r12; hFile
0x1802260ca  call    cs:__imp_WriteFile
0x1802260d0  test    eax, eax
0x1802260d2  jz      loc_180226189
0x1802260d8  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x1802260dc  jb      loc_180226191
0x1802260e2  inc     dword ptr [rbx+8]
0x1802260e5  inc     dword ptr [rbx+4]
0x1802260e8  mov     edx, [rbx+4]
0x1802260eb  cmp     rsi, [rbp+4Fh+var_B0]
0x1802260ef  jnb     loc_180226191
0x1802260f5  mov     r10, [rbp+4Fh+var_A8]
0x1802260f9  mov     r11, [rbp+4Fh+var_60]
0x1802260fd  mov     ecx, [rbp+4Fh+var_94]
0x180226100  jmp     loc_180225DF1
0x180226105  test    r8, r8
0x180226108  jle     short loc_180226135
0x18022610a  sub     rsi, r14
0x18022610d  lea     r9, cs:180000000h
0x180226114  lea     rdx, [r14+r15*8]
0x180226118  mov     rcx, rva __pioinfo[r9+r13*8]
0x180226120  mov     al, [rsi+r14]
0x180226124  mov     [rdx+rcx+3Eh], al
0x180226128  inc     edi
0x18022612a  inc     r14
0x18022612d  movsxd  rax, edi
0x180226130  cmp     rax, r8
0x180226133  jl      short loc_180226114
0x180226135  add     [rbx+4], r8d
0x180226139  jmp     short loc_180226191
0x18022613b  test    r9, r9
0x18022613e  jle     short loc_180226168
0x180226140  mov     r8, rdi
0x180226143  mov     r10, [rbp+4Fh+var_88]
0x180226147  lea     rdx, [r8+r15*8]
0x18022614b  mov     rcx, rva __pioinfo[r12+r10*8]
0x180226153  mov     al, [r8+rsi]
0x180226157  mov     [rdx+rcx+3Eh], al
0x18022615b  inc     edi
0x18022615d  inc     r8
0x180226160  movsxd  rax, edi
0x180226163  cmp     rax, r9
0x180226166  jl      short loc_180226147
0x180226168  add     [rbx+4], r9d
0x18022616c  jmp     short loc_180226191
0x18022616e  mov     [r8+r15*8+3Eh], r9b
0x180226173  mov     rax, rva __pioinfo[r11+r13*8]
0x18022617b  or      byte ptr [rax+r15*8+3Dh], 4
0x180226181  lea     eax, [rdx+1]
0x180226184  mov     [rbx+4], eax
0x180226187  jmp     short loc_180226191
0x180226189  call    cs:__imp_GetLastError
0x18022618f  mov     [rbx], eax
0x180226191  mov     rax, rbx
0x180226194  mov     rcx, [rbp+4Fh+var_38]
0x180226198  xor     rcx, rsp; StackCookie
0x18022619b  call    __security_check_cookie
0x1802261a0  mov     rbx, [rsp+100h+arg_0]
0x1802261a8  add     rsp, 0D0h
0x1802261af  pop     r15
0x1802261b1  pop     r14
0x1802261b3  pop     r13
0x1802261b5  pop     r12
  ... truncated ...
```
