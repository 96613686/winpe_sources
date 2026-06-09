# s_WebAuthNAuthenticatorMakeCredentialNgc(_CTAPDEVICE_CONTROL_BLOCK *,_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *,int,ushort const *,bool,PasskeyTelemetry &)

- ea: `0x180089b74`
- end: `0x18008b1e4`
- name: `?s_WebAuthNAuthenticatorMakeCredentialNgc@@YAJPEAU_CTAPDEVICE_CONTROL_BLOCK@@PEAU_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST@@HPEBG_NAEAUPasskeyTelemetry@@@Z`
- size: `5744`
- prototype: `__int64 __fastcall(struct _CTAPDEVICE_CONTROL_BLOCK *, struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *, int, const unsigned __int16 *, bool, struct PasskeyTelemetry *)`
- caller_count: `2`
- callee_count: `65`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180084df4`
- `0x18009f024`

## callees

- `0x18000af70`
- `0x18001687c`
- `0x180017764`
- `0x180017a88`
- `0x180017bb4`
- `0x18001c0d4`
- `0x18001d6d8`
- `0x18001df88`
- `0x18001ee9c`
- `0x18001f2c4`
- `0x18001fa64`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180020718`
- `0x180025880`
- `0x180027338`
- `0x180027884`
- `0x18002819c`
- `0x180028918`
- `0x18002a2f0`
- `0x18002bbf4`
- `0x180031708`
- `0x1800317c0`
- `0x1800350b4`
- `0x18003988c`
- `0x1800398d8`
- `0x18003de2c`
- `0x18003e378`
- `0x180046768`
- `0x180047464`
- `0x18004f5b4`
- `0x18005378c`
- `0x1800537a4`
- `0x180062c84`
- `0x18006568c`
- `0x180067c90`
- `0x180067e24`
- `0x1800681f8`
- `0x18006823c`
- `0x18006ca30`
- `0x18007293c`
- `0x180073374`
- `0x180077f4c`
- `0x18007c8c8`
- `0x18007d358`
- `0x18007ed34`
- `0x1800817f4`
- `0x180084df4`
- `0x1800869ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b0b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b12d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b173`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b1b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b0b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b12d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b173`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089f01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089f01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a08a`
- `CRYPT32!CryptHashCertificate2` at `0x18008a0d4`
- `CRYPT32!CryptHashCertificate2` at `0x18008a0d4`
- `ncrypt!NCryptSetProperty` at `0x18008ab93`
- `ncrypt!NCryptSetProperty` at `0x18008ab93`
- `ncrypt!NCryptDeleteKey` at `0x18008a6df`
- `ncrypt!NCryptDeleteKey` at `0x18008a6df`
- `ncrypt!NCryptGetProperty` at `0x18008a779`
- `ncrypt!NCryptGetProperty` at `0x18008a7ce`
- `ncrypt!NCryptGetProperty` at `0x18008a8cc`
- `ncrypt!NCryptGetProperty` at `0x18008a779`
- `ncrypt!NCryptGetProperty` at `0x18008a7ce`
- `ncrypt!NCryptGetProperty` at `0x18008a8cc`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18008a022`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18008a022`
- `cryptngc!NgcGetUserIdKeyName` at `0x18008a341`
- `cryptngc!NgcGetUserIdKeyName` at `0x18008a341`

## string_xrefs

- `0x180089dde`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180089ee4`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a041`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a103`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a1a7`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a240`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a284`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a499`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a525`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a896`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008a94d`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008aa56`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008ae32`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008ae81`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008aec8`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008afb5`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008afd3`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008ab89`: `PinCacheIsGestureRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall s_WebAuthNAuthenticatorMakeCredentialNgc(
        struct _CTAPDEVICE_CONTROL_BLOCK *a1,
        struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *a2,
        int a3,
        const unsigned __int16 *a4,
        bool a5,
        struct PasskeyTelemetry *a6)
{
  __int64 v7; // rsi
  __int64 v8; // r15
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // eax
  int v14; // r14d
  struct _CREDUI_INFOW *v15; // rsi
  int CredBrowserInPrivateModeString; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rcx
  bool v20; // zf
  const char *v21; // rdx
  const char *v22; // rax
  void *v23; // rcx
  int NonzeroLastError; // eax
  __int64 v25; // rdx
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // r9
  unsigned int v28; // edi
  __int64 v29; // r9
  __int64 v30; // rdx
  SECURITY_STATUS v31; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  unsigned __int64 v34; // r9
  struct _CREDUI_INFOW *v35; // rdi
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // r8
  int v42; // ebx
  __int64 v43; // rax
  struct _CREDUI_INFOW *p_pUiInfo; // rcx
  __int64 v45; // rax
  unsigned __int16 **v46; // r9
  int v47; // esi
  int v48; // ecx
  unsigned int v49; // ebx
  _DWORD *v50; // rcx
  unsigned __int64 v51; // rbx
  unsigned __int8 *v52; // rdi
  unsigned __int8 *v53; // rax
  size_t v54; // rbx
  __int64 v55; // r12
  int v56; // eax
  SECURITY_STATUS v57; // eax
  char IsEnabled; // al
  NCRYPT_HANDLE v59; // rbx
  SECURITY_STATUS Property; // eax
  __int128 v61; // xmm0
  _DWORD *v62; // rdi
  int v63; // r15d
  const wchar_t *v64; // r15
  int v65; // r13d
  int v66; // eax
  int TpmAttestation; // edi
  int v68; // edi
  HLOCAL v69; // r12
  int SelfAttestation; // ebx
  int v71; // ebx
  int CredentialResponse; // ebx
  int v73; // edi
  unsigned int v74; // ebx
  unsigned int v75; // eax
  unsigned int updated; // eax
  int v77; // ebx
  const unsigned __int16 *v78; // r9
  int v79; // ebx
  int v80; // r9d
  int v81; // eax
  HLOCAL v82; // rcx
  HLOCAL v83; // rcx
  HLOCAL v84; // rcx
  HLOCAL v85; // rcx
  HLOCAL v86; // rcx
  HLOCAL v87; // rcx
  HLOCAL v88; // rcx
  unsigned int ulInAuthBufferSize; // [rsp+20h] [rbp-100h]
  unsigned int ulInAuthBufferSizea; // [rsp+20h] [rbp-100h]
  int ulInAuthBufferSizeb; // [rsp+20h] [rbp-100h]
  LPVOID *ppvOutAuthBuffer; // [rsp+28h] [rbp-F8h]
  LPVOID *ppvOutAuthBuffera; // [rsp+28h] [rbp-F8h]
  int v95; // [rsp+A0h] [rbp-80h]
  unsigned __int16 *v96[2]; // [rsp+B0h] [rbp-70h] BYREF
  char v97; // [rsp+C0h] [rbp-60h]
  __int64 v98; // [rsp+D0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-48h] BYREF
  ULONG pulAuthPackage; // [rsp+E0h] [rbp-40h] BYREF
  DWORD pcbComputedHash; // [rsp+E4h] [rbp-3Ch] BYREF
  int v102; // [rsp+E8h] [rbp-38h] BYREF
  DWORD v103; // [rsp+ECh] [rbp-34h] BYREF
  int v104; // [rsp+F0h] [rbp-30h]
  unsigned int v105; // [rsp+F4h] [rbp-2Ch] BYREF
  struct _CREDUI_INFOW *v106; // [rsp+F8h] [rbp-28h]
  int v107; // [rsp+100h] [rbp-20h]
  BYTE v108[4]; // [rsp+104h] [rbp-1Ch] BYREF
  int v109; // [rsp+108h] [rbp-18h]
  int v110; // [rsp+10Ch] [rbp-14h]
  int v111; // [rsp+110h] [rbp-10h]
  int v112; // [rsp+114h] [rbp-Ch] BYREF
  HLOCAL v113; // [rsp+118h] [rbp-8h] BYREF
  HLOCAL v114; // [rsp+120h] [rbp+0h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+128h] [rbp+8h] BYREF
  unsigned int v116; // [rsp+130h] [rbp+10h] BYREF
  DWORD cbOutput; // [rsp+134h] [rbp+14h] BYREF
  int v118; // [rsp+138h] [rbp+18h]
  int v119; // [rsp+13Ch] [rbp+1Ch] BYREF
  int v120; // [rsp+140h] [rbp+20h] BYREF
  int v121; // [rsp+144h] [rbp+24h] BYREF
  BYTE v122[8]; // [rsp+148h] [rbp+28h] BYREF
  char v123[8]; // [rsp+150h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+158h] [rbp+38h] BYREF
  HLOCAL v125; // [rsp+160h] [rbp+40h] BYREF
  HLOCAL v126; // [rsp+168h] [rbp+48h] BYREF
  unsigned __int16 *v127; // [rsp+170h] [rbp+50h] BYREF
  HLOCAL v128; // [rsp+178h] [rbp+58h] BYREF
  unsigned __int16 *v129; // [rsp+180h] [rbp+60h] BYREF
  HLOCAL v130; // [rsp+188h] [rbp+68h] BYREF
  HLOCAL hMem; // [rsp+190h] [rbp+70h] BYREF
  unsigned __int8 *v132[2]; // [rsp+198h] [rbp+78h] BYREF
  __int64 v133; // [rsp+1A8h] [rbp+88h]
  struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *v134; // [rsp+1B0h] [rbp+90h]
  __int64 v135; // [rsp+1B8h] [rbp+98h]
  struct _WEBAUTHN_COSE_CREDENTIAL_PARAMETERS *v136; // [rsp+1C0h] [rbp+A0h]
  HANDLE hObject; // [rsp+1C8h] [rbp+A8h]
  __int64 v138; // [rsp+1D0h] [rbp+B0h] BYREF
  unsigned __int16 *v139; // [rsp+1D8h] [rbp+B8h] BYREF
  _QWORD v140[2]; // [rsp+1E0h] [rbp+C0h] BYREF
  _QWORD v141[2]; // [rsp+1F0h] [rbp+D0h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+200h] [rbp+E0h] BYREF
  struct _CTAPDEVICE_CONTROL_BLOCK *v143; // [rsp+208h] [rbp+E8h]
  __int64 v144; // [rsp+210h] [rbp+F0h]
  __int128 v145; // [rsp+218h] [rbp+F8h] BYREF
  __int128 v146; // [rsp+228h] [rbp+108h]
  __int64 v147; // [rsp+238h] [rbp+118h] BYREF
  __int128 v148; // [rsp+240h] [rbp+120h] BYREF
  __int64 v149; // [rsp+250h] [rbp+130h]
  _DWORD v150[2]; // [rsp+258h] [rbp+138h] BYREF
  HLOCAL v151; // [rsp+260h] [rbp+140h]
  __int128 *v152; // [rsp+268h] [rbp+148h]
  int v153; // [rsp+270h] [rbp+150h] BYREF
  const wchar_t *v154; // [rsp+278h] [rbp+158h]
  int v155; // [rsp+280h] [rbp+160h]
  HLOCAL v156; // [rsp+288h] [rbp+168h]
  int v157; // [rsp+290h] [rbp+170h]
  HLOCAL v158; // [rsp+298h] [rbp+178h]
  int v159; // [rsp+2A0h] [rbp+180h]
  HLOCAL v160; // [rsp+2A8h] [rbp+188h]
  _DWORD v161[52]; // [rsp+330h] [rbp+210h] BYREF
  int v162; // [rsp+400h] [rbp+2E0h] BYREF
  BYTE *v163; // [rsp+408h] [rbp+2E8h]
  char v164; // [rsp+410h] [rbp+2F0h]
  int v165; // [rsp+414h] [rbp+2F4h]
  __int128 v166; // [rsp+418h] [rbp+2F8h] BYREF
  unsigned __int16 v167; // [rsp+428h] [rbp+308h]
  HLOCAL v168; // [rsp+430h] [rbp+310h]
  unsigned __int16 v169; // [rsp+438h] [rbp+318h]
  HLOCAL v170; // [rsp+440h] [rbp+320h]
  __int16 v171; // [rsp+448h] [rbp+328h]
  __int64 v172; // [rsp+450h] [rbp+330h]
  struct _CREDUI_INFOW pUiInfo; // [rsp+460h] [rbp+340h] BYREF
  int v174; // [rsp+524h] [rbp+404h]
  char v175; // [rsp+528h] [rbp+408h] BYREF
  char v176; // [rsp+530h] [rbp+410h] BYREF
  int v177; // [rsp+538h] [rbp+418h]
  int v178; // [rsp+53Ch] [rbp+41Ch]
  __int128 v179; // [rsp+570h] [rbp+450h] BYREF
  __int64 v180; // [rsp+580h] [rbp+460h] BYREF
  struct _CREDUI_INFOW *v181; // [rsp+588h] [rbp+468h]
  __int64 v182; // [rsp+590h] [rbp+470h]
  __int128 v183; // [rsp+598h] [rbp+478h]
  char v184; // [rsp+5C0h] [rbp+4A0h]
  _BYTE v185[32]; // [rsp+5E0h] [rbp+4C0h] BYREF
  char v186[32]; // [rsp+600h] [rbp+4E0h] BYREF
  __int128 v187; // [rsp+620h] [rbp+500h]
  __int64 v188; // [rsp+630h] [rbp+510h]
  __int64 v189; // [rsp+638h] [rbp+518h]
  _BYTE v190[32]; // [rsp+640h] [rbp+520h] BYREF
  char v191[32]; // [rsp+660h] [rbp+540h] BYREF
  __int128 v192; // [rsp+680h] [rbp+560h]
  __int64 v193; // [rsp+690h] [rbp+570h]
  __int64 v194; // [rsp+698h] [rbp+578h]
  BYTE pbComputedHash[16]; // [rsp+6A0h] [rbp+580h] BYREF
  __int128 v196; // [rsp+6B0h] [rbp+590h]
  BYTE pbOutput[32]; // [rsp+6C0h] [rbp+5A0h] BYREF
  char v198; // [rsp+6E0h] [rbp+5C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+628h]

  v107 = a3;
  v134 = a2;
  v143 = a1;
  v7 = *((_QWORD *)a1 + 39);
  v144 = v7;
  v8 = *(_QWORD *)(v7 + 56);
  v135 = *(_QWORD *)(v8 + 152);
  v95 = v8 + 16;
  v136 = (struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *)((char *)a2 + 48);
  v106 = (struct _CREDUI_INFOW *)*((_QWORD *)a2 + 4);
  v9 = *((_QWORD *)a2 + 5);
  v126 = 0;
  v120 = 0;
  v105 = 0;
  v140[0] = 0;
  v148 = 0;
  v149 = 0;
  hKey = 0;
  v118 = 0;
  v130 = 0;
  v179 = 0;
  memset_0(&v162, 0, 0x58u);
  v119 = 0;
  v114 = 0;
  memset_0(&v153, 0, 0xC0u);
  v129 = 0;
  v128 = 0;
  v116 = 0;
  v102 = 0;
  v113 = 0;
  v104 = 0;
  v125 = 0;
  HIDWORD(v180) = 0;
  v183 = 0;
  *(_OWORD *)pbComputedHash = 0;
  v196 = 0;
  pcbComputedHash = 0;
  v147 = 0;
  v127 = 0;
  v112 = 0;
  v111 = 0;
  v110 = 0;
  v109 = 0;
  hObject = 0;
  hProvider = 0;
  *(_DWORD *)v108 = 0;
  cbOutput = 4;
  v139 = 0;
  std::wstring::wstring(v190);
  std::wstring::wstring(v191);
  v192 = 0;
  v193 = v10;
  v194 = 0;
  std::wstring::wstring(v185);
  std::wstring::wstring(v186);
  v187 = 0;
  v188 = v11;
  v189 = 0;
  *(_DWORD *)v122 = v11;
  *(_OWORD *)v132 = 0;
  v133 = v11;
  v103 = v11;
  memset_0(pbOutput, v11, (unsigned int)(v11 + 64));
  v145 = 0;
  v146 = 0;
  v121 = 0;
  v138 = 0;
  v150[1] = 0;
  memset_0(v161, 0, 0xC8u);
  hMem = 0;
  if ( (Microsoft_Windows_WebAuthNEnableBits & 8) != 0 )
    McTemplateU0j_EventWriteTransfer(v12, &EVENT_WEBAUTHN_NGC_MAKE_CREDENTIAL_START, v8 + 16);
  v13 = CtapSrvImpersonateRpcToken(*(HANDLE *)(v7 + 64));
  LODWORD(v7) = v13;
  if ( v13 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x754,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v13,
      ulInAuthBufferSize);
    v14 = 0;
LABEL_5:
    if ( (int)v7 <= 0 )
    {
LABEL_174:
      v79 = v95;
      goto LABEL_175;
    }
    LODWORD(v7) = (unsigned __int16)v7;
LABEL_7:
    LODWORD(v7) = v7 | 0x80070000;
    goto LABEL_174;
  }
  v14 = 1;
  v15 = v106;
  if ( !v106
    || !v106->hwndParent
    || !v9
    || !*(_DWORD *)(v9 + 4)
    || !*(_QWORD *)(v9 + 8)
    || !*((_DWORD *)a2 + 12)
    || !*((_QWORD *)a2 + 7)
    || !*((_QWORD *)a2 + 3)
    || !*((_DWORD *)a2 + 4) )
  {
    LODWORD(v7) = -2146893785;
    v29 = 2148073511LL;
    v30 = 1889;
    goto LABEL_173;
  }
  if ( *(_DWORD *)(v8 + 176) && !v107 )
  {
    memset_0(&pUiInfo, 0, 0x88u);
    v141[0] = &pUiInfo;
    pulAuthPackage = -9594;
    pulOutAuthBufferSize = 0;
    pv = 0;
    v96[0] = (unsigned __int16 *)&word_18015030C;
    CredBrowserInPrivateModeString = GetMakeCredBrowserInPrivateModeString(*(unsigned __int16 ***)(*((_QWORD *)a2 + 4)
                                                                                                 + 8LL));
    LODWORD(v7) = CredBrowserInPrivateModeString;
    v17 = retaddr;
    if ( CredBrowserInPrivateModeString < 0 )
    {
      v18 = 1913;
LABEL_21:
      wil::details::in1diag3::_Log_Hr(
        v17,
        (void *)v18,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)CredBrowserInPrivateModeString,
        ulInAuthBufferSize);
LABEL_22:
      v19 = pv;
      v20 = pv == 0;
      pv = 0;
      if ( !v20 )
        CoTaskMemFree(v19);
      wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(v141);
      goto LABEL_174;
    }
    CredBrowserInPrivateModeString = I_WebAuthNCtapBuildMakeCredentialCredUiInfo(
                                       *(HWND *)v135,
                                       0x40Cu,
                                       v96[0],
                                       (struct CREDUI_INFO_INTERNAL *)&pUiInfo);
    LODWORD(v7) = CredBrowserInPrivateModeString;
    v17 = retaddr;
    if ( CredBrowserInPrivateModeString < 0 )
    {
      v18 = 1919;
      goto LABEL_21;
    }
    v7 = v144;
    *(_OWORD *)v96 = *(_OWORD *)(*(_QWORD *)(v144 + 56) + 16LL);
    tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(
      v123,
      v96);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(v123) )
    {
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(
                               v123,
                               v96)
                + 276LL) = 8;
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(v96);
      v22 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::ui_invoked", v21);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::set_flag(
        v123,
        1,
        v22);
    }
    if ( *(_DWORD *)(v8 + 460) )
      LODWORD(pUiInfo.hbmBanner) |= 0x80000u;
    v96[0] = (unsigned __int16 *)&pv;
    v96[1] = 0;
    v97 = 1;
    LODWORD(v7) = CredUIPromptForWindowsCredentialsW(
                    &pUiInfo,
                    0,
                    &pulAuthPackage,
                    *(LPCVOID *)(*(_QWORD *)(v7 + 56) + 144LL),
                    *(_DWORD *)(*(_QWORD *)(v7 + 56) + 136LL),
                    (LPVOID *)&v96[1],
                    &pulOutAuthBufferSize,
                    0,
                    0x8000210u);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v96);
    if ( (_DWORD)v7 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x797,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)(unsigned int)v7,
        ulInAuthBufferSizea);
      if ( (int)v7 > 0 )
        LODWORD(v7) = (unsigned __int16)v7 | 0x80070000;
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v123);
      goto LABEL_22;
    }
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v123);
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(v141);
    v15 = v106;
  }
  pcbComputedHash = 32;
  if ( !CryptHashCertificate2(
          L"SHA256",
          0,
          0,
          *((const BYTE **)a2 + 1),
          *((_DWORD *)a2 + 1),
          pbComputedHash,
          &pcbComputedHash) )
  {
    NonzeroLastError = _GetNonzeroLastError();
    LODWORD(v7) = NonzeroLastError;
    if ( NonzeroLastError > 0 )
      LODWORD(v7) = (unsigned __int16)NonzeroLastError | 0x80070000;
    v25 = 1955;
    goto LABEL_42;
  }
  LODWORD(v180) = 2;
  v181 = v15;
  v182 = v9;
  v96[0] = (unsigned __int16 *)&v128;
  v96[1] = 0;
  v97 = 1;
  v28 = CtapCborEncodeAccountInformation(&v180, &v116, &v96[1], &v105);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
  if ( v28 )
  {
    v7 = (unsigned int)HRESULT_FROM_CBOR_ERROR(v28);
    v29 = v7;
    v30 = 1968;
LABEL_173:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v29,
      ulInAuthBufferSize);
    goto LABEL_174;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hProvider,
    0);
  v31 = WebAuthNOpenNgcKsp(&hProvider);
  LODWORD(v7) = v31;
  v32 = retaddr;
  if ( v31 < 0 )
  {
    v33 = 1972;
LABEL_49:
    v34 = (unsigned int)v31;
LABEL_50:
    wil::details::in1diag3::_Log_Hr(
      v32,
      (void *)v33,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v34,
      ulInAuthBufferSize);
    goto LABEL_174;
  }
  v35 = v106;
  if ( *((_QWORD *)v134 + 9) && *((_DWORD *)v134 + 16) )
  {
    LOBYTE(v98) = 0;
    v31 = DoesExcludedCredentialExist(hProvider, (__int64)v134 + 64, (__int64)&v98);
    LODWORD(v7) = v31;
    v32 = retaddr;
    if ( v31 < 0 )
    {
      v33 = 1986;
      goto LABEL_49;
    }
    if ( (_BYTE)v98 == 1 )
    {
      LODWORD(v7) = CtapSrvRestoreThreadToken(hObject);
      if ( (_DWORD)v7 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x7C8,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          (const char *)(unsigned int)v7,
          ulInAuthBufferSize);
        goto LABEL_5;
      }
      v14 = 0;
      v36 = I_NgcDummyUserVerification(v143, a6);
      LODWORD(v7) = v36;
      v26 = retaddr;
      if ( v36 < 0 )
      {
        v27 = (unsigned int)v36;
        v25 = 2008;
        goto LABEL_44;
      }
      LODWORD(v7) = -2146893809;
      v25 = 2004;
LABEL_43:
      v27 = (unsigned int)v7;
LABEL_44:
      wil::details::in1diag3::Log_Hr(
        v26,
        (void *)v25,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
        (const char *)v27,
        ulInAuthBufferSize);
      goto LABEL_174;
    }
  }
  v96[0] = (unsigned __int16 *)v140;
  v96[1] = 0;
  v97 = 1;
  LODWORD(v7) = BuildNgcFidoUserId(
                  pbComputedHash,
                  pcbComputedHash,
                  *(BYTE **)(v9 + 8),
                  *(_DWORD *)(v9 + 4),
                  (__int64)&v96[1]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v96);
  v32 = retaddr;
  if ( (int)v7 < 0 )
  {
    v34 = (unsigned int)v7;
    v33 = 2019;
    goto LABEL_50;
  }
  *(_QWORD *)&v148 = L"FIDO_AUTHENTICATOR";
  *((_QWORD *)&v148 + 1) = 0;
  v149 = v140[0];
  v96[0] = (unsigned __int16 *)&v129;
  v96[1] = 0;
  v97 = 1;
  LODWORD(v7) = NgcGetUserIdKeyName(&v148, 0, &v96[1]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v96);
  v32 = retaddr;
  if ( (int)v7 < 0 )
  {
    v34 = (unsigned int)v7;
    v33 = 2029;
    goto LABEL_50;
  }
  v37 = -1;
  v38 = -1;
  do
    ++v38;
  while ( *((_WORD *)v35->hwndParent + v38) );
  v39 = *(_QWORD *)(v9 + 16);
  do
    ++v37;
  while ( *(_WORD *)(v39 + 2 * v37) );
  v96[0] = (unsigned __int16 *)v35->hwndParent;
  v96[1] = (unsigned __int16 *)v38;
  v141[0] = v39;
  v141[1] = v37;
  v40 = WebAuthNUI::CreatePasskeyHeader(&v180, v141, v96, 0);
  NgcUtils::CredUiAdditionalInfo::operator=(v190, v40);
  NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)&v180);
  v42 = v107;
  if ( v107 && *((_DWORD *)a6 + 47) == 2 )
  {
    LOBYTE(v41) = a5;
    v43 = WebAuthNUI::CreatePasskeyFooter(&v180, 1250, v41, 112);
    NgcUtils::CredUiAdditionalInfo::operator=(v185, v43);
    p_pUiInfo = (struct _CREDUI_INFOW *)&v180;
  }
  else
  {
    LOBYTE(v41) = a5;
    v45 = WebAuthNUI::CreatePasskeyFooter(&pUiInfo, 1033, v41, 97);
    NgcUtils::CredUiAdditionalInfo::operator=(v185, v45);
    p_pUiInfo = &pUiInfo;
  }
  NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)p_pUiInfo);
  v96[0] = (unsigned __int16 *)&v139;
  v96[1] = 0;
  v97 = 1;
  LODWORD(v7) = FidoCommon::FidoGetFormattedMessage(
                  (FidoCommon *)g_hInstance,
                  (HINSTANCE)0x40C,
                  (unsigned int)&v96[1],
                  v46);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v96);
  v32 = retaddr;
  if ( (int)v7 < 0 )
  {
    v33 = 2053;
LABEL_75:
    v34 = (unsigned int)v7;
    goto LABEL_50;
  }
  v47 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
  {
    v47 = *(_DWORD *)(v8 + 440);
    v48 = *(_DWORD *)(v8 + 160);
    if ( v48 )
    {
      pv = 0;
      v96[0] = (unsigned __int16 *)&pv;
      v96[1] = 0;
      v97 = 1;
      v49 = CtapCborDecodeHmacSecretSaltValues(
              v48,
              *(_QWORD *)(v8 + 168),
              (unsigned int)&v96[1],
              0,
              0,
              (__int64)ppvOutAuthBuffer);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(v96);
      if ( v49 )
      {
        v7 = (unsigned int)HRESULT_FROM_CBOR_ERROR(v49);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x812,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          (const char *)v7,
          ulInAuthBufferSizeb);
        wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&pv, 0);
        goto LABEL_174;
      }
      v50 = *(_DWORD **)pv;
      if ( !*(_QWORD *)pv )
        goto LABEL_89;
      v51 = (unsigned int)(*v50 + v50[4]);
      v52 = v132[1];
      if ( v51 < v132[1] - v132[0] )
      {
        v53 = &v132[0][*v50 + v50[4]];
LABEL_87:
        v132[1] = v53;
        goto LABEL_88;
      }
      if ( v51 > v132[1] - v132[0] )
      {
        if ( v51 <= v133 - (unsigned __int64)v132[0] )
        {
          v54 = v51 - (v132[1] - v132[0]);
          memset_0(v132[1], 0, v54);
          v53 = &v52[v54];
          goto LABEL_87;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v132, (unsigned int)(*v50 + v50[4]));
      }
LABEL_88:
      memcpy_0(v132[0], *(const void **)(*(_QWORD *)pv + 8LL), **(unsigned int **)pv);
      memcpy_0(
        &v132[0][**(unsigned int **)pv],
        *(const void **)(*(_QWORD *)pv + 24LL),
        *(unsigned int *)(*(_QWORD *)pv + 16LL));
LABEL_89:
      wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&pv, 0);
      v42 = v107;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v127,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v55 = v135;
  v56 = WebAuthNCreateUserIdKeyHandle(
          hProvider,
          v129,
          v136,
          *(HWND *)v135,
          0,
          v139,
          (struct NgcUtils::CredUiAdditionalInfo *)v190,
          (struct NgcUtils::CredUiAdditionalInfo *)v185,
          *(_DWORD *)(v8 + 460),
          (unsigned __int8 *)v128,
          v116,
          v47,
          v132[0],
          LODWORD(v132[1]) - LODWORD(v132[0]),
          0x84u,
          *(struct _GUID **)(v135 + 32),
          &hKey,
          &v127,
          &v112);
  LODWORD(v7) = v56;
  v32 = retaddr;
  if ( v56 < 0 )
  {
    v34 = (unsigned int)v56;
    v33 = 2098;
    goto LABEL_50;
  }
  if ( v42 )
  {
    v57 = NCryptDeleteKey(hKey, 0);
    v32 = retaddr;
    if ( v57 >= 0 )
      goto LABEL_174;
    v34 = (unsigned int)v57;
    v33 = 2108;
    goto LABEL_50;
  }
  v184 = 1;
  CredentialAuthenticatorCache::ClearAuthenticator(*(_QWORD *)(v144 + 64), &v180);
  std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(&v180);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl);
  v59 = hKey;
  if ( IsEnabled )
  {
    if ( v132[1] != v132[0] && NCryptGetProperty(hKey, L"NgcFidoHmacSecret", pbOutput, 0x40u, &v103, 0x40u) >= 0 )
    {
      if ( v103 == 32 )
      {
        *((_QWORD *)&v145 + 1) = pbOutput;
        LODWORD(v145) = 32;
      }
      else
      {
        if ( v103 != 64 )
        {
          LODWORD(v7) = -2146893813;
          v25 = 2140;
LABEL_42:
          v26 = retaddr;
          goto LABEL_43;
        }
        *((_QWORD *)&v145 + 1) = pbOutput;
        LODWORD(v145) = 32;
        *((_QWORD *)&v146 + 1) = &v198;
        LODWORD(v146) = 32;
      }
    }
    pulAuthPackage = 0;
    NCryptGetProperty(v59, L"NgcFidoThirdPartyPayment", v122, 4u, &pulAuthPackage, 0x40u);
  }
  v96[0] = (unsigned __int16 *)&v125;
  v96[1] = 0;
  v97 = 1;
  LODWORD(v7) = I_WebAuthNGetNgcGetCredentialId(v59);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
  v32 = retaddr;
  if ( (int)v7 < 0 )
  {
    v33 = 2160;
    goto LABEL_75;
  }
  v96[0] = (unsigned __int16 *)&v130;
  v96[1] = 0;
  v97 = 1;
  LODWORD(v7) = CtapCborEncodePublicKeyFromNCryptKeyHandle(v59);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
  if ( (_DWORD)v7 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x877,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)v7,
      ulInAuthBufferSize);
    goto LABEL_5;
  }
  Property = NCryptGetProperty(v59, L"NgcKeyImplType", v108, cbOutput, &cbOutput, 0);
  LODWORD(v7) = Property;
  v32 = retaddr;
  if ( Property < 0 )
  {
    v34 = (unsigned int)Property;
    v33 = 2176;
    goto LABEL_50;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
  {
    switch ( v108[0] )
    {
      case 0x21u:
        v61 = WEBAUTHN_HELLO_AUTHENTICATOR_VIRTUALIZATION_SECURITY_MODULE_HARDWARE_GUID;
        break;
      case 0x22u:
        v61 = WEBAUTHN_HELLO_AUTHENTICATOR_VIRTUALIZATION_SECURITY_MODULE_SOFTWARE_GUID;
        break;
      case 1u:
        v61 = WEBAUTHN_HELLO_AUTHENTICATOR_HARDWARE_ATTESTATION_GUID;
        break;
      case 2u:
        v61 = WEBAUTHN_HELLO_AUTHENTICATOR_SOFTWARE_ATTESTATION_GUID;
        break;
      default:
        v27 = 2148073513LL;
        LODWORD(v7) = -2146893783;
        v26 = retaddr;
        v25 = 2198;
        goto LABEL_44;
    }
    v62 = (_DWORD *)(v55 + 24);
  }
  else
  {
    v62 = (_DWORD *)(v55 + 24);
    if ( *(_DWORD *)(v55 + 24) == 1 )
    {
      v61 = 0;
    }
    else
    {
      switch ( v108[0] )
      {
        case 0x21u:
          v61 = WEBAUTHN_HELLO_AUTHENTICATOR_VIRTUALIZATION_SECURITY_MODULE_HARDWARE_GUID;
          break;
        case 0x22u:
          v61 = WEBAUTHN_HELLO_AUTHENTICATOR_VIRTUALIZATION_SECURITY_MODULE_SOFTWARE_GUID;
          break;
        case 1u:
          v61 = WEBAUTHN_HELLO_AUTHENTICATOR_HARDWARE_ATTESTATION_GUID;
          break;
        case 2u:
          v61 = WEBAUTHN_HELLO_AUTHENTICATOR_SOFTWARE_ATTESTATION_GUID;
          break;
        default:
          v27 = 2148073513LL;
          LODWORD(v7) = -2146893783;
          v26 = retaddr;
          v25 = 2225;
          goto LABEL_44;
      }
    }
  }
  v179 = v61;
  v162 = 1;
  v163 = pbComputedHash;
  v164 = 69;
  v166 = v61;
  v167 = v104;
  v168 = v125;
  v169 = v118;
  v170 = v130;
  v165 = 0;
  v172 = 0;
  v171 = 0;
  v96[0] = (unsigned __int16 *)&v114;
  v96[1] = 0;
  v97 = 1;
  v63 = CtapCborPackAuthenticatorData(&v162, &v119, &v96[1]);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
  if ( v63 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x8CD,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)(unsigned int)v63,
      ulInAuthBufferSize);
    if ( v63 <= 0 )
    {
      LODWORD(v7) = v63;
      goto LABEL_174;
    }
    LODWORD(v7) = (unsigned __int16)v63;
    goto LABEL_7;
  }
  v153 = 8;
  v64 = L"none";
  v154 = L"none";
  v65 = v119;
  v155 = v119;
  v156 = v114;
  v66 = IsTpm20(retaddr);
  v111 = v66;
  if ( (unsigned int)(*v62 - 2) > 1 )
  {
    v69 = v158;
    v68 = v157;
  }
  else
  {
    if ( v66
      && (v96[0] = (unsigned __int16 *)&v113,
          v96[1] = 0,
          v97 = 1,
          ppvOutAuthBuffera = (LPVOID *)*((_QWORD *)v134 + 3),
          TpmAttestation = NgcFidoCreateTpmAttestation(v106, v129, *(_QWORD *)v55, v114, v65),
          v110 = TpmAttestation,
          wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96),
          TpmAttestation >= 0) )
    {
      v64 = L"tpm";
      v154 = L"tpm";
      v68 = v102;
      v157 = v102;
      v69 = v113;
      v158 = v113;
    }
    else
    {
      v69 = v158;
      v68 = v157;
    }
    if ( !wcscmp_0(v64, L"none") )
    {
      pulAuthPackage = 0;
      v31 = NCryptSetProperty(v59, L"PinCacheIsGestureRequired", (PBYTE)&pulAuthPackage, 4u, 0);
      LODWORD(v7) = v31;
      v32 = retaddr;
      if ( v31 < 0 )
      {
        v33 = 2297;
        goto LABEL_49;
      }
      v96[0] = (unsigned __int16 *)&v113;
      v96[1] = 0;
      v97 = 1;
      SelfAttestation = NgcFidoCreateSelfAttestation(
                          (int)v114,
                          v65,
                          *((_QWORD *)v134 + 3),
                          *((_DWORD *)v134 + 4),
                          v59,
                          (__int64)&v96[1],
                          (__int64)&v102);
      v109 = SelfAttestation;
      wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
      if ( SelfAttestation >= 0 )
      {
        v64 = L"packed";
        v154 = L"packed";
        v68 = v102;
        v157 = v102;
        v69 = v113;
        v158 = v113;
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcTpmAttestationTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_NgcTpmAttestationTelemetry>::GetImpl'::`2'::impl)
    && v68
    && v69
    && (!wcscmp_0(v64, L"tpm") || !wcscmp_0(v64, L"packed")) )
  {
    v96[0] = (unsigned __int16 *)&hMem;
    v96[1] = 0;
    v97 = 1;
    v71 = CtapCborDecodeCommonAttestation(v68, (_DWORD)v69, (unsigned int)&v96[1], 0, 0, (__int64)ppvOutAuthBuffera);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
    if ( !v71 )
    {
      if ( hMem )
      {
        v159 = 1;
        v160 = hMem;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v96[0] = (unsigned __int16 *)&v126;
  v96[1] = 0;
  v97 = 1;
  CredentialResponse = CtapCborEncodeMakeCredentialResponse(
                         0,
                         (unsigned int)&v153,
                         (unsigned int)&v120,
                         (unsigned int)&v96[1],
                         (__int64)&v105,
                         (__int64)ppvOutAuthBuffera);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v96);
  if ( CredentialResponse )
  {
    LODWORD(v7) = -2147418113;
    v25 = 2351;
    goto LABEL_42;
  }
  memset_0(&pUiInfo, 0, 0x110u);
  v180 = 1;
  LODWORD(v182) = 0;
  pUiInfo.cbSize = 1;
  pUiInfo.hwndParent = (HWND)L"Platform";
  pUiInfo.pszMessageText = L"MicrosoftPlatformProvider";
  v174 = 1;
  v181 = &pUiInfo;
  v73 = v120;
  HIDWORD(v182) = v120;
  v183 = (unsigned __int64)v126;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
  {
    if ( v103 )
    {
      v150[0] = v104;
      v151 = v125;
      v152 = &v145;
      v96[0] = (unsigned __int16 *)&v138;
      v96[1] = 0;
      v97 = 1;
      v74 = CtapCborEncodeCredWithHmacSecret(v150, &v121, &v96[1], &v105);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(v96);
      if ( v74 )
      {
        v7 = (unsigned int)HRESULT_FROM_CBOR_ERROR(v74);
        v26 = retaddr;
        v27 = v7;
        v25 = 2381;
        goto LABEL_44;
      }
      v75 = CtapCborEncodeAppendToArray((unsigned int)&v175, (unsigned int)&v176, v121, v138, (__int64)&v105);
      if ( v75 )
      {
        v7 = (unsigned int)HRESULT_FROM_CBOR_ERROR(v75);
        v26 = retaddr;
        v27 = v7;
        v25 = 2389;
        goto LABEL_44;
      }
    }
    v177 = *(_DWORD *)v122;
    v178 = 16;
  }
  updated = CtapDeviceUpdateControlBlockResponse(v143, &v180);
  v77 = updated;
  if ( updated )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x95E,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)updated,
      ulInAuthBufferSize);
    if ( v77 <= 0 )
    {
      LODWORD(v7) = v77;
      goto LABEL_174;
    }
    LODWORD(v7) = (unsigned __int16)v77;
    goto LABEL_7;
  }
  if ( (Microsoft_Windows_WebAuthNEnableBits & 8) == 0 )
    goto LABEL_174;
  v78 = &word_18015030C;
  if ( v64 )
    LODWORD(v78) = (_DWORD)v64;
  v79 = v95;
  McTemplateU0jzqbr2ddjqbr7tqbr10qbr12_EventWriteTransfer(
    (_DWORD)v126 + 1,
    (unsigned int)&EVENT_WEBAUTHN_NGC_MAKE_CREDENTIAL_RESPONSE,
    v95,
    (_DWORD)v78,
    v163 != 0 ? 0x20 : 0,
    (__int64)v163,
    v164,
    v165,
    (__int64)&v166,
    v167,
    (__int64)v168,
    0,
    v169,
    (__int64)v170,
    v73 - 1,
    (__int64)v126 + 1);
LABEL_175:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcTpmAttestationTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_NgcTpmAttestationTelemetry>::GetImpl'::`2'::impl) )
  {
    v161[0] = 9;
    v161[13] = *(_DWORD *)(v135 + 24);
    LogNgcMakeCredentialStopEvent(
      v79,
      v7,
      v106->hwndParent,
      v80,
      v112,
      v111,
      v110,
      v109,
      (__int64)&v179,
      (__int64)v136,
      (__int64)v161,
      (__int64)&v153);
  }
  else
  {
    LogNgcMakeCredentialStopEvent(
      v79,
      v7,
      v106->hwndParent,
      v80,
      v112,
      v111,
      v110,
      v109,
      (__int64)&v179,
      (__int64)v136,
      0,
      0);
  }
  if ( v14 )
  {
    v81 = CtapSrvRestoreThreadToken(hObject);
    if ( v81 )
    {
      if ( !(_DWORD)v7 )
      {
        if ( v81 > 0 )
          LODWORD(v7) = (unsigned __int16)v81 | 0x80070000;
        else
          LODWORD(v7) = v81;
      }
    }
  }
  v82 = hMem;
  hMem = 0;
  if ( v82 )
    LocalFree(v82);
  wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&v138, 0);
  std::vector<unsigned char>::_Tidy(v132);
  NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v185);
  NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v190);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v139);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v127);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v147);
  v83 = v125;
  v125 = 0;
  if ( v83 )
    LocalFree(v83);
  v84 = v113;
  v113 = 0;
  if ( v84 )
    LocalFree(v84);
  v85 = v128;
  v128 = 0;
  if ( v85 )
    LocalFree(v85);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v129);
  v86 = v114;
  v114 = 0;
  if ( v86 )
    LocalFree(v86);
  v87 = v130;
  v130 = 0;
  if ( v87 )
    LocalFree(v87);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v140);
  v88 = v126;
  v126 = 0;
  if ( v88 )
    LocalFree(v88);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180089b74  mov     [rsp-8+arg_10], rbx
0x180089b79  push    rbp
0x180089b7a  push    rsi
0x180089b7b  push    rdi
0x180089b7c  push    r12
0x180089b7e  push    r13
0x180089b80  push    r14
0x180089b82  push    r15
0x180089b84  lea     rbp, [rsp-5F0h]
0x180089b8c  sub     rsp, 710h
0x180089b93  mov     rax, cs:__security_cookie
0x180089b9a  xor     rax, rsp
0x180089b9d  mov     [rbp+620h+var_40], rax
0x180089ba4  mov     [rbp+620h+var_640], r8d
0x180089ba8  mov     rdi, rdx
0x180089bab  mov     [rbp+620h+var_590], rdx
0x180089bb2  mov     [rbp+620h+var_538], rcx
0x180089bb9  mov     r12b, [rbp+620h+arg_20]
0x180089bc0  mov     r13, [rbp+620h+arg_28]
0x180089bc7  mov     rsi, [rcx+138h]
0x180089bce  mov     [rbp+620h+var_530], rsi
0x180089bd5  mov     r15, [rsi+38h]
0x180089bd9  mov     rax, [r15+98h]
0x180089be0  mov     [rbp+620h+var_588], rax
0x180089be7  lea     r14, [r15+10h]
0x180089beb  mov     qword ptr [rbp+620h+var_6A0], r14
0x180089bef  lea     rax, [rdx+30h]
0x180089bf3  mov     [rbp+620h+var_580], rax
0x180089bfa  mov     rax, [rdx+20h]
0x180089bfe  mov     [rbp+620h+var_648], rax
0x180089c02  mov     rbx, [rdx+28h]
0x180089c06  xor     ecx, ecx
0x180089c08  mov     [rbp+620h+var_5D8], rcx
0x180089c0c  mov     [rbp+620h+var_600], ecx
0x180089c0f  mov     [rbp+620h+var_64C], ecx
0x180089c12  mov     [rbp+620h+var_560], rcx
0x180089c19  xorps   xmm0, xmm0
0x180089c1c  xor     eax, eax
0x180089c1e  movups  [rbp+620h+var_500], xmm0
0x180089c25  mov     [rbp+620h+var_4F0], rax
0x180089c2c  mov     [rbp+620h+hKey], rcx
0x180089c30  mov     [rbp+620h+var_608], ecx
0x180089c33  mov     [rbp+620h+var_5B8], rcx
0x180089c37  movups  [rbp+620h+var_1D0], xmm0
0x180089c3e  xor     edx, edx; Val
0x180089c40  lea     r8d, [rcx+58h]; Size
0x180089c44  lea     rcx, [rbp+620h+var_340]; void *
0x180089c4b  call    memset_0
0x180089c50  xor     eax, eax
0x180089c52  mov     [rbp+620h+var_604], eax
0x180089c55  mov     [rbp+620h+var_620], rax
0x180089c59  xor     edx, edx; Val
0x180089c5b  mov     r8d, 0C0h; Size
0x180089c61  lea     rcx, [rbp+620h+var_4D0]; void *
0x180089c68  call    memset_0
0x180089c6d  xor     edx, edx
0x180089c6f  mov     [rbp+620h+var_5C0], rdx
0x180089c73  mov     [rbp+620h+var_5C8], rdx
0x180089c77  mov     [rbp+620h+var_610], edx
0x180089c7a  mov     dword ptr [rbp+620h+var_658], edx
0x180089c7d  mov     [rbp+620h+var_628], rdx
0x180089c81  mov     [rbp+620h+var_650], edx
0x180089c84  mov     [rbp+620h+var_5E0], rdx
0x180089c88  mov     dword ptr [rbp+620h+var_1C0+4], edx
0x180089c8e  xorps   xmm0, xmm0
0x180089c91  movdqu  [rbp+620h+var_1A8], xmm0
0x180089c99  xorps   xmm1, xmm1
0x180089c9c  movups  xmmword ptr [rbp+620h+pbComputedHash], xmm1
0x180089ca3  movups  [rbp+620h+var_90], xmm1
0x180089caa  mov     [rbp+620h+pcbComputedHash], edx
0x180089cad  mov     [rbp+620h+var_508], rdx
0x180089cb4  mov     [rbp+620h+var_5D0], rdx
0x180089cb8  mov     [rbp+620h+var_62C], edx
0x180089cbb  mov     [rbp+620h+var_630], edx
0x180089cbe  mov     [rbp+620h+var_634], edx
0x180089cc1  mov     [rbp+620h+var_638], edx
0x180089cc4  mov     [rbp+620h+hObject], rdx
0x180089ccb  mov     [rbp+620h+hProvider], rdx
0x180089ccf  mov     dword ptr [rbp+620h+var_63C], edx
0x180089cd2  mov     [rbp+620h+cbOutput], 4
0x180089cd9  mov     [rbp+620h+var_568], rdx
0x180089ce0  lea     rcx, [rbp+620h+var_100]
0x180089ce7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180089cec  lea     rcx, [rbp+620h+var_E0]
0x180089cf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180089cf8  movdqa  [rbp+620h+var_C0], xmm1
0x180089d00  mov     [rbp+620h+var_B0], rdx
0x180089d07  xor     eax, eax
0x180089d09  mov     [rbp+620h+var_A8], rax
0x180089d10  lea     rcx, [rbp+620h+var_160]
0x180089d17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180089d1c  lea     rcx, [rbp+620h+var_140]
0x180089d23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180089d28  movdqa  [rbp+620h+var_120], xmm1
0x180089d30  mov     [rbp+620h+var_110], rdx
0x180089d37  xor     eax, eax
0x180089d39  mov     [rbp+620h+var_108], rax
0x180089d40  mov     dword ptr [rbp+620h+var_5F8], edx
0x180089d43  xorps   xmm0, xmm0
0x180089d46  movdqu  xmmword ptr [rbp+620h+var_5A8], xmm0
0x180089d4b  mov     [rbp+620h+var_598], rdx
0x180089d52  mov     dword ptr [rbp+620h+var_658+4], edx
0x180089d55  lea     r8d, [rdx+40h]; Size
0x180089d59  lea     rcx, [rbp+620h+pbOutput]; void *
0x180089d60  call    memset_0
0x180089d65  xorps   xmm0, xmm0
0x180089d68  movups  [rbp+620h+var_528], xmm0
0x180089d6f  movups  [rbp+620h+var_518], xmm0
0x180089d76  xor     eax, eax
0x180089d78  mov     [rbp+620h+var_5FC], eax
0x180089d7b  mov     [rbp+620h+var_570], rax
0x180089d82  mov     [rbp+620h+var_4E4], eax
0x180089d88  xor     edx, edx; Val
0x180089d8a  mov     r8d, 0C8h; Size
0x180089d90  lea     rcx, [rbp+620h+var_410]; void *
0x180089d97  call    memset_0
0x180089d9c  mov     [rbp+620h+hMem], 0
0x180089da4  test    cs:Microsoft_Windows_WebAuthNEnableBits, 8
0x180089dab  jz      short loc_180089DBC
0x180089dad  mov     r8, r14
0x180089db0  lea     rdx, EVENT_WEBAUTHN_NGC_MAKE_CREDENTIAL_START
0x180089db7  call    McTemplateU0j_EventWriteTransfer
0x180089dbc  lea     rdx, [rbp+620h+hObject]
0x180089dc3  mov     rcx, [rsi+40h]; Token
0x180089dc7  call    CtapSrvImpersonateRpcToken
0x180089dcc  mov     esi, eax
0x180089dce  mov     rcx, [rbp+628h]; this
0x180089dd5  xor     edx, edx; Val
0x180089dd7  test    eax, eax
0x180089dd9  jz      short loc_180089E0B
0x180089ddb  mov     r9d, eax; char *
0x180089dde  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180089de5  mov     edx, 754h; void *
0x180089dea  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180089def  xor     r13d, r13d
0x180089df2  mov     r14d, r13d
0x180089df5  test    esi, esi
0x180089df7  jle     loc_18008AFE9
0x180089dfd  movzx   esi, si
0x180089e00  or      esi, 80070000h
0x180089e06  jmp     loc_18008AFE9
0x180089e0b  mov     r14d, 1
0x180089e11  mov     rsi, [rbp+620h+var_648]
0x180089e15  test    rsi, rsi
0x180089e18  jz      loc_18008AFC6
0x180089e1e  cmp     [rsi+8], rdx
0x180089e22  jz      loc_18008AFC6
0x180089e28  test    rbx, rbx
0x180089e2b  jz      loc_18008AFC6
0x180089e31  cmp     [rbx+4], edx
0x180089e34  jz      loc_18008AFC6
0x180089e3a  cmp     [rbx+8], rdx
0x180089e3e  jz      loc_18008AFC6
0x180089e44  cmp     [rdi+30h], edx
0x180089e47  jz      loc_18008AFC6
0x180089e4d  cmp     [rdi+38h], rdx
0x180089e51  jz      loc_18008AFC6
0x180089e57  cmp     [rdi+18h], rdx
0x180089e5b  jz      loc_18008AFC6
0x180089e61  cmp     [rdi+10h], edx
0x180089e64  jz      loc_18008AFC6
0x180089e6a  cmp     [r15+0B0h], edx
0x180089e71  jz      loc_18008A0A1
0x180089e77  cmp     [rbp+620h+var_640], edx
0x180089e7a  jnz     loc_18008A0A1
0x180089e80  mov     r8d, 88h; Size
0x180089e86  lea     rcx, [rbp+620h+pUiInfo]; void *
0x180089e8d  call    memset_0
0x180089e92  lea     rax, [rbp+620h+pUiInfo]
0x180089e99  mov     [rbp+620h+var_550], rax
0x180089ea0  mov     [rbp+620h+pulAuthPackage], 0FFFFDA86h
0x180089ea7  xor     eax, eax
0x180089ea9  mov     [rbp+620h+var_540], eax
0x180089eaf  mov     [rbp+620h+pv], rax
0x180089eb3  lea     rax, word_18015030C
0x180089eba  mov     [rbp+620h+var_690], rax
0x180089ebe  mov     rcx, [rdi+20h]
0x180089ec2  lea     rdx, [rbp+620h+var_690]
0x180089ec6  mov     rcx, [rcx+8]
0x180089eca  call    _GetMakeCredBrowserInPrivateModeString
0x180089ecf  mov     esi, eax
0x180089ed1  mov     rcx, [rbp+628h]; this
0x180089ed8  test    eax, eax
0x180089eda  jns     short loc_180089F19
0x180089edc  mov     edx, 779h; void *
0x180089ee1  mov     r9d, eax; char *
0x180089ee4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180089eeb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180089ef0  nop
0x180089ef1  xor     r13d, r13d
0x180089ef4  mov     rcx, [rbp+620h+pv]; pv
0x180089ef8  test    rcx, rcx
0x180089efb  mov     [rbp+620h+pv], r13
0x180089eff  jz      short loc_180089F08
0x180089f01  call    cs:__imp_CoTaskMemFree
0x180089f07  nop
0x180089f08  lea     rcx, [rbp+620h+var_550]
0x180089f0f  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x180089f14  jmp     loc_18008AFE9
0x180089f19  lea     r9, [rbp+620h+pUiInfo]; struct CREDUI_INFO_INTERNAL *
0x180089f20  mov     r8, [rbp+620h+var_690]; unsigned __int16 *
0x180089f24  mov     edx, 40Ch; unsigned int
0x180089f29  mov     rcx, [rbp+620h+var_588]
0x180089f30  mov     rcx, [rcx]; HWND
0x180089f33  call    ?I_WebAuthNCtapBuildMakeCredentialCredUiInfo@@YAJPEAUHWND__@@KPEBGPEAUCREDUI_INFO_INTERNAL@@@Z; I_WebAuthNCtapBuildMakeCredentialCredUiInfo(HWND__ *,ulong,ushort const *,CREDUI_INFO_INTERNAL *)
0x180089f38  mov     esi, eax
0x180089f3a  mov     rcx, [rbp+628h]
0x180089f41  test    eax, eax
0x180089f43  jns     short loc_180089F4C
0x180089f45  mov     edx, 77Fh
0x180089f4a  jmp     short loc_180089EE1
0x180089f4c  mov     rsi, [rbp+620h+var_530]
0x180089f53  mov     rax, [rsi+38h]
0x180089f57  movups  xmm0, xmmword ptr [rax+10h]
0x180089f5b  movdqu  xmmword ptr [rbp+620h+var_690], xmm0
0x180089f60  lea     rdx, [rbp+620h+var_690]
0x180089f64  lea     rcx, [rbp+620h+var_5F0]
0x180089f68  call    ??$open@V?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@0@U_GUID@@@Z; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(_GUID)
0x180089f6d  lea     rcx, [rbp+620h+var_5F0]
0x180089f71  call    ??B?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::operator bool(void)
0x180089f76  xor     ecx, ecx
0x180089f78  test    al, al
0x180089f7a  jz      short loc_180089FBC
0x180089f7c  lea     rdx, [rbp+620h+var_690]
0x180089f80  lea     rcx, [rbp+620h+var_5F0]
0x180089f84  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(void)
0x180089f89  mov     rcx, [rax]
0x180089f8c  mov     dword ptr [rcx+114h], 8
0x180089f96  lea     rcx, [rbp+620h+var_690]
0x180089f9a  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(void)
0x180089f9f  lea     rcx, aWebauthnuiperf; "WebAuthNUIPerformanceTest::reason::ui_i"...
0x180089fa6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180089fab  mov     r8, rax
0x180089fae  mov     edx, r14d
0x180089fb1  lea     rcx, [rbp+620h+var_5F0]
0x180089fb5  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::set_flag(ushort,char const *)
0x180089fba  xor     ecx, ecx
0x180089fbc  cmp     [r15+1CCh], ecx
0x180089fc3  jz      short loc_180089FCD
0x180089fc5  bts     dword ptr [rbp+620h+pUiInfo.hbmBanner], 13h
0x180089fcd  lea     rax, [rbp+620h+pv]
0x180089fd1  mov     [rbp+620h+var_690], rax
0x180089fd5  mov     [rbp+620h+var_690+8], rcx
0x180089fd9  mov     [rbp+620h+var_680], r14b
0x180089fdd  mov     r9, [rsi+38h]
0x180089fe1  mov     [rsp+740h+dwFlags], 8000210h; dwFlags
0x180089fe9  mov     [rsp+740h+pfSave], rcx; pfSave
0x180089fee  lea     rax, [rbp+620h+var_540]
0x180089ff5  mov     [rsp+740h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180089ffa  lea     rax, [rbp+620h+var_690+8]
0x180089ffe  mov     [rsp+740h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18008a003  mov     eax, [r9+88h]
0x18008a00a  mov     [rsp+740h+ulInAuthBufferSize], eax; unsigned int
0x18008a00e  mov     r9, [r9+90h]; pvInAuthBuffer
0x18008a015  lea     r8, [rbp+620h+pulAuthPackage]; pulAuthPackage
0x18008a019  xor     edx, edx; dwAuthError
0x18008a01b  lea     rcx, [rbp+620h+pUiInfo]; pUiInfo
0x18008a022  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18008a028  mov     esi, eax
0x18008a02a  lea     rcx, [rbp+620h+var_690]
0x18008a02e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008a033  mov     rcx, [rbp+628h]; this
0x18008a03a  test    esi, esi
0x18008a03c  jz      short loc_18008A071
0x18008a03e  mov     r9d, esi; char *
0x18008a041  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18008a048  mov     edx, 797h; void *
0x18008a04d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18008a052  xor     r13d, r13d
0x18008a055  test    esi, esi
0x18008a057  jle     short loc_18008A062
0x18008a059  movzx   esi, si
0x18008a05c  or      esi, 80070000h
0x18008a062  lea     rcx, [rbp+620h+var_5F0]
0x18008a066  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x18008a06b  nop
0x18008a06c  jmp     loc_180089EF4
0x18008a071  lea     rcx, [rbp+620h+var_5F0]
0x18008a075  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x18008a07a  nop
0x18008a07b  mov     rcx, [rbp+620h+pv]; pv
0x18008a07f  xor     eax, eax
0x18008a081  mov     [rbp+620h+pv], rax
0x18008a085  test    rcx, rcx
0x18008a088  jz      short loc_18008A091
0x18008a08a  call    cs:__imp_CoTaskMemFree
0x18008a090  nop
0x18008a091  lea     rcx, [rbp+620h+var_550]
0x18008a098  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x18008a09d  mov     rsi, [rbp+620h+var_648]
0x18008a0a1  mov     [rbp+620h+pcbComputedHash], 20h ; ' '
0x18008a0a8  lea     rax, [rbp+620h+pcbComputedHash]
0x18008a0ac  mov     [rsp+740h+pulOutAuthBufferSize], rax; pcbComputedHash
0x18008a0b1  lea     rax, [rbp+620h+pbComputedHash]
0x18008a0b8  mov     [rsp+740h+ppvOutAuthBuffer], rax; pbComputedHash
0x18008a0bd  mov     eax, [rdi+4]
0x18008a0c0  mov     [rsp+740h+ulInAuthBufferSize], eax; int
0x18008a0c4  mov     r9, [rdi+8]; pbEncoded
0x18008a0c8  xor     r8d, r8d; pvReserved
0x18008a0cb  xor     edx, edx; dwFlags
  ... truncated ...
```
