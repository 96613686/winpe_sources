# UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,ulong,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)

- ea: `0x140077774`
- end: `0x140077f0d`
- name: `?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@KAEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1945`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400605e4`
- `0x140077710`
- `0x140077f94`

## callees

- `0x14001ab44`
- `0x140056a50`
- `0x140056a88`
- `0x140056ac4`
- `0x140077774`
- `0x14007af90`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140077ed7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077ed7`
- `FLTMGR!FltQueryInformationByName` at `0x1400778a0`
- `FLTMGR!FltQueryInformationByName` at `0x140077b3f`
- `FLTMGR!FltQueryInformationByName` at `0x140077dcb`
- `FLTMGR!FltQueryInformationByName` at `0x1400778a0`
- `FLTMGR!FltQueryInformationByName` at `0x140077b3f`
- `FLTMGR!FltQueryInformationByName` at `0x140077dcb`
- `FLTMGR!FltPrepareToReuseEcp` at `0x140077ce3`
- `FLTMGR!FltPrepareToReuseEcp` at `0x140077ce3`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400778eb`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400778eb`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077a5d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077e35`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077a5d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077e35`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140077a0a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140077a0a`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140077975`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140077975`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077b7a`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077ba5`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077b7a`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077ba5`
- `FLTMGR!FltAttachVolume` at `0x140077bfb`
- `FLTMGR!FltAttachVolume` at `0x140077bfb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140077de1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140077de1`
- `FLTMGR!FltObjectDereference` at `0x140077c1f`
- `FLTMGR!FltObjectDereference` at `0x140077c72`
- `FLTMGR!FltObjectDereference` at `0x140077c90`
- `FLTMGR!FltObjectDereference` at `0x140077cb2`
- `FLTMGR!FltObjectDereference` at `0x140077df7`
- `FLTMGR!FltObjectDereference` at `0x140077c1f`
- `FLTMGR!FltObjectDereference` at `0x140077c72`
- `FLTMGR!FltObjectDereference` at `0x140077c90`
- `FLTMGR!FltObjectDereference` at `0x140077cb2`
- `FLTMGR!FltObjectDereference` at `0x140077df7`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140077e85`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140077e85`

## string_xrefs

- `0x140077bb5`: `API: FLT_CREATEFILE_TARGET_ECP not acknowledged`
- `0x140077e9d`: `ORIGIN: Bad symlink data`
- `0x140077e13`: `Cross-volume reparse failed for FltQueryInformationByName`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::StatItem(
        struct _UNICODE_STRING *a1,
        struct _FLT_INSTANCE *a2,
        ULONG a3,
        __int64 a4,
        char a5,
        void *a6,
        int a7,
        struct _TXN_PARAMETER_BLOCK *a8,
        PFLT_CALLBACK_DATA Data)
{
  __int64 v12; // rsi
  int v13; // r12d
  unsigned int v14; // ecx
  int InformationByName; // eax
  NTSTATUS Parameter; // ebx
  __int64 v17; // rsi
  const char *v18; // rax
  __int64 v19; // r8
  struct _ECP_LIST *v21; // r12
  PFLT_FILTER *v22; // rcx
  const char *v23; // rax
  __int64 v24; // r8
  int v25; // eax
  struct _FLT_FILTER *v26; // rcx
  _QWORD *v27; // rdi
  PFLT_INSTANCE v28; // rsi
  PVOID v29; // rax
  void *v30; // rcx
  _QWORD *v31; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v32; // rdi
  int v33; // eax
  struct _FLT_TAG_DATA_BUFFER *v34; // rdx
  const char *PoolTag; // [rsp+28h] [rbp-D8h]
  PVOID *EcpContext; // [rsp+30h] [rbp-D0h]
  PVOID v37; // [rsp+50h] [rbp-B0h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp-A8h] BYREF
  PVOID FltObject; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+78h] [rbp-88h]
  __int16 v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+82h] [rbp-7Eh]
  __int16 v44; // [rsp+86h] [rbp-7Ah]
  PECP_LIST v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  struct _TXN_PARAMETER_BLOCK *v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES v49; // [rsp+A8h] [rbp-58h] BYREF
  PVOID *p_FltObject; // [rsp+D8h] [rbp-28h]
  PFLT_INSTANCE RetInstance; // [rsp+E0h] [rbp-20h] BYREF
  char v52; // [rsp+E8h] [rbp-18h]
  _QWORD v53[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v54; // [rsp+100h] [rbp+0h]
  struct _IO_DRIVER_CREATE_CONTEXT v55; // [rsp+108h] [rbp+8h] BYREF
  __int64 v56; // [rsp+128h] [rbp+28h]
  struct _OBJECT_ATTRIBUTES v57[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v58; // [rsp+1A0h] [rbp+A0h]

  v12 = a4;
  memset(a6, 0, 0x48u);
  v13 = a5 & 4;
  memset(&v55.Size + 1, 0, 22);
  v56 = v12;
  v55.Size = 40;
  v55.TxnParameters = a8;
  *(_QWORD *)&v57[0].Length = 48;
  *(&v57[0].Attributes + 1) = 0;
  v57[0].RootDirectory = 0;
  v57[0].Attributes = a3;
  v57[0].ObjectName = a1;
  *(_OWORD *)&v57[0].SecurityDescriptor = 0;
  v41 = v13;
  *(_OWORD *)P = 0;
  if ( (a5 & 4) != 0 || (v14 = 0, v58 = 0, (a5 & 2) != 0) )
  {
    v14 = 8;
    v58 = 8;
  }
  if ( UnionFs::QueryInformationByName2 )
  {
    InformationByName = UnionFs::QueryInformationByName2(
                          *(struct _FLT_FILTER **)UnionFs::g_FilterState,
                          a2,
                          v57,
                          (struct _IO_STATUS_BLOCK *)P,
                          a6,
                          0x48u,
                          (enum _FILE_INFORMATION_CLASS)68,
                          v14,
                          &v55);
  }
  else
  {
    LODWORD(EcpContext) = 68;
    LODWORD(PoolTag) = 72;
    InformationByName = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, a2, v57, P, a6);
  }
  Parameter = InformationByName;
  if ( InformationByName != -1073740951 )
  {
    v17 = 0xBC002108A8LL;
    if ( InformationByName != -1073740952 )
      goto LABEL_52;
    v12 = a4;
  }
  EcpList = 0;
  Parameter = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( Parameter < 0 )
  {
    v18 = "API: Allocating ECP list";
    v19 = 0x4A8002108E5LL;
LABEL_12:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      a7,
      (struct UnionFs::StackEventTracer *)v19,
      (unsigned __int64)"UnionFs::Utils::StatItem",
      v18,
      (const char *)a1,
      (const struct _UNICODE_STRING *)EcpContext);
    return (unsigned int)Parameter;
  }
  v21 = EcpList;
  v37 = 0;
  Parameter = FltAllocateExtraCreateParameter(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                &GUID_ECP_FLT_CREATEFILE_TARGET,
                0x20u,
                0,
                0,
                0x63654655u,
                &v37);
  if ( Parameter < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      a7,
      (struct UnionFs::StackEventTracer *)0x4A9002108F6LL,
      (unsigned __int64)"UnionFs::Utils::StatItem",
      "API: Allocating targeting ECP",
      (const char *)a1,
      (const struct _UNICODE_STRING *)EcpContext);
LABEL_20:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v21);
    return (unsigned int)Parameter;
  }
  v53[0] = EcpList;
  v54 = 1;
  v53[1] = v37;
  *((_WORD *)v37 + 12) = 1;
  v22 = (PFLT_FILTER *)UnionFs::g_FilterState;
  *(_QWORD *)v37 = 0;
  *((_QWORD *)v37 + 1) = 0;
  *((_QWORD *)v37 + 2) = 0;
  Parameter = FltInsertExtraCreateParameter(*v22, EcpList, v37);
  if ( Parameter < 0 )
  {
    v23 = "API: Inserting ECP";
    v24 = 0x4AA00210922LL;
LABEL_18:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      a7,
      (struct UnionFs::StackEventTracer *)v24,
      (unsigned __int64)"UnionFs::Utils::StatItem",
      v23,
      PoolTag);
LABEL_19:
    wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v53);
    goto LABEL_20;
  }
  v48 = v12;
  v44 = 0;
  v46 = 0;
  v43 = 0;
  *(_QWORD *)&v49.Length = 48;
  v42 = 40;
  v47 = a8;
  v45 = EcpList;
  v49.Attributes = a3;
  memset(&v49.Attributes + 1, 0, 20);
  v49.RootDirectory = 0;
  v49.ObjectName = a1;
  if ( UnionFs::QueryInformationByName2 )
  {
    v25 = UnionFs::QueryInformationByName2(
            *(struct _FLT_FILTER **)UnionFs::g_FilterState,
            a2,
            &v49,
            (struct _IO_STATUS_BLOCK *)P,
            a6,
            0x48u,
            (enum _FILE_INFORMATION_CLASS)68,
            v58,
            &v55);
  }
  else
  {
    LODWORD(EcpContext) = 68;
    LODWORD(PoolTag) = 72;
    v25 = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, a2, &v49, P, a6);
  }
  Parameter = v25;
  if ( v25 == -1073740951 || (v17 = 0x4AB00210931LL, v25 == -1073740952) )
  {
    if ( !FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, v37) )
      MicrosoftTelemetryAssertTriggeredMsgKM("FltMgr DID NOT acknowledge cross-volume ECP!");
    if ( !FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, v37) )
    {
      v23 = "API: FLT_CREATEFILE_TARGET_ECP not acknowledged";
      v24 = 0x52100210958LL;
      goto LABEL_18;
    }
    FltObject = 0;
    p_FltObject = &FltObject;
    RetInstance = 0;
    v26 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
    v52 = 1;
    Parameter = FltAttachVolume(v26, *((PFLT_VOLUME *)v37 + 1), 0, &RetInstance);
    if ( v52 )
    {
      v27 = p_FltObject;
      v28 = RetInstance;
      if ( *p_FltObject )
        FltObjectDereference(*p_FltObject);
      *v27 = v28;
    }
    if ( Parameter < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Parameter,
        a7,
        (struct UnionFs::StackEventTracer *)0x4AC00210963LL,
        (unsigned __int64)"UnionFs::Utils::StatItem",
        "API: Attaching to target",
        (const char *)a1,
        (const struct _UNICODE_STRING *)EcpContext);
      if ( FltObject )
        FltObjectDereference(FltObject);
      goto LABEL_19;
    }
    v29 = v37;
    if ( *(_QWORD *)v37 )
    {
      FltObjectDereference(*(PVOID *)v37);
      *(_QWORD *)v37 = 0;
      v29 = v37;
    }
    v30 = (void *)*((_QWORD *)v29 + 1);
    if ( v30 )
    {
      FltObjectDereference(v30);
      *((_QWORD *)v37 + 1) = 0;
      v29 = v37;
    }
    v31 = UnionFs::g_FilterState;
    v32 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)v29 + 2);
    *((_QWORD *)v29 + 2) = 0;
    FltPrepareToReuseEcp(*v31, v37);
    v43 = 0;
    v42 = 40;
    v48 = a4;
    v47 = a8;
    v45 = EcpList;
    v49.Attributes = a3;
    v49.ObjectName = &v32->Name;
    v44 = 0;
    v46 = 0;
    v49.RootDirectory = 0;
    v17 = 0x52000210982LL;
    v49.Length = 48;
    *(_OWORD *)&v49.SecurityDescriptor = 0;
    if ( UnionFs::QueryInformationByName2 )
    {
      v33 = UnionFs::QueryInformationByName2(
              *(struct _FLT_FILTER **)UnionFs::g_FilterState,
              (struct _FLT_INSTANCE *)FltObject,
              &v49,
              (struct _IO_STATUS_BLOCK *)P,
              a6,
              0x48u,
              (enum _FILE_INFORMATION_CLASS)68,
              v58,
              &v55);
    }
    else
    {
      LODWORD(EcpContext) = 68;
      LODWORD(PoolTag) = 72;
      v33 = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, FltObject, &v49, P, a6);
    }
    Parameter = v33;
    if ( v32 )
      FltReleaseFileNameInformation(v32);
    if ( FltObject )
      FltObjectDereference(FltObject);
    if ( Parameter == -1073740951 || Parameter == -1073740952 )
      MicrosoftTelemetryAssertTriggeredMsgKM("Cross-volume reparse failed for FltQueryInformationByName");
  }
  wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v53);
  FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v21);
  v13 = v41;
LABEL_52:
  if ( Parameter == -2147483603 )
  {
    if ( v13 )
    {
      v34 = (struct _FLT_TAG_DATA_BUFFER *)P[1];
      if ( P[1] && *((_WORD *)P[1] + 2) <= 0x4000u )
      {
        Parameter = 260;
        Data->IoStatus.Information = *(unsigned int *)P[1];
        Data->TagData = v34;
        Data->IoStatus.Status = 260;
        FltSetCallbackDataDirty(Data);
      }
      else
      {
        Parameter = -1073741192;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000278LL,
          a7,
          (struct UnionFs::StackEventTracer *)0x657002109B5LL,
          (unsigned __int64)"UnionFs::Utils::StatItem",
          "ORIGIN: Bad symlink data",
          PoolTag);
      }
      return (unsigned int)Parameter;
    }
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
    goto LABEL_61;
  }
  if ( Parameter < 0 )
  {
LABEL_61:
    v18 = "API: FltQueryInformationByName";
    v19 = v17;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x140077774  mov     [rsp-8+arg_18], r9
0x140077779  mov     [rsp-8+arg_10], r8d
0x14007777e  push    rbp
0x14007777f  push    rbx
0x140077780  push    rsi
0x140077781  push    rdi
0x140077782  push    r12
0x140077784  push    r13
0x140077786  push    r14
0x140077788  lea     rbp, [rsp-60h]
0x14007778d  sub     rsp, 160h
0x140077794  mov     r13, [rbp+90h+arg_28]
0x14007779b  mov     rdi, rdx
0x14007779e  xor     edx, edx; Val
0x1400777a0  mov     ebx, r8d
0x1400777a3  mov     r14, rcx
0x1400777a6  mov     rsi, r9
0x1400777a9  mov     rcx, r13; void *
0x1400777ac  lea     r8d, [rdx+48h]; Size
0x1400777b0  call    memset
0x1400777b5  mov     r12d, dword ptr [rbp+90h+arg_20]
0x1400777bc  xor     edx, edx
0x1400777be  xorps   xmm0, xmm0
0x1400777c1  mov     [rbp+90h+var_76], edx
0x1400777c4  and     r12d, 4
0x1400777c8  mov     [rbp+90h+var_72], dx
0x1400777cc  movdqu  [rbp+90h+var_86], xmm0
0x1400777d1  lea     eax, [rdx+28h]
0x1400777d4  mov     [rbp+90h+var_68], rsi
0x1400777d8  mov     [rbp+90h+var_88], ax
0x1400777dc  mov     rax, [rbp+90h+arg_38]
0x1400777e3  mov     [rbp+90h+var_70], rax
0x1400777e7  mov     [rbp+90h+var_60], 30h ; '0'
0x1400777ef  mov     [rbp+90h+var_44], edx
0x1400777f2  mov     [rbp+90h+var_58], rdx
0x1400777f6  mov     [rbp+90h+var_48], ebx
0x1400777f9  mov     [rbp+90h+var_50], r14
0x1400777fd  movdqu  [rbp+90h+var_40], xmm0
0x140077802  mov     [rsp+190h+var_118], r12d
0x140077807  movups  xmmword ptr [rsp+190h+P], xmm0
0x14007780c  jnz     short loc_14007781F
0x14007780e  test    [rbp+90h+arg_20], 2
0x140077815  mov     ecx, edx
0x140077817  mov     [rbp+90h+arg_0], edx
0x14007781d  jz      short loc_14007782A
0x14007781f  mov     ecx, 8
0x140077824  mov     [rbp+90h+arg_0], ecx
0x14007782a  mov     rax, cs:?QueryInformationByName2@UnionFs@@3P6AJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@KPEAU_IO_DRIVER_CREATE_CONTEXT@@@ZEA; long (*UnionFs::QueryInformationByName2)(_FLT_FILTER *,_FLT_INSTANCE *,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x140077831  lea     r9, [rsp+190h+P]
0x140077836  lea     r8, [rbp+90h+var_60]
0x14007783a  test    rax, rax
0x14007783d  jz      short loc_140077875
0x14007783f  lea     rdx, [rbp+90h+var_88]
0x140077843  mov     [rsp+190h+var_150], rdx
0x140077848  mov     rdx, rdi
0x14007784b  mov     dword ptr [rsp+190h+var_158], ecx
0x14007784f  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077856  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'
0x14007785e  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077866  mov     [rsp+190h+CleanupCallback], r13
0x14007786b  mov     rcx, [rcx]
0x14007786e  call    _guard_dispatch_icall
0x140077873  jmp     short loc_1400778AC
0x140077875  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14007787c  lea     rax, [rbp+90h+var_88]
0x140077880  mov     [rsp+190h+var_158], rax
0x140077885  mov     rdx, rdi
0x140077888  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'; struct _UNICODE_STRING *
0x140077890  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077898  mov     rcx, [rcx]
0x14007789b  mov     [rsp+190h+CleanupCallback], r13
0x1400778a0  call    cs:__imp_FltQueryInformationByName
0x1400778a7  nop     dword ptr [rax+rax+00h]
0x1400778ac  mov     ebx, eax
0x1400778ae  cmp     eax, 0C0000369h
0x1400778b3  jz      short loc_1400778D1
0x1400778b5  mov     rsi, 0BC002108A8h
0x1400778bf  cmp     eax, 0C0000368h
0x1400778c4  jnz     loc_140077E46
0x1400778ca  mov     rsi, [rbp+90h+arg_18]
0x1400778d1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400778d8  lea     r8, [rsp+190h+EcpList]; EcpList
0x1400778dd  xor     edx, edx; Flags
0x1400778df  mov     [rsp+190h+EcpList], 0
0x1400778e8  mov     rcx, [rcx]; Filter
0x1400778eb  call    cs:__imp_FltAllocateExtraCreateParameterList
0x1400778f2  nop     dword ptr [rax+rax+00h]
0x1400778f7  mov     ebx, eax
0x1400778f9  test    eax, eax
0x1400778fb  jns     short loc_140077934
0x1400778fd  lea     rax, aApiAllocatingE; "API: Allocating ECP list"
0x140077904  mov     r8, 4A8002108E5h; struct UnionFs::StackEventTracer *
0x14007790e  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077915  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x14007791c  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x140077921  mov     ecx, ebx; this
0x140077923  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077928  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x14007792d  mov     eax, ebx
0x14007792f  jmp     loc_140077EFA
0x140077934  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14007793b  lea     rax, [rsp+190h+var_140]
0x140077940  mov     r12, [rsp+190h+EcpList]
0x140077945  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14007794c  mov     [rsp+190h+EcpContext], rax; struct _UNICODE_STRING *
0x140077951  xor     r9d, r9d; Flags
0x140077954  mov     [rsp+190h+var_140], 0
0x14007795d  mov     rcx, [rcx]; Filter
0x140077960  mov     [rsp+190h+PoolTag], 63654655h; char *
0x140077968  lea     r8d, [r9+20h]; SizeOfContext
0x14007796c  mov     [rsp+190h+CleanupCallback], 0; CleanupCallback
0x140077975  call    cs:__imp_FltAllocateExtraCreateParameter
0x14007797c  nop     dword ptr [rax+rax+00h]
0x140077981  xor     edx, edx
0x140077983  mov     ebx, eax
0x140077985  test    eax, eax
0x140077987  jns     short loc_1400779BE
0x140077989  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077990  lea     rax, aApiAllocatingT; "API: Allocating targeting ECP"
0x140077997  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x14007799c  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x1400779a3  mov     r8, 4A9002108F6h; struct UnionFs::StackEventTracer *
0x1400779ad  mov     [rsp+190h+CleanupCallback], rax; char *
0x1400779b2  mov     ecx, ebx; this
0x1400779b4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x1400779b9  jmp     loc_140077A50
0x1400779be  mov     rax, [rsp+190h+EcpList]
0x1400779c3  mov     rcx, [rsp+190h+var_140]
0x1400779c8  mov     [rbp+90h+var_A0], rax
0x1400779cc  mov     eax, 1
0x1400779d1  mov     [rbp+90h+var_90], al
0x1400779d4  mov     [rbp+90h+var_98], rcx
0x1400779d8  mov     [rcx+18h], ax
0x1400779dc  mov     rax, [rsp+190h+var_140]
0x1400779e1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400779e8  mov     [rax], rdx
0x1400779eb  mov     rax, [rsp+190h+var_140]
0x1400779f0  mov     [rax+8], rdx
0x1400779f4  mov     rax, [rsp+190h+var_140]
0x1400779f9  mov     [rax+10h], rdx
0x1400779fd  mov     r8, [rsp+190h+var_140]; EcpContext
0x140077a02  mov     rdx, [rsp+190h+EcpList]; EcpList
0x140077a07  mov     rcx, [rcx]; Filter
0x140077a0a  call    cs:__imp_FltInsertExtraCreateParameter
0x140077a11  nop     dword ptr [rax+rax+00h]
0x140077a16  mov     ebx, eax
0x140077a18  test    eax, eax
0x140077a1a  jns     short loc_140077A6E
0x140077a1c  lea     rax, aApiInsertingEc; "API: Inserting ECP"
0x140077a23  mov     r8, 4AA00210922h; struct UnionFs::StackEventTracer *
0x140077a2d  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077a34  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077a3b  mov     ecx, ebx; this
0x140077a3d  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077a42  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140077a47  lea     rcx, [rbp+90h+var_A0]
0x140077a4b  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x140077a50  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077a57  mov     rdx, r12; EcpList
0x140077a5a  mov     rcx, [rcx]; Filter
0x140077a5d  call    cs:__imp_FltFreeExtraCreateParameterList
0x140077a64  nop     dword ptr [rax+rax+00h]
0x140077a69  jmp     loc_14007792D
0x140077a6e  xor     eax, eax
0x140077a70  mov     [rbp+90h+var_F0], rsi
0x140077a74  mov     [rbp+90h+var_10A], ax
0x140077a78  lea     r9, [rsp+190h+P]
0x140077a7d  mov     [rbp+90h+var_100], rax
0x140077a81  lea     r8, [rbp+90h+var_E8]
0x140077a85  xor     esi, esi
0x140077a87  mov     [rbp+90h+var_10E], 0
0x140077a8e  mov     eax, 28h ; '('
0x140077a93  mov     [rbp+90h+var_E8], 30h ; '0'
0x140077a9b  mov     [rbp+90h+var_110], ax
0x140077a9f  xorps   xmm0, xmm0
0x140077aa2  mov     rax, [rbp+90h+arg_38]
0x140077aa9  mov     rdx, rdi
0x140077aac  mov     [rbp+90h+var_F8], rax
0x140077ab0  mov     rax, [rsp+190h+EcpList]
0x140077ab5  mov     [rbp+90h+var_108], rax
0x140077ab9  mov     eax, [rbp+90h+arg_10]
0x140077abf  mov     [rbp+90h+var_D0], eax
0x140077ac2  mov     rax, cs:?QueryInformationByName2@UnionFs@@3P6AJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@KPEAU_IO_DRIVER_CREATE_CONTEXT@@@ZEA; long (*UnionFs::QueryInformationByName2)(_FLT_FILTER *,_FLT_INSTANCE *,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x140077ac9  mov     [rbp+90h+var_CC], esi
0x140077acc  mov     [rbp+90h+var_E0], rsi
0x140077ad0  mov     [rbp+90h+var_D8], r14
0x140077ad4  movdqu  [rbp+90h+var_C8], xmm0
0x140077ad9  test    rax, rax
0x140077adc  jz      short loc_140077B17
0x140077ade  lea     rcx, [rbp+90h+var_88]
0x140077ae2  mov     [rsp+190h+var_150], rcx
0x140077ae7  mov     ecx, [rbp+90h+arg_0]
0x140077aed  mov     dword ptr [rsp+190h+var_158], ecx
0x140077af1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077af8  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'
0x140077b00  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077b08  mov     [rsp+190h+CleanupCallback], r13
0x140077b0d  mov     rcx, [rcx]
0x140077b10  call    _guard_dispatch_icall
0x140077b15  jmp     short loc_140077B4B
0x140077b17  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077b1e  lea     rax, [rbp+90h+var_110]
0x140077b22  mov     [rsp+190h+var_158], rax
0x140077b27  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'; struct _UNICODE_STRING *
0x140077b2f  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077b37  mov     rcx, [rcx]
0x140077b3a  mov     [rsp+190h+CleanupCallback], r13
0x140077b3f  call    cs:__imp_FltQueryInformationByName
0x140077b46  nop     dword ptr [rax+rax+00h]
0x140077b4b  mov     ebx, eax
0x140077b4d  cmp     eax, 0C0000369h
0x140077b52  jz      short loc_140077B6B
0x140077b54  mov     rsi, 4AB00210931h
0x140077b5e  cmp     eax, 0C0000368h
0x140077b63  jnz     loc_140077E1F
0x140077b69  xor     esi, esi
0x140077b6b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077b72  mov     rdx, [rsp+190h+var_140]; EcpContext
0x140077b77  mov     rcx, [rcx]; Filter
0x140077b7a  call    cs:__imp_FltIsEcpAcknowledged
0x140077b81  nop     dword ptr [rax+rax+00h]
0x140077b86  test    al, al
0x140077b88  jnz     short loc_140077B96
0x140077b8a  lea     rcx, aFltmgrDidNotAc; "FltMgr DID NOT acknowledge cross-volume"...
0x140077b91  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140077b96  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077b9d  mov     rdx, [rsp+190h+var_140]; EcpContext
0x140077ba2  mov     rcx, [rcx]; Filter
0x140077ba5  call    cs:__imp_FltIsEcpAcknowledged
0x140077bac  nop     dword ptr [rax+rax+00h]
0x140077bb1  test    al, al
0x140077bb3  jnz     short loc_140077BCB
0x140077bb5  lea     rax, aApiFltCreatefi; "API: FLT_CREATEFILE_TARGET_ECP not ackn"...
0x140077bbc  mov     r8, 52100210958h
0x140077bc6  jmp     loc_140077A2D
0x140077bcb  mov     rdx, [rsp+190h+var_140]
0x140077bd0  lea     rax, [rsp+190h+FltObject]
0x140077bd5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077bdc  lea     r9, [rbp+90h+RetInstance]; RetInstance
0x140077be0  mov     [rsp+190h+FltObject], rsi
0x140077be5  xor     r8d, r8d; InstanceName
0x140077be8  mov     [rbp+90h+var_B8], rax
0x140077bec  mov     [rbp+90h+RetInstance], rsi
0x140077bf0  mov     rcx, [rcx]; Filter
0x140077bf3  mov     [rbp+90h+var_A8], 1
0x140077bf7  mov     rdx, [rdx+8]; Volume
0x140077bfb  call    cs:__imp_FltAttachVolume
0x140077c02  nop     dword ptr [rax+rax+00h]
0x140077c07  mov     ebx, eax
0x140077c09  cmp     [rbp+90h+var_A8], sil
0x140077c0d  jz      short loc_140077C30
0x140077c0f  mov     rdi, [rbp+90h+var_B8]
0x140077c13  mov     rsi, [rbp+90h+RetInstance]
0x140077c17  mov     rcx, [rdi]; FltObject
0x140077c1a  test    rcx, rcx
0x140077c1d  jz      short loc_140077C2B
0x140077c1f  call    cs:__imp_FltObjectDereference
0x140077c26  nop     dword ptr [rax+rax+00h]
0x140077c2b  mov     [rdi], rsi
0x140077c2e  xor     esi, esi
0x140077c30  test    ebx, ebx
0x140077c32  jns     short loc_140077C83
0x140077c34  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077c3b  lea     rax, aApiAttachingTo; "API: Attaching to target"
0x140077c42  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x140077c47  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077c4e  mov     r8, 4AC00210963h; struct UnionFs::StackEventTracer *
0x140077c58  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077c5d  mov     ecx, ebx; this
0x140077c5f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140077c64  mov     rcx, [rsp+190h+FltObject]; FltObject
0x140077c69  test    rcx, rcx
0x140077c6c  jz      loc_140077A47
0x140077c72  call    cs:__imp_FltObjectDereference
0x140077c79  nop     dword ptr [rax+rax+00h]
0x140077c7e  jmp     loc_140077A47
0x140077c83  mov     rax, [rsp+190h+var_140]
0x140077c88  mov     rcx, [rax]; FltObject
0x140077c8b  test    rcx, rcx
0x140077c8e  jz      short loc_140077CA9
0x140077c90  call    cs:__imp_FltObjectDereference
0x140077c97  nop     dword ptr [rax+rax+00h]
0x140077c9c  mov     rax, [rsp+190h+var_140]
0x140077ca1  mov     [rax], rsi
0x140077ca4  mov     rax, [rsp+190h+var_140]
0x140077ca9  mov     rcx, [rax+8]; FltObject
0x140077cad  test    rcx, rcx
0x140077cb0  jz      short loc_140077CCC
0x140077cb2  call    cs:__imp_FltObjectDereference
0x140077cb9  nop     dword ptr [rax+rax+00h]
0x140077cbe  mov     rax, [rsp+190h+var_140]
0x140077cc3  mov     [rax+8], rsi
0x140077cc7  mov     rax, [rsp+190h+var_140]
0x140077ccc  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077cd3  mov     rdi, [rax+10h]
0x140077cd7  mov     [rax+10h], rsi
0x140077cdb  mov     rdx, [rsp+190h+var_140]
0x140077ce0  mov     rcx, [rcx]
0x140077ce3  call    cs:__imp_FltPrepareToReuseEcp
0x140077cea  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
