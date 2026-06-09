# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x1400763a8`
- end: `0x14007683b`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(__int64, int, _BYTE *, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x140076cf4`

## callees

- `0x140051ba0`
- `0x140065e50`
- `0x1400733c0`
- `0x14007381c`
- `0x1400763a8`
- `0x14007ad18`
- `0x14007fc30`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140076704`
- `KERNEL32!WriteFile` at `0x14007674a`
- `KERNEL32!WriteFile` at `0x140076704`
- `KERNEL32!WriteFile` at `0x14007674a`
- `KERNEL32!GetConsoleOutputCP` at `0x140076427`
- `KERNEL32!GetConsoleOutputCP` at `0x140076427`
- `KERNEL32!GetLastError` at `0x140076809`
- `KERNEL32!GetLastError` at `0x140076809`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(
        __int64 a1,
        int a2,
        _BYTE *a3,
        int a4,
        __crt_cached_ptd_host *a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  __crt_cached_ptd_host *v12; // r10
  int v13; // ecx
  __int64 v14; // r11
  int v15; // edx
  int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r9
  int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  _BYTE *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r10
  __int16 v41[2]; // [rsp+48h] [rbp-71h] BYREF
  int v42; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-61h]
  __crt_cached_ptd_host *v45; // [rsp+60h] [rbp-59h]
  __int64 v46; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v48; // [rsp+74h] [rbp-45h]
  _BYTE *v49; // [rsp+78h] [rbp-41h]
  __int64 v50; // [rsp+80h] [rbp-39h]
  __int64 v51; // [rsp+88h] [rbp-31h] BYREF
  _BYTE *v52; // [rsp+90h] [rbp-29h] BYREF
  _BYTE *v53; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v55; // [rsp+A8h] [rbp-11h]
  __int64 v56; // [rsp+B0h] [rbp-9h]
  _BYTE v57[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v58[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v56 = -2;
  v5 = a3;
  v49 = a3;
  v6 = a2;
  v45 = a5;
  v8 = (__int64)a2 >> 6;
  v50 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(qword_1400C4950[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v44 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = a5;
  if ( !*((_BYTE *)a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(v45);
    v12 = v45;
  }
  v13 = *(_DWORD *)(*((_QWORD *)v12 + 3) + 12LL);
  v48 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v49 < v10 )
  {
    v14 = v6 >> 6;
    v55 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v41[0]) = *v5;
      v42 = 0;
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(qword_1400C4950[v14] + 8 * v9 + 62);
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
          v26 = *((char *)qword_1400BE380 + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_1400C4950[v39] + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v46 = 0;
          v53 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( sub_14007381C((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)qword_1400BE380 + *(unsigned __int8 *)(qword_1400C4950[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v46) = v20 - v17;
          v21 = v44 - (_QWORD)v5;
          v22 = v20 - v17;
          if ( v22 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + 8 * v9 + qword_1400C4950[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_1400C4950[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            sub_14007FC30(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_1400C4950[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_14007381C((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_1400C4950[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v58[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v58[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = v58;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**((_QWORD **)v12 + 3) + 2 * v33) >= 0 )
        {
          v31 = 1;
          v32 = v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal(&v42, v32, v31, v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v44 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(qword_1400C4950[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(&v42, v5, 2, v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v42, v16, (unsigned int)Buffer, 5, 0, 0);
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
      v15 = (_DWORD)v5 + *(_DWORD *)(a1 + 8) - (_DWORD)v49;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v41[0]) == 10 )
      {
        v41[0] = 13;
        if ( !WriteFile(v36, v41, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v44 )
        return a1;
      v12 = v45;
      v14 = v55;
      v13 = v48;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400763a8  mov     rax, rsp
0x1400763ab  push    rbp
0x1400763ac  push    rsi
0x1400763ad  push    rdi
0x1400763ae  push    r12
0x1400763b0  push    r13
0x1400763b2  push    r14
0x1400763b4  push    r15
0x1400763b6  lea     rbp, [rax-57h]
0x1400763ba  sub     rsp, 0D0h
0x1400763c1  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x1400763c9  mov     [rax+8], rbx
0x1400763cd  mov     rax, cs:__security_cookie
0x1400763d4  xor     rax, rsp
0x1400763d7  mov     [rbp+4Fh+var_38], rax
0x1400763db  mov     rsi, r8
0x1400763de  mov     [rbp+4Fh+var_90], r8
0x1400763e2  movsxd  r14, edx
0x1400763e5  mov     rbx, rcx
0x1400763e8  mov     rax, [rbp+4Fh+arg_20]
0x1400763ec  mov     [rbp+4Fh+var_A8], rax
0x1400763f0  mov     rax, r14
0x1400763f3  mov     r13, r14
0x1400763f6  sar     r13, 6
0x1400763fa  mov     [rbp+4Fh+var_88], r13
0x1400763fe  lea     rcx, __ImageBase
0x140076405  and     eax, 3Fh
0x140076408  lea     r15, [rax+rax*8]
0x14007640c  mov     rax, rva qword_1400C4950[rcx+r13*8]
0x140076414  mov     rax, [rax+r15*8+28h]
0x140076419  mov     [rbp+4Fh+hFile], rax
0x14007641d  mov     r12d, r9d
0x140076420  add     r12, r8
0x140076423  mov     [rbp+4Fh+var_B0], r12
0x140076427  call    cs:GetConsoleOutputCP
0x14007642d  mov     [rbp+4Fh+var_98], eax
0x140076430  xor     edi, edi
0x140076432  mov     r10, [rbp+4Fh+var_A8]
0x140076436  cmp     [r10+28h], dil
0x14007643a  jnz     short loc_140076448
0x14007643c  mov     rcx, r10; this
0x14007643f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140076444  mov     r10, [rbp+4Fh+var_A8]
0x140076448  mov     rcx, [r10+18h]
0x14007644c  mov     ecx, [rcx+0Ch]
0x14007644f  mov     [rbp+4Fh+var_94], ecx
0x140076452  xor     eax, eax
0x140076454  mov     [rbx], rax
0x140076457  mov     [rbx+8], eax
0x14007645a  cmp     [rbp+4Fh+var_90], r12
0x14007645e  jnb     loc_140076811
0x140076464  mov     r11, r14
0x140076467  sar     r11, 6
0x14007646b  mov     [rbp+4Fh+var_60], r11
0x14007646f  mov     edx, edi
0x140076471  mov     al, [rsi]
0x140076473  mov     byte ptr [rbp+4Fh+var_C0], al
0x140076476  mov     [rbp+4Fh+var_BC], edi
0x140076479  mov     r12d, 1
0x14007647f  cmp     ecx, 0FDE9h
0x140076485  jnz     loc_140076618
0x14007648b  mov     edx, edi
0x14007648d  mov     r14, rdi
0x140076490  lea     r12, __ImageBase
0x140076497  lea     rcx, ds:3Eh[r15*8]
0x14007649f  add     rcx, rva qword_1400C4950[r12+r11*8]
0x1400764a7  cmp     [rcx], dil
0x1400764aa  jz      short loc_1400764BA
0x1400764ac  inc     edx
0x1400764ae  inc     r14
0x1400764b1  inc     rcx
0x1400764b4  cmp     r14, 5
0x1400764b8  jl      short loc_1400764A7
0x1400764ba  test    r14, r14
0x1400764bd  jle     loc_1400765AE
0x1400764c3  mov     rax, rva qword_1400C4950[r12+r13*8]
0x1400764cb  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x1400764d1  movsx   r12d, byte ptr [rcx+r12+0BE380h]
0x1400764da  inc     r12d
0x1400764dd  mov     eax, r12d
0x1400764e0  sub     eax, edx
0x1400764e2  mov     dword ptr [rbp+4Fh+var_A0], eax
0x1400764e5  mov     r8, [rbp+4Fh+var_B0]
0x1400764e9  sub     r8, rsi
0x1400764ec  movsxd  r9, eax
0x1400764ef  cmp     r9, r8
0x1400764f2  jg      loc_140076785
0x1400764f8  mov     rcx, rdi
0x1400764fb  lea     r8, __ImageBase
0x140076502  lea     rdx, ds:3Eh[r15*8]
0x14007650a  add     rdx, rva qword_1400C4950[r8+r11*8]
0x140076512  mov     al, [rdx]
0x140076514  mov     [rbp+rcx+4Fh+var_50], al
0x140076518  inc     rcx
0x14007651b  inc     rdx
0x14007651e  cmp     rcx, r14
0x140076521  jl      short loc_140076512
0x140076523  test    r9, r9
0x140076526  jle     short loc_140076545
0x140076528  lea     rcx, [rbp+4Fh+var_50]
0x14007652c  add     rcx, r14
0x14007652f  mov     r8, r9
0x140076532  mov     rdx, rsi
0x140076535  call    sub_14007FC30
0x14007653a  mov     r10, [rbp+4Fh+var_A8]
0x14007653e  lea     r8, __ImageBase
0x140076545  mov     rdx, rdi
0x140076548  lea     rcx, [rdx+r15*8]
0x14007654c  mov     rax, rva qword_1400C4950[r8+r13*8]
0x140076554  mov     [rcx+rax+3Eh], dil
0x140076559  inc     rdx
0x14007655c  cmp     rdx, r14
0x14007655f  jl      short loc_140076548
0x140076561  mov     [rbp+4Fh+var_80], rdi
0x140076565  lea     rax, [rbp+4Fh+var_50]
0x140076569  mov     [rbp+4Fh+var_78], rax
0x14007656d  mov     eax, edi
0x14007656f  cmp     r12d, 4
0x140076573  setz    al
0x140076576  inc     eax
0x140076578  mov     r12d, eax
0x14007657b  mov     r8d, eax
0x14007657e  mov     [rsp+100h+lpOverlapped], r10
0x140076583  lea     r9, [rbp+4Fh+var_80]
0x140076587  lea     rdx, [rbp+4Fh+var_78]
0x14007658b  lea     rcx, [rbp+4Fh+var_BC]
0x14007658f  call    sub_14007381C
0x140076594  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140076598  jz      loc_140076811
0x14007659e  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x1400765a1  dec     eax
0x1400765a3  movsxd  rcx, eax
0x1400765a6  add     rsi, rcx
0x1400765a9  jmp     loc_1400766B0
0x1400765ae  movzx   eax, byte ptr [rsi]
0x1400765b1  movsx   r13, byte ptr [rax+r12+0BE380h]
0x1400765ba  lea     ecx, [r13+1]
0x1400765be  mov     r9, [rbp+4Fh+var_B0]
0x1400765c2  sub     r9, rsi
0x1400765c5  movsxd  rax, ecx
0x1400765c8  cmp     rax, r9
0x1400765cb  jg      loc_1400767BB
0x1400765d1  mov     [rbp+4Fh+var_A0], rdi
0x1400765d5  mov     [rbp+4Fh+var_70], rsi
0x1400765d9  mov     eax, edi
0x1400765db  cmp     ecx, 4
0x1400765de  setz    al
0x1400765e1  inc     eax
0x1400765e3  mov     r14d, eax
0x1400765e6  mov     r8d, eax
0x1400765e9  mov     [rsp+100h+lpOverlapped], r10
0x1400765ee  lea     r9, [rbp+4Fh+var_A0]
0x1400765f2  lea     rdx, [rbp+4Fh+var_70]
0x1400765f6  lea     rcx, [rbp+4Fh+var_BC]
0x1400765fa  call    sub_14007381C
0x1400765ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140076603  jz      loc_140076811
0x140076609  add     rsi, r13
0x14007660c  mov     r12d, r14d
0x14007660f  mov     r13, [rbp+4Fh+var_88]
0x140076613  jmp     loc_1400766B0
0x140076618  lea     r11, __ImageBase
0x14007661f  mov     r8, rva qword_1400C4950[r11+r13*8]
0x140076627  mov     cl, [r8+r15*8+3Dh]
0x14007662c  test    cl, 4
0x14007662f  jz      short loc_140076652
0x140076631  mov     al, [r8+r15*8+3Eh]
0x140076636  mov     [rbp+4Fh+var_48], al
0x140076639  mov     al, [rsi]
0x14007663b  mov     [rbp+4Fh+var_47], al
0x14007663e  and     cl, 0FBh
0x140076641  mov     [r8+r15*8+3Dh], cl
0x140076646  mov     r8d, 2
0x14007664c  lea     rdx, [rbp+4Fh+var_48]
0x140076650  jmp     short loc_14007669B
0x140076652  movzx   r9d, byte ptr [rsi]
0x140076656  mov     rax, [r10+18h]
0x14007665a  mov     rcx, [rax]
0x14007665d  cmp     [rcx+r9*2], di
0x140076662  jge     short loc_140076695
0x140076664  lea     r14, [rsi+1]
0x140076668  cmp     r14, [rbp+4Fh+var_B0]
0x14007666c  jnb     loc_1400767EE
0x140076672  mov     r9, r10
0x140076675  mov     r8d, 2
0x14007667b  mov     rdx, rsi
0x14007667e  lea     rcx, [rbp+4Fh+var_BC]
0x140076682  call    _mbtowc_internal
0x140076687  cmp     eax, 0FFFFFFFFh
0x14007668a  jz      loc_140076811
0x140076690  mov     rsi, r14
0x140076693  jmp     short loc_1400766B0
0x140076695  mov     r8, r12
0x140076698  mov     rdx, rsi
0x14007669b  mov     r9, r10
0x14007669e  lea     rcx, [rbp+4Fh+var_BC]
0x1400766a2  call    _mbtowc_internal
0x1400766a7  cmp     eax, 0FFFFFFFFh
0x1400766aa  jz      loc_140076811
0x1400766b0  inc     rsi
0x1400766b3  mov     [rsp+38h], rdi
0x1400766b8  mov     [rsp+100h+var_D0], rdi
0x1400766bd  mov     dword ptr [rsp+100h+var_D8], 5
0x1400766c5  lea     rax, [rbp+4Fh+Buffer]
0x1400766c9  mov     [rsp+100h+lpOverlapped], rax
0x1400766ce  mov     r9d, r12d
0x1400766d1  lea     r8, [rbp+4Fh+var_BC]
0x1400766d5  xor     edx, edx
0x1400766d7  mov     ecx, [rbp+4Fh+var_98]
0x1400766da  call    __acrt_WideCharToMultiByte
0x1400766df  mov     r14d, eax
0x1400766e2  test    eax, eax
0x1400766e4  jz      loc_140076811
0x1400766ea  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x1400766ed  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1400766f2  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400766f6  mov     r8d, eax; nNumberOfBytesToWrite
0x1400766f9  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x1400766fd  mov     r12, [rbp+4Fh+hFile]
0x140076701  mov     rcx, r12; hFile
0x140076704  call    cs:WriteFile
0x14007670a  test    eax, eax
0x14007670c  jz      loc_140076809
0x140076712  mov     edx, [rbx+8]
0x140076715  sub     edx, dword ptr [rbp+4Fh+var_90]
0x140076718  add     edx, esi
0x14007671a  mov     [rbx+4], edx
0x14007671d  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x140076721  jb      loc_140076811
0x140076727  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x14007672b  jnz     short loc_14007676B
0x14007672d  mov     eax, 0Dh
0x140076732  mov     [rbp+4Fh+var_C0], ax
0x140076736  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14007673b  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14007673f  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x140076743  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x140076747  mov     rcx, r12; hFile
0x14007674a  call    cs:WriteFile
0x140076750  test    eax, eax
0x140076752  jz      loc_140076809
0x140076758  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14007675c  jb      loc_140076811
0x140076762  inc     dword ptr [rbx+8]
0x140076765  inc     dword ptr [rbx+4]
0x140076768  mov     edx, [rbx+4]
0x14007676b  cmp     rsi, [rbp+4Fh+var_B0]
0x14007676f  jnb     loc_140076811
0x140076775  mov     r10, [rbp+4Fh+var_A8]
0x140076779  mov     r11, [rbp+4Fh+var_60]
0x14007677d  mov     ecx, [rbp+4Fh+var_94]
0x140076780  jmp     loc_140076471
0x140076785  test    r8, r8
0x140076788  jle     short loc_1400767B5
0x14007678a  sub     rsi, r14
0x14007678d  lea     r9, __ImageBase
0x140076794  lea     rdx, [r14+r15*8]
0x140076798  mov     rcx, rva qword_1400C4950[r9+r13*8]
0x1400767a0  mov     al, [rsi+r14]
0x1400767a4  mov     [rdx+rcx+3Eh], al
0x1400767a8  inc     edi
0x1400767aa  inc     r14
0x1400767ad  movsxd  rax, edi
0x1400767b0  cmp     rax, r8
0x1400767b3  jl      short loc_140076794
0x1400767b5  add     [rbx+4], r8d
0x1400767b9  jmp     short loc_140076811
0x1400767bb  test    r9, r9
0x1400767be  jle     short loc_1400767E8
0x1400767c0  mov     r8, rdi
0x1400767c3  mov     r10, [rbp+4Fh+var_88]
0x1400767c7  lea     rdx, [r8+r15*8]
0x1400767cb  mov     rcx, rva qword_1400C4950[r12+r10*8]
0x1400767d3  mov     al, [r8+rsi]
0x1400767d7  mov     [rdx+rcx+3Eh], al
0x1400767db  inc     edi
0x1400767dd  inc     r8
0x1400767e0  movsxd  rax, edi
0x1400767e3  cmp     rax, r9
0x1400767e6  jl      short loc_1400767C7
0x1400767e8  add     [rbx+4], r9d
0x1400767ec  jmp     short loc_140076811
0x1400767ee  mov     [r8+r15*8+3Eh], r9b
0x1400767f3  mov     rax, rva qword_1400C4950[r11+r13*8]
0x1400767fb  or      byte ptr [rax+r15*8+3Dh], 4
0x140076801  lea     eax, [rdx+1]
0x140076804  mov     [rbx+4], eax
0x140076807  jmp     short loc_140076811
0x140076809  call    cs:GetLastError
0x14007680f  mov     [rbx], eax
0x140076811  mov     rax, rbx
0x140076814  mov     rcx, [rbp+4Fh+var_38]
0x140076818  xor     rcx, rsp; StackCookie
0x14007681b  call    __security_check_cookie
0x140076820  mov     rbx, [rsp+100h+arg_0]
0x140076828  add     rsp, 0D0h
0x14007682f  pop     r15
0x140076831  pop     r14
0x140076833  pop     r13
0x140076835  pop     r12
  ... truncated ...
```
