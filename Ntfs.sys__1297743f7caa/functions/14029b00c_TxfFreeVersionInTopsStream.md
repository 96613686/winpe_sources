# TxfFreeVersionInTopsStream

- ea: `0x14029b00c`
- end: `0x14029b5a2`
- name: `TxfFreeVersionInTopsStream`
- size: `1430`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bc404`
- `0x140188f30`
- `0x1401d4d68`
- `0x1401d4f90`
- `0x1401d542c`

## callees

- `0x1400f871c`
- `0x140100b64`
- `0x14020bbc0`
- `0x14029b00c`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b243`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b2b0`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b243`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14029b2b0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14029b29f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14029b29f`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b0ad`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b16e`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b0ad`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14029b16e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b1af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b35f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b471`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b48a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b1af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b35f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b471`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029b48a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029b4a6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14029b4a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029b3e7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14029b3e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b1ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b4bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b50d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b1ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b4bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029b50d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b220`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b37f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b39b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b559`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b576`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b220`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b37f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b39b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b559`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029b576`
- `ntoskrnl!ExAcquireFastMutex` at `0x14029b060`
- `ntoskrnl!ExAcquireFastMutex` at `0x14029b060`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029b097`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029b097`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14029b11f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14029b11f`

## pseudocode

```c
char __fastcall TxfFreeVersionInTopsStream(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
{
  __int64 v10; // r13
  int v11; // eax
  char v12; // r14
  signed __int32 v13; // eax
  __int64 v14; // rdi
  bool v15; // bp
  _QWORD *v16; // rdi
  int v17; // r12d
  __int64 v18; // r8
  _DWORD *i; // r14
  int v20; // r9d
  __int64 v21; // r12
  _QWORD *v22; // rdi
  unsigned int v23; // r15d
  int v24; // r9d
  __int64 v25; // r8
  _QWORD *v26; // rdi
  _QWORD *v27; // r14
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // r8
  CLFS_LSN plsn1; // [rsp+30h] [rbp-48h] BYREF
  __int64 v35; // [rsp+38h] [rbp-40h] BYREF
  int v36; // [rsp+88h] [rbp+10h]
  __int64 v37; // [rsp+90h] [rbp+18h] BYREF

  if ( a2 )
    v10 = *(_QWORD *)(a2 + 64);
  else
    v10 = 0;
  v11 = *(_DWORD *)(a3 + 8);
  plsn1.ullOffset = 0;
  if ( (v11 & 0x20) == 0 )
  {
    v12 = 0;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x800u);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 3 )
      _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x80000u);
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(a3 + 152)) && !*(_QWORD *)(a3 + 288) )
    {
      while ( 1 )
      {
        v16 = *(_QWORD **)(a3 + 296);
        if ( !v16 )
          break;
        if ( *v16 )
        {
          TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(a1 + 16), *v16, 0);
          *v16 = 0;
        }
        *(_QWORD *)(a3 + 296) = v16[3];
        ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v16);
      }
      _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x28u);
      return v12;
    }
    if ( !a2
      || (v13 = _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 44), 1u),
          _InterlockedDecrement((volatile signed __int32 *)(a2 + 44)),
          !v13)
      || a4 )
    {
      v14 = 0;
      v37 = 0;
      plsn1.ullOffset = _InterlockedCompareExchange64(
                          (volatile signed __int64 *)(a1 + 408),
                          NtfsLarge0.QuadPart,
                          NtfsLarge0.QuadPart);
      v15 = ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(a3 + 280))
         || a5
         || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 1
         && (*(_DWORD *)(a3 + 8) & 0x200) != 0
         || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) == 3
         || RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(a3 + 152));
      v17 = *(_DWORD *)(a3 + 8) & 8;
      v36 = v17;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
      if ( v17 )
      {
        if ( !v15 )
        {
LABEL_43:
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          if ( !v17 )
          {
            ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a1 + 280) + 16LL));
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 8u);
          }
          v14 = v37;
          if ( v15 )
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x20u);
          goto LABEL_47;
        }
      }
      else
      {
        LOBYTE(v18) = a6;
        if ( !(unsigned __int8)NtfsAcquireScbPagingResourceExclusive(0, *(_QWORD *)(a1 + 280), v18) )
        {
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          v15 = 0;
LABEL_47:
          if ( *(_QWORD *)(a3 + 296) && (v15 || v14) )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
            v26 = *(_QWORD **)(a3 + 296);
            v27 = 0;
            while ( v26 )
            {
              if ( *v26 )
                *(_QWORD *)(*v26 + 16LL) -= v26[2] << 12;
              v26[2] = 0;
              if ( v15 || !v26[1] )
              {
                if ( *v26 )
                {
                  LOBYTE(v25) = 1;
                  *(_QWORD *)(*v26 + 16LL) -= v26[1] << 12;
                  TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(a1 + 16), *v26, v25);
                  *v26 = 0;
                }
                v28 = v26[3];
                if ( v27 )
                {
                  v27[3] = v28;
                  ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v26);
                }
                else
                {
                  *(_QWORD *)(a3 + 296) = v28;
                  ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v26);
                  v26 = *(_QWORD **)(a3 + 296);
                }
              }
              else
              {
                v27 = v26;
                v26 = (_QWORD *)v26[3];
              }
            }
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
          }
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
          v29 = (_QWORD *)(a3 + 48);
          v30 = *(_QWORD *)(a3 + 48);
          if ( v30 )
          {
            if ( *(_QWORD **)(v30 + 8) != v29 )
              goto LABEL_72;
            v31 = *(_QWORD **)(a3 + 56);
            if ( (_QWORD *)*v31 != v29 )
              goto LABEL_72;
            *v31 = v30;
            *(_QWORD *)(v30 + 8) = v31;
            *v29 = 0;
          }
          if ( v15 || (*(_DWORD *)(a3 + 8) & 0x1000) != 0 )
          {
            v12 = 0;
          }
          else
          {
            if ( v10 )
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v10 + 136), 1u);
            _InterlockedIncrement((volatile signed __int32 *)(a3 + 4));
            _InterlockedOr((volatile signed __int32 *)(a3 + 8), 0x1000u);
            v32 = *(_QWORD **)(a1 + 400);
            if ( *v32 != a1 + 392 )
LABEL_72:
              __fastfail(3u);
            v12 = 1;
            *(_QWORD *)(a3 + 64) = a1 + 392;
            *(_QWORD *)(a3 + 72) = v32;
            *v32 = a3 + 64;
            *(_QWORD *)(a1 + 400) = a3 + 64;
            if ( v10 )
              ExReleaseResourceLite(*(PERESOURCE *)(v10 + 136));
          }
          ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
          return v12;
        }
      }
      for ( i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), 1u);
            i;
            i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), 0) )
      {
        v20 = i[6] << 12;
        v35 = *((_QWORD *)i + 1) << 12;
        TxfFreeTopsRange(a1, 0, (unsigned int)&v35, v20, (2 * v15) | (v17 != 0 ? 32 : 49));
        if ( v15 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), i);
      }
      if ( !v17 )
      {
        v21 = v37;
        while ( 1 )
        {
          v22 = *(_QWORD **)(a3 + 288);
          if ( !v22 )
            break;
          v23 = 0;
          *(_QWORD *)(a3 + 288) = *v22;
          if ( *((_DWORD *)v22 + 2) )
          {
            do
            {
              if ( (v22[2 * v23 + 3] & 0x10000LL) == 0 )
              {
                v24 = LOWORD(v22[2 * v23 + 3]) << 12;
                v37 = v22[2 * v23 + 2] << 12;
                TxfFreeTopsRange(a1, 0, (unsigned int)&v37, v24, 51);
                v21 += LOWORD(v22[2 * v23 + 3]);
              }
              ++v23;
            }
            while ( v23 < *((_DWORD *)v22 + 2) );
            v37 = v21;
          }
          ExFreeToLookasideListEx(&TxfTopsRangeEntryLookasideList, v22);
        }
        v17 = v36;
      }
      goto LABEL_43;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14029b00c  mov     [rsp+arg_18], rbx
0x14029b011  push    rbp
0x14029b012  push    rsi
0x14029b013  push    rdi
0x14029b014  push    r12
0x14029b016  push    r13
0x14029b018  push    r14
0x14029b01a  push    r15
0x14029b01c  sub     rsp, 40h
0x14029b020  xor     r12d, r12d
0x14029b023  mov     ebp, r9d
0x14029b026  mov     rbx, r8
0x14029b029  mov     rdi, rdx
0x14029b02c  mov     rsi, rcx
0x14029b02f  test    rdx, rdx
0x14029b032  jz      short loc_14029B03A
0x14029b034  mov     r13, [rdx+40h]
0x14029b038  jmp     short loc_14029B03D
0x14029b03a  mov     r13, r12
0x14029b03d  mov     eax, [r8+8]
0x14029b041  mov     qword ptr [rsp+78h+plsn1], r12
0x14029b046  test    al, 20h
0x14029b048  jnz     loc_14029B587
0x14029b04e  mov     rcx, [r8+100h]; FastMutex
0x14029b055  mov     r14b, r12b
0x14029b058  mov     [rsp+78h+arg_0], r12b
0x14029b060  call    cs:__imp_ExAcquireFastMutex
0x14029b067  nop     dword ptr [rax+rax+00h]
0x14029b06c  lock or dword ptr [rbx+8], 800h
0x14029b074  mov     ecx, 4
0x14029b079  mov     eax, ecx
0x14029b07b  lock cmpxchg [rsi+84h], ecx
0x14029b083  cmp     eax, 3
0x14029b086  jnz     short loc_14029B090
0x14029b088  lock or dword ptr [rbx+8], 80000h
0x14029b090  mov     rcx, [rbx+100h]; FastMutex
0x14029b097  call    cs:__imp_ExReleaseFastMutex
0x14029b09e  nop     dword ptr [rax+rax+00h]
0x14029b0a3  lea     r15, [rbx+98h]
0x14029b0aa  mov     rcx, r15; Table
0x14029b0ad  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x14029b0b4  nop     dword ptr [rax+rax+00h]
0x14029b0b9  test    al, al
0x14029b0bb  jz      short loc_14029B0CA
0x14029b0bd  cmp     [rbx+120h], r12
0x14029b0c4  jz      loc_14029B1BB
0x14029b0ca  mov     r14d, 1
0x14029b0d0  test    rdi, rdi
0x14029b0d3  jz      short loc_14029B0F1
0x14029b0d5  mov     eax, r14d
0x14029b0d8  lock xadd [rdi+2Ch], eax
0x14029b0dd  lock dec dword ptr [rdi+2Ch]
0x14029b0e1  add     eax, r14d
0x14029b0e4  cmp     eax, r14d
0x14029b0e7  jz      short loc_14029B0F1
0x14029b0e9  test    ebp, ebp
0x14029b0eb  jz      loc_14029B587
0x14029b0f1  mov     rcx, qword ptr cs:NtfsLarge0
0x14029b0f8  xor     edi, edi
0x14029b0fa  mov     [rsp+78h+arg_10], rdi
0x14029b102  mov     rax, rcx
0x14029b105  lock cmpxchg [rsi+198h], rcx
0x14029b10e  lea     rdx, [rbx+118h]; plsn2
0x14029b115  mov     qword ptr [rsp+78h+plsn1], rax
0x14029b11a  lea     rcx, [rsp+78h+plsn1]; plsn1
0x14029b11f  call    cs:__imp_ClfsLsnGreater
0x14029b126  nop     dword ptr [rax+rax+00h]
0x14029b12b  test    al, al
0x14029b12d  jnz     loc_14029B1D1
0x14029b133  cmp     [rsp+78h+arg_20], dil
0x14029b13b  jnz     loc_14029B1D1
0x14029b141  lea     ecx, [rdi+4]
0x14029b144  mov     eax, ecx
0x14029b146  lock cmpxchg [rsi+84h], ecx
0x14029b14e  cmp     eax, r14d
0x14029b151  jnz     short loc_14029B15C
0x14029b153  test    dword ptr [rbx+8], 200h
0x14029b15a  jnz     short loc_14029B1D1
0x14029b15c  mov     eax, ecx
0x14029b15e  lock cmpxchg [rsi+84h], ecx
0x14029b166  cmp     eax, 3
0x14029b169  jz      short loc_14029B1D1
0x14029b16b  mov     rcx, r15; Table
0x14029b16e  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x14029b175  nop     dword ptr [rax+rax+00h]
0x14029b17a  test    al, al
0x14029b17c  jnz     short loc_14029B1D1
0x14029b17e  xor     bpl, bpl
0x14029b181  jmp     short loc_14029B1D4
0x14029b183  mov     rdx, [rdi]
0x14029b186  test    rdx, rdx
0x14029b189  jz      short loc_14029B19A
0x14029b18b  mov     rcx, [rsi+10h]
0x14029b18f  xor     r8d, r8d
0x14029b192  call    TxfDereferenceTxfQuotaControlBlock
0x14029b197  mov     [rdi], r12
0x14029b19a  mov     rax, [rdi+18h]
0x14029b19e  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x14029b1a5  mov     rdx, rdi; Entry
0x14029b1a8  mov     [rbx+128h], rax
0x14029b1af  call    cs:__imp_ExFreeToLookasideListEx
0x14029b1b6  nop     dword ptr [rax+rax+00h]
0x14029b1bb  mov     rdi, [rbx+128h]
0x14029b1c2  test    rdi, rdi
0x14029b1c5  jnz     short loc_14029B183
0x14029b1c7  lock or dword ptr [rbx+8], 28h
0x14029b1cc  jmp     loc_14029B582
0x14029b1d1  mov     bpl, r14b
0x14029b1d4  mov     r12d, [rbx+8]
0x14029b1d8  mov     dl, r14b; Wait
0x14029b1db  mov     rcx, [rsi+170h]; Resource
0x14029b1e2  and     r12d, 8
0x14029b1e6  mov     [rsp+78h+arg_8], r12d
0x14029b1ee  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029b1f5  nop     dword ptr [rax+rax+00h]
0x14029b1fa  test    r12d, r12d
0x14029b1fd  jnz     short loc_14029B234
0x14029b1ff  mov     r8b, [rsp+78h+arg_28]
0x14029b207  xor     ecx, ecx
0x14029b209  mov     rdx, [rsi+118h]
0x14029b210  call    NtfsAcquireScbPagingResourceExclusive
0x14029b215  test    al, al
0x14029b217  jnz     short loc_14029B23D
0x14029b219  mov     rcx, [rsi+170h]; Resource
0x14029b220  call    cs:__imp_ExReleaseResourceLite
0x14029b227  nop     dword ptr [rax+rax+00h]
0x14029b22c  xor     bpl, bpl
0x14029b22f  jmp     loc_14029B3BE
0x14029b234  test    bpl, bpl
0x14029b237  jz      loc_14029B378
0x14029b23d  mov     dl, r14b; Restart
0x14029b240  mov     rcx, r15; Table
0x14029b243  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14029b24a  nop     dword ptr [rax+rax+00h]
0x14029b24f  mov     r14, rax
0x14029b252  test    rax, rax
0x14029b255  jz      short loc_14029B2C4
0x14029b257  mov     eax, r12d
0x14029b25a  movzx   ecx, bpl
0x14029b25e  neg     eax
0x14029b260  sbb     edi, edi
0x14029b262  add     ecx, ecx
0x14029b264  and     edi, 0FFFFFFEFh
0x14029b267  add     edi, 31h ; '1'
0x14029b26a  or      edi, ecx
0x14029b26c  mov     rax, [r14+8]
0x14029b270  lea     r8, [rsp+78h+var_40]
0x14029b275  mov     r9d, [r14+18h]
0x14029b279  xor     edx, edx
0x14029b27b  shl     rax, 0Ch
0x14029b27f  mov     rcx, rsi
0x14029b282  shl     r9d, 0Ch
0x14029b286  mov     [rsp+78h+var_40], rax
0x14029b28b  mov     [rsp+78h+var_58], edi
0x14029b28f  call    TxfFreeTopsRange
0x14029b294  test    bpl, bpl
0x14029b297  jz      short loc_14029B2AB
0x14029b299  mov     rdx, r14; Buffer
0x14029b29c  mov     rcx, r15; Table
0x14029b29f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14029b2a6  nop     dword ptr [rax+rax+00h]
0x14029b2ab  xor     edx, edx; Restart
0x14029b2ad  mov     rcx, r15; Table
0x14029b2b0  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14029b2b7  nop     dword ptr [rax+rax+00h]
0x14029b2bc  mov     r14, rax
0x14029b2bf  test    rax, rax
0x14029b2c2  jnz     short loc_14029B26C
0x14029b2c4  test    r12d, r12d
0x14029b2c7  jnz     loc_14029B378
0x14029b2cd  mov     r12, [rsp+78h+arg_10]
0x14029b2d5  mov     rdi, [rbx+120h]
0x14029b2dc  test    rdi, rdi
0x14029b2df  jz      loc_14029B370
0x14029b2e5  mov     rax, [rdi]
0x14029b2e8  xor     r15d, r15d
0x14029b2eb  mov     [rbx+120h], rax
0x14029b2f2  cmp     [rdi+8], r15d
0x14029b2f6  jbe     short loc_14029B355
0x14029b2f8  mov     r14d, r15d
0x14029b2fb  add     r14, r14
0x14029b2fe  test    byte ptr [rdi+r14*8+1Ah], 1
0x14029b304  jnz     short loc_14029B344
0x14029b306  mov     rax, [rdi+r14*8+10h]
0x14029b30b  lea     r8, [rsp+78h+arg_10]
0x14029b313  movzx   r9d, word ptr [rdi+r14*8+18h]
0x14029b319  xor     edx, edx
0x14029b31b  shl     rax, 0Ch
0x14029b31f  mov     rcx, rsi
0x14029b322  shl     r9d, 0Ch
0x14029b326  mov     [rsp+78h+arg_10], rax
0x14029b32e  mov     [rsp+78h+var_58], 33h ; '3'
0x14029b336  call    TxfFreeTopsRange
0x14029b33b  movzx   eax, word ptr [rdi+r14*8+18h]
0x14029b341  add     r12, rax
0x14029b344  inc     r15d
0x14029b347  cmp     r15d, [rdi+8]
0x14029b34b  jb      short loc_14029B2F8
0x14029b34d  mov     [rsp+78h+arg_10], r12
0x14029b355  mov     rdx, rdi; Entry
0x14029b358  lea     rcx, TxfTopsRangeEntryLookasideList; Lookaside
0x14029b35f  call    cs:__imp_ExFreeToLookasideListEx
0x14029b366  nop     dword ptr [rax+rax+00h]
0x14029b36b  jmp     loc_14029B2D5
0x14029b370  mov     r12d, [rsp+78h+arg_8]
0x14029b378  mov     rcx, [rsi+170h]; Resource
0x14029b37f  call    cs:__imp_ExReleaseResourceLite
0x14029b386  nop     dword ptr [rax+rax+00h]
0x14029b38b  test    r12d, r12d
0x14029b38e  jnz     short loc_14029B3AC
0x14029b390  mov     rcx, [rsi+118h]
0x14029b397  mov     rcx, [rcx+10h]; Resource
0x14029b39b  call    cs:__imp_ExReleaseResourceLite
0x14029b3a2  nop     dword ptr [rax+rax+00h]
0x14029b3a7  lock or dword ptr [rbx+8], 8
0x14029b3ac  mov     rdi, [rsp+78h+arg_10]
0x14029b3b4  test    bpl, bpl
0x14029b3b7  jz      short loc_14029B3BE
0x14029b3b9  lock or dword ptr [rbx+8], 20h
0x14029b3be  cmp     qword ptr [rbx+128h], 0
0x14029b3c6  jz      loc_14029B4B2
0x14029b3cc  test    bpl, bpl
0x14029b3cf  jnz     short loc_14029B3DA
0x14029b3d1  test    rdi, rdi
0x14029b3d4  jz      loc_14029B4B2
0x14029b3da  mov     rcx, [rsi+10h]
0x14029b3de  mov     r12d, 18A8h
0x14029b3e4  add     rcx, r12; FastMutex
0x14029b3e7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14029b3ee  nop     dword ptr [rax+rax+00h]
0x14029b3f3  mov     rdi, [rbx+128h]
0x14029b3fa  xor     r14d, r14d
0x14029b3fd  xor     r15d, r15d
0x14029b400  jmp     loc_14029B496
0x14029b405  mov     rdx, [rdi]
0x14029b408  test    rdx, rdx
0x14029b40b  jz      short loc_14029B419
0x14029b40d  mov     rax, [rdi+10h]
0x14029b411  shl     rax, 0Ch
0x14029b415  sub     [rdx+10h], rax
0x14029b419  mov     [rdi+10h], r15
0x14029b41d  test    bpl, bpl
0x14029b420  jnz     short loc_14029B431
0x14029b422  cmp     [rdi+8], r15
0x14029b426  jz      short loc_14029B431
0x14029b428  mov     r14, rdi
0x14029b42b  mov     rdi, [rdi+18h]
0x14029b42f  jmp     short loc_14029B496
0x14029b431  mov     rcx, [rdi]
0x14029b434  test    rcx, rcx
0x14029b437  jz      short loc_14029B457
0x14029b439  mov     rax, [rdi+8]
0x14029b43d  mov     r8b, 1
0x14029b440  shl     rax, 0Ch
0x14029b444  sub     [rcx+10h], rax
0x14029b448  mov     rdx, [rdi]
0x14029b44b  mov     rcx, [rsi+10h]
0x14029b44f  call    TxfDereferenceTxfQuotaControlBlock
0x14029b454  mov     [rdi], r15
0x14029b457  mov     rax, [rdi+18h]
0x14029b45b  mov     rdx, rdi; Entry
0x14029b45e  lea     rcx, TxfVscbQuotaInfoLookasideList; Lookaside
0x14029b465  test    r14, r14
0x14029b468  jnz     short loc_14029B486
0x14029b46a  mov     [rbx+128h], rax
0x14029b471  call    cs:__imp_ExFreeToLookasideListEx
0x14029b478  nop     dword ptr [rax+rax+00h]
0x14029b47d  mov     rdi, [rbx+128h]
0x14029b484  jmp     short loc_14029B496
0x14029b486  mov     [r14+18h], rax
0x14029b48a  call    cs:__imp_ExFreeToLookasideListEx
0x14029b491  nop     dword ptr [rax+rax+00h]
0x14029b496  test    rdi, rdi
0x14029b499  jnz     loc_14029B405
0x14029b49f  mov     rcx, [rsi+10h]
0x14029b4a3  add     rcx, r12; FastMutex
0x14029b4a6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14029b4ad  nop     dword ptr [rax+rax+00h]
0x14029b4b2  mov     rcx, [rsi+170h]; Resource
0x14029b4b9  mov     dl, 1; Wait
0x14029b4bb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029b4c2  nop     dword ptr [rax+rax+00h]
0x14029b4c7  lea     rax, [rbx+30h]
0x14029b4cb  mov     rcx, [rax]
0x14029b4ce  test    rcx, rcx
0x14029b4d1  jz      short loc_14029B4F0
0x14029b4d3  cmp     [rcx+8], rax
0x14029b4d7  jnz     short loc_14029B531
0x14029b4d9  mov     rdx, [rax+8]
0x14029b4dd  cmp     [rdx], rax
0x14029b4e0  jnz     short loc_14029B531
0x14029b4e2  mov     [rdx], rcx
0x14029b4e5  mov     [rcx+8], rdx
0x14029b4e9  mov     qword ptr [rax], 0
0x14029b4f0  test    bpl, bpl
0x14029b4f3  jnz     short loc_14029B567
0x14029b4f5  mov     edi, 1000h
0x14029b4fa  test    [rbx+8], edi
0x14029b4fd  jnz     short loc_14029B567
0x14029b4ff  test    r13, r13
  ... truncated ...
```
