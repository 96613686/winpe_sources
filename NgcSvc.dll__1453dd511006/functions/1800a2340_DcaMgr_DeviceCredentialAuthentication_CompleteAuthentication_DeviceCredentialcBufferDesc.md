# DcaMgr::DeviceCredentialAuthentication::CompleteAuthentication(_DeviceCredentialcBufferDesc *)

- ea: `0x1800a2340`
- end: `0x1800a28d8`
- name: `?CompleteAuthentication@DeviceCredentialAuthentication@DcaMgr@@UEAAJPEAU_DeviceCredentialcBufferDesc@@@Z`
- size: `1432`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialAuthentication *__hidden this, struct _DeviceCredentialcBufferDesc *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x180013710`
- `0x180022e30`
- `0x180032c20`
- `0x180048304`
- `0x18004b7c4`
- `0x180050b30`
- `0x180053144`
- `0x18005dd20`
- `0x180069998`
- `0x180069b58`
- `0x180069c28`
- `0x180097cb4`
- `0x180098cfc`
- `0x180098e4c`
- `0x18009986c`
- `0x1800a2340`
- `0x1800a6408`
- `0x1800a66a8`
- `0x1800a7624`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x1800a24bd`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x1800a24bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2478`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2562`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2478`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2562`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800a24af`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800a24af`

## string_xrefs

- `0x1800a2422`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a248a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a251a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2573`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a25d6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2636`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a26ec`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2840`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a28ab`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DcaMgr::DeviceCredentialAuthentication::CompleteAuthentication(
        DcaMgr::DeviceCredentialAuthentication *this,
        struct _DeviceCredentialcBufferDesc *a2)
{
  __int64 v3; // rdx
  const void *v4; // rsi
  int v5; // r10d
  const void *v6; // r14
  int v7; // r11d
  unsigned int i; // r9d
  HKEY *v9; // r8
  int Hmac; // ebx
  __int64 v11; // rdx
  unsigned int ValueW; // eax
  HKEY *v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  double v16; // xmm0_8
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // r15d
  char *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  __int64 v24; // rcx
  void *v25; // rdx
  int v26; // eax
  struct DcaMgr::DeviceCredentialMgr *v27; // rax
  __int64 v28; // rcx
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  void *v32; // rdx
  __int64 v33; // rcx
  void *v34; // rdx
  void *v35; // rdx
  void *v37; // rdx
  bool v38; // zf
  void *v39; // rdx
  int pdwType; // [rsp+20h] [rbp-59h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-59h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-59h]
  int pdwTypec; // [rsp+20h] [rbp-59h]
  int pdwTyped; // [rsp+20h] [rbp-59h]
  void *v45; // [rsp+40h] [rbp-39h] BYREF
  void *v46; // [rsp+48h] [rbp-31h] BYREF
  HKEY v47; // [rsp+50h] [rbp-29h] BYREF
  void *Buf1; // [rsp+58h] [rbp-21h] BYREF
  void **p_hkey; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 v50[4]; // [rsp+68h] [rbp-11h] BYREF
  char v51; // [rsp+70h] [rbp-9h]
  void *Destination; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v53; // [rsp+80h] [rbp+7h] BYREF
  int v54[2]; // [rsp+88h] [rbp+Fh] BYREF
  HKEY hkey; // [rsp+90h] [rbp+17h] BYREF
  __time64_t Time[7]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD pcbData; // [rsp+E8h] [rbp+6Fh] BYREF
  size_t Size; // [rsp+F0h] [rbp+77h] BYREF
  int pvData; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( *((_DWORD *)a2 + 1) != 2 || (v3 = *((_QWORD *)a2 + 1)) == 0 )
  {
    v11 = 999;
    goto LABEL_63;
  }
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v9 = (HKEY *)(unsigned int)(*(_DWORD *)(v3 + 16LL * i) - 7);
    if ( *(_DWORD *)(v3 + 16LL * i) == 7 )
    {
      v6 = *(const void **)(v3 + 16LL * i + 8);
      v7 = *(_DWORD *)(v3 + 16LL * i + 4);
    }
    else
    {
      if ( *(_DWORD *)(v3 + 16LL * i) != 8 )
      {
        v11 = 1019;
        goto LABEL_63;
      }
      v4 = *(const void **)(v3 + 16LL * i + 8);
      v5 = *(_DWORD *)(v3 + 16LL * i + 4);
    }
  }
  if ( !v6 || v7 != 32 || !v4 || v5 != 32 )
  {
    v11 = 1025;
LABEL_63:
    Hmac = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)0x80070057LL,
      pdwType);
    return (unsigned int)Hmac;
  }
  hkey = 0;
  p_hkey = (void **)&hkey;
  *(_QWORD *)v50 = 0;
  v51 = 1;
  Hmac = DcaMgr::OpenUserRegKey(*((LPCWSTR *)this + 11), v50, v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( Hmac < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)Hmac,
      pdwType);
LABEL_60:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return (unsigned int)Hmac;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"TpmHmacEnabled", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    v14 = ValueW;
    v15 = 1041;
LABEL_18:
    Hmac = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
             (const char *)v14,
             pdwTypea);
    goto LABEL_60;
  }
  if ( !pvData )
  {
    Time[0] = 0;
    _time64(Time);
    v16 = _o__difftime64(Time[0], *((_QWORD *)this + 12));
    if ( v16 < 0.0 || v16 > 20.0 )
    {
      v14 = 1931;
      v15 = 1050;
      goto LABEL_18;
    }
  }
  v47 = 0;
  p_hkey = (void **)&v47;
  *(_QWORD *)v50 = 0;
  v51 = 1;
  Hmac = DcaMgr::OpenDeviceRegKey(*((LPCWSTR *)this + 1), v50, v13);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( Hmac < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)Hmac,
      pdwTypea);
LABEL_59:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
    goto LABEL_60;
  }
  v53 = 0;
  pcbData = 4;
  v17 = RegGetValueW(v47, 0, L"DeviceCapability", 0x10u, 0, &v53, &pcbData);
  if ( v17 )
  {
    Hmac = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x42A,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
             (const char *)v17,
             pdwTypeb);
    goto LABEL_59;
  }
  v45 = 0;
  LODWORD(Size) = 0;
  p_hkey = &v45;
  *(_QWORD *)v50 = 0;
  v51 = 1;
  Hmac = ReadRegBinaryValue(v47, &Size);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hkey);
  if ( Hmac < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)Hmac,
      pdwTypec);
LABEL_57:
    v39 = v45;
    v45 = 0;
    if ( v39 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v18, v39);
    goto LABEL_59;
  }
  v46 = 0;
  v54[0] = 0;
  p_hkey = &v46;
  *(_QWORD *)v50 = 0;
  v51 = 1;
  Hmac = DpapiProtectUnprotect(0, (_DWORD)v45, Size, (unsigned int)v50, (__int64)v54);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hkey);
  if ( Hmac < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43D,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)Hmac,
      pdwTyped);
    goto LABEL_55;
  }
  v19 = *((_DWORD *)this + 12) + 32;
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&Destination, v19);
  v20 = (char *)Destination;
  if ( !Destination )
  {
    Hmac = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)0x8007000ELL,
      pdwTyped);
LABEL_54:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Destination);
LABEL_55:
    v37 = v46;
    v38 = v46 == 0;
    v46 = 0;
    if ( !v38 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v18, v37);
    goto LABEL_57;
  }
  memcpy_s(Destination, 0x20u, v4, 0x20u);
  memcpy_s(v20 + 32, *((unsigned int *)this + 12), *((const void *const *)this + 5), *((unsigned int *)this + 12));
  Buf1 = 0;
  LODWORD(Size) = 0;
  p_hkey = &Buf1;
  *(_QWORD *)v50 = 0;
  v51 = 1;
  Hmac = GenerateHmac(v21, v46, (unsigned int)v54[0], v20);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hkey);
  if ( Hmac < 0 )
  {
    v22 = 1111;
LABEL_34:
    v23 = (unsigned int)Hmac;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)v23,
      v19);
LABEL_36:
    v25 = Buf1;
    Buf1 = 0;
    if ( v25 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v24, v25);
    goto LABEL_54;
  }
  if ( (_DWORD)Size != 32 || memcmp_0(Buf1, v6, 0x20u) )
  {
    Hmac = -2147024883;
    v22 = 1117;
    goto LABEL_34;
  }
  v26 = (***((__int64 (__fastcall ****)(_QWORD, const void *, __int64))this + 13))(*((_QWORD *)this + 13), v4, 32);
  Hmac = v26;
  if ( v26 < 0 )
  {
    v23 = (unsigned int)v26;
    v22 = 1119;
    goto LABEL_35;
  }
  v27 = DcaMgr::DeviceCredentialMgr::Instance();
  Hmac = DcaMgr::DeviceCredentialMgr::SetDeviceHmac(
           v27,
           *((_QWORD *)this + 1),
           v53,
           *((_QWORD *)this + 11),
           *((_QWORD *)this + 13),
           v50,
           &Size);
  if ( Hmac < 0 )
  {
    v29 = DevCredSvcTraceLoggingProvider::Provider();
    v24 = *(unsigned int *)v29;
    if ( (unsigned int)v24 > 2 )
    {
      LODWORD(Size) = Hmac;
      *(_QWORD *)v54 = *((_QWORD *)this + 1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v29,
        (unsigned __int8 *)&unk_18010AE48,
        v30,
        v31,
        (const WCHAR **)v54,
        (__int64)&Size);
    }
    goto LABEL_36;
  }
  *((_QWORD *)this + 13) = 0;
  v32 = Buf1;
  Buf1 = 0;
  if ( v32 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v28, v32);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Destination);
  v34 = v46;
  v46 = 0;
  if ( v34 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v33, v34);
  v35 = v45;
  v45 = 0;
  if ( v35 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v33, v35);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x1800a2340  mov     [rsp-8+arg_0], rbx
0x1800a2345  push    rbp
0x1800a2346  push    rsi
0x1800a2347  push    rdi
0x1800a2348  push    r12
0x1800a234a  push    r13
0x1800a234c  push    r14
0x1800a234e  push    r15
0x1800a2350  lea     rbp, [rsp-27h]
0x1800a2355  sub     rsp, 0A0h
0x1800a235c  mov     rdi, rcx
0x1800a235f  cmp     dword ptr [rdx+4], 2
0x1800a2363  jnz     loc_1800A289E
0x1800a2369  mov     rdx, [rdx+8]
0x1800a236d  xor     r12d, r12d
0x1800a2370  test    rdx, rdx
0x1800a2373  jz      loc_1800A289E
0x1800a2379  mov     esi, r12d
0x1800a237c  mov     r10d, r12d
0x1800a237f  mov     r14d, r12d
0x1800a2382  mov     r11d, r12d
0x1800a2385  mov     r9d, r12d
0x1800a2388  mov     ecx, r9d
0x1800a238b  add     rcx, rcx
0x1800a238e  mov     r8d, [rdx+rcx*8]
0x1800a2392  sub     r8d, 7; HKEY *
0x1800a2396  jz      short loc_1800A23AE
0x1800a2398  cmp     r8d, 1
0x1800a239c  jnz     loc_1800A2438
0x1800a23a2  mov     rsi, [rdx+rcx*8+8]
0x1800a23a7  mov     r10d, [rdx+rcx*8+4]
0x1800a23ac  jmp     short loc_1800A23B8
0x1800a23ae  mov     r14, [rdx+rcx*8+8]
0x1800a23b3  mov     r11d, [rdx+rcx*8+4]
0x1800a23b8  inc     r9d
0x1800a23bb  cmp     r9d, 2
0x1800a23bf  jb      short loc_1800A2388
0x1800a23c1  test    r14, r14
0x1800a23c4  jz      loc_1800A2897
0x1800a23ca  mov     r13d, 20h ; ' '
0x1800a23d0  cmp     r11d, r13d
0x1800a23d3  jnz     loc_1800A2897
0x1800a23d9  test    rsi, rsi
0x1800a23dc  jz      loc_1800A2897
0x1800a23e2  cmp     r10d, r13d
0x1800a23e5  jnz     loc_1800A2897
0x1800a23eb  mov     [rbp+57h+hkey], r12
0x1800a23ef  lea     rax, [rbp+57h+hkey]
0x1800a23f3  mov     [rbp+57h+var_70], rax
0x1800a23f7  mov     qword ptr [rbp+57h+var_68], r12
0x1800a23fb  mov     [rbp+57h+var_60], 1
0x1800a23ff  lea     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800a2403  mov     rcx, [rdi+58h]; lpSubKey
0x1800a2407  call    ?OpenUserRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenUserRegKey(ushort const *,HKEY__ * *)
0x1800a240c  mov     ebx, eax
0x1800a240e  lea     rcx, [rbp+57h+var_70]
0x1800a2412  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a2417  test    ebx, ebx
0x1800a2419  jns     short loc_1800A2442
0x1800a241b  mov     rcx, [rbp+5Fh]; this
0x1800a241f  mov     r9d, ebx; char *
0x1800a2422  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2429  mov     edx, 406h; void *
0x1800a242e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2433  jmp     loc_1800A288C
0x1800a2438  mov     edx, 3FBh
0x1800a243d  jmp     loc_1800A28A3
0x1800a2442  mov     [rbp+57h+arg_18], r12d
0x1800a2446  mov     r15d, 4
0x1800a244c  mov     [rbp+57h+arg_8], r15d
0x1800a2450  lea     rax, [rbp+57h+arg_8]
0x1800a2454  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800a2459  lea     rax, [rbp+57h+arg_18]
0x1800a245d  mov     [rsp+0D0h+pvData], rax; pvData
0x1800a2462  mov     [rsp+0D0h+pdwType], r12; int
0x1800a2467  lea     r9d, [r15+0Ch]; dwFlags
0x1800a246b  lea     r8, aTpmhmacenabled; "TpmHmacEnabled"
0x1800a2472  xor     edx, edx; lpSubKey
0x1800a2474  mov     rcx, [rbp+57h+hkey]; hkey
0x1800a2478  call    cs:__imp_RegGetValueW
0x1800a247e  test    eax, eax
0x1800a2480  jz      short loc_1800A24A1
0x1800a2482  mov     r9d, eax; char *
0x1800a2485  mov     edx, 411h; void *
0x1800a248a  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2491  mov     rcx, [rbp+5Fh]; this
0x1800a2495  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a249a  mov     ebx, eax
0x1800a249c  jmp     loc_1800A288C
0x1800a24a1  cmp     [rbp+57h+arg_18], r12d
0x1800a24a5  jnz     short loc_1800A24E3
0x1800a24a7  mov     [rbp+57h+Time], r12
0x1800a24ab  lea     rcx, [rbp+57h+Time]; Time
0x1800a24af  call    cs:__imp__time64
0x1800a24b5  mov     rdx, [rdi+60h]
0x1800a24b9  mov     rcx, [rbp+57h+Time]
0x1800a24bd  call    cs:__imp__o__difftime64
0x1800a24c3  xorps   xmm1, xmm1
0x1800a24c6  comisd  xmm1, xmm0
0x1800a24ca  ja      short loc_1800A24D6
0x1800a24cc  comisd  xmm0, cs:__real@4034000000000000
0x1800a24d4  jbe     short loc_1800A24E3
0x1800a24d6  mov     r9d, 78Bh
0x1800a24dc  mov     edx, 41Ah
0x1800a24e1  jmp     short loc_1800A248A
0x1800a24e3  mov     [rbp+57h+var_80], r12
0x1800a24e7  lea     rax, [rbp+57h+var_80]
0x1800a24eb  mov     [rbp+57h+var_70], rax
0x1800a24ef  mov     qword ptr [rbp+57h+var_68], r12
0x1800a24f3  mov     [rbp+57h+var_60], 1
0x1800a24f7  lea     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800a24fb  mov     rcx, [rdi+8]; lpSubKey
0x1800a24ff  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x1800a2504  mov     ebx, eax
0x1800a2506  lea     rcx, [rbp+57h+var_70]
0x1800a250a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a250f  test    ebx, ebx
0x1800a2511  jns     short loc_1800A2530
0x1800a2513  mov     rcx, [rbp+5Fh]; this
0x1800a2517  mov     r9d, ebx; char *
0x1800a251a  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2521  mov     edx, 41Fh; void *
0x1800a2526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a252b  jmp     loc_1800A2882
0x1800a2530  mov     [rbp+57h+var_50], r12d
0x1800a2534  mov     [rbp+57h+arg_8], r15d
0x1800a2538  lea     rax, [rbp+57h+arg_8]
0x1800a253c  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800a2541  lea     rax, [rbp+57h+var_50]
0x1800a2545  mov     [rsp+0D0h+pvData], rax; pvData
0x1800a254a  mov     [rsp+0D0h+pdwType], r12; unsigned int
0x1800a254f  mov     r9d, 10h; dwFlags
0x1800a2555  lea     r8, aDevicecapabili; "DeviceCapability"
0x1800a255c  xor     edx, edx; lpSubKey
0x1800a255e  mov     rcx, [rbp+57h+var_80]; hkey
0x1800a2562  call    cs:__imp_RegGetValueW
0x1800a2568  test    eax, eax
0x1800a256a  jz      short loc_1800A258B
0x1800a256c  mov     rcx, [rbp+5Fh]; this
0x1800a2570  mov     r9d, eax; char *
0x1800a2573  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a257a  mov     edx, 42Ah; void *
0x1800a257f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2584  mov     ebx, eax
0x1800a2586  jmp     loc_1800A2882
0x1800a258b  mov     [rbp+57h+var_90], r12
0x1800a258f  mov     dword ptr [rbp+57h+Size], r12d
0x1800a2593  lea     rax, [rbp+57h+var_90]
0x1800a2597  mov     [rbp+57h+var_70], rax
0x1800a259b  mov     qword ptr [rbp+57h+var_68], r12
0x1800a259f  mov     [rbp+57h+var_60], 1
0x1800a25a3  lea     rax, [rbp+57h+Size]
0x1800a25a7  mov     [rsp+0D0h+pdwType], rax; int
0x1800a25ac  lea     r9, [rbp+57h+var_68]
0x1800a25b0  lea     r8, aAuthkey; "AuthKey"
0x1800a25b7  mov     rcx, [rbp+57h+var_80]; hkey
0x1800a25bb  call    ReadRegBinaryValue
0x1800a25c0  mov     ebx, eax
0x1800a25c2  lea     rcx, [rbp+57h+var_70]
0x1800a25c6  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a25cb  test    ebx, ebx
0x1800a25cd  jns     short loc_1800A25EC
0x1800a25cf  mov     rcx, [rbp+5Fh]; this
0x1800a25d3  mov     r9d, ebx; char *
0x1800a25d6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a25dd  mov     edx, 434h; void *
0x1800a25e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a25e7  jmp     loc_1800A286F
0x1800a25ec  mov     [rbp+57h+var_88], r12
0x1800a25f0  mov     [rbp+57h+var_48], r12d
0x1800a25f4  lea     rax, [rbp+57h+var_88]
0x1800a25f8  mov     [rbp+57h+var_70], rax
0x1800a25fc  mov     qword ptr [rbp+57h+var_68], r12
0x1800a2600  mov     [rbp+57h+var_60], 1
0x1800a2604  lea     rax, [rbp+57h+var_48]
0x1800a2608  mov     [rsp+0D0h+pdwType], rax; int
0x1800a260d  lea     r9, [rbp+57h+var_68]
0x1800a2611  mov     r8d, dword ptr [rbp+57h+Size]
0x1800a2615  mov     rdx, [rbp+57h+var_90]
0x1800a2619  xor     ecx, ecx
0x1800a261b  call    DpapiProtectUnprotect
0x1800a2620  mov     ebx, eax
0x1800a2622  lea     rcx, [rbp+57h+var_70]
0x1800a2626  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a262b  test    ebx, ebx
0x1800a262d  jns     short loc_1800A264C
0x1800a262f  mov     rcx, [rbp+5Fh]; this
0x1800a2633  mov     r9d, ebx; char *
0x1800a2636  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a263d  mov     edx, 43Dh; void *
0x1800a2642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2647  jmp     loc_1800A285C
0x1800a264c  mov     r15d, [rdi+30h]
0x1800a2650  add     r15d, 20h ; ' '
0x1800a2654  mov     edx, r15d
0x1800a2657  lea     rcx, [rbp+57h+Destination]
0x1800a265b  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a2660  nop
0x1800a2661  mov     rbx, [rbp+57h+Destination]
0x1800a2665  test    rbx, rbx
0x1800a2668  jz      loc_1800A2834
0x1800a266e  mov     r9, r13; SourceSize
0x1800a2671  mov     r8, rsi; Source
0x1800a2674  mov     rdx, r13; DestinationSize
0x1800a2677  mov     rcx, rbx; Destination
0x1800a267a  call    memcpy_s
0x1800a267f  mov     edx, [rdi+30h]; DestinationSize
0x1800a2682  lea     rcx, [rbx+20h]; Destination
0x1800a2686  mov     r9d, edx; SourceSize
0x1800a2689  mov     r8, [rdi+28h]; Source
0x1800a268d  call    memcpy_s
0x1800a2692  mov     [rbp+57h+Buf1], r12
0x1800a2696  mov     dword ptr [rbp+57h+Size], r12d
0x1800a269a  lea     rax, [rbp+57h+Buf1]
0x1800a269e  mov     [rbp+57h+var_70], rax
0x1800a26a2  mov     qword ptr [rbp+57h+var_68], r12
0x1800a26a6  mov     [rbp+57h+var_60], 1
0x1800a26aa  lea     rax, [rbp+57h+Size]
0x1800a26ae  mov     [rsp+0D0h+pcbData], rax
0x1800a26b3  lea     rax, [rbp+57h+var_68]
0x1800a26b7  mov     [rsp+0D0h+pvData], rax
0x1800a26bc  mov     dword ptr [rsp+0D0h+pdwType], r15d; int
0x1800a26c1  mov     r9, rbx
0x1800a26c4  mov     r8d, [rbp+57h+var_48]
0x1800a26c8  mov     rdx, [rbp+57h+var_88]
0x1800a26cc  call    GenerateHmac
0x1800a26d1  mov     ebx, eax
0x1800a26d3  lea     rcx, [rbp+57h+var_70]
0x1800a26d7  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a26dc  test    ebx, ebx
0x1800a26de  jns     short loc_1800A2714
0x1800a26e0  mov     edx, 457h; void *
0x1800a26e5  mov     r9d, ebx; char *
0x1800a26e8  mov     rcx, [rbp+5Fh]; this
0x1800a26ec  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a26f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a26f8  nop
0x1800a26f9  mov     rdx, [rbp+57h+Buf1]
0x1800a26fd  mov     [rbp+57h+Buf1], r12
0x1800a2701  test    rdx, rdx
0x1800a2704  jz      loc_1800A2852
0x1800a270a  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800a270f  jmp     loc_1800A2852
0x1800a2714  cmp     dword ptr [rbp+57h+Size], r13d
0x1800a2718  jnz     loc_1800A2825
0x1800a271e  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x1800a2722  mov     rdx, r14; Buf2
0x1800a2725  mov     rcx, [rbp+57h+Buf1]; Buf1
0x1800a2729  call    memcmp_0
0x1800a272e  test    eax, eax
0x1800a2730  jnz     loc_1800A2825
0x1800a2736  mov     rcx, [rdi+68h]
0x1800a273a  mov     rax, [rcx]
0x1800a273d  mov     r8d, r13d
0x1800a2740  mov     rdx, rsi
0x1800a2743  mov     rax, [rax]
0x1800a2746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a274b  mov     ebx, eax
0x1800a274d  test    eax, eax
0x1800a274f  jns     short loc_1800A275B
0x1800a2751  mov     r9d, eax
0x1800a2754  mov     edx, 45Fh
0x1800a2759  jmp     short loc_1800A26E8
0x1800a275b  call    ?Instance@DeviceCredentialMgr@DcaMgr@@SAAEAV12@XZ; DcaMgr::DeviceCredentialMgr::Instance(void)
0x1800a2760  mov     rcx, [rdi+68h]
0x1800a2764  mov     [rsp+0D0h+pdwType], rcx
0x1800a2769  mov     r9, [rdi+58h]
0x1800a276d  mov     r8d, [rbp+57h+var_50]
0x1800a2771  mov     rdx, [rdi+8]
0x1800a2775  mov     rcx, rax
0x1800a2778  call    ?SetDeviceHmac@DeviceCredentialMgr@DcaMgr@@QEAAJPEBGW4_DeviceCredentialCapabilities@@0PEAVDeviceCredentialHmacBase@2@@Z; DcaMgr::DeviceCredentialMgr::SetDeviceHmac(ushort const *,_DeviceCredentialCapabilities,ushort const *,DcaMgr::DeviceCredentialHmacBase *)
0x1800a277d  mov     ebx, eax
0x1800a277f  test    eax, eax
0x1800a2781  jns     short loc_1800A27C4
0x1800a2783  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x1800a2788  mov     ecx, [rax]
0x1800a278a  cmp     ecx, 2
0x1800a278d  jbe     loc_1800A26F9
0x1800a2793  mov     dword ptr [rbp+57h+Size], ebx
0x1800a2796  mov     rcx, [rdi+8]
0x1800a279a  mov     qword ptr [rbp+57h+var_48], rcx
0x1800a279e  lea     rcx, [rbp+57h+Size]
0x1800a27a2  mov     [rsp+0D0h+pvData], rcx
0x1800a27a7  lea     rcx, [rbp+57h+var_48]
0x1800a27ab  mov     [rsp+0D0h+pdwType], rcx
0x1800a27b0  lea     rdx, unk_18010AE48
0x1800a27b7  mov     rcx, rax
0x1800a27ba  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800a27bf  jmp     loc_1800A26F9
0x1800a27c4  mov     [rdi+68h], r12
0x1800a27c8  mov     rdx, [rbp+57h+Buf1]
0x1800a27cc  mov     [rbp+57h+Buf1], r12
0x1800a27d0  test    rdx, rdx
0x1800a27d3  jz      short loc_1800A27DB
0x1800a27d5  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800a27da  nop
0x1800a27db  lea     rcx, [rbp+57h+Destination]
0x1800a27df  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a27e4  nop
0x1800a27e5  mov     rdx, [rbp+57h+var_88]
  ... truncated ...
```
