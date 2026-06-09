# WfpFindAndDeRefFlowContext

- ea: `0x1400070d0`
- end: `0x1400075bb`
- name: `WfpFindAndDeRefFlowContext`
- size: `1259`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400068d0`
- `0x14000cf4c`
- `0x14001a210`
- `0x14002e150`
- `0x14006c850`

## callees

- `0x1400070d0`
- `0x140007ad0`
- `0x14001cea0`
- `0x14001cfe0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007507`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007507`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140007219`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140007219`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400071c7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000729e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400073d2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000746f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400071c7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000729e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400073d2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000746f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007190`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007434`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007190`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007434`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400071ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400071ab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400072cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400072cc`
- `NDIS!NdisAcquireRWLockRead` at `0x140007452`
- `NDIS!NdisAcquireRWLockRead` at `0x140007452`
- `NDIS!NdisReleaseRWLock` at `0x140007407`
- `NDIS!NdisReleaseRWLock` at `0x140007407`

## pseudocode

```c
void __fastcall WfpFindAndDeRefFlowContext(unsigned __int64 a1, unsigned __int16 a2, int a3, int a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // rsi
  ULONG_PTR v9; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v11; // r8
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  char v13; // r9
  unsigned __int32 v14; // ecx
  _DWORD *v15; // rdx
  signed __int32 v16; // ecx
  PNPAGED_LOOKASIDE_LIST v17; // rbx
  _DWORD *v18; // rcx
  PNPAGED_LOOKASIDE_LIST v19; // rdi
  KIRQL v20; // bl
  __int64 v21; // rdx
  unsigned __int16 *Signature; // r9
  unsigned int j; // eax
  __int64 v24; // r10
  struct _LIST_ENTRY *Blink; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int32 *p_Blink; // [rsp+38h] [rbp-80h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+40h] [rbp-78h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+58h] [rbp-60h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  memset(&Context, 0, sizeof(Context));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _mm_lfence();
  v9 = 37
     * (BYTE6(a1)
      + 37
      * (BYTE5(a1)
       + 37 * (BYTE4(a1) + 37 * (BYTE3(a1) + 37 * (BYTE2(a1) + 37 * (BYTE1(a1) + 37LL * (unsigned __int8)a1))))))
     + HIBYTE(a1);
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock(&handleTableLock, &LockHandle);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v11 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v11 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v11 = 4;
  }
  if ( !v9 )
    v9 = -1;
  for ( i = RtlLookupEntryHashTable(&handleTable, v9, &Context); i; i = RtlGetNextEntryHashTable(&handleTable, &Context) )
  {
    if ( i[1].Linkage.Flink == (struct _LIST_ENTRY *)a1 )
    {
      v6 = i - 3;
      if ( gAleDebugEnabled )
      {
        Blink = v6[6].Linkage.Blink;
        if ( Blink != (struct _LIST_ENTRY *)0xBADBADFABADBADFALL )
          _InterlockedIncrement((volatile signed __int32 *)&Blink[1].Blink);
      }
      p_Blink = (unsigned __int32 *)&v6[5].Linkage.Blink;
      v13 = BYTE5(v6[5].Linkage.Blink);
      while ( 1 )
      {
        v14 = *p_Blink;
        if ( (*p_Blink & 2) != 0 || (v14 & 1) == 0 && (v13 || v14 < 4) )
          break;
        if ( v14 == _InterlockedCompareExchange((volatile signed __int32 *)p_Blink, v14 + 4, v14) )
          goto LABEL_14;
      }
      v6 = 0;
      break;
    }
  }
LABEL_14:
  if ( gWfpPerProContext )
  {
    v15 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v15 == 4 )
      *v15 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v6 )
  {
    v19 = gWfpGlobal;
    v20 = KeGetCurrentIrql();
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v19[3].L.AllocateEx, &LockState, 0);
    if ( v20 != 2 && gWfpPerProContext )
    {
      v21 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v21 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v21 = 4;
    }
    Signature = (unsigned __int16 *)v6[4].Signature;
    if ( (unsigned __int64)Signature >= 2 && (*((_DWORD *)Signature + 1) & 1) == 0 )
    {
      for ( j = 0; j < *Signature; ++j )
      {
        v24 = *((_QWORD *)Signature + 1) + 32LL * j;
        if ( *(_DWORD *)(v24 + 12) == a3 && *(_WORD *)(v24 + 8) == a2 )
        {
          v16 = 0;
          if ( a4 )
            *(_DWORD *)v24 &= ~2u;
          if ( *(_QWORD *)(v24 + 16) )
            v16 = _InterlockedDecrement((volatile signed __int32 *)(v24 + 4));
          if ( (*(_DWORD *)v24 & 1) != 0 && !v16 )
          {
            WfpReleaseFastWriteLock(&gWfpGlobal[3].L.AllocateEx, &LockState);
            WfpRemoveContextFromFlow(a1, a2, a3);
            goto LABEL_38;
          }
          break;
        }
      }
    }
    v17 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v18 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v18 == 4 )
        *v18 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v17[3].L.AllocateEx, &LockState);
LABEL_38:
    WfpAleDereferenceEndpoint(v6);
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
0x1400070d0  push    rbx
0x1400070d2  push    rbp
0x1400070d3  push    rsi
0x1400070d4  push    rdi
0x1400070d5  push    r12
0x1400070d7  push    r13
0x1400070d9  push    r14
0x1400070db  push    r15
0x1400070dd  sub     rsp, 78h
0x1400070e1  xor     eax, eax
0x1400070e3  xorps   xmm0, xmm0
0x1400070e6  mov     word ptr [rsp+0B8h+LockState.OldIrql], ax
0x1400070eb  mov     r15d, r9d
0x1400070ee  mov     [rsp+0B8h+LockState.Flags], al
0x1400070f2  mov     r14d, r8d
0x1400070f5  mov     [rsp+0B8h+Context.Signature], rax
0x1400070fa  mov     rdi, rcx
0x1400070fd  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140007102  xor     esi, esi
0x140007104  mov     rax, rcx
0x140007107  shr     rdi, 38h
0x14000710b  shr     rax, 30h
0x14000710f  movzx   r12d, dx
0x140007113  movzx   ebx, al
0x140007116  mov     rbp, rcx
0x140007119  mov     rax, rcx
0x14000711c  shr     rax, 28h
0x140007120  movzx   r11d, al
0x140007124  mov     rax, rcx
0x140007127  shr     rax, 20h
0x14000712b  movzx   r10d, al
0x14000712f  mov     rax, rcx
0x140007132  shr     rax, 18h
0x140007136  movzx   r9d, al
0x14000713a  mov     rax, rcx
0x14000713d  shr     rax, 10h
0x140007141  movzx   r8d, al
0x140007145  mov     rax, rcx
0x140007148  shr     rax, 8
0x14000714c  movzx   edx, al
0x14000714f  movzx   eax, cl
0x140007152  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x140007157  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14000715c  lfence
0x14000715f  imul    rcx, rax, 25h ; '%'
0x140007163  add     rcx, rdx
0x140007166  imul    rax, rcx, 25h ; '%'
0x14000716a  add     rax, r8
0x14000716d  imul    rcx, rax, 25h ; '%'
0x140007171  add     rcx, r9
0x140007174  imul    rax, rcx, 25h ; '%'
0x140007178  add     rax, r10
0x14000717b  imul    rcx, rax, 25h ; '%'
0x14000717f  add     rcx, r11
0x140007182  imul    rax, rcx, 25h ; '%'
0x140007186  add     rax, rbx
0x140007189  imul    rax, 25h ; '%'
0x14000718d  add     rdi, rax
0x140007190  call    cs:__imp_KeGetCurrentIrql
0x140007197  nop     dword ptr [rax+rax+00h]
0x14000719c  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x1400071a1  movzx   ebx, al
0x1400071a4  lea     rcx, handleTableLock; SpinLock
0x1400071ab  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400071b2  nop     dword ptr [rax+rax+00h]
0x1400071b7  cmp     bl, 2
0x1400071ba  jz      short loc_1400071FC
0x1400071bc  cmp     cs:gWfpPerProContext, rsi
0x1400071c3  jz      short loc_1400071FC
0x1400071c5  xor     ecx, ecx; ProcNumber
0x1400071c7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400071ce  nop     dword ptr [rax+rax+00h]
0x1400071d3  imul    eax, cs:gWfpPerProContextSize
0x1400071da  mov     ecx, eax
0x1400071dc  mov     rax, cs:gWfpPerProContext
0x1400071e3  mov     r8, [rcx+rax]
0x1400071e7  mov     rax, ds:0FFFFF78000000008h
0x1400071f1  mov     [r8+8], rax
0x1400071f5  mov     dword ptr [r8], 4
0x1400071fc  test    rdi, rdi
0x1400071ff  lea     r8, [rsp+0B8h+Context]; Context
0x140007204  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14000720b  lea     rcx, handleTable; HashTable
0x140007212  cmovz   rdi, r13
0x140007216  mov     rdx, rdi; Signature
0x140007219  call    cs:__imp_RtlLookupEntryHashTable
0x140007220  nop     dword ptr [rax+rax+00h]
0x140007225  test    rax, rax
0x140007228  jz      short loc_140007292
0x14000722a  cmp     [rax+18h], rbp
0x14000722e  jnz     loc_1400074FB
0x140007234  cmp     cs:gAleDebugEnabled, 0
0x14000723b  lea     rsi, [rax-48h]
0x14000723f  jnz     loc_140007598
0x140007245  lea     rax, [rsi+80h]
0x14000724c  mov     [rsp+0B8h+var_80], rax
0x140007251  mov     rax, [rsp+0B8h+var_80]
0x140007256  mov     [rsp+0B8h+var_80], rax
0x14000725b  mov     rax, [rsp+0B8h+var_80]
0x140007260  movzx   r9d, byte ptr [rax+5]
0x140007265  mov     rcx, [rsp+0B8h+var_80]
0x14000726a  mov     ecx, [rcx]
0x14000726c  test    cl, 2
0x14000726f  jnz     loc_14000751D
0x140007275  test    cl, 1
0x140007278  jz      loc_140007518
0x14000727e  mov     rdx, [rsp+0B8h+var_80]
0x140007283  lea     r8d, [rcx+4]
0x140007287  mov     eax, ecx
0x140007289  lock cmpxchg [rdx], r8d
0x14000728e  cmp     ecx, eax
0x140007290  jnz     short loc_140007265
0x140007292  cmp     cs:gWfpPerProContext, 0
0x14000729a  jz      short loc_1400072C7
0x14000729c  xor     ecx, ecx; ProcNumber
0x14000729e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400072a5  nop     dword ptr [rax+rax+00h]
0x1400072aa  imul    eax, cs:gWfpPerProContextSize
0x1400072b1  mov     ecx, eax
0x1400072b3  mov     rax, cs:gWfpPerProContext
0x1400072ba  mov     rdx, [rcx+rax]
0x1400072be  cmp     dword ptr [rdx], 4
0x1400072c1  jz      loc_1400074E5
0x1400072c7  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x1400072cc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400072d3  nop     dword ptr [rax+rax+00h]
0x1400072d8  test    rsi, rsi
0x1400072db  jnz     loc_14000742D
0x1400072e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072e8  lea     rbx, WPP_GLOBAL_Control
0x1400072ef  cmp     rcx, rbx
0x1400072f2  jz      short loc_1400072FE
0x1400072f4  cmp     byte ptr [rcx+29h], 2
0x1400072f8  jnb     loc_14000752E
0x1400072fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140007305  cmp     rcx, rbx
0x140007308  jz      short loc_14000733D
0x14000730a  cmp     byte ptr [rcx+29h], 2
0x14000730e  jb      short loc_14000733D
0x140007310  test    dword ptr [rcx+2Ch], 1000h
0x140007317  jz      short loc_14000733D
0x140007319  mov     rcx, [rcx+18h]
0x14000731d  lea     r9, aKfdalefindflow; "KfdAleFindFlowContextTable"
0x140007324  mov     edx, 0Fh
0x140007329  mov     [rsp+0B8h+var_98], 0C0000225h
0x140007331  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140007338  call    WPP_SF_sd
0x14000733d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007344  cmp     rcx, rbx
0x140007347  jz      loc_14000741B
0x14000734d  cmp     byte ptr [rcx+29h], 2
0x140007351  jb      loc_14000741B
0x140007357  test    dword ptr [rcx+2Ch], 1000h
0x14000735e  jz      loc_14000741B
0x140007364  mov     rcx, [rcx+18h]
0x140007368  lea     r9, aKfdalegettable; "KfdAleGetTableFromHandle"
0x14000736f  mov     edx, 0Fh
0x140007374  mov     [rsp+0B8h+var_98], 0C0000225h
0x14000737c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140007383  call    WPP_SF_sd
0x140007388  jmp     loc_14000741B
0x14000738d  cmp     [r10+8], r12w
0x140007392  jnz     loc_1400074E1
0x140007398  xor     ecx, ecx
0x14000739a  test    r15d, r15d
0x14000739d  jz      short loc_1400073A3
0x14000739f  and     dword ptr [r10], 0FFFFFFFDh
0x1400073a3  cmp     [r10+10h], rcx
0x1400073a7  jz      short loc_1400073B4
0x1400073a9  mov     ecx, r13d
0x1400073ac  lock xadd [r10+4], ecx
0x1400073b2  dec     ecx
0x1400073b4  mov     eax, [r10]
0x1400073b7  test    al, 1
0x1400073b9  jnz     loc_140007564
0x1400073bf  cmp     cs:gWfpPerProContext, 0
0x1400073c7  mov     rbx, cs:gWfpGlobal
0x1400073ce  jz      short loc_1400073FB
0x1400073d0  xor     ecx, ecx; ProcNumber
0x1400073d2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400073d9  nop     dword ptr [rax+rax+00h]
0x1400073de  imul    eax, cs:gWfpPerProContextSize
0x1400073e5  mov     edx, eax
0x1400073e7  mov     rax, cs:gWfpPerProContext
0x1400073ee  mov     rcx, [rdx+rax]
0x1400073f2  cmp     dword ptr [rcx], 4
0x1400073f5  jz      loc_1400074F0
0x1400073fb  mov     rcx, [rbx+1B0h]; Lock
0x140007402  lea     rdx, [rsp+0B8h+LockState]; LockState
0x140007407  call    cs:__imp_NdisReleaseRWLock
0x14000740e  nop     dword ptr [rax+rax+00h]
0x140007413  mov     rcx, rsi
0x140007416  call    WfpAleDereferenceEndpoint
0x14000741b  add     rsp, 78h
0x14000741f  pop     r15
0x140007421  pop     r14
0x140007423  pop     r13
0x140007425  pop     r12
0x140007427  pop     rdi
0x140007428  pop     rsi
0x140007429  pop     rbp
0x14000742a  pop     rbx
0x14000742b  retn
0x14000742d  mov     rdi, cs:gWfpGlobal
0x140007434  call    cs:__imp_KeGetCurrentIrql
0x14000743b  nop     dword ptr [rax+rax+00h]
0x140007440  mov     rcx, [rdi+1B0h]; Lock
0x140007447  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14000744c  xor     r8d, r8d; Flags
0x14000744f  movzx   ebx, al
0x140007452  call    cs:__imp_NdisAcquireRWLockRead
0x140007459  nop     dword ptr [rax+rax+00h]
0x14000745e  cmp     bl, 2
0x140007461  jz      short loc_1400074A3
0x140007463  cmp     cs:gWfpPerProContext, 0
0x14000746b  jz      short loc_1400074A3
0x14000746d  xor     ecx, ecx; ProcNumber
0x14000746f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140007476  nop     dword ptr [rax+rax+00h]
0x14000747b  imul    eax, cs:gWfpPerProContextSize
0x140007482  mov     ecx, eax
0x140007484  mov     rax, cs:gWfpPerProContext
0x14000748b  mov     rdx, [rcx+rax]
0x14000748f  mov     rax, ds:0FFFFF78000000008h
0x140007499  mov     [rdx+8], rax
0x14000749d  mov     dword ptr [rdx], 4
0x1400074a3  mov     r9, [rsi+70h]
0x1400074a7  cmp     r9, 2
0x1400074ab  jb      loc_1400073BF
0x1400074b1  mov     eax, [r9+4]
0x1400074b5  test    al, 1
0x1400074b7  jnz     loc_1400073BF
0x1400074bd  movzx   r8d, word ptr [r9]
0x1400074c1  xor     eax, eax
0x1400074c3  cmp     eax, r8d
0x1400074c6  jnb     loc_1400073BF
0x1400074cc  mov     r10d, eax
0x1400074cf  shl     r10, 5
0x1400074d3  add     r10, [r9+8]
0x1400074d7  cmp     [r10+0Ch], r14d
0x1400074db  jz      loc_14000738D
0x1400074e1  inc     eax
0x1400074e3  jmp     short loc_1400074C3
0x1400074e5  mov     dword ptr [rdx], 0
0x1400074eb  jmp     loc_1400072C7
0x1400074f0  mov     dword ptr [rcx], 0
0x1400074f6  jmp     loc_1400073FB
0x1400074fb  lea     rdx, [rsp+0B8h+Context]; Context
0x140007500  lea     rcx, handleTable; HashTable
0x140007507  call    cs:__imp_RtlGetNextEntryHashTable
0x14000750e  nop     dword ptr [rax+rax+00h]
0x140007513  jmp     loc_140007225
0x140007518  test    r9b, r9b
0x14000751b  jz      short loc_140007524
0x14000751d  xor     esi, esi
0x14000751f  jmp     loc_140007292
0x140007524  cmp     ecx, 4
0x140007527  jb      short loc_14000751D
0x140007529  jmp     loc_14000727E
0x14000752e  test    dword ptr [rcx+2Ch], 1000h
0x140007535  jz      loc_1400072FE
0x14000753b  mov     rcx, [rcx+18h]
0x14000753f  lea     r9, aKfdalefindflow; "KfdAleFindFlowContextTable"
0x140007546  mov     edx, 0Ah
0x14000754b  mov     [rsp+0B8h+var_98], 0C0000225h
0x140007553  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000755a  call    WPP_SF_sd
0x14000755f  jmp     loc_1400072FE
0x140007564  test    ecx, ecx
0x140007566  jnz     loc_1400073BF
0x14000756c  mov     rcx, cs:gWfpGlobal
0x140007573  lea     rdx, [rsp+0B8h+LockState]
0x140007578  add     rcx, 1B0h
0x14000757f  call    WfpReleaseFastWriteLock
0x140007584  mov     r8d, r14d
0x140007587  movzx   edx, r12w
0x14000758b  mov     rcx, rbp; int
0x14000758e  call    WfpRemoveContextFromFlow
0x140007593  jmp     loc_140007413
0x140007598  mov     rax, [rsi+98h]
0x14000759f  mov     rcx, 0BADBADFABADBADFAh
0x1400075a9  cmp     rax, rcx
0x1400075ac  jz      loc_140007245
0x1400075b2  lock inc dword ptr [rax+18h]
0x1400075b6  jmp     loc_140007245
```
