# TxfReadVersion

- ea: `0x140285a50`
- end: `0x140286534`
- name: `TxfReadVersion`
- size: `2788`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14002c840`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x140021590`
- `0x140025830`
- `0x1400415b4`
- `0x1400529f0`
- `0x1400531ac`
- `0x1400592c0`
- `0x140059740`
- `0x1400b6e90`
- `0x1401019cc`
- `0x1401c0130`
- `0x140285a50`

## import_xrefs

- `ntoskrnl!CcCopyReadEx` at `0x140285e3c`
- `ntoskrnl!CcCopyReadEx` at `0x1402861c7`
- `ntoskrnl!CcCopyReadEx` at `0x140285e3c`
- `ntoskrnl!CcCopyReadEx` at `0x1402861c7`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285d25`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285fe4`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285d25`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285fe4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140285dc7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140285dc7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140285b9a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140285b9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140285bcd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286275`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286432`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bcac1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140285bcd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286275`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286432`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bcac1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285cd3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285f8e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14028632a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285cd3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285f8e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14028632a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285d3f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140286008`
- `ntoskrnl!ExReleaseFastMutex` at `0x14028634b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285d3f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140286008`
- `ntoskrnl!ExReleaseFastMutex` at `0x14028634b`
- `ntoskrnl!ExRaiseStatus` at `0x140285e90`
- `ntoskrnl!ExRaiseStatus` at `0x14028621e`
- `ntoskrnl!ExRaiseStatus` at `0x1402864ed`
- `ntoskrnl!ExRaiseStatus` at `0x140285e90`
- `ntoskrnl!ExRaiseStatus` at `0x14028621e`
- `ntoskrnl!ExRaiseStatus` at `0x1402864ed`

## pseudocode

```c
void __fastcall TxfReadVersion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  _QWORD *v7; // rbx
  __int64 v8; // r15
  unsigned int v11; // r12d
  _QWORD *v12; // rdi
  __int64 v13; // r13
  __int64 v14; // r8
  __int64 v15; // rdi
  char v16; // si
  __int64 v17; // r9
  _QWORD *v18; // rdi
  signed __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r8
  unsigned int *v24; // rsi
  __int64 v25; // r9
  __int64 v26; // rdi
  __int64 v27; // rdx
  unsigned int v28; // edi
  __int64 v29; // rsi
  struct _ERESOURCE *v30; // rcx
  __int64 v31; // r8
  NTSTATUS *v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rdx
  unsigned int v38; // r13d
  _QWORD *v39; // rbx
  __int64 v40; // rsi
  ULONG i; // r9d
  _QWORD *v42; // r10
  unsigned __int64 v43; // r15
  unsigned int v44; // edi
  unsigned int v45; // r9d
  unsigned __int64 v46; // r8
  unsigned int v47; // esi
  unsigned int v48; // r8d
  _QWORD *v49; // rsi
  __int64 v50; // r9
  __int64 j; // rcx
  __int64 v52; // rdx
  NTSTATUS *v53; // rsi
  __int64 v54; // rdx
  unsigned int k; // edx
  unsigned int v56; // edx
  unsigned int v57; // ebx
  unsigned int v58; // edi
  __int64 v59; // rcx
  __int64 v60; // rdx
  char v61; // [rsp+40h] [rbp-148h]
  char v62; // [rsp+41h] [rbp-147h]
  unsigned __int64 v63; // [rsp+48h] [rbp-140h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-138h]
  _QWORD *v65; // [rsp+58h] [rbp-130h]
  unsigned int v66; // [rsp+60h] [rbp-128h]
  ULONG DeleteCount; // [rsp+64h] [rbp-124h] BYREF
  __int64 v68; // [rsp+68h] [rbp-120h]
  int v69; // [rsp+70h] [rbp-118h]
  unsigned int v70; // [rsp+74h] [rbp-114h]
  unsigned __int64 v71; // [rsp+78h] [rbp-110h]
  unsigned int v72; // [rsp+80h] [rbp-108h]
  _DWORD Size[3]; // [rsp+84h] [rbp-104h]
  _QWORD *v74; // [rsp+90h] [rbp-F8h]
  PVOID RestartKey; // [rsp+98h] [rbp-F0h] BYREF
  __int64 v76; // [rsp+A0h] [rbp-E8h]
  __int64 v77; // [rsp+A8h] [rbp-E0h]
  _QWORD *v78; // [rsp+B0h] [rbp-D8h]
  __int64 v79; // [rsp+B8h] [rbp-D0h]
  __int64 v80; // [rsp+C0h] [rbp-C8h]
  __int64 v81; // [rsp+C8h] [rbp-C0h]
  _QWORD *v82; // [rsp+D0h] [rbp-B8h]
  __int64 v83; // [rsp+D8h] [rbp-B0h] BYREF
  unsigned int v84; // [rsp+E0h] [rbp-A8h]
  __int64 v85; // [rsp+E8h] [rbp-A0h]
  __int64 v86; // [rsp+F0h] [rbp-98h]
  __int64 v87; // [rsp+F8h] [rbp-90h]
  __int64 v88; // [rsp+100h] [rbp-88h]
  __int128 MatchData; // [rsp+108h] [rbp-80h] BYREF
  __int128 v90; // [rsp+118h] [rbp-70h]
  __int128 v91; // [rsp+128h] [rbp-60h]
  int v92; // [rsp+138h] [rbp-50h]

  v7 = a4;
  v8 = a3;
  v81 = a2;
  v88 = a1;
  *(_QWORD *)&Size[1] = a5;
  v11 = a6;
  v72 = a6;
  DeleteCount = 0;
  MatchData = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  RestartKey = 0;
  v63 = 0;
  Size[0] = 0;
  v12 = *(_QWORD **)(a3 + 24);
  v74 = a4;
  v65 = (_QWORD *)(*(_QWORD *)(v12[23] + 320LL) + 280LL);
  v13 = 0;
  v76 = 0;
  v82 = 0;
  v80 = NtfsMapUserBuffer(a2, 1073741840);
  if ( *(_QWORD *)(a2 + 8) )
    v62 = 0;
  else
    v62 = *(_BYTE *)(a2 + 64);
  if ( (*(_DWORD *)(v12[66] + 24LL) & 0x1000) != 0 )
    TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept(a1, v12, a7);
  if ( !a7 )
    v8 = v12[35];
  while ( 1 )
  {
    v15 = v7[14];
    if ( v15 )
    {
      v16 = 0;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v15 + 528) + 64LL) + 136LL), 1u);
      if ( v15 == v7[14] )
      {
        TxfIncrementBackupAttributeDependencies(v15);
        v8 = v7[15];
        v16 = 1;
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v15 + 528) + 64LL) + 136LL));
      if ( v16 )
        break;
    }
    v7 = (_QWORD *)v7[5];
    if ( !v7 )
      goto LABEL_15;
  }
  a7 = 0;
  v82 = v7;
LABEL_15:
  v17 = *(_QWORD *)(v8 + 24);
  v79 = v17;
  v87 = v17;
  v18 = v74;
  v19 = *(_QWORD *)(v74[33] + 16LL);
  v20 = **(_QWORD **)&Size[1];
  if ( **(_QWORD **)&Size[1] >= v19 )
  {
    v58 = a6;
    v57 = 0;
    goto LABEL_97;
  }
  if ( v20 + a6 > v19 )
  {
    Size[0] = v20 + a6 - v19;
    v11 = v19 - v20;
    v72 = v19 - v20;
  }
  if ( a7 )
    goto LABEL_49;
  v63 = v20;
  v21 = v11;
  v64 = v11;
  v22 = v20;
  do
  {
    v23 = *(_QWORD *)(v17 + 32);
    if ( v22 + v21 > v23 )
    {
      if ( v22 >= v23 )
        goto LABEL_49;
      v21 = v23 - v20;
      v64 = v23 - v20;
    }
    *(_QWORD *)&MatchData = v22 >> 12;
    DWORD2(v90) = ((v22 & 0xFFF) + 4095 + v21) >> 12;
    RestartKey = 0;
    ExAcquireFastMutex((PFAST_MUTEX)v18[32]);
    if ( (v18[1] & 0x800) != 0 )
      v24 = 0;
    else
      v24 = (unsigned int *)RtlEnumerateGenericTableLikeADirectory(
                              (PRTL_AVL_TABLE)(v18 + 19),
                              TxfMatchPageRange,
                              &MatchData,
                              0,
                              &RestartKey,
                              &DeleteCount,
                              &MatchData);
    ExReleaseFastMutex((PFAST_MUTEX)v18[32]);
    if ( !v24 )
    {
      v28 = v21;
LABEL_32:
      v29 = v79;
      v30 = *(struct _ERESOURCE **)(*(_QWORD *)(v79 + 184) + 112LL);
      if ( v30 && !ExIsResourceAcquiredSharedLite(v30) )
      {
        LOBYTE(v31) = 1;
        NtfsAcquirePagingResourceExclusive(a1, *(_QWORD *)(v29 + 184), v31);
        v13 = v29;
        v76 = v29;
      }
      v32 = (NTSTATUS *)(v81 + 48);
      LOBYTE(v25) = 1;
      CcCopyReadEx(
        v8,
        &v63,
        v28,
        v25,
        v80 + (unsigned int)(v63 - **(_DWORD **)&Size[1]),
        v81 + 48,
        *(_QWORD *)(v81 + 152));
      v36 = (unsigned int)*v32;
      if ( (int)v36 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v36 < 0xFFFFFFED
          && (_DWORD)v36 != -1073741802
          && (_DWORD)v36 != -1073741807
          && (unsigned int)(v36 + 2147483643) > 1
          && (_DWORD)v36 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v36, 3413296);
        }
        ExRaiseStatus(*v32);
      }
      if ( v13 )
      {
        NtfsReleasePagingResourcePriv(v33, *(_QWORD *)(v13 + 184), v34, v35);
        v13 = 0;
        v76 = 0;
      }
      v20 = v63 + v28;
      v63 = v20;
      v21 -= v28;
      goto LABEL_47;
    }
    v26 = *(_QWORD *)v24;
    if ( *(_QWORD *)v24 > (unsigned __int64)MatchData )
    {
      v28 = ((_DWORD)v26 << 12) - v63;
      goto LABEL_32;
    }
    v27 = v24[6];
    if ( v27 + v26 >= (unsigned __int64)MatchData + DWORD2(v90) )
      break;
    v20 = (v27 + v26) << 12;
    v63 = v20;
    v21 = v11 + **(_DWORD **)&Size[1] - (((_DWORD)v26 + (_DWORD)v27) << 12);
LABEL_47:
    v64 = v21;
    v22 = v20;
    v17 = v79;
    v18 = v74;
  }
  while ( v21 );
  v18 = v74;
LABEL_49:
  v37 = **(_QWORD **)&Size[1];
  v63 = **(_QWORD **)&Size[1];
  v64 = v11;
  do
  {
    if ( ((v37 ^ (v11 + v37 - 1)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
      v38 = 0x40000 - (v63 & 0x3FFFF);
    else
      v38 = v11;
    v77 = 0;
    v39 = v18;
    do
    {
      *(_QWORD *)&MatchData = v63 >> 12;
      v40 = v38;
      DWORD2(v90) = (v38 + (v63 & 0xFFF) + 4095) >> 12;
      RestartKey = 0;
      ExAcquireFastMutex((PFAST_MUTEX)v39[32]);
      for ( i = 0; (v39[1] & 0x800) == 0; i = 1 )
      {
        v78 = RtlEnumerateGenericTableLikeADirectory(
                (PRTL_AVL_TABLE)(v39 + 19),
                TxfMatchPageRange,
                &MatchData,
                i,
                &RestartKey,
                &DeleteCount,
                &MatchData);
        if ( !v78 )
          break;
        ExReleaseFastMutex((PFAST_MUTEX)v39[32]);
        v42 = v78;
        v43 = *v78 << 12;
        v71 = v43;
        v44 = *((_DWORD *)v78 + 6) << 12;
        v66 = v44;
        if ( v63 <= v43 )
        {
          v46 = v43;
          v45 = v44;
        }
        else
        {
          v45 = v43 - v63 + v44;
          v44 = v45;
          v66 = v45;
          v43 = v63;
          v71 = v63;
          v46 = v63;
        }
        if ( v40 + v63 < v46 + v45 )
        {
          v44 = v63 - v46 + v38;
          v66 = v44;
          v45 = v44;
        }
        do
        {
          v83 = 0;
          v47 = 4096 - (v43 & 0xFFF);
          LODWORD(v68) = v47;
          if ( v47 > v45 )
            v47 = v44;
          LODWORD(v71) = v47;
          LODWORD(v68) = v47;
          v86 = 1LL << ((v46 >> 12) & 0x3F);
          if ( (v86 & v77) == 0 )
          {
            v68 = v80 + (unsigned int)(v43 - **(_DWORD **)&Size[1]);
            v48 = v46 - ((unsigned int)*v42 << 12);
            v85 = v48;
            v84 = v48;
            v83 = v48 + (v42[1] << 12);
            v49 = v65;
            v61 = NtfsAcquireScbPagingResourceShared(a1, *v65);
            if ( a1 )
            {
              v69 = 0;
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                v69 = j;
                if ( (unsigned int)j >= 2 )
                  break;
                v52 = *(_QWORD *)(a1 + 8 * j + 48);
                if ( !v52 || v52 == *(_QWORD *)(*v49 + 184LL) )
                {
                  *(_QWORD *)(a1 + 8LL * (unsigned int)j + 48) = *(_QWORD *)(*v49 + 184LL);
                  break;
                }
              }
            }
            v53 = (NTSTATUS *)(v81 + 48);
            LOBYTE(v50) = 1;
            CcCopyReadEx(*(_QWORD *)(*v65 + 280LL), &v83, (unsigned int)v71, v50, v68, v81 + 48, *(_QWORD *)(v81 + 152));
            v54 = (unsigned int)*v53;
            if ( (int)v54 < 0 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v54 < 0xFFFFFFED
                && (_DWORD)v54 != -1073741802
                && (_DWORD)v54 != -1073741807
                && (unsigned int)(v54 + 2147483643) > 1
                && (_DWORD)v54 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, v54, 3413650);
              }
              ExRaiseStatus(*v53);
            }
            if ( v61 )
            {
              if ( a1 )
              {
                v70 = 0;
                for ( k = 0; ; ++k )
                {
                  v70 = k;
                  if ( k >= 2 )
                    break;
                  if ( *(_QWORD *)(a1 + 8LL * k + 48) == *(_QWORD *)(*v65 + 184LL) )
                    *(_QWORD *)(a1 + 8LL * k + 48) = 0;
                }
              }
              ExReleaseResourceLite(*(PERESOURCE *)(*v65 + 16LL));
            }
            v56 = (_DWORD)v78 + 36 + 16 * ((unsigned int)v85 >> 12);
            v47 = v71;
            LOBYTE(v56) = v62;
            TxfReplaceDisplacedBytes(
              v68,
              v56,
              v85 & 0xFFFF0FFF,
              (unsigned __int16)v71,
              (__int64)&v78[2 * ((unsigned int)v85 >> 12) + 4] + 4);
            v77 |= v86;
            v42 = v78;
          }
          v43 += v47;
          v46 = v43;
          v71 = v43;
          v44 -= v47;
          v66 = v44;
          v45 = v44;
        }
        while ( v44 );
        DWORD2(v90) += MatchData - *(_DWORD *)v42;
        *(_QWORD *)&MatchData = *v42;
        ExAcquireFastMutex((PFAST_MUTEX)v39[32]);
        v40 = v38;
      }
      ExReleaseFastMutex((PFAST_MUTEX)v39[32]);
      if ( v39[14] )
        break;
      v39 = (_QWORD *)v39[5];
    }
    while ( v39 );
    v37 = v40 + v63;
    v63 += v40;
    v11 -= v38;
    v64 = v11;
    v18 = v74;
  }
  while ( v11 );
  v57 = v72;
  v13 = v76;
  v17 = v79;
  v58 = Size[0];
LABEL_97:
  v59 = v17 + 200;
  if ( (*(_DWORD *)(v17 + 200) & 0x400000) != 0 )
  {
    *(_QWORD *)(v17 + 504) = 0;
    ClearFlagInterlocked(v59, 0x400000);
  }
  if ( v13 )
    NtfsReleasePagingResourcePriv(v59, *(_QWORD *)(v13 + 184), v14, v17);
  if ( v82 )
    TxfDereferenceBackupAttributeForTxfVscb();
  if ( v58 )
    memset((void *)(v80 + v57), 0, v58);
  v60 = v81;
  *(_DWORD *)(v81 + 48) = 0;
  *(_QWORD *)(v60 + 56) = v57 + v58;
}

```

## disassembly

```asm
0x140285a50  mov     r11, rsp
0x140285a53  push    rbx
0x140285a54  push    rsi
0x140285a55  push    rdi
0x140285a56  push    r12
0x140285a58  push    r13
0x140285a5a  push    r14
0x140285a5c  push    r15
0x140285a5e  sub     rsp, 150h
0x140285a65  mov     rax, cs:__security_cookie
0x140285a6c  xor     rax, rsp
0x140285a6f  mov     [rsp+188h+var_48], rax
0x140285a77  mov     rbx, r9
0x140285a7a  mov     r15, r8
0x140285a7d  mov     rsi, rdx
0x140285a80  mov     [rsp+188h+var_C0], rdx
0x140285a88  mov     r14, rcx
0x140285a8b  mov     [rsp+188h+var_88], rcx
0x140285a93  mov     rax, [rsp+188h+arg_20]
0x140285a9b  mov     qword ptr [rsp+188h+Size+4], rax
0x140285aa3  mov     r12d, [rsp+188h+arg_28]
0x140285aab  mov     [r11-108h], r12d
0x140285ab2  xor     edx, edx
0x140285ab4  mov     [rsp+188h+var_124], edx
0x140285ab8  xorps   xmm0, xmm0
0x140285abb  xor     eax, eax
0x140285abd  movups  xmmword ptr [r11-80h], xmm0
0x140285ac2  movups  xmmword ptr [r11-70h], xmm0
0x140285ac7  movups  xmmword ptr [r11-60h], xmm0
0x140285acc  mov     [r11-50h], eax
0x140285ad0  mov     [r11-0F0h], rdx
0x140285ad7  mov     [rsp+188h+var_140], rdx
0x140285adc  mov     dword ptr [rsp+188h+Size], edx
0x140285ae3  mov     rdi, [r8+18h]
0x140285ae7  mov     [r11-0F8h], rbx
0x140285aee  mov     [rsp+188h+var_148], dl
0x140285af2  mov     rax, [rdi+0B8h]
0x140285af9  mov     rax, [rax+140h]
0x140285b00  add     rax, 118h
0x140285b06  mov     [rsp+188h+var_130], rax
0x140285b0b  mov     r13d, edx
0x140285b0e  mov     [r11-0E8h], rdx
0x140285b15  mov     [rsp+188h+var_B8], rdx
0x140285b1d  mov     edx, 40000010h
0x140285b22  mov     rcx, rsi
0x140285b25  call    NtfsMapUserBuffer
0x140285b2a  mov     [rsp+188h+var_C8], rax
0x140285b32  cmp     [rsi+8], r13
0x140285b36  jnz     short loc_140285B41
0x140285b38  mov     dl, [rsi+40h]
0x140285b3b  mov     [rsp+188h+var_147], dl
0x140285b3f  jmp     short loc_140285B46
0x140285b41  mov     [rsp+188h+var_147], r13b
0x140285b46  mov     rax, [rdi+210h]
0x140285b4d  test    dword ptr [rax+18h], 1000h
0x140285b54  jz      short loc_140285B69
0x140285b56  mov     r8d, [rsp+188h+arg_30]
0x140285b5e  mov     rdx, rdi
0x140285b61  mov     rcx, r14
0x140285b64  call    TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept
0x140285b69  cmp     [rsp+188h+arg_30], r13d
0x140285b71  jnz     short loc_140285B7A
0x140285b73  mov     r15, [rdi+118h]
0x140285b7a  mov     rdi, [rbx+70h]
0x140285b7e  test    rdi, rdi
0x140285b81  jz      short loc_140285BDE
0x140285b83  xor     sil, sil
0x140285b86  mov     rax, [rdi+210h]
0x140285b8d  mov     rcx, [rax+40h]
0x140285b91  mov     dl, 1; Wait
0x140285b93  mov     rcx, [rcx+88h]; Resource
0x140285b9a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140285ba1  nop     dword ptr [rax+rax+00h]
0x140285ba6  cmp     rdi, [rbx+70h]
0x140285baa  jnz     short loc_140285BBB
0x140285bac  mov     rcx, rdi
0x140285baf  call    TxfIncrementBackupAttributeDependencies
0x140285bb4  mov     r15, [rbx+78h]
0x140285bb8  mov     sil, 1
0x140285bbb  mov     rax, [rdi+210h]
0x140285bc2  mov     rcx, [rax+40h]
0x140285bc6  mov     rcx, [rcx+88h]; Resource
0x140285bcd  call    cs:__imp_ExReleaseResourceLite
0x140285bd4  nop     dword ptr [rax+rax+00h]
0x140285bd9  test    sil, sil
0x140285bdc  jnz     short loc_140285BE9
0x140285bde  mov     rbx, [rbx+28h]
0x140285be2  test    rbx, rbx
0x140285be5  jnz     short loc_140285B7A
0x140285be7  jmp     short loc_140285BF9
0x140285be9  mov     [rsp+188h+arg_30], r13d
0x140285bf1  mov     [rsp+188h+var_B8], rbx
0x140285bf9  mov     r9, [r15+18h]
0x140285bfd  mov     [rsp+188h+var_D0], r9
0x140285c05  mov     [rsp+188h+var_90], r9
0x140285c0d  mov     rdi, [rsp+188h+var_F8]
0x140285c15  mov     rax, [rdi+108h]
0x140285c1c  mov     rdx, [rax+10h]
0x140285c20  mov     rax, qword ptr [rsp+188h+Size+4]
0x140285c28  mov     rcx, [rax]
0x140285c2b  cmp     rcx, rdx
0x140285c2e  jge     loc_1402863BA
0x140285c34  lea     r8, [rcx+r12]
0x140285c38  cmp     r8, rdx
0x140285c3b  jle     short loc_140285C54
0x140285c3d  mov     eax, r8d
0x140285c40  sub     eax, edx
0x140285c42  mov     dword ptr [rsp+188h+Size], eax
0x140285c49  sub     r12d, eax
0x140285c4c  mov     [rsp+188h+var_108], r12d
0x140285c54  mov     r10d, 0FFFh
0x140285c5a  cmp     [rsp+188h+arg_30], 0
0x140285c62  jnz     loc_140285EFB
0x140285c68  mov     [rsp+188h+var_140], rcx
0x140285c6d  mov     ebx, r12d
0x140285c70  mov     [rsp+188h+var_138], ebx
0x140285c74  mov     rdx, rcx
0x140285c77  mov     r8, [r9+20h]
0x140285c7b  mov     eax, ebx
0x140285c7d  add     rax, rdx
0x140285c80  cmp     rax, r8
0x140285c83  jbe     short loc_140285C97
0x140285c85  cmp     rdx, r8
0x140285c88  jnb     loc_140285EFB
0x140285c8e  mov     ebx, r8d
0x140285c91  sub     ebx, ecx
0x140285c93  mov     [rsp+188h+var_138], ebx
0x140285c97  mov     rax, rdx
0x140285c9a  shr     rax, 0Ch
0x140285c9e  mov     qword ptr [rsp+188h+MatchData], rax
0x140285ca6  and     rdx, r10
0x140285ca9  mov     ecx, ebx
0x140285cab  add     rdx, 0FFFh
0x140285cb2  add     rcx, rdx
0x140285cb5  shr     rcx, 0Ch
0x140285cb9  mov     [rsp+188h+var_68], ecx
0x140285cc0  mov     [rsp+188h+var_F0], 0
0x140285ccc  mov     rcx, [rdi+100h]; FastMutex
0x140285cd3  call    cs:__imp_ExAcquireFastMutex
0x140285cda  nop     dword ptr [rax+rax+00h]
0x140285cdf  test    dword ptr [rdi+8], 800h
0x140285ce6  jnz     short loc_140285D36
0x140285ce8  lea     rcx, [rdi+98h]; Table
0x140285cef  lea     rax, [rsp+188h+MatchData]
0x140285cf7  mov     [rsp+188h+Buffer], rax; Buffer
0x140285cfc  lea     rax, [rsp+188h+var_124]
0x140285d01  mov     [rsp+188h+DeleteCount], rax; DeleteCount
0x140285d06  lea     rax, [rsp+188h+var_F0]
0x140285d0e  mov     [rsp+188h+RestartKey], rax; RestartKey
0x140285d13  xor     r9d, r9d; NextFlag
0x140285d16  lea     r8, [rsp+188h+MatchData]; MatchData
0x140285d1e  lea     rdx, TxfMatchPageRange; MatchFunction
0x140285d25  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x140285d2c  nop     dword ptr [rax+rax+00h]
0x140285d31  mov     rsi, rax
0x140285d34  jmp     short loc_140285D38
0x140285d36  xor     esi, esi
0x140285d38  mov     rcx, [rdi+100h]; FastMutex
0x140285d3f  call    cs:__imp_ExReleaseFastMutex
0x140285d46  nop     dword ptr [rax+rax+00h]
0x140285d4b  test    rsi, rsi
0x140285d4e  jz      short loc_140285DA8
0x140285d50  mov     rdi, [rsi]
0x140285d53  cmp     rdi, qword ptr [rsp+188h+MatchData]
0x140285d5b  ja      short loc_140285D9F
0x140285d5d  mov     edx, [rsi+18h]
0x140285d60  lea     rcx, [rdx+rdi]
0x140285d64  mov     eax, [rsp+188h+var_68]
0x140285d6b  add     rax, qword ptr [rsp+188h+MatchData]
0x140285d73  cmp     rcx, rax
0x140285d76  jnb     loc_140285EED
0x140285d7c  shl     rcx, 0Ch
0x140285d80  mov     [rsp+188h+var_140], rcx
0x140285d85  lea     eax, [rdi+rdx]
0x140285d88  shl     eax, 0Ch
0x140285d8b  mov     rdx, qword ptr [rsp+188h+Size+4]
0x140285d93  mov     ebx, [rdx]
0x140285d95  sub     ebx, eax
0x140285d97  add     ebx, r12d
0x140285d9a  jmp     loc_140285EC6
0x140285d9f  shl     edi, 0Ch
0x140285da2  sub     edi, dword ptr [rsp+188h+var_140]
0x140285da6  jmp     short loc_140285DAA
0x140285da8  mov     edi, ebx
0x140285daa  test    r13, r13
0x140285dad  jnz     short loc_140285DF4
0x140285daf  mov     rsi, [rsp+188h+var_D0]
0x140285db7  mov     rax, [rsi+0B8h]
0x140285dbe  mov     rcx, [rax+70h]; Resource
0x140285dc2  test    rcx, rcx
0x140285dc5  jz      short loc_140285DF4
0x140285dc7  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140285dce  nop     dword ptr [rax+rax+00h]
0x140285dd3  test    eax, eax
0x140285dd5  jnz     short loc_140285DF4
0x140285dd7  mov     r8b, 1
0x140285dda  mov     rdx, [rsi+0B8h]
0x140285de1  mov     rcx, r14
0x140285de4  call    NtfsAcquirePagingResourceExclusive
0x140285de9  mov     r13, rsi
0x140285dec  mov     [rsp+188h+var_E8], rsi
0x140285df4  mov     rdx, [rsp+188h+var_C0]
0x140285dfc  lea     rsi, [rdx+30h]
0x140285e00  mov     eax, dword ptr [rsp+188h+var_140]
0x140285e04  mov     rcx, qword ptr [rsp+188h+Size+4]
0x140285e0c  sub     eax, [rcx]
0x140285e0e  mov     ecx, eax
0x140285e10  add     rcx, [rsp+188h+var_C8]
0x140285e18  mov     rax, [rdx+98h]
0x140285e1f  mov     [rsp+188h+Buffer], rax
0x140285e24  mov     [rsp+188h+DeleteCount], rsi
0x140285e29  mov     [rsp+188h+RestartKey], rcx
0x140285e2e  mov     r9b, 1
0x140285e31  mov     r8d, edi
0x140285e34  lea     rdx, [rsp+188h+var_140]
0x140285e39  mov     rcx, r15
0x140285e3c  call    cs:__imp_CcCopyReadEx
0x140285e43  nop     dword ptr [rax+rax+00h]
0x140285e48  mov     edx, [rsi]
0x140285e4a  test    edx, edx
0x140285e4c  jns     short loc_140285E9C
0x140285e4e  mov     al, cs:NtfsStatusDebugFlags
0x140285e54  test    al, al
0x140285e56  jz      short loc_140285E8E
0x140285e58  cmp     edx, 0FFFFFFEDh
0x140285e5b  jnb     short loc_140285E8E
0x140285e5d  cmp     edx, 0C0000016h
0x140285e63  jz      short loc_140285E8E
0x140285e65  cmp     edx, 0C0000011h
0x140285e6b  jz      short loc_140285E8E
0x140285e6d  lea     eax, [rdx+7FFFFFFBh]
0x140285e73  cmp     eax, 1
0x140285e76  jbe     short loc_140285E8E
0x140285e78  cmp     edx, 0C00000D8h
0x140285e7e  jz      short loc_140285E8E
0x140285e80  mov     r8d, 341530h
0x140285e86  mov     rcx, r14
0x140285e89  call    NtfsStatusTraceAndDebugInternal
0x140285e8e  mov     ecx, [rsi]; Status
0x140285e90  call    cs:__imp_ExRaiseStatus
0x140285e9c  test    r13, r13
0x140285e9f  jz      short loc_140285EB8
0x140285ea1  mov     rdx, [r13+0B8h]
0x140285ea8  call    NtfsReleasePagingResourcePriv
0x140285ead  xor     r13d, r13d
0x140285eb0  mov     [rsp+188h+var_E8], r13
0x140285eb8  mov     ecx, edi
0x140285eba  add     rcx, [rsp+188h+var_140]
0x140285ebf  mov     [rsp+188h+var_140], rcx
0x140285ec4  sub     ebx, edi
0x140285ec6  mov     [rsp+188h+var_138], ebx
0x140285eca  mov     rdx, rcx
0x140285ecd  test    ebx, ebx
0x140285ecf  mov     r9, [rsp+188h+var_D0]
0x140285ed7  mov     r10d, 0FFFh
0x140285edd  mov     rdi, [rsp+188h+var_F8]
0x140285ee5  jnz     loc_140285C77
0x140285eeb  jmp     short loc_140285EF3
0x140285eed  mov     r10d, 0FFFh
0x140285ef3  mov     rdi, [rsp+188h+var_F8]
0x140285efb  mov     rax, qword ptr [rsp+188h+Size+4]
0x140285f03  mov     rdx, [rax]
0x140285f06  mov     [rsp+188h+var_140], rdx
0x140285f0b  mov     [rsp+188h+var_138], r12d
0x140285f10  mov     eax, r12d
0x140285f13  lea     rcx, [rdx-1]
0x140285f17  add     rcx, rax
0x140285f1a  xor     rcx, rdx
0x140285f1d  test    rcx, 0FFFFFFFFFFFC0000h
0x140285f24  jz      short loc_140285F3A
0x140285f26  mov     eax, dword ptr [rsp+188h+var_140]
0x140285f2a  and     eax, 3FFFFh
0x140285f2f  mov     r13d, 40000h
0x140285f35  sub     r13d, eax
0x140285f38  jmp     short loc_140285F3D
0x140285f3a  mov     r13d, r12d
0x140285f3d  mov     [rsp+188h+var_E0], 0
0x140285f49  mov     rbx, rdi
0x140285f4c  mov     rcx, [rsp+188h+var_140]
0x140285f51  mov     rax, rcx
0x140285f54  shr     rax, 0Ch
0x140285f58  mov     qword ptr [rsp+188h+MatchData], rax
0x140285f60  mov     esi, r13d
0x140285f63  and     rcx, r10
0x140285f66  lea     rax, [rcx+0FFFh]
0x140285f6d  add     rax, rsi
0x140285f70  shr     rax, 0Ch
0x140285f74  mov     [rsp+188h+var_68], eax
0x140285f7b  mov     [rsp+188h+var_F0], 0
0x140285f87  mov     rcx, [rbx+100h]; FastMutex
0x140285f8e  call    cs:__imp_ExAcquireFastMutex
0x140285f95  nop     dword ptr [rax+rax+00h]
0x140285f9a  xor     r9d, r9d; NextFlag
0x140285f9d  test    dword ptr [rbx+8], 800h
0x140285fa4  jnz     loc_140286344
0x140285faa  lea     rcx, [rbx+98h]; Table
0x140285fb1  lea     rax, [rsp+188h+MatchData]
0x140285fb9  mov     [rsp+188h+Buffer], rax; Buffer
0x140285fbe  lea     rax, [rsp+188h+var_124]
0x140285fc3  mov     [rsp+188h+DeleteCount], rax; DeleteCount
  ... truncated ...
```
