# PluginInitialize(AadContextFunctions *,ulong,_GUID *,ulong *,ushort * const,uchar * const,void * *,void * *,_APPLUGIN_SECPKG_FUNCTION_TABLE *)

- ea: `0x180017248`
- end: `0x180017b4f`
- name: `?PluginInitialize@@YAJPEAVAadContextFunctions@@KPEAU_GUID@@PEAKQEAGQEAEPEAPEAX5PEAU_APPLUGIN_SECPKG_FUNCTION_TABLE@@@Z`
- size: `2311`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, unsigned int@<edx>, struct _GUID *@<r8>, unsigned int *@<r9>, unsigned __int16 *const, PSID Sid, void **, void **, struct _APPLUGIN_SECPKG_FUNCTION_TABLE *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006cd0`

## callees

- `0x1800011b4`
- `0x1800018e0`
- `0x180001cfc`
- `0x180003c20`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007b20`
- `0x180007cf4`
- `0x180007df8`
- `0x180009f78`
- `0x180017248`
- `0x18001a8fc`
- `0x18001ce38`
- `0x18001ceb4`
- `0x18001cf08`
- `0x18001d16c`
- `0x18001e150`
- `0x18001edac`
- `0x18001f474`
- `0x18001f498`
- `0x180071e14`
- `0x1800727f8`
- `0x180072fd8`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800177b3`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800177b3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017aa4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001743e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001743e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ed`
- `ntdll!RtlLengthSid` at `0x1800174e3`
- `ntdll!RtlLengthSid` at `0x1800174e3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180017620`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180017620`
- `ntdll!RtlInitializeSid` at `0x180017415`
- `ntdll!RtlInitializeSid` at `0x180017415`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017427`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017427`

## string_xrefs

- `0x1800172e4`: `PluginInitialize`
- `0x180017a61`: `Plugin initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PluginInitialize(
        struct AadContextFunctions *a1,
        int a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned __int16 *const a5,
        PSID Sid,
        void **a7,
        void **a8,
        struct _APPLUGIN_SECPKG_FUNCTION_TABLE *a9)
{
  GUID *p_ActivityId; // r9
  unsigned int *v13; // rax
  signed int StringValue; // ecx
  __int64 v15; // rcx
  ULONG v16; // eax
  rsize_t v17; // rdi
  void *LsaHeap; // rax
  const unsigned __int16 *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rax
  unsigned int *v24; // rdi
  _QWORD *v25; // rsi
  __int64 v26; // r9
  unsigned int v27; // ebx
  bool v29[8]; // [rsp+20h] [rbp-D9h]
  bool v30[8]; // [rsp+20h] [rbp-D9h]
  bool v31; // [rsp+28h] [rbp-D1h]
  int v32; // [rsp+30h] [rbp-C9h]
  int v33; // [rsp+30h] [rbp-C9h]
  int v34; // [rsp+50h] [rbp-A9h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A1h] BYREF
  unsigned int *v36; // [rsp+60h] [rbp-99h]
  __int64 v37; // [rsp+68h] [rbp-91h] BYREF
  bool v38[8]; // [rsp+70h] [rbp-89h] BYREF
  PSID Source; // [rsp+78h] [rbp-81h] BYREF
  const char *v40[6]; // [rsp+80h] [rbp-79h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B0h] [rbp-49h] BYREF
  int v42; // [rsp+B8h] [rbp-41h] BYREF
  char v43; // [rsp+BCh] [rbp-3Dh]
  _BYTE v44[16]; // [rsp+C0h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+D0h] [rbp-29h] BYREF
  struct _GUID v46; // [rsp+E0h] [rbp-19h] BYREF

  v36 = a4;
  v35 = (__int64)a8;
  v34 = 0;
  v37 = 0;
  Source = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3072;
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(Microsoft_Windows_AAD_Context, Aad_CloudAPPlugin_Initialize_Start, a3, 1, &v46);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v40,
    (int)"aadcloudap.cpp",
    (int)"PluginInitialize",
    (int)&v34);
  v42 = 0;
  v43 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v42);
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    *(_QWORD *)v38 = 0x1000000;
    if ( !v43 || _tlgGuidIsZero(&ActivityId) )
      p_ActivityId = 0;
    else
      p_ActivityId = &ActivityId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_1800E5050,
      (__int64)word_1800D2B7A,
      (__int64)v44,
      (__int64)p_ActivityId,
      (__int64)v38);
  }
  if ( a2 != 1 )
  {
    v32 = 152;
LABEL_56:
    v34 = -1073741811;
    *(_DWORD *)v29 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v29, "aadcloudap.cpp", v32, "NTSTATUS", &base);
    goto LABEL_57;
  }
  if ( !a1 || !a7 || !v35 || (v13 = v36) == 0 || !a3 )
  {
    v32 = 162;
    goto LABEL_56;
  }
  *(_QWORD *)v35 = 0;
  *v13 = 0;
  *a7 = 0;
  *(_OWORD *)a5 = 0;
  *(_QWORD *)((char *)a5 + 13) = 0;
  memset_0(Sid, 0, 0x44u);
  RtlInitializeSid(Sid, &IdentifierAuthority, 0);
  if ( !ConvertStringSidToSidW(
          L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
          &Source) )
  {
    StringValue = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v34 = StringValue;
    if ( StringValue < 0 )
    {
      v33 = 178;
LABEL_23:
      *(_DWORD *)v29 = StringValue;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v29, "aadcloudap.cpp", v33, "NTSTATUS", &base);
LABEL_57:
      v24 = v36;
      v25 = (_QWORD *)v35;
      goto LABEL_58;
    }
  }
  if ( !Source )
  {
    StringValue = -1073741595;
    v34 = -1073741595;
    v33 = 182;
    goto LABEL_23;
  }
  v16 = RtlLengthSid(Source);
  v17 = v16;
  LsaHeap = PluginAllocateLsaHeap(v16);
  *a7 = LsaHeap;
  if ( !LsaHeap )
  {
    StringValue = -1073741801;
    v34 = -1073741801;
    v33 = 189;
    goto LABEL_23;
  }
  memcpy_s_0(LsaHeap, v17, Source, v17);
  StringValue = PluginState::ConstructPluginHandle((PluginState *)&v37, a1, a3);
  v34 = StringValue;
  if ( StringValue < 0 )
  {
    v33 = 194;
    goto LABEL_23;
  }
  *(_DWORD *)v38 = 1;
  v46 = *a3;
  RegistryHelper::GetDWORDValue(a1, &v46, L"Enabled", (unsigned int *)v38, v29[0]);
  if ( !*(_DWORD *)v38 )
  {
    *(_DWORD *)v30 = -2147187622;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v30, "aadcloudap.cpp", 205, "HRESULT", &base);
    v34 = -1073445798;
    goto LABEL_57;
  }
  if ( !PluginState::IsCloudDomainJoined((PluginState *)&v37) )
  {
    *(_DWORD *)v38 = 0;
    RtlGetDeviceFamilyInfoEnum(0, v38, 0);
    if ( *(_DWORD *)v38 != 3 )
    {
      *(_DWORD *)v30 = -2147187626;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v30, "aadcloudap.cpp", 217, "HRESULT", &base);
      v34 = -1073445802;
      goto LABEL_57;
    }
  }
  v46 = *a3;
  StringValue = RegistryHelper::GetStringValue(a1, &v46, v19, a5, *(unsigned int *)v30, v31);
  v34 = StringValue;
  if ( StringValue < 0 )
  {
    v33 = 226;
    goto LABEL_23;
  }
  v20 = -1;
  do
    ++v20;
  while ( a5[v20] );
  if ( !v20 )
  {
    StringValue = -1073741595;
    v34 = -1073741595;
    v33 = 231;
    goto LABEL_23;
  }
  StringValue = AadContextFunctions::LsaDuplicateString(a1, (struct _UNICODE_STRING *)(v37 + 24), a5);
  v34 = StringValue;
  if ( StringValue < 0 )
  {
    v33 = 233;
    goto LABEL_23;
  }
  StringValue = PluginState::InitalizeCertUpdateInfo((PluginState *)&v37, a1);
  v34 = StringValue;
  if ( StringValue < 0 )
  {
    v33 = 238;
    goto LABEL_23;
  }
  v21 = _o__beginthreadex(0, 0, DeviceP2PCertificateUpdateThreadProc);
  **(_QWORD **)(v37 + 144) = v21;
  v23 = v37;
  if ( !**(_QWORD **)(v37 + 144) )
  {
    if ( (int)GetLastError() > 0 )
      StringValue = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      StringValue = GetLastError();
    v34 = StringValue;
    if ( StringValue < 0 )
    {
      v33 = 250;
      goto LABEL_23;
    }
    v23 = v37;
  }
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_AAD_Context,
      Aad_CloudAPPlugin_DeviceP2PCertificateThreadStarted,
      v22,
      1,
      &v46);
    v23 = v37;
  }
  v15 = *(unsigned int *)(v23 + 40);
  v24 = v36;
  *v36 = v15;
  v25 = (_QWORD *)v35;
  *(_QWORD *)v35 = v23;
  *(_DWORD *)a9 = g_aadCloudAPPluginFunctionTable;
  *(_OWORD *)((char *)a9 + 8) = xmmword_1800E5528;
  *(_OWORD *)((char *)a9 + 24) = xmmword_1800E5538;
  *(_OWORD *)((char *)a9 + 40) = xmmword_1800E5548;
  *(_OWORD *)((char *)a9 + 56) = xmmword_1800E5558;
  *((_QWORD *)a9 + 9) = qword_1800E5568;
  *((_OWORD *)a9 + 5) = xmmword_1800E5570;
  *((_OWORD *)a9 + 6) = xmmword_1800E5580;
  *((_OWORD *)a9 + 7) = xmmword_1800E5590;
  *((_OWORD *)a9 + 8) = xmmword_1800E55A0;
  *((_OWORD *)a9 + 9) = xmmword_1800E55B0;
  *((_OWORD *)a9 + 10) = xmmword_1800E55C0;
LABEL_58:
  if ( Source && a1 )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v34 < 0 )
  {
    PluginState::ReleasePluginHandle((PluginState *)&v37, a1);
    if ( v25 )
      *v25 = 0;
    if ( v24 )
      *v24 = 0;
    if ( a7 && *a7 )
    {
      if ( a1 )
        (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 32LL))(a1);
      *a7 = 0;
    }
    if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_Error,
        L"Plugin initialize",
        (unsigned int)v34);
  }
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v15, Aad_CloudAPPlugin_Initialize_Stop, (unsigned int)v34);
  if ( v43 )
    EventActivityIdControl(4u, &ActivityId);
  v42 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    *(_DWORD *)v38 = v34;
    v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D2B3D,
      (__int64)v44,
      v26,
      (__int64)&v35,
      (__int64)v38);
  }
  v27 = v34;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v42);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v40);
  return v27;
}

```

## disassembly

```asm
0x180017248  mov     [rsp-8+arg_8], rbx
0x18001724d  push    rbp
0x18001724e  push    rsi
0x18001724f  push    rdi
0x180017250  push    r12
0x180017252  push    r13
0x180017254  push    r14
0x180017256  push    r15
0x180017258  lea     rbp, [rsp-7]
0x18001725d  sub     rsp, 100h
0x180017264  mov     rax, cs:__security_cookie
0x18001726b  xor     rax, rsp
0x18001726e  mov     [rbp+37h+var_40], rax
0x180017272  mov     [rsp+130h+var_D0], r9
0x180017277  mov     rsi, r8
0x18001727a  mov     edi, edx
0x18001727c  mov     rbx, rcx
0x18001727f  mov     r12, [rbp+37h+arg_40]
0x180017286  mov     r14, [rbp+37h+arg_20]
0x18001728a  mov     r13, [rbp+37h+Sid]
0x18001728e  mov     r15, [rbp+37h+arg_30]
0x180017292  mov     rax, [rbp+37h+arg_38]
0x180017296  mov     [rsp+130h+var_D8], rax
0x18001729b  xor     eax, eax
0x18001729d  mov     [rsp+130h+var_E0], eax
0x1800172a1  mov     [rsp+130h+var_C8], rax
0x1800172a6  mov     [rsp+130h+Source], rax
0x1800172ab  mov     dword ptr [rbp+37h+IdentifierAuthority.Value], eax
0x1800172ae  mov     word ptr [rbp+37h+IdentifierAuthority.Value+4], 0C00h
0x1800172b4  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x1800172bb  jz      short loc_1800172DF
0x1800172bd  lea     rax, [rbp+37h+var_50]
0x1800172c1  mov     qword ptr [rsp+130h+var_110], rax
0x1800172c6  mov     r9d, 1
0x1800172cc  lea     rdx, Aad_CloudAPPlugin_Initialize_Start
0x1800172d3  lea     rcx, Microsoft_Windows_AAD_Context
0x1800172da  call    McGenEventWrite_EventWriteTransfer
0x1800172df  lea     r9, [rsp+130h+var_E0]
0x1800172e4  lea     r8, aPlugininitiali; "PluginInitialize"
0x1800172eb  lea     rdx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x1800172f2  lea     rcx, [rbp+37h+var_B0]
0x1800172f6  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800172fb  nop
0x1800172fc  mov     [rbp+37h+var_78], 0
0x180017303  mov     [rbp+37h+var_74], 0
0x180017307  lea     rcx, [rbp+37h+var_78]
0x18001730b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180017310  mov     eax, cs:dword_1800E5050
0x180017316  cmp     eax, 5
0x180017319  jbe     short loc_18001737B
0x18001731b  mov     rdx, 400000000000h
0x180017325  lea     rcx, dword_1800E5050
0x18001732c  call    _tlgKeywordOn
0x180017331  test    al, al
0x180017333  jz      short loc_18001737B
0x180017335  mov     qword ptr [rsp+130h+var_C0], 1000000h
0x18001733e  cmp     [rbp+37h+var_74], 0
0x180017342  jz      short loc_180017357
0x180017344  lea     rcx, [rbp+37h+ActivityId]; struct _GUID *
0x180017348  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18001734d  test    al, al
0x18001734f  jnz     short loc_180017357
0x180017351  lea     r9, [rbp+37h+ActivityId]
0x180017355  jmp     short loc_18001735A
0x180017357  xor     r9d, r9d
0x18001735a  lea     rax, [rsp+130h+var_C0]
0x18001735f  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x180017364  lea     r8, [rbp+37h+var_70]
0x180017368  lea     rdx, word_1800D2B7A
0x18001736f  lea     rcx, dword_1800E5050
0x180017376  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001737b  cmp     edi, 1
0x18001737e  jz      short loc_1800173A5
0x180017380  lea     rax, base
0x180017387  mov     [rsp+130h+var_F0], rax
0x18001738c  lea     rax, aNtstatus; "NTSTATUS"
0x180017393  mov     [rsp+130h+var_F8], rax
0x180017398  mov     [rsp+130h+var_100], 98h
0x1800173a0  jmp     loc_1800179AD
0x1800173a5  test    rbx, rbx
0x1800173a8  jz      loc_18001798D
0x1800173ae  test    r15, r15
0x1800173b1  jz      loc_18001798D
0x1800173b7  mov     rcx, [rsp+130h+var_D8]
0x1800173bc  test    rcx, rcx
0x1800173bf  jz      loc_18001798D
0x1800173c5  mov     rax, [rsp+130h+var_D0]
0x1800173ca  test    rax, rax
0x1800173cd  jz      loc_18001798D
0x1800173d3  test    rsi, rsi
0x1800173d6  jz      loc_18001798D
0x1800173dc  mov     qword ptr [rcx], 0
0x1800173e3  mov     dword ptr [rax], 0
0x1800173e9  mov     qword ptr [r15], 0
0x1800173f0  xorps   xmm0, xmm0
0x1800173f3  xor     eax, eax
0x1800173f5  movups  xmmword ptr [r14], xmm0
0x1800173f9  mov     [r14+0Dh], rax
0x1800173fd  xor     edx, edx; Val
0x1800173ff  lea     r8d, [rax+44h]; Size
0x180017403  mov     rcx, r13; void *
0x180017406  call    memset_0
0x18001740b  xor     r8d, r8d; SubAuthorityCount
0x18001740e  lea     rdx, [rbp+37h+IdentifierAuthority]; IdentifierAuthority
0x180017412  mov     rcx, r13; Sid
0x180017415  call    cs:__imp_RtlInitializeSid
0x18001741b  lea     rdx, [rsp+130h+Source]; Sid
0x180017420  lea     rcx, StringSid; "S-1-15-2-1910091885-1573563583-11049412"...
0x180017427  call    cs:__imp_ConvertStringSidToSidW
0x18001742d  xor     r13d, r13d
0x180017430  test    eax, eax
0x180017432  jnz     short loc_1800174AE
0x180017434  call    cs:__imp_GetLastError
0x18001743a  test    eax, eax
0x18001743c  jg      short loc_180017448
0x18001743e  call    cs:__imp_GetLastError
0x180017444  mov     ecx, eax
0x180017446  jmp     short loc_180017457
0x180017448  call    cs:__imp_GetLastError
0x18001744e  movzx   ecx, ax
0x180017451  or      ecx, 0C0070000h
0x180017457  mov     [rsp+130h+var_E0], ecx
0x18001745b  test    ecx, ecx
0x18001745d  jns     short loc_1800174AE
0x18001745f  lea     rax, base
0x180017466  mov     [rsp+130h+var_F0], rax
0x18001746b  lea     rax, aNtstatus; "NTSTATUS"
0x180017472  mov     [rsp+130h+var_F8], rax
0x180017477  mov     [rsp+130h+var_100], 0B2h
0x18001747f  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180017486  mov     [rsp+130h+var_108], rax
0x18001748b  mov     dword ptr [rsp+130h+var_110], ecx
0x18001748f  mov     r14d, 2
0x180017495  mov     r9d, r14d
0x180017498  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18001749f  xor     edx, edx
0x1800174a1  mov     ecx, r14d
0x1800174a4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800174a9  jmp     loc_1800179E3
0x1800174ae  mov     rcx, [rsp+130h+Source]; Sid
0x1800174b3  test    rcx, rcx
0x1800174b6  jnz     short loc_1800174E3
0x1800174b8  mov     ecx, 0C00000E5h
0x1800174bd  mov     [rsp+130h+var_E0], ecx
0x1800174c1  lea     rax, base
0x1800174c8  mov     [rsp+130h+var_F0], rax
0x1800174cd  lea     rax, aNtstatus; "NTSTATUS"
0x1800174d4  mov     [rsp+130h+var_F8], rax
0x1800174d9  mov     [rsp+130h+var_100], 0B6h
0x1800174e1  jmp     short loc_18001747F
0x1800174e3  call    cs:__imp_RtlLengthSid
0x1800174e9  mov     edi, eax
0x1800174eb  mov     ecx, eax; unsigned int
0x1800174ed  call    ?PluginAllocateLsaHeap@@YAPEAXK@Z; PluginAllocateLsaHeap(ulong)
0x1800174f2  mov     [r15], rax
0x1800174f5  test    rax, rax
0x1800174f8  jnz     short loc_180017528
0x1800174fa  mov     ecx, 0C0000017h
0x1800174ff  mov     [rsp+130h+var_E0], ecx
0x180017503  lea     rax, base
0x18001750a  mov     [rsp+130h+var_F0], rax
0x18001750f  lea     rax, aNtstatus; "NTSTATUS"
0x180017516  mov     [rsp+130h+var_F8], rax
0x18001751b  mov     [rsp+130h+var_100], 0BDh
0x180017523  jmp     loc_18001747F
0x180017528  mov     rdx, rdi; DestinationSize
0x18001752b  mov     r9, rdi; SourceSize
0x18001752e  mov     r8, [rsp+130h+Source]; Source
0x180017533  mov     rcx, rax; Destination
0x180017536  call    memcpy_s_0
0x18001753b  mov     r8, rsi; struct _GUID *
0x18001753e  mov     rdx, rbx; struct AadContextFunctions *
0x180017541  lea     rcx, [rsp+130h+var_C8]; this
0x180017546  call    ?ConstructPluginHandle@PluginState@@QEAAJPEAVAadContextFunctions@@PEAU_GUID@@@Z; PluginState::ConstructPluginHandle(AadContextFunctions *,_GUID *)
0x18001754b  mov     ecx, eax
0x18001754d  mov     [rsp+130h+var_E0], eax
0x180017551  test    eax, eax
0x180017553  jns     short loc_18001757A
0x180017555  lea     rax, base
0x18001755c  mov     [rsp+130h+var_F0], rax
0x180017561  lea     rax, aNtstatus; "NTSTATUS"
0x180017568  mov     [rsp+130h+var_F8], rax
0x18001756d  mov     [rsp+130h+var_100], 0C2h
0x180017575  jmp     loc_18001747F
0x18001757a  mov     edi, 1
0x18001757f  mov     dword ptr [rsp+130h+var_C0], edi
0x180017583  movups  xmm0, xmmword ptr [rsi]
0x180017586  movdqu  xmmword ptr [rbp+37h+var_50.Data1], xmm0
0x18001758b  lea     r9, [rsp+130h+var_C0]; unsigned int *
0x180017590  lea     r8, aEnabled; "Enabled"
0x180017597  lea     rdx, [rbp+37h+var_50]; struct _GUID
0x18001759b  mov     rcx, rbx; struct AadContextFunctions *
0x18001759e  call    ?GetDWORDValue@RegistryHelper@@CAJPEAVAadContextFunctions@@U_GUID@@PEBGPEAK_N@Z; RegistryHelper::GetDWORDValue(AadContextFunctions *,_GUID,ushort const *,ulong *,bool)
0x1800175a3  cmp     dword ptr [rsp+130h+var_C0], r13d
0x1800175a8  jnz     short loc_180017603
0x1800175aa  lea     rax, base
0x1800175b1  mov     [rsp+130h+var_F0], rax
0x1800175b6  lea     rax, aHresult; "HRESULT"
0x1800175bd  mov     [rsp+130h+var_F8], rax
0x1800175c2  mov     [rsp+130h+var_100], 0CDh
0x1800175ca  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x1800175d1  mov     [rsp+130h+var_108], rax
0x1800175d6  mov     dword ptr [rsp+130h+var_110], 8004845Ah
0x1800175de  lea     r14d, [rdi+1]
0x1800175e2  mov     r9d, r14d
0x1800175e5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800175ec  xor     edx, edx
0x1800175ee  mov     ecx, r14d
0x1800175f1  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800175f6  mov     [rsp+130h+var_E0], 0C004845Ah
0x1800175fe  jmp     loc_1800179E3
0x180017603  lea     rcx, [rsp+130h+var_C8]; this
0x180017608  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x18001760d  test    al, al
0x18001760f  jnz     short loc_180017688
0x180017611  mov     dword ptr [rsp+130h+var_C0], r13d
0x180017616  xor     r8d, r8d
0x180017619  lea     rdx, [rsp+130h+var_C0]
0x18001761e  xor     ecx, ecx
0x180017620  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180017626  cmp     dword ptr [rsp+130h+var_C0], 3
0x18001762b  jz      short loc_180017688
0x18001762d  lea     rax, base
0x180017634  mov     [rsp+130h+var_F0], rax
0x180017639  lea     rax, aHresult; "HRESULT"
0x180017640  mov     [rsp+130h+var_F8], rax
0x180017645  mov     [rsp+130h+var_100], 0D9h
0x18001764d  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180017654  mov     [rsp+130h+var_108], rax
0x180017659  mov     dword ptr [rsp+130h+var_110], 80048456h
0x180017661  mov     r14d, 2
0x180017667  mov     r9d, r14d
0x18001766a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180017671  xor     edx, edx
0x180017673  mov     ecx, r14d
0x180017676  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18001767b  mov     [rsp+130h+var_E0], 0C0048456h
0x180017683  jmp     loc_1800179E3
0x180017688  movups  xmm0, xmmword ptr [rsi]
0x18001768b  movdqu  xmmword ptr [rbp+37h+var_50.Data1], xmm0
0x180017690  mov     r9, r14; unsigned __int16 *
0x180017693  lea     rdx, [rbp+37h+var_50]; struct _GUID
0x180017697  mov     rcx, rbx; struct AadContextFunctions *
0x18001769a  call    ?GetStringValue@RegistryHelper@@SAJPEAVAadContextFunctions@@U_GUID@@PEBGPEAGK_N@Z; RegistryHelper::GetStringValue(AadContextFunctions *,_GUID,ushort const *,ushort *,ulong,bool)
0x18001769f  mov     ecx, eax
0x1800176a1  mov     [rsp+130h+var_E0], eax
0x1800176a5  test    eax, eax
0x1800176a7  jns     short loc_1800176CE
0x1800176a9  lea     rax, base
0x1800176b0  mov     [rsp+130h+var_F0], rax
0x1800176b5  lea     rax, aNtstatus; "NTSTATUS"
0x1800176bc  mov     [rsp+130h+var_F8], rax
0x1800176c1  mov     [rsp+130h+var_100], 0E2h
0x1800176c9  jmp     loc_18001747F
0x1800176ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800176d2  inc     rax
0x1800176d5  cmp     [r14+rax*2], r13w
0x1800176da  jnz     short loc_1800176D2
0x1800176dc  test    rax, rax
0x1800176df  jnz     short loc_18001770F
0x1800176e1  mov     ecx, 0C00000E5h
0x1800176e6  mov     [rsp+130h+var_E0], ecx
0x1800176ea  lea     rax, base
0x1800176f1  mov     [rsp+130h+var_F0], rax
0x1800176f6  lea     rax, aNtstatus; "NTSTATUS"
0x1800176fd  mov     [rsp+130h+var_F8], rax
0x180017702  mov     [rsp+130h+var_100], 0E7h
0x18001770a  jmp     loc_18001747F
0x18001770f  mov     rdx, [rsp+130h+var_C8]
0x180017714  add     rdx, 18h; struct _UNICODE_STRING *
0x180017718  mov     r8, r14; unsigned __int16 *
0x18001771b  mov     rcx, rbx; this
0x18001771e  call    ?LsaDuplicateString@AadContextFunctions@@QEAAJPEAU_UNICODE_STRING@@PEBG@Z; AadContextFunctions::LsaDuplicateString(_UNICODE_STRING *,ushort const *)
0x180017723  mov     ecx, eax
0x180017725  mov     [rsp+130h+var_E0], eax
0x180017729  test    eax, eax
0x18001772b  jns     short loc_180017752
0x18001772d  lea     rax, base
0x180017734  mov     [rsp+130h+var_F0], rax
0x180017739  lea     rax, aNtstatus; "NTSTATUS"
0x180017740  mov     [rsp+130h+var_F8], rax
0x180017745  mov     [rsp+130h+var_100], 0E9h
0x18001774d  jmp     loc_18001747F
0x180017752  mov     rdx, rbx; struct AadContextFunctions *
0x180017755  lea     rcx, [rsp+130h+var_C8]; this
0x18001775a  call    ?InitalizeCertUpdateInfo@PluginState@@QEAAJPEAVAadContextFunctions@@@Z; PluginState::InitalizeCertUpdateInfo(AadContextFunctions *)
0x18001775f  mov     ecx, eax
0x180017761  mov     [rsp+130h+var_E0], eax
0x180017765  test    eax, eax
0x180017767  jns     short loc_18001778E
0x180017769  lea     rax, base
0x180017770  mov     [rsp+130h+var_F0], rax
0x180017775  lea     rax, aNtstatus; "NTSTATUS"
0x18001777c  mov     [rsp+130h+var_F8], rax
0x180017781  mov     [rsp+130h+var_100], 0EEh
0x180017789  jmp     loc_18001747F
0x18001778e  mov     r9, [rsp+130h+var_C8]
0x180017793  mov     rax, [r9+90h]
0x18001779a  add     rax, 10h
0x18001779e  mov     [rsp+130h+var_108], rax
  ... truncated ...
```
