# write_double_translated_ansi_nolock

- ea: `0x180015210`
- end: `0x1800156a3`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180015d70`

## callees

- `0x180002810`
- `0x18000b794`
- `0x18001512c`
- `0x180015210`
- `0x18001b8ec`
- `0x18001bc10`
- `0x180060910`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x18001528f`
- `KERNEL32!GetConsoleOutputCP` at `0x18001528f`
- `KERNEL32!WriteFile` at `0x18001556c`
- `KERNEL32!WriteFile` at `0x1800155b2`
- `KERNEL32!WriteFile` at `0x18001556c`
- `KERNEL32!WriteFile` at `0x1800155b2`
- `KERNEL32!GetLastError` at `0x180015671`
- `KERNEL32!GetLastError` at `0x180015671`

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
0x180015210  mov     rax, rsp
0x180015213  push    rbp
0x180015214  push    rsi
0x180015215  push    rdi
0x180015216  push    r12
0x180015218  push    r13
0x18001521a  push    r14
0x18001521c  push    r15
0x18001521e  lea     rbp, [rax-57h]
0x180015222  sub     rsp, 0D0h
0x180015229  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180015231  mov     [rax+8], rbx
0x180015235  mov     rax, cs:__security_cookie
0x18001523c  xor     rax, rsp
0x18001523f  mov     [rbp+4Fh+var_38], rax
0x180015243  mov     rsi, r8
0x180015246  mov     [rbp+4Fh+var_90], r8
0x18001524a  movsxd  r14, edx
0x18001524d  mov     rbx, rcx
0x180015250  mov     rax, [rbp+4Fh+arg_20]
0x180015254  mov     [rbp+4Fh+var_A8], rax
0x180015258  mov     rax, r14
0x18001525b  mov     r13, r14
0x18001525e  sar     r13, 6
0x180015262  mov     [rbp+4Fh+var_88], r13
0x180015266  lea     rcx, cs:180000000h
0x18001526d  and     eax, 3Fh
0x180015270  lea     r15, [rax+rax*8]
0x180015274  mov     rax, rva __pioinfo[rcx+r13*8]
0x18001527c  mov     rax, [rax+r15*8+28h]
0x180015281  mov     [rbp+4Fh+hFile], rax
0x180015285  mov     r12d, r9d
0x180015288  add     r12, r8
0x18001528b  mov     [rbp+4Fh+var_B0], r12
0x18001528f  call    cs:__imp_GetConsoleOutputCP
0x180015295  mov     [rbp+4Fh+var_98], eax
0x180015298  xor     edi, edi
0x18001529a  mov     r10, [rbp+4Fh+var_A8]
0x18001529e  cmp     [r10+28h], dil
0x1800152a2  jnz     short loc_1800152B0
0x1800152a4  mov     rcx, r10; this
0x1800152a7  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800152ac  mov     r10, [rbp+4Fh+var_A8]
0x1800152b0  mov     rcx, [r10+18h]
0x1800152b4  mov     ecx, [rcx+0Ch]
0x1800152b7  mov     [rbp+4Fh+var_94], ecx
0x1800152ba  xor     eax, eax
0x1800152bc  mov     [rbx], rax
0x1800152bf  mov     [rbx+8], eax
0x1800152c2  cmp     [rbp+4Fh+var_90], r12
0x1800152c6  jnb     loc_180015679
0x1800152cc  mov     r11, r14
0x1800152cf  sar     r11, 6
0x1800152d3  mov     [rbp+4Fh+var_60], r11
0x1800152d7  mov     edx, edi
0x1800152d9  mov     al, [rsi]
0x1800152db  mov     byte ptr [rbp+4Fh+var_C0], al
0x1800152de  mov     [rbp+4Fh+var_BC], edi
0x1800152e1  mov     r12d, 1
0x1800152e7  cmp     ecx, 0FDE9h
0x1800152ed  jnz     loc_180015480
0x1800152f3  mov     edx, edi
0x1800152f5  mov     r14, rdi
0x1800152f8  lea     r12, cs:180000000h
0x1800152ff  lea     rcx, ds:3Eh[r15*8]
0x180015307  add     rcx, rva __pioinfo[r12+r11*8]
0x18001530f  cmp     [rcx], dil
0x180015312  jz      short loc_180015322
0x180015314  inc     edx
0x180015316  inc     r14
0x180015319  inc     rcx
0x18001531c  cmp     r14, 5
0x180015320  jl      short loc_18001530F
0x180015322  test    r14, r14
0x180015325  jle     loc_180015416
0x18001532b  mov     rax, rva __pioinfo[r12+r13*8]
0x180015333  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x180015339  movsx   r12d, byte ptr [rcx+r12+7AFE0h]
0x180015342  inc     r12d
0x180015345  mov     eax, r12d
0x180015348  sub     eax, edx
0x18001534a  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18001534d  mov     r8, [rbp+4Fh+var_B0]
0x180015351  sub     r8, rsi
0x180015354  movsxd  r9, eax
0x180015357  cmp     r9, r8
0x18001535a  jg      loc_1800155ED
0x180015360  mov     rcx, rdi
0x180015363  lea     r8, cs:180000000h
0x18001536a  lea     rdx, ds:3Eh[r15*8]
0x180015372  add     rdx, rva __pioinfo[r8+r11*8]
0x18001537a  mov     al, [rdx]
0x18001537c  mov     [rbp+rcx+4Fh+var_50], al
0x180015380  inc     rcx
0x180015383  inc     rdx
0x180015386  cmp     rcx, r14
0x180015389  jl      short loc_18001537A
0x18001538b  test    r9, r9
0x18001538e  jle     short loc_1800153AD
0x180015390  lea     rcx, [rbp+4Fh+var_50]
0x180015394  add     rcx, r14; void *
0x180015397  mov     r8, r9; Size
0x18001539a  mov     rdx, rsi; Src
0x18001539d  call    memmove
0x1800153a2  mov     r10, [rbp+4Fh+var_A8]
0x1800153a6  lea     r8, cs:180000000h
0x1800153ad  mov     rdx, rdi
0x1800153b0  lea     rcx, [rdx+r15*8]
0x1800153b4  mov     rax, rva __pioinfo[r8+r13*8]
0x1800153bc  mov     [rcx+rax+3Eh], dil
0x1800153c1  inc     rdx
0x1800153c4  cmp     rdx, r14
0x1800153c7  jl      short loc_1800153B0
0x1800153c9  mov     [rbp+4Fh+var_80], rdi
0x1800153cd  lea     rax, [rbp+4Fh+var_50]
0x1800153d1  mov     qword ptr [rbp+4Fh+var_78], rax
0x1800153d5  mov     eax, edi
0x1800153d7  cmp     r12d, 4
0x1800153db  setz    al
0x1800153de  inc     eax
0x1800153e0  mov     r12d, eax
0x1800153e3  mov     r8d, eax; char **
0x1800153e6  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x1800153eb  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x1800153ef  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x1800153f3  lea     rcx, [rbp+4Fh+var_BC]; this
0x1800153f7  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x1800153fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015400  jz      loc_180015679
0x180015406  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x180015409  dec     eax
0x18001540b  movsxd  rcx, eax
0x18001540e  add     rsi, rcx
0x180015411  jmp     loc_180015518
0x180015416  movzx   eax, byte ptr [rsi]
0x180015419  movsx   r13, byte ptr [rax+r12+7AFE0h]
0x180015422  lea     ecx, [r13+1]
0x180015426  mov     r9, [rbp+4Fh+var_B0]
0x18001542a  sub     r9, rsi
0x18001542d  movsxd  rax, ecx
0x180015430  cmp     rax, r9
0x180015433  jg      loc_180015623
0x180015439  mov     [rbp+4Fh+var_A0], rdi
0x18001543d  mov     qword ptr [rbp+4Fh+var_70], rsi
0x180015441  mov     eax, edi
0x180015443  cmp     ecx, 4
0x180015446  setz    al
0x180015449  inc     eax
0x18001544b  mov     r14d, eax
0x18001544e  mov     r8d, eax; char **
0x180015451  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x180015456  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x18001545a  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x18001545e  lea     rcx, [rbp+4Fh+var_BC]; this
0x180015462  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180015467  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001546b  jz      loc_180015679
0x180015471  add     rsi, r13
0x180015474  mov     r12d, r14d
0x180015477  mov     r13, [rbp+4Fh+var_88]
0x18001547b  jmp     loc_180015518
0x180015480  lea     r11, cs:180000000h
0x180015487  mov     r8, rva __pioinfo[r11+r13*8]
0x18001548f  mov     cl, [r8+r15*8+3Dh]
0x180015494  test    cl, 4
0x180015497  jz      short loc_1800154BA
0x180015499  mov     al, [r8+r15*8+3Eh]
0x18001549e  mov     [rbp+4Fh+var_48], al
0x1800154a1  mov     al, [rsi]
0x1800154a3  mov     [rbp+4Fh+var_47], al
0x1800154a6  and     cl, 0FBh
0x1800154a9  mov     [r8+r15*8+3Dh], cl
0x1800154ae  mov     r8d, 2
0x1800154b4  lea     rdx, [rbp+4Fh+var_48]
0x1800154b8  jmp     short loc_180015503
0x1800154ba  movzx   r9d, byte ptr [rsi]
0x1800154be  mov     rax, [r10+18h]
0x1800154c2  mov     rcx, [rax]
0x1800154c5  cmp     [rcx+r9*2], di
0x1800154ca  jge     short loc_1800154FD
0x1800154cc  lea     r14, [rsi+1]
0x1800154d0  cmp     r14, [rbp+4Fh+var_B0]
0x1800154d4  jnb     loc_180015656
0x1800154da  mov     r9, r10; __crt_cached_ptd_host *
0x1800154dd  mov     r8d, 2; char *
0x1800154e3  mov     rdx, rsi; wchar_t *
0x1800154e6  lea     rcx, [rbp+4Fh+var_BC]; this
0x1800154ea  call    _mbtowc_internal
0x1800154ef  cmp     eax, 0FFFFFFFFh
0x1800154f2  jz      loc_180015679
0x1800154f8  mov     rsi, r14
0x1800154fb  jmp     short loc_180015518
0x1800154fd  mov     r8, r12; char *
0x180015500  mov     rdx, rsi; wchar_t *
0x180015503  mov     r9, r10; __crt_cached_ptd_host *
0x180015506  lea     rcx, [rbp+4Fh+var_BC]; this
0x18001550a  call    _mbtowc_internal
0x18001550f  cmp     eax, 0FFFFFFFFh
0x180015512  jz      loc_180015679
0x180015518  inc     rsi
0x18001551b  mov     [rsp+38h], rdi
0x180015520  mov     [rsp+100h+var_D0], rdi
0x180015525  mov     dword ptr [rsp+100h+var_D8], 5
0x18001552d  lea     rax, [rbp+4Fh+Buffer]
0x180015531  mov     [rsp+100h+lpOverlapped], rax
0x180015536  mov     r9d, r12d
0x180015539  lea     r8, [rbp+4Fh+var_BC]
0x18001553d  xor     edx, edx
0x18001553f  mov     ecx, [rbp+4Fh+var_98]
0x180015542  call    __acrt_WideCharToMultiByte
0x180015547  mov     r14d, eax
0x18001554a  test    eax, eax
0x18001554c  jz      loc_180015679
0x180015552  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x180015555  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18001555a  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001555e  mov     r8d, eax; nNumberOfBytesToWrite
0x180015561  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x180015565  mov     r12, [rbp+4Fh+hFile]
0x180015569  mov     rcx, r12; hFile
0x18001556c  call    cs:__imp_WriteFile
0x180015572  test    eax, eax
0x180015574  jz      loc_180015671
0x18001557a  mov     edx, [rbx+8]
0x18001557d  sub     edx, dword ptr [rbp+4Fh+var_90]
0x180015580  add     edx, esi
0x180015582  mov     [rbx+4], edx
0x180015585  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x180015589  jb      loc_180015679
0x18001558f  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x180015593  jnz     short loc_1800155D3
0x180015595  mov     eax, 0Dh
0x18001559a  mov     [rbp+4Fh+var_C0], ax
0x18001559e  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1800155a3  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800155a7  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x1800155ab  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x1800155af  mov     rcx, r12; hFile
0x1800155b2  call    cs:__imp_WriteFile
0x1800155b8  test    eax, eax
0x1800155ba  jz      loc_180015671
0x1800155c0  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x1800155c4  jb      loc_180015679
0x1800155ca  inc     dword ptr [rbx+8]
0x1800155cd  inc     dword ptr [rbx+4]
0x1800155d0  mov     edx, [rbx+4]
0x1800155d3  cmp     rsi, [rbp+4Fh+var_B0]
0x1800155d7  jnb     loc_180015679
0x1800155dd  mov     r10, [rbp+4Fh+var_A8]
0x1800155e1  mov     r11, [rbp+4Fh+var_60]
0x1800155e5  mov     ecx, [rbp+4Fh+var_94]
0x1800155e8  jmp     loc_1800152D9
0x1800155ed  test    r8, r8
0x1800155f0  jle     short loc_18001561D
0x1800155f2  sub     rsi, r14
0x1800155f5  lea     r9, cs:180000000h
0x1800155fc  lea     rdx, [r14+r15*8]
0x180015600  mov     rcx, rva __pioinfo[r9+r13*8]
0x180015608  mov     al, [rsi+r14]
0x18001560c  mov     [rdx+rcx+3Eh], al
0x180015610  inc     edi
0x180015612  inc     r14
0x180015615  movsxd  rax, edi
0x180015618  cmp     rax, r8
0x18001561b  jl      short loc_1800155FC
0x18001561d  add     [rbx+4], r8d
0x180015621  jmp     short loc_180015679
0x180015623  test    r9, r9
0x180015626  jle     short loc_180015650
0x180015628  mov     r8, rdi
0x18001562b  mov     r10, [rbp+4Fh+var_88]
0x18001562f  lea     rdx, [r8+r15*8]
0x180015633  mov     rcx, rva __pioinfo[r12+r10*8]
0x18001563b  mov     al, [r8+rsi]
0x18001563f  mov     [rdx+rcx+3Eh], al
0x180015643  inc     edi
0x180015645  inc     r8
0x180015648  movsxd  rax, edi
0x18001564b  cmp     rax, r9
0x18001564e  jl      short loc_18001562F
0x180015650  add     [rbx+4], r9d
0x180015654  jmp     short loc_180015679
0x180015656  mov     [r8+r15*8+3Eh], r9b
0x18001565b  mov     rax, rva __pioinfo[r11+r13*8]
0x180015663  or      byte ptr [rax+r15*8+3Dh], 4
0x180015669  lea     eax, [rdx+1]
0x18001566c  mov     [rbx+4], eax
0x18001566f  jmp     short loc_180015679
0x180015671  call    cs:__imp_GetLastError
0x180015677  mov     [rbx], eax
0x180015679  mov     rax, rbx
0x18001567c  mov     rcx, [rbp+4Fh+var_38]
0x180015680  xor     rcx, rsp; StackCookie
0x180015683  call    __security_check_cookie
0x180015688  mov     rbx, [rsp+100h+arg_0]
0x180015690  add     rsp, 0D0h
0x180015697  pop     r15
0x180015699  pop     r14
0x18001569b  pop     r13
0x18001569d  pop     r12
  ... truncated ...
```
