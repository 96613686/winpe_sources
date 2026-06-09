# Common::Deployment::MRTHelper::Initialize(ushort const *,ushort const *,bool,bool)

- ea: `0x1800079d0`
- end: `0x1800081e6`
- name: `?Initialize@MRTHelper@Deployment@Common@@QEAAJPEBG0_N1@Z`
- size: `2070`
- prototype: `int(Common::Deployment::MRTHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, bool)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005b808`
- `0x180081b38`
- `0x1800ee118`

## callees

- `0x18000669c`
- `0x180006970`
- `0x1800069a0`
- `0x180006b10`
- `0x180007908`
- `0x1800079d0`
- `0x180009dc0`
- `0x180012fc8`
- `0x180015590`
- `0x180017640`
- `0x180022f94`
- `0x18003d814`
- `0x18003d8f4`
- `0x180056c2c`
- `0x18007bb18`
- `0x180099b44`
- `0x1800a12bc`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800ba45d`
- `0x1800d6fe0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007e29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007e29`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000815d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000815d`
- `KERNEL32!CopyFileW` at `0x180008175`
- `KERNEL32!CopyFileW` at `0x180008175`

## string_xrefs

- `0x180007a4b`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007a86`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007c78`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007de6`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007e88`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007eed`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007f65`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180008031`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180008141`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x18000818c`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180007ba2`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Common::Deployment::MRTHelper::Initialize(
        Common::Deployment::MRTHelper *this,
        const unsigned __int16 *a2,
        Common::Deployment::Configuration *a3,
        char a4,
        bool a5)
{
  struct Common::StringBuffer *v8; // r8
  signed int RedirectedResourceRootForPackage; // ebx
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdi
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  wil::details::in1diag3 *v21; // rcx
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  wil::details::in1diag3 *v25; // rcx
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  __int64 v28; // r11
  const unsigned __int16 *v29; // rax
  __int64 v30; // rdi
  wil::details::in1diag3 *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r12
  wil::details::in1diag3 *v34; // rcx
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  int v37; // eax
  const unsigned __int16 *v38; // r14
  _BYTE *v39; // r12
  unsigned int v40; // eax
  const unsigned __int16 *v41; // r8
  HRESULT Instance; // eax
  wil::details::in1diag3 *v43; // rcx
  __int64 v44; // rdx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v46)(_QWORD, GUID *, void **); // rbx
  int v47; // eax
  void *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rax
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // rdx
  __int64 *v55; // r8
  int v56; // eax
  const unsigned __int16 *v57; // rax
  __int64 v58; // rcx
  void *v59; // rcx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, GUID *, char *); // r14
  char *v62; // rbx
  __int64 v63; // rcx
  int v64; // eax
  unsigned int v65; // edi
  const struct std::nothrow_t *v66; // rdx
  __int64 v68; // r14
  void (__fastcall *v69)(__int64, const unsigned __int16 *, char *); // r15
  __int64 v70; // rcx
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, const wchar_t *, char *); // r14
  __int64 v73; // rcx
  signed int v74; // eax
  int v75; // eax
  const char *v76; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  char v79; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v81; // [rsp+50h] [rbp-B0h]
  void **v82; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR *v83; // [rsp+60h] [rbp-A0h]
  LPCWSTR *v84; // [rsp+68h] [rbp-98h]
  unsigned __int16 v85[4]; // [rsp+70h] [rbp-90h] BYREF
  int v86; // [rsp+78h] [rbp-88h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v79 = a4;
  Common::Deployment::MRTHelper::ResetResourceMaps(this);
  *((_BYTE *)this + 136) = a5;
  if ( a5 )
  {
    RedirectedResourceRootForPackage = Common::Deployment::Configuration::GetRedirectedResourceRootForPackage(
                                         a3,
                                         (Common::Deployment::MRTHelper *)((char *)this + 112),
                                         v8);
    v10 = retaddr;
    if ( RedirectedResourceRootForPackage < 0 )
    {
      v11 = 221;
LABEL_4:
      wil::details::in1diag3::_Log_Hr(
        v10,
        (void *)v11,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
        (const char *)(unsigned int)RedirectedResourceRootForPackage,
        ppv);
      return (unsigned int)RedirectedResourceRootForPackage;
    }
    TokenHandle = 0;
    Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle);
    RedirectedResourceRootForPackage = Common::Deployment::RecursiveCreateDirectory(
                                         *((Common::Deployment **)this + 15),
                                         v12);
    v13 = retaddr;
    if ( RedirectedResourceRootForPackage < 0 )
    {
      v14 = 225;
LABEL_7:
      wil::details::in1diag3::_Log_Hr(
        v13,
        (void *)v14,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
        (const char *)(unsigned int)RedirectedResourceRootForPackage,
        ppv);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
      return (unsigned int)RedirectedResourceRootForPackage;
    }
    RedirectedResourceRootForPackage = Common::Deployment::AccessHelpers::AddPackageReadAccessHelper(
                                         *((const unsigned __int16 **)this + 15),
                                         (const unsigned __int16 *)a3);
    v13 = retaddr;
    if ( RedirectedResourceRootForPackage < 0 )
    {
      v14 = 226;
      goto LABEL_7;
    }
    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
  }
  RedirectedResourceRootForPackage = Common::StringBuffer::SetValueFromString(
                                       (Common::Deployment::MRTHelper *)((char *)this + 40),
                                       a2);
  v10 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v11 = 229;
    goto LABEL_4;
  }
  RedirectedResourceRootForPackage = Common::StringBuffer::SetValueFromString(
                                       (Common::Deployment::MRTHelper *)((char *)this + 64),
                                       (const unsigned __int16 *)a3);
  v10 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v11 = 230;
    goto LABEL_4;
  }
  *(_OWORD *)lpExistingFileName = 0;
  v81 = 0;
  v83 = lpExistingFileName;
  v82 = &Common::StringBufferBuilder::`vftable';
  v84 = lpExistingFileName;
  if ( !a2 )
  {
    RedirectedResourceRootForPackage = -2147024809;
LABEL_22:
    LODWORD(v17) = 0;
    goto LABEL_23;
  }
  v15 = 0x3FFFFFFF;
  v16 = a2;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v17 = (0x3FFFFFFF - v15) & -(__int64)(v15 != 0);
  RedirectedResourceRootForPackage = v15 == 0 ? 0x80070057 : 0;
  if ( !v15 )
    goto LABEL_22;
LABEL_23:
  v18 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v19 = 53;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)RedirectedResourceRootForPackage,
      ppv);
    goto LABEL_38;
  }
  v20 = (unsigned int)_mm_cvtsi128_si32((__m128i)0LL);
  LODWORD(TokenHandle) = v20;
  RedirectedResourceRootForPackage = ~(_DWORD)v17 < (unsigned int)v20 ? 0x80070216 : 0;
  v21 = retaddr;
  if ( (unsigned int)v20 <= ~(_DWORD)v17 )
  {
    if ( (unsigned int)(v20 + v17) > 0x3FFFFFFF )
    {
      RedirectedResourceRootForPackage = -2147023613;
      goto LABEL_35;
    }
    v24 = Common::StringBufferBuilder::SetLength((Common::StringBufferBuilder *)&v82, (int)v20 + (int)v17);
    RedirectedResourceRootForPackage = v24;
    v21 = retaddr;
    if ( v24 >= 0 )
    {
      RedirectedResourceRootForPackage = 0;
      goto LABEL_34;
    }
    v22 = (unsigned int)v24;
    v23 = 269;
  }
  else
  {
    v22 = (unsigned int)RedirectedResourceRootForPackage;
    v23 = 263;
  }
  wil::details::in1diag3::_Log_Hr(
    v21,
    (void *)v23,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v22,
    ppv);
LABEL_34:
  v20 = (unsigned int)TokenHandle;
LABEL_35:
  v18 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v19 = 121;
    goto LABEL_25;
  }
  memcpy_0((void *)&v83[1][v20], a2, 2LL * (unsigned int)v17);
  RedirectedResourceRootForPackage = 0;
LABEL_38:
  v25 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v26 = 235;
LABEL_40:
    wil::details::in1diag3::_Log_Hr(
      v25,
      (void *)v26,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)RedirectedResourceRootForPackage,
      ppv);
    goto LABEL_103;
  }
  v28 = 0x3FFFFFFF;
  v29 = L"\\resources.pri";
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  RedirectedResourceRootForPackage = v28 == 0 ? 0x80070057 : 0;
  v30 = (0x3FFFFFFF - v28) & -(__int64)(v28 != 0);
  v31 = retaddr;
  if ( !v28 )
  {
    v32 = 53;
LABEL_46:
    wil::details::in1diag3::_Log_Hr(
      v31,
      (void *)v32,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)RedirectedResourceRootForPackage,
      ppv);
    goto LABEL_58;
  }
  v33 = *(unsigned int *)v83;
  RedirectedResourceRootForPackage = ~(_DWORD)v30 < (unsigned int)v33 ? 0x80070216 : 0;
  v34 = retaddr;
  if ( (unsigned int)v33 > ~(_DWORD)v30 )
  {
    v35 = (unsigned int)RedirectedResourceRootForPackage;
    v36 = 263;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      v34,
      (void *)v36,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v35,
      ppv);
    goto LABEL_55;
  }
  if ( (unsigned int)(v30 + v33) <= 0x3FFFFFFF )
  {
    v37 = ((__int64 (__fastcall *)(void ***))*v82)(&v82);
    RedirectedResourceRootForPackage = v37;
    v34 = retaddr;
    if ( v37 < 0 )
    {
      v35 = (unsigned int)v37;
      v36 = 269;
      goto LABEL_49;
    }
    RedirectedResourceRootForPackage = 0;
  }
  else
  {
    RedirectedResourceRootForPackage = -2147023613;
  }
LABEL_55:
  v31 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v32 = 121;
    goto LABEL_46;
  }
  memcpy_0((void *)&v83[1][v33], L"\\resources.pri", 2LL * (unsigned int)v30);
  RedirectedResourceRootForPackage = 0;
LABEL_58:
  v25 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v26 = 236;
    goto LABEL_40;
  }
  v38 = lpExistingFileName[1];
  v39 = (char *)this + 137;
  v40 = NonZeroByteFileExists(lpExistingFileName[1]);
  Instance = Common::Deployment::LogIfAccessDenied((Common::Deployment *)v40, (int)v38, v41);
  RedirectedResourceRootForPackage = Instance;
  v43 = retaddr;
  if ( Instance < 0 )
  {
    v44 = 286;
LABEL_62:
    wil::details::in1diag3::_Log_Hr(
      v43,
      (void *)v44,
      (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_82;
  }
  if ( *v39 )
  {
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease((char *)this + 8);
    Instance = CoCreateInstance(
                 &CLSID_MrtResourceManager,
                 0,
                 1u,
                 &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                 (LPVOID *)this + 1);
    RedirectedResourceRootForPackage = Instance;
    v43 = retaddr;
    if ( Instance < 0 )
    {
      v44 = 290;
      goto LABEL_62;
    }
    TokenHandle = 0;
    v45 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 1);
    v46 = **v45;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&TokenHandle);
    v47 = v46(v45, &GUID_439dd7c9_0eeb_4715_baa7_f0877694e616, &TokenHandle);
    RedirectedResourceRootForPackage = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
        (const char *)(unsigned int)v47,
        ppv);
      v48 = TokenHandle;
      if ( TokenHandle )
      {
        TokenHandle = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 16LL))(v48);
      }
      goto LABEL_82;
    }
    v49 = *(_QWORD *)TokenHandle;
    if ( v79 )
    {
      v50 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, Common::Deployment::Configuration *))(v49 + 40))(
              TokenHandle,
              v38,
              a3);
      RedirectedResourceRootForPackage = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
          (const char *)(unsigned int)v50,
          ppv);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        {
          v51 = RemovePIIfromFilePath(v38);
          McTemplateU0zz_EventWriteTransfer(v52, InitializeInboxMrtResourceManagerFailure, a3, v51);
        }
        v53 = (unsigned int)RemovePIIfromFilePath(v38);
        v55 = InitializeInboxMrtResourceManagerFailure;
LABEL_75:
        ppv = v53;
        details::appxLog<unsigned short *,unsigned short *>(
          (unsigned int)RedirectedResourceRootForPackage,
          v54,
          v55,
          a3);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&TokenHandle);
        goto LABEL_82;
      }
    }
    else
    {
      v56 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, Common::Deployment::Configuration *))(v49 + 24))(
              TokenHandle,
              v38,
              a3);
      RedirectedResourceRootForPackage = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
          (const char *)(unsigned int)v56,
          ppv);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        {
          v57 = RemovePIIfromFilePath(v38);
          McTemplateU0zz_EventWriteTransfer(v58, InitializePackageMrtResourceManagerFailure, a3, v57);
        }
        v53 = (unsigned int)RemovePIIfromFilePath(v38);
        v55 = InitializePackageMrtResourceManagerFailure;
        goto LABEL_75;
      }
    }
    v59 = TokenHandle;
    if ( TokenHandle )
    {
      TokenHandle = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v59 + 16LL))(v59);
    }
  }
LABEL_82:
  v25 = retaddr;
  if ( RedirectedResourceRootForPackage < 0 )
  {
    v26 = 238;
    goto LABEL_40;
  }
  if ( !*v39 )
  {
LABEL_103:
    if ( lpExistingFileName[1] )
      operator delete((void *)lpExistingFileName[1], v27);
    return (unsigned int)RedirectedResourceRootForPackage;
  }
  v60 = *((_QWORD *)this + 1);
  v61 = *(__int64 (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v60 + 56LL);
  v62 = (char *)this + 16;
  v63 = *((_QWORD *)this + 2);
  if ( v63 )
  {
    *(_QWORD *)v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  }
  v64 = v61(v60, &IID_IResourceMap, (char *)this + 16);
  v65 = v64;
  if ( v64 >= 0 )
  {
    v68 = *(_QWORD *)v62;
    v69 = *(void (__fastcall **)(__int64, const unsigned __int16 *, char *))(**(_QWORD **)v62 + 32LL);
    v70 = *((_QWORD *)this + 3);
    if ( v70 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v69(v68, L"Resources", (char *)this + 24);
    v71 = *(_QWORD *)v62;
    v72 = *(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(**(_QWORD **)v62 + 32LL);
    v73 = *((_QWORD *)this + 4);
    if ( v73 )
    {
      *((_QWORD *)this + 4) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v72(v71, L"Files", (char *)this + 32);
    RedirectedResourceRootForPackage = 0;
    if ( v74 != -2147009761 )
      RedirectedResourceRootForPackage = v74;
    if ( *((_BYTE *)this + 136) )
    {
      *(_QWORD *)v85 = *(_QWORD *)L"%s\\%s";
      v86 = *(_DWORD *)L"s";
      TokenHandle = 0;
      Common::AutoNoImpersonateDuringScope::DropImpersonation(&TokenHandle);
      v75 = StringCchPrintfW(FileName, 0x104u, v85, *((_QWORD *)this + 15));
      RedirectedResourceRootForPackage = v75;
      if ( v75 >= 0 )
      {
        SetFileAttributesW(FileName, 0x80u);
        if ( !CopyFileW(lpExistingFileName[1], FileName, 0) )
          RedirectedResourceRootForPackage = wil::details::in1diag3::Return_GetLastError(
                                               retaddr,
                                               (void *)0x110,
                                               (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
                                               v76);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
          (const char *)(unsigned int)v75,
          (int)L"resources.pri");
      }
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&TokenHandle);
    }
    goto LABEL_103;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xF6,
    (unsigned int)"onecore\\admin\\appmodel\\common\\mrthelper.cpp",
    (const char *)(unsigned int)v64,
    ppv);
  if ( lpExistingFileName[1] )
    operator delete((void *)lpExistingFileName[1], v66);
  return v65;
}

```

## disassembly

```asm
0x1800079d0  mov     [rsp-8+arg_18], rbx
0x1800079d5  push    rbp
0x1800079d6  push    rsi
0x1800079d7  push    rdi
0x1800079d8  push    r12
0x1800079da  push    r13
0x1800079dc  push    r14
0x1800079de  push    r15
0x1800079e0  lea     rbp, [rsp-1A0h]
0x1800079e8  sub     rsp, 2A0h
0x1800079ef  mov     rax, cs:__security_cookie
0x1800079f6  xor     rax, rsp
0x1800079f9  mov     [rbp+1D0h+var_40], rax
0x180007a00  mov     [rsp+2D0h+var_298], r9b
0x180007a05  mov     r15, r8
0x180007a08  mov     r12, rdx
0x180007a0b  mov     rsi, rcx
0x180007a0e  call    ?ResetResourceMaps@MRTHelper@Deployment@Common@@AEAAXXZ; Common::Deployment::MRTHelper::ResetResourceMaps(void)
0x180007a13  mov     al, [rbp+1D0h+arg_20]
0x180007a19  mov     [rsi+88h], al
0x180007a1f  xor     r14d, r14d
0x180007a22  test    al, al
0x180007a24  jz      loc_180007ACF
0x180007a2a  lea     rdx, [rsi+70h]; Common::StringBuffer *
0x180007a2e  mov     rcx, r15; this
0x180007a31  call    ?GetRedirectedResourceRootForPackage@Configuration@Deployment@Common@@YAJPEBGPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetRedirectedResourceRootForPackage(ushort const *,Common::StringBuffer *)
0x180007a36  mov     ebx, eax
0x180007a38  mov     rcx, [rbp+1D8h]; this
0x180007a3f  test    eax, eax
0x180007a41  jns     short loc_180007A5C
0x180007a43  mov     edx, 0DDh; void *
0x180007a48  mov     r9d, ebx; char *
0x180007a4b  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180007a52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a57  jmp     loc_1800081B9
0x180007a5c  mov     [rsp+2D0h+TokenHandle], r14
0x180007a61  lea     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x180007a66  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x180007a6b  mov     rcx, [rsi+78h]; this
0x180007a6f  call    ?RecursiveCreateDirectory@Deployment@Common@@YAJPEBG@Z; Common::Deployment::RecursiveCreateDirectory(ushort const *)
0x180007a74  mov     ebx, eax
0x180007a76  mov     rcx, [rbp+1D8h]; this
0x180007a7d  test    eax, eax
0x180007a7f  jns     short loc_180007AA5
0x180007a81  mov     edx, 0E1h; void *
0x180007a86  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180007a8d  mov     r9d, ebx; char *
0x180007a90  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a95  nop
0x180007a96  lea     rcx, [rsp+2D0h+TokenHandle]; this
0x180007a9b  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x180007aa0  jmp     loc_1800081B9
0x180007aa5  mov     rdx, r15; unsigned __int16 *
0x180007aa8  mov     rcx, [rsi+78h]; unsigned __int16 *
0x180007aac  call    ?AddPackageReadAccessHelper@AccessHelpers@Deployment@Common@@SAJPEBG0@Z; Common::Deployment::AccessHelpers::AddPackageReadAccessHelper(ushort const *,ushort const *)
0x180007ab1  mov     ebx, eax
0x180007ab3  mov     rcx, [rbp+1D8h]
0x180007aba  test    eax, eax
0x180007abc  jns     short loc_180007AC5
0x180007abe  mov     edx, 0E2h
0x180007ac3  jmp     short loc_180007A86
0x180007ac5  lea     rcx, [rsp+2D0h+TokenHandle]; this
0x180007aca  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x180007acf  lea     rcx, [rsi+28h]; this
0x180007ad3  mov     rdx, r12; unsigned __int16 *
0x180007ad6  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180007adb  mov     ebx, eax
0x180007add  mov     rcx, [rbp+1D8h]
0x180007ae4  test    eax, eax
0x180007ae6  jns     short loc_180007AF2
0x180007ae8  mov     edx, 0E5h
0x180007aed  jmp     loc_180007A48
0x180007af2  lea     rcx, [rsi+40h]; this
0x180007af6  mov     rdx, r15; unsigned __int16 *
0x180007af9  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180007afe  mov     ebx, eax
0x180007b00  mov     rcx, [rbp+1D8h]
0x180007b07  test    eax, eax
0x180007b09  jns     short loc_180007B15
0x180007b0b  mov     edx, 0E6h
0x180007b10  jmp     loc_180007A48
0x180007b15  xorps   xmm0, xmm0
0x180007b18  movups  xmmword ptr [rsp+2D0h+lpExistingFileName], xmm0
0x180007b1d  mov     [rsp+2D0h+var_280], r14d
0x180007b22  lea     rax, [rsp+2D0h+lpExistingFileName]
0x180007b27  mov     [rsp+2D0h+var_270], rax
0x180007b2c  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180007b33  mov     [rsp+2D0h+var_278], rax
0x180007b38  lea     rax, [rsp+2D0h+lpExistingFileName]
0x180007b3d  mov     [rsp+2D0h+var_268], rax
0x180007b42  mov     r8d, 3FFFFFFFh
0x180007b48  test    r12, r12
0x180007b4b  jz      short loc_180007B8F
0x180007b4d  mov     edx, r8d
0x180007b50  mov     rax, r12
0x180007b53  cmp     [rax], r14w
0x180007b57  jz      short loc_180007B63
0x180007b59  add     rax, 2
0x180007b5d  sub     rdx, 1
0x180007b61  jnz     short loc_180007B53
0x180007b63  mov     rax, rdx
0x180007b66  mov     rcx, r8
0x180007b69  sub     rcx, rdx
0x180007b6c  neg     rax
0x180007b6f  sbb     rdi, rdi
0x180007b72  and     rdi, rcx
0x180007b75  mov     rax, rdx
0x180007b78  neg     rax
0x180007b7b  sbb     ebx, ebx
0x180007b7d  not     ebx
0x180007b7f  mov     r13d, 80070057h
0x180007b85  and     ebx, r13d
0x180007b88  test    rdx, rdx
0x180007b8b  jz      short loc_180007B98
0x180007b8d  jmp     short loc_180007B9B
0x180007b8f  mov     r13d, 80070057h
0x180007b95  mov     ebx, r13d
0x180007b98  mov     rdi, r14
0x180007b9b  mov     rcx, [rbp+1D8h]; this
0x180007ba2  lea     r14, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\string"...
0x180007ba9  test    ebx, ebx
0x180007bab  jns     short loc_180007BC2
0x180007bad  mov     edx, 35h ; '5'; void *
0x180007bb2  mov     r8, r14; unsigned int
0x180007bb5  mov     r9d, ebx; char *
0x180007bb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007bbd  jmp     loc_180007C63
0x180007bc2  movd    r9d, xmm0
0x180007bc7  mov     dword ptr [rsp+2D0h+TokenHandle], r9d
0x180007bcc  mov     eax, edi
0x180007bce  not     eax
0x180007bd0  cmp     eax, r9d
0x180007bd3  sbb     ebx, ebx
0x180007bd5  and     ebx, 80070216h
0x180007bdb  mov     rcx, [rbp+1D8h]; this
0x180007be2  cmp     r9d, eax
0x180007be5  jbe     short loc_180007BF9
0x180007be7  mov     r9d, ebx; char *
0x180007bea  mov     edx, 107h; void *
0x180007bef  mov     r8, r14; unsigned int
0x180007bf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007bf7  jmp     short loc_180007C2C
0x180007bf9  lea     edx, [r9+rdi]; unsigned int
0x180007bfd  cmp     edx, r8d
0x180007c00  jbe     short loc_180007C09
0x180007c02  mov     ebx, 80070503h
0x180007c07  jmp     short loc_180007C31
0x180007c09  lea     rcx, [rsp+2D0h+var_278]; this
0x180007c0e  call    ?SetLength@StringBufferBuilder@Common@@UEAAJK@Z; Common::StringBufferBuilder::SetLength(ulong)
0x180007c13  mov     ebx, eax
0x180007c15  mov     rcx, [rbp+1D8h]
0x180007c1c  test    eax, eax
0x180007c1e  jns     short loc_180007C2A
0x180007c20  mov     r9d, eax
0x180007c23  mov     edx, 10Dh
0x180007c28  jmp     short loc_180007BEF
0x180007c2a  xor     ebx, ebx
0x180007c2c  mov     r9d, dword ptr [rsp+2D0h+TokenHandle]
0x180007c31  mov     rcx, [rbp+1D8h]
0x180007c38  test    ebx, ebx
0x180007c3a  jns     short loc_180007C46
0x180007c3c  mov     edx, 79h ; 'y'
0x180007c41  jmp     loc_180007BB2
0x180007c46  mov     r8d, edi
0x180007c49  add     r8, r8; Size
0x180007c4c  mov     rax, [rsp+2D0h+var_270]
0x180007c51  mov     rcx, [rax+8]
0x180007c55  lea     rcx, [rcx+r9*2]; void *
0x180007c59  mov     rdx, r12; Src
0x180007c5c  call    memcpy_0
0x180007c61  xor     ebx, ebx
0x180007c63  mov     rcx, [rbp+1D8h]; this
0x180007c6a  xor     edi, edi
0x180007c6c  test    ebx, ebx
0x180007c6e  jns     short loc_180007C89
0x180007c70  mov     edx, 0EBh; void *
0x180007c75  mov     r9d, ebx; char *
0x180007c78  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180007c7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007c84  jmp     loc_1800081AA
0x180007c89  mov     r8d, 3FFFFFFFh
0x180007c8f  mov     r11d, r8d
0x180007c92  lea     rax, aResourcesPri_0; "\\resources.pri"
0x180007c99  cmp     [rax], di
0x180007c9c  jz      short loc_180007CA8
0x180007c9e  add     rax, 2
0x180007ca2  sub     r11, 1
0x180007ca6  jnz     short loc_180007C99
0x180007ca8  mov     rax, r11
0x180007cab  neg     rax
0x180007cae  sbb     ebx, ebx
0x180007cb0  not     ebx
0x180007cb2  and     ebx, r13d
0x180007cb5  mov     r10, r11
0x180007cb8  mov     rax, r11
0x180007cbb  mov     rcx, r8
0x180007cbe  sub     rcx, r11
0x180007cc1  neg     rax
0x180007cc4  sbb     r9, r9
0x180007cc7  and     r9, rcx
0x180007cca  neg     r10
0x180007ccd  sbb     rdi, rdi
0x180007cd0  and     rdi, r9
0x180007cd3  mov     rcx, [rbp+1D8h]; this
0x180007cda  xor     r13d, r13d
0x180007cdd  test    r11, r11
0x180007ce0  jnz     short loc_180007CF6
0x180007ce2  lea     edx, [r13+35h]; void *
0x180007ce6  mov     r8, r14; unsigned int
0x180007ce9  mov     r9d, ebx; char *
0x180007cec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007cf1  jmp     loc_180007D9E
0x180007cf6  mov     rax, [rsp+2D0h+var_270]
0x180007cfb  mov     r12d, [rax]
0x180007cfe  mov     eax, edi
0x180007d00  not     eax
0x180007d02  cmp     eax, r12d
0x180007d05  sbb     ebx, ebx
0x180007d07  and     ebx, 80070216h
0x180007d0d  mov     rcx, [rbp+1D8h]; this
0x180007d14  cmp     r12d, eax
0x180007d17  jbe     short loc_180007D2B
0x180007d19  mov     r9d, ebx; char *
0x180007d1c  mov     edx, 107h; void *
0x180007d21  mov     r8, r14; unsigned int
0x180007d24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007d29  jmp     short loc_180007D67
0x180007d2b  lea     edx, [rdi+r12]
0x180007d2f  cmp     edx, r8d
0x180007d32  jbe     short loc_180007D3B
0x180007d34  mov     ebx, 80070503h
0x180007d39  jmp     short loc_180007D67
0x180007d3b  mov     rax, [rsp+2D0h+var_278]
0x180007d40  lea     rcx, [rsp+2D0h+var_278]
0x180007d45  mov     rax, [rax]
0x180007d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4d  mov     ebx, eax
0x180007d4f  mov     rcx, [rbp+1D8h]
0x180007d56  test    eax, eax
0x180007d58  jns     short loc_180007D64
0x180007d5a  mov     r9d, eax
0x180007d5d  mov     edx, 10Dh
0x180007d62  jmp     short loc_180007D21
0x180007d64  mov     ebx, r13d
0x180007d67  mov     rcx, [rbp+1D8h]
0x180007d6e  test    ebx, ebx
0x180007d70  jns     short loc_180007D7C
0x180007d72  mov     edx, 79h ; 'y'
0x180007d77  jmp     loc_180007CE6
0x180007d7c  mov     r8d, edi
0x180007d7f  add     r8, r8; Size
0x180007d82  mov     rax, [rsp+2D0h+var_270]
0x180007d87  mov     rcx, [rax+8]
0x180007d8b  lea     rcx, [rcx+r12*2]; void *
0x180007d8f  lea     rdx, aResourcesPri_0; "\\resources.pri"
0x180007d96  call    memcpy_0
0x180007d9b  mov     ebx, r13d
0x180007d9e  mov     rcx, [rbp+1D8h]
0x180007da5  test    ebx, ebx
0x180007da7  jns     short loc_180007DB3
0x180007da9  mov     edx, 0ECh
0x180007dae  jmp     loc_180007C75
0x180007db3  mov     r14, [rsp+2D0h+lpExistingFileName+8]
0x180007db8  lea     r12, [rsi+89h]
0x180007dbf  mov     rdx, r12
0x180007dc2  mov     rcx, r14; lpFileName
0x180007dc5  call    NonZeroByteFileExists
0x180007dca  mov     ecx, eax; this
0x180007dcc  mov     rdx, r14; int
0x180007dcf  call    ?LogIfAccessDenied@Deployment@Common@@YAJJPEBG@Z; Common::Deployment::LogIfAccessDenied(long,ushort const *)
0x180007dd4  mov     ebx, eax
0x180007dd6  mov     rcx, [rbp+1D8h]; this
0x180007ddd  test    eax, eax
0x180007ddf  jns     short loc_180007DFA
0x180007de1  mov     edx, 11Eh; void *
0x180007de6  lea     r8, aOnecoreAdminAp_133; "onecore\\admin\\appmodel\\common\\mrthe"...
0x180007ded  mov     r9d, eax; char *
0x180007df0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007df5  jmp     loc_180007FC6
0x180007dfa  cmp     [r12], r13b
0x180007dfe  jz      loc_180007FC6
0x180007e04  lea     rdi, [rsi+8]
0x180007e08  mov     rcx, rdi
0x180007e0b  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180007e10  mov     qword ptr [rsp+2D0h+ppv], rdi; int
0x180007e15  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180007e1c  xor     edx, edx; pUnkOuter
0x180007e1e  lea     r8d, [rdx+1]; dwClsContext
0x180007e22  lea     rcx, CLSID_MrtResourceManager; rclsid
0x180007e29  call    cs:__imp_CoCreateInstance
0x180007e30  nop     dword ptr [rax+rax+00h]
0x180007e35  mov     ebx, eax
0x180007e37  mov     rcx, [rbp+1D8h]
0x180007e3e  test    eax, eax
0x180007e40  jns     short loc_180007E49
0x180007e42  mov     edx, 122h
0x180007e47  jmp     short loc_180007DE6
0x180007e49  mov     [rsp+2D0h+TokenHandle], r13
0x180007e4e  mov     rdi, [rdi]
0x180007e51  mov     rax, [rdi]
  ... truncated ...
```
