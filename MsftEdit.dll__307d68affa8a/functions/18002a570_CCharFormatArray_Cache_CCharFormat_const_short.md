# CCharFormatArray::Cache(CCharFormat const *,short *)

- ea: `0x18002a570`
- end: `0x18002a7f6`
- name: `?Cache@CCharFormatArray@@UEAAJPEBVCCharFormat@@PEAF@Z`
- size: `646`
- prototype: `int(CCharFormatArray *__hidden this, const struct CCharFormat *, __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18002a570`
- `0x18002ab44`
- `0x18002af88`
- `0x1800810b8`
- `0x1800b8adc`
- `0x18013c8f2`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a724`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a72a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a72a`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::Cache(CCharFormatArray *this, const struct CCharFormat *a2, __int16 *a3)
{
  int v3; // ebx
  _DWORD *LockTelemetry; // rax
  char v8; // r12
  __int64 v9; // r14
  __int16 i; // bx
  const void *v11; // rcx
  CFixArrayBase *v12; // rdi
  const void *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  RTL_SRWLOCK *Lock; // rax
  __int64 v19; // rax
  __int16 v20; // ax
  int v21; // r10d
  __int128 v22; // xmm1
  __int128 v23; // xmm2
  __int128 v24; // xmm3
  __int64 v25; // rdx
  int v26; // [rsp+78h] [rbp+10h] BYREF

  v3 = (int)CLockSharedData::LockOwner;
  v26 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v3 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v19 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v19 + 4);
  }
  v8 = *((_BYTE *)a2 + 6);
  v9 = v8 & 0xF;
  if ( v8 == *((_BYTE *)qword_1802DFB80 + 4 * v9)
    && (i = *((_WORD *)qword_1802DFB80 + 2 * v9 + 1) - 1, i >= 0)
    && i < *((_DWORD *)this + 5)
    && (*(int (__fastcall **)(CCharFormatArray *, _QWORD))(*(_QWORD *)this + 16LL))(this, (unsigned int)i) > 0
    && ((unsigned int)i >= *((_DWORD *)this + 5)
      ? (v11 = 0)
      : (v11 = (const void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (i / 16)) + *((_DWORD *)this + 7) * (i % 16))),
        !memcmp_0(v11, a2, 0x44u)) )
  {
    v12 = (CCharFormatArray *)((char *)this + 8);
LABEL_20:
    v14 = *((_DWORD *)v12 + 5) * ((i & 0xF) + 1);
    v15 = *(_QWORD *)(*(_QWORD *)v12 + 8 * ((unsigned __int64)(unsigned __int16)i >> 4));
    ++*(_DWORD *)(v14 + v15 - 4);
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 5) )
      {
        v12 = (CCharFormatArray *)((char *)this + 8);
        goto LABEL_27;
      }
      if ( (*(int (__fastcall **)(CCharFormatArray *, _QWORD))(*(_QWORD *)this + 16LL))(this, (unsigned int)i) > 0 )
      {
        v13 = (unsigned int)i >= *((_DWORD *)this + 5)
            ? 0LL
            : (const void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (i / 16)) + *((_DWORD *)this + 7) * (i % 16));
        if ( !memcmp_0(v13, a2, 0x44u) )
          break;
      }
    }
    v12 = (CCharFormatArray *)((char *)this + 8);
    *((_BYTE *)qword_1802DFB80 + 4 * v9) = v8;
    *((_WORD *)qword_1802DFB80 + 2 * v9 + 1) = i + 1;
    if ( i >= 0 )
      goto LABEL_20;
LABEL_27:
    v20 = CFixArrayBase::Add(v12);
    i = v20;
    if ( v20 < 0 )
    {
      v16 = -2147024882;
      goto LABEL_24;
    }
    v21 = *((_DWORD *)a2 + 16);
    v22 = *((_OWORD *)a2 + 1);
    v23 = *((_OWORD *)a2 + 2);
    v24 = *((_OWORD *)a2 + 3);
    if ( (unsigned int)v20 >= *((_DWORD *)v12 + 3) )
      v25 = 0;
    else
      v25 = *(_QWORD *)(*(_QWORD *)v12 + 8LL * (v20 / 16)) + *((_DWORD *)v12 + 5) * (v20 % 16);
    *(_OWORD *)v25 = *(_OWORD *)a2;
    *(_OWORD *)(v25 + 16) = v22;
    *(_OWORD *)(v25 + 32) = v23;
    *(_OWORD *)(v25 + 48) = v24;
    *(_DWORD *)(v25 + 64) = v21;
    *(_DWORD *)(*((_DWORD *)v12 + 5) * (v20 % 16 + 1) + *(_QWORD *)(*(_QWORD *)v12 + 8LL * (v20 / 16)) - 4LL) = 1;
  }
  if ( a3 )
    *a3 = i;
  v16 = 0;
LABEL_24:
  CWriteLock::~CWriteLock((CWriteLock *)&v26);
  return v16;
}

```

## disassembly

```asm
0x18002a570  push    rbx
0x18002a572  push    rbp
0x18002a573  push    rsi
0x18002a574  push    rdi
0x18002a575  push    r12
0x18002a577  push    r13
0x18002a579  push    r14
0x18002a57b  push    r15
0x18002a57d  sub     rsp, 28h
0x18002a581  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002a587  xor     r15d, r15d
0x18002a58a  mov     [rsp+68h+arg_8], r15d
0x18002a58f  mov     r13, r8
0x18002a592  mov     rbp, rdx
0x18002a595  mov     rdi, rcx
0x18002a598  test    ebx, ebx
0x18002a59a  jz      loc_18002A71A
0x18002a5a0  call    cs:__imp_GetCurrentThreadId
0x18002a5a6  cmp     ebx, eax
0x18002a5a8  jnz     loc_18002A71A
0x18002a5ae  xor     ecx, ecx
0x18002a5b0  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18002a5b5  lea     esi, [r15+1]
0x18002a5b9  add     [rax], esi
0x18002a5bb  movzx   r12d, byte ptr [rbp+6]
0x18002a5c0  lea     rax, qword_1802DFB80
0x18002a5c7  mov     r14d, r12d
0x18002a5ca  and     r14d, 0Fh
0x18002a5ce  cmp     r12b, [rax+r14*4]
0x18002a5d2  jnz     short loc_18002A647
0x18002a5d4  movzx   ebx, word ptr [rax+r14*4+2]
0x18002a5da  sub     bx, si
0x18002a5dd  js      short loc_18002A647
0x18002a5df  movsx   r15d, bx
0x18002a5e3  cmp     r15d, [rdi+14h]
0x18002a5e7  jge     short loc_18002A644
0x18002a5e9  mov     rax, [rdi]
0x18002a5ec  mov     edx, r15d
0x18002a5ef  mov     rcx, rdi
0x18002a5f2  mov     rax, [rax+10h]
0x18002a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5fb  test    eax, eax
0x18002a5fd  jle     short loc_18002A644
0x18002a5ff  cmp     r15d, [rdi+14h]
0x18002a603  jnb     loc_18002A7DB
0x18002a609  mov     eax, r15d
0x18002a60c  mov     ecx, 10h
0x18002a611  cdq
0x18002a612  idiv    ecx
0x18002a614  imul    edx, [rdi+1Ch]
0x18002a618  movsxd  r8, eax
0x18002a61b  mov     rax, [rdi+8]
0x18002a61f  movsxd  rcx, edx
0x18002a622  add     rcx, [rax+r8*8]; Buf1
0x18002a626  xor     r15d, r15d
0x18002a629  mov     r8d, 44h ; 'D'; Size
0x18002a62f  mov     rdx, rbp; Buf2
0x18002a632  call    memcmp_0
0x18002a637  test    eax, eax
0x18002a639  jnz     short loc_18002A647
0x18002a63b  add     rdi, 8
0x18002a63f  jmp     loc_18002A6D0
0x18002a644  xor     r15d, r15d
0x18002a647  mov     ebx, r15d
0x18002a64a  movsx   r15d, bx
0x18002a64e  cmp     r15d, [rdi+14h]
0x18002a652  jge     loc_18002A74A
0x18002a658  mov     rax, [rdi]
0x18002a65b  mov     edx, r15d
0x18002a65e  mov     rcx, rdi
0x18002a661  mov     rax, [rax+10h]
0x18002a665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a66a  test    eax, eax
0x18002a66c  jle     short loc_18002A6AA
0x18002a66e  cmp     r15d, [rdi+14h]
0x18002a672  jnb     loc_18002A7E6
0x18002a678  mov     eax, r15d
0x18002a67b  mov     ecx, 10h
0x18002a680  cdq
0x18002a681  idiv    ecx
0x18002a683  imul    edx, [rdi+1Ch]
0x18002a687  movsxd  rcx, edx
0x18002a68a  movsxd  rdx, eax
0x18002a68d  mov     rax, [rdi+8]
0x18002a691  add     rcx, [rax+rdx*8]; Buf1
0x18002a695  xor     r15d, r15d
0x18002a698  mov     r8d, 44h ; 'D'; Size
0x18002a69e  mov     rdx, rbp; Buf2
0x18002a6a1  call    memcmp_0
0x18002a6a6  test    eax, eax
0x18002a6a8  jz      short loc_18002A6AF
0x18002a6aa  add     bx, si
0x18002a6ad  jmp     short loc_18002A64A
0x18002a6af  lea     rcx, qword_1802DFB80
0x18002a6b6  add     rdi, 8
0x18002a6ba  mov     [rcx+r14*4], r12b
0x18002a6be  lea     eax, [rsi+rbx]
0x18002a6c1  mov     [rcx+r14*4+2], ax
0x18002a6c7  test    bx, bx
0x18002a6ca  js      loc_18002A751
0x18002a6d0  movzx   ecx, bx
0x18002a6d3  mov     eax, ecx
0x18002a6d5  shr     rcx, 4
0x18002a6d9  and     eax, 0Fh
0x18002a6dc  add     eax, esi
0x18002a6de  imul    eax, [rdi+14h]
0x18002a6e2  movsxd  rdx, eax
0x18002a6e5  mov     rax, [rdi]
0x18002a6e8  mov     rcx, [rax+rcx*8]
0x18002a6ec  add     [rdx+rcx-4], esi
0x18002a6f0  test    r13, r13
0x18002a6f3  jz      short loc_18002A6FA
0x18002a6f5  mov     [r13+0], bx
0x18002a6fa  mov     ebx, r15d
0x18002a6fd  lea     rcx, [rsp+68h+arg_8]; this
0x18002a702  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18002a707  mov     eax, ebx
0x18002a709  add     rsp, 28h
0x18002a70d  pop     r15
0x18002a70f  pop     r14
0x18002a711  pop     r13
0x18002a713  pop     r12
0x18002a715  pop     rdi
0x18002a716  pop     rsi
0x18002a717  pop     rbp
0x18002a718  pop     rbx
0x18002a719  retn
0x18002a71a  xor     ecx, ecx
0x18002a71c  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002a721  mov     rcx, rax; SRWLock
0x18002a724  call    cs:__imp_AcquireSRWLockExclusive
0x18002a72a  call    cs:__imp_GetCurrentThreadId
0x18002a730  xor     ecx, ecx
0x18002a732  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002a738  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18002a73d  mov     esi, 1
0x18002a742  add     [rax+4], esi
0x18002a745  jmp     loc_18002A5BB
0x18002a74a  add     rdi, 8
0x18002a74e  xor     r15d, r15d
0x18002a751  mov     rcx, rdi; this
0x18002a754  call    ?Add@CFixArrayBase@@QEAAFXZ; CFixArrayBase::Add(void)
0x18002a759  movsx   ebx, ax
0x18002a75c  test    bx, bx
0x18002a75f  jns     short loc_18002A768
0x18002a761  mov     ebx, 8007000Eh
0x18002a766  jmp     short loc_18002A6FD
0x18002a768  movups  xmm0, xmmword ptr [rbp+0]
0x18002a76c  mov     r10d, [rbp+40h]
0x18002a770  movups  xmm1, xmmword ptr [rbp+10h]
0x18002a774  movups  xmm2, xmmword ptr [rbp+20h]
0x18002a778  movups  xmm3, xmmword ptr [rbp+30h]
0x18002a77c  cmp     ebx, [rdi+0Ch]
0x18002a77f  jnb     short loc_18002A7F1
0x18002a781  mov     eax, ebx
0x18002a783  mov     ecx, 10h
0x18002a788  cdq
0x18002a789  idiv    ecx
0x18002a78b  imul    edx, [rdi+14h]
0x18002a78f  movsxd  rcx, eax
0x18002a792  mov     rax, [rdi]
0x18002a795  movsxd  rdx, edx
0x18002a798  add     rdx, [rax+rcx*8]
0x18002a79c  movups  xmmword ptr [rdx], xmm0
0x18002a79f  mov     ecx, 10h
0x18002a7a4  mov     eax, ebx
0x18002a7a6  movups  xmmword ptr [rdx+10h], xmm1
0x18002a7aa  movups  xmmword ptr [rdx+20h], xmm2
0x18002a7ae  movups  xmmword ptr [rdx+30h], xmm3
0x18002a7b2  mov     [rdx+40h], r10d
0x18002a7b6  cdq
0x18002a7b7  idiv    ecx
0x18002a7b9  mov     eax, ebx
0x18002a7bb  add     edx, esi
0x18002a7bd  imul    edx, [rdi+14h]
0x18002a7c1  movsxd  r8, edx
0x18002a7c4  cdq
0x18002a7c5  idiv    ecx
0x18002a7c7  movsxd  rcx, eax
0x18002a7ca  mov     rax, [rdi]
0x18002a7cd  mov     rcx, [rax+rcx*8]
0x18002a7d1  mov     [r8+rcx-4], esi
0x18002a7d6  jmp     loc_18002A6F0
0x18002a7db  xor     r15d, r15d
0x18002a7de  mov     ecx, r15d
0x18002a7e1  jmp     loc_18002A629
0x18002a7e6  xor     r15d, r15d
0x18002a7e9  mov     ecx, r15d
0x18002a7ec  jmp     loc_18002A698
0x18002a7f1  mov     rdx, r15
0x18002a7f4  jmp     short loc_18002A79C
```
