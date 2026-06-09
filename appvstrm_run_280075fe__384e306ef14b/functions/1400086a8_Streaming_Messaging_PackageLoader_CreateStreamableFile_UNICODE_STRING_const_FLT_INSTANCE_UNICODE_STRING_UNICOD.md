# Streaming::Messaging::PackageLoader::CreateStreamableFile(_UNICODE_STRING const &,_FLT_INSTANCE *,_UNICODE_STRING *,_UNICODE_STRING const &,_LARGE_INTEGER &)

- ea: `0x1400086a8`
- end: `0x140008bd6`
- name: `?CreateStreamableFile@PackageLoader@Messaging@Streaming@@CAJAEBU_UNICODE_STRING@@PEAU_FLT_INSTANCE@@PEAU4@0AEAT_LARGE_INTEGER@@@Z`
- size: `1326`
- prototype: `static int(const struct _UNICODE_STRING *, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, const struct _UNICODE_STRING *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140008bdc`

## callees

- `0x140003368`
- `0x1400086a8`
- `0x14000b448`
- `0x14000f6e8`
- `0x14000f770`
- `0x14000f8a0`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400089a2`
- `ntoskrnl!ObfDereferenceObject` at `0x140008bab`
- `ntoskrnl!ObfDereferenceObject` at `0x1400089a2`
- `ntoskrnl!ObfDereferenceObject` at `0x140008bab`
- `FLTMGR!FltCreateFileEx` at `0x140008760`
- `FLTMGR!FltCreateFileEx` at `0x140008760`
- `FLTMGR!FltClose` at `0x140008832`
- `FLTMGR!FltClose` at `0x140008985`
- `FLTMGR!FltClose` at `0x140008b8e`
- `FLTMGR!FltClose` at `0x140008832`
- `FLTMGR!FltClose` at `0x140008985`
- `FLTMGR!FltClose` at `0x140008b8e`
- `FLTMGR!FltFsControlFile` at `0x1400089f0`
- `FLTMGR!FltFsControlFile` at `0x1400089f0`
- `FLTMGR!FltSetInformationFile` at `0x140008a25`
- `FLTMGR!FltSetInformationFile` at `0x140008a25`

## string_xrefs

- `0x140008795`: `PackageLoader::CreateStreamableFile() - Failed to create package file %s. Failure status = 0x%08X.`
- `0x140008899`: `PackageLoader::CreateStreamableFile() - Could not set short name %s on file %s. Failure status = 0x%08X.`
- `0x140008a5b`: `PackageLoader::CreateStreamableFile() - Could not allocate file %s, size %lld. Failure status = 0x%08X, check Disk space.`
- `0x140008af7`: `PackageLoader::CreateStreamableFile() - Could not set the streaming information for file %s. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::PackageLoader::CreateStreamableFile(
        struct _UNICODE_STRING *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        const struct _UNICODE_STRING *a4,
        union _LARGE_INTEGER *a5)
{
  struct _FLT_FILTER *v8; // rcx
  NTSTATUS inited; // edi
  struct _UNICODE_STRING *v10; // r9
  __int64 v11; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *Information; // rbx
  volatile signed __int32 *v14; // rbx
  void *v15; // rcx
  int v16; // r14d
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 *v19; // rax
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rbx
  struct _FILE_OBJECT *v24; // r14
  NTSTATUS v25; // eax
  union _LARGE_INTEGER *v26; // rbx
  union _LARGE_INTEGER v27; // r14
  __int64 v28; // rbx
  __int64 *v29; // rax
  struct _FILE_OBJECT *v30; // r14
  __int64 v31; // rbx
  __int64 *v32; // rax
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  ACCESS_MASK DesiredAccess[2]; // [rsp+28h] [rbp-B1h]
  ACCESS_MASK DesiredAccessa[2]; // [rsp+28h] [rbp-B1h]
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-A9h]
  POBJECT_ATTRIBUTES ObjectAttributesa; // [rsp+30h] [rbp-A9h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK FileInformation; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v41[8]; // [rsp+A0h] [rbp-39h] BYREF
  volatile signed __int32 *v42; // [rsp+A8h] [rbp-31h]
  _BYTE v43[8]; // [rsp+B0h] [rbp-29h] BYREF
  volatile signed __int32 *v44; // [rsp+B8h] [rbp-21h]
  struct _OBJECT_ATTRIBUTES v45; // [rsp+C8h] [rbp-11h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+5Fh] BYREF
  const struct _UNICODE_STRING *InputBuffer; // [rsp+150h] [rbp+77h] BYREF

  InputBuffer = a4;
  v45.ObjectName = a1;
  v8 = (struct _FLT_FILTER *)*((_QWORD *)Streaming::gStrmFltData + 1);
  FileObject = 0;
  FileHandle = 0;
  FileInformation = 0;
  *(_QWORD *)&v45.Length = 48;
  *(_QWORD *)&v45.Attributes = 576;
  v45.RootDirectory = 0;
  *(_OWORD *)&v45.SecurityDescriptor = 0;
  inited = FltCreateFileEx(
             v8,
             a2,
             &FileHandle,
             &FileObject,
             0x110181u,
             &v45,
             &FileInformation,
             0,
             0,
             7u,
             0,
             0x204960u,
             0,
             0,
             0x800u);
  if ( inited < 0 )
  {
    v11 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v41, a1);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&FileInformation);
    DesiredAccess[0] = inited;
    LogWrite(
      1,
      *CurrentActivityID,
      L"PackageLoader::CreateStreamableFile() - Failed to create package file %s. Failure status = 0x%08X.",
      v11,
      *(_QWORD *)DesiredAccess);
    Information = (volatile signed __int32 *)FileInformation.Information;
    if ( FileInformation.Information )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(FileInformation.Information + 8), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Information + 8LL))(Information);
        if ( _InterlockedExchangeAdd(Information + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Information + 16LL))(Information);
      }
    }
    v14 = v42;
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    v15 = FileHandle;
    if ( !FileHandle )
      goto LABEL_53;
    goto LABEL_52;
  }
  if ( !a3 )
    goto LABEL_33;
  v16 = Streaming::FileOperations::SetShortName(a2, FileObject, a3, v10);
  if ( v16 >= 0 )
    goto LABEL_33;
  v17 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v43, a3);
  v18 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&FileInformation, a1);
  v19 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v41);
  LODWORD(ObjectAttributes) = v16;
  LogWrite(
    1,
    *v19,
    L"PackageLoader::CreateStreamableFile() - Could not set short name %s on file %s. Failure status = 0x%08X.",
    v18,
    v17,
    ObjectAttributes);
  v20 = v42;
  if ( v42 )
  {
    if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  v21 = (volatile signed __int32 *)FileInformation.Information;
  if ( FileInformation.Information )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(FileInformation.Information + 8), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  v22 = v44;
  if ( v44 )
  {
    if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  if ( v16 == -1073741409 || v16 == -1073741771 )
  {
LABEL_33:
    v24 = FileObject;
    LOBYTE(InputBuffer) = 1;
    v25 = FltFsControlFile(a2, FileObject, 0x900C4u, &InputBuffer, 1u, 0, 0, 0);
    v26 = a5;
    inited = v25;
    if ( v25 >= 0 )
    {
      FileInformation.Pointer = (PVOID)a5->QuadPart;
      inited = FltSetInformationFile(a2, v24, &FileInformation, 8u, FileEndOfFileInformation);
    }
    v27 = *v26;
    if ( inited >= 0 )
    {
      if ( !v27.QuadPart )
        goto LABEL_51;
      v30 = FileObject;
      LODWORD(InputBuffer) = 0;
      Streaming::Context::StreamingBitMap::StreamingBitMap(
        (Streaming::Context::StreamingBitMap *)&v45,
        (int *)&InputBuffer);
      inited = (int)InputBuffer;
      if ( (int)InputBuffer >= 0 )
      {
        inited = Streaming::Context::StreamingBitMap::InitBitMap((PRTL_BITMAP)&v45, v26);
        if ( inited >= 0 )
          inited = Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(
                     a2,
                     v30,
                     (struct Streaming::Context::StreamingBitMap *)&v45);
      }
      Streaming::Context::StreamingBitMap::~StreamingBitMap((Streaming::Context::StreamingBitMap *)&v45);
      if ( inited >= 0 )
      {
LABEL_51:
        v15 = FileHandle;
        if ( !FileHandle )
        {
LABEL_53:
          if ( FileObject )
            ObfDereferenceObject(FileObject);
          return (unsigned int)inited;
        }
LABEL_52:
        FltClose(v15);
        FileHandle = 0;
        goto LABEL_53;
      }
      v31 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v41, a1);
      v32 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v43);
      DesiredAccessa[0] = inited;
      LogWrite(
        1,
        *v32,
        L"PackageLoader::CreateStreamableFile() - Could not set the streaming information for file %s. Failure status 0x%08X.",
        v31,
        *(_QWORD *)DesiredAccessa);
    }
    else
    {
      v28 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v41, &FileObject->FileName);
      v29 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v43);
      LODWORD(ObjectAttributesa) = inited;
      LogWrite(
        1,
        *v29,
        L"PackageLoader::CreateStreamableFile() - Could not allocate file %s, size %lld. Failure status = 0x%08X, check Disk space.",
        v28,
        v27.QuadPart,
        ObjectAttributesa);
    }
    v33 = v44;
    if ( v44 )
    {
      if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 16LL))(v33);
      }
    }
    v34 = v42;
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
    goto LABEL_51;
  }
  if ( FileHandle )
  {
    FltClose(FileHandle);
    FileHandle = 0;
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400086a8  mov     rax, rsp
0x1400086ab  mov     [rax+10h], rbx
0x1400086af  mov     [rax+18h], rsi
0x1400086b3  mov     [rax+20h], r9
0x1400086b7  push    rbp
0x1400086b8  push    rdi
0x1400086b9  push    r12
0x1400086bb  push    r13
0x1400086bd  push    r14
0x1400086bf  lea     rbp, [rax-57h]
0x1400086c3  sub     rsp, 100h
0x1400086ca  mov     [rsp+120h+Flags], 800h; Flags
0x1400086d2  lea     rax, [rbp+4Fh+FileInformation]
0x1400086d6  xor     r14d, r14d
0x1400086d9  mov     [rbp+4Fh+var_60.ObjectName], rcx
0x1400086dd  mov     [rsp+120h+EaLength], r14d; EaLength
0x1400086e2  lea     r9, [rbp+4Fh+FileObject]; FileObject
0x1400086e6  mov     [rsp+120h+EaBuffer], r14; EaBuffer
0x1400086eb  mov     r13, rcx
0x1400086ee  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x1400086f5  xorps   xmm0, xmm0
0x1400086f8  mov     [rsp+120h+CreateOptions], 204960h; CreateOptions
0x140008700  mov     rbx, r8
0x140008703  mov     [rsp+120h+CreateDisposition], r14d; CreateDisposition
0x140008708  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x14000870c  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x140008714  mov     r12, rdx
0x140008717  mov     rcx, [rcx+8]; Filter
0x14000871b  mov     [rsp+120h+FileAttributes], r14d; FileAttributes
0x140008720  mov     [rsp+120h+AllocationSize], r14; AllocationSize
0x140008725  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000872a  lea     rax, [rbp+4Fh+var_60]
0x14000872e  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140008733  mov     [rsp+120h+DesiredAccess], 110181h; DesiredAccess
0x14000873b  mov     [rbp+4Fh+FileObject], r14
0x14000873f  mov     [rbp+4Fh+FileHandle], r14
0x140008743  movups  xmmword ptr [rbp+4Fh+FileInformation], xmm0
0x140008747  mov     qword ptr [rbp+4Fh+var_60.Length], 30h ; '0'
0x14000874f  mov     qword ptr [rbp+4Fh+var_60.Attributes], 240h
0x140008757  mov     [rbp+4Fh+var_60.RootDirectory], r14
0x14000875b  movdqu  xmmword ptr [rbp+4Fh+var_60.SecurityDescriptor], xmm0
0x140008760  call    cs:__imp_FltCreateFileEx
0x140008767  nop     dword ptr [rax+rax+00h]
0x14000876c  mov     edi, eax
0x14000876e  test    eax, eax
0x140008770  jns     loc_140008847
0x140008776  mov     rdx, r13
0x140008779  lea     rcx, [rbp+4Fh+var_88]
0x14000877d  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008782  lea     rcx, [rbp+4Fh+FileInformation]
0x140008786  mov     rbx, [rax]
0x140008789  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000878e  mov     r9, rbx
0x140008791  mov     [rsp+120h+DesiredAccess], edi
0x140008795  lea     r8, aPackageloaderC; "PackageLoader::CreateStreamableFile() -"...
0x14000879c  lea     ecx, [r14+1]
0x1400087a0  mov     rdx, [rax]
0x1400087a3  call    LogWrite
0x1400087a8  mov     rbx, [rbp+4Fh+FileInformation.Information]
0x1400087ac  or      esi, 0FFFFFFFFh
0x1400087af  test    rbx, rbx
0x1400087b2  jz      short loc_1400087E8
0x1400087b4  mov     eax, esi
0x1400087b6  lock xadd [rbx+8], eax
0x1400087bb  add     eax, esi
0x1400087bd  jnz     short loc_1400087E8
0x1400087bf  mov     rax, [rbx]
0x1400087c2  mov     rcx, rbx
0x1400087c5  mov     rax, [rax+8]
0x1400087c9  call    _guard_dispatch_icall
0x1400087ce  mov     eax, esi
0x1400087d0  lock xadd [rbx+0Ch], eax
0x1400087d5  add     eax, esi
0x1400087d7  jnz     short loc_1400087E8
0x1400087d9  mov     rax, [rbx]
0x1400087dc  mov     rcx, rbx
0x1400087df  mov     rax, [rax+10h]
0x1400087e3  call    _guard_dispatch_icall
0x1400087e8  mov     rbx, [rbp+4Fh+var_80]
0x1400087ec  test    rbx, rbx
0x1400087ef  jz      short loc_140008825
0x1400087f1  mov     eax, esi
0x1400087f3  lock xadd [rbx+8], eax
0x1400087f8  add     eax, esi
0x1400087fa  jnz     short loc_140008825
0x1400087fc  mov     rax, [rbx]
0x1400087ff  mov     rcx, rbx
0x140008802  mov     rax, [rax+8]
0x140008806  call    _guard_dispatch_icall
0x14000880b  mov     eax, esi
0x14000880d  lock xadd [rbx+0Ch], eax
0x140008812  add     eax, esi
0x140008814  jnz     short loc_140008825
0x140008816  mov     rax, [rbx]
0x140008819  mov     rcx, rbx
0x14000881c  mov     rax, [rax+10h]
0x140008820  call    _guard_dispatch_icall
0x140008825  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140008829  test    rcx, rcx
0x14000882c  jz      loc_140008BA2
0x140008832  call    cs:__imp_FltClose
0x140008839  nop     dword ptr [rax+rax+00h]
0x14000883e  mov     [rbp+4Fh+FileHandle], r14
0x140008842  jmp     loc_140008BA2
0x140008847  or      esi, 0FFFFFFFFh
0x14000884a  test    rbx, rbx
0x14000884d  jz      loc_1400089B6
0x140008853  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x140008857  mov     r8, rbx; struct _FILE_OBJECT *
0x14000885a  mov     rcx, r12; Instance
0x14000885d  call    ?SetShortName@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_UNICODE_STRING@@@Z; Streaming::FileOperations::SetShortName(_FLT_INSTANCE *,_FILE_OBJECT &,_UNICODE_STRING &)
0x140008862  mov     r14d, eax
0x140008865  test    eax, eax
0x140008867  jns     loc_1400089B6
0x14000886d  mov     rdx, rbx
0x140008870  lea     rcx, [rbp+4Fh+var_78]
0x140008874  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008879  mov     rdx, r13
0x14000887c  lea     rcx, [rbp+4Fh+FileInformation]
0x140008880  mov     rdi, [rax]
0x140008883  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008888  lea     rcx, [rbp+4Fh+var_88]
0x14000888c  mov     rbx, [rax]
0x14000888f  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008894  mov     dword ptr [rsp+120h+ObjectAttributes], r14d
0x140008899  lea     r8, aPackageloaderC_4; "PackageLoader::CreateStreamableFile() -"...
0x1400088a0  mov     r9, rbx
0x1400088a3  mov     qword ptr [rsp+120h+DesiredAccess], rdi
0x1400088a8  lea     ecx, [rsi+2]
0x1400088ab  mov     rdx, [rax]
0x1400088ae  call    LogWrite
0x1400088b3  mov     rbx, [rbp+4Fh+var_80]
0x1400088b7  test    rbx, rbx
0x1400088ba  jz      short loc_1400088F0
0x1400088bc  mov     eax, esi
0x1400088be  lock xadd [rbx+8], eax
0x1400088c3  add     eax, esi
0x1400088c5  jnz     short loc_1400088F0
0x1400088c7  mov     rax, [rbx]
0x1400088ca  mov     rcx, rbx
0x1400088cd  mov     rax, [rax+8]
0x1400088d1  call    _guard_dispatch_icall
0x1400088d6  mov     eax, esi
0x1400088d8  lock xadd [rbx+0Ch], eax
0x1400088dd  add     eax, esi
0x1400088df  jnz     short loc_1400088F0
0x1400088e1  mov     rax, [rbx]
0x1400088e4  mov     rcx, rbx
0x1400088e7  mov     rax, [rax+10h]
0x1400088eb  call    _guard_dispatch_icall
0x1400088f0  mov     rbx, [rbp+4Fh+FileInformation.Information]
0x1400088f4  test    rbx, rbx
0x1400088f7  jz      short loc_14000892D
0x1400088f9  mov     eax, esi
0x1400088fb  lock xadd [rbx+8], eax
0x140008900  add     eax, esi
0x140008902  jnz     short loc_14000892D
0x140008904  mov     rax, [rbx]
0x140008907  mov     rcx, rbx
0x14000890a  mov     rax, [rax+8]
0x14000890e  call    _guard_dispatch_icall
0x140008913  mov     eax, esi
0x140008915  lock xadd [rbx+0Ch], eax
0x14000891a  add     eax, esi
0x14000891c  jnz     short loc_14000892D
0x14000891e  mov     rax, [rbx]
0x140008921  mov     rcx, rbx
0x140008924  mov     rax, [rax+10h]
0x140008928  call    _guard_dispatch_icall
0x14000892d  mov     rbx, [rbp+4Fh+var_70]
0x140008931  test    rbx, rbx
0x140008934  jz      short loc_14000896A
0x140008936  mov     eax, esi
0x140008938  lock xadd [rbx+8], eax
0x14000893d  add     eax, esi
0x14000893f  jnz     short loc_14000896A
0x140008941  mov     rax, [rbx]
0x140008944  mov     rcx, rbx
0x140008947  mov     rax, [rax+8]
0x14000894b  call    _guard_dispatch_icall
0x140008950  mov     eax, esi
0x140008952  lock xadd [rbx+0Ch], eax
0x140008957  add     eax, esi
0x140008959  jnz     short loc_14000896A
0x14000895b  mov     rax, [rbx]
0x14000895e  mov     rcx, rbx
0x140008961  mov     rax, [rax+10h]
0x140008965  call    _guard_dispatch_icall
0x14000896a  cmp     r14d, 0C000019Fh
0x140008971  jz      short loc_1400089B6
0x140008973  cmp     r14d, 0C0000035h
0x14000897a  jz      short loc_1400089B6
0x14000897c  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140008980  test    rcx, rcx
0x140008983  jz      short loc_140008999
0x140008985  call    cs:__imp_FltClose
0x14000898c  nop     dword ptr [rax+rax+00h]
0x140008991  mov     [rbp+4Fh+FileHandle], 0
0x140008999  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14000899d  test    rcx, rcx
0x1400089a0  jz      short loc_1400089AE
0x1400089a2  call    cs:__imp_ObfDereferenceObject
0x1400089a9  nop     dword ptr [rax+rax+00h]
0x1400089ae  mov     eax, r14d
0x1400089b1  jmp     loc_140008BB9
0x1400089b6  mov     r14, [rbp+4Fh+FileObject]
0x1400089ba  lea     r9, [rbp+4Fh+InputBuffer]; InputBuffer
0x1400089be  mov     [rsp+120h+AllocationSize], 0; LengthReturned
0x1400089c7  mov     rdx, r14; FileObject
0x1400089ca  mov     dword ptr [rsp+120h+IoStatusBlock], 0; OutputBufferLength
0x1400089d2  mov     r8d, 900C4h; FsControlCode
0x1400089d8  mov     [rsp+120h+ObjectAttributes], 0; OutputBuffer
0x1400089e1  mov     rcx, r12; Instance
0x1400089e4  mov     [rsp+120h+DesiredAccess], 1; InputBufferLength
0x1400089ec  mov     byte ptr [rbp+4Fh+InputBuffer], 1
0x1400089f0  call    cs:__imp_FltFsControlFile
0x1400089f7  nop     dword ptr [rax+rax+00h]
0x1400089fc  mov     rbx, [rbp+4Fh+arg_20]
0x140008a00  mov     edi, eax
0x140008a02  test    eax, eax
0x140008a04  js      short loc_140008A33
0x140008a06  mov     rax, [rbx]
0x140008a09  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140008a0d  mov     r9d, 8; Length
0x140008a13  mov     qword ptr [rbp+4Fh+FileInformation], rax
0x140008a17  mov     rdx, r14; FileObject
0x140008a1a  mov     [rsp+120h+DesiredAccess], 14h; FileInformationClass
0x140008a22  mov     rcx, r12; Instance
0x140008a25  call    cs:__imp_FltSetInformationFile
0x140008a2c  nop     dword ptr [rax+rax+00h]
0x140008a31  mov     edi, eax
0x140008a33  mov     r14, [rbx]
0x140008a36  test    edi, edi
0x140008a38  jns     short loc_140008A7C
0x140008a3a  mov     rdx, [rbp+4Fh+FileObject]
0x140008a3e  lea     rcx, [rbp+4Fh+var_88]
0x140008a42  add     rdx, 58h ; 'X'
0x140008a46  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008a4b  lea     rcx, [rbp+4Fh+var_78]
0x140008a4f  mov     rbx, [rax]
0x140008a52  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008a57  mov     dword ptr [rsp+120h+ObjectAttributes], edi
0x140008a5b  lea     r8, aPackageloaderC_0; "PackageLoader::CreateStreamableFile() -"...
0x140008a62  mov     r9, rbx
0x140008a65  mov     qword ptr [rsp+120h+DesiredAccess], r14
0x140008a6a  mov     ecx, 1
0x140008a6f  mov     rdx, [rax]
0x140008a72  call    LogWrite
0x140008a77  jmp     loc_140008B0B
0x140008a7c  test    r14, r14
0x140008a7f  jz      loc_140008B85
0x140008a85  mov     r14, [rbp+4Fh+FileObject]
0x140008a89  lea     rdx, [rbp+4Fh+InputBuffer]; int *
0x140008a8d  lea     rcx, [rbp+4Fh+var_60]; this
0x140008a91  mov     dword ptr [rbp+4Fh+InputBuffer], 0
0x140008a98  call    ??0StreamingBitMap@Context@Streaming@@QEAA@AEAJ@Z; Streaming::Context::StreamingBitMap::StreamingBitMap(long &)
0x140008a9d  mov     edi, dword ptr [rbp+4Fh+InputBuffer]
0x140008aa0  test    edi, edi
0x140008aa2  js      short loc_140008AC7
0x140008aa4  mov     rdx, rbx; union _LARGE_INTEGER *
0x140008aa7  lea     rcx, [rbp+4Fh+var_60]; BitMapHeader
0x140008aab  call    ?InitBitMap@StreamingBitMap@Context@Streaming@@QEAAJAEAT_LARGE_INTEGER@@@Z; Streaming::Context::StreamingBitMap::InitBitMap(_LARGE_INTEGER &)
0x140008ab0  mov     edi, eax
0x140008ab2  test    eax, eax
0x140008ab4  js      short loc_140008AC7
0x140008ab6  lea     r8, [rbp+4Fh+var_60]; struct Streaming::Context::StreamingBitMap *
0x140008aba  mov     rdx, r14; FileObject
0x140008abd  mov     rcx, r12; Instance
0x140008ac0  call    ?UpdateStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAVStreamingBitMap@23@@Z; Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,Streaming::Context::StreamingBitMap &)
0x140008ac5  mov     edi, eax
0x140008ac7  lea     rcx, [rbp+4Fh+var_60]; this
0x140008acb  call    ??1StreamingBitMap@Context@Streaming@@QEAA@XZ; Streaming::Context::StreamingBitMap::~StreamingBitMap(void)
0x140008ad0  test    edi, edi
0x140008ad2  jns     loc_140008B85
0x140008ad8  mov     rdx, r13
0x140008adb  lea     rcx, [rbp+4Fh+var_88]
0x140008adf  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008ae4  lea     rcx, [rbp+4Fh+var_78]
0x140008ae8  mov     rbx, [rax]
0x140008aeb  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140008af0  mov     r9, rbx
0x140008af3  mov     [rsp+120h+DesiredAccess], edi
0x140008af7  lea     r8, aPackageloaderC_7; "PackageLoader::CreateStreamableFile() -"...
0x140008afe  mov     ecx, 1
0x140008b03  mov     rdx, [rax]
0x140008b06  call    LogWrite
0x140008b0b  mov     rbx, [rbp+4Fh+var_70]
0x140008b0f  test    rbx, rbx
0x140008b12  jz      short loc_140008B48
0x140008b14  mov     eax, esi
0x140008b16  lock xadd [rbx+8], eax
0x140008b1b  add     eax, esi
0x140008b1d  jnz     short loc_140008B48
0x140008b1f  mov     rax, [rbx]
0x140008b22  mov     rcx, rbx
0x140008b25  mov     rax, [rax+8]
0x140008b29  call    _guard_dispatch_icall
0x140008b2e  mov     eax, esi
0x140008b30  lock xadd [rbx+0Ch], eax
0x140008b35  add     eax, esi
  ... truncated ...
```
