# CWindowList::ProcessSyncUserDwmMessage(DWMCMD,void *,uint,ulong,_REMOTE_PORT_VIEW const *,uint *)

- ea: `0x1800ddaa0`
- end: `0x1800de44e`
- name: `?ProcessSyncUserDwmMessage@CWindowList@@AEAAJW4DWMCMD@@PEAXIKPEBU_REMOTE_PORT_VIEW@@PEAI@Z`
- size: `2478`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800dd5b0`

## callees

- `0x18001f43c`
- `0x180026ea0`
- `0x180028648`
- `0x1800287e4`
- `0x180029844`
- `0x18002b164`
- `0x180030214`
- `0x18003036c`
- `0x180030aa8`
- `0x180030c84`
- `0x180044e30`
- `0x18004ebfc`
- `0x18005a15c`
- `0x180071cc0`
- `0x180088c9c`
- `0x18008fd58`
- `0x18009dd64`
- `0x18009ddd8`
- `0x18009de78`
- `0x1800acfe0`
- `0x1800b0d7c`
- `0x1800da98c`
- `0x1800dc60c`
- `0x1800dc69c`
- `0x1800dce3c`
- `0x1800dd4c4`
- `0x1800ddaa0`
- `0x1800def44`
- `0x1800df57c`
- `0x1800df7b0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddf20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddf20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddde0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddde0`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x1800dddc4`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x1800dddc4`

## pseudocode

```c
__int64 __fastcall CWindowList::ProcessSyncUserDwmMessage(
        CWindowList *a1,
        int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        struct _REMOTE_PORT_VIEW *a6,
        _DWORD *a7)
{
  unsigned int started; // ebx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  unsigned int IsWindowCapturable; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned __int64 v23; // rcx
  unsigned int ThumbnailSourceSize; // eax
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  struct _GUID v33; // xmm0
  int v34; // eax
  struct _GUID v35; // xmm0
  unsigned __int64 v36; // rcx
  __int64 v37; // r8
  bool v38; // cf
  struct _GUID v39; // xmm0
  __int64 v40; // r9
  __int64 v41; // r8
  CAnimationClockCoordinator *v42; // rcx
  struct _GUID v43; // xmm0
  unsigned int v44; // r8d
  struct _GUID v45; // xmm0
  unsigned int v46; // r8d
  int v47; // edx
  int v48; // edx
  int v49; // edx
  int v50; // edx
  int v51; // edx
  int v52; // edx
  int v53; // edx
  int v54; // edx
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  unsigned int (__fastcall *v58)(__int64, __int64); // r9
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  unsigned int (__fastcall *v62)(__int64, __int64, _QWORD); // r9
  int v63; // edx
  int v64; // edx
  int v65; // edx
  int v66; // edx
  int v67; // edx
  int v68; // edx
  int v69; // edx
  int v70; // r14d
  HWND v71; // rdx
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rcx
  unsigned int (__fastcall *v78)(__int64, _QWORD, _QWORD, __int64); // r10
  unsigned int v80; // [rsp+20h] [rbp-38h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID Buf2; // [rsp+40h] [rbp-18h] BYREF
  bool v83; // [rsp+98h] [rbp+40h] BYREF

  started = -2147024872;
  if ( a2 > 1073741948 )
  {
    if ( a2 > 1073741964 )
    {
      v63 = a2 - 1073741965;
      if ( !v63 )
      {
        if ( a4 != 24 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 20) )
        {
          v76 = CWindowList::ConvertLargeIntegerToDwmWindowCloseEventToken(
                  *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59),
                  &Buf2);
          return v78(v77, *(_QWORD *)(a3 + 4), *(unsigned int *)(a3 + 12), v76);
        }
        return (unsigned int)-2147024891;
      }
      v64 = v63 - 1;
      if ( v64 )
      {
        v65 = v64 - 2;
        if ( !v65 )
        {
          if ( a4 != 12 )
            return started;
          if ( a5 == *(_DWORD *)(a3 + 8) )
          {
            v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
            goto LABEL_96;
          }
          return (unsigned int)-2147024891;
        }
        v66 = v65 - 1;
        if ( !v66 )
        {
          if ( a4 != 12 )
            return started;
          if ( a5 == *(_DWORD *)(a3 + 8) )
          {
            v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
            goto LABEL_96;
          }
          return (unsigned int)-2147024891;
        }
        v67 = v66 - 1;
        if ( v67 )
        {
          v68 = v67 - 2;
          if ( v68 )
          {
            v69 = v68 - 1;
            if ( v69 )
            {
              if ( v69 != 1 )
                return (unsigned int)-2147467263;
              v70 = 0;
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
                return (unsigned int)-2147467263;
              if ( a4 != 16 )
                return started;
              v71 = *(HWND *)(a3 + 4);
              v83 = 0;
              IsWindowCapturable = CWindowList::IsWindowCapturable(a1, v71, &v83);
              LOBYTE(v70) = v83;
              *(_DWORD *)(a3 + 12) = v70;
              goto LABEL_18;
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
              return (unsigned int)-2147467263;
            if ( a4 != 20 )
              return started;
            if ( a5 == *(_DWORD *)(a3 + 16) )
            {
              v73 = (_QWORD *)CWindowList::ConvertLargeIntegerToDwmWindowCloseEventToken(v72, &Buf2);
              return (unsigned int)CWindowList::UnregisterWindowCloseEvent(a1, *(_QWORD *)(a3 + 4), *v73);
            }
          }
          else
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
              return (unsigned int)-2147467263;
            if ( a4 != 28 )
              return started;
            if ( a5 == *(_DWORD *)(a3 + 24) )
            {
              v75 = (_QWORD *)CWindowList::ConvertLargeIntegerToDwmWindowCloseEventToken(v74, &Buf2);
              return (unsigned int)CWindowList::RegisterWindowCloseEvent(
                                     a1,
                                     *(_QWORD *)(a3 + 4),
                                     *(_QWORD *)(a3 + 12),
                                     *v75);
            }
          }
          return (unsigned int)-2147024891;
        }
        if ( a4 != 16 )
          return started;
        if ( a5 != *(_DWORD *)(a3 + 8) )
          return (unsigned int)-2147024891;
        v59 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
      }
      else
      {
        if ( a4 != 16 )
          return started;
        if ( a5 != *(_DWORD *)(a3 + 8) )
          return (unsigned int)-2147024891;
        v59 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
      }
    }
    else
    {
      if ( a2 == 1073741964 )
      {
        if ( a4 != 12 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 8) )
        {
          v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
          goto LABEL_96;
        }
        return (unsigned int)-2147024891;
      }
      v47 = a2 - 1073741950;
      if ( !v47 )
      {
        if ( a4 == 28 )
          return (unsigned int)CWindowList::UpdateAccentBlurRect(
                                 a1,
                                 (const struct MILCMD_DWM_REDIRECTION_ACCENTBLURRECTUPDATE *)a3);
        return started;
      }
      v48 = v47 - 1;
      if ( !v48 )
      {
        if ( a4 == 20 )
          return (unsigned int)CDesktopManager::UpdateSDRToHDRBoost(
                                 CDesktopManager::s_pDesktopManagerInstance,
                                 *(HMONITOR *)(a3 + 4),
                                 *(double *)(a3 + 12));
        return started;
      }
      v49 = v48 - 3;
      if ( !v49 )
      {
        if ( a4 != 12 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 8) )
        {
          v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
          goto LABEL_96;
        }
        return (unsigned int)-2147024891;
      }
      v50 = v49 - 2;
      if ( !v50 )
      {
        if ( a4 != 12 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 8) )
        {
          v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
          goto LABEL_96;
        }
        return (unsigned int)-2147024891;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        if ( a4 != 12 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 8) )
        {
          v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
          goto LABEL_96;
        }
        return (unsigned int)-2147024891;
      }
      v52 = v51 - 1;
      if ( !v52 )
      {
        if ( a4 != 12 )
          return started;
        if ( a5 == *(_DWORD *)(a3 + 8) )
        {
          v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
          goto LABEL_96;
        }
        return (unsigned int)-2147024891;
      }
      v53 = v52 - 2;
      if ( v53 )
      {
        v54 = v53 - 1;
        if ( v54 )
        {
          if ( v54 != 2 )
            return (unsigned int)-2147467263;
          if ( a4 != 12 )
            return started;
          if ( a5 == *(_DWORD *)(a3 + 8) )
          {
            v55 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
LABEL_96:
            v56 = CWindowList::ConvertLargeIntegerToDwmWindowCloseEventToken(v55, &Buf2);
            return v58(v57, v56);
          }
          return (unsigned int)-2147024891;
        }
        if ( a4 != 16 )
          return started;
        if ( a5 != *(_DWORD *)(a3 + 8) )
          return (unsigned int)-2147024891;
        v59 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
      }
      else
      {
        if ( a4 != 16 )
          return started;
        if ( a5 != *(_DWORD *)(a3 + 8) )
          return (unsigned int)-2147024891;
        v59 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 59);
      }
    }
    v60 = CWindowList::ConvertLargeIntegerToDwmWindowCloseEventToken(v59, &Buf2);
    return v62(v61, v60, *(unsigned int *)(a3 + 12));
  }
  if ( a2 == 1073741948 )
  {
    if ( a4 == 64 )
      return (unsigned int)CWindowList::TransitionBitmap(
                             a1,
                             (const struct MILCMD_DWM_REDIRECTION_TRANSITIONBITMAP *)a3,
                             a6);
    return started;
  }
  if ( a2 > 1073741890 )
  {
    v25 = a2 - 1073741897;
    if ( !v25 )
    {
      if ( a4 == 48 )
      {
        started = CWindowList::StartTransition(a1, (struct MILCMD_DWM_REDIRECTION_STARTTRANSITION *)a3);
        *a7 = 48;
      }
      return started;
    }
    v26 = v25 - 20;
    if ( !v26 )
    {
      if ( a4 == 8 )
      {
        *(_QWORD *)&Buf2.Data1 = &CDesktopManager::s_csDwmInstance;
        EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
        *((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 23) = *(_DWORD *)(a3 + 4) != 0;
        *a7 = 8;
        CGuard<CDwmCS>::~CGuard<CDwmCS>(&Buf2);
      }
      return started;
    }
    v27 = v26 - 5;
    if ( !v27 )
    {
      if ( a4 == 24 )
      {
        v45 = *(struct _GUID *)(a3 + 4);
        v46 = *(_DWORD *)(a3 + 20);
        Buf2 = v45;
        return (unsigned int)CAnimationClockCoordinator::OnCreateAnimationClock(
                               *((CAnimationClockCoordinator **)CDesktopManager::s_pDesktopManagerInstance + 21),
                               &Buf2,
                               v46);
      }
      return started;
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      if ( a4 == 24 )
      {
        v43 = *(struct _GUID *)(a3 + 4);
        v44 = *(_DWORD *)(a3 + 20);
        Buf2 = v43;
        return (unsigned int)CAnimationClockCoordinator::OnBeginAnimationClock(
                               *((CAnimationClockCoordinator **)CDesktopManager::s_pDesktopManagerInstance + 21),
                               &Buf2,
                               v44);
      }
      return started;
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      if ( a4 == 20 )
      {
        v42 = (CAnimationClockCoordinator *)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 21);
        Buf2 = *(struct _GUID *)(a3 + 4);
        return (unsigned int)CAnimationClockCoordinator::OnEndAnimationClock(v42, &Buf2);
      }
      return started;
    }
    v30 = v29 - 1;
    if ( !v30 )
    {
      if ( a4 == 32 )
      {
        v39 = *(struct _GUID *)(a3 + 4);
        v40 = a3 + 24;
        v41 = *(unsigned int *)(a3 + 20);
        Buf2 = v39;
        started = CAnimationClockCoordinator::OnGetAnimationClockTime(
                    *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 21),
                    &Buf2,
                    v41,
                    v40);
        *a7 = 32;
      }
      return started;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      if ( a4 == 32 )
      {
        v35 = *(struct _GUID *)(a3 + 4);
        v36 = a3 + 24;
        v37 = *(unsigned int *)(a3 + 20);
        v38 = *(_QWORD *)v36 != 0;
        Buf2 = v35;
        return (unsigned int)CAnimationClockCoordinator::OnSetAnimationClockTime(
                               *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 21),
                               &Buf2,
                               v37,
                               v36 & -(__int64)v38);
      }
      return started;
    }
    v32 = v31 - 1;
    if ( v32 )
    {
      if ( v32 != 1 )
        return (unsigned int)-2147467263;
      if ( a4 != 28 )
        return started;
      hObject[0] = 0;
      started = CAnimationClockCoordinator::OnGetSynchronizationCommitHandle(
                  *((CAnimationClockCoordinator **)CDesktopManager::s_pDesktopManagerInstance + 21),
                  (const struct _GUID *)(a3 + 4),
                  a5,
                  hObject);
      *(HANDLE *)(a3 + 20) = hObject[0];
    }
    else
    {
      if ( a4 != 28 )
        return started;
      v33 = *(struct _GUID *)(a3 + 4);
      hObject[0] = 0;
      Buf2 = v33;
      started = CAnimationClockCoordinator::OnGetAnimationClockToken(
                  *((CAnimationClockCoordinator **)CDesktopManager::s_pDesktopManagerInstance + 21),
                  &Buf2,
                  hObject);
      if ( (started & 0x80000000) == 0 )
      {
        *(_QWORD *)&Buf2.Data1 = 0;
        v34 = NtDCompositionDuplicateHandleToProcess(hObject[0], a5, &Buf2);
        started = v34 | 0x10000000;
        if ( v34 >= 0 )
          *(_QWORD *)(a3 + 20) = *(_QWORD *)&Buf2.Data1;
        CloseHandle(hObject[0]);
      }
    }
    *a7 = 28;
    return started;
  }
  if ( a2 == 1073741890 )
  {
    if ( a4 == 16 )
      return (unsigned int)CContactManager::OnFlick(
                             *((CContactManager **)CDesktopManager::s_pDesktopManagerInstance + 20),
                             (const struct MILCMD_DWM_REDIRECTION_RENDERFLICK *)a3);
    return started;
  }
  v11 = a2 - 1073741856;
  if ( !v11 )
  {
    if ( a4 == 57 )
      return (unsigned int)CWindowList::UpdateThumbnailProperties(
                             a1,
                             a5,
                             (struct MILCMD_DWM_REDIRECTION_UPDATETHUMBNAILPROPERTIES *)a3);
    return started;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( a4 == 12 )
      return (unsigned int)CWindowList::UnregisterThumbnail(
                             a1,
                             a5,
                             (const struct MILCMD_DWM_REDIRECTION_UNREGISTERTHUMBNAIL *)a3);
    return started;
  }
  v13 = v12 - 2;
  if ( !v13 )
  {
    if ( a4 != 20 )
      return started;
    ThumbnailSourceSize = CWindowList::QueryThumbnailSourceSize(
                            a1,
                            a5,
                            (struct MILCMD_DWM_REDIRECTION_QUERYTHUMBNAILSOURCESIZE *)a3);
    goto LABEL_42;
  }
  v14 = v13 - 6;
  if ( !v14 )
  {
    if ( a4 == 36 )
      return (unsigned int)CWindowList::SetColorizationParameters(
                             a1,
                             (const struct MILCMD_DWM_REDIRECTION_SETCOLORIZATIONPARAMETERS *)a3);
    return started;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    if ( a4 == 36 )
    {
      CWindowList::GetColorizationParameters(a1, (struct MILCMD_DWM_REDIRECTION_GETCOLORIZATIONPARAMETERS *)a3);
      started = 0;
      *a7 = 36;
    }
    return started;
  }
  v16 = v15 - 9;
  if ( !v16 )
  {
    if ( a4 != 20 )
      return started;
    ThumbnailSourceSize = CWindowList::GetGlobalState(a1, (struct MILCMD_DWM_REDIRECTION_GETGLOBALSTATE *)a3);
LABEL_42:
    started = ThumbnailSourceSize;
    *a7 = 20;
    return started;
  }
  v17 = v16 - 6;
  if ( v17 )
  {
    v18 = v17 - 3;
    if ( v18 )
    {
      if ( v18 == 5 )
      {
        if ( a4 == 32 )
          return (unsigned int)CContactManager::OnGesture(
                                 *((CContactManager **)CDesktopManager::s_pDesktopManagerInstance + 20),
                                 (const struct MILCMD_DWM_REDIRECTION_RENDERGESTURE *)a3);
        return started;
      }
      return (unsigned int)-2147467263;
    }
    if ( a4 != 16 )
      return started;
    IsWindowCapturable = CWindowList::QueryThumbnailType(a1, a5, (struct MILCMD_DWM_REDIRECTION_QUERYTHUMBNAILTYPE *)a3);
LABEL_18:
    started = IsWindowCapturable;
    *a7 = 16;
    return started;
  }
  if ( !CDesktopManager::IsLivePreviewAllowed() )
    return (unsigned int)-2147024846;
  v21 = *(unsigned int *)(a3 + 8);
  if ( (unsigned __int64)(8 * v21) > 0xFFFFFFFF )
  {
    v80 = 1099;
    goto LABEL_33;
  }
  v22 = 8 * v21 + 32;
  if ( v22 < 0x20 )
  {
    v80 = 1100;
    goto LABEL_33;
  }
  if ( !*(_DWORD *)(a3 + 28) )
    goto LABEL_27;
  v23 = 16 * v21;
  if ( v23 > 0xFFFFFFFF )
  {
    v80 = 1106;
    goto LABEL_33;
  }
  if ( (unsigned int)v23 + v22 < v22 )
  {
    v80 = 1107;
LABEL_33:
    started = -2147024362;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024362, v80, 0);
    return started;
  }
  v22 += v23;
LABEL_27:
  started = 0;
  if ( a4 == v22 )
    return (unsigned int)CWindowList::PostActivateLivePreview(
                           a1,
                           (const struct MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW *)a3);
  return started;
}

```

## disassembly

```asm
0x1800ddaa0  push    rbp
0x1800ddaa2  push    rbx
0x1800ddaa3  push    rsi
0x1800ddaa4  push    rdi
0x1800ddaa5  push    r14
0x1800ddaa7  push    r15
0x1800ddaa9  mov     rbp, rsp
0x1800ddaac  sub     rsp, 58h
0x1800ddab0  mov     eax, 4000007Ch
0x1800ddab5  mov     esi, r9d
0x1800ddab8  mov     rdi, r8
0x1800ddabb  mov     r15, rcx
0x1800ddabe  mov     ebx, 80070018h
0x1800ddac3  cmp     edx, eax
0x1800ddac5  jg      loc_1800DDF86
0x1800ddacb  jz      loc_1800DDF6C
0x1800ddad1  mov     eax, 40000042h
0x1800ddad6  cmp     edx, eax
0x1800ddad8  jg      loc_1800DDCEF
0x1800ddade  jz      loc_1800DDCCB
0x1800ddae4  sub     edx, 40000020h
0x1800ddaea  jz      loc_1800DDCB5
0x1800ddaf0  sub     edx, 1
0x1800ddaf3  jz      loc_1800DDC9F
0x1800ddaf9  sub     edx, 2
0x1800ddafc  jz      loc_1800DDC7D
0x1800ddb02  sub     edx, 6
0x1800ddb05  jz      loc_1800DDC67
0x1800ddb0b  sub     edx, 1
0x1800ddb0e  jz      loc_1800DDC45
0x1800ddb14  sub     edx, 9
0x1800ddb17  jz      loc_1800DDC32
0x1800ddb1d  sub     edx, 6
0x1800ddb20  jz      short loc_1800DDB77
0x1800ddb22  sub     edx, 3
0x1800ddb25  jz      short loc_1800DDB55
0x1800ddb27  cmp     edx, 5
0x1800ddb2a  jnz     loc_1800DE316
0x1800ddb30  cmp     r9d, 20h ; ' '
0x1800ddb34  jnz     loc_1800DE43F
0x1800ddb3a  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddb41  mov     rdx, r8; struct MILCMD_DWM_REDIRECTION_RENDERGESTURE *
0x1800ddb44  mov     rcx, [rcx+0A0h]; this
0x1800ddb4b  call    ?OnGesture@CContactManager@@QEAAJPEBUMILCMD_DWM_REDIRECTION_RENDERGESTURE@@@Z; CContactManager::OnGesture(MILCMD_DWM_REDIRECTION_RENDERGESTURE const *)
0x1800ddb50  jmp     loc_1800DE43D
0x1800ddb55  cmp     esi, 10h
0x1800ddb58  jnz     loc_1800DE43F
0x1800ddb5e  mov     edx, [rbp+arg_20]; unsigned int
0x1800ddb61  call    ?QueryThumbnailType@CWindowList@@AEAAJKPEAUMILCMD_DWM_REDIRECTION_QUERYTHUMBNAILTYPE@@@Z; CWindowList::QueryThumbnailType(ulong,MILCMD_DWM_REDIRECTION_QUERYTHUMBNAILTYPE *)
0x1800ddb66  mov     ebx, eax
0x1800ddb68  mov     rax, [rbp+arg_30]
0x1800ddb6c  mov     dword ptr [rax], 10h
0x1800ddb72  jmp     loc_1800DE43F
0x1800ddb77  call    ?IsLivePreviewAllowed@CDesktopManager@@SA_NXZ; CDesktopManager::IsLivePreviewAllowed(void)
0x1800ddb7c  xor     r14d, r14d
0x1800ddb7f  test    al, al
0x1800ddb81  jnz     short loc_1800DDB8D
0x1800ddb83  mov     ebx, 80070032h
0x1800ddb88  jmp     loc_1800DE43F
0x1800ddb8d  mov     ecx, [rdi+8]
0x1800ddb90  mov     edx, 0FFFFFFFFh
0x1800ddb95  lea     rax, ds:0[rcx*8]
0x1800ddb9d  cmp     rax, rdx
0x1800ddba0  ja      short loc_1800DDC0A
0x1800ddba2  add     eax, 20h ; ' '
0x1800ddba5  cmp     eax, 20h ; ' '
0x1800ddba8  jb      short loc_1800DDBFB
0x1800ddbaa  cmp     [rdi+1Ch], r14d
0x1800ddbae  jz      short loc_1800DDBC2
0x1800ddbb0  shl     rcx, 4
0x1800ddbb4  cmp     rcx, rdx
0x1800ddbb7  ja      short loc_1800DDBEC
0x1800ddbb9  lea     edx, [rcx+rax]
0x1800ddbbc  cmp     edx, eax
0x1800ddbbe  jb      short loc_1800DDBDD
0x1800ddbc0  mov     eax, edx
0x1800ddbc2  mov     ebx, r14d
0x1800ddbc5  cmp     esi, eax
0x1800ddbc7  jnz     loc_1800DE43F
0x1800ddbcd  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW *
0x1800ddbd0  mov     rcx, r15; this
0x1800ddbd3  call    ?PostActivateLivePreview@CWindowList@@AEAAJPEBUMILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW@@@Z; CWindowList::PostActivateLivePreview(MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW const *)
0x1800ddbd8  jmp     loc_1800DE43D
0x1800ddbdd  mov     [rsp+58h+var_30], r14
0x1800ddbe2  mov     [rsp+58h+var_38], 453h
0x1800ddbea  jmp     short loc_1800DDC17
0x1800ddbec  mov     [rsp+58h+var_30], r14
0x1800ddbf1  mov     [rsp+58h+var_38], 452h
0x1800ddbf9  jmp     short loc_1800DDC17
0x1800ddbfb  mov     [rsp+58h+var_30], r14
0x1800ddc00  mov     [rsp+58h+var_38], 44Ch
0x1800ddc08  jmp     short loc_1800DDC17
0x1800ddc0a  mov     [rsp+58h+var_30], r14; void *
0x1800ddc0f  mov     [rsp+58h+var_38], 44Bh; unsigned int
0x1800ddc17  xor     edx, edx; int *
0x1800ddc19  mov     r9d, 80070216h; int
0x1800ddc1f  xor     r8d, r8d; unsigned int
0x1800ddc22  mov     ebx, r9d
0x1800ddc25  lea     ecx, [rdx+14h]; unsigned int
0x1800ddc28  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800ddc2d  jmp     loc_1800DE43F
0x1800ddc32  cmp     esi, 14h
0x1800ddc35  jnz     loc_1800DE43F
0x1800ddc3b  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_GETGLOBALSTATE *
0x1800ddc3e  call    ?GetGlobalState@CWindowList@@AEAAJPEAUMILCMD_DWM_REDIRECTION_GETGLOBALSTATE@@@Z; CWindowList::GetGlobalState(MILCMD_DWM_REDIRECTION_GETGLOBALSTATE *)
0x1800ddc43  jmp     short loc_1800DDC8E
0x1800ddc45  cmp     esi, 24h ; '$'
0x1800ddc48  jnz     loc_1800DE43F
0x1800ddc4e  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_GETCOLORIZATIONPARAMETERS *
0x1800ddc51  call    ?GetColorizationParameters@CWindowList@@AEAAXPEAUMILCMD_DWM_REDIRECTION_GETCOLORIZATIONPARAMETERS@@@Z; CWindowList::GetColorizationParameters(MILCMD_DWM_REDIRECTION_GETCOLORIZATIONPARAMETERS *)
0x1800ddc56  mov     rax, [rbp+arg_30]
0x1800ddc5a  xor     r14d, r14d
0x1800ddc5d  mov     ebx, r14d
0x1800ddc60  mov     [rax], esi
0x1800ddc62  jmp     loc_1800DE43F
0x1800ddc67  cmp     esi, 24h ; '$'
0x1800ddc6a  jnz     loc_1800DE43F
0x1800ddc70  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_SETCOLORIZATIONPARAMETERS *
0x1800ddc73  call    ?SetColorizationParameters@CWindowList@@AEAAJPEBUMILCMD_DWM_REDIRECTION_SETCOLORIZATIONPARAMETERS@@@Z; CWindowList::SetColorizationParameters(MILCMD_DWM_REDIRECTION_SETCOLORIZATIONPARAMETERS const *)
0x1800ddc78  jmp     loc_1800DE43D
0x1800ddc7d  cmp     esi, 14h
0x1800ddc80  jnz     loc_1800DE43F
0x1800ddc86  mov     edx, [rbp+arg_20]; unsigned int
0x1800ddc89  call    ?QueryThumbnailSourceSize@CWindowList@@AEAAJKPEAUMILCMD_DWM_REDIRECTION_QUERYTHUMBNAILSOURCESIZE@@@Z; CWindowList::QueryThumbnailSourceSize(ulong,MILCMD_DWM_REDIRECTION_QUERYTHUMBNAILSOURCESIZE *)
0x1800ddc8e  mov     ebx, eax
0x1800ddc90  mov     rax, [rbp+arg_30]
0x1800ddc94  mov     dword ptr [rax], 14h
0x1800ddc9a  jmp     loc_1800DE43F
0x1800ddc9f  cmp     esi, 0Ch
0x1800ddca2  jnz     loc_1800DE43F
0x1800ddca8  mov     edx, [rbp+arg_20]; unsigned int
0x1800ddcab  call    ?UnregisterThumbnail@CWindowList@@AEAAJKPEBUMILCMD_DWM_REDIRECTION_UNREGISTERTHUMBNAIL@@@Z; CWindowList::UnregisterThumbnail(ulong,MILCMD_DWM_REDIRECTION_UNREGISTERTHUMBNAIL const *)
0x1800ddcb0  jmp     loc_1800DE43D
0x1800ddcb5  cmp     esi, 39h ; '9'
0x1800ddcb8  jnz     loc_1800DE43F
0x1800ddcbe  mov     edx, [rbp+arg_20]; unsigned int
0x1800ddcc1  call    ?UpdateThumbnailProperties@CWindowList@@AEAAJKPEAUMILCMD_DWM_REDIRECTION_UPDATETHUMBNAILPROPERTIES@@@Z; CWindowList::UpdateThumbnailProperties(ulong,MILCMD_DWM_REDIRECTION_UPDATETHUMBNAILPROPERTIES *)
0x1800ddcc6  jmp     loc_1800DE43D
0x1800ddccb  cmp     esi, 10h
0x1800ddcce  jnz     loc_1800DE43F
0x1800ddcd4  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddcdb  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_RENDERFLICK *
0x1800ddcde  mov     rcx, [rcx+0A0h]; this
0x1800ddce5  call    ?OnFlick@CContactManager@@QEAAJPEBUMILCMD_DWM_REDIRECTION_RENDERFLICK@@@Z; CContactManager::OnFlick(MILCMD_DWM_REDIRECTION_RENDERFLICK const *)
0x1800ddcea  jmp     loc_1800DE43D
0x1800ddcef  sub     edx, 40000049h
0x1800ddcf5  jz      loc_1800DDF4E
0x1800ddcfb  sub     edx, 14h
0x1800ddcfe  jz      loc_1800DDF0C
0x1800ddd04  sub     edx, 5
0x1800ddd07  jz      loc_1800DDED9
0x1800ddd0d  sub     edx, 1
0x1800ddd10  jz      loc_1800DDEA6
0x1800ddd16  sub     edx, 1
0x1800ddd19  jz      loc_1800DDE77
0x1800ddd1f  sub     edx, 1
0x1800ddd22  jz      loc_1800DDE38
0x1800ddd28  sub     edx, 1
0x1800ddd2b  jz      loc_1800DDDF5
0x1800ddd31  sub     edx, 1
0x1800ddd34  jz      short loc_1800DDD7A
0x1800ddd36  cmp     edx, 1
0x1800ddd39  jnz     loc_1800DE316
0x1800ddd3f  cmp     esi, 1Ch
0x1800ddd42  jnz     loc_1800DE43F
0x1800ddd48  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddd4f  lea     rdx, [r8+4]; struct _GUID *
0x1800ddd53  mov     r8d, [rbp+arg_20]; unsigned int
0x1800ddd57  lea     r9, [rbp+hObject]; void **
0x1800ddd5b  xor     r14d, r14d
0x1800ddd5e  mov     [rbp+hObject], r14
0x1800ddd62  mov     rcx, [rcx+0A8h]; this
0x1800ddd69  call    ?OnGetSynchronizationCommitHandle@CAnimationClockCoordinator@@QEAAJAEBU_GUID@@KPEAPEAX@Z; CAnimationClockCoordinator::OnGetSynchronizationCommitHandle(_GUID const &,ulong,void * *)
0x1800ddd6e  mov     ebx, eax
0x1800ddd70  mov     rax, [rbp+hObject]
0x1800ddd74  mov     [rdi+14h], rax
0x1800ddd78  jmp     short loc_1800DDDE6
0x1800ddd7a  cmp     esi, 1Ch
0x1800ddd7d  jnz     loc_1800DE43F
0x1800ddd83  movups  xmm0, xmmword ptr [r8+4]
0x1800ddd88  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddd8f  lea     r8, [rbp+hObject]; void **
0x1800ddd93  xor     r14d, r14d
0x1800ddd96  lea     rdx, [rbp+Buf2]; struct _GUID
0x1800ddd9a  mov     [rbp+hObject], r14
0x1800ddd9e  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800ddda3  mov     rcx, [rcx+0A8h]; this
0x1800dddaa  call    ?OnGetAnimationClockToken@CAnimationClockCoordinator@@QEAAJU_GUID@@PEAPEAX@Z; CAnimationClockCoordinator::OnGetAnimationClockToken(_GUID,void * *)
0x1800dddaf  mov     ebx, eax
0x1800dddb1  test    eax, eax
0x1800dddb3  js      short loc_1800DDDE6
0x1800dddb5  mov     edx, [rbp+arg_20]
0x1800dddb8  lea     r8, [rbp+Buf2]
0x1800dddbc  mov     rcx, [rbp+hObject]
0x1800dddc0  mov     qword ptr [rbp+Buf2.Data1], r14
0x1800dddc4  call    cs:__imp_NtDCompositionDuplicateHandleToProcess
0x1800dddca  mov     ebx, eax
0x1800dddcc  or      ebx, 10000000h
0x1800dddd2  jl      short loc_1800DDDDC
0x1800dddd4  mov     rax, qword ptr [rbp+Buf2.Data1]
0x1800dddd8  mov     [rdi+14h], rax
0x1800ddddc  mov     rcx, [rbp+hObject]; hObject
0x1800ddde0  call    cs:__imp_CloseHandle
0x1800ddde6  mov     rax, [rbp+arg_30]
0x1800dddea  mov     dword ptr [rax], 1Ch
0x1800dddf0  jmp     loc_1800DE43F
0x1800dddf5  cmp     esi, 20h ; ' '
0x1800dddf8  jnz     loc_1800DE43F
0x1800dddfe  movups  xmm0, xmmword ptr [r8+4]
0x1800dde03  lea     rcx, [r8+18h]
0x1800dde07  mov     r8d, [r8+14h]
0x1800dde0b  mov     rax, [rcx]
0x1800dde0e  lea     rdx, [rbp+Buf2]
0x1800dde12  neg     rax
0x1800dde15  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800dde1a  sbb     r9, r9
0x1800dde1d  and     r9, rcx
0x1800dde20  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800dde27  mov     rcx, [rcx+0A8h]
0x1800dde2e  call    ?OnSetAnimationClockTime@CAnimationClockCoordinator@@QEAAJU_GUID@@W4DWMPANIMATION_CLOCK_TIME@@PEBT_LARGE_INTEGER@@@Z; CAnimationClockCoordinator::OnSetAnimationClockTime(_GUID,DWMPANIMATION_CLOCK_TIME,_LARGE_INTEGER const *)
0x1800dde33  jmp     loc_1800DE43D
0x1800dde38  cmp     esi, 20h ; ' '
0x1800dde3b  jnz     loc_1800DE43F
0x1800dde41  movups  xmm0, xmmword ptr [r8+4]
0x1800dde46  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800dde4d  lea     r9, [r8+18h]
0x1800dde51  mov     r8d, [r8+14h]
0x1800dde55  lea     rdx, [rbp+Buf2]
0x1800dde59  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800dde5e  mov     rcx, [rcx+0A8h]
0x1800dde65  call    ?OnGetAnimationClockTime@CAnimationClockCoordinator@@QEAAJU_GUID@@W4DWMPANIMATION_CLOCK_TIME@@PEAT_LARGE_INTEGER@@@Z; CAnimationClockCoordinator::OnGetAnimationClockTime(_GUID,DWMPANIMATION_CLOCK_TIME,_LARGE_INTEGER *)
0x1800dde6a  mov     ebx, eax
0x1800dde6c  mov     rax, [rbp+arg_30]
0x1800dde70  mov     [rax], esi
0x1800dde72  jmp     loc_1800DE43F
0x1800dde77  cmp     esi, 14h
0x1800dde7a  jnz     loc_1800DE43F
0x1800dde80  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800dde87  lea     rdx, [rbp+Buf2]; struct _GUID
0x1800dde8b  movups  xmm0, xmmword ptr [r8+4]
0x1800dde90  mov     rcx, [rcx+0A8h]; this
0x1800dde97  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800dde9c  call    ?OnEndAnimationClock@CAnimationClockCoordinator@@QEAAJU_GUID@@@Z; CAnimationClockCoordinator::OnEndAnimationClock(_GUID)
0x1800ddea1  jmp     loc_1800DE43D
0x1800ddea6  cmp     esi, 18h
0x1800ddea9  jnz     loc_1800DE43F
0x1800ddeaf  movups  xmm0, xmmword ptr [r8+4]
0x1800ddeb4  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddebb  lea     rdx, [rbp+Buf2]; struct _GUID
0x1800ddebf  mov     r8d, [r8+14h]; unsigned int
0x1800ddec3  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800ddec8  mov     rcx, [rcx+0A8h]; this
0x1800ddecf  call    ?OnBeginAnimationClock@CAnimationClockCoordinator@@QEAAJU_GUID@@K@Z; CAnimationClockCoordinator::OnBeginAnimationClock(_GUID,ulong)
0x1800dded4  jmp     loc_1800DE43D
0x1800dded9  cmp     esi, 18h
0x1800ddedc  jnz     loc_1800DE43F
0x1800ddee2  movups  xmm0, xmmword ptr [r8+4]
0x1800ddee7  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddeee  lea     rdx, [rbp+Buf2]; Buf2
0x1800ddef2  mov     r8d, [r8+14h]; unsigned int
0x1800ddef6  movdqu  xmmword ptr [rbp+Buf2.Data1], xmm0
0x1800ddefb  mov     rcx, [rcx+0A8h]; this
0x1800ddf02  call    ?OnCreateAnimationClock@CAnimationClockCoordinator@@QEAAJU_GUID@@K@Z; CAnimationClockCoordinator::OnCreateAnimationClock(_GUID,ulong)
0x1800ddf07  jmp     loc_1800DE43D
0x1800ddf0c  cmp     esi, 8
0x1800ddf0f  jnz     loc_1800DE43F
0x1800ddf15  lea     rcx, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; lpCriticalSection
0x1800ddf1c  mov     qword ptr [rbp+Buf2.Data1], rcx
0x1800ddf20  call    cs:__imp_EnterCriticalSection
0x1800ddf26  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ddf2d  xor     r14d, r14d
0x1800ddf30  cmp     [rdi+4], r14d
0x1800ddf34  setnz   cl
0x1800ddf37  mov     [rax+17h], cl
0x1800ddf3a  lea     rcx, [rbp+Buf2]
0x1800ddf3e  mov     rax, [rbp+arg_30]
0x1800ddf42  mov     [rax], esi
0x1800ddf44  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x1800ddf49  jmp     loc_1800DE43F
0x1800ddf4e  cmp     esi, 30h ; '0'
0x1800ddf51  jnz     loc_1800DE43F
0x1800ddf57  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_STARTTRANSITION *
0x1800ddf5a  call    ?StartTransition@CWindowList@@AEAAJPEAUMILCMD_DWM_REDIRECTION_STARTTRANSITION@@@Z; CWindowList::StartTransition(MILCMD_DWM_REDIRECTION_STARTTRANSITION *)
0x1800ddf5f  mov     ebx, eax
0x1800ddf61  mov     rax, [rbp+arg_30]
0x1800ddf65  mov     [rax], esi
0x1800ddf67  jmp     loc_1800DE43F
0x1800ddf6c  cmp     esi, 40h ; '@'
0x1800ddf6f  jnz     loc_1800DE43F
0x1800ddf75  mov     r8, [rbp+arg_28]; struct _REMOTE_PORT_VIEW *
0x1800ddf79  mov     rdx, rdi; struct MILCMD_DWM_REDIRECTION_TRANSITIONBITMAP *
0x1800ddf7c  call    ?TransitionBitmap@CWindowList@@AEAAJPEBUMILCMD_DWM_REDIRECTION_TRANSITIONBITMAP@@PEBU_REMOTE_PORT_VIEW@@@Z; CWindowList::TransitionBitmap(MILCMD_DWM_REDIRECTION_TRANSITIONBITMAP const *,_REMOTE_PORT_VIEW const *)
0x1800ddf81  jmp     loc_1800DE43D
0x1800ddf86  mov     eax, 4000008Ch
0x1800ddf8b  cmp     edx, eax
0x1800ddf8d  jg      loc_1800DE1F6
0x1800ddf93  jz      loc_1800DE1BF
0x1800ddf99  sub     edx, 4000007Eh
0x1800ddf9f  jz      loc_1800DE1A9
0x1800ddfa5  sub     edx, 1
  ... truncated ...
```
