# BfpGeneratePreCreateNormalizedName

- ea: `0x140013864`
- end: `0x140014170`
- name: `BfpGeneratePreCreateNormalizedName`
- size: `2316`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140001010`
- `0x140001348`
- `0x140002e0c`
- `0x140003304`
- `0x140013610`
- `0x140013864`
- `0x140014a70`
- `0x1400152f0`
- `0x1400172f0`
- `0x140017920`
- `0x14001d130`
- `0x140021550`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140013f53`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013fe8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013f53`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013fe8`
- `ntoskrnl!PsGetHostSilo` at `0x140013b84`
- `ntoskrnl!PsGetHostSilo` at `0x140013b84`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013ffe`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014104`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014128`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014104`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014128`
- `ntoskrnl!IoGetSilo` at `0x140013b76`
- `ntoskrnl!IoGetSilo` at `0x140013b76`
- `ntoskrnl!ExAllocatePool2` at `0x140013dd2`
- `ntoskrnl!ExAllocatePool2` at `0x140013dd2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400140e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400140e8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014017`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014017`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140013f75`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140013f75`
- `FLTMGR!FltQueryDirectoryFile` at `0x140013e6f`
- `FLTMGR!FltQueryDirectoryFile` at `0x140013e6f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013d83`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013d83`
- `FLTMGR!FltGetFileNameInformation` at `0x14001391d`
- `FLTMGR!FltGetFileNameInformation` at `0x14001391d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013d52`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001414d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013d52`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001414d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140013af5`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140013af5`
- `FLTMGR!FltCreateFileEx2` at `0x140013c1b`
- `FLTMGR!FltCreateFileEx2` at `0x140013c1b`
- `FLTMGR!FltClose` at `0x1400140d3`
- `FLTMGR!FltClose` at `0x1400140d3`
- `FLTMGR!FltObjectDereference` at `0x140013b2b`
- `FLTMGR!FltObjectDereference` at `0x140013b2b`
- `FLTMGR!FltGetVolumeName` at `0x140013b1b`
- `FLTMGR!FltGetVolumeName` at `0x140013b1b`

## pseudocode

```c
__int64 __fastcall BfpGeneratePreCreateNormalizedName(
        __int64 a1,
        __int64 a2,
        struct _FLT_CALLBACK_DATA *a3,
        int a4,
        __int64 a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  __int64 v9; // r13
  USHORT *Pool2; // r15
  int v11; // esi
  NTSTATUS MappingContexts; // ebx
  int v13; // r9d
  int v14; // r8d
  _QWORD *v15; // r14
  __int64 *v16; // r13
  __int64 v17; // r12
  __int64 *v18; // rax
  __int64 *v19; // rsi
  PFLT_INSTANCE *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 Silo; // rax
  NTSTATUS v24; // eax
  int v25; // r9d
  __int64 v26; // r9
  int v27; // edx
  PFLT_NAME_CONTROL v28; // rdi
  int ObjectAttributes; // [rsp+28h] [rbp-D8h]
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PFLT_VOLUME RetVolume; // [rsp+80h] [rbp-80h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v40[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+D8h] [rbp-28h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp-20h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v45; // [rsp+108h] [rbp+8h]
  struct _OBJECT_ATTRIBUTES v46; // [rsp+110h] [rbp+10h] BYREF
  struct _IO_STATUS_BLOCK v47; // [rsp+140h] [rbp+40h] BYREF
  int v48; // [rsp+1A0h] [rbp+A0h]
  __int64 v49; // [rsp+1A8h] [rbp+A8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+1B0h] [rbp+B0h] BYREF
  ULONG BufferSizeNeeded; // [rsp+1B8h] [rbp+B8h] BYREF

  v49 = a2;
  v48 = a1;
  LOWORD(v45) = 0;
  v40[1] = v40;
  FileHandle = 0;
  v40[0] = v40;
  FileObject = 0;
  v42 = 0;
  v9 = a2;
  v41 = 0;
  Pool2 = 0;
  RetVolume = 0;
  BufferSizeNeeded = 0;
  FileNameInformation = 0;
  *(_OWORD *)P = 0;
  FileName = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&v46, 0, 44);
  v47 = 0;
  DestinationString = 0;
  if ( !a3 )
    goto LABEL_68;
  v11 = *(_DWORD *)(a2 + 80);
  MappingContexts = FltGetFileNameInformation(a3, a4 & 0xFC00FF00 | 0x3000002, &FileNameInformation);
  if ( MappingContexts < 0 )
  {
LABEL_69:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    AllocationSize = MappingContexts;
    v13 = 16;
    IoStatusBlock = -127;
    goto LABEL_71;
  }
  if ( !FileNameInformation->Name.Length && FileNameInformation->Volume.Length )
  {
LABEL_68:
    MappingContexts = -1073741811;
    goto LABEL_69;
  }
  MappingContexts = BfGetMappingContexts(v9, a5, (_DWORD)a3, (unsigned int)&RetVolume, (__int64)&v41, (__int64)&v42);
  if ( MappingContexts < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    AllocationSize = MappingContexts;
    v13 = 17;
    IoStatusBlock = -119;
LABEL_8:
    v14 = 5;
LABEL_72:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      v14,
      v13,
      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
      IoStatusBlock,
      AllocationSize);
    goto LABEL_73;
  }
  MappingContexts = BfCombinedMappingLookup(
                      v42,
                      v41,
                      (_DWORD)RetVolume,
                      a1,
                      (__int64)FileNameInformation,
                      ObjectAttributes,
                      (v11 & 0x20000) == 0,
                      (__int64)v40,
                      (__int64)&BufferSizeNeeded);
  if ( MappingContexts == -1073741766 )
  {
    MappingContexts = BfpPassthroughNameQuery(a3, v9, a1, a4 & 0xFF00FF00 | 1, NameCtrl);
    if ( MappingContexts < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      AllocationSize = MappingContexts;
      v13 = 18;
      IoStatusBlock = -89;
LABEL_71:
      v14 = 9;
      goto LABEL_72;
    }
  }
  else
  {
    if ( MappingContexts < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      AllocationSize = MappingContexts;
      v13 = 19;
      IoStatusBlock = -82;
      goto LABEL_8;
    }
    v15 = (_QWORD *)v40[0];
    v16 = 0;
    LODWORD(v17) = 0;
LABEL_17:
    if ( v15 != v40 )
    {
      v17 = v15[4];
      v18 = (__int64 *)(v17 + 64);
      v19 = *(__int64 **)(v17 + 64);
      while ( 1 )
      {
        if ( v19 == v18 )
          goto LABEL_29;
        MappingContexts = BfRemapPath(
                            (_DWORD)FileNameInformation,
                            (int)v15 + 16,
                            *(_QWORD *)v19[2],
                            (int)v19 + 40,
                            (__int64)P);
        if ( MappingContexts < 0 )
          break;
        v20 = (PFLT_INSTANCE *)v19[2];
        RetVolume = 0;
        BufferSizeNeeded = 0;
        MappingContexts = FltGetVolumeFromInstance(*v20, &RetVolume);
        if ( MappingContexts < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_73;
          AllocationSize = MappingContexts;
          v13 = 21;
          IoStatusBlock = -29;
          goto LABEL_71;
        }
        v16 = v19;
        FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded);
        FltObjectDereference(RetVolume);
        BfRemoveFinalComponent(P, (unsigned __int16)BufferSizeNeeded, &FileName);
        memset(&DriverContext, 0, sizeof(DriverContext));
        DriverContext.Size = 40;
        v45 = 1;
        if ( (*(_DWORD *)(v17 + 8) & 4) != 0 )
          Silo = IoGetSilo(v49);
        else
          Silo = PsGetHostSilo(v22, v21);
        v45 = Silo;
        v46.RootDirectory = 0;
        v46.ObjectName = (PUNICODE_STRING)P;
        v46.Length = 48;
        v46.Attributes = 512;
        *(_OWORD *)&v46.SecurityDescriptor = 0;
        v24 = FltCreateFileEx2(
                g_BindFltState,
                *(PFLT_INSTANCE *)v19[2],
                &FileHandle,
                &FileObject,
                0x80u,
                &v46,
                &v47,
                0,
                0,
                7u,
                1u,
                0x20u,
                0,
                0,
                0,
                &DriverContext);
        MappingContexts = v24;
        if ( v24 != -1073741772 && v24 != -1073741766 )
        {
          if ( v24 >= 0 )
          {
LABEL_29:
            v15 = (_QWORD *)*v15;
            goto LABEL_17;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            FileAttributes = v24;
            v25 = 22;
            IoStatusBlocka = 30;
            goto LABEL_32;
          }
          goto LABEL_73;
        }
        BfFreeUnicodeString(P);
        v19 = (__int64 *)*v19;
        v18 = (__int64 *)(v17 + 64);
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      AllocationSize = MappingContexts;
      v13 = 20;
      IoStatusBlock = -50;
      goto LABEL_71;
    }
    if ( MappingContexts >= 0 )
    {
      FltReleaseFileNameInformation(FileNameInformation);
      FileNameInformation = 0;
      MappingContexts = FltGetFileNameInformationUnsafe(
                          FileObject,
                          *(PFLT_INSTANCE *)v16[2],
                          a4 & 0xFF00FF00 | 1,
                          &FileNameInformation);
      if ( MappingContexts < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_73;
        AllocationSize = MappingContexts;
        v13 = 24;
        IoStatusBlock = 62;
        goto LABEL_71;
      }
      Pool2 = (USHORT *)ExAllocatePool2(256, 1024, 1835943490, v26);
      if ( Pool2 )
      {
        MappingContexts = FltQueryDirectoryFile(
                            *(PFLT_INSTANCE *)v16[2],
                            FileObject,
                            Pool2,
                            0x400u,
                            FileNamesInformation,
                            1u,
                            &FileName,
                            1u,
                            0);
        if ( MappingContexts < 0 )
        {
          if ( MappingContexts != -1073741809 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_73;
            AllocationSize = MappingContexts;
            v13 = 26;
            IoStatusBlock = 114;
            goto LABEL_71;
          }
        }
        else
        {
          FileName.Buffer = Pool2 + 6;
          FileName.Length = Pool2[4];
          FileName.MaximumLength = FileName.Length;
        }
        MappingContexts = BfRemapPath(
                            (_DWORD)FileNameInformation,
                            (int)v16 + 40,
                            v48,
                            (int)v17 + 16,
                            (__int64)&DestinationString);
        if ( MappingContexts == -1073741275 )
        {
          MappingContexts = BfAllocateUnicodeString(FileNameInformation->Name.Length, &DestinationString);
          if ( MappingContexts < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_73;
            AllocationSize = MappingContexts;
            v13 = 27;
            IoStatusBlock = -107;
            goto LABEL_71;
          }
          RtlCopyUnicodeString(&DestinationString, &FileNameInformation->Name);
        }
        else if ( MappingContexts < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_73;
          AllocationSize = MappingContexts;
          v13 = 28;
          IoStatusBlock = -99;
          goto LABEL_71;
        }
        v28 = NameCtrl;
        MappingContexts = FltCheckAndGrowNameControl(NameCtrl, FileName.Length + DestinationString.Length + 2);
        if ( MappingContexts < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_73;
          AllocationSize = MappingContexts;
          v13 = 29;
          IoStatusBlock = -85;
          goto LABEL_71;
        }
        RtlCopyUnicodeString(&v28->Name, &DestinationString);
        MappingContexts = RtlAppendUnicodeToString(&v28->Name, L"\\");
        if ( MappingContexts >= 0 )
        {
          MappingContexts = RtlAppendUnicodeStringToString(&v28->Name, &FileName);
          if ( MappingContexts >= 0 )
          {
            MappingContexts = 0;
            goto LABEL_73;
          }
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          AllocationSize = MappingContexts;
          v13 = 30;
          IoStatusBlock = -69;
          goto LABEL_71;
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v27,
            9,
            25,
            (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
            75);
        }
        MappingContexts = -1073741670;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      FileAttributes = MappingContexts;
      v25 = 23;
      IoStatusBlocka = 43;
LABEL_32:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_sDZd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        9,
        v25,
        (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
        IoStatusBlocka,
        (__int64)P,
        FileAttributes);
    }
  }
LABEL_73:
  BfFreeMappingLookupList(v40);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x6D6E4642u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0x74734642u);
    DestinationString.Buffer = 0;
  }
  *(_DWORD *)&DestinationString.Length = 0;
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)MappingContexts;
}

```

## disassembly

```asm
0x140013864  mov     [rsp-8+arg_8], rdx
0x140013869  mov     [rsp-8+arg_0], rcx
0x14001386e  push    rbp
0x14001386f  push    rbx
0x140013870  push    rsi
0x140013871  push    rdi
0x140013872  push    r12
0x140013874  push    r13
0x140013876  push    r14
0x140013878  push    r15
0x14001387a  lea     rbp, [rsp-58h]
0x14001387f  sub     rsp, 158h
0x140013886  xorps   xmm0, xmm0
0x140013889  xor     eax, eax
0x14001388b  mov     word ptr [rbp+90h+var_88], ax
0x14001388f  xorps   xmm1, xmm1
0x140013892  lea     rax, [rbp+90h+var_D0]
0x140013896  mov     r12, rcx
0x140013899  xor     ecx, ecx
0x14001389b  mov     [rbp+90h+var_C8], rax
0x14001389f  mov     [rbp+90h+FileHandle], rcx
0x1400138a3  lea     rax, [rbp+90h+var_D0]
0x1400138a7  mov     [rbp+90h+var_D0], rax
0x1400138ab  mov     edi, r9d
0x1400138ae  mov     [rbp+90h+FileObject], rcx
0x1400138b2  mov     r14, r8
0x1400138b5  mov     [rbp+90h+var_B8], rcx
0x1400138b9  mov     r13, rdx
0x1400138bc  mov     [rbp+90h+var_C0], rcx
0x1400138c0  mov     r15d, ecx
0x1400138c3  mov     [rbp+90h+RetVolume], rcx
0x1400138c7  mov     [rbp+90h+BufferSizeNeeded], ecx
0x1400138cd  mov     [rbp+90h+FileNameInformation], rcx
0x1400138d4  movups  xmmword ptr [rbp+90h+var_80.ObjectName], xmm0
0x1400138d8  movups  xmmword ptr [rbp+90h+P], xmm0
0x1400138dc  movups  xmmword ptr [rbp+90h+FileName.Length], xmm1
0x1400138e0  movups  xmmword ptr [rbp+90h+var_A8.Size], xmm0
0x1400138e4  movups  xmmword ptr [rbp+90h+var_A8.DeviceObjectHint], xmm0
0x1400138e8  movups  xmmword ptr [rbp+90h+var_80.Length], xmm0
0x1400138ec  movups  xmmword ptr [rbp+90h+var_80+1Ch], xmm0
0x1400138f0  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x1400138f4  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm1
0x1400138f8  test    r8, r8
0x1400138fb  jz      loc_140014051
0x140013901  mov     esi, [rdx+50h]
0x140013904  lea     r8, [rbp+90h+FileNameInformation]; FileNameInformation
0x14001390b  mov     edx, r9d
0x14001390e  mov     rcx, r14; CallbackData
0x140013911  and     edx, 0FF00FF02h
0x140013917  or      edx, 3000002h; NameOptions
0x14001391d  call    cs:__imp_FltGetFileNameInformation
0x140013924  nop     dword ptr [rax+rax+00h]
0x140013929  xor     ecx, ecx
0x14001392b  mov     ebx, eax
0x14001392d  test    eax, eax
0x14001392f  js      loc_140014056
0x140013935  mov     rax, [rbp+90h+FileNameInformation]
0x14001393c  cmp     [rax+8], cx
0x140013940  jnz     short loc_14001394C
0x140013942  cmp     [rax+18h], cx
0x140013946  ja      loc_140014051
0x14001394c  mov     rdx, [rbp+90h+arg_20]
0x140013953  lea     rax, [rbp+90h+var_B8]
0x140013957  mov     [rsp+190h+ObjectAttributes], rax
0x14001395c  lea     r9, [rbp+90h+RetVolume]
0x140013960  lea     rax, [rbp+90h+var_C0]
0x140013964  mov     r8, r14
0x140013967  mov     rcx, r13
0x14001396a  mov     qword ptr [rsp+190h+DesiredAccess], rax
0x14001396f  call    BfGetMappingContexts
0x140013974  mov     ebx, eax
0x140013976  test    eax, eax
0x140013978  jns     short loc_1400139AB
0x14001397a  lea     rax, WPP_RECORDER_INITIALIZED
0x140013981  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013988  jz      loc_1400140A8
0x14001398e  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013992  mov     r9d, 11h
0x140013998  mov     dword ptr [rsp+190h+IoStatusBlock], 189h
0x1400139a0  mov     r8d, 5
0x1400139a6  jmp     loc_14001407E
0x1400139ab  mov     r8, [rbp+90h+RetVolume]
0x1400139af  lea     rax, [rbp+90h+BufferSizeNeeded]
0x1400139b6  mov     rdx, [rbp+90h+var_C0]
0x1400139ba  mov     r9, r12
0x1400139bd  mov     rcx, [rbp+90h+var_B8]
0x1400139c1  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1400139c6  lea     rax, [rbp+90h+var_D0]
0x1400139ca  mov     [rsp+190h+AllocationSize], rax
0x1400139cf  mov     rax, [rbp+90h+FileNameInformation]
0x1400139d6  shr     esi, 11h
0x1400139d9  not     sil
0x1400139dc  and     sil, 1
0x1400139e0  mov     byte ptr [rsp+190h+IoStatusBlock], sil
0x1400139e5  mov     qword ptr [rsp+190h+DesiredAccess], rax
0x1400139ea  call    BfCombinedMappingLookup
0x1400139ef  mov     ebx, eax
0x1400139f1  cmp     eax, 0C000003Ah
0x1400139f6  jnz     short loc_140013A53
0x1400139f8  mov     rax, [rbp+90h+NameCtrl]
0x1400139ff  and     edi, 0FF00FF01h
0x140013a05  or      edi, 1
0x140013a08  mov     qword ptr [rsp+190h+DesiredAccess], rax
0x140013a0d  mov     r9d, edi
0x140013a10  mov     r8, r12
0x140013a13  mov     rdx, r13
0x140013a16  mov     rcx, r14
0x140013a19  call    BfpPassthroughNameQuery
0x140013a1e  mov     ebx, eax
0x140013a20  test    eax, eax
0x140013a22  jns     loc_1400140A8
0x140013a28  lea     rax, WPP_RECORDER_INITIALIZED
0x140013a2f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013a36  jz      loc_1400140A8
0x140013a3c  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013a40  mov     r9d, 12h
0x140013a46  mov     dword ptr [rsp+190h+IoStatusBlock], 1A7h
0x140013a4e  jmp     loc_140014078
0x140013a53  test    ebx, ebx
0x140013a55  jns     short loc_140013A82
0x140013a57  lea     rax, WPP_RECORDER_INITIALIZED
0x140013a5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013a65  jz      loc_1400140A8
0x140013a6b  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013a6f  mov     r9d, 13h
0x140013a75  mov     dword ptr [rsp+190h+IoStatusBlock], 1AEh
0x140013a7d  jmp     loc_1400139A0
0x140013a82  mov     r14, [rbp+90h+var_D0]
0x140013a86  xor     r13d, r13d
0x140013a89  xor     r12d, r12d
0x140013a8c  lea     rax, [rbp+90h+var_D0]
0x140013a90  cmp     r14, rax
0x140013a93  jz      loc_140013D13
0x140013a99  mov     r12, [r14+20h]
0x140013a9d  lea     rax, [r12+40h]
0x140013aa2  mov     rsi, [rax]
0x140013aa5  lea     rcx, [r14+10h]
0x140013aa9  cmp     rsi, rax
0x140013aac  jz      loc_140013C51
0x140013ab2  mov     r8, [rsi+10h]
0x140013ab6  lea     rax, [rbp+90h+P]
0x140013aba  mov     rdx, rcx
0x140013abd  mov     qword ptr [rsp+190h+DesiredAccess], rax
0x140013ac2  mov     rcx, [rbp+90h+FileNameInformation]
0x140013ac9  lea     r9, [rsi+28h]
0x140013acd  mov     r8, [r8]
0x140013ad0  call    BfRemapPath
0x140013ad5  mov     ebx, eax
0x140013ad7  test    eax, eax
0x140013ad9  js      loc_140013CE8
0x140013adf  mov     rcx, [rsi+10h]
0x140013ae3  lea     rdx, [rbp+90h+RetVolume]; RetVolume
0x140013ae7  mov     [rbp+90h+RetVolume], r15
0x140013aeb  mov     [rbp+90h+BufferSizeNeeded], r15d
0x140013af2  mov     rcx, [rcx]; Instance
0x140013af5  call    cs:__imp_FltGetVolumeFromInstance
0x140013afc  nop     dword ptr [rax+rax+00h]
0x140013b01  mov     ebx, eax
0x140013b03  test    eax, eax
0x140013b05  js      loc_140013CBD
0x140013b0b  mov     rcx, [rbp+90h+RetVolume]; Volume
0x140013b0f  lea     r8, [rbp+90h+BufferSizeNeeded]; BufferSizeNeeded
0x140013b16  xor     edx, edx; VolumeName
0x140013b18  mov     r13, rsi
0x140013b1b  call    cs:__imp_FltGetVolumeName
0x140013b22  nop     dword ptr [rax+rax+00h]
0x140013b27  mov     rcx, [rbp+90h+RetVolume]; FltObject
0x140013b2b  call    cs:__imp_FltObjectDereference
0x140013b32  nop     dword ptr [rax+rax+00h]
0x140013b37  movzx   edx, word ptr [rbp+90h+BufferSizeNeeded]
0x140013b3e  lea     r8, [rbp+90h+FileName]
0x140013b42  lea     rcx, [rbp+90h+P]
0x140013b46  call    BfRemoveFinalComponent
0x140013b4b  mov     eax, 28h ; '('
0x140013b50  xorps   xmm0, xmm0
0x140013b53  movups  xmmword ptr [rbp+90h+var_A8.Size], xmm0
0x140013b57  mov     [rbp+90h+var_A8.Size], ax
0x140013b5b  movups  xmmword ptr [rbp+90h+var_A8.DeviceObjectHint], xmm0
0x140013b5f  lea     ebx, [rax-27h]
0x140013b62  mov     [rbp+90h+var_88], rbx
0x140013b66  mov     eax, [r12+8]
0x140013b6b  test    al, 4
0x140013b6d  jz      short loc_140013B84
0x140013b6f  mov     rcx, [rbp+90h+arg_8]
0x140013b76  call    cs:__imp_IoGetSilo
0x140013b7d  nop     dword ptr [rax+rax+00h]
0x140013b82  jmp     short loc_140013B90
0x140013b84  call    cs:__imp_PsGetHostSilo
0x140013b8b  nop     dword ptr [rax+rax+00h]
0x140013b90  xor     ecx, ecx
0x140013b92  mov     [rbp+90h+var_88], rax
0x140013b96  mov     [rbp+90h+var_80.RootDirectory], rcx
0x140013b9a  lea     rax, [rbp+90h+P]
0x140013b9e  mov     [rbp+90h+var_80.ObjectName], rax
0x140013ba2  lea     r9, [rbp+90h+FileObject]; FileObject
0x140013ba6  mov     [rbp+90h+var_80.Length], 30h ; '0'
0x140013bad  lea     rax, [rbp+90h+var_A8]
0x140013bb1  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140013bb6  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x140013bba  mov     [rsp+190h+Flags], ecx; Flags
0x140013bbe  lea     rax, [rbp+90h+var_50]
0x140013bc2  mov     [rsp+190h+EaLength], ecx; EaLength
0x140013bc6  xorps   xmm0, xmm0
0x140013bc9  mov     [rsp+190h+EaBuffer], rcx; EaBuffer
0x140013bce  mov     [rsp+190h+CreateOptions], 20h ; ' '; CreateOptions
0x140013bd6  mov     [rsp+190h+CreateDisposition], ebx; CreateDisposition
0x140013bda  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140013be2  mov     [rsp+190h+FileAttributes], ecx; FileAttributes
0x140013be6  mov     [rsp+190h+AllocationSize], rcx; AllocationSize
0x140013beb  mov     rcx, cs:g_BindFltState; Filter
0x140013bf2  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140013bf7  lea     rax, [rbp+90h+var_80]
0x140013bfb  mov     [rbp+90h+var_80.Attributes], 200h
0x140013c02  movdqu  xmmword ptr [rbp+90h+var_80.SecurityDescriptor], xmm0
0x140013c07  mov     rdx, [rsi+10h]
0x140013c0b  mov     [rsp+190h+ObjectAttributes], rax; ObjectAttributes
0x140013c10  mov     [rsp+190h+DesiredAccess], 80h; DesiredAccess
0x140013c18  mov     rdx, [rdx]; Instance
0x140013c1b  call    cs:__imp_FltCreateFileEx2
0x140013c22  nop     dword ptr [rax+rax+00h]
0x140013c27  mov     ebx, eax
0x140013c29  cmp     eax, 0C0000034h
0x140013c2e  jz      short loc_140013C37
0x140013c30  cmp     eax, 0C000003Ah
0x140013c35  jnz     short loc_140013C4D
0x140013c37  lea     rcx, [rbp+90h+P]
0x140013c3b  call    BfFreeUnicodeString
0x140013c40  mov     rsi, [rsi]
0x140013c43  lea     rax, [r12+40h]
0x140013c48  jmp     loc_140013AA5
0x140013c4d  test    ebx, ebx
0x140013c4f  js      short loc_140013C59
0x140013c51  mov     r14, [r14]
0x140013c54  jmp     loc_140013A8C
0x140013c59  lea     rax, WPP_RECORDER_INITIALIZED
0x140013c60  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013c67  jz      loc_1400140A8
0x140013c6d  mov     [rsp+190h+FileAttributes], ebx
0x140013c71  lea     rax, [rbp+90h+P]
0x140013c75  mov     [rsp+190h+AllocationSize], rax
0x140013c7a  mov     r9d, 16h
0x140013c80  mov     dword ptr [rsp+190h+IoStatusBlock], 21Eh
0x140013c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c8f  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140013c96  mov     [rsp+190h+ObjectAttributes], rax
0x140013c9b  mov     r8d, 9
0x140013ca1  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140013ca8  mov     dl, 2
0x140013caa  mov     qword ptr [rsp+190h+DesiredAccess], rax
0x140013caf  mov     rcx, [rcx+40h]
0x140013cb3  call    WPP_RECORDER_SF_sDZd
0x140013cb8  jmp     loc_1400140A8
0x140013cbd  lea     rax, WPP_RECORDER_INITIALIZED
0x140013cc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013ccb  jz      loc_1400140A8
0x140013cd1  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013cd5  mov     r9d, 15h
0x140013cdb  mov     dword ptr [rsp+190h+IoStatusBlock], 1E3h
0x140013ce3  jmp     loc_140014078
0x140013ce8  lea     rax, WPP_RECORDER_INITIALIZED
0x140013cef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013cf6  jz      loc_1400140A8
0x140013cfc  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013d00  mov     r9d, 14h
0x140013d06  mov     dword ptr [rsp+190h+IoStatusBlock], 1CEh
0x140013d0e  jmp     loc_140014078
0x140013d13  test    ebx, ebx
0x140013d15  jns     short loc_140013D4B
0x140013d17  lea     rax, WPP_RECORDER_INITIALIZED
0x140013d1e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013d25  jz      loc_1400140A8
0x140013d2b  mov     [rsp+190h+FileAttributes], ebx
0x140013d2f  lea     rax, [rbp+90h+P]
0x140013d33  mov     [rsp+190h+AllocationSize], rax
0x140013d38  mov     r9d, 17h
0x140013d3e  mov     dword ptr [rsp+190h+IoStatusBlock], 22Bh
0x140013d46  jmp     loc_140013C88
0x140013d4b  mov     rcx, [rbp+90h+FileNameInformation]; FileNameInformation
0x140013d52  call    cs:__imp_FltReleaseFileNameInformation
0x140013d59  nop     dword ptr [rax+rax+00h]
0x140013d5e  mov     rcx, [rbp+90h+FileObject]; FileObject
0x140013d62  lea     r9, [rbp+90h+FileNameInformation]; FileNameInformation
0x140013d69  mov     [rbp+90h+FileNameInformation], r15
0x140013d70  and     edi, 0FF00FF01h
0x140013d76  mov     rdx, [r13+10h]
0x140013d7a  or      edi, 1
0x140013d7d  mov     r8d, edi; NameOptions
0x140013d80  mov     rdx, [rdx]; Instance
0x140013d83  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140013d8a  nop     dword ptr [rax+rax+00h]
0x140013d8f  mov     ebx, eax
0x140013d91  test    eax, eax
0x140013d93  jns     short loc_140013DC0
0x140013d95  lea     rax, WPP_RECORDER_INITIALIZED
0x140013d9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013da3  jz      loc_1400140A8
0x140013da9  mov     dword ptr [rsp+190h+AllocationSize], ebx
0x140013dad  mov     r9d, 18h
0x140013db3  mov     dword ptr [rsp+190h+IoStatusBlock], 23Eh
0x140013dbb  jmp     loc_140014078
  ... truncated ...
```
