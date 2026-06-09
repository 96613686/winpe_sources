# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x14000b67c`
- end: `0x14000bb0f`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14000bfc8`

## callees

- `0x140001350`
- `0x140005b00`
- `0x140007bc4`
- `0x14000a4ac`
- `0x14000a864`
- `0x14000b67c`
- `0x14000d3f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000badd`
- `KERNEL32!GetLastError` at `0x14000badd`
- `KERNEL32!WriteFile` at `0x14000b9d8`
- `KERNEL32!WriteFile` at `0x14000ba1e`
- `KERNEL32!WriteFile` at `0x14000b9d8`
- `KERNEL32!WriteFile` at `0x14000ba1e`
- `KERNEL32!GetConsoleOutputCP` at `0x14000b6fb`
- `KERNEL32!GetConsoleOutputCP` at `0x14000b6fb`

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
  hFile = *(HANDLE *)(qword_14001A750[v8] + 72LL * (a2 & 0x3F) + 40);
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
        v19 = (_BYTE *)(qword_14001A750[v14] + 8 * v9 + 62);
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
          v26 = *((char *)&qword_140019910[10] + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_14001A750[v39] + 62) = v5[v38];
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
          if ( sub_14000A864((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)&qword_140019910[10] + *(unsigned __int8 *)(qword_14001A750[v8] + 8 * v9 + 62)) + 1;
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
                *(_BYTE *)(v18 + 8 * v9 + qword_14001A750[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_14001A750[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            sub_14000D3F0(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_14001A750[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_14000A864((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_14001A750[v8];
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
          *(_BYTE *)(qword_14001A750[v8] + 8 * v9 + 61) |= 4u;
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
0x14000b67c  mov     rax, rsp
0x14000b67f  push    rbp
0x14000b680  push    rsi
0x14000b681  push    rdi
0x14000b682  push    r12
0x14000b684  push    r13
0x14000b686  push    r14
0x14000b688  push    r15
0x14000b68a  lea     rbp, [rax-57h]
0x14000b68e  sub     rsp, 0D0h
0x14000b695  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x14000b69d  mov     [rax+8], rbx
0x14000b6a1  mov     rax, cs:__security_cookie
0x14000b6a8  xor     rax, rsp
0x14000b6ab  mov     [rbp+4Fh+var_38], rax
0x14000b6af  mov     rsi, r8
0x14000b6b2  mov     [rbp+4Fh+var_90], r8
0x14000b6b6  movsxd  r14, edx
0x14000b6b9  mov     rbx, rcx
0x14000b6bc  mov     rax, [rbp+4Fh+arg_20]
0x14000b6c0  mov     [rbp+4Fh+var_A8], rax
0x14000b6c4  mov     rax, r14
0x14000b6c7  mov     r13, r14
0x14000b6ca  sar     r13, 6
0x14000b6ce  mov     [rbp+4Fh+var_88], r13
0x14000b6d2  lea     rcx, cs:140000000h
0x14000b6d9  and     eax, 3Fh
0x14000b6dc  lea     r15, [rax+rax*8]
0x14000b6e0  mov     rax, rva qword_14001A750[rcx+r13*8]
0x14000b6e8  mov     rax, [rax+r15*8+28h]
0x14000b6ed  mov     [rbp+4Fh+hFile], rax
0x14000b6f1  mov     r12d, r9d
0x14000b6f4  add     r12, r8
0x14000b6f7  mov     [rbp+4Fh+var_B0], r12
0x14000b6fb  call    cs:GetConsoleOutputCP
0x14000b701  mov     [rbp+4Fh+var_98], eax
0x14000b704  xor     edi, edi
0x14000b706  mov     r10, [rbp+4Fh+var_A8]
0x14000b70a  cmp     [r10+28h], dil
0x14000b70e  jnz     short loc_14000B71C
0x14000b710  mov     rcx, r10; this
0x14000b713  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14000b718  mov     r10, [rbp+4Fh+var_A8]
0x14000b71c  mov     rcx, [r10+18h]
0x14000b720  mov     ecx, [rcx+0Ch]
0x14000b723  mov     [rbp+4Fh+var_94], ecx
0x14000b726  xor     eax, eax
0x14000b728  mov     [rbx], rax
0x14000b72b  mov     [rbx+8], eax
0x14000b72e  cmp     [rbp+4Fh+var_90], r12
0x14000b732  jnb     loc_14000BAE5
0x14000b738  mov     r11, r14
0x14000b73b  sar     r11, 6
0x14000b73f  mov     [rbp+4Fh+var_60], r11
0x14000b743  mov     edx, edi
0x14000b745  mov     al, [rsi]
0x14000b747  mov     byte ptr [rbp+4Fh+var_C0], al
0x14000b74a  mov     [rbp+4Fh+var_BC], edi
0x14000b74d  mov     r12d, 1
0x14000b753  cmp     ecx, 0FDE9h
0x14000b759  jnz     loc_14000B8EC
0x14000b75f  mov     edx, edi
0x14000b761  mov     r14, rdi
0x14000b764  lea     r12, cs:140000000h
0x14000b76b  lea     rcx, ds:3Eh[r15*8]
0x14000b773  add     rcx, rva qword_14001A750[r12+r11*8]
0x14000b77b  cmp     [rcx], dil
0x14000b77e  jz      short loc_14000B78E
0x14000b780  inc     edx
0x14000b782  inc     r14
0x14000b785  inc     rcx
0x14000b788  cmp     r14, 5
0x14000b78c  jl      short loc_14000B77B
0x14000b78e  test    r14, r14
0x14000b791  jle     loc_14000B882
0x14000b797  mov     rax, rva qword_14001A750[r12+r13*8]
0x14000b79f  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x14000b7a5  movsx   r12d, byte ptr [rcx+r12+19960h]
0x14000b7ae  inc     r12d
0x14000b7b1  mov     eax, r12d
0x14000b7b4  sub     eax, edx
0x14000b7b6  mov     dword ptr [rbp+4Fh+var_A0], eax
0x14000b7b9  mov     r8, [rbp+4Fh+var_B0]
0x14000b7bd  sub     r8, rsi
0x14000b7c0  movsxd  r9, eax
0x14000b7c3  cmp     r9, r8
0x14000b7c6  jg      loc_14000BA59
0x14000b7cc  mov     rcx, rdi
0x14000b7cf  lea     r8, cs:140000000h
0x14000b7d6  lea     rdx, ds:3Eh[r15*8]
0x14000b7de  add     rdx, rva qword_14001A750[r8+r11*8]
0x14000b7e6  mov     al, [rdx]
0x14000b7e8  mov     [rbp+rcx+4Fh+var_50], al
0x14000b7ec  inc     rcx
0x14000b7ef  inc     rdx
0x14000b7f2  cmp     rcx, r14
0x14000b7f5  jl      short loc_14000B7E6
0x14000b7f7  test    r9, r9
0x14000b7fa  jle     short loc_14000B819
0x14000b7fc  lea     rcx, [rbp+4Fh+var_50]
0x14000b800  add     rcx, r14
0x14000b803  mov     r8, r9
0x14000b806  mov     rdx, rsi
0x14000b809  call    sub_14000D3F0
0x14000b80e  mov     r10, [rbp+4Fh+var_A8]
0x14000b812  lea     r8, cs:140000000h
0x14000b819  mov     rdx, rdi
0x14000b81c  lea     rcx, [rdx+r15*8]
0x14000b820  mov     rax, rva qword_14001A750[r8+r13*8]
0x14000b828  mov     [rcx+rax+3Eh], dil
0x14000b82d  inc     rdx
0x14000b830  cmp     rdx, r14
0x14000b833  jl      short loc_14000B81C
0x14000b835  mov     [rbp+4Fh+var_80], rdi
0x14000b839  lea     rax, [rbp+4Fh+var_50]
0x14000b83d  mov     [rbp+4Fh+var_78], rax
0x14000b841  mov     eax, edi
0x14000b843  cmp     r12d, 4
0x14000b847  setz    al
0x14000b84a  inc     eax
0x14000b84c  mov     r12d, eax
0x14000b84f  mov     r8d, eax
0x14000b852  mov     [rsp+100h+lpOverlapped], r10
0x14000b857  lea     r9, [rbp+4Fh+var_80]
0x14000b85b  lea     rdx, [rbp+4Fh+var_78]
0x14000b85f  lea     rcx, [rbp+4Fh+var_BC]
0x14000b863  call    sub_14000A864
0x14000b868  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b86c  jz      loc_14000BAE5
0x14000b872  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x14000b875  dec     eax
0x14000b877  movsxd  rcx, eax
0x14000b87a  add     rsi, rcx
0x14000b87d  jmp     loc_14000B984
0x14000b882  movzx   eax, byte ptr [rsi]
0x14000b885  movsx   r13, byte ptr [rax+r12+19960h]
0x14000b88e  lea     ecx, [r13+1]
0x14000b892  mov     r9, [rbp+4Fh+var_B0]
0x14000b896  sub     r9, rsi
0x14000b899  movsxd  rax, ecx
0x14000b89c  cmp     rax, r9
0x14000b89f  jg      loc_14000BA8F
0x14000b8a5  mov     [rbp+4Fh+var_A0], rdi
0x14000b8a9  mov     [rbp+4Fh+var_70], rsi
0x14000b8ad  mov     eax, edi
0x14000b8af  cmp     ecx, 4
0x14000b8b2  setz    al
0x14000b8b5  inc     eax
0x14000b8b7  mov     r14d, eax
0x14000b8ba  mov     r8d, eax
0x14000b8bd  mov     [rsp+100h+lpOverlapped], r10
0x14000b8c2  lea     r9, [rbp+4Fh+var_A0]
0x14000b8c6  lea     rdx, [rbp+4Fh+var_70]
0x14000b8ca  lea     rcx, [rbp+4Fh+var_BC]
0x14000b8ce  call    sub_14000A864
0x14000b8d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b8d7  jz      loc_14000BAE5
0x14000b8dd  add     rsi, r13
0x14000b8e0  mov     r12d, r14d
0x14000b8e3  mov     r13, [rbp+4Fh+var_88]
0x14000b8e7  jmp     loc_14000B984
0x14000b8ec  lea     r11, cs:140000000h
0x14000b8f3  mov     r8, rva qword_14001A750[r11+r13*8]
0x14000b8fb  mov     cl, [r8+r15*8+3Dh]
0x14000b900  test    cl, 4
0x14000b903  jz      short loc_14000B926
0x14000b905  mov     al, [r8+r15*8+3Eh]
0x14000b90a  mov     [rbp+4Fh+var_48], al
0x14000b90d  mov     al, [rsi]
0x14000b90f  mov     [rbp+4Fh+var_47], al
0x14000b912  and     cl, 0FBh
0x14000b915  mov     [r8+r15*8+3Dh], cl
0x14000b91a  mov     r8d, 2
0x14000b920  lea     rdx, [rbp+4Fh+var_48]
0x14000b924  jmp     short loc_14000B96F
0x14000b926  movzx   r9d, byte ptr [rsi]
0x14000b92a  mov     rax, [r10+18h]
0x14000b92e  mov     rcx, [rax]
0x14000b931  cmp     [rcx+r9*2], di
0x14000b936  jge     short loc_14000B969
0x14000b938  lea     r14, [rsi+1]
0x14000b93c  cmp     r14, [rbp+4Fh+var_B0]
0x14000b940  jnb     loc_14000BAC2
0x14000b946  mov     r9, r10
0x14000b949  mov     r8d, 2
0x14000b94f  mov     rdx, rsi
0x14000b952  lea     rcx, [rbp+4Fh+var_BC]
0x14000b956  call    _mbtowc_internal
0x14000b95b  cmp     eax, 0FFFFFFFFh
0x14000b95e  jz      loc_14000BAE5
0x14000b964  mov     rsi, r14
0x14000b967  jmp     short loc_14000B984
0x14000b969  mov     r8, r12
0x14000b96c  mov     rdx, rsi
0x14000b96f  mov     r9, r10
0x14000b972  lea     rcx, [rbp+4Fh+var_BC]
0x14000b976  call    _mbtowc_internal
0x14000b97b  cmp     eax, 0FFFFFFFFh
0x14000b97e  jz      loc_14000BAE5
0x14000b984  inc     rsi
0x14000b987  mov     [rsp+38h], rdi
0x14000b98c  mov     [rsp+100h+var_D0], rdi
0x14000b991  mov     dword ptr [rsp+100h+var_D8], 5
0x14000b999  lea     rax, [rbp+4Fh+Buffer]
0x14000b99d  mov     [rsp+100h+lpOverlapped], rax
0x14000b9a2  mov     r9d, r12d
0x14000b9a5  lea     r8, [rbp+4Fh+var_BC]
0x14000b9a9  xor     edx, edx
0x14000b9ab  mov     ecx, [rbp+4Fh+var_98]
0x14000b9ae  call    __acrt_WideCharToMultiByte
0x14000b9b3  mov     r14d, eax
0x14000b9b6  test    eax, eax
0x14000b9b8  jz      loc_14000BAE5
0x14000b9be  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x14000b9c1  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14000b9c6  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000b9ca  mov     r8d, eax; nNumberOfBytesToWrite
0x14000b9cd  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x14000b9d1  mov     r12, [rbp+4Fh+hFile]
0x14000b9d5  mov     rcx, r12; hFile
0x14000b9d8  call    cs:WriteFile
0x14000b9de  test    eax, eax
0x14000b9e0  jz      loc_14000BADD
0x14000b9e6  mov     edx, [rbx+8]
0x14000b9e9  sub     edx, dword ptr [rbp+4Fh+var_90]
0x14000b9ec  add     edx, esi
0x14000b9ee  mov     [rbx+4], edx
0x14000b9f1  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14000b9f5  jb      loc_14000BAE5
0x14000b9fb  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x14000b9ff  jnz     short loc_14000BA3F
0x14000ba01  mov     eax, 0Dh
0x14000ba06  mov     [rbp+4Fh+var_C0], ax
0x14000ba0a  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14000ba0f  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000ba13  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x14000ba17  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x14000ba1b  mov     rcx, r12; hFile
0x14000ba1e  call    cs:WriteFile
0x14000ba24  test    eax, eax
0x14000ba26  jz      loc_14000BADD
0x14000ba2c  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14000ba30  jb      loc_14000BAE5
0x14000ba36  inc     dword ptr [rbx+8]
0x14000ba39  inc     dword ptr [rbx+4]
0x14000ba3c  mov     edx, [rbx+4]
0x14000ba3f  cmp     rsi, [rbp+4Fh+var_B0]
0x14000ba43  jnb     loc_14000BAE5
0x14000ba49  mov     r10, [rbp+4Fh+var_A8]
0x14000ba4d  mov     r11, [rbp+4Fh+var_60]
0x14000ba51  mov     ecx, [rbp+4Fh+var_94]
0x14000ba54  jmp     loc_14000B745
0x14000ba59  test    r8, r8
0x14000ba5c  jle     short loc_14000BA89
0x14000ba5e  sub     rsi, r14
0x14000ba61  lea     r9, cs:140000000h
0x14000ba68  lea     rdx, [r14+r15*8]
0x14000ba6c  mov     rcx, rva qword_14001A750[r9+r13*8]
0x14000ba74  mov     al, [rsi+r14]
0x14000ba78  mov     [rdx+rcx+3Eh], al
0x14000ba7c  inc     edi
0x14000ba7e  inc     r14
0x14000ba81  movsxd  rax, edi
0x14000ba84  cmp     rax, r8
0x14000ba87  jl      short loc_14000BA68
0x14000ba89  add     [rbx+4], r8d
0x14000ba8d  jmp     short loc_14000BAE5
0x14000ba8f  test    r9, r9
0x14000ba92  jle     short loc_14000BABC
0x14000ba94  mov     r8, rdi
0x14000ba97  mov     r10, [rbp+4Fh+var_88]
0x14000ba9b  lea     rdx, [r8+r15*8]
0x14000ba9f  mov     rcx, rva qword_14001A750[r12+r10*8]
0x14000baa7  mov     al, [r8+rsi]
0x14000baab  mov     [rdx+rcx+3Eh], al
0x14000baaf  inc     edi
0x14000bab1  inc     r8
0x14000bab4  movsxd  rax, edi
0x14000bab7  cmp     rax, r9
0x14000baba  jl      short loc_14000BA9B
0x14000babc  add     [rbx+4], r9d
0x14000bac0  jmp     short loc_14000BAE5
0x14000bac2  mov     [r8+r15*8+3Eh], r9b
0x14000bac7  mov     rax, rva qword_14001A750[r11+r13*8]
0x14000bacf  or      byte ptr [rax+r15*8+3Dh], 4
0x14000bad5  lea     eax, [rdx+1]
0x14000bad8  mov     [rbx+4], eax
0x14000badb  jmp     short loc_14000BAE5
0x14000badd  call    cs:GetLastError
0x14000bae3  mov     [rbx], eax
0x14000bae5  mov     rax, rbx
0x14000bae8  mov     rcx, [rbp+4Fh+var_38]
0x14000baec  xor     rcx, rsp; StackCookie
0x14000baef  call    __security_check_cookie
0x14000baf4  mov     rbx, [rsp+100h+arg_0]
0x14000bafc  add     rsp, 0D0h
0x14000bb03  pop     r15
0x14000bb05  pop     r14
0x14000bb07  pop     r13
0x14000bb09  pop     r12
  ... truncated ...
```
