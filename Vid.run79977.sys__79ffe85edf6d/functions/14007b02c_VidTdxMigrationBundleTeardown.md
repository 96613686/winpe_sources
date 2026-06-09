# VidTdxMigrationBundleTeardown

- ea: `0x14007b02c`
- end: `0x14007b13e`
- name: `VidTdxMigrationBundleTeardown`
- size: `274`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14007b454`
- `0x14007baa4`
- `0x14007c600`

## callees

- `0x140024e18`
- `0x140030990`
- `0x1400309d0`
- `0x14007b02c`
- `0x1400efed0`
- `0x1400f0694`

## import_xrefs

- `ntoskrnl!MmFreePagesFromMdl` at `0x14007b09a`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14007b09a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007b086`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007b086`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b121`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b121`
- `winhvr!WinHvDeleteTdMigrationBundle` at `0x14007b0c8`
- `winhvr!WinHvDeleteTdMigrationBundle` at `0x14007b0c8`

## pseudocode

```c
void __fastcall VidTdxMigrationBundleTeardown(__int64 a1, PMDL *a2)
{
  PMDL v4; // rcx
  PMDL *v5; // rbx
  int v6; // eax

  VidLockAcquireExclusive(a2);
  VidClientBufferUnShare(a2 + 35, 0, a2 + 35);
  a2[46] = 0;
  VidClientBufferUninitialize(a2 + 35);
  v4 = a2[44];
  v5 = a2 + 45;
  if ( v4 )
    MmUnmapLockedPages(v4, *v5);
  if ( *v5 )
  {
    MmFreePagesFromMdl(*v5);
    ExFreePoolWithTag(*v5, 0);
  }
  if ( a2[1] != (PMDL)-1LL )
  {
    v6 = WinHvDeleteTdMigrationBundle(*(_QWORD *)(a1 + 648));
    if ( v6 < 0 )
      VidTracePartitionErrorInternal0(
        (__int64)"VidTdxMigrationBundleTeardown",
        (__int64)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
        245,
        a1 + 656,
        (unsigned __int16 *)(a1 + 120),
        *(_QWORD *)(a1 + 648),
        v6);
  }
  VidLockRelease(a2);
  ExFreePoolWithTag(a2, 0x72446456u);
}

```

## disassembly

```asm
0x14007b02c  mov     [rsp+arg_0], rbx
0x14007b031  mov     [rsp+arg_8], rsi
0x14007b036  push    rdi
0x14007b037  sub     rsp, 40h
0x14007b03b  mov     rsi, rcx
0x14007b03e  mov     rdi, rdx
0x14007b041  mov     rcx, rdx
0x14007b044  call    VidLockAcquireExclusive
0x14007b049  lea     rbx, [rdi+118h]
0x14007b050  xor     edx, edx
0x14007b052  mov     r8, rbx
0x14007b055  mov     rcx, rbx
0x14007b058  call    VidClientBufferUnShare
0x14007b05d  mov     rcx, rbx
0x14007b060  mov     qword ptr [rdi+170h], 0
0x14007b06b  call    VidClientBufferUninitialize
0x14007b070  mov     rcx, [rdi+160h]; BaseAddress
0x14007b077  lea     rbx, [rdi+168h]
0x14007b07e  test    rcx, rcx
0x14007b081  jz      short loc_14007B092
0x14007b083  mov     rdx, [rbx]; MemoryDescriptorList
0x14007b086  call    cs:__imp_MmUnmapLockedPages
0x14007b08d  nop     dword ptr [rax+rax+00h]
0x14007b092  mov     rcx, [rbx]; MemoryDescriptorList
0x14007b095  test    rcx, rcx
0x14007b098  jz      short loc_14007B0B7
0x14007b09a  call    cs:__imp_MmFreePagesFromMdl
0x14007b0a1  nop     dword ptr [rax+rax+00h]
0x14007b0a6  mov     rcx, [rbx]; P
0x14007b0a9  xor     edx, edx; Tag
0x14007b0ab  call    cs:__imp_ExFreePoolWithTag
0x14007b0b2  nop     dword ptr [rax+rax+00h]
0x14007b0b7  mov     rdx, [rdi+8]
0x14007b0bb  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14007b0bf  jz      short loc_14007B111
0x14007b0c1  mov     rcx, [rsi+288h]
0x14007b0c8  call    cs:__imp_WinHvDeleteTdMigrationBundle
0x14007b0cf  nop     dword ptr [rax+rax+00h]
0x14007b0d4  test    eax, eax
0x14007b0d6  jns     short loc_14007B111
0x14007b0d8  mov     [rsp+48h+var_18], eax
0x14007b0dc  lea     rcx, [rsi+78h]
0x14007b0e0  mov     rax, [rsi+288h]
0x14007b0e7  lea     r9, [rsi+290h]
0x14007b0ee  mov     [rsp+48h+var_20], rax
0x14007b0f3  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007b0fa  mov     [rsp+48h+var_28], rcx
0x14007b0ff  mov     r8d, 0F5h
0x14007b105  lea     rcx, aVidtdxmigratio; "VidTdxMigrationBundleTeardown"
0x14007b10c  call    VidTracePartitionErrorInternal0
0x14007b111  mov     rcx, rdi
0x14007b114  call    VidLockRelease
0x14007b119  mov     edx, 72446456h; Tag
0x14007b11e  mov     rcx, rdi; P
0x14007b121  call    cs:__imp_ExFreePoolWithTag
0x14007b128  nop     dword ptr [rax+rax+00h]
0x14007b12d  mov     rbx, [rsp+48h+arg_0]
0x14007b132  mov     rsi, [rsp+48h+arg_8]
0x14007b137  add     rsp, 40h
0x14007b13b  pop     rdi
0x14007b13c  retn
```
