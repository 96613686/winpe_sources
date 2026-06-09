# VfsCreateFileByCallbackData

- ea: `0x14000fae0`
- end: `0x14000fd2f`
- name: `VfsCreateFileByCallbackData`
- size: `591`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, char, char, char, PIO_STATUS_BLOCK, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000eb14`

## callees

- `0x14000fae0`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000fc0f`
- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000fc0f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000fc4d`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000fc4d`
- `FLTMGR!FltCreateFileEx2` at `0x14000fcce`
- `FLTMGR!FltCreateFileEx2` at `0x14000fcce`

## string_xrefs

- `0x14000fce5`: `VfsCreateFileByCallbackData() - Failed to create file by callback data: %wZ\n Access:0x%08X\n ShareAccess:0x%08X\n Attributes:0x%08X\n CreateDisposition:0x%08X\n CreateOptions:0x%08X\n CreateFlags:0x%08X\n Status: 0x%08X`

## pseudocode

```c
NTSTATUS __fastcall VfsCreateFileByCallbackData(
        PFLT_CALLBACK_DATA CallbackData,
        ULONG a2,
        struct _FLT_INSTANCE *a3,
        struct _UNICODE_STRING *a4,
        char a5,
        char a6,
        char a7,
        PIO_STATUS_BLOCK a8,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject)
{
  KPROCESSOR_MODE RequestorMode; // r8
  int v14; // edx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r9
  ULONG v16; // ecx
  char OperationFlags; // al
  ULONG v18; // r12d
  ULONG CreateOptions; // esi
  ULONG v20; // r15d
  ACCESS_MASK v21; // edi
  int v22; // edx
  ULONG Flags; // ebx
  NTSTATUS result; // eax
  NTSTATUS v25; // eax
  NTSTATUS v26; // r14d
  ACCESS_MASK DesiredAccess[2]; // [rsp+28h] [rbp-C1h]
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-B9h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-B1h]
  PLARGE_INTEGER AllocationSize; // [rsp+40h] [rbp-A9h]
  __int64 FileAttributes; // [rsp+48h] [rbp-A1h]
  __int64 ShareAccess; // [rsp+50h] [rbp-99h]
  __int64 CreateDisposition; // [rsp+58h] [rbp-91h]
  struct _IO_DRIVER_CREATE_CONTEXT EcpList; // [rsp+88h] [rbp-61h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-41h]
  struct _OBJECT_ATTRIBUTES v36; // [rsp+B0h] [rbp-39h] BYREF
  PVOID EaBuffer; // [rsp+138h] [rbp+4Fh]
  ULONG EaLength; // [rsp+170h] [rbp+87h]

  *(_OWORD *)&v36.ObjectName = 0;
  LOWORD(v35) = 0;
  a8->Status = 0;
  a8->Information = 0;
  RequestorMode = CallbackData->RequestorMode;
  *(_OWORD *)&v36.Length = 0;
  *(_OWORD *)(&v36.Attributes + 1) = 0;
  memset(&EcpList, 0, sizeof(EcpList));
  if ( RequestorMode == 1 || (v14 = 512, !RequestorMode) && (CallbackData->Iopb->OperationFlags & 1) != 0 )
    v14 = 1536;
  Iopb = CallbackData->Iopb;
  v16 = v14 | 0x40;
  OperationFlags = Iopb->OperationFlags;
  v36.Length = 48;
  v36.RootDirectory = 0;
  v36.ObjectName = a4;
  if ( OperationFlags < 0 )
    v16 = v14;
  v36.Attributes = v16;
  v36.SecurityDescriptor = *(PVOID *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 64LL);
  v36.SecurityQualityOfService = 0;
  v18 = Iopb->Parameters.Create.FileAttributes;
  CreateOptions = Iopb->Parameters.Create.Options & 0xFFFFFF;
  v20 = Iopb->Parameters.Create.ShareAccess;
  v21 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  EaLength = Iopb->Parameters.Create.EaLength;
  if ( a6 )
  {
    v21 = v21 & 0xFFF2FE28 | 0x81;
    CreateOptions = Iopb->Parameters.Create.Options & 0xFFEFFF;
  }
  if ( a5 )
    CreateOptions = 16417;
  v22 = Iopb->OperationFlags & 0xFB;
  if ( !a5 )
    v22 = Iopb->OperationFlags;
  Flags = v22 | 1;
  if ( RequestorMode != 1 )
    Flags = v22;
  if ( a7 || !RequestorMode && IoIsFileObjectIgnoringSharing(Iopb->TargetFileObject) )
    Flags |= 0x800u;
  v35 = 1;
  memset(&EcpList, 0, sizeof(EcpList));
  EcpList.Size = 40;
  result = FltGetEcpListFromCallbackData(VfsData, CallbackData, &EcpList.ExtraCreateParameter);
  if ( result >= 0 )
  {
    v25 = FltCreateFileEx2(
            VfsData,
            a3,
            FileHandle,
            FileObject,
            v21,
            &v36,
            a8,
            &CallbackData->Iopb->Parameters.Create.AllocationSize,
            v18,
            v20,
            a2,
            CreateOptions,
            EaBuffer,
            EaLength,
            Flags,
            &EcpList);
    v26 = v25;
    if ( v25 < 0 )
    {
      LODWORD(CreateDisposition) = v25;
      LODWORD(ShareAccess) = Flags;
      LODWORD(FileAttributes) = CreateOptions;
      LODWORD(AllocationSize) = a2;
      LODWORD(IoStatusBlock) = v18;
      LODWORD(ObjectAttributes) = v20;
      DesiredAccess[0] = v21;
      LogWrite(
        1,
        0,
        L"VfsCreateFileByCallbackData() - Failed to create file by callback data: %wZ\n"
         " Access:0x%08X\n"
         " ShareAccess:0x%08X\n"
         " Attributes:0x%08X\n"
         " CreateDisposition:0x%08X\n"
         " CreateOptions:0x%08X\n"
         " CreateFlags:0x%08X\n"
         " Status: 0x%08X",
        a4,
        *(_QWORD *)DesiredAccess,
        ObjectAttributes,
        IoStatusBlock,
        AllocationSize,
        FileAttributes,
        ShareAccess,
        CreateDisposition);
    }
    return v26;
  }
  return result;
}

```

## disassembly

```asm
0x14000fae0  mov     rax, rsp
0x14000fae3  mov     [rax+20h], r9
0x14000fae7  mov     [rax+18h], r8
0x14000faeb  mov     [rax+10h], edx
0x14000faee  push    rbp
0x14000faef  push    rbx
0x14000faf0  push    rsi
0x14000faf1  push    rdi
0x14000faf2  push    r12
0x14000faf4  push    r13
0x14000faf6  push    r14
0x14000faf8  push    r15
0x14000fafa  lea     rbp, [rax-47h]
0x14000fafe  sub     rsp, 0E8h
0x14000fb05  mov     r13, [rbp+3Fh+arg_38]
0x14000fb0c  xorps   xmm0, xmm0
0x14000fb0f  xor     r11d, r11d
0x14000fb12  xor     eax, eax
0x14000fb14  movups  xmmword ptr [rbp+3Fh+var_78.ObjectName], xmm0
0x14000fb18  mov     r10, r9
0x14000fb1b  mov     word ptr [rbp+3Fh+var_80], ax
0x14000fb1f  mov     [r13+0], r11d
0x14000fb23  mov     r14, rcx
0x14000fb26  mov     [r13+8], r11
0x14000fb2a  mov     r8b, [rcx+50h]
0x14000fb2e  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x14000fb32  movups  xmmword ptr [rbp+3Fh+var_78+1Ch], xmm0
0x14000fb36  movups  xmmword ptr [rbp+3Fh+EcpList], xmm0
0x14000fb3a  movups  [rbp+3Fh+var_90], xmm0
0x14000fb3e  cmp     r8b, 1
0x14000fb42  jz      short loc_14000FB58
0x14000fb44  mov     edx, 200h
0x14000fb49  test    r8b, r8b
0x14000fb4c  jnz     short loc_14000FB5D
0x14000fb4e  mov     rax, [rcx+10h]
0x14000fb52  test    byte ptr [rax+6], 1
0x14000fb56  jz      short loc_14000FB5D
0x14000fb58  mov     edx, 600h
0x14000fb5d  mov     r9, [rcx+10h]
0x14000fb61  mov     ecx, edx
0x14000fb63  or      ecx, 40h
0x14000fb66  mov     al, [r9+6]
0x14000fb6a  mov     [rbp+3Fh+var_78.Length], 30h ; '0'
0x14000fb71  test    al, al
0x14000fb73  mov     [rbp+3Fh+var_78.RootDirectory], r11
0x14000fb77  mov     [rbp+3Fh+var_78.ObjectName], r10
0x14000fb7b  cmovs   ecx, edx
0x14000fb7e  mov     [rbp+3Fh+var_78.Attributes], ecx
0x14000fb81  mov     rax, [r9+18h]
0x14000fb85  mov     rcx, [rax+8]
0x14000fb89  mov     rax, [rcx+40h]
0x14000fb8d  mov     [rbp+3Fh+var_78.SecurityDescriptor], rax
0x14000fb91  mov     [rbp+3Fh+var_78.SecurityQualityOfService], r11
0x14000fb95  mov     rax, [r9+18h]
0x14000fb99  mov     esi, [r9+20h]
0x14000fb9d  movzx   r12d, word ptr [r9+28h]
0x14000fba2  and     esi, 0FFFFFFh
0x14000fba8  movzx   r15d, word ptr [r9+2Ah]
0x14000fbad  mov     edi, [rax+10h]
0x14000fbb0  mov     rax, [r9+38h]
0x14000fbb4  mov     [rbp+3Fh+arg_0], rax
0x14000fbb8  mov     eax, [r9+30h]
0x14000fbbc  mov     dword ptr [rbp+3Fh+arg_38], eax
0x14000fbc2  cmp     [rbp+3Fh+arg_28], r11b
0x14000fbc6  jz      short loc_14000FBD8
0x14000fbc8  and     edi, 0FFF2FEA9h
0x14000fbce  or      edi, 81h
0x14000fbd4  btr     esi, 0Ch
0x14000fbd8  mov     al, [rbp+3Fh+arg_20]
0x14000fbdb  mov     edx, 4021h
0x14000fbe0  movzx   ecx, byte ptr [r9+6]
0x14000fbe5  test    al, al
0x14000fbe7  cmovnz  esi, edx
0x14000fbea  mov     edx, ecx
0x14000fbec  and     edx, 0FFFFFFFBh
0x14000fbef  test    al, al
0x14000fbf1  cmovz   edx, ecx
0x14000fbf4  mov     ebx, edx
0x14000fbf6  or      ebx, 1
0x14000fbf9  cmp     r8b, 1
0x14000fbfd  cmovnz  ebx, edx
0x14000fc00  cmp     [rbp+3Fh+arg_30], r11b
0x14000fc04  jnz     short loc_14000FC1F
0x14000fc06  test    r8b, r8b
0x14000fc09  jnz     short loc_14000FC23
0x14000fc0b  mov     rcx, [r9+8]; FileObject
0x14000fc0f  call    cs:__imp_IoIsFileObjectIgnoringSharing
0x14000fc16  nop     dword ptr [rax+rax+00h]
0x14000fc1b  test    al, al
0x14000fc1d  jz      short loc_14000FC23
0x14000fc1f  bts     ebx, 0Bh
0x14000fc23  mov     rcx, cs:VfsData; Filter
0x14000fc2a  lea     r8, [rbp+3Fh+EcpList+8]; EcpList
0x14000fc2e  xorps   xmm0, xmm0
0x14000fc31  mov     [rbp+3Fh+var_80], 1
0x14000fc39  mov     eax, 28h ; '('
0x14000fc3e  mov     rdx, r14; CallbackData
0x14000fc41  movups  xmmword ptr [rbp+3Fh+EcpList], xmm0
0x14000fc45  mov     word ptr [rbp+3Fh+EcpList], ax
0x14000fc49  movups  [rbp+3Fh+var_90], xmm0
0x14000fc4d  call    cs:__imp_FltGetEcpListFromCallbackData
0x14000fc54  nop     dword ptr [rax+rax+00h]
0x14000fc59  test    eax, eax
0x14000fc5b  js      loc_14000FD1A
0x14000fc61  mov     rax, [r14+10h]
0x14000fc65  lea     rcx, [rbp+3Fh+EcpList]
0x14000fc69  mov     r9, [rbp+3Fh+FileObject]; FileObject
0x14000fc70  add     rax, 40h ; '@'
0x14000fc74  mov     r8, [rbp+3Fh+FileHandle]; FileHandle
0x14000fc7b  mov     rdx, [rbp+3Fh+Instance]; Instance
0x14000fc7f  mov     [rsp+78h], rcx; DriverContext
0x14000fc84  mov     ecx, dword ptr [rbp+3Fh+arg_38]
0x14000fc8a  mov     [rsp+120h+Flags], ebx; Flags
0x14000fc8e  mov     [rsp+120h+EaLength], ecx; EaLength
0x14000fc92  mov     rcx, [rbp+3Fh+arg_0]
0x14000fc96  mov     [rsp+120h+EaBuffer], rcx; EaBuffer
0x14000fc9b  mov     ecx, [rbp+3Fh+arg_8]
0x14000fc9e  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x14000fca2  mov     dword ptr [rsp+120h+CreateDisposition], ecx; CreateDisposition
0x14000fca6  mov     rcx, cs:VfsData; Filter
0x14000fcad  mov     dword ptr [rsp+120h+ShareAccess], r15d; ShareAccess
0x14000fcb2  mov     dword ptr [rsp+120h+FileAttributes], r12d; FileAttributes
0x14000fcb7  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x14000fcbc  lea     rax, [rbp+3Fh+var_78]
0x14000fcc0  mov     [rsp+120h+IoStatusBlock], r13; IoStatusBlock
0x14000fcc5  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000fcca  mov     [rsp+120h+DesiredAccess], edi; DesiredAccess
0x14000fcce  call    cs:__imp_FltCreateFileEx2
0x14000fcd5  nop     dword ptr [rax+rax+00h]
0x14000fcda  mov     r14d, eax
0x14000fcdd  test    eax, eax
0x14000fcdf  jns     short loc_14000FD17
0x14000fce1  mov     r9, [rbp+3Fh+arg_18]
0x14000fce5  lea     r8, aVfscreatefileb; "VfsCreateFileByCallbackData() - Failed "...
0x14000fcec  mov     dword ptr [rsp+120h+CreateDisposition], eax
0x14000fcf0  xor     edx, edx
0x14000fcf2  mov     eax, [rbp+3Fh+arg_8]
0x14000fcf5  mov     dword ptr [rsp+120h+ShareAccess], ebx
0x14000fcf9  mov     dword ptr [rsp+120h+FileAttributes], esi
0x14000fcfd  mov     dword ptr [rsp+120h+AllocationSize], eax
0x14000fd01  lea     ecx, [rdx+1]
0x14000fd04  mov     dword ptr [rsp+120h+IoStatusBlock], r12d
0x14000fd09  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x14000fd0e  mov     [rsp+120h+DesiredAccess], edi
0x14000fd12  call    LogWrite
0x14000fd17  mov     eax, r14d
0x14000fd1a  add     rsp, 0E8h
0x14000fd21  pop     r15
0x14000fd23  pop     r14
0x14000fd25  pop     r13
0x14000fd27  pop     r12
0x14000fd29  pop     rdi
0x14000fd2a  pop     rsi
0x14000fd2b  pop     rbx
0x14000fd2c  pop     rbp
0x14000fd2d  retn
```
