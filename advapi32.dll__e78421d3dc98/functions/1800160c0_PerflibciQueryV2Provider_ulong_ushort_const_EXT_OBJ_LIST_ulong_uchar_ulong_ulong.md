# PerflibciQueryV2Provider(ulong,ushort const *,EXT_OBJ_LIST *,ulong,uchar * *,ulong *,ulong *)

- ea: `0x1800160c0`
- end: `0x180016767`
- name: `?PerflibciQueryV2Provider@@YAKKPEBGPEAUEXT_OBJ_LIST@@KPEAPEAEPEAK3@Z`
- size: `1703`
- prototype: `unsigned int(unsigned int, const unsigned __int16 *, struct EXT_OBJ_LIST *, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180014430`
- `0x180015ff0`

## callees

- `0x180001910`
- `0x180003730`
- `0x180003764`
- `0x1800040f8`
- `0x180006488`
- `0x180006930`
- `0x18000957c`
- `0x1800160c0`
- `0x180016770`
- `0x180017100`
- `0x18002aa38`
- `0x18002c0d4`
- `0x18003b57c`
- `0x18003d048`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800163c9`
- `KERNEL32!LocalFree` at `0x180016479`
- `KERNEL32!LocalFree` at `0x18001656c`
- `KERNEL32!LocalFree` at `0x180016575`
- `KERNEL32!LocalFree` at `0x180016627`
- `KERNEL32!LocalFree` at `0x18001672d`
- `KERNEL32!LocalFree` at `0x1800163c9`
- `KERNEL32!LocalFree` at `0x180016479`
- `KERNEL32!LocalFree` at `0x18001656c`
- `KERNEL32!LocalFree` at `0x180016575`
- `KERNEL32!LocalFree` at `0x180016627`
- `KERNEL32!LocalFree` at `0x18001672d`
- `KERNEL32!CompareStringOrdinal` at `0x1800161f5`
- `KERNEL32!CompareStringOrdinal` at `0x1800161f5`

## pseudocode

```c
__int64 __fastcall PerflibciQueryV2Provider(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct EXT_OBJ_LIST *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned int *a7)
{
  DWORD v7; // r15d
  _QWORD *v12; // rcx
  unsigned __int8 **v13; // r12
  _QWORD *i; // rdx
  __int64 v15; // r8
  unsigned int j; // eax
  __int64 v17; // rax
  _QWORD *v18; // r13
  _QWORD *v19; // rdi
  __int64 v20; // rbp
  char v21; // r9
  __int64 v22; // rcx
  int v23; // r8d
  _DWORD *v24; // rdx
  DWORD v25; // eax
  unsigned int v26; // r9d
  __int64 k; // r8
  unsigned int v28; // edi
  unsigned int v31; // eax
  void *v32; // rax
  void *v33; // r14
  unsigned int v34; // eax
  unsigned int v35; // r12d
  unsigned int v36; // edx
  unsigned __int64 v37; // r15
  void *v38; // rax
  void *v39; // r14
  const void *v40; // rdx
  __int64 v41; // r9
  __int128 v42; // xmm0
  unsigned __int64 v43; // r8
  __int64 v44; // rcx
  const WCHAR *v45; // rdx
  _WORD *v46; // r9
  _WORD *v47; // rcx
  __int64 v48; // rax
  void *v49; // rcx
  __int64 v50; // rax
  void *v51; // rdi
  unsigned int v52; // ebx
  __int64 v53; // rax
  __int64 v54; // rcx
  int v55; // [rsp+30h] [rbp-38h] BYREF
  unsigned int Handle; // [rsp+34h] [rbp-34h]

  v7 = 87;
  v55 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids, a1);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = a5;
  if ( !a5 || !a6 || !a7 )
    goto LABEL_46;
  *a6 = 0;
  *a7 = 0;
  *a5 = 0;
  v7 = PerflibciEnsureCounterSetList();
  if ( v7 )
    goto LABEL_45;
  if ( a3 && !a4 )
  {
    v7 = 87;
    goto LABEL_45;
  }
  for ( i = g_ObjectList; ; i = (_QWORD *)i[3] )
  {
    if ( !i )
      goto LABEL_45;
    v15 = i[4];
    if ( !v15 )
      continue;
    if ( !a3 )
      break;
    for ( j = 0; j < a4; ++j )
    {
      if ( (*((_BYTE *)a3 + 8 * j + 4) & 1) == 0 && *(_DWORD *)(v15 + 92) == *((_DWORD *)a3 + 2 * j) )
        goto LABEL_18;
    }
  }
LABEL_18:
  Handle = PerflibciLocalWaitForMutex(g_hGlobalMutex);
  v7 = Handle;
  if ( Handle )
    goto LABEL_45;
  v17 = -1;
  v18 = g_QueryList;
  if ( g_QueryList )
  {
    do
    {
      if ( *((_DWORD *)v18 + 6) == a1 )
      {
        if ( CompareStringOrdinal(a2, -1, (LPCWCH)v18[2], -1, 1) == 2 )
          goto LABEL_22;
        v17 = -1;
      }
      v18 = (_QWORD *)v18[1];
    }
    while ( v18 );
  }
  while ( a2[++v17] != 0 )
    ;
  v28 = 2 * v17 + 2;
  if ( (unsigned __int64)(2 * v17 + 2) >> 32 )
    goto LABEL_43;
  if ( (unsigned int)(2 * v17 + 2) < 0xFFFFFF98 && 2 * (_DWORD)v17 != -2 )
    v18 = (_QWORD *)operator new((unsigned int)(2 * v17 + 106));
  if ( !v18 )
  {
LABEL_43:
    v7 = 14;
    goto LABEL_44;
  }
  v48 = operator new(256);
  v18[5] = v48;
  if ( !v48 )
  {
    v7 = 14;
    goto LABEL_81;
  }
  Handle = PerflibciOpenLocalQueryHandle(0, 1, v18);
  v7 = Handle;
  if ( Handle )
  {
LABEL_81:
    LocalFree((HLOCAL)v18[5]);
    LocalFree(v18);
    goto LABEL_44;
  }
  NtCurrentTeb()->EtwLocalData = (PVOID)1718773072;
  v18[1] = g_QueryList;
  *((_DWORD *)v18 + 7) = 64;
  *((_DWORD *)v18 + 6) = a1;
  v18[2] = v18 + 13;
  StringCbCopyW((unsigned __int16 *)v18 + 52, v28, a2);
  g_QueryList = v18;
LABEL_22:
  v19 = g_ObjectList;
  if ( !g_ObjectList )
    goto LABEL_34;
  while ( 2 )
  {
    v20 = v19[4];
    if ( v20 )
    {
      if ( !a3 )
        goto LABEL_38;
      v21 = 0;
      v22 = 0;
      if ( a4 )
      {
        do
        {
          v23 = *((_DWORD *)a3 + 2 * v22 + 1);
          v24 = (_DWORD *)((char *)a3 + 8 * v22);
          if ( (v23 & 1) == 0 && *(_DWORD *)(v20 + 92) == *v24 )
          {
            v21 = 1;
            v24[1] = v23 | 1;
          }
          v22 = (unsigned int)(v22 + 1);
        }
        while ( (unsigned int)v22 < a4 );
        if ( v21 )
        {
LABEL_38:
          v26 = *((_DWORD *)v18 + 8);
          for ( k = 0; (unsigned int)k < v26; k = (unsigned int)(k + 1) )
          {
            if ( *(_DWORD *)(v18[5] + 4 * k) == *(_DWORD *)(v20 + 92) )
              goto LABEL_31;
          }
          v31 = *((_DWORD *)v18 + 7);
          if ( v26 >= v31 && v31 <= 0x3FFFFFBF )
          {
            v32 = (void *)operator new(saturated_mul(v31 + 64, 4u));
            v33 = v32;
            if ( v32 )
            {
              memcpy_0(v32, (const void *)v18[5], 4LL * *((unsigned int *)v18 + 8));
              LocalFree((HLOCAL)v18[5]);
              *((_DWORD *)v18 + 7) += 64;
              v18[5] = v33;
            }
          }
          v34 = *((_DWORD *)v18 + 8);
          if ( v34 < *((_DWORD *)v18 + 7) )
          {
            *(_DWORD *)(v18[5] + 4LL * v34) = *(_DWORD *)(v20 + 92);
            ++*((_DWORD *)v18 + 8);
            if ( !*((_DWORD *)v18 + 12) )
            {
              *((_DWORD *)v18 + 12) = 1;
              *((_DWORD *)v18 + 17) = 0;
            }
            v35 = 48;
            v36 = *((_DWORD *)v18 + 16);
            if ( (*(_BYTE *)(v20 + 88) & 2) == 0 )
              v35 = 40;
            if ( v35 + *((_DWORD *)v18 + 17) < v36 )
            {
LABEL_65:
              if ( !v7 )
              {
                v41 = *((unsigned int *)v18 + 17) + v18[7];
                *(_DWORD *)(v41 + 16) = 0;
                *(_DWORD *)(v41 + 20) = v35;
                v42 = *(_OWORD *)(v20 + 24);
                *(_QWORD *)(v41 + 24) = -1;
                *(_OWORD *)v41 = v42;
                if ( (*(_BYTE *)(v20 + 88) & 2) != 0 )
                {
                  v43 = ((unsigned __int64)v35 - 40) >> 1;
                  if ( v43 )
                  {
                    v44 = 2147483646;
                    v45 = L"*";
                    v46 = (_WORD *)(v41 + 40);
                    do
                    {
                      if ( !v44 )
                        break;
                      if ( !*v45 )
                        break;
                      *v46++ = *v45++;
                      --v44;
                      --v43;
                    }
                    while ( v43 );
                    v47 = v46 - 1;
                    if ( v43 )
                      v47 = v46;
                    *v47 = 0;
                  }
                }
                *((_DWORD *)v18 + 17) += v35;
              }
            }
            else
            {
              v37 = v36 + 0x2000;
              v38 = operator new(v37, (const struct std::nothrow_t *)&std::nothrow);
              v39 = v38;
              if ( v38 )
              {
                memset_0(v38, 0, (unsigned int)v37);
                v40 = (const void *)v18[7];
                if ( v40 )
                {
                  memcpy_0(v39, v40, *((unsigned int *)v18 + 17));
                  LocalFree((HLOCAL)v18[7]);
                }
                *((_DWORD *)v18 + 16) += 0x2000;
                v7 = Handle;
                v18[7] = v39;
                goto LABEL_65;
              }
              v7 = 14;
              Handle = 14;
            }
          }
        }
      }
    }
LABEL_31:
    v19 = (_QWORD *)v19[3];
    if ( v19 )
      continue;
    break;
  }
  if ( v7 )
    goto LABEL_44;
  v13 = a5;
LABEL_34:
  if ( !*((_DWORD *)v18 + 12) )
    goto LABEL_35;
  v7 = PerflibciLocalValidateCounters((struct _PERF_QUERY *)*v18);
  if ( v7 )
  {
    *((_DWORD *)v18 + 17) = 0;
    *((_DWORD *)v18 + 12) = 0;
    goto LABEL_44;
  }
  v7 = PerflibciLocalQueryCounterInfo(*v18, v18[7], *((unsigned int *)v18 + 16), &v55);
  if ( v7 == 8 )
  {
    while ( 1 )
    {
      v51 = (void *)v18[7];
      v52 = (v55 + 7) & 0xFFFFFFF8;
      v53 = operator new(v52);
      v18[7] = v53;
      if ( !v53 )
        break;
      v54 = *v18;
      *((_DWORD *)v18 + 16) = v52;
      v7 = PerflibciLocalQueryCounterInfo(v54, v53, v52, &v55);
      if ( v7 != 8 )
        goto LABEL_86;
    }
    LocalFree(v51);
    v18[8] = 0;
    goto LABEL_43;
  }
LABEL_86:
  if ( !v7 )
  {
    *((_DWORD *)v18 + 17) = v55;
    v7 = PerflibciBuildDefinitionBlock(v18);
    if ( !v7 )
    {
      *((_DWORD *)v18 + 12) = 0;
LABEL_35:
      while ( 1 )
      {
        v25 = PerflibciLocalQueryCounterData((struct _PERF_QUERY *)*v18, v18[11], *((_DWORD *)v18 + 24), &v55);
        v7 = v25;
        if ( v25 != 8 )
          break;
        v49 = (void *)v18[11];
        *((_DWORD *)v18 + 24) = (v55 + 7) & 0xFFFFFFF8;
        LocalFree(v49);
        v50 = operator new(*((unsigned int *)v18 + 24));
        v18[11] = v50;
        if ( !v50 )
        {
          *((_DWORD *)v18 + 24) = 0;
          goto LABEL_43;
        }
      }
      if ( !v25 )
        v7 = PerflibciBuildPerfObjectType(v18, v13, a6, a7);
    }
  }
LABEL_44:
  PerflibciLocalReleaseMutex(g_hGlobalMutex);
LABEL_45:
  v12 = WPP_GLOBAL_Control;
LABEL_46:
  if ( (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_d(v12[2], 13, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800160c0  mov     rax, rsp
0x1800160c3  push    r15
0x1800160c5  sub     rsp, 60h
0x1800160c9  mov     [rax+8], rbx
0x1800160cd  mov     r15d, 57h ; 'W'
0x1800160d3  mov     [rax+10h], rbp
0x1800160d7  mov     ebx, r9d
0x1800160da  mov     [rax+18h], rsi
0x1800160de  mov     ebp, ecx
0x1800160e0  mov     [rax-10h], rdi
0x1800160e4  mov     rsi, r8
0x1800160e7  mov     [rax-18h], r12
0x1800160eb  xor     edi, edi
0x1800160ed  mov     [rax-28h], r14
0x1800160f1  mov     r14, rdx
0x1800160f4  mov     [rax-38h], edi
0x1800160f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160fe  test    byte ptr [rcx+1Ch], 8
0x180016102  jnz     loc_18001664C
0x180016108  mov     r12, [rsp+68h+arg_20]
0x180016110  test    r12, r12
0x180016113  jz      loc_180016328
0x180016119  mov     rax, [rsp+68h+arg_28]
0x180016121  test    rax, rax
0x180016124  jz      loc_180016328
0x18001612a  mov     rdx, [rsp+68h+arg_30]
0x180016132  test    rdx, rdx
0x180016135  jz      loc_180016328
0x18001613b  mov     [rax], edi
0x18001613d  mov     [rdx], edi
0x18001613f  mov     [r12], rdi
0x180016143  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180016148  mov     r15d, eax
0x18001614b  test    eax, eax
0x18001614d  jnz     loc_180016321
0x180016153  test    rsi, rsi
0x180016156  jz      short loc_180016160
0x180016158  test    ebx, ebx
0x18001615a  jz      loc_180016588
0x180016160  mov     rdx, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180016167  test    rdx, rdx
0x18001616a  jz      loc_180016321
0x180016170  mov     r8, [rdx+20h]
0x180016174  test    r8, r8
0x180016177  jz      short loc_18001619A
0x180016179  test    rsi, rsi
0x18001617c  jz      short loc_1800161A0
0x18001617e  mov     eax, edi
0x180016180  cmp     eax, ebx
0x180016182  jnb     short loc_18001619A
0x180016184  mov     ecx, eax
0x180016186  test    byte ptr [rsi+rcx*8+4], 1
0x18001618b  jnz     short loc_180016196
0x18001618d  mov     ecx, [rsi+rcx*8]
0x180016190  cmp     [r8+5Ch], ecx
0x180016194  jz      short loc_1800161A0
0x180016196  inc     eax
0x180016198  jmp     short loc_180016180
0x18001619a  mov     rdx, [rdx+18h]
0x18001619e  jmp     short loc_180016167
0x1800161a0  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x1800161a7  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x1800161ac  mov     [rsp+68h+var_34], eax
0x1800161b0  mov     r15d, eax
0x1800161b3  test    eax, eax
0x1800161b5  jnz     loc_180016321
0x1800161bb  mov     [rsp+68h+var_20], r13
0x1800161c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800161c7  mov     r13, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x1800161ce  test    r13, r13
0x1800161d1  jz      loc_18001636A
0x1800161d7  cmp     [r13+18h], ebp
0x1800161db  jnz     loc_18001635D
0x1800161e1  mov     r8, [r13+10h]; lpString2
0x1800161e5  mov     r9d, eax; cchCount2
0x1800161e8  mov     edx, eax; cchCount1
0x1800161ea  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800161f2  mov     rcx, r14; lpString1
0x1800161f5  call    cs:__imp_CompareStringOrdinal
0x1800161fb  cmp     eax, 2
0x1800161fe  jnz     loc_18001667A
0x180016204  mov     rdi, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18001620b  test    rdi, rdi
0x18001620e  jz      short loc_18001626C
0x180016210  mov     r10d, 28h ; '('
0x180016216  mov     rbp, [rdi+20h]
0x18001621a  test    rbp, rbp
0x18001621d  jz      short loc_180016252
0x18001621f  test    rsi, rsi
0x180016222  jz      loc_1800162CD
0x180016228  xor     r9b, r9b
0x18001622b  xor     ecx, ecx
0x18001622d  test    ebx, ebx
0x18001622f  jz      short loc_180016252
0x180016231  mov     r8d, [rsi+rcx*8+4]
0x180016236  lea     rdx, [rsi+rcx*8]
0x18001623a  test    r8b, 1
0x18001623e  jnz     short loc_180016247
0x180016240  mov     eax, [rdx]
0x180016242  cmp     [rbp+5Ch], eax
0x180016245  jz      short loc_1800162BD
0x180016247  inc     ecx
0x180016249  cmp     ecx, ebx
0x18001624b  jb      short loc_180016231
0x18001624d  test    r9b, r9b
0x180016250  jnz     short loc_1800162CD
0x180016252  mov     rdi, [rdi+18h]
0x180016256  test    rdi, rdi
0x180016259  jnz     short loc_180016216
0x18001625b  test    r15d, r15d
0x18001625e  jnz     loc_180016310
0x180016264  mov     r12, [rsp+68h+arg_20]
0x18001626c  cmp     dword ptr [r13+30h], 0
0x180016271  jnz     loc_180016593
0x180016277  mov     r8d, [r13+60h]
0x18001627b  lea     r9, [rsp+68h+var_38]
0x180016280  mov     rdx, [r13+58h]
0x180016284  mov     rcx, [r13+0]; struct _PERF_QUERY *
0x180016288  call    PerflibciLocalQueryCounterData
0x18001628d  mov     r15d, eax
0x180016290  cmp     eax, 8
0x180016293  jz      loc_180016615
0x180016299  test    eax, eax
0x18001629b  jnz     short loc_180016310
0x18001629d  mov     r9, [rsp+68h+arg_30]
0x1800162a5  mov     rdx, r12
0x1800162a8  mov     r8, [rsp+68h+arg_28]
0x1800162b0  mov     rcx, r13
0x1800162b3  call    PerflibciBuildPerfObjectType
0x1800162b8  mov     r15d, eax
0x1800162bb  jmp     short loc_180016310
0x1800162bd  or      r8d, 1
0x1800162c1  mov     r9b, 1
0x1800162c4  mov     [rdx+4], r8d
0x1800162c8  jmp     loc_180016247
0x1800162cd  mov     r9d, [r13+20h]
0x1800162d1  xor     r8d, r8d
0x1800162d4  cmp     r8d, r9d
0x1800162d7  jnb     loc_18001637B
0x1800162dd  mov     rcx, [r13+28h]
0x1800162e1  mov     eax, [rbp+5Ch]
0x1800162e4  cmp     [rcx+r8*4], eax
0x1800162e8  jz      loc_180016252
0x1800162ee  inc     r8d
0x1800162f1  jmp     short loc_1800162D4
0x1800162f3  lea     rdi, ds:2[rax*2]
0x1800162fb  mov     rax, rdi
0x1800162fe  shr     rax, 20h
0x180016302  test    eax, eax
0x180016304  jz      loc_18001651F
0x18001630a  mov     r15d, 0Eh
0x180016310  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180016317  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x18001631c  mov     r13, [rsp+68h+var_20]
0x180016321  mov     rcx, cs:WPP_GLOBAL_Control
0x180016328  test    byte ptr [rcx+1Ch], 8
0x18001632c  mov     r14, [rsp+68h+var_28]
0x180016331  mov     r12, [rsp+68h+var_18]
0x180016336  mov     rdi, [rsp+68h+var_10]
0x18001633b  mov     rsi, [rsp+68h+arg_10]
0x180016343  mov     rbp, [rsp+68h+arg_8]
0x180016348  mov     rbx, [rsp+68h+arg_0]
0x18001634d  jnz     loc_180016740
0x180016353  mov     eax, r15d
0x180016356  add     rsp, 60h
0x18001635a  pop     r15
0x18001635c  retn
0x18001635d  mov     r13, [r13+8]
0x180016361  test    r13, r13
0x180016364  jnz     loc_1800161D7
0x18001636a  cmp     [r14+rax*2+2], di
0x180016370  lea     rax, [rax+1]
0x180016374  jnz     short loc_18001636A
0x180016376  jmp     loc_1800162F3
0x18001637b  mov     eax, [r13+1Ch]
0x18001637f  cmp     r9d, eax
0x180016382  jb      short loc_1800163DE
0x180016384  cmp     eax, 3FFFFFBFh
0x180016389  ja      short loc_1800163DE
0x18001638b  lea     ecx, [rax+40h]
0x18001638e  mov     eax, 4
0x180016393  mul     rcx
0x180016396  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001639d  cmovb   rax, rcx
0x1800163a1  mov     rcx, rax
0x1800163a4  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800163a9  mov     r14, rax
0x1800163ac  test    rax, rax
0x1800163af  jz      short loc_1800163D8
0x1800163b1  mov     r8d, [r13+20h]
0x1800163b5  mov     rcx, rax; void *
0x1800163b8  mov     rdx, [r13+28h]; Src
0x1800163bc  shl     r8, 2; Size
0x1800163c0  call    memcpy_0
0x1800163c5  mov     rcx, [r13+28h]; hMem
0x1800163c9  call    cs:__imp_LocalFree
0x1800163cf  add     dword ptr [r13+1Ch], 40h ; '@'
0x1800163d4  mov     [r13+28h], r14
0x1800163d8  mov     r10d, 28h ; '('
0x1800163de  mov     eax, [r13+20h]
0x1800163e2  cmp     eax, [r13+1Ch]
0x1800163e6  jnb     loc_180016252
0x1800163ec  mov     rcx, [r13+28h]
0x1800163f0  mov     edx, eax
0x1800163f2  mov     eax, [rbp+5Ch]
0x1800163f5  mov     [rcx+rdx*4], eax
0x1800163f8  inc     dword ptr [r13+20h]
0x1800163fc  cmp     dword ptr [r13+30h], 0
0x180016401  jnz     short loc_180016413
0x180016403  mov     dword ptr [r13+30h], 1
0x18001640b  mov     dword ptr [r13+44h], 0
0x180016413  test    byte ptr [rbp+58h], 2
0x180016417  mov     r12d, 30h ; '0'
0x18001641d  mov     ecx, [r13+44h]
0x180016421  mov     edx, [r13+40h]
0x180016425  cmovz   r12d, r10d
0x180016429  add     ecx, r12d
0x18001642c  cmp     ecx, edx
0x18001642e  jb      short loc_180016496
0x180016430  lea     eax, [rdx+2000h]
0x180016436  mov     ecx, eax; unsigned __int64
0x180016438  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001643f  mov     r15d, eax
0x180016442  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016447  mov     r14, rax
0x18001644a  test    rax, rax
0x18001644d  jz      loc_1800166CF
0x180016453  mov     r8d, r15d; Size
0x180016456  xor     edx, edx; Val
0x180016458  mov     rcx, rax; void *
0x18001645b  call    memset_0
0x180016460  mov     rdx, [r13+38h]; Src
0x180016464  test    rdx, rdx
0x180016467  jz      short loc_18001647F
0x180016469  mov     r8d, [r13+44h]; Size
0x18001646d  mov     rcx, r14; void *
0x180016470  call    memcpy_0
0x180016475  mov     rcx, [r13+38h]; hMem
0x180016479  call    cs:__imp_LocalFree
0x18001647f  add     dword ptr [r13+40h], 2000h
0x180016487  mov     r10d, 28h ; '('
0x18001648d  mov     r15d, [rsp+68h+var_34]
0x180016492  mov     [r13+38h], r14
0x180016496  test    r15d, r15d
0x180016499  jnz     loc_180016252
0x18001649f  mov     ecx, [r13+44h]
0x1800164a3  mov     r9, [r13+38h]
0x1800164a7  add     r9, rcx
0x1800164aa  mov     [r9+10h], r15d
0x1800164ae  mov     [r9+14h], r12d
0x1800164b2  movups  xmm0, xmmword ptr [rbp+18h]
0x1800164b6  mov     qword ptr [r9+18h], 0FFFFFFFFFFFFFFFFh
0x1800164be  movups  xmmword ptr [r9], xmm0
0x1800164c2  test    byte ptr [rbp+58h], 2
0x1800164c6  jz      short loc_180016516
0x1800164c8  mov     r8d, r12d
0x1800164cb  sub     r8, 28h ; '('
0x1800164cf  shr     r8, 1
0x1800164d2  jz      short loc_180016516
0x1800164d4  mov     ecx, 7FFFFFFEh
0x1800164d9  lea     rdx, asc_18007AE24; "*"
0x1800164e0  add     r9, 28h ; '('
0x1800164e4  test    rcx, rcx
0x1800164e7  jz      short loc_180016506
0x1800164e9  movzx   eax, word ptr [rdx]
0x1800164ec  test    ax, ax
0x1800164ef  jz      short loc_180016506
0x1800164f1  mov     [r9], ax
0x1800164f5  add     rdx, 2
0x1800164f9  add     r9, 2
0x1800164fd  dec     rcx
0x180016500  sub     r8, 1
0x180016504  jnz     short loc_1800164E4
0x180016506  test    r8, r8
0x180016509  lea     rcx, [r9-2]
0x18001650d  cmovnz  rcx, r9
0x180016511  xor     eax, eax
0x180016513  mov     [rcx], ax
0x180016516  add     [r13+44h], r12d
0x18001651a  jmp     loc_180016252
0x18001651f  lea     eax, [rdi+68h]
0x180016522  cmp     eax, 68h ; 'h'
0x180016525  jbe     short loc_180016531
0x180016527  mov     ecx, eax
0x180016529  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18001652e  mov     r13, rax
0x180016531  test    r13, r13
0x180016534  jz      loc_18001630A
0x18001653a  mov     ecx, 100h
0x18001653f  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180016544  mov     [r13+28h], rax
0x180016548  test    rax, rax
0x18001654b  jz      short loc_180016580
0x18001654d  mov     r8, r13
0x180016550  mov     dl, 1
0x180016552  xor     ecx, ecx; unsigned __int16 *
0x180016554  call    PerflibciOpenLocalQueryHandle
0x180016559  mov     [rsp+68h+var_34], eax
0x18001655d  mov     r15d, eax
0x180016560  test    eax, eax
  ... truncated ...
```
