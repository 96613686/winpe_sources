# AfdRioResizeCq

- ea: `0x14006c900`
- end: `0x14006ce80`
- name: `AfdRioResizeCq`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400064f0`

## callees

- `0x140006b4c`
- `0x140006d68`
- `0x14002fd7c`
- `0x1400445d8`
- `0x140069cfc`
- `0x14006c900`
- `0x140072840`
- `0x140072870`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006c97e`
- `ntoskrnl!ExRaiseStatus` at `0x14006ca6d`
- `ntoskrnl!ExRaiseStatus` at `0x14006cae1`
- `ntoskrnl!ExRaiseStatus` at `0x14006cb07`
- `ntoskrnl!ExRaiseStatus` at `0x14006cb18`
- `ntoskrnl!ExRaiseStatus` at `0x14006c97e`
- `ntoskrnl!ExRaiseStatus` at `0x14006ca6d`
- `ntoskrnl!ExRaiseStatus` at `0x14006cae1`
- `ntoskrnl!ExRaiseStatus` at `0x14006cb07`
- `ntoskrnl!ExRaiseStatus` at `0x14006cb18`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006cabe`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006cabe`
- `ntoskrnl!IoFreeMdl` at `0x14006ce47`
- `ntoskrnl!IoFreeMdl` at `0x14006ce47`
- `ntoskrnl!MmUnlockPages` at `0x14006ce33`
- `ntoskrnl!MmUnlockPages` at `0x14006ce33`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006ca84`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006ca84`
- `ntoskrnl!IoAllocateMdl` at `0x14006ca4c`
- `ntoskrnl!IoAllocateMdl` at `0x14006ca4c`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c9a5`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c9a5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006ce15`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006ce15`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006cba5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006cba5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd3f`
- `ntoskrnl!ExAllocatePool2` at `0x14006cc75`
- `ntoskrnl!ExAllocatePool2` at `0x14006cc75`

## pseudocode

```c
__int64 __fastcall AfdRioResizeCq(__int64 a1, void *a2, unsigned int a3, KPROCESSOR_MODE a4)
{
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  ULONG v7; // edx
  struct _MDL *Mdl; // rax
  struct _MDL *v9; // r13
  _DWORD *MappedSystemVa; // rax
  __int64 v11; // r12
  unsigned int v12; // ebx
  KSPIN_LOCK *v13; // rax
  KSPIN_LOCK *v14; // rsi
  unsigned int v15; // r10d
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // eax
  char *Pool2; // r9
  __int64 v20; // rdx
  __int64 v21; // rax
  size_t v22; // rbx
  struct _MDL *v23; // rax
  char v25; // [rsp+50h] [rbp-D8h]
  unsigned int v26; // [rsp+54h] [rbp-D4h]
  _DWORD *v27; // [rsp+58h] [rbp-D0h]
  unsigned int v28; // [rsp+60h] [rbp-C8h]
  unsigned int v29; // [rsp+64h] [rbp-C4h]
  char v30; // [rsp+70h] [rbp-B8h]
  unsigned int v31; // [rsp+88h] [rbp-A0h]
  char *Src; // [rsp+A0h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-60h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-48h] BYREF
  PVOID VirtualAddress; // [rsp+F0h] [rbp-38h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = 0;
  if ( a3 < 0x18 )
    ExRaiseStatus(-1073741811);
  v35 = 0;
  VirtualAddress = 0;
  if ( a4 )
  {
    if ( ((unsigned __int8)a2 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v35, a2, 0x18u);
  }
  else
  {
    RtlCopyVolatileMemory(&v35, a2, 0x18u);
  }
  v6 = DWORD2(v35);
  if ( !DWORD2(v35) || (unsigned int)(DWORD2(v35) - 1) > 0x8000000 )
    ExRaiseStatus(-1073741811);
  v7 = 24 * DWORD2(v35) + 16;
  v30 = (char)VirtualAddress;
  if ( v7 != HIDWORD(v35) || !VirtualAddress )
    ExRaiseStatus(-1073741811);
  Mdl = IoAllocateMdl(VirtualAddress, v7, 0, 1u, 0);
  v9 = Mdl;
  if ( !Mdl )
    ExRaiseStatus(-1073741801);
  MmProbeAndLockPages(Mdl, a4, IoWriteAccess);
  if ( (v9->MdlFlags & 5) != 0 )
    MappedSystemVa = v9->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
  v27 = MappedSystemVa;
  if ( !MappedSystemVa )
    ExRaiseStatus(-1073741670);
  LODWORD(v11) = 0;
  v12 = 0;
  v25 = 0;
  v13 = (KSPIN_LOCK *)AfdRioFindAndReferenceCq(a1, DWORD1(v35));
  v14 = v13;
  if ( !v13 )
  {
    v5 = -1073741811;
    v15 = 0;
    goto LABEL_43;
  }
  KeAcquireInStackQueuedSpinLock(v13, &LockHandle);
  v25 = 1;
  v15 = *((_DWORD *)v14 + 7);
  v29 = v15;
  v11 = *(unsigned int *)v14[2];
  v12 = *(_DWORD *)(v14[2] + 4);
  v31 = v12;
  if ( (unsigned int)v11 >= v15 || v12 >= v15 )
  {
    v5 = -1073741436;
    goto LABEL_43;
  }
  v26 = v6;
  v16 = v12 - v11;
  v17 = *((_DWORD *)v14 + 9);
  if ( v12 < (unsigned int)v11 )
  {
    v16 += v15;
    v28 = v16;
    if ( v17 != v15 && v17 >= (unsigned int)v11 )
      goto LABEL_29;
    if ( v17 < v12 )
    {
      v18 = v15 + v17 - v11;
      goto LABEL_34;
    }
  }
  else
  {
    v28 = v12 - v11;
    if ( v17 >= (unsigned int)v11 && v17 < v12 )
    {
LABEL_29:
      v18 = v17 - v11;
LABEL_34:
      v26 = v18;
    }
  }
  if ( v6 <= *((_DWORD *)v14 + 8) || v6 <= v16 )
  {
    v5 = -1073741618;
  }
  else
  {
    Pool2 = (char *)ExAllocatePool2(97, 24 * v6, 1364150610);
    Src = Pool2;
    v20 = v14[2] + 24 * v11;
    if ( v12 < (unsigned int)v11 )
    {
      v22 = (unsigned int)(24 * (*((_DWORD *)v14 + 7) - v11));
      RtlCopyVolatileMemory(Pool2, (const void *)(v20 + 16), v22);
      Pool2 = &Src[v22];
      v20 = v14[2];
      v12 = v31;
      v21 = v31;
    }
    else
    {
      v21 = v12 - (unsigned int)v11;
    }
    RtlCopyVolatileMemory(Pool2, (const void *)(v20 + 16), 24 * v21);
    RtlCopyVolatileMemory(v27 + 4, Src, 24LL * v28);
    *v27 = 0;
    v27[1] = v28;
    *((_DWORD *)v14 + 9) = v26;
    v14[2] = (KSPIN_LOCK)v27;
    *((_DWORD *)v14 + 7) = v6;
    ExFreePoolWithTag(Src, 0x514F4952u);
    v23 = (struct _MDL *)v14[1];
    v14[1] = (KSPIN_LOCK)v9;
    v9 = v23;
    v15 = v29;
  }
LABEL_43:
  if ( v14 )
  {
    AFDETW_RIO_TRACE_CQ_RESIZE(
      (_DWORD)v14,
      v15 - 1,
      v11,
      v12,
      *((_DWORD *)v14 + 8),
      v6 - 1,
      v30,
      (char)v27,
      24 * v6 + 16,
      v5);
    if ( v25 )
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    AfdRioDereferenceCqInline(v14);
  }
  MmUnlockPages(v9);
  if ( v9 )
    IoFreeMdl(v9);
  return v5;
}

```

## disassembly

```asm
0x14006c900  mov     r11, rsp
0x14006c903  mov     [r11+18h], rbx
0x14006c907  push    rsi
0x14006c908  push    r12
0x14006c90a  push    r13
0x14006c90c  push    r14
0x14006c90e  push    r15
0x14006c910  sub     rsp, 100h
0x14006c917  mov     rax, cs:__security_cookie
0x14006c91e  xor     rax, rsp
0x14006c921  mov     [rsp+128h+var_30], rax
0x14006c929  mov     bl, r9b
0x14006c92c  mov     [rsp+128h+var_90], rcx
0x14006c934  mov     [rsp+128h+var_98], rcx
0x14006c93c  xorps   xmm0, xmm0
0x14006c93f  xor     eax, eax
0x14006c941  movups  xmmword ptr [r11-60h], xmm0
0x14006c946  mov     [r11-50h], rax
0x14006c94a  mov     [r11-80h], rax
0x14006c94e  mov     [r11-78h], rax
0x14006c952  mov     [r11-70h], rax
0x14006c956  mov     [rsp+128h+var_B0], eax
0x14006c95a  mov     [rsp+128h+var_C0], eax
0x14006c95e  mov     [rsp+128h+var_A8], eax
0x14006c965  mov     [rsp+128h+var_D7], al
0x14006c969  xor     r14d, r14d
0x14006c96c  mov     [rsp+128h+var_AC], r14d
0x14006c971  lea     ecx, [rax+18h]
0x14006c974  cmp     r8d, ecx
0x14006c977  jnb     short loc_14006C98A
0x14006c979  mov     ecx, 0C000000Dh; Status
0x14006c97e  call    cs:__imp_ExRaiseStatus
0x14006c98a  xor     eax, eax
0x14006c98c  movups  [rsp+128h+var_48], xmm0
0x14006c994  mov     [rsp+128h+VirtualAddress], rax
0x14006c99c  test    bl, bl
0x14006c99e  jz      short loc_14006C9C8
0x14006c9a0  test    dl, 3
0x14006c9a3  jz      short loc_14006C9B2
0x14006c9a5  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c9ac  nop     dword ptr [rax+rax+00h]
0x14006c9b1  int     3; Trap to Debugger
0x14006c9b2  test    bl, bl
0x14006c9b4  jz      short loc_14006C9C8
0x14006c9b6  mov     r8, rcx; Size
0x14006c9b9  lea     rcx, [rsp+128h+var_48]; void *
0x14006c9c1  call    RtlCopyFromUser
0x14006c9c6  jmp     short loc_14006C9D8
0x14006c9c8  mov     r8, rcx; Size
0x14006c9cb  lea     rcx, [rsp+128h+var_48]; void *
0x14006c9d3  call    RtlCopyVolatileMemory
0x14006c9d8  mov     r15d, dword ptr [rsp+128h+var_48+8]
0x14006c9e0  mov     [rsp+128h+var_C0], r15d
0x14006c9e5  test    r15d, r15d
0x14006c9e8  jz      loc_14006CB13
0x14006c9ee  lea     eax, [r15-1]
0x14006c9f2  cmp     eax, 8000000h
0x14006c9f7  ja      loc_14006CB13
0x14006c9fd  lea     eax, [r15+r15*2]
0x14006ca01  lea     edx, ds:10h[rax*8]; Length
0x14006ca08  mov     [rsp+128h+var_A8], edx
0x14006ca0f  mov     rax, [rsp+128h+VirtualAddress]
0x14006ca17  mov     [rsp+128h+var_B8], rax
0x14006ca1c  mov     [rsp+128h+var_70], rax
0x14006ca24  cmp     edx, dword ptr [rsp+128h+var_48+0Ch]
0x14006ca2b  jnz     loc_14006CB02
0x14006ca31  test    rax, rax
0x14006ca34  jz      loc_14006CB02
0x14006ca3a  mov     [rsp+128h+Irp], 0; Irp
0x14006ca43  mov     r9b, 1; ChargeQuota
0x14006ca46  xor     r8d, r8d; SecondaryBuffer
0x14006ca49  mov     rcx, rax; VirtualAddress
0x14006ca4c  call    cs:__imp_IoAllocateMdl
0x14006ca53  nop     dword ptr [rax+rax+00h]
0x14006ca58  mov     r13, rax
0x14006ca5b  mov     [rsp+128h+MemoryDescriptorList], rax
0x14006ca63  test    rax, rax
0x14006ca66  jnz     short loc_14006CA79
0x14006ca68  mov     ecx, 0C0000017h; Status
0x14006ca6d  call    cs:__imp_ExRaiseStatus
0x14006ca79  mov     r8d, 1; Operation
0x14006ca7f  mov     dl, bl; AccessMode
0x14006ca81  mov     rcx, r13; MemoryDescriptorList
0x14006ca84  call    cs:__imp_MmProbeAndLockPages
0x14006ca8b  nop     dword ptr [rax+rax+00h]
0x14006ca90  mov     [rsp+128h+var_D7], 1
0x14006ca95  test    byte ptr [r13+0Ah], 5
0x14006ca9a  jz      short loc_14006CAA2
0x14006ca9c  mov     rax, [r13+18h]
0x14006caa0  jmp     short loc_14006CACA
0x14006caa2  mov     [rsp+128h+Priority], 40000010h; Priority
0x14006caaa  mov     dword ptr [rsp+128h+Irp], 0; BugCheckOnFailure
0x14006cab2  xor     r9d, r9d; RequestedAddress
0x14006cab5  xor     edx, edx; AccessMode
0x14006cab7  lea     r8d, [r9+1]; CacheType
0x14006cabb  mov     rcx, r13; MemoryDescriptorList
0x14006cabe  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006cac5  nop     dword ptr [rax+rax+00h]
0x14006caca  mov     [rsp+128h+var_D0], rax
0x14006cacf  mov     [rsp+128h+var_78], rax
0x14006cad7  test    rax, rax
0x14006cada  jnz     short loc_14006CAED
0x14006cadc  mov     ecx, 0C000009Ah; Status
0x14006cae1  call    cs:__imp_ExRaiseStatus
0x14006caed  mov     edx, dword ptr [rsp+128h+var_48+4]
0x14006caf4  mov     [rsp+128h+var_B0], edx
0x14006caf8  mov     rax, [rsp+128h+var_90]
0x14006cb00  jmp     short loc_14006CB5D
0x14006cb02  mov     ecx, 0C000000Dh; Status
0x14006cb07  call    cs:__imp_ExRaiseStatus
0x14006cb13  mov     ecx, 0C000000Dh; Status
0x14006cb18  call    cs:__imp_ExRaiseStatus
0x14006cb25  mov     r13, [rsp+128h+MemoryDescriptorList]
0x14006cb2d  mov     rax, [rsp+128h+var_78]
0x14006cb35  mov     [rsp+128h+var_D0], rax
0x14006cb3a  mov     rcx, [rsp+128h+var_70]
0x14006cb42  mov     [rsp+128h+var_B8], rcx
0x14006cb47  mov     edx, [rsp+128h+var_B0]
0x14006cb4b  mov     r15d, [rsp+128h+var_C0]
0x14006cb50  mov     r14d, [rsp+128h+var_AC]
0x14006cb55  mov     rax, [rsp+128h+var_98]
0x14006cb5d  xor     esi, esi
0x14006cb5f  xor     r12d, r12d
0x14006cb62  xor     ebx, ebx
0x14006cb64  xor     r10d, r10d
0x14006cb67  mov     [rsp+128h+var_D8], bl
0x14006cb6b  test    r14d, r14d
0x14006cb6e  js      loc_14006CDB7
0x14006cb74  mov     rcx, rax
0x14006cb77  call    AfdRioFindAndReferenceCq
0x14006cb7c  mov     rsi, rax
0x14006cb7f  mov     [rsp+128h+var_68], rax
0x14006cb87  test    rax, rax
0x14006cb8a  jnz     short loc_14006CB9A
0x14006cb8c  mov     r14d, 0C000000Dh
0x14006cb92  mov     r10d, ebx
0x14006cb95  jmp     loc_14006CDB7
0x14006cb9a  lea     rdx, [rsp+128h+LockHandle]; LockHandle
0x14006cba2  mov     rcx, rsi; SpinLock
0x14006cba5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006cbac  nop     dword ptr [rax+rax+00h]
0x14006cbb1  mov     r10b, 1
0x14006cbb4  mov     [rsp+128h+var_D8], r10b
0x14006cbb9  mov     [rsp+128h+var_D6], r10b
0x14006cbbe  mov     r10d, [rsi+1Ch]
0x14006cbc2  mov     [rsp+128h+var_C4], r10d
0x14006cbc7  mov     dword ptr [rsp+128h+var_90], r10d
0x14006cbcf  mov     rax, [rsi+10h]
0x14006cbd3  mov     r12d, [rax]
0x14006cbd6  mov     [rsp+128h+var_9C], r12d
0x14006cbde  mov     rax, [rsi+10h]
0x14006cbe2  mov     ebx, [rax+4]
0x14006cbe5  mov     [rsp+128h+var_A0], ebx
0x14006cbec  mov     dword ptr [rsp+128h+var_98], ebx
0x14006cbf3  mov     ecx, [rsi+1Ch]
0x14006cbf6  cmp     r12d, ecx
0x14006cbf9  jnb     loc_14006CDB1
0x14006cbff  cmp     ebx, ecx
0x14006cc01  jnb     loc_14006CDB1
0x14006cc07  mov     [rsp+128h+var_D4], r15d
0x14006cc0c  mov     edx, ebx
0x14006cc0e  sub     edx, r12d
0x14006cc11  mov     [rsp+128h+var_A4], edx
0x14006cc18  mov     eax, [rsi+24h]
0x14006cc1b  cmp     ebx, r12d
0x14006cc1e  jb      short loc_14006CC32
0x14006cc20  mov     [rsp+128h+var_C8], edx
0x14006cc24  cmp     eax, r12d
0x14006cc27  jb      short loc_14006CC4E
0x14006cc29  cmp     eax, ebx
0x14006cc2b  jnb     short loc_14006CC4E
0x14006cc2d  sub     eax, r12d
0x14006cc30  jmp     short loc_14006CC4A
0x14006cc32  add     edx, ecx
0x14006cc34  mov     [rsp+128h+var_C8], edx
0x14006cc38  cmp     eax, ecx
0x14006cc3a  jz      short loc_14006CC41
0x14006cc3c  cmp     eax, r12d
0x14006cc3f  jnb     short loc_14006CC2D
0x14006cc41  cmp     eax, ebx
0x14006cc43  jnb     short loc_14006CC4E
0x14006cc45  sub     eax, r12d
0x14006cc48  add     eax, ecx
0x14006cc4a  mov     [rsp+128h+var_D4], eax
0x14006cc4e  cmp     r15d, [rsi+20h]
0x14006cc52  jbe     loc_14006CDA9
0x14006cc58  cmp     r15d, edx
0x14006cc5b  jbe     loc_14006CDA9
0x14006cc61  lea     eax, [r15+r15*2]
0x14006cc65  shl     eax, 3
0x14006cc68  mov     edx, eax
0x14006cc6a  mov     ecx, 61h ; 'a'
0x14006cc6f  mov     r8d, 514F4952h
0x14006cc75  call    cs:__imp_ExAllocatePool2
0x14006cc7c  nop     dword ptr [rax+rax+00h]
0x14006cc81  mov     r9, rax
0x14006cc84  mov     [rsp+128h+Src], rax
0x14006cc8c  lea     rcx, [r12+r12*2]
0x14006cc90  mov     rax, [rsi+10h]
0x14006cc94  lea     rdx, [rax+rcx*8]
0x14006cc98  cmp     ebx, r12d
0x14006cc9b  jb      short loc_14006CCA6
0x14006cc9d  mov     eax, [rsp+128h+var_A4]
0x14006cca4  jmp     short loc_14006CCDB
0x14006cca6  mov     eax, [rsi+1Ch]
0x14006cca9  sub     eax, r12d
0x14006ccac  lea     eax, [rax+rax*2]
0x14006ccaf  shl     eax, 3
0x14006ccb2  mov     ebx, eax
0x14006ccb4  add     rdx, 10h; Src
0x14006ccb8  mov     r8d, eax; Size
0x14006ccbb  mov     rcx, r9; void *
0x14006ccbe  call    RtlCopyVolatileMemory
0x14006ccc3  mov     r9, [rsp+128h+Src]
0x14006cccb  add     r9, rbx
0x14006ccce  mov     rdx, [rsi+10h]
0x14006ccd2  mov     ebx, [rsp+128h+var_A0]
0x14006ccd9  mov     eax, ebx
0x14006ccdb  lea     r8, [rax+rax*2]
0x14006ccdf  shl     r8, 3; Size
0x14006cce3  add     rdx, 10h; Src
0x14006cce7  mov     rcx, r9; void *
0x14006ccea  call    RtlCopyVolatileMemory
0x14006ccef  mov     eax, [rsp+128h+var_C8]
0x14006ccf3  lea     r8, [rax+rax*2]
0x14006ccf7  shl     r8, 3; Size
0x14006ccfb  mov     rcx, [rsp+128h+var_D0]
0x14006cd00  add     rcx, 10h; void *
0x14006cd04  mov     rdx, [rsp+128h+Src]; Src
0x14006cd0c  call    RtlCopyVolatileMemory
0x14006cd11  mov     rcx, [rsp+128h+var_D0]
0x14006cd16  mov     dword ptr [rcx], 0
0x14006cd1c  mov     eax, [rsp+128h+var_C8]
0x14006cd20  mov     [rcx+4], eax
0x14006cd23  mov     eax, [rsp+128h+var_D4]
0x14006cd27  mov     [rsi+24h], eax
0x14006cd2a  mov     [rsi+10h], rcx
0x14006cd2e  mov     [rsi+1Ch], r15d
0x14006cd32  mov     edx, 514F4952h; Tag
0x14006cd37  mov     rcx, [rsp+128h+Src]; P
0x14006cd3f  call    cs:__imp_ExFreePoolWithTag
0x14006cd46  nop     dword ptr [rax+rax+00h]
0x14006cd4b  mov     rax, [rsi+8]
0x14006cd4f  mov     [rsi+8], r13
0x14006cd53  mov     r13, rax
0x14006cd56  mov     r10d, [rsp+128h+var_C4]
0x14006cd5b  jmp     short loc_14006CDB7
0x14006cd5d  mov     r14d, 0C0000017h
0x14006cd63  mov     r13, [rsp+128h+MemoryDescriptorList]
0x14006cd6b  mov     r8, [rsp+128h+var_78]
0x14006cd73  mov     r9, [rsp+128h+var_70]
0x14006cd7b  mov     rsi, [rsp+128h+var_68]
0x14006cd83  mov     r15d, [rsp+128h+var_C0]
0x14006cd88  mov     r12d, [rsp+128h+var_9C]
0x14006cd90  mov     ebx, dword ptr [rsp+128h+var_98]
0x14006cd97  mov     r10d, dword ptr [rsp+128h+var_90]
0x14006cd9f  mov     al, [rsp+128h+var_D6]
0x14006cda3  mov     [rsp+128h+var_D8], al
0x14006cda7  jmp     short loc_14006CDC1
0x14006cda9  mov     r14d, 0C00000CEh
0x14006cdaf  jmp     short loc_14006CDB7
0x14006cdb1  mov     r14d, 0C0000184h
0x14006cdb7  mov     r8, [rsp+128h+var_D0]
0x14006cdbc  mov     r9, [rsp+128h+var_B8]
0x14006cdc1  test    rsi, rsi
0x14006cdc4  jz      short loc_14006CE29
0x14006cdc6  lea     ecx, [r15-1]
0x14006cdca  lea     edx, [r10-1]
0x14006cdce  mov     [rsp+128h+var_E0], r14d
0x14006cdd3  mov     eax, [rsp+128h+var_A8]
0x14006cdda  mov     [rsp+128h+var_E8], eax
0x14006cdde  mov     [rsp+128h+var_F0], r8
0x14006cde3  mov     [rsp+128h+var_F8], r9
0x14006cde8  mov     [rsp+128h+Priority], ecx
0x14006cdec  mov     eax, [rsi+20h]
0x14006cdef  mov     dword ptr [rsp+128h+Irp], eax
0x14006cdf3  mov     r9d, ebx
0x14006cdf6  mov     r8d, r12d
0x14006cdf9  mov     rcx, rsi
0x14006cdfc  call    AFDETW_RIO_TRACE_CQ_RESIZE
0x14006ce01  test    rsi, rsi
0x14006ce04  jz      short loc_14006CE29
0x14006ce06  cmp     [rsp+128h+var_D8], 0
0x14006ce0b  jz      short loc_14006CE21
0x14006ce0d  lea     rcx, [rsp+128h+LockHandle]; LockHandle
0x14006ce15  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006ce1c  nop     dword ptr [rax+rax+00h]
0x14006ce21  mov     rcx, rsi
0x14006ce24  call    AfdRioDereferenceCqInline
0x14006ce29  cmp     [rsp+128h+var_D7], 0
0x14006ce2e  jz      short loc_14006CE3F
0x14006ce30  mov     rcx, r13; MemoryDescriptorList
0x14006ce33  call    cs:__imp_MmUnlockPages
0x14006ce3a  nop     dword ptr [rax+rax+00h]
0x14006ce3f  test    r13, r13
0x14006ce42  jz      short loc_14006CE53
0x14006ce44  mov     rcx, r13; Mdl
0x14006ce47  call    cs:__imp_IoFreeMdl
0x14006ce4e  nop     dword ptr [rax+rax+00h]
0x14006ce53  mov     eax, r14d
  ... truncated ...
```
