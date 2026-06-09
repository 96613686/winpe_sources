# CertificatePrivateKeyHelper::CreateKey(unsigned __int64,ushort const *,ushort const *,CertificatePrivateKeyHelper::PrivateKeyUIPolicy const &,ulong,bool,unsigned __int64 &)

- ea: `0x180080e34`
- end: `0x180081202`
- name: `?CreateKey@CertificatePrivateKeyHelper@@SAJ_KPEBG1AEBUPrivateKeyUIPolicy@1@K_NAEA_K@Z`
- size: `974`
- prototype: `__int64 __usercall@<rax>(NCRYPT_PROV_HANDLE hProvider@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *@<r9>, unsigned int, bool, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080ccc`
- `0x180081208`

## callees

- `0x1800011b4`
- `0x180001cfc`
- `0x1800022bc`
- `0x180003c20`
- `0x1800069c0`
- `0x180006ac4`
- `0x180009f78`
- `0x18001a8fc`
- `0x18001ce38`
- `0x180071e14`
- `0x180080e34`
- `0x180082418`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008113b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008113b`
- `ncrypt!NCryptFinalizeKey` at `0x1800810f3`
- `ncrypt!NCryptFinalizeKey` at `0x1800810f3`
- `ncrypt!NCryptCreatePersistedKey` at `0x180080f2e`
- `ncrypt!NCryptCreatePersistedKey` at `0x180080f2e`
- `ncrypt!NCryptSetProperty` at `0x180080fa7`
- `ncrypt!NCryptSetProperty` at `0x18008100e`
- `ncrypt!NCryptSetProperty` at `0x18008106d`
- `ncrypt!NCryptSetProperty` at `0x1800810c0`
- `ncrypt!NCryptSetProperty` at `0x180080fa7`
- `ncrypt!NCryptSetProperty` at `0x18008100e`
- `ncrypt!NCryptSetProperty` at `0x18008106d`
- `ncrypt!NCryptSetProperty` at `0x1800810c0`
- `ncrypt!NCryptFreeObject` at `0x1800811c5`
- `ncrypt!NCryptFreeObject` at `0x1800811c5`

## string_xrefs

- `0x180080e7b`: `CertificatePrivateKeyHelper::CreateKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CertificatePrivateKeyHelper::CreateKey(
        NCRYPT_PROV_HANDLE hProvider,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *a4,
        DWORD dwFlags,
        bool a6,
        unsigned __int64 *a7)
{
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  SECURITY_STATUS v13; // eax
  __int64 v14; // r9
  unsigned int v15; // ebx
  DWORD dwLegacyKeySpec[2]; // [rsp+20h] [rbp-D1h]
  int v18; // [rsp+30h] [rbp-C1h]
  SECURITY_STATUS v19; // [rsp+50h] [rbp-A1h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-99h] BYREF
  BYTE v21[8]; // [rsp+60h] [rbp-91h] BYREF
  const WCHAR *v22; // [rsp+68h] [rbp-89h] BYREF
  __int64 v23; // [rsp+70h] [rbp-81h] BYREF
  BYTE pbInput[8]; // [rsp+78h] [rbp-79h] BYREF
  __int64 v25; // [rsp+80h] [rbp-71h]
  __int64 v26; // [rsp+88h] [rbp-69h]
  __int64 v27; // [rsp+90h] [rbp-61h]
  const char *v28[6]; // [rsp+98h] [rbp-59h] BYREF
  int v29; // [rsp+C8h] [rbp-29h] BYREF
  char v30; // [rsp+CCh] [rbp-25h]
  _BYTE v31[16]; // [rsp+D0h] [rbp-21h] BYREF
  GUID ActivityId; // [rsp+E0h] [rbp-11h] BYREF

  v19 = 0;
  phKey = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v28,
    (int)"certificateprivatekey.cpp",
    (int)"CertificatePrivateKeyHelper::CreateKey",
    (int)&v19);
  v29 = 0;
  v30 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v29);
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    *(_QWORD *)v21 = 0x1000000;
    if ( !v30 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      p_ActivityId = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D321B,
      (__int64)v31,
      (__int64)p_ActivityId,
      (__int64)v21);
  }
  *a7 = 0;
  v13 = NCryptCreatePersistedKey(hProvider, &phKey, L"RSA", a3, 0, dwFlags);
  v19 = v13;
  if ( v13 < 0 )
  {
    v18 = 321;
LABEL_9:
    dwLegacyKeySpec[0] = v13;
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      *(_QWORD *)dwLegacyKeySpec,
      "certificateprivatekey.cpp",
      v18,
      "HRESULT",
      &base);
    goto LABEL_24;
  }
  v13 = NCryptSetProperty(phKey, L"Length", (PBYTE)&CertificatePrivateKeyHelper::KeyLength, 4u, 0);
  v19 = v13;
  if ( v13 < 0 )
  {
    v18 = 322;
    goto LABEL_9;
  }
  if ( a3 )
  {
    v25 = 0;
    *(_QWORD *)pbInput = 1;
    v26 = *(_QWORD *)a4;
    v27 = *((_QWORD *)a4 + 1);
    v13 = NCryptSetProperty(phKey, L"UI Policy", pbInput, 0x20u, 0x80000000);
    v19 = v13;
    if ( v13 < 0 )
    {
      v18 = 333;
      goto LABEL_9;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl'::`2'::impl) )
  {
    *(_DWORD *)v21 = 2;
    v13 = NCryptSetProperty(phKey, L"Key Usage", v21, 4u, 0);
    v19 = v13;
    if ( v13 < 0 )
    {
      v18 = 340;
      goto LABEL_9;
    }
  }
  if ( a6 )
  {
    *(_DWORD *)v21 = 0;
    v13 = NCryptSetProperty(phKey, L"Export Policy", v21, 4u, 0);
    v19 = v13;
    if ( v13 < 0 )
    {
      v18 = 347;
      goto LABEL_9;
    }
  }
  v13 = NCryptFinalizeKey(phKey, 0);
  v19 = v13;
  if ( v13 < 0 )
  {
    v18 = 350;
    goto LABEL_9;
  }
  *a7 = phKey;
  phKey = 0;
LABEL_24:
  if ( v30 )
    EventActivityIdControl(4u, &ActivityId);
  v29 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    if ( !a2 )
      a2 = &base;
    v22 = a2;
    *(_DWORD *)v21 = v19;
    v23 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5050,
      (__int64)&word_1800D31BE,
      (__int64)v31,
      v14,
      (__int64)&v23,
      (__int64)v21,
      &v22);
  }
  if ( phKey )
    NCryptFreeObject(phKey);
  v15 = v19;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v29);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v28);
  return v15;
}

```

## disassembly

```asm
0x180080e34  push    rbp
0x180080e36  push    rbx
0x180080e37  push    rsi
0x180080e38  push    rdi
0x180080e39  push    r12
0x180080e3b  push    r14
0x180080e3d  push    r15
0x180080e3f  lea     rbp, [rsp-0Fh]
0x180080e44  sub     rsp, 100h
0x180080e4b  mov     rax, cs:__security_cookie
0x180080e52  xor     rax, rsp
0x180080e55  mov     [rbp+3Fh+var_40], rax
0x180080e59  mov     rsi, r9
0x180080e5c  mov     rbx, r8
0x180080e5f  mov     rdi, rdx
0x180080e62  mov     r15, rcx
0x180080e65  mov     r14, [rbp+3Fh+arg_30]
0x180080e69  xor     r12d, r12d
0x180080e6c  mov     [rsp+130h+var_E0], r12d
0x180080e71  mov     [rsp+130h+phKey], r12
0x180080e76  lea     r9, [rsp+130h+var_E0]
0x180080e7b  lea     r8, aCertificatepri; "CertificatePrivateKeyHelper::CreateKey"
0x180080e82  lea     rdx, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x180080e89  lea     rcx, [rbp+3Fh+var_98]
0x180080e8d  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180080e92  nop
0x180080e93  mov     [rbp+3Fh+var_68], r12d
0x180080e97  mov     [rbp+3Fh+var_64], r12b
0x180080e9b  lea     rcx, [rbp+3Fh+var_68]
0x180080e9f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180080ea4  mov     eax, cs:dword_1800E5050
0x180080eaa  cmp     eax, 5
0x180080ead  jbe     short loc_180080F0D
0x180080eaf  mov     rdx, 400000000000h
0x180080eb9  lea     rcx, dword_1800E5050
0x180080ec0  call    _tlgKeywordOn
0x180080ec5  test    al, al
0x180080ec7  jz      short loc_180080F0D
0x180080ec9  mov     qword ptr [rsp+130h+var_D0], 1000000h
0x180080ed2  cmp     [rbp+3Fh+var_64], r12b
0x180080ed6  jz      short loc_180080EE9
0x180080ed8  lea     rcx, [rbp+3Fh+ActivityId]; struct _GUID *
0x180080edc  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180080ee1  test    al, al
0x180080ee3  lea     r9, [rbp+3Fh+ActivityId]
0x180080ee7  jz      short loc_180080EEC
0x180080ee9  mov     r9, r12
0x180080eec  lea     rax, [rsp+130h+var_D0]
0x180080ef1  mov     qword ptr [rsp+130h+dwLegacyKeySpec], rax
0x180080ef6  lea     r8, [rbp+3Fh+var_60]
0x180080efa  lea     rdx, byte_1800D321B
0x180080f01  lea     rcx, dword_1800E5050
0x180080f08  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180080f0d  mov     [r14], r12
0x180080f10  mov     eax, [rbp+3Fh+arg_20]
0x180080f13  mov     [rsp+130h+dwFlags], eax; dwFlags
0x180080f17  mov     [rsp+130h+dwLegacyKeySpec], r12d; dwLegacyKeySpec
0x180080f1c  mov     r9, rbx; pszKeyName
0x180080f1f  lea     r8, aRsa; "RSA"
0x180080f26  lea     rdx, [rsp+130h+phKey]; phKey
0x180080f2b  mov     rcx, r15; hProvider
0x180080f2e  call    cs:__imp_NCryptCreatePersistedKey
0x180080f34  mov     [rsp+130h+var_E0], eax
0x180080f38  lea     r15, base
0x180080f3f  test    eax, eax
0x180080f41  jns     short loc_180080F89
0x180080f43  mov     [rsp+130h+var_F0], r15
0x180080f48  lea     rcx, aHresult; "HRESULT"
0x180080f4f  mov     [rsp+130h+var_F8], rcx
0x180080f54  mov     dword ptr [rsp+130h+var_100], 141h
0x180080f5c  mov     ebx, 2
0x180080f61  lea     rcx, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x180080f68  mov     qword ptr [rsp+130h+dwFlags], rcx
0x180080f6d  mov     [rsp+130h+dwLegacyKeySpec], eax
0x180080f71  mov     r9d, ebx
0x180080f74  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180080f7b  xor     edx, edx
0x180080f7d  mov     ecx, ebx
0x180080f7f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180080f84  jmp     loc_18008112C
0x180080f89  mov     [rsp+130h+dwLegacyKeySpec], r12d; dwFlags
0x180080f8e  mov     r9d, 4; cbInput
0x180080f94  lea     r8, ?KeyLength@CertificatePrivateKeyHelper@@2KB; pbInput
0x180080f9b  lea     rdx, aLength; "Length"
0x180080fa2  mov     rcx, [rsp+130h+phKey]; hObject
0x180080fa7  call    cs:__imp_NCryptSetProperty
0x180080fad  mov     [rsp+130h+var_E0], eax
0x180080fb1  test    eax, eax
0x180080fb3  jns     short loc_180080FD0
0x180080fb5  mov     [rsp+130h+var_F0], r15
0x180080fba  lea     rcx, aHresult; "HRESULT"
0x180080fc1  mov     [rsp+130h+var_F8], rcx
0x180080fc6  mov     dword ptr [rsp+130h+var_100], 142h
0x180080fce  jmp     short loc_180080F5C
0x180080fd0  test    rbx, rbx
0x180080fd3  jz      short loc_18008103A
0x180080fd5  mov     [rbp+3Fh+var_B0], r12
0x180080fd9  mov     qword ptr [rbp+3Fh+pbInput], 1
0x180080fe1  mov     rax, [rsi]
0x180080fe4  mov     [rbp+3Fh+var_A8], rax
0x180080fe8  mov     rax, [rsi+8]
0x180080fec  mov     [rbp+3Fh+var_A0], rax
0x180080ff0  mov     [rsp+130h+dwLegacyKeySpec], 80000000h; dwFlags
0x180080ff8  mov     r9d, 20h ; ' '; cbInput
0x180080ffe  lea     r8, [rbp+3Fh+pbInput]; pbInput
0x180081002  lea     rdx, aUiPolicy; "UI Policy"
0x180081009  mov     rcx, [rsp+130h+phKey]; hObject
0x18008100e  call    cs:__imp_NCryptSetProperty
0x180081014  mov     [rsp+130h+var_E0], eax
0x180081018  test    eax, eax
0x18008101a  jns     short loc_18008103A
0x18008101c  mov     [rsp+130h+var_F0], r15
0x180081021  lea     rcx, aHresult; "HRESULT"
0x180081028  mov     [rsp+130h+var_F8], rcx
0x18008102d  mov     dword ptr [rsp+130h+var_100], 14Dh
0x180081035  jmp     loc_180080F5C
0x18008103a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp> `wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl(void)'::`2'::impl
0x180081041  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(void)
0x180081046  mov     ebx, 2
0x18008104b  test    al, al
0x18008104d  jz      short loc_180081099
0x18008104f  mov     dword ptr [rsp+130h+var_D0], ebx
0x180081053  mov     [rsp+130h+dwLegacyKeySpec], r12d; dwFlags
0x180081058  lea     r9d, [rbx+2]; cbInput
0x18008105c  lea     r8, [rsp+130h+var_D0]; pbInput
0x180081061  lea     rdx, aKeyUsage; "Key Usage"
0x180081068  mov     rcx, [rsp+130h+phKey]; hObject
0x18008106d  call    cs:__imp_NCryptSetProperty
0x180081073  mov     [rsp+130h+var_E0], eax
0x180081077  test    eax, eax
0x180081079  jns     short loc_180081099
0x18008107b  mov     [rsp+130h+var_F0], r15
0x180081080  lea     rcx, aHresult; "HRESULT"
0x180081087  mov     [rsp+130h+var_F8], rcx
0x18008108c  mov     dword ptr [rsp+130h+var_100], 154h
0x180081094  jmp     loc_180080F61
0x180081099  cmp     [rbp+3Fh+arg_28], r12b
0x18008109d  jz      short loc_1800810EC
0x18008109f  mov     dword ptr [rsp+130h+var_D0], r12d
0x1800810a4  mov     [rsp+130h+dwLegacyKeySpec], r12d; dwFlags
0x1800810a9  mov     r9d, 4; cbInput
0x1800810af  lea     r8, [rsp+130h+var_D0]; pbInput
0x1800810b4  lea     rdx, aExportPolicy; "Export Policy"
0x1800810bb  mov     rcx, [rsp+130h+phKey]; hObject
0x1800810c0  call    cs:__imp_NCryptSetProperty
0x1800810c6  mov     [rsp+130h+var_E0], eax
0x1800810ca  test    eax, eax
0x1800810cc  jns     short loc_1800810EC
0x1800810ce  mov     [rsp+130h+var_F0], r15
0x1800810d3  lea     rcx, aHresult; "HRESULT"
0x1800810da  mov     [rsp+130h+var_F8], rcx
0x1800810df  mov     dword ptr [rsp+130h+var_100], 15Bh
0x1800810e7  jmp     loc_180080F61
0x1800810ec  xor     edx, edx; dwFlags
0x1800810ee  mov     rcx, [rsp+130h+phKey]; hKey
0x1800810f3  call    cs:__imp_NCryptFinalizeKey
0x1800810f9  mov     [rsp+130h+var_E0], eax
0x1800810fd  test    eax, eax
0x1800810ff  jns     short loc_18008111F
0x180081101  mov     [rsp+130h+var_F0], r15
0x180081106  lea     rcx, aHresult; "HRESULT"
0x18008110d  mov     [rsp+130h+var_F8], rcx
0x180081112  mov     dword ptr [rsp+130h+var_100], 15Eh
0x18008111a  jmp     loc_180080F61
0x18008111f  mov     rax, [rsp+130h+phKey]
0x180081124  mov     [r14], rax
0x180081127  mov     [rsp+130h+phKey], r12
0x18008112c  cmp     [rbp+3Fh+var_64], r12b
0x180081130  jz      short loc_180081141
0x180081132  lea     rdx, [rbp+3Fh+ActivityId]; ActivityId
0x180081136  mov     ecx, 4; ControlCode
0x18008113b  call    cs:__imp_EventActivityIdControl
0x180081141  mov     [rbp+3Fh+var_68], ebx
0x180081144  mov     eax, cs:dword_1800E5050
0x18008114a  cmp     eax, 5
0x18008114d  jbe     short loc_1800811BB
0x18008114f  mov     rdx, 400000000000h
0x180081159  lea     rcx, dword_1800E5050
0x180081160  call    _tlgKeywordOn
0x180081165  test    al, al
0x180081167  jz      short loc_1800811BB
0x180081169  test    rdi, rdi
0x18008116c  cmovz   rdi, r15
0x180081170  mov     [rsp+130h+var_C8], rdi
0x180081175  mov     eax, [rsp+130h+var_E0]
0x180081179  mov     dword ptr [rsp+130h+var_D0], eax
0x18008117d  mov     [rsp+130h+var_C0], 1000000h
0x180081186  lea     rax, [rsp+130h+var_C8]
0x18008118b  mov     [rsp+130h+var_100], rax
0x180081190  lea     rax, [rsp+130h+var_D0]
0x180081195  mov     qword ptr [rsp+130h+dwFlags], rax
0x18008119a  lea     rax, [rsp+130h+var_C0]
0x18008119f  mov     qword ptr [rsp+130h+dwLegacyKeySpec], rax
0x1800811a4  lea     r8, [rbp+3Fh+var_60]
0x1800811a8  lea     rdx, word_1800D31BE
0x1800811af  lea     rcx, dword_1800E5050
0x1800811b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800811bb  mov     rcx, [rsp+130h+phKey]; hObject
0x1800811c0  test    rcx, rcx
0x1800811c3  jz      short loc_1800811CB
0x1800811c5  call    cs:__imp_NCryptFreeObject
0x1800811cb  mov     ebx, [rsp+130h+var_E0]
0x1800811cf  lea     rcx, [rbp+3Fh+var_68]
0x1800811d3  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800811d8  nop
0x1800811d9  lea     rcx, [rbp+3Fh+var_98]
0x1800811dd  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800811e2  mov     eax, ebx
0x1800811e4  mov     rcx, [rbp+3Fh+var_40]
0x1800811e8  xor     rcx, rsp; StackCookie
0x1800811eb  call    __security_check_cookie
0x1800811f0  add     rsp, 100h
0x1800811f7  pop     r15
0x1800811f9  pop     r14
0x1800811fb  pop     r12
0x1800811fd  pop     rdi
0x1800811fe  pop     rsi
0x1800811ff  pop     rbx
0x180081200  pop     rbp
0x180081201  retn
```
