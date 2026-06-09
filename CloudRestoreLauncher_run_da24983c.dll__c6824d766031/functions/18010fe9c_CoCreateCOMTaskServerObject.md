# CoCreateCOMTaskServerObject

- ea: `0x18010fe9c`
- end: `0x180110092`
- name: `CoCreateCOMTaskServerObject`
- size: `502`
- prototype: `__int64 __fastcall(__int64, __int64, wil *, __int64, int, LPVOID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180110098`

## callees

- `0x18000db0f`
- `0x18001024c`
- `0x180011ea4`
- `0x180015a58`
- `0x1800285e8`
- `0x180082560`
- `0x18010ef00`
- `0x18010f640`
- `0x18010fbec`
- `0x18010fd5c`
- `0x18010fe9c`

## string_xrefs

- `0x18010fed8`: `CoCreateCOMTaskServerObject`
- `0x18010ff6b`: `Global\ShellCreateObjectTaskReadyEvent`
- `0x18010ff40`: `shell\lib\comtaskserverutil.cpp`
- `0x18010ff8d`: `shell\lib\comtaskserverutil.cpp`
- `0x18010ffc0`: `shell\lib\comtaskserverutil.cpp`
- `0x18010ffff`: `shell\lib\comtaskserverutil.cpp`
- `0x180110048`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoCreateCOMTaskServerObject(__int64 a1, __int64 a2, wil *a3, __int64 a4, int a5, LPVOID *a6)
{
  LPVOID *v6; // rdi
  struct wil::details::IFailureCallback *v7; // rax
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  HRESULT Instance_0; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  struct IRegisteredTask *v14; // rcx
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
  Instance_0 = WaitForEventIfPresent(v9, v8);
  v11 = Instance_0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = CoCreateInstance_0(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
    v11 = Instance_0;
    if ( Instance_0 < 0 )
    {
      if ( Instance_0 != -2147221164 )
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
      v18 = CoCreateInstance_0(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
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
    (const char *)(unsigned int)Instance_0,
    ppv);
LABEL_18:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v22);
  return v11;
}

```

## disassembly

```asm
0x18010fe9c  mov     [rsp-8+arg_0], rbx
0x18010fea1  mov     [rsp-8+arg_8], rdi
0x18010fea6  mov     [rsp-8+arg_10], r8
0x18010feab  push    rbp
0x18010feac  mov     rbp, rsp
0x18010feaf  sub     rsp, 80h
0x18010feb6  mov     rdi, [rbp+arg_28]
0x18010feba  mov     qword ptr [rdi], 0
0x18010fec1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_(void)
0x18010fec8  call    ?get@?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@QEAAPEAVCoCreateInstanceAsSystemTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(void (*)(void))
0x18010fecd  mov     [rbp+var_38], 0
0x18010fed1  mov     [rbp+var_50], 0
0x18010fed8  lea     rcx, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x18010fedf  mov     [rbp+var_48], rcx
0x18010fee3  mov     [rbp+var_40], 0
0x18010feeb  mov     r9b, 1; bool
0x18010feee  lea     r8, [rbp+var_50]; struct wil::CallContextInfo *
0x18010fef2  mov     rdx, rax; struct wil::details::IFailureCallback *
0x18010fef5  lea     rcx, [rbp+var_30]; this
0x18010fef9  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18010fefe  call    ?WaitForEventIfPresent@@YAJPEBGK@Z; WaitForEventIfPresent(ushort const *,ulong)
0x18010ff03  mov     ebx, eax
0x18010ff05  test    eax, eax
0x18010ff07  jns     short loc_18010FF10
0x18010ff09  mov     edx, 60h ; '`'
0x18010ff0e  jmp     short loc_18010FF40
0x18010ff10  mov     qword ptr [rsp+80h+ppv], rdi; int
0x18010ff15  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18010ff1c  xor     edx, edx; pUnkOuter
0x18010ff1e  lea     r8d, [rdx+4]; dwClsContext
0x18010ff22  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18010ff29  call    CoCreateInstance_0
0x18010ff2e  mov     ebx, eax
0x18010ff30  test    eax, eax
0x18010ff32  jns     short loc_18010FF58
0x18010ff34  cmp     eax, 80040154h
0x18010ff39  jz      short loc_18010FF63
0x18010ff3b  mov     edx, 64h ; 'd'; void *
0x18010ff40  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18010ff47  mov     r9d, eax; char *
0x18010ff4a  mov     rcx, [rbp+8]; this
0x18010ff4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ff53  jmp     loc_180110072
0x18010ff58  cmp     eax, 80040154h
0x18010ff5d  jnz     loc_180110070
0x18010ff63  mov     [rbp+arg_10], 0
0x18010ff6b  lea     r8, aGlobalShellcre; "Global\\ShellCreateObjectTaskReadyEvent"
0x18010ff72  mov     edx, 1
0x18010ff77  lea     rcx, [rbp+arg_10]
0x18010ff7b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18010ff80  mov     ebx, eax
0x18010ff82  test    eax, eax
0x18010ff84  jns     short loc_18010FFAE
0x18010ff86  mov     rcx, [rbp+8]; this
0x18010ff8a  mov     r9d, eax; char *
0x18010ff8d  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18010ff94  mov     edx, 6Bh ; 'k'; void *
0x18010ff99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ff9e  nop
0x18010ff9f  lea     rcx, [rbp+arg_10]
0x18010ffa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010ffa8  nop
0x18010ffa9  jmp     loc_180110072
0x18010ffae  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x18010ffb3  mov     ebx, eax
0x18010ffb5  test    eax, eax
0x18010ffb7  jns     short loc_18010FFE1
0x18010ffb9  mov     rcx, [rbp+8]; this
0x18010ffbd  mov     r9d, eax; char *
0x18010ffc0  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18010ffc7  mov     edx, 6Eh ; 'n'; void *
0x18010ffcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ffd1  nop
0x18010ffd2  lea     rcx, [rbp+arg_10]
0x18010ffd6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010ffdb  nop
0x18010ffdc  jmp     loc_180110072
0x18010ffe1  mov     edx, 7530h; void *
0x18010ffe6  mov     rcx, [rbp+arg_10]; this
0x18010ffea  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18010ffef  test    al, al
0x18010fff1  jnz     short loc_18011001D
0x18010fff3  mov     rcx, [rbp+8]; this
0x18010fff7  mov     ebx, 800705B4h
0x18010fffc  mov     r9d, ebx; char *
0x18010ffff  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180110006  mov     edx, 6Fh ; 'o'; void *
0x18011000b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110010  nop
0x180110011  lea     rcx, [rbp+arg_10]
0x180110015  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18011001a  nop
0x18011001b  jmp     short loc_180110072
0x18011001d  mov     qword ptr [rsp+80h+ppv], rdi; int
0x180110022  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180110029  xor     edx, edx; pUnkOuter
0x18011002b  lea     r8d, [rdx+4]; dwClsContext
0x18011002f  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x180110036  call    CoCreateInstance_0
0x18011003b  mov     ebx, eax
0x18011003d  test    eax, eax
0x18011003f  jns     short loc_180110066
0x180110041  mov     rcx, [rbp+8]; this
0x180110045  mov     r9d, eax; char *
0x180110048  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18011004f  mov     edx, 71h ; 'q'; void *
0x180110054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110059  nop
0x18011005a  lea     rcx, [rbp+arg_10]
0x18011005e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180110063  nop
0x180110064  jmp     short loc_180110072
0x180110066  lea     rcx, [rbp+arg_10]
0x18011006a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18011006f  nop
0x180110070  xor     ebx, ebx
0x180110072  lea     rcx, [rbp+var_50]; this
0x180110076  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18011007b  mov     eax, ebx
0x18011007d  lea     r11, [rsp+80h+var_s0]
0x180110085  mov     rbx, [r11+10h]
0x180110089  mov     rdi, [r11+18h]
0x18011008d  mov     rsp, r11
0x180110090  pop     rbp
0x180110091  retn
```
