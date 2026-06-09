# CoCreateCOMTaskServerObject(_GUID const &,ushort const *,ushort const *,ulong,_GUID const &)

- ea: `0x1800124f4`
- end: `0x18001263d`
- name: `?CoCreateCOMTaskServerObject@@YA?AV?$ComPtr@UICreateObject@@@WRL@Microsoft@@AEBU_GUID@@PEBG1K0@Z`
- size: `329`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022338`

## callees

- `0x18000fa5c`
- `0x180010394`
- `0x180010c8c`
- `0x1800124f4`
- `0x180012644`
- `0x1800126ac`
- `0x18001dc28`
- `0x180020028`
- `0x1800227ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180012524`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180012524`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012593`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012605`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012593`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012605`

## string_xrefs

- `0x180012552`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x1800125d2`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x180012617`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x180012516`: `Global\CloudExperienceHostCreateObjectTaskReadyEvent`
- `0x1800125a1`: `Global\CloudExperienceHostCreateObjectTaskReadyEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall CoCreateCOMTaskServerObject(LPVOID *a1)
{
  HANDLE v2; // rax
  unsigned int v3; // edx
  int v4; // eax
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // edx
  int v7; // eax
  HRESULT Instance; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  int ppvb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v14; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  v2 = OpenEventW(0x100000u, 0, L"Global\\CloudExperienceHostCreateObjectTaskReadyEvent");
  if ( v2 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v14,
      v2);
    v4 = HrWaitForSingleObject(v14, v3);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
        (const char *)(unsigned int)v4,
        ppv);
  }
  *a1 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  if ( CoCreateInstance(
         &GUID_f7fa3149_91e7_43b7_8040_b707688ced1a,
         0,
         4u,
         &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
         a1) < 0 )
  {
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v14,
      1,
      L"Global\\CloudExperienceHostCreateObjectTaskReadyEvent");
    RunTaskSchedulerTask(v5);
    v7 = HrWaitForSingleObject(v14, v6);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
        (const char *)(unsigned int)v7,
        ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
    Instance = CoCreateInstance(
                 &GUID_f7fa3149_91e7_43b7_8040_b707688ced1a,
                 0,
                 4u,
                 &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                 a1);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
        (const char *)(unsigned int)Instance,
        ppvb);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
  return a1;
}

```

## disassembly

```asm
0x1800124f4  mov     rax, rsp
0x1800124f7  mov     [rax+20h], r9
0x1800124fb  mov     [rax+8], rcx
0x1800124ff  push    rbx
0x180012500  sub     rsp, 40h
0x180012504  mov     rbx, rcx
0x180012507  mov     dword ptr [rax-18h], 0
0x18001250e  mov     qword ptr [rax+20h], 0
0x180012516  lea     r8, Name; "Global\\CloudExperienceHostCreateObject"...
0x18001251d  xor     edx, edx; bInheritHandle
0x18001251f  mov     ecx, 100000h; dwDesiredAccess
0x180012524  call    cs:__imp_OpenEventW
0x18001252a  test    rax, rax
0x18001252d  jz      short loc_180012563
0x18001252f  mov     rdx, rax
0x180012532  lea     rcx, [rsp+48h+arg_18]
0x180012537  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001253c  mov     rcx, [rsp+48h+arg_18]; void *
0x180012541  call    ?HrWaitForSingleObject@@YAJPEAXK@Z; HrWaitForSingleObject(void *,ulong)
0x180012546  mov     rcx, [rsp+48h]; this
0x18001254b  test    eax, eax
0x18001254d  jns     short loc_180012563
0x18001254f  mov     r9d, eax; char *
0x180012552  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x180012559  mov     edx, 4Ah ; 'J'; void *
0x18001255e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012563  mov     qword ptr [rbx], 0
0x18001256a  mov     [rsp+48h+var_18], 1
0x180012572  mov     rcx, rbx
0x180012575  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001257a  mov     qword ptr [rsp+48h+ppv], rbx; int
0x18001257f  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180012586  xor     edx, edx; pUnkOuter
0x180012588  lea     r8d, [rdx+4]; dwClsContext
0x18001258c  lea     rcx, _GUID_f7fa3149_91e7_43b7_8040_b707688ced1a; rclsid
0x180012593  call    cs:__imp_CoCreateInstance
0x180012599  test    eax, eax
0x18001259b  jns     loc_180012629
0x1800125a1  lea     r8, Name; "Global\\CloudExperienceHostCreateObject"...
0x1800125a8  mov     edx, 1
0x1800125ad  lea     rcx, [rsp+48h+arg_18]
0x1800125b2  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800125b7  call    ?RunTaskSchedulerTask@@YAXPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x1800125bc  mov     rcx, [rsp+48h+arg_18]; void *
0x1800125c1  call    ?HrWaitForSingleObject@@YAJPEAXK@Z; HrWaitForSingleObject(void *,ulong)
0x1800125c6  mov     rcx, [rsp+48h]; this
0x1800125cb  test    eax, eax
0x1800125cd  jns     short loc_1800125E4
0x1800125cf  mov     r9d, eax; char *
0x1800125d2  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800125d9  mov     edx, 55h ; 'U'; void *
0x1800125de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800125e4  mov     rcx, rbx
0x1800125e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800125ec  mov     qword ptr [rsp+48h+ppv], rbx; int
0x1800125f1  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x1800125f8  xor     edx, edx; pUnkOuter
0x1800125fa  lea     r8d, [rdx+4]; dwClsContext
0x1800125fe  lea     rcx, _GUID_f7fa3149_91e7_43b7_8040_b707688ced1a; rclsid
0x180012605  call    cs:__imp_CoCreateInstance
0x18001260b  mov     rcx, [rsp+48h]; this
0x180012610  test    eax, eax
0x180012612  jns     short loc_180012629
0x180012614  mov     r9d, eax; char *
0x180012617  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001261e  mov     edx, 56h ; 'V'; void *
0x180012623  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012629  lea     rcx, [rsp+48h+arg_18]
0x18001262e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012633  mov     rax, rbx
0x180012636  add     rsp, 40h
0x18001263a  pop     rbx
0x18001263b  retn
```
