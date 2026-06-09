# HeapInfo::Rescan(RescanFlags)

- ea: `0x180008e4c`
- end: `0x1800094ef`
- name: `?Rescan@HeapInfo@@QEAAIW4RescanFlags@@@Z`
- size: `1699`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800048ac`
- `0x180004f18`

## callees

- `0x180008748`
- `0x180008c98`
- `0x180008e4c`
- `0x180009500`
- `0x180009778`
- `0x180009a10`
- `0x180009cc0`
- `0x180009d70`
- `0x18000a0b4`
- `0x18000a1e8`
- `0x180255e44`
- `0x180255eb0`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x180009178`
- `KERNEL32!ResetWriteWatch` at `0x1800091a3`
- `KERNEL32!ResetWriteWatch` at `0x180009178`
- `KERNEL32!ResetWriteWatch` at `0x1800091a3`
- `KERNEL32!GetWriteWatch` at `0x180008faf`
- `KERNEL32!GetWriteWatch` at `0x18000906b`
- `KERNEL32!GetWriteWatch` at `0x180008faf`
- `KERNEL32!GetWriteWatch` at `0x18000906b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HeapInfo::Rescan(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r15d
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // rbx
  int v9; // edi
  __int64 v10; // r8
  int v11; // ecx
  _BYTE *v12; // r12
  __int64 v13; // rbx
  __int64 v14; // rcx
  DWORD v15; // eax
  PVOID *v16; // rdi
  __int64 v17; // rbx
  _BYTE *v18; // rdi
  int v19; // eax
  int v20; // ebx
  int v21; // eax
  int v22; // r12d
  __int64 i; // rbx
  int v24; // ebx
  int v25; // ebx
  int v27; // eax
  unsigned int v28; // r13d
  char *v29; // r9
  __int64 v30; // rdi
  unsigned int v31; // r15d
  unsigned int v32; // r14d
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rdx
  _QWORD *v36; // rcx
  char v37; // al
  int v38; // eax
  int v39; // eax
  unsigned int v40; // r15d
  char *v41; // r9
  __int64 v42; // rdi
  unsigned int v43; // r12d
  int v44; // r13d
  unsigned int v45; // r14d
  __int64 v46; // rax
  __int64 v47; // rax
  _QWORD *v48; // rdx
  _QWORD *v49; // rcx
  char v50; // al
  int v51; // eax
  _QWORD *Chunk; // rax
  _QWORD *v53; // rax
  bool v54; // al
  int v55; // ebx
  DWORD lpdwGranularity; // [rsp+30h] [rbp-50h] BYREF
  __int64 v57; // [rsp+38h] [rbp-48h]
  PVOID Addresses; // [rsp+40h] [rbp-40h] BYREF
  DWORD dwGranularity[2]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE *v60; // [rsp+50h] [rbp-30h]
  ULONG_PTR dwCount; // [rsp+58h] [rbp-28h] BYREF
  int v62; // [rsp+60h] [rbp-20h]
  int v63; // [rsp+64h] [rbp-1Ch]
  __int64 v64; // [rsp+68h] [rbp-18h]
  __int64 v65; // [rsp+70h] [rbp-10h]
  __int64 v66; // [rsp+78h] [rbp-8h]

  v66 = -2;
  v2 = a2;
  v62 = 0;
  v3 = 0;
  v65 = 0;
  do
  {
    v4 = 304 * v3;
    v5 = v4 + a1 + 88;
    v64 = v5;
    v6 = *(_QWORD *)(a1 + 56);
    v7 = a1 + v4;
    v8 = *(_QWORD *)(a1 + v4 + 384);
    v9 = 0;
    while ( v8 )
    {
      if ( (unsigned __int8)SmallNormalHeapBlock::NeedRescanObjects(v8, v6, v2) )
      {
        SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<1,1>(
          (SmallFinalizableHeapBlock *)v8,
          (struct Recycler *)v6);
LABEL_3:
        ++v9;
        goto LABEL_4;
      }
      if ( *(_BYTE *)(v8 + 120) )
        goto LABEL_3;
LABEL_4:
      v8 = *(_QWORD *)(v8 + 32);
    }
    v63 = v9 + SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(v7 + 280, v6, v2);
    v11 = *(_DWORD *)v6 & 0x2001;
    v12 = (_BYTE *)(v6 + 12901);
    v60 = (_BYTE *)(v6 + 12901);
    if ( v11 != 8193 )
    {
      if ( *v12 )
        v60 = (_BYTE *)(v6 + 12901);
      else
        HeapBucketT<SmallLeafHeapBlock>::PrepareSweep(v5 + 104);
    }
    if ( (*(_DWORD *)v6 & 0x2001) != 0x2001 && !*v12 )
      HeapBucketT<SmallNormalHeapBlock>::PrepareSweep(v5);
    v13 = *(_QWORD *)(v5 + 72);
    v14 = 0;
    v57 = 0;
    if ( !v13 )
      goto LABEL_29;
    v15 = v2 & 1;
    lpdwGranularity = v15;
    do
    {
      if ( v15 )
      {
        *(_BYTE *)(v13 + 120) = 0;
      }
      else if ( *(_BYTE *)(v13 + 120) )
      {
        if ( (v2 & 2) != 0 )
        {
          ResetWriteWatch(*(LPVOID *)(v13 + 8), 0x1000u);
LABEL_24:
          v14 = v57;
          goto LABEL_25;
        }
        goto LABEL_25;
      }
      if ( !*(_WORD *)(v13 + 80) )
        goto LABEL_25;
      if ( !*(_BYTE *)(v13 + 25) )
      {
        if ( *v12 )
          goto LABEL_25;
        dwCount = 1;
        dwGranularity[0] = 4096;
        Addresses = 0;
        v16 = (PVOID *)(v13 + 8);
        if ( GetWriteWatch((v2 >> 1) & 1, *(PVOID *)(v13 + 8), 0x1000u, &Addresses, &dwCount, dwGranularity) || dwCount )
        {
          v14 = v57;
          goto LABEL_55;
        }
        goto LABEL_24;
      }
      if ( !*(_BYTE *)(v6 + 12888) )
      {
        *(_BYTE *)(v13 + 25) = 0;
        v16 = (PVOID *)(v13 + 8);
LABEL_55:
        *(_BYTE *)(v13 + 120) = 1;
        v27 = *(unsigned __int16 *)(v13 + 74);
        v28 = *(unsigned __int16 *)(v13 + 80);
        v29 = (char *)*v16;
        Addresses = *v16;
        v30 = *(unsigned __int16 *)(v13 + 72);
        if ( v28 == v27 )
        {
          v54 = Recycler::AddMark((Recycler *)v6, v29, (unsigned int)(v27 * v30));
          v14 = v57;
          if ( !v54 )
          {
            *(_BYTE *)(v13 + 25) = 1;
            *(_BYTE *)(v6 + 12888) = 1;
          }
        }
        else
        {
          v31 = 0;
          v10 = 0;
          dwGranularity[0] = 0;
          v32 = 0;
          if ( v28 )
          {
            while ( 1 )
            {
              v33 = *(_QWORD *)(v13 + 8 * ((unsigned __int64)v32 >> 6) + 88);
              if ( _bittest64(&v33, v32 & 0x3F) )
                break;
LABEL_65:
              v10 = (unsigned int)(v10 + 1);
              dwGranularity[0] = v10;
              v32 += (unsigned int)v30 >> 5;
              if ( v31 >= v28 )
              {
                v12 = v60;
                v2 = a2;
                v14 = v57;
                goto LABEL_26;
              }
            }
            v34 = *(_QWORD *)(v6 + 12680);
            v35 = *(_QWORD **)(v34 + 16);
            v36 = v35 + 2;
            if ( (unsigned __int64)(v35 + 2) <= *(_QWORD *)(v34 + 24) )
            {
              *(_QWORD *)(v34 + 16) = v36;
              goto LABEL_60;
            }
            Chunk = *(_QWORD **)(v6 + 12688);
            if ( Chunk )
            {
              *(_QWORD *)(v6 + 12688) = 0;
LABEL_85:
              *Chunk = *(_QWORD *)(v6 + 12680);
              Chunk[2] = Chunk + 6;
              *(_QWORD *)(v6 + 12680) = Chunk;
              v35 = Chunk + 4;
LABEL_60:
              if ( v35 )
              {
                *v35 = &v29[(unsigned int)(v30 * v10)];
                v35[1] = v30;
                v37 = 1;
LABEL_62:
                if ( v37 )
                {
                  v38 = 1;
                }
                else
                {
                  *(_BYTE *)(v13 + 25) = 1;
                  *(_BYTE *)(v6 + 12888) = 1;
                  v38 = *(unsigned __int16 *)(v13 + 74) + 1;
                }
                v31 += v38;
                goto LABEL_65;
              }
            }
            else
            {
              Chunk = (_QWORD *)PageStackBase<Recycler::MarkCandidate>::CreateChunk(v36, v6 + 12712, v10);
              if ( Chunk )
              {
                LODWORD(v10) = dwGranularity[0];
                v29 = (char *)Addresses;
                goto LABEL_85;
              }
            }
            v37 = 0;
            LODWORD(v10) = dwGranularity[0];
            v29 = (char *)Addresses;
            goto LABEL_62;
          }
          v2 = a2;
        }
LABEL_26:
        v57 = ++v14;
        goto LABEL_27;
      }
LABEL_25:
      if ( *(_BYTE *)(v13 + 120) )
        goto LABEL_26;
LABEL_27:
      v13 = *(_QWORD *)(v13 + 32);
      v15 = lpdwGranularity;
    }
    while ( v13 );
    v5 = v64;
LABEL_29:
    v17 = *(_QWORD *)(v5 + 80);
    v18 = 0;
    v60 = 0;
    if ( !v17 )
      goto LABEL_42;
    v19 = v2 & 1;
    LODWORD(dwCount) = v19;
    do
    {
      if ( v19 )
      {
        *(_BYTE *)(v17 + 120) = 0;
      }
      else if ( *(_BYTE *)(v17 + 120) )
      {
        if ( (v2 & 2) != 0 )
          ResetWriteWatch(*(LPVOID *)(v17 + 8), 0x1000u);
LABEL_38:
        if ( !*(_BYTE *)(v17 + 120) )
          goto LABEL_40;
        goto LABEL_39;
      }
      if ( !*(_WORD *)(v17 + 80) )
        goto LABEL_38;
      if ( *(_BYTE *)(v17 + 25) )
      {
        if ( *(_BYTE *)(v6 + 12888) )
          goto LABEL_38;
        *(_BYTE *)(v17 + 25) = 0;
      }
      else
      {
        if ( *(_BYTE *)(v6 + 12901) )
          goto LABEL_38;
        Addresses = (PVOID)1;
        lpdwGranularity = 4096;
        *(_QWORD *)dwGranularity = 0;
        if ( !GetWriteWatch(
                (v2 >> 1) & 1,
                *(PVOID *)(v17 + 8),
                0x1000u,
                (PVOID *)dwGranularity,
                (ULONG_PTR *)&Addresses,
                &lpdwGranularity)
          && !Addresses )
        {
          goto LABEL_38;
        }
      }
      *(_BYTE *)(v17 + 120) = 1;
      v39 = *(unsigned __int16 *)(v17 + 74);
      v40 = *(unsigned __int16 *)(v17 + 80);
      v41 = *(char **)(v17 + 8);
      Addresses = v41;
      v42 = *(unsigned __int16 *)(v17 + 72);
      if ( v40 == v39 )
      {
        if ( !Recycler::AddMark((Recycler *)v6, v41, (unsigned int)(v39 * v42)) )
        {
          *(_BYTE *)(v17 + 25) = 1;
          *(_BYTE *)(v6 + 12888) = 1;
        }
      }
      else
      {
        lpdwGranularity = (unsigned int)v42 >> 5;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        if ( v40 )
        {
          while ( 1 )
          {
            v46 = *(_QWORD *)(v17 + 8 * ((unsigned __int64)v45 >> 6) + 88);
            if ( _bittest64(&v46, v45 & 0x3F) )
              break;
LABEL_77:
            ++v44;
            v45 += lpdwGranularity;
            if ( v43 >= v40 )
              goto LABEL_78;
          }
          v47 = *(_QWORD *)(v6 + 12680);
          v48 = *(_QWORD **)(v47 + 16);
          v49 = v48 + 2;
          if ( (unsigned __int64)(v48 + 2) > *(_QWORD *)(v47 + 24) )
          {
            v53 = *(_QWORD **)(v6 + 12688);
            if ( v53 )
            {
              *(_QWORD *)(v6 + 12688) = 0;
            }
            else
            {
              v53 = (_QWORD *)PageStackBase<Recycler::MarkCandidate>::CreateChunk(v49, v6 + 12712, v10);
              if ( !v53 )
                goto LABEL_103;
              v41 = (char *)Addresses;
            }
            *v53 = *(_QWORD *)(v6 + 12680);
            v53[2] = v53 + 6;
            *(_QWORD *)(v6 + 12680) = v53;
            v48 = v53 + 4;
          }
          else
          {
            *(_QWORD *)(v47 + 16) = v49;
          }
          if ( v48 )
          {
            *v48 = &v41[(unsigned int)(v42 * v44)];
            v48[1] = v42;
            v50 = 1;
LABEL_74:
            if ( v50 )
            {
              v51 = 1;
            }
            else
            {
              *(_BYTE *)(v17 + 25) = 1;
              *(_BYTE *)(v6 + 12888) = 1;
              v51 = *(unsigned __int16 *)(v17 + 74) + 1;
            }
            v43 += v51;
            goto LABEL_77;
          }
LABEL_103:
          v50 = 0;
          v41 = (char *)Addresses;
          goto LABEL_74;
        }
      }
LABEL_78:
      v18 = v60;
      v2 = a2;
LABEL_39:
      v60 = ++v18;
LABEL_40:
      v17 = *(_QWORD *)(v17 + 32);
      v19 = dwCount;
    }
    while ( v17 );
    v5 = v64;
LABEL_42:
    if ( *(_BYTE *)(v6 + 12903) )
    {
      v20 = (_DWORD)v18 + v57;
      v55 = SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<1,0>(*(SmallNormalHeapBlock **)(v5 + 88))
          + v20;
      v21 = v55
          + SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<1,0>(*(SmallNormalHeapBlock **)(v5 + 96));
    }
    else
    {
      v21 = (_DWORD)v18 + v57;
    }
    v22 = v63 + v21 + v62;
    v62 = v22;
    v3 = v65 + 1;
    v65 = v3;
  }
  while ( v3 != 32 );
  for ( i = 0; i != 32; ++i )
    v22 += LargeHeapBucket::Rescan(a1 + 8 * (i + 8 * i + 1227), v2);
  v24 = LargeHeapBucket::Rescan(a1 + 12120, v2) + v22;
  v25 = SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(
          *(_QWORD *)(a1 + 72),
          *(_QWORD *)(a1 + 56),
          v2)
      + v24;
  return v25
       + (unsigned int)SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(*(SmallFinalizableHeapBlock **)(a1 + 80));
}

```

## disassembly

```asm
0x180008e4c  mov     rax, rsp
0x180008e4f  mov     [rax+10h], edx
0x180008e52  mov     [rax+8], rcx
0x180008e56  push    rbp
0x180008e57  push    rsi
0x180008e58  push    rdi
0x180008e59  push    r12
0x180008e5b  push    r13
0x180008e5d  push    r14
0x180008e5f  push    r15
0x180008e61  mov     rbp, rsp
0x180008e64  sub     rsp, 80h
0x180008e6b  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180008e73  mov     [rax+18h], rbx
0x180008e77  mov     r15d, [rbp+arg_8]
0x180008e7b  xor     r10d, r10d
0x180008e7e  mov     [rbp+var_20], r10d
0x180008e82  mov     eax, r10d
0x180008e85  mov     [rbp+var_10], rax
0x180008e89  imul    rax, 130h
0x180008e90  mov     rcx, [rbp+arg_0]
0x180008e94  lea     r13, [rcx+58h]
0x180008e98  add     r13, rax
0x180008e9b  mov     [rbp+var_18], r13
0x180008e9f  mov     rsi, [rcx+38h]
0x180008ea3  lea     r14, [rcx+rax]
0x180008ea7  mov     rbx, [r14+180h]
0x180008eae  mov     rdi, r10
0x180008eb1  jmp     short loc_180008EBA
0x180008eb3  inc     rdi
0x180008eb6  mov     rbx, [rbx+20h]
0x180008eba  mov     r8d, r15d
0x180008ebd  mov     rdx, rsi
0x180008ec0  test    rbx, rbx
0x180008ec3  jz      short loc_180008EDC
0x180008ec5  mov     rcx, rbx
0x180008ec8  call    ?NeedRescanObjects@SmallNormalHeapBlock@@QEAA_NPEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBlock::NeedRescanObjects(Recycler *,RescanFlags)
0x180008ecd  test    al, al
0x180008ecf  jnz     loc_180009499
0x180008ed5  cmp     [rbx+78h], al
0x180008ed8  jz      short loc_180008EB6
0x180008eda  jmp     short loc_180008EB3
0x180008edc  lea     rcx, [r14+118h]
0x180008ee3  call    ?Rescan@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@IEAAIPEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(Recycler *,RescanFlags)
0x180008ee8  add     eax, edi
0x180008eea  mov     [rbp+var_1C], eax
0x180008eed  mov     ecx, [rsi]
0x180008eef  mov     ebx, 2001h
0x180008ef4  and     ecx, ebx
0x180008ef6  lea     r12, [rsi+3265h]
0x180008efd  mov     [rbp+var_30], r12
0x180008f01  cmp     ecx, ebx
0x180008f03  jz      short loc_180008F19
0x180008f05  cmp     byte ptr [r12], 0
0x180008f0a  jnz     loc_180009490
0x180008f10  lea     rcx, [r13+68h]
0x180008f14  call    ?PrepareSweep@?$HeapBucketT@VSmallLeafHeapBlock@@@@QEAAXXZ; HeapBucketT<SmallLeafHeapBlock>::PrepareSweep(void)
0x180008f19  mov     eax, [rsi]
0x180008f1b  and     eax, ebx
0x180008f1d  cmp     eax, ebx
0x180008f1f  jz      short loc_180008F30
0x180008f21  cmp     byte ptr [r12], 0
0x180008f26  jnz     short loc_180008F30
0x180008f28  mov     rcx, r13
0x180008f2b  call    ?PrepareSweep@?$HeapBucketT@VSmallNormalHeapBlock@@@@QEAAXXZ; HeapBucketT<SmallNormalHeapBlock>::PrepareSweep(void)
0x180008f30  mov     rbx, [r13+48h]
0x180008f34  xor     r10d, r10d
0x180008f37  mov     ecx, r10d
0x180008f3a  mov     [rbp+var_48], rcx
0x180008f3e  test    rbx, rbx
0x180008f41  jz      loc_180008FEF
0x180008f47  mov     eax, r15d
0x180008f4a  and     eax, 1
0x180008f4d  mov     [rbp+var_50], eax
0x180008f50  test    eax, eax
0x180008f52  jz      loc_18000915B
0x180008f58  mov     [rbx+78h], r10b
0x180008f5c  cmp     [rbx+50h], r10w
0x180008f61  jz      short loc_180008FCE
0x180008f63  cmp     [rbx+19h], r10b
0x180008f67  jnz     loc_180009325
0x180008f6d  cmp     [r12], r10b
0x180008f71  jnz     short loc_180008FCE
0x180008f73  mov     [rbp+dwCount], 1
0x180008f7b  mov     edx, 1000h
0x180008f80  mov     [rbp+dwGranularity], edx
0x180008f83  mov     [rbp+Addresses], r10
0x180008f87  lea     rdi, [rbx+8]
0x180008f8b  mov     ecx, r15d
0x180008f8e  shr     ecx, 1
0x180008f90  and     ecx, 1; dwFlags
0x180008f93  lea     rax, [rbp+dwGranularity]
0x180008f97  mov     [rsp+80h+lpdwGranularity], rax; lpdwGranularity
0x180008f9c  lea     rax, [rbp+dwCount]
0x180008fa0  mov     [rsp+80h+lpdwCount], rax; lpdwCount
0x180008fa5  lea     r9, [rbp+Addresses]; lpAddresses
0x180008fa9  mov     r8d, edx; dwRegionSize
0x180008fac  mov     rdx, [rdi]; lpBaseAddress
0x180008faf  call    cs:__imp_GetWriteWatch
0x180008fb5  xor     r10d, r10d
0x180008fb8  test    eax, eax
0x180008fba  jnz     loc_1800091B1
0x180008fc0  cmp     [rbp+dwCount], r10
0x180008fc4  jnz     loc_1800091B1
0x180008fca  mov     rcx, [rbp+var_48]
0x180008fce  cmp     [rbx+78h], r10b
0x180008fd2  jz      short loc_180008FDB
0x180008fd4  inc     rcx
0x180008fd7  mov     [rbp+var_48], rcx
0x180008fdb  mov     rbx, [rbx+20h]
0x180008fdf  test    rbx, rbx
0x180008fe2  mov     eax, [rbp+var_50]
0x180008fe5  jnz     loc_180008F50
0x180008feb  mov     r13, [rbp+var_18]
0x180008fef  mov     rbx, [r13+50h]
0x180008ff3  mov     rdi, r10
0x180008ff6  mov     [rbp+var_30], r10
0x180008ffa  test    rbx, rbx
0x180008ffd  jz      loc_1800090A7
0x180009003  mov     eax, r15d
0x180009006  and     eax, 1
0x180009009  mov     dword ptr [rbp+dwCount], eax
0x18000900c  test    eax, eax
0x18000900e  jz      loc_180009186
0x180009014  mov     [rbx+78h], r10b
0x180009018  cmp     [rbx+50h], r10w
0x18000901d  jz      short loc_180009086
0x18000901f  cmp     [rbx+19h], r10b
0x180009023  jnz     loc_18000933F
0x180009029  cmp     [rsi+3265h], r10b
0x180009030  jnz     short loc_180009086
0x180009032  mov     [rbp+Addresses], 1
0x18000903a  mov     edx, 1000h
0x18000903f  mov     [rbp+var_50], edx
0x180009042  mov     qword ptr [rbp+dwGranularity], r10
0x180009046  mov     ecx, r15d
0x180009049  shr     ecx, 1
0x18000904b  and     ecx, 1; dwFlags
0x18000904e  lea     rax, [rbp+var_50]
0x180009052  mov     [rsp+80h+lpdwGranularity], rax; lpdwGranularity
0x180009057  lea     rax, [rbp+Addresses]
0x18000905b  mov     [rsp+80h+lpdwCount], rax; lpdwCount
0x180009060  lea     r9, [rbp+dwGranularity]; lpAddresses
0x180009064  mov     r8d, edx; dwRegionSize
0x180009067  mov     rdx, [rbx+8]; lpBaseAddress
0x18000906b  call    cs:__imp_GetWriteWatch
0x180009071  xor     r10d, r10d
0x180009074  test    eax, eax
0x180009076  jnz     loc_180009274
0x18000907c  cmp     [rbp+Addresses], r10
0x180009080  jnz     loc_180009274
0x180009086  cmp     [rbx+78h], r10b
0x18000908a  jz      short loc_180009093
0x18000908c  inc     rdi
0x18000908f  mov     [rbp+var_30], rdi
0x180009093  mov     rbx, [rbx+20h]
0x180009097  test    rbx, rbx
0x18000909a  mov     eax, dword ptr [rbp+dwCount]
0x18000909d  jnz     loc_18000900C
0x1800090a3  mov     r13, [rbp+var_18]
0x1800090a7  mov     rbx, [rbp+var_48]
0x1800090ab  add     ebx, edi
0x1800090ad  cmp     [rsi+3267h], r10b
0x1800090b4  jnz     loc_1800094C5
0x1800090ba  mov     eax, ebx
0x1800090bc  add     eax, [rbp+var_1C]
0x1800090bf  mov     r12d, [rbp+var_20]
0x1800090c3  add     r12d, eax
0x1800090c6  mov     [rbp+var_20], r12d
0x1800090ca  mov     rax, [rbp+var_10]
0x1800090ce  inc     rax
0x1800090d1  mov     [rbp+var_10], rax
0x1800090d5  cmp     rax, 20h ; ' '
0x1800090d9  jnz     loc_180008E89
0x1800090df  mov     rbx, r10
0x1800090e2  mov     rdi, [rbp+arg_0]
0x1800090e6  lea     rax, ds:4CBh[rbx*8]
0x1800090ee  add     rax, rbx
0x1800090f1  lea     rcx, [rdi+rax*8]
0x1800090f5  mov     edx, r15d
0x1800090f8  call    ?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z; LargeHeapBucket::Rescan(RescanFlags)
0x1800090fd  add     r12d, eax
0x180009100  inc     rbx
0x180009103  cmp     rbx, 20h ; ' '
0x180009107  jnz     short loc_1800090E6
0x180009109  lea     rcx, [rdi+2F58h]
0x180009110  mov     edx, r15d
0x180009113  call    ?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z; LargeHeapBucket::Rescan(RescanFlags)
0x180009118  lea     ebx, [rax+r12]
0x18000911c  mov     r8d, r15d
0x18000911f  mov     rdx, [rdi+38h]
0x180009123  mov     rcx, [rdi+48h]
0x180009127  call    ??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallNormalHeapBlock@@@@KA_KPEAVSmallNormalHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(SmallNormalHeapBlock *,Recycler *,RescanFlags)
0x18000912c  add     ebx, eax
0x18000912e  mov     r8d, r15d
0x180009131  mov     rdx, [rdi+38h]
0x180009135  mov     rcx, [rdi+50h]; this
0x180009139  call    ??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KA_KPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(SmallFinalizableHeapBlock *,Recycler *,RescanFlags)
0x18000913e  add     eax, ebx
0x180009140  mov     rbx, [rsp+80h+arg_10]
0x180009148  add     rsp, 80h
0x18000914f  pop     r15
0x180009151  pop     r14
0x180009153  pop     r13
0x180009155  pop     r12
0x180009157  pop     rdi
0x180009158  pop     rsi
0x180009159  pop     rbp
0x18000915a  retn
0x18000915b  cmp     [rbx+78h], r10b
0x18000915f  jz      loc_180008F5C
0x180009165  test    r15b, 2
0x180009169  jz      loc_180008FCE
0x18000916f  mov     edx, 1000h; dwRegionSize
0x180009174  mov     rcx, [rbx+8]; lpBaseAddress
0x180009178  call    cs:__imp_ResetWriteWatch
0x18000917e  xor     r10d, r10d
0x180009181  jmp     loc_180008FCA
0x180009186  cmp     [rbx+78h], r10b
0x18000918a  jz      loc_180009018
0x180009190  test    r15b, 2
0x180009194  jz      loc_180009086
0x18000919a  mov     edx, 1000h; dwRegionSize
0x18000919f  mov     rcx, [rbx+8]; lpBaseAddress
0x1800091a3  call    cs:__imp_ResetWriteWatch
0x1800091a9  xor     r10d, r10d
0x1800091ac  jmp     loc_180009086
0x1800091b1  mov     rcx, [rbp+var_48]
0x1800091b5  mov     byte ptr [rbx+78h], 1
0x1800091b9  movzx   eax, word ptr [rbx+4Ah]
0x1800091bd  movzx   r13d, word ptr [rbx+50h]
0x1800091c2  mov     r9, [rdi]
0x1800091c5  mov     [rbp+Addresses], r9
0x1800091c9  movzx   edi, word ptr [rbx+48h]
0x1800091cd  cmp     r13d, eax
0x1800091d0  jz      loc_180009408
0x1800091d6  mov     eax, edi
0x1800091d8  shr     eax, 5
0x1800091db  mov     r15d, r10d
0x1800091de  mov     r8d, r10d
0x1800091e1  mov     [rbp+dwGranularity], r10d
0x1800091e5  mov     r14d, r10d
0x1800091e8  test    r13d, r13d
0x1800091eb  jz      loc_1800093FF
0x1800091f1  mov     r12d, eax
0x1800091f4  mov     ecx, r14d
0x1800091f7  and     ecx, 3Fh
0x1800091fa  mov     eax, r14d
0x1800091fd  shr     rax, 6
0x180009201  mov     rax, [rbx+rax*8+58h]
0x180009206  bt      rax, rcx
0x18000920a  jnb     short loc_180009254
0x18000920c  mov     rax, [rsi+3188h]
0x180009213  mov     rdx, [rax+10h]
0x180009217  lea     rcx, [rdx+10h]
0x18000921b  cmp     rcx, [rax+18h]
0x18000921f  ja      loc_180009355
0x180009225  mov     [rax+10h], rcx
0x180009229  test    rdx, rdx
0x18000922c  jz      loc_1800094A9
0x180009232  mov     ecx, r8d
0x180009235  imul    ecx, edi
0x180009238  add     rcx, r9
0x18000923b  mov     [rdx], rcx
0x18000923e  mov     [rdx+8], rdi
0x180009242  mov     al, 1
0x180009244  test    al, al
0x180009246  jz      loc_180009464
0x18000924c  mov     eax, 1
0x180009251  add     r15d, eax
0x180009254  inc     r8d
0x180009257  mov     [rbp+dwGranularity], r8d
0x18000925b  add     r14d, r12d
0x18000925e  cmp     r15d, r13d
0x180009261  jb      short loc_1800091F4
0x180009263  mov     r12, [rbp+var_30]
0x180009267  mov     r15d, [rbp+arg_8]
0x18000926b  mov     rcx, [rbp+var_48]
0x18000926f  jmp     loc_180008FD4
0x180009274  mov     byte ptr [rbx+78h], 1
0x180009278  movzx   eax, word ptr [rbx+4Ah]
0x18000927c  movzx   r15d, word ptr [rbx+50h]
0x180009281  mov     r9, [rbx+8]
0x180009285  mov     [rbp+Addresses], r9
0x180009289  movzx   edi, word ptr [rbx+48h]
0x18000928d  cmp     r15d, eax
0x180009290  jz      loc_180009438
0x180009296  mov     eax, edi
0x180009298  shr     eax, 5
0x18000929b  mov     [rbp+var_50], eax
0x18000929e  mov     r12d, r10d
0x1800092a1  mov     r13d, r10d
0x1800092a4  mov     r14d, r10d
0x1800092a7  test    r15d, r15d
0x1800092aa  jz      short loc_180009318
0x1800092ac  mov     ecx, r14d
0x1800092af  and     ecx, 3Fh
0x1800092b2  mov     eax, r14d
0x1800092b5  shr     rax, 6
0x1800092b9  mov     rax, [rbx+rax*8+58h]
  ... truncated ...
```
