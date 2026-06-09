# AfdRoutingInterfaceChange

- ea: `0x140051d50`
- end: `0x140052396`
- name: `AfdRoutingInterfaceChange`
- size: `1606`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140001bb4`
- `0x14002fd5c`
- `0x1400309d0`
- `0x1400445b8`
- `0x140051d50`
- `0x1400726a0`
- `0x1400726d0`
- `0x1400930cc`
- `0x140093104`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005235a`
- `ntoskrnl!IofCompleteRequest` at `0x14005235a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005202e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400520ab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400521a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400521cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005222f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005202e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400520ab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400521a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400521cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005222f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052013`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052109`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052013`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052109`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005226d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005231f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005233d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005226d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005231f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005233d`
- `ntoskrnl!ExAllocatePool2` at `0x140051ee7`
- `ntoskrnl!ExAllocatePool2` at `0x140051fe9`
- `ntoskrnl!ExAllocatePool2` at `0x140051ee7`
- `ntoskrnl!ExAllocatePool2` at `0x140051fe9`
- `ntoskrnl!IoIs32bitProcess` at `0x140051e2b`
- `ntoskrnl!IoIs32bitProcess` at `0x140051e2b`
- `NETIO!NsiDeregisterChangeNotification` at `0x14005224f`
- `NETIO!NsiDeregisterChangeNotification` at `0x140052306`
- `NETIO!NsiDeregisterChangeNotification` at `0x14005224f`
- `NETIO!NsiDeregisterChangeNotification` at `0x140052306`
- `NETIO!NsiRegisterChangeNotification` at `0x1400520ea`
- `NETIO!NsiRegisterChangeNotification` at `0x1400520ea`

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
0x140051d50  mov     r11, rsp
0x140051d53  mov     [r11+18h], rbx
0x140051d57  mov     [r11+20h], rsi
0x140051d5b  push    rdi
0x140051d5c  push    r12
0x140051d5e  push    r13
0x140051d60  push    r14
0x140051d62  push    r15
0x140051d64  sub     rsp, 0D0h
0x140051d6b  mov     rax, cs:__security_cookie
0x140051d72  xor     rax, rsp
0x140051d75  mov     [rsp+0F8h+var_30], rax
0x140051d7d  mov     r8, rdx
0x140051d80  mov     r14, rcx
0x140051d83  mov     [rsp+0F8h+var_50], rcx
0x140051d8b  xor     eax, eax
0x140051d8d  mov     [r11-40h], rax
0x140051d91  mov     [r11-38h], eax
0x140051d95  xor     edi, edi
0x140051d97  mov     esi, edi
0x140051d99  mov     [r11-68h], rdi
0x140051d9d  mov     [rsp+0F8h+P], rax
0x140051da2  mov     [r11-60h], rax
0x140051da6  xorps   xmm0, xmm0
0x140051da9  movups  xmmword ptr [rsp+0F8h+LockHandle.LockQueue.Next], xmm0
0x140051dae  mov     [r11-70h], rax
0x140051db2  mov     [rsp+0F8h+var_98], rdi
0x140051db7  mov     [rsp+0F8h+var_A8], rax
0x140051dbc  mov     [rsp+0F8h+var_A0], edi
0x140051dc0  lea     r13, [rdx+10h]
0x140051dc4  lea     r12, [rcx+18h]
0x140051dc8  lea     rbx, [rdx+30h]
0x140051dcc  test    byte ptr cs:xmmword_1400875E0+2, 1
0x140051dd3  jz      short loc_140051E02
0x140051dd5  mov     r9, [rbx]
0x140051dd8  lea     edx, [rax+0Fh]
0x140051ddb  mov     ecx, 410h
0x140051de0  mov     eax, [r8+8]
0x140051de4  mov     [rsp+0F8h+var_C8], eax
0x140051de8  mov     eax, [r13+0]
0x140051dec  mov     dword ptr [rsp+0F8h+var_D0], eax
0x140051df0  mov     rax, [r12]
0x140051df4  mov     [rsp+0F8h+var_D8], rax
0x140051df9  mov     r9, [r9+18h]
0x140051dfd  call    WPP_SF_qqll
0x140051e02  mov     rax, [rbx]
0x140051e05  mov     r15, [rax+18h]
0x140051e09  mov     [rsp+0F8h+var_48], r15
0x140051e11  lea     rdx, [rsp+0F8h+var_A0]
0x140051e16  mov     rcx, r15
0x140051e19  call    AfdQueryCompartmentId
0x140051e1e  mov     ebx, eax
0x140051e20  test    eax, eax
0x140051e22  js      loc_1400522C8
0x140051e28  mov     rcx, r14; Irp
0x140051e2b  call    cs:__imp_IoIs32bitProcess
0x140051e32  nop     dword ptr [rax+rax+00h]
0x140051e37  mov     ecx, [r13+0]
0x140051e3b  test    al, al
0x140051e3d  jz      short loc_140051E5E
0x140051e3f  cmp     ecx, 18h
0x140051e42  jnb     short loc_140051E4E
0x140051e44  mov     ebx, 0C000000Dh
0x140051e49  jmp     loc_1400522D0
0x140051e4e  mov     rax, [r12]
0x140051e52  mov     ebx, [rax+4]
0x140051e55  mov     r12d, [rax+8]
0x140051e59  mov     eax, [rax+10h]
0x140051e5c  jmp     short loc_140051E72
0x140051e5e  cmp     ecx, 20h ; ' '
0x140051e61  jb      short loc_140051E44
0x140051e63  mov     rax, [r12]
0x140051e67  mov     rbx, [rax+8]
0x140051e6b  mov     r12d, [rax+10h]
0x140051e6f  mov     eax, [rax+18h]
0x140051e72  mov     [rsp+0F8h+var_9C], eax
0x140051e76  mov     [rsp+0F8h+var_B4], dil
0x140051e7b  mov     [rsp+0F8h+var_B8], edi
0x140051e7f  mov     r8d, 0Ch; Size
0x140051e85  cmp     r12d, r8d
0x140051e88  jnb     short loc_140051E9B
0x140051e8a  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051e92  mov     ebx, [rsp+0F8h+var_B8]
0x140051e96  jmp     loc_1400522C8
0x140051e9b  mov     rdx, rbx; Src
0x140051e9e  lea     rcx, [rsp+0F8h+var_40]; void *
0x140051ea6  cmp     [r14+40h], dil
0x140051eaa  jz      short loc_140051EB3
0x140051eac  call    RtlCopyFromUser
0x140051eb1  jmp     short loc_140051EB8
0x140051eb3  call    RtlCopyVolatileMemory
0x140051eb8  movzx   eax, [rsp+0F8h+var_3C]
0x140051ec0  add     eax, 8
0x140051ec3  cmp     r12d, eax
0x140051ec6  jnb     short loc_140051ED9
0x140051ec8  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051ed0  mov     ebx, [rsp+0F8h+var_B8]
0x140051ed4  jmp     loc_1400522C8
0x140051ed9  mov     edx, 50h ; 'P'
0x140051ede  lea     ecx, [rdx+11h]
0x140051ee1  mov     r8d, 71646641h
0x140051ee7  call    cs:__imp_ExAllocatePool2
0x140051eee  nop     dword ptr [rax+rax+00h]
0x140051ef3  mov     rsi, rax
0x140051ef6  mov     [rsp+0F8h+var_68], rax
0x140051efe  movzx   eax, [rsp+0F8h+var_3A]
0x140051f06  mov     [rsp+0F8h+var_B2], ax
0x140051f0b  mov     [rsp+0F8h+var_88], ax
0x140051f10  mov     ecx, [rsp+0F8h+var_A0]
0x140051f14  mov     [rsi+28h], ecx
0x140051f17  mov     r12d, 17h
0x140051f1d  cmp     ax, r12w
0x140051f21  jnz     short loc_140051F7F
0x140051f23  cmp     [rsp+0F8h+var_3C], 1Ah
0x140051f2c  jnb     short loc_140051F3F
0x140051f2e  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051f36  mov     ebx, [rsp+0F8h+var_B8]
0x140051f3a  jmp     loc_1400522C8
0x140051f3f  lea     rdx, [rbx+6]; Src
0x140051f43  lea     rbx, [rsi+30h]
0x140051f47  mov     r8d, 1Ch; Size
0x140051f4d  mov     rcx, rbx; void *
0x140051f50  cmp     [r14+40h], dil
0x140051f54  jz      short loc_140051F5D
0x140051f56  call    RtlCopyFromUser
0x140051f5b  jmp     short loc_140051F62
0x140051f5d  call    RtlCopyVolatileMemory
0x140051f62  mov     [rbx], r12w
0x140051f66  lea     rcx, [rbx+8]; a
0x140051f6a  call    IN6_IS_ADDR_V4MAPPED
0x140051f6f  mov     [rsp+0F8h+var_B4], al
0x140051f73  mov     [rsp+0F8h+var_B0], al
0x140051f77  mov     r12d, 2
0x140051f7d  jmp     short loc_140051FD2
0x140051f7f  mov     r12d, 2
0x140051f85  cmp     ax, r12w
0x140051f89  jnz     loc_14005228A
0x140051f8f  cmp     [rsp+0F8h+var_3C], 0Eh
0x140051f98  jnb     short loc_140051FAB
0x140051f9a  mov     [rsp+0F8h+var_B8], 0C000000Dh
0x140051fa2  mov     ebx, [rsp+0F8h+var_B8]
0x140051fa6  jmp     loc_1400522C8
0x140051fab  lea     rdx, [rbx+6]; Src
0x140051faf  lea     rbx, [rsi+30h]
0x140051fb3  mov     r8d, 10h; Size
0x140051fb9  mov     rcx, rbx; void *
0x140051fbc  cmp     [r14+40h], dil
0x140051fc0  jz      short loc_140051FC9
0x140051fc2  call    RtlCopyFromUser
0x140051fc7  jmp     short loc_140051FCE
0x140051fc9  call    RtlCopyVolatileMemory
0x140051fce  mov     [rbx], r12w
0x140051fd2  cmp     [r15+120h], rdi
0x140051fd9  jnz     short loc_140052007
0x140051fdb  mov     edx, 18h
0x140051fe0  lea     ecx, [rdx+49h]
0x140051fe3  mov     r8d, 71646641h
0x140051fe9  call    cs:__imp_ExAllocatePool2
0x140051ff0  nop     dword ptr [rax+rax+00h]
0x140051ff5  mov     rbx, rax
0x140051ff8  mov     [rsp+0F8h+P], rax
0x140051ffd  mov     [rsp+0F8h+var_60], rax
0x140052005  jmp     short loc_14005200A
0x140052007  mov     rbx, rdi
0x14005200a  lea     rcx, [r15+38h]; SpinLock
0x14005200e  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x140052013  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005201a  nop     dword ptr [rax+rax+00h]
0x14005201f  test    dword ptr [r15+8], 800h
0x140052027  jz      short loc_140052044
0x140052029  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005202e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052035  nop     dword ptr [rax+rax+00h]
0x14005203a  mov     ebx, 0C0000120h
0x14005203f  jmp     loc_1400522F2
0x140052044  cmp     [r15+120h], rdi
0x14005204b  jnz     short loc_14005205C
0x14005204d  mov     [rbx], di
0x140052050  mov     [r15+120h], rbx
0x140052057  mov     [rsp+0F8h+P], rdi
0x14005205c  mov     r13, [r15+120h]
0x140052063  movzx   ecx, [rsp+0F8h+var_B2]
0x140052068  cmp     cx, r12w
0x14005206c  jz      short loc_140052087
0x14005206e  cmp     [rsp+0F8h+var_B4], dil
0x140052073  jnz     short loc_140052087
0x140052075  lea     r12, [r13+10h]
0x140052079  mov     ebx, 17h
0x14005207e  lea     rax, NPI_MS_IPV6_MODULEID
0x140052085  jmp     short loc_140052097
0x140052087  lea     r12, [r13+8]
0x14005208b  mov     ebx, 2
0x140052090  lea     rax, NPI_MS_IPV4_MODULEID
0x140052097  mov     [rsp+0F8h+var_A8], rax
0x14005209c  cmp     [r12], rdi
0x1400520a0  jnz     loc_140052128
0x1400520a6  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400520ab  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400520b2  nop     dword ptr [rax+rax+00h]
0x1400520b7  mov     eax, 17h
0x1400520bc  cmp     bx, ax
0x1400520bf  mov     rax, r15
0x1400520c2  jnz     short loc_1400520C8
0x1400520c4  or      rax, 1
0x1400520c8  lea     rcx, [rsp+0F8h+var_98]
0x1400520cd  mov     [rsp+0F8h+var_D0], rcx
0x1400520d2  mov     [rsp+0F8h+var_D8], rax
0x1400520d7  xor     r9d, r9d
0x1400520da  lea     r8, AfdNsiRouteChangeCallback
0x1400520e1  lea     edx, [r9+10h]
0x1400520e5  mov     rcx, [rsp+0F8h+var_A8]
0x1400520ea  call    cs:__imp_NsiRegisterChangeNotification
0x1400520f1  nop     dword ptr [rax+rax+00h]
0x1400520f6  mov     ebx, eax
0x1400520f8  test    eax, eax
0x1400520fa  js      loc_1400522C8
0x140052100  lea     rdx, [rsp+0F8h+LockHandle]; LockHandle
0x140052105  lea     rcx, [r15+38h]; SpinLock
0x140052109  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140052110  nop     dword ptr [rax+rax+00h]
0x140052115  test    dword ptr [r15+8], 800h
0x14005211d  jnz     loc_140052029
0x140052123  movzx   ecx, [rsp+0F8h+var_B2]
0x140052128  movzx   eax, word ptr [r13+0]
0x14005212d  test    ax, ax
0x140052130  jnz     loc_1400521BD
0x140052136  mov     [r13+0], cx
0x14005213b  cmp     [r12], rdi
0x14005213f  jnz     short loc_14005214F
0x140052141  mov     rax, [rsp+0F8h+var_98]
0x140052146  mov     [r12], rax
0x14005214a  mov     [rsp+0F8h+var_98], rdi
0x14005214f  mov     eax, [r15+48h]
0x140052153  btr     eax, 0Bh
0x140052157  mov     [r15+48h], eax
0x14005215b  lea     rax, AfdCleanupRouteChange
0x140052162  mov     [rsi+10h], rax
0x140052166  mov     [rsi+18h], rdi
0x14005216a  mov     [rsi+20h], rdi
0x14005216e  lea     rax, [r15+128h]
0x140052175  mov     rcx, [rax+8]
0x140052179  cmp     [rcx], rax
0x14005217c  jnz     loc_140052283
0x140052182  mov     [rsi], rax
0x140052185  mov     [rsi+8], rcx
0x140052189  mov     [rcx], rsi
0x14005218c  mov     [rax+8], rsi
0x140052190  mov     eax, [r15+8]
0x140052194  test    al, 10h
0x140052196  jz      short loc_1400521DC
0x140052198  test    byte ptr [rsp+0F8h+var_9C], 2
0x14005219d  jnz     short loc_1400521DC
0x14005219f  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400521a4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400521ab  nop     dword ptr [rax+rax+00h]
0x1400521b0  mov     ebx, 0C00000A3h
0x1400521b5  mov     rsi, rdi
0x1400521b8  jmp     loc_1400522C8
0x1400521bd  cmp     ax, cx
0x1400521c0  jz      loc_14005213B
0x1400521c6  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x1400521cb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400521d2  nop     dword ptr [rax+rax+00h]
0x1400521d7  jmp     loc_140051E44
0x1400521dc  mov     [rsi+20h], r14
0x1400521e0  mov     [r14+78h], rsi
0x1400521e4  lea     rax, AfdCancelRouteChange
0x1400521eb  xchg    rax, [r14+68h]
0x1400521ef  cmp     [r14+44h], dil
0x1400521f3  jz      short loc_14005221F
0x1400521f5  mov     rax, rdi
0x1400521f8  xchg    rax, [r14+68h]
0x1400521fc  test    rax, rax
0x1400521ff  jz      short loc_14005221F
0x140052201  mov     rax, [rsi]
0x140052204  cmp     [rax+8], rsi
0x140052208  jnz     short loc_140052283
0x14005220a  mov     rcx, [rsi+8]
0x14005220e  cmp     [rcx], rsi
0x140052211  jnz     short loc_140052283
0x140052213  mov     [rcx], rax
0x140052216  mov     [rax+8], rcx
0x14005221a  jmp     loc_140052029
0x14005221f  mov     rax, [r14+0B8h]
0x140052226  or      byte ptr [rax+3], 1
0x14005222a  lea     rcx, [rsp+0F8h+LockHandle]; LockHandle
0x14005222f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052236  nop     dword ptr [rax+rax+00h]
0x14005223b  mov     r8, [rsp+0F8h+var_98]
0x140052240  test    r8, r8
0x140052243  jz      short loc_14005225B
0x140052245  mov     edx, 10h
0x14005224a  mov     rcx, [rsp+0F8h+var_A8]
0x14005224f  call    cs:__imp_NsiDeregisterChangeNotification
0x140052256  nop     dword ptr [rax+rax+00h]
0x14005225b  mov     rax, [rsp+0F8h+P]
0x140052260  test    rax, rax
0x140052263  jz      short loc_140052279
0x140052265  mov     edx, 71646641h; Tag
0x14005226a  mov     rcx, rax; P
  ... truncated ...
```
