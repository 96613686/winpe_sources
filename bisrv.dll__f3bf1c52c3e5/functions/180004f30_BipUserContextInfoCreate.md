# BipUserContextInfoCreate

- ea: `0x180004f30`
- end: `0x180005180`
- name: `BipUserContextInfoCreate`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044908`

## callees

- `0x180004e10`
- `0x180004e78`
- `0x180004f30`
- `0x180005280`
- `0x180006300`
- `0x180006dc0`
- `0x18000a9f0`
- `0x1800121b0`
- `0x18006a760`
- `0x18007b73c`
- `0x18009467a`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180005081`
- `ntdll!TpAllocTimer` at `0x180005081`
- `ntdll!RtlFreeHeap` at `0x180005150`
- `ntdll!RtlFreeHeap` at `0x180005167`
- `ntdll!RtlFreeHeap` at `0x180005150`
- `ntdll!RtlFreeHeap` at `0x180005167`
- `ntdll!RtlAllocateHeap` at `0x180004fa7`
- `ntdll!RtlAllocateHeap` at `0x180004fec`
- `ntdll!RtlAllocateHeap` at `0x180004fa7`
- `ntdll!RtlAllocateHeap` at `0x180004fec`
- `ntdll!RtlCopySid` at `0x18000502e`
- `ntdll!RtlCopySid` at `0x18000502e`

## pseudocode

```c
__int64 __fastcall BipUserContextInfoCreate(unsigned int a1, __int64 a2, void *a3, unsigned __int8 a4, _DWORD *a5)
{
  _QWORD *v7; // rbp
  __int64 v10; // rdx
  __int64 i; // rbx
  struct _BI_USERCONTEXT_INFORMATION *Heap; // rdi
  int v13; // ebx
  struct _BI_USER_INFORMATION *v14; // rsi
  _QWORD *v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx

  v7 = 0;
  BipSyncAcquireLock((struct _BI_LOCK *)BipSessionLock);
  for ( i = qword_1800C4400; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_1800C4400 )
    {
      Heap = 0;
      v13 = -1073741275;
      *a5 = 256;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(i + 56) == a1 )
      break;
  }
  if ( BipUserContextInfoFind(a1, a3) )
  {
    Heap = 0;
    v13 = 0;
LABEL_26:
    LOBYTE(v10) = 1;
    BipSyncReleaseLock(BipSessionLock, v10);
    if ( Heap )
    {
      BipUserContextInfoCleanup(Heap);
      RtlFreeHeap(BipHeap, 0, Heap);
    }
    if ( v7 )
      RtlFreeHeap(BipHeap, 0, v7);
    return (unsigned int)v13;
  }
  Heap = (struct _BI_USERCONTEXT_INFORMATION *)RtlAllocateHeap(BipHeap, 0, 0x88u);
  if ( !Heap )
  {
    *a5 = 768;
LABEL_9:
    v13 = -1073741801;
    goto LABEL_26;
  }
  v14 = BipLookupUserBySid(a3);
  if ( !v14 )
  {
    v15 = RtlAllocateHeap(BipHeap, 0, 0x68u);
    v7 = v15;
    if ( !v15 )
    {
      *a5 = 512;
      goto LABEL_9;
    }
    memset_0(v15, 0, 0x68u);
    v7[3] = v7 + 2;
    v7[2] = v7 + 2;
    RtlCopySid(0x44u, (char *)v7 + 36, a3);
    v14 = (struct _BI_USER_INFORMATION *)v7;
  }
  memset_0(Heap, 0, 0x88u);
  *((_QWORD *)Heap + 6) = i;
  *((_QWORD *)Heap + 9) = v14;
  *((_QWORD *)Heap + 16) = a2;
  *((_QWORD *)Heap + 14) = *(_QWORD *)(i + 48);
  *((_DWORD *)Heap + 22) = 11;
  *((_QWORD *)Heap + 8) = (char *)Heap + 56;
  *((_QWORD *)Heap + 7) = (char *)Heap + 56;
  v16 = TpAllocTimer((char *)Heap + 80, BipChangeUserStateTimerCallback, Heap, 0);
  v13 = 0;
  if ( v16 < 0 )
    v13 = v16;
  if ( v13 < 0 )
    goto LABEL_26;
  if ( (unsigned int)CempListEntryIsNull(v14) )
  {
    v17 = qword_1800C43D8;
    if ( *(__int64 **)(qword_1800C43D8 + 8) != &qword_1800C43D8 )
      __fastfail(3u);
    *(_QWORD *)v14 = qword_1800C43D8;
    *((_QWORD *)v14 + 1) = &qword_1800C43D8;
    *(_QWORD *)(v17 + 8) = v14;
    qword_1800C43D8 = (__int64)v14;
  }
  if ( !a4 || v7 )
    *((_DWORD *)v14 + 8) = a1;
  BipUserContextInsertIntoGlobals(a4, Heap);
  BipEnergyBudgetNotifySessionUserChanged(qword_1800C45C0, a1, a3);
  LOBYTE(v18) = 1;
  BipSyncReleaseLock(BipSessionLock, v18);
  BipPackageResetAndQueryAccessStateForUserSidAsync(a3);
  return 0;
}

```

## disassembly

```asm
0x180004f30  push    rbx
0x180004f32  push    rbp
0x180004f33  push    rsi
0x180004f34  push    rdi
0x180004f35  push    r12
0x180004f37  push    r13
0x180004f39  push    r14
0x180004f3b  push    r15
0x180004f3d  sub     rsp, 28h
0x180004f41  mov     r13, rdx
0x180004f44  mov     r14d, ecx
0x180004f47  mov     dl, 1
0x180004f49  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180004f50  xor     ebp, ebp
0x180004f52  mov     r12b, r9b
0x180004f55  mov     r15, r8
0x180004f58  call    BipSyncAcquireLock
0x180004f5d  mov     rbx, cs:qword_1800C4400
0x180004f64  lea     rax, qword_1800C4400
0x180004f6b  cmp     rbx, rax
0x180004f6e  jz      loc_180005114
0x180004f74  cmp     [rbx+38h], r14d
0x180004f78  jz      short loc_180004F7F
0x180004f7a  mov     rbx, [rbx]
0x180004f7d  jmp     short loc_180004F64
0x180004f7f  mov     rdx, r15
0x180004f82  mov     ecx, r14d
0x180004f85  call    BipUserContextInfoFind
0x180004f8a  test    rax, rax
0x180004f8d  jz      short loc_180004F98
0x180004f8f  xor     edi, edi
0x180004f91  xor     ebx, ebx
0x180004f93  jmp     loc_180005129
0x180004f98  mov     rcx, cs:BipHeap; HeapHandle
0x180004f9f  xor     edx, edx; Flags
0x180004fa1  mov     r8d, 88h; Size
0x180004fa7  call    cs:__imp_RtlAllocateHeap
0x180004fad  mov     rdi, rax
0x180004fb0  test    rax, rax
0x180004fb3  jnz     short loc_180004FCD
0x180004fb5  mov     rcx, [rsp+68h+arg_20]
0x180004fbd  mov     dword ptr [rcx], 300h
0x180004fc3  mov     ebx, 0C0000017h
0x180004fc8  jmp     loc_180005129
0x180004fcd  mov     rcx, r15; Sid2
0x180004fd0  call    ?BipLookupUserBySid@@YAPEAU_BI_USER_INFORMATION@@PEAX@Z; BipLookupUserBySid(void *)
0x180004fd5  mov     rsi, rax
0x180004fd8  test    rax, rax
0x180004fdb  jnz     short loc_180005037
0x180004fdd  mov     rcx, cs:BipHeap; HeapHandle
0x180004fe4  lea     esi, [rax+68h]
0x180004fe7  mov     r8d, esi; Size
0x180004fea  xor     edx, edx; Flags
0x180004fec  call    cs:__imp_RtlAllocateHeap
0x180004ff2  mov     rbp, rax
0x180004ff5  test    rax, rax
0x180004ff8  jnz     short loc_18000500A
0x180004ffa  mov     rcx, [rsp+68h+arg_20]
0x180005002  mov     dword ptr [rcx], 200h
0x180005008  jmp     short loc_180004FC3
0x18000500a  mov     r8, rsi; Size
0x18000500d  xor     edx, edx; Val
0x18000500f  mov     rcx, rbp; void *
0x180005012  call    memset_0
0x180005017  lea     rax, [rbp+10h]
0x18000501b  mov     r8, r15; SourceSid
0x18000501e  lea     rdx, [rbp+24h]; DestinationSid
0x180005022  mov     [rax+8], rax
0x180005026  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000502b  mov     [rax], rax
0x18000502e  call    cs:__imp_RtlCopySid
0x180005034  mov     rsi, rbp
0x180005037  xor     edx, edx; Val
0x180005039  mov     r8d, 88h; Size
0x18000503f  mov     rcx, rdi; void *
0x180005042  call    memset_0
0x180005047  mov     [rdi+30h], rbx
0x18000504b  lea     rcx, [rdi+50h]
0x18000504f  mov     [rdi+48h], rsi
0x180005053  lea     rdx, ?BipChangeUserStateTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; BipChangeUserStateTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x18000505a  mov     [rdi+80h], r13
0x180005061  xor     r9d, r9d
0x180005064  mov     rax, [rbx+30h]
0x180005068  mov     r8, rdi
0x18000506b  mov     [rdi+70h], rax
0x18000506f  lea     rax, [rdi+38h]
0x180005073  mov     dword ptr [rdi+58h], 0Bh
0x18000507a  mov     [rax+8], rax
0x18000507e  mov     [rax], rax
0x180005081  call    cs:__imp_TpAllocTimer
0x180005087  xor     ebx, ebx
0x180005089  test    eax, eax
0x18000508b  cmovs   ebx, eax
0x18000508e  test    ebx, ebx
0x180005090  js      loc_180005129
0x180005096  mov     rcx, rsi
0x180005099  call    CempListEntryIsNull
0x18000509e  test    eax, eax
0x1800050a0  jz      short loc_1800050CF
0x1800050a2  mov     rax, cs:qword_1800C43D8
0x1800050a9  lea     rcx, qword_1800C43D8
0x1800050b0  cmp     [rax+8], rcx
0x1800050b4  jz      short loc_1800050BD
0x1800050b6  mov     ecx, 3
0x1800050bb  int     29h; Win8: RtlFailFast(ecx)
0x1800050bd  mov     [rsi], rax
0x1800050c0  mov     [rsi+8], rcx
0x1800050c4  mov     [rax+8], rsi
0x1800050c8  mov     cs:qword_1800C43D8, rsi
0x1800050cf  test    r12b, r12b
0x1800050d2  jz      short loc_1800050D9
0x1800050d4  test    rbp, rbp
0x1800050d7  jz      short loc_1800050DD
0x1800050d9  mov     [rsi+20h], r14d
0x1800050dd  mov     rdx, rdi; struct _BI_USERCONTEXT_INFORMATION *
0x1800050e0  mov     cl, r12b; unsigned __int8
0x1800050e3  call    ?BipUserContextInsertIntoGlobals@@YAXEPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipUserContextInsertIntoGlobals(uchar,_BI_USERCONTEXT_INFORMATION *)
0x1800050e8  mov     rcx, cs:qword_1800C45C0
0x1800050ef  mov     r8, r15
0x1800050f2  mov     edx, r14d
0x1800050f5  call    BipEnergyBudgetNotifySessionUserChanged
0x1800050fa  mov     dl, 1
0x1800050fc  lea     rcx, BipSessionLock
0x180005103  call    BipSyncReleaseLock
0x180005108  mov     rcx, r15; Sid1
0x18000510b  call    BipPackageResetAndQueryAccessStateForUserSidAsync
0x180005110  xor     ebx, ebx
0x180005112  jmp     short loc_18000516D
0x180005114  mov     rax, [rsp+68h+arg_20]
0x18000511c  xor     edi, edi
0x18000511e  mov     ebx, 0C0000225h
0x180005123  mov     dword ptr [rax], 100h
0x180005129  mov     dl, 1
0x18000512b  lea     rcx, BipSessionLock
0x180005132  call    BipSyncReleaseLock
0x180005137  test    rdi, rdi
0x18000513a  jz      short loc_180005156
0x18000513c  mov     rcx, rdi; struct _BI_USERCONTEXT_INFORMATION *
0x18000513f  call    ?BipUserContextInfoCleanup@@YAXPEAU_BI_USERCONTEXT_INFORMATION@@@Z; BipUserContextInfoCleanup(_BI_USERCONTEXT_INFORMATION *)
0x180005144  mov     rcx, cs:BipHeap; HeapHandle
0x18000514b  mov     r8, rdi; P
0x18000514e  xor     edx, edx; Flags
0x180005150  call    cs:__imp_RtlFreeHeap
0x180005156  test    rbp, rbp
0x180005159  jz      short loc_18000516D
0x18000515b  mov     rcx, cs:BipHeap; HeapHandle
0x180005162  mov     r8, rbp; P
0x180005165  xor     edx, edx; Flags
0x180005167  call    cs:__imp_RtlFreeHeap
0x18000516d  mov     eax, ebx
0x18000516f  add     rsp, 28h
0x180005173  pop     r15
0x180005175  pop     r14
0x180005177  pop     r13
0x180005179  pop     r12
0x18000517b  pop     rdi
0x18000517c  pop     rsi
0x18000517d  pop     rbp
0x18000517e  pop     rbx
0x18000517f  retn
```
