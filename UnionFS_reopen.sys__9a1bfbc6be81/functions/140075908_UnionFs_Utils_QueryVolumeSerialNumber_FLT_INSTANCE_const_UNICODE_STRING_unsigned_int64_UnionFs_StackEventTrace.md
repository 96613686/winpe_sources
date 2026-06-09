# UnionFs::Utils::QueryVolumeSerialNumber(_FLT_INSTANCE const &,_UNICODE_STRING &,unsigned __int64 *,UnionFs::StackEventTracer &)

- ea: `0x140075908`
- end: `0x140075b27`
- name: `?QueryVolumeSerialNumber@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAU_UNICODE_STRING@@PEA_KAEAVStackEventTracer@2@@Z`
- size: `543`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, const struct _FLT_INSTANCE *, struct _UNICODE_STRING *, unsigned __int64 *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400352a8`

## callees

- `0x140056a50`
- `0x140075908`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140075a16`
- `ntoskrnl!ObfDereferenceObject` at `0x140075a5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140075ae7`
- `ntoskrnl!ObfDereferenceObject` at `0x140075a16`
- `ntoskrnl!ObfDereferenceObject` at `0x140075a5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140075ae7`
- `FLTMGR!FltCreateFileEx2` at `0x1400759ef`
- `FLTMGR!FltCreateFileEx2` at `0x1400759ef`
- `FLTMGR!FltClose` at `0x140075a6f`
- `FLTMGR!FltClose` at `0x140075afc`
- `FLTMGR!FltClose` at `0x140075a6f`
- `FLTMGR!FltClose` at `0x140075afc`
- `FLTMGR!FltQueryInformationFile` at `0x140075aab`
- `FLTMGR!FltQueryInformationFile` at `0x140075aab`

## string_xrefs

- `0x140075a26`: `API: Opening scratch root`

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
    v10 = 0x61100212305LL;
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
    v10 = 0x61200212310LL;
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
0x140075908  push    rbp
0x14007590a  push    rbx
0x14007590b  push    rsi
0x14007590c  push    rdi
0x14007590d  push    r14
0x14007590f  push    r15
0x140075911  lea     rbp, [rsp-38h]
0x140075916  sub     rsp, 138h
0x14007591d  mov     rax, cs:__security_cookie
0x140075924  xor     rax, rsp
0x140075927  mov     [rbp+60h+var_38], rax
0x14007592b  xor     r15d, r15d
0x14007592e  mov     [rbp+60h+var_B8.ObjectName], rdx
0x140075932  xorps   xmm0, xmm0
0x140075935  mov     qword ptr [rbp+60h+var_B8.Length], 30h ; '0'
0x14007593d  mov     r14, rcx
0x140075940  mov     qword ptr [rbp+60h+var_B8.Attributes], 240h
0x140075948  mov     eax, 28h ; '('
0x14007594d  mov     [rbp+60h+var_B8.RootDirectory], r15
0x140075951  movups  xmmword ptr [rbp+60h+var_88.Size], xmm0
0x140075955  mov     [rbp+60h+var_88.Size], ax
0x140075959  mov     rdi, r9
0x14007595c  mov     rsi, r8
0x14007595f  mov     [rbp+60h+Object], r15
0x140075963  lea     ecx, [rax-27h]
0x140075966  mov     [rbp+60h+FileObject], r15
0x14007596a  mov     [rbp+60h+var_68], rcx
0x14007596e  lea     rax, [rbp+60h+Object]
0x140075972  mov     [rbp+60h+var_D0], rax
0x140075976  lea     r9, [rbp+60h+FileObject]; FileObject
0x14007597a  mov     [rbp+60h+var_C0], cl
0x14007597d  lea     rax, [rbp+60h+var_88]
0x140075981  mov     [rsp+160h+DriverContext], rax; DriverContext
0x140075986  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x14007598a  mov     [rsp+160h+Flags], r15d; Flags
0x14007598f  lea     rax, [rbp+60h+var_60]
0x140075993  mov     [rsp+160h+EaLength], r15d; EaLength
0x140075998  mov     rdx, r14; Instance
0x14007599b  mov     [rsp+160h+EaBuffer], r15; EaBuffer
0x1400759a0  mov     [rsp+160h+CreateOptions], 200001h; CreateOptions
0x1400759a8  mov     [rsp+160h+CreateDisposition], ecx; CreateDisposition
0x1400759ac  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400759b3  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x1400759bb  mov     [rsp+160h+FileAttributes], r15d; FileAttributes
0x1400759c0  mov     [rsp+160h+AllocationSize], r15; AllocationSize
0x1400759c5  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x1400759ca  lea     rax, [rbp+60h+var_B8]
0x1400759ce  movups  xmmword ptr [rbp+60h+var_88.DeviceObjectHint], xmm0
0x1400759d2  mov     [rbp+60h+FileHandle], r15
0x1400759d6  movdqu  xmmword ptr [rbp+60h+var_B8.SecurityDescriptor], xmm0
0x1400759db  mov     [rsp+160h+ObjectAttributes], rax; char *
0x1400759e0  movups  xmmword ptr [rbp+60h+var_60], xmm0
0x1400759e4  mov     rcx, [rcx]; Filter
0x1400759e7  mov     [rsp+160h+DesiredAccess], 80h; DesiredAccess
0x1400759ef  call    cs:__imp_FltCreateFileEx2
0x1400759f6  nop     dword ptr [rax+rax+00h]
0x1400759fb  mov     ebx, eax
0x1400759fd  cmp     [rbp+60h+var_C0], r15b
0x140075a01  jz      short loc_140075A22
0x140075a03  mov     r8, [rbp+60h+var_D0]
0x140075a07  mov     rdx, [rbp+60h+FileObject]
0x140075a0b  mov     rcx, [r8]; Object
0x140075a0e  mov     [r8], rdx
0x140075a11  test    rcx, rcx
0x140075a14  jz      short loc_140075A22
0x140075a16  call    cs:__imp_ObfDereferenceObject
0x140075a1d  nop     dword ptr [rax+rax+00h]
0x140075a22  test    ebx, ebx
0x140075a24  jns     short loc_140075A82
0x140075a26  lea     rax, aApiOpeningScra_1; "API: Opening scratch root"
0x140075a2d  mov     r8, 61100212305h; struct UnionFs::StackEventTracer *
0x140075a37  lea     r9, aUnionfsUtilsQu; "UnionFs::Utils::QueryVolumeSerialNumber"
0x140075a3e  mov     qword ptr [rsp+160h+DesiredAccess], rax; char *
0x140075a43  mov     rdx, rdi; int
0x140075a46  mov     ecx, ebx; this
0x140075a48  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075a4d  mov     rcx, [rbp+60h+Object]; Object
0x140075a51  mov     [rbp+60h+Object], r15
0x140075a55  test    rcx, rcx
0x140075a58  jz      short loc_140075A66
0x140075a5a  call    cs:__imp_ObfDereferenceObject
0x140075a61  nop     dword ptr [rax+rax+00h]
0x140075a66  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x140075a6a  test    rcx, rcx
0x140075a6d  jz      short loc_140075A7B
0x140075a6f  call    cs:__imp_FltClose
0x140075a76  nop     dword ptr [rax+rax+00h]
0x140075a7b  mov     eax, ebx
0x140075a7d  jmp     loc_140075B0A
0x140075a82  mov     rdx, [rbp+60h+Object]; FileObject
0x140075a86  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x140075a8a  xor     eax, eax
0x140075a8c  mov     [rsp+160h+ObjectAttributes], r15; LengthReturned
0x140075a91  xorps   xmm0, xmm0
0x140075a94  mov     [rbp+60h+var_40], rax
0x140075a98  mov     rcx, r14; Instance
0x140075a9b  mov     [rsp+160h+DesiredAccess], 3Bh ; ';'; FileInformationClass
0x140075aa3  movups  [rbp+60h+FileInformation], xmm0
0x140075aa7  lea     r9d, [rax+18h]; Length
0x140075aab  call    cs:__imp_FltQueryInformationFile
0x140075ab2  nop     dword ptr [rax+rax+00h]
0x140075ab7  mov     ebx, eax
0x140075ab9  test    eax, eax
0x140075abb  jns     short loc_140075AD3
0x140075abd  lea     rax, aApiQueryInform; "API: Query information file"
0x140075ac4  mov     r8, 61200212310h
0x140075ace  jmp     loc_140075A37
0x140075ad3  mov     rcx, [rbp+60h+Object]; Object
0x140075ad7  mov     rax, qword ptr [rbp+60h+FileInformation]
0x140075adb  mov     [rsi], rax
0x140075ade  mov     [rbp+60h+Object], r15
0x140075ae2  test    rcx, rcx
0x140075ae5  jz      short loc_140075AF3
0x140075ae7  call    cs:__imp_ObfDereferenceObject
0x140075aee  nop     dword ptr [rax+rax+00h]
0x140075af3  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x140075af7  test    rcx, rcx
0x140075afa  jz      short loc_140075B08
0x140075afc  call    cs:__imp_FltClose
0x140075b03  nop     dword ptr [rax+rax+00h]
0x140075b08  xor     eax, eax
0x140075b0a  mov     rcx, [rbp+60h+var_38]
0x140075b0e  xor     rcx, rsp; StackCookie
0x140075b11  call    __security_check_cookie
0x140075b16  add     rsp, 138h
0x140075b1d  pop     r15
0x140075b1f  pop     r14
0x140075b21  pop     rdi
0x140075b22  pop     rsi
0x140075b23  pop     rbx
0x140075b24  pop     rbp
0x140075b25  retn
```
