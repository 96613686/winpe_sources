# GetStringTypeExW

- ea: `0x180019090`
- end: `0x18001a1b2`
- name: `GetStringTypeExW`
- size: `4386`
- prototype: `BOOL __stdcall(LCID Locale, DWORD dwInfoType, LPCWCH lpSrcStr, int cchSrc, LPWORD lpCharType)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x1800123e0`
- `0x180012f10`
- `0x180018040`
- `0x180019090`
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

- `ntdll!RtlInitUnicodeString` at `0x180019fba`
- `ntdll!RtlInitUnicodeString` at `0x180019fba`
- `ntdll!NtOpenKey` at `0x18001a001`
- `ntdll!NtOpenKey` at `0x18001a001`
- `ntdll!NtCreateKey` at `0x18001a03a`
- `ntdll!NtCreateKey` at `0x18001a03a`
- `ntdll!RtlLcidToLocaleName` at `0x180019dff`
- `ntdll!RtlLcidToLocaleName` at `0x180019dff`
- `ntdll!RtlOpenCurrentUser` at `0x180019a6d`
- `ntdll!RtlOpenCurrentUser` at `0x180019a6d`
- `ntdll!CsrClientCallServer` at `0x1800198f6`
- `ntdll!CsrClientCallServer` at `0x1800198f6`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800198d6`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800198d6`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001991c`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001991c`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800194e5`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800194e5`
- `ntdll!NtClose` at `0x18001955f`
- `ntdll!NtClose` at `0x180019b09`
- `ntdll!NtClose` at `0x18001a04c`
- `ntdll!NtClose` at `0x18001a087`
- `ntdll!NtClose` at `0x18001955f`
- `ntdll!NtClose` at `0x180019b09`
- `ntdll!NtClose` at `0x18001a04c`
- `ntdll!NtClose` at `0x18001a087`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019136`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800194a1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800195d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019731`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019881`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019136`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800194a1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800195d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019731`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019881`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001921d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800196bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800196f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019818`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800198aa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a108`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a18d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001921d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800196bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800196f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019818`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800198aa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a108`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a18d`
- `ntdll!RtlAllocateHeap` at `0x180019f00`
- `ntdll!RtlAllocateHeap` at `0x180019f5f`
- `ntdll!RtlAllocateHeap` at `0x180019f00`
- `ntdll!RtlAllocateHeap` at `0x180019f5f`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall GetStringTypeExW(LCID Locale, DWORD dwInfoType, LPCWCH lpSrcStr, int cchSrc, LPWORD lpCharType)
{
  unsigned __int64 v7; // rsi
  DWORD v8; // edi
  _DWORD *v9; // rax
  DWORD v10; // edi
  __int64 k; // rdx
  unsigned int *v12; // rax
  __int64 v13; // r8
  DWORD v14; // edi
  const WCHAR *v15; // rcx
  __int64 v16; // rax
  BOOL v17; // r12d
  __int64 v18; // r15
  __int64 v19; // rdi
  HANDLE v20; // rcx
  LPCWCH m; // rbx
  __int64 n; // r10
  __int64 v23; // r9
  unsigned __int64 v24; // rax
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v28; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v30; // rdi
  NTSTATUS v31; // r15d
  HANDLE v32; // rdi
  __int64 v33; // rdi
  __int64 v34; // rax
  DWORD v35; // edi
  __int64 j; // rdx
  unsigned int *v37; // rax
  __int64 v38; // r8
  DWORD v39; // edi
  const WCHAR *v40; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  HANDLE *NlsCache; // rdi
  DWORD v43; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v46; // r8
  DWORD v47; // edi
  const WCHAR *v48; // rcx
  __int64 NamedLocaleHashNode; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  int GlobalizationUserModelType; // eax
  int v53; // eax
  __int64 v54; // rcx
  WCHAR *v55; // rax
  __int64 v56; // r9
  const WCHAR *v57; // rdx
  WCHAR *v58; // r8
  __int64 v59; // rcx
  WCHAR *v60; // rcx
  __int64 v61; // rdx
  int v62; // ecx
  int v63; // r12d
  int v64; // eax
  HANDLE *v65; // rdi
  __int64 ii; // r10
  __int64 v67; // r9
  unsigned __int64 v68; // rax
  __int64 jj; // r10
  __int64 v70; // r9
  unsigned __int64 v71; // rax
  HANDLE *Heap; // rax
  HANDLE *v73; // rax
  NTSTATUS v74; // edi
  HANDLE v75; // rcx
  void *v76; // rdi
  unsigned int *v77; // rcx
  __int64 v78; // r8
  const WCHAR *v79; // rcx
  __int64 LocaleHashNode; // rax
  __int64 v81; // rax
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v83; // [rsp+48h] [rbp-B8h]
  ULONG Disposition; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v86; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v91; // [rsp+F8h] [rbp-8h]

  v83 = dwInfoType;
  v7 = Locale;
  v8 = dwInfoType;
  if ( Locale == 127 )
  {
    v9 = (_DWORD *)gpInvLocHashN;
LABEL_27:
    v17 = 1;
    goto LABEL_28;
  }
  if ( Locale <= 0xC00 )
  {
    if ( Locale != 3072 && Locale && Locale != 1024 )
    {
      if ( Locale != 2048 )
        goto LABEL_7;
      v9 = (_DWORD *)gpSysLocHashN;
      if ( gpSysLocHashN || BasepIsSecureProcess )
        goto LABEL_27;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_126;
      v43 = gSystemLocale;
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
        goto LABEL_126;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_154;
      WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( WindowsLocaleData )
      {
        if ( (_WORD)v43 != 127 )
        {
          v47 = HIWORD(v43);
          if ( (v47 & 0xF) == 0 )
          {
            v48 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_122:
            NamedLocaleHashNode = MakeNamedLocaleHashNode(v48, 0);
            goto LABEL_123;
          }
          v51 = WindowsLocaleData[54];
          v48 = (const WCHAR *)qword_18039EC90;
          if ( (_DWORD)v51 )
            v48 = (const WCHAR *)(qword_18039EC90
                                + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v51 + 2LL * (v47 & 0xF)) - 2)
                                + 2);
          if ( v48 && *v48 )
            goto LABEL_122;
LABEL_154:
          gpSysLocHashN = 0;
          goto LABEL_124;
        }
        NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v43, v46, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_154;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          NamedLocaleHashNode = FindLocaleHashNode(v43);
        }
        else
        {
          NamedLocaleHashNode = 0;
        }
      }
LABEL_123:
      gpSysLocHashN = NamedLocaleHashNode;
      if ( NamedLocaleHashNode )
      {
LABEL_126:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v9 = (_DWORD *)gpSysLocHashN;
        goto LABEL_27;
      }
LABEL_124:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_126;
    }
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( !(_DWORD)IsImpersonating )
    {
      IsInteractiveUserProcess = gInteractiveLogonUserProcess;
      if ( gInteractiveLogonUserProcess == -1 )
        IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, dwInfoType, lpSrcStr);
      if ( IsInteractiveUserProcess )
      {
        if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
          word_1803A4276 = 1;
        if ( !word_1803A4276 )
          goto LABEL_107;
        v28 = word_1803A4274;
        if ( word_1803A4274 != 3 )
        {
          RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
          v28 = word_1803A4274;
          if ( word_1803A4274 != 3 )
          {
            if ( !word_1803A4276 )
              goto LABEL_106;
            v28 = word_1803A4274;
          }
        }
        word_1803A4276 = 2;
        if ( v28 == 1 )
        {
          memset_0(ApiMessage, 0, 0x3B8u);
          CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
          v30 = CaptureBuffer;
          if ( CaptureBuffer )
          {
            CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
            v91 = 1660;
            v31 = CsrClientCallServer(ApiMessage, v30, (CSR_API_NUMBER)0x1001B, 0x10u);
            if ( v31 >= 0 )
              memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
            CsrFreeCaptureBuffer(v30);
          }
          else
          {
            v31 = -1073741801;
          }
          if ( word_1803A4274 == 1 && v31 >= 0 )
          {
LABEL_82:
            if ( word_1803A3BF8 == -1 )
            {
              qword_1803A3BF0 = 0;
            }
            else
            {
              v33 = gpOneCustomHashNode;
              _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
              if ( !v33 && gpOneCustomHashNode )
                gpOneCustomHashNode = 0;
              if ( qword_1803A3BF0 )
              {
LABEL_105:
                _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
                if ( word_1803A4274 == 3 )
                {
LABEL_107:
                  NlsCache = &gNlsProcessLocalCache;
LABEL_108:
                  v17 = 1;
LABEL_109:
                  v9 = NlsCache[2];
                  goto LABEL_28;
                }
LABEL_106:
                RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
                goto LABEL_107;
              }
            }
            v34 = gpSysLocHashN;
            if ( gpSysLocHashN || BasepIsSecureProcess )
            {
LABEL_104:
              qword_1803A3BF0 = v34;
              goto LABEL_105;
            }
            RtlAcquireSRWLockExclusive(&gTblPtrsLock);
            if ( gpSysLocHashN )
              goto LABEL_103;
            v35 = gSystemLocale;
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
              goto LABEL_103;
            if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
              goto LABEL_183;
            v37 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
            if ( v37 )
            {
              if ( (_WORD)v35 != 127 )
              {
                v39 = HIWORD(v35);
                if ( (v39 & 0xF) == 0 )
                {
                  v40 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v37);
LABEL_99:
                  LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v40, 0);
                  goto LABEL_100;
                }
                v61 = v37[54];
                v40 = (const WCHAR *)qword_18039EC90;
                if ( (_DWORD)v61 )
                  v40 = (const WCHAR *)(qword_18039EC90
                                      + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v61 + 2LL * (v39 & 0xF)) - 2)
                                      + 2);
                if ( v40 && *v40 )
                  goto LABEL_99;
LABEL_183:
                gpSysLocHashN = 0;
LABEL_101:
                gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
                if ( !gpSysLocHashN )
                  gpSysLocHashN = gpInvLocHashN;
                goto LABEL_103;
              }
              LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v37, v35, v38, 0);
            }
            else
            {
              if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
                goto LABEL_183;
              if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
                || (unsigned int)CreateTransientLocales() )
              {
                LocHashNodeFromSystemLocale = FindLocaleHashNode(v35);
              }
              else
              {
                LocHashNodeFromSystemLocale = 0;
              }
            }
LABEL_100:
            gpSysLocHashN = LocHashNodeFromSystemLocale;
            if ( !LocHashNodeFromSystemLocale )
              goto LABEL_101;
LABEL_103:
            RtlReleaseSRWLockExclusive(&gTblPtrsLock);
            v34 = gpSysLocHashN;
            goto LABEL_104;
          }
        }
        Handle = 0;
        if ( gNlsProcessLocalCache )
        {
          Handle = gNlsProcessLocalCache;
LABEL_79:
          v32 = Handle;
          NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
          if ( word_1803A4274 == 3 && v32 )
            NtClose(v32);
          goto LABEL_82;
        }
        KeyHandle[0] = 0;
        Disposition = 0;
        memset(&ObjectAttributes, 0, 44);
        DestinationString = 0;
        GlobalizationUserModelType = GetGlobalizationUserModelType(0, *(_QWORD *)&dwInfoType, lpSrcStr);
        if ( GlobalizationUserModelType == 1 )
        {
          v53 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
        }
        else
        {
          v64 = GlobalizationUserModelType - 2;
          if ( v64 )
          {
            if ( v64 != 1 )
            {
LABEL_178:
              SetLastError_0(0x3F1u);
              goto LABEL_79;
            }
            v86 = 0;
            v53 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v86);
          }
          else
          {
            v53 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
          }
        }
        if ( v53 >= 0 )
        {
          ApiMessage[0] = 0;
          v54 = 512;
          v55 = ApiMessage;
          do
          {
            if ( !*v55 )
              break;
            ++v55;
            --v54;
          }
          while ( v54 );
          if ( !v54 )
            goto LABEL_176;
          v56 = v54;
          v57 = L"Control Panel\\International";
          v58 = &ApiMessage[512 - v54];
          v59 = 2147483646;
          do
          {
            if ( !v59 )
              break;
            if ( !*v57 )
              break;
            *v58++ = *v57++;
            --v59;
            --v56;
          }
          while ( v56 );
          v60 = v58 - 1;
          if ( v56 )
            v60 = v58;
          *v60 = 0;
          if ( v56 )
          {
            RtlInitUnicodeString(&DestinationString, ApiMessage);
            ObjectAttributes.RootDirectory = KeyHandle[0];
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            Disposition = 0;
            v74 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
            if ( v74 < 0 )
              v74 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
            if ( KeyHandle[0] )
              NtClose(KeyHandle[0]);
            if ( v74 >= 0 )
            {
              v75 = Handle;
            }
            else
            {
              v75 = 0;
              Handle = 0;
            }
            if ( v74 >= 0 )
            {
              v76 = (void *)_InterlockedCompareExchange64(
                              (volatile signed __int64 *)&gNlsProcessLocalCache,
                              (signed __int64)v75,
                              0);
              if ( v76 )
              {
                if ( Handle )
                  NtClose(Handle);
                Handle = v76;
              }
              goto LABEL_79;
            }
          }
          else
          {
LABEL_176:
            if ( KeyHandle[0] )
              NtClose(KeyHandle[0]);
          }
        }
        goto LABEL_178;
      }
      NlsCheckStaleCache();
      goto LABEL_185;
    }
    NlsCache = 0;
    v62 = IsImpersonating - 1;
    if ( v62 )
    {
      if ( v62 != 1 )
        goto LABEL_186;
      if ( BasepIsSecureProcess )
      {
LABEL_185:
        NlsCache = &gNlsProcessLocalCache;
LABEL_186:
        v17 = 1;
        goto LABEL_109;
      }
      v63 = 0;
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
          v63 = 1;
        }
        else
        {
          NlsCache = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = NlsCache;
      }
      if ( NlsCache == &gNlsProcessLocalCache || !v63 && *((_WORD *)NlsCache + 843) != 1 )
        goto LABEL_108;
      v17 = 1;
      *((_WORD *)NlsCache + 843) = 1;
      UpdateNlsInfoCache((__int64)NlsCache, 0, (__int64)lpSrcStr);
      v9 = NlsCache[2];
    }
    else
    {
      if ( BasepIsSecureProcess )
      {
        v65 = &gNlsProcessLocalCache;
      }
      else
      {
        v65 = (HANDLE *)NtCurrentTeb()->NlsCache;
        if ( !v65 )
        {
          v73 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
          v65 = v73;
          if ( v73 )
          {
            *v73 = 0;
            v73[1] = 0;
            v73[2] = 0;
            *((_WORD *)v73 + 842) = 3;
            *((_WORD *)v73 + 843) = 1;
          }
          else
          {
            v65 = &gNlsProcessLocalCache;
          }
          NtCurrentTeb()->NlsCache = v65;
        }
        if ( v65 != &gNlsProcessLocalCache )
        {
          *((_WORD *)v65 + 843) = 1;
          UpdateNlsInfoCache((__int64)v65, 0, (__int64)lpSrcStr);
        }
      }
      NtCurrentTeb()->IsImpersonating = 2;
      v17 = 1;
      v9 = v65[2];
    }
LABEL_28:
    if ( v9 )
    {
LABEL_33:
      v8 = v83;
      goto LABEL_34;
    }
LABEL_29:
    v18 = 8LL * (((unsigned __int8)v7 ^ (unsigned __int8)((v7 ^ (v7 >> 7)) >> 7)) & 0x7F);
    v19 = *(_QWORD *)((char *)P + v18);
    if ( v19 )
    {
      while ( *(_DWORD *)v19 != (_DWORD)v7 )
      {
        v19 = *(_QWORD *)(v19 + 88);
        if ( !v19 )
          goto LABEL_133;
      }
LABEL_31:
      if ( v19 )
      {
        v20 = *(HANDLE *)(v19 + 104);
        if ( v20 )
          goto LABEL_33;
      }
      else
      {
        v20 = 0;
      }
      if ( (_DWORD)v7 == 4096 || (v7 & 0x3FF) == 0 && (unsigned int)(v7 - 0x2000) <= 0x2C00 )
        v20 = GetCurrentNlsCache()[2];
      if ( !v20 )
      {
        SetLastError_0(0x57u);
        return 0;
      }
      goto LABEL_33;
    }
LABEL_133:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v19 = *(_QWORD *)((char *)P + v18);
    if ( v19 )
    {
      while ( *(_DWORD *)v19 != (_DWORD)v7 )
      {
        v19 = *(_QWORD *)(v19 + 88);
        if ( !v19 )
          goto LABEL_254;
      }
      goto LABEL_135;
    }
LABEL_254:
    if ( (v7 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v77 = (unsigned int *)GetWindowsLocaleData((unsigned int)v7);
      if ( v77 )
      {
        if ( (_WORD)v7 == 127 )
        {
          v19 = MakeLocHashNodeFromSystemLocale(v77, (unsigned int)v7, v78, 0);
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_31;
        }
        if ( (v7 & 0xF0000) == 0 )
        {
          v79 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v77);
LABEL_260:
          LocaleHashNode = MakeNamedLocaleHashNode(v79, 0);
LABEL_261:
          v19 = LocaleHashNode;
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_31;
        }
        v81 = v77[54];
        v79 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v81 )
          v79 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v81 + 2LL * (BYTE2(v7) & 0xF)) - 2)
                              + 2);
        if ( v79 && *v79 )
          goto LABEL_260;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        LocaleHashNode = FindLocaleHashNode((unsigned int)v7);
        goto LABEL_261;
      }
    }
    v19 = 0;
LABEL_135:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    goto LABEL_31;
  }
  if ( Locale == 4096 )
  {
    v9 = (_DWORD *)gpOneCustomHashNode;
    if ( gpOneCustomHashNode )
      goto LABEL_27;
  }
  else if ( Locale != 5120 )
  {
    goto LABEL_7;
  }
  KeyHandle[0] = (HANDLE)11141120;
  KeyHandle[1] = ApiMessage;
  if ( (int)RtlLcidToLocaleName(Locale, KeyHandle, 0, 0) < 0 || !GetNamedLocaleHashNode(KeyHandle[1], 0) )
  {
LABEL_7:
    v9 = (_DWORD *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_24:
      v17 = 1;
      if ( (_DWORD)v7 != *v9 )
        goto LABEL_29;
      goto LABEL_28;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v10 = gSystemLocale;
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
      goto LABEL_131;
    v12 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v12 )
    {
      if ( (_WORD)v10 != 127 )
      {
        v14 = HIWORD(v10);
        if ( (v14 & 0xF) == 0 )
        {
          v15 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v12);
LABEL_19:
          v16 = MakeNamedLocaleHashNode(v15, 0);
          goto LABEL_20;
        }
        v50 = v12[54];
        v15 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v50 )
          v15 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v50 + 2LL * (v14 & 0xF)) - 2)
                              + 2);
        if ( v15 && *v15 )
          goto LABEL_19;
LABEL_131:
        gpSysLocHashN = 0;
LABEL_21:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_23;
      }
      v16 = MakeLocHashNodeFromSystemLocale(v12, v10, v13, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_131;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        v16 = FindLocaleHashNode(v10);
      }
      else
      {
        v16 = 0;
      }
    }
LABEL_20:
    gpSysLocHashN = v16;
    if ( !v16 )
      goto LABEL_21;
LABEL_23:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    v9 = (_DWORD *)gpSysLocHashN;
    goto LABEL_24;
  }
  v17 = 1;
LABEL_34:
  if ( lpSrcStr && cchSrc && lpCharType && lpSrcStr != lpCharType )
  {
    if ( cchSrc <= -1 )
    {
      for ( m = lpSrcStr; *m; ++m )
      {
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
      }
      cchSrc = m - lpSrcStr + 1;
    }
    switch ( v8 )
    {
      case 1u:
        for ( n = 0;
              (int)n < cchSrc;
              lpCharType[v23] = *(_WORD *)(qword_18039ECA0
                                         + 6LL
                                         * *(unsigned __int8 *)((v24 & 0xF)
                                                              + qword_18039ECA8
                                                              + *(unsigned __int16 *)(qword_18039ECA8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v24 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_18039ECA8 + 2 * (v24 >> 8)) >> 1))))) )
        {
          v23 = n;
          v24 = lpSrcStr[n];
          n = (unsigned int)(n + 1);
        }
        break;
      case 2u:
        for ( ii = 0;
              (int)ii < cchSrc;
              lpCharType[v67] = *(_WORD *)(qword_18039ECA0
                                         + 6LL
                                         * *(unsigned __int8 *)((v68 & 0xF)
                                                              + qword_18039ECA8
                                                              + *(unsigned __int16 *)(qword_18039ECA8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v68 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_18039ECA8 + 2 * (v68 >> 8)) >> 1))))
                                         + 2) )
        {
          v67 = ii;
          v68 = lpSrcStr[ii];
          ii = (unsigned int)(ii + 1);
        }
        break;
      case 4u:
        for ( jj = 0;
              (int)jj < cchSrc;
              lpCharType[v70] = *(_WORD *)(qword_18039ECA0
                                         + 6LL
                                         * *(unsigned __int8 *)((v71 & 0xF)
                                                              + qword_18039ECA8
                                                              + *(unsigned __int16 *)(qword_18039ECA8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v71 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_18039ECA8 + 2 * (v71 >> 8)) >> 1))))
                                         + 4) )
        {
          v70 = jj;
          v71 = lpSrcStr[jj];
          jj = (unsigned int)(jj + 1);
        }
        break;
      default:
        SetLastError_0(0x3ECu);
        return 0;
    }
  }
  else
  {
    SetLastError_0(0x57u);
    return 0;
  }
  return v17;
}

```

## disassembly

```asm
0x180019090  push    rbp
0x180019092  push    rbx
0x180019093  push    rsi
0x180019094  push    rdi
0x180019095  push    r12
0x180019097  push    r13
0x180019099  push    r14
0x18001909b  push    r15
0x18001909d  lea     rbp, [rsp-3C8h]
0x1800190a5  sub     rsp, 4C8h
0x1800190ac  mov     rax, cs:__security_cookie
0x1800190b3  xor     rax, rsp
0x1800190b6  mov     [rbp+400h+var_50], rax
0x1800190bd  mov     r13, [rbp+400h+lpCharType]
0x1800190c4  mov     ebx, r9d
0x1800190c7  mov     [rsp+500h+var_4B8], edx
0x1800190cb  mov     r14, r8
0x1800190ce  mov     esi, ecx
0x1800190d0  mov     edi, edx
0x1800190d2  mov     r15d, 1
0x1800190d8  cmp     ecx, 7Fh
0x1800190db  jz      loc_180019233
0x1800190e1  cmp     esi, 0C00h
0x1800190e7  ja      loc_180019413
0x1800190ed  jz      loc_180019430
0x1800190f3  test    ecx, ecx
0x1800190f5  jz      loc_180019430
0x1800190fb  cmp     esi, 400h
0x180019101  jz      loc_180019430
0x180019107  cmp     esi, 800h
0x18001910d  jz      loc_18001970E
0x180019113  mov     rax, cs:gpSysLocHashN
0x18001911a  test    rax, rax
0x18001911d  jnz     loc_18001922A
0x180019123  cmp     cs:BasepIsSecureProcess, al
0x180019129  jnz     loc_18001922A
0x18001912f  lea     rcx, gTblPtrsLock
0x180019136  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001913c  cmp     cs:gpSysLocHashN, 0
0x180019144  jnz     loc_180019216
0x18001914a  mov     edi, cs:gSystemLocale
0x180019150  mov     rax, cs:P
0x180019157  mov     ecx, edi
0x180019159  shr     rcx, 7
0x18001915d  xor     rcx, rdi
0x180019160  shr     rcx, 7
0x180019164  xor     rcx, rdi
0x180019167  and     ecx, 7Fh
0x18001916a  mov     rdx, [rax+rcx*8]
0x18001916e  test    rdx, rdx
0x180019171  jz      short loc_18001917B
0x180019173  cmp     [rdx], edi
0x180019175  jnz     loc_1800198B5
0x18001917b  mov     cs:gpSysLocHashN, rdx
0x180019182  test    rdx, rdx
0x180019185  jnz     loc_180019216
0x18001918b  test    edi, 0FFF00000h
0x180019191  jnz     loc_18001985D
0x180019197  cmp     cs:BasepIsSecureProcess, dl
0x18001919d  jnz     loc_18001985D
0x1800191a3  mov     ecx, edi
0x1800191a5  call    GetWindowsLocaleData
0x1800191aa  test    rax, rax
0x1800191ad  jz      loc_180019961
0x1800191b3  cmp     di, 7Fh
0x1800191b7  jz      loc_1800199D2
0x1800191bd  shr     edi, 10h
0x1800191c0  test    dil, 0Fh
0x1800191c4  jnz     loc_18001982A
0x1800191ca  mov     ecx, [rax]
0x1800191cc  mov     rax, cs:qword_18039EC90
0x1800191d3  add     rax, 2
0x1800191d7  lea     rcx, [rax+rcx*2]
0x1800191db  xor     edx, edx
0x1800191dd  call    MakeNamedLocaleHashNode
0x1800191e2  mov     cs:gpSysLocHashN, rax
0x1800191e9  test    rax, rax
0x1800191ec  jnz     short loc_180019216
0x1800191ee  xor     edx, edx
0x1800191f0  lea     rcx, aEnUs; "en-US"
0x1800191f7  call    MakeNamedLocaleHashNode
0x1800191fc  mov     cs:gpSysLocHashN, rax
0x180019203  test    rax, rax
0x180019206  jnz     short loc_180019216
0x180019208  mov     rax, cs:gpInvLocHashN
0x18001920f  mov     cs:gpSysLocHashN, rax
0x180019216  lea     rcx, gTblPtrsLock
0x18001921d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019223  mov     rax, cs:gpSysLocHashN
0x18001922a  mov     r12d, r15d
0x18001922d  cmp     esi, [rax]
0x18001922f  jnz     short loc_180019242
0x180019231  jmp     short loc_18001923D
0x180019233  mov     rax, cs:gpInvLocHashN
0x18001923a  mov     r12d, r15d
0x18001923d  test    rax, rax
0x180019240  jnz     short loc_180019290
0x180019242  mov     rax, cs:P
0x180019249  mov     rcx, rsi
0x18001924c  shr     rcx, 7
0x180019250  xor     rcx, rsi
0x180019253  shr     rcx, 7
0x180019257  xor     rcx, rsi
0x18001925a  and     ecx, 7Fh
0x18001925d  lea     r15, ds:0[rcx*8]
0x180019265  mov     rdi, [r15+rax]
0x180019269  test    rdi, rdi
0x18001926c  jz      loc_18001987A
0x180019272  cmp     [rdi], esi
0x180019274  jnz     loc_18001986D
0x18001927a  test    rdi, rdi
0x18001927d  jz      loc_1800199E4
0x180019283  mov     rcx, [rdi+68h]
0x180019287  test    rcx, rcx
0x18001928a  jz      loc_1800199E6
0x180019290  mov     edi, [rsp+500h+var_4B8]
0x180019294  test    r14, r14
0x180019297  jz      loc_180019C34
0x18001929d  test    ebx, ebx
0x18001929f  jz      loc_180019C34
0x1800192a5  test    r13, r13
0x1800192a8  jz      loc_180019C34
0x1800192ae  cmp     r14, r13
0x1800192b1  jz      loc_180019C34
0x1800192b7  cmp     ebx, 0FFFFFFFFh
0x1800192ba  jg      loc_180019388
0x1800192c0  cmp     word ptr [r14], 0
0x1800192c5  mov     rbx, r14
0x1800192c8  jz      loc_180019380
0x1800192ce  xchg    ax, ax
0x1800192d0  add     rbx, 2
0x1800192d4  cmp     word ptr [rbx], 0
0x1800192d8  jz      loc_180019380
0x1800192de  add     rbx, 2
0x1800192e2  cmp     word ptr [rbx], 0
0x1800192e6  jz      loc_180019380
0x1800192ec  add     rbx, 2
0x1800192f0  cmp     word ptr [rbx], 0
0x1800192f4  jz      loc_180019380
0x1800192fa  add     rbx, 2
0x1800192fe  cmp     word ptr [rbx], 0
0x180019302  jz      short loc_180019380
0x180019304  add     rbx, 2
0x180019308  cmp     word ptr [rbx], 0
0x18001930c  jz      short loc_180019380
0x18001930e  add     rbx, 2
0x180019312  cmp     word ptr [rbx], 0
0x180019316  jz      short loc_180019380
0x180019318  add     rbx, 2
0x18001931c  cmp     word ptr [rbx], 0
0x180019320  jz      short loc_180019380
0x180019322  add     rbx, 2
0x180019326  cmp     word ptr [rbx], 0
0x18001932a  jz      short loc_180019380
0x18001932c  add     rbx, 2
0x180019330  cmp     word ptr [rbx], 0
0x180019334  jz      short loc_180019380
0x180019336  add     rbx, 2
0x18001933a  cmp     word ptr [rbx], 0
0x18001933e  jz      short loc_180019380
0x180019340  add     rbx, 2
0x180019344  cmp     word ptr [rbx], 0
0x180019348  jz      short loc_180019380
0x18001934a  add     rbx, 2
0x18001934e  cmp     word ptr [rbx], 0
0x180019352  jz      short loc_180019380
0x180019354  add     rbx, 2
0x180019358  cmp     word ptr [rbx], 0
0x18001935c  jz      short loc_180019380
0x18001935e  add     rbx, 2
0x180019362  cmp     word ptr [rbx], 0
0x180019366  jz      short loc_180019380
0x180019368  add     rbx, 2
0x18001936c  cmp     word ptr [rbx], 0
0x180019370  jz      short loc_180019380
0x180019372  add     rbx, 2
0x180019376  cmp     word ptr [rbx], 0
0x18001937a  jnz     loc_1800192D0
0x180019380  sub     rbx, r14
0x180019383  sar     rbx, 1
0x180019386  inc     ebx
0x180019388  cmp     edi, 1
0x18001938b  jnz     loc_180019D4A
0x180019391  xor     r10d, r10d
0x180019394  test    ebx, ebx
0x180019396  jle     short loc_1800193ED
0x180019398  mov     rdx, cs:qword_18039ECA8
0x18001939f  lea     r9, [r10+r10]
0x1800193a3  movzx   eax, word ptr [r14+r9]
0x1800193a8  inc     r10d
0x1800193ab  movzx   r8d, al
0x1800193af  shr     rax, 8
0x1800193b3  movzx   ecx, word ptr [rdx+rax*2]
0x1800193b7  mov     eax, r8d
0x1800193ba  shr     rax, 4
0x1800193be  and     r8d, 0Fh
0x1800193c2  shr     rcx, 1
0x1800193c5  add     rcx, rax
0x1800193c8  movzx   eax, word ptr [rdx+rcx*2]
0x1800193cc  add     rax, rdx
0x1800193cf  movzx   ecx, byte ptr [r8+rax]
0x1800193d4  mov     rax, cs:qword_18039ECA0
0x1800193db  lea     rcx, [rcx+rcx*2]
0x1800193df  movzx   ecx, word ptr [rax+rcx*2]
0x1800193e3  mov     [r9+r13], cx
0x1800193e8  cmp     r10d, ebx
0x1800193eb  jl      short loc_180019398
0x1800193ed  mov     eax, r12d
0x1800193f0  mov     rcx, [rbp+400h+var_50]
0x1800193f7  xor     rcx, rsp; StackCookie
0x1800193fa  call    __security_check_cookie
0x1800193ff  add     rsp, 4C8h
0x180019406  pop     r15
0x180019408  pop     r14
0x18001940a  pop     r13
0x18001940c  pop     r12
0x18001940e  pop     rdi
0x18001940f  pop     rsi
0x180019410  pop     rbx
0x180019411  pop     rbp
0x180019412  retn
0x180019413  cmp     esi, 1000h
0x180019419  jz      loc_180019DC7
0x18001941f  cmp     esi, 1400h
0x180019425  jnz     loc_180019113
0x18001942b  jmp     loc_180019DD7
0x180019430  mov     rax, gs:30h
0x180019439  mov     ecx, [rax+179Ch]
0x18001943f  test    ecx, ecx
0x180019441  jnz     loc_180019B74
0x180019447  mov     eax, cs:gInteractiveLogonUserProcess
0x18001944d  cmp     eax, 0FFFFFFFFh
0x180019450  jz      loc_180019CA4
0x180019456  test    eax, eax
0x180019458  jz      loc_180019B60
0x18001945e  mov     rax, cs:gpServerNlsUserInfo
0x180019465  mov     ecx, [rax+678h]
0x18001946b  mov     eax, cs:dword_1803A4270
0x180019471  cmp     eax, ecx
0x180019473  jz      short loc_18001947D
0x180019475  mov     cs:word_1803A4276, r15w
0x18001947d  movzx   eax, cs:word_1803A4276
0x180019484  test    ax, ax
0x180019487  jz      loc_1800196F8
0x18001948d  movzx   eax, cs:word_1803A4274
0x180019494  cmp     ax, 3
0x180019498  jz      short loc_1800194B8
0x18001949a  lea     rcx, gNlsProcessCacheLock
0x1800194a1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800194a7  movzx   eax, cs:word_1803A4274
0x1800194ae  cmp     ax, 3
0x1800194b2  jnz     loc_180019935
0x1800194b8  mov     r12d, 2
0x1800194be  mov     cs:word_1803A4276, r12w
0x1800194c6  cmp     ax, r15w
0x1800194ca  jnz     short loc_180019511
0x1800194cc  xor     edx, edx; Val
0x1800194ce  lea     rcx, [rbp+400h+ApiMessage]; void *
0x1800194d2  mov     r8d, 3B8h; Size
0x1800194d8  call    memset_0
0x1800194dd  mov     edx, 67Ch; BufferSize
0x1800194e2  mov     ecx, r15d; ArgumentCount
0x1800194e5  call    cs:__imp_CsrAllocateCaptureBuffer
0x1800194eb  mov     rdi, rax
0x1800194ee  test    rax, rax
0x1800194f1  jnz     loc_1800198C7
0x1800194f7  mov     r15d, 0C0000017h
0x1800194fd  cmp     cs:word_1803A4274, 1
0x180019505  jz      loc_180019927
0x18001950b  mov     r15d, 1
0x180019511  mov     rax, cs:gNlsProcessLocalCache
0x180019518  mov     [rsp+500h+Handle], 0
0x180019521  test    rax, rax
0x180019524  jz      loc_180019A27
0x18001952a  mov     rax, cs:gNlsProcessLocalCache
0x180019531  mov     [rsp+500h+Handle], rax
0x180019536  mov     rdi, [rsp+500h+Handle]
0x18001953b  lea     rcx, word_1803A3BF8
0x180019542  mov     rdx, rdi
0x180019545  mov     r8d, r15d
0x180019548  call    NlsUpdateCacheInfo
0x18001954d  cmp     cs:word_1803A4274, 3
0x180019555  jnz     short loc_180019565
0x180019557  test    rdi, rdi
0x18001955a  jz      short loc_180019565
0x18001955c  mov     rcx, rdi; Handle
0x18001955f  call    cs:__imp_NtClose
0x180019565  mov     eax, 0FFFFh
0x18001956a  cmp     cs:word_1803A3BF8, ax
0x180019571  jz      loc_180019951
0x180019577  mov     rdi, cs:gpOneCustomHashNode
0x18001957e  lea     rcx, word_1803A3BFA
0x180019585  xor     edx, edx
0x180019587  call    GetNamedLocaleHashNode
0x18001958c  xchg    rax, cs:qword_1803A3BF0
0x180019593  test    rdi, rdi
0x180019596  jnz     short loc_1800195A8
0x180019598  cmp     cs:gpOneCustomHashNode, rdi
0x18001959f  jz      short loc_1800195A8
0x1800195a1  mov     cs:gpOneCustomHashNode, rdi
  ... truncated ...
```
