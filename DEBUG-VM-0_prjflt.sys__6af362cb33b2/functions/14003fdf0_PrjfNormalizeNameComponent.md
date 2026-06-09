# PrjfNormalizeNameComponent

- ea: `0x14003fdf0`
- end: `0x14004044b`
- name: `PrjfNormalizeNameComponent`
- size: `1627`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PUNICODE_STRING FileName, PVOID FileInformation, ULONG Length, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140002f3c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14000d754`
- `0x14000f984`
- `0x14002aecc`
- `0x14003fdf0`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003fea3`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003fea3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400403e4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400403e4`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140040400`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140040400`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140040079`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140040079`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003ffc3`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003ffc3`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003ff0a`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003ff0a`
- `FLTMGR!FltQueryDirectoryFile` at `0x14004038e`
- `FLTMGR!FltQueryDirectoryFile` at `0x14004038e`
- `FLTMGR!FltCreateFileEx2` at `0x14004015d`
- `FLTMGR!FltCreateFileEx2` at `0x14004015d`
- `FLTMGR!FltClose` at `0x1400403cf`
- `FLTMGR!FltClose` at `0x1400403cf`
- `FLTMGR!FltGetInstanceContext` at `0x1400400bb`
- `FLTMGR!FltGetInstanceContext` at `0x1400400bb`
- `FLTMGR!FltReleaseContext` at `0x1400403a5`
- `FLTMGR!FltReleaseContext` at `0x1400403ba`
- `FLTMGR!FltReleaseContext` at `0x140040415`
- `FLTMGR!FltReleaseContext` at `0x1400403a5`
- `FLTMGR!FltReleaseContext` at `0x1400403ba`
- `FLTMGR!FltReleaseContext` at `0x140040415`

## pseudocode

```c
__int64 __fastcall PrjfNormalizeNameComponent(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        PUNICODE_STRING FileName,
        PVOID FileInformation,
        ULONG Length,
        char a8)
{
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  NTSTATUS DirectoryFile; // ebx
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  PVOID *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // r8d
  int SetContextFileObject; // eax
  int v27; // edx
  int v28; // r8d
  int v29; // eax
  int v30; // r8d
  unsigned int v31; // edx
  PFILE_OBJECT FileObjecta; // [rsp+80h] [rbp-80h] BYREF
  PVOID EcpContext; // [rsp+88h] [rbp-78h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-70h] BYREF
  PFLT_CONTEXT v35; // [rsp+98h] [rbp-68h] BYREF
  PFLT_CONTEXT v36; // [rsp+A0h] [rbp-60h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int128 v41; // [rsp+E0h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v44[3]; // [rsp+130h] [rbp+30h] BYREF

  Context = 0;
  EcpContext = 0;
  EcpList = 0;
  memset(v44, 0, sizeof(v44));
  FileHandle = 0;
  FileObjecta = 0;
  v35 = 0;
  v41 = 0;
  v36 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( Length < 0x10 )
    return 3221225485LL;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v40 = 1;
  TransactionParameterBlock = IoGetTransactionParameterBlock(FileObject);
  if ( TransactionParameterBlock )
  {
    LODWORD(v41) = -131056;
    *((_QWORD *)&v41 + 1) = TransactionParameterBlock->TransactionObject;
    DriverContext.TxnParameters = (PTXN_PARAMETER_BLOCK)&v41;
  }
  *((_QWORD *)&v44[0] + 1) = v44;
  v44[1] = 0x800000049000001CuLL;
  *(_QWORD *)&v44[0] = v44;
  DWORD2(v44[2]) = 48;
  v12 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  DirectoryFile = v12;
  if ( v12 >= 0 )
  {
    v16 = FltAllocateExtraCreateParameterFromLookasideList(
            Globals,
            &ECP_TYPE_OPEN_REPARSE_GUID,
            0x10u,
            0,
            0,
            qword_14001A640,
            &EcpContext);
    DirectoryFile = v16;
    if ( v16 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v17,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          28,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          86,
          v16);
      }
      goto LABEL_40;
    }
    v19 = EcpContext;
    *((_QWORD *)EcpContext + 1) = EcpContext;
    *v19 = v19;
    v20 = EcpContext;
    v21 = (PVOID *)*((_QWORD *)EcpContext + 1);
    if ( *v21 != EcpContext )
      __fastfail(3u);
    *((_QWORD *)&v44[0] + 1) = *((_QWORD *)EcpContext + 1);
    *(_QWORD *)&v44[0] = EcpContext;
    *v21 = v44;
    v20[1] = v44;
    if ( FltInsertExtraCreateParameter(Globals, EcpList, EcpContext) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v22);
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    DriverContext.Size = 40;
    DriverContext.ExtraCreateParameter = EcpList;
    *(&DriverContext.Size + 3) = 0;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    v40 = 1;
    if ( FltGetInstanceContext(Instance, &Context) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v23);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = (!(a8 & 1) << 6) | 0x200;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    DirectoryFile = FltCreateFileEx2(
                      Globals,
                      Instance,
                      &FileHandle,
                      &FileObjecta,
                      0x100001u,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x90u,
                      7u,
                      1u,
                      0x4021u,
                      0,
                      0,
                      0x800u,
                      &DriverContext);
    if ( DirectoryFile < 0 )
    {
      if ( DirectoryFile == -1073741191
        && ((BYTE10(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v24) = BYTE10(xmmword_14001A3D0) & 2;
        LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          785,
          v24,
          v25,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          17,
          29,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          141,
          121,
          (__int64)a3);
      }
      goto LABEL_40;
    }
    if ( (BYTE4(v44[1]) & 1) != 0 )
    {
      SetContextFileObject = PrjfGetSetContextFileObject(Instance, FileObjecta, 0, 0, 0, (__int64)&v35, (__int64)&v36);
      DirectoryFile = SetContextFileObject;
      if ( SetContextFileObject < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            517,
            v27,
            v28,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            30,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            170,
            SetContextFileObject,
            (__int64)a3);
        }
        goto LABEL_36;
      }
      v29 = PrjfPartiallyExpandDirectory(0, Instance, FileObjecta, FileName);
      v31 = 0x80000000;
      if ( (int)(v29 + 0x80000000) >= 0
        && v29 != -1073741772
        && ((BYTE10(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v31) = BYTE10(xmmword_14001A3D0) & 2;
        LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZZ(
          785,
          v31,
          v30,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          17,
          31,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          191,
          v29,
          (__int64)a3,
          (__int64)FileName);
      }
    }
    DirectoryFile = FltQueryDirectoryFile(
                      Instance,
                      FileObjecta,
                      FileInformation,
                      Length,
                      FileNamesInformation,
                      1u,
                      FileName,
                      1u,
                      0);
LABEL_36:
    if ( v35 )
      FltReleaseContext(v35);
    if ( v36 )
      FltReleaseContext(v36);
    goto LABEL_40;
  }
  if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v13,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      27,
      (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      72,
      v12);
  }
LABEL_40:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObjecta )
    ObfDereferenceObject(FileObjecta);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)DirectoryFile;
}

```

## disassembly

```asm
0x14003fdf0  mov     [rsp-8+arg_18], rbx
0x14003fdf5  push    rbp
0x14003fdf6  push    rsi
0x14003fdf7  push    rdi
0x14003fdf8  push    r12
0x14003fdfa  push    r13
0x14003fdfc  push    r14
0x14003fdfe  push    r15
0x14003fe00  lea     rbp, [rsp-70h]
0x14003fe05  sub     rsp, 170h
0x14003fe0c  mov     rax, cs:__security_cookie
0x14003fe13  xor     rax, rsp
0x14003fe16  mov     [rbp+0A0h+var_40], rax
0x14003fe1a  mov     rsi, [rbp+0A0h+FileName]
0x14003fe21  xor     r12d, r12d
0x14003fe24  mov     r15, [rbp+0A0h+FileInformation]
0x14003fe2b  xorps   xmm0, xmm0
0x14003fe2e  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x14003fe32  mov     r14, r8
0x14003fe35  mov     [rbp+0A0h+Context], r12
0x14003fe39  lea     ebx, [r12+10h]
0x14003fe3e  mov     [rbp+0A0h+var_118], r12
0x14003fe42  mov     rdi, rcx
0x14003fe45  mov     [rbp+0A0h+EcpList], r12
0x14003fe49  movups  [rbp+0A0h+var_70], xmm0
0x14003fe4d  mov     [rbp+0A0h+FileHandle], r12
0x14003fe51  movups  [rbp+0A0h+var_60], xmm0
0x14003fe55  mov     [rbp+0A0h+FileObject], r12
0x14003fe59  movups  [rbp+0A0h+var_50], xmm0
0x14003fe5d  mov     [rbp+0A0h+var_108], r12
0x14003fe61  movups  [rbp+0A0h+var_C0], xmm0
0x14003fe65  mov     [rbp+0A0h+var_100], r12
0x14003fe69  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x14003fe6d  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x14003fe71  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x14003fe75  cmp     [rbp+0A0h+Length], ebx
0x14003fe7b  jnb     short loc_14003FE87
0x14003fe7d  mov     eax, 0C000000Dh
0x14003fe82  jmp     loc_140040423
0x14003fe87  mov     eax, 28h ; '('
0x14003fe8c  mov     rcx, rdx; FileObject
0x14003fe8f  movups  xmmword ptr [rbp+0A0h+var_E8.Size], xmm0
0x14003fe93  mov     [rbp+0A0h+var_E8.Size], ax
0x14003fe97  movups  xmmword ptr [rbp+0A0h+var_E8.DeviceObjectHint], xmm0
0x14003fe9b  lea     r13d, [rax-27h]
0x14003fe9f  mov     [rbp+0A0h+var_C8], r13
0x14003fea3  call    cs:__imp_IoGetTransactionParameterBlock
0x14003feaa  nop     dword ptr [rax+rax+00h]
0x14003feaf  test    rax, rax
0x14003feb2  jz      short loc_14003FED1
0x14003feb4  mov     word ptr [rbp+0A0h+var_C0], bx
0x14003feb8  mov     rax, [rax+8]
0x14003febc  mov     qword ptr [rbp+0A0h+var_C0+8], rax
0x14003fec0  mov     eax, 0FFFEh
0x14003fec5  mov     word ptr [rbp+0A0h+var_C0+2], ax
0x14003fec9  lea     rax, [rbp+0A0h+var_C0]
0x14003fecd  mov     [rbp+0A0h+var_E8.TxnParameters], rax
0x14003fed1  mov     rcx, cs:Globals; Filter
0x14003fed8  lea     rax, [rbp+0A0h+var_70]
0x14003fedc  mov     qword ptr [rbp+0A0h+var_70+8], rax
0x14003fee0  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x14003fee4  lea     rax, [rbp+0A0h+var_70]
0x14003fee8  mov     dword ptr [rbp+0A0h+var_60], 9000001Ch
0x14003feef  xorps   xmm0, xmm0
0x14003fef2  mov     qword ptr [rbp+0A0h+var_70], rax
0x14003fef6  xor     edx, edx; Flags
0x14003fef8  mov     dword ptr [rbp+0A0h+var_60+4], 80000004h
0x14003feff  movups  [rbp+0A0h+var_60+8], xmm0
0x14003ff03  mov     dword ptr [rbp+0A0h+var_50+8], 30h ; '0'
0x14003ff0a  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14003ff11  nop     dword ptr [rax+rax+00h]
0x14003ff16  mov     ebx, eax
0x14003ff18  test    eax, eax
0x14003ff1a  jns     short loc_14003FF94
0x14003ff1c  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003ff22  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003ff29  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003ff30  setnz   r8b
0x14003ff34  and     dl, 20h
0x14003ff37  jnz     short loc_14003FF42
0x14003ff39  test    r8b, r8b
0x14003ff3c  jz      loc_1400403C6
0x14003ff42  mov     [rsp+1A0h+CreateDisposition], eax
0x14003ff46  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003ff4d  mov     [rsp+1A0h+ShareAccess], 448h
0x14003ff55  mov     qword ptr [rsp+1A0h+FileAttributes], rax
0x14003ff5a  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14003ff61  mov     [rsp+1A0h+AllocationSize], rax
0x14003ff66  mov     word ptr [rsp+1A0h+EcpContext], 1Bh
0x14003ff6d  mov     r9, cs:WPP_GLOBAL_Control
0x14003ff74  mov     ecx, 205h
0x14003ff79  mov     dword ptr [rsp+1A0h+LookasideList], 5
0x14003ff81  mov     byte ptr [rsp+1A0h+CleanupCallback], 2
0x14003ff86  mov     r9, [r9+40h]
0x14003ff8a  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003ff8f  jmp     loc_1400403C6
0x14003ff94  mov     rcx, cs:Globals; Filter
0x14003ff9b  lea     rax, [rbp+0A0h+var_118]
0x14003ff9f  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x14003ffa4  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14003ffab  xor     r9d, r9d; Flags
0x14003ffae  lea     rax, qword_14001A640
0x14003ffb5  mov     [rsp+1A0h+LookasideList], rax; LookasideList
0x14003ffba  mov     [rsp+1A0h+CleanupCallback], r12; CleanupCallback
0x14003ffbf  lea     r8d, [r9+10h]; SizeOfContext
0x14003ffc3  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14003ffca  nop     dword ptr [rax+rax+00h]
0x14003ffcf  mov     ebx, eax
0x14003ffd1  test    eax, eax
0x14003ffd3  jns     short loc_14004002B
0x14003ffd5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003ffdb  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003ffe2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003ffe9  setnz   r8b
0x14003ffed  and     dl, 20h
0x14003fff0  jnz     short loc_14003FFFB
0x14003fff2  test    r8b, r8b
0x14003fff5  jz      loc_1400403C6
0x14003fffb  mov     [rsp+1A0h+CreateDisposition], eax
0x14003ffff  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140040006  mov     [rsp+1A0h+ShareAccess], 456h
0x14004000e  mov     qword ptr [rsp+1A0h+FileAttributes], rax
0x140040013  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14004001a  mov     [rsp+1A0h+AllocationSize], rax
0x14004001f  mov     word ptr [rsp+1A0h+EcpContext], 1Ch
0x140040026  jmp     loc_14003FF6D
0x14004002b  mov     rax, [rbp+0A0h+var_118]
0x14004002f  mov     [rax+8], rax
0x140040033  mov     [rax], rax
0x140040036  mov     rax, [rbp+0A0h+var_118]
0x14004003a  mov     rcx, [rax+8]
0x14004003e  cmp     [rcx], rax
0x140040041  jz      short loc_14004004A
0x140040043  mov     ecx, 3
0x140040048  int     29h; Win8: RtlFailFast(ecx)
0x14004004a  mov     ebx, [rbp+0A0h+arg_38]
0x140040050  lea     rdx, [rbp+0A0h+var_70]
0x140040054  mov     qword ptr [rbp+0A0h+var_70+8], rcx
0x140040058  and     ebx, r13d
0x14004005b  mov     qword ptr [rbp+0A0h+var_70], rax
0x14004005f  mov     [rcx], rdx
0x140040062  lea     rcx, [rbp+0A0h+var_70]
0x140040066  mov     [rax+8], rcx
0x14004006a  mov     r8, [rbp+0A0h+var_118]; EcpContext
0x14004006e  mov     rdx, [rbp+0A0h+EcpList]; EcpList
0x140040072  mov     rcx, cs:Globals; Filter
0x140040079  call    cs:__imp_FltInsertExtraCreateParameter
0x140040080  nop     dword ptr [rax+rax+00h]
0x140040085  test    eax, eax
0x140040087  jns     short loc_14004008E
0x140040089  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14004008e  mov     eax, 28h ; '('
0x140040093  mov     dword ptr [rbp+0A0h+var_E8+2], r12d
0x140040097  mov     [rbp+0A0h+var_E8.Size], ax
0x14004009b  lea     rdx, [rbp+0A0h+Context]; Context
0x14004009f  mov     rax, [rbp+0A0h+EcpList]
0x1400400a3  xorps   xmm0, xmm0
0x1400400a6  mov     rcx, rdi; Instance
0x1400400a9  mov     [rbp+0A0h+var_E8.ExtraCreateParameter], rax
0x1400400ad  mov     word ptr [rbp+0A0h+var_E8+6], r12w
0x1400400b2  movdqu  xmmword ptr [rbp+0A0h+var_E8.DeviceObjectHint], xmm0
0x1400400b7  mov     [rbp+0A0h+var_C8], r13
0x1400400bb  call    cs:__imp_FltGetInstanceContext
0x1400400c2  nop     dword ptr [rax+rax+00h]
0x1400400c7  test    eax, eax
0x1400400c9  jns     short loc_1400400D0
0x1400400cb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400400d0  mov     rcx, cs:Globals; Filter
0x1400400d7  lea     rax, [rbp+0A0h+var_E8]
0x1400400db  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x1400400e0  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x1400400e4  mov     [rsp+1A0h+Flags], 800h; Flags
0x1400400ec  lea     rax, [rbp+0A0h+IoStatusBlock]
0x1400400f0  mov     [rsp+1A0h+EaLength], r12d; EaLength
0x1400400f5  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x1400400f9  mov     [rsp+1A0h+EaBuffer], r12; EaBuffer
0x1400400fe  xor     ebx, r13d
0x140040101  mov     [rsp+1A0h+CreateOptions], 4021h; CreateOptions
0x140040109  xorps   xmm0, xmm0
0x14004010c  mov     [rsp+1A0h+CreateDisposition], r13d; CreateDisposition
0x140040111  mov     rdx, rdi; Instance
0x140040114  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x14004011c  mov     [rsp+1A0h+FileAttributes], 90h; FileAttributes
0x140040124  mov     [rsp+1A0h+AllocationSize], r12; AllocationSize
0x140040129  mov     [rsp+1A0h+EcpContext], rax; IoStatusBlock
0x14004012e  lea     rax, [rbp+0A0h+ObjectAttributes]
0x140040132  mov     [rsp+1A0h+LookasideList], rax; ObjectAttributes
0x140040137  shl     ebx, 6
0x14004013a  bts     ebx, 9
0x14004013e  mov     dword ptr [rsp+1A0h+CleanupCallback], 100001h; DesiredAccess
0x140040146  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x14004014d  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r12
0x140040151  mov     [rbp+0A0h+ObjectAttributes.Attributes], ebx
0x140040154  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r14
0x140040158  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004015d  call    cs:__imp_FltCreateFileEx2
0x140040164  nop     dword ptr [rax+rax+00h]
0x140040169  mov     ebx, eax
0x14004016b  test    eax, eax
0x14004016d  jns     loc_1400401FD
0x140040173  mov     eax, 0C0000279h
0x140040178  cmp     ebx, eax
0x14004017a  jnz     loc_1400403C6
0x140040180  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x140040186  lea     rcx, WPP_RECORDER_INITIALIZED
0x14004018d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140040194  setnz   r8b
0x140040198  and     dl, 2
0x14004019b  jnz     short loc_1400401A6
0x14004019d  test    r8b, r8b
0x1400401a0  jz      loc_1400403C6
0x1400401a6  mov     r9, cs:WPP_GLOBAL_Control
0x1400401ad  mov     ecx, 311h
0x1400401b2  mov     qword ptr [rsp+1A0h+CreateOptions], r14
0x1400401b7  mov     [rsp+1A0h+CreateDisposition], eax
0x1400401bb  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400401c2  mov     [rsp+1A0h+ShareAccess], 48Dh
0x1400401ca  mov     r9, [r9+40h]
0x1400401ce  mov     qword ptr [rsp+1A0h+FileAttributes], rax
0x1400401d3  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x1400401da  mov     [rsp+1A0h+AllocationSize], rax
0x1400401df  mov     word ptr [rsp+1A0h+EcpContext], 1Dh
0x1400401e6  mov     dword ptr [rsp+1A0h+LookasideList], 11h
0x1400401ee  mov     byte ptr [rsp+1A0h+CleanupCallback], 3
0x1400401f3  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400401f8  jmp     loc_1400403C6
0x1400401fd  test    byte ptr [rbp+0A0h+var_60+4], r13b
0x140040201  jz      loc_140040361
0x140040207  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x14004020b  lea     rax, [rbp+0A0h+var_100]
0x14004020f  mov     qword ptr [rsp+1A0h+FileAttributes], rax; __int64
0x140040214  xor     r9d, r9d
0x140040217  lea     rax, [rbp+0A0h+var_108]
0x14004021b  mov     r8d, 80000000h
0x140040221  mov     [rsp+1A0h+AllocationSize], rax; __int64
0x140040226  mov     rcx, rdi; Instance
0x140040229  mov     [rsp+1A0h+EcpContext], r12; __int64
0x14004022e  mov     [rsp+1A0h+LookasideList], r12; __int64
0x140040233  mov     byte ptr [rsp+1A0h+CleanupCallback], r12b; char
0x140040238  call    PrjfGetSetContextFileObject
0x14004023d  mov     ebx, eax
0x14004023f  test    eax, eax
0x140040241  jns     short loc_1400402C0
0x140040243  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140040249  lea     rcx, WPP_RECORDER_INITIALIZED
0x140040250  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140040257  setnz   r8b
0x14004025b  and     dl, 20h
0x14004025e  jnz     short loc_140040269
0x140040260  test    r8b, r8b
0x140040263  jz      loc_14004039C
0x140040269  mov     r9, cs:WPP_GLOBAL_Control
0x140040270  mov     ecx, 205h
0x140040275  mov     qword ptr [rsp+1A0h+CreateOptions], r14
0x14004027a  mov     [rsp+1A0h+CreateDisposition], eax
0x14004027e  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140040285  mov     [rsp+1A0h+ShareAccess], 4AAh
0x14004028d  mov     r9, [r9+40h]
0x140040291  mov     qword ptr [rsp+1A0h+FileAttributes], rax
0x140040296  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14004029d  mov     [rsp+1A0h+AllocationSize], rax
0x1400402a2  mov     word ptr [rsp+1A0h+EcpContext], 1Eh
0x1400402a9  mov     dword ptr [rsp+1A0h+LookasideList], 5
0x1400402b1  mov     byte ptr [rsp+1A0h+CleanupCallback], 2
0x1400402b6  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400402bb  jmp     loc_14004039C
0x1400402c0  mov     r8, [rbp+0A0h+FileObject]; FileObject
0x1400402c4  mov     r9, rsi; FileName
0x1400402c7  mov     rdx, rdi; Instance
0x1400402ca  xor     ecx, ecx; CallbackData
0x1400402cc  call    PrjfPartiallyExpandDirectory
0x1400402d1  mov     edx, 80000000h
0x1400402d6  lea     ecx, [rax+rdx]
0x1400402d9  test    edx, ecx
0x1400402db  jnz     loc_140040361
0x1400402e1  cmp     eax, 0C0000034h
0x1400402e6  jz      short loc_140040361
0x1400402e8  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x1400402ee  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400402f5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400402fc  setnz   r8b
0x140040300  and     dl, 2
0x140040303  jnz     short loc_14004030A
0x140040305  test    r8b, r8b
0x140040308  jz      short loc_140040361
0x14004030a  mov     r9, cs:WPP_GLOBAL_Control
0x140040311  mov     ecx, 311h
0x140040316  mov     [rsp+1A0h+EaBuffer], rsi
0x14004031b  mov     qword ptr [rsp+1A0h+CreateOptions], r14
0x140040320  mov     [rsp+1A0h+CreateDisposition], eax
0x140040324  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004032b  mov     r9, [r9+40h]
0x14004032f  mov     [rsp+1A0h+ShareAccess], 4BFh
0x140040337  mov     qword ptr [rsp+1A0h+FileAttributes], rax
0x14004033c  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140040343  mov     [rsp+1A0h+AllocationSize], rax
0x140040348  mov     word ptr [rsp+1A0h+EcpContext], 1Fh
0x14004034f  mov     dword ptr [rsp+1A0h+LookasideList], 11h
0x140040357  mov     byte ptr [rsp+1A0h+CleanupCallback], 3
0x14004035c  call    WPP_RECORDER_AND_TRACE_SF_sDdZZ
  ... truncated ...
```
