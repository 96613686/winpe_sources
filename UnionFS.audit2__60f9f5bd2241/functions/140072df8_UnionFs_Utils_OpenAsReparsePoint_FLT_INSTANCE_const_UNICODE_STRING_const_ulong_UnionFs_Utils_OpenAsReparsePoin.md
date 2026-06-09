# UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)

- ea: `0x140072df8`
- end: `0x14007321d`
- name: `?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z`
- size: `1061`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x140062a64`
- `0x14006c3ec`

## callees

- `0x140056bd0`
- `0x140056c7c`
- `0x140070e78`
- `0x140072df8`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x14007305a`
- `ntoskrnl!PsGetHostSilo` at `0x14007305a`
- `ntoskrnl!ObfDereferenceObject` at `0x140072e4f`
- `ntoskrnl!ObfDereferenceObject` at `0x140073153`
- `ntoskrnl!ObfDereferenceObject` at `0x140072e4f`
- `ntoskrnl!ObfDereferenceObject` at `0x140073153`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140072f16`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140072f16`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140072e6f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140072e6f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400731f3`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400731f3`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140072fa3`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140072fa3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072f47`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072ff5`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072f47`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072ff5`
- `FLTMGR!FltCreateFileEx2` at `0x14007312c`
- `FLTMGR!FltCreateFileEx2` at `0x14007312c`
- `FLTMGR!FltClose` at `0x140072e31`
- `FLTMGR!FltClose` at `0x1400730b6`
- `FLTMGR!FltClose` at `0x140072e31`
- `FLTMGR!FltClose` at `0x1400730b6`

## string_xrefs

- `0x140072e87`: `API: FltAllocateExtraCreateParameterList`
- `0x140073001`: `PUSH: Preparing QUERY_ON_CREATE ECP`
- `0x140072e8e`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x14007317e`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x1400731cf`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x1400731be`: `PUSH: Getting QUERY_ON_CREATE info`
- `0x140073177`: `API: Opening file`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::OpenAsReparsePoint(
        struct _FLT_INSTANCE *a1,
        struct _UNICODE_STRING *a2,
        ACCESS_MASK a3,
        unsigned int a4,
        PVOID a5,
        __int64 a6,
        __int64 *a7,
        void *a8)
{
  char *v8; // rdi
  void *v11; // rcx
  NTSTATUS Parameter; // ebx
  struct _ECP_LIST *v13; // rcx
  char v14; // r14
  struct _ECP_LIST *v15; // r12
  struct _FLT_FILTER *v16; // rcx
  PVOID v17; // rdx
  const char *v18; // rax
  __int64 v19; // r8
  int v20; // edi
  const char *v21; // rax
  __int64 v22; // r8
  int v23; // edx
  __int64 HostSilo; // rax
  void *v25; // rcx
  PFLT_FILTER *v26; // rcx
  PVOID v27; // rcx
  const char *LookasideList; // [rsp+30h] [rbp-D8h]
  const char *LookasideLista; // [rsp+30h] [rbp-D8h]
  const char *LookasideListb; // [rsp+30h] [rbp-D8h]
  PECP_LIST EcpList; // [rsp+88h] [rbp-80h] BYREF
  PVOID *v33; // [rsp+90h] [rbp-78h]
  PVOID EcpContext; // [rsp+98h] [rbp-70h] BYREF
  char v35; // [rsp+A0h] [rbp-68h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-8h] BYREF

  v8 = (char *)a5;
  if ( *(_QWORD *)a5 )
    FltClose(*(HANDLE *)a5);
  *(_QWORD *)v8 = 0;
  v11 = (void *)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 1) = 0;
  if ( v11 )
    ObfDereferenceObject(v11);
  EcpList = 0;
  Parameter = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( Parameter >= 0 )
  {
    v13 = EcpList;
    v14 = 0;
    v15 = EcpList;
    if ( (a4 & 6) != 0 )
    {
      a5 = 0;
      EcpContext = 0;
      v33 = &a5;
      v16 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
      v35 = 1;
      Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                    v16,
                    &GUID_ECP_QUERY_ON_CREATE,
                    0xC8u,
                    0,
                    UnionFs::Utils::QoCEcpCleanupCallback,
                    (char *)UnionFs::g_FilterState + 2240,
                    &EcpContext);
      if ( v35 )
      {
        v17 = *v33;
        *v33 = EcpContext;
        if ( v17 )
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v17);
      }
      if ( Parameter < 0 )
      {
        v18 = "API: Allocating QoC ECP";
        v19 = 0x305002120E0LL;
LABEL_19:
        v20 = a6;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)Parameter,
          a6,
          (struct UnionFs::StackEventTracer *)v19,
          (unsigned __int64)"UnionFs::Utils::PrepareQoCEcp",
          v18,
          LookasideLista);
        if ( a5 )
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, a5);
        v21 = "PUSH: Preparing QUERY_ON_CREATE ECP";
        v22 = 0x10900212155LL;
        v23 = v20;
        goto LABEL_38;
      }
      memset(a5, 0, 0xC8u);
      if ( (a4 & 2) != 0 )
        *(_DWORD *)a5 |= 1u;
      if ( (a4 & 4) != 0 )
        *(_DWORD *)a5 |= 4u;
      Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v15, a5);
      if ( Parameter < 0 )
      {
        v18 = "API: Inserting QoC ECP";
        v19 = 0x30F002120F4LL;
        goto LABEL_19;
      }
      v13 = EcpList;
      v14 = 1;
      a5 = 0;
    }
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    DriverContext.Size = 40;
    *(&DriverContext.Size + 3) = 0;
    v37 = 1;
    DriverContext.ExtraCreateParameter = v13;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    if ( a7 )
      HostSilo = *a7;
    else
      HostSilo = PsGetHostSilo(v13, 0);
    v25 = *(void **)v8;
    v37 = HostSilo;
    ObjectAttributes.RootDirectory = a8;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes + 1, 0, 20);
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.Attributes = (((a4 & 1) == 0) + 8) << 6;
    v33 = (PVOID *)(v8 + 8);
    EcpContext = 0;
    v35 = 1;
    IoStatusBlock = 0;
    if ( v25 )
      FltClose(v25);
    v26 = (PFLT_FILTER *)UnionFs::g_FilterState;
    *(_QWORD *)v8 = 0;
    Parameter = FltCreateFileEx2(
                  *v26,
                  a1,
                  (PHANDLE)v8,
                  (PFILE_OBJECT *)&EcpContext,
                  a3,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0,
                  7u,
                  1u,
                  0x200028u,
                  0,
                  0,
                  0,
                  &DriverContext);
    if ( v35 )
    {
      v27 = *v33;
      *v33 = EcpContext;
      if ( v27 )
        ObfDereferenceObject(v27);
    }
    if ( Parameter < 0 )
    {
      if ( Parameter != -1073741772 && Parameter != -1073741766 )
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)Parameter,
          a6,
          (struct UnionFs::StackEventTracer *)0x25F0021218ELL,
          (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
          "API: Opening file",
          LookasideListb);
      goto LABEL_40;
    }
    if ( !v14 || (Parameter = UnionFs::Utils::MoveQueryOnCreateEcpToResults(a4, EcpList, v8, a6), Parameter >= 0) )
    {
      Parameter = 0;
      goto LABEL_40;
    }
    v23 = a6;
    v21 = "PUSH: Getting QUERY_ON_CREATE info";
    v22 = 0x33F0021219DLL;
LABEL_38:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Parameter,
      v23,
      (struct UnionFs::StackEventTracer *)v22,
      (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
      v21,
      LookasideListb);
LABEL_40:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v15);
    return (unsigned int)Parameter;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)Parameter,
    a6,
    (struct UnionFs::StackEventTracer *)0x25600212143LL,
    (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
    "API: FltAllocateExtraCreateParameterList",
    LookasideList);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x140072df8  mov     rax, rsp
0x140072dfb  mov     [rax+10h], rbx
0x140072dff  mov     [rax+18h], r8d
0x140072e03  mov     [rax+8], rcx
0x140072e07  push    rbp
0x140072e08  push    rsi
0x140072e09  push    rdi
0x140072e0a  push    r12
0x140072e0c  push    r13
0x140072e0e  push    r14
0x140072e10  push    r15
0x140072e12  lea     rbp, [rax-48h]
0x140072e16  sub     rsp, 110h
0x140072e1d  mov     rdi, [rbp+40h+arg_20]
0x140072e21  xor     ebx, ebx
0x140072e23  mov     esi, r9d
0x140072e26  mov     r13, rdx
0x140072e29  mov     rcx, [rdi]; FileHandle
0x140072e2c  test    rcx, rcx
0x140072e2f  jz      short loc_140072E3D
0x140072e31  call    cs:__imp_FltClose
0x140072e38  nop     dword ptr [rax+rax+00h]
0x140072e3d  lea     r15, [rdi+8]
0x140072e41  mov     [rdi], rbx
0x140072e44  mov     rcx, [r15]; Object
0x140072e47  mov     [r15], rbx
0x140072e4a  test    rcx, rcx
0x140072e4d  jz      short loc_140072E5B
0x140072e4f  call    cs:__imp_ObfDereferenceObject
0x140072e56  nop     dword ptr [rax+rax+00h]
0x140072e5b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072e62  lea     r8, [rbp+40h+EcpList]; EcpList
0x140072e66  mov     [rbp+40h+EcpList], rbx
0x140072e6a  xor     edx, edx; Flags
0x140072e6c  mov     rcx, [rcx]; Filter
0x140072e6f  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140072e76  nop     dword ptr [rax+rax+00h]
0x140072e7b  xor     edx, edx
0x140072e7d  mov     ebx, eax
0x140072e7f  test    eax, eax
0x140072e81  jns     short loc_140072EB0
0x140072e83  mov     rdx, [rbp+40h+arg_28]; int
0x140072e87  lea     rax, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x140072e8e  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x140072e95  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072e9a  mov     r8, 25600212143h; struct UnionFs::StackEventTracer *
0x140072ea4  mov     ecx, ebx; this
0x140072ea6  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072eab  jmp     loc_1400731FF
0x140072eb0  mov     rcx, [rbp+40h+EcpList]
0x140072eb4  mov     r14b, dl
0x140072eb7  mov     r12, rcx
0x140072eba  test    sil, 6
0x140072ebe  jz      loc_140073025
0x140072ec4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072ecb  lea     rax, [rbp+40h+arg_20]
0x140072ecf  mov     [rbp+40h+arg_20], rdx
0x140072ed3  mov     r14d, 0C8h
0x140072ed9  mov     [rbp+40h+var_B0], rdx
0x140072edd  xor     r9d, r9d; Flags
0x140072ee0  mov     [rbp+40h+var_B8], rax
0x140072ee4  lea     rdx, [rbp+40h+var_B0]
0x140072ee8  lea     rax, [rcx+8C0h]
0x140072eef  mov     [rsp+140h+EcpContext], rdx; EcpContext
0x140072ef4  mov     rcx, [rcx]; Filter
0x140072ef7  lea     rdx, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140072efe  mov     [rsp+140h+LookasideList], rax; char *
0x140072f03  mov     r8d, r14d; SizeOfContext
0x140072f06  lea     rax, ?QoCEcpCleanupCallback@Utils@UnionFs@@YAXPEAXPEBU_GUID@@@Z; UnionFs::Utils::QoCEcpCleanupCallback(void *,_GUID const *)
0x140072f0d  mov     [rbp+40h+var_A8], 1
0x140072f11  mov     [rsp+140h+CleanupCallback], rax; CleanupCallback
0x140072f16  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140072f1d  nop     dword ptr [rax+rax+00h]
0x140072f22  cmp     [rbp+40h+var_A8], 0
0x140072f26  mov     ebx, eax
0x140072f28  jz      short loc_140072F53
0x140072f2a  mov     r8, [rbp+40h+var_B8]
0x140072f2e  mov     rcx, [rbp+40h+var_B0]
0x140072f32  mov     rdx, [r8]; EcpContext
0x140072f35  mov     [r8], rcx
0x140072f38  test    rdx, rdx
0x140072f3b  jz      short loc_140072F53
0x140072f3d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072f44  mov     rcx, [rcx]; Filter
0x140072f47  call    cs:__imp_FltFreeExtraCreateParameter
0x140072f4e  nop     dword ptr [rax+rax+00h]
0x140072f53  test    ebx, ebx
0x140072f55  jns     short loc_140072F6A
0x140072f57  lea     rax, aApiAllocatingQ; "API: Allocating QoC ECP"
0x140072f5e  mov     r8, 305002120E0h
0x140072f68  jmp     short loc_140072FC8
0x140072f6a  mov     rcx, [rbp+40h+arg_20]; void *
0x140072f6e  mov     r8, r14; Size
0x140072f71  xor     edx, edx; Val
0x140072f73  call    memset
0x140072f78  test    sil, 2
0x140072f7c  jz      short loc_140072F85
0x140072f7e  mov     rax, [rbp+40h+arg_20]
0x140072f82  or      dword ptr [rax], 1
0x140072f85  test    sil, 4
0x140072f89  jz      short loc_140072F92
0x140072f8b  mov     rax, [rbp+40h+arg_20]
0x140072f8f  or      dword ptr [rax], 4
0x140072f92  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072f99  mov     rdx, r12; EcpList
0x140072f9c  mov     r8, [rbp+40h+arg_20]; EcpContext
0x140072fa0  mov     rcx, [rcx]; Filter
0x140072fa3  call    cs:__imp_FltInsertExtraCreateParameter
0x140072faa  nop     dword ptr [rax+rax+00h]
0x140072faf  xor     edx, edx
0x140072fb1  mov     ebx, eax
0x140072fb3  test    eax, eax
0x140072fb5  jns     short loc_14007301A
0x140072fb7  lea     rax, aApiInsertingQo; "API: Inserting QoC ECP"
0x140072fbe  mov     r8, 30F002120F4h; struct UnionFs::StackEventTracer *
0x140072fc8  mov     rdi, [rbp+40h+arg_28]
0x140072fcc  lea     r9, aUnionfsUtilsPr; "UnionFs::Utils::PrepareQoCEcp"
0x140072fd3  mov     rdx, rdi; int
0x140072fd6  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072fdb  mov     ecx, ebx; this
0x140072fdd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072fe2  mov     rdx, [rbp+40h+arg_20]; EcpContext
0x140072fe6  test    rdx, rdx
0x140072fe9  jz      short loc_140073001
0x140072feb  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072ff2  mov     rcx, [rcx]; Filter
0x140072ff5  call    cs:__imp_FltFreeExtraCreateParameter
0x140072ffc  nop     dword ptr [rax+rax+00h]
0x140073001  lea     rax, aPushPreparingQ; "PUSH: Preparing QUERY_ON_CREATE ECP"
0x140073008  mov     r8, 10900212155h
0x140073012  mov     rdx, rdi
0x140073015  jmp     loc_1400731CF
0x14007301a  mov     rcx, [rbp+40h+EcpList]
0x14007301e  mov     r14b, 1
0x140073021  mov     [rbp+40h+arg_20], rdx
0x140073025  mov     eax, 28h ; '('
0x14007302a  mov     dword ptr [rbp+40h+DriverContext+2], edx
0x14007302d  mov     [rbp+40h+DriverContext.Size], ax
0x140073031  xorps   xmm0, xmm0
0x140073034  mov     rax, [rbp+40h+arg_30]
0x14007303b  mov     word ptr [rbp+40h+DriverContext+6], dx
0x14007303f  mov     [rbp+40h+var_80], 1
0x140073047  mov     [rbp+40h+DriverContext.ExtraCreateParameter], rcx
0x14007304b  movdqu  xmmword ptr [rbp+40h+DriverContext.DeviceObjectHint], xmm0
0x140073050  test    rax, rax
0x140073053  jz      short loc_14007305A
0x140073055  mov     rax, [rax]
0x140073058  jmp     short loc_140073068
0x14007305a  call    cs:__imp_PsGetHostSilo
0x140073061  nop     dword ptr [rax+rax+00h]
0x140073066  xor     edx, edx
0x140073068  mov     rcx, [rdi]; FileHandle
0x14007306b  xorps   xmm0, xmm0
0x14007306e  mov     [rbp+40h+var_80], rax
0x140073072  mov     rax, [rbp+40h+arg_38]
0x140073079  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x14007307d  mov     eax, esi
0x14007307f  not     eax
0x140073081  mov     qword ptr [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x140073089  and     eax, 1
0x14007308c  mov     dword ptr [rbp+40h+ObjectAttributes+1Ch], edx
0x14007308f  add     eax, 8
0x140073092  mov     [rbp+40h+ObjectAttributes.ObjectName], r13
0x140073096  shl     eax, 6
0x140073099  mov     [rbp+40h+ObjectAttributes.Attributes], eax
0x14007309c  mov     [rbp+40h+var_B8], r15
0x1400730a0  mov     [rbp+40h+var_B0], rdx
0x1400730a4  mov     [rbp+40h+var_A8], 1
0x1400730a8  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400730ad  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x1400730b1  test    rcx, rcx
0x1400730b4  jz      short loc_1400730C4
0x1400730b6  call    cs:__imp_FltClose
0x1400730bd  nop     dword ptr [rax+rax+00h]
0x1400730c2  xor     edx, edx
0x1400730c4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400730cb  lea     rax, [rbp+40h+DriverContext]
0x1400730cf  mov     [rsp+78h], rax; DriverContext
0x1400730d4  lea     r9, [rbp+40h+var_B0]; FileObject
0x1400730d8  mov     [rsp+140h+Flags], edx; Flags
0x1400730dc  lea     rax, [rbp+40h+IoStatusBlock]
0x1400730e0  mov     [rsp+140h+EaLength], edx; EaLength
0x1400730e4  mov     r8, rdi; FileHandle
0x1400730e7  mov     [rsp+140h+EaBuffer], rdx; EaBuffer
0x1400730ec  mov     [rsp+140h+CreateOptions], 200028h; CreateOptions
0x1400730f4  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x1400730fc  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x140073104  mov     [rsp+140h+FileAttributes], edx; FileAttributes
0x140073108  mov     [rsp+140h+AllocationSize], rdx; AllocationSize
0x14007310d  mov     [rsp+140h+EcpContext], rax; IoStatusBlock
0x140073112  lea     rax, [rbp+40h+ObjectAttributes]
0x140073116  mov     [rsp+140h+LookasideList], rax; char *
0x14007311b  mov     eax, [rbp+40h+DesiredAccess]
0x14007311e  mov     [rdi], rdx
0x140073121  mov     rdx, [rbp+40h+Instance]; Instance
0x140073125  mov     rcx, [rcx]; Filter
0x140073128  mov     dword ptr [rsp+140h+CleanupCallback], eax; DesiredAccess
0x14007312c  call    cs:__imp_FltCreateFileEx2
0x140073133  nop     dword ptr [rax+rax+00h]
0x140073138  cmp     [rbp+40h+var_A8], 0
0x14007313c  mov     ebx, eax
0x14007313e  jz      short loc_14007315F
0x140073140  mov     r8, [rbp+40h+var_B8]
0x140073144  mov     rdx, [rbp+40h+var_B0]
0x140073148  mov     rcx, [r8]; Object
0x14007314b  mov     [r8], rdx
0x14007314e  test    rcx, rcx
0x140073151  jz      short loc_14007315F
0x140073153  call    cs:__imp_ObfDereferenceObject
0x14007315a  nop     dword ptr [rax+rax+00h]
0x14007315f  test    ebx, ebx
0x140073161  jns     short loc_14007319D
0x140073163  cmp     ebx, 0C0000034h
0x140073169  jz      short loc_1400731E6
0x14007316b  cmp     ebx, 0C000003Ah
0x140073171  jz      short loc_1400731E6
0x140073173  mov     rdx, [rbp+40h+arg_28]; int
0x140073177  lea     rax, aApiOpeningFile; "API: Opening file"
0x14007317e  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x140073185  mov     [rsp+140h+CleanupCallback], rax; char *
0x14007318a  mov     r8, 25F0021218Eh; struct UnionFs::StackEventTracer *
0x140073194  mov     ecx, ebx; this
0x140073196  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007319b  jmp     short loc_1400731E6
0x14007319d  test    r14b, r14b
0x1400731a0  jz      short loc_1400731E4
0x1400731a2  mov     r9, [rbp+40h+arg_28]
0x1400731a6  mov     r8, rdi
0x1400731a9  mov     rdx, [rbp+40h+EcpList]
0x1400731ad  mov     ecx, esi
0x1400731af  call    ?MoveQueryOnCreateEcpToResults@Utils@UnionFs@@YAJW4OpenAsReparsePointFlags@12@AEAU_ECP_LIST@@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MoveQueryOnCreateEcpToResults(UnionFs::Utils::OpenAsReparsePointFlags,_ECP_LIST &,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &)
0x1400731b4  mov     ebx, eax
0x1400731b6  test    eax, eax
0x1400731b8  jns     short loc_1400731E4
0x1400731ba  mov     rdx, [rbp+40h+arg_28]; int
0x1400731be  lea     rax, aPushGettingQue; "PUSH: Getting QUERY_ON_CREATE info"
0x1400731c5  mov     r8, 33F0021219Dh; struct UnionFs::StackEventTracer *
0x1400731cf  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x1400731d6  mov     [rsp+140h+CleanupCallback], rax; char *
0x1400731db  mov     ecx, ebx; this
0x1400731dd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400731e2  jmp     short loc_1400731E6
0x1400731e4  xor     ebx, ebx
0x1400731e6  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400731ed  mov     rdx, r12; EcpList
0x1400731f0  mov     rcx, [rcx]; Filter
0x1400731f3  call    cs:__imp_FltFreeExtraCreateParameterList
0x1400731fa  nop     dword ptr [rax+rax+00h]
0x1400731ff  mov     eax, ebx
0x140073201  mov     rbx, [rsp+140h+arg_8]
0x140073209  add     rsp, 110h
0x140073210  pop     r15
0x140073212  pop     r14
0x140073214  pop     r13
0x140073216  pop     r12
0x140073218  pop     rdi
0x140073219  pop     rsi
0x14007321a  pop     rbp
0x14007321b  retn
```
