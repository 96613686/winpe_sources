# UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)

- ea: `0x140068960`
- end: `0x140069530`
- name: `?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z`
- size: `3024`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140041650`
- `0x14006e1a0`

## callees

- `0x140001008`
- `0x140001c08`
- `0x140003a4c`
- `0x140003d00`
- `0x1400055d0`
- `0x140006168`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140068960`
- `0x14007018c`
- `0x140074bac`
- `0x140079f68`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x140068bc5`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x140068bc5`
- `ntoskrnl!SeAppendPrivileges` at `0x140068ad7`
- `ntoskrnl!SeAppendPrivileges` at `0x140068e94`
- `ntoskrnl!SeAppendPrivileges` at `0x140068ad7`
- `ntoskrnl!SeAppendPrivileges` at `0x140068e94`
- `ntoskrnl!SeFreePrivileges` at `0x140068ae7`
- `ntoskrnl!SeFreePrivileges` at `0x140068c97`
- `ntoskrnl!SeFreePrivileges` at `0x140068db2`
- `ntoskrnl!SeFreePrivileges` at `0x140068ea4`
- `ntoskrnl!SeFreePrivileges` at `0x140068ae7`
- `ntoskrnl!SeFreePrivileges` at `0x140068c97`
- `ntoskrnl!SeFreePrivileges` at `0x140068db2`
- `ntoskrnl!SeFreePrivileges` at `0x140068ea4`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006916e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400692d7`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006916e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400692d7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068a6f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068c2a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068d45`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068e25`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068a6f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068c2a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068d45`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068e25`
- `ntoskrnl!RtlGetAce` at `0x140069288`
- `ntoskrnl!RtlGetAce` at `0x140069288`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14006914f`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14006914f`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140068a02`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140068a02`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140069237`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140069237`
- `ntoskrnl!IoFileObjectType` at `0x1400689f1`
- `ntoskrnl!IoFileObjectType` at `0x140068bb4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140068f0c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400694f7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140068f0c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400694f7`
- `ntoskrnl!SeLockSubjectContext` at `0x140068a55`
- `ntoskrnl!SeLockSubjectContext` at `0x140068a55`

## string_xrefs

- `0x1400689cd`: `UnionFs::Utils::AccessCheck`
- `0x140068b57`: `UnionFs::Utils::AccessCheck`
- `0x140068cd5`: `UnionFs::Utils::AccessCheck`
- `0x140068de9`: `UnionFs::Utils::AccessCheck`
- `0x140068ee2`: `UnionFs::Utils::AccessCheck`
- `0x14006903a`: `UnionFs::Utils::AccessCheck`
- `0x14006910c`: `UnionFs::Utils::AccessCheck`
- `0x1400689ba`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x140068cca`: `PUSH: Requsting FILE_DELETE_CHILD`
- `0x140068b4c`: `API: Check access of target`
- `0x140068ed7`: `PUSH: Re-check access of target`
- `0x140068dde`: `PUSH: Requsting FILE_LIST_DIRECTORY`
- `0x14006906c`: `Access granted`
- `0x140069439`: `NULL DACL`
- `0x140069484`: `NO DACL`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::AccessCheck(__int128 *a1, void *a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rax
  bool v9; // zf
  struct _ACCESS_STATE *v11; // rdi
  int v12; // ebx
  __int64 v13; // rcx
  char v14; // si
  __int64 v15; // rax
  PSECURITY_SUBJECT_CONTEXT v16; // r13
  __int128 v17; // xmm1
  ACCESS_MASK PreviouslyGrantedAccess; // eax
  int v19; // edx
  char v20; // r8
  ACCESS_MASK v21; // ecx
  int v22; // r12d
  char v23; // si
  unsigned int v24; // r14d
  char v25; // r15
  unsigned int v26; // r13d
  int v27; // eax
  int v28; // eax
  int v29; // eax
  PSECURITY_SUBJECT_CONTEXT v30; // rsi
  __int64 v31; // rdx
  int v32; // r15d
  unsigned int v33; // ebx
  int v34; // eax
  __int64 v35; // rdx
  unsigned __int8 v36; // al
  int v37; // ecx
  __int128 v38; // xmm1
  __int64 v39; // xmm0_8
  char v40; // si
  unsigned int v41; // eax
  int v42; // ebx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // r9d
  struct _ACL *v46; // rcx
  struct _UNICODE_STRING *v47; // rax
  int *v48; // r13
  int v49; // edi
  int v50; // esi
  PSECURITY_DESCRIPTOR v51; // rbx
  int v52; // r8d
  int v53; // r9d
  struct _UNICODE_STRING *p_UnicodeString; // rax
  __int64 v55; // rdx
  int v56; // r8d
  int v57; // r9d
  struct _ACL *v58; // rcx
  signed int v59; // ebx
  int v60; // r14d
  int v61; // r8d
  int v62; // r9d
  struct _UNICODE_STRING *v63; // rax
  int AceCount; // ecx
  int v65; // ecx
  __int64 *v66; // rdx
  const char *v67; // rax
  struct _UNICODE_STRING *v68; // rdx
  char *v69; // [rsp+28h] [rbp-E8h]
  unsigned __int8 DaclPresent; // [rsp+90h] [rbp-80h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+91h] [rbp-7Fh] BYREF
  _BYTE v72[6]; // [rsp+92h] [rbp-7Eh] BYREF
  int v73[2]; // [rsp+98h] [rbp-78h] BYREF
  int OriginalDesiredAccess; // [rsp+A0h] [rbp-70h] BYREF
  PSID Owner; // [rsp+A8h] [rbp-68h] BYREF
  PVOID Ace; // [rsp+B0h] [rbp-60h] BYREF
  const char *v77; // [rsp+B8h] [rbp-58h] BYREF
  const char *v78; // [rsp+C0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v79; // [rsp+C8h] [rbp-48h] BYREF
  PPRIVILEGE_SET v80; // [rsp+D8h] [rbp-38h]
  int RemainingDesiredAccess; // [rsp+E0h] [rbp-30h] BYREF
  ULONG Flags; // [rsp+E4h] [rbp-2Ch] BYREF
  int v83; // [rsp+E8h] [rbp-28h] BYREF
  int *v84; // [rsp+F0h] [rbp-20h]
  PSECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+F8h] [rbp-18h]
  PACL Dacl; // [rsp+100h] [rbp-10h] BYREF
  const char *v87; // [rsp+108h] [rbp-8h] BYREF
  const char *v88; // [rsp+110h] [rbp+0h] BYREF
  UnionFs *v89; // [rsp+118h] [rbp+8h]
  struct UnionFs::StackEventTracer *v90; // [rsp+120h] [rbp+10h]
  PPRIVILEGE_SET Privileges; // [rsp+128h] [rbp+18h]
  __int128 v92; // [rsp+130h] [rbp+20h] BYREF
  _OWORD v93[2]; // [rsp+140h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+160h] [rbp+50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+168h] [rbp+58h] BYREF
  __int128 v96; // [rsp+180h] [rbp+70h] BYREF
  __int128 v97; // [rsp+190h] [rbp+80h]
  __int64 v98; // [rsp+1A0h] [rbp+90h]
  _BYTE v99[752]; // [rsp+1B0h] [rbp+A0h] BYREF

  v5 = *(_QWORD *)(a4 + 16);
  Ace = (PVOID)a4;
  SecurityDescriptor = a2;
  v9 = *(_BYTE *)(v5 + 4) == 0;
  v84 = (int *)a1;
  *(_QWORD *)v73 = a5;
  if ( !v9 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      a5,
      (struct UnionFs::StackEventTracer *)0x23200211657LL,
      (unsigned __int64)"UnionFs::Utils::AccessCheck",
      "ORIGIN: Need SubjectSecurityContext in Cbd",
      v69);
    return 3221225485LL;
  }
  v11 = *(struct _ACCESS_STATE **)(*(_QWORD *)(v5 + 24) + 8LL);
  SeAdjustAccessStateForAccessConstraints(IoFileObjectType, a2, v11);
  v12 = a3 & ~v11->PreviouslyGrantedAccess;
  if ( !v12 )
    return 0;
  v13 = *(_QWORD *)(a4 + 16);
  v14 = 1;
  LODWORD(Owner) = v12 & 0x2000000;
  v72[0] = (v12 & 0x2000000) != 0;
  if ( (*(_BYTE *)(v13 + 6) & 1) == 0 )
    v14 = *(_BYTE *)(a4 + 80);
  v15 = *(_QWORD *)(v13 + 24);
  v72[1] = v14;
  SubjectContext = (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(v15 + 8) + 32LL);
  v16 = SubjectContext;
  SeLockSubjectContext(SubjectContext);
  v89 = 0;
  v90 = 0;
  Privileges = 0;
  IoGetFileObjectGenericMapping();
  v17 = a1[1];
  PreviouslyGrantedAccess = v11->PreviouslyGrantedAccess;
  v92 = *a1;
  LODWORD(v69) = PreviouslyGrantedAccess;
  *(_QWORD *)&v93[1] = *((_QWORD *)a1 + 4);
  v93[0] = v17;
  OwnerDefaulted = UnionFs::Utils::PerformSeAccessCheck(&v92, SecurityDescriptor, SubjectContext);
  if ( OwnerDefaulted )
  {
    v19 = (int)v89;
    v20 = 0;
    v11->PreviouslyGrantedAccess |= (unsigned int)v89;
    v21 = v11->PreviouslyGrantedAccess;
    DaclPresent = 0;
    OriginalDesiredAccess = v19;
    v22 = v12 & ~(v19 | 0x2000000);
    v23 = 0;
    v24 = 0;
    if ( (v12 & 0x2000000) != 0 )
    {
      v23 = BYTE2(v21) & 1;
      if ( (v21 & 0x80u) != 0 )
      {
        v20 = 1;
        DaclPresent = 1;
      }
    }
    v11->RemainingDesiredAccess &= ~(v19 | 0x2000000);
    v25 = 0;
LABEL_12:
    if ( !(_DWORD)Owner || v23 && v20 )
      goto LABEL_69;
    goto LABEL_15;
  }
  v24 = HIDWORD(v89);
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)HIDWORD(v89),
    a5,
    v90,
    (unsigned __int64)"UnionFs::Utils::AccessCheck",
    "API: Check access of target",
    v69);
  v20 = 0;
  OriginalDesiredAccess = 0;
  v23 = 0;
  DaclPresent = 0;
  v25 = 0;
  v22 = v12;
  if ( (v12 & 0x10080) == 0 )
    goto LABEL_12;
LABEL_15:
  if ( *((_QWORD *)v84 + 1) )
  {
    if ( (unsigned __int8)SeShouldCheckForAccessRightsFromParent(IoFileObjectType, SecurityDescriptor, v11) )
    {
      v26 = 0;
      if ( (v22 & 0x10000) != 0 || (v27 = (int)Owner) != 0 && !v23 )
      {
        v28 = *v84;
        v92 = 0u;
        memset(v93, 0, 24);
        if ( (v28 & 2) != 0 )
        {
          v29 = v84[4];
          LODWORD(v92) = 1;
          DWORD1(v92) = v29;
        }
        *(_QWORD *)&v79.Length = 0;
        v79.Buffer = 0;
        v80 = 0;
        IoGetFileObjectGenericMapping();
        v30 = SubjectContext;
        v31 = *((_QWORD *)v84 + 1);
        v96 = v92;
        LODWORD(v69) = 0;
        v97 = v93[0];
        v98 = *(_QWORD *)&v93[1];
        v32 = v73[0];
        if ( (unsigned __int8)UnionFs::Utils::PerformSeAccessCheck(&v96, v31, SubjectContext) )
        {
          v26 = *(_DWORD *)&v79.Length & 0xFFFEFFBF | 0x10000;
          v22 &= ~0x10000u;
        }
        else
        {
          v24 = *(_DWORD *)(&v79.MaximumLength + 1);
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)*(unsigned int *)(&v79.MaximumLength + 1),
            v73[0],
            (struct UnionFs::StackEventTracer *)v79.Buffer,
            (unsigned __int64)"UnionFs::Utils::AccessCheck",
            "PUSH: Requsting FILE_DELETE_CHILD",
            v69);
        }
        v27 = (int)Owner;
      }
      else
      {
        v32 = v73[0];
        v30 = SubjectContext;
      }
      v33 = 0;
      if ( (v22 & 0x80u) != 0 || v27 && !DaclPresent )
      {
        v92 = 0u;
        memset(v93, 0, 24);
        if ( (*v84 & 2) != 0 )
        {
          v34 = v84[4];
          LODWORD(v92) = 1;
          DWORD1(v92) = v34;
        }
        *(_QWORD *)&v79.Length = 0;
        v79.Buffer = 0;
        v80 = 0;
        IoGetFileObjectGenericMapping();
        v35 = *((_QWORD *)v84 + 1);
        v96 = v92;
        LODWORD(v69) = 0;
        v97 = v93[0];
        v98 = *(_QWORD *)&v93[1];
        DaclPresent = UnionFs::Utils::PerformSeAccessCheck(&v96, v35, v30);
        if ( DaclPresent )
        {
          v33 = *(_DWORD *)&v79.Length & 0xFFFFFF7E | 0x80;
          v22 &= ~0x80u;
        }
        else
        {
          v24 = *(_DWORD *)(&v79.MaximumLength + 1);
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)*(unsigned int *)(&v79.MaximumLength + 1),
            v32,
            (struct UnionFs::StackEventTracer *)v79.Buffer,
            (unsigned __int64)"UnionFs::Utils::AccessCheck",
            "PUSH: Requsting FILE_LIST_DIRECTORY",
            v69);
        }
      }
      if ( v22 )
      {
        IoGetFileObjectGenericMapping();
        v38 = *((_OWORD *)v84 + 1);
        v96 = *(_OWORD *)v84;
        v39 = *((_QWORD *)v84 + 4);
        LODWORD(v69) = v11->PreviouslyGrantedAccess;
        v97 = v38;
        v98 = v39;
        v40 = UnionFs::Utils::PerformSeAccessCheck(&v96, SecurityDescriptor, v30);
        if ( Privileges )
        {
          SeAppendPrivileges(v11, Privileges);
          SeFreePrivileges(Privileges);
          Privileges = 0;
        }
        if ( v40 )
        {
          v37 = (int)v89;
          goto LABEL_56;
        }
        if ( v22 == 0x2000000 && (v33 || v26) )
        {
          v37 = 0;
          goto LABEL_56;
        }
        v24 = HIDWORD(v89);
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)HIDWORD(v89),
          v32,
          v90,
          (unsigned __int64)"UnionFs::Utils::AccessCheck",
          "PUSH: Re-check access of target",
          v69);
      }
      else
      {
        if ( v33 || v26 )
          v36 = 1;
        else
          v36 = OwnerDefaulted;
        if ( v36 )
        {
          v37 = OriginalDesiredAccess;
LABEL_56:
          v41 = v33;
          v25 = 1;
          v42 = v26 | v33;
          v43 = v26 | v41;
          v16 = SubjectContext;
          v11->PreviouslyGrantedAccess |= v37 | v43;
          v11->RemainingDesiredAccess &= ~(v37 | v42 | 0x2000000);
          goto LABEL_57;
        }
      }
      v16 = SubjectContext;
LABEL_51:
      if ( v16 && v16->PrimaryToken )
        SeUnlockSubjectContext(v16);
      return v24;
    }
    v25 = 0;
  }
LABEL_69:
  if ( !OwnerDefaulted )
    goto LABEL_51;
LABEL_57:
  v44 = *(_QWORD *)v73;
  **(_DWORD **)v73 = 0;
  *(_WORD *)(v44 + 548) = 0;
  if ( (unsigned int)dword_14009E178 <= 5
    || (qword_14009E188 & 0x10000) == 0
    || (qword_14009E190 & 0x10000) != qword_14009E190 )
  {
    goto LABEL_109;
  }
  v79 = 0;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v99, 0x6800211794uLL);
  UnionFs::Utils::GetUserSidString(Ace, &v79, v99);
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x10000) != 0
    && (qword_14009E190 & 0x10000) == qword_14009E190 )
  {
    v46 = (struct _ACL *)&FsTlEmptyUnicodeString;
    OriginalDesiredAccess = v11->OriginalDesiredAccess;
    LODWORD(Owner) = v11->PreviouslyGrantedAccess;
    RemainingDesiredAccess = v11->RemainingDesiredAccess;
    Flags = v11->Flags;
    v47 = &v79;
    if ( !v79.Buffer )
      v47 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
    v83 = v22;
    Ace = v47;
    v87 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
    OwnerDefaulted = 1;
    v73[0] = 6052;
    v77 = "UnionFs::Utils::AccessCheck";
    if ( *((_QWORD *)v84 + 4) )
      v46 = (struct _ACL *)(v84 + 6);
    v78 = "Access granted";
    Dacl = v46;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v46,
      (unsigned int)&word_14009A156,
      (unsigned int)&FsTlEmptyUnicodeString,
      v45,
      (__int64)&v78,
      (__int64)&v77,
      (__int64)&v87,
      (__int64)v73,
      (__int64)&Dacl,
      (__int64)&Ace,
      (__int64)&OwnerDefaulted,
      (__int64)v72,
      (__int64)&v83,
      (__int64)&Flags,
      (__int64)&RemainingDesiredAccess,
      (__int64)&Owner,
      (__int64)&OriginalDesiredAccess);
  }
  v48 = v84;
  v49 = (v25 != 0) + 1;
  OriginalDesiredAccess = v49;
  v50 = 0;
  do
  {
    v51 = SecurityDescriptor;
    if ( v50 )
      v51 = (PSECURITY_DESCRIPTOR)*((_QWORD *)v48 + 1);
    OwnerDefaulted = 0;
    Owner = 0;
    UnicodeString = 0;
    if ( RtlGetOwnerSecurityDescriptor(v51, &Owner, &OwnerDefaulted) >= 0
      && RtlConvertSidToUnicodeString(&UnicodeString, Owner, 1u) >= 0
      && (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x10000) != 0
      && (qword_14009E190 & 0x10000) == qword_14009E190 )
    {
      p_UnicodeString = &UnicodeString;
      v73[0] = 6080;
      if ( !UnicodeString.Buffer )
        p_UnicodeString = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v87 = "UnionFs::Utils::AccessCheck";
      v78 = (const char *)p_UnicodeString;
      v77 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      Ace = "Owner";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (unsigned int)&FsTlEmptyUnicodeString,
        (unsigned int)byte_14009A081,
        v52,
        v53,
        (__int64)&Ace,
        (__int64)&v87,
        (__int64)&v77,
        (__int64)v73,
        (__int64)&v78);
    }
    Dacl = 0;
    DaclPresent = 0;
    if ( RtlGetDaclSecurityDescriptor(v51, &DaclPresent, &Dacl, &OwnerDefaulted) >= 0 )
    {
      if ( DaclPresent )
      {
        v58 = Dacl;
        if ( Dacl )
        {
          v59 = 0;
          if ( Dacl->AceCount )
          {
            do
            {
              Ace = 0;
              if ( RtlGetAce(v58, v59, &Ace) >= 0 )
              {
                v55 = *(unsigned __int8 *)Ace;
                if ( !*(_BYTE *)Ace || (_DWORD)v55 == 1 )
                {
                  v60 = *((_DWORD *)Ace + 1);
                  Owner = (char *)Ace + 8;
                  FsFltWil::Details::FreeUnicodeString(&UnicodeString, (struct _UNICODE_STRING *)v55);
                  UnicodeString = 0;
                  if ( RtlConvertSidToUnicodeString(&UnicodeString, Owner, 1u) >= 0 && (unsigned int)dword_14009E178 > 5 )
                  {
                    v55 = 0x10000;
                    if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
                    {
                      v63 = &UnicodeString;
                      v73[0] = v60;
                      if ( !UnicodeString.Buffer )
                        v63 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
                      v77 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      v78 = (const char *)v63;
                      v87 = "UnionFs::Utils::AccessCheck";
                      v72[0] = *(_BYTE *)Ace;
                      AceCount = Dacl->AceCount;
                      v88 = "DACL";
                      v83 = AceCount;
                      Flags = v59;
                      RemainingDesiredAccess = 6135;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        AceCount,
                        (unsigned int)&word_140099C4E,
                        v61,
                        v62,
                        (__int64)&v88,
                        (__int64)&v87,
                        (__int64)&v77,
                        (__int64)&RemainingDesiredAccess,
                        (__int64)&Flags,
                        (__int64)&v83,
                        (__int64)v72,
                        (__int64)v73,
                        (__int64)&v78);
                    }
                  }
                }
              }
              v58 = Dacl;
              ++v59;
            }
            while ( v59 < Dacl->AceCount );
            v49 = OriginalDesiredAccess;
            v48 = v84;
          }
        }
        else if ( (unsigned int)dword_14009E178 > 5 )
        {
          v65 = qword_14009E190;
          if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
          {
            v73[0] = 6145;
            v88 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
            v66 = qword_14009A040;
            v67 = "NULL DACL";
LABEL_106:
            v77 = v67;
            v78 = "UnionFs::Utils::AccessCheck";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v65,
              (_DWORD)v66,
              v56,
              v57,
              (__int64)&v77,
              (__int64)&v78,
              (__int64)&v88,
              (__int64)v73);
          }
        }
      }
      else if ( (unsigned int)dword_14009E178 > 5 )
      {
        v65 = qword_14009E190;
        if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
        {
          v73[0] = 6151;
          v88 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          v66 = (__int64 *)byte_140099BC3;
          v67 = "NO DACL";
          goto LABEL_106;
        }
      }
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, (struct _UNICODE_STRING *)v55);
    ++v50;
  }
  while ( v50 < v49 );
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v99);
  FsFltWil::Details::FreeUnicodeString(&v79, v68);
  v16 = SubjectContext;
LABEL_109:
  if ( v16 )
  {
    if ( v16->PrimaryToken )
      SeUnlockSubjectContext(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x140068960  mov     [rsp-8+arg_10], rbx
0x140068965  push    rbp
0x140068966  push    rsi
0x140068967  push    rdi
0x140068968  push    r12
0x14006896a  push    r13
0x14006896c  push    r14
0x14006896e  push    r15
0x140068970  lea     rbp, [rsp-3A0h]
0x140068978  sub     rsp, 4B0h
0x14006897f  mov     rax, cs:__security_cookie
0x140068986  xor     rax, rsp
0x140068989  mov     [rbp+3D0h+var_40], rax
0x140068990  mov     rax, [r9+10h]
0x140068994  mov     r13, r9
0x140068997  mov     r12, qword ptr [rbp+3D0h+arg_20]
0x14006899e  mov     esi, r8d
0x1400689a1  mov     [rbp+3D0h+Ace], r9
0x1400689a5  mov     r14, rcx
0x1400689a8  mov     [rbp+3D0h+SecurityDescriptor], rdx
0x1400689ac  cmp     byte ptr [rax+4], 0
0x1400689b0  mov     [rbp+3D0h+var_3F0], rcx
0x1400689b4  mov     qword ptr [rbp+3D0h+var_448], r12
0x1400689b8  jz      short loc_1400689ED
0x1400689ba  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x1400689c1  mov     ebx, 0C000000Dh
0x1400689c6  mov     ecx, ebx; this
0x1400689c8  mov     [rsp+4E0h+var_4C0], rax; char *
0x1400689cd  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x1400689d4  mov     r8, 23200211657h; struct UnionFs::StackEventTracer *
0x1400689de  mov     rdx, r12; int
0x1400689e1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400689e6  mov     eax, ebx
0x1400689e8  jmp     loc_140069505
0x1400689ed  mov     rax, [rax+18h]
0x1400689f1  mov     rcx, cs:__imp_IoFileObjectType
0x1400689f8  mov     rdi, [rax+8]
0x1400689fc  mov     rcx, [rcx]
0x1400689ff  mov     r8, rdi
0x140068a02  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x140068a09  nop     dword ptr [rax+rax+00h]
0x140068a0e  mov     ebx, [rdi+14h]
0x140068a11  not     ebx
0x140068a13  and     ebx, esi
0x140068a15  jz      loc_140069503
0x140068a1b  mov     rcx, [r13+10h]
0x140068a1f  mov     r15d, ebx
0x140068a22  and     r15d, 2000000h
0x140068a29  mov     sil, 1
0x140068a2c  mov     dword ptr [rbp+3D0h+Owner], r15d
0x140068a30  setnz   [rbp+3D0h+var_44E]
0x140068a34  test    byte ptr [rcx+6], 1
0x140068a38  jnz     short loc_140068A3E
0x140068a3a  mov     sil, [r13+50h]
0x140068a3e  mov     rax, [rcx+18h]
0x140068a42  mov     [rbp+3D0h+var_44D], sil
0x140068a46  mov     r13, [rax+8]
0x140068a4a  add     r13, 20h ; ' '
0x140068a4e  mov     rcx, r13; SubjectContext
0x140068a51  mov     [rbp+3D0h+SubjectContext], r13
0x140068a55  call    cs:__imp_SeLockSubjectContext
0x140068a5c  nop     dword ptr [rax+rax+00h]
0x140068a61  xor     eax, eax
0x140068a63  mov     [rbp+3D0h+var_3C8], rax
0x140068a67  mov     [rbp+3D0h+var_3C0], rax
0x140068a6b  mov     [rbp+3D0h+Privileges], rax
0x140068a6f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068a76  nop     dword ptr [rax+rax+00h]
0x140068a7b  movups  xmm0, xmmword ptr [r14]
0x140068a7f  mov     rdx, [rbp+3D0h+SecurityDescriptor]
0x140068a83  lea     rcx, [rbp+3D0h+var_3C8]
0x140068a87  movups  xmm1, xmmword ptr [r14+10h]
0x140068a8c  mov     [rsp+4E0h+var_4A0], rcx
0x140068a91  mov     r8, r13
0x140068a94  mov     byte ptr [rsp+4E0h+var_4A8], sil
0x140068a99  lea     rcx, [rbp+3D0h+var_3B0]
0x140068a9d  mov     [rsp+4E0h+var_4B0], rax
0x140068aa2  mov     eax, [rdi+14h]
0x140068aa5  movaps  [rbp+3D0h+var_3B0], xmm0
0x140068aa9  movsd   xmm0, qword ptr [r14+20h]
0x140068aaf  mov     dword ptr [rsp+4E0h+var_4B8], eax; char *
0x140068ab3  movsd   [rbp+3D0h+var_390], xmm0
0x140068ab8  mov     dword ptr [rsp+4E0h+var_4C0], ebx
0x140068abc  movaps  [rbp+3D0h+var_3A0], xmm1
0x140068ac0  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x140068ac5  mov     rdx, [rbp+3D0h+Privileges]; Privileges
0x140068ac9  mov     sil, al
0x140068acc  mov     [rbp+3D0h+OwnerDefaulted], al
0x140068acf  test    rdx, rdx
0x140068ad2  jz      short loc_140068AFB
0x140068ad4  mov     rcx, rdi; AccessState
0x140068ad7  call    cs:__imp_SeAppendPrivileges
0x140068ade  nop     dword ptr [rax+rax+00h]
0x140068ae3  mov     rcx, [rbp+3D0h+Privileges]; Privileges
0x140068ae7  call    cs:__imp_SeFreePrivileges
0x140068aee  nop     dword ptr [rax+rax+00h]
0x140068af3  mov     [rbp+3D0h+Privileges], 0
0x140068afb  test    sil, sil
0x140068afe  jz      short loc_140068B48
0x140068b00  mov     edx, dword ptr [rbp+3D0h+var_3C8]
0x140068b03  xor     r8b, r8b
0x140068b06  or      [rdi+14h], edx
0x140068b09  mov     eax, edx
0x140068b0b  mov     ecx, [rdi+14h]
0x140068b0e  bts     eax, 19h
0x140068b12  not     eax
0x140068b14  mov     [rbp+3D0h+DaclPresent], r8b
0x140068b18  mov     r12d, eax
0x140068b1b  mov     [rbp+3D0h+var_440], edx
0x140068b1e  and     r12d, ebx
0x140068b21  xor     sil, sil
0x140068b24  xor     r14d, r14d
0x140068b27  test    r15d, r15d
0x140068b2a  jz      short loc_140068B40
0x140068b2c  mov     esi, ecx
0x140068b2e  shr     esi, 10h
0x140068b31  and     sil, 1
0x140068b35  test    cl, cl
0x140068b37  jns     short loc_140068B40
0x140068b39  mov     r8b, 1
0x140068b3c  mov     [rbp+3D0h+DaclPresent], r8b
0x140068b40  and     [rdi+10h], eax
0x140068b43  xor     r15b, r15b
0x140068b46  jmp     short loc_140068B8D
0x140068b48  mov     r14d, dword ptr [rbp+3D0h+var_3C8+4]
0x140068b4c  lea     rax, aApiCheckAccess; "API: Check access of target"
0x140068b53  mov     r8, [rbp+3D0h+var_3C0]; struct UnionFs::StackEventTracer *
0x140068b57  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x140068b5e  mov     ecx, r14d; this
0x140068b61  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068b66  mov     rdx, r12; int
0x140068b69  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068b6e  xor     r8b, r8b
0x140068b71  mov     [rbp+3D0h+var_440], 0
0x140068b78  xor     sil, sil
0x140068b7b  mov     [rbp+3D0h+DaclPresent], r8b
0x140068b7f  xor     r15b, r15b
0x140068b82  mov     r12d, ebx
0x140068b85  test    ebx, 10080h
0x140068b8b  jnz     short loc_140068BA5
0x140068b8d  cmp     dword ptr [rbp+3D0h+Owner], 0
0x140068b91  jz      loc_1400690FD
0x140068b97  test    sil, sil
0x140068b9a  jz      short loc_140068BA5
0x140068b9c  test    r8b, r8b
0x140068b9f  jnz     loc_1400690FD
0x140068ba5  mov     rbx, [rbp+3D0h+var_3F0]
0x140068ba9  cmp     qword ptr [rbx+8], 0
0x140068bae  jz      loc_1400690FD
0x140068bb4  mov     rcx, cs:__imp_IoFileObjectType
0x140068bbb  mov     r8, rdi
0x140068bbe  mov     rdx, [rbp+3D0h+SecurityDescriptor]
0x140068bc2  mov     rcx, [rcx]
0x140068bc5  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x140068bcc  nop     dword ptr [rax+rax+00h]
0x140068bd1  test    al, al
0x140068bd3  jz      loc_1400690FA
0x140068bd9  xor     r13d, r13d
0x140068bdc  bt      r12d, 10h
0x140068be1  jb      short loc_140068BF7
0x140068be3  mov     eax, dword ptr [rbp+3D0h+Owner]
0x140068be6  test    eax, eax
0x140068be8  jz      loc_140068CEE
0x140068bee  test    sil, sil
0x140068bf1  jnz     loc_140068CEE
0x140068bf7  mov     eax, [rbx]
0x140068bf9  xor     ecx, ecx
0x140068bfb  mov     qword ptr [rbp+3D0h+var_3B0], rcx
0x140068bff  xorps   xmm0, xmm0
0x140068c02  mov     qword ptr [rbp+3D0h+var_3B0+8], rcx
0x140068c06  mov     qword ptr [rbp+3D0h+var_3A0], rcx
0x140068c0a  movups  [rbp+3D0h+var_3A0+8], xmm0
0x140068c0e  test    al, 2
0x140068c10  jz      short loc_140068C1E
0x140068c12  mov     eax, [rbx+10h]
0x140068c15  or      ecx, 1
0x140068c18  mov     dword ptr [rbp+3D0h+var_3B0], ecx
0x140068c1b  mov     dword ptr [rbp+3D0h+var_3B0+4], eax
0x140068c1e  mov     qword ptr [rbp+3D0h+var_418.Length], r13
0x140068c22  mov     [rbp+3D0h+var_418.Buffer], r13
0x140068c26  mov     [rbp+3D0h+var_408], r13
0x140068c2a  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068c31  nop     dword ptr [rax+rax+00h]
0x140068c36  movups  xmm0, [rbp+3D0h+var_3B0]
0x140068c3a  mov     rsi, [rbp+3D0h+SubjectContext]
0x140068c3e  lea     rcx, [rbp+3D0h+var_418]
0x140068c42  movups  xmm1, [rbp+3D0h+var_3A0]
0x140068c46  mov     rdx, [rbx+8]
0x140068c4a  mov     r8, rsi
0x140068c4d  mov     [rsp+4E0h+var_4A0], rcx
0x140068c52  mov     cl, [rbp+3D0h+var_44D]
0x140068c55  mov     byte ptr [rsp+4E0h+var_4A8], cl
0x140068c59  lea     rcx, [rbp+3D0h+var_360]
0x140068c5d  mov     [rsp+4E0h+var_4B0], rax
0x140068c62  movaps  [rbp+3D0h+var_360], xmm0
0x140068c66  movsd   xmm0, [rbp+3D0h+var_390]
0x140068c6b  mov     dword ptr [rsp+4E0h+var_4B8], r13d; char *
0x140068c70  mov     dword ptr [rsp+4E0h+var_4C0], 40h ; '@'
0x140068c78  movaps  [rbp+3D0h+var_350], xmm1
0x140068c7f  movsd   [rbp+3D0h+var_340], xmm0
0x140068c87  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x140068c8c  mov     rcx, [rbp+3D0h+var_408]; Privileges
0x140068c90  mov     bl, al
0x140068c92  test    rcx, rcx
0x140068c95  jz      short loc_140068CA7
0x140068c97  call    cs:__imp_SeFreePrivileges
0x140068c9e  nop     dword ptr [rax+rax+00h]
0x140068ca3  mov     [rbp+3D0h+var_408], r13
0x140068ca7  mov     r15, qword ptr [rbp+3D0h+var_448]
0x140068cab  test    bl, bl
0x140068cad  jz      short loc_140068CC6
0x140068caf  mov     r13d, dword ptr [rbp+3D0h+var_418.Length]
0x140068cb3  and     r13d, 0FFFFFFBFh
0x140068cb7  bts     r13d, 10h
0x140068cbc  btr     r12d, 10h
0x140068cc1  mov     eax, dword ptr [rbp+3D0h+Owner]
0x140068cc4  jmp     short loc_140068CF6
0x140068cc6  mov     r14d, dword ptr [rbp+3D0h+var_418+4]
0x140068cca  lea     rax, aPushRequstingF_0; "PUSH: Requsting FILE_DELETE_CHILD"
0x140068cd1  mov     r8, [rbp+3D0h+var_418.Buffer]; struct UnionFs::StackEventTracer *
0x140068cd5  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x140068cdc  mov     ecx, r14d; this
0x140068cdf  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068ce4  mov     rdx, r15; int
0x140068ce7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068cec  jmp     short loc_140068CC1
0x140068cee  mov     r15, qword ptr [rbp+3D0h+var_448]
0x140068cf2  mov     rsi, [rbp+3D0h+SubjectContext]
0x140068cf6  xor     ebx, ebx
0x140068cf8  test    r12b, r12b
0x140068cfb  js      short loc_140068D0E
0x140068cfd  test    eax, eax
0x140068cff  jz      loc_140068E00
0x140068d05  cmp     [rbp+3D0h+DaclPresent], bl
0x140068d08  jnz     loc_140068E00
0x140068d0e  mov     rdx, [rbp+3D0h+var_3F0]
0x140068d12  xor     ecx, ecx
0x140068d14  xorps   xmm0, xmm0
0x140068d17  mov     qword ptr [rbp+3D0h+var_3B0], rcx
0x140068d1b  mov     qword ptr [rbp+3D0h+var_3B0+8], rcx
0x140068d1f  mov     qword ptr [rbp+3D0h+var_3A0], rcx
0x140068d23  mov     eax, [rdx]
0x140068d25  movups  [rbp+3D0h+var_3A0+8], xmm0
0x140068d29  test    al, 2
0x140068d2b  jz      short loc_140068D39
0x140068d2d  mov     eax, [rdx+10h]
0x140068d30  or      ecx, 1
0x140068d33  mov     dword ptr [rbp+3D0h+var_3B0], ecx
0x140068d36  mov     dword ptr [rbp+3D0h+var_3B0+4], eax
0x140068d39  mov     qword ptr [rbp+3D0h+var_418.Length], rbx
0x140068d3d  mov     [rbp+3D0h+var_418.Buffer], rbx
0x140068d41  mov     [rbp+3D0h+var_408], rbx
0x140068d45  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068d4c  nop     dword ptr [rax+rax+00h]
0x140068d51  movups  xmm0, [rbp+3D0h+var_3B0]
0x140068d55  mov     rdx, [rbp+3D0h+var_3F0]
0x140068d59  lea     rcx, [rbp+3D0h+var_418]
0x140068d5d  movups  xmm1, [rbp+3D0h+var_3A0]
0x140068d61  mov     [rsp+4E0h+var_4A0], rcx
0x140068d66  mov     r8, rsi
0x140068d69  mov     cl, [rbp+3D0h+var_44D]
0x140068d6c  mov     rdx, [rdx+8]
0x140068d70  mov     byte ptr [rsp+4E0h+var_4A8], cl
0x140068d74  lea     rcx, [rbp+3D0h+var_360]
0x140068d78  mov     [rsp+4E0h+var_4B0], rax
0x140068d7d  movaps  [rbp+3D0h+var_360], xmm0
0x140068d81  movsd   xmm0, [rbp+3D0h+var_390]
0x140068d86  mov     dword ptr [rsp+4E0h+var_4B8], ebx; char *
0x140068d8a  mov     dword ptr [rsp+4E0h+var_4C0], 1
0x140068d92  movaps  [rbp+3D0h+var_350], xmm1
0x140068d99  movsd   [rbp+3D0h+var_340], xmm0
0x140068da1  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x140068da6  mov     rcx, [rbp+3D0h+var_408]; Privileges
0x140068daa  mov     [rbp+3D0h+DaclPresent], al
0x140068dad  test    rcx, rcx
0x140068db0  jz      short loc_140068DC5
0x140068db2  call    cs:__imp_SeFreePrivileges
0x140068db9  nop     dword ptr [rax+rax+00h]
0x140068dbe  mov     al, [rbp+3D0h+DaclPresent]
0x140068dc1  mov     [rbp+3D0h+var_408], rbx
0x140068dc5  test    al, al
0x140068dc7  jz      short loc_140068DDA
0x140068dc9  mov     ebx, dword ptr [rbp+3D0h+var_418.Length]
0x140068dcc  and     ebx, 0FFFFFFFEh
0x140068dcf  bts     ebx, 7
0x140068dd3  btr     r12d, 7
0x140068dd8  jmp     short loc_140068E00
0x140068dda  mov     r14d, dword ptr [rbp+3D0h+var_418+4]
0x140068dde  lea     rax, aPushRequstingF; "PUSH: Requsting FILE_LIST_DIRECTORY"
0x140068de5  mov     r8, [rbp+3D0h+var_418.Buffer]; struct UnionFs::StackEventTracer *
0x140068de9  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x140068df0  mov     ecx, r14d; this
0x140068df3  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068df8  mov     rdx, r15; int
0x140068dfb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068e00  test    r12d, r12d
0x140068e03  jnz     short loc_140068E25
0x140068e05  test    ebx, ebx
0x140068e07  jnz     short loc_140068E0E
0x140068e09  test    r13d, r13d
  ... truncated ...
```
