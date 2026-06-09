# write_double_translated_ansi_nolock

- ea: `0x14001a20c`
- end: `0x14001a69f`
- name: `write_double_translated_ansi_nolock`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14001ab58`

## callees

- `0x140005c20`
- `0x14000c750`
- `0x140014058`
- `0x14001572c`
- `0x1400170b4`
- `0x14001a20c`
- `0x140025080`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14001a568`
- `KERNEL32!WriteFile` at `0x14001a5ae`
- `KERNEL32!WriteFile` at `0x14001a568`
- `KERNEL32!WriteFile` at `0x14001a5ae`
- `KERNEL32!GetLastError` at `0x14001a66d`
- `KERNEL32!GetLastError` at `0x14001a66d`
- `KERNEL32!GetConsoleOutputCP` at `0x14001a28b`
- `KERNEL32!GetConsoleOutputCP` at `0x14001a28b`

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
0x14001a20c  mov     rax, rsp
0x14001a20f  push    rbp
0x14001a210  push    rsi
0x14001a211  push    rdi
0x14001a212  push    r12
0x14001a214  push    r13
0x14001a216  push    r14
0x14001a218  push    r15
0x14001a21a  lea     rbp, [rax-57h]
0x14001a21e  sub     rsp, 0D0h
0x14001a225  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x14001a22d  mov     [rax+8], rbx
0x14001a231  mov     rax, cs:__security_cookie
0x14001a238  xor     rax, rsp
0x14001a23b  mov     [rbp+4Fh+var_38], rax
0x14001a23f  mov     rsi, r8
0x14001a242  mov     [rbp+4Fh+var_90], r8
0x14001a246  movsxd  r14, edx
0x14001a249  mov     rbx, rcx
0x14001a24c  mov     rax, [rbp+4Fh+arg_20]
0x14001a250  mov     [rbp+4Fh+var_A8], rax
0x14001a254  mov     rax, r14
0x14001a257  mov     r13, r14
0x14001a25a  sar     r13, 6
0x14001a25e  mov     [rbp+4Fh+var_88], r13
0x14001a262  lea     rcx, cs:140000000h
0x14001a269  and     eax, 3Fh
0x14001a26c  lea     r15, [rax+rax*8]
0x14001a270  mov     rax, rva __pioinfo[rcx+r13*8]
0x14001a278  mov     rax, [rax+r15*8+28h]
0x14001a27d  mov     [rbp+4Fh+hFile], rax
0x14001a281  mov     r12d, r9d
0x14001a284  add     r12, r8
0x14001a287  mov     [rbp+4Fh+var_B0], r12
0x14001a28b  call    cs:__imp_GetConsoleOutputCP
0x14001a291  mov     [rbp+4Fh+var_98], eax
0x14001a294  xor     edi, edi
0x14001a296  mov     r10, [rbp+4Fh+var_A8]
0x14001a29a  cmp     [r10+28h], dil
0x14001a29e  jnz     short loc_14001A2AC
0x14001a2a0  mov     rcx, r10; this
0x14001a2a3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14001a2a8  mov     r10, [rbp+4Fh+var_A8]
0x14001a2ac  mov     rcx, [r10+18h]
0x14001a2b0  mov     ecx, [rcx+0Ch]
0x14001a2b3  mov     [rbp+4Fh+var_94], ecx
0x14001a2b6  xor     eax, eax
0x14001a2b8  mov     [rbx], rax
0x14001a2bb  mov     [rbx+8], eax
0x14001a2be  cmp     [rbp+4Fh+var_90], r12
0x14001a2c2  jnb     loc_14001A675
0x14001a2c8  mov     r11, r14
0x14001a2cb  sar     r11, 6
0x14001a2cf  mov     [rbp+4Fh+var_60], r11
0x14001a2d3  mov     edx, edi
0x14001a2d5  mov     al, [rsi]
0x14001a2d7  mov     byte ptr [rbp+4Fh+var_C0], al
0x14001a2da  mov     [rbp+4Fh+var_BC], edi
0x14001a2dd  mov     r12d, 1
0x14001a2e3  cmp     ecx, 0FDE9h
0x14001a2e9  jnz     loc_14001A47C
0x14001a2ef  mov     edx, edi
0x14001a2f1  mov     r14, rdi
0x14001a2f4  lea     r12, cs:140000000h
0x14001a2fb  lea     rcx, ds:3Eh[r15*8]
0x14001a303  add     rcx, rva __pioinfo[r12+r11*8]
0x14001a30b  cmp     [rcx], dil
0x14001a30e  jz      short loc_14001A31E
0x14001a310  inc     edx
0x14001a312  inc     r14
0x14001a315  inc     rcx
0x14001a318  cmp     r14, 5
0x14001a31c  jl      short loc_14001A30B
0x14001a31e  test    r14, r14
0x14001a321  jle     loc_14001A412
0x14001a327  mov     rax, rva __pioinfo[r12+r13*8]
0x14001a32f  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x14001a335  movsx   r12d, byte ptr [rcx+r12+3BA80h]
0x14001a33e  inc     r12d
0x14001a341  mov     eax, r12d
0x14001a344  sub     eax, edx
0x14001a346  mov     dword ptr [rbp+4Fh+var_A0], eax
0x14001a349  mov     r8, [rbp+4Fh+var_B0]
0x14001a34d  sub     r8, rsi
0x14001a350  movsxd  r9, eax
0x14001a353  cmp     r9, r8
0x14001a356  jg      loc_14001A5E9
0x14001a35c  mov     rcx, rdi
0x14001a35f  lea     r8, cs:140000000h
0x14001a366  lea     rdx, ds:3Eh[r15*8]
0x14001a36e  add     rdx, rva __pioinfo[r8+r11*8]
0x14001a376  mov     al, [rdx]
0x14001a378  mov     [rbp+rcx+4Fh+var_50], al
0x14001a37c  inc     rcx
0x14001a37f  inc     rdx
0x14001a382  cmp     rcx, r14
0x14001a385  jl      short loc_14001A376
0x14001a387  test    r9, r9
0x14001a38a  jle     short loc_14001A3A9
0x14001a38c  lea     rcx, [rbp+4Fh+var_50]
0x14001a390  add     rcx, r14; void *
0x14001a393  mov     r8, r9; Size
0x14001a396  mov     rdx, rsi; Src
0x14001a399  call    memmove
0x14001a39e  mov     r10, [rbp+4Fh+var_A8]
0x14001a3a2  lea     r8, cs:140000000h
0x14001a3a9  mov     rdx, rdi
0x14001a3ac  lea     rcx, [rdx+r15*8]
0x14001a3b0  mov     rax, rva __pioinfo[r8+r13*8]
0x14001a3b8  mov     [rcx+rax+3Eh], dil
0x14001a3bd  inc     rdx
0x14001a3c0  cmp     rdx, r14
0x14001a3c3  jl      short loc_14001A3AC
0x14001a3c5  mov     [rbp+4Fh+var_80], rdi
0x14001a3c9  lea     rax, [rbp+4Fh+var_50]
0x14001a3cd  mov     qword ptr [rbp+4Fh+var_78], rax
0x14001a3d1  mov     eax, edi
0x14001a3d3  cmp     r12d, 4
0x14001a3d7  setz    al
0x14001a3da  inc     eax
0x14001a3dc  mov     r12d, eax
0x14001a3df  mov     r8d, eax; char **
0x14001a3e2  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x14001a3e7  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x14001a3eb  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x14001a3ef  lea     rcx, [rbp+4Fh+var_BC]; this
0x14001a3f3  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x14001a3f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a3fc  jz      loc_14001A675
0x14001a402  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x14001a405  dec     eax
0x14001a407  movsxd  rcx, eax
0x14001a40a  add     rsi, rcx
0x14001a40d  jmp     loc_14001A514
0x14001a412  movzx   eax, byte ptr [rsi]
0x14001a415  movsx   r13, byte ptr [rax+r12+3BA80h]
0x14001a41e  lea     ecx, [r13+1]
0x14001a422  mov     r9, [rbp+4Fh+var_B0]
0x14001a426  sub     r9, rsi
0x14001a429  movsxd  rax, ecx
0x14001a42c  cmp     rax, r9
0x14001a42f  jg      loc_14001A61F
0x14001a435  mov     [rbp+4Fh+var_A0], rdi
0x14001a439  mov     qword ptr [rbp+4Fh+var_70], rsi
0x14001a43d  mov     eax, edi
0x14001a43f  cmp     ecx, 4
0x14001a442  setz    al
0x14001a445  inc     eax
0x14001a447  mov     r14d, eax
0x14001a44a  mov     r8d, eax; char **
0x14001a44d  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x14001a452  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x14001a456  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x14001a45a  lea     rcx, [rbp+4Fh+var_BC]; this
0x14001a45e  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x14001a463  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a467  jz      loc_14001A675
0x14001a46d  add     rsi, r13
0x14001a470  mov     r12d, r14d
0x14001a473  mov     r13, [rbp+4Fh+var_88]
0x14001a477  jmp     loc_14001A514
0x14001a47c  lea     r11, cs:140000000h
0x14001a483  mov     r8, rva __pioinfo[r11+r13*8]
0x14001a48b  mov     cl, [r8+r15*8+3Dh]
0x14001a490  test    cl, 4
0x14001a493  jz      short loc_14001A4B6
0x14001a495  mov     al, [r8+r15*8+3Eh]
0x14001a49a  mov     [rbp+4Fh+var_48], al
0x14001a49d  mov     al, [rsi]
0x14001a49f  mov     [rbp+4Fh+var_47], al
0x14001a4a2  and     cl, 0FBh
0x14001a4a5  mov     [r8+r15*8+3Dh], cl
0x14001a4aa  mov     r8d, 2
0x14001a4b0  lea     rdx, [rbp+4Fh+var_48]
0x14001a4b4  jmp     short loc_14001A4FF
0x14001a4b6  movzx   r9d, byte ptr [rsi]
0x14001a4ba  mov     rax, [r10+18h]
0x14001a4be  mov     rcx, [rax]
0x14001a4c1  cmp     [rcx+r9*2], di
0x14001a4c6  jge     short loc_14001A4F9
0x14001a4c8  lea     r14, [rsi+1]
0x14001a4cc  cmp     r14, [rbp+4Fh+var_B0]
0x14001a4d0  jnb     loc_14001A652
0x14001a4d6  mov     r9, r10; __crt_cached_ptd_host *
0x14001a4d9  mov     r8d, 2; char *
0x14001a4df  mov     rdx, rsi; wchar_t *
0x14001a4e2  lea     rcx, [rbp+4Fh+var_BC]; this
0x14001a4e6  call    _mbtowc_internal
0x14001a4eb  cmp     eax, 0FFFFFFFFh
0x14001a4ee  jz      loc_14001A675
0x14001a4f4  mov     rsi, r14
0x14001a4f7  jmp     short loc_14001A514
0x14001a4f9  mov     r8, r12; char *
0x14001a4fc  mov     rdx, rsi; wchar_t *
0x14001a4ff  mov     r9, r10; __crt_cached_ptd_host *
0x14001a502  lea     rcx, [rbp+4Fh+var_BC]; this
0x14001a506  call    _mbtowc_internal
0x14001a50b  cmp     eax, 0FFFFFFFFh
0x14001a50e  jz      loc_14001A675
0x14001a514  inc     rsi
0x14001a517  mov     [rsp+38h], rdi
0x14001a51c  mov     [rsp+100h+var_D0], rdi
0x14001a521  mov     dword ptr [rsp+100h+var_D8], 5
0x14001a529  lea     rax, [rbp+4Fh+Buffer]
0x14001a52d  mov     [rsp+100h+lpOverlapped], rax
0x14001a532  mov     r9d, r12d
0x14001a535  lea     r8, [rbp+4Fh+var_BC]
0x14001a539  xor     edx, edx
0x14001a53b  mov     ecx, [rbp+4Fh+var_98]
0x14001a53e  call    __acrt_WideCharToMultiByte
0x14001a543  mov     r14d, eax
0x14001a546  test    eax, eax
0x14001a548  jz      loc_14001A675
0x14001a54e  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x14001a551  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14001a556  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001a55a  mov     r8d, eax; nNumberOfBytesToWrite
0x14001a55d  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x14001a561  mov     r12, [rbp+4Fh+hFile]
0x14001a565  mov     rcx, r12; hFile
0x14001a568  call    cs:__imp_WriteFile
0x14001a56e  test    eax, eax
0x14001a570  jz      loc_14001A66D
0x14001a576  mov     edx, [rbx+8]
0x14001a579  sub     edx, dword ptr [rbp+4Fh+var_90]
0x14001a57c  add     edx, esi
0x14001a57e  mov     [rbx+4], edx
0x14001a581  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14001a585  jb      loc_14001A675
0x14001a58b  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x14001a58f  jnz     short loc_14001A5CF
0x14001a591  mov     eax, 0Dh
0x14001a596  mov     [rbp+4Fh+var_C0], ax
0x14001a59a  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14001a59f  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001a5a3  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x14001a5a7  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x14001a5ab  mov     rcx, r12; hFile
0x14001a5ae  call    cs:__imp_WriteFile
0x14001a5b4  test    eax, eax
0x14001a5b6  jz      loc_14001A66D
0x14001a5bc  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14001a5c0  jb      loc_14001A675
0x14001a5c6  inc     dword ptr [rbx+8]
0x14001a5c9  inc     dword ptr [rbx+4]
0x14001a5cc  mov     edx, [rbx+4]
0x14001a5cf  cmp     rsi, [rbp+4Fh+var_B0]
0x14001a5d3  jnb     loc_14001A675
0x14001a5d9  mov     r10, [rbp+4Fh+var_A8]
0x14001a5dd  mov     r11, [rbp+4Fh+var_60]
0x14001a5e1  mov     ecx, [rbp+4Fh+var_94]
0x14001a5e4  jmp     loc_14001A2D5
0x14001a5e9  test    r8, r8
0x14001a5ec  jle     short loc_14001A619
0x14001a5ee  sub     rsi, r14
0x14001a5f1  lea     r9, cs:140000000h
0x14001a5f8  lea     rdx, [r14+r15*8]
0x14001a5fc  mov     rcx, rva __pioinfo[r9+r13*8]
0x14001a604  mov     al, [rsi+r14]
0x14001a608  mov     [rdx+rcx+3Eh], al
0x14001a60c  inc     edi
0x14001a60e  inc     r14
0x14001a611  movsxd  rax, edi
0x14001a614  cmp     rax, r8
0x14001a617  jl      short loc_14001A5F8
0x14001a619  add     [rbx+4], r8d
0x14001a61d  jmp     short loc_14001A675
0x14001a61f  test    r9, r9
0x14001a622  jle     short loc_14001A64C
0x14001a624  mov     r8, rdi
0x14001a627  mov     r10, [rbp+4Fh+var_88]
0x14001a62b  lea     rdx, [r8+r15*8]
0x14001a62f  mov     rcx, rva __pioinfo[r12+r10*8]
0x14001a637  mov     al, [r8+rsi]
0x14001a63b  mov     [rdx+rcx+3Eh], al
0x14001a63f  inc     edi
0x14001a641  inc     r8
0x14001a644  movsxd  rax, edi
0x14001a647  cmp     rax, r9
0x14001a64a  jl      short loc_14001A62B
0x14001a64c  add     [rbx+4], r9d
0x14001a650  jmp     short loc_14001A675
0x14001a652  mov     [r8+r15*8+3Eh], r9b
0x14001a657  mov     rax, rva __pioinfo[r11+r13*8]
0x14001a65f  or      byte ptr [rax+r15*8+3Dh], 4
0x14001a665  lea     eax, [rdx+1]
0x14001a668  mov     [rbx+4], eax
0x14001a66b  jmp     short loc_14001A675
0x14001a66d  call    cs:__imp_GetLastError
0x14001a673  mov     [rbx], eax
0x14001a675  mov     rax, rbx
0x14001a678  mov     rcx, [rbp+4Fh+var_38]
0x14001a67c  xor     rcx, rsp; StackCookie
0x14001a67f  call    __security_check_cookie
0x14001a684  mov     rbx, [rsp+100h+arg_0]
0x14001a68c  add     rsp, 0D0h
0x14001a693  pop     r15
0x14001a695  pop     r14
0x14001a697  pop     r13
0x14001a699  pop     r12
  ... truncated ...
```
