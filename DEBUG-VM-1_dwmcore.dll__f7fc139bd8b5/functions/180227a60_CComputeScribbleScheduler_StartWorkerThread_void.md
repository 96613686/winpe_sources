# CComputeScribbleScheduler::StartWorkerThread(void)

- ea: `0x180227a60`
- end: `0x180227b9b`
- name: `?StartWorkerThread@CComputeScribbleScheduler@@AEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(CComputeScribbleScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802545b4`

## callees

- `0x1800088dc`
- `0x1800096c4`
- `0x1800098f8`
- `0x18000a7f4`
- `0x180042854`
- `0x1802004e0`
- `0x180227a60`
- `0x180231ddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180227b45`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180227b45`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180227b38`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180227b38`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180227adf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180227adf`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180227b0d`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180227b0d`

## string_xrefs

- `0x180227a8b`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x180227b1c`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x180227b76`: `onecoreuap\windows\dwm\dwmcore\rendering\global\computescribblescheduler.cpp`
- `0x180227b03`: `D3D12 Compute Scribble`

## pseudocode

```c
__int64 __fastcall CComputeScribbleScheduler::StartWorkerThread(CComputeScribbleScheduler *this)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  __int64 v3; // rdx
  HANDLE Thread; // rax
  const char *v5; // r9
  HANDLE v6; // rbx
  __int64 v7; // rdx
  HRESULT v8; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE hThread; // [rsp+40h] [rbp+8h] BYREF

  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 72, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v3 = 475;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      dwCreationFlags);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 80, 0);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v3 = 478;
    goto LABEL_3;
  }
  hThread = 0;
  Thread = CreateThread(
             0,
             0,
             CComputeScribbleScheduler::StartWorkerThread_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
             this,
             4u,
             0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hThread,
    Thread);
  v6 = hThread;
  if ( hThread )
  {
    v8 = SetThreadDescription(hThread, L"D3D12 Compute Scribble");
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp",
        (const char *)(unsigned int)v8,
        dwCreationFlagsa);
    if ( SetThreadPriority(v6, 2) && ResumeThread(v6) != -1 )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        (char *)this + 64,
        &hThread);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
      return 0;
    }
    v7 = 503;
  }
  else
  {
    v7 = 492;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\rendering\\global\\computescribblescheduler.cpp", v5);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
  return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
}

```

## disassembly

```asm
0x180227a60  mov     [rsp+arg_8], rbx
0x180227a65  push    rdi
0x180227a66  sub     rsp, 30h
0x180227a6a  mov     rdi, rcx
0x180227a6d  mov     edx, 1
0x180227a72  add     rcx, 48h ; 'H'
0x180227a76  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180227a7b  mov     ebx, eax
0x180227a7d  test    eax, eax
0x180227a7f  jns     short loc_180227A9F
0x180227a81  mov     edx, 1DBh; void *
0x180227a86  mov     rcx, [rsp+38h]; this
0x180227a8b  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x180227a92  mov     r9d, ebx; char *
0x180227a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180227a9a  jmp     loc_180227B8E
0x180227a9f  lea     rcx, [rdi+50h]
0x180227aa3  xor     edx, edx
0x180227aa5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180227aaa  mov     ebx, eax
0x180227aac  test    eax, eax
0x180227aae  jns     short loc_180227AB7
0x180227ab0  mov     edx, 1DEh
0x180227ab5  jmp     short loc_180227A86
0x180227ab7  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180227ac0  lea     r8, _CComputeScribbleScheduler__StartWorkerThread____2____lambda_1____lambda_invoker_cdecl_; lpStartAddress
0x180227ac7  mov     r9, rdi; lpParameter
0x180227aca  mov     [rsp+38h+dwCreationFlags], 4; int
0x180227ad2  xor     edx, edx; dwStackSize
0x180227ad4  mov     [rsp+38h+hThread], 0
0x180227add  xor     ecx, ecx; lpThreadAttributes
0x180227adf  call    cs:__imp_CreateThread
0x180227ae5  mov     rdx, rax
0x180227ae8  lea     rcx, [rsp+38h+hThread]
0x180227aed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180227af2  mov     rbx, [rsp+38h+hThread]
0x180227af7  test    rbx, rbx
0x180227afa  jnz     short loc_180227B03
0x180227afc  mov     edx, 1ECh
0x180227b01  jmp     short loc_180227B71
0x180227b03  lea     rdx, aD3d12ComputeSc; "D3D12 Compute Scribble"
0x180227b0a  mov     rcx, rbx; hThread
0x180227b0d  call    cs:__imp_SetThreadDescription
0x180227b13  test    eax, eax
0x180227b15  jns     short loc_180227B30
0x180227b17  mov     rcx, [rsp+38h]; this
0x180227b1c  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x180227b23  mov     r9d, eax; char *
0x180227b26  mov     edx, 1EFh; void *
0x180227b2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180227b30  mov     edx, 2; nPriority
0x180227b35  mov     rcx, rbx; hThread
0x180227b38  call    cs:__imp_SetThreadPriority
0x180227b3e  test    eax, eax
0x180227b40  jz      short loc_180227B6C
0x180227b42  mov     rcx, rbx; hThread
0x180227b45  call    cs:__imp_ResumeThread
0x180227b4b  cmp     eax, 0FFFFFFFFh
0x180227b4e  jz      short loc_180227B6C
0x180227b50  lea     rcx, [rdi+40h]
0x180227b54  lea     rdx, [rsp+38h+hThread]
0x180227b59  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180227b5e  lea     rcx, [rsp+38h+hThread]
0x180227b63  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180227b68  xor     eax, eax
0x180227b6a  jmp     short loc_180227B90
0x180227b6c  mov     edx, 1F7h; void *
0x180227b71  mov     rcx, [rsp+38h]; this
0x180227b76  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\dwmcore\\rend"...
0x180227b7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180227b82  lea     rcx, [rsp+38h+hThread]
0x180227b87  mov     ebx, eax
0x180227b89  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180227b8e  mov     eax, ebx
0x180227b90  mov     rbx, [rsp+38h+arg_8]
0x180227b95  add     rsp, 30h
0x180227b99  pop     rdi
0x180227b9a  retn
```
