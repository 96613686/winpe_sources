# RIMAddInjectionDeviceOfType

- ea: `0x1401fce80`
- end: `0x1401fd7ec`
- name: `RIMAddInjectionDeviceOfType`
- size: `2412`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140204c7c`
- `0x140205030`

## callees

- `0x140012c80`
- `0x14002a0e4`
- `0x1400411c0`
- `0x1400449b0`
- `0x140066bf0`
- `0x140071828`
- `0x1400718f0`
- `0x140073a50`
- `0x140076ef0`
- `0x14009e3c0`
- `0x1400b7e20`
- `0x1400e5630`
- `0x1400fc030`
- `0x1401357d0`
- `0x1401aa4fc`
- `0x1401fce80`
- `0x140238b10`
- `0x140238c40`
- `0x1402bd208`
- `0x1402bd244`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fd1af`
- `ntoskrnl!ProbeForRead` at `0x1401fd1af`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd26a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd26a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fd5fd`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fd5fd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd20c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd20c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fd5a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fd5a4`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd3b7`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd3b7`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf4a`
- `WIN32K!W32GetUserSessionState` at `0x1401fcfce`
- `WIN32K!W32GetUserSessionState` at `0x1401fd409`
- `WIN32K!W32GetUserSessionState` at `0x1401fd4aa`
- `WIN32K!W32GetUserSessionState` at `0x1401fd534`
- `WIN32K!W32GetUserSessionState` at `0x1401fd5b0`
- `WIN32K!W32GetUserSessionState` at `0x1401fd710`
- `WIN32K!W32GetUserSessionState` at `0x1401fd77c`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf4a`
- `WIN32K!W32GetUserSessionState` at `0x1401fcfce`
- `WIN32K!W32GetUserSessionState` at `0x1401fd409`
- `WIN32K!W32GetUserSessionState` at `0x1401fd4aa`
- `WIN32K!W32GetUserSessionState` at `0x1401fd534`
- `WIN32K!W32GetUserSessionState` at `0x1401fd5b0`
- `WIN32K!W32GetUserSessionState` at `0x1401fd710`
- `WIN32K!W32GetUserSessionState` at `0x1401fd77c`

## pseudocode

```c
__int64 __fastcall RIMAddInjectionDeviceOfType(char *a1, __int64 a2, unsigned int a3, __int64 a4, int a5, _QWORD *a6)
{
  char v7; // bl
  bool v8; // r14
  __int64 UserSessionState; // rax
  int v10; // r8d
  int v11; // edx
  char v12; // bl
  bool v13; // r14
  __int64 v14; // rax
  int v15; // r8d
  int v16; // edx
  int v18; // ebx
  int v19; // r14d
  PVOID *v20; // r15
  int ULongFromUser; // ebx
  struct RIMDEV *v22; // rax
  __int64 v23; // rcx
  char v24; // bl
  bool v25; // r12
  int v26; // edx
  int v27; // r8d
  __int64 v28; // r9
  char v29; // bl
  bool v30; // r14
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  char v34; // bl
  bool v35; // r14
  __int64 v36; // rax
  int v37; // r8d
  int v38; // edx
  __int64 v39; // rcx
  __int64 v40; // r14
  __int64 v41; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v43; // rax
  char v44; // al
  _QWORD *i; // rbx
  char v46; // bl
  bool v47; // r15
  __int64 v48; // rax
  int v49; // r8d
  int v50; // edx
  __int16 v51; // [rsp+30h] [rbp-188h]
  struct RIMDEV *v52; // [rsp+58h] [rbp-160h] BYREF
  unsigned int v53; // [rsp+60h] [rbp-158h]
  char *v54; // [rsp+68h] [rbp-150h]
  PVOID Object; // [rsp+70h] [rbp-148h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-140h] BYREF
  int v57; // [rsp+88h] [rbp-130h]
  __int64 v58; // [rsp+90h] [rbp-128h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-120h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+A8h] [rbp-110h]
  _QWORD *v61; // [rsp+B0h] [rbp-108h]
  __int64 v62; // [rsp+B8h] [rbp-100h]
  __int64 v63; // [rsp+C0h] [rbp-F8h]
  __int128 v64; // [rsp+C8h] [rbp-F0h]
  __int64 v65[18]; // [rsp+E0h] [rbp-D8h] BYREF

  v53 = a3;
  v58 = a2;
  v54 = a1;
  v61 = a6;
  LODWORD(v52) = a3;
  v62 = a4;
  v63 = (__int64)a6;
  Object = 0;
  memset(v65, 0, 0x88u);
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v7 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v7 = 0;
  }
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      v10,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      35,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v12 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
    {
      v12 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v12;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v16,
        v15,
        *(_QWORD *)(v14 + 19408),
        3,
        1,
        36,
        (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    }
    return 3221225485LL;
  }
  v18 = a5;
  if ( a5 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1129);
  v19 = RawInputManagerObjectResolveHandle(v54, 3, 0, &Object);
  if ( v19 >= 0 )
  {
    v20 = (PVOID *)Object;
    v54 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v20 + 73) )
    {
      if ( !*((_BYTE *)v20 + 74) )
      {
        v19 = -1073741637;
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
          || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v24 = 0;
        }
        v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v24 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_49;
        v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
        v51 = 40;
LABEL_57:
        LOBYTE(v27) = v25;
        LOBYTE(v26) = v24;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v26,
          v27,
          v28,
          3,
          1,
          v51,
          (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_49:
        RIMUnlockExclusive(v54);
        ObfDereferenceObject(v20);
        goto LABEL_98;
      }
    }
    else if ( !*((_BYTE *)v20 + 74) )
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(v53) & *((_DWORD *)v20 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v64 = 0;
          ULongFromUser = RtlReadULongFromUser(v58);
          LODWORD(v64) = ULongFromUser;
          *((_QWORD *)&v64 + 1) = RtlReadULong64FromUser(v58 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v64);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v64 + 1);
          ProbeForRead(*((volatile void **)&v64 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1165);
            ExRaiseAccessViolation();
          }
          DestinationString.MaximumLength = SourceString.Length;
          DestinationString.Length = SourceString.Length;
          DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
          if ( DestinationString.Buffer )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            p_DestinationString = &DestinationString;
          }
          else
          {
            v19 = -1073741801;
            v57 = -1073741801;
          }
          v18 = a5;
        }
        else
        {
          *(_OWORD *)v65 = *(_OWORD *)a4;
          *(_OWORD *)&v65[2] = *(_OWORD *)(a4 + 16);
          *(_OWORD *)&v65[4] = *(_OWORD *)(a4 + 32);
          *(_OWORD *)&v65[6] = *(_OWORD *)(a4 + 48);
          *(_OWORD *)&v65[8] = *(_OWORD *)(a4 + 64);
          *(_OWORD *)&v65[10] = *(_OWORD *)(a4 + 80);
          *(_OWORD *)&v65[12] = *(_OWORD *)(a4 + 96);
          *(_OWORD *)&v65[14] = *(_OWORD *)(a4 + 112);
          v65[16] = *(_QWORD *)(a4 + 128);
        }
        if ( v19 >= 0 )
        {
          v52 = 0;
          v19 = RIMCreateDev((struct RawInputManagerObject *)v20, 1, (__int64)v65, (__int64)&v52);
          if ( !v18 )
            *(_DWORD *)(a4 + 128) = v65[16];
          if ( v19 >= 0 )
          {
            if ( v18 )
            {
              RtlWriteULong64ToUser(v63, *((_QWORD *)v52 + 2));
              v22 = v52;
            }
            else
            {
              v22 = v52;
              v23 = (v65[2] & 1) != 0 ? *((_QWORD *)v52 + 3) : *((_QWORD *)v52 + 2);
              *v61 = v23;
            }
            if ( v20[103] || *((_DWORD *)v20 + 262) )
              *((_DWORD *)v22 + 42) |= 0x40000u;
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_49;
      }
      v19 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v24 = 0;
      }
      v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v24 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_49;
      v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v51 = 37;
      goto LABEL_57;
    }
    if ( KeGetCurrentThread() == v20[5] )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v29 = 0;
      }
      v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v31 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v32) = v30;
        LOBYTE(v33) = v29;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v33,
          v32,
          *(_QWORD *)(v31 + 19408),
          3,
          1,
          38,
          (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
      }
      v19 = -1073741637;
      goto LABEL_49;
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v34 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
    {
      v34 = 0;
    }
    v35 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v36 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v37) = v35;
      LOBYTE(v38) = v34;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v38,
        v37,
        *(_QWORD *)(v36 + 19408),
        3,
        1,
        39,
        (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    }
    ++*((_DWORD *)v20 + 274);
    RIMUnlockExclusive(v54);
    UserSessionSwitchLeaveCritWithNonPaged();
    KeWaitForSingleObject(v20[136], UserRequest, 0, 0, 0);
    v40 = W32GetUserSessionState(v39);
    v41 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v40,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v40 + 16) = v41;
    if ( v41 )
    {
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v41 + 520), 0, 0) & 0x1000000) == 0
        || *(char *)(v41 + 1360) < 0 )
      {
        v44 = 0;
LABEL_83:
        if ( v44 )
        {
          for ( i = *(_QWORD **)(v40 + 19544); i; i = *(_QWORD **)(v40 + 19544) )
          {
            *(_QWORD *)(v40 + 19544) = i[2];
            i[2] = 0;
            if ( !*(_DWORD *)(*i + 8LL) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            HMUnlockObject(*i);
          }
          DestroyDeferredUnlockObjectAssignmentList(v40 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v40 + 19560);
        }
        goto LABEL_89;
      }
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        v43 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
        if ( v43 )
        {
          if ( *(_BYTE *)(v43 + 1200) == 1 )
          {
            v44 = 1;
            goto LABEL_83;
          }
        }
      }
    }
LABEL_89:
    RIMLockExclusive(v54);
    v19 = -2147483631;
    goto LABEL_49;
  }
  v19 = -1073741816;
LABEL_98:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v46 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v46 = 0;
  }
  v47 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v46 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v48 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v49) = v47;
    LOBYTE(v50) = v46;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v50,
      v49,
      *(_QWORD *)(v48 + 19408),
      4,
      1,
      41,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1401fce80  push    rbx
0x1401fce82  push    rsi
0x1401fce83  push    rdi
0x1401fce84  push    r12
0x1401fce86  push    r13
0x1401fce88  push    r14
0x1401fce8a  push    r15
0x1401fce8c  sub     rsp, 180h
0x1401fce93  mov     rax, cs:__security_cookie
0x1401fce9a  xor     rax, rsp
0x1401fce9d  mov     [rsp+1B8h+var_48], rax
0x1401fcea5  mov     r13, r9
0x1401fcea8  mov     eax, r8d
0x1401fceab  mov     [rsp+1B8h+var_158], eax
0x1401fceaf  mov     [rsp+1B8h+var_128], rdx
0x1401fceb7  mov     [rsp+1B8h+var_150], rcx
0x1401fcebc  mov     rcx, [rsp+1B8h+arg_28]
0x1401fcec4  mov     [rsp+1B8h+var_108], rcx
0x1401fcecc  mov     dword ptr [rsp+1B8h+var_160], eax
0x1401fced0  mov     [rsp+1B8h+var_100], r9
0x1401fced8  mov     [rsp+1B8h+var_F8], rcx
0x1401fcee0  xor     edi, edi
0x1401fcee2  mov     [rsp+1B8h+Object], rdi
0x1401fcee7  xor     edx, edx; Val
0x1401fcee9  mov     r8d, 88h; Size
0x1401fceef  lea     rcx, [rsp+1B8h+var_D8]; void *
0x1401fcef7  call    memset
0x1401fcefc  lea     rdx, WPP_GLOBAL_Control
0x1401fcf03  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcf0a  lea     esi, [rdi+1]
0x1401fcf0d  cmp     rcx, rdx
0x1401fcf10  jz      short loc_1401FCF23
0x1401fcf12  mov     eax, [rcx+2Ch]
0x1401fcf15  test    sil, al
0x1401fcf18  jz      short loc_1401FCF23
0x1401fcf1a  cmp     byte ptr [rcx+29h], 4
0x1401fcf1e  mov     bl, sil
0x1401fcf21  jnb     short loc_1401FCF26
0x1401fcf23  mov     bl, dil
0x1401fcf26  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fcf2d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fcf34  setnz   r14b
0x1401fcf38  test    bl, bl
0x1401fcf3a  jnz     short loc_1401FCF4A
0x1401fcf3c  test    r14b, r14b
0x1401fcf3f  jnz     short loc_1401FCF4A
0x1401fcf41  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fcf48  jmp     short loc_1401FCF95
0x1401fcf4a  call    cs:__imp_W32GetUserSessionState
0x1401fcf51  nop     dword ptr [rax+rax+00h]
0x1401fcf56  mov     r9, [rax+4BD0h]
0x1401fcf5d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fcf64  mov     [rsp+1B8h+var_180], r15
0x1401fcf69  mov     word ptr [rsp+1B8h+var_188], 23h ; '#'
0x1401fcf70  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fcf74  mov     byte ptr [rsp+1B8h+Timeout], 4
0x1401fcf79  mov     r8b, r14b
0x1401fcf7c  mov     dl, bl
0x1401fcf7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcf85  mov     rcx, [rcx+18h]
0x1401fcf89  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fcf8e  lea     rdx, WPP_GLOBAL_Control
0x1401fcf95  test    r13, r13
0x1401fcf98  jnz     short loc_1401FD015
0x1401fcf9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcfa1  cmp     rcx, rdx
0x1401fcfa4  jz      short loc_1401FCFB7
0x1401fcfa6  mov     eax, [rcx+2Ch]
0x1401fcfa9  test    sil, al
0x1401fcfac  jz      short loc_1401FCFB7
0x1401fcfae  cmp     byte ptr [rcx+29h], 3
0x1401fcfb2  mov     bl, sil
0x1401fcfb5  jnb     short loc_1401FCFBA
0x1401fcfb7  mov     bl, dil
0x1401fcfba  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fcfc1  setnz   r14b
0x1401fcfc5  test    bl, bl
0x1401fcfc7  jnz     short loc_1401FCFCE
0x1401fcfc9  test    r14b, r14b
0x1401fcfcc  jz      short loc_1401FD00B
0x1401fcfce  call    cs:__imp_W32GetUserSessionState
0x1401fcfd5  nop     dword ptr [rax+rax+00h]
0x1401fcfda  mov     r9, [rax+4BD0h]
0x1401fcfe1  mov     [rsp+1B8h+var_180], r15
0x1401fcfe6  mov     word ptr [rsp+1B8h+var_188], 24h ; '$'
0x1401fcfed  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fcff1  mov     byte ptr [rsp+1B8h+Timeout], 3
0x1401fcff6  mov     r8b, r14b
0x1401fcff9  mov     dl, bl
0x1401fcffb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd002  mov     rcx, [rcx+18h]
0x1401fd006  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fd00b  mov     eax, 0C000000Dh
0x1401fd010  jmp     loc_1401FD7C8
0x1401fd015  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd01c  test    ebx, ebx
0x1401fd01e  jz      short loc_1401FD03E
0x1401fd020  mov     [rsp+1B8h+var_168], 20000h
0x1401fd028  mov     r8d, 469h
0x1401fd02e  mov     edx, [rsp+1B8h+var_168]
0x1401fd032  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fd039  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fd03e  lea     r9, [rsp+1B8h+Object]
0x1401fd043  xor     r8d, r8d
0x1401fd046  lea     edx, [r8+3]
0x1401fd04a  mov     rcx, [rsp+1B8h+var_150]
0x1401fd04f  call    RawInputManagerObjectResolveHandle
0x1401fd054  mov     r14d, eax
0x1401fd057  test    eax, eax
0x1401fd059  js      loc_1401FD73B
0x1401fd05f  mov     r15, [rsp+1B8h+Object]
0x1401fd064  lea     rax, [r15+60h]
0x1401fd068  mov     [rsp+1B8h+var_150], rax
0x1401fd06d  mov     rcx, rax
0x1401fd070  call    RIMLockExclusive
0x1401fd075  cmp     [r15+49h], dil
0x1401fd079  jnz     loc_1401FD452
0x1401fd07f  cmp     [r15+4Ah], dil
0x1401fd083  jnz     loc_1401FD45C
0x1401fd089  mov     ecx, [rsp+1B8h+var_158]
0x1401fd08d  call    DeviceTypeToRimInputType
0x1401fd092  test    [r15+4Ch], eax
0x1401fd096  jz      loc_1401FD3C8
0x1401fd09c  xorps   xmm0, xmm0
0x1401fd09f  movups  xmmword ptr [rsp+1B8h+SourceString.Length], xmm0
0x1401fd0a4  mov     r12, rdi
0x1401fd0a7  mov     [rsp+1B8h+var_110], rdi
0x1401fd0af  movups  xmmword ptr [rsp+1B8h+DestinationString.Length], xmm0
0x1401fd0b7  test    ebx, ebx
0x1401fd0b9  jnz     loc_1401FD147
0x1401fd0bf  mov     r12, [rsp+1B8h+var_128]
0x1401fd0c7  movups  xmm0, xmmword ptr [r13+0]
0x1401fd0cc  movups  xmmword ptr [rsp+1B8h+var_D8], xmm0
0x1401fd0d4  movups  xmm1, xmmword ptr [r13+10h]
0x1401fd0d9  movups  [rsp+1B8h+var_C8], xmm1
0x1401fd0e1  movups  xmm0, xmmword ptr [r13+20h]
0x1401fd0e6  movups  [rsp+1B8h+var_B8], xmm0
0x1401fd0ee  movups  xmm1, xmmword ptr [r13+30h]
0x1401fd0f3  movups  [rsp+1B8h+var_A8], xmm1
0x1401fd0fb  movups  xmm0, xmmword ptr [r13+40h]
0x1401fd100  movups  [rsp+1B8h+var_98], xmm0
0x1401fd108  movups  xmm1, xmmword ptr [r13+50h]
0x1401fd10d  movups  [rsp+1B8h+var_88], xmm1
0x1401fd115  movups  xmm0, xmmword ptr [r13+60h]
0x1401fd11a  movups  [rsp+1B8h+var_78], xmm0
0x1401fd122  movups  xmm1, xmmword ptr [r13+70h]
0x1401fd127  movups  [rsp+1B8h+var_68], xmm1
0x1401fd12f  mov     rax, [r13+80h]
0x1401fd136  mov     [rsp+1B8h+var_58], rax
0x1401fd13e  mov     eax, [rsp+1B8h+var_158]
0x1401fd142  jmp     loc_1401FD2AA
0x1401fd147  movups  [rsp+1B8h+var_F0], xmm0
0x1401fd14f  mov     rcx, [rsp+1B8h+var_128]
0x1401fd157  call    RtlReadULongFromUser
0x1401fd15c  mov     ebx, eax
0x1401fd15e  mov     dword ptr [rsp+1B8h+var_F0], ebx
0x1401fd165  mov     rcx, [rsp+1B8h+var_128]
0x1401fd16d  add     rcx, 8
0x1401fd171  call    RtlReadULong64FromUser
0x1401fd176  mov     qword ptr [rsp+1B8h+var_F0+8], rax
0x1401fd17e  movzx   edx, bx
0x1401fd181  mov     [rsp+1B8h+SourceString.Length], dx
0x1401fd186  shr     ebx, 10h
0x1401fd189  mov     [rsp+1B8h+SourceString.MaximumLength], bx
0x1401fd18e  mov     ecx, dword ptr [rsp+1B8h+var_F0+4]
0x1401fd195  mov     dword ptr [rsp+1B8h+SourceString+4], ecx
0x1401fd199  mov     [rsp+1B8h+SourceString.Buffer], rax
0x1401fd1a1  mov     ebx, 2
0x1401fd1a6  add     rdx, rbx; Length
0x1401fd1a9  mov     r8d, ebx; Alignment
0x1401fd1ac  mov     rcx, rax; Address
0x1401fd1af  call    cs:__imp_ProbeForRead
0x1401fd1b6  nop     dword ptr [rax+rax+00h]
0x1401fd1bb  movzx   eax, [rsp+1B8h+SourceString.Length]
0x1401fd1c0  cmp     ax, [rsp+1B8h+SourceString.MaximumLength]
0x1401fd1c5  ja      short loc_1401FD245
0x1401fd1c7  mov     byte ptr [rsp+1B8h+SourceString.Length], al
0x1401fd1cb  test    sil, al
0x1401fd1ce  jnz     short loc_1401FD245
0x1401fd1d0  mov     [rsp+1B8h+DestinationString.MaximumLength], ax
0x1401fd1d8  mov     [rsp+1B8h+DestinationString.Length], ax
0x1401fd1e0  mov     edx, eax; unsigned __int64
0x1401fd1e2  mov     ecx, 100h; unsigned __int64
0x1401fd1e7  mov     r8d, 706D7452h; unsigned int
0x1401fd1ed  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fd1f2  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x1401fd1fa  test    rax, rax
0x1401fd1fd  jz      short loc_1401FD22A
0x1401fd1ff  lea     rdx, [rsp+1B8h+SourceString]; SourceString
0x1401fd204  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x1401fd20c  call    cs:__imp_RtlCopyUnicodeString
0x1401fd213  nop     dword ptr [rax+rax+00h]
0x1401fd218  lea     r12, [rsp+1B8h+DestinationString]
0x1401fd220  mov     [rsp+1B8h+var_110], r12
0x1401fd228  jmp     short loc_1401FD238
0x1401fd22a  mov     r14d, 0C0000017h
0x1401fd230  mov     [rsp+1B8h+var_130], r14d
0x1401fd238  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd23f  mov     eax, [rsp+1B8h+var_158]
0x1401fd243  jmp     short loc_1401FD2AA
0x1401fd245  test    byte ptr [rsp+1B8h+SourceString.Length], sil
0x1401fd24a  jz      short loc_1401FD26A
0x1401fd24c  mov     [rsp+1B8h+var_168], 20000h
0x1401fd254  mov     r8d, 48Dh
0x1401fd25a  mov     edx, [rsp+1B8h+var_168]
0x1401fd25e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fd265  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fd26a  call    cs:__imp_ExRaiseAccessViolation
0x1401fd271  nop     dword ptr [rax+rax+00h]
0x1401fd276  nop
0x1401fd277  mov     r14d, 0C000000Dh
0x1401fd27d  mov     [rsp+1B8h+var_130], r14d
0x1401fd285  xor     edi, edi
0x1401fd287  lea     esi, [rdi+1]
0x1401fd28a  mov     r15, [rsp+1B8h+Object]
0x1401fd28f  mov     r12, [rsp+1B8h+var_110]
0x1401fd297  mov     eax, dword ptr [rsp+1B8h+var_160]
0x1401fd29b  mov     r13, [rsp+1B8h+var_100]
0x1401fd2a3  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd2aa  test    r14d, r14d
0x1401fd2ad  js      loc_1401FD38A
0x1401fd2b3  mov     [rsp+1B8h+var_160], rdi
0x1401fd2b8  lea     rcx, [rsp+1B8h+var_160]
0x1401fd2bd  mov     [rsp+1B8h+var_188], rcx; __int64
0x1401fd2c2  lea     rcx, [rsp+1B8h+var_D8]
0x1401fd2ca  mov     [rsp+1B8h+var_190], rcx; __int64
0x1401fd2cf  mov     dword ptr [rsp+1B8h+Timeout], esi; int
0x1401fd2d3  xor     r9d, r9d
0x1401fd2d6  mov     r8, r12
0x1401fd2d9  mov     edx, eax
0x1401fd2db  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd2de  call    RIMCreateDev
0x1401fd2e3  mov     r14d, eax
0x1401fd2e6  test    ebx, ebx
0x1401fd2e8  jnz     short loc_1401FD2F9
0x1401fd2ea  mov     rax, [rsp+1B8h+var_58]
0x1401fd2f2  mov     [r13+80h], eax
0x1401fd2f9  test    r14d, r14d
0x1401fd2fc  js      loc_1401FD38A
0x1401fd302  test    ebx, ebx
0x1401fd304  jnz     short loc_1401FD32C
0x1401fd306  mov     rax, [rsp+1B8h+var_160]
0x1401fd30b  test    byte ptr [rsp+1B8h+var_C8], sil
0x1401fd313  jz      short loc_1401FD31B
0x1401fd315  mov     rcx, [rax+18h]
0x1401fd319  jmp     short loc_1401FD31F
0x1401fd31b  mov     rcx, [rax+10h]
0x1401fd31f  mov     rdx, [rsp+1B8h+var_108]
0x1401fd327  mov     [rdx], rcx
0x1401fd32a  jmp     short loc_1401FD35E
0x1401fd32c  mov     rdx, [rsp+1B8h+var_160]
0x1401fd331  mov     rdx, [rdx+10h]
0x1401fd335  mov     rcx, [rsp+1B8h+var_F8]
0x1401fd33d  call    RtlWriteULong64ToUser
0x1401fd342  mov     rax, [rsp+1B8h+var_160]
0x1401fd347  jmp     short loc_1401FD35E
0x1401fd349  xor     edi, edi
0x1401fd34b  lea     esi, [rdi+1]
0x1401fd34e  mov     r14d, 0C000000Dh
0x1401fd354  mov     r15, [rsp+1B8h+Object]
0x1401fd359  mov     rax, [rsp+1B8h+var_160]
0x1401fd35e  test    r14d, r14d
0x1401fd361  jns     short loc_1401FD370
0x1401fd363  mov     rdx, rax; struct RIMDEV *
0x1401fd366  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd369  call    RIMFreeDev
0x1401fd36e  jmp     short loc_1401FD38A
0x1401fd370  cmp     [r15+338h], rdi
0x1401fd377  jnz     short loc_1401FD382
0x1401fd379  cmp     [r15+418h], edi
0x1401fd380  jz      short loc_1401FD38A
0x1401fd382  bts     dword ptr [rax+0A8h], 12h
0x1401fd38a  mov     rcx, [rsp+1B8h+DestinationString.Buffer]; Buffer
0x1401fd392  test    rcx, rcx
0x1401fd395  jz      short loc_1401FD39C
0x1401fd397  call    GreDeleteFastMutex
0x1401fd39c  lea     r13, WPP_GLOBAL_Control
0x1401fd3a3  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fd3aa  mov     rcx, [rsp+1B8h+var_150]
0x1401fd3af  call    RIMUnlockExclusive
0x1401fd3b4  mov     rcx, r15; Object
0x1401fd3b7  call    cs:__imp_ObfDereferenceObject
0x1401fd3be  nop     dword ptr [rax+rax+00h]
0x1401fd3c3  jmp     loc_1401FD748
0x1401fd3c8  mov     r14d, 0C00000BBh
0x1401fd3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd3d5  lea     r13, WPP_GLOBAL_Control
0x1401fd3dc  cmp     rcx, r13
0x1401fd3df  jz      short loc_1401FD3F2
0x1401fd3e1  mov     eax, [rcx+2Ch]
0x1401fd3e4  test    sil, al
0x1401fd3e7  jz      short loc_1401FD3F2
0x1401fd3e9  cmp     byte ptr [rcx+29h], 3
0x1401fd3ed  mov     bl, sil
0x1401fd3f0  jnb     short loc_1401FD3F5
0x1401fd3f2  mov     bl, dil
0x1401fd3f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd3fc  setnz   r12b
0x1401fd400  test    bl, bl
0x1401fd402  jnz     short loc_1401FD409
  ... truncated ...
```
