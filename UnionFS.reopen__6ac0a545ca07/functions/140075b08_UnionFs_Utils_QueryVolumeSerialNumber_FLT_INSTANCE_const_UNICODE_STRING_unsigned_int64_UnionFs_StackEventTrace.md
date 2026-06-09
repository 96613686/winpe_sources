# UnionFs::Utils::QueryVolumeSerialNumber(_FLT_INSTANCE const &,_UNICODE_STRING &,unsigned __int64 *,UnionFs::StackEventTracer &)

- ea: `0x140075b08`
- end: `0x140075d27`
- name: `?QueryVolumeSerialNumber@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAU_UNICODE_STRING@@PEA_KAEAVStackEventTracer@2@@Z`
- size: `543`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, const struct _FLT_INSTANCE *, struct _UNICODE_STRING *, unsigned __int64 *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400353e0`

## callees

- `0x140056bd0`
- `0x140075b08`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140075c16`
- `ntoskrnl!ObfDereferenceObject` at `0x140075c5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140075ce7`
- `ntoskrnl!ObfDereferenceObject` at `0x140075c16`
- `ntoskrnl!ObfDereferenceObject` at `0x140075c5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140075ce7`
- `FLTMGR!FltCreateFileEx2` at `0x140075bef`
- `FLTMGR!FltCreateFileEx2` at `0x140075bef`
- `FLTMGR!FltClose` at `0x140075c6f`
- `FLTMGR!FltClose` at `0x140075cfc`
- `FLTMGR!FltClose` at `0x140075c6f`
- `FLTMGR!FltClose` at `0x140075cfc`
- `FLTMGR!FltQueryInformationFile` at `0x140075cab`
- `FLTMGR!FltQueryInformationFile` at `0x140075cab`

## string_xrefs

- `0x140075c26`: `API: Opening scratch root`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::QueryVolumeSerialNumber(
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int64 *a4)
{
  int v5; // edi
  NTSTATUS v7; // ebx
  PVOID v8; // rcx
  const char *v9; // rax
  __int64 v10; // r8
  PVOID v11; // rcx
  PVOID v13; // rcx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  PVOID *p_Object; // [rsp+90h] [rbp-70h]
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  char v19; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES v20; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  __int128 FileInformation; // [rsp+110h] [rbp+10h] BYREF
  __int64 v25; // [rsp+120h] [rbp+20h]

  v20.ObjectName = a2;
  *(_QWORD *)&v20.Length = 48;
  *(_QWORD *)&v20.Attributes = 576;
  v20.RootDirectory = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v5 = (int)a4;
  Object = 0;
  FileObject = 0;
  v22 = 1;
  p_Object = &Object;
  v19 = 1;
  FileHandle = 0;
  *(_OWORD *)&v20.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v7 = FltCreateFileEx2(
         *(PFLT_FILTER *)UnionFs::g_FilterState,
         Instance,
         &FileHandle,
         &FileObject,
         0x80u,
         &v20,
         &IoStatusBlock,
         0,
         0,
         7u,
         1u,
         0x200001u,
         0,
         0,
         0,
         &DriverContext);
  if ( v19 )
  {
    v8 = *p_Object;
    *p_Object = FileObject;
    if ( v8 )
      ObfDereferenceObject(v8);
  }
  if ( v7 < 0 )
  {
    v9 = "API: Opening scratch root";
    v10 = 0x6110021233BLL;
LABEL_6:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v7,
      v5,
      (struct UnionFs::StackEventTracer *)v10,
      (unsigned __int64)"UnionFs::Utils::QueryVolumeSerialNumber",
      v9,
      ObjectAttributes);
    v11 = Object;
    Object = 0;
    if ( v11 )
      ObfDereferenceObject(v11);
    if ( FileHandle )
      FltClose(FileHandle);
    return (unsigned int)v7;
  }
  v25 = 0;
  FileInformation = 0;
  v7 = FltQueryInformationFile(
         Instance,
         (PFILE_OBJECT)Object,
         &FileInformation,
         0x18u,
         FileMaximumInformation|FileBothDirectoryInformation,
         0);
  if ( v7 < 0 )
  {
    v9 = "API: Query information file";
    v10 = 0x61200212346LL;
    goto LABEL_6;
  }
  v13 = Object;
  *(_QWORD *)&a3->Length = FileInformation;
  Object = 0;
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( FileHandle )
    FltClose(FileHandle);
  return 0;
}

```

## disassembly

```asm
0x140075b08  push    rbp
0x140075b0a  push    rbx
0x140075b0b  push    rsi
0x140075b0c  push    rdi
0x140075b0d  push    r14
0x140075b0f  push    r15
0x140075b11  lea     rbp, [rsp-38h]
0x140075b16  sub     rsp, 138h
0x140075b1d  mov     rax, cs:__security_cookie
0x140075b24  xor     rax, rsp
0x140075b27  mov     [rbp+60h+var_38], rax
0x140075b2b  xor     r15d, r15d
0x140075b2e  mov     [rbp+60h+var_B8.ObjectName], rdx
0x140075b32  xorps   xmm0, xmm0
0x140075b35  mov     qword ptr [rbp+60h+var_B8.Length], 30h ; '0'
0x140075b3d  mov     r14, rcx
0x140075b40  mov     qword ptr [rbp+60h+var_B8.Attributes], 240h
0x140075b48  mov     eax, 28h ; '('
0x140075b4d  mov     [rbp+60h+var_B8.RootDirectory], r15
0x140075b51  movups  xmmword ptr [rbp+60h+var_88.Size], xmm0
0x140075b55  mov     [rbp+60h+var_88.Size], ax
0x140075b59  mov     rdi, r9
0x140075b5c  mov     rsi, r8
0x140075b5f  mov     [rbp+60h+Object], r15
0x140075b63  lea     ecx, [rax-27h]
0x140075b66  mov     [rbp+60h+FileObject], r15
0x140075b6a  mov     [rbp+60h+var_68], rcx
0x140075b6e  lea     rax, [rbp+60h+Object]
0x140075b72  mov     [rbp+60h+var_D0], rax
0x140075b76  lea     r9, [rbp+60h+FileObject]; FileObject
0x140075b7a  mov     [rbp+60h+var_C0], cl
0x140075b7d  lea     rax, [rbp+60h+var_88]
0x140075b81  mov     [rsp+160h+DriverContext], rax; DriverContext
0x140075b86  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140075b8a  mov     [rsp+160h+Flags], r15d; Flags
0x140075b8f  lea     rax, [rbp+60h+var_60]
0x140075b93  mov     [rsp+160h+EaLength], r15d; EaLength
0x140075b98  mov     rdx, r14; Instance
0x140075b9b  mov     [rsp+160h+EaBuffer], r15; EaBuffer
0x140075ba0  mov     [rsp+160h+CreateOptions], 200001h; CreateOptions
0x140075ba8  mov     [rsp+160h+CreateDisposition], ecx; CreateDisposition
0x140075bac  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140075bb3  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x140075bbb  mov     [rsp+160h+FileAttributes], r15d; FileAttributes
0x140075bc0  mov     [rsp+160h+AllocationSize], r15; AllocationSize
0x140075bc5  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140075bca  lea     rax, [rbp+60h+var_B8]
0x140075bce  movups  xmmword ptr [rbp+60h+var_88.DeviceObjectHint], xmm0
0x140075bd2  mov     [rbp+60h+FileHandle], r15
0x140075bd6  movdqu  xmmword ptr [rbp+60h+var_B8.SecurityDescriptor], xmm0
0x140075bdb  mov     [rsp+160h+ObjectAttributes], rax; char *
0x140075be0  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x140075be4  mov     rcx, [rcx]; Filter
0x140075be7  mov     [rsp+160h+DesiredAccess], 80h; DesiredAccess
0x140075bef  call    cs:__imp_FltCreateFileEx2
0x140075bf6  nop     dword ptr [rax+rax+00h]
0x140075bfb  mov     ebx, eax
0x140075bfd  cmp     [rbp+60h+var_C0], r15b
0x140075c01  jz      short loc_140075C22
0x140075c03  mov     r8, [rbp+60h+var_D0]
0x140075c07  mov     rdx, [rbp+60h+FileObject]
0x140075c0b  mov     rcx, [r8]; Object
0x140075c0e  mov     [r8], rdx
0x140075c11  test    rcx, rcx
0x140075c14  jz      short loc_140075C22
0x140075c16  call    cs:__imp_ObfDereferenceObject
0x140075c1d  nop     dword ptr [rax+rax+00h]
0x140075c22  test    ebx, ebx
0x140075c24  jns     short loc_140075C82
0x140075c26  lea     rax, aApiOpeningScra_1; "API: Opening scratch root"
0x140075c2d  mov     r8, 6110021233Bh; struct UnionFs::StackEventTracer *
0x140075c37  lea     r9, aUnionfsUtilsQu; "UnionFs::Utils::QueryVolumeSerialNumber"
0x140075c3e  mov     qword ptr [rsp+160h+DesiredAccess], rax; char *
0x140075c43  mov     rdx, rdi; int
0x140075c46  mov     ecx, ebx; this
0x140075c48  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075c4d  mov     rcx, [rbp+60h+Object]; Object
0x140075c51  mov     [rbp+60h+Object], r15
0x140075c55  test    rcx, rcx
0x140075c58  jz      short loc_140075C66
0x140075c5a  call    cs:__imp_ObfDereferenceObject
0x140075c61  nop     dword ptr [rax+rax+00h]
0x140075c66  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x140075c6a  test    rcx, rcx
0x140075c6d  jz      short loc_140075C7B
0x140075c6f  call    cs:__imp_FltClose
0x140075c76  nop     dword ptr [rax+rax+00h]
0x140075c7b  mov     eax, ebx
0x140075c7d  jmp     loc_140075D0A
0x140075c82  mov     rdx, [rbp+60h+Object]; FileObject
0x140075c86  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x140075c8a  xor     eax, eax
0x140075c8c  mov     [rsp+160h+ObjectAttributes], r15; LengthReturned
0x140075c91  xorps   xmm0, xmm0
0x140075c94  mov     [rbp+60h+var_40], rax
0x140075c98  mov     rcx, r14; Instance
0x140075c9b  mov     [rsp+160h+DesiredAccess], 3Bh ; ';'; FileInformationClass
0x140075ca3  movups  [rbp+60h+FileInformation], xmm0
0x140075ca7  lea     r9d, [rax+18h]; Length
0x140075cab  call    cs:__imp_FltQueryInformationFile
0x140075cb2  nop     dword ptr [rax+rax+00h]
0x140075cb7  mov     ebx, eax
0x140075cb9  test    eax, eax
0x140075cbb  jns     short loc_140075CD3
0x140075cbd  lea     rax, aApiQueryInform; "API: Query information file"
0x140075cc4  mov     r8, 61200212346h
0x140075cce  jmp     loc_140075C37
0x140075cd3  mov     rcx, [rbp+60h+Object]; Object
0x140075cd7  mov     rax, qword ptr [rbp+60h+FileInformation]
0x140075cdb  mov     [rsi], rax
0x140075cde  mov     [rbp+60h+Object], r15
0x140075ce2  test    rcx, rcx
0x140075ce5  jz      short loc_140075CF3
0x140075ce7  call    cs:__imp_ObfDereferenceObject
0x140075cee  nop     dword ptr [rax+rax+00h]
0x140075cf3  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x140075cf7  test    rcx, rcx
0x140075cfa  jz      short loc_140075D08
0x140075cfc  call    cs:__imp_FltClose
0x140075d03  nop     dword ptr [rax+rax+00h]
0x140075d08  xor     eax, eax
0x140075d0a  mov     rcx, [rbp+60h+var_38]
0x140075d0e  xor     rcx, rsp; StackCookie
0x140075d11  call    __security_check_cookie
0x140075d16  add     rsp, 138h
0x140075d1d  pop     r15
0x140075d1f  pop     r14
0x140075d21  pop     rdi
0x140075d22  pop     rsi
0x140075d23  pop     rbx
0x140075d24  pop     rbp
0x140075d25  retn
```
