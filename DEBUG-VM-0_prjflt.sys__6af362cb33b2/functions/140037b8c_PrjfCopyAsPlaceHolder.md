# PrjfCopyAsPlaceHolder

- ea: `0x140037b8c`
- end: `0x140038756`
- name: `PrjfCopyAsPlaceHolder`
- size: `3018`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140035238`
- `0x1400368c4`

## callees

- `0x14000b1d0`
- `0x14000ba20`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x140037b8c`
- `0x1400389ec`

## import_xrefs

- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140038727`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x140038727`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140037f4d`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140037f4d`
- `ntoskrnl!ObfDereferenceObject` at `0x140038708`
- `ntoskrnl!ObfDereferenceObject` at `0x140038708`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140038546`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140038546`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140038436`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140038436`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400386de`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400386de`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003829d`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003829d`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140038100`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140038100`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140038055`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140038055`
- `FLTMGR!FltCreateFileEx2` at `0x14003836a`
- `FLTMGR!FltCreateFileEx2` at `0x14003836a`
- `FLTMGR!FltClose` at `0x1400386f3`
- `FLTMGR!FltClose` at `0x1400386f3`

## pseudocode

```c
__int64 __fastcall PrjfCopyAsPlaceHolder(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _FLT_INSTANCE *a4,
        __int64 a5,
        int a6,
        char a7,
        unsigned int a8)
{
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rax
  NTSTATUS Parameter; // ebx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rcx
  ULONG v18; // esi
  int v19; // eax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  unsigned __int16 v22; // cx
  NTSTATUS v23; // eax
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edi
  int v28; // edx
  PECP_LIST v29; // rdx
  int LookasideList; // [rsp+28h] [rbp-D8h]
  __int16 EcpContext; // [rsp+30h] [rbp-D0h]
  char ShareAccess; // [rsp+48h] [rbp-B8h]
  char CreateDisposition; // [rsp+50h] [rbp-B0h]
  PVOID v35; // [rsp+80h] [rbp-80h] BYREF
  ULONG EaLength; // [rsp+88h] [rbp-78h]
  ULONG FileAttributes; // [rsp+8Ch] [rbp-74h]
  struct _UNICODE_STRING *v38; // [rsp+90h] [rbp-70h]
  PECP_LIST EcpList; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-58h] BYREF
  ULONG CreateOptions; // [rsp+B0h] [rbp-50h]
  ULONG EcpContextSize; // [rsp+B4h] [rbp-4Ch] BYREF
  void *v44; // [rsp+B8h] [rbp-48h] BYREF
  PVOID EaBuffer; // [rsp+C0h] [rbp-40h]
  PFLT_INSTANCE Instance; // [rsp+C8h] [rbp-38h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  __int128 v51; // [rsp+138h] [rbp+38h] BYREF
  __int128 v52; // [rsp+148h] [rbp+48h]

  Instance = a4;
  v38 = (struct _UNICODE_STRING *)a3;
  v44 = 0;
  v9 = a2;
  EcpList = 0;
  v35 = 0;
  LOWORD(v48) = 0;
  FileHandle = 0;
  FileObject = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v51 = 0;
  v52 = 0;
  if ( !a6 || !a5 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        517,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        63,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        151);
    }
    goto LABEL_94;
  }
  if ( a6 != *(unsigned __int16 *)(a5 + 4) + 8 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        517,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        64,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        158);
    }
LABEL_94:
    Parameter = -1073741811;
    goto LABEL_95;
  }
  if ( !a1 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = xmmword_14001A3D0 & 0x20;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        517,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        65,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        165);
    }
    goto LABEL_94;
  }
  v10 = *(unsigned int *)(a1 + 56);
  a3 = 336;
  EaLength = v10;
  if ( (_DWORD)v10 )
  {
    v11 = *(unsigned int *)(a1 + 60);
    if ( (unsigned int)v11 < 0x150 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          517,
          v10,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          66,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          174);
      }
      goto LABEL_94;
    }
    if ( (int)v11 + (int)v10 < (unsigned int)v11 )
    {
      Parameter = -1073741675;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)Parameter;
      CreateDisposition = -107;
      ShareAccess = -70;
      EcpContext = 67;
      goto LABEL_25;
    }
    if ( a8 < (int)v11 + (int)v10 )
    {
      Parameter = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)Parameter;
      CreateDisposition = 13;
      ShareAccess = -63;
      EcpContext = 68;
LABEL_25:
      v13 = 526;
      LookasideList = 14;
LABEL_26:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        v13,
        v10,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        LookasideList,
        EcpContext,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        ShareAccess,
        CreateDisposition);
      goto LABEL_95;
    }
    EaBuffer = (PVOID)(a1 + v11);
  }
  else
  {
    EaBuffer = 0;
    EaLength = 0;
  }
  v14 = *(_DWORD *)(a1 + 64);
  if ( v14 )
  {
    v15 = *(unsigned int *)(a1 + 68);
    if ( (unsigned int)v15 < 0x150 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          517,
          v10,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          69,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          207);
      }
      goto LABEL_94;
    }
    v16 = v15 + v14;
    if ( v16 < (unsigned int)v15 )
    {
      Parameter = -1073741675;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)Parameter;
      CreateDisposition = -107;
      ShareAccess = -37;
      EcpContext = 70;
      goto LABEL_25;
    }
    if ( a8 < v16 )
    {
      Parameter = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)Parameter;
      CreateDisposition = 13;
      ShareAccess = -30;
      EcpContext = 71;
      goto LABEL_25;
    }
    v17 = v9 + v15;
    LOBYTE(v9) = 1;
    LOBYTE(v10) = 1;
    Parameter = SeCaptureSecurityDescriptor(v17, v10, 1, v9, &v44);
    if ( Parameter < 0 )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_95;
      CreateDisposition = Parameter;
      ShareAccess = -12;
      EcpContext = 72;
      goto LABEL_25;
    }
  }
  if ( *(_DWORD *)(a1 + 72) )
  {
    Parameter = -1073741637;
    goto LABEL_95;
  }
  v18 = *(_DWORD *)(a1 + 48);
  v19 = -(*(_BYTE *)a1 != 0);
  FileAttributes = v18;
  CreateOptions = 2097192 - v19;
  v20 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  Parameter = v20;
  if ( v20 < 0 )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
    if ( (xmmword_14001A3D0 & 0x20) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_95;
    CreateDisposition = v20;
    ShareAccess = 56;
    EcpContext = 76;
    goto LABEL_51;
  }
  v21 = FltAllocateExtraCreateParameterFromLookasideList(
          Globals,
          &GUID_ECP_ATOMIC_CREATE,
          0x58u,
          0,
          0,
          qword_14001A5C0,
          &v35);
  Parameter = v21;
  if ( v21 >= 0 )
  {
    memset(v35, 0, 0x58u);
    *(_WORD *)v35 = 88;
    *((_WORD *)v35 + 1) = 2;
    *((_WORD *)v35 + 2) = 0;
    v22 = *(_WORD *)(a5 + 4);
    if ( (unsigned __int16)(v22 + 8) < v22 )
    {
      *((_WORD *)v35 + 3) = -1;
      Parameter = -1073741675;
    }
    else
    {
      *((_WORD *)v35 + 3) = v22 + 8;
      *((_QWORD *)v35 + 1) = a5;
      if ( !*(_BYTE *)a1 )
      {
        *((_WORD *)v35 + 1) |= 1u;
        *((_QWORD *)v35 + 2) = *(_QWORD *)(a1 + 8);
        *((_WORD *)v35 + 1) |= 4u;
        *((_QWORD *)v35 + 3) = *(_QWORD *)(a1 + 8);
        *((_WORD *)v35 + 1) |= 8u;
      }
      if ( !byte_14001ABCC )
      {
        if ( a7 )
        {
          *((_WORD *)v35 + 1) |= 0x400u;
          *((_WORD *)v35 + 1) |= 0x200u;
        }
        *((_QWORD *)&v52 + 1) = *(_QWORD *)(a1 + 40);
        v51 = *(_OWORD *)(a1 + 16);
        *(_QWORD *)&v52 = *(_QWORD *)(a1 + 32);
        *((_QWORD *)v35 + 4) = &v51;
        *((_WORD *)v35 + 1) |= 0x10u;
        *((_WORD *)v35 + 1) |= 0x20u;
        FileAttributes = v18 | 0x400000;
        *((_DWORD *)v35 + 10) = v18 | 0x400000;
      }
      while ( 1 )
      {
        Parameter = FltInsertExtraCreateParameter(Globals, EcpList, v35);
        if ( Parameter < 0 )
          break;
        *(&DriverContext.Size + 2) = 0;
        *(&DriverContext.Size + 3) = 0;
        *(_DWORD *)&DriverContext.Size = 40;
        DriverContext.ExtraCreateParameter = EcpList;
        ObjectAttributes.ObjectName = v38;
        ObjectAttributes.SecurityDescriptor = v44;
        v48 = 1;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.SecurityQualityOfService = 0;
        *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        v23 = FltCreateFileEx2(
                Globals,
                Instance,
                &FileHandle,
                &FileObject,
                0x40100u,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes,
                7u,
                2u,
                CreateOptions,
                EaBuffer,
                EaLength,
                1u,
                &DriverContext);
        Parameter = v23;
        if ( v23 >= 0 )
        {
          if ( FltIsEcpAcknowledged(Globals, v35) )
          {
            v27 = (int)Instance;
            Parameter = PrjfCopyFileMetaData(a1, (_DWORD)FileHandle, (_DWORD)FileObject, (_DWORD)Instance, 2);
            if ( Parameter >= 0 && byte_14001ABCC )
              Parameter = PrjfCopyFileMetaData(a1, (_DWORD)FileHandle, (_DWORD)FileObject, v27, 104);
          }
          else
          {
            Parameter = -1073741637;
            if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v26) = BYTE1(xmmword_14001A3D0) & 4;
              LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                522,
                v26,
                a3,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                10,
                82,
                (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                61,
                187,
                (__int64)v38);
            }
          }
          goto LABEL_95;
        }
        if ( v23 == -1073741771 )
        {
          Parameter = 0;
          goto LABEL_95;
        }
        if ( v23 != -1073741637 || byte_14001ABCC )
        {
          if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = BYTE1(xmmword_14001A3D0) & 4;
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              522,
              v24,
              a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              10,
              81,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              36,
              v23,
              (__int64)v38);
          }
          goto LABEL_95;
        }
        if ( (BYTE1(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = BYTE1(xmmword_14001A3E0) & 4;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            1034,
            v24,
            a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            4,
            10,
            79,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            235,
            187,
            (__int64)v38);
        }
        EcpContextSize = 0;
        byte_14001ABCC = 1;
        Parameter = FltRemoveExtraCreateParameter(Globals, EcpList, &GUID_ECP_ATOMIC_CREATE, &v35, &EcpContextSize);
        if ( Parameter < 0 )
        {
          if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 4;
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              522,
              v25,
              a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              10,
              80,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              9,
              Parameter,
              (__int64)v38);
          }
          goto LABEL_95;
        }
        *((_WORD *)v35 + 1) &= ~0x10u;
        *((_WORD *)v35 + 1) &= ~0x400u;
        *((_WORD *)v35 + 1) &= ~0x200u;
        *((_WORD *)v35 + 1) &= ~0x20u;
      }
      MicrosoftTelemetryAssertTriggeredNoArgsKM(0);
      if ( SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = BYTE1(xmmword_14001A3D0) & 0x80;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          527,
          v28,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          15,
          78,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          169,
          Parameter);
      }
    }
    goto LABEL_95;
  }
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  LOBYTE(v10) = xmmword_14001A3D0 & 0x20;
  if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CreateDisposition = v21;
    ShareAccess = 70;
    EcpContext = 77;
LABEL_51:
    v13 = 517;
    LookasideList = 5;
    goto LABEL_26;
  }
LABEL_95:
  v29 = EcpList;
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v44 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(v29) = 1;
    SeReleaseSecurityDescriptor(v44, v29, a3);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x140037b8c  push    rbp
0x140037b8e  push    rbx
0x140037b8f  push    rsi
0x140037b90  push    rdi
0x140037b91  push    r12
0x140037b93  push    r13
0x140037b95  push    r14
0x140037b97  push    r15
0x140037b99  lea     rbp, [rsp-68h]
0x140037b9e  sub     rsp, 168h
0x140037ba5  mov     rax, cs:__security_cookie
0x140037bac  xor     rax, rsp
0x140037baf  mov     [rbp+0A0h+var_48], rax
0x140037bb3  xorps   xmm0, xmm0
0x140037bb6  mov     [rbp+0A0h+Instance], r9
0x140037bba  xor     eax, eax
0x140037bbc  mov     [rbp+0A0h+var_110], r8
0x140037bc0  mov     r12, rcx
0x140037bc3  mov     [rbp+0A0h+var_E8], 0
0x140037bcb  mov     ecx, [rbp+0A0h+arg_28]
0x140037bd1  mov     r9, rdx
0x140037bd4  mov     [rbp+0A0h+EcpList], 0
0x140037bdc  mov     [rbp+0A0h+var_120], 0
0x140037be4  lea     r10d, [rax+1]
0x140037be8  mov     word ptr [rbp+0A0h+var_B0], ax
0x140037bec  mov     [rbp+0A0h+FileHandle], rax
0x140037bf0  mov     [rbp+0A0h+FileObject], rax
0x140037bf4  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x140037bf8  movups  xmmword ptr [rbp+0A0h+var_D0.Size], xmm0
0x140037bfc  movups  xmmword ptr [rbp+0A0h+var_D0.DeviceObjectHint], xmm0
0x140037c00  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x140037c04  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x140037c08  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140037c0c  movups  [rbp+0A0h+var_68], xmm0
0x140037c10  movups  [rbp+0A0h+var_58], xmm0
0x140037c14  test    ecx, ecx
0x140037c16  jz      loc_14003865E
0x140037c1c  mov     rdi, [rbp+0A0h+arg_20]
0x140037c23  test    rdi, rdi
0x140037c26  jz      loc_14003865E
0x140037c2c  movzx   eax, word ptr [rdi+4]
0x140037c30  lea     r13d, [r10+7]
0x140037c34  add     eax, r13d
0x140037c37  cmp     ecx, eax
0x140037c39  jz      short loc_140037C8D
0x140037c3b  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140037c41  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037c48  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037c4f  setnz   r8b
0x140037c53  and     dl, 20h
0x140037c56  jnz     short loc_140037C61
0x140037c58  test    r8b, r8b
0x140037c5b  jz      loc_1400386C9
0x140037c61  mov     dword ptr [rsp+1A0h+ShareAccess], 0C9Eh
0x140037c69  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037c70  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037c75  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037c7c  mov     [rsp+1A0h+AllocationSize], r14
0x140037c81  mov     word ptr [rsp+1A0h+EcpContext], 40h ; '@'
0x140037c88  jmp     loc_1400386A7
0x140037c8d  test    r12, r12
0x140037c90  jnz     short loc_140037CE4
0x140037c92  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140037c98  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037c9f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037ca6  setnz   r8b
0x140037caa  and     dl, 20h
0x140037cad  jnz     short loc_140037CB8
0x140037caf  test    r8b, r8b
0x140037cb2  jz      loc_1400386C9
0x140037cb8  mov     dword ptr [rsp+1A0h+ShareAccess], 0CA5h
0x140037cc0  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037cc7  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037ccc  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037cd3  mov     [rsp+1A0h+AllocationSize], r14
0x140037cd8  mov     word ptr [rsp+1A0h+EcpContext], 41h ; 'A'
0x140037cdf  jmp     loc_1400386A7
0x140037ce4  mov     edx, [r12+38h]
0x140037ce9  mov     r8d, 150h
0x140037cef  mov     [rbp+0A0h+var_118], edx
0x140037cf2  test    edx, edx
0x140037cf4  jz      loc_140037E4E
0x140037cfa  mov     eax, [r12+3Ch]
0x140037cff  cmp     eax, r8d
0x140037d02  jnb     short loc_140037D56
0x140037d04  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140037d0a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037d11  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037d18  setnz   r8b
0x140037d1c  and     dl, 20h
0x140037d1f  jnz     short loc_140037D2A
0x140037d21  test    r8b, r8b
0x140037d24  jz      loc_1400386C9
0x140037d2a  mov     dword ptr [rsp+1A0h+ShareAccess], 0CAEh
0x140037d32  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037d39  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037d3e  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037d45  mov     [rsp+1A0h+AllocationSize], r14
0x140037d4a  mov     word ptr [rsp+1A0h+EcpContext], 42h ; 'B'
0x140037d51  jmp     loc_1400386A7
0x140037d56  lea     ecx, [rax+rdx]
0x140037d59  cmp     ecx, eax
0x140037d5b  jb      short loc_140037DCD
0x140037d5d  cmp     [rbp+0A0h+arg_38], ecx
0x140037d63  jnb     short loc_140037DC1
0x140037d65  mov     ebx, 0C000000Dh
0x140037d6a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140037d70  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037d77  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037d7e  mov     eax, 40h ; '@'
0x140037d83  setnz   r8b
0x140037d87  and     dl, al
0x140037d89  jnz     short loc_140037D94
0x140037d8b  test    r8b, r8b
0x140037d8e  jz      loc_140038733
0x140037d94  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x140037d98  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037d9f  mov     dword ptr [rsp+1A0h+ShareAccess], 0CC1h
0x140037da7  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037dae  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037db3  mov     [rsp+1A0h+AllocationSize], r14
0x140037db8  mov     word ptr [rsp+1A0h+EcpContext], 44h ; 'D'
0x140037dbf  jmp     short loc_140037E27
0x140037dc1  add     rax, r12
0x140037dc4  mov     [rbp+0A0h+var_E0], rax
0x140037dc8  jmp     loc_140037E5D
0x140037dcd  mov     ebx, 0C0000095h
0x140037dd2  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140037dd8  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037ddf  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037de6  mov     eax, 40h ; '@'
0x140037deb  setnz   r8b
0x140037def  and     dl, al
0x140037df1  jnz     short loc_140037DFC
0x140037df3  test    r8b, r8b
0x140037df6  jz      loc_140038733
0x140037dfc  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x140037e00  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037e07  mov     dword ptr [rsp+1A0h+ShareAccess], 0CBAh
0x140037e0f  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037e16  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037e1b  mov     [rsp+1A0h+AllocationSize], r14
0x140037e20  mov     word ptr [rsp+1A0h+EcpContext], 43h ; 'C'
0x140037e27  mov     ecx, 20Eh
0x140037e2c  mov     dword ptr [rsp+1A0h+LookasideList], 0Eh
0x140037e34  mov     byte ptr [rsp+1A0h+CleanupCallback], 2
0x140037e39  mov     r9, cs:WPP_GLOBAL_Control
0x140037e40  mov     r9, [r9+40h]
0x140037e44  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140037e49  jmp     loc_1400386CE
0x140037e4e  mov     [rbp+0A0h+var_E0], 0
0x140037e56  mov     [rbp+0A0h+var_118], 0
0x140037e5d  mov     ecx, [r12+40h]
0x140037e62  test    ecx, ecx
0x140037e64  jz      loc_14003801C
0x140037e6a  mov     eax, [r12+44h]
0x140037e6f  cmp     eax, r8d
0x140037e72  jnb     short loc_140037EC6
0x140037e74  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140037e7a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037e81  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037e88  setnz   r8b
0x140037e8c  and     dl, 20h
0x140037e8f  jnz     short loc_140037E9A
0x140037e91  test    r8b, r8b
0x140037e94  jz      loc_1400386C9
0x140037e9a  mov     dword ptr [rsp+1A0h+ShareAccess], 0CCFh
0x140037ea2  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037ea9  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037eae  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037eb5  mov     [rsp+1A0h+AllocationSize], r14
0x140037eba  mov     word ptr [rsp+1A0h+EcpContext], 45h ; 'E'
0x140037ec1  jmp     loc_1400386A7
0x140037ec6  add     ecx, eax
0x140037ec8  cmp     ecx, eax
0x140037eca  jb      loc_140037FBD
0x140037ed0  cmp     [rbp+0A0h+arg_38], ecx
0x140037ed6  jnb     short loc_140037F37
0x140037ed8  mov     ebx, 0C000000Dh
0x140037edd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140037ee3  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037eea  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037ef1  mov     eax, 40h ; '@'
0x140037ef6  setnz   r8b
0x140037efa  and     dl, al
0x140037efc  jnz     short loc_140037F07
0x140037efe  test    r8b, r8b
0x140037f01  jz      loc_140038733
0x140037f07  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x140037f0b  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037f12  mov     dword ptr [rsp+1A0h+ShareAccess], 0CE2h
0x140037f1a  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037f21  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037f26  mov     [rsp+1A0h+AllocationSize], r14
0x140037f2b  mov     word ptr [rsp+1A0h+EcpContext], 47h ; 'G'
0x140037f32  jmp     loc_140037E27
0x140037f37  lea     rcx, [r9+rax]
0x140037f3b  mov     r8d, r10d
0x140037f3e  lea     rax, [rbp+0A0h+var_E8]
0x140037f42  mov     r9b, r10b
0x140037f45  mov     dl, r10b
0x140037f48  mov     [rsp+1A0h+CleanupCallback], rax
0x140037f4d  call    cs:__imp_SeCaptureSecurityDescriptor
0x140037f54  nop     dword ptr [rax+rax+00h]
0x140037f59  mov     ebx, eax
0x140037f5b  test    eax, eax
0x140037f5d  jns     loc_14003801C
0x140037f63  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140037f69  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037f70  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037f77  mov     eax, 40h ; '@'
0x140037f7c  setnz   r8b
0x140037f80  and     dl, al
0x140037f82  jnz     short loc_140037F8D
0x140037f84  test    r8b, r8b
0x140037f87  jz      loc_1400386CE
0x140037f8d  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x140037f91  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037f98  mov     dword ptr [rsp+1A0h+ShareAccess], 0CF4h
0x140037fa0  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037fa7  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x140037fac  mov     [rsp+1A0h+AllocationSize], r14
0x140037fb1  mov     word ptr [rsp+1A0h+EcpContext], 48h ; 'H'
0x140037fb8  jmp     loc_140037E27
0x140037fbd  mov     ebx, 0C0000095h
0x140037fc2  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140037fc8  lea     rdi, WPP_RECORDER_INITIALIZED
0x140037fcf  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037fd6  mov     eax, 40h ; '@'
0x140037fdb  setnz   r8b
0x140037fdf  and     dl, al
0x140037fe1  jnz     short loc_140037FEC
0x140037fe3  test    r8b, r8b
0x140037fe6  jz      loc_140038733
0x140037fec  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x140037ff0  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037ff7  mov     dword ptr [rsp+1A0h+ShareAccess], 0CDBh
0x140037fff  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038006  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x14003800b  mov     [rsp+1A0h+AllocationSize], r14
0x140038010  mov     word ptr [rsp+1A0h+EcpContext], 46h ; 'F'
0x140038017  jmp     loc_140037E27
0x14003801c  cmp     dword ptr [r12+48h], 0
0x140038022  jz      short loc_14003802E
0x140038024  mov     ebx, 0C00000BBh
0x140038029  jmp     loc_1400386CE
0x14003802e  mov     al, [r12]
0x140038032  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x140038036  mov     esi, [r12+30h]
0x14003803b  neg     al
0x14003803d  mov     rcx, cs:Globals; Filter
0x140038044  sbb     eax, eax
0x140038046  mov     [rbp+0A0h+var_114], esi
0x140038049  neg     eax
0x14003804b  xor     edx, edx; Flags
0x14003804d  add     eax, 200028h
0x140038052  mov     [rbp+0A0h+var_F0], eax
0x140038055  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14003805c  nop     dword ptr [rax+rax+00h]
0x140038061  mov     ebx, eax
0x140038063  test    eax, eax
0x140038065  jns     short loc_1400380CA
0x140038067  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003806d  lea     rdi, WPP_RECORDER_INITIALIZED
0x140038074  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003807b  setnz   r8b
0x14003807f  and     dl, 20h
0x140038082  jnz     short loc_14003808D
0x140038084  test    r8b, r8b
0x140038087  jz      loc_1400386CE
0x14003808d  mov     dword ptr [rsp+1A0h+CreateDisposition], eax
0x140038091  lea     rsi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038098  mov     dword ptr [rsp+1A0h+ShareAccess], 0D38h
0x1400380a0  lea     r14, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400380a7  mov     qword ptr [rsp+1A0h+FileAttributes], rsi
0x1400380ac  mov     [rsp+1A0h+AllocationSize], r14
0x1400380b1  mov     word ptr [rsp+1A0h+EcpContext], 4Ch ; 'L'
0x1400380b8  mov     ecx, 205h
0x1400380bd  mov     dword ptr [rsp+1A0h+LookasideList], 5
0x1400380c5  jmp     loc_140037E34
0x1400380ca  mov     rcx, cs:Globals; Filter
0x1400380d1  lea     rax, [rbp+0A0h+var_120]
0x1400380d5  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x1400380da  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x1400380e1  xor     r9d, r9d; Flags
0x1400380e4  lea     rax, qword_14001A5C0
0x1400380eb  mov     [rsp+1A0h+LookasideList], rax; LookasideList
0x1400380f0  mov     [rsp+1A0h+CleanupCallback], 0; CleanupCallback
0x1400380f9  lea     r14d, [r9+58h]
0x1400380fd  mov     r8d, r14d; SizeOfContext
0x140038100  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140038107  nop     dword ptr [rax+rax+00h]
0x14003810c  mov     ebx, eax
0x14003810e  test    eax, eax
0x140038110  jns     short loc_140038168
0x140038112  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140038118  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003811f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140038126  setnz   r8b
0x14003812a  and     dl, 20h
  ... truncated ...
```
