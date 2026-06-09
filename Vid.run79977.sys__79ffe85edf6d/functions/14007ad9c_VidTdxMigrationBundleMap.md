# VidTdxMigrationBundleMap

- ea: `0x14007ad9c`
- end: `0x14007b025`
- name: `VidTdxMigrationBundleMap`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140080764`

## callees

- `0x140021c60`
- `0x140021e00`
- `0x140022340`
- `0x140024e18`
- `0x14007ad9c`
- `0x14009b8b4`
- `0x1400f0210`
- `0x1400f0694`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14007aff3`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007aff3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007af2a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007af2a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007aec1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007aec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007afda`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007afda`
- `ntoskrnl!ExAllocatePool2` at `0x14007ae2c`
- `ntoskrnl!ExAllocatePool2` at `0x14007ae2c`

## pseudocode

```c
__int64 __fastcall VidTdxMigrationBundleMap(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v6; // r14
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdi
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // edi
  _QWORD *Pool2; // rsi
  unsigned int i; // edx
  __int64 v14; // rcx
  void *CurrentProcess; // rax
  _BYTE MemoryDescriptorList[304]; // [rsp+50h] [rbp-B0h] BYREF

  memset(MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v6 = *(unsigned int *)(a2 + 16);
  v7 = 0;
  v8 = (unsigned __int64)(v6 + 511) >> 9;
  if ( (unsigned int)v8 > 0x20 )
  {
    v9 = -1073741670;
    v10 = 85;
    v11 = -1073741670;
    Pool2 = 0;
    goto LABEL_15;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8 * v6, 1917084758);
  if ( !Pool2 )
  {
    v9 = -1073741670;
    v10 = 98;
    v11 = -1073741670;
    goto LABEL_15;
  }
  memset(&MemoryDescriptorList[12], 0, 28);
  *(_QWORD *)MemoryDescriptorList = 0;
  *(_WORD *)&MemoryDescriptorList[8] = 8 * (v8 + 6);
  *(_DWORD *)&MemoryDescriptorList[40] = (_DWORD)v8 << 12;
  *(_WORD *)&MemoryDescriptorList[10] = 2;
  *(_DWORD *)&MemoryDescriptorList[44] = 0;
  if ( (_DWORD)v8 )
    memmove(&MemoryDescriptorList[48], (const void *)(a2 + 24), 8LL * (unsigned int)v8);
  v7 = MmMapLockedPagesSpecifyCache((PMDL)MemoryDescriptorList, 0, MmNonCached, 0, 0, 0x40000010u);
  if ( !v7 )
  {
    v9 = -1073741670;
    v10 = 124;
    v11 = -1073741670;
    goto LABEL_15;
  }
  for ( i = 0; i < *(_DWORD *)(a2 + 16); Pool2[v14] = v7[v14] )
    v14 = i++;
  v9 = VidClientBufferPrepareFromOverlayPages(a2 + 280, Pool2, (unsigned int)v6);
  v11 = v9;
  if ( v9 < 0 )
  {
    v10 = 144;
    goto LABEL_15;
  }
  CurrentProcess = (void *)PsGetCurrentProcess();
  v9 = VidClientBufferShare(a2 + 280, 0, (_QWORD *)(a2 + 280), 0, CurrentProcess, (_QWORD *)(a2 + 368));
  v11 = v9;
  if ( v9 < 0 )
  {
    v10 = 158;
LABEL_15:
    VidTracePartitionErrorInternal0(
      (__int64)"VidTdxMigrationBundleMap",
      (__int64)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
      v10,
      a1 + 656,
      (unsigned __int16 *)(a1 + 120),
      *(_QWORD *)(a1 + 648),
      v9);
    VidClientBufferUnShare(a2 + 280, 0, a2 + 280);
    *(_QWORD *)(a2 + 368) = 0;
    if ( !Pool2 )
      goto LABEL_19;
    goto LABEL_18;
  }
  v11 = 0;
  *a3 = *(_QWORD *)(a2 + 368);
  *a4 = (unsigned int)((_DWORD)v6 << 12);
LABEL_18:
  ExFreePoolWithTag(Pool2, 0x72446456u);
LABEL_19:
  if ( v7 )
    MmUnmapLockedPages(v7, (PMDL)MemoryDescriptorList);
  return v11;
}

```

## disassembly

```asm
0x14007ad9c  push    rbp
0x14007ad9e  push    rbx
0x14007ad9f  push    rsi
0x14007ada0  push    rdi
0x14007ada1  push    r12
0x14007ada3  push    r13
0x14007ada5  push    r14
0x14007ada7  push    r15
0x14007ada9  lea     rbp, [rsp-98h]
0x14007adb1  sub     rsp, 198h
0x14007adb8  mov     rax, cs:__security_cookie
0x14007adbf  xor     rax, rsp
0x14007adc2  mov     [rbp+0D0h+var_50], rax
0x14007adc9  mov     [rsp+1D0h+var_190], r8
0x14007adce  mov     r13, rdx
0x14007add1  mov     rbx, rcx
0x14007add4  mov     [rsp+1D0h+var_188], r9
0x14007add9  xor     edx, edx; Val
0x14007addb  lea     rcx, [rsp+1D0h+MemoryDescriptorList]; void *
0x14007ade0  mov     r8d, 130h; Size
0x14007ade6  call    memset
0x14007adeb  mov     r14d, [r13+10h]
0x14007adef  xor     r12d, r12d
0x14007adf2  mov     r15d, r12d
0x14007adf5  lea     rdi, [r14+1FFh]
0x14007adfc  shr     rdi, 9
0x14007ae00  cmp     edi, 20h ; ' '
0x14007ae03  jbe     short loc_14007AE19
0x14007ae05  mov     eax, 0C000009Ah
0x14007ae0a  lea     r8d, [r12+55h]
0x14007ae0f  mov     edi, eax
0x14007ae11  mov     esi, r12d
0x14007ae14  jmp     loc_14007AF5F
0x14007ae19  lea     rdx, ds:0[r14*8]
0x14007ae21  mov     ecx, 100h
0x14007ae26  mov     r8d, 72446456h
0x14007ae2c  call    cs:__imp_ExAllocatePool2
0x14007ae33  nop     dword ptr [rax+rax+00h]
0x14007ae38  mov     rsi, rax
0x14007ae3b  test    rax, rax
0x14007ae3e  jnz     short loc_14007AE50
0x14007ae40  mov     eax, 0C000009Ah
0x14007ae45  lea     r8d, [rsi+62h]
0x14007ae49  mov     edi, eax
0x14007ae4b  jmp     loc_14007AF5F
0x14007ae50  mov     r8d, edi
0x14007ae53  mov     qword ptr [rsp+1D0h+MemoryDescriptorList+0Ch], r12
0x14007ae58  mov     [rsp+1D0h+MemoryDescriptorList.Process+4], r12
0x14007ae5d  mov     dword ptr [rsp+1D0h+MemoryDescriptorList.MappedSystemVa+4], r12d
0x14007ae62  lea     eax, [r8+6]
0x14007ae66  mov     [rsp+1D0h+MemoryDescriptorList.Next], r12
0x14007ae6b  shl     ax, 3
0x14007ae6f  mov     [rsp+1D0h+MemoryDescriptorList.Size], ax
0x14007ae74  mov     eax, edi
0x14007ae76  shl     rax, 0Ch
0x14007ae7a  mov     [rsp+1D0h+MemoryDescriptorList.ByteCount], eax
0x14007ae7e  mov     eax, 2
0x14007ae83  mov     [rsp+1D0h+MemoryDescriptorList.MdlFlags], ax
0x14007ae88  mov     [rsp+1D0h+MemoryDescriptorList.StartVa], r12
0x14007ae8d  mov     [rsp+1D0h+MemoryDescriptorList.ByteOffset], r12d
0x14007ae92  test    edi, edi
0x14007ae94  jz      short loc_14007AEA7
0x14007ae96  shl     r8, 3; Size
0x14007ae9a  lea     rdx, [r13+18h]; Src
0x14007ae9e  lea     rcx, [rbp+0D0h+var_150]; void *
0x14007aea2  call    memmove
0x14007aea7  mov     [rsp+1D0h+Priority], 40000010h; Priority
0x14007aeaf  lea     rcx, [rsp+1D0h+MemoryDescriptorList]; MemoryDescriptorList
0x14007aeb4  xor     r9d, r9d; RequestedAddress
0x14007aeb7  mov     [rsp+1D0h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14007aebc  xor     r8d, r8d; CacheType
0x14007aebf  xor     edx, edx; AccessMode
0x14007aec1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007aec8  nop     dword ptr [rax+rax+00h]
0x14007aecd  mov     r15, rax
0x14007aed0  test    rax, rax
0x14007aed3  jnz     short loc_14007AEE2
0x14007aed5  mov     eax, 0C000009Ah
0x14007aeda  lea     r8d, [r15+7Ch]
0x14007aede  mov     edi, eax
0x14007aee0  jmp     short loc_14007AF5F
0x14007aee2  mov     edx, r12d
0x14007aee5  cmp     [r13+10h], r12d
0x14007aee9  jbe     short loc_14007AEFD
0x14007aeeb  mov     ecx, edx
0x14007aeed  inc     edx
0x14007aeef  mov     rax, [r15+rcx*8]
0x14007aef3  mov     [rsi+rcx*8], rax
0x14007aef7  cmp     edx, [r13+10h]
0x14007aefb  jb      short loc_14007AEEB
0x14007aefd  lea     r12, [r13+118h]
0x14007af04  mov     r8d, r14d
0x14007af07  mov     rcx, r12
0x14007af0a  mov     rdx, rsi
0x14007af0d  call    VidClientBufferPrepareFromOverlayPages
0x14007af12  mov     edi, eax
0x14007af14  test    eax, eax
0x14007af16  jns     short loc_14007AF23
0x14007af18  mov     r8d, 90h
0x14007af1e  xor     r12d, r12d
0x14007af21  jmp     short loc_14007AF5F
0x14007af23  lea     rdi, [r13+170h]
0x14007af2a  call    cs:__imp_PsGetCurrentProcess
0x14007af31  nop     dword ptr [rax+rax+00h]
0x14007af36  xor     r9d, r9d; int
0x14007af39  mov     qword ptr [rsp+1D0h+Priority], rdi; __int64
0x14007af3e  mov     r8, r12; int
0x14007af41  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rax; Object
0x14007af46  xor     edx, edx; int
0x14007af48  mov     rcx, r12; int
0x14007af4b  call    VidClientBufferShare
0x14007af50  xor     r12d, r12d
0x14007af53  mov     edi, eax
0x14007af55  test    eax, eax
0x14007af57  jns     short loc_14007AFB1
0x14007af59  mov     r8d, 9Eh
0x14007af5f  mov     r11, [rbx+288h]
0x14007af66  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007af6d  lea     r9, [rbx+290h]
0x14007af74  lea     r10, [rbx+78h]
0x14007af78  mov     [rsp+1D0h+var_1A0], eax
0x14007af7c  lea     rcx, aVidtdxmigratio_0; "VidTdxMigrationBundleMap"
0x14007af83  mov     qword ptr [rsp+1D0h+Priority], r11
0x14007af88  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], r10
0x14007af8d  call    VidTracePartitionErrorInternal0
0x14007af92  lea     rcx, [r13+118h]
0x14007af99  xor     edx, edx
0x14007af9b  mov     r8, rcx
0x14007af9e  call    VidClientBufferUnShare
0x14007afa3  mov     [r13+170h], r12
0x14007afaa  test    rsi, rsi
0x14007afad  jz      short loc_14007AFE6
0x14007afaf  jmp     short loc_14007AFD2
0x14007afb1  mov     rax, [r13+170h]
0x14007afb8  mov     edi, r12d
0x14007afbb  mov     rcx, [rsp+1D0h+var_190]
0x14007afc0  shl     r14d, 0Ch
0x14007afc4  mov     [rcx], rax
0x14007afc7  mov     rcx, [rsp+1D0h+var_188]
0x14007afcc  mov     eax, r14d
0x14007afcf  mov     [rcx], rax
0x14007afd2  mov     edx, 72446456h; Tag
0x14007afd7  mov     rcx, rsi; P
0x14007afda  call    cs:__imp_ExFreePoolWithTag
0x14007afe1  nop     dword ptr [rax+rax+00h]
0x14007afe6  test    r15, r15
0x14007afe9  jz      short loc_14007AFFF
0x14007afeb  lea     rdx, [rsp+1D0h+MemoryDescriptorList]; MemoryDescriptorList
0x14007aff0  mov     rcx, r15; BaseAddress
0x14007aff3  call    cs:__imp_MmUnmapLockedPages
0x14007affa  nop     dword ptr [rax+rax+00h]
0x14007afff  mov     eax, edi
0x14007b001  mov     rcx, [rbp+0D0h+var_50]
0x14007b008  xor     rcx, rsp; StackCookie
0x14007b00b  call    __security_check_cookie
0x14007b010  add     rsp, 198h
0x14007b017  pop     r15
0x14007b019  pop     r14
0x14007b01b  pop     r13
0x14007b01d  pop     r12
0x14007b01f  pop     rdi
0x14007b020  pop     rsi
0x14007b021  pop     rbx
0x14007b022  pop     rbp
0x14007b023  retn
```
