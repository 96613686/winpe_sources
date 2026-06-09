# _lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()

- ea: `0x1400685bc`
- end: `0x140068959`
- name: `_lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006b78c`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056bd0`
- `0x1400685bc`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140068885`
- `ntoskrnl!ObfDereferenceObject` at `0x14006892f`
- `ntoskrnl!ObfDereferenceObject` at `0x140068885`
- `ntoskrnl!ObfDereferenceObject` at `0x14006892f`
- `FLTMGR!FltPrepareToReuseEcp` at `0x1400688bd`
- `FLTMGR!FltPrepareToReuseEcp` at `0x1400688bd`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140068692`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140068692`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006861b`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006861b`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400686d7`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x1400686d7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140068755`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140068755`
- `FLTMGR!FltCreateFileEx2` at `0x14006885e`
- `FLTMGR!FltCreateFileEx2` at `0x14006885e`
- `FLTMGR!FltSetInformationFile` at `0x1400688ea`
- `FLTMGR!FltSetInformationFile` at `0x1400688ea`
- `FLTMGR!FltClose` at `0x140068944`
- `FLTMGR!FltClose` at `0x140068944`

## string_xrefs

- `0x1400686a2`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006862b`: `API: FltAllocateExtraCreateParameterList`
- `0x140068765`: `API: FltInsertExtraCreateParameter`
- `0x140068895`: `API: FltCreateFileEx2`
- `0x140068641`: `UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()`
- `0x1400686b8`: `UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()`
- `0x140068912`: `UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()`

## pseudocode

```c
void __fastcall lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()(__int64 a1)
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

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v32, 0x3CC00211E5CuLL);
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
                (struct UnionFs::StackEventTracer *)0x3CE00211ED6LL,
                (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()",
                "API: FltSetInformationFile",
                LookasideListb);
          }
          else
          {
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)v12,
              (int)v32,
              (struct UnionFs::StackEventTracer *)0x3CD00211EC0LL,
              (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()",
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
      v6 = 0x62300211E96LL;
    }
    else
    {
      v5 = "API: FltAllocateExtraCreateParameterFromLookasideList";
      v6 = 0x62000211E82LL;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      (int)v32,
      (struct UnionFs::StackEventTracer *)v6,
      (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()",
      v5,
      LookasideLista);
LABEL_6:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v3);
    goto LABEL_7;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v2,
    (int)v32,
    (struct UnionFs::StackEventTracer *)0x62100211E67LL,
    (unsigned __int64)"UnionFs::Utils::CopyHardLinks::<lambda_d0ebc0232045179cce8cceee9eafce0e>::operator ()",
    "API: FltAllocateExtraCreateParameterList",
    LookasideList);
LABEL_7:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v32);
}

```

## disassembly

```asm
0x1400685bc  mov     [rsp-8+arg_8], rbx
0x1400685c1  mov     [rsp-8+arg_10], rsi
0x1400685c6  push    rbp
0x1400685c7  push    rdi
0x1400685c8  push    r12
0x1400685ca  push    r14
0x1400685cc  push    r15
0x1400685ce  lea     rbp, [rsp-320h]
0x1400685d6  sub     rsp, 420h
0x1400685dd  mov     rax, cs:__security_cookie
0x1400685e4  xor     rax, rsp
0x1400685e7  mov     [rbp+340h+var_28], rax
0x1400685ee  mov     r14, rcx
0x1400685f1  mov     rdx, 3CC00211E5Ch; unsigned __int64
0x1400685fb  lea     rcx, [rbp+340h+var_318]; this
0x1400685ff  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140068604  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006860b  lea     r8, [rbp+340h+EcpList]; EcpList
0x14006860f  xor     r12d, r12d
0x140068612  xor     edx, edx; Flags
0x140068614  mov     [rbp+340h+EcpList], r12
0x140068618  mov     rcx, [rcx]; Filter
0x14006861b  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140068622  nop     dword ptr [rax+rax+00h]
0x140068627  test    eax, eax
0x140068629  jns     short loc_140068658
0x14006862b  lea     rcx, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x140068632  mov     r8, 62100211E67h; struct UnionFs::StackEventTracer *
0x14006863c  mov     [rsp+440h+CleanupCallback], rcx; char *
0x140068641  lea     r9, aUnionfsUtilsCo_3; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x140068648  mov     ecx, eax; this
0x14006864a  lea     rdx, [rbp+340h+var_318]; int
0x14006864e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068653  jmp     loc_1400686E3
0x140068658  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006865f  lea     rdx, [rbp+340h+var_3C0]
0x140068663  mov     r15, [rbp+340h+EcpList]
0x140068667  xor     r9d, r9d; Flags
0x14006866a  mov     [rsp+440h+EcpContext], rdx; EcpContext
0x14006866f  lea     rdx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x140068676  mov     [rbp+340h+var_3C0], r12
0x14006867a  lea     rax, [rcx+940h]
0x140068681  mov     rcx, [rcx]; Filter
0x140068684  mov     [rsp+440h+LookasideList], rax; char *
0x140068689  lea     r8d, [r9+24h]; SizeOfContext
0x14006868d  mov     [rsp+440h+CleanupCallback], r12; CleanupCallback
0x140068692  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140068699  nop     dword ptr [rax+rax+00h]
0x14006869e  test    eax, eax
0x1400686a0  jns     short loc_140068718
0x1400686a2  lea     rcx, aApiFltallocate_2; "API: FltAllocateExtraCreateParameterFro"...
0x1400686a9  mov     r8, 62000211E82h; struct UnionFs::StackEventTracer *
0x1400686b3  mov     [rsp+440h+CleanupCallback], rcx; char *
0x1400686b8  lea     r9, aUnionfsUtilsCo_3; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x1400686bf  mov     ecx, eax; this
0x1400686c1  lea     rdx, [rbp+340h+var_318]; int
0x1400686c5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400686ca  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400686d1  mov     rdx, r15; EcpList
0x1400686d4  mov     rcx, [rcx]; Filter
0x1400686d7  call    cs:__imp_FltFreeExtraCreateParameterList
0x1400686de  nop     dword ptr [rax+rax+00h]
0x1400686e3  lea     rcx, [rbp+340h+var_318]; this
0x1400686e7  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x1400686ec  mov     rcx, [rbp+340h+var_28]
0x1400686f3  xor     rcx, rsp; StackCookie
0x1400686f6  call    __security_check_cookie
0x1400686fb  lea     r11, [rsp+440h+var_20]
0x140068703  mov     rbx, [r11+38h]
0x140068707  mov     rsi, [r11+40h]
0x14006870b  mov     rsp, r11
0x14006870e  pop     r15
0x140068710  pop     r14
0x140068712  pop     r12
0x140068714  pop     rdi
0x140068715  pop     rbp
0x140068716  retn
0x140068718  mov     rax, [rbp+340h+var_3C0]
0x14006871c  xorps   xmm0, xmm0
0x14006871f  xor     ecx, ecx
0x140068721  movups  xmmword ptr [rax], xmm0
0x140068724  movups  xmmword ptr [rax+10h], xmm0
0x140068728  mov     [rax+20h], ecx
0x14006872b  mov     rax, [rbp+340h+var_3C0]
0x14006872f  movups  xmm0, cs:UNIONFS_GUID_ECP_OPLOCK_KEY
0x140068736  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006873d  movdqu  xmmword ptr [rax+10h], xmm0
0x140068742  mov     rax, [rbp+340h+var_3C0]
0x140068746  mov     byte ptr [rax+21h], 1
0x14006874a  mov     r8, [rbp+340h+var_3C0]; EcpContext
0x14006874e  mov     rdx, [rbp+340h+EcpList]; EcpList
0x140068752  mov     rcx, [rcx]; Filter
0x140068755  call    cs:__imp_FltInsertExtraCreateParameter
0x14006875c  nop     dword ptr [rax+rax+00h]
0x140068761  test    eax, eax
0x140068763  jns     short loc_14006877B
0x140068765  lea     rcx, aApiFltinsertex; "API: FltInsertExtraCreateParameter"
0x14006876c  mov     r8, 62300211E96h
0x140068776  jmp     loc_1400686B3
0x14006877b  mov     rdi, [r14]
0x14006877e  mov     rbx, [rdi]
0x140068781  mov     rdi, [rdi+8]
0x140068785  cmp     rbx, rdi
0x140068788  jz      loc_1400686CA
0x14006878e  mov     rax, [rbx]
0x140068791  lea     r9, [rbp+340h+FileObject]; FileObject
0x140068795  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006879c  lea     r8, [rbp+340h+FileHandle]; FileHandle
0x1400687a0  mov     rdx, [r14+8]; Instance
0x1400687a4  xorps   xmm0, xmm0
0x1400687a7  mov     [rbp+340h+ObjectAttributes.ObjectName], rax
0x1400687ab  mov     eax, 28h ; '('
0x1400687b0  mov     [rbp+340h+var_380.Size], ax
0x1400687b4  mov     rax, [rbp+340h+EcpList]
0x1400687b8  mov     [rbp+340h+var_380.ExtraCreateParameter], rax
0x1400687bc  lea     rax, [rbp+340h+var_3B0]
0x1400687c0  mov     [rbp+340h+var_398], rax
0x1400687c4  lea     rax, [rbp+340h+var_380]
0x1400687c8  mov     [rsp+440h+DriverContext], rax; DriverContext
0x1400687cd  lea     rax, [rbp+340h+IoStatusBlock]
0x1400687d1  mov     [rsp+440h+Flags], 800h; Flags
0x1400687d9  mov     [rsp+440h+EaLength], r12d; EaLength
0x1400687de  mov     [rsp+440h+EaBuffer], r12; EaBuffer
0x1400687e3  mov     [rsp+440h+CreateOptions], 60h ; '`'; CreateOptions
0x1400687eb  mov     [rsp+440h+CreateDisposition], 1; CreateDisposition
0x1400687f3  mov     [rsp+440h+ShareAccess], r12d; ShareAccess
0x1400687f8  mov     [rsp+440h+FileAttributes], r12d; FileAttributes
0x1400687fd  mov     [rsp+440h+AllocationSize], r12; AllocationSize
0x140068802  mov     [rsp+440h+EcpContext], rax; IoStatusBlock
0x140068807  lea     rax, [rbp+340h+ObjectAttributes]
0x14006880b  mov     qword ptr [rbp+340h+ObjectAttributes.Length], 30h ; '0'
0x140068813  mov     qword ptr [rbp+340h+ObjectAttributes.Attributes], 200h
0x14006881b  mov     [rbp+340h+ObjectAttributes.RootDirectory], r12
0x14006881f  movdqu  xmmword ptr [rbp+340h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068824  mov     dword ptr [rbp+340h+var_380+2], r12d
0x140068828  movups  xmmword ptr [rbp+340h+IoStatusBlock], xmm0
0x14006882c  mov     word ptr [rbp+340h+var_380+6], r12w
0x140068831  movdqu  xmmword ptr [rbp+340h+var_380.DeviceObjectHint], xmm0
0x140068836  mov     [rbp+340h+var_360], 1
0x14006883e  mov     [rbp+340h+var_3B0], r12
0x140068842  mov     [rbp+340h+FileObject], r12
0x140068846  mov     [rbp+340h+var_388], 1
0x14006884a  mov     [rbp+340h+FileHandle], r12
0x14006884e  mov     rcx, [rcx]; Filter
0x140068851  mov     [rsp+440h+LookasideList], rax; char *
0x140068856  mov     dword ptr [rsp+440h+CleanupCallback], 10000h; DesiredAccess
0x14006885e  call    cs:__imp_FltCreateFileEx2
0x140068865  nop     dword ptr [rax+rax+00h]
0x14006886a  mov     esi, eax
0x14006886c  cmp     [rbp+340h+var_388], r12b
0x140068870  jz      short loc_140068891
0x140068872  mov     r8, [rbp+340h+var_398]
0x140068876  mov     rdx, [rbp+340h+FileObject]
0x14006887a  mov     rcx, [r8]; Object
0x14006887d  mov     [r8], rdx
0x140068880  test    rcx, rcx
0x140068883  jz      short loc_140068891
0x140068885  call    cs:__imp_ObfDereferenceObject
0x14006888c  nop     dword ptr [rax+rax+00h]
0x140068891  test    esi, esi
0x140068893  jns     short loc_1400688AF
0x140068895  lea     rax, aApiFltcreatefi; "API: FltCreateFileEx2"
0x14006889c  mov     r8, 3CD00211EC0h
0x1400688a6  mov     [rsp+440h+CleanupCallback], rax
0x1400688ab  mov     ecx, esi
0x1400688ad  jmp     short loc_140068912
0x1400688af  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400688b6  mov     rdx, [rbp+340h+var_3C0]
0x1400688ba  mov     rcx, [rcx]
0x1400688bd  call    cs:__imp_FltPrepareToReuseEcp
0x1400688c4  nop     dword ptr [rax+rax+00h]
0x1400688c9  mov     rdx, [rbp+340h+var_3B0]; FileObject
0x1400688cd  lea     r8, [rbp+340h+FileInformation]; FileInformation
0x1400688d1  mov     rcx, [r14+8]; Instance
0x1400688d5  mov     r9d, 4; Length
0x1400688db  mov     [rbp+340h+FileInformation], 3
0x1400688e2  mov     dword ptr [rsp+440h+CleanupCallback], 40h ; '@'; FileInformationClass
0x1400688ea  call    cs:__imp_FltSetInformationFile
0x1400688f1  nop     dword ptr [rax+rax+00h]
0x1400688f6  test    eax, eax
0x1400688f8  jns     short loc_140068922
0x1400688fa  lea     rcx, aApiFltsetinfor; "API: FltSetInformationFile"
0x140068901  mov     r8, 3CE00211ED6h; struct UnionFs::StackEventTracer *
0x14006890b  mov     [rsp+440h+CleanupCallback], rcx; char *
0x140068910  mov     ecx, eax; this
0x140068912  lea     r9, aUnionfsUtilsCo_3; "UnionFs::Utils::CopyHardLinks::<lambda_"...
0x140068919  lea     rdx, [rbp+340h+var_318]; int
0x14006891d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068922  mov     rcx, [rbp+340h+var_3B0]; Object
0x140068926  mov     [rbp+340h+var_3B0], r12
0x14006892a  test    rcx, rcx
0x14006892d  jz      short loc_14006893B
0x14006892f  call    cs:__imp_ObfDereferenceObject
0x140068936  nop     dword ptr [rax+rax+00h]
0x14006893b  mov     rcx, [rbp+340h+FileHandle]; FileHandle
0x14006893f  test    rcx, rcx
0x140068942  jz      short loc_140068950
0x140068944  call    cs:__imp_FltClose
0x14006894b  nop     dword ptr [rax+rax+00h]
0x140068950  add     rbx, 8
0x140068954  jmp     loc_140068785
```
