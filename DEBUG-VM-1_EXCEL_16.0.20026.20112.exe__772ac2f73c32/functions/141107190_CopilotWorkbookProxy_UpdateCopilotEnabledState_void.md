# CopilotWorkbookProxy::UpdateCopilotEnabledState(void)

- ea: `0x141107190`
- end: `0x141107dec`
- name: `?UpdateCopilotEnabledState@CopilotWorkbookProxy@@QEAAXXZ`
- size: `3164`
- prototype: `void __fastcall(CopilotWorkbookProxy *__hidden this)`
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x141483610`
- `0x1417a5d50`
- `0x1418def80`
- `0x14331f420`
- `0x1434a69e0`
- `0x1434c9ec0`
- `0x1434d5ad0`
- `0x1434d6170`

## callees

- `0x14004d9e0`
- `0x140056d24`
- `0x140056d90`
- `0x1400b3fdc`
- `0x1400dfed0`
- `0x1400e8050`
- `0x1400ebbe0`
- `0x140177c00`
- `0x1401bfdd0`
- `0x1401e7c50`
- `0x140203fe0`
- `0x14021f590`
- `0x140255270`
- `0x14026cd70`
- `0x140273e90`
- `0x1404850e0`
- `0x140548080`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140cc2870`
- `0x141052fc0`
- `0x1410654f0`
- `0x141107190`
- `0x14125b930`
- `0x1412cc610`
- `0x1415d9490`
- `0x14185cc60`
- `0x141862110`
- `0x1418de700`
- `0x14344b940`
- `0x14349cab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141107500`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x14110752c`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141107500`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x14110752c`
- `MSO!__imp_?IsCopilotDABUnboxingEnabled@CopilotToolkit@@YA_NXZ` at `0x14110788e`
- `MSO!__imp_?IsCopilotDABUnboxingEnabled@CopilotToolkit@@YA_NXZ` at `0x14110788e`
- `Mso98Win32Client!__imp_?IncrementDABUnboxingQualifyingCount@DABUnboxing@Copilot@Mso@@YA_NXZ` at `0x1411078c0`
- `Mso98Win32Client!__imp_?IncrementDABUnboxingQualifyingCount@DABUnboxing@Copilot@Mso@@YA_NXZ` at `0x1411078c0`
- `Mso98Win32Client!__imp_?IsCopilotAutoOpenAllowedForIdentity@Copilot@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@_N@Z` at `0x141107a6e`
- `Mso98Win32Client!__imp_?IsCopilotAutoOpenAllowedForIdentity@Copilot@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@_N@Z` at `0x141107a6e`
- `Mso30Win32Client!__imp_?IsAppGuard@Config@AppGuard@@YA_NXZ` at `0x141107cd4`
- `Mso30Win32Client!__imp_?IsAppGuard@Config@AppGuard@@YA_NXZ` at `0x141107cd4`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x1411077e9`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x1411077e9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141107330`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141107330`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411071d8`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107261`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411073a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411073c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411075d0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107638`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107702`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411078e4`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411071d8`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107261`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411073a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411073c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411075d0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107638`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107702`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411078e4`
- `Mso20Win32Client!__imp_?UseCurrentThread@FastModel@@YAAEAVThread@1@XZ` at `0x1411077b5`
- `Mso20Win32Client!__imp_?UseCurrentThread@FastModel@@YAAEAVThread@1@XZ` at `0x1411077b5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1411077cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141107d80`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1411077cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141107d80`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x1411079d9`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x141107b40`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x1411079d9`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x141107b40`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107780`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107993`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107af8`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107c73`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107780`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107993`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107af8`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141107c73`
- `Mso20Win32Client!__imp_?Evaluate@?$Setting@H@Optimized@AB@Mso@@AEBAAEBHXZ` at `0x14110780c`
- `Mso20Win32Client!__imp_?Evaluate@?$Setting@H@Optimized@AB@Mso@@AEBAAEBHXZ` at `0x14110780c`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141107580`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141107580`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411072d0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107373`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107670`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107ba0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107bc4`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107d20`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1411072d0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107373`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107670`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107ba0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107bc4`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141107d20`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107760`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107973`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107ad9`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107c54`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107760`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107973`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107ad9`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141107c54`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1411077aa`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1411079c0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141107b22`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141107ca0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1411077aa`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1411079c0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141107b22`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141107ca0`
- `Mso20Win32Client!__imp_?PostTimer@Details@Async@Mso@@YAXPEAV?$TCntPtr@UITimerObject@Async@Mso@@@3@_NIPEAVIDispatchQueue@23@$$QEAV?$Functor@$$A6AXXZ@3@@Z` at `0x141107831`
- `Mso20Win32Client!__imp_?PostTimer@Details@Async@Mso@@YAXPEAV?$TCntPtr@UITimerObject@Async@Mso@@@3@_NIPEAVIDispatchQueue@23@$$QEAV?$Functor@$$A6AXXZ@3@@Z` at `0x141107831`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14110776c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107980`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107ae5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107c60`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14110776c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107980`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107ae5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141107c60`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107749`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107960`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107ac6`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107c41`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107749`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107960`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107ac6`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141107c41`

## pseudocode

```c
void __fastcall CopilotWorkbookProxy::UpdateCopilotEnabledState(
        CopilotWorkbookProxy *this,
        const struct Api::Workbook *a2)
{
  CopilotWorkbookProxy *v2; // rdi
  char v3; // r12
  bool v4; // al
  const struct Mso::Authentication::IOfficeIdentity *DocumentIdentity; // rbx
  volatile signed __int32 *v6; // rax
  int v7; // esi
  bool v8; // al
  Copilot **v9; // r14
  __int64 v10; // rcx
  Copilot::Internal *v11; // rcx
  Copilot *v12; // rbx
  bool v13; // al
  int v14; // r13d
  int v15; // ebx
  int v16; // eax
  int v17; // esi
  bool v18; // al
  bool v19; // al
  bool v20; // al
  Copilot *v21; // rcx
  const struct Api::Workbook *v22; // rdx
  int v23; // r14d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  BOOK *v28; // rcx
  struct IMsoOLDocument *v29; // rdx
  bool v30; // al
  __int64 (__fastcall ***v31)(_QWORD, struct IMsoOLDocument *); // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  Copilot::Internal *v34; // rcx
  bool v35; // al
  bool v36; // si
  bool v37; // al
  char v38; // bl
  bool v39; // al
  __int64 v40; // rax
  bool v41; // al
  const struct Mso::CancellationToken *v42; // rax
  unsigned int v43; // r8d
  _DWORD *v44; // rax
  _DWORD *v45; // rbx
  FastModel *v46; // rcx
  struct FastModel::Thread *v47; // rax
  Mso::Async::Details *v48; // rax
  struct Mso::Async::IDispatchQueue *v49; // rdx
  struct Mso::Async::IDispatchQueue *v50; // rsi
  unsigned int *v51; // rax
  unsigned int v52; // ebx
  __int64 v53; // rax
  _DWORD *v54; // rcx
  Copilot::Internal *v55; // rcx
  CopilotToolkit *v56; // rcx
  Mso::Copilot::DABUnboxing *v57; // rcx
  __int64 v58; // rax
  bool v59; // al
  unsigned int v60; // eax
  int v61; // esi
  __int64 v62; // rax
  const struct Mso::CancellationToken *Token; // rax
  unsigned int v64; // r8d
  _DWORD *v65; // rax
  _DWORD *v66; // rbx
  Threading *v67; // rcx
  struct Mso::Async::IDispatchQueue *v68; // rax
  _DWORD *v69; // rcx
  Copilot::Internal *v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rax
  char v73; // bl
  Mso::Copilot *v74; // rsi
  Copilot *v75; // rcx
  const struct Mso::Authentication::IOfficeIdentity *v76; // rdx
  Copilot::Internal *v77; // rcx
  bool v78; // r8
  unsigned int v79; // eax
  int v80; // esi
  const struct Mso::CancellationToken *v81; // rax
  unsigned int v82; // r8d
  _DWORD *v83; // rax
  _DWORD *v84; // rbx
  Threading *v85; // rcx
  struct Mso::Async::IDispatchQueue *v86; // rax
  _DWORD *v87; // rcx
  bool v88; // al
  bool v89; // al
  unsigned int v90; // eax
  const struct Mso::CancellationToken *v91; // rax
  unsigned int v92; // r8d
  _DWORD *v93; // rax
  RibbonHost *v94; // rcx
  AppGuard::Config *v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  bool v99; // al
  Copilot *v100; // rcx
  _DWORD *v101; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v102; // [rsp+38h] [rbp-C8h] BYREF
  const char *v103; // [rsp+40h] [rbp-C0h] BYREF
  Copilot::Internal *v104; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v105[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v106[2]; // [rsp+52h] [rbp-AEh] BYREF
  _BYTE v107[4]; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v108[3]; // [rsp+58h] [rbp-A8h] BYREF
  void **v109; // [rsp+70h] [rbp-90h] BYREF
  char v110[68]; // [rsp+78h] [rbp-88h] BYREF
  int v111; // [rsp+BCh] [rbp-44h]
  __int16 v112; // [rsp+C0h] [rbp-40h]
  void **v113; // [rsp+D0h] [rbp-30h] BYREF
  char Destination[72]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v115; // [rsp+120h] [rbp+20h]
  __int16 v116; // [rsp+128h] [rbp+28h]

  v2 = this;
  v3 = 0;
  if ( byte_1440AA2A8[0] < 0 )
    v4 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA2A8);
  else
    v4 = byte_1440AA2A8[0] != 0;
  if ( v4 )
  {
    DocumentIdentity = CopilotWorkbookProxy::GetDocumentIdentity(v2);
    CopilotWorkbookProxy::RefreshDocumentIdentity(v2);
    if ( DocumentIdentity != CopilotWorkbookProxy::GetDocumentIdentity(v2) )
    {
      CopilotWorkbookProxy::HrCloseTaskPane(v2);
      this = (CopilotWorkbookProxy *)*((_QWORD *)v2 + 3);
      if ( this )
      {
        *((_QWORD *)v2 + 3) = 0;
        v6 = (volatile signed __int32 *)(*(__int64 (__fastcall **)(CopilotWorkbookProxy *))(*(_QWORD *)this + 16LL))(this);
        a2 = (const struct Api::Workbook *)v6;
        this = (CopilotWorkbookProxy *)(unsigned int)_InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF);
        if ( (_DWORD)this == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
  }
  v7 = 0;
  if ( byte_1440AA298[0] < 0 )
    v8 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA298);
  else
    v8 = byte_1440AA298[0] != 0;
  if ( v8 && Copilot::Internal::FEnableCatalystChecks(this) )
  {
    v9 = (Copilot **)((char *)v2 + 120);
    v10 = *((_QWORD *)v2 + 15);
    goto LABEL_19;
  }
  v9 = (Copilot **)((char *)v2 + 120);
  if ( Copilot::Internal::FCopilotLicenseEnabledForTenant(*((Copilot::Internal **)v2 + 15), a2)
    || Copilot::Internal::FCopilotStarterLicenseEnabled(v11) )
  {
    goto LABEL_21;
  }
  if ( Copilot::Internal::FEnableCatalystChecks(v11) )
  {
    v10 = *((_QWORD *)v2 + 15);
LABEL_19:
    if ( (unsigned __int8)Copilot::Internal::IsChatExperienceEnabledForWorkbook(v10, 0) )
      goto LABEL_21;
  }
  v7 = 0x8000;
LABEL_21:
  v12 = *v9;
  if ( byte_144091D08[0] < 0 )
    v13 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_144091D08);
  else
    v13 = byte_144091D08[0] != 0;
  v14 = 4;
  if ( v13 )
  {
    v15 = 0;
  }
  else
  {
    v16 = AugmentationLoop::AugmentationLoopSessionImpl::CheckAugmentationLoopPrerequisitesMet(v12);
    v15 = 2 * (v16 & 1);
    if ( (v16 & 2) != 0 )
      v15 |= 4u;
    if ( (v16 & 4) != 0 )
      v15 |= 8u;
    if ( (v16 & 8) != 0 )
      v15 |= 0x1000u;
    if ( (v16 & 0x20) != 0 )
      v15 |= 0x10u;
    if ( (v16 & 0x10) != 0 )
      v15 |= 0x2000u;
    if ( (v16 & 0xFFFFFFC0) != 0 )
    {
      v15 |= 0x200u;
      MsoShipAssertTagProc(506012357);
    }
  }
  v17 = v15 | v7;
  if ( byte_14418F75A
    && (!Copilot::Internal::FEnableCatalystChecks(v11)
     || !(unsigned __int8)Copilot::Internal::IsChatExperienceEnabledForWorkbook(*v9, 0)) )
  {
    v17 |= 0x80u;
  }
  if ( byte_1440916E8[0] < 0 )
    v18 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_1440916E8);
  else
    v18 = byte_1440916E8[0] != 0;
  if ( v18 )
  {
    if ( byte_1440AA288[0] < 0 )
      v19 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA288);
    else
      v19 = byte_1440AA288[0] != 0;
    if ( !v19
      || (byte_14401EE10[0] < 0
        ? (v20 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_14401EE10))
        : (v20 = byte_14401EE10[0] != 0),
          !v20) )
    {
      if ( !Copilot::FEnabled(v11) )
        goto LABEL_59;
    }
    if ( (Copilot::Internal::GetCopilotVisibilityState(*v9) & 0x400) != 0 )
      goto LABEL_59;
  }
  else if ( !(unsigned __int8)Copilot::FCopilotButtonVisible(*v9, 0, 0) && !Copilot::FCopilotDABVisible(*v9, v22) )
  {
LABEL_59:
    v17 |= 0x100u;
  }
  v23 = v17 | 0x40;
  if ( Copilot::FSupportedLocales(v21) )
    v23 = v17;
  v24 = *((_QWORD *)v2 + 3);
  if ( v24 && (v25 = *(_QWORD *)(v24 + 8)) != 0 && *(_BYTE *)(v25 + 114) )
  {
    v23 |= 0x400u;
  }
  else
  {
    v26 = *((_QWORD *)v2 + 3);
    if ( !v26 || !*(_QWORD *)(v26 + 8) || !*(_BYTE *)(v26 + 24) )
      v23 |= 0x20u;
  }
  v27 = *((_QWORD *)v2 + 15);
  if ( !v27 || (v28 = *(BOOK **)(v27 + 24)) == 0 )
  {
    CrashWithRecovery(0x1E390655u, 0);
    goto LABEL_204;
  }
  v29 = BOOK::Pioldoc(v28);
  if ( v29 )
    v30 = (*(unsigned __int8 (__fastcall **)(PolicyTipsStartup *, struct IMsoOLDocument *))(*(_QWORD *)qword_144089870
                                                                                          + 864LL))(
            qword_144089870,
            v29) < 2u;
  else
    v30 = 0;
  if ( !v30 )
    v23 |= 0x800u;
  v14 = *((_DWORD *)v2 + 20);
  if ( v23 != v14 )
  {
    *((_DWORD *)v2 + 20) = v23;
    v31 = (__int64 (__fastcall ***)(_QWORD, struct IMsoOLDocument *))((*((_QWORD *)v2 + 15) + 152LL)
                                                                    & -(__int64)(*((_QWORD *)v2 + 15) != 0));
    v32 = (**v31)(v31, v29);
    v113 = &Mso::Telemetry::DataField<wchar_t const *>::`vftable';
    v115 = v32;
    v116 = 4;
    strncpy_s(Destination, 0x41u, "WorkbookId", 0xFFFFFFFFFFFFFFFFuLL);
    v109 = &Mso::Telemetry::DataField<int>::`vftable';
    v111 = v23;
    v112 = 4;
    strncpy_s(v110, 0x41u, "State", 0xFFFFFFFFFFFFFFFFuLL);
    v105[1] = 0;
    LOWORD(v101) = 2;
    BYTE2(v101) = 1;
    v106[1] = 0;
    v107[1] = 0;
    v102 = 257;
    Mso::Telemetry::EventFlags::EventFlags(&v103, &v102, v107, v106, &v101, v105);
    v108[0] = &off_14383B630;
    v108[1] = "CopilotEnabledState";
    Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<unsigned char>,Mso::Telemetry::DataField<wchar_t const *>>(
      v108,
      &v103,
      &v109,
      &v113);
    if ( byte_1440AA228[0] < 0 )
      v35 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA228);
    else
      v35 = byte_1440AA228[0] != 0;
    v36 = 0;
    if ( v35 )
    {
      v33 = 304;
      v34 = *(Copilot::Internal **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL);
      if ( *((_DWORD *)v34 + 14)
        || (vgrbitScanload & 1) != 0
        || *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
        && *(_DWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1376LL) )
      {
        v36 = 1;
      }
    }
    if ( byte_1440AA238[0] < 0 )
      v37 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA238);
    else
      v37 = byte_1440AA238[0] != 0;
    if ( !v37 || (v38 = 1, !*(_BYTE *)(*((_QWORD *)v2 + 15) + 2378LL)) )
      v38 = 0;
    if ( byte_1440AA098[0] < 0 )
      v39 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_1440AA098);
    else
      v39 = byte_1440AA098[0] != 0;
    if ( !v39
      || *((_BYTE *)v2 + 85)
      || v23 && (!Copilot::Internal::FEnableCatalystChecks(v34) || (v23 & 0xFFFF4BC0) != 0)
      || *((_QWORD *)v2 + 7)
      || v36
      || v38
      || ((v40 = *((_QWORD *)v2 + 3)) == 0 || !*(_QWORD *)(v40 + 8) || !*(_BYTE *)(v40 + 24))
      && (byte_144091A88[0] < 0
        ? (v41 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_144091A88))
        : (v41 = byte_144091A88[0] != 0),
          v41) )
    {
LABEL_125:
      if ( !*((_BYTE *)v2 + 97) )
      {
        *((_BYTE *)v2 + 97) = 1;
        if ( Copilot::DAB::FDabShouldShowForWorkbook(*((Copilot::DAB **)v2 + 15), (const struct Api::Workbook *)v33)
          && CopilotToolkit::IsCopilotDABUnboxingEnabled(v56) )
        {
          v58 = *((_QWORD *)v2 + 15);
          if ( v58 )
          {
            if ( (((*(_DWORD *)(*(_QWORD *)(v58 + 24) + 1280LL) & 7) - 2) & 0xFFFFFFFD) != 0 )
              Mso::Copilot::DABUnboxing::IncrementDABUnboxingQualifyingCount(v57);
          }
        }
      }
      CopilotWorkbookProxy::RequestDABVisibilityUpdate(v2);
      if ( byte_1440AA218[0] < 0 )
        v59 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1440AA218);
      else
        v59 = byte_1440AA218[0] != 0;
      if ( v59 )
      {
        v60 = *((_DWORD *)v2 + 20) & 0x220F;
        if ( (v60 > 0xC || (v61 = 4101, !_bittest(&v61, v60)))
          && !CopilotWorkbookProxy::FAugLoopEnabledForLocalFiles(v2)
          || (v62 = *((_QWORD *)v2 + 3)) == 0
          || !*(_QWORD *)(v62 + 8)
          || !*(_BYTE *)(v62 + 24)
          || *((_DWORD *)v2 + 23) )
        {
LABEL_186:
          CopilotWorkbookProxy::HrSendCopilotStateToSDX(v2);
          if ( (v14 & 0xFFFF4BC0) == 0 || (v23 & 0xFFFF4BC0) == 0 )
          {
            RibbonHost::UpdateAllCmdBars(v94);
            if ( (v23 & 0xFFFF4BC0) == 0 && !AppGuard::Config::IsAppGuard(v95) )
            {
              v97 = *((_QWORD *)v2 + 15);
              if ( !v97 || (v98 = *(_QWORD *)(v97 + 24)) == 0 || !*(_QWORD *)(v98 + 5416) )
              {
                LOBYTE(v96) = 1;
                Copilot::FCopilotButtonEnabled(v97, v96, 0);
              }
            }
          }
          if ( !v14 )
          {
            if ( byte_144091728[0] < 0 )
              v99 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_144091728);
            else
              v99 = byte_144091728[0] != 0;
            if ( v99 )
            {
              v100 = (Copilot *)*((_QWORD *)v2 + 15);
              if ( Copilot::SmartPasteDetails::g_pWorksheetPending )
              {
                if ( *((Copilot **)Copilot::SmartPasteDetails::g_pWorksheetPending + 5) == v100 )
                  Copilot::CancelPendingSmartPaste(v100);
              }
            }
          }
          return;
        }
        *((_DWORD *)v2 + 23) = 5;
        Token = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2336LL));
        v103 = (const char *)v2;
        Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)&v104, Token);
        v65 = Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, v64);
        v66 = v65;
        if ( !v65 )
        {
          CrashWithRecoveryOnOOM(0x131F462u);
          __debugbreak();
        }
        v65[2] = 1;
        *(_QWORD *)v65 = off_1437F5070;
        *((_QWORD *)v65 + 2) = v103;
        Mso::CancellationToken::CancellationToken(v65 + 6, &v104);
      }
      else
      {
        v71 = *((_QWORD *)v2 + 15);
        if ( !v71 || (v72 = *(_QWORD *)(v71 + 24)) == 0 || *(_QWORD *)(v72 + 560) || (v73 = 0, !*(_QWORD *)(v72 + 56)) )
          v73 = 1;
        v74 = CopilotWorkbookProxy::GetDocumentIdentity(v2);
        if ( Copilot::FCopilotAutoOpenEnabled(v75) )
        {
          LOBYTE(v76) = v73;
          if ( Mso::Copilot::IsCopilotAutoOpenAllowedForIdentity(v74, v76, v78) )
            v3 = 1;
        }
        v79 = *((_DWORD *)v2 + 20) & 0x220F;
        v80 = 4101;
        if ( (v79 <= 0xC && _bittest(&v80, v79) || CopilotWorkbookProxy::FAugLoopEnabledForLocalFiles(v2))
          && v3
          && !*((_DWORD *)v2 + 23) )
        {
          v81 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2336LL));
          v103 = (const char *)v2;
          Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)&v104, v81);
          v83 = Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, v82);
          v84 = v83;
          if ( !v83 )
          {
            CrashWithRecoveryOnOOM(0x131F462u);
            __debugbreak();
          }
          v83[2] = 1;
          *(_QWORD *)v83 = off_1437F5098;
          *((_QWORD *)v83 + 2) = v103;
          Mso::CancellationToken::CancellationToken(v83 + 6, &v104);
          v101 = v84;
          v86 = Threading::PMainThreadIdleQueue(v85);
          Mso::Async::PostIdle(v86, &v101);
          v87 = v101;
          if ( v101 )
          {
            v101 = 0;
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v87 + 16LL))(v87);
          }
          v77 = v104;
          if ( v104 )
          {
            v104 = 0;
            (*(void (__fastcall **)(Copilot::Internal *))(*(_QWORD *)v77 + 16LL))(v77);
          }
        }
        if ( byte_1440914F8[0] < 0 )
          v88 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_1440914F8);
        else
          v88 = byte_1440914F8[0] != 0;
        if ( !v88 )
          goto LABEL_186;
        v89 = byte_144091508[0] < 0
            ? Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)byte_144091508)
            : byte_144091508[0] != 0;
        if ( !v89 || v3 )
          goto LABEL_186;
        v90 = *((_DWORD *)v2 + 20) & 0x220F;
        if ( (v90 > 0xC || !_bittest(&v80, v90)) && !CopilotWorkbookProxy::FAugLoopEnabledForLocalFiles(v2) )
          goto LABEL_186;
        if ( *((_DWORD *)v2 + 23)
          || Copilot::Internal::FEnableCatalystChecks(v77)
          && !(unsigned __int8)Copilot::Internal::IsChatExperienceEnabledForWorkbook(*((_QWORD *)v2 + 15), 2) )
        {
          goto LABEL_186;
        }
        v91 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2336LL));
        v103 = (const char *)v2;
        Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)&v104, v91);
        v93 = Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, v92);
        v66 = v93;
        if ( !v93 )
        {
          CrashWithRecoveryOnOOM(0x131F462u);
          __debugbreak();
        }
        v93[2] = 1;
        *(_QWORD *)v93 = off_1437F5048;
        *((_QWORD *)v93 + 2) = v103;
        Mso::CancellationToken::CancellationToken(v93 + 6, &v104);
      }
      v101 = v66;
      v68 = Threading::PMainThreadIdleQueue(v67);
      Mso::Async::PostIdle(v68, &v101);
      v69 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v70 = v104;
      if ( v104 )
      {
        v104 = 0;
        (*(void (__fastcall **)(Copilot::Internal *))(*(_QWORD *)v70 + 16LL))(v70);
      }
      goto LABEL_186;
    }
    if ( dword_1441956E8 <= *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 16LL) )
    {
LABEL_113:
      if ( !*((_BYTE *)v2 + 86) )
      {
        *((_BYTE *)v2 + 86) = 1;
        v42 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2336LL));
        v103 = (const char *)v2;
        Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)&v104, v42);
        v44 = Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, v43);
        v45 = v44;
        if ( !v44 )
        {
          CrashWithRecoveryOnOOM(0x131F462u);
          __debugbreak();
        }
        v44[2] = 1;
        *(_QWORD *)v44 = off_1437F4FA8;
        *((_QWORD *)v44 + 2) = v103;
        Mso::CancellationToken::CancellationToken(v44 + 6, &v104);
        v101 = v45;
        v47 = FastModel::UseCurrentThread(v46);
        if ( !v47 )
        {
          CrashWithRecovery(0x12183A2u, 0);
          __debugbreak();
        }
        v48 = (Mso::Async::Details *)(*(__int64 (__fastcall **)(struct FastModel::Thread *))(*(_QWORD *)v47 + 40LL))(v47);
        v50 = Mso::Async::Details::AsIdle(v48, v49);
        if ( byte_1441956F2 )
          v51 = (unsigned int *)&unk_144195750;
        else
          v51 = (unsigned int *)Mso::AB::Optimized::Setting<int>::Evaluate(&unk_1441956F0);
        v52 = *v51;
        v53 = Mso::Async::GetDispatchQueue<Mso::Async::IDispatchQueue>(v50);
        Mso::Async::Details::PostTimer(0, 0, v52, v53, &v101);
        v54 = v101;
        if ( v101 )
        {
          v101 = 0;
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v54 + 16LL))(v54);
        }
        v55 = v104;
        if ( v104 )
        {
          v104 = 0;
          (*(void (__fastcall **)(Copilot::Internal *))(*(_QWORD *)v55 + 16LL))(v55);
        }
      }
      goto LABEL_125;
    }
LABEL_204:
    Init_thread_header(&dword_1441956E8);
    if ( dword_1441956E8 == -1 )
    {
      LODWORD(v101) = 30000;
      v103 = "PreloadCopilotChatDelayTime";
      LOBYTE(v102) = 22;
      Mso::AB::Optimized::Setting<int>::Setting<int>(&unk_1441956F0, &v102, &v103, &v101);
      Init_thread_footer(&dword_1441956E8);
    }
    goto LABEL_113;
  }
}

```

## disassembly

```asm
0x141107190  mov     [rsp-8+arg_8], rbx
0x141107195  mov     [rsp-8+arg_10], rsi
0x14110719a  push    rbp
0x14110719b  push    rdi
0x14110719c  push    r12
0x14110719e  push    r13
0x1411071a0  push    r14
0x1411071a2  lea     rbp, [rsp-40h]
0x1411071a7  sub     rsp, 140h
0x1411071ae  mov     rax, cs:__security_cookie
0x1411071b5  xor     rax, rsp
0x1411071b8  mov     [rbp+60h+var_30], rax
0x1411071bc  mov     rdi, rcx
0x1411071bf  mov     al, cs:byte_1440AA2A8
0x1411071c5  xor     r12d, r12d
0x1411071c8  test    al, al
0x1411071ca  js      short loc_1411071D1
0x1411071cc  setnz   al
0x1411071cf  jmp     short loc_1411071DE
0x1411071d1  lea     rcx, byte_1440AA2A8
0x1411071d8  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1411071de  xchg    ax, ax
0x1411071e0  test    al, al
0x1411071e2  jz      short loc_141107248
0x1411071e4  mov     rcx, rdi; this
0x1411071e7  call    ?GetDocumentIdentity@CopilotWorkbookProxy@@QEBAPEBUIOfficeIdentity@Authentication@Mso@@XZ; CopilotWorkbookProxy::GetDocumentIdentity(void)
0x1411071ec  mov     rbx, rax
0x1411071ef  mov     rcx, rdi; this
0x1411071f2  call    ?RefreshDocumentIdentity@CopilotWorkbookProxy@@AEAAXXZ; CopilotWorkbookProxy::RefreshDocumentIdentity(void)
0x1411071f7  mov     rcx, rdi; this
0x1411071fa  call    ?GetDocumentIdentity@CopilotWorkbookProxy@@QEBAPEBUIOfficeIdentity@Authentication@Mso@@XZ; CopilotWorkbookProxy::GetDocumentIdentity(void)
0x1411071ff  nop
0x141107200  cmp     rbx, rax
0x141107203  jz      short loc_141107248
0x141107205  mov     rcx, rdi; this
0x141107208  call    ?HrCloseTaskPane@CopilotWorkbookProxy@@QEAAJXZ; CopilotWorkbookProxy::HrCloseTaskPane(void)
0x14110720d  mov     rcx, [rdi+18h]
0x141107212  test    rcx, rcx
0x141107215  jz      short loc_141107248
0x141107217  mov     [rdi+18h], r12
0x14110721b  mov     rax, [rcx]
0x14110721e  mov     rax, [rax+10h]
0x141107222  call    cs:__guard_dispatch_icall_fptr
0x141107228  mov     rdx, rax
0x14110722b  or      ecx, 0FFFFFFFFh
0x14110722e  lock xadd [rax+8], ecx
0x141107233  cmp     ecx, 1
0x141107236  jnz     short loc_141107248
0x141107238  mov     rcx, [rax]
0x14110723b  mov     rax, [rcx+8]
0x14110723f  mov     rcx, rdx
0x141107242  call    cs:__guard_dispatch_icall_fptr
0x141107248  mov     esi, r12d
0x14110724b  mov     al, cs:byte_1440AA298
0x141107251  test    al, al
0x141107253  js      short loc_14110725A
0x141107255  setnz   al
0x141107258  jmp     short loc_141107267
0x14110725a  lea     rcx, byte_1440AA298
0x141107261  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x141107267  test    al, al
0x141107269  jz      short loc_14110727D
0x14110726b  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x141107270  test    al, al
0x141107272  jz      short loc_14110727D
0x141107274  lea     r14, [rdi+78h]
0x141107278  mov     rcx, [r14]
0x14110727b  jmp     short loc_1411072A7
0x14110727d  lea     rbx, [rdi+78h]
0x141107281  mov     r14, rbx
0x141107284  mov     rcx, [rbx]; this
0x141107287  call    ?FCopilotLicenseEnabledForTenant@Internal@Copilot@@YA_NPEBVWorkbook@Api@@@Z; Copilot::Internal::FCopilotLicenseEnabledForTenant(Api::Workbook const *)
0x14110728c  test    al, al
0x14110728e  jnz     short loc_1411072B7
0x141107290  call    ?FCopilotStarterLicenseEnabled@Internal@Copilot@@YA_NXZ; Copilot::Internal::FCopilotStarterLicenseEnabled(void)
0x141107295  test    al, al
0x141107297  jnz     short loc_1411072B7
0x141107299  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x14110729e  xchg    ax, ax
0x1411072a0  test    al, al
0x1411072a2  jz      short loc_1411072B2
0x1411072a4  mov     rcx, [rbx]
0x1411072a7  xor     edx, edx
0x1411072a9  call    ?IsChatExperienceEnabledForWorkbook@Internal@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@@Z; Copilot::Internal::IsChatExperienceEnabledForWorkbook(Api::Workbook const *,CopilotToolkit::CopilotChatExperience)
0x1411072ae  test    al, al
0x1411072b0  jnz     short loc_1411072B7
0x1411072b2  mov     esi, 8000h
0x1411072b7  mov     rbx, [r14]
0x1411072ba  mov     al, cs:byte_144091D08
0x1411072c0  test    al, al
0x1411072c2  js      short loc_1411072C9
0x1411072c4  setnz   al
0x1411072c7  jmp     short loc_1411072D6
0x1411072c9  lea     rcx, byte_144091D08
0x1411072d0  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1411072d6  mov     r13d, 4
0x1411072e0  test    al, al
0x1411072e2  jz      short loc_1411072E9
0x1411072e4  mov     ebx, r12d
0x1411072e7  jmp     short loc_141107336
0x1411072e9  mov     rcx, rbx
0x1411072ec  call    ?CheckAugmentationLoopPrerequisitesMet@AugmentationLoopSessionImpl@AugmentationLoop@@SA?AW4AugmentationLoopPrerequisitesMet@@AEBVWorkbook@Api@@@Z; AugmentationLoop::AugmentationLoopSessionImpl::CheckAugmentationLoopPrerequisitesMet(Api::Workbook const &)
0x1411072f1  mov     ebx, eax
0x1411072f3  and     ebx, 1
0x1411072f6  add     ebx, ebx
0x1411072f8  test    al, 2
0x1411072fa  jz      short loc_1411072FF
0x1411072fc  or      ebx, r13d
0x1411072ff  nop
0x141107300  test    r13b, al
0x141107303  jz      short loc_141107308
0x141107305  or      ebx, 8
0x141107308  test    al, 8
0x14110730a  jz      short loc_141107310
0x14110730c  bts     ebx, 0Ch
0x141107310  test    al, 20h
0x141107312  jz      short loc_141107317
0x141107314  or      ebx, 10h
0x141107317  test    al, 10h
0x141107319  jz      short loc_14110731F
0x14110731b  bts     ebx, 0Dh
0x14110731f  nop
0x141107320  test    eax, 0FFFFFFC0h
0x141107325  jz      short loc_141107336
0x141107327  bts     ebx, 9
0x14110732b  mov     ecx, 1E2922C5h
0x141107330  call    cs:__imp_MsoShipAssertTagProc
0x141107336  or      esi, ebx
0x141107339  cmp     cs:byte_14418F75A, r12b
0x141107340  jz      short loc_14110735D
0x141107342  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x141107347  test    al, al
0x141107349  jz      short loc_141107359
0x14110734b  xor     edx, edx
0x14110734d  mov     rcx, [r14]
0x141107350  call    ?IsChatExperienceEnabledForWorkbook@Internal@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@@Z; Copilot::Internal::IsChatExperienceEnabledForWorkbook(Api::Workbook const *,CopilotToolkit::CopilotChatExperience)
0x141107355  test    al, al
0x141107357  jnz     short loc_14110735D
0x141107359  bts     esi, 7
0x14110735d  mov     al, cs:byte_1440916E8
0x141107363  test    al, al
0x141107365  js      short loc_14110736C
0x141107367  setnz   al
0x14110736a  jmp     short loc_141107379
0x14110736c  lea     rcx, byte_1440916E8
0x141107373  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x141107379  mov     ebx, 400h
0x141107380  test    al, al
0x141107382  jz      short loc_1411073E2
0x141107384  mov     al, cs:byte_1440AA288
0x14110738a  test    al, al
0x14110738c  js      short loc_141107393
0x14110738e  setnz   al
0x141107391  jmp     short loc_1411073A6
0x141107393  lea     rcx, byte_1440AA288
0x1411073a0  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1411073a6  test    al, al
0x1411073a8  jz      short loc_1411073CA
0x1411073aa  mov     al, cs:byte_14401EE10
0x1411073b0  test    al, al
0x1411073b2  js      short loc_1411073B9
0x1411073b4  setnz   al
0x1411073b7  jmp     short loc_1411073C6
0x1411073b9  lea     rcx, byte_14401EE10
0x1411073c0  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1411073c6  test    al, al
0x1411073c8  jnz     short loc_1411073D3
0x1411073ca  call    ?FEnabled@Copilot@@YA_NXZ; Copilot::FEnabled(void)
0x1411073cf  test    al, al
0x1411073d1  jz      short loc_1411073FF
0x1411073d3  mov     rcx, [r14]
0x1411073d6  call    ?GetCopilotVisibilityState@Internal@Copilot@@YA?AW4CopilotVisibilityState@@PEBVWorkbook@Api@@@Z; Copilot::Internal::GetCopilotVisibilityState(Api::Workbook const *)
0x1411073db  test    ebx, eax
0x1411073dd  jz      short loc_141107403
0x1411073df  nop
0x1411073e0  jmp     short loc_1411073FF
0x1411073e2  xor     r8d, r8d
0x1411073e5  xor     edx, edx
0x1411073e7  mov     rcx, [r14]
0x1411073ea  call    ?FCopilotButtonVisible@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@W4CopilotEntryPoint@1@@Z; Copilot::FCopilotButtonVisible(Api::Workbook const *,CopilotToolkit::CopilotChatExperience,Copilot::CopilotEntryPoint)
0x1411073ef  test    al, al
0x1411073f1  jnz     short loc_141107403
0x1411073f3  mov     rcx, [r14]; this
0x1411073f6  call    ?FCopilotDABVisible@Copilot@@YA_NPEBVWorkbook@Api@@@Z; Copilot::FCopilotDABVisible(Api::Workbook const *)
0x1411073fb  test    al, al
0x1411073fd  jnz     short loc_141107403
0x1411073ff  bts     esi, 8
0x141107403  call    ?FSupportedLocales@Copilot@@YA_NXZ; Copilot::FSupportedLocales(void)
0x141107408  mov     r14d, esi
0x14110740b  or      r14d, 40h
0x14110740f  test    al, al
0x141107411  cmovnz  r14d, esi
0x141107415  mov     rax, [rdi+18h]
0x141107419  test    rax, rax
0x14110741c  jz      short loc_141107433
0x14110741e  mov     rax, [rax+8]
0x141107422  test    rax, rax
0x141107425  jz      short loc_141107433
0x141107427  mov     al, [rax+72h]
0x14110742a  test    al, al
0x14110742c  jz      short loc_141107433
0x14110742e  or      r14d, ebx
0x141107431  jmp     short loc_141107450
0x141107433  mov     rax, [rdi+18h]
0x141107437  test    rax, rax
0x14110743a  jz      short loc_14110744C
0x14110743c  nop     dword ptr [rax+00h]
0x141107440  cmp     [rax+8], r12
0x141107444  jz      short loc_14110744C
0x141107446  cmp     [rax+18h], r12b
0x14110744a  jnz     short loc_141107450
0x14110744c  or      r14d, 20h
0x141107450  mov     rax, [rdi+78h]
0x141107454  test    rax, rax
0x141107457  jz      loc_141107D74
0x14110745d  mov     rcx, [rax+18h]; this
0x141107461  test    rcx, rcx
0x141107464  jz      loc_141107D74
0x14110746a  call    ?Pioldoc@BOOK@@QEBAPEAUIMsoOLDocument@@XZ; BOOK::Pioldoc(void)
0x14110746f  mov     rdx, rax
0x141107472  test    rax, rax
0x141107475  jnz     short loc_14110747C
0x141107477  mov     al, r12b
0x14110747a  jmp     short loc_141107498
0x14110747c  mov     rcx, cs:qword_144089870
0x141107483  mov     rax, [rcx]
0x141107486  mov     rax, [rax+360h]
0x14110748d  call    cs:__guard_dispatch_icall_fptr
0x141107493  cmp     al, 2
0x141107495  setb    al
0x141107498  test    al, al
0x14110749a  jnz     short loc_1411074A1
0x14110749c  bts     r14d, 0Bh
0x1411074a1  mov     r13d, [rdi+50h]
0x1411074a6  cmp     r14d, r13d
0x1411074a9  jz      loc_141107D4C
0x1411074af  mov     [rdi+50h], r14d
0x1411074b3  mov     rcx, [rdi+78h]
0x1411074b7  lea     rax, [rcx+98h]
0x1411074be  neg     rcx
0x1411074c1  sbb     rcx, rcx
0x1411074c4  and     rcx, rax
0x1411074c7  mov     rax, [rcx]
0x1411074ca  mov     rax, [rax]
0x1411074cd  call    cs:__guard_dispatch_icall_fptr
0x1411074d3  lea     rcx, ??_7?$DataField@PEB_W@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<wchar_t const *>::`vftable'
0x1411074da  mov     [rbp+60h+var_90], rcx
0x1411074de  mov     [rbp+60h+var_40], rax
0x1411074e2  mov     esi, 4
0x1411074e7  mov     [rbp+60h+var_38], si
0x1411074eb  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1411074ef  lea     r8, aWorkbookid_0; "WorkbookId"
0x1411074f6  lea     ebx, [rsi+3Dh]
0x1411074f9  mov     edx, ebx; SizeInBytes
0x1411074fb  lea     rcx, [rbp+60h+Destination]; Destination
0x1411074ff  nop
0x141107500  call    cs:__imp_strncpy_s
0x141107506  lea     rax, ??_7?$DataField@H@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<int>::`vftable'
0x14110750d  mov     [rsp+160h+var_F0], rax
0x141107512  mov     [rbp+60h+var_A4], r14d
0x141107516  mov     [rbp+60h+var_A0], si
0x14110751a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14110751e  lea     r8, aState_0; "State"
0x141107525  mov     edx, ebx; SizeInBytes
0x141107527  lea     rcx, [rsp+160h+var_E8]; Destination
0x14110752c  call    cs:__imp_strncpy_s
0x141107532  mov     [rsp+51h], r12b
0x14110753a  lea     eax, [rsi-2]
0x14110753d  mov     word ptr [rsp+160h+var_130], ax
0x141107542  mov     byte ptr [rsp+160h+var_130+2], 1
0x141107547  mov     [rsp+160h+var_10D], r12b
0x14110754c  mov     [rsp+160h+var_10B], r12b
0x141107551  mov     [rsp+160h+var_128], 101h
0x141107558  lea     rax, [rsp+160h+var_110]
0x14110755d  mov     [rsp+160h+var_138], rax
0x141107562  lea     rax, [rsp+160h+var_130]
0x141107567  mov     [rsp+160h+var_140], rax
0x14110756c  lea     r9, [rsp+160h+var_10E]
0x141107571  lea     r8, [rsp+160h+var_10C]
0x141107576  lea     rdx, [rsp+160h+var_128]
0x14110757b  lea     rcx, [rsp+160h+var_120]
0x141107580  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x141107586  lea     rax, off_14383B630
0x14110758d  mov     [rsp+160h+var_108], rax
0x141107592  lea     rax, aCopilotenabled_2; "CopilotEnabledState"
0x141107599  mov     [rsp+160h+var_100], rax
0x14110759e  lea     r9, [rbp+60h+var_90]
0x1411075a2  lea     r8, [rsp+160h+var_F0]
0x1411075a7  lea     rdx, [rsp+160h+var_120]
0x1411075ac  lea     rcx, [rsp+160h+var_108]
0x1411075b1  call    ??$SendTelemetryEvent@U?$DataField@E@Telemetry@Mso@@U?$DataField@PEB_W@23@@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@$$QEAU?$DataField@E@01@$$QEAU?$DataField@PEB_W@01@@Z; Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<uchar>,Mso::Telemetry::DataField<wchar_t const *>>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Mso::Telemetry::DataField<uchar> &&,Mso::Telemetry::DataField<wchar_t const *> &&)
0x1411075b6  mov     al, byte_1440AA228
0x1411075c0  test    al, al
0x1411075c2  js      short loc_1411075C9
0x1411075c4  setnz   al
0x1411075c7  jmp     short loc_1411075D6
0x1411075c9  lea     rcx, byte_1440AA228
0x1411075d0  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1411075d6  test    al, al
0x1411075d8  jz      short loc_14110761F
  ... truncated ...
```
