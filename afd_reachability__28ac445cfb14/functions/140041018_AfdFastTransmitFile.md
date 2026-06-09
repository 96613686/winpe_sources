# AfdFastTransmitFile

- ea: `0x140041018`
- end: `0x14004179c`
- name: `AfdFastTransmitFile`
- size: `1924`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000a870`

## callees

- `0x14000cbe0`
- `0x140012610`
- `0x14001b800`
- `0x14001c708`
- `0x14002be58`
- `0x14002fd5c`
- `0x140041018`
- `0x1400417a4`
- `0x1400445b8`
- `0x140055bbc`
- `0x1400567c0`
- `0x1400726d0`
- `0x140072780`
- `0x140072b00`
- `0x140093008`
- `0x140094274`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140041613`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140041613`
- `ntoskrnl!ExGetPreviousMode` at `0x14004129e`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412cf`
- `ntoskrnl!ExGetPreviousMode` at `0x140041315`
- `ntoskrnl!ExGetPreviousMode` at `0x14004129e`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412cf`
- `ntoskrnl!ExGetPreviousMode` at `0x140041315`
- `ntoskrnl!FsRtlMdlRead` at `0x140041440`
- `ntoskrnl!FsRtlMdlRead` at `0x140041440`
- `ntoskrnl!FsRtlCopyRead` at `0x1400413ea`
- `ntoskrnl!FsRtlCopyRead` at `0x1400413ea`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400413b0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400413b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400413fb`
- `ntoskrnl!ObfDereferenceObject` at `0x14004153f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400413fb`
- `ntoskrnl!ObfDereferenceObject` at `0x14004153f`
- `ntoskrnl!IofCallDriver` at `0x14004171a`
- `ntoskrnl!IofCallDriver` at `0x14004171a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400411cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400415a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400411cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400415a2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400411a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041586`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400411a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041586`
- `ntoskrnl!IoFileObjectType` at `0x14004133e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140041352`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140041352`

## pseudocode

```c
char __fastcall AfdFastTransmitFile(__int64 a1, __int64 a2, struct _IO_STATUS_BLOCK *a3)
{
  int v5; // edx
  __int64 v6; // rcx
  ULONG v7; // edx
  __int64 v8; // rdx
  __int64 v9; // r8
  ULONG_PTR v10; // rbx
  __int64 v11; // r15
  struct _FILE_OBJECT *v12; // r13
  char v13; // r12
  __int64 v14; // rsi
  SIZE_T v15; // rcx
  __int64 Buffer; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  KPROCESSOR_MODE PreviousMode; // al
  size_t v20; // r8
  void *v21; // rdx
  void *v22; // rcx
  KPROCESSOR_MODE v23; // al
  size_t v24; // r8
  void *v25; // rdx
  void *v26; // rcx
  KPROCESSOR_MODE v27; // al
  NTSTATUS v28; // eax
  __int64 v29; // rcx
  struct _DEVICE_OBJECT *DeviceObject; // rax
  bool v31; // zf
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  signed __int64 v35; // rax
  bool v36; // cc
  signed __int64 v37; // rax
  PIRP v38; // r12
  NTSTATUS v39; // r15d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v41; // rcx
  PIO_STATUS_BLOCK v42; // rax
  int v44; // [rsp+50h] [rbp-118h]
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp-110h] BYREF
  __int64 v46; // [rsp+60h] [rbp-108h] BYREF
  int v47; // [rsp+68h] [rbp-100h]
  ULONG_PTR v48; // [rsp+70h] [rbp-F8h]
  PIRP Irp; // [rsp+78h] [rbp-F0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-C8h]
  __int64 v52; // [rsp+B8h] [rbp-B0h]
  PKSPIN_LOCK SpinLock; // [rsp+C0h] [rbp-A8h]
  _QWORD v54[19]; // [rsp+D0h] [rbp-98h] BYREF
  PVOID Object; // [rsp+170h] [rbp+8h] BYREF
  PIO_STATUS_BLOCK IoStatus; // [rsp+180h] [rbp+18h]
  ULONG Length; // [rsp+188h] [rbp+20h]

  IoStatus = a3;
  memset(&LockHandle, 0, sizeof(LockHandle));
  FileOffset.QuadPart = 0;
  v46 = 0;
  if ( (*(_DWORD *)(a1 + 8) & 0xF0000) != 0
    || *(_WORD *)a1 != 0xAFD2
    || *(_BYTE *)(a1 + 2) != 4
    || (*(_DWORD *)(a1 + 8) & 0x100) == 0 && (*(_DWORD *)(a1 + 16) & 0x200) != 0 )
  {
    return 0;
  }
  v5 = *(_DWORD *)(a2 + 60);
  if ( (v5 & 0x30) == 48 || (v5 & 0xFFFFFFC8) != 0 || (v5 & 0xFFFFFFCF) != 4 )
    return 0;
  if ( SBYTE1(xmmword_1400875E0) < 0 )
    WPP_SF_qq(1039, 55, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, a1, *(_QWORD *)(a1 + 192));
  v46 = 0;
  v6 = *(_QWORD *)(a2 + 24);
  v7 = v6 ? *(_DWORD *)(a2 + 8) : 0;
  Length = v7;
  if ( AfdMaxActiveTransmitFileCount || v6 && (!v7 || *(__int64 *)a2 < 0) )
    return 0;
  v48 = v7;
  v8 = *(unsigned int *)(a2 + 40);
  v9 = *(unsigned int *)(a2 + 56);
  v10 = v8 + v9 + v48;
  v44 = v8 + v9 + v48;
  if ( v10 > (unsigned int)AfdMaxFastTransmit )
    return 0;
  v47 = v8 + v9 + v48;
  if ( (unsigned int)v10 > AfdMaxFastCopyTransmit && (!(_DWORD)v8 || (_DWORD)v9) )
    return 0;
  if ( *(_DWORD *)(a2 + 12) || (unsigned int)v8 > 0x1000 )
    return 0;
  SpinLock = (PKSPIN_LOCK)(a1 + 56);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  v11 = *(_QWORD *)(a1 + 192);
  v52 = v11;
  if ( !v11 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 0;
  }
  v12 = 0;
  if ( (unsigned __int8)AfdShouldSendBlock(a1, v11, (unsigned int)v10) )
  {
    v13 = 0;
    v14 = 0;
    AfdNotifySockIndicateEventsUnlock(a1, &LockHandle, 0);
LABEL_66:
    LODWORD(v10) = v44;
    goto LABEL_67;
  }
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v11 + 48)) <= 1 )
    __fastfail(0xEu);
  AfdNotifySockIndicateEventsUnlock(a1, &LockHandle, 0);
  LOBYTE(Object) = 1;
  if ( (unsigned int)v10 <= AfdMaxFastCopyTransmit )
    v15 = (unsigned int)v10;
  else
    v15 = *(unsigned int *)(a2 + 40);
  if ( (unsigned int)v15 < 0x58 )
    v15 = 88;
  Buffer = AfdGetBuffer(v15);
  v14 = Buffer;
  v51 = Buffer;
  if ( !Buffer )
    goto LABEL_91;
  Irp = *(PIRP *)(Buffer + 104);
  Irp->Tail.Overlay.Thread = 0;
  *(_QWORD *)(Buffer + 8) = 0;
  if ( *(_DWORD *)(a2 + 40) )
  {
    PreviousMode = ExGetPreviousMode();
    v20 = *(unsigned int *)(a2 + 40);
    v21 = *(void **)(a2 + 32);
    v22 = *(void **)(v14 + 112);
    if ( PreviousMode )
      RtlCopyFromUser(v22, v21, v20);
    else
      RtlCopyVolatileMemory(v22, v21, v20);
  }
  if ( *(_DWORD *)(a2 + 56) )
  {
    v23 = ExGetPreviousMode();
    v24 = *(unsigned int *)(a2 + 56);
    v25 = *(void **)(a2 + 48);
    v26 = (void *)(*(unsigned int *)(a2 + 40) + *(_QWORD *)(v14 + 112) + v48);
    if ( v23 )
      RtlCopyFromUser(v26, v25, v24);
    else
      RtlCopyVolatileMemory(v26, v25, v24);
  }
  if ( *(_QWORD *)(a2 + 24) )
  {
    v27 = ExGetPreviousMode();
    Object = 0;
    v28 = ObReferenceObjectByHandle(*(HANDLE *)(a2 + 24), 1u, (POBJECT_TYPE)IoFileObjectType, v27, &Object, 0);
    v12 = (struct _FILE_OBJECT *)Object;
    if ( v28 < 0 || (*((_DWORD *)Object + 20) & 0x40) == 0 )
      goto LABEL_65;
    v29 = *(_QWORD *)a2;
    FileOffset = *(union _LARGE_INTEGER *)a2;
    if ( (*((_DWORD *)Object + 20) & 2) != 0 && !v29 )
      FileOffset = *(union _LARGE_INTEGER *)((char *)Object + 104);
    if ( (unsigned int)v10 > AfdMaxFastCopyTransmit )
    {
      if ( !(unsigned __int8)FsRtlMdlRead(Object, &FileOffset, Length, 0, &v46, IoStatus) )
        goto LABEL_65;
      *(_QWORD *)(v14 + 8) = v12;
      *(union _LARGE_INTEGER *)(v14 + 16) = FileOffset;
      if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
      {
        v32 = *(_DWORD *)(a2 + 60) & 0x30;
        if ( v32 == 32 || !v32 && AfdDefaultTransmitWorker == 32 )
          Irp = 0;
      }
LABEL_58:
      if ( IoStatus->Information >= v48 )
        goto LABEL_59;
LABEL_65:
      v13 = 1;
      goto LABEL_66;
    }
    v10 = *(unsigned int *)(a2 + 40) + *(_QWORD *)(v14 + 112);
    DeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
    LOBYTE(v10) = FsRtlCopyRead(v12, &FileOffset, Length, 0, 0, (PVOID)v10, IoStatus, DeviceObject);
    ObfDereferenceObject(v12);
    v12 = 0;
    v31 = (_BYTE)v10 == 0;
    LODWORD(v10) = v44;
    if ( !v31 )
      goto LABEL_58;
LABEL_91:
    v13 = 1;
LABEL_67:
    if ( v46 && (int)AfdMdlReadComplete(v12) < 0 )
    {
      *(_QWORD *)(v14 + 48) = v11;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v11 + 48)) <= 1 )
        __fastfail(0xEu);
      AfdLRMdlReadComplete((PSLIST_ENTRY)v14);
      v14 = 0;
      v12 = 0;
    }
    if ( v12 )
      ObfDereferenceObject(v12);
    if ( v14 )
    {
      **(_QWORD **)(v14 + 56) = 0;
      *(_DWORD *)(*(_QWORD *)(v14 + 56) + 40LL) = *(_DWORD *)(v14 + 72);
      AfdReturnBuffer((unsigned __int16 *)v14, *(PEPROCESS *)(v11 + 32));
    }
    if ( v13 )
    {
      KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
      *(_DWORD *)(v11 + 120) -= v10;
      --*(_DWORD *)(v11 + 124);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v35 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v11 + 48), 0xFFFFFFFFFFFFFFFFuLL);
      v36 = v35 <= 1;
      v37 = v35 - 1;
      if ( v36 )
      {
        if ( v37 )
          __fastfail(0xEu);
        AfdCloseConnection(v11);
      }
    }
    return 0;
  }
LABEL_59:
  v33 = *(_QWORD *)(v14 + 56);
  if ( v46 )
  {
    *(_DWORD *)(v33 + 40) = *(_DWORD *)(a2 + 40);
    **(_QWORD **)(v14 + 56) = v46;
  }
  else
  {
    *(_DWORD *)(v33 + 40) = v10;
  }
  v34 = *(unsigned __int8 *)(a1 + 2);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 368), v34, 0) )
    goto LABEL_65;
  if ( *(_BYTE *)(a1 + 2) != 4 )
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 368), 0);
    goto LABEL_65;
  }
  *(_QWORD *)(v14 + 48) = v11;
  v38 = Irp;
  if ( !Irp )
  {
    v38 = IoBuildDeviceIoControlRequest(3u, *(PDEVICE_OBJECT *)(v11 + 24), 0, 0, 0, 0, 1u, 0, &AfdDontCareIoStatus);
    if ( !v38 )
      v38 = *(PIRP *)(v14 + 104);
  }
  if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
    WPP_SF_qqql(v34, v17, v18, a1, v12, v14, v10);
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    memset(v54, 0, 0x58u);
    v54[0] = AfdTLRestartFastTransmitSend;
    v54[2] = v14;
    v54[4] = *(_QWORD *)(v14 + 56);
    v10 = (unsigned int)v10;
    v54[6] = (unsigned int)v10;
    v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v11 + 24) + 24LL))(*(_QWORD *)(v11 + 16), v54);
    if ( v39 != 259 )
      AfdTLRestartFastTransmitSend((PVOID)v14);
  }
  else
  {
    CurrentStackLocation = v38->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartFastTransmitSend;
    CurrentStackLocation[-1].Context = (PVOID)v14;
    CurrentStackLocation[-1].Control = -32;
    v41 = v38->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&v41[-1].MajorFunction = 1807;
    v41[-1].DeviceObject = *(PDEVICE_OBJECT *)(v11 + 24);
    v41[-1].FileObject = *(PFILE_OBJECT *)(v11 + 16);
    *(&v41[-1].Parameters.Read.Length + 1) = 0;
    v41[-1].Parameters.Read.Length = v10;
    v38->MdlAddress = *(PMDL *)(v14 + 56);
    v39 = IofCallDriver(*(PDEVICE_OBJECT *)(v11 + 24), v38);
    v10 = (unsigned int)v10;
  }
  _InterlockedExchange((volatile __int32 *)(a1 + 368), 0);
  if ( v39 >= 0 )
  {
    v42 = IoStatus;
    IoStatus->Information = v10;
    v42->Status = 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140041018  mov     [rsp+arg_10], r8
0x14004101d  push    rbx
0x14004101e  push    rsi
0x14004101f  push    rdi
0x140041020  push    r12
0x140041022  push    r13
0x140041024  push    r14
0x140041026  push    r15
0x140041028  sub     rsp, 130h
0x14004102f  mov     r12, rdx
0x140041032  mov     r14, rcx
0x140041035  xorps   xmm0, xmm0
0x140041038  xor     eax, eax
0x14004103a  movups  xmmword ptr [rsp+168h+LockHandle.LockQueue.Next], xmm0
0x140041042  mov     qword ptr [rsp+168h+LockHandle.OldIrql], rax
0x14004104a  xor     edi, edi
0x14004104c  mov     qword ptr [rsp+168h+FileOffset], rdi
0x140041051  mov     [rsp+168h+var_108], rdi
0x140041056  mov     eax, [rcx+8]
0x140041059  test    eax, 0F0000h
0x14004105e  jnz     loc_140041786
0x140041064  mov     eax, 0AFD2h
0x140041069  cmp     [rcx], ax
0x14004106c  jnz     loc_140041786
0x140041072  cmp     byte ptr [rcx+2], 4
0x140041076  jnz     loc_140041786
0x14004107c  mov     eax, [rcx+8]
0x14004107f  bt      eax, 8
0x140041083  jb      short loc_140041092
0x140041085  test    dword ptr [rcx+10h], 200h
0x14004108c  jnz     loc_140041786
0x140041092  mov     edx, [rdx+3Ch]
0x140041095  mov     eax, edx
0x140041097  and     eax, 30h
0x14004109a  cmp     al, 30h ; '0'
0x14004109c  setnz   cl
0x14004109f  test    edx, 0FFFFFFC8h
0x1400410a5  setz    al
0x1400410a8  test    al, cl
0x1400410aa  jz      loc_140041786
0x1400410b0  and     edx, 0FFFFFFCFh
0x1400410b3  cmp     edx, 4
0x1400410b6  jnz     loc_140041786
0x1400410bc  mov     al, byte ptr cs:xmmword_1400875E0+1
0x1400410c2  test    al, al
0x1400410c4  jns     short loc_1400410EB
0x1400410c6  mov     edx, 37h ; '7'
0x1400410cb  mov     ecx, 40Fh
0x1400410d0  mov     rax, [r14+0C0h]
0x1400410d7  mov     [rsp+168h+Object], rax
0x1400410dc  mov     r9, r14
0x1400410df  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x1400410e6  call    WPP_SF_qq
0x1400410eb  mov     [rsp+168h+var_108], rdi
0x1400410f0  mov     rcx, [r12+18h]
0x1400410f5  test    rcx, rcx
0x1400410f8  jz      short loc_140041101
0x1400410fa  mov     edx, [r12+8]
0x1400410ff  jmp     short loc_140041103
0x140041101  mov     edx, edi
0x140041103  mov     [rsp+168h+Length], edx
0x14004110a  cmp     cs:AfdMaxActiveTransmitFileCount, edi
0x140041110  jnz     loc_140041786
0x140041116  test    rcx, rcx
0x140041119  jz      short loc_14004112D
0x14004111b  test    edx, edx
0x14004111d  jz      loc_140041786
0x140041123  cmp     [r12], rdi
0x140041127  jl      loc_140041786
0x14004112d  mov     eax, edx
0x14004112f  mov     [rsp+168h+var_F8], rax
0x140041134  mov     edx, [r12+28h]
0x140041139  mov     r8d, [r12+38h]
0x14004113e  lea     rbx, [r8+rax]
0x140041142  add     rbx, rdx
0x140041145  mov     [rsp+168h+var_118], rbx
0x14004114a  mov     eax, cs:AfdMaxFastTransmit
0x140041150  cmp     rbx, rax
0x140041153  ja      loc_140041786
0x140041159  mov     [rsp+168h+var_100], ebx
0x14004115d  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x140041163  jbe     short loc_140041176
0x140041165  test    edx, edx
0x140041167  jz      loc_140041786
0x14004116d  test    r8d, r8d
0x140041170  jnz     loc_140041786
0x140041176  cmp     [r12+0Ch], edi
0x14004117b  jnz     loc_140041786
0x140041181  cmp     edx, 1000h
0x140041187  ja      loc_140041786
0x14004118d  lea     rax, [r14+38h]
0x140041191  mov     [rsp+168h+SpinLock], rax
0x140041199  lea     rdx, [rsp+168h+LockHandle]; LockHandle
0x1400411a1  mov     rcx, rax; SpinLock
0x1400411a4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400411ab  nop     dword ptr [rax+rax+00h]
0x1400411b0  mov     r15, [r14+0C0h]
0x1400411b7  mov     [rsp+168h+var_B0], r15
0x1400411bf  test    r15, r15
0x1400411c2  jnz     short loc_1400411DD
0x1400411c4  lea     rcx, [rsp+168h+LockHandle]; LockHandle
0x1400411cc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400411d3  nop     dword ptr [rax+rax+00h]
0x1400411d8  jmp     loc_140041786
0x1400411dd  mov     r13, rdi
0x1400411e0  mov     r8d, ebx
0x1400411e3  mov     rdx, r15
0x1400411e6  mov     rcx, r14
0x1400411e9  call    AfdShouldSendBlock
0x1400411ee  test    al, al
0x1400411f0  jz      short loc_140041210
0x1400411f2  mov     r12b, dil
0x1400411f5  mov     rsi, rdi
0x1400411f8  xor     r8d, r8d
0x1400411fb  lea     rdx, [rsp+168h+LockHandle]
0x140041203  mov     rcx, r14
0x140041206  call    AfdNotifySockIndicateEventsUnlock
0x14004120b  jmp     loc_1400414EA
0x140041210  mov     eax, 1
0x140041215  lock xadd [r15+30h], rax
0x14004121b  inc     rax
0x14004121e  cmp     rax, 1
0x140041222  jg      short loc_14004122B
0x140041224  mov     ecx, 0Eh
0x140041229  int     29h; Win8: RtlFailFast(ecx)
0x14004122b  xor     r8d, r8d
0x14004122e  lea     rdx, [rsp+168h+LockHandle]
0x140041236  mov     rcx, r14
0x140041239  call    AfdNotifySockIndicateEventsUnlock
0x14004123e  mov     byte ptr [rsp+168h+arg_0], 1
0x140041246  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x14004124c  jbe     short loc_140041255
0x14004124e  mov     ecx, [r12+28h]
0x140041253  jmp     short loc_140041257
0x140041255  mov     ecx, ebx
0x140041257  mov     eax, 58h ; 'X'
0x14004125c  cmp     ecx, eax
0x14004125e  cmovb   ecx, eax; Length
0x140041261  xor     r9d, r9d
0x140041264  mov     r8, [r15+20h]
0x140041268  xor     edx, edx
0x14004126a  call    AfdGetBuffer
0x14004126f  mov     rsi, rax
0x140041272  mov     [rsp+168h+var_C8], rax
0x14004127a  test    rax, rax
0x14004127d  jz      loc_140041771
0x140041283  mov     rax, [rax+68h]
0x140041287  mov     [rsp+168h+Irp], rax
0x14004128c  mov     [rax+98h], rdi
0x140041293  mov     [rsi+8], rdi
0x140041297  cmp     [r12+28h], edi
0x14004129c  jbe     short loc_1400412C8
0x14004129e  call    cs:__imp_ExGetPreviousMode
0x1400412a5  nop     dword ptr [rax+rax+00h]
0x1400412aa  mov     r8d, [r12+28h]; Size
0x1400412af  mov     rdx, [r12+20h]; Src
0x1400412b4  mov     rcx, [rsi+70h]; void *
0x1400412b8  test    al, al
0x1400412ba  jz      short loc_1400412C3
0x1400412bc  call    RtlCopyFromUser
0x1400412c1  jmp     short loc_1400412C8
0x1400412c3  call    RtlCopyVolatileMemory
0x1400412c8  cmp     [r12+38h], edi
0x1400412cd  jbe     short loc_14004130A
0x1400412cf  call    cs:__imp_ExGetPreviousMode
0x1400412d6  nop     dword ptr [rax+rax+00h]
0x1400412db  mov     r8d, [r12+38h]; Size
0x1400412e0  mov     rdx, [r12+30h]; Src
0x1400412e5  mov     ecx, [r12+28h]
0x1400412ea  mov     r9, [rsi+70h]
0x1400412ee  add     r9, rcx
0x1400412f1  mov     rcx, [rsp+168h+var_F8]
0x1400412f6  add     rcx, r9; void *
0x1400412f9  test    al, al
0x1400412fb  jz      short loc_140041304
0x1400412fd  call    RtlCopyFromUser
0x140041302  jmp     short loc_14004130A
0x140041304  call    RtlCopyVolatileMemory
0x140041309  nop
0x14004130a  cmp     [r12+18h], rdi
0x14004130f  jz      loc_14004149D
0x140041315  call    cs:__imp_ExGetPreviousMode
0x14004131c  nop     dword ptr [rax+rax+00h]
0x140041321  mov     [rsp+168h+arg_0], rdi
0x140041329  mov     [rsp+168h+HandleInformation], rdi; HandleInformation
0x14004132e  lea     rcx, [rsp+168h+arg_0]
0x140041336  mov     [rsp+168h+Object], rcx; Object
0x14004133b  mov     r9b, al; AccessMode
0x14004133e  mov     r8, cs:__imp_IoFileObjectType
0x140041345  mov     r8, [r8]; ObjectType
0x140041348  mov     edx, 1; DesiredAccess
0x14004134d  mov     rcx, [r12+18h]; Handle
0x140041352  call    cs:__imp_ObReferenceObjectByHandle
0x140041359  nop     dword ptr [rax+rax+00h]
0x14004135e  mov     r13, [rsp+168h+arg_0]
0x140041366  test    eax, eax
0x140041368  js      loc_1400414E7
0x14004136e  mov     eax, [r13+50h]
0x140041372  test    al, 40h
0x140041374  jz      loc_1400414E7
0x14004137a  mov     rcx, [r12]
0x14004137e  mov     qword ptr [rsp+168h+FileOffset], rcx
0x140041383  mov     eax, [r13+50h]
0x140041387  test    al, 2
0x140041389  jz      short loc_140041399
0x14004138b  test    rcx, rcx
0x14004138e  jnz     short loc_140041399
0x140041390  mov     rax, [r13+68h]
0x140041394  mov     qword ptr [rsp+168h+FileOffset], rax
0x140041399  mov     rcx, r13; FileObject
0x14004139c  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x1400413a2  ja      short loc_140041419
0x1400413a4  mov     edx, [r12+28h]
0x1400413a9  mov     rbx, [rsi+70h]
0x1400413ad  add     rbx, rdx
0x1400413b0  call    cs:__imp_IoGetRelatedDeviceObject
0x1400413b7  nop     dword ptr [rax+rax+00h]
0x1400413bc  mov     [rsp+168h+DeviceObject], rax; DeviceObject
0x1400413c1  mov     rax, [rsp+168h+arg_10]
0x1400413c9  mov     [rsp+168h+IoStatus], rax; IoStatus
0x1400413ce  mov     [rsp+168h+HandleInformation], rbx; Buffer
0x1400413d3  mov     dword ptr [rsp+168h+Object], edi; LockKey
0x1400413d7  xor     r9d, r9d; Wait
0x1400413da  mov     r8d, [rsp+168h+Length]; Length
0x1400413e2  lea     rdx, [rsp+168h+FileOffset]; FileOffset
0x1400413e7  mov     rcx, r13; FileObject
0x1400413ea  call    cs:__imp_FsRtlCopyRead
0x1400413f1  nop     dword ptr [rax+rax+00h]
0x1400413f6  mov     bl, al
0x1400413f8  mov     rcx, r13; Object
0x1400413fb  call    cs:__imp_ObfDereferenceObject
0x140041402  nop     dword ptr [rax+rax+00h]
0x140041407  mov     r13, rdi
0x14004140a  test    bl, bl
0x14004140c  mov     rbx, [rsp+168h+var_118]
0x140041411  jz      loc_140041776
0x140041417  jmp     short loc_14004148A
0x140041419  mov     rax, [rsp+168h+arg_10]
0x140041421  mov     [rsp+168h+HandleInformation], rax
0x140041426  lea     rax, [rsp+168h+var_108]
0x14004142b  mov     [rsp+168h+Object], rax
0x140041430  xor     r9d, r9d
0x140041433  mov     r8d, [rsp+168h+Length]
0x14004143b  lea     rdx, [rsp+168h+FileOffset]
0x140041440  call    cs:__imp_FsRtlMdlRead
0x140041447  nop     dword ptr [rax+rax+00h]
0x14004144c  test    al, al
0x14004144e  jz      loc_1400414E7
0x140041454  mov     [rsi+8], r13
0x140041458  mov     rax, qword ptr [rsp+168h+FileOffset]
0x14004145d  mov     [rsi+10h], rax
0x140041461  mov     eax, [r14+8]
0x140041465  bt      eax, 8
0x140041469  jb      short loc_14004148A
0x14004146b  mov     eax, [r12+3Ch]
0x140041470  and     eax, 30h
0x140041473  cmp     eax, 20h ; ' '
0x140041476  jz      short loc_140041485
0x140041478  test    eax, eax
0x14004147a  jnz     short loc_14004148A
0x14004147c  cmp     cs:AfdDefaultTransmitWorker, 20h ; ' '
0x140041483  jnz     short loc_14004148A
0x140041485  mov     [rsp+168h+Irp], rdi
0x14004148a  mov     rax, [rsp+168h+arg_10]
0x140041492  mov     rcx, [rsp+168h+var_F8]
0x140041497  cmp     [rax+8], rcx
0x14004149b  jb      short loc_1400414E7
0x14004149d  mov     rcx, [rsi+38h]
0x1400414a1  cmp     [rsp+168h+var_108], rdi
0x1400414a6  jnz     short loc_1400414AD
0x1400414a8  mov     [rcx+28h], ebx
0x1400414ab  jmp     short loc_1400414C1
0x1400414ad  mov     eax, [r12+28h]
0x1400414b2  mov     [rcx+28h], eax
0x1400414b5  mov     rcx, [rsi+38h]
0x1400414b9  mov     rax, [rsp+168h+var_108]
0x1400414be  mov     [rcx], rax
0x1400414c1  movzx   ecx, byte ptr [r14+2]
0x1400414c6  xor     eax, eax
0x1400414c8  lock cmpxchg [r14+170h], ecx
0x1400414d1  jnz     short loc_1400414E7
0x1400414d3  cmp     byte ptr [r14+2], 4
0x1400414d8  jz      loc_1400415D7
0x1400414de  mov     eax, edi
0x1400414e0  xchg    eax, [r14+170h]
0x1400414e7  mov     r12b, 1
0x1400414ea  mov     rbx, [rsp+168h+var_118]
0x1400414ef  mov     rdx, [rsp+168h+var_108]
0x1400414f4  test    rdx, rdx
0x1400414f7  jz      short loc_140041537
0x1400414f9  lea     r8, [rsp+168h+FileOffset]
0x1400414fe  mov     rcx, r13; Object
0x140041501  call    AfdMdlReadComplete
0x140041506  test    eax, eax
0x140041508  jns     short loc_140041537
0x14004150a  mov     [rsi+30h], r15
0x14004150e  mov     eax, 1
0x140041513  lock xadd [r15+30h], rax
0x140041519  inc     rax
0x14004151c  cmp     rax, 1
  ... truncated ...
```
