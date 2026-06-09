# CopilotWorkbookProxy::UpdateCopilotEnabledState(void)

- ea: `0x141907840`
- end: `0x14190848c`
- name: `?UpdateCopilotEnabledState@CopilotWorkbookProxy@@QEAAXXZ`
- size: `3148`
- prototype: `void __fastcall(CopilotWorkbookProxy *__hidden this)`
- caller_count: `7`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x141304710`
- `0x1414dca40`
- `0x142ac4d70`
- `0x14343e220`
- `0x143461f60`
- `0x14346e020`
- `0x14346e6b0`

## callees

- `0x14004d2e0`
- `0x140056584`
- `0x1400565f0`
- `0x1400b33fc`
- `0x1400df4b0`
- `0x1400e6bf0`
- `0x1400e8650`
- `0x14016f100`
- `0x1401e2ab0`
- `0x140200c80`
- `0x140212d30`
- `0x14021b4e0`
- `0x14023fd80`
- `0x140258780`
- `0x140270d10`
- `0x140486500`
- `0x14054f560`
- `0x1408cc4b0`
- `0x1408cfe50`
- `0x140cf0f50`
- `0x141059800`
- `0x14105fe10`
- `0x1412e1a30`
- `0x14140d4a0`
- `0x1416dc510`
- `0x141906630`
- `0x141907840`
- `0x1433e2b00`
- `0x1434342d0`
- `0x14346ca80`
- `0x14346ef00`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141907bb9`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141907be5`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141907bb9`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x141907be5`
- `MSO!__imp_?IsCopilotDABUnboxingEnabled@CopilotToolkit@@YA_NXZ` at `0x141907f2e`
- `MSO!__imp_?IsCopilotDABUnboxingEnabled@CopilotToolkit@@YA_NXZ` at `0x141907f2e`
- `Mso98Win32Client!__imp_?IncrementDABUnboxingQualifyingCount@DABUnboxing@Copilot@Mso@@YA_NXZ` at `0x141907f60`
- `Mso98Win32Client!__imp_?IncrementDABUnboxingQualifyingCount@DABUnboxing@Copilot@Mso@@YA_NXZ` at `0x141907f60`
- `Mso98Win32Client!__imp_?IsCopilotAutoOpenAllowedForIdentity@Copilot@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@_N@Z` at `0x14190810e`
- `Mso98Win32Client!__imp_?IsCopilotAutoOpenAllowedForIdentity@Copilot@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@_N@Z` at `0x14190810e`
- `Mso30Win32Client!__imp_?IsAppGuard@Config@AppGuard@@YA_NXZ` at `0x141908374`
- `Mso30Win32Client!__imp_?IsAppGuard@Config@AppGuard@@YA_NXZ` at `0x141908374`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x141907e8c`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x141907e8c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1419079e7`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1419079e7`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907889`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907910`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a55`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a75`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907c82`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907cf0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907da9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907f84`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907889`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907910`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a55`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a75`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907c82`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907cf0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907da9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907f84`
- `Mso20Win32Client!__imp_?UseCurrentThread@FastModel@@YAAEAVThread@1@XZ` at `0x141907e60`
- `Mso20Win32Client!__imp_?UseCurrentThread@FastModel@@YAAEAVThread@1@XZ` at `0x141907e60`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141907e75`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141908420`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141907e75`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141908420`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x141908079`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x1419081e0`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x141908079`
- `Mso20Win32Client!__imp_?PostIdle@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x1419081e0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141907e2b`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908033`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908198`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908313`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141907e2b`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908033`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908198`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141908313`
- `Mso20Win32Client!__imp_?Evaluate@?$Setting@H@Optimized@AB@Mso@@AEBAAEBHXZ` at `0x141907eaf`
- `Mso20Win32Client!__imp_?Evaluate@?$Setting@H@Optimized@AB@Mso@@AEBAAEBHXZ` at `0x141907eaf`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141907c36`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141907c36`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907989`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a30`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907d22`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141908240`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141908264`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1419083c0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907989`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907a30`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141907d22`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141908240`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141908264`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1419083c0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141907e0c`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141908013`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141908179`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x1419082f4`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141907e0c`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141908013`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x141908179`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x1419082f4`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141907e55`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141908060`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1419081c2`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141908340`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141907e55`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141908060`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x1419081c2`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@$$QEAV01@@Z` at `0x141908340`
- `Mso20Win32Client!__imp_?PostTimer@Details@Async@Mso@@YAXPEAV?$TCntPtr@UITimerObject@Async@Mso@@@3@_NIPEAVIDispatchQueue@23@$$QEAV?$Functor@$$A6AXXZ@3@@Z` at `0x141907ed9`
- `Mso20Win32Client!__imp_?PostTimer@Details@Async@Mso@@YAXPEAV?$TCntPtr@UITimerObject@Async@Mso@@@3@_NIPEAVIDispatchQueue@23@$$QEAV?$Functor@$$A6AXXZ@3@@Z` at `0x141907ed9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141907e18`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908020`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908185`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908300`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141907e18`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908020`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908185`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141908300`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141907df9`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141908000`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141908166`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x1419082e1`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141907df9`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141908000`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x141908166`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x1419082e1`

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
  __int64 *v51; // rax
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
  if ( byte_144036858 < 0 )
    v4 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_144036858);
  else
    v4 = byte_144036858 != 0;
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
  if ( byte_1440368D8 < 0 )
    v8 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_1440368D8);
  else
    v8 = byte_1440368D8 != 0;
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
  if ( byte_14401E628 < 0 )
    v13 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_14401E628);
  else
    v13 = byte_14401E628 != 0;
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
  if ( byte_14411A880
    && (!Copilot::Internal::FEnableCatalystChecks(v11)
     || !(unsigned __int8)Copilot::Internal::IsChatExperienceEnabledForWorkbook(*v9, 0)) )
  {
    v17 |= 0x80u;
  }
  if ( byte_14401E010 < 0 )
    v18 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_14401E010);
  else
    v18 = byte_14401E010 != 0;
  if ( v18 )
  {
    if ( byte_1440368E8 < 0 )
      v19 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_1440368E8);
    else
      v19 = byte_1440368E8 != 0;
    if ( !v19
      || (byte_143FABA00 < 0
        ? (v20 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_143FABA00))
        : (v20 = byte_143FABA00 != 0),
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
    v30 = (*(unsigned __int8 (__fastcall **)(PolicyTipsStartup *, struct IMsoOLDocument *))(*(_QWORD *)qword_1440164E8
                                                                                          + 864LL))(
            qword_1440164E8,
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
    v108[0] = &off_1437EAD60;
    v108[1] = "CopilotEnabledState";
    Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<unsigned char>,Mso::Telemetry::DataField<wchar_t const *>>(
      v108,
      &v103,
      &v109,
      &v113);
    if ( byte_144036898 < 0 )
      v35 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_144036898);
    else
      v35 = byte_144036898 != 0;
    v36 = 0;
    if ( v35 )
    {
      v33 = 304;
      v34 = *(Copilot::Internal **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL);
      if ( *((_DWORD *)v34 + 20)
        || (vgrbitScanload & 1) != 0
        || *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
        && *(_DWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1376LL) )
      {
        v36 = 1;
      }
    }
    if ( byte_1440368A8 < 0 )
      v37 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_1440368A8);
    else
      v37 = byte_1440368A8 != 0;
    if ( !v37 || (v38 = 1, !*(_BYTE *)(*((_QWORD *)v2 + 15) + 2370LL)) )
      v38 = 0;
    if ( byte_144036710 < 0 )
      v39 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_144036710);
    else
      v39 = byte_144036710 != 0;
    if ( !v39
      || *((_BYTE *)v2 + 85)
      || v23 && (!Copilot::Internal::FEnableCatalystChecks(v34) || (v23 & 0xFFFF4BC0) != 0)
      || *((_QWORD *)v2 + 7)
      || v36
      || v38
      || ((v40 = *((_QWORD *)v2 + 3)) == 0 || !*(_QWORD *)(v40 + 8) || !*(_BYTE *)(v40 + 24))
      && (byte_14401E3D8 < 0
        ? (v41 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_14401E3D8))
        : (v41 = byte_14401E3D8 != 0),
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
      if ( byte_1440368B8 < 0 )
        v59 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_1440368B8);
      else
        v59 = byte_1440368B8 != 0;
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
            if ( byte_14401E068 < 0 )
              v99 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_14401E068);
            else
              v99 = byte_14401E068 != 0;
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
        Token = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2328LL));
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
        *(_QWORD *)v65 = off_143792348;
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
          v81 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2328LL));
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
          *(_QWORD *)v83 = off_143792370;
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
        if ( byte_14401DE60 < 0 )
          v88 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_14401DE60);
        else
          v88 = byte_14401DE60 != 0;
        if ( !v88 )
          goto LABEL_186;
        v89 = byte_14401DE70 < 0
            ? Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_14401DE70)
            : byte_14401DE70 != 0;
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
        v91 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2328LL));
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
        *(_QWORD *)v93 = off_143792398;
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
    if ( dword_144120668 <= *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 16LL) )
    {
LABEL_113:
      if ( !*((_BYTE *)v2 + 86) )
      {
        *((_BYTE *)v2 + 86) = 1;
        v42 = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)(*((_QWORD *)v2 + 15) + 2328LL));
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
        *(_QWORD *)v44 = off_143792320;
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
        if ( byte_144120672 )
          v51 = qword_1441206D0;
        else
          v51 = (__int64 *)Mso::AB::Optimized::Setting<int>::Evaluate(byte_144120670);
        v52 = *(_DWORD *)v51;
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
    Init_thread_header(&dword_144120668);
    if ( dword_144120668 == -1 )
    {
      LODWORD(v101) = 30000;
      v103 = "PreloadCopilotChatDelayTime";
      LOBYTE(v102) = 22;
      Mso::AB::Optimized::Setting<int>::Setting<int>(byte_144120670, &v102, &v103, &v101);
      Init_thread_footer(&dword_144120668);
    }
    goto LABEL_113;
  }
}

```

## disassembly

```asm
0x141907840  mov     [rsp-8+arg_8], rbx
0x141907845  mov     [rsp-8+arg_10], rsi
0x14190784a  push    rbp
0x14190784b  push    rdi
0x14190784c  push    r12
0x14190784e  push    r13
0x141907850  push    r14
0x141907852  lea     rbp, [rsp-40h]
0x141907857  sub     rsp, 140h
0x14190785e  mov     rax, cs:__security_cookie
0x141907865  xor     rax, rsp
0x141907868  mov     [rbp+60h+var_30], rax
0x14190786c  mov     rdi, rcx
0x14190786f  mov     al, cs:byte_144036858
0x141907875  xor     r12d, r12d
0x141907878  test    al, al
0x14190787a  js      short loc_141907882
0x14190787c  setnz   al
0x141907880  jmp     short loc_14190788F
0x141907882  lea     rcx, byte_144036858
0x141907889  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x14190788f  test    al, al
0x141907891  jz      short loc_1419078F6
0x141907893  mov     rcx, rdi; this
0x141907896  call    ?GetDocumentIdentity@CopilotWorkbookProxy@@QEBAPEBUIOfficeIdentity@Authentication@Mso@@XZ; CopilotWorkbookProxy::GetDocumentIdentity(void)
0x14190789b  mov     rbx, rax
0x14190789e  mov     rcx, rdi; this
0x1419078a1  call    ?RefreshDocumentIdentity@CopilotWorkbookProxy@@AEAAXXZ; CopilotWorkbookProxy::RefreshDocumentIdentity(void)
0x1419078a6  mov     rcx, rdi; this
0x1419078a9  call    ?GetDocumentIdentity@CopilotWorkbookProxy@@QEBAPEBUIOfficeIdentity@Authentication@Mso@@XZ; CopilotWorkbookProxy::GetDocumentIdentity(void)
0x1419078ae  cmp     rbx, rax
0x1419078b1  jz      short loc_1419078F6
0x1419078b3  mov     rcx, rdi; this
0x1419078b6  call    ?HrCloseTaskPane@CopilotWorkbookProxy@@QEAAJXZ; CopilotWorkbookProxy::HrCloseTaskPane(void)
0x1419078bb  mov     rcx, [rdi+18h]
0x1419078c0  test    rcx, rcx
0x1419078c3  jz      short loc_1419078F6
0x1419078c5  mov     [rdi+18h], r12
0x1419078c9  mov     rax, [rcx]
0x1419078cc  mov     rax, [rax+10h]
0x1419078d0  call    cs:__guard_dispatch_icall_fptr
0x1419078d6  mov     rdx, rax
0x1419078d9  or      ecx, 0FFFFFFFFh
0x1419078dc  lock xadd [rax+8], ecx
0x1419078e1  cmp     ecx, 1
0x1419078e4  jnz     short loc_1419078F6
0x1419078e6  mov     rcx, [rax]
0x1419078e9  mov     rax, [rcx+8]
0x1419078ed  mov     rcx, rdx
0x1419078f0  call    cs:__guard_dispatch_icall_fptr
0x1419078f6  mov     esi, r12d
0x1419078fa  mov     al, cs:byte_1440368D8
0x141907900  test    al, al
0x141907902  js      short loc_141907909
0x141907904  setnz   al
0x141907907  jmp     short loc_141907916
0x141907909  lea     rcx, byte_1440368D8
0x141907910  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x141907916  test    al, al
0x141907918  jz      short loc_14190792D
0x14190791a  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x14190791f  nop
0x141907920  test    al, al
0x141907922  jz      short loc_14190792D
0x141907924  lea     r14, [rdi+78h]
0x141907928  mov     rcx, [r14]
0x14190792b  jmp     short loc_141907959
0x14190792d  lea     rbx, [rdi+78h]
0x141907931  mov     r14, rbx
0x141907934  mov     rcx, [rbx]; this
0x141907937  call    ?FCopilotLicenseEnabledForTenant@Internal@Copilot@@YA_NPEBVWorkbook@Api@@@Z; Copilot::Internal::FCopilotLicenseEnabledForTenant(Api::Workbook const *)
0x14190793c  nop     dword ptr [rax+00h]
0x141907940  test    al, al
0x141907942  jnz     short loc_14190796E
0x141907944  call    ?FCopilotStarterLicenseEnabled@Internal@Copilot@@YA_NXZ; Copilot::Internal::FCopilotStarterLicenseEnabled(void)
0x141907949  test    al, al
0x14190794b  jnz     short loc_14190796E
0x14190794d  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x141907952  test    al, al
0x141907954  jz      short loc_141907969
0x141907956  mov     rcx, [rbx]
0x141907959  xor     edx, edx
0x141907960  call    ?IsChatExperienceEnabledForWorkbook@Internal@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@@Z; Copilot::Internal::IsChatExperienceEnabledForWorkbook(Api::Workbook const *,CopilotToolkit::CopilotChatExperience)
0x141907965  test    al, al
0x141907967  jnz     short loc_14190796E
0x141907969  mov     esi, 8000h
0x14190796e  mov     rbx, [r14]
0x141907971  mov     al, cs:byte_14401E628
0x141907977  test    al, al
0x141907979  js      short loc_141907982
0x14190797b  setnz   al
0x141907980  jmp     short loc_14190798F
0x141907982  lea     rcx, byte_14401E628
0x141907989  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x14190798f  mov     r13d, 4
0x141907995  test    al, al
0x141907997  jz      short loc_14190799E
0x141907999  mov     ebx, r12d
0x14190799c  jmp     short loc_1419079ED
0x14190799e  mov     rcx, rbx
0x1419079a1  call    ?CheckAugmentationLoopPrerequisitesMet@AugmentationLoopSessionImpl@AugmentationLoop@@SA?AW4AugmentationLoopPrerequisitesMet@@AEBVWorkbook@Api@@@Z; AugmentationLoop::AugmentationLoopSessionImpl::CheckAugmentationLoopPrerequisitesMet(Api::Workbook const &)
0x1419079a6  mov     ebx, eax
0x1419079a8  and     ebx, 1
0x1419079ab  add     ebx, ebx
0x1419079ad  test    al, 2
0x1419079af  jz      short loc_1419079B4
0x1419079b1  or      ebx, r13d
0x1419079b4  test    r13b, al
0x1419079b7  jz      short loc_1419079BC
0x1419079b9  or      ebx, 8
0x1419079bc  nop     dword ptr [rax+00h]
0x1419079c0  test    al, 8
0x1419079c2  jz      short loc_1419079C8
0x1419079c4  bts     ebx, 0Ch
0x1419079c8  test    al, 20h
0x1419079ca  jz      short loc_1419079CF
0x1419079cc  or      ebx, 10h
0x1419079cf  test    al, 10h
0x1419079d1  jz      short loc_1419079D7
0x1419079d3  bts     ebx, 0Dh
0x1419079d7  test    eax, 0FFFFFFC0h
0x1419079dc  jz      short loc_1419079ED
0x1419079de  bts     ebx, 9
0x1419079e2  mov     ecx, 1E2922C5h
0x1419079e7  call    cs:__imp_MsoShipAssertTagProc
0x1419079ed  or      esi, ebx
0x1419079ef  cmp     cs:byte_14411A880, r12b
0x1419079f6  jz      short loc_141907A16
0x1419079f8  call    ?FEnableCatalystChecks@Internal@Copilot@@YA_NXZ; Copilot::Internal::FEnableCatalystChecks(void)
0x1419079fd  nop     dword ptr [rax]
0x141907a00  test    al, al
0x141907a02  jz      short loc_141907A12
0x141907a04  xor     edx, edx
0x141907a06  mov     rcx, [r14]
0x141907a09  call    ?IsChatExperienceEnabledForWorkbook@Internal@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@@Z; Copilot::Internal::IsChatExperienceEnabledForWorkbook(Api::Workbook const *,CopilotToolkit::CopilotChatExperience)
0x141907a0e  test    al, al
0x141907a10  jnz     short loc_141907A16
0x141907a12  bts     esi, 7
0x141907a16  mov     al, byte_14401E010
0x141907a20  test    al, al
0x141907a22  js      short loc_141907A29
0x141907a24  setnz   al
0x141907a27  jmp     short loc_141907A36
0x141907a29  lea     rcx, byte_14401E010
0x141907a30  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x141907a36  mov     ebx, 400h
0x141907a3b  test    al, al
0x141907a3d  jz      short loc_141907A97
0x141907a3f  mov     al, cs:byte_1440368E8
0x141907a45  test    al, al
0x141907a47  js      short loc_141907A4E
0x141907a49  setnz   al
0x141907a4c  jmp     short loc_141907A5B
0x141907a4e  lea     rcx, byte_1440368E8
0x141907a55  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x141907a5b  test    al, al
0x141907a5d  jz      short loc_141907A7F
0x141907a5f  mov     al, cs:byte_143FABA00
0x141907a65  test    al, al
0x141907a67  js      short loc_141907A6E
0x141907a69  setnz   al
0x141907a6c  jmp     short loc_141907A7B
0x141907a6e  lea     rcx, byte_143FABA00
0x141907a75  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x141907a7b  test    al, al
0x141907a7d  jnz     short loc_141907A89
0x141907a7f  nop
0x141907a80  call    ?FEnabled@Copilot@@YA_NXZ; Copilot::FEnabled(void)
0x141907a85  test    al, al
0x141907a87  jz      short loc_141907AB5
0x141907a89  mov     rcx, [r14]
0x141907a8c  call    ?GetCopilotVisibilityState@Internal@Copilot@@YA?AW4CopilotVisibilityState@@PEBVWorkbook@Api@@@Z; Copilot::Internal::GetCopilotVisibilityState(Api::Workbook const *)
0x141907a91  test    ebx, eax
0x141907a93  jz      short loc_141907AB9
0x141907a95  jmp     short loc_141907AB5
0x141907a97  xor     r8d, r8d
0x141907a9b  xor     edx, edx
0x141907a9d  mov     rcx, [r14]
0x141907aa0  call    ?FCopilotButtonVisible@Copilot@@YA_NPEBVWorkbook@Api@@W4CopilotChatExperience@CopilotToolkit@@W4CopilotEntryPoint@1@@Z; Copilot::FCopilotButtonVisible(Api::Workbook const *,CopilotToolkit::CopilotChatExperience,Copilot::CopilotEntryPoint)
0x141907aa5  test    al, al
0x141907aa7  jnz     short loc_141907AB9
0x141907aa9  mov     rcx, [r14]; this
0x141907aac  call    ?FCopilotDABVisible@Copilot@@YA_NPEBVWorkbook@Api@@@Z; Copilot::FCopilotDABVisible(Api::Workbook const *)
0x141907ab1  test    al, al
0x141907ab3  jnz     short loc_141907AB9
0x141907ab5  bts     esi, 8
0x141907ab9  call    ?FSupportedLocales@Copilot@@YA_NXZ; Copilot::FSupportedLocales(void)
0x141907abe  mov     r14d, esi
0x141907ac1  or      r14d, 40h
0x141907ac5  test    al, al
0x141907ac7  cmovnz  r14d, esi
0x141907acb  mov     rax, [rdi+18h]
0x141907acf  test    rax, rax
0x141907ad2  jz      short loc_141907AE9
0x141907ad4  mov     rax, [rax+8]
0x141907ad8  test    rax, rax
0x141907adb  jz      short loc_141907AE9
0x141907add  mov     al, [rax+72h]
0x141907ae0  test    al, al
0x141907ae2  jz      short loc_141907AE9
0x141907ae4  or      r14d, ebx
0x141907ae7  jmp     short loc_141907B02
0x141907ae9  mov     rax, [rdi+18h]
0x141907aed  test    rax, rax
0x141907af0  jz      short loc_141907AFE
0x141907af2  cmp     [rax+8], r12
0x141907af6  jz      short loc_141907AFE
0x141907af8  cmp     [rax+18h], r12b
0x141907afc  jnz     short loc_141907B02
0x141907afe  or      r14d, 20h
0x141907b02  mov     rax, [rdi+78h]
0x141907b06  test    rax, rax
0x141907b09  jz      loc_141908414
0x141907b0f  mov     rcx, [rax+18h]; this
0x141907b13  test    rcx, rcx
0x141907b16  jz      loc_141908414
0x141907b1c  nop     dword ptr [rax+00h]
0x141907b20  call    ?Pioldoc@BOOK@@QEBAPEAUIMsoOLDocument@@XZ; BOOK::Pioldoc(void)
0x141907b25  mov     rdx, rax
0x141907b28  test    rax, rax
0x141907b2b  jnz     short loc_141907B32
0x141907b2d  mov     al, r12b
0x141907b30  jmp     short loc_141907B4E
0x141907b32  mov     rcx, cs:qword_1440164E8
0x141907b39  mov     rax, [rcx]
0x141907b3c  mov     rax, [rax+360h]
0x141907b43  call    cs:__guard_dispatch_icall_fptr
0x141907b49  cmp     al, 2
0x141907b4b  setb    al
0x141907b4e  test    al, al
0x141907b50  jnz     short loc_141907B57
0x141907b52  bts     r14d, 0Bh
0x141907b57  mov     r13d, [rdi+50h]
0x141907b60  cmp     r14d, r13d
0x141907b63  jz      loc_1419083EC
0x141907b69  mov     [rdi+50h], r14d
0x141907b6d  mov     rcx, [rdi+78h]
0x141907b71  lea     rax, [rcx+98h]
0x141907b78  neg     rcx
0x141907b7b  sbb     rcx, rcx
0x141907b7e  and     rcx, rax
0x141907b81  mov     rax, [rcx]
0x141907b84  mov     rax, [rax]
0x141907b87  call    cs:__guard_dispatch_icall_fptr
0x141907b8d  lea     rcx, ??_7?$DataField@PEB_W@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<wchar_t const *>::`vftable'
0x141907b94  mov     [rbp+60h+var_90], rcx
0x141907b98  mov     [rbp+60h+var_40], rax
0x141907b9c  mov     esi, 4
0x141907ba1  mov     [rbp+60h+var_38], si
0x141907ba5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x141907ba9  lea     r8, aWorkbookid_0; "WorkbookId"
0x141907bb0  lea     ebx, [rsi+3Dh]
0x141907bb3  mov     edx, ebx; SizeInBytes
0x141907bb5  lea     rcx, [rbp+60h+Destination]; Destination
0x141907bb9  call    cs:__imp_strncpy_s
0x141907bbf  lea     rax, ??_7?$DataField@H@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<int>::`vftable'
0x141907bc6  mov     [rsp+160h+var_F0], rax
0x141907bcb  mov     [rbp+60h+var_A4], r14d
0x141907bcf  mov     [rbp+60h+var_A0], si
0x141907bd3  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x141907bd7  lea     r8, aState_0; "State"
0x141907bde  mov     edx, ebx; SizeInBytes
0x141907be0  lea     rcx, [rsp+160h+var_E8]; Destination
0x141907be5  call    cs:__imp_strncpy_s
0x141907beb  mov     [rsp+160h+var_10F], r12b
0x141907bf0  lea     eax, [rsi-2]
0x141907bf3  mov     word ptr [rsp+160h+var_130], ax
0x141907bf8  mov     byte ptr [rsp+160h+var_130+2], 1
0x141907bfd  mov     [rsp+160h+var_10D], r12b
0x141907c02  mov     [rsp+160h+var_10B], r12b
0x141907c07  mov     [rsp+160h+var_128], 101h
0x141907c0e  lea     rax, [rsp+160h+var_110]
0x141907c13  mov     [rsp+160h+var_138], rax
0x141907c18  lea     rax, [rsp+160h+var_130]
0x141907c1d  mov     [rsp+160h+var_140], rax
0x141907c22  lea     r9, [rsp+160h+var_10E]
0x141907c27  lea     r8, [rsp+160h+var_10C]
0x141907c2c  lea     rdx, [rsp+160h+var_128]
0x141907c31  lea     rcx, [rsp+160h+var_120]
0x141907c36  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x141907c3c  lea     rax, off_1437EAD60
0x141907c43  mov     [rsp+160h+var_108], rax
0x141907c48  lea     rax, aCopilotenabled_2; "CopilotEnabledState"
0x141907c4f  mov     [rsp+160h+var_100], rax
0x141907c54  lea     r9, [rbp+60h+var_90]
0x141907c58  lea     r8, [rsp+160h+var_F0]
0x141907c5d  lea     rdx, [rsp+160h+var_120]
0x141907c62  lea     rcx, [rsp+160h+var_108]
0x141907c67  call    ??$SendTelemetryEvent@U?$DataField@E@Telemetry@Mso@@U?$DataField@PEB_W@23@@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@$$QEAU?$DataField@E@01@$$QEAU?$DataField@PEB_W@01@@Z; Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<uchar>,Mso::Telemetry::DataField<wchar_t const *>>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Mso::Telemetry::DataField<uchar> &&,Mso::Telemetry::DataField<wchar_t const *> &&)
0x141907c6c  mov     al, cs:byte_144036898
0x141907c72  test    al, al
0x141907c74  js      short loc_141907C7B
0x141907c76  setnz   al
0x141907c79  jmp     short loc_141907C88
0x141907c7b  lea     rcx, byte_144036898
0x141907c82  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x141907c88  test    al, al
0x141907c8a  jz      short loc_141907CD3
0x141907c8c  mov     edx, 130h
0x141907c91  mov     rax, gs:58h
  ... truncated ...
```
