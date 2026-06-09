# UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,__int64,UnionFs::StackEventTracer &)

- ea: `0x14006b084`
- end: `0x14006b49c`
- name: `?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@0123_JAEAVStackEventTracer@2@@Z`
- size: `1048`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE InitiatingInstance@<rcx>, const struct _FLT_INSTANCE *@<rdx>, void *@<r8>, const struct _FILE_OBJECT *@<r9>, PFLT_INSTANCE Instance, const struct _FLT_INSTANCE *, void *, const struct _FILE_OBJECT *, const struct _UNICODE_STRING *, __int64, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006be68`

## callees

- `0x140056a50`
- `0x140056afc`
- `0x14006ae4c`
- `0x14006b084`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14006b0c3`
- `ntoskrnl!IoGetSilo` at `0x14006b230`
- `ntoskrnl!IoGetSilo` at `0x14006b0c3`
- `ntoskrnl!IoGetSilo` at `0x14006b230`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b1a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b1e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b310`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b358`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b433`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b461`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b1a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b1e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b310`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b358`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b433`
- `ntoskrnl!ObfDereferenceObject` at `0x14006b461`
- `FLTMGR!FltCreateFileEx2` at `0x14006b17a`
- `FLTMGR!FltCreateFileEx2` at `0x14006b2e9`
- `FLTMGR!FltCreateFileEx2` at `0x14006b17a`
- `FLTMGR!FltCreateFileEx2` at `0x14006b2e9`
- `FLTMGR!FltSetInformationFile` at `0x14006b3a7`
- `FLTMGR!FltSetInformationFile` at `0x14006b3a7`
- `FLTMGR!FltClose` at `0x14006b1fe`
- `FLTMGR!FltClose` at `0x14006b371`
- `FLTMGR!FltClose` at `0x14006b448`
- `FLTMGR!FltClose` at `0x14006b476`
- `FLTMGR!FltClose` at `0x14006b1fe`
- `FLTMGR!FltClose` at `0x14006b371`
- `FLTMGR!FltClose` at `0x14006b448`
- `FLTMGR!FltClose` at `0x14006b476`

## string_xrefs

- `0x14006b1bf`: `UnionFs::Utils::CopyDataStream`
- `0x14006b338`: `UnionFs::Utils::CopyDataStream`
- `0x14006b40b`: `UnionFs::Utils::CopyDataStream`
- `0x14006b1b8`: `API: Opening source stream`
- `0x14006b3fa`: `PUSH: Copying named stream`

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
      (struct UnionFs::StackEventTracer *)0x27E002119D3LL,
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
    v19 = 0x27F002119F4LL;
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
    v19 = 0x28000211A00LL;
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
      (struct UnionFs::StackEventTracer *)0x28100211A0CLL,
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
0x14006b084  mov     [rsp-8+arg_0], rbx
0x14006b089  push    rbp
0x14006b08a  push    rsi
0x14006b08b  push    rdi
0x14006b08c  push    r12
0x14006b08e  push    r15
0x14006b090  lea     rbp, [rsp-20h]
0x14006b095  sub     rsp, 120h
0x14006b09c  mov     eax, 28h ; '('
0x14006b0a1  xorps   xmm0, xmm0
0x14006b0a4  mov     r15, rcx
0x14006b0a7  mov     rdi, r9
0x14006b0aa  movups  xmmword ptr [rbp+40h+var_98.Size], xmm0
0x14006b0ae  mov     rcx, r8
0x14006b0b1  mov     [rbp+40h+var_98.Size], ax
0x14006b0b5  lea     esi, [rax-27h]
0x14006b0b8  mov     rbx, rdx
0x14006b0bb  mov     [rbp+40h+var_78], rsi
0x14006b0bf  movups  xmmword ptr [rbp+40h+var_98.DeviceObjectHint], xmm0
0x14006b0c3  call    cs:__imp_IoGetSilo
0x14006b0ca  nop     dword ptr [rax+rax+00h]
0x14006b0cf  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b0d6  lea     r9, [rbp+40h+FileObject]; FileObject
0x14006b0da  mov     [rbp+40h+var_78], rax
0x14006b0de  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x14006b0e2  xor     r12d, r12d
0x14006b0e5  mov     [rbp+40h+var_70.ObjectName], rdi
0x14006b0e9  xorps   xmm0, xmm0
0x14006b0ec  mov     qword ptr [rbp+40h+var_70.Length], 30h ; '0'
0x14006b0f4  lea     rax, [rbp+40h+Object]
0x14006b0f8  mov     qword ptr [rbp+40h+var_70.Attributes], 240h
0x14006b100  mov     [rbp+40h+var_B0], rax
0x14006b104  mov     edi, 100h
0x14006b109  lea     rax, [rbp+40h+var_98]
0x14006b10d  mov     [rbp+40h+var_70.RootDirectory], rbx
0x14006b111  mov     [rsp+140h+DriverContext], rax; DriverContext
0x14006b116  mov     rdx, r15; Instance
0x14006b119  mov     [rsp+140h+Flags], edi; Flags
0x14006b11d  lea     rax, [rbp+40h+var_38]
0x14006b121  mov     [rsp+140h+EaLength], r12d; EaLength
0x14006b126  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14006b12b  mov     [rsp+140h+CreateOptions], 200020h; CreateOptions
0x14006b133  mov     [rsp+140h+CreateDisposition], esi; CreateDisposition
0x14006b137  mov     [rsp+140h+ShareAccess], esi; ShareAccess
0x14006b13b  mov     [rsp+140h+FileAttributes], 80h; FileAttributes
0x14006b143  mov     [rsp+140h+AllocationSize], r12; AllocationSize
0x14006b148  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14006b14d  lea     rax, [rbp+40h+var_70]
0x14006b151  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x14006b156  mov     [rbp+40h+Object], r12
0x14006b15a  movups  xmmword ptr [rbp+40h+var_38], xmm0
0x14006b15e  mov     [rbp+40h+FileObject], r12
0x14006b162  mov     [rbp+40h+var_A0], sil
0x14006b166  mov     [rbp+40h+FileHandle], r12
0x14006b16a  mov     rcx, [rcx]; Filter
0x14006b16d  mov     [rsp+140h+ObjectAttributes], rax; char *
0x14006b172  mov     [rsp+140h+DesiredAccess], 120089h; DesiredAccess
0x14006b17a  call    cs:__imp_FltCreateFileEx2
0x14006b181  nop     dword ptr [rax+rax+00h]
0x14006b186  mov     ebx, eax
0x14006b188  cmp     [rbp+40h+var_A0], r12b
0x14006b18c  jz      short loc_14006B1AD
0x14006b18e  mov     r8, [rbp+40h+var_B0]
0x14006b192  mov     rdx, [rbp+40h+FileObject]
0x14006b196  mov     rcx, [r8]; Object
0x14006b199  mov     [r8], rdx
0x14006b19c  test    rcx, rcx
0x14006b19f  jz      short loc_14006B1AD
0x14006b1a1  call    cs:__imp_ObfDereferenceObject
0x14006b1a8  nop     dword ptr [rax+rax+00h]
0x14006b1ad  test    ebx, ebx
0x14006b1af  jns     short loc_14006B211
0x14006b1b1  mov     rdx, qword ptr [rbp+40h+arg_48]; int
0x14006b1b8  lea     rax, aApiOpeningSour; "API: Opening source stream"
0x14006b1bf  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b1c6  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b1cb  mov     r8, 27E002119D3h; struct UnionFs::StackEventTracer *
0x14006b1d5  mov     ecx, ebx; this
0x14006b1d7  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b1dc  mov     rcx, [rbp+40h+Object]; Object
0x14006b1e0  mov     [rbp+40h+Object], r12
0x14006b1e4  test    rcx, rcx
0x14006b1e7  jz      short loc_14006B1F5
0x14006b1e9  call    cs:__imp_ObfDereferenceObject
0x14006b1f0  nop     dword ptr [rax+rax+00h]
0x14006b1f5  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14006b1f9  test    rcx, rcx
0x14006b1fc  jz      short loc_14006B20A
0x14006b1fe  call    cs:__imp_FltClose
0x14006b205  nop     dword ptr [rax+rax+00h]
0x14006b20a  mov     eax, ebx
0x14006b20c  jmp     loc_14006B484
0x14006b211  mov     rcx, [rbp+40h+arg_30]
0x14006b218  xorps   xmm0, xmm0
0x14006b21b  mov     eax, 28h ; '('
0x14006b220  mov     [rbp+40h+var_78], rsi
0x14006b224  movups  xmmword ptr [rbp+40h+var_98.Size], xmm0
0x14006b228  mov     [rbp+40h+var_98.Size], ax
0x14006b22c  movups  xmmword ptr [rbp+40h+var_98.DeviceObjectHint], xmm0
0x14006b230  call    cs:__imp_IoGetSilo
0x14006b237  nop     dword ptr [rax+rax+00h]
0x14006b23c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b243  lea     r9, [rbp+40h+FileObject]; FileObject
0x14006b247  mov     rdx, [rbp+40h+Instance]; Instance
0x14006b24b  lea     r8, [rbp+40h+var_B8]; FileHandle
0x14006b24f  mov     [rbp+40h+var_78], rax
0x14006b253  xorps   xmm0, xmm0
0x14006b256  mov     rax, [rbp+40h+arg_28]
0x14006b25a  mov     [rbp+40h+var_70.RootDirectory], rax
0x14006b25e  mov     rax, [rbp+40h+arg_38]
0x14006b265  mov     [rbp+40h+var_70.ObjectName], rax
0x14006b269  lea     rax, [rbp+40h+arg_18]
0x14006b26d  mov     [rbp+40h+var_B0], rax
0x14006b271  lea     rax, [rbp+40h+var_98]
0x14006b275  mov     [rsp+140h+DriverContext], rax; DriverContext
0x14006b27a  lea     rax, [rbp+40h+var_38]
0x14006b27e  mov     [rsp+140h+Flags], edi; Flags
0x14006b282  mov     [rsp+140h+EaLength], r12d; EaLength
0x14006b287  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14006b28c  mov     [rsp+140h+CreateOptions], 200028h; CreateOptions
0x14006b294  mov     [rsp+140h+CreateDisposition], 2; CreateDisposition
0x14006b29c  mov     [rsp+140h+ShareAccess], esi; ShareAccess
0x14006b2a0  mov     [rsp+140h+FileAttributes], 80h; FileAttributes
0x14006b2a8  mov     [rsp+140h+AllocationSize], r12; struct UnionFs::StackEventTracer *
0x14006b2ad  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14006b2b2  lea     rax, [rbp+40h+var_70]
0x14006b2b6  mov     [rbp+40h+var_70.Length], 30h ; '0'
0x14006b2bd  mov     [rbp+40h+var_70.Attributes], 240h
0x14006b2c4  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x14006b2c9  mov     [rbp+40h+arg_18], r12
0x14006b2cd  mov     [rbp+40h+FileObject], r12
0x14006b2d1  mov     [rbp+40h+var_A0], sil
0x14006b2d5  mov     [rbp+40h+var_B8], r12
0x14006b2d9  mov     rcx, [rcx]; Filter
0x14006b2dc  mov     [rsp+140h+ObjectAttributes], rax; char *
0x14006b2e1  mov     [rsp+140h+DesiredAccess], 0C0000000h; DesiredAccess
0x14006b2e9  call    cs:__imp_FltCreateFileEx2
0x14006b2f0  nop     dword ptr [rax+rax+00h]
0x14006b2f5  mov     ebx, eax
0x14006b2f7  cmp     [rbp+40h+var_A0], r12b
0x14006b2fb  jz      short loc_14006B31C
0x14006b2fd  mov     r8, [rbp+40h+var_B0]
0x14006b301  mov     rdx, [rbp+40h+FileObject]
0x14006b305  mov     rcx, [r8]; Object
0x14006b308  mov     [r8], rdx
0x14006b30b  test    rcx, rcx
0x14006b30e  jz      short loc_14006B31C
0x14006b310  call    cs:__imp_ObfDereferenceObject
0x14006b317  nop     dword ptr [rax+rax+00h]
0x14006b31c  test    ebx, ebx
0x14006b31e  jns     short loc_14006B382
0x14006b320  lea     rax, aApiCreatingTar; "API: Creating target stream"
0x14006b327  mov     r8, 27F002119F4h; struct UnionFs::StackEventTracer *
0x14006b331  mov     rdx, qword ptr [rbp+40h+arg_48]; int
0x14006b338  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b33f  mov     ecx, ebx; this
0x14006b341  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b346  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b34b  mov     rcx, [rbp+40h+arg_18]; Object
0x14006b34f  mov     [rbp+40h+arg_18], r12
0x14006b353  test    rcx, rcx
0x14006b356  jz      short loc_14006B364
0x14006b358  call    cs:__imp_ObfDereferenceObject
0x14006b35f  nop     dword ptr [rax+rax+00h]
0x14006b364  mov     rcx, [rbp+40h+var_B8]; FileHandle
0x14006b368  test    rcx, rcx
0x14006b36b  jz      loc_14006B1DC
0x14006b371  call    cs:__imp_FltClose
0x14006b378  nop     dword ptr [rax+rax+00h]
0x14006b37d  jmp     loc_14006B1DC
0x14006b382  mov     rdi, [rbp+40h+BytesWritten]
0x14006b389  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14006b38d  mov     rdx, [rbp+40h+arg_18]; FileObject
0x14006b391  mov     r9d, 8; Length
0x14006b397  mov     rcx, [rbp+40h+Instance]; Instance
0x14006b39b  mov     [rbp+40h+FileInformation], rdi
0x14006b39f  mov     [rsp+140h+DesiredAccess], 14h; FileInformationClass
0x14006b3a7  call    cs:__imp_FltSetInformationFile
0x14006b3ae  nop     dword ptr [rax+rax+00h]
0x14006b3b3  mov     ebx, eax
0x14006b3b5  test    eax, eax
0x14006b3b7  jns     short loc_14006B3CF
0x14006b3b9  lea     rax, aApiSettingTarg; "API: Setting target EOF"
0x14006b3c0  mov     r8, 28000211A00h
0x14006b3ca  jmp     loc_14006B331
0x14006b3cf  mov     rsi, qword ptr [rbp+40h+arg_48]
0x14006b3d6  mov     rcx, r15; InitiatingInstance
0x14006b3d9  mov     r9, [rbp+40h+arg_18]; struct _FLT_INSTANCE *
0x14006b3dd  mov     r8, [rbp+40h+Instance]; Instance
0x14006b3e1  mov     rdx, [rbp+40h+Object]; FileObject
0x14006b3e5  mov     [rsp+140h+IoStatusBlock], rsi; bool
0x14006b3ea  mov     qword ptr [rsp+140h+DesiredAccess], rdi; BytesWritten
0x14006b3ef  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)
0x14006b3f4  mov     ebx, eax
0x14006b3f6  test    eax, eax
0x14006b3f8  jns     short loc_14006B426
0x14006b3fa  lea     rax, aPushCopyingNam; "PUSH: Copying named stream"
0x14006b401  mov     r8, 28100211A0Ch; struct UnionFs::StackEventTracer *
0x14006b40b  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b412  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x14006b417  mov     rdx, rsi; int
0x14006b41a  mov     ecx, ebx; this
0x14006b41c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b421  jmp     loc_14006B34B
0x14006b426  mov     rcx, [rbp+40h+arg_18]; Object
0x14006b42a  mov     [rbp+40h+arg_18], r12
0x14006b42e  test    rcx, rcx
0x14006b431  jz      short loc_14006B43F
0x14006b433  call    cs:__imp_ObfDereferenceObject
0x14006b43a  nop     dword ptr [rax+rax+00h]
0x14006b43f  mov     rcx, [rbp+40h+var_B8]; FileHandle
0x14006b443  test    rcx, rcx
0x14006b446  jz      short loc_14006B454
0x14006b448  call    cs:__imp_FltClose
0x14006b44f  nop     dword ptr [rax+rax+00h]
0x14006b454  mov     rcx, [rbp+40h+Object]; Object
0x14006b458  mov     [rbp+40h+Object], r12
0x14006b45c  test    rcx, rcx
0x14006b45f  jz      short loc_14006B46D
0x14006b461  call    cs:__imp_ObfDereferenceObject
0x14006b468  nop     dword ptr [rax+rax+00h]
0x14006b46d  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14006b471  test    rcx, rcx
0x14006b474  jz      short loc_14006B482
0x14006b476  call    cs:__imp_FltClose
0x14006b47d  nop     dword ptr [rax+rax+00h]
0x14006b482  xor     eax, eax
0x14006b484  mov     rbx, [rsp+140h+arg_0]
0x14006b48c  add     rsp, 120h
0x14006b493  pop     r15
0x14006b495  pop     r12
0x14006b497  pop     rdi
0x14006b498  pop     rsi
0x14006b499  pop     rbp
0x14006b49a  retn
```
