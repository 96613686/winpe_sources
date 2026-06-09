# RetailDemoUserAgent::ConnectToAutoMsa(unsigned __int64)

- ea: `0x180039fa0`
- end: `0x18003a1b5`
- name: `?ConnectToAutoMsa@RetailDemoUserAgent@@UEAAJ_K@Z`
- size: `533`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006d4c`
- `0x180008bbc`
- `0x18000aa7c`
- `0x180025cd8`
- `0x1800325d0`
- `0x180034c20`
- `0x1800365f8`
- `0x180039fa0`
- `0x18003e048`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003a144`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003a144`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a111`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039ff8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039ff8`

## string_xrefs

- `0x18003a00b`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003a052`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RetailDemoUserAgent::ConnectToAutoMsa(HANDLE *this, void *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  HRESULT v6; // eax
  unsigned int Error; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  LPVOID v16; // rdi
  __int64 (__fastcall *v17)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int ppv; // [rsp+20h] [rbp-50h]
  void *v30; // [rsp+30h] [rbp-40h] BYREF
  __int64 v31; // [rsp+38h] [rbp-38h] BYREF
  int v32; // [rsp+40h] [rbp-30h]
  HANDLE Handles[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h] BYREF
  int v35; // [rsp+60h] [rbp-10h]
  char v36; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v38; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v39; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID v40; // [rsp+B8h] [rbp+48h] BYREF

  v30 = a2;
  if ( !(unsigned __int8)IsMsaDefaultAccount() )
  {
    v40 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v4, v5);
    v6 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v40);
    Error = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7DE,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v6,
        ppv);
LABEL_19:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v8, v9);
      goto LABEL_16;
    }
    v39 = 0;
    v38 = 0;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 8, 1, 0);
    Error = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v13 = 2020;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        ppv);
LABEL_18:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v14, v15);
      goto LABEL_19;
    }
    v16 = v40;
    v17 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v40 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v11, v12);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v17(v16, &IID_IImmersiveApplicationNotificationService, &GUID_7860c098_fb29_49aa_a512_adacc0ffee84, &v39);
    Error = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v13 = 2021;
      goto LABEL_6;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v39 + 24LL))(v39, (unsigned __int64)(this + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)(this - 9) >> 64), &v38);
    Error = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v13 = 2022;
      goto LABEL_6;
    }
    v20 = v39;
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    v32 = v38;
    v34 = v20;
    v31 = 0;
    v35 = v38;
    v36 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31, v18, v19);
    CurrentThreadId = GetCurrentThreadId();
    Windows::Internal::ComTaskPool::QueueTask__lambda_a63a45bce6f319689b2cff365b7d75bc___(v23, v22, CurrentThreadId);
    Handles[0] = a2;
    Handles[1] = this[8];
    if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0x7530u, 0) == -1 )
    {
      Error = ResultFromKnownLastError();
      wil::details::ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___::_ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___(&v34);
      goto LABEL_18;
    }
    wil::details::ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___::_ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v24, v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v26, v27);
  }
  Error = 0;
LABEL_16:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
  return Error;
}

```

## disassembly

```asm
0x180039fa0  mov     [rsp-28h+arg_0], rbx
0x180039fa5  push    rbp
0x180039fa6  push    rsi
0x180039fa7  push    rdi
0x180039fa8  push    r14
0x180039faa  push    r15
0x180039fac  mov     rbp, rsp
0x180039faf  sub     rsp, 70h
0x180039fb3  mov     r14, rdx
0x180039fb6  mov     rsi, rcx
0x180039fb9  mov     [rbp+var_40], rdx
0x180039fbd  call    IsMsaDefaultAccount
0x180039fc2  test    al, al
0x180039fc4  jnz     loc_18003A16C
0x180039fca  mov     [rbp+arg_18], 0
0x180039fd2  lea     rcx, [rbp+arg_18]
0x180039fd6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039fdb  lea     rax, [rbp+arg_18]
0x180039fdf  mov     qword ptr [rsp+70h+ppv], rax; int
0x180039fe4  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180039feb  xor     edx, edx; pUnkOuter
0x180039fed  lea     r8d, [rdx+4]; dwClsContext
0x180039ff1  lea     rcx, CLSID_ImmersiveShell; rclsid
0x180039ff8  call    cs:__imp_CoCreateInstance
0x180039ffe  mov     ebx, eax
0x18003a000  test    eax, eax
0x18003a002  jns     short loc_18003A021
0x18003a004  mov     rcx, [rbp+28h]; this
0x18003a008  mov     r9d, eax; char *
0x18003a00b  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003a012  mov     edx, 7DEh; void *
0x18003a017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a01c  jmp     loc_18003A1A9
0x18003a021  mov     [rbp+arg_10], 0
0x18003a029  mov     [rbp+arg_8], 0
0x18003a030  xor     r8d, r8d
0x18003a033  lea     edx, [r8+1]
0x18003a037  lea     rcx, [rsi+40h]
0x18003a03b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003a040  mov     ebx, eax
0x18003a042  test    eax, eax
0x18003a044  jns     short loc_18003A063
0x18003a046  mov     edx, 7E4h; void *
0x18003a04b  mov     rcx, [rbp+28h]; this
0x18003a04f  mov     r9d, eax; char *
0x18003a052  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003a059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a05e  jmp     loc_18003A19F
0x18003a063  mov     rdi, [rbp+arg_18]
0x18003a067  mov     rax, [rdi]
0x18003a06a  mov     rbx, [rax+18h]
0x18003a06e  lea     rcx, [rbp+arg_10]
0x18003a072  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a077  lea     r9, [rbp+arg_10]
0x18003a07b  lea     r8, _GUID_7860c098_fb29_49aa_a512_adacc0ffee84
0x18003a082  lea     rdx, IID_IImmersiveApplicationNotificationService
0x18003a089  mov     rcx, rdi
0x18003a08c  mov     rax, rbx
0x18003a08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a094  mov     ebx, eax
0x18003a096  test    eax, eax
0x18003a098  jns     short loc_18003A0A1
0x18003a09a  mov     edx, 7E5h
0x18003a09f  jmp     short loc_18003A04B
0x18003a0a1  mov     rcx, [rbp+arg_10]
0x18003a0a5  mov     r9, [rcx]
0x18003a0a8  lea     rax, [rsi-48h]
0x18003a0ac  lea     r8, [rsi+10h]
0x18003a0b0  neg     rax
0x18003a0b3  sbb     rdx, rdx
0x18003a0b6  and     rdx, r8
0x18003a0b9  lea     r8, [rbp+arg_8]
0x18003a0bd  mov     rax, [r9+18h]
0x18003a0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0c6  mov     ebx, eax
0x18003a0c8  test    eax, eax
0x18003a0ca  jns     short loc_18003A0D6
0x18003a0cc  mov     edx, 7E6h
0x18003a0d1  jmp     loc_18003A04B
0x18003a0d6  mov     rbx, [rbp+arg_10]
0x18003a0da  test    rbx, rbx
0x18003a0dd  jz      short loc_18003A0EF
0x18003a0df  mov     rax, [rbx]
0x18003a0e2  mov     rcx, rbx
0x18003a0e5  mov     rax, [rax+8]
0x18003a0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0ee  nop
0x18003a0ef  mov     eax, [rbp+arg_8]
0x18003a0f2  mov     [rbp+var_30], eax
0x18003a0f5  mov     [rbp+var_18], rbx
0x18003a0f9  mov     [rbp+var_38], 0
0x18003a101  mov     [rbp+var_10], eax
0x18003a104  mov     [rbp+var_8], 1
0x18003a108  lea     rcx, [rbp+var_38]
0x18003a10c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a111  call    cs:__imp_GetCurrentThreadId
0x18003a117  mov     r8d, eax
0x18003a11a  call    Windows__Internal__ComTaskPool__QueueTask__lambda_a63a45bce6f319689b2cff365b7d75bc___
0x18003a11f  mov     [rbp+Handles], r14
0x18003a123  mov     rax, [rsi+40h]
0x18003a127  mov     [rbp+var_20], rax
0x18003a12b  mov     [rsp+70h+ppv], 0; bAlertable
0x18003a133  mov     r9d, 7530h; dwMilliseconds
0x18003a139  xor     r8d, r8d; bWaitAll
0x18003a13c  lea     rdx, [rbp+Handles]; lpHandles
0x18003a140  lea     ecx, [r8+2]; nCount
0x18003a144  call    cs:__imp_WaitForMultipleObjectsEx
0x18003a14a  cmp     eax, 0FFFFFFFFh
0x18003a14d  jz      short loc_18003A18D
0x18003a14f  lea     rcx, [rbp+var_18]
0x18003a153  call    wil__details__ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333______ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___
0x18003a158  nop
0x18003a159  lea     rcx, [rbp+arg_10]
0x18003a15d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a162  nop
0x18003a163  lea     rcx, [rbp+arg_18]
0x18003a167  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a16c  xor     ebx, ebx
0x18003a16e  lea     rcx, [rbp+var_40]
0x18003a172  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003a177  mov     eax, ebx
0x18003a179  mov     rbx, [rsp+70h+arg_0]
0x18003a181  add     rsp, 70h
0x18003a185  pop     r15
0x18003a187  pop     r14
0x18003a189  pop     rdi
0x18003a18a  pop     rsi
0x18003a18b  pop     rbp
0x18003a18c  retn
0x18003a18d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a192  nop
0x18003a193  mov     ebx, eax
0x18003a195  lea     rcx, [rbp+var_18]
0x18003a199  call    wil__details__ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333______ScopeExitFn__lambda_90c465788d40eead4cd3c075557b9333___
0x18003a19e  nop
0x18003a19f  lea     rcx, [rbp+arg_10]
0x18003a1a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a1a8  nop
0x18003a1a9  lea     rcx, [rbp+arg_18]
0x18003a1ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a1b2  jmp     short loc_18003A16E
```
