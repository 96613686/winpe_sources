# RefsCreateScb(_IRP_CONTEXT *,_FCB *,_REFS_ATTRIBUTE_TYPE_CODE,_UNICODE_STRING const *,REFS_CREATE_SCB_INFLAGS,uchar *)

- ea: `0x140309cb0`
- end: `0x14030a441`
- name: `?RefsCreateScb@@YAPEAU_SCB@@PEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@PEBU_UNICODE_STRING@@W4REFS_CREATE_SCB_INFLAGS@@PEAE@Z`
- size: `1937`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `28`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14009b7e4`
- `0x1400d63f4`
- `0x1400daa80`
- `0x1400f01fc`
- `0x1401005bc`
- `0x140103530`
- `0x140112d1c`
- `0x140295380`
- `0x140295afc`
- `0x140297d70`
- `0x1402986f0`
- `0x14029a0bc`
- `0x14029b914`
- `0x14029bf9c`
- `0x14029cb40`
- `0x14029cd7c`
- `0x1402aa38c`
- `0x1402cc968`
- `0x1402d2d88`
- `0x1402fbbf8`
- `0x1402ff3f0`
- `0x140306d6c`
- `0x140307db0`
- `0x140308440`
- `0x1403099e0`
- `0x14030d820`
- `0x140313b80`
- `0x14033c460`

## callees

- `0x140035da0`
- `0x140037e00`
- `0x140038480`
- `0x14008ad80`
- `0x140099bd0`
- `0x1400ac00c`
- `0x1401f4100`
- `0x1401f4920`
- `0x1402d92fc`
- `0x140309cb0`
- `0x140316020`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x140309d69`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140309d69`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140342247`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140342247`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14034226d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14034226d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14030a057`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14030a057`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14030a22b`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14030a22b`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14030a378`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14030a378`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140309d79`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140309d79`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309de9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309e6c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030a421`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034221c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309de9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140309e6c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030a421`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034221c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309df5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309e78`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030a42d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342228`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309df5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140309e78`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030a42d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342228`
- `ntoskrnl!KeInitializeEvent` at `0x14030a1f8`
- `ntoskrnl!KeInitializeEvent` at `0x14030a1f8`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140309e17`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140309e17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034227d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403422a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034227d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403422a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140309fcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030a011`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030a17a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140309fcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030a011`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030a17a`

## pseudocode

```c
char *__fastcall RefsCreateScb(__int64 a1, __int64 a2, __int16 a3, __int64 *a4, char a5, _BYTE *a6)
{
  __int64 *v6; // r15
  __int64 v10; // rdx
  __int64 v12; // rbx
  __int64 *v13; // rax
  __int64 *i; // rbx
  char v15; // bl
  __int64 v16; // rax
  unsigned __int16 v17; // r12
  __int16 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  char *PoolWithTag; // rax
  char *v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r12d
  PVOID v26; // rax
  struct _KEVENT *NPagedPerProcessorLookaside; // rax
  unsigned __int64 v28; // rdx
  PVOID *v29; // r12
  _OWORD *v30; // rax
  char *v31; // r15
  _OWORD *v32; // rax
  _QWORD *v33; // rcx
  unsigned __int16 v34; // [rsp+C0h] [rbp+18h]

  v6 = a4;
  if ( a3 == 160 )
  {
    v10 = *(_QWORD *)(a2 + 328);
    if ( v10 )
    {
      if ( (*(_DWORD *)(v10 + 300) & 0x40) == 0 || (*(_DWORD *)(a2 + 8) & 0x8000000) != 0 )
      {
        if ( a6 )
          *a6 = 1;
        return (char *)v10;
      }
    }
  }
  if ( a6 )
    *a6 = 0;
  if ( !a4 )
  {
    v6 = (__int64 *)&RefsFileNameIndex;
    if ( a3 != 160 )
      v6 = qword_14020D488;
  }
  v12 = *(_QWORD *)(a2 + 88);
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v12 + 8));
  v13 = (__int64 *)(a2 + 48);
  for ( i = *(__int64 **)(a2 + 48); i != v13; i = (__int64 *)*i )
  {
    if ( a3 == *((_WORD *)i + 48) )
    {
      if ( ((*((_DWORD *)i + 45) & 0x40) == 0 || a3 == 160 && (*(_DWORD *)(a2 + 8) & 0x8000000) != 0)
        && *((_WORD *)i + 52) == *(_WORD *)v6
        && !memcmp((const void *)i[14], (const void *)v6[1], *((unsigned __int16 *)i + 52)) )
      {
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
        KeLeaveGuardedRegion();
        if ( a6 )
          *a6 = 1;
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(i[2] + 88) + 64LL) && *(_BYTE *)(a1 + 40) != 3 )
          RefsSnapshotScb(a1, i - 15, 0);
        if ( (i[4] & 0x1000000) != 0 )
          RefsDeleteEncryptionContext((struct _SCB *)(i - 15));
        return (char *)(i - 15);
      }
      v13 = (__int64 *)(a2 + 48);
    }
  }
  if ( (a5 & 1) != 0 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
    KeLeaveGuardedRegion();
    return 0;
  }
  v15 = 1;
  if ( a3 == 160 )
  {
    v16 = *(_QWORD *)(a2 + 88);
    if ( *(_QWORD *)(v16 + 256) != 1536 || *(_QWORD *)(v16 + 248) )
      v17 = 2051;
    else
      v17 = 2052;
    v18 = 432;
    v34 = 432;
  }
  else
  {
    v17 = 2053;
    v18 = 496;
    v34 = 496;
    if ( a3 == 128 || a3 == 176 )
    {
      if ( (*(_DWORD *)(a2 + 8) & 0x100LL) == 0 || (a5 & 8) != 0 )
      {
        v15 = 4;
      }
      else
      {
        v19 = *(_QWORD *)(a2 + 88);
        if ( *(_QWORD *)(v19 + 256) == 1313 && (*(_QWORD *)(v19 + 248) == 1024 || *(_QWORD *)(v19 + 248) == 512) )
          v15 = 5;
      }
    }
  }
  v20 = *(_QWORD *)(a2 + 8);
  if ( (v20 & 2) != 0 )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, v18, 0x6E666552u);
    v15 |= 2u;
  }
  else if ( a3 == 160 )
  {
    if ( (v20 & 0x400) != 0 )
    {
      v22 = (char *)(a2 + 368);
      if ( !*(_WORD *)(a2 + 368) )
        goto LABEL_60;
    }
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x1B0u, 0x53666552u);
  }
  else
  {
    if ( (v20 & 0x200) != 0 && (a3 == 128 || a3 == 176) )
    {
      v22 = (char *)(a2 + 368);
      if ( !*(_WORD *)(a2 + 368) )
        goto LABEL_60;
    }
    PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsScbDataLookasideList);
    v15 |= 8u;
  }
  v22 = PoolWithTag;
LABEL_60:
  _SCB::Initialize(v22, v17, v34, a2, a3);
  if ( (v15 & 4) != 0 )
  {
    if ( !*(_QWORD *)(a2 + 96) )
    {
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 && !*(_BYTE *)(a1 + 40) && *(_QWORD *)(a1 + 72) || (a5 & 8) != 0 )
      {
        v23 = *(_QWORD *)(a1 + 56);
        if ( v23 )
        {
          RefsReleasePagingResource(a1, v23);
          *(_QWORD *)(a1 + 56) = 0;
        }
        v24 = 16;
      }
      else
      {
        v24 = (a5 & 0x10) != 0 ? 0x30 : 0;
      }
      RefsAddPagingIoToFcb(a1, a2, v24);
    }
    *((_QWORD *)v22 + 2) = *(_QWORD *)(a2 + 96);
  }
  v25 = *(unsigned __int16 *)v6;
  if ( (_WORD)v25 )
  {
    if ( v25 == 8 && !memcmp((const void *)v6[1], L"$I30", 8u) )
    {
      *((UNICODE_STRING *)v22 + 14) = RefsFileNameIndex;
    }
    else
    {
      *((_WORD *)v22 + 112) = v25;
      *((_WORD *)v22 + 113) = *(_WORD *)v6 + 2;
      v26 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *(unsigned __int16 *)v6 + 2LL, 0x73466552u);
      *((_QWORD *)v22 + 29) = v26;
      memmove(v26, (const void *)v6[1], *(unsigned __int16 *)v6);
      *(_WORD *)(*((_QWORD *)v22 + 29) + 2 * ((unsigned __int64)*(unsigned __int16 *)v6 >> 1)) = 0;
    }
  }
  if ( (v15 & 2) != 0 )
  {
    *((_DWORD *)v22 + 75) |= 0x10u;
    NPagedPerProcessorLookaside = (struct _KEVENT *)RefsAllocateNPagedPerProcessorLookaside(RefsFastMutexNonpagedLookasideList);
    *((_QWORD *)v22 + 6) = NPagedPerProcessorLookaside;
    NPagedPerProcessorLookaside->Header.LockNV = 1;
    NPagedPerProcessorLookaside->Header.WaitListHead.Flink = 0;
    LODWORD(NPagedPerProcessorLookaside->Header.WaitListHead.Blink) = 0;
    KeInitializeEvent(NPagedPerProcessorLookaside + 1, SynchronizationEvent, 0);
  }
  else
  {
    *((_QWORD *)v22 + 6) = *(_QWORD *)(a2 + 88) + 8LL;
  }
  v28 = *(_QWORD *)(a2 + 8);
  if ( (v28 & 4) != 0 )
  {
    v22[4] |= 0x40u;
    v22[6] |= 8u;
    v29 = (PVOID *)(v22 + 88);
  }
  else
  {
    ExInitializeAutoExpandPushLock(v22 + 352, (v28 >> 1) & 1);
    v22[4] |= 0x40u;
    v22[6] |= 2u;
    v22[7] = v22[7] & 0xF | 0x50;
    *((_QWORD *)v22 + 8) = v22 + 56;
    *((_QWORD *)v22 + 7) = v22 + 56;
    *((_QWORD *)v22 + 9) = 0;
    *((_QWORD *)v22 + 10) = 0;
    v29 = (PVOID *)(v22 + 88);
    *((_QWORD *)v22 + 11) = 0;
    *((_QWORD *)v22 + 12) = 0;
    *((_DWORD *)v22 + 26) = 0;
    *((_QWORD *)v22 + 14) = 0;
    if ( a2 != -256 )
      *((_QWORD *)v22 + 10) = a2 + 256;
    if ( v22 != (char *)-352LL )
      *((_QWORD *)v22 + 12) = v22 + 352;
  }
  v30 = (_OWORD *)(*(_QWORD *)(a2 + 88) + 168LL);
  v31 = v22 + 248;
  if ( *(_WORD *)v30 )
  {
    v32 = RefsAllocateNPagedPerProcessorLookaside(RefsScbNonpagedLookasideList);
    *(_QWORD *)v31 = v32;
    *v32 = 0;
    v32[1] = 0;
    v32[2] = 0;
    v32[3] = 0;
    v32[4] = 0;
    **(_WORD **)v31 = 2055;
    *(_WORD *)(*(_QWORD *)v31 + 2LL) = 80;
    *(_QWORD *)(*(_QWORD *)v31 + 56LL) = *((_QWORD *)v22 + 18);
    *(_DWORD *)(*(_QWORD *)v31 + 72LL) = 0;
  }
  else
  {
    *(_QWORD *)v31 = v30;
    *v30 = 0;
    v30[1] = 0;
    v30[2] = 0;
    v30[3] = 0;
    v30[4] = 0;
    **(_WORD **)v31 = 2055;
    *(_WORD *)(*(_QWORD *)v31 + 2LL) = 80;
    *(_QWORD *)(*(_QWORD *)v31 + 56LL) = *((_QWORD *)v22 + 18);
    *(_DWORD *)(*(_QWORD *)v31 + 72LL) = 1;
  }
  FsLibInitializeRangeLock(*(_QWORD *)v31 + 64LL);
  if ( (unsigned __int16)(*(_WORD *)v22 - 2051) <= 2u )
    FsRtlInitializeOplock(v29);
  if ( *(_WORD *)v22 != 2053 && a3 == 160 && *((const WCHAR **)v22 + 29) == L"$I30" )
    *(_QWORD *)(*((_QWORD *)v22 + 17) + 328LL) = v22;
  if ( (v15 & 1) != 0 )
    *((_DWORD *)v22 + 75) |= 0x20u;
  if ( *(char *)(a2 + 8) < 0 )
    *((_DWORD *)v22 + 75) |= 0x4000u;
  if ( (a5 & 4) != 0 )
    *((_DWORD *)v22 + 75) |= 0x40u;
  *((_QWORD *)v22 + 1) = *(_QWORD *)(a2 + 88) + 64LL;
  v33 = *(_QWORD **)(a2 + 56);
  if ( *v33 != a2 + 48 )
    __fastfail(3u);
  *((_QWORD *)v22 + 15) = a2 + 48;
  *((_QWORD *)v22 + 16) = v33;
  *v33 = v22 + 120;
  *(_QWORD *)(a2 + 56) = v22 + 120;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
  KeLeaveGuardedRegion();
  return v22;
}

```

## disassembly

```asm
0x140309cb0  mov     [rsp+arg_0], rbx
0x140309cb5  mov     [rsp+arg_18], rsi
0x140309cba  mov     [rsp+arg_8], rdx
0x140309cbf  push    rdi
0x140309cc0  push    r12
0x140309cc2  push    r13
0x140309cc4  push    r14
0x140309cc6  push    r15
0x140309cc8  sub     rsp, 80h
0x140309ccf  mov     r15, r9
0x140309cd2  movzx   r14d, r8w
0x140309cd6  mov     rsi, rdx
0x140309cd9  mov     r13, rcx
0x140309cdc  mov     edi, 0A0h
0x140309ce1  cmp     r8w, di
0x140309ce5  jnz     short loc_140309D38
0x140309ce7  mov     rdx, [rdx+148h]
0x140309cee  test    rdx, rdx
0x140309cf1  jz      short loc_140309D38
0x140309cf3  mov     eax, [rdx+12Ch]
0x140309cf9  test    al, 40h
0x140309cfb  jz      short loc_140309D07
0x140309cfd  mov     ecx, [rsi+8]
0x140309d00  bt      rcx, 1Bh
0x140309d05  jnb     short loc_140309D38
0x140309d07  mov     rax, [rsp+0A8h+arg_28]
0x140309d0f  test    rax, rax
0x140309d12  jz      short loc_140309D17
0x140309d14  mov     byte ptr [rax], 1
0x140309d17  mov     rax, rdx
0x140309d1a  lea     r11, [rsp+0A8h+var_28]
0x140309d22  mov     rbx, [r11+30h]
0x140309d26  mov     rsi, [r11+48h]
0x140309d2a  mov     rsp, r11
0x140309d2d  pop     r15
0x140309d2f  pop     r14
0x140309d31  pop     r13
0x140309d33  pop     r12
0x140309d35  pop     rdi
0x140309d36  retn
0x140309d38  mov     r12, [rsp+0A8h+arg_28]
0x140309d40  test    r12, r12
0x140309d43  jz      short loc_140309D4A
0x140309d45  mov     byte ptr [r12], 0
0x140309d4a  test    r9, r9
0x140309d4d  jnz     short loc_140309D65
0x140309d4f  lea     r15, ?RefsFileNameIndex@@3U_UNICODE_STRING@@B; _UNICODE_STRING const RefsFileNameIndex
0x140309d56  lea     rax, qword_14020D488
0x140309d5d  cmp     r14w, di
0x140309d61  cmovnz  r15, rax
0x140309d65  mov     rbx, [rsi+58h]
0x140309d69  call    cs:__imp_KeEnterGuardedRegion
0x140309d70  nop     dword ptr [rax+rax+00h]
0x140309d75  lea     rcx, [rbx+8]; FastMutex
0x140309d79  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140309d80  nop     dword ptr [rax+rax+00h]
0x140309d85  lea     rax, [rsi+30h]
0x140309d89  mov     rbx, [rax]
0x140309d8c  nop     dword ptr [rax+00h]
0x140309d90  cmp     rbx, rax
0x140309d93  jz      loc_140309E58
0x140309d99  cmp     r14w, [rbx+60h]
0x140309d9e  jnz     short loc_140309DDC
0x140309da0  mov     eax, [rbx+0B4h]
0x140309da6  test    al, 40h
0x140309da8  jz      short loc_140309DBA
0x140309daa  cmp     r14w, di
0x140309dae  jnz     short loc_140309DD8
0x140309db0  mov     eax, [rsi+8]
0x140309db3  bt      rax, 1Bh
0x140309db8  jnb     short loc_140309DD8
0x140309dba  movzx   eax, word ptr [rbx+68h]
0x140309dbe  cmp     ax, [r15]
0x140309dc2  jnz     short loc_140309DD8
0x140309dc4  mov     r8d, eax; Size
0x140309dc7  mov     rdx, [r15+8]; Buf2
0x140309dcb  mov     rcx, [rbx+70h]; Buf1
0x140309dcf  call    memcmp
0x140309dd4  test    eax, eax
0x140309dd6  jz      short loc_140309DE1
0x140309dd8  lea     rax, [rsi+30h]
0x140309ddc  mov     rbx, [rbx]
0x140309ddf  jmp     short loc_140309D90
0x140309de1  mov     rcx, [rsi+58h]
0x140309de5  add     rcx, 8; FastMutex
0x140309de9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140309df0  nop     dword ptr [rax+rax+00h]
0x140309df5  call    cs:__imp_KeLeaveGuardedRegion
0x140309dfc  nop     dword ptr [rax+rax+00h]
0x140309e01  test    r12, r12
0x140309e04  jz      short loc_140309E0B
0x140309e06  mov     byte ptr [r12], 1
0x140309e0b  mov     rax, [rbx+10h]
0x140309e0f  mov     rcx, [rax+58h]
0x140309e13  add     rcx, 40h ; '@'
0x140309e17  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140309e1e  nop     dword ptr [rax+rax+00h]
0x140309e23  test    al, al
0x140309e25  jz      short loc_140309E3D
0x140309e27  cmp     byte ptr [r13+28h], 3
0x140309e2c  jz      short loc_140309E3D
0x140309e2e  xor     r8d, r8d
0x140309e31  lea     rdx, [rbx-78h]
0x140309e35  mov     rcx, r13
0x140309e38  call    ?RefsSnapshotScb@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@W4HandleUnloadedSizes@@@Z; RefsSnapshotScb(_IRP_CONTEXT *,_SCB *,HandleUnloadedSizes)
0x140309e3d  test    dword ptr [rbx+20h], 1000000h
0x140309e44  jz      short loc_140309E4F
0x140309e46  lea     rcx, [rbx-78h]; struct _SCB *
0x140309e4a  call    ?RefsDeleteEncryptionContext@@YAXPEAU_SCB@@@Z; RefsDeleteEncryptionContext(_SCB *)
0x140309e4f  lea     rax, [rbx-78h]
0x140309e53  jmp     loc_140309D1A
0x140309e58  mov     edx, dword ptr [rsp+0A8h+arg_20]
0x140309e5f  test    dl, 1
0x140309e62  jz      short loc_140309E8B
0x140309e64  mov     rcx, [rsi+58h]
0x140309e68  add     rcx, 8; FastMutex
0x140309e6c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140309e73  nop     dword ptr [rax+rax+00h]
0x140309e78  call    cs:__imp_KeLeaveGuardedRegion
0x140309e7f  nop     dword ptr [rax+rax+00h]
0x140309e84  xor     eax, eax
0x140309e86  jmp     loc_140309D1A
0x140309e8b  xorps   xmm0, xmm0
0x140309e8e  movups  [rsp+0A8h+var_60], xmm0
0x140309e93  movups  [rsp+0A8h+var_50], xmm0
0x140309e98  xor     r11d, r11d
0x140309e9b  mov     [rsp+0A8h+var_38], r11
0x140309ea0  mov     bl, 1
0x140309ea2  mov     [rsp+0A8h+var_78], bl
0x140309ea6  mov     [rsp+0A8h+var_68], r11
0x140309eab  mov     [rsp+0A8h+var_74], r11w
0x140309eb1  mov     [rsp+0A8h+var_70], r11w
0x140309eb7  mov     edi, 0A0h
0x140309ebc  cmp     r14w, di
0x140309ec0  jnz     short loc_140309F1E
0x140309ec2  mov     rax, [rsi+58h]
0x140309ec6  cmp     qword ptr [rax+100h], 600h
0x140309ed1  jnz     short loc_140309EEA
0x140309ed3  cmp     [rax+0F8h], r11
0x140309eda  jnz     short loc_140309EEA
0x140309edc  mov     r12d, 804h
0x140309ee2  mov     [rsp+0A8h+var_74], r12w
0x140309ee8  jmp     short loc_140309EF8
0x140309eea  mov     eax, 803h
0x140309eef  movzx   r12d, ax
0x140309ef3  mov     [rsp+0A8h+var_74], ax
0x140309ef8  mov     edx, 1B0h
0x140309efd  movzx   r8d, dx
0x140309f01  mov     [rsp+0A8h+arg_10], r8d
0x140309f09  mov     [rsp+0A8h+var_70], dx
0x140309f0e  mov     ecx, 0B0h
0x140309f13  mov     r9d, 80h
0x140309f19  jmp     loc_140309FB1
0x140309f1e  mov     r10d, 805h
0x140309f24  movzx   r12d, r10w
0x140309f28  mov     [rsp+0A8h+var_74], r10w
0x140309f2e  mov     r8d, 1F0h
0x140309f34  mov     [rsp+0A8h+arg_10], r8d
0x140309f3c  mov     [rsp+0A8h+var_70], r8w
0x140309f42  mov     r9d, 80h
0x140309f48  mov     ecx, 0B0h
0x140309f4d  cmp     r14w, r9w
0x140309f51  jz      short loc_140309F59
0x140309f53  cmp     r14w, cx
0x140309f57  jnz     short loc_140309FAC
0x140309f59  mov     eax, [rsi+8]
0x140309f5c  bt      rax, 8
0x140309f61  jnb     short loc_140309FA1
0x140309f63  mov     eax, edx
0x140309f65  and     eax, 8
0x140309f68  jnz     short loc_140309FA1
0x140309f6a  mov     rax, [rsi+58h]
0x140309f6e  mov     rdx, [rax+100h]
0x140309f75  cmp     rdx, 521h
0x140309f7c  jnz     short loc_140309FAC
0x140309f7e  cmp     qword ptr [rax+0F8h], 400h
0x140309f89  jz      short loc_140309F9D
0x140309f8b  cmp     rdx, rdx
0x140309f8e  jnz     short loc_140309FAC
0x140309f90  cmp     qword ptr [rax+0F8h], 200h
0x140309f9b  jnz     short loc_140309FAC
0x140309f9d  mov     bl, 5
0x140309f9f  jmp     short loc_140309FA8
0x140309fa1  mov     [rsp+0A8h+var_78], 0
0x140309fa6  mov     bl, 4
0x140309fa8  mov     [rsp+0A8h+var_78], bl
0x140309fac  mov     edx, 1B0h; NumberOfBytes
0x140309fb1  mov     [rsp+0A8h+var_68], r11
0x140309fb6  mov     rax, [rsi+8]
0x140309fba  test    al, 2
0x140309fbc  jz      short loc_140309FE1
0x140309fbe  movsx   rdx, r8w; NumberOfBytes
0x140309fc2  mov     ecx, 210h; PoolType
0x140309fc7  mov     r8d, 6E666552h; Tag
0x140309fcd  call    cs:__imp_ExAllocatePoolWithTag
0x140309fd4  nop     dword ptr [rax+rax+00h]
0x140309fd9  or      bl, 2
0x140309fdc  jmp     loc_14030A066
0x140309fe1  cmp     r14w, di
0x140309fe5  jnz     short loc_14030A029
0x140309fe7  bt      rax, 0Ah
0x140309fec  jnb     short loc_14030A002
0x140309fee  lea     rdi, [rsi+170h]
0x140309ff5  cmp     word ptr [rdi], 0
0x140309ff9  jnz     short loc_14030A002
0x140309ffb  mov     [rsp+0A8h+var_68], rdi
0x14030a000  jmp     short loc_14030A077
0x14030a002  mov     ecx, cs:PoolType
0x14030a008  or      ecx, 10h; PoolType
0x14030a00b  mov     r8d, 53666552h; Tag
0x14030a011  call    cs:__imp_ExAllocatePoolWithTag
0x14030a018  nop     dword ptr [rax+rax+00h]
0x14030a01d  mov     [rsp+0A8h+var_68], rax
0x14030a022  mov     qword ptr [rsp+0A8h+var_60], rax
0x14030a027  jmp     short loc_14030A074
0x14030a029  bt      rax, 9
0x14030a02e  jnb     short loc_14030A050
0x14030a030  cmp     r14w, r9w
0x14030a034  jz      short loc_14030A03C
0x14030a036  cmp     r14w, cx
0x14030a03a  jnz     short loc_14030A050
0x14030a03c  lea     rdi, [rsi+170h]
0x14030a043  cmp     word ptr [rdi], 0
0x14030a047  jnz     short loc_14030A050
0x14030a049  mov     [rsp+0A8h+var_68], rdi
0x14030a04e  jmp     short loc_14030A077
0x14030a050  lea     rcx, ?RefsScbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14030a057  call    cs:__imp_ExAllocateFromLookasideListEx
0x14030a05e  nop     dword ptr [rax+rax+00h]
0x14030a063  or      bl, 8
0x14030a066  mov     [rsp+0A8h+var_68], rax
0x14030a06b  mov     qword ptr [rsp+0A8h+var_60], rax
0x14030a070  mov     [rsp+0A8h+var_78], bl
0x14030a074  mov     rdi, rax
0x14030a077  mov     [rsp+0A8h+var_88], r14w
0x14030a07d  mov     r9, rsi
0x14030a080  movzx   r8d, word ptr [rsp+0A8h+arg_10]
0x14030a089  movzx   edx, r12w
0x14030a08d  mov     rcx, rdi
0x14030a090  call    ?Initialize@_SCB@@QEAAXGFAEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@@Z; _SCB::Initialize(ushort,short,_FCB &,_REFS_ATTRIBUTE_TYPE_CODE)
0x14030a095  test    bl, 4
0x14030a098  jz      short loc_14030A10E
0x14030a09a  cmp     qword ptr [rsi+60h], 0
0x14030a09f  jnz     short loc_14030A106
0x14030a0a1  test    dword ptr [r13+4], 10000h
0x14030a0a9  jz      short loc_14030A0B9
0x14030a0ab  cmp     byte ptr [r13+28h], 0
0x14030a0b0  jnz     short loc_14030A0B9
0x14030a0b2  cmp     qword ptr [r13+48h], 0
0x14030a0b7  jnz     short loc_14030A0C7
0x14030a0b9  mov     ecx, dword ptr [rsp+0A8h+arg_20]
0x14030a0c0  mov     eax, ecx
0x14030a0c2  and     eax, 8
0x14030a0c5  jz      short loc_14030A0ED
0x14030a0c7  mov     rdx, [r13+38h]
0x14030a0cb  test    rdx, rdx
0x14030a0ce  jz      short loc_14030A0E5
0x14030a0d0  mov     [rsp+0A8h+var_40], rdx
0x14030a0d5  mov     rcx, r13
0x14030a0d8  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x14030a0dd  mov     qword ptr [r13+38h], 0
0x14030a0e5  mov     r8d, 10h
0x14030a0eb  jmp     short loc_14030A0FB
0x14030a0ed  mov     eax, ecx
0x14030a0ef  and     eax, 10h
0x14030a0f2  neg     eax
0x14030a0f4  sbb     r8d, r8d
0x14030a0f7  and     r8d, 30h
0x14030a0fb  mov     rdx, rsi
0x14030a0fe  mov     rcx, r13
0x14030a101  call    ?RefsAddPagingIoToFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAddPagingIoToFcb(_IRP_CONTEXT *,_FCB *,_REFS_ACQUIRE_FLAGS)
0x14030a106  mov     rax, [rsi+60h]
0x14030a10a  mov     [rdi+10h], rax
0x14030a10e  movzx   r12d, word ptr [r15]
0x14030a112  lea     r13, Buf2; "$I30"
0x14030a119  test    r12w, r12w
0x14030a11d  jz      loc_14030A1B6
0x14030a123  cmp     r12d, 8
0x14030a127  jnz     short loc_14030A14C
0x14030a129  mov     r8d, r12d; Size
0x14030a12c  mov     rdx, r13; Buf2
0x14030a12f  mov     rcx, [r15+8]; Buf1
0x14030a133  call    memcmp
0x14030a138  test    eax, eax
0x14030a13a  jnz     short loc_14030A14C
0x14030a13c  movups  xmm0, xmmword ptr cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Length; _UNICODE_STRING const RefsFileNameIndex ...
0x14030a143  movups  xmmword ptr [rdi+0E0h], xmm0
0x14030a14a  jmp     short loc_14030A1B6
0x14030a14c  mov     [rdi+0E0h], r12w
0x14030a154  movzx   eax, word ptr [r15]
0x14030a158  add     ax, 2
0x14030a15c  mov     [rdi+0E2h], ax
0x14030a163  movzx   edx, word ptr [r15]
0x14030a167  add     rdx, 2; NumberOfBytes
0x14030a16b  mov     ecx, cs:PoolType
0x14030a171  or      ecx, 10h; PoolType
0x14030a174  mov     r8d, 73466552h; Tag
0x14030a17a  call    cs:__imp_ExAllocatePoolWithTag
0x14030a181  nop     dword ptr [rax+rax+00h]
0x14030a186  mov     [rdi+0E8h], rax
  ... truncated ...
```
