# AfdRoutingInterfaceChange

- ea: `0x140051df0`
- end: `0x140052436`
- name: `AfdRoutingInterfaceChange`
- size: `1606`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140001bb4`
- `0x14002fd7c`
- `0x1400309f0`
- `0x1400445d8`
- `0x140051df0`
- `0x140072840`
- `0x140072870`
- `0x1400930cc`
- `0x140093104`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400523fa`
- `ntoskrnl!IofCompleteRequest` at `0x1400523fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400520ce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005214b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052244`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005226b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400522cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400520ce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005214b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052244`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005226b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400522cf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400520b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400521a9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400520b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400521a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005230d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005230d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523dd`
- `ntoskrnl!ExAllocatePool2` at `0x140051f87`
- `ntoskrnl!ExAllocatePool2` at `0x140052089`
- `ntoskrnl!ExAllocatePool2` at `0x140051f87`
- `ntoskrnl!ExAllocatePool2` at `0x140052089`
- `ntoskrnl!IoIs32bitProcess` at `0x140051ecb`
- `ntoskrnl!IoIs32bitProcess` at `0x140051ecb`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400522ef`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400523a6`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400522ef`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400523a6`
- `NETIO!NsiRegisterChangeNotification` at `0x14005218a`
- `NETIO!NsiRegisterChangeNotification` at `0x14005218a`

## pseudocode

```c
__int64 __fastcall AfdRoutingInterfaceChange(PIRP Irp, __int64 a2)
{
  __int64 v2; // r8
  __int64 Pool2; // rsi
  unsigned int *v5; // r13
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r12
  __int64 v7; // rbx
  __int64 v8; // r15
  NTSTATUS v9; // ebx
  BOOLEAN v10; // al
  unsigned int v11; // ecx
  struct _IRP *MasterIrp; // rax
  PMDL v13; // rbx
  unsigned int MdlAddress; // r12d
  ULONG Flags; // eax
  struct _IRP *v16; // rax
  __int16 v17; // ax
  void *v18; // rdx
  void *v19; // rcx
  void *v20; // rdx
  void *v21; // rcx
  _WORD *v22; // rbx
  _WORD *v23; // r13
  __int16 v24; // cx
  _QWORD *v25; // r12
  const NPI_MODULEID *v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rcx
  BOOLEAN v31; // [rsp+44h] [rbp-B4h]
  __int16 v32; // [rsp+46h] [rbp-B2h]
  const NPI_MODULEID *v33; // [rsp+50h] [rbp-A8h]
  int v34; // [rsp+58h] [rbp-A0h] BYREF
  ULONG v35; // [rsp+5Ch] [rbp-9Ch]
  __int64 v36; // [rsp+60h] [rbp-98h]
  PVOID P; // [rsp+68h] [rbp-90h]
  __int16 v38; // [rsp+70h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-68h]
  _WORD *v41; // [rsp+98h] [rbp-60h]
  PIRP v42; // [rsp+A8h] [rbp-50h]
  __int64 v43; // [rsp+B0h] [rbp-48h]
  __int64 v44; // [rsp+B8h] [rbp-40h] BYREF
  int v45; // [rsp+C0h] [rbp-38h]

  v2 = a2;
  v42 = Irp;
  v44 = 0;
  v45 = 0;
  Pool2 = 0;
  v40 = 0;
  P = 0;
  v41 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v36 = 0;
  v33 = 0;
  v34 = 0;
  v5 = (unsigned int *)(a2 + 16);
  p_AssociatedIrp = &Irp->AssociatedIrp;
  v7 = a2 + 48;
  if ( (BYTE2(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qqll(1040, 15, a2, *(_QWORD *)(*(_QWORD *)v7 + 24LL), p_AssociatedIrp->MasterIrp, *v5, *(_DWORD *)(a2 + 8));
  v8 = *(_QWORD *)(*(_QWORD *)v7 + 24LL);
  v43 = v8;
  v9 = AfdQueryCompartmentId(v8, &v34, v2);
  if ( v9 < 0 )
  {
LABEL_68:
    if ( v9 == -1073741811 )
    {
LABEL_69:
      if ( (BYTE2(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1040, 16, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, v8);
    }
LABEL_71:
    if ( v36 )
      NsiDeregisterChangeNotification(v33, 16);
    if ( Pool2 )
      ExFreePoolWithTag((PVOID)Pool2, 0x71646641u);
    if ( P )
      ExFreePoolWithTag(P, 0x71646641u);
    Irp->IoStatus.Status = v9;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, AfdPriorityBoost);
    return (unsigned int)v9;
  }
  v10 = IoIs32bitProcess(Irp);
  v11 = *v5;
  if ( v10 )
  {
    if ( v11 < 0x18 )
    {
LABEL_6:
      v9 = -1073741811;
      goto LABEL_69;
    }
    MasterIrp = p_AssociatedIrp->MasterIrp;
    v13 = (PMDL)*(unsigned int *)(&p_AssociatedIrp->MasterIrp->Size + 1);
    MdlAddress = (unsigned int)p_AssociatedIrp->MasterIrp->MdlAddress;
    Flags = MasterIrp->Flags;
  }
  else
  {
    if ( v11 < 0x20 )
      goto LABEL_6;
    v16 = p_AssociatedIrp->MasterIrp;
    v13 = p_AssociatedIrp->MasterIrp->MdlAddress;
    MdlAddress = p_AssociatedIrp->MasterIrp->Flags;
    Flags = v16->AssociatedIrp.IrpCount;
  }
  v35 = Flags;
  v31 = 0;
  if ( MdlAddress < 0xC )
  {
    v9 = -1073741811;
    goto LABEL_68;
  }
  if ( Irp->RequestorMode )
    RtlCopyFromUser(&v44, v13, 0xCu);
  else
    RtlCopyVolatileMemory(&v44, v13, 0xCu);
  if ( MdlAddress < (unsigned int)WORD2(v44) + 8 )
  {
    v9 = -1073741811;
    goto LABEL_68;
  }
  Pool2 = ExAllocatePool2(97, 80, 1902405185);
  v40 = Pool2;
  v17 = HIWORD(v44);
  v32 = HIWORD(v44);
  v38 = HIWORD(v44);
  *(_DWORD *)(Pool2 + 40) = v34;
  if ( v17 == 23 )
  {
    if ( WORD2(v44) < 0x1Au )
    {
      v9 = -1073741811;
      goto LABEL_68;
    }
    v18 = (char *)&v13->Next + 6;
    v19 = (void *)(Pool2 + 48);
    if ( Irp->RequestorMode )
      RtlCopyFromUser(v19, v18, 0x1Cu);
    else
      RtlCopyVolatileMemory(v19, v18, 0x1Cu);
    *(_WORD *)(Pool2 + 48) = 23;
    v31 = IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(Pool2 + 56));
    goto LABEL_31;
  }
  if ( v17 != 2 )
  {
    v9 = -1073741637;
    goto LABEL_68;
  }
  if ( WORD2(v44) < 0xEu )
  {
    v9 = -1073741811;
    goto LABEL_68;
  }
  v20 = (char *)&v13->Next + 6;
  v21 = (void *)(Pool2 + 48);
  if ( Irp->RequestorMode )
    RtlCopyFromUser(v21, v20, 0x10u);
  else
    RtlCopyVolatileMemory(v21, v20, 0x10u);
  *(_WORD *)(Pool2 + 48) = 2;
LABEL_31:
  if ( *(_QWORD *)(v8 + 288) )
  {
    v22 = 0;
  }
  else
  {
    v22 = (_WORD *)ExAllocatePool2(97, 24, 1902405185);
    P = v22;
    v41 = v22;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v8 + 56), &LockHandle);
  if ( (*(_DWORD *)(v8 + 8) & 0x800) != 0 )
    goto LABEL_35;
  if ( !*(_QWORD *)(v8 + 288) )
  {
    *v22 = 0;
    *(_QWORD *)(v8 + 288) = v22;
    P = 0;
  }
  v23 = *(_WORD **)(v8 + 288);
  v24 = v32;
  if ( v32 == 2 || v31 )
  {
    v25 = v23 + 4;
    v26 = &NPI_MS_IPV4_MODULEID;
  }
  else
  {
    v25 = v23 + 8;
    v26 = &NPI_MS_IPV6_MODULEID;
  }
  v33 = v26;
  if ( !*v25 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = NsiRegisterChangeNotification(v33, 16, AfdNsiRouteChangeCallback);
    if ( v9 < 0 )
      goto LABEL_68;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v8 + 56), &LockHandle);
    if ( (*(_DWORD *)(v8 + 8) & 0x800) != 0 )
    {
LABEL_35:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v9 = -1073741536;
      goto LABEL_71;
    }
    v24 = v32;
  }
  if ( *v23 )
  {
    if ( *v23 != v24 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      goto LABEL_6;
    }
  }
  else
  {
    *v23 = v24;
  }
  if ( !*v25 )
  {
    *v25 = v36;
    v36 = 0;
  }
  *(_DWORD *)(v8 + 72) &= ~0x800u;
  *(_QWORD *)(Pool2 + 16) = &AfdCleanupRouteChange;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  v27 = *(__int64 **)(v8 + 304);
  if ( *v27 != v8 + 296 )
LABEL_66:
    __fastfail(3u);
  *(_QWORD *)Pool2 = v8 + 296;
  *(_QWORD *)(Pool2 + 8) = v27;
  *v27 = Pool2;
  *(_QWORD *)(v8 + 304) = Pool2;
  if ( (*(_DWORD *)(v8 + 8) & 0x10) != 0 && (v35 & 2) == 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = -1073741661;
    Pool2 = 0;
    goto LABEL_68;
  }
  *(_QWORD *)(Pool2 + 32) = Irp;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)Pool2;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelRouteChange);
  if ( Irp->Cancel && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
  {
    v28 = *(_QWORD *)Pool2;
    if ( *(_QWORD *)(*(_QWORD *)Pool2 + 8LL) == Pool2 )
    {
      v29 = *(_QWORD **)(Pool2 + 8);
      if ( *v29 == Pool2 )
      {
        *v29 = v28;
        *(_QWORD *)(v28 + 8) = v29;
        goto LABEL_35;
      }
    }
    goto LABEL_66;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v36 )
    NsiDeregisterChangeNotification(v33, 16);
  if ( P )
    ExFreePoolWithTag(P, 0x71646641u);
  return 259;
}

```

## disassembly

```asm
0x140051df0  mov     r11, rsp
0x140051df3  mov     [r11+18h], rbx
0x140051df7  mov     [r11+20h], rsi
0x140051dfb  push    rdi
0x140051dfc  push    r12
0x140051dfe  push    r13
0x140051e00  push    r14
0x140051e02  push    r15
0x140051e04  sub     rsp, 0D0h
0x140051e0b  mov     rax, cs:__security_cookie
0x140051e12  xor     rax, rsp
0x140051e15  mov     [rsp+0F8h+var_30], rax
0x140051e1d  mov     r8, rdx
0x140051e20  mov     r14, rcx
0x140051e23  mov     [rsp+0F8h+var_50], rcx
0x140051e2b  xor     eax, eax
0x140051e2d  mov     [r11-40h], rax
0x140051e31  mov     [r11-38h], eax
0x140051e35  xor     edi, edi
0x140051e37  mov     esi, edi
0x140051e39  mov     [r11-68h], rdi
0x140051e3d  mov     [rsp+0F8h+P], rax
0x140051e42  mov     [r11-60h], rax
0x140051e46  xorps   xmm0, xmm0
0x140051e49  movups  xmmword ptr [rsp+0F8h+LockHandle.LockQueue.Next], xmm0
0x140051e4e  mov     [r11-70h], rax
0x140051e52  mov     [rsp+0F8h+var_98], rdi
0x140051e57  mov     [rsp+0F8h+var_A8], rax
0x140051e5c  mov     [rsp+0F8h+var_A0], edi
0x140051e60  lea     r13, [rdx+10h]
0x140051e64  lea     r12, [rcx+18h]
0x140051e68  lea     rbx, [rdx+30h]
0x140051e6c  test    byte ptr cs:xmmword_1400875E0+2, 1
0x140051e73  jz      short loc_140051EA2
0x140051e75  mov     r9, [rbx]
0x140051e78  lea     edx, [rax+0Fh]
0x140051e7b  mov     ecx, 410h
0x140051e80  mov     eax, [r8+8]
0x140051e84  mov     [rsp+0F8h+var_C8], eax
0x140051e88  mov     eax, [r13+0]
0x140051e8c  mov     dword ptr [rsp+0F8h+var_D0], eax
0x140051e90  mov     rax, [r12]
0x140051e94  mov     [rsp+0F8h+var_D8], rax
0x140051e99  mov     r9, [r9+18h]
0x140051e9d  call    WPP_SF_qqll
0x140051ea2  mov     rax, [rbx]
0x140051ea5  mov     r15, [rax+18h]
0x140051ea9  mov     [rsp+0F8h+var_48], r15
0x140051eb1  lea     rdx, [rsp+0F8h+var_A0]
0x140051eb6  mov     rcx, r15
0x140051eb9  call    AfdQueryCompartmentId
0x140051ebe  mov     ebx, eax
0x140051ec0  test    eax, eax
0x140051ec2  js      loc_140052368
0x140051ec8  mov     rcx, r14; Irp
0x140051ecb  call    cs:__imp_IoIs32bitProcess
0x140051ed2  nop     dword ptr [rax+rax+00h]
0x140051ed7  mov     ecx, [r13+0]
0x140051edb  test    al, al
0x140051edd  jz      short loc_140051EFE
0x140051edf  cmp     ecx, 18h
0x140051ee2  jnb     short loc_140051EEE
0x140051ee4  mov     ebx, 0C000000Dh
0x140051ee9  jmp     loc_140052370
0x140051eee  mov     rax, [r12]
0x140051ef2  mov     ebx, [rax+4]
0x140051ef5  mov     r12d, [rax+8]
0x140051ef9  mov     eax, [rax+10h]
0x140051efc  jmp     short loc_140051F12
0x140051efe  cmp     ecx, 20h ; ' '
0x140051f01  jb      short loc_140051EE4
0x140051f03  mov     rax, [r12]
0x140051f07  mov     rbx, [rax+8]
0x140051f0b  mov     r12d, [rax+10h]
0x140051f0f  mov     eax, [rax+18h]
0x140051f12  mov     [rsp+0F8h+var_9C], eax
0x140051f16  mov     [rsp+0F8h+var_B4], dil
0x140051f1b  mov     [rsp+0F8h+var_B8], edi
0x140051f1f  mov     r8d, 0Ch; Size
0x140051f25  cmp     r12d, r8d
0x140051f28  jnb     short loc_140051F3B
0x140051f2a  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051f32  mov     ebx, [rsp+0F8h+var_B8]
0x140051f36  jmp     loc_140052368
0x140051f3b  mov     rdx, rbx; Src
0x140051f3e  lea     rcx, [rsp+0F8h+var_40]; void *
0x140051f46  cmp     [r14+40h], dil
0x140051f4a  jz      short loc_140051F53
0x140051f4c  call    RtlCopyFromUser
0x140051f51  jmp     short loc_140051F58
0x140051f53  call    RtlCopyVolatileMemory
0x140051f58  movzx   eax, [rsp+0F8h+var_3C]
0x140051f60  add     eax, 8
0x140051f63  cmp     r12d, eax
0x140051f66  jnb     short loc_140051F79
0x140051f68  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051f70  mov     ebx, [rsp+0F8h+var_B8]
0x140051f74  jmp     loc_140052368
0x140051f79  mov     edx, 50h ; 'P'
0x140051f7e  lea     ecx, [rdx+11h]
0x140051f81  mov     r8d, 71646641h
0x140051f87  call    cs:__imp_ExAllocatePool2
0x140051f8e  nop     dword ptr [rax+rax+00h]
0x140051f93  mov     rsi, rax
0x140051f96  mov     [rsp+0F8h+var_68], rax
0x140051f9e  movzx   eax, [rsp+0F8h+var_3A]
0x140051fa6  mov     [rsp+0F8h+var_B2], ax
0x140051fab  mov     [rsp+0F8h+var_88], ax
0x140051fb0  mov     ecx, [rsp+0F8h+var_A0]
0x140051fb4  mov     [rsi+28h], ecx
0x140051fb7  mov     r12d, 17h
0x140051fbd  cmp     ax, r12w
0x140051fc1  jnz     short loc_14005201F
0x140051fc3  cmp     [rsp+0F8h+var_3C], 1Ah
0x140051fcc  jnb     short loc_140051FDF
0x140051fce  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051fd6  mov     ebx, [rsp+0F8h+var_B8]
0x140051fda  jmp     loc_140052368
0x140051fdf  lea     rdx, [rbx+6]; Src
0x140051fe3  lea     rbx, [rsi+30h]
0x140051fe7  mov     r8d, 1Ch; Size
0x140051fed  mov     rcx, rbx; void *
0x140051ff0  cmp     [r14+40h], dil
0x140051ff4  jz      short loc_140051FFD
0x140051ff6  call    RtlCopyFromUser
0x140051ffb  jmp     short loc_140052002
0x140051ffd  call    RtlCopyVolatileMemory
0x140052002  mov     [rbx], r12w
0x140052006  lea     rcx, [rbx+8]; a
0x14005200a  call    IN6_IS_ADDR_V4MAPPED
0x14005200f  mov     [rsp+0F8h+var_B4], al
0x140052013  mov     [rsp+0F8h+var_B0], al
0x140052017  mov     r12d, 2
0x14005201d  jmp     short loc_140052072
0x14005201f  mov     r12d, 2
0x140052025  cmp     ax, r12w
0x140052029  jnz     loc_14005232A
0x14005202f  cmp     [rsp+0F8h+var_3C], 0Eh
0x140052038  jnb     short loc_14005204B
0x14005203a  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140052042  mov     ebx, [rsp+0F8h+var_B8]
0x140052046  jmp     loc_140052368
0x14005204b  lea     rdx, [rbx+6]; Src
0x14005204f  lea     rbx, [rsi+30h]
0x140052053  mov     r8d, 10h; Size
0x140052059  mov     rcx, rbx; void *
0x14005205c  cmp     [r14+40h], dil
0x140052060  jz      short loc_140052069
0x140052062  call    RtlCopyFromUser
0x140052067  jmp     short loc_14005206E
0x140052069  call    RtlCopyVolatileMemory
0x14005206e  mov     [rbx], r12w
0x140052072  cmp     [r15+120h], rdi
0x140052079  jnz     short loc_1400520A7
0x14005207b  mov     edx, 18h
0x140052080  lea     ecx, [rdx+49h]
0x140052083  mov     r8d, 71646641h
0x140052089  call    cs:__imp_ExAllocatePool2
0x140052090  nop     dword ptr [rax+rax+00h]
0x140052095  mov     rbx, rax
0x140052098  mov     [rsp+0F8h+P], rax
0x14005209d  mov     [rsp+0F8h+var_60], rax
0x1400520a5  jmp     short loc_1400520AA
0x1400520a7  mov     rbx, rdi
0x1400520aa  lea     rcx, [r15+38h]; SpinLock
0x1400520ae  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x1400520b3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400520ba  nop     dword ptr [rax+rax+00h]
0x1400520bf  test    dword ptr [r15+8], 800h
0x1400520c7  jz      short loc_1400520E4
0x1400520c9  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400520ce  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400520d5  nop     dword ptr [rax+rax+00h]
0x1400520da  mov     ebx, 0C0000120h
0x1400520df  jmp     loc_140052392
0x1400520e4  cmp     [r15+120h], rdi
0x1400520eb  jnz     short loc_1400520FC
0x1400520ed  mov     [rbx], di
0x1400520f0  mov     [r15+120h], rbx
0x1400520f7  mov     [rsp+0F8h+P], rdi
0x1400520fc  mov     r13, [r15+120h]
0x140052103  movzx   ecx, [rsp+0F8h+var_B2]
0x140052108  cmp     cx, r12w
0x14005210c  jz      short loc_140052127
0x14005210e  cmp     [rsp+0F8h+var_B4], dil
0x140052113  jnz     short loc_140052127
0x140052115  lea     r12, [r13+10h]
0x140052119  mov     ebx, 17h
0x14005211e  lea     rax, NPI_MS_IPV6_MODULEID
0x140052125  jmp     short loc_140052137
0x140052127  lea     r12, [r13+8]
0x14005212b  mov     ebx, 2
0x140052130  lea     rax, NPI_MS_IPV4_MODULEID
0x140052137  mov     [rsp+0F8h+var_A8], rax
0x14005213c  cmp     [r12], rdi
0x140052140  jnz     loc_1400521C8
0x140052146  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005214b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052152  nop     dword ptr [rax+rax+00h]
0x140052157  mov     eax, 17h
0x14005215c  cmp     bx, ax
0x14005215f  mov     rax, r15
0x140052162  jnz     short loc_140052168
0x140052164  or      rax, 1
0x140052168  lea     rcx, [rsp+0F8h+var_98]
0x14005216d  mov     [rsp+0F8h+var_D0], rcx
0x140052172  mov     [rsp+0F8h+var_D8], rax
0x140052177  xor     r9d, r9d
0x14005217a  lea     r8, AfdNsiRouteChangeCallback
0x140052181  lea     edx, [r9+10h]
0x140052185  mov     rcx, [rsp+0F8h+var_A8]
0x14005218a  call    cs:__imp_NsiRegisterChangeNotification
0x140052191  nop     dword ptr [rax+rax+00h]
0x140052196  mov     ebx, eax
0x140052198  test    eax, eax
0x14005219a  js      loc_140052368
0x1400521a0  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x1400521a5  lea     rcx, [r15+38h]; SpinLock
0x1400521a9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400521b0  nop     dword ptr [rax+rax+00h]
0x1400521b5  test    dword ptr [r15+8], 800h
0x1400521bd  jnz     loc_1400520C9
0x1400521c3  movzx   ecx, [rsp+0F8h+var_B2]
0x1400521c8  movzx   eax, word ptr [r13+0]
0x1400521cd  test    ax, ax
0x1400521d0  jnz     loc_14005225D
0x1400521d6  mov     [r13+0], cx
0x1400521db  cmp     [r12], rdi
0x1400521df  jnz     short loc_1400521EF
0x1400521e1  mov     rax, [rsp+0F8h+var_98]
0x1400521e6  mov     [r12], rax
0x1400521ea  mov     [rsp+0F8h+var_98], rdi
0x1400521ef  mov     eax, [r15+48h]
0x1400521f3  btr     eax, 0Bh
0x1400521f7  mov     [r15+48h], eax
0x1400521fb  lea     rax, AfdCleanupRouteChange
0x140052202  mov     [rsi+10h], rax
0x140052206  mov     [rsi+18h], rdi
0x14005220a  mov     [rsi+20h], rdi
0x14005220e  lea     rax, [r15+128h]
0x140052215  mov     rcx, [rax+8]
0x140052219  cmp     [rcx], rax
0x14005221c  jnz     loc_140052323
0x140052222  mov     [rsi], rax
0x140052225  mov     [rsi+8], rcx
0x140052229  mov     [rcx], rsi
0x14005222c  mov     [rax+8], rsi
0x140052230  mov     eax, [r15+8]
0x140052234  test    al, 10h
0x140052236  jz      short loc_14005227C
0x140052238  test    byte ptr [rsp+0F8h+var_9C], 2
0x14005223d  jnz     short loc_14005227C
0x14005223f  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x140052244  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005224b  nop     dword ptr [rax+rax+00h]
0x140052250  mov     ebx, 0C00000A3h
0x140052255  mov     rsi, rdi
0x140052258  jmp     loc_140052368
0x14005225d  cmp     ax, cx
0x140052260  jz      loc_1400521DB
0x140052266  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005226b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052272  nop     dword ptr [rax+rax+00h]
0x140052277  jmp     loc_140051EE4
0x14005227c  mov     [rsi+20h], r14
0x140052280  mov     [r14+78h], rsi
0x140052284  lea     rax, AfdCancelRouteChange
0x14005228b  xchg    rax, [r14+68h]
0x14005228f  cmp     [r14+44h], dil
0x140052293  jz      short loc_1400522BF
0x140052295  mov     rax, rdi
0x140052298  xchg    rax, [r14+68h]
0x14005229c  test    rax, rax
0x14005229f  jz      short loc_1400522BF
0x1400522a1  mov     rax, [rsi]
0x1400522a4  cmp     [rax+8], rsi
0x1400522a8  jnz     short loc_140052323
0x1400522aa  mov     rcx, [rsi+8]
0x1400522ae  cmp     [rcx], rsi
0x1400522b1  jnz     short loc_140052323
0x1400522b3  mov     [rcx], rax
0x1400522b6  mov     [rax+8], rcx
0x1400522ba  jmp     loc_1400520C9
0x1400522bf  mov     rax, [r14+0B8h]
0x1400522c6  or      byte ptr [rax+3], 1
0x1400522ca  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400522cf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400522d6  nop     dword ptr [rax+rax+00h]
0x1400522db  mov     r8, [rsp+0F8h+var_98]
0x1400522e0  test    r8, r8
0x1400522e3  jz      short loc_1400522FB
0x1400522e5  mov     edx, 10h
0x1400522ea  mov     rcx, [rsp+0F8h+var_A8]
0x1400522ef  call    cs:__imp_NsiDeregisterChangeNotification
0x1400522f6  nop     dword ptr [rax+rax+00h]
0x1400522fb  mov     rax, [rsp+0F8h+P]
0x140052300  test    rax, rax
0x140052303  jz      short loc_140052319
0x140052305  mov     edx, 71646641h; Tag
0x14005230a  mov     rcx, rax; P
  ... truncated ...
```
