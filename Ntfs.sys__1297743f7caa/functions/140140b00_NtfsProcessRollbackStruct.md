# NtfsProcessRollbackStruct

- ea: `0x140140b00`
- end: `0x140140fa4`
- name: `NtfsProcessRollbackStruct`
- size: `1188`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140129550`
- `0x14012b270`
- `0x140140370`
- `0x1401406b0`

## callees

- `0x1400211b0`
- `0x14010c0a0`
- `0x140140b00`
- `0x140140fac`
- `0x140173b00`
- `0x140196e80`
- `0x1401d94d4`
- `0x14020d75c`
- `0x14022f51c`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c8729`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c8729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140140c0d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c85de`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140140c0d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c85de`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c8918`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c8918`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140bd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140cd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140e0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140bd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140cd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140e0b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140140ef4`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140140ef4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140c81`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140d6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140e35`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c8b6c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140c81`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140d6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140e35`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c8b6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140d14`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140db0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c865c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8758`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8bb3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140d14`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140db0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c865c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8758`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8bb3`

## pseudocode

```c
void __fastcall NtfsProcessRollbackStruct(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  int v3; // eax
  int v5; // eax
  _DWORD *v6; // rdi
  unsigned __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  unsigned __int16 **v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // rbp
  void *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _DWORD *v22; // r8
  __int64 v23; // rcx
  struct _ERESOURCE *v24; // rcx
  _QWORD *v25; // rdx
  signed __int64 v26; // r8
  signed __int64 v27; // rax
  bool v28; // zf
  __int64 v29; // rtt
  signed __int64 v30; // rax
  __int64 v31; // rtt
  signed __int64 v32; // r8
  signed __int64 v33; // rax
  __int64 v34; // rtt
  signed __int64 v35; // rax
  __int64 v36; // rtt
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  signed __int64 v44; // r8
  signed __int64 v45; // rax
  __int64 v46; // rtt
  signed __int64 v47; // rax
  __int64 v48; // rtt
  unsigned __int16 *v49; // rdx
  unsigned __int16 *v50; // r9
  _DWORD *v51; // r14
  unsigned __int16 *v52; // rsi
  char **v53; // rdi
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned __int16 *v56; // r15
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r9
  __int64 v63; // r8
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // eax

  v3 = *a2;
  if ( (_WORD)v3 != 1831 )
  {
    if ( (a3 & 0x10) != 0 )
    {
      if ( v3 == 1827 )
      {
        if ( (*((_DWORD *)a2 + 1) & 0x100) != 0 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 60LL));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 64LL), 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb(*((char **)a2 + 10));
        }
      }
      else if ( v3 == 1864 && (*((_DWORD *)a2 + 1) & 1) != 0 )
      {
        v19 = (void *)*((_QWORD *)a2 + 5);
        if ( v19 )
          ExFreePoolWithTag(v19, 0);
      }
      v9 = *((_QWORD *)a2 + 1);
      v10 = a2 + 4;
      if ( *(unsigned __int16 **)(v9 + 8) != a2 + 4 )
        goto LABEL_24;
      goto LABEL_16;
    }
    if ( (a3 & 5) == 0 )
      return;
    if ( v3 != 1827 )
    {
      v7 = (unsigned int)(v3 - 1828);
      switch ( *a2 )
      {
        case 0x724u:
          if ( (a3 & 4) == 0 )
            goto LABEL_79;
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*((_QWORD *)a2 + 3) + 136LL), 1u);
          if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
            **(_DWORD **)(*((_QWORD *)a2 + 3) + 48LL) = 0;
          if ( (*((_DWORD *)a2 + 1) & 2) == 0 )
            goto LABEL_70;
          ExAcquireResourceExclusiveLite(
            (PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL) + 24LL) + 80LL),
            1u);
          v15 = (_QWORD *)*((_QWORD *)a2 + 4);
          v16 = *v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_24;
          v17 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v17 != v15 )
            goto LABEL_24;
          *v17 = v16;
          *(_QWORD *)(v16 + 8) = v17;
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL) + 24LL) + 80LL));
          v18 = *(void **)(*((_QWORD *)a2 + 4) + 32LL);
          if ( v18 )
            TxfDereferenceTxfFcb(v18);
          ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, *((PVOID *)a2 + 4));
LABEL_70:
          if ( (*((_DWORD *)a2 + 1) & 4) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 20LL) -= *((_DWORD *)a2 + 10);
          if ( (*((_DWORD *)a2 + 1) & 8) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~4u;
          if ( (*((_DWORD *)a2 + 1) & 0x20) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~0x200000u;
          if ( (*((_DWORD *)a2 + 1) & 0x10) != 0 )
          {
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~0x80000u;
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 52LL) = 0;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 48LL) = 0;
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 54LL) = 0;
          }
          ExReleaseResourceLite(*(PERESOURCE *)(*((_QWORD *)a2 + 3) + 136LL));
LABEL_79:
          *((_DWORD *)a2 + 1) &= 0xFFFFFFC0;
          *((_DWORD *)a2 + 10) = 0;
          break;
        case 0x725u:
          if ( (a3 & 4) != 0 )
          {
            if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
              TxfReserveSpaceForAbortPriv(
                0,
                *(_QWORD *)(*((_QWORD *)a2 + 3) + 208LL),
                *((_QWORD *)a2 + 3),
                *((_QWORD *)a2 + 5));
            if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
              TxfReleaseSpaceForAbortPriv(*(_QWORD *)(*((_QWORD *)a2 + 3) + 208LL), *((_QWORD *)a2 + 3));
          }
          goto LABEL_86;
        case 0x726u:
          if ( (a3 & 4) != 0 )
          {
            if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
              *(_OWORD *)(*((_QWORD *)a2 + 3) + 264LL) = *((_OWORD *)a2 + 2);
            if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
            {
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 452LL) = *((_DWORD *)a2 + 12);
              *(_BYTE *)(*((_QWORD *)a2 + 3) + 462LL) = *((_BYTE *)a2 + 54);
              *(_WORD *)(*((_QWORD *)a2 + 3) + 460LL) = a2[26];
            }
            if ( (*((_DWORD *)a2 + 1) & 4) != 0 )
            {
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) &= ~*((_DWORD *)a2 + 15);
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) |= *((_DWORD *)a2 + 15) & *((_DWORD *)a2 + 14);
            }
          }
          if ( (a2[2] & 8) != 0 && (a3 & 1) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) &= ~0x2000000u;
          *((_DWORD *)a2 + 1) &= 0xFFFFFFF0;
          break;
        case 0x728u:
          if ( (a3 & 4) == 0 )
            goto LABEL_86;
          if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
          {
            v7 = *((_QWORD *)a2 + 3);
            *(_DWORD *)v7 = *((_DWORD *)a2 + 8);
          }
          if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
          {
            LOBYTE(a3) = 1;
            NtfsAcquireResourceExclusive(v7, **(_QWORD **)(*((_QWORD *)a2 + 5) + 96LL), a3);
            RtlDeleteElementGenericTableAvl(*((PRTL_AVL_TABLE *)a2 + 5), *((PVOID *)a2 + 3));
            v23 = **(_QWORD **)(*((_QWORD *)a2 + 5) + 96LL);
            if ( *(_WORD *)v23 == 1794 )
              v24 = (struct _ERESOURCE *)(*(_QWORD *)(v23 + 104) + 64LL);
            else
              v24 = *(struct _ERESOURCE **)(v23 + 8);
            ExReleaseResourceLite(v24);
            *((_DWORD *)a2 + 1) &= 0xFFFFFFFC;
          }
          else
          {
LABEL_86:
            *((_DWORD *)a2 + 1) &= 0xFFFFFFFC;
          }
          break;
        case 0x742u:
          if ( (a3 & 4) != 0 && (*((_DWORD *)a2 + 1) & 1) != 0 )
            *(_QWORD *)(*((_QWORD *)a2 + 3) + 64LL) = *((_QWORD *)a2 + 4);
          goto LABEL_19;
        case 0x748u:
          if ( (*((_DWORD *)a2 + 1) & 1) == 0 )
            goto LABEL_19;
          if ( (a3 & 4) != 0 )
          {
            v12 = 0;
            ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)a2 + 3) + 10792LL), 1u);
            if ( *((_QWORD *)a2 + 5) )
              v12 = NtfsCalculateVcbStorageReserveTotalReserved(*((_QWORD *)a2 + 3));
            v13 = *((_QWORD *)a2 + 3);
            if ( *(_QWORD *)(v13 + 10904) )
              v12 -= NtfsCalculateVcbStorageReserveTotalReserved(*((_QWORD *)a2 + 3));
            if ( v12 )
            {
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v13 + 720));
              *(_QWORD *)(*((_QWORD *)a2 + 3) + 328LL) += v12;
              v20 = (_QWORD *)*((_QWORD *)a2 + 3);
              v21 = v20[41];
              if ( v12 <= 0 )
              {
                if ( v21 < v20[1039] )
                  v20[1039] = v21;
                v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                v32 = v25[38] - ((__int64)v25[41] >> 8) - v25[796] - v25[41];
                if ( v32 <= 0 )
                  v32 = 0;
                do
                {
                  v33 = v25[1043];
                  if ( v32 >= v33 )
                    break;
                  v34 = v25[1043];
                  v28 = v34 == _InterlockedCompareExchange64(v25 + 1043, v32, v33);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
                do
                {
                  v35 = v25[1044];
                  if ( v32 <= v35 )
                    break;
                  v36 = v25[1044];
                  v28 = v36 == _InterlockedCompareExchange64(v25 + 1044, v32, v35);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
              }
              else
              {
                if ( v21 > v20[1040] )
                  v20[1040] = v21;
                v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                v26 = v25[38] - ((__int64)v25[41] >> 8) - v25[796] - v25[41];
                if ( v26 <= 0 )
                  v26 = 0;
                do
                {
                  v27 = v25[1043];
                  if ( v26 >= v27 )
                    break;
                  v29 = v25[1043];
                  v28 = v29 == _InterlockedCompareExchange64(v25 + 1043, v26, v27);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
                do
                {
                  v30 = v25[1044];
                  if ( v26 <= v30 )
                    break;
                  v31 = v25[1044];
                  v28 = v31 == _InterlockedCompareExchange64(v25 + 1044, v26, v30);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
              }
              v37 = v25[41];
              v38 = v37;
              if ( v37 <= 0 )
                v38 = 0;
              if ( v38 >= 0xFFFFFFFFLL )
              {
                v37 = 0xFFFFFFFFLL;
              }
              else if ( v37 <= 0 )
              {
                v37 = 0;
              }
              v25[41] = v37;
              v39 = *((_QWORD *)a2 + 3);
              v40 = *(_QWORD *)(v39 + 328);
              if ( v40 > *(_QWORD *)(v39 + 8320) )
                *(_QWORD *)(v39 + 8320) = v40;
              v41 = *((_QWORD *)a2 + 3);
              v42 = *(_QWORD *)(v41 + 328);
              if ( v42 < *(_QWORD *)(v41 + 8312) )
                *(_QWORD *)(v41 + 8312) = v42;
              v43 = *((_QWORD *)a2 + 3);
              v44 = *(_QWORD *)(v43 + 304)
                  - (*(__int64 *)(v43 + 328) >> 8)
                  - *(_QWORD *)(v43 + 6368)
                  - *(_QWORD *)(v43 + 328);
              if ( v44 <= 0 )
                v44 = 0;
              do
              {
                v45 = *(_QWORD *)(v43 + 8344);
                if ( v44 >= v45 )
                  break;
                v46 = *(_QWORD *)(v43 + 8344);
                v28 = v46 == _InterlockedCompareExchange64((volatile signed __int64 *)(v43 + 8344), v44, v45);
                v43 = *((_QWORD *)a2 + 3);
              }
              while ( !v28 );
              do
              {
                v47 = *(_QWORD *)(v43 + 8352);
                if ( v44 <= v47 )
                  break;
                v48 = *(_QWORD *)(v43 + 8352);
                v28 = v48 == _InterlockedCompareExchange64((volatile signed __int64 *)(v43 + 8352), v44, v47);
                v43 = *((_QWORD *)a2 + 3);
              }
              while ( !v28 );
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v43 + 720));
            }
            v14 = *(void **)(*((_QWORD *)a2 + 3) + 10904LL);
            if ( v14 )
              ExFreePoolWithTag(v14, 0);
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 10900LL) = *((_DWORD *)a2 + 8);
            *(_QWORD *)(*((_QWORD *)a2 + 3) + 10904LL) = *((_QWORD *)a2 + 5);
            NtfsCalculateVcbStorageReserveFields(*((_QWORD *)a2 + 3));
            ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)a2 + 3) + 10792LL));
            *((_DWORD *)a2 + 1) &= ~1u;
          }
          else
          {
            v8 = (void *)*((_QWORD *)a2 + 5);
            if ( v8 )
            {
              ExFreePoolWithTag(v8, 0);
              *((_DWORD *)a2 + 1) &= ~1u;
            }
            else
            {
LABEL_19:
              *((_DWORD *)a2 + 1) &= ~1u;
            }
          }
          break;
        default:
          break;
      }
LABEL_8:
      if ( *((_DWORD *)a2 + 1) )
        return;
      v9 = *((_QWORD *)a2 + 1);
      v10 = a2 + 4;
      if ( *(unsigned __int16 **)(v9 + 8) != a2 + 4 )
LABEL_24:
        __fastfail(3u);
LABEL_16:
      v11 = (unsigned __int16 **)*((_QWORD *)v10 + 1);
      if ( *v11 == v10 )
      {
        *v11 = (unsigned __int16 *)v9;
        *(_QWORD *)(v9 + 8) = v11;
        ExFreeToLookasideListEx(&NtfsRollbackStructLookasideList, a2);
        return;
      }
      goto LABEL_24;
    }
    v5 = *((_DWORD *)a2 + 1);
    v6 = a2 + 2;
    if ( (a3 & 4) == 0 )
    {
      if ( (v5 & 0x100) != 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 60LL));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 64LL), 0xFFFFFFFF) == 1 )
          TxfDeleteTxfRmcb(*((char **)a2 + 10));
      }
LABEL_7:
      *v6 &= 0xFFFFC000;
      *((_DWORD *)a2 + 9) = 0;
      a2[53] = 0;
      goto LABEL_8;
    }
    v22 = a2 + 2;
    if ( (v5 & 1) != 0 )
    {
      *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~*((_DWORD *)a2 + 9);
      *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) |= *((_DWORD *)a2 + 9) & *((_DWORD *)a2 + 8);
    }
    v49 = a2 + 12;
    if ( (*v6 & 0x1000) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)v49 + 136LL) = *((_QWORD *)a2 + 14);
      *(_QWORD *)(*(_QWORD *)v49 + 144LL) = *((_QWORD *)a2 + 15);
      *(_QWORD *)(*(_QWORD *)v49 + 192LL) = *((_QWORD *)a2 + 16);
    }
    else
    {
      v22 = v6;
    }
    v50 = a2 + 12;
    if ( (*v6 & 2) != 0 )
    {
      *(_WORD *)(*(_QWORD *)v49 + 188LL) -= a2[53];
      *(_WORD *)(*(_QWORD *)v49 + 190LL) -= a2[52];
    }
    if ( (*v22 & 4) != 0 )
    {
      v51 = a2 + 2;
      *(_QWORD *)(*(_QWORD *)v49 + 240LL) = *((_QWORD *)a2 + 7);
    }
    else
    {
      v51 = v22;
      v50 = a2 + 12;
    }
    if ( (*v22 & 8) != 0 )
      *(_QWORD *)(*(_QWORD *)v50 + 256LL) = *((_QWORD *)a2 + 8);
    else
      v51 = v22;
    if ( (*v22 & 0x80u) == 0 )
    {
      v52 = v50;
    }
    else
    {
      v52 = a2 + 12;
      *(_QWORD *)(*(_QWORD *)v50 + 248LL) = *((_QWORD *)a2 + 9);
    }
    if ( (*v51 & 0x100) != 0 )
    {
      v53 = (char **)(a2 + 40);
      v54 = *((_QWORD *)a2 + 10);
      if ( *(_QWORD *)(*(_QWORD *)v50 + 320LL) != v54 )
      {
        if ( v54 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v54 + 64));
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 36LL));
          v52 = a2 + 12;
        }
        v55 = *(_QWORD *)(*(_QWORD *)v52 + 320LL);
        if ( v55
          && (_InterlockedDecrement((volatile signed __int32 *)(v55 + 36)),
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)v52 + 320LL) + 64LL),
                0xFFFFFFFF) == 1) )
        {
          TxfDeleteTxfRmcb(*(char **)(*(_QWORD *)v52 + 320LL));
        }
        else
        {
          v53 = (char **)(a2 + 40);
        }
        v51 = a2 + 2;
        *(_QWORD *)(*(_QWORD *)v52 + 320LL) = *((_QWORD *)a2 + 10);
      }
      _InterlockedDecrement((volatile signed __int32 *)*v53 + 15);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v53 + 16, 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*v53);
    }
    if ( (*v51 & 0x10) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v52 + 176LL) &= ~*((_DWORD *)a2 + 11);
      *(_DWORD *)(*(_QWORD *)v52 + 176LL) |= *((_DWORD *)a2 + 11) & *((_DWORD *)a2 + 10);
    }
    if ( (*v51 & 0x20) != 0 )
    {
      v56 = a2 + 12;
      v6 = a2 + 2;
      *(_DWORD *)(*(_QWORD *)v52 + 184LL) &= ~*((_DWORD *)a2 + 13);
      *(_DWORD *)(*(_QWORD *)v52 + 184LL) |= *((_DWORD *)a2 + 13) & *((_DWORD *)a2 + 12);
    }
    else
    {
      v6 = v51;
      v56 = v52;
    }
    if ( (*v51 & 0x40) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v52 + 180LL) = *((_DWORD *)a2 + 22);
    }
    else
    {
      v6 = v51;
      v56 = v52;
    }
    if ( (*v51 & 0x2000) != 0 )
      *(_BYTE *)(*(_QWORD *)v56 + 37LL) = *((_BYTE *)a2 + 92);
    if ( (*v6 & 0x200) == 0 )
      goto LABEL_7;
    if ( (*v6 & 0x400) == 0 )
    {
      v57 = *(_QWORD *)v56;
      v58 = *((_QWORD *)a2 + 12);
      if ( v58 == *(_QWORD *)(*(_QWORD *)v56 + 40LL) )
      {
        if ( *((_BYTE *)a2 + 93) == *(_BYTE *)(v57 + 38) || !v58 )
          goto LABEL_167;
        v56 = a2 + 12;
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v57 + 96) + 10688LL), 1u);
      NtfsAdjustStorageReserveClustersUsed(
        v59,
        *(_QWORD *)(*(_QWORD *)v56 + 96LL),
        *(unsigned __int8 *)(*(_QWORD *)v56 + 38LL),
        -*(_QWORD *)(*(_QWORD *)v56 + 40LL));
      NtfsAdjustStorageReserveClustersUsed(
        v60,
        *(_QWORD *)(*(_QWORD *)v56 + 96LL),
        *((unsigned __int8 *)a2 + 93),
        *((_QWORD *)a2 + 12));
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)v56 + 96LL) + 10688LL));
    }
LABEL_167:
    if ( (*((_DWORD *)a2 + 1) & 0x800) != 0 )
    {
      v61 = *((_QWORD *)a2 + 3);
      v62 = *(_QWORD *)(v61 + 96);
      v63 = *(unsigned __int8 *)(v61 + 38);
      v64 = *(unsigned __int16 *)(v62 + 11524);
      if ( _bittest(&v64, v63) )
        *(_QWORD *)(v62 + 8 * v63 + 11536) -= *(_QWORD *)(v61 + 40);
      v65 = *((unsigned __int8 *)a2 + 93);
      v66 = *(_QWORD *)(*((_QWORD *)a2 + 3) + 96LL);
      v67 = *(unsigned __int16 *)(v66 + 11524);
      if ( _bittest(&v67, v65) )
        *(_QWORD *)(v66 + 8 * v65 + 11536) += *((_QWORD *)a2 + 12);
    }
    v6 = a2 + 2;
    *(_BYTE *)(*((_QWORD *)a2 + 3) + 38LL) = *((_BYTE *)a2 + 93);
    *(_QWORD *)(*((_QWORD *)a2 + 3) + 40LL) = *((_QWORD *)a2 + 12);
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x140140b00  mov     [rsp+arg_0], rcx
0x140140b05  push    rbx
0x140140b06  sub     rsp, 30h
0x140140b0a  movzx   eax, word ptr [rdx]
0x140140b0d  mov     ecx, 727h
0x140140b12  mov     rbx, rdx
0x140140b15  cmp     ax, cx
0x140140b18  jnz     short loc_140140B21
0x140140b1a  add     rsp, 30h
0x140140b1e  pop     rbx
0x140140b1f  retn
0x140140b21  mov     [rsp+38h+arg_8], rbp
0x140140b26  mov     [rsp+38h+arg_10], rsi
0x140140b2b  mov     [rsp+38h+arg_18], rdi
0x140140b30  test    r8b, 10h
0x140140b34  jnz     loc_140140DDA
0x140140b3a  test    r8b, 5
0x140140b3e  jz      short loc_140140B79
0x140140b40  mov     ecx, eax
0x140140b42  cmp     eax, 723h
0x140140b47  jnz     short loc_140140B8A
0x140140b49  mov     eax, [rdx+4]
0x140140b4c  lea     rdi, [rdx+4]
0x140140b50  test    r8b, 4
0x140140b54  jnz     loc_140140F38
0x140140b5a  bt      eax, 8
0x140140b5e  jb      loc_140140F77
0x140140b64  and     dword ptr [rdi], 0FFFFC000h
0x140140b6a  xor     edi, edi
0x140140b6c  mov     [rbx+24h], edi
0x140140b6f  mov     [rbx+6Ah], di
0x140140b73  cmp     dword ptr [rbx+4], 0; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140b77  jz      short loc_140140BE5
0x140140b79  mov     rsi, [rsp+38h+arg_10]
0x140140b7e  mov     rbp, [rsp+38h+arg_8]
0x140140b83  mov     rdi, [rsp+38h+arg_18]
0x140140b88  jmp     short loc_140140B1A
0x140140b8a  add     ecx, 0FFFFF8DCh; switch 37 cases
0x140140b90  cmp     ecx, 24h
0x140140b93  ja      short def_140140BB1; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140b95  movsxd  rax, ecx
0x140140b98  lea     rdx, cs:140000000h
0x140140b9f  movzx   eax, ds:(byte_14006E574 - 140000000h)[rdx+rax]
0x140140ba7  mov     ecx, ds:(jpt_140140BB1 - 140000000h)[rdx+rax*4]
0x140140bae  add     rcx, rdx
0x140140bb1  jmp     rcx; switch jump
0x140140bb7  mov     eax, [rbx+4]; jumptable 0000000140140BB1 case 1864
0x140140bba  test    al, 1
0x140140bbc  jz      short loc_140140C37
0x140140bbe  test    r8b, 4
0x140140bc2  jnz     loc_140140C70
0x140140bc8  mov     rcx, [rbx+28h]; P
0x140140bcc  test    rcx, rcx
0x140140bcf  jz      short loc_140140C37
0x140140bd1  xor     edx, edx; Tag
0x140140bd3  call    cs:__imp_ExFreePoolWithTag
0x140140bda  nop     dword ptr [rax+rax+00h]
0x140140bdf  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140be3  jmp     short def_140140BB1; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140be5  mov     rcx, [rbx+8]
0x140140be9  lea     rax, [rbx+8]
0x140140bed  cmp     [rcx+8], rax
0x140140bf1  jnz     short loc_140140C69
0x140140bf3  mov     rdx, [rax+8]
0x140140bf7  cmp     [rdx], rax
0x140140bfa  jnz     short loc_140140C69
0x140140bfc  mov     [rdx], rcx
0x140140bff  mov     [rcx+8], rdx
0x140140c03  mov     rdx, rbx; Entry
0x140140c06  lea     rcx, NtfsRollbackStructLookasideList; Lookaside
0x140140c0d  call    cs:__imp_ExFreeToLookasideListEx
0x140140c14  nop     dword ptr [rax+rax+00h]
0x140140c19  mov     rsi, [rsp+38h+arg_10]
0x140140c1e  mov     rbp, [rsp+38h+arg_8]
0x140140c23  mov     rdi, [rsp+38h+arg_18]
0x140140c28  jmp     loc_140140B1A
0x140140c2d  test    r8b, 4; jumptable 0000000140140BB1 case 1858
0x140140c31  jnz     loc_140140E5B
0x140140c37  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140c3b  jmp     def_140140BB1; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140c40  test    r8b, 4; jumptable 0000000140140BB1 case 1830
0x140140c44  jnz     loc_140140E77
0x140140c4a  test    byte ptr [rbx+4], 8
0x140140c4e  setnz   cl
0x140140c51  test    r8b, 1
0x140140c55  setnz   al
0x140140c58  test    al, cl
0x140140c5a  jnz     loc_140140D29
0x140140c60  and     dword ptr [rbx+4], 0FFFFFFF0h
0x140140c64  jmp     def_140140BB1; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140c69  mov     ecx, 3
0x140140c6e  int     29h; Win8: RtlFailFast(ecx)
0x140140c70  mov     rcx, [rbx+18h]
0x140140c74  xor     edi, edi
0x140140c76  add     rcx, 2A28h; Resource
0x140140c7d  mov     dl, 1; Wait
0x140140c7f  mov     esi, edi
0x140140c81  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140c88  nop     dword ptr [rax+rax+00h]
0x140140c8d  mov     rdx, [rbx+28h]
0x140140c91  test    rdx, rdx
0x140140c94  jz      short loc_140140CA2
0x140140c96  mov     rcx, [rbx+18h]
0x140140c9a  call    NtfsCalculateVcbStorageReserveTotalReserved
0x140140c9f  mov     rsi, rax
0x140140ca2  mov     rbp, [rbx+18h]
0x140140ca6  mov     rdx, [rbp+2A98h]
0x140140cad  test    rdx, rdx
0x140140cb0  jz      short loc_140140CBD
0x140140cb2  mov     rcx, rbp
0x140140cb5  call    NtfsCalculateVcbStorageReserveTotalReserved
0x140140cba  sub     rsi, rax
0x140140cbd  test    rsi, rsi
0x140140cc0  jnz     loc_140140EED
0x140140cc6  mov     rax, [rbx+18h]
0x140140cca  mov     rcx, [rax+2A98h]; P
0x140140cd1  test    rcx, rcx
0x140140cd4  jz      short loc_140140CE4
0x140140cd6  xor     edx, edx; Tag
0x140140cd8  call    cs:__imp_ExFreePoolWithTag
0x140140cdf  nop     dword ptr [rax+rax+00h]
0x140140ce4  mov     rcx, [rbx+18h]
0x140140ce8  mov     eax, [rbx+20h]
0x140140ceb  mov     [rcx+2A94h], eax
0x140140cf1  mov     rcx, [rbx+18h]
0x140140cf5  mov     rax, [rbx+28h]
0x140140cf9  mov     [rcx+2A98h], rax
0x140140d00  mov     rcx, [rbx+18h]
0x140140d04  call    NtfsCalculateVcbStorageReserveFields
0x140140d09  mov     rcx, [rbx+18h]
0x140140d0d  add     rcx, 2A28h; Resource
0x140140d14  call    cs:__imp_ExReleaseResourceLite
0x140140d1b  nop     dword ptr [rax+rax+00h]
0x140140d20  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140d24  jmp     def_140140BB1; jumptable 0000000140140BB1 default case, cases 1831,1833-1857,1859-1863
0x140140d29  mov     rax, [rbx+18h]
0x140140d2d  mov     ecx, [rax+200h]
0x140140d33  mov     rax, [rbx+18h]
0x140140d37  btr     ecx, 19h
0x140140d3b  mov     [rax+200h], ecx
0x140140d41  jmp     loc_140140C60
0x140140d46  mov     rcx, [rbx+8]
0x140140d4a  lea     rax, [rbx+8]
0x140140d4e  cmp     [rcx+8], rax
0x140140d52  jnz     loc_140140C69
0x140140d58  jmp     loc_140140BF3
0x140140d5d  mov     rax, [rbx+18h]
0x140140d61  mov     dl, 1; Wait
0x140140d63  mov     rcx, [rax+18h]
0x140140d67  mov     rcx, [rcx+18h]
0x140140d6b  add     rcx, 50h ; 'P'; Resource
0x140140d6f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140d76  nop     dword ptr [rax+rax+00h]
0x140140d7b  mov     rax, [rbx+20h]
0x140140d7f  mov     rdx, [rax]
0x140140d82  cmp     [rdx+8], rax
0x140140d86  jnz     loc_140140C69
0x140140d8c  mov     rcx, [rax+8]
0x140140d90  cmp     [rcx], rax
0x140140d93  jnz     loc_140140C69
0x140140d99  mov     [rcx], rdx
0x140140d9c  mov     [rdx+8], rcx
0x140140da0  mov     rax, [rbx+18h]
0x140140da4  mov     rcx, [rax+18h]
0x140140da8  mov     rcx, [rcx+18h]
0x140140dac  add     rcx, 50h ; 'P'; Resource
0x140140db0  call    cs:__imp_ExReleaseResourceLite
0x140140db7  nop     dword ptr [rax+rax+00h]
0x140140dbc  mov     rax, [rbx+20h]
0x140140dc0  mov     rcx, [rax+20h]
0x140140dc4  test    rcx, rcx
0x140140dc7  jz      loc_1402C85D3
0x140140dcd  xor     edx, edx
0x140140dcf  call    TxfDereferenceTxfFcb
0x140140dd4  nop
0x140140dd5  jmp     loc_1402C85D3
0x140140dda  mov     ecx, eax
0x140140ddc  sub     ecx, 723h
0x140140de2  jz      loc_1402C858C
0x140140de8  cmp     ecx, 25h ; '%'
0x140140deb  jnz     loc_140140D46
0x140140df1  mov     eax, [rdx+4]
0x140140df4  test    al, 1
0x140140df6  jz      loc_140140D46
0x140140dfc  mov     rcx, [rdx+28h]; P
0x140140e00  test    rcx, rcx
0x140140e03  jz      loc_140140D46
0x140140e09  xor     edx, edx; Tag
0x140140e0b  call    cs:__imp_ExFreePoolWithTag
0x140140e12  nop     dword ptr [rax+rax+00h]
0x140140e17  jmp     loc_140140D46
0x140140e1c  xor     edi, edi; jumptable 0000000140140BB1 case 1828
0x140140e1e  test    r8b, 4
0x140140e22  jz      loc_1402C8668
0x140140e28  mov     rcx, [rbx+18h]
0x140140e2c  mov     dl, 1; Wait
0x140140e2e  mov     rcx, [rcx+88h]; Resource
0x140140e35  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140e3c  nop     dword ptr [rax+rax+00h]
0x140140e41  mov     eax, [rbx+4]
0x140140e44  test    al, 1
0x140140e46  jz      loc_1402C85C7
0x140140e4c  mov     rax, [rbx+18h]
0x140140e50  mov     rcx, [rax+30h]
0x140140e54  mov     [rcx], edi
0x140140e56  jmp     loc_1402C85C7
0x140140e5b  mov     eax, [rbx+4]
0x140140e5e  test    al, 1
0x140140e60  jz      loc_140140C37
0x140140e66  mov     rcx, [rbx+18h]
0x140140e6a  mov     rax, [rbx+20h]
0x140140e6e  mov     [rcx+40h], rax
0x140140e72  jmp     loc_140140C37
0x140140e77  mov     eax, [rbx+4]
0x140140e7a  test    al, 2
0x140140e7c  jz      loc_1402C8674
0x140140e82  mov     rax, [rbx+18h]
0x140140e86  movups  xmm0, xmmword ptr [rbx+20h]
0x140140e8a  movups  xmmword ptr [rax+108h], xmm0
0x140140e91  jmp     loc_1402C8674
0x140140e96  test    r8b, 4; jumptable 0000000140140BB1 case 1829
0x140140e9a  jz      loc_1402C86FE
0x140140ea0  mov     eax, [rbx+4]
0x140140ea3  test    al, 2
0x140140ea5  jz      loc_1402C86E0
0x140140eab  mov     rdx, [rbx+18h]
0x140140eaf  xor     ecx, ecx
0x140140eb1  mov     r9, [rbx+28h]
0x140140eb5  mov     r8, rdx
0x140140eb8  mov     rdx, [rdx+0D0h]
0x140140ebf  call    TxfReserveSpaceForAbortPriv
0x140140ec4  nop
0x140140ec5  jmp     loc_1402C86E0
0x140140eca  test    r8b, 4; jumptable 0000000140140BB1 case 1832
0x140140ece  jz      loc_1402C86FE
0x140140ed4  mov     eax, [rbx+4]
0x140140ed7  test    al, 2
0x140140ed9  jz      loc_1402C8707
0x140140edf  mov     rcx, [rbx+18h]
0x140140ee3  mov     eax, [rbx+20h]
0x140140ee6  mov     [rcx], eax
0x140140ee8  jmp     loc_1402C8707
0x140140eed  lea     rcx, [rbp+2D0h]; Mutex
0x140140ef4  call    cs:__imp_KeAcquireGuardedMutex
0x140140efb  nop     dword ptr [rax+rax+00h]
0x140140f00  mov     rax, [rbx+18h]
0x140140f04  add     [rax+148h], rsi
0x140140f0b  mov     rax, [rbx+18h]
0x140140f0f  mov     rcx, [rax+148h]
0x140140f16  test    rsi, rsi
0x140140f19  jle     loc_1402C87D6
0x140140f1f  cmp     rcx, [rax+2080h]
0x140140f26  jle     loc_1402C876D
0x140140f2c  mov     [rax+2080h], rcx
0x140140f33  jmp     loc_1402C876D
0x140140f38  mov     [rsp+38h+var_10], r14
0x140140f3d  test    al, 1
0x140140f3f  jz      loc_1402C892A
0x140140f45  mov     edx, [rdx+24h]
0x140140f48  lea     r8, [rbx+4]
0x140140f4c  mov     rcx, [rbx+18h]
0x140140f50  not     edx
0x140140f52  mov     eax, [rcx+4]
0x140140f55  and     edx, eax
0x140140f57  mov     [rcx+4], edx
0x140140f5a  mov     eax, [rcx+4]
0x140140f5d  mov     rcx, [rbx+18h]
0x140140f61  mov     edx, [rbx+20h]
0x140140f64  and     edx, [rbx+24h]
0x140140f67  mov     eax, [rcx+4]
0x140140f6a  or      eax, edx
0x140140f6c  mov     [rcx+4], eax
0x140140f6f  mov     eax, [rcx+4]
0x140140f72  jmp     loc_1402C892D
0x140140f77  mov     rax, [rdx+50h]
0x140140f7b  mov     ebp, 0FFFFFFFFh
0x140140f80  lock dec dword ptr [rax+3Ch]
0x140140f84  mov     rax, [rdx+50h]
0x140140f88  lock xadd [rax+40h], ebp
0x140140f8d  cmp     ebp, 1
0x140140f90  jnz     loc_140140B64
0x140140f96  mov     rcx, [rdx+50h]; P
0x140140f9a  call    TxfDeleteTxfRmcb
0x140140f9f  jmp     loc_140140B64
0x1402c858c  test    dword ptr [rdx+4], 100h
0x1402c8593  jz      loc_140140D46
0x1402c8599  mov     rax, [rdx+50h]
0x1402c859d  mov     ebp, 0FFFFFFFFh
0x1402c85a2  lock dec dword ptr [rax+3Ch]
0x1402c85a6  mov     rax, [rdx+50h]
0x1402c85aa  lock xadd [rax+40h], ebp
0x1402c85af  cmp     ebp, 1
0x1402c85b2  jnz     loc_140140D46
0x1402c85b8  mov     rcx, [rdx+50h]; P
0x1402c85bc  call    TxfDeleteTxfRmcb
0x1402c85c1  nop
0x1402c85c2  jmp     loc_140140D46
0x1402c85c7  mov     eax, [rbx+4]
0x1402c85ca  test    al, 2
0x1402c85cc  jz      short loc_1402C85EA
  ... truncated ...
```
