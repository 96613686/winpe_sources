# RIMRegisterForInputWithCallbacks

- ea: `0x140161f70`
- end: `0x140162fc0`
- name: `RIMRegisterForInputWithCallbacks`
- size: `4176`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x140161f00`
- `0x1401b3864`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140066bf0`
- `0x140071828`
- `0x1400718f0`
- `0x140076420`
- `0x14009e3c0`
- `0x14009ff00`
- `0x1400b7e20`
- `0x1400cb450`
- `0x140117a60`
- `0x140161f70`
- `0x140162fd0`
- `0x1401649c8`
- `0x14016bca0`
- `0x140171480`
- `0x14017377c`
- `0x1401798f8`
- `0x1401aa4fc`
- `0x1401aaa7c`
- `0x1401b3fb4`
- `0x1401b58f8`
- `0x1401bfe50`
- `0x1401c6588`
- `0x1401ff930`
- `0x140202f0c`
- `0x140238b10`
- `0x1402bd208`
- `0x1402bd244`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140162aea`
- `ntoskrnl!ProbeForRead` at `0x140162aea`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140162bba`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140162bba`
- `ntoskrnl!ZwClose` at `0x140162eb3`
- `ntoskrnl!ZwClose` at `0x140162ecc`
- `ntoskrnl!ZwClose` at `0x140162ee5`
- `ntoskrnl!ZwClose` at `0x140162eb3`
- `ntoskrnl!ZwClose` at `0x140162ecc`
- `ntoskrnl!ZwClose` at `0x140162ee5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140162562`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140162562`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016258a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016258a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140162b5c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140162b5c`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14016286a`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14016286a`
- `ntoskrnl!ObCloseHandle` at `0x140162f01`
- `ntoskrnl!ObCloseHandle` at `0x140162f01`
- `ntoskrnl!ObfDereferenceObject` at `0x140162d4a`
- `ntoskrnl!ObfDereferenceObject` at `0x140162d4a`
- `WIN32K!W32GetUserSessionState` at `0x14016207b`
- `WIN32K!W32GetUserSessionState` at `0x140162120`
- `WIN32K!W32GetUserSessionState` at `0x1401621b4`
- `WIN32K!W32GetUserSessionState` at `0x140162229`
- `WIN32K!W32GetUserSessionState` at `0x1401622a4`
- `WIN32K!W32GetUserSessionState` at `0x14016232a`
- `WIN32K!W32GetUserSessionState` at `0x1401623bf`
- `WIN32K!W32GetUserSessionState` at `0x1401629a4`
- `WIN32K!W32GetUserSessionState` at `0x140162c08`
- `WIN32K!W32GetUserSessionState` at `0x140162f56`
- `WIN32K!W32GetUserSessionState` at `0x14016207b`
- `WIN32K!W32GetUserSessionState` at `0x140162120`
- `WIN32K!W32GetUserSessionState` at `0x1401621b4`
- `WIN32K!W32GetUserSessionState` at `0x140162229`
- `WIN32K!W32GetUserSessionState` at `0x1401622a4`
- `WIN32K!W32GetUserSessionState` at `0x14016232a`
- `WIN32K!W32GetUserSessionState` at `0x1401623bf`
- `WIN32K!W32GetUserSessionState` at `0x1401629a4`
- `WIN32K!W32GetUserSessionState` at `0x140162c08`
- `WIN32K!W32GetUserSessionState` at `0x140162f56`

## pseudocode

```c
__int64 __fastcall RIMRegisterForInputWithCallbacks(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12,
        HANDLE *a13)
{
  bool v15; // r12
  __int64 UserSessionState; // rax
  int v17; // r8d
  int v18; // edx
  bool v19; // r15
  __int64 v20; // rax
  int v21; // r8d
  int v22; // edx
  char v23; // bl
  bool v24; // si
  __int64 v25; // rax
  int v26; // edx
  int v27; // r8d
  char v28; // r12
  bool v29; // r13
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  bool v33; // r13
  __int64 v34; // rax
  int v35; // r8d
  int v36; // edx
  int v38; // eax
  void *KernelSemaphore; // rsi
  __int64 v40; // r15
  void *v41; // rcx
  unsigned int i; // edx
  void *v43; // rax
  __int64 j; // rbx
  PVOID v45; // rcx
  int v46; // r15d
  int v47; // ecx
  bool v48; // sf
  int v49; // edx
  int v50; // r8d
  int v51; // r9d
  char *v52; // rsi
  unsigned int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  void *v58; // rax
  int v59; // ecx
  unsigned int v60; // r8d
  __int64 v61; // r9
  unsigned int k; // ebx
  __int64 v63; // rax
  int ULongFromUser; // ebx
  void *v65; // rcx
  void *v66; // rbx
  __int64 n; // r13
  __int64 m; // r12
  PVOID v69; // rcx
  char v70; // bl
  bool v71; // r12
  __int64 v72; // rax
  int v73; // r8d
  int v74; // edx
  int TableContext; // [rsp+20h] [rbp-158h]
  int v76; // [rsp+28h] [rbp-150h]
  int v77; // [rsp+30h] [rbp-148h]
  __int16 v78; // [rsp+30h] [rbp-148h]
  int v79; // [rsp+38h] [rbp-140h]
  bool v80; // [rsp+60h] [rbp-118h]
  bool v81; // [rsp+60h] [rbp-118h]
  bool v82; // [rsp+60h] [rbp-118h]
  int v83; // [rsp+68h] [rbp-110h]
  unsigned int v85; // [rsp+74h] [rbp-104h]
  __int64 v86; // [rsp+78h] [rbp-100h]
  bool v87; // [rsp+80h] [rbp-F8h]
  HANDLE v88; // [rsp+88h] [rbp-F0h] BYREF
  PVOID Object; // [rsp+90h] [rbp-E8h] BYREF
  UNICODE_STRING SourceString; // [rsp+98h] [rbp-E0h] BYREF
  void *v91; // [rsp+A8h] [rbp-D0h]
  HANDLE *v92; // [rsp+B0h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned int v94; // [rsp+C8h] [rbp-B0h]
  int v95; // [rsp+CCh] [rbp-ACh]
  HANDLE Handle; // [rsp+D0h] [rbp-A8h] BYREF
  HANDLE v97; // [rsp+D8h] [rbp-A0h] BYREF
  HANDLE v98; // [rsp+E0h] [rbp-98h] BYREF
  __int64 v99; // [rsp+E8h] [rbp-90h]
  __int64 v100; // [rsp+F0h] [rbp-88h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+F8h] [rbp-80h]
  __int128 v102; // [rsp+100h] [rbp-78h]
  __int64 v103; // [rsp+110h] [rbp-68h]
  PVOID Buffer[3]; // [rsp+118h] [rbp-60h] BYREF

  v99 = a4;
  v86 = a2;
  v100 = a2;
  *(_QWORD *)&SourceString.Length = a4;
  v103 = a7;
  *(_QWORD *)&v102 = a8;
  v92 = a13;
  Handle = (HANDLE)-1LL;
  v97 = (HANDLE)-1LL;
  v98 = (HANDLE)-1LL;
  v88 = (HANDLE)-1LL;
  memset(Buffer, 0, sizeof(Buffer));
  v15 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
    LOBYTE(v17) = v80;
    LOBYTE(v18) = v15;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      11,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    a2 = v86;
  }
  if ( (a1 & 0xFFFFFFC0) != 0 )
  {
    v19 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
    v81 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
      LOBYTE(v21) = v81;
      LOBYTE(v22) = v19;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v22,
        v21,
        *(_QWORD *)(v20 + 19408),
        2,
        1,
        12,
        (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
        a1);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v23 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
    v78 = 13;
LABEL_60:
    LOBYTE(v27) = v24;
    LOBYTE(v26) = v23;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      *(_QWORD *)(v25 + 19408),
      4,
      1,
      v78,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    return 3221225485LL;
  }
  if ( a2 && (!a1 || ((a1 - 1) & a1) != 0 || a3) )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v28 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
    {
      v28 = 0;
    }
    v29 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v30 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
      LOBYTE(v31) = v29;
      LOBYTE(v32) = v28;
      WPP_RECORDER_AND_TRACE_SF_qDd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 19408),
        TableContext,
        v76,
        v77,
        v79,
        v86,
        a1,
        a3);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v23 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
    v78 = 15;
    goto LABEL_60;
  }
  v87 = 0;
  if ( a3 )
  {
    if ( (a1 & 0x20) == 0 )
    {
      v33 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
      v82 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v34 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
        LOBYTE(v35) = v82;
        LOBYTE(v36) = v33;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v36,
          v35,
          *(_QWORD *)(v34 + 19408),
          2,
          1,
          16,
          (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
          a1,
          a3);
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
      {
        v23 = 0;
      }
      v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225485LL;
      v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
      v78 = 17;
      goto LABEL_60;
    }
    if ( a12 )
    {
      v38 = rimCheckForRegistrationConflicts(a1);
      if ( v38 == 1 )
        return 3221225506LL;
      v87 = v38 == 0;
    }
  }
  KernelSemaphore = (void *)CreateKernelSemaphore(0, -1);
  *(_QWORD *)&DestinationString.Length = KernelSemaphore;
  if ( !KernelSemaphore )
    return 3221225495LL;
  v40 = CreateKernelSemaphore(0, 0x7FFFFFFF);
  v91 = (void *)v40;
  if ( !v40 )
  {
    v41 = KernelSemaphore;
LABEL_70:
    GreDeleteFastMutex(v41);
    return 3221225495LL;
  }
  for ( i = 0; ; i = v85 + 1 )
  {
    v85 = i;
    if ( i > 2 )
      break;
    v43 = Win32AllocPoolZInitImpl(0x40u, 0x68u, 0x63704152u);
    Buffer[v85] = v43;
    if ( !v43 )
    {
      for ( j = 0; j != 3; ++j )
      {
        v45 = Buffer[j];
        if ( v45 )
          GreDeleteFastMutex(v45);
      }
      GreDeleteFastMutex(KernelSemaphore);
      v41 = (void *)v40;
      goto LABEL_70;
    }
  }
  LODWORD(Object) = a12 != 0;
  v46 = rimConvertUserToKernelEventHandle(a6, &Handle);
  v83 = rimConvertUserToKernelTimerHandle(v103, &v97);
  v47 = rimConvertUserToKernelSemaphoreHandle(v102, &v98);
  v48 = v46 < 0;
  if ( v46 < 0 )
    goto LABEL_131;
  if ( v83 < 0 || v47 < 0 )
  {
    v48 = v46 < 0;
LABEL_131:
    if ( !v48 )
      v46 = v83;
    goto LABEL_133;
  }
  KeEnterCriticalRegion();
  v46 = RawInputManagerObjectCreate((int)Object, v49, v50, v51, &v88);
  KeLeaveCriticalRegion();
  if ( v46 >= 0 )
  {
    Object = 0;
    v46 = RawInputManagerObjectResolveHandle(v88, 3, 1, &Object);
    if ( v46 >= 0 )
    {
      v52 = (char *)Object;
      *((_QWORD *)Object + 8) = v88;
      *((_WORD *)v52 + 36) = 0;
      v52[74] = 0;
      *((_DWORD *)v52 + 19) = a1;
      *((_QWORD *)v52 + 14) = a5;
      *((_QWORD *)v52 + 12) = 0;
      *((_QWORD *)v52 + 13) = 0;
      *((_QWORD *)v52 + 94) = 0;
      *((_QWORD *)v52 + 95) = 0;
      *((_QWORD *)v52 + 52) = 0;
      *((_DWORD *)v52 + 100) = 0;
      *((_QWORD *)v52 + 51) = 0;
      *((_QWORD *)v52 + 54) = v52 + 424;
      *((_QWORD *)v52 + 53) = v52 + 424;
      *((_QWORD *)v52 + 56) = v52 + 440;
      *((_QWORD *)v52 + 55) = v52 + 440;
      RIMCheckPressureDefaultSetting(v52);
      *((_DWORD *)v52 + 262) = a12 == 0;
      *((_QWORD *)v52 + 132) = *(_QWORD *)&DestinationString.Length;
      *((_DWORD *)v52 + 266) = 0;
      *((_QWORD *)v52 + 136) = v91;
      *((_DWORD *)v52 + 274) = 0;
      v53 = 0;
      v54 = 0;
      do
      {
        v55 = 32 * v54;
        *(_OWORD *)&v52[v55 + 120] = *(_OWORD *)&(&off_140251120)[4 * v54];
        *(_OWORD *)&v52[v55 + 136] = *((_OWORD *)&off_140251120 + 2 * v54 + 1);
        *(_QWORD *)&v52[8 * v54 + 216] = 0;
        *(_QWORD *)&v52[8 * v54 + 304] = Buffer[v54];
        *(_DWORD *)&v52[4 * v54 + 288] = 0;
        Buffer[v54] = 0;
        *(_DWORD *)&v52[16 * v54 + 248] = v53;
        *(_QWORD *)&v52[16 * v54 + 240] = v52;
        ++v53;
        ++v54;
      }
      while ( v53 <= 2 );
      *((_QWORD *)v52 + 41) = v97;
      *((_QWORD *)v52 + 49) = a9;
      *((_QWORD *)v52 + 42) = Handle;
      v52[384] = v87;
      v52[385] = 0;
      *((_QWORD *)v52 + 43) = 0;
      *((_QWORD *)v52 + 44) = 0;
      *((_QWORD *)v52 + 45) = v98;
      *((_QWORD *)v52 + 47) = v52 + 368;
      *((_QWORD *)v52 + 46) = v52 + 368;
      v52[768] = 0;
      *((_QWORD *)v52 + 112) = 0;
      v56 = ((unsigned __int64)(500 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v52 + 111) = (v56 + ((unsigned __int64)(500 * gliQpcFreq.QuadPart - v56) >> 1)) >> 9;
      v57 = ((unsigned __int64)(5000 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v52 + 115) = (v57 + ((unsigned __int64)(5000 * gliQpcFreq.QuadPart - v57) >> 1)) >> 9;
      *((_QWORD *)v52 + 102) = a10;
      *((_QWORD *)v52 + 103) = a11;
      *((_WORD *)v52 + 352) = 0;
      *(_QWORD *)(v52 + 708) = 1;
      *((_QWORD *)v52 + 99) = 0;
      *((_QWORD *)v52 + 91) = v52 + 720;
      *((_QWORD *)v52 + 90) = v52 + 720;
      *((_QWORD *)v52 + 93) = v52 + 736;
      *((_QWORD *)v52 + 92) = v52 + 736;
      *((_QWORD *)v52 + 98) = v52 + 776;
      *((_QWORD *)v52 + 97) = v52 + 776;
      *((_QWORD *)v52 + 101) = v52 + 800;
      *((_QWORD *)v52 + 100) = v52 + 800;
      *((_QWORD *)v52 + 135) = v52 + 1072;
      *((_QWORD *)v52 + 134) = v52 + 1072;
      RtlInitializeGenericTableAvl(
        (PRTL_AVL_TABLE)(v52 + 928),
        rimUserMemAllocNodeCompare,
        rimUserMemAllocNodeAlloc,
        rimUserMemAllocNodeFree,
        0);
      *((_DWORD *)v52 + 20) = a3;
      if ( a3 )
      {
        if ( v86 )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 458);
        if ( 4 * (unsigned __int64)a3 > 0xFFFFFFFF )
        {
          v46 = -1073741811;
        }
        else
        {
          v58 = Win32AllocPoolZInitImpl(0x100u, 4 * a3, 0x70617552u);
          *((_QWORD *)v52 + 11) = v58;
          v59 = a12;
          if ( !v58 )
          {
            v46 = -1073741801;
LABEL_103:
            v63 = v86;
LABEL_104:
            if ( v63 )
            {
              SourceString = 0;
              p_DestinationString = 0;
              DestinationString = 0;
              if ( v59 )
              {
                v102 = 0;
                ULongFromUser = RtlReadULongFromUser(v86);
                LODWORD(v102) = ULongFromUser;
                *((_QWORD *)&v102 + 1) = RtlReadULong64FromUser(v86 + 8);
                *(_DWORD *)&SourceString.Length = ULongFromUser;
                *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v102);
                SourceString.Buffer = (PWSTR)*((_QWORD *)&v102 + 1);
                ProbeForRead(*((volatile void **)&v102 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
                if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
                {
                  if ( (SourceString.Length & 1) != 0 )
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 521);
                  ExRaiseAccessViolation();
                }
                if ( SourceString.Length )
                {
                  DestinationString.MaximumLength = SourceString.Length;
                  DestinationString.Length = SourceString.Length;
                  DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
                  if ( DestinationString.Buffer )
                  {
                    RtlCopyUnicodeString(&DestinationString, &SourceString);
                    p_DestinationString = &DestinationString;
                  }
                }
                else
                {
                  v46 = -1073741801;
                  v95 = -1073741801;
                }
              }
              if ( v46 >= 0 )
              {
                RIMLockExclusive(v52 + 96);
                v46 = RIMDiscoverSpecificDevice((struct RawInputManagerObject *)v52);
                RIMUnlockExclusive(v52 + 96);
                if ( v46 < 0 )
                {
                  if ( *((_QWORD *)v52 + 11) )
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 558);
                  v65 = (void *)*((_QWORD *)v52 + 51);
                  if ( v65 )
                  {
                    GreDeleteFastMutex(v65);
                    *((_QWORD *)v52 + 51) = 0;
                  }
                  *((_QWORD *)v52 + 41) = -1;
                  *((_QWORD *)v52 + 42) = -1;
                  *((_QWORD *)v52 + 45) = -1;
                }
              }
              if ( DestinationString.Buffer )
                GreDeleteFastMutex(DestinationString.Buffer);
            }
            else
            {
              if ( v46 >= 0 && !v52[384] )
                RIMDiscoverDevicesOfInputType(v52);
              RIMIDEAdoptOrphanedRimDevs(v52);
            }
            v66 = 0;
            InputTraceLogging::RIM::RawInputManagerObjectUsed((const struct RawInputManagerObject *)v52);
            ObfDereferenceObject(v52);
            KernelSemaphore = 0;
            goto LABEL_134;
          }
          if ( a12 )
          {
            for ( k = 0; ; ++k )
            {
              v94 = k;
              if ( k >= a3 )
                break;
              RtlCopyFromUser((void *)(*((_QWORD *)v52 + 11) + 4LL * k), (void *)(v99 + 4LL * k), 4u);
            }
            v63 = v86;
            v59 = a12;
            goto LABEL_104;
          }
          v60 = 0;
          v61 = v99;
          do
          {
            *(_DWORD *)(*((_QWORD *)v52 + 11) + 4LL * v60) = *(_DWORD *)(v61 + 4LL * v60);
            ++v60;
          }
          while ( v60 < a3 );
        }
      }
      v59 = a12;
      goto LABEL_103;
    }
  }
LABEL_133:
  v66 = v91;
LABEL_134:
  if ( v46 < 0 )
  {
    for ( m = 0; m != 3; ++m )
    {
      v69 = Buffer[m];
      if ( v69 )
        GreDeleteFastMutex(v69);
    }
    if ( KernelSemaphore )
      GreDeleteFastMutex(KernelSemaphore);
    if ( v66 )
      GreDeleteFastMutex(v66);
    if ( Handle != (HANDLE)-1LL )
      ZwClose(Handle);
    if ( v97 != (HANDLE)-1LL )
      ZwClose(v97);
    if ( v98 != (HANDLE)-1LL )
      ZwClose(v98);
    if ( v88 != (HANDLE)-1LL )
      ObCloseHandle(v88, 1);
  }
  else
  {
    for ( n = 0; n != 3; ++n )
    {
      if ( Buffer[n] )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 609);
    }
    if ( KernelSemaphore )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 612);
    if ( v66 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 613);
    if ( a12 )
      RtlWriteULong64ToUser(v92, v88);
    else
      *v92 = v88;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v70 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v70 = 0;
  }
  v71 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v70 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v72 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
    LOBYTE(v73) = v71;
    LOBYTE(v74) = v70;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v74,
      v73,
      *(_QWORD *)(v72 + 19408),
      4,
      1,
      20,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v46);
  }
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x140161f70  mov     r11, rsp
0x140161f73  push    rbx
0x140161f74  push    rsi
0x140161f75  push    rdi
0x140161f76  push    r12
0x140161f78  push    r13
0x140161f7a  push    r14
0x140161f7c  push    r15
0x140161f7e  sub     rsp, 140h
0x140161f85  mov     rax, cs:__security_cookie
0x140161f8c  xor     rax, rsp
0x140161f8f  mov     [rsp+178h+var_48], rax
0x140161f97  mov     rax, r9
0x140161f9a  mov     [rsp+178h+var_90], rax
0x140161fa2  mov     r15d, r8d
0x140161fa5  mov     [rsp+178h+var_108], r8d
0x140161faa  mov     [rsp+178h+var_100], rdx
0x140161faf  mov     ebx, ecx
0x140161fb1  mov     [rsp+178h+var_88], rdx
0x140161fb9  mov     qword ptr [rsp+178h+SourceString.Length], rax
0x140161fc1  mov     rax, [rsp+178h+arg_28]
0x140161fc9  mov     [rsp+178h+var_110], rax
0x140161fce  mov     rax, [rsp+178h+arg_30]
0x140161fd6  mov     [rsp+178h+var_68], rax
0x140161fde  mov     rax, [rsp+178h+arg_38]
0x140161fe6  mov     qword ptr [rsp+178h+var_78], rax
0x140161fee  mov     rax, [rsp+178h+arg_60]
0x140161ff6  mov     [rsp+178h+var_C8], rax
0x140161ffe  or      r13, 0FFFFFFFFFFFFFFFFh
0x140162002  mov     [r11-0A8h], r13
0x140162009  mov     [r11-0A0h], r13
0x140162010  mov     [r11-98h], r13
0x140162017  mov     [r11-0F0h], r13
0x14016201e  xorps   xmm0, xmm0
0x140162021  xor     eax, eax
0x140162023  movups  xmmword ptr [r11-60h], xmm0
0x140162028  mov     [r11-50h], rax
0x14016202c  lea     rsi, WPP_GLOBAL_Control
0x140162033  mov     rcx, cs:WPP_GLOBAL_Control
0x14016203a  lea     r14d, [r13+2]
0x14016203e  cmp     rcx, rsi
0x140162041  jz      short loc_140162058
0x140162043  mov     eax, [rcx+2Ch]
0x140162046  test    r14b, al
0x140162049  jz      short loc_140162058
0x14016204b  cmp     byte ptr [rcx+29h], 4
0x14016204f  jb      short loc_140162058
0x140162051  mov     r12b, r14b
0x140162054  xor     edi, edi
0x140162056  jmp     short loc_14016205D
0x140162058  xor     edi, edi
0x14016205a  mov     r12b, dil
0x14016205d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162064  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016206b  setnz   al
0x14016206e  mov     [rsp+178h+var_118], al
0x140162072  test    r12b, r12b
0x140162075  jnz     short loc_14016207B
0x140162077  test    al, al
0x140162079  jz      short loc_1401620CF
0x14016207b  call    cs:__imp_W32GetUserSessionState
0x140162082  nop     dword ptr [rax+rax+00h]
0x140162087  mov     r9, [rax+4BD0h]
0x14016208e  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162095  mov     [rsp+178h+var_140], rax
0x14016209a  mov     [rsp+178h+var_148], 0Bh
0x1401620a1  mov     [rsp+178h+var_150], r14d
0x1401620a6  mov     byte ptr [rsp+178h+TableContext], 4
0x1401620ab  mov     r8b, [rsp+178h+var_118]
0x1401620b0  mov     dl, r12b
0x1401620b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401620ba  mov     rcx, [rcx+18h]
0x1401620be  call    WPP_RECORDER_AND_TRACE_SF_
0x1401620c3  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401620ca  mov     rdx, [rsp+178h+var_100]
0x1401620cf  test    ebx, 0FFFFFFC0h
0x1401620d5  jz      loc_1401621D1
0x1401620db  mov     rdx, cs:WPP_GLOBAL_Control
0x1401620e2  cmp     rdx, rsi
0x1401620e5  jz      short loc_140162100
0x1401620e7  mov     eax, [rdx+2Ch]
0x1401620ea  test    r14b, al
0x1401620ed  jz      short loc_140162100
0x1401620ef  mov     r12d, 2
0x1401620f5  cmp     [rdx+29h], r12b
0x1401620f9  jb      short loc_140162106
0x1401620fb  mov     r15b, r14b
0x1401620fe  jmp     short loc_140162109
0x140162100  mov     r12d, 2
0x140162106  mov     r15b, dil
0x140162109  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162110  setnz   al
0x140162113  mov     [rsp+178h+var_118], al
0x140162117  test    r15b, r15b
0x14016211a  jnz     short loc_140162120
0x14016211c  test    al, al
0x14016211e  jz      short loc_140162175
0x140162120  call    cs:__imp_W32GetUserSessionState
0x140162127  nop     dword ptr [rax+rax+00h]
0x14016212c  mov     r9, [rax+4BD0h]
0x140162133  mov     dword ptr [rsp+178h+var_138], ebx
0x140162137  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x14016213e  mov     [rsp+178h+var_140], r13
0x140162143  mov     [rsp+178h+var_148], 0Ch
0x14016214a  mov     [rsp+178h+var_150], r14d
0x14016214f  mov     byte ptr [rsp+178h+TableContext], r12b
0x140162154  mov     r8b, [rsp+178h+var_118]
0x140162159  mov     dl, r15b
0x14016215c  mov     rcx, cs:WPP_GLOBAL_Control
0x140162163  mov     rcx, [rcx+18h]
0x140162167  call    WPP_RECORDER_AND_TRACE_SF_D
0x14016216c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162173  jmp     short loc_14016217C
0x140162175  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x14016217c  mov     rdx, cs:WPP_GLOBAL_Control
0x140162183  cmp     rdx, rsi
0x140162186  jz      short loc_140162199
0x140162188  mov     eax, [rdx+2Ch]
0x14016218b  test    r14b, al
0x14016218e  jz      short loc_140162199
0x140162190  cmp     byte ptr [rdx+29h], 4
0x140162194  mov     bl, r14b
0x140162197  jnb     short loc_14016219C
0x140162199  mov     bl, dil
0x14016219c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401621a3  setnz   sil
0x1401621a7  test    bl, bl
0x1401621a9  jnz     short loc_1401621B4
0x1401621ab  test    sil, sil
0x1401621ae  jz      loc_1401623FD
0x1401621b4  call    cs:__imp_W32GetUserSessionState
0x1401621bb  nop     dword ptr [rax+rax+00h]
0x1401621c0  mov     [rsp+178h+var_140], r13
0x1401621c5  mov     [rsp+178h+var_148], 0Dh
0x1401621cc  jmp     loc_1401623D7
0x1401621d1  test    rdx, rdx
0x1401621d4  jz      loc_1401622C8
0x1401621da  test    ebx, ebx
0x1401621dc  jz      short loc_1401621EE
0x1401621de  lea     eax, [rbx-1]
0x1401621e1  test    ebx, eax
0x1401621e3  jnz     short loc_1401621EE
0x1401621e5  test    r15d, r15d
0x1401621e8  jz      loc_1401622C8
0x1401621ee  mov     rdx, cs:WPP_GLOBAL_Control
0x1401621f5  cmp     rdx, rsi
0x1401621f8  jz      short loc_140162211
0x1401621fa  mov     eax, [rdx+2Ch]
0x1401621fd  test    r14b, al
0x140162200  jz      short loc_140162211
0x140162202  mov     r12d, 2
0x140162208  cmp     [rdx+29h], r12b
0x14016220c  mov     r12b, r14b
0x14016220f  jnb     short loc_140162214
0x140162211  mov     r12b, dil
0x140162214  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016221b  setnz   r13b
0x14016221f  test    r12b, r12b
0x140162222  jnz     short loc_140162229
0x140162224  test    r13b, r13b
0x140162227  jz      short loc_14016226C
0x140162229  call    cs:__imp_W32GetUserSessionState
0x140162230  nop     dword ptr [rax+rax+00h]
0x140162235  mov     r9, [rax+4BD0h]
0x14016223c  mov     [rsp+178h+var_128], r15d
0x140162241  mov     [rsp+178h+var_130], ebx
0x140162245  mov     rax, [rsp+178h+var_100]
0x14016224a  mov     [rsp+178h+var_138], rax
0x14016224f  mov     r8b, r13b
0x140162252  mov     dl, r12b
0x140162255  mov     rcx, cs:WPP_GLOBAL_Control
0x14016225c  mov     rcx, [rcx+18h]
0x140162260  call    WPP_RECORDER_AND_TRACE_SF_qDd
0x140162265  lea     rcx, WPP_RECORDER_INITIALIZED
0x14016226c  mov     rdx, cs:WPP_GLOBAL_Control
0x140162273  cmp     rdx, rsi
0x140162276  jz      short loc_140162289
0x140162278  mov     eax, [rdx+2Ch]
0x14016227b  test    r14b, al
0x14016227e  jz      short loc_140162289
0x140162280  cmp     byte ptr [rdx+29h], 4
0x140162284  mov     bl, r14b
0x140162287  jnb     short loc_14016228C
0x140162289  mov     bl, dil
0x14016228c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162293  setnz   sil
0x140162297  test    bl, bl
0x140162299  jnz     short loc_1401622A4
0x14016229b  test    sil, sil
0x14016229e  jz      loc_1401623FD
0x1401622a4  call    cs:__imp_W32GetUserSessionState
0x1401622ab  nop     dword ptr [rax+rax+00h]
0x1401622b0  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401622b7  mov     [rsp+178h+var_140], r13
0x1401622bc  mov     [rsp+178h+var_148], 0Fh
0x1401622c3  jmp     loc_1401623D7
0x1401622c8  mov     r12b, dil
0x1401622cb  mov     dword ptr [rsp+178h+var_F8], r12d
0x1401622d3  test    r15d, r15d
0x1401622d6  jz      loc_140162438
0x1401622dc  test    bl, 20h
0x1401622df  jnz     loc_140162407
0x1401622e5  mov     rdx, cs:WPP_GLOBAL_Control
0x1401622ec  cmp     rdx, rsi
0x1401622ef  jz      short loc_14016230A
0x1401622f1  mov     eax, [rdx+2Ch]
0x1401622f4  test    r14b, al
0x1401622f7  jz      short loc_14016230A
0x1401622f9  mov     r12d, 2
0x1401622ff  cmp     [rdx+29h], r12b
0x140162303  jb      short loc_140162310
0x140162305  mov     r13b, r14b
0x140162308  jmp     short loc_140162313
0x14016230a  mov     r12d, 2
0x140162310  mov     r13b, dil
0x140162313  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016231a  setnz   al
0x14016231d  mov     [rsp+178h+var_118], al
0x140162321  test    r13b, r13b
0x140162324  jnz     short loc_14016232A
0x140162326  test    al, al
0x140162328  jz      short loc_140162384
0x14016232a  call    cs:__imp_W32GetUserSessionState
0x140162331  nop     dword ptr [rax+rax+00h]
0x140162336  mov     r9, [rax+4BD0h]
0x14016233d  mov     [rsp+178h+var_130], r15d
0x140162342  mov     dword ptr [rsp+178h+var_138], ebx
0x140162346  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x14016234d  mov     [rsp+178h+var_140], r15
0x140162352  mov     [rsp+178h+var_148], 10h
0x140162359  mov     [rsp+178h+var_150], r14d
0x14016235e  mov     byte ptr [rsp+178h+TableContext], r12b
0x140162363  mov     r8b, [rsp+178h+var_118]
0x140162368  mov     dl, r13b
0x14016236b  mov     rcx, cs:WPP_GLOBAL_Control
0x140162372  mov     rcx, [rcx+18h]
0x140162376  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14016237b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162382  jmp     short loc_14016238B
0x140162384  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x14016238b  mov     rdx, cs:WPP_GLOBAL_Control
0x140162392  cmp     rdx, rsi
0x140162395  jz      short loc_1401623A8
0x140162397  mov     eax, [rdx+2Ch]
0x14016239a  test    r14b, al
0x14016239d  jz      short loc_1401623A8
0x14016239f  cmp     byte ptr [rdx+29h], 4
0x1401623a3  mov     bl, r14b
0x1401623a6  jnb     short loc_1401623AB
0x1401623a8  mov     bl, dil
0x1401623ab  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401623b2  setnz   sil
0x1401623b6  test    bl, bl
0x1401623b8  jnz     short loc_1401623BF
0x1401623ba  test    sil, sil
0x1401623bd  jz      short loc_1401623FD
0x1401623bf  call    cs:__imp_W32GetUserSessionState
0x1401623c6  nop     dword ptr [rax+rax+00h]
0x1401623cb  mov     [rsp+178h+var_140], r15
0x1401623d0  mov     [rsp+178h+var_148], 11h
0x1401623d7  mov     [rsp+178h+var_150], r14d
0x1401623dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401623e3  mov     byte ptr [rsp+178h+TableContext], 4
0x1401623e8  mov     r9, [rax+4BD0h]
0x1401623ef  mov     r8b, sil
0x1401623f2  mov     dl, bl
0x1401623f4  mov     rcx, [rcx+18h]
0x1401623f8  call    WPP_RECORDER_AND_TRACE_SF_
0x1401623fd  mov     eax, 0C000000Dh
0x140162402  jmp     loc_140162F9C
0x140162407  cmp     [rsp+178h+arg_58], edi
0x14016240e  jz      short loc_140162438
0x140162410  mov     ecx, ebx
0x140162412  call    rimCheckForRegistrationConflicts
0x140162417  cmp     eax, r14d
0x14016241a  jnz     short loc_140162426
0x14016241c  mov     eax, 0C0000022h
0x140162421  jmp     loc_140162F9C
0x140162426  movzx   r12d, r12b
0x14016242a  test    eax, eax
0x14016242c  cmovz   r12d, r14d
0x140162430  mov     dword ptr [rsp+178h+var_F8], r12d
0x140162438  mov     edx, r13d; Limit
0x14016243b  xor     ecx, ecx; Count
0x14016243d  call    CreateKernelSemaphore
0x140162442  mov     rsi, rax
0x140162445  mov     qword ptr [rsp+178h+DestinationString.Length], rax
0x14016244d  test    rax, rax
0x140162450  jnz     short loc_14016245C
0x140162452  mov     eax, 0C0000017h
0x140162457  jmp     loc_140162F9C
0x14016245c  mov     edx, 7FFFFFFFh; Limit
0x140162461  xor     ecx, ecx; Count
0x140162463  call    CreateKernelSemaphore
0x140162468  mov     r15, rax
0x14016246b  mov     [rsp+178h+var_D0], rax
0x140162473  test    rax, rax
0x140162476  jnz     short loc_140162482
0x140162478  mov     rcx, rsi; Buffer
0x14016247b  call    GreDeleteFastMutex
  ... truncated ...
```
