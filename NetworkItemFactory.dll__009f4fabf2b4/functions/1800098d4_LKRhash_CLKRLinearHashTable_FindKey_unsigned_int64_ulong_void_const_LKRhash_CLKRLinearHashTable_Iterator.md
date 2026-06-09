# LKRhash::CLKRLinearHashTable::_FindKey(unsigned __int64,ulong,void const * *,LKRhash::CLKRLinearHashTable_Iterator *)

- ea: `0x1800098d4`
- end: `0x180009aea`
- name: `?_FindKey@CLKRLinearHashTable@LKRhash@@AEBA?AW4LK_RETCODE@2@_KKPEAPEBXPEAVCLKRLinearHashTable_Iterator@2@@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008354`

## callees

- `0x180003ca0`
- `0x1800075f0`
- `0x1800076c8`
- `0x1800098d4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009909`
- `KERNEL32!GetCurrentThreadId` at `0x180009909`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_FindKey(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  volatile __int32 *v4; // rdi
  int v8; // ebx
  char v9; // bp
  signed __int32 v10; // edx
  signed __int32 v11; // edx
  int v12; // edx
  signed __int32 v13; // edx
  unsigned int v15; // r15d
  unsigned int v16; // eax
  CReaderWriterLock2 *v17; // rbx
  signed __int32 v18; // edx
  signed __int32 v19; // edx
  int v20; // edx
  signed __int32 v21; // edx
  char *v22; // rdi
  __int64 v23; // rbp
  __int64 v24; // rax
  __int64 v25; // rcx
  void (__fastcall *v26)(__int64, __int64); // rax
  bool i; // zf
  signed __int32 v28; // edx

  i = *(_BYTE *)(a1 + 153) == 0;
  v4 = (volatile __int32 *)(a1 + 24);
  *a4 = 0;
  if ( !i )
  {
    v8 = *(_DWORD *)(a1 + 28);
    if ( ((v8 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)v4);
      v9 = 0;
      goto LABEL_8;
    }
    if ( (unsigned __int16)*v4 == 0xFFFF || (v10 = *v4, v10 != _InterlockedCompareExchange(v4, v10 + 1, v10)) )
      CReaderWriterLock3::_LockSpin(v4, 3);
  }
  v9 = 1;
LABEL_8:
  if ( *(_DWORD *)(a1 + 20) )
  {
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( v9 )
      {
        do
          v11 = *v4;
        while ( v11 != _InterlockedCompareExchange(v4, v11 - 1, v11) );
      }
      else
      {
        v12 = *((_DWORD *)v4 + 1) - 1;
        i = (((*((_BYTE *)v4 + 4) - 1) & 3) != 0 ? v12 : 0) == 0;
        _InterlockedExchange(v4 + 1, ((*((_BYTE *)v4 + 4) - 1) & 3) != 0 ? v12 : 0);
        if ( i )
        {
          _m_prefetchw((const void *)v4);
          do
            v13 = *v4;
          while ( v13 != _InterlockedCompareExchange(v4, (v13 - 0x10000) & 0xFFFF0000, v13) );
        }
      }
    }
    return *(unsigned int *)(a1 + 20);
  }
  else
  {
    v15 = 2;
    v16 = *(_DWORD *)(a1 + 88) & a3;
    if ( v16 < *(_DWORD *)(a1 + 96) )
      v16 = a3 & *(_DWORD *)(a1 + 92);
    v17 = (CReaderWriterLock2 *)(((unsigned __int64)(v16 & *(_DWORD *)(a1 + 76)) << 6)
                               + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v16 >> *(_DWORD *)(a1 + 68))));
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( (*(_DWORD *)v17 & 0xFFFF8000) != 0
        || (v18 = *(_DWORD *)v17, v18 != _InterlockedCompareExchange((volatile signed __int32 *)v17, v18 + 1, v18)) )
      {
        CReaderWriterLock2::_LockSpin(v17, 0);
      }
      if ( *(_BYTE *)(a1 + 153) )
      {
        if ( v9 )
        {
          do
            v19 = *v4;
          while ( v19 != _InterlockedCompareExchange(v4, v19 - 1, v19) );
        }
        else
        {
          v20 = *((_DWORD *)v4 + 1) - 1;
          i = (((*((_BYTE *)v4 + 4) - 1) & 3) != 0 ? v20 : 0) == 0;
          _InterlockedExchange(v4 + 1, ((*((_BYTE *)v4 + 4) - 1) & 3) != 0 ? v20 : 0);
          if ( i )
          {
            _m_prefetchw((const void *)v4);
            do
              v21 = *v4;
            while ( v21 != _InterlockedCompareExchange(v4, (v21 - 0x10000) & 0xFFFF0000, v21) );
          }
        }
      }
    }
    v22 = (char *)v17 + 8;
LABEL_38:
    if ( v22 )
    {
      v23 = 0;
      while ( *(_DWORD *)&v22[4 * v23] != 31678523 )
      {
        if ( a3 == *(_DWORD *)&v22[4 * v23] )
        {
          v24 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 32))(*(_QWORD *)&v22[8 * v23 + 24]);
          if ( a2 == v24 || (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(a2, v24) )
          {
            v25 = *(_QWORD *)&v22[8 * v23 + 24];
            v15 = 0;
            v26 = *(void (__fastcall **)(__int64, __int64))(a1 + 56);
            *a4 = v25;
            v26(v25, 1);
            break;
          }
        }
        v23 = (unsigned int)(v23 + 1);
        if ( (int)v23 >= 4 )
        {
          v22 = (char *)*((_QWORD *)v22 + 2);
          goto LABEL_38;
        }
      }
    }
    for ( i = *(_BYTE *)(a1 + 153) == 0;
          !i;
          i = v28 == _InterlockedCompareExchange((volatile signed __int32 *)v17, v28 - 1, v28) )
    {
      v28 = *(_DWORD *)v17;
    }
    return v15;
  }
}

```

## disassembly

```asm
0x1800098d4  mov     [rsp+arg_8], rdx
0x1800098d9  push    rbx
0x1800098da  push    rbp
0x1800098db  push    rsi
0x1800098dc  push    rdi
0x1800098dd  push    r12
0x1800098df  push    r13
0x1800098e1  push    r14
0x1800098e3  push    r15
0x1800098e5  sub     rsp, 28h
0x1800098e9  cmp     byte ptr [rcx+99h], 0
0x1800098f0  lea     rdi, [rcx+18h]
0x1800098f4  mov     r13, r9
0x1800098f7  mov     qword ptr [r9], 0
0x1800098fe  mov     r12d, r8d
0x180009901  mov     rsi, rcx
0x180009904  jz      short loc_180009948
0x180009906  mov     ebx, [rdi+4]
0x180009909  call    cs:__imp_GetCurrentThreadId
0x18000990f  xor     eax, ebx
0x180009911  test    eax, 0FFFFFFFCh
0x180009916  jnz     short loc_180009925
0x180009918  mov     rcx, rdi; this
0x18000991b  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180009920  xor     bpl, bpl
0x180009923  jmp     short loc_18000994B
0x180009925  mov     edx, [rdi]
0x180009927  cmp     dx, 0FFFFh
0x18000992c  jz      short loc_18000993B
0x18000992e  lea     ecx, [rdx+1]
0x180009931  mov     eax, edx
0x180009933  lock cmpxchg [rdi], ecx
0x180009937  cmp     edx, eax
0x180009939  jz      short loc_180009948
0x18000993b  mov     edx, 3
0x180009940  mov     rcx, rdi
0x180009943  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x180009948  mov     bpl, 1
0x18000994b  cmp     dword ptr [rsi+14h], 0
0x18000994f  jz      short loc_1800099A7
0x180009951  cmp     byte ptr [rsi+99h], 0
0x180009958  jz      short loc_18000999F
0x18000995a  test    bpl, bpl
0x18000995d  jz      short loc_180009970
0x18000995f  mov     edx, [rdi]
0x180009961  mov     eax, edx
0x180009963  lea     ecx, [rdx-1]
0x180009966  lock cmpxchg [rdi], ecx
0x18000996a  cmp     edx, eax
0x18000996c  jz      short loc_18000999F
0x18000996e  jmp     short loc_18000995F
0x180009970  mov     edx, [rdi+4]
0x180009973  dec     edx
0x180009975  mov     eax, edx
0x180009977  and     al, 3
0x180009979  neg     al
0x18000997b  sbb     ecx, ecx
0x18000997d  and     ecx, edx
0x18000997f  xchg    ecx, [rdi+4]
0x180009982  jnz     short loc_18000999F
0x180009984  prefetchw byte ptr [rdi]
0x180009987  mov     edx, [rdi]
0x180009989  mov     eax, edx
0x18000998b  lea     ecx, [rdx-10000h]
0x180009991  and     ecx, 0FFFF0000h
0x180009997  lock cmpxchg [rdi], ecx
0x18000999b  cmp     edx, eax
0x18000999d  jnz     short loc_180009987
0x18000999f  mov     eax, [rsi+14h]
0x1800099a2  jmp     loc_180009AD9
0x1800099a7  mov     eax, r12d
0x1800099aa  mov     r15d, 2
0x1800099b0  and     eax, [rsi+58h]
0x1800099b3  cmp     eax, [rsi+60h]
0x1800099b6  jnb     short loc_1800099BE
0x1800099b8  mov     eax, [rsi+5Ch]
0x1800099bb  and     eax, r12d
0x1800099be  mov     ecx, [rsi+44h]
0x1800099c1  mov     edx, [rsi+4Ch]
0x1800099c4  and     rdx, rax
0x1800099c7  mov     r8d, eax
0x1800099ca  shr     r8, cl
0x1800099cd  mov     rcx, [rsi+68h]
0x1800099d1  shl     rdx, 6
0x1800099d5  mov     rbx, [rcx+r8*8]
0x1800099d9  add     rbx, rdx
0x1800099dc  cmp     byte ptr [rsi+99h], 0
0x1800099e3  jz      short loc_180009A54
0x1800099e5  mov     edx, [rbx]
0x1800099e7  test    edx, 0FFFF8000h
0x1800099ed  jnz     short loc_1800099FC
0x1800099ef  lea     ecx, [rdx+1]
0x1800099f2  mov     eax, edx
0x1800099f4  lock cmpxchg [rbx], ecx
0x1800099f8  cmp     edx, eax
0x1800099fa  jz      short loc_180009A06
0x1800099fc  xor     edx, edx; bool
0x1800099fe  mov     rcx, rbx; this
0x180009a01  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180009a06  cmp     byte ptr [rsi+99h], 0
0x180009a0d  jz      short loc_180009A54
0x180009a0f  test    bpl, bpl
0x180009a12  jz      short loc_180009A25
0x180009a14  mov     edx, [rdi]
0x180009a16  mov     eax, edx
0x180009a18  lea     ecx, [rdx-1]
0x180009a1b  lock cmpxchg [rdi], ecx
0x180009a1f  cmp     edx, eax
0x180009a21  jz      short loc_180009A54
0x180009a23  jmp     short loc_180009A14
0x180009a25  mov     edx, [rdi+4]
0x180009a28  dec     edx
0x180009a2a  mov     eax, edx
0x180009a2c  and     al, 3
0x180009a2e  neg     al
0x180009a30  sbb     ecx, ecx
0x180009a32  and     ecx, edx
0x180009a34  xchg    ecx, [rdi+4]
0x180009a37  jnz     short loc_180009A54
0x180009a39  prefetchw byte ptr [rdi]
0x180009a3c  mov     edx, [rdi]
0x180009a3e  mov     eax, edx
0x180009a40  lea     ecx, [rdx-10000h]
0x180009a46  and     ecx, 0FFFF0000h
0x180009a4c  lock cmpxchg [rdi], ecx
0x180009a50  cmp     edx, eax
0x180009a52  jnz     short loc_180009A3C
0x180009a54  lea     rdi, [rbx+8]
0x180009a58  jmp     short loc_180009A9E
0x180009a5a  xor     ebp, ebp
0x180009a5c  cmp     dword ptr [rdi+rbp*4], 1E3603Bh
0x180009a63  jz      short loc_180009ABE
0x180009a65  cmp     r12d, [rdi+rbp*4]
0x180009a69  jnz     short loc_180009A93
0x180009a6b  mov     rcx, [rdi+rbp*8+18h]
0x180009a70  mov     rax, [rsi+20h]
0x180009a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a79  mov     rcx, [rsp+68h+arg_8]
0x180009a7e  cmp     rcx, rax
0x180009a81  jz      short loc_180009AA5
0x180009a83  mov     rdx, rax
0x180009a86  mov     rax, [rsi+30h]
0x180009a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8f  test    al, al
0x180009a91  jnz     short loc_180009AA5
0x180009a93  inc     ebp
0x180009a95  cmp     ebp, 4
0x180009a98  jl      short loc_180009A5C
0x180009a9a  mov     rdi, [rdi+10h]
0x180009a9e  test    rdi, rdi
0x180009aa1  jnz     short loc_180009A5A
0x180009aa3  jmp     short loc_180009ABE
0x180009aa5  mov     rcx, [rdi+rbp*8+18h]
0x180009aaa  xor     r15d, r15d
0x180009aad  mov     rax, [rsi+38h]
0x180009ab1  mov     [r13+0], rcx
0x180009ab5  lea     edx, [r15+1]
0x180009ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009abe  cmp     byte ptr [rsi+99h], 0
0x180009ac5  jz      short loc_180009AD6
0x180009ac7  mov     edx, [rbx]
0x180009ac9  mov     eax, edx
0x180009acb  lea     ecx, [rdx-1]
0x180009ace  lock cmpxchg [rbx], ecx
0x180009ad2  cmp     edx, eax
0x180009ad4  jmp     short loc_180009AC5
0x180009ad6  mov     eax, r15d
0x180009ad9  add     rsp, 28h
0x180009add  pop     r15
0x180009adf  pop     r14
0x180009ae1  pop     r13
0x180009ae3  pop     r12
0x180009ae5  pop     rdi
0x180009ae6  pop     rsi
0x180009ae7  pop     rbp
0x180009ae8  pop     rbx
0x180009ae9  retn
```
