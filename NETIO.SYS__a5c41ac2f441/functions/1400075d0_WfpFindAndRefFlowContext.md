# WfpFindAndRefFlowContext

- ea: `0x1400075d0`
- end: `0x140007ac0`
- name: `WfpFindAndRefFlowContext`
- size: `1264`
- prototype: `void __fastcall(struct _LIST_ENTRY *, __int16, int, int, _QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a210`
- `0x14002e150`
- `0x1400427c0`
- `0x14006c850`

## callees

- `0x1400075d0`
- `0x140007ad0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007962`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007962`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140007734`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140007734`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400076e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400077cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400078ec`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400079c5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400076e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400077cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400078ec`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400079c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400076ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000798a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400076ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000798a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400076c6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400076c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400077f9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400077f9`
- `NDIS!NdisAcquireRWLockRead` at `0x1400079a8`
- `NDIS!NdisAcquireRWLockRead` at `0x1400079a8`
- `NDIS!NdisReleaseRWLock` at `0x14000791d`
- `NDIS!NdisReleaseRWLock` at `0x14000791d`

## pseudocode

```c
void __fastcall WfpFindAndRefFlowContext(struct _LIST_ENTRY *a1, __int16 a2, int a3, int a4, _QWORD *a5, _QWORD *a6)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rsi
  ULONG_PTR v12; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v14; // r8
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  char v16; // r9
  unsigned __int32 v17; // ecx
  _DWORD *v18; // rdx
  PNPAGED_LOOKASIDE_LIST v19; // rbx
  _DWORD *v20; // rdx
  PNPAGED_LOOKASIDE_LIST v21; // rdi
  KIRQL v22; // bl
  __int64 v23; // rdx
  unsigned __int16 *Signature; // r9
  unsigned int j; // eax
  __int64 v26; // r10
  struct _LIST_ENTRY *Blink; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-88h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+38h] [rbp-80h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-68h] BYREF
  volatile signed __int32 *p_Blink; // [rsp+E8h] [rbp+30h]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *a6 = 0;
  *a5 = 0;
  v11 = 0;
  memset(&Context, 0, sizeof(Context));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _mm_lfence();
  v12 = 37
      * (BYTE6(a1)
       + 37
       * (BYTE5(a1)
        + 37 * (BYTE4(a1) + 37 * (BYTE3(a1) + 37 * (BYTE2(a1) + 37 * (BYTE1(a1) + 37LL * (unsigned __int8)a1))))))
      + ((unsigned __int64)a1 >> 56);
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock(&handleTableLock, &LockHandle);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v14 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v14 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v14 = 4;
  }
  if ( !v12 )
    v12 = -1;
  for ( i = RtlLookupEntryHashTable(&handleTable, v12, &Context); i; i = RtlGetNextEntryHashTable(
                                                                           &handleTable,
                                                                           &Context) )
  {
    if ( i[1].Linkage.Flink == a1 )
    {
      v11 = i - 3;
      if ( gAleDebugEnabled )
      {
        Blink = v11[6].Linkage.Blink;
        if ( Blink != (struct _LIST_ENTRY *)0xBADBADFABADBADFALL )
          _InterlockedIncrement((volatile signed __int32 *)&Blink[1].Blink);
      }
      p_Blink = (volatile signed __int32 *)&v11[5].Linkage.Blink;
      v16 = BYTE5(v11[5].Linkage.Blink);
      while ( 1 )
      {
        v17 = *p_Blink;
        if ( (*p_Blink & 2) != 0 || (v17 & 1) == 0 && (v16 || v17 < 4) )
          break;
        if ( v17 == _InterlockedCompareExchange(p_Blink, v17 + 4, v17) )
          goto LABEL_14;
      }
      v11 = 0;
      break;
    }
  }
LABEL_14:
  if ( gWfpPerProContext )
  {
    v18 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v18 == 4 )
      *v18 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v11 )
  {
    v21 = gWfpGlobal;
    v22 = KeGetCurrentIrql();
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v21[3].L.AllocateEx, &LockState, 0);
    if ( v22 != 2 && gWfpPerProContext )
    {
      v23 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v23 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v23 = 4;
    }
    Signature = (unsigned __int16 *)v11[4].Signature;
    if ( (unsigned __int64)Signature >= 2 && (*((_DWORD *)Signature + 1) & 1) == 0 )
    {
      for ( j = 0; j < *Signature; ++j )
      {
        v26 = *((_QWORD *)Signature + 1) + 32LL * j;
        if ( *(_DWORD *)(v26 + 12) == a3 && *(_WORD *)(v26 + 8) == a2 )
        {
          if ( a4 )
            *(_DWORD *)v26 |= 2u;
          if ( (*(_DWORD *)v26 & 3) != 1 && *(_QWORD *)(v26 + 16) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 4));
            *a5 = *(_QWORD *)(v26 + 16);
          }
          *a6 = *(_QWORD *)(v26 + 24);
          break;
        }
      }
    }
    v19 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v20 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v20 == 4 )
        *v20 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v19[3].L.AllocateEx, &LockState);
    WfpAleDereferenceEndpoint(v11);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"KfdAleFindFlowContextTable",
        37);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"KfdAleFindFlowContextTable",
        37);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"KfdAleGetTableFromHandle",
        37);
    }
  }
}

```

## disassembly

```asm
0x1400075d0  push    rbx
0x1400075d2  push    rbp
0x1400075d3  push    rsi
0x1400075d4  push    rdi
0x1400075d5  push    r12
0x1400075d7  push    r13
0x1400075d9  push    r14
0x1400075db  push    r15
0x1400075dd  sub     rsp, 78h
0x1400075e1  mov     r15, [rsp+0B8h+arg_28]
0x1400075e9  xor     eax, eax
0x1400075eb  mov     word ptr [rsp+0B8h+LockState.OldIrql], ax
0x1400075f0  mov     rbp, rcx
0x1400075f3  mov     [rsp+0B8h+LockState.Flags], al
0x1400075f7  xor     ecx, ecx
0x1400075f9  mov     rax, [rsp+0B8h+arg_20]
0x140007601  xorps   xmm0, xmm0
0x140007604  mov     r12d, r9d
0x140007607  mov     [r15], rcx
0x14000760a  mov     r14d, r8d
0x14000760d  mov     rdi, rbp
0x140007610  shr     rdi, 38h
0x140007614  movzx   r13d, dx
0x140007618  mov     [rax], rcx
0x14000761b  mov     esi, ecx
0x14000761d  xor     eax, eax
0x14000761f  mov     [rsp+0B8h+Context.Signature], rax
0x140007624  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140007629  mov     rax, rbp
0x14000762c  shr     rax, 30h
0x140007630  movzx   ebx, al
0x140007633  mov     rax, rbp
0x140007636  shr     rax, 28h
0x14000763a  movzx   r11d, al
0x14000763e  mov     rax, rbp
0x140007641  shr     rax, 20h
0x140007645  movzx   r10d, al
0x140007649  mov     rax, rbp
0x14000764c  shr     rax, 18h
0x140007650  movzx   r9d, al
0x140007654  mov     rax, rbp
0x140007657  shr     rax, 10h
0x14000765b  movzx   r8d, al
0x14000765f  mov     rax, rbp
0x140007662  shr     rax, 8
0x140007666  movzx   edx, al
0x140007669  movzx   eax, bpl
0x14000766d  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x140007672  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140007677  lfence
0x14000767a  imul    rcx, rax, 25h ; '%'
0x14000767e  add     rcx, rdx
0x140007681  imul    rax, rcx, 25h ; '%'
0x140007685  add     rax, r8
0x140007688  imul    rcx, rax, 25h ; '%'
0x14000768c  add     rcx, r9
0x14000768f  imul    rax, rcx, 25h ; '%'
0x140007693  add     rax, r10
0x140007696  imul    rcx, rax, 25h ; '%'
0x14000769a  add     rcx, r11
0x14000769d  imul    rax, rcx, 25h ; '%'
0x1400076a1  add     rax, rbx
0x1400076a4  imul    rax, 25h ; '%'
0x1400076a8  add     rdi, rax
0x1400076ab  call    cs:__imp_KeGetCurrentIrql
0x1400076b2  nop     dword ptr [rax+rax+00h]
0x1400076b7  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x1400076bc  movzx   ebx, al
0x1400076bf  lea     rcx, handleTableLock; SpinLock
0x1400076c6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400076cd  nop     dword ptr [rax+rax+00h]
0x1400076d2  cmp     bl, 2
0x1400076d5  jz      short loc_140007717
0x1400076d7  cmp     cs:gWfpPerProContext, rsi
0x1400076de  jz      short loc_140007717
0x1400076e0  xor     ecx, ecx; ProcNumber
0x1400076e2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400076e9  nop     dword ptr [rax+rax+00h]
0x1400076ee  imul    eax, cs:gWfpPerProContextSize
0x1400076f5  mov     ecx, eax
0x1400076f7  mov     rax, cs:gWfpPerProContext
0x1400076fe  mov     r8, [rcx+rax]
0x140007702  mov     rax, ds:0FFFFF78000000008h
0x14000770c  mov     [r8+8], rax
0x140007710  mov     dword ptr [r8], 4
0x140007717  test    rdi, rdi
0x14000771a  lea     r8, [rsp+0B8h+Context]; Context
0x14000771f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140007726  lea     rcx, handleTable; HashTable
0x14000772d  cmovz   rdi, rax
0x140007731  mov     rdx, rdi; Signature
0x140007734  call    cs:__imp_RtlLookupEntryHashTable
0x14000773b  nop     dword ptr [rax+rax+00h]
0x140007740  test    rax, rax
0x140007743  jz      short loc_1400077BF
0x140007745  cmp     [rax+18h], rbp
0x140007749  jnz     loc_140007956
0x14000774f  cmp     cs:gAleDebugEnabled, 0
0x140007756  lea     rsi, [rax-48h]
0x14000775a  jnz     loc_140007A9D
0x140007760  lea     rax, [rsi+80h]
0x140007767  mov     [rsp+0B8h+arg_28], rax
0x14000776f  mov     rax, [rsp+0B8h+arg_28]
0x140007777  mov     [rsp+0B8h+arg_28], rax
0x14000777f  mov     rax, [rsp+0B8h+arg_28]
0x140007787  movzx   r9d, byte ptr [rax+5]
0x14000778c  mov     rcx, [rsp+0B8h+arg_28]
0x140007794  mov     ecx, [rcx]
0x140007796  test    cl, 2
0x140007799  jnz     loc_14000797C
0x14000779f  test    cl, 1
0x1400077a2  jz      loc_140007973
0x1400077a8  mov     rdx, [rsp+0B8h+arg_28]
0x1400077b0  lea     r8d, [rcx+4]
0x1400077b4  mov     eax, ecx
0x1400077b6  lock cmpxchg [rdx], r8d
0x1400077bb  cmp     ecx, eax
0x1400077bd  jnz     short loc_14000778C
0x1400077bf  cmp     cs:gWfpPerProContext, 0
0x1400077c7  jz      short loc_1400077F4
0x1400077c9  xor     ecx, ecx; ProcNumber
0x1400077cb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400077d2  nop     dword ptr [rax+rax+00h]
0x1400077d7  imul    eax, cs:gWfpPerProContextSize
0x1400077de  mov     ecx, eax
0x1400077e0  mov     rax, cs:gWfpPerProContext
0x1400077e7  mov     rdx, [rcx+rax]
0x1400077eb  cmp     dword ptr [rdx], 4
0x1400077ee  jz      loc_14000794B
0x1400077f4  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x1400077f9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007800  nop     dword ptr [rax+rax+00h]
0x140007805  test    rsi, rsi
0x140007808  jnz     loc_140007983
0x14000780e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007815  lea     rbx, WPP_GLOBAL_Control
0x14000781c  cmp     rcx, rbx
0x14000781f  jz      short loc_14000782B
0x140007821  cmp     byte ptr [rcx+29h], 2
0x140007825  jnb     loc_140007A67
0x14000782b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007832  cmp     rcx, rbx
0x140007835  jz      short loc_14000786A
0x140007837  cmp     byte ptr [rcx+29h], 2
0x14000783b  jb      short loc_14000786A
0x14000783d  test    dword ptr [rcx+2Ch], 1000h
0x140007844  jz      short loc_14000786A
0x140007846  mov     rcx, [rcx+18h]
0x14000784a  lea     r9, aKfdalefindflow; "KfdAleFindFlowContextTable"
0x140007851  mov     edx, 0Fh
0x140007856  mov     [rsp+0B8h+var_98], 0C0000225h
0x14000785e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140007865  call    WPP_SF_sd
0x14000786a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007871  cmp     rcx, rbx
0x140007874  jz      loc_140007931
0x14000787a  cmp     byte ptr [rcx+29h], 2
0x14000787e  jb      loc_140007931
0x140007884  test    dword ptr [rcx+2Ch], 1000h
0x14000788b  jz      loc_140007931
0x140007891  mov     rcx, [rcx+18h]
0x140007895  lea     r9, aKfdalegettable; "KfdAleGetTableFromHandle"
0x14000789c  mov     edx, 0Fh
0x1400078a1  mov     [rsp+0B8h+var_98], 0C0000225h
0x1400078a9  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400078b0  call    WPP_SF_sd
0x1400078b5  jmp     short loc_140007931
0x1400078b7  cmp     qword ptr [r10+10h], 0
0x1400078bc  jz      short loc_1400078D2
0x1400078be  lock inc dword ptr [r10+4]
0x1400078c3  mov     rcx, [rsp+0B8h+arg_20]
0x1400078cb  mov     rax, [r10+10h]
0x1400078cf  mov     [rcx], rax
0x1400078d2  mov     rax, [r10+18h]
0x1400078d6  mov     [r15], rax
0x1400078d9  cmp     cs:gWfpPerProContext, 0
0x1400078e1  mov     rbx, cs:gWfpGlobal
0x1400078e8  jz      short loc_140007911
0x1400078ea  xor     ecx, ecx; ProcNumber
0x1400078ec  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400078f3  nop     dword ptr [rax+rax+00h]
0x1400078f8  imul    eax, cs:gWfpPerProContextSize
0x1400078ff  mov     ecx, eax
0x140007901  mov     rax, cs:gWfpPerProContext
0x140007908  mov     rdx, [rcx+rax]
0x14000790c  cmp     dword ptr [rdx], 4
0x14000790f  jz      short loc_140007943
0x140007911  mov     rcx, [rbx+1B0h]; Lock
0x140007918  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14000791d  call    cs:__imp_NdisReleaseRWLock
0x140007924  nop     dword ptr [rax+rax+00h]
0x140007929  mov     rcx, rsi
0x14000792c  call    WfpAleDereferenceEndpoint
0x140007931  add     rsp, 78h
0x140007935  pop     r15
0x140007937  pop     r14
0x140007939  pop     r13
0x14000793b  pop     r12
0x14000793d  pop     rdi
0x14000793e  pop     rsi
0x14000793f  pop     rbp
0x140007940  pop     rbx
0x140007941  retn
0x140007943  mov     dword ptr [rdx], 0
0x140007949  jmp     short loc_140007911
0x14000794b  mov     dword ptr [rdx], 0
0x140007951  jmp     loc_1400077F4
0x140007956  lea     rdx, [rsp+0B8h+Context]; Context
0x14000795b  lea     rcx, handleTable; HashTable
0x140007962  call    cs:__imp_RtlGetNextEntryHashTable
0x140007969  nop     dword ptr [rax+rax+00h]
0x14000796e  jmp     loc_140007740
0x140007973  test    r9b, r9b
0x140007976  jz      loc_140007A59
0x14000797c  xor     esi, esi
0x14000797e  jmp     loc_1400077BF
0x140007983  mov     rdi, cs:gWfpGlobal
0x14000798a  call    cs:__imp_KeGetCurrentIrql
0x140007991  nop     dword ptr [rax+rax+00h]
0x140007996  mov     rcx, [rdi+1B0h]; Lock
0x14000799d  lea     rdx, [rsp+0B8h+LockState]; LockState
0x1400079a2  xor     r8d, r8d; Flags
0x1400079a5  movzx   ebx, al
0x1400079a8  call    cs:__imp_NdisAcquireRWLockRead
0x1400079af  nop     dword ptr [rax+rax+00h]
0x1400079b4  cmp     bl, 2
0x1400079b7  jz      short loc_1400079F9
0x1400079b9  cmp     cs:gWfpPerProContext, 0
0x1400079c1  jz      short loc_1400079F9
0x1400079c3  xor     ecx, ecx; ProcNumber
0x1400079c5  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400079cc  nop     dword ptr [rax+rax+00h]
0x1400079d1  imul    eax, cs:gWfpPerProContextSize
0x1400079d8  mov     ecx, eax
0x1400079da  mov     rax, cs:gWfpPerProContext
0x1400079e1  mov     rdx, [rcx+rax]
0x1400079e5  mov     rax, ds:0FFFFF78000000008h
0x1400079ef  mov     [rdx+8], rax
0x1400079f3  mov     dword ptr [rdx], 4
0x1400079f9  mov     r9, [rsi+70h]
0x1400079fd  cmp     r9, 2
0x140007a01  jb      loc_1400078D9
0x140007a07  mov     eax, [r9+4]
0x140007a0b  test    al, 1
0x140007a0d  jnz     loc_1400078D9
0x140007a13  movzx   r8d, word ptr [r9]
0x140007a17  xor     eax, eax
0x140007a19  cmp     eax, r8d
0x140007a1c  jnb     loc_1400078D9
0x140007a22  mov     r10d, eax
0x140007a25  shl     r10, 5
0x140007a29  add     r10, [r9+8]
0x140007a2d  cmp     [r10+0Ch], r14d
0x140007a31  jz      short loc_140007A37
0x140007a33  inc     eax
0x140007a35  jmp     short loc_140007A19
0x140007a37  cmp     [r10+8], r13w
0x140007a3c  jnz     short loc_140007A33
0x140007a3e  test    r12d, r12d
0x140007a41  jz      short loc_140007A47
0x140007a43  or      dword ptr [r10], 2
0x140007a47  mov     eax, [r10]
0x140007a4a  and     al, 3
0x140007a4c  cmp     al, 1
0x140007a4e  jz      loc_1400078D2
0x140007a54  jmp     loc_1400078B7
0x140007a59  cmp     ecx, 4
0x140007a5c  jb      loc_14000797C
0x140007a62  jmp     loc_1400077A8
0x140007a67  test    dword ptr [rcx+2Ch], 1000h
0x140007a6e  jz      loc_14000782B
0x140007a74  mov     rcx, [rcx+18h]
0x140007a78  lea     r9, aKfdalefindflow; "KfdAleFindFlowContextTable"
0x140007a7f  mov     edx, 0Ah
0x140007a84  mov     [rsp+0B8h+var_98], 0C0000225h
0x140007a8c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140007a93  call    WPP_SF_sd
0x140007a98  jmp     loc_14000782B
0x140007a9d  mov     rax, [rsi+98h]
0x140007aa4  mov     rcx, 0BADBADFABADBADFAh
0x140007aae  cmp     rax, rcx
0x140007ab1  jz      loc_140007760
0x140007ab7  lock inc dword ptr [rax+18h]
0x140007abb  jmp     loc_140007760
```
