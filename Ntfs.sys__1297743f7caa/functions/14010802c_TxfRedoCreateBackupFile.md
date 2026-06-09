# TxfRedoCreateBackupFile

- ea: `0x14010802c`
- end: `0x14010860a`
- name: `TxfRedoCreateBackupFile`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140133f80`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140012e70`
- `0x14001c8c0`
- `0x140020de0`
- `0x1400f95cc`
- `0x14010802c`
- `0x14012b270`
- `0x140133244`
- `0x1401403d0`
- `0x140140fac`
- `0x1401911a8`
- `0x140191424`
- `0x140194cb8`
- `0x1401d2c84`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402c573e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402c573e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c571c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c571c`
- `ntoskrnl!DbgPrintEx` at `0x14010815a`
- `ntoskrnl!DbgPrintEx` at `0x1401082cb`
- `ntoskrnl!DbgPrintEx` at `0x14010815a`
- `ntoskrnl!DbgPrintEx` at `0x1401082cb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402c5779`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402c5779`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401085ea`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c57cd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401085ea`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c57cd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14010819b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14010819b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140108550`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140108550`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14010852d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14010852d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140108567`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140108567`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401085a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401085a2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010809a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010809a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401080cc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401080cc`
- `ntoskrnl!ExRaiseStatus` at `0x140108182`
- `ntoskrnl!ExRaiseStatus` at `0x1401083b8`
- `ntoskrnl!ExRaiseStatus` at `0x140108182`
- `ntoskrnl!ExRaiseStatus` at `0x1401083b8`

## pseudocode

```c
void __fastcall TxfRedoCreateBackupFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r15
  _QWORD *v8; // r14
  __int64 v9; // rcx
  char TxfDataAttribute; // bl
  _OWORD *v11; // rdi
  int v12; // eax
  int v13; // ebx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // r15
  _QWORD *v20; // r13
  int v21; // eax
  __int64 v22; // rax
  _QWORD *v23; // rcx
  void *v24; // rcx
  int v25; // [rsp+20h] [rbp-F8h]
  char v26; // [rsp+70h] [rbp-A8h]
  __int64 v27; // [rsp+78h] [rbp-A0h] BYREF
  _QWORD *v28; // [rsp+80h] [rbp-98h]
  _OWORD *v29; // [rsp+88h] [rbp-90h]
  _QWORD *v30; // [rsp+90h] [rbp-88h]
  __int128 v31; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v33; // [rsp+B8h] [rbp-60h]
  __int64 v34; // [rsp+128h] [rbp+10h] BYREF
  __int64 v35; // [rsp+130h] [rbp+18h] BYREF
  __int64 v36; // [rsp+138h] [rbp+20h]

  v36 = a4;
  v7 = 0;
  v35 = 0;
  v34 = 0;
  v27 = 0;
  v31 = 0;
  v33 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x68u )
    TxfRaiseBoundsCheckFailure();
  v8 = *(_QWORD **)(a2 + 208);
  v30 = v8;
  ExAcquireFastMutex((PFAST_MUTEX)(v8[3] + 472LL));
  v28 = (_QWORD *)(a3 + 80);
  v9 = *(_QWORD *)(a3 + 80);
  if ( v8[86] < v9 )
    v8[86] = v9;
  ExReleaseFastMutex((PFAST_MUTEX)(v8[3] + 472LL));
  NtfsAcquireSharedFcb(a1, *(_QWORD *)(v8[10] + 184LL), v8[10], 0);
  TxfDataAttribute = TxfReadTxfDataAttribute(a1, *(_QWORD *)(v8[10] + 184LL), v32);
  NtfsReleaseFcbEx(a1, *(_QWORD *)(v8[10] + 184LL), 0);
  if ( !TxfDataAttribute )
  {
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 18089, "Status", -1073741566);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3229354);
    ExRaiseStatus(-1073741566);
  }
  v26 = 0;
  v11 = ExAllocateFromLookasideListEx(&TxfDeletedLinkLookasideList);
  v29 = v11;
  *v11 = 0;
  v11[1] = 0;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)&v31 + 1) = 0;
  *(_QWORD *)&v31 = *(_QWORD *)(a3 + 80);
  if ( (int)TxfOpenFileCheckId(
              a1,
              (PRTL_AVL_TABLE *)a2,
              a3,
              (unsigned __int64 *)&v31,
              0,
              2,
              *(_BYTE *)(a3 + 74) & 8,
              0,
              &v27,
              &v34) >= 0 )
  {
    v20 = v28;
  }
  else
  {
    if ( (__int64)v33 >= *(_QWORD *)(a3 + 80) )
      goto LABEL_48;
    v12 = TxfOpenFileCheckId(
            a1,
            (PRTL_AVL_TABLE *)a2,
            a3,
            (unsigned __int64 *)(a3 + 88),
            0,
            2,
            *(_BYTE *)(a3 + 74) & 8,
            0,
            &v27,
            &v34);
    v13 = v12;
    if ( v12 == -1072103368 )
      goto LABEL_48;
    if ( v12 < 0 )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 18181, "Status", v12);
      if ( v13 == -1073741801
        || (v14 = (unsigned int)(v13 + 1073741697), (unsigned int)v14 <= 0x22)
        && (v15 = 0x408000001LL, _bittest64(&v15, v14)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v13 == -1072037845
             || v13 == -1073741202
             || v13 == -1073741435
             || v13 == -1073741496
             || (v16 = (unsigned int)(v13 + 1073741667), (unsigned int)v16 <= 0x23)
             && (v17 = 0x800000041LL, _bittest64(&v17, v16))
             || (unsigned int)(v13 + 1073741811) <= 0x15 && (v18 = 2097219, _bittest(&v18, v13 + 1073741811))
             || v13 == -2147483626
             || v13 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3229446);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3229447);
      ExRaiseStatus(-1073741566);
    }
    v19 = *(_QWORD *)(*(_QWORD *)(v34 + 24) + 184LL);
    NtfsAcquireExclusiveVcb(a1, v8[2], 0);
    v26 = 1;
    if ( (*(_DWORD *)(v8[2] + 4LL) & 1) == 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 3229465);
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3229465);
    }
    NtfsAcquireExclusiveFcb(a1, v19, 0, 0);
    NtfsAcquireExclusiveScbEx(a1, v8[10], 0);
    v34 = 0;
    v20 = v28;
    TxfCreateBackupFileInternal(a1, (__int64)&v34, (__int64)&v35);
    if ( !v36 || (v21 = 1, (*(_DWORD *)(v19 + 4) & 0x100000) != 0) )
      v21 = 0;
    TxfUpdateTxfDataAttributeMembers(a1, v19, v25, 0, v21, v36, 0, 0, 0, 0, 0);
    NtfsCheckpointCurrentTransaction(a1);
    v7 = v35;
  }
  *((_QWORD *)v11 + 3) = *v20;
  if ( v7 )
  {
    v22 = *(_QWORD *)(v7 + 328);
    if ( v22 )
    {
      *((_QWORD *)v11 + 4) = v22;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v22 + 40) + 16LL) + 6176LL));
      ++*(_WORD *)(*((_QWORD *)v11 + 4) + 16LL);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 4) + 40LL) + 16LL) + 6176LL));
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(a2 + 24) + 80LL), 1u);
  v23 = *(_QWORD **)(a2 + 184);
  if ( *v23 != a2 + 176 )
    __fastfail(3u);
  *(_QWORD *)v11 = a2 + 176;
  *((_QWORD *)v11 + 1) = v23;
  *v23 = v11;
  *(_QWORD *)(a2 + 184) = v11;
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 24) + 80LL));
  v11 = 0;
  v29 = 0;
LABEL_48:
  if ( v26 )
    NtfsReleaseVcb(a1, v8[2]);
  if ( v11 )
  {
    v24 = (void *)*((_QWORD *)v11 + 4);
    if ( v24 )
      TxfDereferenceTxfFcb(v24);
    ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v11);
  }
}

```

## disassembly

```asm
0x14010802c  mov     rax, rsp
0x14010802f  mov     [rax+20h], r9
0x140108033  mov     [rax+8], rcx
0x140108037  push    rbx
0x140108038  push    rsi
0x140108039  push    rdi
0x14010803a  push    r12
0x14010803c  push    r13
0x14010803e  push    r14
0x140108040  push    r15
0x140108042  sub     rsp, 0E0h
0x140108049  mov     r13, r8
0x14010804c  mov     r12, rdx
0x14010804f  mov     rsi, rcx
0x140108052  xor     edi, edi
0x140108054  mov     r15d, edi
0x140108057  mov     [rax+18h], rdi
0x14010805b  mov     [rax+10h], rdi
0x14010805f  mov     [rsp+118h+var_A0], rdi
0x140108064  xorps   xmm0, xmm0
0x140108067  movups  xmmword ptr [rax-80h], xmm0
0x14010806b  xorps   xmm1, xmm1
0x14010806e  movups  xmmword ptr [rax-60h], xmm1
0x140108072  cmp     dword ptr [r8+40h], 68h ; 'h'
0x140108077  jnb     short loc_14010807F
0x140108079  call    TxfRaiseBoundsCheckFailure
0x14010807f  mov     r14, [rdx+0D0h]
0x140108086  mov     [rsp+118h+var_88], r14
0x14010808e  mov     rcx, [r14+18h]
0x140108092  mov     ebx, 1D8h
0x140108097  add     rcx, rbx; FastMutex
0x14010809a  call    cs:__imp_ExAcquireFastMutex
0x1401080a1  nop     dword ptr [rax+rax+00h]
0x1401080a6  lea     rax, [r13+50h]
0x1401080aa  mov     [rsp+118h+var_98], rax
0x1401080b2  mov     rcx, [rax]
0x1401080b5  cmp     [r14+2B0h], rcx
0x1401080bc  jge     short loc_1401080C5
0x1401080be  mov     [r14+2B0h], rcx
0x1401080c5  mov     rcx, [r14+18h]
0x1401080c9  add     rcx, rbx; FastMutex
0x1401080cc  call    cs:__imp_ExReleaseFastMutex
0x1401080d3  nop     dword ptr [rax+rax+00h]
0x1401080d8  mov     rdx, [r14+50h]
0x1401080dc  xor     r9d, r9d
0x1401080df  mov     r8, rdx
0x1401080e2  mov     rdx, [rdx+0B8h]
0x1401080e9  mov     rcx, rsi
0x1401080ec  call    NtfsAcquireSharedFcb
0x1401080f1  mov     rdx, [r14+50h]
0x1401080f5  lea     r8, [rsp+118h+var_70]
0x1401080fd  mov     rdx, [rdx+0B8h]
0x140108104  mov     rcx, rsi
0x140108107  call    TxfReadTxfDataAttribute
0x14010810c  mov     bl, al
0x14010810e  mov     rdx, [r14+50h]
0x140108112  xor     r8d, r8d
0x140108115  mov     rdx, [rdx+0B8h]
0x14010811c  mov     rcx, rsi
0x14010811f  call    NtfsReleaseFcbEx
0x140108124  test    bl, bl
0x140108126  jnz     short loc_14010818F
0x140108128  mov     ebx, 0C0000102h
0x14010812d  mov     [rsp+118h+var_E8], ebx
0x140108131  lea     rax, aStatus; "Status"
0x140108138  mov     [rsp+118h+var_F0], rax
0x14010813d  mov     dword ptr [rsp+118h+var_F8], 46A9h
0x140108145  lea     r9, aTxftransC; "txftrans.c"
0x14010814c  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x140108153  xor     edx, edx; Level
0x140108155  mov     ecx, 82h; ComponentId
0x14010815a  call    cs:__imp_DbgPrintEx
0x140108161  nop     dword ptr [rax+rax+00h]
0x140108166  mov     al, cs:NtfsStatusDebugFlags
0x14010816c  test    al, al
0x14010816e  jz      short loc_140108180
0x140108170  mov     r8d, 3146AAh
0x140108176  mov     edx, ebx
0x140108178  mov     rcx, rsi
0x14010817b  call    NtfsStatusTraceAndDebugInternal
0x140108180  mov     ecx, ebx; Status
0x140108182  call    cs:__imp_ExRaiseStatus
0x14010818f  mov     [rsp+118h+var_A8], dil
0x140108194  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x14010819b  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401081a2  nop     dword ptr [rax+rax+00h]
0x1401081a7  mov     rdi, rax
0x1401081aa  mov     [rsp+118h+var_90], rax
0x1401081b2  xorps   xmm0, xmm0
0x1401081b5  xor     eax, eax
0x1401081b7  movups  xmmword ptr [rdi], xmm0
0x1401081ba  movups  xmmword ptr [rdi+10h], xmm0
0x1401081be  mov     [rdi+20h], rax
0x1401081c2  xor     edx, edx
0x1401081c4  mov     [rsp+118h+var_78], rdx
0x1401081cc  mov     rax, [r13+50h]
0x1401081d0  mov     [rsp+118h+var_80], rax
0x1401081d8  mov     al, [r13+4Ah]
0x1401081dc  and     al, 8
0x1401081de  lea     rcx, [rsp+118h+arg_8]
0x1401081e6  mov     [rsp+118h+var_D0], rcx
0x1401081eb  lea     rcx, [rsp+118h+var_A0]
0x1401081f0  mov     [rsp+118h+var_D8], rcx
0x1401081f5  mov     [rsp+118h+var_E0], rdx
0x1401081fa  mov     byte ptr [rsp+118h+var_E8], al
0x1401081fe  mov     dword ptr [rsp+118h+var_F0], 2
0x140108206  mov     [rsp+118h+var_F8], rdx
0x14010820b  lea     r9, [rsp+118h+var_80]
0x140108213  mov     r8, r13
0x140108216  mov     rdx, r12
0x140108219  mov     rcx, rsi
0x14010821c  call    TxfOpenFileCheckId
0x140108221  nop
0x140108222  test    eax, eax
0x140108224  jns     loc_1401084F2
0x14010822a  mov     rax, qword ptr [rsp+118h+var_60]
0x140108232  cmp     rax, [r13+50h]
0x140108236  jge     loc_1401085B8
0x14010823c  mov     al, [r13+4Ah]
0x140108240  and     al, 8
0x140108242  lea     r9, [r13+58h]
0x140108246  lea     rcx, [rsp+118h+arg_8]
0x14010824e  mov     [rsp+118h+var_D0], rcx
0x140108253  lea     rcx, [rsp+118h+var_A0]
0x140108258  mov     [rsp+118h+var_D8], rcx
0x14010825d  mov     [rsp+118h+var_E0], 0
0x140108266  mov     byte ptr [rsp+118h+var_E8], al
0x14010826a  mov     dword ptr [rsp+118h+var_F0], 2
0x140108272  mov     [rsp+118h+var_F8], 0
0x14010827b  mov     r8, r13
0x14010827e  mov     rdx, r12
0x140108281  mov     rcx, rsi
0x140108284  call    TxfOpenFileCheckId
0x140108289  mov     ebx, eax
0x14010828b  cmp     eax, 0C0190038h
0x140108290  jz      loc_1401085B8
0x140108296  test    eax, eax
0x140108298  jns     loc_1401083C4
0x14010829e  mov     [rsp+118h+var_E8], eax
0x1401082a2  lea     rax, aStatus; "Status"
0x1401082a9  mov     [rsp+118h+var_F0], rax
0x1401082ae  mov     dword ptr [rsp+118h+var_F8], 4705h
0x1401082b6  lea     r9, aTxftransC; "txftrans.c"
0x1401082bd  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x1401082c4  xor     edx, edx; Level
0x1401082c6  mov     ecx, 82h; ComponentId
0x1401082cb  call    cs:__imp_DbgPrintEx
0x1401082d2  nop     dword ptr [rax+rax+00h]
0x1401082d7  cmp     ebx, 0C0000017h
0x1401082dd  jz      loc_14010836F
0x1401082e3  lea     eax, [rbx+3FFFFF81h]
0x1401082e9  cmp     eax, 22h ; '"'
0x1401082ec  ja      short loc_1401082FE
0x1401082ee  mov     rcx, 408000001h
0x1401082f8  bt      rcx, rax
0x1401082fc  jb      short loc_14010836F
0x1401082fe  cmp     ebx, 0C01A002Bh
0x140108304  jz      short loc_14010835E
0x140108306  cmp     ebx, 0C000026Eh
0x14010830c  jz      short loc_14010835E
0x14010830e  cmp     ebx, 0C0000185h
0x140108314  jz      short loc_14010835E
0x140108316  cmp     ebx, 0C0000148h
0x14010831c  jz      short loc_14010835E
0x14010831e  lea     eax, [rbx+3FFFFF63h]
0x140108324  cmp     eax, 23h ; '#'
0x140108327  ja      short loc_140108339
0x140108329  mov     rcx, 800000041h
0x140108333  bt      rcx, rax
0x140108337  jb      short loc_14010835E
0x140108339  lea     eax, [rbx+3FFFFFF3h]
0x14010833f  cmp     eax, 15h
0x140108342  ja      short loc_14010834E
0x140108344  mov     ecx, 200043h
0x140108349  bt      ecx, eax
0x14010834c  jb      short loc_14010835E
0x14010834e  cmp     ebx, 80000016h
0x140108354  jz      short loc_14010835E
0x140108356  cmp     ebx, 0C01A002Fh
0x14010835c  jnz     short loc_14010837E
0x14010835e  mov     rax, cs:TxfData
0x140108365  mov     ebx, 1
0x14010836a  add     [rax+10h], ebx
0x14010836d  jmp     short loc_14010837E
0x14010836f  mov     rax, cs:TxfData
0x140108376  mov     ebx, 1
0x14010837b  add     [rax+0Ch], ebx
0x14010837e  mov     al, cs:NtfsStatusDebugFlags
0x140108384  mov     ebx, 0C0000102h
0x140108389  test    al, al
0x14010838b  jz      short loc_14010839C
0x14010838d  mov     r8d, 314706h
0x140108393  mov     edx, ebx
0x140108395  xor     ecx, ecx
0x140108397  call    NtfsStatusTraceAndDebugInternal
0x14010839c  mov     al, cs:NtfsStatusDebugFlags
0x1401083a2  test    al, al
0x1401083a4  jz      short loc_1401083B6
0x1401083a6  mov     r8d, 314707h
0x1401083ac  mov     edx, ebx
0x1401083ae  mov     rcx, rsi
0x1401083b1  call    NtfsStatusTraceAndDebugInternal
0x1401083b6  mov     ecx, ebx; Status
0x1401083b8  call    cs:__imp_ExRaiseStatus
0x1401083c4  mov     rax, [rsp+118h+arg_8]
0x1401083cc  mov     rcx, [rax+18h]
0x1401083d0  mov     r15, [rcx+0B8h]
0x1401083d7  xor     r8d, r8d
0x1401083da  mov     rdx, [r14+10h]
0x1401083de  mov     rcx, rsi
0x1401083e1  call    NtfsAcquireExclusiveVcb
0x1401083e6  mov     ebx, 1
0x1401083eb  mov     [rsp+118h+var_A8], bl
0x1401083ef  mov     rax, [r14+10h]
0x1401083f3  mov     ecx, [rax+4]
0x1401083f6  test    bl, cl
0x1401083f8  jnz     short loc_140108433
0x1401083fa  mov     al, cs:NtfsStatusDebugFlags
0x140108400  test    al, al
0x140108402  jz      short loc_140108417
0x140108404  mov     edx, 0C000026Eh
0x140108409  mov     r8d, 314719h
0x14010840f  mov     rcx, rsi
0x140108412  call    NtfsStatusTraceAndDebugInternal
0x140108417  mov     [rsp+118h+var_F8], 314719h
0x140108420  xor     r9d, r9d
0x140108423  xor     r8d, r8d
0x140108426  mov     edx, 0C000026Eh
0x14010842b  mov     rcx, rsi
0x14010842e  call    NtfsRaiseStatusInternal
0x140108433  xor     r9d, r9d
0x140108436  xor     r8d, r8d
0x140108439  mov     rdx, r15
0x14010843c  mov     rcx, rsi
0x14010843f  call    NtfsAcquireExclusiveFcb
0x140108444  xor     r8d, r8d
0x140108447  mov     rdx, [r14+50h]
0x14010844b  mov     rcx, rsi
0x14010844e  call    NtfsAcquireExclusiveScbEx
0x140108453  mov     [rsp+118h+arg_8], 0
0x14010845f  lea     rax, [rsp+118h+arg_10]
0x140108467  mov     [rsp+118h+var_F0], rax; __int64
0x14010846c  lea     rax, [rsp+118h+arg_8]
0x140108474  mov     [rsp+118h+var_F8], rax; int
0x140108479  mov     r9, r15
0x14010847c  mov     r13, [rsp+118h+var_98]
0x140108484  mov     r8, r13
0x140108487  mov     rdx, r14
0x14010848a  mov     rcx, rsi; int
0x14010848d  call    TxfCreateBackupFileInternal
0x140108492  mov     rcx, [rsp+118h+arg_18]
0x14010849a  xor     edx, edx
0x14010849c  test    rcx, rcx
0x14010849f  jz      short loc_1401084AD
0x1401084a1  test    dword ptr [r15+4], 100000h
0x1401084a9  mov     eax, ebx
0x1401084ab  jz      short loc_1401084AF
0x1401084ad  mov     eax, edx
0x1401084af  mov     [rsp+118h+var_B8], rdx; __int64
0x1401084b4  mov     [rsp+118h+var_C0], rdx; __int64
0x1401084b9  mov     [rsp+118h+var_C8], rdx; __int64
0x1401084be  mov     [rsp+118h+var_D0], rdx; __int64
0x1401084c3  mov     [rsp+118h+var_D8], rdx; __int64
0x1401084c8  mov     [rsp+118h+var_E0], rcx; __int64
0x1401084cd  mov     [rsp+118h+var_E8], eax; int
0x1401084d1  mov     dword ptr [rsp+118h+var_F0], edx; int
0x1401084d5  mov     rdx, r15; int
0x1401084d8  mov     rcx, rsi; int
0x1401084db  call    TxfUpdateTxfDataAttributeMembers
0x1401084e0  mov     rcx, rsi
0x1401084e3  call    NtfsCheckpointCurrentTransaction
0x1401084e8  mov     r15, [rsp+118h+arg_10]
0x1401084f0  jmp     short loc_1401084FF
0x1401084f2  mov     ebx, 1
0x1401084f7  mov     r13, [rsp+118h+var_98]
0x1401084ff  mov     rax, [r13+0]
0x140108503  mov     [rdi+18h], rax
0x140108507  test    r15, r15
0x14010850a  jz      short loc_14010855C
0x14010850c  mov     rax, [r15+148h]
0x140108513  test    rax, rax
0x140108516  jz      short loc_14010855C
0x140108518  mov     [rdi+20h], rax
0x14010851c  mov     rax, [rax+28h]
0x140108520  mov     rcx, [rax+10h]
0x140108524  mov     r15d, 1820h
0x14010852a  add     rcx, r15; FastMutex
0x14010852d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140108534  nop     dword ptr [rax+rax+00h]
0x140108539  mov     rax, [rdi+20h]
0x14010853d  add     [rax+10h], bx
0x140108541  mov     rax, [rdi+20h]
0x140108545  mov     rcx, [rax+28h]
0x140108549  mov     rcx, [rcx+10h]
0x14010854d  add     rcx, r15; FastMutex
0x140108550  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140108557  nop     dword ptr [rax+rax+00h]
0x14010855c  mov     rcx, [r12+18h]
0x140108561  add     rcx, 50h ; 'P'; Resource
0x140108565  mov     dl, bl; Wait
  ... truncated ...
```
