# CWorkflowAppSession::LaunchWorkflowUIWithoutMem(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001f200`
- end: `0x18001f408`
- name: `?LaunchWorkflowUIWithoutMem@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `520`
- prototype: `__int64 __fastcall(CWorkflowAppSession *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eaf8`

## callees

- `0x180001314`
- `0x180001614`
- `0x18000a128`
- `0x180010b0c`
- `0x180012bf8`
- `0x1800166a8`
- `0x18001ecd8`
- `0x18001f200`
- `0x180020d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f35c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f285`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f285`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001f330`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001f330`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001f2ce`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001f2ce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001f317`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001f317`

## string_xrefs

- `0x18001f39b`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001f3c1`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWorkflowAppSession::LaunchWorkflowUIWithoutMem(
        CWorkflowModalExperienceManagerAppListener **this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HANDLE v7; // rbx
  DWORD v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // edi
  DWORD v12; // ebx
  signed int LastError; // eax
  int v14; // eax
  CWorkflowModalExperienceManagerAppListener *v15; // rcx
  int dwCreationFlags; // [rsp+20h] [rbp-50h]
  DWORD ExitCode; // [rsp+30h] [rbp-40h] BYREF
  void *v19; // [rsp+38h] [rbp-38h] BYREF
  HANDLE v20; // [rsp+40h] [rbp-30h] BYREF
  HANDLE Handles[2]; // [rsp+48h] [rbp-28h] BYREF
  void *Parameter; // [rsp+58h] [rbp-18h] BYREF
  HWND hWnd[2]; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)&byte_180071E67,
      0);
  v19 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v19,
    1);
  Parameter = v19;
  *(_OWORD *)hWnd = 0;
  v7 = CreateThread(0, 0, CWorkflowAppSession::MemParentHostThreadProc, &Parameter, 0, 0);
  v20 = v7;
  Handles[0] = Parameter;
  Handles[1] = v7;
  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)qword_180071E10,
      0);
  v8 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  v11 = v8;
  if ( (unsigned int)dword_180083038 > 5 )
  {
    ExitCode = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180083038,
      (__int64)&word_180071DAE,
      v9,
      v10,
      (__int64)&ExitCode);
  }
  if ( !v11 )
  {
    v14 = CWorkflowAppSession::LaunchWorkflowUIWithMem((CWorkflowAppSession *)this, a3, a4);
    v12 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
        (const char *)(unsigned int)v14,
        dwCreationFlags);
      goto LABEL_24;
    }
    v15 = this[12];
    if ( v15 )
    {
      CWorkflowModalExperienceManagerAppListener::SetViewClosedEvent(v15, hWnd[1]);
      v12 = 0;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationFlags);
    goto LABEL_22;
  }
  if ( hWnd[0] )
    PostMessageW(hWnd[0], 0x10u, 0, 0);
  if ( v11 == 1 )
  {
    ExitCode = 0;
    if ( GetExitCodeThread(v7, &ExitCode) )
    {
      v12 = ExitCode;
      if ( (int)ExitCode > 0 )
        v12 = (unsigned __int16)ExitCode | 0x80070000;
      goto LABEL_24;
    }
LABEL_22:
    v12 = -2147418113;
    goto LABEL_24;
  }
  if ( v11 != -1 )
    goto LABEL_22;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v12 = LastError;
LABEL_24:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  return v12;
}

```

## disassembly

```asm
0x18001f200  push    rbp
0x18001f202  push    rbx
0x18001f203  push    rsi
0x18001f204  push    rdi
0x18001f205  push    r12
0x18001f207  push    r14
0x18001f209  push    r15
0x18001f20b  mov     rbp, rsp
0x18001f20e  sub     rsp, 70h
0x18001f212  mov     r14, r9
0x18001f215  mov     r15, r8
0x18001f218  mov     r12, rdx
0x18001f21b  mov     rsi, rcx
0x18001f21e  mov     eax, cs:dword_180083038
0x18001f224  cmp     eax, 5
0x18001f227  jbe     short loc_18001F23F
0x18001f229  xor     r8d, r8d
0x18001f22c  lea     rdx, byte_180071E67
0x18001f233  lea     rcx, dword_180083038
0x18001f23a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f23f  mov     [rbp+var_38], 0
0x18001f247  mov     edx, 1
0x18001f24c  lea     rcx, [rbp+var_38]
0x18001f250  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001f255  mov     rax, [rbp+var_38]
0x18001f259  mov     [rbp+Parameter], rax
0x18001f25d  xorps   xmm0, xmm0
0x18001f260  movdqu  xmmword ptr [rbp+hWnd], xmm0
0x18001f265  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x18001f26e  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x18001f276  lea     r9, [rbp+Parameter]; lpParameter
0x18001f27a  lea     r8, ?MemParentHostThreadProc@CWorkflowAppSession@@SAKPEAX@Z; lpStartAddress
0x18001f281  xor     edx, edx; dwStackSize
0x18001f283  xor     ecx, ecx; lpThreadAttributes
0x18001f285  call    cs:__imp_CreateThread
0x18001f28b  mov     rbx, rax
0x18001f28e  mov     [rbp+var_30], rax
0x18001f292  mov     rax, [rbp+Parameter]
0x18001f296  mov     [rbp+Handles], rax
0x18001f29a  mov     [rbp+var_20], rbx
0x18001f29e  mov     eax, cs:dword_180083038
0x18001f2a4  cmp     eax, 5
0x18001f2a7  jbe     short loc_18001F2BF
0x18001f2a9  xor     r8d, r8d
0x18001f2ac  lea     rdx, qword_180071E10
0x18001f2b3  lea     rcx, dword_180083038
0x18001f2ba  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001f2bf  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001f2c3  xor     r8d, r8d; bWaitAll
0x18001f2c6  lea     rdx, [rbp+Handles]; lpHandles
0x18001f2ca  lea     ecx, [r8+2]; nCount
0x18001f2ce  call    cs:__imp_WaitForMultipleObjects
0x18001f2d4  mov     edi, eax
0x18001f2d6  mov     edx, cs:dword_180083038
0x18001f2dc  cmp     edx, 5
0x18001f2df  jbe     short loc_18001F300
0x18001f2e1  mov     [rbp+ExitCode], eax
0x18001f2e4  lea     rax, [rbp+ExitCode]
0x18001f2e8  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x18001f2ed  lea     rdx, word_180071DAE
0x18001f2f4  lea     rcx, dword_180083038
0x18001f2fb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f300  test    edi, edi
0x18001f302  jz      short loc_18001F372
0x18001f304  mov     rcx, [rbp+hWnd]; hWnd
0x18001f308  test    rcx, rcx
0x18001f30b  jz      short loc_18001F31D
0x18001f30d  xor     r9d, r9d; lParam
0x18001f310  xor     r8d, r8d; wParam
0x18001f313  lea     edx, [r9+10h]; Msg
0x18001f317  call    cs:__imp_PostMessageW
0x18001f31d  cmp     edi, 1
0x18001f320  jnz     short loc_18001F357
0x18001f322  mov     [rbp+ExitCode], 0
0x18001f329  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18001f32d  mov     rcx, rbx; hThread
0x18001f330  call    cs:__imp_GetExitCodeThread
0x18001f336  test    eax, eax
0x18001f338  jz      loc_18001F3D2
0x18001f33e  mov     ebx, [rbp+ExitCode]
0x18001f341  test    ebx, ebx
0x18001f343  jle     loc_18001F3E4
0x18001f349  movzx   ebx, bx
0x18001f34c  or      ebx, 80070000h
0x18001f352  jmp     loc_18001F3E4
0x18001f357  cmp     edi, 0FFFFFFFFh
0x18001f35a  jnz     short loc_18001F3D2
0x18001f35c  call    cs:__imp_GetLastError
0x18001f362  test    eax, eax
0x18001f364  jle     short loc_18001F36E
0x18001f366  movzx   eax, ax
0x18001f369  or      eax, 80070000h
0x18001f36e  mov     ebx, eax
0x18001f370  jmp     short loc_18001F3E4
0x18001f372  mov     [rsp+70h+lpThreadId], r14; __int64
0x18001f377  mov     qword ptr [rsp+70h+dwCreationFlags], r15; int
0x18001f37c  xor     r9d, r9d
0x18001f37f  mov     r8, [rbp+hWnd]
0x18001f383  mov     rdx, r12
0x18001f386  mov     rcx, rsi; this
0x18001f389  call    ?LaunchWorkflowUIWithMem@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@_KEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; CWorkflowAppSession::LaunchWorkflowUIWithMem(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,unsigned __int64,uchar,std::wstring const &,std::wstring const &)
0x18001f38e  mov     ebx, eax
0x18001f390  test    eax, eax
0x18001f392  jns     short loc_18001F3AE
0x18001f394  mov     rcx, [rbp+38h]; this
0x18001f398  mov     r9d, eax; char *
0x18001f39b  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001f3a2  mov     edx, 2EFh; void *
0x18001f3a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3ac  jmp     short loc_18001F3E4
0x18001f3ae  mov     rcx, [rsi+60h]; this
0x18001f3b2  test    rcx, rcx
0x18001f3b5  jnz     short loc_18001F3D9
0x18001f3b7  mov     rcx, [rbp+38h]; this
0x18001f3bb  mov     r9d, 8000FFFFh; char *
0x18001f3c1  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001f3c8  mov     edx, 2F1h; void *
0x18001f3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3d2  mov     ebx, 8000FFFFh
0x18001f3d7  jmp     short loc_18001F3E4
0x18001f3d9  mov     rdx, [rbp+hWnd+8]; void *
0x18001f3dd  call    ?SetViewClosedEvent@CWorkflowModalExperienceManagerAppListener@@QEAAJPEAX@Z; CWorkflowModalExperienceManagerAppListener::SetViewClosedEvent(void *)
0x18001f3e2  xor     ebx, ebx
0x18001f3e4  lea     rcx, [rbp+var_30]
0x18001f3e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f3ed  nop
0x18001f3ee  lea     rcx, [rbp+var_38]
0x18001f3f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f3f7  mov     eax, ebx
0x18001f3f9  add     rsp, 70h
0x18001f3fd  pop     r15
0x18001f3ff  pop     r14
0x18001f401  pop     r12
0x18001f403  pop     rdi
0x18001f404  pop     rsi
0x18001f405  pop     rbx
0x18001f406  pop     rbp
0x18001f407  retn
```
