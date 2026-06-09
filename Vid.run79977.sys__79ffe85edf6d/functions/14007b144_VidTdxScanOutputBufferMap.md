# VidTdxScanOutputBufferMap

- ea: `0x14007b144`
- end: `0x14007b381`
- name: `VidTdxScanOutputBufferMap`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140080b74`

## callees

- `0x140021c60`
- `0x140024e18`
- `0x14007b144`
- `0x14009b8b4`
- `0x1400f0210`
- `0x1400f0694`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14007b352`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007b352`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007b295`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007b295`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b23a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007b23a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b33a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b33a`
- `ntoskrnl!ExAllocatePool2` at `0x14007b1d0`
- `ntoskrnl!ExAllocatePool2` at `0x14007b1d0`

## pseudocode

```c
__int64 __fastcall VidTdxScanOutputBufferMap(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v4; // r14
  unsigned __int64 v7; // rdi
  int v8; // eax
  _QWORD *Pool2; // rsi
  unsigned int v10; // edi
  int v11; // r8d
  __int64 i; // rdx
  void *CurrentProcess; // rax
  __int64 v16; // [rsp+48h] [rbp-41h]
  struct _MDL MemoryDescriptorList; // [rsp+58h] [rbp-31h] BYREF
  __int64 v19; // [rsp+88h] [rbp-1h]

  v19 = 0;
  v4 = 0;
  v16 = *(unsigned int *)(a2 + 16);
  memset(&MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v7 = (unsigned __int64)(v16 + 511) >> 9;
  if ( (unsigned int)v7 > 0x200 )
  {
    v8 = -1073741670;
    Pool2 = 0;
    v10 = -1073741670;
    v11 = 338;
    goto LABEL_13;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8LL * (unsigned int)v7, 1917084758);
  if ( !Pool2 )
  {
    v8 = -1073741670;
    v11 = 351;
    v10 = -1073741670;
    goto LABEL_13;
  }
  v19 = *(_QWORD *)(a2 + 24);
  MemoryDescriptorList.Next = 0;
  memset(&MemoryDescriptorList.MdlFlags + 1, 0, 28);
  *(_DWORD *)&MemoryDescriptorList.Size = 131128;
  *(_QWORD *)&MemoryDescriptorList.ByteCount = 4096;
  v4 = MmMapLockedPagesSpecifyCache(&MemoryDescriptorList, 0, MmNonCached, 0, 0, 0x40000010u);
  if ( !v4 )
  {
    v8 = -1073741670;
    v11 = 373;
    v10 = -1073741670;
    goto LABEL_13;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
    Pool2[i] = v4[i];
  v8 = VidClientBufferPrepareFromOverlayPages(a2 + 32, Pool2, (unsigned int)v7);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 393;
    goto LABEL_13;
  }
  CurrentProcess = (void *)PsGetCurrentProcess();
  v8 = VidClientBufferShare(a2 + 32, 0, (_QWORD *)(a2 + 32), 1, CurrentProcess, (_QWORD *)(a2 + 104));
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 407;
LABEL_13:
    VidTracePartitionErrorInternal0(
      (__int64)"VidTdxScanOutputBufferMap",
      (__int64)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
      v11,
      a1 + 656,
      (unsigned __int16 *)(a1 + 120),
      *(_QWORD *)(a1 + 648),
      v8);
    VidClientBufferUnShare(a2 + 32, 0, a2 + 32);
    *(_QWORD *)(a2 + 104) = 0;
    if ( !Pool2 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v10 = 0;
  *a3 = *(_QWORD *)(a2 + 104);
  *a4 = v16;
LABEL_16:
  ExFreePoolWithTag(Pool2, 0x72446456u);
LABEL_17:
  if ( v4 )
    MmUnmapLockedPages(v4, &MemoryDescriptorList);
  return v10;
}

```

## disassembly

```asm
0x14007b144  push    rbp
0x14007b146  push    rbx
0x14007b147  push    rsi
0x14007b148  push    rdi
0x14007b149  push    r12
0x14007b14b  push    r13
0x14007b14d  push    r14
0x14007b14f  push    r15
0x14007b151  lea     rbp, [rsp-1Fh]
0x14007b156  sub     rsp, 0A8h
0x14007b15d  mov     rax, cs:__security_cookie
0x14007b164  xor     rax, rsp
0x14007b167  mov     [rbp+57h+var_50], rax
0x14007b16b  xor     eax, eax
0x14007b16d  mov     [rbp+57h+var_90], r9
0x14007b171  xorps   xmm0, xmm0
0x14007b174  mov     [rbp+57h+var_58], rax
0x14007b178  mov     eax, [rdx+10h]
0x14007b17b  xor     r14d, r14d
0x14007b17e  mov     [rbp+57h+var_A0], r8
0x14007b182  mov     r13, rdx
0x14007b185  mov     rbx, rcx
0x14007b188  mov     [rbp+57h+var_98], rax
0x14007b18c  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.Next], xmm0
0x14007b190  lea     rdi, [rax+1FFh]
0x14007b197  shr     rdi, 9
0x14007b19b  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.Process], xmm0
0x14007b19f  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.StartVa], xmm0
0x14007b1a3  cmp     edi, 200h
0x14007b1a9  jbe     short loc_14007B1BF
0x14007b1ab  mov     eax, 0C000009Ah
0x14007b1b0  xor     esi, esi
0x14007b1b2  mov     edi, eax
0x14007b1b4  mov     r8d, 152h
0x14007b1ba  jmp     loc_14007B2CA
0x14007b1bf  mov     edx, edi
0x14007b1c1  mov     ecx, 100h
0x14007b1c6  shl     rdx, 3
0x14007b1ca  mov     r8d, 72446456h
0x14007b1d0  call    cs:__imp_ExAllocatePool2
0x14007b1d7  nop     dword ptr [rax+rax+00h]
0x14007b1dc  mov     rsi, rax
0x14007b1df  test    rax, rax
0x14007b1e2  jnz     short loc_14007B1F6
0x14007b1e4  mov     eax, 0C000009Ah
0x14007b1e9  mov     r8d, 15Fh
0x14007b1ef  mov     edi, eax
0x14007b1f1  jmp     loc_14007B2CA
0x14007b1f6  mov     rax, [r13+18h]
0x14007b1fa  lea     rcx, [rbp+57h+MemoryDescriptorList]; MemoryDescriptorList
0x14007b1fe  xorps   xmm0, xmm0
0x14007b201  mov     [rsp+0E0h+Priority], 40000010h; Priority
0x14007b209  xor     r9d, r9d; RequestedAddress
0x14007b20c  mov     [rbp+57h+var_58], rax
0x14007b210  xor     r8d, r8d; CacheType
0x14007b213  mov     dword ptr [rbp+57h+MemoryDescriptorList.MappedSystemVa+4], r14d
0x14007b217  xor     edx, edx; AccessMode
0x14007b219  mov     [rbp+57h+MemoryDescriptorList.Next], r14
0x14007b21d  movdqu  xmmword ptr [rbp+57h+MemoryDescriptorList+0Ch], xmm0
0x14007b222  mov     dword ptr [rbp+57h+MemoryDescriptorList.Size], 20038h
0x14007b229  mov     [rbp+57h+MemoryDescriptorList.StartVa], r14
0x14007b22d  mov     qword ptr [rbp+57h+MemoryDescriptorList.ByteCount], 1000h
0x14007b235  mov     [rsp+0E0h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x14007b23a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007b241  nop     dword ptr [rax+rax+00h]
0x14007b246  mov     r14, rax
0x14007b249  test    rax, rax
0x14007b24c  jnz     short loc_14007B25D
0x14007b24e  mov     eax, 0C000009Ah
0x14007b253  mov     r8d, 175h
0x14007b259  mov     edi, eax
0x14007b25b  jmp     short loc_14007B2CA
0x14007b25d  xor     edx, edx
0x14007b25f  test    edi, edi
0x14007b261  jz      short loc_14007B271
0x14007b263  mov     rax, [r14+rdx*8]
0x14007b267  mov     [rsi+rdx*8], rax
0x14007b26b  inc     edx
0x14007b26d  cmp     edx, edi
0x14007b26f  jb      short loc_14007B263
0x14007b271  lea     r15, [r13+20h]
0x14007b275  mov     r8d, edi
0x14007b278  mov     rcx, r15
0x14007b27b  mov     rdx, rsi
0x14007b27e  call    VidClientBufferPrepareFromOverlayPages
0x14007b283  mov     edi, eax
0x14007b285  test    eax, eax
0x14007b287  jns     short loc_14007B291
0x14007b289  mov     r8d, 189h
0x14007b28f  jmp     short loc_14007B2CA
0x14007b291  lea     r12, [r13+68h]
0x14007b295  call    cs:__imp_PsGetCurrentProcess
0x14007b29c  nop     dword ptr [rax+rax+00h]
0x14007b2a1  mov     r9d, 1; int
0x14007b2a7  mov     qword ptr [rsp+0E0h+Priority], r12; __int64
0x14007b2ac  mov     r8, r15; int
0x14007b2af  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], rax; Object
0x14007b2b4  xor     edx, edx; int
0x14007b2b6  mov     rcx, r15; int
0x14007b2b9  call    VidClientBufferShare
0x14007b2be  mov     edi, eax
0x14007b2c0  test    eax, eax
0x14007b2c2  jns     short loc_14007B31A
0x14007b2c4  mov     r8d, 197h
0x14007b2ca  mov     r11, [rbx+288h]
0x14007b2d1  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007b2d8  lea     r9, [rbx+290h]
0x14007b2df  lea     r10, [rbx+78h]
0x14007b2e3  mov     [rsp+0E0h+var_B0], eax
0x14007b2e7  lea     rcx, aVidtdxscanoutp; "VidTdxScanOutputBufferMap"
0x14007b2ee  mov     qword ptr [rsp+0E0h+Priority], r11
0x14007b2f3  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], r10
0x14007b2f8  call    VidTracePartitionErrorInternal0
0x14007b2fd  lea     rcx, [r13+20h]
0x14007b301  xor     edx, edx
0x14007b303  mov     r8, rcx
0x14007b306  call    VidClientBufferUnShare
0x14007b30b  mov     qword ptr [r13+68h], 0
0x14007b313  test    rsi, rsi
0x14007b316  jz      short loc_14007B346
0x14007b318  jmp     short loc_14007B332
0x14007b31a  mov     rax, [r12]
0x14007b31e  xor     edi, edi
0x14007b320  mov     rcx, [rbp+57h+var_A0]
0x14007b324  mov     [rcx], rax
0x14007b327  mov     rcx, [rbp+57h+var_90]
0x14007b32b  mov     rax, [rbp+57h+var_98]
0x14007b32f  mov     [rcx], rax
0x14007b332  mov     edx, 72446456h; Tag
0x14007b337  mov     rcx, rsi; P
0x14007b33a  call    cs:__imp_ExFreePoolWithTag
0x14007b341  nop     dword ptr [rax+rax+00h]
0x14007b346  test    r14, r14
0x14007b349  jz      short loc_14007B35E
0x14007b34b  lea     rdx, [rbp+57h+MemoryDescriptorList]; MemoryDescriptorList
0x14007b34f  mov     rcx, r14; BaseAddress
0x14007b352  call    cs:__imp_MmUnmapLockedPages
0x14007b359  nop     dword ptr [rax+rax+00h]
0x14007b35e  mov     eax, edi
0x14007b360  mov     rcx, [rbp+57h+var_50]
0x14007b364  xor     rcx, rsp; StackCookie
0x14007b367  call    __security_check_cookie
0x14007b36c  add     rsp, 0A8h
0x14007b373  pop     r15
0x14007b375  pop     r14
0x14007b377  pop     r13
0x14007b379  pop     r12
0x14007b37b  pop     rdi
0x14007b37c  pop     rsi
0x14007b37d  pop     rbx
0x14007b37e  pop     rbp
0x14007b37f  retn
```
