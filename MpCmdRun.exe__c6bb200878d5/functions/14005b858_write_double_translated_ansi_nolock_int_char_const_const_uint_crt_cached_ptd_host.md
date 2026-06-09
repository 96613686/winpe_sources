# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x14005b858`
- end: `0x14005bceb`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(__int64, int, _BYTE *, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14005c23c`

## callees

- `0x140036780`
- `0x14004c130`
- `0x14005b858`
- `0x140066ac8`
- `0x140066fbc`
- `0x14006bd48`
- `0x140120780`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005bcb9`
- `KERNEL32!GetLastError` at `0x14005bcb9`
- `KERNEL32!WriteFile` at `0x14005bbb4`
- `KERNEL32!WriteFile` at `0x14005bbfa`
- `KERNEL32!WriteFile` at `0x14005bbb4`
- `KERNEL32!WriteFile` at `0x14005bbfa`
- `KERNEL32!GetConsoleOutputCP` at `0x14005b8d7`
- `KERNEL32!GetConsoleOutputCP` at `0x14005b8d7`

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
  hFile = *(HANDLE *)(qword_140195270[v8] + 72LL * (a2 & 0x3F) + 40);
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
        v19 = (_BYTE *)(qword_140195270[v14] + 8 * v9 + 62);
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
          v26 = *((char *)qword_14018D420 + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_140195270[v39] + 62) = v5[v38];
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
          if ( sub_140066FBC((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)qword_14018D420 + *(unsigned __int8 *)(qword_140195270[v8] + 8 * v9 + 62)) + 1;
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
                *(_BYTE *)(v18 + 8 * v9 + qword_140195270[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_140195270[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            sub_140120780(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_140195270[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_140066FBC((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_140195270[v8];
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
          *(_BYTE *)(qword_140195270[v8] + 8 * v9 + 61) |= 4u;
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
0x14005b858  mov     rax, rsp
0x14005b85b  push    rbp
0x14005b85c  push    rsi
0x14005b85d  push    rdi
0x14005b85e  push    r12
0x14005b860  push    r13
0x14005b862  push    r14
0x14005b864  push    r15
0x14005b866  lea     rbp, [rax-57h]
0x14005b86a  sub     rsp, 0D0h
0x14005b871  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x14005b879  mov     [rax+8], rbx
0x14005b87d  mov     rax, cs:__security_cookie
0x14005b884  xor     rax, rsp
0x14005b887  mov     [rbp+4Fh+var_38], rax
0x14005b88b  mov     rsi, r8
0x14005b88e  mov     [rbp+4Fh+var_90], r8
0x14005b892  movsxd  r14, edx
0x14005b895  mov     rbx, rcx
0x14005b898  mov     rax, [rbp+4Fh+arg_20]
0x14005b89c  mov     [rbp+4Fh+var_A8], rax
0x14005b8a0  mov     rax, r14
0x14005b8a3  mov     r13, r14
0x14005b8a6  sar     r13, 6
0x14005b8aa  mov     [rbp+4Fh+var_88], r13
0x14005b8ae  lea     rcx, __ImageBase
0x14005b8b5  and     eax, 3Fh
0x14005b8b8  lea     r15, [rax+rax*8]
0x14005b8bc  mov     rax, rva qword_140195270[rcx+r13*8]
0x14005b8c4  mov     rax, [rax+r15*8+28h]
0x14005b8c9  mov     [rbp+4Fh+hFile], rax
0x14005b8cd  mov     r12d, r9d
0x14005b8d0  add     r12, r8
0x14005b8d3  mov     [rbp+4Fh+var_B0], r12
0x14005b8d7  call    cs:GetConsoleOutputCP
0x14005b8dd  mov     [rbp+4Fh+var_98], eax
0x14005b8e0  xor     edi, edi
0x14005b8e2  mov     r10, [rbp+4Fh+var_A8]
0x14005b8e6  cmp     [r10+28h], dil
0x14005b8ea  jnz     short loc_14005B8F8
0x14005b8ec  mov     rcx, r10; this
0x14005b8ef  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14005b8f4  mov     r10, [rbp+4Fh+var_A8]
0x14005b8f8  mov     rcx, [r10+18h]
0x14005b8fc  mov     ecx, [rcx+0Ch]
0x14005b8ff  mov     [rbp+4Fh+var_94], ecx
0x14005b902  xor     eax, eax
0x14005b904  mov     [rbx], rax
0x14005b907  mov     [rbx+8], eax
0x14005b90a  cmp     [rbp+4Fh+var_90], r12
0x14005b90e  jnb     loc_14005BCC1
0x14005b914  mov     r11, r14
0x14005b917  sar     r11, 6
0x14005b91b  mov     [rbp+4Fh+var_60], r11
0x14005b91f  mov     edx, edi
0x14005b921  mov     al, [rsi]
0x14005b923  mov     byte ptr [rbp+4Fh+var_C0], al
0x14005b926  mov     [rbp+4Fh+var_BC], edi
0x14005b929  mov     r12d, 1
0x14005b92f  cmp     ecx, 0FDE9h
0x14005b935  jnz     loc_14005BAC8
0x14005b93b  mov     edx, edi
0x14005b93d  mov     r14, rdi
0x14005b940  lea     r12, __ImageBase
0x14005b947  lea     rcx, ds:3Eh[r15*8]
0x14005b94f  add     rcx, rva qword_140195270[r12+r11*8]
0x14005b957  cmp     [rcx], dil
0x14005b95a  jz      short loc_14005B96A
0x14005b95c  inc     edx
0x14005b95e  inc     r14
0x14005b961  inc     rcx
0x14005b964  cmp     r14, 5
0x14005b968  jl      short loc_14005B957
0x14005b96a  test    r14, r14
0x14005b96d  jle     loc_14005BA5E
0x14005b973  mov     rax, rva qword_140195270[r12+r13*8]
0x14005b97b  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x14005b981  movsx   r12d, byte ptr [rcx+r12+18D420h]
0x14005b98a  inc     r12d
0x14005b98d  mov     eax, r12d
0x14005b990  sub     eax, edx
0x14005b992  mov     dword ptr [rbp+4Fh+var_A0], eax
0x14005b995  mov     r8, [rbp+4Fh+var_B0]
0x14005b999  sub     r8, rsi
0x14005b99c  movsxd  r9, eax
0x14005b99f  cmp     r9, r8
0x14005b9a2  jg      loc_14005BC35
0x14005b9a8  mov     rcx, rdi
0x14005b9ab  lea     r8, __ImageBase
0x14005b9b2  lea     rdx, ds:3Eh[r15*8]
0x14005b9ba  add     rdx, rva qword_140195270[r8+r11*8]
0x14005b9c2  mov     al, [rdx]
0x14005b9c4  mov     [rbp+rcx+4Fh+var_50], al
0x14005b9c8  inc     rcx
0x14005b9cb  inc     rdx
0x14005b9ce  cmp     rcx, r14
0x14005b9d1  jl      short loc_14005B9C2
0x14005b9d3  test    r9, r9
0x14005b9d6  jle     short loc_14005B9F5
0x14005b9d8  lea     rcx, [rbp+4Fh+var_50]
0x14005b9dc  add     rcx, r14
0x14005b9df  mov     r8, r9
0x14005b9e2  mov     rdx, rsi
0x14005b9e5  call    sub_140120780
0x14005b9ea  mov     r10, [rbp+4Fh+var_A8]
0x14005b9ee  lea     r8, __ImageBase
0x14005b9f5  mov     rdx, rdi
0x14005b9f8  lea     rcx, [rdx+r15*8]
0x14005b9fc  mov     rax, rva qword_140195270[r8+r13*8]
0x14005ba04  mov     [rcx+rax+3Eh], dil
0x14005ba09  inc     rdx
0x14005ba0c  cmp     rdx, r14
0x14005ba0f  jl      short loc_14005B9F8
0x14005ba11  mov     [rbp+4Fh+var_80], rdi
0x14005ba15  lea     rax, [rbp+4Fh+var_50]
0x14005ba19  mov     [rbp+4Fh+var_78], rax
0x14005ba1d  mov     eax, edi
0x14005ba1f  cmp     r12d, 4
0x14005ba23  setz    al
0x14005ba26  inc     eax
0x14005ba28  mov     r12d, eax
0x14005ba2b  mov     r8d, eax
0x14005ba2e  mov     [rsp+100h+lpOverlapped], r10
0x14005ba33  lea     r9, [rbp+4Fh+var_80]
0x14005ba37  lea     rdx, [rbp+4Fh+var_78]
0x14005ba3b  lea     rcx, [rbp+4Fh+var_BC]
0x14005ba3f  call    sub_140066FBC
0x14005ba44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005ba48  jz      loc_14005BCC1
0x14005ba4e  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x14005ba51  dec     eax
0x14005ba53  movsxd  rcx, eax
0x14005ba56  add     rsi, rcx
0x14005ba59  jmp     loc_14005BB60
0x14005ba5e  movzx   eax, byte ptr [rsi]
0x14005ba61  movsx   r13, byte ptr [rax+r12+18D420h]
0x14005ba6a  lea     ecx, [r13+1]
0x14005ba6e  mov     r9, [rbp+4Fh+var_B0]
0x14005ba72  sub     r9, rsi
0x14005ba75  movsxd  rax, ecx
0x14005ba78  cmp     rax, r9
0x14005ba7b  jg      loc_14005BC6B
0x14005ba81  mov     [rbp+4Fh+var_A0], rdi
0x14005ba85  mov     [rbp+4Fh+var_70], rsi
0x14005ba89  mov     eax, edi
0x14005ba8b  cmp     ecx, 4
0x14005ba8e  setz    al
0x14005ba91  inc     eax
0x14005ba93  mov     r14d, eax
0x14005ba96  mov     r8d, eax
0x14005ba99  mov     [rsp+100h+lpOverlapped], r10
0x14005ba9e  lea     r9, [rbp+4Fh+var_A0]
0x14005baa2  lea     rdx, [rbp+4Fh+var_70]
0x14005baa6  lea     rcx, [rbp+4Fh+var_BC]
0x14005baaa  call    sub_140066FBC
0x14005baaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005bab3  jz      loc_14005BCC1
0x14005bab9  add     rsi, r13
0x14005babc  mov     r12d, r14d
0x14005babf  mov     r13, [rbp+4Fh+var_88]
0x14005bac3  jmp     loc_14005BB60
0x14005bac8  lea     r11, __ImageBase
0x14005bacf  mov     r8, rva qword_140195270[r11+r13*8]
0x14005bad7  mov     cl, [r8+r15*8+3Dh]
0x14005badc  test    cl, 4
0x14005badf  jz      short loc_14005BB02
0x14005bae1  mov     al, [r8+r15*8+3Eh]
0x14005bae6  mov     [rbp+4Fh+var_48], al
0x14005bae9  mov     al, [rsi]
0x14005baeb  mov     [rbp+4Fh+var_47], al
0x14005baee  and     cl, 0FBh
0x14005baf1  mov     [r8+r15*8+3Dh], cl
0x14005baf6  mov     r8d, 2
0x14005bafc  lea     rdx, [rbp+4Fh+var_48]
0x14005bb00  jmp     short loc_14005BB4B
0x14005bb02  movzx   r9d, byte ptr [rsi]
0x14005bb06  mov     rax, [r10+18h]
0x14005bb0a  mov     rcx, [rax]
0x14005bb0d  cmp     [rcx+r9*2], di
0x14005bb12  jge     short loc_14005BB45
0x14005bb14  lea     r14, [rsi+1]
0x14005bb18  cmp     r14, [rbp+4Fh+var_B0]
0x14005bb1c  jnb     loc_14005BC9E
0x14005bb22  mov     r9, r10
0x14005bb25  mov     r8d, 2
0x14005bb2b  mov     rdx, rsi
0x14005bb2e  lea     rcx, [rbp+4Fh+var_BC]
0x14005bb32  call    _mbtowc_internal
0x14005bb37  cmp     eax, 0FFFFFFFFh
0x14005bb3a  jz      loc_14005BCC1
0x14005bb40  mov     rsi, r14
0x14005bb43  jmp     short loc_14005BB60
0x14005bb45  mov     r8, r12
0x14005bb48  mov     rdx, rsi
0x14005bb4b  mov     r9, r10
0x14005bb4e  lea     rcx, [rbp+4Fh+var_BC]
0x14005bb52  call    _mbtowc_internal
0x14005bb57  cmp     eax, 0FFFFFFFFh
0x14005bb5a  jz      loc_14005BCC1
0x14005bb60  inc     rsi
0x14005bb63  mov     [rsp+38h], rdi
0x14005bb68  mov     [rsp+100h+var_D0], rdi
0x14005bb6d  mov     dword ptr [rsp+100h+var_D8], 5
0x14005bb75  lea     rax, [rbp+4Fh+Buffer]
0x14005bb79  mov     [rsp+100h+lpOverlapped], rax
0x14005bb7e  mov     r9d, r12d
0x14005bb81  lea     r8, [rbp+4Fh+var_BC]
0x14005bb85  xor     edx, edx
0x14005bb87  mov     ecx, [rbp+4Fh+var_98]
0x14005bb8a  call    __acrt_WideCharToMultiByte
0x14005bb8f  mov     r14d, eax
0x14005bb92  test    eax, eax
0x14005bb94  jz      loc_14005BCC1
0x14005bb9a  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x14005bb9d  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14005bba2  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005bba6  mov     r8d, eax; nNumberOfBytesToWrite
0x14005bba9  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x14005bbad  mov     r12, [rbp+4Fh+hFile]
0x14005bbb1  mov     rcx, r12; hFile
0x14005bbb4  call    cs:WriteFile
0x14005bbba  test    eax, eax
0x14005bbbc  jz      loc_14005BCB9
0x14005bbc2  mov     edx, [rbx+8]
0x14005bbc5  sub     edx, dword ptr [rbp+4Fh+var_90]
0x14005bbc8  add     edx, esi
0x14005bbca  mov     [rbx+4], edx
0x14005bbcd  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14005bbd1  jb      loc_14005BCC1
0x14005bbd7  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x14005bbdb  jnz     short loc_14005BC1B
0x14005bbdd  mov     eax, 0Dh
0x14005bbe2  mov     [rbp+4Fh+var_C0], ax
0x14005bbe6  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14005bbeb  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005bbef  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x14005bbf3  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x14005bbf7  mov     rcx, r12; hFile
0x14005bbfa  call    cs:WriteFile
0x14005bc00  test    eax, eax
0x14005bc02  jz      loc_14005BCB9
0x14005bc08  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14005bc0c  jb      loc_14005BCC1
0x14005bc12  inc     dword ptr [rbx+8]
0x14005bc15  inc     dword ptr [rbx+4]
0x14005bc18  mov     edx, [rbx+4]
0x14005bc1b  cmp     rsi, [rbp+4Fh+var_B0]
0x14005bc1f  jnb     loc_14005BCC1
0x14005bc25  mov     r10, [rbp+4Fh+var_A8]
0x14005bc29  mov     r11, [rbp+4Fh+var_60]
0x14005bc2d  mov     ecx, [rbp+4Fh+var_94]
0x14005bc30  jmp     loc_14005B921
0x14005bc35  test    r8, r8
0x14005bc38  jle     short loc_14005BC65
0x14005bc3a  sub     rsi, r14
0x14005bc3d  lea     r9, __ImageBase
0x14005bc44  lea     rdx, [r14+r15*8]
0x14005bc48  mov     rcx, rva qword_140195270[r9+r13*8]
0x14005bc50  mov     al, [rsi+r14]
0x14005bc54  mov     [rdx+rcx+3Eh], al
0x14005bc58  inc     edi
0x14005bc5a  inc     r14
0x14005bc5d  movsxd  rax, edi
0x14005bc60  cmp     rax, r8
0x14005bc63  jl      short loc_14005BC44
0x14005bc65  add     [rbx+4], r8d
0x14005bc69  jmp     short loc_14005BCC1
0x14005bc6b  test    r9, r9
0x14005bc6e  jle     short loc_14005BC98
0x14005bc70  mov     r8, rdi
0x14005bc73  mov     r10, [rbp+4Fh+var_88]
0x14005bc77  lea     rdx, [r8+r15*8]
0x14005bc7b  mov     rcx, rva qword_140195270[r12+r10*8]
0x14005bc83  mov     al, [r8+rsi]
0x14005bc87  mov     [rdx+rcx+3Eh], al
0x14005bc8b  inc     edi
0x14005bc8d  inc     r8
0x14005bc90  movsxd  rax, edi
0x14005bc93  cmp     rax, r9
0x14005bc96  jl      short loc_14005BC77
0x14005bc98  add     [rbx+4], r9d
0x14005bc9c  jmp     short loc_14005BCC1
0x14005bc9e  mov     [r8+r15*8+3Eh], r9b
0x14005bca3  mov     rax, rva qword_140195270[r11+r13*8]
0x14005bcab  or      byte ptr [rax+r15*8+3Dh], 4
0x14005bcb1  lea     eax, [rdx+1]
0x14005bcb4  mov     [rbx+4], eax
0x14005bcb7  jmp     short loc_14005BCC1
0x14005bcb9  call    cs:GetLastError
0x14005bcbf  mov     [rbx], eax
0x14005bcc1  mov     rax, rbx
0x14005bcc4  mov     rcx, [rbp+4Fh+var_38]
0x14005bcc8  xor     rcx, rsp; StackCookie
0x14005bccb  call    __security_check_cookie
0x14005bcd0  mov     rbx, [rsp+100h+arg_0]
0x14005bcd8  add     rsp, 0D0h
0x14005bcdf  pop     r15
0x14005bce1  pop     r14
0x14005bce3  pop     r13
0x14005bce5  pop     r12
  ... truncated ...
```
