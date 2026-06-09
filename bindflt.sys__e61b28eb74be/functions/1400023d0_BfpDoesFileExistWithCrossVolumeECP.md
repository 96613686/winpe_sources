# BfpDoesFileExistWithCrossVolumeECP

- ea: `0x1400023d0`
- end: `0x14000272f`
- name: `BfpDoesFileExistWithCrossVolumeECP`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400157a0`

## callees

- `0x1400023d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400024d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14000267f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14000267f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140002526`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140002526`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14000271e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14000271e`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400025a2`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400025a2`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400026a6`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400026a6`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140002563`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140002563`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400026f0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400026f0`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140002707`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140002707`
- `FLTMGR!FltCreateFileEx2` at `0x1400024ab`
- `FLTMGR!FltCreateFileEx2` at `0x140002653`
- `FLTMGR!FltCreateFileEx2` at `0x1400024ab`
- `FLTMGR!FltCreateFileEx2` at `0x140002653`
- `FLTMGR!FltClose` at `0x1400024c2`
- `FLTMGR!FltClose` at `0x14000266a`
- `FLTMGR!FltClose` at `0x1400024c2`
- `FLTMGR!FltClose` at `0x14000266a`
- `FLTMGR!FltObjectDereference` at `0x1400026be`
- `FLTMGR!FltObjectDereference` at `0x1400026d7`
- `FLTMGR!FltObjectDereference` at `0x1400026be`
- `FLTMGR!FltObjectDereference` at `0x1400026d7`

## pseudocode

```c
NTSTATUS __fastcall BfpDoesFileExistWithCrossVolumeECP(
        struct _UNICODE_STRING *a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        ULONG CreateOptions,
        int a5)
{
  NTSTATUS v8; // ebx
  NTSTATUS result; // eax
  _QWORD *v10; // rdx
  void *v11; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v12; // rcx
  void *FileHandle; // [rsp+80h] [rbp-61h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-59h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-51h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp+7h] BYREF
  PVOID EcpContext; // [rsp+140h] [rbp+5Fh] BYREF
  PECP_LIST EcpList; // [rsp+150h] [rbp+6Fh] BYREF

  ObjectAttributes.ObjectName = a1;
  v16 = a3;
  EcpList = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&DriverContext, 0, sizeof(DriverContext));
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  EcpContext = 0;
  FileHandle = 0;
  FileObject = 0;
  DriverContext.Size = 40;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = FltCreateFileEx2(
         g_BindFltState,
         a2,
         &FileHandle,
         &FileObject,
         0x80u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         7u,
         1u,
         CreateOptions,
         0,
         0,
         a5 | 8,
         &DriverContext);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v8 == -2147483603 )
    return 0;
  if ( (unsigned int)(v8 + 1073740952) > 1 )
    return v8;
  result = FltAllocateExtraCreateParameterList(g_BindFltState, 0, &EcpList);
  if ( result >= 0 )
  {
    result = FltAllocateExtraCreateParameter(
               g_BindFltState,
               &GUID_ECP_FLT_CREATEFILE_TARGET,
               0x20u,
               0,
               0,
               0x6D6E4642u,
               &EcpContext);
    if ( result >= 0 )
    {
      *((_WORD *)EcpContext + 12) = 1;
      *(_QWORD *)EcpContext = 0;
      *((_QWORD *)EcpContext + 1) = 0;
      *((_QWORD *)EcpContext + 2) = 0;
      result = FltInsertExtraCreateParameter(g_BindFltState, EcpList, EcpContext);
      if ( result >= 0 )
      {
        DriverContext.ExtraCreateParameter = EcpList;
        *(_DWORD *)(&DriverContext.Size + 1) = 0;
        *(&DriverContext.Size + 3) = 0;
        *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
        DriverContext.Size = 40;
        v16 = a3;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = a1;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v8 = FltCreateFileEx2(
               g_BindFltState,
               a2,
               &FileHandle,
               &FileObject,
               0x80u,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0,
               7u,
               1u,
               0,
               0,
               0,
               0,
               &DriverContext);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( FileObject )
          ObfDereferenceObject(FileObject);
        FltRemoveExtraCreateParameter(g_BindFltState, EcpList, &GUID_ECP_FLT_CREATEFILE_TARGET, &EcpContext, 0);
        v10 = EcpContext;
        if ( *(_QWORD *)EcpContext )
        {
          FltObjectDereference(*(PVOID *)EcpContext);
          v10 = EcpContext;
        }
        v11 = (void *)v10[1];
        if ( v11 )
        {
          FltObjectDereference(v11);
          v10 = EcpContext;
        }
        v12 = (struct _FLT_FILE_NAME_INFORMATION *)v10[2];
        if ( v12 )
        {
          FltReleaseFileNameInformation(v12);
          v10 = EcpContext;
        }
        FltFreeExtraCreateParameter(g_BindFltState, v10);
        FltFreeExtraCreateParameterList(g_BindFltState, EcpList);
        return v8;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400023d0  mov     [rsp-8+arg_8], rbx
0x1400023d5  push    rbp
0x1400023d6  push    rsi
0x1400023d7  push    rdi
0x1400023d8  push    r12
0x1400023da  push    r13
0x1400023dc  push    r14
0x1400023de  push    r15
0x1400023e0  lea     rbp, [rsp-1Fh]
0x1400023e5  sub     rsp, 100h
0x1400023ec  mov     eax, [rbp+4Fh+arg_20]
0x1400023ef  xor     r15d, r15d
0x1400023f2  xorps   xmm0, xmm0
0x1400023f5  mov     [rbp+4Fh+var_78.ObjectName], rcx
0x1400023f9  or      eax, 8
0x1400023fc  mov     [rbp+4Fh+var_80], r8
0x140002400  mov     r14, rcx
0x140002403  mov     [rbp+4Fh+EcpList], r15
0x140002407  lea     rcx, [rbp+4Fh+var_A0]
0x14000240b  mov     qword ptr [rbp+4Fh+var_78.Length], 30h ; '0'
0x140002413  mov     [rsp+130h+DriverContext], rcx; DriverContext
0x140002418  mov     rdi, r8
0x14000241b  mov     rcx, cs:g_BindFltState; Filter
0x140002422  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x140002426  mov     [rsp+130h+Flags], eax; Flags
0x14000242a  mov     r12d, 1
0x140002430  mov     [rsp+130h+EaLength], r15d; EaLength
0x140002435  lea     rax, [rbp+4Fh+var_48]
0x140002439  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x14000243e  mov     r13d, 28h ; '('
0x140002444  mov     [rsp+130h+CreateOptions], r9d; CreateOptions
0x140002449  mov     rsi, rdx
0x14000244c  mov     [rsp+130h+CreateDisposition], r12d; CreateDisposition
0x140002451  lea     r9, [rbp+4Fh+FileObject]; FileObject
0x140002455  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14000245d  mov     [rsp+130h+FileAttributes], r15d; FileAttributes
0x140002462  mov     [rsp+130h+AllocationSize], r15; AllocationSize
0x140002467  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14000246c  lea     rax, [rbp+4Fh+var_78]
0x140002470  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x140002475  movups  xmmword ptr [rbp+4Fh+var_A0.Size], xmm0
0x140002479  mov     [rsp+130h+DesiredAccess], 80h; DesiredAccess
0x140002481  mov     qword ptr [rbp+4Fh+var_78.Attributes], 240h
0x140002489  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x14000248d  mov     [rbp+4Fh+EcpContext], r15
0x140002491  mov     [rbp+4Fh+FileHandle], r15
0x140002495  mov     [rbp+4Fh+FileObject], r15
0x140002499  movups  xmmword ptr [rbp+4Fh+var_A0.DeviceObjectHint], xmm0
0x14000249d  mov     [rbp+4Fh+var_A0.Size], r13w
0x1400024a2  mov     [rbp+4Fh+var_78.RootDirectory], r15
0x1400024a6  movdqu  xmmword ptr [rbp+4Fh+var_78.SecurityDescriptor], xmm0
0x1400024ab  call    cs:__imp_FltCreateFileEx2
0x1400024b2  nop     dword ptr [rax+rax+00h]
0x1400024b7  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400024bb  mov     ebx, eax
0x1400024bd  test    rcx, rcx
0x1400024c0  jz      short loc_1400024CE
0x1400024c2  call    cs:__imp_FltClose
0x1400024c9  nop     dword ptr [rax+rax+00h]
0x1400024ce  mov     rcx, [rbp+4Fh+FileObject]; Object
0x1400024d2  test    rcx, rcx
0x1400024d5  jz      short loc_1400024E3
0x1400024d7  call    cs:__imp_ObfDereferenceObject
0x1400024de  nop     dword ptr [rax+rax+00h]
0x1400024e3  cmp     ebx, 8000002Dh
0x1400024e9  jz      short loc_140002514
0x1400024eb  lea     eax, [rbx+3FFFFC98h]
0x1400024f1  cmp     eax, r12d
0x1400024f4  jbe     short loc_140002519
0x1400024f6  mov     eax, ebx
0x1400024f8  mov     rbx, [rsp+130h+arg_8]
0x140002500  add     rsp, 100h
0x140002507  pop     r15
0x140002509  pop     r14
0x14000250b  pop     r13
0x14000250d  pop     r12
0x14000250f  pop     rdi
0x140002510  pop     rsi
0x140002511  pop     rbp
0x140002512  retn
0x140002514  mov     eax, r15d
0x140002517  jmp     short loc_1400024F8
0x140002519  mov     rcx, cs:g_BindFltState; Filter
0x140002520  lea     r8, [rbp+4Fh+EcpList]; EcpList
0x140002524  xor     edx, edx; Flags
0x140002526  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14000252d  nop     dword ptr [rax+rax+00h]
0x140002532  test    eax, eax
0x140002534  js      short loc_1400024F8
0x140002536  mov     rcx, cs:g_BindFltState; Filter
0x14000253d  lea     rax, [rbp+4Fh+EcpContext]
0x140002541  mov     [rsp+130h+IoStatusBlock], rax; EcpContext
0x140002546  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14000254d  mov     dword ptr [rsp+130h+ObjectAttributes], 6D6E4642h; PoolTag
0x140002555  xor     r9d, r9d; Flags
0x140002558  mov     r8d, 20h ; ' '; SizeOfContext
0x14000255e  mov     qword ptr [rsp+130h+DesiredAccess], r15; CleanupCallback
0x140002563  call    cs:__imp_FltAllocateExtraCreateParameter
0x14000256a  nop     dword ptr [rax+rax+00h]
0x14000256f  test    eax, eax
0x140002571  js      short loc_1400024F8
0x140002573  mov     rax, [rbp+4Fh+EcpContext]
0x140002577  mov     [rax+18h], r12w
0x14000257c  mov     rax, [rbp+4Fh+EcpContext]
0x140002580  mov     [rax], r15
0x140002583  mov     rax, [rbp+4Fh+EcpContext]
0x140002587  mov     [rax+8], r15
0x14000258b  mov     rax, [rbp+4Fh+EcpContext]
0x14000258f  mov     [rax+10h], r15
0x140002593  mov     r8, [rbp+4Fh+EcpContext]; EcpContext
0x140002597  mov     rdx, [rbp+4Fh+EcpList]; EcpList
0x14000259b  mov     rcx, cs:g_BindFltState; Filter
0x1400025a2  call    cs:__imp_FltInsertExtraCreateParameter
0x1400025a9  nop     dword ptr [rax+rax+00h]
0x1400025ae  test    eax, eax
0x1400025b0  js      loc_1400024F8
0x1400025b6  mov     rax, [rbp+4Fh+EcpList]
0x1400025ba  lea     r9, [rbp+4Fh+FileObject]; FileObject
0x1400025be  mov     rcx, cs:g_BindFltState; Filter
0x1400025c5  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x1400025c9  mov     [rbp+4Fh+var_A0.ExtraCreateParameter], rax
0x1400025cd  xorps   xmm0, xmm0
0x1400025d0  lea     rax, [rbp+4Fh+var_A0]
0x1400025d4  mov     dword ptr [rbp+4Fh+var_A0+2], r15d
0x1400025d8  mov     [rsp+130h+DriverContext], rax; DriverContext
0x1400025dd  mov     rdx, rsi; Instance
0x1400025e0  mov     [rsp+130h+Flags], r15d; Flags
0x1400025e5  lea     rax, [rbp+4Fh+var_48]
0x1400025e9  mov     [rsp+130h+EaLength], r15d; EaLength
0x1400025ee  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x1400025f3  mov     [rsp+130h+CreateOptions], r15d; CreateOptions
0x1400025f8  mov     [rsp+130h+CreateDisposition], r12d; CreateDisposition
0x1400025fd  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140002605  mov     [rsp+130h+FileAttributes], r15d; FileAttributes
0x14000260a  mov     [rsp+130h+AllocationSize], r15; AllocationSize
0x14000260f  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x140002614  lea     rax, [rbp+4Fh+var_78]
0x140002618  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14000261d  mov     [rsp+130h+DesiredAccess], 80h; DesiredAccess
0x140002625  mov     word ptr [rbp+4Fh+var_A0+6], r15w
0x14000262a  movdqu  xmmword ptr [rbp+4Fh+var_A0.DeviceObjectHint], xmm0
0x14000262f  mov     [rbp+4Fh+var_A0.Size], r13w
0x140002634  mov     [rbp+4Fh+var_80], rdi
0x140002638  mov     [rbp+4Fh+var_78.Length], 30h ; '0'
0x14000263f  mov     [rbp+4Fh+var_78.RootDirectory], r15
0x140002643  mov     [rbp+4Fh+var_78.Attributes], 240h
0x14000264a  mov     [rbp+4Fh+var_78.ObjectName], r14
0x14000264e  movdqu  xmmword ptr [rbp+4Fh+var_78.SecurityDescriptor], xmm0
0x140002653  call    cs:__imp_FltCreateFileEx2
0x14000265a  nop     dword ptr [rax+rax+00h]
0x14000265f  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140002663  mov     ebx, eax
0x140002665  test    rcx, rcx
0x140002668  jz      short loc_140002676
0x14000266a  call    cs:__imp_FltClose
0x140002671  nop     dword ptr [rax+rax+00h]
0x140002676  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14000267a  test    rcx, rcx
0x14000267d  jz      short loc_14000268B
0x14000267f  call    cs:__imp_ObfDereferenceObject
0x140002686  nop     dword ptr [rax+rax+00h]
0x14000268b  mov     rdx, [rbp+4Fh+EcpList]; EcpList
0x14000268f  lea     r9, [rbp+4Fh+EcpContext]; EcpContext
0x140002693  mov     rcx, cs:g_BindFltState; Filter
0x14000269a  lea     r8, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x1400026a1  mov     qword ptr [rsp+130h+DesiredAccess], r15; EcpContextSize
0x1400026a6  call    cs:__imp_FltRemoveExtraCreateParameter
0x1400026ad  nop     dword ptr [rax+rax+00h]
0x1400026b2  mov     rdx, [rbp+4Fh+EcpContext]
0x1400026b6  mov     rcx, [rdx]; FltObject
0x1400026b9  test    rcx, rcx
0x1400026bc  jz      short loc_1400026CE
0x1400026be  call    cs:__imp_FltObjectDereference
0x1400026c5  nop     dword ptr [rax+rax+00h]
0x1400026ca  mov     rdx, [rbp+4Fh+EcpContext]
0x1400026ce  mov     rcx, [rdx+8]; FltObject
0x1400026d2  test    rcx, rcx
0x1400026d5  jz      short loc_1400026E7
0x1400026d7  call    cs:__imp_FltObjectDereference
0x1400026de  nop     dword ptr [rax+rax+00h]
0x1400026e3  mov     rdx, [rbp+4Fh+EcpContext]
0x1400026e7  mov     rcx, [rdx+10h]; FileNameInformation
0x1400026eb  test    rcx, rcx
0x1400026ee  jz      short loc_140002700
0x1400026f0  call    cs:__imp_FltReleaseFileNameInformation
0x1400026f7  nop     dword ptr [rax+rax+00h]
0x1400026fc  mov     rdx, [rbp+4Fh+EcpContext]; EcpContext
0x140002700  mov     rcx, cs:g_BindFltState; Filter
0x140002707  call    cs:__imp_FltFreeExtraCreateParameter
0x14000270e  nop     dword ptr [rax+rax+00h]
0x140002713  mov     rdx, [rbp+4Fh+EcpList]; EcpList
0x140002717  mov     rcx, cs:g_BindFltState; Filter
0x14000271e  call    cs:__imp_FltFreeExtraCreateParameterList
0x140002725  nop     dword ptr [rax+rax+00h]
0x14000272a  jmp     loc_1400024F6
```
