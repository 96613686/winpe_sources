# CWebDialogAction::_SyncBackstopVisualToLogonVisual(void)

- ea: `0x18005c5f4`
- end: `0x18005cac0`
- name: `?_SyncBackstopVisualToLogonVisual@CWebDialogAction@@AEAAJXZ`
- size: `1228`
- prototype: `__int64 __fastcall(CWebDialogAction *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18006b870`
- `0x18008d0c0`

## callees

- `0x180017dec`
- `0x18001db70`
- `0x18001f3a0`
- `0x180026e70`
- `0x18002f554`
- `0x18002fe2c`
- `0x18005b3e4`
- `0x18005c110`
- `0x18005c5f4`
- `0x18005cac8`
- `0x18005d488`
- `0x180067c80`
- `0x180067cb4`
- `0x18006c000`
- `0x18008b9bc`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c7ae`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ca4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ca8e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005c7ae`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ca4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005ca8e`
- `KERNEL32!CloseHandle` at `0x18005c94a`
- `KERNEL32!CloseHandle` at `0x18005c94a`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18005c8cf`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18005c8cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18005c6e4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18005c6e4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18005c69a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18005c6ac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18005c69a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18005c6ac`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18005c85a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18005c86a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18005c85a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18005c86a`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18005c87c`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18005c87c`

## pseudocode

```c
__int64 __fastcall CWebDialogAction::_SyncBackstopVisualToLogonVisual(CWebDialogAction *this)
{
  HWND WindowW; // r14
  HWND v3; // rax
  HWND v4; // r15
  int v5; // eax
  unsigned int v6; // ebx
  struct IDCompositionDesktopDevicePartner *v7; // rdi
  __int64 (__fastcall *v8)(struct IDCompositionDesktopDevicePartner *, _QWORD, GUID *, __int64); // rbx
  __int64 v9; // rax
  int v10; // eax
  struct IDCompositionDesktopDevicePartner *v11; // rdi
  __int64 (__fastcall *v12)(struct IDCompositionDesktopDevicePartner *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  struct IDCompositionDesktopDevicePartner *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  HANDLE v22; // rax
  RTL_SRWLOCK *v23; // rcx
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  struct IDCompositionDesktopDevicePartner *v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h]
  PSRWLOCK v33; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID Buf1; // [rsp+78h] [rbp-88h] BYREF
  struct tagRECT rcDst; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v36[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v37[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v37,
    "CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity");
  v37[0] = &LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v37,
      &Buf1);
  LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::StartActivity((LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity *)v37);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 272);
  WindowW = FindWindowW(L"LogonUI Logon Window", 0);
  v3 = FindWindowW(L"LogonUI worker window", 0);
  v4 = v3;
  if ( WindowW && v3 )
  {
    CWebDialogAction::_CleanupThumbnail(this);
    CWebDialogAction::_CleanupSharedVisual(this);
    PostMessageW(WindowW, 0x7Eu, 0, 0);
    v27 = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v27);
    v5 = CWebDialogAction::_EnsureDevice(this, &v27);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v5,
        v25);
      goto LABEL_10;
    }
    v7 = v27;
    v29 = 0;
    v8 = *(__int64 (__fastcall **)(struct IDCompositionDesktopDevicePartner *, _QWORD, GUID *, __int64))(*(_QWORD *)v27 + 232LL);
    v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(&v29);
    v10 = v8(v7, *((_QWORD *)this + 36), &GUID_eacdd04c_117e_4e17_88f4_d1b12b0e3d89, v9);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v10,
        v25);
LABEL_9:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v29);
LABEL_10:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v27);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_40;
    }
    v11 = v27;
    v28 = 0;
    v12 = *(__int64 (__fastcall **)(struct IDCompositionDesktopDevicePartner *, __int64 *))(*(_QWORD *)v27 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v28);
    v13 = v12(v11, &v28);
    v6 = v13;
    if ( v13 < 0 )
    {
      v14 = 466;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v13,
        v25);
LABEL_15:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v28);
      goto LABEL_9;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, v28);
    v6 = v13;
    if ( v13 < 0 )
    {
      v14 = 467;
      goto LABEL_14;
    }
    rcDst = 0;
    rcDst.left = 25;
    memset(v36, 0, 29);
    *(_QWORD *)&Buf1.Data1 = 0;
    *(_DWORD *)Buf1.Data4 = GetSystemMetrics(0);
    *(_DWORD *)&Buf1.Data4[4] = GetSystemMetrics(1);
    CopyRect((LPRECT)&rcDst.top, (const RECT *)&Buf1);
    *(_DWORD *)((char *)&v36[1] + 5) = 1;
    *(_DWORD *)((char *)&v36[1] + 9) = 1;
    v30 = 0;
    hObject = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v30);
    v26 = (int)v27;
    v15 = DwmpCreateSharedThumbnailVisual(v4, WindowW, 0, &rcDst);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v15,
        v26);
LABEL_20:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v30);
      goto LABEL_15;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v28 + 128LL))(v28, v30, 1, 0);
    v6 = v16;
    if ( v16 < 0 )
    {
      v17 = 485;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\webdialogaction.cpp",
        (const char *)(unsigned int)v16,
        v26);
      CloseHandle(hObject);
      goto LABEL_20;
    }
    v16 = (*(__int64 (__fastcall **)(struct IDCompositionDesktopDevicePartner *))(*(_QWORD *)v27 + 24LL))(v27);
    v6 = v16;
    if ( v16 < 0 )
    {
      v17 = 487;
      goto LABEL_23;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v33, (char *)this + 296);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 304);
    v18 = v27;
    if ( v27 )
    {
      (*(void (__fastcall **)(struct IDCompositionDesktopDevicePartner *))(*(_QWORD *)v27 + 8LL))(v27);
      v18 = v27;
    }
    *((_QWORD *)this + 38) = v18;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 312);
    v19 = v29;
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      v19 = v29;
    }
    *((_QWORD *)this + 39) = v19;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 320);
    v20 = v28;
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      v20 = v28;
    }
    *((_QWORD *)this + 40) = v20;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 328);
    v21 = v30;
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
      v21 = v30;
    }
    v22 = hObject;
    *((_QWORD *)this + 41) = v21;
    v23 = v33;
    *((_QWORD *)this + 42) = v22;
    if ( v23 )
      ReleaseSRWLockExclusive(v23);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v27);
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v37, 0);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v6 = 0;
LABEL_40:
  LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::~CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity((LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity *)v37);
  return v6;
}

```

## disassembly

```asm
0x18005c5f4  push    rbp
0x18005c5f6  push    rbx
0x18005c5f7  push    rsi
0x18005c5f8  push    rdi
0x18005c5f9  push    r14
0x18005c5fb  push    r15
0x18005c5fd  lea     rbp, [rsp-128h]
0x18005c605  sub     rsp, 228h
0x18005c60c  mov     rax, cs:__security_cookie
0x18005c613  xor     rax, rsp
0x18005c616  mov     [rbp+150h+var_40], rax
0x18005c61d  mov     rsi, rcx
0x18005c620  lea     rdx, aCwebdialogacti_6; "CWebDialogAction__SyncBackstopVisualToL"...
0x18005c627  lea     rcx, [rbp+150h+var_190]
0x18005c62b  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005c630  lea     rax, ??_7CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::`vftable'
0x18005c637  lea     rcx, [rsp+250h+Buf1]; retstr
0x18005c63c  mov     [rbp+150h+var_190], rax
0x18005c640  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18005c645  mov     r8d, 10h; Size
0x18005c64b  lea     rdx, GUID_NULL; Buf2
0x18005c652  lea     rcx, [rsp+250h+Buf1]; Buf1
0x18005c657  movups  xmm0, xmmword ptr [rax]
0x18005c65a  movdqu  [rsp+250h+Buf1], xmm0
0x18005c660  call    memcmp_0
0x18005c665  test    eax, eax
0x18005c667  jz      short loc_18005C677
0x18005c669  lea     rdx, [rsp+250h+Buf1]
0x18005c66e  lea     rcx, [rbp+150h+var_190]
0x18005c672  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18005c677  lea     rcx, [rbp+150h+var_190]; this
0x18005c67b  call    ?StartActivity@CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::StartActivity(void)
0x18005c680  lea     rdx, [rsi+110h]
0x18005c687  lea     rcx, [rsp+250h+SRWLock]
0x18005c68c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005c691  xor     edx, edx; lpWindowName
0x18005c693  lea     rcx, ClassName; "LogonUI Logon Window"
0x18005c69a  call    cs:__imp_FindWindowW
0x18005c6a0  xor     edx, edx; lpWindowName
0x18005c6a2  lea     rcx, aLogonuiWorkerW; "LogonUI worker window"
0x18005c6a9  mov     r14, rax
0x18005c6ac  call    cs:__imp_FindWindowW
0x18005c6b2  mov     r15, rax
0x18005c6b5  test    r14, r14
0x18005c6b8  jz      loc_18005CA79
0x18005c6be  test    rax, rax
0x18005c6c1  jz      loc_18005CA79
0x18005c6c7  mov     rcx, rsi; this
0x18005c6ca  call    ?_CleanupThumbnail@CWebDialogAction@@AEAAXXZ; CWebDialogAction::_CleanupThumbnail(void)
0x18005c6cf  mov     rcx, rsi; this
0x18005c6d2  call    ?_CleanupSharedVisual@CWebDialogAction@@AEAAXXZ; CWebDialogAction::_CleanupSharedVisual(void)
0x18005c6d7  xor     r9d, r9d; lParam
0x18005c6da  xor     r8d, r8d; wParam
0x18005c6dd  mov     rcx, r14; hWnd
0x18005c6e0  lea     edx, [r9+7Eh]; Msg
0x18005c6e4  call    cs:__imp_PostMessageW
0x18005c6ea  lea     rcx, [rsp+250h+var_210]
0x18005c6ef  mov     [rsp+250h+var_210], 0
0x18005c6f8  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c6fd  lea     rdx, [rsp+250h+var_210]; struct IDCompositionDesktopDevicePartner **
0x18005c702  mov     rcx, rsi; this
0x18005c705  call    ?_EnsureDevice@CWebDialogAction@@AEAAJPEAPEAUIDCompositionDesktopDevicePartner@@@Z; CWebDialogAction::_EnsureDevice(IDCompositionDesktopDevicePartner * *)
0x18005c70a  mov     ebx, eax
0x18005c70c  test    eax, eax
0x18005c70e  jns     short loc_18005C72D
0x18005c710  mov     rcx, [rbp+158h]; this
0x18005c717  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c71e  mov     r9d, eax; char *
0x18005c721  mov     edx, 1CCh; void *
0x18005c726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c72b  jmp     short loc_18005C796
0x18005c72d  mov     rdi, [rsp+250h+var_210]
0x18005c732  lea     rcx, [rsp+250h+var_200]
0x18005c737  mov     [rsp+250h+var_200], 0
0x18005c740  mov     rax, [rdi]
0x18005c743  mov     rbx, [rax+0E8h]
0x18005c74a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>)
0x18005c74f  mov     rdx, [rsi+120h]
0x18005c756  lea     r8, _GUID_eacdd04c_117e_4e17_88f4_d1b12b0e3d89
0x18005c75d  mov     r9, rax
0x18005c760  mov     rcx, rdi
0x18005c763  mov     rax, rbx
0x18005c766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c76b  mov     ebx, eax
0x18005c76d  test    eax, eax
0x18005c76f  jns     short loc_18005C7B9
0x18005c771  mov     rcx, [rbp+158h]; this
0x18005c778  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c77f  mov     r9d, eax; char *
0x18005c782  mov     edx, 1CFh; void *
0x18005c787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c78c  lea     rcx, [rsp+250h+var_200]
0x18005c791  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c796  lea     rcx, [rsp+250h+var_210]
0x18005c79b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c7a0  mov     rcx, [rsp+250h+SRWLock]; SRWLock
0x18005c7a5  test    rcx, rcx
0x18005c7a8  jz      loc_18005CA96
0x18005c7ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c7b4  jmp     loc_18005CA96
0x18005c7b9  mov     rdi, [rsp+250h+var_210]
0x18005c7be  lea     rcx, [rsp+250h+var_208]
0x18005c7c3  mov     [rsp+250h+var_208], 0
0x18005c7cc  mov     rax, [rdi]
0x18005c7cf  mov     rbx, [rax+30h]
0x18005c7d3  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c7d8  lea     rdx, [rsp+250h+var_208]
0x18005c7dd  mov     rcx, rdi
0x18005c7e0  mov     rax, rbx
0x18005c7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7e8  mov     ebx, eax
0x18005c7ea  test    eax, eax
0x18005c7ec  jns     short loc_18005C818
0x18005c7ee  mov     edx, 1D2h; void *
0x18005c7f3  mov     rcx, [rbp+158h]; this
0x18005c7fa  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c801  mov     r9d, eax; char *
0x18005c804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c809  lea     rcx, [rsp+250h+var_208]
0x18005c80e  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c813  jmp     loc_18005C78C
0x18005c818  mov     rcx, [rsp+250h+var_200]
0x18005c81d  mov     rdx, [rsp+250h+var_208]
0x18005c822  mov     rax, [rcx]
0x18005c825  mov     rax, [rax+18h]
0x18005c829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c82e  mov     ebx, eax
0x18005c830  test    eax, eax
0x18005c832  jns     short loc_18005C83B
0x18005c834  mov     edx, 1D3h
0x18005c839  jmp     short loc_18005C7F3
0x18005c83b  xorps   xmm0, xmm0
0x18005c83e  xor     eax, eax
0x18005c840  movups  xmmword ptr [rbp+150h+rcDst.left], xmm0
0x18005c844  xor     ecx, ecx; nIndex
0x18005c846  mov     [rbp+150h+rcDst.left], 19h
0x18005c84d  movups  [rbp+150h+var_1B8], xmm0
0x18005c851  mov     qword ptr [rsp+250h+Buf1], rax
0x18005c856  movups  [rbp+150h+var_1B8+0Dh], xmm0
0x18005c85a  call    cs:__imp_GetSystemMetrics
0x18005c860  mov     edi, 1
0x18005c865  mov     dword ptr [rbp+150h+Buf1+8], eax
0x18005c868  mov     ecx, edi; nIndex
0x18005c86a  call    cs:__imp_GetSystemMetrics
0x18005c870  lea     rdx, [rsp+250h+Buf1]; lprcSrc
0x18005c875  mov     dword ptr [rbp+150h+Buf1+0Ch], eax
0x18005c878  lea     rcx, [rbp+150h+rcDst.top]; lprcDst
0x18005c87c  call    cs:__imp_CopyRect
0x18005c882  lea     rcx, [rsp+250h+var_1F8]
0x18005c887  mov     [rbp+150h+var_1A3], edi
0x18005c88a  mov     [rbp+150h+var_19F], edi
0x18005c88d  mov     [rsp+250h+var_1F8], 0
0x18005c896  mov     [rsp+250h+hObject], 0
0x18005c89f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c8a4  mov     rax, [rsp+250h+var_210]
0x18005c8a9  lea     rcx, [rsp+250h+hObject]
0x18005c8ae  mov     [rsp+250h+var_220], rcx
0x18005c8b3  lea     r9, [rbp+150h+rcDst]
0x18005c8b7  lea     rcx, [rsp+250h+var_1F8]
0x18005c8bc  xor     r8d, r8d
0x18005c8bf  mov     [rsp+250h+var_228], rcx
0x18005c8c4  mov     rdx, r14
0x18005c8c7  mov     rcx, r15
0x18005c8ca  mov     qword ptr [rsp+250h+var_230], rax; int
0x18005c8cf  call    cs:__imp_DwmpCreateSharedThumbnailVisual
0x18005c8d5  mov     ebx, eax
0x18005c8d7  test    eax, eax
0x18005c8d9  jns     short loc_18005C905
0x18005c8db  mov     rcx, [rbp+158h]; this
0x18005c8e2  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c8e9  mov     r9d, eax; char *
0x18005c8ec  mov     edx, 1DFh; void *
0x18005c8f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c8f6  lea     rcx, [rsp+250h+var_1F8]
0x18005c8fb  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c900  jmp     loc_18005C809
0x18005c905  mov     rcx, [rsp+250h+var_208]
0x18005c90a  xor     r9d, r9d
0x18005c90d  mov     rdx, [rsp+250h+var_1F8]
0x18005c912  mov     r8d, edi
0x18005c915  mov     rax, [rcx]
0x18005c918  mov     rax, [rax+80h]
0x18005c91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c924  mov     ebx, eax
0x18005c926  test    eax, eax
0x18005c928  jns     short loc_18005C952
0x18005c92a  mov     edx, 1E5h; void *
0x18005c92f  mov     rcx, [rbp+158h]; this
0x18005c936  lea     r8, aPcshellShellAu_11; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005c93d  mov     r9d, eax; char *
0x18005c940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c945  mov     rcx, [rsp+250h+hObject]; hObject
0x18005c94a  call    cs:__imp_CloseHandle
0x18005c950  jmp     short loc_18005C8F6
0x18005c952  mov     rcx, [rsp+250h+var_210]
0x18005c957  mov     rax, [rcx]
0x18005c95a  mov     rax, [rax+18h]
0x18005c95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c963  mov     ebx, eax
0x18005c965  test    eax, eax
0x18005c967  jns     short loc_18005C970
0x18005c969  mov     edx, 1E7h
0x18005c96e  jmp     short loc_18005C92F
0x18005c970  lea     rdx, [rsi+128h]
0x18005c977  lea     rcx, [rsp+250h+var_1E0]
0x18005c97c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005c981  lea     rbx, [rsi+130h]
0x18005c988  mov     rcx, rbx
0x18005c98b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c990  mov     rcx, [rsp+250h+var_210]
0x18005c995  test    rcx, rcx
0x18005c998  jz      short loc_18005C9AB
0x18005c99a  mov     rax, [rcx]
0x18005c99d  mov     rax, [rax+8]
0x18005c9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9a6  mov     rcx, [rsp+250h+var_210]
0x18005c9ab  mov     [rbx], rcx
0x18005c9ae  lea     rbx, [rsi+138h]
0x18005c9b5  mov     rcx, rbx
0x18005c9b8  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c9bd  mov     rcx, [rsp+250h+var_200]
0x18005c9c2  test    rcx, rcx
0x18005c9c5  jz      short loc_18005C9D8
0x18005c9c7  mov     rax, [rcx]
0x18005c9ca  mov     rax, [rax+8]
0x18005c9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9d3  mov     rcx, [rsp+250h+var_200]
0x18005c9d8  mov     [rbx], rcx
0x18005c9db  lea     rbx, [rsi+140h]
0x18005c9e2  mov     rcx, rbx
0x18005c9e5  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005c9ea  mov     rcx, [rsp+250h+var_208]
0x18005c9ef  test    rcx, rcx
0x18005c9f2  jz      short loc_18005CA05
0x18005c9f4  mov     rax, [rcx]
0x18005c9f7  mov     rax, [rax+8]
0x18005c9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca00  mov     rcx, [rsp+250h+var_208]
0x18005ca05  mov     [rbx], rcx
0x18005ca08  lea     rbx, [rsi+148h]
0x18005ca0f  mov     rcx, rbx
0x18005ca12  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ca17  mov     rcx, [rsp+250h+var_1F8]
0x18005ca1c  test    rcx, rcx
0x18005ca1f  jz      short loc_18005CA32
0x18005ca21  mov     rax, [rcx]
0x18005ca24  mov     rax, [rax+8]
0x18005ca28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca2d  mov     rcx, [rsp+250h+var_1F8]
0x18005ca32  mov     rax, [rsp+250h+hObject]
0x18005ca37  mov     [rbx], rcx
0x18005ca3a  mov     rcx, [rsp+250h+var_1E0]; SRWLock
0x18005ca3f  mov     [rsi+150h], rax
0x18005ca46  test    rcx, rcx
0x18005ca49  jz      short loc_18005CA51
0x18005ca4b  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ca51  lea     rcx, [rsp+250h+var_1F8]
0x18005ca56  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ca5b  lea     rcx, [rsp+250h+var_208]
0x18005ca60  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ca65  lea     rcx, [rsp+250h+var_200]
0x18005ca6a  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ca6f  lea     rcx, [rsp+250h+var_210]
0x18005ca74  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18005ca79  xor     edx, edx
0x18005ca7b  lea     rcx, [rbp+150h+var_190]
0x18005ca7f  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005ca84  mov     rcx, [rsp+250h+SRWLock]; SRWLock
0x18005ca89  test    rcx, rcx
0x18005ca8c  jz      short loc_18005CA94
0x18005ca8e  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ca94  xor     ebx, ebx
0x18005ca96  lea     rcx, [rbp+150h+var_190]; this
0x18005ca9a  call    ??1CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity::~CWebDialogAction__SyncBackstopVisualToLogonVisual_Activity(void)
0x18005ca9f  mov     eax, ebx
0x18005caa1  mov     rcx, [rbp+150h+var_40]
0x18005caa8  xor     rcx, rsp; StackCookie
0x18005caab  call    __security_check_cookie
0x18005cab0  add     rsp, 228h
0x18005cab7  pop     r15
0x18005cab9  pop     r14
0x18005cabb  pop     rdi
0x18005cabc  pop     rsi
0x18005cabd  pop     rbx
0x18005cabe  pop     rbp
0x18005cabf  retn
```
