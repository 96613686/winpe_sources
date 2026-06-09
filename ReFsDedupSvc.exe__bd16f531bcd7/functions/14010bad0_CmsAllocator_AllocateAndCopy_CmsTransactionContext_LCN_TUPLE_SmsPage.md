# CmsAllocator::AllocateAndCopy(CmsTransactionContext *,_LCN_TUPLE *,SmsPage *)

- ea: `0x14010bad0`
- end: `0x14010be1a`
- name: `?AllocateAndCopy@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@PEAUSmsPage@@@Z`
- size: `842`
- prototype: `int(CmsAllocator *__hidden this, struct CmsTransactionContext *, union _LCN_TUPLE *, struct SmsPage *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x14008cf60`

## callees

- `0x140090d88`
- `0x140098a38`
- `0x1400a2a8c`
- `0x1400ac048`
- `0x1400b99b8`
- `0x1400d989c`
- `0x1400da37c`
- `0x1400da780`
- `0x1400dada8`
- `0x14010bad0`

## import_xrefs

- `ntdll!RtlCopyMemoryNonTemporal` at `0x14010bbc2`
- `ntdll!RtlCopyMemoryNonTemporal` at `0x14010bbc2`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x14010bc1c`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x14010bc1c`
- `ntdll!RtlReleaseSRWLockShared` at `0x14010bcd3`
- `ntdll!RtlReleaseSRWLockShared` at `0x14010bcd3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14010bce1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14010bce1`

## pseudocode

```c
__int64 __fastcall CmsAllocator::AllocateAndCopy(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        union _LCN_TUPLE *a3,
        struct SmsPage *a4)
{
  __int64 v4; // rdi
  unsigned __int8 v6; // r9
  __int64 v9; // rdx
  struct CmsTransactionContext *v10; // rdx
  unsigned int v11; // r8d
  struct SmsUndoRecord *Undo; // r13
  int v13; // ebp
  struct SmsPage *v15; // rdi
  struct SmsPage *v16; // r14
  struct SmsPage *v17; // r15
  CmsCachedPin *v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  void *v21; // rbx
  unsigned int v22; // r9d
  CmsVolume *v23; // r14
  struct SmsPage *v24; // rsi
  unsigned int v25; // ebx
  int *v26; // rcx
  int v27; // r10d
  int *v28; // rdx
  int v29; // eax
  _BYTE v30[104]; // [rsp+40h] [rbp-68h] BYREF
  struct SmsPage *v31; // [rsp+B0h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 56);
  v6 = *((_BYTE *)a4 + 392);
  v31 = 0;
  SmsView::SmsView((SmsView *)v30, a2, *((const struct CmsBPlusTable **)a4 + 12), v6);
  Undo = (struct SmsUndoRecord *)CmsBPlusTable::AllocateUndo(*((_QWORD *)a4 + 12), v9, 1);
  if ( !Undo )
  {
    v13 = -1073741670;
LABEL_3:
    CmsBPlusTable::FreeUndoRecord(Undo, v10, v11);
    return (unsigned int)v13;
  }
  v13 = CmsVolume::PinSinglePage(v4, a2, v30, a3, *((_DWORD *)a4 + 94), 7, 0, &v31);
  if ( v13 < 0 )
    goto LABEL_3;
  v15 = 0;
  v16 = v31;
  v17 = 0;
  RtlCopyMemoryNonTemporal(*((_QWORD *)v31 + 13) + 80LL, *((_QWORD *)a4 + 13) + 80LL, *((unsigned int *)a4 + 80) - 80LL);
  *((_QWORD *)v16 + 32) = a4;
  *((_QWORD *)a4 + 33) = v16;
  if ( *((_QWORD *)a4 + 75) )
  {
    if ( *((_BYTE *)a4 + 392) != 0xF8 )
    {
      if ( byte_14021FF88 )
      {
        ++dword_14021FE8C;
        if ( (unsigned __int8)RtlTryAcquireSRWLockExclusive(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a4 + 12) + 32LL) + 40LL)) )
        {
          v18 = (CmsCachedPin *)*((_QWORD *)a4 + 75);
          if ( v18 && (*((_BYTE *)v18 + 104) & 1) != 0 && !CmsCachedPin::ShouldDoomCachedPin(v18) )
          {
            *((_QWORD *)v16 + 75) = v19;
            v15 = a4;
            *((_QWORD *)a4 + 75) = 0;
            v17 = v16;
            *(_QWORD *)(*((_QWORD *)v16 + 75) + 32LL) = v16;
            *(_DWORD *)(*((_QWORD *)v16 + 75) + 88LL) = *((_DWORD *)v16 + 92);
            *((_DWORD *)v16 + 93) = *((_DWORD *)a4 + 93) + 1;
            *(_QWORD *)(*((_QWORD *)v16 + 75) + 120LL) = *((_QWORD *)v16 + 13)
                                                       + 80LL
                                                       + *(unsigned int *)(*((_QWORD *)v16 + 13) + 80LL);
            ++dword_14021FE90;
            ++*(_DWORD *)(*((_QWORD *)v16 + 75) + 148LL);
          }
          v20 = *(_QWORD **)(*(_QWORD *)(*((_QWORD *)a4 + 12) + 32LL) + 40LL);
          if ( *v20 < 0x10u )
            RtlReleaseSRWLockExclusive(v20);
          else
            RtlReleaseSRWLockShared(v20);
        }
      }
    }
  }
  ++*((_DWORD *)a4 + 92);
  SmsPage::UpdatePersistentQIsForPageCow(a4, a2, v16);
  v21 = (void *)*((_QWORD *)Undo + 3);
  SmsMultiPageUndoRecord::PinPages(v21, a2, a4, 4, v16, 1);
  CmsBPlusTable::FormatUndoRecord(*((CmsBPlusTable **)a4 + 12), a2, Undo, 0, v21, 0x20u, 0);
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)v17 + 95);
  if ( v15 )
  {
    v22 = 2;
    v23 = *(CmsVolume **)(*(_QWORD *)(*((_QWORD *)v15 + 12) + 112LL) + 16LL);
    do
    {
      v24 = 0;
      v25 = v22;
      if ( *((_QWORD *)v15 + 38) )
      {
        v26 = (int *)((char *)v15 + 312);
        if ( (v22 & 1) != 0 )
        {
          v27 = *v26;
          if ( *((_DWORD *)v15 + 96) == *v26 )
          {
            v28 = (int *)((char *)v15 + 316);
            v24 = (struct SmsPage *)*((_QWORD *)v15 + 38);
            if ( (v22 & 4) == 0 )
              goto LABEL_31;
            v29 = *v28;
            if ( *((_DWORD *)v15 + 97) != *v28 )
            {
              v25 = v22 & 0xFFFFFFFB;
              goto LABEL_31;
            }
LABEL_30:
            *v28 = v29 - 1;
LABEL_31:
            *v26 = v27 - 1;
            if ( v27 == 1 )
              *((_QWORD *)v15 + 38) = 0;
            goto LABEL_33;
          }
        }
        if ( (v22 & 4) != 0 )
        {
          v28 = (int *)((char *)v15 + 316);
          v29 = *((_DWORD *)v15 + 79);
          if ( *((_DWORD *)v15 + 97) == v29 )
          {
            v27 = *v26;
            v24 = (struct SmsPage *)*((_QWORD *)v15 + 38);
            goto LABEL_30;
          }
        }
      }
LABEL_33:
      CmsVolume::UnpinInternal(v23, a2, v15, v22);
      v15 = v24;
      v22 = v25;
    }
    while ( v24 );
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14010bad0  mov     rax, rsp
0x14010bad3  push    rbx
0x14010bad4  push    rbp
0x14010bad5  push    rsi
0x14010bad6  push    rdi
0x14010bad7  push    r12
0x14010bad9  push    r13
0x14010badb  push    r14
0x14010badd  push    r15
0x14010badf  sub     rsp, 68h
0x14010bae3  mov     rdi, [rcx+1C0h]
0x14010baea  mov     rsi, r9
0x14010baed  mov     r9b, [r9+188h]; unsigned __int8
0x14010baf4  lea     rcx, [rax-68h]; this
0x14010baf8  mov     rbx, r8
0x14010bafb  mov     qword ptr [rax+8], 0
0x14010bb03  mov     r12, rdx
0x14010bb06  mov     r8, [rsi+60h]; struct CmsBPlusTable *
0x14010bb0a  call    ??0SmsView@@QEAA@AEBVCmsTransactionContext@@AEBVCmsBPlusTable@@E@Z; SmsView::SmsView(CmsTransactionContext const &,CmsBPlusTable const &,uchar)
0x14010bb0f  mov     rcx, [rsi+60h]
0x14010bb13  mov     r8d, 1
0x14010bb19  mov     [rsp+0A8h+var_80], 0
0x14010bb21  mov     dword ptr [rsp+0A8h+var_88], 20h ; ' '
0x14010bb29  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x14010bb2e  mov     r13, rax
0x14010bb31  test    rax, rax
0x14010bb34  jnz     short loc_14010BB57
0x14010bb36  mov     ebp, 0C000009Ah
0x14010bb3b  mov     rcx, r13; struct SmsUndoRecord *
0x14010bb3e  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x14010bb43  mov     eax, ebp
0x14010bb45  add     rsp, 68h
0x14010bb49  pop     r15
0x14010bb4b  pop     r14
0x14010bb4d  pop     r13
0x14010bb4f  pop     r12
0x14010bb51  pop     rdi
0x14010bb52  pop     rsi
0x14010bb53  pop     rbp
0x14010bb54  pop     rbx
0x14010bb55  retn
0x14010bb57  lea     rax, [rsp+0A8h+arg_0]
0x14010bb5f  mov     r9, rbx
0x14010bb62  mov     [rsp+0A8h+var_70], rax
0x14010bb67  lea     r8, [rsp+0A8h+var_68]
0x14010bb6c  mov     eax, [rsi+178h]
0x14010bb72  mov     rdx, r12
0x14010bb75  mov     qword ptr [rsp+0A8h+var_78], 0
0x14010bb7e  mov     rcx, rdi
0x14010bb81  mov     [rsp+0A8h+var_80], 7
0x14010bb89  mov     dword ptr [rsp+0A8h+var_88], eax
0x14010bb8d  call    ?PinSinglePage@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEBT_LCN_TUPLE@@KW4_EMS_PIN_FLAGS@@PEAUSmsChecksumBlob@@PEAPEAUSmsPage@@@Z; CmsVolume::PinSinglePage(CmsTransactionContext *,SmsView *,_LCN_TUPLE const *,ulong,_EMS_PIN_FLAGS,SmsChecksumBlob *,SmsPage * *)
0x14010bb92  xor     ebx, ebx
0x14010bb94  mov     ebp, eax
0x14010bb96  test    eax, eax
0x14010bb98  js      short loc_14010BB3B
0x14010bb9a  mov     r8d, [rsi+140h]
0x14010bba1  mov     edi, ebx
0x14010bba3  mov     rdx, [rsi+68h]
0x14010bba7  sub     r8, 50h ; 'P'
0x14010bbab  mov     r14, [rsp+0A8h+arg_0]
0x14010bbb3  add     rdx, 50h ; 'P'
0x14010bbb7  mov     r15d, ebx
0x14010bbba  mov     rcx, [r14+68h]
0x14010bbbe  add     rcx, 50h ; 'P'
0x14010bbc2  call    cs:__imp_RtlCopyMemoryNonTemporal
0x14010bbc9  nop     dword ptr [rax+rax+00h]
0x14010bbce  mov     [r14+100h], rsi
0x14010bbd5  mov     [rsi+108h], r14
0x14010bbdc  cmp     [rsi+258h], rbx
0x14010bbe3  jz      loc_14010BCED
0x14010bbe9  cmp     byte ptr [rsi+188h], 0F8h
0x14010bbf0  jz      loc_14010BCED
0x14010bbf6  cmp     cs:byte_14021FF88, bl
0x14010bbfc  jz      loc_14010BCED
0x14010bc02  mov     eax, cs:dword_14021FE8C
0x14010bc08  inc     eax
0x14010bc0a  mov     cs:dword_14021FE8C, eax
0x14010bc10  mov     rax, [rsi+60h]
0x14010bc14  mov     rcx, [rax+20h]
0x14010bc18  mov     rcx, [rcx+28h]
0x14010bc1c  call    cs:__imp_RtlTryAcquireSRWLockExclusive
0x14010bc23  nop     dword ptr [rax+rax+00h]
0x14010bc28  test    al, al
0x14010bc2a  jz      loc_14010BCED
0x14010bc30  mov     rcx, [rsi+258h]; this
0x14010bc37  test    rcx, rcx
0x14010bc3a  jz      loc_14010BCC1
0x14010bc40  test    byte ptr [rcx+68h], 1
0x14010bc44  jz      short loc_14010BCC1
0x14010bc46  call    ?ShouldDoomCachedPin@CmsCachedPin@@QEBA_NXZ; CmsCachedPin::ShouldDoomCachedPin(void)
0x14010bc4b  test    al, al
0x14010bc4d  jnz     short loc_14010BCC1
0x14010bc4f  mov     [r14+258h], rcx
0x14010bc56  mov     rdi, rsi
0x14010bc59  mov     [rsi+258h], rbx
0x14010bc60  mov     r15, r14
0x14010bc63  mov     rax, [r14+258h]
0x14010bc6a  mov     [rax+20h], r14
0x14010bc6e  mov     eax, [r14+170h]
0x14010bc75  mov     rcx, [r14+258h]
0x14010bc7c  mov     [rcx+58h], eax
0x14010bc7f  mov     eax, [rsi+174h]
0x14010bc85  inc     eax
0x14010bc87  mov     [r14+174h], eax
0x14010bc8e  mov     rax, [r14+68h]
0x14010bc92  add     rax, 50h ; 'P'
0x14010bc96  mov     ecx, [rax]
0x14010bc98  add     rcx, rax
0x14010bc9b  mov     rax, [r14+258h]
0x14010bca2  mov     [rax+78h], rcx
0x14010bca6  mov     eax, cs:dword_14021FE90
0x14010bcac  inc     eax
0x14010bcae  mov     cs:dword_14021FE90, eax
0x14010bcb4  mov     rax, [r14+258h]
0x14010bcbb  inc     dword ptr [rax+94h]
0x14010bcc1  mov     rax, [rsi+60h]
0x14010bcc5  mov     rcx, [rax+20h]
0x14010bcc9  mov     rcx, [rcx+28h]
0x14010bccd  cmp     qword ptr [rcx], 10h
0x14010bcd1  jb      short loc_14010BCE1
0x14010bcd3  call    cs:__imp_RtlReleaseSRWLockShared
0x14010bcda  nop     dword ptr [rax+rax+00h]
0x14010bcdf  jmp     short loc_14010BCED
0x14010bce1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14010bce8  nop     dword ptr [rax+rax+00h]
0x14010bced  inc     dword ptr [rsi+170h]
0x14010bcf3  mov     r8, r14; struct SmsPage *
0x14010bcf6  mov     rdx, r12; struct CmsTransactionContext *
0x14010bcf9  mov     rcx, rsi; this
0x14010bcfc  call    ?UpdatePersistentQIsForPageCow@SmsPage@@QEAAXAEAVCmsTransactionContext@@PEAU1@@Z; SmsPage::UpdatePersistentQIsForPageCow(CmsTransactionContext &,SmsPage *)
0x14010bd01  mov     rbx, [r13+18h]
0x14010bd05  mov     r9d, 4
0x14010bd0b  mov     rcx, rbx
0x14010bd0e  mov     [rsp+0A8h+var_80], 1
0x14010bd16  mov     r8, rsi
0x14010bd19  mov     [rsp+0A8h+var_88], r14
0x14010bd1e  mov     rdx, r12
0x14010bd21  call    ?PinPages@SmsMultiPageUndoRecord@@QEAAXPEAVCmsTransactionContext@@PEAUSmsPage@@W4_MS_PAGE_HISTORY@@12PEAVCmsBPlusTable@@@Z; SmsMultiPageUndoRecord::PinPages(CmsTransactionContext *,SmsPage *,_MS_PAGE_HISTORY,SmsPage *,_MS_PAGE_HISTORY,CmsBPlusTable *)
0x14010bd26  mov     rcx, [rsi+60h]; this
0x14010bd2a  xor     r9d, r9d; struct SmsLookupStack *
0x14010bd2d  mov     [rsp+0A8h+var_78], 0; int
0x14010bd35  mov     r8, r13; struct SmsUndoRecord *
0x14010bd38  mov     [rsp+0A8h+var_80], 20h ; ' '; unsigned int
0x14010bd40  mov     rdx, r12; struct CmsTransactionContext *
0x14010bd43  mov     [rsp+0A8h+var_88], rbx; void *
0x14010bd48  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEBUSmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,SmsLookupStack const *,void *,ulong,long)
0x14010bd4d  test    r15, r15
0x14010bd50  jz      short loc_14010BD5C
0x14010bd52  nop
0x14010bd53  lock inc dword ptr [r15+17Ch]
0x14010bd5b  nop
0x14010bd5c  test    rdi, rdi
0x14010bd5f  jz      loc_14010BB43
0x14010bd65  mov     rax, [rdi+60h]
0x14010bd69  mov     r9d, 2; unsigned int
0x14010bd6f  mov     rcx, [rax+70h]
0x14010bd73  mov     r14, [rcx+10h]
0x14010bd77  mov     r8, [rdi+130h]
0x14010bd7e  xor     esi, esi
0x14010bd80  mov     ebx, r9d
0x14010bd83  test    r8, r8
0x14010bd86  jz      short loc_14010BDF8
0x14010bd88  lea     rcx, [rdi+138h]
0x14010bd8f  test    r9b, 1
0x14010bd93  jz      short loc_14010BDC1
0x14010bd95  mov     r10d, [rcx]
0x14010bd98  cmp     [rdi+180h], r10d
0x14010bd9f  jnz     short loc_14010BDC1
0x14010bda1  lea     rdx, [rdi+13Ch]
0x14010bda8  mov     rsi, r8
0x14010bdab  bt      r9d, 2
0x14010bdb0  jnb     short loc_14010BDE3
0x14010bdb2  mov     eax, [rdx]
0x14010bdb4  cmp     [rdi+184h], eax
0x14010bdba  jz      short loc_14010BDDF
0x14010bdbc  and     ebx, 0FFFFFFFBh
0x14010bdbf  jmp     short loc_14010BDE3
0x14010bdc1  bt      r9d, 2
0x14010bdc6  jnb     short loc_14010BDF8
0x14010bdc8  lea     rdx, [rdi+13Ch]
0x14010bdcf  mov     eax, [rdx]
0x14010bdd1  cmp     [rdi+184h], eax
0x14010bdd7  jnz     short loc_14010BDF8
0x14010bdd9  mov     r10d, [rcx]
0x14010bddc  mov     rsi, r8
0x14010bddf  dec     eax
0x14010bde1  mov     [rdx], eax
0x14010bde3  lea     eax, [r10-1]
0x14010bde7  mov     [rcx], eax
0x14010bde9  test    eax, eax
0x14010bdeb  jnz     short loc_14010BDF8
0x14010bded  mov     qword ptr [rdi+130h], 0
0x14010bdf8  mov     r8, rdi; struct SmsPage *
0x14010bdfb  mov     rdx, r12; struct CmsTransactionCore *
0x14010bdfe  mov     rcx, r14; this
0x14010be01  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x14010be06  mov     rdi, rsi
0x14010be09  mov     r9d, ebx
0x14010be0c  test    rsi, rsi
0x14010be0f  jnz     loc_14010BD77
0x14010be15  jmp     loc_14010BB43
```
