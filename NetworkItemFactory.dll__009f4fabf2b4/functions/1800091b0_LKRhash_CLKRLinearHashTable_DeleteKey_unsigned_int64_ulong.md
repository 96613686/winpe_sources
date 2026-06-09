# LKRhash::CLKRLinearHashTable::_DeleteKey(unsigned __int64,ulong)

- ea: `0x1800091b0`
- end: `0x180009436`
- name: `?_DeleteKey@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@_KK@Z`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800082bc`

## callees

- `0x180003ca0`
- `0x1800075f0`
- `0x180008bf4`
- `0x1800091b0`
- `0x18000943c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_DeleteKey(__int64 a1, __int64 a2, int a3)
{
  signed __int32 *v3; // rdi
  unsigned int *v7; // r8
  int v8; // edx
  signed __int32 v9; // edx
  unsigned int v11; // r15d
  unsigned int v12; // eax
  unsigned __int64 v13; // rsi
  signed __int32 v14; // edx
  signed __int32 v15; // edx
  int v16; // edx
  signed __int32 v17; // edx
  struct LKRhash::CNodeClump *v18; // rdi
  int v19; // ebp
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rax
  struct LKRhash::CNodeClump *v23; // rax
  bool i; // zf
  signed __int32 v25; // edx
  double v26; // xmm6_8
  int v27; // eax
  double j; // xmm0_8
  struct LKRhash::CNodeClump *v29; // [rsp+30h] [rbp-48h] BYREF
  int v30; // [rsp+80h] [rbp+8h] BYREF
  struct LKRhash::CNodeClump *v31; // [rsp+98h] [rbp+20h] BYREF

  v3 = (signed __int32 *)(a1 + 24);
  if ( *(_BYTE *)(a1 + 153) )
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 24));
  v7 = (unsigned int *)(a1 + 20);
  if ( *(_DWORD *)(a1 + 20) )
  {
    if ( *(_BYTE *)(a1 + 153) )
    {
      v8 = v3[1] - 1;
      i = (((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v8 : 0) == 0;
      _InterlockedExchange(v3 + 1, ((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v8 : 0);
      if ( i )
      {
        _m_prefetchw(v3);
        do
          v9 = *v3;
        while ( v9 != _InterlockedCompareExchange(v3, (v9 - 0x10000) & 0xFFFF0000, v9) );
        v7 = (unsigned int *)(a1 + 20);
      }
    }
    return *v7;
  }
  else
  {
    v11 = 2;
    v12 = *(_DWORD *)(a1 + 88) & a3;
    if ( v12 < *(_DWORD *)(a1 + 96) )
      v12 = a3 & *(_DWORD *)(a1 + 92);
    v13 = ((unsigned __int64)(v12 & *(_DWORD *)(a1 + 76)) << 6)
        + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v12 >> *(_DWORD *)(a1 + 68)));
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( (unsigned __int16)*(_DWORD *)v13
        || (v14 = *(_DWORD *)v13,
            v14 != _InterlockedCompareExchange((volatile signed __int32 *)v13, (v14 + 0x10000) | 0xFFFF, v14)) )
      {
        do
          v15 = *(_DWORD *)v13;
        while ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)v13, v15 + 0x10000, v15) );
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v13, 1);
      }
      if ( *(_BYTE *)(a1 + 153) )
      {
        v16 = v3[1] - 1;
        i = (((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v16 : 0) == 0;
        _InterlockedExchange(v3 + 1, ((*((_BYTE *)v3 + 4) - 1) & 3) != 0 ? v16 : 0);
        if ( i )
        {
          _m_prefetchw(v3);
          do
            v17 = *v3;
          while ( v17 != _InterlockedCompareExchange(v3, (v17 - 0x10000) & 0xFFFF0000, v17) );
        }
      }
    }
    v18 = (struct LKRhash::CNodeClump *)(v13 + 8);
    v31 = 0;
    v29 = (struct LKRhash::CNodeClump *)(v13 + 8);
    if ( v13 != -8 )
    {
LABEL_22:
      v19 = 0;
      v30 = 0;
      v20 = 0;
      v21 = 0;
      while ( *((_DWORD *)v18 + v20) != 31678523 )
      {
        if ( a3 == *((_DWORD *)v18 + v20) )
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 32))(*((_QWORD *)v18 + v21 + 3));
          if ( a2 == v22 || (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(a2, v22) )
          {
            LKRhash::CLKRLinearHashTable::_DeleteNode(
              (LKRhash::CLKRLinearHashTable *)a1,
              (struct LKRhash::CBucket *const)v13,
              &v29,
              &v31,
              &v30);
            v11 = 0;
            break;
          }
        }
        v30 = ++v19;
        v20 = v19;
        v21 = v19;
        if ( v19 >= 4 )
        {
          v23 = (struct LKRhash::CNodeClump *)*((_QWORD *)v18 + 2);
          v31 = v18;
          v18 = v23;
          v29 = v23;
          if ( v23 )
            goto LABEL_22;
          break;
        }
      }
    }
    for ( i = *(_BYTE *)(a1 + 153) == 0;
          !i;
          i = v25 == _InterlockedCompareExchange((volatile signed __int32 *)v13, (v25 - 0x10000) & 0xFFFF0000, v25) )
    {
      v25 = *(_DWORD *)v13;
    }
    if ( !v11 )
    {
      v26 = (double)(*(_DWORD *)(a1 + 120) + (*(_DWORD *)(a1 + 120) >> 4));
      v27 = *(_DWORD *)(a1 + 124);
      for ( j = (double)v27;
            j * *(double *)(a1 + 80) > v26
         && (unsigned int)v27 > *(_DWORD *)(a1 + 72)
         && !(unsigned int)LKRhash::CLKRLinearHashTable::_Contract(a1);
            j = (double)v27 )
      {
        v27 = *(_DWORD *)(a1 + 124);
      }
    }
    return v11;
  }
}

```

## disassembly

```asm
0x1800091b0  mov     [rsp+arg_8], rbx
0x1800091b5  mov     [rsp+arg_10], rbp
0x1800091ba  push    rsi
0x1800091bb  push    rdi
0x1800091bc  push    r12
0x1800091be  push    r13
0x1800091c0  push    r15
0x1800091c2  sub     rsp, 50h
0x1800091c6  cmp     byte ptr [rcx+99h], 0
0x1800091cd  lea     rdi, [rcx+18h]
0x1800091d1  movaps  [rsp+78h+var_38], xmm6
0x1800091d6  mov     r12d, r8d
0x1800091d9  mov     r13, rdx
0x1800091dc  mov     rbx, rcx
0x1800091df  jz      short loc_1800091E9
0x1800091e1  mov     rcx, rdi; this
0x1800091e4  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800091e9  lea     r8, [rbx+14h]
0x1800091ed  cmp     dword ptr [r8], 0
0x1800091f1  jz      short loc_180009237
0x1800091f3  cmp     byte ptr [rbx+99h], 0
0x1800091fa  jz      short loc_18000922F
0x1800091fc  mov     edx, [rdi+4]
0x1800091ff  dec     edx
0x180009201  mov     eax, edx
0x180009203  and     al, 3
0x180009205  neg     al
0x180009207  sbb     ecx, ecx
0x180009209  and     ecx, edx
0x18000920b  xchg    ecx, [rdi+4]
0x18000920e  jnz     short loc_18000922F
0x180009210  prefetchw byte ptr [rdi]
0x180009213  mov     edx, [rdi]
0x180009215  mov     eax, edx
0x180009217  lea     ecx, [rdx-10000h]
0x18000921d  and     ecx, 0FFFF0000h
0x180009223  lock cmpxchg [rdi], ecx
0x180009227  cmp     edx, eax
0x180009229  jnz     short loc_180009213
0x18000922b  lea     r8, [rbx+14h]
0x18000922f  mov     eax, [r8]
0x180009232  jmp     loc_180009418
0x180009237  mov     eax, r12d
0x18000923a  mov     r15d, 2
0x180009240  and     eax, [rbx+58h]
0x180009243  cmp     eax, [rbx+60h]
0x180009246  jnb     short loc_18000924E
0x180009248  mov     eax, [rbx+5Ch]
0x18000924b  and     eax, r12d
0x18000924e  mov     ecx, [rbx+44h]
0x180009251  mov     edx, [rbx+4Ch]
0x180009254  and     rdx, rax
0x180009257  mov     r8d, eax
0x18000925a  shr     r8, cl
0x18000925d  mov     rcx, [rbx+68h]
0x180009261  shl     rdx, 6
0x180009265  mov     rsi, [rcx+r8*8]
0x180009269  add     rsi, rdx
0x18000926c  cmp     byte ptr [rbx+99h], 0
0x180009273  jz      short loc_1800092E6
0x180009275  mov     edx, [rsi]
0x180009277  test    dx, dx
0x18000927a  jnz     short loc_180009292
0x18000927c  lea     ecx, [rdx+10000h]
0x180009282  mov     eax, edx
0x180009284  or      ecx, 0FFFFh
0x18000928a  lock cmpxchg [rsi], ecx
0x18000928e  cmp     edx, eax
0x180009290  jz      short loc_1800092AE
0x180009292  mov     edx, [rsi]
0x180009294  mov     eax, edx
0x180009296  lea     ecx, [rdx+10000h]
0x18000929c  lock cmpxchg [rsi], ecx
0x1800092a0  cmp     edx, eax
0x1800092a2  jnz     short loc_180009292
0x1800092a4  mov     dl, 1; bool
0x1800092a6  mov     rcx, rsi; this
0x1800092a9  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800092ae  cmp     byte ptr [rbx+99h], 0
0x1800092b5  jz      short loc_1800092E6
0x1800092b7  mov     edx, [rdi+4]
0x1800092ba  dec     edx
0x1800092bc  mov     eax, edx
0x1800092be  and     al, 3
0x1800092c0  neg     al
0x1800092c2  sbb     ecx, ecx
0x1800092c4  and     ecx, edx
0x1800092c6  xchg    ecx, [rdi+4]
0x1800092c9  jnz     short loc_1800092E6
0x1800092cb  prefetchw byte ptr [rdi]
0x1800092ce  mov     edx, [rdi]
0x1800092d0  mov     eax, edx
0x1800092d2  lea     ecx, [rdx-10000h]
0x1800092d8  and     ecx, 0FFFF0000h
0x1800092de  lock cmpxchg [rdi], ecx
0x1800092e2  cmp     edx, eax
0x1800092e4  jnz     short loc_1800092CE
0x1800092e6  lea     rdi, [rsi+8]
0x1800092ea  mov     [rsp+78h+arg_18], 0
0x1800092f6  mov     [rsp+78h+var_48], rdi
0x1800092fb  test    rdi, rdi
0x1800092fe  jz      loc_1800093A8
0x180009304  xor     ebp, ebp
0x180009306  mov     [rsp+78h+arg_0], 0
0x180009311  xor     eax, eax
0x180009313  xor     ecx, ecx
0x180009315  cdqe
0x180009317  cmp     dword ptr [rdi+rax*4], 1E3603Bh
0x18000931e  jz      loc_1800093A8
0x180009324  cmp     r12d, [rdi+rax*4]
0x180009328  jnz     short loc_180009353
0x18000932a  mov     rax, [rbx+20h]
0x18000932e  movsxd  rcx, ecx
0x180009331  mov     rcx, [rdi+rcx*8+18h]
0x180009336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000933b  cmp     r13, rax
0x18000933e  jz      short loc_180009380
0x180009340  mov     rdx, rax
0x180009343  mov     rcx, r13
0x180009346  mov     rax, [rbx+30h]
0x18000934a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934f  test    al, al
0x180009351  jnz     short loc_180009380
0x180009353  inc     ebp
0x180009355  mov     [rsp+78h+arg_0], ebp
0x18000935c  mov     eax, ebp
0x18000935e  mov     ecx, ebp
0x180009360  cmp     ebp, 4
0x180009363  jl      short loc_180009315
0x180009365  mov     rax, [rdi+10h]
0x180009369  mov     [rsp+78h+arg_18], rdi
0x180009371  mov     rdi, rax
0x180009374  mov     [rsp+78h+var_48], rax
0x180009379  test    rax, rax
0x18000937c  jnz     short loc_180009304
0x18000937e  jmp     short loc_1800093A8
0x180009380  lea     rax, [rsp+78h+arg_0]
0x180009388  mov     rdx, rsi; struct LKRhash::CBucket *
0x18000938b  lea     r9, [rsp+78h+arg_18]; struct LKRhash::CNodeClump **
0x180009393  mov     [rsp+78h+var_58], rax; int *
0x180009398  lea     r8, [rsp+78h+var_48]; struct LKRhash::CNodeClump **
0x18000939d  mov     rcx, rbx; this
0x1800093a0  call    ?_DeleteNode@CLKRLinearHashTable@LKRhash@@AEAA_NQEAVCBucket@2@AEAPEAVCNodeClump@2@1AEAH@Z; LKRhash::CLKRLinearHashTable::_DeleteNode(LKRhash::CBucket * const,LKRhash::CNodeClump * &,LKRhash::CNodeClump * &,int &)
0x1800093a5  xor     r15d, r15d
0x1800093a8  cmp     byte ptr [rbx+99h], 0
0x1800093af  jz      short loc_1800093C9
0x1800093b1  mov     edx, [rsi]
0x1800093b3  mov     eax, edx
0x1800093b5  lea     ecx, [rdx-10000h]
0x1800093bb  and     ecx, 0FFFF0000h
0x1800093c1  lock cmpxchg [rsi], ecx
0x1800093c5  cmp     edx, eax
0x1800093c7  jmp     short loc_1800093AF
0x1800093c9  test    r15d, r15d
0x1800093cc  jnz     short loc_180009415
0x1800093ce  mov     eax, [rbx+78h]
0x1800093d1  xorps   xmm6, xmm6
0x1800093d4  shr     eax, 4
0x1800093d7  xorps   xmm0, xmm0
0x1800093da  add     eax, [rbx+78h]
0x1800093dd  cvtsi2sd xmm6, rax
0x1800093e2  mov     eax, [rbx+7Ch]
0x1800093e5  cvtsi2sd xmm0, rax
0x1800093ea  jmp     short loc_18000940A
0x1800093ec  cmp     eax, [rbx+48h]
0x1800093ef  jbe     short loc_180009415
0x1800093f1  mov     rcx, rbx
0x1800093f4  call    ?_Contract@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@XZ; LKRhash::CLKRLinearHashTable::_Contract(void)
0x1800093f9  test    eax, eax
0x1800093fb  jnz     short loc_180009415
0x1800093fd  mov     ecx, [rbx+7Ch]
0x180009400  xorps   xmm0, xmm0
0x180009403  mov     eax, ecx
0x180009405  cvtsi2sd xmm0, rcx
0x18000940a  mulsd   xmm0, qword ptr [rbx+50h]
0x18000940f  comisd  xmm0, xmm6
0x180009413  ja      short loc_1800093EC
0x180009415  mov     eax, r15d
0x180009418  movaps  xmm6, [rsp+78h+var_38]
0x18000941d  lea     r11, [rsp+78h+var_28]
0x180009422  mov     rbx, [r11+38h]
0x180009426  mov     rbp, [r11+40h]
0x18000942a  mov     rsp, r11
0x18000942d  pop     r15
0x18000942f  pop     r13
0x180009431  pop     r12
0x180009433  pop     rdi
0x180009434  pop     rsi
0x180009435  retn
```
