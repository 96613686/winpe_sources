# Jot::CModifyNotebookPropertiesListener::MoveNotebookButtonClick(void)

- ea: `0x140152308`
- end: `0x1401527ac`
- name: `?MoveNotebookButtonClick@CModifyNotebookPropertiesListener@Jot@@AEAA?AW4MoveNotebookResult@12@XZ`
- size: `1188`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400d5760`

## callees

- `0x140012020`
- `0x14002535c`
- `0x140054290`
- `0x140057580`
- `0x14008708c`
- `0x1400cd2c8`
- `0x1400d5008`
- `0x1400ec1c4`
- `0x14013479c`
- `0x14013c3f4`
- `0x140151df8`
- `0x140152308`

## import_xrefs

- `onmain!??1Activity@Logging@Jot@@QEAA@XZ` at `0x140152744`
- `onmain!??1Activity@Logging@Jot@@QEAA@XZ` at `0x140152791`
- `onmain!??1Activity@Logging@Jot@@QEAA@XZ` at `0x140152744`
- `onmain!??1Activity@Logging@Jot@@QEAA@XZ` at `0x140152791`
- `onmain!?GetThreadCurrentParenter@Activity@Logging@Jot@@SA?AV?$TCntPtr@UIActivityParenter@Telemetry@Mso@@@Mso@@XZ` at `0x140152328`
- `onmain!?GetThreadCurrentParenter@Activity@Logging@Jot@@SA?AV?$TCntPtr@UIActivityParenter@Telemetry@Mso@@@Mso@@XZ` at `0x140152328`
- `onmain!?SetContext@Activity@Logging@Jot@@AEAAXAEBV?$initializer_list@PEBUIStructuredTrace@Logging@Mso@@@std@@@Z` at `0x1401524bd`
- `onmain!?SetContext@Activity@Logging@Jot@@AEAAXAEBV?$initializer_list@PEBUIStructuredTrace@Logging@Mso@@@std@@@Z` at `0x1401524bd`
- `onmain!?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ` at `0x140152559`
- `onmain!?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ` at `0x1401526c4`
- `onmain!?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ` at `0x140152559`
- `onmain!?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ` at `0x1401526c4`
- `onmain!?GetNamespace@NotebookManagement@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x14015239c`
- `onmain!?GetNamespace@NotebookManagement@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x14015239c`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140152683`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14015271e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140152770`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140152683`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14015271e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140152770`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14015260f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401526b9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14015260f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401526b9`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140152396`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140152396`

## string_xrefs

- `0x1401526a9`: `ReopenNotebookFailed`

## pseudocode

```c
__int64 __fastcall Jot::CModifyNotebookPropertiesListener::MoveNotebookButtonClick(__int64 a1)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  Office::OneNote::NotebookManagement *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rbx
  struct MsoCF::AFrame *v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rbx
  unsigned __int8 (__fastcall *v12)(__int64, __int64, _QWORD, _QWORD); // r15
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // rdi
  const char *v16; // rdx
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h]
  _BYTE v20[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct MsoCF::IActionContext *v21; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v22; // [rsp+60h] [rbp-A0h] BYREF
  char v23; // [rsp+62h] [rbp-9Eh]
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 *Namespace; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v26; // [rsp+78h] [rbp-88h]
  _BYTE v27[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[48]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v29[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v30[496]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v32; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v33; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v34; // [rsp+2D8h] [rbp+1D8h] BYREF
  char v35; // [rsp+2D9h] [rbp+1D9h]

  v2 = *(_QWORD *)Jot::Logging::Activity::GetThreadCurrentParenter(&v24);
  v3 = 0;
  v20[1] = 0;
  v35 = 0;
  v22 = 6;
  v23 = 1;
  LOWORD(v31) = 258;
  LOWORD(v32) = 256;
  LOWORD(v33) = 447;
  Mso::Telemetry::EventFlags::EventFlags(v27, &v33, &v32, &v31, &v22, &v34);
  Namespace = (__int64 *)Office::OneNote::NotebookManagement::GetNamespace(v4);
  v26 = (__int64 *)"NotebookPropertiesChangeLocationButton";
  Jot::Logging::HighValueActivity::HighValueActivity(
    (unsigned int)v30,
    (unsigned int)&Namespace,
    (unsigned int)v27,
    (unsigned int)v20,
    v2);
  v5 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *(_QWORD *)MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::Now(&v31);
  v21 = 0;
  v7 = Jot::CBaseRootElement::UseFrame(*(Jot::CBaseRootElement **)(a1 + 40));
  (*(void (__fastcall **)(struct MsoCF::AFrame *, struct MsoCF::IActionContext **))(*(_QWORD *)v7 + 80LL))(v7, &v21);
  v18 = 0;
  v19 = 0;
  Jot::CBasicUIActor::OpenFileDialog((__int64)v7, v21, 9u, 0, 0, (const char *)&v18, 0);
  MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::TimeSince(&v31, v6);
  v32 = v31 / 10;
  v31 = Jot::Logging::details::LogDataValidated<unsigned __int64>(v28, v31 / 10, &v32);
  Namespace = &v31;
  v26 = &v32;
  Jot::Logging::Activity::SetContext(v30, &Namespace);
  std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v29);
  if ( v19 == 117899322 && v18 )
  {
    v8 = (*(__int64 (__fastcall **)(struct MsoCF::AFrame *))(*(_QWORD *)v7 + 144LL))(v7);
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v8 + 112) + 680LL))(
                     *(_QWORD *)(v8 + 112),
                     &v33);
    (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v9 + 536LL))(*v9, &v32);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v32 )
    {
      v31 = 0;
      LOBYTE(v10) = 1;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v32 + 48LL))(v32, &v31, v10) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 56LL))(v31);
        v11 = v31;
        v12 = *(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v31 + 32LL);
        if ( v19 != 117899322 || !v18 )
        {
          CrashWithRecovery(0x65756F6Eu, 0);
          __debugbreak();
        }
        v13 = (*(_DWORD *)(v18 + 4) >> 1) & 0x1FFFFFFF;
        v14 = v18 + 8;
        if ( v18 != -8 )
        {
          if ( !(_DWORD)v13 || (v15 = v18 + 8 + 2 * v13, _std_find_trivial_2(v18 + 8, v15, 0) == v15) )
          {
            CrashWithRecovery(0x1F46100Du, 0);
            __debugbreak();
          }
        }
        if ( v12(v11, v14, 0, 0) )
        {
          Jot::Logging::Activity::Succeed<char const *,>(v30, &qword_1401B4DB8);
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v32 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          if ( (v19 & 0x2000000) != 0 )
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&v18);
          if ( v21 )
            (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v21 + 16LL))(v21);
          goto LABEL_37;
        }
        v16 = "ReopenNotebookFailed";
      }
      else
      {
        Jot::Logging::Activity::SetLogUnexpectedFlag((Jot::Logging::Activity *)v30);
        v16 = "NotebookCannotSync";
      }
      Jot::Logging::Activity::Fail<char const *,>(v30, v16);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    else
    {
      Jot::Logging::Activity::SetLogUnexpectedFlag((Jot::Logging::Activity *)v30);
      Jot::Logging::Activity::Fail<char const *,>(v30, "NoActiveNotebook");
    }
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( (v19 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v18);
    if ( v21 )
      (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v21 + 16LL))(v21);
    v3 = 2;
LABEL_37:
    Jot::Logging::Activity::~Activity((Jot::Logging::Activity *)v30);
    return v3;
  }
  Jot::Logging::Activity::Fail<char const *,>(v30, "UserCancelled");
  if ( (v19 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v18);
  if ( v21 )
    (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v21 + 16LL))(v21);
  Jot::Logging::Activity::~Activity((Jot::Logging::Activity *)v30);
  return 1;
}

```

## disassembly

```asm
0x140152308  push    rbp
0x14015230a  push    rbx
0x14015230b  push    rsi
0x14015230c  push    rdi
0x14015230d  push    r14
0x14015230f  push    r15
0x140152311  lea     rbp, [rsp-188h]
0x140152319  sub     rsp, 288h
0x140152320  mov     rdi, rcx
0x140152323  lea     rcx, [rsp+2B0h+var_248]
0x140152328  call    cs:__imp_?GetThreadCurrentParenter@Activity@Logging@Jot@@SA?AV?$TCntPtr@UIActivityParenter@Telemetry@Mso@@@Mso@@XZ; Jot::Logging::Activity::GetThreadCurrentParenter(void)
0x14015232e  mov     rbx, [rax]
0x140152331  xor     esi, esi
0x140152333  mov     [rsp+2B0h+var_25F], sil
0x140152338  mov     [rbp+1B0h+arg_19], sil
0x14015233f  lea     eax, [rsi+6]
0x140152342  mov     [rsp+2B0h+var_250], ax
0x140152347  mov     [rsp+2B0h+var_24E], 1
0x14015234c  mov     word ptr [rbp+1B0h+arg_0], 102h
0x140152355  mov     word ptr [rbp+1B0h+arg_8], 100h
0x14015235e  mov     word ptr [rbp+1B0h+arg_10], 1BFh
0x140152367  lea     rax, [rbp+1B0h+arg_18]
0x14015236e  mov     [rsp+2B0h+var_288], rax
0x140152373  lea     rax, [rsp+2B0h+var_250]
0x140152378  mov     [rsp+2B0h+var_290], rax
0x14015237d  lea     r9, [rbp+1B0h+arg_0]
0x140152384  lea     r8, [rbp+1B0h+arg_8]
0x14015238b  lea     rdx, [rbp+1B0h+arg_10]
0x140152392  lea     rcx, [rbp+1B0h+var_230]
0x140152396  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x14015239c  call    cs:__imp_?GetNamespace@NotebookManagement@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::OneNote::NotebookManagement::GetNamespace(void)
0x1401523a2  mov     [rsp+2B0h+var_240], rax
0x1401523a7  lea     rax, aNotebookproper; "NotebookPropertiesChangeLocationButton"
0x1401523ae  mov     [rsp+2B0h+var_238], rax
0x1401523b3  mov     [rsp+2B0h+var_290], rbx
0x1401523b8  lea     r9, [rsp+2B0h+var_260]
0x1401523bd  lea     r8, [rbp+1B0h+var_230]
0x1401523c1  lea     rdx, [rsp+2B0h+var_240]
0x1401523c6  lea     rcx, [rbp+1B0h+var_1F0]
0x1401523ca  call    ??0HighValueActivity@Logging@Jot@@QEAA@AEBUEventName@Telemetry@Mso@@AEBUEventFlags@45@$$QEAV?$optional@VEventExportability@Telemetry@Mso@@@std@@AEBUIActivityParenter@45@@Z; Jot::Logging::HighValueActivity::HighValueActivity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,std::optional<Mso::Telemetry::EventExportability> &&,Mso::Telemetry::IActivityParenter const &)
0x1401523cf  mov     rcx, [rsp+2B0h+var_248]
0x1401523d4  test    rcx, rcx
0x1401523d7  jz      short loc_1401523EB
0x1401523d9  mov     [rsp+2B0h+var_248], rsi
0x1401523de  mov     rax, [rcx]
0x1401523e1  mov     rax, [rax+10h]
0x1401523e5  call    cs:__guard_dispatch_icall_fptr
0x1401523eb  lea     rcx, [rbp+1B0h+arg_0]
0x1401523f2  call    ?Now@?$CTickCountBase@UGetTickCountAPIs@Jot@@@MsoCF@@SA?AV12@XZ; MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::Now(void)
0x1401523f7  mov     rbx, [rax]
0x1401523fa  mov     [rsp+2B0h+var_258], rsi
0x1401523ff  mov     rcx, [rdi+28h]; this
0x140152403  call    ?UseFrame@CBaseRootElement@Jot@@QEAAPEAUAFrame@MsoCF@@XZ; Jot::CBaseRootElement::UseFrame(void)
0x140152408  mov     rdi, rax
0x14015240b  mov     rcx, [rax]
0x14015240e  mov     rax, [rcx+50h]
0x140152412  lea     rdx, [rsp+2B0h+var_258]
0x140152417  mov     rcx, rdi
0x14015241a  call    cs:__guard_dispatch_icall_fptr
0x140152420  mov     [rsp+2B0h+var_270], rsi
0x140152425  mov     [rsp+2B0h+var_268], esi
0x140152429  mov     [rsp+2B0h+var_280], esi
0x14015242d  lea     rax, [rsp+2B0h+var_270]
0x140152432  mov     [rsp+2B0h+var_288], rax
0x140152437  mov     [rsp+2B0h+var_290], rsi
0x14015243c  xor     r9d, r9d
0x14015243f  lea     r8d, [r9+9]
0x140152443  mov     rdx, [rsp+2B0h+var_258]
0x140152448  mov     rcx, rdi
0x14015244b  call    ?OpenFileDialog@CBasicUIActor@Jot@@SA_NPEAUAFrame@MsoCF@@PEAUIActionContext@4@W4EnumOpenFileIndex@2@PEB_W3PEAVCPropertyValue@4@I@Z; Jot::CBasicUIActor::OpenFileDialog(MsoCF::AFrame *,MsoCF::IActionContext *,Jot::EnumOpenFileIndex,wchar_t const *,wchar_t const *,MsoCF::CPropertyValue *,uint)
0x140152450  mov     rdx, rbx
0x140152453  lea     rcx, [rbp+1B0h+arg_0]
0x14015245a  call    ?TimeSince@?$CTickCountBase@UGetTickCountAPIs@Jot@@@MsoCF@@SA?AVCTimeSpan@2@V12@@Z; MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::TimeSince(MsoCF::CTickCountBase<Jot::GetTickCountAPIs>)
0x14015245f  mov     rax, 6666666666666667h
0x140152469  imul    [rbp+1B0h+arg_0]
0x140152470  sar     rdx, 2
0x140152474  mov     rax, rdx
0x140152477  shr     rax, 3Fh
0x14015247b  add     rdx, rax
0x14015247e  mov     [rbp+1B0h+arg_8], rdx
0x140152485  lea     r8, [rbp+1B0h+arg_8]
0x14015248c  lea     rcx, [rbp+1B0h+var_228]
0x140152490  call    ??$LogDataValidated@_K@details@Logging@Jot@@YA?A_PPEBDAEB_KW4DataClassifications@1Mso@@@Z
0x140152495  mov     [rbp+1B0h+arg_0], rax
0x14015249c  lea     rax, [rbp+1B0h+arg_0]
0x1401524a3  mov     [rsp+2B0h+var_240], rax
0x1401524a8  lea     rax, [rbp+1B0h+arg_8]
0x1401524af  mov     [rsp+2B0h+var_238], rax
0x1401524b4  lea     rdx, [rsp+2B0h+var_240]
0x1401524b9  lea     rcx, [rbp+1B0h+var_1F0]
0x1401524bd  call    cs:__imp_?SetContext@Activity@Logging@Jot@@AEAAXAEBV?$initializer_list@PEBUIStructuredTrace@Logging@Mso@@@std@@@Z; Jot::Logging::Activity::SetContext(std::initializer_list<Mso::Logging::IStructuredTrace const *> const &)
0x1401524c3  lea     rcx, [rbp+1B0h+var_1F8]
0x1401524c7  call    ??1?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(void)
0x1401524cc  mov     r14d, 707003Ah
0x1401524d2  cmp     [rsp+2B0h+var_268], r14d
0x1401524d7  jnz     loc_14015274E
0x1401524dd  cmp     [rsp+2B0h+var_270], rsi
0x1401524e2  jz      loc_14015274E
0x1401524e8  mov     rax, [rdi]
0x1401524eb  mov     rcx, rdi
0x1401524ee  mov     rax, [rax+90h]
0x1401524f5  call    cs:__guard_dispatch_icall_fptr
0x1401524fb  mov     rcx, [rax+70h]
0x1401524ff  mov     rax, [rcx]
0x140152502  lea     rdx, [rbp+1B0h+arg_10]
0x140152509  mov     rax, [rax+2A8h]
0x140152510  call    cs:__guard_dispatch_icall_fptr
0x140152516  mov     rcx, [rax]
0x140152519  mov     rax, [rcx]
0x14015251c  lea     rdx, [rbp+1B0h+arg_8]
0x140152523  mov     rax, [rax+218h]
0x14015252a  call    cs:__guard_dispatch_icall_fptr
0x140152530  mov     rcx, [rbp+1B0h+arg_10]
0x140152537  test    rcx, rcx
0x14015253a  jz      short loc_140152549
0x14015253c  mov     rax, [rcx]
0x14015253f  mov     rax, [rax+10h]
0x140152543  call    cs:__guard_dispatch_icall_fptr
0x140152549  mov     rcx, [rbp+1B0h+arg_8]
0x140152550  test    rcx, rcx
0x140152553  jnz     short loc_140152574
0x140152555  lea     rcx, [rbp+1B0h+var_1F0]
0x140152559  call    cs:__imp_?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ; Jot::Logging::Activity::SetLogUnexpectedFlag(void)
0x14015255f  lea     rdx, aNoactivenotebo; "NoActiveNotebook"
0x140152566  lea     rcx, [rbp+1B0h+var_1F0]
0x14015256a  call    ??$Fail@PEBD$$V@Activity@Logging@Jot@@QEAAXQEBDK@Z; Jot::Logging::Activity::Fail<char const *,>(char const * const,ulong)
0x14015256f  jmp     loc_1401526F3
0x140152574  mov     [rbp+1B0h+arg_0], rsi
0x14015257b  mov     rax, [rcx]
0x14015257e  mov     r8b, 1
0x140152581  lea     rdx, [rbp+1B0h+arg_0]
0x140152588  mov     rax, [rax+30h]
0x14015258c  call    cs:__guard_dispatch_icall_fptr
0x140152592  test    al, al
0x140152594  jz      loc_1401526C0
0x14015259a  mov     rcx, [rbp+1B0h+arg_0]
0x1401525a1  mov     rax, [rcx]
0x1401525a4  mov     rax, [rax+38h]
0x1401525a8  call    cs:__guard_dispatch_icall_fptr
0x1401525ae  mov     rbx, [rbp+1B0h+arg_0]
0x1401525b5  mov     rax, [rbx]
0x1401525b8  mov     r15, [rax+20h]
0x1401525bc  cmp     [rsp+2B0h+var_268], r14d
0x1401525c1  jnz     loc_1401526B2
0x1401525c7  mov     rcx, [rsp+2B0h+var_270]
0x1401525cc  test    rcx, rcx
0x1401525cf  jz      loc_1401526B2
0x1401525d5  mov     eax, [rcx+4]
0x1401525d8  shr     eax, 1
0x1401525da  and     eax, 1FFFFFFFh
0x1401525df  lea     r14, [rcx+8]
0x1401525e3  test    r14, r14
0x1401525e6  jz      short loc_140152616
0x1401525e8  cmp     eax, 1
0x1401525eb  jb      short loc_140152608
0x1401525ed  add     rcx, 8
0x1401525f1  lea     rdi, [rcx+rax*2]
0x1401525f5  xor     r8d, r8d
0x1401525f8  mov     rdx, rdi
0x1401525fb  mov     rcx, r14
0x1401525fe  call    __std_find_trivial_2
0x140152603  cmp     rax, rdi
0x140152606  jnz     short loc_140152616
0x140152608  xor     edx, edx
0x14015260a  mov     ecx, 1F46100Dh
0x14015260f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140152615  int     3; Trap to Debugger
0x140152616  xor     r9d, r9d
0x140152619  xor     r8d, r8d
0x14015261c  mov     rdx, r14
0x14015261f  mov     rcx, rbx
0x140152622  mov     rax, r15
0x140152625  call    cs:__guard_dispatch_icall_fptr
0x14015262b  lea     rcx, [rbp+1B0h+var_1F0]
0x14015262f  test    al, al
0x140152631  jz      short loc_1401526A9
0x140152633  lea     rdx, qword_1401B4DB8
0x14015263a  call    ??$Succeed@PEBD$$V@Activity@Logging@Jot@@QEAAXQEBD@Z; Jot::Logging::Activity::Succeed<char const *,>(char const * const)
0x14015263f  mov     rcx, [rbp+1B0h+arg_0]
0x140152646  test    rcx, rcx
0x140152649  jz      short loc_140152658
0x14015264b  mov     rax, [rcx]
0x14015264e  mov     rax, [rax+10h]
0x140152652  call    cs:__guard_dispatch_icall_fptr
0x140152658  mov     rcx, [rbp+1B0h+arg_8]
0x14015265f  test    rcx, rcx
0x140152662  jz      short loc_140152671
0x140152664  mov     rax, [rcx]
0x140152667  mov     rax, [rax+10h]
0x14015266b  call    cs:__guard_dispatch_icall_fptr
0x140152671  mov     edx, [rsp+2B0h+var_268]
0x140152675  mov     eax, edx
0x140152677  shr     eax, 19h
0x14015267a  test    al, 1
0x14015267c  jz      short loc_140152689
0x14015267e  lea     rcx, [rsp+2B0h+var_270]
0x140152683  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140152689  mov     rcx, [rsp+2B0h+var_258]
0x14015268e  test    rcx, rcx
0x140152691  jz      loc_140152740
0x140152697  mov     rax, [rcx]
0x14015269a  mov     rax, [rax+10h]
0x14015269e  call    cs:__guard_dispatch_icall_fptr
0x1401526a4  jmp     loc_140152740
0x1401526a9  lea     rdx, aReopennotebook; "ReopenNotebookFailed"
0x1401526b0  jmp     short loc_1401526D5
0x1401526b2  xor     edx, edx
0x1401526b4  mov     ecx, 65756F6Eh
0x1401526b9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1401526bf  int     3; Trap to Debugger
0x1401526c0  lea     rcx, [rbp+1B0h+var_1F0]
0x1401526c4  call    cs:__imp_?SetLogUnexpectedFlag@Activity@Logging@Jot@@AEAAXXZ; Jot::Logging::Activity::SetLogUnexpectedFlag(void)
0x1401526ca  lea     rdx, aNotebookcannot; "NotebookCannotSync"
0x1401526d1  lea     rcx, [rbp+1B0h+var_1F0]
0x1401526d5  call    ??$Fail@PEBD$$V@Activity@Logging@Jot@@QEAAXQEBDK@Z; Jot::Logging::Activity::Fail<char const *,>(char const * const,ulong)
0x1401526da  mov     rcx, [rbp+1B0h+arg_0]
0x1401526e1  test    rcx, rcx
0x1401526e4  jz      short loc_1401526F3
0x1401526e6  mov     rax, [rcx]
0x1401526e9  mov     rax, [rax+10h]
0x1401526ed  call    cs:__guard_dispatch_icall_fptr
0x1401526f3  mov     rcx, [rbp+1B0h+arg_8]
0x1401526fa  test    rcx, rcx
0x1401526fd  jz      short loc_14015270C
0x1401526ff  mov     rax, [rcx]
0x140152702  mov     rax, [rax+10h]
0x140152706  call    cs:__guard_dispatch_icall_fptr
0x14015270c  mov     edx, [rsp+2B0h+var_268]
0x140152710  mov     eax, edx
0x140152712  shr     eax, 19h
0x140152715  test    al, 1
0x140152717  jz      short loc_140152724
0x140152719  lea     rcx, [rsp+2B0h+var_270]
0x14015271e  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140152724  mov     rcx, [rsp+2B0h+var_258]
0x140152729  test    rcx, rcx
0x14015272c  jz      short loc_14015273B
0x14015272e  mov     rax, [rcx]
0x140152731  mov     rax, [rax+10h]
0x140152735  call    cs:__guard_dispatch_icall_fptr
0x14015273b  mov     esi, 2
0x140152740  lea     rcx, [rbp+1B0h+var_1F0]
0x140152744  call    cs:__imp_??1Activity@Logging@Jot@@QEAA@XZ; Jot::Logging::Activity::~Activity(void)
0x14015274a  mov     eax, esi
0x14015274c  jmp     short loc_14015279C
0x14015274e  lea     rdx, aUsercancelled; "UserCancelled"
0x140152755  lea     rcx, [rbp+1B0h+var_1F0]
0x140152759  call    ??$Fail@PEBD$$V@Activity@Logging@Jot@@QEAAXQEBDK@Z; Jot::Logging::Activity::Fail<char const *,>(char const * const,ulong)
0x14015275e  mov     edx, [rsp+2B0h+var_268]
0x140152762  mov     eax, edx
0x140152764  shr     eax, 19h
0x140152767  test    al, 1
0x140152769  jz      short loc_140152776
0x14015276b  lea     rcx, [rsp+2B0h+var_270]
0x140152770  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140152776  mov     rcx, [rsp+2B0h+var_258]
0x14015277b  test    rcx, rcx
0x14015277e  jz      short loc_14015278D
0x140152780  mov     rdx, [rcx]
0x140152783  mov     rax, [rdx+10h]
0x140152787  call    cs:__guard_dispatch_icall_fptr
0x14015278d  lea     rcx, [rbp+1B0h+var_1F0]
0x140152791  call    cs:__imp_??1Activity@Logging@Jot@@QEAA@XZ; Jot::Logging::Activity::~Activity(void)
0x140152797  mov     eax, 1
0x14015279c  add     rsp, 288h
0x1401527a3  pop     r15
0x1401527a5  pop     r14
0x1401527a7  pop     rdi
0x1401527a8  pop     rsi
0x1401527a9  pop     rbx
0x1401527aa  pop     rbp
0x1401527ab  retn
```
