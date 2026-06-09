# TokenBindingHelper::IsKeyGuardWithAttestationAvailable(AadContextFunctions *,int &)

- ea: `0x18003e89c`
- end: `0x18003ecd4`
- name: `?IsKeyGuardWithAttestationAvailable@TokenBindingHelper@@SAJPEAVAadContextFunctions@@AEAH@Z`
- size: `1080`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004861c`

## callees

- `0x180003c20`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x18001cf08`
- `0x18003d2b4`
- `0x18003e89c`
- `0x180071e14`
- `0x180076b68`

## import_xrefs

- `ncrypt!NCryptCreatePersistedKey` at `0x18003ea0e`
- `ncrypt!NCryptCreatePersistedKey` at `0x18003ea86`
- `ncrypt!NCryptCreatePersistedKey` at `0x18003ea0e`
- `ncrypt!NCryptCreatePersistedKey` at `0x18003ea86`
- `ncrypt!NCryptCreateClaim` at `0x18003eb47`
- `ncrypt!NCryptCreateClaim` at `0x18003eb47`
- `ncrypt!NCryptDeleteKey` at `0x18003ebbd`
- `ncrypt!NCryptDeleteKey` at `0x18003ec26`
- `ncrypt!NCryptDeleteKey` at `0x18003ebbd`
- `ncrypt!NCryptDeleteKey` at `0x18003ec26`
- `ncrypt!NCryptSetProperty` at `0x18003eac1`
- `ncrypt!NCryptSetProperty` at `0x18003eac1`
- `ncrypt!NCryptFreeObject` at `0x18003ec6c`
- `ncrypt!NCryptFreeObject` at `0x18003ec7b`
- `ncrypt!NCryptFreeObject` at `0x18003ec8a`
- `ncrypt!NCryptFreeObject` at `0x18003ec6c`
- `ncrypt!NCryptFreeObject` at `0x18003ec7b`
- `ncrypt!NCryptFreeObject` at `0x18003ec8a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18003e9bf`
- `ncrypt!NCryptOpenStorageProvider` at `0x18003e9bf`

## string_xrefs

- `0x18003e8ef`: `TokenBindingHelper::IsKeyGuardWithAttestationAvailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TokenBindingHelper::IsKeyGuardWithAttestationAvailable(struct AadContextFunctions *a1, int *a2)
{
  SECURITY_STATUS v4; // edi
  SECURITY_STATUS v5; // eax
  __int64 v6; // rdx
  LPCWSTR *v7; // rax
  SECURITY_STATUS v8; // esi
  DWORD v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  DWORD dwLegacyKeySpec[2]; // [rsp+20h] [rbp-99h]
  DWORD dwLegacyKeySpeca[2]; // [rsp+20h] [rbp-99h]
  DWORD dwLegacyKeySpecb[2]; // [rsp+20h] [rbp-99h]
  int v16; // [rsp+30h] [rbp-89h]
  __int64 v17; // [rsp+30h] [rbp-89h]
  __int64 v18; // [rsp+30h] [rbp-89h]
  unsigned int v19; // [rsp+50h] [rbp-69h] BYREF
  NCRYPT_KEY_HANDLE hObject; // [rsp+58h] [rbp-61h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-59h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR pszKeyName; // [rsp+70h] [rbp-49h] BYREF
  BYTE pbInput[8]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v25; // [rsp+80h] [rbp-39h] BYREF
  _DWORD v26[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 *v27; // [rsp+90h] [rbp-29h]
  _DWORD v28[2]; // [rsp+98h] [rbp-21h] BYREF
  _DWORD *v29; // [rsp+A0h] [rbp-19h]
  const char *v30[6]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v31; // [rsp+D8h] [rbp+1Fh] BYREF
  int v32; // [rsp+E0h] [rbp+27h]
  WCHAR v33; // [rsp+E4h] [rbp+2Bh]

  v19 = 0;
  phProvider = 0;
  phKey = 0;
  hObject = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pszKeyName);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v30,
    (int)"tokenbindinghelper.cpp",
    (int)"TokenBindingHelper::IsKeyGuardWithAttestationAvailable",
    (int)&v19);
  *a2 = 0;
  if ( !a1 )
  {
    v19 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "tokenbindinghelper.cpp", 1691, "NTSTATUS", &base);
    goto LABEL_22;
  }
  v4 = StringUtility::CreateGuid(&pszKeyName);
  if ( v4 < 0 )
  {
    v16 = 1703;
LABEL_5:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v4, "tokenbindinghelper.cpp", v16, "HRESULT", &base);
    v19 = v4 & 0xAFFFFFFF | 0x40000000;
    goto LABEL_22;
  }
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( v4 < 0 )
  {
    v16 = 1704;
    goto LABEL_5;
  }
  v5 = NCryptCreatePersistedKey(phProvider, &phKey, L"ECDSA_P256", pszKeyName, 0, 0x20080u);
  if ( v5 < 0 )
  {
    dwLegacyKeySpec[0] = v5;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      *(_QWORD *)dwLegacyKeySpec,
      "tokenbindinghelper.cpp",
      1759,
      "KeyGuard is not enabled.",
      &base);
  }
  else
  {
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "tokenbindinghelper.cpp", 1710, "KeyGuard is enabled", &base);
    v7 = (LPCWSTR *)ATL::operator+(&v25, v6, &pszKeyName);
    v8 = NCryptCreatePersistedKey(phProvider, &hObject, L"ECDSA_P256", *v7, 0, 0x20080u);
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    if ( v8 < 0 )
      goto LABEL_17;
    *(_DWORD *)pbInput = 16;
    v8 = NCryptSetProperty(hObject, L"Key Usage", pbInput, 4u, 0);
    if ( v8 >= 0 )
    {
      v31 = *(_QWORD *)L"SHA256";
      v32 = *(_DWORD *)L"56";
      v33 = aSha256[6];
      v26[0] = 14;
      v26[1] = 90;
      v27 = &v31;
      v28[0] = 0;
      v28[1] = 1;
      v29 = v26;
      LODWORD(v25) = 0;
      v9 = NCryptCreateClaim(phKey, hObject, 6, v28, 0, 0, &v25, 0);
      if ( v9 == -2146893783 )
      {
        LODWORD(v18) = 1730;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "tokenbindinghelper.cpp",
          v18,
          "KeyGuard attestation is NOT supported.",
          &base);
      }
      else
      {
        LODWORD(v18) = 1734;
        dwLegacyKeySpecb[0] = v9;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          *(_QWORD *)dwLegacyKeySpecb,
          "tokenbindinghelper.cpp",
          v18,
          "KeyGuard attestation is detected as supported.",
          &base);
        *a2 = 1;
      }
    }
    if ( NCryptDeleteKey(hObject, 0) >= 0 )
      hObject = 0;
    if ( v8 < 0 )
    {
LABEL_17:
      LODWORD(v17) = 1748;
      dwLegacyKeySpeca[0] = v8;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        *(_QWORD *)dwLegacyKeySpeca,
        "tokenbindinghelper.cpp",
        v17,
        "KeyGuard attestation capability detection FAILED",
        &base);
      if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        McTemplateU0d_EventWriteTransfer(
          v10,
          Aad_CloudAPPlugin_Token_Binding_KeyGuard_Detection_Failure,
          (unsigned int)v8);
    }
    if ( NCryptDeleteKey(phKey, 0) >= 0 )
      phKey = 0;
  }
LABEL_22:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( hObject )
    NCryptFreeObject(hObject);
  v11 = v19;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v30);
  ATL::CStringData::Release((ATL::CStringData *)(pszKeyName - 12));
  return v11;
}

```

## disassembly

```asm
0x18003e89c  mov     [rsp-8+arg_0], rbx
0x18003e8a1  mov     [rsp-8+arg_10], rsi
0x18003e8a6  push    rbp
0x18003e8a7  push    rdi
0x18003e8a8  push    r12
0x18003e8aa  push    r14
0x18003e8ac  push    r15
0x18003e8ae  lea     rbp, [rsp-37h]
0x18003e8b3  sub     rsp, 0F0h
0x18003e8ba  mov     rax, cs:__security_cookie
0x18003e8c1  xor     rax, rsp
0x18003e8c4  mov     [rbp+57h+var_28], rax
0x18003e8c8  mov     r14, rdx
0x18003e8cb  mov     rbx, rcx
0x18003e8ce  xor     r15d, r15d
0x18003e8d1  mov     [rbp+57h+var_C0], r15d
0x18003e8d5  mov     [rbp+57h+phProvider], r15
0x18003e8d9  mov     [rbp+57h+phKey], r15
0x18003e8dd  mov     [rbp+57h+hObject], r15
0x18003e8e1  lea     rcx, [rbp+57h+pszKeyName]; void *
0x18003e8e5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003e8ea  nop
0x18003e8eb  lea     r9, [rbp+57h+var_C0]
0x18003e8ef  lea     r8, aTokenbindinghe_3; "TokenBindingHelper::IsKeyGuardWithAttes"...
0x18003e8f6  lea     r12, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003e8fd  mov     rdx, r12
0x18003e900  lea     rcx, [rbp+57h+var_68]
0x18003e904  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18003e909  nop
0x18003e90a  mov     [r14], r15d
0x18003e90d  test    rbx, rbx
0x18003e910  jnz     short loc_18003E951
0x18003e912  mov     ecx, 0C000000Dh
0x18003e917  mov     [rbp+57h+var_C0], ecx
0x18003e91a  lea     rbx, base
0x18003e921  mov     [rsp+110h+var_D0], rbx
0x18003e926  lea     rax, aNtstatus; "NTSTATUS"
0x18003e92d  mov     [rsp+110h+var_D8], rax
0x18003e932  mov     dword ptr [rsp+110h+var_E0], 69Bh
0x18003e93a  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003e93f  mov     [rsp+110h+dwLegacyKeySpec], ecx
0x18003e943  lea     ebx, [r15+2]
0x18003e947  mov     r9d, ebx
0x18003e94a  mov     ecx, ebx
0x18003e94c  jmp     loc_18003EC55
0x18003e951  lea     rcx, [rbp+57h+pszKeyName]
0x18003e955  call    ?CreateGuid@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; StringUtility::CreateGuid(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003e95a  mov     edi, eax
0x18003e95c  test    eax, eax
0x18003e95e  jns     short loc_18003E9B1
0x18003e960  lea     rbx, base
0x18003e967  mov     [rsp+110h+var_D0], rbx
0x18003e96c  lea     rax, aHresult; "HRESULT"
0x18003e973  mov     [rsp+110h+var_D8], rax
0x18003e978  mov     dword ptr [rsp+110h+var_E0], 6A7h
0x18003e980  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003e985  mov     [rsp+110h+dwLegacyKeySpec], edi
0x18003e989  mov     ebx, 2
0x18003e98e  mov     r9d, ebx
0x18003e991  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003e998  xor     edx, edx
0x18003e99a  mov     ecx, ebx
0x18003e99c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003e9a1  btr     edi, 1Ch
0x18003e9a5  bts     edi, 1Eh
0x18003e9a9  mov     [rbp+57h+var_C0], edi
0x18003e9ac  jmp     loc_18003EC63
0x18003e9b1  xor     r8d, r8d; dwFlags
0x18003e9b4  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18003e9bb  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18003e9bf  call    cs:__imp_NCryptOpenStorageProvider
0x18003e9c5  mov     edi, eax
0x18003e9c7  test    eax, eax
0x18003e9c9  jns     short loc_18003E9ED
0x18003e9cb  lea     rbx, base
0x18003e9d2  mov     [rsp+110h+var_D0], rbx
0x18003e9d7  lea     rax, aHresult; "HRESULT"
0x18003e9de  mov     [rsp+110h+var_D8], rax
0x18003e9e3  mov     dword ptr [rsp+110h+var_E0], 6A8h
0x18003e9eb  jmp     short loc_18003E980
0x18003e9ed  mov     esi, 20080h
0x18003e9f2  mov     [rsp+110h+dwFlags], esi; dwFlags
0x18003e9f6  mov     [rsp+110h+dwLegacyKeySpec], r15d; dwLegacyKeySpec
0x18003e9fb  mov     r9, [rbp+57h+pszKeyName]; pszKeyName
0x18003e9ff  lea     r8, pszAlgId; "ECDSA_P256"
0x18003ea06  lea     rdx, [rbp+57h+phKey]; phKey
0x18003ea0a  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18003ea0e  call    cs:__imp_NCryptCreatePersistedKey
0x18003ea14  lea     rbx, base
0x18003ea1b  mov     edi, 4
0x18003ea20  mov     [rsp+110h+var_D0], rbx
0x18003ea25  mov     r9d, edi
0x18003ea28  test    eax, eax
0x18003ea2a  js      loc_18003EC36
0x18003ea30  lea     rax, aKeyguardIsEnab; "KeyGuard is enabled"
0x18003ea37  mov     [rsp+110h+var_D8], rax
0x18003ea3c  mov     dword ptr [rsp+110h+var_E0], 6AEh
0x18003ea44  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003ea49  mov     qword ptr [rsp+110h+dwLegacyKeySpec], r15
0x18003ea4e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003ea55  xor     edx, edx
0x18003ea57  mov     ecx, edi
0x18003ea59  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003ea5e  lea     r8, [rbp+57h+pszKeyName]
0x18003ea62  lea     rcx, [rbp+57h+var_90]
0x18003ea66  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003ea6b  mov     [rsp+110h+dwFlags], esi; dwFlags
0x18003ea6f  mov     [rsp+110h+dwLegacyKeySpec], r15d; dwLegacyKeySpec
0x18003ea74  mov     r9, [rax]; pszKeyName
0x18003ea77  lea     r8, pszAlgId; "ECDSA_P256"
0x18003ea7e  lea     rdx, [rbp+57h+hObject]; phKey
0x18003ea82  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18003ea86  call    cs:__imp_NCryptCreatePersistedKey
0x18003ea8c  mov     esi, eax
0x18003ea8e  mov     rcx, [rbp+57h+var_90]
0x18003ea92  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003ea96  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003ea9b  test    esi, esi
0x18003ea9d  js      loc_18003EBCF
0x18003eaa3  mov     dword ptr [rbp+57h+pbInput], 10h
0x18003eaaa  mov     [rsp+110h+dwLegacyKeySpec], r15d; dwFlags
0x18003eaaf  mov     r9d, edi; cbInput
0x18003eab2  lea     r8, [rbp+57h+pbInput]; pbInput
0x18003eab6  lea     rdx, aKeyUsage; "Key Usage"
0x18003eabd  mov     rcx, [rbp+57h+hObject]; hObject
0x18003eac1  call    cs:__imp_NCryptSetProperty
0x18003eac7  mov     esi, eax
0x18003eac9  test    eax, eax
0x18003eacb  js      loc_18003EBB7
0x18003ead1  movsd   xmm0, qword ptr cs:aSha256; "SHA256"
0x18003ead9  movsd   [rbp+57h+var_38], xmm0
0x18003eade  mov     eax, dword ptr cs:aSha256+8; "56"
0x18003eae4  mov     [rbp+57h+var_30], eax
0x18003eae7  movzx   eax, word ptr cs:aSha256+0Ch; ""
0x18003eaee  mov     [rbp+57h+var_2C], ax
0x18003eaf2  mov     [rbp+57h+var_88], 0Eh
0x18003eaf9  mov     [rbp+57h+var_84], 5Ah ; 'Z'
0x18003eb00  lea     rax, [rbp+57h+var_38]
0x18003eb04  mov     [rbp+57h+var_80], rax
0x18003eb08  mov     [rbp+57h+var_78], r15d
0x18003eb0c  mov     [rbp+57h+var_74], 1
0x18003eb13  lea     rax, [rbp+57h+var_88]
0x18003eb17  mov     [rbp+57h+var_70], rax
0x18003eb1b  mov     dword ptr [rbp+57h+var_90], r15d
0x18003eb1f  mov     dword ptr [rsp+110h+var_D8], r15d
0x18003eb24  lea     rax, [rbp+57h+var_90]
0x18003eb28  mov     [rsp+110h+var_E0], rax
0x18003eb2d  mov     [rsp+110h+dwFlags], r15d
0x18003eb32  mov     qword ptr [rsp+110h+dwLegacyKeySpec], r15
0x18003eb37  lea     r9, [rbp+57h+var_78]
0x18003eb3b  lea     r8d, [rdi+2]
0x18003eb3f  mov     rdx, [rbp+57h+hObject]
0x18003eb43  mov     rcx, [rbp+57h+phKey]
0x18003eb47  call    cs:__imp_NCryptCreateClaim
0x18003eb4d  mov     [rsp+110h+var_D0], rbx
0x18003eb52  mov     r9d, edi
0x18003eb55  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003eb5c  xor     edx, edx
0x18003eb5e  cmp     eax, 80090029h
0x18003eb63  jnz     short loc_18003EB8C
0x18003eb65  lea     rax, aKeyguardAttest_0; "KeyGuard attestation is NOT supported."
0x18003eb6c  mov     [rsp+110h+var_D8], rax
0x18003eb71  mov     dword ptr [rsp+110h+var_E0], 6C2h
0x18003eb79  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003eb7e  mov     qword ptr [rsp+110h+dwLegacyKeySpec], r15
0x18003eb83  mov     ecx, edi
0x18003eb85  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003eb8a  jmp     short loc_18003EBB7
0x18003eb8c  lea     rcx, aKeyguardAttest_1; "KeyGuard attestation is detected as sup"...
0x18003eb93  mov     [rsp+110h+var_D8], rcx
0x18003eb98  mov     dword ptr [rsp+110h+var_E0], 6C6h
0x18003eba0  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003eba5  mov     [rsp+110h+dwLegacyKeySpec], eax
0x18003eba9  mov     ecx, edi
0x18003ebab  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003ebb0  mov     dword ptr [r14], 1
0x18003ebb7  xor     edx, edx; dwFlags
0x18003ebb9  mov     rcx, [rbp+57h+hObject]; hKey
0x18003ebbd  call    cs:__imp_NCryptDeleteKey
0x18003ebc3  test    eax, eax
0x18003ebc5  js      short loc_18003EBCB
0x18003ebc7  mov     [rbp+57h+hObject], r15
0x18003ebcb  test    esi, esi
0x18003ebcd  jns     short loc_18003EC20
0x18003ebcf  mov     [rsp+110h+var_D0], rbx
0x18003ebd4  lea     rax, aKeyguardAttest; "KeyGuard attestation capability detecti"...
0x18003ebdb  mov     [rsp+110h+var_D8], rax
0x18003ebe0  mov     dword ptr [rsp+110h+var_E0], 6D4h
0x18003ebe8  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003ebed  mov     [rsp+110h+dwLegacyKeySpec], esi
0x18003ebf1  mov     ebx, 2
0x18003ebf6  mov     r9d, ebx
0x18003ebf9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003ec00  xor     edx, edx
0x18003ec02  mov     ecx, ebx
0x18003ec04  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003ec09  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x18003ec0f  jz      short loc_18003EC20
0x18003ec11  mov     r8d, esi
0x18003ec14  lea     rdx, Aad_CloudAPPlugin_Token_Binding_KeyGuard_Detection_Failure
0x18003ec1b  call    McTemplateU0d_EventWriteTransfer
0x18003ec20  xor     edx, edx; dwFlags
0x18003ec22  mov     rcx, [rbp+57h+phKey]; hKey
0x18003ec26  call    cs:__imp_NCryptDeleteKey
0x18003ec2c  test    eax, eax
0x18003ec2e  js      short loc_18003EC63
0x18003ec30  mov     [rbp+57h+phKey], r15
0x18003ec34  jmp     short loc_18003EC63
0x18003ec36  lea     rcx, aKeyguardIsNotE; "KeyGuard is not enabled."
0x18003ec3d  mov     [rsp+110h+var_D8], rcx
0x18003ec42  mov     dword ptr [rsp+110h+var_E0], 6DFh
0x18003ec4a  mov     qword ptr [rsp+110h+dwFlags], r12
0x18003ec4f  mov     [rsp+110h+dwLegacyKeySpec], eax
0x18003ec53  mov     ecx, edi
0x18003ec55  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003ec5c  xor     edx, edx
0x18003ec5e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003ec63  mov     rcx, [rbp+57h+phProvider]; hObject
0x18003ec67  test    rcx, rcx
0x18003ec6a  jz      short loc_18003EC72
0x18003ec6c  call    cs:__imp_NCryptFreeObject
0x18003ec72  mov     rcx, [rbp+57h+phKey]; hObject
0x18003ec76  test    rcx, rcx
0x18003ec79  jz      short loc_18003EC81
0x18003ec7b  call    cs:__imp_NCryptFreeObject
0x18003ec81  mov     rcx, [rbp+57h+hObject]; hObject
0x18003ec85  test    rcx, rcx
0x18003ec88  jz      short loc_18003EC90
0x18003ec8a  call    cs:__imp_NCryptFreeObject
0x18003ec90  mov     ebx, [rbp+57h+var_C0]
0x18003ec93  lea     rcx, [rbp+57h+var_68]
0x18003ec97  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18003ec9c  nop
0x18003ec9d  mov     rcx, [rbp+57h+pszKeyName]
0x18003eca1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003eca5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003ecaa  mov     eax, ebx
0x18003ecac  mov     rcx, [rbp+57h+var_28]
0x18003ecb0  xor     rcx, rsp; StackCookie
0x18003ecb3  call    __security_check_cookie
0x18003ecb8  lea     r11, [rsp+110h+var_20]
0x18003ecc0  mov     rbx, [r11+30h]
0x18003ecc4  mov     rsi, [r11+40h]
0x18003ecc8  mov     rsp, r11
0x18003eccb  pop     r15
0x18003eccd  pop     r14
0x18003eccf  pop     r12
0x18003ecd1  pop     rdi
0x18003ecd2  pop     rbp
0x18003ecd3  retn
```
