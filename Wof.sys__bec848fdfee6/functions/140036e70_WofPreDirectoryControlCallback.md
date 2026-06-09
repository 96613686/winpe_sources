# WofPreDirectoryControlCallback

- ea: `0x140036e70`
- end: `0x1400376de`
- name: `WofPreDirectoryControlCallback`
- size: `2158`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400014d0`
- `0x14002378c`
- `0x14002382c`
- `0x140036e70`
- `0x1400376f0`
- `0x140037d20`
- `0x14003ba5c`
- `0x14003bf4c`
- `0x14003e0b8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400372c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037313`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400372c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037313`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037116`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037116`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f5a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003735c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f5a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003735c`
- `FLTMGR!FltPerformSynchronousIo` at `0x140037040`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003749b`
- `FLTMGR!FltPerformSynchronousIo` at `0x140037040`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003749b`
- `FLTMGR!FltLockUserBuffer` at `0x140037262`
- `FLTMGR!FltLockUserBuffer` at `0x140037609`
- `FLTMGR!FltLockUserBuffer` at `0x140037262`
- `FLTMGR!FltLockUserBuffer` at `0x140037609`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x140036f86`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400373bb`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x140036f86`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400373bb`
- `FLTMGR!FltPropagateIrpExtension` at `0x140036fa4`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400373d9`
- `FLTMGR!FltPropagateIrpExtension` at `0x140036fa4`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400373d9`
- `FLTMGR!FltFreeCallbackData` at `0x140037059`
- `FLTMGR!FltFreeCallbackData` at `0x1400374b5`
- `FLTMGR!FltFreeCallbackData` at `0x1400376c5`
- `FLTMGR!FltFreeCallbackData` at `0x140037059`
- `FLTMGR!FltFreeCallbackData` at `0x1400374b5`
- `FLTMGR!FltFreeCallbackData` at `0x1400376c5`
- `FLTMGR!FltReleaseContext` at `0x140036ede`
- `FLTMGR!FltReleaseContext` at `0x140037175`
- `FLTMGR!FltReleaseContext` at `0x140036ede`
- `FLTMGR!FltReleaseContext` at `0x140037175`

## pseudocode

```c
__int64 __fastcall WofPreDirectoryControlCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v3; // ebx
  NTSTATUS VolumeContext; // r14d
  _DWORD *PoolWithTag; // r15
  PFLT_IO_PARAMETER_BLOCK v8; // rdi
  unsigned __int64 LowPart; // r13
  unsigned __int64 v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // edx
  DWORD v13; // r14d
  unsigned int v14; // edi
  ULONG v15; // edi
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS Status; // edi
  NTSTATUS v19; // r12d
  PFLT_IO_PARAMETER_BLOCK v20; // rax
  unsigned int v21; // edi
  PVOID v22; // r9
  KPROCESSOR_MODE RequestorMode; // cl
  DWORD v24; // r14d
  DWORD v25; // r14d
  DWORD v26; // r14d
  DWORD v27; // r14d
  NTSTATUS v29; // eax
  ULONG Length; // eax
  int v31; // eax
  LARGE_INTEGER AllocationSize; // rcx
  PVOID v33; // r13
  LARGE_INTEGER v34; // rcx
  unsigned int v35; // ecx
  ULONG v36; // edi
  char v37; // r13
  struct _FILE_OBJECT *v38; // rdx
  struct _FLT_INSTANCE *v39; // rcx
  PFLT_IO_PARAMETER_BLOCK v40; // rcx
  UCHAR v41; // al
  int v42; // eax
  ULONG Priority; // [rsp+28h] [rbp-48h]
  char v44; // [rsp+40h] [rbp-30h]
  unsigned int v45; // [rsp+44h] [rbp-2Ch] BYREF
  ULONG v46; // [rsp+48h] [rbp-28h]
  unsigned int Information; // [rsp+4Ch] [rbp-24h]
  ULONG v48; // [rsp+50h] [rbp-20h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+58h] [rbp-18h] BYREF
  PVOID EaBuffer; // [rsp+60h] [rbp-10h]
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp+40h] BYREF
  UCHAR OperationFlags; // [rsp+C8h] [rbp+58h]

  Iopb = CallbackData->Iopb;
  RetNewCallbackData = 0;
  v3 = 1;
  v45 = 0;
  Context = 0;
  if ( Iopb->MinorFunction != 1 )
    return v3;
  VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
  if ( VolumeContext >= 0 )
  {
    if ( (*((_DWORD *)Context + 14) & 1) == 0 )
    {
      PoolWithTag = 0;
      FltReleaseContext(Context);
      v8 = CallbackData->Iopb;
      LowPart = v8->Parameters.Read.ByteOffset.LowPart;
      if ( (unsigned int)LowPart > 0x3F || (v10 = 0x900000600000000EuLL, !_bittest64((const __int64 *)&v10, LowPart)) )
      {
        if ( (unsigned int)(LowPart - 78) > 3 )
        {
          if ( (_DWORD)LowPart != 33 || !byte_140018454 )
            goto LABEL_29;
          v3 = 4;
          Length = v8->Parameters.Read.Length;
          OperationFlags = v8->OperationFlags;
          v46 = Length;
          if ( v8->Parameters.Create.AllocationSize.QuadPart )
          {
            v31 = FltLockUserBuffer(CallbackData);
            VolumeContext = v31;
            if ( v31 < 0 )
            {
              CallbackData->IoStatus.Status = v31;
              goto LABEL_29;
            }
            AllocationSize = CallbackData->Iopb->Parameters.Create.AllocationSize;
            if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
              v33 = *(PVOID *)(AllocationSize.QuadPart + 24);
            else
              v33 = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
            EaBuffer = v33;
            if ( !v33 )
            {
              CallbackData->IoStatus.Status = -1073741801;
              goto LABEL_29;
            }
          }
          else
          {
            EaBuffer = v8->Parameters.Create.EaBuffer;
            if ( (CallbackData->Flags & 8) == 0 )
            {
              LOBYTE(Context) = CallbackData->RequestorMode;
              goto LABEL_64;
            }
          }
          LOBYTE(Context) = 0;
LABEL_64:
          v35 = v8->Parameters.Read.Length;
          if ( v35 > 0x10000 )
            v35 = 0x10000;
          v48 = v35;
          PoolWithTag = ExAllocatePoolWithTag(PagedPool, v35, 0x44666F57u);
          if ( PoolWithTag )
          {
            v36 = 0;
            v44 = 1;
            v37 = 0;
            while ( VolumeContext >= 0 && !v37 && v36 < v46 )
            {
              v38 = *(struct _FILE_OBJECT **)(a2 + 32);
              v39 = *(struct _FLT_INSTANCE **)(a2 + 24);
              v45 = 0;
              v16 = FltAllocateCallbackDataEx(v39, v38, 1u, &RetNewCallbackData);
              if ( v16 < 0 )
                goto LABEL_98;
              v16 = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
              if ( v16 < 0 )
                goto LABEL_98;
              RetNewCallbackData->Iopb->MajorFunction = 12;
              RetNewCallbackData->Iopb->MinorFunction = 1;
              RetNewCallbackData->Iopb->Parameters.Read.Length = v48;
              RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = 33;
              v40 = RetNewCallbackData->Iopb;
              if ( v44 )
              {
                v40->Parameters.QueryEa.EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
                RetNewCallbackData->Iopb->Parameters.Create.EaLength = CallbackData->Iopb->Parameters.Create.EaLength;
              }
              else
              {
                v40->Parameters.QueryEa.EaList = 0;
                RetNewCallbackData->Iopb->Parameters.Create.EaLength = 0;
              }
              RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = PoolWithTag;
              RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
              v41 = OperationFlags;
              RetNewCallbackData->Iopb->OperationFlags = OperationFlags;
              OperationFlags = v41 & 0xFA;
              FltPerformSynchronousIo(RetNewCallbackData);
              VolumeContext = RetNewCallbackData->IoStatus.Status;
              Information = RetNewCallbackData->IoStatus.Information;
              FltFreeCallbackData(RetNewCallbackData);
              RetNewCallbackData = 0;
              CallbackData->IoStatus.Status = VolumeContext;
              if ( VolumeContext == -2147483642 )
              {
                if ( v36 + Information )
                {
                  CallbackData->IoStatus.Status = 0;
                  v37 = 1;
                }
              }
              else if ( VolumeContext >= 0 )
              {
                v16 = WofFilterReparseEnumerate(
                        (unsigned __int8)Context,
                        PoolWithTag,
                        Information,
                        (__int64)EaBuffer + v36,
                        v46 - v36,
                        (char)Context,
                        &v45);
                VolumeContext = v16;
                if ( v16 < 0 )
                  goto LABEL_98;
                v36 += v45;
                if ( v46 - v36 < 0x10 )
                  v37 = 1;
                if ( (OperationFlags & 2) != 0 && v45 )
                  v37 = 1;
              }
              v44 = 0;
            }
            CallbackData->IoStatus.Information = v36;
          }
          else
          {
            CallbackData->IoStatus.Status = -1073741670;
          }
LABEL_29:
          if ( RetNewCallbackData )
          {
            FltFreeCallbackData(RetNewCallbackData);
            RetNewCallbackData = 0;
          }
          if ( !PoolWithTag )
            return v3;
          goto LABEL_32;
        }
      }
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v3 = 4;
      switch ( (int)LowPart )
      {
        case 1:
          v12 = 80;
          v11 = 64;
          v13 = 78;
          break;
        case 2:
          v12 = 80;
          v11 = 68;
          v13 = 78;
          break;
        case 3:
          v12 = 106;
          v11 = 94;
          v13 = 79;
          break;
        case 37:
          v12 = 106;
          v11 = 104;
          v13 = 79;
          break;
        case 38:
        case 78:
          v11 = 80;
          v12 = 80;
          v13 = 78;
          break;
        case 60:
          v11 = 88;
          v13 = 60;
          goto LABEL_96;
        case 63:
          v11 = 114;
          v13 = 63;
          goto LABEL_96;
        case 79:
          v12 = 106;
          v13 = 79;
          v11 = 106;
          break;
        case 80:
          v11 = 96;
          v13 = 80;
          goto LABEL_96;
        case 81:
          v11 = 122;
          v13 = 81;
LABEL_96:
          v12 = v11;
          break;
        default:
          break;
      }
      v14 = v12 + v8->Parameters.Read.Length;
      if ( v14 < v12 || v14 < v11 )
      {
        CallbackData->IoStatus.Status = -1073741811;
        goto LABEL_29;
      }
      v15 = v14 - v11;
      if ( v15 > 0x10000 )
        v15 = 0x10000;
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, v15, 0x44666F57u);
      if ( !PoolWithTag )
      {
        CallbackData->IoStatus.Status = -1073741670;
        goto LABEL_29;
      }
      v16 = FltAllocateCallbackDataEx(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 1u, &RetNewCallbackData);
      if ( v16 < 0 )
      {
LABEL_98:
        CallbackData->IoStatus.Status = v16;
        goto LABEL_29;
      }
      v17 = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
      if ( v17 < 0 )
      {
        CallbackData->IoStatus.Status = v17;
        goto LABEL_29;
      }
      RetNewCallbackData->Iopb->MajorFunction = 12;
      RetNewCallbackData->Iopb->MinorFunction = 1;
      RetNewCallbackData->Iopb->Parameters.Read.Length = v15;
      RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = v13;
      RetNewCallbackData->Iopb->Parameters.QueryEa.EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
      RetNewCallbackData->Iopb->Parameters.Create.EaLength = CallbackData->Iopb->Parameters.Create.EaLength;
      RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = PoolWithTag;
      RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
      RetNewCallbackData->Iopb->OperationFlags = CallbackData->Iopb->OperationFlags;
      FltPerformSynchronousIo(RetNewCallbackData);
      Status = RetNewCallbackData->IoStatus.Status;
      LODWORD(Context) = RetNewCallbackData->IoStatus.Information;
      FltFreeCallbackData(RetNewCallbackData);
      v19 = 0;
      RetNewCallbackData = 0;
      CallbackData->IoStatus.Status = Status;
      if ( Status != -2147483643 )
        v19 = Status;
      if ( v19 < 0 )
      {
LABEL_32:
        ExFreePoolWithTag(PoolWithTag, 0);
        return v3;
      }
      v20 = CallbackData->Iopb;
      v21 = v20->Parameters.Read.Length;
      if ( v20->Parameters.Create.AllocationSize.QuadPart )
      {
        v42 = FltLockUserBuffer(CallbackData);
        v19 = v42;
        if ( v42 < 0 )
        {
          CallbackData->IoStatus.Status = v42;
          goto LABEL_29;
        }
        v34 = CallbackData->Iopb->Parameters.Create.AllocationSize;
        if ( (*(_BYTE *)(v34.QuadPart + 10) & 5) != 0 )
          v22 = *(PVOID *)(v34.QuadPart + 24);
        else
          v22 = MmMapLockedPagesSpecifyCache((PMDL)v34.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
        if ( !v22 )
        {
          CallbackData->IoStatus.Status = -1073741801;
          goto LABEL_29;
        }
      }
      else
      {
        v22 = v20->Parameters.Create.EaBuffer;
        if ( (CallbackData->Flags & 8) == 0 )
        {
          RequestorMode = CallbackData->RequestorMode;
          goto LABEL_20;
        }
      }
      RequestorMode = 0;
LABEL_20:
      if ( v13 == 79 )
      {
        LOBYTE(Priority) = RequestorMode;
        v29 = WofMungeDirectoryEnumerateWithShortnameFileId64(
                (unsigned int)LowPart,
                PoolWithTag,
                (unsigned int)Context,
                v22,
                v21,
                Priority,
                &v45);
      }
      else
      {
        v24 = v13 - 60;
        if ( v24 )
        {
          v25 = v24 - 3;
          if ( v25 )
          {
            v26 = v25 - 15;
            if ( !v26 )
            {
              v19 = WofMungeDirectoryEnumerateWithoutShortnameFileId64(
                      LowPart,
                      PoolWithTag,
                      (unsigned int)Context,
                      (__int64)v22,
                      v21,
                      RequestorMode,
                      &v45);
LABEL_26:
              if ( v19 < 0 )
                CallbackData->IoStatus.Status = v19;
              else
                CallbackData->IoStatus.Information = v45;
              goto LABEL_29;
            }
            v27 = v26 - 2;
            if ( v27 )
            {
              if ( v27 != 1 )
                goto LABEL_26;
              LOBYTE(Priority) = RequestorMode;
              v29 = WofMungeDirectoryEnumerateWithShortnameFileIdAll(
                      (unsigned int)LowPart,
                      PoolWithTag,
                      (unsigned int)Context,
                      v22,
                      v21,
                      Priority,
                      &v45);
            }
            else
            {
              LOBYTE(Priority) = RequestorMode;
              v29 = WofMungeDirectoryEnumerateWithoutShortnameFileIdAll(
                      (unsigned int)LowPart,
                      PoolWithTag,
                      (unsigned int)Context,
                      v22,
                      v21,
                      Priority,
                      &v45);
            }
          }
          else
          {
            LOBYTE(Priority) = RequestorMode;
            v29 = WofMungeDirectoryEnumerateWithShortname(
                    (unsigned int)LowPart,
                    PoolWithTag,
                    (unsigned int)Context,
                    v22,
                    v21,
                    Priority,
                    &v45);
          }
        }
        else
        {
          v29 = WofMungeDirectoryEnumerateWithoutShortname(
                  LowPart,
                  PoolWithTag,
                  (unsigned int)Context,
                  (__int64)v22,
                  v21,
                  RequestorMode,
                  &v45);
        }
      }
      v19 = v29;
      goto LABEL_26;
    }
    FltReleaseContext(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x140036e70  push    rbp
0x140036e72  push    rbx
0x140036e73  push    rsi
0x140036e74  push    rdi
0x140036e75  push    r12
0x140036e77  push    r14
0x140036e79  push    r15
0x140036e7b  mov     rbp, rsp
0x140036e7e  sub     rsp, 70h
0x140036e82  mov     rax, [rcx+10h]
0x140036e86  xor     edi, edi
0x140036e88  mov     r15d, 1
0x140036e8e  mov     [rbp+RetNewCallbackData], rdi
0x140036e92  mov     ebx, r15d
0x140036e95  mov     [rbp+var_2C], edi
0x140036e98  mov     r12, rdx
0x140036e9b  mov     [rbp+Context], rdi
0x140036e9f  mov     rsi, rcx
0x140036ea2  cmp     [rax+5], bl
0x140036ea5  jnz     loc_14003712A
0x140036eab  mov     rcx, [r12+18h]; Instance
0x140036eb0  lea     rdx, [rbp+Context]
0x140036eb4  call    WofGetVolumeContext
0x140036eb9  mov     r14d, eax
0x140036ebc  test    eax, eax
0x140036ebe  js      loc_140037181
0x140036ec4  mov     rcx, [rbp+Context]; Context
0x140036ec8  mov     eax, [rcx+38h]
0x140036ecb  test    bl, al
0x140036ecd  jnz     loc_140037175
0x140036ed3  mov     [rsp+70h+arg_8], r13
0x140036edb  mov     r15d, edi
0x140036ede  call    cs:__imp_FltReleaseContext
0x140036ee5  nop     dword ptr [rax+rax+00h]
0x140036eea  mov     rdi, [rsi+10h]
0x140036eee  mov     r13d, [rdi+28h]
0x140036ef2  cmp     r13d, 3Fh ; '?'
0x140036ef6  ja      loc_14003721F
0x140036efc  mov     rcx, 900000600000000Eh
0x140036f06  bt      rcx, r13
0x140036f0a  jnb     loc_14003721F
0x140036f10  xor     r8d, r8d
0x140036f13  lea     eax, [r13-1]; switch 81 cases
0x140036f17  xor     edx, edx
0x140036f19  xor     r14d, r14d
0x140036f1c  mov     ebx, 4
0x140036f21  cmp     eax, 50h
0x140036f24  jbe     loc_14003713C
0x140036f2a  mov     edi, [rdi+18h]; jumptable 0000000140037159 default case, cases 4-36,39-59,61,62,64-77
0x140036f2d  add     edi, edx
0x140036f2f  cmp     edi, edx
0x140036f31  jb      loc_1400370F8
0x140036f37  cmp     edi, r8d
0x140036f3a  jb      loc_1400370F8
0x140036f40  sub     edi, r8d
0x140036f43  mov     eax, 10000h
0x140036f48  cmp     edi, eax
0x140036f4a  mov     ecx, 1; PoolType
0x140036f4f  mov     r8d, 44666F57h; Tag
0x140036f55  cmova   edi, eax
0x140036f58  mov     edx, edi; NumberOfBytes
0x140036f5a  call    cs:__imp_ExAllocatePoolWithTag
0x140036f61  nop     dword ptr [rax+rax+00h]
0x140036f66  mov     r15, rax
0x140036f69  test    rax, rax
0x140036f6c  jz      loc_1400375F2
0x140036f72  mov     rdx, [r12+20h]; FileObject
0x140036f77  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140036f7b  mov     rcx, [r12+18h]; Instance
0x140036f80  mov     r8d, 1; Flags
0x140036f86  call    cs:__imp_FltAllocateCallbackDataEx
0x140036f8d  nop     dword ptr [rax+rax+00h]
0x140036f92  test    eax, eax
0x140036f94  js      loc_1400375FE
0x140036f9a  mov     rdx, [rbp+RetNewCallbackData]
0x140036f9e  xor     r8d, r8d
0x140036fa1  mov     rcx, rsi
0x140036fa4  call    cs:__imp_FltPropagateIrpExtension
0x140036fab  nop     dword ptr [rax+rax+00h]
0x140036fb0  test    eax, eax
0x140036fb2  js      loc_1400371C3
0x140036fb8  mov     rax, [rbp+RetNewCallbackData]
0x140036fbc  mov     rcx, [rax+10h]
0x140036fc0  mov     byte ptr [rcx+4], 0Ch
0x140036fc4  mov     rax, [rbp+RetNewCallbackData]
0x140036fc8  mov     rcx, [rax+10h]
0x140036fcc  mov     byte ptr [rcx+5], 1
0x140036fd0  mov     rax, [rbp+RetNewCallbackData]
0x140036fd4  mov     rcx, [rax+10h]
0x140036fd8  mov     [rcx+18h], edi
0x140036fdb  mov     rax, [rbp+RetNewCallbackData]
0x140036fdf  mov     rcx, [rax+10h]
0x140036fe3  mov     [rcx+28h], r14d
0x140036fe7  mov     rax, [rbp+RetNewCallbackData]
0x140036feb  mov     rdx, [rsi+10h]
0x140036fef  mov     rcx, [rax+10h]
0x140036ff3  mov     rax, [rdx+20h]
0x140036ff7  mov     [rcx+20h], rax
0x140036ffb  mov     rax, [rbp+RetNewCallbackData]
0x140036fff  mov     rdx, [rsi+10h]
0x140037003  mov     rcx, [rax+10h]
0x140037007  mov     eax, [rdx+30h]
0x14003700a  mov     [rcx+30h], eax
0x14003700d  mov     rax, [rbp+RetNewCallbackData]
0x140037011  mov     rcx, [rax+10h]
0x140037015  mov     [rcx+38h], r15
0x140037019  mov     rax, [rbp+RetNewCallbackData]
0x14003701d  mov     rcx, [rax+10h]
0x140037021  mov     qword ptr [rcx+40h], 0
0x140037029  mov     rax, [rbp+RetNewCallbackData]
0x14003702d  mov     rdx, [rsi+10h]
0x140037031  mov     rcx, [rax+10h]
0x140037035  movzx   eax, byte ptr [rdx+6]
0x140037039  mov     [rcx+6], al
0x14003703c  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140037040  call    cs:__imp_FltPerformSynchronousIo
0x140037047  nop     dword ptr [rax+rax+00h]
0x14003704c  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140037050  mov     eax, [rcx+20h]
0x140037053  mov     edi, [rcx+18h]
0x140037056  mov     dword ptr [rbp+Context], eax
0x140037059  call    cs:__imp_FltFreeCallbackData
0x140037060  nop     dword ptr [rax+rax+00h]
0x140037065  xor     r12d, r12d
0x140037068  mov     [rbp+RetNewCallbackData], 0
0x140037070  cmp     edi, 80000005h
0x140037076  mov     [rsi+18h], edi
0x140037079  cmovnz  r12d, edi
0x14003707d  test    r12d, r12d
0x140037080  js      loc_140037111
0x140037086  mov     rax, [rsi+10h]
0x14003708a  cmp     qword ptr [rax+40h], 0
0x14003708f  mov     edi, [rax+18h]
0x140037092  jnz     loc_140037606
0x140037098  mov     r9, [rax+38h]
0x14003709c  mov     eax, [rsi]
0x14003709e  test    al, 8
0x1400370a0  jnz     loc_1400371BC
0x1400370a6  movzx   ecx, byte ptr [rsi+50h]
0x1400370aa  cmp     r14d, 4Fh ; 'O'
0x1400370ae  jz      loc_140037194
0x1400370b4  sub     r14d, 3Ch ; '<'
0x1400370b8  jz      loc_140037697
0x1400370be  sub     r14d, 3
0x1400370c2  jz      loc_140037672
0x1400370c8  sub     r14d, 0Fh
0x1400370cc  jz      loc_1400371F7
0x1400370d2  sub     r14d, 2
0x1400370d6  jz      loc_14003764D
0x1400370dc  cmp     r14d, 1
0x1400370e0  jz      loc_140037628
0x1400370e6  test    r12d, r12d
0x1400370e9  js      loc_1400376BC
0x1400370ef  mov     eax, [rbp+var_2C]
0x1400370f2  mov     [rsi+20h], rax
0x1400370f6  jmp     short loc_1400370FF
0x1400370f8  mov     dword ptr [rsi+18h], 0C000000Dh
0x1400370ff  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140037103  test    rcx, rcx
0x140037106  jnz     loc_1400376C5
0x14003710c  test    r15, r15
0x14003710f  jz      short loc_140037122
0x140037111  xor     edx, edx; Tag
0x140037113  mov     rcx, r15; P
0x140037116  call    cs:__imp_ExFreePoolWithTag
0x14003711d  nop     dword ptr [rax+rax+00h]
0x140037122  mov     r13, [rsp+70h+arg_8]
0x14003712a  mov     eax, ebx
0x14003712c  add     rsp, 70h
0x140037130  pop     r15
0x140037132  pop     r14
0x140037134  pop     r12
0x140037136  pop     rdi
0x140037137  pop     rsi
0x140037138  pop     rbx
0x140037139  pop     rbp
0x14003713a  retn
0x14003713c  lea     r9, cs:140000000h
0x140037143  cdqe
0x140037145  movzx   eax, ds:(byte_1400144AC - 140000000h)[r9+rax]
0x14003714e  mov     ecx, ds:(jpt_140037159 - 140000000h)[r9+rax*4]
0x140037156  add     rcx, r9
0x140037159  jmp     rcx; switch jump
0x14003715f  mov     edx, 6Ah ; 'j'; jumptable 0000000140037159 case 3
0x140037164  mov     r8d, 5Eh ; '^'
0x14003716a  mov     r14d, 4Fh ; 'O'
0x140037170  jmp     def_140037159; jumptable 0000000140037159 default case, cases 4-36,39-59,61,62,64-77
0x140037175  call    cs:__imp_FltReleaseContext
0x14003717c  nop     dword ptr [rax+rax+00h]
0x140037181  mov     eax, r15d
0x140037184  add     rsp, 70h
0x140037188  pop     r15
0x14003718a  pop     r14
0x14003718c  pop     r12
0x14003718e  pop     rdi
0x14003718f  pop     rsi
0x140037190  pop     rbx
0x140037191  pop     rbp
0x140037192  retn
0x140037194  mov     r8d, dword ptr [rbp+Context]
0x140037198  lea     rax, [rbp+var_2C]
0x14003719c  mov     [rsp+70h+var_40], rax
0x1400371a1  mov     rdx, r15
0x1400371a4  mov     byte ptr [rsp+70h+Priority], cl
0x1400371a8  mov     ecx, r13d
0x1400371ab  mov     [rsp+70h+BugCheckOnFailure], edi
0x1400371af  call    WofMungeDirectoryEnumerateWithShortnameFileId64
0x1400371b4  mov     r12d, eax
0x1400371b7  jmp     loc_1400370E6
0x1400371bc  xor     cl, cl
0x1400371be  jmp     loc_1400370AA
0x1400371c3  mov     [rsi+18h], eax
0x1400371c6  jmp     loc_1400370FF
0x1400371cb  mov     edx, 50h ; 'P'; jumptable 0000000140037159 case 2
0x1400371d0  mov     r8d, 44h ; 'D'
0x1400371d6  mov     r14d, 4Eh ; 'N'
0x1400371dc  jmp     def_140037159; jumptable 0000000140037159 default case, cases 4-36,39-59,61,62,64-77
0x1400371e1  mov     edx, 6Ah ; 'j'; jumptable 0000000140037159 case 37
0x1400371e6  mov     r8d, 68h ; 'h'
0x1400371ec  mov     r14d, 4Fh ; 'O'
0x1400371f2  jmp     def_140037159; jumptable 0000000140037159 default case, cases 4-36,39-59,61,62,64-77
0x1400371f7  mov     r8d, dword ptr [rbp+Context]
0x1400371fb  lea     rax, [rbp+var_2C]
0x1400371ff  mov     [rsp+70h+var_40], rax
0x140037204  mov     rdx, r15
0x140037207  mov     byte ptr [rsp+70h+Priority], cl
0x14003720b  mov     ecx, r13d
0x14003720e  mov     [rsp+70h+BugCheckOnFailure], edi
0x140037212  call    WofMungeDirectoryEnumerateWithoutShortnameFileId64
0x140037217  mov     r12d, eax
0x14003721a  jmp     loc_1400370E6
0x14003721f  lea     eax, [r13-4Eh]
0x140037223  cmp     eax, 3
0x140037226  jbe     loc_140036F10
0x14003722c  cmp     r13d, 21h ; '!'
0x140037230  jnz     loc_1400370FF
0x140037236  cmp     cs:byte_140018454, r15b
0x14003723d  jz      loc_1400370FF
0x140037243  mov     ebx, 4
0x140037248  movzx   edx, byte ptr [rdi+6]
0x14003724c  mov     eax, [rdi+18h]
0x14003724f  mov     [rbp+arg_18], dl
0x140037252  mov     [rbp+var_28], eax
0x140037255  cmp     [rdi+40h], r15
0x140037259  jz      loc_140037324
0x14003725f  mov     rcx, rsi; CallbackData
0x140037262  call    cs:__imp_FltLockUserBuffer
0x140037269  nop     dword ptr [rax+rax+00h]
0x14003726e  mov     r14d, eax
0x140037271  test    eax, eax
0x140037273  jns     short loc_14003727D
0x140037275  mov     [rsi+18h], eax
0x140037278  jmp     loc_1400370FF
0x14003727d  mov     rax, [rsi+10h]
0x140037281  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140037285  test    byte ptr [rcx+0Ah], 5
0x140037289  jz      short loc_1400372A8
0x14003728b  mov     r13, [rcx+18h]
0x14003728f  mov     [rbp+var_10], r13
0x140037293  test    r13, r13
0x140037296  jnz     loc_14003733B
0x14003729c  mov     dword ptr [rsi+18h], 0C0000017h
0x1400372a3  jmp     loc_1400370FF
0x1400372a8  mov     [rsp+70h+Priority], 40000010h; Priority
0x1400372b0  xor     r9d, r9d; RequestedAddress
0x1400372b3  xor     edx, edx; AccessMode
0x1400372b5  mov     [rsp+70h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x1400372ba  mov     r8d, 1; CacheType
0x1400372c0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400372c7  nop     dword ptr [rax+rax+00h]
0x1400372cc  mov     r13, rax
0x1400372cf  jmp     short loc_14003728F
0x1400372d1  mov     rax, [rsi+10h]
0x1400372d5  mov     rcx, [rax+40h]; MemoryDescriptorList
0x1400372d9  test    byte ptr [rcx+0Ah], 5
0x1400372dd  jz      short loc_1400372F8
0x1400372df  mov     r9, [rcx+18h]
0x1400372e3  test    r9, r9
0x1400372e6  jnz     loc_1400371BC
0x1400372ec  mov     dword ptr [rsi+18h], 0C0000017h
0x1400372f3  jmp     loc_1400370FF
0x1400372f8  mov     [rsp+70h+Priority], 40000010h; Priority
0x140037300  xor     r9d, r9d; RequestedAddress
0x140037303  xor     edx, edx; AccessMode
0x140037305  mov     [rsp+70h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003730d  mov     r8d, 1; CacheType
0x140037313  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003731a  nop     dword ptr [rax+rax+00h]
0x14003731f  mov     r9, rax
0x140037322  jmp     short loc_1400372E3
0x140037324  mov     rax, [rdi+38h]
0x140037328  mov     [rbp+var_10], rax
0x14003732c  mov     eax, [rsi]
0x14003732e  test    al, 8
0x140037330  jnz     short loc_14003733B
0x140037332  movzx   eax, byte ptr [rsi+50h]
0x140037336  mov     byte ptr [rbp+Context], al
0x140037339  jmp     short loc_14003733F
0x14003733b  mov     byte ptr [rbp+Context], r15b
0x14003733f  mov     ecx, [rdi+18h]
  ... truncated ...
```
