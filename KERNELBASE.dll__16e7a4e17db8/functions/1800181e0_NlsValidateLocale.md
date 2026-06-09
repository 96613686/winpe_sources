# NlsValidateLocale

- ea: `0x1800181e0`
- end: `0x180019087`
- name: `NlsValidateLocale`
- size: `3751`
- prototype: ``
- caller_count: `25`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014ad0`
- `0x180015e20`
- `0x180038db0`
- `0x18003bd40`
- `0x18003c2e0`
- `0x18003fa10`
- `0x1800420a0`
- `0x180088c90`
- `0x1800a32b0`
- `0x1800a365c`
- `0x1800af830`
- `0x1800bd470`
- `0x1800e72d0`
- `0x1800e7e20`
- `0x1800ef820`
- `0x1800f3c60`
- `0x1800fcd80`
- `0x180108880`
- `0x18010c960`
- `0x18010ca40`
- `0x1801234d0`
- `0x180139790`
- `0x180139800`
- `0x1801398c0`
- `0x18013c1f0`

## callees

- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x1800123e0`
- `0x180012f10`
- `0x180018040`
- `0x1800181e0`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x180071550`
- `0x18007217c`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018e92`
- `ntdll!RtlInitUnicodeString` at `0x180018e92`
- `ntdll!NtOpenKey` at `0x180018ed9`
- `ntdll!NtOpenKey` at `0x180018ed9`
- `ntdll!NtCreateKey` at `0x180018f12`
- `ntdll!NtCreateKey` at `0x180018f12`
- `ntdll!RtlLcidToLocaleName` at `0x180018d6f`
- `ntdll!RtlLcidToLocaleName` at `0x180018d6f`
- `ntdll!RtlOpenCurrentUser` at `0x180018a58`
- `ntdll!RtlOpenCurrentUser` at `0x180018a58`
- `ntdll!CsrClientCallServer` at `0x1800188f1`
- `ntdll!CsrClientCallServer` at `0x1800188f1`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800188d1`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800188d1`
- `ntdll!CsrFreeCaptureBuffer` at `0x180018916`
- `ntdll!CsrFreeCaptureBuffer` at `0x180018916`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180018602`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180018602`
- `ntdll!NtClose` at `0x180018675`
- `ntdll!NtClose` at `0x180018af7`
- `ntdll!NtClose` at `0x180018f24`
- `ntdll!NtClose` at `0x180018f5f`
- `ntdll!NtClose` at `0x180018675`
- `ntdll!NtClose` at `0x180018af7`
- `ntdll!NtClose` at `0x180018f24`
- `ntdll!NtClose` at `0x180018f5f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018272`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800183a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800185be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800186ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001887c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018272`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800183a5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800185be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800186ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001887c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018358`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001848c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800187d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018807`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800188a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018fda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019062`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018358`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001848c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800187d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018807`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800188a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018fda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019062`
- `ntdll!RtlAllocateHeap` at `0x180018de0`
- `ntdll!RtlAllocateHeap` at `0x180018e3b`
- `ntdll!RtlAllocateHeap` at `0x180018de0`
- `ntdll!RtlAllocateHeap` at `0x180018e3b`

## pseudocode

```c
unsigned int *__fastcall NlsValidateLocale(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // r15d
  unsigned int *result; // rax
  DWORD v7; // ebx
  __int64 j; // rdx
  unsigned int *v9; // rax
  __int64 v10; // r8
  DWORD v11; // ebx
  const WCHAR *v12; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  DWORD v14; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v17; // r8
  DWORD v18; // edi
  const WCHAR *v19; // rcx
  __int64 NamedLocaleHashNode; // rax
  unsigned __int64 v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // r14
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v27; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v29; // rbx
  NTSTATUS v30; // edi
  HANDLE v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // rax
  DWORD v34; // ebx
  __int64 k; // rdx
  unsigned int *v36; // rax
  __int64 v37; // r8
  DWORD v38; // ebx
  const WCHAR *v39; // rcx
  __int64 LocaleHashNode; // rax
  HANDLE *NlsCache; // rbx
  __int64 v42; // rdx
  __int64 v43; // rdx
  unsigned int v44; // ecx
  int GlobalizationUserModelType; // eax
  int v46; // eax
  __int64 v47; // rcx
  WCHAR *v48; // rax
  __int64 v49; // r9
  const WCHAR *v50; // rdx
  WCHAR *v51; // r8
  __int64 v52; // rcx
  WCHAR *v53; // rcx
  __int64 v54; // rdx
  int v55; // ecx
  int v56; // r12d
  int v57; // eax
  HANDLE *v58; // rbx
  HANDLE *Heap; // rax
  HANDLE *v60; // rax
  NTSTATUS v61; // ebx
  HANDLE v62; // rcx
  void *v63; // rbx
  unsigned int *v64; // rax
  __int64 v65; // r8
  unsigned int v66; // edi
  const WCHAR *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdx
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v73; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v78; // [rsp+F8h] [rbp-8h]

  v3 = *a1;
  v4 = a2;
  if ( *a1 == 127 )
  {
    result = (unsigned int *)gpInvLocHashN;
    goto LABEL_44;
  }
  if ( v3 > 0xC00 )
  {
    if ( v3 == 4096 )
    {
      result = (unsigned int *)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_53;
    }
    else if ( v3 != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(v3, KeyHandle, 0, 0) >= 0 )
    {
      result = (unsigned int *)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( result )
        goto LABEL_53;
    }
LABEL_26:
    result = (unsigned int *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( v3 != *result )
        goto LABEL_45;
      goto LABEL_44;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v14 = gSystemLocale;
    for ( i = *((_QWORD *)P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); i; i = *(_QWORD *)(i + 88) )
    {
      if ( *(_DWORD *)i == gSystemLocale )
        break;
    }
    gpSysLocHashN = i;
    if ( i )
      goto LABEL_42;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_103;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v14 != 127 )
      {
        v18 = HIWORD(v14);
        if ( (v18 & 0xF) == 0 )
        {
          v19 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          NamedLocaleHashNode = MakeNamedLocaleHashNode(v19, 0);
          goto LABEL_39;
        }
        v42 = WindowsLocaleData[54];
        v19 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v42 )
          v19 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v42 + 2LL * (v18 & 0xF)) - 2)
                              + 2);
        if ( v19 && *v19 )
          goto LABEL_38;
LABEL_103:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v14, v17, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_103;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        NamedLocaleHashNode = FindLocaleHashNode(v14);
      }
      else
      {
        NamedLocaleHashNode = 0;
      }
    }
LABEL_39:
    gpSysLocHashN = NamedLocaleHashNode;
    if ( !NamedLocaleHashNode )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    result = (unsigned int *)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( v3 != 3072 && v3 && v3 != 1024 )
  {
    if ( v3 == 2048 )
    {
      result = (unsigned int *)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_53;
      if ( BasepIsSecureProcess )
        goto LABEL_44;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_23;
      v7 = gSystemLocale;
      for ( j = *((_QWORD *)P
                + (((unsigned __int8)gSystemLocale
                  ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                 & 0x7F)); j; j = *(_QWORD *)(j + 88) )
      {
        if ( *(_DWORD *)j == gSystemLocale )
          break;
      }
      gpSysLocHashN = j;
      if ( j )
        goto LABEL_23;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_126;
      v9 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v9 )
      {
        if ( (_WORD)v7 != 127 )
        {
          v11 = HIWORD(v7);
          if ( (v11 & 0xF) == 0 )
          {
            v12 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v9);
LABEL_19:
            LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v12, 0);
            goto LABEL_20;
          }
          v43 = v9[54];
          v12 = (const WCHAR *)qword_18039EC90;
          if ( (_DWORD)v43 )
            v12 = (const WCHAR *)(qword_18039EC90
                                + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v43 + 2LL * (v11 & 0xF)) - 2)
                                + 2);
          if ( v12 && *v12 )
            goto LABEL_19;
LABEL_126:
          gpSysLocHashN = 0;
          goto LABEL_21;
        }
        LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v9, v7, v10, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_126;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          LocHashNodeFromSystemLocale = FindLocaleHashNode(v7);
        }
        else
        {
          LocHashNodeFromSystemLocale = 0;
        }
      }
LABEL_20:
      gpSysLocHashN = LocHashNodeFromSystemLocale;
      if ( LocHashNodeFromSystemLocale )
      {
LABEL_23:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        result = (unsigned int *)gpSysLocHashN;
        goto LABEL_44;
      }
LABEL_21:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  if ( !(_DWORD)IsImpersonating )
  {
    IsInteractiveUserProcess = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, a2, a3);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_97;
    }
    if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803A4276 = 1;
    if ( !word_1803A4276 )
      goto LABEL_97;
    v27 = word_1803A4274;
    if ( word_1803A4274 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v27 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        if ( !word_1803A4276 )
          goto LABEL_96;
        v27 = word_1803A4274;
      }
    }
    word_1803A4276 = 2;
    if ( v27 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v29 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v78 = 1660;
        v30 = CsrClientCallServer(ApiMessage, v29, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v30 >= 0 )
          memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v29);
      }
      else
      {
        v30 = -1073741801;
      }
      if ( word_1803A4274 == 1 && v30 >= 0 )
      {
LABEL_72:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
        }
        else
        {
          v32 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
          if ( !v32 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803A3BF0 )
          {
LABEL_95:
            _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
            if ( word_1803A4274 != 3 )
LABEL_96:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_97:
            NlsCache = &gNlsProcessLocalCache;
LABEL_98:
            result = (unsigned int *)NlsCache[2];
            goto LABEL_44;
          }
        }
        v33 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_94:
          qword_1803A3BF0 = v33;
          goto LABEL_95;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_93;
        v34 = gSystemLocale;
        for ( k = *((_QWORD *)P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); k; k = *(_QWORD *)(k + 88) )
        {
          if ( *(_DWORD *)k == gSystemLocale )
            break;
        }
        gpSysLocHashN = k;
        if ( k )
          goto LABEL_93;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_154;
        v36 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v36 )
        {
          if ( (_WORD)v34 != 127 )
          {
            v38 = HIWORD(v34);
            if ( (v38 & 0xF) == 0 )
            {
              v39 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v36);
LABEL_89:
              LocaleHashNode = MakeNamedLocaleHashNode(v39, 0);
              goto LABEL_90;
            }
            v54 = v36[54];
            v39 = (const WCHAR *)qword_18039EC90;
            if ( (_DWORD)v54 )
              v39 = (const WCHAR *)(qword_18039EC90
                                  + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v54 + 2LL * (v38 & 0xF)) - 2)
                                  + 2);
            if ( v39 && *v39 )
              goto LABEL_89;
LABEL_154:
            gpSysLocHashN = 0;
LABEL_91:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_93;
          }
          LocaleHashNode = MakeLocHashNodeFromSystemLocale(v36, v34, v37, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_154;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocaleHashNode = FindLocaleHashNode(v34);
          }
          else
          {
            LocaleHashNode = 0;
          }
        }
LABEL_90:
        gpSysLocHashN = LocaleHashNode;
        if ( !LocaleHashNode )
          goto LABEL_91;
LABEL_93:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v33 = gpSysLocHashN;
        goto LABEL_94;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_69:
      v31 = Handle;
      NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
      if ( word_1803A4274 == 3 && v31 )
        NtClose(v31);
      goto LABEL_72;
    }
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, a2, a3);
    if ( GlobalizationUserModelType == 1 )
    {
      v46 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v57 = GlobalizationUserModelType - 2;
      if ( v57 )
      {
        if ( v57 != 1 )
        {
LABEL_149:
          SetLastError_0(0x3F1u);
          goto LABEL_69;
        }
        v73 = 0;
        v46 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v73);
      }
      else
      {
        v46 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v46 >= 0 )
    {
      ApiMessage[0] = 0;
      v47 = 512;
      v48 = ApiMessage;
      do
      {
        if ( !*v48 )
          break;
        ++v48;
        --v47;
      }
      while ( v47 );
      if ( !v47 )
        goto LABEL_147;
      v49 = v47;
      v50 = L"Control Panel\\International";
      v51 = &ApiMessage[512 - v47];
      v52 = 2147483646;
      do
      {
        if ( !v52 )
          break;
        if ( !*v50 )
          break;
        *v51++ = *v50++;
        --v52;
        --v49;
      }
      while ( v49 );
      v53 = v51 - 1;
      if ( v49 )
        v53 = v51;
      *v53 = 0;
      if ( v49 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v61 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v61 < 0 )
          v61 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v61 >= 0 )
        {
          v62 = Handle;
        }
        else
        {
          v62 = 0;
          Handle = 0;
        }
        if ( v61 >= 0 )
        {
          v63 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v62,
                          0);
          if ( v63 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v63;
          }
          goto LABEL_69;
        }
      }
      else
      {
LABEL_147:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_149;
  }
  NlsCache = 0;
  v55 = IsImpersonating - 1;
  if ( v55 )
  {
    if ( v55 != 1 )
      goto LABEL_98;
    if ( BasepIsSecureProcess )
      goto LABEL_97;
    v56 = 0;
    NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
    if ( !NlsCache )
    {
      Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
      NlsCache = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        Heap[2] = 0;
        v56 = 1;
        *((_WORD *)Heap + 842) = 3;
        *((_WORD *)Heap + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v56 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_98;
    *((_WORD *)NlsCache + 843) = 1;
    UpdateNlsInfoCache(NlsCache, 0);
    result = (unsigned int *)NlsCache[2];
  }
  else
  {
    if ( BasepIsSecureProcess )
    {
      v58 = &gNlsProcessLocalCache;
    }
    else
    {
      v58 = (HANDLE *)NtCurrentTeb()->NlsCache;
      if ( !v58 )
      {
        v60 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
        v58 = v60;
        if ( v60 )
        {
          *v60 = 0;
          v60[1] = 0;
          v60[2] = 0;
          *((_WORD *)v60 + 842) = 3;
          *((_WORD *)v60 + 843) = 1;
        }
        else
        {
          v58 = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = v58;
      }
      if ( v58 != &gNlsProcessLocalCache )
      {
        *((_WORD *)v58 + 843) = 1;
        UpdateNlsInfoCache(v58, 0);
      }
    }
    NtCurrentTeb()->IsImpersonating = 2;
    result = (unsigned int *)v58[2];
  }
LABEL_44:
  if ( result )
    goto LABEL_53;
LABEL_45:
  v21 = *a1;
  v22 = ((unsigned __int8)v21 ^ (unsigned __int8)((v21 ^ (v21 >> 7)) >> 7)) & 0x7F;
  v23 = *((_QWORD *)P + v22);
  v24 = 8 * v22;
  if ( !v23 )
  {
LABEL_105:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v23 = *(_QWORD *)((char *)P + v24);
    if ( v23 )
    {
      while ( *(_DWORD *)v23 != (_DWORD)v21 )
      {
        v23 = *(_QWORD *)(v23 + 88);
        if ( !v23 )
          goto LABEL_213;
      }
      goto LABEL_107;
    }
LABEL_213:
    if ( (v21 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v64 = (unsigned int *)GetWindowsLocaleData((unsigned int)v21);
      if ( v64 )
      {
        if ( (_WORD)v21 == 127 )
        {
          v23 = MakeLocHashNodeFromSystemLocale(v64, (unsigned int)v21, v65, 0);
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_47;
        }
        v66 = WORD1(v21);
        if ( (v66 & 0xF) == 0 )
        {
          v67 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v64);
LABEL_219:
          v68 = MakeNamedLocaleHashNode(v67, 0);
LABEL_220:
          v23 = v68;
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_47;
        }
        v69 = v64[54];
        v67 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v69 )
          v67 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v69 + 2LL * (v66 & 0xF)) - 2)
                              + 2);
        if ( v67 && *v67 )
          goto LABEL_219;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        v68 = FindLocaleHashNode((unsigned int)v21);
        goto LABEL_220;
      }
    }
    v23 = 0;
LABEL_107:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    goto LABEL_47;
  }
  while ( *(_DWORD *)v23 != (_DWORD)v21 )
  {
    v23 = *(_QWORD *)(v23 + 88);
    if ( !v23 )
      goto LABEL_105;
  }
LABEL_47:
  if ( !v23 )
  {
    result = 0;
LABEL_128:
    v44 = *a1;
    if ( *a1 != 4096 && ((v44 & 0x3FF) != 0 || v44 - 0x2000 > 0x2C00) )
      return result;
    result = (unsigned int *)GetCurrentNlsCache()[2];
LABEL_53:
    *a1 = *result;
    return result;
  }
  if ( v4 )
    return (unsigned int *)v23;
  result = *(unsigned int **)(v23 + 104);
  if ( !result )
    goto LABEL_128;
  return result;
}

```

## disassembly

```asm
0x1800181e0  mov     [rsp-8+arg_10], rbx
0x1800181e5  push    rbp
0x1800181e6  push    rsi
0x1800181e7  push    rdi
0x1800181e8  push    r14
0x1800181ea  push    r15
0x1800181ec  lea     rbp, [rsp-3C0h]
0x1800181f4  sub     rsp, 4C0h
0x1800181fb  mov     rax, cs:__security_cookie
0x180018202  xor     rax, rsp
0x180018205  mov     [rbp+3E0h+var_30], rax
0x18001820c  mov     ebx, [rcx]
0x18001820e  mov     r15d, edx
0x180018211  mov     rsi, rcx
0x180018214  cmp     ebx, 7Fh
0x180018217  jz      loc_180018524
0x18001821d  cmp     ebx, 0C00h
0x180018223  ja      loc_18001836A
0x180018229  jz      loc_18001853F
0x18001822f  test    ebx, ebx
0x180018231  jz      loc_18001853F
0x180018237  cmp     ebx, 400h
0x18001823d  jz      loc_18001853F
0x180018243  cmp     ebx, 800h
0x180018249  jnz     loc_180018382
0x18001824f  mov     rax, cs:gpSysLocHashN
0x180018256  test    rax, rax
0x180018259  jnz     loc_180018539
0x18001825f  cmp     cs:BasepIsSecureProcess, al
0x180018265  jnz     loc_18001849D
0x18001826b  lea     rcx, gTblPtrsLock
0x180018272  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018278  cmp     cs:gpSysLocHashN, 0
0x180018280  jnz     loc_180018351
0x180018286  mov     ebx, cs:gSystemLocale
0x18001828c  mov     rax, cs:P
0x180018293  mov     ecx, ebx
0x180018295  shr     rcx, 7
0x180018299  xor     rcx, rbx
0x18001829c  shr     rcx, 7
0x1800182a0  xor     rcx, rbx
0x1800182a3  and     ecx, 7Fh
0x1800182a6  mov     rdx, [rax+rcx*8]
0x1800182aa  test    rdx, rdx
0x1800182ad  jz      short loc_1800182B7
0x1800182af  cmp     [rdx], ebx
0x1800182b1  jnz     loc_180018BEC
0x1800182b7  mov     cs:gpSysLocHashN, rdx
0x1800182be  test    rdx, rdx
0x1800182c1  jnz     loc_180018351
0x1800182c7  test    ebx, 0FFF00000h
0x1800182cd  jnz     loc_1800189BB
0x1800182d3  cmp     cs:BasepIsSecureProcess, dl
0x1800182d9  jnz     loc_1800189BB
0x1800182df  mov     ecx, ebx
0x1800182e1  call    GetWindowsLocaleData
0x1800182e6  test    rax, rax
0x1800182e9  jz      loc_180018BFE
0x1800182ef  cmp     bx, 7Fh
0x1800182f3  jz      loc_180018C36
0x1800182f9  shr     ebx, 10h
0x1800182fc  test    bl, 0Fh
0x1800182ff  jnz     loc_180018988
0x180018305  mov     ecx, [rax]
0x180018307  mov     rax, cs:qword_18039EC90
0x18001830e  add     rax, 2
0x180018312  lea     rcx, [rax+rcx*2]
0x180018316  xor     edx, edx
0x180018318  call    MakeNamedLocaleHashNode
0x18001831d  mov     cs:gpSysLocHashN, rax
0x180018324  test    rax, rax
0x180018327  jnz     short loc_180018351
0x180018329  xor     edx, edx
0x18001832b  lea     rcx, aEnUs; "en-US"
0x180018332  call    MakeNamedLocaleHashNode
0x180018337  mov     cs:gpSysLocHashN, rax
0x18001833e  test    rax, rax
0x180018341  jnz     short loc_180018351
0x180018343  mov     rax, cs:gpInvLocHashN
0x18001834a  mov     cs:gpSysLocHashN, rax
0x180018351  lea     rcx, gTblPtrsLock
0x180018358  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001835e  mov     rax, cs:gpSysLocHashN
0x180018365  jmp     loc_18001849D
0x18001836a  cmp     ebx, 1000h
0x180018370  jz      loc_180018D37
0x180018376  cmp     ebx, 1400h
0x18001837c  jz      loc_180018D47
0x180018382  mov     rax, cs:gpSysLocHashN
0x180018389  test    rax, rax
0x18001838c  jnz     loc_180018499
0x180018392  cmp     cs:BasepIsSecureProcess, al
0x180018398  jnz     loc_180018499
0x18001839e  lea     rcx, gTblPtrsLock
0x1800183a5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800183ab  cmp     cs:gpSysLocHashN, 0
0x1800183b3  jnz     loc_180018485
0x1800183b9  mov     edi, cs:gSystemLocale
0x1800183bf  mov     rax, cs:P
0x1800183c6  mov     ecx, edi
0x1800183c8  shr     rcx, 7
0x1800183cc  xor     rcx, rdi
0x1800183cf  shr     rcx, 7
0x1800183d3  xor     rcx, rdi
0x1800183d6  and     ecx, 7Fh
0x1800183d9  mov     rdx, [rax+rcx*8]
0x1800183dd  test    rdx, rdx
0x1800183e0  jz      short loc_1800183EA
0x1800183e2  cmp     [rdx], edi
0x1800183e4  jnz     loc_1800188B0
0x1800183ea  mov     cs:gpSysLocHashN, rdx
0x1800183f1  test    rdx, rdx
0x1800183f4  jnz     loc_180018485
0x1800183fa  test    edi, 0FFF00000h
0x180018400  jnz     loc_180018858
0x180018406  cmp     cs:BasepIsSecureProcess, dl
0x18001840c  jnz     loc_180018858
0x180018412  mov     ecx, edi
0x180018414  call    GetWindowsLocaleData
0x180018419  test    rax, rax
0x18001841c  jz      loc_18001895A
0x180018422  cmp     di, 7Fh
0x180018426  jz      loc_180018A00
0x18001842c  shr     edi, 10h
0x18001842f  test    dil, 0Fh
0x180018433  jnz     loc_180018825
0x180018439  mov     ecx, [rax]
0x18001843b  mov     rax, cs:qword_18039EC90
0x180018442  add     rax, 2
0x180018446  lea     rcx, [rax+rcx*2]
0x18001844a  xor     edx, edx
0x18001844c  call    MakeNamedLocaleHashNode
0x180018451  mov     cs:gpSysLocHashN, rax
0x180018458  test    rax, rax
0x18001845b  jnz     short loc_180018485
0x18001845d  xor     edx, edx
0x18001845f  lea     rcx, aEnUs; "en-US"
0x180018466  call    MakeNamedLocaleHashNode
0x18001846b  mov     cs:gpSysLocHashN, rax
0x180018472  test    rax, rax
0x180018475  jnz     short loc_180018485
0x180018477  mov     rax, cs:gpInvLocHashN
0x18001847e  mov     cs:gpSysLocHashN, rax
0x180018485  lea     rcx, gTblPtrsLock
0x18001848c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018492  mov     rax, cs:gpSysLocHashN
0x180018499  cmp     ebx, [rax]
0x18001849b  jnz     short loc_1800184A6
0x18001849d  test    rax, rax
0x1800184a0  jnz     loc_180018539
0x1800184a6  mov     edi, [rsi]
0x1800184a8  mov     rax, cs:P
0x1800184af  mov     ecx, edi
0x1800184b1  shr     rcx, 7
0x1800184b5  xor     rcx, rdi
0x1800184b8  shr     rcx, 7
0x1800184bc  xor     rcx, rdi
0x1800184bf  and     ecx, 7Fh
0x1800184c2  mov     rbx, [rax+rcx*8]
0x1800184c6  lea     r14, ds:0[rcx*8]
0x1800184ce  test    rbx, rbx
0x1800184d1  jz      loc_180018875
0x1800184d7  cmp     [rbx], edi
0x1800184d9  jnz     loc_180018868
0x1800184df  test    rbx, rbx
0x1800184e2  jz      loc_1800189CB
0x1800184e8  test    r15d, r15d
0x1800184eb  jnz     loc_180018D97
0x1800184f1  mov     rax, [rbx+68h]
0x1800184f5  test    rax, rax
0x1800184f8  jz      loc_1800189CD
0x1800184fe  mov     rcx, [rbp+3E0h+var_30]
0x180018505  xor     rcx, rsp; StackCookie
0x180018508  call    __security_check_cookie
0x18001850d  mov     rbx, [rsp+4E0h+arg_10]
0x180018515  add     rsp, 4C0h
0x18001851c  pop     r15
0x18001851e  pop     r14
0x180018520  pop     rdi
0x180018521  pop     rsi
0x180018522  pop     rbp
0x180018523  retn
0x180018524  mov     rax, cs:gpInvLocHashN
0x18001852b  jmp     loc_18001849D
0x180018530  call    GetCurrentNlsCache
0x180018535  mov     rax, [rax+10h]
0x180018539  mov     ecx, [rax]
0x18001853b  mov     [rsi], ecx
0x18001853d  jmp     short loc_1800184FE
0x18001853f  mov     rax, gs:30h
0x180018548  mov     [rsp+4E0h+arg_8], r12
0x180018550  mov     ecx, [rax+179Ch]
0x180018556  test    ecx, ecx
0x180018558  jnz     loc_180018B58
0x18001855e  mov     eax, cs:gInteractiveLogonUserProcess
0x180018564  cmp     eax, 0FFFFFFFFh
0x180018567  jz      loc_180018C82
0x18001856d  test    eax, eax
0x18001856f  jz      loc_180018B4E
0x180018575  mov     rax, cs:gpServerNlsUserInfo
0x18001857c  mov     r14d, 1
0x180018582  mov     ecx, [rax+678h]
0x180018588  mov     eax, cs:dword_1803A4270
0x18001858e  cmp     eax, ecx
0x180018590  jz      short loc_18001859A
0x180018592  mov     cs:word_1803A4276, r14w
0x18001859a  movzx   eax, cs:word_1803A4276
0x1800185a1  test    ax, ax
0x1800185a4  jz      loc_18001880D
0x1800185aa  movzx   eax, cs:word_1803A4274
0x1800185b1  cmp     ax, 3
0x1800185b5  jz      short loc_1800185D5
0x1800185b7  lea     rcx, gNlsProcessCacheLock
0x1800185be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800185c4  movzx   eax, cs:word_1803A4274
0x1800185cb  cmp     ax, 3
0x1800185cf  jnz     loc_18001892E
0x1800185d5  mov     r12d, 2
0x1800185db  mov     cs:word_1803A4276, r12w
0x1800185e3  cmp     ax, r14w
0x1800185e7  jnz     short loc_180018627
0x1800185e9  xor     edx, edx; Val
0x1800185eb  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x1800185ef  mov     r8d, 3B8h; Size
0x1800185f5  call    memset_0
0x1800185fa  mov     edx, 67Ch; BufferSize
0x1800185ff  mov     ecx, r14d; ArgumentCount
0x180018602  call    cs:__imp_CsrAllocateCaptureBuffer
0x180018608  mov     rbx, rax
0x18001860b  test    rax, rax
0x18001860e  jnz     loc_1800188C2
0x180018614  mov     edi, 0C0000017h
0x180018619  cmp     cs:word_1803A4274, r14w
0x180018621  jz      loc_180018921
0x180018627  mov     rax, cs:gNlsProcessLocalCache
0x18001862e  mov     [rsp+4E0h+Handle], 0
0x180018637  test    rax, rax
0x18001863a  jz      loc_180018A12
0x180018640  mov     rax, cs:gNlsProcessLocalCache
0x180018647  mov     [rsp+4E0h+Handle], rax
0x18001864c  mov     rbx, [rsp+4E0h+Handle]
0x180018651  lea     rcx, word_1803A3BF8
0x180018658  mov     rdx, rbx
0x18001865b  mov     r8d, r14d
0x18001865e  call    NlsUpdateCacheInfo
0x180018663  cmp     cs:word_1803A4274, 3
0x18001866b  jnz     short loc_18001867B
0x18001866d  test    rbx, rbx
0x180018670  jz      short loc_18001867B
0x180018672  mov     rcx, rbx; Handle
0x180018675  call    cs:__imp_NtClose
0x18001867b  mov     eax, 0FFFFh
0x180018680  cmp     cs:word_1803A3BF8, ax
0x180018687  jz      loc_18001894A
0x18001868d  mov     rbx, cs:gpOneCustomHashNode
0x180018694  lea     rcx, word_1803A3BFA
0x18001869b  xor     edx, edx
0x18001869d  call    GetNamedLocaleHashNode
0x1800186a2  xchg    rax, cs:qword_1803A3BF0
0x1800186a9  test    rbx, rbx
0x1800186ac  jnz     short loc_1800186BE
0x1800186ae  cmp     cs:gpOneCustomHashNode, rbx
0x1800186b5  jz      short loc_1800186BE
0x1800186b7  mov     cs:gpOneCustomHashNode, rbx
0x1800186be  cmp     cs:qword_1803A3BF0, 0
0x1800186c6  jnz     loc_1800187E8
0x1800186cc  mov     rax, cs:gpSysLocHashN
0x1800186d3  test    rax, rax
0x1800186d6  jnz     loc_1800187E1
0x1800186dc  cmp     cs:BasepIsSecureProcess, al
0x1800186e2  jnz     loc_1800187E1
0x1800186e8  lea     rcx, gTblPtrsLock
0x1800186ef  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800186f5  cmp     cs:gpSysLocHashN, 0
0x1800186fd  jnz     loc_1800187CD
0x180018703  mov     ebx, cs:gSystemLocale
0x180018709  mov     rax, cs:P
0x180018710  mov     ecx, ebx
0x180018712  shr     rcx, 7
0x180018716  xor     rcx, rbx
0x180018719  shr     rcx, 7
0x18001871d  xor     rcx, rbx
0x180018720  and     ecx, 7Fh
0x180018723  mov     rdx, [rax+rcx*8]
0x180018727  test    rdx, rdx
0x18001872a  jz      short loc_180018734
0x18001872c  cmp     [rdx], ebx
0x18001872e  jnz     loc_180018C24
0x180018734  mov     cs:gpSysLocHashN, rdx
0x18001873b  test    rdx, rdx
0x18001873e  jnz     loc_1800187CD
0x180018744  test    ebx, 0FFF00000h
0x18001874a  jnz     loc_180018B3E
0x180018750  cmp     cs:BasepIsSecureProcess, dl
0x180018756  jnz     loc_180018B3E
0x18001875c  mov     ecx, ebx
0x18001875e  call    GetWindowsLocaleData
0x180018763  test    rax, rax
0x180018766  jz      loc_180018C48
0x18001876c  cmp     bx, 7Fh
  ... truncated ...
```
