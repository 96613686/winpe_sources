# UnionFs::UfsEnumSource::AllocAndInit(UnionFs::UfsLayerCtx const &,_UNICODE_STRING const &,_EJOB const &,utl::unique_ptr<UnionFs::UfsEnumSource,utl::default_delete<UnionFs::UfsEnumSource>> &,UnionFs::StackEventTracer &,ulong,_FLT_INSTANCE const *,void *)

- ea: `0x14001af94`
- end: `0x14001b69d`
- name: `?AllocAndInit@UfsEnumSource@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_UNICODE_STRING@@AEBU_EJOB@@AEAV?$unique_ptr@VUfsEnumSource@UnionFs@@U?$default_delete@VUfsEnumSource@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@KPEBU_FLT_INSTANCE@@PEAX@Z`
- size: `1801`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsLayerCtx *this@<rcx>, PCUNICODE_STRING Source@<rdx>, struct _UNICODE_STRING *, struct _UNICODE_STRING, PVOID EcpContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025208`

## callees

- `0x14001abe4`
- `0x14001af94`
- `0x140036268`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14006a5bc`
- `0x140079f68`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001b001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b5be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b5be`
- `ntoskrnl!ExAllocatePool2` at `0x14001b53a`
- `ntoskrnl!ExAllocatePool2` at `0x14001b53a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001afdb`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b197`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b46d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b598`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5e7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b652`
- `ntoskrnl!ObfDereferenceObject` at `0x14001afdb`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b197`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b46d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b598`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5e7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b652`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001b1c6`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001b1c6`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b290`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b4e4`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b290`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001b4e4`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001b307`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001b307`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001b248`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001b248`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001b48e`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001b48e`
- `FLTMGR!FltCreateFileEx2` at `0x14001b170`
- `FLTMGR!FltCreateFileEx2` at `0x14001b443`
- `FLTMGR!FltCreateFileEx2` at `0x14001b170`
- `FLTMGR!FltCreateFileEx2` at `0x14001b443`
- `FLTMGR!FltClose` at `0x14001aff0`
- `FLTMGR!FltClose` at `0x14001b3c9`
- `FLTMGR!FltClose` at `0x14001b5ad`
- `FLTMGR!FltClose` at `0x14001b602`
- `FLTMGR!FltClose` at `0x14001b66a`
- `FLTMGR!FltClose` at `0x14001aff0`
- `FLTMGR!FltClose` at `0x14001b3c9`
- `FLTMGR!FltClose` at `0x14001b5ad`
- `FLTMGR!FltClose` at `0x14001b602`
- `FLTMGR!FltClose` at `0x14001b66a`

## string_xrefs

- `0x14001b069`: `PUSH: Combine layerRootWithVolume, RelativePath`
- `0x14001b4c2`: `Cross-volume reparse failed; not attached to volume?`
- `0x14001b508`: `API: Failed opening source`
- `0x14001b51e`: `API: Failed opening relative source`

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
0x14001af94  mov     [rsp-8+arg_0], rbx
0x14001af99  mov     [rsp-8+arg_10], r8
0x14001af9e  push    rbp
0x14001af9f  push    rsi
0x14001afa0  push    rdi
0x14001afa1  push    r12
0x14001afa3  push    r13
0x14001afa5  push    r14
0x14001afa7  push    r15
0x14001afa9  lea     rbp, [rsp-70h]
0x14001afae  sub     rsp, 170h
0x14001afb5  mov     rbx, [r9]
0x14001afb8  xor     edi, edi
0x14001afba  mov     [r9], rdi
0x14001afbd  mov     r14, r9
0x14001afc0  mov     r15, r8
0x14001afc3  mov     r12, rdx
0x14001afc6  mov     r13, rcx
0x14001afc9  test    rbx, rbx
0x14001afcc  jz      short loc_14001B00D
0x14001afce  mov     rcx, [rbx+10h]; Object
0x14001afd2  mov     [rbx+10h], rdi
0x14001afd6  test    rcx, rcx
0x14001afd9  jz      short loc_14001AFE7
0x14001afdb  call    cs:__imp_ObfDereferenceObject
0x14001afe2  nop     dword ptr [rax+rax+00h]
0x14001afe7  mov     rcx, [rbx+8]; FileHandle
0x14001afeb  test    rcx, rcx
0x14001afee  jz      short loc_14001AFFC
0x14001aff0  call    cs:__imp_FltClose
0x14001aff7  nop     dword ptr [rax+rax+00h]
0x14001affc  xor     edx, edx; Tag
0x14001affe  mov     rcx, rbx; P
0x14001b001  call    cs:__imp_ExFreePoolWithTag
0x14001b008  nop     dword ptr [rax+rax+00h]
0x14001b00d  xorps   xmm0, xmm0
0x14001b010  lea     rdx, [rbp+0A0h+SourceString]; struct _UNICODE_STRING *
0x14001b014  xorps   xmm1, xmm1
0x14001b017  mov     r8b, 1; bool
0x14001b01a  mov     rcx, r13; this
0x14001b01d  movups  xmmword ptr [rbp+0A0h+UnicodeString.Length], xmm0
0x14001b021  movups  xmmword ptr [rbp+0A0h+var_F0.Length], xmm1
0x14001b025  movups  xmmword ptr [rbp+0A0h+var_F0.ObjectName], xmm1
0x14001b029  movups  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm1
0x14001b02d  movups  xmmword ptr [rbp+0A0h+SourceString.Length], xmm0
0x14001b031  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14001b036  mov     rsi, [rbp+0A0h+arg_20]
0x14001b03d  lea     r8, [rbp+0A0h+UnicodeString]; UnicodeString
0x14001b041  mov     [rbp+0A0h+arg_28.Length], ax
0x14001b048  lea     rcx, [rbp+0A0h+SourceString]; SourceString
0x14001b04c  lea     rax, [rbp+0A0h+arg_28]
0x14001b053  mov     r9, rsi; struct _UNICODE_STRING *
0x14001b056  mov     rdx, r12; Source
0x14001b059  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; struct _UNICODE_STRING *
0x14001b05e  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x14001b063  mov     ebx, eax
0x14001b065  test    eax, eax
0x14001b067  jns     short loc_14001B095
0x14001b069  lea     rax, aPushCombineLay; "PUSH: Combine layerRootWithVolume, Rela"...
0x14001b070  mov     r8, 1B90004045Ah; struct UnionFs::StackEventTracer *
0x14001b07a  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b081  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b086  mov     rdx, rsi; int
0x14001b089  mov     ecx, ebx; this
0x14001b08b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b090  jmp     loc_14001B676
0x14001b095  xorps   xmm0, xmm0
0x14001b098  mov     [rbp+0A0h+var_F0.Length], 30h ; '0'
0x14001b09f  mov     [rbp+0A0h+var_F0.RootDirectory], rdi
0x14001b0a3  lea     rax, [rbp+0A0h+UnicodeString]
0x14001b0a7  mov     [rbp+0A0h+var_F0.ObjectName], rax
0x14001b0ab  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14001b0af  mov     rax, [r13+8]
0x14001b0b3  lea     r8, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b0ba  mov     [rbp+0A0h+var_F0.Attributes], 240h
0x14001b0c1  xorps   xmm1, xmm1
0x14001b0c4  movdqu  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm0
0x14001b0c9  mov     rdi, [rax]
0x14001b0cc  mov     eax, 28h ; '('
0x14001b0d1  movups  xmmword ptr [rbp+0A0h+var_60.Size], xmm1
0x14001b0d5  mov     [rbp+0A0h+var_60.Size], ax
0x14001b0d9  mov     rdx, rdi; Instance
0x14001b0dc  mov     [rbp+0A0h+var_40], r15
0x14001b0e0  lea     rax, [rbp+0A0h+Object]
0x14001b0e7  xor     r15d, r15d
0x14001b0ea  mov     [rbp+0A0h+var_118], rax
0x14001b0ee  lea     rax, [rbp+0A0h+var_60]
0x14001b0f2  mov     [rbp+0A0h+Object], 0
0x14001b0fd  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14001b102  lea     rax, [rbp+0A0h+var_98]
0x14001b106  mov     [rsp+1A0h+Flags], 800h; Flags
0x14001b10e  mov     [rsp+1A0h+EaLength], r15d; EaLength
0x14001b113  lea     ecx, [r15+1]
0x14001b117  mov     [rsp+1A0h+EaBuffer], r15; EaBuffer
0x14001b11c  mov     [rsp+1A0h+CreateOptions], 200021h; CreateOptions
0x14001b124  mov     [rsp+1A0h+CreateDisposition], ecx; CreateDisposition
0x14001b128  mov     [rsp+1A0h+ShareAccess], 3; ShareAccess
0x14001b130  mov     [rsp+1A0h+FileAttributes], r15d; FileAttributes
0x14001b135  mov     [rbp+0A0h+var_108], cl
0x14001b138  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b13f  mov     [rsp+1A0h+AllocationSize], r15; AllocationSize
0x14001b144  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x14001b149  lea     rax, [rbp+0A0h+var_F0]
0x14001b14d  movups  xmmword ptr [rbp+0A0h+var_98], xmm0
0x14001b151  mov     [rbp+0A0h+FileObject], r15
0x14001b155  movups  xmmword ptr [rbp+0A0h+var_60.DeviceObjectHint], xmm1
0x14001b159  mov     [rbp+0A0h+arg_28.Buffer], r15
0x14001b160  mov     rcx, [rcx]; Filter
0x14001b163  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14001b168  mov     [rsp+1A0h+DesiredAccess], 80000000h; DesiredAccess
0x14001b170  call    cs:__imp_FltCreateFileEx2
0x14001b177  nop     dword ptr [rax+rax+00h]
0x14001b17c  mov     ebx, eax
0x14001b17e  cmp     [rbp+0A0h+var_108], r15b
0x14001b182  jz      short loc_14001B1A3
0x14001b184  mov     r8, [rbp+0A0h+var_118]
0x14001b188  mov     rdx, [rbp+0A0h+FileObject]
0x14001b18c  mov     rcx, [r8]; Object
0x14001b18f  mov     [r8], rdx
0x14001b192  test    rcx, rcx
0x14001b195  jz      short loc_14001B1A3
0x14001b197  call    cs:__imp_ObfDereferenceObject
0x14001b19e  nop     dword ptr [rax+rax+00h]
0x14001b1a3  lea     eax, [rbx+3FFFFC98h]
0x14001b1a9  cmp     eax, 1
0x14001b1ac  ja      loc_14001B4F3
0x14001b1b2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b1b9  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x14001b1bd  xor     edx, edx; Flags
0x14001b1bf  mov     [rbp+0A0h+EcpList], r15
0x14001b1c3  mov     rcx, [rcx]; Filter
0x14001b1c6  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14001b1cd  nop     dword ptr [rax+rax+00h]
0x14001b1d2  mov     ebx, eax
0x14001b1d4  test    eax, eax
0x14001b1d6  jns     short loc_14001B204
0x14001b1d8  lea     rax, aApiAllocatingE; "API: Allocating ECP list"
0x14001b1df  mov     r8, 1BD000404A1h; struct UnionFs::StackEventTracer *
0x14001b1e9  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b1f0  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b1f5  mov     rdx, rsi; int
0x14001b1f8  mov     ecx, ebx; this
0x14001b1fa  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b1ff  jmp     loc_14001B63F
0x14001b204  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b20b  lea     rax, [rbp+0A0h+EcpContext]
0x14001b212  mov     r15, [rbp+0A0h+EcpList]
0x14001b216  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14001b21d  mov     [rsp+1A0h+IoStatusBlock], rax; EcpContext
0x14001b222  xor     r9d, r9d; Flags
0x14001b225  mov     [rbp+0A0h+EcpContext], 0
0x14001b230  mov     rcx, [rcx]; Filter
0x14001b233  mov     dword ptr [rsp+1A0h+ObjectAttributes], 63654655h; char *
0x14001b23b  lea     r8d, [r9+20h]; SizeOfContext
0x14001b23f  mov     qword ptr [rsp+1A0h+DesiredAccess], 0; CleanupCallback
0x14001b248  call    cs:__imp_FltAllocateExtraCreateParameter
0x14001b24f  nop     dword ptr [rax+rax+00h]
0x14001b254  xor     edx, edx
0x14001b256  mov     ebx, eax
0x14001b258  test    eax, eax
0x14001b25a  jns     short loc_14001B2B3
0x14001b25c  lea     rax, aApiAllocatingT; "API: Allocating targeting ECP"
0x14001b263  mov     r8, 1BE000404B0h; struct UnionFs::StackEventTracer *
0x14001b26d  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b274  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b279  mov     rdx, rsi; int
0x14001b27c  mov     ecx, ebx; this
0x14001b27e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b283  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b28a  mov     rdx, r15; EcpList
0x14001b28d  mov     rcx, [rcx]; Filter
0x14001b290  call    cs:__imp_FltFreeExtraCreateParameterList
0x14001b297  nop     dword ptr [rax+rax+00h]
0x14001b29c  mov     rcx, [rbp+0A0h+Object]
0x14001b2a3  mov     [rbp+0A0h+Object], 0
0x14001b2ae  jmp     loc_14001B64D
0x14001b2b3  mov     rax, [rbp+0A0h+EcpList]
0x14001b2b7  mov     rcx, [rbp+0A0h+EcpContext]
0x14001b2be  mov     [rbp+0A0h+var_C0], rax
0x14001b2c2  mov     eax, 1
0x14001b2c7  mov     [rbp+0A0h+var_B0], al
0x14001b2ca  mov     [rbp+0A0h+var_B8], rcx
0x14001b2ce  mov     [rcx+18h], ax
0x14001b2d2  mov     rax, [rbp+0A0h+EcpContext]
0x14001b2d9  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b2e0  mov     [rax], rdx
0x14001b2e3  mov     rax, [rbp+0A0h+EcpContext]
0x14001b2ea  mov     [rax+8], rdx
0x14001b2ee  mov     rax, [rbp+0A0h+EcpContext]
0x14001b2f5  mov     [rax+10h], rdx
0x14001b2f9  mov     r8, [rbp+0A0h+EcpContext]; EcpContext
0x14001b300  mov     rdx, [rbp+0A0h+EcpList]; EcpList
0x14001b304  mov     rcx, [rcx]; Filter
0x14001b307  call    cs:__imp_FltInsertExtraCreateParameter
0x14001b30e  nop     dword ptr [rax+rax+00h]
0x14001b313  xor     edx, edx
0x14001b315  mov     ebx, eax
0x14001b317  test    eax, eax
0x14001b319  jns     short loc_14001B350
0x14001b31b  lea     rax, aApiInsertingEc; "API: Inserting ECP"
0x14001b322  mov     r8, 1BF000404DCh; struct UnionFs::StackEventTracer *
0x14001b32c  lea     r9, aUnionfsUfsenum_2; "UnionFs::UfsEnumSource::AllocAndInit"
0x14001b333  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14001b338  mov     rdx, rsi; int
0x14001b33b  mov     ecx, ebx; this
0x14001b33d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b342  lea     rcx, [rbp+0A0h+var_C0]
0x14001b346  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x14001b34b  jmp     loc_14001B283
0x14001b350  mov     eax, 28h ; '('
0x14001b355  xorps   xmm0, xmm0
0x14001b358  mov     [rbp+0A0h+var_88.Size], ax
0x14001b35c  mov     rax, [rbp+0A0h+arg_10]
0x14001b363  mov     [rbp+0A0h+var_68], rax
0x14001b367  mov     rax, [rbp+0A0h+EcpList]
0x14001b36b  mov     [rbp+0A0h+var_88.ExtraCreateParameter], rax
0x14001b36f  mov     dword ptr [rbp+0A0h+var_88+2], edx
0x14001b372  mov     word ptr [rbp+0A0h+var_88+6], dx
0x14001b376  movdqu  xmmword ptr [rbp+0A0h+var_88.DeviceObjectHint], xmm0
0x14001b37b  mov     [rbp+0A0h+var_F0.Length], 30h ; '0'
0x14001b382  mov     [rbp+0A0h+var_F0.RootDirectory], rdx
0x14001b386  mov     [rbp+0A0h+var_F0.Attributes], 240h
0x14001b38d  movdqu  xmmword ptr [rbp+0A0h+var_F0.SecurityDescriptor], xmm0
0x14001b392  cmp     [rbp+0A0h+UnicodeString.Length], dx
0x14001b396  jbe     short loc_14001B3A2
0x14001b398  lea     rax, [rbp+0A0h+UnicodeString]
0x14001b39c  mov     [rbp+0A0h+var_F0.ObjectName], rax
0x14001b3a0  jmp     short loc_14001B3A6
0x14001b3a2  mov     [rbp+0A0h+var_F0.ObjectName], r12
0x14001b3a6  mov     rcx, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b3ad  lea     rax, [rbp+0A0h+Object]
0x14001b3b4  mov     [rbp+0A0h+var_118], rax
0x14001b3b8  mov     ebx, 1
0x14001b3bd  mov     [rbp+0A0h+FileObject], rdx
0x14001b3c1  mov     [rbp+0A0h+var_108], bl
0x14001b3c4  test    rcx, rcx
0x14001b3c7  jz      short loc_14001B3D7
0x14001b3c9  call    cs:__imp_FltClose
0x14001b3d0  nop     dword ptr [rax+rax+00h]
0x14001b3d5  xor     edx, edx
0x14001b3d7  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b3de  lea     rax, [rbp+0A0h+var_88]
0x14001b3e2  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14001b3e7  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14001b3eb  mov     [rsp+1A0h+Flags], edx; Flags
0x14001b3ef  lea     rax, [rbp+0A0h+var_98]
0x14001b3f3  mov     [rsp+1A0h+EaLength], edx; EaLength
0x14001b3f7  lea     r8, [rbp+0A0h+arg_28.Buffer]; FileHandle
0x14001b3fe  mov     [rsp+1A0h+EaBuffer], rdx; EaBuffer
0x14001b403  mov     [rsp+1A0h+CreateOptions], 200021h; CreateOptions
0x14001b40b  mov     [rsp+1A0h+CreateDisposition], ebx; CreateDisposition
0x14001b40f  mov     [rsp+1A0h+ShareAccess], 3; ShareAccess
0x14001b417  mov     [rsp+1A0h+FileAttributes], edx; FileAttributes
0x14001b41b  mov     [rsp+1A0h+AllocationSize], rdx; AllocationSize
0x14001b420  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x14001b425  lea     rax, [rbp+0A0h+var_F0]
0x14001b429  mov     [rbp+0A0h+arg_28.Buffer], rdx
0x14001b430  mov     rdx, rdi; Instance
0x14001b433  mov     rcx, [rcx]; Filter
0x14001b436  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14001b43b  mov     [rsp+1A0h+DesiredAccess], 80000000h; DesiredAccess
0x14001b443  call    cs:__imp_FltCreateFileEx2
0x14001b44a  nop     dword ptr [rax+rax+00h]
0x14001b44f  xor     r12d, r12d
0x14001b452  mov     ebx, eax
0x14001b454  cmp     [rbp+0A0h+var_108], r12b
0x14001b458  jz      short loc_14001B479
0x14001b45a  mov     rdx, [rbp+0A0h+var_118]
0x14001b45e  mov     rax, [rbp+0A0h+FileObject]
0x14001b462  mov     rcx, [rdx]; Object
0x14001b465  mov     [rdx], rax
0x14001b468  test    rcx, rcx
0x14001b46b  jz      short loc_14001B479
0x14001b46d  call    cs:__imp_ObfDereferenceObject
0x14001b474  nop     dword ptr [rax+rax+00h]
0x14001b479  test    ebx, ebx
0x14001b47b  js      short loc_14001B4B2
0x14001b47d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b484  mov     rdx, [rbp+0A0h+EcpContext]; EcpContext
0x14001b48b  mov     rcx, [rcx]; Filter
0x14001b48e  call    cs:__imp_FltIsEcpAcknowledged
0x14001b495  nop     dword ptr [rax+rax+00h]
0x14001b49a  test    al, al
0x14001b49c  jz      short loc_14001B4CE
0x14001b49e  mov     rax, [rbp+0A0h+EcpContext]
0x14001b4a5  mov     rcx, [rax]
0x14001b4a8  test    rcx, rcx
0x14001b4ab  jz      short loc_14001B4CE
0x14001b4ad  mov     rdi, rcx
0x14001b4b0  jmp     short loc_14001B4CE
0x14001b4b2  cmp     ebx, 0C0000369h
0x14001b4b8  jz      short loc_14001B4C2
0x14001b4ba  cmp     ebx, 0C0000368h
0x14001b4c0  jnz     short loc_14001B4CE
0x14001b4c2  lea     rcx, aCrossVolumeRep; "Cross-volume reparse failed; not attach"...
0x14001b4c9  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001b4ce  lea     rcx, [rbp+0A0h+var_C0]
0x14001b4d2  call    wil__details__lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb______lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___
0x14001b4d7  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b4de  mov     rdx, r15; EcpList
  ... truncated ...
```
