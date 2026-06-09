# _lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()

- ea: `0x1400683cc`
- end: `0x140068769`
- name: `_lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006b59c`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056a50`
- `0x1400683cc`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140068695`
- `ntoskrnl!ObfDereferenceObject` at `0x14006873f`
- `ntoskrnl!ObfDereferenceObject` at `0x140068695`
- `ntoskrnl!ObfDereferenceObject` at `0x14006873f`
- `FLTMGR!FltPrepareToReuseEcp` at `0x1400686cd`
- `FLTMGR!FltPrepareToReuseEcp` at `0x1400686cd`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400684a2`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400684a2`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006842b`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006842b`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400684e7`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400684e7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140068565`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140068565`
- `FLTMGR!FltCreateFileEx2` at `0x14006866e`
- `FLTMGR!FltCreateFileEx2` at `0x14006866e`
- `FLTMGR!FltSetInformationFile` at `0x1400686fa`
- `FLTMGR!FltSetInformationFile` at `0x1400686fa`
- `FLTMGR!FltClose` at `0x140068754`
- `FLTMGR!FltClose` at `0x140068754`

## string_xrefs

- `0x1400684b2`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006843b`: `API: FltAllocateExtraCreateParameterList`
- `0x140068575`: `API: FltInsertExtraCreateParameter`
- `0x1400686a5`: `API: FltCreateFileEx2`
- `0x140068451`: `UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()`
- `0x1400684c8`: `UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()`
- `0x140068722`: `UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()`

## pseudocode

```c
void __fastcall lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()(__int64 a1)
{
  NTSTATUS v2; // eax
  struct _ECP_LIST *v3; // r15
  NTSTATUS Parameter; // eax
  const char *v5; // rcx
  __int64 v6; // r8
  _OWORD *v7; // rax
  PFLT_FILTER *v8; // rcx
  PUNICODE_STRING *v9; // rbx
  PUNICODE_STRING *v10; // rdi
  struct _FLT_INSTANCE *v11; // rdx
  NTSTATUS v12; // esi
  PFILE_OBJECT v13; // rcx
  struct _FLT_INSTANCE *v14; // rcx
  NTSTATUS v15; // eax
  PFILE_OBJECT v16; // rcx
  const char *LookasideList; // [rsp+28h] [rbp-D8h]
  const char *LookasideLista; // [rsp+28h] [rbp-D8h]
  const char *LookasideListb; // [rsp+28h] [rbp-D8h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT v22; // [rsp+90h] [rbp-70h] BYREF
  int FileInformation; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PFILE_OBJECT *v25; // [rsp+A8h] [rbp-58h]
  PFILE_OBJECT FileObject; // [rsp+B0h] [rbp-50h] BYREF
  char v27; // [rsp+B8h] [rbp-48h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF
  int v32[188]; // [rsp+128h] [rbp+28h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v32, 0x3CC00211E26uLL);
  EcpList = 0;
  v2 = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( v2 >= 0 )
  {
    v3 = EcpList;
    EcpContext = 0;
    Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                  *(PFLT_FILTER *)UnionFs::g_FilterState,
                  &GUID_ECP_DUAL_OPLOCK_KEY,
                  0x24u,
                  0,
                  0,
                  (char *)UnionFs::g_FilterState + 2368,
                  &EcpContext);
    if ( Parameter >= 0 )
    {
      v7 = EcpContext;
      *(_OWORD *)EcpContext = 0;
      v7[1] = 0;
      *((_DWORD *)v7 + 8) = 0;
      v8 = (PFLT_FILTER *)UnionFs::g_FilterState;
      *((_OWORD *)EcpContext + 1) = UNIONFS_GUID_ECP_OPLOCK_KEY;
      *((_BYTE *)EcpContext + 33) = 1;
      Parameter = FltInsertExtraCreateParameter(*v8, EcpList, EcpContext);
      if ( Parameter >= 0 )
      {
        v9 = **(PUNICODE_STRING ***)a1;
        v10 = *(PUNICODE_STRING **)(*(_QWORD *)a1 + 8LL);
        while ( v9 != v10 )
        {
          v11 = *(struct _FLT_INSTANCE **)(a1 + 8);
          ObjectAttributes.ObjectName = *v9;
          DriverContext.Size = 40;
          DriverContext.ExtraCreateParameter = EcpList;
          v25 = &v22;
          *(_QWORD *)&ObjectAttributes.Length = 48;
          *(_QWORD *)&ObjectAttributes.Attributes = 512;
          ObjectAttributes.RootDirectory = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          *(_DWORD *)(&DriverContext.Size + 1) = 0;
          IoStatusBlock = 0;
          *(&DriverContext.Size + 3) = 0;
          *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
          v29 = 1;
          v22 = 0;
          FileObject = 0;
          v27 = 1;
          FileHandle = 0;
          v12 = FltCreateFileEx2(
                  *(PFLT_FILTER *)UnionFs::g_FilterState,
                  v11,
                  &FileHandle,
                  &FileObject,
                  0x10000u,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0,
                  0,
                  1u,
                  0x60u,
                  0,
                  0,
                  0x800u,
                  &DriverContext);
          if ( v27 )
          {
            v13 = *v25;
            *v25 = FileObject;
            if ( v13 )
              ObfDereferenceObject(v13);
          }
          if ( v12 >= 0 )
          {
            FltPrepareToReuseEcp(*(_QWORD *)UnionFs::g_FilterState, EcpContext);
            v14 = *(struct _FLT_INSTANCE **)(a1 + 8);
            FileInformation = 3;
            v15 = FltSetInformationFile(v14, v22, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
            if ( v15 < 0 )
              UnionFs::ProcessTraceStatusFromApi(
                (UnionFs *)(unsigned int)v15,
                (int)v32,
                (struct UnionFs::StackEventTracer *)0x3CE00211EA0LL,
                (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()",
                "API: FltSetInformationFile",
                LookasideListb);
          }
          else
          {
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)v12,
              (int)v32,
              (struct UnionFs::StackEventTracer *)0x3CD00211E8ALL,
              (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()",
              "API: FltCreateFileEx2",
              LookasideListb);
          }
          v16 = v22;
          v22 = 0;
          if ( v16 )
            ObfDereferenceObject(v16);
          if ( FileHandle )
            FltClose(FileHandle);
          ++v9;
        }
        goto LABEL_6;
      }
      v5 = "API: FltInsertExtraCreateParameter";
      v6 = 0x62300211E60LL;
    }
    else
    {
      v5 = "API: FltAllocateExtraCreateParameterFromLookasideList";
      v6 = 0x62000211E4CLL;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      (int)v32,
      (struct UnionFs::StackEventTracer *)v6,
      (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()",
      v5,
      LookasideLista);
LABEL_6:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v3);
    goto LABEL_7;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v2,
    (int)v32,
    (struct UnionFs::StackEventTracer *)0x62100211E31LL,
    (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d07897a6db9635dde06c57e4c17e80c6>::operator ()",
    "API: FltAllocateExtraCreateParameterList",
    LookasideList);
LABEL_7:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v32);
}

```

## disassembly

```asm
0x1400683cc  mov     [rsp-8+arg_8], rbx
0x1400683d1  mov     [rsp-8+arg_10], rsi
0x1400683d6  push    rbp
0x1400683d7  push    rdi
0x1400683d8  push    r12
0x1400683da  push    r14
0x1400683dc  push    r15
0x1400683de  lea     rbp, [rsp-320h]
0x1400683e6  sub     rsp, 420h
0x1400683ed  mov     rax, cs:__security_cookie
0x1400683f4  xor     rax, rsp
0x1400683f7  mov     [rbp+340h+var_28], rax
0x1400683fe  mov     r14, rcx
0x140068401  mov     rdx, 3CC00211E26h; unsigned __int64
0x14006840b  lea     rcx, [rbp+340h+var_318]; this
0x14006840f  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140068414  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006841b  lea     r8, [rbp+340h+EcpList]; EcpList
0x14006841f  xor     r12d, r12d
0x140068422  xor     edx, edx; Flags
0x140068424  mov     [rbp+340h+EcpList], r12
0x140068428  mov     rcx, [rcx]; Filter
0x14006842b  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140068432  nop     dword ptr [rax+rax+00h]
0x140068437  test    eax, eax
0x140068439  jns     short loc_140068468
0x14006843b  lea     rcx, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x140068442  mov     r8, 62100211E31h; struct UnionFs::StackEventTracer *
0x14006844c  mov     [rsp+440h+CleanupCallback], rcx; char *
0x140068451  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x140068458  mov     ecx, eax; this
0x14006845a  lea     rdx, [rbp+340h+var_318]; int
0x14006845e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068463  jmp     loc_1400684F3
0x140068468  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006846f  lea     rdx, [rbp+340h+var_3C0]
0x140068473  mov     r15, [rbp+340h+EcpList]
0x140068477  xor     r9d, r9d; Flags
0x14006847a  mov     [rsp+440h+EcpContext], rdx; EcpContext
0x14006847f  lea     rdx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x140068486  mov     [rbp+340h+var_3C0], r12
0x14006848a  lea     rax, [rcx+940h]
0x140068491  mov     rcx, [rcx]; Filter
0x140068494  mov     [rsp+440h+LookasideList], rax; char *
0x140068499  lea     r8d, [r9+24h]; SizeOfContext
0x14006849d  mov     [rsp+440h+CleanupCallback], r12; CleanupCallback
0x1400684a2  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x1400684a9  nop     dword ptr [rax+rax+00h]
0x1400684ae  test    eax, eax
0x1400684b0  jns     short loc_140068528
0x1400684b2  lea     rcx, aApiFltallocate_2; "API: FltAllocateExtraCreateParameterFro"...
0x1400684b9  mov     r8, 62000211E4Ch; struct UnionFs::StackEventTracer *
0x1400684c3  mov     [rsp+440h+CleanupCallback], rcx; char *
0x1400684c8  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x1400684cf  mov     ecx, eax; this
0x1400684d1  lea     rdx, [rbp+340h+var_318]; int
0x1400684d5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400684da  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400684e1  mov     rdx, r15; EcpList
0x1400684e4  mov     rcx, [rcx]; Filter
0x1400684e7  call    cs:__imp_FltFreeExtraCreateParameterList
0x1400684ee  nop     dword ptr [rax+rax+00h]
0x1400684f3  lea     rcx, [rbp+340h+var_318]; this
0x1400684f7  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x1400684fc  mov     rcx, [rbp+340h+var_28]
0x140068503  xor     rcx, rsp; StackCookie
0x140068506  call    __security_check_cookie
0x14006850b  lea     r11, [rsp+440h+var_20]
0x140068513  mov     rbx, [r11+38h]
0x140068517  mov     rsi, [r11+40h]
0x14006851b  mov     rsp, r11
0x14006851e  pop     r15
0x140068520  pop     r14
0x140068522  pop     r12
0x140068524  pop     rdi
0x140068525  pop     rbp
0x140068526  retn
0x140068528  mov     rax, [rbp+340h+var_3C0]
0x14006852c  xorps   xmm0, xmm0
0x14006852f  xor     ecx, ecx
0x140068531  movups  xmmword ptr [rax], xmm0
0x140068534  movups  xmmword ptr [rax+10h], xmm0
0x140068538  mov     [rax+20h], ecx
0x14006853b  mov     rax, [rbp+340h+var_3C0]
0x14006853f  movups  xmm0, cs:UNIONFS_GUID_ECP_OPLOCK_KEY
0x140068546  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006854d  movdqu  xmmword ptr [rax+10h], xmm0
0x140068552  mov     rax, [rbp+340h+var_3C0]
0x140068556  mov     byte ptr [rax+21h], 1
0x14006855a  mov     r8, [rbp+340h+var_3C0]; EcpContext
0x14006855e  mov     rdx, [rbp+340h+EcpList]; EcpList
0x140068562  mov     rcx, [rcx]; Filter
0x140068565  call    cs:__imp_FltInsertExtraCreateParameter
0x14006856c  nop     dword ptr [rax+rax+00h]
0x140068571  test    eax, eax
0x140068573  jns     short loc_14006858B
0x140068575  lea     rcx, aApiFltinsertex; "API: FltInsertExtraCreateParameter"
0x14006857c  mov     r8, 62300211E60h
0x140068586  jmp     loc_1400684C3
0x14006858b  mov     rdi, [r14]
0x14006858e  mov     rbx, [rdi]
0x140068591  mov     rdi, [rdi+8]
0x140068595  cmp     rbx, rdi
0x140068598  jz      loc_1400684DA
0x14006859e  mov     rax, [rbx]
0x1400685a1  lea     r9, [rbp+340h+FileObject]; FileObject
0x1400685a5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400685ac  lea     r8, [rbp+340h+FileHandle]; FileHandle
0x1400685b0  mov     rdx, [r14+8]; Instance
0x1400685b4  xorps   xmm0, xmm0
0x1400685b7  mov     [rbp+340h+ObjectAttributes.ObjectName], rax
0x1400685bb  mov     eax, 28h ; '('
0x1400685c0  mov     [rbp+340h+var_380.Size], ax
0x1400685c4  mov     rax, [rbp+340h+EcpList]
0x1400685c8  mov     [rbp+340h+var_380.ExtraCreateParameter], rax
0x1400685cc  lea     rax, [rbp+340h+var_3B0]
0x1400685d0  mov     [rbp+340h+var_398], rax
0x1400685d4  lea     rax, [rbp+340h+var_380]
0x1400685d8  mov     [rsp+440h+DriverContext], rax; DriverContext
0x1400685dd  lea     rax, [rbp+340h+IoStatusBlock]
0x1400685e1  mov     [rsp+440h+Flags], 800h; Flags
0x1400685e9  mov     [rsp+440h+EaLength], r12d; EaLength
0x1400685ee  mov     [rsp+440h+EaBuffer], r12; EaBuffer
0x1400685f3  mov     [rsp+440h+CreateOptions], 60h ; '`'; CreateOptions
0x1400685fb  mov     [rsp+440h+CreateDisposition], 1; CreateDisposition
0x140068603  mov     [rsp+440h+ShareAccess], r12d; ShareAccess
0x140068608  mov     [rsp+440h+FileAttributes], r12d; FileAttributes
0x14006860d  mov     [rsp+440h+AllocationSize], r12; AllocationSize
0x140068612  mov     [rsp+440h+EcpContext], rax; IoStatusBlock
0x140068617  lea     rax, [rbp+340h+ObjectAttributes]
0x14006861b  mov     qword ptr [rbp+340h+ObjectAttributes.Length], 30h ; '0'
0x140068623  mov     qword ptr [rbp+340h+ObjectAttributes.Attributes], 200h
0x14006862b  mov     [rbp+340h+ObjectAttributes.RootDirectory], r12
0x14006862f  movdqu  xmmword ptr [rbp+340h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068634  mov     dword ptr [rbp+340h+var_380+2], r12d
0x140068638  movups  xmmword ptr [rbp+340h+IoStatusBlock], xmm0
0x14006863c  mov     word ptr [rbp+340h+var_380+6], r12w
0x140068641  movdqu  xmmword ptr [rbp+340h+var_380.DeviceObjectHint], xmm0
0x140068646  mov     [rbp+340h+var_360], 1
0x14006864e  mov     [rbp+340h+var_3B0], r12
0x140068652  mov     [rbp+340h+FileObject], r12
0x140068656  mov     [rbp+340h+var_388], 1
0x14006865a  mov     [rbp+340h+FileHandle], r12
0x14006865e  mov     rcx, [rcx]; Filter
0x140068661  mov     [rsp+440h+LookasideList], rax; char *
0x140068666  mov     dword ptr [rsp+440h+CleanupCallback], 10000h; DesiredAccess
0x14006866e  call    cs:__imp_FltCreateFileEx2
0x140068675  nop     dword ptr [rax+rax+00h]
0x14006867a  mov     esi, eax
0x14006867c  cmp     [rbp+340h+var_388], r12b
0x140068680  jz      short loc_1400686A1
0x140068682  mov     r8, [rbp+340h+var_398]
0x140068686  mov     rdx, [rbp+340h+FileObject]
0x14006868a  mov     rcx, [r8]; Object
0x14006868d  mov     [r8], rdx
0x140068690  test    rcx, rcx
0x140068693  jz      short loc_1400686A1
0x140068695  call    cs:__imp_ObfDereferenceObject
0x14006869c  nop     dword ptr [rax+rax+00h]
0x1400686a1  test    esi, esi
0x1400686a3  jns     short loc_1400686BF
0x1400686a5  lea     rax, aApiFltcreatefi; "API: FltCreateFileEx2"
0x1400686ac  mov     r8, 3CD00211E8Ah
0x1400686b6  mov     [rsp+440h+CleanupCallback], rax
0x1400686bb  mov     ecx, esi
0x1400686bd  jmp     short loc_140068722
0x1400686bf  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400686c6  mov     rdx, [rbp+340h+var_3C0]
0x1400686ca  mov     rcx, [rcx]
0x1400686cd  call    cs:__imp_FltPrepareToReuseEcp
0x1400686d4  nop     dword ptr [rax+rax+00h]
0x1400686d9  mov     rdx, [rbp+340h+var_3B0]; FileObject
0x1400686dd  lea     r8, [rbp+340h+FileInformation]; FileInformation
0x1400686e1  mov     rcx, [r14+8]; Instance
0x1400686e5  mov     r9d, 4; Length
0x1400686eb  mov     [rbp+340h+FileInformation], 3
0x1400686f2  mov     dword ptr [rsp+440h+CleanupCallback], 40h ; '@'; FileInformationClass
0x1400686fa  call    cs:__imp_FltSetInformationFile
0x140068701  nop     dword ptr [rax+rax+00h]
0x140068706  test    eax, eax
0x140068708  jns     short loc_140068732
0x14006870a  lea     rcx, aApiFltsetinfor; "API: FltSetInformationFile"
0x140068711  mov     r8, 3CE00211EA0h; struct UnionFs::StackEventTracer *
0x14006871b  mov     [rsp+440h+CleanupCallback], rcx; char *
0x140068720  mov     ecx, eax; this
0x140068722  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x140068729  lea     rdx, [rbp+340h+var_318]; int
0x14006872d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068732  mov     rcx, [rbp+340h+var_3B0]; Object
0x140068736  mov     [rbp+340h+var_3B0], r12
0x14006873a  test    rcx, rcx
0x14006873d  jz      short loc_14006874B
0x14006873f  call    cs:__imp_ObfDereferenceObject
0x140068746  nop     dword ptr [rax+rax+00h]
0x14006874b  mov     rcx, [rbp+340h+FileHandle]; FileHandle
0x14006874f  test    rcx, rcx
0x140068752  jz      short loc_140068760
0x140068754  call    cs:__imp_FltClose
0x14006875b  nop     dword ptr [rax+rax+00h]
0x140068760  add     rbx, 8
0x140068764  jmp     loc_140068595
```
