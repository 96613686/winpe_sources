# SetScheduledTaskEnabledState(bool)

- ea: `0x1800101c0`
- end: `0x180010452`
- name: `?SetScheduledTaskEnabledState@@YAJ_N@Z`
- size: `658`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800115f0`

## callees

- `0x180003530`
- `0x180005120`
- `0x180008a38`
- `0x18000d73c`
- `0x18000e808`
- `0x18000f5f0`
- `0x18000f80c`
- `0x1800101c0`
- `0x18001065c`
- `0x180011428`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010240`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010240`

## string_xrefs

- `0x1800101eb`: `SetScheduledTaskEnabledStateActivity`
- `0x1800102ac`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x18001031c`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x180010396`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
__int64 __fastcall SetScheduledTaskEnabledState(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  int *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v18; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-50h]
  __int128 v26; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-30h]
  _QWORD v28[42]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "SetScheduledTaskEnabledStateActivity",
    a3);
  v28[0] = &SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::`vftable';
  SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::StartActivity((SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity *)v28);
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v3 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 164;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
      (const char *)(unsigned int)v3,
      (int)ppv);
    goto LABEL_15;
  }
  *(_OWORD *)v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  ppv = v20;
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v18 + 80LL))(
         v18,
         &v26,
         &v24,
         &v22);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 166;
    goto LABEL_5;
  }
  wil::make_bstr(&v17, L"\\Microsoft\\Windows\\SharedPC");
  v15 = 0;
  v6 = v18;
  v7 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v18 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v8 = v7(v6, v17, &v15);
  v4 = v8;
  if ( v8 >= 0 )
  {
    wil::make_bstr(v19, L"Account Cleanup");
    v16 = 0;
    v9 = v15;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v11 = v10(v9, v19[0], &v16);
    v4 = v11;
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 88LL))(v16, 0xFFFFFFFFLL);
      v4 = v11;
      if ( v11 >= 0 )
      {
        wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        v4 = 0;
        goto LABEL_15;
      }
      v12 = 175;
    }
    else
    {
      v12 = 174;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
      (const char *)(unsigned int)v11,
      (int)v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
      (const char *)(unsigned int)v8,
      (int)v20);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::~SetScheduledTaskEnabledStateActivity((SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity *)v28);
  return v4;
}

```

## disassembly

```asm
0x1800101c0  mov     [rsp-8+arg_0], rbx
0x1800101c5  mov     [rsp-8+arg_8], rdi
0x1800101ca  push    rbp
0x1800101cb  lea     rbp, [rsp-140h]
0x1800101d3  sub     rsp, 240h
0x1800101da  mov     rax, cs:__security_cookie
0x1800101e1  xor     rax, rsp
0x1800101e4  mov     [rbp+140h+var_10], rax
0x1800101eb  lea     rdx, aSetscheduledta; "SetScheduledTaskEnabledStateActivity"
0x1800101f2  lea     rcx, [rbp+140h+var_160]
0x1800101f6  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800101fb  lea     rax, ??_7SetScheduledTaskEnabledStateActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::`vftable'
0x180010202  mov     [rbp+140h+var_160], rax
0x180010206  lea     rcx, [rbp+140h+var_160]; this
0x18001020a  call    ?StartActivity@SetScheduledTaskEnabledStateActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::StartActivity(void)
0x18001020f  mov     [rsp+240h+var_1F8], 0
0x180010218  lea     rcx, [rsp+240h+var_1F8]
0x18001021d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010222  lea     rax, [rsp+240h+var_1F8]
0x180010227  mov     [rsp+240h+ppv], rax; ppv
0x18001022c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180010233  xor     edx, edx; pUnkOuter
0x180010235  lea     r8d, [rdx+1]; dwClsContext
0x180010239  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180010240  call    cs:__imp_CoCreateInstance
0x180010246  mov     ebx, eax
0x180010248  test    eax, eax
0x18001024a  jns     short loc_180010253
0x18001024c  mov     edx, 0A4h
0x180010251  jmp     short loc_1800102AC
0x180010253  xorps   xmm1, xmm1
0x180010256  xor     eax, eax
0x180010258  mov     rcx, [rsp+240h+var_1F8]
0x18001025d  movaps  xmmword ptr [rsp+240h+var_1E0], xmm1
0x180010262  mov     [rsp+240h+var_1D0], rax
0x180010267  movaps  [rbp+140h+var_1C0], xmm1
0x18001026b  mov     [rbp+140h+var_1B0], rax
0x18001026f  movaps  [rbp+140h+var_1A0], xmm1
0x180010273  mov     [rbp+140h+var_190], rax
0x180010277  movaps  [rbp+140h+var_180], xmm1
0x18001027b  mov     [rbp+140h+var_170], rax
0x18001027f  mov     rax, [rcx]
0x180010282  lea     rdx, [rsp+240h+var_1E0]
0x180010287  mov     [rsp+240h+ppv], rdx; int
0x18001028c  lea     r9, [rbp+140h+var_1C0]
0x180010290  lea     r8, [rbp+140h+var_1A0]
0x180010294  lea     rdx, [rbp+140h+var_180]
0x180010298  mov     rax, [rax+50h]
0x18001029c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102a1  mov     ebx, eax
0x1800102a3  test    eax, eax
0x1800102a5  jns     short loc_1800102C7
0x1800102a7  mov     edx, 0A6h; void *
0x1800102ac  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800102b3  mov     r9d, eax; char *
0x1800102b6  mov     rcx, [rbp+148h]; this
0x1800102bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102c2  jmp     loc_180010419
0x1800102c7  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\SharedPC"
0x1800102ce  lea     rcx, [rsp+240h+var_200]
0x1800102d3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800102d8  mov     [rsp+240h+var_210], 0
0x1800102e1  mov     rdi, [rsp+240h+var_1F8]
0x1800102e6  mov     rax, [rdi]
0x1800102e9  mov     rbx, [rax+38h]
0x1800102ed  lea     rcx, [rsp+240h+var_210]
0x1800102f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800102f7  lea     r8, [rsp+240h+var_210]
0x1800102fc  mov     rdx, [rsp+240h+var_200]
0x180010301  mov     rcx, rdi
0x180010304  mov     rax, rbx
0x180010307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001030c  mov     ebx, eax
0x18001030e  test    eax, eax
0x180010310  jns     short loc_180010346
0x180010312  mov     rcx, [rbp+148h]; this
0x180010319  mov     r9d, eax; char *
0x18001031c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180010323  mov     edx, 0AAh; void *
0x180010328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001032d  lea     rcx, [rsp+240h+var_210]
0x180010332  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010337  lea     rcx, [rsp+240h+var_200]
0x18001033c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010341  jmp     loc_180010419
0x180010346  lea     rdx, aAccountCleanup; "Account Cleanup"
0x18001034d  lea     rcx, [rsp+240h+var_1F0]
0x180010352  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180010357  mov     [rsp+240h+var_208], 0
0x180010360  mov     rdi, [rsp+240h+var_210]
0x180010365  mov     rax, [rdi]
0x180010368  mov     rbx, [rax+68h]
0x18001036c  lea     rcx, [rsp+240h+var_208]
0x180010371  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010376  lea     r8, [rsp+240h+var_208]
0x18001037b  mov     rdx, [rsp+240h+var_1F0]
0x180010380  mov     rcx, rdi
0x180010383  mov     rax, rbx
0x180010386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001038b  mov     ebx, eax
0x18001038d  test    eax, eax
0x18001038f  jns     short loc_1800103C5
0x180010391  mov     edx, 0AEh; void *
0x180010396  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001039d  mov     r9d, eax; char *
0x1800103a0  mov     rcx, [rbp+148h]; this
0x1800103a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103ac  lea     rcx, [rsp+240h+var_208]
0x1800103b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103b6  lea     rcx, [rsp+240h+var_1F0]
0x1800103bb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800103c0  jmp     loc_18001032D
0x1800103c5  mov     rcx, [rsp+240h+var_208]
0x1800103ca  mov     rax, [rcx]
0x1800103cd  or      edx, 0FFFFFFFFh
0x1800103d0  mov     rax, [rax+58h]
0x1800103d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d9  mov     ebx, eax
0x1800103db  test    eax, eax
0x1800103dd  jns     short loc_1800103E6
0x1800103df  mov     edx, 0AFh
0x1800103e4  jmp     short loc_180010396
0x1800103e6  lea     rcx, [rbp+140h+var_160]
0x1800103ea  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800103ef  lea     rcx, [rsp+240h+var_208]
0x1800103f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800103f9  lea     rcx, [rsp+240h+var_1F0]
0x1800103fe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010403  lea     rcx, [rsp+240h+var_210]
0x180010408  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001040d  lea     rcx, [rsp+240h+var_200]
0x180010412  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010417  xor     ebx, ebx
0x180010419  lea     rcx, [rsp+240h+var_1F8]
0x18001041e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010423  lea     rcx, [rbp+140h+var_160]; this
0x180010427  call    ??1SetScheduledTaskEnabledStateActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::~SetScheduledTaskEnabledStateActivity(void)
0x18001042c  mov     eax, ebx
0x18001042e  mov     rcx, [rbp+140h+var_10]
0x180010435  xor     rcx, rsp; StackCookie
0x180010438  call    __security_check_cookie
0x18001043d  lea     r11, [rsp+240h+var_s0]
0x180010445  mov     rbx, [r11+10h]
0x180010449  mov     rdi, [r11+18h]
0x18001044d  mov     rsp, r11
0x180010450  pop     rbp
0x180010451  retn
```
