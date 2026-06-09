# LMCallback::InitializeInterfaces(void)

- ea: `0x180005f00`
- end: `0x1800060ee`
- name: `?InitializeInterfaces@LMCallback@@UEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(LMCallback *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001730`
- `0x1800018c0`
- `0x180002ed8`
- `0x180003690`
- `0x180004ea8`
- `0x180005f00`
- `0x1800060f4`
- `0x180007584`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180005f89`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180005f89`
- `LicenseManager!WnfEventHandlerForXboxTestNetworkConnectionComplete` at `0x180006053`
- `LicenseManager!WnfEventHandlerForDeviceIdChange` at `0x180005feb`
- `LicenseManager!WnfEventHandlerForOfflinePcChange` at `0x18000601f`

## string_xrefs

- `0x180006047`: `LastXboxTestNetworkConnectionComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LMCallback::InitializeInterfaces(LMCallback *this)
{
  ApplicationLicenseManagerClassFactory *v2; // rax
  IUnknown *v3; // rbx
  unsigned int v4; // r8d
  HRESULT v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 result; // rax
  signed int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // r8d
  __int64 v18; // [rsp+0h] [rbp-38h] BYREF
  LPDWORD lpdwRegister; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  IUnknown *v21; // [rsp+48h] [rbp+10h] BYREF

  v2 = (ApplicationLicenseManagerClassFactory *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = (IUnknown *)v2;
  v3 = 0;
  if ( v2 )
  {
    *(_OWORD *)v2 = 0;
    *((_QWORD *)v2 + 2) = 0;
    v3 = (IUnknown *)ApplicationLicenseManagerClassFactory::ApplicationLicenseManagerClassFactory(v2);
    v21 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<ApplicationLicenseManagerClassFactory>::~MakeAllocator<ApplicationLicenseManagerClassFactory>(&v21);
  try
  {
    v21 = v3;
    if ( !v3 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xB9, v4, (const char *)0x8007000ELL, (int)lpdwRegister);
    v5 = CoRegisterClassObject(&CLSID_ApplicationLicenseManager, v3, 4u, 1u, (LPDWORD)this + 2);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xBB, v6, (const char *)(unsigned int)v5, (int)lpdwRegister);
    if ( !IsXboxLicensingUndocked() )
    {
      v10 = RegisterRpcInterfaces((void **)this + 2);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC4,
          v11,
          (const char *)(unsigned int)v10,
          (int)lpdwRegister);
      *((_BYTE *)this + 24) = 1;
      v12 = RegisterWnfListener(
              *((struct SERVICE_STATUS_HANDLE__ **)this + 7),
              (struct _WNF_USER_SUBSCRIPTION **)this + 4,
              WNF_LIC_DEVICE_LICENSE_UPDATED,
              WnfEventHandlerForDeviceIdChange,
              L"LastWnfChangeStamp");
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC8,
          v13,
          (const char *)(unsigned int)v12,
          (int)lpdwRegister);
      v14 = RegisterWnfListener(
              *((struct SERVICE_STATUS_HANDLE__ **)this + 7),
              (struct _WNF_USER_SUBSCRIPTION **)this + 5,
              WNF_LM_OFFLINE_PC_CHANGED,
              WnfEventHandlerForOfflinePcChange,
              L"LastWnfOfflinePcChangeStamp");
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC9,
          v15,
          (const char *)(unsigned int)v14,
          (int)lpdwRegister);
      v16 = RegisterWnfListener(
              *((struct SERVICE_STATUS_HANDLE__ **)this + 7),
              (struct _WNF_USER_SUBSCRIPTION **)this + 6,
              WNF_XBOX_TEST_NETWORK_CONNECTION_COMPLETE,
              WnfEventHandlerForXboxTestNetworkConnectionComplete,
              L"LastXboxTestNetworkConnectionComplete");
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xCA,
          v17,
          (const char *)(unsigned int)v16,
          (int)lpdwRegister);
    }
    ((void (__fastcall *)(IUnknown *))v3->lpVtbl->Release)(v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v18, v7, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180005f00  mov     [rsp+arg_0], rbx
0x180005f05  push    rdi
0x180005f06  sub     rsp, 30h
0x180005f0a  mov     rdi, rcx
0x180005f0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f14  mov     ecx, 18h; unsigned __int64
0x180005f19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005f1e  mov     [rsp+38h+arg_8], rax
0x180005f23  xor     ebx, ebx
0x180005f25  test    rax, rax
0x180005f28  jz      short loc_180005F4A
0x180005f2a  xorps   xmm0, xmm0
0x180005f2d  xor     ecx, ecx
0x180005f2f  movups  xmmword ptr [rax], xmm0
0x180005f32  mov     [rax+10h], rcx
0x180005f36  mov     rcx, rax; this
0x180005f39  call    ??0ApplicationLicenseManagerClassFactory@@QEAA@XZ; ApplicationLicenseManagerClassFactory::ApplicationLicenseManagerClassFactory(void)
0x180005f3e  mov     rbx, rax
0x180005f41  mov     [rsp+38h+arg_8], 0
0x180005f4a  lea     rcx, [rsp+38h+arg_8]
0x180005f4f  call    ??1?$MakeAllocator@VApplicationLicenseManagerClassFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<ApplicationLicenseManagerClassFactory>::~MakeAllocator<ApplicationLicenseManagerClassFactory>(void)
0x180005f54  mov     [rsp+38h+arg_8], rbx
0x180005f59  test    rbx, rbx
0x180005f5c  setz    al
0x180005f5f  mov     rcx, [rsp+38h]; this
0x180005f64  test    al, al
0x180005f66  jnz     loc_18000609B
0x180005f6c  lea     rax, [rdi+8]
0x180005f70  mov     [rsp+38h+lpdwRegister], rax; int
0x180005f75  mov     r9d, 1; flags
0x180005f7b  lea     r8d, [r9+3]; dwClsContext
0x180005f7f  mov     rdx, rbx; pUnk
0x180005f82  lea     rcx, CLSID_ApplicationLicenseManager; rclsid
0x180005f89  call    cs:__imp_CoRegisterClassObject
0x180005f8f  mov     rcx, [rsp+38h]; this
0x180005f94  test    eax, eax
0x180005f96  js      loc_1800060AB
0x180005f9c  call    IsXboxLicensingUndocked
0x180005fa1  test    al, al
0x180005fa3  jz      short loc_180005FC1
0x180005fa5  test    rbx, rbx
0x180005fa8  jz      short loc_180005FBA
0x180005faa  mov     rax, [rbx]
0x180005fad  mov     rcx, rbx
0x180005fb0  mov     rax, [rax+10h]
0x180005fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb9  nop
0x180005fba  xor     eax, eax
0x180005fbc  jmp     loc_180006090
0x180005fc1  lea     rcx, [rdi+10h]; void **
0x180005fc5  call    ?RegisterRpcInterfaces@@YAJPEAPEAX@Z; RegisterRpcInterfaces(void * *)
0x180005fca  mov     rcx, [rsp+38h]; this
0x180005fcf  test    eax, eax
0x180005fd1  js      loc_1800060B8
0x180005fd7  mov     byte ptr [rdi+18h], 1
0x180005fdb  lea     rdx, [rdi+20h]; struct _WNF_USER_SUBSCRIPTION **
0x180005fdf  lea     rax, Value; "LastWnfChangeStamp"
0x180005fe6  mov     [rsp+38h+lpdwRegister], rax; int
0x180005feb  mov     r9, cs:__imp_?WnfEventHandlerForDeviceIdChange@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)
0x180005ff2  mov     r8, qword ptr cs:WNF_LIC_DEVICE_LICENSE_UPDATED.Data; struct _WNF_STATE_NAME
0x180005ff9  mov     rcx, [rdi+38h]; struct SERVICE_STATUS_HANDLE__ *
0x180005ffd  call    ?RegisterWnfListener@@YAJPEAUSERVICE_STATUS_HANDLE__@@PEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@P6AJ2KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZPEBG@Z; RegisterWnfListener(SERVICE_STATUS_HANDLE__ *,_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),ushort const *)
0x180006002  mov     rcx, [rsp+38h]; this
0x180006007  test    eax, eax
0x180006009  js      loc_1800060C5
0x18000600f  lea     rdx, [rdi+28h]; struct _WNF_USER_SUBSCRIPTION **
0x180006013  lea     rax, aLastwnfoffline; "LastWnfOfflinePcChangeStamp"
0x18000601a  mov     [rsp+38h+lpdwRegister], rax; int
0x18000601f  mov     r9, cs:__imp_?WnfEventHandlerForOfflinePcChange@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)
0x180006026  mov     r8, qword ptr cs:WNF_LM_OFFLINE_PC_CHANGED.Data; struct _WNF_STATE_NAME
0x18000602d  mov     rcx, [rdi+38h]; struct SERVICE_STATUS_HANDLE__ *
0x180006031  call    ?RegisterWnfListener@@YAJPEAUSERVICE_STATUS_HANDLE__@@PEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@P6AJ2KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZPEBG@Z; RegisterWnfListener(SERVICE_STATUS_HANDLE__ *,_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),ushort const *)
0x180006036  mov     rcx, [rsp+38h]; this
0x18000603b  test    eax, eax
0x18000603d  js      loc_1800060D2
0x180006043  lea     rdx, [rdi+30h]; struct _WNF_USER_SUBSCRIPTION **
0x180006047  lea     rax, aLastxboxtestne; "LastXboxTestNetworkConnectionComplete"
0x18000604e  mov     [rsp+38h+lpdwRegister], rax; int
0x180006053  mov     r9, cs:__imp_?WnfEventHandlerForXboxTestNetworkConnectionComplete@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)
0x18000605a  mov     r8, qword ptr cs:WNF_XBOX_TEST_NETWORK_CONNECTION_COMPLETE.Data; struct _WNF_STATE_NAME
0x180006061  mov     rcx, [rdi+38h]; struct SERVICE_STATUS_HANDLE__ *
0x180006065  call    ?RegisterWnfListener@@YAJPEAUSERVICE_STATUS_HANDLE__@@PEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@P6AJ2KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZPEBG@Z; RegisterWnfListener(SERVICE_STATUS_HANDLE__ *,_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),ushort const *)
0x18000606a  mov     rcx, [rsp+38h]; this
0x18000606f  test    eax, eax
0x180006071  js      short loc_1800060DF
0x180006073  test    rbx, rbx
0x180006076  jz      short loc_180006088
0x180006078  mov     rax, [rbx]
0x18000607b  mov     rcx, rbx
0x18000607e  mov     rax, [rax+10h]
0x180006082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006087  nop
0x180006088  xor     eax, eax
0x18000608a  jmp     short loc_180006090
0x18000608c  mov     eax, dword ptr [rsp+38h+arg_8]
0x180006090  mov     rbx, [rsp+38h+arg_0]
0x180006095  add     rsp, 30h
0x180006099  pop     rdi
0x18000609a  retn
0x18000609b  mov     edx, 0B9h; void *
0x1800060a0  mov     r9d, 8007000Eh; char *
0x1800060a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060ab  mov     r9d, eax; char *
0x1800060ae  mov     edx, 0BBh; void *
0x1800060b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060b8  mov     r9d, eax; char *
0x1800060bb  mov     edx, 0C4h; void *
0x1800060c0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060c5  mov     r9d, eax; char *
0x1800060c8  mov     edx, 0C8h; void *
0x1800060cd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060d2  mov     r9d, eax; char *
0x1800060d5  mov     edx, 0C9h; void *
0x1800060da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060df  mov     r9d, eax; char *
0x1800060e2  mov     edx, 0CAh; void *
0x1800060e7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
