# OSIntegration::DEH::CapabilityAuthorizationHandler::ParseDeviceCapabilitiesFromManifest(OSIntegration::Package const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x18001ac8c`
- end: `0x18001b338`
- name: `?ParseDeviceCapabilitiesFromManifest@CapabilityAuthorizationHandler@DEH@OSIntegration@@AEBAJPEBVPackage@3@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@1@Z`
- size: `1708`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801321e0`

## callees

- `0x18000b3bc`
- `0x18000e6e0`
- `0x18000fed0`
- `0x18001aba8`
- `0x18001ac8c`
- `0x18001b340`
- `0x18001b40c`
- `0x18006a98c`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001afc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001afc3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001af6c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001af6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b10e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b1d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b10e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b1d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b240`

## string_xrefs

- `0x18001ad42`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::CapabilityAuthorizationHandler::ParseDeviceCapabilitiesFromManifest(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  int v10; // eax
  unsigned int appended; // ebx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID *); // rbx
  int v15; // eax
  __int64 v16; // r9
  const wchar_t *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rsi
  int v20; // eax
  __int64 v21; // rdx
  _WORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  const wchar_t *v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rsi
  int v28; // eax
  int v29; // eax
  WCHAR *v30; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 v32; // rdx
  int v33; // eax
  unsigned __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  unsigned __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-69h]
  __int64 v52; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-51h] BYREF
  __int64 v54; // [rsp+40h] [rbp-49h] BYREF
  int v55; // [rsp+48h] [rbp-41h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+50h] [rbp-39h] BYREF
  int v57; // [rsp+60h] [rbp-29h]
  const int *v58; // [rsp+68h] [rbp-21h] BYREF
  LPCOLESTR *v59; // [rsp+70h] [rbp-19h]
  LPCOLESTR *v60; // [rsp+78h] [rbp-11h]
  LPCWCH lpString1[2]; // [rsp+80h] [rbp-9h] BYREF
  int v62; // [rsp+90h] [rbp+7h]
  GUID pclsid; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v55 = 0;
  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v7 = 0;
  v54 = 0;
  v8 = *(_QWORD *)(a2 + 40);
  if ( v8 )
  {
    v54 = *(_QWORD *)(a2 + 40);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v7 = v54;
  }
  v52 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v10 = v9(v7, &v52);
  appended = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    v43 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return appended;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 32LL))(v52, &v55);
  appended = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
LABEL_55:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    return appended;
  }
  while ( 1 )
  {
    if ( !v55 )
    {
      v38 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v39 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      return 0;
    }
    pv = 0;
    v13 = v52;
    v14 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v52 + 24LL);
    CoTaskMemFree(0);
    pv = 0;
    v15 = v14(v13, &pv);
    appended = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
      goto LABEL_54;
    }
    pclsid = 0;
    *(_OWORD *)lpsz = 0;
    v57 = 0;
    v59 = lpsz;
    v58 = &Common::StringBufferBuilder::`vftable';
    v60 = lpsz;
    v16 = 0x3FFFFFFF;
    v17 = L"{";
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    appended = v16 == 0 ? 0x80070057 : 0;
    v18 = (0x3FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64) & -(__int64)(v16 != 0);
    if ( !v16 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)appended,
        bIgnoreCase);
LABEL_84:
      v37 = appended;
      v36 = 527;
      goto LABEL_85;
    }
    v19 = LODWORD(lpsz[0]);
    v20 = Common::StringBuilder::Insert((Common::StringBuilder *)&v58, (unsigned int)lpsz[0], v18);
    appended = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    }
    else
    {
      memcpy_0((void *)&v59[1][v19], L"{", 2LL * (unsigned int)v18);
      appended = 0;
    }
    if ( (appended & 0x80000000) != 0 )
      goto LABEL_84;
    if ( !pv )
    {
      appended = -2147024809;
LABEL_80:
      LODWORD(v23) = 0;
      goto LABEL_19;
    }
    v21 = 0x3FFFFFFF;
    v22 = pv;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v23 = (0x3FFFFFFF - v21) & -(__int64)(v21 != 0);
    appended = v21 == 0 ? 0x80070057 : 0;
    if ( !v21 )
      goto LABEL_80;
LABEL_19:
    if ( (appended & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)appended,
        bIgnoreCase);
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
        (const char *)appended,
        bIgnoreCase);
      if ( lpsz[1] )
        operator delete((void *)lpsz[1], v45);
      CoTaskMemFree(pv);
      v46 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      return appended;
    }
    appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)&v58, (const unsigned __int16 *)pv, v23);
    if ( (appended & 0x80000000) != 0 )
      goto LABEL_64;
    v24 = 0x3FFFFFFF;
    v25 = L"}";
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    appended = v24 == 0 ? 0x80070057 : 0;
    v26 = (0x3FFFFFFF - v24) & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64) & -(__int64)(v24 != 0);
    if ( !v24 )
      break;
    v27 = *(unsigned int *)v59;
    v28 = Common::StringBuilder::Insert((Common::StringBuilder *)&v58, *(_DWORD *)v59, v26);
    appended = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v28,
        bIgnoreCase);
    }
    else
    {
      memcpy_0((void *)&v59[1][v27], L"}", 2LL * (unsigned int)v26);
      appended = 0;
    }
    if ( (appended & 0x80000000) != 0 )
      goto LABEL_71;
    if ( CLSIDFromString(lpsz[1], &pclsid) >= 0 )
    {
      v33 = OSIntegration::DEH::CapabilityAuthorizationHandler::AddUniqueCapabilityToList(a4, lpsz);
      appended = v33;
      if ( v33 < 0 )
      {
        v36 = 541;
LABEL_45:
        v37 = (unsigned int)v33;
LABEL_85:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
          (const char *)v37,
          bIgnoreCase);
LABEL_53:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpsz);
LABEL_54:
        CoTaskMemFree(pv);
        goto LABEL_55;
      }
    }
    else
    {
      *(_OWORD *)lpString1 = 0;
      v62 = 0;
      v29 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)lpString1, (const unsigned __int16 *)pv);
      appended = v29;
      if ( v29 < 0 )
      {
        v41 = (unsigned int)v29;
        v42 = 535;
LABEL_52:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
          (const char *)v41,
          bIgnoreCase);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
        goto LABEL_53;
      }
      v30 = (WCHAR *)lpString1[1];
      for ( i = 0; i < a3[2]; ++i )
      {
        if ( CompareStringOrdinal(v30, -1, *(LPCWCH *)(*a3 + 8 * i), -1, 1) == 2 )
        {
          if ( i != 0x40000000 )
            goto LABEL_34;
          break;
        }
      }
      v35 = Common::Array<unsigned short,Common::ContainerOperations<unsigned short,unsigned short>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned short>,Common::ArrayOperations<unsigned short,Common::NoKey>>::Add(
              a3,
              v30);
      appended = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
          (const char *)(unsigned int)v35,
          bIgnoreCase);
        v41 = appended;
        v42 = 536;
        goto LABEL_52;
      }
      v30 = 0;
      LODWORD(lpString1[0]) = 0;
      v62 = 0;
LABEL_34:
      if ( v30 )
        operator delete(v30, v32);
    }
    v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 40LL))(v52, &v55);
    appended = v33;
    if ( v33 < 0 )
    {
      v36 = 544;
      goto LABEL_45;
    }
    if ( lpsz[1] )
      operator delete((void *)lpsz[1], v34);
    CoTaskMemFree(pv);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)appended,
    bIgnoreCase);
LABEL_71:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x211,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\capabilityauthorization\\capabilityauthorizationhandler.cpp",
    (const char *)appended,
    bIgnoreCase);
  if ( lpsz[1] )
    operator delete((void *)lpsz[1], v48);
  CoTaskMemFree(pv);
  v49 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  return appended;
}

```

## disassembly

```asm
0x18001ac8c  mov     [rsp-8+arg_0], rbx
0x18001ac91  push    rbp
0x18001ac92  push    rsi
0x18001ac93  push    rdi
0x18001ac94  push    r12
0x18001ac96  push    r13
0x18001ac98  push    r14
0x18001ac9a  push    r15
0x18001ac9c  lea     rbp, [rsp-27h]
0x18001aca1  sub     rsp, 0B0h
0x18001aca8  mov     rax, cs:__security_cookie
0x18001acaf  xor     rax, rsp
0x18001acb2  mov     [rbp+57h+var_38], rax
0x18001acb6  mov     r15, r9
0x18001acb9  mov     r14, r8
0x18001acbc  mov     rdi, rdx
0x18001acbf  xor     r12d, r12d
0x18001acc2  mov     [rbp+57h+var_98], r12d
0x18001acc6  mov     [rbp+57h+var_A0], r12
0x18001acca  lea     rcx, [rbp+57h+var_A0]
0x18001acce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001acd3  mov     ebx, r12d
0x18001acd6  mov     [rbp+57h+var_A0], rbx
0x18001acda  mov     rcx, [rdi+28h]
0x18001acde  test    rcx, rcx
0x18001ace1  jz      short loc_18001ACF7
0x18001ace3  mov     [rbp+57h+var_A0], rcx
0x18001ace7  mov     rax, [rcx]
0x18001acea  mov     rax, [rax+8]
0x18001acee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acf3  mov     rbx, [rbp+57h+var_A0]
0x18001acf7  mov     [rbp+57h+var_B0], r12
0x18001acfb  mov     rax, [rbx]
0x18001acfe  mov     rdi, [rax+40h]
0x18001ad02  lea     rcx, [rbp+57h+var_B0]
0x18001ad06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ad0b  lea     rdx, [rbp+57h+var_B0]
0x18001ad0f  mov     rcx, rbx
0x18001ad12  mov     rax, rdi
0x18001ad15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad1a  mov     ebx, eax
0x18001ad1c  test    eax, eax
0x18001ad1e  js      loc_18001B159
0x18001ad24  mov     rcx, [rbp+57h+var_B0]
0x18001ad28  mov     rax, [rcx]
0x18001ad2b  lea     rdx, [rbp+57h+var_98]
0x18001ad2f  mov     rax, [rax+20h]
0x18001ad33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad38  mov     ebx, eax
0x18001ad3a  test    eax, eax
0x18001ad3c  js      loc_18001B280
0x18001ad42  lea     r13, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\string"...
0x18001ad49  cmp     [rbp+57h+var_98], r12d
0x18001ad4d  jz      loc_18001B069
0x18001ad53  mov     [rbp+57h+pv], r12
0x18001ad57  mov     rdi, [rbp+57h+var_B0]
0x18001ad5b  mov     rax, [rdi]
0x18001ad5e  mov     rbx, [rax+18h]
0x18001ad62  xor     ecx, ecx; pv
0x18001ad64  call    cs:__imp_CoTaskMemFree
0x18001ad6a  mov     [rbp+57h+pv], r12
0x18001ad6e  lea     rdx, [rbp+57h+pv]
0x18001ad72  mov     rcx, rdi
0x18001ad75  mov     rax, rbx
0x18001ad78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad7d  mov     ebx, eax
0x18001ad7f  test    eax, eax
0x18001ad81  js      loc_18001B31A
0x18001ad87  xorps   xmm0, xmm0
0x18001ad8a  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001ad8e  movups  xmmword ptr [rbp+57h+lpsz], xmm0
0x18001ad92  mov     [rbp+57h+var_80], r12d
0x18001ad96  lea     rax, [rbp+57h+lpsz]
0x18001ad9a  mov     [rbp+57h+var_70], rax
0x18001ad9e  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001ada5  mov     [rbp+57h+var_78], rax
0x18001ada9  lea     rax, [rbp+57h+lpsz]
0x18001adad  mov     [rbp+57h+var_68], rax
0x18001adb1  mov     r9d, 3FFFFFFFh
0x18001adb7  lea     rax, Str; "{"
0x18001adbe  cmp     [rax], r12w
0x18001adc2  jz      short loc_18001ADCE
0x18001adc4  add     rax, 2
0x18001adc8  sub     r9, 1
0x18001adcc  jnz     short loc_18001ADBE
0x18001adce  mov     rax, r9
0x18001add1  neg     rax
0x18001add4  sbb     ebx, ebx
0x18001add6  not     ebx
0x18001add8  and     ebx, 80070057h
0x18001adde  mov     r8, r9
0x18001ade1  mov     rax, r9
0x18001ade4  mov     ecx, 3FFFFFFFh
0x18001ade9  sub     rcx, r9
0x18001adec  neg     rax
0x18001adef  sbb     rdx, rdx
0x18001adf2  and     rdx, rcx
0x18001adf5  neg     r8
0x18001adf8  sbb     rdi, rdi
0x18001adfb  and     rdi, rdx
0x18001adfe  mov     rcx, [rbp+5Fh]; this
0x18001ae02  test    r9, r9
0x18001ae05  jz      loc_18001B2C3
0x18001ae0b  mov     esi, dword ptr [rbp+57h+lpsz]
0x18001ae0e  mov     r8d, edi; unsigned int
0x18001ae11  mov     edx, esi; unsigned int
0x18001ae13  lea     rcx, [rbp+57h+var_78]; this
0x18001ae17  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x18001ae1c  mov     ebx, eax
0x18001ae1e  mov     rcx, [rbp+5Fh]; this
0x18001ae22  test    eax, eax
0x18001ae24  js      loc_18001B12F
0x18001ae2a  mov     r8d, edi
0x18001ae2d  add     r8, r8; Size
0x18001ae30  mov     rax, [rbp+57h+var_70]
0x18001ae34  mov     rcx, [rax+8]
0x18001ae38  lea     rcx, [rcx+rsi*2]; void *
0x18001ae3c  lea     rdx, Str; "{"
0x18001ae43  call    memcpy_0
0x18001ae48  mov     ebx, r12d
0x18001ae4b  test    ebx, ebx
0x18001ae4d  js      loc_18001B2D3
0x18001ae53  mov     r9, [rbp+57h+pv]
0x18001ae57  mov     edi, 3FFFFFFFh
0x18001ae5c  test    r9, r9
0x18001ae5f  jz      loc_18001B29D
0x18001ae65  mov     edx, edi
0x18001ae67  mov     rax, r9
0x18001ae6a  cmp     [rax], r12w
0x18001ae6e  jz      short loc_18001AE7A
0x18001ae70  add     rax, 2
0x18001ae74  sub     rdx, 1
0x18001ae78  jnz     short loc_18001AE6A
0x18001ae7a  mov     rax, rdx
0x18001ae7d  mov     rcx, rdi
0x18001ae80  sub     rcx, rdx
0x18001ae83  neg     rax
0x18001ae86  sbb     r8, r8
0x18001ae89  and     r8, rcx; unsigned int
0x18001ae8c  mov     rax, rdx
0x18001ae8f  neg     rax
0x18001ae92  sbb     ebx, ebx
0x18001ae94  not     ebx
0x18001ae96  mov     esi, 80070057h
0x18001ae9b  and     ebx, esi
0x18001ae9d  test    rdx, rdx
0x18001aea0  jz      loc_18001B2A4
0x18001aea6  mov     rcx, [rbp+5Fh]; this
0x18001aeaa  test    ebx, ebx
0x18001aeac  js      loc_18001B305
0x18001aeb2  mov     rdx, r9; unsigned __int16 *
0x18001aeb5  lea     rcx, [rbp+57h+var_78]; this
0x18001aeb9  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001aebe  mov     ebx, eax
0x18001aec0  test    eax, eax
0x18001aec2  js      loc_18001B1A8
0x18001aec8  mov     r9, rdi
0x18001aecb  lea     rax, asc_180232158; "}"
0x18001aed2  cmp     [rax], r12w
0x18001aed6  jz      short loc_18001AEE2
0x18001aed8  add     rax, 2
0x18001aedc  sub     r9, 1
0x18001aee0  jnz     short loc_18001AED2
0x18001aee2  mov     rax, r9
0x18001aee5  neg     rax
0x18001aee8  sbb     ebx, ebx
0x18001aeea  not     ebx
0x18001aeec  and     ebx, esi
0x18001aeee  mov     r8, r9
0x18001aef1  mov     rax, r9
0x18001aef4  mov     rcx, rdi
0x18001aef7  sub     rcx, r9
0x18001aefa  neg     rax
0x18001aefd  sbb     rdx, rdx
0x18001af00  and     rdx, rcx
0x18001af03  neg     r8
0x18001af06  sbb     rdi, rdi
0x18001af09  and     rdi, rdx
0x18001af0c  mov     rcx, [rbp+5Fh]; this
0x18001af10  test    r9, r9
0x18001af13  jz      loc_18001B2F0
0x18001af19  mov     rax, [rbp+57h+var_70]
0x18001af1d  mov     esi, [rax]
0x18001af1f  mov     r8d, edi; unsigned int
0x18001af22  mov     edx, esi; unsigned int
0x18001af24  lea     rcx, [rbp+57h+var_78]; this
0x18001af28  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x18001af2d  mov     ebx, eax
0x18001af2f  mov     rcx, [rbp+5Fh]; this
0x18001af33  test    eax, eax
0x18001af35  js      loc_18001B144
0x18001af3b  mov     r8d, edi
0x18001af3e  add     r8, r8; Size
0x18001af41  mov     rax, [rbp+57h+var_70]
0x18001af45  mov     rcx, [rax+8]
0x18001af49  lea     rcx, [rcx+rsi*2]; void *
0x18001af4d  lea     rdx, asc_180232158; "}"
0x18001af54  call    memcpy_0
0x18001af59  mov     ebx, r12d
0x18001af5c  test    ebx, ebx
0x18001af5e  js      loc_18001B214
0x18001af64  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001af68  mov     rcx, [rbp+57h+lpsz+8]; lpsz
0x18001af6c  call    cs:__imp_CLSIDFromString
0x18001af72  test    eax, eax
0x18001af74  jns     loc_18001B04A
0x18001af7a  xorps   xmm0, xmm0
0x18001af7d  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x18001af81  mov     [rbp+57h+var_50], r12d
0x18001af85  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18001af89  lea     rcx, [rbp+57h+lpString1]; this
0x18001af8d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001af92  mov     ebx, eax
0x18001af94  test    eax, eax
0x18001af96  js      loc_18001B2AC
0x18001af9c  mov     rdi, [rbp+57h+lpString1+8]
0x18001afa0  mov     rbx, r12
0x18001afa3  cmp     rbx, [r14+10h]
0x18001afa7  jnb     short loc_18001B028
0x18001afa9  mov     r8, [r14]
0x18001afac  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18001afb4  or      eax, 0FFFFFFFFh
0x18001afb7  mov     r9d, eax; cchCount2
0x18001afba  mov     r8, [r8+rbx*8]; lpString2
0x18001afbe  mov     edx, eax; cchCount1
0x18001afc0  mov     rcx, rdi; lpString1
0x18001afc3  call    cs:__imp_CompareStringOrdinal
0x18001afc9  add     eax, 0FFFFFFFEh
0x18001afcc  jnz     short loc_18001B020
0x18001afce  cmp     rbx, 40000000h
0x18001afd5  jz      short loc_18001B028
0x18001afd7  test    rdi, rdi
0x18001afda  jz      short loc_18001AFE4
0x18001afdc  mov     rcx, rdi; void *
0x18001afdf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001afe4  mov     rcx, [rbp+57h+var_B0]
0x18001afe8  mov     rax, [rcx]
0x18001afeb  lea     rdx, [rbp+57h+var_98]
0x18001afef  mov     rax, [rax+28h]
0x18001aff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff8  mov     ebx, eax
0x18001affa  test    eax, eax
0x18001affc  js      loc_18001B2B9
0x18001b002  mov     rcx, [rbp+57h+lpsz+8]; void *
0x18001b006  test    rcx, rcx
0x18001b009  jz      short loc_18001B011
0x18001b00b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b010  nop
0x18001b011  mov     rcx, [rbp+57h+pv]; pv
0x18001b015  call    cs:__imp_CoTaskMemFree
0x18001b01b  jmp     loc_18001AD49
0x18001b020  inc     rbx
0x18001b023  jmp     loc_18001AFA3
0x18001b028  mov     rdx, rdi
0x18001b02b  mov     rcx, r14
0x18001b02e  call    ?Add@?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@QEAAJPEAG@Z; Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>>::Add(ushort *)
0x18001b033  mov     ebx, eax
0x18001b035  test    eax, eax
0x18001b037  js      loc_18001B0C6
0x18001b03d  mov     rdi, r12
0x18001b040  mov     dword ptr [rbp+57h+lpString1], r12d
0x18001b044  mov     [rbp+57h+var_50], r12d
0x18001b048  jmp     short loc_18001AFD7
0x18001b04a  lea     rdx, [rbp+57h+lpsz]
0x18001b04e  mov     rcx, r15
0x18001b051  call    ?AddUniqueCapabilityToList@CapabilityAuthorizationHandler@DEH@OSIntegration@@CAJAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@AEAVStringBuffer@5@@Z; OSIntegration::DEH::CapabilityAuthorizationHandler::AddUniqueCapabilityToList(Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &,Common::StringBuffer &)
0x18001b056  mov     ebx, eax
0x18001b058  test    eax, eax
0x18001b05a  jns     short loc_18001AFE4
0x18001b05c  mov     edx, 21Dh
0x18001b061  mov     r9d, eax
0x18001b064  jmp     loc_18001B2DB
0x18001b069  mov     rcx, [rbp+57h+var_B0]
0x18001b06d  test    rcx, rcx
0x18001b070  jz      short loc_18001B083
0x18001b072  mov     [rbp+57h+var_B0], r12
0x18001b076  mov     rax, [rcx]
0x18001b079  mov     rax, [rax+10h]
0x18001b07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b082  nop
0x18001b083  mov     rcx, [rbp+57h+var_A0]
0x18001b087  test    rcx, rcx
0x18001b08a  jz      short loc_18001B09D
0x18001b08c  mov     [rbp+57h+var_A0], r12
0x18001b090  mov     rax, [rcx]
0x18001b093  mov     rax, [rax+10h]
0x18001b097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b09c  nop
0x18001b09d  xor     eax, eax
0x18001b09f  mov     rcx, [rbp+57h+var_38]
0x18001b0a3  xor     rcx, rsp; StackCookie
0x18001b0a6  call    __security_check_cookie
0x18001b0ab  mov     rbx, [rsp+0E0h+arg_0]
0x18001b0b3  add     rsp, 0B0h
0x18001b0ba  pop     r15
0x18001b0bc  pop     r14
0x18001b0be  pop     r13
0x18001b0c0  pop     r12
0x18001b0c2  pop     rdi
0x18001b0c3  pop     rsi
  ... truncated ...
```
