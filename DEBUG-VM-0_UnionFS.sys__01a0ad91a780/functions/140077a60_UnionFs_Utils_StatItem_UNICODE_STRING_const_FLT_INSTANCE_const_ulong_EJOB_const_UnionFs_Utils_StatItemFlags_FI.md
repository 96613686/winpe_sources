# UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,ulong,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)

- ea: `0x140077a60`
- end: `0x140078233`
- name: `?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@KAEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `2003`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140060764`
- `0x1400779fc`
- `0x1400782bc`

## callees

- `0x14001abe4`
- `0x140056bd0`
- `0x140056c08`
- `0x140056c44`
- `0x140077a60`
- `0x14007b2b0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400781fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400781fd`
- `FLTMGR!FltQueryInformationByName` at `0x140077b8c`
- `FLTMGR!FltQueryInformationByName` at `0x140077e2b`
- `FLTMGR!FltQueryInformationByName` at `0x1400780b7`
- `FLTMGR!FltQueryInformationByName` at `0x140077b8c`
- `FLTMGR!FltQueryInformationByName` at `0x140077e2b`
- `FLTMGR!FltQueryInformationByName` at `0x1400780b7`
- `FLTMGR!FltPrepareToReuseEcp` at `0x140077fcf`
- `FLTMGR!FltPrepareToReuseEcp` at `0x140077fcf`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140077bd7`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140077bd7`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077d49`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140078121`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140077d49`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140078121`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140077cf6`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140077cf6`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140077c61`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x140077c61`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077e66`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077e91`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077e66`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140077e91`
- `FLTMGR!FltAttachVolume` at `0x140077ee7`
- `FLTMGR!FltAttachVolume` at `0x140077ee7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400780cd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400780cd`
- `FLTMGR!FltObjectDereference` at `0x140077f0b`
- `FLTMGR!FltObjectDereference` at `0x140077f5e`
- `FLTMGR!FltObjectDereference` at `0x140077f7c`
- `FLTMGR!FltObjectDereference` at `0x140077f9e`
- `FLTMGR!FltObjectDereference` at `0x1400780e3`
- `FLTMGR!FltObjectDereference` at `0x140077f0b`
- `FLTMGR!FltObjectDereference` at `0x140077f5e`
- `FLTMGR!FltObjectDereference` at `0x140077f7c`
- `FLTMGR!FltObjectDereference` at `0x140077f9e`
- `FLTMGR!FltObjectDereference` at `0x1400780e3`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400781ab`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400781ab`

## string_xrefs

- `0x140077ea1`: `API: FLT_CREATEFILE_TARGET_ECP not acknowledged`
- `0x1400780ff`: `Cross-volume reparse failed for FltQueryInformationByName`
- `0x1400781c3`: `ORIGIN: Bad symlink data`

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
  struct _FLT_TAG_DATA_BUFFER *v34; // r8
  __int16 v35; // r9
  PFILE_OBJECT TargetFileObject; // r10
  unsigned __int16 v37; // ax
  const char *PoolTag; // [rsp+28h] [rbp-D8h]
  PVOID *EcpContext; // [rsp+30h] [rbp-D0h]
  PVOID v40; // [rsp+50h] [rbp-B0h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp-A8h] BYREF
  PVOID FltObject; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h] BYREF
  int v44; // [rsp+78h] [rbp-88h]
  __int16 v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+82h] [rbp-7Eh]
  __int16 v47; // [rsp+86h] [rbp-7Ah]
  PECP_LIST v48; // [rsp+88h] [rbp-78h]
  __int64 v49; // [rsp+90h] [rbp-70h]
  struct _TXN_PARAMETER_BLOCK *v50; // [rsp+98h] [rbp-68h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES v52; // [rsp+A8h] [rbp-58h] BYREF
  PVOID *p_FltObject; // [rsp+D8h] [rbp-28h]
  PFLT_INSTANCE RetInstance; // [rsp+E0h] [rbp-20h] BYREF
  char v55; // [rsp+E8h] [rbp-18h]
  _QWORD v56[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v57; // [rsp+100h] [rbp+0h]
  struct _IO_DRIVER_CREATE_CONTEXT v58; // [rsp+108h] [rbp+8h] BYREF
  __int64 v59; // [rsp+128h] [rbp+28h]
  struct _OBJECT_ATTRIBUTES v60[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v61; // [rsp+1A0h] [rbp+A0h]

  v12 = a4;
  memset(a6, 0, 0x48u);
  v13 = a5 & 4;
  memset(&v58.Size + 1, 0, 22);
  v59 = v12;
  v58.Size = 40;
  v58.TxnParameters = a8;
  *(_QWORD *)&v60[0].Length = 48;
  *(&v60[0].Attributes + 1) = 0;
  v60[0].RootDirectory = 0;
  v60[0].Attributes = a3;
  v60[0].ObjectName = a1;
  *(_OWORD *)&v60[0].SecurityDescriptor = 0;
  v44 = v13;
  *(_OWORD *)P = 0;
  if ( (a5 & 4) != 0 || (v14 = 0, v61 = 0, (a5 & 2) != 0) )
  {
    v14 = 8;
    v61 = 8;
  }
  if ( UnionFs::QueryInformationByName2 )
  {
    InformationByName = UnionFs::QueryInformationByName2(
                          *(struct _FLT_FILTER **)UnionFs::g_FilterState,
                          a2,
                          v60,
                          (struct _IO_STATUS_BLOCK *)P,
                          a6,
                          0x48u,
                          (enum _FILE_INFORMATION_CLASS)68,
                          v14,
                          &v58);
  }
  else
  {
    LODWORD(EcpContext) = 68;
    LODWORD(PoolTag) = 72;
    InformationByName = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, a2, v60, P, a6);
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
  v40 = 0;
  Parameter = FltAllocateExtraCreateParameter(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                &GUID_ECP_FLT_CREATEFILE_TARGET,
                0x20u,
                0,
                0,
                0x63654655u,
                &v40);
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
  v56[0] = EcpList;
  v57 = 1;
  v56[1] = v40;
  *((_WORD *)v40 + 12) = 1;
  v22 = (PFLT_FILTER *)UnionFs::g_FilterState;
  *(_QWORD *)v40 = 0;
  *((_QWORD *)v40 + 1) = 0;
  *((_QWORD *)v40 + 2) = 0;
  Parameter = FltInsertExtraCreateParameter(*v22, EcpList, v40);
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
    wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v56);
    goto LABEL_20;
  }
  v51 = v12;
  v47 = 0;
  v49 = 0;
  v46 = 0;
  *(_QWORD *)&v52.Length = 48;
  v45 = 40;
  v50 = a8;
  v48 = EcpList;
  v52.Attributes = a3;
  memset(&v52.Attributes + 1, 0, 20);
  v52.RootDirectory = 0;
  v52.ObjectName = a1;
  if ( UnionFs::QueryInformationByName2 )
  {
    v25 = UnionFs::QueryInformationByName2(
            *(struct _FLT_FILTER **)UnionFs::g_FilterState,
            a2,
            &v52,
            (struct _IO_STATUS_BLOCK *)P,
            a6,
            0x48u,
            (enum _FILE_INFORMATION_CLASS)68,
            v61,
            &v58);
  }
  else
  {
    LODWORD(EcpContext) = 68;
    LODWORD(PoolTag) = 72;
    v25 = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, a2, &v52, P, a6);
  }
  Parameter = v25;
  if ( v25 == -1073740951 || (v17 = 0x4AB00210931LL, v25 == -1073740952) )
  {
    if ( !FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, v40) )
      MicrosoftTelemetryAssertTriggeredMsgKM("FltMgr DID NOT acknowledge cross-volume ECP!");
    if ( !FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, v40) )
    {
      v23 = "API: FLT_CREATEFILE_TARGET_ECP not acknowledged";
      v24 = 0x52100210958LL;
      goto LABEL_18;
    }
    FltObject = 0;
    p_FltObject = &FltObject;
    RetInstance = 0;
    v26 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
    v55 = 1;
    Parameter = FltAttachVolume(v26, *((PFLT_VOLUME *)v40 + 1), 0, &RetInstance);
    if ( v55 )
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
    v29 = v40;
    if ( *(_QWORD *)v40 )
    {
      FltObjectDereference(*(PVOID *)v40);
      *(_QWORD *)v40 = 0;
      v29 = v40;
    }
    v30 = (void *)*((_QWORD *)v29 + 1);
    if ( v30 )
    {
      FltObjectDereference(v30);
      *((_QWORD *)v40 + 1) = 0;
      v29 = v40;
    }
    v31 = UnionFs::g_FilterState;
    v32 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)v29 + 2);
    *((_QWORD *)v29 + 2) = 0;
    FltPrepareToReuseEcp(*v31, v40);
    v46 = 0;
    v45 = 40;
    v51 = a4;
    v50 = a8;
    v48 = EcpList;
    v52.Attributes = a3;
    v52.ObjectName = &v32->Name;
    v47 = 0;
    v49 = 0;
    v52.RootDirectory = 0;
    v17 = 0x52000210982LL;
    v52.Length = 48;
    *(_OWORD *)&v52.SecurityDescriptor = 0;
    if ( UnionFs::QueryInformationByName2 )
    {
      v33 = UnionFs::QueryInformationByName2(
              *(struct _FLT_FILTER **)UnionFs::g_FilterState,
              (struct _FLT_INSTANCE *)FltObject,
              &v52,
              (struct _IO_STATUS_BLOCK *)P,
              a6,
              0x48u,
              (enum _FILE_INFORMATION_CLASS)68,
              v61,
              &v58);
    }
    else
    {
      LODWORD(EcpContext) = 68;
      LODWORD(PoolTag) = 72;
      v33 = FltQueryInformationByName(*(_QWORD *)UnionFs::g_FilterState, FltObject, &v52, P, a6);
    }
    Parameter = v33;
    if ( v32 )
      FltReleaseFileNameInformation(v32);
    if ( FltObject )
      FltObjectDereference(FltObject);
    if ( Parameter == -1073740951 || Parameter == -1073740952 )
      MicrosoftTelemetryAssertTriggeredMsgKM("Cross-volume reparse failed for FltQueryInformationByName");
  }
  wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v56);
  FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v21);
  v13 = v44;
LABEL_52:
  if ( Parameter == -2147483603 )
  {
    if ( v13 )
    {
      v34 = (struct _FLT_TAG_DATA_BUFFER *)P[1];
      if ( P[1] && *((_WORD *)P[1] + 2) <= 0x4000u )
      {
        v35 = *((_WORD *)P[1] + 3);
        TargetFileObject = Data->Iopb->TargetFileObject;
        v37 = TargetFileObject->FileName.Length - v35;
        if ( v37 && TargetFileObject->FileName.Buffer[((unsigned __int64)v37 >> 1) - 1] == 92 )
          *((_WORD *)P[1] + 3) = v35 + 2;
        Parameter = 260;
        Data->IoStatus.Information = v34->FileTag;
        Data->IoStatus.Status = 260;
        Data->TagData = v34;
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
    goto LABEL_64;
  }
  if ( Parameter < 0 )
  {
LABEL_64:
    v18 = "API: FltQueryInformationByName";
    v19 = v17;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x140077a60  mov     [rsp-8+arg_18], r9
0x140077a65  mov     [rsp-8+arg_10], r8d
0x140077a6a  push    rbp
0x140077a6b  push    rbx
0x140077a6c  push    rsi
0x140077a6d  push    rdi
0x140077a6e  push    r12
0x140077a70  push    r13
0x140077a72  push    r14
0x140077a74  lea     rbp, [rsp-60h]
0x140077a79  sub     rsp, 160h
0x140077a80  mov     r13, [rbp+90h+arg_28]
0x140077a87  mov     rdi, rdx
0x140077a8a  xor     edx, edx; Val
0x140077a8c  mov     ebx, r8d
0x140077a8f  mov     r14, rcx
0x140077a92  mov     rsi, r9
0x140077a95  mov     rcx, r13; void *
0x140077a98  lea     r8d, [rdx+48h]; Size
0x140077a9c  call    memset
0x140077aa1  mov     r12d, dword ptr [rbp+90h+arg_20]
0x140077aa8  xor     edx, edx
0x140077aaa  xorps   xmm0, xmm0
0x140077aad  mov     [rbp+90h+var_76], edx
0x140077ab0  and     r12d, 4
0x140077ab4  mov     [rbp+90h+var_72], dx
0x140077ab8  movdqu  [rbp+90h+var_86], xmm0
0x140077abd  lea     eax, [rdx+28h]
0x140077ac0  mov     [rbp+90h+var_68], rsi
0x140077ac4  mov     [rbp+90h+var_88], ax
0x140077ac8  mov     rax, [rbp+90h+arg_38]
0x140077acf  mov     [rbp+90h+var_70], rax
0x140077ad3  mov     [rbp+90h+var_60], 30h ; '0'
0x140077adb  mov     [rbp+90h+var_44], edx
0x140077ade  mov     [rbp+90h+var_58], rdx
0x140077ae2  mov     [rbp+90h+var_48], ebx
0x140077ae5  mov     [rbp+90h+var_50], r14
0x140077ae9  movdqu  [rbp+90h+var_40], xmm0
0x140077aee  mov     [rsp+190h+var_118], r12d
0x140077af3  movups  xmmword ptr [rsp+190h+P], xmm0
0x140077af8  jnz     short loc_140077B0B
0x140077afa  test    [rbp+90h+arg_20], 2
0x140077b01  mov     ecx, edx
0x140077b03  mov     [rbp+90h+arg_0], edx
0x140077b09  jz      short loc_140077B16
0x140077b0b  mov     ecx, 8
0x140077b10  mov     [rbp+90h+arg_0], ecx
0x140077b16  mov     rax, cs:?QueryInformationByName2@UnionFs@@3P6AJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@KPEAU_IO_DRIVER_CREATE_CONTEXT@@@ZEA; long (*UnionFs::QueryInformationByName2)(_FLT_FILTER *,_FLT_INSTANCE *,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x140077b1d  lea     r9, [rsp+190h+P]
0x140077b22  lea     r8, [rbp+90h+var_60]
0x140077b26  test    rax, rax
0x140077b29  jz      short loc_140077B61
0x140077b2b  lea     rdx, [rbp+90h+var_88]
0x140077b2f  mov     [rsp+190h+var_150], rdx
0x140077b34  mov     rdx, rdi
0x140077b37  mov     dword ptr [rsp+190h+var_158], ecx
0x140077b3b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077b42  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'
0x140077b4a  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077b52  mov     [rsp+190h+CleanupCallback], r13
0x140077b57  mov     rcx, [rcx]
0x140077b5a  call    _guard_dispatch_icall
0x140077b5f  jmp     short loc_140077B98
0x140077b61  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077b68  lea     rax, [rbp+90h+var_88]
0x140077b6c  mov     [rsp+190h+var_158], rax
0x140077b71  mov     rdx, rdi
0x140077b74  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'; struct _UNICODE_STRING *
0x140077b7c  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077b84  mov     rcx, [rcx]
0x140077b87  mov     [rsp+190h+CleanupCallback], r13
0x140077b8c  call    cs:__imp_FltQueryInformationByName
0x140077b93  nop     dword ptr [rax+rax+00h]
0x140077b98  mov     ebx, eax
0x140077b9a  cmp     eax, 0C0000369h
0x140077b9f  jz      short loc_140077BBD
0x140077ba1  mov     rsi, 0BC002108A8h
0x140077bab  cmp     eax, 0C0000368h
0x140077bb0  jnz     loc_140078132
0x140077bb6  mov     rsi, [rbp+90h+arg_18]
0x140077bbd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077bc4  lea     r8, [rsp+190h+EcpList]; EcpList
0x140077bc9  xor     edx, edx; Flags
0x140077bcb  mov     [rsp+190h+EcpList], 0
0x140077bd4  mov     rcx, [rcx]; Filter
0x140077bd7  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140077bde  nop     dword ptr [rax+rax+00h]
0x140077be3  mov     ebx, eax
0x140077be5  test    eax, eax
0x140077be7  jns     short loc_140077C20
0x140077be9  lea     rax, aApiAllocatingE; "API: Allocating ECP list"
0x140077bf0  mov     r8, 4A8002108E5h; struct UnionFs::StackEventTracer *
0x140077bfa  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077c01  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077c08  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x140077c0d  mov     ecx, ebx; this
0x140077c0f  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077c14  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140077c19  mov     eax, ebx
0x140077c1b  jmp     loc_140078220
0x140077c20  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077c27  lea     rax, [rsp+190h+var_140]
0x140077c2c  mov     r12, [rsp+190h+EcpList]
0x140077c31  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x140077c38  mov     [rsp+190h+EcpContext], rax; struct _UNICODE_STRING *
0x140077c3d  xor     r9d, r9d; Flags
0x140077c40  mov     [rsp+190h+var_140], 0
0x140077c49  mov     rcx, [rcx]; Filter
0x140077c4c  mov     [rsp+190h+PoolTag], 63654655h; char *
0x140077c54  lea     r8d, [r9+20h]; SizeOfContext
0x140077c58  mov     [rsp+190h+CleanupCallback], 0; CleanupCallback
0x140077c61  call    cs:__imp_FltAllocateExtraCreateParameter
0x140077c68  nop     dword ptr [rax+rax+00h]
0x140077c6d  xor     edx, edx
0x140077c6f  mov     ebx, eax
0x140077c71  test    eax, eax
0x140077c73  jns     short loc_140077CAA
0x140077c75  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077c7c  lea     rax, aApiAllocatingT; "API: Allocating targeting ECP"
0x140077c83  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x140077c88  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077c8f  mov     r8, 4A9002108F6h; struct UnionFs::StackEventTracer *
0x140077c99  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077c9e  mov     ecx, ebx; this
0x140077ca0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140077ca5  jmp     loc_140077D3C
0x140077caa  mov     rax, [rsp+190h+EcpList]
0x140077caf  mov     rcx, [rsp+190h+var_140]
0x140077cb4  mov     [rbp+90h+var_A0], rax
0x140077cb8  mov     eax, 1
0x140077cbd  mov     [rbp+90h+var_90], al
0x140077cc0  mov     [rbp+90h+var_98], rcx
0x140077cc4  mov     [rcx+18h], ax
0x140077cc8  mov     rax, [rsp+190h+var_140]
0x140077ccd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077cd4  mov     [rax], rdx
0x140077cd7  mov     rax, [rsp+190h+var_140]
0x140077cdc  mov     [rax+8], rdx
0x140077ce0  mov     rax, [rsp+190h+var_140]
0x140077ce5  mov     [rax+10h], rdx
0x140077ce9  mov     r8, [rsp+190h+var_140]; EcpContext
0x140077cee  mov     rdx, [rsp+190h+EcpList]; EcpList
0x140077cf3  mov     rcx, [rcx]; Filter
0x140077cf6  call    cs:__imp_FltInsertExtraCreateParameter
0x140077cfd  nop     dword ptr [rax+rax+00h]
0x140077d02  mov     ebx, eax
0x140077d04  test    eax, eax
0x140077d06  jns     short loc_140077D5A
0x140077d08  lea     rax, aApiInsertingEc; "API: Inserting ECP"
0x140077d0f  mov     r8, 4AA00210922h; struct UnionFs::StackEventTracer *
0x140077d19  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077d20  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077d27  mov     ecx, ebx; this
0x140077d29  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077d2e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140077d33  lea     rcx, [rbp+90h+var_A0]
0x140077d37  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x140077d3c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077d43  mov     rdx, r12; EcpList
0x140077d46  mov     rcx, [rcx]; Filter
0x140077d49  call    cs:__imp_FltFreeExtraCreateParameterList
0x140077d50  nop     dword ptr [rax+rax+00h]
0x140077d55  jmp     loc_140077C19
0x140077d5a  xor     eax, eax
0x140077d5c  mov     [rbp+90h+var_F0], rsi
0x140077d60  mov     [rbp+90h+var_10A], ax
0x140077d64  lea     r9, [rsp+190h+P]
0x140077d69  mov     [rbp+90h+var_100], rax
0x140077d6d  lea     r8, [rbp+90h+var_E8]
0x140077d71  xor     esi, esi
0x140077d73  mov     [rbp+90h+var_10E], 0
0x140077d7a  mov     eax, 28h ; '('
0x140077d7f  mov     [rbp+90h+var_E8], 30h ; '0'
0x140077d87  mov     [rbp+90h+var_110], ax
0x140077d8b  xorps   xmm0, xmm0
0x140077d8e  mov     rax, [rbp+90h+arg_38]
0x140077d95  mov     rdx, rdi
0x140077d98  mov     [rbp+90h+var_F8], rax
0x140077d9c  mov     rax, [rsp+190h+EcpList]
0x140077da1  mov     [rbp+90h+var_108], rax
0x140077da5  mov     eax, [rbp+90h+arg_10]
0x140077dab  mov     [rbp+90h+var_D0], eax
0x140077dae  mov     rax, cs:?QueryInformationByName2@UnionFs@@3P6AJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@KPEAU_IO_DRIVER_CREATE_CONTEXT@@@ZEA; long (*UnionFs::QueryInformationByName2)(_FLT_FILTER *,_FLT_INSTANCE *,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x140077db5  mov     [rbp+90h+var_CC], esi
0x140077db8  mov     [rbp+90h+var_E0], rsi
0x140077dbc  mov     [rbp+90h+var_D8], r14
0x140077dc0  movdqu  [rbp+90h+var_C8], xmm0
0x140077dc5  test    rax, rax
0x140077dc8  jz      short loc_140077E03
0x140077dca  lea     rcx, [rbp+90h+var_88]
0x140077dce  mov     [rsp+190h+var_150], rcx
0x140077dd3  mov     ecx, [rbp+90h+arg_0]
0x140077dd9  mov     dword ptr [rsp+190h+var_158], ecx
0x140077ddd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077de4  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'
0x140077dec  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077df4  mov     [rsp+190h+CleanupCallback], r13
0x140077df9  mov     rcx, [rcx]
0x140077dfc  call    _guard_dispatch_icall
0x140077e01  jmp     short loc_140077E37
0x140077e03  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077e0a  lea     rax, [rbp+90h+var_110]
0x140077e0e  mov     [rsp+190h+var_158], rax
0x140077e13  mov     dword ptr [rsp+190h+EcpContext], 44h ; 'D'; struct _UNICODE_STRING *
0x140077e1b  mov     [rsp+190h+PoolTag], 48h ; 'H'
0x140077e23  mov     rcx, [rcx]
0x140077e26  mov     [rsp+190h+CleanupCallback], r13
0x140077e2b  call    cs:__imp_FltQueryInformationByName
0x140077e32  nop     dword ptr [rax+rax+00h]
0x140077e37  mov     ebx, eax
0x140077e39  cmp     eax, 0C0000369h
0x140077e3e  jz      short loc_140077E57
0x140077e40  mov     rsi, 4AB00210931h
0x140077e4a  cmp     eax, 0C0000368h
0x140077e4f  jnz     loc_14007810B
0x140077e55  xor     esi, esi
0x140077e57  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077e5e  mov     rdx, [rsp+190h+var_140]; EcpContext
0x140077e63  mov     rcx, [rcx]; Filter
0x140077e66  call    cs:__imp_FltIsEcpAcknowledged
0x140077e6d  nop     dword ptr [rax+rax+00h]
0x140077e72  test    al, al
0x140077e74  jnz     short loc_140077E82
0x140077e76  lea     rcx, aFltmgrDidNotAc; "FltMgr DID NOT acknowledge cross-volume"...
0x140077e7d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140077e82  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077e89  mov     rdx, [rsp+190h+var_140]; EcpContext
0x140077e8e  mov     rcx, [rcx]; Filter
0x140077e91  call    cs:__imp_FltIsEcpAcknowledged
0x140077e98  nop     dword ptr [rax+rax+00h]
0x140077e9d  test    al, al
0x140077e9f  jnz     short loc_140077EB7
0x140077ea1  lea     rax, aApiFltCreatefi; "API: FLT_CREATEFILE_TARGET_ECP not ackn"...
0x140077ea8  mov     r8, 52100210958h
0x140077eb2  jmp     loc_140077D19
0x140077eb7  mov     rdx, [rsp+190h+var_140]
0x140077ebc  lea     rax, [rsp+190h+FltObject]
0x140077ec1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077ec8  lea     r9, [rbp+90h+RetInstance]; RetInstance
0x140077ecc  mov     [rsp+190h+FltObject], rsi
0x140077ed1  xor     r8d, r8d; InstanceName
0x140077ed4  mov     [rbp+90h+var_B8], rax
0x140077ed8  mov     [rbp+90h+RetInstance], rsi
0x140077edc  mov     rcx, [rcx]; Filter
0x140077edf  mov     [rbp+90h+var_A8], 1
0x140077ee3  mov     rdx, [rdx+8]; Volume
0x140077ee7  call    cs:__imp_FltAttachVolume
0x140077eee  nop     dword ptr [rax+rax+00h]
0x140077ef3  mov     ebx, eax
0x140077ef5  cmp     [rbp+90h+var_A8], sil
0x140077ef9  jz      short loc_140077F1C
0x140077efb  mov     rdi, [rbp+90h+var_B8]
0x140077eff  mov     rsi, [rbp+90h+RetInstance]
0x140077f03  mov     rcx, [rdi]; FltObject
0x140077f06  test    rcx, rcx
0x140077f09  jz      short loc_140077F17
0x140077f0b  call    cs:__imp_FltObjectDereference
0x140077f12  nop     dword ptr [rax+rax+00h]
0x140077f17  mov     [rdi], rsi
0x140077f1a  xor     esi, esi
0x140077f1c  test    ebx, ebx
0x140077f1e  jns     short loc_140077F6F
0x140077f20  mov     rdx, qword ptr [rbp+90h+arg_30]; int
0x140077f27  lea     rax, aApiAttachingTo; "API: Attaching to target"
0x140077f2e  mov     qword ptr [rsp+190h+PoolTag], r14; char *
0x140077f33  lea     r9, aUnionfsUtilsSt; "UnionFs::Utils::StatItem"
0x140077f3a  mov     r8, 4AC00210963h; struct UnionFs::StackEventTracer *
0x140077f44  mov     [rsp+190h+CleanupCallback], rax; char *
0x140077f49  mov     ecx, ebx; this
0x140077f4b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140077f50  mov     rcx, [rsp+190h+FltObject]; FltObject
0x140077f55  test    rcx, rcx
0x140077f58  jz      loc_140077D33
0x140077f5e  call    cs:__imp_FltObjectDereference
0x140077f65  nop     dword ptr [rax+rax+00h]
0x140077f6a  jmp     loc_140077D33
0x140077f6f  mov     rax, [rsp+190h+var_140]
0x140077f74  mov     rcx, [rax]; FltObject
0x140077f77  test    rcx, rcx
0x140077f7a  jz      short loc_140077F95
0x140077f7c  call    cs:__imp_FltObjectDereference
0x140077f83  nop     dword ptr [rax+rax+00h]
0x140077f88  mov     rax, [rsp+190h+var_140]
0x140077f8d  mov     [rax], rsi
0x140077f90  mov     rax, [rsp+190h+var_140]
0x140077f95  mov     rcx, [rax+8]; FltObject
0x140077f99  test    rcx, rcx
0x140077f9c  jz      short loc_140077FB8
0x140077f9e  call    cs:__imp_FltObjectDereference
0x140077fa5  nop     dword ptr [rax+rax+00h]
0x140077faa  mov     rax, [rsp+190h+var_140]
0x140077faf  mov     [rax+8], rsi
0x140077fb3  mov     rax, [rsp+190h+var_140]
0x140077fb8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140077fbf  mov     rdi, [rax+10h]
0x140077fc3  mov     [rax+10h], rsi
0x140077fc7  mov     rdx, [rsp+190h+var_140]
0x140077fcc  mov     rcx, [rcx]
0x140077fcf  call    cs:__imp_FltPrepareToReuseEcp
0x140077fd6  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
