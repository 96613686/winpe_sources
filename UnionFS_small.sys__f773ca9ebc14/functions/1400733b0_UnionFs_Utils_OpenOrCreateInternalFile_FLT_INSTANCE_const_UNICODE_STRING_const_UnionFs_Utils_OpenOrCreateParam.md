# UnionFs::Utils::OpenOrCreateInternalFile(_FLT_INSTANCE const &,_UNICODE_STRING const &,UnionFs::Utils::OpenOrCreateParams,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &)

- ea: `0x1400733b0`
- end: `0x1400747bd`
- name: `?OpenOrCreateInternalFile@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@UOpenOrCreateParams@12@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `5133`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140051630`
- `0x140051df4`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001c08`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x1400679c8`
- `0x1400733b0`
- `0x14007579c`
- `0x1400793b0`
- `0x140079408`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400736cf`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x1400736cf`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400735be`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400735be`
- `ntoskrnl!RtlInitializeSid` at `0x140073494`
- `ntoskrnl!RtlInitializeSid` at `0x140073494`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400734ef`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400734ef`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14007369b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14007369b`
- `ntoskrnl!RtlGetAce` at `0x140073bc0`
- `ntoskrnl!RtlGetAce` at `0x140073bc0`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140073b06`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140073b06`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14007342f`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14007342f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140073663`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140073663`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140073b3e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140073b3e`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140073aa9`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140073aa9`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140073702`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140073702`
- `ntoskrnl!RtlCreateAcl` at `0x140073626`
- `ntoskrnl!RtlCreateAcl` at `0x140073626`
- `ntoskrnl!RtlEqualSid` at `0x140073c63`
- `ntoskrnl!RtlEqualSid` at `0x140073cb5`
- `ntoskrnl!RtlEqualSid` at `0x140073d5f`
- `ntoskrnl!RtlEqualSid` at `0x140073eca`
- `ntoskrnl!RtlEqualSid` at `0x140074037`
- `ntoskrnl!RtlEqualSid` at `0x1400743be`
- `ntoskrnl!RtlEqualSid` at `0x140073c63`
- `ntoskrnl!RtlEqualSid` at `0x140073cb5`
- `ntoskrnl!RtlEqualSid` at `0x140073d5f`
- `ntoskrnl!RtlEqualSid` at `0x140073eca`
- `ntoskrnl!RtlEqualSid` at `0x140074037`
- `ntoskrnl!RtlEqualSid` at `0x1400743be`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400735ec`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400735ec`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007355b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007355b`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140073b81`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140073b81`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140073c03`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140073c03`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400734d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073a91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074766`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007478e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400734d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073a91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074766`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007478e`
- `ntoskrnl!PsGetHostSilo` at `0x140073769`
- `ntoskrnl!PsGetHostSilo` at `0x140073769`
- `ntoskrnl!ObfDereferenceObject` at `0x14007341c`
- `ntoskrnl!ObfDereferenceObject` at `0x14007384e`
- `ntoskrnl!ObfDereferenceObject` at `0x14007341c`
- `ntoskrnl!ObfDereferenceObject` at `0x14007384e`
- `FLTMGR!FltSetSecurityObject` at `0x140074734`
- `FLTMGR!FltSetSecurityObject` at `0x140074734`
- `FLTMGR!FltCreateFileEx2` at `0x140073821`
- `FLTMGR!FltCreateFileEx2` at `0x140073821`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400735a0`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14007477a`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x1400735a0`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14007477a`
- `FLTMGR!FltClose` at `0x1400733fa`
- `FLTMGR!FltClose` at `0x1400737ad`
- `FLTMGR!FltClose` at `0x1400733fa`
- `FLTMGR!FltClose` at `0x1400737ad`
- `FLTMGR!FltFsControlFile` at `0x1400738d1`
- `FLTMGR!FltFsControlFile` at `0x1400738d1`

## string_xrefs

- `0x140073462`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x1400734b7`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x140073535`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x14007357e`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x140073878`: `UnionFs::Utils::OpenOrCreateInternalFile`
- `0x14007344f`: `ORIGIN: Allocating System SID buffer`
- `0x1400734a6`: `API: Initializing SID`
- `0x14007363b`: `API: Initializing DACL`
- `0x1400736ad`: `API: Setting DACL in SD`
- `0x140073675`: `API: Adding System access ACE`
- `0x1400736e1`: `API: Setting null SACL in SD`
- `0x14007385e`: `API: Open/Create internal file`
- `0x140073b93`: `API: Getting DACL from existing SD`
- `0x140073c15`: `API: Getting SACL from existing SD`
- `0x140073bd2`: `API: Getting ACE from existing DACL`
- `0x140073c73`: `API: Comparing owner in existing SD`
- `0x140073cc5`: `API: Comparing group in existing SD`
- `0x140073d05`: `ORIGIN: NULL DACL`
- `0x140073ce6`: `ORIGIN: No DACL`
- `0x140073d6f`: `API: Comparing ACE SID`
- `0x140073ded`: `ORIGIN: Non-NULL SACL`
- `0x140073dca`: `ORIGIN: No SACL`
- `0x140073f35`: `Owner in existing security descriptor on internal file is not System.`
- `0x140073e52`: `No owner in existing security descriptor on internal file.`
- `0x1400740a2`: `Group in existing security descriptor on internal file is not System.`
- `0x140073fe6`: `No group in existing security descriptor on internal file.`
- `0x140074203`: `NULL DACL in existing security descriptor on internal file.`
- `0x140074151`: `No DACL in existing security descriptor on internal file.`
- `0x140074369`: `ACE type in existing security descriptor on internal file is not ACCESS_ALLOWED_ACE_TYPE.`
- `0x1400742b7`: `ACE count in existing security descriptor on internal file is not 1.`
- `0x1400744df`: `ACE mask in existing security descriptor on internal file does not grant read/write access.`
- `0x140074429`: `ACE SID in existing security descriptor on internal file is not System.`
- `0x140074636`: `Non-NULL SACL in existing security descriptor on internal file.`
- `0x14007458e`: `No SACL in existing security descriptor on internal file.`
- `0x1400746c8`: `Replacing existing security descriptor on internal file.`

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
      (struct UnionFs::StackEventTracer *)0x52200210DA4LL,
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
        (struct UnionFs::StackEventTracer *)0x52300210DBBLL,
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
      v17 = 0x52400210DC4LL;
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
      v17 = 0x52500210DCBLL;
      goto LABEL_15;
    }
    Acl = RtlSetGroupSecurityDescriptor(v15, v18, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting group in SD";
      v17 = 0x52600210DD0LL;
      goto LABEL_15;
    }
    Acl = RtlCreateAcl(v15 + 5, v14 - 40, 2u);
    if ( Acl < 0 )
    {
      v16 = "API: Initializing DACL";
      v17 = 0x52700210DDALL;
      goto LABEL_15;
    }
    Acl = RtlAddAccessAllowedAce(v15 + 5, 2u, 0x12019Fu, Sid);
    if ( Acl < 0 )
    {
      v16 = "API: Adding System access ACE";
      v17 = 0x52800210DE2LL;
      goto LABEL_15;
    }
    Acl = RtlSetDaclSecurityDescriptor(v15, 1u, v15 + 5, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting DACL in SD";
      v17 = 0x52900210DE8LL;
      goto LABEL_15;
    }
    Acl = RtlSetSaclSecurityDescriptor(v15, 1u, 0, 0);
    if ( Acl < 0 )
    {
      v16 = "API: Setting null SACL in SD";
      v17 = 0x52E00210DEFLL;
      goto LABEL_15;
    }
    Acl = RtlSetControlSecurityDescriptor(v15, 0x3000u, 0x3000u);
    if ( Acl < 0 )
    {
      v16 = "API: Setting SD control flags";
      v17 = 0x4CA00210DF7LL;
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
      v17 = 0x76300210E24LL;
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
          v17 = 0x2F700210E44LL;
          goto LABEL_15;
        }
        if ( (unsigned int)dword_14009E178 > 3
          && (qword_14009E188 & 0x8000) != 0
          && (qword_14009E190 & 0x8000) == qword_14009E190 )
        {
          LODWORD(Ace) = Acl;
          Sacl = (PACL)"onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          LODWORD(P) = 3658;
          Owner = "Failed to enable ReFS integrity stream on persistence file (best-effort)";
          Group = (PSID)"UnionFs::Utils::OpenOrCreateInternalFile";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            0x8000,
            (unsigned int)&dword_140099B84,
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
        LODWORD(Ace) = 3645;
        Sacl = (PACL)"onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        Group = (PSID)"UnionFs::Utils::OpenOrCreateInternalFile";
        Owner = "ReFS integrity stream enabled on persistence file";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0x8000,
          (unsigned int)qword_140099C78,
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
        (struct UnionFs::StackEventTracer *)0x52A00210E55LL,
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
      v35 = 0x52B00210E5CLL;
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
      v35 = 0x52C00210E65LL;
      goto LABEL_59;
    }
    Group = 0;
    Acl = RtlGetGroupSecurityDescriptor(v33, &Group, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting group from existing SD";
      v35 = 0x52D00210E6BLL;
      goto LABEL_59;
    }
    Dacl = 0;
    DaclPresent = 0;
    Acl = RtlGetDaclSecurityDescriptor(v33, &DaclPresent, &Dacl, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting DACL from existing SD";
      v35 = 0x4BD00210E75LL;
      goto LABEL_59;
    }
    Ace = 0;
    if ( Dacl )
    {
      Acl = RtlGetAce(Dacl, 0, &Ace);
      if ( Acl < 0 )
      {
        v34 = "API: Getting ACE from existing DACL";
        v35 = 0x4C100210E7DLL;
        goto LABEL_59;
      }
    }
    Sacl = 0;
    SaclPresent[0] = 0;
    Acl = RtlGetSaclSecurityDescriptor(v33, SaclPresent, &Sacl, &OwnerDefaulted);
    if ( Acl < 0 )
    {
      v34 = "API: Getting SACL from existing SD";
      v35 = 0x4C500210E88LL;
      goto LABEL_59;
    }
    if ( (unsigned int)Feature_UnionFs_EnforceFileSecurity__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( !Owner )
      {
        v37 = "ORIGIN: No owner";
        v38 = 0x4C600210E93LL;
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
        v35 = 0x4C700210E9ALL;
        Acl = -1073741734;
        goto LABEL_59;
      }
      if ( !Group )
      {
        v37 = "ORIGIN: No group";
        v38 = 0x4C800210EA1LL;
        Acl = -1073741733;
        goto LABEL_95;
      }
      if ( !RtlEqualSid(v39, Group) )
      {
        v34 = "API: Comparing group in existing SD";
        v35 = 0x4BC00210EA8LL;
        Acl = -1073741733;
        goto LABEL_59;
      }
      if ( !DaclPresent )
      {
        v37 = "ORIGIN: No DACL";
        v38 = 0x4BE00210EADLL;
LABEL_98:
        Acl = -1073741705;
        goto LABEL_95;
      }
      if ( !Dacl )
      {
        v37 = "ORIGIN: NULL DACL";
        v38 = 0x4BF00210EAELL;
        goto LABEL_98;
      }
      if ( Dacl->AceCount != 1 )
      {
        v37 = "ORIGIN: ACE count";
        v38 = 0x4C000210EB3LL;
LABEL_101:
        Acl = -2147483625;
        goto LABEL_95;
      }
      if ( *(_BYTE *)Ace )
      {
        v37 = "ORIGIN: ACE type";
        v38 = 0x4C200210EBBLL;
LABEL_94:
        Acl = -1073741406;
        goto LABEL_95;
      }
      if ( !RtlEqualSid((char *)Ace + 8, v39) )
      {
        v34 = "API: Comparing ACE SID";
        v35 = 0x4C300210EC2LL;
        Acl = -1073741406;
        goto LABEL_59;
      }
      if ( *((_DWORD *)Ace + 1) != 1180063 )
      {
        v37 = "ORIGIN: ACE mask";
        v38 = 0x4C400210EC9LL;
        goto LABEL_94;
      }
      if ( !SaclPresent[0] )
      {
        v37 = "ORIGIN: No SACL";
        v38 = 0x4DB00210ECCLL;
        goto LABEL_98;
      }
      if ( Sacl )
      {
        v37 = "ORIGIN: Non-NULL SACL";
        v38 = 0x4CB00210ED1LL;
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
                      LODWORD(P) = 3876;
                      if ( v40 )
                        v51 = &FsTlEmptyUnicodeString;
                      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                      v66 = (const char *)v51;
                      v63 = "ACE type in existing security descriptor on internal file is not ACCESS_ALLOWED_ACE_TYPE.";
                      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        (_DWORD)v51,
                        (unsigned int)byte_14009A34D,
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
                          LODWORD(P) = 3916;
                          if ( v40 )
                            v56 = &FsTlEmptyUnicodeString;
                          v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                          v66 = (const char *)v56;
                          v63 = "Non-NULL SACL in existing security descriptor on internal file.";
                          v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                            (_DWORD)v56,
                            (unsigned int)&byte_140099EDF,
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
                        LODWORD(P) = 3906;
                        if ( v40 )
                          v55 = &FsTlEmptyUnicodeString;
                        v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                        v66 = (const char *)v55;
                        v63 = "No SACL in existing security descriptor on internal file.";
                        v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                          (_DWORD)v55,
                          (unsigned int)byte_140099F75,
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
                      LODWORD(P) = 3896;
                      if ( v40 )
                        v54 = &FsTlEmptyUnicodeString;
                      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                      v66 = (const char *)v54;
                      v63 = "ACE mask in existing security descriptor on internal file does not grant read/write access.";
                      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        (_DWORD)v54,
                        (unsigned int)byte_14009A1E3,
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
                    LODWORD(P) = 3886;
                    if ( v40 )
                      v53 = &FsTlEmptyUnicodeString;
                    v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                    v66 = (const char *)v53;
                    v63 = "ACE SID in existing security descriptor on internal file is not System.";
                    v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                      (_DWORD)v53,
                      (unsigned int)word_140099DFA,
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
                  LODWORD(P) = 3866;
                  if ( v40 )
                    v50 = &FsTlEmptyUnicodeString;
                  v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                  v66 = (const char *)v50;
                  v63 = "ACE count in existing security descriptor on internal file is not 1.";
                  v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                    (_DWORD)v50,
                    (unsigned int)byte_14009A279,
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
                LODWORD(P) = 3856;
                if ( v40 )
                  v49 = &FsTlEmptyUnicodeString;
                v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
                v66 = (const char *)v49;
                v63 = "NULL DACL in existing security descriptor on internal file.";
                v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                  (_DWORD)v49,
                  (unsigned int)byte_14009A08B,
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
              LODWORD(P) = 3846;
              if ( v40 )
                v48 = &FsTlEmptyUnicodeString;
              v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
              v66 = (const char *)v48;
              v63 = "No DACL in existing security descriptor on internal file.";
              v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (_DWORD)v48,
                (unsigned int)qword_14009A398,
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
            LODWORD(P) = 3836;
            if ( v40 )
              v47 = &FsTlEmptyUnicodeString;
            v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
            v66 = (const char *)v47;
            v63 = "Group in existing security descriptor on internal file is not System.";
            v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (_DWORD)v47,
              (unsigned int)byte_14009A3E3,
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
          LODWORD(P) = 3826;
          if ( v40 )
            v45 = &FsTlEmptyUnicodeString;
          v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
          v66 = (const char *)v45;
          v63 = "No group in existing security descriptor on internal file.";
          v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (_DWORD)v45,
            (unsigned int)&word_14009A22E,
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
        LODWORD(P) = 3816;
        if ( v40 )
          v44 = &FsTlEmptyUnicodeString;
        v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
        v66 = (const char *)v44;
        v63 = "Owner in existing security descriptor on internal file is not System.";
        v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (_DWORD)v44,
          (unsigned int)&dword_14009A2C4,
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
      LODWORD(P) = 3806;
      v64 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v41 = a2;
      v65 = "UnionFs::Utils::OpenOrCreateInternalFile";
      if ( v40 )
        v41 = &FsTlEmptyUnicodeString;
      v63 = (const char *)v41;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (_DWORD)v41,
        (unsigned int)word_140099F2A,
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
      LODWORD(P) = 3930;
      if ( v40 )
        a2 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v66 = (const char *)a2;
      v65 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v64 = "UnionFs::Utils::OpenOrCreateInternalFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        qword_14009E190,
        (unsigned int)&dword_140099E94,
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
      v35 = 0x4CC00210F66LL;
      goto LABEL_59;
    }
    goto LABEL_194;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v12,
    a5,
    (struct UnionFs::StackEventTracer *)0x4C900210DABLL,
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
0x1400733b0  push    rbp
0x1400733b2  push    rbx
0x1400733b3  push    rsi
0x1400733b4  push    rdi
0x1400733b5  push    r12
0x1400733b7  push    r13
0x1400733b9  push    r14
0x1400733bb  push    r15
0x1400733bd  lea     rbp, [rsp-88h]
0x1400733c5  sub     rsp, 188h
0x1400733cc  mov     rax, cs:__security_cookie
0x1400733d3  xor     rax, rsp
0x1400733d6  mov     [rbp+0C0h+var_48], rax
0x1400733da  mov     r15, qword ptr [rbp+0C0h+arg_20]
0x1400733e1  xor     r14d, r14d
0x1400733e4  mov     [rbp+0C0h+Instance], rcx
0x1400733e8  mov     rsi, r9
0x1400733eb  mov     rcx, [r9]; FileHandle
0x1400733ee  mov     r13, rdx
0x1400733f1  mov     [rbp+0C0h+Sacl], r8
0x1400733f5  test    rcx, rcx
0x1400733f8  jz      short loc_140073406
0x1400733fa  call    cs:__imp_FltClose
0x140073401  nop     dword ptr [rax+rax+00h]
0x140073406  lea     rax, [rsi+8]
0x14007340a  mov     [rsi], r14
0x14007340d  mov     rcx, [rax]; Object
0x140073410  mov     [rbp+0C0h+Dacl], rax
0x140073414  mov     [rax], r14
0x140073417  test    rcx, rcx
0x14007341a  jz      short loc_140073428
0x14007341c  call    cs:__imp_ObfDereferenceObject
0x140073423  nop     dword ptr [rax+rax+00h]
0x140073428  mov     ebx, 1
0x14007342d  mov     ecx, ebx; SubAuthorityCount
0x14007342f  call    cs:__imp_RtlLengthRequiredSid
0x140073436  nop     dword ptr [rax+rax+00h]
0x14007343b  mov     edx, eax
0x14007343d  lea     rcx, [rbp+0C0h+Sid]
0x140073441  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x140073446  mov     rdi, [rbp+0C0h+Sid]
0x14007344a  test    rdi, rdi
0x14007344d  jnz     short loc_140073480
0x14007344f  lea     rax, aOriginAllocati_23; "ORIGIN: Allocating System SID buffer"
0x140073456  mov     edi, 0C000009Ah
0x14007345b  mov     ecx, edi; this
0x14007345d  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x140073462  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x140073469  mov     r8, 52200210DA4h; struct UnionFs::StackEventTracer *
0x140073473  mov     rdx, r15; int
0x140073476  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007347b  jmp     loc_14007479A
0x140073480  mov     r8b, bl; SubAuthorityCount
0x140073483  mov     dword ptr [rbp+0C0h+IdentifierAuthority.Value], r14d
0x140073487  lea     rdx, [rbp+0C0h+IdentifierAuthority]; IdentifierAuthority
0x14007348b  mov     word ptr [rbp+0C0h+IdentifierAuthority.Value+4], 500h
0x140073491  mov     rcx, rdi; Sid
0x140073494  call    cs:__imp_RtlInitializeSid
0x14007349b  nop     dword ptr [rax+rax+00h]
0x1400734a0  mov     ebx, eax
0x1400734a2  test    eax, eax
0x1400734a4  jns     short loc_1400734EA
0x1400734a6  lea     rax, aApiInitializin_10; "API: Initializing SID"
0x1400734ad  mov     r8, 4C900210DABh; struct UnionFs::StackEventTracer *
0x1400734b7  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x1400734be  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x1400734c3  mov     rdx, r15; int
0x1400734c6  mov     ecx, ebx; this
0x1400734c8  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400734cd  test    rdi, rdi
0x1400734d0  jz      short loc_1400734E3
0x1400734d2  xor     edx, edx; Tag
0x1400734d4  mov     rcx, rdi; P
0x1400734d7  call    cs:__imp_ExFreePoolWithTag
0x1400734de  nop     dword ptr [rax+rax+00h]
0x1400734e3  mov     eax, ebx
0x1400734e5  jmp     loc_14007479C
0x1400734ea  xor     edx, edx; SubAuthority
0x1400734ec  mov     rcx, rdi; Sid
0x1400734ef  call    cs:__imp_RtlSubAuthoritySid
0x1400734f6  nop     dword ptr [rax+rax+00h]
0x1400734fb  lea     rcx, [rbp+0C0h+SecurityDescriptor]
0x1400734ff  mov     dword ptr [rax], 12h
0x140073505  movzx   eax, byte ptr [rdi+1]
0x140073509  lea     r12d, ds:44h[rax*4]
0x140073511  mov     edx, r12d
0x140073514  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x140073519  mov     rbx, [rbp+0C0h+SecurityDescriptor]
0x14007351d  test    rbx, rbx
0x140073520  jnz     short loc_140073553
0x140073522  lea     rax, aOriginAllocati_43; "ORIGIN: Allocating SD buffer"
0x140073529  mov     edi, 0C000009Ah
0x14007352e  mov     ecx, edi; this
0x140073530  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x140073535  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x14007353c  mov     r8, 52300210DBBh; struct UnionFs::StackEventTracer *
0x140073546  mov     rdx, r15; int
0x140073549  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007354e  jmp     loc_140074788
0x140073553  mov     edx, 1; Revision
0x140073558  mov     rcx, rbx; SecurityDescriptor
0x14007355b  call    cs:__imp_RtlCreateSecurityDescriptor
0x140073562  nop     dword ptr [rax+rax+00h]
0x140073567  mov     edi, eax
0x140073569  test    eax, eax
0x14007356b  jns     short loc_1400735B1
0x14007356d  lea     rax, aApiInitializin_18; "API: Initializing SD"
0x140073574  mov     r8, 52400210DC4h; struct UnionFs::StackEventTracer *
0x14007357e  lea     r9, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x140073585  mov     qword ptr [rsp+1C0h+DesiredAccess], rax; char *
0x14007358a  mov     rdx, r15; int
0x14007358d  mov     ecx, edi; this
0x14007358f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140073594  test    rbx, rbx
0x140073597  jz      loc_140074788
0x14007359d  mov     rcx, rbx; SecurityDescriptor
0x1400735a0  call    cs:__imp_FltFreeSecurityDescriptor
0x1400735a7  nop     dword ptr [rax+rax+00h]
0x1400735ac  jmp     loc_140074788
0x1400735b1  mov     r14, [rbp+0C0h+Sid]
0x1400735b5  xor     r8d, r8d; OwnerDefaulted
0x1400735b8  mov     rdx, r14; Owner
0x1400735bb  mov     rcx, rbx; SecurityDescriptor
0x1400735be  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400735c5  nop     dword ptr [rax+rax+00h]
0x1400735ca  mov     edi, eax
0x1400735cc  test    eax, eax
0x1400735ce  jns     short loc_1400735E3
0x1400735d0  lea     rax, aApiSettingOwne; "API: Setting owner in SD"
0x1400735d7  mov     r8, 52500210DCBh
0x1400735e1  jmp     short loc_14007357E
0x1400735e3  xor     r8d, r8d; GroupDefaulted
0x1400735e6  mov     rdx, r14; Group
0x1400735e9  mov     rcx, rbx; SecurityDescriptor
0x1400735ec  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1400735f3  nop     dword ptr [rax+rax+00h]
0x1400735f8  mov     edi, eax
0x1400735fa  test    eax, eax
0x1400735fc  jns     short loc_140073614
0x1400735fe  lea     rax, aApiSettingGrou; "API: Setting group in SD"
0x140073605  mov     r8, 52600210DD0h
0x14007360f  jmp     loc_14007357E
0x140073614  lea     r14, [rbx+28h]
0x140073618  mov     r8d, 2; AclRevision
0x14007361e  mov     rcx, r14; Acl
0x140073621  lea     edx, [r12-28h]; AclLength
0x140073626  call    cs:__imp_RtlCreateAcl
0x14007362d  nop     dword ptr [rax+rax+00h]
0x140073632  xor     r12d, r12d
0x140073635  mov     edi, eax
0x140073637  test    eax, eax
0x140073639  jns     short loc_140073651
0x14007363b  lea     rax, aApiInitializin_5; "API: Initializing DACL"
0x140073642  mov     r8, 52700210DDAh
0x14007364c  jmp     loc_14007357E
0x140073651  mov     r9, [rbp+0C0h+Sid]; Sid
0x140073655  mov     edx, 2; AceRevision
0x14007365a  mov     r8d, 12019Fh; AccessMask
0x140073660  mov     rcx, r14; Acl
0x140073663  call    cs:__imp_RtlAddAccessAllowedAce
0x14007366a  nop     dword ptr [rax+rax+00h]
0x14007366f  mov     edi, eax
0x140073671  test    eax, eax
0x140073673  jns     short loc_14007368B
0x140073675  lea     rax, aApiAddingSyste; "API: Adding System access ACE"
0x14007367c  mov     r8, 52800210DE2h
0x140073686  jmp     loc_14007357E
0x14007368b  xor     r9d, r9d; DaclDefaulted
0x14007368e  mov     r8, r14; Dacl
0x140073691  mov     rcx, rbx; SecurityDescriptor
0x140073694  lea     r14d, [r9+1]
0x140073698  mov     dl, r14b; DaclPresent
0x14007369b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400736a2  nop     dword ptr [rax+rax+00h]
0x1400736a7  mov     edi, eax
0x1400736a9  test    eax, eax
0x1400736ab  jns     short loc_1400736C3
0x1400736ad  lea     rax, aApiSettingDacl; "API: Setting DACL in SD"
0x1400736b4  mov     r8, 52900210DE8h
0x1400736be  jmp     loc_14007357E
0x1400736c3  xor     r9d, r9d; SaclDefaulted
0x1400736c6  xor     r8d, r8d; Sacl
0x1400736c9  mov     dl, r14b; SaclPresent
0x1400736cc  mov     rcx, rbx; SecurityDescriptor
0x1400736cf  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1400736d6  nop     dword ptr [rax+rax+00h]
0x1400736db  mov     edi, eax
0x1400736dd  test    eax, eax
0x1400736df  jns     short loc_1400736F7
0x1400736e1  lea     rax, aApiSettingNull; "API: Setting null SACL in SD"
0x1400736e8  mov     r8, 52E00210DEFh
0x1400736f2  jmp     loc_14007357E
0x1400736f7  mov     edx, 3000h; ControlBitsOfInterest
0x1400736fc  mov     rcx, rbx; SecurityDescriptor
0x1400736ff  mov     r8d, edx; ControlBitsToSet
0x140073702  call    cs:__imp_RtlSetControlSecurityDescriptor
0x140073709  nop     dword ptr [rax+rax+00h]
0x14007370e  mov     edi, eax
0x140073710  test    eax, eax
0x140073712  jns     short loc_14007372A
0x140073714  lea     rax, aApiSettingSdCo; "API: Setting SD control flags"
0x14007371b  mov     r8, 4CA00210DF7h
0x140073725  jmp     loc_14007357E
0x14007372a  xorps   xmm1, xmm1
0x14007372d  mov     qword ptr [rbp+0C0h+var_A8.Length], 30h ; '0'
0x140073735  xorps   xmm0, xmm0
0x140073738  mov     qword ptr [rbp+0C0h+var_A8.Attributes], 240h
0x140073740  mov     eax, 28h ; '('
0x140073745  mov     [rbp+0C0h+var_A8.RootDirectory], r12
0x140073749  movups  xmmword ptr [rbp+0C0h+var_78.Size], xmm1
0x14007374d  mov     [rbp+0C0h+var_78.Size], ax
0x140073751  mov     [rbp+0C0h+var_A8.ObjectName], r13
0x140073755  mov     [rbp+0C0h+var_A8.SecurityDescriptor], rbx
0x140073759  mov     [rbp+0C0h+var_A8.SecurityQualityOfService], r12
0x14007375d  movups  xmmword ptr [rbp+0C0h+var_B8], xmm0
0x140073761  mov     [rbp+0C0h+var_58], r14
0x140073765  movups  xmmword ptr [rbp+0C0h+var_78.DeviceObjectHint], xmm1
0x140073769  call    cs:__imp_PsGetHostSilo
0x140073770  nop     dword ptr [rax+rax+00h]
0x140073775  mov     rcx, [rbp+0C0h+Sacl]
0x140073779  mov     [rbp+0C0h+var_58], rax
0x14007377d  mov     al, [rcx+8]
0x140073780  mov     r14d, [rcx+4]
0x140073784  neg     al
0x140073786  mov     r12d, [rcx]
0x140073789  lea     rax, [rsi+8]
0x14007378d  sbb     edi, edi
0x14007378f  mov     [rbp+0C0h+var_D0], rax
0x140073793  xor     edx, edx
0x140073795  and     edi, 8
0x140073798  add     edi, 20h ; ' '
0x14007379b  mov     [rbp+0C0h+FileObject], rdx
0x14007379f  lea     ecx, [rdx+1]
0x1400737a2  mov     [rbp+0C0h+var_C0], cl
0x1400737a5  mov     rcx, [rsi]; FileHandle
0x1400737a8  test    rcx, rcx
0x1400737ab  jz      short loc_1400737BB
0x1400737ad  call    cs:__imp_FltClose
0x1400737b4  nop     dword ptr [rax+rax+00h]
0x1400737b9  xor     edx, edx
0x1400737bb  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400737c2  lea     rax, [rbp+0C0h+var_78]
0x1400737c6  mov     [rsp+1C0h+DriverContext], rax; DriverContext
0x1400737cb  lea     r9, [rbp+0C0h+FileObject]; FileObject
0x1400737cf  mov     [rsp+1C0h+Flags], edx; Flags
0x1400737d3  lea     rax, [rbp+0C0h+var_B8]
0x1400737d7  mov     [rsp+1C0h+EaLength], edx; EaLength
0x1400737db  mov     r8, rsi; FileHandle
0x1400737de  mov     [rsp+1C0h+EaBuffer], rdx; EaBuffer
0x1400737e3  mov     [rsp+1C0h+CreateOptions], edi; CreateOptions
0x1400737e7  mov     [rsp+1C0h+CreateDisposition], r14d; CreateDisposition
0x1400737ec  mov     r14, [rbp+0C0h+Instance]
0x1400737f0  mov     [rsp+1C0h+ShareAccess], 1; ShareAccess
0x1400737f8  mov     [rsp+1C0h+FileAttributes], 6; FileAttributes
0x140073800  mov     [rsp+1C0h+AllocationSize], rdx; AllocationSize
0x140073805  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x14007380a  lea     rax, [rbp+0C0h+var_A8]
0x14007380e  mov     [rsi], rdx
0x140073811  mov     rdx, r14; Instance
0x140073814  mov     rcx, [rcx]; Filter
0x140073817  mov     [rsp+1C0h+ObjectAttributes], rax; char *
0x14007381c  mov     [rsp+1C0h+DesiredAccess], r12d; DesiredAccess
0x140073821  call    cs:__imp_FltCreateFileEx2
0x140073828  nop     dword ptr [rax+rax+00h]
0x14007382d  xor     r12d, r12d
0x140073830  mov     edi, eax
0x140073832  cmp     [rbp+0C0h+var_C0], r12b
0x140073836  jz      short loc_14007385A
0x140073838  mov     rcx, [rbp+0C0h+var_D0]
0x14007383c  mov     rax, [rbp+0C0h+FileObject]
0x140073840  mov     rdx, [rcx]
0x140073843  mov     [rcx], rax
0x140073846  test    rdx, rdx
0x140073849  jz      short loc_14007385A
0x14007384b  mov     rcx, rdx; Object
0x14007384e  call    cs:__imp_ObfDereferenceObject
0x140073855  nop     dword ptr [rax+rax+00h]
0x14007385a  test    edi, edi
0x14007385c  jns     short loc_140073874
0x14007385e  lea     rax, aApiOpenCreateI; "API: Open/Create internal file"
0x140073865  mov     r8, 76300210E24h
0x14007386f  jmp     loc_14007357E
0x140073874  mov     r8, [rbp+0C0h+Sacl]
0x140073878  lea     rsi, aUnionfsUtilsOp; "UnionFs::Utils::OpenOrCreateInternalFil"...
0x14007387f  cmp     dword ptr [r8+0Ch], 1Ch
0x140073884  jnz     loc_140073A27
0x14007388a  test    [rbp+0C0h+var_B8.Information], 0FFFFFFFFFFFFFFFDh
0x140073892  jnz     loc_140073A27
0x140073898  mov     [rsp+1C0h+AllocationSize], r12; LengthReturned
0x14007389d  lea     r9, [rbp+0C0h+SecurityDescriptor]; InputBuffer
0x1400738a1  mov     dword ptr [rsp+1C0h+IoStatusBlock], r12d; OutputBufferLength
0x1400738a6  mov     eax, 2
0x1400738ab  mov     [rbp+0C0h+SecurityDescriptor], r12
0x1400738af  mov     r8d, 9C280h; FsControlCode
0x1400738b5  mov     [rsp+1C0h+ObjectAttributes], r12; OutputBuffer
0x1400738ba  mov     rcx, r14; Instance
0x1400738bd  mov     r12, [rbp+0C0h+Dacl]
0x1400738c1  mov     word ptr [rbp+0C0h+SecurityDescriptor], ax
0x1400738c5  mov     [rsp+1C0h+DesiredAccess], 8; InputBufferLength
0x1400738cd  mov     rdx, [r12]; FileObject
  ... truncated ...
```
