# UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,__int64,UnionFs::StackEventTracer &)

- ea: `0x14006b274`
- end: `0x14006b68c`
- name: `?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@0123_JAEAVStackEventTracer@2@@Z`
- size: `1048`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE InitiatingInstance@<rcx>, const struct _FLT_INSTANCE *@<rdx>, void *@<r8>, const struct _FILE_OBJECT *@<r9>, PFLT_INSTANCE Instance, const struct _FLT_INSTANCE *, void *, const struct _FILE_OBJECT *, const struct _UNICODE_STRING *, __int64, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006c058`

## callees

- `0x140056bd0`
- `0x140056c7c`
- `0x14006b03c`
- `0x14006b274`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14006b2b3`
- `ntoskrnl!IoGetSilo` at `0x14006b420`
- `ntoskrnl!IoGetSilo` at `0x14006b2b3`
- `ntoskrnl!IoGetSilo` at `0x14006b420`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b391`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b3d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b500`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b548`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b623`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b651`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b391`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b3d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b500`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b548`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b623`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b651`
- `FLTMGR!FltCreateFileEx2` at `0x14006b36a`
- `FLTMGR!FltCreateFileEx2` at `0x14006b4d9`
- `FLTMGR!FltCreateFileEx2` at `0x14006b36a`
- `FLTMGR!FltCreateFileEx2` at `0x14006b4d9`
- `FLTMGR!FltSetInformationFile` at `0x14006b597`
- `FLTMGR!FltSetInformationFile` at `0x14006b597`
- `FLTMGR!FltClose` at `0x14006b3ee`
- `FLTMGR!FltClose` at `0x14006b561`
- `FLTMGR!FltClose` at `0x14006b638`
- `FLTMGR!FltClose` at `0x14006b666`
- `FLTMGR!FltClose` at `0x14006b3ee`
- `FLTMGR!FltClose` at `0x14006b561`
- `FLTMGR!FltClose` at `0x14006b638`
- `FLTMGR!FltClose` at `0x14006b666`

## string_xrefs

- `0x14006b3af`: `UnionFs::Utils::CopyDataStream`
- `0x14006b528`: `UnionFs::Utils::CopyDataStream`
- `0x14006b5fb`: `UnionFs::Utils::CopyDataStream`
- `0x14006b3a8`: `API: Opening source stream`
- `0x14006b5ea`: `PUSH: Copying named stream`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyDataStream(
        PFLT_INSTANCE InitiatingInstance,
        const struct _FLT_INSTANCE *a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        PFLT_INSTANCE Instance,
        const struct _FLT_INSTANCE *a6,
        void *a7,
        struct _UNICODE_STRING *a8,
        const struct _UNICODE_STRING *BytesWritten,
        __int64 a10)
{
  int v13; // ebx
  PVOID v14; // rcx
  PVOID v15; // rcx
  PVOID v17; // rcx
  const char *v18; // rax
  __int64 v19; // r8
  PVOID v20; // rcx
  const struct _UNICODE_STRING *v21; // rdi
  int v22; // esi
  PVOID v23; // rcx
  PVOID v24; // rcx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesb; // [rsp+28h] [rbp-D8h]
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v29; // [rsp+88h] [rbp-78h] BYREF
  PVOID *p_Object; // [rsp+90h] [rbp-70h]
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  char v32; // [rsp+A0h] [rbp-60h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A8h] [rbp-58h] BYREF
  __int64 Silo; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES v35; // [rsp+D0h] [rbp-30h] BYREF
  const struct _UNICODE_STRING *FileInformation; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  PVOID Object; // [rsp+158h] [rbp+58h] BYREF
  PVOID v39; // [rsp+168h] [rbp+68h] BYREF

  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  Silo = IoGetSilo(a3);
  v35.ObjectName = a4;
  *(_QWORD *)&v35.Length = 48;
  *(_QWORD *)&v35.Attributes = 576;
  p_Object = &Object;
  v35.RootDirectory = a2;
  *(_OWORD *)&v35.SecurityDescriptor = 0;
  Object = 0;
  IoStatusBlock = 0;
  FileObject = 0;
  v32 = 1;
  FileHandle = 0;
  v13 = FltCreateFileEx2(
          *(PFLT_FILTER *)UnionFs::g_FilterState,
          InitiatingInstance,
          &FileHandle,
          &FileObject,
          0x120089u,
          &v35,
          &IoStatusBlock,
          0,
          0x80u,
          1u,
          1u,
          0x200020u,
          0,
          0,
          0x100u,
          &DriverContext);
  if ( v32 )
  {
    v14 = *p_Object;
    *p_Object = FileObject;
    if ( v14 )
      ObfDereferenceObject(v14);
  }
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a10,
      (struct UnionFs::StackEventTracer *)0x27E00211A09LL,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      "API: Opening source stream",
      ObjectAttributes);
LABEL_6:
    v15 = Object;
    Object = 0;
    if ( v15 )
      ObfDereferenceObject(v15);
    if ( FileHandle )
      FltClose(FileHandle);
    return (unsigned int)v13;
  }
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  Silo = IoGetSilo(a7);
  v35.RootDirectory = a6;
  v35.ObjectName = a8;
  p_Object = &v39;
  v35.Length = 48;
  v35.Attributes = 576;
  *(_OWORD *)&v35.SecurityDescriptor = 0;
  v39 = 0;
  FileObject = 0;
  v32 = 1;
  v29 = 0;
  v13 = FltCreateFileEx2(
          *(PFLT_FILTER *)UnionFs::g_FilterState,
          Instance,
          &v29,
          &FileObject,
          0xC0000000,
          &v35,
          &IoStatusBlock,
          0,
          0x80u,
          1u,
          2u,
          0x200028u,
          0,
          0,
          0x100u,
          &DriverContext);
  if ( v32 )
  {
    v17 = *p_Object;
    *p_Object = FileObject;
    if ( v17 )
      ObfDereferenceObject(v17);
  }
  if ( v13 < 0 )
  {
    v18 = "API: Creating target stream";
    v19 = 0x27F00211A2ALL;
LABEL_16:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a10,
      (struct UnionFs::StackEventTracer *)v19,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      v18,
      ObjectAttributesa);
LABEL_17:
    v20 = v39;
    v39 = 0;
    if ( v20 )
      ObfDereferenceObject(v20);
    if ( v29 )
      FltClose(v29);
    goto LABEL_6;
  }
  v21 = BytesWritten;
  FileInformation = BytesWritten;
  v13 = FltSetInformationFile(Instance, (PFILE_OBJECT)v39, &FileInformation, 8u, FileEndOfFileInformation);
  if ( v13 < 0 )
  {
    v18 = "API: Setting target EOF";
    v19 = 0x28000211A36LL;
    goto LABEL_16;
  }
  v22 = a10;
  v13 = UnionFs::Utils::CopyDataStream(
          InitiatingInstance,
          (PFILE_OBJECT)Object,
          Instance,
          (struct _FILE_OBJECT *)v39,
          (__int64)v21,
          (ULONG)ObjectAttributesa,
          a10);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      v22,
      (struct UnionFs::StackEventTracer *)0x28100211A42LL,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      "PUSH: Copying named stream",
      ObjectAttributesb);
    goto LABEL_17;
  }
  v23 = v39;
  v39 = 0;
  if ( v23 )
    ObfDereferenceObject(v23);
  if ( v29 )
    FltClose(v29);
  v24 = Object;
  Object = 0;
  if ( v24 )
    ObfDereferenceObject(v24);
  if ( FileHandle )
    FltClose(FileHandle);
  return 0;
}

```

## disassembly

```asm
0x14006b274  mov     [rsp-8+arg_0], rbx
0x14006b279  push    rbp
0x14006b27a  push    rsi
0x14006b27b  push    rdi
0x14006b27c  push    r12
0x14006b27e  push    r15
0x14006b280  lea     rbp, [rsp-20h]
0x14006b285  sub     rsp, 120h
0x14006b28c  mov     eax, 28h ; '('
0x14006b291  xorps   xmm0, xmm0
0x14006b294  mov     r15, rcx
0x14006b297  mov     rdi, r9
0x14006b29a  movups  xmmword ptr [rbp+40h+var_98.Size], xmm0
0x14006b29e  mov     rcx, r8
0x14006b2a1  mov     [rbp+40h+var_98.Size], ax
0x14006b2a5  lea     esi, [rax-27h]
0x14006b2a8  mov     rbx, rdx
0x14006b2ab  mov     [rbp+40h+var_78], rsi
0x14006b2af  movups  xmmword ptr [rbp+40h+var_98.DeviceObjectHint], xmm0
0x14006b2b3  call    cs:__imp_IoGetSilo
0x14006b2ba  nop     dword ptr [rax+rax+00h]
0x14006b2bf  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b2c6  lea     r9, [rbp+40h+FileObject]; FileObject
0x14006b2ca  mov     [rbp+40h+var_78], rax
0x14006b2ce  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x14006b2d2  xor     r12d, r12d
0x14006b2d5  mov     [rbp+40h+var_70.ObjectName], rdi
0x14006b2d9  xorps   xmm0, xmm0
0x14006b2dc  mov     qword ptr [rbp+40h+var_70.Length], 30h ; '0'
0x14006b2e4  lea     rax, [rbp+40h+Object]
0x14006b2e8  mov     qword ptr [rbp+40h+var_70.Attributes], 240h
0x14006b2f0  mov     [rbp+40h+var_B0], rax
0x14006b2f4  mov     edi, 100h
0x14006b2f9  lea     rax, [rbp+40h+var_98]
0x14006b2fd  mov     [rbp+40h+var_70.RootDirectory], rbx
0x14006b301  mov     [rsp+140h+DriverContext], rax; DriverContext
0x14006b306  mov     rdx, r15; Instance
0x14006b309  mov     [rsp+140h+Flags], edi; Flags
0x14006b30d  lea     rax, [rbp+40h+var_38]
0x14006b311  mov     [rsp+140h+EaLength], r12d; EaLength
0x14006b316  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14006b31b  mov     [rsp+140h+CreateOptions], 200020h; CreateOptions
0x14006b323  mov     [rsp+140h+CreateDisposition], esi; CreateDisposition
0x14006b327  mov     [rsp+140h+ShareAccess], esi; ShareAccess
0x14006b32b  mov     [rsp+140h+FileAttributes], 80h; FileAttributes
0x14006b333  mov     [rsp+140h+AllocationSize], r12; AllocationSize
0x14006b338  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14006b33d  lea     rax, [rbp+40h+var_70]
0x14006b341  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x14006b346  mov     [rbp+40h+Object], r12
0x14006b34a  movups  xmmword ptr [rbp+40h+var_38], xmm0
0x14006b34e  mov     [rbp+40h+FileObject], r12
0x14006b352  mov     [rbp+40h+var_A0], sil
0x14006b356  mov     [rbp+40h+FileHandle], r12
0x14006b35a  mov     rcx, [rcx]; Filter
0x14006b35d  mov     [rsp+140h+ObjectAttributes], rax; char *
0x14006b362  mov     [rsp+140h+DesiredAccess], 120089h; DesiredAccess
0x14006b36a  call    cs:__imp_FltCreateFileEx2
0x14006b371  nop     dword ptr [rax+rax+00h]
0x14006b376  mov     ebx, eax
0x14006b378  cmp     [rbp+40h+var_A0], r12b
0x14006b37c  jz      short loc_14006B39D
0x14006b37e  mov     r8, [rbp+40h+var_B0]
0x14006b382  mov     rdx, [rbp+40h+FileObject]
0x14006b386  mov     rcx, [r8]; Object
0x14006b389  mov     [r8], rdx
0x14006b38c  test    rcx, rcx
0x14006b38f  jz      short loc_14006B39D
0x14006b391  call    cs:__imp_ObfDereferenceObject
0x14006b398  nop     dword ptr [rax+rax+00h]
0x14006b39d  test    ebx, ebx
0x14006b39f  jns     short loc_14006B401
0x14006b3a1  mov     rdx, qword ptr [rbp+40h+arg_48]; int
0x14006b3a8  lea     rax, aApiOpeningSour; "API: Opening source stream"
0x14006b3af  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b3b6  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b3bb  mov     r8, 27E00211A09h; struct UnionFs::StackEventTracer *
0x14006b3c5  mov     ecx, ebx; this
0x14006b3c7  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b3cc  mov     rcx, [rbp+40h+Object]; Object
0x14006b3d0  mov     [rbp+40h+Object], r12
0x14006b3d4  test    rcx, rcx
0x14006b3d7  jz      short loc_14006B3E5
0x14006b3d9  call    cs:__imp_ObfDereferenceObject
0x14006b3e0  nop     dword ptr [rax+rax+00h]
0x14006b3e5  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14006b3e9  test    rcx, rcx
0x14006b3ec  jz      short loc_14006B3FA
0x14006b3ee  call    cs:__imp_FltClose
0x14006b3f5  nop     dword ptr [rax+rax+00h]
0x14006b3fa  mov     eax, ebx
0x14006b3fc  jmp     loc_14006B674
0x14006b401  mov     rcx, [rbp+40h+arg_30]
0x14006b408  xorps   xmm0, xmm0
0x14006b40b  mov     eax, 28h ; '('
0x14006b410  mov     [rbp+40h+var_78], rsi
0x14006b414  movups  xmmword ptr [rbp+40h+var_98.Size], xmm0
0x14006b418  mov     [rbp+40h+var_98.Size], ax
0x14006b41c  movups  xmmword ptr [rbp+40h+var_98.DeviceObjectHint], xmm0
0x14006b420  call    cs:__imp_IoGetSilo
0x14006b427  nop     dword ptr [rax+rax+00h]
0x14006b42c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b433  lea     r9, [rbp+40h+FileObject]; FileObject
0x14006b437  mov     rdx, [rbp+40h+Instance]; Instance
0x14006b43b  lea     r8, [rbp+40h+var_B8]; FileHandle
0x14006b43f  mov     [rbp+40h+var_78], rax
0x14006b443  xorps   xmm0, xmm0
0x14006b446  mov     rax, [rbp+40h+arg_28]
0x14006b44a  mov     [rbp+40h+var_70.RootDirectory], rax
0x14006b44e  mov     rax, [rbp+40h+arg_38]
0x14006b455  mov     [rbp+40h+var_70.ObjectName], rax
0x14006b459  lea     rax, [rbp+40h+arg_18]
0x14006b45d  mov     [rbp+40h+var_B0], rax
0x14006b461  lea     rax, [rbp+40h+var_98]
0x14006b465  mov     [rsp+140h+DriverContext], rax; DriverContext
0x14006b46a  lea     rax, [rbp+40h+var_38]
0x14006b46e  mov     [rsp+140h+Flags], edi; Flags
0x14006b472  mov     [rsp+140h+EaLength], r12d; EaLength
0x14006b477  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14006b47c  mov     [rsp+140h+CreateOptions], 200028h; CreateOptions
0x14006b484  mov     [rsp+140h+CreateDisposition], 2; CreateDisposition
0x14006b48c  mov     [rsp+140h+ShareAccess], esi; ShareAccess
0x14006b490  mov     [rsp+140h+FileAttributes], 80h; FileAttributes
0x14006b498  mov     [rsp+140h+AllocationSize], r12; struct UnionFs::StackEventTracer *
0x14006b49d  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14006b4a2  lea     rax, [rbp+40h+var_70]
0x14006b4a6  mov     [rbp+40h+var_70.Length], 30h ; '0'
0x14006b4ad  mov     [rbp+40h+var_70.Attributes], 240h
0x14006b4b4  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x14006b4b9  mov     [rbp+40h+arg_18], r12
0x14006b4bd  mov     [rbp+40h+FileObject], r12
0x14006b4c1  mov     [rbp+40h+var_A0], sil
0x14006b4c5  mov     [rbp+40h+var_B8], r12
0x14006b4c9  mov     rcx, [rcx]; Filter
0x14006b4cc  mov     [rsp+140h+ObjectAttributes], rax; char *
0x14006b4d1  mov     [rsp+140h+DesiredAccess], 0C0000000h; DesiredAccess
0x14006b4d9  call    cs:__imp_FltCreateFileEx2
0x14006b4e0  nop     dword ptr [rax+rax+00h]
0x14006b4e5  mov     ebx, eax
0x14006b4e7  cmp     [rbp+40h+var_A0], r12b
0x14006b4eb  jz      short loc_14006B50C
0x14006b4ed  mov     r8, [rbp+40h+var_B0]
0x14006b4f1  mov     rdx, [rbp+40h+FileObject]
0x14006b4f5  mov     rcx, [r8]; Object
0x14006b4f8  mov     [r8], rdx
0x14006b4fb  test    rcx, rcx
0x14006b4fe  jz      short loc_14006B50C
0x14006b500  call    cs:__imp_ObfDereferenceObject
0x14006b507  nop     dword ptr [rax+rax+00h]
0x14006b50c  test    ebx, ebx
0x14006b50e  jns     short loc_14006B572
0x14006b510  lea     rax, aApiCreatingTar; "API: Creating target stream"
0x14006b517  mov     r8, 27F00211A2Ah; struct UnionFs::StackEventTracer *
0x14006b521  mov     rdx, qword ptr [rbp+40h+arg_48]; int
0x14006b528  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b52f  mov     ecx, ebx; this
0x14006b531  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b536  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b53b  mov     rcx, [rbp+40h+arg_18]; Object
0x14006b53f  mov     [rbp+40h+arg_18], r12
0x14006b543  test    rcx, rcx
0x14006b546  jz      short loc_14006B554
0x14006b548  call    cs:__imp_ObfDereferenceObject
0x14006b54f  nop     dword ptr [rax+rax+00h]
0x14006b554  mov     rcx, [rbp+40h+var_B8]; FileHandle
0x14006b558  test    rcx, rcx
0x14006b55b  jz      loc_14006B3CC
0x14006b561  call    cs:__imp_FltClose
0x14006b568  nop     dword ptr [rax+rax+00h]
0x14006b56d  jmp     loc_14006B3CC
0x14006b572  mov     rdi, [rbp+40h+BytesWritten]
0x14006b579  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14006b57d  mov     rdx, [rbp+40h+arg_18]; FileObject
0x14006b581  mov     r9d, 8; Length
0x14006b587  mov     rcx, [rbp+40h+Instance]; Instance
0x14006b58b  mov     [rbp+40h+FileInformation], rdi
0x14006b58f  mov     [rsp+140h+DesiredAccess], 14h; FileInformationClass
0x14006b597  call    cs:__imp_FltSetInformationFile
0x14006b59e  nop     dword ptr [rax+rax+00h]
0x14006b5a3  mov     ebx, eax
0x14006b5a5  test    eax, eax
0x14006b5a7  jns     short loc_14006B5BF
0x14006b5a9  lea     rax, aApiSettingTarg; "API: Setting target EOF"
0x14006b5b0  mov     r8, 28000211A36h
0x14006b5ba  jmp     loc_14006B521
0x14006b5bf  mov     rsi, qword ptr [rbp+40h+arg_48]
0x14006b5c6  mov     rcx, r15; InitiatingInstance
0x14006b5c9  mov     r9, [rbp+40h+arg_18]; struct _FLT_INSTANCE *
0x14006b5cd  mov     r8, [rbp+40h+Instance]; Instance
0x14006b5d1  mov     rdx, [rbp+40h+Object]; FileObject
0x14006b5d5  mov     [rsp+140h+IoStatusBlock], rsi; bool
0x14006b5da  mov     qword ptr [rsp+140h+DesiredAccess], rdi; BytesWritten
0x14006b5df  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)
0x14006b5e4  mov     ebx, eax
0x14006b5e6  test    eax, eax
0x14006b5e8  jns     short loc_14006B616
0x14006b5ea  lea     rax, aPushCopyingNam; "PUSH: Copying named stream"
0x14006b5f1  mov     r8, 28100211A42h; struct UnionFs::StackEventTracer *
0x14006b5fb  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b602  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b607  mov     rdx, rsi; int
0x14006b60a  mov     ecx, ebx; this
0x14006b60c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b611  jmp     loc_14006B53B
0x14006b616  mov     rcx, [rbp+40h+arg_18]; Object
0x14006b61a  mov     [rbp+40h+arg_18], r12
0x14006b61e  test    rcx, rcx
0x14006b621  jz      short loc_14006B62F
0x14006b623  call    cs:__imp_ObfDereferenceObject
0x14006b62a  nop     dword ptr [rax+rax+00h]
0x14006b62f  mov     rcx, [rbp+40h+var_B8]; FileHandle
0x14006b633  test    rcx, rcx
0x14006b636  jz      short loc_14006B644
0x14006b638  call    cs:__imp_FltClose
0x14006b63f  nop     dword ptr [rax+rax+00h]
0x14006b644  mov     rcx, [rbp+40h+Object]; Object
0x14006b648  mov     [rbp+40h+Object], r12
0x14006b64c  test    rcx, rcx
0x14006b64f  jz      short loc_14006B65D
0x14006b651  call    cs:__imp_ObfDereferenceObject
0x14006b658  nop     dword ptr [rax+rax+00h]
0x14006b65d  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14006b661  test    rcx, rcx
0x14006b664  jz      short loc_14006B672
0x14006b666  call    cs:__imp_FltClose
0x14006b66d  nop     dword ptr [rax+rax+00h]
0x14006b672  xor     eax, eax
0x14006b674  mov     rbx, [rsp+140h+arg_0]
0x14006b67c  add     rsp, 120h
0x14006b683  pop     r15
0x14006b685  pop     r12
0x14006b687  pop     rdi
0x14006b688  pop     rsi
0x14006b689  pop     rbp
0x14006b68a  retn
```
