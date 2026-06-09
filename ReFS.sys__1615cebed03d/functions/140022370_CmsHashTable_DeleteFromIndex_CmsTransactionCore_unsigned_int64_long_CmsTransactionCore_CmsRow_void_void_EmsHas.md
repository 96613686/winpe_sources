# CmsHashTable::DeleteFromIndex(CmsTransactionCore *,unsigned __int64,long (*)(CmsTransactionCore *,_CmsRow *,void *),void *,EmsHashTableFlags,_SmsQuickIndex *,_SmsHashOverflow * *)

- ea: `0x140022370`
- end: `0x1400227a8`
- name: `?DeleteFromIndex@CmsHashTable@@QEAAJPEAVCmsTransactionCore@@_KP6AJ0PEAU_CmsRow@@PEAX@Z3W4EmsHashTableFlags@@PEAU_SmsQuickIndex@@PEAPEAU_SmsHashOverflow@@@Z`
- size: `1080`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b05d8`
- `0x14011fcb8`
- `0x140146048`
- `0x140152a18`
- `0x140154e10`
- `0x140154fd0`

## callees

- `0x140021720`
- `0x140022370`
- `0x140055a30`
- `0x14008f270`
- `0x1401f40a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400226cf`
- `ntoskrnl!KeSetEvent` at `0x1400226cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022525`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022525`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002272f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002272f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140022583`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140022583`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa4d5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa4d5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400226ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x140022797`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400226ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x140022797`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022765`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fa4f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022765`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401fa4f1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140022681`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140022681`

## pseudocode

```c
__int64 __fastcall CmsHashTable::DeleteFromIndex(
        CmsHashTable *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 (__fastcall *a4)(__int64, struct SmsHashEntry **, __int64),
        __int64 a5,
        char a6,
        _DWORD *a7,
        _QWORD *a8)
{
  char v8; // r12
  unsigned __int64 v10; // r10
  CmsHashTable *v11; // r14
  struct SmsHashEntry *v12; // r13
  signed __int64 v13; // rbx
  struct SmsHashEntry *v14; // rdi
  __int64 v15; // rdx
  __int16 v16; // ax
  __int16 v17; // cx
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // esi
  struct SmsHashEntry *v22; // rcx
  _QWORD *v23; // rsi
  __int64 v24; // rbx
  struct _SLIST_ENTRY *v25; // r8
  struct _NPAGED_LOOKASIDE_LIST *v26; // rcx
  unsigned int v28; // edx
  __int64 v29; // r13
  __int64 v30; // rax
  __int64 v32; // rax
  __int64 *v33; // rbx
  __int64 **v34; // rcx
  struct _KEVENT *v35; // rcx
  __int64 v36; // rcx
  struct _SmsHashLocation *v37; // [rsp+38h] [rbp-71h]
  struct SmsHashEntry **v38; // [rsp+40h] [rbp-69h]
  struct SmsHashEntry *v39[2]; // [rsp+50h] [rbp-59h] BYREF
  int v40; // [rsp+60h] [rbp-49h]
  int v41; // [rsp+64h] [rbp-45h]
  __int64 v42; // [rsp+68h] [rbp-41h]
  __int128 v43; // [rsp+70h] [rbp-39h] BYREF
  __int64 v44; // [rsp+80h] [rbp-29h]
  int v45; // [rsp+90h] [rbp-19h] BYREF
  struct SmsHashEntry *v46; // [rsp+98h] [rbp-11h]
  __int64 v47; // [rsp+A0h] [rbp-9h]
  __int64 v48; // [rsp+A8h] [rbp-1h]
  unsigned int v52; // [rsp+120h] [rbp+77h]

  v8 = a6;
  v44 = 0;
  v39[0] = 0;
  v10 = a3;
  v11 = a1;
  v43 = 0;
  if ( (a6 & 8) != 0 )
  {
    ExAcquirePushLockSharedEx((char *)a1 + 40, 4);
    v10 = a3;
  }
  if ( a7 )
  {
    v28 = a7[2];
    v29 = (unsigned int)a7[4];
    HIDWORD(v43) = a7[3];
    v52 = v28;
    DWORD2(v43) = v28;
    v14 = (struct SmsHashEntry *)(16LL * HIDWORD(v43) + *((_QWORD *)v11 + 2 * v28));
    LODWORD(v44) = v29;
    v46 = v14;
    v45 = 0;
    v47 = -2;
    v48 = -3;
    do
    {
      while ( 1 )
      {
        v13 = *(_QWORD *)v14;
        if ( (unsigned __int64)(*(_QWORD *)v14 + 3LL) > 1 )
          break;
        if ( !MsBackoff((struct _SmsBackoff *)&v45, v28) )
          SmsHashEntry::WaitExtended(v14);
      }
    }
    while ( v13 != _InterlockedCompareExchange64((volatile signed __int64 *)v14, -2, v13) );
    *(_QWORD *)&v43 = v13;
    if ( v13 == -1 )
      v12 = (struct SmsHashEntry *)(*(_QWORD *)(*((_QWORD *)v14 + 1) + 8LL) + 16 * v29);
    else
      v12 = v14;
    v8 = a6;
    v39[0] = v14;
    if ( v12 )
      goto LABEL_6;
    v10 = a3;
  }
  v12 = CmsHashTable::FindAndLockEntryInternal(
          v11,
          v10,
          0,
          (v8 & 2) != 0,
          *((_QWORD *)v11 + 2) != 0,
          (struct _SmsHashLocation *)&v43,
          v39,
          v37,
          v38);
  if ( !v12 )
  {
    v21 = -1073741772;
    goto LABEL_21;
  }
  v13 = v43;
  v14 = v39[0];
  v52 = DWORD2(v43);
LABEL_6:
  if ( a4 )
  {
    v15 = *((_QWORD *)v12 + 1);
    v40 = 0;
    *(_OWORD *)v39 = 0;
    v42 = 0;
    v16 = *(_WORD *)(v15 + 8);
    v17 = v16 & 3;
    if ( (v16 & 0x40) != 0 )
    {
      *((_QWORD *)&v43 + 1) = v15 + 12;
      v18 = *(unsigned __int16 *)(v15 + 10);
      WORD3(v43) = HIWORD(v39[0]);
      LODWORD(v43) = 12;
      WORD2(v43) = v16 & 3;
    }
    else
    {
      v18 = *(_DWORD *)(v15 + 12);
      LODWORD(v43) = *(unsigned __int16 *)(v15 + 6);
      WORD3(v43) = HIWORD(v39[0]);
      v19 = v15 + *(unsigned __int16 *)(v15 + 4);
      WORD2(v43) = v17 | 4;
      v20 = *(unsigned __int16 *)(v15 + 10);
      *((_QWORD *)&v43 + 1) = v19;
      v15 += v20;
    }
    v40 = v18;
    v41 = HIDWORD(v39[0]);
    v42 = v15;
    *(_OWORD *)v39 = v43;
    v21 = a4(a2, v39, a5);
    if ( v21 )
    {
      v11 = a1;
      goto LABEL_21;
    }
  }
  v22 = (struct SmsHashEntry *)*((_QWORD *)v12 + 1);
  v39[0] = v22;
  v23 = 0;
  *((_QWORD *)v12 + 1) = 0;
  if ( v13 == -1 )
  {
    *(_QWORD *)v12 = 0;
    v30 = *((_QWORD *)v14 + 1);
    if ( (*(_DWORD *)(v30 + 4))-- != 1 )
      goto LABEL_12;
    v23 = (_QWORD *)*((_QWORD *)v14 + 1);
    *((_QWORD *)v14 + 1) = 0;
  }
  v13 = 0;
LABEL_12:
  if ( _InterlockedExchange64((volatile __int64 *)v14, v13) == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
    v32 = qword_14026C3C8;
    if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
    {
      do
      {
        v33 = *(__int64 **)v32;
        if ( *(struct SmsHashEntry **)(v32 + 24) == v14 )
        {
          if ( v33[1] != v32 || (v34 = *(__int64 ***)(v32 + 8), *v34 != (__int64 *)v32) )
            __fastfail(3u);
          *v34 = v33;
          v33[1] = (__int64)v34;
          v35 = *(struct _KEVENT **)(v32 + 16);
          *(_QWORD *)v32 = 0;
          KeSetEvent(v35, 0, 0);
        }
        v32 = (__int64)v33;
      }
      while ( v33 != &qword_14026C3C8 );
    }
    ExReleasePushLockEx(&qword_14026C3C0, 0);
    v22 = v39[0];
  }
  if ( (v8 & 1) != 0 || !v22 )
    goto LABEL_19;
  v24 = *((_QWORD *)v22 - 2);
  v25 = (struct _SLIST_ENTRY *)((char *)v22 - 16);
  if ( !v24 )
    goto LABEL_50;
  if ( *(_BYTE *)(v24 + 8) )
  {
    v26 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 64);
    if ( *(_BYTE *)(v24 + 9) )
      ExFreeToNPagedLookasideList(v26, v25);
    else
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v26, v25);
    goto LABEL_19;
  }
  v36 = *(_QWORD *)(v24 + 88);
  if ( (int)v36 < *(_DWORD *)(v24 + 80) || SHIDWORD(v36) >= (int)v36 )
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 64), v25);
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
  }
  else
  {
LABEL_50:
    ExFreePoolWithTag(v25, 0);
  }
LABEL_19:
  if ( v23 )
  {
    if ( a8 )
    {
      *v23 = *a8;
      *a8 = v23;
    }
    else
    {
      ExFreePoolWithTag(v23, 0);
    }
  }
  v11 = a1;
  _InterlockedDecrement((volatile signed __int32 *)a1 + 4 * v52 + 3);
  v21 = 0;
LABEL_21:
  if ( (a6 & 8) != 0 )
    ExReleasePushLockEx((char *)v11 + 40, 0);
  return v21;
}

```

## disassembly

```asm
0x140022370  mov     [rsp-8+arg_10], r8
0x140022375  mov     [rsp-8+arg_8], rdx
0x14002237a  mov     [rsp-8+arg_0], rcx
0x14002237f  push    rbp
0x140022380  push    rsi
0x140022381  push    r12
0x140022383  push    r14
0x140022385  push    r15
0x140022387  lea     rbp, [rsp-17h]
0x14002238c  sub     rsp, 0C0h
0x140022393  mov     r12d, dword ptr [rbp+37h+arg_28]
0x140022397  xor     eax, eax
0x140022399  mov     r15d, r12d
0x14002239c  mov     [rbp+37h+var_60], rax
0x1400223a0  mov     [rbp+37h+var_90], rax
0x1400223a4  xorps   xmm0, xmm0
0x1400223a7  mov     rsi, r9
0x1400223aa  mov     r10, r8
0x1400223ad  mov     r14, rcx
0x1400223b0  movups  [rbp+37h+var_70], xmm0
0x1400223b4  and     r15d, 8
0x1400223b8  jnz     loc_140022726
0x1400223be  mov     rax, [rbp+37h+arg_30]
0x1400223c2  mov     [rsp+0E0h+arg_18], rbx
0x1400223ca  mov     [rsp+0E0h+var_28], rdi
0x1400223d2  mov     [rsp+0E0h+var_30], r13
0x1400223da  test    rax, rax
0x1400223dd  jnz     loc_140022591
0x1400223e3  cmp     qword ptr [r14+10h], 0
0x1400223e8  lea     rcx, [rbp+37h+var_90]
0x1400223ec  mov     [rsp+0E0h+var_B0], rcx; struct SmsHashEntry **
0x1400223f1  mov     r9d, r12d
0x1400223f4  setnz   al
0x1400223f7  lea     rcx, [rbp+37h+var_70]
0x1400223fb  mov     [rsp+0E0h+var_B8], rcx; struct _SmsHashLocation *
0x140022400  xor     r8d, r8d; unsigned __int8
0x140022403  shr     r9d, 1
0x140022406  mov     rcx, r14; this
0x140022409  and     r9b, 1; unsigned __int8
0x14002240d  mov     [rsp+0E0h+var_C0], al; char
0x140022411  mov     rdx, r10; unsigned __int64
0x140022414  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x140022419  mov     r13, rax
0x14002241c  test    rax, rax
0x14002241f  jz      loc_140022670
0x140022425  mov     eax, dword ptr [rbp+37h+var_70+8]
0x140022428  mov     rbx, qword ptr [rbp+37h+var_70]
0x14002242c  mov     rdi, [rbp+37h+var_90]
0x140022430  mov     [rbp+37h+arg_30], rax
0x140022434  test    rsi, rsi
0x140022437  jz      loc_1400224C8
0x14002243d  mov     rdx, [r13+8]
0x140022441  xor     eax, eax
0x140022443  xorps   xmm0, xmm0
0x140022446  mov     [rbp+37h+var_80], eax
0x140022449  movups  xmmword ptr [rbp+37h+var_90], xmm0
0x14002244d  mov     [rbp+37h+var_78], rax
0x140022451  movzx   eax, word ptr [rdx+8]
0x140022455  lea     r8, [rdx+0Ch]
0x140022459  movzx   ecx, ax
0x14002245c  and     cx, 3
0x140022460  test    al, 40h
0x140022462  jnz     loc_14002264F
0x140022468  movzx   eax, word ptr [rdx+6]
0x14002246c  or      cx, 4
0x140022470  mov     r8d, [r8]
0x140022473  mov     dword ptr [rbp+37h+var_70], eax
0x140022476  movzx   eax, word ptr [rbp+37h+var_90+6]
0x14002247a  mov     word ptr [rbp+37h+var_70+6], ax
0x14002247e  movzx   eax, word ptr [rdx+4]
0x140022482  add     rax, rdx
0x140022485  mov     word ptr [rbp+37h+var_70+4], cx
0x140022489  movzx   ecx, word ptr [rdx+0Ah]
0x14002248d  mov     qword ptr [rbp+37h+var_70+8], rax
0x140022491  add     rdx, rcx
0x140022494  mov     eax, dword ptr [rbp+37h+var_90+4]
0x140022497  movups  xmm0, [rbp+37h+var_70]
0x14002249b  mov     rcx, [rbp+37h+arg_8]
0x14002249f  mov     [rbp+37h+var_80], r8d
0x1400224a3  mov     r8, [rbp+37h+arg_20]
0x1400224a7  mov     [rbp+37h+var_7C], eax
0x1400224aa  mov     rax, rsi
0x1400224ad  mov     [rbp+37h+var_78], rdx
0x1400224b1  lea     rdx, [rbp+37h+var_90]
0x1400224b5  movups  xmmword ptr [rbp+37h+var_90], xmm0
0x1400224b9  call    _guard_dispatch_icall
0x1400224be  mov     esi, eax
0x1400224c0  test    eax, eax
0x1400224c2  jnz     loc_140022627
0x1400224c8  mov     rcx, [r13+8]
0x1400224cc  xor     edx, edx
0x1400224ce  mov     [rbp+37h+var_90], rcx
0x1400224d2  mov     esi, edx
0x1400224d4  mov     [r13+8], rdx
0x1400224d8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400224dc  jz      loc_140022630
0x1400224e2  mov     rbx, rdx
0x1400224e5  xchg    rbx, [rdi]
0x1400224e8  cmp     rbx, 0FFFFFFFFFFFFFFFDh
0x1400224ec  jz      loc_14002267A
0x1400224f2  test    r12b, 1
0x1400224f6  jnz     short loc_140022531
0x1400224f8  test    rcx, rcx
0x1400224fb  jz      short loc_140022531
0x1400224fd  mov     rbx, [rcx-10h]
0x140022501  lea     r8, [rcx-10h]
0x140022505  test    rbx, rbx
0x140022508  jz      loc_140022760
0x14002250e  cmp     byte ptr [rbx+8], 0
0x140022512  jz      loc_140022744
0x140022518  cmp     byte ptr [rbx+9], 0
0x14002251c  lea     rcx, [rbx+40h]; Lookaside
0x140022520  mov     rdx, r8; Entry
0x140022523  jz      short loc_140022583
0x140022525  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002252c  nop     dword ptr [rax+rax+00h]
0x140022531  test    rsi, rsi
0x140022534  jnz     loc_140022776
0x14002253a  mov     eax, dword ptr [rbp+37h+arg_30]
0x14002253d  nop
0x14002253e  mov     r14, [rbp+37h+arg_0]
0x140022542  shl     rax, 4
0x140022546  lock dec dword ptr [rax+r14+0Ch]
0x14002254c  nop
0x14002254d  xor     esi, esi
0x14002254f  test    r15d, r15d
0x140022552  jnz     loc_140022791
0x140022558  mov     r13, [rsp+0E0h+var_30]
0x140022560  mov     eax, esi
0x140022562  mov     rdi, [rsp+0E0h+var_28]
0x14002256a  mov     rbx, [rsp+0E0h+arg_18]
0x140022572  add     rsp, 0C0h
0x140022579  pop     r15
0x14002257b  pop     r14
0x14002257d  pop     r12
0x14002257f  pop     rsi
0x140022580  pop     rbp
0x140022581  retn
0x140022583  call    cs:__imp_ExFreeToPagedLookasideList
0x14002258a  nop     dword ptr [rax+rax+00h]
0x14002258f  jmp     short loc_140022531
0x140022591  mov     edx, [rax+8]; unsigned int
0x140022594  mov     r12, 0FFFFFFFFFFFFFFFEh
0x14002259b  mov     ecx, [rax+0Ch]
0x14002259e  mov     r13d, [rax+10h]
0x1400225a2  mov     eax, edx
0x1400225a4  add     rax, rax
0x1400225a7  mov     dword ptr [rbp+37h+var_70+0Ch], ecx
0x1400225aa  shl     rcx, 4
0x1400225ae  mov     [rbp+37h+arg_30], rdx
0x1400225b2  mov     dword ptr [rbp+37h+var_70+8], edx
0x1400225b5  mov     rdi, [r14+rax*8]
0x1400225b9  add     rdi, rcx
0x1400225bc  mov     dword ptr [rbp+37h+var_60], r13d
0x1400225c0  xor     eax, eax
0x1400225c2  mov     [rbp+37h+var_48], rdi
0x1400225c6  mov     [rbp+37h+var_50], eax
0x1400225c9  mov     [rbp+37h+var_40], r12
0x1400225cd  mov     [rbp+37h+var_38], 0FFFFFFFFFFFFFFFDh
0x1400225d5  mov     rbx, [rdi]
0x1400225d8  lea     rax, [rbx+3]
0x1400225dc  cmp     rax, 1
0x1400225e0  jbe     loc_140022708
0x1400225e6  nop
0x1400225e7  mov     rax, rbx
0x1400225ea  lock cmpxchg [rdi], r12
0x1400225ef  nop
0x1400225f0  jnz     short loc_1400225D5
0x1400225f2  mov     qword ptr [rbp+37h+var_70], rbx
0x1400225f6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400225fa  jnz     short loc_140022622
0x1400225fc  mov     rax, [rdi+8]
0x140022600  shl     r13, 4
0x140022604  add     r13, [rax+8]
0x140022608  mov     r12d, dword ptr [rbp+37h+arg_28]
0x14002260c  mov     [rbp+37h+var_90], rdi
0x140022610  test    r13, r13
0x140022613  jnz     loc_140022434
0x140022619  mov     r10, [rbp+37h+arg_10]
0x14002261d  jmp     loc_1400223E3
0x140022622  mov     r13, rdi
0x140022625  jmp     short loc_140022608
0x140022627  mov     r14, [rbp+37h+arg_0]
0x14002262b  jmp     loc_14002254F
0x140022630  mov     [r13+0], rdx
0x140022634  mov     rax, [rdi+8]
0x140022638  add     dword ptr [rax+4], 0FFFFFFFFh
0x14002263c  jnz     loc_1400224E5
0x140022642  mov     rsi, [rdi+8]
0x140022646  mov     [rdi+8], rdx
0x14002264a  jmp     loc_1400224E2
0x14002264f  movzx   eax, word ptr [rbp+37h+var_90+6]
0x140022653  mov     qword ptr [rbp+37h+var_70+8], r8
0x140022657  movzx   r8d, word ptr [rdx+0Ah]
0x14002265c  mov     word ptr [rbp+37h+var_70+6], ax
0x140022660  mov     dword ptr [rbp+37h+var_70], 0Ch
0x140022667  mov     word ptr [rbp+37h+var_70+4], cx
0x14002266b  jmp     loc_140022494
0x140022670  mov     esi, 0C0000034h
0x140022675  jmp     loc_14002254F
0x14002267a  lea     rcx, qword_14026C3C0
0x140022681  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140022688  nop     dword ptr [rax+rax+00h]
0x14002268d  mov     rax, cs:qword_14026C3C8
0x140022694  lea     r14, qword_14026C3C8
0x14002269b  cmp     rax, r14
0x14002269e  jz      short loc_1400226E3
0x1400226a0  mov     rbx, [rax]
0x1400226a3  cmp     [rax+18h], rdi
0x1400226a7  jnz     short loc_1400226DB
0x1400226a9  cmp     [rbx+8], rax
0x1400226ad  jnz     short loc_140022701
0x1400226af  mov     rcx, [rax+8]
0x1400226b3  cmp     [rcx], rax
0x1400226b6  jnz     short loc_140022701
0x1400226b8  mov     [rcx], rbx
0x1400226bb  xor     r8d, r8d; Wait
0x1400226be  mov     [rbx+8], rcx
0x1400226c2  xor     edx, edx; Increment
0x1400226c4  mov     rcx, [rax+10h]; Event
0x1400226c8  mov     qword ptr [rax], 0
0x1400226cf  call    cs:__imp_KeSetEvent
0x1400226d6  nop     dword ptr [rax+rax+00h]
0x1400226db  mov     rax, rbx
0x1400226de  cmp     rbx, r14
0x1400226e1  jnz     short loc_1400226A0
0x1400226e3  xor     edx, edx
0x1400226e5  lea     rcx, qword_14026C3C0
0x1400226ec  call    cs:__imp_ExReleasePushLockEx
0x1400226f3  nop     dword ptr [rax+rax+00h]
0x1400226f8  mov     rcx, [rbp+37h+var_90]
0x1400226fc  jmp     loc_1400224F2
0x140022701  mov     ecx, 3
0x140022706  int     29h; Win8: RtlFailFast(ecx)
0x140022708  lea     rcx, [rbp+37h+var_50]; struct _SmsBackoff *
0x14002270c  call    ?MsBackoff@@YAEPEAU_SmsBackoff@@K@Z; MsBackoff(_SmsBackoff *,ulong)
0x140022711  test    al, al
0x140022713  jnz     loc_1400225D5
0x140022719  mov     rcx, rdi; this
0x14002271c  call    ?WaitExtended@SmsHashEntry@@AEAAXXZ; SmsHashEntry::WaitExtended(void)
0x140022721  jmp     loc_1400225D5
0x140022726  add     rcx, 28h ; '('
0x14002272a  mov     edx, 4
0x14002272f  call    cs:__imp_ExAcquirePushLockSharedEx
0x140022736  nop     dword ptr [rax+rax+00h]
0x14002273b  mov     r10, [rbp+37h+arg_10]
0x14002273f  jmp     loc_1400223BE
0x140022744  mov     rcx, [rbx+58h]
0x140022748  cmp     ecx, [rbx+50h]
0x14002274b  jl      loc_1401FA4CE
0x140022751  mov     rax, rcx
0x140022754  shr     rax, 20h
0x140022758  cmp     eax, ecx
0x14002275a  jge     loc_1401FA4CE
0x140022760  xor     edx, edx; Tag
0x140022762  mov     rcx, r8; P
0x140022765  call    cs:__imp_ExFreePoolWithTag
0x14002276c  nop     dword ptr [rax+rax+00h]
0x140022771  jmp     loc_140022531
0x140022776  mov     rcx, [rbp+37h+arg_38]
0x14002277a  test    rcx, rcx
0x14002277d  jz      loc_1401FA4EC
0x140022783  mov     rax, [rcx]
0x140022786  mov     [rsi], rax
0x140022789  mov     [rcx], rsi
0x14002278c  jmp     loc_14002253A
0x140022791  lea     rcx, [r14+28h]
0x140022795  xor     edx, edx
0x140022797  call    cs:__imp_ExReleasePushLockEx
0x14002279e  nop     dword ptr [rax+rax+00h]
0x1400227a3  jmp     loc_140022558
0x1401fa4ce  lea     rcx, [rbx+40h]; ListHead
0x1401fa4d2  mov     rdx, r8; ListEntry
0x1401fa4d5  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fa4dc  nop     dword ptr [rax+rax+00h]
0x1401fa4e1  nop
0x1401fa4e2  lock inc dword ptr [rbx+58h]
0x1401fa4e6  nop
0x1401fa4e7  jmp     loc_140022531
0x1401fa4ec  xor     edx, edx; Tag
0x1401fa4ee  mov     rcx, rsi; P
0x1401fa4f1  call    cs:__imp_ExFreePoolWithTag
0x1401fa4f8  nop     dword ptr [rax+rax+00h]
0x1401fa4fd  nop
0x1401fa4fe  jmp     loc_14002253A
```
