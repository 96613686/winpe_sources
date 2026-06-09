# CoCreateCOMTaskServerObject

- ea: `0x18004860c`
- end: `0x180048804`
- name: `CoCreateCOMTaskServerObject`
- size: `504`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004880c`

## callees

- `0x180006d4c`
- `0x18000aa7c`
- `0x180013a64`
- `0x1800325d0`
- `0x1800428a4`
- `0x180047644`
- `0x180047da0`
- `0x18004835c`
- `0x1800484cc`
- `0x18004860c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048699`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800487a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048699`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800487a7`

## string_xrefs

- `0x180048648`: `CoCreateCOMTaskServerObject`
- `0x1800486dc`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x1800486b1`: `shell\lib\comtaskserverutil.cpp`
- `0x1800486fe`: `shell\lib\comtaskserverutil.cpp`
- `0x180048731`: `shell\lib\comtaskserverutil.cpp`
- `0x180048770`: `shell\lib\comtaskserverutil.cpp`
- `0x1800487ba`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoCreateCOMTaskServerObject(__int64 a1, __int64 a2, wil *a3, __int64 a4, int a5, LPVOID *a6)
{
  LPVOID *v6; // rdi
  struct wil::details::IFailureCallback *v7; // rax
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  HRESULT Instance; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  const unsigned __int16 *v14; // rcx
  int v15; // eax
  unsigned int v16; // r8d
  int v17; // r9d
  HRESULT v18; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int v22; // [rsp+30h] [rbp-50h] BYREF
  const char *v23; // [rsp+38h] [rbp-48h]
  __int64 v24; // [rsp+40h] [rbp-40h]
  char v25; // [rsp+48h] [rbp-38h]
  _BYTE v26[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  wil *v28; // [rsp+A0h] [rbp+20h] BYREF

  v28 = a3;
  v6 = a6;
  *a6 = 0;
  v7 = (struct wil::details::IFailureCallback *)wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(
                                                  a1,
                                                  _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_);
  v25 = 0;
  v22 = 0;
  v23 = "CoCreateCOMTaskServerObject";
  v24 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v26,
    v7,
    (struct wil::CallContextInfo *)&v22,
    1);
  Instance = WaitForEventIfPresent(v9, v8);
  v11 = Instance;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
    v11 = Instance;
    if ( Instance < 0 )
    {
      if ( Instance != -2147221164 )
      {
        v12 = 100;
        goto LABEL_6;
      }
      v28 = 0;
      v13 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              &v28,
              1,
              L"Global\\ShellCreateObjectTaskReadyEvent");
      v11 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)(unsigned int)v13,
          ppv);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
        goto LABEL_18;
      }
      v15 = RunTaskSchedulerTask(v14);
      v11 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)(unsigned int)v15,
          ppv);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
        goto LABEL_18;
      }
      if ( !wil::handle_wait(v28, (void *)0x7530, v16, v17) )
      {
        v11 = -2147023436;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)0x800705B4LL,
          ppv);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
        goto LABEL_18;
      }
      v18 = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
      v11 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)(unsigned int)v18,
          ppva);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
        goto LABEL_18;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    v11 = 0;
    goto LABEL_18;
  }
  v12 = 96;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_18:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v22);
  return v11;
}

```

## disassembly

```asm
0x18004860c  mov     [rsp-8+arg_0], rbx
0x180048611  mov     [rsp-8+arg_8], rdi
0x180048616  mov     [rsp-8+arg_10], r8
0x18004861b  push    rbp
0x18004861c  mov     rbp, rsp
0x18004861f  sub     rsp, 80h
0x180048626  mov     rdi, [rbp+arg_28]
0x18004862a  mov     qword ptr [rdi], 0
0x180048631  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_(void)
0x180048638  call    ?get@?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@QEAAPEAVCoCreateInstanceAsSystemTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(void (*)(void))
0x18004863d  mov     [rbp+var_38], 0
0x180048641  mov     [rbp+var_50], 0
0x180048648  lea     rcx, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x18004864f  mov     [rbp+var_48], rcx
0x180048653  mov     [rbp+var_40], 0
0x18004865b  mov     r9b, 1; bool
0x18004865e  lea     r8, [rbp+var_50]; struct wil::CallContextInfo *
0x180048662  mov     rdx, rax; struct wil::details::IFailureCallback *
0x180048665  lea     rcx, [rbp+var_30]; this
0x180048669  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18004866e  call    ?WaitForEventIfPresent@@YAJPEBGK@Z; WaitForEventIfPresent(ushort const *,ulong)
0x180048673  mov     ebx, eax
0x180048675  test    eax, eax
0x180048677  jns     short loc_180048680
0x180048679  mov     edx, 60h ; '`'
0x18004867e  jmp     short loc_1800486B1
0x180048680  mov     qword ptr [rsp+80h+ppv], rdi; int
0x180048685  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18004868c  xor     edx, edx; pUnkOuter
0x18004868e  lea     r8d, [rdx+4]; dwClsContext
0x180048692  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x180048699  call    cs:__imp_CoCreateInstance
0x18004869f  mov     ebx, eax
0x1800486a1  test    eax, eax
0x1800486a3  jns     short loc_1800486C9
0x1800486a5  cmp     eax, 80040154h
0x1800486aa  jz      short loc_1800486D4
0x1800486ac  mov     edx, 64h ; 'd'; void *
0x1800486b1  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800486b8  mov     r9d, eax; char *
0x1800486bb  mov     rcx, [rbp+8]; this
0x1800486bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800486c4  jmp     loc_1800487E4
0x1800486c9  cmp     eax, 80040154h
0x1800486ce  jnz     loc_1800487E2
0x1800486d4  mov     [rbp+arg_10], 0
0x1800486dc  lea     r8, aGlobalShellcre; "Global\\ShellCreateObjectTaskReadyEvent"
0x1800486e3  mov     edx, 1
0x1800486e8  lea     rcx, [rbp+arg_10]
0x1800486ec  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800486f1  mov     ebx, eax
0x1800486f3  test    eax, eax
0x1800486f5  jns     short loc_18004871F
0x1800486f7  mov     rcx, [rbp+8]; this
0x1800486fb  mov     r9d, eax; char *
0x1800486fe  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180048705  mov     edx, 6Bh ; 'k'; void *
0x18004870a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004870f  nop
0x180048710  lea     rcx, [rbp+arg_10]
0x180048714  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180048719  nop
0x18004871a  jmp     loc_1800487E4
0x18004871f  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x180048724  mov     ebx, eax
0x180048726  test    eax, eax
0x180048728  jns     short loc_180048752
0x18004872a  mov     rcx, [rbp+8]; this
0x18004872e  mov     r9d, eax; char *
0x180048731  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180048738  mov     edx, 6Eh ; 'n'; void *
0x18004873d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048742  nop
0x180048743  lea     rcx, [rbp+arg_10]
0x180048747  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004874c  nop
0x18004874d  jmp     loc_1800487E4
0x180048752  mov     edx, 7530h; void *
0x180048757  mov     rcx, [rbp+arg_10]; this
0x18004875b  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180048760  test    al, al
0x180048762  jnz     short loc_18004878E
0x180048764  mov     rcx, [rbp+8]; this
0x180048768  mov     ebx, 800705B4h
0x18004876d  mov     r9d, ebx; char *
0x180048770  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180048777  mov     edx, 6Fh ; 'o'; void *
0x18004877c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048781  nop
0x180048782  lea     rcx, [rbp+arg_10]
0x180048786  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004878b  nop
0x18004878c  jmp     short loc_1800487E4
0x18004878e  mov     qword ptr [rsp+80h+ppv], rdi; int
0x180048793  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18004879a  xor     edx, edx; pUnkOuter
0x18004879c  lea     r8d, [rdx+4]; dwClsContext
0x1800487a0  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x1800487a7  call    cs:__imp_CoCreateInstance
0x1800487ad  mov     ebx, eax
0x1800487af  test    eax, eax
0x1800487b1  jns     short loc_1800487D8
0x1800487b3  mov     rcx, [rbp+8]; this
0x1800487b7  mov     r9d, eax; char *
0x1800487ba  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800487c1  mov     edx, 71h ; 'q'; void *
0x1800487c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800487cb  nop
0x1800487cc  lea     rcx, [rbp+arg_10]
0x1800487d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800487d5  nop
0x1800487d6  jmp     short loc_1800487E4
0x1800487d8  lea     rcx, [rbp+arg_10]
0x1800487dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800487e1  nop
0x1800487e2  xor     ebx, ebx
0x1800487e4  lea     rcx, [rbp+var_50]; this
0x1800487e8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800487ed  mov     eax, ebx
0x1800487ef  lea     r11, [rsp+80h+var_s0]
0x1800487f7  mov     rbx, [r11+10h]
0x1800487fb  mov     rdi, [r11+18h]
0x1800487ff  mov     rsp, r11
0x180048802  pop     rbp
0x180048803  retn
```
