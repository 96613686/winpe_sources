# UnionFs::UfsPathCacheManager::StopCacheManagerWorkers(void)

- ea: `0x14003ebb4`
- end: `0x14003ed41`
- name: `?StopCacheManagerWorkers@UfsPathCacheManager@UnionFs@@QEAAXXZ`
- size: `397`
- prototype: `void __fastcall(UnionFs::UfsPathCacheManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006390`
- `0x14003df70`

## callees

- `0x14003b848`
- `0x14003ebb4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ebd9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ebd9`
- `ntoskrnl!KeCancelTimer` at `0x14003ec0a`
- `ntoskrnl!KeCancelTimer` at `0x14003ec0a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ec7e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ec7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ebee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ebee`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ed19`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ed19`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003ec96`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003ecb9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003ec96`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003ecb9`

## pseudocode

```c
void __fastcall UnionFs::UfsPathCacheManager::StopCacheManagerWorkers(UnionFs::UfsPathCacheManager *this)
{
  unsigned __int8 v2; // dl
  __int64 v3; // rcx
  ULONG v4; // r10d
  struct _FLT_GENERIC_WORKITEM *v5; // rcx
  struct _FLT_GENERIC_WORKITEM *v6; // rcx
  UnionFs::UfsPathCacheListItem **v7; // rsi
  UnionFs::UfsPathCacheListItem *v8; // rdi
  UnionFs::UfsPathCacheListItem *v9; // rax
  PVOID Object[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this, &LockHandle);
  *((_BYTE *)this + 8) = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v2 = 0;
  if ( *((_QWORD *)this + 28) )
  {
    KeCancelTimer((PKTIMER)((char *)this + 16));
    v2 = 1;
  }
  v3 = *((_QWORD *)this + 34);
  *(_OWORD *)Object = 0;
  if ( v2 )
    Object[0] = (char *)this + 240;
  v4 = v2;
  if ( v3 )
  {
    Object[v2] = (char *)this + 376;
    v4 = v2 + 1;
  }
  if ( v4 )
    KeWaitForMultipleObjects(v4, Object, WaitAll, Executive, 0, 0, 0, 0);
  v5 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)this + 28);
  if ( v5 )
    FltFreeGenericWorkItem(v5);
  *((_QWORD *)this + 28) = 0;
  v6 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)this + 34);
  if ( v6 )
    FltFreeGenericWorkItem(v6);
  *((_QWORD *)this + 34) = 0;
  v7 = (UnionFs::UfsPathCacheListItem **)((char *)this + 144);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == (UnionFs::UfsPathCacheListItem *)v7 )
      break;
    if ( *((UnionFs::UfsPathCacheListItem ***)v8 + 1) != v7
      || (v9 = *(UnionFs::UfsPathCacheListItem **)v8, *(UnionFs::UfsPathCacheListItem **)(*(_QWORD *)v8 + 8LL) != v8) )
    {
      __fastfail(3u);
    }
    *v7 = v9;
    *((_QWORD *)v9 + 1) = v7;
    --*((_DWORD *)this + 54);
    if ( v8 )
    {
      UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(v8);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v8);
    }
  }
}

```

## disassembly

```asm
0x14003ebb4  mov     r11, rsp
0x14003ebb7  mov     [r11+8], rbx
0x14003ebbb  mov     [r11+10h], rsi
0x14003ebbf  push    rdi
0x14003ebc0  sub     rsp, 70h
0x14003ebc4  xorps   xmm0, xmm0
0x14003ebc7  lea     rdx, [r11-28h]; LockHandle
0x14003ebcb  xor     eax, eax
0x14003ebcd  mov     rbx, rcx
0x14003ebd0  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14003ebd5  mov     [r11-18h], rax
0x14003ebd9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003ebe0  nop     dword ptr [rax+rax+00h]
0x14003ebe5  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14003ebea  mov     byte ptr [rbx+8], 0
0x14003ebee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ebf5  nop     dword ptr [rax+rax+00h]
0x14003ebfa  xor     dl, dl
0x14003ebfc  lea     rcx, [rbx+10h]; PKTIMER
0x14003ec00  cmp     qword ptr [rcx+0D0h], 0
0x14003ec08  jz      short loc_14003EC18
0x14003ec0a  call    cs:__imp_KeCancelTimer
0x14003ec11  nop     dword ptr [rax+rax+00h]
0x14003ec16  mov     dl, 1
0x14003ec18  mov     rcx, [rbx+110h]
0x14003ec1f  xorps   xmm0, xmm0
0x14003ec22  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14003ec27  test    dl, dl
0x14003ec29  jz      short loc_14003EC37
0x14003ec2b  lea     rax, [rbx+0F0h]
0x14003ec32  mov     [rsp+78h+Object], rax
0x14003ec37  movzx   r10d, dl
0x14003ec3b  test    rcx, rcx
0x14003ec3e  jz      short loc_14003EC4F
0x14003ec40  lea     rcx, [rbx+178h]
0x14003ec47  mov     [rsp+r10*8+78h+Object], rcx
0x14003ec4c  inc     r10d
0x14003ec4f  test    r10d, r10d
0x14003ec52  jz      short loc_14003EC8A
0x14003ec54  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14003ec5d  lea     rdx, [rsp+78h+Object]; Object
0x14003ec62  mov     [rsp+78h+Timeout], 0; Timeout
0x14003ec6b  xor     r9d, r9d; WaitReason
0x14003ec6e  mov     [rsp+78h+Alertable], 0; Alertable
0x14003ec73  xor     r8d, r8d; WaitType
0x14003ec76  mov     ecx, r10d; Count
0x14003ec79  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14003ec7e  call    cs:__imp_KeWaitForMultipleObjects
0x14003ec85  nop     dword ptr [rax+rax+00h]
0x14003ec8a  mov     rcx, [rbx+0E0h]; FltWorkItem
0x14003ec91  test    rcx, rcx
0x14003ec94  jz      short loc_14003ECA2
0x14003ec96  call    cs:__imp_FltFreeGenericWorkItem
0x14003ec9d  nop     dword ptr [rax+rax+00h]
0x14003eca2  mov     qword ptr [rbx+0E0h], 0
0x14003ecad  mov     rcx, [rbx+110h]; FltWorkItem
0x14003ecb4  test    rcx, rcx
0x14003ecb7  jz      short loc_14003ECC5
0x14003ecb9  call    cs:__imp_FltFreeGenericWorkItem
0x14003ecc0  nop     dword ptr [rax+rax+00h]
0x14003ecc5  mov     qword ptr [rbx+110h], 0
0x14003ecd0  lea     rsi, [rbx+90h]
0x14003ecd7  mov     rdi, [rsi]
0x14003ecda  cmp     rdi, rsi
0x14003ecdd  jz      short loc_14003ED2E
0x14003ecdf  cmp     [rdi+8], rsi
0x14003ece3  jnz     short loc_14003ED27
0x14003ece5  mov     rax, [rdi]
0x14003ece8  cmp     [rax+8], rdi
0x14003ecec  jnz     short loc_14003ED27
0x14003ecee  mov     [rsi], rax
0x14003ecf1  mov     [rax+8], rsi
0x14003ecf5  dec     dword ptr [rbx+0D8h]
0x14003ecfb  test    rdi, rdi
0x14003ecfe  jz      short loc_14003ECD7
0x14003ed00  mov     rcx, rdi; this
0x14003ed03  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003ed08  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003ed0f  mov     rdx, rdi; Entry
0x14003ed12  add     rcx, 3E0h; Lookaside
0x14003ed19  call    cs:__imp_ExFreeToLookasideListEx
0x14003ed20  nop     dword ptr [rax+rax+00h]
0x14003ed25  jmp     short loc_14003ECD7
0x14003ed27  mov     ecx, 3
0x14003ed2c  int     29h; Win8: RtlFailFast(ecx)
0x14003ed2e  lea     r11, [rsp+78h+var_8]
0x14003ed33  mov     rbx, [r11+10h]
0x14003ed37  mov     rsi, [r11+18h]
0x14003ed3b  mov     rsp, r11
0x14003ed3e  pop     rdi
0x14003ed3f  retn
```
