# WimFSFReadWim

- ea: `0x14003cd40`
- end: `0x14003d265`
- name: `WimFSFReadWim`
- size: `1317`
- prototype: `__int64 __fastcall(unsigned __int8, __int64, __int64, struct _FLT_CALLBACK_DATA *, PVOID, void *, int, char *Context)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14002e244`
- `0x14003da58`

## callees

- `0x14000afc0`
- `0x14000bf54`
- `0x14000c074`
- `0x14000cfe0`
- `0x14000d2fc`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010774`
- `0x14003cd40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003d012`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003d012`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003cf08`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003d162`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003cf08`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14003d162`
- `ntoskrnl!KeInitializeEvent` at `0x14003ceaf`
- `ntoskrnl!KeInitializeEvent` at `0x14003cfaa`
- `ntoskrnl!KeInitializeEvent` at `0x14003d238`
- `ntoskrnl!KeInitializeEvent` at `0x14003ceaf`
- `ntoskrnl!KeInitializeEvent` at `0x14003cfaa`
- `ntoskrnl!KeInitializeEvent` at `0x14003d238`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003d180`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003d180`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x14003d153`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x14003d153`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14003d1d6`
- `FLTMGR!FltPerformAsynchronousIo` at `0x14003d1d6`
- `FLTMGR!FltReadFile` at `0x14003cf7f`
- `FLTMGR!FltReadFile` at `0x14003cf7f`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003ce6b`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14003ce6b`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003d248`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003d248`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003d08b`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003d08b`
- `FLTMGR!FltPropagateIrpExtension` at `0x14003d0af`
- `FLTMGR!FltPropagateIrpExtension` at `0x14003d0af`
- `FLTMGR!FltFreeCallbackData` at `0x14003d0c5`
- `FLTMGR!FltFreeCallbackData` at `0x14003d0c5`

## pseudocode

```c
__int64 __fastcall WimFSFReadWim(
        unsigned __int8 a1,
        __int64 a2,
        __int64 a3,
        struct _FLT_CALLBACK_DATA *a4,
        PVOID a5,
        void *a6,
        int a7,
        char *Context)
{
  char *v8; // rdi
  int v10; // r15d
  char v11; // r12
  struct _FLT_INSTANCE *v12; // r13
  __int64 v13; // r14
  int v14; // esi
  int v15; // r9d
  char v16; // al
  ULONG v17; // r12d
  PVOID v18; // rbx
  PVOID Buffer; // r15
  NTSTATUS v20; // ebx
  char v21; // si
  __int64 v23; // rcx
  struct _FILE_OBJECT *v24; // rdx
  PFLT_CALLBACK_DATA v25; // rax
  void *v26; // rdx
  int v27; // [rsp+50h] [rbp-18h] BYREF
  ULONG BytesRead; // [rsp+54h] [rbp-14h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-10h] BYREF
  SIZE_T NumberOfBytes; // [rsp+B8h] [rbp+50h] BYREF
  char v32; // [rsp+C0h] [rbp+58h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+C8h] [rbp+60h] BYREF

  RetNewCallbackData = a4;
  v32 = a3;
  v8 = Context;
  v10 = a1;
  v11 = a2;
  BytesRead = 0;
  ByteOffset.QuadPart = 0;
  v12 = (struct _FLT_INSTANCE *)*((_QWORD *)Context + 5);
  v13 = *((_QWORD *)Context + 6);
  LODWORD(NumberOfBytes) = 0;
  v27 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  v14 = a7;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_iqDl(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a4, a5, a7, v10);
  *((_DWORD *)v8 + 29) = 0;
  if ( v11 )
  {
    ByteOffset.QuadPart = (LONGLONG)a4;
    v17 = v14;
  }
  else
  {
    if ( (_BYTE)v10 )
      v15 = *(_DWORD *)(v13 + 92);
    else
      v15 = 1;
    v16 = WimFSFGetAlignedSizesForIntegrity(
            v13,
            (unsigned int)&RetNewCallbackData,
            v14,
            v15,
            (__int64)&ByteOffset,
            (__int64)&NumberOfBytes,
            (__int64)&v27);
    v17 = NumberOfBytes;
    v32 = v16;
  }
  if ( (struct _FLT_CALLBACK_DATA *)ByteOffset.QuadPart == a4 && v17 == v14 )
  {
    v18 = a5;
    Buffer = a5;
  }
  else
  {
    a6 = 0;
    Buffer = FltAllocatePoolAlignedWithTag(v12, (POOL_TYPE)512, v17, 0x44527077u);
    if ( !Buffer )
    {
      v20 = -1073741670;
      goto LABEL_38;
    }
    v18 = a5;
  }
  if ( (*((_DWORD *)v8 + 36) & 1) != 0 )
  {
    v8[201] = 1;
    KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
  }
  else
  {
    v8[201] = 0;
  }
  v8[152] = v32;
  *((union _LARGE_INTEGER *)v8 + 20) = ByteOffset;
  *((_DWORD *)v8 + 46) = v27;
  *((_DWORD *)v8 + 39) = v14;
  *((_QWORD *)v8 + 21) = Buffer;
  *((_QWORD *)v8 + 22) = v18;
  WimFSFReferenceReadCompletionContext(v8);
  if ( !a1 && !KeAreAllApcsDisabled() )
  {
    v8[200] = 0;
    v21 = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    v20 = FltReadFile(
            *(PFLT_INSTANCE *)(*(_QWORD *)(v13 + 40) + 120LL),
            *(PFILE_OBJECT *)(v13 + 72),
            &ByteOffset,
            v17,
            Buffer,
            4u,
            &BytesRead,
            0,
            0);
    if ( !v8[201] )
    {
      v8[201] = 1;
      KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
    }
    *((_DWORD *)v8 + 58) = BytesRead;
    *((_DWORD *)v8 + 2) = v20;
    WimFSFReadWimCompletion(0, v8);
LABEL_30:
    if ( v20 < 0 )
      goto LABEL_36;
    goto LABEL_31;
  }
  v23 = *(_QWORD *)(v13 + 40);
  v24 = *(struct _FILE_OBJECT **)(v13 + 72);
  RetNewCallbackData = 0;
  v21 = 1;
  v20 = FltAllocateCallbackDataEx(*(PFLT_INSTANCE *)(v23 + 120), v24, 1u, &RetNewCallbackData);
  if ( v20 < 0 )
    goto LABEL_30;
  v20 = FltPropagateIrpExtension(*((_QWORD *)v8 + 3), RetNewCallbackData, 0);
  if ( v20 < 0 )
  {
    FltFreeCallbackData(RetNewCallbackData);
    goto LABEL_37;
  }
  v25 = RetNewCallbackData;
  v26 = a6;
  *((_QWORD *)v8 + 24) = a6;
  v8[200] = 1;
  v25->Iopb->MajorFunction = 3;
  RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = ByteOffset;
  RetNewCallbackData->Iopb->Parameters.Read.Length = v17;
  RetNewCallbackData->Iopb->Parameters.Create.Options = 0;
  RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = v26;
  RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = Buffer;
  WofTraceRedirectedFileIo(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 3) + 16LL) + 8LL), RetNewCallbackData);
  FltSetIoPriorityHintIntoCallbackData(RetNewCallbackData, *((IO_PRIORITY_HINT *)v8 + 32));
  v21 = 0;
  if ( KeAreAllApcsDisabled()
    || (*((_DWORD *)v8 + 36) & 1) != 0
    || FltIsOperationSynchronous(*((PFLT_CALLBACK_DATA *)v8 + 3)) )
  {
    RetNewCallbackData->Iopb->IrpFlags |= 0x143u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    if ( !v8[201] )
    {
      v8[201] = 1;
      KeInitializeEvent((PRKEVENT)(v8 + 208), SynchronizationEvent, 0);
    }
    FltPerformSynchronousIo(RetNewCallbackData);
    WimFSFReadWimCompletion(RetNewCallbackData, v8);
  }
  else
  {
    v20 = 259;
    RetNewCallbackData->Iopb->IrpFlags |= 0x103u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    FltPerformAsynchronousIo(RetNewCallbackData, WimFSFReadWimCompletion, v8);
  }
LABEL_31:
  if ( v8[201] )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    KeWaitForSingleObject(v8 + 208, Executive, 0, 0, 0);
    v20 = *((_DWORD *)v8 + 2);
  }
LABEL_36:
  if ( v21 )
LABEL_37:
    WimFSFReleaseReadCompletionContext(v8);
LABEL_38:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14003cd40  mov     [rsp-40h+RetNewCallbackData], r9
0x14003cd45  mov     [rsp-40h+arg_10], r8b
0x14003cd4a  mov     [rsp-40h+arg_0], cl
0x14003cd4e  push    rbp
0x14003cd4f  push    rbx
0x14003cd50  push    rsi
0x14003cd51  push    rdi
0x14003cd52  push    r12
0x14003cd54  push    r13
0x14003cd56  push    r14
0x14003cd58  push    r15
0x14003cd5a  mov     rbp, rsp
0x14003cd5d  sub     rsp, 68h
0x14003cd61  mov     rdi, [rbp+Context]
0x14003cd68  xor     eax, eax
0x14003cd6a  mov     rbx, r9
0x14003cd6d  movzx   r15d, cl
0x14003cd71  mov     r12b, dl
0x14003cd74  mov     [rbp+var_14], eax
0x14003cd77  mov     qword ptr [rbp+ByteOffset], rax
0x14003cd7b  mov     r13, [rdi+28h]
0x14003cd7f  mov     r14, [rdi+30h]
0x14003cd83  mov     dword ptr [rbp+NumberOfBytes], eax
0x14003cd86  mov     [rbp+var_18], eax
0x14003cd89  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd90  mov     eax, [rcx+2Ch]
0x14003cd93  test    al, 20h
0x14003cd95  jz      short loc_14003CDB2
0x14003cd97  cmp     byte ptr [rcx+29h], 4
0x14003cd9b  jb      short loc_14003CDB2
0x14003cd9d  mov     rcx, [rcx+18h]
0x14003cda1  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cda8  mov     edx, 31h ; '1'
0x14003cdad  call    WPP_SF_
0x14003cdb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cdb9  mov     esi, [rbp+arg_30]
0x14003cdbc  mov     eax, [rcx+2Ch]
0x14003cdbf  test    al, 20h
0x14003cdc1  jz      short loc_14003CDE7
0x14003cdc3  cmp     byte ptr [rcx+29h], 5
0x14003cdc7  jb      short loc_14003CDE7
0x14003cdc9  mov     rax, [rbp+arg_20]
0x14003cdcd  mov     r9, rbx
0x14003cdd0  mov     rcx, [rcx+18h]
0x14003cdd4  mov     dword ptr [rsp+68h+BytesRead], r15d
0x14003cdd9  mov     [rsp+68h+Flags], esi
0x14003cddd  mov     [rsp+68h+Buffer], rax
0x14003cde2  call    WPP_SF_iqDl
0x14003cde7  mov     dword ptr [rdi+74h], 0
0x14003cdee  test    r12b, r12b
0x14003cdf1  jnz     short loc_14003CE37
0x14003cdf3  test    r15b, r15b
0x14003cdf6  jz      short loc_14003CDFE
0x14003cdf8  mov     r9d, [r14+5Ch]
0x14003cdfc  jmp     short loc_14003CE04
0x14003cdfe  mov     r9d, 1
0x14003ce04  lea     rax, [rbp+var_18]
0x14003ce08  mov     r8d, esi
0x14003ce0b  mov     [rsp+68h+BytesRead], rax
0x14003ce10  lea     rdx, [rbp+RetNewCallbackData]
0x14003ce14  lea     rax, [rbp+NumberOfBytes]
0x14003ce18  mov     rcx, r14
0x14003ce1b  mov     qword ptr [rsp+68h+Flags], rax
0x14003ce20  lea     rax, [rbp+ByteOffset]
0x14003ce24  mov     [rsp+68h+Buffer], rax
0x14003ce29  call    WimFSFGetAlignedSizesForIntegrity
0x14003ce2e  mov     r12d, dword ptr [rbp+NumberOfBytes]
0x14003ce32  mov     [rbp+arg_10], al
0x14003ce35  jmp     short loc_14003CE3E
0x14003ce37  mov     qword ptr [rbp+ByteOffset], rbx
0x14003ce3b  mov     r12d, esi
0x14003ce3e  cmp     qword ptr [rbp+ByteOffset], rbx
0x14003ce42  jnz     short loc_14003CE52
0x14003ce44  cmp     r12d, esi
0x14003ce47  jnz     short loc_14003CE52
0x14003ce49  mov     rbx, [rbp+arg_20]
0x14003ce4d  mov     r15, rbx
0x14003ce50  jmp     short loc_14003CE8D
0x14003ce52  mov     r8d, r12d; NumberOfBytes
0x14003ce55  mov     edx, 200h; PoolType
0x14003ce5a  mov     r9d, 44527077h; Tag
0x14003ce60  mov     [rbp+arg_28], 0
0x14003ce68  mov     rcx, r13; Instance
0x14003ce6b  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14003ce72  nop     dword ptr [rax+rax+00h]
0x14003ce77  mov     r15, rax
0x14003ce7a  test    rax, rax
0x14003ce7d  jnz     short loc_14003CE89
0x14003ce7f  mov     ebx, 0C000009Ah
0x14003ce84  jmp     loc_14003D02E
0x14003ce89  mov     rbx, [rbp+arg_20]
0x14003ce8d  mov     eax, [rdi+90h]
0x14003ce93  lea     r13, [rdi+0D0h]
0x14003ce9a  test    al, 1
0x14003ce9c  jz      short loc_14003CEBD
0x14003ce9e  xor     r8d, r8d; State
0x14003cea1  mov     byte ptr [rdi+0C9h], 1
0x14003cea8  mov     rcx, r13; Event
0x14003ceab  lea     edx, [r8+1]; Type
0x14003ceaf  call    cs:__imp_KeInitializeEvent
0x14003ceb6  nop     dword ptr [rax+rax+00h]
0x14003cebb  jmp     short loc_14003CEC4
0x14003cebd  mov     byte ptr [rdi+0C9h], 0
0x14003cec4  mov     al, [rbp+arg_10]
0x14003cec7  mov     rcx, rdi
0x14003ceca  mov     [rdi+98h], al
0x14003ced0  mov     rax, qword ptr [rbp+ByteOffset]
0x14003ced4  mov     [rdi+0A0h], rax
0x14003cedb  mov     eax, [rbp+var_18]
0x14003cede  mov     [rdi+0B8h], eax
0x14003cee4  mov     [rdi+9Ch], esi
0x14003ceea  mov     [rdi+0A8h], r15
0x14003cef1  mov     [rdi+0B0h], rbx
0x14003cef8  call    WimFSFReferenceReadCompletionContext
0x14003cefd  xor     ebx, ebx
0x14003ceff  cmp     [rbp+arg_0], bl
0x14003cf02  jnz     loc_14003D06E
0x14003cf08  call    cs:__imp_KeAreAllApcsDisabled
0x14003cf0f  nop     dword ptr [rax+rax+00h]
0x14003cf14  test    al, al
0x14003cf16  jnz     loc_14003D06E
0x14003cf1c  mov     [rdi+0C8h], bl
0x14003cf22  mov     sil, bl
0x14003cf25  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf2c  mov     eax, [rcx+2Ch]
0x14003cf2f  test    al, 20h
0x14003cf31  jz      short loc_14003CF4C
0x14003cf33  cmp     byte ptr [rcx+29h], 5
0x14003cf37  jb      short loc_14003CF4C
0x14003cf39  mov     rcx, [rcx+18h]
0x14003cf3d  lea     edx, [rbx+35h]
0x14003cf40  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cf47  call    WPP_SF_
0x14003cf4c  mov     rcx, [r14+28h]
0x14003cf50  lea     rax, [rbp+var_14]
0x14003cf54  mov     rdx, [r14+48h]; FileObject
0x14003cf58  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14003cf5c  mov     [rsp+68h+CallbackContext], rbx; CallbackContext
0x14003cf61  mov     r9d, r12d; Length
0x14003cf64  mov     [rsp+68h+CallbackRoutine], rbx; CallbackRoutine
0x14003cf69  mov     rcx, [rcx+78h]; InitiatingInstance
0x14003cf6d  mov     [rsp+68h+BytesRead], rax; BytesRead
0x14003cf72  mov     [rsp+68h+Flags], 4; Flags
0x14003cf7a  mov     [rsp+68h+Buffer], r15; Buffer
0x14003cf7f  call    cs:__imp_FltReadFile
0x14003cf86  nop     dword ptr [rax+rax+00h]
0x14003cf8b  xor     r14d, r14d
0x14003cf8e  mov     ebx, eax
0x14003cf90  cmp     [rdi+0C9h], r14b
0x14003cf97  jnz     short loc_14003CFB6
0x14003cf99  xor     r8d, r8d; State
0x14003cf9c  mov     byte ptr [rdi+0C9h], 1
0x14003cfa3  lea     edx, [r14+1]; Type
0x14003cfa7  mov     rcx, r13; Event
0x14003cfaa  call    cs:__imp_KeInitializeEvent
0x14003cfb1  nop     dword ptr [rax+rax+00h]
0x14003cfb6  mov     ecx, [rbp+var_14]
0x14003cfb9  mov     rdx, rdi; Context
0x14003cfbc  mov     [rdi+0E8h], ecx
0x14003cfc2  xor     ecx, ecx; CallbackData
0x14003cfc4  mov     [rdi+8], ebx
0x14003cfc7  call    WimFSFReadWimCompletion
0x14003cfcc  test    ebx, ebx
0x14003cfce  js      short loc_14003D021
0x14003cfd0  cmp     [rdi+0C9h], r14b
0x14003cfd7  jz      short loc_14003D021
0x14003cfd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfe0  mov     eax, [rcx+2Ch]
0x14003cfe3  test    al, 20h
0x14003cfe5  jz      short loc_14003D002
0x14003cfe7  cmp     byte ptr [rcx+29h], 5
0x14003cfeb  jb      short loc_14003D002
0x14003cfed  mov     rcx, [rcx+18h]
0x14003cff1  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003cff8  mov     edx, 36h ; '6'
0x14003cffd  call    WPP_SF_
0x14003d002  xor     r9d, r9d; Alertable
0x14003d005  mov     [rsp+68h+Buffer], r14; Timeout
0x14003d00a  xor     r8d, r8d; WaitMode
0x14003d00d  xor     edx, edx; WaitReason
0x14003d00f  mov     rcx, r13; Object
0x14003d012  call    cs:__imp_KeWaitForSingleObject
0x14003d019  nop     dword ptr [rax+rax+00h]
0x14003d01e  mov     ebx, [rdi+8]
0x14003d021  test    sil, sil
0x14003d024  jz      short loc_14003D02E
0x14003d026  mov     rcx, rdi; Entry
0x14003d029  call    WimFSFReleaseReadCompletionContext
0x14003d02e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d035  mov     eax, [rcx+2Ch]
0x14003d038  test    al, 20h
0x14003d03a  jz      short loc_14003D05A
0x14003d03c  cmp     byte ptr [rcx+29h], 4
0x14003d040  jb      short loc_14003D05A
0x14003d042  mov     rcx, [rcx+18h]
0x14003d046  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003d04d  mov     edx, 37h ; '7'
0x14003d052  mov     r9d, ebx
0x14003d055  call    WPP_SF_d
0x14003d05a  mov     eax, ebx
0x14003d05c  add     rsp, 68h
0x14003d060  pop     r15
0x14003d062  pop     r14
0x14003d064  pop     r13
0x14003d066  pop     r12
0x14003d068  pop     rdi
0x14003d069  pop     rsi
0x14003d06a  pop     rbx
0x14003d06b  pop     rbp
0x14003d06c  retn
0x14003d06e  mov     rcx, [r14+28h]
0x14003d072  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14003d076  mov     rdx, [r14+48h]; FileObject
0x14003d07a  mov     r8d, 1; Flags
0x14003d080  mov     [rbp+RetNewCallbackData], rbx
0x14003d084  mov     sil, 1
0x14003d087  mov     rcx, [rcx+78h]; Instance
0x14003d08b  call    cs:__imp_FltAllocateCallbackDataEx
0x14003d092  nop     dword ptr [rax+rax+00h]
0x14003d097  xor     r14d, r14d
0x14003d09a  mov     ebx, eax
0x14003d09c  test    eax, eax
0x14003d09e  js      loc_14003CFCC
0x14003d0a4  mov     rdx, [rbp+RetNewCallbackData]
0x14003d0a8  xor     r8d, r8d
0x14003d0ab  mov     rcx, [rdi+18h]
0x14003d0af  call    cs:__imp_FltPropagateIrpExtension
0x14003d0b6  nop     dword ptr [rax+rax+00h]
0x14003d0bb  mov     ebx, eax
0x14003d0bd  test    eax, eax
0x14003d0bf  jns     short loc_14003D0D6
0x14003d0c1  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003d0c5  call    cs:__imp_FltFreeCallbackData
0x14003d0cc  nop     dword ptr [rax+rax+00h]
0x14003d0d1  jmp     loc_14003D026
0x14003d0d6  mov     rax, [rbp+RetNewCallbackData]
0x14003d0da  mov     rdx, [rbp+arg_28]
0x14003d0de  mov     [rdi+0C0h], rdx
0x14003d0e5  mov     [rdi+0C8h], sil
0x14003d0ec  mov     rcx, [rax+10h]
0x14003d0f0  mov     byte ptr [rcx+4], 3
0x14003d0f4  mov     rax, [rbp+RetNewCallbackData]
0x14003d0f8  mov     rcx, [rax+10h]
0x14003d0fc  mov     rax, qword ptr [rbp+ByteOffset]
0x14003d100  mov     [rcx+28h], rax
0x14003d104  mov     rax, [rbp+RetNewCallbackData]
0x14003d108  mov     rcx, [rax+10h]
0x14003d10c  mov     [rcx+18h], r12d
0x14003d110  mov     rax, [rbp+RetNewCallbackData]
0x14003d114  mov     rcx, [rax+10h]
0x14003d118  mov     [rcx+20h], r14d
0x14003d11c  mov     rax, [rbp+RetNewCallbackData]
0x14003d120  mov     rcx, [rax+10h]
0x14003d124  mov     [rcx+38h], rdx
0x14003d128  mov     rax, [rbp+RetNewCallbackData]
0x14003d12c  mov     rcx, [rax+10h]
0x14003d130  mov     [rcx+30h], r15
0x14003d134  mov     rax, [rdi+18h]
0x14003d138  mov     rdx, [rbp+RetNewCallbackData]
0x14003d13c  mov     rcx, [rax+10h]
0x14003d140  mov     rcx, [rcx+8]
0x14003d144  call    WofTraceRedirectedFileIo
0x14003d149  mov     edx, [rdi+80h]; PriorityHint
0x14003d14f  mov     rcx, [rbp+RetNewCallbackData]; Data
0x14003d153  call    cs:__imp_FltSetIoPriorityHintIntoCallbackData
0x14003d15a  nop     dword ptr [rax+rax+00h]
0x14003d15f  mov     sil, r14b
0x14003d162  call    cs:__imp_KeAreAllApcsDisabled
0x14003d169  nop     dword ptr [rax+rax+00h]
0x14003d16e  test    al, al
0x14003d170  jnz     short loc_14003D1E7
0x14003d172  mov     eax, [rdi+90h]
0x14003d178  test    al, 1
0x14003d17a  jnz     short loc_14003D1E7
0x14003d17c  mov     rcx, [rdi+18h]; CallbackData
0x14003d180  call    cs:__imp_FltIsOperationSynchronous
0x14003d187  nop     dword ptr [rax+rax+00h]
0x14003d18c  test    al, al
0x14003d18e  jnz     short loc_14003D1E7
0x14003d190  mov     rax, [rbp+RetNewCallbackData]
0x14003d194  mov     ebx, 103h
0x14003d199  mov     rcx, [rax+10h]
0x14003d19d  or      [rcx], ebx
0x14003d19f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d1a6  mov     eax, [rcx+2Ch]
0x14003d1a9  test    al, 20h
0x14003d1ab  jz      short loc_14003D1C8
0x14003d1ad  cmp     byte ptr [rcx+29h], 5
0x14003d1b1  jb      short loc_14003D1C8
0x14003d1b3  mov     rcx, [rcx+18h]
0x14003d1b7  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003d1be  mov     edx, 34h ; '4'
0x14003d1c3  call    WPP_SF_
0x14003d1c8  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003d1cc  lea     rdx, WimFSFReadWimCompletion; CallbackRoutine
0x14003d1d3  mov     r8, rdi; CallbackContext
0x14003d1d6  call    cs:__imp_FltPerformAsynchronousIo
0x14003d1dd  nop     dword ptr [rax+rax+00h]
0x14003d1e2  jmp     loc_14003CFD0
0x14003d1e7  mov     rax, [rbp+RetNewCallbackData]
  ... truncated ...
```
