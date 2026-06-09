# OSIntegration::DEH::CapabilityAuthorizationHandler::ParseCapabilityCategoryFromManifest(OSIntegration::Package const *,APPX_CAPABILITY_CLASS_TYPE,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180013c10`
- end: `0x180014236`
- name: `?ParseCapabilityCategoryFromManifest@CapabilityAuthorizationHandler@DEH@OSIntegration@@AEBAJPEBVPackage@3@W4APPX_CAPABILITY_CLASS_TYPE@@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `1574`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801321e0`

## callees

- `0x18000b3bc`
- `0x18000e6e0`
- `0x1800138e0`
- `0x180013c10`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0700`
- `0x1800f073c`
- `0x1800fc229`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ddf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001420d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001420d`

## string_xrefs

- `0x1800141d5`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::CapabilityAuthorizationHandler::ParseCapabilityCategoryFromManifest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, LPVOID *); // rbx
  int v18; // eax
  __int64 v19; // r10
  _WORD *v20; // rax
  WCHAR *v21; // rbx
  unsigned __int64 i; // rdi
  int v23; // eax
  unsigned __int64 v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rcx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  void *v34; // rax
  void *v35; // r14
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rcx
  unsigned __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-40h]
  __int64 v55; // [rsp+30h] [rbp-30h] BYREF
  __int64 v56; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  LPCWCH lpString1[2]; // [rsp+48h] [rbp-18h] BYREF
  int v59; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v61; // [rsp+90h] [rbp+30h] BYREF
  int v62; // [rsp+94h] [rbp+34h]
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp+38h] BYREF

  v62 = HIDWORD(a1);
  v61 = 0;
  v63 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v7 = 0;
  v63 = 0;
  v8 = *(_QWORD *)(a2 + 40);
  if ( v8 )
  {
    v63 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a2 + 40);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v7 = v63;
  }
  v56 = 0;
  v9 = **v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  v10 = v9(v7, &GUID_c43825ab_69b7_400a_9709_cc37f5a72d24, &v56);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    v48 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
    if ( v63 )
    {
      v63 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v49)[2])(v49);
    }
    return v11;
  }
  v55 = 0;
  v12 = v56;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v14 = v13(v12, a3, &v55);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    v45 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
    if ( v63 )
    {
      v63 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
    }
    return v11;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 32LL))(v55, &v61);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
      (const char *)(unsigned int)v15,
      bIgnoreCase);
    goto LABEL_87;
  }
  while ( 1 )
  {
    if ( !v61 )
    {
      v30 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
      if ( v63 )
      {
        v63 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
      }
      return 0;
    }
    pv = 0;
    v16 = v55;
    v17 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v55 + 24LL);
    CoTaskMemFree(0);
    pv = 0;
    v18 = v17(v16, &pv);
    v11 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
      CoTaskMemFree(pv);
      v50 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      v51 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
      v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
      if ( v63 )
      {
        v63 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
      }
      return v11;
    }
    *(_OWORD *)lpString1 = 0;
    v59 = 0;
    if ( !pv )
    {
      LODWORD(lpString1[0]) = 0;
      goto LABEL_14;
    }
    v19 = 1073741822;
    v20 = pv;
    do
    {
      if ( !*v20 )
        break;
      ++v20;
      --v19;
    }
    while ( v19 );
    v11 = v19 == 0 ? 0x80070057 : 0;
    if ( !v19 )
      break;
    v11 = Common::StringBuffer::SetValue(
            (Common::StringBuffer *)lpString1,
            (const unsigned __int16 *)pv,
            v19 != 0 ? 1073741822 - v19 : 0);
    if ( (v11 & 0x80000000) != 0 )
      goto LABEL_86;
LABEL_14:
    v21 = (WCHAR *)lpString1[1];
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_QWORD *)(a4 + 16) )
        goto LABEL_23;
      if ( CompareStringOrdinal(v21, -1, *(LPCWCH *)(*(_QWORD *)a4 + 8 * i), -1, 1) == 2 )
        break;
    }
    if ( i == 0x40000000 )
    {
LABEL_23:
      v26 = *(_QWORD *)(a4 + 16);
      v27 = v26 + 1;
      v28 = *(_QWORD *)(a4 + 8);
      if ( v26 + 1 > v28 )
      {
        if ( v28 == 0x3FFFFFFF )
        {
          v25 = -2147483637;
          goto LABEL_45;
        }
        if ( v28 )
          v29 = ((3 * v28) >> 1) + 1;
        else
          v29 = 16;
        if ( v27 <= v29 )
          v27 = v29;
        if ( v27 > 0x3FFFFFFF )
          v27 = 0x3FFFFFFF;
        v34 = operator new[](8 * v27, (const struct std::nothrow_t *)std::nothrow);
        v35 = v34;
        if ( !v34 )
        {
          v25 = -2147024882;
LABEL_45:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B8,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
            (const char *)v25,
            bIgnoreCase);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
            (const char *)v25,
            bIgnoreCasea);
          if ( v21 )
            operator delete(v21, v37);
          CoTaskMemFree(pv);
          v38 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          v39 = v56;
          if ( v56 )
          {
            v56 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          }
          v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
          if ( v63 )
          {
            v63 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v40)[2])(v40);
          }
          return v25;
        }
        if ( *(_QWORD *)a4 )
        {
          memmove_0(v34, *(const void **)a4, 8LL * *(_QWORD *)(a4 + 16));
          operator delete(*(void **)a4, v36);
        }
        *(_QWORD *)a4 = v35;
        *(_QWORD *)(a4 + 8) = v27;
        v26 = *(_QWORD *)(a4 + 16);
      }
      *(_QWORD *)(*(_QWORD *)a4 + 8 * v26) = v21;
      ++*(_QWORD *)(a4 + 16);
      v21 = 0;
      lpString1[1] = 0;
      LODWORD(lpString1[0]) = 0;
      v59 = 0;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 40LL))(v55, &v61);
    v25 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCase);
      if ( v21 )
        operator delete(v21, v41);
      CoTaskMemFree(pv);
      v42 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
      if ( v63 )
      {
        v63 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v44)[2])(v44);
      }
      return v25;
    }
    if ( v21 )
      operator delete(v21, v24);
    CoTaskMemFree(pv);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x249,
    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
    (const char *)v11,
    bIgnoreCase);
LABEL_86:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F1,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
    (const char *)v11,
    bIgnoreCase);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
  CoTaskMemFree(pv);
LABEL_87:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  return v11;
}

```

## disassembly

```asm
0x180013c10  mov     [rsp-28h+arg_10], rbx
0x180013c15  mov     [rsp-28h+arg_18], rsi
0x180013c1a  mov     [rsp-28h+arg_0], rcx
0x180013c1f  push    rbp
0x180013c20  push    rdi
0x180013c21  push    r13
0x180013c23  push    r14
0x180013c25  push    r15
0x180013c27  mov     rbp, rsp
0x180013c2a  sub     rsp, 60h
0x180013c2e  mov     rsi, r9
0x180013c31  mov     r14d, r8d
0x180013c34  mov     rdi, rdx
0x180013c37  xor     r15d, r15d
0x180013c3a  mov     dword ptr [rbp+arg_0], r15d
0x180013c3e  mov     [rbp+arg_8], r15
0x180013c42  lea     rcx, [rbp+arg_8]
0x180013c46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013c4b  mov     ebx, r15d
0x180013c4e  mov     [rbp+arg_8], rbx
0x180013c52  mov     rcx, [rdi+28h]
0x180013c56  test    rcx, rcx
0x180013c59  jz      short loc_180013C6F
0x180013c5b  mov     [rbp+arg_8], rcx
0x180013c5f  mov     rax, [rcx]
0x180013c62  mov     rax, [rax+8]
0x180013c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6b  mov     rbx, [rbp+arg_8]
0x180013c6f  mov     [rbp+var_28], r15
0x180013c73  mov     rax, [rbx]
0x180013c76  mov     rdi, [rax]
0x180013c79  lea     rcx, [rbp+var_28]
0x180013c7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013c82  lea     r8, [rbp+var_28]
0x180013c86  lea     rdx, _GUID_c43825ab_69b7_400a_9709_cc37f5a72d24
0x180013c8d  mov     rcx, rbx
0x180013c90  mov     rax, rdi
0x180013c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c98  mov     ebx, eax
0x180013c9a  test    eax, eax
0x180013c9c  js      loc_1800140E9
0x180013ca2  mov     [rbp+var_30], r15
0x180013ca6  mov     rdi, [rbp+var_28]
0x180013caa  mov     rax, [rdi]
0x180013cad  mov     rbx, [rax+68h]
0x180013cb1  lea     rcx, [rbp+var_30]
0x180013cb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013cba  lea     r8, [rbp+var_30]
0x180013cbe  mov     edx, r14d
0x180013cc1  mov     rcx, rdi
0x180013cc4  mov     rax, rbx
0x180013cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ccc  mov     ebx, eax
0x180013cce  test    eax, eax
0x180013cd0  js      loc_18001407B
0x180013cd6  mov     rcx, [rbp+var_30]
0x180013cda  mov     rax, [rcx]
0x180013cdd  lea     rdx, [rbp+arg_0]
0x180013ce1  mov     rax, [rax+20h]
0x180013ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cea  mov     ebx, eax
0x180013cec  test    eax, eax
0x180013cee  js      loc_1800141B8
0x180013cf4  mov     r13d, 3FFFFFFFh
0x180013cfa  cmp     dword ptr [rbp+arg_0], r15d
0x180013cfe  jz      loc_180013E62
0x180013d04  mov     [rbp+pv], r15
0x180013d08  mov     rdi, [rbp+var_30]
0x180013d0c  mov     rax, [rdi]
0x180013d0f  mov     rbx, [rax+18h]
0x180013d13  xor     ecx, ecx; pv
0x180013d15  call    cs:__imp_CoTaskMemFree
0x180013d1b  mov     [rbp+pv], r15
0x180013d1f  lea     rdx, [rbp+pv]
0x180013d23  mov     rcx, rdi
0x180013d26  mov     rax, rbx
0x180013d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d2e  mov     ebx, eax
0x180013d30  test    eax, eax
0x180013d32  js      loc_180014138
0x180013d38  xorps   xmm0, xmm0
0x180013d3b  movups  xmmword ptr [rbp+lpString1], xmm0
0x180013d3f  mov     [rbp+var_8], r15d
0x180013d43  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180013d47  test    rdx, rdx
0x180013d4a  jz      loc_1800141AF
0x180013d50  mov     r10d, 3FFFFFFEh
0x180013d56  mov     rax, rdx
0x180013d59  cmp     [rax], r15w
0x180013d5d  jz      short loc_180013D69
0x180013d5f  add     rax, 2
0x180013d63  sub     r10, 1
0x180013d67  jnz     short loc_180013D59
0x180013d69  mov     rax, r10
0x180013d6c  neg     rax
0x180013d6f  sbb     ebx, ebx
0x180013d71  not     ebx
0x180013d73  and     ebx, 80070057h
0x180013d79  mov     r8, r10
0x180013d7c  mov     rax, r10
0x180013d7f  mov     ecx, 3FFFFFFEh
0x180013d84  sub     rcx, r10
0x180013d87  neg     rax
0x180013d8a  sbb     r9, r9
0x180013d8d  and     r9, rcx
0x180013d90  neg     r8
0x180013d93  sbb     r8, r8
0x180013d96  and     r8, r9; unsigned int
0x180013d99  mov     rcx, [rbp+28h]; this
0x180013d9d  test    r10, r10
0x180013da0  jz      loc_1800141D2
0x180013da6  lea     rcx, [rbp+lpString1]; this
0x180013daa  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180013daf  mov     ebx, eax
0x180013db1  test    eax, eax
0x180013db3  js      loc_1800141E6
0x180013db9  mov     rbx, [rbp+lpString1+8]
0x180013dbd  mov     rdi, r15
0x180013dc0  cmp     rdi, [rsi+10h]
0x180013dc4  jnb     short loc_180013E33
0x180013dc6  mov     r8, [rsi]
0x180013dc9  mov     [rsp+60h+bIgnoreCase], 1; int
0x180013dd1  or      r9d, 0FFFFFFFFh; cchCount2
0x180013dd5  mov     r8, [r8+rdi*8]; lpString2
0x180013dd9  or      edx, r9d; cchCount1
0x180013ddc  mov     rcx, rbx; lpString1
0x180013ddf  call    cs:__imp_CompareStringOrdinal
0x180013de5  add     eax, 0FFFFFFFEh
0x180013de8  jz      short loc_180013DEF
0x180013dea  inc     rdi
0x180013ded  jmp     short loc_180013DC0
0x180013def  cmp     rdi, 40000000h
0x180013df6  jz      short loc_180013E33
0x180013df8  mov     rcx, [rbp+var_30]
0x180013dfc  mov     rax, [rcx]
0x180013dff  lea     rdx, [rbp+arg_0]
0x180013e03  mov     rax, [rax+28h]
0x180013e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0c  mov     edi, eax
0x180013e0e  test    eax, eax
0x180013e10  js      loc_180013FEC
0x180013e16  test    rbx, rbx
0x180013e19  jz      short loc_180013E24
0x180013e1b  mov     rcx, rbx; void *
0x180013e1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013e23  nop
0x180013e24  mov     rcx, [rbp+pv]; pv
0x180013e28  call    cs:__imp_CoTaskMemFree
0x180013e2e  jmp     loc_180013CFA
0x180013e33  mov     rcx, [rsi+10h]
0x180013e37  lea     rdi, [rcx+1]
0x180013e3b  mov     rax, [rsi+8]
0x180013e3f  cmp     rdi, rax
0x180013e42  jbe     loc_180013F29
0x180013e48  cmp     rax, r13
0x180013e4b  jz      loc_180013F48
0x180013e51  test    rax, rax
0x180013e54  jz      short loc_180013ECB
0x180013e56  lea     rax, [rax+rax*2]
0x180013e5a  shr     rax, 1
0x180013e5d  inc     rax
0x180013e60  jmp     short loc_180013ED0
0x180013e62  mov     rcx, [rbp+var_30]
0x180013e66  test    rcx, rcx
0x180013e69  jz      short loc_180013E7C
0x180013e6b  mov     [rbp+var_30], r15
0x180013e6f  mov     rax, [rcx]
0x180013e72  mov     rax, [rax+10h]
0x180013e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7b  nop
0x180013e7c  mov     rcx, [rbp+var_28]
0x180013e80  test    rcx, rcx
0x180013e83  jz      short loc_180013E96
0x180013e85  mov     [rbp+var_28], r15
0x180013e89  mov     rax, [rcx]
0x180013e8c  mov     rax, [rax+10h]
0x180013e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e95  nop
0x180013e96  mov     rcx, [rbp+arg_8]
0x180013e9a  test    rcx, rcx
0x180013e9d  jz      short loc_180013EB0
0x180013e9f  mov     [rbp+arg_8], r15
0x180013ea3  mov     rax, [rcx]
0x180013ea6  mov     rax, [rax+10h]
0x180013eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eaf  nop
0x180013eb0  xor     eax, eax
0x180013eb2  lea     r11, [rsp+60h+var_s0]
0x180013eb7  mov     rbx, [r11+40h]
0x180013ebb  mov     rsi, [r11+48h]
0x180013ebf  mov     rsp, r11
0x180013ec2  pop     r15
0x180013ec4  pop     r14
0x180013ec6  pop     r13
0x180013ec8  pop     rdi
0x180013ec9  pop     rbp
0x180013eca  retn
0x180013ecb  mov     eax, 10h
0x180013ed0  cmp     rdi, rax
0x180013ed3  cmovbe  rdi, rax
0x180013ed7  cmp     rdi, r13
0x180013eda  cmova   rdi, r13
0x180013ede  lea     rcx, ds:0[rdi*8]; unsigned __int64
0x180013ee6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013eed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013ef2  mov     r14, rax
0x180013ef5  test    rax, rax
0x180013ef8  jz      loc_180014071
0x180013efe  mov     rdx, [rsi]; Src
0x180013f01  test    rdx, rdx
0x180013f04  jz      short loc_180013F1E
0x180013f06  mov     r8, [rsi+10h]
0x180013f0a  shl     r8, 3; Size
0x180013f0e  mov     rcx, rax; void *
0x180013f11  call    memmove_0
0x180013f16  mov     rcx, [rsi]; void *
0x180013f19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013f1e  mov     [rsi], r14
0x180013f21  mov     [rsi+8], rdi
0x180013f25  mov     rcx, [rsi+10h]
0x180013f29  mov     rax, [rsi]
0x180013f2c  mov     [rax+rcx*8], rbx
0x180013f30  inc     qword ptr [rsi+10h]
0x180013f34  mov     rbx, r15
0x180013f37  mov     [rbp+lpString1+8], rbx
0x180013f3b  mov     dword ptr [rbp+lpString1], r15d
0x180013f3f  mov     [rbp+var_8], r15d
0x180013f43  jmp     loc_180013DF8
0x180013f48  mov     edi, 8000000Bh
0x180013f4d  mov     rcx, [rbp+28h]; this
0x180013f51  mov     r9d, edi; char *
0x180013f54  lea     r8, aOnecoreAdminAp_165; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180013f5b  mov     edx, 1B8h; void *
0x180013f60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f65  mov     rcx, [rbp+28h]; this
0x180013f69  mov     r9d, edi; char *
0x180013f6c  lea     r8, aOnecoreAdminAp_165; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180013f73  mov     edx, 1F2h; void *
0x180013f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f7d  nop
0x180013f7e  test    rbx, rbx
0x180013f81  jz      short loc_180013F8C
0x180013f83  mov     rcx, rbx; void *
0x180013f86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013f8b  nop
0x180013f8c  mov     rcx, [rbp+pv]; pv
0x180013f90  call    cs:__imp_CoTaskMemFree
0x180013f96  nop
0x180013f97  mov     rcx, [rbp+var_30]
0x180013f9b  test    rcx, rcx
0x180013f9e  jz      short loc_180013FB1
0x180013fa0  mov     [rbp+var_30], r15
0x180013fa4  mov     rax, [rcx]
0x180013fa7  mov     rax, [rax+10h]
0x180013fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fb0  nop
0x180013fb1  mov     rcx, [rbp+var_28]
0x180013fb5  test    rcx, rcx
0x180013fb8  jz      short loc_180013FCB
0x180013fba  mov     [rbp+var_28], r15
0x180013fbe  mov     rax, [rcx]
0x180013fc1  mov     rax, [rax+10h]
0x180013fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fca  nop
0x180013fcb  mov     rcx, [rbp+arg_8]
0x180013fcf  test    rcx, rcx
0x180013fd2  jz      short loc_180013FE5
0x180013fd4  mov     [rbp+arg_8], r15
0x180013fd8  mov     rdx, [rcx]
0x180013fdb  mov     rax, [rdx+10h]
0x180013fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe4  nop
0x180013fe5  mov     eax, edi
0x180013fe7  jmp     loc_180013EB2
0x180013fec  mov     rcx, [rbp+28h]; this
0x180013ff0  mov     r9d, edi; char *
0x180013ff3  lea     r8, aOnecoreAdminAp_165; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180013ffa  mov     edx, 1F3h; void *
0x180013fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014004  nop
0x180014005  test    rbx, rbx
0x180014008  jz      short loc_180014013
0x18001400a  mov     rcx, rbx; void *
0x18001400d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014012  nop
0x180014013  mov     rcx, [rbp+pv]; pv
0x180014017  call    cs:__imp_CoTaskMemFree
0x18001401d  nop
0x18001401e  mov     rcx, [rbp+var_30]
0x180014022  test    rcx, rcx
0x180014025  jz      short loc_180014038
0x180014027  mov     [rbp+var_30], r15
0x18001402b  mov     rax, [rcx]
0x18001402e  mov     rax, [rax+10h]
0x180014032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014037  nop
0x180014038  mov     rcx, [rbp+var_28]
0x18001403c  test    rcx, rcx
0x18001403f  jz      short loc_180014052
0x180014041  mov     [rbp+var_28], r15
  ... truncated ...
```
