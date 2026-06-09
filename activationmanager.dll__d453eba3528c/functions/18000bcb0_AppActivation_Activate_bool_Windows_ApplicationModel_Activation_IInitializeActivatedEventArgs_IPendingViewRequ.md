# AppActivation::Activate(bool,Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *,IPendingViewRequest *,ACTIVATION_PHASE *,IInspectable * *)

- ea: `0x18000bcb0`
- end: `0x18000c532`
- name: `?Activate@AppActivation@@UEAAJ_NPEAUIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIPendingViewRequest@@PEAW4ACTIVATION_PHASE@@PEAPEAUIInspectable@@@Z`
- size: `2178`
- prototype: `__int64 __fastcall(AppActivation *__hidden this, bool, struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *, struct IPendingViewRequest *, enum ACTIVATION_PHASE *, struct IInspectable **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18000bcb0`
- `0x18000c538`
- `0x18000c9e0`
- `0x180011328`
- `0x180023620`
- `0x180032ed4`
- `0x180048324`
- `0x18005ae90`
- `0x180067e64`
- `0x18007b6e8`
- `0x1800837b0`
- `0x18008442c`
- `0x1800848cc`
- `0x180089994`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000c4c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000c4c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c4bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c4bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bed9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000beb4`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000beb4`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000c2a3`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18000c2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c00c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c13a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c14a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c00c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c13a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c14a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c487`
- `api-ms-win-core-com-private-l1-1-0!CoGetErrorInfo` at `0x18000c471`
- `api-ms-win-core-com-private-l1-1-0!CoGetErrorInfo` at `0x18000c471`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000c4db`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000c4db`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerStart` at `0x18000c324`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerStart` at `0x18000c324`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerInitialize` at `0x18000c2ca`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerInitialize` at `0x18000c2ca`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerCleanup` at `0x18000be88`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerCleanup` at `0x18000be88`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppActivation::Activate(
        HSTRING *this,
        bool a2,
        struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *a3,
        struct IPendingViewRequest *a4,
        enum ACTIVATION_PHASE *a5,
        struct IInspectable **a6)
{
  __int64 v7; // r13
  const WCHAR **v8; // rbx
  int v9; // esi
  HSTRING v10; // rcx
  const WCHAR *v11; // rdi
  HSTRING v12; // r14
  _WORD *v13; // rbx
  int v14; // r15d
  HSTRING v15; // r12
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rdi
  AppActivation *v18; // rsi
  int v19; // edi
  PCWSTR v20; // rcx
  __int64 *v21; // r14
  _WORD *v23; // rax
  _WORD *v24; // rdx
  unsigned __int64 v25; // rcx
  __int16 v26; // ax
  PCWSTR v27; // rbx
  PCWSTR v28; // r9
  struct _TP_WAIT *v29; // r8
  const wchar_t *v30; // rdx
  __int64 v31; // rcx
  int v32; // ecx
  unsigned int v33; // r10d
  __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rax
  unsigned int v37; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v39; // r9
  struct _TP_WAIT *v40; // r8
  const wchar_t *v41; // rdx
  __int64 v42; // rcx
  int v43; // ecx
  __int64 v44; // rax
  unsigned int v45; // eax
  __int64 v46; // rax
  unsigned int v47; // eax
  __int64 v48; // rax
  unsigned int v49; // eax
  HRESULT v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  unsigned int v54; // ebx
  __int64 v55; // rbx
  unsigned int v56; // eax
  __int64 v57; // rcx
  void *v58; // rbx
  const unsigned __int16 *v59; // rax
  struct IPendingViewRequest *v60; // [rsp+20h] [rbp-E0h]
  struct IPendingViewRequest *v61; // [rsp+20h] [rbp-E0h]
  bool v62; // [rsp+50h] [rbp-B0h]
  int v63; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v64; // [rsp+60h] [rbp-A0h] BYREF
  AppActivation *v65; // [rsp+68h] [rbp-98h]
  _WORD *v66; // [rsp+70h] [rbp-90h] BYREF
  struct IInspectable **v67; // [rsp+78h] [rbp-88h]
  enum ACTIVATION_PHASE *v68; // [rsp+80h] [rbp-80h]
  struct IPendingViewRequest *v69; // [rsp+88h] [rbp-78h]
  struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *v70; // [rsp+90h] [rbp-70h]
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  DWORD CurrentThreadId; // [rsp+A8h] [rbp-58h]
  unsigned int v73; // [rsp+ACh] [rbp-54h]
  const wchar_t *v74; // [rsp+B0h] [rbp-50h]
  int v75; // [rsp+B8h] [rbp-48h]
  int v76; // [rsp+BCh] [rbp-44h]
  PTP_WAIT pwa[2]; // [rsp+C0h] [rbp-40h]
  PCWSTR v78; // [rsp+D0h] [rbp-30h]
  LPVOID pv; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v80; // [rsp+E0h] [rbp-20h]
  HANDLE hObject; // [rsp+F0h] [rbp-10h]
  __int64 v82; // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v83; // [rsp+100h] [rbp+0h]
  __int64 v84; // [rsp+108h] [rbp+8h]
  HSTRING v85; // [rsp+110h] [rbp+10h]
  HSTRING v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v69 = a4;
  v70 = a3;
  v62 = a2;
  v65 = (AppActivation *)this;
  v68 = a5;
  v67 = a6;
  *(_DWORD *)a5 = 32;
  if ( a6 )
    *a6 = 0;
  v7 = -1;
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 4) != 0 )
  {
    v63 = *((unsigned __int8 *)this + 104);
    StringRawBuffer = WindowsGetStringRawBuffer(this[16], 0);
    v39 = WindowsGetStringRawBuffer(this[15], 0);
    v40 = (struct _TP_WAIT *)this[4];
    v41 = (const wchar_t *)this[2];
    v64 = 0;
    if ( v41 )
    {
      v42 = -1;
      do
        ++v42;
      while ( v41[v42] );
      v43 = 2 * v42 + 2;
    }
    else
    {
      v43 = 10;
      v41 = L"NULL";
    }
    v74 = v41;
    v75 = v43;
    v76 = 0;
    if ( v40 )
    {
      v44 = -1;
      do
        ++v44;
      while ( *((_WORD *)v40 + v44) );
      v45 = 2 * v44 + 2;
    }
    else
    {
      v45 = 10;
      v40 = (struct _TP_WAIT *)L"NULL";
    }
    pwa[0] = v40;
    pwa[1] = (PTP_WAIT)v45;
    if ( v39 )
    {
      v46 = -1;
      do
        ++v46;
      while ( v39[v46] );
      v47 = 2 * v46 + 2;
    }
    else
    {
      v47 = 10;
      v39 = L"NULL";
    }
    v78 = v39;
    pv = (LPVOID)v47;
    if ( StringRawBuffer )
    {
      v48 = -1;
      do
        ++v48;
      while ( StringRawBuffer[v48] );
      v49 = 2 * v48 + 2;
    }
    else
    {
      v49 = 10;
      StringRawBuffer = L"NULL";
    }
    *(_QWORD *)&v80 = StringRawBuffer;
    *((_QWORD *)&v80 + 1) = v49;
    hObject = &v64;
    v82 = 4;
    v83 = (__int64 *)&v63;
    v84 = 4;
    v60 = (struct IPendingViewRequest *)&v71;
    McGenEventWrite_EventWriteTransfer(
      MICROSOFT_TWINUI_PUBLISHER_Context,
      PerfTrack_AppActivation_Activate_Start,
      v40,
      7);
  }
  *(_DWORD *)a5 = 8;
  v8 = (const WCHAR **)(this + 26);
  if ( this[26] )
  {
    v53 = AppActivation::WaitForHamActivityStarted((AppActivation *)this);
    v54 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v53,
        (int)v60);
      return v54;
    }
    v8 = (const WCHAR **)(this + 26);
  }
  *(_DWORD *)a5 = 32;
  v63 = 0;
  v9 = 2;
  v10 = this[21];
  if ( v10 )
  {
    (*(void (__fastcall **)(HSTRING, int *))(*(_QWORD *)v10 + 136LL))(v10, &v63);
    if ( (v63 & 0x10000) != 0 )
    {
      v9 = 4;
    }
    else if ( (v63 & 0x20000) != 0 )
    {
      v9 = 8;
    }
  }
  v11 = *v8;
  v64 = *((_DWORD *)this + 23);
  v12 = this[9];
  v13 = this[5];
  v66 = v13;
  v14 = *((_DWORD *)this + 22);
  v15 = this[14];
  v71 = *((_QWORD *)v65 + 8);
  CurrentThreadId = GetCurrentThreadId();
  v73 = v64;
  v74 = 0;
  v75 = 0;
  *(_OWORD *)pwa = 0;
  v78 = v11;
  if ( v11 )
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v11 + 8LL))(v11);
  pv = 0;
  v80 = 0;
  hObject = 0;
  v83 = 0;
  LODWORD(v84) = v14;
  v85 = v12;
  v86 = v15;
  v87 = v9;
  if ( v13 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v13[v16] );
    v17 = v16 + 1;
    if ( v16 + 1 >= v16 && is_mul_ok(v17, 2u) )
    {
      v23 = CoTaskMemAlloc(2 * v17);
      if ( v23 )
      {
        *((_QWORD *)&v80 + 1) = v16 + 1;
        pv = v23;
        *v23 = 0;
        if ( v16 != -1 )
        {
          v24 = pv;
          if ( v16 <= 0x7FFFFFFE && v17 <= 0x7FFFFFFF )
          {
            v25 = v16;
            while ( v25 )
            {
              v26 = *v13;
              if ( !*v13 )
              {
                if ( !v17 )
                {
LABEL_45:
                  --v24;
                  break;
                }
                break;
              }
              ++v13;
              *v24++ = v26;
              --v25;
              if ( !--v17 )
                goto LABEL_45;
            }
          }
          *v24 = 0;
        }
        *(_QWORD *)&v80 = v16;
      }
    }
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  }
  if ( v64 != -1 )
  {
    v50 = CoEnableCallCancellation(0);
    if ( v50 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\RpcTimer.h",
        (const char *)(unsigned int)v50,
        (int)v60);
      AAMTraceProvider::CoEnableCallCancellationFailure<unsigned short const * &>(&v66);
      MicrosoftTelemetryAssertTriggeredNoArgs(v57);
    }
    else
    {
      BYTE2(v75) = 1;
      if ( !HIBYTE(v75) )
      {
        if ( (unsigned int)PsmTimerInitialize(&v82) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v51);
        v83 = &v82;
        LODWORD(v60) = v87;
        if ( (unsigned int)PsmTimerStart(
                             &v82,
                             v86,
                             (unsigned int)v84,
                             pv,
                             v60,
                             v85,
                             0,
                             v73,
                             CRPCTimeoutAndWaitOnAppLaunchGrace::s_ResourceAwareTimerExpiration,
                             &v71,
                             v62) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v52);
      }
    }
  }
  v18 = v65;
  v19 = AppActivation::ActivateInternal(v65, v62, v70, (struct CRPCTimeoutAndWaitOnAppLaunchGrace *)&v71, v69, v68, v67);
  if ( v19 < 0 )
  {
    if ( BYTE1(v75) )
    {
      v19 = -2144927142;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v18 + 216);
      CoGetErrorInfo(0, (char *)v18 + 216);
      v58 = (void *)*((_QWORD *)v18 + 32);
      v59 = WindowsGetStringRawBuffer(*((HSTRING *)v18 + 16), 0);
      v19 = AppActivation::TransformActivationError(v18, v19, *((const unsigned __int16 **)v18 + 4), v59, v58);
    }
  }
  if ( BYTE2(v75) )
  {
    if ( !HIBYTE(v75) )
    {
      HIBYTE(v75) = 1;
      if ( BYTE1(v75) )
        AAMTraceProvider::RPCTimerDisarming<unsigned __int64 &>(&v71);
      if ( v83 )
      {
        PsmTimerCleanup();
        v83 = 0;
      }
      if ( pwa[1] )
      {
        WaitForThreadpoolWaitCallbacks(pwa[1], 1);
        CloseThreadpoolWait(pwa[1]);
        pwa[1] = 0;
      }
      if ( pwa[0] )
      {
        DeleteTimerQueueTimer(0, pwa[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        pwa[0] = 0;
      }
    }
    if ( BYTE2(v75) )
    {
      CoDisableCallCancellation(0);
      BYTE2(v75) = 0;
    }
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v80 = 0;
  v20 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = (__int64 *)((char *)v18 + 208);
  if ( v19 < 0 )
  {
    v55 = *v21;
    if ( *v21 )
    {
      v56 = HamTerminateTypeFromHRESULT((unsigned int)v19);
      HamActivityWrapper::TerminateHost(v55, v56, 3328);
    }
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 4) != 0 )
  {
    v63 = *((unsigned __int8 *)v18 + 104);
    v27 = WindowsGetStringRawBuffer(*((HSTRING *)v18 + 16), 0);
    v28 = WindowsGetStringRawBuffer(*((HSTRING *)v18 + 15), 0);
    v29 = (struct _TP_WAIT *)*((_QWORD *)v18 + 4);
    v30 = (const wchar_t *)*((_QWORD *)v18 + 2);
    v64 = 0;
    if ( v30 )
    {
      v31 = -1;
      do
        ++v31;
      while ( v30[v31] );
      v32 = 2 * v31 + 2;
      v33 = 10;
    }
    else
    {
      v33 = 10;
      v32 = 10;
      v30 = L"NULL";
    }
    v74 = v30;
    v75 = v32;
    v76 = 0;
    if ( v29 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v29 + v34) );
      v35 = 2 * v34 + 2;
    }
    else
    {
      v35 = 10;
      v29 = (struct _TP_WAIT *)L"NULL";
    }
    pwa[0] = v29;
    pwa[1] = (PTP_WAIT)v35;
    if ( v28 )
    {
      v36 = -1;
      do
        ++v36;
      while ( v28[v36] );
      v37 = 2 * v36 + 2;
    }
    else
    {
      v37 = 10;
      v28 = L"NULL";
    }
    v78 = v28;
    pv = (LPVOID)v37;
    if ( v27 )
    {
      do
        ++v7;
      while ( v27[v7] );
      v33 = 2 * v7 + 2;
    }
    else
    {
      v27 = L"NULL";
    }
    *(_QWORD *)&v80 = v27;
    *((_QWORD *)&v80 + 1) = v33;
    hObject = &v64;
    v82 = 4;
    v83 = (__int64 *)&v63;
    v84 = 4;
    v61 = (struct IPendingViewRequest *)&v71;
    McGenEventWrite_EventWriteTransfer(
      MICROSOFT_TWINUI_PUBLISHER_Context,
      PerfTrack_AppActivation_Activate_Stop,
      v29,
      7);
  }
  if ( v19 >= 0 )
  {
    if ( (*((_BYTE *)v18 + 100) & 1) != 0 )
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v18 + 208);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v19,
      (int)v61);
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x18000bcb0  push    rbp
0x18000bcb2  push    rbx
0x18000bcb3  push    rsi
0x18000bcb4  push    rdi
0x18000bcb5  push    r12
0x18000bcb7  push    r13
0x18000bcb9  push    r14
0x18000bcbb  push    r15
0x18000bcbd  lea     rbp, [rsp-48h]
0x18000bcc2  sub     rsp, 148h
0x18000bcc9  mov     rax, cs:__security_cookie
0x18000bcd0  xor     rax, rsp
0x18000bcd3  mov     [rbp+80h+var_50], rax
0x18000bcd7  mov     [rbp+80h+var_F8], r9
0x18000bcdb  mov     [rbp+80h+var_F0], r8
0x18000bcdf  mov     [rsp+180h+var_130], dl
0x18000bce3  mov     r12, rcx
0x18000bce6  mov     [rsp+180h+var_118], rcx
0x18000bceb  mov     rdi, [rbp+80h+arg_20]
0x18000bcf2  mov     [rbp+80h+var_100], rdi
0x18000bcf6  mov     rax, [rbp+80h+arg_28]
0x18000bcfd  mov     [rsp+180h+var_108], rax
0x18000bd02  mov     dword ptr [rdi], 20h ; ' '
0x18000bd08  xor     esi, esi
0x18000bd0a  test    rax, rax
0x18000bd0d  jnz     loc_18000C3CE
0x18000bd13  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000bd1a  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 4
0x18000bd21  jnz     loc_18000C129
0x18000bd27  mov     r14d, 8
0x18000bd2d  mov     [rdi], r14d
0x18000bd30  lea     rbx, [r12+0D0h]
0x18000bd38  cmp     [rbx], rsi
0x18000bd3b  jnz     loc_18000C349
0x18000bd41  mov     dword ptr [rdi], 20h ; ' '
0x18000bd47  mov     [rsp+180h+var_128], esi
0x18000bd4b  mov     esi, 2
0x18000bd50  mov     rcx, [r12+0A8h]
0x18000bd58  test    rcx, rcx
0x18000bd5b  jnz     loc_18000C275
0x18000bd61  mov     rdi, [rbx]
0x18000bd64  mov     eax, [r12+5Ch]
0x18000bd69  mov     [rsp+180h+var_120], eax
0x18000bd6d  mov     r14, [r12+48h]
0x18000bd72  mov     rbx, [r12+28h]
0x18000bd77  mov     [rsp+180h+var_110], rbx
0x18000bd7c  mov     r15d, [r12+58h]
0x18000bd81  mov     r12, [r12+70h]
0x18000bd86  mov     rax, [rsp+180h+var_118]
0x18000bd8b  mov     rax, [rax+40h]
0x18000bd8f  mov     [rbp+80h+var_E0], rax
0x18000bd93  call    cs:__imp_GetCurrentThreadId
0x18000bd99  mov     [rbp+80h+var_D8], eax
0x18000bd9c  mov     eax, [rsp+180h+var_120]
0x18000bda0  mov     [rbp+80h+var_D4], eax
0x18000bda3  xor     eax, eax
0x18000bda5  mov     [rbp+80h+var_D0], rax
0x18000bda9  mov     [rbp+80h+var_C8], eax
0x18000bdac  xorps   xmm0, xmm0
0x18000bdaf  movdqa  xmmword ptr [rbp+80h+pwa], xmm0
0x18000bdb4  mov     [rbp+80h+var_B0], rdi
0x18000bdb8  test    rdi, rdi
0x18000bdbb  jz      short loc_18000BDCE
0x18000bdbd  mov     rax, [rdi]
0x18000bdc0  mov     rcx, rdi
0x18000bdc3  mov     rax, [rax+8]
0x18000bdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdcc  xor     eax, eax
0x18000bdce  mov     [rbp+80h+pv], rax
0x18000bdd2  xorps   xmm0, xmm0
0x18000bdd5  movdqa  [rbp+80h+var_A0], xmm0
0x18000bdda  mov     [rbp+80h+hObject], rax
0x18000bdde  mov     [rbp+80h+var_80], rax
0x18000bde2  mov     dword ptr [rbp+80h+var_78], r15d
0x18000bde6  mov     [rbp+80h+var_70], r14
0x18000bdea  mov     [rbp+80h+var_68], r12
0x18000bdee  mov     [rbp+80h+var_60], esi
0x18000bdf1  test    rbx, rbx
0x18000bdf4  jz      loc_18000C409
0x18000bdfa  mov     rsi, r13
0x18000bdfd  nop     dword ptr [rax]
0x18000be00  inc     rsi
0x18000be03  cmp     word ptr [rbx+rsi*2], 0
0x18000be08  jnz     short loc_18000BE00
0x18000be0a  lea     rdi, [rsi+1]
0x18000be0e  xor     r15d, r15d
0x18000be11  cmp     rdi, rsi
0x18000be14  jnb     loc_18000BF66
0x18000be1a  cmp     [rsp+180h+var_120], 0FFFFFFFFh
0x18000be1f  jnz     loc_18000C2A1
0x18000be25  mov     rax, [rsp+180h+var_108]
0x18000be2a  mov     [rsp+180h+var_150], rax; struct IInspectable **
0x18000be2f  mov     rax, [rbp+80h+var_100]
0x18000be33  mov     [rsp+180h+var_158], rax; enum ACTIVATION_PHASE *
0x18000be38  mov     rax, [rbp+80h+var_F8]
0x18000be3c  mov     [rsp+180h+var_160], rax; int
0x18000be41  lea     r9, [rbp+80h+var_E0]; struct CRPCTimeoutAndWaitOnAppLaunchGrace *
0x18000be45  mov     r8, [rbp+80h+var_F0]; struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *
0x18000be49  movzx   edx, [rsp+180h+var_130]; bool
0x18000be4e  mov     rsi, [rsp+180h+var_118]
0x18000be53  mov     rcx, rsi; this
0x18000be56  call    ?ActivateInternal@AppActivation@@AEAAJ_NPEAUIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAVCRPCTimeoutAndWaitOnAppLaunchGrace@@PEAUIPendingViewRequest@@PEAW4ACTIVATION_PHASE@@PEAPEAUIInspectable@@@Z; AppActivation::ActivateInternal(bool,Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *,CRPCTimeoutAndWaitOnAppLaunchGrace *,IPendingViewRequest *,ACTIVATION_PHASE *,IInspectable * *)
0x18000be5b  mov     edi, eax
0x18000be5d  test    eax, eax
0x18000be5f  js      loc_18000C44C
0x18000be65  cmp     byte ptr [rbp+80h+var_C8+2], 0
0x18000be69  jz      short loc_18000BEBE
0x18000be6b  cmp     byte ptr [rbp+80h+var_C8+3], 0
0x18000be6f  jnz     short loc_18000BEAC
0x18000be71  mov     byte ptr [rbp+80h+var_C8+3], 1
0x18000be75  cmp     byte ptr [rbp+80h+var_C8+1], 0
0x18000be79  jnz     loc_18000C4AA
0x18000be7f  mov     rcx, [rbp+80h+var_80]
0x18000be83  test    rcx, rcx
0x18000be86  jz      short loc_18000BE92
0x18000be88  call    cs:__imp_PsmTimerCleanup
0x18000be8e  mov     [rbp+80h+var_80], r15
0x18000be92  mov     rcx, [rbp+80h+pwa+8]; pwa
0x18000be96  test    rcx, rcx
0x18000be99  jnz     loc_18000C4B8
0x18000be9f  mov     rdx, [rbp+80h+pwa]; Timer
0x18000bea3  test    rdx, rdx
0x18000bea6  jnz     loc_18000C4D6
0x18000beac  cmp     byte ptr [rbp+80h+var_C8+2], 0
0x18000beb0  jz      short loc_18000BEBE
0x18000beb2  xor     ecx, ecx; pReserved
0x18000beb4  call    cs:__imp_CoDisableCallCancellation
0x18000beba  mov     byte ptr [rbp+80h+var_C8+2], 0
0x18000bebe  mov     rcx, [rbp+80h+hObject]; hObject
0x18000bec2  lea     rax, [rcx-1]
0x18000bec6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000beca  jbe     loc_18000C4EA
0x18000bed0  mov     rcx, [rbp+80h+pv]; pv
0x18000bed4  test    rcx, rcx
0x18000bed7  jz      short loc_18000BEE3
0x18000bed9  call    cs:__imp_CoTaskMemFree
0x18000bedf  mov     [rbp+80h+pv], r15
0x18000bee3  xorps   xmm0, xmm0
0x18000bee6  movdqa  [rbp+80h+var_A0], xmm0
0x18000beeb  mov     rcx, [rbp+80h+var_B0]
0x18000beef  test    rcx, rcx
0x18000bef2  jz      short loc_18000BF05
0x18000bef4  mov     [rbp+80h+var_B0], r15
0x18000bef8  mov     rax, [rcx]
0x18000befb  mov     rax, [rax+10h]
0x18000beff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf04  nop
0x18000bf05  lea     r14, [rsi+0D0h]
0x18000bf0c  test    edi, edi
0x18000bf0e  js      loc_18000C386
0x18000bf14  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 4
0x18000bf1b  jnz     loc_18000BFEC
0x18000bf21  test    edi, edi
0x18000bf23  jns     loc_18000C264
0x18000bf29  mov     rcx, [rbp+88h]; this
0x18000bf30  mov     r9d, edi; char *
0x18000bf33  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000bf3a  mov     edx, 231h; void *
0x18000bf3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf44  mov     eax, edi
0x18000bf46  mov     rcx, [rbp+80h+var_50]
0x18000bf4a  xor     rcx, rsp; StackCookie
0x18000bf4d  call    __security_check_cookie
0x18000bf52  add     rsp, 148h
0x18000bf59  pop     r15
0x18000bf5b  pop     r14
0x18000bf5d  pop     r13
0x18000bf5f  pop     r12
0x18000bf61  pop     rdi
0x18000bf62  pop     rsi
0x18000bf63  pop     rbx
0x18000bf64  pop     rbp
0x18000bf65  retn
0x18000bf66  mov     eax, 2
0x18000bf6b  mul     rdi
0x18000bf6e  test    rdx, rdx
0x18000bf71  jnz     loc_18000BE1A
0x18000bf77  mov     rcx, rax; cb
0x18000bf7a  call    cs:__imp_CoTaskMemAlloc
0x18000bf80  test    rax, rax
0x18000bf83  jz      loc_18000BE1A
0x18000bf89  mov     qword ptr [rbp+80h+var_A0+8], rdi
0x18000bf8d  mov     [rbp+80h+pv], rax
0x18000bf91  mov     [rax], r15w
0x18000bf95  test    rdi, rdi
0x18000bf98  jz      short loc_18000BFE3
0x18000bf9a  mov     rdx, [rbp+80h+pv]
0x18000bf9e  cmp     rsi, 7FFFFFFEh
0x18000bfa5  ja      short loc_18000BFDF
0x18000bfa7  cmp     rdi, 7FFFFFFFh
0x18000bfae  ja      short loc_18000BFDF
0x18000bfb0  mov     rcx, rsi
0x18000bfb3  test    rcx, rcx
0x18000bfb6  jz      short loc_18000BFDF
0x18000bfb8  movzx   eax, word ptr [rbx]
0x18000bfbb  test    ax, ax
0x18000bfbe  jz      short loc_18000BFDA
0x18000bfc0  add     rbx, 2
0x18000bfc4  mov     [rdx], ax
0x18000bfc7  add     rdx, 2
0x18000bfcb  dec     rcx
0x18000bfce  sub     rdi, 1
0x18000bfd2  jnz     short loc_18000BFB3
0x18000bfd4  sub     rdx, 2
0x18000bfd8  jmp     short loc_18000BFDF
0x18000bfda  test    rdi, rdi
0x18000bfdd  jz      short loc_18000BFD4
0x18000bfdf  mov     [rdx], r15w
0x18000bfe3  mov     qword ptr [rbp+80h+var_A0], rsi
0x18000bfe7  jmp     loc_18000BE1A
0x18000bfec  movzx   eax, byte ptr [rsi+68h]
0x18000bff0  mov     [rsp+180h+var_128], eax
0x18000bff4  xor     edx, edx; length
0x18000bff6  mov     rcx, [rsi+80h]; string
0x18000bffd  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c003  mov     rbx, rax
0x18000c006  xor     edx, edx; length
0x18000c008  mov     rcx, [rsi+78h]; string
0x18000c00c  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c012  mov     r9, rax
0x18000c015  mov     r8, [rsi+20h]
0x18000c019  mov     rdx, [rsi+10h]
0x18000c01d  mov     [rsp+180h+var_120], r15d
0x18000c022  test    rdx, rdx
0x18000c025  jz      loc_18000C4F5
0x18000c02b  mov     rcx, r13
0x18000c02e  xchg    ax, ax
0x18000c030  lea     rcx, [rcx+1]
0x18000c034  cmp     word ptr [rdx+rcx*2], 0
0x18000c039  jnz     short loc_18000C030
0x18000c03b  lea     ecx, ds:2[rcx*2]
0x18000c042  mov     r10d, 0Ah
0x18000c048  mov     [rbp+80h+var_D0], rdx
0x18000c04c  mov     [rbp+80h+var_C8], ecx
0x18000c04f  mov     [rbp+80h+var_C4], r15d
0x18000c053  test    r8, r8
0x18000c056  jz      loc_18000C50A
0x18000c05c  mov     rax, r13
0x18000c05f  nop
0x18000c060  lea     rax, [rax+1]
0x18000c064  cmp     word ptr [r8+rax*2], 0
0x18000c06a  jnz     short loc_18000C060
0x18000c06c  lea     eax, ds:2[rax*2]
0x18000c073  mov     [rbp+80h+pwa], r8
0x18000c077  mov     dword ptr [rbp+80h+pwa+8], eax
0x18000c07a  mov     dword ptr [rbp+80h+pwa+0Ch], r15d
0x18000c07e  test    r9, r9
0x18000c081  jz      loc_18000C3AE
0x18000c087  mov     rax, r13
0x18000c08a  nop     word ptr [rax+rax+00h]
0x18000c090  lea     rax, [rax+1]
0x18000c094  cmp     word ptr [r9+rax*2], 0
0x18000c09a  jnz     short loc_18000C090
0x18000c09c  lea     eax, ds:2[rax*2]
0x18000c0a3  mov     [rbp+80h+var_B0], r9
0x18000c0a7  mov     dword ptr [rbp+80h+pv], eax
0x18000c0aa  mov     dword ptr [rbp+80h+pv+4], r15d
0x18000c0ae  test    rbx, rbx
0x18000c0b1  jz      loc_18000C519
0x18000c0b7  nop     word ptr [rax+rax+00000000h]
0x18000c0c0  lea     r13, [r13+1]
0x18000c0c4  cmp     word ptr [rbx+r13*2], 0
0x18000c0ca  jnz     short loc_18000C0C0
0x18000c0cc  lea     r10d, ds:2[r13*2]
0x18000c0d4  mov     qword ptr [rbp+80h+var_A0], rbx
0x18000c0d8  mov     dword ptr [rbp+80h+var_A0+8], r10d
0x18000c0dc  mov     dword ptr [rbp+80h+var_A0+0Ch], r15d
0x18000c0e0  lea     rax, [rsp+180h+var_120]
0x18000c0e5  mov     [rbp+80h+hObject], rax
0x18000c0e9  mov     [rbp+80h+var_88], 4
0x18000c0f1  lea     rax, [rsp+180h+var_128]
0x18000c0f6  mov     [rbp+80h+var_80], rax
0x18000c0fa  mov     [rbp+80h+var_78], 4
0x18000c102  lea     rax, [rbp+80h+var_E0]
0x18000c106  mov     [rsp+180h+var_160], rax
0x18000c10b  mov     r9d, 7
0x18000c111  lea     rdx, PerfTrack_AppActivation_Activate_Stop
0x18000c118  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18000c11f  call    McGenEventWrite_EventWriteTransfer
0x18000c124  jmp     loc_18000BF21
0x18000c129  movzx   eax, byte ptr [rcx+68h]
0x18000c12d  mov     [rsp+180h+var_128], eax
0x18000c131  xor     edx, edx; length
0x18000c133  mov     rcx, [rcx+80h]; string
0x18000c13a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c140  mov     rbx, rax
0x18000c143  xor     edx, edx; length
0x18000c145  mov     rcx, [r12+78h]; string
0x18000c14a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c150  mov     r9, rax
0x18000c153  mov     r8, [r12+20h]
0x18000c158  mov     rdx, [r12+10h]
0x18000c15d  mov     [rsp+180h+var_120], esi
0x18000c161  test    rdx, rdx
0x18000c164  jz      loc_18000C3D6
0x18000c16a  mov     rcx, r13
0x18000c16d  nop     dword ptr [rax]
0x18000c170  lea     rcx, [rcx+1]
0x18000c174  cmp     [rdx+rcx*2], si
0x18000c178  jnz     short loc_18000C170
  ... truncated ...
```
