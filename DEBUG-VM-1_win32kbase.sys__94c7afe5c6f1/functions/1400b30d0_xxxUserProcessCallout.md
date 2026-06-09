# xxxUserProcessCallout

- ea: `0x1400b30d0`
- end: `0x1400b3755`
- name: `xxxUserProcessCallout`
- size: `1669`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x14000e260`
- `0x140012c80`
- `0x1400153b8`
- `0x1400153e4`
- `0x14002a0e4`
- `0x140073a50`
- `0x140076ef0`
- `0x1400b2bac`
- `0x1400b30d0`
- `0x1400b375c`
- `0x1400b471c`
- `0x1400b4f98`
- `0x1400cb450`
- `0x1400cb9dc`
- `0x140144bc0`
- `0x140144e40`
- `0x140150098`
- `0x1401aa4fc`
- `0x1401b8974`
- `0x1402160b0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b3315`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b34da`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b3315`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b34da`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400b3128`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400b3128`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400b3436`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400b3436`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400b346e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400b346e`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b32ab`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b33be`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b32ab`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b33be`
- `ntoskrnl!PsGetProcessJob` at `0x1400b33ec`
- `ntoskrnl!PsGetProcessJob` at `0x1400b35b5`
- `ntoskrnl!PsGetProcessJob` at `0x1400b33ec`
- `ntoskrnl!PsGetProcessJob` at `0x1400b35b5`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1400b3403`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1400b3403`
- `ntoskrnl!PsGetJobLock` at `0x1400b3427`
- `ntoskrnl!PsGetJobLock` at `0x1400b345f`
- `ntoskrnl!PsGetJobLock` at `0x1400b3427`
- `ntoskrnl!PsGetJobLock` at `0x1400b345f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b35c6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b35eb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b35c6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b35eb`
- `WIN32K!W32GetSessionState` at `0x1400b3675`
- `WIN32K!W32GetSessionState` at `0x1400b36f4`
- `WIN32K!W32GetSessionState` at `0x1400b3675`
- `WIN32K!W32GetSessionState` at `0x1400b36f4`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b3561`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b3574`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b358c`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b3561`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b3574`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b358c`
- `WIN32K!W32GetUserSessionState` at `0x1400b3182`
- `WIN32K!W32GetUserSessionState` at `0x1400b3257`
- `WIN32K!W32GetUserSessionState` at `0x1400b32be`
- `WIN32K!W32GetUserSessionState` at `0x1400b347f`
- `WIN32K!W32GetUserSessionState` at `0x1400b35a1`
- `WIN32K!W32GetUserSessionState` at `0x1400b361f`
- `WIN32K!W32GetUserSessionState` at `0x1400b3635`
- `WIN32K!W32GetUserSessionState` at `0x1400b365a`
- `WIN32K!W32GetUserSessionState` at `0x1400b368a`
- `WIN32K!W32GetUserSessionState` at `0x1400b36a1`
- `WIN32K!W32GetUserSessionState` at `0x1400b36d8`
- `WIN32K!W32GetUserSessionState` at `0x1400b3182`
- `WIN32K!W32GetUserSessionState` at `0x1400b3257`
- `WIN32K!W32GetUserSessionState` at `0x1400b32be`
- `WIN32K!W32GetUserSessionState` at `0x1400b347f`
- `WIN32K!W32GetUserSessionState` at `0x1400b35a1`
- `WIN32K!W32GetUserSessionState` at `0x1400b361f`
- `WIN32K!W32GetUserSessionState` at `0x1400b3635`
- `WIN32K!W32GetUserSessionState` at `0x1400b365a`
- `WIN32K!W32GetUserSessionState` at `0x1400b368a`
- `WIN32K!W32GetUserSessionState` at `0x1400b36a1`
- `WIN32K!W32GetUserSessionState` at `0x1400b36d8`

## pseudocode

```c
__int64 __fastcall xxxUserProcessCallout(struct _W32PROCESS *a1, PEPROCESS *a2)
{
  __int64 v4; // rcx
  char v5; // di
  PACCESS_TOKEN v7; // r15
  bool v8; // si
  int v9; // ebx
  __int64 v10; // rax
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rcx
  int v14; // esi
  bool v15; // r14
  int v16; // ebx
  __int64 v17; // rax
  int v18; // r8d
  int v19; // edx
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // r14
  int inited; // r14d
  __int64 ProcessJob; // rax
  __int64 v27; // rsi
  struct _ERESOURCE *JobLock; // rax
  struct _ERESOURCE *v29; // rax
  __int64 UserSessionState; // rsi
  char v31; // di
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v36; // rax
  _QWORD *v37; // r14
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int (*v42)(void); // rax
  __int64 v43; // rcx
  void (__fastcall *v44)(struct _W32PROCESS *); // rax
  __int64 v45; // rcx
  __int64 v46; // r14
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned __int64 i; // rsi
  __int64 v51; // rax
  __int64 SessionState; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  _DWORD *v55; // rbx
  __int64 v56; // rcx
  _DWORD *v57; // rsi
  __int64 v58; // rax
  unsigned int v59; // [rsp+50h] [rbp-9h] BYREF
  __int64 v60; // [rsp+58h] [rbp-1h] BYREF
  __int128 v61; // [rsp+60h] [rbp+7h] BYREF
  __int128 v62; // [rsp+70h] [rbp+17h]
  __int64 v63; // [rsp+80h] [rbp+27h]
  PVOID v64; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 )
      return xxxUserProcessInitCallout(a1, a2);
    UserProcessDestroyCallout(a1);
    return 0;
  }
  if ( !a2 )
  {
    UserSessionState = W32GetUserSessionState(v4);
    v31 = 1;
    v32 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            UserSessionState,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v32;
    v34 = v32;
    if ( v32 )
    {
      v33 = 0;
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v32 + 520), 0, 0) & 0x1000000) != 0
        && *(char *)(v32 + 1360) >= 0 )
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        if ( CurrentProcessWin32Process )
        {
          if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
          {
            while ( 1 )
            {
              v37 = *(_QWORD **)(UserSessionState + 19544);
              if ( !v37 )
                break;
              *(_QWORD *)(UserSessionState + 19544) = v37[2];
              v36 = *v37;
              v37[2] = 0;
              if ( !*(_DWORD *)(v36 + 8) )
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
              HMUnlockObject(*v37);
            }
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
            DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
          }
        }
      }
    }
    if ( !*(_QWORD *)(W32GetUserGdiSessionState(v33, v34) + 40)
      || (v39 = *(_QWORD *)(W32GetUserGdiSessionState(v39, v38) + 40), *(_QWORD *)a1 != v39) )
    {
      v31 = 0;
    }
    v40 = *(_QWORD *)(W32GetUserGdiSessionState(v39, v38) + 40);
    if ( *(_QWORD *)a1 == v40 )
      W32GetUserSessionState(v40);
    if ( *(_QWORD *)a1 )
    {
      if ( ((__int64 (*)(void))PsGetProcessJob)() )
      {
        v42 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v41) + 48) + 608LL);
        if ( v42 )
        {
          if ( v42() >= 0 )
          {
            v44 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 48)
                                                              + 616LL);
            if ( v44 )
              v44(a1);
          }
        }
      }
    }
    if ( (unsigned int)DestroyProcessInfo(a1) )
    {
      v46 = W32GetUserSessionState(v45);
      v47 = *(_QWORD *)(v46 + 19720);
      for ( i = v47 + 32LL * *(unsigned int *)(W32GetUserSessionState(v48) + 19648);
            i > *(_QWORD *)(v46 + 19720) && !*(_BYTE *)(i + 24);
            i -= 32LL )
      {
        v51 = W32GetUserSessionState(v49);
        --*(_DWORD *)(v51 + 19648);
      }
      SessionState = W32GetSessionState(v49);
      GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
      v54 = *(_QWORD *)(W32GetUserSessionState(v53) + 56744);
      v55 = *(_DWORD **)(v54 + 24);
      if ( v55 != (_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v54) + 56744) + 24LL) )
      {
        do
        {
          v57 = *(_DWORD **)v55;
          if ( (v55[12] & 0x400000) != 0 )
            DestroyCacheDC(v55);
          v55 = v57;
          v56 = *(_QWORD *)(W32GetUserSessionState(v56) + 56744) + 24LL;
        }
        while ( v57 != (_DWORD *)v56 );
      }
      v58 = W32GetSessionState(v56);
      GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v58 + 88));
      ApiSetEditionShowSystemCursor();
      if ( v31 )
        CloseWin32InputRelatedObHandles();
    }
    UserSessionSwitchLeaveCritWithNonPaged();
    return 0;
  }
  v5 = 1;
  if ( *((_BYTE *)a1 + 1200) == 1 )
    return 1073741851;
  v7 = PsReferencePrimaryToken(a2[2]);
  if ( v7 )
  {
    v59 = 0;
    LODWORD(v64) = 0;
    v60 = 0;
    v14 = UserProcessImmersiveType(
            (struct _WIN32_PROCESS_CALLOUT_PARAMETERS *)a2,
            v7,
            (enum _PROCESS_IMMERSIVE_TYPE *)&v59,
            &v64,
            (struct _PS_PKG_CLAIM *)&v60);
    if ( v14 >= 0 )
    {
      v20 = W32GetUserSessionState(v13);
      v21 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
              v20,
              1,
              0,
              _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
      *(_QWORD *)(v20 + 16) = v21;
      if ( v21 )
      {
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v21 + 520), 0, 0) & 0x1000000) != 0
          && *(char *)(v21 + 1360) >= 0 )
        {
          v22 = PsGetCurrentProcessWin32Process();
          if ( v22 )
          {
            if ( *(_QWORD *)v22 && *(_BYTE *)(v22 + 1200) == 1 )
            {
              while ( 1 )
              {
                v24 = *(_QWORD **)(v20 + 19544);
                if ( !v24 )
                  break;
                *(_QWORD *)(v20 + 19544) = v24[2];
                v23 = *v24;
                v24[2] = 0;
                if ( !*(_DWORD *)(v23 + 8) )
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                HMUnlockObject(*v24);
              }
              DestroyDeferredUnlockObjectAssignmentList(v20 + 19576);
              DestroyDeferredUnlockObjectAssignmentList(v20 + 19560);
            }
          }
        }
      }
      inited = xxxInitProcessInfo(a1, v7, v59, (unsigned int)v64, (__int64)&v60);
      PsDereferencePrimaryToken(v7);
      if ( inited >= 0 )
      {
        UserSessionSwitchLeaveCritWithNonPaged();
        ProcessJob = PsGetProcessJob(*(_QWORD *)a1);
        v27 = ProcessJob;
        if ( ProcessJob && (unsigned int)PsGetJobUIRestrictionsClass(ProcessJob) )
        {
          v63 = 0;
          v61 = 0;
          v62 = 0;
          JobLock = (struct _ERESOURCE *)PsGetJobLock(v27);
          ExEnterCriticalRegionAndAcquireResourceExclusive(JobLock);
          v63 = *(_QWORD *)a1;
          *(_QWORD *)&v62 = v27;
          DWORD2(v62) = 1;
          inited = UserJobCallout(&v61);
          v29 = (struct _ERESOURCE *)PsGetJobLock(v27);
          ExReleaseResourceAndLeaveCriticalRegion(v29);
        }
      }
      else
      {
        DestroyProcessInfo(a1);
        UserSessionSwitchLeaveCritWithNonPaged();
      }
      return (unsigned int)inited;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (v13 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v13 & 0x80u) == 0LL)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v5 = 0;
      }
      v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = *((_DWORD *)a1 + 14);
        v17 = W32GetUserSessionState(v13);
        LOBYTE(v18) = v15;
        LOBYTE(v19) = v5;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v19,
          v18,
          *(_QWORD *)(v17 + 69136),
          3,
          8,
          35,
          (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
          v14,
          v16);
      }
      PsDereferencePrimaryToken(v7);
      return (unsigned int)v14;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v5 = 0;
    }
    v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *((_DWORD *)a1 + 14);
      v10 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v11) = v8;
      LOBYTE(v12) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v11,
        *(_QWORD *)(v10 + 69136),
        3,
        8,
        34,
        (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
        v9);
    }
    return 3221225596LL;
  }
}

```

## disassembly

```asm
0x1400b30d0  mov     [rsp-8+arg_0], rbx
0x1400b30d5  mov     [rsp-8+arg_8], rsi
0x1400b30da  push    rbp
0x1400b30db  push    rdi
0x1400b30dc  push    r12
0x1400b30de  push    r14
0x1400b30e0  push    r15
0x1400b30e2  lea     rbp, [rsp-37h]
0x1400b30e7  sub     rsp, 90h
0x1400b30ee  mov     rsi, rdx
0x1400b30f1  mov     rbx, rcx
0x1400b30f4  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1400b30f9  test    eax, eax
0x1400b30fb  jnz     loc_1400B371F
0x1400b3101  test    rsi, rsi
0x1400b3104  jz      loc_1400B347F
0x1400b310a  mov     al, [rbx+4B0h]
0x1400b3110  mov     edi, 1
0x1400b3115  cmp     al, dil
0x1400b3118  jnz     short loc_1400B3124
0x1400b311a  mov     eax, 4000001Bh
0x1400b311f  jmp     loc_1400B3738
0x1400b3124  mov     rcx, [rsi+10h]; Process
0x1400b3128  call    cs:__imp_PsReferencePrimaryToken
0x1400b312f  nop     dword ptr [rax+rax+00h]
0x1400b3134  mov     r15, rax
0x1400b3137  test    rax, rax
0x1400b313a  jnz     loc_1400B31D9
0x1400b3140  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3147  lea     rax, WPP_GLOBAL_Control
0x1400b314e  cmp     rcx, rax
0x1400b3151  jz      short loc_1400B3160
0x1400b3153  mov     eax, [rcx+2Ch]
0x1400b3156  test    al, al
0x1400b3158  jns     short loc_1400B3160
0x1400b315a  cmp     byte ptr [rcx+29h], 3
0x1400b315e  jnb     short loc_1400B3163
0x1400b3160  xor     dil, dil
0x1400b3163  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b316a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3171  setnz   sil
0x1400b3175  test    dil, dil
0x1400b3178  jnz     short loc_1400B317F
0x1400b317a  test    sil, sil
0x1400b317d  jz      short loc_1400B31CF
0x1400b317f  mov     ebx, [rbx+38h]
0x1400b3182  call    cs:__imp_W32GetUserSessionState
0x1400b3189  nop     dword ptr [rax+rax+00h]
0x1400b318e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3195  mov     r8b, sil
0x1400b3198  mov     [rsp+0B0h+var_70], ebx
0x1400b319c  mov     dl, dil
0x1400b319f  mov     r9, [rax+10E10h]
0x1400b31a6  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x1400b31ad  mov     rcx, [rcx+18h]
0x1400b31b1  mov     [rsp+0B0h+var_78], rax
0x1400b31b6  mov     [rsp+0B0h+var_80], 22h ; '"'
0x1400b31bd  mov     [rsp+0B0h+var_88], 8
0x1400b31c5  mov     byte ptr [rsp+0B0h+var_90], 3
0x1400b31ca  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400b31cf  mov     eax, 0C000007Ch
0x1400b31d4  jmp     loc_1400B3738
0x1400b31d9  lea     rax, [rbp+57h+var_58]
0x1400b31dd  mov     [rbp+57h+var_60], 0
0x1400b31e4  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x1400b31e8  mov     [rsp+0B0h+var_90], rax; struct _PS_PKG_CLAIM *
0x1400b31ed  lea     r8, [rbp+57h+var_60]; enum _PROCESS_IMMERSIVE_TYPE *
0x1400b31f1  mov     dword ptr [rbp+57h+arg_18], 0
0x1400b31f8  mov     rdx, r15; void *
0x1400b31fb  mov     [rbp+57h+var_58], 0
0x1400b3203  mov     rcx, rsi; struct _WIN32_PROCESS_CALLOUT_PARAMETERS *
0x1400b3206  call    ?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z; UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)
0x1400b320b  mov     esi, eax
0x1400b320d  test    eax, eax
0x1400b320f  jns     loc_1400B32BE
0x1400b3215  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b321c  lea     rax, WPP_GLOBAL_Control
0x1400b3223  cmp     rdx, rax
0x1400b3226  jz      short loc_1400B3235
0x1400b3228  mov     ecx, [rdx+2Ch]
0x1400b322b  test    cl, cl
0x1400b322d  jns     short loc_1400B3235
0x1400b322f  cmp     byte ptr [rdx+29h], 3
0x1400b3233  jnb     short loc_1400B3238
0x1400b3235  xor     dil, dil
0x1400b3238  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b323f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3246  setnz   r14b
0x1400b324a  test    dil, dil
0x1400b324d  jnz     short loc_1400B3254
0x1400b324f  test    r14b, r14b
0x1400b3252  jz      short loc_1400B32A8
0x1400b3254  mov     ebx, [rbx+38h]
0x1400b3257  call    cs:__imp_W32GetUserSessionState
0x1400b325e  nop     dword ptr [rax+rax+00h]
0x1400b3263  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b326a  mov     r8b, r14b
0x1400b326d  mov     [rsp+0B0h+var_68], ebx
0x1400b3271  mov     dl, dil
0x1400b3274  mov     [rsp+0B0h+var_70], esi
0x1400b3278  mov     r9, [rax+10E10h]
0x1400b327f  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x1400b3286  mov     rcx, [rcx+18h]
0x1400b328a  mov     [rsp+0B0h+var_78], rax
0x1400b328f  mov     [rsp+0B0h+var_80], 23h ; '#'
0x1400b3296  mov     [rsp+0B0h+var_88], 8
0x1400b329e  mov     byte ptr [rsp+0B0h+var_90], 3
0x1400b32a3  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400b32a8  mov     rcx, r15; PrimaryToken
0x1400b32ab  call    cs:__imp_PsDereferencePrimaryToken
0x1400b32b2  nop     dword ptr [rax+rax+00h]
0x1400b32b7  mov     eax, esi
0x1400b32b9  jmp     loc_1400B3738
0x1400b32be  call    cs:__imp_W32GetUserSessionState
0x1400b32c5  nop     dword ptr [rax+rax+00h]
0x1400b32ca  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400b32d1  xor     r8d, r8d
0x1400b32d4  mov     rcx, rax
0x1400b32d7  mov     edx, edi
0x1400b32d9  mov     rsi, rax
0x1400b32dc  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1400b32e1  mov     [rsi+10h], rax
0x1400b32e5  mov     rdx, rax
0x1400b32e8  test    rax, rax
0x1400b32eb  jz      loc_1400B339C
0x1400b32f1  xor     ecx, ecx
0x1400b32f3  xor     eax, eax
0x1400b32f5  lock cmpxchg [rdx+208h], ecx
0x1400b32fd  bt      eax, 18h
0x1400b3301  jnb     loc_1400B339C
0x1400b3307  mov     al, [rdx+550h]
0x1400b330d  test    al, al
0x1400b330f  js      loc_1400B339C
0x1400b3315  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400b331c  nop     dword ptr [rax+rax+00h]
0x1400b3321  test    rax, rax
0x1400b3324  jz      short loc_1400B339C
0x1400b3326  cmp     qword ptr [rax], 0
0x1400b332a  jz      short loc_1400B339C
0x1400b332c  mov     al, [rax+4B0h]
0x1400b3332  cmp     al, dil
0x1400b3335  jz      short loc_1400B3378
0x1400b3337  jmp     short loc_1400B339C
0x1400b3339  mov     rax, [r14+10h]
0x1400b333d  mov     [rsi+4C58h], rax
0x1400b3344  mov     rax, [r14]
0x1400b3347  mov     qword ptr [r14+10h], 0
0x1400b334f  cmp     [rax+8], edi
0x1400b3352  jnb     short loc_1400B3370
0x1400b3354  mov     [rbp+57h+arg_10], 20000h
0x1400b335b  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400b3362  mov     edx, [rbp+57h+arg_10]
0x1400b3365  mov     r8d, 1236h
0x1400b336b  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400b3370  mov     rcx, [r14]
0x1400b3373  call    HMUnlockObject
0x1400b3378  mov     r14, [rsi+4C58h]
0x1400b337f  test    r14, r14
0x1400b3382  jnz     short loc_1400B3339
0x1400b3384  lea     rcx, [rsi+4C78h]
0x1400b338b  call    DestroyDeferredUnlockObjectAssignmentList
0x1400b3390  lea     rcx, [rsi+4C68h]
0x1400b3397  call    DestroyDeferredUnlockObjectAssignmentList
0x1400b339c  mov     r9d, dword ptr [rbp+57h+arg_18]
0x1400b33a0  lea     rax, [rbp+57h+var_58]
0x1400b33a4  mov     r8d, [rbp+57h+var_60]
0x1400b33a8  mov     rdx, r15; Token
0x1400b33ab  mov     rcx, rbx; struct _W32PROCESS *
0x1400b33ae  mov     [rsp+0B0h+var_90], rax; __int64
0x1400b33b3  call    xxxInitProcessInfo
0x1400b33b8  mov     rcx, r15; PrimaryToken
0x1400b33bb  mov     r14d, eax
0x1400b33be  call    cs:__imp_PsDereferencePrimaryToken
0x1400b33c5  nop     dword ptr [rax+rax+00h]
0x1400b33ca  test    r14d, r14d
0x1400b33cd  jns     short loc_1400B33E4
0x1400b33cf  mov     rcx, rbx
0x1400b33d2  call    DestroyProcessInfo
0x1400b33d7  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400b33dc  mov     eax, r14d
0x1400b33df  jmp     loc_1400B3738
0x1400b33e4  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400b33e9  mov     rcx, [rbx]
0x1400b33ec  call    cs:__imp_PsGetProcessJob
0x1400b33f3  nop     dword ptr [rax+rax+00h]
0x1400b33f8  mov     rsi, rax
0x1400b33fb  test    rax, rax
0x1400b33fe  jz      short loc_1400B33DC
0x1400b3400  mov     rcx, rax
0x1400b3403  call    cs:__imp_PsGetJobUIRestrictionsClass
0x1400b340a  nop     dword ptr [rax+rax+00h]
0x1400b340f  test    eax, eax
0x1400b3411  jz      short loc_1400B33DC
0x1400b3413  xorps   xmm0, xmm0
0x1400b3416  xor     eax, eax
0x1400b3418  mov     rcx, rsi
0x1400b341b  mov     [rbp+57h+var_30], rax
0x1400b341f  movups  [rbp+57h+var_50], xmm0
0x1400b3423  movups  [rbp+57h+var_40], xmm0
0x1400b3427  call    cs:__imp_PsGetJobLock
0x1400b342e  nop     dword ptr [rax+rax+00h]
0x1400b3433  mov     rcx, rax; Resource
0x1400b3436  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400b343d  nop     dword ptr [rax+rax+00h]
0x1400b3442  mov     rax, [rbx]
0x1400b3445  lea     rcx, [rbp+57h+var_50]
0x1400b3449  mov     [rbp+57h+var_30], rax
0x1400b344d  mov     qword ptr [rbp+57h+var_40], rsi
0x1400b3451  mov     dword ptr [rbp+57h+var_40+8], edi
0x1400b3454  call    UserJobCallout
0x1400b3459  mov     rcx, rsi
0x1400b345c  mov     r14d, eax
0x1400b345f  call    cs:__imp_PsGetJobLock
0x1400b3466  nop     dword ptr [rax+rax+00h]
0x1400b346b  mov     rcx, rax; Resource
0x1400b346e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400b3475  nop     dword ptr [rax+rax+00h]
0x1400b347a  jmp     loc_1400B33DC
0x1400b347f  call    cs:__imp_W32GetUserSessionState
0x1400b3486  nop     dword ptr [rax+rax+00h]
0x1400b348b  xor     r8d, r8d
0x1400b348e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400b3495  mov     rcx, rax
0x1400b3498  mov     rsi, rax
0x1400b349b  lea     edi, [r8+1]
0x1400b349f  mov     edx, edi
0x1400b34a1  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1400b34a6  mov     [rsi+10h], rax
0x1400b34aa  mov     rdx, rax
0x1400b34ad  test    rax, rax
0x1400b34b0  jz      loc_1400B3561
0x1400b34b6  xor     ecx, ecx
0x1400b34b8  xor     eax, eax
0x1400b34ba  lock cmpxchg [rdx+208h], ecx
0x1400b34c2  bt      eax, 18h
0x1400b34c6  jnb     loc_1400B3561
0x1400b34cc  mov     al, [rdx+550h]
0x1400b34d2  test    al, al
0x1400b34d4  js      loc_1400B3561
0x1400b34da  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400b34e1  nop     dword ptr [rax+rax+00h]
0x1400b34e6  test    rax, rax
0x1400b34e9  jz      short loc_1400B3561
0x1400b34eb  cmp     qword ptr [rax], 0
0x1400b34ef  jz      short loc_1400B3561
0x1400b34f1  mov     al, [rax+4B0h]
0x1400b34f7  cmp     al, dil
0x1400b34fa  jz      short loc_1400B353D
0x1400b34fc  jmp     short loc_1400B3561
0x1400b34fe  mov     rax, [r14+10h]
0x1400b3502  mov     [rsi+4C58h], rax
0x1400b3509  mov     rax, [r14]
0x1400b350c  mov     qword ptr [r14+10h], 0
0x1400b3514  cmp     [rax+8], edi
0x1400b3517  jnb     short loc_1400B3535
0x1400b3519  mov     [rbp+57h+arg_10], 20000h
0x1400b3520  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400b3527  mov     edx, [rbp+57h+arg_10]
0x1400b352a  mov     r8d, 1236h
0x1400b3530  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400b3535  mov     rcx, [r14]
0x1400b3538  call    HMUnlockObject
0x1400b353d  mov     r14, [rsi+4C58h]
0x1400b3544  test    r14, r14
0x1400b3547  jnz     short loc_1400B34FE
0x1400b3549  lea     rcx, [rsi+4C78h]
0x1400b3550  call    DestroyDeferredUnlockObjectAssignmentList
0x1400b3555  lea     rcx, [rsi+4C68h]
0x1400b355c  call    DestroyDeferredUnlockObjectAssignmentList
0x1400b3561  call    cs:__imp_W32GetUserGdiSessionState
0x1400b3568  nop     dword ptr [rax+rax+00h]
0x1400b356d  cmp     qword ptr [rax+28h], 0
0x1400b3572  jz      short loc_1400B3589
0x1400b3574  call    cs:__imp_W32GetUserGdiSessionState
0x1400b357b  nop     dword ptr [rax+rax+00h]
0x1400b3580  mov     rcx, [rax+28h]
0x1400b3584  cmp     [rbx], rcx
0x1400b3587  jz      short loc_1400B358C
0x1400b3589  xor     dil, dil
0x1400b358c  call    cs:__imp_W32GetUserGdiSessionState
0x1400b3593  nop     dword ptr [rax+rax+00h]
0x1400b3598  mov     rcx, [rax+28h]
0x1400b359c  cmp     [rbx], rcx
0x1400b359f  jnz     short loc_1400B35AD
0x1400b35a1  call    cs:__imp_W32GetUserSessionState
0x1400b35a8  nop     dword ptr [rax+rax+00h]
0x1400b35ad  mov     rcx, [rbx]
0x1400b35b0  test    rcx, rcx
0x1400b35b3  jz      short loc_1400B360F
0x1400b35b5  call    cs:__imp_PsGetProcessJob
0x1400b35bc  nop     dword ptr [rax+rax+00h]
0x1400b35c1  test    rax, rax
0x1400b35c4  jz      short loc_1400B360F
0x1400b35c6  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400b35cd  nop     dword ptr [rax+rax+00h]
0x1400b35d2  mov     rcx, [rax+30h]
0x1400b35d6  mov     rax, [rcx+260h]
0x1400b35dd  test    rax, rax
0x1400b35e0  jz      short loc_1400B360F
0x1400b35e2  call    _guard_dispatch_icall
  ... truncated ...
```
