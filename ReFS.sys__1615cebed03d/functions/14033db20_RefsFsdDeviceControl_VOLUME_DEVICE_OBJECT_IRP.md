# RefsFsdDeviceControl(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14033db20`
- end: `0x14033de3c`
- name: `?RefsFsdDeviceControl@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `796`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140075660`
- `0x1400862c0`
- `0x140088c00`
- `0x14009a130`
- `0x1400a069c`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x14029d114`
- `0x14033a7a8`
- `0x14033db20`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x14033dd5e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033dd5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033dbf0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033dce3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033dbf0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033dce3`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14033dcfc`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14033dcfc`
- `ntoskrnl!IoClearActivityIdThread` at `0x14033de07`
- `ntoskrnl!IoClearActivityIdThread` at `0x14033de07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033dc15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033de13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033dc15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033de13`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14033dcd3`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14033dcd3`

## pseudocode

```c
__int64 __fastcall RefsFsdDeviceControl(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PFILE_OBJECT FileObject; // rax
  _QWORD *FsContext; // rbx
  _BYTE *FsContext2; // rcx
  __int64 v7; // rbx
  struct _IO_STACK_LOCATION *v8; // rax
  NTSTATUS v9; // ebx
  unsigned int v11; // esi
  struct _TOP_LEVEL_CONTEXT *v12; // rbx
  int v13; // edx
  struct _IRP_CONTEXT *v14; // rdi
  BOOLEAN IsOperationSynchronous; // [rsp+20h] [rbp-88h]
  int v16[5]; // [rsp+24h] [rbp-84h] BYREF
  struct _TOP_LEVEL_CONTEXT *v17; // [rsp+38h] [rbp-70h]
  _QWORD v18[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v19; // [rsp+50h] [rbp-58h] BYREF
  __int64 v20; // [rsp+60h] [rbp-48h]
  __int128 v21; // [rsp+68h] [rbp-40h] BYREF

  v18[1] = a2;
  v21 = 0;
  v18[0] = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 508004
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5488640
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5488644 )
  {
    v19 = 0;
    v20 = 0;
    v16[2] = 0;
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
    KeEnterCriticalRegion();
    *(_QWORD *)v16 = (unsigned int)IoPropagateActivityIdToThread(a2, &v21, v18);
    v12 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v19, 0, 0);
    v17 = v12;
    RefsInitializeIrpContext(a2, IsOperationSynchronous, 1, (struct _IRP_CONTEXT **)&v16[1]);
    if ( *((_QWORD *)v12 + 2) )
    {
      v14 = *(struct _IRP_CONTEXT **)&v16[1];
      *(_QWORD *)(*(_QWORD *)&v16[1] + 104LL) = *((_QWORD *)v12 + 2);
    }
    else
    {
      *((_DWORD *)v12 + 1) = 1397140410;
      v14 = *(struct _IRP_CONTEXT **)&v16[1];
      *((_QWORD *)v12 + 2) = *(_QWORD *)&v16[1];
      *((_QWORD *)v14 + 1) |= 0x100000uLL;
      IoSetTopLevelIrp((PIRP)v12);
      *((_QWORD *)v14 + 13) = *((_QWORD *)v12 + 2);
    }
    RefsPreRequestProcessingExtend(v14, v13);
    v11 = RefsCommonDeviceControl(v14, a2);
    v16[3] = v11;
    if ( v16[0] >= 0 )
      IoClearActivityIdThread(v18[0]);
    KeLeaveCriticalRegion();
    return v11;
  }
  v16[0] = 0;
  FileObject = CurrentStackLocation->FileObject;
  FsContext = FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = FileObject->FsContext2;
    if ( FsContext2 )
    {
      if ( FsContext2[80] == 4 )
      {
        v7 = FsContext[18];
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                   + 6);
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
        CurrentStackLocation[-1].Control = 0;
        v8 = a2->Tail.Overlay.CurrentStackLocation;
        v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DeviceControlCompletionRoutine;
        v8[-1].Context = 0;
        v8[-1].Control = -32;
        KeEnterCriticalRegion();
        v9 = RefsCallStorageDriver(*(PDEVICE_OBJECT *)(v7 + 192), a2, 0, v16);
        KeLeaveCriticalRegion();
        if ( v9 < 0 )
        {
          RefsCompleteRequest(0, a2, v9);
          return (unsigned int)v9;
        }
        return (unsigned int)v16[0];
      }
    }
  }
  RefsCompleteRequest(0, a2, -1073741811);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d2b858aa66583678702511d96250d83d_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741811, 0, "DevCtrl.c", 0xDBu);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14033db20  push    rbx
0x14033db22  push    rsi
0x14033db23  push    rdi
0x14033db24  push    r14
0x14033db26  sub     rsp, 88h
0x14033db2d  mov     rax, cs:__security_cookie
0x14033db34  xor     rax, rsp
0x14033db37  mov     [rsp+0A8h+var_30], rax
0x14033db3c  mov     r14, rdx
0x14033db3f  mov     [rsp+0A8h+var_60], rdx
0x14033db44  xorps   xmm0, xmm0
0x14033db47  movups  [rsp+0A8h+var_40], xmm0
0x14033db4c  xor     edi, edi
0x14033db4e  mov     [rsp+0A8h+var_68], rdi
0x14033db53  mov     rdx, [rdx+0B8h]
0x14033db5a  mov     ecx, [rdx+18h]
0x14033db5d  sub     ecx, 7C064h
0x14033db63  jz      loc_14033DCBD
0x14033db69  sub     ecx, 4BFF9Ch
0x14033db6f  jz      loc_14033DCBD
0x14033db75  cmp     ecx, 4
0x14033db78  jz      loc_14033DCBD
0x14033db7e  mov     [rsp+0A8h+var_84], edi
0x14033db82  mov     rax, [rdx+30h]
0x14033db86  mov     rbx, [rax+18h]
0x14033db8a  test    rbx, rbx
0x14033db8d  jz      loc_14033DC42
0x14033db93  mov     rcx, [rax+20h]
0x14033db97  test    rcx, rcx
0x14033db9a  jz      loc_14033DC42
0x14033dba0  cmp     byte ptr [rcx+50h], 4
0x14033dba4  jnz     loc_14033DC42
0x14033dbaa  mov     rbx, [rbx+90h]
0x14033dbb1  movups  xmm0, xmmword ptr [rdx]
0x14033dbb4  movups  xmmword ptr [rdx-48h], xmm0
0x14033dbb8  movups  xmm1, xmmword ptr [rdx+10h]
0x14033dbbc  movups  xmmword ptr [rdx-38h], xmm1
0x14033dbc0  movups  xmm0, xmmword ptr [rdx+20h]
0x14033dbc4  movups  xmmword ptr [rdx-28h], xmm0
0x14033dbc8  movsd   xmm1, qword ptr [rdx+30h]
0x14033dbcd  movsd   qword ptr [rdx-18h], xmm1
0x14033dbd2  mov     [rdx-45h], dil
0x14033dbd6  mov     rax, [r14+0B8h]
0x14033dbdd  lea     rcx, ?DeviceControlCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; DeviceControlCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14033dbe4  mov     [rax-10h], rcx
0x14033dbe8  mov     [rax-8], rdi
0x14033dbec  mov     byte ptr [rax-45h], 0E0h
0x14033dbf0  call    cs:__imp_KeEnterCriticalRegion
0x14033dbf7  nop     dword ptr [rax+rax+00h]
0x14033dbfc  lea     r9, [rsp+0A8h+var_84]; int *
0x14033dc01  xor     r8d, r8d; Context
0x14033dc04  mov     rdx, r14; Irp
0x14033dc07  mov     rcx, [rbx+0C0h]; DeviceObject
0x14033dc0e  call    ?RefsCallStorageDriver@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAXPEAJ@Z; RefsCallStorageDriver(_DEVICE_OBJECT *,_IRP *,void *,long *)
0x14033dc13  mov     ebx, eax
0x14033dc15  call    cs:__imp_KeLeaveCriticalRegion
0x14033dc1c  nop     dword ptr [rax+rax+00h]
0x14033dc21  test    ebx, ebx
0x14033dc23  jns     short loc_14033DC39
0x14033dc25  mov     r8d, ebx; Status
0x14033dc28  mov     rdx, r14; Irp
0x14033dc2b  xor     ecx, ecx; struct _IRP_CONTEXT *
0x14033dc2d  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14033dc32  mov     eax, ebx
0x14033dc34  jmp     loc_14033DE21
0x14033dc39  mov     esi, [rsp+0A8h+var_84]
0x14033dc3d  jmp     loc_14033DE1F
0x14033dc42  mov     r8d, 0C000000Dh; Status
0x14033dc48  mov     rdx, r14; Irp
0x14033dc4b  xor     ecx, ecx; struct _IRP_CONTEXT *
0x14033dc4d  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14033dc52  lea     rax, WPP_GLOBAL_Control
0x14033dc59  mov     rcx, cs:WPP_GLOBAL_Control
0x14033dc60  cmp     rcx, rax
0x14033dc63  jz      short loc_14033DC8F
0x14033dc65  test    dword ptr [rcx+2Ch], 100h
0x14033dc6c  jz      short loc_14033DC8F
0x14033dc6e  cmp     byte ptr [rcx+29h], 4
0x14033dc72  jb      short loc_14033DC8F
0x14033dc74  mov     edx, 0Ah
0x14033dc79  mov     r9d, 0C000000Dh
0x14033dc7f  lea     r8, WPP_d2b858aa66583678702511d96250d83d_Traceguids
0x14033dc86  mov     rcx, [rcx+18h]
0x14033dc8a  call    WPP_SF_d
0x14033dc8f  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14033dc96  test    cl, cl
0x14033dc98  jz      short loc_14033DCB3
0x14033dc9a  mov     r9d, 0DBh; unsigned int
0x14033dca0  lea     r8, aDevctrlC; "DevCtrl.c"
0x14033dca7  xor     edx, edx; struct _IRP_CONTEXT *
0x14033dca9  mov     ecx, 0C000000Dh; Status
0x14033dcae  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14033dcb3  mov     eax, 0C000000Dh
0x14033dcb8  jmp     loc_14033DE21
0x14033dcbd  mov     esi, edi
0x14033dcbf  xor     eax, eax
0x14033dcc1  movups  [rsp+0A8h+var_58], xmm0
0x14033dcc6  mov     [rsp+0A8h+var_48], rax
0x14033dccb  mov     [rsp+0A8h+var_80], rdi
0x14033dcd0  mov     rcx, r14; Irp
0x14033dcd3  call    cs:__imp_IoIsOperationSynchronous
0x14033dcda  nop     dword ptr [rax+rax+00h]
0x14033dcdf  mov     [rsp+0A8h+var_88], al
0x14033dce3  call    cs:__imp_KeEnterCriticalRegion
0x14033dcea  nop     dword ptr [rax+rax+00h]
0x14033dcef  lea     r8, [rsp+0A8h+var_68]
0x14033dcf4  lea     rdx, [rsp+0A8h+var_40]
0x14033dcf9  mov     rcx, r14
0x14033dcfc  call    cs:__imp_IoPropagateActivityIdToThread
0x14033dd03  nop     dword ptr [rax+rax+00h]
0x14033dd08  mov     [rsp+0A8h+var_84], eax
0x14033dd0c  xor     r8d, r8d; unsigned __int8
0x14033dd0f  xor     edx, edx; unsigned __int8
0x14033dd11  lea     rcx, [rsp+0A8h+var_58]; struct _TOP_LEVEL_CONTEXT *
0x14033dd16  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x14033dd1b  mov     rbx, rax
0x14033dd1e  mov     [rsp+0A8h+var_70], rax
0x14033dd23  test    rdi, rdi
0x14033dd26  jnz     short loc_14033DD83
0x14033dd28  lea     r9, [rsp+0A8h+var_80]; struct _IRP_CONTEXT **
0x14033dd2d  mov     r8b, 1; unsigned __int8
0x14033dd30  movzx   edx, [rsp+0A8h+var_88]; unsigned __int8
0x14033dd35  mov     rcx, r14; Irp
0x14033dd38  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x14033dd3d  cmp     [rbx+10h], rdi
0x14033dd41  jnz     short loc_14033DD74
0x14033dd43  mov     dword ptr [rbx+4], 5346ABBAh
0x14033dd4a  mov     rdi, [rsp+0A8h+var_80]
0x14033dd4f  mov     [rbx+10h], rdi
0x14033dd53  or      qword ptr [rdi+8], 100000h
0x14033dd5b  mov     rcx, rbx; Irp
0x14033dd5e  call    cs:__imp_IoSetTopLevelIrp
0x14033dd65  nop     dword ptr [rax+rax+00h]
0x14033dd6a  mov     rax, [rbx+10h]
0x14033dd6e  mov     [rdi+68h], rax
0x14033dd72  jmp     short loc_14033DD93
0x14033dd74  mov     rdi, [rsp+0A8h+var_80]
0x14033dd79  mov     rax, [rbx+10h]
0x14033dd7d  mov     [rdi+68h], rax
0x14033dd81  jmp     short loc_14033DD93
0x14033dd83  cmp     esi, 0C0000188h
0x14033dd89  jnz     short loc_14033DD93
0x14033dd8b  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14033dd8e  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x14033dd93  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14033dd96  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x14033dd9b  mov     rdx, r14; Irp
0x14033dd9e  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14033dda1  call    ?RefsCommonDeviceControl@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonDeviceControl(_IRP_CONTEXT *,_IRP *)
0x14033dda6  mov     esi, eax
0x14033dda8  mov     [rsp+0A8h+var_78], eax
0x14033ddac  jmp     short loc_14033DDFB
0x14033ddae  mov     r8d, eax; int
0x14033ddb1  mov     r14, [rsp+0A8h+var_60]
0x14033ddb6  mov     rdx, r14; struct _IRP *
0x14033ddb9  mov     rdi, [rsp+0A8h+var_80]
0x14033ddbe  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14033ddc1  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x14033ddc6  mov     esi, eax
0x14033ddc8  mov     [rsp+0A8h+var_78], eax
0x14033ddcc  cmp     eax, 0C00000D8h
0x14033ddd1  jz      short loc_14033DDE0
0x14033ddd3  cmp     eax, 0C00001A8h
0x14033ddd8  jnz     short loc_14033DDEA
0x14033ddda  nop     word ptr [rax+rax+00h]
0x14033dde0  mov     rbx, [rsp+0A8h+var_70]
0x14033dde5  jmp     loc_14033DD23
0x14033ddea  cmp     eax, 0C0000188h
0x14033ddef  jnz     short loc_14033DDFB
0x14033ddf1  mov     rbx, [rsp+0A8h+var_70]
0x14033ddf6  jmp     loc_14033DD23
0x14033ddfb  cmp     [rsp+0A8h+var_84], 0
0x14033de00  jl      short loc_14033DE13
0x14033de02  mov     rcx, [rsp+0A8h+var_68]
0x14033de07  call    cs:__imp_IoClearActivityIdThread
0x14033de0e  nop     dword ptr [rax+rax+00h]
0x14033de13  call    cs:__imp_KeLeaveCriticalRegion
0x14033de1a  nop     dword ptr [rax+rax+00h]
0x14033de1f  mov     eax, esi
0x14033de21  mov     rcx, [rsp+0A8h+var_30]
0x14033de26  xor     rcx, rsp; StackCookie
0x14033de29  call    __security_check_cookie
0x14033de2e  add     rsp, 88h
0x14033de35  pop     r14
0x14033de37  pop     rdi
0x14033de38  pop     rsi
0x14033de39  pop     rbx
0x14033de3a  retn
0x140346600  push    rbp
0x140346602  sub     rsp, 20h
0x140346606  mov     rbp, rdx
0x140346609  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x14034660c  mov     rcx, [rbp+28h]; struct _IRP_CONTEXT *
0x140346610  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x140346615  nop
0x140346616  add     rsp, 20h
0x14034661a  pop     rbp
0x14034661b  retn
```
