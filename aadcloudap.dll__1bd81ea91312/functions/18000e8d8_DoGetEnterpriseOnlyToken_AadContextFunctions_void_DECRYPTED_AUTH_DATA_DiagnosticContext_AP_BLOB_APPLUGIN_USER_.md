# DoGetEnterpriseOnlyToken(AadContextFunctions *,void *,_DECRYPTED_AUTH_DATA *,DiagnosticContext &,_AP_BLOB *,_APPLUGIN_USER_INFO * *)

- ea: `0x18000e8d8`
- end: `0x18000eff4`
- name: `?DoGetEnterpriseOnlyToken@@YAJPEAVAadContextFunctions@@PEAXPEAU_DECRYPTED_AUTH_DATA@@AEAVDiagnosticContext@@PEAU_AP_BLOB@@PEAPEAU_APPLUGIN_USER_INFO@@@Z`
- size: `1820`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, void *@<rdx>, struct _DECRYPTED_AUTH_DATA *@<r8>, struct DiagnosticContext *@<r9>, struct _AP_BLOB *, struct _APPLUGIN_USER_INFO **)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b580`

## callees

- `0x1800011b4`
- `0x1800015c8`
- `0x1800018e0`
- `0x180001af4`
- `0x180001cfc`
- `0x180003c20`
- `0x180004a24`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180006e0c`
- `0x180007dd4`
- `0x180009f78`
- `0x18000e8d8`
- `0x18001a8fc`
- `0x18001ce38`
- `0x18001d0ec`
- `0x18001dcf0`
- `0x18001f474`
- `0x180021cbc`
- `0x180036bf4`
- `0x18003b394`
- `0x18003fd78`
- `0x180070678`
- `0x18007093c`
- `0x180071e14`
- `0x180075584`
- `0x1800787ec`
- `0x180078b98`
- `0x1800790ac`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ef21`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ef21`

## string_xrefs

- `0x18000edab`: `Token is expired`
- `0x18000e971`: `DoGetEnterpriseOnlyToken`
- `0x18000ea1f`: `DoGetEnterpriseToken`
- `0x18000eeaa`: `DoGetEnterpriseToken`
- `0x18000ebab`: `Get EnterpriseOnly Token correlation ID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoGetEnterpriseOnlyToken(
        struct AadContextFunctions *a1,
        _QWORD *a2,
        struct _DECRYPTED_AUTH_DATA *a3,
        struct DiagnosticContext *a4,
        struct _AP_BLOB *a5,
        struct _APPLUGIN_USER_INFO **a6)
{
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  int LogonCredsFromAuthData; // ecx
  const WCHAR *v13; // rax
  __int64 v14; // r9
  int v15; // r8d
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // r9
  struct _APPLUGIN_USER_INFO *v19; // rdi
  struct AadContextFunctions *v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned int v23; // ebx
  struct _AadNetworkConfig *v25; // [rsp+20h] [rbp-E0h]
  struct _DECRYPTED_AUTH_DATA *v26; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  struct _APPLUGIN_USER_INFO *v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v33[9]; // [rsp+90h] [rbp-70h] BYREF
  const char *v34[7]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v35[248]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v36; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 *v37[22]; // [rsp+210h] [rbp+110h] BYREF
  int v38; // [rsp+2C0h] [rbp+1C0h]
  int v39; // [rsp+380h] [rbp+280h] BYREF
  char v40; // [rsp+384h] [rbp+284h]
  _BYTE v41[16]; // [rsp+388h] [rbp+288h] BYREF
  GUID ActivityId; // [rsp+398h] [rbp+298h] BYREF
  struct _GUID v43; // [rsp+3A8h] [rbp+2A8h] BYREF

  v27 = 0;
  memset(v33, 0, 64);
  memset_0(v35, 0, 0x268u);
  v28 = a2;
  v31 = 0;
  v32 = 0;
  v43 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v34,
    (int)"aadcloudap.cpp",
    (int)"DoGetEnterpriseOnlyToken",
    (int)&v27);
  v39 = 0;
  v40 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v39);
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v30 = 0x1000000;
    if ( !v40 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      p_ActivityId = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D284B,
      (__int64)v41,
      (__int64)p_ActivityId,
      (__int64)&v30);
  }
  v33[8] = (const unsigned __int16 *)a4;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
    (char *)a4 + 64,
    L"DoGetEnterpriseToken");
  if ( !a1 || !a6 || !a5 || !a2 )
  {
    LogonCredsFromAuthData = -1073741811;
    LODWORD(v26) = 1575;
    goto LABEL_44;
  }
  if ( !a3 )
  {
    LogonCredsFromAuthData = -2146893039;
    LODWORD(v26) = 1580;
LABEL_44:
    v27 = LogonCredsFromAuthData;
    goto LABEL_45;
  }
  *a6 = 0;
  *(_QWORD *)a5 = 0;
  *((_QWORD *)a5 + 1) = 0;
  if ( PluginState::IsCloudDomainJoined((PluginState *)&v28) )
  {
    LogonCredsFromAuthData = AuthBufferHelper::GetLogonCredsFromAuthData(a1, a3, (struct _AAD_LOGON_CRED *)v33, &v43);
    v27 = LogonCredsFromAuthData;
    if ( LogonCredsFromAuthData >= 0 )
    {
      LogonCredsFromAuthData = PluginState::CheckAuthorityUri((PluginState *)&v28, a1);
      v27 = LogonCredsFromAuthData;
      if ( LogonCredsFromAuthData >= 0 )
      {
        if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_GetToken_CorrelationID,
            *((_QWORD *)a4 + 3));
        v13 = &base;
        if ( *((_QWORD *)a4 + 3) )
          v13 = (const WCHAR *)*((_QWORD *)a4 + 3);
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "aadcloudap.cpp",
          1601,
          "Get EnterpriseOnly Token correlation ID",
          v13);
        if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
        {
          LODWORD(v28) = v33[2];
          v30 = *((_QWORD *)a4 + 3);
          v29 = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800E5050,
            (__int64)&byte_1800D27EF,
            (__int64)v41,
            v14,
            (__int64)&v29,
            (const WCHAR **)&v30,
            (__int64)&v28);
        }
        LogonCredsFromAuthData = EnterpriseSTSHelper::LogonAsPrimary(
                                   a1,
                                   *(const unsigned __int16 **)(a2[1] + 8LL),
                                   *(const unsigned __int16 **)(a2[1] + 24LL),
                                   a4,
                                   (struct _AadNetworkConfig *)*a2,
                                   (struct _AAD_LOGON_CRED *)v33,
                                   a3,
                                   &v31,
                                   (struct _AadApPluginTokenInfo *)v35);
        v27 = LogonCredsFromAuthData;
        if ( LogonCredsFromAuthData >= 0 )
        {
          v16 = *(const unsigned __int16 **)(a2[1] + 40LL);
          if ( v16 && !v36 )
            DuplicateString(a1, v16, v15, &v36);
          v17 = *(const unsigned __int16 **)(a2[1] + 72LL);
          if ( v17 && !v37[0] )
            DuplicateString(a1, v17, v15, v37);
          v38 = 1;
          LogonCredsFromAuthData = TokenInfoSerializeHelper::SerializeTokenInfo(a1, v35, &v32, 3);
          v27 = LogonCredsFromAuthData;
          if ( LogonCredsFromAuthData >= 0 )
          {
            if ( !IsTimeOlderThan((__int64)v37[12], 3, 1) )
              goto LABEL_42;
            v27 = -1073740964;
            if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
            {
              v29 = (__int64)"Token is expired";
              LODWORD(v28) = v27;
              v30 = 2048;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (__int64)&dword_1800E5050,
                (__int64)word_1800D27A2,
                (__int64)v41,
                v18,
                (__int64)&v30,
                (__int64)&v28,
                (const unsigned __int16 **)&v29);
            }
            LogonCredsFromAuthData = v27;
            if ( v27 >= 0 )
            {
LABEL_42:
              *a6 = v31;
              *(_OWORD *)a5 = v32;
              goto LABEL_46;
            }
            LODWORD(v26) = 1646;
          }
          else
          {
            LODWORD(v26) = 1639;
          }
        }
        else
        {
          LODWORD(v26) = 1618;
        }
      }
      else
      {
        LODWORD(v26) = 1598;
      }
    }
    else
    {
      LODWORD(v26) = 1595;
    }
LABEL_45:
    LODWORD(v25) = LogonCredsFromAuthData;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v25, "aadcloudap.cpp", v26, "NTSTATUS", &base);
LABEL_46:
    if ( v27 >= 0 )
      goto LABEL_48;
    goto LABEL_47;
  }
  LODWORD(v25) = -2147187631;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v25, "aadcloudap.cpp", 1588, "HRESULT", &base);
  v27 = -1073445807;
LABEL_47:
  DiagnosticContext::LogDiagnosticEvent(a4, L"DoGetEnterpriseToken", v27, v33[1], (int)v33[2], 1, 0);
LABEL_48:
  AuthBufferHelper::FreeLogonCredsContent(a1, (struct _AAD_LOGON_CRED *)v33);
  ReleaseTokenInfo(a1, (struct _AadApPluginTokenInfo *)v35);
  if ( v27 < 0 )
  {
    v19 = v31;
    if ( v31 )
    {
      v20 = PluginContextHelper::Context();
      v21 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)v20 + 48LL))(v20);
      (*(void (__fastcall **)(struct _APPLUGIN_USER_INFO *))(v21 + 56))(v19);
    }
    PluginLsaFreeApBlob((struct _AP_BLOB *)&v32);
  }
  if ( v40 )
    EventActivityIdControl(4u, &ActivityId);
  v39 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    LODWORD(v28) = v27;
    v29 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D275D,
      (__int64)v41,
      v22,
      (__int64)&v29,
      (__int64)&v28);
  }
  v23 = v27;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveHead(
    (char *)a4 + 64,
    &v29);
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v39);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v34);
  return v23;
}

```

## disassembly

```asm
0x18000e8d8  mov     [rsp-8+arg_8], rbx
0x18000e8dd  push    rbp
0x18000e8de  push    rsi
0x18000e8df  push    rdi
0x18000e8e0  push    r12
0x18000e8e2  push    r13
0x18000e8e4  push    r14
0x18000e8e6  push    r15
0x18000e8e8  lea     rbp, [rsp-2C0h]
0x18000e8f0  sub     rsp, 3C0h
0x18000e8f7  mov     rax, cs:__security_cookie
0x18000e8fe  xor     rax, rsp
0x18000e901  mov     [rbp+2F0h+var_38], rax
0x18000e908  mov     r15, r9
0x18000e90b  mov     r12, r8
0x18000e90e  mov     rbx, rdx
0x18000e911  mov     rsi, rcx
0x18000e914  mov     r14, [rbp+2F0h+arg_20]
0x18000e91b  mov     r13, [rbp+2F0h+arg_28]
0x18000e922  xor     edi, edi
0x18000e924  mov     [rsp+3F0h+var_3A0], edi
0x18000e928  mov     [rbp+2F0h+var_360], di
0x18000e92c  xorps   xmm0, xmm0
0x18000e92f  movups  xmmword ptr [rbp+2F0h+var_35E], xmm0
0x18000e933  movups  [rbp+2F0h+var_34E], xmm0
0x18000e937  movups  xmmword ptr [rbp+2F0h+var_33E], xmm0
0x18000e93b  movups  xmmword ptr [rbp+2F0h+var_33E+0Eh], xmm0
0x18000e93f  xor     edx, edx; Val
0x18000e941  mov     r8d, 268h; Size
0x18000e947  lea     rcx, [rbp+2F0h+var_2E0]; void *
0x18000e94b  call    memset_0
0x18000e950  mov     [rsp+3F0h+var_398], rbx
0x18000e955  mov     [rsp+3F0h+var_380], rdi
0x18000e95a  xorps   xmm0, xmm0
0x18000e95d  movups  [rsp+3F0h+var_378], xmm0
0x18000e962  xorps   xmm1, xmm1
0x18000e965  movups  xmmword ptr [rbp+2F0h+var_48.Data1], xmm1
0x18000e96c  lea     r9, [rsp+3F0h+var_3A0]
0x18000e971  lea     r8, aDogetenterpris_0; "DoGetEnterpriseOnlyToken"
0x18000e978  lea     rdx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000e97f  lea     rcx, [rbp+2F0h+var_318]
0x18000e983  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18000e988  nop
0x18000e989  mov     [rbp+2F0h+var_70], edi
0x18000e98f  mov     [rbp+2F0h+var_6C], dil
0x18000e996  lea     rcx, [rbp+2F0h+var_70]
0x18000e99d  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18000e9a2  mov     eax, cs:dword_1800E5050
0x18000e9a8  cmp     eax, 5
0x18000e9ab  jbe     short loc_18000EA17
0x18000e9ad  mov     rdx, 400000000000h
0x18000e9b7  lea     rcx, dword_1800E5050
0x18000e9be  call    _tlgKeywordOn
0x18000e9c3  test    al, al
0x18000e9c5  jz      short loc_18000EA17
0x18000e9c7  mov     [rsp+3F0h+var_388], 1000000h
0x18000e9d0  cmp     [rbp+2F0h+var_6C], dil
0x18000e9d7  jz      short loc_18000E9F0
0x18000e9d9  lea     rcx, [rbp+2F0h+ActivityId]; struct _GUID *
0x18000e9e0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18000e9e5  test    al, al
0x18000e9e7  lea     r9, [rbp+2F0h+ActivityId]
0x18000e9ee  jz      short loc_18000E9F3
0x18000e9f0  mov     r9, rdi
0x18000e9f3  lea     rax, [rsp+3F0h+var_388]
0x18000e9f8  mov     [rsp+3F0h+var_3D0], rax
0x18000e9fd  lea     r8, [rbp+2F0h+var_68]
0x18000ea04  lea     rdx, byte_1800D284B
0x18000ea0b  lea     rcx, dword_1800E5050
0x18000ea12  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18000ea17  mov     [rbp+2F0h+var_320], r15
0x18000ea1b  lea     rcx, [r15+40h]
0x18000ea1f  lea     rdx, aDogetenterpris; "DoGetEnterpriseToken"
0x18000ea26  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x18000ea2b  nop
0x18000ea2c  test    rsi, rsi
0x18000ea2f  jz      loc_18000EE38
0x18000ea35  test    r13, r13
0x18000ea38  jz      loc_18000EE38
0x18000ea3e  test    r14, r14
0x18000ea41  jz      loc_18000EE38
0x18000ea47  test    rbx, rbx
0x18000ea4a  jz      loc_18000EE38
0x18000ea50  test    r12, r12
0x18000ea53  jnz     short loc_18000EA7F
0x18000ea55  mov     ecx, 80090311h
0x18000ea5a  lea     rdi, base
0x18000ea61  mov     [rsp+3F0h+var_3B0], rdi
0x18000ea66  lea     rax, aNtstatus; "NTSTATUS"
0x18000ea6d  mov     [rsp+3F0h+var_3B8], rax
0x18000ea72  mov     dword ptr [rsp+3F0h+var_3C0], 62Ch
0x18000ea7a  jmp     loc_18000EE5D
0x18000ea7f  mov     [r13+0], rdi
0x18000ea83  mov     [r14], rdi
0x18000ea86  mov     [r14+8], rdi
0x18000ea8a  lea     rcx, [rsp+3F0h+var_398]; this
0x18000ea8f  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x18000ea94  test    al, al
0x18000ea96  jnz     short loc_18000EAF1
0x18000ea98  lea     rdi, base
0x18000ea9f  mov     [rsp+3F0h+var_3B0], rdi
0x18000eaa4  lea     rax, aHresult; "HRESULT"
0x18000eaab  mov     [rsp+3F0h+var_3B8], rax
0x18000eab0  mov     dword ptr [rsp+3F0h+var_3C0], 634h
0x18000eab8  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000eabf  mov     [rsp+3F0h+var_3C8], rax
0x18000eac4  mov     dword ptr [rsp+3F0h+var_3D0], 80048451h
0x18000eacc  mov     ebx, 2
0x18000ead1  mov     r9d, ebx
0x18000ead4  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000eadb  xor     edx, edx
0x18000eadd  mov     ecx, ebx
0x18000eadf  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000eae4  mov     [rsp+3F0h+var_3A0], 0C0048451h
0x18000eaec  jmp     loc_18000EE90
0x18000eaf1  lea     r9, [rbp+2F0h+var_48]; struct _GUID *
0x18000eaf8  lea     r8, [rbp+2F0h+var_360]; struct _AAD_LOGON_CRED *
0x18000eafc  mov     rdx, r12; struct _DECRYPTED_AUTH_DATA *
0x18000eaff  mov     rcx, rsi; this
0x18000eb02  call    ?GetLogonCredsFromAuthData@AuthBufferHelper@@SAJPEAVAadContextFunctions@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_AAD_LOGON_CRED@@PEAU_GUID@@@Z; AuthBufferHelper::GetLogonCredsFromAuthData(AadContextFunctions *,_DECRYPTED_AUTH_DATA *,_AAD_LOGON_CRED *,_GUID *)
0x18000eb07  mov     ecx, eax
0x18000eb09  mov     [rsp+3F0h+var_3A0], eax
0x18000eb0d  test    eax, eax
0x18000eb0f  jns     short loc_18000EB36
0x18000eb11  lea     rdi, base
0x18000eb18  mov     [rsp+3F0h+var_3B0], rdi
0x18000eb1d  lea     rax, aNtstatus; "NTSTATUS"
0x18000eb24  mov     [rsp+3F0h+var_3B8], rax
0x18000eb29  mov     dword ptr [rsp+3F0h+var_3C0], 63Bh
0x18000eb31  jmp     loc_18000EE61
0x18000eb36  mov     rdx, rsi; struct AadContextFunctions *
0x18000eb39  lea     rcx, [rsp+3F0h+var_398]; this
0x18000eb3e  call    ?CheckAuthorityUri@PluginState@@QEAAJPEAVAadContextFunctions@@@Z; PluginState::CheckAuthorityUri(AadContextFunctions *)
0x18000eb43  mov     ecx, eax
0x18000eb45  mov     [rsp+3F0h+var_3A0], eax
0x18000eb49  test    eax, eax
0x18000eb4b  jns     short loc_18000EB72
0x18000eb4d  lea     rdi, base
0x18000eb54  mov     [rsp+3F0h+var_3B0], rdi
0x18000eb59  lea     rax, aNtstatus; "NTSTATUS"
0x18000eb60  mov     [rsp+3F0h+var_3B8], rax
0x18000eb65  mov     dword ptr [rsp+3F0h+var_3C0], 63Eh
0x18000eb6d  jmp     loc_18000EE61
0x18000eb72  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18000eb79  jz      short loc_18000EB92
0x18000eb7b  mov     r8, [r15+18h]
0x18000eb7f  lea     rdx, Aad_CloudAPPlugin_GetToken_CorrelationID
0x18000eb86  lea     rcx, Microsoft_Windows_AAD_Context
0x18000eb8d  call    McTemplateU0z_EventWriteTransfer
0x18000eb92  lea     rdi, base
0x18000eb99  mov     rax, rdi
0x18000eb9c  cmp     qword ptr [r15+18h], 0
0x18000eba1  cmovnz  rax, [r15+18h]
0x18000eba6  mov     [rsp+3F0h+var_3B0], rax
0x18000ebab  lea     rax, aGetEnterpriseo; "Get EnterpriseOnly Token correlation ID"
0x18000ebb2  mov     [rsp+3F0h+var_3B8], rax
0x18000ebb7  mov     dword ptr [rsp+3F0h+var_3C0], 641h
0x18000ebbf  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000ebc6  mov     [rsp+3F0h+var_3C8], rax
0x18000ebcb  mov     [rsp+3F0h+var_3D0], 0
0x18000ebd4  mov     eax, 4
0x18000ebd9  mov     r9d, eax
0x18000ebdc  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000ebe3  xor     edx, edx
0x18000ebe5  mov     ecx, eax
0x18000ebe7  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000ebec  mov     eax, cs:dword_1800E5050
0x18000ebf2  cmp     eax, 4
0x18000ebf5  jbe     short loc_18000EC62
0x18000ebf7  mov     rdx, 400000000000h
0x18000ec01  lea     rcx, dword_1800E5050
0x18000ec08  call    _tlgKeywordOn
0x18000ec0d  test    al, al
0x18000ec0f  jz      short loc_18000EC62
0x18000ec11  mov     eax, dword ptr [rbp+2F0h+var_35E+0Eh]
0x18000ec14  mov     dword ptr [rsp+3F0h+var_398], eax
0x18000ec18  mov     rax, [r15+18h]
0x18000ec1c  mov     [rsp+3F0h+var_388], rax
0x18000ec21  mov     [rsp+3F0h+var_390], 800h
0x18000ec2a  lea     rax, [rsp+3F0h+var_398]
0x18000ec2f  mov     [rsp+3F0h+var_3C0], rax
0x18000ec34  lea     rax, [rsp+3F0h+var_388]
0x18000ec39  mov     [rsp+3F0h+var_3C8], rax
0x18000ec3e  lea     rax, [rsp+3F0h+var_390]
0x18000ec43  mov     [rsp+3F0h+var_3D0], rax
0x18000ec48  lea     r8, [rbp+2F0h+var_68]
0x18000ec4f  lea     rdx, byte_1800D27EF
0x18000ec56  lea     rcx, dword_1800E5050
0x18000ec5d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000ec62  mov     rdx, [rbx+8]
0x18000ec66  lea     rax, [rbp+2F0h+var_2E0]
0x18000ec6a  mov     [rsp+3F0h+var_3B0], rax; struct _AadApPluginTokenInfo *
0x18000ec6f  lea     rax, [rsp+3F0h+var_380]
0x18000ec74  mov     [rsp+3F0h+var_3B8], rax; struct _APPLUGIN_USER_INFO **
0x18000ec79  mov     [rsp+3F0h+var_3C0], r12; struct _DECRYPTED_AUTH_DATA *
0x18000ec7e  lea     rax, [rbp+2F0h+var_360]
0x18000ec82  mov     [rsp+3F0h+var_3C8], rax; struct _AAD_LOGON_CRED *
0x18000ec87  mov     rax, [rbx]
0x18000ec8a  mov     [rsp+3F0h+var_3D0], rax; struct _AadNetworkConfig *
0x18000ec8f  mov     r9, r15; struct DiagnosticContext *
0x18000ec92  mov     r8, [rdx+18h]; unsigned __int16 *
0x18000ec96  mov     rdx, [rdx+8]; unsigned __int16 *
0x18000ec9a  mov     rcx, rsi; struct AadContextFunctions *
0x18000ec9d  call    ?LogonAsPrimary@EnterpriseSTSHelper@@SAJPEAVAadContextFunctions@@PEBG1AEAVDiagnosticContext@@PEAU_AadNetworkConfig@@PEAU_AAD_LOGON_CRED@@PEAU_DECRYPTED_AUTH_DATA@@PEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@@Z; EnterpriseSTSHelper::LogonAsPrimary(AadContextFunctions *,ushort const *,ushort const *,DiagnosticContext &,_AadNetworkConfig *,_AAD_LOGON_CRED *,_DECRYPTED_AUTH_DATA *,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *)
0x18000eca2  mov     ecx, eax
0x18000eca4  mov     [rsp+3F0h+var_3A0], eax
0x18000eca8  test    eax, eax
0x18000ecaa  jns     short loc_18000ECCA
0x18000ecac  mov     [rsp+3F0h+var_3B0], rdi
0x18000ecb1  lea     rax, aNtstatus; "NTSTATUS"
0x18000ecb8  mov     [rsp+3F0h+var_3B8], rax
0x18000ecbd  mov     dword ptr [rsp+3F0h+var_3C0], 652h
0x18000ecc5  jmp     loc_18000EE61
0x18000ecca  mov     rax, [rbx+8]
0x18000ecce  mov     rdx, [rax+28h]; unsigned __int16 *
0x18000ecd2  test    rdx, rdx
0x18000ecd5  jz      short loc_18000ECF0
0x18000ecd7  cmp     [rbp+2F0h+var_1E8], 0
0x18000ecdf  jnz     short loc_18000ECF0
0x18000ece1  lea     r9, [rbp+2F0h+var_1E8]; unsigned __int16 **
0x18000ece8  mov     rcx, rsi; struct AadContextFunctions *
0x18000eceb  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18000ecf0  mov     rax, [rbx+8]
0x18000ecf4  mov     rdx, [rax+48h]; unsigned __int16 *
0x18000ecf8  test    rdx, rdx
0x18000ecfb  jz      short loc_18000ED16
0x18000ecfd  cmp     [rbp+2F0h+var_1E0], 0
0x18000ed05  jnz     short loc_18000ED16
0x18000ed07  lea     r9, [rbp+2F0h+var_1E0]; unsigned __int16 **
0x18000ed0e  mov     rcx, rsi; struct AadContextFunctions *
0x18000ed11  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18000ed16  mov     [rbp+2F0h+var_130], 1
0x18000ed20  mov     ebx, 3
0x18000ed25  mov     r9d, ebx
0x18000ed28  lea     r8, [rsp+3F0h+var_378]
0x18000ed2d  lea     rdx, [rbp+2F0h+var_2E0]
0x18000ed31  mov     rcx, rsi
0x18000ed34  call    ?SerializeTokenInfo@TokenInfoSerializeHelper@@SAJPEAVAadContextFunctions@@PEAU_AadApPluginTokenInfo@@PEAU_AP_BLOB@@W4TokenSerializationFlags@1@@Z; TokenInfoSerializeHelper::SerializeTokenInfo(AadContextFunctions *,_AadApPluginTokenInfo *,_AP_BLOB *,TokenInfoSerializeHelper::TokenSerializationFlags)
0x18000ed39  mov     ecx, eax
0x18000ed3b  mov     [rsp+3F0h+var_3A0], eax
0x18000ed3f  test    eax, eax
0x18000ed41  jns     short loc_18000ED61
0x18000ed43  mov     [rsp+3F0h+var_3B0], rdi
0x18000ed48  lea     rax, aNtstatus; "NTSTATUS"
0x18000ed4f  mov     [rsp+3F0h+var_3B8], rax
0x18000ed54  mov     dword ptr [rsp+3F0h+var_3C0], 667h
0x18000ed5c  jmp     loc_18000EE61
0x18000ed61  mov     r8b, 1; bool
0x18000ed64  mov     edx, ebx; int
0x18000ed66  mov     rcx, [rbp+2F0h+var_180]; __int64
0x18000ed6d  call    ?IsTimeOlderThan@@YA_N_JH_N@Z; IsTimeOlderThan(__int64,int,bool)
0x18000ed72  mov     ebx, 2
0x18000ed77  test    al, al
0x18000ed79  jz      loc_18000EE23
0x18000ed7f  mov     [rsp+3F0h+var_3A0], 0C000035Ch
0x18000ed87  mov     eax, cs:dword_1800E5050
0x18000ed8d  cmp     eax, ebx
0x18000ed8f  jbe     short loc_18000EE00
0x18000ed91  mov     rdx, 400000000000h
0x18000ed9b  lea     rcx, dword_1800E5050
0x18000eda2  call    _tlgKeywordOn
0x18000eda7  test    al, al
0x18000eda9  jz      short loc_18000EE00
0x18000edab  lea     rax, aTokenIsExpired; "Token is expired"
0x18000edb2  mov     [rsp+3F0h+var_390], rax
0x18000edb7  mov     eax, [rsp+3F0h+var_3A0]
0x18000edbb  mov     dword ptr [rsp+3F0h+var_398], eax
0x18000edbf  mov     [rsp+3F0h+var_388], 800h
0x18000edc8  lea     rax, [rsp+3F0h+var_390]
0x18000edcd  mov     [rsp+3F0h+var_3C0], rax
0x18000edd2  lea     rax, [rsp+3F0h+var_398]
0x18000edd7  mov     [rsp+3F0h+var_3C8], rax
0x18000eddc  lea     rax, [rsp+3F0h+var_388]
0x18000ede1  mov     [rsp+3F0h+var_3D0], rax
0x18000ede6  lea     r8, [rbp+2F0h+var_68]
0x18000eded  lea     rdx, word_1800D27A2
0x18000edf4  lea     rcx, dword_1800E5050
0x18000edfb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ee00  mov     ecx, [rsp+3F0h+var_3A0]
0x18000ee04  test    ecx, ecx
0x18000ee06  jns     short loc_18000EE23
0x18000ee08  mov     [rsp+3F0h+var_3B0], rdi
0x18000ee0d  lea     rax, aNtstatus; "NTSTATUS"
0x18000ee14  mov     [rsp+3F0h+var_3B8], rax
0x18000ee19  mov     dword ptr [rsp+3F0h+var_3C0], 66Eh
0x18000ee21  jmp     short loc_18000EE66
0x18000ee23  mov     rax, [rsp+3F0h+var_380]
0x18000ee28  mov     [r13+0], rax
0x18000ee2c  movups  xmm0, [rsp+3F0h+var_378]
0x18000ee31  movdqu  xmmword ptr [r14], xmm0
0x18000ee36  jmp     short loc_18000EE89
0x18000ee38  mov     ecx, 0C000000Dh
0x18000ee3d  lea     rdi, base
0x18000ee44  mov     [rsp+3F0h+var_3B0], rdi
0x18000ee49  lea     rax, aNtstatus; "NTSTATUS"
0x18000ee50  mov     [rsp+3F0h+var_3B8], rax
0x18000ee55  mov     dword ptr [rsp+3F0h+var_3C0], 627h
0x18000ee5d  mov     [rsp+3F0h+var_3A0], ecx
0x18000ee61  mov     ebx, 2
0x18000ee66  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
  ... truncated ...
```
