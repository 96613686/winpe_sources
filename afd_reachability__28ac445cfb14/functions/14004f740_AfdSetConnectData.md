# AfdSetConnectData

- ea: `0x14004f740`
- end: `0x14004fb9b`
- name: `AfdSetConnectData`
- size: `1115`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14002fd5c`
- `0x1400445b8`
- `0x1400477a8`
- `0x14004f740`
- `0x1400726a0`
- `0x1400726d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004f8ce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004f8ce`
- `ntoskrnl!IoFreeMdl` at `0x14004fb69`
- `ntoskrnl!IoFreeMdl` at `0x14004fb69`
- `ntoskrnl!MmUnlockPages` at `0x14004fb5a`
- `ntoskrnl!MmUnlockPages` at `0x14004fb5a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004f899`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004f899`
- `ntoskrnl!IoAllocateMdl` at `0x14004f866`
- `ntoskrnl!IoAllocateMdl` at `0x14004f866`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004f7fe`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004f7fe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004f9d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fa1c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fafb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fb31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004f9d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fa1c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fafb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fb31`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004f926`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004f926`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fab6`
- `ntoskrnl!ExAllocatePool2` at `0x14004f9fb`
- `ntoskrnl!ExAllocatePool2` at `0x14004fae3`
- `ntoskrnl!ExAllocatePool2` at `0x14004f9fb`
- `ntoskrnl!ExAllocatePool2` at `0x14004fae3`

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
0x14004f740  push    rbx
0x14004f742  push    rsi
0x14004f743  push    rdi
0x14004f744  push    r12
0x14004f746  push    r13
0x14004f748  push    r14
0x14004f74a  push    r15
0x14004f74c  sub     rsp, 190h
0x14004f753  mov     rax, cs:__security_cookie
0x14004f75a  xor     rax, rsp
0x14004f75d  mov     [rsp+1C8h+var_48], rax
0x14004f765  mov     r12b, r8b
0x14004f768  mov     esi, edx
0x14004f76a  mov     r13, [rsp+1C8h+VirtualAddress]
0x14004f772  mov     r15d, [rsp+1C8h+Length]
0x14004f77a  mov     rax, [rsp+1C8h+arg_38]
0x14004f782  xor     edx, edx
0x14004f784  mov     [rsp+1C8h+var_160], rdx
0x14004f789  mov     [rsp+1C8h+var_158], edx
0x14004f78d  xorps   xmm0, xmm0
0x14004f790  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004f795  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], rdx
0x14004f79a  mov     rdi, [rcx+18h]
0x14004f79e  xor     r14d, r14d
0x14004f7a1  mov     [rsp+1C8h+var_190], r14
0x14004f7a6  xor     ebx, ebx
0x14004f7a8  mov     [rsp+1C8h+var_198], ebx
0x14004f7ac  mov     [rax], rdx
0x14004f7af  mov     eax, 5030h
0x14004f7b4  add     ax, [rdi]
0x14004f7b7  mov     ecx, 0FFF9h
0x14004f7bc  test    cx, ax
0x14004f7bf  jz      short loc_14004F7CB
0x14004f7c1  mov     ebx, 0C000000Dh
0x14004f7c6  jmp     loc_14004FB4B
0x14004f7cb  mov     eax, [rsp+1C8h+arg_20]
0x14004f7d2  test    eax, eax
0x14004f7d4  jz      short loc_14004F82E
0x14004f7d6  mov     r8d, 0Ch; Size
0x14004f7dc  cmp     eax, r8d
0x14004f7df  jnb     short loc_14004F7F3
0x14004f7e1  mov     ebx, 0C000000Dh
0x14004f7e6  mov     [rsp+1C8h+var_198], ebx
0x14004f7ea  mov     ebx, [rsp+1C8h+var_198]
0x14004f7ee  jmp     loc_14004FB4B
0x14004f7f3  test    r12b, r12b
0x14004f7f6  jz      short loc_14004F81F
0x14004f7f8  test    r9b, 3
0x14004f7fc  jz      short loc_14004F80B
0x14004f7fe  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004f805  nop     dword ptr [rax+rax+00h]
0x14004f80a  int     3; Trap to Debugger
0x14004f80b  test    r12b, r12b
0x14004f80e  jz      short loc_14004F81F
0x14004f810  mov     rdx, r9; Src
0x14004f813  lea     rcx, [rsp+1C8h+var_160]; void *
0x14004f818  call    RtlCopyFromUser
0x14004f81d  jmp     short loc_14004F83B
0x14004f81f  mov     rdx, r9; Src
0x14004f822  lea     rcx, [rsp+1C8h+var_160]; void *
0x14004f827  call    RtlCopyVolatileMemory
0x14004f82c  jmp     short loc_14004F83B
0x14004f82e  mov     dword ptr [rsp+1C8h+var_160], 0
0x14004f836  mov     byte ptr [rsp+1C8h+var_158], 0
0x14004f83b  test    r15d, r15d
0x14004f83e  jz      loc_14004F91D
0x14004f844  cmp     r15d, 100h
0x14004f84b  jbe     loc_14004F8F8
0x14004f851  mov     [rsp+1C8h+Irp], 0; Irp
0x14004f85a  mov     r9b, 1; ChargeQuota
0x14004f85d  xor     r8d, r8d; SecondaryBuffer
0x14004f860  mov     edx, r15d; Length
0x14004f863  mov     rcx, r13; VirtualAddress
0x14004f866  call    cs:__imp_IoAllocateMdl
0x14004f86d  nop     dword ptr [rax+rax+00h]
0x14004f872  mov     r14, rax
0x14004f875  mov     [rsp+1C8h+var_190], rax
0x14004f87a  test    rax, rax
0x14004f87d  jnz     short loc_14004F890
0x14004f87f  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004f887  mov     ebx, [rsp+1C8h+var_198]
0x14004f88b  jmp     loc_14004FB4B
0x14004f890  xor     r8d, r8d; Operation
0x14004f893  mov     dl, r12b; AccessMode
0x14004f896  mov     rcx, r14; MemoryDescriptorList
0x14004f899  call    cs:__imp_MmProbeAndLockPages
0x14004f8a0  nop     dword ptr [rax+rax+00h]
0x14004f8a5  test    byte ptr [r14+0Ah], 5
0x14004f8aa  jz      short loc_14004F8B2
0x14004f8ac  mov     r13, [r14+18h]
0x14004f8b0  jmp     short loc_14004F8DD
0x14004f8b2  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004f8ba  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004f8c2  xor     r9d, r9d; RequestedAddress
0x14004f8c5  xor     edx, edx; AccessMode
0x14004f8c7  lea     r8d, [r9+1]; CacheType
0x14004f8cb  mov     rcx, r14; MemoryDescriptorList
0x14004f8ce  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004f8d5  nop     dword ptr [rax+rax+00h]
0x14004f8da  mov     r13, rax
0x14004f8dd  mov     [rsp+1C8h+var_170], r13
0x14004f8e2  test    r13, r13
0x14004f8e5  jnz     short loc_14004F91D
0x14004f8e7  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004f8ef  mov     ebx, [rsp+1C8h+var_198]
0x14004f8f3  jmp     loc_14004FB4B
0x14004f8f8  test    r12b, r12b
0x14004f8fb  jz      short loc_14004F91D
0x14004f8fd  mov     r8, r15; Size
0x14004f900  mov     rdx, r13; Src
0x14004f903  lea     rcx, [rsp+1C8h+var_148]; void *
0x14004f90b  call    RtlCopyFromUser
0x14004f910  lea     r13, [rsp+1C8h+var_148]
0x14004f918  mov     [rsp+1C8h+var_170], r13
0x14004f91d  lea     rcx, [rdi+38h]; SpinLock
0x14004f921  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004f926  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004f92d  nop     dword ptr [rax+rax+00h]
0x14004f932  cmp     dword ptr [rdi+170h], 0
0x14004f939  jnz     loc_14004FB2C
0x14004f93f  mov     edx, [rdi+8]
0x14004f942  mov     eax, edx
0x14004f944  shr     eax, 10h
0x14004f947  test    al, 2
0x14004f949  setz    cl
0x14004f94c  bt      edx, 10h
0x14004f950  setnb   al
0x14004f953  test    al, cl
0x14004f955  jz      loc_14004FB2C
0x14004f95b  movzx   eax, word ptr [rdi]
0x14004f95e  cmp     [rsp+1C8h+arg_20], 0
0x14004f966  jbe     short loc_14004F997
0x14004f968  mov     ecx, 0AFD4h
0x14004f96d  and     ax, cx
0x14004f970  cmp     ax, cx
0x14004f973  jnz     short loc_14004F983
0x14004f975  mov     edx, dword ptr [rsp+1C8h+var_160]
0x14004f979  mov     rcx, rdi
0x14004f97c  call    AfdFindReturnedConnection
0x14004f981  jmp     short loc_14004F985
0x14004f983  xor     eax, eax
0x14004f985  test    rax, rax
0x14004f988  jz      loc_14004FB2C
0x14004f98e  lea     r12, [rax+0E0h]
0x14004f995  jmp     short loc_14004F9C5
0x14004f997  mov     ecx, 0AFD2h
0x14004f99c  and     ax, cx
0x14004f99f  cmp     ax, cx
0x14004f9a2  jnz     short loc_14004F9AD
0x14004f9a4  mov     r12, [rdi+0C0h]
0x14004f9ab  jmp     short loc_14004F9B0
0x14004f9ad  xor     r12d, r12d
0x14004f9b0  test    r12, r12
0x14004f9b3  jz      short loc_14004F9BE
0x14004f9b5  add     r12, 0E0h
0x14004f9bc  jmp     short loc_14004F9C5
0x14004f9be  lea     r12, [rdi+0D0h]
0x14004f9c5  mov     eax, [rdi+8]
0x14004f9c8  bt      eax, 8
0x14004f9cc  jnb     short loc_14004F9E4
0x14004f9ce  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004f9d3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004f9da  nop     dword ptr [rax+rax+00h]
0x14004f9df  jmp     loc_14004FB4B
0x14004f9e4  mov     rdi, [r12]
0x14004f9e8  test    rdi, rdi
0x14004f9eb  jnz     short loc_14004FA32
0x14004f9ed  mov     edx, 0E8h
0x14004f9f2  lea     ecx, [rdi+61h]
0x14004f9f5  mov     r8d, 63646641h
0x14004f9fb  call    cs:__imp_ExAllocatePool2
0x14004fa02  nop     dword ptr [rax+rax+00h]
0x14004fa07  mov     rdi, rax
0x14004fa0a  mov     [rsp+1C8h+var_168], rax
0x14004fa0f  mov     [r12], rax
0x14004fa13  jmp     short loc_14004FA32
0x14004fa15  mov     ebx, eax
0x14004fa17  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fa1c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fa23  nop     dword ptr [rax+rax+00h]
0x14004fa28  mov     r14, [rsp+1C8h+var_190]
0x14004fa2d  jmp     loc_14004FB4B
0x14004fa32  xor     r12b, r12b
0x14004fa35  sub     esi, 1204Bh
0x14004fa3b  jz      short loc_14004FA9B
0x14004fa3d  mov     eax, 4
0x14004fa42  sub     esi, eax
0x14004fa44  jz      short loc_14004FA97
0x14004fa46  sub     esi, eax
0x14004fa48  jz      short loc_14004FA91
0x14004fa4a  sub     esi, eax
0x14004fa4c  jz      short loc_14004FA8B
0x14004fa4e  sub     esi, 14h
0x14004fa51  jz      short loc_14004FA75
0x14004fa53  sub     esi, eax
0x14004fa55  jz      short loc_14004FA6F
0x14004fa57  sub     esi, eax
0x14004fa59  jz      short loc_14004FA69
0x14004fa5b  cmp     esi, eax
0x14004fa5d  jnz     loc_14004FB2C
0x14004fa63  add     rdi, 70h ; 'p'
0x14004fa67  jmp     short loc_14004FA79
0x14004fa69  add     rdi, 60h ; '`'
0x14004fa6d  jmp     short loc_14004FA79
0x14004fa6f  add     rdi, 30h ; '0'
0x14004fa73  jmp     short loc_14004FA79
0x14004fa75  add     rdi, 20h ; ' '
0x14004fa79  mov     r12b, 1
0x14004fa7c  cmp     r15d, eax
0x14004fa7f  jb      loc_14004FB2C
0x14004fa85  mov     r15d, [r13+0]
0x14004fa89  jmp     short loc_14004FA9B
0x14004fa8b  add     rdi, 50h ; 'P'
0x14004fa8f  jmp     short loc_14004FA9B
0x14004fa91  add     rdi, 40h ; '@'
0x14004fa95  jmp     short loc_14004FA9B
0x14004fa97  add     rdi, 10h
0x14004fa9b  mov     rax, [rdi]
0x14004fa9e  test    rax, rax
0x14004faa1  jz      short loc_14004FAC2
0x14004faa3  cmp     [rdi+8], r15d
0x14004faa7  jnb     short loc_14004FB10
0x14004faa9  test    rax, rax
0x14004faac  jz      short loc_14004FAC2
0x14004faae  mov     edx, 63646641h; Tag
0x14004fab3  mov     rcx, rax; P
0x14004fab6  call    cs:__imp_ExFreePoolWithTag
0x14004fabd  nop     dword ptr [rax+rax+00h]
0x14004fac2  mov     qword ptr [rdi], 0
0x14004fac9  mov     dword ptr [rdi+8], 0
0x14004fad0  test    r15d, r15d
0x14004fad3  jz      short loc_14004FB0E
0x14004fad5  mov     edx, r15d
0x14004fad8  mov     ecx, 61h ; 'a'
0x14004fadd  mov     r8d, 63646641h
0x14004fae3  call    cs:__imp_ExAllocatePool2
0x14004faea  nop     dword ptr [rax+rax+00h]
0x14004faef  mov     [rdi], rax
0x14004faf2  jmp     short loc_14004FB10
0x14004faf4  mov     ebx, eax
0x14004faf6  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fafb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fb02  nop     dword ptr [rax+rax+00h]
0x14004fb07  mov     r14, [rsp+1C8h+var_190]
0x14004fb0c  jmp     short loc_14004FB4B
0x14004fb0e  xor     eax, eax
0x14004fb10  test    r12b, r12b
0x14004fb13  jnz     short loc_14004FB23
0x14004fb15  mov     r8d, r15d; Size
0x14004fb18  mov     rdx, r13; Src
0x14004fb1b  mov     rcx, rax; void *
0x14004fb1e  call    RtlCopyVolatileMemory
0x14004fb23  mov     [rdi+8], r15d
0x14004fb27  jmp     loc_14004F9CE
0x14004fb2c  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004fb31  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fb38  nop     dword ptr [rax+rax+00h]
0x14004fb3d  jmp     loc_14004F7C1
0x14004fb42  mov     r14, [rsp+1C8h+var_190]
0x14004fb47  mov     ebx, [rsp+1C8h+var_198]
0x14004fb4b  test    r14, r14
0x14004fb4e  jz      short loc_14004FB75
0x14004fb50  test    byte ptr [r14+0Ah], 2
0x14004fb55  jz      short loc_14004FB66
0x14004fb57  mov     rcx, r14; MemoryDescriptorList
0x14004fb5a  call    cs:__imp_MmUnlockPages
0x14004fb61  nop     dword ptr [rax+rax+00h]
0x14004fb66  mov     rcx, r14; Mdl
0x14004fb69  call    cs:__imp_IoFreeMdl
0x14004fb70  nop     dword ptr [rax+rax+00h]
0x14004fb75  mov     eax, ebx
0x14004fb77  mov     rcx, [rsp+1C8h+var_48]
0x14004fb7f  xor     rcx, rsp; StackCookie
0x14004fb82  call    __security_check_cookie
0x14004fb87  add     rsp, 190h
0x14004fb8e  pop     r15
0x14004fb90  pop     r14
0x14004fb92  pop     r13
0x14004fb94  pop     r12
0x14004fb96  pop     rdi
0x14004fb97  pop     rsi
0x14004fb98  pop     rbx
0x14004fb99  retn
0x140073f66  push    rbp
0x140073f68  sub     rsp, 30h
0x140073f6c  mov     rbp, rdx
0x140073f6f  mov     r8, rcx
0x140073f72  lea     r9, [rbp+30h]
0x140073f76  mov     edx, 1162h
0x140073f7b  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073f82  call    AfdExceptionFilter
0x140073f87  nop
0x140073f88  add     rsp, 30h
0x140073f8c  pop     rbp
0x140073f8d  retn
```
