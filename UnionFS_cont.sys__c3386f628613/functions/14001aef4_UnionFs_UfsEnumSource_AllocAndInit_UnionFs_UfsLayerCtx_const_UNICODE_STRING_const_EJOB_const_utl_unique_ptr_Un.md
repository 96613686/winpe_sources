# UnionFs::UfsEnumSource::AllocAndInit(UnionFs::UfsLayerCtx const &,_UNICODE_STRING const &,_EJOB const &,utl::unique_ptr<UnionFs::UfsEnumSource,utl::default_delete<UnionFs::UfsEnumSource>> &,UnionFs::StackEventTracer &,ulong,_FLT_INSTANCE const *,void *)

- ea: `0x14001aef4`
- end: `0x14001b5fd`
- name: `?AllocAndInit@UfsEnumSource@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_UNICODE_STRING@@AEBU_EJOB@@AEAV?$unique_ptr@VUfsEnumSource@UnionFs@@U?$default_delete@VUfsEnumSource@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@KPEBU_FLT_INSTANCE@@PEAX@Z`
- size: `1801`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsLayerCtx *this@<rcx>, PCUNICODE_STRING Source@<rdx>, struct _UNICODE_STRING *, struct _UNICODE_STRING, PVOID EcpContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025168`

## callees

- `0x14001ab44`
- `0x14001aef4`
- `0x140036128`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14006a3cc`
- `0x140079c48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001af61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b51e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001af61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b51e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b49a`
- `ntoskrnl!ExAllocatePool2` at `0x14001b49a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001af3b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b0f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b3cd`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b4f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b547`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5b2`
- `ntoskrnl!ObfDereferenceObject` at `0x14001af3b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b0f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b3cd`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b4f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b547`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5b2`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001b126`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001b126`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b1f0`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b444`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b1f0`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b444`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001b267`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001b267`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001b1a8`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001b1a8`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001b3ee`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001b3ee`
- `FLTMGR!FltCreateFileEx2` at `0x14001b0d0`
- `FLTMGR!FltCreateFileEx2` at `0x14001b3a3`
- `FLTMGR!FltCreateFileEx2` at `0x14001b0d0`
- `FLTMGR!FltCreateFileEx2` at `0x14001b3a3`
- `FLTMGR!FltClose` at `0x14001af50`
- `FLTMGR!FltClose` at `0x14001b329`
- `FLTMGR!FltClose` at `0x14001b50d`
- `FLTMGR!FltClose` at `0x14001b562`
- `FLTMGR!FltClose` at `0x14001b5ca`
- `FLTMGR!FltClose` at `0x14001af50`
- `FLTMGR!FltClose` at `0x14001b329`
- `FLTMGR!FltClose` at `0x14001b50d`
- `FLTMGR!FltClose` at `0x14001b562`
- `FLTMGR!FltClose` at `0x14001b5ca`

## string_xrefs

- `0x14001afc9`: `PUSH: Combine layerRootWithVolume, RelativePath`
- `0x14001b422`: `Cross-volume reparse failed; not attached to volume?`
- `0x14001b468`: `API: Failed opening source`
- `0x14001b47e`: `API: Failed opening relative source`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsEnumSource::AllocAndInit(
        struct _FLT_INSTANCE ***this,
        struct _UNICODE_STRING *Source,
        __int64 a3,
        struct _FLT_INSTANCE ***a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING a6,
        _WORD *EcpContext)
{
  struct _FLT_INSTANCE **v7; // rbx
  struct _FLT_INSTANCE *v12; // rcx
  struct _FLT_INSTANCE *v13; // rcx
  USHORT NormalizedLayerRootPath; // ax
  int v15; // esi
  NTSTATUS Parameter; // ebx
  struct _UNICODE_STRING *v17; // rdx
  struct _FLT_INSTANCE **v18; // rax
  struct _FLT_INSTANCE *v19; // rdi
  PVOID v20; // rcx
  const char *v21; // rax
  __int64 v22; // r8
  struct _ECP_LIST *v23; // r15
  PVOID v24; // rcx
  PFLT_FILTER *v25; // rcx
  PVOID v26; // rcx
  struct _FLT_INSTANCE **Pool2; // rax
  struct _FLT_INSTANCE **v28; // rbx
  struct _FLT_INSTANCE *v29; // r8
  PVOID v30; // r9
  PWSTR Buffer; // rcx
  struct _FLT_INSTANCE *v32; // rcx
  struct _FLT_INSTANCE *v33; // rcx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesb; // [rsp+28h] [rbp-D8h]
  PECP_LIST EcpList; // [rsp+80h] [rbp-80h] BYREF
  PVOID *p_Object; // [rsp+88h] [rbp-78h]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h] BYREF
  char v41; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING UnicodeString; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES v43; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v44[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v45; // [rsp+F0h] [rbp-10h]
  UNICODE_STRING SourceString; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT v48; // [rsp+118h] [rbp+18h] BYREF
  __int64 v49; // [rsp+138h] [rbp+38h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+140h] [rbp+40h] BYREF
  __int64 v51; // [rsp+160h] [rbp+60h]
  PVOID Object; // [rsp+1C8h] [rbp+C8h] BYREF

  v7 = *a4;
  *a4 = 0;
  if ( v7 )
  {
    v12 = v7[2];
    v7[2] = 0;
    if ( v12 )
      ObfDereferenceObject(v12);
    v13 = v7[1];
    if ( v13 )
      FltClose(v13);
    ExFreePoolWithTag(v7, 0);
  }
  UnicodeString = 0;
  memset(&v43, 0, sizeof(v43));
  SourceString = 0;
  NormalizedLayerRootPath = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(
                              (UnionFs::UfsLayerCtx *)this,
                              &SourceString,
                              1);
  v15 = (int)a5;
  a6.Length = NormalizedLayerRootPath;
  Parameter = UnionFs::Utils::CombinePath(&SourceString, Source, &UnicodeString, a5, &a6);
  if ( Parameter < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Parameter,
      v15,
      (struct UnionFs::StackEventTracer *)0x1B90004045ALL,
      (unsigned __int64)"UnionFs::UfsEnumSource::AllocAndInit",
      "PUSH: Combine layerRootWithVolume, RelativePath",
      ObjectAttributes);
    goto LABEL_59;
  }
  v43.Length = 48;
  v43.RootDirectory = 0;
  v43.ObjectName = &UnicodeString;
  v18 = this[1];
  v43.Attributes = 576;
  *(_OWORD *)&v43.SecurityDescriptor = 0;
  v19 = *v18;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v51 = a3;
  p_Object = &Object;
  Object = 0;
  v41 = 1;
  IoStatusBlock = 0;
  FileObject = 0;
  a6.Buffer = 0;
  Parameter = FltCreateFileEx2(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                v19,
                (PHANDLE)&a6.Buffer,
                &FileObject,
                0x80000000,
                &v43,
                &IoStatusBlock,
                0,
                0,
                3u,
                1u,
                0x200021u,
                0,
                0,
                0x800u,
                &DriverContext);
  if ( v41 )
  {
    v20 = *p_Object;
    *p_Object = FileObject;
    if ( v20 )
      ObfDereferenceObject(v20);
  }
  if ( (unsigned int)(Parameter + 1073740952) <= 1 )
  {
    EcpList = 0;
    Parameter = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
    if ( Parameter < 0 )
    {
      v21 = "API: Allocating ECP list";
      v22 = 0x1BD000404A1LL;
LABEL_15:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Parameter,
        v15,
        (struct UnionFs::StackEventTracer *)v22,
        (unsigned __int64)"UnionFs::UfsEnumSource::AllocAndInit",
        v21,
        ObjectAttributesa);
LABEL_54:
      v24 = Object;
      Object = 0;
      goto LABEL_55;
    }
    v23 = EcpList;
    EcpContext = 0;
    Parameter = FltAllocateExtraCreateParameter(
                  *(PFLT_FILTER *)UnionFs::g_FilterState,
                  &GUID_ECP_FLT_CREATEFILE_TARGET,
                  0x20u,
                  0,
                  0,
                  0x63654655u,
                  (PVOID *)&EcpContext);
    if ( Parameter < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Parameter,
        v15,
        (struct UnionFs::StackEventTracer *)0x1BE000404B0LL,
        (unsigned __int64)"UnionFs::UfsEnumSource::AllocAndInit",
        "API: Allocating targeting ECP",
        ObjectAttributesb);
LABEL_18:
      FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v23);
      v24 = Object;
      Object = 0;
LABEL_55:
      if ( v24 )
        ObfDereferenceObject(v24);
      if ( a6.Buffer )
        FltClose(a6.Buffer);
      goto LABEL_59;
    }
    v44[0] = EcpList;
    v45 = 1;
    v44[1] = EcpContext;
    EcpContext[12] = 1;
    v25 = (PFLT_FILTER *)UnionFs::g_FilterState;
    *(_QWORD *)EcpContext = 0;
    *((_QWORD *)EcpContext + 1) = 0;
    *((_QWORD *)EcpContext + 2) = 0;
    Parameter = FltInsertExtraCreateParameter(*v25, EcpList, EcpContext);
    if ( Parameter < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Parameter,
        v15,
        (struct UnionFs::StackEventTracer *)0x1BF000404DCLL,
        (unsigned __int64)"UnionFs::UfsEnumSource::AllocAndInit",
        "API: Inserting ECP",
        ObjectAttributesb);
      wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v44);
      goto LABEL_18;
    }
    v48.Size = 40;
    v49 = a3;
    v48.ExtraCreateParameter = EcpList;
    *(_DWORD *)(&v48.Size + 1) = 0;
    *(&v48.Size + 3) = 0;
    *(_OWORD *)&v48.DeviceObjectHint = 0;
    v43.Length = 48;
    v43.RootDirectory = 0;
    v43.Attributes = 576;
    *(_OWORD *)&v43.SecurityDescriptor = 0;
    if ( UnicodeString.Length )
      v43.ObjectName = &UnicodeString;
    else
      v43.ObjectName = Source;
    p_Object = &Object;
    FileObject = 0;
    v41 = 1;
    if ( a6.Buffer )
      FltClose(a6.Buffer);
    a6.Buffer = 0;
    Parameter = FltCreateFileEx2(
                  *(PFLT_FILTER *)UnionFs::g_FilterState,
                  v19,
                  (PHANDLE)&a6.Buffer,
                  &FileObject,
                  0x80000000,
                  &v43,
                  &IoStatusBlock,
                  0,
                  0,
                  3u,
                  1u,
                  0x200021u,
                  0,
                  0,
                  0,
                  &v48);
    if ( v41 )
    {
      v26 = *p_Object;
      *p_Object = FileObject;
      if ( v26 )
        ObfDereferenceObject(v26);
    }
    if ( Parameter < 0 )
    {
      if ( Parameter == -1073740951 || Parameter == -1073740952 )
        MicrosoftTelemetryAssertTriggeredMsgKM("Cross-volume reparse failed; not attached to volume?");
    }
    else if ( FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext) && *(_QWORD *)EcpContext )
    {
      v19 = *(struct _FLT_INSTANCE **)EcpContext;
    }
    wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(v44);
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v23);
  }
  if ( Parameter < 0 )
  {
    if ( UnicodeString.Length )
    {
      v22 = 0x1C00004051FLL;
      v21 = "API: Failed opening source";
    }
    else
    {
      v22 = 0x1C100040523LL;
      v21 = "API: Failed opening relative source";
    }
    goto LABEL_15;
  }
  Pool2 = (struct _FLT_INSTANCE **)ExAllocatePool2(258, 32, 1852130901);
  if ( !Pool2 )
  {
    Parameter = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      v15,
      (struct UnionFs::StackEventTracer *)0x1BC00040532LL,
      (unsigned __int64)"UnionFs::UfsEnumSource::AllocAndInit",
      "ORIGIN: Allocating UfsEnumSource",
      ObjectAttributesa);
    goto LABEL_54;
  }
  v28 = *a4;
  v17 = 0;
  v29 = (struct _FLT_INSTANCE *)Object;
  v30 = 0;
  Buffer = a6.Buffer;
  Object = 0;
  a6.Buffer = 0;
  *Pool2 = v19;
  Pool2[1] = (struct _FLT_INSTANCE *)Buffer;
  Pool2[2] = v29;
  Pool2[3] = (struct _FLT_INSTANCE *)this;
  *a4 = Pool2;
  if ( v28 )
  {
    v32 = v28[2];
    v28[2] = 0;
    if ( v32 )
      ObfDereferenceObject(v32);
    v33 = v28[1];
    if ( v33 )
      FltClose(v33);
    ExFreePoolWithTag(v28, 0);
    v17 = (struct _UNICODE_STRING *)a6.Buffer;
    v30 = Object;
  }
  Object = 0;
  if ( v30 )
  {
    ObfDereferenceObject(v30);
    v17 = (struct _UNICODE_STRING *)a6.Buffer;
  }
  if ( v17 )
    FltClose(v17);
  Parameter = 0;
LABEL_59:
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v17);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x14001aef4  mov     [rsp-8+arg_0], rbx
0x14001aef9  mov     [rsp-8+arg_10], r8
0x14001aefe  push    rbp
0x14001aeff  push    rsi
0x14001af00  push    rdi
0x14001af01  push    r12
0x14001af03  push    r13
0x14001af05  push    r14
0x14001af07  push    r15
0x14001af09  lea     rbp, [rsp-70h]
0x14001af0e  sub     rsp, 170h
0x14001af15  mov     rbx, [r9]
0x14001af18  xor     edi, edi
0x14001af1a  mov     [r9], rdi
0x14001af1d  mov     r14, r9
0x14001af20  mov     r15, r8
0x14001af23  mov     r12, rdx
0x14001af26  mov     r13, rcx
0x14001af29  test    rbx, rbx
0x14001af2c  jz      short loc_14001AF6D
0x14001af2e  mov     rcx, [rbx+10h]; Object
0x14001af32  mov     [rbx+10h], rdi
0x14001af36  test    rcx, rcx
0x14001af39  jz      short loc_14001AF47
0x14001af3b  call    cs:__imp_ObfDereferenceObject
0x14001af42  nop     dword ptr [rax+rax+00h]
0x14001af47  mov     rcx, [rbx+8]; FileHandle
0x14001af4b  test    rcx, rcx
0x14001af4e  jz      short loc_14001AF5C
0x14001af50  call    cs:__imp_FltClose
0x14001af57  nop     dword ptr [rax+rax+00h]
0x14001af5c  xor     edx, edx; Tag
0x14001af5e  mov     rcx, rbx; P
0x14001af61  call    cs:__imp_ExFreePoolWithTag
0x14001af68  nop     dword ptr [rax+rax+00h]
0x14001af6d  xorps   xmm0, xmm0
0x14001af70  lea     rdx, [rbp+0A0h+SourceString]; struct _UNICODE_STRING *
0x14001af74  xorps   xmm1, xmm1
0x14001af77  mov     r8b, 1; bool
0x14001af7a  mov     rcx, r13; this
0x14001af7d  movups  xmmword ptr [rbp+0A0h+UnicodeString.Length], xmm0
0x14001af81  movups  xmmword ptr [rbp+0A0h+var_F0.Length], xmm1
0x14001af85  movups  xmmword ptr [rbp+0A0h+var_F0.ObjectName], xmm1
0x14001af89  movups  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm1
0x14001af8d  movups  xmmword ptr [rbp+0A0h+SourceString.Length], xmm0
0x14001af91  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14001af96  mov     rsi, [rbp+0A0h+arg_20]
0x14001af9d  lea     r8, [rbp+0A0h+UnicodeString]; UnicodeString
0x14001afa1  mov     [rbp+0A0h+arg_28.Length], ax
0x14001afa8  lea     rcx, [rbp+0A0h+SourceString]; SourceString
0x14001afac  lea     rax, [rbp+0A0h+arg_28]
0x14001afb3  mov     r9, rsi; struct _UNICODE_STRING *
0x14001afb6  mov     rdx, r12; Source
0x14001afb9  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; struct _UNICODE_STRING *
0x14001afbe  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x14001afc3  mov     ebx, eax
0x14001afc5  test    eax, eax
0x14001afc7  jns     short loc_14001AFF5
0x14001afc9  lea     rax, aPushCombineLay; "PUSH: Combine layerRootWithVolume, Rela"...
0x14001afd0  mov     r8, 1B90004045Ah; struct UnionFs::StackEventTracer *
0x14001afda  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001afe1  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001afe6  mov     rdx, rsi; int
0x14001afe9  mov     ecx, ebx; this
0x14001afeb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001aff0  jmp     loc_14001B5D6
0x14001aff5  xorps   xmm0, xmm0
0x14001aff8  mov     [rbp+0A0h+var_F0.Length], 30h ; '0'
0x14001afff  mov     [rbp+0A0h+var_F0.RootDirectory], rdi
0x14001b003  lea     rax, [rbp+0A0h+UnicodeString]
0x14001b007  mov     [rbp+0A0h+var_F0.ObjectName], rax
0x14001b00b  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14001b00f  mov     rax, [r13+8]
0x14001b013  lea     r8, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b01a  mov     [rbp+0A0h+var_F0.Attributes], 240h
0x14001b021  xorps   xmm1, xmm1
0x14001b024  movdqu  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm0
0x14001b029  mov     rdi, [rax]
0x14001b02c  mov     eax, 28h ; '('
0x14001b031  movups  xmmword ptr [rbp+0A0h+var_60.Size], xmm1
0x14001b035  mov     [rbp+0A0h+var_60.Size], ax
0x14001b039  mov     rdx, rdi; Instance
0x14001b03c  mov     [rbp+0A0h+var_40], r15
0x14001b040  lea     rax, [rbp+0A0h+Object]
0x14001b047  xor     r15d, r15d
0x14001b04a  mov     [rbp+0A0h+var_118], rax
0x14001b04e  lea     rax, [rbp+0A0h+var_60]
0x14001b052  mov     [rbp+0A0h+Object], 0
0x14001b05d  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14001b062  lea     rax, [rbp+0A0h+var_98]
0x14001b066  mov     [rsp+1A0h+Flags], 800h; Flags
0x14001b06e  mov     [rsp+1A0h+EaLength], r15d; EaLength
0x14001b073  lea     ecx, [r15+1]
0x14001b077  mov     [rsp+1A0h+EaBuffer], r15; EaBuffer
0x14001b07c  mov     [rsp+1A0h+CreateOptions], 200021h; CreateOptions
0x14001b084  mov     [rsp+1A0h+CreateDisposition], ecx; CreateDisposition
0x14001b088  mov     [rsp+1A0h+ShareAccess], 3; ShareAccess
0x14001b090  mov     [rsp+1A0h+FileAttributes], r15d; FileAttributes
0x14001b095  mov     [rbp+0A0h+var_108], cl
0x14001b098  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b09f  mov     [rsp+1A0h+AllocationSize], r15; AllocationSize
0x14001b0a4  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x14001b0a9  lea     rax, [rbp+0A0h+var_F0]
0x14001b0ad  movups  xmmword ptr [rbp+0A0h+var_98], xmm0
0x14001b0b1  mov     [rbp+0A0h+FileObject], r15
0x14001b0b5  movups  xmmword ptr [rbp+0A0h+var_60.DeviceObjectHint], xmm1
0x14001b0b9  mov     [rbp+0A0h+arg_28.Buffer], r15
0x14001b0c0  mov     rcx, [rcx]; Filter
0x14001b0c3  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14001b0c8  mov     [rsp+1A0h+DesiredAccess], 80000000h; DesiredAccess
0x14001b0d0  call    cs:__imp_FltCreateFileEx2
0x14001b0d7  nop     dword ptr [rax+rax+00h]
0x14001b0dc  mov     ebx, eax
0x14001b0de  cmp     [rbp+0A0h+var_108], r15b
0x14001b0e2  jz      short loc_14001B103
0x14001b0e4  mov     r8, [rbp+0A0h+var_118]
0x14001b0e8  mov     rdx, [rbp+0A0h+FileObject]
0x14001b0ec  mov     rcx, [r8]; Object
0x14001b0ef  mov     [r8], rdx
0x14001b0f2  test    rcx, rcx
0x14001b0f5  jz      short loc_14001B103
0x14001b0f7  call    cs:__imp_ObfDereferenceObject
0x14001b0fe  nop     dword ptr [rax+rax+00h]
0x14001b103  lea     eax, [rbx+3FFFFC98h]
0x14001b109  cmp     eax, 1
0x14001b10c  ja      loc_14001B453
0x14001b112  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b119  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x14001b11d  xor     edx, edx; Flags
0x14001b11f  mov     [rbp+0A0h+EcpList], r15
0x14001b123  mov     rcx, [rcx]; Filter
0x14001b126  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14001b12d  nop     dword ptr [rax+rax+00h]
0x14001b132  mov     ebx, eax
0x14001b134  test    eax, eax
0x14001b136  jns     short loc_14001B164
0x14001b138  lea     rax, aApiAllocatingE; "API: Allocating ECP list"
0x14001b13f  mov     r8, 1BD000404A1h; struct UnionFs::StackEventTracer *
0x14001b149  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b150  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b155  mov     rdx, rsi; int
0x14001b158  mov     ecx, ebx; this
0x14001b15a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b15f  jmp     loc_14001B59F
0x14001b164  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b16b  lea     rax, [rbp+0A0h+EcpContext]
0x14001b172  mov     r15, [rbp+0A0h+EcpList]
0x14001b176  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14001b17d  mov     [rsp+1A0h+IoStatusBlock], rax; EcpContext
0x14001b182  xor     r9d, r9d; Flags
0x14001b185  mov     [rbp+0A0h+EcpContext], 0
0x14001b190  mov     rcx, [rcx]; Filter
0x14001b193  mov     dword ptr [rsp+1A0h+ObjectAttributes], 63654655h; char *
0x14001b19b  lea     r8d, [r9+20h]; SizeOfContext
0x14001b19f  mov     qword ptr [rsp+1A0h+DesiredAccess], 0; CleanupCallback
0x14001b1a8  call    cs:__imp_FltAllocateExtraCreateParameter
0x14001b1af  nop     dword ptr [rax+rax+00h]
0x14001b1b4  xor     edx, edx
0x14001b1b6  mov     ebx, eax
0x14001b1b8  test    eax, eax
0x14001b1ba  jns     short loc_14001B213
0x14001b1bc  lea     rax, aApiAllocatingT; "API: Allocating targeting ECP"
0x14001b1c3  mov     r8, 1BE000404B0h; struct UnionFs::StackEventTracer *
0x14001b1cd  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b1d4  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b1d9  mov     rdx, rsi; int
0x14001b1dc  mov     ecx, ebx; this
0x14001b1de  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b1e3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b1ea  mov     rdx, r15; EcpList
0x14001b1ed  mov     rcx, [rcx]; Filter
0x14001b1f0  call    cs:__imp_FltFreeExtraCreateParameterList
0x14001b1f7  nop     dword ptr [rax+rax+00h]
0x14001b1fc  mov     rcx, [rbp+0A0h+Object]
0x14001b203  mov     [rbp+0A0h+Object], 0
0x14001b20e  jmp     loc_14001B5AD
0x14001b213  mov     rax, [rbp+0A0h+EcpList]
0x14001b217  mov     rcx, [rbp+0A0h+EcpContext]
0x14001b21e  mov     [rbp+0A0h+var_C0], rax
0x14001b222  mov     eax, 1
0x14001b227  mov     [rbp+0A0h+var_B0], al
0x14001b22a  mov     [rbp+0A0h+var_B8], rcx
0x14001b22e  mov     [rcx+18h], ax
0x14001b232  mov     rax, [rbp+0A0h+EcpContext]
0x14001b239  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b240  mov     [rax], rdx
0x14001b243  mov     rax, [rbp+0A0h+EcpContext]
0x14001b24a  mov     [rax+8], rdx
0x14001b24e  mov     rax, [rbp+0A0h+EcpContext]
0x14001b255  mov     [rax+10h], rdx
0x14001b259  mov     r8, [rbp+0A0h+EcpContext]; EcpContext
0x14001b260  mov     rdx, [rbp+0A0h+EcpList]; EcpList
0x14001b264  mov     rcx, [rcx]; Filter
0x14001b267  call    cs:__imp_FltInsertExtraCreateParameter
0x14001b26e  nop     dword ptr [rax+rax+00h]
0x14001b273  xor     edx, edx
0x14001b275  mov     ebx, eax
0x14001b277  test    eax, eax
0x14001b279  jns     short loc_14001B2B0
0x14001b27b  lea     rax, aApiInsertingEc; "API: Inserting ECP"
0x14001b282  mov     r8, 1BF000404DCh; struct UnionFs::StackEventTracer *
0x14001b28c  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b293  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b298  mov     rdx, rsi; int
0x14001b29b  mov     ecx, ebx; this
0x14001b29d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b2a2  lea     rcx, [rbp+0A0h+var_C0]
0x14001b2a6  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x14001b2ab  jmp     loc_14001B1E3
0x14001b2b0  mov     eax, 28h ; '('
0x14001b2b5  xorps   xmm0, xmm0
0x14001b2b8  mov     [rbp+0A0h+var_88.Size], ax
0x14001b2bc  mov     rax, [rbp+0A0h+arg_10]
0x14001b2c3  mov     [rbp+0A0h+var_68], rax
0x14001b2c7  mov     rax, [rbp+0A0h+EcpList]
0x14001b2cb  mov     [rbp+0A0h+var_88.ExtraCreateParameter], rax
0x14001b2cf  mov     dword ptr [rbp+0A0h+var_88+2], edx
0x14001b2d2  mov     word ptr [rbp+0A0h+var_88+6], dx
0x14001b2d6  movdqu  xmmword ptr [rbp+0A0h+var_88.DeviceObjectHint], xmm0
0x14001b2db  mov     [rbp+0A0h+var_F0.Length], 30h ; '0'
0x14001b2e2  mov     [rbp+0A0h+var_F0.RootDirectory], rdx
0x14001b2e6  mov     [rbp+0A0h+var_F0.Attributes], 240h
0x14001b2ed  movdqu  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm0
0x14001b2f2  cmp     [rbp+0A0h+UnicodeString.Length], dx
0x14001b2f6  jbe     short loc_14001B302
0x14001b2f8  lea     rax, [rbp+0A0h+UnicodeString]
0x14001b2fc  mov     [rbp+0A0h+var_F0.ObjectName], rax
0x14001b300  jmp     short loc_14001B306
0x14001b302  mov     [rbp+0A0h+var_F0.ObjectName], r12
0x14001b306  mov     rcx, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b30d  lea     rax, [rbp+0A0h+Object]
0x14001b314  mov     [rbp+0A0h+var_118], rax
0x14001b318  mov     ebx, 1
0x14001b31d  mov     [rbp+0A0h+FileObject], rdx
0x14001b321  mov     [rbp+0A0h+var_108], bl
0x14001b324  test    rcx, rcx
0x14001b327  jz      short loc_14001B337
0x14001b329  call    cs:__imp_FltClose
0x14001b330  nop     dword ptr [rax+rax+00h]
0x14001b335  xor     edx, edx
0x14001b337  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b33e  lea     rax, [rbp+0A0h+var_88]
0x14001b342  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14001b347  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14001b34b  mov     [rsp+1A0h+Flags], edx; Flags
0x14001b34f  lea     rax, [rbp+0A0h+var_98]
0x14001b353  mov     [rsp+1A0h+EaLength], edx; EaLength
0x14001b357  lea     r8, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b35e  mov     [rsp+1A0h+EaBuffer], rdx; EaBuffer
0x14001b363  mov     [rsp+1A0h+CreateOptions], 200021h; CreateOptions
0x14001b36b  mov     [rsp+1A0h+CreateDisposition], ebx; CreateDisposition
0x14001b36f  mov     [rsp+1A0h+ShareAccess], 3; ShareAccess
0x14001b377  mov     [rsp+1A0h+FileAttributes], edx; FileAttributes
0x14001b37b  mov     [rsp+1A0h+AllocationSize], rdx; AllocationSize
0x14001b380  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x14001b385  lea     rax, [rbp+0A0h+var_F0]
0x14001b389  mov     [rbp+0A0h+arg_28.Buffer], rdx
0x14001b390  mov     rdx, rdi; Instance
0x14001b393  mov     rcx, [rcx]; Filter
0x14001b396  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14001b39b  mov     [rsp+1A0h+DesiredAccess], 80000000h; DesiredAccess
0x14001b3a3  call    cs:__imp_FltCreateFileEx2
0x14001b3aa  nop     dword ptr [rax+rax+00h]
0x14001b3af  xor     r12d, r12d
0x14001b3b2  mov     ebx, eax
0x14001b3b4  cmp     [rbp+0A0h+var_108], r12b
0x14001b3b8  jz      short loc_14001B3D9
0x14001b3ba  mov     rdx, [rbp+0A0h+var_118]
0x14001b3be  mov     rax, [rbp+0A0h+FileObject]
0x14001b3c2  mov     rcx, [rdx]; Object
0x14001b3c5  mov     [rdx], rax
0x14001b3c8  test    rcx, rcx
0x14001b3cb  jz      short loc_14001B3D9
0x14001b3cd  call    cs:__imp_ObfDereferenceObject
0x14001b3d4  nop     dword ptr [rax+rax+00h]
0x14001b3d9  test    ebx, ebx
0x14001b3db  js      short loc_14001B412
0x14001b3dd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b3e4  mov     rdx, [rbp+0A0h+EcpContext]; EcpContext
0x14001b3eb  mov     rcx, [rcx]; Filter
0x14001b3ee  call    cs:__imp_FltIsEcpAcknowledged
0x14001b3f5  nop     dword ptr [rax+rax+00h]
0x14001b3fa  test    al, al
0x14001b3fc  jz      short loc_14001B42E
0x14001b3fe  mov     rax, [rbp+0A0h+EcpContext]
0x14001b405  mov     rcx, [rax]
0x14001b408  test    rcx, rcx
0x14001b40b  jz      short loc_14001B42E
0x14001b40d  mov     rdi, rcx
0x14001b410  jmp     short loc_14001B42E
0x14001b412  cmp     ebx, 0C0000369h
0x14001b418  jz      short loc_14001B422
0x14001b41a  cmp     ebx, 0C0000368h
0x14001b420  jnz     short loc_14001B42E
0x14001b422  lea     rcx, aCrossVolumeRep; "Cross-volume reparse failed; not attach"...
0x14001b429  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001b42e  lea     rcx, [rbp+0A0h+var_C0]
0x14001b432  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x14001b437  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b43e  mov     rdx, r15; EcpList
  ... truncated ...
```
