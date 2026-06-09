# WskTdiTLRequestIoControlEndpoint

- ea: `0x140064d50`
- end: `0x140065582`
- name: `WskTdiTLRequestIoControlEndpoint`
- size: `2098`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003670`
- `0x140005b60`
- `0x140015990`
- `0x1400309d0`
- `0x1400643a8`
- `0x140064d50`
- `0x140065f30`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140065188`
- `ntoskrnl!IoFreeIrp` at `0x1400651c1`
- `ntoskrnl!IoFreeIrp` at `0x140065188`
- `ntoskrnl!IoFreeIrp` at `0x1400651c1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400652da`
- `ntoskrnl!KeGetCurrentIrql` at `0x140065351`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400652da`
- `ntoskrnl!KeGetCurrentIrql` at `0x140065351`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400651f6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400651f6`
- `ntoskrnl!IoAllocateIrp` at `0x140065156`
- `ntoskrnl!IoAllocateIrp` at `0x140065156`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065171`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400653f7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065171`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400653f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400651d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140065558`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400651d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140065558`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14006538c`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14006538c`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140065374`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140065374`
- `ntoskrnl!IoAllocateMdl` at `0x1400651aa`
- `ntoskrnl!IoAllocateMdl` at `0x1400651aa`
- `ntoskrnl!IofCompleteRequest` at `0x1400650de`
- `ntoskrnl!IofCompleteRequest` at `0x1400650de`
- `ntoskrnl!IofCallDriver` at `0x14006526d`
- `ntoskrnl!IofCallDriver` at `0x14006526d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064ee9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064f50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064fae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065055`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400654f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064ee9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064f50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064fae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065055`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400654f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064f2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064ff0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006507a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065530`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064f2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064ff0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006507a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065530`
- `NETIO!NetioInsertWorkQueue` at `0x14006530d`
- `NETIO!NetioInsertWorkQueue` at `0x14006530d`

## pseudocode

```c
__int64 __fastcall WskTdiTLRequestIoControlEndpoint(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  int v5; // r8d
  unsigned int v6; // edi
  unsigned __int8 v7; // r14
  __int64 v8; // rbx
  int *v9; // rbx
  unsigned __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  KIRQL v13; // r8
  int v14; // edx
  unsigned int v15; // ecx
  int v16; // eax
  KIRQL v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rbx
  KIRQL v20; // al
  volatile signed __int32 *v21; // rsi
  volatile signed __int32 *v22; // rdx
  unsigned __int8 v23; // bp
  IRP *v24; // rbx
  __int64 v25; // r14
  PIRP Irp; // r15
  char *v27; // rax
  void *v28; // r13
  struct _MDL *Mdl; // rax
  struct _MDL *v30; // r12
  struct _IO_STACK_LOCATION *v31; // rax
  struct _IO_STACK_LOCATION *v32; // rcx
  size_t v33; // rdx
  void *PoolPriority; // rax
  void *v35; // rbx
  __int64 *v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rcx
  char *v40; // rax
  char *v41; // r15
  __int64 v42; // r14
  __int64 v43; // rcx
  bool v44; // zf
  __int16 v45; // ax
  int v46; // eax
  char *v47; // rbx
  UCHAR v48; // r14
  UCHAR v49; // al
  KIRQL v50; // al
  int v51; // r9d
  volatile signed __int32 *v52; // rbp
  unsigned int v53; // r8d
  int v54; // r9d
  _WORD Src[2]; // [rsp+30h] [rbp-58h] BYREF
  int v56; // [rsp+34h] [rbp-54h]
  __int64 v57; // [rsp+38h] [rbp-50h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+90h] [rbp+8h]

  *(_QWORD *)(a2 + 64) = 0;
  *(_QWORD *)(a2 + 72) = 0;
  v4 = *(_QWORD *)(a1 + 280);
  if ( !v4 )
  {
    v4 = *(_QWORD *)(a2 + 8);
    if ( *(void (**)())a2 != AfdTLDontCareIOCompletion )
    {
      if ( *(__int64 (__fastcall **)())a2 == AfdSynchronousTlIORequestComplete )
        v4 = *(_QWORD *)(v4 + 16);
      else
        v4 = *(_QWORD *)(*(_QWORD *)(v4 + 184) + 8LL);
    }
    *(_QWORD *)(a1 + 280) = v4;
  }
  v5 = *(_DWORD *)(a2 + 16);
  if ( !v5 )
  {
    v18 = *(_DWORD *)(a2 + 24);
    v19 = 32;
    if ( v18 > 0x20 )
    {
      if ( v18 != 40 )
      {
        if ( v18 == 44 || v18 == 48 )
          return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
        if ( v18 == 52 )
          return 0;
        return (unsigned int)-1073741811;
      }
      goto LABEL_61;
    }
    switch ( v18 )
    {
      case 0x20u:
        v23 = 0;
        v19 = 48;
        goto LABEL_92;
      case 8u:
        v33 = *(_QWORD *)(a2 + 40);
        if ( (unsigned int)v33 > (unsigned int)AfdStandardAddressLength )
          PoolPriority = (void *)AfdAllocatePoolPriority(64, v33, 1382311489, 0);
        else
          PoolPriority = AfdAllocateZeroedFromLookasideList(v4, v33);
        v35 = PoolPriority;
        if ( !PoolPriority )
          return (unsigned int)-1073741670;
        memmove(PoolPriority, *(const void **)(a2 + 32), *(_QWORD *)(a2 + 40));
        *(_QWORD *)(a1 + 48) = v35;
        *(_QWORD *)(a1 + 304) = *(_QWORD *)(a2 + 8);
        *(_QWORD *)(a1 + 312) = *(_QWORD *)a2;
        if ( KeGetCurrentIrql() )
        {
          NetioInsertWorkQueue(WskTdiWQEndpointBind, a1 + 296);
        }
        else
        {
          *(_QWORD *)(a1 + 296) = 0;
          WskTdiWQRoutineEndpointBind(a1 + 296);
        }
        break;
      case 0x10u:
        v24 = *(IRP **)(a2 + 8);
        if ( (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
        {
          memmove(*(void **)(a2 + 48), *(const void **)(a1 + 48), *(_QWORD *)(a2 + 56));
          v6 = 0;
LABEL_81:
          v24->IoStatus.Status = v6;
          goto LABEL_67;
        }
        CurrentStackLocation = v24->Tail.Overlay.CurrentStackLocation;
        if ( *(_WORD *)a1 == 0xACD2 )
        {
          v25 = 144;
          if ( *(_BYTE *)(v4 + 2) != 2 )
            v25 = 56;
        }
        else
        {
          v25 = 56;
        }
        Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v25 + a1 + 16) + 76LL), 0);
        if ( !Irp )
        {
LABEL_80:
          v6 = -1073741670;
          goto LABEL_81;
        }
        v27 = (char *)ExAllocateFromNPagedLookasideList(&stru_1400877C0);
        v28 = v27;
        if ( !v27 )
        {
          IoFreeIrp(Irp);
          goto LABEL_80;
        }
        Mdl = IoAllocateMdl(v27 + 8, 0x8Au, 0, 0, 0);
        v30 = Mdl;
        if ( !Mdl )
        {
          IoFreeIrp(Irp);
          ExFreeToNPagedLookasideList(&stru_1400877C0, v28);
          goto LABEL_80;
        }
        MmBuildMdlForNonPagedPool(Mdl);
        v31 = Irp->Tail.Overlay.CurrentStackLocation;
        Irp->MdlAddress = v30;
        v31[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)WskTdiCOMPAddressQuery;
        v31[-1].Context = v24;
        v31[-1].Control = -32;
        v32 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v32[-1].MajorFunction = 3087;
        v32[-1].DeviceObject = *(PDEVICE_OBJECT *)(v25 + a1 + 16);
        v32[-1].FileObject = *(PFILE_OBJECT *)(v25 + a1 + 8);
        v32[-1].Parameters.Read.Length = 3;
        v32[-1].Parameters.QueryDirectory.FileName = 0;
        CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v28;
        v24->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        IofCallDriver(*(PDEVICE_OBJECT *)(v25 + a1 + 16), Irp);
        break;
      case 0x14u:
        v24 = *(IRP **)(a2 + 8);
        memmove(*(void **)(a2 + 48), *(const void **)(a1 + 200), *(_QWORD *)(a2 + 56));
        v24->IoStatus.Status = 0;
        v6 = 0;
LABEL_67:
        v24->IoStatus.Information = *(_QWORD *)(a2 + 56);
        IofCompleteRequest(v24, 2);
        return v6;
      case 0x18u:
        v23 = 1;
LABEL_92:
        if ( *(_QWORD *)(a2 + 16 * (v23 ^ 1LL) + 40) < 8u )
          return (unsigned int)-1073741306;
        if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
          return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
        v36 = *(__int64 **)(v19 + a2);
        if ( KeGetCurrentIrql() )
          return (unsigned int)-1073741637;
        if ( v23 )
        {
          v37 = *(_QWORD *)(a1 + 40);
          if ( v37 )
            ObDereferenceSecurityDescriptor(v37, 1);
          v38 = *v36;
          *(_QWORD *)(a1 + 40) = *v36;
          ObReferenceSecurityDescriptor(v38, 1);
        }
        else
        {
          *v36 = *(_QWORD *)(a1 + 40);
          *(_QWORD *)(a2 + 72) = 8;
        }
        return 0;
      case 0x1Cu:
LABEL_61:
        if ( !*(_QWORD *)(a2 + 40) )
        {
          v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          v21 = *(volatile signed __int32 **)(a1 + 144);
          *(_DWORD *)(a1 + 16) &= ~0x10000u;
          *(_QWORD *)(a1 + 144) = 0;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v20);
          if ( !v21 || _InterlockedExchangeAdd(v21, 0xFFFFFFFF) != 1 )
            return 0;
          v22 = v21;
          goto LABEL_119;
        }
        v40 = (char *)ExAllocateFromNPagedLookasideList(&stru_1400877C0);
        v41 = v40;
        if ( v40 )
        {
          v42 = *(_QWORD *)(a2 + 32);
          memset(v40 + 4, 0, 0xC4u);
          *(_DWORD *)v41 = 1;
          if ( (*(_DWORD *)(a1 + 16) & 0x20) != 0 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v42 + 8)) )
          {
            v44 = *(_WORD *)v42 == 23;
            v45 = *(_WORD *)(v42 + 2);
            Src[0] = 2;
            Src[1] = v45;
            v57 = 0;
            if ( !v44 )
              v43 = v42 + 4;
            v46 = *(_DWORD *)(v43 + 12);
            v47 = v41 + 56;
            *((_DWORD *)v41 + 14) = 1;
            v56 = v46;
            v48 = SOCKADDR_SIZE(2u);
            *((_WORD *)v41 + 30) = v48 - 2;
            memmove(v41 + 62, Src, v48);
          }
          else
          {
            v47 = v41 + 56;
            *((_DWORD *)v41 + 14) = 1;
            *((_WORD *)v41 + 30) = SOCKADDR_SIZE(*(_WORD *)v42) - 2;
            v49 = SOCKADDR_SIZE(*(_WORD *)v42);
            memmove(v41 + 62, (const void *)v42, v49);
            v48 = SOCKADDR_SIZE(*(_WORD *)v42);
          }
          *((_DWORD *)v41 + 10) = v48 + 6;
          *((_QWORD *)v41 + 6) = v47;
          v50 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          v51 = *(_DWORD *)(a1 + 16);
          v52 = *(volatile signed __int32 **)(a1 + 144);
          v53 = v51 & 0xFFFEFFFF;
          *(_QWORD *)(a1 + 144) = v41;
          v54 = v51 | 0x10000;
          if ( *(_DWORD *)(a2 + 24) != 40 )
            v54 = v53;
          *(_DWORD *)(a1 + 16) = v54;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v50);
          if ( !v52 || _InterlockedExchangeAdd(v52, 0xFFFFFFFF) != 1 )
            return 0;
          v22 = v52;
LABEL_119:
          ExFreeToNPagedLookasideList(&stru_1400877C0, (PVOID)v22);
          return 0;
        }
        return (unsigned int)-1073741670;
      default:
        return (unsigned int)-1073741811;
    }
    return 259;
  }
  if ( v5 == 1 || v5 == 2 )
  {
    if ( v5 == 1 )
    {
      v7 = 1;
      v8 = 32;
    }
    else
    {
      v7 = 0;
      v8 = 48;
    }
    v9 = *(int **)(v8 + a2);
    v10 = *(_QWORD *)(a2 + 16 * (v7 ^ 1LL) + 40);
    v11 = *(_DWORD *)(a2 + 20);
    if ( v11 != 0xFFFF )
    {
      if ( v11 != 41 || *(_DWORD *)(a2 + 24) != 27 )
        return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
      if ( v10 >= 4 )
      {
        if ( !v9 )
          return (unsigned int)-1073741811;
        v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v7 )
        {
          v14 = *v9 == 0 ? 8 : 0;
          v15 = *(_DWORD *)(a1 + 16) & 0xFFFFFFF7;
          goto LABEL_49;
        }
        v16 = *(_DWORD *)(a1 + 16) >> 3;
        goto LABEL_51;
      }
      return (unsigned int)-1073741306;
    }
    v12 = *(_DWORD *)(a2 + 24);
    if ( v12 == 4 )
    {
      if ( v10 >= 4 )
      {
        if ( !v9 )
          return (unsigned int)-1073741811;
        v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v7 )
        {
          v14 = *v9 != 0 ? 2 : 0;
          v15 = *(_DWORD *)(a1 + 16) & 0xFFFFFFFD;
          goto LABEL_49;
        }
        v16 = *(_DWORD *)(a1 + 16) >> 1;
LABEL_51:
        *v9 = v16 & 1;
        *(_QWORD *)(a2 + 72) = 4;
LABEL_52:
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v13);
        if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
          return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
        return 0;
      }
      return (unsigned int)-1073741306;
    }
    if ( v12 != 12290 )
    {
      if ( v12 == 12292 )
      {
        if ( *(__int64 (__fastcall **)())a2 != AfdSynchronousTlIORequestComplete
          || v7
          || (*(_DWORD *)(a1 + 16) & 1) != 0
          || v10 < 4
          || !v9 )
        {
          return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
        }
        *v9 = 0;
        *(_QWORD *)(a2 + 72) = 4;
        return 0;
      }
      if ( v12 != -5 )
        return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
      if ( v10 >= 4 )
      {
        if ( !v9 )
          return (unsigned int)-1073741811;
        v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v7 )
        {
          v14 = *v9 != 0 ? 4 : 0;
          v15 = *(_DWORD *)(a1 + 16) & 0xFFFFFFFB;
LABEL_49:
          *(_DWORD *)(a1 + 16) = v15 | v14;
          goto LABEL_52;
        }
        v16 = *(_DWORD *)(a1 + 16) >> 2;
        goto LABEL_51;
      }
      return (unsigned int)-1073741306;
    }
    if ( v10 < 4 )
      return (unsigned int)-1073741306;
    if ( !v9 )
      return (unsigned int)-1073741811;
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    if ( v7 )
    {
      *(_DWORD *)(a1 + 16) = *(_DWORD *)(a1 + 16) & 0xFFFDFFFF | (*v9 != 0 ? 0x20000 : 0);
    }
    else
    {
      *v9 = (*(_DWORD *)(a1 + 16) >> 17) & 1;
      *(_QWORD *)(a2 + 72) = 4;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v17);
    return 0;
  }
  if ( v5 != 3 )
    return (unsigned int)-1073741811;
  return (unsigned int)WskTdiTLIoControl(a1, (struct _UNICODE_STRING *)a2);
}

```

## disassembly

```asm
0x140064d50  push    rbx
0x140064d52  push    rbp
0x140064d53  push    rsi
0x140064d54  push    rdi
0x140064d55  push    r12
0x140064d57  push    r13
0x140064d59  push    r14
0x140064d5b  push    r15
0x140064d5d  sub     rsp, 48h
0x140064d61  xor     r12d, r12d
0x140064d64  lea     r9, AfdSynchronousTlIORequestComplete
0x140064d6b  mov     [rdx+40h], r12
0x140064d6f  mov     rdi, rcx
0x140064d72  mov     [rdx+48h], r12
0x140064d76  mov     rsi, rdx
0x140064d79  mov     rcx, [rcx+118h]
0x140064d80  test    rcx, rcx
0x140064d83  jnz     short loc_140064DB5
0x140064d85  mov     rax, [rdx]
0x140064d88  mov     rcx, [rdx+8]
0x140064d8c  lea     rdx, AfdTLDontCareIOCompletion
0x140064d93  cmp     rax, rdx
0x140064d96  jz      short loc_140064DAE
0x140064d98  cmp     rax, r9
0x140064d9b  jnz     short loc_140064DA3
0x140064d9d  mov     rcx, [rcx+10h]
0x140064da1  jmp     short loc_140064DAE
0x140064da3  mov     rax, [rcx+0B8h]
0x140064daa  mov     rcx, [rax+8]
0x140064dae  mov     [rdi+118h], rcx
0x140064db5  mov     r8d, [rsi+10h]
0x140064db9  mov     edx, r8d
0x140064dbc  test    r8d, r8d
0x140064dbf  jz      loc_14006500C
0x140064dc5  sub     edx, 1
0x140064dc8  jz      short loc_140064DEA
0x140064dca  sub     edx, 1
0x140064dcd  jz      short loc_140064DEA
0x140064dcf  cmp     edx, 1
0x140064dd2  jnz     loc_1400653DF
0x140064dd8  mov     rdx, rsi
0x140064ddb  mov     rcx, rdi
0x140064dde  call    WskTdiTLIoControl
0x140064de3  mov     edi, eax
0x140064de5  jmp     loc_14006556E
0x140064dea  cmp     r8d, 1
0x140064dee  jnz     short loc_140064DF9
0x140064df0  mov     r14b, r8b
0x140064df3  lea     ebx, [r8+1Fh]
0x140064df7  jmp     short loc_140064E01
0x140064df9  mov     r14b, r12b
0x140064dfc  mov     ebx, 30h ; '0'
0x140064e01  mov     rbx, [rbx+rsi]
0x140064e05  movzx   eax, r14b
0x140064e09  xor     rax, 1
0x140064e0d  add     rax, rax
0x140064e10  mov     rcx, [rsi+rax*8+28h]
0x140064e15  mov     eax, [rsi+14h]
0x140064e18  cmp     eax, 0FFFFh
0x140064e1d  jnz     loc_140064F7C
0x140064e23  mov     eax, [rsi+18h]
0x140064e26  mov     ebp, 4
0x140064e2b  cmp     eax, ebp
0x140064e2d  jz      loc_140064F3E
0x140064e33  cmp     eax, 3002h
0x140064e38  jz      loc_140064ED3
0x140064e3e  cmp     eax, 3004h
0x140064e43  jz      short loc_140064E98
0x140064e45  mov     r13d, 0FFFFFFFBh
0x140064e4b  cmp     eax, r13d
0x140064e4e  jnz     short loc_140064DD8
0x140064e50  cmp     rcx, rbp
0x140064e53  jb      loc_140064F97
0x140064e59  test    rbx, rbx
0x140064e5c  jz      loc_1400653DF
0x140064e62  lea     rcx, [rdi+8]; SpinLock
0x140064e66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064e6d  nop     dword ptr [rax+rax+00h]
0x140064e72  mov     r8b, al
0x140064e75  test    r14b, r14b
0x140064e78  jz      short loc_140064E8D
0x140064e7a  mov     ecx, [rbx]
0x140064e7c  neg     ecx
0x140064e7e  mov     ecx, [rdi+10h]
0x140064e81  sbb     edx, edx
0x140064e83  and     edx, ebp
0x140064e85  and     ecx, r13d
0x140064e88  jmp     loc_140064FD3
0x140064e8d  mov     eax, [rdi+10h]
0x140064e90  shr     eax, 2
0x140064e93  jmp     loc_140064FE0
0x140064e98  cmp     [rsi], r9
0x140064e9b  jnz     loc_140064DD8
0x140064ea1  test    r14b, r14b
0x140064ea4  jnz     loc_140064DD8
0x140064eaa  mov     eax, [rdi+10h]
0x140064ead  test    al, 1
0x140064eaf  jnz     loc_140064DD8
0x140064eb5  cmp     rcx, rbp
0x140064eb8  jb      loc_140064DD8
0x140064ebe  test    rbx, rbx
0x140064ec1  jz      loc_140064DD8
0x140064ec7  mov     [rbx], r12d
0x140064eca  mov     [rsi+48h], rbp
0x140064ece  jmp     loc_140065564
0x140064ed3  cmp     rcx, rbp
0x140064ed6  jb      loc_140064F97
0x140064edc  test    rbx, rbx
0x140064edf  jz      loc_1400653DF
0x140064ee5  lea     rcx, [rdi+8]; SpinLock
0x140064ee9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064ef0  nop     dword ptr [rax+rax+00h]
0x140064ef5  mov     r8b, al
0x140064ef8  test    r14b, r14b
0x140064efb  jz      short loc_140064F17
0x140064efd  mov     ecx, [rbx]
0x140064eff  neg     ecx
0x140064f01  mov     ecx, [rdi+10h]
0x140064f04  sbb     edx, edx
0x140064f06  btr     ecx, 11h
0x140064f0a  and     edx, 20000h
0x140064f10  or      edx, ecx
0x140064f12  mov     [rdi+10h], edx
0x140064f15  jmp     short loc_140064F26
0x140064f17  mov     eax, [rdi+10h]
0x140064f1a  shr     eax, 11h
0x140064f1d  and     eax, 1
0x140064f20  mov     [rbx], eax
0x140064f22  mov     [rsi+48h], rbp
0x140064f26  mov     dl, r8b; NewIrql
0x140064f29  lea     rcx, [rdi+8]; SpinLock
0x140064f2d  call    cs:__imp_KeReleaseSpinLock
0x140064f34  nop     dword ptr [rax+rax+00h]
0x140064f39  jmp     loc_140065564
0x140064f3e  cmp     rcx, rbp
0x140064f41  jb      short loc_140064F97
0x140064f43  test    rbx, rbx
0x140064f46  jz      loc_1400653DF
0x140064f4c  lea     rcx, [rdi+8]; SpinLock
0x140064f50  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064f57  nop     dword ptr [rax+rax+00h]
0x140064f5c  mov     r8b, al
0x140064f5f  test    r14b, r14b
0x140064f62  jz      short loc_140064F75
0x140064f64  mov     ecx, [rbx]
0x140064f66  neg     ecx
0x140064f68  mov     ecx, [rdi+10h]
0x140064f6b  sbb     edx, edx
0x140064f6d  and     edx, 2
0x140064f70  and     ecx, 0FFFFFFFDh
0x140064f73  jmp     short loc_140064FD3
0x140064f75  mov     eax, [rdi+10h]
0x140064f78  shr     eax, 1
0x140064f7a  jmp     short loc_140064FE0
0x140064f7c  cmp     eax, 29h ; ')'
0x140064f7f  jnz     loc_140064DD8
0x140064f85  cmp     dword ptr [rsi+18h], 1Bh
0x140064f89  jnz     loc_140064DD8
0x140064f8f  lea     ebp, [rax-25h]
0x140064f92  cmp     rcx, rbp
0x140064f95  jnb     short loc_140064FA1
0x140064f97  mov     edi, 0C0000206h
0x140064f9c  jmp     loc_14006556E
0x140064fa1  test    rbx, rbx
0x140064fa4  jz      loc_1400653DF
0x140064faa  lea     rcx, [rdi+8]; SpinLock
0x140064fae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140064fb5  nop     dword ptr [rax+rax+00h]
0x140064fba  mov     r8b, al
0x140064fbd  test    r14b, r14b
0x140064fc0  jz      short loc_140064FDA
0x140064fc2  mov     ecx, [rbx]
0x140064fc4  neg     ecx
0x140064fc6  mov     ecx, [rdi+10h]
0x140064fc9  sbb     edx, edx
0x140064fcb  not     edx
0x140064fcd  and     edx, 8
0x140064fd0  and     ecx, 0FFFFFFF7h
0x140064fd3  or      edx, ecx
0x140064fd5  mov     [rdi+10h], edx
0x140064fd8  jmp     short loc_140064FE9
0x140064fda  mov     eax, [rdi+10h]
0x140064fdd  shr     eax, 3
0x140064fe0  and     eax, 1
0x140064fe3  mov     [rbx], eax
0x140064fe5  mov     [rsi+48h], rbp
0x140064fe9  mov     dl, r8b; NewIrql
0x140064fec  lea     rcx, [rdi+8]; SpinLock
0x140064ff0  call    cs:__imp_KeReleaseSpinLock
0x140064ff7  nop     dword ptr [rax+rax+00h]
0x140064ffc  mov     eax, [rdi+10h]
0x140064fff  test    al, 1
0x140065001  jz      loc_140065564
0x140065007  jmp     loc_140064DD8
0x14006500c  mov     eax, [rsi+18h]
0x14006500f  mov     ebx, 20h ; ' '
0x140065014  cmp     eax, ebx
0x140065016  ja      loc_1400653BB
0x14006501c  jz      loc_140065323
0x140065022  cmp     eax, 8
0x140065025  jz      loc_14006527E
0x14006502b  cmp     eax, 10h
0x14006502e  jz      loc_1400650EF
0x140065034  cmp     eax, 14h
0x140065037  jz      short loc_1400650AF
0x140065039  cmp     eax, 18h
0x14006503c  jz      short loc_1400650A7
0x14006503e  cmp     eax, 1Ch
0x140065041  jnz     loc_1400653DF
0x140065047  cmp     [rsi+28h], r12
0x14006504b  jnz     loc_1400653F0
0x140065051  lea     rcx, [rdi+8]; SpinLock
0x140065055  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006505c  nop     dword ptr [rax+rax+00h]
0x140065061  mov     rsi, [rdi+90h]
0x140065068  lea     rcx, [rdi+8]; SpinLock
0x14006506c  btr     dword ptr [rdi+10h], 10h
0x140065071  mov     dl, al; NewIrql
0x140065073  mov     [rdi+90h], r12
0x14006507a  call    cs:__imp_KeReleaseSpinLock
0x140065081  nop     dword ptr [rax+rax+00h]
0x140065086  test    rsi, rsi
0x140065089  jz      loc_140065564
0x14006508f  or      eax, 0FFFFFFFFh
0x140065092  lock xadd [rsi], eax
0x140065096  cmp     eax, 1
0x140065099  jnz     loc_140065564
0x14006509f  mov     rdx, rsi
0x1400650a2  jmp     loc_140065551
0x1400650a7  mov     bpl, 1
0x1400650aa  jmp     loc_14006532B
0x1400650af  mov     r8, [rsi+38h]; Size
0x1400650b3  mov     rdx, [rdi+0C8h]; Src
0x1400650ba  mov     rcx, [rsi+30h]; void *
0x1400650be  mov     rbx, [rsi+8]
0x1400650c2  call    memmove
0x1400650c7  mov     edx, 2; PriorityBoost
0x1400650cc  mov     [rbx+30h], r12d
0x1400650d0  mov     edi, r12d
0x1400650d3  mov     rax, [rsi+38h]
0x1400650d7  mov     rcx, rbx; Irp
0x1400650da  mov     [rbx+38h], rax
0x1400650de  call    cs:__imp_IofCompleteRequest
0x1400650e5  nop     dword ptr [rax+rax+00h]
0x1400650ea  jmp     loc_14006556E
0x1400650ef  test    dword ptr [rdi+10h], 100h
0x1400650f6  mov     ebp, 2
0x1400650fb  mov     rbx, [rsi+8]
0x1400650ff  jz      short loc_14006511A
0x140065101  mov     r8, [rsi+38h]; Size
0x140065105  mov     rdx, [rdi+30h]; Src
0x140065109  mov     rcx, [rsi+30h]; void *
0x14006510d  call    memmove
0x140065112  mov     edi, r12d
0x140065115  jmp     loc_1400651E8
0x14006511a  mov     rax, [rbx+0B8h]
0x140065121  mov     edx, 0ACD2h
0x140065126  mov     [rsp+88h+arg_0], rax
0x14006512e  cmp     [rdi], dx
0x140065131  jnz     short loc_140065146
0x140065133  cmp     [rcx+2], bpl
0x140065137  mov     eax, 38h ; '8'
0x14006513c  lea     r14d, [rax+58h]
0x140065140  cmovnz  r14d, eax
0x140065144  jmp     short loc_14006514C
0x140065146  mov     r14d, 38h ; '8'
0x14006514c  mov     rcx, [r14+rdi+10h]
0x140065151  xor     edx, edx; ChargeQuota
0x140065153  mov     cl, [rcx+4Ch]; StackSize
0x140065156  call    cs:__imp_IoAllocateIrp
0x14006515d  nop     dword ptr [rax+rax+00h]
0x140065162  mov     r15, rax
0x140065165  test    rax, rax
0x140065168  jz      short loc_1400651E3
0x14006516a  lea     rcx, stru_1400877C0; Lookaside
0x140065171  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140065178  nop     dword ptr [rax+rax+00h]
0x14006517d  mov     r13, rax
0x140065180  test    rax, rax
0x140065183  jnz     short loc_140065196
0x140065185  mov     rcx, r15; Irp
0x140065188  call    cs:__imp_IoFreeIrp
0x14006518f  nop     dword ptr [rax+rax+00h]
0x140065194  jmp     short loc_1400651E3
0x140065196  lea     rcx, [rax+8]; VirtualAddress
0x14006519a  mov     [rsp+88h+Irp], r12; Irp
0x14006519f  xor     r9d, r9d; ChargeQuota
0x1400651a2  xor     r8d, r8d; SecondaryBuffer
0x1400651a5  mov     edx, 8Ah; Length
0x1400651aa  call    cs:__imp_IoAllocateMdl
0x1400651b1  nop     dword ptr [rax+rax+00h]
0x1400651b6  mov     r12, rax
0x1400651b9  test    rax, rax
0x1400651bc  jnz     short loc_1400651F3
0x1400651be  mov     rcx, r15; Irp
0x1400651c1  call    cs:__imp_IoFreeIrp
0x1400651c8  nop     dword ptr [rax+rax+00h]
0x1400651cd  mov     rdx, r13; Entry
0x1400651d0  lea     rcx, stru_1400877C0; Lookaside
0x1400651d7  call    cs:__imp_ExFreeToNPagedLookasideList
  ... truncated ...
```
