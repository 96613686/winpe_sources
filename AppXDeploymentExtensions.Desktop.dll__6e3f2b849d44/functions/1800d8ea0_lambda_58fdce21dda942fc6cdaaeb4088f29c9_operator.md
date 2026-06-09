# _lambda_58fdce21dda942fc6cdaaeb4088f29c9_::operator()

- ea: `0x1800d8ea0`
- end: `0x1800d97bc`
- name: `_lambda_58fdce21dda942fc6cdaaeb4088f29c9_::operator()`
- size: `2332`
- prototype: `__int64 __fastcall(const unsigned __int16 **, const struct std::nothrow_t *, __int64, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800da32c`

## callees

- `0x180006970`
- `0x180012fc8`
- `0x18001adb4`
- `0x18001e42c`
- `0x18003d814`
- `0x18003d8f4`
- `0x18003d9b0`
- `0x180050884`
- `0x180068824`
- `0x180086ab8`
- `0x180086ea4`
- `0x180099b44`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af918`
- `0x1800d8ea0`
- `0x1800da738`
- `0x1800da7c0`
- `0x1800da864`
- `0x1800da964`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d8f8f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d8f8f`

## string_xrefs

- `0x1800d8f19`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d8fa6`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9024`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9085`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d91e2`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9240`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d92ba`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d937d`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9444`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d94f7`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d95bb`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9625`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d968e`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d9710`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x1800d95a0`: `: does not have a resources.pri file or could not create a resource manager`
- `0x1800d96f5`: `: does not have a resources.pri file or could not create a resource manager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_58fdce21dda942fc6cdaaeb4088f29c9_::operator()(
        const unsigned __int16 **a1,
        const struct std::nothrow_t *a2,
        __int64 a3,
        struct Common::StringBuffer *a4)
{
  const unsigned __int16 *v5; // rcx
  int v6; // eax
  bool *v7; // r8
  unsigned int v8; // ebx
  const struct std::nothrow_t *v9; // rdx
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rdx
  bool *v13; // r8
  void *v14; // rcx
  int v15; // eax
  void *v16; // rcx
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, GUID *, __int64); // rdi
  __int64 v23; // rbx
  struct Common::StringBuffer *v24; // r8
  const unsigned __int16 *v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // ecx
  void *v30; // rdi
  __int64 v31; // rdx
  int v32; // ecx
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, const wchar_t *, __int64); // rdi
  __int64 v35; // rbx
  struct Common::StringBuffer *v36; // r8
  __int64 v37; // rdx
  int v38; // ecx
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, const unsigned __int16 *, __int64); // rdi
  __int64 v41; // rbx
  struct Common::StringBuffer *v42; // r8
  __int64 v43; // rdx
  int v44; // ecx
  char IsEnabled; // al
  struct Common::StringBuffer *v46; // r8
  const unsigned __int16 *v47; // rdx
  int v48; // ecx
  __int64 v49; // rdx
  int v50; // ecx
  __int64 v51; // rdx
  wil::details::in1diag3 *v52; // rcx
  __int64 v53; // rdx
  int v54; // ecx
  wil::details::in1diag3 *v55; // rcx
  const struct std::nothrow_t *v56; // rdx
  void *v57; // rcx
  int v58; // [rsp+28h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-E0h]
  __int64 *cbSid; // [rsp+38h] [rbp-D0h] BYREF
  DWORD cbSid_8[4]; // [rsp+40h] [rbp-C8h] BYREF
  int v62; // [rsp+50h] [rbp-B8h]
  __int128 v63; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-A0h]
  void *TokenHandle[3]; // [rsp+70h] [rbp-98h] BYREF
  int v66; // [rsp+88h] [rbp-80h]
  void **v67; // [rsp+90h] [rbp-78h] BYREF
  __int128 *v68; // [rsp+98h] [rbp-70h]
  __int128 *v69; // [rsp+A0h] [rbp-68h]
  _BYTE pSid[80]; // [rsp+A8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  *(_OWORD *)cbSid_8 = 0;
  v62 = 0;
  *(_OWORD *)&TokenHandle[1] = 0;
  v66 = 0;
  v5 = *a1;
  if ( (v5[198] & 0x23) != 0 )
  {
    v6 = OSIntegration::Tools::ConcatenatePaths(
           (OSIntegration::Tools *)(v5 + 44),
           (const struct Common::COMMON_STRING *)&qword_1801BF5F8,
           (const struct Common::COMMON_STRING *)cbSid_8,
           a4);
    v8 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x713,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
        (const char *)(unsigned int)v6,
        v58);
LABEL_4:
      if ( *(_QWORD *)&cbSid_8[2] )
        operator delete(*(void **)&cbSid_8[2], v9);
      return v8;
    }
    if ( (unsigned int)Common::FileExists(*(Common **)&cbSid_8[2], *a1, v7) == -2147024891 )
    {
      TokenHandle[0] = 0;
      Common::AutoNoImpersonateDuringScope::DropImpersonation(TokenHandle);
      memset_0(pSid, 0, 0x44u);
      LODWORD(cbSid) = 68;
      if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, pSid, (DWORD *)&cbSid) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x721,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
          (const char *)0x80070005LL,
          v58);
        Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)TokenHandle);
LABEL_16:
        if ( *(_QWORD *)&cbSid_8[2] )
          operator delete(*(void **)&cbSid_8[2], v11);
        return 2147942405LL;
      }
      if ( (int)Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(
                  *((WCHAR **)*a1 + 12),
                  pSid,
                  (*((_DWORD *)*a1 + 96) & 0x100) == 0) < 0 )
      {
        v12 = 1828;
        goto LABEL_14;
      }
      if ( (int)Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(
                  *(WCHAR **)&cbSid_8[2],
                  pSid,
                  (*((_DWORD *)*a1 + 96) & 0x100) == 0) < 0 )
      {
        v12 = 1831;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
          (const char *)0x80070005LL,
          v58);
        Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)TokenHandle);
        v14 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v14 )
          operator delete(v14, v11);
        goto LABEL_16;
      }
      v15 = Common::FileExists(*(Common **)&cbSid_8[2], *a1, v13);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x729,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
          (const char *)(unsigned int)v15,
          v58);
        Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)TokenHandle);
        v16 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( !v16 )
          goto LABEL_4;
LABEL_21:
        operator delete(v16, v9);
        goto LABEL_4;
      }
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)TokenHandle);
    }
  }
  v17 = *a1;
  if ( *(_BYTE *)*a1 || *((_BYTE *)v17 + 369) )
  {
    cbSid = 0;
    v8 = Microsoft::WRL::ComPtr<IMrtResourceManager>::As<IMrtResourceManager2>(v17 + 16, &cbSid);
    if ( (v8 & 0x80000000) == 0 )
    {
      v18 = *cbSid;
      v19 = *((_QWORD *)*a1 + 28);
      v20 = *((_BYTE *)*a1 + 369)
          ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v18 + 40))(cbSid, *(_QWORD *)&cbSid_8[2], v19)
          : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v18 + 24))(
              cbSid,
              *(_QWORD *)&cbSid_8[2],
              v19);
      v8 = v20;
      if ( v20 >= 0 )
      {
        v21 = *((_QWORD *)*a1 + 4);
        v22 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v21 + 56LL);
        v23 = (__int64)(*a1 + 4);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v23);
        v8 = v22(v21, &IID_IResourceMap, v23);
        if ( (v8 & 0x80000000) == 0 )
        {
          v33 = *((_QWORD *)*a1 + 1);
          v34 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v33 + 32LL);
          v35 = (__int64)(*a1 + 8);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v35);
          v8 = v34(v33, L"Files", v35);
          if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147009761 )
          {
            v39 = *((_QWORD *)*a1 + 1);
            v40 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v39 + 32LL);
            v41 = (__int64)(*a1 + 12);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v41);
            v8 = v40(v39, L"Resources", v41);
            if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147009761 )
            {
LABEL_82:
              Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&cbSid);
              goto LABEL_83;
            }
            OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v42);
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7A6,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
              (const char *)v8,
              v58);
            v30 = TokenHandle[2];
            if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
              McTemplateU0zzd_EventWriteTransfer(
                v44,
                (unsigned int)OSIMGetReferenceHandlerError,
                *((_QWORD *)*a1 + 28),
                TokenHandle[2],
                v8);
            details::appxLog<unsigned short const *,long,unsigned short *>(
              v8,
              v43,
              OSIMGetReferenceHandlerError,
              *((_QWORD *)*a1 + 28));
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7A7,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
              (const char *)v8,
              (int)v30);
          }
          else
          {
            OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v36);
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x798,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
              (const char *)v8,
              v58);
            v30 = TokenHandle[2];
            if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
              McTemplateU0zzd_EventWriteTransfer(
                v38,
                (unsigned int)OSIMGetReferenceHandlerError,
                *((_QWORD *)*a1 + 28),
                TokenHandle[2],
                v8);
            details::appxLog<unsigned short const *,long,unsigned short *>(
              v8,
              v37,
              OSIMGetReferenceHandlerError,
              *((_QWORD *)*a1 + 28));
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x799,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
              (const char *)v8,
              (int)v30);
          }
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl'::`2'::impl) )
        {
          v25 = *a1;
          if ( *((_DWORD *)*a1 + 93) == 5 )
          {
            v63 = 0;
            LODWORD(v64) = 0;
            v68 = &v63;
            v67 = &Common::StringBufferBuilder::`vftable';
            v69 = &v63;
            Common::StringBuilder::AppendString((Common::StringBuilder *)&v67, *((const unsigned __int16 **)v25 + 28));
            Common::StringBuilder::AppendString(
              (Common::StringBuilder *)&v67,
              L": Signed SBOM package - could not get main resource map (expected, no resources.pri)");
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x77C,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
              (const char *)v8,
              v58);
            if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
              McTemplateU0zd_EventWriteTransfer(v27, PackageManagerAPIDebugLog, *((_QWORD *)&v63 + 1), v8);
LABEL_80:
            details::appxLog<unsigned short *,unsigned short *>(
              v8,
              v26,
              PackageManagerAPIDebugLog,
              *((_QWORD *)&v63 + 1),
              v8);
            if ( *((_QWORD *)&v63 + 1) )
              operator delete(*((void **)&v63 + 1), v56);
            goto LABEL_82;
          }
          OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v24);
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x782,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            v58);
          v30 = TokenHandle[2];
          if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v29,
              (unsigned int)OSIMGetReferenceHandlerError,
              *((_QWORD *)*a1 + 28),
              TokenHandle[2],
              v8);
          details::appxLog<unsigned short const *,long,unsigned short *>(
            v8,
            v28,
            OSIMGetReferenceHandlerError,
            *((_QWORD *)*a1 + 28));
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x783,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            (int)v30);
        }
        else
        {
          OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v24);
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x789,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            v58);
          v30 = TokenHandle[2];
          if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v32,
              (unsigned int)OSIMGetReferenceHandlerError,
              *((_QWORD *)*a1 + 28),
              TokenHandle[2],
              v8);
          details::appxLog<unsigned short const *,long,unsigned short *>(
            v8,
            v31,
            OSIMGetReferenceHandlerError,
            *((_QWORD *)*a1 + 28));
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78A,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            (int)v30);
        }
        goto LABEL_74;
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl'::`2'::impl);
    v47 = *a1;
    v48 = *((_DWORD *)*a1 + 99) & 2;
    if ( IsEnabled )
    {
      if ( v48 || *((_DWORD *)v47 + 93) == 5 )
      {
        v63 = 0;
        LODWORD(v64) = 0;
        v68 = &v63;
        v67 = &Common::StringBufferBuilder::`vftable';
        v69 = &v63;
        Common::StringBuilder::AppendString((Common::StringBuilder *)&v67, *((const unsigned __int16 **)v47 + 28));
        Common::StringBuilder::AppendString(
          (Common::StringBuilder *)&v67,
          L": does not have a resources.pri file or could not create a resource manager");
        v52 = retaddr;
        if ( (v8 & 0x80000000) != 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x753,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            v58);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v52, PackageManagerAPIDebugLog, *((_QWORD *)&v63 + 1), v8);
        goto LABEL_80;
      }
      OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v46);
      v50 = (int)retaddr;
      if ( (v8 & 0x80000000) != 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x74A,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
          (const char *)v8,
          v58);
      v30 = TokenHandle[2];
      if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v50,
          (unsigned int)OSIMGetReferenceHandlerError,
          *((_QWORD *)*a1 + 28),
          TokenHandle[2],
          v8);
      v59 = (int)v30;
      details::appxLog<unsigned short const *,long,unsigned short *>(
        v8,
        v49,
        OSIMGetReferenceHandlerError,
        *((_QWORD *)*a1 + 28));
      if ( (v8 & 0x80000000) == 0 )
      {
LABEL_74:
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&cbSid);
        if ( !v30 )
          goto LABEL_4;
        v16 = v30;
        goto LABEL_21;
      }
      v51 = 1867;
    }
    else
    {
      if ( v48 )
      {
        v63 = 0;
        LODWORD(v64) = 0;
        v68 = &v63;
        v67 = &Common::StringBufferBuilder::`vftable';
        v69 = &v63;
        Common::StringBuilder::AppendString((Common::StringBuilder *)&v67, *((const unsigned __int16 **)v47 + 28));
        Common::StringBuilder::AppendString(
          (Common::StringBuilder *)&v67,
          L": does not have a resources.pri file or could not create a resource manager");
        v55 = retaddr;
        if ( (v8 & 0x80000000) != 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x765,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
            (const char *)v8,
            v58);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v55, PackageManagerAPIDebugLog, *((_QWORD *)&v63 + 1), v8);
        goto LABEL_80;
      }
      OSIntegration::Tools::FormatMessageInternal(v8, (Common::StringBuffer *)&TokenHandle[1], v46);
      v54 = (int)retaddr;
      if ( (v8 & 0x80000000) != 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x75C,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
          (const char *)v8,
          v58);
      v30 = TokenHandle[2];
      if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v54,
          (unsigned int)OSIMGetReferenceHandlerError,
          *((_QWORD *)*a1 + 28),
          TokenHandle[2],
          v8);
      v59 = (int)v30;
      details::appxLog<unsigned short const *,long,unsigned short *>(
        v8,
        v53,
        OSIMGetReferenceHandlerError,
        *((_QWORD *)*a1 + 28));
      if ( (v8 & 0x80000000) == 0 )
        goto LABEL_74;
      v51 = 1885;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)v8,
      v59);
    goto LABEL_74;
  }
LABEL_83:
  v57 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v57 )
    operator delete(v57, a2);
  if ( *(_QWORD *)&cbSid_8[2] )
    operator delete(*(void **)&cbSid_8[2], a2);
  return 0;
}

```

## disassembly

```asm
0x1800d8ea0  mov     rax, rsp
0x1800d8ea3  push    rbp
0x1800d8ea4  push    rbx
0x1800d8ea5  push    rsi
0x1800d8ea6  push    rdi
0x1800d8ea7  push    r14
0x1800d8ea9  push    r15
0x1800d8eab  lea     rbp, [rax-48h]
0x1800d8eaf  sub     rsp, 118h
0x1800d8eb6  movaps  xmmword ptr [rax-48h], xmm6
0x1800d8eba  mov     rax, cs:__security_cookie
0x1800d8ec1  xor     rax, rsp
0x1800d8ec4  mov     [rbp+40h+var_50], rax
0x1800d8ec8  mov     r14, rcx
0x1800d8ecb  xorps   xmm0, xmm0
0x1800d8ece  movups  xmmword ptr [rsp+140h+cbSid+8], xmm0
0x1800d8ed3  xor     r15d, r15d
0x1800d8ed6  mov     dword ptr [rsp+140h+var_F8], r15d
0x1800d8edb  xorps   xmm6, xmm6
0x1800d8ede  movups  xmmword ptr [rsp+140h+TokenHandle+8], xmm6
0x1800d8ee3  mov     [rbp+40h+var_C0], r15d
0x1800d8ee7  mov     rcx, [rcx]
0x1800d8eea  test    byte ptr [rcx+18Ch], 23h
0x1800d8ef1  jz      loc_1800D90C9
0x1800d8ef7  add     rcx, 58h ; 'X'; this
0x1800d8efb  lea     r8, [rsp+140h+cbSid+8]; struct Common::COMMON_STRING *
0x1800d8f00  lea     rdx, qword_1801BF5F8; struct Common::COMMON_STRING *
0x1800d8f07  call    ?ConcatenatePaths@Tools@OSIntegration@@YAJPEBUCOMMON_STRING@Common@@0AEAVStringBuffer@4@@Z; OSIntegration::Tools::ConcatenatePaths(Common::COMMON_STRING const *,Common::COMMON_STRING const *,Common::StringBuffer &)
0x1800d8f0c  mov     ebx, eax
0x1800d8f0e  test    eax, eax
0x1800d8f10  jns     short loc_1800D8F41
0x1800d8f12  mov     rcx, [rbp+48h]; this
0x1800d8f16  mov     r9d, eax; char *
0x1800d8f19  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d8f20  mov     edx, 713h; void *
0x1800d8f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8f2a  nop
0x1800d8f2b  mov     rcx, [rsp+140h+var_100]; void *
0x1800d8f30  test    rcx, rcx
0x1800d8f33  jz      short loc_1800D8F3A
0x1800d8f35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d8f3a  mov     eax, ebx
0x1800d8f3c  jmp     loc_1800D9797
0x1800d8f41  mov     rdx, [r14]; unsigned __int16 *
0x1800d8f44  mov     rcx, [rsp+140h+var_100]; this
0x1800d8f49  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x1800d8f4e  mov     edi, 80070005h
0x1800d8f53  cmp     eax, edi
0x1800d8f55  jnz     loc_1800D90C9
0x1800d8f5b  mov     qword ptr [rsp+140h+TokenHandle], r15
0x1800d8f60  lea     rcx, [rsp+140h+TokenHandle]; TokenHandle
0x1800d8f65  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x1800d8f6a  mov     ebx, 44h ; 'D'
0x1800d8f6f  mov     r8d, ebx; Size
0x1800d8f72  xor     edx, edx; Val
0x1800d8f74  lea     rcx, [rbp+40h+pSid]; void *
0x1800d8f78  call    memset_0
0x1800d8f7d  mov     [rsp+140h+cbSid], ebx
0x1800d8f81  lea     r9, [rsp+140h+cbSid]; cbSid
0x1800d8f86  lea     r8, [rbp+40h+pSid]; pSid
0x1800d8f8a  xor     edx, edx; DomainSid
0x1800d8f8c  lea     ecx, [rbx-29h]; WellKnownSidType
0x1800d8f8f  call    cs:__imp_CreateWellKnownSid
0x1800d8f96  nop     dword ptr [rax+rax+00h]
0x1800d8f9b  test    eax, eax
0x1800d8f9d  jnz     short loc_1800D8FC8
0x1800d8f9f  mov     rcx, [rbp+48h]; this
0x1800d8fa3  mov     r9d, edi; char *
0x1800d8fa6  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d8fad  mov     edx, 721h; void *
0x1800d8fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8fb7  nop
0x1800d8fb8  lea     rcx, [rsp+140h+TokenHandle]; this
0x1800d8fbd  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800d8fc2  nop
0x1800d8fc3  jmp     loc_1800D9055
0x1800d8fc8  mov     rcx, [r14]
0x1800d8fcb  mov     r8d, [rcx+180h]
0x1800d8fd2  shr     r8d, 8
0x1800d8fd6  not     r8b
0x1800d8fd9  and     r8b, 1; bool
0x1800d8fdd  lea     rdx, [rbp+40h+pSid]; pSid2
0x1800d8fe1  mov     rcx, [rcx+60h]; unsigned __int16 *
0x1800d8fe5  call    ?AddUserReadExecuteAccessHelper@AccessHelpers@Deployment@Common@@SAJPEBGQEAX_N@Z; Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(ushort const *,void * const,bool)
0x1800d8fea  test    eax, eax
0x1800d8fec  jns     short loc_1800D8FF5
0x1800d8fee  mov     edx, 724h
0x1800d8ff3  jmp     short loc_1800D9021
0x1800d8ff5  mov     rax, [r14]
0x1800d8ff8  mov     r8d, [rax+180h]
0x1800d8fff  shr     r8d, 8
0x1800d9003  not     r8b
0x1800d9006  and     r8b, 1; bool
0x1800d900a  lea     rdx, [rbp+40h+pSid]; pSid2
0x1800d900e  mov     rcx, [rsp+140h+var_100]; unsigned __int16 *
0x1800d9013  call    ?AddUserReadExecuteAccessHelper@AccessHelpers@Deployment@Common@@SAJPEBGQEAX_N@Z; Common::Deployment::AccessHelpers::AddUserReadExecuteAccessHelper(ushort const *,void * const,bool)
0x1800d9018  test    eax, eax
0x1800d901a  jns     short loc_1800D906B
0x1800d901c  mov     edx, 727h; void *
0x1800d9021  mov     r9d, edi; char *
0x1800d9024  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d902b  mov     rcx, [rbp+48h]; this
0x1800d902f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9034  nop
0x1800d9035  lea     rcx, [rsp+140h+TokenHandle]; this
0x1800d903a  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800d903f  nop
0x1800d9040  psrldq  xmm6, 8
0x1800d9045  movq    rcx, xmm6; void *
0x1800d904a  test    rcx, rcx
0x1800d904d  jz      short loc_1800D9055
0x1800d904f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d9054  nop
0x1800d9055  mov     rcx, [rsp+140h+var_100]; void *
0x1800d905a  test    rcx, rcx
0x1800d905d  jz      short loc_1800D9064
0x1800d905f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d9064  mov     eax, edi
0x1800d9066  jmp     loc_1800D9797
0x1800d906b  mov     rdx, [r14]; unsigned __int16 *
0x1800d906e  mov     rcx, [rsp+140h+var_100]; this
0x1800d9073  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x1800d9078  mov     ebx, eax
0x1800d907a  test    eax, eax
0x1800d907c  jns     short loc_1800D90BF
0x1800d907e  mov     rcx, [rbp+48h]; this
0x1800d9082  mov     r9d, eax; char *
0x1800d9085  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d908c  mov     edx, 729h; void *
0x1800d9091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9096  nop
0x1800d9097  lea     rcx, [rsp+140h+TokenHandle]; this
0x1800d909c  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800d90a1  nop
0x1800d90a2  psrldq  xmm6, 8
0x1800d90a7  movq    rcx, xmm6; void *
0x1800d90ac  test    rcx, rcx
0x1800d90af  jz      loc_1800D8F2B
0x1800d90b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d90ba  jmp     loc_1800D8F2B
0x1800d90bf  lea     rcx, [rsp+140h+TokenHandle]; this
0x1800d90c4  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800d90c9  mov     rcx, [r14]
0x1800d90cc  cmp     [rcx], r15b
0x1800d90cf  jnz     short loc_1800D90DE
0x1800d90d1  cmp     [rcx+171h], r15b
0x1800d90d8  jz      loc_1800D9771
0x1800d90de  mov     qword ptr [rsp+140h+cbSid], r15
0x1800d90e3  add     rcx, 20h ; ' '
0x1800d90e7  lea     rdx, [rsp+140h+cbSid]
0x1800d90ec  call    ??$As@UIMrtResourceManager2@@@?$ComPtr@UIMrtResourceManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMrtResourceManager2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMrtResourceManager>::As<IMrtResourceManager2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMrtResourceManager2>>)
0x1800d90f1  mov     ebx, eax
0x1800d90f3  test    eax, eax
0x1800d90f5  js      loc_1800D94AB
0x1800d90fb  mov     r8, [r14]
0x1800d90fe  mov     rcx, qword ptr [rsp+140h+cbSid]
0x1800d9103  mov     rdx, [rsp+140h+var_100]
0x1800d9108  mov     rax, [rcx]
0x1800d910b  cmp     [r8+171h], r15b
0x1800d9112  mov     r8, [r8+0E0h]
0x1800d9119  jz      short loc_1800D9121
0x1800d911b  mov     rax, [rax+28h]
0x1800d911f  jmp     short loc_1800D9125
0x1800d9121  mov     rax, [rax+18h]
0x1800d9125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d912a  mov     ebx, eax
0x1800d912c  test    eax, eax
0x1800d912e  js      loc_1800D94AB
0x1800d9134  mov     rdx, [r14]
0x1800d9137  mov     rsi, [rdx+20h]
0x1800d913b  mov     rax, [rsi]
0x1800d913e  mov     rdi, [rax+38h]
0x1800d9142  lea     rbx, [rdx+8]
0x1800d9146  mov     rcx, rbx
0x1800d9149  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800d914e  mov     r8, rbx
0x1800d9151  lea     rdx, IID_IResourceMap
0x1800d9158  mov     rcx, rsi
0x1800d915b  mov     rax, rdi
0x1800d915e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9163  mov     ebx, eax
0x1800d9165  test    eax, eax
0x1800d9167  jns     loc_1800D9321
0x1800d916d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB> `wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl(void)'::`2'::impl
0x1800d9174  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(void)
0x1800d9179  test    al, al
0x1800d917b  jz      loc_1800D92A7
0x1800d9181  mov     rdx, [r14]
0x1800d9184  cmp     dword ptr [rdx+174h], 5
0x1800d918b  jnz     loc_1800D922D
0x1800d9191  xorps   xmm0, xmm0
0x1800d9194  movups  [rsp+140h+var_F8+8], xmm0
0x1800d9199  mov     dword ptr [rsp+140h+var_E0], r15d
0x1800d919e  lea     rax, [rsp+140h+var_F8+8]
0x1800d91a3  mov     [rbp+40h+var_B0], rax
0x1800d91a7  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800d91ae  mov     [rbp+40h+var_B8], rax
0x1800d91b2  lea     rax, [rsp+140h+var_F8+8]
0x1800d91b7  mov     [rbp+40h+var_A8], rax
0x1800d91bb  mov     rdx, [rdx+0E0h]; unsigned __int16 *
0x1800d91c2  lea     rcx, [rbp+40h+var_B8]; this
0x1800d91c6  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800d91cb  lea     rdx, aSignedSbomPack; ": Signed SBOM package - could not get m"...
0x1800d91d2  lea     rcx, [rbp+40h+var_B8]; this
0x1800d91d6  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800d91db  mov     rcx, [rbp+48h]; this
0x1800d91df  mov     r9d, ebx; char *
0x1800d91e2  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d91e9  mov     edx, 77Ch; void *
0x1800d91ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d91f3  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r15b
0x1800d91fa  jge     short loc_1800D9210
0x1800d91fc  mov     r9d, ebx
0x1800d91ff  mov     r8, [rsp+140h+var_E8]
0x1800d9204  lea     rdx, PackageManagerAPIDebugLog
0x1800d920b  call    McTemplateU0zd_EventWriteTransfer
0x1800d9210  mov     [rsp+140h+var_120], ebx
0x1800d9214  mov     r9, [rsp+140h+var_E8]
0x1800d9219  lea     r8, PackageManagerAPIDebugLog
0x1800d9220  mov     ecx, ebx
0x1800d9222  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x1800d9227  nop
0x1800d9228  jmp     loc_1800D9756
0x1800d922d  lea     rdx, [rsp+140h+TokenHandle+8]; this
0x1800d9232  mov     ecx, ebx; dwMessageId
0x1800d9234  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800d9239  mov     rcx, [rbp+48h]; this
0x1800d923d  mov     r9d, ebx; char *
0x1800d9240  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d9247  mov     edx, 782h; void *
0x1800d924c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d9251  mov     rdi, qword ptr [rsp+140h+TokenHandle+10h]
0x1800d9256  test    cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 1
0x1800d925d  jz      short loc_1800D927C
0x1800d925f  mov     r8, [r14]
0x1800d9262  mov     [rsp+140h+var_120], ebx
0x1800d9266  mov     r9, rdi
0x1800d9269  mov     r8, [r8+0E0h]
0x1800d9270  lea     rdx, OSIMGetReferenceHandlerError
0x1800d9277  call    McTemplateU0zzd_EventWriteTransfer
0x1800d927c  mov     r9, [r14]
0x1800d927f  mov     dword ptr [rsp+140h+var_118], ebx
0x1800d9283  mov     qword ptr [rsp+140h+var_120], rdi
0x1800d9288  mov     r9, [r9+0E0h]
0x1800d928f  lea     r8, OSIMGetReferenceHandlerError
0x1800d9296  mov     ecx, ebx
0x1800d9298  call    ??$appxLog@PEBGJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGJPEAG@Z; details::appxLog<ushort const *,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,long,ushort *)
0x1800d929d  mov     edx, 783h
0x1800d92a2  jmp     loc_1800D968B
0x1800d92a7  lea     rdx, [rsp+140h+TokenHandle+8]; this
0x1800d92ac  mov     ecx, ebx; dwMessageId
0x1800d92ae  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800d92b3  mov     rcx, [rbp+48h]; this
0x1800d92b7  mov     r9d, ebx; char *
0x1800d92ba  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d92c1  mov     edx, 789h; void *
0x1800d92c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d92cb  mov     rdi, qword ptr [rsp+140h+TokenHandle+10h]
0x1800d92d0  test    cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 1
0x1800d92d7  jz      short loc_1800D92F6
0x1800d92d9  mov     r8, [r14]
0x1800d92dc  mov     [rsp+140h+var_120], ebx
0x1800d92e0  mov     r9, rdi
0x1800d92e3  mov     r8, [r8+0E0h]
0x1800d92ea  lea     rdx, OSIMGetReferenceHandlerError
0x1800d92f1  call    McTemplateU0zzd_EventWriteTransfer
0x1800d92f6  mov     r9, [r14]
0x1800d92f9  mov     dword ptr [rsp+140h+var_118], ebx
0x1800d92fd  mov     qword ptr [rsp+140h+var_120], rdi
0x1800d9302  mov     r9, [r9+0E0h]
0x1800d9309  lea     r8, OSIMGetReferenceHandlerError
0x1800d9310  mov     ecx, ebx
0x1800d9312  call    ??$appxLog@PEBGJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGJPEAG@Z; details::appxLog<ushort const *,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,long,ushort *)
0x1800d9317  mov     edx, 78Ah
0x1800d931c  jmp     loc_1800D968B
0x1800d9321  mov     rdx, [r14]
0x1800d9324  mov     rsi, [rdx+8]
0x1800d9328  mov     rax, [rsi]
0x1800d932b  mov     rdi, [rax+20h]
0x1800d932f  lea     rbx, [rdx+10h]
0x1800d9333  mov     rcx, rbx
0x1800d9336  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800d933b  mov     r8, rbx
0x1800d933e  lea     rdx, aFiles; "Files"
0x1800d9345  mov     rcx, rsi
0x1800d9348  mov     rax, rdi
0x1800d934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9350  mov     ebx, eax
0x1800d9352  mov     eax, 80000000h
0x1800d9357  lea     ecx, [rbx+rax]
0x1800d935a  test    eax, ecx
0x1800d935c  jnz     loc_1800D93E4
0x1800d9362  cmp     ebx, 80073B1Fh
0x1800d9368  jz      short loc_1800D93E4
0x1800d936a  lea     rdx, [rsp+140h+TokenHandle+8]; this
0x1800d936f  mov     ecx, ebx; dwMessageId
0x1800d9371  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800d9376  mov     rcx, [rbp+48h]; this
0x1800d937a  mov     r9d, ebx; char *
0x1800d937d  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
  ... truncated ...
```
