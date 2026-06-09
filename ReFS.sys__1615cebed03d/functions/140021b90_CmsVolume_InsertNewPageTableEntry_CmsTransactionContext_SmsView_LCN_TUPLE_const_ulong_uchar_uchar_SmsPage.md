# CmsVolume::InsertNewPageTableEntry(CmsTransactionContext *,SmsView *,_LCN_TUPLE const *,ulong,uchar,uchar,SmsPage * *)

- ea: `0x140021b90`
- end: `0x1400221eb`
- name: `?InsertNewPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEBT_LCN_TUPLE@@KEEPEAPEAUSmsPage@@@Z`
- size: `1627`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct SmsView *, const union _LCN_TUPLE *, unsigned int, unsigned __int8, unsigned __int8, struct SmsPage **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140066ed0`
- `0x14006ec00`
- `0x14009d520`

## callees

- `0x140021720`
- `0x140021b90`
- `0x140022200`
- `0x1400227b0`
- `0x1400227f0`
- `0x140022950`
- `0x14003b5d0`
- `0x140079480`
- `0x14008a090`
- `0x1400b5758`
- `0x1400ce3f4`
- `0x1400ceda0`
- `0x14011c920`
- `0x14011c938`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140022084`
- `ntoskrnl!KeSetEvent` at `0x140022084`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140022139`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140022139`
- `ntoskrnl!ExAllocatePool2` at `0x140021bf6`
- `ntoskrnl!ExAllocatePool2` at `0x140021bf6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140021bb9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140021bb9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa46a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa46a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140022156`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140022156`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400220a1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400220a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140022036`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140022036`

## string_xrefs

- `0x140021c0a`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsVolume::InsertNewPageTableEntry(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        struct SmsView *a3,
        const union _LCN_TUPLE *a4,
        unsigned int a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        struct SmsPage **a8)
{
  __int64 v11; // rbp
  struct _SmsLookaside **v12; // rbx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 Pool2; // rax
  int v16; // ecx
  __int64 v17; // rsi
  __int64 v18; // rbx
  unsigned __int64 *v19; // r15
  __int64 v20; // rbx
  __int16 v21; // ax
  unsigned int v22; // eax
  __int128 v23; // xmm1
  __int64 v24; // rax
  unsigned __int64 v25; // r15
  __int64 v26; // rdi
  __int64 v27; // r14
  struct SmsHashEntry *v28; // rax
  CmsHashTable *v29; // rcx
  SmsHashEntry *v30; // rbp
  bool v31; // r12
  int v32; // edi
  CmsHashTable *v33; // rcx
  unsigned __int8 v34; // r8
  __int64 result; // rax
  _SmsPerfStats *v36; // rcx
  unsigned int v37; // r8d
  unsigned __int64 v38; // r10
  __int64 v39; // r9
  __int64 v40; // r8
  bool v41; // zf
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 *v44; // rsi
  __int64 **v45; // rcx
  struct _KEVENT *v46; // rcx
  int v47; // edx
  _SmsPerfStats *v48; // rcx
  unsigned int v49; // r9d
  struct _NPAGED_LOOKASIDE_LIST *v50; // rcx
  __int64 v51; // rdx
  struct _SmsHashLocation *v52; // [rsp+38h] [rbp-90h]
  struct _SmsHashLocation *v53; // [rsp+38h] [rbp-90h]
  struct SmsHashEntry **v54; // [rsp+40h] [rbp-88h]
  struct SmsHashEntry **v55; // [rsp+40h] [rbp-88h]
  unsigned __int64 v56[2]; // [rsp+50h] [rbp-78h] BYREF
  __int64 v57; // [rsp+60h] [rbp-68h]
  _QWORD v58[2]; // [rsp+70h] [rbp-58h] BYREF
  int v59; // [rsp+80h] [rbp-48h]
  int v60; // [rsp+84h] [rbp-44h]
  __int64 v61; // [rsp+88h] [rbp-40h]
  __int64 v62; // [rsp+90h] [rbp-38h]
  SmsHashEntry *v63; // [rsp+D0h] [rbp+8h] BYREF

  v63 = this;
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 32LL) + 40LL);
  v12 = &LookasideLists[24 * (KeGetCurrentProcessorNumberEx(0) % NumProcessors)];
  if ( *(_DWORD *)v12 < 0x2D0u )
  {
    v12 = 0;
    v14 = 736;
    goto LABEL_3;
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v50 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 8);
    if ( *((_BYTE *)v12 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v50);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v50);
LABEL_31:
    if ( Pool2 )
      goto LABEL_32;
    goto LABEL_9;
  }
  if ( (int)v12[11] > (int)HIDWORD(v12[11]) )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)v12 + 22);
    if ( v16 >= *((_DWORD *)v12 + 23) && v16 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)v12 + 4);
      goto LABEL_31;
    }
    _InterlockedIncrement((volatile signed __int32 *)v12 + 22);
  }
LABEL_9:
  v14 = *((unsigned int *)v12 + 1);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v14, 1766871885, v13);
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
LABEL_32:
  if ( !Pool2 )
    goto LABEL_33;
  v17 = Pool2 + 16;
  *(_QWORD *)Pool2 = v12;
  if ( Pool2 == -16 )
    goto LABEL_33;
  *(_DWORD *)v17 = 720;
  *(_WORD *)(Pool2 + 26) = 16;
  *(_WORD *)(Pool2 + 20) = 16;
  *(_DWORD *)(Pool2 + 22) = 8;
  *(_DWORD *)(Pool2 + 28) = 704;
  memset((void *)(Pool2 + 32), 0, 0x2C0u);
  v18 = *(unsigned __int16 *)(v17 + 10);
  v19 = (unsigned __int64 *)(v17 + *(unsigned __int16 *)(v17 + 4));
  LODWORD(v56[0]) = *(unsigned __int16 *)(v17 + 6);
  v20 = v17 + v18;
  v21 = *(_WORD *)(v17 + 8) & 3;
  v62 = v17;
  v58[1] = v19;
  WORD2(v56[0]) = v21 | 4;
  v58[0] = v56[0];
  v59 = *(_DWORD *)(v17 + 12);
  v60 = HIDWORD(v56[0]);
  v61 = v20;
  if ( !v20 )
  {
LABEL_33:
    v32 = -1073741670;
LABEL_34:
    v20 = 0;
    goto LABEL_35;
  }
  SmsPage::InitializePageInternals(v20, a2, *(_QWORD *)a3, 0, a7 == 0);
  v41 = a6 == 0;
  *(_BYTE *)(v20 + 392) = *((_BYTE *)a3 + 24);
  *(_QWORD *)(v20 + 328) = *((_QWORD *)a3 + 2);
  *(_OWORD *)(v20 + 394) = 0;
  *(_OWORD *)(v20 + 410) = 0;
  *(_OWORD *)(v20 + 426) = 0;
  *(_OWORD *)(v20 + 442) = 0;
  *(_OWORD *)(v20 + 458) = 0;
  *(_OWORD *)(v20 + 474) = 0;
  *(_OWORD *)(v20 + 490) = 0;
  *(_OWORD *)(v20 + 506) = 0;
  if ( !v41 )
  {
    v38 = *(_QWORD *)(v20 + 336);
    v39 = *(_QWORD *)(v20 + 96);
    if ( v38 < 2 )
      goto LABEL_48;
    if ( *(_QWORD *)a3 == v39 )
    {
      v41 = *((_QWORD *)a3 + 2) == v38;
    }
    else
    {
      v40 = *(_QWORD *)(v39 + 160);
      if ( *((_QWORD *)a3 + 2) + v40 - *(_QWORD *)(*(_QWORD *)a3 + 160LL) )
        v40 = *((_QWORD *)a3 + 2) + *(_QWORD *)(v39 + 160) - *(_QWORD *)(*(_QWORD *)a3 + 160LL);
      v41 = v38 == v40;
    }
    if ( !v41 )
    {
LABEL_48:
      *(_QWORD *)(v20 + 336) = *((_QWORD *)a3 + 2);
      if ( ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v39 + 24) + 72LL) + 3396LL) & 2) == 0
         || CmsBPlusTable::IsVirtualTable((CmsBPlusTable *)v39))
        && !*(_DWORD *)(v39 + 120)
        && (*(_DWORD *)(*((_QWORD *)a2 + 1) + 3396LL) & 0x20000000) == 0 )
      {
        v42 = v39;
        if ( *(_QWORD *)(v39 + 64) == v39 )
        {
LABEL_50:
          if ( (*(_BYTE *)(v42 + 15) & 8) == 0 )
            CmsBPlusTable::EnqueueTreeUpdate(v39, a2, 1);
        }
        else
        {
          while ( (*(_BYTE *)(v42 + 15) & 8) == 0 )
          {
            v42 = *(_QWORD *)(v42 + 64);
            if ( *(_QWORD *)(v42 + 64) == v42 )
              goto LABEL_50;
          }
        }
      }
    }
    _InterlockedOr((volatile signed __int32 *)(v20 + 552), 0x100098u);
  }
  *v19 = *(_QWORD *)a4;
  v22 = a5;
  *(_OWORD *)v20 = *(_OWORD *)a4;
  v23 = *((_OWORD *)a4 + 1);
  *(_DWORD *)(v20 + 376) = v22;
  *(_OWORD *)(v20 + 16) = v23;
  v24 = *((_QWORD *)a2 + 1);
  *(_OWORD *)v56 = 0;
  *(_DWORD *)(v20 + 320) = *(_DWORD *)(v24 + 3332);
  v25 = *v19;
  v57 = 0;
  if ( !v25 )
  {
    v32 = -1073741811;
LABEL_28:
    if ( *(char *)(*(_QWORD *)(v20 + 96) + 14LL) >= 0 )
      --*((_DWORD *)a2 + 49);
    SmsPage::ReleasePageLockInternal((SmsPage *)v20, a2);
    SmsPage::TeardownPageInternals((SmsPage *)v20);
    CmsHashTable::CleanupPreAllocatedRow(v33, (struct _SmsPreAllocatedRow *)v58, v34);
    goto LABEL_34;
  }
  v26 = *(_QWORD *)(v11 + 32);
  v27 = v11 + 16;
  v63 = 0;
  v28 = CmsHashTable::FindAndLockEntryInternal(
          (CmsHashTable *)(v11 + 16),
          v25,
          1u,
          0,
          v26 != 0,
          (struct _SmsHashLocation *)v56,
          &v63,
          v52,
          v54);
  if ( !v26 && *(_QWORD *)(v11 + 32) )
  {
    if ( v63 )
      SmsHashEntry::Unlock(v63, v56);
    v28 = CmsHashTable::FindAndLockEntryInternal(
            (CmsHashTable *)(v11 + 16),
            v25,
            1u,
            0,
            1,
            (struct _SmsHashLocation *)v56,
            &v63,
            v53,
            v55);
  }
  v30 = v63;
  if ( !v28 && !v63 )
  {
    v32 = -1073741771;
    goto LABEL_28;
  }
  v31 = 0;
  v32 = 0;
  if ( v28 )
  {
    *(_QWORD *)v28 = v25;
    *((_QWORD *)v28 + 1) = v17;
    ++*(_DWORD *)(*((_QWORD *)v30 + 1) + 4LL);
    goto LABEL_21;
  }
  if ( !v56[0] )
  {
    *((_QWORD *)v63 + 1) = v17;
    v56[0] = v25;
LABEL_21:
    _InterlockedIncrement((volatile signed __int32 *)(16LL * LODWORD(v56[1]) + v27 + 12));
    goto LABEL_22;
  }
  v32 = CmsHashTable::CreateOrExpandOverflowBucket(v29, (struct _SmsHashLocation *)v56, v63);
  if ( v32 >= 0 )
  {
    v51 = *((_QWORD *)v30 + 1);
    *(_QWORD *)(*(_QWORD *)(v51 + 8) + 16LL * *(unsigned int *)(v51 + 4)) = v25;
    *(_QWORD *)(*(_QWORD *)(v51 + 8) + 16LL * (unsigned int)(*(_DWORD *)(v51 + 4))++ + 8) = v17;
    goto LABEL_21;
  }
LABEL_22:
  if ( v32 >= 0 )
  {
    v36 = (_SmsPerfStats *)*(unsigned int *)(v27 + 12);
    v37 = (_DWORD)v36 + *(_DWORD *)(v27 + 28);
    if ( (++*(_DWORD *)(v27 + 36) & 0xF) == 0 )
    {
      if ( !*(_QWORD *)(v27 + 16) )
        v31 = *(_DWORD *)(v27 + 8) < *(_DWORD *)(v27 + 12) >> 2;
      _SmsPerfStats::UpdateIfLargerHashMostEntries(v36, v37);
      if ( v49 < v37 )
        _SmsPerfStats::UpdateIfLargerHashMostSpillover(v48, v47 - v49);
    }
    if ( v37 > *(_DWORD *)(v27 + 32) )
      *(_DWORD *)(v27 + 32) = v37;
  }
  if ( v30 && _InterlockedExchange64((volatile __int64 *)v30, v56[0]) == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
    v43 = qword_14026C3C8;
    if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
    {
      do
      {
        v44 = *(__int64 **)v43;
        if ( *(SmsHashEntry **)(v43 + 24) == v30 )
        {
          if ( v44[1] != v43 || (v45 = *(__int64 ***)(v43 + 8), *v45 != (__int64 *)v43) )
            __fastfail(3u);
          *v45 = v44;
          v44[1] = (__int64)v45;
          v46 = *(struct _KEVENT **)(v43 + 16);
          *(_QWORD *)v43 = 0;
          KeSetEvent(v46, 0, 0);
        }
        v43 = (__int64)v44;
      }
      while ( v44 != &qword_14026C3C8 );
    }
    ExReleasePushLockEx(&qword_14026C3C0, 0);
  }
  if ( v31 )
    CmsHashTable::AttemptResize((CmsHashTable *)v27, 1u);
  if ( v32 < 0 )
    goto LABEL_28;
LABEL_35:
  result = (unsigned int)v32;
  *a8 = (struct SmsPage *)v20;
  return result;
}

```

## disassembly

```asm
0x140021b90  mov     [rsp+arg_0], rcx
0x140021b95  push    rbx
0x140021b96  push    rbp
0x140021b97  push    rdi
0x140021b98  push    r13
0x140021b9a  push    r14
0x140021b9c  sub     rsp, 0A0h
0x140021ba3  mov     rax, [r8]
0x140021ba6  mov     r14, r9
0x140021ba9  mov     rdi, r8
0x140021bac  mov     r13, rdx
0x140021baf  mov     rcx, [rax+20h]
0x140021bb3  mov     rbp, [rcx+28h]
0x140021bb7  xor     ecx, ecx; ProcNumber
0x140021bb9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140021bc0  nop     dword ptr [rax+rax+00h]
0x140021bc5  xor     edx, edx
0x140021bc7  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140021bcd  lea     rbx, [rdx+rdx*2]
0x140021bd1  shl     rbx, 6
0x140021bd5  add     rbx, cs:?LookasideLists@@3PAPEAU_SmsLookaside@@A; _SmsLookaside * near * LookasideLists
0x140021bdc  cmp     dword ptr [rbx], 2D0h
0x140021be2  jnb     short loc_140021C17
0x140021be4  xor     ebx, ebx
0x140021be6  mov     edx, 2E0h
0x140021beb  mov     ecx, 42h ; 'B'
0x140021bf0  mov     r8d, 6950534Dh
0x140021bf6  call    cs:__imp_ExAllocatePool2
0x140021bfd  nop     dword ptr [rax+rax+00h]
0x140021c02  test    al, 0Fh
0x140021c04  jz      loc_140021ED1
0x140021c0a  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140021c11  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140021c17  cmp     byte ptr [rbx+8], 0
0x140021c1b  jnz     loc_14002212B
0x140021c21  mov     rcx, [rbx+58h]
0x140021c25  mov     rax, rcx
0x140021c28  shr     rax, 20h
0x140021c2c  cmp     ecx, eax
0x140021c2e  jle     short loc_140021C4F
0x140021c30  nop
0x140021c31  mov     ecx, 0FFFFFFFFh
0x140021c36  lock xadd [rbx+58h], ecx
0x140021c3b  nop
0x140021c3c  dec     ecx
0x140021c3e  mov     eax, [rbx+5Ch]
0x140021c41  cmp     ecx, eax
0x140021c43  jge     loc_14002214A
0x140021c49  nop
0x140021c4a  lock inc dword ptr [rbx+58h]
0x140021c4e  nop
0x140021c4f  mov     edx, [rbx+4]
0x140021c52  jmp     short loc_140021BEB
0x140021c54  lea     rsi, [rax+10h]
0x140021c58  mov     [rax], rbx
0x140021c5b  test    rsi, rsi
0x140021c5e  jz      loc_140021EF2
0x140021c64  mov     eax, 10h
0x140021c69  mov     dword ptr [rsi], 2D0h
0x140021c6f  lea     rcx, [rsi+10h]; void *
0x140021c73  mov     [rsi+0Ah], ax
0x140021c77  xor     edx, edx; Val
0x140021c79  mov     [rsi+4], ax
0x140021c7d  mov     r8d, 2C0h; Size
0x140021c83  mov     dword ptr [rsi+6], 8
0x140021c8a  mov     dword ptr [rsi+0Ch], 2C0h
0x140021c91  call    memset
0x140021c96  movzx   eax, word ptr [rsi+6]
0x140021c9a  movzx   r15d, word ptr [rsi+4]
0x140021c9f  movzx   ebx, word ptr [rsi+0Ah]
0x140021ca3  add     r15, rsi
0x140021ca6  mov     dword ptr [rsp+0C8h+var_78], eax
0x140021caa  add     rbx, rsi
0x140021cad  movzx   eax, word ptr [rsi+8]
0x140021cb1  and     ax, 3
0x140021cb5  mov     [rsp+0C8h+var_38], rsi
0x140021cbd  or      ax, 4
0x140021cc1  mov     [rsp+0C8h+var_50], r15
0x140021cc6  mov     word ptr [rsp+0C8h+var_78+4], ax
0x140021ccb  movzx   eax, word ptr [rsp+0C8h+var_78+6]
0x140021cd0  mov     word ptr [rsp+0C8h+var_78+6], ax
0x140021cd5  mov     rax, [rsp+0C8h+var_78]
0x140021cda  mov     [rsp+0C8h+var_58], rax
0x140021cdf  mov     eax, [rsi+0Ch]
0x140021ce2  mov     [rsp+0C8h+var_48], eax
0x140021ce9  mov     eax, dword ptr [rsp+0C8h+var_78+4]
0x140021ced  mov     [rsp+0C8h+var_44], eax
0x140021cf4  mov     [rsp+0C8h+var_40], rbx
0x140021cfc  test    rbx, rbx
0x140021cff  jz      loc_140021EF2
0x140021d05  mov     r8, [rdi]
0x140021d08  xor     eax, eax
0x140021d0a  cmp     [rsp+0C8h+arg_30], al
0x140021d11  mov     rdx, r13
0x140021d14  mov     rcx, rbx
0x140021d17  setz    al
0x140021d1a  xor     r9d, r9d
0x140021d1d  mov     dword ptr [rsp+0C8h+var_A8], eax
0x140021d21  call    ?InitializePageInternals@SmsPage@@QEAAXPEAVCmsTransactionContext@@AEAVCmsBPlusTable@@W4_EMS_PAGE_STATE@@W4InitialLockState@SmsPageLatch@@@Z; SmsPage::InitializePageInternals(CmsTransactionContext *,CmsBPlusTable &,_EMS_PAGE_STATE,SmsPageLatch::InitialLockState)
0x140021d26  cmp     [rsp+0C8h+arg_28], 0
0x140021d2e  xorps   xmm0, xmm0
0x140021d31  movzx   eax, byte ptr [rdi+18h]
0x140021d35  mov     [rbx+188h], al
0x140021d3b  mov     rax, [rdi+10h]
0x140021d3f  mov     [rbx+148h], rax
0x140021d46  movups  xmmword ptr [rbx+18Ah], xmm0
0x140021d4d  movups  xmmword ptr [rbx+19Ah], xmm0
0x140021d54  movups  xmmword ptr [rbx+1AAh], xmm0
0x140021d5b  movups  xmmword ptr [rbx+1BAh], xmm0
0x140021d62  movups  xmmword ptr [rbx+1CAh], xmm0
0x140021d69  movups  xmmword ptr [rbx+1DAh], xmm0
0x140021d70  movups  xmmword ptr [rbx+1EAh], xmm0
0x140021d77  movups  xmmword ptr [rbx+1FAh], xmm0
0x140021d7e  jnz     loc_140021F78
0x140021d84  mov     rax, [r14]
0x140021d87  mov     [r15], rax
0x140021d8a  movups  xmm0, xmmword ptr [r14]
0x140021d8e  mov     eax, [rsp+0C8h+arg_20]
0x140021d95  movups  xmmword ptr [rbx], xmm0
0x140021d98  movups  xmm1, xmmword ptr [r14+10h]
0x140021d9d  mov     [rbx+178h], eax
0x140021da3  xorps   xmm0, xmm0
0x140021da6  movups  xmmword ptr [rbx+10h], xmm1
0x140021daa  mov     rax, [r13+8]
0x140021dae  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x140021db3  mov     ecx, [rax+0D04h]
0x140021db9  xor     eax, eax
0x140021dbb  mov     [rbx+140h], ecx
0x140021dc1  mov     r15, [r15]
0x140021dc4  mov     [rsp+0C8h+var_68], rax
0x140021dc9  test    r15, r15
0x140021dcc  jz      loc_140022167
0x140021dd2  mov     rdi, [rbp+20h]
0x140021dd6  lea     r14, [rbp+10h]
0x140021dda  lea     rcx, [rsp+0C8h+arg_0]
0x140021de2  mov     [rsp+0C8h+arg_0], rax
0x140021dea  mov     [rsp+0C8h+var_98], rcx; struct SmsHashEntry **
0x140021def  test    rdi, rdi
0x140021df2  lea     rcx, [rsp+0C8h+var_78]
0x140021df7  mov     r8b, 1; unsigned __int8
0x140021dfa  setnz   al
0x140021dfd  mov     [rsp+0C8h+var_A0], rcx; struct _SmsHashLocation *
0x140021e02  xor     r9d, r9d; unsigned __int8
0x140021e05  mov     [rsp+0C8h+var_A8], al; char
0x140021e09  mov     rdx, r15; unsigned __int64
0x140021e0c  mov     rcx, r14; this
0x140021e0f  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x140021e14  test    rdi, rdi
0x140021e17  jnz     short loc_140021E23
0x140021e19  cmp     [r14+10h], rdi
0x140021e1d  jnz     loc_140022171
0x140021e23  mov     rbp, [rsp+0C8h+arg_0]
0x140021e2b  test    rax, rax
0x140021e2e  jnz     short loc_140021E39
0x140021e30  test    rbp, rbp
0x140021e33  jz      loc_140022192
0x140021e39  xor     r12b, r12b
0x140021e3c  xor     edi, edi
0x140021e3e  test    rax, rax
0x140021e41  jnz     loc_140021F2E
0x140021e47  cmp     [rsp+0C8h+var_78], rdi
0x140021e4c  jnz     loc_14002219C
0x140021e52  mov     [rbp+8], rsi
0x140021e56  mov     [rsp+0C8h+var_78], r15
0x140021e5b  mov     eax, dword ptr [rsp+0C8h+var_78+8]
0x140021e5f  nop
0x140021e60  shl     rax, 4
0x140021e64  lock inc dword ptr [rax+r14+0Ch]
0x140021e6a  nop
0x140021e6b  test    edi, edi
0x140021e6d  jns     loc_140021F41
0x140021e73  test    rbp, rbp
0x140021e76  jz      short loc_140021E8B
0x140021e78  mov     rax, [rsp+0C8h+var_78]
0x140021e7d  xchg    rax, [rbp+0]
0x140021e81  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021e85  jz      loc_14002202D
0x140021e8b  test    r12b, r12b
0x140021e8e  jnz     loc_1400221DC
0x140021e94  test    edi, edi
0x140021e96  jns     short loc_140021EF9
0x140021e98  mov     rax, [rbx+60h]
0x140021e9c  cmp     byte ptr [rax+0Eh], 0
0x140021ea0  jl      short loc_140021EA9
0x140021ea2  dec     dword ptr [r13+0C4h]
0x140021ea9  mov     rdx, r13; struct CmsTransactionContext *
0x140021eac  mov     rcx, rbx; this
0x140021eaf  call    ?ReleasePageLockInternal@SmsPage@@QEAAXPEAVCmsTransactionContext@@@Z; SmsPage::ReleasePageLockInternal(CmsTransactionContext *)
0x140021eb4  mov     rcx, rbx; this
0x140021eb7  call    ?TeardownPageInternals@SmsPage@@QEAAXXZ; SmsPage::TeardownPageInternals(void)
0x140021ebc  lea     rdx, [rsp+0C8h+var_58]; struct _SmsPreAllocatedRow *
0x140021ec1  call    ?CleanupPreAllocatedRow@CmsHashTable@@QEAAXPEAU_SmsPreAllocatedRow@@E@Z; CmsHashTable::CleanupPreAllocatedRow(_SmsPreAllocatedRow *,uchar)
0x140021ec6  jmp     short loc_140021EF7
0x140021ec8  test    rax, rax
0x140021ecb  jz      loc_140021C4F
0x140021ed1  mov     [rsp+0C8h+arg_8], rsi
0x140021ed9  mov     [rsp+0C8h+arg_10], r12
0x140021ee1  mov     [rsp+0C8h+arg_18], r15
0x140021ee9  test    rax, rax
0x140021eec  jnz     loc_140021C54
0x140021ef2  mov     edi, 0C000009Ah
0x140021ef7  xor     ebx, ebx
0x140021ef9  mov     rcx, [rsp+0C8h+arg_38]
0x140021f01  mov     eax, edi
0x140021f03  mov     r12, [rsp+0C8h+arg_10]
0x140021f0b  mov     rsi, [rsp+0C8h+arg_8]
0x140021f13  mov     r15, [rsp+0C8h+arg_18]
0x140021f1b  mov     [rcx], rbx
0x140021f1e  add     rsp, 0A0h
0x140021f25  pop     r14
0x140021f27  pop     r13
0x140021f29  pop     rdi
0x140021f2a  pop     rbp
0x140021f2b  pop     rbx
0x140021f2c  retn
0x140021f2e  mov     [rax], r15
0x140021f31  mov     [rax+8], rsi
0x140021f35  mov     rax, [rbp+8]
0x140021f39  inc     dword ptr [rax+4]
0x140021f3c  jmp     loc_140021E5B
0x140021f41  mov     ecx, [r14+0Ch]; this
0x140021f45  mov     r8d, [r14+1Ch]
0x140021f49  mov     eax, [r14+24h]
0x140021f4d  add     r8d, ecx
0x140021f50  inc     eax
0x140021f52  mov     [r14+24h], eax
0x140021f56  mov     eax, [r14+24h]
0x140021f5a  test    al, 0Fh
0x140021f5c  jz      loc_1400220EF
0x140021f62  mov     eax, [r14+20h]
0x140021f66  cmp     r8d, eax
0x140021f69  jbe     loc_140021E73
0x140021f6f  mov     [r14+20h], r8d
0x140021f73  jmp     loc_140021E73
0x140021f78  mov     r10, [rbx+150h]
0x140021f7f  mov     r9, [rbx+60h]
0x140021f83  cmp     r10, 2
0x140021f87  jb      short loc_140021FB8
0x140021f89  mov     rax, [rdi]
0x140021f8c  cmp     rax, r9
0x140021f8f  jz      loc_140022027
0x140021f95  mov     r8, [r9+0A0h]
0x140021f9c  mov     rdx, r8
0x140021f9f  sub     rdx, [rax+0A0h]
0x140021fa6  add     rdx, [rdi+10h]
0x140021faa  cmovnz  r8, rdx
0x140021fae  cmp     r10, r8
0x140021fb1  setz    al
0x140021fb4  test    al, al
0x140021fb6  jnz     short loc_140022015
0x140021fb8  mov     rax, [rdi+10h]
0x140021fbc  mov     [rbx+150h], rax
0x140021fc3  mov     rax, [r9+18h]
0x140021fc7  mov     rcx, [rax+48h]
0x140021fcb  mov     eax, [rcx+0D44h]
0x140021fd1  test    al, 2
0x140021fd3  jnz     loc_1400220DA
0x140021fd9  mov     eax, [r9+78h]
0x140021fdd  test    eax, eax
0x140021fdf  jnz     short loc_140022015
0x140021fe1  mov     rax, [r13+8]
0x140021fe5  test    dword ptr [rax+0D44h], 20000000h
0x140021fef  jnz     short loc_140022015
0x140021ff1  mov     rcx, r9
0x140021ff4  cmp     [r9+40h], r9
0x140021ff8  jnz     loc_1400220C0
0x140021ffe  test    byte ptr [rcx+0Fh], 8
0x140022002  jnz     short loc_140022015
0x140022004  mov     r8d, 1
0x14002200a  mov     rdx, r13
0x14002200d  mov     rcx, r9
0x140022010  call    ?EnqueueTreeUpdate@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@W4_EMS_ENQUEUE_FLAGS@@@Z; CmsBPlusTable::EnqueueTreeUpdate(CmsTransactionContext *,_EMS_ENQUEUE_FLAGS)
0x140022015  nop
0x140022016  lock or dword ptr [rbx+228h], 100098h
0x140022021  nop
0x140022022  jmp     loc_140021D84
0x140022027  cmp     [rdi+10h], r10
0x14002202b  jmp     short loc_140021FB1
0x14002202d  xor     edx, edx
0x14002202f  lea     rcx, qword_14026C3C0
0x140022036  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002203d  nop     dword ptr [rax+rax+00h]
0x140022042  mov     rax, cs:qword_14026C3C8
0x140022049  lea     r15, qword_14026C3C8
0x140022050  cmp     rax, r15
0x140022053  jz      short loc_140022098
0x140022055  mov     rsi, [rax]
0x140022058  cmp     [rax+18h], rbp
0x14002205c  jnz     short loc_140022090
0x14002205e  cmp     [rsi+8], rax
0x140022062  jnz     short loc_1400220B2
0x140022064  mov     rcx, [rax+8]
0x140022068  cmp     [rcx], rax
0x14002206b  jnz     short loc_1400220B2
0x14002206d  mov     [rcx], rsi
0x140022070  xor     r8d, r8d; Wait
0x140022073  mov     [rsi+8], rcx
0x140022077  xor     edx, edx; Increment
0x140022079  mov     rcx, [rax+10h]; Event
0x14002207d  mov     qword ptr [rax], 0
  ... truncated ...
```
