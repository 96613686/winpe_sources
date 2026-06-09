# CmsVolumeContainer::UpdateCurrentToInitialAllocationBitmap(CmsTransactionContext *,SmsContainer *,_RANGE const &)

- ea: `0x140125a80`
- end: `0x140125dc7`
- name: `?UpdateCurrentToInitialAllocationBitmap@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@AEBU_RANGE@@@Z`
- size: `839`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsContainer *, const struct _RANGE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401258a8`

## callees

- `0x140081bf4`
- `0x140082f98`
- `0x14008c930`
- `0x14008d430`
- `0x14008e220`
- `0x140090d88`
- `0x1400a9b80`
- `0x1400aa998`
- `0x1400c323c`
- `0x1400d989c`
- `0x1400da37c`
- `0x140125a80`

## import_xrefs

- `ntdll!RtlExtractBitMap` at `0x140125cab`
- `ntdll!RtlExtractBitMap` at `0x140125cab`
- `ntdll!RtlCopyBitMap` at `0x140125d0a`
- `ntdll!RtlCopyBitMap` at `0x140125d6e`
- `ntdll!RtlCopyBitMap` at `0x140125d0a`
- `ntdll!RtlCopyBitMap` at `0x140125d6e`
- `ntdll!RtlInitializeBitMap` at `0x140125ba8`
- `ntdll!RtlInitializeBitMap` at `0x140125c53`
- `ntdll!RtlInitializeBitMap` at `0x140125cc7`
- `ntdll!RtlInitializeBitMap` at `0x140125d57`
- `ntdll!RtlInitializeBitMap` at `0x140125ba8`
- `ntdll!RtlInitializeBitMap` at `0x140125c53`
- `ntdll!RtlInitializeBitMap` at `0x140125cc7`
- `ntdll!RtlInitializeBitMap` at `0x140125d57`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::UpdateCurrentToInitialAllocationBitmap(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        struct SmsContainer *a3,
        const struct _RANGE *a4)
{
  __int64 v8; // rdx
  __int64 Undo; // rax
  struct SmsUndoRecord *v10; // r15
  int updated; // ebx
  struct CmsTransactionContext *v12; // rdx
  unsigned int v13; // r8d
  char *v15; // r12
  __int64 v16; // rdx
  ULONG *v17; // rdx
  unsigned int v18; // [rsp+20h] [rbp-69h]
  unsigned int v19; // [rsp+20h] [rbp-69h]
  struct CmsRowWithBuffer *v20; // [rsp+40h] [rbp-49h]
  struct _RTL_BITMAP v21; // [rsp+48h] [rbp-41h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+58h] [rbp-31h] BYREF
  struct _RTL_BITMAP v23; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v24[24]; // [rsp+78h] [rbp-11h] BYREF
  __int16 v25; // [rsp+90h] [rbp+7h]
  char v26; // [rsp+92h] [rbp+9h]
  int v27; // [rsp+A0h] [rbp+17h]
  ULONG SizeOfBitMap; // [rsp+F0h] [rbp+67h]
  struct CmsRowWithBuffer *v29; // [rsp+108h] [rbp+7Fh]

  SizeOfBitMap = *(_DWORD *)(*((_QWORD *)this + 1) + 84LL);
  v20 = CmsTransactionContext::PopRow(a2);
  v29 = CmsTransactionContext::PopRow(a2);
  v21.SizeOfBitMap = *((_DWORD *)a4 + 2) + 7;
  v25 = 0;
  v26 = 0;
  BitMapHeader = 0;
  v27 = 0;
  v23 = 0;
  CmsVolume::BeginTopLevelActionInternal(v21.SizeOfBitMap, a2, v24);
  v18 = ((*((_DWORD *)a4 + 2) + 3) & 0xFFFFFFFC) + 40;
  Undo = CmsBPlusTable::AllocateUndo(*((_QWORD *)this + 8), v8, 48);
  v10 = (struct SmsUndoRecord *)Undo;
  if ( !Undo )
  {
    updated = -1073741670;
LABEL_3:
    CmsVolume::AbortTopLevelAction(*((CmsVolume **)this + 1), a2, (struct _SmsTopLevelAction *)v24);
    goto LABEL_4;
  }
  v15 = *(char **)(Undo + 24);
  *(_QWORD *)v15 = a3;
  *(_OWORD *)(v15 + 8) = *(_OWORD *)a4;
  RtlInitializeBitMap((PRTL_BITMAP)(v15 + 24), (PULONG)v15 + 10, *((_DWORD *)a4 + 2));
  updated = CmsRowWithBuffer::NewLength(v20, 0, (SizeOfBitMap >> 3) + 48, 0x10u, v18);
  if ( updated < 0 )
    goto LABEL_3;
  updated = CmsRowWithBuffer::NewLength(v29, 0, v21.SizeOfBitMap >> 3, 0, v19);
  if ( updated < 0 )
    goto LABEL_3;
  v16 = *((_QWORD *)v20 + 3);
  *(_OWORD *)v16 = *((_OWORD *)a3 + 37);
  *(_DWORD *)(v16 + 12) = 3;
  *(_DWORD *)(v16 + 8) = 0;
  *(_BYTE *)(v16 + 16) = 1;
  *(_DWORD *)(v16 + 20) = 0;
  *(_QWORD *)(v16 + 24) = *((_QWORD *)a3 + 74) << ((unsigned __int8)*(_DWORD *)(*((_QWORD *)this + 1) + 80LL) + 1);
  *(_QWORD *)(v16 + 32) = SizeOfBitMap;
  *(_BYTE *)(v16 + 40) = 48;
  RtlInitializeBitMap(&BitMapHeader, (PULONG)(v16 + 48), SizeOfBitMap);
  *(_QWORD *)&v21.SizeOfBitMap = 0;
  v21.Buffer = (PULONG)SizeOfBitMap;
  updated = CmsVolumeContainer::CopyContainerAllocationBitmap(this, a2, a3, 3, &v21, &BitMapHeader);
  if ( updated < 0 )
    goto LABEL_3;
  RtlExtractBitMap(&BitMapHeader, v15 + 24, *(unsigned int *)a4, *((unsigned int *)a4 + 2));
  RtlInitializeBitMap(&v23, *((PULONG *)v29 + 3), *((_DWORD *)a4 + 2));
  updated = CmsVolumeContainer::CopyContainerAllocationBitmap(this, a2, a3, 5, a4, &v23);
  if ( updated < 0 )
    goto LABEL_3;
  RtlCopyBitMap(&v23, &BitMapHeader, *(unsigned int *)a4);
  updated = CmsTable::UpdateRow(*((CmsTable **)this + 8), a2, v20, 0, 0);
  if ( updated < 0 )
    goto LABEL_3;
  v17 = (ULONG *)*((_QWORD *)a3 + 21);
  if ( v17 )
  {
    v21 = 0;
    RtlInitializeBitMap(&v21, v17, SizeOfBitMap);
    RtlCopyBitMap(&v23, &v21, *(unsigned int *)a4);
  }
  CmsVolume::CommitTopLevelAction(*((CmsVolume **)this + 1), a2, (struct _SmsTopLevelAction *)v24, 0);
  CmsBPlusTable::FormatUndoRecord(
    *((CmsBPlusTable **)this + 8),
    a2,
    v10,
    0,
    v15,
    ((unsigned __int64)(*((_QWORD *)a4 + 1) + 3LL) >> 2) + 40,
    0);
  v10 = 0;
LABEL_4:
  CmsBPlusTable::FreeUndoRecord(v10, v12, v13);
  CmsTransactionContext::PushRow(a2, v29);
  CmsTransactionContext::PushRow(a2, v20);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140125a80  mov     [rsp-8+arg_8], rbx
0x140125a85  push    rbp
0x140125a86  push    rsi
0x140125a87  push    rdi
0x140125a88  push    r12
0x140125a8a  push    r13
0x140125a8c  push    r14
0x140125a8e  push    r15
0x140125a90  lea     rbp, [rsp-27h]
0x140125a95  sub     rsp, 0B0h
0x140125a9c  mov     rax, [rcx+8]
0x140125aa0  mov     r14, rcx
0x140125aa3  mov     rcx, rdx; this
0x140125aa6  mov     rsi, r9
0x140125aa9  mov     r13, r8
0x140125aac  mov     rdi, rdx
0x140125aaf  mov     eax, [rax+54h]
0x140125ab2  mov     [rbp+57h+SizeOfBitMap], eax
0x140125ab5  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x140125aba  mov     rcx, rdi; this
0x140125abd  mov     [rbp+57h+var_A0], rax
0x140125ac1  mov     rbx, rax
0x140125ac4  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x140125ac9  mov     ecx, [rsi+8]
0x140125acc  lea     r8, [rbp+57h+var_68]
0x140125ad0  xor     r12d, r12d
0x140125ad3  mov     [rbp+57h+arg_18], rax
0x140125ad7  add     ecx, 7
0x140125ada  mov     byte ptr [rsp+0E0h+var_B8], r12b
0x140125adf  xorps   xmm1, xmm1
0x140125ae2  mov     [rbp+57h+var_98.SizeOfBitMap], ecx
0x140125ae5  xorps   xmm0, xmm0
0x140125ae8  mov     [rbp+57h+var_50], r12w
0x140125aed  mov     rdx, rdi
0x140125af0  mov     [rbp+57h+var_4E], r12b
0x140125af4  movups  xmmword ptr [rbp+57h+BitMapHeader.SizeOfBitMap], xmm1
0x140125af8  mov     [rbp+57h+var_40], r12d
0x140125afc  movups  xmmword ptr [rbp+57h+var_78.SizeOfBitMap], xmm0
0x140125b00  mov     byte ptr [rsp+0E0h+var_C0], r12b
0x140125b05  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x140125b0a  mov     eax, [rsi+8]
0x140125b0d  lea     r8d, [r12+30h]
0x140125b12  mov     rcx, [r14+40h]
0x140125b16  add     eax, 3
0x140125b19  and     eax, 0FFFFFFFCh
0x140125b1c  mov     [rsp+0E0h+var_B8], r12d
0x140125b21  add     eax, 28h ; '('
0x140125b24  mov     dword ptr [rsp+0E0h+var_C0], eax; unsigned int
0x140125b28  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x140125b2d  mov     r15, rax
0x140125b30  test    rax, rax
0x140125b33  jnz     short loc_140125B88
0x140125b35  mov     ebx, 0C000009Ah
0x140125b3a  mov     rcx, [r14+8]; this
0x140125b3e  lea     r8, [rbp+57h+var_68]; struct _SmsTopLevelAction *
0x140125b42  mov     rdx, rdi; struct CmsTransactionContext *
0x140125b45  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x140125b4a  mov     rcx, r15; struct SmsUndoRecord *
0x140125b4d  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x140125b52  mov     rdx, [rbp+57h+arg_18]; struct CmsRowWithBuffer *
0x140125b56  mov     rcx, rdi; this
0x140125b59  call    ?PushRow@CmsTransactionContext@@QEAAXPEAVCmsRowWithBuffer@@@Z; CmsTransactionContext::PushRow(CmsRowWithBuffer *)
0x140125b5e  mov     rdx, [rbp+57h+var_A0]; struct CmsRowWithBuffer *
0x140125b62  mov     rcx, rdi; this
0x140125b65  call    ?PushRow@CmsTransactionContext@@QEAAXPEAVCmsRowWithBuffer@@@Z; CmsTransactionContext::PushRow(CmsRowWithBuffer *)
0x140125b6a  mov     eax, ebx
0x140125b6c  mov     rbx, [rsp+0E0h+arg_8]
0x140125b74  add     rsp, 0B0h
0x140125b7b  pop     r15
0x140125b7d  pop     r14
0x140125b7f  pop     r13
0x140125b81  pop     r12
0x140125b83  pop     rdi
0x140125b84  pop     rsi
0x140125b85  pop     rbp
0x140125b86  retn
0x140125b88  mov     r12, [rax+18h]
0x140125b8c  mov     [r12], r13
0x140125b90  lea     rcx, [r12+18h]; BitMapHeader
0x140125b95  movups  xmm0, xmmword ptr [rsi]
0x140125b98  lea     rdx, [r12+28h]; BitMapBuffer
0x140125b9d  movdqu  xmmword ptr [r12+8], xmm0
0x140125ba4  mov     r8d, [rsi+8]; SizeOfBitMap
0x140125ba8  call    cs:__imp_RtlInitializeBitMap
0x140125baf  nop     dword ptr [rax+rax+00h]
0x140125bb4  mov     r8d, [rbp+57h+SizeOfBitMap]
0x140125bb8  xor     edx, edx; unsigned int
0x140125bba  shr     r8d, 3
0x140125bbe  mov     rcx, rbx; this
0x140125bc1  add     r8d, 30h ; '0'; unsigned int
0x140125bc5  lea     r9d, [rdx+10h]; unsigned int
0x140125bc9  call    ?NewLength@CmsRowWithBuffer@@QEAAJKKKK@Z; CmsRowWithBuffer::NewLength(ulong,ulong,ulong,ulong)
0x140125bce  mov     ebx, eax
0x140125bd0  test    eax, eax
0x140125bd2  js      loc_140125B3A
0x140125bd8  mov     r8, qword ptr [rbp+57h+var_98.SizeOfBitMap]
0x140125bdc  xor     r9d, r9d; unsigned int
0x140125bdf  mov     rcx, [rbp+57h+arg_18]; this
0x140125be3  xor     edx, edx; unsigned int
0x140125be5  shr     r8d, 3; unsigned int
0x140125be9  call    ?NewLength@CmsRowWithBuffer@@QEAAJKKKK@Z; CmsRowWithBuffer::NewLength(ulong,ulong,ulong,ulong)
0x140125bee  mov     ebx, eax
0x140125bf0  test    eax, eax
0x140125bf2  js      loc_140125B3A
0x140125bf8  movups  xmm0, xmmword ptr [r13+250h]
0x140125c00  mov     r8d, [rbp+57h+SizeOfBitMap]; SizeOfBitMap
0x140125c04  mov     rdx, [rbp+57h+var_A0]
0x140125c08  mov     ebx, r8d
0x140125c0b  mov     rdx, [rdx+18h]
0x140125c0f  movdqu  xmmword ptr [rdx], xmm0
0x140125c13  mov     dword ptr [rdx+0Ch], 3
0x140125c1a  mov     dword ptr [rdx+8], 0
0x140125c21  mov     byte ptr [rdx+10h], 1
0x140125c25  mov     dword ptr [rdx+14h], 0
0x140125c2c  mov     rax, [r14+8]
0x140125c30  mov     ecx, [rax+50h]
0x140125c33  mov     rax, [r13+250h]
0x140125c3a  inc     ecx
0x140125c3c  shl     rax, cl
0x140125c3f  lea     rcx, [rbp+57h+BitMapHeader]; BitMapHeader
0x140125c43  mov     [rdx+18h], rax
0x140125c47  mov     [rdx+20h], rbx
0x140125c4b  mov     byte ptr [rdx+28h], 30h ; '0'
0x140125c4f  add     rdx, 30h ; '0'; BitMapBuffer
0x140125c53  call    cs:__imp_RtlInitializeBitMap
0x140125c5a  nop     dword ptr [rax+rax+00h]
0x140125c5f  lea     rax, [rbp+57h+BitMapHeader]
0x140125c63  mov     qword ptr [rbp+57h+var_98.SizeOfBitMap], 0
0x140125c6b  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140125c70  mov     r9d, 3
0x140125c76  lea     rax, [rbp+57h+var_98]
0x140125c7a  mov     [rbp+57h+var_98.Buffer], rbx
0x140125c7e  mov     r8, r13
0x140125c81  mov     [rsp+0E0h+var_C0], rax
0x140125c86  mov     rdx, rdi
0x140125c89  mov     rcx, r14
0x140125c8c  call    ?CopyContainerAllocationBitmap@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@W4_EmsContainerType@@AEBU_RANGE@@PEAU_RTL_BITMAP@@@Z; CmsVolumeContainer::CopyContainerAllocationBitmap(CmsTransactionContext *,SmsContainer *,_EmsContainerType,_RANGE const &,_RTL_BITMAP *)
0x140125c91  mov     ebx, eax
0x140125c93  test    eax, eax
0x140125c95  js      loc_140125B3A
0x140125c9b  mov     r9d, [rsi+8]
0x140125c9f  lea     rdx, [r12+18h]
0x140125ca4  mov     r8d, [rsi]
0x140125ca7  lea     rcx, [rbp+57h+BitMapHeader]
0x140125cab  call    cs:__imp_RtlExtractBitMap
0x140125cb2  nop     dword ptr [rax+rax+00h]
0x140125cb7  mov     rax, [rbp+57h+arg_18]
0x140125cbb  lea     rcx, [rbp+57h+var_78]; BitMapHeader
0x140125cbf  mov     r8d, [rsi+8]; SizeOfBitMap
0x140125cc3  mov     rdx, [rax+18h]; BitMapBuffer
0x140125cc7  call    cs:__imp_RtlInitializeBitMap
0x140125cce  nop     dword ptr [rax+rax+00h]
0x140125cd3  lea     rax, [rbp+57h+var_78]
0x140125cd7  mov     r9d, 5
0x140125cdd  mov     qword ptr [rsp+0E0h+var_B8], rax
0x140125ce2  mov     r8, r13
0x140125ce5  mov     rdx, rdi
0x140125ce8  mov     [rsp+0E0h+var_C0], rsi
0x140125ced  mov     rcx, r14
0x140125cf0  call    ?CopyContainerAllocationBitmap@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@W4_EmsContainerType@@AEBU_RANGE@@PEAU_RTL_BITMAP@@@Z; CmsVolumeContainer::CopyContainerAllocationBitmap(CmsTransactionContext *,SmsContainer *,_EmsContainerType,_RANGE const &,_RTL_BITMAP *)
0x140125cf5  mov     ebx, eax
0x140125cf7  test    eax, eax
0x140125cf9  js      loc_140125B3A
0x140125cff  mov     r8d, [rsi]
0x140125d02  lea     rdx, [rbp+57h+BitMapHeader]
0x140125d06  lea     rcx, [rbp+57h+var_78]
0x140125d0a  call    cs:__imp_RtlCopyBitMap
0x140125d11  nop     dword ptr [rax+rax+00h]
0x140125d16  mov     r8, [rbp+57h+var_A0]; struct _CmsRow *
0x140125d1a  xor     r9d, r9d; struct SmsLookupStack *
0x140125d1d  mov     rcx, [r14+40h]; this
0x140125d21  mov     rdx, rdi; struct CmsTransactionContext *
0x140125d24  mov     [rsp+0E0h+var_C0], 0; unsigned int *
0x140125d2d  call    ?UpdateRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@PEAUSmsLookupStack@@PEAK@Z; CmsTable::UpdateRow(CmsTransactionContext *,_CmsRow const &,SmsLookupStack *,ulong *)
0x140125d32  mov     ebx, eax
0x140125d34  test    eax, eax
0x140125d36  js      loc_140125B3A
0x140125d3c  mov     rdx, [r13+0A8h]; BitMapBuffer
0x140125d43  test    rdx, rdx
0x140125d46  jz      short loc_140125D7A
0x140125d48  mov     r8d, [rbp+57h+SizeOfBitMap]; SizeOfBitMap
0x140125d4c  lea     rcx, [rbp+57h+var_98]; BitMapHeader
0x140125d50  xorps   xmm0, xmm0
0x140125d53  movups  xmmword ptr [rbp+57h+var_98.SizeOfBitMap], xmm0
0x140125d57  call    cs:__imp_RtlInitializeBitMap
0x140125d5e  nop     dword ptr [rax+rax+00h]
0x140125d63  mov     r8d, [rsi]
0x140125d66  lea     rdx, [rbp+57h+var_98]
0x140125d6a  lea     rcx, [rbp+57h+var_78]
0x140125d6e  call    cs:__imp_RtlCopyBitMap
0x140125d75  nop     dword ptr [rax+rax+00h]
0x140125d7a  mov     rcx, [r14+8]; this
0x140125d7e  lea     r8, [rbp+57h+var_68]; struct _SmsTopLevelAction *
0x140125d82  xor     r9d, r9d; unsigned __int8
0x140125d85  mov     rdx, rdi; struct CmsTransactionContext *
0x140125d88  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x140125d8d  mov     rax, [rsi+8]
0x140125d91  xor     r9d, r9d; struct SmsLookupStack *
0x140125d94  mov     rcx, [r14+40h]; this
0x140125d98  add     rax, 3
0x140125d9c  shr     rax, 2
0x140125da0  mov     r8, r15; struct SmsUndoRecord *
0x140125da3  add     eax, 28h ; '('
0x140125da6  mov     [rsp+0E0h+var_B0], 0; int
0x140125dae  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140125db2  mov     rdx, rdi; struct CmsTransactionContext *
0x140125db5  mov     [rsp+0E0h+var_C0], r12; void *
0x140125dba  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEBUSmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,SmsLookupStack const *,void *,ulong,long)
0x140125dbf  xor     r15d, r15d
0x140125dc2  jmp     loc_140125B4A
```
