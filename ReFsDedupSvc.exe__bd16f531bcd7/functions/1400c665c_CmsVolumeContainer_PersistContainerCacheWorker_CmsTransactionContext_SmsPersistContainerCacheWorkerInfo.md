# CmsVolumeContainer::PersistContainerCacheWorker(CmsTransactionContext *,SmsPersistContainerCacheWorkerInfo *)

- ea: `0x1400c665c`
- end: `0x1400c6ccc`
- name: `?PersistContainerCacheWorker@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsPersistContainerCacheWorkerInfo@@@Z`
- size: `1648`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsPersistContainerCacheWorkerInfo *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400c6ce0`

## callees

- `0x1400057e0`
- `0x1400057f8`
- `0x140091594`
- `0x1400c14dc`
- `0x1400c3ac0`
- `0x1400c4a28`
- `0x1400c6274`
- `0x1400c665c`
- `0x1400c6d70`
- `0x1400c70a8`
- `0x1400c8a14`
- `0x1400ccee0`
- `0x14011223c`
- `0x140115eb4`
- `0x140137f58`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1400c67a2`
- `ntdll!RtlRemoveEntryHashTable` at `0x1400c67a2`
- `ntdll!RtlIsZeroMemory` at `0x1400c6a25`
- `ntdll!RtlIsZeroMemory` at `0x1400c6a25`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400c6754`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400c6754`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400c67bb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400c67bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400c67c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400c67c9`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::PersistContainerCacheWorker(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        struct SmsPersistContainerCacheWorkerInfo *a3)
{
  char v3; // r12
  unsigned int v5; // edx
  int refreshed; // r15d
  unsigned int v7; // r9d
  __int64 v9; // rbx
  __int64 v10; // rcx
  unsigned __int64 v11; // r14
  char v12; // al
  char v13; // al
  char v14; // r13
  char v15; // al
  char v16; // al
  char *v17; // rcx
  __int64 v18; // rdx
  bool v19; // r9
  SmsAllocationRegionEx *v20; // rbx
  char v21; // r12
  signed __int64 v22; // rcx
  int v23; // ecx
  char v24; // al
  __int64 v25; // r8
  __int64 v26; // rdx
  char v27; // al
  __int64 v28; // rcx
  __int64 v29; // rdx
  CmsVolumeContainer *v30; // rcx
  CmsVolumeContainer *v31; // rcx
  CmsVolumeContainer *v32; // rcx
  int v33; // eax
  CmsAllocator *v34; // rcx
  __int64 v35; // r12
  CmsAllocator *v36; // rcx
  SmsAllocationRegionEx *v37; // r13
  CmsAllocator *v38; // rcx
  char v40; // [rsp+30h] [rbp-20h]
  SmsAllocationRegionEx *v41; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v42[4]; // [rsp+40h] [rbp-10h] BYREF
  char v43; // [rsp+90h] [rbp+40h]
  unsigned int v44; // [rsp+A0h] [rbp+50h]
  unsigned int v45; // [rsp+A8h] [rbp+58h]

  v3 = *((_BYTE *)a3 + 40);
  v5 = *((_DWORD *)a3 + 8);
  refreshed = 0;
  v7 = *((_DWORD *)a3 + 9);
  v40 = 0;
  v44 = v5;
  v43 = v3;
  v45 = v7;
  while ( 1 )
  {
    v9 = 0;
    if ( v5 < v7 )
    {
      do
      {
        if ( v9 )
          break;
        v10 = v5++;
        v9 = *(_QWORD *)(*((_QWORD *)this + 59) + 8 * v10);
      }
      while ( v5 < v7 );
      v44 = v5;
    }
    v41 = (SmsAllocationRegionEx *)v9;
    if ( !v9 )
      break;
    v11 = *(_QWORD *)(v9 + 592);
    if ( v3 )
    {
      if ( !*(_DWORD *)(v9 + 88) && !*(_DWORD *)(v9 + 84) )
      {
        v12 = *(_BYTE *)(v9 + 24);
        if ( (v12 & 0x48) == 0 && !*(_DWORD *)(v9 + 104) && !*(_DWORD *)(v9 + 108) && (v12 & 0x25) == 0 )
        {
          v13 = *(_BYTE *)(v9 + 25);
          if ( (v13 & 8) == 0
            && (*(_DWORD *)(v9 + 612) & 0x201) == 0
            && (v13 & 0x10) == 0
            && (int)++*(_DWORD *)(v9 + 92) >= 10 )
          {
            v14 = 0;
            RtlAcquireSRWLockExclusive((char *)this + 56);
            if ( !*(_DWORD *)(v9 + 88) && !*(_DWORD *)(v9 + 84) )
            {
              v15 = *(_BYTE *)(v9 + 24);
              if ( (v15 & 0x48) == 0 && !*(_DWORD *)(v9 + 104) && !*(_DWORD *)(v9 + 108) && (v15 & 0x25) == 0 )
              {
                v16 = *(_BYTE *)(v9 + 25);
                if ( (v16 & 8) == 0 && (*(_DWORD *)(v9 + 612) & 0x201) == 0 && (v16 & 0x10) == 0 )
                {
                  RtlRemoveEntryHashTable(*((_QWORD *)this + 6), v9, 0);
                  v14 = 1;
                }
              }
            }
            v17 = (char *)this + 56;
            if ( *((_QWORD *)this + 7) < 0x10u )
              RtlReleaseSRWLockExclusive(v17);
            else
              RtlReleaseSRWLockShared(v17);
            if ( v14 )
            {
              v18 = v44 - 1;
              *(_QWORD *)(*((_QWORD *)this + 59) + 8 * v18) = 0;
              SmsContainer::`scalar deleting destructor'((SmsContainer *)v9, v18);
LABEL_33:
              v3 = v43;
              goto LABEL_34;
            }
            v3 = v43;
          }
        }
      }
    }
    *(_QWORD *)a2 |= 0x400000000uLL;
    refreshed = CmsVolumeContainer::PinContainer(this, a2, v11, &v41, 0, 1u);
    *(_QWORD *)a2 &= ~0x400000000uLL;
    if ( refreshed < 0 )
      break;
    v20 = v41;
    if ( v3 )
    {
      v21 = *((_BYTE *)v41 + 25) & 0x10;
      if ( v21 )
      {
        refreshed = CmsVolumeContainer::RefreshContainerAllocationStatusInContainerEntry(this, a2, v41);
        if ( refreshed < 0 )
        {
LABEL_91:
          CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v22, a2, v11, 0);
          goto LABEL_94;
        }
      }
      v23 = *((_DWORD *)v20 + 153);
      if ( (v23 & 0x2000) != 0 || (*((_BYTE *)v20 + 24) & 4) != 0 )
      {
        v24 = v40;
        v25 = 1;
        if ( (v23 & 8) != 0 && !*((_DWORD *)v20 + 21) )
          v24 = 1;
      }
      else
      {
        v24 = v40;
        v25 = 1;
      }
      v22 = v23 & 0x2108;
      if ( (_DWORD)v22 == 8448 )
        v24 = 1;
      v40 = v24;
      if ( (*((_BYTE *)v20 + 24) & 0x40) != 0 )
      {
        v22 = *(_QWORD *)(*((_QWORD *)this + 1) + 2088LL);
        if ( *((_QWORD *)v20 + 5) <= v22 )
        {
          *((_DWORD *)v20 + 163) = 0;
          *((_BYTE *)v20 + 24) &= ~0x40u;
          *((_BYTE *)v20 + 24) |= 1u;
          v26 = *(_QWORD *)(*((_QWORD *)this + 1) + 2088LL);
          v27 = _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 44, 1u);
          v28 = 3LL * ((v27 + 1) & 0xF);
          *((_DWORD *)v20 + 2 * v28 + 46) = 12;
          *((_QWORD *)v20 + 3 * ((v27 + 1) & 0xF) + 24) = v26;
          *((_QWORD *)v20 + v28 + 25) = 0;
          _InterlockedDecrement((volatile signed __int32 *)this + 112);
          _InterlockedAdd64(
            (volatile signed __int64 *)(*((_QWORD *)this + 1) + 3704LL),
            *(unsigned int *)(*((_QWORD *)this + 1) + 84LL));
          _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)this + 1) + 3720LL), 1u);
          v29 = *((_QWORD *)this + 1);
          v22 = -*(_DWORD *)(v29 + 84);
          _InterlockedAdd64((volatile signed __int64 *)(v29 + 3728), v22);
        }
      }
      if ( (*((_BYTE *)v20 + 24) & 1) == 0 )
      {
        CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v22, a2, v11, 0);
        goto LABEL_33;
      }
      if ( v21 && (*((_BYTE *)this + 720) & 0x40) == 0 )
      {
        LODWORD(v41) = 0;
        v42[0] = 0;
        refreshed = CmsVolumeContainer::GetNumAllocatedForContainerEntry(
                      this,
                      a2,
                      (SmsAllocationRegionEx *)((char *)v20 + 592),
                      v19,
                      (unsigned int *)&v41,
                      v42);
        if ( refreshed < 0 )
          goto LABEL_91;
        if ( (unsigned int)v41 < v42[0] && (*((_BYTE *)v20 + 612) & 8) == 0 && (*((_BYTE *)this + 112) & 8) == 0 )
          *((_DWORD *)v20 + 158) = (_DWORD)v41;
      }
      if ( (*((_DWORD *)v20 + 153) & 0x2008) == 0x2000 )
      {
        v22 = *(_QWORD *)(*((_QWORD *)this + 1) + 3184LL);
        if ( *(_BYTE *)(v22 + 16) )
        {
          if ( !(unsigned __int8)RtlIsZeroMemory((char *)v20 + 672, (unsigned int)(16 * *((_DWORD *)this + 95)), v25) )
          {
            *((_DWORD *)v20 + 153) |= 0x100u;
            v40 = 1;
          }
        }
      }
      if ( (*((_BYTE *)v20 + 24) & 2) != 0 )
      {
        refreshed = CmsVolumeContainer::PersistNewContainer(this, a2, v20);
        CmsVolumeContainer::UnpinContainer(v30, a2, v11, 0);
      }
      else
      {
        CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v22, a2, v11, 0);
        refreshed = CmsVolumeContainer::PersistContainer(this, a2, v11);
        if ( refreshed < 0 )
          goto LABEL_94;
      }
      v3 = v43;
      v7 = v45;
      v5 = v44;
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 3184LL) + 16LL) && (*((_BYTE *)v20 + 612) & 8) == 0 )
      {
        memcpy_0(*((void **)v20 + 71), (char *)v20 + 672, (unsigned int)(16 * *((_DWORD *)this + 95)));
LABEL_34:
        v5 = v44;
        v7 = v45;
      }
    }
    else
    {
      v42[0] = 0;
      refreshed = CmsVolumeContainer::GetNumAllocatedForContainerEntry(
                    this,
                    a2,
                    (SmsAllocationRegionEx *)((char *)v41 + 592),
                    v19,
                    v42,
                    0);
      if ( refreshed < 0 )
      {
        CmsVolumeContainer::UnpinContainer(v31, a2, v11, 0);
        return (unsigned int)refreshed;
      }
      v32 = (CmsVolumeContainer *)v42[0];
      if ( v42[0] && (*((_BYTE *)v20 + 24) & 4) == 0
        || (*((_BYTE *)v20 + 612) & 8) == 0
        || *((_DWORD *)v20 + 21)
        || (*(_DWORD *)(*((_QWORD *)this + 1) + 3284LL) & 0x8000) != 0 )
      {
        v33 = *((_DWORD *)v20 + 153);
        if ( (v33 & 0x100) == 0
          || v42[0]
          || (v33 & 8) != 0
          || (v32 = (CmsVolumeContainer *)*((_QWORD *)this + 1), !*(_BYTE *)(*((_QWORD *)v32 + 398) + 16LL)) )
        {
          CmsVolumeContainer::UnpinContainer(v32, a2, v11, 0);
        }
        else
        {
          v34 = (CmsAllocator *)*((_QWORD *)v32 + 396);
          v35 = (unsigned int)(16 * *((_DWORD *)this + 95));
          v41 = 0;
          if ( (int)CmsAllocator::PinBitmapRegion(v34, a2, (SmsAllocationRegionEx *)((char *)v20 + v35 + 672), &v41) >= 0 )
          {
            v37 = v41;
            if ( CmsAllocator::TryProtectRegion(v36, v41, 1) >= 0 )
            {
              if ( *((_QWORD *)v37 + 1) == SmsAllocationRegionEx::GetTotalFree(v37)
                && (int)CmsIntegrityState::ResetIntegrityState(
                          *(CmsIntegrityState **)(*((_QWORD *)this + 1) + 3184LL),
                          a2,
                          (SmsAllocationRegionEx *)((char *)v20 + v35 + 672)) >= 0 )
              {
                memset_0((char *)v20 + 672, 0, (unsigned int)(16 * *((_DWORD *)this + 95)));
                *((_DWORD *)v20 + 153) &= ~0x100u;
                *((_BYTE *)v20 + 24) |= 1u;
              }
              CmsAllocator::TryProtectRegion(v38, v37, 0);
            }
          }
          CmsVolumeContainer::UnpinContainer(v36, a2, v11, 0);
          v3 = v43;
        }
      }
      else
      {
        CmsVolumeContainer::UnpinContainer((CmsVolumeContainer *)v42[0], a2, v11, 0);
        CmsVolumeContainer::DeleteContainer((CmsBPlusTable **)this, (CmsVolume **)a2, v11);
      }
      v5 = v44;
      v7 = v45;
    }
  }
  if ( !v3 )
    return (unsigned int)refreshed;
LABEL_94:
  if ( v40 )
    *((_BYTE *)this + 273) = 1;
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x1400c665c  mov     [rsp-38h+arg_8], rbx
0x1400c6661  push    rbp
0x1400c6662  push    rsi
0x1400c6663  push    rdi
0x1400c6664  push    r12
0x1400c6666  push    r13
0x1400c6668  push    r14
0x1400c666a  push    r15
0x1400c666c  mov     rbp, rsp
0x1400c666f  sub     rsp, 50h
0x1400c6673  mov     r12b, [r8+28h]
0x1400c6677  mov     rsi, rdx
0x1400c667a  mov     edx, [r8+20h]
0x1400c667e  xor     r15d, r15d
0x1400c6681  mov     r9d, [r8+24h]
0x1400c6685  mov     rdi, rcx
0x1400c6688  mov     [rbp+var_20], r15b
0x1400c668c  mov     [rbp+arg_10], edx
0x1400c668f  mov     [rbp+arg_0], r12b
0x1400c6693  mov     [rbp+arg_18], r9d
0x1400c6697  mov     r13d, 1
0x1400c669d  xor     ebx, ebx
0x1400c669f  cmp     edx, r9d
0x1400c66a2  jnb     short loc_1400C66C1
0x1400c66a4  test    rbx, rbx
0x1400c66a7  jnz     short loc_1400C66BE
0x1400c66a9  mov     rax, [rdi+1D8h]
0x1400c66b0  mov     ecx, edx
0x1400c66b2  add     edx, r13d
0x1400c66b5  mov     rbx, [rax+rcx*8]
0x1400c66b9  cmp     edx, r9d
0x1400c66bc  jb      short loc_1400C66A4
0x1400c66be  mov     [rbp+arg_10], edx
0x1400c66c1  mov     [rbp+var_18], rbx
0x1400c66c5  test    rbx, rbx
0x1400c66c8  jz      loc_1400C6C9E
0x1400c66ce  mov     r14, [rbx+250h]
0x1400c66d5  test    r12b, r12b
0x1400c66d8  jz      loc_1400C6810
0x1400c66de  cmp     dword ptr [rbx+58h], 0
0x1400c66e2  jnz     loc_1400C6810
0x1400c66e8  cmp     dword ptr [rbx+54h], 0
0x1400c66ec  jnz     loc_1400C6810
0x1400c66f2  mov     al, [rbx+18h]
0x1400c66f5  test    al, 48h
0x1400c66f7  jnz     loc_1400C6810
0x1400c66fd  cmp     dword ptr [rbx+68h], 0
0x1400c6701  jnz     loc_1400C6810
0x1400c6707  cmp     dword ptr [rbx+6Ch], 0
0x1400c670b  jnz     loc_1400C6810
0x1400c6711  test    al, 25h
0x1400c6713  jnz     loc_1400C6810
0x1400c6719  mov     al, [rbx+19h]
0x1400c671c  test    al, 8
0x1400c671e  jnz     loc_1400C6810
0x1400c6724  test    dword ptr [rbx+264h], 201h
0x1400c672e  jnz     loc_1400C6810
0x1400c6734  test    al, 10h
0x1400c6736  jnz     loc_1400C6810
0x1400c673c  add     [rbx+5Ch], r13d
0x1400c6740  cmp     dword ptr [rbx+5Ch], 0Ah
0x1400c6744  jl      loc_1400C6810
0x1400c674a  lea     r12, [rdi+38h]
0x1400c674e  xor     r13b, r13b
0x1400c6751  mov     rcx, r12
0x1400c6754  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400c675b  nop     dword ptr [rax+rax+00h]
0x1400c6760  xor     ecx, ecx
0x1400c6762  cmp     [rbx+58h], ecx
0x1400c6765  jnz     short loc_1400C67B1
0x1400c6767  cmp     [rbx+54h], ecx
0x1400c676a  jnz     short loc_1400C67B1
0x1400c676c  mov     al, [rbx+18h]
0x1400c676f  test    al, 48h
0x1400c6771  jnz     short loc_1400C67B1
0x1400c6773  cmp     [rbx+68h], ecx
0x1400c6776  jnz     short loc_1400C67B1
0x1400c6778  cmp     [rbx+6Ch], ecx
0x1400c677b  jnz     short loc_1400C67B1
0x1400c677d  test    al, 25h
0x1400c677f  jnz     short loc_1400C67B1
0x1400c6781  mov     al, [rbx+19h]
0x1400c6784  test    al, 8
0x1400c6786  jnz     short loc_1400C67B1
0x1400c6788  test    dword ptr [rbx+264h], 201h
0x1400c6792  jnz     short loc_1400C67B1
0x1400c6794  test    al, 10h
0x1400c6796  jnz     short loc_1400C67B1
0x1400c6798  mov     rcx, [rdi+30h]
0x1400c679c  xor     r8d, r8d
0x1400c679f  mov     rdx, rbx
0x1400c67a2  call    cs:__imp_RtlRemoveEntryHashTable
0x1400c67a9  nop     dword ptr [rax+rax+00h]
0x1400c67ae  mov     r13b, 1
0x1400c67b1  cmp     qword ptr [r12], 10h
0x1400c67b6  mov     rcx, r12
0x1400c67b9  jb      short loc_1400C67C9
0x1400c67bb  call    cs:__imp_RtlReleaseSRWLockShared
0x1400c67c2  nop     dword ptr [rax+rax+00h]
0x1400c67c7  jmp     short loc_1400C67D5
0x1400c67c9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400c67d0  nop     dword ptr [rax+rax+00h]
0x1400c67d5  test    r13b, r13b
0x1400c67d8  jz      short loc_1400C6806
0x1400c67da  mov     edx, [rbp+arg_10]
0x1400c67dd  mov     rcx, rbx; this
0x1400c67e0  mov     rax, [rdi+1D8h]
0x1400c67e7  dec     edx; unsigned int
0x1400c67e9  mov     qword ptr [rax+rdx*8], 0
0x1400c67f1  call    ??_GSmsContainer@@QEAAPEAXI@Z; SmsContainer::`scalar deleting destructor'(uint)
0x1400c67f6  mov     r12b, [rbp+arg_0]
0x1400c67fa  mov     edx, [rbp+arg_10]
0x1400c67fd  mov     r9d, [rbp+arg_18]
0x1400c6801  jmp     loc_1400C6697
0x1400c6806  mov     r12b, [rbp+arg_0]
0x1400c680a  mov     r13d, 1
0x1400c6810  mov     rax, 400000000h
0x1400c681a  mov     byte ptr [rsp+50h+var_28], r13b; unsigned __int8
0x1400c681f  or      [rsi], rax
0x1400c6822  lea     r9, [rbp+var_18]; struct SmsContainer **
0x1400c6826  mov     r8, r14; unsigned __int64
0x1400c6829  mov     [rsp+50h+var_30], 0; struct _SmsContainerOverflowPinList *
0x1400c6832  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6835  mov     rcx, rdi; this
0x1400c6838  call    ?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@E@Z; CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar)
0x1400c683d  mov     r15d, eax
0x1400c6840  mov     rax, 0FFFFFFFBFFFFFFFFh
0x1400c684a  and     [rsi], rax
0x1400c684d  test    r15d, r15d
0x1400c6850  js      loc_1400C6C9E
0x1400c6856  mov     rbx, [rbp+var_18]
0x1400c685a  test    r12b, r12b
0x1400c685d  jz      loc_1400C6AEC
0x1400c6863  mov     r12b, [rbx+19h]
0x1400c6867  and     r12b, 10h
0x1400c686b  jz      short loc_1400C6886
0x1400c686d  mov     r8, rbx; struct SmsContainer *
0x1400c6870  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6873  mov     rcx, rdi; this
0x1400c6876  call    ?RefreshContainerAllocationStatusInContainerEntry@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@AEAUSmsContainer@@@Z; CmsVolumeContainer::RefreshContainerAllocationStatusInContainerEntry(CmsTransactionContext *,SmsContainer &)
0x1400c687b  mov     r15d, eax
0x1400c687e  test    eax, eax
0x1400c6880  js      loc_1400C6C7E
0x1400c6886  lea     r13, [rbx+250h]
0x1400c688d  mov     ecx, [r13+14h]
0x1400c6891  bt      ecx, 0Dh
0x1400c6895  jb      short loc_1400C689D
0x1400c6897  test    byte ptr [rbx+18h], 4
0x1400c689b  jz      short loc_1400C68B8
0x1400c689d  mov     eax, dword ptr [rbp+var_20]
0x1400c68a0  mov     r8d, 1
0x1400c68a6  test    cl, 8
0x1400c68a9  jz      short loc_1400C68C1
0x1400c68ab  cmp     dword ptr [rbx+54h], 0
0x1400c68af  movzx   eax, al
0x1400c68b2  cmovz   eax, r8d
0x1400c68b6  jmp     short loc_1400C68C1
0x1400c68b8  mov     eax, dword ptr [rbp+var_20]
0x1400c68bb  mov     r8d, 1
0x1400c68c1  and     ecx, 2108h
0x1400c68c7  movzx   eax, al
0x1400c68ca  cmp     ecx, 2100h
0x1400c68d0  cmovz   eax, r8d
0x1400c68d4  test    byte ptr [rbx+18h], 40h
0x1400c68d8  mov     [rbp+var_20], al
0x1400c68db  jz      loc_1400C6987
0x1400c68e1  mov     rax, [rdi+8]
0x1400c68e5  mov     rcx, [rax+828h]
0x1400c68ec  cmp     [rbx+28h], rcx
0x1400c68f0  jg      loc_1400C6987
0x1400c68f6  mov     dword ptr [rbx+28Ch], 0
0x1400c6900  and     byte ptr [rbx+18h], 0BFh
0x1400c6904  or      [rbx+18h], r8b
0x1400c6908  mov     rax, [rdi+8]
0x1400c690c  mov     rdx, [rax+828h]
0x1400c6913  mov     eax, r8d
0x1400c6916  lock xadd [rbx+0B0h], eax
0x1400c691e  add     eax, r8d
0x1400c6921  and     eax, 0Fh
0x1400c6924  lea     rcx, [rax+rax*2]
0x1400c6928  mov     dword ptr [rbx+rcx*8+0B8h], 0Ch
0x1400c6933  lea     rax, [rax+rax*2]
0x1400c6937  mov     [rbx+rax*8+0C0h], rdx
0x1400c693f  mov     qword ptr [rbx+rcx*8+0C8h], 0
0x1400c694b  nop
0x1400c694c  lock dec dword ptr [rdi+1C0h]
0x1400c6953  nop
0x1400c6954  mov     rcx, [rdi+8]
0x1400c6958  mov     eax, [rcx+54h]
0x1400c695b  nop
0x1400c695c  lock add [rcx+0E78h], rax
0x1400c6964  nop
0x1400c6965  mov     rax, [rdi+8]
0x1400c6969  lock add [rax+0E88h], r8
0x1400c6971  mov     rdx, [rdi+8]
0x1400c6975  mov     eax, [rdx+54h]
0x1400c6978  nop
0x1400c6979  neg     eax
0x1400c697b  movsxd  rcx, eax; this
0x1400c697e  lock add [rdx+0E90h], rcx
0x1400c6986  nop
0x1400c6987  test    [rbx+18h], r8b
0x1400c698b  jz      loc_1400C6AD9
0x1400c6991  test    r12b, r12b
0x1400c6994  jz      short loc_1400C69F5
0x1400c6996  test    byte ptr [rdi+2D0h], 40h
0x1400c699d  jnz     short loc_1400C69F5
0x1400c699f  lea     rax, [rbp+var_10]
0x1400c69a3  mov     dword ptr [rbp+var_18], 0
0x1400c69aa  mov     [rsp+50h+var_28], rax; unsigned int *
0x1400c69af  mov     r8, r13; struct _SmsContainerEntry *
0x1400c69b2  lea     rax, [rbp+var_18]
0x1400c69b6  mov     [rbp+var_10], 0
0x1400c69bd  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c69c0  mov     [rsp+50h+var_30], rax; unsigned int *
0x1400c69c5  mov     rcx, rdi; this
0x1400c69c8  call    ?GetNumAllocatedForContainerEntry@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@AEBU_SmsContainerEntry@@_NPEAK3@Z; CmsVolumeContainer::GetNumAllocatedForContainerEntry(CmsTransactionContext *,_SmsContainerEntry const &,bool,ulong *,ulong *)
0x1400c69cd  mov     r15d, eax
0x1400c69d0  test    eax, eax
0x1400c69d2  js      loc_1400C6C7E
0x1400c69d8  mov     eax, dword ptr [rbp+var_18]
0x1400c69db  cmp     eax, [rbp+var_10]
0x1400c69de  jnb     short loc_1400C69F5
0x1400c69e0  test    byte ptr [rbx+264h], 8
0x1400c69e7  jnz     short loc_1400C69F5
0x1400c69e9  test    byte ptr [rdi+70h], 8
0x1400c69ed  jnz     short loc_1400C69F5
0x1400c69ef  mov     [rbx+278h], eax
0x1400c69f5  mov     eax, [rbx+264h]
0x1400c69fb  and     eax, 2008h
0x1400c6a00  cmp     eax, 2000h
0x1400c6a05  jnz     short loc_1400C6A41
0x1400c6a07  mov     rax, [rdi+8]
0x1400c6a0b  mov     rcx, [rax+0C70h]
0x1400c6a12  cmp     byte ptr [rcx+10h], 0
0x1400c6a16  jz      short loc_1400C6A41
0x1400c6a18  mov     edx, [rdi+17Ch]
0x1400c6a1e  lea     rcx, [r13+50h]
0x1400c6a22  shl     edx, 4
0x1400c6a25  call    cs:__imp_RtlIsZeroMemory
0x1400c6a2c  nop     dword ptr [rax+rax+00h]
0x1400c6a31  test    al, al
0x1400c6a33  jnz     short loc_1400C6A41
0x1400c6a35  bts     dword ptr [rbx+264h], 8
0x1400c6a3d  mov     [rbp+var_20], 1
0x1400c6a41  test    byte ptr [rbx+18h], 2
0x1400c6a45  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6a48  jz      short loc_1400C6A68
0x1400c6a4a  mov     r8, rbx; struct SmsContainer *
0x1400c6a4d  mov     rcx, rdi; this
0x1400c6a50  call    ?PersistNewContainer@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::PersistNewContainer(CmsTransactionContext *,SmsContainer *)
0x1400c6a55  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1400c6a58  mov     r8, r14; unsigned __int64
0x1400c6a5b  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6a5e  mov     r15d, eax
0x1400c6a61  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1400c6a66  jmp     short loc_1400C6A8C
0x1400c6a68  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1400c6a6b  mov     r8, r14; unsigned __int64
0x1400c6a6e  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1400c6a73  mov     r8, r14; unsigned __int64
0x1400c6a76  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6a79  mov     rcx, rdi; this
0x1400c6a7c  call    ?PersistContainer@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_K@Z; CmsVolumeContainer::PersistContainer(CmsTransactionContext *,unsigned __int64)
0x1400c6a81  mov     r15d, eax
0x1400c6a84  test    eax, eax
0x1400c6a86  js      loc_1400C6CA3
0x1400c6a8c  mov     rax, [rdi+8]
0x1400c6a90  mov     r12b, [rbp+arg_0]
0x1400c6a94  mov     r9d, [rbp+arg_18]
0x1400c6a98  mov     rdx, [rax+0C70h]
0x1400c6a9f  cmp     byte ptr [rdx+10h], 0
0x1400c6aa3  mov     edx, [rbp+arg_10]
0x1400c6aa6  jz      loc_1400C6697
0x1400c6aac  test    byte ptr [rbx+264h], 8
0x1400c6ab3  jnz     loc_1400C6697
0x1400c6ab9  mov     r8d, [rdi+17Ch]
0x1400c6ac0  lea     rdx, [r13+50h]; Src
0x1400c6ac4  mov     rcx, [rbx+238h]; void *
0x1400c6acb  shl     r8d, 4; Size
0x1400c6acf  call    memcpy_0
0x1400c6ad4  jmp     loc_1400C67FA
0x1400c6ad9  xor     r9d, r9d; struct _SmsContainerOverflowPinList *
0x1400c6adc  mov     r8, r14; unsigned __int64
0x1400c6adf  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6ae2  call    ?UnpinContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@_KPEAU_SmsContainerOverflowPinList@@@Z; CmsVolumeContainer::UnpinContainer(CmsTransactionContext *,unsigned __int64,_SmsContainerOverflowPinList *)
0x1400c6ae7  jmp     loc_1400C67F6
0x1400c6aec  lea     rcx, [rbp+var_10]
0x1400c6af0  mov     [rsp+50h+var_28], 0; unsigned int *
0x1400c6af9  mov     [rsp+50h+var_30], rcx; unsigned int *
0x1400c6afe  lea     r8, [rbx+250h]; struct _SmsContainerEntry *
0x1400c6b05  mov     rcx, rdi; this
0x1400c6b08  mov     [rbp+var_10], 0
0x1400c6b0f  mov     rdx, rsi; struct CmsTransactionContext *
0x1400c6b12  call    ?GetNumAllocatedForContainerEntry@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@AEBU_SmsContainerEntry@@_NPEAK3@Z; CmsVolumeContainer::GetNumAllocatedForContainerEntry(CmsTransactionContext *,_SmsContainerEntry const &,bool,ulong *,ulong *)
0x1400c6b17  mov     r15d, eax
0x1400c6b1a  test    eax, eax
0x1400c6b1c  js      loc_1400C6C8E
0x1400c6b22  mov     ecx, [rbp+var_10]; this
0x1400c6b25  test    ecx, ecx
  ... truncated ...
```
