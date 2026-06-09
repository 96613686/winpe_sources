# UnionFs::Utils::OpenBackingFile(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,_FLT_INSTANCE const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140073034`
- end: `0x1400733a9`
- name: `?OpenBackingFile@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@_N@Z`
- size: `885`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, char *, PFLT_INSTANCE Instance, PHANDLE FileHandle, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x14003ff88`

## callees

- `0x140056a50`
- `0x140056a88`
- `0x140056ac4`
- `0x140073034`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x140073116`
- `ntoskrnl!PsGetHostSilo` at `0x140073116`
- `ntoskrnl!ObfDereferenceObject` at `0x140073082`
- `ntoskrnl!ObfDereferenceObject` at `0x140073281`
- `ntoskrnl!ObfDereferenceObject` at `0x140073082`
- `ntoskrnl!ObfDereferenceObject` at `0x140073281`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400732c8`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x1400732c8`
- `FLTMGR!FltCreateFileEx2` at `0x14007325a`
- `FLTMGR!FltCreateFileEx2` at `0x14007325a`
- `FLTMGR!FltClose` at `0x140073064`
- `FLTMGR!FltClose` at `0x1400731e8`
- `FLTMGR!FltClose` at `0x140073064`
- `FLTMGR!FltClose` at `0x1400731e8`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140073137`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140073137`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140073338`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140073338`

## string_xrefs

- `0x140073348`: `ORIGIN: Bad symlink data`
- `0x1400730b2`: `UnionFs::Utils::OpenBackingFile`
- `0x140073155`: `UnionFs::Utils::OpenBackingFile`
- `0x1400732f7`: `UnionFs::Utils::OpenBackingFile`
- `0x140073373`: `UnionFs::Utils::OpenBackingFile`
- `0x14007318b`: `ORIGIN: Directory and non-directory`
- `0x140073367`: `API: Opening layer file`

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
  ULONG_PTR v29; // rax
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const struct _UNICODE_STRING *IoStatusBlock; // [rsp+30h] [rbp-D0h]
  void **v32; // [rsp+80h] [rbp-80h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  char v34; // [rsp+90h] [rbp-70h]
  struct _IO_DRIVER_CREATE_CONTEXT EcpList; // [rsp+98h] [rbp-68h] BYREF
  __int64 HostSilo; // [rsp+B8h] [rbp-48h]
  struct _IO_STATUS_BLOCK v37; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES v38; // [rsp+D0h] [rbp-30h] BYREF
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
    v12 = 0x24700210CE6LL;
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
  *(_QWORD *)&v38.Length = 48;
  memset(&v38.Attributes + 1, 0, 20);
  v38.Attributes = v15 + 576;
  memset(&EcpList, 0, sizeof(EcpList));
  EcpList.Size = 40;
  v38.RootDirectory = 0;
  v38.ObjectName = a2;
  HostSilo = PsGetHostSilo(v9, a2);
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
      v12 = 0x24D00210D12LL;
      v13 = -1073741811;
      goto LABEL_7;
    }
    OperationFlags = v17->OperationFlags;
    v20 = Options & 0x204041;
    v32 = FileHandle + 1;
    v34 = 1;
    CreateOptions = Options & 0x204041 | 0x20;
    v22 = (Options & 1) == 0;
    v23 = *FileHandle;
    v37 = 0;
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
            &v38,
            &v37,
            0,
            0,
            7u,
            1u,
            CreateOptions,
            0,
            0,
            Flags,
            &EcpList);
    if ( v34 )
    {
      v27 = *v32;
      *v32 = FileObject;
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
              (struct UnionFs::StackEventTracer *)0x61800210D52LL,
              (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
              "API: Removing ECP",
              ObjectAttributes);
        }
        if ( !v37.Information || *(_WORD *)(v37.Information + 4) > 0x4000u )
        {
          v11 = "ORIGIN: Bad symlink data";
          v12 = 0x33E00210D5DLL;
          v13 = -1073741192;
          goto LABEL_7;
        }
        v29 = *(unsigned int *)v37.Information;
        v26 = 260;
        Data->TagData = (struct _FLT_TAG_DATA_BUFFER *)v37.Information;
        Data->IoStatus.Information = v29;
        Data->IoStatus.Status = 260;
        FltSetCallbackDataDirty(Data);
      }
      else
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v26,
          a5,
          (struct UnionFs::StackEventTracer *)0x24900210D6ALL,
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
      (struct UnionFs::StackEventTracer *)0x24800210D02LL,
      (unsigned __int64)"UnionFs::Utils::OpenBackingFile",
      "API: Getting ECP list from caller CBD",
      ObjectAttributes);
    return (unsigned int)EcpListFromCallbackData;
  }
}

```

## disassembly

```asm
0x140073034  push    rbp
0x140073036  push    rbx
0x140073037  push    rsi
0x140073038  push    rdi
0x140073039  push    r12
0x14007303b  push    r13
0x14007303d  push    r14
0x14007303f  push    r15
0x140073041  lea     rbp, [rsp-8]
0x140073046  sub     rsp, 108h
0x14007304d  mov     rbx, rcx
0x140073050  xor     r15d, r15d
0x140073053  mov     rcx, [r9]; FileHandle
0x140073056  mov     rdi, r9
0x140073059  mov     r13, r8
0x14007305c  mov     r12, rdx
0x14007305f  test    rcx, rcx
0x140073062  jz      short loc_140073070
0x140073064  call    cs:__imp_FltClose
0x14007306b  nop     dword ptr [rax+rax+00h]
0x140073070  lea     rsi, [rdi+8]
0x140073074  mov     [rdi], r15
0x140073077  mov     rcx, [rsi]; Object
0x14007307a  mov     [rsi], r15
0x14007307d  test    rcx, rcx
0x140073080  jz      short loc_14007308E
0x140073082  call    cs:__imp_ObfDereferenceObject
0x140073089  nop     dword ptr [rax+rax+00h]
0x14007308e  mov     rax, [rbx+10h]
0x140073092  cmp     [rax+4], r15b
0x140073096  jz      short loc_1400730CC
0x140073098  lea     rax, aOriginInvalidO_1; "ORIGIN: Invalid operation type"
0x14007309f  mov     r8, 24700210CE6h; struct UnionFs::StackEventTracer *
0x1400730a9  mov     ebx, 0C00000E5h
0x1400730ae  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x1400730b2  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x1400730b9  mov     ecx, ebx; this
0x1400730bb  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x1400730c0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400730c5  mov     eax, ebx
0x1400730c7  jmp     loc_140073394
0x1400730cc  movsx   eax, byte ptr [rax+6]
0x1400730d0  xorps   xmm1, xmm1
0x1400730d3  sar     eax, 1Fh
0x1400730d6  xorps   xmm0, xmm0
0x1400730d9  and     eax, 0FFFFFFC0h
0x1400730dc  mov     qword ptr [rbp+40h+var_70.Length], 30h ; '0'
0x1400730e4  add     eax, 240h
0x1400730e9  mov     dword ptr [rbp+40h+var_70+1Ch], r15d
0x1400730ed  mov     [rbp+40h+var_70.Attributes], eax
0x1400730f0  mov     eax, 28h ; '('
0x1400730f5  movups  xmmword ptr [rbp+40h+EcpList], xmm1
0x1400730f9  mov     word ptr [rbp+40h+EcpList], ax
0x1400730fd  mov     [rbp+40h+var_70.RootDirectory], r15
0x140073101  mov     [rbp+40h+var_70.ObjectName], r12
0x140073105  movdqu  xmmword ptr [rbp+40h+var_70.SecurityDescriptor], xmm0
0x14007310a  mov     [rbp+40h+var_88], 1
0x140073112  movups  [rbp+40h+var_98], xmm1
0x140073116  call    cs:__imp_PsGetHostSilo
0x14007311d  nop     dword ptr [rax+rax+00h]
0x140073122  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140073129  lea     r8, [rbp+40h+EcpList+8]; EcpList
0x14007312d  mov     [rbp+40h+var_88], rax
0x140073131  mov     rdx, rbx; CallbackData
0x140073134  mov     rcx, [rcx]; Filter
0x140073137  call    cs:__imp_FltGetEcpListFromCallbackData
0x14007313e  nop     dword ptr [rax+rax+00h]
0x140073143  mov     r14d, eax
0x140073146  test    eax, eax
0x140073148  jns     short loc_14007317B
0x14007314a  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x14007314e  lea     rax, aApiGettingEcpL; "API: Getting ECP list from caller CBD"
0x140073155  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x14007315c  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x140073161  mov     r8, 24800210D02h; struct UnionFs::StackEventTracer *
0x14007316b  mov     ecx, r14d; this
0x14007316e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140073173  mov     eax, r14d
0x140073176  jmp     loc_140073394
0x14007317b  mov     rdx, [rbx+10h]
0x14007317f  mov     ecx, [rdx+20h]
0x140073182  mov     eax, ecx
0x140073184  and     eax, 41h
0x140073187  cmp     al, 41h ; 'A'
0x140073189  jnz     short loc_1400731A6
0x14007318b  lea     rax, aOriginDirector_0; "ORIGIN: Directory and non-directory"
0x140073192  mov     r8, 24D00210D12h
0x14007319c  mov     ebx, 0C000000Dh
0x1400731a1  jmp     loc_1400730AE
0x1400731a6  movzx   r15d, byte ptr [rdx+6]
0x1400731ab  mov     eax, ecx
0x1400731ad  and     eax, 204041h
0x1400731b2  mov     [rbp+40h+var_C0], rsi
0x1400731b6  mov     r14d, eax
0x1400731b9  mov     [rbp+40h+var_B0], 1
0x1400731bd  or      r14d, 20h
0x1400731c1  xorps   xmm0, xmm0
0x1400731c4  test    cl, 1
0x1400731c7  mov     rcx, [rdi]; FileHandle
0x1400731ca  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x1400731ce  cmovz   r14d, eax
0x1400731d2  and     r15d, 4
0x1400731d6  xor     esi, esi
0x1400731d8  or      r15d, 808h
0x1400731df  mov     [rbp+40h+FileObject], rsi
0x1400731e3  test    rcx, rcx
0x1400731e6  jz      short loc_1400731F4
0x1400731e8  call    cs:__imp_FltClose
0x1400731ef  nop     dword ptr [rax+rax+00h]
0x1400731f4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400731fb  lea     rax, [rbp+40h+EcpList]
0x1400731ff  mov     [rsp+140h+DriverContext], rax; DriverContext
0x140073204  lea     r9, [rbp+40h+FileObject]; FileObject
0x140073208  mov     [rsp+140h+Flags], r15d; Flags
0x14007320d  lea     rax, [rbp+40h+var_80]
0x140073211  mov     [rsp+140h+EaLength], esi; EaLength
0x140073215  mov     r8, rdi; FileHandle
0x140073218  mov     [rsp+140h+EaBuffer], rsi; EaBuffer
0x14007321d  mov     rdx, r13; Instance
0x140073220  mov     [rsp+140h+CreateOptions], r14d; CreateOptions
0x140073225  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x14007322d  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x140073235  mov     [rsp+140h+FileAttributes], esi; FileAttributes
0x140073239  mov     [rsp+140h+AllocationSize], rsi; AllocationSize
0x14007323e  mov     [rsp+140h+IoStatusBlock], rax; struct _UNICODE_STRING *
0x140073243  lea     rax, [rbp+40h+var_70]
0x140073247  mov     [rdi], rsi
0x14007324a  mov     rcx, [rcx]; Filter
0x14007324d  mov     [rsp+140h+ObjectAttributes], rax; char *
0x140073252  mov     [rsp+140h+DesiredAccess], 0A0000000h; DesiredAccess
0x14007325a  call    cs:__imp_FltCreateFileEx2
0x140073261  nop     dword ptr [rax+rax+00h]
0x140073266  mov     edi, eax
0x140073268  cmp     [rbp+40h+var_B0], sil
0x14007326c  jz      short loc_14007328D
0x14007326e  mov     r8, [rbp+40h+var_C0]
0x140073272  mov     rdx, [rbp+40h+FileObject]
0x140073276  mov     rcx, [r8]; Object
0x140073279  mov     [r8], rdx
0x14007327c  test    rcx, rcx
0x14007327f  jz      short loc_14007328D
0x140073281  call    cs:__imp_ObfDereferenceObject
0x140073288  nop     dword ptr [rax+rax+00h]
0x14007328d  test    edi, edi
0x14007328f  jns     loc_140073392
0x140073295  cmp     edi, 8000002Dh
0x14007329b  jnz     loc_140073363
0x1400732a1  mov     rdx, [rbp+40h+EcpList+8]; EcpList
0x1400732a5  test    rdx, rdx
0x1400732a8  jz      short loc_14007330F
0x1400732aa  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400732b1  lea     r9, [rbp+40h+EcpContext]; EcpContext
0x1400732b5  lea     r8, EcpType; EcpType
0x1400732bc  mov     [rbp+40h+EcpContext], rsi
0x1400732c0  mov     qword ptr [rsp+140h+DesiredAccess], rsi; EcpContextSize
0x1400732c5  mov     rcx, [rcx]; Filter
0x1400732c8  call    cs:__imp_FltRemoveExtraCreateParameter
0x1400732cf  nop     dword ptr [rax+rax+00h]
0x1400732d4  mov     edx, 80000000h
0x1400732d9  lea     ecx, [rax+rdx]
0x1400732dc  test    edx, ecx
0x1400732de  jnz     short loc_14007330F
0x1400732e0  cmp     eax, 0C0000225h
0x1400732e5  jz      short loc_14007330F
0x1400732e7  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x1400732eb  lea     rcx, aApiRemovingEcp; "API: Removing ECP"
0x1400732f2  mov     qword ptr [rsp+140h+DesiredAccess], rcx; char *
0x1400732f7  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x1400732fe  mov     ecx, eax; this
0x140073300  mov     r8, 61800210D52h; struct UnionFs::StackEventTracer *
0x14007330a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007330f  mov     rcx, [rbp+40h+var_80.Information]
0x140073313  test    rcx, rcx
0x140073316  jz      short loc_140073348
0x140073318  mov     eax, 4000h
0x14007331d  cmp     [rcx+4], ax
0x140073321  ja      short loc_140073348
0x140073323  mov     eax, [rcx]
0x140073325  mov     edi, 104h
0x14007332a  mov     [rbx+28h], rcx
0x14007332e  mov     rcx, rbx; Data
0x140073331  mov     [rbx+20h], rax
0x140073335  mov     [rbx+18h], edi
0x140073338  call    cs:__imp_FltSetCallbackDataDirty
0x14007333f  nop     dword ptr [rax+rax+00h]
0x140073344  mov     eax, edi
0x140073346  jmp     short loc_140073394
0x140073348  lea     rax, aOriginBadSymli; "ORIGIN: Bad symlink data"
0x14007334f  mov     r8, 33E00210D5Dh
0x140073359  mov     ebx, 0C0000278h
0x14007335e  jmp     loc_1400730AE
0x140073363  mov     rdx, qword ptr [rbp+40h+arg_20]; int
0x140073367  lea     rax, aApiOpeningLaye; "API: Opening layer file"
0x14007336e  mov     [rsp+140h+ObjectAttributes], r12; char *
0x140073373  lea     r9, aUnionfsUtilsOp_2; "UnionFs::Utils::OpenBackingFile"
0x14007337a  mov     r8, 24900210D6Ah; struct UnionFs::StackEventTracer *
0x140073384  mov     qword ptr [rsp+140h+DesiredAccess], rax; char *
0x140073389  mov     ecx, edi; this
0x14007338b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140073390  jmp     short loc_140073344
0x140073392  xor     eax, eax
0x140073394  add     rsp, 108h
0x14007339b  pop     r15
0x14007339d  pop     r14
0x14007339f  pop     r13
0x1400733a1  pop     r12
0x1400733a3  pop     rdi
0x1400733a4  pop     rsi
0x1400733a5  pop     rbx
0x1400733a6  pop     rbp
0x1400733a7  retn
```
