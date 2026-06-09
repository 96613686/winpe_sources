# write_double_translated_ansi_nolock

- ea: `0x180014ab0`
- end: `0x180014f43`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180015610`

## callees

- `0x18000b034`
- `0x1800149cc`
- `0x180014ab0`
- `0x18001b18c`
- `0x18001b4b0`
- `0x180032370`
- `0x180060630`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x180014b2f`
- `KERNEL32!GetConsoleOutputCP` at `0x180014b2f`
- `KERNEL32!WriteFile` at `0x180014e0c`
- `KERNEL32!WriteFile` at `0x180014e52`
- `KERNEL32!WriteFile` at `0x180014e0c`
- `KERNEL32!WriteFile` at `0x180014e52`
- `KERNEL32!GetLastError` at `0x180014f11`
- `KERNEL32!GetLastError` at `0x180014f11`

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
0x180014ab0  mov     rax, rsp
0x180014ab3  push    rbp
0x180014ab4  push    rsi
0x180014ab5  push    rdi
0x180014ab6  push    r12
0x180014ab8  push    r13
0x180014aba  push    r14
0x180014abc  push    r15
0x180014abe  lea     rbp, [rax-57h]
0x180014ac2  sub     rsp, 0D0h
0x180014ac9  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180014ad1  mov     [rax+8], rbx
0x180014ad5  mov     rax, cs:__security_cookie
0x180014adc  xor     rax, rsp
0x180014adf  mov     [rbp+4Fh+var_38], rax
0x180014ae3  mov     rsi, r8
0x180014ae6  mov     [rbp+4Fh+var_90], r8
0x180014aea  movsxd  r14, edx
0x180014aed  mov     rbx, rcx
0x180014af0  mov     rax, [rbp+4Fh+arg_20]
0x180014af4  mov     [rbp+4Fh+var_A8], rax
0x180014af8  mov     rax, r14
0x180014afb  mov     r13, r14
0x180014afe  sar     r13, 6
0x180014b02  mov     [rbp+4Fh+var_88], r13
0x180014b06  lea     rcx, cs:180000000h
0x180014b0d  and     eax, 3Fh
0x180014b10  lea     r15, [rax+rax*8]
0x180014b14  mov     rax, rva __pioinfo[rcx+r13*8]
0x180014b1c  mov     rax, [rax+r15*8+28h]
0x180014b21  mov     [rbp+4Fh+hFile], rax
0x180014b25  mov     r12d, r9d
0x180014b28  add     r12, r8
0x180014b2b  mov     [rbp+4Fh+var_B0], r12
0x180014b2f  call    cs:__imp_GetConsoleOutputCP
0x180014b35  mov     [rbp+4Fh+var_98], eax
0x180014b38  xor     edi, edi
0x180014b3a  mov     r10, [rbp+4Fh+var_A8]
0x180014b3e  cmp     [r10+28h], dil
0x180014b42  jnz     short loc_180014B50
0x180014b44  mov     rcx, r10; this
0x180014b47  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180014b4c  mov     r10, [rbp+4Fh+var_A8]
0x180014b50  mov     rcx, [r10+18h]
0x180014b54  mov     ecx, [rcx+0Ch]
0x180014b57  mov     [rbp+4Fh+var_94], ecx
0x180014b5a  xor     eax, eax
0x180014b5c  mov     [rbx], rax
0x180014b5f  mov     [rbx+8], eax
0x180014b62  cmp     [rbp+4Fh+var_90], r12
0x180014b66  jnb     loc_180014F19
0x180014b6c  mov     r11, r14
0x180014b6f  sar     r11, 6
0x180014b73  mov     [rbp+4Fh+var_60], r11
0x180014b77  mov     edx, edi
0x180014b79  mov     al, [rsi]
0x180014b7b  mov     byte ptr [rbp+4Fh+var_C0], al
0x180014b7e  mov     [rbp+4Fh+var_BC], edi
0x180014b81  mov     r12d, 1
0x180014b87  cmp     ecx, 0FDE9h
0x180014b8d  jnz     loc_180014D20
0x180014b93  mov     edx, edi
0x180014b95  mov     r14, rdi
0x180014b98  lea     r12, cs:180000000h
0x180014b9f  lea     rcx, ds:3Eh[r15*8]
0x180014ba7  add     rcx, rva __pioinfo[r12+r11*8]
0x180014baf  cmp     [rcx], dil
0x180014bb2  jz      short loc_180014BC2
0x180014bb4  inc     edx
0x180014bb6  inc     r14
0x180014bb9  inc     rcx
0x180014bbc  cmp     r14, 5
0x180014bc0  jl      short loc_180014BAF
0x180014bc2  test    r14, r14
0x180014bc5  jle     loc_180014CB6
0x180014bcb  mov     rax, rva __pioinfo[r12+r13*8]
0x180014bd3  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x180014bd9  movsx   r12d, byte ptr [rcx+r12+77AA0h]
0x180014be2  inc     r12d
0x180014be5  mov     eax, r12d
0x180014be8  sub     eax, edx
0x180014bea  mov     dword ptr [rbp+4Fh+var_A0], eax
0x180014bed  mov     r8, [rbp+4Fh+var_B0]
0x180014bf1  sub     r8, rsi
0x180014bf4  movsxd  r9, eax
0x180014bf7  cmp     r9, r8
0x180014bfa  jg      loc_180014E8D
0x180014c00  mov     rcx, rdi
0x180014c03  lea     r8, cs:180000000h
0x180014c0a  lea     rdx, ds:3Eh[r15*8]
0x180014c12  add     rdx, rva __pioinfo[r8+r11*8]
0x180014c1a  mov     al, [rdx]
0x180014c1c  mov     [rbp+rcx+4Fh+var_50], al
0x180014c20  inc     rcx
0x180014c23  inc     rdx
0x180014c26  cmp     rcx, r14
0x180014c29  jl      short loc_180014C1A
0x180014c2b  test    r9, r9
0x180014c2e  jle     short loc_180014C4D
0x180014c30  lea     rcx, [rbp+4Fh+var_50]
0x180014c34  add     rcx, r14; void *
0x180014c37  mov     r8, r9; Size
0x180014c3a  mov     rdx, rsi; Src
0x180014c3d  call    memmove
0x180014c42  mov     r10, [rbp+4Fh+var_A8]
0x180014c46  lea     r8, cs:180000000h
0x180014c4d  mov     rdx, rdi
0x180014c50  lea     rcx, [rdx+r15*8]
0x180014c54  mov     rax, rva __pioinfo[r8+r13*8]
0x180014c5c  mov     [rcx+rax+3Eh], dil
0x180014c61  inc     rdx
0x180014c64  cmp     rdx, r14
0x180014c67  jl      short loc_180014C50
0x180014c69  mov     [rbp+4Fh+var_80], rdi
0x180014c6d  lea     rax, [rbp+4Fh+var_50]
0x180014c71  mov     qword ptr [rbp+4Fh+var_78], rax
0x180014c75  mov     eax, edi
0x180014c77  cmp     r12d, 4
0x180014c7b  setz    al
0x180014c7e  inc     eax
0x180014c80  mov     r12d, eax
0x180014c83  mov     r8d, eax; char **
0x180014c86  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180014c8b  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x180014c8f  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x180014c93  lea     rcx, [rbp+4Fh+var_BC]; this
0x180014c97  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180014c9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014ca0  jz      loc_180014F19
0x180014ca6  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x180014ca9  dec     eax
0x180014cab  movsxd  rcx, eax
0x180014cae  add     rsi, rcx
0x180014cb1  jmp     loc_180014DB8
0x180014cb6  movzx   eax, byte ptr [rsi]
0x180014cb9  movsx   r13, byte ptr [rax+r12+77AA0h]
0x180014cc2  lea     ecx, [r13+1]
0x180014cc6  mov     r9, [rbp+4Fh+var_B0]
0x180014cca  sub     r9, rsi
0x180014ccd  movsxd  rax, ecx
0x180014cd0  cmp     rax, r9
0x180014cd3  jg      loc_180014EC3
0x180014cd9  mov     [rbp+4Fh+var_A0], rdi
0x180014cdd  mov     qword ptr [rbp+4Fh+var_70], rsi
0x180014ce1  mov     eax, edi
0x180014ce3  cmp     ecx, 4
0x180014ce6  setz    al
0x180014ce9  inc     eax
0x180014ceb  mov     r14d, eax
0x180014cee  mov     r8d, eax; char **
0x180014cf1  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180014cf6  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x180014cfa  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x180014cfe  lea     rcx, [rbp+4Fh+var_BC]; this
0x180014d02  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180014d07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014d0b  jz      loc_180014F19
0x180014d11  add     rsi, r13
0x180014d14  mov     r12d, r14d
0x180014d17  mov     r13, [rbp+4Fh+var_88]
0x180014d1b  jmp     loc_180014DB8
0x180014d20  lea     r11, cs:180000000h
0x180014d27  mov     r8, rva __pioinfo[r11+r13*8]
0x180014d2f  mov     cl, [r8+r15*8+3Dh]
0x180014d34  test    cl, 4
0x180014d37  jz      short loc_180014D5A
0x180014d39  mov     al, [r8+r15*8+3Eh]
0x180014d3e  mov     [rbp+4Fh+var_48], al
0x180014d41  mov     al, [rsi]
0x180014d43  mov     [rbp+4Fh+var_47], al
0x180014d46  and     cl, 0FBh
0x180014d49  mov     [r8+r15*8+3Dh], cl
0x180014d4e  mov     r8d, 2
0x180014d54  lea     rdx, [rbp+4Fh+var_48]
0x180014d58  jmp     short loc_180014DA3
0x180014d5a  movzx   r9d, byte ptr [rsi]
0x180014d5e  mov     rax, [r10+18h]
0x180014d62  mov     rcx, [rax]
0x180014d65  cmp     [rcx+r9*2], di
0x180014d6a  jge     short loc_180014D9D
0x180014d6c  lea     r14, [rsi+1]
0x180014d70  cmp     r14, [rbp+4Fh+var_B0]
0x180014d74  jnb     loc_180014EF6
0x180014d7a  mov     r9, r10; __crt_cached_ptd_host *
0x180014d7d  mov     r8d, 2; char *
0x180014d83  mov     rdx, rsi; wchar_t *
0x180014d86  lea     rcx, [rbp+4Fh+var_BC]; this
0x180014d8a  call    _mbtowc_internal
0x180014d8f  cmp     eax, 0FFFFFFFFh
0x180014d92  jz      loc_180014F19
0x180014d98  mov     rsi, r14
0x180014d9b  jmp     short loc_180014DB8
0x180014d9d  mov     r8, r12; char *
0x180014da0  mov     rdx, rsi; wchar_t *
0x180014da3  mov     r9, r10; __crt_cached_ptd_host *
0x180014da6  lea     rcx, [rbp+4Fh+var_BC]; this
0x180014daa  call    _mbtowc_internal
0x180014daf  cmp     eax, 0FFFFFFFFh
0x180014db2  jz      loc_180014F19
0x180014db8  inc     rsi
0x180014dbb  mov     [rsp+38h], rdi
0x180014dc0  mov     [rsp+100h+var_D0], rdi
0x180014dc5  mov     dword ptr [rsp+100h+var_D8], 5
0x180014dcd  lea     rax, [rbp+4Fh+Buffer]
0x180014dd1  mov     [rsp+100h+lpOverlapped], rax
0x180014dd6  mov     r9d, r12d
0x180014dd9  lea     r8, [rbp+4Fh+var_BC]
0x180014ddd  xor     edx, edx
0x180014ddf  mov     ecx, [rbp+4Fh+var_98]
0x180014de2  call    __acrt_WideCharToMultiByte
0x180014de7  mov     r14d, eax
0x180014dea  test    eax, eax
0x180014dec  jz      loc_180014F19
0x180014df2  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x180014df5  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x180014dfa  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014dfe  mov     r8d, eax; nNumberOfBytesToWrite
0x180014e01  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x180014e05  mov     r12, [rbp+4Fh+hFile]
0x180014e09  mov     rcx, r12; hFile
0x180014e0c  call    cs:__imp_WriteFile
0x180014e12  test    eax, eax
0x180014e14  jz      loc_180014F11
0x180014e1a  mov     edx, [rbx+8]
0x180014e1d  sub     edx, dword ptr [rbp+4Fh+var_90]
0x180014e20  add     edx, esi
0x180014e22  mov     [rbx+4], edx
0x180014e25  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x180014e29  jb      loc_180014F19
0x180014e2f  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x180014e33  jnz     short loc_180014E73
0x180014e35  mov     eax, 0Dh
0x180014e3a  mov     [rbp+4Fh+var_C0], ax
0x180014e3e  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x180014e43  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014e47  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x180014e4b  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x180014e4f  mov     rcx, r12; hFile
0x180014e52  call    cs:__imp_WriteFile
0x180014e58  test    eax, eax
0x180014e5a  jz      loc_180014F11
0x180014e60  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x180014e64  jb      loc_180014F19
0x180014e6a  inc     dword ptr [rbx+8]
0x180014e6d  inc     dword ptr [rbx+4]
0x180014e70  mov     edx, [rbx+4]
0x180014e73  cmp     rsi, [rbp+4Fh+var_B0]
0x180014e77  jnb     loc_180014F19
0x180014e7d  mov     r10, [rbp+4Fh+var_A8]
0x180014e81  mov     r11, [rbp+4Fh+var_60]
0x180014e85  mov     ecx, [rbp+4Fh+var_94]
0x180014e88  jmp     loc_180014B79
0x180014e8d  test    r8, r8
0x180014e90  jle     short loc_180014EBD
0x180014e92  sub     rsi, r14
0x180014e95  lea     r9, cs:180000000h
0x180014e9c  lea     rdx, [r14+r15*8]
0x180014ea0  mov     rcx, rva __pioinfo[r9+r13*8]
0x180014ea8  mov     al, [rsi+r14]
0x180014eac  mov     [rdx+rcx+3Eh], al
0x180014eb0  inc     edi
0x180014eb2  inc     r14
0x180014eb5  movsxd  rax, edi
0x180014eb8  cmp     rax, r8
0x180014ebb  jl      short loc_180014E9C
0x180014ebd  add     [rbx+4], r8d
0x180014ec1  jmp     short loc_180014F19
0x180014ec3  test    r9, r9
0x180014ec6  jle     short loc_180014EF0
0x180014ec8  mov     r8, rdi
0x180014ecb  mov     r10, [rbp+4Fh+var_88]
0x180014ecf  lea     rdx, [r8+r15*8]
0x180014ed3  mov     rcx, rva __pioinfo[r12+r10*8]
0x180014edb  mov     al, [r8+rsi]
0x180014edf  mov     [rdx+rcx+3Eh], al
0x180014ee3  inc     edi
0x180014ee5  inc     r8
0x180014ee8  movsxd  rax, edi
0x180014eeb  cmp     rax, r9
0x180014eee  jl      short loc_180014ECF
0x180014ef0  add     [rbx+4], r9d
0x180014ef4  jmp     short loc_180014F19
0x180014ef6  mov     [r8+r15*8+3Eh], r9b
0x180014efb  mov     rax, rva __pioinfo[r11+r13*8]
0x180014f03  or      byte ptr [rax+r15*8+3Dh], 4
0x180014f09  lea     eax, [rdx+1]
0x180014f0c  mov     [rbx+4], eax
0x180014f0f  jmp     short loc_180014F19
0x180014f11  call    cs:__imp_GetLastError
0x180014f17  mov     [rbx], eax
0x180014f19  mov     rax, rbx
0x180014f1c  mov     rcx, [rbp+4Fh+var_38]
0x180014f20  xor     rcx, rsp; StackCookie
0x180014f23  call    __security_check_cookie
0x180014f28  mov     rbx, [rsp+100h+arg_0]
0x180014f30  add     rsp, 0D0h
0x180014f37  pop     r15
0x180014f39  pop     r14
0x180014f3b  pop     r13
0x180014f3d  pop     r12
  ... truncated ...
```
