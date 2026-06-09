# AddUndoForSliceFastPath

- ea: `0x14003e770`
- end: `0x14003f0e4`
- name: `AddUndoForSliceFastPath`
- size: `2420`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003ca00`

## callees

- `0x14001c620`
- `0x14003e770`
- `0x14003f0f0`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14003ef6d`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003efbb`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003efec`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003f002`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f03e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f086`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f03e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f086`
- `ntoskrnl!ExAllocatePool2` at `0x14003e88a`
- `ntoskrnl!ExAllocatePool2` at `0x14003e90a`
- `ntoskrnl!ExAllocatePool2` at `0x14003e88a`
- `ntoskrnl!ExAllocatePool2` at `0x14003e90a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e84b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e8ca`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e84b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e8ca`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc1b0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc1c2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc1b0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc1c2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003f05b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003f0a3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003f05b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003f0a3`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003ec49`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003ed84`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003ec49`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003ed84`

## string_xrefs

- `0x1401fc1d4`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall AddUndoForSliceFastPath(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int *a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned __int64 v7; // rdx
  unsigned int v8; // r15d
  __int64 *v10; // r14
  __int64 v11; // rbp
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  __int64 i; // rsi
  __int64 v15; // rcx
  unsigned int v16; // esi
  unsigned int v17; // esi
  unsigned __int64 v18; // rbx
  unsigned int *v19; // rdi
  __int64 v20; // r9
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  _DWORD *v23; // rbx
  unsigned __int64 v24; // rdi
  unsigned int *v25; // rbp
  __int64 v26; // r9
  unsigned __int64 v27; // rdx
  __int64 Pool2; // rax
  struct SmsUndoRecord **v29; // rdx
  _QWORD *v30; // rdi
  __int64 v31; // rcx
  int v32; // edx
  __int64 v33; // rcx
  int v34; // edx
  __int64 v35; // rcx
  int v36; // edx
  int v37; // ecx
  int v38; // ecx
  __int64 v39; // r9
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  unsigned __int64 v42; // r8
  __int64 v43; // r9
  unsigned __int64 v44; // r8
  unsigned int v45; // r12d
  unsigned int *v46; // rdi
  unsigned int v47; // eax
  __int64 v48; // rsi
  __int64 v49; // rdx
  __int64 v50; // r8
  int v51; // r9d
  __int64 v52; // r10
  int v53; // r11d
  __int64 v54; // rax
  unsigned int v55; // eax
  unsigned int *v56; // rcx
  __int64 v57; // rbp
  __int64 v58; // r12
  struct SmsUndoRecord *v59; // rbx
  const void *v60; // rsi
  __int64 v61; // rdi
  __int64 v62; // rdx
  __int64 v63; // r8
  int v64; // r9d
  __int64 v65; // r10
  int v66; // r11d
  __int64 v67; // rax
  unsigned int v68; // eax
  void *v69; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v71; // rcx
  _QWORD *v72; // rax
  struct _NPAGED_LOOKASIDE_LIST *v73; // rcx
  _DWORD *v74; // rax
  unsigned int v75; // [rsp+20h] [rbp-B8h]
  __int64 *v77; // [rsp+38h] [rbp-A0h]
  struct SmsUndoRecord *v78[2]; // [rsp+70h] [rbp-68h] BYREF
  struct SmsUndoRecord *v79[2]; // [rsp+80h] [rbp-58h]

  v5 = 0;
  v77 = (__int64 *)a3;
  v7 = *((_QWORD *)a4 + 1);
  v8 = 0;
  v75 = 0;
  v10 = (__int64 *)a3;
  v11 = a1;
  *(_OWORD *)v78 = 0;
  *(_OWORD *)v79 = 0;
  if ( v7 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(*(_QWORD *)(a3 + 8) + 12LL) )
    {
      v31 = a4[4];
      if ( (_DWORD)v31 && (a3 = *((_QWORD *)a4 + 3), v7 >= a3) && v7 <= a3 + v31 )
      {
        v32 = 0;
      }
      else
      {
        v39 = *a4;
        if ( (_DWORD)v39 && (_DWORD)v31 && (v40 = *((_QWORD *)a4 + 3), v7 + v39 >= v40) && v7 + v39 <= v40 + v31 )
          a3 = (unsigned int)(v40 - v7);
        else
          a3 = (unsigned __int16)(v39 + 7) & 0xFFF8;
        v32 = (unsigned __int16)a3;
      }
      if ( v32 + (((_DWORD)v31 + 7) & 0xFFFFFFF8) + 16 )
        v8 = v32 + ((v31 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[4] + 7) & 0xFFFFFFF8) != 0 )
    {
      v8 = (a4[4] + 7) & 0xFFFFFFF8;
    }
  }
  v12 = *((_QWORD *)a4 + 5);
  if ( v12 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(v10[1] + 12) )
    {
      v33 = a4[12];
      if ( (_DWORD)v33 && (a3 = *((_QWORD *)a4 + 7), v12 >= a3) && v12 <= a3 + v33 )
      {
        v34 = 0;
      }
      else
      {
        v41 = a4[8];
        if ( (_DWORD)v41 && (_DWORD)v33 && (v42 = *((_QWORD *)a4 + 7), v12 + v41 >= v42) && v12 + v41 <= v42 + v33 )
          a3 = (unsigned int)(v42 - v12);
        else
          a3 = (unsigned __int16)(v41 + 7) & 0xFFF8;
        v34 = (unsigned __int16)a3;
      }
      if ( v34 + (((_DWORD)v33 + 7) & 0xFFFFFFF8) + 16 > v8 )
        v8 = v34 + ((v33 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[12] + 7) & 0xFFFFFFF8) > v8 )
    {
      v8 = (a4[12] + 7) & 0xFFFFFFF8;
    }
  }
  v13 = *((_QWORD *)a4 + 9);
  if ( v13 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(v10[1] + 12) )
    {
      v35 = a4[20];
      if ( (_DWORD)v35 && (a3 = *((_QWORD *)a4 + 11), v13 >= a3) && v13 <= a3 + v35 )
      {
        v36 = 0;
      }
      else
      {
        v43 = a4[16];
        if ( (_DWORD)v43 && (_DWORD)v35 && (v44 = *((_QWORD *)a4 + 11), v13 + v43 >= v44) && v13 + v43 <= v44 + v35 )
          a3 = (unsigned int)(v44 - v13);
        else
          a3 = (unsigned __int16)(v43 + 7) & 0xFFF8;
        v36 = (unsigned __int16)a3;
      }
      if ( v36 + (((_DWORD)v35 + 7) & 0xFFFFFFF8) + 16 > v8 )
        v8 = v36 + ((v35 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[20] + 7) & 0xFFFFFFF8) > v8 )
    {
      v8 = (a4[20] + 7) & 0xFFFFFFF8;
    }
  }
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    if ( !*(_QWORD *)&a4[8 * (unsigned int)i + 2] )
      continue;
    if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(a3) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, a3);
LABEL_142:
      v78[i] = 0;
LABEL_143:
      v45 = -1073741670;
      if ( v78[0] )
        CmsBPlusTable::FreeUndoRecord(v78[0], (struct CmsTransactionContext *)v29, a3);
      if ( v78[1] )
        CmsBPlusTable::FreeUndoRecord(v78[1], (struct CmsTransactionContext *)v29, a3);
      if ( v79[0] )
        CmsBPlusTable::FreeUndoRecord(v79[0], (struct CmsTransactionContext *)v29, a3);
      if ( v79[1] )
        CmsBPlusTable::FreeUndoRecord(v79[1], (struct CmsTransactionContext *)v29, a3);
      return v45;
    }
    v24 = ((v8 + 7) & 0xFFFFFFF8) + 88;
    v25 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v24 > *v25 )
    {
      v25 = 0;
      v27 = v24 + 16;
      goto LABEL_19;
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v71 = (struct _NPAGED_LOOKASIDE_LIST *)(v25 + 16);
      if ( *((_BYTE *)v25 + 9) )
        v72 = ExAllocateFromNPagedLookasideList(v71);
      else
        v72 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v71);
    }
    else
    {
      if ( (int)*((_QWORD *)v25 + 11) <= (int)HIDWORD(*((_QWORD *)v25 + 11)) )
        goto LABEL_50;
      v38 = _InterlockedDecrement((volatile signed __int32 *)v25 + 22);
      if ( v38 < (int)v25[23] || v38 < 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v25 + 22);
LABEL_50:
        v27 = v25[1];
LABEL_19:
        Pool2 = ExAllocatePool2(66, v27, 1766871885, v26);
        v30 = (_QWORD *)Pool2;
        if ( (Pool2 & 0xF) != 0 )
          goto LABEL_169;
        if ( !Pool2 )
          goto LABEL_134;
        goto LABEL_133;
      }
      v72 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25 + 4);
    }
    v30 = v72;
    if ( !v72 )
      goto LABEL_50;
LABEL_133:
    *v30 = v25;
    v30 += 2;
LABEL_134:
    if ( !v30 )
      goto LABEL_142;
    v11 = a1;
    v30[5] = a1;
    *((_DWORD *)v30 + 4) = 31;
    *((_DWORD *)v30 + 3) = v8;
    *((_DWORD *)v30 + 2) = v8;
    *((_WORD *)v30 + 10) = 0;
    *((_OWORD *)v30 + 3) = 0;
    *((_OWORD *)v30 + 4) = 0;
    v30[10] = 0;
    *((_DWORD *)v30 + 8) = 0;
    if ( v8 )
    {
      v30[3] = v30 + 11;
      memset(v30 + 11, 0, v8);
    }
    else
    {
      v30[3] = 0;
    }
    v78[i] = (struct SmsUndoRecord *)v30;
    v5 = ++v75;
  }
  v15 = v10[2];
  if ( (*(_BYTE *)(v15 + 8) & 0x40) != 0 )
    v16 = (*(unsigned __int16 *)(v15 + 10) + 7) & 0xFFFFFFF8;
  else
    v16 = *(_DWORD *)v15;
  if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(a3) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, a3);
    v29 = &v78[v5];
    goto LABEL_148;
  }
  v17 = 2 * v16;
  v18 = ((v17 + 7) & 0xFFFFFFF8) + 88;
  v19 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v18 > *v19 )
  {
    v19 = 0;
    v21 = v18 + 16;
    goto LABEL_13;
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v73 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 16);
    if ( *((_BYTE *)v19 + 9) )
      v74 = ExAllocateFromNPagedLookasideList(v73);
    else
      v74 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v73);
LABEL_87:
    v23 = v74;
    if ( !v74 )
      goto LABEL_45;
    goto LABEL_88;
  }
  if ( (int)*((_QWORD *)v19 + 11) > (int)HIDWORD(*((_QWORD *)v19 + 11)) )
  {
    v37 = _InterlockedDecrement((volatile signed __int32 *)v19 + 22);
    if ( v37 >= (int)v19[23] && v37 >= 0 )
    {
      v74 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v19 + 4);
      goto LABEL_87;
    }
    _InterlockedIncrement((volatile signed __int32 *)v19 + 22);
  }
LABEL_45:
  v21 = v19[1];
LABEL_13:
  v22 = ExAllocatePool2(66, v21, 1766871885, v20);
  v23 = (_DWORD *)v22;
  if ( (v22 & 0xF) != 0 )
LABEL_169:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v22 )
  {
LABEL_88:
    *(_QWORD *)v23 = v19;
    v23 += 4;
  }
  if ( !v23 )
  {
    v29 = &v78[v75];
LABEL_148:
    *v29 = 0;
    goto LABEL_143;
  }
  v23[4] = 30;
  *((_QWORD *)v23 + 5) = v11;
  v23[3] = v17;
  v23[2] = v17;
  *((_WORD *)v23 + 10) = 0;
  *((_OWORD *)v23 + 3) = 0;
  *((_OWORD *)v23 + 4) = 0;
  *((_QWORD *)v23 + 10) = 0;
  v23[8] = 0;
  if ( v17 )
  {
    *((_QWORD *)v23 + 3) = v23 + 22;
    memset(v23 + 22, 0, v17);
  }
  else
  {
    *((_QWORD *)v23 + 3) = 0;
  }
  v45 = 0;
  v46 = (unsigned int *)v10[2];
  v78[v75] = (struct SmsUndoRecord *)v23;
  if ( (v46[2] & 0x40) != 0 )
    v47 = (*((unsigned __int16 *)v46 + 5) + 7) & 0xFFFFFFF8;
  else
    v47 = *v46;
  v23[2] = v47;
  v23[8] = 0;
  *((_QWORD *)v23 + 5) = v11;
  v48 = *v10;
  _InterlockedIncrement((volatile signed __int32 *)(*v10 + 380));
  if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v48 + 560) )
    ++*(_DWORD *)(v48 + 384);
  else
    SmsPageLatch::AcquireShared((SmsPageLatch *)(v48 + 560), (struct CmsTransactionContext *)a2, 1);
  if ( *(char *)(*(_QWORD *)(v48 + 96) + 14LL) >= 0 )
    ++*(_DWORD *)(a2 + 196);
  ++*(_DWORD *)(v48 + 388);
  v49 = v10[1];
  v50 = v10[2];
  v51 = *((_DWORD *)v10 + 6);
  v52 = v10[4];
  v53 = *((_DWORD *)v10 + 7);
  if ( *((_QWORD *)v23 + 6) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *((_QWORD *)v23 + 6) = *v10;
  *((_QWORD *)v23 + 7) = v49;
  *((_QWORD *)v23 + 8) = v50;
  v23[18] = v51;
  *((_QWORD *)v23 + 10) = v52;
  v23[19] = v53;
  v54 = *v10;
  if ( *v10 && (!*(_BYTE *)(v54 + 392) && *(_QWORD *)(v54 + 96) == a1 || !*(_BYTE *)(a1 + 212)) )
    *((_BYTE *)v23 + 20) |= 1u;
  v55 = v23[2];
  if ( v55 )
  {
    v56 = (unsigned int *)*((_QWORD *)v23 + 3);
    if ( v46 )
    {
      if ( v46 != v56 )
        memmove(v56, v46, v55);
    }
    else
    {
      memset(v56, 0, (unsigned int)v23[2]);
    }
  }
  v57 = 0;
  *(_QWORD *)v23 = *(_QWORD *)(a2 + 144);
  *(_QWORD *)(a2 + 144) = v23;
  if ( v75 )
  {
    do
    {
      v58 = 8 * v57;
      v59 = v78[v57];
      v60 = (const void *)*((_QWORD *)v59 + 3);
      *((_DWORD *)v59 + 2) = v8;
      *((_DWORD *)v59 + 8) = 0;
      *((_QWORD *)v59 + 5) = a1;
      v61 = *v10;
      _InterlockedIncrement((volatile signed __int32 *)(*v10 + 380));
      if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v61 + 560) )
        ++*(_DWORD *)(v61 + 384);
      else
        SmsPageLatch::AcquireShared((SmsPageLatch *)(v61 + 560), (struct CmsTransactionContext *)a2, 1);
      if ( *(char *)(*(_QWORD *)(v61 + 96) + 14LL) >= 0 )
        ++*(_DWORD *)(a2 + 196);
      ++*(_DWORD *)(v61 + 388);
      v10 = v77;
      v62 = v77[1];
      v63 = v77[2];
      v64 = *((_DWORD *)v77 + 6);
      v65 = v77[4];
      v66 = *((_DWORD *)v77 + 7);
      if ( *((_QWORD *)v59 + 6) && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      *((_QWORD *)v59 + 6) = *v77;
      *((_QWORD *)v59 + 7) = v62;
      *((_QWORD *)v59 + 8) = v63;
      *((_DWORD *)v59 + 18) = v64;
      *((_QWORD *)v59 + 10) = v65;
      *((_DWORD *)v59 + 19) = v66;
      v67 = *v77;
      if ( *v77 && (!*(_BYTE *)(v67 + 392) && *(_QWORD *)(v67 + 96) == a1 || !*(_BYTE *)(a1 + 212)) )
        *((_BYTE *)v59 + 20) |= 1u;
      v68 = *((_DWORD *)v59 + 2);
      if ( v68 )
      {
        v69 = (void *)*((_QWORD *)v59 + 3);
        if ( v60 )
        {
          if ( v60 != v69 )
            memmove(v69, v60, v68);
        }
        else
        {
          memset(v69, 0, *((unsigned int *)v59 + 2));
        }
      }
      v57 = (unsigned int)(v57 + 1);
      *(_QWORD *)v59 = *(_QWORD *)(a2 + 144);
      *(_QWORD *)(a2 + 144) = v59;
      *(_QWORD *)(v58 + a5) = *((_QWORD *)v59 + 3);
    }
    while ( (unsigned int)v57 < v75 );
    return 0;
  }
  return v45;
}

```

## disassembly

```asm
0x14003e770  mov     [rsp+arg_0], rbx
0x14003e775  push    rbp
0x14003e776  push    rsi
0x14003e777  push    rdi
0x14003e778  push    r12
0x14003e77a  push    r13
0x14003e77c  push    r14
0x14003e77e  push    r15
0x14003e780  sub     rsp, 0A0h
0x14003e787  mov     rax, cs:__security_cookie
0x14003e78e  xor     rax, rsp
0x14003e791  mov     [rsp+0D8h+var_48], rax
0x14003e799  mov     rax, [rsp+0D8h+arg_20]
0x14003e7a1  xor     edi, edi
0x14003e7a3  xorps   xmm0, xmm0
0x14003e7a6  mov     [rsp+0D8h+var_A0], r8
0x14003e7ab  mov     r13, rdx
0x14003e7ae  mov     [rsp+0D8h+var_B0], rcx
0x14003e7b3  mov     rdx, [r9+8]
0x14003e7b7  xor     r15d, r15d
0x14003e7ba  mov     [rsp+0D8h+var_98], rax
0x14003e7bf  mov     rbx, r9
0x14003e7c2  mov     [rsp+0D8h+var_B8], edi
0x14003e7c6  mov     r14, r8
0x14003e7c9  mov     rbp, rcx
0x14003e7cc  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x14003e7d1  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x14003e7d9  test    rdx, rdx
0x14003e7dc  jnz     loc_14003E92F
0x14003e7e2  mov     rdx, [rbx+28h]
0x14003e7e6  test    rdx, rdx
0x14003e7e9  jnz     loc_14003E96C
0x14003e7ef  mov     rdx, [rbx+48h]
0x14003e7f3  test    rdx, rdx
0x14003e7f6  jnz     loc_14003E9A8
0x14003e7fc  xor     esi, esi
0x14003e7fe  mov     r12d, 0FFFFFFFFh
0x14003e804  cmp     esi, 3
0x14003e807  jnb     short loc_14003E81F
0x14003e809  mov     eax, esi
0x14003e80b  shl     rax, 5
0x14003e80f  cmp     qword ptr [rax+rbx+8], 0
0x14003e815  jnz     loc_14003E8AF
0x14003e81b  inc     esi
0x14003e81d  jmp     short loc_14003E804
0x14003e81f  mov     rcx, [r14+10h]
0x14003e823  test    byte ptr [rcx+8], 40h
0x14003e827  jnz     loc_14003E9F6
0x14003e82d  mov     esi, [rcx]
0x14003e82f  mov     eax, [r13+0]
0x14003e833  bt      rax, 0Ch
0x14003e838  jb      loc_14003EFBB
0x14003e83e  add     esi, esi
0x14003e840  xor     ecx, ecx; ProcNumber
0x14003e842  lea     ebx, [rsi+7]
0x14003e845  and     ebx, 0FFFFFFF8h
0x14003e848  add     ebx, 58h ; 'X'
0x14003e84b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003e852  nop     dword ptr [rax+rax+00h]
0x14003e857  xor     edx, edx
0x14003e859  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14003e85f  lea     rdi, [rdx+rdx*2]
0x14003e863  shl     rdi, 6
0x14003e867  add     rdi, cs:qword_140269410
0x14003e86e  mov     eax, [rdi]
0x14003e870  cmp     rbx, rax
0x14003e873  jbe     loc_14003EA05
0x14003e879  xor     edi, edi
0x14003e87b  lea     rdx, [rbx+10h]
0x14003e87f  mov     ecx, 42h ; 'B'
0x14003e884  mov     r8d, 6950534Dh
0x14003e88a  call    cs:__imp_ExAllocatePool2
0x14003e891  nop     dword ptr [rax+rax+00h]
0x14003e896  mov     rbx, rax
0x14003e899  test    al, 0Fh
0x14003e89b  jnz     loc_1401FC1D4
0x14003e8a1  test    rax, rax
0x14003e8a4  jz      loc_14003EBD1
0x14003e8aa  jmp     loc_14003EBCA
0x14003e8af  mov     eax, [r13+0]
0x14003e8b3  bt      rax, 0Ch
0x14003e8b8  jb      loc_14003EF6D
0x14003e8be  lea     edi, [r15+7]
0x14003e8c2  xor     ecx, ecx; ProcNumber
0x14003e8c4  and     edi, 0FFFFFFF8h
0x14003e8c7  add     edi, 58h ; 'X'
0x14003e8ca  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003e8d1  nop     dword ptr [rax+rax+00h]
0x14003e8d6  xor     edx, edx
0x14003e8d8  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14003e8de  lea     rbp, [rdx+rdx*2]
0x14003e8e2  shl     rbp, 6
0x14003e8e6  add     rbp, cs:qword_140269410
0x14003e8ed  mov     eax, [rbp+0]
0x14003e8f0  cmp     rdi, rax
0x14003e8f3  jbe     loc_14003EA44
0x14003e8f9  xor     ebp, ebp
0x14003e8fb  lea     rdx, [rdi+10h]
0x14003e8ff  mov     ecx, 42h ; 'B'
0x14003e904  mov     r8d, 6950534Dh
0x14003e90a  call    cs:__imp_ExAllocatePool2
0x14003e911  nop     dword ptr [rax+rax+00h]
0x14003e916  mov     rdi, rax
0x14003e919  test    al, 0Fh
0x14003e91b  jnz     loc_1401FC1D4
0x14003e921  test    rax, rax
0x14003e924  jz      loc_14003EEF1
0x14003e92a  jmp     loc_14003EEEA
0x14003e92f  mov     rax, [rcx+18h]
0x14003e933  mov     ecx, [rax+2Ch]
0x14003e936  test    cl, 4
0x14003e939  jnz     loc_14003EB1A
0x14003e93f  mov     ecx, [r9+10h]
0x14003e943  test    ecx, ecx
0x14003e945  jz      loc_14003EA82
0x14003e94b  mov     r8, [r9+18h]
0x14003e94f  cmp     rdx, r8
0x14003e952  jb      loc_14003EA82
0x14003e958  lea     rax, [r8+rcx]
0x14003e95c  cmp     rdx, rax
0x14003e95f  ja      loc_14003EA82
0x14003e965  xor     edx, edx
0x14003e967  jmp     loc_14003EAB7
0x14003e96c  mov     rax, [rbp+18h]
0x14003e970  mov     ecx, [rax+2Ch]
0x14003e973  test    cl, 4
0x14003e976  jnz     loc_14003EB3D
0x14003e97c  mov     ecx, [rbx+30h]
0x14003e97f  test    ecx, ecx
0x14003e981  jz      loc_14003EACD
0x14003e987  mov     r8, [rbx+38h]
0x14003e98b  cmp     rdx, r8
0x14003e98e  jb      loc_14003EACD
0x14003e994  lea     rax, [r8+rcx]
0x14003e998  cmp     rdx, rax
0x14003e99b  ja      loc_14003EACD
0x14003e9a1  xor     edx, edx
0x14003e9a3  jmp     loc_14003EB03
0x14003e9a8  mov     rax, [rbp+18h]
0x14003e9ac  mov     ecx, [rax+2Ch]
0x14003e9af  test    cl, 4
0x14003e9b2  jnz     loc_14003EB60
0x14003e9b8  mov     ecx, [rbx+50h]
0x14003e9bb  test    ecx, ecx
0x14003e9bd  jz      loc_14003EB83
0x14003e9c3  mov     r8, [rbx+58h]
0x14003e9c7  cmp     rdx, r8
0x14003e9ca  jb      loc_14003EB83
0x14003e9d0  lea     rax, [r8+rcx]
0x14003e9d4  cmp     rdx, rax
0x14003e9d7  ja      loc_14003EB83
0x14003e9dd  xor     edx, edx
0x14003e9df  lea     eax, [rcx+7]
0x14003e9e2  and     eax, 0FFFFFFF8h
0x14003e9e5  add     eax, 10h
0x14003e9e8  add     eax, edx
0x14003e9ea  cmp     eax, r15d
0x14003e9ed  cmova   r15d, eax
0x14003e9f1  jmp     loc_14003E7FC
0x14003e9f6  movzx   esi, word ptr [rcx+0Ah]
0x14003e9fa  add     esi, 7
0x14003e9fd  and     esi, 0FFFFFFF8h
0x14003ea00  jmp     loc_14003E82F
0x14003ea05  cmp     byte ptr [rdi+8], 0
0x14003ea09  jnz     loc_14003F078
0x14003ea0f  mov     rcx, [rdi+58h]
0x14003ea13  mov     rax, rcx
0x14003ea16  shr     rax, 20h
0x14003ea1a  cmp     ecx, eax
0x14003ea1c  jle     short loc_14003EA3C
0x14003ea1e  nop
0x14003ea1f  lock xadd [rdi+58h], r12d
0x14003ea25  nop
0x14003ea26  lea     ecx, [r12-1]
0x14003ea2b  mov     eax, [rdi+5Ch]
0x14003ea2e  cmp     ecx, eax
0x14003ea30  jge     loc_14003F097
0x14003ea36  nop
0x14003ea37  lock inc dword ptr [rdi+58h]
0x14003ea3b  nop
0x14003ea3c  mov     edx, [rdi+4]
0x14003ea3f  jmp     loc_14003E87F
0x14003ea44  cmp     byte ptr [rbp+8], 0
0x14003ea48  jnz     loc_14003F030
0x14003ea4e  mov     rcx, [rbp+58h]
0x14003ea52  mov     rax, rcx
0x14003ea55  shr     rax, 20h
0x14003ea59  cmp     ecx, eax
0x14003ea5b  jle     short loc_14003EA7A
0x14003ea5d  nop
0x14003ea5e  mov     ecx, r12d
0x14003ea61  lock xadd [rbp+58h], ecx
0x14003ea66  nop
0x14003ea67  dec     ecx
0x14003ea69  mov     eax, [rbp+5Ch]
0x14003ea6c  cmp     ecx, eax
0x14003ea6e  jge     loc_14003F04F
0x14003ea74  nop
0x14003ea75  lock inc dword ptr [rbp+58h]
0x14003ea79  nop
0x14003ea7a  mov     edx, [rbp+4]
0x14003ea7d  jmp     loc_14003E8FF
0x14003ea82  mov     r9d, [r9]
0x14003ea85  test    r9d, r9d
0x14003ea88  jz      short loc_14003EAA8
0x14003ea8a  test    ecx, ecx
0x14003ea8c  jz      short loc_14003EAA8
0x14003ea8e  mov     r8, [rbx+18h]
0x14003ea92  lea     r10, [rdx+r9]
0x14003ea96  cmp     r10, r8
0x14003ea99  jb      short loc_14003EAA8
0x14003ea9b  lea     rax, [r8+rcx]
0x14003ea9f  cmp     r10, rax
0x14003eaa2  jbe     loc_14003F018
0x14003eaa8  lea     r8d, [r9+7]
0x14003eaac  and     r8d, 0FFF8h
0x14003eab3  movzx   edx, r8w
0x14003eab7  lea     eax, [rcx+7]
0x14003eaba  and     eax, 0FFFFFFF8h
0x14003eabd  add     eax, 10h
0x14003eac0  add     eax, edx
0x14003eac2  test    eax, eax
0x14003eac4  cmovnz  r15d, eax
0x14003eac8  jmp     loc_14003E7E2
0x14003eacd  mov     r9d, [rbx+20h]
0x14003ead1  test    r9d, r9d
0x14003ead4  jz      short loc_14003EAF4
0x14003ead6  test    ecx, ecx
0x14003ead8  jz      short loc_14003EAF4
0x14003eada  mov     r8, [rbx+38h]
0x14003eade  lea     r10, [rdx+r9]
0x14003eae2  cmp     r10, r8
0x14003eae5  jb      short loc_14003EAF4
0x14003eae7  lea     rax, [r8+rcx]
0x14003eaeb  cmp     r10, rax
0x14003eaee  jbe     loc_14003F020
0x14003eaf4  lea     r8d, [r9+7]
0x14003eaf8  and     r8d, 0FFF8h
0x14003eaff  movzx   edx, r8w
0x14003eb03  lea     eax, [rcx+7]
0x14003eb06  and     eax, 0FFFFFFF8h
0x14003eb09  add     eax, 10h
0x14003eb0c  add     eax, edx
0x14003eb0e  cmp     eax, r15d
0x14003eb11  cmova   r15d, eax
0x14003eb15  jmp     loc_14003E7EF
0x14003eb1a  mov     rax, [r8+8]
0x14003eb1e  cmp     [rax+0Ch], dil
0x14003eb22  jnz     loc_14003E93F
0x14003eb28  mov     eax, [r9+10h]
0x14003eb2c  add     eax, 7
0x14003eb2f  and     eax, 0FFFFFFF8h
0x14003eb32  test    eax, eax
0x14003eb34  cmovnz  r15d, eax
0x14003eb38  jmp     loc_14003E7E2
0x14003eb3d  mov     rax, [r14+8]
0x14003eb41  cmp     [rax+0Ch], dil
0x14003eb45  jnz     loc_14003E97C
0x14003eb4b  mov     eax, [rbx+30h]
0x14003eb4e  add     eax, 7
0x14003eb51  and     eax, 0FFFFFFF8h
0x14003eb54  cmp     eax, r15d
0x14003eb57  cmova   r15d, eax
0x14003eb5b  jmp     loc_14003E7EF
0x14003eb60  mov     rax, [r14+8]
0x14003eb64  cmp     [rax+0Ch], dil
0x14003eb68  jnz     loc_14003E9B8
0x14003eb6e  mov     eax, [rbx+50h]
0x14003eb71  add     eax, 7
0x14003eb74  and     eax, 0FFFFFFF8h
0x14003eb77  cmp     eax, r15d
0x14003eb7a  cmova   r15d, eax
0x14003eb7e  jmp     loc_14003E7FC
0x14003eb83  mov     r9d, [rbx+40h]
0x14003eb87  test    r9d, r9d
0x14003eb8a  jz      short loc_14003EBAA
0x14003eb8c  test    ecx, ecx
0x14003eb8e  jz      short loc_14003EBAA
0x14003eb90  mov     r8, [rbx+58h]
0x14003eb94  lea     r10, [rdx+r9]
0x14003eb98  cmp     r10, r8
0x14003eb9b  jb      short loc_14003EBAA
0x14003eb9d  lea     rax, [r8+rcx]
0x14003eba1  cmp     r10, rax
0x14003eba4  jbe     loc_14003F028
0x14003ebaa  lea     r8d, [r9+7]
0x14003ebae  and     r8d, 0FFF8h
0x14003ebb5  movzx   edx, r8w
0x14003ebb9  jmp     loc_14003E9DF
0x14003ebbe  mov     rbx, rax
0x14003ebc1  test    rax, rax
0x14003ebc4  jz      loc_14003EA3C
0x14003ebca  mov     [rbx], rdi
0x14003ebcd  add     rbx, 10h
0x14003ebd1  test    rbx, rbx
0x14003ebd4  jz      loc_14003F0B4
0x14003ebda  mov     dword ptr [rbx+10h], 1Eh
0x14003ebe1  xorps   xmm0, xmm0
0x14003ebe4  mov     [rbx+28h], rbp
0x14003ebe8  xor     eax, eax
  ... truncated ...
```
