# ReadTiffData

- ea: `0x18000e16c`
- end: `0x18000e436`
- name: `ReadTiffData`
- size: `714`
- prototype: `char *__fastcall(_DWORD *, unsigned int, _DWORD *, unsigned int *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000dc98`

## callees

- `0x1800091a0`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000d3d0`
- `0x18000e16c`
- `0x18000e790`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bc2`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e1fc`
- `KERNEL32!GetLastError` at `0x18000e2f2`
- `KERNEL32!GetLastError` at `0x18000e1fc`
- `KERNEL32!GetLastError` at `0x18000e2f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ReadTiffData(_DWORD *a1, unsigned int a2, _DWORD *a3, unsigned int *a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int *v6; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbx
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // r15d
  unsigned int v18; // edi
  size_t v19; // rbx
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  char *v22; // rbp
  __int64 v23; // rbx
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  void *v28; // r14
  char *v29; // r15
  unsigned int v30; // r12d
  unsigned int v32; // [rsp+30h] [rbp-68h] BYREF
  int v33; // [rsp+38h] [rbp-60h]
  int v34; // [rsp+3Ch] [rbp-5Ch]
  int v35; // [rsp+40h] [rbp-58h]
  char *v36; // [rsp+48h] [rbp-50h]

  v6 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids);
  }
  if ( !(unsigned int)TiffSeekToPage((__int64)a1, a2, 2) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    v14 = 11;
    v15 = v12;
    v16 = LastError;
    goto LABEL_10;
  }
  v17 = a1[391];
  v18 = a1[392];
  v33 = v17;
  v19 = (unsigned int)(v17 + 7) >> 3;
  v20 = v19 * v18;
  if ( v20 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v18, (unsigned int)(v17 + 7) >> 3);
    }
    return 0;
  }
  v34 = a1[421];
  v35 = a1[422];
  v21 = pMemAlloc((unsigned int)v20);
  v36 = (char *)v21;
  v22 = (char *)v21;
  if ( !v21 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v14 = 15;
    v16 = v18 * (unsigned int)v19;
LABEL_10:
    WPP_SF_d(v15, v14, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids, v16);
    return 0;
  }
  v32 = v18;
  if ( !(unsigned int)TiffUncompressMmrPage(a1, v21, (unsigned int)v19 * v18, &v32) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v24 = GetLastError();
    v25 = 16;
    v26 = v23;
    v27 = v24;
LABEL_27:
    WPP_SF_d(v26, v25, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids, v27);
LABEL_28:
    pMemFree(v22);
    return 0;
  }
  v28 = (void *)pMemAlloc((unsigned int)(v17 + 7) >> 3);
  if ( !v28 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v25 = 17;
    v27 = (unsigned int)v19;
    goto LABEL_27;
  }
  if ( v18 >> 1 )
  {
    v29 = &v22[(unsigned int)v19 * (v18 - 1)];
    v30 = 0;
    do
    {
      memcpy_0(v28, v22, v19);
      memcpy_0(v22, v29, v19);
      memcpy_0(v29, v28, v19);
      v22 += v19;
      v29 -= v19;
      ++v30;
    }
    while ( v30 < v18 >> 1 );
    v22 = v36;
    v6 = a4;
    v17 = v33;
  }
  pMemFree(v28);
  if ( a3 )
    *a3 = v17;
  if ( v6 )
    *v6 = v18;
  if ( a5 )
    *a5 = v34;
  if ( a6 )
    *a6 = v35;
  return v22;
}

```

## disassembly

```asm
0x18000e16c  mov     [rsp+arg_18], r9
0x18000e171  push    rbx
0x18000e172  push    rbp
0x18000e173  push    rsi
0x18000e174  push    rdi
0x18000e175  push    r12
0x18000e177  push    r13
0x18000e179  push    r14
0x18000e17b  push    r15
0x18000e17d  sub     rsp, 58h
0x18000e181  mov     r12, r9
0x18000e184  mov     r13, r8
0x18000e187  mov     ebx, edx
0x18000e189  mov     rsi, rcx
0x18000e18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e193  lea     r14, WPP_GLOBAL_Control
0x18000e19a  mov     ebp, 2
0x18000e19f  cmp     rcx, r14
0x18000e1a2  jz      short loc_18000E1C3
0x18000e1a4  test    [rcx+1Ch], bpl
0x18000e1a8  jz      short loc_18000E1C3
0x18000e1aa  cmp     byte ptr [rcx+19h], 5
0x18000e1ae  jb      short loc_18000E1C3
0x18000e1b0  mov     rcx, [rcx+10h]
0x18000e1b4  lea     edx, [rbp+8]
0x18000e1b7  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e1be  call    WPP_SF_
0x18000e1c3  mov     r8d, ebp
0x18000e1c6  mov     edx, ebx
0x18000e1c8  mov     rcx, rsi
0x18000e1cb  call    TiffSeekToPage
0x18000e1d0  test    eax, eax
0x18000e1d2  jnz     short loc_18000E21E
0x18000e1d4  mov     rbx, cs:WPP_GLOBAL_Control
0x18000e1db  cmp     rbx, r14
0x18000e1de  jz      loc_18000E423
0x18000e1e4  test    [rbx+1Ch], bpl
0x18000e1e8  jz      loc_18000E423
0x18000e1ee  cmp     [rbx+19h], bpl
0x18000e1f2  jb      loc_18000E423
0x18000e1f8  mov     rbx, [rbx+10h]
0x18000e1fc  call    cs:__imp_GetLastError
0x18000e202  mov     edx, 0Bh
0x18000e207  mov     rcx, rbx
0x18000e20a  mov     r9d, eax
0x18000e20d  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e214  call    WPP_SF_d
0x18000e219  jmp     loc_18000E423
0x18000e21e  mov     r15d, [rsi+61Ch]
0x18000e225  mov     ecx, 0FFFFFFFFh
0x18000e22a  mov     edi, [rsi+620h]
0x18000e230  mov     eax, edi
0x18000e232  mov     [rsp+98h+var_60], r15d
0x18000e237  lea     ebx, [r15+7]
0x18000e23b  shr     ebx, 3
0x18000e23e  imul    rax, rbx
0x18000e242  cmp     rax, rcx
0x18000e245  ja      loc_18000E3FB
0x18000e24b  mov     r14d, eax
0x18000e24e  mov     eax, [rsi+694h]
0x18000e254  mov     ecx, r14d; dwBytes
0x18000e257  mov     [rsp+98h+var_5C], eax
0x18000e25b  mov     eax, [rsi+698h]
0x18000e261  mov     [rsp+98h+var_58], eax
0x18000e265  call    pMemAlloc
0x18000e26a  mov     [rsp+98h+var_50], rax
0x18000e26f  mov     rbp, rax
0x18000e272  test    rax, rax
0x18000e275  jnz     short loc_18000E2B4
0x18000e277  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e27e  lea     rax, WPP_GLOBAL_Control
0x18000e285  cmp     rcx, rax
0x18000e288  jz      loc_18000E423
0x18000e28e  test    byte ptr [rcx+1Ch], 2
0x18000e292  jz      loc_18000E423
0x18000e298  cmp     byte ptr [rcx+19h], 2
0x18000e29c  jb      loc_18000E423
0x18000e2a2  mov     rcx, [rcx+10h]
0x18000e2a6  lea     edx, [rbp+0Fh]
0x18000e2a9  imul    ebx, edi
0x18000e2ac  mov     r9d, ebx
0x18000e2af  jmp     loc_18000E20D
0x18000e2b4  lea     r9, [rsp+98h+var_68]
0x18000e2b9  mov     [rsp+98h+var_68], edi
0x18000e2bd  mov     r8d, r14d
0x18000e2c0  mov     rdx, rbp
0x18000e2c3  mov     rcx, rsi
0x18000e2c6  call    TiffUncompressMmrPage
0x18000e2cb  test    eax, eax
0x18000e2cd  jnz     short loc_18000E305
0x18000e2cf  mov     rbx, cs:WPP_GLOBAL_Control
0x18000e2d6  lea     rax, WPP_GLOBAL_Control
0x18000e2dd  cmp     rbx, rax
0x18000e2e0  jz      short loc_18000E34B
0x18000e2e2  test    byte ptr [rbx+1Ch], 2
0x18000e2e6  jz      short loc_18000E34B
0x18000e2e8  cmp     byte ptr [rbx+19h], 2
0x18000e2ec  jb      short loc_18000E34B
0x18000e2ee  mov     rbx, [rbx+10h]
0x18000e2f2  call    cs:__imp_GetLastError
0x18000e2f8  mov     edx, 10h
0x18000e2fd  mov     rcx, rbx
0x18000e300  mov     r9d, eax
0x18000e303  jmp     short loc_18000E33F
0x18000e305  mov     rcx, rbx; dwBytes
0x18000e308  call    pMemAlloc
0x18000e30d  mov     r14, rax
0x18000e310  test    rax, rax
0x18000e313  jnz     short loc_18000E358
0x18000e315  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e31c  lea     rax, WPP_GLOBAL_Control
0x18000e323  cmp     rcx, rax
0x18000e326  jz      short loc_18000E34B
0x18000e328  test    byte ptr [rcx+1Ch], 2
0x18000e32c  jz      short loc_18000E34B
0x18000e32e  cmp     byte ptr [rcx+19h], 2
0x18000e332  jb      short loc_18000E34B
0x18000e334  mov     rcx, [rcx+10h]
0x18000e338  lea     edx, [r14+11h]
0x18000e33c  mov     r9d, ebx
0x18000e33f  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e346  call    WPP_SF_d
0x18000e34b  mov     rcx, rbp; lpMem
0x18000e34e  call    pMemFree
0x18000e353  jmp     loc_18000E423
0x18000e358  mov     esi, edi
0x18000e35a  shr     esi, 1
0x18000e35c  jz      short loc_18000E3B6
0x18000e35e  lea     r15d, [rdi-1]
0x18000e362  imul    r15d, ebx
0x18000e366  add     r15, rbp
0x18000e369  xor     r12d, r12d
0x18000e36c  mov     r8, rbx; Size
0x18000e36f  mov     rdx, rbp; Src
0x18000e372  mov     rcx, r14; void *
0x18000e375  call    memcpy_0
0x18000e37a  mov     r8, rbx; Size
0x18000e37d  mov     rdx, r15; Src
0x18000e380  mov     rcx, rbp; void *
0x18000e383  call    memcpy_0
0x18000e388  mov     r8, rbx; Size
0x18000e38b  mov     rdx, r14; Src
0x18000e38e  mov     rcx, r15; void *
0x18000e391  call    memcpy_0
0x18000e396  add     rbp, rbx
0x18000e399  sub     r15, rbx
0x18000e39c  inc     r12d
0x18000e39f  cmp     r12d, esi
0x18000e3a2  jb      short loc_18000E36C
0x18000e3a4  mov     rbp, [rsp+98h+var_50]
0x18000e3a9  mov     r12, [rsp+98h+arg_18]
0x18000e3b1  mov     r15d, [rsp+98h+var_60]
0x18000e3b6  mov     rcx, r14; lpMem
0x18000e3b9  call    pMemFree
0x18000e3be  test    r13, r13
0x18000e3c1  jz      short loc_18000E3C7
0x18000e3c3  mov     [r13+0], r15d
0x18000e3c7  test    r12, r12
0x18000e3ca  jz      short loc_18000E3D0
0x18000e3cc  mov     [r12], edi
0x18000e3d0  mov     rax, [rsp+98h+arg_20]
0x18000e3d8  test    rax, rax
0x18000e3db  jz      short loc_18000E3E3
0x18000e3dd  mov     ecx, [rsp+98h+var_5C]
0x18000e3e1  mov     [rax], ecx
0x18000e3e3  mov     rax, [rsp+98h+arg_28]
0x18000e3eb  test    rax, rax
0x18000e3ee  jz      short loc_18000E3F6
0x18000e3f0  mov     ecx, [rsp+98h+var_58]
0x18000e3f4  mov     [rax], ecx
0x18000e3f6  mov     rax, rbp
0x18000e3f9  jmp     short loc_18000E425
0x18000e3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e402  cmp     rcx, r14
0x18000e405  jz      short loc_18000E423
0x18000e407  test    [rcx+1Ch], bpl
0x18000e40b  jz      short loc_18000E423
0x18000e40d  cmp     [rcx+19h], bpl
0x18000e411  jb      short loc_18000E423
0x18000e413  mov     rcx, [rcx+10h]
0x18000e417  mov     r9d, edi
0x18000e41a  mov     [rsp+98h+var_78], ebx
0x18000e41e  call    WPP_SF_LL
0x18000e423  xor     eax, eax
0x18000e425  add     rsp, 58h
0x18000e429  pop     r15
0x18000e42b  pop     r14
0x18000e42d  pop     r13
0x18000e42f  pop     r12
0x18000e431  pop     rdi
0x18000e432  pop     rsi
0x18000e433  pop     rbp
0x18000e434  pop     rbx
0x18000e435  retn
```
