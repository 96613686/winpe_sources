# CLKRLinearHashTable::_Expand(void)

- ea: `0x180077420`
- end: `0x180077758`
- name: `?_Expand@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180074cd0`

## callees

- `0x180076f60`
- `0x180076ff0`
- `0x180077040`
- `0x1800770e0`
- `0x180077420`
- `0x180077760`
- `0x1800b3f20`
- `0x1800b44b0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077487`
- `KERNEL32!GetCurrentThreadId` at `0x180077498`
- `KERNEL32!GetCurrentThreadId` at `0x180077636`
- `KERNEL32!GetCurrentThreadId` at `0x180077660`
- `KERNEL32!GetCurrentThreadId` at `0x180077487`
- `KERNEL32!GetCurrentThreadId` at `0x180077498`
- `KERNEL32!GetCurrentThreadId` at `0x180077636`
- `KERNEL32!GetCurrentThreadId` at `0x180077660`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_Expand(__int64 a1)
{
  __int64 result; // rax
  volatile signed __int32 *v3; // rdi
  signed __int32 v4; // edx
  DWORD v5; // eax
  int v6; // ecx
  unsigned int v7; // ebp
  struct CLKRLinearHashTable::CDirEntry *SegmentDirectory; // r14
  unsigned int i; // r8d
  __int64 v10; // rdx
  int v11; // ecx
  unsigned __int64 v12; // r14
  __int64 v13; // rax
  unsigned int v14; // r12d
  struct CLKRLinearHashTable::CSegment *Segment; // r8
  int v16; // edx
  bool v17; // zf
  signed __int32 v18; // edx
  int v19; // edx
  signed __int32 v20; // edx
  __int64 v21; // rcx
  __int64 v22; // r14
  __int64 v23; // rcx
  volatile signed __int32 *v24; // r15
  bool v25; // cl
  bool v26; // cl
  struct CLKRLinearHashTable::CNodeClump *NodeClump; // r9
  unsigned int v28; // ebp
  int v29; // ecx
  int v30; // eax
  unsigned int v31; // r10d
  int v32; // edx
  int v33; // r11d
  signed __int32 v34; // edx

  if ( *(_DWORD *)(a1 + 108) >= (unsigned int)((*(_DWORD *)(a1 + 56) << 20) - 1) )
    return 4294967198LL;
  v3 = (volatile signed __int32 *)(a1 + 8);
  if ( !*(_DWORD *)(a1 + 12) && !(unsigned __int16)*v3 )
  {
    v4 = *v3;
    if ( v4 == _InterlockedCompareExchange(v3, (v4 + 0x10000) | 0xFFFF, v4) )
    {
      v5 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_7:
      _InterlockedExchange(v3 + 1, v5);
      goto LABEL_11;
    }
  }
  if ( ((GetCurrentThreadId() ^ *(_DWORD *)(a1 + 12)) & 0xFFFFFFFC) == 0 )
  {
    v5 = *((_DWORD *)v3 + 1) + 1;
    goto LABEL_7;
  }
  VonetLocks::CReaderWriterLock3::_WriteLockSpin((VonetLocks::CReaderWriterLock3 *)v3);
LABEL_11:
  v6 = *(_DWORD *)(a1 + 100);
  if ( *(_DWORD *)(a1 + 108) >= (unsigned int)(*(_DWORD *)(a1 + 56) * v6) )
  {
    v7 = 8;
    if ( v6 )
      v7 = 2 * v6;
    SegmentDirectory = CLKRLinearHashTable::_AllocateSegmentDirectory(v7);
    if ( !SegmentDirectory )
    {
      v19 = *((_DWORD *)v3 + 1) - 1;
      v17 = (((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v19 : 0) == 0;
      _InterlockedExchange(v3 + 1, ((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v19 : 0);
      if ( v17 )
      {
        _m_prefetchw((const void *)v3);
        do
          v20 = *v3;
        while ( v20 != _InterlockedCompareExchange(v3, (v20 - 0x10000) & 0xFFFF0000, v20) );
      }
      return 4294967198LL;
    }
    for ( i = 0; i < *(_DWORD *)(a1 + 100); *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v10) = 0 )
    {
      v10 = i++;
      *((_QWORD *)SegmentDirectory + v10) = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v10);
    }
    CLKRLinearHashTable::_FreeSegmentDirectory(*(struct CLKRLinearHashTable::CDirEntry **)(a1 + 88));
    *(_QWORD *)(a1 + 88) = SegmentDirectory;
    *(_DWORD *)(a1 + 100) = v7;
  }
  v11 = *(_DWORD *)(a1 + 96);
  v12 = *(unsigned int *)(a1 + 80);
  v13 = *(_QWORD *)(a1 + 88);
  ++*(_DWORD *)(a1 + 108);
  v14 = v12 | (1 << v11);
  if ( !*(_QWORD *)(v13 + 8 * ((unsigned __int64)v14 >> *(_BYTE *)(a1 + 52))) )
  {
    Segment = CLKRLinearHashTable::_AllocateSegment((CLKRLinearHashTable *)a1);
    if ( !Segment )
    {
      --*(_DWORD *)(a1 + 108);
      v16 = *((_DWORD *)v3 + 1) - 1;
      v17 = (((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v16 : 0) == 0;
      _InterlockedExchange(v3 + 1, ((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v16 : 0);
      if ( v17 )
      {
        _m_prefetchw((const void *)v3);
        do
          v18 = *v3;
        while ( v18 != _InterlockedCompareExchange(v3, (v18 - 0x10000) & 0xFFFF0000, v18) );
      }
      return 4294967198LL;
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * ((unsigned __int64)v14 >> *(_BYTE *)(a1 + 52))) = Segment;
  }
  v21 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * (v12 >> *(_BYTE *)(a1 + 52)));
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 40LL))(
          v21,
          (unsigned int)v12 & *(_DWORD *)(a1 + 60));
  v23 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * ((unsigned __int64)v14 >> *(_BYTE *)(a1 + 52)));
  v24 = (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 40LL))(
                                     v23,
                                     v14 & *(_DWORD *)(a1 + 60));
  if ( *(_DWORD *)v22 )
    v25 = 0;
  else
    v25 = _InterlockedCompareExchange((volatile signed __int32 *)v22, GetCurrentThreadId(), 0) == 0;
  if ( !v25 )
    VonetLocks::CSmallSpinLock::_LockSpin((VonetLocks::CSmallSpinLock *)v22);
  if ( *v24 )
    v26 = 0;
  else
    v26 = _InterlockedCompareExchange(v24, GetCurrentThreadId(), 0) == 0;
  if ( !v26 )
    VonetLocks::CSmallSpinLock::_LockSpin((VonetLocks::CSmallSpinLock *)v24);
  NodeClump = 0;
  v28 = 0;
  if ( !*(_QWORD *)(v22 + 24) || (NodeClump = CLKRLinearHashTable::_AllocateNodeClump()) != 0 )
  {
    v29 = *(_DWORD *)(a1 + 96);
    if ( ++*(_DWORD *)(a1 + 80) == 1 << v29 )
    {
      *(_DWORD *)(a1 + 80) = 0;
      *(_DWORD *)(a1 + 96) = v29 + 1;
      v30 = (2 * *(_DWORD *)(a1 + 72)) | 1;
      *(_DWORD *)(a1 + 72) = v30;
      *(_DWORD *)(a1 + 76) = (2 * v30) | 1;
    }
  }
  else
  {
    --*(_DWORD *)(a1 + 108);
    v28 = -98;
  }
  v31 = *(_DWORD *)(a1 + 80);
  v32 = *((_DWORD *)v3 + 1) - 1;
  v33 = *(_DWORD *)(a1 + 72);
  v17 = (((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v32 : 0) == 0;
  _InterlockedExchange(v3 + 1, ((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v32 : 0);
  if ( v17 )
  {
    _m_prefetchw((const void *)v3);
    do
      v34 = *v3;
    while ( v34 != _InterlockedCompareExchange(v3, (v34 - 0x10000) & 0xFFFF0000, v34) );
  }
  if ( !v28 )
    v28 = CLKRLinearHashTable::_SplitRecordSet(a1, v22 + 8, v24 + 2, v31, v33, v14, NodeClump);
  result = v28;
  _InterlockedExchange(v24, 0);
  _InterlockedExchange((volatile __int32 *)v22, 0);
  return result;
}

```

## disassembly

```asm
0x180077420  mov     [rsp+arg_0], rbx
0x180077425  mov     [rsp+arg_8], rbp
0x18007742a  mov     [rsp+arg_10], rsi
0x18007742f  push    rdi
0x180077430  push    r12
0x180077432  push    r13
0x180077434  push    r14
0x180077436  push    r15
0x180077438  sub     rsp, 40h
0x18007743c  mov     eax, [rcx+38h]
0x18007743f  mov     r13d, 1
0x180077445  shl     eax, 14h
0x180077448  mov     rbx, rcx
0x18007744b  sub     eax, r13d
0x18007744e  cmp     [rcx+6Ch], eax
0x180077451  jb      short loc_18007745D
0x180077453  mov     eax, 0FFFFFF9Eh
0x180077458  jmp     loc_18007773A
0x18007745d  lea     rdi, [rcx+8]
0x180077461  xor     esi, esi
0x180077463  mov     eax, [rdi+4]
0x180077466  test    eax, eax
0x180077468  jnz     short loc_180077498
0x18007746a  mov     edx, [rdi]
0x18007746c  test    dx, dx
0x18007746f  jnz     short loc_180077498
0x180077471  lea     ecx, [rdx+10000h]
0x180077477  mov     eax, edx
0x180077479  or      ecx, 0FFFFh
0x18007747f  lock cmpxchg [rdi], ecx
0x180077483  cmp     edx, eax
0x180077485  jnz     short loc_180077498
0x180077487  call    cs:GetCurrentThreadId
0x18007748d  and     eax, 0FFFFFFFDh
0x180077490  or      eax, r13d
0x180077493  xchg    eax, [rdi+4]
0x180077496  jmp     short loc_1800774BB
0x180077498  call    cs:GetCurrentThreadId
0x18007749e  mov     ecx, [rdi+4]
0x1800774a1  xor     ecx, eax
0x1800774a3  test    ecx, 0FFFFFFFCh
0x1800774a9  jnz     short loc_1800774B3
0x1800774ab  mov     eax, [rdi+4]
0x1800774ae  add     eax, r13d
0x1800774b1  jmp     short loc_180077493
0x1800774b3  mov     rcx, rdi; this
0x1800774b6  call    ?_WriteLockSpin@CReaderWriterLock3@VonetLocks@@AEAAXXZ; VonetLocks::CReaderWriterLock3::_WriteLockSpin(void)
0x1800774bb  mov     ecx, [rbx+64h]
0x1800774be  mov     eax, ecx
0x1800774c0  imul    eax, [rbx+38h]
0x1800774c4  cmp     [rbx+6Ch], eax
0x1800774c7  jb      short loc_180077520
0x1800774c9  mov     ebp, 8
0x1800774ce  test    ecx, ecx
0x1800774d0  jz      short loc_1800774D5
0x1800774d2  lea     ebp, [rcx+rcx]
0x1800774d5  mov     ecx, ebp; unsigned __int64
0x1800774d7  call    ?_AllocateSegmentDirectory@CLKRLinearHashTable@@CAQEAVCDirEntry@1@_K@Z; CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)
0x1800774dc  mov     r14, rax
0x1800774df  test    rax, rax
0x1800774e2  jz      loc_18007759A
0x1800774e8  mov     r8d, esi
0x1800774eb  cmp     [rbx+64h], esi
0x1800774ee  jbe     short loc_180077510
0x1800774f0  mov     rcx, [rbx+58h]
0x1800774f4  mov     edx, r8d
0x1800774f7  add     r8d, r13d
0x1800774fa  mov     rax, [rcx+rdx*8]
0x1800774fe  mov     [r14+rdx*8], rax
0x180077502  mov     rax, [rbx+58h]
0x180077506  mov     [rax+rdx*8], rsi
0x18007750a  cmp     r8d, [rbx+64h]
0x18007750e  jb      short loc_1800774F0
0x180077510  mov     rcx, [rbx+58h]; struct CLKRLinearHashTable::CDirEntry *
0x180077514  call    ?_FreeSegmentDirectory@CLKRLinearHashTable@@CA_NPEAVCDirEntry@1@@Z; CLKRLinearHashTable::_FreeSegmentDirectory(CLKRLinearHashTable::CDirEntry *)
0x180077519  mov     [rbx+58h], r14
0x18007751d  mov     [rbx+64h], ebp
0x180077520  mov     ecx, [rbx+60h]
0x180077523  mov     r12d, r13d
0x180077526  mov     r14d, [rbx+50h]
0x18007752a  mov     rax, [rbx+58h]
0x18007752e  add     [rbx+6Ch], r13d
0x180077532  shl     r12d, cl
0x180077535  mov     cl, [rbx+34h]
0x180077538  or      r12d, r14d
0x18007753b  mov     edx, r12d
0x18007753e  shr     rdx, cl
0x180077541  mov     ebp, r12d
0x180077544  cmp     [rax+rdx*8], rsi
0x180077548  jnz     loc_1800775E4
0x18007754e  mov     rcx, rbx; this
0x180077551  call    ?_AllocateSegment@CLKRLinearHashTable@@AEBAQEAVCSegment@1@XZ; CLKRLinearHashTable::_AllocateSegment(void)
0x180077556  mov     r8, rax
0x180077559  test    rax, rax
0x18007755c  jnz     short loc_1800775D3
0x18007755e  dec     dword ptr [rbx+6Ch]
0x180077561  mov     edx, [rdi+4]
0x180077564  sub     edx, r13d
0x180077567  mov     al, dl
0x180077569  and     al, 3
0x18007756b  neg     al
0x18007756d  sbb     ecx, ecx
0x18007756f  and     ecx, edx
0x180077571  xchg    ecx, [rdi+4]
0x180077574  jnz     loc_180077453
0x18007757a  prefetchw byte ptr [rdi]
0x18007757d  mov     edx, [rdi]
0x18007757f  mov     eax, edx
0x180077581  lea     ecx, [rdx-10000h]
0x180077587  and     ecx, 0FFFF0000h
0x18007758d  lock cmpxchg [rdi], ecx
0x180077591  cmp     edx, eax
0x180077593  jnz     short loc_18007757D
0x180077595  jmp     loc_180077453
0x18007759a  mov     edx, [rdi+4]
0x18007759d  sub     edx, r13d
0x1800775a0  mov     al, dl
0x1800775a2  and     al, 3
0x1800775a4  neg     al
0x1800775a6  sbb     ecx, ecx
0x1800775a8  and     ecx, edx
0x1800775aa  xchg    ecx, [rdi+4]
0x1800775ad  jnz     loc_180077453
0x1800775b3  prefetchw byte ptr [rdi]
0x1800775b6  mov     edx, [rdi]
0x1800775b8  mov     eax, edx
0x1800775ba  lea     ecx, [rdx-10000h]
0x1800775c0  and     ecx, 0FFFF0000h
0x1800775c6  lock cmpxchg [rdi], ecx
0x1800775ca  cmp     edx, eax
0x1800775cc  jnz     short loc_1800775B6
0x1800775ce  jmp     loc_180077453
0x1800775d3  mov     cl, [rbx+34h]
0x1800775d6  mov     rdx, rbp
0x1800775d9  mov     rax, [rbx+58h]
0x1800775dd  shr     rdx, cl
0x1800775e0  mov     [rax+rdx*8], r8
0x1800775e4  mov     cl, [rbx+34h]
0x1800775e7  mov     rdx, r14
0x1800775ea  mov     rax, [rbx+58h]
0x1800775ee  shr     rdx, cl
0x1800775f1  mov     rcx, [rax+rdx*8]
0x1800775f5  mov     edx, [rbx+3Ch]
0x1800775f8  and     edx, r14d
0x1800775fb  mov     rax, [rcx]
0x1800775fe  mov     rax, [rax+28h]
0x180077602  call    cs:__guard_dispatch_icall_fptr
0x180077608  mov     cl, [rbx+34h]
0x18007760b  mov     r14, rax
0x18007760e  mov     edx, [rbx+3Ch]
0x180077611  shr     rbp, cl
0x180077614  and     edx, r12d
0x180077617  mov     rcx, [rbx+58h]
0x18007761b  mov     rcx, [rcx+rbp*8]
0x18007761f  mov     r8, [rcx]
0x180077622  mov     rax, [r8+28h]
0x180077626  call    cs:__guard_dispatch_icall_fptr
0x18007762c  mov     ecx, [r14]
0x18007762f  mov     r15, rax
0x180077632  test    ecx, ecx
0x180077634  jnz     short loc_18007764A
0x180077636  call    cs:GetCurrentThreadId
0x18007763c  mov     ecx, eax
0x18007763e  xor     eax, eax
0x180077640  lock cmpxchg [r14], ecx
0x180077645  setz    cl
0x180077648  jmp     short loc_18007764D
0x18007764a  mov     cl, sil
0x18007764d  test    cl, cl
0x18007764f  jnz     short loc_180077659
0x180077651  mov     rcx, r14; this
0x180077654  call    ?_LockSpin@CSmallSpinLock@VonetLocks@@AEAAXXZ; VonetLocks::CSmallSpinLock::_LockSpin(void)
0x180077659  mov     eax, [r15]
0x18007765c  test    eax, eax
0x18007765e  jnz     short loc_180077674
0x180077660  call    cs:GetCurrentThreadId
0x180077666  mov     ecx, eax
0x180077668  xor     eax, eax
0x18007766a  lock cmpxchg [r15], ecx
0x18007766f  setz    cl
0x180077672  jmp     short loc_180077677
0x180077674  mov     cl, sil
0x180077677  test    cl, cl
0x180077679  jnz     short loc_180077683
0x18007767b  mov     rcx, r15; this
0x18007767e  call    ?_LockSpin@CSmallSpinLock@VonetLocks@@AEAAXXZ; VonetLocks::CSmallSpinLock::_LockSpin(void)
0x180077683  mov     r9, rsi
0x180077686  mov     ebp, esi
0x180077688  cmp     [r14+18h], rsi
0x18007768c  jz      short loc_1800776A3
0x18007768e  call    ?_AllocateNodeClump@CLKRLinearHashTable@@CAQEAVCNodeClump@1@XZ; CLKRLinearHashTable::_AllocateNodeClump(void)
0x180077693  mov     r9, rax
0x180077696  test    rax, rax
0x180077699  jnz     short loc_1800776A3
0x18007769b  dec     dword ptr [rbx+6Ch]
0x18007769e  lea     ebp, [rax-62h]
0x1800776a1  jmp     short loc_1800776D0
0x1800776a3  mov     ecx, [rbx+60h]
0x1800776a6  mov     eax, r13d
0x1800776a9  add     [rbx+50h], r13d
0x1800776ad  shl     eax, cl
0x1800776af  cmp     [rbx+50h], eax
0x1800776b2  jnz     short loc_1800776D0
0x1800776b4  lea     eax, [rcx+1]
0x1800776b7  mov     [rbx+50h], esi
0x1800776ba  mov     [rbx+60h], eax
0x1800776bd  mov     eax, [rbx+48h]
0x1800776c0  add     eax, eax
0x1800776c2  or      eax, r13d
0x1800776c5  mov     [rbx+48h], eax
0x1800776c8  add     eax, eax
0x1800776ca  or      eax, r13d
0x1800776cd  mov     [rbx+4Ch], eax
0x1800776d0  mov     edx, [rdi+4]
0x1800776d3  mov     r10d, [rbx+50h]
0x1800776d7  sub     edx, r13d
0x1800776da  mov     r11d, [rbx+48h]
0x1800776de  mov     al, dl
0x1800776e0  and     al, 3
0x1800776e2  neg     al
0x1800776e4  sbb     ecx, ecx
0x1800776e6  and     ecx, edx
0x1800776e8  xchg    ecx, [rdi+4]
0x1800776eb  jnz     short loc_180077708
0x1800776ed  prefetchw byte ptr [rdi]
0x1800776f0  mov     edx, [rdi]
0x1800776f2  mov     eax, edx
0x1800776f4  lea     ecx, [rdx-10000h]
0x1800776fa  and     ecx, 0FFFF0000h
0x180077700  lock cmpxchg [rdi], ecx
0x180077704  cmp     edx, eax
0x180077706  jnz     short loc_1800776F0
0x180077708  test    ebp, ebp
0x18007770a  jnz     short loc_180077730
0x18007770c  mov     [rsp+68h+var_38], r9
0x180077711  lea     r8, [r15+8]
0x180077715  mov     [rsp+68h+var_40], r12d
0x18007771a  lea     rdx, [r14+8]
0x18007771e  mov     r9d, r10d
0x180077721  mov     [rsp+68h+var_48], r11d
0x180077726  mov     rcx, rbx
0x180077729  call    ?_SplitRecordSet@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEAVCNodeClump@1@0KKK0@Z; CLKRLinearHashTable::_SplitRecordSet(CLKRLinearHashTable::CNodeClump *,CLKRLinearHashTable::CNodeClump *,ulong,ulong,ulong,CLKRLinearHashTable::CNodeClump *)
0x18007772e  mov     ebp, eax
0x180077730  mov     ecx, esi
0x180077732  mov     eax, ebp
0x180077734  xchg    ecx, [r15]
0x180077737  xchg    esi, [r14]
0x18007773a  lea     r11, [rsp+68h+var_28]
0x18007773f  mov     rbx, [r11+30h]
0x180077743  mov     rbp, [r11+38h]
0x180077747  mov     rsi, [r11+40h]
0x18007774b  mov     rsp, r11
0x18007774e  pop     r15
0x180077750  pop     r14
0x180077752  pop     r13
0x180077754  pop     r12
0x180077756  pop     rdi
0x180077757  retn
```
