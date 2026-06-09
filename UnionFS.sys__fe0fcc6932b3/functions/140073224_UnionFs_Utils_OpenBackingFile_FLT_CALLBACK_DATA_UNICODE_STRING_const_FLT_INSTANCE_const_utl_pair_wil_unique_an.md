# UnionFs::Utils::OpenBackingFile(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,_FLT_INSTANCE const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140073224`
- end: `0x1400735cd`
- name: `?OpenBackingFile@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@_N@Z`
- size: `937`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, struct _UNICODE_STRING *, PFLT_INSTANCE Instance, PHANDLE FileHandle, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, installer_update`

## callers

- `0x140040110`

## callees

- `0x140056bd0`
- `0x140056c08`
- `0x140056c44`
- `0x140073224`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x140073306`
- `ntoskrnl!PsGetHostSilo` at `0x140073306`
- `ntoskrnl!ObfDereferenceObject` at `0x140073272`
- `ntoskrnl!ObfDereferenceObject` at `0x140073471`
- `ntoskrnl!ObfDereferenceObject` at `0x140073272`
- `ntoskrnl!ObfDereferenceObject` at `0x140073471`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400734b8`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400734b8`
- `FLTMGR!FltCreateFileEx2` at `0x14007344a`
- `FLTMGR!FltCreateFileEx2` at `0x14007344a`
- `FLTMGR!FltClose` at `0x140073254`
- `FLTMGR!FltClose` at `0x1400733d8`
- `FLTMGR!FltClose` at `0x140073254`
- `FLTMGR!FltClose` at `0x1400733d8`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140073327`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140073327`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14007355c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14007355c`

## string_xrefs

- `0x14007356c`: `ORIGIN: Bad symlink data`
- `0x1400732a2`: `UnionFs::Utils::OpenBackingFile`
- `0x140073345`: `UnionFs::Utils::OpenBackingFile`
- `0x1400734e7`: `UnionFs::Utils::OpenBackingFile`
- `0x140073597`: `UnionFs::Utils::OpenBackingFile`
- `0x14007337b`: `ORIGIN: Directory and non-directory`
- `0x14007358b`: `API: Opening layer file`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::OpenBackingFile(
        PFLT_CALLBACK_DATA Data,
        struct _UNICODE_STRING *a2,
        PFLT_INSTANCE Instance,
        PHANDLE FileHandle,
        int a5)
{
  void *v9; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  const char *v11; // rax
  __int64 v12; // r8
  unsigned int v13; // ebx
  unsigned int v15; // eax
  NTSTATUS EcpListFromCallbackData; // r14d
  PFLT_IO_PARAMETER_BLOCK v17; // rdx
  ULONG Options; // ecx
  UCHAR OperationFlags; // r15
  int v20; // eax
  ULONG CreateOptions; // r14d
  bool v22; // zf
  HANDLE v23; // rcx
  ULONG Flags; // r15d
  PFLT_FILTER *v25; // rcx
  NTSTATUS v26; // edi
  void *v27; // rcx
  unsigned int v28; // eax
  struct _FLT_TAG_DATA_BUFFER *Information; // rdx
  __int16 v30; // r8
  PFILE_OBJECT TargetFileObject; // r9
  unsigned __int16 v32; // ax
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const struct _UNICODE_STRING *IoStatusBlock; // [rsp+30h] [rbp-D0h]
  void **v35; // [rsp+80h] [rbp-80h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  char v37; // [rsp+90h] [rbp-70h]
  struct _IO_DRIVER_CREATE_CONTEXT EcpList; // [rsp+98h] [rbp-68h] BYREF
  __int64 HostSilo; // [rsp+B8h] [rbp-48h]
  struct _IO_STATUS_BLOCK v40; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES v41; // [rsp+D0h] [rbp-30h] BYREF
  PVOID EcpContext; // [rsp+150h] [rbp+50h] BYREF

  if ( *FileHandle )
    FltClose(*FileHandle);
  *FileHandle = 0;
  v9 = FileHandle[1];
  FileHandle[1] = 0;
  if ( v9 )
    ObfDereferenceObject(v9);
  Iopb = Data->Iopb;
  if ( Iopb->MajorFunction )
  {
    v11 = "ORIGIN: Invalid operation type";
    v12 = 0x24700210D13LL;
    v13 = -1073741595;
LABEL_7:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)v13,
      a5,
      (struct UnionFs::StackEventTracer *)v12,
      (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
      v11,
      ObjectAttributes);
    return v13;
  }
  v15 = ((char)Iopb->OperationFlags >> 31) & 0xFFFFFFC0;
  *(_QWORD *)&v41.Length = 48;
  memset(&v41.Attributes + 1, 0, 20);
  v41.Attributes = v15 + 576;
  memset(&EcpList, 0, sizeof(EcpList));
  EcpList.Size = 40;
  v41.RootDirectory = 0;
  v41.ObjectName = a2;
  HostSilo = PsGetHostSilo();
  EcpListFromCallbackData = FltGetEcpListFromCallbackData(
                              *(PFLT_FILTER *)UnionFs::g_FilterState,
                              Data,
                              &EcpList.ExtraCreateParameter);
  if ( EcpListFromCallbackData >= 0 )
  {
    v17 = Data->Iopb;
    Options = v17->Parameters.Create.Options;
    if ( ((__int64)v17->Parameters.QueryEa.EaList & 0x41) == 0x41 )
    {
      v11 = "ORIGIN: Directory and non-directory";
      v12 = 0x24D00210D3FLL;
      v13 = -1073741811;
      goto LABEL_7;
    }
    OperationFlags = v17->OperationFlags;
    v20 = Options & 0x204041;
    v35 = FileHandle + 1;
    v37 = 1;
    CreateOptions = Options & 0x204041 | 0x20;
    v22 = (Options & 1) == 0;
    v23 = *FileHandle;
    v40 = 0;
    if ( v22 )
      CreateOptions = v20;
    Flags = OperationFlags & 4 | 0x808;
    FileObject = 0;
    if ( v23 )
      FltClose(v23);
    v25 = (PFLT_FILTER *)UnionFs::g_FilterState;
    *FileHandle = 0;
    v26 = FltCreateFileEx2(
            *v25,
            Instance,
            FileHandle,
            &FileObject,
            0xA0000000,
            &v41,
            &v40,
            0,
            0,
            7u,
            1u,
            CreateOptions,
            0,
            0,
            Flags,
            &EcpList);
    if ( v37 )
    {
      v27 = *v35;
      *v35 = FileObject;
      if ( v27 )
        ObfDereferenceObject(v27);
    }
    if ( v26 >= 0 )
    {
      return 0;
    }
    else
    {
      if ( v26 == -2147483603 )
      {
        if ( EcpList.ExtraCreateParameter )
        {
          EcpContext = 0;
          v28 = FltRemoveExtraCreateParameter(
                  *(PFLT_FILTER *)UnionFs::g_FilterState,
                  EcpList.ExtraCreateParameter,
                  &EcpType,
                  &EcpContext,
                  0);
          if ( (int)(v28 + 0x80000000) >= 0 && v28 != -1073741275 )
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)v28,
              a5,
              (struct UnionFs::StackEventTracer *)0x61800210D7FLL,
              (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
              "API: Removing ECP",
              ObjectAttributes);
        }
        Information = (struct _FLT_TAG_DATA_BUFFER *)v40.Information;
        if ( !v40.Information || *(_WORD *)(v40.Information + 4) > 0x4000u )
        {
          v11 = "ORIGIN: Bad symlink data";
          v12 = 0x33E00210D8ALL;
          v13 = -1073741192;
          goto LABEL_7;
        }
        v30 = *(_WORD *)(v40.Information + 6);
        TargetFileObject = Data->Iopb->TargetFileObject;
        v32 = TargetFileObject->FileName.Length - v30;
        if ( v32 )
        {
          if ( TargetFileObject->FileName.Buffer[((unsigned __int64)v32 >> 1) - 1] == 92 )
            *(_WORD *)(v40.Information + 6) = v30 + 2;
        }
        v26 = 260;
        Data->IoStatus.Information = Information->FileTag;
        Data->IoStatus.Status = 260;
        Data->TagData = Information;
        FltSetCallbackDataDirty(Data);
      }
      else
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v26,
          a5,
          (struct UnionFs::StackEventTracer *)0x24900210DA3LL,
          (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
          "API: Opening layer file",
          (const char *)a2,
          IoStatusBlock);
      }
      return (unsigned int)v26;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)EcpListFromCallbackData,
      a5,
      (struct UnionFs::StackEventTracer *)0x24800210D2FLL,
      (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
      "API: Getting ECP list from caller CBD",
      ObjectAttributes);
    return (unsigned int)EcpListFromCallbackData;
  }
}

```

## disassembly

```asm
0x140073224  push    rbp
0x140073226  push    rbx
0x140073227  push    rsi
0x140073228  push    rdi
0x140073229  push    r12
0x14007322b  push    r13
0x14007322d  push    r14
0x14007322f  push    r15
0x140073231  lea     rbp, [rsp-8]
0x140073236  sub     rsp, 108h
0x14007323d  mov     rbx, rcx
0x140073240  xor     r15d, r15d
0x140073243  mov     rcx, [r9]; FileHandle
0x140073246  mov     rdi, r9
0x140073249  mov     r13, r8
0x14007324c  mov     r12, rdx
0x14007324f  test    rcx, rcx
0x140073252  jz      short loc_140073260
0x140073254  call    cs:__imp_FltClose
0x14007325b  nop     dword ptr [rax+rax+00h]
0x140073260  lea     rsi, [rdi+8]
0x140073264  mov     [rdi], r15
0x140073267  mov     rcx, [rsi]; Object
0x14007326a  mov     [rsi], r15
0x14007326d  test    rcx, rcx
0x140073270  jz      short loc_14007327E
0x140073272  call    cs:__imp_ObfDereferenceObject
0x140073279  nop     dword ptr [rax+rax+00h]
0x14007327e  mov     rax, [rbx+10h]
0x140073282  cmp     [rax+4], r15b
0x140073286  jz      short loc_1400732BC
0x140073288  lea     rax, aOriginInvalidO_1; "ORIGIN: Invalid operation type"
0x14007328f  mov     r8, 24700210D13h; struct UnionFs::StackEventTracer *
0x140073299  mov     ebx, 0C00000E5h
0x14007329e  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x1400732a2  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x1400732a9  mov     ecx, ebx; this
0x1400732ab  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x1400732b0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400732b5  mov     eax, ebx
0x1400732b7  jmp     loc_1400735B8
0x1400732bc  movsx   eax, byte ptr [rax+6]
0x1400732c0  xorps   xmm1, xmm1
0x1400732c3  sar     eax, 1Fh
0x1400732c6  xorps   xmm0, xmm0
0x1400732c9  and     eax, 0FFFFFFC0h
0x1400732cc  mov     qword ptr [rbp+40h+var_70.Length], 30h ; '0'
0x1400732d4  add     eax, 240h
0x1400732d9  mov     dword ptr [rbp+40h+var_70+1Ch], r15d
0x1400732dd  mov     [rbp+40h+var_70.Attributes], eax
0x1400732e0  mov     eax, 28h ; '('
0x1400732e5  movups  xmmword ptr [rbp+40h+EcpList], xmm1
0x1400732e9  mov     word ptr [rbp+40h+EcpList], ax
0x1400732ed  mov     [rbp+40h+var_70.RootDirectory], r15
0x1400732f1  mov     [rbp+40h+var_70.ObjectName], r12
0x1400732f5  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x1400732fa  mov     [rbp+40h+var_88], 1
0x140073302  movups  [rbp+40h+var_98], xmm1
0x140073306  call    cs:__imp_PsGetHostSilo
0x14007330d  nop     dword ptr [rax+rax+00h]
0x140073312  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140073319  lea     r8, [rbp+40h+EcpList+8]; EcpList
0x14007331d  mov     [rbp+40h+var_88], rax
0x140073321  mov     rdx, rbx; CallbackData
0x140073324  mov     rcx, [rcx]; Filter
0x140073327  call    cs:__imp_FltGetEcpListFromCallbackData
0x14007332e  nop     dword ptr [rax+rax+00h]
0x140073333  mov     r14d, eax
0x140073336  test    eax, eax
0x140073338  jns     short loc_14007336B
0x14007333a  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x14007333e  lea     rax, aApiGettingEcpL; "API: Getting ECP list from caller CBD"
0x140073345  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x14007334c  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x140073351  mov     r8, 24800210D2Fh; struct UnionFs::StackEventTracer *
0x14007335b  mov     ecx, r14d; this
0x14007335e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140073363  mov     eax, r14d
0x140073366  jmp     loc_1400735B8
0x14007336b  mov     rdx, [rbx+10h]
0x14007336f  mov     ecx, [rdx+20h]
0x140073372  mov     eax, ecx
0x140073374  and     eax, 41h
0x140073377  cmp     al, 41h ; 'A'
0x140073379  jnz     short loc_140073396
0x14007337b  lea     rax, aOriginDirector_0; "ORIGIN: Directory and non-directory"
0x140073382  mov     r8, 24D00210D3Fh
0x14007338c  mov     ebx, 0C000000Dh
0x140073391  jmp     loc_14007329E
0x140073396  movzx   r15d, byte ptr [rdx+6]
0x14007339b  mov     eax, ecx
0x14007339d  and     eax, 204041h
0x1400733a2  mov     [rbp+40h+var_C0], rsi
0x1400733a6  mov     r14d, eax
0x1400733a9  mov     [rbp+40h+var_B0], 1
0x1400733ad  or      r14d, 20h
0x1400733b1  xorps   xmm0, xmm0
0x1400733b4  test    cl, 1
0x1400733b7  mov     rcx, [rdi]; FileHandle
0x1400733ba  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x1400733be  cmovz   r14d, eax
0x1400733c2  and     r15d, 4
0x1400733c6  xor     esi, esi
0x1400733c8  or      r15d, 808h
0x1400733cf  mov     [rbp+40h+FileObject], rsi
0x1400733d3  test    rcx, rcx
0x1400733d6  jz      short loc_1400733E4
0x1400733d8  call    cs:__imp_FltClose
0x1400733df  nop     dword ptr [rax+rax+00h]
0x1400733e4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400733eb  lea     rax, [rbp+40h+EcpList]
0x1400733ef  mov     [rsp+140h+DriverContext], rax; DriverContext
0x1400733f4  lea     r9, [rbp+40h+FileObject]; FileObject
0x1400733f8  mov     [rsp+140h+Flags], r15d; Flags
0x1400733fd  lea     rax, [rbp+40h+var_80]
0x140073401  mov     [rsp+140h+EaLength], esi; EaLength
0x140073405  mov     r8, rdi; FileHandle
0x140073408  mov     [rsp+140h+EaBuffer], rsi; EaBuffer
0x14007340d  mov     rdx, r13; Instance
0x140073410  mov     [rsp+140h+CreateOptions], r14d; CreateOptions
0x140073415  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x14007341d  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x140073425  mov     [rsp+140h+FileAttributes], esi; FileAttributes
0x140073429  mov     [rsp+140h+AllocationSize], rsi; AllocationSize
0x14007342e  mov     [rsp+140h+IoStatusBlock], rax; struct _UNICODE_STRING *
0x140073433  lea     rax, [rbp+40h+var_70]
0x140073437  mov     [rdi], rsi
0x14007343a  mov     rcx, [rcx]; Filter
0x14007343d  mov     [rsp+140h+ObjectAttributes], rax; char *
0x140073442  mov     [rsp+140h+DesiredAccess], 0A0000000h; DesiredAccess
0x14007344a  call    cs:__imp_FltCreateFileEx2
0x140073451  nop     dword ptr [rax+rax+00h]
0x140073456  mov     edi, eax
0x140073458  cmp     [rbp+40h+var_B0], sil
0x14007345c  jz      short loc_14007347D
0x14007345e  mov     r8, [rbp+40h+var_C0]
0x140073462  mov     rdx, [rbp+40h+FileObject]
0x140073466  mov     rcx, [r8]; Object
0x140073469  mov     [r8], rdx
0x14007346c  test    rcx, rcx
0x14007346f  jz      short loc_14007347D
0x140073471  call    cs:__imp_ObfDereferenceObject
0x140073478  nop     dword ptr [rax+rax+00h]
0x14007347d  test    edi, edi
0x14007347f  jns     loc_1400735B6
0x140073485  cmp     edi, 8000002Dh
0x14007348b  jnz     loc_140073587
0x140073491  mov     rdx, [rbp+40h+EcpList+8]; EcpList
0x140073495  test    rdx, rdx
0x140073498  jz      short loc_1400734FF
0x14007349a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400734a1  lea     r9, [rbp+40h+EcpContext]; EcpContext
0x1400734a5  lea     r8, EcpType; EcpType
0x1400734ac  mov     [rbp+40h+EcpContext], rsi
0x1400734b0  mov     qword ptr [rsp+140h+DesiredAccess], rsi; EcpContextSize
0x1400734b5  mov     rcx, [rcx]; Filter
0x1400734b8  call    cs:__imp_FltRemoveExtraCreateParameter
0x1400734bf  nop     dword ptr [rax+rax+00h]
0x1400734c4  mov     edx, 80000000h
0x1400734c9  lea     ecx, [rax+rdx]
0x1400734cc  test    edx, ecx
0x1400734ce  jnz     short loc_1400734FF
0x1400734d0  cmp     eax, 0C0000225h
0x1400734d5  jz      short loc_1400734FF
0x1400734d7  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x1400734db  lea     rcx, aApiRemovingEcp; "API: Removing ECP"
0x1400734e2  mov     qword ptr [rsp+140h+DesiredAccess], rcx; char *
0x1400734e7  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x1400734ee  mov     ecx, eax; this
0x1400734f0  mov     r8, 61800210D7Fh; struct UnionFs::StackEventTracer *
0x1400734fa  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400734ff  mov     rdx, [rbp+40h+var_80.Information]
0x140073503  test    rdx, rdx
0x140073506  jz      short loc_14007356C
0x140073508  mov     eax, 4000h
0x14007350d  cmp     [rdx+4], ax
0x140073511  ja      short loc_14007356C
0x140073513  mov     rax, [rbx+10h]
0x140073517  movzx   r8d, word ptr [rdx+6]
0x14007351c  mov     r9, [rax+8]
0x140073520  movzx   eax, word ptr [r9+58h]
0x140073525  sub     ax, r8w
0x140073529  jz      short loc_140073547
0x14007352b  movzx   ecx, ax
0x14007352e  mov     rax, [r9+60h]
0x140073532  shr     rcx, 1
0x140073535  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007353b  jnz     short loc_140073547
0x14007353d  add     r8w, 2
0x140073542  mov     [rdx+6], r8w
0x140073547  mov     eax, [rdx]
0x140073549  mov     edi, 104h
0x14007354e  mov     rcx, rbx; Data
0x140073551  mov     [rbx+20h], rax
0x140073555  mov     [rbx+18h], edi
0x140073558  mov     [rbx+28h], rdx
0x14007355c  call    cs:__imp_FltSetCallbackDataDirty
0x140073563  nop     dword ptr [rax+rax+00h]
0x140073568  mov     eax, edi
0x14007356a  jmp     short loc_1400735B8
0x14007356c  lea     rax, aOriginBadSymli; "ORIGIN: Bad symlink data"
0x140073573  mov     r8, 33E00210D8Ah
0x14007357d  mov     ebx, 0C0000278h
0x140073582  jmp     loc_14007329E
0x140073587  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x14007358b  lea     rax, aApiOpeningLaye; "API: Opening layer file"
0x140073592  mov     [rsp+140h+ObjectAttributes], r12; char *
0x140073597  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x14007359e  mov     r8, 24900210DA3h; struct UnionFs::StackEventTracer *
0x1400735a8  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x1400735ad  mov     ecx, edi; this
0x1400735af  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x1400735b4  jmp     short loc_140073568
0x1400735b6  xor     eax, eax
0x1400735b8  add     rsp, 108h
0x1400735bf  pop     r15
0x1400735c1  pop     r14
0x1400735c3  pop     r13
0x1400735c5  pop     r12
0x1400735c7  pop     rdi
0x1400735c8  pop     rsi
0x1400735c9  pop     rbx
0x1400735ca  pop     rbp
0x1400735cb  retn
```
