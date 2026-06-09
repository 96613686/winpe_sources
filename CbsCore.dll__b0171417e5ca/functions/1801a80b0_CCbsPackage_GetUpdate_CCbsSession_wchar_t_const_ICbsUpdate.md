# CCbsPackage::GetUpdate(CCbsSession *,wchar_t const *,ICbsUpdate * *)

- ea: `0x1801a80b0`
- end: `0x1801a8a7d`
- name: `?GetUpdate@CCbsPackage@@QEAAJPEAVCCbsSession@@PEB_WPEAPEAUICbsUpdate@@@Z`
- size: `2509`
- prototype: `__int64 __fastcall(CCbsPackage *__hidden this, struct CCbsSession *, const wchar_t *, struct ICbsUpdate **)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b9d94`
- `0x1801bb434`

## callees

- `0x180010cc0`
- `0x1800138b8`
- `0x180023f30`
- `0x18002573c`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002c34c`
- `0x1800416d4`
- `0x1800430c4`
- `0x180066c28`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800be858`
- `0x1800c0054`
- `0x1800eb920`
- `0x180128510`
- `0x1801a54d8`
- `0x1801a80b0`
- `0x1801a8b68`
- `0x1801c2c30`
- `0x1801e1cd4`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8765`

## string_xrefs

- `0x1801a8181`: `No update name specified`
- `0x1801a814b`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a82a3`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8423`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8893`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8a38`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a87e9`: `Duplicate update when enumerating update on Package: {}, Update: {}`
- `0x1801a89a5`: `Attempt to find a feature failed on a Read-Only image (ContainerOS/VAIL). This feature may exist on the image but no longer have optionality. Update Name: {}`
- `0x1801a857c`: `Failed to call internal update on package {}:`
- `0x1801a8904`: `Failed to call internal update on package {}:`
- `0x1801a89e6`: `Failed to get internal update: {} in Package: {}`
- `0x1801a83e5`: `Failed to list packages based on update {}:`
- `0x1801a8262`: `Cannot get update from a dead package.`
- `0x1801a81df`: `No update result specified`

## pseudocode

```c
__int64 __fastcall CCbsPackage::GetUpdate(
        CCbsPackage *this,
        struct CCbsSession *a2,
        wchar_t *a3,
        struct ICbsUpdate **a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  int IsFullyInitialized; // eax
  __int64 v10; // rdx
  struct IEnumCbsIdentity **InitPointer; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64, int *); // rbx
  __int64 v15; // rax
  struct CCbsPackage **v16; // rax
  struct ICbsUIHandler *v17; // r9
  const wchar_t *v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 i; // rsi
  struct ICbsUpdate *v21; // rdi
  unsigned int (__fastcall *v22)(struct ICbsUpdate *, __int64); // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned int (__fastcall *v25)(__int64, __int64); // rbx
  __int64 v26; // rax
  int *v27; // rdi
  unsigned int (__fastcall *v28)(int *, __int64); // rbx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  const wchar_t *v33; // rdx
  int v34; // eax
  const wchar_t *v35; // rdx
  struct ICbsUpdate *v36; // rcx
  const wchar_t *v38; // rdx
  int v39; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v43; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v44[24]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v45; // [rsp+A8h] [rbp-58h] BYREF
  int v46; // [rsp+B0h] [rbp-50h] BYREF
  int v47[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v48; // [rsp+C0h] [rbp-40h] BYREF
  struct ICbsIdentity *v49; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h] BYREF
  int *v51; // [rsp+D8h] [rbp-28h] BYREF
  int v52; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v54[64]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v55[48]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v56; // [rsp+160h] [rbp+60h]
  struct ICbsUpdate **v57; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v45 = a3;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = -2147024809;
      v46 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update name specified");
        *(_QWORD *)v47 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v47);
      }
      v8 = 211;
      goto LABEL_5;
    }
    if ( !a4 )
    {
      v7 = -2147467261;
      v46 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update result specified");
        *(_QWORD *)v47 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v47);
      }
      v8 = 212;
      goto LABEL_5;
    }
    CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>(v55);
    CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v54);
    CritSecLocker::CritSecLocker((CritSecLocker *)v44, (CCbsPackage *)((char *)this + 1064), 1);
    if ( *((_DWORD *)this + 22) )
    {
      v7 = -2146498537;
      v46 = -2146498537;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot get update from a dead package.");
        *(_QWORD *)v47 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)0x800F0817LL,
        v39);
      CritSecLocker::~CritSecLocker((CritSecLocker *)v44);
      goto LABEL_93;
    }
    CritSecLocker::~CritSecLocker((CritSecLocker *)v44);
    IsFullyInitialized = CCbsPackage::MakeSurePackageIsFullyInitialized(this, a2);
    v7 = IsFullyInitialized;
    if ( IsFullyInitialized < 0 )
    {
      v46 = IsFullyInitialized;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Delay Initialization Failed");
        *(_QWORD *)v47 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v47);
      }
      v10 = 226;
LABEL_92:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)(unsigned int)v7,
        v39);
LABEL_93:
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v54);
      CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::~CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>(v55);
      return (unsigned int)v7;
    }
    if ( *((_BYTE *)a2 + 624) )
    {
      v40 = 0;
      if ( (int)CCbsPackage::InternalEnumerateUpdate(
                  (__int64)this,
                  a2,
                  (__int64)v54,
                  0,
                  0,
                  0,
                  v45,
                  1,
                  (__int64)v55,
                  0,
                  0,
                  0,
                  0) < 0
        || !v56 )
      {
        InitPointer = (struct IEnumCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v40);
        v12 = PackageStoreEnumeratePackages(a2, 0x70u, InitPointer);
        v7 = v12;
        if ( v12 < 0 )
        {
          v46 = v12;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to list packages based on update {}:",
              (__int64)&v45);
            *(_QWORD *)v47 = &v46;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v47);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)v7,
            v39);
LABEL_29:
          if ( v40 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            v40 = 0;
          }
          goto LABEL_93;
        }
        while ( 1 )
        {
          v13 = v40;
          v46 = 0;
          v49 = 0;
          v50 = 0;
          v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v40 + 24LL);
          v15 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v49);
          v7 = v14(v13, 1, v15, &v46);
          if ( v7 < 0 )
          {
            v48 = v7;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get package identities from enumeration.");
              *(_QWORD *)v47 = &v48;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v47);
            }
            v19 = 263;
            goto LABEL_74;
          }
          if ( v46 != 1 )
            break;
          v16 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v50);
          v7 = CCbsSession::ResolvePackage(a2, 0, 0, v17, v49, 1, v16, 0);
          if ( v7 < 0 )
          {
            v48 = v7;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v47 = GetFastCbsIdentityString(v49);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to resolve package {}:",
                (__int64)v47);
              v51 = &v48;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v51);
            }
            v19 = 279;
            goto LABEL_74;
          }
          v7 = CCbsPackage::InternalEnumerateUpdate(v50, a2, (__int64)v54, 0, 18, 0, v45, 1, (__int64)v55, 0, 0, 0, 0);
          if ( v7 < 0 )
          {
            v48 = v7;
            if ( LogAdapter::g_Logger )
            {
              v18 = &qword_1802EB518;
              if ( *(_QWORD *)(v50 + 120) )
                v18 = *(const wchar_t **)(v50 + 120);
              *(_QWORD *)v47 = v18;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to call internal update on package {}:",
                (__int64)v47);
              v51 = &v48;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v51);
            }
            v19 = 292;
LABEL_74:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
              (const char *)(unsigned int)v7,
              v39);
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v50);
            if ( v49 )
            {
              (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v49 + 16LL))(v49);
              v49 = 0;
            }
            goto LABEL_29;
          }
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v50);
          if ( v49 )
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v49 + 16LL))(v49);
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v50);
        if ( v49 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v49 + 16LL))(v49);
          v49 = 0;
        }
      }
      if ( v40 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        v40 = 0;
      }
    }
    else
    {
      v34 = CCbsPackage::InternalEnumerateUpdate(
              (__int64)this,
              a2,
              (__int64)v54,
              0,
              0,
              0,
              v45,
              1,
              (__int64)v55,
              0,
              0,
              0,
              0);
      v7 = v34;
      if ( v34 < 0 )
      {
        v48 = v34;
        if ( LogAdapter::g_Logger )
        {
          v35 = &qword_1802EB518;
          if ( *((_QWORD *)this + 15) )
            v35 = (const wchar_t *)*((_QWORD *)this + 15);
          *(_QWORD *)v47 = v35;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to call internal update on package {}:",
            (__int64)v47);
          *(_QWORD *)v41 = &v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v41);
        }
        v10 = 309;
        goto LABEL_92;
      }
    }
    if ( v56 )
    {
      if ( v56 == 1 )
      {
        v36 = *v57;
        *a4 = *v57;
        (*(void (__fastcall **)(struct ICbsUpdate *))(*(_QWORD *)v36 + 8LL))(v36);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v54);
        CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::~CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>(v55);
        return 0;
      }
      for ( i = 0; i < v56; ++i )
      {
        *(_QWORD *)v47 = 0;
        v51 = 0;
        pv = 0;
        if ( i >= v56 )
          __fastfail(8u);
        v21 = v57[i];
        v22 = *(unsigned int (__fastcall **)(struct ICbsUpdate *, __int64))(*(_QWORD *)v21 + 32LL);
        v23 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v47);
        if ( !v22(v21, v23) )
        {
          v24 = *(_QWORD *)v47;
          v25 = *(unsigned int (__fastcall **)(__int64, __int64))(**(_QWORD **)v47 + 24LL);
          v26 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v51);
          if ( !v25(v24, v26) )
          {
            v27 = v51;
            v28 = *(unsigned int (__fastcall **)(int *, __int64))(*(_QWORD *)v51 + 64LL);
            v29 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
            if ( !v28(v27, v29) )
            {
              v42 = i;
              if ( LogAdapter::g_Logger )
                LogAdapter::Logger::LogNumObjects<int,Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
                  (__int64)LogAdapter::g_Logger,
                  v30,
                  v31,
                  v32,
                  (__int64)&v42,
                  (__int64)&pv);
            }
          }
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v51 )
        {
          (*(void (__fastcall **)(int *))(*(_QWORD *)v51 + 16LL))(v51);
          v51 = 0;
        }
        if ( *(_QWORD *)v47 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 16LL))(*(_QWORD *)v47);
          *(_QWORD *)v47 = 0;
        }
      }
      v7 = -2146498535;
      v52 = -2146498535;
      if ( LogAdapter::g_Logger )
      {
        v33 = &qword_1802EB518;
        if ( *((_QWORD *)this + 15) )
          v33 = (const wchar_t *)*((_QWORD *)this + 15);
        v43 = v33;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Duplicate update when enumerating update on Package: {}, Update: {}",
          (__int64)&v43,
          (__int64)&v45);
        *(_QWORD *)v41 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v41);
      }
      v10 = 366;
    }
    else
    {
      if ( CCbsSession::IsImageReadOnly(a2) )
      {
        if ( !vbInTestMode )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        LogAdapter::TraceAtLevel<wchar_t const *>(
          1,
          "Attempt to find a feature failed on a Read-Only image (ContainerOS/VAIL). This feature may exist on the image "
          "but no longer have optionality. Update Name: {}",
          &v45);
      }
      v7 = -2146498548;
      v52 = -2146498548;
      if ( LogAdapter::g_Logger )
      {
        v38 = &qword_1802EB518;
        if ( *((_QWORD *)this + 15) )
          v38 = (const wchar_t *)*((_QWORD *)this + 15);
        v43 = v38;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get internal update: {} in Package: {}",
          (__int64)&v45,
          (__int64)&v43);
        *(_QWORD *)v41 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v41);
      }
      v10 = 327;
    }
    goto LABEL_92;
  }
  v7 = -2147024809;
  v46 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session specified");
    *(_QWORD *)v47 = &v46;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v47);
  }
  v8 = 210;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
    (const char *)(unsigned int)v7,
    v39);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801a80b0  push    rbp
0x1801a80b2  push    rbx
0x1801a80b3  push    rsi
0x1801a80b4  push    rdi
0x1801a80b5  push    r12
0x1801a80b7  push    r14
0x1801a80b9  push    r15
0x1801a80bb  lea     rbp, [rsp-0E0h]
0x1801a80c3  sub     rsp, 1E0h
0x1801a80ca  mov     rax, cs:__security_cookie
0x1801a80d1  xor     rax, rsp
0x1801a80d4  mov     [rbp+110h+var_40], rax
0x1801a80db  xor     r12d, r12d
0x1801a80de  mov     [rbp+110h+var_168], r8
0x1801a80e2  mov     r15, r9
0x1801a80e5  mov     rsi, rdx
0x1801a80e8  mov     r14, rcx
0x1801a80eb  test    rdx, rdx
0x1801a80ee  jnz     short loc_1801A815F
0x1801a80f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a80f7  mov     ebx, 80070057h
0x1801a80fc  mov     [rbp+110h+var_160], ebx
0x1801a80ff  test    rcx, rcx
0x1801a8102  jz      short loc_1801A813F
0x1801a8104  lea     edi, [rdx+3]
0x1801a8107  mov     r8d, edi
0x1801a810a  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1801a8111  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8116  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a811d  lea     rax, [rbp+110h+var_160]
0x1801a8121  mov     qword ptr [rbp+110h+var_158], rax
0x1801a8125  lea     r9, asc_1802EE7AC; ": {}"
0x1801a812c  lea     rax, [rbp+110h+var_158]
0x1801a8130  mov     r8d, edi
0x1801a8133  mov     dl, 1
0x1801a8135  mov     [rsp+210h+var_1F0], rax; int
0x1801a813a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a813f  mov     edx, 0D2h; void *
0x1801a8144  mov     rcx, [rbp+118h]; this
0x1801a814b  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8152  mov     r9d, ebx; char *
0x1801a8155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a815a  jmp     loc_1801A8A59
0x1801a815f  test    r8, r8
0x1801a8162  jnz     short loc_1801A81BD
0x1801a8164  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a816b  mov     ebx, 80070057h
0x1801a8170  mov     [rbp+110h+var_160], ebx
0x1801a8173  test    rcx, rcx
0x1801a8176  jz      short loc_1801A81B6
0x1801a8178  lea     edi, [r8+3]
0x1801a817c  xor     edx, edx
0x1801a817e  mov     r8d, edi
0x1801a8181  lea     r9, aNoUpdateNameSp; "No update name specified"
0x1801a8188  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a818d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8194  lea     rax, [rbp+110h+var_160]
0x1801a8198  mov     qword ptr [rbp+110h+var_158], rax
0x1801a819c  lea     r9, asc_1802EE7AC; ": {}"
0x1801a81a3  lea     rax, [rbp+110h+var_158]
0x1801a81a7  mov     r8d, edi
0x1801a81aa  mov     dl, 1
0x1801a81ac  mov     [rsp+210h+var_1F0], rax
0x1801a81b1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a81b6  mov     edx, 0D3h
0x1801a81bb  jmp     short loc_1801A8144
0x1801a81bd  test    r15, r15
0x1801a81c0  jnz     short loc_1801A821E
0x1801a81c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a81c9  mov     ebx, 80004003h
0x1801a81ce  mov     [rbp+110h+var_160], ebx
0x1801a81d1  test    rcx, rcx
0x1801a81d4  jz      short loc_1801A8214
0x1801a81d6  lea     edi, [r15+3]
0x1801a81da  xor     edx, edx
0x1801a81dc  mov     r8d, edi
0x1801a81df  lea     r9, aNoUpdateResult; "No update result specified"
0x1801a81e6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a81eb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a81f2  lea     rax, [rbp+110h+var_160]
0x1801a81f6  mov     qword ptr [rbp+110h+var_158], rax
0x1801a81fa  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8201  lea     rax, [rbp+110h+var_158]
0x1801a8205  mov     r8d, edi
0x1801a8208  mov     dl, 1
0x1801a820a  mov     [rsp+210h+var_1F0], rax
0x1801a820f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8214  mov     edx, 0D4h
0x1801a8219  jmp     loc_1801A8144
0x1801a821e  lea     rcx, [rbp+110h+var_E0]
0x1801a8222  call    ??0?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@QEAA@XZ; CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>::CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>(void)
0x1801a8227  lea     rcx, [rbp+110h+var_120]
0x1801a822b  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801a8230  lea     rdx, [r14+428h]; struct AutoCritSec *
0x1801a8237  mov     r8b, 1; bool
0x1801a823a  lea     rcx, [rbp+110h+var_180]; this
0x1801a823e  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801a8243  cmp     [r14+58h], r12d
0x1801a8247  jz      short loc_1801A82C5
0x1801a8249  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8250  mov     ebx, 800F0817h
0x1801a8255  mov     [rbp+110h+var_160], ebx
0x1801a8258  test    rcx, rcx
0x1801a825b  jz      short loc_1801A829C
0x1801a825d  mov     edi, 3
0x1801a8262  lea     r9, aCannotGetUpdat; "Cannot get update from a dead package."
0x1801a8269  mov     r8d, edi
0x1801a826c  xor     edx, edx
0x1801a826e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8273  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a827a  lea     rax, [rbp+110h+var_160]
0x1801a827e  mov     qword ptr [rbp+110h+var_158], rax
0x1801a8282  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8289  lea     rax, [rbp+110h+var_158]
0x1801a828d  mov     r8d, edi
0x1801a8290  mov     dl, 1
0x1801a8292  mov     [rsp+210h+var_1F0], rax; int
0x1801a8297  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a829c  mov     rcx, [rbp+118h]; this
0x1801a82a3  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a82aa  mov     r9d, ebx; char *
0x1801a82ad  mov     edx, 0DEh; void *
0x1801a82b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a82b7  lea     rcx, [rbp+110h+var_180]; this
0x1801a82bb  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801a82c0  jmp     loc_1801A8A47
0x1801a82c5  lea     rcx, [rbp+110h+var_180]; this
0x1801a82c9  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801a82ce  mov     rdx, rsi; struct CCbsSession *
0x1801a82d1  mov     rcx, r14; this
0x1801a82d4  call    ?MakeSurePackageIsFullyInitialized@CCbsPackage@@QEAAJPEAVCCbsSession@@@Z; CCbsPackage::MakeSurePackageIsFullyInitialized(CCbsSession *)
0x1801a82d9  mov     ebx, eax
0x1801a82db  test    eax, eax
0x1801a82dd  jns     short loc_1801A8337
0x1801a82df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a82e6  mov     [rbp+110h+var_160], eax
0x1801a82e9  test    rcx, rcx
0x1801a82ec  jz      short loc_1801A832D
0x1801a82ee  mov     edi, 3
0x1801a82f3  lea     r9, aDelayInitializ; "Delay Initialization Failed"
0x1801a82fa  mov     r8d, edi
0x1801a82fd  xor     edx, edx
0x1801a82ff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8304  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a830b  lea     rax, [rbp+110h+var_160]
0x1801a830f  mov     qword ptr [rbp+110h+var_158], rax
0x1801a8313  lea     r9, asc_1802EE7AC; ": {}"
0x1801a831a  lea     rax, [rbp+110h+var_158]
0x1801a831e  mov     r8d, edi
0x1801a8321  mov     dl, 1
0x1801a8323  mov     [rsp+210h+var_1F0], rax
0x1801a8328  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a832d  mov     edx, 0E2h
0x1801a8332  jmp     loc_1801A8A31
0x1801a8337  mov     [rsp+210h+var_1B0], r12
0x1801a833c  lea     rax, [rbp+110h+var_E0]
0x1801a8340  mov     [rsp+210h+var_1B8], r12
0x1801a8345  lea     r8, [rbp+110h+var_120]
0x1801a8349  mov     [rsp+210h+var_1C0], r12d
0x1801a834e  xor     r9d, r9d
0x1801a8351  mov     rdx, rsi
0x1801a8354  mov     [rsp+210h+var_1C8], r12d
0x1801a8359  mov     rcx, r14
0x1801a835c  mov     [rsp+210h+var_1D0], rax
0x1801a8361  mov     rax, [rbp+110h+var_168]
0x1801a8365  mov     [rsp+210h+var_1D8], 1
0x1801a836d  mov     [rsp+210h+var_1E0], rax
0x1801a8372  mov     [rsp+210h+var_1E8], r12d
0x1801a8377  mov     dword ptr [rsp+210h+var_1F0], r12d
0x1801a837c  cmp     [rsi+270h], r12b
0x1801a8383  jz      loc_1801A88CD
0x1801a8389  mov     [rsp+210h+var_1A0], r12
0x1801a838e  call    ?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z; CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)
0x1801a8393  test    eax, eax
0x1801a8395  js      short loc_1801A83A1
0x1801a8397  cmp     [rbp+110h+var_B0], r12
0x1801a839b  jnz     loc_1801A8666
0x1801a83a1  lea     rcx, [rsp+210h+var_1A0]
0x1801a83a6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801a83ab  mov     r8, rax; struct IEnumCbsIdentity **
0x1801a83ae  mov     edx, 70h ; 'p'; unsigned int
0x1801a83b3  mov     rcx, rsi; struct CCbsSession *
0x1801a83b6  call    ?PackageStoreEnumeratePackages@@YAJPEAVCCbsSession@@KPEAPEAUIEnumCbsIdentity@@@Z; PackageStoreEnumeratePackages(CCbsSession *,ulong,IEnumCbsIdentity * *)
0x1801a83bb  mov     ebx, eax
0x1801a83bd  test    eax, eax
0x1801a83bf  jns     loc_1801A845B
0x1801a83c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a83cc  mov     [rbp+110h+var_160], eax
0x1801a83cf  test    rcx, rcx
0x1801a83d2  jz      short loc_1801A841C
0x1801a83d4  lea     rax, [rbp+110h+var_168]
0x1801a83d8  mov     edi, 3
0x1801a83dd  mov     r8d, edi
0x1801a83e0  mov     [rsp+210h+var_1F0], rax
0x1801a83e5  lea     r9, aFailedToListPa; "Failed to list packages based on update"...
0x1801a83ec  xor     edx, edx
0x1801a83ee  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801a83f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a83fa  lea     rax, [rbp+110h+var_160]
0x1801a83fe  mov     qword ptr [rbp+110h+var_158], rax
0x1801a8402  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8409  lea     rax, [rbp+110h+var_158]
0x1801a840d  mov     r8d, edi
0x1801a8410  mov     dl, 1
0x1801a8412  mov     [rsp+210h+var_1F0], rax; int
0x1801a8417  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a841c  mov     rcx, [rbp+118h]; this
0x1801a8423  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a842a  mov     r9d, ebx; char *
0x1801a842d  mov     edx, 0FDh; void *
0x1801a8432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8437  mov     rcx, [rsp+210h+var_1A0]
0x1801a843c  test    rcx, rcx
0x1801a843f  jz      loc_1801A8A47
0x1801a8445  mov     rax, [rcx]
0x1801a8448  mov     rax, [rax+10h]
0x1801a844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8451  mov     [rsp+210h+var_1A0], r12
0x1801a8456  jmp     loc_1801A8A47
0x1801a845b  mov     rdi, [rsp+210h+var_1A0]
0x1801a8460  lea     rcx, [rbp+110h+var_148]
0x1801a8464  mov     [rbp+110h+var_160], r12d
0x1801a8468  mov     [rbp+110h+var_148], r12
0x1801a846c  mov     [rbp+110h+var_140], r12
0x1801a8470  mov     rax, [rdi]
0x1801a8473  mov     rbx, [rax+18h]
0x1801a8477  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801a847c  mov     r8, rax
0x1801a847f  lea     r9, [rbp+110h+var_160]
0x1801a8483  mov     rax, rbx
0x1801a8486  mov     edx, 1
0x1801a848b  mov     rcx, rdi
0x1801a848e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8493  mov     ebx, eax
0x1801a8495  test    eax, eax
0x1801a8497  js      loc_1801A8839
0x1801a849d  cmp     [rbp+110h+var_160], 1
0x1801a84a1  lea     rcx, [rbp+110h+var_140]
0x1801a84a5  jnz     loc_1801A8648
0x1801a84ab  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801a84b0  mov     rcx, [rbp+110h+var_148]
0x1801a84b4  xor     r8d, r8d; void *
0x1801a84b7  mov     [rsp+210h+var_1D8], r12d; int
0x1801a84bc  xor     edx, edx; struct PerSessionPackageState *
0x1801a84be  mov     [rsp+210h+var_1E0], rax; struct CCbsPackage **
0x1801a84c3  mov     [rsp+210h+var_1E8], 1; int
0x1801a84cb  mov     [rsp+210h+var_1F0], rcx; struct ICbsIdentity *
0x1801a84d0  mov     rcx, rsi; this
0x1801a84d3  call    ?ResolvePackage@CCbsSession@@QEAAJPEAUPerSessionPackageState@@PEAXPEAUICbsUIHandler@@PEAUICbsIdentity@@HPEAPEAVCCbsPackage@@H@Z; CCbsSession::ResolvePackage(PerSessionPackageState *,void *,ICbsUIHandler *,ICbsIdentity *,int,CCbsPackage * *,int)
0x1801a84d8  mov     ebx, eax
0x1801a84da  test    eax, eax
0x1801a84dc  js      loc_1801A85D6
0x1801a84e2  mov     rax, [rbp+110h+var_168]
0x1801a84e6  lea     rcx, [rbp+110h+var_E0]
0x1801a84ea  mov     [rsp+210h+var_1B0], r12
0x1801a84ef  lea     r8, [rbp+110h+var_120]
0x1801a84f3  mov     [rsp+210h+var_1B8], r12
0x1801a84f8  xor     r9d, r9d
0x1801a84fb  mov     [rsp+210h+var_1C0], r12d
0x1801a8500  mov     rdx, rsi
0x1801a8503  mov     [rsp+210h+var_1C8], r12d
0x1801a8508  mov     [rsp+210h+var_1D0], rcx
0x1801a850d  mov     rcx, [rbp+110h+var_140]
0x1801a8511  mov     [rsp+210h+var_1D8], 1
0x1801a8519  mov     [rsp+210h+var_1E0], rax
0x1801a851e  mov     [rsp+210h+var_1E8], r12d
0x1801a8523  mov     dword ptr [rsp+210h+var_1F0], 12h
0x1801a852b  call    ?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z; CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)
0x1801a8530  mov     ebx, eax
0x1801a8532  test    eax, eax
0x1801a8534  js      short loc_1801A855D
0x1801a8536  lea     rcx, [rbp+110h+var_140]
0x1801a853a  call    ?Close@?$AutoComPtr@VCCbsDriverDeployment@@@Windows@@QEAAXXZ; Windows::AutoComPtr<CCbsDriverDeployment>::Close(void)
0x1801a853f  mov     rcx, [rbp+110h+var_148]
0x1801a8543  test    rcx, rcx
0x1801a8546  jz      loc_1801A845B
0x1801a854c  mov     rax, [rcx]
0x1801a854f  mov     rax, [rax+10h]
0x1801a8553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8558  jmp     loc_1801A845B
0x1801a855d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8564  mov     [rbp+110h+var_150], ebx
0x1801a8567  test    rcx, rcx
0x1801a856a  jz      short loc_1801A85CC
0x1801a856c  mov     rax, [rbp+110h+var_140]
0x1801a8570  lea     rdx, qword_1802EB518
0x1801a8577  mov     edi, 3
0x1801a857c  lea     r9, aFailedToCallIn_0; "Failed to call internal update on packa"...
0x1801a8583  mov     r8d, edi
0x1801a8586  cmp     [rax+78h], r12
0x1801a858a  cmovnz  rdx, [rax+78h]
0x1801a858f  lea     rax, [rbp+110h+var_158]
0x1801a8593  mov     qword ptr [rbp+110h+var_158], rdx
0x1801a8597  xor     edx, edx
0x1801a8599  mov     [rsp+210h+var_1F0], rax
0x1801a859e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801a85a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a85aa  lea     rax, [rbp+110h+var_150]
0x1801a85ae  mov     [rbp+110h+var_138], rax
0x1801a85b2  lea     r9, asc_1802EE7AC; ": {}"
  ... truncated ...
```
