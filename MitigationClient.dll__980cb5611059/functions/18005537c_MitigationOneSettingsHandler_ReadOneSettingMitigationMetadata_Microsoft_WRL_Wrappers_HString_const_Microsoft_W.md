# MitigationOneSettingsHandler::ReadOneSettingMitigationMetadata(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload> const &,Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata> &)

- ea: `0x18005537c`
- end: `0x1800557bf`
- name: `?ReadOneSettingMitigationMetadata@MitigationOneSettingsHandler@@CAJAEBVHString@Wrappers@WRL@Microsoft@@0AEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@45@AEBV?$ComPtr@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@45@AEAV?$ComPtr@VMitigationOneSettingsMetadata@@@45@@Z`
- size: `1091`
- prototype: `__int64 __fastcall(HSTRING *, HSTRING, _QWORD *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800557c8`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x18001c68c`
- `0x180035ecc`
- `0x180035ee8`
- `0x180042ac8`
- `0x180042edc`
- `0x1800442d0`
- `0x180054760`
- `0x18005537c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800553cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800554b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005574e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055772`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800553cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800554b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005574e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055772`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005541d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005548e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005552e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800555a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055698`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005541d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055434`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005548e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005552e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800555a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055698`

## pseudocode

```c
__int64 __fastcall MitigationOneSettingsHandler::ReadOneSettingMitigationMetadata(
        HSTRING *a1,
        HSTRING a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v10; // rax
  int v11; // ebx
  HSTRING v12; // rcx
  PCWSTR v13; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  MitigationContext *MitigationContext; // rbx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v19; // rax
  PCWSTR v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, double *); // rbx
  __int64 v26; // rax
  PCWSTR v27; // rax
  __int64 v28; // rdi
  int (__fastcall *v29)(__int64, _QWORD, double *); // rbx
  __int64 v30; // rax
  int v31; // esi
  const unsigned __int16 *v32; // rax
  struct MitigationContext *v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdi
  int (__fastcall *v38)(__int64, _QWORD, double *); // rbx
  __int64 v39; // rax
  int v40; // ecx
  const unsigned __int16 *v41; // rax
  struct MitigationContext *v42; // rax
  TSExperimentationState *v43; // rbx
  __int64 v44; // rcx
  int v45; // eax
  int v46; // edi
  HSTRING v48; // [rsp+28h] [rbp-61h] BYREF
  HSTRING v49; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  HSTRING v51; // [rsp+40h] [rbp-49h] BYREF
  double v52; // [rsp+48h] [rbp-41h] BYREF
  double v53; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v54; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v55[32]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+57h]

  v54 = a2;
  string = 0;
  v8 = *a3;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          v55,
          &MitigationOneSettingsHandler::s_oneSettingsMitigationVersionRef);
  v11 = v9(v8, *(_QWORD *)(v10 + 24), &string);
  v12 = *a1;
  if ( v11 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
    MitigationContext = MitigationExecutionContext::GetMitigationContext(StringRawBuffer);
    v16 = WindowsGetStringRawBuffer(string, 0);
    MitigationContext::SetMitigationVersion(MitigationContext, v16);
    v49 = 0;
    v17 = *a3;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a3 + 80LL);
    WindowsDeleteString(0);
    v49 = 0;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            v55,
            &MitigationOneSettingsHandler::s_oneSettingsMitigationLearnMoreRef);
    v11 = v18(v17, *(_QWORD *)(v19 + 24), &v49);
    if ( v11 < 0 )
    {
      v20 = WindowsGetStringRawBuffer(*a1, 0);
      MitigationExecutionContext::DispatchEvent(v20, 1, (unsigned int)v11);
LABEL_30:
      WindowsDeleteString(v49);
      v49 = 0;
      goto LABEL_31;
    }
    v51 = 0;
    v21 = *a3;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a3 + 80LL);
    WindowsDeleteString(0);
    v51 = 0;
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            v55,
            &MitigationOneSettingsHandler::s_oneSettingsMitigationTitleRef);
    v11 = v22(v21, *(_QWORD *)(v23 + 24), &v51);
    if ( v11 < 0
      || (v53 = 0.0,
          v24 = *a3,
          v25 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a3 + 88LL),
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  v55,
                  &MitigationOneSettingsHandler::s_oneSettingsMitigationExperimentFeatureId),
          v11 = v25(v24, *(_QWORD *)(v26 + 24), &v53),
          v11 < 0) )
    {
      v27 = WindowsGetStringRawBuffer(*a1, 0);
      MitigationExecutionContext::DispatchEvent(v27, 1, (unsigned int)v11);
LABEL_29:
      WindowsDeleteString(v51);
      v51 = 0;
      goto LABEL_30;
    }
    v52 = 0.0;
    v28 = *a3;
    v29 = *(int (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a3 + 88LL);
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            v55,
            &MitigationOneSettingsHandler::s_oneSettingsMitigationTypeRef);
    v31 = 1;
    if ( v29(v28, *(_QWORD *)(v30 + 24), &v52) >= 0 )
    {
      *(_DWORD *)(*(_QWORD *)a5 + 60LL) = ((__int64 (*)(void))MitigationOneSettingsMetadata::MapToMitigationType)();
      v32 = WindowsGetStringRawBuffer(*a1, 0);
      v33 = MitigationExecutionContext::GetMitigationContext(v32);
      v35 = MitigationOneSettingsMetadata::MapToMitigationType(v34, v33);
      if ( !*(_BYTE *)(v36 + 34) )
        *(_DWORD *)(v36 + 116) = v35;
    }
    v52 = 0.0;
    v37 = *a3;
    v38 = *(int (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)*a3 + 88LL);
    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            v55,
            &MitigationOneSettingsHandler::s_oneSettingsReApplyFlagRef);
    if ( v38(v37, *(_QWORD *)(v39 + 24), &v52) >= 0 )
    {
      v40 = (int)v52;
      if ( (unsigned int)(int)v52 > 3 )
        v40 = 0;
      *(_DWORD *)(*(_QWORD *)a5 + 56LL) = v40;
    }
    v48 = *a1;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)a5 + 16LL), &v48);
    v48 = string;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)a5 + 24LL), &v48);
    v48 = v49;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)a5 + 32LL), &v48);
    v48 = v51;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)a5 + 40LL), &v48);
    v54 = *(HSTRING *)v54;
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(*(_QWORD *)a5 + 48LL), &v54);
    v41 = WindowsGetStringRawBuffer(*a1, 0);
    v42 = MitigationExecutionContext::GetMitigationContext(v41);
    v43 = (struct MitigationContext *)((char *)v42 + 424);
    if ( v53 > 0.0 )
    {
      *((_BYTE *)v42 + 425) = 1;
      *((_DWORD *)v42 + 108) = (int)v53;
      TSExperimentationState::FetchAndSaveExperimentState(v43);
      if ( *((_DWORD *)v43 + 2) && !*((_DWORD *)v43 + 1) )
      {
        v11 = -2135164398;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x174,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationones"
                        "ettingshandler.cpp",
          (const char *)0x80BBFA12LL,
          (int)v48);
        goto LABEL_29;
      }
LABEL_28:
      v11 = 0;
      goto LABEL_29;
    }
    *((_BYTE *)v42 + 425) = 0;
    v44 = *a4;
    if ( !*a4 )
      goto LABEL_28;
    LODWORD(v48) = 0;
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v44 + 160LL))(v44, *a3, &v48);
    v46 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationoneset"
                      "tingshandler.cpp",
        (const char *)(unsigned int)v45,
        (int)v48);
      v11 = v46;
      goto LABEL_29;
    }
    if ( (_DWORD)v48 )
    {
      if ( (_DWORD)v48 == 1 )
      {
        *(_BYTE *)v43 = 1;
        goto LABEL_27;
      }
      if ( (_DWORD)v48 == 2 )
      {
        v31 = 2;
LABEL_27:
        *((_DWORD *)v43 + 1) = v31;
        goto LABEL_28;
      }
    }
    v31 = 0;
    goto LABEL_27;
  }
  v13 = WindowsGetStringRawBuffer(v12, 0);
  MitigationExecutionContext::DispatchEvent(v13, 1, (unsigned int)v11);
LABEL_31:
  WindowsDeleteString(string);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005537c  mov     rax, rsp
0x18005537f  push    rbp
0x180055380  push    rbx
0x180055381  push    rsi
0x180055382  push    rdi
0x180055383  push    r12
0x180055385  push    r13
0x180055387  push    r14
0x180055389  push    r15
0x18005538b  lea     rbp, [rax-57h]
0x18005538f  sub     rsp, 98h
0x180055396  movaps  xmmword ptr [rax-58h], xmm6
0x18005539a  mov     rax, cs:__security_cookie
0x1800553a1  xor     rax, rsp
0x1800553a4  mov     qword ptr [rbp+4Fh+var_58], rax
0x1800553a8  mov     r13, r9
0x1800553ab  mov     r14, r8
0x1800553ae  mov     [rbp+4Fh+var_80], rdx
0x1800553b2  mov     r15, rcx
0x1800553b5  mov     r12, [rbp+4Fh+arg_20]
0x1800553b9  xor     esi, esi
0x1800553bb  mov     [rbp+4Fh+string], rsi
0x1800553bf  mov     rdi, [r8]
0x1800553c2  mov     rax, [rdi]
0x1800553c5  mov     rbx, [rax+50h]
0x1800553c9  xor     ecx, ecx; string
0x1800553cb  call    cs:__imp_WindowsDeleteString
0x1800553d1  mov     [rbp+4Fh+string], rsi
0x1800553d5  lea     rdx, ?s_oneSettingsMitigationVersionRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsMitigationVersionRef
0x1800553dc  lea     rcx, [rbp+4Fh+var_78]
0x1800553e0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800553e5  nop
0x1800553e6  lea     r8, [rbp+4Fh+string]
0x1800553ea  mov     rdx, [rax+18h]
0x1800553ee  mov     rcx, rdi
0x1800553f1  mov     rax, rbx
0x1800553f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553f9  mov     ebx, eax
0x1800553fb  mov     rcx, [r15]; string
0x1800553fe  xor     edx, edx; length
0x180055400  test    eax, eax
0x180055402  jns     short loc_18005541D
0x180055404  call    cs:__imp_WindowsGetStringRawBuffer
0x18005540a  mov     r8d, ebx
0x18005540d  lea     edx, [rsi+1]
0x180055410  mov     rcx, rax
0x180055413  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x180055418  jmp     loc_18005576E
0x18005541d  call    cs:__imp_WindowsGetStringRawBuffer
0x180055423  mov     rcx, rax; unsigned __int16 *
0x180055426  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x18005542b  mov     rbx, rax
0x18005542e  xor     edx, edx; length
0x180055430  mov     rcx, [rbp+4Fh+string]; string
0x180055434  call    cs:__imp_WindowsGetStringRawBuffer
0x18005543a  mov     rdx, rax; unsigned __int16 *
0x18005543d  mov     rcx, rbx; this
0x180055440  call    ?SetMitigationVersion@MitigationContext@@QEAAXPEBG@Z; MitigationContext::SetMitigationVersion(ushort const *)
0x180055445  mov     [rbp+4Fh+var_A8], rsi
0x180055449  mov     rdi, [r14]
0x18005544c  mov     rax, [rdi]
0x18005544f  mov     rbx, [rax+50h]
0x180055453  xor     ecx, ecx; string
0x180055455  call    cs:__imp_WindowsDeleteString
0x18005545b  mov     [rbp+4Fh+var_A8], rsi
0x18005545f  lea     rdx, ?s_oneSettingsMitigationLearnMoreRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsMitigationLearnMoreRef
0x180055466  lea     rcx, [rbp+4Fh+var_78]
0x18005546a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005546f  nop
0x180055470  lea     r8, [rbp+4Fh+var_A8]
0x180055474  mov     rdx, [rax+18h]
0x180055478  mov     rcx, rdi
0x18005547b  mov     rax, rbx
0x18005547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055483  mov     ebx, eax
0x180055485  test    eax, eax
0x180055487  jns     short loc_1800554A9
0x180055489  xor     edx, edx; length
0x18005548b  mov     rcx, [r15]; string
0x18005548e  call    cs:__imp_WindowsGetStringRawBuffer
0x180055494  mov     r8d, ebx
0x180055497  mov     edx, 1
0x18005549c  mov     rcx, rax
0x18005549f  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x1800554a4  jmp     loc_18005575C
0x1800554a9  mov     [rbp+4Fh+var_98], rsi
0x1800554ad  mov     rdi, [r14]
0x1800554b0  mov     rax, [rdi]
0x1800554b3  mov     rbx, [rax+50h]
0x1800554b7  xor     ecx, ecx; string
0x1800554b9  call    cs:__imp_WindowsDeleteString
0x1800554bf  mov     [rbp+4Fh+var_98], rsi
0x1800554c3  lea     rdx, ?s_oneSettingsMitigationTitleRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsMitigationTitleRef
0x1800554ca  lea     rcx, [rbp+4Fh+var_78]
0x1800554ce  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800554d3  nop
0x1800554d4  lea     r8, [rbp+4Fh+var_98]
0x1800554d8  mov     rdx, [rax+18h]
0x1800554dc  mov     rcx, rdi
0x1800554df  mov     rax, rbx
0x1800554e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554e7  mov     ebx, eax
0x1800554e9  test    eax, eax
0x1800554eb  js      short loc_180055529
0x1800554ed  xorps   xmm6, xmm6
0x1800554f0  movsd   [rbp+4Fh+var_88], xmm6
0x1800554f5  mov     rdi, [r14]
0x1800554f8  mov     rax, [rdi]
0x1800554fb  mov     rbx, [rax+58h]
0x1800554ff  lea     rdx, ?s_oneSettingsMitigationExperimentFeatureId@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsMitigationExperimentFeatureId
0x180055506  lea     rcx, [rbp+4Fh+var_78]
0x18005550a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005550f  nop
0x180055510  lea     r8, [rbp+4Fh+var_88]
0x180055514  mov     rdx, [rax+18h]
0x180055518  mov     rcx, rdi
0x18005551b  mov     rax, rbx
0x18005551e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055523  mov     ebx, eax
0x180055525  test    eax, eax
0x180055527  jns     short loc_180055549
0x180055529  xor     edx, edx; length
0x18005552b  mov     rcx, [r15]; string
0x18005552e  call    cs:__imp_WindowsGetStringRawBuffer
0x180055534  mov     r8d, ebx
0x180055537  mov     edx, 1
0x18005553c  mov     rcx, rax
0x18005553f  call    ?DispatchEvent@MitigationExecutionContext@@SAXPEBGW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(ushort const *,MitigationError,long)
0x180055544  jmp     loc_18005574A
0x180055549  movsd   [rbp+4Fh+var_90], xmm6
0x18005554e  mov     rdi, [r14]
0x180055551  mov     rax, [rdi]
0x180055554  mov     rbx, [rax+58h]
0x180055558  lea     rdx, ?s_oneSettingsMitigationTypeRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsMitigationTypeRef
0x18005555f  lea     rcx, [rbp+4Fh+var_78]
0x180055563  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180055568  nop
0x180055569  lea     r8, [rbp+4Fh+var_90]
0x18005556d  mov     rdx, [rax+18h]
0x180055571  mov     rcx, rdi
0x180055574  mov     rax, rbx
0x180055577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005557c  nop
0x18005557d  shr     eax, 1Fh
0x180055580  mov     esi, 1
0x180055585  xor     al, sil
0x180055588  jz      short loc_1800555C4
0x18005558a  movsd   xmm0, [rbp+4Fh+var_90]
0x18005558f  call    ?MapToMitigationType@MitigationOneSettingsMetadata@@SA?AW4MitigationType@@N@Z; MitigationOneSettingsMetadata::MapToMitigationType(double)
0x180055594  mov     rcx, [r12]
0x180055598  mov     [rcx+3Ch], eax
0x18005559b  xor     edx, edx; length
0x18005559d  mov     rcx, [r15]; string
0x1800555a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800555a6  mov     rcx, rax; unsigned __int16 *
0x1800555a9  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x1800555ae  mov     rdx, rax
0x1800555b1  movsd   xmm0, [rbp+4Fh+var_90]
0x1800555b6  call    ?MapToMitigationType@MitigationOneSettingsMetadata@@SA?AW4MitigationType@@N@Z; MitigationOneSettingsMetadata::MapToMitigationType(double)
0x1800555bb  cmp     byte ptr [rdx+22h], 0
0x1800555bf  jnz     short loc_1800555C4
0x1800555c1  mov     [rdx+74h], eax
0x1800555c4  movsd   [rbp+4Fh+var_90], xmm6
0x1800555c9  mov     rdi, [r14]
0x1800555cc  mov     rax, [rdi]
0x1800555cf  mov     rbx, [rax+58h]
0x1800555d3  lea     rdx, ?s_oneSettingsReApplyFlagRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsReApplyFlagRef
0x1800555da  lea     rcx, [rbp+4Fh+var_78]
0x1800555de  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800555e3  nop
0x1800555e4  lea     r8, [rbp+4Fh+var_90]
0x1800555e8  mov     rdx, [rax+18h]
0x1800555ec  mov     rcx, rdi
0x1800555ef  mov     rax, rbx
0x1800555f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555f7  nop
0x1800555f8  shr     eax, 1Fh
0x1800555fb  xor     al, sil
0x1800555fe  jz      short loc_180055614
0x180055600  cvttsd2si ecx, [rbp+4Fh+var_90]
0x180055605  xor     eax, eax
0x180055607  cmp     ecx, 3
0x18005560a  cmova   ecx, eax
0x18005560d  mov     rax, [r12]
0x180055611  mov     [rax+38h], ecx
0x180055614  mov     rax, [r15]
0x180055617  mov     [rbp+4Fh+var_B0], rax
0x18005561b  mov     rcx, [r12]
0x18005561f  add     rcx, 10h; newString
0x180055623  lea     rdx, [rbp+4Fh+var_B0]; HSTRING *
0x180055627  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18005562c  mov     rax, [rbp+4Fh+string]
0x180055630  mov     [rbp+4Fh+var_B0], rax
0x180055634  mov     rcx, [r12]
0x180055638  add     rcx, 18h; newString
0x18005563c  lea     rdx, [rbp+4Fh+var_B0]; HSTRING *
0x180055640  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180055645  mov     rax, [rbp+4Fh+var_A8]
0x180055649  mov     [rbp+4Fh+var_B0], rax
0x18005564d  mov     rcx, [r12]
0x180055651  add     rcx, 20h ; ' '; newString
0x180055655  lea     rdx, [rbp+4Fh+var_B0]; HSTRING *
0x180055659  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18005565e  mov     rax, [rbp+4Fh+var_98]
0x180055662  mov     [rbp+4Fh+var_B0], rax
0x180055666  mov     rcx, [r12]
0x18005566a  add     rcx, 28h ; '('; newString
0x18005566e  lea     rdx, [rbp+4Fh+var_B0]; HSTRING *
0x180055672  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180055677  mov     rcx, [rbp+4Fh+var_80]
0x18005567b  mov     rax, [rcx]
0x18005567e  mov     [rbp+4Fh+var_80], rax
0x180055682  mov     rcx, [r12]
0x180055686  add     rcx, 30h ; '0'; newString
0x18005568a  lea     rdx, [rbp+4Fh+var_80]; HSTRING *
0x18005568e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180055693  xor     edx, edx; length
0x180055695  mov     rcx, [r15]; string
0x180055698  call    cs:__imp_WindowsGetStringRawBuffer
0x18005569e  mov     rcx, rax; unsigned __int16 *
0x1800556a1  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x1800556a6  lea     rbx, [rax+1A8h]
0x1800556ad  movsd   xmm0, [rbp+4Fh+var_88]
0x1800556b2  comisd  xmm0, xmm6
0x1800556b6  jbe     short loc_1800556F8
0x1800556b8  mov     [rbx+1], sil
0x1800556bc  cvttsd2si rax, [rbp+4Fh+var_88]
0x1800556c2  mov     [rbx+8], eax
0x1800556c5  mov     rcx, rbx; this
0x1800556c8  call    ?FetchAndSaveExperimentState@TSExperimentationState@@QEAAXXZ; TSExperimentationState::FetchAndSaveExperimentState(void)
0x1800556cd  cmp     dword ptr [rbx+8], 0
0x1800556d1  jbe     short loc_180055748
0x1800556d3  cmp     dword ptr [rbx+4], 0
0x1800556d7  jnz     short loc_180055748
0x1800556d9  mov     rcx, [rbp+57h]; this
0x1800556dd  mov     ebx, 80BBFA12h
0x1800556e2  mov     r9d, ebx; char *
0x1800556e5  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800556ec  mov     edx, 174h; void *
0x1800556f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800556f6  jmp     short loc_18005574A
0x1800556f8  mov     byte ptr [rbx+1], 0
0x1800556fc  mov     rcx, [r13+0]
0x180055700  test    rcx, rcx
0x180055703  jz      short loc_180055748
0x180055705  mov     dword ptr [rbp+4Fh+var_B0], 0
0x18005570c  mov     rax, [rcx]
0x18005570f  lea     r8, [rbp+4Fh+var_B0]
0x180055713  mov     rdx, [r14]
0x180055716  mov     rax, [rax+0A0h]
0x18005571d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055722  mov     edi, eax
0x180055724  test    eax, eax
0x180055726  js      short loc_1800557A2
0x180055728  mov     ecx, dword ptr [rbp+4Fh+var_B0]
0x18005572b  test    ecx, ecx
0x18005572d  jz      short loc_180055743
0x18005572f  sub     ecx, 1
0x180055732  jz      short loc_18005573E
0x180055734  cmp     ecx, 1
0x180055737  jnz     short loc_180055743
0x180055739  lea     esi, [rcx+1]
0x18005573c  jmp     short loc_180055745
0x18005573e  mov     [rbx], sil
0x180055741  jmp     short loc_180055745
0x180055743  xor     esi, esi
0x180055745  mov     [rbx+4], esi
0x180055748  xor     ebx, ebx
0x18005574a  mov     rcx, [rbp+4Fh+var_98]; string
0x18005574e  call    cs:__imp_WindowsDeleteString
0x180055754  mov     [rbp+4Fh+var_98], 0
0x18005575c  mov     rcx, [rbp+4Fh+var_A8]; string
0x180055760  call    cs:__imp_WindowsDeleteString
0x180055766  mov     [rbp+4Fh+var_A8], 0
0x18005576e  mov     rcx, [rbp+4Fh+string]; string
0x180055772  call    cs:__imp_WindowsDeleteString
0x180055778  mov     eax, ebx
0x18005577a  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x18005577e  xor     rcx, rsp; StackCookie
0x180055781  call    __security_check_cookie
0x180055786  movaps  xmm6, [rsp+0D0h+var_58+8]
0x18005578e  add     rsp, 98h
0x180055795  pop     r15
0x180055797  pop     r14
0x180055799  pop     r13
0x18005579b  pop     r12
0x18005579d  pop     rdi
0x18005579e  pop     rsi
0x18005579f  pop     rbx
0x1800557a0  pop     rbp
0x1800557a1  retn
0x1800557a2  mov     rcx, [rbp+57h]; this
0x1800557a6  mov     r9d, edi; char *
0x1800557a9  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800557b0  mov     edx, 183h; void *
0x1800557b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557ba  mov     ebx, edi
0x1800557bc  jmp     short loc_18005574A
```
