# write_double_translated_ansi_nolock

- ea: `0x180038418`
- end: `0x180038907`
- name: `write_double_translated_ansi_nolock`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180038df8`

## callees

- `0x180023930`
- `0x180028d00`
- `0x1800293a0`
- `0x1800371c4`
- `0x180037600`
- `0x180038418`
- `0x18009a070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800388d5`
- `KERNEL32!GetLastError` at `0x1800388d5`
- `KERNEL32!WriteFile` at `0x180038798`
- `KERNEL32!WriteFile` at `0x1800387e6`
- `KERNEL32!WriteFile` at `0x180038798`
- `KERNEL32!WriteFile` at `0x1800387e6`
- `KERNEL32!GetConsoleOutputCP` at `0x18003849e`
- `KERNEL32!GetConsoleOutputCP` at `0x18003849e`

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
          LODWORD(v42) = lookuptrailbytes[*(unsigned __int8 *)(_pioinfo[v9] + v17 + 62)] + 1;
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
          v25 = lookuptrailbytes[(unsigned __int8)*v5];
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
0x180038418  mov     rax, rsp
0x18003841b  push    rbp
0x18003841c  push    rsi
0x18003841d  push    rdi
0x18003841e  push    r12
0x180038420  push    r13
0x180038422  push    r14
0x180038424  push    r15
0x180038426  lea     rbp, [rax-57h]
0x18003842a  sub     rsp, 0E0h
0x180038431  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180038439  mov     [rax+8], rbx
0x18003843d  mov     rax, cs:__security_cookie
0x180038444  xor     rax, rsp
0x180038447  mov     [rbp+4Fh+var_38], rax
0x18003844b  mov     rdi, r8
0x18003844e  mov     [rbp+4Fh+var_60], r8
0x180038452  movsxd  r14, edx
0x180038455  mov     rbx, rcx
0x180038458  mov     [rbp+4Fh+var_98], rcx
0x18003845c  mov     rax, [rbp+4Fh+arg_20]
0x180038460  mov     [rbp+4Fh+var_B8], rax
0x180038464  mov     r13, r14
0x180038467  mov     r12, r14
0x18003846a  sar     r12, 6
0x18003846e  lea     rcx, __ImageBase
0x180038475  mov     eax, r14d
0x180038478  and     eax, 3Fh
0x18003847b  lea     rsi, [rax+rax*8]
0x18003847f  mov     [rbp+4Fh+var_90], rsi
0x180038483  mov     rax, rva __pioinfo[rcx+r12*8]
0x18003848b  mov     rax, [rax+rsi*8+28h]
0x180038490  mov     [rbp+4Fh+hFile], rax
0x180038494  mov     r15d, r9d
0x180038497  add     r15, r8
0x18003849a  mov     [rbp+4Fh+var_C0], r15
0x18003849e  call    cs:__imp_GetConsoleOutputCP
0x1800384a4  mov     [rbp+4Fh+var_A4], eax
0x1800384a7  xor     r10d, r10d
0x1800384aa  mov     r11, [rbp+4Fh+var_B8]
0x1800384ae  cmp     [r11+28h], r10b
0x1800384b2  jnz     short loc_1800384C3
0x1800384b4  mov     rcx, r11; this
0x1800384b7  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800384bc  mov     r11, [rbp+4Fh+var_B8]
0x1800384c0  xor     r10d, r10d
0x1800384c3  xor     eax, eax
0x1800384c5  mov     [rbx], rax
0x1800384c8  mov     [rbx+8], eax
0x1800384cb  mov     [rbp+4Fh+var_88], rdi
0x1800384cf  cmp     rdi, r15
0x1800384d2  jnb     loc_1800388DD
0x1800384d8  mov     rax, [r11+18h]
0x1800384dc  mov     ecx, [rax+0Ch]
0x1800384df  mov     [rbp+4Fh+var_A0], ecx
0x1800384e2  mov     rdx, r14
0x1800384e5  sar     rdx, 6
0x1800384e9  mov     [rbp+4Fh+var_88], rdx
0x1800384ed  mov     r8d, r10d
0x1800384f0  mov     al, [rdi]
0x1800384f2  mov     byte ptr [rsp+110h+var_D0], al
0x1800384f6  mov     [rbp+4Fh+var_CC], r10d
0x1800384fa  cmp     ecx, 0FDE9h
0x180038500  jnz     loc_180038699
0x180038506  mov     esi, r10d
0x180038509  mov     rax, r13
0x18003850c  and     eax, 3Fh
0x18003850f  lea     r14, [rax+rax*8]
0x180038513  shl     r14, 3
0x180038517  lea     r8, __ImageBase
0x18003851e  mov     eax, esi
0x180038520  add     rax, rva __pioinfo[r8+rdx*8]
0x180038528  cmp     [rax+r14+3Eh], r10b
0x18003852d  jz      short loc_180038536
0x18003852f  inc     esi
0x180038531  cmp     esi, 5
0x180038534  jl      short loc_18003851E
0x180038536  test    esi, esi
0x180038538  jz      loc_18003862F
0x18003853e  mov     rax, rva __pioinfo[r8+r12*8]
0x180038546  movzx   ecx, byte ptr [rax+r14+3Eh]
0x18003854c  movsx   eax, byte ptr [rcx+r8+0D3B10h]
0x180038555  inc     eax
0x180038557  mov     dword ptr [rbp+4Fh+var_B0], eax
0x18003855a  mov     r15d, eax
0x18003855d  sub     r15d, esi
0x180038560  mov     r10, [rbp+4Fh+var_C0]
0x180038564  sub     r10, rdi
0x180038567  movsxd  r8, r15d; Size
0x18003856a  xor     eax, eax
0x18003856c  mov     r9d, eax
0x18003856f  cmp     r8, r10
0x180038572  jg      loc_180038828
0x180038578  lea     r10, __ImageBase
0x18003857f  mov     r10, rva __pioinfo[r10+rdx*8]
0x180038587  mov     edx, r9d
0x18003858a  lea     rax, [r10+r14]
0x18003858e  mov     cl, [rax+rdx+3Eh]
0x180038592  mov     [rbp+rdx+4Fh+var_50], cl
0x180038596  inc     r9d
0x180038599  cmp     r9d, esi
0x18003859c  jl      short loc_180038587
0x18003859e  xor     r9d, r9d
0x1800385a1  test    r15d, r15d
0x1800385a4  jle     short loc_1800385BE
0x1800385a6  mov     eax, esi
0x1800385a8  lea     rcx, [rbp+4Fh+var_50]
0x1800385ac  add     rcx, rax; void *
0x1800385af  mov     rdx, rdi; Src
0x1800385b2  call    memmove
0x1800385b7  xor     r9d, r9d
0x1800385ba  mov     r11, [rbp+4Fh+var_B8]
0x1800385be  mov     edx, r9d
0x1800385c1  lea     rbx, __ImageBase
0x1800385c8  movsxd  rcx, edx
0x1800385cb  add     rcx, r14
0x1800385ce  mov     rax, rva __pioinfo[rbx+r12*8]
0x1800385d6  mov     [rcx+rax+3Eh], r9b
0x1800385db  inc     edx
0x1800385dd  cmp     edx, esi
0x1800385df  jl      short loc_1800385C8
0x1800385e1  mov     rbx, [rbp+4Fh+var_98]
0x1800385e5  mov     [rbp+4Fh+var_80], r9
0x1800385e9  lea     rax, [rbp+4Fh+var_50]
0x1800385ed  mov     qword ptr [rbp+4Fh+var_78], rax
0x1800385f1  mov     eax, r9d
0x1800385f4  cmp     dword ptr [rbp+4Fh+var_B0], 4
0x1800385f8  setz    al
0x1800385fb  inc     eax
0x1800385fd  mov     r14d, eax
0x180038600  mov     r8d, eax; char **
0x180038603  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x180038608  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x18003860c  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x180038610  lea     rcx, [rbp+4Fh+var_CC]; this
0x180038614  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180038619  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003861d  jz      loc_1800388DD
0x180038623  lea     eax, [r15-1]
0x180038627  movsxd  rcx, eax
0x18003862a  add     rdi, rcx
0x18003862d  jmp     short loc_180038690
0x18003862f  movzx   eax, byte ptr [rdi]
0x180038632  movsx   r15, byte ptr [rax+r8+0D3B10h]
0x18003863b  lea     ecx, [r15+1]
0x18003863f  mov     r9, [rbp+4Fh+var_C0]
0x180038643  sub     r9, rdi
0x180038646  movsxd  rax, ecx
0x180038649  cmp     rax, r9
0x18003864c  jg      loc_180038866
0x180038652  mov     [rbp+4Fh+var_B0], r10
0x180038656  mov     qword ptr [rbp+4Fh+var_70], rdi
0x18003865a  mov     eax, r10d
0x18003865d  cmp     ecx, 4
0x180038660  setz    al
0x180038663  inc     eax
0x180038665  mov     esi, eax
0x180038667  mov     r8d, eax; char **
0x18003866a  mov     [rsp+110h+lpOverlapped], r11; struct _Mbstatet *
0x18003866f  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64
0x180038673  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x180038677  lea     rcx, [rbp+4Fh+var_CC]; this
0x18003867b  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180038680  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038684  jz      loc_1800388DD
0x18003868a  add     rdi, r15
0x18003868d  mov     r14d, esi
0x180038690  mov     r15, [rbp+4Fh+var_C0]
0x180038694  jmp     loc_180038741
0x180038699  mov     r14d, 1
0x18003869f  lea     rax, __ImageBase
0x1800386a6  mov     rdx, rva __pioinfo[rax+r12*8]
0x1800386ae  test    byte ptr [rdx+rsi*8+3Dh], 4
0x1800386b3  jz      short loc_1800386E4
0x1800386b5  mov     rax, r13
0x1800386b8  and     eax, 3Fh
0x1800386bb  lea     rax, [rax+rax*8]
0x1800386bf  mov     cl, [rdx+rax*8+3Eh]
0x1800386c3  mov     [rbp+4Fh+var_48], cl
0x1800386c6  mov     al, [rdi]
0x1800386c8  mov     [rbp+4Fh+var_47], al
0x1800386cb  mov     eax, r13d
0x1800386ce  and     eax, 3Fh
0x1800386d1  lea     rcx, [rax+rax*8]
0x1800386d5  and     byte ptr [rdx+rcx*8+3Dh], 0FBh
0x1800386da  lea     r8d, [r14+1]
0x1800386de  lea     rdx, [rbp+4Fh+var_48]
0x1800386e2  jmp     short loc_18003872C
0x1800386e4  movzx   r9d, byte ptr [rdi]
0x1800386e8  mov     rax, [r11+18h]
0x1800386ec  mov     rcx, [rax]
0x1800386ef  cmp     [rcx+r9*2], r10w
0x1800386f4  jge     short loc_180038726
0x1800386f6  lea     rsi, [rdi+1]
0x1800386fa  cmp     rsi, r15
0x1800386fd  jnb     loc_1800388A0
0x180038703  mov     r9, r11; __crt_cached_ptd_host *
0x180038706  mov     r8d, 2; char *
0x18003870c  mov     rdx, rdi; wchar_t *
0x18003870f  lea     rcx, [rbp+4Fh+var_CC]; this
0x180038713  call    _mbtowc_internal
0x180038718  cmp     eax, 0FFFFFFFFh
0x18003871b  jz      loc_1800388DD
0x180038721  mov     rdi, rsi
0x180038724  jmp     short loc_180038741
0x180038726  mov     r8, r14; char *
0x180038729  mov     rdx, rdi; wchar_t *
0x18003872c  mov     r9, r11; __crt_cached_ptd_host *
0x18003872f  lea     rcx, [rbp+4Fh+var_CC]; this
0x180038733  call    _mbtowc_internal
0x180038738  cmp     eax, 0FFFFFFFFh
0x18003873b  jz      loc_1800388DD
0x180038741  inc     rdi
0x180038744  xor     eax, eax
0x180038746  mov     qword ptr [rsp+110h+var_D8], rax
0x18003874b  mov     [rsp+110h+var_E0], rax
0x180038750  mov     dword ptr [rsp+110h+var_E8], 5
0x180038758  lea     rax, [rbp+4Fh+Buffer]
0x18003875c  mov     [rsp+110h+lpOverlapped], rax
0x180038761  mov     r9d, r14d
0x180038764  lea     r8, [rbp+4Fh+var_CC]
0x180038768  xor     edx, edx
0x18003876a  mov     ecx, [rbp+4Fh+var_A4]
0x18003876d  call    __acrt_WideCharToMultiByte
0x180038772  mov     esi, eax
0x180038774  xor     eax, eax
0x180038776  test    esi, esi
0x180038778  jz      loc_1800388DD
0x18003877e  mov     [rbp+4Fh+NumberOfBytesWritten], eax
0x180038781  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x180038786  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003878a  mov     r8d, esi; nNumberOfBytesToWrite
0x18003878d  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x180038791  mov     r14, [rbp+4Fh+hFile]
0x180038795  mov     rcx, r14; hFile
0x180038798  call    cs:__imp_WriteFile
0x18003879e  xor     r10d, r10d
0x1800387a1  test    eax, eax
0x1800387a3  jz      loc_1800388D5
0x1800387a9  mov     r8d, [rbx+8]
0x1800387ad  sub     r8d, dword ptr [rbp+4Fh+var_60]
0x1800387b1  add     r8d, edi
0x1800387b4  mov     [rbx+4], r8d
0x1800387b8  cmp     [rbp+4Fh+NumberOfBytesWritten], esi
0x1800387bb  jb      loc_1800388DD
0x1800387c1  cmp     byte ptr [rsp+110h+var_D0], 0Ah
0x1800387c6  jnz     short loc_18003880B
0x1800387c8  lea     eax, [r10+0Dh]
0x1800387cc  mov     [rsp+110h+var_D0], ax
0x1800387d1  mov     [rsp+110h+lpOverlapped], r10; lpOverlapped
0x1800387d6  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800387da  lea     r8d, [r10+1]; nNumberOfBytesToWrite
0x1800387de  lea     rdx, [rsp+110h+var_D0]; lpBuffer
0x1800387e3  mov     rcx, r14; hFile
0x1800387e6  call    cs:__imp_WriteFile
0x1800387ec  xor     r10d, r10d
0x1800387ef  test    eax, eax
0x1800387f1  jz      loc_1800388D5
0x1800387f7  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x1800387fb  jb      loc_1800388DD
0x180038801  inc     dword ptr [rbx+8]
0x180038804  inc     dword ptr [rbx+4]
0x180038807  mov     r8d, [rbx+4]
0x18003880b  cmp     rdi, r15
0x18003880e  jnb     loc_1800388DD
0x180038814  mov     r11, [rbp+4Fh+var_B8]
0x180038818  mov     rsi, [rbp+4Fh+var_90]
0x18003881c  mov     rdx, [rbp+4Fh+var_88]
0x180038820  mov     ecx, [rbp+4Fh+var_A0]
0x180038823  jmp     loc_1800384F0
0x180038828  test    r10, r10
0x18003882b  jle     short loc_180038860
0x18003882d  lea     rbx, __ImageBase
0x180038834  movsxd  r8, r9d
0x180038837  lea     eax, [r9+rsi]
0x18003883b  movsxd  rdx, eax
0x18003883e  add     rdx, r14
0x180038841  mov     rcx, rva __pioinfo[rbx+r12*8]
0x180038849  mov     al, [r8+rdi]
0x18003884d  mov     [rdx+rcx+3Eh], al
0x180038851  inc     r9d
0x180038854  movsxd  rax, r9d
0x180038857  cmp     rax, r10
0x18003885a  jl      short loc_180038834
0x18003885c  mov     rbx, [rbp+4Fh+var_98]
0x180038860  add     [rbx+4], r10d
0x180038864  jmp     short loc_1800388DD
0x180038866  mov     r8d, r10d
0x180038869  test    r9, r9
0x18003886c  jle     short loc_18003889A
0x18003886e  lea     rbx, __ImageBase
0x180038875  movsxd  rdx, r8d
0x180038878  mov     rcx, rva __pioinfo[rbx+r12*8]
0x180038880  add     rcx, rdx
0x180038883  mov     al, [rdx+rdi]
0x180038886  mov     [rcx+r14+3Eh], al
0x18003888b  inc     r8d
0x18003888e  movsxd  rax, r8d
0x180038891  cmp     rax, r9
0x180038894  jl      short loc_180038875
  ... truncated ...
```
