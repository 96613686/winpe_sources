# FindCallingThreadImmersiveWindow(ulong,HWND__ * *)

- ea: `0x18000e880`
- end: `0x18000eb37`
- name: `?FindCallingThreadImmersiveWindow@@YAJKPEAPEAUHWND__@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(DWORD dwThreadId, HWND__ **phWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006060`
- `0x180006cd8`
- `0x18000737c`
- `0x18000e880`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e932`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18000e926`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18000e926`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000e8b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000e8b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb0c`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x18000e9ab`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x18000e9ab`

## pseudocode

```c
__int64 __fastcall FindCallingThreadImmersiveWindow(DWORD dwThreadId, HWND__ **phWnd)
{
  HANDLE v4; // rax
  void *v5; // rsi
  signed int v6; // eax
  int ApplicationService; // edi
  DWORD ProcessIdOfThread; // ebx
  signed int LastError; // eax
  WPP_PROJECT_CONTROL_BLOCK *v10; // rcx
  unsigned __int16 v11; // dx
  Microsoft::WRL::ComPtr<ICallingProcessInfo> *v12; // rax
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *ptr; // rdi
  HRESULT (__fastcall *GetWindowFromThreadId)(Windows::ApplicationModel::Core::ICoreApplicationPrivate *, unsigned int, Windows::UI::Core::ICoreWindow **); // rbx
  Windows::UI::Core::ICoreWindow *v15; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  WPP_PROJECT_CONTROL_BLOCK *v17; // rcx
  unsigned __int16 v18; // dx
  Microsoft::WRL::ComPtr<ICoreWindowInterop> spCoreWinInterop; // [rsp+58h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow> spCoreWindow; // [rsp+60h] [rbp+40h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> spCoreAppPrivate; // [rsp+68h] [rbp+48h] BYREF

  *phWnd = 0;
  spCoreAppPrivate.ptr_ = 0;
  spCoreWindow.ptr_ = 0;
  v4 = OpenThread(0x40u, 0, dwThreadId);
  v5 = v4;
  if ( v4 )
  {
    ProcessIdOfThread = GetProcessIdOfThread(v4);
    if ( !ProcessIdOfThread )
    {
      LastError = GetLastError();
      ApplicationService = LastError;
      if ( LastError > 0 )
        ApplicationService = (unsigned __int16)LastError | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $exit;
      }
      v11 = 11;
LABEL_15:
      WPP_SF_d(v10[1].Control.Logger, v11, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids, ApplicationService);
$exit:
      CloseHandle(v5);
      goto LABEL_40;
    }
    v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICallingProcessInfo> >)&spCoreAppPrivate);
    ApplicationService = CoreQueryApplicationService(
                           ProcessIdOfThread,
                           &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
                           &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
                           v12);
    if ( ApplicationService < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $exit;
      }
      v11 = 12;
      goto LABEL_15;
    }
    ptr = spCoreAppPrivate.ptr_;
    GetWindowFromThreadId = spCoreAppPrivate.ptr_->GetWindowFromThreadId;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCoreWindow);
    ApplicationService = GetWindowFromThreadId(ptr, dwThreadId, &spCoreWindow.ptr_);
    if ( ApplicationService < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $exit;
      }
      v11 = 13;
      goto LABEL_15;
    }
    v15 = spCoreWindow.ptr_;
    if ( !spCoreWindow.ptr_ )
      goto $exit;
    spCoreWinInterop.ptr_ = 0;
    QueryInterface = spCoreWindow.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCoreWinInterop);
    ApplicationService = QueryInterface(
                           v15,
                           &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f,
                           (void **)&spCoreWinInterop.ptr_);
    if ( ApplicationService >= 0 )
    {
      ApplicationService = spCoreWinInterop.ptr_->get_WindowHandle(spCoreWinInterop.ptr_, phWnd);
      if ( ApplicationService >= 0 )
        goto LABEL_38;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_38;
      }
      v18 = 15;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_38;
      }
      v18 = 14;
    }
    WPP_SF_d(v17[1].Control.Logger, v18, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids, ApplicationService);
LABEL_38:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCoreWinInterop);
    goto $exit;
  }
  v6 = GetLastError();
  ApplicationService = v6;
  if ( v6 > 0 )
    ApplicationService = (unsigned __int16)v6 | 0x80070000;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Control.Logger,
      0xAu,
      WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids,
      ApplicationService);
  }
LABEL_40:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCoreWindow);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCoreAppPrivate);
  return (unsigned int)ApplicationService;
}

```

## disassembly

```asm
0x18000e880  mov     [rsp-28h+arg_0], rbx
0x18000e885  push    rbp
0x18000e886  push    rsi
0x18000e887  push    rdi
0x18000e888  push    r14
0x18000e88a  push    r15
0x18000e88c  mov     rbp, rsp
0x18000e88f  sub     rsp, 20h
0x18000e893  mov     r15, phWnd
0x18000e896  mov     qword ptr [phWnd], 0
0x18000e89d  xor     edx, edx; bInheritHandle
0x18000e89f  mov     [rbp+spCoreAppPrivate.ptr_], 0
0x18000e8a7  mov     r14d, dwThreadId
0x18000e8aa  mov     [rbp+spCoreWindow.ptr_], 0
0x18000e8b2  mov     r8d, dwThreadId; dwThreadId
0x18000e8b5  lea     dwThreadId, [phWnd+40h]; dwDesiredAccess
0x18000e8b8  call    cs:__imp_OpenThread
0x18000e8be  mov     rsi, rax
0x18000e8c1  test    rax, rax
0x18000e8c4  jnz     short loc_18000E923
0x18000e8c6  call    cs:__imp_GetLastError
0x18000e8cc  mov     edi, eax
0x18000e8ce  test    eax, eax
0x18000e8d0  jle     short loc_18000E8DB
0x18000e8d2  movzx   edi, ax
0x18000e8d5  or      edi, 80070000h
0x18000e8db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000e8e2  lea     rax, WPP_GLOBAL_Control
0x18000e8e9  cmp     rcx, rax
0x18000e8ec  jz      loc_18000EB12
0x18000e8f2  test    byte ptr [rcx+44h], 8
0x18000e8f6  jz      loc_18000EB12
0x18000e8fc  cmp     byte ptr [rcx+41h], 2
0x18000e900  jb      loc_18000EB12
0x18000e906  mov     rcx, [rcx+38h]; Logger
0x18000e90a  lea     r8, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids; TraceGuid
0x18000e911  mov     edx, 0Ah; id
0x18000e916  mov     r9d, edi; _a1
0x18000e919  call    WPP_SF_d
0x18000e91e  jmp     loc_18000EB12
0x18000e923  mov     rcx, rsi; Thread
0x18000e926  call    cs:__imp_GetProcessIdOfThread
0x18000e92c  mov     ebx, eax
0x18000e92e  test    eax, eax
0x18000e930  jnz     short loc_18000E98F
0x18000e932  call    cs:__imp_GetLastError
0x18000e938  mov     edi, eax
0x18000e93a  test    eax, eax
0x18000e93c  jle     short loc_18000E947
0x18000e93e  movzx   edi, ax
0x18000e941  or      edi, 80070000h
0x18000e947  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000e94e  lea     rax, WPP_GLOBAL_Control
0x18000e955  cmp     rcx, rax
0x18000e958  jz      $exit
0x18000e95e  test    byte ptr [rcx+44h], 8
0x18000e962  jz      $exit
0x18000e968  cmp     byte ptr [rcx+41h], 2
0x18000e96c  jb      $exit
0x18000e972  mov     edx, 0Bh; id
0x18000e977  mov     rcx, [rcx+38h]; Logger
0x18000e97b  lea     r8, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids; TraceGuid
0x18000e982  mov     r9d, edi; _a1
0x18000e985  call    WPP_SF_d
0x18000e98a  jmp     $exit
0x18000e98f  lea     rcx, [rbp+spCoreAppPrivate]; pp
0x18000e993  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UICoreApplicationPrivate@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UICoreApplicationPrivate@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate>>)
0x18000e998  mov     r9, rax
0x18000e99b  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x18000e9a2  lea     phWnd, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18000e9a9  mov     dwThreadId, ebx
0x18000e9ab  call    cs:__imp_CoreQueryApplicationService
0x18000e9b1  mov     edi, eax
0x18000e9b3  test    eax, eax
0x18000e9b5  jns     short loc_18000E9E9
0x18000e9b7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000e9be  lea     rax, WPP_GLOBAL_Control
0x18000e9c5  cmp     rcx, rax
0x18000e9c8  jz      $exit
0x18000e9ce  test    byte ptr [rcx+44h], 8
0x18000e9d2  jz      $exit
0x18000e9d8  cmp     byte ptr [rcx+41h], 2
0x18000e9dc  jb      $exit
0x18000e9e2  mov     edx, 0Ch
0x18000e9e7  jmp     short loc_18000E977
0x18000e9e9  mov     rdi, [rbp+spCoreAppPrivate.ptr_]
0x18000e9ed  lea     rcx, [rbp+spCoreWindow]; this
0x18000e9f1  mov     rax, [rdi]
0x18000e9f4  mov     rbx, [rax+40h]
0x18000e9f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e9fd  lea     r8, [rbp+spCoreWindow]
0x18000ea01  mov     edx, r14d
0x18000ea04  mov     rcx, rdi
0x18000ea07  mov     rax, rbx
0x18000ea0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea0f  mov     edi, eax
0x18000ea11  test    eax, eax
0x18000ea13  jns     short loc_18000EA4A
0x18000ea15  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ea1c  lea     rax, WPP_GLOBAL_Control
0x18000ea23  cmp     rcx, rax
0x18000ea26  jz      $exit
0x18000ea2c  test    byte ptr [rcx+44h], 8
0x18000ea30  jz      $exit
0x18000ea36  cmp     byte ptr [rcx+41h], 2
0x18000ea3a  jb      $exit
0x18000ea40  mov     edx, 0Dh
0x18000ea45  jmp     loc_18000E977
0x18000ea4a  mov     rbx, [rbp+spCoreWindow.ptr_]
0x18000ea4e  test    rbx, rbx
0x18000ea51  jz      $exit
0x18000ea57  mov     [rbp+spCoreWinInterop.ptr_], 0
0x18000ea5f  lea     rcx, [rbp+spCoreWinInterop]; this
0x18000ea63  mov     rax, [rbx]
0x18000ea66  mov     rdi, [rax]
0x18000ea69  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ea6e  lea     r8, [rbp+spCoreWinInterop]
0x18000ea72  mov     rcx, rbx
0x18000ea75  lea     phWnd, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x18000ea7c  mov     rax, rdi
0x18000ea7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea84  mov     edi, eax
0x18000ea86  test    eax, eax
0x18000ea88  jns     short loc_18000EAB0
0x18000ea8a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ea91  lea     rax, WPP_GLOBAL_Control
0x18000ea98  cmp     rcx, rax
0x18000ea9b  jz      short loc_18000EB00
0x18000ea9d  test    byte ptr [rcx+44h], 8
0x18000eaa1  jz      short loc_18000EB00
0x18000eaa3  cmp     byte ptr [rcx+41h], 2
0x18000eaa7  jb      short loc_18000EB00
0x18000eaa9  mov     edx, 0Eh
0x18000eaae  jmp     short loc_18000EAED
0x18000eab0  mov     rcx, [rbp+spCoreWinInterop.ptr_]
0x18000eab4  mov     phWnd, r15
0x18000eab7  mov     rax, [rcx]
0x18000eaba  mov     rax, [rax+18h]
0x18000eabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eac3  mov     edi, eax
0x18000eac5  test    eax, eax
0x18000eac7  jns     short loc_18000EB00
0x18000eac9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ead0  lea     rax, WPP_GLOBAL_Control
0x18000ead7  cmp     rcx, rax
0x18000eada  jz      short loc_18000EB00
0x18000eadc  test    byte ptr [rcx+44h], 8
0x18000eae0  jz      short loc_18000EB00
0x18000eae2  cmp     byte ptr [rcx+41h], 2
0x18000eae6  jb      short loc_18000EB00
0x18000eae8  mov     edx, 0Fh; id
0x18000eaed  mov     rcx, [rcx+38h]; Logger
0x18000eaf1  lea     r8, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids; TraceGuid
0x18000eaf8  mov     r9d, edi; _a1
0x18000eafb  call    WPP_SF_d
0x18000eb00  lea     rcx, [rbp+spCoreWinInterop]; this
0x18000eb04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eb09  mov     rcx, rsi; hObject
0x18000eb0c  call    cs:__imp_CloseHandle
0x18000eb12  lea     rcx, [rbp+spCoreWindow]; this
0x18000eb16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eb1b  lea     rcx, [rbp+spCoreAppPrivate]; this
0x18000eb1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eb24  mov     rbx, [rsp+20h+arg_0]
0x18000eb29  mov     eax, edi
0x18000eb2b  add     rsp, 20h
0x18000eb2f  pop     r15
0x18000eb31  pop     r14
0x18000eb33  pop     rdi
0x18000eb34  pop     rsi
0x18000eb35  pop     rbp
0x18000eb36  retn
```
