# CompareStringW

- ea: `0x18001a230`
- end: `0x18001b1c3`
- name: `CompareStringW`
- size: `3987`
- prototype: `int __stdcall(LCID Locale, DWORD dwCmpFlags, PCNZWCH lpString1, int cchCount1, PCNZWCH lpString2, int cchCount2)`
- caller_count: `6`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800299b0`
- `0x1800b1fd0`
- `0x1800db4c8`
- `0x1800e6160`
- `0x1801005f0`
- `0x1801042bc`

## callees

- `0x18000d4a0`
- `0x18000d7e0`
- `0x18000dd50`
- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x1800123e0`
- `0x180012f10`
- `0x180018040`
- `0x18001a1b8`
- `0x18001a230`
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
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001afcf`
- `ntdll!RtlInitUnicodeString` at `0x18001afcf`
- `ntdll!NtOpenKey` at `0x18001b013`
- `ntdll!NtOpenKey` at `0x18001b013`
- `ntdll!NtCreateKey` at `0x18001b04b`
- `ntdll!NtCreateKey` at `0x18001b04b`
- `ntdll!RtlLcidToLocaleName` at `0x18001aea7`
- `ntdll!RtlLcidToLocaleName` at `0x18001aea7`
- `ntdll!RtlOpenCurrentUser` at `0x18001ab9c`
- `ntdll!RtlOpenCurrentUser` at `0x18001ab9c`
- `ntdll!CsrClientCallServer` at `0x18001a9a7`
- `ntdll!CsrClientCallServer` at `0x18001a9a7`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001a987`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001a987`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001a9cc`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001a9cc`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001a6bc`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001a6bc`
- `ntdll!NtClose` at `0x18001a72f`
- `ntdll!NtClose` at `0x18001ac37`
- `ntdll!NtClose` at `0x18001b05d`
- `ntdll!NtClose` at `0x18001b098`
- `ntdll!NtClose` at `0x18001a72f`
- `ntdll!NtClose` at `0x18001ac37`
- `ntdll!NtClose` at `0x18001b05d`
- `ntdll!NtClose` at `0x18001b098`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a2db`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a40e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a678`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a7a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a932`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001aaaa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a2db`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a40e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a678`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a7a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a932`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001aaaa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a4f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a88e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a8c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a95b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b119`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b19e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a4f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a88e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a8c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a95b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001ab02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b119`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b19e`
- `ntdll!RtlAllocateHeap` at `0x18001af1c`
- `ntdll!RtlAllocateHeap` at `0x18001af77`
- `ntdll!RtlAllocateHeap` at `0x18001af1c`
- `ntdll!RtlAllocateHeap` at `0x18001af77`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
int __stdcall CompareStringW(
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZWCH lpString1,
        int cchCount1,
        PCNZWCH lpString2,
        int cchCount2)
{
  unsigned int v6; // r14d
  unsigned __int64 v9; // rdi
  HANDLE NamedLocaleHashNode; // rax
  DWORD v11; // ebx
  __int64 j; // rdx
  unsigned int *v13; // rax
  __int64 v14; // r8
  DWORD v15; // ebx
  const WCHAR *v16; // rcx
  __int64 LocaleHashNode; // rax
  DWORD v18; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v21; // r8
  DWORD v22; // ebx
  const WCHAR *v23; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rsi
  __int16 *v28; // rbx
  __int64 SortNode; // rax
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v33; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v35; // rbx
  NTSTATUS v36; // esi
  HANDLE v37; // rbx
  __int64 v38; // rbx
  __int64 v39; // rax
  DWORD v40; // ebx
  __int64 k; // rdx
  unsigned int *v42; // rax
  __int64 v43; // r8
  DWORD v44; // ebx
  const WCHAR *v45; // rcx
  __int64 v46; // rax
  HANDLE *NlsCache; // rbx
  __int64 v48; // rdx
  __int64 v49; // rdx
  int v50; // eax
  int GlobalizationUserModelType; // eax
  int v52; // eax
  __int64 v53; // rcx
  WCHAR *v54; // rax
  __int64 v55; // r9
  const WCHAR *v56; // rdx
  WCHAR *v57; // r8
  __int64 v58; // rcx
  WCHAR *v59; // rcx
  __int64 v60; // rdx
  int v61; // ecx
  int v62; // r14d
  int v63; // eax
  HANDLE *v64; // rbx
  HANDLE *Heap; // rax
  HANDLE *v66; // rax
  NTSTATUS v67; // ebx
  HANDLE v68; // rcx
  void *v69; // rbx
  unsigned int *v70; // rcx
  __int64 v71; // r8
  const WCHAR *v72; // rcx
  __int64 v73; // rax
  __int64 v74; // rax
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v79; // [rsp+80h] [rbp-80h]
  __int64 v80; // [rsp+88h] [rbp-78h]
  int v81; // [rsp+90h] [rbp-70h] BYREF
  int v82; // [rsp+94h] [rbp-6Ch]
  PCNZWCH v83; // [rsp+98h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ApiMessage[32]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID CapturedData; // [rsp+110h] [rbp+10h] BYREF
  int v87; // [rsp+118h] [rbp+18h]

  v6 = cchCount1;
  v83 = lpString2;
  v82 = cchCount1;
  v9 = Locale;
  if ( Locale == 127 )
  {
    NamedLocaleHashNode = (HANDLE)gpInvLocHashN;
    goto LABEL_44;
  }
  if ( Locale > 0xC00 )
  {
    if ( Locale == 4096 )
    {
      NamedLocaleHashNode = (HANDLE)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_49;
    }
    else if ( Locale != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(Locale, KeyHandle, 0, 0) >= 0 )
    {
      NamedLocaleHashNode = (HANDLE)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( NamedLocaleHashNode )
        goto LABEL_49;
    }
LABEL_26:
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( (_DWORD)v9 != *(_DWORD *)NamedLocaleHashNode )
        goto LABEL_45;
      goto LABEL_44;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v18 = gSystemLocale;
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
      goto LABEL_104;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v18 != 127 )
      {
        v22 = HIWORD(v18);
        if ( (v22 & 0xF) == 0 )
        {
          v23 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v23, 0);
          goto LABEL_39;
        }
        v48 = WindowsLocaleData[54];
        v23 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v48 )
          v23 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v48 + 2LL * (v22 & 0xF)) - 2)
                              + 2);
        if ( v23 && *v23 )
          goto LABEL_38;
LABEL_104:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v18, v21, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_104;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocHashNodeFromSystemLocale = FindLocaleHashNode(v18);
      }
      else
      {
        LocHashNodeFromSystemLocale = 0;
      }
    }
LABEL_39:
    gpSysLocHashN = LocHashNodeFromSystemLocale;
    if ( !LocHashNodeFromSystemLocale )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( Locale != 3072 && Locale && Locale != 1024 )
  {
    if ( Locale == 2048 )
    {
      NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_49;
      if ( BasepIsSecureProcess )
        goto LABEL_44;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_23;
      v11 = gSystemLocale;
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
        goto LABEL_127;
      v13 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v13 )
      {
        if ( (_WORD)v11 != 127 )
        {
          v15 = HIWORD(v11);
          if ( (v15 & 0xF) == 0 )
          {
            v16 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v13);
LABEL_19:
            LocaleHashNode = MakeNamedLocaleHashNode(v16, 0);
            goto LABEL_20;
          }
          v49 = v13[54];
          v16 = (const WCHAR *)qword_18039EC90;
          if ( (_DWORD)v49 )
            v16 = (const WCHAR *)(qword_18039EC90
                                + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v49 + 2LL * (v15 & 0xF)) - 2)
                                + 2);
          if ( v16 && *v16 )
            goto LABEL_19;
LABEL_127:
          gpSysLocHashN = 0;
          goto LABEL_21;
        }
        LocaleHashNode = MakeLocHashNodeFromSystemLocale(v13, v11, v14, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_127;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          LocaleHashNode = FindLocaleHashNode(v11);
        }
        else
        {
          LocaleHashNode = 0;
        }
      }
LABEL_20:
      gpSysLocHashN = LocaleHashNode;
      if ( LocaleHashNode )
      {
LABEL_23:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
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
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, dwCmpFlags, lpString1);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_98;
    }
    if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803A4276 = 1;
    if ( !word_1803A4276 )
      goto LABEL_98;
    v33 = word_1803A4274;
    if ( word_1803A4274 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v33 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        if ( !word_1803A4276 )
          goto LABEL_97;
        v33 = word_1803A4274;
      }
    }
    word_1803A4276 = 2;
    if ( v33 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v35 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v87 = 1660;
        v36 = CsrClientCallServer(ApiMessage, v35, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v36 >= 0 )
          memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v35);
      }
      else
      {
        v36 = -1073741801;
      }
      if ( word_1803A4274 == 1 && v36 >= 0 )
      {
LABEL_73:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
        }
        else
        {
          v38 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
          if ( !v38 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803A3BF0 )
          {
LABEL_96:
            _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
            if ( word_1803A4274 != 3 )
LABEL_97:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_98:
            NlsCache = &gNlsProcessLocalCache;
LABEL_99:
            NamedLocaleHashNode = NlsCache[2];
            v6 = v82;
            goto LABEL_44;
          }
        }
        v39 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_95:
          qword_1803A3BF0 = v39;
          goto LABEL_96;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_94;
        v40 = gSystemLocale;
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
          goto LABEL_94;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_162;
        v42 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v42 )
        {
          if ( (_WORD)v40 != 127 )
          {
            v44 = HIWORD(v40);
            if ( (v44 & 0xF) == 0 )
            {
              v45 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v42);
LABEL_90:
              v46 = MakeNamedLocaleHashNode(v45, 0);
              goto LABEL_91;
            }
            v60 = v42[54];
            v45 = (const WCHAR *)qword_18039EC90;
            if ( (_DWORD)v60 )
              v45 = (const WCHAR *)(qword_18039EC90
                                  + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v60 + 2LL * (v44 & 0xF)) - 2)
                                  + 2);
            if ( v45 && *v45 )
              goto LABEL_90;
LABEL_162:
            gpSysLocHashN = 0;
LABEL_92:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_94;
          }
          v46 = MakeLocHashNodeFromSystemLocale(v42, v40, v43, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_162;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            v46 = FindLocaleHashNode(v40);
          }
          else
          {
            v46 = 0;
          }
        }
LABEL_91:
        gpSysLocHashN = v46;
        if ( !v46 )
          goto LABEL_92;
LABEL_94:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v39 = gpSysLocHashN;
        goto LABEL_95;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_70:
      v37 = Handle;
      NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
      if ( word_1803A4274 == 3 && v37 )
        NtClose(v37);
      goto LABEL_73;
    }
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, *(_QWORD *)&dwCmpFlags, lpString1);
    if ( GlobalizationUserModelType == 1 )
    {
      v52 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v63 = GlobalizationUserModelType - 2;
      if ( v63 )
      {
        if ( v63 != 1 )
        {
LABEL_157:
          SetLastError_0(0x3F1u);
          goto LABEL_70;
        }
        v81 = 0;
        v52 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v81);
      }
      else
      {
        v52 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v52 >= 0 )
    {
      ApiMessage[0] = 0;
      v53 = 512;
      v54 = ApiMessage;
      do
      {
        if ( !*v54 )
          break;
        ++v54;
        --v53;
      }
      while ( v53 );
      if ( !v53 )
        goto LABEL_155;
      v55 = v53;
      v56 = L"Control Panel\\International";
      v57 = &ApiMessage[512 - v53];
      v58 = 2147483646;
      do
      {
        if ( !v58 )
          break;
        if ( !*v56 )
          break;
        *v57++ = *v56++;
        --v58;
        --v55;
      }
      while ( v55 );
      v59 = v57 - 1;
      if ( v55 )
        v59 = v57;
      *v59 = 0;
      if ( v55 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v67 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v67 < 0 )
          v67 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v67 >= 0 )
        {
          v68 = Handle;
        }
        else
        {
          v68 = 0;
          Handle = 0;
        }
        if ( v67 >= 0 )
        {
          v69 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v68,
                          0);
          if ( v69 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v69;
          }
          goto LABEL_70;
        }
      }
      else
      {
LABEL_155:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_157;
  }
  NlsCache = 0;
  v61 = IsImpersonating - 1;
  if ( v61 )
  {
    if ( v61 != 1 )
      goto LABEL_99;
    if ( BasepIsSecureProcess )
      goto LABEL_98;
    v62 = 0;
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
        v62 = 1;
        *((_WORD *)Heap + 842) = 3;
        *((_WORD *)Heap + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v62 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_99;
    *((_WORD *)NlsCache + 843) = 1;
    UpdateNlsInfoCache(NlsCache, 0);
    NamedLocaleHashNode = NlsCache[2];
    v6 = v82;
  }
  else
  {
    if ( BasepIsSecureProcess )
    {
      v64 = &gNlsProcessLocalCache;
    }
    else
    {
      v64 = (HANDLE *)NtCurrentTeb()->NlsCache;
      if ( !v64 )
      {
        v66 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
        v64 = v66;
        if ( v66 )
        {
          *v66 = 0;
          v66[1] = 0;
          v66[2] = 0;
          *((_WORD *)v66 + 842) = 3;
          *((_WORD *)v66 + 843) = 1;
        }
        else
        {
          v64 = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = v64;
      }
      if ( v64 != &gNlsProcessLocalCache )
      {
        *((_WORD *)v64 + 843) = 1;
        UpdateNlsInfoCache(v64, 0);
      }
    }
    NtCurrentTeb()->IsImpersonating = 2;
    NamedLocaleHashNode = v64[2];
    v6 = v82;
  }
LABEL_44:
  if ( NamedLocaleHashNode )
    goto LABEL_49;
LABEL_45:
  v25 = ((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F;
  v26 = *((_QWORD *)P + v25);
  v27 = 8 * v25;
  if ( v26 )
  {
    while ( *(_DWORD *)v26 != (_DWORD)v9 )
    {
      v26 = *(_QWORD *)(v26 + 88);
      if ( !v26 )
        goto LABEL_106;
    }
    goto LABEL_47;
  }
LABEL_106:
  RtlAcquireSRWLockExclusive(&gTblPtrsLock);
  v26 = *(_QWORD *)((char *)P + v27);
  if ( v26 )
  {
    while ( *(_DWORD *)v26 != (_DWORD)v9 )
    {
      v26 = *(_QWORD *)(v26 + 88);
      if ( !v26 )
        goto LABEL_222;
    }
    goto LABEL_108;
  }
LABEL_222:
  if ( (v9 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
  {
    v70 = (unsigned int *)GetWindowsLocaleData((unsigned int)v9);
    if ( v70 )
    {
      if ( (_WORD)v9 == 127 )
      {
        v26 = MakeLocHashNodeFromSystemLocale(v70, (unsigned int)v9, v71, 0);
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        goto LABEL_47;
      }
      if ( (v9 & 0xF0000) == 0 )
      {
        v72 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v70);
LABEL_228:
        v73 = MakeNamedLocaleHashNode(v72, 0);
LABEL_229:
        v26 = v73;
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        goto LABEL_47;
      }
      v74 = v70[54];
      v72 = (const WCHAR *)qword_18039EC90;
      if ( (_DWORD)v74 )
        v72 = (const WCHAR *)(qword_18039EC90
                            + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v74 + 2LL * (BYTE2(v9) & 0xF)) - 2)
                            + 2);
      if ( v72 && *v72 )
        goto LABEL_228;
    }
    else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
           && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales()) )
    {
      v73 = FindLocaleHashNode((unsigned int)v9);
      goto LABEL_229;
    }
  }
  v26 = 0;
LABEL_108:
  RtlReleaseSRWLockExclusive(&gTblPtrsLock);
LABEL_47:
  if ( v26 )
  {
    NamedLocaleHashNode = *(HANDLE *)(v26 + 104);
    if ( NamedLocaleHashNode )
      goto LABEL_49;
  }
  else
  {
    NamedLocaleHashNode = 0;
  }
  if ( (_DWORD)v9 == 4096 || (v9 & 0x3FF) == 0 && (unsigned int)(v9 - 0x2000) <= 0x2C00 )
    NamedLocaleHashNode = GetCurrentNlsCache()[2];
  if ( !NamedLocaleHashNode )
    goto LABEL_50;
LABEL_49:
  v28 = (__int16 *)*((_QWORD *)NamedLocaleHashNode + 4);
  if ( !v28 )
    goto LABEL_50;
  if ( !g_definedDefaultSortVersion )
  {
    *(_QWORD *)&DestinationString.Length = 32;
    DestinationString.Buffer = 0;
    v79 = 0;
    v80 = 0;
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( !g_definedDefaultSortVersion )
    {
      if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
        && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
      {
        v50 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
      }
      else
      {
        v50 = 256;
      }
      dword_18039D2B4 = v50 | 0xFF;
      dword_18039D2B8 = v50 | 0xFF;
      _InterlockedExchange(&g_definedDefaultSortVersion, 1);
    }
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
  }
  SortNode = GetSortNode(v28, (__int64)g_defaultSortVersion, 0);
  if ( !SortNode )
  {
LABEL_50:
    SetLastError_0(0x57u);
    return 0;
  }
  return (*(__int64 (__fastcall **)(__int64, _QWORD, PCNZWCH, _QWORD, PCNZWCH, int, _QWORD, _QWORD))(SortNode + 240))(
           SortNode,
           dwCmpFlags ^ 0x8000000,
           lpString1,
           v6,
           v83,
           cchCount2,
           0,
           0);
}

```

## disassembly

```asm
0x18001a230  push    rbp
0x18001a232  push    rbx
0x18001a233  push    rsi
0x18001a234  push    rdi
0x18001a235  push    r12
0x18001a237  push    r13
0x18001a239  push    r14
0x18001a23b  push    r15
0x18001a23d  lea     rbp, [rsp-3E8h]
0x18001a245  sub     rsp, 4E8h
0x18001a24c  mov     rax, cs:__security_cookie
0x18001a253  xor     rax, rsp
0x18001a256  mov     [rbp+420h+var_50], rax
0x18001a25d  mov     rax, [rbp+420h+lpString2]
0x18001a264  mov     r14d, r9d
0x18001a267  mov     [rbp+420h+var_488], rax
0x18001a26b  mov     r13, r8
0x18001a26e  mov     [rbp+420h+var_48C], r9d
0x18001a272  mov     r12d, edx
0x18001a275  mov     edi, ecx
0x18001a277  mov     r15d, 1
0x18001a27d  cmp     ecx, 7Fh
0x18001a280  jz      loc_18001A590
0x18001a286  cmp     edi, 0C00h
0x18001a28c  ja      loc_18001A3D3
0x18001a292  jz      loc_18001A607
0x18001a298  test    ecx, ecx
0x18001a29a  jz      loc_18001A607
0x18001a2a0  cmp     edi, 400h
0x18001a2a6  jz      loc_18001A607
0x18001a2ac  cmp     edi, 800h
0x18001a2b2  jnz     loc_18001A3EB
0x18001a2b8  mov     rax, cs:gpSysLocHashN
0x18001a2bf  test    rax, rax
0x18001a2c2  jnz     loc_18001A558
0x18001a2c8  cmp     cs:BasepIsSecureProcess, al
0x18001a2ce  jnz     loc_18001A505
0x18001a2d4  lea     rcx, gTblPtrsLock
0x18001a2db  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a2e1  cmp     cs:gpSysLocHashN, 0
0x18001a2e9  jnz     loc_18001A3BA
0x18001a2ef  mov     ebx, cs:gSystemLocale
0x18001a2f5  mov     rax, cs:P
0x18001a2fc  mov     ecx, ebx
0x18001a2fe  shr     rcx, 7
0x18001a302  xor     rcx, rbx
0x18001a305  shr     rcx, 7
0x18001a309  xor     rcx, rbx
0x18001a30c  and     ecx, 7Fh
0x18001a30f  mov     rdx, [rax+rcx*8]
0x18001a313  test    rdx, rdx
0x18001a316  jz      short loc_18001A320
0x18001a318  cmp     [rdx], ebx
0x18001a31a  jnz     loc_18001AD25
0x18001a320  mov     cs:gpSysLocHashN, rdx
0x18001a327  test    rdx, rdx
0x18001a32a  jnz     loc_18001A3BA
0x18001a330  test    ebx, 0FFF00000h
0x18001a336  jnz     loc_18001AA71
0x18001a33c  cmp     cs:BasepIsSecureProcess, dl
0x18001a342  jnz     loc_18001AA71
0x18001a348  mov     ecx, ebx
0x18001a34a  call    GetWindowsLocaleData
0x18001a34f  test    rax, rax
0x18001a352  jz      loc_18001AD37
0x18001a358  cmp     bx, 7Fh
0x18001a35c  jz      loc_18001AD78
0x18001a362  shr     ebx, 10h
0x18001a365  test    bl, 0Fh
0x18001a368  jnz     loc_18001AA3E
0x18001a36e  mov     ecx, [rax]
0x18001a370  mov     rax, cs:qword_18039EC90
0x18001a377  add     rax, 2
0x18001a37b  lea     rcx, [rax+rcx*2]
0x18001a37f  xor     edx, edx
0x18001a381  call    MakeNamedLocaleHashNode
0x18001a386  mov     cs:gpSysLocHashN, rax
0x18001a38d  test    rax, rax
0x18001a390  jnz     short loc_18001A3BA
0x18001a392  xor     edx, edx
0x18001a394  lea     rcx, aEnUs; "en-US"
0x18001a39b  call    MakeNamedLocaleHashNode
0x18001a3a0  mov     cs:gpSysLocHashN, rax
0x18001a3a7  test    rax, rax
0x18001a3aa  jnz     short loc_18001A3BA
0x18001a3ac  mov     rax, cs:gpInvLocHashN
0x18001a3b3  mov     cs:gpSysLocHashN, rax
0x18001a3ba  lea     rcx, gTblPtrsLock
0x18001a3c1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a3c7  mov     rax, cs:gpSysLocHashN
0x18001a3ce  jmp     loc_18001A505
0x18001a3d3  cmp     edi, 1000h
0x18001a3d9  jz      loc_18001AE6F
0x18001a3df  cmp     edi, 1400h
0x18001a3e5  jz      loc_18001AE7F
0x18001a3eb  mov     rax, cs:gpSysLocHashN
0x18001a3f2  test    rax, rax
0x18001a3f5  jnz     loc_18001A501
0x18001a3fb  cmp     cs:BasepIsSecureProcess, al
0x18001a401  jnz     loc_18001A501
0x18001a407  lea     rcx, gTblPtrsLock
0x18001a40e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a414  cmp     cs:gpSysLocHashN, 0
0x18001a41c  jnz     loc_18001A4ED
0x18001a422  mov     ebx, cs:gSystemLocale
0x18001a428  mov     rax, cs:P
0x18001a42f  mov     ecx, ebx
0x18001a431  shr     rcx, 7
0x18001a435  xor     rcx, rbx
0x18001a438  shr     rcx, 7
0x18001a43c  xor     rcx, rbx
0x18001a43f  and     ecx, 7Fh
0x18001a442  mov     rdx, [rax+rcx*8]
0x18001a446  test    rdx, rdx
0x18001a449  jz      short loc_18001A453
0x18001a44b  cmp     [rdx], ebx
0x18001a44d  jnz     loc_18001A966
0x18001a453  mov     cs:gpSysLocHashN, rdx
0x18001a45a  test    rdx, rdx
0x18001a45d  jnz     loc_18001A4ED
0x18001a463  test    ebx, 0FFF00000h
0x18001a469  jnz     loc_18001A90E
0x18001a46f  cmp     cs:BasepIsSecureProcess, dl
0x18001a475  jnz     loc_18001A90E
0x18001a47b  mov     ecx, ebx
0x18001a47d  call    GetWindowsLocaleData
0x18001a482  test    rax, rax
0x18001a485  jz      loc_18001AA10
0x18001a48b  cmp     bx, 7Fh
0x18001a48f  jz      loc_18001AB45
0x18001a495  shr     ebx, 10h
0x18001a498  test    bl, 0Fh
0x18001a49b  jnz     loc_18001A8DB
0x18001a4a1  mov     ecx, [rax]
0x18001a4a3  mov     rax, cs:qword_18039EC90
0x18001a4aa  add     rax, 2
0x18001a4ae  lea     rcx, [rax+rcx*2]
0x18001a4b2  xor     edx, edx
0x18001a4b4  call    MakeNamedLocaleHashNode
0x18001a4b9  mov     cs:gpSysLocHashN, rax
0x18001a4c0  test    rax, rax
0x18001a4c3  jnz     short loc_18001A4ED
0x18001a4c5  xor     edx, edx
0x18001a4c7  lea     rcx, aEnUs; "en-US"
0x18001a4ce  call    MakeNamedLocaleHashNode
0x18001a4d3  mov     cs:gpSysLocHashN, rax
0x18001a4da  test    rax, rax
0x18001a4dd  jnz     short loc_18001A4ED
0x18001a4df  mov     rax, cs:gpInvLocHashN
0x18001a4e6  mov     cs:gpSysLocHashN, rax
0x18001a4ed  lea     rcx, gTblPtrsLock
0x18001a4f4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a4fa  mov     rax, cs:gpSysLocHashN
0x18001a501  cmp     edi, [rax]
0x18001a503  jnz     short loc_18001A50A
0x18001a505  test    rax, rax
0x18001a508  jnz     short loc_18001A558
0x18001a50a  mov     rax, cs:P
0x18001a511  mov     rcx, rdi
0x18001a514  shr     rcx, 7
0x18001a518  xor     rcx, rdi
0x18001a51b  shr     rcx, 7
0x18001a51f  xor     rcx, rdi
0x18001a522  and     ecx, 7Fh
0x18001a525  mov     rbx, [rax+rcx*8]
0x18001a529  lea     rsi, ds:0[rcx*8]
0x18001a531  test    rbx, rbx
0x18001a534  jz      loc_18001A92B
0x18001a53a  cmp     [rbx], edi
0x18001a53c  jnz     loc_18001A91E
0x18001a542  test    rbx, rbx
0x18001a545  jz      loc_18001AB0D
0x18001a54b  mov     rax, [rbx+68h]
0x18001a54f  test    rax, rax
0x18001a552  jz      loc_18001AB0F
0x18001a558  mov     rbx, [rax+20h]
0x18001a55c  test    rbx, rbx
0x18001a55f  jnz     short loc_18001A59C
0x18001a561  mov     ecx, 57h ; 'W'; dwErrCode
0x18001a566  call    SetLastError_0
0x18001a56b  xor     eax, eax
0x18001a56d  mov     rcx, [rbp+420h+var_50]
0x18001a574  xor     rcx, rsp; StackCookie
0x18001a577  call    __security_check_cookie
0x18001a57c  add     rsp, 4E8h
0x18001a583  pop     r15
0x18001a585  pop     r14
0x18001a587  pop     r13
0x18001a589  pop     r12
0x18001a58b  pop     rdi
0x18001a58c  pop     rsi
0x18001a58d  pop     rbx
0x18001a58e  pop     rbp
0x18001a58f  retn
0x18001a590  mov     rax, cs:gpInvLocHashN
0x18001a597  jmp     loc_18001A505
0x18001a59c  cmp     cs:g_definedDefaultSortVersion, 0
0x18001a5a3  jz      loc_18001AA81
0x18001a5a9  xor     r8d, r8d
0x18001a5ac  lea     rdx, g_defaultSortVersion
0x18001a5b3  mov     rcx, rbx
0x18001a5b6  call    GetSortNode
0x18001a5bb  test    rax, rax
0x18001a5be  jz      short loc_18001A561
0x18001a5c0  mov     ecx, [rbp+420h+cchCount2]
0x18001a5c6  btc     r12d, 1Bh
0x18001a5cb  mov     [rsp+520h+var_4E8], 0
0x18001a5d4  mov     r9d, r14d
0x18001a5d7  mov     [rsp+520h+Disposition], 0
0x18001a5e0  mov     r8, r13
0x18001a5e3  mov     [rsp+520h+CreateOptions], ecx
0x18001a5e7  mov     edx, r12d
0x18001a5ea  mov     rcx, [rbp+420h+var_488]
0x18001a5ee  mov     [rsp+520h+Class], rcx
0x18001a5f3  mov     rcx, rax
0x18001a5f6  mov     rax, [rax+0F0h]
0x18001a5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a602  jmp     loc_18001A56D
0x18001a607  mov     rax, gs:30h
0x18001a610  mov     ecx, [rax+179Ch]
0x18001a616  test    ecx, ecx
0x18001a618  jnz     loc_18001AC98
0x18001a61e  mov     eax, cs:gInteractiveLogonUserProcess
0x18001a624  cmp     eax, 0FFFFFFFFh
0x18001a627  jz      loc_18001ADC4
0x18001a62d  test    eax, eax
0x18001a62f  jz      loc_18001AC8E
0x18001a635  mov     rax, cs:gpServerNlsUserInfo
0x18001a63c  mov     ecx, [rax+678h]
0x18001a642  mov     eax, cs:dword_1803A4270
0x18001a648  cmp     eax, ecx
0x18001a64a  jz      short loc_18001A654
0x18001a64c  mov     cs:word_1803A4276, r15w
0x18001a654  movzx   eax, cs:word_1803A4276
0x18001a65b  test    ax, ax
0x18001a65e  jz      loc_18001A8C7
0x18001a664  movzx   eax, cs:word_1803A4274
0x18001a66b  cmp     ax, 3
0x18001a66f  jz      short loc_18001A68F
0x18001a671  lea     rcx, gNlsProcessCacheLock
0x18001a678  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a67e  movzx   eax, cs:word_1803A4274
0x18001a685  cmp     ax, 3
0x18001a689  jnz     loc_18001A9E4
0x18001a68f  mov     r14d, 2
0x18001a695  mov     cs:word_1803A4276, r14w
0x18001a69d  cmp     ax, r15w
0x18001a6a1  jnz     short loc_18001A6E1
0x18001a6a3  xor     edx, edx; Val
0x18001a6a5  lea     rcx, [rbp+420h+ApiMessage]; void *
0x18001a6a9  mov     r8d, 3B8h; Size
0x18001a6af  call    memset_0
0x18001a6b4  mov     edx, 67Ch; BufferSize
0x18001a6b9  mov     ecx, r15d; ArgumentCount
0x18001a6bc  call    cs:__imp_CsrAllocateCaptureBuffer
0x18001a6c2  mov     rbx, rax
0x18001a6c5  test    rax, rax
0x18001a6c8  jnz     loc_18001A978
0x18001a6ce  mov     esi, 0C0000017h
0x18001a6d3  cmp     cs:word_1803A4274, r15w
0x18001a6db  jz      loc_18001A9D7
0x18001a6e1  mov     rax, cs:gNlsProcessLocalCache
0x18001a6e8  mov     [rsp+520h+Handle], 0
0x18001a6f1  test    rax, rax
0x18001a6f4  jz      loc_18001AB57
0x18001a6fa  mov     rax, cs:gNlsProcessLocalCache
0x18001a701  mov     [rsp+520h+Handle], rax
0x18001a706  mov     rbx, [rsp+520h+Handle]
0x18001a70b  lea     rcx, word_1803A3BF8
0x18001a712  mov     rdx, rbx
0x18001a715  mov     r8d, r15d
0x18001a718  call    NlsUpdateCacheInfo
0x18001a71d  cmp     cs:word_1803A4274, 3
0x18001a725  jnz     short loc_18001A735
0x18001a727  test    rbx, rbx
0x18001a72a  jz      short loc_18001A735
0x18001a72c  mov     rcx, rbx; Handle
0x18001a72f  call    cs:__imp_NtClose
0x18001a735  mov     eax, 0FFFFh
0x18001a73a  cmp     cs:word_1803A3BF8, ax
0x18001a741  jz      loc_18001AA00
0x18001a747  mov     rbx, cs:gpOneCustomHashNode
0x18001a74e  lea     rcx, word_1803A3BFA
0x18001a755  xor     edx, edx
0x18001a757  call    GetNamedLocaleHashNode
0x18001a75c  xchg    rax, cs:qword_1803A3BF0
0x18001a763  test    rbx, rbx
0x18001a766  jnz     short loc_18001A778
0x18001a768  cmp     cs:gpOneCustomHashNode, rbx
0x18001a76f  jz      short loc_18001A778
0x18001a771  mov     cs:gpOneCustomHashNode, rbx
0x18001a778  cmp     cs:qword_1803A3BF0, 0
0x18001a780  jnz     loc_18001A8A2
0x18001a786  mov     rax, cs:gpSysLocHashN
0x18001a78d  test    rax, rax
0x18001a790  jnz     loc_18001A89B
0x18001a796  cmp     cs:BasepIsSecureProcess, al
0x18001a79c  jnz     loc_18001A89B
0x18001a7a2  lea     rcx, gTblPtrsLock
0x18001a7a9  call    cs:__imp_RtlAcquireSRWLockExclusive
  ... truncated ...
```
