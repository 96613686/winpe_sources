# SrpVerifyDll

- ea: `0x140034550`
- end: `0x14003523c`
- name: `SrpVerifyDll`
- size: `3308`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140033f50`

## callees

- `0x140001550`
- `0x140001590`
- `0x140002118`
- `0x140006a20`
- `0x140006c40`
- `0x14001fb40`
- `0x140020090`
- `0x1400237dc`
- `0x140023934`
- `0x140029678`
- `0x14002f560`
- `0x140031370`
- `0x140032a50`
- `0x140032dc0`
- `0x140032e40`
- `0x140032f60`
- `0x140033130`
- `0x1400333b0`
- `0x140034550`
- `0x140035460`
- `0x140035580`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034886`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034954`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034c02`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034886`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034954`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140034c02`
- `ntoskrnl!IoFileObjectType` at `0x140034858`
- `ntoskrnl!IoFileObjectType` at `0x1400348b6`
- `ntoskrnl!IoFileObjectType` at `0x140034927`
- `ntoskrnl!ObfDereferenceObject` at `0x14003497b`
- `ntoskrnl!ObfDereferenceObject` at `0x140034a7f`
- `ntoskrnl!ObfDereferenceObject` at `0x140034c73`
- `ntoskrnl!ObfDereferenceObject` at `0x140035187`
- `ntoskrnl!ObfDereferenceObject` at `0x14003497b`
- `ntoskrnl!ObfDereferenceObject` at `0x140034a7f`
- `ntoskrnl!ObfDereferenceObject` at `0x140034c73`
- `ntoskrnl!ObfDereferenceObject` at `0x140035187`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003515a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003515a`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140034670`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140034670`
- `ntoskrnl!ExAllocatePool2` at `0x140034d48`
- `ntoskrnl!ExAllocatePool2` at `0x140034d48`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400345c4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400345c4`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400346e4`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400346e4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400348d2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400348d2`
- `ntoskrnl!SeGetLogonSessionToken` at `0x14003482e`
- `ntoskrnl!SeGetLogonSessionToken` at `0x14003482e`
- `ntoskrnl!ZwDuplicateObject` at `0x140034911`
- `ntoskrnl!ZwDuplicateObject` at `0x140034911`
- `ntoskrnl!ZwDuplicateToken` at `0x140034735`
- `ntoskrnl!ZwDuplicateToken` at `0x140034735`
- `ntoskrnl!ZwQueryInformationToken` at `0x140034787`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400347fd`
- `ntoskrnl!ZwQueryInformationToken` at `0x140034787`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400347fd`
- `ntoskrnl!wcsrchr` at `0x140034e02`
- `ntoskrnl!wcsrchr` at `0x140034e02`
- `ntoskrnl!ZwClose` at `0x14003474d`
- `ntoskrnl!ZwClose` at `0x14003519c`
- `ntoskrnl!ZwClose` at `0x1400351b1`
- `ntoskrnl!ZwClose` at `0x1400351c6`
- `ntoskrnl!ZwClose` at `0x14003474d`
- `ntoskrnl!ZwClose` at `0x14003519c`
- `ntoskrnl!ZwClose` at `0x1400351b1`
- `ntoskrnl!ZwClose` at `0x1400351c6`
- `ntoskrnl!EtwWriteTransfer` at `0x140035025`
- `ntoskrnl!EtwWriteTransfer` at `0x140035137`
- `ntoskrnl!EtwWriteTransfer` at `0x140035025`
- `ntoskrnl!EtwWriteTransfer` at `0x140035137`

## pseudocode

```c
__int64 __fastcall SrpVerifyDll(__int64 a1, unsigned int a2, int *a3, int a4, KPROCESSOR_MODE a5, _QWORD *a6)
{
  __int64 v7; // rsi
  int v8; // r13d
  int *v10; // r12
  HANDLE CurrentProcessId; // rax
  __int64 v13; // rdx
  __int64 PerformanceCounter; // rbx
  __int64 v15; // r8
  int v16; // ecx
  void *v17; // r15
  void *v18; // rax
  NTSTATUS LogonSessionToken; // edi
  __int64 Policy; // rax
  NTSTATUS IsTokenService; // eax
  __int64 v22; // rax
  int v23; // ecx
  char *v24; // r12
  char v25; // r15
  unsigned int v26; // ecx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  _QWORD *v30; // r14
  void *v31; // rcx
  int v32; // ecx
  int v34; // eax
  bool v35; // r14
  char IsEnabled; // r15
  bool v37; // cl
  __int64 v38; // rax
  void *v40; // r14
  int v41; // r15d
  __int64 v42; // rdx
  unsigned __int64 updated; // r15
  const struct _TraceLoggingMetadata_t *v44; // r9
  __int64 v45; // r8
  unsigned __int16 v46; // bx
  wchar_t *Pool2; // r14
  unsigned __int64 v48; // rdx
  wchar_t *v49; // r9
  unsigned __int64 v50; // rcx
  wchar_t *v51; // r8
  wchar_t *v52; // rcx
  wchar_t *v53; // rax
  __int16 *v54; // rax
  char v56; // [rsp+70h] [rbp-90h] BYREF
  char v57; // [rsp+71h] [rbp-8Fh]
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-80h] BYREF
  int v60[2]; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h] BYREF
  char v63[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v64; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE NewTokenHandle; // [rsp+B0h] [rbp-50h] BYREF
  void *TargetHandle; // [rsp+B8h] [rbp-48h] BYREF
  PVOID FileObject; // [rsp+C0h] [rbp-40h]
  __int64 v68; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v69; // [rsp+D0h] [rbp-30h] BYREF
  PVOID Object; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v71; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+120h] [rbp+20h] BYREF
  __int128 v74; // [rsp+130h] [rbp+30h]
  __int64 *v75; // [rsp+140h] [rbp+40h]
  __int64 v76; // [rsp+148h] [rbp+48h]
  char *v77; // [rsp+150h] [rbp+50h]
  __int64 v78; // [rsp+158h] [rbp+58h] BYREF
  __int128 v79; // [rsp+160h] [rbp+60h]
  char *v80; // [rsp+170h] [rbp+70h]
  __int64 v81; // [rsp+178h] [rbp+78h]

  v64 = (unsigned __int64)a3;
  FileObject = 0;
  v7 = 0;
  TargetHandle = 0;
  v8 = 0;
  v68 = 0;
  NewTokenHandle = 0;
  v10 = a3;
  *(_QWORD *)v60 = 0;
  P = 0;
  v69 = 0;
  v56 = 0;
  LODWORD(v62) = 0;
  v71 = a6;
  CurrentProcessId = PsGetCurrentProcessId();
  LOBYTE(v13) = 1;
  *(_QWORD *)v63 = CurrentProcessId;
  PerformanceCounter = AiQueryPerformanceCounter(0, v13);
  *a6 = 0;
  if ( a2 < 0xA || (v16 = *(unsigned __int16 *)(a1 + 8), a2 != v16 + 10) || (v16 & 1) != 0 || !(_WORD)v16 || a4 != 4 )
  {
    LogonSessionToken = -1073741811;
    goto LABEL_95;
  }
  *a6 = 4;
  v17 = *(void **)a1;
  LOWORD(v60[0]) = *(_WORD *)(a1 + 8);
  HIWORD(v60[0]) = v60[0];
  v18 = (void *)AiAlloc();
  P = v18;
  if ( !v18 )
  {
    LogonSessionToken = -1073741801;
    goto LABEL_95;
  }
  memmove(v18, (const void *)(a1 + 10), LOWORD(v60[0]));
  LogonSessionToken = RtlRunOnceExecuteOnce(&AipInitRunOnceState, AipInitRunOnce, 0, 0);
  if ( LogonSessionToken >= 0 )
  {
    Policy = SrpGetPolicy();
    v7 = Policy;
    if ( !Policy )
    {
      LogonSessionToken = -1073740956;
      goto LABEL_95;
    }
    if ( *(int *)(Policy + 80) >= 0 && *(_DWORD *)(*(_QWORD *)(Policy + 88) + 12LL) )
    {
      v57 = 1;
    }
    else
    {
      v57 = 0;
      if ( !*(_BYTE *)(Policy + 284) )
      {
        *v10 = 0;
        goto LABEL_95;
      }
    }
    TokenHandle = 0;
    memset(&ObjectAttributes, 0, 44);
    LogonSessionToken = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x200u, &TokenHandle);
    if ( LogonSessionToken >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      LogonSessionToken = ZwDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle);
    }
    if ( TokenHandle )
      ZwClose(TokenHandle);
    if ( LogonSessionToken >= 0 )
    {
      LODWORD(TokenHandle) = 0;
      TokenInformation = 0;
      IsTokenService = ZwQueryInformationToken(
                         NewTokenHandle,
                         TokenSandBoxInert,
                         &TokenInformation,
                         4u,
                         (PULONG)&TokenHandle);
      LogonSessionToken = IsTokenService;
      if ( IsTokenService < 0
        || TokenInformation
        || (IsTokenService = SrpIsTokenService(NewTokenHandle, &v56),
            LogonSessionToken = IsTokenService,
            IsTokenService < 0)
        || (LODWORD(TokenHandle) = 0,
            TokenInformation = 0,
            IsTokenService = ZwQueryInformationToken(
                               NewTokenHandle,
                               TokenIsRestricted,
                               &TokenInformation,
                               4u,
                               (PULONG)&TokenHandle),
            LogonSessionToken = IsTokenService,
            IsTokenService < 0) )
      {
        *v10 = IsTokenService;
        goto LABEL_95;
      }
      if ( TokenInformation )
      {
        LogonSessionToken = SeGetLogonSessionToken(NewTokenHandle, 0, &v69);
        if ( (int)(LogonSessionToken + 0x80000000) >= 0 && LogonSessionToken != -1073741700 )
        {
          *v10 = LogonSessionToken;
          goto LABEL_95;
        }
      }
      Object = 0;
      LogonSessionToken = ObReferenceObjectByHandle(v17, 0x100001u, (POBJECT_TYPE)IoFileObjectType, a5, &Object, 0);
      FileObject = Object;
      if ( LogonSessionToken < 0 )
        goto LABEL_95;
      LogonSessionToken = ObOpenObjectByPointer(
                            Object,
                            0x200u,
                            0,
                            0x80100000,
                            (POBJECT_TYPE)IoFileObjectType,
                            0,
                            &TargetHandle);
      if ( LogonSessionToken == -1073741790 )
      {
        LogonSessionToken = ZwDuplicateObject(
                              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                              v17,
                              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                              &TargetHandle,
                              0,
                              0x200u,
                              2u);
        if ( LogonSessionToken < 0 )
          goto LABEL_95;
        TokenHandle = 0;
        LogonSessionToken = ObReferenceObjectByHandle(
                              TargetHandle,
                              0x100001u,
                              (POBJECT_TYPE)IoFileObjectType,
                              0,
                              &TokenHandle,
                              0);
        if ( LogonSessionToken < 0 )
          goto LABEL_95;
        if ( TokenHandle != FileObject )
          LogonSessionToken = -1073741816;
        ObfDereferenceObject(TokenHandle);
      }
      if ( LogonSessionToken < 0 )
        goto LABEL_95;
      v22 = *(_QWORD *)(v7 + 88);
      UserData.Ptr = 0;
      *(_QWORD *)&UserData.Size = 0;
      v74 = 0;
      v23 = *(_DWORD *)(v22 + 24) & 0xC;
      v75 = 0;
      v79 = 0;
      v78 = a1;
      if ( v56 )
      {
        if ( v23 )
          goto LABEL_40;
      }
      else if ( v23 != 8 )
      {
        goto LABEL_40;
      }
      if ( !*(_BYTE *)(v7 + 284) )
      {
        *v10 = 0;
        goto LABEL_95;
      }
LABEL_40:
      v24 = (char *)NewTokenHandle;
      v25 = v57;
      if ( v69 )
        v24 = (char *)v69;
      if ( v57 && (unsigned __int8)SrpIsOnlySmartLockerEnabledForPolicyType(v7, 1) )
      {
LABEL_65:
        v35 = *(int *)(v7 + 176) >= 0 && *(_DWORD *)(*(_QWORD *)(v7 + 184) + 12LL);
        IsEnabled = SmartlockerSmartScreenRegistryIsEnabled();
        v37 = !(unsigned int)SmartlockerRegistryDisableOverrideIsSet() && (v35 || IsEnabled);
        if ( !dword_1400196E4 || !v37 )
          goto LABEL_88;
        v38 = *(_QWORD *)(v7 + 88);
        if ( v56 ? (*(_DWORD *)(v38 + 24) & 0xC) == 0 : (*(_DWORD *)(v38 + 24) & 0xC) == 8 )
          goto LABEL_88;
        v40 = 0;
        TokenHandle = 0;
        if ( ObReferenceObjectByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x1000u, 0, 0, &TokenHandle, 0) >= 0 )
          v40 = TokenHandle;
        v41 = SmartlockerVerifyProcess(
                (int)v24,
                (int)NewTokenHandle,
                v7,
                (int)v60,
                v63[0],
                0,
                (__int64)v40,
                v8,
                (PFILE_OBJECT)FileObject,
                TargetHandle,
                v56,
                1,
                IsEnabled);
        if ( v40 )
          ObfDereferenceObject(v40);
        if ( v41 >= 0 && *(_BYTE *)(v7 + 333) && (v8 & 0x20000) == 0 )
        {
          LogonSessionToken = v41;
        }
        else
        {
LABEL_88:
          if ( LogonSessionToken < 0 )
          {
LABEL_91:
            v10 = (int *)v64;
            *(_DWORD *)v64 = LogonSessionToken;
            if ( LogonSessionToken == -1073740956 )
              LogonSessionToken = 0;
            goto LABEL_95;
          }
        }
        if ( *(_BYTE *)(v7 + 284) )
        {
          v76 = *(unsigned int *)v63;
          v77 = v24;
          LogonSessionToken = SrpInvokePlugins(v7, 1, &UserData);
        }
        goto LABEL_91;
      }
      v26 = *(_DWORD *)(v7 + 280);
      LODWORD(ObjectAttributes.RootDirectory) = 0;
      ObjectAttributes.Length = v26 & 1;
      TokenHandle = 0;
      HIDWORD(ObjectAttributes.RootDirectory) = (v26 >> 1) & 1;
      LODWORD(ObjectAttributes.ObjectName) = (v26 >> 2) & 1;
      v27 = (v26 >> 3) & 1;
      v28 = (v26 >> 4) & 1;
      HIDWORD(ObjectAttributes.ObjectName) = v27;
      *(&ObjectAttributes.Length + 1) = v28;
      v29 = AipAllocateImageContext(v28, TargetHandle, 0, &TokenHandle);
      v30 = TokenHandle;
      LogonSessionToken = v29;
      if ( v29 < 0
        || (LogonSessionToken = AipCollectImageProperties(TokenHandle, &ObjectAttributes, 0, &v68), LogonSessionToken < 0) )
      {
        if ( !v30 )
          goto LABEL_94;
        AipFreeImageContext(v30);
        if ( LogonSessionToken < 0 )
          goto LABEL_94;
      }
      else
      {
        v31 = (void *)v30[2];
        if ( v31 )
        {
          ObfDereferenceObject(v31);
          v30[2] = 0;
        }
      }
      LogonSessionToken = AiSetTokenAttributes(v24, v68);
      if ( LogonSessionToken >= 0 )
      {
        if ( dword_1400196E4 && v25 )
        {
          v32 = *(_DWORD *)(*(_QWORD *)(v7 + 88) + 24LL);
          if ( !(v56 ? (v32 & 0xC) == 0 : (v32 & 0xC) == 8) )
          {
            v34 = SrppAccessCheck(v24, 0, (__int64)&v62);
            v8 = v62;
            LogonSessionToken = v34;
            if ( v34 < 0
              && (*(_DWORD *)(*(_QWORD *)(v7 + 88) + 24LL) & 0x20) != 0
              && (v62 & 0x20000) == 0
              && (unsigned __int8)SrpIsWindowsSigned(FileObject, TargetHandle) )
            {
              LogonSessionToken = 0;
              v8 = 0x10000;
            }
          }
        }
        goto LABEL_65;
      }
LABEL_94:
      v10 = (int *)v64;
    }
  }
LABEL_95:
  LOBYTE(v15) = 1;
  updated = AiUpdatePerfTime(&qword_140019630, PerformanceCounter, v15);
  v44 = &TraceLoggingMetadata;
  v45 = 0x200000000000LL;
  if ( updated > 0x7A120 || LogonSessionToken < 0 )
  {
    v46 = 0;
    if ( LOWORD(v60[0]) )
    {
      if ( P )
      {
        Pool2 = (wchar_t *)ExAllocatePool2(258, LOWORD(v60[0]) + 2LL, 1145663553, &TraceLoggingMetadata);
        if ( Pool2 )
        {
          v48 = ((unsigned __int64)LOWORD(v60[0]) + 2) >> 1;
          if ( v48 - 1 <= 0x7FFE )
          {
            if ( (v60[0] & 1) != 0
              || (v60[0] & 0x10000) != 0
              || LOWORD(v60[0]) > HIWORD(v60[0])
              || HIWORD(v60[0]) == 0xFFFF
              || (v49 = (wchar_t *)P) == 0 && v60[0] )
            {
              *Pool2 = 0;
            }
            else
            {
              v50 = (unsigned __int64)LOWORD(v60[0]) >> 1;
              v51 = Pool2;
              do
              {
                if ( !v50 )
                  break;
                --v50;
                *v51++ = *v49++;
                --v48;
              }
              while ( v48 );
              v52 = v51 - 1;
              if ( v48 )
                v52 = v51;
              *v52 = 0;
              if ( v48 )
              {
                v46 = LOWORD(v60[0]) >> 1;
                v53 = wcsrchr(Pool2, 0x5Cu);
                if ( v53 )
                  v46 -= ((char *)v53 - (char *)Pool2 + 2) >> 1;
              }
            }
          }
          ExFreePoolWithTag(Pool2, 0);
        }
      }
    }
    v42 = 0;
    v45 = 0x200000000000LL;
    if ( LogonSessionToken >= 0 )
    {
      if ( (unsigned int)dword_140019000 <= 4
        || (qword_140019010 & 0x200000000000LL) == 0
        || (qword_140019018 & 0x200000000000LL) != qword_140019018 )
      {
        goto LABEL_127;
      }
      v75 = &v78;
      v76 = 2;
      v64 = updated;
      *((_QWORD *)&v79 + 1) = 8;
      v81 = 8;
      v77 = (char *)P + 2 * (((unsigned __int64)LOWORD(v60[0]) >> 1) - v46);
      v78 = 2 * (unsigned int)v46;
      *(_QWORD *)&v79 = &v64;
      *(_QWORD *)v63 = *v10;
      v80 = v63;
      *(&ObjectAttributes.Length + 1) = 4;
      UserData.Ptr = (ULONGLONG)EventInformation;
      ObjectAttributes.Length = 184549376;
      ObjectAttributes.RootDirectory = (HANDLE)0x200000000000LL;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v54 = (__int16 *)byte_140015F8D;
      DWORD2(v74) = 77;
    }
    else
    {
      if ( (unsigned int)dword_140019000 <= 4
        || (qword_140019010 & 0x200000000000LL) == 0
        || (qword_140019018 & 0x200000000000LL) != qword_140019018 )
      {
        goto LABEL_127;
      }
      v75 = &v78;
      v76 = 2;
      v64 = updated;
      *((_QWORD *)&v79 + 1) = 8;
      v81 = 8;
      v77 = (char *)P + 2 * (((unsigned __int64)LOWORD(v60[0]) >> 1) - v46);
      v78 = 2 * (unsigned int)v46;
      *(_QWORD *)&v79 = &v64;
      *(_QWORD *)v63 = LogonSessionToken;
      v80 = v63;
      *(&ObjectAttributes.Length + 1) = 4;
      UserData.Ptr = (ULONGLONG)EventInformation;
      ObjectAttributes.Length = 184549376;
      ObjectAttributes.RootDirectory = (HANDLE)0x200000000000LL;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v54 = &word_140015FE6;
      DWORD2(v74) = 65;
    }
    *(_QWORD *)&v74 = v54;
    UserData.Reserved = 2;
    HIDWORD(v74) = 1;
    LODWORD(TokenHandle) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ObjectAttributes, 0, 0, 6u, &UserData);
    v45 = 0x200000000000LL;
LABEL_127:
    v44 = &TraceLoggingMetadata;
  }
  if ( *(_QWORD *)&qword_140019638 >= 0xC350u )
  {
    if ( (unsigned int)dword_140019000 > 4
      && (qword_140019010 & 0x200000000000LL) != 0
      && (qword_140019018 & 0x200000000000LL) == qword_140019018 )
    {
      *(_QWORD *)v63 = *(_QWORD *)&qword_140019638;
      v64 = (unsigned __int64)qword_140019630 / *(_QWORD *)&qword_140019638;
      ObjectAttributes.RootDirectory = (HANDLE)0x200000000000LL;
      v75 = (__int64 *)&v64;
      v76 = 8;
      v77 = v63;
      *(&ObjectAttributes.Length + 1) = 4;
      UserData.Ptr = (ULONGLONG)EventInformation;
      v78 = 8;
      ObjectAttributes.Length = 184549376;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      *(_QWORD *)&v74 = byte_140015F3B;
      UserData.Reserved = 2;
      *((_QWORD *)&v74 + 1) = 0x100000046LL;
      LODWORD(TokenHandle) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ObjectAttributes, 0, 0, 4u, &UserData);
    }
    AiResetPerfTimeCounter(&qword_140019630, v42, v45, v44);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v68 )
    AipFreeImageContext((PVOID)(v68 - 664));
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( TargetHandle )
    ZwClose(TargetHandle);
  if ( NewTokenHandle )
    ZwClose(NewTokenHandle);
  if ( v69 )
    ZwClose(v69);
  if ( *v71 == 4 && (LogonSessionToken < 0 || *v10 < 0) )
  {
    if ( v7 )
    {
      if ( !*(_BYTE *)(v7 + 285) )
      {
        *v10 = 0;
        LogonSessionToken = 0;
      }
      goto LABEL_153;
    }
  }
  else if ( v7 )
  {
LABEL_153:
    ReleasePolicyRef((PVOID)(v7 - 8));
  }
  return (unsigned int)LogonSessionToken;
}

```

## disassembly

```asm
0x140034550  mov     [rsp-8+arg_8], rbx
0x140034555  push    rbp
0x140034556  push    rsi
0x140034557  push    rdi
0x140034558  push    r12
0x14003455a  push    r13
0x14003455c  push    r14
0x14003455e  push    r15
0x140034560  lea     rbp, [rsp-90h]
0x140034568  sub     rsp, 190h
0x14003456f  mov     rax, cs:__security_cookie
0x140034576  xor     rax, rsp
0x140034579  mov     [rbp+0C0h+var_40], rax
0x140034580  mov     rax, [rbp+0C0h+arg_28]
0x140034587  mov     r14, rcx
0x14003458a  xor     ecx, ecx
0x14003458c  mov     [rbp+0C0h+var_118], r8
0x140034590  mov     [rbp+0C0h+var_100], rcx
0x140034594  mov     esi, ecx
0x140034596  mov     [rbp+0C0h+TargetHandle], rcx
0x14003459a  mov     r13d, ecx
0x14003459d  mov     [rbp+0C0h+var_F8], rcx
0x1400345a1  mov     r15d, r9d
0x1400345a4  mov     [rbp+0C0h+var_110], rcx
0x1400345a8  mov     r12, r8
0x1400345ab  mov     qword ptr [rbp+0C0h+var_138], rcx
0x1400345af  mov     edi, edx
0x1400345b1  mov     [rbp+0C0h+P], rcx
0x1400345b5  mov     [rbp+0C0h+var_F0], rcx
0x1400345b9  mov     [rsp+1C0h+var_150], cl
0x1400345bd  mov     dword ptr [rbp+0C0h+var_128], ecx
0x1400345c0  mov     [rbp+0C0h+var_E0], rax
0x1400345c4  call    cs:__imp_PsGetCurrentProcessId
0x1400345cb  nop     dword ptr [rax+rax+00h]
0x1400345d0  mov     dl, 1
0x1400345d2  xor     ecx, ecx
0x1400345d4  mov     qword ptr [rbp+0C0h+var_120], rax
0x1400345d8  call    AiQueryPerformanceCounter
0x1400345dd  mov     rdx, [rbp+0C0h+var_E0]
0x1400345e1  mov     rbx, rax
0x1400345e4  mov     [rdx], rsi
0x1400345e7  cmp     edi, 0Ah
0x1400345ea  jb      loc_140034CD8
0x1400345f0  movzx   ecx, word ptr [r14+8]
0x1400345f5  lea     eax, [rcx+0Ah]
0x1400345f8  cmp     edi, eax
0x1400345fa  jnz     loc_140034CD8
0x140034600  test    cl, 1
0x140034603  jnz     loc_140034CD8
0x140034609  test    cx, cx
0x14003460c  jz      loc_140034CD8
0x140034612  cmp     r15d, 4
0x140034616  jnz     loc_140034CD8
0x14003461c  mov     qword ptr [rdx], 4
0x140034623  movzx   ecx, word ptr [r14+8]
0x140034628  mov     r15, [r14]
0x14003462b  mov     word ptr [rbp+0C0h+var_138], cx
0x14003462f  mov     word ptr [rbp+0C0h+var_138+2], cx
0x140034633  call    AiAlloc
0x140034638  mov     [rbp+0C0h+P], rax
0x14003463c  test    rax, rax
0x14003463f  jnz     short loc_14003464B
0x140034641  mov     edi, 0C0000017h
0x140034646  jmp     loc_140034CE3
0x14003464b  movzx   r8d, word ptr [rbp+0C0h+var_138]; Size
0x140034650  lea     rdx, [r14+0Ah]; Src
0x140034654  mov     rcx, rax; void *
0x140034657  call    memmove
0x14003465c  xor     r9d, r9d; Context
0x14003465f  lea     rdx, AipInitRunOnce; InitFn
0x140034666  xor     r8d, r8d; Parameter
0x140034669  lea     rcx, AipInitRunOnceState; RunOnce
0x140034670  call    cs:__imp_RtlRunOnceExecuteOnce
0x140034677  nop     dword ptr [rax+rax+00h]
0x14003467c  mov     edi, eax
0x14003467e  test    eax, eax
0x140034680  js      loc_140034CE3
0x140034686  call    SrpGetPolicy
0x14003468b  mov     rsi, rax
0x14003468e  test    rax, rax
0x140034691  jnz     short loc_14003469D
0x140034693  mov     edi, 0C0000364h
0x140034698  jmp     loc_140034CE3
0x14003469d  cmp     [rax+50h], r13d
0x1400346a1  jl      loc_1400347BC
0x1400346a7  mov     rax, [rax+58h]
0x1400346ab  cmp     [rax+0Ch], r13d
0x1400346af  jz      loc_1400347BC
0x1400346b5  mov     [rsp+1C0h+var_14F], 1
0x1400346ba  xorps   xmm0, xmm0
0x1400346bd  mov     [rsp+1C0h+TokenHandle], r13
0x1400346c2  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x1400346c6  xor     eax, eax
0x1400346c8  lea     r9, [rsp+1C0h+TokenHandle]; TokenHandle
0x1400346cd  xor     edx, edx; DesiredAccess
0x1400346cf  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400346d6  mov     r8d, 200h; HandleAttributes
0x1400346dc  movups  xmmword ptr [rbp+0C0h+ObjectAttributes+1Ch], xmm0
0x1400346e0  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x1400346e4  call    cs:__imp_ZwOpenProcessTokenEx
0x1400346eb  nop     dword ptr [rax+rax+00h]
0x1400346f0  mov     edi, eax
0x1400346f2  test    eax, eax
0x1400346f4  js      short loc_140034743
0x1400346f6  mov     rcx, [rsp+1C0h+TokenHandle]; ExistingTokenHandle
0x1400346fb  lea     r8, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x1400346ff  xor     eax, eax
0x140034701  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x140034708  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], rax
0x14003470c  xorps   xmm0, xmm0
0x14003470f  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rax
0x140034713  xor     r9d, r9d; EffectiveOnly
0x140034716  lea     rax, [rbp+0C0h+var_110]
0x14003471a  mov     [rbp+0C0h+ObjectAttributes.Attributes], 200h
0x140034721  mov     [rsp+1C0h+NewTokenHandle], rax; NewTokenHandle
0x140034726  xor     edx, edx; DesiredAccess
0x140034728  mov     [rsp+1C0h+TokenType], 1; TokenType
0x140034730  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140034735  call    cs:__imp_ZwDuplicateToken
0x14003473c  nop     dword ptr [rax+rax+00h]
0x140034741  mov     edi, eax
0x140034743  mov     rcx, [rsp+1C0h+TokenHandle]; Handle
0x140034748  test    rcx, rcx
0x14003474b  jz      short loc_140034759
0x14003474d  call    cs:__imp_ZwClose
0x140034754  nop     dword ptr [rax+rax+00h]
0x140034759  test    edi, edi
0x14003475b  js      loc_140034CE3
0x140034761  mov     rcx, [rbp+0C0h+var_110]; TokenHandle
0x140034765  lea     r8, [rbp+0C0h+TokenInformation]; TokenInformation
0x140034769  xor     eax, eax
0x14003476b  mov     r9d, 4; TokenInformationLength
0x140034771  mov     dword ptr [rsp+1C0h+TokenHandle], eax
0x140034775  mov     edx, 0Fh; TokenInformationClass
0x14003477a  mov     [rbp+0C0h+TokenInformation], eax
0x14003477d  lea     rax, [rsp+1C0h+TokenHandle]
0x140034782  mov     qword ptr [rsp+1C0h+TokenType], rax; ReturnLength
0x140034787  call    cs:__imp_ZwQueryInformationToken
0x14003478e  nop     dword ptr [rax+rax+00h]
0x140034793  mov     edi, eax
0x140034795  test    eax, eax
0x140034797  js      short loc_1400347B3
0x140034799  cmp     [rbp+0C0h+TokenInformation], r13d
0x14003479d  jnz     short loc_1400347B3
0x14003479f  mov     rcx, [rbp+0C0h+var_110]
0x1400347a3  lea     rdx, [rsp+1C0h+var_150]
0x1400347a8  call    SrpIsTokenService
0x1400347ad  mov     edi, eax
0x1400347af  test    eax, eax
0x1400347b1  jns     short loc_1400347D7
0x1400347b3  mov     [r12], eax
0x1400347b7  jmp     loc_140034CE3
0x1400347bc  mov     [rsp+1C0h+var_14F], r13b
0x1400347c1  cmp     [rsi+11Ch], r13b
0x1400347c8  jnz     loc_1400346BA
0x1400347ce  mov     [r12], r13d
0x1400347d2  jmp     loc_140034CE3
0x1400347d7  mov     rcx, [rbp+0C0h+var_110]; TokenHandle
0x1400347db  lea     r8, [rbp+0C0h+TokenInformation]; TokenInformation
0x1400347df  xor     eax, eax
0x1400347e1  mov     r9d, 4; TokenInformationLength
0x1400347e7  mov     dword ptr [rsp+1C0h+TokenHandle], eax
0x1400347eb  mov     edx, 28h ; '('; TokenInformationClass
0x1400347f0  mov     [rbp+0C0h+TokenInformation], eax
0x1400347f3  lea     rax, [rsp+1C0h+TokenHandle]
0x1400347f8  mov     qword ptr [rsp+1C0h+TokenType], rax; ReturnLength
0x1400347fd  call    cs:__imp_ZwQueryInformationToken
0x140034804  nop     dword ptr [rax+rax+00h]
0x140034809  mov     edi, eax
0x14003480b  test    eax, eax
0x14003480d  js      short loc_1400347B3
0x14003480f  xor     al, al
0x140034811  mov     ecx, 1
0x140034816  cmp     [rbp+0C0h+TokenInformation], r13d
0x14003481a  movzx   eax, al
0x14003481d  cmovnz  eax, ecx
0x140034820  test    al, al
0x140034822  jz      short loc_140034858
0x140034824  mov     rcx, [rbp+0C0h+var_110]
0x140034828  lea     r8, [rbp+0C0h+var_F0]
0x14003482c  xor     edx, edx
0x14003482e  call    cs:__imp_SeGetLogonSessionToken
0x140034835  nop     dword ptr [rax+rax+00h]
0x14003483a  mov     ecx, 80000000h
0x14003483f  mov     edi, eax
0x140034841  add     eax, ecx
0x140034843  test    ecx, eax
0x140034845  jnz     short loc_140034858
0x140034847  cmp     edi, 0C000007Ch
0x14003484d  jz      short loc_140034858
0x14003484f  mov     [r12], edi
0x140034853  jmp     loc_140034CE3
0x140034858  mov     r8, cs:__imp_IoFileObjectType
0x14003485f  xor     eax, eax
0x140034861  movzx   r9d, [rbp+0C0h+arg_20]; AccessMode
0x140034869  mov     edx, 100001h; DesiredAccess
0x14003486e  mov     [rsp+1C0h+NewTokenHandle], rax; HandleInformation
0x140034873  mov     rcx, r15; Handle
0x140034876  mov     [rbp+0C0h+Object], rax
0x14003487a  lea     rax, [rbp+0C0h+Object]
0x14003487e  mov     r8, [r8]; ObjectType
0x140034881  mov     qword ptr [rsp+1C0h+TokenType], rax; Object
0x140034886  call    cs:__imp_ObReferenceObjectByHandle
0x14003488d  nop     dword ptr [rax+rax+00h]
0x140034892  mov     r10, [rbp+0C0h+Object]
0x140034896  mov     edi, eax
0x140034898  mov     [rbp+0C0h+var_100], r10
0x14003489c  test    eax, eax
0x14003489e  js      loc_140034CE3
0x1400348a4  lea     rax, [rbp+0C0h+TargetHandle]
0x1400348a8  mov     r9d, 80100000h; DesiredAccess
0x1400348ae  mov     [rsp+1C0h+Handle], rax; Handle
0x1400348b3  xor     r8d, r8d; PassedAccessState
0x1400348b6  mov     rax, cs:__imp_IoFileObjectType
0x1400348bd  mov     edx, 200h; HandleAttributes
0x1400348c2  mov     byte ptr [rsp+1C0h+NewTokenHandle], r13b; AccessMode
0x1400348c7  mov     rcx, [rax]
0x1400348ca  mov     qword ptr [rsp+1C0h+TokenType], rcx; ObjectType
0x1400348cf  mov     rcx, r10; Object
0x1400348d2  call    cs:__imp_ObOpenObjectByPointer
0x1400348d9  nop     dword ptr [rax+rax+00h]
0x1400348de  mov     edi, eax
0x1400348e0  cmp     eax, 0C0000022h
0x1400348e5  jnz     loc_140034989
0x1400348eb  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1400348f2  mov     dword ptr [rsp+1C0h+Handle], 2; Options
0x1400348fa  mov     rcx, r8; SourceProcessHandle
0x1400348fd  mov     dword ptr [rsp+1C0h+NewTokenHandle], 200h; HandleAttributes
0x140034905  lea     r9, [rbp+0C0h+TargetHandle]; TargetHandle
0x140034909  mov     [rsp+1C0h+TokenType], r13d; DesiredAccess
0x14003490e  mov     rdx, r15; SourceHandle
0x140034911  call    cs:__imp_ZwDuplicateObject
0x140034918  nop     dword ptr [rax+rax+00h]
0x14003491d  mov     edi, eax
0x14003491f  test    eax, eax
0x140034921  js      loc_140034CE3
0x140034927  mov     r8, cs:__imp_IoFileObjectType
0x14003492e  lea     rax, [rsp+1C0h+TokenHandle]
0x140034933  mov     rcx, [rbp+0C0h+TargetHandle]; Handle
0x140034937  xor     r15d, r15d
0x14003493a  mov     [rsp+1C0h+NewTokenHandle], r15; HandleInformation
0x14003493f  xor     r9d, r9d; AccessMode
0x140034942  mov     edx, 100001h; DesiredAccess
0x140034947  mov     [rsp+1C0h+TokenHandle], r15
0x14003494c  mov     r8, [r8]; ObjectType
0x14003494f  mov     qword ptr [rsp+1C0h+TokenType], rax; Object
0x140034954  call    cs:__imp_ObReferenceObjectByHandle
0x14003495b  nop     dword ptr [rax+rax+00h]
0x140034960  mov     edi, eax
0x140034962  test    eax, eax
0x140034964  js      loc_140034CE3
0x14003496a  mov     rcx, [rsp+1C0h+TokenHandle]; Object
0x14003496f  mov     eax, 0C0000008h
0x140034974  cmp     rcx, [rbp+0C0h+var_100]
0x140034978  cmovnz  edi, eax
0x14003497b  call    cs:__imp_ObfDereferenceObject
0x140034982  nop     dword ptr [rax+rax+00h]
0x140034987  jmp     short loc_14003498C
0x140034989  xor     r15d, r15d
0x14003498c  test    edi, edi
0x14003498e  js      loc_140034CE3
0x140034994  mov     rax, [rsi+58h]
0x140034998  xorps   xmm0, xmm0
0x14003499b  xorps   xmm1, xmm1
0x14003499e  mov     [rbp+0C0h+UserData.Ptr], r15
0x1400349a2  mov     qword ptr [rbp+0C0h+UserData.Size], r15
0x1400349a6  movdqa  [rbp+0C0h+var_90], xmm0
0x1400349ab  mov     ecx, [rax+18h]
0x1400349ae  and     ecx, 0Ch
0x1400349b1  mov     [rbp+0C0h+var_80], r15
0x1400349b5  movdqa  [rbp+0C0h+var_60], xmm1
0x1400349ba  mov     [rbp+0C0h+var_68], r14
0x1400349be  cmp     [rsp+1C0h+var_150], r13b
0x1400349c3  jz      loc_140034A91
0x1400349c9  test    ecx, ecx
0x1400349cb  jz      loc_140034A9A
0x1400349d1  mov     rax, [rbp+0C0h+var_F0]
0x1400349d5  mov     r12, [rbp+0C0h+var_110]
0x1400349d9  test    rax, rax
0x1400349dc  movzx   r15d, [rsp+1C0h+var_14F]
0x1400349e2  cmovnz  r12, rax
0x1400349e6  test    r15b, r15b
0x1400349e9  jz      short loc_140034A00
0x1400349eb  mov     edx, 1
0x1400349f0  mov     rcx, rsi
0x1400349f3  call    SrpIsOnlySmartLockerEnabledForPolicyType
0x1400349f8  test    al, al
0x1400349fa  jnz     loc_140034B63
0x140034a00  mov     ecx, [rsi+118h]
0x140034a06  lea     r9, [rsp+1C0h+TokenHandle]
0x140034a0b  mov     eax, ecx
0x140034a0d  xor     edx, edx
0x140034a0f  and     eax, 1
0x140034a12  mov     dword ptr [rbp+0C0h+ObjectAttributes.RootDirectory], edx
0x140034a15  mov     [rbp+0C0h+ObjectAttributes.Length], eax
0x140034a18  xor     r8d, r8d
0x140034a1b  mov     eax, ecx
0x140034a1d  mov     [rsp+1C0h+TokenHandle], rdx
0x140034a22  mov     rdx, [rbp+0C0h+TargetHandle]
0x140034a26  shr     eax, 1
  ... truncated ...
```
