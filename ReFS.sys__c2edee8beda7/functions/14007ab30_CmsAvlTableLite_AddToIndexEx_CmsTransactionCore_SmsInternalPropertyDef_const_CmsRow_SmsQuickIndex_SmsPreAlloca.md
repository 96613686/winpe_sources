# CmsAvlTableLite::AddToIndexEx(CmsTransactionCore *,SmsInternalPropertyDef const *,_CmsRow *,_SmsQuickIndex *,_SmsPreAllocatedRow *)

- ea: `0x14007ab30`
- end: `0x14007b28b`
- name: `?AddToIndexEx@CmsAvlTableLite@@QEAAJPEAVCmsTransactionCore@@PEBUSmsInternalPropertyDef@@PEAU_CmsRow@@PEAU_SmsQuickIndex@@PEAU_SmsPreAllocatedRow@@@Z`
- size: `1883`
- prototype: `__int64 __fastcall(CmsAvlTableLite *__hidden this, struct CmsTransactionCore *, const struct SmsInternalPropertyDef *, struct _CmsRow *, struct _SmsQuickIndex *, struct _SmsPreAllocatedRow *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140049760`
- `0x14007a200`
- `0x140094d80`
- `0x14016996c`

## callees

- `0x14004b8d0`
- `0x14004c580`
- `0x14007aa30`
- `0x14007ab30`
- `0x1400ceda0`
- `0x1401f40a0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b159`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b191`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b159`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b191`
- `ntoskrnl!ExAllocatePool2` at `0x14007aec7`
- `ntoskrnl!ExAllocatePool2` at `0x14007af91`
- `ntoskrnl!ExAllocatePool2` at `0x14007b008`
- `ntoskrnl!ExAllocatePool2` at `0x14007aec7`
- `ntoskrnl!ExAllocatePool2` at `0x14007af91`
- `ntoskrnl!ExAllocatePool2` at `0x14007b008`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007ae85`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007af5f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007ae85`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007af5f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff7ae`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff7c0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff7ae`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff7c0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007b173`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007b1ac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007b173`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007b1ac`

## string_xrefs

- `0x1401ff7d2`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAvlTableLite::AddToIndexEx(
        CmsAvlTableLite *this,
        struct CmsTransactionCore *a2,
        const struct SmsInternalPropertyDef *a3,
        unsigned __int64 a4,
        struct _SmsQuickIndex *a5,
        struct _RTL_AVL_ENTRY **a6)
{
  struct _SmsPreAllocatedRow *v6; // rsi
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r15
  CmsAvlTableLite *v11; // r13
  __int16 v12; // r12
  struct _RTL_AVL_ENTRY *v13; // r15
  unsigned int v14; // r14d
  int v15; // r8d
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned __int8 v18; // dl
  char *v19; // rcx
  char *v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  struct _RTL_AVL_ENTRY **v23; // rdx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  struct CmsTransactionCore *v27; // rdx
  int v28; // eax
  _QWORD *v30; // rsi
  _OWORD *v31; // rax
  unsigned __int64 v32; // rdx
  unsigned __int64 *v33; // rax
  int v34; // r13d
  unsigned int v35; // eax
  unsigned __int64 v36; // rsi
  __int64 v37; // r9
  unsigned int *v38; // r13
  unsigned __int64 v39; // rdx
  __int64 Pool2; // rax
  _WORD *v41; // r14
  unsigned __int64 v42; // rdx
  unsigned __int64 *v43; // rax
  __int64 v44; // r9
  __int64 v45; // r12
  unsigned __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // ecx
  int v49; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v50; // rcx
  _WORD *v51; // rax
  struct _NPAGED_LOOKASIDE_LIST *v52; // rcx
  _WORD *v53; // rax
  int NodeOrParentIn; // eax
  unsigned __int64 i; // rdx
  bool v56; // zf
  char v57; // cl
  char v58; // al
  _QWORD v59[9]; // [rsp+30h] [rbp-48h] BYREF
  int v61; // [rsp+98h] [rbp+20h]
  __int16 v62; // [rsp+98h] [rbp+20h]
  __int64 v63; // [rsp+98h] [rbp+20h]
  unsigned __int8 v64; // [rsp+A8h] [rbp+30h]
  struct _SmsPreAllocatedRow *v65; // [rsp+A8h] [rbp+30h]

  v6 = (struct _SmsPreAllocatedRow *)a6;
  v7 = 0;
  v59[0] = 0;
  v8 = a4;
  v11 = this;
  v12 = 0x8000;
  if ( a6 )
  {
    v13 = a6[4];
    v14 = 0;
    LOBYTE(a4) = 0;
    goto LABEL_3;
  }
  v34 = *(_DWORD *)(a4 + 16);
  v62 = v34;
  v65 = (struct _SmsPreAllocatedRow *)*(unsigned __int8 *)a4;
  v35 = ((v34 + 7) & 0xFFFFFFF8) + 32;
  v36 = v35;
  if ( v35 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v35 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v38 = (unsigned int *)(qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v36 > *v38 )
      {
        v38 = 0;
        v39 = v36 + 16;
        goto LABEL_64;
      }
      if ( !*((_BYTE *)v38 + 8) )
      {
        if ( (int)*((_QWORD *)v38 + 11) > (int)HIDWORD(*((_QWORD *)v38 + 11)) )
        {
          v48 = _InterlockedDecrement((volatile signed __int32 *)v38 + 22);
          if ( v48 >= (int)v38[23] && v48 >= 0 )
          {
            v51 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v38 + 4);
            goto LABEL_100;
          }
          _InterlockedIncrement((volatile signed __int32 *)v38 + 22);
        }
LABEL_87:
        v39 = v38[1];
LABEL_64:
        Pool2 = ExAllocatePool2(66, v39, 1766871885, v37);
        v41 = (_WORD *)Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_102:
            LOWORD(v34) = v62;
            v12 = 0x2000;
            goto LABEL_103;
          }
LABEL_101:
          *(_QWORD *)v41 = v38;
          v41 += 8;
          goto LABEL_102;
        }
LABEL_130:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v50 = (struct _NPAGED_LOOKASIDE_LIST *)(v38 + 16);
      if ( *((_BYTE *)v38 + 9) )
        v51 = ExAllocateFromNPagedLookasideList(v50);
      else
        v51 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v50);
LABEL_100:
      v41 = v51;
      if ( v51 )
        goto LABEL_101;
      goto LABEL_87;
    }
    KeGetCurrentProcessorNumberEx(0);
    v45 = qword_140269460;
    if ( v36 > *(unsigned int *)qword_140269460 )
    {
      v45 = 0;
      v46 = v36 + 16;
      goto LABEL_80;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v49 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v49 >= *(_DWORD *)(v45 + 92) && v49 >= 0 )
        {
          v53 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v45 + 64));
          goto LABEL_105;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v45 + 88));
      }
LABEL_94:
      v46 = *(unsigned int *)(v45 + 4);
LABEL_80:
      v47 = ExAllocatePool2(66, v46, 1766871885, v44);
      v41 = (_WORD *)v47;
      if ( (v47 & 0xF) != 0 )
        goto LABEL_130;
      if ( !v47 )
      {
LABEL_107:
        v12 = 0x4000;
LABEL_103:
        if ( v41 )
        {
          v63 = (__int64)v41;
          goto LABEL_89;
        }
        return 3221225626LL;
      }
LABEL_106:
      *(_QWORD *)v41 = v45;
      v41 += 8;
      goto LABEL_107;
    }
    v52 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v53 = ExAllocateFromNPagedLookasideList(v52);
    else
      v53 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v52);
LABEL_105:
    v41 = v53;
    if ( v53 )
      goto LABEL_106;
    goto LABEL_94;
  }
  v63 = ExAllocatePool2(66, ((v34 + 7) & 0xFFFFFFF8) + 32, 1766871885, a4);
  v41 = (_WORD *)v63;
  if ( v63 )
  {
LABEL_89:
    v41[14] = 0;
    v6 = (struct _SmsPreAllocatedRow *)v8;
    memmove(v41 + 16, *(const void **)(v8 + 24), *(unsigned int *)(v8 + 16));
    LOBYTE(a4) = 1;
    v13 = (struct _RTL_AVL_ENTRY *)v63;
    *((_BYTE *)v41 + 26) = 32;
    v41[14] |= v12;
    v41[15] = v34;
    v11 = this;
    *((_BYTE *)v41 + 27) = (_BYTE)v65;
    v14 = 0;
LABEL_3:
    v15 = 2;
    v16 = *((unsigned __int8 *)a2 + 96);
    v17 = 5;
    v64 = a4;
    if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
      v17 = 2;
    v61 = 2;
    if ( v16 < v17 )
    {
      v18 = v16 + 1;
      *((_BYTE *)a2 + 96) = v18;
      if ( v18 <= 2u )
        v19 = (char *)a2 - 24;
      else
        v19 = (char *)a2 + 784;
      v20 = &v19[40 * v18];
      *(_QWORD *)v20 = v6;
      *((_WORD *)v20 + 16) = 0;
      *((_QWORD *)v20 + 1) = a3;
      *((_QWORD *)v20 + 2) = *((_QWORD *)a3 + 7);
      LOBYTE(v16) = *((_BYTE *)a2 + 96);
    }
    if ( (_BYTE)a4 )
    {
      if ( (unsigned __int8)v16 <= 2u )
        v21 = (char *)a2 + 9;
      else
        v21 = (char *)a2 + 817;
      v21[40 * (unsigned __int8)v16] = 1;
    }
    v22 = *((unsigned __int8 *)a2 + 96);
    v23 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v22);
    if ( (unsigned __int8)v22 > 2u )
      v23 += 101;
    *v23 = v13;
    if ( a5 && *((_QWORD *)a5 + 1) )
    {
      a4 = *(_QWORD *)a5;
      if ( !*(_QWORD *)a5 )
      {
        v15 = *((_DWORD *)a5 + 4);
        v30 = (_QWORD *)((char *)v11 + 16);
        v61 = v15;
        v7 = *((_QWORD *)a5 + 1);
        goto LABEL_44;
      }
      if ( *((_WORD *)a3 + 2) == 3 )
      {
        if ( !*((_QWORD *)v11 + 2) )
        {
          v15 = 0;
          v61 = 0;
LABEL_25:
          v25 = 0;
          goto LABEL_36;
        }
        v7 = *(_QWORD *)a5;
        v42 = **((_QWORD **)v6 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v43 = v7 ? (unsigned __int64 *)(v7 + *(unsigned __int8 *)(v7 + 26)) : 0LL;
            if ( v42 >= *v43 )
              break;
            if ( !*(_QWORD *)(v7 + 8) )
              goto LABEL_25;
            v7 = *(_QWORD *)(v7 + 8);
          }
          if ( v42 < v43[1] + *v43 )
            break;
          if ( !*(_QWORD *)(v7 + 16) )
          {
            v15 = 3;
            v25 = 0;
            v61 = 3;
            goto LABEL_36;
          }
          v7 = *(_QWORD *)(v7 + 16);
        }
        v15 = 1;
        v25 = v7;
      }
      else
      {
        NodeOrParentIn = FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(
                           (_DWORD)v11,
                           (_DWORD)a2,
                           2,
                           a4,
                           (__int64)v59);
        v7 = v59[0];
        v15 = NodeOrParentIn;
        v25 = v59[0];
        if ( v15 != 1 )
          v25 = 0;
      }
      v61 = v15;
    }
    else
    {
      v24 = *((_QWORD *)v11 + 2);
      if ( *((_WORD *)a3 + 2) == 3 )
      {
        if ( v24 )
        {
          v7 = *((_QWORD *)v11 + 2);
          v32 = **((_QWORD **)v6 + 1);
          while ( 1 )
          {
            while ( 1 )
            {
              v33 = v7 ? (unsigned __int64 *)(v7 + *(unsigned __int8 *)(v7 + 26)) : 0LL;
              if ( v32 >= *v33 )
                break;
              if ( !*(_QWORD *)(v7 + 8) )
                goto LABEL_19;
              v7 = *(_QWORD *)(v7 + 8);
            }
            if ( v32 < v33[1] + *v33 )
              break;
            if ( !*(_QWORD *)(v7 + 16) )
            {
              v15 = 3;
              v25 = 0;
              v61 = 3;
              goto LABEL_37;
            }
            v7 = *(_QWORD *)(v7 + 16);
          }
          v15 = 1;
          v61 = 1;
          v25 = v7;
        }
        else
        {
          v15 = 0;
LABEL_19:
          v61 = v15;
          v25 = 0;
        }
        goto LABEL_37;
      }
      if ( v24 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v26 = *((unsigned __int8 *)a2 + 96);
            v7 = v24;
            v27 = (unsigned __int8)v26 <= 2u
                ? (struct CmsTransactionCore *)((char *)a2 - 24)
                : (struct CmsTransactionCore *)((char *)a2 + 784);
            LODWORD(v59[0]) = *(unsigned __int8 *)(v24 + 27);
            v59[1] = v24 + *(unsigned __int8 *)(v24 + 26);
            WORD2(v59[0]) = 0;
            v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**((_QWORD **)v27 + 5 * v26 + 2) + 8LL))(
                    *((_QWORD *)v27 + 5 * v26 + 2),
                    (__int64)v27 + 40 * v26,
                    v59);
            if ( v28 )
              break;
            v24 = *(_QWORD *)(v7 + 8);
            if ( !v24 )
            {
              v15 = 2;
              goto LABEL_35;
            }
          }
          if ( v28 != 1 )
            break;
          v24 = *(_QWORD *)(v7 + 16);
          if ( !v24 )
          {
            v15 = 3;
            goto LABEL_35;
          }
        }
        v15 = 1;
        v61 = 1;
        v25 = v7;
      }
      else
      {
        v15 = 0;
LABEL_35:
        v61 = v15;
        v25 = 0;
      }
    }
LABEL_36:
    a4 = v64;
LABEL_37:
    if ( v25 )
    {
      if ( a5 )
      {
        *(_QWORD *)a5 = v25;
        *((_QWORD *)a5 + 1) = v25;
        *((_DWORD *)a5 + 4) = 3;
        *((_DWORD *)a5 + 5) = *((_DWORD *)v11 + 10);
      }
      --*((_BYTE *)a2 + 96);
      if ( v13 )
      {
        if ( (_BYTE)a4 )
          CmsAvlTableLite::FreeIndexEntry(v13);
      }
      return (unsigned int)-1073741771;
    }
    v30 = (_QWORD *)((char *)v11 + 16);
LABEL_44:
    ++*((_DWORD *)v11 + 10);
    if ( v15 != 1 )
    {
      v31 = (_OWORD *)((__int64 (__fastcall *)(CmsAvlTableLite *, _QWORD, struct CmsTransactionCore *, unsigned __int64))qword_1402692F0)(
                        v11,
                        0,
                        a2,
                        a4);
      if ( v31 )
      {
        *v31 = 0;
        *(_OWORD *)((char *)v31 + 10) = 0;
        ++*((_DWORD *)v11 + 8);
        if ( v61 )
        {
          if ( v61 == 2 )
            *(_QWORD *)(v7 + 8) = v31;
          else
            *(_QWORD *)(v7 + 16) = v31;
          *(_QWORD *)v31 = v7;
          *((_BYTE *)v11 + 24) = -1;
          for ( i = *(_QWORD *)v31; ; v7 = i )
          {
            v56 = *(_QWORD *)(i + 8) == (_QWORD)v31;
            v57 = -1;
            v58 = *(_BYTE *)(v7 + 24);
            if ( !v56 )
              v57 = 1;
            if ( v58 )
              break;
            i = *(_QWORD *)v7;
            v31 = (_OWORD *)v7;
            *(_BYTE *)(v7 + 24) = v57;
          }
          if ( v58 == v57 )
            RebalanceNode((struct _RTL_AVL_ENTRY *)v7);
          else
            *(_BYTE *)(v7 + 24) = 0;
        }
        else
        {
          *v30 = v31;
          *(_QWORD *)v31 = v11;
        }
      }
    }
    if ( a5 )
    {
      *(_QWORD *)a5 = v13;
      *((_QWORD *)a5 + 1) = v13;
      *((_DWORD *)a5 + 4) = 1;
      *((_DWORD *)a5 + 5) = *((_DWORD *)v11 + 10);
    }
    --*((_BYTE *)a2 + 96);
    return v14;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14007ab30  mov     [rsp+arg_8], rbx
0x14007ab35  mov     [rsp+arg_0], rcx
0x14007ab3a  push    rbp
0x14007ab3b  push    rsi
0x14007ab3c  push    rdi
0x14007ab3d  push    r12
0x14007ab3f  push    r13
0x14007ab41  push    r14
0x14007ab43  push    r15
0x14007ab45  sub     rsp, 40h
0x14007ab49  mov     rsi, [rsp+78h+arg_28]
0x14007ab51  xor     ebx, ebx
0x14007ab53  mov     [rsp+78h+var_48], rbx
0x14007ab58  mov     r15, r9
0x14007ab5b  mov     rbp, r8
0x14007ab5e  mov     rdi, rdx
0x14007ab61  mov     r13, rcx
0x14007ab64  mov     r12d, 8000h
0x14007ab6a  test    rsi, rsi
0x14007ab6d  jz      loc_14007AE48
0x14007ab73  mov     r15, [rsi+20h]
0x14007ab77  xor     r14d, r14d
0x14007ab7a  xor     r9b, r9b
0x14007ab7d  mov     eax, [rdi]
0x14007ab7f  mov     r8d, 2
0x14007ab85  movzx   edx, byte ptr [rdi+60h]
0x14007ab89  test    r12, rax
0x14007ab8c  mov     eax, 5
0x14007ab91  mov     byte ptr [rsp+78h+arg_28], r9b
0x14007ab99  cmovz   eax, r8d
0x14007ab9d  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007aba5  cmp     edx, eax
0x14007aba7  jnb     short loc_14007ABE2
0x14007aba9  inc     dl
0x14007abab  movzx   ecx, dl
0x14007abae  mov     [rdi+60h], cl
0x14007abb1  lea     rax, [rcx+rcx*4]
0x14007abb5  cmp     cl, r8b
0x14007abb8  jbe     loc_14007B1BD
0x14007abbe  lea     rcx, [rdi+310h]
0x14007abc5  lea     rcx, [rcx+rax*8]
0x14007abc9  xor     eax, eax
0x14007abcb  mov     [rcx], rsi
0x14007abce  mov     [rcx+20h], ax
0x14007abd2  mov     [rcx+8], rbp
0x14007abd6  mov     rax, [rbp+38h]
0x14007abda  mov     [rcx+10h], rax
0x14007abde  movzx   edx, byte ptr [rdi+60h]
0x14007abe2  test    r9b, r9b
0x14007abe5  jz      short loc_14007AC05
0x14007abe7  movzx   eax, dl
0x14007abea  lea     rcx, [rax+rax*4]
0x14007abee  cmp     dl, r8b
0x14007abf1  jbe     loc_14007B1C6
0x14007abf7  lea     rax, [rdi+331h]
0x14007abfe  lea     rax, [rax+rcx*8]
0x14007ac02  mov     byte ptr [rax], 1
0x14007ac05  movzx   ecx, byte ptr [rdi+60h]
0x14007ac09  lea     rax, [rcx+rcx*4]
0x14007ac0d  lea     rdx, [rdi+rax*8]
0x14007ac11  cmp     cl, r8b
0x14007ac14  jbe     short loc_14007AC1D
0x14007ac16  add     rdx, 328h
0x14007ac1d  mov     r12, [rsp+78h+arg_20]
0x14007ac25  mov     [rdx], r15
0x14007ac28  test    r12, r12
0x14007ac2b  jnz     short loc_14007AC58
0x14007ac2d  cmp     word ptr [rbp+4], 3
0x14007ac32  mov     ebp, 1
0x14007ac37  mov     rax, [r13+10h]
0x14007ac3b  jnz     short loc_14007AC9B
0x14007ac3d  test    rax, rax
0x14007ac40  jnz     loc_14007ADC2
0x14007ac46  xor     r8d, r8d
0x14007ac49  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007ac51  xor     eax, eax
0x14007ac53  jmp     loc_14007AD32
0x14007ac58  mov     rax, [r12+8]
0x14007ac5d  test    rax, rax
0x14007ac60  jz      short loc_14007AC2D
0x14007ac62  mov     r9, [r12]
0x14007ac66  test    r9, r9
0x14007ac69  jz      loc_14007AE15
0x14007ac6f  cmp     word ptr [rbp+4], 3
0x14007ac74  jnz     loc_14007B1DD
0x14007ac7a  cmp     [r13+10h], rbx
0x14007ac7e  jnz     loc_14007AEF4
0x14007ac84  xor     r8d, r8d
0x14007ac87  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007ac8f  xor     eax, eax
0x14007ac91  mov     ebp, 1
0x14007ac96  jmp     loc_14007AD29
0x14007ac9b  test    rax, rax
0x14007ac9e  jz      loc_14007AEEC
0x14007aca4  movzx   ecx, byte ptr [rdi+60h]
0x14007aca8  mov     rbx, rax
0x14007acab  lea     rax, [rcx+rcx*4]
0x14007acaf  cmp     cl, 2
0x14007acb2  jbe     loc_14007B21E
0x14007acb8  lea     rdx, [rdi+310h]
0x14007acbf  lea     rdx, [rdx+rax*8]
0x14007acc3  movzx   eax, byte ptr [rbx+1Bh]
0x14007acc7  mov     dword ptr [rsp+78h+var_48], eax
0x14007accb  lea     r8, [rsp+78h+var_48]
0x14007acd0  movzx   eax, byte ptr [rbx+1Ah]
0x14007acd4  add     rax, rbx
0x14007acd7  mov     [rsp+78h+var_40], rax
0x14007acdc  xor     eax, eax
0x14007acde  mov     word ptr [rsp+78h+var_48+4], ax
0x14007ace3  mov     rcx, [rdx+10h]
0x14007ace7  mov     rax, [rcx]
0x14007acea  mov     rax, [rax+8]
0x14007acee  call    _guard_dispatch_icall
0x14007acf3  test    eax, eax
0x14007acf5  jnz     short loc_14007AD08
0x14007acf7  mov     rax, [rbx+8]
0x14007acfb  test    rax, rax
0x14007acfe  jnz     short loc_14007ACA4
0x14007ad00  mov     r8d, 2
0x14007ad06  jmp     short loc_14007AD1F
0x14007ad08  cmp     eax, ebp
0x14007ad0a  jnz     loc_14007B0D7
0x14007ad10  mov     rax, [rbx+10h]
0x14007ad14  test    rax, rax
0x14007ad17  jnz     short loc_14007ACA4
0x14007ad19  mov     r8d, 3
0x14007ad1f  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007ad27  xor     eax, eax
0x14007ad29  movzx   r9d, byte ptr [rsp+78h+arg_28]
0x14007ad32  mov     rdx, r13
0x14007ad35  mov     ecx, 10h
0x14007ad3a  test    rax, rax
0x14007ad3d  jz      short loc_14007AD76
0x14007ad3f  test    r12, r12
0x14007ad42  jnz     loc_14007B255
0x14007ad48  dec     byte ptr [rdi+60h]
0x14007ad4b  test    r15, r15
0x14007ad4e  jnz     loc_14007B275
0x14007ad54  mov     r14d, 0C0000035h
0x14007ad5a  mov     eax, r14d
0x14007ad5d  mov     rbx, [rsp+78h+arg_8]
0x14007ad65  add     rsp, 40h
0x14007ad69  pop     r15
0x14007ad6b  pop     r14
0x14007ad6d  pop     r13
0x14007ad6f  pop     r12
0x14007ad71  pop     rdi
0x14007ad72  pop     rsi
0x14007ad73  pop     rbp
0x14007ad74  retn
0x14007ad76  lea     rsi, [rdx+rcx]
0x14007ad7a  inc     dword ptr [r13+28h]
0x14007ad7e  cmp     r8d, 1
0x14007ad82  jz      short loc_14007ADA1
0x14007ad84  mov     rax, cs:qword_1402692F0
0x14007ad8b  mov     r8, rdi
0x14007ad8e  xor     edx, edx
0x14007ad90  mov     rcx, r13
0x14007ad93  call    _guard_dispatch_icall
0x14007ad98  test    rax, rax
0x14007ad9b  jnz     loc_14007B227
0x14007ada1  test    r12, r12
0x14007ada4  jz      short loc_14007ADBD
0x14007ada6  mov     [r12], r15
0x14007adaa  mov     [r12+8], r15
0x14007adaf  mov     [r12+10h], ebp
0x14007adb4  mov     eax, [r13+28h]
0x14007adb8  mov     [r12+14h], eax
0x14007adbd  dec     byte ptr [rdi+60h]
0x14007adc0  jmp     short loc_14007AD5A
0x14007adc2  mov     rbx, rax
0x14007adc5  mov     rax, [rsi+8]
0x14007adc9  mov     rdx, [rax]
0x14007adcc  nop     dword ptr [rax+00h]
0x14007add0  test    rbx, rbx
0x14007add3  jz      loc_14007B0C9
0x14007add9  movzx   eax, byte ptr [rbx+1Ah]
0x14007addd  add     rax, rbx
0x14007ade0  mov     rcx, [rax]
0x14007ade3  cmp     rdx, rcx
0x14007ade6  jb      short loc_14007AE03
0x14007ade8  add     rcx, [rax+8]
0x14007adec  cmp     rdx, rcx
0x14007adef  jb      loc_14007B20C
0x14007adf5  mov     rax, [rbx+10h]
0x14007adf9  test    rax, rax
0x14007adfc  jz      short loc_14007AE33
0x14007adfe  mov     rbx, rax
0x14007ae01  jmp     short loc_14007ADD0
0x14007ae03  mov     rax, [rbx+8]
0x14007ae07  test    rax, rax
0x14007ae0a  jz      loc_14007AC49
0x14007ae10  mov     rbx, rax
0x14007ae13  jmp     short loc_14007ADD0
0x14007ae15  mov     r8d, [r12+10h]
0x14007ae1a  lea     rsi, [r13+10h]
0x14007ae1e  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007ae26  mov     rbx, rax
0x14007ae29  mov     ebp, 1
0x14007ae2e  jmp     loc_14007AD7A
0x14007ae33  mov     r8d, 3
0x14007ae39  xor     eax, eax
0x14007ae3b  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007ae43  jmp     loc_14007AD32
0x14007ae48  mov     r13d, [r9+10h]
0x14007ae4c  movzx   ecx, byte ptr [r9]
0x14007ae50  mov     dword ptr [rsp+78h+arg_18], r13d
0x14007ae58  mov     byte ptr [rsp+78h+arg_28], cl
0x14007ae5f  lea     eax, [r13+7]
0x14007ae63  and     eax, 0FFFFFFF8h
0x14007ae66  add     eax, 20h ; ' '
0x14007ae69  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14007ae6f  mov     esi, eax
0x14007ae71  ja      loc_14007AFFA
0x14007ae77  xor     ecx, ecx; ProcNumber
0x14007ae79  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14007ae7f  ja      loc_14007AF5F
0x14007ae85  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007ae8c  nop     dword ptr [rax+rax+00h]
0x14007ae91  xor     edx, edx
0x14007ae93  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14007ae99  lea     r13, [rdx+rdx*2]
0x14007ae9d  shl     r13, 6
0x14007aea1  add     r13, cs:qword_140269458
0x14007aea8  mov     eax, [r13+0]
0x14007aeac  cmp     rsi, rax
0x14007aeaf  jbe     loc_14007AFB6
0x14007aeb5  xor     r13d, r13d
0x14007aeb8  lea     rdx, [rsi+10h]
0x14007aebc  mov     ecx, 42h ; 'B'
0x14007aec1  mov     r8d, 6950534Dh
0x14007aec7  call    cs:__imp_ExAllocatePool2
0x14007aece  nop     dword ptr [rax+rax+00h]
0x14007aed3  mov     r14, rax
0x14007aed6  test    al, 0Fh
0x14007aed8  jnz     loc_1401FF7D2
0x14007aede  test    rax, rax
0x14007aee1  jz      loc_14007B114
0x14007aee7  jmp     loc_14007B10D
0x14007aeec  xor     r8d, r8d
0x14007aeef  jmp     loc_14007AD1F
0x14007aef4  mov     rax, [rsi+8]
0x14007aef8  mov     rbx, r9
0x14007aefb  mov     rdx, [rax]
0x14007aefe  xchg    ax, ax
0x14007af00  test    rbx, rbx
0x14007af03  jz      loc_14007B0D0
0x14007af09  movzx   eax, byte ptr [rbx+1Ah]
0x14007af0d  add     rax, rbx
0x14007af10  mov     rcx, [rax]
0x14007af13  cmp     rdx, rcx
0x14007af16  jb      short loc_14007AF33
0x14007af18  add     rcx, [rax+8]
0x14007af1c  cmp     rdx, rcx
0x14007af1f  jb      loc_14007B1CF
0x14007af25  mov     rax, [rbx+10h]
0x14007af29  test    rax, rax
0x14007af2c  jz      short loc_14007AF45
0x14007af2e  mov     rbx, rax
0x14007af31  jmp     short loc_14007AF00
0x14007af33  mov     rax, [rbx+8]
0x14007af37  test    rax, rax
0x14007af3a  jz      loc_14007AC8F
0x14007af40  mov     rbx, rax
0x14007af43  jmp     short loc_14007AF00
0x14007af45  mov     r8d, 3
0x14007af4b  xor     eax, eax
0x14007af4d  mov     dword ptr [rsp+78h+arg_18], r8d
0x14007af55  mov     ebp, 1
0x14007af5a  jmp     loc_14007AD29
0x14007af5f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007af66  nop     dword ptr [rax+rax+00h]
0x14007af6b  mov     r12, cs:qword_140269460
0x14007af72  mov     eax, [r12]
0x14007af76  cmp     rsi, rax
0x14007af79  jbe     loc_14007B07F
0x14007af7f  xor     r12d, r12d
0x14007af82  lea     rdx, [rsi+10h]
0x14007af86  mov     ecx, 42h ; 'B'
0x14007af8b  mov     r8d, 6950534Dh
0x14007af91  call    cs:__imp_ExAllocatePool2
0x14007af98  nop     dword ptr [rax+rax+00h]
0x14007af9d  mov     r14, rax
0x14007afa0  test    al, 0Fh
0x14007afa2  jnz     loc_1401FF7D2
0x14007afa8  test    rax, rax
0x14007afab  jz      loc_14007B143
0x14007afb1  jmp     loc_14007B13C
0x14007afb6  cmp     [r13+8], bl
0x14007afba  jnz     loc_14007B14B
0x14007afc0  mov     rcx, [r13+58h]
0x14007afc4  mov     rax, rcx
0x14007afc7  shr     rax, 20h
0x14007afcb  cmp     ecx, eax
0x14007afcd  jle     short loc_14007AFF1
0x14007afcf  nop
0x14007afd0  mov     ecx, 0FFFFFFFFh
0x14007afd5  lock xadd [r13+58h], ecx
0x14007afdb  nop
0x14007afdc  dec     ecx
  ... truncated ...
```
