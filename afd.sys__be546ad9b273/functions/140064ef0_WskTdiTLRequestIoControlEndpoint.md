# WskTdiTLRequestIoControlEndpoint

- ea: `0x140064ef0`
- end: `0x140065722`
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
- `0x1400309f0`
- `0x140064548`
- `0x140064ef0`
- `0x1400660d0`
- `0x140072980`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140065328`
- `ntoskrnl!IoFreeIrp` at `0x140065361`
- `ntoskrnl!IoFreeIrp` at `0x140065328`
- `ntoskrnl!IoFreeIrp` at `0x140065361`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006547a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400654f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006547a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400654f1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140065396`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140065396`
- `ntoskrnl!IoAllocateIrp` at `0x1400652f6`
- `ntoskrnl!IoAllocateIrp` at `0x1400652f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065311`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065597`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065311`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065597`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140065377`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400656f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140065377`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400656f8`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14006552c`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14006552c`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140065514`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140065514`
- `ntoskrnl!IoAllocateMdl` at `0x14006534a`
- `ntoskrnl!IoAllocateMdl` at `0x14006534a`
- `ntoskrnl!IofCompleteRequest` at `0x14006527e`
- `ntoskrnl!IofCompleteRequest` at `0x14006527e`
- `ntoskrnl!IofCallDriver` at `0x14006540d`
- `ntoskrnl!IofCallDriver` at `0x14006540d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065006`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065089`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400650f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006514e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400651f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065693`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065006`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065089`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400650f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006514e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400651f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065693`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400650cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065190`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006521a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400656d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400650cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065190`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006521a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400656d0`
- `NETIO!NetioInsertWorkQueue` at `0x1400654ad`
- `NETIO!NetioInsertWorkQueue` at `0x1400654ad`

## pseudocode

```c
__int64 __fastcall WskTdiTLRequestIoControlEndpoint(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v2)(); // r9
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // edi
  unsigned __int8 v8; // r14
  __int64 v9; // rbx
  int *v10; // rbx
  unsigned __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  KIRQL v14; // r8
  int v15; // edx
  unsigned int v16; // ecx
  int v17; // eax
  KIRQL v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rbx
  KIRQL v21; // al
  volatile signed __int32 *v22; // rsi
  volatile signed __int32 *v23; // rdx
  unsigned __int8 v24; // bp
  IRP *v25; // rbx
  __int64 v26; // r14
  PIRP Irp; // r15
  char *v28; // rax
  void *v29; // r13
  struct _MDL *Mdl; // rax
  struct _MDL *v31; // r12
  struct _IO_STACK_LOCATION *v32; // rax
  struct _IO_STACK_LOCATION *v33; // rcx
  __int64 v34; // rdx
  void *PoolPriority; // rax
  void *v36; // rbx
  __int64 *v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  char *v41; // rax
  char *v42; // r15
  __int64 v43; // r14
  __int64 v44; // rcx
  bool v45; // zf
  __int16 v46; // ax
  int v47; // eax
  char *v48; // rbx
  UCHAR v49; // r14
  UCHAR v50; // al
  KIRQL v51; // al
  int v52; // r9d
  volatile signed __int32 *v53; // rbp
  unsigned int v54; // r8d
  int v55; // r9d
  _WORD Src[2]; // [rsp+30h] [rbp-58h] BYREF
  int v57; // [rsp+34h] [rbp-54h]
  __int64 v58; // [rsp+38h] [rbp-50h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+90h] [rbp+8h]

  v2 = AfdSynchronousTlIORequestComplete;
  *(_QWORD *)(a2 + 64) = 0;
  *(_QWORD *)(a2 + 72) = 0;
  v5 = *(_QWORD *)(a1 + 280);
  if ( !v5 )
  {
    v5 = *(_QWORD *)(a2 + 8);
    if ( *(__int64 (__fastcall **)())a2 != AfdTLDontCareIOCompletion )
    {
      if ( *(__int64 (__fastcall **)())a2 == AfdSynchronousTlIORequestComplete )
        v5 = *(_QWORD *)(v5 + 16);
      else
        v5 = *(_QWORD *)(*(_QWORD *)(v5 + 184) + 8LL);
    }
    *(_QWORD *)(a1 + 280) = v5;
  }
  v6 = *(unsigned int *)(a2 + 16);
  if ( !(_DWORD)v6 )
  {
    v19 = *(_DWORD *)(a2 + 24);
    v20 = 32;
    if ( v19 > 0x20 )
    {
      if ( v19 != 40 )
      {
        if ( v19 == 44 || v19 == 48 )
          return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
        if ( v19 == 52 )
          return 0;
        return (unsigned int)-1073741811;
      }
      goto LABEL_61;
    }
    switch ( v19 )
    {
      case 0x20u:
        v24 = 0;
        v20 = 48;
        goto LABEL_92;
      case 8u:
        v34 = *(_QWORD *)(a2 + 40);
        if ( (unsigned int)v34 > (unsigned int)AfdStandardAddressLength )
          PoolPriority = (void *)AfdAllocatePoolPriority(64, v34, 1382311489);
        else
          PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v5, v34, v6, AfdSynchronousTlIORequestComplete);
        v36 = PoolPriority;
        if ( !PoolPriority )
          return (unsigned int)-1073741670;
        memmove(PoolPriority, *(const void **)(a2 + 32), *(_QWORD *)(a2 + 40));
        *(_QWORD *)(a1 + 48) = v36;
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
        v25 = *(IRP **)(a2 + 8);
        if ( (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
        {
          memmove(*(void **)(a2 + 48), *(const void **)(a1 + 48), *(_QWORD *)(a2 + 56));
          v7 = 0;
LABEL_81:
          v25->IoStatus.Status = v7;
          goto LABEL_67;
        }
        CurrentStackLocation = v25->Tail.Overlay.CurrentStackLocation;
        if ( *(_WORD *)a1 == 0xACD2 )
        {
          v26 = 144;
          if ( *(_BYTE *)(v5 + 2) != 2 )
            v26 = 56;
        }
        else
        {
          v26 = 56;
        }
        Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v26 + a1 + 16) + 76LL), 0);
        if ( !Irp )
        {
LABEL_80:
          v7 = -1073741670;
          goto LABEL_81;
        }
        v28 = (char *)ExAllocateFromNPagedLookasideList(&stru_1400877C0);
        v29 = v28;
        if ( !v28 )
        {
          IoFreeIrp(Irp);
          goto LABEL_80;
        }
        Mdl = IoAllocateMdl(v28 + 8, 0x8Au, 0, 0, 0);
        v31 = Mdl;
        if ( !Mdl )
        {
          IoFreeIrp(Irp);
          ExFreeToNPagedLookasideList(&stru_1400877C0, v29);
          goto LABEL_80;
        }
        MmBuildMdlForNonPagedPool(Mdl);
        v32 = Irp->Tail.Overlay.CurrentStackLocation;
        Irp->MdlAddress = v31;
        v32[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPAddressQuery;
        v32[-1].Context = v25;
        v32[-1].Control = -32;
        v33 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v33[-1].MajorFunction = 3087;
        v33[-1].DeviceObject = *(PDEVICE_OBJECT *)(v26 + a1 + 16);
        v33[-1].FileObject = *(PFILE_OBJECT *)(v26 + a1 + 8);
        v33[-1].Parameters.Read.Length = 3;
        v33[-1].Parameters.QueryDirectory.FileName = 0;
        CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v29;
        v25->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        IofCallDriver(*(PDEVICE_OBJECT *)(v26 + a1 + 16), Irp);
        break;
      case 0x14u:
        v25 = *(IRP **)(a2 + 8);
        memmove(*(void **)(a2 + 48), *(const void **)(a1 + 200), *(_QWORD *)(a2 + 56));
        v25->IoStatus.Status = 0;
        v7 = 0;
LABEL_67:
        v25->IoStatus.Information = *(_QWORD *)(a2 + 56);
        IofCompleteRequest(v25, 2);
        return v7;
      case 0x18u:
        v24 = 1;
LABEL_92:
        if ( *(_QWORD *)(a2 + 16 * (v24 ^ 1LL) + 40) < 8u )
          return (unsigned int)-1073741306;
        if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
          return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
        v37 = *(__int64 **)(v20 + a2);
        if ( KeGetCurrentIrql() )
          return (unsigned int)-1073741637;
        if ( v24 )
        {
          v38 = *(_QWORD *)(a1 + 40);
          if ( v38 )
            ObDereferenceSecurityDescriptor(v38, 1);
          v39 = *v37;
          *(_QWORD *)(a1 + 40) = *v37;
          ObReferenceSecurityDescriptor(v39, 1);
        }
        else
        {
          *v37 = *(_QWORD *)(a1 + 40);
          *(_QWORD *)(a2 + 72) = 8;
        }
        return 0;
      case 0x1Cu:
LABEL_61:
        if ( !*(_QWORD *)(a2 + 40) )
        {
          v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          v22 = *(volatile signed __int32 **)(a1 + 144);
          *(_DWORD *)(a1 + 16) &= ~0x10000u;
          *(_QWORD *)(a1 + 144) = 0;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v21);
          if ( !v22 || _InterlockedExchangeAdd(v22, 0xFFFFFFFF) != 1 )
            return 0;
          v23 = v22;
          goto LABEL_119;
        }
        v41 = (char *)ExAllocateFromNPagedLookasideList(&stru_1400877C0);
        v42 = v41;
        if ( v41 )
        {
          v43 = *(_QWORD *)(a2 + 32);
          memset(v41 + 4, 0, 0xC4u);
          *(_DWORD *)v42 = 1;
          if ( (*(_DWORD *)(a1 + 16) & 0x20) != 0 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(v43 + 8)) )
          {
            v45 = *(_WORD *)v43 == 23;
            v46 = *(_WORD *)(v43 + 2);
            Src[0] = 2;
            Src[1] = v46;
            v58 = 0;
            if ( !v45 )
              v44 = v43 + 4;
            v47 = *(_DWORD *)(v44 + 12);
            v48 = v42 + 56;
            *((_DWORD *)v42 + 14) = 1;
            v57 = v47;
            v49 = SOCKADDR_SIZE(2u);
            *((_WORD *)v42 + 30) = v49 - 2;
            memmove(v42 + 62, Src, v49);
          }
          else
          {
            v48 = v42 + 56;
            *((_DWORD *)v42 + 14) = 1;
            *((_WORD *)v42 + 30) = SOCKADDR_SIZE(*(_WORD *)v43) - 2;
            v50 = SOCKADDR_SIZE(*(_WORD *)v43);
            memmove(v42 + 62, (const void *)v43, v50);
            v49 = SOCKADDR_SIZE(*(_WORD *)v43);
          }
          *((_DWORD *)v42 + 10) = v49 + 6;
          *((_QWORD *)v42 + 6) = v48;
          v51 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          v52 = *(_DWORD *)(a1 + 16);
          v53 = *(volatile signed __int32 **)(a1 + 144);
          v54 = v52 & 0xFFFEFFFF;
          *(_QWORD *)(a1 + 144) = v42;
          v55 = v52 | 0x10000;
          if ( *(_DWORD *)(a2 + 24) != 40 )
            v55 = v54;
          *(_DWORD *)(a1 + 16) = v55;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v51);
          if ( !v53 || _InterlockedExchangeAdd(v53, 0xFFFFFFFF) != 1 )
            return 0;
          v23 = v53;
LABEL_119:
          ExFreeToNPagedLookasideList(&stru_1400877C0, (PVOID)v23);
          return 0;
        }
        return (unsigned int)-1073741670;
      default:
        return (unsigned int)-1073741811;
    }
    return 259;
  }
  if ( (_DWORD)v6 == 1 || (_DWORD)v6 == 2 )
  {
    if ( (_DWORD)v6 == 1 )
    {
      v8 = 1;
      v9 = 32;
    }
    else
    {
      v8 = 0;
      v9 = 48;
    }
    v10 = *(int **)(v9 + a2);
    v11 = *(_QWORD *)(a2 + 16 * (v8 ^ 1LL) + 40);
    v12 = *(_DWORD *)(a2 + 20);
    if ( v12 != 0xFFFF )
    {
      if ( v12 != 41 || *(_DWORD *)(a2 + 24) != 27 )
        return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
      if ( v11 >= 4 )
      {
        if ( !v10 )
          return (unsigned int)-1073741811;
        v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v8 )
        {
          v15 = *v10 == 0 ? 8 : 0;
          v16 = *(_DWORD *)(a1 + 16) & 0xFFFFFFF7;
          goto LABEL_49;
        }
        v17 = *(_DWORD *)(a1 + 16) >> 3;
        goto LABEL_51;
      }
      return (unsigned int)-1073741306;
    }
    v13 = *(_DWORD *)(a2 + 24);
    if ( v13 == 4 )
    {
      if ( v11 >= 4 )
      {
        if ( !v10 )
          return (unsigned int)-1073741811;
        v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v8 )
        {
          v15 = *v10 != 0 ? 2 : 0;
          v16 = *(_DWORD *)(a1 + 16) & 0xFFFFFFFD;
          goto LABEL_49;
        }
        v17 = *(_DWORD *)(a1 + 16) >> 1;
LABEL_51:
        *v10 = v17 & 1;
        *(_QWORD *)(a2 + 72) = 4;
LABEL_52:
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v14);
        if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
          return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
        return 0;
      }
      return (unsigned int)-1073741306;
    }
    if ( v13 != 12290 )
    {
      if ( v13 == 12292 )
      {
        if ( *(__int64 (__fastcall **)())a2 != AfdSynchronousTlIORequestComplete
          || v8
          || (*(_DWORD *)(a1 + 16) & 1) != 0
          || v11 < 4
          || !v10 )
        {
          return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
        }
        *v10 = 0;
        *(_QWORD *)(a2 + 72) = 4;
        return 0;
      }
      if ( v13 != -5 )
        return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
      if ( v11 >= 4 )
      {
        if ( !v10 )
          return (unsigned int)-1073741811;
        v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
        if ( v8 )
        {
          v15 = *v10 != 0 ? 4 : 0;
          v16 = *(_DWORD *)(a1 + 16) & 0xFFFFFFFB;
LABEL_49:
          *(_DWORD *)(a1 + 16) = v16 | v15;
          goto LABEL_52;
        }
        v17 = *(_DWORD *)(a1 + 16) >> 2;
        goto LABEL_51;
      }
      return (unsigned int)-1073741306;
    }
    if ( v11 < 4 )
      return (unsigned int)-1073741306;
    if ( !v10 )
      return (unsigned int)-1073741811;
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    if ( v8 )
    {
      *(_DWORD *)(a1 + 16) = *(_DWORD *)(a1 + 16) & 0xFFFDFFFF | (*v10 != 0 ? 0x20000 : 0);
    }
    else
    {
      *v10 = (*(_DWORD *)(a1 + 16) >> 17) & 1;
      *(_QWORD *)(a2 + 72) = 4;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v18);
    return 0;
  }
  if ( (_DWORD)v6 != 3 )
    return (unsigned int)-1073741811;
  return (unsigned int)WskTdiTLIoControl(a1, a2, v6, v2);
}

```

## disassembly

```asm
0x140064ef0  push    rbx
0x140064ef2  push    rbp
0x140064ef3  push    rsi
0x140064ef4  push    rdi
0x140064ef5  push    r12
0x140064ef7  push    r13
0x140064ef9  push    r14
0x140064efb  push    r15
0x140064efd  sub     rsp, 48h
0x140064f01  xor     r12d, r12d
0x140064f04  lea     r9, AfdSynchronousTlIORequestComplete
0x140064f0b  mov     [rdx+40h], r12
0x140064f0f  mov     rdi, rcx
0x140064f12  mov     [rdx+48h], r12
0x140064f16  mov     rsi, rdx
0x140064f19  mov     rcx, [rcx+118h]
0x140064f20  test    rcx, rcx
0x140064f23  jnz     short loc_140064F55
0x140064f25  mov     rax, [rdx]
0x140064f28  mov     rcx, [rdx+8]
0x140064f2c  lea     rdx, AfdTLDontCareIOCompletion
0x140064f33  cmp     rax, rdx
0x140064f36  jz      short loc_140064F4E
0x140064f38  cmp     rax, r9
0x140064f3b  jnz     short loc_140064F43
0x140064f3d  mov     rcx, [rcx+10h]
0x140064f41  jmp     short loc_140064F4E
0x140064f43  mov     rax, [rcx+0B8h]
0x140064f4a  mov     rcx, [rax+8]
0x140064f4e  mov     [rdi+118h], rcx
0x140064f55  mov     r8d, [rsi+10h]
0x140064f59  mov     edx, r8d
0x140064f5c  test    r8d, r8d
0x140064f5f  jz      loc_1400651AC
0x140064f65  sub     edx, 1
0x140064f68  jz      short loc_140064F8A
0x140064f6a  sub     edx, 1
0x140064f6d  jz      short loc_140064F8A
0x140064f6f  cmp     edx, 1
0x140064f72  jnz     loc_14006557F
0x140064f78  mov     rdx, rsi
0x140064f7b  mov     rcx, rdi
0x140064f7e  call    WskTdiTLIoControl
0x140064f83  mov     edi, eax
0x140064f85  jmp     loc_14006570E
0x140064f8a  cmp     r8d, 1
0x140064f8e  jnz     short loc_140064F99
0x140064f90  mov     r14b, r8b
0x140064f93  lea     ebx, [r8+1Fh]
0x140064f97  jmp     short loc_140064FA1
0x140064f99  mov     r14b, r12b
0x140064f9c  mov     ebx, 30h ; '0'
0x140064fa1  mov     rbx, [rbx+rsi]
0x140064fa5  movzx   eax, r14b
0x140064fa9  xor     rax, 1
0x140064fad  add     rax, rax
0x140064fb0  mov     rcx, [rsi+rax*8+28h]
0x140064fb5  mov     eax, [rsi+14h]
0x140064fb8  cmp     eax, 0FFFFh
0x140064fbd  jnz     loc_14006511C
0x140064fc3  mov     eax, [rsi+18h]
0x140064fc6  mov     ebp, 4
0x140064fcb  cmp     eax, ebp
0x140064fcd  jz      loc_1400650DE
0x140064fd3  cmp     eax, 3002h
0x140064fd8  jz      loc_140065073
0x140064fde  cmp     eax, 3004h
0x140064fe3  jz      short loc_140065038
0x140064fe5  mov     r13d, 0FFFFFFFBh
0x140064feb  cmp     eax, r13d
0x140064fee  jnz     short loc_140064F78
0x140064ff0  cmp     rcx, rbp
0x140064ff3  jb      loc_140065137
0x140064ff9  test    rbx, rbx
0x140064ffc  jz      loc_14006557F
0x140065002  lea     rcx, [rdi+8]; SpinLock
0x140065006  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006500d  nop     dword ptr [rax+rax+00h]
0x140065012  mov     r8b, al
0x140065015  test    r14b, r14b
0x140065018  jz      short loc_14006502D
0x14006501a  mov     ecx, [rbx]
0x14006501c  neg     ecx
0x14006501e  mov     ecx, [rdi+10h]
0x140065021  sbb     edx, edx
0x140065023  and     edx, ebp
0x140065025  and     ecx, r13d
0x140065028  jmp     loc_140065173
0x14006502d  mov     eax, [rdi+10h]
0x140065030  shr     eax, 2
0x140065033  jmp     loc_140065180
0x140065038  cmp     [rsi], r9
0x14006503b  jnz     loc_140064F78
0x140065041  test    r14b, r14b
0x140065044  jnz     loc_140064F78
0x14006504a  mov     eax, [rdi+10h]
0x14006504d  test    al, 1
0x14006504f  jnz     loc_140064F78
0x140065055  cmp     rcx, rbp
0x140065058  jb      loc_140064F78
0x14006505e  test    rbx, rbx
0x140065061  jz      loc_140064F78
0x140065067  mov     [rbx], r12d
0x14006506a  mov     [rsi+48h], rbp
0x14006506e  jmp     loc_140065704
0x140065073  cmp     rcx, rbp
0x140065076  jb      loc_140065137
0x14006507c  test    rbx, rbx
0x14006507f  jz      loc_14006557F
0x140065085  lea     rcx, [rdi+8]; SpinLock
0x140065089  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140065090  nop     dword ptr [rax+rax+00h]
0x140065095  mov     r8b, al
0x140065098  test    r14b, r14b
0x14006509b  jz      short loc_1400650B7
0x14006509d  mov     ecx, [rbx]
0x14006509f  neg     ecx
0x1400650a1  mov     ecx, [rdi+10h]
0x1400650a4  sbb     edx, edx
0x1400650a6  btr     ecx, 11h
0x1400650aa  and     edx, 20000h
0x1400650b0  or      edx, ecx
0x1400650b2  mov     [rdi+10h], edx
0x1400650b5  jmp     short loc_1400650C6
0x1400650b7  mov     eax, [rdi+10h]
0x1400650ba  shr     eax, 11h
0x1400650bd  and     eax, 1
0x1400650c0  mov     [rbx], eax
0x1400650c2  mov     [rsi+48h], rbp
0x1400650c6  mov     dl, r8b; NewIrql
0x1400650c9  lea     rcx, [rdi+8]; SpinLock
0x1400650cd  call    cs:__imp_KeReleaseSpinLock
0x1400650d4  nop     dword ptr [rax+rax+00h]
0x1400650d9  jmp     loc_140065704
0x1400650de  cmp     rcx, rbp
0x1400650e1  jb      short loc_140065137
0x1400650e3  test    rbx, rbx
0x1400650e6  jz      loc_14006557F
0x1400650ec  lea     rcx, [rdi+8]; SpinLock
0x1400650f0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400650f7  nop     dword ptr [rax+rax+00h]
0x1400650fc  mov     r8b, al
0x1400650ff  test    r14b, r14b
0x140065102  jz      short loc_140065115
0x140065104  mov     ecx, [rbx]
0x140065106  neg     ecx
0x140065108  mov     ecx, [rdi+10h]
0x14006510b  sbb     edx, edx
0x14006510d  and     edx, 2
0x140065110  and     ecx, 0FFFFFFFDh
0x140065113  jmp     short loc_140065173
0x140065115  mov     eax, [rdi+10h]
0x140065118  shr     eax, 1
0x14006511a  jmp     short loc_140065180
0x14006511c  cmp     eax, 29h ; ')'
0x14006511f  jnz     loc_140064F78
0x140065125  cmp     dword ptr [rsi+18h], 1Bh
0x140065129  jnz     loc_140064F78
0x14006512f  lea     ebp, [rax-25h]
0x140065132  cmp     rcx, rbp
0x140065135  jnb     short loc_140065141
0x140065137  mov     edi, 0C0000206h
0x14006513c  jmp     loc_14006570E
0x140065141  test    rbx, rbx
0x140065144  jz      loc_14006557F
0x14006514a  lea     rcx, [rdi+8]; SpinLock
0x14006514e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140065155  nop     dword ptr [rax+rax+00h]
0x14006515a  mov     r8b, al
0x14006515d  test    r14b, r14b
0x140065160  jz      short loc_14006517A
0x140065162  mov     ecx, [rbx]
0x140065164  neg     ecx
0x140065166  mov     ecx, [rdi+10h]
0x140065169  sbb     edx, edx
0x14006516b  not     edx
0x14006516d  and     edx, 8
0x140065170  and     ecx, 0FFFFFFF7h
0x140065173  or      edx, ecx
0x140065175  mov     [rdi+10h], edx
0x140065178  jmp     short loc_140065189
0x14006517a  mov     eax, [rdi+10h]
0x14006517d  shr     eax, 3
0x140065180  and     eax, 1
0x140065183  mov     [rbx], eax
0x140065185  mov     [rsi+48h], rbp
0x140065189  mov     dl, r8b; NewIrql
0x14006518c  lea     rcx, [rdi+8]; SpinLock
0x140065190  call    cs:__imp_KeReleaseSpinLock
0x140065197  nop     dword ptr [rax+rax+00h]
0x14006519c  mov     eax, [rdi+10h]
0x14006519f  test    al, 1
0x1400651a1  jz      loc_140065704
0x1400651a7  jmp     loc_140064F78
0x1400651ac  mov     eax, [rsi+18h]
0x1400651af  mov     ebx, 20h ; ' '
0x1400651b4  cmp     eax, ebx
0x1400651b6  ja      loc_14006555B
0x1400651bc  jz      loc_1400654C3
0x1400651c2  cmp     eax, 8
0x1400651c5  jz      loc_14006541E
0x1400651cb  cmp     eax, 10h
0x1400651ce  jz      loc_14006528F
0x1400651d4  cmp     eax, 14h
0x1400651d7  jz      short loc_14006524F
0x1400651d9  cmp     eax, 18h
0x1400651dc  jz      short loc_140065247
0x1400651de  cmp     eax, 1Ch
0x1400651e1  jnz     loc_14006557F
0x1400651e7  cmp     [rsi+28h], r12
0x1400651eb  jnz     loc_140065590
0x1400651f1  lea     rcx, [rdi+8]; SpinLock
0x1400651f5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400651fc  nop     dword ptr [rax+rax+00h]
0x140065201  mov     rsi, [rdi+90h]
0x140065208  lea     rcx, [rdi+8]; SpinLock
0x14006520c  btr     dword ptr [rdi+10h], 10h
0x140065211  mov     dl, al; NewIrql
0x140065213  mov     [rdi+90h], r12
0x14006521a  call    cs:__imp_KeReleaseSpinLock
0x140065221  nop     dword ptr [rax+rax+00h]
0x140065226  test    rsi, rsi
0x140065229  jz      loc_140065704
0x14006522f  or      eax, 0FFFFFFFFh
0x140065232  lock xadd [rsi], eax
0x140065236  cmp     eax, 1
0x140065239  jnz     loc_140065704
0x14006523f  mov     rdx, rsi
0x140065242  jmp     loc_1400656F1
0x140065247  mov     bpl, 1
0x14006524a  jmp     loc_1400654CB
0x14006524f  mov     r8, [rsi+38h]; Size
0x140065253  mov     rdx, [rdi+0C8h]; Src
0x14006525a  mov     rcx, [rsi+30h]; void *
0x14006525e  mov     rbx, [rsi+8]
0x140065262  call    memmove
0x140065267  mov     edx, 2; PriorityBoost
0x14006526c  mov     [rbx+30h], r12d
0x140065270  mov     edi, r12d
0x140065273  mov     rax, [rsi+38h]
0x140065277  mov     rcx, rbx; Irp
0x14006527a  mov     [rbx+38h], rax
0x14006527e  call    cs:__imp_IofCompleteRequest
0x140065285  nop     dword ptr [rax+rax+00h]
0x14006528a  jmp     loc_14006570E
0x14006528f  test    dword ptr [rdi+10h], 100h
0x140065296  mov     ebp, 2
0x14006529b  mov     rbx, [rsi+8]
0x14006529f  jz      short loc_1400652BA
0x1400652a1  mov     r8, [rsi+38h]; Size
0x1400652a5  mov     rdx, [rdi+30h]; Src
0x1400652a9  mov     rcx, [rsi+30h]; void *
0x1400652ad  call    memmove
0x1400652b2  mov     edi, r12d
0x1400652b5  jmp     loc_140065388
0x1400652ba  mov     rax, [rbx+0B8h]
0x1400652c1  mov     edx, 0ACD2h
0x1400652c6  mov     [rsp+88h+arg_0], rax
0x1400652ce  cmp     [rdi], dx
0x1400652d1  jnz     short loc_1400652E6
0x1400652d3  cmp     [rcx+2], bpl
0x1400652d7  mov     eax, 38h ; '8'
0x1400652dc  lea     r14d, [rax+58h]
0x1400652e0  cmovnz  r14d, eax
0x1400652e4  jmp     short loc_1400652EC
0x1400652e6  mov     r14d, 38h ; '8'
0x1400652ec  mov     rcx, [r14+rdi+10h]
0x1400652f1  xor     edx, edx; ChargeQuota
0x1400652f3  mov     cl, [rcx+4Ch]; StackSize
0x1400652f6  call    cs:__imp_IoAllocateIrp
0x1400652fd  nop     dword ptr [rax+rax+00h]
0x140065302  mov     r15, rax
0x140065305  test    rax, rax
0x140065308  jz      short loc_140065383
0x14006530a  lea     rcx, stru_1400877C0; Lookaside
0x140065311  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140065318  nop     dword ptr [rax+rax+00h]
0x14006531d  mov     r13, rax
0x140065320  test    rax, rax
0x140065323  jnz     short loc_140065336
0x140065325  mov     rcx, r15; Irp
0x140065328  call    cs:__imp_IoFreeIrp
0x14006532f  nop     dword ptr [rax+rax+00h]
0x140065334  jmp     short loc_140065383
0x140065336  lea     rcx, [rax+8]; VirtualAddress
0x14006533a  mov     [rsp+88h+Irp], r12; Irp
0x14006533f  xor     r9d, r9d; ChargeQuota
0x140065342  xor     r8d, r8d; SecondaryBuffer
0x140065345  mov     edx, 8Ah; Length
0x14006534a  call    cs:__imp_IoAllocateMdl
0x140065351  nop     dword ptr [rax+rax+00h]
0x140065356  mov     r12, rax
0x140065359  test    rax, rax
0x14006535c  jnz     short loc_140065393
0x14006535e  mov     rcx, r15; Irp
0x140065361  call    cs:__imp_IoFreeIrp
0x140065368  nop     dword ptr [rax+rax+00h]
0x14006536d  mov     rdx, r13; Entry
0x140065370  lea     rcx, stru_1400877C0; Lookaside
0x140065377  call    cs:__imp_ExFreeToNPagedLookasideList
  ... truncated ...
```
