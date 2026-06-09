# RefsFsdFileSystemControl(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x140323940`
- end: `0x140323cd1`
- name: `?RefsFsdFileSystemControl@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `913`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000c180`
- `0x140050ba0`
- `0x140075660`
- `0x1400862c0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400aeae0`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x140323940`
- `0x140323dd8`
- `0x140324914`
- `0x14033439c`
- `0x14033a7a8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140323b94`
- `ntoskrnl!ObfDereferenceObject` at `0x140323b94`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140323a3f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140323a3f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403239b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403239b8`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1403239d4`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1403239d4`
- `ntoskrnl!IoClearActivityIdThread` at `0x140323cc3`
- `ntoskrnl!IoClearActivityIdThread` at `0x140323cc3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140323c61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140323c61`
- `ntoskrnl!KeSetEvent` at `0x140323b83`
- `ntoskrnl!KeSetEvent` at `0x140323b83`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1403239a8`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1403239a8`
- `ntoskrnl!FsRtlNotifyVolumeEventEx` at `0x140323b66`
- `ntoskrnl!FsRtlNotifyVolumeEventEx` at `0x140323b66`

## pseudocode

```c
__int64 __fastcall RefsFsdFileSystemControl(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _TOP_LEVEL_CONTEXT *v3; // r14
  int v4; // edx
  struct _IRP_CONTEXT *v5; // rbx
  __int64 v6; // r8
  const char *v7; // r9
  UCHAR MinorFunction; // al
  unsigned int v9; // esi
  BOOLEAN IsOperationSynchronous; // [rsp+20h] [rbp-F8h]
  struct _IRP_CONTEXT *v12; // [rsp+28h] [rbp-F0h] BYREF
  int v13; // [rsp+30h] [rbp-E8h]
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-E0h]
  struct _VCB *v15; // [rsp+40h] [rbp-D8h]
  struct _TOP_LEVEL_CONTEXT *v16; // [rsp+48h] [rbp-D0h]
  __int64 v17; // [rsp+50h] [rbp-C8h] BYREF
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+58h] [rbp-C0h]
  struct _IRP *v19; // [rsp+60h] [rbp-B8h]
  __int128 v20; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+78h] [rbp-A0h]
  __int128 v22; // [rsp+80h] [rbp-98h] BYREF

  v19 = a2;
  v20 = 0;
  v21 = 0;
  v12 = 0;
  v22 = 0;
  v17 = 0;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
  if ( a2->Tail.Overlay.CurrentStackLocation->FileObject )
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
  else
    IsOperationSynchronous = 1;
  KeEnterCriticalRegion();
  v13 = IoPropagateActivityIdToThread(a2, &v22, &v17);
  v3 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v20, 0, 0);
  v16 = v3;
  RefsInitializeIrpContext(a2, IsOperationSynchronous, 1, &v12);
  if ( *((_QWORD *)v3 + 2) )
  {
    v5 = v12;
  }
  else
  {
    *((_DWORD *)v3 + 1) = 1397140410;
    v5 = v12;
    *((_QWORD *)v3 + 2) = v12;
    *((_QWORD *)v5 + 1) |= 0x100000uLL;
    IoSetTopLevelIrp((PIRP)v3);
  }
  *((_QWORD *)v5 + 13) = *((_QWORD *)v3 + 2);
  RefsPreRequestProcessingExtend(v5, v4);
  MinorFunction = p_CurrentStackLocation->CurrentStackLocation->MinorFunction;
  if ( MinorFunction == 1 )
  {
    v9 = RefsPostRequest(v5, (struct _SECURITY_SUBJECT_CONTEXT *)a2, 1, 0);
  }
  else if ( MinorFunction == 2 )
  {
    v9 = RefsVerifyVolumeRequest(v5, a2);
  }
  else
  {
    v15 = 0;
    FileObject = 0;
    if ( MinorFunction == 4 || !MinorFunction )
    {
      v9 = RefsUserFsRequest((_VCB **)v5, a2, v6, v7);
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v9 = -1073741808;
      }
      else
      {
        v9 = -1073741808;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225488LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741808, 0, "FsCtrl.c", 0x573u);
      RefsCompleteFileSystemControlRequest(v5, a2, -1073741808);
    }
  }
  if ( v13 >= 0 )
    IoClearActivityIdThread(v17);
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x140323940  push    rbx
0x140323942  push    rsi
0x140323943  push    rdi
0x140323944  push    r14
0x140323946  sub     rsp, 0F8h
0x14032394d  mov     rax, cs:__security_cookie
0x140323954  xor     rax, rsp
0x140323957  mov     [rsp+118h+var_38], rax
0x14032395f  mov     rdi, rdx
0x140323962  mov     [rsp+118h+var_B8], rdx
0x140323967  xorps   xmm0, xmm0
0x14032396a  xor     eax, eax
0x14032396c  movups  [rsp+118h+var_B0], xmm0
0x140323971  mov     [rsp+118h+var_A0], rax
0x140323976  xor     ebx, ebx
0x140323978  mov     [rsp+118h+var_F0], rbx
0x14032397d  xor     esi, esi
0x14032397f  movups  [rsp+118h+var_98], xmm0
0x140323987  mov     [rsp+118h+var_C8], rax
0x14032398c  lea     rax, [rdx+0B8h]
0x140323993  mov     [rsp+118h+var_C0], rax
0x140323998  mov     rax, [rax]
0x14032399b  cmp     [rax+30h], rbx
0x14032399f  jz      loc_140323C8D
0x1403239a5  mov     rcx, rdx; Irp
0x1403239a8  call    cs:__imp_IoIsOperationSynchronous
0x1403239af  nop     dword ptr [rax+rax+00h]
0x1403239b4  mov     [rsp+118h+var_F8], al
0x1403239b8  call    cs:__imp_KeEnterCriticalRegion
0x1403239bf  nop     dword ptr [rax+rax+00h]
0x1403239c4  lea     r8, [rsp+118h+var_C8]
0x1403239c9  lea     rdx, [rsp+118h+var_98]
0x1403239d1  mov     rcx, rdi
0x1403239d4  call    cs:__imp_IoPropagateActivityIdToThread
0x1403239db  nop     dword ptr [rax+rax+00h]
0x1403239e0  mov     [rsp+118h+var_E8], eax
0x1403239e4  xor     r8d, r8d; unsigned __int8
0x1403239e7  xor     edx, edx; unsigned __int8
0x1403239e9  lea     rcx, [rsp+118h+var_B0]; struct _TOP_LEVEL_CONTEXT *
0x1403239ee  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1403239f3  mov     r14, rax
0x1403239f6  mov     [rsp+118h+var_D0], rax
0x1403239fb  test    rbx, rbx
0x1403239fe  jnz     loc_140323BA5
0x140323a04  lea     r9, [rsp+118h+var_F0]; struct _IRP_CONTEXT **
0x140323a09  mov     r8b, 1; unsigned __int8
0x140323a0c  movzx   edx, [rsp+118h+var_F8]; unsigned __int8
0x140323a11  mov     rcx, rdi; Irp
0x140323a14  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140323a19  cmp     [r14+10h], rbx
0x140323a1d  jnz     loc_140323ACE
0x140323a23  mov     dword ptr [r14+4], 5346ABBAh
0x140323a2b  mov     rbx, [rsp+118h+var_F0]
0x140323a30  mov     [r14+10h], rbx
0x140323a34  or      qword ptr [rbx+8], 100000h
0x140323a3c  mov     rcx, r14; Irp
0x140323a3f  call    cs:__imp_IoSetTopLevelIrp
0x140323a46  nop     dword ptr [rax+rax+00h]
0x140323a4b  mov     rax, [r14+10h]
0x140323a4f  mov     [rbx+68h], rax
0x140323a53  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323a56  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140323a5b  mov     rax, [rsp+118h+var_C0]
0x140323a60  mov     rcx, [rax]
0x140323a63  movzx   eax, byte ptr [rcx+1]
0x140323a67  cmp     al, 1
0x140323a69  jnz     short loc_140323A88
0x140323a6b  xor     r9d, r9d; unsigned __int8
0x140323a6e  movzx   r8d, al; unsigned __int8
0x140323a72  mov     rdx, rdi; struct _IRP *
0x140323a75  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323a78  call    ?RefsPostRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z; RefsPostRequest(_IRP_CONTEXT *,_IRP *,uchar,uchar)
0x140323a7d  mov     esi, eax
0x140323a7f  mov     [rsp+118h+var_F4], eax
0x140323a83  jmp     loc_140323C38
0x140323a88  cmp     al, 2
0x140323a8a  jz      short loc_140323AB8
0x140323a8c  mov     [rsp+118h+var_D8], 0
0x140323a95  mov     [rsp+118h+FileObject], 0
0x140323a9e  cmp     al, 4
0x140323aa0  jnz     short loc_140323AD8
0x140323aa2  mov     rdx, rdi; Irp
0x140323aa5  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323aa8  call    ?RefsUserFsRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsUserFsRequest(_IRP_CONTEXT *,_IRP *)
0x140323aad  mov     esi, eax
0x140323aaf  mov     [rsp+118h+var_F4], esi
0x140323ab3  jmp     loc_140323C38
0x140323ab8  mov     rdx, rdi; Irp
0x140323abb  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323abe  call    ?RefsVerifyVolumeRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsVerifyVolumeRequest(_IRP_CONTEXT *,_IRP *)
0x140323ac3  mov     esi, eax
0x140323ac5  mov     [rsp+118h+var_F4], eax
0x140323ac9  jmp     loc_140323C38
0x140323ace  mov     rbx, [rsp+118h+var_F0]
0x140323ad3  jmp     loc_140323A4B
0x140323ad8  test    al, al
0x140323ada  jz      short loc_140323AA2
0x140323adc  cmp     eax, 1
0x140323adf  jnz     loc_140323BBE
0x140323ae5  lea     r9, [rsp+118h+FileObject]; struct _FILE_OBJECT **
0x140323aea  lea     r8, [rsp+118h+var_D8]; struct _VCB **
0x140323aef  mov     rdx, rdi; Irp
0x140323af2  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323af5  call    ?RefsMountVolume@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAPEAU_VCB@@PEAPEAU_FILE_OBJECT@@@Z; RefsMountVolume(_IRP_CONTEXT *,_IRP *,_VCB * *,_FILE_OBJECT * *)
0x140323afa  mov     esi, eax
0x140323afc  mov     rcx, [rsp+118h+FileObject]; FileObject
0x140323b01  test    rcx, rcx
0x140323b04  jz      short loc_140323AAF
0x140323b06  mov     dword ptr [rsp+118h+Event.Version], 480001h
0x140323b11  mov     [rsp+118h+Event.FileObject], 0
0x140323b1d  mov     [rsp+118h+Event.NameBufferOffset], 0FFFFFFFFh
0x140323b28  mov     qword ptr [rsp+118h+Event.CustomDataBuffer], 1
0x140323b34  mov     [rsp+118h+var_5C], 8
0x140323b3f  mov     [rsp+118h+var_58], 10h
0x140323b4a  mov     rax, qword ptr cs:aRefs_0; "ReFS"
0x140323b51  mov     [rsp+118h+var_54], rax
0x140323b59  lea     r8, [rsp+118h+Event]; Event
0x140323b61  mov     edx, 6; EventCode
0x140323b66  call    cs:__imp_FsRtlNotifyVolumeEventEx
0x140323b6d  nop     dword ptr [rax+rax+00h]
0x140323b72  mov     rcx, [rsp+118h+var_D8]
0x140323b77  add     rcx, 17F0h; Event
0x140323b7e  xor     r8d, r8d; Wait
0x140323b81  xor     edx, edx; Increment
0x140323b83  call    cs:__imp_KeSetEvent
0x140323b8a  nop     dword ptr [rax+rax+00h]
0x140323b8f  mov     rcx, [rsp+118h+FileObject]; Object
0x140323b94  call    cs:__imp_ObfDereferenceObject
0x140323b9b  nop     dword ptr [rax+rax+00h]
0x140323ba0  jmp     loc_140323AAF
0x140323ba5  cmp     esi, 0C0000188h
0x140323bab  jnz     loc_140323A53
0x140323bb1  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323bb4  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140323bb9  jmp     loc_140323A53
0x140323bbe  lea     rax, WPP_GLOBAL_Control
0x140323bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140323bcc  cmp     rcx, rax
0x140323bcf  jz      short loc_140323BFF
0x140323bd1  test    dword ptr [rcx+2Ch], 100h
0x140323bd8  jz      short loc_140323BFF
0x140323bda  cmp     byte ptr [rcx+29h], 4
0x140323bde  jb      short loc_140323BFF
0x140323be0  mov     edx, 0Ch
0x140323be5  mov     esi, 0C0000010h
0x140323bea  mov     r9d, esi
0x140323bed  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x140323bf4  mov     rcx, [rcx+18h]
0x140323bf8  call    WPP_SF_d
0x140323bfd  jmp     short loc_140323C04
0x140323bff  mov     esi, 0C0000010h
0x140323c04  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140323c0b  test    al, al
0x140323c0d  jz      short loc_140323C25
0x140323c0f  mov     r9d, 573h; unsigned int
0x140323c15  lea     r8, aFsctrlC; "FsCtrl.c"
0x140323c1c  xor     edx, edx; struct _IRP_CONTEXT *
0x140323c1e  mov     ecx, esi; Status
0x140323c20  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140323c25  mov     r8d, esi; int
0x140323c28  mov     rdx, rdi; struct _IRP *
0x140323c2b  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323c2e  call    ?RefsCompleteFileSystemControlRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteFileSystemControlRequest(_IRP_CONTEXT *,_IRP *,long)
0x140323c33  jmp     loc_140323AAF
0x140323c38  jmp     short loc_140323C5A
0x140323c3a  mov     r8d, eax; int
0x140323c3d  mov     rdi, [rsp+118h+var_B8]
0x140323c42  mov     rdx, rdi; struct _IRP *
0x140323c45  mov     rbx, [rsp+118h+var_F0]
0x140323c4a  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140323c4d  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140323c52  mov     esi, eax
0x140323c54  mov     [rsp+118h+var_F4], eax
0x140323c58  jmp     short loc_140323C97
0x140323c5a  cmp     [rsp+118h+var_E8], 0
0x140323c5f  jge     short loc_140323CBE
0x140323c61  call    cs:__imp_KeLeaveCriticalRegion
0x140323c68  nop     dword ptr [rax+rax+00h]
0x140323c6d  mov     eax, esi
0x140323c6f  mov     rcx, [rsp+118h+var_38]
0x140323c77  xor     rcx, rsp; StackCookie
0x140323c7a  call    __security_check_cookie
0x140323c7f  add     rsp, 0F8h
0x140323c86  pop     r14
0x140323c88  pop     rdi
0x140323c89  pop     rsi
0x140323c8a  pop     rbx
0x140323c8b  retn
0x140323c8d  mov     [rsp+118h+var_F8], 1
0x140323c92  jmp     loc_1403239B8
0x140323c97  cmp     eax, 0C00000D8h
0x140323c9c  jz      loc_14034D3F2
0x140323ca2  cmp     eax, 0C00001A8h
0x140323ca7  jz      loc_14034D3F2
0x140323cad  cmp     eax, 0C0000188h
0x140323cb2  jnz     short loc_140323C5A
0x140323cb4  mov     r14, [rsp+118h+var_D0]
0x140323cb9  jmp     loc_1403239FB
0x140323cbe  mov     rcx, [rsp+118h+var_C8]
0x140323cc3  call    cs:__imp_IoClearActivityIdThread
0x140323cca  nop     dword ptr [rax+rax+00h]
0x140323ccf  jmp     short loc_140323C61
0x1403439b0  push    rbp
0x1403439b2  sub     rsp, 20h
0x1403439b6  mov     rbp, rdx
0x1403439b9  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x1403439bc  mov     rcx, [rbp+28h]; struct _IRP_CONTEXT *
0x1403439c0  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x1403439c5  nop
0x1403439c6  add     rsp, 20h
0x1403439ca  pop     rbp
0x1403439cb  retn
0x14034d3f2  mov     r14, [rsp+118h+var_D0]
0x14034d3f7  jmp     loc_1403239FB
```
