# ModernDeployment::Autopilot::Core::CryptoWrappers::CreateSelfSignedCert(ModernDeployment::Autopilot::Core::NcryptKeyData &,__int64,__int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>> &)

- ea: `0x18015dbd4`
- end: `0x18015e2ee`
- name: `?CreateSelfSignedCert@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEAVNcryptKeyData@234@_J1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1818`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18013aff8`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006dfb8`
- `0x18006e89c`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x180081330`
- `0x1800839bc`
- `0x18008e328`
- `0x1800a13a4`
- `0x18015d7f0`
- `0x18015d85c`
- `0x18015dbd4`
- `0x18015e2f4`
- `0x18015e3f0`
- `0x18015e4f8`
- `0x18015e600`
- `0x18015eaec`
- `0x18015ee48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015e20c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015e20c`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18015e191`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18015e191`

## string_xrefs

- `0x18015dc2d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015dc5e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015dd16`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015dda0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015de00`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015de65`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015df2e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015dfb4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015e230`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015e289`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015e2ae`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`

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
0x18015dbd4  push    rbx
0x18015dbd6  push    rsi
0x18015dbd7  push    rdi
0x18015dbd8  push    r12
0x18015dbda  push    r13
0x18015dbdc  push    r14
0x18015dbde  push    r15
0x18015dbe0  sub     rsp, 2B0h
0x18015dbe7  mov     rax, cs:__security_cookie
0x18015dbee  xor     rax, rsp
0x18015dbf1  mov     [rsp+2E8h+var_48], rax
0x18015dbf9  mov     rsi, r9
0x18015dbfc  mov     r15, r8
0x18015dbff  mov     rbx, rcx
0x18015dc02  mov     r14, [rsp+2E8h+arg_28]
0x18015dc0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18015dc11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18015dc16  xor     r13d, r13d
0x18015dc19  test    al, al
0x18015dc1b  jnz     short loc_18015DC45
0x18015dc1d  mov     rcx, [rsp+2E8h]; this
0x18015dc25  mov     ebx, 80004001h
0x18015dc2a  mov     r9d, ebx; char *
0x18015dc2d  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015dc34  mov     edx, 2F5h; void *
0x18015dc39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015dc3e  mov     eax, ebx
0x18015dc40  jmp     loc_18015E2CA
0x18015dc45  cmp     [rbx+0BCh], r13b
0x18015dc4c  jnz     short loc_18015DC76
0x18015dc4e  mov     rcx, [rsp+2E8h]; this
0x18015dc56  mov     ebx, 80070057h
0x18015dc5b  mov     r9d, ebx; char *
0x18015dc5e  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015dc65  mov     edx, 2F8h; void *
0x18015dc6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015dc6f  mov     eax, ebx
0x18015dc71  jmp     loc_18015E2CA
0x18015dc76  mov     rax, [rbx+10h]
0x18015dc7a  test    rax, rax
0x18015dc7d  jz      loc_18015E29E
0x18015dc83  cmp     [rax], r13
0x18015dc86  jz      loc_18015E29E
0x18015dc8c  mov     rax, [rbx]
0x18015dc8f  test    rax, rax
0x18015dc92  jz      loc_18015E279
0x18015dc98  cmp     [rax], r13
0x18015dc9b  jz      loc_18015E279
0x18015dca1  lea     rdx, aCn; "CN="
0x18015dca8  lea     rcx, [rsp+2E8h+var_288]
0x18015dcad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18015dcb2  nop
0x18015dcb3  lea     r12, [rbx+20h]
0x18015dcb7  mov     r8, r12
0x18015dcba  mov     rdx, rax
0x18015dcbd  lea     rcx, [rsp+2E8h+var_1F0]
0x18015dcc5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18015dcca  nop
0x18015dccb  lea     rcx, [rsp+2E8h+var_288]
0x18015dcd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015dcd5  xorps   xmm0, xmm0
0x18015dcd8  movups  xmmword ptr [rsp+2E8h+pSubjectIssuerBlob.cbData], xmm0
0x18015dce0  mov     [rsp+2E8h+var_210], r13
0x18015dce8  lea     r9, [rsp+2E8h+var_210]
0x18015dcf0  lea     r8, [rsp+2E8h+pSubjectIssuerBlob]
0x18015dcf8  lea     rcx, [rsp+2E8h+var_1F0]
0x18015dd00  call    ?EncodeCertStringToName@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAU_CRYPTOAPI_BLOB@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@5@@Z; ModernDeployment::Autopilot::Core::EncodeCertStringToName(std::wstring const &,ulong,_CRYPTOAPI_BLOB &,std::unique_ptr<uchar [0]> &)
0x18015dd05  mov     edi, eax
0x18015dd07  test    eax, eax
0x18015dd09  jns     short loc_18015DD4A
0x18015dd0b  mov     rcx, [rsp+2E8h]; this
0x18015dd13  mov     r9d, eax; char *
0x18015dd16  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015dd1d  mov     edx, 302h; void *
0x18015dd22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015dd27  nop
0x18015dd28  lea     rcx, [rsp+2E8h+var_210]
0x18015dd30  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015dd35  nop
0x18015dd36  lea     rcx, [rsp+2E8h+var_1F0]
0x18015dd3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015dd43  mov     eax, edi
0x18015dd45  jmp     loc_18015E2CA
0x18015dd4a  xorps   xmm0, xmm0
0x18015dd4d  xor     eax, eax
0x18015dd4f  movups  xmmword ptr [rsp+2E8h+var_228.pszObjId], xmm0
0x18015dd57  mov     [rsp+2E8h+var_228.Parameters.pbData], rax
0x18015dd5f  lea     rcx, [rbx+40h]
0x18015dd63  call    ?GetCertSigningAlgorithmOid@Core@Autopilot@ModernDeployment@@YAPEBDAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::GetCertSigningAlgorithmOid(std::wstring const &)
0x18015dd68  mov     [rsp+2E8h+var_228.pszObjId], rax
0x18015dd70  xorps   xmm0, xmm0
0x18015dd73  movups  xmmword ptr [rsp+2E8h+var_1C0.wYear], xmm0
0x18015dd7b  lea     rdx, [rsp+2E8h+var_1C0]; __int64
0x18015dd83  mov     rcx, 0FFFFFFFFFD6CD200h; this
0x18015dd8a  call    ?GetSystemTimeWithDeltaMilliseconds@Core@Autopilot@ModernDeployment@@YAJ_JAEAU_SYSTEMTIME@@@Z; ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(__int64,_SYSTEMTIME &)
0x18015dd8f  mov     ebx, eax
0x18015dd91  test    eax, eax
0x18015dd93  jns     short loc_18015DDD4
0x18015dd95  mov     rcx, [rsp+2E8h]; this
0x18015dd9d  mov     r9d, eax; char *
0x18015dda0  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015dda7  mov     edx, 30Bh; void *
0x18015ddac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015ddb1  nop
0x18015ddb2  lea     rcx, [rsp+2E8h+var_210]
0x18015ddba  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015ddbf  nop
0x18015ddc0  lea     rcx, [rsp+2E8h+var_1F0]
0x18015ddc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015ddcd  mov     eax, ebx
0x18015ddcf  jmp     loc_18015E2CA
0x18015ddd4  xorps   xmm0, xmm0
0x18015ddd7  movups  xmmword ptr [rsp+2E8h+var_1D0.wYear], xmm0
0x18015dddf  lea     rdx, [rsp+2E8h+var_1D0]; __int64
0x18015dde7  mov     rcx, r15; this
0x18015ddea  call    ?GetSystemTimeWithDeltaMilliseconds@Core@Autopilot@ModernDeployment@@YAJ_JAEAU_SYSTEMTIME@@@Z; ModernDeployment::Autopilot::Core::GetSystemTimeWithDeltaMilliseconds(__int64,_SYSTEMTIME &)
0x18015ddef  mov     ebx, eax
0x18015ddf1  test    eax, eax
0x18015ddf3  jns     short loc_18015DE34
0x18015ddf5  mov     rcx, [rsp+2E8h]; this
0x18015ddfd  mov     r9d, eax; char *
0x18015de00  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015de07  mov     edx, 30Eh; void *
0x18015de0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015de11  nop
0x18015de12  lea     rcx, [rsp+2E8h+var_210]
0x18015de1a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015de1f  nop
0x18015de20  lea     rcx, [rsp+2E8h+var_1F0]
0x18015de28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015de2d  mov     eax, ebx
0x18015de2f  jmp     loc_18015E2CA
0x18015de34  xorps   xmm0, xmm0
0x18015de37  movups  xmmword ptr [rsp+2E8h+var_180], xmm0
0x18015de3f  movups  [rsp+2E8h+var_170], xmm0
0x18015de47  lea     rdx, [rsp+2E8h+var_180]; unsigned __int8
0x18015de4f  call    ?EncodeKeyUsageExtension@Core@Autopilot@ModernDeployment@@YAJEAEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeKeyUsageExtension(uchar,_CERT_EXTENSION &)
0x18015de54  mov     ebx, eax
0x18015de56  test    eax, eax
0x18015de58  jns     short loc_18015DE99
0x18015de5a  mov     rcx, [rsp+2E8h]; this
0x18015de62  mov     r9d, eax; char *
0x18015de65  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015de6c  mov     edx, 313h; void *
0x18015de71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015de76  nop
0x18015de77  lea     rcx, [rsp+2E8h+var_210]
0x18015de7f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015de84  nop
0x18015de85  lea     rcx, [rsp+2E8h+var_1F0]
0x18015de8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015de92  mov     eax, ebx
0x18015de94  jmp     loc_18015E2CA
0x18015de99  xorps   xmm0, xmm0
0x18015de9c  movups  [rsp+2E8h+var_160], xmm0
0x18015dea4  movups  [rsp+2E8h+var_150], xmm0
0x18015deac  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x18015deb3  mov     [rsp+2E8h+var_288], rax
0x18015deb8  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x18015debf  mov     [rsp+2E8h+var_280], rax
0x18015dec4  movdqu  [rsp+2E8h+var_208], xmm0
0x18015decd  mov     [rsp+2E8h+var_1F8], r13
0x18015ded5  lea     rax, [rsp+2E8h+var_278]
0x18015deda  mov     [rsp+2E8h+var_290], rax
0x18015dedf  lea     rax, [rsp+2E8h+var_288]
0x18015dee4  mov     [rsp+2E8h+var_2A8], rax
0x18015dee9  lea     r9, [rsp+2E8h+var_290]
0x18015deee  lea     r8, [rsp+2E8h+var_2A8]
0x18015def3  mov     edi, 2
0x18015def8  mov     edx, edi
0x18015defa  lea     rcx, [rsp+2E8h+var_208]
0x18015df02  call    ??$_Construct_n@PEBQEBDPEBQEBD@?$vector@PEBDV?$allocator@PEBD@std@@@std@@AEAAX_K$$QEAPEBQEBD1@Z; std::vector<char const *>::_Construct_n<char const * const *,char const * const *>(unsigned __int64,char const * const * &&,char const * const * &&)
0x18015df07  nop
0x18015df08  lea     rdx, [rsp+2E8h+var_160]
0x18015df10  lea     rcx, [rsp+2E8h+var_208]
0x18015df18  call    ?EncodeEkuExtension@Core@Autopilot@ModernDeployment@@YAJAEBV?$vector@PEBDV?$allocator@PEBD@std@@@std@@AEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeEkuExtension(std::vector<char const *> const &,_CERT_EXTENSION &)
0x18015df1d  mov     ebx, eax
0x18015df1f  test    eax, eax
0x18015df21  jns     short loc_18015DF70
0x18015df23  mov     rcx, [rsp+2E8h]; this
0x18015df2b  mov     r9d, eax; char *
0x18015df2e  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015df35  mov     edx, 318h; void *
0x18015df3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015df3f  nop
0x18015df40  lea     rcx, [rsp+2E8h+var_208]
0x18015df48  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x18015df4d  nop
0x18015df4e  lea     rcx, [rsp+2E8h+var_210]
0x18015df56  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015df5b  nop
0x18015df5c  lea     rcx, [rsp+2E8h+var_1F0]
0x18015df64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015df69  mov     eax, ebx
0x18015df6b  jmp     loc_18015E2CA
0x18015df70  xorps   xmm4, xmm4
0x18015df73  movups  [rsp+2E8h+var_1A0], xmm4
0x18015df7b  xorps   xmm5, xmm5
0x18015df7e  movups  [rsp+2E8h+var_190], xmm5
0x18015df86  cmp     [rsi+10h], r13
0x18015df8a  jz      short loc_18015E006
0x18015df8c  lea     r8, [rsp+2E8h+var_1A0]
0x18015df94  mov     edx, [rsp+2E8h+arg_20]
0x18015df9b  mov     rcx, rsi
0x18015df9e  call    ?EncodeRsaPssExtension@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAU_CERT_EXTENSION@@@Z; ModernDeployment::Autopilot::Core::EncodeRsaPssExtension(std::wstring const &,ulong,_CERT_EXTENSION &)
0x18015dfa3  mov     ebx, eax
0x18015dfa5  test    eax, eax
0x18015dfa7  jns     short loc_18015DFF6
0x18015dfa9  mov     rcx, [rsp+2E8h]; this
0x18015dfb1  mov     r9d, eax; char *
0x18015dfb4  lea     r8, aOnecoreuapAdmi_121; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015dfbb  mov     edx, 31Eh; void *
0x18015dfc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015dfc5  nop
0x18015dfc6  lea     rcx, [rsp+2E8h+var_208]
0x18015dfce  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x18015dfd3  nop
0x18015dfd4  lea     rcx, [rsp+2E8h+var_210]
0x18015dfdc  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18015dfe1  nop
0x18015dfe2  lea     rcx, [rsp+2E8h+var_1F0]
0x18015dfea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015dfef  mov     eax, ebx
0x18015dff1  jmp     loc_18015E2CA
0x18015dff6  movups  xmm5, [rsp+2E8h+var_190]
0x18015dffe  movups  xmm4, [rsp+2E8h+var_1A0]
0x18015e006  movups  xmm3, xmmword ptr [rsp+2E8h+var_180]
0x18015e00e  movaps  [rsp+2E8h+var_138], xmm3
0x18015e016  movups  xmm2, [rsp+2E8h+var_170]
0x18015e01e  movaps  [rsp+2E8h+var_128], xmm2
0x18015e026  movups  xmm1, [rsp+2E8h+var_160]
0x18015e02e  movaps  [rsp+2E8h+var_118], xmm1
0x18015e036  movups  xmm0, [rsp+2E8h+var_150]
0x18015e03e  movaps  [rsp+2E8h+var_108], xmm0
0x18015e046  movaps  [rsp+2E8h+var_F8], xmm3
0x18015e04e  movaps  [rsp+2E8h+var_E8], xmm2
0x18015e056  movaps  [rsp+2E8h+var_D8], xmm1
0x18015e05e  movaps  [rsp+2E8h+var_C8], xmm0
0x18015e066  movaps  [rsp+2E8h+var_B8], xmm4
0x18015e06e  movaps  [rsp+2E8h+var_A8], xmm5
0x18015e076  mov     dword ptr [rsp+2E8h+var_268+4], r13d
0x18015e07e  cmp     [rsi+10h], r13
0x18015e082  jz      short loc_18015E099
0x18015e084  mov     [rsp+2E8h+var_268.cExtension], 3
0x18015e08f  lea     rax, [rsp+2E8h+var_F8]
0x18015e097  jmp     short loc_18015E0A8
0x18015e099  mov     [rsp+2E8h+var_268.cExtension], edi
0x18015e0a0  lea     rax, [rsp+2E8h+var_138]
0x18015e0a8  mov     [rsp+2E8h+var_268.rgExtension], rax
0x18015e0b0  movaps  xmm0, xmmword ptr cs:pszProviderName; "Microsoft Platform Crypto Provider"
0x18015e0b7  movaps  [rsp+2E8h+var_98], xmm0
0x18015e0bf  movaps  xmm1, xmmword ptr cs:pszProviderName+10h; "t Platform Crypto Provider"
0x18015e0c6  movaps  [rsp+2E8h+var_88], xmm1
0x18015e0ce  movaps  xmm0, xmmword ptr cs:pszProviderName+20h; "rm Crypto Provider"
0x18015e0d5  movaps  [rsp+2E8h+var_78], xmm0
0x18015e0dd  movaps  xmm1, xmmword ptr cs:pszProviderName+30h; "o Provider"
0x18015e0e4  movaps  xmmword ptr [rsp+2E8h+var_68], xmm1
0x18015e0ec  movsd   xmm0, qword ptr cs:pszProviderName+3Eh; "der"
0x18015e0f4  movsd   qword ptr [rsp+2E8h+var_68+0Eh], xmm0
0x18015e0fd  mov     qword ptr [rsp+2E8h+pKeyProvInfo.cProvParam], r13
0x18015e105  mov     qword ptr [rsp+2E8h+pKeyProvInfo.dwKeySpec], r13
0x18015e10d  mov     rcx, r12
0x18015e110  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18015e115  mov     [rsp+2E8h+pKeyProvInfo.pwszContainerName], rax
0x18015e11d  lea     rax, [rsp+2E8h+var_98]
0x18015e125  mov     [rsp+2E8h+pKeyProvInfo.pwszProvName], rax
0x18015e12d  mov     [rsp+2E8h+pKeyProvInfo.dwProvType], r13d
0x18015e135  mov     [rsp+2E8h+pKeyProvInfo.dwFlags], 60h ; '`'
0x18015e140  mov     [rsp+2E8h+pKeyProvInfo.rgProvParam], r13
0x18015e148  lea     rax, [rsp+2E8h+var_268]
0x18015e150  mov     [rsp+2E8h+pExtensions], rax; pExtensions
0x18015e155  lea     rax, [rsp+2E8h+var_1D0]
0x18015e15d  mov     [rsp+2E8h+pEndTime], rax; pEndTime
0x18015e162  lea     rax, [rsp+2E8h+var_1C0]
0x18015e16a  mov     [rsp+2E8h+pStartTime], rax; pStartTime
0x18015e16f  lea     rax, [rsp+2E8h+var_228]
0x18015e177  mov     [rsp+2E8h+pSignatureAlgorithm], rax; int
0x18015e17c  lea     r9, [rsp+2E8h+pKeyProvInfo]; pKeyProvInfo
0x18015e184  xor     r8d, r8d; dwFlags
0x18015e187  lea     rdx, [rsp+2E8h+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x18015e18f  xor     ecx, ecx; hCryptProvOrNCryptKey
0x18015e191  call    cs:__imp_CertCreateSelfSignCertificate
0x18015e197  mov     [rsp+2E8h+var_2A8], rax
0x18015e19c  lea     rdx, [rsp+2E8h+var_2A8]
0x18015e1a1  lea     rcx, [rsp+2E8h+var_2A0]
0x18015e1a6  call    ??$?0PEBU_CERT_CONTEXT@@@?$shared_any_t@V?$shared_storage@V?$unique_any_t@Ucert_context_t@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAPEBU_CERT_CONTEXT@@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::cert_context_t>>>(_CERT_CONTEXT const * &&)
0x18015e1ab  mov     rax, [rsp+2E8h+var_2A0]
0x18015e1b0  test    rax, rax
0x18015e1b3  jz      short loc_18015E20C
0x18015e1b5  cmp     [rax], r13
0x18015e1b8  jz      short loc_18015E20C
0x18015e1ba  lea     rax, [rsp+2E8h+var_2A0]
0x18015e1bf  cmp     r14, rax
0x18015e1c2  jz      short loc_18015E1D1
0x18015e1c4  lea     rdx, [rsp+2E8h+var_2A0]
0x18015e1c9  mov     rcx, r14
0x18015e1cc  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18015e1d1  lea     rcx, [rsp+2E8h+var_2A0]
0x18015e1d6  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18015e1db  nop
  ... truncated ...
```
