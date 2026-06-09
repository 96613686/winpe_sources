# AfdSetConnectData

- ea: `0x14004f7e0`
- end: `0x14004fc3b`
- name: `AfdSetConnectData`
- size: `1115`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14002fd7c`
- `0x1400445d8`
- `0x140047828`
- `0x14004f7e0`
- `0x140072840`
- `0x140072870`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004f96e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004f96e`
- `ntoskrnl!IoFreeMdl` at `0x14004fc09`
- `ntoskrnl!IoFreeMdl` at `0x14004fc09`
- `ntoskrnl!MmUnlockPages` at `0x14004fbfa`
- `ntoskrnl!MmUnlockPages` at `0x14004fbfa`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004f939`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004f939`
- `ntoskrnl!IoAllocateMdl` at `0x14004f906`
- `ntoskrnl!IoAllocateMdl` at `0x14004f906`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004f89e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004f89e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fa73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fabc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fb9b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fbd1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fa73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fabc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fb9b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fbd1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004f9c6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004f9c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fb56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fb56`
- `ntoskrnl!ExAllocatePool2` at `0x14004fa9b`
- `ntoskrnl!ExAllocatePool2` at `0x14004fb83`
- `ntoskrnl!ExAllocatePool2` at `0x14004fa9b`
- `ntoskrnl!ExAllocatePool2` at `0x14004fb83`

## pseudocode

```c
__int64 __fastcall AfdSetConnectData(
        __int64 a1,
        int a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        _DWORD *VirtualAddress,
        ULONG Length,
        _QWORD *a8)
{
  _DWORD *MappedSystemVa; // r13
  ULONG v11; // r15d
  __int16 *v12; // rdi
  struct _MDL *v13; // r14
  unsigned int v14; // ebx
  struct _MDL *Mdl; // rax
  __int16 v16; // ax
  __int64 ReturnedConnection; // rax
  __int64 *v18; // r12
  __int64 v19; // r12
  __int64 Pool2; // rdi
  char v21; // r12
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  PVOID v29; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-188h] BYREF
  _BYTE *v32; // [rsp+58h] [rbp-170h]
  __int64 v33; // [rsp+60h] [rbp-168h]
  __int64 v34; // [rsp+68h] [rbp-160h] BYREF
  int v35; // [rsp+70h] [rbp-158h]
  _BYTE v36[256]; // [rsp+80h] [rbp-148h] BYREF

  MappedSystemVa = VirtualAddress;
  v11 = Length;
  v34 = 0;
  v35 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v12 = *(__int16 **)(a1 + 24);
  v13 = 0;
  v14 = 0;
  *a8 = 0;
  if ( ((*v12 + 20528) & 0xFFF9) != 0 )
    goto LABEL_2;
  if ( a5 )
  {
    if ( a5 < 0xC )
    {
      v14 = -1073741811;
      goto LABEL_69;
    }
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&v34, a4, 0xCu);
    }
    else
    {
      RtlCopyVolatileMemory(&v34, a4, 0xCu);
    }
  }
  else
  {
    LODWORD(v34) = 0;
    LOBYTE(v35) = 0;
  }
  if ( Length )
  {
    if ( Length <= 0x100 )
    {
      if ( a3 )
      {
        RtlCopyFromUser(v36, VirtualAddress, Length);
        MappedSystemVa = v36;
        v32 = v36;
      }
    }
    else
    {
      Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 1u, 0);
      v13 = Mdl;
      if ( !Mdl )
      {
        v14 = -1073741670;
        goto LABEL_69;
      }
      MmProbeAndLockPages(Mdl, a3, IoReadAccess);
      if ( (v13->MdlFlags & 5) != 0 )
        MappedSystemVa = v13->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v13, 0, MmCached, 0, 0, 0x40000000u);
      v32 = MappedSystemVa;
      if ( !MappedSystemVa )
      {
        v14 = -1073741670;
        goto LABEL_69;
      }
    }
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v12 + 7, &LockHandle);
  if ( *((_DWORD *)v12 + 92) || (*((_DWORD *)v12 + 2) & 0x20000) != 0 || (*((_DWORD *)v12 + 2) & 0x10000) != 0 )
    goto LABEL_68;
  v16 = *v12;
  if ( a5 )
  {
    if ( (v16 & 0xAFD4) == 0xAFD4 )
      ReturnedConnection = AfdFindReturnedConnection(v12, (unsigned int)v34);
    else
      ReturnedConnection = 0;
    if ( !ReturnedConnection )
      goto LABEL_68;
    v18 = (__int64 *)(ReturnedConnection + 224);
  }
  else
  {
    if ( (v16 & 0xAFD2) == 0xAFD2 )
      v19 = *((_QWORD *)v12 + 24);
    else
      v19 = 0;
    if ( v19 )
      v18 = (__int64 *)(v19 + 224);
    else
      v18 = (__int64 *)(v12 + 104);
  }
  if ( (*((_DWORD *)v12 + 2) & 0x100) == 0 )
  {
    Pool2 = *v18;
    if ( !*v18 )
    {
      Pool2 = ExAllocatePool2(97, 232, 1667524161);
      v33 = Pool2;
      *v18 = Pool2;
    }
    v21 = 0;
    v22 = a2 - 73803;
    if ( v22 )
    {
      v23 = v22 - 4;
      if ( v23 )
      {
        v24 = v23 - 4;
        if ( v24 )
        {
          v25 = v24 - 4;
          if ( v25 )
          {
            v26 = v25 - 20;
            if ( v26 )
            {
              v27 = v26 - 4;
              if ( v27 )
              {
                v28 = v27 - 4;
                if ( v28 )
                {
                  if ( v28 != 4 )
                    goto LABEL_68;
                  Pool2 += 112;
                }
                else
                {
                  Pool2 += 96;
                }
              }
              else
              {
                Pool2 += 48;
              }
            }
            else
            {
              Pool2 += 32;
            }
            v21 = 1;
            if ( Length >= 4 )
            {
              v11 = *MappedSystemVa;
              goto LABEL_58;
            }
LABEL_68:
            KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_2:
            v14 = -1073741811;
            goto LABEL_69;
          }
          Pool2 += 80;
        }
        else
        {
          Pool2 += 64;
        }
      }
      else
      {
        Pool2 += 16;
      }
    }
LABEL_58:
    v29 = *(PVOID *)Pool2;
    if ( *(_QWORD *)Pool2 )
    {
      if ( *(_DWORD *)(Pool2 + 8) >= v11 )
      {
LABEL_65:
        if ( !v21 )
          RtlCopyVolatileMemory(v29, MappedSystemVa, v11);
        *(_DWORD *)(Pool2 + 8) = v11;
        goto LABEL_38;
      }
      if ( v29 )
        ExFreePoolWithTag(*(PVOID *)Pool2, 0x63646641u);
    }
    *(_QWORD *)Pool2 = 0;
    *(_DWORD *)(Pool2 + 8) = 0;
    if ( v11 )
    {
      v29 = (PVOID)ExAllocatePool2(97, v11, 1667524161);
      *(_QWORD *)Pool2 = v29;
    }
    else
    {
      v29 = 0;
    }
    goto LABEL_65;
  }
LABEL_38:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_69:
  if ( v13 )
  {
    if ( (v13->MdlFlags & 2) != 0 )
      MmUnlockPages(v13);
    IoFreeMdl(v13);
  }
  return v14;
}

```

## disassembly

```asm
0x14004f7e0  push    rbx
0x14004f7e2  push    rsi
0x14004f7e3  push    rdi
0x14004f7e4  push    r12
0x14004f7e6  push    r13
0x14004f7e8  push    r14
0x14004f7ea  push    r15
0x14004f7ec  sub     rsp, 190h
0x14004f7f3  mov     rax, cs:__security_cookie
0x14004f7fa  xor     rax, rsp
0x14004f7fd  mov     [rsp+1C8h+var_48], rax
0x14004f805  mov     r12b, r8b
0x14004f808  mov     esi, edx
0x14004f80a  mov     r13, [rsp+1C8h+VirtualAddress]
0x14004f812  mov     r15d, [rsp+1C8h+Length]
0x14004f81a  mov     rax, [rsp+1C8h+arg_38]
0x14004f822  xor     edx, edx
0x14004f824  mov     [rsp+1C8h+var_160], rdx
0x14004f829  mov     [rsp+1C8h+var_158], edx
0x14004f82d  xorps   xmm0, xmm0
0x14004f830  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004f835  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], rdx
0x14004f83a  mov     rdi, [rcx+18h]
0x14004f83e  xor     r14d, r14d
0x14004f841  mov     [rsp+1C8h+var_190], r14
0x14004f846  xor     ebx, ebx
0x14004f848  mov     [rsp+1C8h+var_198], ebx
0x14004f84c  mov     [rax], rdx
0x14004f84f  mov     eax, 5030h
0x14004f854  add     ax, [rdi]
0x14004f857  mov     ecx, 0FFF9h
0x14004f85c  test    cx, ax
0x14004f85f  jz      short loc_14004F86B
0x14004f861  mov     ebx, 0C000000Dh
0x14004f866  jmp     loc_14004FBEB
0x14004f86b  mov     eax, [rsp+1C8h+arg_20]
0x14004f872  test    eax, eax
0x14004f874  jz      short loc_14004F8CE
0x14004f876  mov     r8d, 0Ch; Size
0x14004f87c  cmp     eax, r8d
0x14004f87f  jnb     short loc_14004F893
0x14004f881  mov     ebx, 0C000000Dh
0x14004f886  mov     [rsp+1C8h+var_198], ebx
0x14004f88a  mov     ebx, [rsp+1C8h+var_198]
0x14004f88e  jmp     loc_14004FBEB
0x14004f893  test    r12b, r12b
0x14004f896  jz      short loc_14004F8BF
0x14004f898  test    r9b, 3
0x14004f89c  jz      short loc_14004F8AB
0x14004f89e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004f8a5  nop     dword ptr [rax+rax+00h]
0x14004f8aa  int     3; Trap to Debugger
0x14004f8ab  test    r12b, r12b
0x14004f8ae  jz      short loc_14004F8BF
0x14004f8b0  mov     rdx, r9; Src
0x14004f8b3  lea     rcx, [rsp+1C8h+var_160]; void *
0x14004f8b8  call    RtlCopyFromUser
0x14004f8bd  jmp     short loc_14004F8DB
0x14004f8bf  mov     rdx, r9; Src
0x14004f8c2  lea     rcx, [rsp+1C8h+var_160]; void *
0x14004f8c7  call    RtlCopyVolatileMemory
0x14004f8cc  jmp     short loc_14004F8DB
0x14004f8ce  mov     dword ptr [rsp+1C8h+var_160], 0
0x14004f8d6  mov     byte ptr [rsp+1C8h+var_158], 0
0x14004f8db  test    r15d, r15d
0x14004f8de  jz      loc_14004F9BD
0x14004f8e4  cmp     r15d, 100h
0x14004f8eb  jbe     loc_14004F998
0x14004f8f1  mov     [rsp+1C8h+Irp], 0; Irp
0x14004f8fa  mov     r9b, 1; ChargeQuota
0x14004f8fd  xor     r8d, r8d; SecondaryBuffer
0x14004f900  mov     edx, r15d; Length
0x14004f903  mov     rcx, r13; VirtualAddress
0x14004f906  call    cs:__imp_IoAllocateMdl
0x14004f90d  nop     dword ptr [rax+rax+00h]
0x14004f912  mov     r14, rax
0x14004f915  mov     [rsp+1C8h+var_190], rax
0x14004f91a  test    rax, rax
0x14004f91d  jnz     short loc_14004F930
0x14004f91f  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004f927  mov     ebx, [rsp+1C8h+var_198]
0x14004f92b  jmp     loc_14004FBEB
0x14004f930  xor     r8d, r8d; Operation
0x14004f933  mov     dl, r12b; AccessMode
0x14004f936  mov     rcx, r14; MemoryDescriptorList
0x14004f939  call    cs:__imp_MmProbeAndLockPages
0x14004f940  nop     dword ptr [rax+rax+00h]
0x14004f945  test    byte ptr [r14+0Ah], 5
0x14004f94a  jz      short loc_14004F952
0x14004f94c  mov     r13, [r14+18h]
0x14004f950  jmp     short loc_14004F97D
0x14004f952  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004f95a  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004f962  xor     r9d, r9d; RequestedAddress
0x14004f965  xor     edx, edx; AccessMode
0x14004f967  lea     r8d, [r9+1]; CacheType
0x14004f96b  mov     rcx, r14; MemoryDescriptorList
0x14004f96e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004f975  nop     dword ptr [rax+rax+00h]
0x14004f97a  mov     r13, rax
0x14004f97d  mov     [rsp+1C8h+var_170], r13
0x14004f982  test    r13, r13
0x14004f985  jnz     short loc_14004F9BD
0x14004f987  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004f98f  mov     ebx, [rsp+1C8h+var_198]
0x14004f993  jmp     loc_14004FBEB
0x14004f998  test    r12b, r12b
0x14004f99b  jz      short loc_14004F9BD
0x14004f99d  mov     r8, r15; Size
0x14004f9a0  mov     rdx, r13; Src
0x14004f9a3  lea     rcx, [rsp+1C8h+var_148]; void *
0x14004f9ab  call    RtlCopyFromUser
0x14004f9b0  lea     r13, [rsp+1C8h+var_148]
0x14004f9b8  mov     [rsp+1C8h+var_170], r13
0x14004f9bd  lea     rcx, [rdi+38h]; SpinLock
0x14004f9c1  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004f9c6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004f9cd  nop     dword ptr [rax+rax+00h]
0x14004f9d2  cmp     dword ptr [rdi+170h], 0
0x14004f9d9  jnz     loc_14004FBCC
0x14004f9df  mov     edx, [rdi+8]
0x14004f9e2  mov     eax, edx
0x14004f9e4  shr     eax, 10h
0x14004f9e7  test    al, 2
0x14004f9e9  setz    cl
0x14004f9ec  bt      edx, 10h
0x14004f9f0  setnb   al
0x14004f9f3  test    al, cl
0x14004f9f5  jz      loc_14004FBCC
0x14004f9fb  movzx   eax, word ptr [rdi]
0x14004f9fe  cmp     [rsp+1C8h+arg_20], 0
0x14004fa06  jbe     short loc_14004FA37
0x14004fa08  mov     ecx, 0AFD4h
0x14004fa0d  and     ax, cx
0x14004fa10  cmp     ax, cx
0x14004fa13  jnz     short loc_14004FA23
0x14004fa15  mov     edx, dword ptr [rsp+1C8h+var_160]
0x14004fa19  mov     rcx, rdi
0x14004fa1c  call    AfdFindReturnedConnection
0x14004fa21  jmp     short loc_14004FA25
0x14004fa23  xor     eax, eax
0x14004fa25  test    rax, rax
0x14004fa28  jz      loc_14004FBCC
0x14004fa2e  lea     r12, [rax+0E0h]
0x14004fa35  jmp     short loc_14004FA65
0x14004fa37  mov     ecx, 0AFD2h
0x14004fa3c  and     ax, cx
0x14004fa3f  cmp     ax, cx
0x14004fa42  jnz     short loc_14004FA4D
0x14004fa44  mov     r12, [rdi+0C0h]
0x14004fa4b  jmp     short loc_14004FA50
0x14004fa4d  xor     r12d, r12d
0x14004fa50  test    r12, r12
0x14004fa53  jz      short loc_14004FA5E
0x14004fa55  add     r12, 0E0h
0x14004fa5c  jmp     short loc_14004FA65
0x14004fa5e  lea     r12, [rdi+0D0h]
0x14004fa65  mov     eax, [rdi+8]
0x14004fa68  bt      eax, 8
0x14004fa6c  jnb     short loc_14004FA84
0x14004fa6e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fa73  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fa7a  nop     dword ptr [rax+rax+00h]
0x14004fa7f  jmp     loc_14004FBEB
0x14004fa84  mov     rdi, [r12]
0x14004fa88  test    rdi, rdi
0x14004fa8b  jnz     short loc_14004FAD2
0x14004fa8d  mov     edx, 0E8h
0x14004fa92  lea     ecx, [rdi+61h]
0x14004fa95  mov     r8d, 63646641h
0x14004fa9b  call    cs:__imp_ExAllocatePool2
0x14004faa2  nop     dword ptr [rax+rax+00h]
0x14004faa7  mov     rdi, rax
0x14004faaa  mov     [rsp+1C8h+var_168], rax
0x14004faaf  mov     [r12], rax
0x14004fab3  jmp     short loc_14004FAD2
0x14004fab5  mov     ebx, eax
0x14004fab7  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fabc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fac3  nop     dword ptr [rax+rax+00h]
0x14004fac8  mov     r14, [rsp+1C8h+var_190]
0x14004facd  jmp     loc_14004FBEB
0x14004fad2  xor     r12b, r12b
0x14004fad5  sub     esi, 1204Bh
0x14004fadb  jz      short loc_14004FB3B
0x14004fadd  mov     eax, 4
0x14004fae2  sub     esi, eax
0x14004fae4  jz      short loc_14004FB37
0x14004fae6  sub     esi, eax
0x14004fae8  jz      short loc_14004FB31
0x14004faea  sub     esi, eax
0x14004faec  jz      short loc_14004FB2B
0x14004faee  sub     esi, 14h
0x14004faf1  jz      short loc_14004FB15
0x14004faf3  sub     esi, eax
0x14004faf5  jz      short loc_14004FB0F
0x14004faf7  sub     esi, eax
0x14004faf9  jz      short loc_14004FB09
0x14004fafb  cmp     esi, eax
0x14004fafd  jnz     loc_14004FBCC
0x14004fb03  add     rdi, 70h ; 'p'
0x14004fb07  jmp     short loc_14004FB19
0x14004fb09  add     rdi, 60h ; '`'
0x14004fb0d  jmp     short loc_14004FB19
0x14004fb0f  add     rdi, 30h ; '0'
0x14004fb13  jmp     short loc_14004FB19
0x14004fb15  add     rdi, 20h ; ' '
0x14004fb19  mov     r12b, 1
0x14004fb1c  cmp     r15d, eax
0x14004fb1f  jb      loc_14004FBCC
0x14004fb25  mov     r15d, [r13+0]
0x14004fb29  jmp     short loc_14004FB3B
0x14004fb2b  add     rdi, 50h ; 'P'
0x14004fb2f  jmp     short loc_14004FB3B
0x14004fb31  add     rdi, 40h ; '@'
0x14004fb35  jmp     short loc_14004FB3B
0x14004fb37  add     rdi, 10h
0x14004fb3b  mov     rax, [rdi]
0x14004fb3e  test    rax, rax
0x14004fb41  jz      short loc_14004FB62
0x14004fb43  cmp     [rdi+8], r15d
0x14004fb47  jnb     short loc_14004FBB0
0x14004fb49  test    rax, rax
0x14004fb4c  jz      short loc_14004FB62
0x14004fb4e  mov     edx, 63646641h; Tag
0x14004fb53  mov     rcx, rax; P
0x14004fb56  call    cs:__imp_ExFreePoolWithTag
0x14004fb5d  nop     dword ptr [rax+rax+00h]
0x14004fb62  mov     qword ptr [rdi], 0
0x14004fb69  mov     dword ptr [rdi+8], 0
0x14004fb70  test    r15d, r15d
0x14004fb73  jz      short loc_14004FBAE
0x14004fb75  mov     edx, r15d
0x14004fb78  mov     ecx, 61h ; 'a'
0x14004fb7d  mov     r8d, 63646641h
0x14004fb83  call    cs:__imp_ExAllocatePool2
0x14004fb8a  nop     dword ptr [rax+rax+00h]
0x14004fb8f  mov     [rdi], rax
0x14004fb92  jmp     short loc_14004FBB0
0x14004fb94  mov     ebx, eax
0x14004fb96  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fb9b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fba2  nop     dword ptr [rax+rax+00h]
0x14004fba7  mov     r14, [rsp+1C8h+var_190]
0x14004fbac  jmp     short loc_14004FBEB
0x14004fbae  xor     eax, eax
0x14004fbb0  test    r12b, r12b
0x14004fbb3  jnz     short loc_14004FBC3
0x14004fbb5  mov     r8d, r15d; Size
0x14004fbb8  mov     rdx, r13; Src
0x14004fbbb  mov     rcx, rax; void *
0x14004fbbe  call    RtlCopyVolatileMemory
0x14004fbc3  mov     [rdi+8], r15d
0x14004fbc7  jmp     loc_14004FA6E
0x14004fbcc  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fbd1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fbd8  nop     dword ptr [rax+rax+00h]
0x14004fbdd  jmp     loc_14004F861
0x14004fbe2  mov     r14, [rsp+1C8h+var_190]
0x14004fbe7  mov     ebx, [rsp+1C8h+var_198]
0x14004fbeb  test    r14, r14
0x14004fbee  jz      short loc_14004FC15
0x14004fbf0  test    byte ptr [r14+0Ah], 2
0x14004fbf5  jz      short loc_14004FC06
0x14004fbf7  mov     rcx, r14; MemoryDescriptorList
0x14004fbfa  call    cs:__imp_MmUnlockPages
0x14004fc01  nop     dword ptr [rax+rax+00h]
0x14004fc06  mov     rcx, r14; Mdl
0x14004fc09  call    cs:__imp_IoFreeMdl
0x14004fc10  nop     dword ptr [rax+rax+00h]
0x14004fc15  mov     eax, ebx
0x14004fc17  mov     rcx, [rsp+1C8h+var_48]
0x14004fc1f  xor     rcx, rsp; StackCookie
0x14004fc22  call    __security_check_cookie
0x14004fc27  add     rsp, 190h
0x14004fc2e  pop     r15
0x14004fc30  pop     r14
0x14004fc32  pop     r13
0x14004fc34  pop     r12
0x14004fc36  pop     rdi
0x14004fc37  pop     rsi
0x14004fc38  pop     rbx
0x14004fc39  retn
0x1400740e6  push    rbp
0x1400740e8  sub     rsp, 30h
0x1400740ec  mov     rbp, rdx
0x1400740ef  mov     r8, rcx
0x1400740f2  lea     r9, [rbp+30h]
0x1400740f6  mov     edx, 1162h
0x1400740fb  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074102  call    AfdExceptionFilter
0x140074107  nop
0x140074108  add     rsp, 30h
0x14007410c  pop     rbp
0x14007410d  retn
```
