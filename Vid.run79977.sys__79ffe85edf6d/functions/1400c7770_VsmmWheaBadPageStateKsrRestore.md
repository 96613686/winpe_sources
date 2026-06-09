# VsmmWheaBadPageStateKsrRestore

- ea: `0x1400c7770`
- end: `0x1400c799f`
- name: `VsmmWheaBadPageStateKsrRestore`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400d216c`

## callees

- `0x140022340`
- `0x14002f724`
- `0x140078ea0`
- `0x1400c7770`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400c796a`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400c796a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c78ff`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c78ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c797b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c797b`
- `ntoskrnl!ExAllocatePool2` at `0x1400c7844`
- `ntoskrnl!ExAllocatePool2` at `0x1400c7844`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400c77b3`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400c77b3`

## pseudocode

```c
__int64 __fastcall VsmmWheaBadPageStateKsrRestore(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r10d
  __int64 v7; // rbx
  __int64 i; // rcx
  unsigned __int64 v9; // r9
  unsigned int v10; // edx
  unsigned __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 Pool2; // rax
  struct _MDL *v15; // rdi
  PVOID v16; // rax
  void *v17; // rsi
  int v18; // eax
  _QWORD v20[2]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD Src[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v22; // [rsp+80h] [rbp+8h] BYREF
  int v23; // [rsp+84h] [rbp+Ch]

  v23 = HIDWORD(a1);
  v22 = 0;
  v4 = KsrClaimPersistedMemory(&VSMM_KSR_GLOBAL_STATE_GUID, a3, v20, 2, 0, &v22);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = v22;
    v7 = 0;
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      v9 = v20[i];
      v10 = 0;
      v11 = v9 >> 40;
      if ( v9 >> 40 )
      {
        v12 = v9 & 0xFFFFFFFFFFLL;
        do
        {
          v13 = v10++;
          Src[v7++] = v12 + v13;
        }
        while ( v10 < (unsigned int)v11 );
      }
    }
    Pool2 = ExAllocatePool2(64, (unsigned int)(8 * v7 + 48), 1833788502);
    v15 = (struct _MDL *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 12) = 0;
      *(_QWORD *)(Pool2 + 20) = 0;
      *(_DWORD *)(Pool2 + 28) = 0;
      *(_QWORD *)Pool2 = 0;
      *(_DWORD *)(Pool2 + 40) = (_DWORD)v7 << 12;
      *(_QWORD *)(Pool2 + 32) = 0;
      *(_WORD *)(Pool2 + 8) = 8 * (v7 + 6);
      *(_DWORD *)(Pool2 + 44) = 0;
      *(_WORD *)(Pool2 + 10) = 2;
      memmove((void *)(Pool2 + 48), Src, 8 * v7);
      v16 = MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000010u);
      v17 = v16;
      if ( v16 )
      {
        v18 = VsmmWheapBadPageTableBuildFromBitmap(a2, v16);
        v5 = v18;
        if ( v18 >= 0 )
        {
          v5 = 0;
          *(_QWORD *)(a2 + 32) = v17;
          *(_QWORD *)(a2 + 40) = v15;
          return v5;
        }
        VidTraceErrorStatusInternal0(
          "VsmmWheaBadPageStateKsrRestore",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
          8328,
          (unsigned int)v18);
        MmUnmapLockedPages(v17, v15);
      }
      else
      {
        v5 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VsmmWheaBadPageStateKsrRestore",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
          8321,
          3221225626LL);
      }
      ExFreePoolWithTag(v15, 0);
    }
    else
    {
      v5 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmWheaBadPageStateKsrRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        8304,
        3221225626LL);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmWheaBadPageStateKsrRestore",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
      8278,
      (unsigned int)v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1400c7770  mov     r11, rsp
0x1400c7773  mov     [r11+8], rcx
0x1400c7777  push    rbx
0x1400c7778  push    rbp
0x1400c7779  push    rsi
0x1400c777a  push    rdi
0x1400c777b  sub     rsp, 58h
0x1400c777f  lea     rcx, [r11+8]
0x1400c7783  mov     dword ptr [r11+8], 0
0x1400c778b  mov     rax, r8
0x1400c778e  mov     [r11-50h], rcx
0x1400c7792  mov     rbp, rdx
0x1400c7795  mov     [rsp+78h+BugCheckOnFailure], 0
0x1400c779d  mov     esi, 2
0x1400c77a2  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x1400c77a9  mov     r9d, esi
0x1400c77ac  lea     r8, [r11-48h]
0x1400c77b0  mov     rdx, rax
0x1400c77b3  call    cs:__imp_KsrClaimPersistedMemory
0x1400c77ba  nop     dword ptr [rax+rax+00h]
0x1400c77bf  mov     ebx, eax
0x1400c77c1  test    eax, eax
0x1400c77c3  jns     short loc_1400C77E6
0x1400c77c5  mov     r9d, eax
0x1400c77c8  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c77cf  mov     r8d, 2056h
0x1400c77d5  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c77dc  call    VidTraceErrorStatusInternal0
0x1400c77e1  jmp     loc_1400C7993
0x1400c77e6  mov     r10d, [rsp+78h+arg_0]
0x1400c77ee  xor     ebx, ebx
0x1400c77f0  xor     ecx, ecx
0x1400c77f2  test    r10d, r10d
0x1400c77f5  jz      short loc_1400C7832
0x1400c77f7  mov     r9, [rsp+rcx*8+78h+var_48]
0x1400c77fc  xor     edx, edx
0x1400c77fe  mov     r8, r9
0x1400c7801  shr     r8, 28h
0x1400c7805  test    r8d, r8d
0x1400c7808  jz      short loc_1400C782B
0x1400c780a  mov     rax, 0FFFFFFFFFFh
0x1400c7814  and     r9, rax
0x1400c7817  mov     eax, edx
0x1400c7819  inc     edx
0x1400c781b  add     rax, r9
0x1400c781e  mov     [rsp+rbx*8+78h+Src], rax
0x1400c7823  inc     rbx
0x1400c7826  cmp     edx, r8d
0x1400c7829  jb      short loc_1400C7817
0x1400c782b  inc     ecx
0x1400c782d  cmp     ecx, r10d
0x1400c7830  jb      short loc_1400C77F7
0x1400c7832  lea     edx, ds:30h[rbx*8]
0x1400c7839  mov     ecx, 40h ; '@'
0x1400c783e  mov     r8d, 6D4D6456h
0x1400c7844  call    cs:__imp_ExAllocatePool2
0x1400c784b  nop     dword ptr [rax+rax+00h]
0x1400c7850  mov     rdi, rax
0x1400c7853  test    rax, rax
0x1400c7856  jnz     short loc_1400C787F
0x1400c7858  mov     r9d, 0C000009Ah
0x1400c785e  mov     ebx, r9d
0x1400c7861  mov     r8d, 2070h
0x1400c7867  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c786e  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c7875  call    VidTraceErrorStatusInternal0
0x1400c787a  jmp     loc_1400C7993
0x1400c787f  mov     qword ptr [rax+0Ch], 0
0x1400c7887  lea     r8, ds:0[rbx*8]; Size
0x1400c788f  mov     qword ptr [rax+14h], 0
0x1400c7897  lea     rdx, [rsp+78h+Src]; Src
0x1400c789c  mov     dword ptr [rax+1Ch], 0
0x1400c78a3  mov     rcx, rbx
0x1400c78a6  mov     qword ptr [rax], 0
0x1400c78ad  shl     rcx, 0Ch
0x1400c78b1  mov     rax, rcx
0x1400c78b4  mov     [rdi+28h], ecx
0x1400c78b7  shr     rax, 0Ch
0x1400c78bb  lea     rcx, [rdi+30h]; void *
0x1400c78bf  add     ax, 6
0x1400c78c3  mov     qword ptr [rdi+20h], 0
0x1400c78cb  shl     ax, 3
0x1400c78cf  mov     [rdi+8], ax
0x1400c78d3  mov     dword ptr [rdi+2Ch], 0
0x1400c78da  mov     [rdi+0Ah], si
0x1400c78de  call    memmove
0x1400c78e3  xor     r9d, r9d; RequestedAddress
0x1400c78e6  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400c78ee  xor     edx, edx; AccessMode
0x1400c78f0  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400c78f8  mov     rcx, rdi; MemoryDescriptorList
0x1400c78fb  lea     r8d, [r9+1]; CacheType
0x1400c78ff  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c7906  nop     dword ptr [rax+rax+00h]
0x1400c790b  mov     rsi, rax
0x1400c790e  test    rax, rax
0x1400c7911  jnz     short loc_1400C7937
0x1400c7913  mov     r9d, 0C000009Ah
0x1400c7919  mov     ebx, r9d
0x1400c791c  mov     r8d, 2081h
0x1400c7922  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c7929  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c7930  call    VidTraceErrorStatusInternal0
0x1400c7935  jmp     short loc_1400C7976
0x1400c7937  mov     rdx, rsi
0x1400c793a  mov     rcx, rbp
0x1400c793d  call    VsmmWheapBadPageTableBuildFromBitmap
0x1400c7942  mov     ebx, eax
0x1400c7944  test    eax, eax
0x1400c7946  jns     short loc_1400C7989
0x1400c7948  mov     r9d, eax
0x1400c794b  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c7952  mov     r8d, 2088h
0x1400c7958  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c795f  call    VidTraceErrorStatusInternal0
0x1400c7964  mov     rdx, rdi; MemoryDescriptorList
0x1400c7967  mov     rcx, rsi; BaseAddress
0x1400c796a  call    cs:__imp_MmUnmapLockedPages
0x1400c7971  nop     dword ptr [rax+rax+00h]
0x1400c7976  xor     edx, edx; Tag
0x1400c7978  mov     rcx, rdi; P
0x1400c797b  call    cs:__imp_ExFreePoolWithTag
0x1400c7982  nop     dword ptr [rax+rax+00h]
0x1400c7987  jmp     short loc_1400C7993
0x1400c7989  xor     ebx, ebx
0x1400c798b  mov     [rbp+20h], rsi
0x1400c798f  mov     [rbp+28h], rdi
0x1400c7993  mov     eax, ebx
0x1400c7995  add     rsp, 58h
0x1400c7999  pop     rdi
0x1400c799a  pop     rsi
0x1400c799b  pop     rbp
0x1400c799c  pop     rbx
0x1400c799d  retn
```
