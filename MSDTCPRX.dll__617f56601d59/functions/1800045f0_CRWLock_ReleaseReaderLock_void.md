# CRWLock::ReleaseReaderLock(void)

- ea: `0x1800045f0`
- end: `0x1800048bd`
- name: `?ReleaseReaderLock@CRWLock@@QEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `18`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003090`
- `0x1800039a0`
- `0x180003d60`
- `0x180004dc0`
- `0x180004fe4`
- `0x1800055a0`
- `0x18000f270`
- `0x18000fa88`
- `0x1800581d4`
- `0x18006540c`
- `0x180065b30`
- `0x1800676b8`
- `0x180067e20`
- `0x180068130`
- `0x180068950`
- `0x18006c490`
- `0x18006c550`
- `0x18006c994`

## callees

- `0x1800045f0`
- `0x18000cd08`
- `0x18000d5f4`
- `0x180012b28`
- `0x18001d178`
- `0x18007cb3c`
- `0x18007cb88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000460c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000461a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000460c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000461a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004816`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004816`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRWLock::ReleaseReaderLock(CRWLock *this)
{
  int v2; // ebx
  DWORD CurrentThreadId; // ebp
  void **v4; // rdx
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  unsigned int v7; // esi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *ReaderEvent; // r14
  void *WriterEvent; // r15
  signed __int32 v15; // ebx
  int v16; // ecx
  int v17; // ebp
  signed __int32 v18; // edx
  void **v20; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+28h] [rbp-40h]
  __int64 v22; // [rsp+30h] [rbp-38h]
  char *v23; // [rsp+38h] [rbp-30h]

  v2 = *((_DWORD *)this + 21);
  if ( v2 == GetCurrentThreadId() )
    return (unsigned int)CRWLock::ReleaseWriterLock(this);
  CurrentThreadId = GetCurrentThreadId();
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v4 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  v20 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  v23 = (char *)this + 96;
  v22 = 0;
  v21 = *((_QWORD *)this + 14);
  v5 = 0;
  v21 = *((_QWORD *)this + 14);
  while ( ((unsigned int (__fastcall *)(void ***))v4[2])(&v20) )
  {
    v6 = ((__int64 (__fastcall *)(void ***))v20[1])(&v20);
    ((void (__fastcall *)(void ***, _QWORD))v20[3])(&v20, 0);
    if ( CurrentThreadId == *(_DWORD *)(v6 + 48) )
    {
      v5 = (_DWORD *)v6;
      break;
    }
    v4 = v20;
  }
  v20 = &UTStaticList2Iterator<CTimeoutTableRow *>::`vftable';
  if ( !v5 )
    DtcInternalErrorW(L"LockEntry not found");
  v7 = 0;
  if ( v5[14]-- != 1 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    return v7;
  }
  v9 = *((_QWORD *)v5 + 2);
  if ( *(_DWORD **)(v9 + 16) == v5 )
    *(_QWORD *)(v9 + 16) = *((_QWORD *)v5 + 3);
  v10 = *((_QWORD *)v5 + 2);
  if ( *(_DWORD **)(v10 + 24) == v5 )
    *(_QWORD *)(v10 + 24) = *((_QWORD *)v5 + 4);
  v11 = *((_QWORD *)v5 + 4);
  if ( v11 )
    *(_QWORD *)(v11 + 24) = *((_QWORD *)v5 + 3);
  v12 = *((_QWORD *)v5 + 3);
  if ( v12 )
    *(_QWORD *)(v12 + 32) = *((_QWORD *)v5 + 4);
  --*(_DWORD *)(*((_QWORD *)v5 + 2) + 8LL);
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v5[10] = 0;
  if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 16) + 80LL))((char *)this + 128) >= 0x64 )
  {
    *(_QWORD *)v5 = &UTStaticLink2<CLockEntry *>::`vftable';
    operator delete(v5);
  }
  else
  {
    (*(void (__fastcall **)(char *, _DWORD *))(*((_QWORD *)this + 16) + 8LL))((char *)this + 128, v5);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  ReaderEvent = 0;
  WriterEvent = 0;
  v15 = *((_DWORD *)this + 20);
  do
  {
    v16 = -1;
    if ( (v15 & 0x7FF) != 1 )
    {
      v17 = 0;
LABEL_22:
      v18 = v15;
      v15 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v15 + v16, v15);
      continue;
    }
    v17 = 1;
    if ( (v15 & 0xFF800000) != 0 )
    {
      WriterEvent = CRWLock::GetWriterEvent(this);
      if ( WriterEvent )
      {
        v16 = 2047;
        goto LABEL_22;
      }
    }
    else
    {
      if ( (v15 & 0x7FE000) == 0 )
        goto LABEL_22;
      ReaderEvent = CRWLock::GetReaderEvent(this);
      if ( ReaderEvent )
      {
        v16 = 1023;
        goto LABEL_22;
      }
    }
    Sleep(0x64u);
    v15 = *((_DWORD *)this + 20);
    v18 = 0;
  }
  while ( v15 != v18 );
  if ( v17 )
  {
    if ( (v18 & 0xFF800000) != 0 )
    {
      CRWLock::RWSetEvent(WriterEvent);
    }
    else if ( (v18 & 0x7FE000) != 0 )
    {
      CRWLock::RWSetEvent(ReaderEvent);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800045f0  mov     [rsp+arg_8], rbx
0x1800045f5  mov     [rsp+arg_10], rbp
0x1800045fa  push    rsi
0x1800045fb  push    rdi
0x1800045fc  push    r12
0x1800045fe  push    r14
0x180004600  push    r15
0x180004602  sub     rsp, 40h
0x180004606  mov     rdi, rcx
0x180004609  mov     ebx, [rcx+54h]
0x18000460c  call    cs:__imp_GetCurrentThreadId
0x180004612  cmp     ebx, eax
0x180004614  jz      loc_18000484F
0x18000461a  call    cs:__imp_GetCurrentThreadId
0x180004620  mov     ebp, eax
0x180004622  mov     rcx, [rdi+8]
0x180004626  mov     rax, [rcx]
0x180004629  lea     rcx, [rdi+8]
0x18000462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004632  lea     r15, ??_7?$UTStaticList2Iterator@PEAVCTimeoutTableRow@@@@6B@; const UTStaticList2Iterator<CTimeoutTableRow *>::`vftable'
0x180004639  mov     rdx, r15
0x18000463c  mov     [rsp+68h+var_48], rdx
0x180004641  lea     rcx, [rdi+60h]
0x180004645  mov     [rsp+68h+var_30], rcx
0x18000464a  xor     r12d, r12d
0x18000464d  mov     [rsp+68h+var_38], r12
0x180004652  mov     rax, [rcx+10h]
0x180004656  mov     [rsp+68h+var_40], rax
0x18000465b  mov     ebx, r12d
0x18000465e  mov     [rsp+68h+var_38], r12
0x180004663  mov     rax, [rcx+10h]
0x180004667  mov     [rsp+68h+var_40], rax
0x18000466c  lea     rcx, [rsp+68h+var_48]
0x180004671  mov     rax, [rdx+10h]
0x180004675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467a  test    eax, eax
0x18000467c  jz      short loc_1800046B5
0x18000467e  mov     rax, [rsp+68h+var_48]
0x180004683  lea     rcx, [rsp+68h+var_48]
0x180004688  mov     rax, [rax+8]
0x18000468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004691  mov     rsi, rax
0x180004694  mov     rcx, [rsp+68h+var_48]
0x180004699  mov     rax, [rcx+18h]
0x18000469d  xor     edx, edx
0x18000469f  lea     rcx, [rsp+68h+var_48]
0x1800046a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a9  cmp     ebp, [rsi+30h]
0x1800046ac  jnz     loc_18000483B
0x1800046b2  mov     rbx, rsi
0x1800046b5  mov     [rsp+68h+var_48], r15
0x1800046ba  test    rbx, rbx
0x1800046bd  jz      loc_18000485E
0x1800046c3  mov     esi, r12d
0x1800046c6  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x1800046ca  jnz     loc_1800047E9
0x1800046d0  mov     rcx, [rbx+10h]
0x1800046d4  cmp     [rcx+10h], rbx
0x1800046d8  jnz     short loc_1800046E2
0x1800046da  mov     rax, [rbx+18h]
0x1800046de  mov     [rcx+10h], rax
0x1800046e2  mov     rcx, [rbx+10h]
0x1800046e6  cmp     [rcx+18h], rbx
0x1800046ea  jnz     short loc_1800046F4
0x1800046ec  mov     rax, [rbx+20h]
0x1800046f0  mov     [rcx+18h], rax
0x1800046f4  mov     rcx, [rbx+20h]
0x1800046f8  test    rcx, rcx
0x1800046fb  jnz     loc_18000486B
0x180004701  mov     rcx, [rbx+18h]
0x180004705  test    rcx, rcx
0x180004708  jnz     loc_180004878
0x18000470e  mov     rax, [rbx+10h]
0x180004712  dec     dword ptr [rax+8]
0x180004715  mov     [rbx+10h], r12
0x180004719  mov     [rbx+18h], r12
0x18000471d  mov     [rbx+20h], r12
0x180004721  mov     [rbx+28h], r12d
0x180004725  mov     rax, [rdi+80h]
0x18000472c  lea     rcx, [rdi+80h]
0x180004733  mov     rax, [rax+50h]
0x180004737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473c  cmp     eax, 64h ; 'd'
0x18000473f  jnb     loc_180004824
0x180004745  mov     rax, [rdi+80h]
0x18000474c  mov     rdx, rbx
0x18000474f  lea     rcx, [rdi+80h]
0x180004756  mov     rax, [rax+8]
0x18000475a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475f  mov     rax, [rdi+8]
0x180004763  lea     rcx, [rdi+8]
0x180004767  mov     rax, [rax+8]
0x18000476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004770  mov     r14, r12
0x180004773  mov     r15, r12
0x180004776  mov     ebx, [rdi+50h]
0x180004779  mov     ecx, 0FFFFFFFFh
0x18000477e  mov     eax, ebx
0x180004780  and     eax, 7FFh
0x180004785  cmp     eax, 1
0x180004788  jnz     short loc_1800047FC
0x18000478a  mov     ebp, eax
0x18000478c  test    ebx, 0FF800000h
0x180004792  jnz     loc_180004885
0x180004798  test    ebx, 7FE000h
0x18000479e  jnz     short loc_180004801
0x1800047a0  mov     edx, ebx
0x1800047a2  add     ecx, ebx
0x1800047a4  mov     eax, ebx
0x1800047a6  lock cmpxchg [rdi+50h], ecx
0x1800047ab  mov     ebx, eax
0x1800047ad  cmp     ebx, edx
0x1800047af  jnz     short loc_180004779
0x1800047b1  test    ebp, ebp
0x1800047b3  jz      short loc_1800047CD
0x1800047b5  test    edx, 0FF800000h
0x1800047bb  jnz     loc_1800048A3
0x1800047c1  test    edx, 7FE000h
0x1800047c7  jnz     loc_1800048B0
0x1800047cd  mov     eax, esi
0x1800047cf  mov     rbx, [rsp+68h+arg_8]
0x1800047d4  mov     rbp, [rsp+68h+arg_10]
0x1800047dc  add     rsp, 40h
0x1800047e0  pop     r15
0x1800047e2  pop     r14
0x1800047e4  pop     r12
0x1800047e6  pop     rdi
0x1800047e7  pop     rsi
0x1800047e8  retn
0x1800047e9  mov     rax, [rdi+8]
0x1800047ed  lea     rcx, [rdi+8]
0x1800047f1  mov     rax, [rax+8]
0x1800047f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047fa  jmp     short loc_1800047CD
0x1800047fc  mov     ebp, r12d
0x1800047ff  jmp     short loc_1800047A0
0x180004801  mov     rcx, rdi; this
0x180004804  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x180004809  mov     r14, rax
0x18000480c  test    rax, rax
0x18000480f  jnz     short loc_180004845
0x180004811  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180004816  call    cs:__imp_Sleep
0x18000481c  mov     ebx, [rdi+50h]
0x18000481f  mov     edx, r12d
0x180004822  jmp     short loc_1800047AD
0x180004824  lea     rax, ??_7?$UTStaticLink2@PEAVCLockEntry@@@@6B@; const UTStaticLink2<CLockEntry *>::`vftable'
0x18000482b  mov     [rbx], rax
0x18000482e  mov     rcx, rbx; Block
0x180004831  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004836  jmp     loc_18000475F
0x18000483b  mov     rdx, [rsp+68h+var_48]
0x180004840  jmp     loc_18000466C
0x180004845  mov     ecx, 3FFh
0x18000484a  jmp     loc_1800047A0
0x18000484f  mov     rcx, rdi; this
0x180004852  call    ?ReleaseWriterLock@CRWLock@@QEAAJXZ; CRWLock::ReleaseWriterLock(void)
0x180004857  mov     esi, eax
0x180004859  jmp     loc_1800047CD
0x18000485e  lea     rcx, aLockentryNotFo; "LockEntry not found"
0x180004865  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000486b  mov     rax, [rbx+18h]
0x18000486f  mov     [rcx+18h], rax
0x180004873  jmp     loc_180004701
0x180004878  mov     rax, [rbx+20h]
0x18000487c  mov     [rcx+20h], rax
0x180004880  jmp     loc_18000470E
0x180004885  mov     rcx, rdi; this
0x180004888  call    ?GetWriterEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetWriterEvent(void)
0x18000488d  mov     r15, rax
0x180004890  test    rax, rax
0x180004893  jz      loc_180004811
0x180004899  mov     ecx, 7FFh
0x18000489e  jmp     loc_1800047A0
0x1800048a3  mov     rcx, r15; void *
0x1800048a6  call    ?RWSetEvent@CRWLock@@CAXPEAX@Z; CRWLock::RWSetEvent(void *)
0x1800048ab  jmp     loc_1800047CD
0x1800048b0  mov     rcx, r14; void *
0x1800048b3  call    ?RWSetEvent@CRWLock@@CAXPEAX@Z; CRWLock::RWSetEvent(void *)
0x1800048b8  jmp     loc_1800047CD
```
