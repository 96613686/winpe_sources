# UnionFs::Utils::OpenOrCreateInternalFile(_FLT_INSTANCE const &,_UNICODE_STRING const &,UnionFs::Utils::OpenOrCreateParams,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &)

- ea: `0x1400735d4`
- end: `0x1400749e1`
- name: `?OpenOrCreateInternalFile@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@UOpenOrCreateParams@12@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `5133`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400517b0`
- `0x140051f74`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001c08`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140067b48`
- `0x1400735d4`
- `0x14007599c`
- `0x1400796c4`
- `0x14007971c`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400738f3`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400738f3`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400737e2`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400737e2`
- `ntoskrnl!RtlInitializeSid` at `0x1400736b8`
- `ntoskrnl!RtlInitializeSid` at `0x1400736b8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140073713`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140073713`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400738bf`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400738bf`
- `ntoskrnl!RtlGetAce` at `0x140073de4`
- `ntoskrnl!RtlGetAce` at `0x140073de4`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140073d2a`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140073d2a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140073653`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140073653`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140073887`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140073887`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140073d62`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140073d62`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140073ccd`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140073ccd`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140073926`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140073926`
- `ntoskrnl!RtlCreateAcl` at `0x14007384a`
- `ntoskrnl!RtlCreateAcl` at `0x14007384a`
- `ntoskrnl!RtlEqualSid` at `0x140073e87`
- `ntoskrnl!RtlEqualSid` at `0x140073ed9`
- `ntoskrnl!RtlEqualSid` at `0x140073f83`
- `ntoskrnl!RtlEqualSid` at `0x1400740ee`
- `ntoskrnl!RtlEqualSid` at `0x14007425b`
- `ntoskrnl!RtlEqualSid` at `0x1400745e2`
- `ntoskrnl!RtlEqualSid` at `0x140073e87`
- `ntoskrnl!RtlEqualSid` at `0x140073ed9`
- `ntoskrnl!RtlEqualSid` at `0x140073f83`
- `ntoskrnl!RtlEqualSid` at `0x1400740ee`
- `ntoskrnl!RtlEqualSid` at `0x14007425b`
- `ntoskrnl!RtlEqualSid` at `0x1400745e2`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140073810`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140073810`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007377f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007377f`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140073da5`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140073da5`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140073e27`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140073e27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400736fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073cb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007498a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400749b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400736fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073cb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007498a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400749b2`
- `ntoskrnl!PsGetHostSilo` at `0x14007398d`
- `ntoskrnl!PsGetHostSilo` at `0x14007398d`
- `ntoskrnl!ObfDereferenceObject` at `0x140073640`
- `ntoskrnl!ObfDereferenceObject` at `0x140073a72`
- `ntoskrnl!ObfDereferenceObject` at `0x140073640`
- `ntoskrnl!ObfDereferenceObject` at `0x140073a72`
- `FLTMGR!FltSetSecurityObject` at `0x140074958`
- `FLTMGR!FltSetSecurityObject` at `0x140074958`
- `FLTMGR!FltCreateFileEx2` at `0x140073a45`
- `FLTMGR!FltCreateFileEx2` at `0x140073a45`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400737c4`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14007499e`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400737c4`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14007499e`
- `FLTMGR!FltClose` at `0x14007361e`
- `FLTMGR!FltClose` at `0x1400739d1`
- `FLTMGR!FltClose` at `0x14007361e`
- `FLTMGR!FltClose` at `0x1400739d1`
- `FLTMGR!FltFsControlFile` at `0x140073af5`
- `FLTMGR!FltFsControlFile` at `0x140073af5`

## string_xrefs

- `0x140073686`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x1400736db`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x140073759`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x1400737a2`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x140073a9c`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x140073673`: `ORIGIN: Allocating System SID buffer`
- `0x1400736ca`: `API: Initializing SID`
- `0x14007385f`: `API: Initializing DACL`
- `0x1400738d1`: `API: Setting DACL in SD`
- `0x140073899`: `API: Adding System access ACE`
- `0x140073905`: `API: Setting null SACL in SD`
- `0x140073a82`: `API: Open/Create internal file`
- `0x140073db7`: `API: Getting DACL from existing SD`
- `0x140073e39`: `API: Getting SACL from existing SD`
- `0x140073df6`: `API: Getting ACE from existing DACL`
- `0x140073e97`: `API: Comparing owner in existing SD`
- `0x140073ee9`: `API: Comparing group in existing SD`
- `0x140073f29`: `ORIGIN: NULL DACL`
- `0x140073f0a`: `ORIGIN: No DACL`
- `0x140073f93`: `API: Comparing ACE SID`
- `0x140074011`: `ORIGIN: Non-NULL SACL`
- `0x140073fee`: `ORIGIN: No SACL`
- `0x140074159`: `Owner in existing security descriptor on internal file is not System.`
- `0x140074076`: `No owner in existing security descriptor on internal file.`
- `0x1400742c6`: `Group in existing security descriptor on internal file is not System.`
- `0x14007420a`: `No group in existing security descriptor on internal file.`
- `0x140074427`: `NULL DACL in existing security descriptor on internal file.`
- `0x140074375`: `No DACL in existing security descriptor on internal file.`
- `0x14007458d`: `ACE type in existing security descriptor on internal file is not ACCESS_ALLOWED_ACE_TYPE.`
- `0x1400744db`: `ACE count in existing security descriptor on internal file is not 1.`
- `0x140074703`: `ACE mask in existing security descriptor on internal file does not grant read/write access.`
- `0x14007464d`: `ACE SID in existing security descriptor on internal file is not System.`
- `0x14007485a`: `Non-NULL SACL in existing security descriptor on internal file.`
- `0x1400747b2`: `No SACL in existing security descriptor on internal file.`
- `0x1400748ec`: `Replacing existing security descriptor on internal file.`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::OpenOrCreateInternalFile(
        struct _FLT_INSTANCE *a1,
        struct _UNICODE_STRING *a2,
        struct _ACL *a3,
        __int64 a4,
        int a5)
{
  HANDLE v6; // rcx
  void *v8; // rcx
  ULONG v9; // eax
  unsigned __int8 *v10; // rdi
  NTSTATUS Acl; // edi
  NTSTATUS v12; // ebx
  unsigned int v14; // r12d
  struct _ACL *v15; // rbx
  const char *v16; // rax
  __int64 v17; // r8
  PSID v18; // r14
  ULONG v19; // r14d
  ACCESS_MASK DesiredAccess; // r12d
  int v21; // edi
  ULONG CreateOptions; // edi
  PFLT_FILTER *v23; // rcx
  struct _FLT_INSTANCE *v24; // r14
  void *v25; // rdx
  PFILE_OBJECT *v26; // r12
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  struct _FILE_OBJECT *v31; // rdx
  PVOID v32; // rcx
  PVOID v33; // r14
  const char *v34; // rax
  __int64 v35; // r8
  int v36; // r9d
  const char *v37; // rax
  __int64 v38; // r8
  PSID v39; // rdi
  bool v40; // zf
  const struct _UNICODE_STRING *v41; // rcx
  PSID v42; // rdi
  int v43; // r8d
  const struct _UNICODE_STRING *v44; // rcx
  const struct _UNICODE_STRING *v45; // rcx
  int v46; // r8d
  const struct _UNICODE_STRING *v47; // rcx
  const struct _UNICODE_STRING *v48; // rcx
  const struct _UNICODE_STRING *v49; // rcx
  const struct _UNICODE_STRING *v50; // rcx
  const struct _UNICODE_STRING *v51; // rcx
  int v52; // r8d
  const struct _UNICODE_STRING *v53; // rcx
  const struct _UNICODE_STRING *v54; // rcx
  const struct _UNICODE_STRING *v55; // rcx
  const struct _UNICODE_STRING *v56; // rcx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  ULONG CreateDisposition; // [rsp+50h] [rbp-B0h]
  unsigned __int8 OwnerDefaulted; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 DaclPresent; // [rsp+81h] [rbp-7Fh] BYREF
  unsigned __int8 SaclPresent[6]; // [rsp+82h] [rbp-7Eh] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  const char *v63; // [rsp+90h] [rbp-70h] BYREF
  const char *v64; // [rsp+98h] [rbp-68h] BYREF
  const char *v65; // [rsp+A0h] [rbp-60h] BYREF
  const char *v66; // [rsp+A8h] [rbp-58h] BYREF
  PACL Sacl; // [rsp+B0h] [rbp-50h] BYREF
  PVOID Ace; // [rsp+B8h] [rbp-48h] BYREF
  PACL Dacl; // [rsp+C0h] [rbp-40h] BYREF
  PSID Owner; // [rsp+C8h] [rbp-38h] BYREF
  PSID Group; // [rsp+D0h] [rbp-30h] BYREF
  PSID Sid; // [rsp+D8h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+E0h] [rbp-20h] BYREF
  PFLT_INSTANCE Instance; // [rsp+E8h] [rbp-18h]
  void **v75; // [rsp+F0h] [rbp-10h]
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp-8h] BYREF
  char v77; // [rsp+100h] [rbp+0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES v79; // [rsp+118h] [rbp+18h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+148h] [rbp+48h] BYREF
  __int64 HostSilo; // [rsp+168h] [rbp+68h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+170h] [rbp+70h] BYREF

  Instance = a1;
  v6 = *(HANDLE *)a4;
  Sacl = a3;
  if ( v6 )
    FltClose(v6);
  *(_QWORD *)a4 = 0;
  v8 = *(void **)(a4 + 8);
  Dacl = (PACL)(a4 + 8);
  *(_QWORD *)(a4 + 8) = 0;
  if ( v8 )
    ObfDereferenceObject(v8);
  v9 = RtlLengthRequiredSid(1u);
  utl::make_unique_pool<enum gsl::byte [0],256,1685276245,0>(&Sid, v9);
  v10 = (unsigned __int8 *)Sid;
  if ( !Sid )
  {
    Acl = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x52200210DDDLL,
      (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
      "ORIGIN: Allocating System SID buffer",
      ObjectAttributes);
    return (unsigned int)Acl;
  }
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v12 = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  if ( v12 >= 0 )
  {
    *RtlSubAuthoritySid(v10, 0) = 18;
    v14 = 4 * v10[1] + 68;
    utl::make_unique_pool<enum gsl::byte [0],256,1685276245,0>(&SecurityDescriptor, v14);
    v15 = (struct _ACL *)SecurityDescriptor;
    if ( !SecurityDescriptor )
    {
      Acl = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a5,
        (struct UnionFs::StackEventTracer *)0x52300210DF4LL,
        (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
        "ORIGIN: Allocating SD buffer",
        ObjectAttributes);
LABEL_199:
      ExFreePoolWithTag(Sid, 0);
      return (unsigned int)Acl;
    }
    Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( Acl < 0 )
    {
      v16 = "API: Initializing SD";
      v17 = 0x52400210DFDLL;
LABEL_15:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Acl,
        a5,
        (struct UnionFs::StackEventTracer *)v17,
        (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
        v16,
        ObjectAttributes);
      goto LABEL_16;
    }
    v18 = Sid;
    Acl = RtlSetOwnerSecurityDescriptor(v15, Sid, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting owner in SD";
      v17 = 0x52500210E04LL;
      goto LABEL_15;
    }
    Acl = RtlSetGroupSecurityDescriptor(v15, v18, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting group in SD";
      v17 = 0x52600210E09LL;
      goto LABEL_15;
    }
    Acl = RtlCreateAcl(v15 + 5, v14 - 40, 2u);
    if ( Acl < 0 )
    {
      v16 = "API: Initializing DACL";
      v17 = 0x52700210E13LL;
      goto LABEL_15;
    }
    Acl = RtlAddAccessAllowedAce(v15 + 5, 2u, 0x12019Fu, Sid);
    if ( Acl < 0 )
    {
      v16 = "API: Adding System access ACE";
      v17 = 0x52800210E1BLL;
      goto LABEL_15;
    }
    Acl = RtlSetDaclSecurityDescriptor(v15, 1u, v15 + 5, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting DACL in SD";
      v17 = 0x52900210E21LL;
      goto LABEL_15;
    }
    Acl = RtlSetSaclSecurityDescriptor(v15, 1u, 0, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting null SACL in SD";
      v17 = 0x52E00210E28LL;
      goto LABEL_15;
    }
    Acl = RtlSetControlSecurityDescriptor(v15, 0x3000u, 0x3000u);
    if ( Acl < 0 )
    {
      v16 = "API: Setting SD control flags";
      v17 = 0x4CA00210E30LL;
      goto LABEL_15;
    }
    *(_QWORD *)&v79.Length = 48;
    *(_QWORD *)&v79.Attributes = 576;
    v79.RootDirectory = 0;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    v79.ObjectName = a2;
    v79.SecurityDescriptor = v15;
    v79.SecurityQualityOfService = 0;
    IoStatusBlock = 0;
    HostSilo = 1;
    HostSilo = PsGetHostSilo();
    v19 = *(_DWORD *)&Sacl->AceCount;
    DesiredAccess = *(_DWORD *)&Sacl->AclRevision;
    v21 = -(Sacl[1].AclRevision != 0);
    v75 = (void **)(a4 + 8);
    CreateOptions = (v21 & 8) + 32;
    FileObject = 0;
    v77 = 1;
    if ( *(_QWORD *)a4 )
      FltClose(*(HANDLE *)a4);
    v23 = (PFLT_FILTER *)UnionFs::g_FilterState;
    CreateDisposition = v19;
    v24 = Instance;
    *(_QWORD *)a4 = 0;
    Acl = FltCreateFileEx2(
            *v23,
            v24,
            (PHANDLE)a4,
            &FileObject,
            DesiredAccess,
            &v79,
            &IoStatusBlock,
            0,
            6u,
            1u,
            CreateDisposition,
            CreateOptions,
            0,
            0,
            0,
            &DriverContext);
    if ( v77 )
    {
      v25 = *v75;
      *v75 = FileObject;
      if ( v25 )
        ObfDereferenceObject(v25);
    }
    if ( Acl < 0 )
    {
      v16 = "API: Open/Create internal file";
      v17 = 0x76300210E5DLL;
      goto LABEL_15;
    }
    if ( *(_DWORD *)&Sacl[1].AceCount != 28 || (IoStatusBlock.Information & 0xFFFFFFFFFFFFFFFDuLL) != 0 )
    {
      v26 = (PFILE_OBJECT *)Dacl;
    }
    else
    {
      SecurityDescriptor = (PSECURITY_DESCRIPTOR)2;
      v26 = (PFILE_OBJECT *)Dacl;
      Acl = FltFsControlFile(v24, *(PFILE_OBJECT *)Dacl, 0x9C280u, &SecurityDescriptor, 8u, 0, 0, 0);
      if ( Acl < 0 )
      {
        if ( (unsigned int)Feature_UnionFs_EnforceIntegrity__private_IsEnabledDeviceUsageNoInline() )
        {
          v16 = "API: Setting ReFS integrity";
          v17 = 0x2F700210E7ALL;
          goto LABEL_15;
        }
        if ( (unsigned int)dword_14009E178 > 3
          && (qword_14009E188 & 0x8000) != 0
          && (qword_14009E190 & 0x8000) == qword_14009E190 )
        {
          LODWORD(Ace) = Acl;
          Sacl = (PACL)"onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          LODWORD(P) = 3712;
          Owner = "Failed to enable ReFS integrity stream on persistence file (best-effort)";
          Group = (PSID)"UnionFs::Utils::OpenOrCreateInternalFile";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            0x8000,
            (unsigned int)&dword_140099C04,
            v29,
            v30,
            (__int64)&Owner,
            (__int64)&Group,
            (__int64)&Sacl,
            (__int64)&P,
            (__int64)&Ace);
        }
      }
      else if ( (unsigned int)dword_14009E178 > 5
             && (qword_14009E188 & 0x8000) != 0
             && (qword_14009E190 & 0x8000) == qword_14009E190 )
      {
        LODWORD(Ace) = 3702;
        Sacl = (PACL)"onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        Group = (PSID)"UnionFs::Utils::OpenOrCreateInternalFile";
        Owner = "ReFS integrity stream enabled on persistence file";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0x8000,
          (unsigned int)qword_140099CF8,
          v27,
          v28,
          (__int64)&Owner,
          (__int64)&Group,
          (__int64)&Sacl,
          (__int64)&Ace);
      }
    }
    if ( IoStatusBlock.Information != 1 )
    {
LABEL_196:
      if ( v15 )
        FltFreeSecurityDescriptor(v15);
      Acl = 0;
      goto LABEL_199;
    }
    v31 = *v26;
    P = 0;
    Acl = UnionFs::Utils::QuerySecurity(v24, v31, 0xFu);
    if ( Acl < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Acl,
        a5,
        (struct UnionFs::StackEventTracer *)0x52A00210E8BLL,
        (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
        "PUSH: Querying existing SD",
        ObjectAttributes);
      v32 = P;
      if ( !P )
        goto LABEL_16;
      goto LABEL_56;
    }
    v33 = P;
    if ( !RtlValidSecurityDescriptor(P) )
    {
      v34 = "API: Validating existing SD";
      v35 = 0x52B00210E92LL;
      Acl = -1073741703;
LABEL_59:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Acl,
        a5,
        (struct UnionFs::StackEventTracer *)v35,
        (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
        v34,
        ObjectAttributes);
LABEL_60:
      if ( !v33 )
      {
LABEL_16:
        if ( v15 )
          FltFreeSecurityDescriptor(v15);
        goto LABEL_199;
      }
      v32 = v33;
LABEL_56:
      ExFreePoolWithTag(v32, 0);
      goto LABEL_16;
    }
    OwnerDefaulted = 0;
    Owner = 0;
    Acl = RtlGetOwnerSecurityDescriptor(v33, &Owner, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting owner from existing SD";
      v35 = 0x52C00210E9BLL;
      goto LABEL_59;
    }
    Group = 0;
    Acl = RtlGetGroupSecurityDescriptor(v33, &Group, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting group from existing SD";
      v35 = 0x52D00210EA1LL;
      goto LABEL_59;
    }
    Dacl = 0;
    DaclPresent = 0;
    Acl = RtlGetDaclSecurityDescriptor(v33, &DaclPresent, &Dacl, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting DACL from existing SD";
      v35 = 0x4BD00210EABLL;
      goto LABEL_59;
    }
    Ace = 0;
    if ( Dacl )
    {
      Acl = RtlGetAce(Dacl, 0, &Ace);
      if ( Acl < 0 )
      {
        v34 = "API: Getting ACE from existing DACL";
        v35 = 0x4C100210EB3LL;
        goto LABEL_59;
      }
    }
    Sacl = 0;
    SaclPresent[0] = 0;
    Acl = RtlGetSaclSecurityDescriptor(v33, SaclPresent, &Sacl, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting SACL from existing SD";
      v35 = 0x4C500210EBELL;
      goto LABEL_59;
    }
    if ( (unsigned int)Feature_UnionFs_EnforceFileSecurity__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( !Owner )
      {
        v37 = "ORIGIN: No owner";
        v38 = 0x4C600210EC9LL;
        Acl = -1073741734;
LABEL_95:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)(unsigned int)Acl,
          a5,
          (struct UnionFs::StackEventTracer *)v38,
          (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
          v37,
          ObjectAttributes);
        goto LABEL_60;
      }
      v39 = Sid;
      if ( !RtlEqualSid(Sid, Owner) )
      {
        v34 = "API: Comparing owner in existing SD";
        v35 = 0x4C700210ED0LL;
        Acl = -1073741734;
        goto LABEL_59;
      }
      if ( !Group )
      {
        v37 = "ORIGIN: No group";
        v38 = 0x4C800210ED7LL;
        Acl = -1073741733;
        goto LABEL_95;
      }
      if ( !RtlEqualSid(v39, Group) )
      {
        v34 = "API: Comparing group in existing SD";
        v35 = 0x4BC00210EDELL;
        Acl = -1073741733;
        goto LABEL_59;
      }
      if ( !DaclPresent )
      {
        v37 = "ORIGIN: No DACL";
        v38 = 0x4BE00210EE3LL;
LABEL_98:
        Acl = -1073741705;
        goto LABEL_95;
      }
      if ( !Dacl )
      {
        v37 = "ORIGIN: NULL DACL";
        v38 = 0x4BF00210EE4LL;
        goto LABEL_98;
      }
      if ( Dacl->AceCount != 1 )
      {
        v37 = "ORIGIN: ACE count";
        v38 = 0x4C000210EE9LL;
LABEL_101:
        Acl = -2147483625;
        goto LABEL_95;
      }
      if ( *(_BYTE *)Ace )
      {
        v37 = "ORIGIN: ACE type";
        v38 = 0x4C200210EF1LL;
LABEL_94:
        Acl = -1073741406;
        goto LABEL_95;
      }
      if ( !RtlEqualSid((char *)Ace + 8, v39) )
      {
        v34 = "API: Comparing ACE SID";
        v35 = 0x4C300210EF8LL;
        Acl = -1073741406;
        goto LABEL_59;
      }
      if ( *((_DWORD *)Ace + 1) != 1180063 )
      {
        v37 = "ORIGIN: ACE mask";
        v38 = 0x4C400210EFFLL;
        goto LABEL_94;
      }
      if ( !SaclPresent[0] )
      {
        v37 = "ORIGIN: No SACL";
        v38 = 0x4DB00210F02LL;
        goto LABEL_98;
      }
      if ( Sacl )
      {
        v37 = "ORIGIN: Non-NULL SACL";
        v38 = 0x4CB00210F07LL;
        goto LABEL_101;
      }
      goto LABEL_194;
    }
    if ( Owner )
    {
      v42 = Sid;
      if ( RtlEqualSid(Sid, Owner) )
      {
        if ( Group )
        {
          if ( RtlEqualSid(v42, Group) )
          {
            if ( DaclPresent )
            {
              if ( Dacl )
              {
                if ( Dacl->AceCount == 1 )
                {
                  if ( *(_BYTE *)Ace )
                  {
                    if ( (unsigned int)dword_14009E178 > 3
                      && (qword_14009E188 & 0x100) != 0
                      && (qword_14009E190 & 0x100) == qword_14009E190 )
                    {
                      v40 = a2->Buffer == 0;
                      v51 = a2;
                      LODWORD(P) = 3930;
                      if ( v40 )
                        v51 = &FsTlEmptyUnicodeString;
                      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                      v66 = (const char *)v51;
                      v63 = "ACE type in existing security descriptor on internal file is not ACCESS_ALLOWED_ACE_TYPE.";
                      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        (_DWORD)v51,
                        (unsigned int)byte_14009A3CD,
                        v46,
                        v36,
                        (__int64)&v63,
                        (__int64)&v64,
                        (__int64)&v65,
                        (__int64)&P,
                        (__int64)&v66);
                    }
                  }
                  else if ( RtlEqualSid((char *)Ace + 8, v42) )
                  {
                    if ( *((_DWORD *)Ace + 1) == 1180063 )
                    {
                      if ( SaclPresent[0] )
                      {
                        if ( !Sacl )
                        {
LABEL_194:
                          if ( v33 )
                            ExFreePoolWithTag(v33, 0);
                          goto LABEL_196;
                        }
                        if ( (unsigned int)dword_14009E178 > 3
                          && (qword_14009E188 & 0x100) != 0
                          && (qword_14009E190 & 0x100) == qword_14009E190 )
                        {
                          v40 = a2->Buffer == 0;
                          v56 = a2;
                          LODWORD(P) = 3970;
                          if ( v40 )
                            v56 = &FsTlEmptyUnicodeString;
                          v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                          v66 = (const char *)v56;
                          v63 = "Non-NULL SACL in existing security descriptor on internal file.";
                          v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                            (_DWORD)v56,
                            (unsigned int)&byte_140099F5F,
                            v52,
                            v36,
                            (__int64)&v63,
                            (__int64)&v64,
                            (__int64)&v65,
                            (__int64)&P,
                            (__int64)&v66);
                        }
                      }
                      else if ( (unsigned int)dword_14009E178 > 3
                             && (qword_14009E188 & 0x100) != 0
                             && (qword_14009E190 & 0x100) == qword_14009E190 )
                      {
                        v40 = a2->Buffer == 0;
                        v55 = a2;
                        LODWORD(P) = 3960;
                        if ( v40 )
                          v55 = &FsTlEmptyUnicodeString;
                        v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                        v66 = (const char *)v55;
                        v63 = "No SACL in existing security descriptor on internal file.";
                        v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                          (_DWORD)v55,
                          (unsigned int)byte_140099FF5,
                          v52,
                          v36,
                          (__int64)&v63,
                          (__int64)&v64,
                          (__int64)&v65,
                          (__int64)&P,
                          (__int64)&v66);
                      }
                    }
                    else if ( (unsigned int)dword_14009E178 > 3
                           && (qword_14009E188 & 0x100) != 0
                           && (qword_14009E190 & 0x100) == qword_14009E190 )
                    {
                      v40 = a2->Buffer == 0;
                      v54 = a2;
                      LODWORD(P) = 3950;
                      if ( v40 )
                        v54 = &FsTlEmptyUnicodeString;
                      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                      v66 = (const char *)v54;
                      v63 = "ACE mask in existing security descriptor on internal file does not grant read/write access.";
                      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        (_DWORD)v54,
                        (unsigned int)byte_14009A263,
                        v52,
                        v36,
                        (__int64)&v63,
                        (__int64)&v64,
                        (__int64)&v65,
                        (__int64)&P,
                        (__int64)&v66);
                    }
                  }
                  else if ( (unsigned int)dword_14009E178 > 3
                         && (qword_14009E188 & 0x100) != 0
                         && (qword_14009E190 & 0x100) == qword_14009E190 )
                  {
                    v40 = a2->Buffer == 0;
                    v53 = a2;
                    LODWORD(P) = 3940;
                    if ( v40 )
                      v53 = &FsTlEmptyUnicodeString;
                    v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                    v66 = (const char *)v53;
                    v63 = "ACE SID in existing security descriptor on internal file is not System.";
                    v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                      (_DWORD)v53,
                      (unsigned int)word_140099E7A,
                      v52,
                      v36,
                      (__int64)&v63,
                      (__int64)&v64,
                      (__int64)&v65,
                      (__int64)&P,
                      (__int64)&v66);
                  }
                }
                else if ( (unsigned int)dword_14009E178 > 3
                       && (qword_14009E188 & 0x100) != 0
                       && (qword_14009E190 & 0x100) == qword_14009E190 )
                {
                  v40 = a2->Buffer == 0;
                  v50 = a2;
                  LODWORD(P) = 3920;
                  if ( v40 )
                    v50 = &FsTlEmptyUnicodeString;
                  v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                  v66 = (const char *)v50;
                  v63 = "ACE count in existing security descriptor on internal file is not 1.";
                  v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                    (_DWORD)v50,
                    (unsigned int)byte_14009A2F9,
                    v46,
                    v36,
                    (__int64)&v63,
                    (__int64)&v64,
                    (__int64)&v65,
                    (__int64)&P,
                    (__int64)&v66);
                }
              }
              else if ( (unsigned int)dword_14009E178 > 3
                     && (qword_14009E188 & 0x100) != 0
                     && (qword_14009E190 & 0x100) == qword_14009E190 )
              {
                v40 = a2->Buffer == 0;
                v49 = a2;
                LODWORD(P) = 3910;
                if ( v40 )
                  v49 = &FsTlEmptyUnicodeString;
                v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                v66 = (const char *)v49;
                v63 = "NULL DACL in existing security descriptor on internal file.";
                v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                  (_DWORD)v49,
                  (unsigned int)byte_14009A10B,
                  v46,
                  v36,
                  (__int64)&v63,
                  (__int64)&v64,
                  (__int64)&v65,
                  (__int64)&P,
                  (__int64)&v66);
              }
            }
            else if ( (unsigned int)dword_14009E178 > 3
                   && (qword_14009E188 & 0x100) != 0
                   && (qword_14009E190 & 0x100) == qword_14009E190 )
            {
              v40 = a2->Buffer == 0;
              v48 = a2;
              LODWORD(P) = 3900;
              if ( v40 )
                v48 = &FsTlEmptyUnicodeString;
              v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
              v66 = (const char *)v48;
              v63 = "No DACL in existing security descriptor on internal file.";
              v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (_DWORD)v48,
                (unsigned int)qword_14009A418,
                v46,
                v36,
                (__int64)&v63,
                (__int64)&v64,
                (__int64)&v65,
                (__int64)&P,
                (__int64)&v66);
            }
          }
          else if ( (unsigned int)dword_14009E178 > 3
                 && (qword_14009E188 & 0x100) != 0
                 && (qword_14009E190 & 0x100) == qword_14009E190 )
          {
            v40 = a2->Buffer == 0;
            v47 = a2;
            LODWORD(P) = 3890;
            if ( v40 )
              v47 = &FsTlEmptyUnicodeString;
            v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
            v66 = (const char *)v47;
            v63 = "Group in existing security descriptor on internal file is not System.";
            v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (_DWORD)v47,
              (unsigned int)byte_14009A463,
              v46,
              v36,
              (__int64)&v63,
              (__int64)&v64,
              (__int64)&v65,
              (__int64)&P,
              (__int64)&v66);
          }
        }
        else if ( (unsigned int)dword_14009E178 > 3
               && (qword_14009E188 & 0x100) != 0
               && (qword_14009E190 & 0x100) == qword_14009E190 )
        {
          v40 = a2->Buffer == Group;
          v45 = a2;
          LODWORD(P) = 3880;
          if ( v40 )
            v45 = &FsTlEmptyUnicodeString;
          v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
          v66 = (const char *)v45;
          v63 = "No group in existing security descriptor on internal file.";
          v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (_DWORD)v45,
            (unsigned int)&word_14009A2AE,
            v43,
            v36,
            (__int64)&v63,
            (__int64)&v64,
            (__int64)&v65,
            (__int64)&P,
            (__int64)&v66);
        }
      }
      else if ( (unsigned int)dword_14009E178 > 3
             && (qword_14009E188 & 0x100) != 0
             && (qword_14009E190 & 0x100) == qword_14009E190 )
      {
        v40 = a2->Buffer == 0;
        v44 = a2;
        LODWORD(P) = 3870;
        if ( v40 )
          v44 = &FsTlEmptyUnicodeString;
        v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
        v66 = (const char *)v44;
        v63 = "Owner in existing security descriptor on internal file is not System.";
        v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (_DWORD)v44,
          (unsigned int)&dword_14009A344,
          v43,
          v36,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v65,
          (__int64)&P,
          (__int64)&v66);
      }
    }
    else if ( (unsigned int)dword_14009E178 > 3
           && (qword_14009E188 & 0x100) != 0
           && (qword_14009E190 & 0x100) == qword_14009E190 )
    {
      v40 = a2->Buffer == Owner;
      v66 = "No owner in existing security descriptor on internal file.";
      LODWORD(P) = 3860;
      v64 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v41 = a2;
      v65 = "UnionFs::Utils::OpenOrCreateInternalFile";
      if ( v40 )
        v41 = &FsTlEmptyUnicodeString;
      v63 = (const char *)v41;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (_DWORD)v41,
        (unsigned int)word_140099FAA,
        (unsigned int)&FsTlEmptyUnicodeString,
        v36,
        (__int64)&v66,
        (__int64)&v65,
        (__int64)&v64,
        (__int64)&P,
        (__int64)&v63);
    }
    if ( (unsigned int)dword_14009E178 > 3
      && (qword_14009E188 & 0x100) != 0
      && (qword_14009E190 & 0x100) == qword_14009E190 )
    {
      v40 = a2->Buffer == 0;
      v63 = "Replacing existing security descriptor on internal file.";
      LODWORD(P) = 3984;
      if ( v40 )
        a2 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v66 = (const char *)a2;
      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        qword_14009E190,
        (unsigned int)&dword_140099F14,
        (unsigned int)&FsTlEmptyUnicodeString,
        v36,
        (__int64)&v63,
        (__int64)&v64,
        (__int64)&v65,
        (__int64)&P,
        (__int64)&v66);
    }
    Acl = FltSetSecurityObject(Instance, *v26, 0xFu, v15);
    if ( Acl < 0 )
    {
      v34 = "API: Setting SD on existing file";
      v35 = 0x4CC00210F9CLL;
      goto LABEL_59;
    }
    goto LABEL_194;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v12,
    a5,
    (struct UnionFs::StackEventTracer *)0x4C900210DE4LL,
    (unsigned __int64)"UnionFs::Utils::OpenOrCreateInternalFile",
    "API: Initializing SID",
    ObjectAttributes);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400735d4  push    rbp
0x1400735d6  push    rbx
0x1400735d7  push    rsi
0x1400735d8  push    rdi
0x1400735d9  push    r12
0x1400735db  push    r13
0x1400735dd  push    r14
0x1400735df  push    r15
0x1400735e1  lea     rbp, [rsp-88h]
0x1400735e9  sub     rsp, 188h
0x1400735f0  mov     rax, cs:__security_cookie
0x1400735f7  xor     rax, rsp
0x1400735fa  mov     [rbp+0C0h+var_48], rax
0x1400735fe  mov     r15, qword ptr [rbp+0C0h+arg_20]
0x140073605  xor     r14d, r14d
0x140073608  mov     [rbp+0C0h+Instance], rcx
0x14007360c  mov     rsi, r9
0x14007360f  mov     rcx, [r9]; FileHandle
0x140073612  mov     r13, rdx
0x140073615  mov     [rbp+0C0h+Sacl], r8
0x140073619  test    rcx, rcx
0x14007361c  jz      short loc_14007362A
0x14007361e  call    cs:__imp_FltClose
0x140073625  nop     dword ptr [rax+rax+00h]
0x14007362a  lea     rax, [rsi+8]
0x14007362e  mov     [rsi], r14
0x140073631  mov     rcx, [rax]; Object
0x140073634  mov     [rbp+0C0h+Dacl], rax
0x140073638  mov     [rax], r14
0x14007363b  test    rcx, rcx
0x14007363e  jz      short loc_14007364C
0x140073640  call    cs:__imp_ObfDereferenceObject
0x140073647  nop     dword ptr [rax+rax+00h]
0x14007364c  mov     ebx, 1
0x140073651  mov     ecx, ebx; SubAuthorityCount
0x140073653  call    cs:__imp_RtlLengthRequiredSid
0x14007365a  nop     dword ptr [rax+rax+00h]
0x14007365f  mov     edx, eax
0x140073661  lea     rcx, [rbp+0C0h+Sid]
0x140073665  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x14007366a  mov     rdi, [rbp+0C0h+Sid]
0x14007366e  test    rdi, rdi
0x140073671  jnz     short loc_1400736A4
0x140073673  lea     rax, aOriginAllocati_23; "ORIGIN: Allocating System SID buffer"
0x14007367a  mov     edi, 0C000009Ah
0x14007367f  mov     ecx, edi; this
0x140073681  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x140073686  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x14007368d  mov     r8, 52200210DDDh; struct UnionFs::StackEventTracer *
0x140073697  mov     rdx, r15; int
0x14007369a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007369f  jmp     loc_1400749BE
0x1400736a4  mov     r8b, bl; SubAuthorityCount
0x1400736a7  mov     dword ptr [rbp+0C0h+IdentifierAuthority.Value], r14d
0x1400736ab  lea     rdx, [rbp+0C0h+IdentifierAuthority]; IdentifierAuthority
0x1400736af  mov     word ptr [rbp+0C0h+IdentifierAuthority.Value+4], 500h
0x1400736b5  mov     rcx, rdi; Sid
0x1400736b8  call    cs:__imp_RtlInitializeSid
0x1400736bf  nop     dword ptr [rax+rax+00h]
0x1400736c4  mov     ebx, eax
0x1400736c6  test    eax, eax
0x1400736c8  jns     short loc_14007370E
0x1400736ca  lea     rax, aApiInitializin_10; "API: Initializing SID"
0x1400736d1  mov     r8, 4C900210DE4h; struct UnionFs::StackEventTracer *
0x1400736db  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x1400736e2  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x1400736e7  mov     rdx, r15; int
0x1400736ea  mov     ecx, ebx; this
0x1400736ec  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400736f1  test    rdi, rdi
0x1400736f4  jz      short loc_140073707
0x1400736f6  xor     edx, edx; Tag
0x1400736f8  mov     rcx, rdi; P
0x1400736fb  call    cs:__imp_ExFreePoolWithTag
0x140073702  nop     dword ptr [rax+rax+00h]
0x140073707  mov     eax, ebx
0x140073709  jmp     loc_1400749C0
0x14007370e  xor     edx, edx; SubAuthority
0x140073710  mov     rcx, rdi; Sid
0x140073713  call    cs:__imp_RtlSubAuthoritySid
0x14007371a  nop     dword ptr [rax+rax+00h]
0x14007371f  lea     rcx, [rbp+0C0h+SecurityDescriptor]
0x140073723  mov     dword ptr [rax], 12h
0x140073729  movzx   eax, byte ptr [rdi+1]
0x14007372d  lea     r12d, ds:44h[rax*4]
0x140073735  mov     edx, r12d
0x140073738  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x14007373d  mov     rbx, [rbp+0C0h+SecurityDescriptor]
0x140073741  test    rbx, rbx
0x140073744  jnz     short loc_140073777
0x140073746  lea     rax, aOriginAllocati_44; "ORIGIN: Allocating SD buffer"
0x14007374d  mov     edi, 0C000009Ah
0x140073752  mov     ecx, edi; this
0x140073754  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x140073759  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x140073760  mov     r8, 52300210DF4h; struct UnionFs::StackEventTracer *
0x14007376a  mov     rdx, r15; int
0x14007376d  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140073772  jmp     loc_1400749AC
0x140073777  mov     edx, 1; Revision
0x14007377c  mov     rcx, rbx; SecurityDescriptor
0x14007377f  call    cs:__imp_RtlCreateSecurityDescriptor
0x140073786  nop     dword ptr [rax+rax+00h]
0x14007378b  mov     edi, eax
0x14007378d  test    eax, eax
0x14007378f  jns     short loc_1400737D5
0x140073791  lea     rax, aApiInitializin_18; "API: Initializing SD"
0x140073798  mov     r8, 52400210DFDh; struct UnionFs::StackEventTracer *
0x1400737a2  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x1400737a9  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x1400737ae  mov     rdx, r15; int
0x1400737b1  mov     ecx, edi; this
0x1400737b3  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400737b8  test    rbx, rbx
0x1400737bb  jz      loc_1400749AC
0x1400737c1  mov     rcx, rbx; SecurityDescriptor
0x1400737c4  call    cs:__imp_FltFreeSecurityDescriptor
0x1400737cb  nop     dword ptr [rax+rax+00h]
0x1400737d0  jmp     loc_1400749AC
0x1400737d5  mov     r14, [rbp+0C0h+Sid]
0x1400737d9  xor     r8d, r8d; OwnerDefaulted
0x1400737dc  mov     rdx, r14; Owner
0x1400737df  mov     rcx, rbx; SecurityDescriptor
0x1400737e2  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400737e9  nop     dword ptr [rax+rax+00h]
0x1400737ee  mov     edi, eax
0x1400737f0  test    eax, eax
0x1400737f2  jns     short loc_140073807
0x1400737f4  lea     rax, aApiSettingOwne; "API: Setting owner in SD"
0x1400737fb  mov     r8, 52500210E04h
0x140073805  jmp     short loc_1400737A2
0x140073807  xor     r8d, r8d; GroupDefaulted
0x14007380a  mov     rdx, r14; Group
0x14007380d  mov     rcx, rbx; SecurityDescriptor
0x140073810  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140073817  nop     dword ptr [rax+rax+00h]
0x14007381c  mov     edi, eax
0x14007381e  test    eax, eax
0x140073820  jns     short loc_140073838
0x140073822  lea     rax, aApiSettingGrou; "API: Setting group in SD"
0x140073829  mov     r8, 52600210E09h
0x140073833  jmp     loc_1400737A2
0x140073838  lea     r14, [rbx+28h]
0x14007383c  mov     r8d, 2; AclRevision
0x140073842  mov     rcx, r14; Acl
0x140073845  lea     edx, [r12-28h]; AclLength
0x14007384a  call    cs:__imp_RtlCreateAcl
0x140073851  nop     dword ptr [rax+rax+00h]
0x140073856  xor     r12d, r12d
0x140073859  mov     edi, eax
0x14007385b  test    eax, eax
0x14007385d  jns     short loc_140073875
0x14007385f  lea     rax, aApiInitializin_5; "API: Initializing DACL"
0x140073866  mov     r8, 52700210E13h
0x140073870  jmp     loc_1400737A2
0x140073875  mov     r9, [rbp+0C0h+Sid]; Sid
0x140073879  mov     edx, 2; AceRevision
0x14007387e  mov     r8d, 12019Fh; AccessMask
0x140073884  mov     rcx, r14; Acl
0x140073887  call    cs:__imp_RtlAddAccessAllowedAce
0x14007388e  nop     dword ptr [rax+rax+00h]
0x140073893  mov     edi, eax
0x140073895  test    eax, eax
0x140073897  jns     short loc_1400738AF
0x140073899  lea     rax, aApiAddingSyste; "API: Adding System access ACE"
0x1400738a0  mov     r8, 52800210E1Bh
0x1400738aa  jmp     loc_1400737A2
0x1400738af  xor     r9d, r9d; DaclDefaulted
0x1400738b2  mov     r8, r14; Dacl
0x1400738b5  mov     rcx, rbx; SecurityDescriptor
0x1400738b8  lea     r14d, [r9+1]
0x1400738bc  mov     dl, r14b; DaclPresent
0x1400738bf  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400738c6  nop     dword ptr [rax+rax+00h]
0x1400738cb  mov     edi, eax
0x1400738cd  test    eax, eax
0x1400738cf  jns     short loc_1400738E7
0x1400738d1  lea     rax, aApiSettingDacl; "API: Setting DACL in SD"
0x1400738d8  mov     r8, 52900210E21h
0x1400738e2  jmp     loc_1400737A2
0x1400738e7  xor     r9d, r9d; SaclDefaulted
0x1400738ea  xor     r8d, r8d; Sacl
0x1400738ed  mov     dl, r14b; SaclPresent
0x1400738f0  mov     rcx, rbx; SecurityDescriptor
0x1400738f3  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1400738fa  nop     dword ptr [rax+rax+00h]
0x1400738ff  mov     edi, eax
0x140073901  test    eax, eax
0x140073903  jns     short loc_14007391B
0x140073905  lea     rax, aApiSettingNull; "API: Setting null SACL in SD"
0x14007390c  mov     r8, 52E00210E28h
0x140073916  jmp     loc_1400737A2
0x14007391b  mov     edx, 3000h; ControlBitsOfInterest
0x140073920  mov     rcx, rbx; SecurityDescriptor
0x140073923  mov     r8d, edx; ControlBitsToSet
0x140073926  call    cs:__imp_RtlSetControlSecurityDescriptor
0x14007392d  nop     dword ptr [rax+rax+00h]
0x140073932  mov     edi, eax
0x140073934  test    eax, eax
0x140073936  jns     short loc_14007394E
0x140073938  lea     rax, aApiSettingSdCo; "API: Setting SD control flags"
0x14007393f  mov     r8, 4CA00210E30h
0x140073949  jmp     loc_1400737A2
0x14007394e  xorps   xmm1, xmm1
0x140073951  mov     qword ptr [rbp+0C0h+var_A8.Length], 30h ; '0'
0x140073959  xorps   xmm0, xmm0
0x14007395c  mov     qword ptr [rbp+0C0h+var_A8.Attributes], 240h
0x140073964  mov     eax, 28h ; '('
0x140073969  mov     [rbp+0C0h+var_A8.RootDirectory], r12
0x14007396d  movups  xmmword ptr [rbp+0C0h+var_78.Size], xmm1
0x140073971  mov     [rbp+0C0h+var_78.Size], ax
0x140073975  mov     [rbp+0C0h+var_A8.ObjectName], r13
0x140073979  mov     [rbp+0C0h+var_A8.SecurityDescriptor], rbx
0x14007397d  mov     [rbp+0C0h+var_A8.SecurityQualityOfService], r12
0x140073981  movups  xmmword ptr [rbp+0C0h+var_B8], xmm0
0x140073985  mov     [rbp+0C0h+var_58], r14
0x140073989  movups  xmmword ptr [rbp+0C0h+var_78.DeviceObjectHint], xmm1
0x14007398d  call    cs:__imp_PsGetHostSilo
0x140073994  nop     dword ptr [rax+rax+00h]
0x140073999  mov     rcx, [rbp+0C0h+Sacl]
0x14007399d  mov     [rbp+0C0h+var_58], rax
0x1400739a1  mov     al, [rcx+8]
0x1400739a4  mov     r14d, [rcx+4]
0x1400739a8  neg     al
0x1400739aa  mov     r12d, [rcx]
0x1400739ad  lea     rax, [rsi+8]
0x1400739b1  sbb     edi, edi
0x1400739b3  mov     [rbp+0C0h+var_D0], rax
0x1400739b7  xor     edx, edx
0x1400739b9  and     edi, 8
0x1400739bc  add     edi, 20h ; ' '
0x1400739bf  mov     [rbp+0C0h+FileObject], rdx
0x1400739c3  lea     ecx, [rdx+1]
0x1400739c6  mov     [rbp+0C0h+var_C0], cl
0x1400739c9  mov     rcx, [rsi]; FileHandle
0x1400739cc  test    rcx, rcx
0x1400739cf  jz      short loc_1400739DF
0x1400739d1  call    cs:__imp_FltClose
0x1400739d8  nop     dword ptr [rax+rax+00h]
0x1400739dd  xor     edx, edx
0x1400739df  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400739e6  lea     rax, [rbp+0C0h+var_78]
0x1400739ea  mov     [rsp+1C0h+DriverContext], rax; DriverContext
0x1400739ef  lea     r9, [rbp+0C0h+FileObject]; FileObject
0x1400739f3  mov     [rsp+1C0h+Flags], edx; Flags
0x1400739f7  lea     rax, [rbp+0C0h+var_B8]
0x1400739fb  mov     [rsp+1C0h+EaLength], edx; EaLength
0x1400739ff  mov     r8, rsi; FileHandle
0x140073a02  mov     [rsp+1C0h+EaBuffer], rdx; EaBuffer
0x140073a07  mov     [rsp+1C0h+CreateOptions], edi; CreateOptions
0x140073a0b  mov     [rsp+1C0h+CreateDisposition], r14d; CreateDisposition
0x140073a10  mov     r14, [rbp+0C0h+Instance]
0x140073a14  mov     [rsp+1C0h+ShareAccess], 1; ShareAccess
0x140073a1c  mov     [rsp+1C0h+FileAttributes], 6; FileAttributes
0x140073a24  mov     [rsp+1C0h+AllocationSize], rdx; AllocationSize
0x140073a29  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x140073a2e  lea     rax, [rbp+0C0h+var_A8]
0x140073a32  mov     [rsi], rdx
0x140073a35  mov     rdx, r14; Instance
0x140073a38  mov     rcx, [rcx]; Filter
0x140073a3b  mov     [rsp+1C0h+ObjectAttributes], rax; char *
0x140073a40  mov     [rsp+1C0h+DesiredAccess], r12d; DesiredAccess
0x140073a45  call    cs:__imp_FltCreateFileEx2
0x140073a4c  nop     dword ptr [rax+rax+00h]
0x140073a51  xor     r12d, r12d
0x140073a54  mov     edi, eax
0x140073a56  cmp     [rbp+0C0h+var_C0], r12b
0x140073a5a  jz      short loc_140073A7E
0x140073a5c  mov     rcx, [rbp+0C0h+var_D0]
0x140073a60  mov     rax, [rbp+0C0h+FileObject]
0x140073a64  mov     rdx, [rcx]
0x140073a67  mov     [rcx], rax
0x140073a6a  test    rdx, rdx
0x140073a6d  jz      short loc_140073A7E
0x140073a6f  mov     rcx, rdx; Object
0x140073a72  call    cs:__imp_ObfDereferenceObject
0x140073a79  nop     dword ptr [rax+rax+00h]
0x140073a7e  test    edi, edi
0x140073a80  jns     short loc_140073A98
0x140073a82  lea     rax, aApiOpenCreateI; "API: Open/Create internal file"
0x140073a89  mov     r8, 76300210E5Dh
0x140073a93  jmp     loc_1400737A2
0x140073a98  mov     r8, [rbp+0C0h+Sacl]
0x140073a9c  lea     rsi, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x140073aa3  cmp     dword ptr [r8+0Ch], 1Ch
0x140073aa8  jnz     loc_140073C4B
0x140073aae  test    [rbp+0C0h+var_B8.Information], 0FFFFFFFFFFFFFFFDh
0x140073ab6  jnz     loc_140073C4B
0x140073abc  mov     [rsp+1C0h+AllocationSize], r12; LengthReturned
0x140073ac1  lea     r9, [rbp+0C0h+SecurityDescriptor]; InputBuffer
0x140073ac5  mov     dword ptr [rsp+1C0h+IoStatusBlock], r12d; OutputBufferLength
0x140073aca  mov     eax, 2
0x140073acf  mov     [rbp+0C0h+SecurityDescriptor], r12
0x140073ad3  mov     r8d, 9C280h; FsControlCode
0x140073ad9  mov     [rsp+1C0h+ObjectAttributes], r12; OutputBuffer
0x140073ade  mov     rcx, r14; Instance
0x140073ae1  mov     r12, [rbp+0C0h+Dacl]
0x140073ae5  mov     word ptr [rbp+0C0h+SecurityDescriptor], ax
0x140073ae9  mov     [rsp+1C0h+DesiredAccess], 8; InputBufferLength
0x140073af1  mov     rdx, [r12]; FileObject
  ... truncated ...
```
