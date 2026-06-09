# CLKRLinearHashTable::_Contract(void)

- ea: `0x180077980`
- end: `0x180077d60`
- name: `?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180074f70`
- `0x1800751b0`

## callees

- `0x180076f60`
- `0x180076ff0`
- `0x180077040`
- `0x1800772c0`
- `0x180077980`
- `0x180077d60`
- `0x1800838f0`
- `0x1800b3f20`
- `0x1800b44b0`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800779dc`
- `KERNEL32!GetCurrentThreadId` at `0x1800779ed`
- `KERNEL32!GetCurrentThreadId` at `0x180077a69`
- `KERNEL32!GetCurrentThreadId` at `0x180077abd`
- `KERNEL32!GetCurrentThreadId` at `0x1800779dc`
- `KERNEL32!GetCurrentThreadId` at `0x1800779ed`
- `KERNEL32!GetCurrentThreadId` at `0x180077a69`
- `KERNEL32!GetCurrentThreadId` at `0x180077abd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180077bef`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180077bef`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_Contract(__int64 a1)
{
  volatile signed __int32 *v1; // rsi
  signed __int32 v3; // edx
  DWORD v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // ecx
  char v8; // cl
  unsigned int v9; // r8d
  __int64 v10; // rcx
  __int64 v11; // r13
  bool v12; // cl
  char v13; // cl
  __int64 v14; // rax
  __int64 v15; // rcx
  volatile signed __int32 *v16; // r12
  bool v17; // cl
  _OWORD *v18; // r15
  int v19; // ebp
  __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  volatile signed __int32 *i; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  struct CLKRLinearHashTable::CNodeClump *NodeClump; // r14
  struct CLKRLinearHashTable::CNodeClump *v27; // rax
  int v28; // ecx
  int v29; // eax
  int v30; // edx
  bool v31; // zf
  signed __int32 v32; // edx
  __int64 result; // rax
  _QWORD *v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // ecx
  unsigned int v37; // ebp
  unsigned int v38; // ebp
  __int64 v39; // r15
  struct CLKRLinearHashTable::CDirEntry *SegmentDirectory; // rax
  struct CLKRLinearHashTable::CDirEntry *v41; // r13
  __int64 v42; // r8
  unsigned int j; // edx
  __int64 v44; // rcx
  int v45; // edx
  signed __int32 v46; // r8d
  _OWORD v47[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v48; // [rsp+50h] [rbp-38h]

  v1 = (volatile signed __int32 *)(a1 + 8);
  if ( !*(_DWORD *)(a1 + 12) && !(unsigned __int16)*v1 )
  {
    v3 = *v1;
    if ( v3 == _InterlockedCompareExchange(v1, (v3 + 0x10000) | 0xFFFF, v3) )
    {
      v4 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_5:
      _InterlockedExchange(v1 + 1, v4);
      goto LABEL_9;
    }
  }
  if ( ((GetCurrentThreadId() ^ *(_DWORD *)(a1 + 12)) & 0xFFFFFFFC) == 0 )
  {
    v4 = *((_DWORD *)v1 + 1) + 1;
    goto LABEL_5;
  }
  VonetLocks::CReaderWriterLock3::_WriteLockSpin((VonetLocks::CReaderWriterLock3 *)v1);
LABEL_9:
  v5 = *(_DWORD *)(a1 + 80);
  if ( v5 )
  {
    v6 = v5 - 1;
  }
  else
  {
    v7 = --*(_DWORD *)(a1 + 96);
    *(_DWORD *)(a1 + 72) >>= 1;
    v6 = (1 << v7) - 1;
    *(_DWORD *)(a1 + 76) >>= 1;
  }
  v8 = *(_BYTE *)(a1 + 52);
  v9 = *(_DWORD *)(a1 + 108);
  *(_DWORD *)(a1 + 80) = v6;
  v10 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * ((unsigned __int64)--v9 >> v8));
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, v9 & *(_DWORD *)(a1 + 60));
  if ( *(_DWORD *)v11 )
    v12 = 0;
  else
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)v11, GetCurrentThreadId(), 0) == 0;
  if ( !v12 )
    VonetLocks::CSmallSpinLock::_LockSpin((VonetLocks::CSmallSpinLock *)v11);
  v13 = *(_BYTE *)(a1 + 52);
  v14 = *(_QWORD *)(a1 + 88);
  --*(_DWORD *)(a1 + 108);
  v15 = *(_QWORD *)(v14 + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 80) >> v13));
  v16 = (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 40LL))(
                                     v15,
                                     (unsigned int)(*(_DWORD *)(a1 + 80) & *(_DWORD *)(a1 + 60)));
  if ( *v16 )
    v17 = 0;
  else
    v17 = _InterlockedCompareExchange(v16, GetCurrentThreadId(), 0) == 0;
  if ( !v17 )
    VonetLocks::CSmallSpinLock::_LockSpin((VonetLocks::CSmallSpinLock *)v16);
  v18 = (_OWORD *)(v11 + 8);
  v19 = 0;
  v20 = v11 + 8;
  if ( v11 != -8 )
  {
    do
    {
      v21 = (_QWORD *)(v20 + 24);
      v22 = 4;
      do
      {
        if ( *v21 )
          ++v19;
        ++v21;
        --v22;
      }
      while ( v22 );
      v20 = *(_QWORD *)(v20 + 16);
    }
    while ( v20 );
  }
  for ( i = v16 + 2; i; i = (volatile signed __int32 *)*((_QWORD *)i + 2) )
  {
    v24 = i + 6;
    v25 = 4;
    do
    {
      if ( !*v24 )
        --v19;
      ++v24;
      --v25;
    }
    while ( v25 );
  }
  NodeClump = 0;
  if ( v19 > 0 )
  {
    NodeClump = CLKRLinearHashTable::_AllocateNodeClump();
    if ( !NodeClump )
    {
LABEL_41:
      v28 = *(_DWORD *)(a1 + 96);
      if ( ++*(_DWORD *)(a1 + 80) == 1 << v28 )
      {
        *(_DWORD *)(a1 + 80) = 0;
        *(_DWORD *)(a1 + 96) = v28 + 1;
        v29 = (2 * *(_DWORD *)(a1 + 72)) | 1;
        *(_DWORD *)(a1 + 72) = v29;
        *(_DWORD *)(a1 + 76) = (2 * v29) | 1;
      }
      ++*(_DWORD *)(a1 + 108);
      _InterlockedExchange((volatile __int32 *)v11, 0);
      _InterlockedExchange(v16, 0);
      v30 = *((_DWORD *)v1 + 1) - 1;
      v31 = (((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v30 : 0) == 0;
      _InterlockedExchange(v1 + 1, ((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v30 : 0);
      if ( v31 )
      {
        _m_prefetchw((const void *)v1);
        do
          v32 = *v1;
        while ( v32 != _InterlockedCompareExchange(v1, (v32 - 0x10000) & 0xFFFF0000, v32) );
      }
      return 4294967198LL;
    }
    if ( v19 > 4 )
    {
      v27 = CLKRLinearHashTable::_AllocateNodeClump();
      if ( !v27 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(NodeClump);
        else
          free(NodeClump);
        goto LABEL_41;
      }
      *((_QWORD *)NodeClump + 2) = v27;
    }
  }
  v34 = (_QWORD *)(v11 + 32);
  v35 = 4;
  v47[0] = *v18;
  v47[1] = *(_OWORD *)(v11 + 24);
  v47[2] = *(_OWORD *)(v11 + 40);
  v48 = *(_QWORD *)(v11 + 56);
  *(_QWORD *)(v11 + 24) = 0;
  do
  {
    *(_DWORD *)v18 = 31678523;
    v18 = (_OWORD *)((char *)v18 + 4);
    *v34++ = 0;
    --v35;
  }
  while ( v35 );
  _InterlockedExchange((volatile __int32 *)v11, 0);
  v36 = *(_DWORD *)(a1 + 108);
  if ( (v36 & *(_DWORD *)(a1 + 60)) == 0 )
  {
    CLKRLinearHashTable::_FreeSegment(*(struct CLKRLinearHashTable::CSegment **)(*(_QWORD *)(a1 + 88)
                                                                               + 8
                                                                               * ((unsigned __int64)v36 >> *(_BYTE *)(a1 + 52))));
    *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 108) >> *(_BYTE *)(a1 + 52))) = 0;
  }
  v37 = *(_DWORD *)(a1 + 100);
  if ( *(_DWORD *)(a1 + 108) <= (v37 * *(_DWORD *)(a1 + 56)) >> 1 && v37 > 8 )
  {
    v38 = v37 >> 1;
    v39 = v38;
    SegmentDirectory = CLKRLinearHashTable::_AllocateSegmentDirectory(v38);
    v41 = SegmentDirectory;
    if ( SegmentDirectory )
    {
      if ( v38 )
      {
        v42 = 0;
        do
        {
          *(_QWORD *)((char *)SegmentDirectory + v42) = *(_QWORD *)(v42 + *(_QWORD *)(a1 + 88));
          v42 += 8;
          --v39;
        }
        while ( v39 );
      }
      for ( j = 0; j < *(_DWORD *)(a1 + 100); *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v44) = 0 )
        v44 = j++;
      CLKRLinearHashTable::_FreeSegmentDirectory(*(struct CLKRLinearHashTable::CDirEntry **)(a1 + 88));
      *(_QWORD *)(a1 + 88) = v41;
      *(_DWORD *)(a1 + 100) = v38;
    }
  }
  v45 = *((_DWORD *)v1 + 1) - 1;
  v31 = (((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v45 : 0) == 0;
  _InterlockedExchange(v1 + 1, ((*((_BYTE *)v1 + 4) - 1) & 3) != 0 ? v45 : 0);
  if ( v31 )
  {
    _m_prefetchw((const void *)v1);
    do
      v46 = *v1;
    while ( v46 != _InterlockedCompareExchange(v1, (v46 - 0x10000) & 0xFFFF0000, v46) );
  }
  result = ((__int64 (__fastcall *)(__int64, volatile signed __int32 *, _OWORD *, struct CLKRLinearHashTable::CNodeClump *))CLKRLinearHashTable::_MergeRecordSets)(
             a1,
             v16,
             v47,
             NodeClump);
  _InterlockedExchange(v16, 0);
  return result;
}

```

## disassembly

```asm
0x180077980  mov     [rsp+arg_8], rbx
0x180077985  mov     [rsp+arg_10], rbp
0x18007798a  mov     [rsp+arg_18], rsi
0x18007798f  push    rdi
0x180077990  push    r12
0x180077992  push    r13
0x180077994  push    r14
0x180077996  push    r15
0x180077998  sub     rsp, 60h
0x18007799c  mov     rax, cs:__security_cookie
0x1800779a3  xor     rax, rsp
0x1800779a6  mov     [rsp+88h+var_30], rax
0x1800779ab  xor     edi, edi
0x1800779ad  lea     rsi, [rcx+8]
0x1800779b1  mov     eax, [rsi+4]
0x1800779b4  mov     rbx, rcx
0x1800779b7  lea     r14d, [rdi+1]
0x1800779bb  test    eax, eax
0x1800779bd  jnz     short loc_1800779ED
0x1800779bf  mov     edx, [rsi]
0x1800779c1  test    dx, dx
0x1800779c4  jnz     short loc_1800779ED
0x1800779c6  lea     ecx, [rdx+10000h]
0x1800779cc  mov     eax, edx
0x1800779ce  or      ecx, 0FFFFh
0x1800779d4  lock cmpxchg [rsi], ecx
0x1800779d8  cmp     edx, eax
0x1800779da  jnz     short loc_1800779ED
0x1800779dc  call    cs:GetCurrentThreadId
0x1800779e2  and     eax, 0FFFFFFFDh
0x1800779e5  or      eax, r14d
0x1800779e8  xchg    eax, [rsi+4]
0x1800779eb  jmp     short loc_180077A10
0x1800779ed  call    cs:GetCurrentThreadId
0x1800779f3  mov     ecx, [rsi+4]
0x1800779f6  xor     ecx, eax
0x1800779f8  test    ecx, 0FFFFFFFCh
0x1800779fe  jnz     short loc_180077A08
0x180077a00  mov     eax, [rsi+4]
0x180077a03  add     eax, r14d
0x180077a06  jmp     short loc_1800779E8
0x180077a08  mov     rcx, rsi; this
0x180077a0b  call    ?_WriteLockSpin@CReaderWriterLock3@VonetLocks@@AEAAXXZ; VonetLocks::CReaderWriterLock3::_WriteLockSpin(void)
0x180077a10  mov     eax, [rbx+50h]
0x180077a13  or      ebp, 0FFFFFFFFh
0x180077a16  test    eax, eax
0x180077a18  jz      short loc_180077A1E
0x180077a1a  dec     eax
0x180077a1c  jmp     short loc_180077A32
0x180077a1e  add     [rbx+60h], ebp
0x180077a21  mov     eax, r14d
0x180077a24  mov     ecx, [rbx+60h]
0x180077a27  shr     dword ptr [rbx+48h], 1
0x180077a2a  shl     eax, cl
0x180077a2c  sub     eax, r14d
0x180077a2f  shr     dword ptr [rbx+4Ch], 1
0x180077a32  mov     cl, [rbx+34h]
0x180077a35  mov     r8d, [rbx+6Ch]
0x180077a39  mov     [rbx+50h], eax
0x180077a3c  sub     r8d, r14d
0x180077a3f  mov     rax, [rbx+58h]
0x180077a43  mov     edx, r8d
0x180077a46  shr     rdx, cl
0x180077a49  mov     rcx, [rax+rdx*8]
0x180077a4d  mov     edx, [rbx+3Ch]
0x180077a50  and     edx, r8d
0x180077a53  mov     rax, [rcx]
0x180077a56  mov     rax, [rax+28h]
0x180077a5a  call    cs:__guard_dispatch_icall_fptr
0x180077a60  mov     r13, rax
0x180077a63  mov     ecx, [rax]
0x180077a65  test    ecx, ecx
0x180077a67  jnz     short loc_180077A7E
0x180077a69  call    cs:GetCurrentThreadId
0x180077a6f  mov     ecx, eax
0x180077a71  xor     eax, eax
0x180077a73  lock cmpxchg [r13+0], ecx
0x180077a79  setz    cl
0x180077a7c  jmp     short loc_180077A81
0x180077a7e  mov     cl, dil
0x180077a81  test    cl, cl
0x180077a83  jnz     short loc_180077A8D
0x180077a85  mov     rcx, r13; this
0x180077a88  call    ?_LockSpin@CSmallSpinLock@VonetLocks@@AEAAXXZ; VonetLocks::CSmallSpinLock::_LockSpin(void)
0x180077a8d  mov     cl, [rbx+34h]
0x180077a90  mov     rax, [rbx+58h]
0x180077a94  add     [rbx+6Ch], ebp
0x180077a97  mov     edx, [rbx+50h]
0x180077a9a  shr     rdx, cl
0x180077a9d  mov     rcx, [rax+rdx*8]
0x180077aa1  mov     edx, [rbx+3Ch]
0x180077aa4  and     edx, [rbx+50h]
0x180077aa7  mov     rax, [rcx]
0x180077aaa  mov     rax, [rax+28h]
0x180077aae  call    cs:__guard_dispatch_icall_fptr
0x180077ab4  mov     r12, rax
0x180077ab7  mov     ecx, [rax]
0x180077ab9  test    ecx, ecx
0x180077abb  jnz     short loc_180077AD2
0x180077abd  call    cs:GetCurrentThreadId
0x180077ac3  mov     ecx, eax
0x180077ac5  xor     eax, eax
0x180077ac7  lock cmpxchg [r12], ecx
0x180077acd  setz    cl
0x180077ad0  jmp     short loc_180077AD5
0x180077ad2  mov     cl, dil
0x180077ad5  test    cl, cl
0x180077ad7  jnz     short loc_180077AE1
0x180077ad9  mov     rcx, r12; this
0x180077adc  call    ?_LockSpin@CSmallSpinLock@VonetLocks@@AEAAXXZ; VonetLocks::CSmallSpinLock::_LockSpin(void)
0x180077ae1  lea     r15, [r13+8]
0x180077ae5  mov     ebp, edi
0x180077ae7  mov     rax, r15
0x180077aea  test    r15, r15
0x180077aed  jz      short loc_180077B12
0x180077aef  lea     rcx, [rax+18h]
0x180077af3  mov     edx, 4
0x180077af8  cmp     [rcx], rdi
0x180077afb  jz      short loc_180077B00
0x180077afd  add     ebp, r14d
0x180077b00  add     rcx, 8
0x180077b04  sub     rdx, r14
0x180077b07  jnz     short loc_180077AF8
0x180077b09  mov     rax, [rax+10h]
0x180077b0d  test    rax, rax
0x180077b10  jnz     short loc_180077AEF
0x180077b12  lea     rax, [r12+8]
0x180077b17  jmp     short loc_180077B37
0x180077b19  lea     rcx, [rax+18h]
0x180077b1d  mov     edx, 4
0x180077b22  cmp     [rcx], rdi
0x180077b25  jnz     short loc_180077B2A
0x180077b27  sub     ebp, r14d
0x180077b2a  add     rcx, 8
0x180077b2e  sub     rdx, r14
0x180077b31  jnz     short loc_180077B22
0x180077b33  mov     rax, [rax+10h]
0x180077b37  test    rax, rax
0x180077b3a  jnz     short loc_180077B19
0x180077b3c  mov     r14, rdi
0x180077b3f  test    ebp, ebp
0x180077b41  jle     loc_180077BFB
0x180077b47  call    ?_AllocateNodeClump@CLKRLinearHashTable@@CAQEAVCNodeClump@1@XZ; CLKRLinearHashTable::_AllocateNodeClump(void)
0x180077b4c  mov     r14, rax
0x180077b4f  test    rax, rax
0x180077b52  jz      short loc_180077B7B
0x180077b54  cmp     ebp, 4
0x180077b57  jle     loc_180077BFB
0x180077b5d  call    ?_AllocateNodeClump@CLKRLinearHashTable@@CAQEAVCNodeClump@1@XZ; CLKRLinearHashTable::_AllocateNodeClump(void)
0x180077b62  test    rax, rax
0x180077b65  jnz     loc_180077BF7
0x180077b6b  cmp     cs:dword_1802B0018, edi
0x180077b71  mov     rcx, r14; void *
0x180077b74  jz      short loc_180077BEF
0x180077b76  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180077b7b  mov     ecx, [rbx+60h]
0x180077b7e  mov     eax, 1
0x180077b83  inc     dword ptr [rbx+50h]
0x180077b86  shl     eax, cl
0x180077b88  cmp     [rbx+50h], eax
0x180077b8b  jnz     short loc_180077BA9
0x180077b8d  lea     eax, [rcx+1]
0x180077b90  mov     [rbx+50h], edi
0x180077b93  mov     [rbx+60h], eax
0x180077b96  mov     eax, [rbx+48h]
0x180077b99  add     eax, eax
0x180077b9b  or      eax, 1
0x180077b9e  mov     [rbx+48h], eax
0x180077ba1  add     eax, eax
0x180077ba3  or      eax, 1
0x180077ba6  mov     [rbx+4Ch], eax
0x180077ba9  inc     dword ptr [rbx+6Ch]
0x180077bac  mov     eax, edi
0x180077bae  xchg    eax, [r13+0]
0x180077bb2  xchg    edi, [r12]
0x180077bb6  mov     edx, [rsi+4]
0x180077bb9  dec     edx
0x180077bbb  mov     al, dl
0x180077bbd  and     al, 3
0x180077bbf  neg     al
0x180077bc1  sbb     ecx, ecx
0x180077bc3  and     ecx, edx
0x180077bc5  xchg    ecx, [rsi+4]
0x180077bc8  jnz     short loc_180077BE5
0x180077bca  prefetchw byte ptr [rsi]
0x180077bcd  mov     edx, [rsi]
0x180077bcf  mov     eax, edx
0x180077bd1  lea     ecx, [rdx-10000h]
0x180077bd7  and     ecx, 0FFFF0000h
0x180077bdd  lock cmpxchg [rsi], ecx
0x180077be1  cmp     edx, eax
0x180077be3  jnz     short loc_180077BCD
0x180077be5  mov     eax, 0FFFFFF9Eh
0x180077bea  jmp     loc_180077D35
0x180077bef  call    cs:free
0x180077bf5  jmp     short loc_180077B7B
0x180077bf7  mov     [r14+10h], rax
0x180077bfb  movups  xmm0, xmmword ptr [r15]
0x180077bff  lea     rax, [r15+18h]
0x180077c03  mov     ecx, 4
0x180077c08  movups  [rsp+88h+var_68], xmm0
0x180077c0d  movups  xmm1, xmmword ptr [r15+10h]
0x180077c12  movups  [rsp+88h+var_58], xmm1
0x180077c17  movups  xmm0, xmmword ptr [r15+20h]
0x180077c1c  movups  [rsp+88h+var_48], xmm0
0x180077c21  movsd   xmm1, qword ptr [r15+30h]
0x180077c27  movsd   [rsp+88h+var_38], xmm1
0x180077c2d  mov     [r15+10h], rdi
0x180077c31  mov     dword ptr [r15], 1E3603Bh
0x180077c38  lea     r15, [r15+4]
0x180077c3c  mov     [rax], rdi
0x180077c3f  lea     rax, [rax+8]
0x180077c43  sub     rcx, 1
0x180077c47  jnz     short loc_180077C31
0x180077c49  mov     eax, edi
0x180077c4b  xchg    eax, [r13+0]
0x180077c4f  mov     ecx, [rbx+6Ch]
0x180077c52  test    [rbx+3Ch], ecx
0x180077c55  jnz     short loc_180077C7D
0x180077c57  mov     eax, ecx
0x180077c59  mov     cl, [rbx+34h]
0x180077c5c  shr     rax, cl
0x180077c5f  mov     rcx, [rbx+58h]
0x180077c63  mov     rcx, [rcx+rax*8]; struct CLKRLinearHashTable::CSegment *
0x180077c67  call    ?_FreeSegment@CLKRLinearHashTable@@CA_NPEAVCSegment@1@@Z; CLKRLinearHashTable::_FreeSegment(CLKRLinearHashTable::CSegment *)
0x180077c6c  mov     edx, [rbx+6Ch]
0x180077c6f  mov     cl, [rbx+34h]
0x180077c72  mov     rax, [rbx+58h]
0x180077c76  shr     rdx, cl
0x180077c79  mov     [rax+rdx*8], rdi
0x180077c7d  mov     eax, [rbx+38h]
0x180077c80  mov     ebp, [rbx+64h]
0x180077c83  imul    eax, ebp
0x180077c86  shr     eax, 1
0x180077c88  cmp     [rbx+6Ch], eax
0x180077c8b  ja      short loc_180077CEB
0x180077c8d  cmp     ebp, 8
0x180077c90  jbe     short loc_180077CEB
0x180077c92  shr     ebp, 1
0x180077c94  mov     ecx, ebp; unsigned __int64
0x180077c96  mov     r15d, ebp
0x180077c99  call    ?_AllocateSegmentDirectory@CLKRLinearHashTable@@CAQEAVCDirEntry@1@_K@Z; CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)
0x180077c9e  mov     r13, rax
0x180077ca1  test    rax, rax
0x180077ca4  jz      short loc_180077CEB
0x180077ca6  test    ebp, ebp
0x180077ca8  jz      short loc_180077CC3
0x180077caa  mov     r8, rdi
0x180077cad  mov     rcx, [rbx+58h]
0x180077cb1  mov     rdx, [r8+rcx]
0x180077cb5  mov     [r8+rax], rdx
0x180077cb9  lea     r8, [r8+8]
0x180077cbd  sub     r15, 1
0x180077cc1  jnz     short loc_180077CAD
0x180077cc3  mov     edx, edi
0x180077cc5  cmp     [rbx+64h], edi
0x180077cc8  jbe     short loc_180077CDB
0x180077cca  mov     rax, [rbx+58h]
0x180077cce  mov     ecx, edx
0x180077cd0  inc     edx
0x180077cd2  mov     [rax+rcx*8], rdi
0x180077cd6  cmp     edx, [rbx+64h]
0x180077cd9  jb      short loc_180077CCA
0x180077cdb  mov     rcx, [rbx+58h]; struct CLKRLinearHashTable::CDirEntry *
0x180077cdf  call    ?_FreeSegmentDirectory@CLKRLinearHashTable@@CA_NPEAVCDirEntry@1@@Z; CLKRLinearHashTable::_FreeSegmentDirectory(CLKRLinearHashTable::CDirEntry *)
0x180077ce4  mov     [rbx+58h], r13
0x180077ce8  mov     [rbx+64h], ebp
0x180077ceb  mov     edx, [rsi+4]
0x180077cee  dec     edx
0x180077cf0  mov     al, dl
0x180077cf2  and     al, 3
0x180077cf4  neg     al
0x180077cf6  sbb     ecx, ecx
0x180077cf8  and     ecx, edx
0x180077cfa  xchg    ecx, [rsi+4]
0x180077cfd  jnz     short loc_180077D1E
0x180077cff  prefetchw byte ptr [rsi]
0x180077d02  mov     r8d, [rsi]
0x180077d05  mov     eax, r8d
0x180077d08  lea     edx, [r8-10000h]
0x180077d0f  and     edx, 0FFFF0000h
0x180077d15  lock cmpxchg [rsi], edx
0x180077d19  cmp     r8d, eax
0x180077d1c  jnz     short loc_180077D02
0x180077d1e  mov     r9, r14
0x180077d21  lea     r8, [rsp+88h+var_68]
0x180077d26  mov     rdx, r12
0x180077d29  mov     rcx, rbx
0x180077d2c  call    ?_MergeRecordSets@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEAVCBucket@1@PEAVCNodeClump@1@1@Z; CLKRLinearHashTable::_MergeRecordSets(CLKRLinearHashTable::CBucket *,CLKRLinearHashTable::CNodeClump *,CLKRLinearHashTable::CNodeClump *)
0x180077d31  xchg    edi, [r12]
0x180077d35  mov     rcx, [rsp+88h+var_30]
0x180077d3a  xor     rcx, rsp
0x180077d3d  call    sub_1801503E0
0x180077d42  lea     r11, [rsp+88h+var_28]
0x180077d47  mov     rbx, [r11+38h]
0x180077d4b  mov     rbp, [r11+40h]
0x180077d4f  mov     rsi, [r11+48h]
0x180077d53  mov     rsp, r11
0x180077d56  pop     r15
0x180077d58  pop     r14
  ... truncated ...
```
