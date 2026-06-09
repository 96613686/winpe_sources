# BfConvertContainerRootIdToShortNames

- ea: `0x14001d2c0`
- end: `0x14001d96e`
- name: `BfConvertContainerRootIdToShortNames`
- size: `1710`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001b280`
- `0x14001efcc`

## callees

- `0x140001348`
- `0x140003304`
- `0x140004cc0`
- `0x14001d2c0`
- `0x14001e5c8`
- `0x14001e6fc`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x14001d486`
- `ntoskrnl!PsGetHostSilo` at `0x14001d486`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001d54d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001d635`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001d54d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001d635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d95d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d95d`
- `ntoskrnl!ExAllocatePool2` at `0x14001d3a6`
- `ntoskrnl!ExAllocatePool2` at `0x14001d3a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d5b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d933`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d5b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d933`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001d56e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001d65a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001d56e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001d65a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14001d601`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14001d601`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d68e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d944`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d68e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d944`
- `FLTMGR!FltCreateFileEx2` at `0x14001d51e`
- `FLTMGR!FltCreateFileEx2` at `0x14001d51e`
- `FLTMGR!FltClose` at `0x14001d594`
- `FLTMGR!FltClose` at `0x14001d922`
- `FLTMGR!FltClose` at `0x14001d594`
- `FLTMGR!FltClose` at `0x14001d922`
- `FLTMGR!FltObjectDereference` at `0x14001d6bd`
- `FLTMGR!FltObjectDereference` at `0x14001d6bd`

## pseudocode

```c
__int64 __fastcall BfConvertContainerRootIdToShortNames(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v3; // rdx
  NTSTATUS FileNameInformationUnsafe; // ebx
  unsigned __int16 v5; // r8
  __int16 v6; // dx
  __int64 i; // r9
  __int16 v8; // ax
  USHORT v9; // bx
  unsigned __int16 *Pool2; // rax
  unsigned __int16 *v11; // rdi
  size_t v12; // r8
  unsigned __int64 v13; // rdx
  int v14; // ecx
  unsigned __int16 v15; // r12
  USHORT v16; // ax
  PFILE_OBJECT v17; // rcx
  struct _FLT_INSTANCE *v18; // r13
  unsigned __int16 v19; // r10
  __int64 v20; // rdx
  int v21; // edx
  int v23; // r9d
  int v24; // r8d
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  PFLT_INSTANCE Instance; // [rsp+88h] [rbp-78h]
  __int128 v29; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING VolumeName; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+C0h] [rbp-40h] BYREF
  __int64 HostSilo; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK v35; // [rsp+118h] [rbp+18h] BYREF
  char v36; // [rsp+180h] [rbp+80h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+190h] [rbp+90h] BYREF
  PFILE_OBJECT FileObject; // [rsp+198h] [rbp+98h] BYREF

  *a2 = 0;
  FileHandle = 0;
  LOWORD(HostSilo) = 0;
  FileObject = 0;
  v3 = *a1;
  v29 = 0;
  FileNameInformation = 0;
  Destination = 0;
  Instance = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(&DriverContext, 0, sizeof(DriverContext));
  v35 = 0;
  FileNameInformationUnsafe = BfValidateContainerRootId(a1, v3);
  if ( FileNameInformationUnsafe < 0 )
  {
    v11 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        6,
        10,
        (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
        75,
        FileNameInformationUnsafe);
    goto LABEL_31;
  }
  v5 = a1[2] >> 1;
  v6 = 0;
  for ( i = 0; (unsigned __int16)i < v5; v6 = v8 )
  {
    v8 = v6 + 1;
    if ( a1[(unsigned __int16)i + 3] != 92 )
      v8 = v6;
    LOWORD(i) = i + 1;
  }
  v9 = a1[1] + 26 * v6;
  Pool2 = (unsigned __int16 *)ExAllocatePool2(256, (unsigned __int16)(v9 + 6), 1886209602, i);
  v11 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        6,
        11,
        (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
        115);
    FileNameInformationUnsafe = -1073741670;
    goto LABEL_31;
  }
  *Pool2 = v9 + 6;
  v12 = a1[1];
  Pool2[1] = a1[1];
  memmove(Pool2 + 3, a1 + 3, v12);
  v13 = v11[1];
  v11[2] = v13;
  v14 = a1[1];
  if ( a1[2] - v14 == 2 )
  {
    v18 = Instance;
    v11[(v13 >> 1) + 3] = 92;
    v11[2] += 2;
    FileNameInformationUnsafe = 0;
LABEL_28:
    *a2 = v11;
    v11 = 0;
    goto LABEL_29;
  }
  LOWORD(v29) = a1[1];
  Destination.Buffer = v11 + 3;
  VolumeName = 0;
  *((_QWORD *)&v29 + 1) = a1 + 3;
  v15 = v14 + 4;
  WORD1(v29) = v9;
  Destination.MaximumLength = v9;
  v16 = v11[1];
  VolumeName.Length = v14;
  VolumeName.MaximumLength = v14;
  Destination.Length = v16;
  VolumeName.Buffer = a1 + 3;
  BfGetInstanceFromVolumeName(&VolumeName);
  v18 = Instance;
  v36 = 1;
  while ( 1 )
  {
    v19 = a1[2];
    v20 = v19;
    LOWORD(v20) = v19 >> 1;
    if ( !(v19 >> 1) || !*((_QWORD *)&v29 + 1) )
      goto LABEL_10;
    v24 = (unsigned __int16)v20;
    v17 = (PFILE_OBJECT)(v15 >> 1);
    if ( (unsigned int)v17 < (unsigned __int16)v20 )
    {
      v20 = 92;
      do
      {
        if ( *(_WORD *)(*((_QWORD *)&v29 + 1) + 2LL * (__int16)v17) == 92 )
          break;
        LOWORD(v17) = (_WORD)v17 + 1;
      }
      while ( (__int16)v17 < v24 );
    }
    if ( (__int16)v17 < v24 )
    {
      LOWORD(v29) = 2 * (_WORD)v17;
      v15 = 2 * (_WORD)v17 + 4;
    }
    else
    {
LABEL_10:
      v36 = 0;
      LOWORD(v29) = a1[2];
    }
    HostSilo = 1;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    HostSilo = PsGetHostSilo(v17, v20);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v29;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileNameInformationUnsafe = FltCreateFileEx2(
                                  g_BindFltState,
                                  v18,
                                  &FileHandle,
                                  &FileObject,
                                  0x120089u,
                                  &ObjectAttributes,
                                  &v35,
                                  0,
                                  0,
                                  7u,
                                  1u,
                                  0x200000u,
                                  0,
                                  0,
                                  0,
                                  &DriverContext);
    if ( FileNameInformationUnsafe < 0 )
      break;
    FileNameInformation = 0;
    if ( !FileObject )
      goto LABEL_48;
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, v18, 0x103u, &FileNameInformation);
    if ( FileNameInformationUnsafe < 0 )
      break;
    if ( !FileNameInformation->Name.Length && FileNameInformation->Volume.Length )
    {
LABEL_48:
      FileNameInformationUnsafe = -1073741811;
      break;
    }
    FileNameInformationUnsafe = RtlAppendUnicodeToString(&Destination, L"\\");
    if ( FileNameInformationUnsafe < 0
      || (FileNameInformationUnsafe = RtlAppendUnicodeStringToString(&Destination, &FileNameInformation->Name),
          FileNameInformationUnsafe < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      AllocationSize = FileNameInformationUnsafe;
      v23 = 13;
      IoStatusBlock = 63;
      goto LABEL_44;
    }
    v11[2] += 2;
    v11[2] += FileNameInformation->Name.Length;
    FltReleaseFileNameInformation(FileNameInformation);
    FileNameInformationUnsafe = 0;
    FileNameInformation = 0;
LABEL_16:
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    v17 = FileObject;
    if ( FileObject )
    {
      ObfDereferenceObject(FileObject);
      FileObject = 0;
    }
    if ( !v36 )
      goto LABEL_28;
  }
  if ( FileNameInformationUnsafe == -1073741772
    || FileNameInformationUnsafe == -1073741766
    || FileNameInformationUnsafe == -1071906811 )
  {
    FileNameInformationUnsafe = RtlAppendUnicodeToString(&Destination, L"\\");
    if ( FileNameInformationUnsafe < 0
      || (FileNameInformationUnsafe = RtlAppendUnicodeStringToString(&Destination, &g_NoShortComponent),
          FileNameInformationUnsafe < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      AllocationSize = FileNameInformationUnsafe;
      v23 = 14;
      IoStatusBlock = 98;
      goto LABEL_44;
    }
    v11[2] += 4;
    FileNameInformationUnsafe = 0;
    goto LABEL_16;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    AllocationSize = FileNameInformationUnsafe;
    v23 = 15;
    IoStatusBlock = 107;
LABEL_44:
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      6,
      v23,
      (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
      IoStatusBlock,
      AllocationSize);
  }
LABEL_29:
  if ( v18 )
    FltObjectDereference(v18);
LABEL_31:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v11 )
    ExFreePoolWithTag(v11, 0x706D4642u);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x14001d2c0  mov     [rsp-8+arg_8], rdx
0x14001d2c5  push    rbp
0x14001d2c6  push    rbx
0x14001d2c7  push    rsi
0x14001d2c8  push    rdi
0x14001d2c9  push    r12
0x14001d2cb  push    r13
0x14001d2cd  push    r14
0x14001d2cf  push    r15
0x14001d2d1  lea     rbp, [rsp-38h]
0x14001d2d6  sub     rsp, 138h
0x14001d2dd  xorps   xmm0, xmm0
0x14001d2e0  xor     r13d, r13d
0x14001d2e3  mov     r14, rcx
0x14001d2e6  mov     [rdx], r13
0x14001d2e9  xor     ecx, ecx
0x14001d2eb  mov     [rbp+70h+FileHandle], r13
0x14001d2ef  xorps   xmm1, xmm1
0x14001d2f2  mov     word ptr [rbp+70h+var_90], cx
0x14001d2f6  mov     rcx, r14
0x14001d2f9  mov     [rbp+70h+FileObject], r13
0x14001d300  movzx   edx, word ptr [r14]
0x14001d304  movups  [rbp+70h+var_E0], xmm0
0x14001d308  mov     [rbp+70h+FileNameInformation], r13
0x14001d30f  movups  xmmword ptr [rbp+70h+Destination.Length], xmm1
0x14001d313  mov     [rbp+70h+Instance], r13
0x14001d317  movups  xmmword ptr [rbp+70h+var_88.Length], xmm0
0x14001d31b  movups  xmmword ptr [rbp+70h+var_88.ObjectName], xmm0
0x14001d31f  movups  xmmword ptr [rbp+70h+var_88.SecurityDescriptor], xmm0
0x14001d323  movups  xmmword ptr [rbp+70h+var_B0.Size], xmm0
0x14001d327  movups  xmmword ptr [rbp+70h+var_B0.DeviceObjectHint], xmm0
0x14001d32b  movups  xmmword ptr [rbp+70h+var_58], xmm0
0x14001d32f  call    BfValidateContainerRootId
0x14001d334  mov     ebx, eax
0x14001d336  test    eax, eax
0x14001d338  js      loc_14001D793
0x14001d33e  movzx   r8d, word ptr [r14+4]
0x14001d343  lea     ebx, [r13+5Ch]
0x14001d347  movzx   r10d, word ptr [r14+2]
0x14001d34c  lea     r11d, [r13+1]
0x14001d350  shr     r8w, 1
0x14001d354  mov     edx, r13d
0x14001d357  mov     r9d, r13d
0x14001d35a  cmp     r13w, r8w
0x14001d35e  jnb     short loc_14001D382
0x14001d360  movzx   eax, r9w
0x14001d364  movzx   ecx, word ptr [r14+rax*2+6]
0x14001d36a  lea     eax, [r11+rdx]
0x14001d36e  cmp     cx, bx
0x14001d371  cmovnz  ax, dx
0x14001d375  add     r9w, r11w
0x14001d379  movzx   edx, ax
0x14001d37c  cmp     r9w, r8w
0x14001d380  jb      short loc_14001D360
0x14001d382  movzx   eax, dx
0x14001d385  mov     r15d, 6
0x14001d38b  imul    ebx, eax, 1Ah
0x14001d38e  mov     ecx, 100h
0x14001d393  mov     r8d, 706D4642h
0x14001d399  add     bx, r10w
0x14001d39d  lea     eax, [r15+rbx]
0x14001d3a1  movzx   esi, ax
0x14001d3a4  mov     edx, esi
0x14001d3a6  call    cs:__imp_ExAllocatePool2
0x14001d3ad  nop     dword ptr [rax+rax+00h]
0x14001d3b2  mov     rdi, rax
0x14001d3b5  test    rax, rax
0x14001d3b8  jz      loc_14001D8AF
0x14001d3be  mov     [rax], si
0x14001d3c1  lea     r13, [r14+6]
0x14001d3c5  movzx   eax, word ptr [r14+2]
0x14001d3ca  lea     r12, [rdi+6]
0x14001d3ce  mov     r8d, eax; Size
0x14001d3d1  mov     [rdi+2], ax
0x14001d3d5  mov     rdx, r13; Src
0x14001d3d8  mov     rcx, r12; void *
0x14001d3db  call    memmove
0x14001d3e0  movzx   edx, word ptr [rdi+2]
0x14001d3e4  lea     esi, [r15-4]
0x14001d3e8  mov     [rdi+4], dx
0x14001d3ec  movzx   ecx, word ptr [r14+2]
0x14001d3f1  movzx   eax, word ptr [r14+4]
0x14001d3f6  sub     eax, ecx
0x14001d3f8  cmp     eax, esi
0x14001d3fa  jz      loc_14001D906
0x14001d400  mov     word ptr [rbp+70h+var_E0], cx
0x14001d404  lea     rdx, [rbp+70h+Instance]
0x14001d408  mov     [rbp+70h+Destination.Buffer], r12
0x14001d40c  xorps   xmm0, xmm0
0x14001d40f  movups  xmmword ptr [rbp+70h+VolumeName.Length], xmm0
0x14001d413  mov     qword ptr [rbp+70h+var_E0+8], r13
0x14001d417  lea     r12d, [rcx+4]
0x14001d41b  mov     word ptr [rbp+70h+var_E0+2], bx
0x14001d41f  mov     [rbp+70h+Destination.MaximumLength], bx
0x14001d423  movzx   eax, word ptr [rdi+2]
0x14001d427  mov     [rbp+70h+VolumeName.Length], cx
0x14001d42b  mov     [rbp+70h+VolumeName.MaximumLength], cx
0x14001d42f  lea     rcx, [rbp+70h+VolumeName]; VolumeName
0x14001d433  mov     [rbp+70h+Destination.Length], ax
0x14001d437  mov     [rbp+70h+VolumeName.Buffer], r13
0x14001d43b  call    BfGetInstanceFromVolumeName
0x14001d440  mov     r13, [rbp+70h+Instance]
0x14001d444  lea     r11d, [r15-5]
0x14001d448  mov     [rbp+70h+arg_0], r11b
0x14001d44f  xor     ebx, ebx
0x14001d451  movzx   r10d, word ptr [r14+4]
0x14001d456  movzx   edx, r10w
0x14001d45a  shr     dx, 1
0x14001d45d  jnz     loc_14001D850
0x14001d463  mov     [rbp+70h+arg_0], bl
0x14001d469  mov     word ptr [rbp+70h+var_E0], r10w
0x14001d46e  xorps   xmm0, xmm0
0x14001d471  mov     [rbp+70h+var_90], r11
0x14001d475  mov     eax, 28h ; '('
0x14001d47a  movups  xmmword ptr [rbp+70h+var_B0.Size], xmm0
0x14001d47e  mov     [rbp+70h+var_B0.Size], ax
0x14001d482  movups  xmmword ptr [rbp+70h+var_B0.DeviceObjectHint], xmm0
0x14001d486  call    cs:__imp_PsGetHostSilo
0x14001d48d  nop     dword ptr [rax+rax+00h]
0x14001d492  mov     rcx, cs:g_BindFltState; Filter
0x14001d499  lea     r9, [rbp+70h+FileObject]; FileObject
0x14001d4a0  mov     [rbp+70h+var_90], rax
0x14001d4a4  lea     r8, [rbp+70h+FileHandle]; FileHandle
0x14001d4a8  lea     rax, [rbp+70h+var_E0]
0x14001d4ac  mov     [rbp+70h+var_88.Length], 30h ; '0'
0x14001d4b3  mov     [rbp+70h+var_88.ObjectName], rax
0x14001d4b7  xorps   xmm0, xmm0
0x14001d4ba  lea     rax, [rbp+70h+var_B0]
0x14001d4be  mov     [rbp+70h+var_88.RootDirectory], rbx
0x14001d4c2  mov     [rsp+170h+DriverContext], rax; DriverContext
0x14001d4c7  mov     rdx, r13; Instance
0x14001d4ca  mov     [rsp+170h+Flags], ebx; Flags
0x14001d4ce  lea     rax, [rbp+70h+var_58]
0x14001d4d2  mov     [rsp+170h+EaLength], ebx; EaLength
0x14001d4d6  mov     [rsp+170h+EaBuffer], rbx; EaBuffer
0x14001d4db  mov     [rsp+170h+CreateOptions], 200000h; CreateOptions
0x14001d4e3  mov     [rsp+170h+CreateDisposition], 1; CreateDisposition
0x14001d4eb  mov     [rsp+170h+ShareAccess], 7; ShareAccess
0x14001d4f3  mov     [rsp+170h+FileAttributes], ebx; FileAttributes
0x14001d4f7  mov     [rsp+170h+AllocationSize], rbx; AllocationSize
0x14001d4fc  mov     [rsp+170h+IoStatusBlock], rax; IoStatusBlock
0x14001d501  lea     rax, [rbp+70h+var_88]
0x14001d505  mov     [rsp+170h+ObjectAttributes], rax; ObjectAttributes
0x14001d50a  mov     [rsp+170h+DesiredAccess], 120089h; DesiredAccess
0x14001d512  mov     [rbp+70h+var_88.Attributes], 240h
0x14001d519  movdqu  xmmword ptr [rbp+70h+var_88.SecurityDescriptor], xmm0
0x14001d51e  call    cs:__imp_FltCreateFileEx2
0x14001d525  nop     dword ptr [rax+rax+00h]
0x14001d52a  mov     ebx, eax
0x14001d52c  xor     eax, eax
0x14001d52e  test    ebx, ebx
0x14001d530  jns     loc_14001D5DA
0x14001d536  cmp     ebx, 0C0000034h
0x14001d53c  jnz     loc_14001D805
0x14001d542  lea     rdx, Source; "\\"
0x14001d549  lea     rcx, [rbp+70h+Destination]; Destination
0x14001d54d  call    cs:__imp_RtlAppendUnicodeToString
0x14001d554  nop     dword ptr [rax+rax+00h]
0x14001d559  mov     ebx, eax
0x14001d55b  test    eax, eax
0x14001d55d  js      loc_14001D73A
0x14001d563  lea     rdx, g_NoShortComponent; Source
0x14001d56a  lea     rcx, [rbp+70h+Destination]; Destination
0x14001d56e  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001d575  nop     dword ptr [rax+rax+00h]
0x14001d57a  mov     ebx, eax
0x14001d57c  test    eax, eax
0x14001d57e  js      loc_14001D73A
0x14001d584  add     word ptr [rdi+4], 4
0x14001d589  xor     ebx, ebx
0x14001d58b  mov     rcx, [rbp+70h+FileHandle]; FileHandle
0x14001d58f  test    rcx, rcx
0x14001d592  jz      short loc_14001D5A4
0x14001d594  call    cs:__imp_FltClose
0x14001d59b  nop     dword ptr [rax+rax+00h]
0x14001d5a0  mov     [rbp+70h+FileHandle], rbx
0x14001d5a4  mov     rcx, [rbp+70h+FileObject]; Object
0x14001d5ab  test    rcx, rcx
0x14001d5ae  jz      short loc_14001D5C3
0x14001d5b0  call    cs:__imp_ObfDereferenceObject
0x14001d5b7  nop     dword ptr [rax+rax+00h]
0x14001d5bc  mov     [rbp+70h+FileObject], rbx
0x14001d5c3  cmp     [rbp+70h+arg_0], bl
0x14001d5c9  jz      loc_14001D6A8
0x14001d5cf  mov     r11d, 1
0x14001d5d5  jmp     loc_14001D451
0x14001d5da  mov     rcx, [rbp+70h+FileObject]; FileObject
0x14001d5e1  mov     [rbp+70h+FileNameInformation], rax
0x14001d5e8  test    rcx, rcx
0x14001d5eb  jz      loc_14001D7FB
0x14001d5f1  lea     r9, [rbp+70h+FileNameInformation]; FileNameInformation
0x14001d5f8  mov     r8d, 103h; NameOptions
0x14001d5fe  mov     rdx, r13; Instance
0x14001d601  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14001d608  nop     dword ptr [rax+rax+00h]
0x14001d60d  mov     ebx, eax
0x14001d60f  xor     eax, eax
0x14001d611  test    ebx, ebx
0x14001d613  js      loc_14001D536
0x14001d619  mov     rcx, [rbp+70h+FileNameInformation]
0x14001d620  cmp     [rcx+8], ax
0x14001d624  jz      loc_14001D7F1
0x14001d62a  lea     rdx, Source; "\\"
0x14001d631  lea     rcx, [rbp+70h+Destination]; Destination
0x14001d635  call    cs:__imp_RtlAppendUnicodeToString
0x14001d63c  nop     dword ptr [rax+rax+00h]
0x14001d641  mov     ebx, eax
0x14001d643  test    eax, eax
0x14001d645  js      loc_14001D716
0x14001d64b  mov     rdx, [rbp+70h+FileNameInformation]
0x14001d652  lea     rcx, [rbp+70h+Destination]; Destination
0x14001d656  add     rdx, 8; Source
0x14001d65a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001d661  nop     dword ptr [rax+rax+00h]
0x14001d666  mov     ebx, eax
0x14001d668  test    eax, eax
0x14001d66a  js      loc_14001D716
0x14001d670  add     [rdi+4], si
0x14001d674  movzx   ecx, word ptr [rdi+4]
0x14001d678  mov     rax, [rbp+70h+FileNameInformation]
0x14001d67f  add     cx, [rax+8]
0x14001d683  mov     [rdi+4], cx
0x14001d687  mov     rcx, [rbp+70h+FileNameInformation]; FileNameInformation
0x14001d68e  call    cs:__imp_FltReleaseFileNameInformation
0x14001d695  nop     dword ptr [rax+rax+00h]
0x14001d69a  xor     ebx, ebx
0x14001d69c  mov     [rbp+70h+FileNameInformation], rbx
0x14001d6a3  jmp     loc_14001D58B
0x14001d6a8  mov     rax, [rbp+70h+arg_8]
0x14001d6af  mov     [rax], rdi
0x14001d6b2  mov     rdi, rbx
0x14001d6b5  test    r13, r13
0x14001d6b8  jz      short loc_14001D6C9
0x14001d6ba  mov     rcx, r13; FltObject
0x14001d6bd  call    cs:__imp_FltObjectDereference
0x14001d6c4  nop     dword ptr [rax+rax+00h]
0x14001d6c9  mov     rcx, [rbp+70h+FileHandle]; FileHandle
0x14001d6cd  test    rcx, rcx
0x14001d6d0  jnz     loc_14001D922
0x14001d6d6  mov     rcx, [rbp+70h+FileObject]; Object
0x14001d6dd  test    rcx, rcx
0x14001d6e0  jnz     loc_14001D933
0x14001d6e6  mov     rcx, [rbp+70h+FileNameInformation]; FileNameInformation
0x14001d6ed  test    rcx, rcx
0x14001d6f0  jnz     loc_14001D944
0x14001d6f6  test    rdi, rdi
0x14001d6f9  jnz     loc_14001D955
0x14001d6ff  mov     eax, ebx
0x14001d701  add     rsp, 138h
0x14001d708  pop     r15
0x14001d70a  pop     r14
0x14001d70c  pop     r13
0x14001d70e  pop     r12
0x14001d710  pop     rdi
0x14001d711  pop     rsi
0x14001d712  pop     rbx
0x14001d713  pop     rbp
0x14001d714  retn
0x14001d716  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d71d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d724  jz      short loc_14001D6B5
0x14001d726  mov     dword ptr [rsp+170h+AllocationSize], ebx
0x14001d72a  mov     r9d, 0Dh
0x14001d730  mov     dword ptr [rsp+170h+IoStatusBlock], 23Fh
0x14001d738  jmp     short loc_14001D760
0x14001d73a  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d741  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d748  jz      loc_14001D6B5
0x14001d74e  mov     dword ptr [rsp+170h+AllocationSize], ebx
0x14001d752  mov     r9d, 0Eh
0x14001d758  mov     dword ptr [rsp+170h+IoStatusBlock], 262h
0x14001d760  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d767  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001d76e  mov     [rsp+170h+ObjectAttributes], rax
0x14001d773  mov     r8d, r15d
0x14001d776  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14001d77d  mov     dl, sil
0x14001d780  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x14001d785  mov     rcx, [rcx+40h]
0x14001d789  call    WPP_RECORDER_SF_sDd
0x14001d78e  jmp     loc_14001D6B5
0x14001d793  mov     rdi, r13
0x14001d796  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d79d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d7a4  jz      loc_14001D6C9
0x14001d7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7b1  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001d7b8  mov     r9d, 0Ah
0x14001d7be  mov     dword ptr [rsp+170h+AllocationSize], ebx
0x14001d7c2  mov     dword ptr [rsp+170h+IoStatusBlock], 14Bh
0x14001d7ca  mov     [rsp+170h+ObjectAttributes], rax
0x14001d7cf  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14001d7d6  mov     rcx, [rcx+40h]
0x14001d7da  lea     edx, [r9-8]
0x14001d7de  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x14001d7e3  lea     r8d, [r9-4]
0x14001d7e7  call    WPP_RECORDER_SF_sDd
0x14001d7ec  jmp     loc_14001D6C9
0x14001d7f1  cmp     [rcx+18h], ax
0x14001d7f5  jbe     loc_14001D62A
  ... truncated ...
```
