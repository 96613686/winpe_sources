# CRegistryPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x1800322a0`
- end: `0x1800328ac`
- name: `?GetValue@CRegistryPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `1548`
- prototype: `__int64 __fastcall(CRegistryPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ceb0`
- `0x180010da8`
- `0x18001f2b0`
- `0x180022de4`
- `0x180026500`
- `0x180026fcc`
- `0x1800322a0`
- `0x1800328b4`
- `0x180033444`
- `0x180033464`
- `0x18003e920`
- `0x18003f7a4`
- `0x180062618`
- `0x18006262c`
- `0x1800628c8`
- `0x180063068`
- `0x18006322c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003246e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032527`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800325d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032651`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032766`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003246e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032527`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800325d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032651`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032766`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800323c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800323c0`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800327c3`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800327c3`
- `api-ms-win-core-localization-private-l1-1-0!LoadStringByReference` at `0x1800327fc`
- `api-ms-win-core-localization-private-l1-1-0!LoadStringByReference` at `0x1800327fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032868`

## string_xrefs

- `0x180032334`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x18003236a`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x18003248d`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800324f3`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x18003258a`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800325ea`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032667`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800326a6`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032713`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180032780`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x18003280d`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CRegistryPropertyStore::GetValue(
        CRegistryPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  unsigned __int64 v9; // r8
  HRESULT v10; // esi
  unsigned __int64 v11; // r9
  int v12; // eax
  HKEY v13; // rcx
  LSTATUS v14; // eax
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rdx
  HKEY v18; // rcx
  unsigned int v19; // eax
  void *v20; // rcx
  __int64 v21; // rdx
  PVOID v22; // rcx
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int inited; // eax
  PVOID v26; // rcx
  unsigned int ValueW; // eax
  void *v28; // rsi
  unsigned int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  unsigned __int64 v32; // r9
  unsigned int v33; // eax
  HRESULT LastError; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  const char *v37; // r9
  int v38; // eax
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatab; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatac; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v45[4]; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v48[16]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  PVOID *p_pvData; // [rsp+70h] [rbp-90h] BYREF
  void *v51; // [rsp+78h] [rbp-88h] BYREF
  char v52; // [rsp+80h] [rbp-80h]
  _BYTE v53[24]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  ATL::CCritSecLock::CCritSecLock(
    (ATL::CCritSecLock *)v53,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16),
    (bool)a3);
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 1022;
LABEL_8:
    v11 = (unsigned int)v6;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)v11,
      lpData);
    goto LABEL_78;
  }
  v45[0] = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v8 = (*(__int64 (__fastcall **)(CRegistryPropertyStore *, _BYTE *))(*(_QWORD *)this + 80LL))(this, v45);
  v10 = v8;
  if ( v8 >= 0 )
  {
    if ( !v45[0] )
    {
      v6 = -2147024894;
      v7 = 1027;
      goto LABEL_8;
    }
    v12 = KeyRep(a2, ValueName, v9);
    v6 = v12;
    if ( v12 < 0 )
    {
      v11 = (unsigned int)v12;
      v7 = 1031;
      goto LABEL_9;
    }
    v13 = (HKEY)*((_QWORD *)this + 1);
    Type = 0;
    cbData = 0;
    v14 = RegQueryValueExW(v13, ValueName, 0, &Type, 0, &cbData);
    if ( v14 && v14 != 234 )
    {
      a3->vt = 0;
      if ( v14 == 5 )
      {
        v6 = -2147024891;
        v7 = 1041;
        goto LABEL_8;
      }
LABEL_77:
      v6 = 0;
      goto LABEL_78;
    }
    v15 = lambda_fddb834c1d6a90001df23262bd46f9fd_::_lambda_fddb834c1d6a90001df23262bd46f9fd_(&pvData, a2);
    wil::scope_exit__lambda_fddb834c1d6a90001df23262bd46f9fd___(v48, v15);
    v16 = (void *)(Type - 1);
    if ( Type != 1 )
    {
      v16 = (void *)(Type - 2);
      if ( Type != 2 )
      {
        if ( Type != 3 )
        {
          if ( Type == 4 )
          {
            if ( cbData != 4 )
            {
              v6 = -2147023267;
              v17 = 1060;
              goto LABEL_38;
            }
            ValueW = RegGetValueW(*((HKEY *)this + 1), 0, ValueName, 0x10u, 0, &a3->decVal.8, &cbData);
            if ( ValueW != 2 )
            {
              if ( ValueW )
              {
                v6 = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x428,
                       (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                       (const char *)ValueW,
                       lpDatab);
                goto LABEL_39;
              }
              a3->vt = 19;
            }
            goto LABEL_76;
          }
          if ( Type != 7 )
          {
            v6 = -2147023266;
            v17 = 1169;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
              (const char *)(unsigned int)v6,
              lpData);
LABEL_39:
            wil::details::lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd___::_lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd___(v48);
            goto LABEL_78;
          }
          v18 = (HKEY)*((_QWORD *)this + 1);
          pvData = 0;
          v19 = RegGetValueW(v18, 0, ValueName, 0x20u, 0, 0, &cbData);
          if ( v19 != 2 )
          {
            if ( v19 )
            {
              v21 = 1129;
LABEL_25:
              v6 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v21,
                     (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                     (const char *)v19,
                     lpDataa);
LABEL_26:
              v22 = pvData;
              pvData = 0;
              goto LABEL_58;
            }
            p_pvData = &pvData;
            v51 = 0;
            v52 = 1;
            v6 = CTCoAllocPolicy::Alloc(v20, 1u, cbData, &v51);
            wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pvData);
            if ( v6 < 0 )
            {
              v23 = (unsigned int)v6;
              v24 = 1132;
LABEL_29:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v24,
                (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                (const char *)v23,
                lpDataa);
              goto LABEL_26;
            }
            v19 = RegGetValueW(*((HKEY *)this + 1), 0, ValueName, 0x20u, 0, pvData, &cbData);
            if ( v19 != 2 )
            {
              if ( v19 )
              {
                v21 = 1138;
                goto LABEL_25;
              }
              inited = InitPropVariantFromStringAsVector((unsigned __int16 *)pvData, cbData >> 1, a3);
              v6 = inited;
              if ( inited < 0 )
              {
                v23 = (unsigned int)inited;
                v24 = 1140;
                goto LABEL_29;
              }
            }
          }
          v26 = pvData;
          pvData = 0;
LABEL_74:
          if ( v26 )
            goto LABEL_75;
LABEL_76:
          v48[8] = 0;
          wil::details::lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd___::_lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd___(v48);
          goto LABEL_77;
        }
        v28 = CoTaskMemAlloc(cbData);
        if ( !v28 )
        {
          v6 = -2147024882;
          v17 = 1152;
          goto LABEL_38;
        }
        v29 = RegGetValueW(*((HKEY *)this + 1), 0, ValueName, 8u, 0, v28, &cbData);
        if ( v29 != 2 )
        {
          if ( v29 )
          {
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x486,
                   (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                   (const char *)v29,
                   lpDatac);
LABEL_49:
            v22 = v28;
            goto LABEL_59;
          }
          v30 = DeserializePropVariant(Type, (unsigned __int8 *)v28, cbData, a3);
          v6 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x488,
              (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
              (const char *)(unsigned int)v30,
              lpDatac);
            goto LABEL_49;
          }
        }
        v26 = v28;
LABEL_75:
        CoTaskMemFree(v26);
        goto LABEL_76;
      }
    }
    pv = 0;
    p_pvData = &pv;
    v51 = 0;
    v52 = 1;
    v6 = CTCoAllocPolicy::Alloc(v16, 1u, cbData + 2LL, &v51);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pvData);
    if ( v6 < 0 )
    {
      v31 = 1078;
LABEL_55:
      v32 = (unsigned int)v6;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)v32,
        lpData);
LABEL_57:
      v22 = pv;
      pv = 0;
LABEL_58:
      if ( !v22 )
        goto LABEL_39;
LABEL_59:
      CoTaskMemFree(v22);
      goto LABEL_39;
    }
    v33 = RegGetValueW(*((HKEY *)this + 1), 0, ValueName, 6u, 0, pv, &cbData);
    if ( v33 == 2 )
    {
LABEL_73:
      v26 = pv;
      pv = 0;
      goto LABEL_74;
    }
    if ( v33 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x43C,
                    (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                    (const char *)v33,
                    lpData);
LABEL_63:
      v6 = LastError;
      goto LABEL_57;
    }
    memset_0(pszOutBuf, 0, 0x208u);
    v6 = SHLoadIndirectString((PCWSTR)pv, pszOutBuf, 0x104u, 0);
    if ( v6 == -2147467259 )
    {
      if ( GetLastError() == 5 )
      {
        if ( !LoadStringByReference(8u, 0, (PCWSTR)pv, pszOutBuf, 0x104u, 0, 0) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x44A,
                        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                        v37);
          goto LABEL_63;
        }
        goto LABEL_70;
      }
    }
    else if ( v6 >= 0 )
    {
LABEL_70:
      v38 = _AllocString<CTCoAllocPolicy>(v36, v35, pszOutBuf, &a3->decVal.Lo32);
      v6 = v38;
      if ( v38 < 0 )
      {
        v32 = (unsigned int)v38;
        v31 = 1104;
        goto LABEL_56;
      }
      a3->vt = 31;
      goto LABEL_73;
    }
    v31 = 1101;
    goto LABEL_55;
  }
  v6 = -2147024891;
  if ( v8 != -2147024891 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x402,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)(unsigned int)v8,
      lpData);
    v6 = v10;
  }
LABEL_78:
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v53);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800322a0  push    rbp
0x1800322a2  push    rbx
0x1800322a3  push    rsi
0x1800322a4  push    rdi
0x1800322a5  push    r12
0x1800322a7  push    r14
0x1800322a9  push    r15
0x1800322ab  lea     rbp, [rsp-2C0h]
0x1800322b3  sub     rsp, 3C0h
0x1800322ba  mov     rax, cs:__security_cookie
0x1800322c1  xor     rax, rsp
0x1800322c4  mov     [rbp+2F0h+var_40], rax
0x1800322cb  mov     r15, rdx
0x1800322ce  mov     r14, rcx
0x1800322d1  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x1800322d5  mov     rdi, r8
0x1800322d8  lea     rcx, [rbp+2F0h+var_368]; this
0x1800322dc  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800322e1  xor     r12d, r12d
0x1800322e4  test    rdi, rdi
0x1800322e7  jnz     short loc_1800322F5
0x1800322e9  mov     ebx, 80004003h
0x1800322ee  mov     edx, 3FEh
0x1800322f3  jmp     short loc_180032360
0x1800322f5  xor     eax, eax
0x1800322f7  mov     [rsp+3F0h+var_3AC], r12b
0x1800322fc  xorps   xmm0, xmm0
0x1800322ff  lea     rdx, [rsp+3F0h+var_3AC]
0x180032304  movups  xmmword ptr [rdi], xmm0
0x180032307  mov     [rdi+10h], rax
0x18003230b  mov     rcx, r14
0x18003230e  mov     rax, [r14]
0x180032311  mov     rax, [rax+50h]
0x180032315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003231a  mov     esi, eax
0x18003231c  test    eax, eax
0x18003231e  jns     short loc_18003234F
0x180032320  mov     ebx, 80070005h
0x180032325  cmp     eax, ebx
0x180032327  jz      loc_180032880
0x18003232d  mov     rcx, [rbp+2F8h]; this
0x180032334  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x18003233b  mov     r9d, eax; char *
0x18003233e  mov     edx, 402h; void *
0x180032343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032348  mov     ebx, esi
0x18003234a  jmp     loc_180032880
0x18003234f  cmp     [rsp+3F0h+var_3AC], r12b
0x180032354  jnz     short loc_18003237B
0x180032356  mov     ebx, 80070002h
0x18003235b  mov     edx, 403h; void *
0x180032360  mov     r9d, ebx; char *
0x180032363  mov     rcx, [rbp+2F8h]; this
0x18003236a  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032376  jmp     loc_180032880
0x18003237b  lea     rdx, [rbp+2F0h+ValueName]; unsigned __int16 *
0x18003237f  mov     rcx, r15; struct _tagpropertykey *
0x180032382  call    ?KeyRep@@YAJAEBU_tagpropertykey@@PEAG_K@Z; KeyRep(_tagpropertykey const &,ushort *,unsigned __int64)
0x180032387  mov     ebx, eax
0x180032389  test    eax, eax
0x18003238b  jns     short loc_180032397
0x18003238d  mov     r9d, eax
0x180032390  mov     edx, 407h
0x180032395  jmp     short loc_180032363
0x180032397  mov     rcx, [r14+8]; hKey
0x18003239b  lea     rax, [rsp+3F0h+cbData]
0x1800323a0  mov     [rsp+3F0h+lpcbData], rax; lpcbData
0x1800323a5  lea     r9, [rsp+3F0h+Type]; lpType
0x1800323aa  xor     r8d, r8d; lpReserved
0x1800323ad  mov     [rsp+3F0h+lpData], r12; int
0x1800323b2  lea     rdx, [rbp+2F0h+ValueName]; lpValueName
0x1800323b6  mov     [rsp+3F0h+Type], r12d
0x1800323bb  mov     [rsp+3F0h+cbData], r12d
0x1800323c0  call    cs:__imp_RegQueryValueExW
0x1800323c6  test    eax, eax
0x1800323c8  jz      short loc_1800323ED
0x1800323ca  cmp     eax, 0EAh
0x1800323cf  jz      short loc_1800323ED
0x1800323d1  mov     [rdi], r12w
0x1800323d5  cmp     eax, 5
0x1800323d8  jnz     loc_18003287D
0x1800323de  mov     ebx, 80070005h
0x1800323e3  mov     edx, 411h
0x1800323e8  jmp     loc_180032360
0x1800323ed  mov     rdx, r15
0x1800323f0  lea     rcx, [rsp+3F0h+pvData]
0x1800323f5  call    _lambda_fddb834c1d6a90001df23262bd46f9fd____lambda_fddb834c1d6a90001df23262bd46f9fd_
0x1800323fa  mov     rdx, rax
0x1800323fd  lea     rcx, [rsp+3F0h+var_398]
0x180032402  call    wil__scope_exit__lambda_fddb834c1d6a90001df23262bd46f9fd___
0x180032407  mov     ecx, [rsp+3F0h+Type]
0x18003240b  sub     ecx, 1; void *
0x18003240e  jz      loc_1800326C4
0x180032414  sub     ecx, 1
0x180032417  jz      loc_1800326C4
0x18003241d  sub     ecx, 1
0x180032420  jz      loc_18003260C
0x180032426  sub     ecx, 1
0x180032429  jz      loc_180032572
0x18003242f  cmp     ecx, 3
0x180032432  jz      short loc_180032443
0x180032434  mov     ebx, 8007065Eh
0x180032439  mov     edx, 491h
0x18003243e  jmp     loc_180032583
0x180032443  mov     rcx, [r14+8]; hkey
0x180032447  lea     rax, [rsp+3F0h+cbData]
0x18003244c  mov     [rsp+3F0h+pcbData], rax; pcbData
0x180032451  lea     r8, [rbp+2F0h+ValueName]; lpValue
0x180032455  mov     esi, 20h ; ' '
0x18003245a  mov     [rsp+3F0h+lpcbData], r12; pvData
0x18003245f  mov     r9d, esi; dwFlags
0x180032462  mov     [rsp+3F0h+lpData], r12; int
0x180032467  xor     edx, edx; lpSubKey
0x180032469  mov     [rsp+3F0h+pvData], r12
0x18003246e  call    cs:__imp_RegGetValueW
0x180032474  cmp     eax, 2
0x180032477  jz      loc_180032563
0x18003247d  test    eax, eax
0x18003247f  jz      short loc_1800324AD
0x180032481  mov     edx, 469h; void *
0x180032486  mov     rcx, [rbp+2F8h]; this
0x18003248d  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032494  mov     r9d, eax; char *
0x180032497  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003249c  mov     ebx, eax
0x18003249e  mov     rcx, [rsp+3F0h+pvData]
0x1800324a3  mov     [rsp+3F0h+pvData], r12
0x1800324a8  jmp     loc_180032729
0x1800324ad  mov     r8d, [rsp+3F0h+cbData]; unsigned __int64
0x1800324b2  lea     rax, [rsp+3F0h+pvData]
0x1800324b7  lea     r9, [rsp+3F0h+var_378]; void **
0x1800324bc  mov     [rsp+3F0h+var_380], rax
0x1800324c1  mov     edx, 1; unsigned int
0x1800324c6  mov     [rsp+3F0h+var_378], r12
0x1800324cb  mov     [rbp+2F0h+var_370], 1
0x1800324cf  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800324d4  lea     rcx, [rsp+3F0h+var_380]
0x1800324d9  mov     ebx, eax
0x1800324db  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800324e0  test    ebx, ebx
0x1800324e2  jns     short loc_180032501
0x1800324e4  mov     r9d, ebx; char *
0x1800324e7  mov     edx, 46Ch; void *
0x1800324ec  mov     rcx, [rbp+2F8h]; this
0x1800324f3  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800324fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324ff  jmp     short loc_18003249E
0x180032501  mov     rax, [rsp+3F0h+pvData]
0x180032506  lea     rcx, [rsp+3F0h+cbData]
0x18003250b  mov     [rsp+3F0h+pcbData], rcx; pcbData
0x180032510  lea     r8, [rbp+2F0h+ValueName]; lpValue
0x180032514  mov     rcx, [r14+8]; hkey
0x180032518  mov     r9d, esi; dwFlags
0x18003251b  mov     [rsp+3F0h+lpcbData], rax; pvData
0x180032520  xor     edx, edx; lpSubKey
0x180032522  mov     [rsp+3F0h+lpData], r12; pdwType
0x180032527  call    cs:__imp_RegGetValueW
0x18003252d  cmp     eax, 2
0x180032530  jz      short loc_180032563
0x180032532  test    eax, eax
0x180032534  jz      short loc_180032540
0x180032536  mov     edx, 472h
0x18003253b  jmp     loc_180032486
0x180032540  mov     edx, [rsp+3F0h+cbData]
0x180032544  mov     r8, rdi; struct tagPROPVARIANT *
0x180032547  mov     rcx, [rsp+3F0h+pvData]; unsigned __int16 *
0x18003254c  shr     edx, 1; unsigned int
0x18003254e  call    ?InitPropVariantFromStringAsVector@@YAJPEAGIPEAUtagPROPVARIANT@@@Z; InitPropVariantFromStringAsVector(ushort *,uint,tagPROPVARIANT *)
0x180032553  mov     ebx, eax
0x180032555  test    eax, eax
0x180032557  jns     short loc_180032563
0x180032559  mov     r9d, eax
0x18003255c  mov     edx, 474h
0x180032561  jmp     short loc_1800324EC
0x180032563  mov     rcx, [rsp+3F0h+pvData]
0x180032568  mov     [rsp+3F0h+pvData], r12
0x18003256d  jmp     loc_180032863
0x180032572  cmp     [rsp+3F0h+cbData], 4
0x180032577  jz      short loc_1800325A8
0x180032579  mov     ebx, 8007065Dh
0x18003257e  mov     edx, 424h; void *
0x180032583  mov     rcx, [rbp+2F8h]; this
0x18003258a  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032591  mov     r9d, ebx; char *
0x180032594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032599  lea     rcx, [rsp+3F0h+var_398]
0x18003259e  call    wil__details__lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd______lambda_call__lambda_fddb834c1d6a90001df23262bd46f9fd___
0x1800325a3  jmp     loc_180032880
0x1800325a8  lea     rcx, [rsp+3F0h+cbData]
0x1800325ad  mov     r9d, 10h; dwFlags
0x1800325b3  mov     [rsp+3F0h+pcbData], rcx; pcbData
0x1800325b8  lea     rax, [rdi+8]
0x1800325bc  mov     rcx, [r14+8]; hkey
0x1800325c0  lea     r8, [rbp+2F0h+ValueName]; lpValue
0x1800325c4  mov     [rsp+3F0h+lpcbData], rax; pvData
0x1800325c9  xor     edx, edx; lpSubKey
0x1800325cb  mov     [rsp+3F0h+lpData], r12; unsigned int
0x1800325d0  call    cs:__imp_RegGetValueW
0x1800325d6  cmp     eax, 2
0x1800325d9  jz      loc_18003286E
0x1800325df  test    eax, eax
0x1800325e1  jz      short loc_180032602
0x1800325e3  mov     rcx, [rbp+2F8h]; this
0x1800325ea  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800325f1  mov     r9d, eax; char *
0x1800325f4  mov     edx, 428h; void *
0x1800325f9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800325fe  mov     ebx, eax
0x180032600  jmp     short loc_180032599
0x180032602  mov     word ptr [rdi], 13h
0x180032607  jmp     loc_18003286E
0x18003260c  mov     ecx, [rsp+3F0h+cbData]; cb
0x180032610  call    cs:__imp_CoTaskMemAlloc
0x180032616  mov     rsi, rax
0x180032619  test    rax, rax
0x18003261c  jnz     short loc_18003262D
0x18003261e  mov     ebx, 8007000Eh
0x180032623  mov     edx, 480h
0x180032628  jmp     loc_180032583
0x18003262d  mov     rcx, [r14+8]; hkey
0x180032631  lea     rax, [rsp+3F0h+cbData]
0x180032636  mov     [rsp+3F0h+pcbData], rax; pcbData
0x18003263b  lea     r8, [rbp+2F0h+ValueName]; lpValue
0x18003263f  mov     [rsp+3F0h+lpcbData], rsi; pvData
0x180032644  mov     r9d, 8; dwFlags
0x18003264a  xor     edx, edx; lpSubKey
0x18003264c  mov     [rsp+3F0h+lpData], r12; int
0x180032651  call    cs:__imp_RegGetValueW
0x180032657  cmp     eax, 2
0x18003265a  jz      short loc_1800326BC
0x18003265c  test    eax, eax
0x18003265e  jz      short loc_180032685
0x180032660  mov     rcx, [rbp+2F8h]; this
0x180032667  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x18003266e  mov     r9d, eax; char *
0x180032671  mov     edx, 486h; void *
0x180032676  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003267b  mov     ebx, eax
0x18003267d  mov     rcx, rsi
0x180032680  jmp     loc_180032732
0x180032685  mov     r8d, [rsp+3F0h+cbData]; unsigned __int64
0x18003268a  mov     r9, rdi; struct tagPROPVARIANT *
0x18003268d  mov     ecx, [rsp+3F0h+Type]; unsigned int
0x180032691  mov     rdx, rsi; unsigned __int8 *
0x180032694  call    ?DeserializePropVariant@@YAJKPEAE_KPEAUtagPROPVARIANT@@@Z; DeserializePropVariant(ulong,uchar *,unsigned __int64,tagPROPVARIANT *)
0x180032699  mov     ebx, eax
0x18003269b  test    eax, eax
0x18003269d  jns     short loc_1800326BC
0x18003269f  mov     rcx, [rbp+2F8h]; this
0x1800326a6  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800326ad  mov     r9d, eax; char *
0x1800326b0  mov     edx, 488h; void *
0x1800326b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326ba  jmp     short loc_18003267D
0x1800326bc  mov     rcx, rsi
0x1800326bf  jmp     loc_180032868
0x1800326c4  mov     r8d, [rsp+3F0h+cbData]
0x1800326c9  lea     rax, [rsp+3F0h+pv]
0x1800326ce  add     r8, 2; unsigned __int64
0x1800326d2  mov     [rsp+3F0h+pv], r12
0x1800326d7  lea     r9, [rsp+3F0h+var_378]; void **
0x1800326dc  mov     [rsp+3F0h+var_380], rax
0x1800326e1  mov     edx, 1; unsigned int
0x1800326e6  mov     [rsp+3F0h+var_378], r12
0x1800326eb  mov     [rbp+2F0h+var_370], 1
0x1800326ef  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800326f4  lea     rcx, [rsp+3F0h+var_380]
0x1800326f9  mov     ebx, eax
0x1800326fb  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180032700  test    ebx, ebx
0x180032702  jns     short loc_18003273D
0x180032704  mov     edx, 436h; void *
0x180032709  mov     r9d, ebx; char *
0x18003270c  mov     rcx, [rbp+2F8h]; this
0x180032713  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x18003271a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003271f  mov     rcx, [rsp+3F0h+pv]; pv
0x180032724  mov     [rsp+3F0h+pv], r12
0x180032729  test    rcx, rcx
0x18003272c  jz      loc_180032599
0x180032732  call    cs:__imp_CoTaskMemFree
0x180032738  jmp     loc_180032599
0x18003273d  mov     rax, [rsp+3F0h+pv]
0x180032742  lea     rcx, [rsp+3F0h+cbData]
0x180032747  mov     [rsp+3F0h+pcbData], rcx; pcbData
0x18003274c  lea     r8, [rbp+2F0h+ValueName]; lpValue
0x180032750  mov     rcx, [r14+8]; hkey
0x180032754  mov     r9d, 6; dwFlags
0x18003275a  mov     [rsp+3F0h+lpcbData], rax; pvData
0x18003275f  xor     edx, edx; lpSubKey
0x180032761  mov     [rsp+3F0h+lpData], r12; unsigned int
0x180032766  call    cs:__imp_RegGetValueW
0x18003276c  cmp     eax, 2
0x18003276f  jz      loc_180032859
0x180032775  test    eax, eax
0x180032777  jz      short loc_180032798
0x180032779  mov     rcx, [rbp+2F8h]; this
0x180032780  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180032787  mov     r9d, eax; char *
  ... truncated ...
```
