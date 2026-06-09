# CmsVolumeContainer::UpdateCurrentToInitialAllocationBitmap(CmsTransactionContext *,SmsContainer *,_RANGE const &)

- ea: `0x1401713b0`
- end: `0x1401716fa`
- name: `?UpdateCurrentToInitialAllocationBitmap@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@AEBU_RANGE@@@Z`
- size: `842`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsContainer *, const struct _RANGE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401711d4`

## callees

- `0x140012c34`
- `0x140012ec0`
- `0x14001c620`
- `0x14002dd70`
- `0x14005d060`
- `0x140062090`
- `0x140062470`
- `0x140078ce0`
- `0x140083220`
- `0x140092660`
- `0x140139404`
- `0x1401713b0`

## import_xrefs

- `ntoskrnl!RtlExtractBitMap` at `0x1401715de`
- `ntoskrnl!RtlExtractBitMap` at `0x1401715de`
- `ntoskrnl!RtlCopyBitMap` at `0x14017163d`
- `ntoskrnl!RtlCopyBitMap` at `0x1401716a1`
- `ntoskrnl!RtlCopyBitMap` at `0x14017163d`
- `ntoskrnl!RtlCopyBitMap` at `0x1401716a1`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401714db`
- `ntoskrnl!RtlInitializeBitMap` at `0x140171586`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401715fa`
- `ntoskrnl!RtlInitializeBitMap` at `0x14017168a`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401714db`
- `ntoskrnl!RtlInitializeBitMap` at `0x140171586`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401715fa`
- `ntoskrnl!RtlInitializeBitMap` at `0x14017168a`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::UpdateCurrentToInitialAllocationBitmap(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        struct SmsContainer *a3,
        const struct _RANGE *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r9
  struct SmsUndoRecord *Undo; // rax
  struct SmsUndoRecord *v11; // r15
  int updated; // ebx
  struct CmsTransactionContext *v13; // rdx
  unsigned int v14; // r8d
  char *v16; // r12
  __int64 v17; // rdx
  ULONG *v18; // rdx
  unsigned int v19; // [rsp+20h] [rbp-69h]
  unsigned int v20; // [rsp+20h] [rbp-69h]
  struct CmsRowWithBuffer *v21; // [rsp+40h] [rbp-49h]
  struct _RTL_BITMAP v22; // [rsp+48h] [rbp-41h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+58h] [rbp-31h] BYREF
  struct _RTL_BITMAP v24; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v25[24]; // [rsp+78h] [rbp-11h] BYREF
  __int16 v26; // [rsp+90h] [rbp+7h]
  char v27; // [rsp+92h] [rbp+9h]
  int v28; // [rsp+A0h] [rbp+17h]
  ULONG SizeOfBitMap; // [rsp+F0h] [rbp+67h]
  CmsRowWithBuffer *v30; // [rsp+108h] [rbp+7Fh]

  SizeOfBitMap = *(_DWORD *)(*((_QWORD *)this + 1) + 84LL);
  v21 = CmsTransactionContext::PopRow(a2);
  v30 = CmsTransactionContext::PopRow(a2);
  v22.SizeOfBitMap = *((_DWORD *)a4 + 2) + 7;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  BitMapHeader = 0;
  v24 = 0;
  CmsVolume::BeginTopLevelActionInternal(v22.SizeOfBitMap, a2, v25, 0, 0, 0);
  Undo = (struct SmsUndoRecord *)CmsBPlusTable::AllocateUndo(
                                   *((_QWORD *)this + 9),
                                   v8,
                                   48,
                                   v9,
                                   ((*((_DWORD *)a4 + 2) + 3) & 0xFFFFFFFC) + 40,
                                   0);
  v11 = Undo;
  if ( !Undo )
  {
    updated = -1073741670;
LABEL_3:
    CmsVolume::AbortTopLevelAction(*((CmsVolume **)this + 1), a2, (struct _SmsTopLevelAction *)v25);
    goto LABEL_4;
  }
  v16 = (char *)*((_QWORD *)Undo + 3);
  *(_QWORD *)v16 = a3;
  *(_OWORD *)(v16 + 8) = *(_OWORD *)a4;
  RtlInitializeBitMap((PRTL_BITMAP)(v16 + 24), (PULONG)v16 + 10, *((_DWORD *)a4 + 2));
  updated = CmsRowWithBuffer::NewLength(v21, 0, (SizeOfBitMap >> 3) + 48, 0x10u, v19);
  if ( updated < 0 )
    goto LABEL_3;
  updated = CmsRowWithBuffer::NewLength(v30, 0, v22.SizeOfBitMap >> 3, 0, v20);
  if ( updated < 0 )
    goto LABEL_3;
  v17 = *((_QWORD *)v21 + 3);
  *(_OWORD *)v17 = *((_OWORD *)a3 + 37);
  *(_DWORD *)(v17 + 12) = 3;
  *(_DWORD *)(v17 + 8) = 0;
  *(_BYTE *)(v17 + 16) = 1;
  *(_DWORD *)(v17 + 20) = 0;
  *(_QWORD *)(v17 + 24) = *((_QWORD *)a3 + 74) << ((unsigned __int8)*(_DWORD *)(*((_QWORD *)this + 1) + 80LL) + 1);
  *(_QWORD *)(v17 + 32) = SizeOfBitMap;
  *(_BYTE *)(v17 + 40) = 48;
  RtlInitializeBitMap(&BitMapHeader, (PULONG)(v17 + 48), SizeOfBitMap);
  *(_QWORD *)&v22.SizeOfBitMap = 0;
  v22.Buffer = (PULONG)SizeOfBitMap;
  updated = CmsVolumeContainer::CopyContainerAllocationBitmap(this, a2, a3, 3, &v22, &BitMapHeader);
  if ( updated < 0 )
    goto LABEL_3;
  RtlExtractBitMap(&BitMapHeader, v16 + 24, *(unsigned int *)a4, *((unsigned int *)a4 + 2));
  RtlInitializeBitMap(&v24, *((PULONG *)v30 + 3), *((_DWORD *)a4 + 2));
  updated = CmsVolumeContainer::CopyContainerAllocationBitmap(this, a2, a3, 5, a4, &v24);
  if ( updated < 0 )
    goto LABEL_3;
  RtlCopyBitMap(&v24, &BitMapHeader, *(unsigned int *)a4);
  updated = CmsTable::UpdateRow(*((CmsTable **)this + 9), a2, v21, 0, 0);
  if ( updated < 0 )
    goto LABEL_3;
  v18 = (ULONG *)*((_QWORD *)a3 + 21);
  if ( v18 )
  {
    v22 = 0;
    RtlInitializeBitMap(&v22, v18, SizeOfBitMap);
    RtlCopyBitMap(&v24, &v22, *(unsigned int *)a4);
  }
  CmsVolume::CommitTopLevelAction(*((CmsVolume **)this + 1), a2, (struct _SmsTopLevelAction *)v25, 0);
  CmsBPlusTable::FormatUndoRecord(
    *((CmsBPlusTable **)this + 9),
    a2,
    v11,
    0,
    v16,
    ((unsigned __int64)(*((_QWORD *)a4 + 1) + 3LL) >> 2) + 40,
    0);
  v11 = 0;
LABEL_4:
  CmsBPlusTable::FreeUndoRecord(v11, v13, v14);
  CmsTransactionContext::PushRow(a2, v30);
  CmsTransactionContext::PushRow(a2, v21);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1401713b0  mov     [rsp-8+arg_8], rbx
0x1401713b5  push    rbp
0x1401713b6  push    rsi
0x1401713b7  push    rdi
0x1401713b8  push    r12
0x1401713ba  push    r13
0x1401713bc  push    r14
0x1401713be  push    r15
0x1401713c0  lea     rbp, [rsp-27h]
0x1401713c5  sub     rsp, 0B0h
0x1401713cc  mov     rax, [rcx+8]
0x1401713d0  mov     r14, rcx
0x1401713d3  mov     rcx, rdx; this
0x1401713d6  mov     rsi, r9
0x1401713d9  mov     r13, r8
0x1401713dc  mov     rdi, rdx
0x1401713df  mov     eax, [rax+54h]
0x1401713e2  mov     [rbp+57h+SizeOfBitMap], eax
0x1401713e5  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x1401713ea  mov     rcx, rdi; this
0x1401713ed  mov     [rbp+57h+var_A0], rax
0x1401713f1  mov     rbx, rax
0x1401713f4  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x1401713f9  mov     ecx, [rsi+8]
0x1401713fc  lea     r8, [rbp+57h+var_68]
0x140171400  xor     r12d, r12d
0x140171403  mov     [rbp+57h+arg_18], rax
0x140171407  add     ecx, 7
0x14017140a  mov     byte ptr [rsp+0E0h+var_B8], r12b
0x14017140f  xorps   xmm1, xmm1
0x140171412  mov     [rbp+57h+var_98.SizeOfBitMap], ecx
0x140171415  xorps   xmm0, xmm0
0x140171418  mov     [rbp+57h+var_50], r12w
0x14017141d  xor     r9d, r9d
0x140171420  mov     [rbp+57h+var_4E], r12b
0x140171424  mov     rdx, rdi
0x140171427  mov     [rbp+57h+var_40], r12d
0x14017142b  movups  xmmword ptr [rbp+57h+BitMapHeader.SizeOfBitMap], xmm1
0x14017142f  mov     byte ptr [rsp+0E0h+var_C0], r12b
0x140171434  movups  xmmword ptr [rbp+57h+var_78.SizeOfBitMap], xmm0
0x140171438  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x14017143d  mov     eax, [rsi+8]
0x140171440  lea     r8d, [r12+30h]
0x140171445  mov     rcx, [r14+48h]
0x140171449  add     eax, 3
0x14017144c  and     eax, 0FFFFFFFCh
0x14017144f  mov     [rsp+0E0h+var_B8], r12d
0x140171454  add     eax, 28h ; '('
0x140171457  mov     dword ptr [rsp+0E0h+var_C0], eax; unsigned int
0x14017145b  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x140171460  mov     r15, rax
0x140171463  test    rax, rax
0x140171466  jnz     short loc_1401714BB
0x140171468  mov     ebx, 0C000009Ah
0x14017146d  mov     rcx, [r14+8]; this
0x140171471  lea     r8, [rbp+57h+var_68]; struct _SmsTopLevelAction *
0x140171475  mov     rdx, rdi; struct CmsTransactionContext *
0x140171478  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x14017147d  mov     rcx, r15; struct SmsUndoRecord *
0x140171480  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x140171485  mov     rdx, [rbp+57h+arg_18]; struct CmsRowWithBuffer *
0x140171489  mov     rcx, rdi; this
0x14017148c  call    ?PushRow@CmsTransactionContext@@QEAAXPEAVCmsRowWithBuffer@@@Z; CmsTransactionContext::PushRow(CmsRowWithBuffer *)
0x140171491  mov     rdx, [rbp+57h+var_A0]; struct CmsRowWithBuffer *
0x140171495  mov     rcx, rdi; this
0x140171498  call    ?PushRow@CmsTransactionContext@@QEAAXPEAVCmsRowWithBuffer@@@Z; CmsTransactionContext::PushRow(CmsRowWithBuffer *)
0x14017149d  mov     eax, ebx
0x14017149f  mov     rbx, [rsp+0E0h+arg_8]
0x1401714a7  add     rsp, 0B0h
0x1401714ae  pop     r15
0x1401714b0  pop     r14
0x1401714b2  pop     r13
0x1401714b4  pop     r12
0x1401714b6  pop     rdi
0x1401714b7  pop     rsi
0x1401714b8  pop     rbp
0x1401714b9  retn
0x1401714bb  mov     r12, [rax+18h]
0x1401714bf  mov     [r12], r13
0x1401714c3  lea     rcx, [r12+18h]; BitMapHeader
0x1401714c8  movups  xmm0, xmmword ptr [rsi]
0x1401714cb  lea     rdx, [r12+28h]; BitMapBuffer
0x1401714d0  movdqu  xmmword ptr [r12+8], xmm0
0x1401714d7  mov     r8d, [rsi+8]; SizeOfBitMap
0x1401714db  call    cs:__imp_RtlInitializeBitMap
0x1401714e2  nop     dword ptr [rax+rax+00h]
0x1401714e7  mov     r8d, [rbp+57h+SizeOfBitMap]
0x1401714eb  xor     edx, edx; unsigned int
0x1401714ed  shr     r8d, 3
0x1401714f1  mov     rcx, rbx; this
0x1401714f4  add     r8d, 30h ; '0'; unsigned int
0x1401714f8  lea     r9d, [rdx+10h]; unsigned int
0x1401714fc  call    ?NewLength@CmsRowWithBuffer@@QEAAJKKKK@Z; CmsRowWithBuffer::NewLength(ulong,ulong,ulong,ulong)
0x140171501  mov     ebx, eax
0x140171503  test    eax, eax
0x140171505  js      loc_14017146D
0x14017150b  mov     r8, qword ptr [rbp+57h+var_98.SizeOfBitMap]
0x14017150f  xor     r9d, r9d; unsigned int
0x140171512  mov     rcx, [rbp+57h+arg_18]; this
0x140171516  xor     edx, edx; unsigned int
0x140171518  shr     r8d, 3; unsigned int
0x14017151c  call    ?NewLength@CmsRowWithBuffer@@QEAAJKKKK@Z; CmsRowWithBuffer::NewLength(ulong,ulong,ulong,ulong)
0x140171521  mov     ebx, eax
0x140171523  test    eax, eax
0x140171525  js      loc_14017146D
0x14017152b  movups  xmm0, xmmword ptr [r13+250h]
0x140171533  mov     r8d, [rbp+57h+SizeOfBitMap]; SizeOfBitMap
0x140171537  mov     rdx, [rbp+57h+var_A0]
0x14017153b  mov     ebx, r8d
0x14017153e  mov     rdx, [rdx+18h]
0x140171542  movdqu  xmmword ptr [rdx], xmm0
0x140171546  mov     dword ptr [rdx+0Ch], 3
0x14017154d  mov     dword ptr [rdx+8], 0
0x140171554  mov     byte ptr [rdx+10h], 1
0x140171558  mov     dword ptr [rdx+14h], 0
0x14017155f  mov     rax, [r14+8]
0x140171563  mov     ecx, [rax+50h]
0x140171566  mov     rax, [r13+250h]
0x14017156d  inc     ecx
0x14017156f  shl     rax, cl
0x140171572  lea     rcx, [rbp+57h+BitMapHeader]; BitMapHeader
0x140171576  mov     [rdx+18h], rax
0x14017157a  mov     [rdx+20h], rbx
0x14017157e  mov     byte ptr [rdx+28h], 30h ; '0'
0x140171582  add     rdx, 30h ; '0'; BitMapBuffer
0x140171586  call    cs:__imp_RtlInitializeBitMap
0x14017158d  nop     dword ptr [rax+rax+00h]
0x140171592  lea     rax, [rbp+57h+BitMapHeader]
0x140171596  mov     qword ptr [rbp+57h+var_98.SizeOfBitMap], 0
0x14017159e  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1401715a3  mov     r9d, 3
0x1401715a9  lea     rax, [rbp+57h+var_98]
0x1401715ad  mov     [rbp+57h+var_98.Buffer], rbx
0x1401715b1  mov     r8, r13
0x1401715b4  mov     [rsp+0E0h+var_C0], rax
0x1401715b9  mov     rdx, rdi
0x1401715bc  mov     rcx, r14
0x1401715bf  call    ?CopyContainerAllocationBitmap@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@W4_EmsContainerType@@AEBU_RANGE@@PEAU_RTL_BITMAP@@@Z; CmsVolumeContainer::CopyContainerAllocationBitmap(CmsTransactionContext *,SmsContainer *,_EmsContainerType,_RANGE const &,_RTL_BITMAP *)
0x1401715c4  mov     ebx, eax
0x1401715c6  test    eax, eax
0x1401715c8  js      loc_14017146D
0x1401715ce  mov     r9d, [rsi+8]
0x1401715d2  lea     rdx, [r12+18h]
0x1401715d7  mov     r8d, [rsi]
0x1401715da  lea     rcx, [rbp+57h+BitMapHeader]
0x1401715de  call    cs:__imp_RtlExtractBitMap
0x1401715e5  nop     dword ptr [rax+rax+00h]
0x1401715ea  mov     rax, [rbp+57h+arg_18]
0x1401715ee  lea     rcx, [rbp+57h+var_78]; BitMapHeader
0x1401715f2  mov     r8d, [rsi+8]; SizeOfBitMap
0x1401715f6  mov     rdx, [rax+18h]; BitMapBuffer
0x1401715fa  call    cs:__imp_RtlInitializeBitMap
0x140171601  nop     dword ptr [rax+rax+00h]
0x140171606  lea     rax, [rbp+57h+var_78]
0x14017160a  mov     r9d, 5
0x140171610  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140171615  mov     r8, r13
0x140171618  mov     rdx, rdi
0x14017161b  mov     [rsp+0E0h+var_C0], rsi
0x140171620  mov     rcx, r14
0x140171623  call    ?CopyContainerAllocationBitmap@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@W4_EmsContainerType@@AEBU_RANGE@@PEAU_RTL_BITMAP@@@Z; CmsVolumeContainer::CopyContainerAllocationBitmap(CmsTransactionContext *,SmsContainer *,_EmsContainerType,_RANGE const &,_RTL_BITMAP *)
0x140171628  mov     ebx, eax
0x14017162a  test    eax, eax
0x14017162c  js      loc_14017146D
0x140171632  mov     r8d, [rsi]
0x140171635  lea     rdx, [rbp+57h+BitMapHeader]
0x140171639  lea     rcx, [rbp+57h+var_78]
0x14017163d  call    cs:__imp_RtlCopyBitMap
0x140171644  nop     dword ptr [rax+rax+00h]
0x140171649  mov     r8, [rbp+57h+var_A0]; struct _CmsRow *
0x14017164d  xor     r9d, r9d; struct SmsLookupStack *
0x140171650  mov     rcx, [r14+48h]; this
0x140171654  mov     rdx, rdi; struct CmsTransactionContext *
0x140171657  mov     [rsp+0E0h+var_C0], 0; unsigned int *
0x140171660  call    ?UpdateRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@PEAUSmsLookupStack@@PEAK@Z; CmsTable::UpdateRow(CmsTransactionContext *,_CmsRow const &,SmsLookupStack *,ulong *)
0x140171665  mov     ebx, eax
0x140171667  test    eax, eax
0x140171669  js      loc_14017146D
0x14017166f  mov     rdx, [r13+0A8h]; BitMapBuffer
0x140171676  test    rdx, rdx
0x140171679  jz      short loc_1401716AD
0x14017167b  mov     r8d, [rbp+57h+SizeOfBitMap]; SizeOfBitMap
0x14017167f  lea     rcx, [rbp+57h+var_98]; BitMapHeader
0x140171683  xorps   xmm0, xmm0
0x140171686  movups  xmmword ptr [rbp+57h+var_98.SizeOfBitMap], xmm0
0x14017168a  call    cs:__imp_RtlInitializeBitMap
0x140171691  nop     dword ptr [rax+rax+00h]
0x140171696  mov     r8d, [rsi]
0x140171699  lea     rdx, [rbp+57h+var_98]
0x14017169d  lea     rcx, [rbp+57h+var_78]
0x1401716a1  call    cs:__imp_RtlCopyBitMap
0x1401716a8  nop     dword ptr [rax+rax+00h]
0x1401716ad  mov     rcx, [r14+8]; this
0x1401716b1  lea     r8, [rbp+57h+var_68]; struct _SmsTopLevelAction *
0x1401716b5  xor     r9d, r9d; unsigned __int8
0x1401716b8  mov     rdx, rdi; struct CmsTransactionContext *
0x1401716bb  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x1401716c0  mov     rax, [rsi+8]
0x1401716c4  xor     r9d, r9d; struct SmsLookupStack *
0x1401716c7  mov     rcx, [r14+48h]; this
0x1401716cb  add     rax, 3
0x1401716cf  shr     rax, 2
0x1401716d3  mov     r8, r15; struct SmsUndoRecord *
0x1401716d6  add     eax, 28h ; '('
0x1401716d9  mov     [rsp+0E0h+var_B0], 0; int
0x1401716e1  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1401716e5  mov     rdx, rdi; struct CmsTransactionContext *
0x1401716e8  mov     [rsp+0E0h+var_C0], r12; void *
0x1401716ed  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEBUSmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,SmsLookupStack const *,void *,ulong,long)
0x1401716f2  xor     r15d, r15d
0x1401716f5  jmp     loc_14017147D
```
