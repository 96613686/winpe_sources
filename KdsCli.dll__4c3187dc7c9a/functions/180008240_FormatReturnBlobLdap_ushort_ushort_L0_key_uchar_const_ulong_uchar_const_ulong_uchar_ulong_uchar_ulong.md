# FormatReturnBlobLdap(ushort *,ushort *,_L0_key *,uchar * const,ulong,uchar * const,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180008240`
- end: `0x180008522`
- name: `?FormatReturnBlobLdap@@YAJPEAG0PEAU_L0_key@@QEAEK2KPEAEKPEAPEAEPEAK@Z`
- size: `738`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, struct _L0_key *, unsigned __int8 *const, unsigned int, unsigned __int8 *const, unsigned int, size_t, size_t, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`

## callees

- `0x180008240`
- `0x180010920`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x180008383`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall FormatReturnBlobLdap(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _L0_key *a3,
        unsigned __int8 *const a4,
        unsigned int a5,
        unsigned __int8 *const a6,
        unsigned int a7,
        unsigned __int8 *a8,
        size_t a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  __int64 v11; // r10
  __int64 v13; // r8
  __int64 v15; // rax
  __int64 v17; // rdi
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v21; // rcx
  size_t v22; // r11
  size_t v23; // rsi
  size_t v24; // rbp
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // r13d
  char *v28; // rax
  unsigned __int8 *v29; // rdi
  unsigned int v30; // r12d
  unsigned __int8 *v31; // rbx
  unsigned __int8 *v32; // rbx
  char *v33; // rbx
  char *v34; // rbx
  char *v35; // rbx
  char *v36; // rbx
  unsigned __int8 *v37; // rdx
  int v39; // [rsp+20h] [rbp-78h]
  size_t v40; // [rsp+28h] [rbp-70h]
  size_t Size; // [rsp+30h] [rbp-68h]
  size_t v42; // [rsp+38h] [rbp-60h]
  __int64 v43; // [rsp+40h] [rbp-58h]
  unsigned int v46; // [rsp+B0h] [rbp+18h]
  size_t v48; // [rsp+D8h] [rbp+40h]

  v11 = -1;
  v13 = *((_QWORD *)a3 + 5);
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v13 + 2 * v15) );
  v17 = *((unsigned int *)a3 + 14);
  v18 = 2 * v15 + 2;
  v19 = -1;
  Size = v18;
  v46 = *((_DWORD *)a3 + 14);
  do
    ++v19;
  while ( *(_WORD *)(*((_QWORD *)a3 + 8) + 2 * v19) );
  v21 = 2 * v19 + 2;
  v22 = *((unsigned int *)a3 + 20);
  v40 = v21;
  *a10 = 0;
  v39 = v22;
  *a11 = 0;
  if ( a8 )
  {
    v23 = (unsigned int)a9;
    v24 = 0;
  }
  else
  {
    v23 = 64;
    v24 = 64;
    if ( a7 == 31 )
    {
      v23 = 0;
    }
    else
    {
      v24 = -(__int64)(a5 != 0) & 0x40;
      v21 = 2 * v19 + 2;
    }
  }
  v25 = -1;
  do
    ++v25;
  while ( a1[v25] );
  v26 = 2 * v25 + 2;
  v42 = v26;
  do
    ++v11;
  while ( a2[v11] );
  v48 = v22;
  v43 = 2 * v11 + 2;
  v27 = v24 + v23 + v18 + v21 + 80 + v26 + v43 + v22 + v17;
  v28 = (char *)SIDKeyProvAlloc(v24 + v23 + v18 + v21 + 80 + v26 + v43 + v22 + v17);
  v29 = (unsigned __int8 *)v28;
  if ( v28 )
  {
    v30 = 0;
    *((_DWORD *)v28 + 10) = Size;
    *((_DWORD *)v28 + 11) = v46;
    *((_DWORD *)v28 + 12) = v40;
    *((_DWORD *)v28 + 13) = v39;
    *((_DWORD *)v28 + 14) = *((_DWORD *)a3 + 21);
    *((_DWORD *)v28 + 15) = *((_DWORD *)a3 + 22);
    *((_DWORD *)v28 + 16) = v24;
    *((_DWORD *)v28 + 17) = v23;
    *((_DWORD *)v28 + 3) = *(_DWORD *)a3;
    *((_DWORD *)v28 + 4) = a5;
    *((_DWORD *)v28 + 5) = a7;
    *((_DWORD *)v28 + 1) = 1263748171;
    *(_DWORD *)v28 = 1;
    if ( a8 )
      *((_DWORD *)v28 + 2) |= 1u;
    *((_DWORD *)v28 + 18) = v42;
    *((_DWORD *)v28 + 19) = v43;
    *(_OWORD *)(v28 + 24) = *(_OWORD *)((char *)a3 + 12);
    memcpy_0(v28 + 80, *((const void **)a3 + 5), Size);
    v31 = &v29[Size + 80];
    memcpy_0(v31, *((const void **)a3 + 6), v46);
    v32 = &v31[v46];
    memcpy_0(v32, *((const void **)a3 + 8), v40);
    v33 = (char *)&v32[v40];
    memcpy_0(v33, *((const void **)a3 + 9), v48);
    v34 = &v33[v48];
    memcpy_0(v34, a1, v42);
    v35 = &v34[v42];
    memcpy_0(v35, a2, v43);
    v36 = &v35[v43];
    if ( v24 )
    {
      memcpy_0(v36, a4, v24);
      v36 += v24;
    }
    if ( v23 )
    {
      v37 = a8;
      if ( !a8 )
        v37 = a6;
      memcpy_0(v36, v37, v23);
    }
    *a10 = v29;
    *a11 = v27;
  }
  else
  {
    v30 = -2147024882;
    SidKeyDebugTraceError(14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 94);
  }
  return v30;
}

```

## disassembly

```asm
0x180008240  mov     [rsp+arg_18], r9
0x180008245  mov     [rsp+arg_8], rdx
0x18000824a  mov     [rsp+Src], rcx
0x18000824f  push    rbx
0x180008250  push    rbp
0x180008251  push    rsi
0x180008252  push    rdi
0x180008253  push    r12
0x180008255  push    r13
0x180008257  push    r14
0x180008259  push    r15
0x18000825b  sub     rsp, 58h
0x18000825f  or      r10, 0FFFFFFFFFFFFFFFFh
0x180008263  mov     r14, r8
0x180008266  mov     r8, [r8+28h]
0x18000826a  mov     r12, rdx
0x18000826d  mov     rax, r10
0x180008270  xor     r13d, r13d
0x180008273  mov     rdx, rcx
0x180008276  inc     rax
0x180008279  cmp     [r8+rax*2], r13w
0x18000827e  jnz     short loc_180008276
0x180008280  mov     edi, [r14+38h]
0x180008284  lea     r9, ds:2[rax*2]
0x18000828c  mov     rcx, [r14+40h]
0x180008290  mov     rax, r10
0x180008293  mov     [rsp+98h+Size], r9
0x180008298  mov     dword ptr [rsp+98h+arg_10], edi
0x18000829f  inc     rax
0x1800082a2  cmp     [rcx+rax*2], r13w
0x1800082a7  jnz     short loc_18000829F
0x1800082a9  mov     r15, [rsp+98h+arg_38]
0x1800082b1  lea     rcx, ds:2[rax*2]
0x1800082b9  mov     rax, [rsp+98h+arg_48]
0x1800082c1  mov     r11d, [r14+50h]
0x1800082c5  mov     ebx, [rsp+98h+arg_30]
0x1800082cc  mov     [rsp+98h+var_70], rcx
0x1800082d1  mov     [rax], r13
0x1800082d4  mov     rax, [rsp+98h+arg_50]
0x1800082dc  mov     [rsp+98h+var_78], r11d
0x1800082e1  mov     [rax], r13d
0x1800082e4  test    r15, r15
0x1800082e7  jz      short loc_1800082F5
0x1800082e9  mov     esi, dword ptr [rsp+98h+arg_40]
0x1800082f0  mov     rbp, r13
0x1800082f3  jmp     short loc_18000831A
0x1800082f5  mov     esi, 40h ; '@'
0x1800082fa  mov     ebp, esi
0x1800082fc  cmp     ebx, 1Fh
0x1800082ff  jnz     short loc_180008306
0x180008301  mov     rsi, r13
0x180008304  jmp     short loc_18000831A
0x180008306  mov     eax, [rsp+98h+arg_20]
0x18000830d  neg     eax
0x18000830f  sbb     rcx, rcx
0x180008312  and     rbp, rcx
0x180008315  mov     rcx, [rsp+98h+var_70]
0x18000831a  mov     rax, r10
0x18000831d  inc     rax
0x180008320  cmp     [rdx+rax*2], r13w
0x180008325  jnz     short loc_18000831D
0x180008327  lea     rdx, ds:2[rax*2]
0x18000832f  mov     [rsp+98h+var_60], rdx
0x180008334  inc     r10
0x180008337  cmp     [r12+r10*2], r13w
0x18000833c  jnz     short loc_180008334
0x18000833e  lea     r8, ds:2[r10*2]
0x180008346  mov     [rsp+98h+arg_38], r11
0x18000834e  add     rcx, 50h ; 'P'
0x180008352  mov     [rsp+98h+var_58], r8
0x180008357  lea     r13, [r11+rdi]
0x18000835b  add     r13, r8
0x18000835e  add     r13, rdx
0x180008361  add     r13, rcx
0x180008364  add     r13, r9
0x180008367  add     r13, rsi
0x18000836a  add     r13, rbp
0x18000836d  mov     rcx, r13; unsigned __int64
0x180008370  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180008375  mov     rdi, rax
0x180008378  test    rax, rax
0x18000837b  jnz     short loc_1800083A6
0x18000837d  mov     r9d, 45Eh; unsigned int
0x180008383  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000838a  lea     rdx, aHr; "hr"
0x180008391  mov     ecx, 8007000Eh; unsigned int
0x180008396  mov     r12d, 8007000Eh
0x18000839c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800083a1  jmp     loc_18000850E
0x1800083a6  mov     rcx, [rsp+98h+Size]
0x1800083ab  xor     r12d, r12d
0x1800083ae  mov     edx, dword ptr [rsp+98h+arg_10]
0x1800083b5  mov     [rax+28h], ecx
0x1800083b8  mov     [rax+2Ch], edx
0x1800083bb  mov     rax, [rsp+98h+var_70]
0x1800083c0  mov     [rdi+30h], eax
0x1800083c3  mov     eax, [rsp+98h+var_78]
0x1800083c7  mov     [rdi+34h], eax
0x1800083ca  mov     eax, [r14+54h]
0x1800083ce  mov     [rdi+38h], eax
0x1800083d1  mov     eax, [r14+58h]
0x1800083d5  mov     [rdi+3Ch], eax
0x1800083d8  mov     [rdi+40h], ebp
0x1800083db  mov     [rdi+44h], esi
0x1800083de  mov     eax, [r14]
0x1800083e1  mov     [rdi+0Ch], eax
0x1800083e4  mov     eax, [rsp+98h+arg_20]
0x1800083eb  mov     [rdi+10h], eax
0x1800083ee  mov     [rdi+14h], ebx
0x1800083f1  mov     dword ptr [rdi+4], 4B53444Bh
0x1800083f8  mov     dword ptr [rdi], 1
0x1800083fe  test    r15, r15
0x180008401  jz      short loc_180008407
0x180008403  or      dword ptr [rdi+8], 1
0x180008407  mov     rax, [rsp+98h+var_60]
0x18000840c  lea     rbx, [rdi+50h]
0x180008410  mov     [rdi+48h], eax
0x180008413  mov     r8, rcx; Size
0x180008416  mov     rax, [rsp+98h+var_58]
0x18000841b  mov     rcx, rbx; void *
0x18000841e  mov     [rdi+4Ch], eax
0x180008421  movups  xmm0, xmmword ptr [r14+0Ch]
0x180008426  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000842b  mov     rdx, [r14+28h]; Src
0x18000842f  call    memcpy_0
0x180008434  add     rbx, [rsp+98h+Size]
0x180008439  mov     r8d, dword ptr [rsp+98h+arg_10]; Size
0x180008441  mov     rcx, rbx; void *
0x180008444  mov     rdx, [r14+30h]; Src
0x180008448  call    memcpy_0
0x18000844d  mov     edx, dword ptr [rsp+98h+arg_10]
0x180008454  mov     r8, [rsp+98h+var_70]; Size
0x180008459  add     rbx, rdx
0x18000845c  mov     rdx, [r14+40h]; Src
0x180008460  mov     rcx, rbx; void *
0x180008463  call    memcpy_0
0x180008468  add     rbx, [rsp+98h+var_70]
0x18000846d  mov     r8, [rsp+98h+arg_38]; Size
0x180008475  mov     rcx, rbx; void *
0x180008478  mov     rdx, [r14+48h]; Src
0x18000847c  call    memcpy_0
0x180008481  add     rbx, [rsp+98h+arg_38]
0x180008489  mov     r8, [rsp+98h+var_60]; Size
0x18000848e  mov     rcx, rbx; void *
0x180008491  mov     rdx, [rsp+98h+Src]; Src
0x180008499  call    memcpy_0
0x18000849e  add     rbx, [rsp+98h+var_60]
0x1800084a3  mov     r8, [rsp+98h+var_58]; Size
0x1800084a8  mov     rcx, rbx; void *
0x1800084ab  mov     rdx, [rsp+98h+arg_8]; Src
0x1800084b3  call    memcpy_0
0x1800084b8  add     rbx, [rsp+98h+var_58]
0x1800084bd  test    rbp, rbp
0x1800084c0  jz      short loc_1800084D8
0x1800084c2  mov     rdx, [rsp+98h+arg_18]; Src
0x1800084ca  mov     r8, rbp; Size
0x1800084cd  mov     rcx, rbx; void *
0x1800084d0  call    memcpy_0
0x1800084d5  add     rbx, rbp
0x1800084d8  test    rsi, rsi
0x1800084db  jz      short loc_1800084F8
0x1800084dd  mov     r8, rsi; Size
0x1800084e0  mov     rcx, rbx; void *
0x1800084e3  mov     rdx, r15
0x1800084e6  test    r15, r15
0x1800084e9  jnz     short loc_1800084F3
0x1800084eb  mov     rdx, [rsp+98h+arg_28]; Src
0x1800084f3  call    memcpy_0
0x1800084f8  mov     rax, [rsp+98h+arg_48]
0x180008500  mov     [rax], rdi
0x180008503  mov     rax, [rsp+98h+arg_50]
0x18000850b  mov     [rax], r13d
0x18000850e  mov     eax, r12d
0x180008511  add     rsp, 58h
0x180008515  pop     r15
0x180008517  pop     r14
0x180008519  pop     r13
0x18000851b  pop     r12
0x18000851d  pop     rdi
0x18000851e  pop     rsi
0x18000851f  pop     rbp
0x180008520  pop     rbx
0x180008521  retn
```
