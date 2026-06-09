# AfdFastTransmitFile

- ea: `0x140041038`
- end: `0x1400417bc`
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
- `0x14002fd7c`
- `0x140041038`
- `0x1400417c4`
- `0x1400445d8`
- `0x140055c5c`
- `0x140056860`
- `0x140072870`
- `0x140072920`
- `0x140072c80`
- `0x140093008`
- `0x140094274`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140041633`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140041633`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412be`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412ef`
- `ntoskrnl!ExGetPreviousMode` at `0x140041335`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412be`
- `ntoskrnl!ExGetPreviousMode` at `0x1400412ef`
- `ntoskrnl!ExGetPreviousMode` at `0x140041335`
- `ntoskrnl!FsRtlMdlRead` at `0x140041460`
- `ntoskrnl!FsRtlMdlRead` at `0x140041460`
- `ntoskrnl!FsRtlCopyRead` at `0x14004140a`
- `ntoskrnl!FsRtlCopyRead` at `0x14004140a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400413d0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400413d0`
- `ntoskrnl!ObfDereferenceObject` at `0x14004141b`
- `ntoskrnl!ObfDereferenceObject` at `0x14004155f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004141b`
- `ntoskrnl!ObfDereferenceObject` at `0x14004155f`
- `ntoskrnl!IofCallDriver` at `0x14004173a`
- `ntoskrnl!IofCallDriver` at `0x14004173a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400411ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400415c2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400411ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400415c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400411c4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400415a6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400411c4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400415a6`
- `ntoskrnl!IoFileObjectType` at `0x14004135e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140041372`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140041372`

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
    WPP_SF_qq(1039, 55, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, a1, *(_QWORD *)(a1 + 192));
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
0x140041038  mov     [rsp+arg_10], r8
0x14004103d  push    rbx
0x14004103e  push    rsi
0x14004103f  push    rdi
0x140041040  push    r12
0x140041042  push    r13
0x140041044  push    r14
0x140041046  push    r15
0x140041048  sub     rsp, 130h
0x14004104f  mov     r12, rdx
0x140041052  mov     r14, rcx
0x140041055  xorps   xmm0, xmm0
0x140041058  xor     eax, eax
0x14004105a  movups  xmmword ptr [rsp+168h+LockHandle.LockQueue.Next], xmm0
0x140041062  mov     qword ptr [rsp+168h+LockHandle.OldIrql], rax
0x14004106a  xor     edi, edi
0x14004106c  mov     qword ptr [rsp+168h+FileOffset], rdi
0x140041071  mov     [rsp+168h+var_108], rdi
0x140041076  mov     eax, [rcx+8]
0x140041079  test    eax, 0F0000h
0x14004107e  jnz     loc_1400417A6
0x140041084  mov     eax, 0AFD2h
0x140041089  cmp     [rcx], ax
0x14004108c  jnz     loc_1400417A6
0x140041092  cmp     byte ptr [rcx+2], 4
0x140041096  jnz     loc_1400417A6
0x14004109c  mov     eax, [rcx+8]
0x14004109f  bt      eax, 8
0x1400410a3  jb      short loc_1400410B2
0x1400410a5  test    dword ptr [rcx+10h], 200h
0x1400410ac  jnz     loc_1400417A6
0x1400410b2  mov     edx, [rdx+3Ch]
0x1400410b5  mov     eax, edx
0x1400410b7  and     eax, 30h
0x1400410ba  cmp     al, 30h ; '0'
0x1400410bc  setnz   cl
0x1400410bf  test    edx, 0FFFFFFC8h
0x1400410c5  setz    al
0x1400410c8  test    al, cl
0x1400410ca  jz      loc_1400417A6
0x1400410d0  and     edx, 0FFFFFFCFh
0x1400410d3  cmp     edx, 4
0x1400410d6  jnz     loc_1400417A6
0x1400410dc  mov     al, byte ptr cs:xmmword_1400875E0+1
0x1400410e2  test    al, al
0x1400410e4  jns     short loc_14004110B
0x1400410e6  mov     edx, 37h ; '7'
0x1400410eb  mov     ecx, 40Fh
0x1400410f0  mov     rax, [r14+0C0h]
0x1400410f7  mov     [rsp+168h+Object], rax
0x1400410fc  mov     r9, r14
0x1400410ff  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140041106  call    WPP_SF_qq
0x14004110b  mov     [rsp+168h+var_108], rdi
0x140041110  mov     rcx, [r12+18h]
0x140041115  test    rcx, rcx
0x140041118  jz      short loc_140041121
0x14004111a  mov     edx, [r12+8]
0x14004111f  jmp     short loc_140041123
0x140041121  mov     edx, edi
0x140041123  mov     [rsp+168h+Length], edx
0x14004112a  cmp     cs:AfdMaxActiveTransmitFileCount, edi
0x140041130  jnz     loc_1400417A6
0x140041136  test    rcx, rcx
0x140041139  jz      short loc_14004114D
0x14004113b  test    edx, edx
0x14004113d  jz      loc_1400417A6
0x140041143  cmp     [r12], rdi
0x140041147  jl      loc_1400417A6
0x14004114d  mov     eax, edx
0x14004114f  mov     [rsp+168h+var_F8], rax
0x140041154  mov     edx, [r12+28h]
0x140041159  mov     r8d, [r12+38h]
0x14004115e  lea     rbx, [r8+rax]
0x140041162  add     rbx, rdx
0x140041165  mov     [rsp+168h+var_118], rbx
0x14004116a  mov     eax, cs:AfdMaxFastTransmit
0x140041170  cmp     rbx, rax
0x140041173  ja      loc_1400417A6
0x140041179  mov     [rsp+168h+var_100], ebx
0x14004117d  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x140041183  jbe     short loc_140041196
0x140041185  test    edx, edx
0x140041187  jz      loc_1400417A6
0x14004118d  test    r8d, r8d
0x140041190  jnz     loc_1400417A6
0x140041196  cmp     [r12+0Ch], edi
0x14004119b  jnz     loc_1400417A6
0x1400411a1  cmp     edx, 1000h
0x1400411a7  ja      loc_1400417A6
0x1400411ad  lea     rax, [r14+38h]
0x1400411b1  mov     [rsp+168h+SpinLock], rax
0x1400411b9  lea     rdx, [rsp+168h+LockHandle]; LockHandle
0x1400411c1  mov     rcx, rax; SpinLock
0x1400411c4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400411cb  nop     dword ptr [rax+rax+00h]
0x1400411d0  mov     r15, [r14+0C0h]
0x1400411d7  mov     [rsp+168h+var_B0], r15
0x1400411df  test    r15, r15
0x1400411e2  jnz     short loc_1400411FD
0x1400411e4  lea     rcx, [rsp+168h+LockHandle]; LockHandle
0x1400411ec  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400411f3  nop     dword ptr [rax+rax+00h]
0x1400411f8  jmp     loc_1400417A6
0x1400411fd  mov     r13, rdi
0x140041200  mov     r8d, ebx
0x140041203  mov     rdx, r15
0x140041206  mov     rcx, r14
0x140041209  call    AfdShouldSendBlock
0x14004120e  test    al, al
0x140041210  jz      short loc_140041230
0x140041212  mov     r12b, dil
0x140041215  mov     rsi, rdi
0x140041218  xor     r8d, r8d
0x14004121b  lea     rdx, [rsp+168h+LockHandle]
0x140041223  mov     rcx, r14
0x140041226  call    AfdNotifySockIndicateEventsUnlock
0x14004122b  jmp     loc_14004150A
0x140041230  mov     eax, 1
0x140041235  lock xadd [r15+30h], rax
0x14004123b  inc     rax
0x14004123e  cmp     rax, 1
0x140041242  jg      short loc_14004124B
0x140041244  mov     ecx, 0Eh
0x140041249  int     29h; Win8: RtlFailFast(ecx)
0x14004124b  xor     r8d, r8d
0x14004124e  lea     rdx, [rsp+168h+LockHandle]
0x140041256  mov     rcx, r14
0x140041259  call    AfdNotifySockIndicateEventsUnlock
0x14004125e  mov     byte ptr [rsp+168h+arg_0], 1
0x140041266  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x14004126c  jbe     short loc_140041275
0x14004126e  mov     ecx, [r12+28h]
0x140041273  jmp     short loc_140041277
0x140041275  mov     ecx, ebx
0x140041277  mov     eax, 58h ; 'X'
0x14004127c  cmp     ecx, eax
0x14004127e  cmovb   ecx, eax; Length
0x140041281  xor     r9d, r9d
0x140041284  mov     r8, [r15+20h]
0x140041288  xor     edx, edx
0x14004128a  call    AfdGetBuffer
0x14004128f  mov     rsi, rax
0x140041292  mov     [rsp+168h+var_C8], rax
0x14004129a  test    rax, rax
0x14004129d  jz      loc_140041791
0x1400412a3  mov     rax, [rax+68h]
0x1400412a7  mov     [rsp+168h+Irp], rax
0x1400412ac  mov     [rax+98h], rdi
0x1400412b3  mov     [rsi+8], rdi
0x1400412b7  cmp     [r12+28h], edi
0x1400412bc  jbe     short loc_1400412E8
0x1400412be  call    cs:__imp_ExGetPreviousMode
0x1400412c5  nop     dword ptr [rax+rax+00h]
0x1400412ca  mov     r8d, [r12+28h]; Size
0x1400412cf  mov     rdx, [r12+20h]; Src
0x1400412d4  mov     rcx, [rsi+70h]; void *
0x1400412d8  test    al, al
0x1400412da  jz      short loc_1400412E3
0x1400412dc  call    RtlCopyFromUser
0x1400412e1  jmp     short loc_1400412E8
0x1400412e3  call    RtlCopyVolatileMemory
0x1400412e8  cmp     [r12+38h], edi
0x1400412ed  jbe     short loc_14004132A
0x1400412ef  call    cs:__imp_ExGetPreviousMode
0x1400412f6  nop     dword ptr [rax+rax+00h]
0x1400412fb  mov     r8d, [r12+38h]; Size
0x140041300  mov     rdx, [r12+30h]; Src
0x140041305  mov     ecx, [r12+28h]
0x14004130a  mov     r9, [rsi+70h]
0x14004130e  add     r9, rcx
0x140041311  mov     rcx, [rsp+168h+var_F8]
0x140041316  add     rcx, r9; void *
0x140041319  test    al, al
0x14004131b  jz      short loc_140041324
0x14004131d  call    RtlCopyFromUser
0x140041322  jmp     short loc_14004132A
0x140041324  call    RtlCopyVolatileMemory
0x140041329  nop
0x14004132a  cmp     [r12+18h], rdi
0x14004132f  jz      loc_1400414BD
0x140041335  call    cs:__imp_ExGetPreviousMode
0x14004133c  nop     dword ptr [rax+rax+00h]
0x140041341  mov     [rsp+168h+arg_0], rdi
0x140041349  mov     [rsp+168h+HandleInformation], rdi; HandleInformation
0x14004134e  lea     rcx, [rsp+168h+arg_0]
0x140041356  mov     [rsp+168h+Object], rcx; Object
0x14004135b  mov     r9b, al; AccessMode
0x14004135e  mov     r8, cs:__imp_IoFileObjectType
0x140041365  mov     r8, [r8]; ObjectType
0x140041368  mov     edx, 1; DesiredAccess
0x14004136d  mov     rcx, [r12+18h]; Handle
0x140041372  call    cs:__imp_ObReferenceObjectByHandle
0x140041379  nop     dword ptr [rax+rax+00h]
0x14004137e  mov     r13, [rsp+168h+arg_0]
0x140041386  test    eax, eax
0x140041388  js      loc_140041507
0x14004138e  mov     eax, [r13+50h]
0x140041392  test    al, 40h
0x140041394  jz      loc_140041507
0x14004139a  mov     rcx, [r12]
0x14004139e  mov     qword ptr [rsp+168h+FileOffset], rcx
0x1400413a3  mov     eax, [r13+50h]
0x1400413a7  test    al, 2
0x1400413a9  jz      short loc_1400413B9
0x1400413ab  test    rcx, rcx
0x1400413ae  jnz     short loc_1400413B9
0x1400413b0  mov     rax, [r13+68h]
0x1400413b4  mov     qword ptr [rsp+168h+FileOffset], rax
0x1400413b9  mov     rcx, r13; FileObject
0x1400413bc  cmp     ebx, cs:AfdMaxFastCopyTransmit
0x1400413c2  ja      short loc_140041439
0x1400413c4  mov     edx, [r12+28h]
0x1400413c9  mov     rbx, [rsi+70h]
0x1400413cd  add     rbx, rdx
0x1400413d0  call    cs:__imp_IoGetRelatedDeviceObject
0x1400413d7  nop     dword ptr [rax+rax+00h]
0x1400413dc  mov     [rsp+168h+DeviceObject], rax; DeviceObject
0x1400413e1  mov     rax, [rsp+168h+arg_10]
0x1400413e9  mov     [rsp+168h+IoStatus], rax; IoStatus
0x1400413ee  mov     [rsp+168h+HandleInformation], rbx; Buffer
0x1400413f3  mov     dword ptr [rsp+168h+Object], edi; LockKey
0x1400413f7  xor     r9d, r9d; Wait
0x1400413fa  mov     r8d, [rsp+168h+Length]; Length
0x140041402  lea     rdx, [rsp+168h+FileOffset]; FileOffset
0x140041407  mov     rcx, r13; FileObject
0x14004140a  call    cs:__imp_FsRtlCopyRead
0x140041411  nop     dword ptr [rax+rax+00h]
0x140041416  mov     bl, al
0x140041418  mov     rcx, r13; Object
0x14004141b  call    cs:__imp_ObfDereferenceObject
0x140041422  nop     dword ptr [rax+rax+00h]
0x140041427  mov     r13, rdi
0x14004142a  test    bl, bl
0x14004142c  mov     rbx, [rsp+168h+var_118]
0x140041431  jz      loc_140041796
0x140041437  jmp     short loc_1400414AA
0x140041439  mov     rax, [rsp+168h+arg_10]
0x140041441  mov     [rsp+168h+HandleInformation], rax
0x140041446  lea     rax, [rsp+168h+var_108]
0x14004144b  mov     [rsp+168h+Object], rax
0x140041450  xor     r9d, r9d
0x140041453  mov     r8d, [rsp+168h+Length]
0x14004145b  lea     rdx, [rsp+168h+FileOffset]
0x140041460  call    cs:__imp_FsRtlMdlRead
0x140041467  nop     dword ptr [rax+rax+00h]
0x14004146c  test    al, al
0x14004146e  jz      loc_140041507
0x140041474  mov     [rsi+8], r13
0x140041478  mov     rax, qword ptr [rsp+168h+FileOffset]
0x14004147d  mov     [rsi+10h], rax
0x140041481  mov     eax, [r14+8]
0x140041485  bt      eax, 8
0x140041489  jb      short loc_1400414AA
0x14004148b  mov     eax, [r12+3Ch]
0x140041490  and     eax, 30h
0x140041493  cmp     eax, 20h ; ' '
0x140041496  jz      short loc_1400414A5
0x140041498  test    eax, eax
0x14004149a  jnz     short loc_1400414AA
0x14004149c  cmp     cs:AfdDefaultTransmitWorker, 20h ; ' '
0x1400414a3  jnz     short loc_1400414AA
0x1400414a5  mov     [rsp+168h+Irp], rdi
0x1400414aa  mov     rax, [rsp+168h+arg_10]
0x1400414b2  mov     rcx, [rsp+168h+var_F8]
0x1400414b7  cmp     [rax+8], rcx
0x1400414bb  jb      short loc_140041507
0x1400414bd  mov     rcx, [rsi+38h]
0x1400414c1  cmp     [rsp+168h+var_108], rdi
0x1400414c6  jnz     short loc_1400414CD
0x1400414c8  mov     [rcx+28h], ebx
0x1400414cb  jmp     short loc_1400414E1
0x1400414cd  mov     eax, [r12+28h]
0x1400414d2  mov     [rcx+28h], eax
0x1400414d5  mov     rcx, [rsi+38h]
0x1400414d9  mov     rax, [rsp+168h+var_108]
0x1400414de  mov     [rcx], rax
0x1400414e1  movzx   ecx, byte ptr [r14+2]
0x1400414e6  xor     eax, eax
0x1400414e8  lock cmpxchg [r14+170h], ecx
0x1400414f1  jnz     short loc_140041507
0x1400414f3  cmp     byte ptr [r14+2], 4
0x1400414f8  jz      loc_1400415F7
0x1400414fe  mov     eax, edi
0x140041500  xchg    eax, [r14+170h]
0x140041507  mov     r12b, 1
0x14004150a  mov     rbx, [rsp+168h+var_118]
0x14004150f  mov     rdx, [rsp+168h+var_108]
0x140041514  test    rdx, rdx
0x140041517  jz      short loc_140041557
0x140041519  lea     r8, [rsp+168h+FileOffset]
0x14004151e  mov     rcx, r13; Object
0x140041521  call    AfdMdlReadComplete
0x140041526  test    eax, eax
0x140041528  jns     short loc_140041557
0x14004152a  mov     [rsi+30h], r15
0x14004152e  mov     eax, 1
0x140041533  lock xadd [r15+30h], rax
0x140041539  inc     rax
0x14004153c  cmp     rax, 1
  ... truncated ...
```
