# CheckSpecialLocales

- ea: `0x18001b3a0`
- end: `0x18001c964`
- name: `CheckSpecialLocales`
- size: `5572`
- prototype: ``
- caller_count: `20`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bb00`
- `0x180014ad0`
- `0x180015820`
- `0x180015e20`
- `0x18001ea50`
- `0x18001eec0`
- `0x180037730`
- `0x180038db0`
- `0x18003abc0`
- `0x18003b110`
- `0x18003b620`
- `0x18003cde0`
- `0x18003d2c0`
- `0x18003d8e0`
- `0x18003db80`
- `0x18003de00`
- `0x18003e5d0`
- `0x18003fd00`
- `0x180040000`
- `0x1800b66a0`

## callees

- `0x180010080`
- `0x180011b90`
- `0x180012dc0`
- `0x180012f10`
- `0x1800134a0`
- `0x18001a1b8`
- `0x18001b3a0`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x180071550`
- `0x18007217c`
- `0x1800fa3bc`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001c57c`
- `ntdll!RtlInitUnicodeString` at `0x18001c653`
- `ntdll!RtlInitUnicodeString` at `0x18001c798`
- `ntdll!RtlInitUnicodeString` at `0x18001c57c`
- `ntdll!RtlInitUnicodeString` at `0x18001c653`
- `ntdll!RtlInitUnicodeString` at `0x18001c798`
- `ntdll!RtlEqualSid` at `0x18001c8e3`
- `ntdll!RtlEqualSid` at `0x18001c8e3`
- `ntdll!RtlSetLastWin32Error` at `0x18001c3ab`
- `ntdll!RtlSetLastWin32Error` at `0x18001c3ab`
- `ntdll!NtOpenKey` at `0x18001c5bc`
- `ntdll!NtOpenKey` at `0x18001c693`
- `ntdll!NtOpenKey` at `0x18001c7d8`
- `ntdll!NtOpenKey` at `0x18001c5bc`
- `ntdll!NtOpenKey` at `0x18001c693`
- `ntdll!NtOpenKey` at `0x18001c7d8`
- `ntdll!NtCreateEvent` at `0x18001c390`
- `ntdll!NtCreateEvent` at `0x18001c390`
- `ntdll!NtCreateKey` at `0x18001c5ec`
- `ntdll!NtCreateKey` at `0x18001c6c4`
- `ntdll!NtCreateKey` at `0x18001c808`
- `ntdll!NtCreateKey` at `0x18001c5ec`
- `ntdll!NtCreateKey` at `0x18001c6c4`
- `ntdll!NtCreateKey` at `0x18001c808`
- `ntdll!RtlLcidToLocaleName` at `0x18001c2fd`
- `ntdll!RtlLcidToLocaleName` at `0x18001c2fd`
- `ntdll!RtlOpenCurrentUser` at `0x18001bb80`
- `ntdll!RtlOpenCurrentUser` at `0x18001c007`
- `ntdll!RtlOpenCurrentUser` at `0x18001c138`
- `ntdll!RtlOpenCurrentUser` at `0x18001bb80`
- `ntdll!RtlOpenCurrentUser` at `0x18001c007`
- `ntdll!RtlOpenCurrentUser` at `0x18001c138`
- `ntdll!NtNotifyChangeKey` at `0x18001c400`
- `ntdll!NtNotifyChangeKey` at `0x18001c400`
- `ntdll!NtQueryInformationToken` at `0x18001c745`
- `ntdll!NtQueryInformationToken` at `0x18001c8c8`
- `ntdll!NtQueryInformationToken` at `0x18001c745`
- `ntdll!NtQueryInformationToken` at `0x18001c8c8`
- `ntdll!CsrClientCallServer` at `0x18001ba29`
- `ntdll!CsrClientCallServer` at `0x18001bf57`
- `ntdll!CsrClientCallServer` at `0x18001ba29`
- `ntdll!CsrClientCallServer` at `0x18001bf57`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001ba09`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001bf37`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001ba09`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001bf37`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001ba4f`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001bf7f`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001ba4f`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001bf7f`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001b769`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001bd0d`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001b769`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001bd0d`
- `ntdll!NtClose` at `0x18001b7d9`
- `ntdll!NtClose` at `0x18001bc12`
- `ntdll!NtClose` at `0x18001bd82`
- `ntdll!NtClose` at `0x18001c092`
- `ntdll!NtClose` at `0x18001c1bd`
- `ntdll!NtClose` at `0x18001c5fe`
- `ntdll!NtClose` at `0x18001c63a`
- `ntdll!NtClose` at `0x18001c6d7`
- `ntdll!NtClose` at `0x18001c715`
- `ntdll!NtClose` at `0x18001c81a`
- `ntdll!NtClose` at `0x18001c856`
- `ntdll!NtClose` at `0x18001b7d9`
- `ntdll!NtClose` at `0x18001bc12`
- `ntdll!NtClose` at `0x18001bd82`
- `ntdll!NtClose` at `0x18001c092`
- `ntdll!NtClose` at `0x18001c1bd`
- `ntdll!NtClose` at `0x18001c5fe`
- `ntdll!NtClose` at `0x18001c63a`
- `ntdll!NtClose` at `0x18001c6d7`
- `ntdll!NtClose` at `0x18001c715`
- `ntdll!NtClose` at `0x18001c81a`
- `ntdll!NtClose` at `0x18001c856`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b42b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b55e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b725`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b853`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001bcc9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001bdfc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001c351`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b42b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b55e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b725`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b853`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001bcc9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001bdfc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001c351`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b511`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b645`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b938`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b969`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001c40d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b511`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b645`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b938`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b969`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001c40d`
- `ntdll!RtlFreeHeap` at `0x18001c901`
- `ntdll!RtlFreeHeap` at `0x18001c901`
- `ntdll!RtlAllocateHeap` at `0x18001c4be`
- `ntdll!RtlAllocateHeap` at `0x18001c530`
- `ntdll!RtlAllocateHeap` at `0x18001c899`
- `ntdll!RtlAllocateHeap` at `0x18001c4be`
- `ntdll!RtlAllocateHeap` at `0x18001c530`
- `ntdll!RtlAllocateHeap` at `0x18001c899`

## pseudocode

```c
_DWORD *__fastcall CheckSpecialLocales(__int64 a1)
{
  int v1; // ebx
  _DWORD *result; // rax
  DWORD v3; // ebx
  __int64 m; // rdx
  unsigned int *v5; // rax
  __int64 v6; // r8
  DWORD v7; // ebx
  _WORD *v8; // rcx
  __int64 TransientLocale; // rax
  DWORD v10; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v13; // r8
  DWORD v14; // edi
  _WORD *v15; // rcx
  __int64 NamedLocaleHashNode; // rax
  HANDLE *v17; // rdi
  ULONG IsImpersonating; // ecx
  int v19; // ebx
  __int16 v20; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v22; // rbx
  NTSTATUS v23; // r13d
  HANDLE v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rax
  DWORD v27; // ebx
  __int64 j; // rdx
  unsigned int *v29; // rax
  __int64 v30; // r8
  DWORD v31; // ebx
  _WORD *v32; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  int GlobalizationUserModelType; // ecx
  NTSTATUS v38; // eax
  __int64 v39; // rcx
  WCHAR *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rsi
  WCHAR *v43; // rcx
  const WCHAR *v44; // r14
  __int64 v45; // rbx
  WCHAR *v46; // rax
  HANDLE v47; // r12
  const WCHAR *v48; // r14
  __int64 v49; // rsi
  __int16 v50; // ax
  PCSR_CAPTURE_BUFFER v51; // rax
  struct _CSR_CAPTURE_BUFFER *v52; // r13
  NTSTATUS v53; // r13d
  HANDLE v54; // rbx
  __int64 v55; // rbx
  __int64 k; // rdx
  ULONG v57; // ecx
  HANDLE *NlsCache; // rsi
  int v59; // ecx
  NTSTATUS v60; // eax
  WCHAR *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  WCHAR *v64; // r9
  __int64 v65; // rcx
  const WCHAR *v66; // rdx
  __int64 v67; // r8
  WCHAR *v68; // rax
  int v69; // ecx
  NTSTATUS v70; // eax
  WCHAR *v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rax
  WCHAR *v74; // rcx
  __int64 v75; // rbx
  WCHAR *v76; // rax
  int v77; // ecx
  HANDLE *v78; // rsi
  int v79; // ecx
  NTSTATUS Event; // eax
  ULONG v81; // ecx
  HANDLE v82; // rax
  int v83; // ecx
  HANDLE *Heap; // rax
  HANDLE *v85; // rax
  NTSTATUS v86; // ebx
  HANDLE v87; // rcx
  void *v88; // rbx
  NTSTATUS v89; // r12d
  HANDLE v90; // rcx
  void *v91; // r12
  NTSTATUS v92; // ebx
  HANDLE v93; // rcx
  void *v94; // rbx
  PSID *v95; // rsi
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v99; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  __int64 v102; // [rsp+B8h] [rbp-48h]
  WCHAR ApiMessage[32]; // [rsp+C0h] [rbp-40h] BYREF
  PVOID CapturedData; // [rsp+100h] [rbp+0h] BYREF
  int v105; // [rsp+108h] [rbp+8h]

  v1 = a1;
  if ( (_DWORD)a1 == 127 )
    return (_DWORD *)gpInvLocHashN;
  if ( (unsigned int)a1 > 0xC00 )
  {
    if ( (_DWORD)a1 == 4096 )
    {
      result = (_DWORD *)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        return result;
    }
    else if ( (_DWORD)a1 != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(a1, KeyHandle, 0, 0) >= 0 )
    {
      result = (_DWORD *)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( result )
        return result;
    }
LABEL_26:
    result = (_DWORD *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( v1 != *result )
        return 0;
      return result;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v10 = gSystemLocale;
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
      goto LABEL_95;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v10 != 127 )
      {
        v14 = HIWORD(v10);
        if ( (v14 & 0xF) == 0 )
        {
          v15 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
          goto LABEL_39;
        }
        v34 = WindowsLocaleData[54];
        v15 = (_WORD *)qword_18039EC90;
        if ( (_DWORD)v34 )
          v15 = (_WORD *)(qword_18039EC90
                        + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v34 + 2LL * (v14 & 0xF)) - 2)
                        + 2);
        if ( v15 && *v15 )
          goto LABEL_38;
LABEL_95:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v10, v13, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_95;
      NamedLocaleHashNode = GetTransientLocale(v10);
    }
LABEL_39:
    gpSysLocHashN = NamedLocaleHashNode;
    if ( !NamedLocaleHashNode )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    result = (_DWORD *)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( (_DWORD)a1 == 3072 || !(_DWORD)a1 || (_DWORD)a1 == 1024 )
  {
    v17 = 0;
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( IsImpersonating )
    {
      v57 = IsImpersonating - 1;
      if ( v57 )
      {
        if ( v57 == 1 )
        {
          if ( BasepIsSecureProcess )
          {
            v17 = &gNlsProcessLocalCache;
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
                LODWORD(v17) = 1;
                *((_WORD *)Heap + 842) = 3;
                *((_WORD *)Heap + 843) = 1;
              }
              else
              {
                NlsCache = &gNlsProcessLocalCache;
              }
              NtCurrentTeb()->NlsCache = NlsCache;
            }
            if ( NlsCache != &gNlsProcessLocalCache && ((_DWORD)v17 || *((_WORD *)NlsCache + 843) == 1) )
            {
              *((_WORD *)NlsCache + 843) = 1;
              UpdateNlsInfoCache(NlsCache, 0);
            }
            v17 = NlsCache;
          }
        }
      }
      else
      {
        if ( BasepIsSecureProcess )
        {
          v78 = &gNlsProcessLocalCache;
        }
        else
        {
          v78 = (HANDLE *)NtCurrentTeb()->NlsCache;
          if ( !v78 )
          {
            v85 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
            v78 = v85;
            if ( v85 )
            {
              *v85 = 0;
              v85[1] = 0;
              v85[2] = 0;
              *((_WORD *)v85 + 842) = 3;
              *((_WORD *)v85 + 843) = 1;
            }
            else
            {
              v78 = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = v78;
          }
          if ( v78 != &gNlsProcessLocalCache )
          {
            *((_WORD *)v78 + 843) = 1;
            UpdateNlsInfoCache(v78, 0);
          }
        }
        v17 = v78;
        NtCurrentTeb()->IsImpersonating = 2;
      }
      return v17[2];
    }
    v19 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
    {
      Disposition = 0;
      v19 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v102 = 0;
      if ( !BasepIsSecureProcess
        && NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFCLL,
             TokenStatistics,
             &ObjectAttributes,
             0x38u,
             &Disposition) >= 0 )
      {
        if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
        {
          v19 = 1;
          gInteractiveLogonUserProcess = 1;
          word_1803A4274 = 1;
          goto LABEL_49;
        }
        v95 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
        if ( v95 )
        {
          if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, v95, 0x54u, &Disposition) >= 0 )
            v19 = RtlEqualSid(*v95, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v95);
        }
      }
      gInteractiveLogonUserProcess = v19;
      if ( v19 )
        word_1803A4274 = 1;
      else
        word_1803A4274 = 20;
    }
LABEL_49:
    if ( v19 )
    {
      if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
        word_1803A4276 = 1;
      if ( !word_1803A4276 )
        goto LABEL_89;
      v20 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v20 = word_1803A4274;
        if ( word_1803A4274 != 3 )
        {
          if ( !word_1803A4276 )
            goto LABEL_88;
          v20 = word_1803A4274;
        }
      }
      word_1803A4276 = 2;
      if ( v20 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        v22 = CaptureBuffer;
        if ( CaptureBuffer )
        {
          CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
          v105 = 1660;
          v23 = CsrClientCallServer(ApiMessage, v22, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v23 >= 0 )
            memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer(v22);
        }
        else
        {
          v23 = -1073741801;
        }
        if ( word_1803A4274 == 1 && v23 >= 0 )
          goto LABEL_64;
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_61:
        v24 = Handle;
        NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
        if ( word_1803A4274 == 3 && v24 )
          NtClose(v24);
LABEL_64:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
          goto LABEL_69;
        }
        v25 = gpOneCustomHashNode;
        _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
        if ( !v25 && gpOneCustomHashNode )
          gpOneCustomHashNode = 0;
        if ( !qword_1803A3BF0 )
        {
LABEL_69:
          v26 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_86;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_85;
          v27 = gSystemLocale;
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
            goto LABEL_85;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_117;
          v29 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( v29 )
          {
            if ( (_WORD)v27 != 127 )
            {
LABEL_79:
              v31 = HIWORD(v27);
              if ( (v31 & 0xF) == 0 )
              {
                v32 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v29);
LABEL_81:
                LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v32, 0);
                goto LABEL_82;
              }
              v36 = v29[54];
              v32 = (_WORD *)qword_18039EC90;
              if ( (_DWORD)v36 )
                v32 = (_WORD *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v36 + 2LL * (v31 & 0xF)) - 2)
                              + 2);
              if ( v32 && *v32 )
                goto LABEL_81;
LABEL_117:
              gpSysLocHashN = 0;
LABEL_83:
              gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
              if ( !gpSysLocHashN )
                gpSysLocHashN = gpInvLocHashN;
              goto LABEL_85;
            }
            goto LABEL_169;
          }
          goto LABEL_207;
        }
LABEL_87:
        _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
        if ( word_1803A4274 == 3 )
        {
LABEL_89:
          v17 = &gNlsProcessLocalCache;
          return v17[2];
        }
LABEL_88:
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
        goto LABEL_89;
      }
      KeyHandle[0] = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      GlobalizationUserModelType = GetGlobalizationUserModelType();
      if ( GlobalizationUserModelType == 1 )
      {
        v38 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
      }
      else
      {
        v77 = GlobalizationUserModelType - 2;
        if ( v77 )
        {
          if ( v77 != 1 )
          {
LABEL_135:
            SetLastError_0(0x3F1u);
            goto LABEL_61;
          }
          v99 = 0;
          v38 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
        }
        else
        {
          v38 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
        }
      }
      if ( v38 >= 0 )
      {
        ApiMessage[0] = 0;
        v39 = 512;
        v40 = ApiMessage;
        do
        {
          if ( !*v40 )
            break;
          ++v40;
          --v39;
        }
        while ( v39 );
        v41 = 512 - v39;
        if ( !v39 )
          goto LABEL_133;
        v42 = 2147483646;
        v43 = &ApiMessage[v41];
        v44 = L"Control Panel\\International";
        v45 = 512 - v41;
        if ( 512 != v41 )
        {
          do
          {
            if ( !v42 )
              break;
            if ( !*v44 )
              break;
            *v43++ = *v44++;
            --v42;
            --v45;
          }
          while ( v45 );
        }
        v46 = v43 - 1;
        if ( v45 )
          v46 = v43;
        *v46 = 0;
        if ( v45 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle[0];
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v86 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v86 < 0 )
            v86 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
          if ( v86 >= 0 )
          {
            v87 = Handle;
          }
          else
          {
            v87 = 0;
            Handle = 0;
          }
          if ( v86 >= 0 )
          {
            v88 = (void *)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&gNlsProcessLocalCache,
                            (signed __int64)v87,
                            0);
            if ( v88 )
            {
              if ( Handle )
                NtClose(Handle);
              Handle = v88;
            }
            goto LABEL_61;
          }
        }
        else
        {
LABEL_133:
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
        }
      }
      goto LABEL_135;
    }
    v47 = gNlsProcessLocalCache;
    if ( BasepIsSecureProcess )
      goto LABEL_89;
    v48 = L"Control Panel\\International";
    v49 = 2147483646;
    if ( gNlsProcessLocalCache )
    {
LABEL_140:
      if ( !::Event || !WaitForSingleObjectEx(::Event, 0, 0) )
      {
        word_1803A4276 = 1;
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        if ( !::Event )
        {
          KeyHandle[0] = 0;
          memset(&ObjectAttributes, 0, 44);
          DestinationString = 0;
          Event = NtCreateEvent(KeyHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event < 0 )
          {
            BaseSetLastNTError((unsigned int)Event);
            v82 = 0;
          }
          else
          {
            if ( Event == 0x40000000 )
              v81 = 183;
            else
              v81 = 0;
            RtlSetLastWin32Error(v81);
            v82 = KeyHandle[0];
          }
          ::Event = v82;
        }
        if ( ::Event )
          NtNotifyChangeKey(v47, ::Event, 0, 0, &IoStatusRegChange, 0x10000005u, 1u, 0, 0, 1u);
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
      }
LABEL_142:
      if ( !word_1803A4276 )
        goto LABEL_89;
      v50 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v50 = word_1803A4274;
        if ( word_1803A4274 != 3 )
        {
          if ( !word_1803A4276 )
            goto LABEL_88;
          v50 = word_1803A4274;
        }
      }
      word_1803A4276 = 2;
      if ( v50 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        v51 = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        KeyHandle[0] = v51;
        v52 = v51;
        if ( v51 )
        {
          CsrCaptureMessageBuffer(v51, 0, 0x67Cu, &CapturedData);
          v105 = 1660;
          v53 = CsrClientCallServer(ApiMessage, v52, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v53 >= 0 )
            memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer((PCSR_CAPTURE_BUFFER)KeyHandle[0]);
        }
        else
        {
          v53 = -1073741801;
        }
        if ( word_1803A4274 == 1 && v53 >= 0 )
        {
LABEL_154:
          if ( word_1803A3BF8 == -1 )
          {
            qword_1803A3BF0 = 0;
          }
          else
          {
            v55 = gpOneCustomHashNode;
            _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
            if ( !v55 && gpOneCustomHashNode )
              gpOneCustomHashNode = 0;
            if ( qword_1803A3BF0 )
              goto LABEL_87;
          }
          v26 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_86;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_85;
          v27 = gSystemLocale;
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
            goto LABEL_85;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_117;
          v29 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( v29 )
          {
            if ( (_WORD)v27 != 127 )
              goto LABEL_79;
LABEL_169:
            LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v29, v27, v30, 0);
            goto LABEL_82;
          }
LABEL_207:
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_117;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocHashNodeFromSystemLocale = FindLocaleHashNode(v27);
          }
          else
          {
            LocHashNodeFromSystemLocale = 0;
          }
LABEL_82:
          gpSysLocHashN = LocHashNodeFromSystemLocale;
          if ( !LocHashNodeFromSystemLocale )
            goto LABEL_83;
LABEL_85:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          v26 = gpSysLocHashN;
LABEL_86:
          qword_1803A3BF0 = v26;
          goto LABEL_87;
        }
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_151:
        v54 = Handle;
        NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
        if ( word_1803A4274 == 3 && v54 )
          NtClose(v54);
        goto LABEL_154;
      }
      KeyHandle[0] = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      v69 = GetGlobalizationUserModelType();
      if ( v69 == 1 )
      {
        v70 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
      }
      else
      {
        v83 = v69 - 2;
        if ( v83 )
        {
          if ( v83 != 1 )
          {
LABEL_229:
            SetLastError_0(0x3F1u);
            goto LABEL_151;
          }
          v99 = 0;
          v70 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
        }
        else
        {
          v70 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
        }
      }
      if ( v70 >= 0 )
      {
        ApiMessage[0] = 0;
        v71 = ApiMessage;
        v72 = 512;
        do
        {
          if ( !*v71 )
            break;
          ++v71;
          --v72;
        }
        while ( v72 );
        v73 = 512 - v72;
        if ( !v72 )
          goto LABEL_227;
        v74 = &ApiMessage[v73];
        v75 = 512 - v73;
        if ( 512 != v73 )
        {
          do
          {
            if ( !v49 )
              break;
            if ( !*v48 )
              break;
            *v74++ = *v48++;
            --v49;
            --v75;
          }
          while ( v75 );
        }
        v76 = v74 - 1;
        if ( v75 )
          v76 = v74;
        *v76 = 0;
        if ( v75 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle[0];
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v92 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v92 < 0 )
            v92 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
          if ( v92 >= 0 )
          {
            v93 = Handle;
          }
          else
          {
            v93 = 0;
            Handle = 0;
          }
          if ( v92 >= 0 )
          {
            v94 = (void *)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&gNlsProcessLocalCache,
                            (signed __int64)v93,
                            0);
            if ( v94 )
            {
              if ( Handle )
                NtClose(Handle);
              Handle = v94;
            }
            goto LABEL_151;
          }
        }
        else
        {
LABEL_227:
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
        }
      }
      goto LABEL_229;
    }
    Handle = 0;
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    v59 = GetGlobalizationUserModelType();
    if ( v59 == 1 )
    {
      v60 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v79 = v59 - 2;
      if ( v79 )
      {
        if ( v79 != 1 )
          goto LABEL_206;
        v99 = 0;
        v60 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
      }
      else
      {
        v60 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v60 >= 0 )
    {
      ApiMessage[0] = 0;
      v61 = ApiMessage;
      v62 = 512;
      do
      {
        if ( !*v61 )
          break;
        ++v61;
        --v62;
      }
      while ( v62 );
      v63 = 512 - v62;
      if ( !v62 )
        goto LABEL_204;
      v64 = &ApiMessage[v63];
      v65 = 2147483646;
      v66 = L"Control Panel\\International";
      v67 = 512 - v63;
      if ( v63 != 512 )
      {
        do
        {
          if ( !v65 )
            break;
          if ( !*v66 )
            break;
          *v64++ = *v66++;
          --v65;
          --v67;
        }
        while ( v67 );
      }
      v68 = v64 - 1;
      if ( v67 )
        v68 = v64;
      *v68 = 0;
      if ( v67 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v89 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v89 < 0 )
          v89 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v89 >= 0 )
        {
          v90 = Handle;
        }
        else
        {
          v90 = 0;
          Handle = 0;
        }
        if ( v89 >= 0 )
        {
          v91 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v90,
                          0);
          if ( v91 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v91;
          }
LABEL_139:
          v47 = Handle;
          if ( !Handle )
            goto LABEL_142;
          goto LABEL_140;
        }
      }
      else
      {
LABEL_204:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
LABEL_206:
    SetLastError_0(0x3F1u);
    goto LABEL_139;
  }
  if ( (_DWORD)a1 != 2048 )
    goto LABEL_26;
  result = (_DWORD *)gpSysLocHashN;
  if ( !gpSysLocHashN && !BasepIsSecureProcess )
  {
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v3 = gSystemLocale;
    for ( m = *((_QWORD *)P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); m; m = *(_QWORD *)(m + 88) )
    {
      if ( *(_DWORD *)m == gSystemLocale )
        break;
    }
    gpSysLocHashN = m;
    if ( m )
      goto LABEL_23;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_112;
    v5 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v5 )
    {
      if ( (_WORD)v3 != 127 )
      {
        v7 = HIWORD(v3);
        if ( (v7 & 0xF) == 0 )
        {
          v8 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v5);
LABEL_19:
          TransientLocale = MakeNamedLocaleHashNode(v8, 0);
          goto LABEL_20;
        }
        v35 = v5[54];
        v8 = (_WORD *)qword_18039EC90;
        if ( (_DWORD)v35 )
          v8 = (_WORD *)(qword_18039EC90
                       + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v35 + 2LL * (v7 & 0xF)) - 2)
                       + 2);
        if ( v8 && *v8 )
          goto LABEL_19;
LABEL_112:
        gpSysLocHashN = 0;
        goto LABEL_21;
      }
      TransientLocale = MakeLocHashNodeFromSystemLocale(v5, v3, v6, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_112;
      TransientLocale = GetTransientLocale(v3);
    }
LABEL_20:
    gpSysLocHashN = TransientLocale;
    if ( TransientLocale )
    {
LABEL_23:
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      return (_DWORD *)gpSysLocHashN;
    }
LABEL_21:
    gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
    if ( !gpSysLocHashN )
      gpSysLocHashN = gpInvLocHashN;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x18001b3a0  push    rbp
0x18001b3a2  push    rbx
0x18001b3a3  lea     rbp, [rsp-3E8h]
0x18001b3ab  sub     rsp, 4E8h
0x18001b3b2  mov     rax, cs:__security_cookie
0x18001b3b9  xor     rax, rsp
0x18001b3bc  mov     [rbp+3F0h+var_30], rax
0x18001b3c3  mov     ebx, ecx
0x18001b3c5  cmp     ecx, 7Fh
0x18001b3c8  jz      loc_18001B67B
0x18001b3ce  mov     [rsp+4F0h+arg_10], rdi
0x18001b3d6  cmp     ecx, 0C00h
0x18001b3dc  ja      loc_18001B523
0x18001b3e2  jz      loc_18001B684
0x18001b3e8  test    ecx, ecx
0x18001b3ea  jz      loc_18001B684
0x18001b3f0  cmp     ecx, 400h
0x18001b3f6  jz      loc_18001B684
0x18001b3fc  cmp     ecx, 800h
0x18001b402  jnz     loc_18001B53B
0x18001b408  mov     rax, cs:gpSysLocHashN
0x18001b40f  test    rax, rax
0x18001b412  jnz     loc_18001B65A
0x18001b418  cmp     cs:BasepIsSecureProcess, al
0x18001b41e  jnz     loc_18001B65A
0x18001b424  lea     rcx, gTblPtrsLock
0x18001b42b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b431  cmp     cs:gpSysLocHashN, 0
0x18001b439  jnz     loc_18001B50A
0x18001b43f  mov     ebx, cs:gSystemLocale
0x18001b445  mov     rax, cs:P
0x18001b44c  mov     ecx, ebx
0x18001b44e  shr     rcx, 7
0x18001b452  xor     rcx, rbx
0x18001b455  shr     rcx, 7
0x18001b459  xor     rcx, rbx
0x18001b45c  and     ecx, 7Fh
0x18001b45f  mov     rdx, [rax+rcx*8]
0x18001b463  test    rdx, rdx
0x18001b466  jz      short loc_18001B470
0x18001b468  cmp     [rdx], ebx
0x18001b46a  jnz     loc_18001BEFD
0x18001b470  mov     cs:gpSysLocHashN, rdx
0x18001b477  test    rdx, rdx
0x18001b47a  jnz     loc_18001B50A
0x18001b480  test    ebx, 0FFF00000h
0x18001b486  jnz     loc_18001BADC
0x18001b48c  cmp     cs:BasepIsSecureProcess, dl
0x18001b492  jnz     loc_18001BADC
0x18001b498  mov     ecx, ebx
0x18001b49a  call    GetWindowsLocaleData
0x18001b49f  test    rax, rax
0x18001b4a2  jz      loc_18001BF0F
0x18001b4a8  cmp     bx, 7Fh
0x18001b4ac  jz      loc_18001C0DF
0x18001b4b2  shr     ebx, 10h
0x18001b4b5  test    bl, 0Fh
0x18001b4b8  jnz     loc_18001BAA9
0x18001b4be  mov     ecx, [rax]
0x18001b4c0  mov     rax, cs:qword_18039EC90
0x18001b4c7  add     rax, 2
0x18001b4cb  lea     rcx, [rax+rcx*2]
0x18001b4cf  xor     edx, edx
0x18001b4d1  call    MakeNamedLocaleHashNode
0x18001b4d6  mov     cs:gpSysLocHashN, rax
0x18001b4dd  test    rax, rax
0x18001b4e0  jnz     short loc_18001B50A
0x18001b4e2  xor     edx, edx
0x18001b4e4  lea     rcx, aEnUs; "en-US"
0x18001b4eb  call    MakeNamedLocaleHashNode
0x18001b4f0  mov     cs:gpSysLocHashN, rax
0x18001b4f7  test    rax, rax
0x18001b4fa  jnz     short loc_18001B50A
0x18001b4fc  mov     rax, cs:gpInvLocHashN
0x18001b503  mov     cs:gpSysLocHashN, rax
0x18001b50a  lea     rcx, gTblPtrsLock
0x18001b511  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b517  mov     rax, cs:gpSysLocHashN
0x18001b51e  jmp     loc_18001B65A
0x18001b523  cmp     ebx, 1000h
0x18001b529  jz      loc_18001C2C7
0x18001b52f  cmp     ebx, 1400h
0x18001b535  jz      loc_18001C2D7
0x18001b53b  mov     rax, cs:gpSysLocHashN
0x18001b542  test    rax, rax
0x18001b545  jnz     loc_18001B652
0x18001b54b  cmp     cs:BasepIsSecureProcess, al
0x18001b551  jnz     loc_18001B652
0x18001b557  lea     rcx, gTblPtrsLock
0x18001b55e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b564  cmp     cs:gpSysLocHashN, 0
0x18001b56c  jnz     loc_18001B63E
0x18001b572  mov     edi, cs:gSystemLocale
0x18001b578  mov     rax, cs:P
0x18001b57f  mov     ecx, edi
0x18001b581  shr     rcx, 7
0x18001b585  xor     rcx, rdi
0x18001b588  shr     rcx, 7
0x18001b58c  xor     rcx, rdi
0x18001b58f  and     ecx, 7Fh
0x18001b592  mov     rdx, [rax+rcx*8]
0x18001b596  test    rdx, rdx
0x18001b599  jz      short loc_18001B5A3
0x18001b59b  cmp     [rdx], edi
0x18001b59d  jnz     loc_18001B9E8
0x18001b5a3  mov     cs:gpSysLocHashN, rdx
0x18001b5aa  test    rdx, rdx
0x18001b5ad  jnz     loc_18001B63E
0x18001b5b3  test    edi, 0FFF00000h
0x18001b5b9  jnz     loc_18001B9DA
0x18001b5bf  cmp     cs:BasepIsSecureProcess, dl
0x18001b5c5  jnz     loc_18001B9DA
0x18001b5cb  mov     ecx, edi
0x18001b5cd  call    GetWindowsLocaleData
0x18001b5d2  test    rax, rax
0x18001b5d5  jz      loc_18001BA90
0x18001b5db  cmp     di, 7Fh
0x18001b5df  jz      loc_18001BB27
0x18001b5e5  shr     edi, 10h
0x18001b5e8  test    dil, 0Fh
0x18001b5ec  jnz     loc_18001B9A7
0x18001b5f2  mov     ecx, [rax]
0x18001b5f4  mov     rax, cs:qword_18039EC90
0x18001b5fb  add     rax, 2
0x18001b5ff  lea     rcx, [rax+rcx*2]
0x18001b603  xor     edx, edx
0x18001b605  call    MakeNamedLocaleHashNode
0x18001b60a  mov     cs:gpSysLocHashN, rax
0x18001b611  test    rax, rax
0x18001b614  jnz     short loc_18001B63E
0x18001b616  xor     edx, edx
0x18001b618  lea     rcx, aEnUs; "en-US"
0x18001b61f  call    MakeNamedLocaleHashNode
0x18001b624  mov     cs:gpSysLocHashN, rax
0x18001b62b  test    rax, rax
0x18001b62e  jnz     short loc_18001B63E
0x18001b630  mov     rax, cs:gpInvLocHashN
0x18001b637  mov     cs:gpSysLocHashN, rax
0x18001b63e  lea     rcx, gTblPtrsLock
0x18001b645  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b64b  mov     rax, cs:gpSysLocHashN
0x18001b652  cmp     ebx, [rax]
0x18001b654  jnz     loc_18001C2AE
0x18001b65a  mov     rdi, [rsp+4F0h+arg_10]
0x18001b662  mov     rcx, [rbp+3F0h+var_30]
0x18001b669  xor     rcx, rsp; StackCookie
0x18001b66c  call    __security_check_cookie
0x18001b671  add     rsp, 4E8h
0x18001b678  pop     rbx
0x18001b679  pop     rbp
0x18001b67a  retn
0x18001b67b  mov     rax, cs:gpInvLocHashN
0x18001b682  jmp     short loc_18001B662
0x18001b684  mov     rax, gs:30h
0x18001b68d  xor     edi, edi
0x18001b68f  mov     [rsp+4F0h+arg_8], rsi
0x18001b697  mov     [rsp+4F0h+arg_18], r12
0x18001b69f  mov     [rsp+4F0h+var_20], r15
0x18001b6a7  mov     ecx, [rax+179Ch]
0x18001b6ad  test    ecx, ecx
0x18001b6af  jnz     loc_18001BE95
0x18001b6b5  mov     ebx, cs:gInteractiveLogonUserProcess
0x18001b6bb  mov     r15d, 1
0x18001b6c1  cmp     ebx, 0FFFFFFFFh
0x18001b6c4  jz      loc_18001C1D2
0x18001b6ca  mov     [rsp+4F0h+var_10], r13
0x18001b6d2  mov     [rsp+4F0h+var_18], r14
0x18001b6da  test    ebx, ebx
0x18001b6dc  jz      loc_18001BC27
0x18001b6e2  mov     ecx, cs:dword_1803A4270
0x18001b6e8  mov     rax, cs:gpServerNlsUserInfo
0x18001b6ef  mov     eax, [rax+678h]
0x18001b6f5  cmp     ecx, eax
0x18001b6f7  jz      short loc_18001B701
0x18001b6f9  mov     cs:word_1803A4276, r15w
0x18001b701  movzx   eax, cs:word_1803A4276
0x18001b708  test    ax, ax
0x18001b70b  jz      loc_18001B96F
0x18001b711  movzx   eax, cs:word_1803A4274
0x18001b718  cmp     ax, 3
0x18001b71c  jz      short loc_18001B73C
0x18001b71e  lea     rcx, gNlsProcessCacheLock
0x18001b725  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b72b  movzx   eax, cs:word_1803A4274
0x18001b732  cmp     ax, 3
0x18001b736  jnz     loc_18001BA68
0x18001b73c  mov     r12d, 2
0x18001b742  mov     cs:word_1803A4276, r12w
0x18001b74a  cmp     ax, r15w
0x18001b74e  jnz     short loc_18001B78F
0x18001b750  xor     edx, edx; Val
0x18001b752  lea     rcx, [rbp+3F0h+ApiMessage]; void *
0x18001b756  mov     r8d, 3B8h; Size
0x18001b75c  call    memset_0
0x18001b761  mov     edx, 67Ch; BufferSize
0x18001b766  mov     ecx, r15d; ArgumentCount
0x18001b769  call    cs:__imp_CsrAllocateCaptureBuffer
0x18001b76f  mov     rbx, rax
0x18001b772  test    rax, rax
0x18001b775  jnz     loc_18001B9FA
0x18001b77b  mov     r13d, 0C0000017h
0x18001b781  cmp     cs:word_1803A4274, r15w
0x18001b789  jz      loc_18001BA5A
0x18001b78f  mov     rax, cs:gNlsProcessLocalCache
0x18001b796  mov     [rsp+4F0h+Handle], rdi
0x18001b79b  test    rax, rax
0x18001b79e  jz      loc_18001BB39
0x18001b7a4  mov     rax, cs:gNlsProcessLocalCache
0x18001b7ab  mov     [rsp+4F0h+Handle], rax
0x18001b7b0  mov     rbx, [rsp+4F0h+Handle]
0x18001b7b5  lea     rcx, word_1803A3BF8
0x18001b7bc  mov     rdx, rbx
0x18001b7bf  mov     r8d, r15d
0x18001b7c2  call    NlsUpdateCacheInfo
0x18001b7c7  cmp     cs:word_1803A4274, 3
0x18001b7cf  jnz     short loc_18001B7DF
0x18001b7d1  test    rbx, rbx
0x18001b7d4  jz      short loc_18001B7DF
0x18001b7d6  mov     rcx, rbx; Handle
0x18001b7d9  call    cs:__imp_NtClose
0x18001b7df  mov     eax, 0FFFFh
0x18001b7e4  cmp     cs:word_1803A3BF8, ax
0x18001b7eb  jz      loc_18001BA84
0x18001b7f1  mov     rbx, cs:gpOneCustomHashNode
0x18001b7f8  lea     rcx, word_1803A3BFA
0x18001b7ff  xor     edx, edx
0x18001b801  call    GetNamedLocaleHashNode
0x18001b806  xchg    rax, cs:qword_1803A3BF0
0x18001b80d  test    rbx, rbx
0x18001b810  jnz     short loc_18001B822
0x18001b812  cmp     cs:gpOneCustomHashNode, rdi
0x18001b819  jz      short loc_18001B822
0x18001b81b  mov     cs:gpOneCustomHashNode, rdi
0x18001b822  cmp     cs:qword_1803A3BF0, rdi
0x18001b829  jnz     loc_18001B94C
0x18001b82f  mov     rax, cs:gpSysLocHashN
0x18001b836  test    rax, rax
0x18001b839  jnz     loc_18001B945
0x18001b83f  cmp     cs:BasepIsSecureProcess, dil
0x18001b846  jnz     loc_18001B945
0x18001b84c  lea     rcx, gTblPtrsLock
0x18001b853  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b859  cmp     cs:gpSysLocHashN, rdi
0x18001b860  jnz     loc_18001B931
0x18001b866  mov     ebx, cs:gSystemLocale
0x18001b86c  mov     rax, cs:P
0x18001b873  mov     ecx, ebx
0x18001b875  shr     rcx, 7
0x18001b879  xor     rcx, rbx
0x18001b87c  shr     rcx, 7
0x18001b880  xor     rcx, rbx
0x18001b883  and     ecx, 7Fh
0x18001b886  mov     rdx, [rax+rcx*8]
0x18001b88a  test    rdx, rdx
0x18001b88d  jz      short loc_18001B897
0x18001b88f  cmp     [rdx], ebx
0x18001b891  jnz     loc_18001C0CD
0x18001b897  mov     cs:gpSysLocHashN, rdx
0x18001b89e  test    rdx, rdx
0x18001b8a1  jnz     loc_18001B931
0x18001b8a7  test    ebx, 0FFF00000h
0x18001b8ad  jnz     loc_18001BB1B
0x18001b8b3  cmp     cs:BasepIsSecureProcess, dil
0x18001b8ba  jnz     loc_18001BB1B
0x18001b8c0  mov     ecx, ebx
0x18001b8c2  call    GetWindowsLocaleData
0x18001b8c7  test    rax, rax
0x18001b8ca  jz      loc_18001C0A7
0x18001b8d0  cmp     bx, 7Fh
0x18001b8d4  jz      loc_18001BE83
0x18001b8da  shr     ebx, 10h
0x18001b8dd  test    bl, 0Fh
0x18001b8e0  jnz     loc_18001BAEA
0x18001b8e6  mov     ecx, [rax]
0x18001b8e8  mov     rax, cs:qword_18039EC90
0x18001b8ef  add     rax, r12
0x18001b8f2  lea     rcx, [rax+rcx*2]
0x18001b8f6  xor     edx, edx
0x18001b8f8  call    MakeNamedLocaleHashNode
0x18001b8fd  mov     cs:gpSysLocHashN, rax
0x18001b904  test    rax, rax
0x18001b907  jnz     short loc_18001B931
0x18001b909  xor     edx, edx
0x18001b90b  lea     rcx, aEnUs; "en-US"
0x18001b912  call    MakeNamedLocaleHashNode
0x18001b917  mov     cs:gpSysLocHashN, rax
0x18001b91e  test    rax, rax
0x18001b921  jnz     short loc_18001B931
0x18001b923  mov     rax, cs:gpInvLocHashN
0x18001b92a  mov     cs:gpSysLocHashN, rax
0x18001b931  lea     rcx, gTblPtrsLock
0x18001b938  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b93e  mov     rax, cs:gpSysLocHashN
0x18001b945  mov     cs:qword_1803A3BF0, rax
0x18001b94c  mov     eax, r12d
0x18001b94f  lock cmpxchg cs:word_1803A4276, di
0x18001b958  cmp     cs:word_1803A4274, 3
0x18001b960  jz      short loc_18001B96F
0x18001b962  lea     rcx, gNlsProcessCacheLock
0x18001b969  call    cs:__imp_RtlReleaseSRWLockExclusive
  ... truncated ...
```
