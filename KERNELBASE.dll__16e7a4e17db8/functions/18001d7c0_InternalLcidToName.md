# InternalLcidToName

- ea: `0x18001d7c0`
- end: `0x18001e78e`
- name: `InternalLcidToName`
- size: `4046`
- prototype: ``
- caller_count: `9`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007610`
- `0x18001ea50`
- `0x18001eec0`
- `0x18003bb00`
- `0x18003ca40`
- `0x18003cb20`
- `0x18003cec0`
- `0x18003d060`
- `0x18003e120`

## callees

- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x1800123e0`
- `0x180012f10`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001d7c0`
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

- `ntdll!RtlInitUnicodeString` at `0x18001e48d`
- `ntdll!RtlInitUnicodeString` at `0x18001e48d`
- `ntdll!RtlEqualSid` at `0x18001e6ba`
- `ntdll!RtlEqualSid` at `0x18001e6ba`
- `ntdll!NtOpenKey` at `0x18001e4d3`
- `ntdll!NtOpenKey` at `0x18001e4d3`
- `ntdll!NtCreateKey` at `0x18001e50c`
- `ntdll!NtCreateKey` at `0x18001e50c`
- `ntdll!RtlLcidToLocaleName` at `0x18001e360`
- `ntdll!RtlLcidToLocaleName` at `0x18001e360`
- `ntdll!RtlOpenCurrentUser` at `0x18001e02a`
- `ntdll!RtlOpenCurrentUser` at `0x18001e02a`
- `ntdll!NtQueryInformationToken` at `0x18001e60a`
- `ntdll!NtQueryInformationToken` at `0x18001e69f`
- `ntdll!NtQueryInformationToken` at `0x18001e60a`
- `ntdll!NtQueryInformationToken` at `0x18001e69f`
- `ntdll!CsrClientCallServer` at `0x18001dec1`
- `ntdll!CsrClientCallServer` at `0x18001dec1`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001dea1`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001dea1`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001dee6`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001dee6`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001dab0`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001dab0`
- `ntdll!NtClose` at `0x18001db23`
- `ntdll!NtClose` at `0x18001e0c7`
- `ntdll!NtClose` at `0x18001e51e`
- `ntdll!NtClose` at `0x18001e559`
- `ntdll!NtClose` at `0x18001db23`
- `ntdll!NtClose` at `0x18001e0c7`
- `ntdll!NtClose` at `0x18001e51e`
- `ntdll!NtClose` at `0x18001e559`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d84a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001da6c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001db9d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001dcfe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de4c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d84a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001da6c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001db9d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001dcfe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d92f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dc82`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dcb5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dde3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001de75`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e5de`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e769`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d92f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dc82`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dcb5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001dde3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001de75`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e5de`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e769`
- `ntdll!RtlFreeHeap` at `0x18001e6d8`
- `ntdll!RtlFreeHeap` at `0x18001e6d8`
- `ntdll!RtlAllocateHeap` at `0x18001e3da`
- `ntdll!RtlAllocateHeap` at `0x18001e435`
- `ntdll!RtlAllocateHeap` at `0x18001e670`
- `ntdll!RtlAllocateHeap` at `0x18001e3da`
- `ntdll!RtlAllocateHeap` at `0x18001e435`
- `ntdll!RtlAllocateHeap` at `0x18001e670`

## pseudocode

```c
__int64 __fastcall InternalLcidToName(unsigned int a1, int a2)
{
  unsigned __int64 v2; // rdi
  _QWORD *v4; // rbx
  DWORD v5; // ebx
  __int64 k; // rdx
  unsigned int *v7; // rax
  __int64 v8; // r8
  DWORD v9; // ebx
  _WORD *v10; // rcx
  __int64 LocaleHashNode; // rax
  __int64 v12; // rsi
  ULONG IsImpersonating; // ecx
  int v15; // ebx
  __int16 v16; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v18; // rbx
  NTSTATUS v19; // esi
  HANDLE v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rax
  DWORD v23; // ebx
  __int64 j; // rdx
  unsigned int *v25; // rax
  __int64 v26; // r8
  DWORD v27; // ebx
  _WORD *v28; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  HANDLE *NlsCache; // rbx
  DWORD v31; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v34; // r8
  DWORD v35; // ebx
  _WORD *v36; // rcx
  __int64 NamedLocaleHashNode; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  int GlobalizationUserModelType; // eax
  int v41; // eax
  __int64 v42; // rcx
  WCHAR *v43; // rax
  __int64 v44; // r9
  const WCHAR *v45; // rdx
  WCHAR *v46; // r8
  __int64 v47; // rcx
  WCHAR *v48; // rcx
  __int64 v49; // rdx
  ULONG v50; // ecx
  int v51; // r15d
  int v52; // eax
  HANDLE *v53; // rax
  HANDLE *Heap; // rax
  NTSTATUS v55; // ebx
  HANDLE v56; // rcx
  void *v57; // rbx
  unsigned int *v58; // rcx
  __int64 v59; // r8
  _WORD *v60; // rcx
  __int64 v61; // rax
  PSID *v62; // rsi
  __int64 v63; // rax
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-58h]
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v73; // [rsp+F8h] [rbp-8h]

  v2 = a1;
  if ( a1 == 127 )
  {
    v4 = (_QWORD *)gpInvLocHashN;
    goto LABEL_25;
  }
  if ( a1 <= 0xC00 )
  {
    if ( a1 != 3072 && a1 && a1 != 1024 )
    {
      if ( a1 != 2048 )
        goto LABEL_7;
      v4 = (_QWORD *)gpSysLocHashN;
      if ( gpSysLocHashN )
        return v4[4];
      if ( BasepIsSecureProcess )
        goto LABEL_25;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_96;
      v31 = gSystemLocale;
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
        goto LABEL_96;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_124;
      WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( WindowsLocaleData )
      {
        if ( (_WORD)v31 != 127 )
        {
          v35 = HIWORD(v31);
          if ( (v35 & 0xF) == 0 )
          {
            v36 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_92:
            NamedLocaleHashNode = MakeNamedLocaleHashNode(v36, 0);
            goto LABEL_93;
          }
          v39 = WindowsLocaleData[54];
          v36 = (_WORD *)qword_18039EC90;
          if ( (_DWORD)v39 )
            v36 = (_WORD *)(qword_18039EC90
                          + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v39 + 2LL * (v35 & 0xF)) - 2)
                          + 2);
          if ( v36 && *v36 )
            goto LABEL_92;
LABEL_124:
          gpSysLocHashN = 0;
LABEL_94:
          gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
          if ( !gpSysLocHashN )
            gpSysLocHashN = gpInvLocHashN;
          goto LABEL_96;
        }
        NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v31, v34, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_124;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          NamedLocaleHashNode = FindLocaleHashNode(v31);
        }
        else
        {
          NamedLocaleHashNode = 0;
        }
      }
LABEL_93:
      gpSysLocHashN = NamedLocaleHashNode;
      if ( !NamedLocaleHashNode )
        goto LABEL_94;
LABEL_96:
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      v4 = (_QWORD *)gpSysLocHashN;
      goto LABEL_25;
    }
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( IsImpersonating )
    {
      NlsCache = 0;
      v50 = IsImpersonating - 1;
      if ( !v50 )
      {
        if ( BasepIsSecureProcess )
        {
          NlsCache = &gNlsProcessLocalCache;
        }
        else
        {
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
              *((_WORD *)Heap + 842) = 3;
              *((_WORD *)Heap + 843) = 1;
            }
            else
            {
              NlsCache = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = NlsCache;
          }
          if ( NlsCache != &gNlsProcessLocalCache )
          {
            *((_WORD *)NlsCache + 843) = 1;
            UpdateNlsInfoCache(NlsCache, 0);
          }
        }
        NtCurrentTeb()->IsImpersonating = 2;
        goto LABEL_79;
      }
      if ( v50 != 1 )
      {
LABEL_79:
        v4 = NlsCache[2];
        goto LABEL_25;
      }
      if ( !BasepIsSecureProcess )
      {
        v51 = 0;
        NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
        if ( !NlsCache )
        {
          v53 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
          NlsCache = v53;
          if ( v53 )
          {
            *v53 = 0;
            v53[1] = 0;
            v53[2] = 0;
            v51 = 1;
            *((_WORD *)v53 + 842) = 3;
            *((_WORD *)v53 + 843) = 1;
          }
          else
          {
            NlsCache = &gNlsProcessLocalCache;
          }
          NtCurrentTeb()->NlsCache = NlsCache;
        }
        if ( NlsCache != &gNlsProcessLocalCache && (v51 || *((_WORD *)NlsCache + 843) == 1) )
        {
          *((_WORD *)NlsCache + 843) = 1;
          UpdateNlsInfoCache(NlsCache, 0);
        }
        goto LABEL_79;
      }
      goto LABEL_78;
    }
    v15 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
    {
      v15 = 0;
      v70 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      ReturnLength = 0;
      if ( !BasepIsSecureProcess
        && NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFCLL,
             TokenStatistics,
             &ObjectAttributes,
             0x38u,
             &ReturnLength) >= 0 )
      {
        if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
        {
          v15 = 1;
          gInteractiveLogonUserProcess = 1;
          word_1803A4274 = 1;
          goto LABEL_38;
        }
        v62 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
        if ( v62 )
        {
          if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, v62, 0x54u, &ReturnLength) >= 0 )
            v15 = RtlEqualSid(*v62, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v62);
        }
      }
      gInteractiveLogonUserProcess = v15;
      if ( v15 )
        word_1803A4274 = 1;
      else
        word_1803A4274 = 20;
    }
LABEL_38:
    if ( !v15 )
    {
      NlsCheckStaleCache();
      goto LABEL_78;
    }
    if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803A4276 = 1;
    if ( !word_1803A4276 )
      goto LABEL_78;
    v16 = word_1803A4274;
    if ( word_1803A4274 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v16 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        if ( !word_1803A4276 )
          goto LABEL_77;
        v16 = word_1803A4274;
      }
    }
    word_1803A4276 = 2;
    if ( v16 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v18 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v73 = 1660;
        v19 = CsrClientCallServer(ApiMessage, v18, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v19 >= 0 )
          memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v18);
      }
      else
      {
        v19 = -1073741801;
      }
      if ( word_1803A4274 == 1 && v19 >= 0 )
      {
LABEL_53:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
        }
        else
        {
          v21 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
          if ( !v21 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803A3BF0 )
          {
LABEL_76:
            _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
            if ( word_1803A4274 != 3 )
LABEL_77:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_78:
            NlsCache = &gNlsProcessLocalCache;
            goto LABEL_79;
          }
        }
        v22 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_75:
          qword_1803A3BF0 = v22;
          goto LABEL_76;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_74;
        v23 = gSystemLocale;
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
          goto LABEL_74;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_152;
        v25 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v25 )
        {
          if ( (_WORD)v23 != 127 )
          {
            v27 = HIWORD(v23);
            if ( (v27 & 0xF) == 0 )
            {
              v28 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v25);
LABEL_70:
              LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v28, 0);
              goto LABEL_71;
            }
            v49 = v25[54];
            v28 = (_WORD *)qword_18039EC90;
            if ( (_DWORD)v49 )
              v28 = (_WORD *)(qword_18039EC90
                            + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v49 + 2LL * (v27 & 0xF)) - 2)
                            + 2);
            if ( v28 && *v28 )
              goto LABEL_70;
LABEL_152:
            gpSysLocHashN = 0;
LABEL_72:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_74;
          }
          LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v25, v23, v26, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_152;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocHashNodeFromSystemLocale = FindLocaleHashNode(v23);
          }
          else
          {
            LocHashNodeFromSystemLocale = 0;
          }
        }
LABEL_71:
        gpSysLocHashN = LocHashNodeFromSystemLocale;
        if ( !LocHashNodeFromSystemLocale )
          goto LABEL_72;
LABEL_74:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v22 = gpSysLocHashN;
        goto LABEL_75;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_50:
      v20 = Handle;
      NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
      if ( word_1803A4274 == 3 && v20 )
        NtClose(v20);
      goto LABEL_53;
    }
    KeyHandle[0] = 0;
    ReturnLength = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType();
    if ( GlobalizationUserModelType == 1 )
    {
      v41 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v52 = GlobalizationUserModelType - 2;
      if ( v52 )
      {
        if ( v52 != 1 )
        {
LABEL_147:
          SetLastError_0(0x3F1u);
          goto LABEL_50;
        }
        v67 = 0;
        v41 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v67);
      }
      else
      {
        v41 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v41 >= 0 )
    {
      ApiMessage[0] = 0;
      v42 = 512;
      v43 = ApiMessage;
      do
      {
        if ( !*v43 )
          break;
        ++v43;
        --v42;
      }
      while ( v42 );
      if ( !v42 )
        goto LABEL_145;
      v44 = v42;
      v45 = L"Control Panel\\International";
      v46 = &ApiMessage[512 - v42];
      v47 = 2147483646;
      do
      {
        if ( !v47 )
          break;
        if ( !*v45 )
          break;
        *v46++ = *v45++;
        --v47;
        --v44;
      }
      while ( v44 );
      v48 = v46 - 1;
      if ( v44 )
        v48 = v46;
      *v48 = 0;
      if ( v44 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ReturnLength = 0;
        v55 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v55 < 0 )
          v55 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &ReturnLength);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v55 >= 0 )
        {
          v56 = Handle;
        }
        else
        {
          v56 = 0;
          Handle = 0;
        }
        if ( v55 >= 0 )
        {
          v57 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v56,
                          0);
          if ( v57 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v57;
          }
          goto LABEL_50;
        }
      }
      else
      {
LABEL_145:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_147;
  }
  if ( a1 == 4096 )
  {
    v4 = (_QWORD *)gpOneCustomHashNode;
    if ( gpOneCustomHashNode )
      return v4[4];
  }
  else if ( a1 != 5120 )
  {
    goto LABEL_7;
  }
  KeyHandle[0] = (HANDLE)11141120;
  KeyHandle[1] = ApiMessage;
  if ( (int)RtlLcidToLocaleName(a1, KeyHandle, 0, 0) >= 0 )
  {
    v4 = (_QWORD *)GetNamedLocaleHashNode(KeyHandle[1], 0);
    if ( v4 )
      return v4[4];
  }
LABEL_7:
  v4 = (_QWORD *)gpSysLocHashN;
  if ( !gpSysLocHashN && !BasepIsSecureProcess )
  {
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v5 = gSystemLocale;
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
      goto LABEL_23;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_101;
    v7 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v7 )
    {
      if ( (_WORD)v5 != 127 )
      {
        v9 = HIWORD(v5);
        if ( (v9 & 0xF) == 0 )
        {
          v10 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v7);
LABEL_19:
          LocaleHashNode = MakeNamedLocaleHashNode(v10, 0);
          goto LABEL_20;
        }
        v38 = v7[54];
        v10 = (_WORD *)qword_18039EC90;
        if ( (_DWORD)v38 )
          v10 = (_WORD *)(qword_18039EC90
                        + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v38 + 2LL * (v9 & 0xF)) - 2)
                        + 2);
        if ( v10 && *v10 )
          goto LABEL_19;
LABEL_101:
        gpSysLocHashN = 0;
        goto LABEL_21;
      }
      LocaleHashNode = MakeLocHashNodeFromSystemLocale(v7, v5, v8, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_101;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocaleHashNode = FindLocaleHashNode(v5);
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
      v4 = (_QWORD *)gpSysLocHashN;
      goto LABEL_24;
    }
LABEL_21:
    gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
    if ( !gpSysLocHashN )
      gpSysLocHashN = gpInvLocHashN;
    goto LABEL_23;
  }
LABEL_24:
  if ( (_DWORD)v2 != *(_DWORD *)v4 )
    goto LABEL_26;
LABEL_25:
  if ( v4 )
    return v4[4];
LABEL_26:
  v12 = 8LL * (((unsigned __int8)v2 ^ (unsigned __int8)((v2 ^ (v2 >> 7)) >> 7)) & 0x7F);
  v4 = *(_QWORD **)((char *)P + v12);
  if ( !v4 )
  {
LABEL_103:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v4 = *(_QWORD **)((char *)P + v12);
    if ( v4 )
    {
      while ( *(_DWORD *)v4 != (_DWORD)v2 )
      {
        v4 = (_QWORD *)v4[11];
        if ( !v4 )
          goto LABEL_214;
      }
      goto LABEL_105;
    }
LABEL_214:
    if ( (v2 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v58 = (unsigned int *)GetWindowsLocaleData((unsigned int)v2);
      if ( v58 )
      {
        if ( (_WORD)v2 == 127 )
        {
          v4 = (_QWORD *)MakeLocHashNodeFromSystemLocale(v58, (unsigned int)v2, v59, 0);
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_28;
        }
        if ( (v2 & 0xF0000) == 0 )
        {
          v60 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v58);
LABEL_220:
          v61 = MakeNamedLocaleHashNode(v60, 0);
LABEL_221:
          v4 = (_QWORD *)v61;
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_28;
        }
        v63 = v58[54];
        v60 = (_WORD *)qword_18039EC90;
        if ( (_DWORD)v63 )
          v60 = (_WORD *)(qword_18039EC90
                        + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v63 + 2LL * (BYTE2(v2) & 0xF)) - 2)
                        + 2);
        if ( v60 && *v60 )
          goto LABEL_220;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        v61 = FindLocaleHashNode((unsigned int)v2);
        goto LABEL_221;
      }
    }
    v4 = 0;
LABEL_105:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    goto LABEL_28;
  }
  while ( *(_DWORD *)v4 != (_DWORD)v2 )
  {
    v4 = (_QWORD *)v4[11];
    if ( !v4 )
      goto LABEL_103;
  }
LABEL_28:
  if ( v4 )
  {
    if ( a2 )
      return v4[4];
    v4 = (_QWORD *)v4[13];
    if ( v4 )
      return v4[4];
  }
  if ( (_DWORD)v2 == 4096 || (v2 & 0x3FF) == 0 && (unsigned int)(v2 - 0x2000) <= 0x2C00 )
    v4 = GetCurrentNlsCache()[2];
  if ( v4 )
    return v4[4];
  return 0;
}

```

## disassembly

```asm
0x18001d7c0  push    rbp
0x18001d7c2  push    rbx
0x18001d7c3  push    rsi
0x18001d7c4  push    rdi
0x18001d7c5  push    r12
0x18001d7c7  lea     rbp, [rsp-3C0h]
0x18001d7cf  sub     rsp, 4C0h
0x18001d7d6  mov     rax, cs:__security_cookie
0x18001d7dd  xor     rax, rsp
0x18001d7e0  mov     [rbp+3E0h+var_30], rax
0x18001d7e7  mov     edi, ecx
0x18001d7e9  mov     r12d, edx
0x18001d7ec  cmp     ecx, 7Fh
0x18001d7ef  jz      loc_18001D9BC
0x18001d7f5  cmp     edi, 0C00h
0x18001d7fb  ja      loc_18001D9C8
0x18001d801  jz      loc_18001D9E5
0x18001d807  test    ecx, ecx
0x18001d809  jz      loc_18001D9E5
0x18001d80f  cmp     edi, 400h
0x18001d815  jz      loc_18001D9E5
0x18001d81b  cmp     edi, 800h
0x18001d821  jz      loc_18001DCDB
0x18001d827  mov     rbx, cs:gpSysLocHashN
0x18001d82e  test    rbx, rbx
0x18001d831  jnz     loc_18001D93C
0x18001d837  cmp     cs:BasepIsSecureProcess, bl
0x18001d83d  jnz     loc_18001D93C
0x18001d843  lea     rcx, gTblPtrsLock
0x18001d84a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001d850  cmp     cs:gpSysLocHashN, rbx
0x18001d857  jnz     loc_18001D928
0x18001d85d  mov     ebx, cs:gSystemLocale
0x18001d863  mov     rax, cs:P
0x18001d86a  mov     ecx, ebx
0x18001d86c  shr     rcx, 7
0x18001d870  xor     rcx, rbx
0x18001d873  shr     rcx, 7
0x18001d877  xor     rcx, rbx
0x18001d87a  and     ecx, 7Fh
0x18001d87d  mov     rdx, [rax+rcx*8]
0x18001d881  test    rdx, rdx
0x18001d884  jz      short loc_18001D88E
0x18001d886  cmp     [rdx], ebx
0x18001d888  jnz     loc_18001DE80
0x18001d88e  mov     cs:gpSysLocHashN, rdx
0x18001d895  test    rdx, rdx
0x18001d898  jnz     loc_18001D928
0x18001d89e  test    ebx, 0FFF00000h
0x18001d8a4  jnz     loc_18001DE28
0x18001d8aa  cmp     cs:BasepIsSecureProcess, dl
0x18001d8b0  jnz     loc_18001DE28
0x18001d8b6  mov     ecx, ebx
0x18001d8b8  call    GetWindowsLocaleData
0x18001d8bd  test    rax, rax
0x18001d8c0  jz      loc_18001DF2A
0x18001d8c6  cmp     bx, 7Fh
0x18001d8ca  jz      loc_18001DFD2
0x18001d8d0  shr     ebx, 10h
0x18001d8d3  test    bl, 0Fh
0x18001d8d6  jnz     loc_18001DDF5
0x18001d8dc  mov     ecx, [rax]
0x18001d8de  mov     rax, cs:qword_18039EC90
0x18001d8e5  add     rax, 2
0x18001d8e9  lea     rcx, [rax+rcx*2]
0x18001d8ed  xor     edx, edx
0x18001d8ef  call    MakeNamedLocaleHashNode
0x18001d8f4  mov     cs:gpSysLocHashN, rax
0x18001d8fb  test    rax, rax
0x18001d8fe  jnz     short loc_18001D928
0x18001d900  xor     edx, edx
0x18001d902  lea     rcx, aEnUs; "en-US"
0x18001d909  call    MakeNamedLocaleHashNode
0x18001d90e  mov     cs:gpSysLocHashN, rax
0x18001d915  test    rax, rax
0x18001d918  jnz     short loc_18001D928
0x18001d91a  mov     rax, cs:gpInvLocHashN
0x18001d921  mov     cs:gpSysLocHashN, rax
0x18001d928  lea     rcx, gTblPtrsLock
0x18001d92f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d935  mov     rbx, cs:gpSysLocHashN
0x18001d93c  cmp     edi, [rbx]
0x18001d93e  jnz     short loc_18001D945
0x18001d940  test    rbx, rbx
0x18001d943  jnz     short loc_18001D99B
0x18001d945  mov     rbx, cs:P
0x18001d94c  mov     rcx, rdi
0x18001d94f  shr     rcx, 7
0x18001d953  xor     rcx, rdi
0x18001d956  shr     rcx, 7
0x18001d95a  xor     rcx, rdi
0x18001d95d  and     ecx, 7Fh
0x18001d960  lea     rsi, ds:0[rcx*8]
0x18001d968  mov     rbx, [rsi+rbx]
0x18001d96c  test    rbx, rbx
0x18001d96f  jz      loc_18001DE45
0x18001d975  cmp     [rbx], edi
0x18001d977  jnz     loc_18001DE38
0x18001d97d  test    rbx, rbx
0x18001d980  jz      loc_18001DF9B
0x18001d986  test    r12d, r12d
0x18001d989  jnz     short loc_18001D99B
0x18001d98b  mov     rax, [rbx+68h]
0x18001d98f  mov     rbx, rax
0x18001d992  test    rax, rax
0x18001d995  jz      loc_18001DF9B
0x18001d99b  mov     rax, [rbx+20h]
0x18001d99f  mov     rcx, [rbp+3E0h+var_30]
0x18001d9a6  xor     rcx, rsp; StackCookie
0x18001d9a9  call    __security_check_cookie
0x18001d9ae  add     rsp, 4C0h
0x18001d9b5  pop     r12
0x18001d9b7  pop     rdi
0x18001d9b8  pop     rsi
0x18001d9b9  pop     rbx
0x18001d9ba  pop     rbp
0x18001d9bb  retn
0x18001d9bc  mov     rbx, cs:gpInvLocHashN
0x18001d9c3  jmp     loc_18001D940
0x18001d9c8  cmp     edi, 1000h
0x18001d9ce  jz      loc_18001E328
0x18001d9d4  cmp     edi, 1400h
0x18001d9da  jnz     loc_18001D827
0x18001d9e0  jmp     loc_18001E338
0x18001d9e5  mov     rax, gs:30h
0x18001d9ee  mov     [rsp+4E0h+arg_8], r14
0x18001d9f6  mov     [rsp+4E0h+arg_10], r15
0x18001d9fe  mov     ecx, [rax+179Ch]
0x18001da04  test    ecx, ecx
0x18001da06  jnz     loc_18001E128
0x18001da0c  mov     ebx, cs:gInteractiveLogonUserProcess
0x18001da12  mov     r14d, 1
0x18001da18  cmp     ebx, 0FFFFFFFFh
0x18001da1b  jz      loc_18001E246
0x18001da21  test    ebx, ebx
0x18001da23  jz      loc_18001E11E
0x18001da29  mov     rax, cs:gpServerNlsUserInfo
0x18001da30  mov     ecx, [rax+678h]
0x18001da36  mov     eax, cs:dword_1803A4270
0x18001da3c  cmp     eax, ecx
0x18001da3e  jz      short loc_18001DA48
0x18001da40  mov     cs:word_1803A4276, r14w
0x18001da48  movzx   eax, cs:word_1803A4276
0x18001da4f  test    ax, ax
0x18001da52  jz      loc_18001DCBB
0x18001da58  movzx   eax, cs:word_1803A4274
0x18001da5f  cmp     ax, 3
0x18001da63  jz      short loc_18001DA83
0x18001da65  lea     rcx, gNlsProcessCacheLock
0x18001da6c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001da72  movzx   eax, cs:word_1803A4274
0x18001da79  cmp     ax, 3
0x18001da7d  jnz     loc_18001DEFE
0x18001da83  mov     r15d, 2
0x18001da89  mov     cs:word_1803A4276, r15w
0x18001da91  cmp     ax, r14w
0x18001da95  jnz     short loc_18001DAD5
0x18001da97  xor     edx, edx; Val
0x18001da99  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x18001da9d  mov     r8d, 3B8h; Size
0x18001daa3  call    memset_0
0x18001daa8  mov     edx, 67Ch; BufferSize
0x18001daad  mov     ecx, r14d; ArgumentCount
0x18001dab0  call    cs:__imp_CsrAllocateCaptureBuffer
0x18001dab6  mov     rbx, rax
0x18001dab9  test    rax, rax
0x18001dabc  jnz     loc_18001DE92
0x18001dac2  mov     esi, 0C0000017h
0x18001dac7  cmp     cs:word_1803A4274, r14w
0x18001dacf  jz      loc_18001DEF1
0x18001dad5  mov     rax, cs:gNlsProcessLocalCache
0x18001dadc  mov     [rsp+4E0h+Handle], 0
0x18001dae5  test    rax, rax
0x18001dae8  jz      loc_18001DFE4
0x18001daee  mov     rax, cs:gNlsProcessLocalCache
0x18001daf5  mov     [rsp+4E0h+Handle], rax
0x18001dafa  mov     rbx, [rsp+4E0h+Handle]
0x18001daff  lea     rcx, word_1803A3BF8
0x18001db06  mov     rdx, rbx
0x18001db09  mov     r8d, r14d
0x18001db0c  call    NlsUpdateCacheInfo
0x18001db11  cmp     cs:word_1803A4274, 3
0x18001db19  jnz     short loc_18001DB29
0x18001db1b  test    rbx, rbx
0x18001db1e  jz      short loc_18001DB29
0x18001db20  mov     rcx, rbx; Handle
0x18001db23  call    cs:__imp_NtClose
0x18001db29  mov     eax, 0FFFFh
0x18001db2e  cmp     cs:word_1803A3BF8, ax
0x18001db35  jz      loc_18001DF1A
0x18001db3b  mov     rbx, cs:gpOneCustomHashNode
0x18001db42  lea     rcx, word_1803A3BFA
0x18001db49  xor     edx, edx
0x18001db4b  call    GetNamedLocaleHashNode
0x18001db50  xchg    rax, cs:qword_1803A3BF0
0x18001db57  test    rbx, rbx
0x18001db5a  jnz     short loc_18001DB6C
0x18001db5c  cmp     cs:gpOneCustomHashNode, rbx
0x18001db63  jz      short loc_18001DB6C
0x18001db65  mov     cs:gpOneCustomHashNode, rbx
0x18001db6c  cmp     cs:qword_1803A3BF0, 0
0x18001db74  jnz     loc_18001DC96
0x18001db7a  mov     rax, cs:gpSysLocHashN
0x18001db81  test    rax, rax
0x18001db84  jnz     loc_18001DC8F
0x18001db8a  cmp     cs:BasepIsSecureProcess, al
0x18001db90  jnz     loc_18001DC8F
0x18001db96  lea     rcx, gTblPtrsLock
0x18001db9d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001dba3  cmp     cs:gpSysLocHashN, 0
0x18001dbab  jnz     loc_18001DC7B
0x18001dbb1  mov     ebx, cs:gSystemLocale
0x18001dbb7  mov     rax, cs:P
0x18001dbbe  mov     ecx, ebx
0x18001dbc0  shr     rcx, 7
0x18001dbc4  xor     rcx, rbx
0x18001dbc7  shr     rcx, 7
0x18001dbcb  xor     rcx, rbx
0x18001dbce  and     ecx, 7Fh
0x18001dbd1  mov     rdx, [rax+rcx*8]
0x18001dbd5  test    rdx, rdx
0x18001dbd8  jz      short loc_18001DBE2
0x18001dbda  cmp     [rdx], ebx
0x18001dbdc  jnz     loc_18001E1E8
0x18001dbe2  mov     cs:gpSysLocHashN, rdx
0x18001dbe9  test    rdx, rdx
0x18001dbec  jnz     loc_18001DC7B
0x18001dbf2  test    ebx, 0FFF00000h
0x18001dbf8  jnz     loc_18001E10E
0x18001dbfe  cmp     cs:BasepIsSecureProcess, dl
0x18001dc04  jnz     loc_18001E10E
0x18001dc0a  mov     ecx, ebx
0x18001dc0c  call    GetWindowsLocaleData
0x18001dc11  test    rax, rax
0x18001dc14  jz      loc_18001E20C
0x18001dc1a  cmp     bx, 7Fh
0x18001dc1e  jz      loc_18001E289
0x18001dc24  shr     ebx, 10h
0x18001dc27  test    bl, 0Fh
0x18001dc2a  jnz     loc_18001E0DC
0x18001dc30  mov     ecx, [rax]
0x18001dc32  mov     rax, cs:qword_18039EC90
0x18001dc39  add     rax, r15
0x18001dc3c  lea     rcx, [rax+rcx*2]
0x18001dc40  xor     edx, edx
0x18001dc42  call    MakeNamedLocaleHashNode
0x18001dc47  mov     cs:gpSysLocHashN, rax
0x18001dc4e  test    rax, rax
0x18001dc51  jnz     short loc_18001DC7B
0x18001dc53  xor     edx, edx
0x18001dc55  lea     rcx, aEnUs; "en-US"
0x18001dc5c  call    MakeNamedLocaleHashNode
0x18001dc61  mov     cs:gpSysLocHashN, rax
0x18001dc68  test    rax, rax
0x18001dc6b  jnz     short loc_18001DC7B
0x18001dc6d  mov     rcx, cs:gpInvLocHashN
0x18001dc74  mov     cs:gpSysLocHashN, rcx
0x18001dc7b  lea     rcx, gTblPtrsLock
0x18001dc82  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001dc88  mov     rax, cs:gpSysLocHashN
0x18001dc8f  mov     cs:qword_1803A3BF0, rax
0x18001dc96  mov     eax, r15d
0x18001dc99  xor     edx, edx
0x18001dc9b  lock cmpxchg cs:word_1803A4276, dx
0x18001dca4  cmp     cs:word_1803A4274, 3
0x18001dcac  jz      short loc_18001DCBB
0x18001dcae  lea     rcx, gNlsProcessCacheLock
0x18001dcb5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001dcbb  lea     rbx, gNlsProcessLocalCache
0x18001dcc2  mov     rbx, [rbx+10h]
0x18001dcc6  mov     r15, [rsp+4E0h+arg_10]
0x18001dcce  mov     r14, [rsp+4E0h+arg_8]
0x18001dcd6  jmp     loc_18001D940
0x18001dcdb  mov     rbx, cs:gpSysLocHashN
0x18001dce2  test    rbx, rbx
0x18001dce5  jnz     loc_18001D99B
0x18001dceb  cmp     cs:BasepIsSecureProcess, bl
0x18001dcf1  jnz     loc_18001D940
0x18001dcf7  lea     rcx, gTblPtrsLock
0x18001dcfe  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001dd04  cmp     cs:gpSysLocHashN, rbx
0x18001dd0b  jnz     loc_18001DDDC
0x18001dd11  mov     ebx, cs:gSystemLocale
0x18001dd17  mov     rax, cs:P
0x18001dd1e  mov     ecx, ebx
0x18001dd20  shr     rcx, 7
0x18001dd24  xor     rcx, rbx
0x18001dd27  shr     rcx, 7
0x18001dd2b  xor     rcx, rbx
0x18001dd2e  and     ecx, 7Fh
0x18001dd31  mov     rdx, [rax+rcx*8]
0x18001dd35  test    rdx, rdx
0x18001dd38  jz      short loc_18001DD42
0x18001dd3a  cmp     [rdx], ebx
0x18001dd3c  jnz     loc_18001E1B0
0x18001dd42  mov     cs:gpSysLocHashN, rdx
0x18001dd49  test    rdx, rdx
0x18001dd4c  jnz     loc_18001DDDC
0x18001dd52  test    ebx, 0FFF00000h
0x18001dd58  jnz     loc_18001DF8B
  ... truncated ...
```
