# FltpDeleteContextList

- ea: `0x180062ba0`
- end: `0x180062da7`
- name: `FltpDeleteContextList`
- size: `519`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180060fd0`
- `0x1800616f0`
- `0x180062050`
- `0x180062b70`
- `0x180063b40`
- `0x180068e20`

## callees

- `0x180009f20`
- `0x18000f5b0`
- `0x180010540`
- `0x180010ab0`
- `0x180012d80`
- `0x18005dcc0`
- `0x180062ba0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180062ccc`
- `ntoskrnl!ObfDereferenceObject` at `0x180062ccc`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180062bb7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180062bb7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180062c07`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180062c07`
- `ntoskrnl!ZwClose` at `0x180062cdf`
- `ntoskrnl!ZwClose` at `0x180062cdf`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180062bc8`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180062bc8`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180062bfb`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180062bfb`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x180062ca0`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x180062ca0`

## pseudocode

```c
void __fastcall FltpDeleteContextList(__int64 a1, __int64 a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  void *v10; // rax
  struct _KENLISTMENT *v11; // rcx
  unsigned int OnlyEnlistment; // eax
  signed __int64 v13; // rax
  unsigned int i; // r8d
  signed __int64 v15; // rax
  char *v16; // rax
  _QWORD *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx

  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(a2, 0);
  v8 = TreeUnlinkMulti((_QWORD *)(a1 + 128), a3, a4);
  if ( FltpVelocity )
  {
    for ( i = 0; i < 8; i += 4 )
    {
      v17 = (_QWORD *)(a1 + 16LL * i);
      v18 = v17[1];
      if ( v18 && (a3 == -1 || a3 == *(_QWORD *)(v18 + 56)) && (a4 == -1 || a4 == *(_QWORD *)(v18 + 64)) )
      {
        do
        {
          _m_prefetchw(v17);
          v19 = 0;
          if ( (_InterlockedOr64(v17, 1u) & 1) == 0 )
            v19 = a1 + 16LL * i;
        }
        while ( !v19 );
        v20 = v17[1];
        v17[1] = 0;
        _InterlockedAnd64(v17, 0);
        *(_DWORD *)(v20 + 72) &= ~0x10000u;
        *(_OWORD *)(v20 + 24) = 0;
        *(_QWORD *)(v20 + 48) = 0;
        *(_QWORD *)(v20 + 40) = v8;
        v8 = v20 + 24;
      }
      v21 = (_QWORD *)(a1 + 16LL * (i + 1));
      v22 = v21[1];
      if ( v22 && (a3 == -1 || a3 == *(_QWORD *)(v22 + 56)) && (a4 == -1 || a4 == *(_QWORD *)(v22 + 64)) )
      {
        do
        {
          _m_prefetchw(v21);
          v23 = 0;
          if ( (_InterlockedOr64(v21, 1u) & 1) == 0 )
            v23 = a1 + 16LL * (i + 1);
        }
        while ( !v23 );
        v24 = v21[1];
        v21[1] = 0;
        _InterlockedAnd64(v21, 0);
        *(_OWORD *)(v24 + 24) = 0;
        *(_QWORD *)(v24 + 40) = 0;
        *(_QWORD *)(v24 + 48) = 0;
        *(_DWORD *)(v24 + 72) &= ~0x10000u;
        *(_QWORD *)(v24 + 40) = v8;
        v8 = v24 + 24;
      }
      v25 = (_QWORD *)(a1 + 16LL * (i + 2));
      v26 = v25[1];
      if ( v26 && (a3 == -1 || a3 == *(_QWORD *)(v26 + 56)) && (a4 == -1 || a4 == *(_QWORD *)(v26 + 64)) )
      {
        do
        {
          _m_prefetchw(v25);
          v27 = 0;
          if ( (_InterlockedOr64(v25, 1u) & 1) == 0 )
            v27 = a1 + 16LL * (i + 2);
        }
        while ( !v27 );
        v28 = v25[1];
        v25[1] = 0;
        _InterlockedAnd64(v25, 0);
        *(_OWORD *)(v28 + 24) = 0;
        *(_QWORD *)(v28 + 40) = 0;
        *(_QWORD *)(v28 + 48) = 0;
        *(_DWORD *)(v28 + 72) &= ~0x10000u;
        *(_QWORD *)(v28 + 40) = v8;
        v8 = v28 + 24;
      }
      v29 = (_QWORD *)(a1 + 16LL * (i + 3));
      v30 = v29[1];
      if ( v30 && (a3 == -1 || a3 == *(_QWORD *)(v30 + 56)) && (a4 == -1 || a4 == *(_QWORD *)(v30 + 64)) )
      {
        do
        {
          _m_prefetchw(v29);
          v31 = 0;
          if ( (_InterlockedOr64(v29, 1u) & 1) == 0 )
            v31 = a1 + 16LL * (i + 3);
        }
        while ( !v31 );
        v32 = v29[1];
        v29[1] = 0;
        _InterlockedAnd64(v29, 0);
        *(_OWORD *)(v32 + 24) = 0;
        *(_QWORD *)(v32 + 40) = 0;
        *(_QWORD *)(v32 + 48) = 0;
        *(_DWORD *)(v32 + 72) &= ~0x10000u;
        *(_QWORD *)(v32 + 40) = v8;
        v8 = v32 + 24;
      }
    }
  }
  ExReleaseAutoExpandPushLockExclusive(a2, 0);
  KeLeaveGuardedRegion();
  if ( v8 )
  {
    do
    {
      v9 = *(_QWORD *)(v8 + 16);
      switch ( *(_WORD *)(*(_QWORD *)(v8 - 16) + 24LL) )
      {
        case 1:
        case 2:
          v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 - 8), 0, *(_QWORD *)(v8 - 8));
          if ( v15 )
            goto LABEL_63;
          break;
        case 4:
          v10 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)(v8 - 8), 0, *(_QWORD *)(v8 - 8));
          if ( v10 )
            FltpReleaseFileListCtrl(v10);
          break;
        case 8:
        case 0x10:
        case 0x40:
          v16 = (char *)_InterlockedCompareExchange64((volatile signed __int64 *)(v8 - 8), 0, *(_QWORD *)(v8 - 8));
          if ( v16 )
            FltpReleaseStreamListCtrl(v16);
          break;
        case 0x20:
          v11 = *(struct _KENLISTMENT **)(*(_QWORD *)(v8 - 24) + 8LL);
          if ( v11 == (struct _KENLISTMENT *)-1LL )
          {
            v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 - 8), 0, *(_QWORD *)(v8 - 8));
            if ( v15 )
LABEL_63:
              FltpObjectPointerDereference(v15);
          }
          else
          {
            OnlyEnlistment = TmReadOnlyEnlistment(v11, 0);
            if ( (int)FltpDbgStatus(OnlyEnlistment, "minkernel\\fs\\filtermgr\\filter\\contextsup.c", 1020, 0) < 0 )
            {
              if ( *(_QWORD *)(v8 - 8) && (*(_DWORD *)(v8 + 48) & 4) == 0 )
                _InterlockedOr((volatile signed __int32 *)(v8 + 48), 4u);
            }
            else
            {
              ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(v8 - 24) + 8LL));
              ZwClose(**(HANDLE **)(v8 - 24));
              *(_QWORD *)(*(_QWORD *)(v8 - 24) + 8LL) = -1;
              **(_QWORD **)(v8 - 24) = 0;
              v13 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 - 8), 0, *(_QWORD *)(v8 - 8));
              if ( v13 )
                FltpObjectPointerDereference(v13);
              DoReleaseContext((HANDLE **)(v8 - 24));
            }
          }
          break;
        default:
          break;
      }
      DoReleaseContext((HANDLE **)(v8 - 24));
      v8 = v9;
    }
    while ( v9 );
  }
}

```

## disassembly

```asm
0x180062ba0  push    rbx
0x180062ba2  push    rbp
0x180062ba3  push    rsi
0x180062ba4  push    rdi
0x180062ba5  push    r14
0x180062ba7  sub     rsp, 20h
0x180062bab  mov     rsi, r9
0x180062bae  mov     rbp, r8
0x180062bb1  mov     rdi, rdx
0x180062bb4  mov     r14, rcx
0x180062bb7  call    cs:__imp_KeEnterGuardedRegion
0x180062bbe  nop     dword ptr [rax+rax+00h]
0x180062bc3  xor     edx, edx
0x180062bc5  mov     rcx, rdi
0x180062bc8  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x180062bcf  nop     dword ptr [rax+rax+00h]
0x180062bd4  lea     rcx, [r14+80h]
0x180062bdb  mov     r8, rsi
0x180062bde  mov     rdx, rbp
0x180062be1  call    TreeUnlinkMulti
0x180062be6  cmp     cs:FltpVelocity, 0
0x180062bed  mov     rbx, rax
0x180062bf0  jnz     loc_180062D49
0x180062bf6  xor     edx, edx
0x180062bf8  mov     rcx, rdi
0x180062bfb  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180062c02  nop     dword ptr [rax+rax+00h]
0x180062c07  call    cs:__imp_KeLeaveGuardedRegion
0x180062c0e  nop     dword ptr [rax+rax+00h]
0x180062c13  test    rbx, rbx
0x180062c16  jnz     short loc_180062C24
0x180062c18  add     rsp, 20h
0x180062c1c  pop     r14
0x180062c1e  pop     rdi
0x180062c1f  pop     rsi
0x180062c20  pop     rbp
0x180062c21  pop     rbx
0x180062c22  retn
0x180062c24  lea     rsi, cs:180000000h
0x180062c2b  mov     ebp, 3FCh
0x180062c30  mov     rax, [rbx-10h]
0x180062c34  mov     rdi, [rbx+10h]
0x180062c38  movzx   ecx, word ptr [rax+18h]
0x180062c3c  dec     ecx; switch 64 cases
0x180062c3e  cmp     ecx, 3Fh
0x180062c41  jbe     short loc_180062C56
0x180062c43  lea     rcx, [rbx-18h]; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062c47  call    DoReleaseContext
0x180062c4c  mov     rbx, rdi
0x180062c4f  test    rdi, rdi
0x180062c52  jz      short loc_180062C18
0x180062c54  jmp     short loc_180062C30
0x180062c56  movsxd  rax, ecx
0x180062c59  movzx   eax, ds:(byte_180031DE1 - 180000000h)[rsi+rax]
0x180062c61  mov     ecx, ds:(jpt_180062C6B - 180000000h)[rsi+rax*4]
0x180062c68  add     rcx, rsi
0x180062c6b  jmp     rcx; switch jump
0x180062c71  mov     rax, [rbx-8]; jumptable 0000000180062C6B case 4
0x180062c75  xor     ecx, ecx
0x180062c77  lock cmpxchg [rbx-8], rcx
0x180062c7d  test    rax, rax
0x180062c80  jz      short def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062c82  mov     rcx, rax; Entry
0x180062c85  call    FltpReleaseFileListCtrl
0x180062c8a  jmp     short def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062c8c  mov     rax, [rbx-18h]; jumptable 0000000180062C6B case 32
0x180062c90  mov     rcx, [rax+8]; Enlistment
0x180062c94  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180062c98  jz      loc_180062D8D
0x180062c9e  xor     edx, edx; TmVirtualClock
0x180062ca0  call    cs:__imp_TmReadOnlyEnlistment
0x180062ca7  nop     dword ptr [rax+rax+00h]
0x180062cac  xor     r9d, r9d
0x180062caf  lea     rdx, aMinkernelFsFil_9; "minkernel\\fs\\filtermgr\\filter\\conte"...
0x180062cb6  mov     ecx, eax
0x180062cb8  mov     r8d, ebp
0x180062cbb  call    FltpDbgStatus
0x180062cc0  test    eax, eax
0x180062cc2  js      short loc_180062D29
0x180062cc4  mov     rcx, [rbx-18h]
0x180062cc8  mov     rcx, [rcx+8]; Object
0x180062ccc  call    cs:__imp_ObfDereferenceObject
0x180062cd3  nop     dword ptr [rax+rax+00h]
0x180062cd8  mov     rcx, [rbx-18h]
0x180062cdc  mov     rcx, [rcx]; Handle
0x180062cdf  call    cs:__imp_ZwClose
0x180062ce6  nop     dword ptr [rax+rax+00h]
0x180062ceb  mov     rax, [rbx-18h]
0x180062cef  xor     ecx, ecx
0x180062cf1  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180062cf9  mov     rax, [rbx-18h]
0x180062cfd  mov     qword ptr [rax], 0
0x180062d04  mov     rax, [rbx-8]
0x180062d08  lock cmpxchg [rbx-8], rcx
0x180062d0e  test    rax, rax
0x180062d11  jz      short loc_180062D1B
0x180062d13  mov     rcx, rax
0x180062d16  call    FltpObjectPointerDereference
0x180062d1b  lea     rcx, [rbx-18h]; BugCheckParameter3
0x180062d1f  call    DoReleaseContext
0x180062d24  jmp     def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d29  cmp     qword ptr [rbx-8], 0
0x180062d2e  jz      def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d34  mov     eax, [rbx+30h]
0x180062d37  test    al, 4
0x180062d39  jnz     def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d3f  lock or dword ptr [rbx+30h], 4
0x180062d44  jmp     def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d49  xor     r8d, r8d
0x180062d4c  jmp     loc_18007A152
0x180062d51  mov     rax, [rbx-8]; jumptable 0000000180062C6B cases 1,2
0x180062d55  xor     ecx, ecx
0x180062d57  lock cmpxchg [rbx-8], rcx
0x180062d5d  test    rax, rax
0x180062d60  jz      def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d66  jmp     loc_18007A364
0x180062d6b  mov     rax, [rbx-8]; jumptable 0000000180062C6B cases 8,16,64
0x180062d6f  xor     ecx, ecx
0x180062d71  lock cmpxchg [rbx-8], rcx
0x180062d77  test    rax, rax
0x180062d7a  jz      def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d80  mov     rcx, rax; Entry
0x180062d83  call    FltpReleaseStreamListCtrl
0x180062d88  jmp     def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062d8d  mov     rax, [rbx-8]
0x180062d91  xor     ecx, ecx
0x180062d93  lock cmpxchg [rbx-8], rcx
0x180062d99  test    rax, rax
0x180062d9c  jz      def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
0x180062da2  jmp     loc_18007A364
0x18007a152  mov     edx, r8d
0x18007a155  shl     rdx, 4
0x18007a159  add     rdx, r14
0x18007a15c  mov     rax, [rdx+8]
0x18007a160  test    rax, rax
0x18007a163  jz      short loc_18007A1CE
0x18007a165  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18007a169  jz      short loc_18007A171
0x18007a16b  cmp     rbp, [rax+38h]
0x18007a16f  jnz     short loc_18007A1CE
0x18007a171  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a175  jz      short loc_18007A17D
0x18007a177  cmp     rsi, [rax+40h]
0x18007a17b  jnz     short loc_18007A1CE
0x18007a17d  prefetchw byte ptr [rdx]
0x18007a180  mov     rax, [rdx]
0x18007a183  mov     rcx, rax
0x18007a186  or      rcx, 1
0x18007a18a  lock cmpxchg [rdx], rcx
0x18007a18f  jnz     short loc_18007A183
0x18007a191  test    al, 1
0x18007a193  mov     eax, 0
0x18007a198  cmovz   rax, rdx
0x18007a19c  test    rax, rax
0x18007a19f  jz      short loc_18007A17D
0x18007a1a1  mov     rcx, [rdx+8]
0x18007a1a5  mov     qword ptr [rdx+8], 0
0x18007a1ad  lock and qword ptr [rdx], 0
0x18007a1b2  xor     edx, edx
0x18007a1b4  xorps   xmm0, xmm0
0x18007a1b7  and     dword ptr [rcx+48h], 0FFFEFFFFh
0x18007a1be  movups  xmmword ptr [rcx+18h], xmm0
0x18007a1c2  mov     [rcx+30h], rdx
0x18007a1c6  mov     [rcx+28h], rbx
0x18007a1ca  lea     rbx, [rcx+18h]
0x18007a1ce  lea     edx, [r8+1]
0x18007a1d2  shl     rdx, 4
0x18007a1d6  add     rdx, r14
0x18007a1d9  mov     rax, [rdx+8]
0x18007a1dd  test    rax, rax
0x18007a1e0  jz      short loc_18007A24F
0x18007a1e2  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18007a1e6  jz      short loc_18007A1EE
0x18007a1e8  cmp     rbp, [rax+38h]
0x18007a1ec  jnz     short loc_18007A24F
0x18007a1ee  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a1f2  jz      short loc_18007A1FA
0x18007a1f4  cmp     rsi, [rax+40h]
0x18007a1f8  jnz     short loc_18007A24F
0x18007a1fa  prefetchw byte ptr [rdx]
0x18007a1fd  mov     rax, [rdx]
0x18007a200  mov     rcx, rax
0x18007a203  or      rcx, 1
0x18007a207  lock cmpxchg [rdx], rcx
0x18007a20c  jnz     short loc_18007A200
0x18007a20e  test    al, 1
0x18007a210  mov     eax, 0
0x18007a215  cmovz   rax, rdx
0x18007a219  test    rax, rax
0x18007a21c  jz      short loc_18007A1FA
0x18007a21e  mov     rcx, [rdx+8]
0x18007a222  mov     qword ptr [rdx+8], 0
0x18007a22a  lock and qword ptr [rdx], 0
0x18007a22f  xor     edx, edx
0x18007a231  xorps   xmm0, xmm0
0x18007a234  movups  xmmword ptr [rcx+18h], xmm0
0x18007a238  mov     [rcx+28h], rdx
0x18007a23c  mov     [rcx+30h], rdx
0x18007a240  and     dword ptr [rcx+48h], 0FFFEFFFFh
0x18007a247  mov     [rcx+28h], rbx
0x18007a24b  lea     rbx, [rcx+18h]
0x18007a24f  lea     edx, [r8+2]
0x18007a253  shl     rdx, 4
0x18007a257  add     rdx, r14
0x18007a25a  mov     rax, [rdx+8]
0x18007a25e  test    rax, rax
0x18007a261  jz      short loc_18007A2D0
0x18007a263  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18007a267  jz      short loc_18007A26F
0x18007a269  cmp     rbp, [rax+38h]
0x18007a26d  jnz     short loc_18007A2D0
0x18007a26f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a273  jz      short loc_18007A27B
0x18007a275  cmp     rsi, [rax+40h]
0x18007a279  jnz     short loc_18007A2D0
0x18007a27b  prefetchw byte ptr [rdx]
0x18007a27e  mov     rax, [rdx]
0x18007a281  mov     rcx, rax
0x18007a284  or      rcx, 1
0x18007a288  lock cmpxchg [rdx], rcx
0x18007a28d  jnz     short loc_18007A281
0x18007a28f  test    al, 1
0x18007a291  mov     eax, 0
0x18007a296  cmovz   rax, rdx
0x18007a29a  test    rax, rax
0x18007a29d  jz      short loc_18007A27B
0x18007a29f  mov     rcx, [rdx+8]
0x18007a2a3  mov     qword ptr [rdx+8], 0
0x18007a2ab  lock and qword ptr [rdx], 0
0x18007a2b0  xor     edx, edx
0x18007a2b2  xorps   xmm0, xmm0
0x18007a2b5  movups  xmmword ptr [rcx+18h], xmm0
0x18007a2b9  mov     [rcx+28h], rdx
0x18007a2bd  mov     [rcx+30h], rdx
0x18007a2c1  and     dword ptr [rcx+48h], 0FFFEFFFFh
0x18007a2c8  mov     [rcx+28h], rbx
0x18007a2cc  lea     rbx, [rcx+18h]
0x18007a2d0  lea     edx, [r8+3]
0x18007a2d4  shl     rdx, 4
0x18007a2d8  add     rdx, r14
0x18007a2db  mov     rax, [rdx+8]
0x18007a2df  test    rax, rax
0x18007a2e2  jz      short loc_18007A351
0x18007a2e4  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18007a2e8  jz      short loc_18007A2F0
0x18007a2ea  cmp     rbp, [rax+38h]
0x18007a2ee  jnz     short loc_18007A351
0x18007a2f0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a2f4  jz      short loc_18007A2FC
0x18007a2f6  cmp     rsi, [rax+40h]
0x18007a2fa  jnz     short loc_18007A351
0x18007a2fc  prefetchw byte ptr [rdx]
0x18007a2ff  mov     rax, [rdx]
0x18007a302  mov     rcx, rax
0x18007a305  or      rcx, 1
0x18007a309  lock cmpxchg [rdx], rcx
0x18007a30e  jnz     short loc_18007A302
0x18007a310  test    al, 1
0x18007a312  mov     eax, 0
0x18007a317  cmovz   rax, rdx
0x18007a31b  test    rax, rax
0x18007a31e  jz      short loc_18007A2FC
0x18007a320  mov     rcx, [rdx+8]
0x18007a324  mov     qword ptr [rdx+8], 0
0x18007a32c  lock and qword ptr [rdx], 0
0x18007a331  xor     edx, edx
0x18007a333  xorps   xmm0, xmm0
0x18007a336  movups  xmmword ptr [rcx+18h], xmm0
0x18007a33a  mov     [rcx+28h], rdx
0x18007a33e  mov     [rcx+30h], rdx
0x18007a342  and     dword ptr [rcx+48h], 0FFFEFFFFh
0x18007a349  mov     [rcx+28h], rbx
0x18007a34d  lea     rbx, [rcx+18h]
0x18007a351  add     r8d, 4
0x18007a355  cmp     r8d, 8
0x18007a359  jb      loc_18007A152
0x18007a35f  jmp     loc_180062BF6
0x18007a364  mov     rcx, rax
0x18007a367  call    FltpObjectPointerDereference
0x18007a36c  nop
0x18007a36d  jmp     def_180062C6B; jumptable 0000000180062C6B default case, cases 3,5-7,9-15,17-31,33-63
```
