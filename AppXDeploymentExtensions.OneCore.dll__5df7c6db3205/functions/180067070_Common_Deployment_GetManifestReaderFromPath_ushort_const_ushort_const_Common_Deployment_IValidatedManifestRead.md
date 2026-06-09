# Common::Deployment::GetManifestReaderFromPath(ushort const *,ushort const *,Common::Deployment::IValidatedManifestReaderHelper *,IAppxManifestReader * *)

- ea: `0x180067070`
- end: `0x18006782d`
- name: `?GetManifestReaderFromPath@Deployment@Common@@YAJPEBG0PEAVIValidatedManifestReaderHelper@12@PEAPEAUIAppxManifestReader@@@Z`
- size: `1981`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Common::Deployment::IValidatedManifestReaderHelper *, struct IAppxManifestReader **)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800be454`
- `0x1801ec160`

## callees

- `0x18000b3bc`
- `0x18000e6e0`
- `0x18000fed0`
- `0x18002cc90`
- `0x180056994`
- `0x180057010`
- `0x180067070`
- `0x180068764`
- `0x18008cad0`
- `0x180098bf4`
- `0x1800ac7a8`
- `0x1800ac80c`
- `0x1800ac8ac`
- `0x1800ac904`
- `0x1800ac9a0`
- `0x1800aca58`
- `0x1800ae314`
- `0x1800ce12c`
- `0x1800db7bc`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1800fc211`
- `0x1801d9a38`
- `0x1801e33a4`
- `0x1801efe4c`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006711e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800675bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006711e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800675bf`
- `RPCRT4!UuidToStringW` at `0x18006751f`
- `RPCRT4!UuidToStringW` at `0x18006751f`
- `RPCRT4!UuidCreate` at `0x1800674fc`
- `RPCRT4!UuidCreate` at `0x1800674fc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800673bb`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800673bb`

## string_xrefs

- `0x1800670a9`: `LoadingManifestFromDisk_GetManifestReaderFromPath`
- `0x180067138`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800671fd`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067239`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800672fa`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067343`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067388`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800673da`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067451`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x18006753c`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800675d5`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x18006762b`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800676c0`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067742`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180067323`: `TEMP.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Common::Deployment::GetManifestReaderFromPath(
        Common::Deployment *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct Common::Deployment::IValidatedManifestReaderHelper *a4)
{
  char v8; // r14
  HRESULT v9; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // rdx
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  int v14; // eax
  int v15; // eax
  LPVOID v16; // rdi
  __int64 (__fastcall *v17)(LPVOID, Common::Deployment *, __int64); // rbx
  int v18; // edi
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  int appended; // eax
  int v22; // eax
  Common *v23; // rcx
  int HResultFromLastError; // eax
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, LPCWSTR, __int64); // rbx
  int v27; // eax
  RPC_STATUS v28; // eax
  HRESULT v29; // eax
  int v30; // eax
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  void *v33; // rsi
  int v34; // eax
  unsigned __int64 v35; // rdx
  int v36; // eax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int *ppva; // [rsp+20h] [rbp-E0h]
  _QWORD v42[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v46; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v47; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+88h] [rbp-78h]
  __int128 v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+A0h] [rbp-60h]
  _QWORD v52[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v53[4]; // [rsp+C0h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-20h] BYREF
  void **v55; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v56[272]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v57[8]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v58[48]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v55);
  v55 = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable';
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::StartActivity(
    (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath *)&v55,
    a2,
    (const unsigned __int16 *)this);
  v8 = 0;
  v47 = 0;
  v46 = 0;
  v44 = 0;
  *(_OWORD *)lpNewFileName = 0;
  v49 = 0;
  Uuid = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v9 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v46);
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
LABEL_74:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::~LoadingManifestFromDisk_GetManifestReaderFromPath((AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath *)&v55);
      return v10;
    }
    v42[0] = 0;
    v42[1] = 0;
    v15 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v42, 0);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      if ( LODWORD(v42[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
      goto LABEL_74;
    }
    v16 = v46;
    v17 = *(__int64 (__fastcall **)(LPVOID, Common::Deployment *, __int64))(*(_QWORD *)v46 + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v18 = v17(v16, this, 1);
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
    if ( v18 == -2147024864 )
    {
      v52[1] = lpNewFileName;
      v52[0] = &Common::StringBufferBuilder::`vftable';
      v52[2] = lpNewFileName;
      v20 = Common::StringBuilder::Delete((Common::StringBuilder *)v52, LODWORD(lpNewFileName[0]) - 4, 4u);
      v10 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x217,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v20,
          128);
        if ( LODWORD(v42[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v52, L"TEMP.xml");
      v10 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x218,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)appended,
          128);
        if ( LODWORD(v42[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
      v22 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v42, 0);
      v10 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21B,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v22,
          128);
        if ( LODWORD(v42[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
      if ( !CopyFileW((LPCWSTR)this, lpNewFileName[1], 0) )
      {
        HResultFromLastError = Common::GetHResultFromLastError(v23);
        v10 = HResultFromLastError;
        if ( HResultFromLastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)HResultFromLastError,
            128);
          if ( LODWORD(v42[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
          goto LABEL_74;
        }
      }
      v25 = v46;
      v26 = *(__int64 (__fastcall **)(LPVOID, LPCWSTR, __int64))(*(_QWORD *)v46 + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      v27 = v26(v25, lpNewFileName[1], 1);
      v10 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v27,
          128);
        if ( LODWORD(v42[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
      v18 = 0;
      v8 = 1;
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
    }
    else if ( v18 < 0 )
    {
      if ( LODWORD(v42[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
LABEL_73:
      v10 = v18;
      goto LABEL_74;
    }
    *(_QWORD *)a4 = 0;
    LOBYTE(v43) = 0;
    if ( !a3
      || (ppva = &v43,
          (*(void (__fastcall **)(unsigned __int16 *, __int64, Common::Deployment *, const unsigned __int16 *))(*(_QWORD *)a3 + 16LL))(
            a3,
            v44,
            this,
            a2),
          a3 = 0,
          !*(_QWORD *)a4) )
    {
      Common::Deployment::PrefetchFile(this, v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v29 = CoCreateInstance(
              &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
              0,
              1u,
              &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
              &v47);
      v10 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24B,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v29,
          (int)ppva);
        if ( LODWORD(v42[0]) != (_DWORD)a3 )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
      v30 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct Common::Deployment::IValidatedManifestReaderHelper *))(*(_QWORD *)v47 + 40LL))(
              v47,
              v44,
              a4);
      v10 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24C,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v30,
          (int)ppva);
        if ( LODWORD(v42[0]) != (_DWORD)a3 )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        goto LABEL_74;
      }
    }
    if ( v8 )
    {
      if ( (int)AppXDeleteFile(lpNewFileName[1], 1u, 0) < 0 )
      {
        v28 = UuidCreate(&Uuid);
        if ( !v28 || v28 == 1824 )
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
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
            if ( LODWORD(v42[0]) != (_DWORD)a3 )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
            goto LABEL_74;
          }
          v31 = -1;
          do
            ++v31;
          while ( StringUuid[v31] != (_WORD)a3 );
          v32 = (unsigned int)(v31 + 1);
          v33 = operator new[](saturated_mul(v32, 2u));
          v53[3] = v33;
          memcpy_0(v33, StringUuid, 2 * v32);
          v50 = 0;
          v51 = (int)a3;
          v34 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v50, (const unsigned __int16 *)v33);
          v10 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x265,
              (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
              (const char *)(unsigned int)v34,
              (int)ppva);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v50);
            operator delete(v33, v35);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
            if ( LODWORD(v42[0]) != (_DWORD)a3 )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
            goto LABEL_74;
          }
          v53[1] = &v50;
          v53[0] = &Common::StringBufferBuilder::`vftable';
          v53[2] = &v50;
          v36 = Common::StringBuilder::AppendString(
                  (Common::StringBuilder *)v53,
                  L"_1.0.0.0_neutral_neutral_nopublisherid");
          v10 = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x267,
              (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
              (const char *)(unsigned int)v36,
              (int)ppva);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v50);
            operator delete(v33, v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
            if ( LODWORD(v42[0]) != (_DWORD)a3 )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
            goto LABEL_74;
          }
          ReliableCleanup::CleanupManager::AddToPurgeList(*((_QWORD *)&v50 + 1), 0, lpNewFileName[1]);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v50);
          operator delete(v33, v38);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
        }
      }
    }
    wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v55,
      (unsigned int)v18);
    if ( LODWORD(v42[0]) != (_DWORD)a3 )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
    goto LABEL_73;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1FB,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)(unsigned int)v9,
    ppv);
  if ( lpNewFileName[1] )
    operator delete((void *)lpNewFileName[1], v11);
  v12 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v55 = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable';
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v55);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v58);
  wil::details::shared_object<wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v57);
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>(v56);
  return v10;
}

```

## disassembly

```asm
0x180067070  push    rbp
0x180067072  push    rbx
0x180067073  push    rsi
0x180067074  push    rdi
0x180067075  push    r12
0x180067077  push    r13
0x180067079  push    r14
0x18006707b  push    r15
0x18006707d  lea     rbp, [rsp-158h]
0x180067085  sub     rsp, 258h
0x18006708c  mov     rax, cs:__security_cookie
0x180067093  xor     rax, rsp
0x180067096  mov     [rbp+190h+var_50], rax
0x18006709d  mov     r15, r9
0x1800670a0  mov     r12, r8
0x1800670a3  mov     r13, rdx
0x1800670a6  mov     rsi, rcx
0x1800670a9  lea     rdx, aLoadingmanifes; "LoadingManifestFromDisk_GetManifestRead"...
0x1800670b0  lea     rcx, [rbp+190h+var_1A0]; struct wil::details::IFailureCallback *
0x1800670b4  call    ??0?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800670b9  lea     rdi, ??_7LoadingManifestFromDisk_GetManifestReaderFromPath@AppXDeploymentServerTelemetry@@6B@; const AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::`vftable'
0x1800670c0  mov     [rbp+190h+var_1A0], rdi
0x1800670c4  mov     r8, rsi; unsigned __int16 *
0x1800670c7  mov     rdx, r13; unsigned __int16 *
0x1800670ca  lea     rcx, [rbp+190h+var_1A0]; this
0x1800670ce  call    ?StartActivity@LoadingManifestFromDisk_GetManifestReaderFromPath@AppXDeploymentServerTelemetry@@QEAAXPEBG0@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromPath::StartActivity(ushort const *,ushort const *)
0x1800670d3  nop
0x1800670d4  xor     r14d, r14d
0x1800670d7  mov     [rsp+290h+var_220], r14
0x1800670dc  mov     [rsp+290h+var_228], r14
0x1800670e1  mov     [rsp+290h+var_238], r14
0x1800670e6  xorps   xmm0, xmm0
0x1800670e9  movups  xmmword ptr [rsp+290h+lpNewFileName], xmm0
0x1800670ee  mov     [rbp+190h+var_208], r14d
0x1800670f2  movups  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x1800670f6  lea     rcx, [rsp+290h+var_228]
0x1800670fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067100  lea     rax, [rsp+290h+var_228]
0x180067105  mov     [rsp+290h+ppv], rax; int
0x18006710a  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180067111  xor     edx, edx; pUnkOuter
0x180067113  lea     r8d, [r14+1]; dwClsContext
0x180067117  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x18006711e  call    cs:__imp_CoCreateInstance
0x180067124  mov     ebx, eax
0x180067126  test    eax, eax
0x180067128  jns     loc_1800671E0
0x18006712e  mov     rcx, [rbp+198h]; this
0x180067135  mov     r9d, eax; char *
0x180067138  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18006713f  mov     edx, 1FBh; void *
0x180067144  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067149  nop
0x18006714a  mov     rcx, [rbp+190h+lpNewFileName+8]; void *
0x18006714e  test    rcx, rcx
0x180067151  jz      short loc_180067159
0x180067153  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180067158  nop
0x180067159  mov     rcx, [rsp+290h+var_238]
0x18006715e  test    rcx, rcx
0x180067161  jz      short loc_180067175
0x180067163  mov     [rsp+290h+var_238], r14
0x180067168  mov     rax, [rcx]
0x18006716b  mov     rax, [rax+10h]
0x18006716f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067174  nop
0x180067175  mov     rcx, [rsp+290h+var_228]
0x18006717a  test    rcx, rcx
0x18006717d  jz      short loc_180067191
0x18006717f  mov     [rsp+290h+var_228], r14
0x180067184  mov     rax, [rcx]
0x180067187  mov     rax, [rax+10h]
0x18006718b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067190  nop
0x180067191  mov     rcx, [rsp+290h+var_220]
0x180067196  test    rcx, rcx
0x180067199  jz      short loc_1800671AD
0x18006719b  mov     [rsp+290h+var_220], r14
0x1800671a0  mov     rax, [rcx]
0x1800671a3  mov     rax, [rax+10h]
0x1800671a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671ac  nop
0x1800671ad  mov     [rbp+190h+var_1A0], rdi
0x1800671b1  lea     rcx, [rbp+190h+var_1A0]
0x1800671b5  call    ?Destroy@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800671ba  lea     rcx, [rbp+190h+var_80]; this
0x1800671c1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800671c6  lea     rcx, [rbp+190h+var_88]
0x1800671cd  call    ?reset@?$shared_object@V?$ActivityData@VAppXDeploymentServerTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800671d2  lea     rcx, [rbp+190h+var_198]
0x1800671d6  call    ??1?$ActivityData@VAppXDeploymentServerTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AppXDeploymentServerTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800671db  jmp     loc_180067808
0x1800671e0  mov     rdx, rsi; unsigned __int16 *
0x1800671e3  lea     rcx, [rsp+290h+lpNewFileName]; this
0x1800671e8  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800671ed  mov     ebx, eax
0x1800671ef  test    eax, eax
0x1800671f1  jns     short loc_180067213
0x1800671f3  mov     rcx, [rbp+198h]; this
0x1800671fa  mov     r9d, eax; char *
0x1800671fd  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180067204  mov     edx, 1FEh; void *
0x180067209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006720e  jmp     loc_1800677D3
0x180067213  mov     [rsp+290h+var_250], r14
0x180067218  mov     [rsp+290h+var_248], r14
0x18006721d  xor     edx, edx; void *
0x18006721f  lea     rcx, [rsp+290h+var_250]; this
0x180067224  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180067229  mov     ebx, eax
0x18006722b  test    eax, eax
0x18006722d  jns     short loc_180067262
0x18006722f  mov     rcx, [rbp+198h]; this
0x180067236  mov     r9d, eax; char *
0x180067239  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180067240  mov     edx, 202h; void *
0x180067245  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006724a  nop
0x18006724b  cmp     dword ptr [rsp+290h+var_250], r14d
0x180067250  jz      short loc_18006725D
0x180067252  lea     rcx, [rsp+290h+var_250]; this
0x180067257  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18006725c  nop
0x18006725d  jmp     loc_1800677D3
0x180067262  mov     rdi, [rsp+290h+var_228]
0x180067267  mov     rax, [rdi]
0x18006726a  mov     rbx, [rax+28h]
0x18006726e  lea     rcx, [rsp+290h+var_238]
0x180067273  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067278  lea     rax, [rsp+290h+var_238]
0x18006727d  mov     [rsp+290h+var_268], rax
0x180067282  mov     dword ptr [rsp+290h+ppv], 80h; int
0x18006728a  xor     r9d, r9d
0x18006728d  lea     r8d, [r9+1]
0x180067291  mov     rdx, rsi
0x180067294  mov     rcx, rdi
0x180067297  mov     rax, rbx
0x18006729a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006729f  mov     edi, eax
0x1800672a1  lea     rcx, [rsp+290h+var_250]; this
0x1800672a6  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800672ab  lea     rcx, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800672b2  cmp     edi, 80070020h
0x1800672b8  jnz     loc_180067570
0x1800672be  lea     rax, [rsp+290h+lpNewFileName]
0x1800672c3  mov     [rbp+190h+var_1E0], rax
0x1800672c7  mov     [rbp+190h+var_1E8], rcx
0x1800672cb  lea     rax, [rsp+290h+lpNewFileName]
0x1800672d0  mov     [rbp+190h+var_1D8], rax
0x1800672d4  mov     edx, dword ptr [rsp+290h+lpNewFileName]
0x1800672d8  add     edx, 0FFFFFFFCh; unsigned int
0x1800672db  mov     r8d, 4; unsigned int
0x1800672e1  lea     rcx, [rbp+190h+var_1E8]; this
0x1800672e5  call    ?Delete@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Delete(ulong,ulong)
0x1800672ea  mov     ebx, eax
0x1800672ec  test    eax, eax
0x1800672ee  jns     short loc_180067323
0x1800672f0  mov     rcx, [rbp+198h]; this
0x1800672f7  mov     r9d, eax; char *
0x1800672fa  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180067301  mov     edx, 217h; void *
0x180067306  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006730b  nop
0x18006730c  cmp     dword ptr [rsp+290h+var_250], r14d
0x180067311  jz      short loc_18006731E
0x180067313  lea     rcx, [rsp+290h+var_250]; this
0x180067318  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18006731d  nop
0x18006731e  jmp     loc_1800677D3
0x180067323  lea     rdx, aTempXml; "TEMP.xml"
0x18006732a  lea     rcx, [rbp+190h+var_1E8]; this
0x18006732e  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180067333  mov     ebx, eax
0x180067335  test    eax, eax
0x180067337  jns     short loc_18006736C
0x180067339  mov     rcx, [rbp+198h]; this
0x180067340  mov     r9d, eax; char *
0x180067343  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18006734a  mov     edx, 218h; void *
0x18006734f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067354  nop
0x180067355  cmp     dword ptr [rsp+290h+var_250], r14d
0x18006735a  jz      short loc_180067367
0x18006735c  lea     rcx, [rsp+290h+var_250]; this
0x180067361  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180067366  nop
0x180067367  jmp     loc_1800677D3
0x18006736c  xor     edx, edx; void *
0x18006736e  lea     rcx, [rsp+290h+var_250]; this
0x180067373  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180067378  mov     ebx, eax
0x18006737a  test    eax, eax
0x18006737c  jns     short loc_1800673B1
0x18006737e  mov     rcx, [rbp+198h]; this
0x180067385  mov     r9d, eax; char *
0x180067388  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18006738f  mov     edx, 21Bh; void *
0x180067394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067399  nop
0x18006739a  cmp     dword ptr [rsp+290h+var_250], r14d
0x18006739f  jz      short loc_1800673AC
0x1800673a1  lea     rcx, [rsp+290h+var_250]; this
0x1800673a6  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800673ab  nop
0x1800673ac  jmp     loc_1800677D3
0x1800673b1  xor     r8d, r8d; bFailIfExists
0x1800673b4  mov     rdx, [rbp+190h+lpNewFileName+8]; lpNewFileName
0x1800673b8  mov     rcx, rsi; lpExistingFileName
0x1800673bb  call    cs:__imp_CopyFileW
0x1800673c1  test    eax, eax
0x1800673c3  jnz     short loc_180067403
0x1800673c5  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800673ca  mov     ebx, eax
0x1800673cc  test    eax, eax
0x1800673ce  jns     short loc_180067403
0x1800673d0  mov     rcx, [rbp+198h]; this
0x1800673d7  mov     r9d, eax; char *
0x1800673da  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1800673e1  mov     edx, 21Eh; void *
0x1800673e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800673eb  nop
0x1800673ec  cmp     dword ptr [rsp+290h+var_250], r14d
0x1800673f1  jz      short loc_1800673FE
0x1800673f3  lea     rcx, [rsp+290h+var_250]; this
0x1800673f8  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800673fd  nop
0x1800673fe  jmp     loc_1800677D3
0x180067403  mov     rdi, [rsp+290h+var_228]
0x180067408  mov     rax, [rdi]
0x18006740b  mov     rbx, [rax+28h]
0x18006740f  lea     rcx, [rsp+290h+var_238]
0x180067414  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067419  lea     rax, [rsp+290h+var_238]
0x18006741e  mov     [rsp+290h+var_268], rax
0x180067423  mov     dword ptr [rsp+290h+ppv], 80h; int
0x18006742b  xor     r9d, r9d
0x18006742e  lea     r8d, [r9+1]
0x180067432  mov     rdx, [rbp+190h+lpNewFileName+8]
0x180067436  mov     rcx, rdi
0x180067439  mov     rax, rbx
0x18006743c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067441  mov     ebx, eax
0x180067443  test    eax, eax
0x180067445  jns     short loc_18006747A
0x180067447  mov     rcx, [rbp+198h]; this
0x18006744e  mov     r9d, eax; char *
0x180067451  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x180067458  mov     edx, 227h; void *
0x18006745d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067462  nop
0x180067463  cmp     dword ptr [rsp+290h+var_250], r14d
0x180067468  jz      short loc_180067475
0x18006746a  lea     rcx, [rsp+290h+var_250]; this
0x18006746f  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180067474  nop
0x180067475  jmp     loc_1800677D3
0x18006747a  mov     edi, r14d
0x18006747d  mov     r14b, 1
0x180067480  lea     rcx, [rsp+290h+var_250]; this
0x180067485  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18006748a  xor     ecx, ecx
0x18006748c  mov     [r15], rcx
0x18006748f  mov     byte ptr [rsp+290h+var_240], cl
0x180067493  test    r12, r12
0x180067496  jz      loc_18006758F
0x18006749c  mov     rax, [r12]
0x1800674a0  mov     [rsp+290h+var_260], rcx
0x1800674a5  mov     [rsp+290h+var_268], r15
0x1800674aa  lea     rcx, [rsp+290h+var_240]
0x1800674af  mov     [rsp+290h+ppv], rcx; int
0x1800674b4  mov     r9, r13
0x1800674b7  mov     r8, rsi
0x1800674ba  mov     rdx, [rsp+290h+var_238]
0x1800674bf  mov     rcx, r12
0x1800674c2  mov     rax, [rax+10h]
0x1800674c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674cb  xor     r12d, r12d
0x1800674ce  cmp     [r15], r12
0x1800674d1  jz      loc_18006758F
0x1800674d7  test    r14b, r14b
0x1800674da  jz      loc_1800677B3
0x1800674e0  xor     r8d, r8d; unsigned int *
0x1800674e3  lea     edx, [r8+1]; unsigned int
0x1800674e7  mov     rcx, [rbp+190h+lpNewFileName+8]; lpFileName
0x1800674eb  call    ?AppXDeleteFile@@YAJPEAGKPEAK@Z; AppXDeleteFile(ushort *,ulong,ulong *)
0x1800674f0  test    eax, eax
0x1800674f2  jns     loc_1800677B3
0x1800674f8  lea     rcx, [rbp+190h+Uuid]; Uuid
0x1800674fc  call    cs:__imp_UuidCreate
0x180067502  test    eax, eax
0x180067504  jz      short loc_180067511
0x180067506  cmp     eax, 720h
0x18006750b  jnz     loc_1800677B3
0x180067511  mov     [rsp+290h+StringUuid], r12
0x180067516  lea     rdx, [rsp+290h+StringUuid]; StringUuid
0x18006751b  lea     rcx, [rbp+190h+Uuid]; Uuid
0x18006751f  call    cs:__imp_UuidToStringW
0x180067525  test    eax, eax
0x180067527  jz      loc_180067654
0x18006752d  mov     rcx, [rbp+198h]; this
  ... truncated ...
```
