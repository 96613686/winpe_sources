# AfdRioResizeCq

- ea: `0x14006c760`
- end: `0x14006cce0`
- name: `AfdRioResizeCq`
- size: `1408`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, KPROCESSOR_MODE)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400064f0`

## callees

- `0x140006b4c`
- `0x140006d68`
- `0x14002fd5c`
- `0x1400445b8`
- `0x140069b5c`
- `0x14006c760`
- `0x1400726a0`
- `0x1400726d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006c7de`
- `ntoskrnl!ExRaiseStatus` at `0x14006c8cd`
- `ntoskrnl!ExRaiseStatus` at `0x14006c941`
- `ntoskrnl!ExRaiseStatus` at `0x14006c967`
- `ntoskrnl!ExRaiseStatus` at `0x14006c978`
- `ntoskrnl!ExRaiseStatus` at `0x14006c7de`
- `ntoskrnl!ExRaiseStatus` at `0x14006c8cd`
- `ntoskrnl!ExRaiseStatus` at `0x14006c941`
- `ntoskrnl!ExRaiseStatus` at `0x14006c967`
- `ntoskrnl!ExRaiseStatus` at `0x14006c978`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c91e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c91e`
- `ntoskrnl!IoFreeMdl` at `0x14006cca7`
- `ntoskrnl!IoFreeMdl` at `0x14006cca7`
- `ntoskrnl!MmUnlockPages` at `0x14006cc93`
- `ntoskrnl!MmUnlockPages` at `0x14006cc93`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c8e4`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c8e4`
- `ntoskrnl!IoAllocateMdl` at `0x14006c8ac`
- `ntoskrnl!IoAllocateMdl` at `0x14006c8ac`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c805`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c805`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006cc75`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006cc75`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ca05`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ca05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb9f`
- `ntoskrnl!ExAllocatePool2` at `0x14006cad5`
- `ntoskrnl!ExAllocatePool2` at `0x14006cad5`

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
  char v31; // [rsp+80h] [rbp-A8h]
  unsigned int v32; // [rsp+88h] [rbp-A0h]
  char *Src; // [rsp+A0h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-60h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-48h] BYREF
  PVOID VirtualAddress; // [rsp+F0h] [rbp-38h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = 0;
  if ( a3 < 0x18 )
    ExRaiseStatus(-1073741811);
  v36 = 0;
  VirtualAddress = 0;
  if ( a4 )
  {
    if ( ((unsigned __int8)a2 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v36, a2, 0x18u);
  }
  else
  {
    RtlCopyVolatileMemory(&v36, a2, 0x18u);
  }
  v6 = DWORD2(v36);
  if ( !DWORD2(v36) || (unsigned int)(DWORD2(v36) - 1) > 0x8000000 )
    ExRaiseStatus(-1073741811);
  v7 = 24 * DWORD2(v36) + 16;
  v31 = 24 * BYTE8(v36) + 16;
  v30 = (char)VirtualAddress;
  if ( v7 != HIDWORD(v36) || !VirtualAddress )
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
  v13 = (KSPIN_LOCK *)AfdRioFindAndReferenceCq(a1, DWORD1(v36));
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
  v32 = v12;
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
      v12 = v32;
      v21 = v32;
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
    AFDETW_RIO_TRACE_CQ_RESIZE((_DWORD)v14, v15 - 1, v11, v12, *((_DWORD *)v14 + 8), v6 - 1, v30, (char)v27, v31, v5);
    if ( v25 )
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    AfdRioDereferenceCqInline((volatile signed __int32 *)v14);
  }
  MmUnlockPages(v9);
  if ( v9 )
    IoFreeMdl(v9);
  return v5;
}

```

## disassembly

```asm
0x14006c760  mov     r11, rsp
0x14006c763  mov     [r11+18h], rbx
0x14006c767  push    rsi
0x14006c768  push    r12
0x14006c76a  push    r13
0x14006c76c  push    r14
0x14006c76e  push    r15
0x14006c770  sub     rsp, 100h
0x14006c777  mov     rax, cs:__security_cookie
0x14006c77e  xor     rax, rsp
0x14006c781  mov     [rsp+128h+var_30], rax
0x14006c789  mov     bl, r9b
0x14006c78c  mov     [rsp+128h+var_90], rcx
0x14006c794  mov     [rsp+128h+var_98], rcx
0x14006c79c  xorps   xmm0, xmm0
0x14006c79f  xor     eax, eax
0x14006c7a1  movups  xmmword ptr [r11-60h], xmm0
0x14006c7a6  mov     [r11-50h], rax
0x14006c7aa  mov     [r11-80h], rax
0x14006c7ae  mov     [r11-78h], rax
0x14006c7b2  mov     [r11-70h], rax
0x14006c7b6  mov     [rsp+128h+var_B0], eax
0x14006c7ba  mov     [rsp+128h+var_C0], eax
0x14006c7be  mov     [rsp+128h+var_A8], eax
0x14006c7c5  mov     [rsp+128h+var_D7], al
0x14006c7c9  xor     r14d, r14d
0x14006c7cc  mov     [rsp+128h+var_AC], r14d
0x14006c7d1  lea     ecx, [rax+18h]
0x14006c7d4  cmp     r8d, ecx
0x14006c7d7  jnb     short loc_14006C7EA
0x14006c7d9  mov     ecx, 0C000000Dh; Status
0x14006c7de  call    cs:__imp_ExRaiseStatus
0x14006c7ea  xor     eax, eax
0x14006c7ec  movups  [rsp+128h+var_48], xmm0
0x14006c7f4  mov     [rsp+128h+VirtualAddress], rax
0x14006c7fc  test    bl, bl
0x14006c7fe  jz      short loc_14006C828
0x14006c800  test    dl, 3
0x14006c803  jz      short loc_14006C812
0x14006c805  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c80c  nop     dword ptr [rax+rax+00h]
0x14006c811  int     3; Trap to Debugger
0x14006c812  test    bl, bl
0x14006c814  jz      short loc_14006C828
0x14006c816  mov     r8, rcx; Size
0x14006c819  lea     rcx, [rsp+128h+var_48]; void *
0x14006c821  call    RtlCopyFromUser
0x14006c826  jmp     short loc_14006C838
0x14006c828  mov     r8, rcx; Size
0x14006c82b  lea     rcx, [rsp+128h+var_48]; void *
0x14006c833  call    RtlCopyVolatileMemory
0x14006c838  mov     r15d, dword ptr [rsp+128h+var_48+8]
0x14006c840  mov     [rsp+128h+var_C0], r15d
0x14006c845  test    r15d, r15d
0x14006c848  jz      loc_14006C973
0x14006c84e  lea     eax, [r15-1]
0x14006c852  cmp     eax, 8000000h
0x14006c857  ja      loc_14006C973
0x14006c85d  lea     eax, [r15+r15*2]
0x14006c861  lea     edx, ds:10h[rax*8]; Length
0x14006c868  mov     [rsp+128h+var_A8], edx
0x14006c86f  mov     rax, [rsp+128h+VirtualAddress]
0x14006c877  mov     [rsp+128h+var_B8], rax
0x14006c87c  mov     [rsp+128h+var_70], rax
0x14006c884  cmp     edx, dword ptr [rsp+128h+var_48+0Ch]
0x14006c88b  jnz     loc_14006C962
0x14006c891  test    rax, rax
0x14006c894  jz      loc_14006C962
0x14006c89a  mov     [rsp+128h+Irp], 0; Irp
0x14006c8a3  mov     r9b, 1; ChargeQuota
0x14006c8a6  xor     r8d, r8d; SecondaryBuffer
0x14006c8a9  mov     rcx, rax; VirtualAddress
0x14006c8ac  call    cs:__imp_IoAllocateMdl
0x14006c8b3  nop     dword ptr [rax+rax+00h]
0x14006c8b8  mov     r13, rax
0x14006c8bb  mov     [rsp+128h+MemoryDescriptorList], rax
0x14006c8c3  test    rax, rax
0x14006c8c6  jnz     short loc_14006C8D9
0x14006c8c8  mov     ecx, 0C0000017h; Status
0x14006c8cd  call    cs:__imp_ExRaiseStatus
0x14006c8d9  mov     r8d, 1; Operation
0x14006c8df  mov     dl, bl; AccessMode
0x14006c8e1  mov     rcx, r13; MemoryDescriptorList
0x14006c8e4  call    cs:__imp_MmProbeAndLockPages
0x14006c8eb  nop     dword ptr [rax+rax+00h]
0x14006c8f0  mov     [rsp+128h+var_D7], 1
0x14006c8f5  test    byte ptr [r13+0Ah], 5
0x14006c8fa  jz      short loc_14006C902
0x14006c8fc  mov     rax, [r13+18h]
0x14006c900  jmp     short loc_14006C92A
0x14006c902  mov     [rsp+128h+Priority], 40000010h; Priority
0x14006c90a  mov     dword ptr [rsp+128h+Irp], 0; BugCheckOnFailure
0x14006c912  xor     r9d, r9d; RequestedAddress
0x14006c915  xor     edx, edx; AccessMode
0x14006c917  lea     r8d, [r9+1]; CacheType
0x14006c91b  mov     rcx, r13; MemoryDescriptorList
0x14006c91e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c925  nop     dword ptr [rax+rax+00h]
0x14006c92a  mov     [rsp+128h+var_D0], rax
0x14006c92f  mov     [rsp+128h+var_78], rax
0x14006c937  test    rax, rax
0x14006c93a  jnz     short loc_14006C94D
0x14006c93c  mov     ecx, 0C000009Ah; Status
0x14006c941  call    cs:__imp_ExRaiseStatus
0x14006c94d  mov     edx, dword ptr [rsp+128h+var_48+4]
0x14006c954  mov     [rsp+128h+var_B0], edx
0x14006c958  mov     rax, [rsp+128h+var_90]
0x14006c960  jmp     short loc_14006C9BD
0x14006c962  mov     ecx, 0C000000Dh; Status
0x14006c967  call    cs:__imp_ExRaiseStatus
0x14006c973  mov     ecx, 0C000000Dh; Status
0x14006c978  call    cs:__imp_ExRaiseStatus
0x14006c985  mov     r13, [rsp+128h+MemoryDescriptorList]
0x14006c98d  mov     rax, [rsp+128h+var_78]
0x14006c995  mov     [rsp+128h+var_D0], rax
0x14006c99a  mov     rcx, [rsp+128h+var_70]
0x14006c9a2  mov     [rsp+128h+var_B8], rcx
0x14006c9a7  mov     edx, [rsp+128h+var_B0]
0x14006c9ab  mov     r15d, [rsp+128h+var_C0]
0x14006c9b0  mov     r14d, [rsp+128h+var_AC]
0x14006c9b5  mov     rax, [rsp+128h+var_98]
0x14006c9bd  xor     esi, esi
0x14006c9bf  xor     r12d, r12d
0x14006c9c2  xor     ebx, ebx
0x14006c9c4  xor     r10d, r10d
0x14006c9c7  mov     [rsp+128h+var_D8], bl
0x14006c9cb  test    r14d, r14d
0x14006c9ce  js      loc_14006CC17
0x14006c9d4  mov     rcx, rax
0x14006c9d7  call    AfdRioFindAndReferenceCq
0x14006c9dc  mov     rsi, rax
0x14006c9df  mov     [rsp+128h+var_68], rax
0x14006c9e7  test    rax, rax
0x14006c9ea  jnz     short loc_14006C9FA
0x14006c9ec  mov     r14d, 0C000000Dh
0x14006c9f2  mov     r10d, ebx
0x14006c9f5  jmp     loc_14006CC17
0x14006c9fa  lea     rdx, [rsp+128h+LockHandle]; LockHandle
0x14006ca02  mov     rcx, rsi; SpinLock
0x14006ca05  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006ca0c  nop     dword ptr [rax+rax+00h]
0x14006ca11  mov     r10b, 1
0x14006ca14  mov     [rsp+128h+var_D8], r10b
0x14006ca19  mov     [rsp+128h+var_D6], r10b
0x14006ca1e  mov     r10d, [rsi+1Ch]
0x14006ca22  mov     [rsp+128h+var_C4], r10d
0x14006ca27  mov     dword ptr [rsp+128h+var_90], r10d
0x14006ca2f  mov     rax, [rsi+10h]
0x14006ca33  mov     r12d, [rax]
0x14006ca36  mov     [rsp+128h+var_9C], r12d
0x14006ca3e  mov     rax, [rsi+10h]
0x14006ca42  mov     ebx, [rax+4]
0x14006ca45  mov     [rsp+128h+var_A0], ebx
0x14006ca4c  mov     dword ptr [rsp+128h+var_98], ebx
0x14006ca53  mov     ecx, [rsi+1Ch]
0x14006ca56  cmp     r12d, ecx
0x14006ca59  jnb     loc_14006CC11
0x14006ca5f  cmp     ebx, ecx
0x14006ca61  jnb     loc_14006CC11
0x14006ca67  mov     [rsp+128h+var_D4], r15d
0x14006ca6c  mov     edx, ebx
0x14006ca6e  sub     edx, r12d
0x14006ca71  mov     [rsp+128h+var_A4], edx
0x14006ca78  mov     eax, [rsi+24h]
0x14006ca7b  cmp     ebx, r12d
0x14006ca7e  jb      short loc_14006CA92
0x14006ca80  mov     [rsp+128h+var_C8], edx
0x14006ca84  cmp     eax, r12d
0x14006ca87  jb      short loc_14006CAAE
0x14006ca89  cmp     eax, ebx
0x14006ca8b  jnb     short loc_14006CAAE
0x14006ca8d  sub     eax, r12d
0x14006ca90  jmp     short loc_14006CAAA
0x14006ca92  add     edx, ecx
0x14006ca94  mov     [rsp+128h+var_C8], edx
0x14006ca98  cmp     eax, ecx
0x14006ca9a  jz      short loc_14006CAA1
0x14006ca9c  cmp     eax, r12d
0x14006ca9f  jnb     short loc_14006CA8D
0x14006caa1  cmp     eax, ebx
0x14006caa3  jnb     short loc_14006CAAE
0x14006caa5  sub     eax, r12d
0x14006caa8  add     eax, ecx
0x14006caaa  mov     [rsp+128h+var_D4], eax
0x14006caae  cmp     r15d, [rsi+20h]
0x14006cab2  jbe     loc_14006CC09
0x14006cab8  cmp     r15d, edx
0x14006cabb  jbe     loc_14006CC09
0x14006cac1  lea     eax, [r15+r15*2]
0x14006cac5  shl     eax, 3
0x14006cac8  mov     edx, eax
0x14006caca  mov     ecx, 61h ; 'a'
0x14006cacf  mov     r8d, 514F4952h
0x14006cad5  call    cs:__imp_ExAllocatePool2
0x14006cadc  nop     dword ptr [rax+rax+00h]
0x14006cae1  mov     r9, rax
0x14006cae4  mov     [rsp+128h+Src], rax
0x14006caec  lea     rcx, [r12+r12*2]
0x14006caf0  mov     rax, [rsi+10h]
0x14006caf4  lea     rdx, [rax+rcx*8]
0x14006caf8  cmp     ebx, r12d
0x14006cafb  jb      short loc_14006CB06
0x14006cafd  mov     eax, [rsp+128h+var_A4]
0x14006cb04  jmp     short loc_14006CB3B
0x14006cb06  mov     eax, [rsi+1Ch]
0x14006cb09  sub     eax, r12d
0x14006cb0c  lea     eax, [rax+rax*2]
0x14006cb0f  shl     eax, 3
0x14006cb12  mov     ebx, eax
0x14006cb14  add     rdx, 10h; Src
0x14006cb18  mov     r8d, eax; Size
0x14006cb1b  mov     rcx, r9; void *
0x14006cb1e  call    RtlCopyVolatileMemory
0x14006cb23  mov     r9, [rsp+128h+Src]
0x14006cb2b  add     r9, rbx
0x14006cb2e  mov     rdx, [rsi+10h]
0x14006cb32  mov     ebx, [rsp+128h+var_A0]
0x14006cb39  mov     eax, ebx
0x14006cb3b  lea     r8, [rax+rax*2]
0x14006cb3f  shl     r8, 3; Size
0x14006cb43  add     rdx, 10h; Src
0x14006cb47  mov     rcx, r9; void *
0x14006cb4a  call    RtlCopyVolatileMemory
0x14006cb4f  mov     eax, [rsp+128h+var_C8]
0x14006cb53  lea     r8, [rax+rax*2]
0x14006cb57  shl     r8, 3; Size
0x14006cb5b  mov     rcx, [rsp+128h+var_D0]
0x14006cb60  add     rcx, 10h; void *
0x14006cb64  mov     rdx, [rsp+128h+Src]; Src
0x14006cb6c  call    RtlCopyVolatileMemory
0x14006cb71  mov     rcx, [rsp+128h+var_D0]
0x14006cb76  mov     dword ptr [rcx], 0
0x14006cb7c  mov     eax, [rsp+128h+var_C8]
0x14006cb80  mov     [rcx+4], eax
0x14006cb83  mov     eax, [rsp+128h+var_D4]
0x14006cb87  mov     [rsi+24h], eax
0x14006cb8a  mov     [rsi+10h], rcx
0x14006cb8e  mov     [rsi+1Ch], r15d
0x14006cb92  mov     edx, 514F4952h; Tag
0x14006cb97  mov     rcx, [rsp+128h+Src]; P
0x14006cb9f  call    cs:__imp_ExFreePoolWithTag
0x14006cba6  nop     dword ptr [rax+rax+00h]
0x14006cbab  mov     rax, [rsi+8]
0x14006cbaf  mov     [rsi+8], r13
0x14006cbb3  mov     r13, rax
0x14006cbb6  mov     r10d, [rsp+128h+var_C4]
0x14006cbbb  jmp     short loc_14006CC17
0x14006cbbd  mov     r14d, 0C0000017h
0x14006cbc3  mov     r13, [rsp+128h+MemoryDescriptorList]
0x14006cbcb  mov     r8, [rsp+128h+var_78]
0x14006cbd3  mov     r9, [rsp+128h+var_70]
0x14006cbdb  mov     rsi, [rsp+128h+var_68]
0x14006cbe3  mov     r15d, [rsp+128h+var_C0]
0x14006cbe8  mov     r12d, [rsp+128h+var_9C]
0x14006cbf0  mov     ebx, dword ptr [rsp+128h+var_98]
0x14006cbf7  mov     r10d, dword ptr [rsp+128h+var_90]
0x14006cbff  mov     al, [rsp+128h+var_D6]
0x14006cc03  mov     [rsp+128h+var_D8], al
0x14006cc07  jmp     short loc_14006CC21
0x14006cc09  mov     r14d, 0C00000CEh
0x14006cc0f  jmp     short loc_14006CC17
0x14006cc11  mov     r14d, 0C0000184h
0x14006cc17  mov     r8, [rsp+128h+var_D0]
0x14006cc1c  mov     r9, [rsp+128h+var_B8]
0x14006cc21  test    rsi, rsi
0x14006cc24  jz      short loc_14006CC89
0x14006cc26  lea     ecx, [r15-1]
0x14006cc2a  lea     edx, [r10-1]
0x14006cc2e  mov     [rsp+128h+var_E0], r14d
0x14006cc33  mov     eax, [rsp+128h+var_A8]
0x14006cc3a  mov     [rsp+128h+var_E8], eax
0x14006cc3e  mov     [rsp+128h+var_F0], r8
0x14006cc43  mov     [rsp+128h+var_F8], r9
0x14006cc48  mov     [rsp+128h+Priority], ecx
0x14006cc4c  mov     eax, [rsi+20h]
0x14006cc4f  mov     dword ptr [rsp+128h+Irp], eax
0x14006cc53  mov     r9d, ebx
0x14006cc56  mov     r8d, r12d
0x14006cc59  mov     rcx, rsi
0x14006cc5c  call    AFDETW_RIO_TRACE_CQ_RESIZE
0x14006cc61  test    rsi, rsi
0x14006cc64  jz      short loc_14006CC89
0x14006cc66  cmp     [rsp+128h+var_D8], 0
0x14006cc6b  jz      short loc_14006CC81
0x14006cc6d  lea     rcx, [rsp+128h+LockHandle]; LockHandle
0x14006cc75  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006cc7c  nop     dword ptr [rax+rax+00h]
0x14006cc81  mov     rcx, rsi
0x14006cc84  call    AfdRioDereferenceCqInline
0x14006cc89  cmp     [rsp+128h+var_D7], 0
0x14006cc8e  jz      short loc_14006CC9F
0x14006cc90  mov     rcx, r13; MemoryDescriptorList
0x14006cc93  call    cs:__imp_MmUnlockPages
0x14006cc9a  nop     dword ptr [rax+rax+00h]
0x14006cc9f  test    r13, r13
0x14006cca2  jz      short loc_14006CCB3
0x14006cca4  mov     rcx, r13; Mdl
0x14006cca7  call    cs:__imp_IoFreeMdl
0x14006ccae  nop     dword ptr [rax+rax+00h]
0x14006ccb3  mov     eax, r14d
  ... truncated ...
```
