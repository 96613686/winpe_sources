# ModernDeployment::Autopilot::Core::CryptoWrappers::CreateSelfSignedCert(ModernDeployment::Autopilot::Core::NcryptKeyData &,__int64,__int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>> &)

- ea: `0x180161f04`
- end: `0x18016262a`
- name: `?CreateSelfSignedCert@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEAVNcryptKeyData@234@_J1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1830`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18013f04c`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e508`
- `0x18006ee48`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081db0`
- `0x180084574`
- `0x18008f458`
- `0x1800a29ac`
- `0x180161b20`
- `0x180161b90`
- `0x180161f04`
- `0x180162630`
- `0x18016273c`
- `0x18016284c`
- `0x18016295c`
- `0x180162e6c`
- `0x1801631d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162542`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x1801624c1`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x1801624c1`

## string_xrefs

- `0x180161f5d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180161f8e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180162046`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x1801620d0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180162130`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180162195`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18016225e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x1801622e4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18016256c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x1801625c5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x1801625ea`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::CryptoWrappers::CreateSelfSignedCert(
        __int64 a1,
        __int64 a2,
        ModernDeployment::Autopilot::Core *a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6)
{
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // edi
  struct _SYSTEMTIME *v16; // r8
  int SystemTimeWithDeltaMilliseconds; // eax
  struct _SYSTEMTIME *v18; // r8
  unsigned int v19; // ebx
  int v20; // eax
  ModernDeployment::Autopilot::Core *v21; // rcx
  struct _CERT_EXTENSION *v22; // r8
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  __int128 v28; // xmm4
  __int128 v29; // xmm5
  int v30; // eax
  unsigned int v31; // ebx
  struct _CERT_EXTENSION *v32; // rax
  signed int LastError; // eax
  unsigned int v34; // ebx
  int pSignatureAlgorithm; // [rsp+20h] [rbp-2C8h]
  int pSignatureAlgorithma; // [rsp+20h] [rbp-2C8h]
  PCCERT_CONTEXT v37; // [rsp+40h] [rbp-2A8h] BYREF
  _QWORD v38[2]; // [rsp+48h] [rbp-2A0h] BYREF
  char *v39; // [rsp+58h] [rbp-290h] BYREF
  _QWORD v40[2]; // [rsp+60h] [rbp-288h] BYREF
  char v41; // [rsp+70h] [rbp-278h] BYREF
  struct _CERT_EXTENSIONS pExtensions; // [rsp+80h] [rbp-268h] BYREF
  _CRYPT_KEY_PROV_INFO pKeyProvInfo; // [rsp+90h] [rbp-258h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER v44; // [rsp+C0h] [rbp-228h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-210h] BYREF
  __int128 v46; // [rsp+E0h] [rbp-208h] BYREF
  __int64 v47; // [rsp+F0h] [rbp-1F8h]
  _BYTE v48[32]; // [rsp+F8h] [rbp-1F0h] BYREF
  struct _SYSTEMTIME pEndTime; // [rsp+118h] [rbp-1D0h] BYREF
  struct _SYSTEMTIME pStartTime; // [rsp+128h] [rbp-1C0h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+138h] [rbp-1B0h] BYREF
  __int128 v52; // [rsp+148h] [rbp-1A0h] BYREF
  __int128 v53; // [rsp+158h] [rbp-190h]
  unsigned __int8 v54[16]; // [rsp+168h] [rbp-180h] BYREF
  __int128 v55; // [rsp+178h] [rbp-170h]
  __int128 v56; // [rsp+188h] [rbp-160h] BYREF
  __int128 v57; // [rsp+198h] [rbp-150h]
  _OWORD v58[4]; // [rsp+1B0h] [rbp-138h] BYREF
  _OWORD v59[6]; // [rsp+1F0h] [rbp-F8h] BYREF
  _OWORD v60[3]; // [rsp+250h] [rbp-98h] BYREF
  _OWORD v61[2]; // [rsp+280h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
      (const char *)0x80004001LL,
      pSignatureAlgorithm);
    return 2147500033LL;
  }
  if ( !*(_BYTE *)(a1 + 188) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
      (const char *)0x80070057LL,
      pSignatureAlgorithm);
    return 2147942487LL;
  }
  v10 = *(_QWORD **)(a1 + 16);
  if ( v10 && *v10 )
  {
    if ( *(_QWORD *)a1 && **(_QWORD **)a1 )
    {
      v11 = std::wstring::wstring(v40, L"CN=");
      v12 = a1 + 32;
      std::operator+<unsigned short>(v48, v11, a1 + 32);
      std::wstring::_Tidy_deallocate(v40);
      pSubjectIssuerBlob = 0;
      v45 = 0;
      v14 = ModernDeployment::Autopilot::Core::EncodeCertStringToName(v48, v13, &pSubjectIssuerBlob, &v45);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x302,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
          (const char *)(unsigned int)v14,
          pSignatureAlgorithm);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v15;
      }
      memset(&v44, 0, sizeof(v44));
      v44.pszObjId = (LPSTR)ModernDeployment::Autopilot::Core::GetCertSigningAlgorithmOid(a1 + 64);
      pStartTime = 0;
      SystemTimeWithDeltaMilliseconds = ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(
                                          (ModernDeployment::Autopilot::Core *)0xFFFFFFFFFD6CD200LL,
                                          (__int64)&pStartTime,
                                          v16);
      v19 = SystemTimeWithDeltaMilliseconds;
      if ( SystemTimeWithDeltaMilliseconds < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30B,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
          (const char *)(unsigned int)SystemTimeWithDeltaMilliseconds,
          pSignatureAlgorithm);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v19;
      }
      pEndTime = 0;
      v20 = ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(a3, (__int64)&pEndTime, v18);
      v23 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
          (const char *)(unsigned int)v20,
          pSignatureAlgorithm);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v23;
      }
      *(_OWORD *)v54 = 0;
      v55 = 0;
      v24 = ModernDeployment::Autopilot::Core::EncodeKeyUsageExtension(v21, (unsigned __int8)v54, v22);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x313,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
          (const char *)(unsigned int)v24,
          pSignatureAlgorithm);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v25;
      }
      v56 = 0;
      v57 = 0;
      v40[0] = "1.3.6.1.5.5.7.3.2";
      v40[1] = "1.3.6.1.5.5.7.3.1";
      v46 = 0;
      v47 = 0;
      v39 = &v41;
      v37 = (PCCERT_CONTEXT)v40;
      std::vector<char const *>::_Construct_n<char const * const *,char const * const *>(&v46, 2, &v37, &v39);
      v26 = ModernDeployment::Autopilot::Core::EncodeEkuExtension(&v46, &v56);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x318,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
          (const char *)(unsigned int)v26,
          pSignatureAlgorithm);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v46);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v27;
      }
      v28 = 0;
      v52 = 0;
      v29 = 0;
      v53 = 0;
      if ( *(_QWORD *)(a4 + 16) )
      {
        v30 = ModernDeployment::Autopilot::Core::EncodeRsaPssExtension(a4, a5, &v52);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x31E,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
            (const char *)(unsigned int)v30,
            pSignatureAlgorithm);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v46);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
          std::wstring::_Tidy_deallocate(v48);
          return v31;
        }
        v29 = v53;
        v28 = v52;
      }
      v58[0] = *(_OWORD *)v54;
      v58[1] = v55;
      v58[2] = v56;
      v58[3] = v57;
      v59[0] = *(_OWORD *)v54;
      v59[1] = v55;
      v59[2] = v56;
      v59[3] = v57;
      v59[4] = v28;
      v59[5] = v29;
      *(&pExtensions.cExtension + 1) = 0;
      if ( *(_QWORD *)(a4 + 16) )
      {
        pExtensions.cExtension = 3;
        v32 = (struct _CERT_EXTENSION *)v59;
      }
      else
      {
        pExtensions.cExtension = 2;
        v32 = (struct _CERT_EXTENSION *)v58;
      }
      pExtensions.rgExtension = v32;
      v60[0] = *(_OWORD *)L"Microsoft Platform Crypto Provider";
      v60[1] = *(_OWORD *)L"t Platform Crypto Provider";
      v60[2] = *(_OWORD *)L"rm Crypto Provider";
      v61[0] = *(_OWORD *)L"o Provider";
      *(_QWORD *)((char *)v61 + 14) = *(_QWORD *)L"der";
      *(_QWORD *)&pKeyProvInfo.cProvParam = 0;
      *(_QWORD *)&pKeyProvInfo.dwKeySpec = 0;
      pKeyProvInfo.pwszContainerName = (LPWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
      pKeyProvInfo.pwszProvName = (LPWSTR)v60;
      pKeyProvInfo.dwProvType = 0;
      pKeyProvInfo.dwFlags = 96;
      pKeyProvInfo.rgProvParam = 0;
      v37 = CertCreateSelfSignCertificate(
              0,
              &pSubjectIssuerBlob,
              0,
              &pKeyProvInfo,
              &v44,
              &pStartTime,
              &pEndTime,
              &pExtensions);
      wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>(
        v38,
        &v37);
      if ( v38[0] && *(_QWORD *)v38[0] )
      {
        if ( a6 != v38 )
          std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(a6, v38);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v38);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v46);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v34 = LastError;
        if ( LastError > 0 )
          v34 = (unsigned __int16)LastError | 0x80070000;
        if ( (v34 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x349,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
            (const char *)v34,
            pSignatureAlgorithma);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v38);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v46);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
        std::wstring::_Tidy_deallocate(v48);
        return v34;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
        (const char *)0x80070057LL,
        pSignatureAlgorithm);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\cryptowrappers.cpp",
      (const char *)0x80070057LL,
      pSignatureAlgorithm);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180161f04  push    rbx
0x180161f06  push    rsi
0x180161f07  push    rdi
0x180161f08  push    r12
0x180161f0a  push    r13
0x180161f0c  push    r14
0x180161f0e  push    r15
0x180161f10  sub     rsp, 2B0h
0x180161f17  mov     rax, cs:__security_cookie
0x180161f1e  xor     rax, rsp
0x180161f21  mov     [rsp+2E8h+var_48], rax
0x180161f29  mov     rsi, r9
0x180161f2c  mov     r15, r8
0x180161f2f  mov     rbx, rcx
0x180161f32  mov     r14, [rsp+2E8h+arg_28]
0x180161f3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180161f41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180161f46  xor     r13d, r13d
0x180161f49  test    al, al
0x180161f4b  jnz     short loc_180161F75
0x180161f4d  mov     rcx, [rsp+2E8h]; this
0x180161f55  mov     ebx, 80004001h
0x180161f5a  mov     r9d, ebx; char *
0x180161f5d  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x180161f64  mov     edx, 2F5h; void *
0x180161f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161f6e  mov     eax, ebx
0x180161f70  jmp     loc_180162606
0x180161f75  cmp     [rbx+0BCh], r13b
0x180161f7c  jnz     short loc_180161FA6
0x180161f7e  mov     rcx, [rsp+2E8h]; this
0x180161f86  mov     ebx, 80070057h
0x180161f8b  mov     r9d, ebx; char *
0x180161f8e  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x180161f95  mov     edx, 2F8h; void *
0x180161f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161f9f  mov     eax, ebx
0x180161fa1  jmp     loc_180162606
0x180161fa6  mov     rax, [rbx+10h]
0x180161faa  test    rax, rax
0x180161fad  jz      loc_1801625DA
0x180161fb3  cmp     [rax], r13
0x180161fb6  jz      loc_1801625DA
0x180161fbc  mov     rax, [rbx]
0x180161fbf  test    rax, rax
0x180161fc2  jz      loc_1801625B5
0x180161fc8  cmp     [rax], r13
0x180161fcb  jz      loc_1801625B5
0x180161fd1  lea     rdx, aCn; "CN="
0x180161fd8  lea     rcx, [rsp+2E8h+var_288]
0x180161fdd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180161fe2  nop
0x180161fe3  lea     r12, [rbx+20h]
0x180161fe7  mov     r8, r12
0x180161fea  mov     rdx, rax
0x180161fed  lea     rcx, [rsp+2E8h+var_1F0]
0x180161ff5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180161ffa  nop
0x180161ffb  lea     rcx, [rsp+2E8h+var_288]
0x180162000  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180162005  xorps   xmm0, xmm0
0x180162008  movups  xmmword ptr [rsp+2E8h+pSubjectIssuerBlob.cbData], xmm0
0x180162010  mov     [rsp+2E8h+var_210], r13
0x180162018  lea     r9, [rsp+2E8h+var_210]
0x180162020  lea     r8, [rsp+2E8h+pSubjectIssuerBlob]
0x180162028  lea     rcx, [rsp+2E8h+var_1F0]
0x180162030  call    ?EncodeCertStringToName@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAU_CRYPTOAPI_BLOB@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@5@@Z; ModernDeployment::Autopilot::Core::EncodeCertStringToName(std::wstring const &,ulong,_CRYPTOAPI_BLOB &,std::unique_ptr<uchar [0]> &)
0x180162035  mov     edi, eax
0x180162037  test    eax, eax
0x180162039  jns     short loc_18016207A
0x18016203b  mov     rcx, [rsp+2E8h]; this
0x180162043  mov     r9d, eax; char *
0x180162046  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016204d  mov     edx, 302h; void *
0x180162052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180162057  nop
0x180162058  lea     rcx, [rsp+2E8h+var_210]
0x180162060  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180162065  nop
0x180162066  lea     rcx, [rsp+2E8h+var_1F0]
0x18016206e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180162073  mov     eax, edi
0x180162075  jmp     loc_180162606
0x18016207a  xorps   xmm0, xmm0
0x18016207d  xor     eax, eax
0x18016207f  movups  xmmword ptr [rsp+2E8h+var_228.pszObjId], xmm0
0x180162087  mov     [rsp+2E8h+var_228.Parameters.pbData], rax
0x18016208f  lea     rcx, [rbx+40h]
0x180162093  call    ?GetCertSigningAlgorithmOid@Core@Autopilot@ModernDeployment@@YAPEBDAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::GetCertSigningAlgorithmOid(std::wstring const &)
0x180162098  mov     [rsp+2E8h+var_228.pszObjId], rax
0x1801620a0  xorps   xmm0, xmm0
0x1801620a3  movups  xmmword ptr [rsp+2E8h+var_1C0.wYear], xmm0
0x1801620ab  lea     rdx, [rsp+2E8h+var_1C0]; __int64
0x1801620b3  mov     rcx, 0FFFFFFFFFD6CD200h; this
0x1801620ba  call    ?GetSystemTimeWithDeltaMilliseconds@Core@Autopilot@ModernDeployment@@YAJ_JAEAU_SYSTEMTIME@@@Z; ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(__int64,_SYSTEMTIME &)
0x1801620bf  mov     ebx, eax
0x1801620c1  test    eax, eax
0x1801620c3  jns     short loc_180162104
0x1801620c5  mov     rcx, [rsp+2E8h]; this
0x1801620cd  mov     r9d, eax; char *
0x1801620d0  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801620d7  mov     edx, 30Bh; void *
0x1801620dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801620e1  nop
0x1801620e2  lea     rcx, [rsp+2E8h+var_210]
0x1801620ea  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801620ef  nop
0x1801620f0  lea     rcx, [rsp+2E8h+var_1F0]
0x1801620f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801620fd  mov     eax, ebx
0x1801620ff  jmp     loc_180162606
0x180162104  xorps   xmm0, xmm0
0x180162107  movups  xmmword ptr [rsp+2E8h+var_1D0.wYear], xmm0
0x18016210f  lea     rdx, [rsp+2E8h+var_1D0]; __int64
0x180162117  mov     rcx, r15; this
0x18016211a  call    ?GetSystemTimeWithDeltaMilliseconds@Core@Autopilot@ModernDeployment@@YAJ_JAEAU_SYSTEMTIME@@@Z; ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(__int64,_SYSTEMTIME &)
0x18016211f  mov     ebx, eax
0x180162121  test    eax, eax
0x180162123  jns     short loc_180162164
0x180162125  mov     rcx, [rsp+2E8h]; this
0x18016212d  mov     r9d, eax; char *
0x180162130  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x180162137  mov     edx, 30Eh; void *
0x18016213c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180162141  nop
0x180162142  lea     rcx, [rsp+2E8h+var_210]
0x18016214a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18016214f  nop
0x180162150  lea     rcx, [rsp+2E8h+var_1F0]
0x180162158  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016215d  mov     eax, ebx
0x18016215f  jmp     loc_180162606
0x180162164  xorps   xmm0, xmm0
0x180162167  movups  xmmword ptr [rsp+2E8h+var_180], xmm0
0x18016216f  movups  [rsp+2E8h+var_170], xmm0
0x180162177  lea     rdx, [rsp+2E8h+var_180]; unsigned __int8
0x18016217f  call    ?EncodeKeyUsageExtension@Core@Autopilot@ModernDeployment@@YAJEAEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeKeyUsageExtension(uchar,_CERT_EXTENSION &)
0x180162184  mov     ebx, eax
0x180162186  test    eax, eax
0x180162188  jns     short loc_1801621C9
0x18016218a  mov     rcx, [rsp+2E8h]; this
0x180162192  mov     r9d, eax; char *
0x180162195  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016219c  mov     edx, 313h; void *
0x1801621a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801621a6  nop
0x1801621a7  lea     rcx, [rsp+2E8h+var_210]
0x1801621af  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801621b4  nop
0x1801621b5  lea     rcx, [rsp+2E8h+var_1F0]
0x1801621bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801621c2  mov     eax, ebx
0x1801621c4  jmp     loc_180162606
0x1801621c9  xorps   xmm0, xmm0
0x1801621cc  movups  [rsp+2E8h+var_160], xmm0
0x1801621d4  movups  [rsp+2E8h+var_150], xmm0
0x1801621dc  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x1801621e3  mov     [rsp+2E8h+var_288], rax
0x1801621e8  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x1801621ef  mov     [rsp+2E8h+var_280], rax
0x1801621f4  movdqu  [rsp+2E8h+var_208], xmm0
0x1801621fd  mov     [rsp+2E8h+var_1F8], r13
0x180162205  lea     rax, [rsp+2E8h+var_278]
0x18016220a  mov     [rsp+2E8h+var_290], rax
0x18016220f  lea     rax, [rsp+2E8h+var_288]
0x180162214  mov     [rsp+2E8h+var_2A8], rax
0x180162219  lea     r9, [rsp+2E8h+var_290]
0x18016221e  lea     r8, [rsp+2E8h+var_2A8]
0x180162223  mov     edi, 2
0x180162228  mov     edx, edi
0x18016222a  lea     rcx, [rsp+2E8h+var_208]
0x180162232  call    ??$_Construct_n@PEBQEBDPEBQEBD@?$vector@PEBDV?$allocator@PEBD@std@@@std@@AEAAX_K$$QEAPEBQEBD1@Z; std::vector<char const *>::_Construct_n<char const * const *,char const * const *>(unsigned __int64,char const * const * &&,char const * const * &&)
0x180162237  nop
0x180162238  lea     rdx, [rsp+2E8h+var_160]
0x180162240  lea     rcx, [rsp+2E8h+var_208]
0x180162248  call    ?EncodeEkuExtension@Core@Autopilot@ModernDeployment@@YAJAEBV?$vector@PEBDV?$allocator@PEBD@std@@@std@@AEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeEkuExtension(std::vector<char const *> const &,_CERT_EXTENSION &)
0x18016224d  mov     ebx, eax
0x18016224f  test    eax, eax
0x180162251  jns     short loc_1801622A0
0x180162253  mov     rcx, [rsp+2E8h]; this
0x18016225b  mov     r9d, eax; char *
0x18016225e  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x180162265  mov     edx, 318h; void *
0x18016226a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016226f  nop
0x180162270  lea     rcx, [rsp+2E8h+var_208]
0x180162278  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x18016227d  nop
0x18016227e  lea     rcx, [rsp+2E8h+var_210]
0x180162286  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18016228b  nop
0x18016228c  lea     rcx, [rsp+2E8h+var_1F0]
0x180162294  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180162299  mov     eax, ebx
0x18016229b  jmp     loc_180162606
0x1801622a0  xorps   xmm4, xmm4
0x1801622a3  movups  [rsp+2E8h+var_1A0], xmm4
0x1801622ab  xorps   xmm5, xmm5
0x1801622ae  movups  [rsp+2E8h+var_190], xmm5
0x1801622b6  cmp     [rsi+10h], r13
0x1801622ba  jz      short loc_180162336
0x1801622bc  lea     r8, [rsp+2E8h+var_1A0]
0x1801622c4  mov     edx, [rsp+2E8h+arg_20]
0x1801622cb  mov     rcx, rsi
0x1801622ce  call    ?EncodeRsaPssExtension@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeRsaPssExtension(std::wstring const &,ulong,_CERT_EXTENSION &)
0x1801622d3  mov     ebx, eax
0x1801622d5  test    eax, eax
0x1801622d7  jns     short loc_180162326
0x1801622d9  mov     rcx, [rsp+2E8h]; this
0x1801622e1  mov     r9d, eax; char *
0x1801622e4  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801622eb  mov     edx, 31Eh; void *
0x1801622f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801622f5  nop
0x1801622f6  lea     rcx, [rsp+2E8h+var_208]
0x1801622fe  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x180162303  nop
0x180162304  lea     rcx, [rsp+2E8h+var_210]
0x18016230c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180162311  nop
0x180162312  lea     rcx, [rsp+2E8h+var_1F0]
0x18016231a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016231f  mov     eax, ebx
0x180162321  jmp     loc_180162606
0x180162326  movups  xmm5, [rsp+2E8h+var_190]
0x18016232e  movups  xmm4, [rsp+2E8h+var_1A0]
0x180162336  movups  xmm3, xmmword ptr [rsp+2E8h+var_180]
0x18016233e  movaps  [rsp+2E8h+var_138], xmm3
0x180162346  movups  xmm2, [rsp+2E8h+var_170]
0x18016234e  movaps  [rsp+2E8h+var_128], xmm2
0x180162356  movups  xmm1, [rsp+2E8h+var_160]
0x18016235e  movaps  [rsp+2E8h+var_118], xmm1
0x180162366  movups  xmm0, [rsp+2E8h+var_150]
0x18016236e  movaps  [rsp+2E8h+var_108], xmm0
0x180162376  movaps  [rsp+2E8h+var_F8], xmm3
0x18016237e  movaps  [rsp+2E8h+var_E8], xmm2
0x180162386  movaps  [rsp+2E8h+var_D8], xmm1
0x18016238e  movaps  [rsp+2E8h+var_C8], xmm0
0x180162396  movaps  [rsp+2E8h+var_B8], xmm4
0x18016239e  movaps  [rsp+2E8h+var_A8], xmm5
0x1801623a6  mov     dword ptr [rsp+2E8h+var_268+4], r13d
0x1801623ae  cmp     [rsi+10h], r13
0x1801623b2  jz      short loc_1801623C9
0x1801623b4  mov     [rsp+2E8h+var_268.cExtension], 3
0x1801623bf  lea     rax, [rsp+2E8h+var_F8]
0x1801623c7  jmp     short loc_1801623D8
0x1801623c9  mov     [rsp+2E8h+var_268.cExtension], edi
0x1801623d0  lea     rax, [rsp+2E8h+var_138]
0x1801623d8  mov     [rsp+2E8h+var_268.rgExtension], rax
0x1801623e0  movaps  xmm0, xmmword ptr cs:pszProviderName; "Microsoft Platform Crypto Provider"
0x1801623e7  movaps  [rsp+2E8h+var_98], xmm0
0x1801623ef  movaps  xmm1, xmmword ptr cs:pszProviderName+10h; "t Platform Crypto Provider"
0x1801623f6  movaps  [rsp+2E8h+var_88], xmm1
0x1801623fe  movaps  xmm0, xmmword ptr cs:pszProviderName+20h; "rm Crypto Provider"
0x180162405  movaps  [rsp+2E8h+var_78], xmm0
0x18016240d  movaps  xmm1, xmmword ptr cs:pszProviderName+30h; "o Provider"
0x180162414  movaps  xmmword ptr [rsp+2E8h+var_68], xmm1
0x18016241c  movsd   xmm0, qword ptr cs:pszProviderName+3Eh; "der"
0x180162424  movsd   qword ptr [rsp+2E8h+var_68+0Eh], xmm0
0x18016242d  mov     qword ptr [rsp+2E8h+pKeyProvInfo.cProvParam], r13
0x180162435  mov     qword ptr [rsp+2E8h+pKeyProvInfo.dwKeySpec], r13
0x18016243d  mov     rcx, r12
0x180162440  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180162445  mov     [rsp+2E8h+pKeyProvInfo.pwszContainerName], rax
0x18016244d  lea     rax, [rsp+2E8h+var_98]
0x180162455  mov     [rsp+2E8h+pKeyProvInfo.pwszProvName], rax
0x18016245d  mov     [rsp+2E8h+pKeyProvInfo.dwProvType], r13d
0x180162465  mov     [rsp+2E8h+pKeyProvInfo.dwFlags], 60h ; '`'
0x180162470  mov     [rsp+2E8h+pKeyProvInfo.rgProvParam], r13
0x180162478  lea     rax, [rsp+2E8h+var_268]
0x180162480  mov     [rsp+2E8h+pExtensions], rax; pExtensions
0x180162485  lea     rax, [rsp+2E8h+var_1D0]
0x18016248d  mov     [rsp+2E8h+pEndTime], rax; pEndTime
0x180162492  lea     rax, [rsp+2E8h+var_1C0]
0x18016249a  mov     [rsp+2E8h+pStartTime], rax; pStartTime
0x18016249f  lea     rax, [rsp+2E8h+var_228]
0x1801624a7  mov     [rsp+2E8h+pSignatureAlgorithm], rax; int
0x1801624ac  lea     r9, [rsp+2E8h+pKeyProvInfo]; pKeyProvInfo
0x1801624b4  xor     r8d, r8d; dwFlags
0x1801624b7  lea     rdx, [rsp+2E8h+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x1801624bf  xor     ecx, ecx; hCryptProvOrNCryptKey
0x1801624c1  call    cs:__imp_CertCreateSelfSignCertificate
0x1801624c8  nop     dword ptr [rax+rax+00h]
0x1801624cd  mov     [rsp+2E8h+var_2A8], rax
0x1801624d2  lea     rdx, [rsp+2E8h+var_2A8]
0x1801624d7  lea     rcx, [rsp+2E8h+var_2A0]
0x1801624dc  call    ??$?0PEBU_CERT_CONTEXT@@@?$shared_any_t@V?$shared_storage@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAPEBU_CERT_CONTEXT@@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>(_CERT_CONTEXT const * &&)
0x1801624e1  mov     rax, [rsp+2E8h+var_2A0]
0x1801624e6  test    rax, rax
0x1801624e9  jz      short loc_180162542
0x1801624eb  cmp     [rax], r13
0x1801624ee  jz      short loc_180162542
0x1801624f0  lea     rax, [rsp+2E8h+var_2A0]
0x1801624f5  cmp     r14, rax
0x1801624f8  jz      short loc_180162507
0x1801624fa  lea     rdx, [rsp+2E8h+var_2A0]
0x1801624ff  mov     rcx, r14
0x180162502  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x180162507  lea     rcx, [rsp+2E8h+var_2A0]
0x18016250c  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
  ... truncated ...
```
