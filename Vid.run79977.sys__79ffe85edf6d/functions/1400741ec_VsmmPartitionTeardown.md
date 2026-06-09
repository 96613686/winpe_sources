# VsmmPartitionTeardown

- ea: `0x1400741ec`
- end: `0x1400743a3`
- name: `VsmmPartitionTeardown`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011c20`

## callees

- `0x1400347a4`
- `0x1400347d4`
- `0x140034b64`
- `0x1400741ec`
- `0x1400743ac`
- `0x140074420`
- `0x140074548`
- `0x1400745d8`
- `0x140074a64`
- `0x140075da4`
- `0x140076448`
- `0x140076734`
- `0x140076964`
- `0x14007b454`
- `0x14009fe7c`
- `0x1400cf034`
- `0x1400e6094`
- `0x1400ed598`
- `0x1400fa8c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140074212`
- `ntoskrnl!KeWaitForSingleObject` at `0x140074212`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140074378`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140074378`

## pseudocode

```c
void __fastcall VsmmPartitionTeardown(__int64 a1)
{
  __int64 v2; // rax
  _QWORD *v3; // r14
  unsigned __int8 i; // di
  __int64 v5; // rbp
  int j; // esi

  KeWaitForSingleObject((PVOID)(a1 + 8576), Executive, 0, 0, 0);
  VsmmMemXferPartitionTeardown(a1);
  VidVpGlobalSuspendBegin(a1);
  VsmmEpfPartitionReset(a1);
  if ( *(_BYTE *)(a1 + 10648) )
    VidOpCtrlExUnblock(a1 + 10488);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 3216));
  VsmmVaGpaRangepBackgroundDecommitTeardown(a1);
  if ( (unsigned __int64)((*(_QWORD *)(a1 + 10432) >> 61) - 3LL) <= 1 )
    VsmmPartitionUnblockDeviceAttach(a1);
  VidObjectLockAcquireShared(a1);
  VidObjectLockAcquireExclusive(a1 + 3736);
  VsmmDmSlpCleanup(a1);
  VsmmPpmInfoTeardown(a1);
  v2 = *(_QWORD *)(a1 + 32) & 0x1E0LL;
  if ( v2 == 32 )
  {
    if ( *(_BYTE *)(a1 + 8848) && (*(_DWORD *)(a1 + 8636) != 2 || *(_DWORD *)(a1 + 8632) != 2) )
      VsmmSvcPartitionTeardown(a1);
  }
  else if ( ((v2 - 64) & 0xFFFFFFFFFFFFFFDFuLL) == 0 )
  {
    VsmmHwIsoPartitionTeardown(a1);
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 )
    VsmmVaGpaCoreTeardown(a1);
  VsmmGpaRangeCleanup(a1);
  VsmmCryptPartitionKeysRelease(a1);
  VsmmTeardownMemoryBlockReadWriteBuffers(a1);
  if ( (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0x60 )
    VidTdxTeardown(a1);
  VidObjectLockRelease(a1 + 3736);
  VidObjectLockRelease(a1);
  v3 = VidDeviceExtension;
  for ( i = 0; i < *(_BYTE *)(a1 + 2040); ++i )
  {
    v5 = *(_QWORD *)(v3[33] + 8LL * *(unsigned __int8 *)(i + a1 + 2041)) + 224LL;
    for ( j = 0; j != 2; ++j )
      ExFlushLookasideListEx((PLOOKASIDE_LIST_EX)(v5 + 96LL * j));
  }
}

```

## disassembly

```asm
0x1400741ec  push    rbx
0x1400741ee  push    rbp
0x1400741ef  push    rsi
0x1400741f0  push    rdi
0x1400741f1  push    r14
0x1400741f3  sub     rsp, 30h
0x1400741f7  mov     rbx, rcx
0x1400741fa  mov     [rsp+58h+Timeout], 0; Timeout
0x140074203  add     rcx, 2180h; Object
0x14007420a  xor     r9d, r9d; Alertable
0x14007420d  xor     r8d, r8d; WaitMode
0x140074210  xor     edx, edx; WaitReason
0x140074212  call    cs:__imp_KeWaitForSingleObject
0x140074219  nop     dword ptr [rax+rax+00h]
0x14007421e  mov     rcx, rbx
0x140074221  call    VsmmMemXferPartitionTeardown
0x140074226  mov     rcx, rbx
0x140074229  call    VidVpGlobalSuspendBegin
0x14007422e  mov     rcx, rbx
0x140074231  call    VsmmEpfPartitionReset
0x140074236  cmp     byte ptr [rbx+2998h], 0
0x14007423d  jz      short loc_14007424B
0x14007423f  lea     rcx, [rbx+28F8h]
0x140074246  call    VidOpCtrlExUnblock
0x14007424b  lock dec dword ptr [rbx+0C90h]
0x140074252  mov     rcx, rbx
0x140074255  call    VsmmVaGpaRangepBackgroundDecommitTeardown
0x14007425a  mov     rax, [rbx+28C0h]
0x140074261  shr     rax, 3Dh
0x140074265  sub     rax, 3
0x140074269  cmp     rax, 1
0x14007426d  ja      short loc_140074277
0x14007426f  mov     rcx, rbx
0x140074272  call    VsmmPartitionUnblockDeviceAttach
0x140074277  mov     rcx, rbx
0x14007427a  call    VidObjectLockAcquireShared
0x14007427f  lea     rdi, [rbx+0E98h]
0x140074286  mov     rcx, rdi
0x140074289  call    VidObjectLockAcquireExclusive
0x14007428e  mov     rcx, rbx
0x140074291  call    VsmmDmSlpCleanup
0x140074296  mov     rcx, rbx
0x140074299  call    VsmmPpmInfoTeardown
0x14007429e  mov     rax, [rbx+20h]
0x1400742a2  mov     esi, 1E0h
0x1400742a7  and     rax, rsi
0x1400742aa  cmp     rax, 20h ; ' '
0x1400742ae  jnz     short loc_1400742D5
0x1400742b0  cmp     byte ptr [rbx+2290h], 0
0x1400742b7  jz      short loc_1400742E9
0x1400742b9  cmp     dword ptr [rbx+21BCh], 2
0x1400742c0  jnz     short loc_1400742CB
0x1400742c2  cmp     dword ptr [rbx+21B8h], 2
0x1400742c9  jz      short loc_1400742E9
0x1400742cb  mov     rcx, rbx
0x1400742ce  call    VsmmSvcPartitionTeardown
0x1400742d3  jmp     short loc_1400742E9
0x1400742d5  add     rax, 0FFFFFFFFFFFFFFC0h
0x1400742d9  test    rax, 0FFFFFFFFFFFFFFDFh
0x1400742df  jnz     short loc_1400742E9
0x1400742e1  mov     rcx, rbx
0x1400742e4  call    VsmmHwIsoPartitionTeardown
0x1400742e9  mov     eax, [rbx+10h]
0x1400742ec  bt      rax, 0Fh
0x1400742f1  jnb     short loc_1400742FB
0x1400742f3  mov     rcx, rbx
0x1400742f6  call    VsmmVaGpaCoreTeardown
0x1400742fb  mov     rcx, rbx
0x1400742fe  call    VsmmGpaRangeCleanup
0x140074303  mov     rcx, rbx
0x140074306  call    VsmmCryptPartitionKeysRelease
0x14007430b  mov     rcx, rbx
0x14007430e  call    VsmmTeardownMemoryBlockReadWriteBuffers
0x140074313  mov     eax, [rbx+20h]
0x140074316  and     rax, rsi
0x140074319  cmp     rax, 60h ; '`'
0x14007431d  jnz     short loc_140074327
0x14007431f  mov     rcx, rbx
0x140074322  call    VidTdxTeardown
0x140074327  mov     rcx, rdi
0x14007432a  call    VidObjectLockRelease
0x14007432f  mov     rcx, rbx
0x140074332  call    VidObjectLockRelease
0x140074337  mov     r14, cs:VidDeviceExtension
0x14007433e  xor     dil, dil
0x140074341  cmp     [rbx+7F8h], dil
0x140074348  jbe     short loc_140074397
0x14007434a  movzx   eax, dil
0x14007434e  movzx   ecx, byte ptr [rax+rbx+7F9h]
0x140074356  mov     rax, [r14+108h]
0x14007435d  mov     rbp, [rax+rcx*8]
0x140074361  add     rbp, 0E0h
0x140074368  xor     esi, esi
0x14007436a  movsxd  rax, esi
0x14007436d  lea     rcx, [rax+rax*2]
0x140074371  shl     rcx, 5
0x140074375  add     rcx, rbp; Lookaside
0x140074378  call    cs:__imp_ExFlushLookasideListEx
0x14007437f  nop     dword ptr [rax+rax+00h]
0x140074384  inc     esi
0x140074386  cmp     esi, 2
0x140074389  jnz     short loc_14007436A
0x14007438b  inc     dil
0x14007438e  cmp     dil, [rbx+7F8h]
0x140074395  jb      short loc_14007434A
0x140074397  add     rsp, 30h
0x14007439b  pop     r14
0x14007439d  pop     rdi
0x14007439e  pop     rsi
0x14007439f  pop     rbp
0x1400743a0  pop     rbx
0x1400743a1  retn
```
