# Protector::Bio::AuthenticateProtector(uchar const *,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800454b0`
- end: `0x1800459c1`
- name: `?AuthenticateProtector@Bio@Protector@@UEAAJPEBEKPEA_K1@Z`
- size: `1297`
- prototype: `__int64 __usercall@<rax>(Protector::Bio *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int64 *@<r9>, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180017f94`
- `0x180018418`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001d230`
- `0x18002d090`
- `0x18002d3f0`
- `0x18002dbac`
- `0x18002dc44`
- `0x18002dfd4`
- `0x18002e2e4`
- `0x180034878`
- `0x18003500c`
- `0x18003b778`
- `0x1800441b4`
- `0x18004469c`
- `0x1800446f8`
- `0x1800453b0`
- `0x1800454b0`
- `0x180045e04`
- `0x180047484`
- `0x180066934`
- `0x1800758fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800456b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800456cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004575f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800456b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800456cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004575f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045774`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045673`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180045673`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800456eb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800456eb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045701`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045701`
- `ntdll!RtlPublishWnfStateData` at `0x180045728`
- `ntdll!RtlPublishWnfStateData` at `0x180045728`
- `ext-ms-win-biometrics-winbio-core-l1-1-2!WinBioGetGestureMetadata` at `0x180045565`
- `ext-ms-win-biometrics-winbio-core-l1-1-2!WinBioGetGestureMetadata` at `0x180045565`

## string_xrefs

- `0x180045521`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x18004558c`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x180045690`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x18004573f`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x1800457d1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x18004581b`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x1800458c4`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x180045936`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Protector::Bio::AuthenticateProtector(
        Protector::Bio *this,
        const unsigned __int8 *a2,
        int a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  int GestureMetadata; // edi
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  NgcUtils *v14; // rcx
  __int64 v15; // r8
  const WCHAR *v16; // rax
  BOOL v17; // ebx
  const char *v18; // r9
  __int64 v19; // rdx
  int LastError; // eax
  HLOCAL v21; // rcx
  bool v22; // zf
  HLOCAL v23; // rcx
  DWORD LengthSid; // eax
  int v25; // eax
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  int updated; // eax
  int v29; // eax
  Properties::SecretStore *v30; // rcx
  Properties::SecretStore *v31; // rcx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int *v36; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v38; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v42[80]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v43[368]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[368]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v45[24]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v46[744]; // [rsp+398h] [rbp+298h] BYREF
  int v47[2]; // [rsp+680h] [rbp+580h] BYREF
  PSID Sid; // [rsp+688h] [rbp+588h] BYREF
  char v49; // [rsp+690h] [rbp+590h]
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  LogProvider::WatchCurrentThread(v42, "BioAuthenticateProtector");
  if ( a3 == 8 )
  {
    v10 = *(_QWORD *)a2;
    if ( !*(_QWORD *)a2 )
    {
      v9 = 733;
      goto LABEL_5;
    }
    v37 = 0;
    *(_QWORD *)v47 = &v37;
    Sid = 0;
    v49 = 1;
    GestureMetadata = WinBioGetGestureMetadata(v10, &Sid);
    wil::details::out_param_t<std::unique_ptr<_WINBIO_NGC_AUTHORIZATION,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_NGC_AUTHORIZATION,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>(v47);
    if ( GestureMetadata < 0 )
    {
      v12 = 736;
LABEL_8:
      v13 = (unsigned int)GestureMetadata;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
        (const char *)v13,
        (int)v36);
LABEL_10:
      std::unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>::~unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>(&v37);
      goto LABEL_55;
    }
    if ( *(_DWORD *)(v37 + 16) == 2 )
    {
      v40 = 0;
      GestureMetadata = Protector::Bio::AuthenticateSecureBioProtector(this, v10, &v40, a4, a5);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::GetImpl'::`2'::impl) )
      {
        if ( GestureMetadata == -2146893813 || GestureMetadata == -2146893808 )
        {
          if ( (Microsoft_Windows_HelloForBusinessEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(
              &MS_PROVIDER_HFB_Context,
              EVENT_HFB_BIOMETRICS_INVALID_SECUREBIO_PROTECTOR,
              v15,
              1);
          wil::make_unique_hlocal<_WINBIO_IDENTITY,>(&v38);
          *(_DWORD *)v38 = 3;
          hMem = 0;
          *(_QWORD *)v47 = &hMem;
          Sid = 0;
          v49 = 1;
          v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
          v17 = ConvertStringSidToSidW(v16, &Sid);
          wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v47);
          if ( !v17 )
          {
            v19 = 759;
LABEL_19:
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)v19,
                          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
                          v18);
            v21 = hMem;
            v22 = hMem == 0;
            hMem = 0;
            GestureMetadata = LastError;
            if ( !v22 )
              LocalFree(v21);
            v23 = v38;
            v38 = 0;
            if ( v23 )
              LocalFree(v23);
            goto LABEL_10;
          }
          if ( !CopySid(0x44u, (char *)v38 + 8, hMem) )
          {
            v19 = 765;
            goto LABEL_19;
          }
          LengthSid = GetLengthSid(hMem);
          *((_DWORD *)v38 + 1) = LengthSid;
          LODWORD(v36) = 0;
          v25 = RtlPublishWnfStateData(WNF_WBIO_CORRUPTED_ESS_ENROLLMENT_DETECTED, 0, v38, 76) | 0x10000000;
          if ( v25 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x301,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
              (const char *)(unsigned int)v25,
              0);
          v26 = hMem;
          hMem = 0;
          if ( v26 )
            LocalFree(v26);
          v27 = v38;
          v38 = 0;
          if ( v27 )
            LocalFree(v27);
        }
      }
      else if ( GestureMetadata == -2146893813 )
      {
        if ( (Microsoft_Windows_HelloForBusinessEnableBits & 2) != 0 )
        {
          v36 = v47;
          McGenEventWrite_EventWriteTransfer(
            &MS_PROVIDER_HFB_Context,
            EVENT_HFB_BIOMETRICS_INVALID_SECUREBIO_PROTECTOR,
            v15,
            1);
        }
        updated = NgcUtils::SetBioProtectorUpdateNeeded(v14);
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x309,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
            (const char *)(unsigned int)updated,
            (int)v36);
        goto LABEL_32;
      }
      if ( GestureMetadata < 0 )
      {
LABEL_32:
        v12 = 780;
        goto LABEL_8;
      }
      if ( v40 )
      {
        Properties::SecretStore::SecretStore((Properties::SecretStore *)v43);
        v29 = NgcIsoTrustlet::ExportSecretStore((char *)this + 8, 7, v43);
        GestureMetadata = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x314,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
            (const char *)(unsigned int)v29,
            (int)v36);
          v30 = (Properties::SecretStore *)v43;
LABEL_41:
          Properties::SecretStore::~SecretStore(v30);
          goto LABEL_10;
        }
        Properties::SecretStore::operator=((char *)this + 448, v43);
        v31 = (Properties::SecretStore *)v43;
LABEL_50:
        Properties::SecretStore::~SecretStore(v31);
      }
    }
    else
    {
      v41 = 0;
      v32 = Protector::Bio::AuthenticateBioProtector(this, v10, &v41, a4, a5);
      GestureMetadata = v32;
      if ( v32 < 0 )
      {
        v13 = (unsigned int)v32;
        v12 = 799;
        goto LABEL_9;
      }
      if ( v41 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SecureBioSekFix>::GetImpl'::`2'::impl) )
        {
          Properties::SecretStore::SecretStore((Properties::SecretStore *)v44);
          v33 = NgcIsoTrustlet::ExportSecretStore((char *)this + 8, 2, v44);
          GestureMetadata = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x329,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
              (const char *)(unsigned int)v33,
              (int)v36);
            v30 = (Properties::SecretStore *)v44;
            goto LABEL_41;
          }
          Properties::SecretStore::operator=((char *)this + 80, v44);
          v31 = (Properties::SecretStore *)v44;
          goto LABEL_50;
        }
        Properties::BioProtector::BioProtector((Properties::BioProtector *)v45);
        v34 = NgcIsoTrustlet::ExportSecretStore((char *)this + 8, 2, v46);
        GestureMetadata = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x332,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
            (const char *)(unsigned int)v34,
            (int)v36);
          Properties::BioProtector::~BioProtector((Properties::BioProtector *)v45);
          goto LABEL_10;
        }
        std::vector<unsigned char>::operator=(v45, (char *)this + 56);
        Properties::BioProtector::operator=((char *)this + 56, v45);
        Properties::BioProtector::~BioProtector((Properties::BioProtector *)v45);
      }
    }
    std::unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>::~unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>(&v37);
    GestureMetadata = 0;
    goto LABEL_55;
  }
  v9 = 731;
LABEL_5:
  GestureMetadata = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
    (const char *)0x80070057LL,
    (int)v36);
LABEL_55:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v42);
  return (unsigned int)GestureMetadata;
}

```

## disassembly

```asm
0x1800454b0  push    rbp
0x1800454b2  push    rbx
0x1800454b3  push    rsi
0x1800454b4  push    rdi
0x1800454b5  push    r12
0x1800454b7  push    r14
0x1800454b9  push    r15
0x1800454bb  lea     rbp, [rsp-5A0h]
0x1800454c3  sub     rsp, 6A0h
0x1800454ca  mov     rax, cs:__security_cookie
0x1800454d1  xor     rax, rsp
0x1800454d4  mov     [rbp+5D0h+var_38], rax
0x1800454db  mov     r14, r9
0x1800454de  mov     ebx, r8d
0x1800454e1  mov     rdi, rdx
0x1800454e4  mov     rsi, rcx
0x1800454e7  mov     r15, [rbp+5D0h+arg_20]
0x1800454ee  lea     rdx, aBioauthenticat; "BioAuthenticateProtector"
0x1800454f5  lea     rcx, [rsp+6D0h+var_680]
0x1800454fa  call    ?WatchCurrentThread@LogProvider@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; LogProvider::WatchCurrentThread(char const *)
0x1800454ff  nop
0x180045500  cmp     ebx, 8
0x180045503  jz      short loc_18004550C
0x180045505  mov     edx, 2DBh
0x18004550a  jmp     short loc_18004551C
0x18004550c  mov     rbx, [rdi]
0x18004550f  xor     r12d, r12d
0x180045512  test    rbx, rbx
0x180045515  jnz     short loc_18004553C
0x180045517  mov     edx, 2DDh; void *
0x18004551c  mov     edi, 80070057h
0x180045521  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180045528  mov     r9d, edi; char *
0x18004552b  mov     rcx, [rbp+5D8h]; this
0x180045532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045537  jmp     loc_180045994
0x18004553c  mov     [rsp+6D0h+var_6A0], r12
0x180045541  lea     rax, [rsp+6D0h+var_6A0]
0x180045546  mov     qword ptr [rbp+5D0h+var_50], rax
0x18004554d  mov     [rbp+5D0h+Sid], r12
0x180045554  mov     [rbp+5D0h+var_40], 1
0x18004555b  lea     rdx, [rbp+5D0h+Sid]
0x180045562  mov     rcx, rbx
0x180045565  call    cs:__imp_WinBioGetGestureMetadata
0x18004556b  mov     edi, eax
0x18004556d  lea     rcx, [rbp+5D0h+var_50]
0x180045574  call    ??1?$out_param_t@V?$unique_ptr@U_WINBIO_NGC_AUTHORIZATION@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_WINBIO_NGC_AUTHORIZATION,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::~out_param_t<std::unique_ptr<_WINBIO_NGC_AUTHORIZATION,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>(void)
0x180045579  test    edi, edi
0x18004557b  jns     short loc_1800455A8
0x18004557d  mov     edx, 2E0h; void *
0x180045582  mov     r9d, edi; char *
0x180045585  mov     rcx, [rbp+5D8h]; this
0x18004558c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180045593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045598  nop
0x180045599  lea     rcx, [rsp+6D0h+var_6A0]
0x18004559e  call    ??1?$unique_ptr@U_WINBIO_GESTURE_METADATA@@U?$bio_delete@U_WINBIO_GESTURE_METADATA@@@detail@bio@@@std@@QEAA@XZ; std::unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>::~unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>(void)
0x1800455a3  jmp     loc_180045994
0x1800455a8  mov     rax, [rsp+6D0h+var_6A0]
0x1800455ad  mov     [rsp+6D0h+var_6B0], r15; int
0x1800455b2  mov     r9, r14; unsigned __int64 *
0x1800455b5  mov     rdx, rbx; unsigned __int64
0x1800455b8  mov     rcx, rsi; this
0x1800455bb  cmp     dword ptr [rax+10h], 2
0x1800455bf  jnz     loc_180045855
0x1800455c5  mov     [rsp+6D0h+var_688], r12d
0x1800455ca  lea     r8, [rsp+6D0h+var_688]; int *
0x1800455cf  call    ?AuthenticateSecureBioProtector@Bio@Protector@@AEAAJ_KPEAHPEA_K2@Z; Protector::Bio::AuthenticateSecureBioProtector(unsigned __int64,int *,unsigned __int64 *,unsigned __int64 *)
0x1800455d4  mov     edi, eax
0x1800455d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments> `wil::Feature<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::GetImpl(void)'::`2'::impl
0x1800455dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::__private_IsEnabled(void)
0x1800455e2  test    al, al
0x1800455e4  jz      loc_180045788
0x1800455ea  cmp     edi, 8009000Bh
0x1800455f0  jz      short loc_1800455FE
0x1800455f2  cmp     edi, 80090010h
0x1800455f8  jnz     loc_18004577A
0x1800455fe  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 2
0x180045605  jz      short loc_18004562C
0x180045607  lea     rax, [rbp+5D0h+var_50]
0x18004560e  mov     [rsp+6D0h+var_6B0], rax
0x180045613  mov     r9d, 1
0x180045619  lea     rdx, EVENT_HFB_BIOMETRICS_INVALID_SECUREBIO_PROTECTOR
0x180045620  lea     rcx, MS_PROVIDER_HFB_Context
0x180045627  call    McGenEventWrite_EventWriteTransfer
0x18004562c  lea     rcx, [rsp+6D0h+var_698]
0x180045631  call    ??$make_unique_hlocal@U_WINBIO_IDENTITY@@$$V@wil@@YA?AV?$unique_ptr@U_WINBIO_IDENTITY@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_WINBIO_IDENTITY,>(void)
0x180045636  mov     rax, [rsp+6D0h+var_698]
0x18004563b  mov     dword ptr [rax], 3
0x180045641  mov     [rsp+6D0h+hMem], r12
0x180045646  lea     rax, [rsp+6D0h+hMem]
0x18004564b  mov     qword ptr [rbp+5D0h+var_50], rax
0x180045652  mov     [rbp+5D0h+Sid], r12
0x180045659  mov     [rbp+5D0h+var_40], 1
0x180045660  lea     rcx, [rsi+18h]
0x180045664  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045669  lea     rdx, [rbp+5D0h+Sid]; Sid
0x180045670  mov     rcx, rax; StringSid
0x180045673  call    cs:__imp_ConvertStringSidToSidW
0x180045679  mov     ebx, eax
0x18004567b  lea     rcx, [rbp+5D0h+var_50]
0x180045682  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180045687  test    ebx, ebx
0x180045689  jnz     short loc_1800456D8
0x18004568b  mov     edx, 2F7h; void *
0x180045690  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180045697  mov     rcx, [rbp+5D8h]; this
0x18004569e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800456a3  mov     rcx, [rsp+6D0h+hMem]; hMem
0x1800456a8  test    rcx, rcx
0x1800456ab  mov     [rsp+6D0h+hMem], r12
0x1800456b0  mov     edi, eax
0x1800456b2  jz      short loc_1800456BA
0x1800456b4  call    cs:__imp_LocalFree
0x1800456ba  mov     rcx, [rsp+6D0h+var_698]; hMem
0x1800456bf  mov     [rsp+6D0h+var_698], r12
0x1800456c4  test    rcx, rcx
0x1800456c7  jz      loc_180045599
0x1800456cd  call    cs:__imp_LocalFree
0x1800456d3  jmp     loc_180045599
0x1800456d8  mov     rdx, [rsp+6D0h+var_698]
0x1800456dd  add     rdx, 8; pDestinationSid
0x1800456e1  mov     r8, [rsp+6D0h+hMem]; pSourceSid
0x1800456e6  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800456eb  call    cs:__imp_CopySid
0x1800456f1  test    eax, eax
0x1800456f3  jnz     short loc_1800456FC
0x1800456f5  mov     edx, 2FDh
0x1800456fa  jmp     short loc_180045690
0x1800456fc  mov     rcx, [rsp+6D0h+hMem]; pSid
0x180045701  call    cs:__imp_GetLengthSid
0x180045707  mov     rcx, [rsp+6D0h+var_698]
0x18004570c  mov     [rcx+4], eax
0x18004570f  mov     [rsp+6D0h+var_6B0], r12; int
0x180045714  mov     r9d, 4Ch ; 'L'
0x18004571a  mov     r8, [rsp+6D0h+var_698]
0x18004571f  xor     edx, edx
0x180045721  mov     rcx, cs:WNF_WBIO_CORRUPTED_ESS_ENROLLMENT_DETECTED
0x180045728  call    cs:__imp_RtlPublishWnfStateData
0x18004572e  or      eax, 10000000h
0x180045733  mov     rcx, [rbp+5D8h]; this
0x18004573a  jge     short loc_180045750
0x18004573c  mov     r9d, eax; char *
0x18004573f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180045746  mov     edx, 301h; void *
0x18004574b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045750  mov     rcx, [rsp+6D0h+hMem]; hMem
0x180045755  mov     [rsp+6D0h+hMem], r12
0x18004575a  test    rcx, rcx
0x18004575d  jz      short loc_180045765
0x18004575f  call    cs:__imp_LocalFree
0x180045765  mov     rcx, [rsp+6D0h+var_698]; hMem
0x18004576a  mov     [rsp+6D0h+var_698], r12
0x18004576f  test    rcx, rcx
0x180045772  jz      short loc_18004577A
0x180045774  call    cs:__imp_LocalFree
0x18004577a  test    edi, edi
0x18004577c  jns     short loc_1800457E4
0x18004577e  mov     edx, 30Ch
0x180045783  jmp     loc_180045582
0x180045788  cmp     edi, 8009000Bh
0x18004578e  jnz     short loc_18004577A
0x180045790  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 2
0x180045797  jz      short loc_1800457BE
0x180045799  lea     rax, [rbp+5D0h+var_50]
0x1800457a0  mov     [rsp+6D0h+var_6B0], rax; int
0x1800457a5  mov     r9d, 1
0x1800457ab  lea     rdx, EVENT_HFB_BIOMETRICS_INVALID_SECUREBIO_PROTECTOR
0x1800457b2  lea     rcx, MS_PROVIDER_HFB_Context
0x1800457b9  call    McGenEventWrite_EventWriteTransfer
0x1800457be  call    ?SetBioProtectorUpdateNeeded@NgcUtils@@YAJXZ; NgcUtils::SetBioProtectorUpdateNeeded(void)
0x1800457c3  mov     rcx, [rbp+5D8h]; this
0x1800457ca  test    eax, eax
0x1800457cc  jns     short loc_18004577E
0x1800457ce  mov     r9d, eax; char *
0x1800457d1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800457d8  mov     edx, 309h; void *
0x1800457dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800457e2  jmp     short loc_18004577E
0x1800457e4  cmp     [rsp+6D0h+var_688], r12d
0x1800457e9  jz      loc_180045987
0x1800457ef  lea     rcx, [rbp+5D0h+var_630]; this
0x1800457f3  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x1800457f8  nop
0x1800457f9  lea     rcx, [rsi+8]
0x1800457fd  lea     r8, [rbp+5D0h+var_630]
0x180045801  mov     edx, 7
0x180045806  call    ?ExportSecretStore@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@PEAUSecretStore@Properties@@@Z; NgcIsoTrustlet::ExportSecretStore(_GUID const &,NgcCtnrProtectorId,Properties::SecretStore *)
0x18004580b  mov     edi, eax
0x18004580d  test    eax, eax
0x18004580f  jns     short loc_18004583B
0x180045811  mov     rcx, [rbp+5D8h]; this
0x180045818  mov     r9d, eax; char *
0x18004581b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180045822  mov     edx, 314h; void *
0x180045827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004582c  nop
0x18004582d  lea     rcx, [rbp+5D0h+var_630]; this
0x180045831  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x180045836  jmp     loc_180045599
0x18004583b  lea     rcx, [rsi+1C0h]
0x180045842  lea     rdx, [rbp+5D0h+var_630]
0x180045846  call    ??4SecretStore@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::SecretStore::operator=(Properties::SecretStore &&)
0x18004584b  nop
0x18004584c  lea     rcx, [rbp+5D0h+var_630]
0x180045850  jmp     loc_1800458FA
0x180045855  mov     [rsp+6D0h+var_684], r12d
0x18004585a  lea     r8, [rsp+6D0h+var_684]; int *
0x18004585f  call    ?AuthenticateBioProtector@Bio@Protector@@AEAAJ_KPEAHPEA_K2@Z; Protector::Bio::AuthenticateBioProtector(unsigned __int64,int *,unsigned __int64 *,unsigned __int64 *)
0x180045864  mov     edi, eax
0x180045866  test    eax, eax
0x180045868  jns     short loc_180045877
0x18004586a  mov     r9d, eax
0x18004586d  mov     edx, 31Fh
0x180045872  jmp     loc_180045585
0x180045877  cmp     [rsp+6D0h+var_684], r12d
0x18004587c  jz      loc_180045987
0x180045882  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureBioSekFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureBioSekFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix> `wil::Feature<__WilFeatureTraits_Feature_SecureBioSekFix>::GetImpl(void)'::`2'::impl
0x180045889  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureBioSekFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix>::__private_IsEnabled(void)
0x18004588e  test    al, al
0x180045890  jz      short loc_180045904
0x180045892  lea     rcx, [rbp+5D0h+var_4C0]; this
0x180045899  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x18004589e  nop
0x18004589f  lea     r8, [rbp+5D0h+var_4C0]
0x1800458a6  mov     edx, 2
0x1800458ab  lea     rcx, [rsi+8]
0x1800458af  call    ?ExportSecretStore@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@PEAUSecretStore@Properties@@@Z; NgcIsoTrustlet::ExportSecretStore(_GUID const &,NgcCtnrProtectorId,Properties::SecretStore *)
0x1800458b4  mov     edi, eax
0x1800458b6  test    eax, eax
0x1800458b8  jns     short loc_1800458E2
0x1800458ba  mov     rcx, [rbp+5D8h]; this
0x1800458c1  mov     r9d, eax; char *
0x1800458c4  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800458cb  mov     edx, 329h; void *
0x1800458d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800458d5  nop
0x1800458d6  lea     rcx, [rbp+5D0h+var_4C0]
0x1800458dd  jmp     loc_180045831
0x1800458e2  lea     rcx, [rsi+50h]
0x1800458e6  lea     rdx, [rbp+5D0h+var_4C0]
0x1800458ed  call    ??4SecretStore@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::SecretStore::operator=(Properties::SecretStore &&)
0x1800458f2  nop
0x1800458f3  lea     rcx, [rbp+5D0h+var_4C0]; this
0x1800458fa  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x1800458ff  jmp     loc_180045987
0x180045904  lea     rcx, [rbp+5D0h+var_350]; this
0x18004590b  call    ??0BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::BioProtector(void)
0x180045910  nop
0x180045911  lea     r8, [rbp+5D0h+var_338]
0x180045918  mov     edx, 2
0x18004591d  lea     rcx, [rsi+8]
0x180045921  call    ?ExportSecretStore@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@PEAUSecretStore@Properties@@@Z; NgcIsoTrustlet::ExportSecretStore(_GUID const &,NgcCtnrProtectorId,Properties::SecretStore *)
0x180045926  mov     edi, eax
0x180045928  test    eax, eax
0x18004592a  jns     short loc_180045959
0x18004592c  mov     rcx, [rbp+5D8h]; this
0x180045933  mov     r9d, eax; char *
0x180045936  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004593d  mov     edx, 332h; void *
0x180045942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045947  nop
0x180045948  lea     rcx, [rbp+5D0h+var_350]; this
0x18004594f  call    ??1BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::~BioProtector(void)
0x180045954  jmp     loc_180045599
0x180045959  lea     rdx, [rsi+38h]
0x18004595d  lea     rcx, [rbp+5D0h+var_350]
0x180045964  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180045969  lea     rdx, [rbp+5D0h+var_350]
0x180045970  lea     rcx, [rsi+38h]
0x180045974  call    ??4BioProtector@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::BioProtector::operator=(Properties::BioProtector &&)
0x180045979  nop
0x18004597a  lea     rcx, [rbp+5D0h+var_350]; this
0x180045981  call    ??1BioProtector@Properties@@QEAA@XZ; Properties::BioProtector::~BioProtector(void)
0x180045986  nop
0x180045987  lea     rcx, [rsp+6D0h+var_6A0]
0x18004598c  call    ??1?$unique_ptr@U_WINBIO_GESTURE_METADATA@@U?$bio_delete@U_WINBIO_GESTURE_METADATA@@@detail@bio@@@std@@QEAA@XZ; std::unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>::~unique_ptr<_WINBIO_GESTURE_METADATA,bio::detail::bio_delete<_WINBIO_GESTURE_METADATA>>(void)
0x180045991  mov     edi, r12d
0x180045994  lea     rcx, [rsp+6D0h+var_680]; this
0x180045999  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18004599e  mov     eax, edi
0x1800459a0  mov     rcx, [rbp+5D0h+var_38]
0x1800459a7  xor     rcx, rsp; StackCookie
0x1800459aa  call    __security_check_cookie
0x1800459af  add     rsp, 6A0h
0x1800459b6  pop     r15
0x1800459b8  pop     r14
0x1800459ba  pop     r12
0x1800459bc  pop     rdi
0x1800459bd  pop     rsi
0x1800459be  pop     rbx
0x1800459bf  pop     rbp
0x1800459c0  retn
```
