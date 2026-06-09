# VfsCreateShadow

- ea: `0x14000eb14`
- end: `0x14000f04f`
- name: `VfsCreateShadow`
- size: `1339`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, int, struct _FLT_INSTANCE *, struct _FLT_INSTANCE *, PFLT_INSTANCE, PFLT_INSTANCE TargetInstance, __int64, char, char, char, char, char, __int64, __int64, __int64, _BYTE *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1400046bc`
- `0x1400049b4`
- `0x140004d1c`
- `0x14000502c`

## callees

- `0x14000eb14`
- `0x14000f188`
- `0x14000f7ac`
- `0x14000fae0`
- `0x140010654`
- `0x14001070c`
- `0x140011934`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000effa`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f026`
- `ntoskrnl!ObfDereferenceObject` at `0x14001555a`
- `ntoskrnl!ObfDereferenceObject` at `0x140015586`
- `ntoskrnl!ObfDereferenceObject` at `0x14000effa`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f026`
- `ntoskrnl!ObfDereferenceObject` at `0x14001555a`
- `ntoskrnl!ObfDereferenceObject` at `0x140015586`
- `FLTMGR!FltObjectReference` at `0x14000eca1`
- `FLTMGR!FltObjectReference` at `0x14000eca1`
- `FLTMGR!FltObjectDereference` at `0x14000efce`
- `FLTMGR!FltObjectDereference` at `0x14001552e`
- `FLTMGR!FltObjectDereference` at `0x14000efce`
- `FLTMGR!FltObjectDereference` at `0x14001552e`
- `FLTMGR!FltGetInstanceContext` at `0x14000ebd9`
- `FLTMGR!FltGetInstanceContext` at `0x14000ebd9`
- `FLTMGR!FltClose` at `0x14000efe4`
- `FLTMGR!FltClose` at `0x14000f010`
- `FLTMGR!FltClose` at `0x140015544`
- `FLTMGR!FltClose` at `0x140015570`
- `FLTMGR!FltClose` at `0x14000efe4`
- `FLTMGR!FltClose` at `0x14000f010`
- `FLTMGR!FltClose` at `0x140015544`
- `FLTMGR!FltClose` at `0x140015570`
- `FLTMGR!FltReleaseContext` at `0x14000f03c`
- `FLTMGR!FltReleaseContext` at `0x14001559c`
- `FLTMGR!FltReleaseContext` at `0x14000f03c`
- `FLTMGR!FltReleaseContext` at `0x14001559c`

## string_xrefs

- `0x14000ebf7`: `VfsCreateShadow() - Failed to get instance context for instance: %p\n Status: 0x%08X`
- `0x14000ec88`: `VfsCreateShadow() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x14000ecba`: `VfsCreateShadow() - Failed to reference instance: %p\n Status: 0x%08X`
- `0x14000ed31`: `VfsCreateShadow() - Failed to delete tombstone: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateShadow(
        PFLT_CALLBACK_DATA CallbackData,
        int a2,
        struct _FLT_INSTANCE *a3,
        struct _FLT_INSTANCE *a4,
        PFLT_INSTANCE a5,
        PFLT_INSTANCE TargetInstance,
        __int64 a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        _BYTE *a16)
{
  char v19; // r12
  NTSTATUS InstanceContext; // eax
  __int64 v22; // rdx
  int v23; // ebx
  PFLT_INSTANCE v24; // r9
  const wchar_t *v25; // r8
  int v26; // eax
  struct _FLT_INSTANCE *v27; // r15
  int v28; // ecx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PFILE_OBJECT v30; // rdx
  PVOID FsContext2; // rdx
  ULONG v32[2]; // [rsp+58h] [rbp-C8h]
  int FileObject; // [rsp+70h] [rbp-B0h]
  char v34; // [rsp+88h] [rbp-98h]
  HANDLE FileHandle; // [rsp+90h] [rbp-90h] BYREF
  PVOID Object; // [rsp+98h] [rbp-88h] BYREF
  HANDLE v37; // [rsp+A0h] [rbp-80h] BYREF
  PVOID v38; // [rsp+A8h] [rbp-78h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-70h] BYREF
  __int128 v40; // [rsp+B8h] [rbp-68h] BYREF
  __int128 v41; // [rsp+C8h] [rbp-58h]
  __int64 v42; // [rsp+D8h] [rbp-48h]
  PFILE_OBJECT TargetFileObject; // [rsp+E0h] [rbp-40h]
  struct _IO_STATUS_BLOCK v44; // [rsp+E8h] [rbp-38h] BYREF

  FileHandle = 0;
  Object = 0;
  v37 = 0;
  v38 = 0;
  TargetFileObject = CallbackData->Iopb->TargetFileObject;
  Context = 0;
  v44 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v19 = 0;
  v34 = 0;
  *a16 = 0;
  if ( a10 && a8 )
    return 3221225485LL;
  InstanceContext = FltGetInstanceContext(CallbackData->Iopb->TargetInstance, &Context);
  v23 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    v24 = CallbackData->Iopb->TargetInstance;
    v25 = L"VfsCreateShadow() - Failed to get instance context for instance: %p\n Status: 0x%08X";
LABEL_6:
    v32[0] = InstanceContext;
    LogWrite(1, 0, v25, v24, *(_QWORD *)v32);
    goto LABEL_45;
  }
  if ( !a8 && !a10 && a3 && a4 )
  {
    InstanceContext = VfsOpenFile(a3, 1u, 0x4020u, &FileHandle, (PFILE_OBJECT *)&Object);
    v23 = InstanceContext;
    if ( InstanceContext < 0 )
    {
      v24 = a4;
      v25 = L"VfsCreateShadow() - Failed to open file: %wZ\n Status: 0x%08X";
      goto LABEL_6;
    }
    if ( (CallbackData->Iopb->OperationFlags & 4) != 0 )
    {
      InstanceContext = FltObjectReference(a3);
      v23 = InstanceContext;
      if ( InstanceContext < 0 )
      {
        v24 = a3;
        v25 = L"VfsCreateShadow() - Failed to reference instance: %p\n Status: 0x%08X";
        goto LABEL_6;
      }
      v19 = 1;
    }
  }
  if ( !a10 || a2 != 2 )
  {
LABEL_25:
    v23 = VfsCreateFileByCallbackData(
            CallbackData,
            (CallbackData->Iopb->OperationFlags & 4) != 0,
            a12,
            a12 != 0,
            &v44,
            &v37,
            (PFILE_OBJECT *)&v38);
    if ( v23 >= 0 )
    {
      v27 = CallbackData->Iopb->TargetInstance;
      v23 = VfsAdjustDeviceStackSizeForIoRedirection(v27, TargetInstance);
      if ( v23 >= 0 )
      {
        if ( !a5 || a5 == TargetInstance || (v23 = VfsAdjustDeviceStackSizeForIoRedirection(v27, a5), v23 >= 0) )
          v23 = 0;
      }
      if ( v23 >= 0 )
      {
        *((_QWORD *)&v40 + 1) = a13;
        *(_QWORD *)&v41 = a14;
        *((_QWORD *)&v41 + 1) = Context;
        v42 = a15;
        LODWORD(v40) = 0;
        v28 = 0;
        if ( a9 )
        {
          LODWORD(v40) = 4;
          v28 = 4;
        }
        Iopb = CallbackData->Iopb;
        if ( (Iopb->OperationFlags & 4) != 0 || (Iopb->Parameters.Create.Options & 1) != 0 || a11 )
          LODWORD(v40) = v28 | 2;
        LOBYTE(FileObject) = a8;
        v23 = VfsSetupShadowFileObject(CallbackData, &v40, a3, Object, TargetInstance, v38, v37, FileObject, a16);
        if ( v23 >= 0 && !*a16 )
        {
          _InterlockedAdd((volatile signed __int32 *)Context + 6, 1u);
          v30 = TargetFileObject;
          _InterlockedAdd((volatile signed __int32 *)TargetFileObject->FsContext + 70, 1u);
          FsContext2 = v30->FsContext2;
          *((_DWORD *)FsContext2 + 1) |= 2u;
          if ( (CallbackData->Iopb->Parameters.Create.Options & 0x1000) != 0 )
            _InterlockedOr((volatile signed __int32 *)FsContext2 + 1, 0x40u);
          v37 = 0;
          v38 = 0;
          if ( (CallbackData->Iopb->OperationFlags & 4) != 0 && FileHandle )
          {
            *((_DWORD *)FsContext2 + 1) |= 8u;
            *((_QWORD *)FsContext2 + 5) = a3;
            *((_QWORD *)FsContext2 + 7) = FileHandle;
            *((_QWORD *)FsContext2 + 6) = Object;
            v19 = 0;
            FileHandle = 0;
            Object = 0;
          }
        }
      }
    }
    goto LABEL_45;
  }
  if ( a11 )
    v26 = VfsMarkFileDeleted(TargetInstance, 0);
  else
    v26 = VfsDeleteFile(TargetInstance, v22, a7);
  v23 = v26;
  if ( v26 >= 0 )
  {
    v34 = 1;
    goto LABEL_25;
  }
  v32[0] = v26;
  LogWrite(1, 0, L"VfsCreateShadow() - Failed to delete tombstone: %wZ\n Status: 0x%08X", a7, *(_QWORD *)v32);
LABEL_45:
  if ( v23 < 0 && v34 )
    VfsMarkFileDeleted(TargetInstance, 1);
  if ( v19 )
    FltObjectDereference(a3);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v37 )
    FltClose(v37);
  if ( v38 )
    ObfDereferenceObject(v38);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14000eb14  mov     r11, rsp
0x14000eb17  mov     [r11+10h], rbx
0x14000eb1b  mov     [r11+18h], r8
0x14000eb1f  push    rsi
0x14000eb20  push    rdi
0x14000eb21  push    r12
0x14000eb23  push    r14
0x14000eb25  push    r15
0x14000eb27  sub     rsp, 0C0h
0x14000eb2e  mov     r15, r9
0x14000eb31  mov     r14, r8
0x14000eb34  mov     [r11+8], edx
0x14000eb38  mov     rsi, rcx
0x14000eb3b  xor     edi, edi
0x14000eb3d  mov     [rsp+0E8h+var_94], edi
0x14000eb41  mov     [rsp+0E8h+FileHandle], rdi
0x14000eb46  mov     [rsp+0E8h+Object], rdi
0x14000eb4b  mov     [r11-80h], rdi
0x14000eb4f  mov     [r11-78h], rdi
0x14000eb53  mov     rax, [rcx+10h]
0x14000eb57  mov     rax, [rax+8]
0x14000eb5b  mov     [rsp+0E8h+var_40], rax
0x14000eb63  mov     [r11-70h], rdi
0x14000eb67  xorps   xmm0, xmm0
0x14000eb6a  movups  xmmword ptr [r11-38h], xmm0
0x14000eb6f  xorps   xmm1, xmm1
0x14000eb72  xor     eax, eax
0x14000eb74  movups  xmmword ptr [r11-68h], xmm1
0x14000eb79  movups  xmmword ptr [r11-58h], xmm1
0x14000eb7e  mov     [r11-48h], rax
0x14000eb82  mov     r12b, dil
0x14000eb85  mov     [rsp+0E8h+var_97], dil
0x14000eb8a  mov     [rsp+0E8h+var_98], dil
0x14000eb8f  mov     rax, [rsp+0E8h+arg_78]
0x14000eb97  mov     [rax], dil
0x14000eb9a  cmp     [rsp+0E8h+arg_48], dil
0x14000eba2  jz      short loc_14000EBCC
0x14000eba4  cmp     [rsp+0E8h+arg_38], dil
0x14000ebac  jz      short loc_14000EBCC
0x14000ebae  mov     eax, 0C000000Dh
0x14000ebb3  mov     rbx, [rsp+0E8h+arg_8]
0x14000ebbb  add     rsp, 0C0h
0x14000ebc2  pop     r15
0x14000ebc4  pop     r14
0x14000ebc6  pop     r12
0x14000ebc8  pop     rdi
0x14000ebc9  pop     rsi
0x14000ebca  retn
0x14000ebcc  mov     rcx, [rcx+10h]
0x14000ebd0  lea     rdx, [rsp+0E8h+Context]; Context
0x14000ebd5  mov     rcx, [rcx+10h]; Instance
0x14000ebd9  call    cs:__imp_FltGetInstanceContext
0x14000ebe0  nop     dword ptr [rax+rax+00h]
0x14000ebe5  mov     ebx, eax
0x14000ebe7  mov     [rsp+0E8h+var_94], eax
0x14000ebeb  test    eax, eax
0x14000ebed  jns     short loc_14000EC15
0x14000ebef  mov     r9, [rsi+10h]
0x14000ebf3  mov     r9, [r9+10h]
0x14000ebf7  lea     r8, aVfscreateshado_0; "VfsCreateShadow() - Failed to get insta"...
0x14000ebfe  mov     edi, 1
0x14000ec03  mov     [rsp+0E8h+var_C8], eax
0x14000ec07  xor     edx, edx
0x14000ec09  mov     ecx, edi
0x14000ec0b  call    LogWrite
0x14000ec10  jmp     loc_14000EF99
0x14000ec15  cmp     [rsp+0E8h+arg_38], dil
0x14000ec1d  jnz     loc_14000ECD0
0x14000ec23  cmp     [rsp+0E8h+arg_48], dil
0x14000ec2b  jnz     loc_14000ECD0
0x14000ec31  test    r14, r14
0x14000ec34  jz      loc_14000ECD0
0x14000ec3a  test    r15, r15
0x14000ec3d  jz      loc_14000ECD0
0x14000ec43  lea     rax, [rsp+0E8h+Object]
0x14000ec48  mov     [rsp+0E8h+FileObject], rax; FileObject
0x14000ec4d  lea     rax, [rsp+0E8h+FileHandle]
0x14000ec52  mov     [rsp+0E8h+var_B8], rax; FileHandle
0x14000ec57  mov     [rsp+0E8h+var_C0], 4020h; ULONG
0x14000ec5f  mov     edi, 1
0x14000ec64  mov     [rsp+0E8h+var_C8], edi; ULONG
0x14000ec68  mov     r9d, 100000h
0x14000ec6e  mov     r8, r15
0x14000ec71  xor     edx, edx
0x14000ec73  mov     rcx, r14; Instance
0x14000ec76  call    VfsOpenFile
0x14000ec7b  mov     ebx, eax
0x14000ec7d  mov     [rsp+0E8h+var_94], eax
0x14000ec81  test    eax, eax
0x14000ec83  jns     short loc_14000EC94
0x14000ec85  mov     r9, r15
0x14000ec88  lea     r8, aVfscreateshado_2; "VfsCreateShadow() - Failed to open file"...
0x14000ec8f  jmp     loc_14000EC03
0x14000ec94  mov     rax, [rsi+10h]
0x14000ec98  test    byte ptr [rax+6], 4
0x14000ec9c  jz      short loc_14000ECD5
0x14000ec9e  mov     rcx, r14; FltObject
0x14000eca1  call    cs:__imp_FltObjectReference
0x14000eca8  nop     dword ptr [rax+rax+00h]
0x14000ecad  mov     ebx, eax
0x14000ecaf  mov     [rsp+0E8h+var_94], eax
0x14000ecb3  test    eax, eax
0x14000ecb5  jns     short loc_14000ECC6
0x14000ecb7  mov     r9, r14
0x14000ecba  lea     r8, aVfscreateshado; "VfsCreateShadow() - Failed to reference"...
0x14000ecc1  jmp     loc_14000EC03
0x14000ecc6  mov     r12b, dil
0x14000ecc9  mov     [rsp+0E8h+var_97], dil
0x14000ecce  jmp     short loc_14000ECD5
0x14000ecd0  mov     edi, 1
0x14000ecd5  mov     r15d, [rsp+0E8h+arg_0]
0x14000ecdd  cmp     [rsp+0E8h+arg_48], 0
0x14000ece5  jz      short loc_14000ED56
0x14000ece7  cmp     r15d, 2
0x14000eceb  jnz     short loc_14000ED56
0x14000eced  mov     r8, [rsp+0E8h+arg_30]
0x14000ecf5  mov     rcx, [rsp+0E8h+TargetInstance]; Instance
0x14000ecfd  cmp     [rsp+0E8h+arg_50], 0
0x14000ed05  jz      short loc_14000ED16
0x14000ed07  mov     byte ptr [rsp+0E8h+var_C8], 0; char
0x14000ed0c  mov     r9b, dil
0x14000ed0f  call    VfsMarkFileDeleted
0x14000ed14  jmp     short loc_14000ED1B
0x14000ed16  call    VfsDeleteFile
0x14000ed1b  mov     ebx, eax
0x14000ed1d  mov     [rsp+0E8h+var_94], eax
0x14000ed21  test    eax, eax
0x14000ed23  jns     short loc_14000ED3D
0x14000ed25  mov     [rsp+0E8h+var_C8], eax
0x14000ed29  mov     r9, [rsp+0E8h+arg_30]
0x14000ed31  lea     r8, aVfscreateshado_1; "VfsCreateShadow() - Failed to delete to"...
0x14000ed38  jmp     loc_14000EC07
0x14000ed3d  mov     eax, 3
0x14000ed42  cmp     [rsp+0E8h+arg_50], 0
0x14000ed4a  cmovz   eax, r15d
0x14000ed4e  mov     r15d, eax
0x14000ed51  mov     [rsp+0E8h+var_98], dil
0x14000ed56  mov     r8b, [rsp+0E8h+arg_58]
0x14000ed5e  test    r8b, r8b
0x14000ed61  setnz   cl
0x14000ed64  mov     rax, [rsi+10h]
0x14000ed68  mov     dl, [rax+6]
0x14000ed6b  shr     dl, 2
0x14000ed6e  and     dl, dil
0x14000ed71  lea     rax, [rsp+0E8h+var_78]
0x14000ed76  mov     [rsp+0E8h+var_A0], rax; FileObject
0x14000ed7b  lea     rax, [rsp+0E8h+var_80]
0x14000ed80  mov     [rsp+0E8h+var_A8], rax; FileHandle
0x14000ed85  lea     rax, [rsp+0E8h+var_38]
0x14000ed8d  mov     [rsp+0E8h+FileObject], rax; PIO_STATUS_BLOCK
0x14000ed92  mov     byte ptr [rsp+0E8h+var_B8], cl; char
0x14000ed96  mov     byte ptr [rsp+0E8h+var_C0], r8b; char
0x14000ed9b  mov     byte ptr [rsp+0E8h+var_C8], dl; char
0x14000ed9f  mov     r9, [rsp+0E8h+arg_30]
0x14000eda7  mov     r8, [rsp+0E8h+TargetInstance]
0x14000edaf  mov     edx, r15d
0x14000edb2  mov     rcx, rsi; CallbackData
0x14000edb5  call    VfsCreateFileByCallbackData
0x14000edba  mov     ebx, eax
0x14000edbc  mov     [rsp+0E8h+var_94], eax
0x14000edc0  test    eax, eax
0x14000edc2  js      loc_14000EF99
0x14000edc8  mov     rax, [rsi+10h]
0x14000edcc  mov     r15, [rax+10h]
0x14000edd0  mov     rdx, [rsp+0E8h+TargetInstance]; TargetInstance
0x14000edd8  mov     rcx, r15; SourceInstance
0x14000eddb  call    VfsAdjustDeviceStackSizeForIoRedirection
0x14000ede0  mov     ebx, eax
0x14000ede2  test    eax, eax
0x14000ede4  js      short loc_14000EE0D
0x14000ede6  mov     rdx, [rsp+0E8h+arg_20]; TargetInstance
0x14000edee  test    rdx, rdx
0x14000edf1  jz      short loc_14000EE0B
0x14000edf3  cmp     rdx, [rsp+0E8h+TargetInstance]
0x14000edfb  jz      short loc_14000EE0B
0x14000edfd  mov     rcx, r15; SourceInstance
0x14000ee00  call    VfsAdjustDeviceStackSizeForIoRedirection
0x14000ee05  mov     ebx, eax
0x14000ee07  test    eax, eax
0x14000ee09  js      short loc_14000EE0D
0x14000ee0b  xor     ebx, ebx
0x14000ee0d  mov     [rsp+0E8h+var_94], ebx
0x14000ee11  test    ebx, ebx
0x14000ee13  js      loc_14000EF99
0x14000ee19  mov     rax, [rsp+0E8h+arg_60]
0x14000ee21  mov     [rsp+0E8h+var_60], rax
0x14000ee29  mov     rax, [rsp+0E8h+arg_68]
0x14000ee31  mov     [rsp+0E8h+var_58], rax
0x14000ee39  mov     rax, [rsp+0E8h+Context]
0x14000ee3e  mov     [rsp+0E8h+var_50], rax
0x14000ee46  mov     rax, [rsp+0E8h+arg_70]
0x14000ee4e  mov     [rsp+0E8h+var_48], rax
0x14000ee56  mov     [rsp+0E8h+var_68], 0
0x14000ee61  xor     ecx, ecx
0x14000ee63  cmp     [rsp+0E8h+arg_40], cl
0x14000ee6a  jz      short loc_14000EE7C
0x14000ee6c  mov     [rsp+0E8h+var_68], 4
0x14000ee77  mov     ecx, 4
0x14000ee7c  mov     rdx, [rsi+10h]
0x14000ee80  test    byte ptr [rdx+6], 4
0x14000ee84  jnz     short loc_14000EE98
0x14000ee86  mov     eax, [rdx+20h]
0x14000ee89  test    dil, al
0x14000ee8c  jnz     short loc_14000EE98
0x14000ee8e  cmp     [rsp+0E8h+arg_50], 0
0x14000ee96  jz      short loc_14000EEA2
0x14000ee98  or      ecx, 2
0x14000ee9b  mov     [rsp+0E8h+var_68], ecx
0x14000eea2  mov     r15, [rsp+0E8h+arg_78]
0x14000eeaa  mov     [rsp+0E8h+var_A8], r15
0x14000eeaf  mov     al, [rsp+0E8h+arg_38]
0x14000eeb6  mov     byte ptr [rsp+0E8h+FileObject], al
0x14000eeba  mov     rax, [rsp+0E8h+var_80]
0x14000eebf  mov     [rsp+0E8h+var_B8], rax
0x14000eec4  mov     rax, [rsp+0E8h+var_78]
0x14000eec9  mov     qword ptr [rsp+0E8h+var_C0], rax
0x14000eece  mov     rax, [rsp+0E8h+TargetInstance]
0x14000eed6  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14000eedb  mov     r9, [rsp+0E8h+Object]
0x14000eee0  mov     r8, r14
0x14000eee3  lea     rdx, [rsp+0E8h+var_68]
0x14000eeeb  mov     rcx, rsi
0x14000eeee  call    VfsSetupShadowFileObject
0x14000eef3  mov     ebx, eax
0x14000eef5  mov     [rsp+0E8h+var_94], eax
0x14000eef9  test    eax, eax
0x14000eefb  js      loc_14000EF99
0x14000ef01  cmp     byte ptr [r15], 0
0x14000ef05  jnz     loc_14000EF99
0x14000ef0b  mov     rax, [rsp+0E8h+Context]
0x14000ef10  lock add [rax+18h], edi
0x14000ef14  mov     rdx, [rsp+0E8h+var_40]
0x14000ef1c  mov     rax, [rdx+18h]
0x14000ef20  lock add [rax+118h], edi
0x14000ef27  mov     rdx, [rdx+20h]
0x14000ef2b  or      dword ptr [rdx+4], 2
0x14000ef2f  mov     rax, [rsi+10h]
0x14000ef33  test    dword ptr [rax+20h], 1000h
0x14000ef3a  jz      short loc_14000EF41
0x14000ef3c  lock or dword ptr [rdx+4], 40h
0x14000ef41  mov     [rsp+0E8h+var_80], 0
0x14000ef4a  mov     [rsp+0E8h+var_78], 0
0x14000ef53  mov     rax, [rsi+10h]
0x14000ef57  test    byte ptr [rax+6], 4
0x14000ef5b  jz      short loc_14000EF99
0x14000ef5d  cmp     [rsp+0E8h+FileHandle], 0
0x14000ef63  jz      short loc_14000EF99
0x14000ef65  or      dword ptr [rdx+4], 8
0x14000ef69  mov     [rdx+28h], r14
0x14000ef6d  mov     rax, [rsp+0E8h+FileHandle]
0x14000ef72  mov     [rdx+38h], rax
0x14000ef76  mov     rax, [rsp+0E8h+Object]
0x14000ef7b  mov     [rdx+30h], rax
0x14000ef7f  xor     r12b, r12b
0x14000ef82  mov     [rsp+0E8h+var_97], r12b
0x14000ef87  mov     [rsp+0E8h+FileHandle], 0
0x14000ef90  mov     [rsp+0E8h+Object], 0
0x14000ef99  test    ebx, ebx
0x14000ef9b  jns     short loc_14000EFC6
0x14000ef9d  cmp     [rsp+0E8h+var_98], 0
0x14000efa2  jz      short loc_14000EFC6
0x14000efa4  mov     byte ptr [rsp+0E8h+var_C8], dil; char
0x14000efa9  mov     r9b, [rsp+0E8h+arg_50]
0x14000efb1  mov     r8, [rsp+0E8h+arg_30]
0x14000efb9  mov     rcx, [rsp+0E8h+TargetInstance]; Instance
0x14000efc1  call    VfsMarkFileDeleted
0x14000efc6  test    r12b, r12b
0x14000efc9  jz      short loc_14000EFDA
0x14000efcb  mov     rcx, r14; FltObject
0x14000efce  call    cs:__imp_FltObjectDereference
0x14000efd5  nop     dword ptr [rax+rax+00h]
0x14000efda  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x14000efdf  test    rcx, rcx
0x14000efe2  jz      short loc_14000EFF0
0x14000efe4  call    cs:__imp_FltClose
0x14000efeb  nop     dword ptr [rax+rax+00h]
0x14000eff0  mov     rcx, [rsp+0E8h+Object]; Object
0x14000eff5  test    rcx, rcx
0x14000eff8  jz      short loc_14000F006
0x14000effa  call    cs:__imp_ObfDereferenceObject
0x14000f001  nop     dword ptr [rax+rax+00h]
0x14000f006  mov     rcx, [rsp+0E8h+var_80]; FileHandle
0x14000f00b  test    rcx, rcx
0x14000f00e  jz      short loc_14000F01C
0x14000f010  call    cs:__imp_FltClose
0x14000f017  nop     dword ptr [rax+rax+00h]
0x14000f01c  mov     rcx, [rsp+0E8h+var_78]; Object
0x14000f021  test    rcx, rcx
0x14000f024  jz      short loc_14000F032
0x14000f026  call    cs:__imp_ObfDereferenceObject
0x14000f02d  nop     dword ptr [rax+rax+00h]
0x14000f032  mov     rcx, [rsp+0E8h+Context]; Context
0x14000f037  test    rcx, rcx
0x14000f03a  jz      short loc_14000F048
0x14000f03c  call    cs:__imp_FltReleaseContext
0x14000f043  nop     dword ptr [rax+rax+00h]
0x14000f048  mov     eax, ebx
0x14000f04a  jmp     loc_14000EBB3
0x1400154ec  push    rbp
0x1400154ee  sub     rsp, 50h
  ... truncated ...
```
