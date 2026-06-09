# Common::Deployment::GetManifestReaderFromPath(ushort const *,ushort const *,Common::Deployment::IValidatedManifestReaderHelper *,IAppxManifestReader * *)

- ea: `0x18004057c`
- end: `0x180040bd8`
- name: `?GetManifestReaderFromPath@Deployment@Common@@YAJPEBG0PEAVIValidatedManifestReaderHelper@12@PEAPEAUIAppxManifestReader@@@Z`
- size: `1628`
- prototype: `__int64 __fastcall(Common::Deployment *this, const unsigned __int16 *, unsigned __int16 *, struct Common::Deployment::IValidatedManifestReaderHelper *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075370`
- `0x180181930`

## callees

- `0x180006970`
- `0x180009dc0`
- `0x18001adb4`
- `0x1800225fc`
- `0x18003d9b0`
- `0x18004057c`
- `0x1800413e4`
- `0x180050e60`
- `0x18006cac4`
- `0x180076000`
- `0x180076064`
- `0x180076110`
- `0x180076168`
- `0x180078c5c`
- `0x180078d20`
- `0x180081838`
- `0x1800878f0`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800ba45d`
- `0x18017cdb8`
- `0x18017d580`
- `0x180184ac8`
- `0x18018ad90`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040627`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800409f5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040627`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800409f5`
- `RPCRT4!UuidToStringW` at `0x180040974`
- `RPCRT4!UuidToStringW` at `0x180040974`
- `RPCRT4!UuidCreate` at `0x18004094b`
- `RPCRT4!UuidCreate` at `0x18004094b`
- `KERNEL32!CopyFileW` at `0x18004085c`
- `KERNEL32!CopyFileW` at `0x18004085c`

## string_xrefs

- `0x180040647`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180040709`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180040747`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180040997`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180040a0c`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180040ac0`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800405b5`: `LoadingManifestFromDisk_GetManifestReaderFromPath`
- `0x180040815`: `TEMP.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::Deployment::GetManifestReaderFromPath(
        Common::Deployment *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct Common::Deployment::IValidatedManifestReaderHelper *a4)
{
  char v8; // r14
  HRESULT v9; // eax
  unsigned int v10; // ebx
  const struct std::nothrow_t *v11; // rdx
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  int v14; // eax
  const struct std::nothrow_t *v15; // rdx
  int appended; // eax
  __int64 v17; // rdx
  bool v18; // zf
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, Common::Deployment *, __int64); // rbx
  int v21; // edi
  const struct std::nothrow_t *v22; // rdx
  Common *v23; // rcx
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, LPCWSTR, __int64); // rbx
  unsigned int *v26; // r8
  RPC_STATUS v27; // eax
  bool v28; // zf
  HRESULT v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  void *v33; // rsi
  int v34; // eax
  __int64 v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int *ppva; // [rsp+20h] [rbp-E0h]
  void *v41[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+70h] [rbp-90h]
  RPC_WSTR StringUuid; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v47; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v48; // [rsp+88h] [rbp-78h] BYREF
  void *v49[2]; // [rsp+90h] [rbp-70h] BYREF
  int v50; // [rsp+A0h] [rbp-60h]
  _QWORD v51[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v52[4]; // [rsp+C0h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-20h] BYREF
  void **v54; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v55[272]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v56[8]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v57[48]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v54,
    "LoadingManifestFromDisk_GetManifestReaderFromPath");
  v54 = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable';
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::StartActivity(
    (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath *)&v54,
    a2,
    (const unsigned __int16 *)this);
  v8 = 0;
  v48 = 0;
  v47 = 0;
  v43 = 0;
  *(_OWORD *)lpNewFileName = 0;
  v45 = 0;
  Uuid = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v47);
  v9 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v47);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v14 = Common::StringBuffer::SetValueFromString(
            (Common::StringBuffer *)lpNewFileName,
            (const unsigned __int16 *)this);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FE,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v14,
        ppv);
LABEL_16:
      if ( lpNewFileName[1] )
        operator delete((void *)lpNewFileName[1], v15);
LABEL_66:
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
      AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::~LoadingManifestFromDisk_GetManifestReaderFromPath((AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath *)&v54);
      return v10;
    }
    v41[0] = 0;
    v41[1] = 0;
    appended = Common::ImpersonationContext::Impersonate(v41, 0);
    v10 = appended;
    if ( appended < 0 )
    {
      v17 = 514;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)appended,
        ppv);
      v18 = LODWORD(v41[0]) == 0;
      goto LABEL_14;
    }
    v19 = v47;
    v20 = *(__int64 (__fastcall **)(LPVOID, Common::Deployment *, __int64))(*(_QWORD *)v47 + 40LL);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v43);
    ppv = 128;
    v21 = v20(v19, this, 1);
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v41);
    if ( v21 == -2147024864 )
    {
      v51[1] = lpNewFileName;
      v51[0] = &Common::StringBufferBuilder::`vftable';
      v51[2] = lpNewFileName;
      appended = Common::StringBuilder::Delete((Common::StringBuilder *)v51, LODWORD(lpNewFileName[0]) - 4, 4u);
      v10 = appended;
      if ( appended < 0 )
      {
        v17 = 535;
        goto LABEL_13;
      }
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v51, L"TEMP.xml");
      v10 = appended;
      if ( appended < 0 )
      {
        v17 = 536;
        goto LABEL_13;
      }
      appended = Common::ImpersonationContext::Impersonate(v41, 0);
      v10 = appended;
      if ( appended < 0 )
      {
        v17 = 539;
        goto LABEL_13;
      }
      if ( !CopyFileW((LPCWSTR)this, lpNewFileName[1], 0) )
      {
        appended = Common::GetHResultFromLastError(v23);
        v10 = appended;
        if ( appended < 0 )
        {
          v17 = 542;
          goto LABEL_13;
        }
      }
      v24 = v47;
      v25 = *(__int64 (__fastcall **)(LPVOID, LPCWSTR, __int64))(*(_QWORD *)v47 + 40LL);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v43);
      ppv = 128;
      appended = v25(v24, lpNewFileName[1], 1);
      v10 = appended;
      if ( appended < 0 )
      {
        v17 = 551;
        goto LABEL_13;
      }
      v21 = 0;
      v8 = 1;
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v41);
    }
    else if ( v21 < 0 )
    {
      v28 = LODWORD(v41[0]) == 0;
      goto LABEL_61;
    }
    *(_QWORD *)a4 = 0;
    LOBYTE(v42) = 0;
    if ( a3 )
    {
      ppva = &v42;
      (*(void (__fastcall **)(unsigned __int16 *, __int64, Common::Deployment *, const unsigned __int16 *))(*(_QWORD *)a3 + 16LL))(
        a3,
        v43,
        this,
        a2);
      a3 = 0;
      if ( *(_QWORD *)a4 )
      {
LABEL_33:
        if ( v8 )
        {
          if ( (int)AppXDeleteFile(lpNewFileName[1], (unsigned int)v22, v26) < 0 )
          {
            v27 = UuidCreate(&Uuid);
            if ( !v27 || v27 == 1824 )
            {
              StringUuid = a3;
              if ( UuidToStringW(&Uuid, &StringUuid) )
              {
                v10 = -2147418113;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x25A,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
                  (const char *)0x8000FFFFLL,
                  (int)ppva);
LABEL_39:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
LABEL_45:
                v18 = LODWORD(v41[0]) == (_DWORD)a3;
LABEL_14:
                if ( !v18 )
                  Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v41);
                goto LABEL_16;
              }
              v31 = -1;
              do
                ++v31;
              while ( StringUuid[v31] != (_WORD)a3 );
              v32 = (unsigned int)(v31 + 1);
              v33 = operator new[](saturated_mul(v32, 2u));
              v52[3] = v33;
              memcpy_0(v33, StringUuid, 2 * v32);
              *(_OWORD *)v49 = 0;
              v50 = (int)a3;
              v34 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v49, (const unsigned __int16 *)v33);
              v10 = v34;
              if ( v34 < 0 )
              {
                v35 = 613;
LABEL_52:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v35,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
                  (const char *)(unsigned int)v34,
                  (int)ppva);
                if ( v49[1] )
                  operator delete(v49[1], v36);
                operator delete(v33, v36);
                goto LABEL_39;
              }
              v52[1] = v49;
              v52[0] = &Common::StringBufferBuilder::`vftable';
              v52[2] = v49;
              v34 = Common::StringBuilder::AppendString(
                      (Common::StringBuilder *)v52,
                      L"_1.0.0.0_neutral_neutral_nopublisherid");
              v10 = v34;
              if ( v34 < 0 )
              {
                v35 = 615;
                goto LABEL_52;
              }
              ReliableCleanup::CleanupManager::AddToPurgeList(v49[1], 0, lpNewFileName[1]);
              if ( v49[1] )
                operator delete(v49[1], v37);
              operator delete(v33, v37);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
            }
          }
        }
        wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          &v54,
          (unsigned int)v21);
        v28 = LODWORD(v41[0]) == (_DWORD)a3;
LABEL_61:
        if ( !v28 )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v41);
        if ( lpNewFileName[1] )
          operator delete((void *)lpNewFileName[1], v22);
        v10 = v21;
        goto LABEL_66;
      }
    }
    Common::Deployment::PrefetchFile(this, (const unsigned __int16 *)v22);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
    v29 = CoCreateInstance(
            &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
            0,
            1u,
            &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
            &v48);
    v10 = v29;
    if ( v29 >= 0 )
    {
      v29 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct Common::Deployment::IValidatedManifestReaderHelper *))(*(_QWORD *)v48 + 40LL))(
              v48,
              v43,
              a4);
      v10 = v29;
      if ( v29 >= 0 )
        goto LABEL_33;
      v30 = 588;
    }
    else
    {
      v30 = 587;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
      (const char *)(unsigned int)v29,
      (int)ppva);
    goto LABEL_45;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1FB,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)(unsigned int)v9,
    ppv);
  if ( lpNewFileName[1] )
    operator delete((void *)lpNewFileName[1], v11);
  v12 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v54 = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable';
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v57);
  wil::details::shared_object<wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v56);
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>(v55);
  return v10;
}

```

## disassembly

```asm
0x18004057c  push    rbp
0x18004057e  push    rbx
0x18004057f  push    rsi
0x180040580  push    rdi
0x180040581  push    r12
0x180040583  push    r13
0x180040585  push    r14
0x180040587  push    r15
0x180040589  lea     rbp, [rsp-158h]
0x180040591  sub     rsp, 258h
0x180040598  mov     rax, cs:__security_cookie
0x18004059f  xor     rax, rsp
0x1800405a2  mov     [rbp+190h+var_50], rax
0x1800405a9  mov     r15, r9
0x1800405ac  mov     r12, r8
0x1800405af  mov     r13, rdx
0x1800405b2  mov     rsi, rcx
0x1800405b5  lea     rdx, aLoadingmanifes; "LoadingManifestFromDisk_GetManifestRead"...
0x1800405bc  lea     rcx, [rbp+190h+var_1A0]
0x1800405c0  call    ??0?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800405c5  lea     rdi, ??_7LoadingManifestFromDisk_GetManifestReaderFromPath@AppXDeploymentServerTelemetry@@6B@; const AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable'
0x1800405cc  mov     [rbp+190h+var_1A0], rdi
0x1800405d0  mov     r8, rsi; unsigned __int16 *
0x1800405d3  mov     rdx, r13; unsigned __int16 *
0x1800405d6  lea     rcx, [rbp+190h+var_1A0]; this
0x1800405da  call    ?StartActivity@LoadingManifestFromDisk_GetManifestReaderFromPath@AppXDeploymentServerTelemetry@@QEAAXPEBG0@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::StartActivity(ushort const *,ushort const *)
0x1800405df  nop
0x1800405e0  xor     r14d, r14d
0x1800405e3  mov     [rbp+190h+var_208], r14
0x1800405e7  mov     [rbp+190h+var_210], r14
0x1800405eb  mov     [rsp+290h+var_238], r14
0x1800405f0  xorps   xmm0, xmm0
0x1800405f3  movups  xmmword ptr [rsp+290h+lpNewFileName], xmm0
0x1800405f8  mov     [rsp+290h+var_220], r14d
0x1800405fd  movups  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x180040601  lea     rcx, [rbp+190h+var_210]
0x180040605  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18004060a  lea     rax, [rbp+190h+var_210]
0x18004060e  mov     [rsp+290h+ppv], rax; int
0x180040613  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x18004061a  xor     edx, edx; pUnkOuter
0x18004061c  lea     r8d, [r14+1]; dwClsContext
0x180040620  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x180040627  call    cs:__imp_CoCreateInstance
0x18004062e  nop     dword ptr [rax+rax+00h]
0x180040633  mov     ebx, eax
0x180040635  test    eax, eax
0x180040637  jns     loc_1800406EC
0x18004063d  mov     rcx, [rbp+198h]; this
0x180040644  mov     r9d, eax; char *
0x180040647  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18004064e  mov     edx, 1FBh; void *
0x180040653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040658  nop
0x180040659  mov     rcx, [rsp+290h+lpNewFileName+8]; void *
0x18004065e  test    rcx, rcx
0x180040661  jz      short loc_180040669
0x180040663  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040668  nop
0x180040669  mov     rcx, [rsp+290h+var_238]
0x18004066e  test    rcx, rcx
0x180040671  jz      short loc_180040685
0x180040673  mov     [rsp+290h+var_238], r14
0x180040678  mov     rax, [rcx]
0x18004067b  mov     rax, [rax+10h]
0x18004067f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040684  nop
0x180040685  mov     rcx, [rbp+190h+var_210]
0x180040689  test    rcx, rcx
0x18004068c  jz      short loc_18004069F
0x18004068e  mov     [rbp+190h+var_210], r14
0x180040692  mov     rax, [rcx]
0x180040695  mov     rax, [rax+10h]
0x180040699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004069e  nop
0x18004069f  mov     rcx, [rbp+190h+var_208]
0x1800406a3  test    rcx, rcx
0x1800406a6  jz      short loc_1800406B9
0x1800406a8  mov     [rbp+190h+var_208], r14
0x1800406ac  mov     rax, [rcx]
0x1800406af  mov     rax, [rax+10h]
0x1800406b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406b8  nop
0x1800406b9  mov     [rbp+190h+var_1A0], rdi
0x1800406bd  lea     rcx, [rbp+190h+var_1A0]
0x1800406c1  call    ?Destroy@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800406c6  lea     rcx, [rbp+190h+var_80]; this
0x1800406cd  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800406d2  lea     rcx, [rbp+190h+var_88]
0x1800406d9  call    ?reset@?$shared_object@V?$ActivityData@VAppXDeploymentServerTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800406de  lea     rcx, [rbp+190h+var_198]
0x1800406e2  call    ??1?$ActivityData@VAppXDeploymentServerTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800406e7  jmp     loc_180040BB2
0x1800406ec  mov     rdx, rsi; unsigned __int16 *
0x1800406ef  lea     rcx, [rsp+290h+lpNewFileName]; this
0x1800406f4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800406f9  mov     ebx, eax
0x1800406fb  test    eax, eax
0x1800406fd  jns     short loc_18004071C
0x1800406ff  mov     rcx, [rbp+198h]; this
0x180040706  mov     r9d, eax; char *
0x180040709  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180040710  mov     edx, 1FEh; void *
0x180040715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004071a  jmp     short loc_180040766
0x18004071c  mov     [rsp+290h+var_250], r14
0x180040721  mov     [rsp+290h+var_248], r14
0x180040726  xor     edx, edx; void *
0x180040728  lea     rcx, [rsp+290h+var_250]; this
0x18004072d  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180040732  mov     ebx, eax
0x180040734  test    eax, eax
0x180040736  jns     short loc_18004077E
0x180040738  mov     edx, 202h; void *
0x18004073d  mov     rcx, [rbp+198h]; this
0x180040744  mov     r9d, eax; char *
0x180040747  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18004074e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040753  nop
0x180040754  cmp     dword ptr [rsp+290h+var_250], r14d
0x180040759  jz      short loc_180040766
0x18004075b  lea     rcx, [rsp+290h+var_250]; this
0x180040760  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180040765  nop
0x180040766  mov     rcx, [rsp+290h+lpNewFileName+8]; void *
0x18004076b  test    rcx, rcx
0x18004076e  jz      loc_180040B8A
0x180040774  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040779  jmp     loc_180040B8A
0x18004077e  mov     rdi, [rbp+190h+var_210]
0x180040782  mov     rax, [rdi]
0x180040785  mov     rbx, [rax+28h]
0x180040789  lea     rcx, [rsp+290h+var_238]
0x18004078e  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180040793  lea     rax, [rsp+290h+var_238]
0x180040798  mov     [rsp+290h+var_268], rax
0x18004079d  mov     dword ptr [rsp+290h+ppv], 80h
0x1800407a5  xor     r9d, r9d
0x1800407a8  lea     r8d, [r9+1]
0x1800407ac  mov     rdx, rsi
0x1800407af  mov     rcx, rdi
0x1800407b2  mov     rax, rbx
0x1800407b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ba  mov     edi, eax
0x1800407bc  lea     rcx, [rsp+290h+var_250]; this
0x1800407c1  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800407c6  lea     rcx, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800407cd  cmp     edi, 80070020h
0x1800407d3  jnz     loc_1800409B5
0x1800407d9  lea     rax, [rsp+290h+lpNewFileName]
0x1800407de  mov     [rbp+190h+var_1E0], rax
0x1800407e2  mov     [rbp+190h+var_1E8], rcx
0x1800407e6  lea     rax, [rsp+290h+lpNewFileName]
0x1800407eb  mov     [rbp+190h+var_1D8], rax
0x1800407ef  mov     edx, dword ptr [rsp+290h+lpNewFileName]
0x1800407f3  add     edx, 0FFFFFFFCh; unsigned int
0x1800407f6  mov     r8d, 4; unsigned int
0x1800407fc  lea     rcx, [rbp+190h+var_1E8]; this
0x180040800  call    ?Delete@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Delete(ulong,ulong)
0x180040805  mov     ebx, eax
0x180040807  test    eax, eax
0x180040809  jns     short loc_180040815
0x18004080b  mov     edx, 217h
0x180040810  jmp     loc_18004073D
0x180040815  lea     rdx, aTempXml; "TEMP.xml"
0x18004081c  lea     rcx, [rbp+190h+var_1E8]; this
0x180040820  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180040825  mov     ebx, eax
0x180040827  test    eax, eax
0x180040829  jns     short loc_180040835
0x18004082b  mov     edx, 218h
0x180040830  jmp     loc_18004073D
0x180040835  xor     edx, edx; void *
0x180040837  lea     rcx, [rsp+290h+var_250]; this
0x18004083c  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180040841  mov     ebx, eax
0x180040843  test    eax, eax
0x180040845  jns     short loc_180040851
0x180040847  mov     edx, 21Bh
0x18004084c  jmp     loc_18004073D
0x180040851  xor     r8d, r8d; bFailIfExists
0x180040854  mov     rdx, [rsp+290h+lpNewFileName+8]; lpNewFileName
0x180040859  mov     rcx, rsi; lpExistingFileName
0x18004085c  call    cs:__imp_CopyFileW
0x180040863  nop     dword ptr [rax+rax+00h]
0x180040868  test    eax, eax
0x18004086a  jnz     short loc_180040881
0x18004086c  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180040871  mov     ebx, eax
0x180040873  test    eax, eax
0x180040875  jns     short loc_180040881
0x180040877  mov     edx, 21Eh
0x18004087c  jmp     loc_18004073D
0x180040881  mov     rdi, [rbp+190h+var_210]
0x180040885  mov     rax, [rdi]
0x180040888  mov     rbx, [rax+28h]
0x18004088c  lea     rcx, [rsp+290h+var_238]
0x180040891  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180040896  lea     rax, [rsp+290h+var_238]
0x18004089b  mov     [rsp+290h+var_268], rax
0x1800408a0  mov     dword ptr [rsp+290h+ppv], 80h
0x1800408a8  xor     r9d, r9d
0x1800408ab  lea     r8d, [r9+1]
0x1800408af  mov     rdx, [rsp+290h+lpNewFileName+8]
0x1800408b4  mov     rcx, rdi
0x1800408b7  mov     rax, rbx
0x1800408ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408bf  mov     ebx, eax
0x1800408c1  test    eax, eax
0x1800408c3  jns     short loc_1800408CF
0x1800408c5  mov     edx, 227h
0x1800408ca  jmp     loc_18004073D
0x1800408cf  mov     edi, r14d
0x1800408d2  mov     r14b, 1
0x1800408d5  lea     rcx, [rsp+290h+var_250]; this
0x1800408da  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800408df  xor     ecx, ecx
0x1800408e1  mov     [r15], rcx
0x1800408e4  mov     byte ptr [rsp+290h+var_240], cl
0x1800408e8  test    r12, r12
0x1800408eb  jz      loc_1800409C7
0x1800408f1  mov     rax, [r12]
0x1800408f5  mov     [rsp+290h+var_260], rcx
0x1800408fa  mov     [rsp+290h+var_268], r15
0x1800408ff  lea     rcx, [rsp+290h+var_240]
0x180040904  mov     [rsp+290h+ppv], rcx; int
0x180040909  mov     r9, r13
0x18004090c  mov     r8, rsi
0x18004090f  mov     rdx, [rsp+290h+var_238]
0x180040914  mov     rcx, r12
0x180040917  mov     rax, [rax+10h]
0x18004091b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040920  xor     r12d, r12d
0x180040923  cmp     [r15], r12
0x180040926  jz      loc_1800409C7
0x18004092c  test    r14b, r14b
0x18004092f  jz      loc_180040B5B
0x180040935  mov     rcx, [rsp+290h+lpNewFileName+8]; lpFileName
0x18004093a  call    ?AppXDeleteFile@@YAJPEAGKPEAK@Z; AppXDeleteFile(ushort *,ulong,ulong *)
0x18004093f  test    eax, eax
0x180040941  jns     loc_180040B5B
0x180040947  lea     rcx, [rbp+190h+Uuid]; Uuid
0x18004094b  call    cs:__imp_UuidCreate
0x180040952  nop     dword ptr [rax+rax+00h]
0x180040957  test    eax, eax
0x180040959  jz      short loc_180040966
0x18004095b  cmp     eax, 720h
0x180040960  jnz     loc_180040B5B
0x180040966  mov     [rsp+290h+StringUuid], r12
0x18004096b  lea     rdx, [rsp+290h+StringUuid]; StringUuid
0x180040970  lea     rcx, [rbp+190h+Uuid]; Uuid
0x180040974  call    cs:__imp_UuidToStringW
0x18004097b  nop     dword ptr [rax+rax+00h]
0x180040980  test    eax, eax
0x180040982  jz      loc_180040A56
0x180040988  mov     rcx, [rbp+198h]; this
0x18004098f  mov     ebx, 8000FFFFh
0x180040994  mov     r9d, ebx; char *
0x180040997  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18004099e  mov     edx, 25Ah; void *
0x1800409a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800409a8  nop
0x1800409a9  lea     rcx, [rsp+290h+StringUuid]
0x1800409ae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800409b3  jmp     short loc_180040A23
0x1800409b5  test    edi, edi
0x1800409b7  jns     loc_1800408DF
0x1800409bd  cmp     dword ptr [rsp+290h+var_250], r14d
0x1800409c2  jmp     loc_180040B6C
0x1800409c7  mov     rcx, rsi; this
0x1800409ca  call    ?PrefetchFile@Deployment@Common@@YAJPEBG@Z; Common::Deployment::PrefetchFile(ushort const *)
0x1800409cf  lea     rcx, [rbp+190h+var_208]
0x1800409d3  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800409d8  lea     rax, [rbp+190h+var_208]
0x1800409dc  mov     [rsp+290h+ppv], rax; int
0x1800409e1  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800409e8  xor     edx, edx; pUnkOuter
0x1800409ea  lea     r8d, [rdx+1]; dwClsContext
0x1800409ee  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800409f5  call    cs:__imp_CoCreateInstance
0x1800409fc  nop     dword ptr [rax+rax+00h]
0x180040a01  mov     ebx, eax
0x180040a03  test    eax, eax
0x180040a05  jns     short loc_180040A2D
0x180040a07  mov     edx, 24Bh; void *
0x180040a0c  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180040a13  mov     r9d, eax; char *
0x180040a16  mov     rcx, [rbp+198h]; this
0x180040a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040a22  nop
0x180040a23  cmp     dword ptr [rsp+290h+var_250], r12d
0x180040a28  jmp     loc_180040759
0x180040a2d  mov     rcx, [rbp+190h+var_208]
0x180040a31  mov     rax, [rcx]
0x180040a34  mov     r8, r15
0x180040a37  mov     rdx, [rsp+290h+var_238]
0x180040a3c  mov     rax, [rax+28h]
0x180040a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a45  mov     ebx, eax
0x180040a47  test    eax, eax
  ... truncated ...
```
