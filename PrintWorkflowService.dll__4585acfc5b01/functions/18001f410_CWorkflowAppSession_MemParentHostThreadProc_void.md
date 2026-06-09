# CWorkflowAppSession::MemParentHostThreadProc(void *)

- ea: `0x18001f410`
- end: `0x18001f69c`
- name: `?MemParentHostThreadProc@CWorkflowAppSession@@SAKPEAX@Z`
- size: `652`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001314`
- `0x180001614`
- `0x180003ca0`
- `0x18000495c`
- `0x18000a128`
- `0x180012bf8`
- `0x180014950`
- `0x18001f410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f59f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f59f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18001f5f3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18001f5f3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18001f60f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18001f60f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001f5e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001f5e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18001f516`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18001f516`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18001f669`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18001f669`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18001f575`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18001f575`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001f563`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001f563`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x18001f4ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkflowAppSession::MemParentHostThreadProc(HANDLE *Parameter)
{
  HWND Window; // rax
  HWND v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  void *v7; // [rsp+60h] [rbp-A0h] BYREF
  UINT message; // [rsp+68h] [rbp-98h] BYREF
  MSG Msg; // [rsp+70h] [rbp-90h] BYREF
  WNDCLASSEXW v10; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v11; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v12[2]; // [rsp+100h] [rbp+0h]

  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)&word_180072006,
      0);
  if ( !Parameter || !*Parameter || Parameter[2] )
    return 160;
  v7 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v7,
    1);
  if ( v7 )
  {
    Parameter[2] = v7;
    v11 = *(_OWORD *)L"Print_WorkflowParent";
    v12[0] = *(_OWORD *)L"rkflowParent";
    *(_OWORD *)((char *)v12 + 10) = *(_OWORD *)L"wParent";
    v10.cbSize = 80;
    memset_0(&v10.style, 0, 0x4Cu);
    v10.style = 512;
    v10.lpfnWndProc = DefWindowProcW;
    v10.hInstance = &_ImageBase;
    v10.lpszClassName = (LPCWSTR)&v11;
    v10.cbWndExtra = 8;
    RegisterClassExW(&v10);
    Window = CreateWindowExW(
               0x40000u,
               v10.lpszClassName,
               0,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               0,
               0,
               &_ImageBase,
               0);
    Parameter[1] = Window;
    ShowWindow(Window, 4);
    if ( (unsigned int)dword_180083038 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180083038,
        (__int64)word_180071FB2,
        0);
    v4 = (HWND)Parameter[1];
    SetEvent(*Parameter);
    memset(&Msg, 0, sizeof(Msg));
    do
    {
      while ( PeekMessageW(&Msg, v4, 0, 0, 1u) )
      {
        if ( (unsigned int)dword_180083038 > 5 )
        {
          message = Msg.message;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180083038,
            (__int64)&word_180071F56,
            v5,
            v6,
            (__int64)&message);
        }
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
    while ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                                &v7,
                                200) );
    if ( (unsigned int)dword_180083038 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180083038,
        (__int64)&word_180071EF6,
        0);
    if ( (unsigned int)dword_180083038 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180083038,
        (__int64)&word_180071EA6,
        0);
    DestroyWindow(v4);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v7);
    return 0;
  }
  else
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v7);
    return 14;
  }
}

```

## disassembly

```asm
0x18001f410  push    rbp
0x18001f412  push    rbx
0x18001f413  push    rdi
0x18001f414  push    r14
0x18001f416  lea     rbp, [rsp-38h]
0x18001f41b  sub     rsp, 138h
0x18001f422  mov     rax, cs:__security_cookie
0x18001f429  xor     rax, rsp
0x18001f42c  mov     [rbp+50h+var_30], rax
0x18001f430  mov     rbx, rcx
0x18001f433  mov     eax, cs:dword_180083038
0x18001f439  lea     r14, dword_180083038
0x18001f440  cmp     eax, 5
0x18001f443  jbe     short loc_18001F457
0x18001f445  xor     r8d, r8d
0x18001f448  lea     rdx, word_180072006
0x18001f44f  mov     rcx, r14
0x18001f452  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f457  test    rbx, rbx
0x18001f45a  jz      loc_18001F67E
0x18001f460  cmp     qword ptr [rbx], 0
0x18001f464  jz      loc_18001F67E
0x18001f46a  cmp     qword ptr [rbx+10h], 0
0x18001f46f  jnz     loc_18001F67E
0x18001f475  mov     [rsp+150h+var_F0], 0
0x18001f47e  mov     edx, 1
0x18001f483  lea     rcx, [rsp+150h+var_F0]
0x18001f488  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001f48d  mov     rax, [rsp+150h+var_F0]
0x18001f492  test    rax, rax
0x18001f495  jnz     short loc_18001F4AB
0x18001f497  lea     rcx, [rsp+150h+var_F0]
0x18001f49c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4a1  mov     eax, 0Eh
0x18001f4a6  jmp     loc_18001F683
0x18001f4ab  mov     [rbx+10h], rax
0x18001f4af  movups  xmm0, xmmword ptr cs:aPrintWorkflowp; "Print_WorkflowParent"
0x18001f4b6  movups  [rbp+50h+var_60], xmm0
0x18001f4ba  movups  xmm1, xmmword ptr cs:aPrintWorkflowp+10h; "rkflowParent"
0x18001f4c1  movups  xmmword ptr [rbp+50h+var_50], xmm1
0x18001f4c5  movups  xmm0, xmmword ptr cs:aPrintWorkflowp+1Ah; "wParent"
0x18001f4cc  movups  xmmword ptr [rbp+50h+var_50+0Ah], xmm0
0x18001f4d0  mov     [rbp+50h+var_B0.cbSize], 50h ; 'P'
0x18001f4d7  xor     edx, edx; Val
0x18001f4d9  lea     r8d, [rdx+4Ch]; Size
0x18001f4dd  lea     rcx, [rbp+50h+var_B0.style]; void *
0x18001f4e1  call    memset_0
0x18001f4e6  mov     [rbp+50h+var_B0.style], 200h
0x18001f4ed  mov     rax, cs:__imp_DefWindowProcW
0x18001f4f4  mov     [rbp+50h+var_B0.lpfnWndProc], rax
0x18001f4f8  lea     rdi, __ImageBase
0x18001f4ff  mov     [rbp+50h+var_B0.hInstance], rdi
0x18001f503  lea     rax, [rbp+50h+var_60]
0x18001f507  mov     [rbp+50h+var_B0.lpszClassName], rax
0x18001f50b  mov     [rbp+50h+var_B0.cbWndExtra], 8
0x18001f512  lea     rcx, [rbp+50h+var_B0]; WNDCLASSEXW *
0x18001f516  call    cs:__imp_RegisterClassExW
0x18001f51c  mov     [rsp+150h+lpParam], 0; lpParam
0x18001f525  mov     [rsp+150h+hInstance], rdi; hInstance
0x18001f52a  mov     [rsp+150h+hMenu], 0; hMenu
0x18001f533  mov     [rsp+150h+hWndParent], 0; hWndParent
0x18001f53c  mov     eax, 80000000h
0x18001f541  mov     [rsp+150h+nHeight], eax; nHeight
0x18001f545  mov     [rsp+150h+nWidth], eax; nWidth
0x18001f549  mov     [rsp+150h+Y], eax; Y
0x18001f54d  mov     [rsp+150h+X], eax; X
0x18001f551  mov     r9d, 80000000h; dwStyle
0x18001f557  xor     r8d, r8d; lpWindowName
0x18001f55a  mov     rdx, [rbp+50h+var_B0.lpszClassName]; lpClassName
0x18001f55e  mov     ecx, 40000h; dwExStyle
0x18001f563  call    cs:__imp_CreateWindowExW
0x18001f569  mov     [rbx+8], rax
0x18001f56d  mov     edx, 4; nCmdShow
0x18001f572  mov     rcx, rax; hWnd
0x18001f575  call    cs:__imp_ShowWindow
0x18001f57b  mov     eax, cs:dword_180083038
0x18001f581  cmp     eax, 5
0x18001f584  jbe     short loc_18001F598
0x18001f586  xor     r8d, r8d
0x18001f589  lea     rdx, word_180071FB2
0x18001f590  mov     rcx, r14
0x18001f593  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f598  mov     rdi, [rbx+8]
0x18001f59c  mov     rcx, [rbx]; hEvent
0x18001f59f  call    cs:__imp_SetEvent
0x18001f5a5  xorps   xmm0, xmm0
0x18001f5a8  movups  xmmword ptr [rsp+150h+Msg.hwnd], xmm0
0x18001f5ad  movups  xmmword ptr [rbp+50h+Msg.wParam], xmm0
0x18001f5b1  movups  xmmword ptr [rbp+50h+Msg.time], xmm0
0x18001f5b5  jmp     short loc_18001F5F9
0x18001f5b7  mov     eax, cs:dword_180083038
0x18001f5bd  cmp     eax, 5
0x18001f5c0  jbe     short loc_18001F5E3
0x18001f5c2  mov     eax, [rsp+150h+Msg.message]
0x18001f5c6  mov     [rsp+150h+var_E8], eax
0x18001f5ca  lea     rax, [rsp+150h+var_E8]
0x18001f5cf  mov     qword ptr [rsp+150h+X], rax
0x18001f5d4  lea     rdx, word_180071F56
0x18001f5db  mov     rcx, r14
0x18001f5de  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f5e3  lea     rcx, [rsp+150h+Msg]; lpMsg
0x18001f5e8  call    cs:__imp_TranslateMessage
0x18001f5ee  lea     rcx, [rsp+150h+Msg]; lpMsg
0x18001f5f3  call    cs:__imp_DispatchMessageW
0x18001f5f9  mov     [rsp+150h+X], 1; wRemoveMsg
0x18001f601  xor     r9d, r9d; wMsgFilterMax
0x18001f604  xor     r8d, r8d; wMsgFilterMin
0x18001f607  mov     rdx, rdi; hWnd
0x18001f60a  lea     rcx, [rsp+150h+Msg]; lpMsg
0x18001f60f  call    cs:__imp_PeekMessageW
0x18001f615  test    eax, eax
0x18001f617  jnz     short loc_18001F5B7
0x18001f619  mov     edx, 0C8h
0x18001f61e  lea     rcx, [rsp+150h+var_F0]
0x18001f623  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18001f628  test    al, al
0x18001f62a  jz      short loc_18001F5F9
0x18001f62c  mov     eax, cs:dword_180083038
0x18001f632  cmp     eax, 5
0x18001f635  jbe     short loc_18001F649
0x18001f637  xor     r8d, r8d
0x18001f63a  lea     rdx, word_180071EF6
0x18001f641  mov     rcx, r14
0x18001f644  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f649  mov     eax, cs:dword_180083038
0x18001f64f  cmp     eax, 5
0x18001f652  jbe     short loc_18001F666
0x18001f654  xor     r8d, r8d
0x18001f657  lea     rdx, word_180071EA6
0x18001f65e  mov     rcx, r14
0x18001f661  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f666  mov     rcx, rdi; hWnd
0x18001f669  call    cs:__imp_DestroyWindow
0x18001f66f  nop
0x18001f670  lea     rcx, [rsp+150h+var_F0]
0x18001f675  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f67a  xor     eax, eax
0x18001f67c  jmp     short loc_18001F683
0x18001f67e  mov     eax, 0A0h
0x18001f683  mov     rcx, [rbp+50h+var_30]
0x18001f687  xor     rcx, rsp; StackCookie
0x18001f68a  call    __security_check_cookie
0x18001f68f  add     rsp, 138h
0x18001f696  pop     r14
0x18001f698  pop     rdi
0x18001f699  pop     rbx
0x18001f69a  pop     rbp
0x18001f69b  retn
```
