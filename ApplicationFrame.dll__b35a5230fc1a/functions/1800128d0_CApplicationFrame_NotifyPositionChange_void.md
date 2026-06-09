# CApplicationFrame::_NotifyPositionChange(void)

- ea: `0x1800128d0`
- end: `0x180013193`
- name: `?_NotifyPositionChange@CApplicationFrame@@AEAAXXZ`
- size: `2243`
- prototype: `void __fastcall(CApplicationFrame *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013430`

## callees

- `0x180004c98`
- `0x180011ef0`
- `0x180011f94`
- `0x180012010`
- `0x1800128d0`
- `0x1800131a0`
- `0x180013350`
- `0x1800145f0`
- `0x18001511c`
- `0x180024184`
- `0x1800396a0`
- `0x18003ed08`
- `0x18003f804`
- `0x18003fbc0`
- `0x180040270`
- `0x1800422b8`
- `0x180043c30`
- `0x180046b0c`
- `0x180054940`
- `0x18005c438`
- `0x18005c990`
- `0x18005e480`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012983`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012983`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012943`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012dde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012943`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012dde`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012e9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012eaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012e9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001296f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001296f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013188`
- `SHCORE!SHTaskPoolQueueTask` at `0x180012d97`
- `SHCORE!SHTaskPoolQueueTask` at `0x180012d97`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180012e0b`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180012e0b`
- `ext-ms-win-ntuser-private-l1-3-2!__imp_GetResizeDCompositionSynchronizationObject` at `0x18001290c`
- `ext-ms-win-ntuser-private-l1-3-2!__imp_GetResizeDCompositionSynchronizationObject` at `0x18001290c`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180012eb9`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180012eb9`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800129e6`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180012b97`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x1800129e6`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180012b97`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180012923`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180012923`

## string_xrefs

- `0x1800130b6`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`
- `0x1800130ef`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CApplicationFrame::_NotifyPositionChange(CApplicationFrame *this)
{
  int v2; // edi
  char v3; // r14
  RTL_SRWLOCK *v4; // rbx
  int v5; // edi
  __int64 v6; // rcx
  HANDLE v7; // r15
  const char *v8; // r9
  struct _RTL_CRITICAL_SECTION *v9; // r14
  __int64 v10; // r13
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, const WCHAR **); // rbx
  int v13; // ebx
  const WCHAR *v14; // rcx
  int v15; // eax
  int v16; // eax
  HANDLE v17; // r12
  int v18; // eax
  struct _RTL_CRITICAL_SECTION *v19; // r14
  __int64 v20; // rdx
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  LONG v22; // ebx
  struct _RTL_CRITICAL_SECTION *v23; // r15
  int v24; // eax
  struct _RTL_CRITICAL_SECTION *v25; // rbx
  struct _RTL_CRITICAL_SECTION *v26; // rdi
  LONG v27; // r15d
  HANDLE OwningThread; // rcx
  __int64 v29; // rax
  unsigned int v30; // edi
  __int64 v31; // r14
  unsigned int v32; // r15d
  _QWORD *v33; // rax
  _QWORD *v34; // rbx
  int v35; // edi
  __int64 v36; // rdi
  __int64 v37; // r12
  char v38; // r14
  char v39; // si
  char *v40; // rcx
  const struct _GUID *v41; // rdx
  const WCHAR *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int PresentedWindowRects; // eax
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  int v50; // [rsp+20h] [rbp-E0h]
  char v51[8]; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v52; // [rsp+58h] [rbp-A8h] BYREF
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp-88h] BYREF
  struct tagRECT v57; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT v58; // [rsp+98h] [rbp-68h] BYREF
  struct tagRECT v59; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v60[96]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  hObject = 0;
  GetResizeDCompositionSynchronizationObject(*((_QWORD *)this + 3), &hObject);
  if ( (*((_BYTE *)this + 272) & 1) != 0 )
  {
    if ( IsZoomed(*((HWND *)this + 3)) )
      v2 = 3;
    else
      v2 = 2 - IsIconic(*((HWND *)this + 3));
    v3 = 0;
    v4 = (RTL_SRWLOCK *)((char *)this + 136);
    AcquireSRWLockExclusive((PSRWLOCK)this + 17);
    if ( v2 != *((_DWORD *)this + 92) )
    {
      v3 = 1;
      *((_DWORD *)this + 92) = v2;
    }
    if ( this != (CApplicationFrame *)-136LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 17);
    if ( !v3 )
      goto LABEL_9;
    switch ( v2 )
    {
      case 2:
        v41 = &ApplicationFrameRestoreCommand;
        break;
      case 1:
        v41 = (const struct _GUID *)ApplicationFrameMinimizeCommand;
        break;
      case 3:
        v41 = (const struct _GUID *)ApplicationFrameMaximizeCommand;
        break;
      default:
        goto LABEL_72;
    }
    CApplicationFrame::OnCommand((CApplicationFrame *)((char *)this + 40), v41, 0);
LABEL_72:
    LODWORD(v55) = v2;
    v42 = &pszDefault;
    if ( *((_QWORD *)this + 25) )
      v42 = (const WCHAR *)*((_QWORD *)this + 25);
    v52 = v42;
    CApplicationFrameTelemetry::WindowStateChanged<unsigned short const *,unsigned long>(&v52, &v55);
    goto LABEL_9;
  }
  v4 = (RTL_SRWLOCK *)((char *)this + 136);
LABEL_9:
  AcquireSRWLockShared(v4);
  v5 = *((_DWORD *)this + 69);
  if ( v4 )
    ReleaseSRWLockShared(v4);
  if ( v5 == 1 )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 22) + 40LL))(
      *((_QWORD *)this + 22),
      (char *)this + 40);
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
  {
    v51[0] = 0;
    (*(void (__fastcall **)(__int64, HANDLE, char *))(*(_QWORD *)v6 + 232LL))(v6, hObject, v51);
    if ( v51[0] )
      CApplicationFrame::NotifyChromeChange((char *)this + 40, 0);
  }
  if ( !*((_QWORD *)this + 102) )
    goto LABEL_30;
  if ( *((_BYTE *)this + 365) )
    goto LABEL_46;
  v7 = hObject;
  Rect = 0;
  if ( !GetClientRect(*((HWND *)this + 3), &Rect) )
  {
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0xB3A,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      v8);
    goto LABEL_30;
  }
  v53 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 248LL))(*((_QWORD *)this + 24));
  v9 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 15);
  EnterCriticalSection(v9);
  *(_QWORD *)&v57.left = v9;
  v10 = *((_QWORD *)this + 102);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 95);
    LODWORD(v55) = Rect.right - Rect.left;
    v52 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v11 + 88LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v52);
    v13 = v12(v11, &v52);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(const WCHAR *))(*(_QWORD *)v52 + 32LL))(v52);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(const WCHAR *))(*(_QWORD *)v52 + 48LL))(v52);
        if ( v13 >= 0 )
          v13 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v10 + 56LL))(v10, v52);
      }
    }
    v14 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB42,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
        (const char *)(unsigned int)v13,
        v50);
      if ( !v9 )
        goto LABEL_30;
      goto LABEL_29;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 102) + 48LL))(*((_QWORD *)this + 102));
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB43,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
        (const char *)(unsigned int)v15,
        v50);
      if ( !v9 )
        goto LABEL_30;
      goto LABEL_29;
    }
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, HANDLE))(**((_QWORD **)this + 95) + 552LL))(*((_QWORD *)this + 95), v7);
  if ( (unsigned int)(v16 + 2005270523) > 2 )
  {
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4E,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
        (const char *)(unsigned int)v16,
        v50);
      if ( !v9 )
        goto LABEL_30;
      goto LABEL_29;
    }
  }
  else
  {
    CApplicationFrame::RecreateDeviceAsync((CApplicationFrame *)((char *)this + 56));
  }
  if ( v9 )
LABEL_29:
    LeaveCriticalSection(v9);
LABEL_30:
  if ( !*((_BYTE *)this + 365) )
  {
    Rect = 0;
    if ( *((_QWORD *)this + 18) )
    {
      v17 = hObject;
      if ( GetClientRect(*((HWND *)this + 3), &Rect) )
      {
        *(float *)&v52 = (float)(Rect.right - Rect.left);
        v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 248LL))(*((_QWORD *)this + 24));
        *((float *)&v52 + 1) = (float)(Rect.bottom - v18 - Rect.top);
        v19 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 15);
        EnterCriticalSection(v19);
        *(_QWORD *)&v57.left = v19;
        v20 = *((_QWORD *)this + 18);
        *(_QWORD *)(v20 + 204) = v52;
        if ( *(_DWORD *)(v20 + 184) == 1 )
        {
          v43 = lambda_da8f0cb0d38a7c0413d97f66b7e8af4f_::_lambda_da8f0cb0d38a7c0413d97f66b7e8af4f_(&v58, v20, &v52);
          v44 = wil::ResultFromException__lambda_51a891446160b65dc558e4d6e9e100e0___(v43);
          if ( v44 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x44,
              (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\systemvisuals.cpp",
              (const char *)(unsigned int)v44,
              v50);
        }
        v21 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 18);
        v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 376LL))(*((_QWORD *)this + 24));
        v23 = v21 + 1;
        if ( !v21 )
          v23 = 0;
        v24 = CObjectWithThreadUseDetection::TryEnterOnCurrentThread(v23);
        v21[5].RecursionCount = v22;
        if ( v24 >= 0 )
          LeaveCriticalSection(v23);
        v25 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 18);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 248LL))(*((_QWORD *)this + 24));
        v26 = v25 + 1;
        if ( !v25 )
          v26 = 0;
        *(_QWORD *)&v58.left = v26;
        v27 = CObjectWithThreadUseDetection::TryEnterOnCurrentThread(v26);
        v58.right = v27;
        OwningThread = v25[3].OwningThread;
        if ( OwningThread )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 48LL))(OwningThread);
        if ( v27 >= 0 )
          LeaveCriticalSection(v26);
        (*(void (__fastcall **)(_QWORD, HANDLE))(**((_QWORD **)this + 95) + 552LL))(*((_QWORD *)this + 95), v17);
        if ( v19 )
          LeaveCriticalSection(v19);
      }
    }
  }
LABEL_46:
  v29 = *((_QWORD *)this + 21);
  if ( v29 )
  {
    v30 = CWindowPresentationMessaging::s_wmWindowPositionChanged;
    if ( CWindowPresentationMessaging::s_wmWindowPositionChanged )
    {
      v31 = *(_QWORD *)(v29 + 48);
      if ( v31 )
      {
        v32 = *(_DWORD *)(v29 + 40);
        v33 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v34 = v33;
        if ( v33 )
        {
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(v33);
          *v34 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
          v34[2] = v31;
          *((_DWORD *)v34 + 6) = v30;
          *((_DWORD *)v34 + 7) = v58.bottom;
          v34[4] = 0;
          v34[5] = 0;
          *v34 = &off_180073128;
        }
        else
        {
          v34 = 0;
        }
        v50 = (int)v34;
        v35 = SHTaskPoolQueueTask(3, 2, v32, 0);
        if ( v34 )
          (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
        if ( v35 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x96,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\windowpresentationmessaging.cpp",
            (const char *)(unsigned int)v35,
            (int)v34);
      }
    }
  }
  v36 = *((_QWORD *)this + 28);
  if ( v36 )
  {
    Rect = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v36 + 80));
    v37 = *(_QWORD *)(v36 + 96);
    v55 = v37;
    v38 = *(_BYTE *)(v36 + 88);
    v39 = *(_BYTE *)(v36 + 89);
    v51[0] = v39;
    v53 = *(_DWORD *)(v36 + 92);
    CopyRect(&Rect, (const RECT *)(v36 + 104));
    *(_BYTE *)(v36 + 88) = 0;
    *(_QWORD *)(v36 + 96) = 0;
    *(_DWORD *)(v36 + 92) = 0;
    *(_OWORD *)(v36 + 104) = 0;
    if ( v36 != -80 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v36 + 80));
    v57 = 0;
    v59 = 0;
    v58 = 0;
    if ( !v39 )
      goto LABEL_94;
    PresentedWindowRects = CApplicationFrameInputPaneWindowService::_GetPresentedWindowRects(
                             (CApplicationFrameInputPaneWindowService *)v36,
                             &v57,
                             &v59);
    if ( PresentedWindowRects < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)PresentedWindowRects,
        v50);
      goto LABEL_62;
    }
    v46 = CApplicationFrameInputPaneWindowService::_MapScreenToPresentedWindowClientRect(
            (CApplicationFrameInputPaneWindowService *)v36,
            &Rect,
            &v58);
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v46,
        v50);
    }
    else
    {
LABEL_94:
      if ( v38 && v37 )
      {
        v52 = (const WCHAR *)v36;
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalAddRef(&v52);
        v47 = lambda_da07a0e4b93a96d0f294b733e0f5fabb_::_lambda_da07a0e4b93a96d0f294b733e0f5fabb_(
                (unsigned int)v60,
                (unsigned int)&v52,
                (unsigned int)&v55,
                (unsigned int)v51,
                (__int64)&v53,
                (__int64)&Rect,
                (__int64)&v58,
                (__int64)&v59,
                (__int64)&v57);
        Windows::Internal::ComTaskPool::QueueTask__lambda_da07a0e4b93a96d0f294b733e0f5fabb___(
          v49,
          v48,
          *(unsigned int *)(v36 + 72),
          v47);
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::~ComPtr<CApplicationFrameInputPaneWindowService>(v60);
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(&v52);
      }
    }
  }
LABEL_62:
  v40 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v40 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v40);
}

```

## disassembly

```asm
0x1800128d0  push    rbp
0x1800128d2  push    rbx
0x1800128d3  push    rsi
0x1800128d4  push    rdi
0x1800128d5  push    r12
0x1800128d7  push    r13
0x1800128d9  push    r14
0x1800128db  push    r15
0x1800128dd  lea     rbp, [rsp-48h]
0x1800128e2  sub     rsp, 148h
0x1800128e9  mov     rax, cs:__security_cookie
0x1800128f0  xor     rax, rsp
0x1800128f3  mov     [rbp+80h+var_50], rax
0x1800128f7  mov     rsi, rcx
0x1800128fa  mov     [rsp+180h+hObject], 0
0x180012903  lea     rdx, [rsp+180h+hObject]
0x180012908  mov     rcx, [rcx+18h]
0x18001290c  call    cs:__imp_GetResizeDCompositionSynchronizationObject
0x180012912  test    byte ptr [rsi+110h], 1
0x180012919  jz      loc_180012E8D
0x18001291f  mov     rcx, [rsi+18h]; hWnd
0x180012923  call    cs:__imp_IsZoomed
0x180012929  test    eax, eax
0x18001292b  jz      loc_180012EB5
0x180012931  mov     edi, 3
0x180012936  xor     r14b, r14b
0x180012939  lea     rbx, [rsi+88h]
0x180012940  mov     rcx, rbx; SRWLock
0x180012943  call    cs:__imp_AcquireSRWLockExclusive
0x180012949  cmp     edi, [rsi+170h]
0x18001294f  jz      short loc_18001295A
0x180012951  mov     r14b, 1
0x180012954  mov     [rsi+170h], edi
0x18001295a  test    rbx, rbx
0x18001295d  jnz     loc_180012E99
0x180012963  test    r14b, r14b
0x180012966  jnz     loc_180012F1D
0x18001296c  mov     rcx, rbx; SRWLock
0x18001296f  call    cs:__imp_AcquireSRWLockShared
0x180012975  mov     edi, [rsi+114h]
0x18001297b  test    rbx, rbx
0x18001297e  jz      short loc_180012989
0x180012980  mov     rcx, rbx; SRWLock
0x180012983  call    cs:__imp_ReleaseSRWLockShared
0x180012989  cmp     edi, 1
0x18001298c  jnz     short loc_1800129A5
0x18001298e  mov     rcx, [rsi+0B0h]
0x180012995  mov     rax, [rcx]
0x180012998  lea     rdx, [rsi+28h]
0x18001299c  mov     rax, [rax+28h]
0x1800129a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129a5  mov     rcx, [rsi+0C0h]
0x1800129ac  test    rcx, rcx
0x1800129af  jnz     loc_180012ECB
0x1800129b5  cmp     qword ptr [rsi+330h], 0
0x1800129bd  jz      loc_180012B66
0x1800129c3  cmp     byte ptr [rsi+16Dh], 0
0x1800129ca  jnz     loc_180012CE4
0x1800129d0  mov     r15, [rsp+180h+hObject]
0x1800129d5  xorps   xmm0, xmm0
0x1800129d8  movups  xmmword ptr [rsp+180h+Rect.left], xmm0
0x1800129dd  lea     rdx, [rsp+180h+Rect]; lpRect
0x1800129e2  mov     rcx, [rsi+18h]; hWnd
0x1800129e6  call    cs:__imp_GetClientRect
0x1800129ec  test    eax, eax
0x1800129ee  jz      loc_180013070
0x1800129f4  mov     rcx, [rsi+0C0h]
0x1800129fb  mov     rax, [rcx]
0x1800129fe  mov     rax, [rax+0F8h]
0x180012a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a0a  mov     [rsp+180h+var_120], eax
0x180012a0e  mov     ecx, [rbp+80h+Rect.bottom]
0x180012a11  sub     ecx, [rsp+180h+Rect.top]
0x180012a15  sub     ecx, eax
0x180012a17  mov     r12d, 0
0x180012a1d  cmovns  r12d, ecx
0x180012a21  mov     r14, [rsi+78h]
0x180012a25  mov     rcx, r14; lpCriticalSection
0x180012a28  call    cs:__imp_EnterCriticalSection
0x180012a2e  mov     qword ptr [rbp+80h+var_F8.left], r14
0x180012a32  mov     r13, [rsi+330h]
0x180012a39  test    r13, r13
0x180012a3c  jz      loc_180012B26
0x180012a42  mov     rdi, [rsi+2F8h]
0x180012a49  mov     eax, [rbp+80h+Rect.right]
0x180012a4c  sub     eax, [rsp+180h+Rect.left]
0x180012a50  mov     dword ptr [rsp+180h+var_110], eax
0x180012a54  mov     [rsp+180h+var_128], 0
0x180012a5d  mov     rax, [rdi]
0x180012a60  mov     rbx, [rax+58h]
0x180012a64  lea     rcx, [rsp+180h+var_128]
0x180012a69  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180012a6e  lea     rdx, [rsp+180h+var_128]
0x180012a73  mov     rcx, rdi
0x180012a76  mov     rax, rbx
0x180012a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a7e  mov     ebx, eax
0x180012a80  test    eax, eax
0x180012a82  js      short loc_180012ADA
0x180012a84  mov     rcx, [rsp+180h+var_128]
0x180012a89  mov     rax, [rcx]
0x180012a8c  movd    xmm1, dword ptr [rsp+180h+var_110]
0x180012a92  cvtdq2ps xmm1, xmm1
0x180012a95  mov     rax, [rax+20h]
0x180012a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a9e  mov     ebx, eax
0x180012aa0  test    eax, eax
0x180012aa2  js      short loc_180012ADA
0x180012aa4  mov     rcx, [rsp+180h+var_128]
0x180012aa9  mov     rax, [rcx]
0x180012aac  movd    xmm1, r12d
0x180012ab1  cvtdq2ps xmm1, xmm1
0x180012ab4  mov     rax, [rax+30h]
0x180012ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abd  mov     ebx, eax
0x180012abf  test    eax, eax
0x180012ac1  js      short loc_180012ADA
0x180012ac3  mov     rax, [r13+0]
0x180012ac7  mov     rdx, [rsp+180h+var_128]
0x180012acc  mov     rcx, r13
0x180012acf  mov     rax, [rax+38h]
0x180012ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ad8  mov     ebx, eax
0x180012ada  mov     rcx, [rsp+180h+var_128]
0x180012adf  test    rcx, rcx
0x180012ae2  jz      short loc_180012AFA
0x180012ae4  mov     [rsp+180h+var_128], 0
0x180012aed  mov     rax, [rcx]
0x180012af0  mov     rax, [rax+10h]
0x180012af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012af9  nop
0x180012afa  test    ebx, ebx
0x180012afc  js      loc_180012FC5
0x180012b02  mov     rcx, [rsi+330h]
0x180012b09  mov     rax, [rcx]
0x180012b0c  movd    xmm1, [rsp+180h+var_120]
0x180012b12  cvtdq2ps xmm1, xmm1
0x180012b15  mov     rax, [rax+30h]
0x180012b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1e  test    eax, eax
0x180012b20  js      loc_18001303A
0x180012b26  mov     rcx, [rsi+2F8h]
0x180012b2d  mov     rax, [rcx]
0x180012b30  mov     rdx, r15
0x180012b33  mov     rax, [rax+228h]
0x180012b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b3f  lea     ecx, [rax+7785FFFBh]
0x180012b45  cmp     ecx, 2
0x180012b48  ja      loc_180013008
0x180012b4e  lea     rcx, [rsi+38h]; this
0x180012b52  call    ?RecreateDeviceAsync@CApplicationFrame@@UEAAXXZ; CApplicationFrame::RecreateDeviceAsync(void)
0x180012b57  nop
0x180012b58  test    r14, r14
0x180012b5b  jz      short loc_180012B66
0x180012b5d  mov     rcx, r14; lpCriticalSection
0x180012b60  call    cs:__imp_LeaveCriticalSection
0x180012b66  cmp     byte ptr [rsi+16Dh], 0
0x180012b6d  jnz     loc_180012CE4
0x180012b73  xorps   xmm0, xmm0
0x180012b76  movups  xmmword ptr [rsp+180h+Rect.left], xmm0
0x180012b7b  cmp     qword ptr [rsi+90h], 0
0x180012b83  jz      loc_180012CE4
0x180012b89  mov     r12, [rsp+180h+hObject]
0x180012b8e  lea     rdx, [rsp+180h+Rect]; lpRect
0x180012b93  mov     rcx, [rsi+18h]; hWnd
0x180012b97  call    cs:__imp_GetClientRect
0x180012b9d  test    eax, eax
0x180012b9f  jz      loc_180012CE4
0x180012ba5  mov     eax, [rbp+80h+Rect.right]
0x180012ba8  sub     eax, [rsp+180h+Rect.left]
0x180012bac  movd    xmm0, eax
0x180012bb0  cvtdq2ps xmm0, xmm0
0x180012bb3  movss   dword ptr [rsp+180h+var_128], xmm0
0x180012bb9  mov     rcx, [rsi+0C0h]
0x180012bc0  mov     rax, [rcx]
0x180012bc3  mov     rax, [rax+0F8h]
0x180012bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bcf  mov     ecx, [rbp+80h+Rect.bottom]
0x180012bd2  sub     ecx, eax
0x180012bd4  sub     ecx, [rsp+180h+Rect.top]
0x180012bd8  movd    xmm0, ecx
0x180012bdc  cvtdq2ps xmm0, xmm0
0x180012bdf  movss   dword ptr [rsp+180h+var_128+4], xmm0
0x180012be5  mov     r14, [rsi+78h]
0x180012be9  mov     rcx, r14; lpCriticalSection
0x180012bec  call    cs:__imp_EnterCriticalSection
0x180012bf2  mov     qword ptr [rbp+80h+var_F8.left], r14
0x180012bf6  mov     rdx, [rsi+90h]
0x180012bfd  movsd   xmm0, [rsp+180h+var_128]
0x180012c03  movsd   qword ptr [rdx+0CCh], xmm0
0x180012c0b  cmp     dword ptr [rdx+0B8h], 1
0x180012c12  jz      loc_180012F6B
0x180012c18  mov     rdi, [rsi+90h]
0x180012c1f  mov     rcx, [rsi+0C0h]
0x180012c26  mov     rax, [rcx]
0x180012c29  mov     rax, [rax+178h]
0x180012c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c35  mov     ebx, eax
0x180012c37  lea     r15, [rdi+28h]
0x180012c3b  xor     edx, edx
0x180012c3d  test    rdi, rdi
0x180012c40  cmovz   r15, rdx
0x180012c44  mov     rcx, r15
0x180012c47  call    ?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z; CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)
0x180012c4c  mov     [rdi+0D4h], ebx
0x180012c52  test    eax, eax
0x180012c54  js      short loc_180012C5F
0x180012c56  mov     rcx, r15; lpCriticalSection
0x180012c59  call    cs:__imp_LeaveCriticalSection
0x180012c5f  mov     rbx, [rsi+90h]
0x180012c66  mov     rcx, [rsi+0C0h]
0x180012c6d  mov     rax, [rcx]
0x180012c70  mov     rax, [rax+0F8h]
0x180012c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c7c  mov     r13d, eax
0x180012c7f  lea     rdi, [rbx+28h]
0x180012c83  xor     ecx, ecx
0x180012c85  test    rbx, rbx
0x180012c88  cmovz   rdi, rcx
0x180012c8c  mov     qword ptr [rbp+80h+var_E8.left], rdi
0x180012c90  mov     rcx, rdi
0x180012c93  call    ?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z; CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)
0x180012c98  mov     r15d, eax
0x180012c9b  mov     [rbp+80h+var_E8.right], eax
0x180012c9e  mov     rcx, [rbx+88h]
0x180012ca5  test    rcx, rcx
0x180012ca8  jnz     loc_180012F04
0x180012cae  test    r15d, r15d
0x180012cb1  js      short loc_180012CBC
0x180012cb3  mov     rcx, rdi; lpCriticalSection
0x180012cb6  call    cs:__imp_LeaveCriticalSection
0x180012cbc  mov     rcx, [rsi+2F8h]
0x180012cc3  mov     rax, [rcx]
0x180012cc6  mov     rdx, r12
0x180012cc9  mov     rax, [rax+228h]
0x180012cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cd5  nop
0x180012cd6  test    r14, r14
0x180012cd9  jz      short loc_180012CE4
0x180012cdb  mov     rcx, r14; lpCriticalSection
0x180012cde  call    cs:__imp_LeaveCriticalSection
0x180012ce4  mov     rax, [rsi+0A8h]
0x180012ceb  test    rax, rax
0x180012cee  jz      loc_180012E85
0x180012cf4  mov     edi, cs:?s_wmWindowPositionChanged@CWindowPresentationMessaging@@0IA; uint CWindowPresentationMessaging::s_wmWindowPositionChanged
0x180012cfa  test    edi, edi
0x180012cfc  jz      loc_180012E85
0x180012d02  mov     r14, [rax+30h]
0x180012d06  test    r14, r14
0x180012d09  jz      loc_180012E85
0x180012d0f  mov     r15d, [rax+28h]
0x180012d13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d1a  mov     ecx, 30h ; '0'; unsigned __int64
0x180012d1f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012d24  mov     rbx, rax
0x180012d27  test    rax, rax
0x180012d2a  jz      loc_18001308D
0x180012d30  mov     rcx, rax
0x180012d33  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExtensionStateManager@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(void)
0x180012d38  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x180012d3f  mov     [rbx], rcx
0x180012d42  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180012d49  test    rcx, rcx
0x180012d4c  jz      short loc_180012D5B
0x180012d4e  mov     rax, [rcx]
0x180012d51  mov     rax, [rax+8]
0x180012d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d5a  nop
0x180012d5b  mov     [rbx+10h], r14
0x180012d5f  mov     [rbx+18h], edi
0x180012d62  mov     eax, [rbp+80h+var_E8.bottom]
0x180012d65  mov     [rbx+1Ch], eax
0x180012d68  xor     r13d, r13d
0x180012d6b  mov     [rbx+20h], r13
0x180012d6f  mov     [rbx+28h], r13
0x180012d73  lea     rax, off_180073128
0x180012d7a  mov     [rbx], rax
0x180012d7d  mov     [rsp+180h+var_158], r13
0x180012d82  mov     qword ptr [rsp+180h+var_160], rbx; int
0x180012d87  xor     r9d, r9d
0x180012d8a  mov     r8d, r15d
0x180012d8d  mov     edx, 2
0x180012d92  mov     ecx, 3
0x180012d97  call    cs:__imp_SHTaskPoolQueueTask
0x180012d9d  mov     edi, eax
0x180012d9f  test    rbx, rbx
0x180012da2  jz      short loc_180012DB4
0x180012da4  mov     rcx, [rbx]
0x180012da7  mov     rax, [rcx+10h]
0x180012dab  mov     rcx, rbx
0x180012dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db3  nop
0x180012db4  mov     rcx, [rbp+88h]; this
0x180012dbb  test    edi, edi
0x180012dbd  js      loc_180012FEF
0x180012dc3  mov     rdi, [rsi+0E0h]
0x180012dca  test    rdi, rdi
0x180012dcd  jz      short loc_180012E4D
0x180012dcf  xorps   xmm0, xmm0
0x180012dd2  movups  xmmword ptr [rsp+180h+Rect.left], xmm0
  ... truncated ...
```
