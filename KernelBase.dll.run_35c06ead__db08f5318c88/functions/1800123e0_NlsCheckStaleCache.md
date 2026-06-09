# NlsCheckStaleCache

- ea: `0x1800123e0`
- end: `0x180012d9d`
- name: `NlsCheckStaleCache`
- size: `2493`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001d7c0`
- `0x180037730`

## callees

- `0x180010080`
- `0x180011b90`
- `0x1800123e0`
- `0x180012dc0`
- `0x180012f10`
- `0x1800134a0`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x18007217c`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180012bc7`
- `ntdll!RtlInitUnicodeString` at `0x180012ca3`
- `ntdll!RtlInitUnicodeString` at `0x180012bc7`
- `ntdll!RtlInitUnicodeString` at `0x180012ca3`
- `ntdll!RtlSetLastWin32Error` at `0x180012ada`
- `ntdll!RtlSetLastWin32Error` at `0x180012ada`
- `ntdll!NtOpenKey` at `0x180012c0b`
- `ntdll!NtOpenKey` at `0x180012ce7`
- `ntdll!NtOpenKey` at `0x180012c0b`
- `ntdll!NtOpenKey` at `0x180012ce7`
- `ntdll!NtCreateEvent` at `0x180012abf`
- `ntdll!NtCreateEvent` at `0x180012abf`
- `ntdll!NtCreateKey` at `0x180012c3d`
- `ntdll!NtCreateKey` at `0x180012d19`
- `ntdll!NtCreateKey` at `0x180012c3d`
- `ntdll!NtCreateKey` at `0x180012d19`
- `ntdll!RtlOpenCurrentUser` at `0x18001283d`
- `ntdll!RtlOpenCurrentUser` at `0x18001292d`
- `ntdll!RtlOpenCurrentUser` at `0x18001283d`
- `ntdll!RtlOpenCurrentUser` at `0x18001292d`
- `ntdll!NtNotifyChangeKey` at `0x180012b30`
- `ntdll!NtNotifyChangeKey` at `0x180012b30`
- `ntdll!CsrClientCallServer` at `0x180012791`
- `ntdll!CsrClientCallServer` at `0x180012791`
- `ntdll!CsrCaptureMessageBuffer` at `0x180012771`
- `ntdll!CsrCaptureMessageBuffer` at `0x180012771`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800127b6`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800127b6`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001250e`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001250e`
- `ntdll!NtClose` at `0x18001257d`
- `ntdll!NtClose` at `0x1800128d1`
- `ntdll!NtClose` at `0x1800129b0`
- `ntdll!NtClose` at `0x180012c4f`
- `ntdll!NtClose` at `0x180012c8b`
- `ntdll!NtClose` at `0x180012d2b`
- `ntdll!NtClose` at `0x180012d63`
- `ntdll!NtClose` at `0x18001257d`
- `ntdll!NtClose` at `0x1800128d1`
- `ntdll!NtClose` at `0x1800129b0`
- `ntdll!NtClose` at `0x180012c4f`
- `ntdll!NtClose` at `0x180012c8b`
- `ntdll!NtClose` at `0x180012d2b`
- `ntdll!NtClose` at `0x180012d63`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800124c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800125ff`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012a7f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800124c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800125ff`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012a7f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800126e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001271b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800126e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001271b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b3d`

## pseudocode

```c
void NlsCheckStaleCache()
{
  HANDLE v0; // rbx
  __int64 v1; // r14
  const WCHAR *v2; // r15
  __int16 v3; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v5; // rbx
  NTSTATUS v6; // esi
  HANDLE v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rax
  DWORD v10; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v13; // r8
  DWORD v14; // ebx
  _WORD *v15; // rcx
  __int64 NamedLocaleHashNode; // rax
  int GlobalizationUserModelType; // eax
  int v18; // eax
  WCHAR *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  bool v23; // zf
  __int64 v24; // r8
  const WCHAR *v25; // rdx
  WCHAR *v26; // r9
  WCHAR *v27; // rcx
  int v28; // eax
  int v29; // eax
  WCHAR *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdi
  WCHAR *v33; // rdx
  WCHAR *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  NTSTATUS v37; // eax
  ULONG v38; // ecx
  HANDLE v39; // rax
  int v40; // eax
  NTSTATUS v41; // ebx
  HANDLE v42; // rcx
  void *v43; // rbx
  NTSTATUS v44; // ebx
  HANDLE v45; // rcx
  void *v46; // rbx
  HANDLE Handle; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD ObjectAttributes[7]; // [rsp+68h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B8h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F8h] [rbp-10h] BYREF
  int v53; // [rsp+100h] [rbp-8h]

  v0 = gNlsProcessLocalCache;
  if ( BasepIsSecureProcess )
    return;
  v1 = 2147483646;
  v2 = L"Control Panel\\International";
  if ( !gNlsProcessLocalCache )
  {
    Handle = 0;
    KeyHandle = 0;
    LODWORD(ObjectAttributes[0]) = 0;
    memset(&ObjectAttributes[1], 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType();
    if ( GlobalizationUserModelType == 1 )
    {
      v18 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v36 = GlobalizationUserModelType - 2;
      if ( v36 )
      {
        if ( v36 != 1 )
          goto LABEL_70;
        HIDWORD(ObjectAttributes[0]) = 0;
        v18 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, (_DWORD *)ObjectAttributes + 1);
      }
      else
      {
        v18 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v18 >= 0 )
    {
      ApiMessage[0] = 0;
      v19 = ApiMessage;
      v20 = 512;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v20;
      }
      while ( v20 );
      v21 = 512 - v20;
      if ( !v20 )
        goto LABEL_68;
      v22 = 2147483646;
      v24 = 512 - v21;
      v23 = v21 == 512;
      v25 = L"Control Panel\\International";
      v26 = &ApiMessage[v21];
      if ( !v23 )
      {
        do
        {
          if ( !v22 )
            break;
          if ( !*v25 )
            break;
          *v26++ = *v25++;
          --v22;
          --v24;
        }
        while ( v24 );
      }
      v27 = v26 - 1;
      if ( v24 )
        v27 = v26;
      *v27 = 0;
      if ( v24 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes[2] = KeyHandle;
        LODWORD(ObjectAttributes[1]) = 48;
        ObjectAttributes[3] = &DestinationString;
        LODWORD(ObjectAttributes[4]) = 64;
        *(_OWORD *)&ObjectAttributes[5] = 0;
        LODWORD(ObjectAttributes[0]) = 0;
        v41 = NtOpenKey(&Handle, 0x20019u, (POBJECT_ATTRIBUTES)&ObjectAttributes[1]);
        if ( v41 < 0 )
          v41 = NtCreateKey(
                  &Handle,
                  0x20019u,
                  (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                  0,
                  0,
                  0,
                  (PULONG)ObjectAttributes);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v41 >= 0 )
        {
          v42 = Handle;
        }
        else
        {
          v42 = 0;
          Handle = 0;
        }
        if ( v41 >= 0 )
        {
          v43 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v42,
                          0);
          if ( v43 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v43;
          }
          goto LABEL_4;
        }
      }
      else
      {
LABEL_68:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
LABEL_70:
    SetLastError_0(0x3F1u);
LABEL_4:
    v0 = Handle;
  }
  if ( v0 && (!Event || !WaitForSingleObjectEx(Event, 0, 0)) )
  {
    word_1803A4276 = 1;
    RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
    if ( !Event )
    {
      KeyHandle = 0;
      memset(&ObjectAttributes[1], 0, 44);
      DestinationString = 0;
      v37 = NtCreateEvent(&KeyHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
      if ( v37 < 0 )
      {
        BaseSetLastNTError((unsigned int)v37);
        v39 = 0;
      }
      else
      {
        if ( v37 == 0x40000000 )
          v38 = 183;
        else
          v38 = 0;
        RtlSetLastWin32Error(v38);
        v39 = KeyHandle;
      }
      Event = v39;
    }
    if ( Event )
      NtNotifyChangeKey(v0, Event, 0, 0, &IoStatusRegChange, 0x10000005u, 1u, 0, 0, 1u);
    RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
  }
  if ( word_1803A4276 )
  {
    v3 = word_1803A4274;
    if ( word_1803A4274 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v3 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        if ( !word_1803A4276 )
        {
LABEL_44:
          RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
          return;
        }
        v3 = word_1803A4274;
      }
    }
    word_1803A4276 = 2;
    if ( v3 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v5 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v53 = 1660;
        v6 = CsrClientCallServer(ApiMessage, v5, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v6 >= 0 )
          memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v5);
      }
      else
      {
        v6 = -1073741801;
      }
      if ( word_1803A4274 == 1 && v6 >= 0 )
      {
LABEL_20:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
        }
        else
        {
          v8 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
          if ( !v8 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803A3BF0 )
          {
LABEL_43:
            _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
            if ( word_1803A4274 == 3 )
              return;
            goto LABEL_44;
          }
        }
        v9 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_42:
          qword_1803A3BF0 = v9;
          goto LABEL_43;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_41;
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
          goto LABEL_41;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_92;
        WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( WindowsLocaleData )
        {
          if ( (_WORD)v10 != 127 )
          {
            v14 = HIWORD(v10);
            if ( (v14 & 0xF) == 0 )
            {
              v15 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_37:
              NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
              goto LABEL_38;
            }
            v35 = WindowsLocaleData[54];
            v15 = (_WORD *)qword_18039EC90;
            if ( (_DWORD)v35 )
              v15 = (_WORD *)(qword_18039EC90
                            + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v35 + 2LL * (v14 & 0xF)) - 2)
                            + 2);
            if ( v15 && *v15 )
              goto LABEL_37;
LABEL_92:
            gpSysLocHashN = 0;
LABEL_39:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_41;
          }
          NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v10, v13, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_92;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            NamedLocaleHashNode = FindLocaleHashNode(v10);
          }
          else
          {
            NamedLocaleHashNode = 0;
          }
        }
LABEL_38:
        gpSysLocHashN = NamedLocaleHashNode;
        if ( !NamedLocaleHashNode )
          goto LABEL_39;
LABEL_41:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v9 = gpSysLocHashN;
        goto LABEL_42;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_17:
      v7 = Handle;
      NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
      if ( word_1803A4274 == 3 && v7 )
        NtClose(v7);
      goto LABEL_20;
    }
    KeyHandle = 0;
    LODWORD(ObjectAttributes[0]) = 0;
    memset(&ObjectAttributes[1], 0, 44);
    DestinationString = 0;
    v28 = GetGlobalizationUserModelType();
    if ( v28 == 1 )
    {
      v29 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v40 = v28 - 2;
      if ( v40 )
      {
        if ( v40 != 1 )
        {
LABEL_87:
          SetLastError_0(0x3F1u);
          goto LABEL_17;
        }
        HIDWORD(ObjectAttributes[0]) = 0;
        v29 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, (_DWORD *)ObjectAttributes + 1);
      }
      else
      {
        v29 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v29 >= 0 )
    {
      ApiMessage[0] = 0;
      v30 = ApiMessage;
      v31 = 512;
      do
      {
        if ( !*v30 )
          break;
        ++v30;
        --v31;
      }
      while ( v31 );
      if ( !v31 )
        goto LABEL_85;
      v32 = v31;
      v33 = &ApiMessage[512 - v31];
      do
      {
        if ( !v1 )
          break;
        if ( !*v2 )
          break;
        *v33++ = *v2++;
        --v1;
        --v32;
      }
      while ( v32 );
      v34 = v33 - 1;
      if ( v32 )
        v34 = v33;
      *v34 = 0;
      if ( v32 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes[2] = KeyHandle;
        LODWORD(ObjectAttributes[1]) = 48;
        ObjectAttributes[3] = &DestinationString;
        LODWORD(ObjectAttributes[4]) = 64;
        *(_OWORD *)&ObjectAttributes[5] = 0;
        LODWORD(ObjectAttributes[0]) = 0;
        v44 = NtOpenKey(&Handle, 0x20019u, (POBJECT_ATTRIBUTES)&ObjectAttributes[1]);
        if ( v44 < 0 )
          v44 = NtCreateKey(
                  &Handle,
                  0x20019u,
                  (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                  0,
                  0,
                  0,
                  (PULONG)ObjectAttributes);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v44 >= 0 )
        {
          v45 = Handle;
        }
        else
        {
          v45 = 0;
          Handle = 0;
        }
        if ( v44 >= 0 )
        {
          v46 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v45,
                          0);
          if ( v46 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v46;
          }
          goto LABEL_17;
        }
      }
      else
      {
LABEL_85:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
    goto LABEL_87;
  }
}

```

## disassembly

```asm
0x1800123e0  mov     r11, rsp
0x1800123e3  push    rbp
0x1800123e4  push    rbx
0x1800123e5  lea     rbp, [r11-3E8h]
0x1800123ec  sub     rsp, 4D8h
0x1800123f3  mov     rax, cs:__security_cookie
0x1800123fa  xor     rax, rsp
0x1800123fd  mov     [rbp+3E0h+var_30], rax
0x180012404  mov     rbx, cs:gNlsProcessLocalCache
0x18001240b  cmp     cs:BasepIsSecureProcess, 0
0x180012412  jnz     loc_180012749
0x180012418  mov     [r11+10h], rdi
0x18001241c  mov     edi, 200h
0x180012421  mov     [r11+18h], r12
0x180012425  xor     r12d, r12d
0x180012428  mov     [r11-18h], r13
0x18001242c  mov     [r11-20h], r14
0x180012430  mov     r14d, 7FFFFFFEh
0x180012436  mov     [r11-28h], r15
0x18001243a  lea     r15, aControlPanelIn; "Control Panel\\International"
0x180012441  test    rbx, rbx
0x180012444  jnz     short loc_18001246C
0x180012446  mov     rax, cs:gNlsProcessLocalCache
0x18001244d  mov     [rsp+4E0h+Handle], r12
0x180012452  test    rax, rax
0x180012455  jz      loc_1800127F6
0x18001245b  mov     rax, cs:gNlsProcessLocalCache
0x180012462  mov     [rsp+4E0h+Handle], rax
0x180012467  mov     rbx, [rsp+4E0h+Handle]
0x18001246c  mov     r13d, 1
0x180012472  test    rbx, rbx
0x180012475  jz      short loc_1800124A0
0x180012477  mov     rax, cs:Event
0x18001247e  test    rax, rax
0x180012481  jz      loc_180012A70
0x180012487  mov     rcx, cs:Event; hHandle
0x18001248e  xor     r8d, r8d; bAlertable
0x180012491  xor     edx, edx; dwMilliseconds
0x180012493  call    WaitForSingleObjectEx
0x180012498  test    eax, eax
0x18001249a  jz      loc_180012A70
0x1800124a0  movzx   eax, cs:word_1803A4276
0x1800124a7  test    ax, ax
0x1800124aa  jz      loc_180012721
0x1800124b0  movzx   eax, cs:word_1803A4274
0x1800124b7  cmp     ax, 3
0x1800124bb  jz      short loc_1800124DB
0x1800124bd  lea     rcx, gNlsProcessCacheLock
0x1800124c4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800124ca  movzx   eax, cs:word_1803A4274
0x1800124d1  cmp     ax, 3
0x1800124d5  jnz     loc_1800127CE
0x1800124db  mov     [rsp+4E0h+arg_0], rsi
0x1800124e3  mov     ecx, 2
0x1800124e8  mov     cs:word_1803A4276, cx
0x1800124ef  cmp     ax, r13w
0x1800124f3  jnz     short loc_180012533
0x1800124f5  xor     edx, edx; Val
0x1800124f7  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x1800124fb  mov     r8d, 3B8h; Size
0x180012501  call    memset_0
0x180012506  mov     edx, 67Ch; BufferSize
0x18001250b  mov     ecx, r13d; ArgumentCount
0x18001250e  call    cs:__imp_CsrAllocateCaptureBuffer
0x180012514  mov     rbx, rax
0x180012517  test    rax, rax
0x18001251a  jnz     loc_180012762
0x180012520  mov     esi, 0C0000017h
0x180012525  cmp     cs:word_1803A4274, r13w
0x18001252d  jz      loc_1800127C1
0x180012533  mov     rax, cs:gNlsProcessLocalCache
0x18001253a  mov     [rsp+4E0h+Handle], r12
0x18001253f  test    rax, rax
0x180012542  jz      loc_1800128E6
0x180012548  mov     rax, cs:gNlsProcessLocalCache
0x18001254f  mov     [rsp+4E0h+Handle], rax
0x180012554  mov     rbx, [rsp+4E0h+Handle]
0x180012559  lea     rcx, word_1803A3BF8
0x180012560  mov     rdx, rbx
0x180012563  mov     r8d, r13d
0x180012566  call    NlsUpdateCacheInfo
0x18001256b  cmp     cs:word_1803A4274, 3
0x180012573  jnz     short loc_180012583
0x180012575  test    rbx, rbx
0x180012578  jz      short loc_180012583
0x18001257a  mov     rcx, rbx; Handle
0x18001257d  call    cs:__imp_NtClose
0x180012583  mov     rsi, [rsp+4E0h+arg_0]
0x18001258b  mov     eax, 0FFFFh
0x180012590  cmp     cs:word_1803A3BF8, ax
0x180012597  jz      loc_1800127EA
0x18001259d  mov     rbx, cs:gpOneCustomHashNode
0x1800125a4  lea     rcx, word_1803A3BFA
0x1800125ab  xor     edx, edx
0x1800125ad  call    GetNamedLocaleHashNode
0x1800125b2  xchg    rax, cs:qword_1803A3BF0
0x1800125b9  test    rbx, rbx
0x1800125bc  jnz     short loc_1800125CE
0x1800125be  cmp     cs:gpOneCustomHashNode, r12
0x1800125c5  jz      short loc_1800125CE
0x1800125c7  mov     cs:gpOneCustomHashNode, r12
0x1800125ce  cmp     cs:qword_1803A3BF0, r12
0x1800125d5  jnz     loc_1800126F9
0x1800125db  mov     rax, cs:gpSysLocHashN
0x1800125e2  test    rax, rax
0x1800125e5  jnz     loc_1800126F2
0x1800125eb  cmp     cs:BasepIsSecureProcess, r12b
0x1800125f2  jnz     loc_1800126F2
0x1800125f8  lea     rcx, gTblPtrsLock
0x1800125ff  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012605  cmp     cs:gpSysLocHashN, r12
0x18001260c  jnz     loc_1800126DE
0x180012612  mov     ebx, cs:gSystemLocale
0x180012618  mov     rax, cs:P
0x18001261f  mov     ecx, ebx
0x180012621  shr     rcx, 7
0x180012625  xor     rcx, rbx
0x180012628  shr     rcx, 7
0x18001262c  xor     rcx, rbx
0x18001262f  and     ecx, 7Fh
0x180012632  mov     rdx, [rax+rcx*8]
0x180012636  test    rdx, rdx
0x180012639  jz      short loc_180012643
0x18001263b  cmp     [rdx], ebx
0x18001263d  jnz     loc_180012A04
0x180012643  mov     cs:gpSysLocHashN, rdx
0x18001264a  test    rdx, rdx
0x18001264d  jnz     loc_1800126DE
0x180012653  test    ebx, 0FFF00000h
0x180012659  jnz     loc_1800129F8
0x18001265f  cmp     cs:BasepIsSecureProcess, r12b
0x180012666  jnz     loc_1800129F8
0x18001266c  mov     ecx, ebx
0x18001266e  call    GetWindowsLocaleData
0x180012673  test    rax, rax
0x180012676  jz      loc_180012A16
0x18001267c  cmp     bx, 7Fh
0x180012680  jz      loc_180012A5E
0x180012686  shr     ebx, 10h
0x180012689  test    bl, 0Fh
0x18001268c  jnz     loc_1800129C5
0x180012692  mov     ecx, [rax]
0x180012694  mov     rax, cs:qword_18039EC90
0x18001269b  add     rax, 2
0x18001269f  lea     rcx, [rax+rcx*2]
0x1800126a3  xor     edx, edx
0x1800126a5  call    MakeNamedLocaleHashNode
0x1800126aa  mov     cs:gpSysLocHashN, rax
0x1800126b1  test    rax, rax
0x1800126b4  jnz     short loc_1800126DE
0x1800126b6  xor     edx, edx
0x1800126b8  lea     rcx, aEnUs; "en-US"
0x1800126bf  call    MakeNamedLocaleHashNode
0x1800126c4  mov     cs:gpSysLocHashN, rax
0x1800126cb  test    rax, rax
0x1800126ce  jnz     short loc_1800126DE
0x1800126d0  mov     rdx, cs:gpInvLocHashN
0x1800126d7  mov     cs:gpSysLocHashN, rdx
0x1800126de  lea     rcx, gTblPtrsLock
0x1800126e5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800126eb  mov     rax, cs:gpSysLocHashN
0x1800126f2  mov     cs:qword_1803A3BF0, rax
0x1800126f9  mov     eax, 2
0x1800126fe  mov     edx, r12d
0x180012701  lock cmpxchg cs:word_1803A4276, dx
0x18001270a  cmp     cs:word_1803A4274, 3
0x180012712  jz      short loc_180012721
0x180012714  lea     rcx, gNlsProcessCacheLock
0x18001271b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012721  mov     r14, [rsp+4E0h+var_18]
0x180012729  mov     r13, [rsp+4D0h]
0x180012731  mov     r12, [rsp+4E0h+arg_10]
0x180012739  mov     rdi, [rsp+4E0h+arg_8]
0x180012741  mov     r15, [rsp+4E0h+var_20]
0x180012749  mov     rcx, [rbp+3E0h+var_30]
0x180012750  xor     rcx, rsp; StackCookie
0x180012753  call    __security_check_cookie
0x180012758  add     rsp, 4D8h
0x18001275f  pop     rbx
0x180012760  pop     rbp
0x180012761  retn
0x180012762  lea     r9, [rbp+3E0h+CapturedData]; CapturedData
0x180012766  xor     edx, edx; MessageBuffer
0x180012768  mov     r8d, 67Ch; MessageLength
0x18001276e  mov     rcx, rbx; CaptureBuffer
0x180012771  call    cs:__imp_CsrCaptureMessageBuffer
0x180012777  mov     r9d, 10h; DataLength
0x18001277d  mov     [rbp+3E0h+var_3E8], 67Ch
0x180012784  mov     r8d, 1001Bh; ApiNumber
0x18001278a  lea     rcx, [rbp+3E0h+ApiMessage]; ApiMessage
0x18001278e  mov     rdx, rbx; CaptureBuffer
0x180012791  call    cs:__imp_CsrClientCallServer
0x180012797  mov     esi, eax
0x180012799  test    eax, eax
0x18001279b  js      short loc_1800127B3
0x18001279d  mov     rdx, [rbp+3E0h+CapturedData]; Src
0x1800127a1  lea     rcx, word_1803A3BF8; void *
0x1800127a8  mov     r8d, 67Ch; Size
0x1800127ae  call    memcpy_0
0x1800127b3  mov     rcx, rbx; CaptureBuffer
0x1800127b6  call    cs:__imp_CsrFreeCaptureBuffer
0x1800127bc  jmp     loc_180012525
0x1800127c1  test    esi, esi
0x1800127c3  jns     loc_180012583
0x1800127c9  jmp     loc_180012533
0x1800127ce  movzx   eax, cs:word_1803A4276
0x1800127d5  test    ax, ax
0x1800127d8  jz      loc_180012714
0x1800127de  movzx   eax, cs:word_1803A4274
0x1800127e5  jmp     loc_1800124DB
0x1800127ea  mov     cs:qword_1803A3BF0, r12
0x1800127f1  jmp     loc_1800125DB
0x1800127f6  mov     rcx, [rsp+4E0h+Handle]
0x1800127fb  test    rcx, rcx
0x1800127fe  jnz     loc_180012C6D
0x180012804  xorps   xmm0, xmm0
0x180012807  mov     [rsp+4E0h+KeyHandle], r12
0x18001280c  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+18h], xmm0
0x180012811  xor     eax, eax
0x180012813  mov     dword ptr [rsp+4E0h+ObjectAttributes], r12d
0x180012818  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+24h], xmm0
0x18001281c  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+8], xmm0
0x180012821  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x180012825  call    GetGlobalizationUserModelType
0x18001282a  cmp     eax, 1
0x18001282d  jnz     loc_180012A41
0x180012833  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x180012838  mov     ecx, 2000000h; DesiredAccess
0x18001283d  call    cs:__imp_RtlOpenCurrentUser
0x180012843  test    eax, eax
0x180012845  js      loc_1800128D7
0x18001284b  mov     [rbp+3E0h+ApiMessage], r12w
0x180012850  lea     rax, [rbp+3E0h+ApiMessage]
0x180012854  mov     rcx, rdi
0x180012857  cmp     [rax], r12w
0x18001285b  jz      short loc_180012867
0x18001285d  add     rax, 2
0x180012861  sub     rcx, 1
0x180012865  jnz     short loc_180012857
0x180012867  mov     r9, rdi
0x18001286a  sub     r9, rcx
0x18001286d  test    rcx, rcx
0x180012870  cmovz   r9, r12
0x180012874  jz      short loc_1800128C7
0x180012876  mov     r8, rdi
0x180012879  mov     rcx, r14
0x18001287c  sub     r8, r9
0x18001287f  mov     rdx, r15
0x180012882  lea     r9, [rbp+r9*2+3E0h+ApiMessage]
0x180012887  jz      short loc_1800128B2
0x180012889  nop     dword ptr [rax+00000000h]
0x180012890  test    rcx, rcx
0x180012893  jz      short loc_1800128B2
0x180012895  movzx   eax, word ptr [rdx]
0x180012898  test    ax, ax
0x18001289b  jz      short loc_1800128B2
0x18001289d  mov     [r9], ax
0x1800128a1  add     rdx, 2
0x1800128a5  add     r9, 2
0x1800128a9  dec     rcx
0x1800128ac  sub     r8, 1
0x1800128b0  jnz     short loc_180012890
0x1800128b2  test    r8, r8
0x1800128b5  lea     rcx, [r9-2]
0x1800128b9  cmovnz  rcx, r9
0x1800128bd  mov     [rcx], r12w
0x1800128c1  jnz     loc_180012BBF
0x1800128c7  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x1800128cc  test    rcx, rcx
0x1800128cf  jz      short loc_1800128D7
0x1800128d1  call    cs:__imp_NtClose
0x1800128d7  mov     ecx, 3F1h; dwErrCode
0x1800128dc  call    SetLastError_0
0x1800128e1  jmp     loc_180012467
0x1800128e6  mov     rcx, [rsp+4E0h+Handle]
0x1800128eb  test    rcx, rcx
0x1800128ee  jnz     loc_180012D45
0x1800128f4  xorps   xmm0, xmm0
0x1800128f7  mov     [rsp+4E0h+KeyHandle], r12
0x1800128fc  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+18h], xmm0
0x180012901  xor     eax, eax
0x180012903  mov     dword ptr [rsp+4E0h+ObjectAttributes], r12d
0x180012908  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+24h], xmm0
0x18001290c  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+8], xmm0
0x180012911  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x180012915  call    GetGlobalizationUserModelType
0x18001291a  cmp     eax, r13d
0x18001291d  jnz     loc_180012B48
0x180012923  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x180012928  mov     ecx, 2000000h; DesiredAccess
0x18001292d  call    cs:__imp_RtlOpenCurrentUser
0x180012933  test    eax, eax
0x180012935  js      short loc_1800129B6
0x180012937  mov     [rbp+3E0h+ApiMessage], r12w
0x18001293c  lea     rax, [rbp+3E0h+ApiMessage]
0x180012940  mov     rcx, rdi
0x180012943  cmp     [rax], r12w
0x180012947  jz      short loc_180012952
0x180012949  add     rax, 2
0x18001294d  sub     rcx, r13
  ... truncated ...
```
