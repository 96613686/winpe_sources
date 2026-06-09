# s_WebAuthNAuthenticatorMakeCredentialNgcSyncedPasskeys(_CTAPDEVICE_CONTROL_BLOCK *,_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *,bool,PasskeyTelemetry &)

- ea: `0x18003298c`
- end: `0x180033927`
- name: `?s_WebAuthNAuthenticatorMakeCredentialNgcSyncedPasskeys@@YAJPEAU_CTAPDEVICE_CONTROL_BLOCK@@PEAU_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST@@_NAEAUPasskeyTelemetry@@@Z`
- size: `3995`
- prototype: `int(struct _CTAPDEVICE_CONTROL_BLOCK *, struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *, bool, struct PasskeyTelemetry *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009f0f8`

## callees

- `0x18001687c`
- `0x180017a88`
- `0x18001c0d4`
- `0x18001cdd4`
- `0x18001d5e4`
- `0x18001df88`
- `0x1800288c8`
- `0x18002a314`
- `0x1800328b8`
- `0x180032964`
- `0x18003298c`
- `0x180033930`
- `0x1800350b4`
- `0x180036448`
- `0x18003653c`
- `0x180036da4`
- `0x18003e378`
- `0x180043ab4`
- `0x18004c6ec`
- `0x18004d8f4`
- `0x18005378c`
- `0x1800537a4`
- `0x1800642d8`
- `0x18007e1b4`
- `0x18007ed34`
- `0x18007f6d0`
- `0x180080fd4`
- `0x180084df4`
- `0x18008b978`
- `0x18008f3e8`
- `0x18008f67c`
- `0x1800d2d14`
- `0x1800d3830`
- `0x1800d6410`
- `0x1800e3eb8`
- `0x180138924`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032e87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033178`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003327a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003357f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003369c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033823`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032e87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033178`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003327a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003357f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003369c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033823`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003375e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003375e`

## string_xrefs

- `0x1800329d7`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032a04`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032a32`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032a60`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032a8e`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032abc`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032aed`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032b1b`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032b4c`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032b7a`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032ba8`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032c6d`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032d82`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180032f99`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180033141`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180033258`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180033559`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18003363c`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180033787`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180033882`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x1800332f1`: `onecore\ds\security\cbor\lib\common\cose.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall s_WebAuthNAuthenticatorMakeCredentialNgcSyncedPasskeys(
        struct _CTAPDEVICE_CONTROL_BLOCK *a1,
        struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *a2,
        char a3,
        struct PasskeyTelemetry *a4)
{
  unsigned int v7; // r14d
  __int64 v9; // r15
  __int64 v10; // rsi
  char *v11; // rbx
  _DWORD *v12; // r8
  _DWORD *v13; // rdx
  struct _WEBAUTHN_CREDENTIAL_LIST *v14; // rdx
  int FilteredCredentials; // eax
  unsigned int v16; // ebx
  int v17; // ebx
  __int64 v18; // rdx
  int v19; // ecx
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  HLOCAL v23; // rcx
  _DWORD *v24; // rcx
  unsigned __int64 v25; // r8
  size_t v26; // r8
  char *v27; // rbx
  HLOCAL v28; // rcx
  __int64 v29; // r9
  __int64 v30; // r8
  int Credential; // ebx
  _QWORD *v32; // rdx
  HLOCAL v33; // rcx
  HLOCAL v34; // rcx
  HLOCAL v35; // rcx
  unsigned int CredentialResponse; // ebx
  int v37; // eax
  unsigned int v38; // ebx
  HLOCAL v39; // rcx
  HLOCAL v40; // rcx
  unsigned int v41; // eax
  HLOCAL v42; // rcx
  HLOCAL v43; // rcx
  unsigned int v44; // ebx
  int v45; // eax
  HLOCAL v46; // rcx
  HLOCAL v47; // rcx
  HLOCAL v48; // rcx
  unsigned int v49; // eax
  int v50; // eax
  HLOCAL v51; // rcx
  HLOCAL v52; // rcx
  HLOCAL v53; // rcx
  HLOCAL v54; // rcx
  void *v55; // rbx
  unsigned int updated; // eax
  HLOCAL v57; // rcx
  HLOCAL v58; // rcx
  HLOCAL v59; // rcx
  HLOCAL v60; // rcx
  HLOCAL v61; // rcx
  HLOCAL v62; // rcx
  void *v63; // [rsp+20h] [rbp-468h]
  int v64; // [rsp+20h] [rbp-468h]
  unsigned int v65; // [rsp+20h] [rbp-468h]
  __int64 v66; // [rsp+28h] [rbp-460h]
  unsigned __int8 *v67; // [rsp+40h] [rbp-448h]
  struct NgcPasskeys::WebAuthnCredentialAttestation *v68; // [rsp+60h] [rbp-428h]
  HLOCAL v69; // [rsp+68h] [rbp-420h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-418h] BYREF
  HLOCAL v71; // [rsp+78h] [rbp-410h] BYREF
  HLOCAL v72; // [rsp+80h] [rbp-408h] BYREF
  unsigned int v73[2]; // [rsp+88h] [rbp-400h] BYREF
  char v74; // [rsp+90h] [rbp-3F8h]
  _QWORD v75[2]; // [rsp+A0h] [rbp-3E8h] BYREF
  bool v76[16]; // [rsp+B0h] [rbp-3D8h] BYREF
  __int128 *v77; // [rsp+C0h] [rbp-3C8h]
  struct _GUID *v78; // [rsp+D0h] [rbp-3B8h] BYREF
  void *v79; // [rsp+D8h] [rbp-3B0h]
  __int64 v80; // [rsp+E0h] [rbp-3A8h]
  unsigned __int8 *v81; // [rsp+E8h] [rbp-3A0h] BYREF
  __int128 v82; // [rsp+F0h] [rbp-398h] BYREF
  __int128 v83; // [rsp+100h] [rbp-388h]
  __int64 v84; // [rsp+110h] [rbp-378h]
  HLOCAL *v85; // [rsp+128h] [rbp-360h] BYREF
  __int64 v86; // [rsp+130h] [rbp-358h] BYREF
  char v87; // [rsp+138h] [rbp-350h]
  _BYTE v88[40]; // [rsp+140h] [rbp-348h] BYREF
  void *v89; // [rsp+168h] [rbp-320h]
  char v90; // [rsp+170h] [rbp-318h]
  unsigned int v91; // [rsp+171h] [rbp-317h]
  __int16 v92; // [rsp+175h] [rbp-313h]
  char v93; // [rsp+177h] [rbp-311h]
  char v94; // [rsp+278h] [rbp-210h]
  _BYTE v95[24]; // [rsp+280h] [rbp-208h] BYREF
  __int128 v96; // [rsp+298h] [rbp-1F0h]
  unsigned __int16 v97; // [rsp+2A8h] [rbp-1E0h]
  __int64 v98; // [rsp+2B0h] [rbp-1D8h]
  unsigned __int16 v99; // [rsp+2B8h] [rbp-1D0h]
  __int64 v100; // [rsp+2C0h] [rbp-1C8h]
  int v101; // [rsp+2E0h] [rbp-1A8h] BYREF
  const wchar_t *v102; // [rsp+2E8h] [rbp-1A0h]
  const wchar_t *v103; // [rsp+2F0h] [rbp-198h]
  int v104; // [rsp+3A4h] [rbp-E4h]
  char v105; // [rsp+3A8h] [rbp-E0h] BYREF
  char v106; // [rsp+3B0h] [rbp-D8h] BYREF
  int v107; // [rsp+3B8h] [rbp-D0h]
  int v108; // [rsp+3BCh] [rbp-CCh]
  unsigned int v109[4]; // [rsp+3F0h] [rbp-98h] BYREF
  _QWORD v110[4]; // [rsp+400h] [rbp-88h] BYREF
  void *Src; // [rsp+420h] [rbp-68h] BYREF
  __int64 v112; // [rsp+428h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  LOBYTE(v68) = a3;
  v7 = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63A,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*((_QWORD *)a2 + 3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63C,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*((_DWORD *)a2 + 4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63D,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*((_QWORD *)a2 + 7) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x643,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*((_DWORD *)a2 + 12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x644,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  v9 = *((_QWORD *)a2 + 4);
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x645,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*(_QWORD *)(v9 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  v10 = *((_QWORD *)a2 + 5);
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x647,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*(_QWORD *)(v10 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  if ( !*(_DWORD *)(v10 + 4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x80090027LL,
      (int)v63);
    return 2148073511LL;
  }
  v11 = (char *)a4 + 144;
  std::vector<long>::_Assign_counted_range<long const *>((char *)a4 + 144, 0, 0);
  while ( v7 < *((_DWORD *)a2 + 12) )
  {
    v12 = (_DWORD *)(*((_QWORD *)a2 + 7) + 8 * (3LL * v7 + 2));
    v13 = (_DWORD *)*((_QWORD *)v11 + 1);
    if ( v13 == *((_DWORD **)v11 + 2) )
    {
      std::vector<long>::_Emplace_reallocate<long const &>(v11, v13, v12);
    }
    else
    {
      *v13 = *v12;
      *((_QWORD *)v11 + 1) += 4LL;
    }
    ++v7;
  }
  if ( *((_QWORD *)a2 + 9) && *((_DWORD *)a2 + 16) )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v76);
    FilteredCredentials = HelloPasskey::GetFilteredCredentials(
                            *(_QWORD *)(v9 + 8),
                            v14,
                            *(_QWORD *)(*((_QWORD *)a1 + 39) + 64LL),
                            0,
                            (__int64 *)v76);
    v16 = FilteredCredentials;
    if ( FilteredCredentials < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65A,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)FilteredCredentials,
        (int)v63);
      std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(v76);
      return v16;
    }
    if ( *(_QWORD *)v76 != *(_QWORD *)&v76[8] )
    {
      v17 = I_NgcDummyUserVerification(a1, a4);
      std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(v76);
      if ( v17 < 0 )
        return (unsigned int)v17;
      else
        return 2148073487LL;
    }
    std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(v76);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v78);
  v18 = *(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL);
  v19 = *(_DWORD *)(v18 + 160);
  if ( v19 )
  {
    hMem = 0;
    *(_QWORD *)v76 = &hMem;
    *(_QWORD *)&v76[8] = 0;
    LOBYTE(v77) = 1;
    v20 = CtapCborDecodeHmacSecretSaltValues(v19, *(_QWORD *)(v18 + 168), (unsigned int)&v76[8], 0, 0);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v76);
    if ( v20 )
    {
      v21 = HRESULT_FROM_CBOR_ERROR(v20);
      v22 = v21;
      if ( v21 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67F,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          (const char *)(unsigned int)v21,
          (int)v63);
      v23 = hMem;
      hMem = 0;
      if ( v23 )
        LocalFree(v23);
      std::vector<unsigned char>::_Tidy(&v78);
      return v22;
    }
    v24 = *(_DWORD **)hMem;
    if ( *(_QWORD *)hMem )
    {
      v25 = (unsigned int)(*v24 + v24[4]);
      if ( v25 >= (_BYTE *)v79 - (_BYTE *)v78 )
      {
        if ( v25 > (_BYTE *)v79 - (_BYTE *)v78 )
        {
          if ( v25 <= v80 - (__int64)v78 )
          {
            v26 = v25 - ((_BYTE *)v79 - (_BYTE *)v78);
            v27 = (char *)v79 + v26;
            memset_0(v79, 0, v26);
            v79 = v27;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v78, (unsigned int)(*v24 + v24[4]));
          }
        }
      }
      else
      {
        v79 = (char *)v78 + (unsigned int)(*v24 + v24[4]);
      }
      memcpy_0(v78, *(const void **)(*(_QWORD *)hMem + 8LL), **(unsigned int **)hMem);
      memcpy_0(
        (char *)v78 + **(unsigned int **)hMem,
        *(const void **)(*(_QWORD *)hMem + 24LL),
        *(unsigned int *)(*(_QWORD *)hMem + 16LL));
    }
    v28 = hMem;
    hMem = 0;
    if ( v28 )
      LocalFree(v28);
  }
  v75[0] = 0;
  LODWORD(v81) = 0;
  *(_OWORD *)v109 = 0;
  std::wstring::wstring(v110);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
  v72 = v75;
  *(_QWORD *)v73 = 0;
  v74 = 1;
  v29 = *((_QWORD *)a1 + 39);
  v30 = *(_QWORD *)(v29 + 56);
  *(_OWORD *)v76 = *(_OWORD *)(v30 + 16);
  LODWORD(v67) = (_DWORD)v79 - (_DWORD)v78;
  LODWORD(v63) = *(_DWORD *)(v30 + 460);
  Credential = HelloPasskey::MakeCredential(
                 **(HelloPasskey ***)(v30 + 152),
                 (HWND)a2,
                 (const struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *)*(unsigned int *)(v30 + 440),
                 *(_QWORD *)(v29 + 64),
                 v63,
                 (char)v68,
                 (bool)v76,
                 v78,
                 v67,
                 (unsigned int)v73,
                 &v81,
                 v109,
                 v68);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>(&v72);
  if ( Credential < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)Credential,
      v64);
    NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation((NgcPasskeys::WebAuthnCredentialAttestation *)v109);
    wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(v75, 0);
    std::vector<unsigned char>::_Tidy(&v78);
    return (unsigned int)Credential;
  }
  wil::make_unique_hlocal<_WEBAUTHN_CREDENTIAL_ATTESTATION,>(&v69);
  *(_DWORD *)v69 = v109[2];
  v32 = v110;
  if ( v110[3] > 7u )
    v32 = (_QWORD *)v110[0];
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &hMem,
    v32,
    -1);
  wil::make_unique_hlocal<unsigned char [0]>(&v72, v112 - (_QWORD)Src);
  if ( !v72 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A5,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)0x8007000ELL,
      v64);
    v61 = v72;
    v72 = 0;
    if ( v61 )
      LocalFree(v61);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
    v62 = v69;
    v69 = 0;
    if ( v62 )
      LocalFree(v62);
    NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation((NgcPasskeys::WebAuthnCredentialAttestation *)v109);
    wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(v75, 0);
    std::vector<unsigned char>::_Tidy(&v78);
    return 2147942414LL;
  }
  memcpy_0(v72, Src, v112 - (_QWORD)Src);
  v33 = hMem;
  hMem = 0;
  *((_QWORD *)v69 + 1) = v33;
  *((_DWORD *)v69 + 4) = v112 - (_DWORD)Src;
  v34 = v72;
  v72 = 0;
  *((_QWORD *)v69 + 3) = v34;
  v35 = v72;
  v72 = 0;
  if ( v35 )
    LocalFree(v35);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&hMem);
  v71 = 0;
  LODWORD(hMem) = 0;
  *(_QWORD *)v76 = &v71;
  *(_QWORD *)&v76[8] = 0;
  LOBYTE(v77) = 1;
  CredentialResponse = CtapCborEncodeMakeCredentialResponse(
                         0,
                         (_DWORD)v69,
                         (unsigned int)&hMem,
                         (unsigned int)&v76[8],
                         0,
                         v66);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v76);
  if ( CredentialResponse )
  {
    v37 = HRESULT_FROM_CBOR_ERROR(CredentialResponse);
    v38 = v37;
    if ( v37 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B1,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)v37,
        v65);
    v39 = v71;
    v71 = 0;
    if ( v39 )
      LocalFree(v39);
    v40 = v69;
    v69 = 0;
    if ( v40 )
      LocalFree(v40);
LABEL_117:
    NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation((NgcPasskeys::WebAuthnCredentialAttestation *)v109);
    wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(v75, 0);
    std::vector<unsigned char>::_Tidy(&v78);
    return v38;
  }
  memset_0(&v101, 0, 0x110u);
  v101 = 1;
  v102 = L"Platform";
  v103 = L"MicrosoftPlatformProvider";
  v104 = 1;
  v107 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 440LL);
  v108 = 16;
  memset_0(v95, 0, 0x58u);
  v41 = CtapCborUnpackAuthenticatorData(*((unsigned int *)v69 + 4), *((_QWORD *)v69 + 3), v95);
  if ( v41 )
  {
    v38 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x6BF,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)v41,
            v65);
    v42 = v71;
    v71 = 0;
    if ( v42 )
      LocalFree(v42);
    v43 = v69;
    v69 = 0;
    if ( v43 )
      LocalFree(v43);
    goto LABEL_117;
  }
  *((_OWORD *)a4 + 2) = v96;
  LODWORD(v72) = 517;
  HIDWORD(v72) = *(_DWORD *)&v76[4];
  *(_QWORD *)v73 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  *(_QWORD *)v76 = v100;
  *(_QWORD *)&v76[8] = v99;
  SimpleCbor::Decoder::Decoder(&v82, v76, &v72);
  Cose::Key::FromCbor(v88, &v82);
  SimpleCbor::Decoder::~Decoder((SimpleCbor::Decoder *)&v82);
  if ( !v94 )
  {
    v72 = v89;
    LOBYTE(v73[0]) = v90;
    *(unsigned int *)((char *)v73 + 1) = v91;
    *(_WORD *)((char *)&v73[1] + 1) = v92;
    HIBYTE(v73[1]) = v93;
    if ( !v90 )
      goto LABEL_82;
    goto LABEL_81;
  }
  if ( v94 == 1 )
  {
    v72 = v89;
    LOBYTE(v73[0]) = v90;
    *(unsigned int *)((char *)v73 + 1) = v91;
    *(_WORD *)((char *)&v73[1] + 1) = v92;
    HIBYTE(v73[1]) = v93;
    if ( v90 )
LABEL_81:
      *((_DWORD *)a4 + 42) = *(_DWORD *)std::optional<enum Cose::Algorithm>::value(&v72);
  }
LABEL_82:
  if ( (_DWORD)v81 )
  {
    v82 = 0;
    v83 = 0;
    *(_DWORD *)&v76[4] = 0;
    HIDWORD(v81) = 0;
    v72 = 0;
    if ( (_DWORD)v81 == 32 )
    {
      *((_QWORD *)&v82 + 1) = v75[0];
    }
    else
    {
      if ( (_DWORD)v81 != 64 )
      {
LABEL_88:
        *(_DWORD *)v76 = v97;
        *(_QWORD *)&v76[8] = v98;
        v77 = &v82;
        v85 = &v72;
        v86 = 0;
        v87 = 1;
        v44 = CtapCborEncodeCredWithHmacSecret(v76, (char *)&v81 + 4, &v86, 0);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v85);
        if ( v44 )
        {
          v45 = HRESULT_FROM_CBOR_ERROR(v44);
          v38 = v45;
          if ( v45 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F0,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)(unsigned int)v45,
              v65);
          v46 = v72;
          v72 = 0;
          if ( v46 )
            LocalFree(v46);
          std::_Variant_base<Cose::RsaKey,Cose::EccKey,Cose::SymmetricKey>::_Destroy(v88);
          v47 = v71;
          v71 = 0;
          if ( v47 )
            LocalFree(v47);
          v48 = v69;
          v69 = 0;
          if ( v48 )
            LocalFree(v48);
          goto LABEL_117;
        }
        v49 = CtapCborEncodeAppendToArray((unsigned int)&v105, (unsigned int)&v106, HIDWORD(v81), (_DWORD)v72, 0);
        if ( v49 )
        {
          v50 = HRESULT_FROM_CBOR_ERROR(v49);
          v38 = v50;
          if ( v50 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F5,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)(unsigned int)v50,
              v65);
          v51 = v72;
          v72 = 0;
          if ( v51 )
            LocalFree(v51);
          std::_Variant_base<Cose::RsaKey,Cose::EccKey,Cose::SymmetricKey>::_Destroy(v88);
          v52 = v71;
          v71 = 0;
          if ( v52 )
            LocalFree(v52);
          v53 = v69;
          v69 = 0;
          if ( v53 )
            LocalFree(v53);
          goto LABEL_117;
        }
        v54 = v72;
        v72 = 0;
        if ( v54 )
          LocalFree(v54);
        goto LABEL_110;
      }
      *((_QWORD *)&v82 + 1) = v75[0];
      *((_QWORD *)&v83 + 1) = v75[0] + 32LL;
      LODWORD(v83) = 32;
    }
    LODWORD(v82) = 32;
    goto LABEL_88;
  }
LABEL_110:
  *(_QWORD *)&v82 = 1;
  LODWORD(v83) = 0;
  v84 = 0;
  *((_QWORD *)&v82 + 1) = &v101;
  DWORD1(v83) = (_DWORD)hMem;
  *((_QWORD *)&v83 + 1) = v71;
  v55 = (void *)*((_QWORD *)v69 + 3);
  v72 = (HLOCAL)*((_QWORD *)v69 + 1);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v72);
  if ( v55 )
    CoTaskMemFree(v55);
  updated = CtapDeviceUpdateControlBlockResponse(a1, &v82);
  if ( updated )
  {
    v38 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x704,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)updated,
            v65);
    std::_Variant_base<Cose::RsaKey,Cose::EccKey,Cose::SymmetricKey>::_Destroy(v88);
    v57 = v71;
    v71 = 0;
    if ( v57 )
      LocalFree(v57);
    v58 = v69;
    v69 = 0;
    if ( v58 )
      LocalFree(v58);
    goto LABEL_117;
  }
  std::_Variant_base<Cose::RsaKey,Cose::EccKey,Cose::SymmetricKey>::_Destroy(v88);
  v59 = v71;
  v71 = 0;
  if ( v59 )
    LocalFree(v59);
  v60 = v69;
  v69 = 0;
  if ( v60 )
    LocalFree(v60);
  NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation((NgcPasskeys::WebAuthnCredentialAttestation *)v109);
  wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>::reset(v75, 0);
  std::vector<unsigned char>::_Tidy(&v78);
  return 0;
}

```

## disassembly

```asm
0x18003298c  push    rbx
0x18003298e  push    rsi
0x18003298f  push    rdi
0x180032990  push    r12
0x180032992  push    r13
0x180032994  push    r14
0x180032996  push    r15
0x180032998  sub     rsp, 450h
0x18003299f  mov     rax, cs:__security_cookie
0x1800329a6  xor     rax, rsp
0x1800329a9  mov     [rsp+488h+var_48], rax
0x1800329b1  mov     r12, r9
0x1800329b4  mov     byte ptr [rsp+488h+var_428], r8b; struct NgcPasskeys::WebAuthnCredentialAttestation *
0x1800329b9  mov     rdi, rdx
0x1800329bc  mov     r13, rcx
0x1800329bf  xor     r14d, r14d
0x1800329c2  test    rcx, rcx
0x1800329c5  jnz     short loc_1800329EF
0x1800329c7  mov     rcx, [rsp+488h]; this
0x1800329cf  mov     ebx, 80090027h
0x1800329d4  mov     r9d, ebx; char *
0x1800329d7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800329de  mov     edx, 63Ah; void *
0x1800329e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800329e8  mov     eax, ebx
0x1800329ea  jmp     loc_180033903
0x1800329ef  test    rdi, rdi
0x1800329f2  jnz     short loc_180032A1C
0x1800329f4  mov     rcx, [rsp+488h]; this
0x1800329fc  mov     ebx, 80090027h
0x180032a01  mov     r9d, ebx; char *
0x180032a04  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032a0b  mov     edx, 63Bh; void *
0x180032a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a15  mov     eax, ebx
0x180032a17  jmp     loc_180033903
0x180032a1c  cmp     [rdx+18h], r14
0x180032a20  jnz     short loc_180032A4A
0x180032a22  mov     rcx, [rsp+488h]; this
0x180032a2a  mov     ebx, 80090027h
0x180032a2f  mov     r9d, ebx; char *
0x180032a32  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032a39  mov     edx, 63Ch; void *
0x180032a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a43  mov     eax, ebx
0x180032a45  jmp     loc_180033903
0x180032a4a  cmp     [rdx+10h], r14d
0x180032a4e  jnz     short loc_180032A78
0x180032a50  mov     rcx, [rsp+488h]; this
0x180032a58  mov     ebx, 80090027h
0x180032a5d  mov     r9d, ebx; char *
0x180032a60  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032a67  mov     edx, 63Dh; void *
0x180032a6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a71  mov     eax, ebx
0x180032a73  jmp     loc_180033903
0x180032a78  cmp     [rdx+38h], r14
0x180032a7c  jnz     short loc_180032AA6
0x180032a7e  mov     rcx, [rsp+488h]; this
0x180032a86  mov     ebx, 80090027h
0x180032a8b  mov     r9d, ebx; char *
0x180032a8e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032a95  mov     edx, 643h; void *
0x180032a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a9f  mov     eax, ebx
0x180032aa1  jmp     loc_180033903
0x180032aa6  cmp     [rdx+30h], r14d
0x180032aaa  jnz     short loc_180032AD4
0x180032aac  mov     rcx, [rsp+488h]; this
0x180032ab4  mov     ebx, 80090027h
0x180032ab9  mov     r9d, ebx; char *
0x180032abc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032ac3  mov     edx, 644h; void *
0x180032ac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032acd  mov     eax, ebx
0x180032acf  jmp     loc_180033903
0x180032ad4  mov     r15, [rdx+20h]
0x180032ad8  test    r15, r15
0x180032adb  jnz     short loc_180032B05
0x180032add  mov     rcx, [rsp+488h]; this
0x180032ae5  mov     ebx, 80090027h
0x180032aea  mov     r9d, ebx; char *
0x180032aed  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032af4  mov     edx, 645h; void *
0x180032af9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032afe  mov     eax, ebx
0x180032b00  jmp     loc_180033903
0x180032b05  cmp     [r15+8], r14
0x180032b09  jnz     short loc_180032B33
0x180032b0b  mov     rcx, [rsp+488h]; this
0x180032b13  mov     ebx, 80090027h
0x180032b18  mov     r9d, ebx; char *
0x180032b1b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032b22  mov     edx, 646h; void *
0x180032b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032b2c  mov     eax, ebx
0x180032b2e  jmp     loc_180033903
0x180032b33  mov     rsi, [rdx+28h]
0x180032b37  test    rsi, rsi
0x180032b3a  jnz     short loc_180032B64
0x180032b3c  mov     rcx, [rsp+488h]; this
0x180032b44  mov     ebx, 80090027h
0x180032b49  mov     r9d, ebx; char *
0x180032b4c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032b53  mov     edx, 647h; void *
0x180032b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032b5d  mov     eax, ebx
0x180032b5f  jmp     loc_180033903
0x180032b64  cmp     [rsi+8], r14
0x180032b68  jnz     short loc_180032B92
0x180032b6a  mov     rcx, [rsp+488h]; this
0x180032b72  mov     ebx, 80090027h
0x180032b77  mov     r9d, ebx; char *
0x180032b7a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032b81  mov     edx, 648h; void *
0x180032b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032b8b  mov     eax, ebx
0x180032b8d  jmp     loc_180033903
0x180032b92  cmp     [rsi+4], r14d
0x180032b96  jnz     short loc_180032BC0
0x180032b98  mov     rcx, [rsp+488h]; this
0x180032ba0  mov     ebx, 80090027h
0x180032ba5  mov     r9d, ebx; char *
0x180032ba8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032baf  mov     edx, 649h; void *
0x180032bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032bb9  mov     eax, ebx
0x180032bbb  jmp     loc_180033903
0x180032bc0  lea     rbx, [r9+90h]
0x180032bc7  xor     r8d, r8d
0x180032bca  xor     edx, edx
0x180032bcc  mov     rcx, rbx
0x180032bcf  call    ??$_Assign_counted_range@PEBJ@?$vector@JV?$allocator@J@std@@@std@@AEAAXPEBJ_K@Z; std::vector<long>::_Assign_counted_range<long const *>(long const *,unsigned __int64)
0x180032bd4  cmp     r14d, [rdi+30h]
0x180032bd8  jnb     short loc_180032C10
0x180032bda  mov     eax, r14d
0x180032bdd  lea     r8, [rax+rax*2]
0x180032be1  mov     rax, [rdi+38h]
0x180032be5  lea     r8, [r8+2]
0x180032be9  lea     r8, [rax+r8*8]
0x180032bed  mov     rdx, [rbx+8]
0x180032bf1  cmp     rdx, [rbx+10h]
0x180032bf5  jz      short loc_180032C03
0x180032bf7  mov     eax, [r8]
0x180032bfa  mov     [rdx], eax
0x180032bfc  add     qword ptr [rbx+8], 4
0x180032c01  jmp     short loc_180032C0B
0x180032c03  mov     rcx, rbx
0x180032c06  call    ??$_Emplace_reallocate@AEBJ@?$vector@JV?$allocator@J@std@@@std@@AEAAPEAJQEAJAEBJ@Z; std::vector<long>::_Emplace_reallocate<long const &>(long * const,long const &)
0x180032c0b  inc     r14d
0x180032c0e  jmp     short loc_180032BD4
0x180032c10  lea     rdx, [rdi+40h]
0x180032c14  xor     r14d, r14d
0x180032c17  cmp     [rdx+8], r14
0x180032c1b  jz      loc_180032CF2
0x180032c21  cmp     [rdx], r14d
0x180032c24  jz      loc_180032CF2
0x180032c2a  lea     rcx, [rsp+488h+var_3D8]
0x180032c32  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180032c37  nop
0x180032c38  mov     r8, [r13+138h]
0x180032c3f  lea     rax, [rsp+488h+var_3D8]
0x180032c47  mov     [rsp+488h+var_468], rax; int
0x180032c4c  xor     r9d, r9d
0x180032c4f  mov     r8, [r8+40h]
0x180032c53  mov     rcx, [r15+8]
0x180032c57  call    ?GetFilteredCredentials@HelloPasskey@@YAJPEBGPEBU_WEBAUTHN_CREDENTIAL_LIST@@PEAX_NAEAV?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@@Z; HelloPasskey::GetFilteredCredentials(ushort const *,_WEBAUTHN_CREDENTIAL_LIST const *,void *,bool,std::vector<NgcPasskeys::WebAuthnAccountCredential> &)
0x180032c5c  mov     ebx, eax
0x180032c5e  test    eax, eax
0x180032c60  jns     short loc_180032C93
0x180032c62  mov     rcx, [rsp+488h]; this
0x180032c6a  mov     r9d, eax; char *
0x180032c6d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032c74  mov     edx, 65Ah; void *
0x180032c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c7e  nop
0x180032c7f  lea     rcx, [rsp+488h+var_3D8]
0x180032c87  call    ?_Tidy@?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@AEAAXXZ; std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(void)
0x180032c8c  mov     eax, ebx
0x180032c8e  jmp     loc_180033903
0x180032c93  mov     rax, qword ptr [rsp+488h+var_3D8+8]
0x180032c9b  cmp     qword ptr [rsp+488h+var_3D8], rax
0x180032ca3  jnz     short loc_180032CB4
0x180032ca5  lea     rcx, [rsp+488h+var_3D8]
0x180032cad  call    ?_Tidy@?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@AEAAXXZ; std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(void)
0x180032cb2  jmp     short loc_180032CF2
0x180032cb4  mov     [rsp+488h+var_468], r12
0x180032cb9  mov     r9b, byte ptr [rsp+488h+var_428]
0x180032cbe  mov     r8, [r15+8]
0x180032cc2  mov     rdx, [rsi+10h]
0x180032cc6  mov     rcx, r13
0x180032cc9  call    I_NgcDummyUserVerification
0x180032cce  mov     ebx, eax
0x180032cd0  lea     rcx, [rsp+488h+var_3D8]
0x180032cd8  call    ?_Tidy@?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@AEAAXXZ; std::vector<NgcPasskeys::WebAuthnAccountCredential>::_Tidy(void)
0x180032cdd  test    ebx, ebx
0x180032cdf  js      short loc_180032CEB
0x180032ce1  mov     eax, 8009000Fh
0x180032ce6  jmp     loc_180033903
0x180032ceb  mov     eax, ebx
0x180032ced  jmp     loc_180033903
0x180032cf2  lea     rcx, [rsp+488h+var_3B8]
0x180032cfa  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180032cff  nop
0x180032d00  mov     rax, [r13+138h]
0x180032d07  mov     rdx, [rax+38h]
0x180032d0b  mov     ecx, [rdx+0A0h]
0x180032d11  test    ecx, ecx
0x180032d13  jz      loc_180032E8D
0x180032d19  mov     [rsp+488h+hMem], r14
0x180032d1e  lea     rax, [rsp+488h+hMem]
0x180032d23  mov     qword ptr [rsp+488h+var_3D8], rax
0x180032d2b  mov     qword ptr [rsp+488h+var_3D8+8], r14
0x180032d33  mov     byte ptr [rsp+488h+var_3C8], 1
0x180032d3b  mov     [rsp+488h+var_468], r14; int
0x180032d40  xor     r9d, r9d
0x180032d43  lea     r8, [rsp+488h+var_3D8+8]
0x180032d4b  mov     rdx, [rdx+0A8h]
0x180032d52  call    CtapCborDecodeHmacSecretSaltValues
0x180032d57  mov     ebx, eax
0x180032d59  lea     rcx, [rsp+488h+var_3D8]
0x180032d61  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180032d66  test    ebx, ebx
0x180032d68  jz      short loc_180032DBE
0x180032d6a  mov     ecx, ebx
0x180032d6c  call    _HRESULT_FROM_CBOR_ERROR
0x180032d71  mov     ebx, eax
0x180032d73  test    eax, eax
0x180032d75  jns     short loc_180032D94
0x180032d77  mov     rcx, [rsp+488h]; this
0x180032d7f  mov     r9d, eax; char *
0x180032d82  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180032d89  mov     edx, 67Fh; void *
0x180032d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d93  nop
0x180032d94  mov     rcx, [rsp+488h+hMem]; hMem
0x180032d99  mov     [rsp+488h+hMem], r14
0x180032d9e  test    rcx, rcx
0x180032da1  jz      short loc_180032DAA
0x180032da3  call    cs:__imp_LocalFree
0x180032da9  nop
0x180032daa  lea     rcx, [rsp+488h+var_3B8]
0x180032db2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180032db7  mov     eax, ebx
0x180032db9  jmp     loc_180033903
0x180032dbe  mov     rax, [rsp+488h+hMem]
0x180032dc3  mov     rcx, [rax]
0x180032dc6  test    rcx, rcx
0x180032dc9  jz      loc_180032E78
0x180032dcf  mov     eax, [rcx+10h]
0x180032dd2  add     eax, [rcx]
0x180032dd4  mov     r8d, eax
0x180032dd7  mov     rdx, [rsp+488h+var_3B8]
0x180032ddf  mov     r9, [rsp+488h+var_3B0]
0x180032de7  mov     rcx, r9
0x180032dea  sub     rcx, rdx
0x180032ded  cmp     r8, rcx
0x180032df0  jnb     short loc_180032DFF
0x180032df2  add     rax, rdx
0x180032df5  mov     [rsp+488h+var_3B0], rax
0x180032dfd  jmp     short loc_180032E3C
0x180032dff  jbe     short loc_180032E3C
0x180032e01  mov     rax, [rsp+488h+var_3A8]
0x180032e09  sub     rax, rdx
0x180032e0c  cmp     r8, rax
0x180032e0f  jbe     short loc_180032E23
0x180032e11  mov     rdx, r8
0x180032e14  lea     rcx, [rsp+488h+var_3B8]
0x180032e1c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180032e21  jmp     short loc_180032E3C
0x180032e23  sub     r8, rcx; Size
0x180032e26  lea     rbx, [r9+r8]
0x180032e2a  xor     edx, edx; Val
0x180032e2c  mov     rcx, r9; void *
0x180032e2f  call    memset_0
0x180032e34  mov     [rsp+488h+var_3B0], rbx
0x180032e3c  mov     rax, [rsp+488h+hMem]
0x180032e41  mov     rdx, [rax]
0x180032e44  mov     r8d, [rdx]; Size
0x180032e47  mov     rdx, [rdx+8]; Src
0x180032e4b  mov     rcx, [rsp+488h+var_3B8]; void *
0x180032e53  call    memcpy_0
0x180032e58  mov     rax, [rsp+488h+hMem]
0x180032e5d  mov     rdx, [rax]
0x180032e60  mov     r8d, [rdx+10h]; Size
0x180032e64  mov     ecx, [rdx]
0x180032e66  add     rcx, [rsp+488h+var_3B8]; void *
0x180032e6e  mov     rdx, [rdx+18h]; Src
0x180032e72  call    memcpy_0
0x180032e77  nop
0x180032e78  mov     rcx, [rsp+488h+hMem]; hMem
0x180032e7d  mov     [rsp+488h+hMem], r14
0x180032e82  test    rcx, rcx
0x180032e85  jz      short loc_180032E8D
0x180032e87  call    cs:__imp_LocalFree
0x180032e8d  mov     [rsp+488h+var_3E8], r14
0x180032e95  mov     dword ptr [rsp+488h+var_3A0], r14d
0x180032e9d  xorps   xmm0, xmm0
0x180032ea0  movups  xmmword ptr [rsp+488h+var_98], xmm0
0x180032ea8  lea     rcx, [rsp+488h+var_88]
  ... truncated ...
```
