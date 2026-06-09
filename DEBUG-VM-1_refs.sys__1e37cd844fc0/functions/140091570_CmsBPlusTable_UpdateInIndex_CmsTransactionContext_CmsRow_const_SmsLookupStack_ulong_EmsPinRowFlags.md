# CmsBPlusTable::UpdateInIndex(CmsTransactionContext *,_CmsRow const &,SmsLookupStack &&,ulong,EmsPinRowFlags)

- ea: `0x140091570`
- end: `0x140091d7a`
- name: `?UpdateInIndex@CmsBPlusTable@@UEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@$$QEAUSmsLookupStack@@KW4EmsPinRowFlags@@@Z`
- size: `2058`
- prototype: `__int64 __usercall@<rax>(CmsBPlusTable *this@<rcx>, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003f39c`
- `0x14005b78c`
- `0x140062700`
- `0x140135680`
- `0x14015c96c`

## callees

- `0x140016440`
- `0x14003f0f0`
- `0x14007d820`
- `0x140091570`
- `0x1400cb544`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1400d1e34`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140091c4a`
- `ntoskrnl!KdDebuggerEnabled` at `0x140091c8a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140091d10`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140091d10`
- `ntoskrnl!ExAllocatePool2` at `0x1400916bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400916bf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140091684`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140091684`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140201906`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140201906`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140091d2d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140091d2d`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140091ae6`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140091ae6`

## string_xrefs

- `0x140091d56`: `Calling UpdateSimple with a mismatch DataLength row!`
- `0x1400916d6`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::UpdateInIndex(
        CmsBPlusTable *this,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        unsigned int a5)
{
  __int64 v5; // r10
  __int64 v8; // r13
  __int16 v9; // r9
  __int16 v11; // r11
  unsigned int v12; // r8d
  unsigned int v13; // edx
  unsigned int *v14; // r14
  char v15; // bl
  __int64 v16; // r8
  int v17; // esi
  __int64 *v18; // r13
  __int64 v19; // r14
  __int16 v20; // ax
  bool v21; // zf
  unsigned __int16 v22; // ax
  unsigned int v23; // edi
  unsigned __int64 v24; // rbx
  unsigned int *v25; // rsi
  __int64 v26; // r9
  unsigned __int64 v27; // rdx
  __int64 Pool2; // rax
  _DWORD *v29; // rbx
  int v30; // ecx
  __int64 v31; // rdi
  unsigned int v32; // r8d
  struct _SmsRedoMarker *v33; // rcx
  __int16 v34; // r9
  __int64 v35; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // r9d
  __int64 v40; // r10
  int v41; // r11d
  __int64 v42; // rax
  unsigned int v43; // eax
  char *v44; // rcx
  int v45; // r14d
  __int64 v46; // r9
  _BYTE *v47; // rsi
  unsigned __int16 *v48; // r12
  int *v49; // rbx
  int v50; // edi
  int v51; // eax
  __int64 v52; // r8
  CmsVolume *v53; // r12
  unsigned int v54; // r10d
  __int64 v55; // rdi
  __int64 v56; // rbx
  unsigned int v57; // esi
  int *v58; // rcx
  int v59; // r9d
  int *v60; // rdx
  int v61; // eax
  char *v62; // rsi
  _DWORD *v63; // r12
  unsigned int v64; // eax
  size_t v65; // r8
  const void *v66; // rdx
  __int64 v67; // rdi
  __int128 v68; // xmm0
  unsigned __int16 v69; // r11
  __int16 v70; // ax
  __int16 v71; // ax
  void *v72; // rcx
  const void *v73; // rdx
  __int64 v74; // rax
  struct _NPAGED_LOOKASIDE_LIST *v75; // rcx
  _DWORD *v76; // rax
  __int64 v77; // [rsp+40h] [rbp-69h]
  unsigned int *v78; // [rsp+60h] [rbp-49h]
  struct _SmsRedoMarker *v79; // [rsp+68h] [rbp-41h] BYREF
  int v80; // [rsp+70h] [rbp-39h] BYREF
  __int16 v81; // [rsp+74h] [rbp-35h]
  __int64 v82; // [rsp+78h] [rbp-31h]
  _DWORD v83[2]; // [rsp+80h] [rbp-29h] BYREF
  unsigned int *v84; // [rsp+88h] [rbp-21h]
  __int64 v85; // [rsp+90h] [rbp-19h] BYREF
  __int64 v86; // [rsp+98h] [rbp-11h]
  int v87; // [rsp+A4h] [rbp-5h]

  v5 = a4[2];
  v85 = 0;
  v86 = 0;
  v8 = a2;
  v79 = 0;
  v9 = *(_WORD *)(v5 + 8);
  v11 = v9 & 0x40;
  if ( (v9 & 0x40) != 0 )
    v12 = *(unsigned __int16 *)(v5 + 10);
  else
    v12 = *(_DWORD *)(v5 + 12);
  v13 = a5;
  v14 = (unsigned int *)(a3 + 16);
  v78 = (unsigned int *)(a3 + 16);
  if ( a5 )
    goto LABEL_4;
  if ( *v14 < v12 )
  {
    v78 = (unsigned int *)(a3 + 16);
LABEL_4:
    v15 = 1;
    goto LABEL_5;
  }
  v15 = 0;
LABEL_5:
  if ( a5 + *v14 > v12 )
    return 3221225859LL;
  v16 = 12;
  v17 = 1;
  if ( (*((_BYTE *)this + 15) & 0x40) == 0 )
  {
    v31 = *(_QWORD *)(v8 + 416);
    v32 = 0;
    v33 = *(struct _SmsRedoMarker **)(v31 + 8);
    v83[0] = 0;
    v84 = 0;
    if ( !v33 )
      v33 = (struct _SmsRedoMarker *)(v31 + 8);
    v79 = v33;
    if ( a5 )
    {
      v32 = 1;
      v83[1] = v87;
      v84 = &a5;
      v83[0] = 4;
    }
    v34 = v9 & 3;
    if ( v11 )
    {
      v35 = v5 + 12;
      v80 = 12;
    }
    else
    {
      v34 |= 4u;
      v80 = *(unsigned __int16 *)(v5 + 6);
      v35 = v5 + *(unsigned __int16 *)(v5 + 4);
    }
    v82 = v35;
    v81 = v34;
    if ( !MsDisableRedoLogging && (*(_QWORD *)v8 & 0x2000000000LL) == 0 && (*(_QWORD *)v8 & 0x20) == 0 )
    {
      v74 = *(_QWORD *)(v8 + 8);
      if ( !v74 || (*(_DWORD *)(v74 + 3396) & 0x400001) == 0 )
      {
        v45 = CmsTxMemLog::AddRedoRecord(v31, this, 3u, &v80, v14, (__int64)v83, v32, 0, v77, 0, 0);
        if ( CmsBPlusTable::HasGlobalBindingSemantics(this) )
        {
          *(_QWORD *)(v8 + 112) = this;
          *(_QWORD *)v8 |= 0x80000000000uLL;
        }
        if ( v45 < 0 )
          goto LABEL_111;
        v13 = a5;
        v14 = v78;
      }
    }
    v16 = 12;
  }
  v18 = 0;
  if ( v15 && (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) == 0 )
  {
    v18 = &v85;
    v85 = v13;
    v86 = *v14;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 && !*(_BYTE *)(a4[1] + 12) )
    v17 = 2;
  v19 = a4[2];
  v20 = *(_WORD *)(v19 + 8) & 0x40;
  if ( v18 )
  {
    v21 = v20 == 0;
    v22 = 12;
    if ( v21 )
      v22 = *(_WORD *)(v19 + 6);
    v23 = *((_DWORD *)v18 + 2) + ((v22 + 7) & 0xFFFFFFF8);
  }
  else if ( v20 )
  {
    v23 = v17 * ((*(unsigned __int16 *)(v19 + 10) + 7) & 0xFFFFFFF8);
  }
  else
  {
    v23 = v17 * *(_DWORD *)v19;
  }
  if ( (*(_DWORD *)a2 & 0x1000LL) == 0 )
  {
    v24 = ((v23 + 47) & 0xFFFFFFF8) + 88;
    v25 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v24 > *v25 )
    {
      v25 = 0;
      v27 = v24 + 16;
      goto LABEL_16;
    }
    if ( !*((_BYTE *)v25 + 8) )
    {
      if ( (int)*((_QWORD *)v25 + 11) > (int)HIDWORD(*((_QWORD *)v25 + 11)) )
      {
        v30 = _InterlockedDecrement((volatile signed __int32 *)v25 + 22);
        if ( v30 >= (int)v25[23] && v30 >= 0 )
        {
          v76 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25 + 4);
          goto LABEL_75;
        }
        _InterlockedIncrement((volatile signed __int32 *)v25 + 22);
      }
LABEL_26:
      v27 = v25[1];
LABEL_16:
      Pool2 = ExAllocatePool2(66, v27, 1766871885, v26);
      v29 = (_DWORD *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
        goto LABEL_77;
      goto LABEL_76;
    }
    v75 = (struct _NPAGED_LOOKASIDE_LIST *)(v25 + 16);
    if ( *((_BYTE *)v25 + 9) )
      v76 = ExAllocateFromNPagedLookasideList(v75);
    else
      v76 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v75);
LABEL_75:
    v29 = v76;
    if ( v76 )
    {
LABEL_76:
      *(_QWORD *)v29 = v25;
      v29 += 4;
LABEL_77:
      if ( v29 )
      {
        v29[4] = 7;
        v29[3] = v23 + 40;
        v29[2] = v23 + 40;
        *((_QWORD *)v29 + 5) = this;
        *((_WORD *)v29 + 10) = 0;
        *((_OWORD *)v29 + 3) = 0;
        *((_OWORD *)v29 + 4) = 0;
        *((_QWORD *)v29 + 10) = 0;
        v29[8] = 0;
        if ( v23 == -40 )
        {
          *((_QWORD *)v29 + 3) = 0;
          v62 = 0;
        }
        else
        {
          *((_QWORD *)v29 + 3) = v29 + 22;
          memset(v29 + 22, 0, v23 + 40);
          v62 = (char *)*((_QWORD *)v29 + 3);
        }
        v63 = v62 + 20;
        if ( v18 )
        {
          v68 = *(_OWORD *)v18;
          v62[16] = 1;
          v69 = 12;
          *(_OWORD *)v62 = v68;
          *((_WORD *)v62 + 14) = *(_WORD *)(v19 + 8);
          *v63 = v23 + 16;
          v70 = 12;
          *((_WORD *)v62 + 12) = 16;
          if ( (*(_BYTE *)(v19 + 8) & 0x40) == 0 )
            v70 = *(_WORD *)(v19 + 6);
          *((_WORD *)v62 + 13) = v70;
          v71 = 12;
          if ( (*(_BYTE *)(v19 + 8) & 0x40) == 0 )
            v71 = *(_WORD *)(v19 + 6);
          v72 = v62 + 32;
          *((_WORD *)v62 + 15) = (v71 + 23) & 0xFFF8;
          *((_DWORD *)v62 + 8) = *((_DWORD *)v18 + 2);
          if ( (*(_BYTE *)(v19 + 8) & 0x40) != 0 )
          {
            v73 = (const void *)(v19 + 12);
          }
          else
          {
            v69 = *(_WORD *)(v19 + 6);
            v73 = (const void *)(v19 + *(unsigned __int16 *)(v19 + 4));
          }
          if ( (v62[28] & 0x40) == 0 )
            v72 = v62 + 36;
          memmove(v72, v73, v69);
          if ( (*(_BYTE *)(v19 + 8) & 0x40) == 0 )
            v19 += *(unsigned __int16 *)(v19 + 10);
          if ( (v62[28] & 0x40) == 0 )
            v63 = (_DWORD *)((char *)v63 + *((unsigned __int16 *)v62 + 15));
          v65 = v18[1];
          v66 = (const void *)(v19 + *v18);
        }
        else
        {
          *(_QWORD *)v62 = 0;
          *((_QWORD *)v62 + 1) = 0;
          v62[16] = 0;
          if ( (*(_BYTE *)(v19 + 8) & 0x40) != 0 )
            v64 = (*(unsigned __int16 *)(v19 + 10) + 7) & 0xFFFFFFF8;
          else
            v64 = *(_DWORD *)v19;
          v65 = v64;
          v66 = (const void *)v19;
        }
        memmove(v63, v66, v65);
        v29[2] = v23 + 40;
        *((_QWORD *)v29 + 5) = this;
        v29[8] = 0;
        v67 = *a4;
        _InterlockedIncrement((volatile signed __int32 *)(*a4 + 380));
        v8 = a2;
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v67 + 560) )
          ++*(_DWORD *)(v67 + 384);
        else
          SmsPageLatch::AcquireShared((SmsPageLatch *)(v67 + 560), (struct CmsTransactionContext *)a2, 1);
        if ( *(char *)(*(_QWORD *)(v67 + 96) + 14LL) >= 0 )
          ++*(_DWORD *)(a2 + 196);
        ++*(_DWORD *)(v67 + 388);
        v37 = a4[1];
        v38 = a4[2];
        v39 = *((_DWORD *)a4 + 6);
        v40 = a4[4];
        v41 = *((_DWORD *)a4 + 7);
        if ( *((_QWORD *)v29 + 6) && (_BYTE)KdDebuggerEnabled )
          __debugbreak();
        *((_QWORD *)v29 + 6) = *a4;
        *((_QWORD *)v29 + 7) = v37;
        *((_QWORD *)v29 + 8) = v38;
        v29[18] = v39;
        *((_QWORD *)v29 + 10) = v40;
        v29[19] = v41;
        v42 = *a4;
        if ( *a4 && (!*(_BYTE *)(v42 + 392) && *(CmsBPlusTable **)(v42 + 96) == this || !*((_BYTE *)this + 212)) )
          *((_BYTE *)v29 + 20) |= 1u;
        v43 = v29[2];
        if ( v43 )
        {
          v44 = (char *)*((_QWORD *)v29 + 3);
          if ( v62 )
          {
            if ( v62 != v44 )
              memmove(v44, v62, v43);
          }
          else
          {
            memset(v44, 0, (unsigned int)v29[2]);
          }
        }
        v45 = 0;
        *(_QWORD *)v29 = *(_QWORD *)(a2 + 144);
        *(_QWORD *)(a2 + 144) = v29;
        v46 = a4[1] + *(unsigned __int16 *)(a4[1] + *(unsigned int *)(a4[1] + 16) + 4LL * *((unsigned int *)a4 + 6));
        v47 = (_BYTE *)(v46 + 8);
        v48 = (unsigned __int16 *)(v46 + 10);
        v49 = (int *)(v46 + 12);
        if ( (*(_BYTE *)(v46 + 8) & 0x40) != 0 )
        {
          v50 = *v48;
        }
        else
        {
          v50 = *v49;
          v46 += *v48;
        }
        memmove((void *)(v46 + a5), *(const void **)(a3 + 24), *v78);
        if ( (*v47 & 0x40) != 0 )
          v51 = *v48;
        else
          v51 = *v49;
        if ( v51 != v50 )
          MsUnsupportedOperationBugCheck("Calling UpdateSimple with a mismatch DataLength row!");
        goto LABEL_54;
      }
      v8 = a2;
      goto LABEL_110;
    }
    goto LABEL_26;
  }
  if ( (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v8 = a2;
  LOBYTE(v16) = 1;
  CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, v16);
LABEL_110:
  v45 = -1073741670;
LABEL_111:
  CmsTxMemLog::DiscardPendingRecordsFrom(*(CmsTxMemLog **)(v8 + 416), &v79);
LABEL_54:
  v52 = *a4;
  if ( !*a4 )
    return (unsigned int)v45;
  v53 = *(CmsVolume **)(v8 + 8);
  v54 = 3;
  do
  {
    while ( 1 )
    {
      v55 = *(_QWORD *)(v52 + 304);
      v56 = 0;
      v57 = v54;
      if ( !v55 )
        goto LABEL_58;
      v58 = (int *)(v52 + 312);
      if ( (v54 & 1) == 0 )
        break;
      v59 = *v58;
      if ( *(_DWORD *)(v52 + 384) != *v58 )
        break;
      v60 = (int *)(v52 + 316);
      v56 = *(_QWORD *)(v52 + 304);
      if ( (v54 & 4) == 0 )
        goto LABEL_73;
      v61 = *v60;
      if ( *(_DWORD *)(v52 + 388) != *v60 )
      {
        v57 = v54 & 0xFFFFFFFB;
        goto LABEL_73;
      }
LABEL_134:
      *v60 = v61 - 1;
LABEL_73:
      *v58 = v59 - 1;
      if ( v59 != 1 )
        goto LABEL_58;
      *(_QWORD *)(v52 + 304) = 0;
      CmsVolume::UnpinInternal(v53, (struct CmsTransactionCore *)v8, (struct SmsPage *)v52, v54);
      v52 = v55;
      v54 = v57;
    }
    if ( (v54 & 4) != 0 )
    {
      v60 = (int *)(v52 + 316);
      v61 = *(_DWORD *)(v52 + 316);
      if ( *(_DWORD *)(v52 + 388) == v61 )
      {
        v59 = *v58;
        v56 = *(_QWORD *)(v52 + 304);
        goto LABEL_134;
      }
    }
LABEL_58:
    CmsVolume::UnpinInternal(v53, (struct CmsTransactionCore *)v8, (struct SmsPage *)v52, v54);
    v52 = v56;
    v54 = v57;
  }
  while ( v56 );
  *a4 = 0;
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x140091570  mov     [rsp-8+arg_10], r8
0x140091575  mov     [rsp-8+arg_8], rdx
0x14009157a  mov     [rsp-8+arg_0], rcx
0x14009157f  push    rbp
0x140091580  push    rbx
0x140091581  push    r12
0x140091583  push    r13
0x140091585  push    r14
0x140091587  push    r15
0x140091589  lea     rbp, [rsp-1Fh]
0x14009158e  sub     rsp, 0C8h
0x140091595  mov     r10, [r9+10h]
0x140091599  xor     eax, eax
0x14009159b  mov     r15, r9
0x14009159e  mov     [rbp+47h+var_60], rax
0x1400915a2  mov     rbx, r8
0x1400915a5  mov     [rbp+47h+var_58], rax
0x1400915a9  mov     r13, rdx
0x1400915ac  mov     [rbp+47h+var_88], rax
0x1400915b0  movzx   r9d, word ptr [r10+8]
0x1400915b5  mov     r12, rcx
0x1400915b8  movzx   r11d, r9w
0x1400915bc  and     r11w, 40h
0x1400915c1  jnz     loc_140091984
0x1400915c7  mov     r8d, [r10+0Ch]
0x1400915cb  mov     edx, [rbp+47h+arg_20]
0x1400915ce  lea     r14, [rbx+10h]
0x1400915d2  mov     [rbp+47h+var_90], r14
0x1400915d6  test    edx, edx
0x1400915d8  jz      loc_1400916F3
0x1400915de  mov     bl, 1
0x1400915e0  mov     ecx, [r14]
0x1400915e3  add     ecx, edx
0x1400915e5  cmp     ecx, r8d
0x1400915e8  ja      loc_1400917C7
0x1400915ee  test    byte ptr [r12+0Fh], 40h
0x1400915f4  mov     r8d, 0Ch
0x1400915fa  mov     [rsp+0F0h+var_30], rsi
0x140091602  mov     esi, 1
0x140091607  mov     [rsp+0F0h+var_38], rdi
0x14009160f  jz      loc_140091756
0x140091615  xor     r13d, r13d
0x140091618  test    bl, bl
0x14009161a  jnz     loc_140091CBD
0x140091620  mov     rax, [r12+18h]
0x140091625  mov     ecx, [rax+2Ch]
0x140091628  test    cl, 2
0x14009162b  jnz     loc_140091CE4
0x140091631  mov     r14, [r15+10h]
0x140091635  movzx   eax, word ptr [r14+8]
0x14009163a  and     ax, 40h
0x14009163e  test    r13, r13
0x140091641  jz      loc_1400916E3
0x140091647  test    ax, ax
0x14009164a  movzx   eax, r8w
0x14009164e  jnz     short loc_140091655
0x140091650  movzx   eax, word ptr [r14+6]
0x140091655  movzx   edi, ax
0x140091658  add     edi, 7
0x14009165b  and     edi, 0FFFFFFF8h
0x14009165e  add     edi, [r13+8]
0x140091662  mov     rax, [rbp+47h+arg_8]
0x140091666  mov     eax, [rax]
0x140091668  bt      rax, 0Ch
0x14009166d  jb      loc_140091C4A
0x140091673  lea     eax, [rdi+28h]
0x140091676  xor     ecx, ecx; ProcNumber
0x140091678  lea     ebx, [rax+7]
0x14009167b  mov     [rbp+47h+arg_18], eax
0x14009167e  and     ebx, 0FFFFFFF8h
0x140091681  add     ebx, 58h ; 'X'
0x140091684  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009168b  nop     dword ptr [rax+rax+00h]
0x140091690  xor     edx, edx
0x140091692  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140091698  lea     rsi, [rdx+rdx*2]
0x14009169c  shl     rsi, 6
0x1400916a0  add     rsi, cs:qword_140269410
0x1400916a7  mov     eax, [rsi]
0x1400916a9  cmp     rbx, rax
0x1400916ac  jbe     short loc_140091703
0x1400916ae  xor     esi, esi
0x1400916b0  lea     rdx, [rbx+10h]
0x1400916b4  mov     ecx, 42h ; 'B'
0x1400916b9  mov     r8d, 6950534Dh
0x1400916bf  call    cs:__imp_ExAllocatePool2
0x1400916c6  nop     dword ptr [rax+rax+00h]
0x1400916cb  mov     rbx, rax
0x1400916ce  test    al, 0Fh
0x1400916d0  jz      loc_140201918
0x1400916d6  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400916dd  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400916e3  test    ax, ax
0x1400916e6  jnz     short loc_140091743
0x1400916e8  mov     edi, [r14]
0x1400916eb  imul    edi, esi
0x1400916ee  jmp     loc_140091662
0x1400916f3  cmp     [r14], r8d
0x1400916f6  jb      loc_1400919CF
0x1400916fc  xor     bl, bl
0x1400916fe  jmp     loc_1400915E0
0x140091703  cmp     byte ptr [rsi+8], 0
0x140091707  jnz     loc_140091D02
0x14009170d  mov     rcx, [rsi+58h]
0x140091711  mov     rax, rcx
0x140091714  shr     rax, 20h
0x140091718  cmp     ecx, eax
0x14009171a  jle     short loc_14009173B
0x14009171c  nop
0x14009171d  mov     ecx, 0FFFFFFFFh
0x140091722  lock xadd [rsi+58h], ecx
0x140091727  nop
0x140091728  dec     ecx
0x14009172a  mov     eax, [rsi+5Ch]
0x14009172d  cmp     ecx, eax
0x14009172f  jge     loc_140091D21
0x140091735  nop
0x140091736  lock inc dword ptr [rsi+58h]
0x14009173a  nop
0x14009173b  mov     edx, [rsi+4]
0x14009173e  jmp     loc_1400916B4
0x140091743  movzx   edi, word ptr [r14+0Ah]
0x140091748  add     edi, 7
0x14009174b  and     edi, 0FFFFFFF8h
0x14009174e  imul    edi, esi
0x140091751  jmp     loc_140091662
0x140091756  mov     rdi, [r13+1A0h]
0x14009175d  mov     r8d, eax
0x140091760  mov     rcx, [rdi+8]
0x140091764  test    rcx, rcx
0x140091767  mov     [rbp+47h+var_70], eax
0x14009176a  mov     [rbp+47h+var_68], rax
0x14009176e  lea     rax, [rdi+8]
0x140091772  cmovz   rcx, rax
0x140091776  mov     [rbp+47h+var_88], rcx
0x14009177a  test    edx, edx
0x14009177c  jnz     loc_140091CA0
0x140091782  and     r9w, 3
0x140091787  test    r11w, r11w
0x14009178b  jnz     loc_1400919D8
0x140091791  movzx   eax, word ptr [r10+6]
0x140091796  or      r9w, 4
0x14009179b  mov     [rbp+47h+var_80], eax
0x14009179e  movzx   eax, word ptr [r10+4]
0x1400917a3  add     rax, r10
0x1400917a6  cmp     cs:?MsDisableRedoLogging@@3EA, 0; uchar MsDisableRedoLogging
0x1400917ad  mov     [rbp+47h+var_78], rax
0x1400917b1  mov     [rbp+47h+var_7C], r9w
0x1400917b6  jz      loc_140091C11
0x1400917bc  mov     r8d, 0Ch
0x1400917c2  jmp     loc_140091615
0x1400917c7  mov     eax, 0C0000183h
0x1400917cc  add     rsp, 0C8h
0x1400917d3  pop     r15
0x1400917d5  pop     r14
0x1400917d7  pop     r13
0x1400917d9  pop     r12
0x1400917db  pop     rbx
0x1400917dc  pop     rbp
0x1400917dd  retn
0x1400917df  inc     dword ptr [rdi+180h]
0x1400917e5  mov     rax, [rdi+60h]
0x1400917e9  cmp     byte ptr [rax+0Eh], 0
0x1400917ed  jl      short loc_1400917F6
0x1400917ef  inc     dword ptr [r13+0C4h]
0x1400917f6  inc     dword ptr [rdi+184h]
0x1400917fc  cmp     qword ptr [rbx+30h], 0
0x140091801  mov     rcx, [r15]
0x140091804  mov     rdx, [r15+8]
0x140091808  mov     r8, [r15+10h]
0x14009180c  mov     r9d, [r15+18h]
0x140091810  mov     r10, [r15+20h]
0x140091814  mov     r11d, [r15+1Ch]
0x140091818  jnz     loc_140091C8A
0x14009181e  mov     [rbx+30h], rcx
0x140091822  mov     [rbx+38h], rdx
0x140091826  mov     [rbx+40h], r8
0x14009182a  mov     [rbx+48h], r9d
0x14009182e  mov     [rbx+50h], r10
0x140091832  mov     [rbx+4Ch], r11d
0x140091836  mov     rax, [r15]
0x140091839  test    rax, rax
0x14009183c  jz      short loc_140091859
0x14009183e  cmp     byte ptr [rax+188h], 0
0x140091845  jnz     loc_14009195C
0x14009184b  cmp     [rax+60h], r12
0x14009184f  jnz     loc_14009195C
0x140091855  or      byte ptr [rbx+14h], 1
0x140091859  mov     eax, [rbx+8]
0x14009185c  test    eax, eax
0x14009185e  jz      short loc_14009187D
0x140091860  mov     rcx, [rbx+18h]; void *
0x140091864  test    rsi, rsi
0x140091867  jz      loc_140091D47
0x14009186d  cmp     rsi, rcx
0x140091870  jz      short loc_14009187D
0x140091872  mov     r8d, eax; Size
0x140091875  mov     rdx, rsi; Src
0x140091878  call    memmove
0x14009187d  mov     rax, [r13+90h]
0x140091884  xor     r14d, r14d
0x140091887  mov     [rbx], rax
0x14009188a  mov     [r13+90h], rbx
0x140091891  mov     rdx, [r15+8]
0x140091895  mov     ecx, [r15+18h]
0x140091899  mov     eax, [rdx+10h]
0x14009189c  add     rax, rdx
0x14009189f  movzx   r9d, word ptr [rax+rcx*4]
0x1400918a4  add     r9, rdx
0x1400918a7  test    byte ptr [r9+8], 40h
0x1400918ac  lea     rsi, [r9+8]
0x1400918b0  lea     r12, [r9+0Ah]
0x1400918b4  lea     rbx, [r9+0Ch]
0x1400918b8  jnz     loc_140091970
0x1400918be  movzx   eax, word ptr [r12]
0x1400918c3  mov     edi, [rbx]
0x1400918c5  add     r9, rax
0x1400918c8  mov     rax, [rbp+47h+var_90]
0x1400918cc  mov     ecx, [rbp+47h+arg_20]
0x1400918cf  mov     rdx, [rbp+47h+arg_10]
0x1400918d3  add     rcx, r9; void *
0x1400918d6  mov     r8d, [rax]; Size
0x1400918d9  mov     rdx, [rdx+18h]; Src
0x1400918dd  call    memmove
0x1400918e2  test    byte ptr [rsi], 40h
0x1400918e5  jnz     loc_14009197A
0x1400918eb  mov     eax, [rbx]
0x1400918ed  cmp     eax, edi
0x1400918ef  jnz     loc_140091D56
0x1400918f5  mov     r8, [r15]; struct SmsPage *
0x1400918f8  test    r8, r8
0x1400918fb  jnz     short loc_140091923
0x1400918fd  mov     rsi, [rsp+0F0h+var_30]
0x140091905  mov     eax, r14d
0x140091908  mov     rdi, [rsp+0F0h+var_38]
0x140091910  add     rsp, 0C8h
0x140091917  pop     r15
0x140091919  pop     r14
0x14009191b  pop     r13
0x14009191d  pop     r12
0x14009191f  pop     rbx
0x140091920  pop     rbp
0x140091921  retn
0x140091923  mov     r12, [r13+8]
0x140091927  mov     r10d, 3
0x14009192d  mov     rdi, [r8+130h]
0x140091934  xor     ebx, ebx
0x140091936  mov     esi, r10d
0x140091939  test    rdi, rdi
0x14009193c  jnz     short loc_14009198E
0x14009193e  mov     r9d, r10d; unsigned int
0x140091941  mov     rdx, r13; struct CmsTransactionCore *
0x140091944  mov     rcx, r12; this
0x140091947  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x14009194c  mov     r8, rbx
0x14009194f  mov     r10d, esi
0x140091952  test    rbx, rbx
0x140091955  jnz     short loc_14009192D
0x140091957  mov     [r15], rbx
0x14009195a  jmp     short loc_1400918FD
0x14009195c  cmp     byte ptr [r12+0D4h], 0
0x140091965  jz      loc_140091855
0x14009196b  jmp     loc_140091859
0x140091970  movzx   edi, word ptr [r12]
0x140091975  jmp     loc_1400918C8
0x14009197a  movzx   eax, word ptr [r12]
0x14009197f  jmp     loc_1400918ED
0x140091984  movzx   r8d, word ptr [r10+0Ah]
0x140091989  jmp     loc_1400915CB
0x14009198e  lea     rcx, [r8+138h]
0x140091995  test    r10b, 1
0x140091999  jz      short loc_1400919A7
0x14009199b  mov     r9d, [rcx]
0x14009199e  cmp     [r8+180h], r9d
0x1400919a5  jz      short loc_1400919EB
0x1400919a7  bt      r10d, 2
0x1400919ac  jnb     short loc_14009193E
0x1400919ae  lea     rdx, [r8+13Ch]
0x1400919b5  mov     eax, [rdx]
0x1400919b7  cmp     [r8+184h], eax
0x1400919be  jnz     loc_14009193E
0x1400919c4  mov     r9d, [rcx]
0x1400919c7  mov     rbx, rdi
0x1400919ca  jmp     loc_140201926
0x1400919cf  mov     [rbp+47h+var_90], r14
0x1400919d3  jmp     loc_1400915DE
0x1400919d8  mov     r11d, 0Ch
0x1400919de  lea     rax, [r10+0Ch]
0x1400919e2  mov     [rbp+47h+var_80], r11d
0x1400919e6  jmp     loc_1400917A6
0x1400919eb  lea     rdx, [r8+13Ch]
0x1400919f2  mov     rbx, rdi
0x1400919f5  bt      r10d, 2
0x1400919fa  jb      loc_140091D63
0x140091a00  lea     eax, [r9-1]
0x140091a04  mov     [rcx], eax
0x140091a06  test    eax, eax
0x140091a08  jnz     loc_14009193E
0x140091a0e  mov     r9d, r10d; unsigned int
0x140091a11  mov     qword ptr [r8+130h], 0
  ... truncated ...
```
