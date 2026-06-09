# `CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (*&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::operator()(void *)

- ea: `0x140047864`
- end: `0x140047b25`
- name: `??R_lambda_1_@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV5@AEAPEAU6@@Z@@CmsHashTable@@QEAAJK$$QEAV0?1???$ParallelTuPageTableWork@AEAP6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV3@AEAPEAU4@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV1@AEAP6AX01KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@ZAEAPEAV4@AEAPEAU5@@Z@@Z@QEBA@PEAX@Z`
- size: `705`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140047be0`
- `0x140144740`

## callees

- `0x140014750`
- `0x140047288`
- `0x140047300`
- `0x140047730`
- `0x140047864`
- `0x140047b2c`
- `0x140049050`
- `0x140088930`
- `0x1400ceda0`
- `0x1401f40a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140047a56`
- `ntoskrnl!KeSetEvent` at `0x140047a56`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a30`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047aa1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047aa1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400478c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400478c3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fcef4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fcef4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140047a74`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140047a74`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcf31`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcf31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140047abf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140047abf`

## string_xrefs

- `0x140047aef`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
LONG __fastcall __R_lambda_1___1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_AEAP6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable__AEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV5_AEAPEAU6__Z__CmsHashTable__QEAAJK__QEAV0_1____ParallelTuPageTableWork_AEAP6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV3_AEAPEAU4__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV1_AEAP6AX01KKPEAVCmsAllocator__PEAUSmsWritePlan___ZAEAPEAV4_AEAPEAU5__Z__Z_QEBA_PEAX_Z(
        __int64 a1,
        volatile signed __int32 **a2)
{
  unsigned int v3; // r12d
  unsigned int v4; // r13d
  __int64 *v5; // rax
  __int64 v6; // r15
  __int64 v7; // rsi
  const struct std::nothrow_t *v8; // rdx
  __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  int v11; // ecx
  PSLIST_ENTRY v12; // rdi
  _QWORD *p_Next; // rdi
  __int64 v14; // rsi
  char v15; // bl
  __int64 v16; // rbx
  struct _SLIST_ENTRY *v17; // rdi
  struct _SLIST_ENTRY *Next; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  signed __int32 v20; // ebp
  LONG result; // eax
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  struct _SLIST_ENTRY *v23; // rax
  struct _SLIST_ENTRY *v24; // rax
  __int64 v25; // rcx
  void (__fastcall **v26)(_QWORD *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp+8h]
  _QWORD *v27; // [rsp+98h] [rbp+10h]
  _QWORD *v28; // [rsp+A0h] [rbp+18h]
  _QWORD *v29; // [rsp+A8h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 7);
  v4 = *((_DWORD *)a2 + 6);
  v27 = (_QWORD *)*((_QWORD *)*a2 + 4);
  v28 = (_QWORD *)*((_QWORD *)*a2 + 3);
  v29 = (_QWORD *)*((_QWORD *)*a2 + 2);
  v5 = *(__int64 **)*a2;
  v26 = (void (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)*a2 + 1);
  v6 = *v5;
  v7 = *(_QWORD *)(*v5 + 8);
  v8 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v9 = qword_140269408 + 192LL * (_QWORD)v8;
  if ( *(_DWORD *)v9 < 0xDD0u )
  {
    v9 = 0;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v9 + 8) )
  {
    v22 = (struct _NPAGED_LOOKASIDE_LIST *)(v9 + 64);
    if ( *(_BYTE *)(v9 + 9) )
      v23 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v22);
    else
      v23 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v22);
    v12 = v23;
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v23->Next + 1);
  }
  else
  {
    if ( (int)*(_QWORD *)(v9 + 88) <= (int)HIDWORD(*(_QWORD *)(v9 + 88)) )
      goto LABEL_26;
    v11 = _InterlockedDecrement((volatile signed __int32 *)(v9 + 88));
    if ( v11 < *(_DWORD *)(v9 + 92) || v11 < 0 )
    {
      v12 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 88));
    }
    else
    {
      v12 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v9 + 64));
    }
  }
  if ( v12 )
    goto LABEL_9;
LABEL_26:
  if ( v9 )
  {
    v10 = *(unsigned int *)(v9 + 4);
    goto LABEL_28;
  }
LABEL_3:
  v10 = 3552;
LABEL_28:
  v24 = (struct _SLIST_ENTRY *)operator new(v10, v8);
  v12 = v24;
  if ( ((unsigned __int8)v24 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !v24 )
    goto LABEL_11;
  CmsTransactionContext::InitializeTransactionMemoryBuffer(&v24[1]);
LABEL_9:
  v12->Next = (struct _SLIST_ENTRY *)v9;
  p_Next = &v12[1].Next;
  if ( p_Next )
  {
    p_Next[1] = v7;
    v14 = 0x8000;
    goto LABEL_12;
  }
LABEL_11:
  p_Next = CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v7 + 160));
  CmsTransactionContext::InitializeTransactionMemoryBuffer(p_Next);
  p_Next[1] = v7;
  v14 = 268468224;
LABEL_12:
  *p_Next = v14;
  v15 = *((_BYTE *)p_Next + 220);
  *p_Next = *(_QWORD *)v6 | v14;
  *((_BYTE *)p_Next + 220) = *(_BYTE *)(v6 + 220);
  (*v26)(p_Next, *v29, v4, v3, *v28, *v27);
  CmsTransactionContext::Commit((CmsTransactionContext *)p_Next, 0, 0, 0);
  *((_BYTE *)p_Next + 220) = v15;
  v16 = p_Next[1];
  *p_Next = v14;
  CmsTransactionContext::~CmsTransactionContext((CmsTransactionContext *)p_Next);
  if ( (v14 & 0x10000000) != 0 )
  {
    CmsReservedPool::FreeToPool((CmsReservedPool *)(v16 + 160), p_Next);
  }
  else
  {
    v17 = (struct _SLIST_ENTRY *)(p_Next - 2);
    Next = v17->Next;
    if ( !v17->Next )
      goto LABEL_32;
    if ( *((_BYTE *)&Next->Next + 8) )
    {
      v19 = (struct _NPAGED_LOOKASIDE_LIST *)&Next[4];
      if ( *((_BYTE *)&Next->Next + 9) )
        ExFreeToNPagedLookasideList(v19, v17);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v19, v17);
      goto LABEL_17;
    }
    v25 = *((_QWORD *)&Next[5].Next + 1);
    if ( (int)v25 < SLODWORD(Next[5].Next) || SHIDWORD(v25) >= (int)v25 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)&Next[4], v17);
      _InterlockedIncrement((volatile signed __int32 *)&Next[5].Next + 2);
    }
    else
    {
LABEL_32:
      operator delete(v17);
    }
  }
LABEL_17:
  v20 = _InterlockedExchangeAdd(a2[2], 0xFFFFFFFF);
  result = v20 - 1;
  if ( v20 == 1 )
    return KeSetEvent((PRKEVENT)a2[4], 0, 0);
  return result;
}

```

## disassembly

```asm
0x140047864  mov     [rsp+arg_0], rcx
0x140047869  push    rbx
0x14004786a  push    rbp
0x14004786b  push    rsi
0x14004786c  push    rdi
0x14004786d  push    r12
0x14004786f  push    r13
0x140047871  push    r14
0x140047873  push    r15
0x140047875  sub     rsp, 48h
0x140047879  mov     rax, [rdx]
0x14004787c  mov     r14, rdx
0x14004787f  mov     r12d, [rdx+1Ch]
0x140047883  mov     r13d, [rdx+18h]
0x140047887  mov     rcx, [rax+20h]
0x14004788b  mov     [rsp+88h+arg_8], rcx
0x140047893  mov     rcx, [rax+18h]
0x140047897  mov     [rsp+88h+arg_10], rcx
0x14004789f  mov     rcx, [rax+10h]
0x1400478a3  mov     [rsp+88h+arg_18], rcx
0x1400478ab  mov     rcx, [rax+8]
0x1400478af  mov     rax, [rax]
0x1400478b2  mov     [rsp+88h+arg_0], rcx
0x1400478ba  xor     ecx, ecx; ProcNumber
0x1400478bc  mov     r15, [rax]
0x1400478bf  mov     rsi, [r15+8]
0x1400478c3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400478ca  nop     dword ptr [rax+rax+00h]
0x1400478cf  xor     edx, edx; struct std::nothrow_t *
0x1400478d1  or      ebp, 0FFFFFFFFh
0x1400478d4  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400478da  lea     rbx, [rdx+rdx*2]
0x1400478de  shl     rbx, 6
0x1400478e2  add     rbx, cs:qword_140269408
0x1400478e9  cmp     dword ptr [rbx], 0DD0h
0x1400478ef  jnb     short loc_1400478FD
0x1400478f1  xor     ebx, ebx
0x1400478f3  mov     ecx, 0DE0h
0x1400478f8  jmp     loc_140047ADF
0x1400478fd  cmp     byte ptr [rbx+8], 0
0x140047901  jnz     loc_140047A93
0x140047907  mov     rcx, [rbx+58h]
0x14004790b  mov     rax, rcx
0x14004790e  sar     rax, 20h
0x140047912  cmp     ecx, eax
0x140047914  jle     loc_140047AD3
0x14004791a  nop
0x14004791b  mov     ecx, ebp
0x14004791d  lock xadd [rbx+58h], ecx
0x140047922  nop
0x140047923  dec     ecx
0x140047925  mov     eax, [rbx+5Ch]
0x140047928  cmp     ecx, eax
0x14004792a  jge     loc_140047AB3
0x140047930  xor     edi, edi
0x140047932  nop
0x140047933  lock inc dword ptr [rbx+58h]
0x140047937  nop
0x140047938  test    rdi, rdi
0x14004793b  jz      loc_140047AD3
0x140047941  mov     [rdi], rbx
0x140047944  add     rdi, 10h
0x140047948  jz      short loc_14004795A
0x14004794a  mov     [rdi+8], rsi
0x14004794e  mov     esi, 8000h
0x140047953  jmp     short loc_14004797A
0x140047955  test    rdi, rdi
0x140047958  jnz     short loc_140047941
0x14004795a  lea     rcx, [rsi+0A0h]; this
0x140047961  call    ?AllocateFromPool@CmsReservedPool@@QEAAPEAXXZ; CmsReservedPool::AllocateFromPool(void)
0x140047966  mov     rcx, rax; void *
0x140047969  mov     rdi, rax
0x14004796c  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x140047971  mov     [rdi+8], rsi
0x140047975  mov     esi, 10008000h
0x14004797a  mov     rax, [rsp+88h+arg_0]
0x140047982  mov     rcx, rsi
0x140047985  mov     rdx, [rsp+88h+arg_18]
0x14004798d  mov     r9d, r12d
0x140047990  mov     [rdi], rsi
0x140047993  mov     r8d, r13d
0x140047996  or      rcx, [r15]
0x140047999  mov     bl, [rdi+0DCh]
0x14004799f  mov     [rdi], rcx
0x1400479a2  mov     cl, [r15+0DCh]
0x1400479a9  mov     [rdi+0DCh], cl
0x1400479af  mov     rcx, [rsp+88h+arg_8]
0x1400479b7  mov     rax, [rax]
0x1400479ba  mov     rdx, [rdx]
0x1400479bd  mov     rcx, [rcx]
0x1400479c0  mov     [rsp+88h+var_60], rcx
0x1400479c5  mov     rcx, [rsp+88h+arg_10]
0x1400479cd  mov     rcx, [rcx]
0x1400479d0  mov     [rsp+88h+var_68], rcx
0x1400479d5  mov     rcx, rdi
0x1400479d8  call    _guard_dispatch_icall
0x1400479dd  xor     r9d, r9d; unsigned __int8
0x1400479e0  xor     r8d, r8d; struct _SmsLsn *
0x1400479e3  xor     edx, edx; unsigned __int8
0x1400479e5  mov     rcx, rdi; this
0x1400479e8  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1400479ed  mov     [rdi+0DCh], bl
0x1400479f3  mov     rcx, rdi; this
0x1400479f6  mov     rbx, [rdi+8]
0x1400479fa  mov     [rdi], rsi
0x1400479fd  call    ??1CmsTransactionContext@@AEAA@XZ; CmsTransactionContext::~CmsTransactionContext(void)
0x140047a02  bt      rsi, 1Ch
0x140047a07  jb      short loc_140047A82
0x140047a09  add     rdi, 0FFFFFFFFFFFFFFF0h
0x140047a0d  mov     rbx, [rdi]
0x140047a10  test    rbx, rbx
0x140047a13  jz      loc_140047B18
0x140047a19  cmp     byte ptr [rbx+8], 0
0x140047a1d  jz      loc_140047AFC
0x140047a23  cmp     byte ptr [rbx+9], 0
0x140047a27  lea     rcx, [rbx+40h]; Lookaside
0x140047a2b  mov     rdx, rdi; Entry
0x140047a2e  jz      short loc_140047A74
0x140047a30  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047a37  nop     dword ptr [rax+rax+00h]
0x140047a3c  mov     rax, [r14+10h]
0x140047a40  nop
0x140047a41  lock xadd [rax], ebp
0x140047a45  lea     eax, [rbp-1]
0x140047a48  nop
0x140047a49  test    eax, eax
0x140047a4b  jnz     short loc_140047A62
0x140047a4d  mov     rcx, [r14+20h]; Event
0x140047a51  xor     r8d, r8d; Wait
0x140047a54  xor     edx, edx; Increment
0x140047a56  call    cs:__imp_KeSetEvent
0x140047a5d  nop     dword ptr [rax+rax+00h]
0x140047a62  add     rsp, 48h
0x140047a66  pop     r15
0x140047a68  pop     r14
0x140047a6a  pop     r13
0x140047a6c  pop     r12
0x140047a6e  pop     rdi
0x140047a6f  pop     rsi
0x140047a70  pop     rbp
0x140047a71  pop     rbx
0x140047a72  retn
0x140047a74  call    cs:__imp_ExFreeToPagedLookasideList
0x140047a7b  nop     dword ptr [rax+rax+00h]
0x140047a80  jmp     short loc_140047A3C
0x140047a82  lea     rcx, [rbx+0A0h]; this
0x140047a89  mov     rdx, rdi; void *
0x140047a8c  call    ?FreeToPool@CmsReservedPool@@QEAAEPEAX@Z; CmsReservedPool::FreeToPool(void *)
0x140047a91  jmp     short loc_140047A3C
0x140047a93  cmp     byte ptr [rbx+9], 0
0x140047a97  lea     rcx, [rbx+40h]; Lookaside
0x140047a9b  jz      loc_1401FCEF4
0x140047aa1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140047aa8  nop     dword ptr [rax+rax+00h]
0x140047aad  nop
0x140047aae  jmp     loc_1401FCF00
0x140047ab3  test    ecx, ecx
0x140047ab5  js      loc_140047930
0x140047abb  lea     rcx, [rbx+40h]; ListHead
0x140047abf  call    cs:__imp_ExpInterlockedPopEntrySList
0x140047ac6  nop     dword ptr [rax+rax+00h]
0x140047acb  mov     rdi, rax
0x140047ace  jmp     loc_140047938
0x140047ad3  test    rbx, rbx
0x140047ad6  jz      loc_1400478F3
0x140047adc  mov     ecx, [rbx+4]; unsigned __int64
0x140047adf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140047ae4  mov     rdi, rax
0x140047ae7  test    al, 0Fh
0x140047ae9  jz      loc_1401FCF12
0x140047aef  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140047af6  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140047afc  mov     rcx, [rbx+58h]
0x140047b00  cmp     ecx, [rbx+50h]
0x140047b03  jl      loc_1401FCF2A
0x140047b09  mov     rax, rcx
0x140047b0c  sar     rax, 20h
0x140047b10  cmp     eax, ecx
0x140047b12  jge     loc_1401FCF2A
0x140047b18  mov     rcx, rdi; void *
0x140047b1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140047b20  jmp     loc_140047A3C
0x1401fcef4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401fcefb  nop     dword ptr [rax+rax+00h]
0x1401fcf00  lea     rcx, [rax+8]; void *
0x1401fcf04  mov     rdi, rax
0x1401fcf07  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401fcf0c  nop
0x1401fcf0d  jmp     loc_140047938
0x1401fcf12  test    rax, rax
0x1401fcf15  jz      loc_140047955
0x1401fcf1b  lea     rcx, [rax+10h]; void *
0x1401fcf1f  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401fcf24  nop
0x1401fcf25  jmp     loc_140047941
0x1401fcf2a  lea     rcx, [rbx+40h]; ListHead
0x1401fcf2e  mov     rdx, rdi; ListEntry
0x1401fcf31  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fcf38  nop     dword ptr [rax+rax+00h]
0x1401fcf3d  nop
0x1401fcf3e  lock inc dword ptr [rbx+58h]
0x1401fcf42  nop
0x1401fcf43  jmp     loc_140047A3C
```
