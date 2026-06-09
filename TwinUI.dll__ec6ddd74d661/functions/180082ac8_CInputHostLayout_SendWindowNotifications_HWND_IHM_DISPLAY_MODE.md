# CInputHostLayout::_SendWindowNotifications(HWND__ *,IHM_DISPLAY_MODE)

- ea: `0x180082ac8`
- end: `0x1800831e9`
- name: `?_SendWindowNotifications@CInputHostLayout@@AEAAJPEAUHWND__@@W4IHM_DISPLAY_MODE@@@Z`
- size: `1825`
- prototype: `int __high(HWND, enum IHM_DISPLAY_MODE)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180082aa0`

## callees

- `0x180009dd0`
- `0x1800374ac`
- `0x18004c11c`
- `0x180082ac8`
- `0x1800831f0`
- `0x180083248`
- `0x1800832c8`
- `0x180085788`
- `0x1801000ec`
- `0x180142e10`
- `0x18026252c`
- `0x180262574`
- `0x1802625bc`
- `0x18026265c`
- `0x180262898`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082b0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008310d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082b0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008310d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083144`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180082bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180082bcc`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c24`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c5d`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c96`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c24`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c5d`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082c96`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180083045`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180083045`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d0d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d21`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d35`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d0d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d21`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180082d35`

## pseudocode

```c
__int64 __fastcall CInputHostLayout::_SendWindowNotifications(RTL_SRWLOCK *a1, RTL_SRWLOCK *a2, unsigned int a3)
{
  __int64 v6; // rbx
  RTL_SRWLOCK *v7; // r12
  char *i; // rsi
  __int64 v9; // rsi
  int v10; // r14d
  RTL_SRWLOCK *v11; // rsi
  DWORD v12; // r14d
  CGITRegistrationList *v13; // rsi
  int v14; // r15d
  DWORD v15; // esi
  unsigned int left; // r12d
  __int64 v17; // rcx
  struct IObjectArray *v18; // rcx
  unsigned __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rcx
  InputHostManagerTelemetry *v22; // rcx
  unsigned __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rcx
  InputHostManagerTelemetry *v26; // rcx
  unsigned __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // rcx
  InputHostManagerTelemetry *v30; // rcx
  unsigned __int64 v31; // rdx
  int v32; // ecx
  __int64 v33; // rcx
  InputHostManagerTelemetry *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  DWORD DueTime; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+60h] [rbp-A0h]
  int v45; // [rsp+64h] [rbp-9Ch]
  int v46; // [rsp+68h] [rbp-98h]
  struct IObjectArray *v47; // [rsp+70h] [rbp-90h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp-88h] BYREF
  DWORD Parameter; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+84h] [rbp-7Ch]
  int v51; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+90h] [rbp-70h]
  CGITRegistrationList *v53; // [rsp+98h] [rbp-68h]
  RTL_SRWLOCK *v54; // [rsp+A0h] [rbp-60h]
  struct tagRECT rc; // [rsp+A8h] [rbp-58h] BYREF
  int v56; // [rsp+B8h] [rbp-48h] BYREF
  RECT rcSrc; // [rsp+BCh] [rbp-44h] BYREF
  RECT v58; // [rsp+CCh] [rbp-34h] BYREF
  RECT v59; // [rsp+DCh] [rbp-24h] BYREF
  LONG v60; // [rsp+ECh] [rbp-14h]
  struct tagRECT v61; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT v62; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT rcDst; // [rsp+110h] [rbp+10h] BYREF

  SRWLock = a1 + 32;
  AcquireSRWLockExclusive(a1 + 32);
  v6 = 0;
  v7 = a1 + 33;
  v54 = a1 + 33;
  for ( i = 0; ; ++i )
  {
    if ( i >= a1[34].Ptr )
    {
      v10 = -2147319765;
      goto LABEL_11;
    }
    if ( a2 == (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v7->Ptr + (_QWORD)i) + 24LL))(*((_QWORD *)v7->Ptr + (_QWORD)i)) )
      break;
  }
  if ( i >= a1[34].Ptr )
  {
    v10 = -2147316575;
  }
  else
  {
    _mm_lfence();
    v9 = *((_QWORD *)v7->Ptr + (_QWORD)i);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v6 = v9;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
  }
LABEL_11:
  v11 = a1 + 32;
  v40 = v10;
  ReleaseSRWLockExclusive(a1 + 32);
  if ( v10 < 0 )
    goto LABEL_73;
  DueTime = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
  Parameter = GetCurrentThreadId();
  v50 = 0;
  v51 = -2147467259;
  v52 = 0;
  CBaseRPCTimeout::Arm(&Parameter, DueTime);
  v43 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
  v42 = 0;
  v44 = CoreQueryWindowService(a2, &SID_SystemUIInputHostHandler, &GUID_c91fa253_e03a_45c3_8123_15e348a62f8d, &v43);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
  v41 = 0;
  v45 = CoreQueryWindowService(a2, &SID_InputPaneEventHandler, &GUID_87482e5d_0157_459a_bd7c_cb18085be80f, &v42);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v41);
  v46 = CoreQueryWindowService(
          a2,
          &SID_ApplicationFrameInputPaneEventHandler,
          &GUID_fb45dabf_22c2_43b2_b887_af34b3a857f1,
          &v41);
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
  IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA::IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA((IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA *)&v56);
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 48LL))(v6, &v56) < 0 )
    goto LABEL_64;
  v12 = DueTime;
  v13 = (CGITRegistrationList *)&a1[26];
  v53 = (CGITRegistrationList *)&a1[26];
  do
  {
    v14 = v56;
    rc.left = v60;
    rcDst = 0;
    v62 = 0;
    v61 = 0;
    if ( v56 == 1 )
    {
      CopyRect(&rcDst, &rcSrc);
      CopyRect(&v62, &v58);
      CopyRect(&v61, &v59);
    }
    v47 = 0;
    if ( (int)CGITRegistrationList::GetCallbackArray(v13, &v47) >= 0 )
    {
      DueTime = 0;
      if ( ((int (__fastcall *)(struct IObjectArray *, DWORD *))v47->lpVtbl->GetCount)(v47, &DueTime) >= 0 )
      {
        v15 = 0;
        if ( DueTime )
        {
          left = rc.left;
          do
          {
            *(_QWORD *)&rc.left = 0;
            if ( ((int (__fastcall *)(struct IObjectArray *, _QWORD, GUID *, struct tagRECT *))v47->lpVtbl->GetAt)(
                   v47,
                   v15,
                   &GUID_4fb9f2b9_bdd6_47b9_9ebe_703eacdc1c8e,
                   &rc) >= 0 )
            {
              if ( v14 == 1 )
              {
                (*(void (__fastcall **)(_QWORD, RTL_SRWLOCK *, struct tagRECT *, _QWORD, struct tagRECT *, struct tagRECT *))(**(_QWORD **)&rc.left + 24LL))(
                  *(_QWORD *)&rc.left,
                  a2,
                  &rcDst,
                  left,
                  &v62,
                  &v61);
              }
              else if ( v14 == 2 )
              {
                (*(void (__fastcall **)(_QWORD, RTL_SRWLOCK *, _QWORD))(**(_QWORD **)&rc.left + 32LL))(
                  *(_QWORD *)&rc.left,
                  a2,
                  left);
              }
            }
            v17 = *(_QWORD *)&rc.left;
            if ( *(_QWORD *)&rc.left )
            {
              *(_QWORD *)&rc.left = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            ++v15;
          }
          while ( v15 < DueTime );
        }
        v13 = v53;
      }
    }
    v18 = v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(struct IObjectArray *))v18->lpVtbl->Release)(v18);
    }
    if ( v56 == 1 )
    {
      CBaseRPCTimeout::Arm(&Parameter, v12);
      if ( v44 < 0 )
      {
        if ( v45 >= 0 )
        {
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
            McTemplateU0dpdddd_EventWriteTransfer(
              v28,
              (unsigned int)ImmersiveShell_InputHost_AppNotification_Start,
              1,
              (_DWORD)a2,
              rcSrc.left,
              rcSrc.top,
              rcSrc.right,
              rcSrc.bottom);
          if ( InputHostManagerTelemetry::IsEnabled(v28, v27) )
          {
            wil::details::static_lazy<InputHostManagerTelemetry>::get(
              v29,
              _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
            InputHostManagerTelemetry::InputPaneAppNotification_Showing_Start_(v30, (HWND)a2, &rcSrc);
          }
          if ( v46 < 0 )
          {
            rc = 0;
            SetRectEmpty(&rc);
            (*(void (__fastcall **)(__int64, RECT *, struct tagRECT *, struct tagRECT *, struct tagRECT *, unsigned int))(*(_QWORD *)v42 + 24LL))(
              v42,
              &rcSrc,
              &rc,
              &rc,
              &rc,
              a3);
          }
          else
          {
            (*(void (__fastcall **)(__int64, RTL_SRWLOCK *, RECT *, _QWORD))(*(_QWORD *)v41 + 32LL))(
              v41,
              a2,
              &rcSrc,
              a3);
          }
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
            McTemplateU0dpdddd_EventWriteTransfer(
              v32,
              (unsigned int)ImmersiveShell_InputHost_AppNotification_Stop,
              1,
              (_DWORD)a2,
              rcSrc.left,
              rcSrc.top,
              rcSrc.right,
              rcSrc.bottom);
          if ( InputHostManagerTelemetry::IsEnabled(v32, v31) )
          {
            wil::details::static_lazy<InputHostManagerTelemetry>::get(
              v33,
              _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
            InputHostManagerTelemetry::InputPaneAppNotification_Showing_Stop_(v34, (HWND)a2);
          }
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64, RECT *, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, &rcSrc, a3);
      }
    }
    else
    {
      if ( v56 != 2 )
        continue;
      CBaseRPCTimeout::Arm(&Parameter, v12);
      if ( v44 < 0 )
      {
        if ( v45 >= 0 )
        {
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
            McTemplateU0dpdddd_EventWriteTransfer(
              v20,
              (unsigned int)ImmersiveShell_InputHost_AppNotification_Start,
              2,
              (_DWORD)a2,
              0,
              0,
              0,
              0);
          if ( InputHostManagerTelemetry::IsEnabled(v20, v19) )
          {
            wil::details::static_lazy<InputHostManagerTelemetry>::get(
              v21,
              _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
            InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Start_(v22, (HWND)a2);
          }
          if ( v46 < 0 )
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 32LL))(v42, a3);
          else
            (*(void (__fastcall **)(__int64, RTL_SRWLOCK *, _QWORD))(*(_QWORD *)v41 + 40LL))(v41, a2, a3);
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
            McTemplateU0dpdddd_EventWriteTransfer(
              v24,
              (unsigned int)ImmersiveShell_InputHost_AppNotification_Stop,
              2,
              (_DWORD)a2,
              0,
              0,
              0,
              0);
          if ( InputHostManagerTelemetry::IsEnabled(v24, v23) )
          {
            wil::details::static_lazy<InputHostManagerTelemetry>::get(
              v25,
              _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
            InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Stop_(v26, (HWND)a2);
          }
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 32LL))(v43, a3);
      }
    }
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
  }
  while ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 48LL))(v6, &v56) >= 0 );
  v10 = v40;
  v7 = v54;
  v11 = SRWLock;
LABEL_64:
  AcquireSRWLockExclusive(v11);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6) )
  {
    SRWLock = a2;
    v10 = CTSimpleArray<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>>::RemoveEx<CPerWindowNotificationQueueFinder>(
            v7,
            &SRWLock);
  }
  ReleaseSRWLockExclusive(v11);
  v35 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
LABEL_73:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180082ac8  mov     [rsp-8+arg_18], rbx
0x180082acd  push    rbp
0x180082ace  push    rsi
0x180082acf  push    rdi
0x180082ad0  push    r12
0x180082ad2  push    r13
0x180082ad4  push    r14
0x180082ad6  push    r15
0x180082ad8  lea     rbp, [rsp-30h]
0x180082add  sub     rsp, 130h
0x180082ae4  mov     rax, cs:__security_cookie
0x180082aeb  xor     rax, rsp
0x180082aee  mov     [rbp+60h+var_40], rax
0x180082af2  lea     rax, [rcx+100h]
0x180082af9  mov     r15, rcx
0x180082afc  mov     rcx, rax; SRWLock
0x180082aff  mov     [rsp+160h+SRWLock], rax
0x180082b04  mov     r13d, r8d
0x180082b07  mov     rdi, rdx
0x180082b0a  call    cs:__imp_AcquireSRWLockExclusive
0x180082b11  nop     dword ptr [rax+rax+00h]
0x180082b16  xor     ebx, ebx
0x180082b18  lea     r12, [r15+108h]
0x180082b1f  mov     [rbp+60h+var_C0], r12
0x180082b23  xor     esi, esi
0x180082b25  cmp     rsi, [r12+8]
0x180082b2a  jnb     short loc_180082B8F
0x180082b2c  mov     rax, [r12]
0x180082b30  mov     rcx, [rax+rsi*8]
0x180082b34  mov     rax, [rcx]
0x180082b37  mov     rax, [rax+18h]
0x180082b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b40  cmp     rdi, rax
0x180082b43  jz      short loc_180082B4A
0x180082b45  inc     rsi
0x180082b48  jmp     short loc_180082B25
0x180082b4a  cmp     rsi, [r12+8]
0x180082b4f  jnb     short loc_180082B87
0x180082b51  lfence
0x180082b54  mov     rax, [r12]
0x180082b58  mov     rsi, [rax+rsi*8]
0x180082b5c  test    rsi, rsi
0x180082b5f  jz      short loc_180082B73
0x180082b61  mov     rax, [rsi]
0x180082b64  mov     rcx, rsi
0x180082b67  mov     rax, [rax+8]
0x180082b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b70  mov     rbx, rsi
0x180082b73  mov     rax, [rbx]
0x180082b76  mov     rcx, rbx
0x180082b79  mov     rax, [rax+20h]
0x180082b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b82  mov     r14d, eax
0x180082b85  jmp     short loc_180082B95
0x180082b87  mov     r14d, 80028CA1h
0x180082b8d  jmp     short loc_180082B95
0x180082b8f  mov     r14d, 8002802Bh
0x180082b95  lea     rsi, [r15+100h]
0x180082b9c  mov     [rsp+160h+var_11C], r14d
0x180082ba1  mov     rcx, rsi; SRWLock
0x180082ba4  call    cs:__imp_ReleaseSRWLockExclusive
0x180082bab  nop     dword ptr [rax+rax+00h]
0x180082bb0  test    r14d, r14d
0x180082bb3  js      loc_1800831AA
0x180082bb9  mov     rax, [rbx]
0x180082bbc  mov     rcx, rbx
0x180082bbf  mov     rax, [rax+40h]
0x180082bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bc8  mov     [rsp+160h+DueTime], eax
0x180082bcc  call    cs:__imp_GetCurrentThreadId
0x180082bd3  nop     dword ptr [rax+rax+00h]
0x180082bd8  mov     edx, [rsp+160h+DueTime]; DueTime
0x180082bdc  lea     rcx, [rbp+60h+Parameter]; Parameter
0x180082be0  mov     [rbp+60h+Parameter], eax
0x180082be3  mov     [rbp+60h+var_DC], 0
0x180082be7  mov     [rbp+60h+var_D8], 80004005h
0x180082bee  mov     [rbp+60h+var_D0], 0
0x180082bf6  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x180082bfb  lea     rcx, [rsp+160h+var_108]
0x180082c00  mov     [rsp+160h+var_108], 0
0x180082c09  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180082c0e  lea     r9, [rsp+160h+var_108]
0x180082c13  mov     rcx, rdi
0x180082c16  lea     r8, _GUID_c91fa253_e03a_45c3_8123_15e348a62f8d
0x180082c1d  lea     rdx, SID_SystemUIInputHostHandler
0x180082c24  call    cs:__imp_CoreQueryWindowService
0x180082c2b  nop     dword ptr [rax+rax+00h]
0x180082c30  lea     rcx, [rsp+160h+var_110]
0x180082c35  mov     [rsp+160h+var_110], 0
0x180082c3e  mov     [rsp+160h+var_100], eax
0x180082c42  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180082c47  lea     r9, [rsp+160h+var_110]
0x180082c4c  mov     rcx, rdi
0x180082c4f  lea     r8, _GUID_87482e5d_0157_459a_bd7c_cb18085be80f
0x180082c56  lea     rdx, SID_InputPaneEventHandler
0x180082c5d  call    cs:__imp_CoreQueryWindowService
0x180082c64  nop     dword ptr [rax+rax+00h]
0x180082c69  lea     rcx, [rsp+160h+var_118]
0x180082c6e  mov     [rsp+160h+var_118], 0
0x180082c77  mov     [rsp+160h+var_FC], eax
0x180082c7b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180082c80  lea     r9, [rsp+160h+var_118]
0x180082c85  mov     rcx, rdi
0x180082c88  lea     r8, _GUID_fb45dabf_22c2_43b2_b887_af34b3a857f1
0x180082c8f  lea     rdx, SID_ApplicationFrameInputPaneEventHandler
0x180082c96  call    cs:__imp_CoreQueryWindowService
0x180082c9d  nop     dword ptr [rax+rax+00h]
0x180082ca2  lea     rcx, [rbp+60h+Parameter]; this
0x180082ca6  mov     [rsp+160h+var_F8], eax
0x180082caa  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180082caf  lea     rcx, [rbp+60h+var_A8]; this
0x180082cb3  call    ??0IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA@@QEAA@XZ; IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA::IHM_PER_WINDOW_NOTIFICATION_QUEUE_DATA(void)
0x180082cb8  mov     rcx, [rbx]
0x180082cbb  lea     rdx, [rbp+60h+var_A8]
0x180082cbf  mov     rax, [rcx+30h]
0x180082cc3  mov     rcx, rbx
0x180082cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ccb  test    eax, eax
0x180082ccd  js      loc_180083107
0x180082cd3  mov     r14d, [rsp+160h+DueTime]
0x180082cd8  lea     rsi, [r15+0D0h]
0x180082cdf  mov     [rbp+60h+var_C8], rsi
0x180082ce3  mov     r15d, [rbp+60h+var_A8]
0x180082ce7  xorps   xmm0, xmm0
0x180082cea  mov     eax, [rbp+60h+var_74]
0x180082ced  xorps   xmm1, xmm1
0x180082cf0  mov     [rbp+60h+rc.left], eax
0x180082cf3  movups  xmmword ptr [rbp+60h+rcDst.left], xmm0
0x180082cf7  movups  xmmword ptr [rbp+60h+var_60.left], xmm1
0x180082cfb  movups  xmmword ptr [rbp+60h+var_70.left], xmm0
0x180082cff  cmp     r15d, 1
0x180082d03  jnz     short loc_180082D41
0x180082d05  lea     rdx, [rbp+60h+rcSrc]; lprcSrc
0x180082d09  lea     rcx, [rbp+60h+rcDst]; lprcDst
0x180082d0d  call    cs:__imp_CopyRect
0x180082d14  nop     dword ptr [rax+rax+00h]
0x180082d19  lea     rdx, [rbp+60h+var_94]; lprcSrc
0x180082d1d  lea     rcx, [rbp+60h+var_60]; lprcDst
0x180082d21  call    cs:__imp_CopyRect
0x180082d28  nop     dword ptr [rax+rax+00h]
0x180082d2d  lea     rdx, [rbp+60h+var_84]; lprcSrc
0x180082d31  lea     rcx, [rbp+60h+var_70]; lprcDst
0x180082d35  call    cs:__imp_CopyRect
0x180082d3c  nop     dword ptr [rax+rax+00h]
0x180082d41  xor     r12d, r12d
0x180082d44  lea     rdx, [rsp+160h+var_F0]; struct IObjectArray **
0x180082d49  mov     rcx, rsi; this
0x180082d4c  mov     [rsp+160h+var_F0], r12
0x180082d51  call    ?GetCallbackArray@CGITRegistrationList@@QEAAJPEAPEAUIObjectArray@@@Z; CGITRegistrationList::GetCallbackArray(IObjectArray * *)
0x180082d56  test    eax, eax
0x180082d58  js      loc_180082E3B
0x180082d5e  mov     rcx, [rsp+160h+var_F0]
0x180082d63  lea     rdx, [rsp+160h+DueTime]
0x180082d68  mov     [rsp+160h+DueTime], r12d
0x180082d6d  mov     rax, [rcx]
0x180082d70  mov     rax, [rax+18h]
0x180082d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d79  test    eax, eax
0x180082d7b  js      loc_180082E3B
0x180082d81  mov     esi, r12d
0x180082d84  cmp     [rsp+160h+DueTime], r12d
0x180082d89  jbe     loc_180082E37
0x180082d8f  mov     r12d, [rbp+60h+rc.left]
0x180082d93  mov     rcx, [rsp+160h+var_F0]
0x180082d98  lea     r9, [rbp+60h+rc]
0x180082d9c  mov     qword ptr [rbp+60h+rc.left], 0
0x180082da4  lea     r8, _GUID_4fb9f2b9_bdd6_47b9_9ebe_703eacdc1c8e
0x180082dab  mov     edx, esi
0x180082dad  mov     rax, [rcx]
0x180082db0  mov     rax, [rax+20h]
0x180082db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082db9  test    eax, eax
0x180082dbb  js      short loc_180082E0E
0x180082dbd  mov     ecx, r15d
0x180082dc0  sub     ecx, 1
0x180082dc3  jz      short loc_180082DE2
0x180082dc5  cmp     ecx, 1
0x180082dc8  jnz     short loc_180082E0E
0x180082dca  mov     rcx, qword ptr [rbp+60h+rc.left]
0x180082dce  mov     r8d, r12d
0x180082dd1  mov     rdx, rdi
0x180082dd4  mov     rax, [rcx]
0x180082dd7  mov     rax, [rax+20h]
0x180082ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082de0  jmp     short loc_180082E0E
0x180082de2  mov     rcx, qword ptr [rbp+60h+rc.left]
0x180082de6  lea     rdx, [rbp+60h+var_70]
0x180082dea  mov     [rsp+160h+var_138], rdx
0x180082def  lea     r8, [rbp+60h+rcDst]
0x180082df3  lea     rdx, [rbp+60h+var_60]
0x180082df7  mov     r9d, r12d
0x180082dfa  mov     [rsp+160h+var_140], rdx
0x180082dff  mov     rdx, rdi
0x180082e02  mov     rax, [rcx]
0x180082e05  mov     rax, [rax+18h]
0x180082e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e0e  mov     rcx, qword ptr [rbp+60h+rc.left]
0x180082e12  test    rcx, rcx
0x180082e15  jz      short loc_180082E2B
0x180082e17  mov     qword ptr [rbp+60h+rc.left], 0
0x180082e1f  mov     rax, [rcx]
0x180082e22  mov     rax, [rax+10h]
0x180082e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e2b  inc     esi
0x180082e2d  cmp     esi, [rsp+160h+DueTime]
0x180082e31  jb      loc_180082D93
0x180082e37  mov     rsi, [rbp+60h+var_C8]
0x180082e3b  mov     rcx, [rsp+160h+var_F0]
0x180082e40  xor     r15d, r15d
0x180082e43  test    rcx, rcx
0x180082e46  jz      short loc_180082E59
0x180082e48  mov     [rsp+160h+var_F0], r15
0x180082e4d  mov     rax, [rcx]
0x180082e50  mov     rax, [rax+10h]
0x180082e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e59  mov     ecx, [rbp+60h+var_A8]
0x180082e5c  sub     ecx, 1
0x180082e5f  jz      loc_180082F80
0x180082e65  cmp     ecx, 1
0x180082e68  jnz     loc_1800830DC
0x180082e6e  mov     edx, r14d; DueTime
0x180082e71  lea     rcx, [rbp+60h+Parameter]; Parameter
0x180082e75  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x180082e7a  cmp     [rsp+160h+var_100], r15d
0x180082e7f  jl      short loc_180082E9A
0x180082e81  mov     rcx, [rsp+160h+var_108]
0x180082e86  mov     edx, r13d
0x180082e89  mov     rax, [rcx]
0x180082e8c  mov     rax, [rax+20h]
0x180082e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e95  jmp     loc_1800830D3
0x180082e9a  cmp     [rsp+160h+var_FC], r15d
0x180082e9f  jl      loc_1800830D3
0x180082ea5  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180082eac  jz      short loc_180082ED7
0x180082eae  mov     [rsp+160h+var_128], r15d
0x180082eb3  lea     rdx, ImmersiveShell_InputHost_AppNotification_Start
0x180082eba  mov     [rsp+160h+var_130], r15d
0x180082ebf  mov     r9, rdi
0x180082ec2  mov     dword ptr [rsp+160h+var_138], r15d
0x180082ec7  mov     r8d, 2
0x180082ecd  mov     dword ptr [rsp+160h+var_140], r15d
0x180082ed2  call    McTemplateU0dpdddd_EventWriteTransfer
0x180082ed7  call    ?IsEnabled@InputHostManagerTelemetry@@SA_NE_K@Z; InputHostManagerTelemetry::IsEnabled(uchar,unsigned __int64)
0x180082edc  test    al, al
0x180082ede  jz      short loc_180082EF4
0x180082ee0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d53bed665c4d83ca2776d67ec0cbd1ab_@@CA@XZ; _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_(void)
0x180082ee7  call    ?get@?$static_lazy@VInputHostManagerTelemetry@@@details@wil@@QEAAPEAVInputHostManagerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<InputHostManagerTelemetry>::get(void (*)(void))
0x180082eec  mov     rdx, rdi; HWND
0x180082eef  call    ?InputPaneAppNotification_Hiding_Start_@InputHostManagerTelemetry@@QEBAXPEAUHWND__@@@Z; InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Start_(HWND__ *)
0x180082ef4  cmp     [rsp+160h+var_F8], r15d
0x180082ef9  jl      short loc_180082F14
0x180082efb  mov     rcx, [rsp+160h+var_118]
0x180082f00  mov     r8d, r13d
0x180082f03  mov     rdx, rdi
0x180082f06  mov     rax, [rcx]
0x180082f09  mov     rax, [rax+28h]
0x180082f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f12  jmp     short loc_180082F28
0x180082f14  mov     rcx, [rsp+160h+var_110]
0x180082f19  mov     edx, r13d
0x180082f1c  mov     rax, [rcx]
0x180082f1f  mov     rax, [rax+20h]
0x180082f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f28  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180082f2f  jz      short loc_180082F5A
0x180082f31  mov     [rsp+160h+var_128], r15d
0x180082f36  lea     rdx, ImmersiveShell_InputHost_AppNotification_Stop
0x180082f3d  mov     [rsp+160h+var_130], r15d
0x180082f42  mov     r9, rdi
0x180082f45  mov     dword ptr [rsp+160h+var_138], r15d
0x180082f4a  mov     r8d, 2
0x180082f50  mov     dword ptr [rsp+160h+var_140], r15d
0x180082f55  call    McTemplateU0dpdddd_EventWriteTransfer
0x180082f5a  call    ?IsEnabled@InputHostManagerTelemetry@@SA_NE_K@Z; InputHostManagerTelemetry::IsEnabled(uchar,unsigned __int64)
0x180082f5f  test    al, al
0x180082f61  jz      loc_1800830D3
0x180082f67  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d53bed665c4d83ca2776d67ec0cbd1ab_@@CA@XZ; _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_(void)
0x180082f6e  call    ?get@?$static_lazy@VInputHostManagerTelemetry@@@details@wil@@QEAAPEAVInputHostManagerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<InputHostManagerTelemetry>::get(void (*)(void))
0x180082f73  mov     rdx, rdi; HWND
0x180082f76  call    ?InputPaneAppNotification_Hiding_Stop_@InputHostManagerTelemetry@@QEBAXPEAUHWND__@@@Z; InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Stop_(HWND__ *)
0x180082f7b  jmp     loc_1800830D3
0x180082f80  mov     edx, r14d; DueTime
0x180082f83  lea     rcx, [rbp+60h+Parameter]; Parameter
0x180082f87  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x180082f8c  cmp     [rsp+160h+var_100], r15d
0x180082f91  jl      short loc_180082FB0
0x180082f93  mov     rcx, [rsp+160h+var_108]
0x180082f98  lea     rdx, [rbp+60h+rcSrc]
0x180082f9c  mov     r8d, r13d
0x180082f9f  mov     rax, [rcx]
0x180082fa2  mov     rax, [rax+18h]
0x180082fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082fab  jmp     loc_1800830D3
0x180082fb0  cmp     [rsp+160h+var_FC], r15d
0x180082fb5  jl      loc_1800830D3
0x180082fbb  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180082fc2  jz      short loc_180082FF5
0x180082fc4  mov     eax, [rbp+60h+rcSrc.bottom]
0x180082fc7  lea     rdx, ImmersiveShell_InputHost_AppNotification_Start
  ... truncated ...
```
