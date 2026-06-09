# PerflibciLocalEnumerateCounterSetInstances

- ea: `0x180004470`
- end: `0x18000497f`
- name: `PerflibciLocalEnumerateCounterSetInstances`
- size: `1295`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *Buf1, struct _PERF_INSTANCE_HEADER *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004310`

## callees

- `0x180003900`
- `0x180004470`
- `0x180005e40`
- `0x180006488`
- `0x180009684`
- `0x180017554`
- `0x18002a880`
- `0x18003d048`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800047a2`
- `msvcrt!wcsnlen` at `0x1800047a2`
- `KERNEL32!LocalFree` at `0x180004594`
- `KERNEL32!LocalFree` at `0x180004680`
- `KERNEL32!LocalFree` at `0x180004727`
- `KERNEL32!LocalFree` at `0x180004594`
- `KERNEL32!LocalFree` at `0x180004680`
- `KERNEL32!LocalFree` at `0x180004727`
- `KERNEL32!GetComputerNameW` at `0x180004579`
- `KERNEL32!GetComputerNameW` at `0x180004579`

## pseudocode

```c
DWORD __fastcall PerflibciLocalEnumerateCounterSetInstances(
        unsigned __int16 *a1,
        void *Buf1,
        struct _PERF_INSTANCE_HEADER *a3,
        unsigned int a4,
        unsigned int *a5)
{
  DWORD result; // eax
  int v10; // r14d
  __int64 CounterSet; // rax
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rax
  DWORD v15; // eax
  unsigned __int64 v16; // rbp
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  int v19; // edx
  bool v20; // zf
  unsigned int *v21; // rcx
  unsigned int v22; // edx
  unsigned int v23; // ebx
  unsigned int v24; // ebp
  unsigned int v25; // edx
  int v26; // eax
  int v27; // eax
  unsigned int *v28; // rdi
  __int64 v29; // r10
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned int v32; // ebp
  unsigned int v33; // r9d
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int16 *v36; // rax
  unsigned int v37; // edx
  unsigned int v38; // ecx
  unsigned int v39; // edx
  unsigned int v40; // r10d
  const WCHAR *v41; // r9
  __int64 v42; // rcx
  _WORD *v43; // rdx
  __int64 v44; // r8
  _WORD *v45; // rcx
  int v46; // [rsp+20h] [rbp-78h]
  unsigned int Src; // [rsp+40h] [rbp-58h]
  unsigned __int16 *Srca; // [rsp+40h] [rbp-58h]
  unsigned int v49; // [rsp+48h] [rbp-50h]
  DWORD nSize; // [rsp+4Ch] [rbp-4Ch] BYREF
  unsigned int v51; // [rsp+50h] [rbp-48h] BYREF
  int v52; // [rsp+54h] [rbp-44h]
  unsigned int v53; // [rsp+58h] [rbp-40h]
  unsigned int v54; // [rsp+5Ch] [rbp-3Ch]
  HLOCAL hMem; // [rsp+60h] [rbp-38h] BYREF
  int v56; // [rsp+68h] [rbp-30h]
  int v57; // [rsp+A8h] [rbp+10h]

  v57 = (int)Buf1;
  hMem = 0;
  nSize = 0;
  v51 = 0;
  result = PerflibciEnsureCounterSetList();
  v10 = result;
  if ( !result )
  {
    CounterSet = PerflibciCreateOrFindCounterSet(Buf1, 0, 0, 0, 0);
    v12 = CounterSet;
    if ( !CounterSet )
      return 4200;
    if ( *(_DWORD *)(*(_QWORD *)(CounterSet + 16) + 32LL) == 1 )
      return PerfpEnumerateKernelInstances((struct PERFLIBCI_COUNTERSET_NODE *)CounterSet, a3, a4, a5);
    *a5 = 0;
    if ( a4 )
    {
      if ( a3 )
      {
        LOBYTE(a3->Size) = 0;
        *((_BYTE *)a3 + a4 - 1) = 0;
      }
      else
      {
        v10 = 87;
      }
    }
    v13 = -1;
    if ( a1 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a1[v14] );
      v15 = v14 + 1;
    }
    else
    {
      v15 = 261;
    }
    nSize = v15;
    v16 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v16 = -1;
    v17 = (unsigned __int16 *)operator new(v16, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v10 = 14;
      goto LABEL_16;
    }
    memset_0(v17, 0, v16);
    if ( a1 && *a1 )
      StringCchCopyW(v18, nSize, a1);
    else
      GetComputerNameW(v18, &nSize);
    do
      v20 = v18[++v13] == 0;
    while ( !v20 );
    if ( v10 )
      goto LABEL_16;
    v51 = 0x2000;
    v10 = PerfpSendStateLessNotification(v57, v19, (_DWORD)v18, 2 * (int)v13 + 2, (__int64)&hMem, (__int64)&v51);
    if ( v10 )
      goto LABEL_16;
    v21 = (unsigned int *)hMem;
    v22 = 0;
    v23 = 0;
    Src = 0;
    v49 = 0;
    v24 = 8;
    while ( 1 )
    {
      v54 = v22;
      v53 = v24;
      if ( v22 >= *v21 || v24 >= v51 )
        break;
      v28 = (unsigned int *)((char *)v21 + v24);
      v29 = *v28;
      v56 = v29;
      if ( (unsigned int)v29 >= 0x20 && !v28[3] )
      {
        v30 = v28[6];
        if ( (*(_BYTE *)(v12 + 88) & 2) != 0 )
        {
          if ( v30 == -1 )
            goto LABEL_46;
          if ( v30 )
          {
            LODWORD(v31) = v29;
            if ( (unsigned __int64)(v29 - 8) > 0x20 )
            {
              v32 = Src;
              v33 = 32;
              v52 = 32;
              v34 = 32;
              do
              {
                v35 = *(unsigned int *)((char *)v28 + v34);
                Srca = (unsigned __int16 *)((char *)v28 + v34);
                if ( (unsigned int)v35 > (unsigned int)v31 - v33 || (unsigned int)v35 < 0x10 )
                  break;
                if ( (unsigned int)((unsigned __int64)(v35 - 8) >> 1) == wcsnlen(
                                                                           (const wchar_t *)((char *)v28 + v34 + 8),
                                                                           (unsigned int)((unsigned __int64)(v35 - 8) >> 1)) )
                {
                  v23 = v49;
                  break;
                }
                v23 = v49;
                v20 = PerflibciFindInstance(
                        (struct PERFLIBCI_COUNTERSET_NODE *)v12,
                        Srca + 4,
                        *((_DWORD *)Srca + 1),
                        v28[7],
                        v46) == 0;
                v36 = Srca;
                if ( !v20 )
                {
                  v23 = ++v49;
                  if ( (*(_BYTE *)(v12 + 88) & 2) != 0 )
                  {
                    if ( a3
                      && (v37 = *(_DWORD *)Srca, v38 = *(_DWORD *)Srca + v32, v32 <= v38)
                      && v37 <= v38
                      && v38 <= a4 )
                    {
                      memcpy_0((char *)a3 + v32, Srca, v37);
                      v36 = Srca;
                    }
                    else
                    {
                      v10 = 8;
                    }
                    v32 += *(_DWORD *)v36;
                  }
                }
                v33 = *(_DWORD *)v36 + v52;
                v31 = *v28;
                v34 = v33;
                v52 = v33;
              }
              while ( v33 < (unsigned __int64)(v31 - 8) );
              v22 = v54;
              LODWORD(v29) = v56;
              Src = v32;
              v24 = v53;
            }
            v21 = (unsigned int *)hMem;
          }
        }
        else if ( v30 == -1 )
        {
          v49 = ++v23;
        }
        else if ( v30 )
        {
LABEL_46:
          v10 = 4211;
          break;
        }
      }
      v24 += v29;
      ++v22;
    }
    if ( *(_DWORD *)(v12 + 88) != 6 || !v23 )
    {
      v25 = Src;
      goto LABEL_24;
    }
    ++v23;
    if ( a3 )
    {
      v39 = Src;
      v40 = Src + 24;
      if ( Src < Src + 24 && v40 >= 0x18 && v40 <= a4 )
      {
        *(struct _PERF_INSTANCE_HEADER *)((char *)a3 + Src) = (struct _PERF_INSTANCE_HEADER)24LL;
        v41 = L"_Total";
        v42 = 2147483646;
        v43 = (_WORD *)((char *)&a3[1] + Src);
        v44 = 7;
        do
        {
          if ( !v42 )
            break;
          if ( !*v41 )
            break;
          *v43++ = *v41++;
          --v42;
          --v44;
        }
        while ( v44 );
        v45 = v43 - 1;
        if ( v44 )
          v45 = v43;
        v25 = Src + 24;
        *v45 = 0;
        v21 = (unsigned int *)hMem;
LABEL_24:
        if ( (v10 & 0xFFFFFFF7) == 0 )
        {
          v26 = *(_DWORD *)(v12 + 88);
          if ( v26 == 6 )
          {
LABEL_26:
            v27 = v10;
            if ( !v23 )
              v27 = 4201;
            v10 = v27;
            *a5 = v25;
            goto LABEL_29;
          }
          if ( v26 )
          {
            if ( v26 == 2 )
              goto LABEL_26;
            if ( v26 != 4 && v26 != 12 )
            {
LABEL_44:
              v10 = 4211;
              LocalFree(v21);
              goto LABEL_16;
            }
          }
          else if ( v23 > 1 )
          {
            goto LABEL_44;
          }
          if ( v23 )
            *a5 = 0;
          else
            v10 = 4201;
        }
LABEL_29:
        LocalFree(v21);
LABEL_16:
        LocalFree(v18);
        return v10;
      }
    }
    else
    {
      v39 = Src;
    }
    v10 = 8;
    v25 = v39 + 24;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x180004470  mov     [rsp+arg_18], rbx
0x180004475  mov     [rsp+arg_8], rdx
0x18000447a  push    rsi
0x18000447b  push    rdi
0x18000447c  push    r12
0x18000447e  push    r13
0x180004480  push    r14
0x180004482  sub     rsp, 70h
0x180004486  xor     esi, esi
0x180004488  mov     r13d, r9d
0x18000448b  mov     [rsp+98h+hMem], rsi
0x180004490  mov     r12, r8
0x180004493  mov     [rsp+98h+nSize], esi
0x180004497  mov     rdi, rdx
0x18000449a  mov     [rsp+98h+var_48], esi
0x18000449e  mov     rbx, rcx
0x1800044a1  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x1800044a6  mov     r14d, eax
0x1800044a9  test    eax, eax
0x1800044ab  jnz     loc_1800045AD
0x1800044b1  mov     [rsp+98h+var_68], esi; int
0x1800044b5  xor     r9d, r9d
0x1800044b8  mov     [rsp+98h+var_70], si; __int16
0x1800044bd  xor     r8d, r8d
0x1800044c0  xor     edx, edx; Src
0x1800044c2  mov     [rsp+98h+var_78], rsi; void *
0x1800044c7  mov     rcx, rdi; Buf1
0x1800044ca  mov     [rsp+98h+arg_10], r15
0x1800044d2  call    PerflibciCreateOrFindCounterSet
0x1800044d7  mov     r15, rax
0x1800044da  test    rax, rax
0x1800044dd  jz      loc_18000490A
0x1800044e3  mov     rax, [rax+10h]
0x1800044e7  cmp     dword ptr [rax+20h], 1
0x1800044eb  jz      loc_1800045C2
0x1800044f1  mov     rax, [rsp+98h+arg_20]
0x1800044f9  mov     [rsp+98h+arg_0], rbp
0x180004501  mov     [rax], esi
0x180004503  test    r13d, r13d
0x180004506  jnz     loc_1800046A9
0x18000450c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180004513  test    rbx, rbx
0x180004516  jz      loc_180004914
0x18000451c  mov     rax, rdi
0x18000451f  nop
0x180004520  inc     rax
0x180004523  cmp     [rbx+rax*2], si
0x180004527  jnz     short loc_180004520
0x180004529  inc     eax
0x18000452b  mov     ecx, eax
0x18000452d  mov     [rsp+98h+nSize], eax
0x180004531  mov     eax, 2
0x180004536  mul     rcx
0x180004539  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004540  mov     rbp, rax
0x180004543  cmovb   rbp, rdi
0x180004547  mov     rcx, rbp; unsigned __int64
0x18000454a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000454f  mov     rsi, rax
0x180004552  test    rax, rax
0x180004555  jz      loc_1800048F4
0x18000455b  mov     r8, rbp; Size
0x18000455e  xor     edx, edx; Val
0x180004560  mov     rcx, rax; void *
0x180004563  call    memset_0
0x180004568  test    rbx, rbx
0x18000456b  jnz     loc_18000468B
0x180004571  lea     rdx, [rsp+98h+nSize]; nSize
0x180004576  mov     rcx, rsi; lpBuffer
0x180004579  call    cs:__imp_GetComputerNameW
0x18000457f  nop
0x180004580  cmp     word ptr [rsi+rdi*2+2], 0
0x180004586  lea     rdi, [rdi+1]
0x18000458a  jnz     short loc_180004580
0x18000458c  test    r14d, r14d
0x18000458f  jz      short loc_1800045DA
0x180004591  mov     rcx, rsi; hMem
0x180004594  call    cs:__imp_LocalFree
0x18000459a  mov     rbp, [rsp+98h+arg_0]
0x1800045a2  mov     eax, r14d
0x1800045a5  mov     r15, [rsp+98h+arg_10]
0x1800045ad  mov     rbx, [rsp+98h+arg_18]
0x1800045b5  add     rsp, 70h
0x1800045b9  pop     r14
0x1800045bb  pop     r13
0x1800045bd  pop     r12
0x1800045bf  pop     rdi
0x1800045c0  pop     rsi
0x1800045c1  retn
0x1800045c2  mov     r9, [rsp+98h+arg_20]; unsigned int *
0x1800045ca  mov     r8d, r13d; unsigned int
0x1800045cd  mov     rdx, r12; struct _PERF_INSTANCE_HEADER *
0x1800045d0  mov     rcx, r15; struct PERFLIBCI_COUNTERSET_NODE *
0x1800045d3  call    ?PerfpEnumerateKernelInstances@@YAKPEAUPERFLIBCI_COUNTERSET_NODE@@PEAU_PERF_INSTANCE_HEADER@@KPEAK@Z; PerfpEnumerateKernelInstances(PERFLIBCI_COUNTERSET_NODE *,_PERF_INSTANCE_HEADER *,ulong,ulong *)
0x1800045d8  jmp     short loc_1800045A5
0x1800045da  mov     rcx, [rsp+98h+arg_8]
0x1800045e2  lea     rax, [rsp+98h+var_48]
0x1800045e7  mov     qword ptr [rsp+98h+var_70], rax
0x1800045ec  lea     r9d, ds:2[rdi*2]
0x1800045f4  lea     rax, [rsp+98h+hMem]
0x1800045f9  mov     [rsp+98h+var_48], 2000h
0x180004601  mov     r8, rsi
0x180004604  mov     [rsp+98h+var_78], rax; int
0x180004609  call    PerfpSendStateLessNotification
0x18000460e  mov     r14d, eax
0x180004611  test    eax, eax
0x180004613  jnz     loc_180004591
0x180004619  mov     rcx, [rsp+98h+hMem]; hMem
0x18000461e  xor     edx, edx
0x180004620  xor     ebx, ebx
0x180004622  mov     dword ptr [rsp+98h+Src], edx
0x180004626  mov     [rsp+98h+var_50], ebx
0x18000462a  mov     ebp, 8
0x18000462f  mov     [rsp+98h+var_3C], edx
0x180004633  mov     [rsp+98h+var_40], ebp
0x180004637  cmp     edx, [rcx]
0x180004639  jb      loc_1800046CA
0x18000463f  cmp     dword ptr [r15+58h], 6
0x180004644  jz      loc_18000485D
0x18000464a  mov     edx, dword ptr [rsp+98h+Src]
0x18000464e  test    r14d, 0FFFFFFF7h
0x180004655  jnz     short loc_180004680
0x180004657  mov     eax, [r15+58h]
0x18000465b  cmp     eax, 6
0x18000465e  jnz     loc_180004710
0x180004664  mov     eax, r14d
0x180004667  test    ebx, ebx
0x180004669  mov     r14d, 1069h
0x18000466f  cmovz   eax, r14d
0x180004673  mov     r14d, eax
0x180004676  mov     rax, [rsp+98h+arg_20]
0x18000467e  mov     [rax], edx
0x180004680  call    cs:__imp_LocalFree
0x180004686  jmp     loc_180004591
0x18000468b  cmp     word ptr [rbx], 0
0x18000468f  jz      loc_180004571
0x180004695  mov     edx, [rsp+98h+nSize]; unsigned __int64
0x180004699  mov     r8, rbx; unsigned __int16 *
0x18000469c  mov     rcx, rsi; unsigned __int16 *
0x18000469f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800046a4  jmp     loc_180004580
0x1800046a9  test    r12, r12
0x1800046ac  jnz     short loc_1800046B9
0x1800046ae  mov     r14d, 57h ; 'W'
0x1800046b4  jmp     loc_18000450C
0x1800046b9  lea     eax, [r13-1]
0x1800046bd  mov     [r12], sil
0x1800046c1  mov     [rax+r12], sil
0x1800046c5  jmp     loc_18000450C
0x1800046ca  cmp     ebp, [rsp+98h+var_48]
0x1800046ce  jnb     loc_18000463F
0x1800046d4  mov     edi, ebp
0x1800046d6  add     rdi, rcx
0x1800046d9  mov     r10d, [rdi]
0x1800046dc  mov     [rsp+98h+var_30], r10d
0x1800046e1  cmp     r10d, 20h ; ' '
0x1800046e5  jb      short loc_180004706
0x1800046e7  cmp     dword ptr [rdi+0Ch], 0
0x1800046eb  jnz     short loc_180004706
0x1800046ed  test    byte ptr [r15+58h], 2
0x1800046f2  mov     eax, [rdi+18h]
0x1800046f5  jnz     short loc_180004732
0x1800046f7  cmp     eax, 0FFFFFFFFh
0x1800046fa  jnz     loc_18000491E
0x180004700  inc     ebx
0x180004702  mov     [rsp+98h+var_50], ebx
0x180004706  add     ebp, r10d
0x180004709  inc     edx
0x18000470b  jmp     loc_18000462F
0x180004710  test    eax, eax
0x180004712  jnz     loc_180004946
0x180004718  cmp     ebx, 1
0x18000471b  jbe     loc_18000495D
0x180004721  mov     r14d, 1073h
0x180004727  call    cs:__imp_LocalFree
0x18000472d  jmp     loc_180004591
0x180004732  cmp     eax, 0FFFFFFFFh
0x180004735  jnz     short loc_180004742
0x180004737  mov     r14d, 1073h
0x18000473d  jmp     loc_18000463F
0x180004742  test    eax, eax
0x180004744  jz      short loc_180004706
0x180004746  lea     rax, [r10-8]
0x18000474a  mov     rcx, r10
0x18000474d  cmp     rax, 20h ; ' '
0x180004751  jbe     loc_180004853
0x180004757  mov     ebp, dword ptr [rsp+98h+Src]
0x18000475b  mov     r9d, 20h ; ' '
0x180004761  mov     [rsp+98h+var_44], r9d
0x180004766  mov     edx, r9d
0x180004769  nop     dword ptr [rax+00000000h]
0x180004770  mov     r8d, [rdx+rdi]
0x180004774  lea     rax, [rdx+rdi]
0x180004778  sub     ecx, r9d
0x18000477b  mov     [rsp+98h+Src], rax
0x180004780  cmp     r8d, ecx
0x180004783  ja      loc_180004842
0x180004789  cmp     r8d, 10h
0x18000478d  jb      loc_180004842
0x180004793  lea     rcx, [rax+8]; Source
0x180004797  lea     rax, [r8-8]
0x18000479b  shr     rax, 1
0x18000479e  mov     edx, eax; MaxCount
0x1800047a0  mov     ebx, eax
0x1800047a2  call    cs:__imp_wcsnlen
0x1800047a8  cmp     rbx, rax
0x1800047ab  jz      loc_18000492B
0x1800047b1  mov     rax, [rsp+98h+Src]
0x1800047b6  mov     rcx, r15; struct PERFLIBCI_COUNTERSET_NODE *
0x1800047b9  mov     r9d, [rdi+1Ch]; unsigned int
0x1800047bd  mov     r8d, [rax+4]; unsigned int
0x1800047c1  lea     rdx, [rax+8]; unsigned __int16 *
0x1800047c5  call    ?PerflibciFindInstance@@YAPEAUPERFLIBCI_INSTANCE_NODE@@PEAUPERFLIBCI_COUNTERSET_NODE@@PEAGKKH@Z; PerflibciFindInstance(PERFLIBCI_COUNTERSET_NODE *,ushort *,ulong,ulong,int)
0x1800047ca  mov     ebx, [rsp+98h+var_50]
0x1800047ce  test    rax, rax
0x1800047d1  mov     rax, [rsp+98h+Src]
0x1800047d6  jz      short loc_180004823
0x1800047d8  inc     ebx
0x1800047da  test    byte ptr [r15+58h], 2
0x1800047df  mov     [rsp+98h+var_50], ebx
0x1800047e3  jz      short loc_180004823
0x1800047e5  test    r12, r12
0x1800047e8  jz      loc_1800048FF
0x1800047ee  mov     edx, [rax]
0x1800047f0  lea     ecx, [rdx+rbp]
0x1800047f3  cmp     ebp, ecx
0x1800047f5  ja      loc_1800048FF
0x1800047fb  cmp     edx, ecx
0x1800047fd  ja      loc_1800048FF
0x180004803  cmp     ecx, r13d
0x180004806  ja      loc_1800048FF
0x18000480c  mov     r8d, edx; Size
0x18000480f  mov     ecx, ebp
0x180004811  add     rcx, r12; void *
0x180004814  mov     rdx, rax; Src
0x180004817  call    memcpy_0
0x18000481c  mov     rax, [rsp+98h+Src]
0x180004821  add     ebp, [rax]
0x180004823  mov     r9d, [rsp+98h+var_44]
0x180004828  add     r9d, [rax]
0x18000482b  mov     ecx, [rdi]
0x18000482d  mov     edx, r9d
0x180004830  mov     [rsp+98h+var_44], r9d
0x180004835  lea     rax, [rcx-8]
0x180004839  cmp     rdx, rax
0x18000483c  jb      loc_180004770
0x180004842  mov     edx, [rsp+98h+var_3C]
0x180004846  mov     r10d, [rsp+98h+var_30]
0x18000484b  mov     dword ptr [rsp+98h+Src], ebp
0x18000484f  mov     ebp, [rsp+98h+var_40]
0x180004853  mov     rcx, [rsp+98h+hMem]
0x180004858  jmp     loc_180004706
0x18000485d  test    ebx, ebx
0x18000485f  jz      loc_18000464A
0x180004865  inc     ebx
0x180004867  test    r12, r12
0x18000486a  jz      loc_180004934
0x180004870  mov     edx, dword ptr [rsp+98h+Src]
0x180004874  lea     r10d, [rdx+18h]
0x180004878  cmp     edx, r10d
0x18000487b  jnb     loc_180004938
0x180004881  cmp     r10d, 18h
0x180004885  jb      loc_180004938
0x18000488b  cmp     r10d, r13d
0x18000488e  ja      loc_180004938
0x180004894  mov     qword ptr [rdx+r12], 18h
0x18000489c  lea     r9, String2; "_Total"
0x1800048a3  add     rdx, 8
0x1800048a7  mov     ecx, 7FFFFFFEh
0x1800048ac  add     rdx, r12
0x1800048af  mov     r8d, 7
0x1800048b5  test    rcx, rcx
0x1800048b8  jz      short loc_1800048D7
0x1800048ba  movzx   eax, word ptr [r9]
0x1800048be  test    ax, ax
0x1800048c1  jz      short loc_1800048D7
0x1800048c3  mov     [rdx], ax
0x1800048c6  add     r9, 2
0x1800048ca  add     rdx, 2
0x1800048ce  dec     rcx
0x1800048d1  sub     r8, 1
0x1800048d5  jnz     short loc_1800048B5
0x1800048d7  test    r8, r8
0x1800048da  lea     rcx, [rdx-2]
0x1800048de  cmovnz  rcx, rdx
0x1800048e2  xor     eax, eax
0x1800048e4  mov     edx, r10d
0x1800048e7  mov     [rcx], ax
0x1800048ea  mov     rcx, [rsp+98h+hMem]
0x1800048ef  jmp     loc_18000464E
0x1800048f4  mov     r14d, 0Eh
0x1800048fa  jmp     loc_180004591
0x1800048ff  mov     r14d, 8
0x180004905  jmp     loc_180004821
0x18000490a  mov     eax, 1068h
0x18000490f  jmp     loc_1800045A5
0x180004914  mov     eax, 105h
0x180004919  jmp     loc_18000452B
0x18000491e  test    eax, eax
0x180004920  jnz     loc_180004737
  ... truncated ...
```
