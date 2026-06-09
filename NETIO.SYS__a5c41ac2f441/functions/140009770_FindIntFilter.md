# FindIntFilter

- ea: `0x140009770`
- end: `0x1400099ad`
- name: `FindIntFilter`
- size: `573`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009190`
- `0x140009580`
- `0x14001b4e8`
- `0x140067894`
- `0x140067aa8`
- `0x140067fa0`

## callees

- `0x140009520`
- `0x140009770`
- `0x140009e00`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000999c`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000999c`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400098bd`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400098bd`
- `NDIS!NdisAcquireRWLockRead` at `0x1400097a4`
- `NDIS!NdisAcquireRWLockRead` at `0x1400097a4`
- `NDIS!NdisReleaseRWLock` at `0x140009917`
- `NDIS!NdisReleaseRWLock` at `0x140009976`
- `NDIS!NdisReleaseRWLock` at `0x140009917`
- `NDIS!NdisReleaseRWLock` at `0x140009976`

## pseudocode

```c
__int64 __fastcall FindIntFilter(unsigned __int16 a1, struct _LIST_ENTRY *a2, ULONG_PTR *a3)
{
  int v3; // esi
  unsigned __int8 *v6; // r8
  ULONG_PTR v7; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v9; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdi
  PNPAGED_LOOKASIDE_LIST v13; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+8h] BYREF

  v3 = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
  memset(&Context, 0, sizeof(Context));
  _mm_lfence();
  _mm_lfence();
  v6 = (unsigned __int8 *)gWfpGlobal;
  _mm_lfence();
  v7 = v6[411]
     + 37
     * (v6[410]
      + 37
      * (v6[409]
       + 37
       * (v6[408]
        + 37
        * (((unsigned __int64)a2 >> 56)
         + 37
         * (BYTE6(a2)
          + 37
          * (BYTE5(a2)
           + 37
           * (BYTE4(a2)
            + 37
            * (BYTE3(a2)
             + 37
             * (BYTE2(a2) + 37
                          * (BYTE1(a2) + 37 * ((unsigned __int8)a2 + 37 * (37LL * (unsigned __int8)v3 + BYTE1(v3)))))))))))));
  if ( !v7 )
    v7 = -1;
  for ( i = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)&gWfpGlobal[3].L.Depth, v7, &Context);
        ;
        i = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)&gWfpGlobal[3].L.Depth, &Context) )
  {
    v10 = i;
    if ( !i )
      break;
    if ( LODWORD(i[1].Linkage.Flink) == gWfpGlobal[3].L.AllocateMisses
      && HIDWORD(i[1].Linkage.Flink) == v3
      && i[1].Linkage.Blink == a2 )
    {
      v12 = 0;
      goto LABEL_11;
    }
  }
  v10 = 0;
  v11 = WfpReportSysErrorAsNtStatus(v9, "RtlLookupEntryHashTable", 3221225473LL, 1);
  v12 = v11;
  if ( v11 )
  {
    WfpReportError(v11, "FindEntryFromFilterHashtable");
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
    WfpReportError(v12, "FindIntFilter");
    return v12;
  }
LABEL_11:
  _InterlockedIncrement64((volatile signed __int64 *)(v10[1].Signature + 16));
  v13 = gWfpGlobal;
  *a3 = v10[1].Signature;
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v13[13].L.ListEntry.Flink, &LockState);
  return v12;
}

```

## disassembly

```asm
0x140009770  push    rbx
0x140009772  push    rsi
0x140009773  push    rdi
0x140009774  push    r14
0x140009776  sub     rsp, 48h
0x14000977a  movzx   esi, cx
0x14000977d  xor     eax, eax
0x14000977f  mov     rcx, cs:gWfpGlobal
0x140009786  mov     r14, r8
0x140009789  mov     rdi, rdx
0x14000978c  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x140009791  mov     [rsp+68h+LockState.Flags], al
0x140009795  lea     rdx, [rsp+68h+LockState]; LockState
0x14000979a  mov     r8b, 1; Flags
0x14000979d  mov     rcx, [rcx+6C0h]; Lock
0x1400097a4  call    cs:__imp_NdisAcquireRWLockRead
0x1400097ab  nop     dword ptr [rax+rax+00h]
0x1400097b0  xor     eax, eax
0x1400097b2  xorps   xmm0, xmm0
0x1400097b5  mov     [rsp+68h+Context.Signature], rax
0x1400097ba  movzx   eax, si
0x1400097bd  shr     ax, 8
0x1400097c1  movzx   ecx, ax
0x1400097c4  movzx   eax, sil
0x1400097c8  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x1400097cd  lfence
0x1400097d0  imul    rax, 25h ; '%'
0x1400097d4  add     rcx, rax
0x1400097d7  lfence
0x1400097da  mov     r8, cs:gWfpGlobal
0x1400097e1  imul    rdx, rcx, 25h ; '%'
0x1400097e5  movzx   eax, dil
0x1400097e9  add     rdx, rax
0x1400097ec  mov     rax, rdi
0x1400097ef  shr     rax, 8
0x1400097f3  movzx   eax, al
0x1400097f6  imul    rcx, rdx, 25h ; '%'
0x1400097fa  add     rcx, rax
0x1400097fd  mov     rax, rdi
0x140009800  shr     rax, 10h
0x140009804  movzx   eax, al
0x140009807  imul    rdx, rcx, 25h ; '%'
0x14000980b  add     rdx, rax
0x14000980e  mov     rax, rdi
0x140009811  shr     rax, 18h
0x140009815  movzx   eax, al
0x140009818  imul    rcx, rdx, 25h ; '%'
0x14000981c  add     rcx, rax
0x14000981f  mov     rax, rdi
0x140009822  shr     rax, 20h
0x140009826  movzx   eax, al
0x140009829  imul    rdx, rcx, 25h ; '%'
0x14000982d  add     rdx, rax
0x140009830  mov     rax, rdi
0x140009833  shr     rax, 28h
0x140009837  movzx   eax, al
0x14000983a  imul    rcx, rdx, 25h ; '%'
0x14000983e  add     rcx, rax
0x140009841  mov     rax, rdi
0x140009844  shr     rax, 30h
0x140009848  movzx   eax, al
0x14000984b  imul    rdx, rcx, 25h ; '%'
0x14000984f  add     rdx, rax
0x140009852  mov     rax, rdi
0x140009855  imul    rdx, 25h ; '%'
0x140009859  shr     rax, 38h
0x14000985d  add     rdx, rax
0x140009860  lfence
0x140009863  movzx   eax, byte ptr [r8+198h]
0x14000986b  imul    rcx, rdx, 25h ; '%'
0x14000986f  add     rcx, rax
0x140009872  movzx   eax, byte ptr [r8+199h]
0x14000987a  imul    rdx, rcx, 25h ; '%'
0x14000987e  add     rdx, rax
0x140009881  movzx   eax, byte ptr [r8+19Ah]
0x140009889  imul    rcx, rdx, 25h ; '%'
0x14000988d  add     rcx, rax
0x140009890  movzx   eax, byte ptr [r8+19Bh]
0x140009898  imul    rdx, rcx, 25h ; '%'
0x14000989c  mov     rcx, cs:gWfpGlobal
0x1400098a3  lea     r8, [rsp+68h+Context]; Context
0x1400098a8  add     rdx, rax
0x1400098ab  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400098b2  cmovz   rdx, rax; Signature
0x1400098b6  mov     rcx, [rcx+190h]; HashTable
0x1400098bd  call    cs:__imp_RtlLookupEntryHashTable
0x1400098c4  nop     dword ptr [rax+rax+00h]
0x1400098c9  mov     rbx, rax
0x1400098cc  test    rax, rax
0x1400098cf  jnz     short loc_140009934
0x1400098d1  xor     edi, edi
0x1400098d3  lea     rdx, aRtllookupentry; "RtlLookupEntryHashTable"
0x1400098da  mov     r9d, 1
0x1400098e0  mov     r8d, 0C0000001h
0x1400098e6  mov     ebx, edi
0x1400098e8  call    WfpReportSysErrorAsNtStatus
0x1400098ed  mov     rdi, rax
0x1400098f0  test    rax, rax
0x1400098f3  jz      short loc_140009953
0x1400098f5  lea     rdx, aFindentryfromf; "FindEntryFromFilterHashtable"
0x1400098fc  mov     rcx, rax
0x1400098ff  call    WfpReportError
0x140009904  mov     rcx, cs:gWfpGlobal
0x14000990b  lea     rdx, [rsp+68h+LockState]; LockState
0x140009910  mov     rcx, [rcx+6C0h]; Lock
0x140009917  call    cs:__imp_NdisReleaseRWLock
0x14000991e  nop     dword ptr [rax+rax+00h]
0x140009923  lea     rdx, aFindintfilter; "FindIntFilter"
0x14000992a  mov     rcx, rdi
0x14000992d  call    WfpReportError
0x140009932  jmp     short loc_140009982
0x140009934  mov     rcx, cs:gWfpGlobal
0x14000993b  mov     eax, [rcx+198h]
0x140009941  cmp     [rbx+18h], eax
0x140009944  jnz     short loc_140009990
0x140009946  cmp     [rbx+1Ch], esi
0x140009949  jnz     short loc_140009990
0x14000994b  cmp     [rbx+20h], rdi
0x14000994f  jnz     short loc_140009990
0x140009951  xor     edi, edi
0x140009953  mov     rax, [rbx+28h]
0x140009957  lock inc qword ptr [rax+10h]
0x14000995c  mov     rcx, cs:gWfpGlobal
0x140009963  lea     rdx, [rsp+68h+LockState]; LockState
0x140009968  mov     rax, [rbx+28h]
0x14000996c  mov     [r14], rax
0x14000996f  mov     rcx, [rcx+6C0h]; Lock
0x140009976  call    cs:__imp_NdisReleaseRWLock
0x14000997d  nop     dword ptr [rax+rax+00h]
0x140009982  mov     rax, rdi
0x140009985  add     rsp, 48h
0x140009989  pop     r14
0x14000998b  pop     rdi
0x14000998c  pop     rsi
0x14000998d  pop     rbx
0x14000998e  retn
0x140009990  mov     rcx, [rcx+190h]; HashTable
0x140009997  lea     rdx, [rsp+68h+Context]; Context
0x14000999c  call    cs:__imp_RtlGetNextEntryHashTable
0x1400099a3  nop     dword ptr [rax+rax+00h]
0x1400099a8  jmp     loc_1400098C9
```
