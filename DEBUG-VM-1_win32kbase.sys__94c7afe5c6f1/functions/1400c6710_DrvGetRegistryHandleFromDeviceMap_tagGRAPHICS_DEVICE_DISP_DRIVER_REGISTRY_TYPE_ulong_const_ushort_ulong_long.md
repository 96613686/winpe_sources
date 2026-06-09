# DrvGetRegistryHandleFromDeviceMap(tagGRAPHICS_DEVICE *,_DISP_DRIVER_REGISTRY_TYPE,ulong const *,ushort *,ulong,long *)

- ea: `0x1400c6710`
- end: `0x1400c7138`
- name: `?DrvGetRegistryHandleFromDeviceMap@@YAPEAXPEAUtagGRAPHICS_DEVICE@@W4_DISP_DRIVER_REGISTRY_TYPE@@PEBKPEAGKPEAJ@Z`
- size: `2600`
- prototype: ``
- caller_count: `11`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400c37a0`
- `0x1400c5f88`
- `0x1400c661c`
- `0x1400c8144`
- `0x1400c89ec`
- `0x140101b40`
- `0x1401536c4`
- `0x140164da8`
- `0x14016bff4`
- `0x14017a0b8`
- `0x14018c750`

## callees

- `0x140028ef0`
- `0x140040394`
- `0x1400411c0`
- `0x1400bc7fc`
- `0x1400c6710`
- `0x1400c7290`
- `0x1400cabf0`
- `0x14010f2b0`
- `0x140169ddc`
- `0x1401b404c`
- `0x1401ba240`
- `0x1401c438c`
- `0x1401c45c8`
- `0x1401c49e4`
- `0x1401c4a54`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400c6b24`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c6b24`
- `ntoskrnl!ZwOpenKey` at `0x1400c6883`
- `ntoskrnl!ZwOpenKey` at `0x1400c6aba`
- `ntoskrnl!ZwOpenKey` at `0x1400c6e42`
- `ntoskrnl!ZwOpenKey` at `0x1400c6883`
- `ntoskrnl!ZwOpenKey` at `0x1400c6aba`
- `ntoskrnl!ZwOpenKey` at `0x1400c6e42`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c68f9`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c6ea2`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c68f9`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c6ea2`
- `ntoskrnl!ZwClose` at `0x1400c6969`
- `ntoskrnl!ZwClose` at `0x1400c6f58`
- `ntoskrnl!ZwClose` at `0x1400c7093`
- `ntoskrnl!ZwClose` at `0x1400c6969`
- `ntoskrnl!ZwClose` at `0x1400c6f58`
- `ntoskrnl!ZwClose` at `0x1400c7093`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6a52`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6aa0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6ca5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6ccf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6fd4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c7001`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c707d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6a52`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6aa0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6ca5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6ccf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c6fd4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c7001`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c707d`
- `ntoskrnl!ZwCreateKey` at `0x1400c7042`
- `ntoskrnl!ZwCreateKey` at `0x1400c70bc`
- `ntoskrnl!ZwCreateKey` at `0x1400c7042`
- `ntoskrnl!ZwCreateKey` at `0x1400c70bc`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400c6fe0`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400c6fe0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6846`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c68cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6e02`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6e67`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6846`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c68cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6e02`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6e67`
- `watchdog!WdLogSingleEntry3` at `0x1400c67bb`
- `watchdog!WdLogSingleEntry3` at `0x1400c67bb`
- `watchdog!WdLogSingleEntry1` at `0x1400c6994`
- `watchdog!WdLogSingleEntry1` at `0x1400c70f0`
- `watchdog!WdLogSingleEntry1` at `0x1400c6994`
- `watchdog!WdLogSingleEntry1` at `0x1400c70f0`
- `WIN32K!W32GetSessionState` at `0x1400c679a`
- `WIN32K!W32GetSessionState` at `0x1400c6b4d`
- `WIN32K!W32GetSessionState` at `0x1400c679a`
- `WIN32K!W32GetSessionState` at `0x1400c6b4d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c6b14`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c6b14`

## string_xrefs

- `0x1400c683a`: `\Registry\Machine\Hardware\DeviceMap\Video`
- `0x1400c6a39`: `\Registry\Machine\System\CurrentControlSet`
- `0x1400c6c91`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server\Video\`
- `0x1400c6d12`: `\SERVICES`
- `0x1400c6e5b`: `Service`

## pseudocode

```c
HANDLE __fastcall DrvGetRegistryHandleFromDeviceMap(
        unsigned __int16 *a1,
        int a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        NTSTATUS *a6)
{
  __int64 v6; // rbx
  unsigned int *v9; // r14
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // rdx
  int v14; // esi
  NTSTATUS v15; // ebx
  const WCHAR *v16; // rdx
  unsigned __int16 *v17; // rsi
  WCHAR *v18; // rbx
  ULONG v19; // r15d
  WCHAR *v20; // rdi
  HANDLE result; // rax
  wchar_t *v22; // rsi
  __int64 v23; // r13
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  const WCHAR *v39; // rdx
  __int64 v40; // rcx
  int v41; // r12d
  char *v42; // rcx
  __int64 v43; // rax
  unsigned __int64 Length; // r15
  unsigned __int16 *v45; // rax
  unsigned __int16 *v46; // rbx
  __int64 v47; // r11
  unsigned __int16 *i; // rcx
  unsigned __int16 *v49; // r15
  unsigned __int16 v50; // ax
  int v51; // ecx
  wchar_t *v52; // r15
  wchar_t *v53; // r13
  wchar_t *v54; // rbx
  wchar_t *v55; // rax
  wchar_t *v56; // rdi
  WCHAR *v58; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v59; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v61; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str1; // [rsp+68h] [rbp-98h]
  size_t Size; // [rsp+70h] [rbp-90h]
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp-40h] BYREF
  ULONG v68[2]; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v69; // [rsp+D0h] [rbp-30h]
  HANDLE Handle; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v71; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v72; // [rsp+E8h] [rbp-18h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  unsigned int *v74; // [rsp+F8h] [rbp-8h]
  NTSTATUS *v75; // [rsp+100h] [rbp+0h]
  unsigned __int16 v76[152]; // [rsp+110h] [rbp+10h] BYREF

  v6 = a2;
  v75 = a6;
  v74 = a3;
  v61 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  v71 = a4;
  v9 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v76, 0, sizeof(v76));
  v12 = *(_QWORD *)(W32GetSessionState(v11) + 88);
  v73 = v12;
  WdLogSingleEntry3(5, a1, v6, a3);
  WdLogGlobalForLineNumber = 2078;
  if ( a4 && !a5 )
  {
    v20 = 0;
LABEL_16:
    v15 = -1073741811;
    goto LABEL_17;
  }
  v14 = 0;
  if ( *(_DWORD *)(v12 + 3000) )
  {
    v26 = *(_QWORD *)(W32GetSessionState(0) + 88);
    if ( (unsigned int)UserIsRemoteAndNotDisconnectConnection() )
    {
      if ( *(_QWORD *)(v26 + 3016) )
      {
        v25 = *(_QWORD *)(W32GetUserGdiSessionState() + 40);
        if ( PsGetCurrentProcess() != v25
          && !(unsigned int)UserIsCurrentProcessDwm()
          && (*((_DWORD *)a1 + 40) & 0x4000000) != 0 )
        {
          v28 = 2;
          v29 = v76;
          do
          {
            v30 = *((_OWORD *)a1 + 1);
            *(_OWORD *)v29 = *(_OWORD *)a1;
            v31 = *((_OWORD *)a1 + 2);
            *((_OWORD *)v29 + 1) = v30;
            v32 = *((_OWORD *)a1 + 3);
            *((_OWORD *)v29 + 2) = v31;
            v33 = *((_OWORD *)a1 + 4);
            *((_OWORD *)v29 + 3) = v32;
            v34 = *((_OWORD *)a1 + 5);
            *((_OWORD *)v29 + 4) = v33;
            v35 = *((_OWORD *)a1 + 6);
            *((_OWORD *)v29 + 5) = v34;
            v36 = *((_OWORD *)a1 + 7);
            a1 += 64;
            *((_OWORD *)v29 + 6) = v35;
            *((_OWORD *)v29 + 7) = v36;
            v29 += 64;
            --v28;
          }
          while ( v28 );
          v37 = *((_OWORD *)a1 + 1);
          *(_OWORD *)v29 = *(_OWORD *)a1;
          v38 = *((_OWORD *)a1 + 2);
          a1 = v76;
          *((_OWORD *)v29 + 1) = v37;
          *((_OWORD *)v29 + 2) = v38;
          StringCchCopyW(v76, 0x20u, (const unsigned __int16 *)(v12 + 3024));
          *(_DWORD *)&v76[80] &= ~0x4000000u;
        }
      }
    }
    LODWORD(v6) = a2;
  }
  if ( (*((_DWORD *)a1 + 40) & 8) != 0 )
  {
    v27 = (unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    Str1 = (wchar_t *)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
    if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
    {
      v59 = __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
      wil_details_FeatureReporting_ReportUsageToService(
        &Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
        __PAIR64__(HIDWORD(Str1), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
        3,
        1);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v59,
        3,
        &Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v27, v13);
    v14 = 1;
  }
  v58 = (WCHAR *)PALLOCMEM(512, 1886221383);
  if ( !v58 )
  {
    v15 = -1073741670;
    v20 = 0;
    goto LABEL_17;
  }
  if ( (*((_DWORD *)a1 + 40) & 0x4000000) == 0 || v14 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Hardware\\DeviceMap\\Video");
  }
  else
  {
    if ( (unsigned int)(v6 - 1) <= 1 )
    {
      v15 = -1073741766;
      v20 = v58;
      goto LABEL_17;
    }
    DestinationString.Buffer = v58;
    *(_DWORD *)&DestinationString.Length = 33423360;
    RtlAppendUnicodeToString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server\\Video\\");
    v39 = L"vgastub";
    if ( *(_QWORD *)(v73 + 2976) )
      v39 = *(const WCHAR **)(v73 + 2976);
    RtlAppendUnicodeToString(&DestinationString, v39);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v15 < 0 )
    goto LABEL_106;
  v9 = (unsigned int *)PALLOCMEM(1024, 1886221383);
  if ( !v9 )
  {
    v15 = -1073741670;
    goto LABEL_36;
  }
  if ( (*((_DWORD *)a1 + 40) & 0x4000000) == 0 || (v16 = L"\\Device\\Video0", v14) )
    v16 = a1;
  RtlInitUnicodeString(&DestinationString, v16);
  v15 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, v9, 0x200u, &ResultLength);
  if ( v15 < 0 )
  {
LABEL_106:
    WdLogSingleEntry1(5, v15);
    WdLogGlobalForLineNumber = 2623;
    goto LABEL_36;
  }
  v17 = (unsigned __int16 *)((char *)v9 + v9[2]);
  Destination = 0;
  if ( a2 != 3 )
  {
    v18 = (WCHAR *)(v9 + 128);
    v69 = 0;
    v19 = 0;
    while ( *v17 )
    {
      *v17 = toupper(*v17);
      ++v17;
    }
    v22 = wcsstr((const wchar_t *)((char *)v9 + v9[2]), L"\\CONTROL\\");
    if ( !v22 )
      v22 = wcsstr((const wchar_t *)((char *)v9 + v9[2]), L"\\SERVICES");
    v23 = -1;
    if ( v71 )
    {
      v40 = v9[2];
      v41 = a5 - 1;
      Str1 = v71;
      Handle = 0;
      if ( a5 - 1 > 0x1F )
        v41 = 31;
      v42 = (char *)v9 + v40;
      v43 = -1;
      do
        ++v43;
      while ( *(_WORD *)&v42[2 * v43] );
      *(_QWORD *)v68 = (int)v43;
      Length = 2LL * (int)v43 + 12;
      if ( Length <= 0x66 )
        LODWORD(Length) = 102;
      v45 = (unsigned __int16 *)PALLOCMEM((unsigned int)Length, 1936876615);
      v72 = v45;
      v46 = v45;
      if ( v45 )
      {
        Size = (int)Length;
        memset(v45, 0, (int)Length);
        StringCchCopyW(v46, Size >> 1, (const unsigned __int16 *)((char *)v9 + v9[2]));
        for ( i = &v46[*(_QWORD *)v68 - 1]; i > v46; --i )
        {
          if ( *i == 92 )
            goto LABEL_76;
        }
        if ( *i != 92 )
          goto LABEL_90;
LABEL_76:
        StringCchCopyW(i + 1, v47 - *(_QWORD *)v68, L"Video");
        RtlInitUnicodeString(&DestinationString, v46);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          v68[0] = 0;
          RtlInitUnicodeString(&DestinationString, L"Service");
          memset(v46, 0, Size);
          if ( ZwQueryValueKey(Handle, &DestinationString, KeyValueFullInformation, v46, Length, v68) >= 0 )
          {
            v49 = (unsigned __int16 *)((char *)v46 + *((unsigned int *)v46 + 2));
            v50 = *v49;
            if ( *v49 )
            {
              do
              {
                *v49++ = toupper(v50);
                v50 = *v49;
              }
              while ( *v49 );
              v46 = v72;
            }
            v51 = v41;
            v52 = (unsigned __int16 *)((char *)v46 + *((unsigned int *)v46 + 2));
            LODWORD(Size) = v41;
            if ( v41 )
            {
              v53 = Str1;
              v54 = Str1;
              do
              {
                if ( !*v52 )
                  break;
                *v53 = *v52;
                --v41;
                Str1 = ++v53;
                if ( v41 == v51 - 3 )
                {
                  if ( !wcsnicmp(v54, L"VGA", 3u) )
                    break;
                  v51 = Size;
                }
                ++v52;
              }
              while ( v41 );
              v46 = v72;
              v23 = -1;
            }
          }
          ZwClose(Handle);
        }
LABEL_90:
        GreDeleteFastMutex(v46);
      }
      v18 = (WCHAR *)(v9 + 128);
      v19 = v69;
      *Str1 = 0;
    }
    if ( v74 )
    {
      do
        ++v23;
      while ( v22[v23] );
      StringCchPrintfW(
        &v22[v23],
        512 - ((unsigned int)(((char *)v22 - (char *)v9) >> 1) >> 1) - (unsigned int)v23,
        L"\\Mon%08X",
        *v74);
    }
    Destination.Buffer = v18;
    *(_DWORD *)&Destination.Length = 33423360;
    RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet");
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      if ( (*((_DWORD *)a1 + 40) & 0x800000) != 0 )
      {
        RtlAppendUnicodeToString(&Destination, L"\\Control\\UnitedVideo");
        v19 = (unsigned __int8)RtlIsStateSeparationEnabled() != 0;
      }
      else
      {
        RtlAppendUnicodeToString(&Destination, L"\\Hardware Profiles\\Current\\System\\CurrentControlSet");
      }
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    if ( a2 == 2 )
    {
      ObjectAttributes.SecurityDescriptor = *(PVOID *)(v73 + 1824);
      ObjectAttributes.SecurityQualityOfService = 0;
      v15 = ZwCreateKey(&v61, 0, &ObjectAttributes, 0, 0, v19, 0);
      if ( v15 >= 0 )
      {
        while ( 1 )
        {
          v55 = wcschr(v22 + 1, 0x5Cu);
          v56 = v55;
          if ( v55 )
            *v55 = 0;
          RtlAppendUnicodeToString(&Destination, v22);
          if ( v61 )
            ZwClose(v61);
          v15 = ZwCreateKey(&v61, 0, &ObjectAttributes, 0, 0, v19, 0);
          if ( v15 < 0 )
            break;
          if ( !v56 )
            goto LABEL_36;
          *v56 = 92;
          v22 = v56;
        }
      }
      v61 = 0;
    }
    else
    {
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RtlAppendUnicodeToString(&Destination, v22);
      v15 = ZwOpenKey(&v61, 0x20019u, &ObjectAttributes);
      if ( v15 >= 0 )
      {
LABEL_36:
        v20 = v58;
        goto LABEL_17;
      }
      v15 = -1073741438;
    }
    goto LABEL_106;
  }
  if ( !a4 )
    goto LABEL_36;
  v24 = StringCchCopyNW(a4, a5, v17, 0x7Fu);
  if ( (int)(v24 + 0x80000000) < 0 )
    goto LABEL_36;
  v20 = v58;
  if ( v24 != -2147024774 )
    goto LABEL_16;
LABEL_17:
  if ( v75 )
    *v75 = v15;
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v20 )
    GreDeleteFastMutex(v20);
  if ( v9 )
    GreDeleteFastMutex(v9);
  WdLogSingleEntry1(5, v15);
  result = v61;
  WdLogGlobalForLineNumber = 2647;
  return result;
}

```

## disassembly

```asm
0x1400c6710  push    rbp
0x1400c6712  push    rbx
0x1400c6713  push    rsi
0x1400c6714  push    rdi
0x1400c6715  push    r12
0x1400c6717  push    r13
0x1400c6719  push    r14
0x1400c671b  push    r15
0x1400c671d  lea     rbp, [rsp-158h]
0x1400c6725  sub     rsp, 258h
0x1400c672c  mov     rax, cs:__security_cookie
0x1400c6733  xor     rax, rsp
0x1400c6736  mov     [rbp+190h+var_50], rax
0x1400c673d  mov     rax, [rbp+190h+arg_28]
0x1400c6744  xorps   xmm1, xmm1
0x1400c6747  movsxd  rbx, edx
0x1400c674a  mov     rsi, r8
0x1400c674d  mov     [rbp+190h+var_190], rax
0x1400c6751  mov     rdi, rcx
0x1400c6754  xor     eax, eax
0x1400c6756  mov     [rbp+190h+var_198], r8
0x1400c675a  xorps   xmm0, xmm0
0x1400c675d  mov     [rsp+290h+var_230], rax
0x1400c6762  xor     edx, edx; Val
0x1400c6764  mov     [rsp+290h+KeyHandle], rax
0x1400c6769  mov     r8d, 130h; Size
0x1400c676f  mov     [rbp+190h+var_1D0], eax
0x1400c6772  lea     rcx, [rbp+190h+var_180]; void *
0x1400c6776  mov     [rbp+190h+var_1B0], r9
0x1400c677a  mov     r14d, eax
0x1400c677d  mov     [rsp+290h+var_250], ebx
0x1400c6781  mov     r15, r9
0x1400c6784  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x1400c6789  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm1
0x1400c678d  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm1
0x1400c6791  movups  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400c6795  call    memset
0x1400c679a  call    cs:__imp_W32GetSessionState
0x1400c67a1  nop     dword ptr [rax+rax+00h]
0x1400c67a6  mov     r13, [rax+58h]
0x1400c67aa  mov     [rbp+190h+var_1A0], r13
0x1400c67ae  mov     r8, rbx
0x1400c67b1  lea     ecx, [r14+5]
0x1400c67b5  mov     r9, rsi
0x1400c67b8  mov     rdx, rdi
0x1400c67bb  call    cs:__imp_WdLogSingleEntry3
0x1400c67c2  nop     dword ptr [rax+rax+00h]
0x1400c67c7  mov     r12d, dword ptr [rbp+190h+arg_20]
0x1400c67ce  xor     ecx, ecx
0x1400c67d0  mov     cs:WdLogGlobalForLineNumber, 81Eh
0x1400c67da  test    r15, r15
0x1400c67dd  jnz     loc_1400C693E
0x1400c67e3  mov     esi, ecx
0x1400c67e5  cmp     [r13+0BB8h], ecx
0x1400c67ec  jnz     loc_1400C6B4D
0x1400c67f2  mov     eax, [rdi+0A0h]
0x1400c67f8  mov     r13d, 1
0x1400c67fe  test    al, 8
0x1400c6800  jnz     loc_1400C6B73
0x1400c6806  mov     r13d, 200h
0x1400c680c  mov     edx, 706D7447h
0x1400c6811  mov     ecx, r13d
0x1400c6814  call    PALLOCMEM
0x1400c6819  mov     [rsp+290h+var_248], rax
0x1400c681e  mov     rcx, rax
0x1400c6821  test    rax, rax
0x1400c6824  jz      loc_1400C69D3
0x1400c682a  test    dword ptr [rdi+0A0h], 4000000h
0x1400c6834  jnz     loc_1400C6C7C
0x1400c683a  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\Hardware\\DeviceMa"...
0x1400c6841  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400c6846  call    cs:__imp_RtlInitUnicodeString
0x1400c684d  nop     dword ptr [rax+rax+00h]
0x1400c6852  lea     rax, [rsp+290h+DestinationString]
0x1400c6857  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400c685e  xorps   xmm0, xmm0
0x1400c6861  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400c6865  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400c6869  mov     [rbp+190h+ObjectAttributes.RootDirectory], r14
0x1400c686d  mov     edx, 20019h; DesiredAccess
0x1400c6872  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400c6879  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400c687e  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c6883  call    cs:__imp_ZwOpenKey
0x1400c688a  nop     dword ptr [rax+rax+00h]
0x1400c688f  mov     ebx, eax
0x1400c6891  test    eax, eax
0x1400c6893  js      loc_1400C7112
0x1400c6899  mov     edx, 706D7447h
0x1400c689e  mov     ecx, 400h
0x1400c68a3  call    PALLOCMEM
0x1400c68a8  mov     r14, rax
0x1400c68ab  test    rax, rax
0x1400c68ae  jz      loc_1400C6CED
0x1400c68b4  test    dword ptr [rdi+0A0h], 4000000h
0x1400c68be  jnz     loc_1400C6CFA
0x1400c68c4  mov     rdx, rdi; SourceString
0x1400c68c7  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x1400c68cc  call    cs:__imp_RtlInitUnicodeString
0x1400c68d3  nop     dword ptr [rax+rax+00h]
0x1400c68d8  mov     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1400c68dd  lea     rax, [rbp+190h+var_1D0]
0x1400c68e1  mov     [rsp+290h+ResultLength], rax; ResultLength
0x1400c68e6  lea     rdx, [rsp+290h+DestinationString]; ValueName
0x1400c68eb  mov     r9, r14; KeyValueInformation
0x1400c68ee  mov     [rsp+290h+Length], r13d; Length
0x1400c68f3  mov     r8d, 1; KeyValueInformationClass
0x1400c68f9  call    cs:__imp_ZwQueryValueKey
0x1400c6900  nop     dword ptr [rax+rax+00h]
0x1400c6905  xor     r13d, r13d
0x1400c6908  mov     ebx, eax
0x1400c690a  test    eax, eax
0x1400c690c  js      loc_1400C70E8
0x1400c6912  mov     esi, [r14+8]
0x1400c6916  xorps   xmm0, xmm0
0x1400c6919  add     rsi, r14
0x1400c691c  cmp     [rsp+290h+var_250], 3
0x1400c6921  movups  xmmword ptr [rbp+190h+Destination.Length], xmm0
0x1400c6925  jz      loc_1400C6ADA
0x1400c692b  lea     rbx, [r14+200h]
0x1400c6932  mov     [rbp+190h+var_1C0], r13d
0x1400c6936  mov     r15d, r13d
0x1400c6939  jmp     loc_1400C69F2
0x1400c693e  test    r12d, r12d
0x1400c6941  jnz     loc_1400C67E3
0x1400c6947  xor     r13d, r13d
0x1400c694a  mov     edi, r13d
0x1400c694d  mov     ebx, 0C000000Dh
0x1400c6952  mov     rax, [rbp+190h+var_190]
0x1400c6956  test    rax, rax
0x1400c6959  jnz     loc_1400C7117
0x1400c695f  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x1400c6964  test    rcx, rcx
0x1400c6967  jz      short loc_1400C697A
0x1400c6969  call    cs:__imp_ZwClose
0x1400c6970  nop     dword ptr [rax+rax+00h]
0x1400c6975  mov     [rsp+290h+KeyHandle], r13
0x1400c697a  test    rdi, rdi
0x1400c697d  jnz     loc_1400C711E
0x1400c6983  test    r14, r14
0x1400c6986  jnz     loc_1400C712B
0x1400c698c  movsxd  rdx, ebx
0x1400c698f  mov     ecx, 5
0x1400c6994  call    cs:__imp_WdLogSingleEntry1
0x1400c699b  nop     dword ptr [rax+rax+00h]
0x1400c69a0  mov     rax, [rsp+290h+var_230]
0x1400c69a5  mov     cs:WdLogGlobalForLineNumber, 0A57h
0x1400c69af  mov     rcx, [rbp+190h+var_50]
0x1400c69b6  xor     rcx, rsp; StackCookie
0x1400c69b9  call    __security_check_cookie
0x1400c69be  add     rsp, 258h
0x1400c69c5  pop     r15
0x1400c69c7  pop     r14
0x1400c69c9  pop     r13
0x1400c69cb  pop     r12
0x1400c69cd  pop     rdi
0x1400c69ce  pop     rsi
0x1400c69cf  pop     rbx
0x1400c69d0  pop     rbp
0x1400c69d1  retn
0x1400c69d3  mov     ebx, 0C000009Ah
0x1400c69d8  mov     rdi, rax
0x1400c69db  xor     r13d, r13d
0x1400c69de  jmp     loc_1400C6952
0x1400c69e3  movzx   ecx, ax; C
0x1400c69e6  call    toupper
0x1400c69eb  mov     [rsi], ax
0x1400c69ee  lea     rsi, [rsi+2]
0x1400c69f2  movzx   eax, word ptr [rsi]
0x1400c69f5  test    ax, ax
0x1400c69f8  jnz     short loc_1400C69E3
0x1400c69fa  mov     ecx, [r14+8]
0x1400c69fe  lea     rdx, aControl; "\\CONTROL\\"
0x1400c6a05  add     rcx, r14; Str
0x1400c6a08  call    wcsstr
0x1400c6a0d  mov     rsi, rax
0x1400c6a10  test    rax, rax
0x1400c6a13  jz      loc_1400C6D0E
0x1400c6a19  mov     rax, [rbp+190h+var_1B0]
0x1400c6a1d  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400c6a21  xor     edx, edx
0x1400c6a23  test    rax, rax
0x1400c6a26  jnz     loc_1400C6D29
0x1400c6a2c  mov     r9, [rbp+190h+var_198]
0x1400c6a30  test    r9, r9
0x1400c6a33  jnz     loc_1400C6F86
0x1400c6a39  lea     rdx, Src; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400c6a40  mov     [rbp+190h+Destination.Buffer], rbx
0x1400c6a44  lea     rcx, [rbp+190h+Destination]; Destination
0x1400c6a48  mov     dword ptr [rbp+190h+Destination.Length], 1FE0000h
0x1400c6a4f  xor     r13d, r13d
0x1400c6a52  call    cs:__imp_RtlAppendUnicodeToString
0x1400c6a59  nop     dword ptr [rax+rax+00h]
0x1400c6a5e  mov     ebx, [rsp+290h+var_250]
0x1400c6a62  lea     eax, [rbx-1]
0x1400c6a65  cmp     eax, 1
0x1400c6a68  jbe     loc_1400C6FBD
0x1400c6a6e  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400c6a75  lea     rax, [rbp+190h+Destination]
0x1400c6a79  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x1400c6a7d  mov     [rbp+190h+ObjectAttributes.RootDirectory], r13
0x1400c6a81  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x1400c6a88  cmp     ebx, 2
0x1400c6a8b  jz      loc_1400C7012
0x1400c6a91  xorps   xmm0, xmm0
0x1400c6a94  lea     rcx, [rbp+190h+Destination]; Destination
0x1400c6a98  mov     rdx, rsi; Source
0x1400c6a9b  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c6aa0  call    cs:__imp_RtlAppendUnicodeToString
0x1400c6aa7  nop     dword ptr [rax+rax+00h]
0x1400c6aac  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x1400c6ab0  mov     edx, 20019h; DesiredAccess
0x1400c6ab5  lea     rcx, [rsp+290h+var_230]; KeyHandle
0x1400c6aba  call    cs:__imp_ZwOpenKey
0x1400c6ac1  nop     dword ptr [rax+rax+00h]
0x1400c6ac6  mov     ebx, eax
0x1400c6ac8  test    eax, eax
0x1400c6aca  js      loc_1400C710B
0x1400c6ad0  mov     rdi, [rsp+290h+var_248]
0x1400c6ad5  jmp     loc_1400C6952
0x1400c6ada  test    r15, r15
0x1400c6add  jz      short loc_1400C6AD0
0x1400c6adf  mov     rdx, r12; unsigned __int64
0x1400c6ae2  mov     r9d, 7Fh; unsigned __int64
0x1400c6ae8  mov     r8, rsi; unsigned __int16 *
0x1400c6aeb  mov     rcx, r15; unsigned __int16 *
0x1400c6aee  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400c6af3  mov     edx, 80000000h
0x1400c6af8  lea     ecx, [rax+rdx]
0x1400c6afb  test    edx, ecx
0x1400c6afd  jnz     short loc_1400C6AD0
0x1400c6aff  mov     rdi, [rsp+290h+var_248]
0x1400c6b04  cmp     eax, 8007007Ah
0x1400c6b09  jz      loc_1400C6952
0x1400c6b0f  jmp     loc_1400C694D
0x1400c6b14  call    cs:__imp_W32GetUserGdiSessionState
0x1400c6b1b  nop     dword ptr [rax+rax+00h]
0x1400c6b20  mov     rbx, [rax+28h]
0x1400c6b24  call    cs:__imp_PsGetCurrentProcess
0x1400c6b2b  nop     dword ptr [rax+rax+00h]
0x1400c6b30  cmp     rax, rbx
0x1400c6b33  jz      loc_1400C6C2F
0x1400c6b39  call    UserIsCurrentProcessDwm
0x1400c6b3e  xor     ecx, ecx
0x1400c6b40  test    eax, eax
0x1400c6b42  jz      short loc_1400C6B98
0x1400c6b44  mov     ebx, [rsp+290h+var_250]
0x1400c6b48  jmp     loc_1400C67F2
0x1400c6b4d  call    cs:__imp_W32GetSessionState
0x1400c6b54  nop     dword ptr [rax+rax+00h]
0x1400c6b59  mov     rbx, [rax+58h]
0x1400c6b5d  call    UserIsRemoteAndNotDisconnectConnection
0x1400c6b62  xor     ecx, ecx
0x1400c6b64  test    eax, eax
0x1400c6b66  jz      short loc_1400C6B44
0x1400c6b68  cmp     [rbx+0BC8h], rcx
0x1400c6b6f  jz      short loc_1400C6B44
0x1400c6b71  jmp     short loc_1400C6B14
0x1400c6b73  mov     [rsp+290h+Str1], rcx
0x1400c6b78  mov     ecx, cs:Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState
0x1400c6b7e  mov     dword ptr [rsp+290h+Str1], ecx
0x1400c6b82  test    cl, 10h
0x1400c6b85  jz      loc_1400C6C36
0x1400c6b8b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400c6b90  mov     esi, r13d
0x1400c6b93  jmp     loc_1400C6806
0x1400c6b98  test    dword ptr [rdi+0A0h], 4000000h
0x1400c6ba2  jz      short loc_1400C6B44
0x1400c6ba4  mov     ecx, 2
0x1400c6ba9  lea     rax, [rbp+190h+var_180]
0x1400c6bad  lea     edx, [rcx+7Eh]
0x1400c6bb0  movups  xmm0, xmmword ptr [rdi]
0x1400c6bb3  movups  xmm1, xmmword ptr [rdi+10h]
0x1400c6bb7  movups  xmmword ptr [rax], xmm0
0x1400c6bba  movups  xmm0, xmmword ptr [rdi+20h]
0x1400c6bbe  movups  xmmword ptr [rax+10h], xmm1
0x1400c6bc2  movups  xmm1, xmmword ptr [rdi+30h]
0x1400c6bc6  movups  xmmword ptr [rax+20h], xmm0
0x1400c6bca  movups  xmm0, xmmword ptr [rdi+40h]
0x1400c6bce  movups  xmmword ptr [rax+30h], xmm1
0x1400c6bd2  movups  xmm1, xmmword ptr [rdi+50h]
0x1400c6bd6  movups  xmmword ptr [rax+40h], xmm0
0x1400c6bda  movups  xmm0, xmmword ptr [rdi+60h]
0x1400c6bde  movups  xmmword ptr [rax+50h], xmm1
0x1400c6be2  movups  xmm1, xmmword ptr [rdi+70h]
0x1400c6be6  add     rdi, rdx
0x1400c6be9  movups  xmmword ptr [rax+60h], xmm0
0x1400c6bed  movups  xmmword ptr [rax+70h], xmm1
0x1400c6bf1  add     rax, rdx
0x1400c6bf4  sub     rcx, 1
0x1400c6bf8  jnz     short loc_1400C6BB0
0x1400c6bfa  movups  xmm0, xmmword ptr [rdi]
0x1400c6bfd  lea     edx, [rcx+20h]; unsigned __int64
0x1400c6c00  movups  xmm1, xmmword ptr [rdi+10h]
0x1400c6c04  lea     r8, [r13+0BD0h]; unsigned __int16 *
0x1400c6c0b  movups  xmmword ptr [rax], xmm0
0x1400c6c0e  lea     rcx, [rbp+190h+var_180]; unsigned __int16 *
0x1400c6c12  movups  xmm0, xmmword ptr [rdi+20h]
0x1400c6c16  lea     rdi, [rbp+190h+var_180]
0x1400c6c1a  movups  xmmword ptr [rax+10h], xmm1
  ... truncated ...
```
