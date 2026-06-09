# LKRhash::CLKRLinearHashTable::_Clear(bool)

- ea: `0x1800089a4`
- end: `0x180008bee`
- name: `?_Clear@CLKRLinearHashTable@LKRhash@@AEAAX_N@Z`
- size: `586`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007e18`
- `0x180008250`

## callees

- `0x1800075f0`
- `0x1800089a4`
- `0x180009af0`
- `0x180009b54`
- `0x18000a330`
- `0x18000b010`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_Clear(LKRhash::CLKRLinearHashTable *this, char a2)
{
  unsigned int v2; // r15d
  char v3; // r14
  unsigned int i; // r13d
  unsigned __int64 v6; // rbx
  signed __int32 v7; // edx
  signed __int32 v8; // edx
  bool j; // zf
  signed __int32 v10; // edx
  int v11; // r12d
  unsigned __int64 v12; // rsi
  __int64 v13; // r14
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  signed __int32 v16; // edx
  bool k; // zf
  signed __int32 v18; // r8d
  unsigned int m; // esi
  __int64 v20; // rdx
  __int64 v21; // r8

  v2 = 0;
  v3 = a2;
  if ( !*((_DWORD *)this + 5) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 30, 0) )
    {
      for ( i = 0; i < *((_DWORD *)this + 31); ++i )
      {
        v6 = *(_QWORD *)(*((_QWORD *)this + 13) + 8 * ((unsigned __int64)i >> *((_DWORD *)this + 17)))
           + ((unsigned __int64)(i & *((_DWORD *)this + 19)) << 6);
        if ( v3 )
        {
          if ( *((_BYTE *)this + 153) )
          {
            if ( (unsigned __int16)*(_DWORD *)v6
              || (v7 = *(_DWORD *)v6,
                  v7 != _InterlockedCompareExchange((volatile signed __int32 *)v6, (v7 + 0x10000) | 0xFFFF, v7)) )
            {
              do
                v8 = *(_DWORD *)v6;
              while ( v8 != _InterlockedCompareExchange((volatile signed __int32 *)v6, v8 + 0x10000, v8) );
              CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v6, 1);
            }
          }
        }
        if ( *(_DWORD *)(v6 + 8) == 31678523 )
        {
          if ( v3 )
          {
            for ( j = *((_BYTE *)this + 153) == 0;
                  !j;
                  j = v10 == _InterlockedCompareExchange(
                               (volatile signed __int32 *)v6,
                               (v10 - 0x10000) & 0xFFFF0000,
                               v10) )
            {
              v10 = *(_DWORD *)v6;
            }
          }
        }
        else
        {
          v11 = 0;
          v12 = v6 + 8;
          do
          {
            do
            {
              v13 = v2;
              if ( *(_DWORD *)(v12 + 4LL * v2) == 31678523 )
                break;
              (*((void (__fastcall **)(_QWORD, __int64))this + 7))(*(_QWORD *)(v12 + 8LL * v2 + 24), 0xFFFFFFFFLL);
              ++v11;
              *(_QWORD *)(v12 + 8LL * v2++ + 24) = 0;
              *(_DWORD *)(v12 + 4 * v13) = 31678523;
            }
            while ( (int)v2 < 4 );
            v14 = v12;
            v15 = (_QWORD *)(v12 + 16);
            v12 = *(_QWORD *)(v12 + 16);
            v2 = 0;
            *v15 = 0;
            if ( v14 != v6 + 8 )
              (*(void (__fastcall **)(_QWORD, unsigned __int64, __int64))(**((_QWORD **)this + 18) + 8LL))(
                *((_QWORD *)this + 18),
                v14,
                4);
          }
          while ( v12 );
          v3 = a2;
          if ( a2 )
          {
            v16 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 30, -v11);
            for ( k = *((_BYTE *)this + 153) == 0;
                  !k;
                  k = v18 == _InterlockedCompareExchange(
                               (volatile signed __int32 *)v6,
                               (v18 - 0x10000) & 0xFFFF0000,
                               v18) )
            {
              v18 = *(_DWORD *)v6;
            }
          }
          else
          {
            v16 = *((_DWORD *)this + 30);
            *((_DWORD *)this + 30) = v16 - v11;
          }
          if ( v11 == v16 )
            break;
        }
      }
    }
    for ( m = 0; m < *((_DWORD *)this + 31); m += *((_DWORD *)this + 18) )
    {
      LKRhash::CLKRLinearHashTable::_FreeSegment(
        this,
        *(struct LKRhash::CSegment **)(*((_QWORD *)this + 13) + 8 * ((unsigned __int64)m >> *((_DWORD *)this + 17))));
      *(_QWORD *)(*((_QWORD *)this + 13) + 8 * ((unsigned __int64)m >> *((_DWORD *)this + 17))) = 0;
    }
    LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(this);
    *(_QWORD *)((char *)this + 92) = 3;
    *((_DWORD *)this + 31) = 0;
    *((_DWORD *)this + 28) = 0;
    *((_DWORD *)this + 22) = 1;
    if ( v3 )
    {
      v20 = *((unsigned int *)this + 16);
      if ( (_DWORD)v20 == 1 )
      {
        v21 = 8;
      }
      else if ( (_DWORD)v20 == 2 )
      {
        v21 = 128;
      }
      else
      {
        v21 = 0;
        if ( (_DWORD)v20 == 3 )
          v21 = 2048;
      }
      LKRhash::CLKRLinearHashTable::_SetSegVars(this, v20, v21);
    }
  }
}

```

## disassembly

```asm
0x1800089a4  mov     [rsp+arg_8], dl
0x1800089a8  push    rbx
0x1800089a9  push    rbp
0x1800089aa  push    rsi
0x1800089ab  push    rdi
0x1800089ac  push    r12
0x1800089ae  push    r13
0x1800089b0  push    r14
0x1800089b2  push    r15
0x1800089b4  sub     rsp, 28h
0x1800089b8  xor     r15d, r15d
0x1800089bb  mov     r14b, dl
0x1800089be  mov     rdi, rcx
0x1800089c1  cmp     [rcx+14h], r15d
0x1800089c5  jnz     loc_180008BDD
0x1800089cb  mov     eax, r15d
0x1800089ce  lock xadd [rcx+78h], eax
0x1800089d3  test    eax, eax
0x1800089d5  jz      loc_180008B50
0x1800089db  mov     r13d, r15d
0x1800089de  cmp     [rcx+7Ch], r15d
0x1800089e2  jbe     loc_180008B50
0x1800089e8  mov     ecx, [rdi+44h]
0x1800089eb  mov     ebx, [rdi+4Ch]
0x1800089ee  mov     edx, r13d
0x1800089f1  shr     rdx, cl
0x1800089f4  mov     rcx, [rdi+68h]
0x1800089f8  mov     eax, r13d
0x1800089fb  and     rbx, rax
0x1800089fe  shl     rbx, 6
0x180008a02  add     rbx, [rcx+rdx*8]
0x180008a06  test    r14b, r14b
0x180008a09  jz      short loc_180008A4D
0x180008a0b  cmp     [rdi+99h], r15b
0x180008a12  jz      short loc_180008A4D
0x180008a14  mov     edx, [rbx]
0x180008a16  test    dx, dx
0x180008a19  jnz     short loc_180008A31
0x180008a1b  lea     ecx, [rdx+10000h]
0x180008a21  mov     eax, edx
0x180008a23  or      ecx, 0FFFFh
0x180008a29  lock cmpxchg [rbx], ecx
0x180008a2d  cmp     edx, eax
0x180008a2f  jz      short loc_180008A4D
0x180008a31  mov     edx, [rbx]
0x180008a33  mov     eax, edx
0x180008a35  lea     ecx, [rdx+10000h]
0x180008a3b  lock cmpxchg [rbx], ecx
0x180008a3f  cmp     edx, eax
0x180008a41  jnz     short loc_180008A31
0x180008a43  mov     dl, 1; bool
0x180008a45  mov     rcx, rbx; this
0x180008a48  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180008a4d  lea     rbp, [rbx+8]
0x180008a51  cmp     dword ptr [rbp+0], 1E3603Bh
0x180008a58  jnz     short loc_180008A88
0x180008a5a  test    r14b, r14b
0x180008a5d  jz      loc_180008B43
0x180008a63  cmp     [rdi+99h], r15b
0x180008a6a  jz      loc_180008B43
0x180008a70  mov     edx, [rbx]
0x180008a72  mov     eax, edx
0x180008a74  lea     ecx, [rdx-10000h]
0x180008a7a  and     ecx, 0FFFF0000h
0x180008a80  lock cmpxchg [rbx], ecx
0x180008a84  cmp     edx, eax
0x180008a86  jmp     short loc_180008A6A
0x180008a88  mov     r12d, r15d
0x180008a8b  mov     rsi, rbp
0x180008a8e  mov     r14d, r15d
0x180008a91  cmp     dword ptr [rsi+r14*4], 1E3603Bh
0x180008a99  jz      short loc_180008AC9
0x180008a9b  mov     rcx, [rsi+r14*8+18h]
0x180008aa0  or      edx, 0FFFFFFFFh
0x180008aa3  mov     rax, [rdi+38h]
0x180008aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aac  inc     r12d
0x180008aaf  mov     qword ptr [rsi+r14*8+18h], 0
0x180008ab8  inc     r15d
0x180008abb  mov     dword ptr [rsi+r14*4], 1E3603Bh
0x180008ac3  cmp     r15d, 4
0x180008ac7  jl      short loc_180008A8E
0x180008ac9  mov     rdx, rsi
0x180008acc  lea     rax, [rsi+10h]
0x180008ad0  mov     rsi, [rax]
0x180008ad3  xor     r15d, r15d
0x180008ad6  mov     [rax], r15
0x180008ad9  cmp     rdx, rbp
0x180008adc  jz      short loc_180008AF5
0x180008ade  mov     rcx, [rdi+90h]
0x180008ae5  lea     r8d, [r15+4]
0x180008ae9  mov     rax, [rcx]
0x180008aec  mov     rax, [rax+8]
0x180008af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af5  test    rsi, rsi
0x180008af8  jnz     short loc_180008A8E
0x180008afa  mov     r14b, [rsp+68h+arg_8]
0x180008aff  test    r14b, r14b
0x180008b02  jz      short loc_180008B33
0x180008b04  mov     edx, r12d
0x180008b07  neg     edx
0x180008b09  lock xadd [rdi+78h], edx
0x180008b0e  cmp     [rdi+99h], r15b
0x180008b15  jz      short loc_180008B3E
0x180008b17  mov     r8d, [rbx]
0x180008b1a  mov     eax, r8d
0x180008b1d  lea     ecx, [r8-10000h]
0x180008b24  and     ecx, 0FFFF0000h
0x180008b2a  lock cmpxchg [rbx], ecx
0x180008b2e  cmp     r8d, eax
0x180008b31  jmp     short loc_180008B15
0x180008b33  mov     edx, [rdi+78h]
0x180008b36  mov     eax, edx
0x180008b38  sub     eax, r12d
0x180008b3b  mov     [rdi+78h], eax
0x180008b3e  cmp     r12d, edx
0x180008b41  jz      short loc_180008B50
0x180008b43  inc     r13d
0x180008b46  cmp     r13d, [rdi+7Ch]
0x180008b4a  jb      loc_1800089E8
0x180008b50  mov     esi, r15d
0x180008b53  cmp     [rdi+7Ch], r15d
0x180008b57  jbe     short loc_180008B89
0x180008b59  mov     ecx, [rdi+44h]
0x180008b5c  mov     rdx, [rdi+68h]
0x180008b60  mov     eax, esi
0x180008b62  shr     rax, cl
0x180008b65  mov     rcx, rdi; this
0x180008b68  mov     ebx, esi
0x180008b6a  mov     rdx, [rdx+rax*8]; struct LKRhash::CSegment *
0x180008b6e  call    ?_FreeSegment@CLKRLinearHashTable@LKRhash@@AEBA_NPEAVCSegment@2@@Z; LKRhash::CLKRLinearHashTable::_FreeSegment(LKRhash::CSegment *)
0x180008b73  mov     ecx, [rdi+44h]
0x180008b76  mov     rax, [rdi+68h]
0x180008b7a  shr     rbx, cl
0x180008b7d  mov     [rax+rbx*8], r15
0x180008b81  add     esi, [rdi+48h]
0x180008b84  cmp     esi, [rdi+7Ch]
0x180008b87  jb      short loc_180008B59
0x180008b89  mov     rcx, rdi; this
0x180008b8c  call    ?_FreeSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAA_NXZ; LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(void)
0x180008b91  mov     qword ptr [rdi+5Ch], 3
0x180008b99  mov     [rdi+7Ch], r15d
0x180008b9d  mov     [rdi+70h], r15d
0x180008ba1  mov     dword ptr [rdi+58h], 1
0x180008ba8  test    r14b, r14b
0x180008bab  jz      short loc_180008BDD
0x180008bad  mov     edx, [rdi+40h]
0x180008bb0  cmp     edx, 1
0x180008bb3  jnz     short loc_180008BBB
0x180008bb5  lea     r8d, [rdx+7]
0x180008bb9  jmp     short loc_180008BD5
0x180008bbb  cmp     edx, 2
0x180008bbe  jnz     short loc_180008BC6
0x180008bc0  lea     r8d, [rdx+7Eh]
0x180008bc4  jmp     short loc_180008BD5
0x180008bc6  cmp     edx, 3
0x180008bc9  mov     r8d, r15d
0x180008bcc  mov     eax, 800h
0x180008bd1  cmovz   r8d, eax
0x180008bd5  mov     rcx, rdi
0x180008bd8  call    ?_SetSegVars@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@W4LK_TABLESIZE@2@K@Z; LKRhash::CLKRLinearHashTable::_SetSegVars(LKRhash::LK_TABLESIZE,ulong)
0x180008bdd  add     rsp, 28h
0x180008be1  pop     r15
0x180008be3  pop     r14
0x180008be5  pop     r13
0x180008be7  pop     r12
0x180008be9  pop     rdi
0x180008bea  pop     rsi
0x180008beb  pop     rbp
0x180008bec  pop     rbx
0x180008bed  retn
```
