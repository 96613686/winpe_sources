# PerflibciQueryV2Provider(ulong,ushort const *,EXT_OBJ_LIST *,ulong,uchar * *,ulong *,ulong *)

- ea: `0x18000c6f0`
- end: `0x18000cdcb`
- name: `?PerflibciQueryV2Provider@@YAKKPEBGPEAUEXT_OBJ_LIST@@KPEAPEAEPEAK3@Z`
- size: `1755`
- prototype: `unsigned int(unsigned int, const unsigned __int16 *, struct EXT_OBJ_LIST *, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000c614`
- `0x18000d240`

## callees

- `0x1800011c4`
- `0x180001cc0`
- `0x180002e40`
- `0x180002ef8`
- `0x180003644`
- `0x1800045d0`
- `0x180006ad4`
- `0x180006fe0`
- `0x180007020`
- `0x18000a560`
- `0x18000c2bc`
- `0x18000c6f0`
- `0x18003fb18`
- `0x18004165c`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000ca09`
- `KERNEL32!LocalFree` at `0x18000cabf`
- `KERNEL32!LocalFree` at `0x18000cbb8`
- `KERNEL32!LocalFree` at `0x18000cbc7`
- `KERNEL32!LocalFree` at `0x18000cc7f`
- `KERNEL32!LocalFree` at `0x18000cd8b`
- `KERNEL32!LocalFree` at `0x18000ca09`
- `KERNEL32!LocalFree` at `0x18000cabf`
- `KERNEL32!LocalFree` at `0x18000cbb8`
- `KERNEL32!LocalFree` at `0x18000cbc7`
- `KERNEL32!LocalFree` at `0x18000cc7f`
- `KERNEL32!LocalFree` at `0x18000cd8b`
- `KERNEL32!CompareStringOrdinal` at `0x18000c825`
- `KERNEL32!CompareStringOrdinal` at `0x18000c825`

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
0x18000c6f0  mov     rax, rsp
0x18000c6f3  push    r15
0x18000c6f5  sub     rsp, 60h
0x18000c6f9  mov     [rax+8], rbx
0x18000c6fd  mov     r15d, 57h ; 'W'
0x18000c703  mov     [rax+10h], rbp
0x18000c707  mov     ebx, r9d
0x18000c70a  mov     [rax+18h], rsi
0x18000c70e  mov     ebp, ecx
0x18000c710  mov     [rax-10h], rdi
0x18000c714  mov     rsi, r8
0x18000c717  mov     [rax-18h], r12
0x18000c71b  xor     edi, edi
0x18000c71d  mov     [rax-28h], r14
0x18000c721  mov     r14, rdx
0x18000c724  mov     [rax-38h], edi
0x18000c727  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c72e  test    byte ptr [rcx+1Ch], 8
0x18000c732  jnz     loc_18000CCAA
0x18000c738  mov     r12, [rsp+68h+arg_20]
0x18000c740  test    r12, r12
0x18000c743  jz      loc_18000C967
0x18000c749  mov     rax, [rsp+68h+arg_28]
0x18000c751  test    rax, rax
0x18000c754  jz      loc_18000C967
0x18000c75a  mov     rdx, [rsp+68h+arg_30]
0x18000c762  test    rdx, rdx
0x18000c765  jz      loc_18000C967
0x18000c76b  mov     [rax], edi
0x18000c76d  mov     [rdx], edi
0x18000c76f  mov     [r12], rdi
0x18000c773  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x18000c778  mov     r15d, eax
0x18000c77b  test    eax, eax
0x18000c77d  jnz     loc_18000C960
0x18000c783  test    rsi, rsi
0x18000c786  jz      short loc_18000C790
0x18000c788  test    ebx, ebx
0x18000c78a  jz      loc_18000CBE0
0x18000c790  mov     rdx, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18000c797  test    rdx, rdx
0x18000c79a  jz      loc_18000C960
0x18000c7a0  mov     r8, [rdx+20h]
0x18000c7a4  test    r8, r8
0x18000c7a7  jz      short loc_18000C7CA
0x18000c7a9  test    rsi, rsi
0x18000c7ac  jz      short loc_18000C7D0
0x18000c7ae  mov     eax, edi
0x18000c7b0  cmp     eax, ebx
0x18000c7b2  jnb     short loc_18000C7CA
0x18000c7b4  mov     ecx, eax
0x18000c7b6  test    byte ptr [rsi+rcx*8+4], 1
0x18000c7bb  jnz     short loc_18000C7C6
0x18000c7bd  mov     ecx, [rsi+rcx*8]
0x18000c7c0  cmp     [r8+5Ch], ecx
0x18000c7c4  jz      short loc_18000C7D0
0x18000c7c6  inc     eax
0x18000c7c8  jmp     short loc_18000C7B0
0x18000c7ca  mov     rdx, [rdx+18h]
0x18000c7ce  jmp     short loc_18000C797
0x18000c7d0  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18000c7d7  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x18000c7dc  mov     [rsp+68h+var_34], eax
0x18000c7e0  mov     r15d, eax
0x18000c7e3  test    eax, eax
0x18000c7e5  jnz     loc_18000C960
0x18000c7eb  mov     [rsp+68h+var_20], r13
0x18000c7f0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c7f7  mov     r13, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x18000c7fe  test    r13, r13
0x18000c801  jz      loc_18000C9AA
0x18000c807  cmp     [r13+18h], ebp
0x18000c80b  jnz     loc_18000C99D
0x18000c811  mov     r8, [r13+10h]; lpString2
0x18000c815  mov     r9d, eax; cchCount2
0x18000c818  mov     edx, eax; cchCount1
0x18000c81a  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18000c822  mov     rcx, r14; lpString1
0x18000c825  call    cs:__imp_CompareStringOrdinal
0x18000c82c  nop     dword ptr [rax+rax+00h]
0x18000c831  cmp     eax, 2
0x18000c834  jnz     loc_18000CCD8
0x18000c83a  mov     rdi, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18000c841  test    rdi, rdi
0x18000c844  jz      short loc_18000C8AB
0x18000c846  mov     r10d, 28h ; '('
0x18000c84c  nop     dword ptr [rax+00h]
0x18000c850  mov     rbp, [rdi+20h]
0x18000c854  test    rbp, rbp
0x18000c857  jz      short loc_18000C891
0x18000c859  test    rsi, rsi
0x18000c85c  jz      loc_18000C90C
0x18000c862  xor     r9b, r9b
0x18000c865  xor     ecx, ecx
0x18000c867  test    ebx, ebx
0x18000c869  jz      short loc_18000C891
0x18000c86b  nop     dword ptr [rax+rax+00h]
0x18000c870  mov     r8d, [rsi+rcx*8+4]
0x18000c875  lea     rdx, [rsi+rcx*8]
0x18000c879  test    r8b, 1
0x18000c87d  jnz     short loc_18000C886
0x18000c87f  mov     eax, [rdx]
0x18000c881  cmp     [rbp+5Ch], eax
0x18000c884  jz      short loc_18000C8FC
0x18000c886  inc     ecx
0x18000c888  cmp     ecx, ebx
0x18000c88a  jb      short loc_18000C870
0x18000c88c  test    r9b, r9b
0x18000c88f  jnz     short loc_18000C90C
0x18000c891  mov     rdi, [rdi+18h]
0x18000c895  test    rdi, rdi
0x18000c898  jnz     short loc_18000C850
0x18000c89a  test    r15d, r15d
0x18000c89d  jnz     loc_18000C94F
0x18000c8a3  mov     r12, [rsp+68h+arg_20]
0x18000c8ab  cmp     dword ptr [r13+30h], 0
0x18000c8b0  jnz     loc_18000CBEB
0x18000c8b6  mov     r8d, [r13+60h]
0x18000c8ba  lea     r9, [rsp+68h+var_38]
0x18000c8bf  mov     rdx, [r13+58h]
0x18000c8c3  mov     rcx, [r13+0]; struct _PERF_QUERY *
0x18000c8c7  call    PerflibciLocalQueryCounterData
0x18000c8cc  mov     r15d, eax
0x18000c8cf  cmp     eax, 8
0x18000c8d2  jz      loc_18000CC6D
0x18000c8d8  test    eax, eax
0x18000c8da  jnz     short loc_18000C94F
0x18000c8dc  mov     r9, [rsp+68h+arg_30]
0x18000c8e4  mov     rdx, r12
0x18000c8e7  mov     r8, [rsp+68h+arg_28]
0x18000c8ef  mov     rcx, r13
0x18000c8f2  call    PerflibciBuildPerfObjectType
0x18000c8f7  mov     r15d, eax
0x18000c8fa  jmp     short loc_18000C94F
0x18000c8fc  or      r8d, 1
0x18000c900  mov     r9b, 1
0x18000c903  mov     [rdx+4], r8d
0x18000c907  jmp     loc_18000C886
0x18000c90c  mov     r9d, [r13+20h]
0x18000c910  xor     r8d, r8d
0x18000c913  cmp     r8d, r9d
0x18000c916  jnb     loc_18000C9BB
0x18000c91c  mov     rcx, [r13+28h]
0x18000c920  mov     eax, [rbp+5Ch]
0x18000c923  cmp     [rcx+r8*4], eax
0x18000c927  jz      loc_18000C891
0x18000c92d  inc     r8d
0x18000c930  jmp     short loc_18000C913
0x18000c932  lea     rdi, ds:2[rax*2]
0x18000c93a  mov     rax, rdi
0x18000c93d  shr     rax, 20h
0x18000c941  test    eax, eax
0x18000c943  jz      loc_18000CB6B
0x18000c949  mov     r15d, 0Eh
0x18000c94f  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18000c956  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x18000c95b  mov     r13, [rsp+68h+var_20]
0x18000c960  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c967  test    byte ptr [rcx+1Ch], 8
0x18000c96b  mov     r14, [rsp+68h+var_28]
0x18000c970  mov     r12, [rsp+68h+var_18]
0x18000c975  mov     rdi, [rsp+68h+var_10]
0x18000c97a  mov     rsi, [rsp+68h+arg_10]
0x18000c982  mov     rbp, [rsp+68h+arg_8]
0x18000c987  mov     rbx, [rsp+68h+arg_0]
0x18000c98c  jnz     loc_18000CDA4
0x18000c992  mov     eax, r15d
0x18000c995  add     rsp, 60h
0x18000c999  pop     r15
0x18000c99b  retn
0x18000c99d  mov     r13, [r13+8]
0x18000c9a1  test    r13, r13
0x18000c9a4  jnz     loc_18000C807
0x18000c9aa  cmp     [r14+rax*2+2], di
0x18000c9b0  lea     rax, [rax+1]
0x18000c9b4  jnz     short loc_18000C9AA
0x18000c9b6  jmp     loc_18000C932
0x18000c9bb  mov     eax, [r13+1Ch]
0x18000c9bf  cmp     r9d, eax
0x18000c9c2  jb      short loc_18000CA24
0x18000c9c4  cmp     eax, 3FFFFFBFh
0x18000c9c9  ja      short loc_18000CA24
0x18000c9cb  lea     ecx, [rax+40h]
0x18000c9ce  mov     eax, 4
0x18000c9d3  mul     rcx
0x18000c9d6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c9dd  cmovb   rax, rcx
0x18000c9e1  mov     rcx, rax
0x18000c9e4  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000c9e9  mov     r14, rax
0x18000c9ec  test    rax, rax
0x18000c9ef  jz      short loc_18000CA1E
0x18000c9f1  mov     r8d, [r13+20h]
0x18000c9f5  mov     rcx, rax; void *
0x18000c9f8  mov     rdx, [r13+28h]; Src
0x18000c9fc  shl     r8, 2; Size
0x18000ca00  call    memcpy_0
0x18000ca05  mov     rcx, [r13+28h]; hMem
0x18000ca09  call    cs:__imp_LocalFree
0x18000ca10  nop     dword ptr [rax+rax+00h]
0x18000ca15  add     dword ptr [r13+1Ch], 40h ; '@'
0x18000ca1a  mov     [r13+28h], r14
0x18000ca1e  mov     r10d, 28h ; '('
0x18000ca24  mov     eax, [r13+20h]
0x18000ca28  cmp     eax, [r13+1Ch]
0x18000ca2c  jnb     loc_18000C891
0x18000ca32  mov     rcx, [r13+28h]
0x18000ca36  mov     edx, eax
0x18000ca38  mov     eax, [rbp+5Ch]
0x18000ca3b  mov     [rcx+rdx*4], eax
0x18000ca3e  inc     dword ptr [r13+20h]
0x18000ca42  cmp     dword ptr [r13+30h], 0
0x18000ca47  jnz     short loc_18000CA59
0x18000ca49  mov     dword ptr [r13+30h], 1
0x18000ca51  mov     dword ptr [r13+44h], 0
0x18000ca59  test    byte ptr [rbp+58h], 2
0x18000ca5d  mov     r12d, 30h ; '0'
0x18000ca63  mov     ecx, [r13+44h]
0x18000ca67  mov     edx, [r13+40h]
0x18000ca6b  cmovz   r12d, r10d
0x18000ca6f  add     ecx, r12d
0x18000ca72  cmp     ecx, edx
0x18000ca74  jb      short loc_18000CAE2
0x18000ca76  lea     eax, [rdx+2000h]
0x18000ca7c  mov     ecx, eax; unsigned __int64
0x18000ca7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ca85  mov     r15d, eax
0x18000ca88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ca8d  mov     r14, rax
0x18000ca90  test    rax, rax
0x18000ca93  jz      loc_18000CD2D
0x18000ca99  mov     r8d, r15d; Size
0x18000ca9c  xor     edx, edx; Val
0x18000ca9e  mov     rcx, rax; void *
0x18000caa1  call    memset_0
0x18000caa6  mov     rdx, [r13+38h]; Src
0x18000caaa  test    rdx, rdx
0x18000caad  jz      short loc_18000CACB
0x18000caaf  mov     r8d, [r13+44h]; Size
0x18000cab3  mov     rcx, r14; void *
0x18000cab6  call    memcpy_0
0x18000cabb  mov     rcx, [r13+38h]; hMem
0x18000cabf  call    cs:__imp_LocalFree
0x18000cac6  nop     dword ptr [rax+rax+00h]
0x18000cacb  add     dword ptr [r13+40h], 2000h
0x18000cad3  mov     r10d, 28h ; '('
0x18000cad9  mov     r15d, [rsp+68h+var_34]
0x18000cade  mov     [r13+38h], r14
0x18000cae2  test    r15d, r15d
0x18000cae5  jnz     loc_18000C891
0x18000caeb  mov     ecx, [r13+44h]
0x18000caef  mov     r9, [r13+38h]
0x18000caf3  add     r9, rcx
0x18000caf6  mov     [r9+10h], r15d
0x18000cafa  mov     [r9+14h], r12d
0x18000cafe  movups  xmm0, xmmword ptr [rbp+18h]
0x18000cb02  mov     qword ptr [r9+18h], 0FFFFFFFFFFFFFFFFh
0x18000cb0a  movups  xmmword ptr [r9], xmm0
0x18000cb0e  test    byte ptr [rbp+58h], 2
0x18000cb12  jz      short loc_18000CB62
0x18000cb14  mov     r8d, r12d
0x18000cb17  sub     r8, 28h ; '('
0x18000cb1b  shr     r8, 1
0x18000cb1e  jz      short loc_18000CB62
0x18000cb20  mov     ecx, 7FFFFFFEh
0x18000cb25  lea     rdx, asc_1800884A8; "*"
0x18000cb2c  add     r9, 28h ; '('
0x18000cb30  test    rcx, rcx
0x18000cb33  jz      short loc_18000CB52
0x18000cb35  movzx   eax, word ptr [rdx]
0x18000cb38  test    ax, ax
0x18000cb3b  jz      short loc_18000CB52
0x18000cb3d  mov     [r9], ax
0x18000cb41  add     rdx, 2
0x18000cb45  add     r9, 2
0x18000cb49  dec     rcx
0x18000cb4c  sub     r8, 1
0x18000cb50  jnz     short loc_18000CB30
0x18000cb52  test    r8, r8
0x18000cb55  lea     rcx, [r9-2]
0x18000cb59  cmovnz  rcx, r9
0x18000cb5d  xor     eax, eax
0x18000cb5f  mov     [rcx], ax
0x18000cb62  add     [r13+44h], r12d
0x18000cb66  jmp     loc_18000C891
0x18000cb6b  lea     eax, [rdi+68h]
0x18000cb6e  cmp     eax, 68h ; 'h'
0x18000cb71  jbe     short loc_18000CB7D
0x18000cb73  mov     ecx, eax
0x18000cb75  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000cb7a  mov     r13, rax
0x18000cb7d  test    r13, r13
0x18000cb80  jz      loc_18000C949
0x18000cb86  mov     ecx, 100h
0x18000cb8b  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000cb90  mov     [r13+28h], rax
0x18000cb94  test    rax, rax
0x18000cb97  jz      short loc_18000CBD8
0x18000cb99  mov     r8, r13
0x18000cb9c  mov     dl, 1
  ... truncated ...
```
