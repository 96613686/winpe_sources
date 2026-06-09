# PhoneController::_ProcessControllerMessage(ControllerMessage *)

- ea: `0x1800454bc`
- end: `0x18004612e`
- name: `?_ProcessControllerMessage@PhoneController@@IEAAXPEAVControllerMessage@@@Z`
- size: `3186`
- prototype: `void __fastcall(PhoneController *__hidden this, struct ControllerMessage *)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024c00`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x18000dfe0`
- `0x18000edac`
- `0x1800224a8`
- `0x18002c574`
- `0x18002c580`
- `0x1800358f0`
- `0x18003cedc`
- `0x18003d720`
- `0x180040954`
- `0x180040de4`
- `0x180040ec0`
- `0x180041084`
- `0x180042438`
- `0x1800426f4`
- `0x180042884`
- `0x180042a68`
- `0x180042c34`
- `0x180042de8`
- `0x18004310c`
- `0x180043270`
- `0x1800433a0`
- `0x180043560`
- `0x180043690`
- `0x180043c58`
- `0x180043f90`
- `0x1800441fc`
- `0x180044324`
- `0x180044484`
- `0x1800447f8`
- `0x1800449e8`
- `0x180044b6c`
- `0x180044cbc`
- `0x180044d78`
- `0x180044f68`
- `0x1800454bc`
- `0x1800482bc`
- `0x18004841c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004563a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004565a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004588f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800458af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045ac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045e0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004563a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004565a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004588f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800458af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045ac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045e0e`

## string_xrefs

- `0x18004558d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004564e`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004567f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004578a`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800458a3`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045ab9`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045ae8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045b13`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045b80`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045db4`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045e02`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045f26`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800460db`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
void __fastcall PhoneController::_ProcessControllerMessage(PhoneController *this, struct ControllerMessage *a2)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  void (__fastcall **v13)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  int v14; // eax
  __int64 v15; // r9
  struct AsyncApiCompletedMessage *v16; // rcx
  void (__fastcall **v17)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  void (__fastcall **v18)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  void (__fastcall **v19)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  struct LineConfigurationMessage *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  void (__fastcall **v24)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  void (__fastcall **v25)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  void (__fastcall **v26)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  int v27; // eax
  __int64 v28; // r9
  void (__fastcall **v29)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  void (__fastcall **v30)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **); // rax
  int v31; // edx
  int v32; // edx
  int v33; // edx
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // edx
  void (__fastcall **v38)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  int v39; // ecx
  struct AsyncApiCompletedMessage *v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rcx
  void (__fastcall **v43)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  int v44; // eax
  __int64 v45; // r9
  void (__fastcall **v46)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v47)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v48)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v49)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v50)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v51)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  struct AsyncApiCompletedMessage *v52; // rdi
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // r9
  __int64 v56; // r8
  int v57; // eax
  BackTraceCollection *v58; // rcx
  unsigned int v59; // r14d
  __int64 v60; // rcx
  int v61; // edx
  int v62; // edx
  int v63; // edx
  int v64; // edx
  int v65; // edx
  int v66; // edx
  int v67; // edx
  void (__fastcall **v68)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v69)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v70)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v71)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v72)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  __int64 v73; // rax
  __int64 v74; // r9
  int v75; // eax
  __int64 v76; // rax
  void (__fastcall **v77)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  __int64 v78; // rcx
  __int64 v79; // rcx
  void (__fastcall **v80)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v81)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  int v82; // edx
  int v83; // edx
  int v84; // edx
  int v85; // edx
  int v86; // edx
  int v87; // edx
  int v88; // edx
  void (__fastcall **v89)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  int v90; // ecx
  void (__fastcall **v91)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v92)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v93)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v94)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  void (__fastcall **v95)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **); // rax
  __int64 v96; // [rsp+20h] [rbp-29h]
  struct AsyncApiCompletedMessage *v97; // [rsp+30h] [rbp-19h] BYREF
  struct LineConfigurationMessage *v98; // [rsp+38h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-9h] BYREF
  __int16 v100; // [rsp+50h] [rbp+7h] BYREF
  __int64 v101; // [rsp+52h] [rbp+9h]
  int v102; // [rsp+5Ah] [rbp+11h]
  __int16 v103; // [rsp+5Eh] [rbp+15h]
  __int128 v104; // [rsp+60h] [rbp+17h] BYREF
  __int64 v105; // [rsp+70h] [rbp+27h]

  v4 = *((_DWORD *)a2 + 6);
  if ( v4 > 22 )
  {
    if ( v4 <= 31 )
    {
      if ( v4 == 31 )
      {
        v81 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
        v97 = 0;
        (*v81)(a2, &GUID_db8e154e_f710_4e59_baaf_2b5ef11694db, &v97);
        v44 = PhoneController::_OnCallMovedToLineMessage(this, v97);
        if ( v44 >= 0 )
          goto LABEL_148;
        v45 = 7968;
      }
      else
      {
        v61 = v4 - 23;
        if ( v61 )
        {
          v62 = v61 - 1;
          if ( !v62 )
          {
            v77 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v77)(a2, &GUID_d1f49927_262d_4f96_94ea_20333b7b7da2, &v97);
            if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
            {
              Log_AssertionEvent_3(v78, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2870);
              if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
                MicrosoftTelemetryAssertTriggeredNoArgs();
            }
            v79 = *((_QWORD *)this + 11);
            v105 = 0;
            v104 = 0;
            InternalSinkMessageDispatcher::OnControllerMessage(v79, 50, &v104);
            if ( v105 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            goto LABEL_148;
          }
          v63 = v62 - 1;
          if ( !v63 )
          {
            (*(void (__fastcall **)(struct ControllerMessage *))(*(_QWORD *)a2 + 8LL))(a2);
            v75 = PhoneController::_OnPhoneLineComponentsChangedMessage(this);
            if ( v75 < 0 )
              Log_HREvent_7(
                (unsigned int)v75,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                8047);
            v76 = *(_QWORD *)a2;
            v16 = a2;
            goto LABEL_151;
          }
          v64 = v63 - 1;
          if ( !v64 )
          {
            v72 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v72)(a2, &GUID_632d4aeb_eb8c_410d_b206_3a6e261b3f41, &v97);
            v73 = *((_QWORD *)v97 + 11);
            v74 = *((_QWORD *)v97 + 7);
            if ( v73 == *((_QWORD *)v97 + 12) )
              v73 = 0;
            if ( v74 == *((_QWORD *)v97 + 8) )
              v74 = 0;
            PhoneController::_SendImmediateControllerMessage(
              this,
              *((unsigned int *)v97 + 8),
              (char *)v97 + 36,
              v74,
              v73);
            goto LABEL_148;
          }
          v65 = v64 - 1;
          if ( v65 )
          {
            v66 = v65 - 1;
            if ( v66 )
            {
              v67 = v66 - 1;
              if ( !v67 )
              {
                v69 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
                v97 = 0;
                (*v69)(a2, &GUID_57d31857_69a8_482b_bc5a_5b3408915633, &v97);
                PhoneController::_HandleAsyncApiCompleted(this, v97);
                goto LABEL_148;
              }
              if ( v67 != 1 )
                goto LABEL_128;
              v68 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
              v97 = 0;
              (*v68)(a2, &GUID_11f48d43_d34c_4db2_a33d_e101b88e8b0d, &v97);
              v44 = PhoneController::_OnDataConnectivityStateChange(this, v97);
              if ( v44 >= 0 )
              {
LABEL_148:
                v16 = v97;
                goto LABEL_149;
              }
              v45 = 8163;
            }
            else
            {
              v70 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
              v97 = 0;
              (*v70)(a2, &GUID_17990256_1a63_40c9_962b_b9665c21294a, &v97);
              v44 = PhoneController::_HandleTimerFired(this, v97);
              if ( v44 >= 0 )
                goto LABEL_148;
              v45 = 8135;
            }
          }
          else
          {
            v71 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v71)(a2, &GUID_1c449d34_13d8_4dcb_b152_b6599fae5926, &v97);
            v44 = (**((__int64 (__fastcall ***)(char *, _QWORD))this + 1))((char *)this + 8, *((_QWORD *)v97 + 4));
            if ( v44 >= 0 )
              goto LABEL_148;
            v45 = 8128;
          }
        }
        else
        {
          v80 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
          v97 = 0;
          (*v80)(a2, &GUID_acc6b4cf_e3ca_4b4f_86db_c0bbe9292d6b, &v97);
          v44 = PhoneController::_OnSendLineSettingModifiedMessage(this, v97);
          if ( v44 >= 0 )
            goto LABEL_148;
          v45 = 8103;
        }
      }
      goto LABEL_146;
    }
    v82 = v4 - 32;
    if ( v82 )
    {
      v83 = v82 - 1;
      if ( v83 )
      {
        v84 = v83 - 1;
        if ( !v84 )
        {
          v27 = PhoneController::_OnRecordingStateChanged(this);
          if ( v27 >= 0 )
            return;
          v28 = 8056;
          goto LABEL_39;
        }
        v85 = v84 - 1;
        if ( v85 )
        {
          v86 = v85 - 1;
          if ( !v86 )
          {
            v27 = PhoneController::_OnWifiCallDropWarningMessage(this);
            if ( v27 >= 0 )
              return;
            v28 = 8190;
            goto LABEL_39;
          }
          v87 = v86 - 1;
          if ( v87 )
          {
            v88 = v87 - 1;
            if ( v88 )
            {
              if ( v88 != 1 )
                goto LABEL_128;
              v89 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
              v97 = 0;
              (*v89)(a2, &GUID_46159c1d_325b_4ec9_81fb_10e16274113b, &v97);
              if ( !v97 )
                ATL::AtlThrowImpl(v90);
              v44 = PhoneController::_OnSendAssociatedDevicesChangedMessage(this, v97);
              if ( v44 >= 0 )
                goto LABEL_148;
              v45 = 8083;
            }
            else
            {
              v91 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
              v97 = 0;
              (*v91)(a2, &GUID_ed4e8403_0e75_4104_9138_523692375224, &v97);
              v44 = PhoneController::_OnAssociatedDevicesChangedMessage(this, v97);
              if ( v44 >= 0 )
                goto LABEL_148;
              v45 = 7961;
            }
          }
          else
          {
            v92 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v92)(a2, &GUID_4679880e_9056_41cf_96b6_91a2ca54488c, &v97);
            v44 = PhoneController::_OnVoipAppCallStateChangedMessage(this, v97);
            if ( v44 >= 0 )
              goto LABEL_148;
            v45 = 7954;
          }
        }
        else
        {
          v93 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
          v97 = 0;
          (*v93)(a2, &GUID_11f47e18_4111_4588_acec_503c0c2eed91, &v97);
          v44 = PhoneController::_OnShowWiFiCallingUpsellPrompt(this, v97);
          if ( v44 >= 0 )
            goto LABEL_148;
          v45 = 8184;
        }
      }
      else
      {
        v94 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
        v97 = 0;
        (*v94)(a2, &GUID_0f19fe3a_d6f5_4382_9096_e0f37558289c, &v97);
        v44 = PhoneController::_OnCancelUpgradeMessage(this, v97);
        if ( v44 >= 0 )
          goto LABEL_148;
        v45 = 8177;
      }
    }
    else
    {
      v95 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
      v97 = 0;
      (*v95)(a2, &GUID_23427ddc_1ca8_4ed4_9c65_fafa968451a9, &v97);
      v44 = PhoneController::_OnEndUpgradeOriginationCallMessage(this, v97);
      if ( v44 >= 0 )
        goto LABEL_148;
      v45 = 8170;
    }
LABEL_146:
    v60 = (unsigned int)v44;
LABEL_147:
    Log_HREvent_7(v60, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v45);
    goto LABEL_148;
  }
  if ( v4 == 22 )
  {
    v51 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
    v97 = 0;
    (*v51)(a2, &GUID_5bcec006_8cfa_4202_ac00_f9c461cf0662, &v97);
    v52 = v97;
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v54, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2815);
      if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( *((_QWORD *)v52 + 10) == *((_QWORD *)v52 + 11) )
    {
      Log_AssertionEvent_3(v54, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2817);
      if ( *((_QWORD *)v52 + 10) == *((_QWORD *)v52 + 11) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( *((_QWORD *)v52 + 14) == *((_QWORD *)v52 + 15) )
    {
      Log_AssertionEvent_3(v54, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2818);
      if ( *((_QWORD *)v52 + 14) == *((_QWORD *)v52 + 15) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v55 = *((_QWORD *)v52 + 10);
    v56 = *((_QWORD *)v52 + 14);
    Block[0] = &v100;
    Block[1] = &v100;
    v96 = *((_QWORD *)v52 + 6);
    v101 = 0;
    v102 = 0;
    v103 = 0;
    v100 = 0;
    v57 = PhoneController::_BuildDialSimString(v54, v53, v56, v55, v96, (__int64)Block);
    v59 = v57;
    if ( v57 >= 0 )
    {
      PhoneController::_SendImmediateControllerMessage(this, 2, (char *)v52 + 32, *((_QWORD *)v52 + 10), Block[0]);
      if ( Block[0] != &v100 )
        operator delete(Block[0]);
      goto LABEL_148;
    }
    BackTraceCollection::Capture(v58, v57);
    Log_HREvent_7(v59, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2822);
    if ( Block[0] != &v100 )
      operator delete(Block[0]);
    v45 = 8069;
    v60 = v59;
    goto LABEL_147;
  }
  if ( v4 > 10 )
  {
    v31 = v4 - 11;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                v37 = v36 - 1;
                if ( v37 )
                {
                  if ( v37 != 1 )
                    goto LABEL_128;
                  v38 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
                  v97 = 0;
                  (*v38)(a2, &GUID_67436729_0d37_4ef5_8c6b_a007ba3c0a41, &v97);
                  v40 = v97;
                  if ( !v97 )
                    ATL::AtlThrowImpl(v39);
                  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
                  {
                    Log_AssertionEvent_3(
                      v41,
                      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                      2835);
                    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
                      MicrosoftTelemetryAssertTriggeredNoArgs();
                  }
                  v42 = *((_QWORD *)this + 11);
                  LODWORD(v98) = *((_DWORD *)v40 + 14);
                  *(_QWORD *)&v104 = (char *)v40 + 32;
                  *((_QWORD *)&v104 + 1) = &v98;
                  InternalSinkMessageDispatcher::_BroadcastSinkMessage_ICallsStateChangeSink__lambda_92d415eeddfd7392f1ad88e9977be355___(
                    v42,
                    v42 + 24,
                    &v104);
                  goto LABEL_148;
                }
                v43 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
                v97 = 0;
                (*v43)(a2, &GUID_2fa1e53d_a503_4af3_ad56_f9f6b2f4e21f, &v97);
                v44 = PhoneController::_OnSendErrorMessage(this, v97);
                if ( v44 >= 0 )
                  goto LABEL_148;
                v45 = 8090;
                goto LABEL_146;
              }
              v27 = PhoneController::_SendImmediateAudioChangedNotification(this);
              if ( v27 >= 0 )
                return;
              v28 = 8096;
LABEL_39:
              Log_HREvent_7(
                (unsigned int)v27,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                v28);
              return;
            }
            v46 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v46)(a2, &GUID_1663d789_9ba0_4d4a_901d_53636cd43e26, &v97);
            v44 = PhoneController::_OnRemovedPhoneLine(this, v97);
            if ( v44 >= 0 )
              goto LABEL_148;
            v45 = 8040;
          }
          else
          {
            v47 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
            v97 = 0;
            (*v47)(a2, &GUID_e98baa9b_6c18_4ac9_9a46_973babadde09, &v97);
            v44 = PhoneController::_OnOperationCompleteMessage(this, *((_QWORD *)v97 + 5), *((_DWORD *)v97 + 8));
            if ( v44 >= 0 )
              goto LABEL_148;
            v45 = 7975;
          }
        }
        else
        {
          v48 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
          v97 = 0;
          (*v48)(a2, &GUID_0e18f82a_6c86_4483_b5e2_fa92a5a79e53, &v97);
          v44 = PhoneController::_OnNewPhoneLine(this, v97);
          if ( v44 >= 0 )
            goto LABEL_148;
          v45 = 8033;
        }
      }
      else
      {
        v49 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
        v97 = 0;
        (*v49)(a2, &GUID_6e48e7c8_b5ee_457c_8644_1cbe4a5931ce, &v97);
        v44 = PhoneController::_OnLineStateChanged(this, v97);
        if ( v44 >= 0 )
          goto LABEL_148;
        v45 = 7997;
      }
    }
    else
    {
      v50 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct AsyncApiCompletedMessage **))a2;
      v97 = 0;
      (*v50)(a2, &GUID_0bc1d389_06d3_48fa_b1cb_1dd0bd27831e, &v97);
      v44 = PhoneController::_OnLineLockInfoChanged(this, v97);
      if ( v44 >= 0 )
        goto LABEL_148;
      v45 = 8011;
    }
    goto LABEL_146;
  }
  if ( v4 == 10 )
  {
    v30 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v30)(a2, &GUID_f7a55515_96b7_47f8_913d_9816c51d5df8, &v98);
    v14 = PhoneController::_OnLineRegistrationInfoChanged(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 8004;
    goto LABEL_16;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v29 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v29)(a2, &GUID_d5deda58_3a7a_4026_9abb_bbc27a4c97ca, &v98);
    v14 = PhoneController::_OnAlertMessage(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 7983;
    goto LABEL_16;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v27 = PhoneController::_SendImmediateAudioChangedNotification(this);
    if ( v27 >= 0 )
      return;
    v28 = 2747;
    goto LABEL_39;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v26 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v26)(a2, &GUID_75be0e87_45eb_44d3_8225_16128010303e, &v98);
    v14 = PhoneController::_OnCallsChangedMessage(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 7947;
    goto LABEL_16;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v25 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v25)(a2, &GUID_9e0fa113_ec8e_473d_8b6d_8ae3d5b8c530, &v98);
    v14 = PhoneController::_OnContactRemoteInfoMessage(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 8149;
    goto LABEL_16;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v24 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v24)(a2, &GUID_eb0bdb2e_14b0_4e5c_8e60_5e2d3b300ea6, &v98);
    v14 = PhoneController::_OnCallUpgradeSupportLevelMessage(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 8156;
    goto LABEL_16;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v19 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v19)(a2, &GUID_b1819a4f_9080_4656_8068_cc12af8f5ebf, &v98);
    v20 = v98;
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v21, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2789);
      if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v22 = *((unsigned int *)v20 + 8);
    if ( (_DWORD)v22 )
    {
      if ( (_DWORD)v22 != 1 )
      {
        Log_AssertionEvent_3(v22, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2802);
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_17;
      }
      v23 = 18;
    }
    else
    {
      v23 = 19;
    }
    PhoneController::_SendImmediateControllerMessage(this, v23, &GUID_00000000_0000_0000_0000_000000000000, 0, 0);
    goto LABEL_17;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v18 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v18)(a2, &GUID_826590ff_84f7_4dbd_b9de_e4c33d2a498f, &v98);
    v14 = PhoneController::_OnLineBluetoothHandsFreeDeviceStateChanged(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 7990;
    goto LABEL_16;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v17 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
    v98 = 0;
    (*v17)(a2, &GUID_dd7cef16_fdff_46b7_a621_7ab44c080c11, &v98);
    v14 = PhoneController::_OnLineConfigurationChanged(this, v98);
    if ( v14 >= 0 )
      goto LABEL_17;
    v15 = 8026;
    goto LABEL_16;
  }
  if ( v12 != 1 )
  {
LABEL_128:
    Log_AssertionEvent_3(this, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8195);
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return;
  }
  v13 = *(void (__fastcall ***)(struct ControllerMessage *, GUID *, struct LineConfigurationMessage **))a2;
  v98 = 0;
  (*v13)(a2, &GUID_6234182b_8559_4ef6_a5b9_980b1ba064c8, &v98);
  v14 = PhoneController::_OnLineSignalStrengthChanged(this, v98);
  if ( v14 < 0 )
  {
    v15 = 8018;
LABEL_16:
    Log_HREvent_7((unsigned int)v14, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v15);
  }
LABEL_17:
  v16 = v98;
LABEL_149:
  if ( !v16 )
    return;
  v76 = *(_QWORD *)v16;
LABEL_151:
  (*(void (__fastcall **)(struct AsyncApiCompletedMessage *))(v76 + 16))(v16);
}

```

## disassembly

```asm
0x1800454bc  mov     [rsp-8+arg_10], rbx
0x1800454c1  mov     [rsp-8+arg_18], rsi
0x1800454c6  push    rbp
0x1800454c7  push    rdi
0x1800454c8  push    r14
0x1800454ca  lea     rbp, [rsp-47h]
0x1800454cf  sub     rsp, 90h
0x1800454d6  mov     rax, cs:__security_cookie
0x1800454dd  xor     rax, rsp
0x1800454e0  mov     [rbp+57h+var_20], rax
0x1800454e4  mov     rdi, rdx
0x1800454e7  mov     rsi, rcx
0x1800454ea  mov     edx, [rdx+18h]
0x1800454ed  cmp     edx, 16h
0x1800454f0  jg      loc_180045BFB
0x1800454f6  jz      loc_180045A82
0x1800454fc  cmp     edx, 0Ah
0x1800454ff  jg      loc_18004581B
0x180045505  jz      loc_1800457DD
0x18004550b  sub     edx, 1
0x18004550e  jz      loc_18004579F
0x180045514  sub     edx, 1
0x180045517  jz      loc_180045777
0x18004551d  sub     edx, 1
0x180045520  jz      loc_180045739
0x180045526  sub     edx, 1
0x180045529  jz      loc_1800456FB
0x18004552f  sub     edx, 1
0x180045532  jz      loc_1800456BD
0x180045538  sub     edx, 1
0x18004553b  jz      loc_180045617
0x180045541  sub     edx, 1
0x180045544  jz      loc_1800455DD
0x18004554a  sub     edx, 1
0x18004554d  jz      short loc_1800455A6
0x18004554f  cmp     edx, 1
0x180045552  jnz     loc_180045F20
0x180045558  mov     rax, [rdi]
0x18004555b  lea     r8, [rbp+57h+var_68]
0x18004555f  xor     ebx, ebx
0x180045561  lea     rdx, _GUID_6234182b_8559_4ef6_a5b9_980b1ba064c8
0x180045568  mov     rcx, rdi
0x18004556b  mov     [rbp+57h+var_68], rbx
0x18004556f  mov     rax, [rax]
0x180045572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045577  mov     rdx, [rbp+57h+var_68]; struct LineSignalStrengthMessage *
0x18004557b  mov     rcx, rsi; this
0x18004557e  call    ?_OnLineSignalStrengthChanged@PhoneController@@IEAAJPEBVLineSignalStrengthMessage@@@Z; PhoneController::_OnLineSignalStrengthChanged(LineSignalStrengthMessage const *)
0x180045583  test    eax, eax
0x180045585  jns     short loc_18004559D
0x180045587  mov     r9d, 1F52h
0x18004558d  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045594  xor     edx, edx
0x180045596  mov     ecx, eax
0x180045598  call    Log_HREvent_7
0x18004559d  mov     rcx, [rbp+57h+var_68]
0x1800455a1  jmp     loc_1800460ED
0x1800455a6  mov     rax, [rdi]
0x1800455a9  lea     r8, [rbp+57h+var_68]
0x1800455ad  xor     ebx, ebx
0x1800455af  lea     rdx, _GUID_dd7cef16_fdff_46b7_a621_7ab44c080c11
0x1800455b6  mov     rcx, rdi
0x1800455b9  mov     [rbp+57h+var_68], rbx
0x1800455bd  mov     rax, [rax]
0x1800455c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455c5  mov     rdx, [rbp+57h+var_68]; struct LineConfigurationMessage *
0x1800455c9  mov     rcx, rsi; this
0x1800455cc  call    ?_OnLineConfigurationChanged@PhoneController@@IEAAJPEBVLineConfigurationMessage@@@Z; PhoneController::_OnLineConfigurationChanged(LineConfigurationMessage const *)
0x1800455d1  test    eax, eax
0x1800455d3  jns     short loc_18004559D
0x1800455d5  mov     r9d, 1F5Ah
0x1800455db  jmp     short loc_18004558D
0x1800455dd  mov     rax, [rdi]
0x1800455e0  lea     r8, [rbp+57h+var_68]
0x1800455e4  xor     ebx, ebx
0x1800455e6  lea     rdx, _GUID_826590ff_84f7_4dbd_b9de_e4c33d2a498f
0x1800455ed  mov     rcx, rdi
0x1800455f0  mov     [rbp+57h+var_68], rbx
0x1800455f4  mov     rax, [rax]
0x1800455f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455fc  mov     rdx, [rbp+57h+var_68]; struct LineBluetoothHandsFreeDeviceStateMessage *
0x180045600  mov     rcx, rsi; this
0x180045603  call    ?_OnLineBluetoothHandsFreeDeviceStateChanged@PhoneController@@IEAAJPEBVLineBluetoothHandsFreeDeviceStateMessage@@@Z; PhoneController::_OnLineBluetoothHandsFreeDeviceStateChanged(LineBluetoothHandsFreeDeviceStateMessage const *)
0x180045608  test    eax, eax
0x18004560a  jns     short loc_18004559D
0x18004560c  mov     r9d, 1F36h
0x180045612  jmp     loc_18004558D
0x180045617  mov     rax, [rdi]
0x18004561a  lea     r8, [rbp+57h+var_68]
0x18004561e  xor     ebx, ebx
0x180045620  lea     rdx, _GUID_b1819a4f_9080_4656_8068_cc12af8f5ebf
0x180045627  mov     rcx, rdi
0x18004562a  mov     [rbp+57h+var_68], rbx
0x18004562e  mov     rax, [rax]
0x180045631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045636  mov     rdi, [rbp+57h+var_68]
0x18004563a  call    cs:__imp_GetCurrentThreadId
0x180045640  cmp     [rsi+0F0h], eax
0x180045646  jnz     short loc_18004566D
0x180045648  mov     r8d, 0AE5h
0x18004564e  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045655  call    Log_AssertionEvent_3
0x18004565a  call    cs:__imp_GetCurrentThreadId
0x180045660  cmp     [rsi+0F0h], eax
0x180045666  jnz     short loc_18004566D
0x180045668  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004566d  mov     ecx, [rdi+20h]
0x180045670  test    ecx, ecx
0x180045672  jz      short loc_18004569C
0x180045674  cmp     ecx, 1
0x180045677  jz      short loc_180045695
0x180045679  mov     r8d, 0AF2h
0x18004567f  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045686  call    Log_AssertionEvent_3
0x18004568b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180045690  jmp     loc_18004559D
0x180045695  mov     edx, 12h
0x18004569a  jmp     short loc_1800456A1
0x18004569c  mov     edx, 13h
0x1800456a1  xor     r9d, r9d
0x1800456a4  mov     [rsp+0A0h+var_80], rbx
0x1800456a9  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x1800456b0  mov     rcx, rsi
0x1800456b3  call    ?_SendImmediateControllerMessage@PhoneController@@IEAAXW4tagPH_MSG@@AEBU_GUID@@PEBG2@Z; PhoneController::_SendImmediateControllerMessage(tagPH_MSG,_GUID const &,ushort const *,ushort const *)
0x1800456b8  jmp     loc_18004559D
0x1800456bd  mov     rax, [rdi]
0x1800456c0  lea     r8, [rbp+57h+var_68]
0x1800456c4  xor     ebx, ebx
0x1800456c6  lea     rdx, _GUID_eb0bdb2e_14b0_4e5c_8e60_5e2d3b300ea6
0x1800456cd  mov     rcx, rdi
0x1800456d0  mov     [rbp+57h+var_68], rbx
0x1800456d4  mov     rax, [rax]
0x1800456d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456dc  mov     rdx, [rbp+57h+var_68]; struct CallUpgradeSupportLevelMessage *
0x1800456e0  mov     rcx, rsi; this
0x1800456e3  call    ?_OnCallUpgradeSupportLevelMessage@PhoneController@@IEAAJPEBVCallUpgradeSupportLevelMessage@@@Z; PhoneController::_OnCallUpgradeSupportLevelMessage(CallUpgradeSupportLevelMessage const *)
0x1800456e8  test    eax, eax
0x1800456ea  jns     loc_18004559D
0x1800456f0  mov     r9d, 1FDCh
0x1800456f6  jmp     loc_18004558D
0x1800456fb  mov     rax, [rdi]
0x1800456fe  lea     r8, [rbp+57h+var_68]
0x180045702  xor     ebx, ebx
0x180045704  lea     rdx, _GUID_9e0fa113_ec8e_473d_8b6d_8ae3d5b8c530
0x18004570b  mov     rcx, rdi
0x18004570e  mov     [rbp+57h+var_68], rbx
0x180045712  mov     rax, [rax]
0x180045715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004571a  mov     rdx, [rbp+57h+var_68]; struct ContactRemoteInfoMessage *
0x18004571e  mov     rcx, rsi; this
0x180045721  call    ?_OnContactRemoteInfoMessage@PhoneController@@IEAAJPEBVContactRemoteInfoMessage@@@Z; PhoneController::_OnContactRemoteInfoMessage(ContactRemoteInfoMessage const *)
0x180045726  test    eax, eax
0x180045728  jns     loc_18004559D
0x18004572e  mov     r9d, 1FD5h
0x180045734  jmp     loc_18004558D
0x180045739  mov     rax, [rdi]
0x18004573c  lea     r8, [rbp+57h+var_68]
0x180045740  xor     ebx, ebx
0x180045742  lea     rdx, _GUID_75be0e87_45eb_44d3_8225_16128010303e
0x180045749  mov     rcx, rdi
0x18004574c  mov     [rbp+57h+var_68], rbx
0x180045750  mov     rax, [rax]
0x180045753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045758  mov     rdx, [rbp+57h+var_68]; struct CallsChangedMessage *
0x18004575c  mov     rcx, rsi; this
0x18004575f  call    ?_OnCallsChangedMessage@PhoneController@@IEAAJPEBVCallsChangedMessage@@@Z; PhoneController::_OnCallsChangedMessage(CallsChangedMessage const *)
0x180045764  test    eax, eax
0x180045766  jns     loc_18004559D
0x18004576c  mov     r9d, 1F0Bh
0x180045772  jmp     loc_18004558D
0x180045777  call    ?_SendImmediateAudioChangedNotification@PhoneController@@IEAAJXZ; PhoneController::_SendImmediateAudioChangedNotification(void)
0x18004577c  test    eax, eax
0x18004577e  jns     loc_1800460FE
0x180045784  mov     r9d, 0ABBh
0x18004578a  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045791  xor     edx, edx
0x180045793  mov     ecx, eax
0x180045795  call    Log_HREvent_7
0x18004579a  jmp     loc_1800460FE
0x18004579f  mov     rax, [rdi]
0x1800457a2  lea     r8, [rbp+57h+var_68]
0x1800457a6  xor     ebx, ebx
0x1800457a8  lea     rdx, _GUID_d5deda58_3a7a_4026_9abb_bbc27a4c97ca
0x1800457af  mov     rcx, rdi
0x1800457b2  mov     [rbp+57h+var_68], rbx
0x1800457b6  mov     rax, [rax]
0x1800457b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457be  mov     rdx, [rbp+57h+var_68]; struct AlertMessage *
0x1800457c2  mov     rcx, rsi; this
0x1800457c5  call    ?_OnAlertMessage@PhoneController@@IEAAJPEBVAlertMessage@@@Z; PhoneController::_OnAlertMessage(AlertMessage const *)
0x1800457ca  test    eax, eax
0x1800457cc  jns     loc_18004559D
0x1800457d2  mov     r9d, 1F2Fh
0x1800457d8  jmp     loc_18004558D
0x1800457dd  mov     rax, [rdi]
0x1800457e0  lea     r8, [rbp+57h+var_68]
0x1800457e4  xor     ebx, ebx
0x1800457e6  lea     rdx, _GUID_f7a55515_96b7_47f8_913d_9816c51d5df8
0x1800457ed  mov     rcx, rdi
0x1800457f0  mov     [rbp+57h+var_68], rbx
0x1800457f4  mov     rax, [rax]
0x1800457f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457fc  mov     rdx, [rbp+57h+var_68]; struct LineRegistrationInfoMessage *
0x180045800  mov     rcx, rsi; this
0x180045803  call    ?_OnLineRegistrationInfoChanged@PhoneController@@IEAAJPEBVLineRegistrationInfoMessage@@@Z; PhoneController::_OnLineRegistrationInfoChanged(LineRegistrationInfoMessage const *)
0x180045808  test    eax, eax
0x18004580a  jns     loc_18004559D
0x180045810  mov     r9d, 1F44h
0x180045816  jmp     loc_18004558D
0x18004581b  sub     edx, 0Bh
0x18004581e  jz      loc_180045A44
0x180045824  sub     edx, 1
0x180045827  jz      loc_180045A06
0x18004582d  sub     edx, 1
0x180045830  jz      loc_1800459C8
0x180045836  sub     edx, 1
0x180045839  jz      loc_180045982
0x18004583f  sub     edx, 1
0x180045842  jz      loc_180045944
0x180045848  sub     edx, 1
0x18004584b  jz      loc_18004592C
0x180045851  sub     edx, 1
0x180045854  jz      loc_1800458EE
0x18004585a  cmp     edx, 1
0x18004585d  jnz     loc_180045F20
0x180045863  mov     rax, [rdi]
0x180045866  lea     r8, [rbp+57h+var_70]
0x18004586a  xor     ebx, ebx
0x18004586c  lea     rdx, _GUID_67436729_0d37_4ef5_8c6b_a007ba3c0a41
0x180045873  mov     rcx, rdi
0x180045876  mov     [rbp+57h+var_70], rbx
0x18004587a  mov     rax, [rax]
0x18004587d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045882  mov     rdi, [rbp+57h+var_70]
0x180045886  test    rdi, rdi
0x180045889  jz      loc_180046128
0x18004588f  call    cs:__imp_GetCurrentThreadId
0x180045895  cmp     [rsi+0F0h], eax
0x18004589b  jnz     short loc_1800458C2
0x18004589d  mov     r8d, 0B13h
0x1800458a3  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800458aa  call    Log_AssertionEvent_3
0x1800458af  call    cs:__imp_GetCurrentThreadId
0x1800458b5  cmp     [rsi+0F0h], eax
0x1800458bb  jnz     short loc_1800458C2
0x1800458bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800458c2  mov     eax, [rdi+38h]
0x1800458c5  lea     r8, [rbp+57h+var_40]
0x1800458c9  mov     rcx, [rsi+58h]
0x1800458cd  mov     dword ptr [rbp+57h+var_68], eax
0x1800458d0  lea     rax, [rdi+20h]
0x1800458d4  mov     qword ptr [rbp+57h+var_40], rax
0x1800458d8  lea     rax, [rbp+57h+var_68]
0x1800458dc  mov     qword ptr [rbp+57h+var_40+8], rax
0x1800458e0  lea     rdx, [rcx+18h]
0x1800458e4  call    InternalSinkMessageDispatcher___BroadcastSinkMessage_ICallsStateChangeSink__lambda_92d415eeddfd7392f1ad88e9977be355___
0x1800458e9  jmp     loc_1800460E9
0x1800458ee  mov     rax, [rdi]
0x1800458f1  lea     r8, [rbp+57h+var_70]
0x1800458f5  xor     ebx, ebx
0x1800458f7  lea     rdx, _GUID_2fa1e53d_a503_4af3_ad56_f9f6b2f4e21f
0x1800458fe  mov     rcx, rdi
0x180045901  mov     [rbp+57h+var_70], rbx
0x180045905  mov     rax, [rax]
0x180045908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004590d  mov     rdx, [rbp+57h+var_70]; struct SendErrorMessage *
0x180045911  mov     rcx, rsi; this
0x180045914  call    ?_OnSendErrorMessage@PhoneController@@IEAAJPEBVSendErrorMessage@@@Z; PhoneController::_OnSendErrorMessage(SendErrorMessage const *)
0x180045919  test    eax, eax
0x18004591b  jns     loc_1800460E9
0x180045921  mov     r9d, 1F9Ah
0x180045927  jmp     loc_1800460D9
0x18004592c  call    ?_SendImmediateAudioChangedNotification@PhoneController@@IEAAJXZ; PhoneController::_SendImmediateAudioChangedNotification(void)
0x180045931  test    eax, eax
0x180045933  jns     loc_1800460FE
0x180045939  mov     r9d, 1FA0h
0x18004593f  jmp     loc_18004578A
0x180045944  mov     rax, [rdi]
0x180045947  lea     r8, [rbp+57h+var_70]
0x18004594b  xor     ebx, ebx
0x18004594d  lea     rdx, _GUID_1663d789_9ba0_4d4a_901d_53636cd43e26
0x180045954  mov     rcx, rdi
0x180045957  mov     [rbp+57h+var_70], rbx
0x18004595b  mov     rax, [rax]
0x18004595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045963  mov     rdx, [rbp+57h+var_70]; struct RemovedPhoneLineMessage *
0x180045967  mov     rcx, rsi; this
0x18004596a  call    ?_OnRemovedPhoneLine@PhoneController@@IEAAJPEBVRemovedPhoneLineMessage@@@Z; PhoneController::_OnRemovedPhoneLine(RemovedPhoneLineMessage const *)
0x18004596f  test    eax, eax
0x180045971  jns     loc_1800460E9
0x180045977  mov     r9d, 1F68h
0x18004597d  jmp     loc_1800460D9
0x180045982  mov     rax, [rdi]
0x180045985  lea     r8, [rbp+57h+var_70]
0x180045989  xor     ebx, ebx
0x18004598b  lea     rdx, _GUID_e98baa9b_6c18_4ac9_9a46_973babadde09
0x180045992  mov     rcx, rdi
0x180045995  mov     [rbp+57h+var_70], rbx
0x180045999  mov     rax, [rax]
0x18004599c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
