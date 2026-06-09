# OobeEasyConnectTask::OnAsyncOperationFinished(_GUID const &,SimSlot,ESimSettingOperation,long,ulong)

- ea: `0x1800215a0`
- end: `0x180021b02`
- name: `?OnAsyncOperationFinished@OobeEasyConnectTask@@UEAAJAEBU_GUID@@W4SimSlot@@W4ESimSettingOperation@@JK@Z`
- size: `1378`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ad20`
- `0x18000bde0`
- `0x18001f898`
- `0x1800215a0`
- `0x180021b08`
- `0x180021cfc`
- `0x180022a1c`
- `0x180022a3c`
- `0x180022ac0`
- `0x180022bf8`
- `0x180022c1c`
- `0x180022ce0`
- `0x180022e9c`
- `0x18002cd20`
- `0x18002d8c8`
- `0x180047c2c`
- `0x180047c64`
- `0x180047f38`
- `0x1800482b4`
- `0x180048440`
- `0x1800485a4`
- `0x18004a364`
- `0x18004a514`

## string_xrefs

- `0x1800215fe`: `OobeEasyConnectTask::OnAsyncOperationFinished`
- `0x180021649`: `OobeEasyConnectTask::OnAsyncOperationFinished`
- `0x180021831`: `Max number of discovery attempts reached, stop trying discovery and continue`
- `0x180021851`: `Changing state to WaitingForCorrectStateForBootstrapDelete`
- `0x180021a07`: `Changing state to WaitingForCorrectStateForBootstrapDelete`
- `0x1800219d9`: `Discovery Complete/Cancelled`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall OobeEasyConnectTask::OnAsyncOperationFinished(
        __int64 a1,
        _QWORD *a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6)
{
  __int64 v8; // rax
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // edi
  int v15; // edi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int AvailableConnectivityTypesForTelemetry; // r10d
  const wchar_t **v19; // rdi
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // r10d
  const wchar_t *v28; // rcx
  const wchar_t *v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // ebx
  int v35; // [rsp+28h] [rbp-140h]
  char v36; // [rsp+40h] [rbp-128h]
  __int64 v37; // [rsp+48h] [rbp-120h] BYREF
  _BYTE v38[16]; // [rsp+50h] [rbp-118h] BYREF
  char v39[64]; // [rsp+60h] [rbp-108h] BYREF
  char v40[144]; // [rsp+A0h] [rbp-C8h] BYREF

  v8 = *(_QWORD *)(a1 + 80) - *a2;
  if ( !v8 )
    v8 = *(_QWORD *)(a1 + 88) - a2[1];
  if ( v8 )
    return 0;
  if ( *(_DWORD *)(a1 + 116) != a3 )
  {
    MBSettingUXLogging::Info(
      "OobeEasyConnectTask::OnAsyncOperationFinished",
      360,
      "Discarding notification for slot %d",
      a3);
    return 0;
  }
  wil::EnterCriticalSection(v38, a1 + 24);
  MBSettingUXLogging::Info(
    "OobeEasyConnectTask::OnAsyncOperationFinished",
    365,
    "operation=%d, HRESULT=0x%x, errorDetail=%d",
    a4,
    a5,
    a6);
  v10 = a1 + 1192;
  v11 = tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(a1 + 1192);
  tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(
    v39,
    v11);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::operator->(
                           a1 + 1192,
                           &v37)
            + 276LL) = a5;
  tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(&v37);
  if ( a5 < 0 )
  {
    v12 = tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(a1 + 1192);
    tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(
      &v37,
      v12);
    v13 = v37;
    *(_DWORD *)(v37 + 280) = a4;
    *(_DWORD *)(v13 + 284) = a6;
    tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::close(&v37);
    v14 = a4 - 4;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( (unsigned int)(v15 - 1) <= 1 && (unsigned int)(*(_DWORD *)(a1 + 96) - 1) <= 1 )
        {
          if ( *(_DWORD *)(a1 + 100) )
          {
            v16 = (_QWORD *)(a1 + 216);
            *(_QWORD *)(a1 + 232) = 0;
            if ( *(_QWORD *)(a1 + 240) > 7u )
              v16 = (_QWORD *)*v16;
            *(_WORD *)v16 = 0;
            MBSettingUXLogging::Warn(
              "OobeEasyConnectTask::OnAsyncOperationFinished",
              389,
              "Failed to finish Discovery, %d retries left",
              *(_DWORD *)(a1 + 100));
            *(_DWORD *)(a1 + 96) = 0;
            OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
            --*(_DWORD *)(a1 + 100);
            LOBYTE(v17) = v36;
            OobeEasyConnectTask::AttemptDiscovery(a1, v17);
          }
          else
          {
            memset_0(v40, 0, 0x81u);
            TraceLoggingCorrelationVector::ToStringImpl(
              *(TraceLoggingCorrelationVector **)(a1 + 104),
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 104) + 136LL), 0),
              v40);
            AvailableConnectivityTypesForTelemetry = OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(a1);
            v19 = (const wchar_t **)(a1 + 216);
            if ( *(_QWORD *)(a1 + 1176) )
            {
              if ( *(_QWORD *)(a1 + 240) <= 7u )
                v20 = (const wchar_t *)(a1 + 216);
              else
                v20 = *v19;
            }
            else
            {
              v20 = L"00000000";
            }
            if ( *(_DWORD *)(a1 + 96) == 1 )
            {
              v21 = L"Discovery";
            }
            else
            {
              v21 = L"Downloading";
              if ( *(_DWORD *)(a1 + 96) != 2 )
                v21 = L"Other";
            }
            LOBYTE(v35) = *(_BYTE *)(a1 + 112);
            MBSettingUXLogging::OperatorDiscoveryCompleted(
              v40,
              v21,
              (unsigned int)a5,
              a6,
              a1 + 550,
              v35,
              v20,
              AvailableConnectivityTypesForTelemetry);
            *(_QWORD *)(a1 + 232) = 0;
            if ( *(_QWORD *)(a1 + 240) > 7u )
              v19 = (const wchar_t **)*v19;
            *(_WORD *)v19 = 0;
            MBSettingUXLogging::Warn(
              "OobeEasyConnectTask::OnAsyncOperationFinished",
              412,
              "Max number of discovery attempts reached, stop trying discovery and continue");
            if ( *(_BYTE *)(a1 + 168) )
            {
              MBSettingUXLogging::Info(
                "OobeEasyConnectTask::OnAsyncOperationFinished",
                415,
                "Changing state to WaitingForCorrectStateForBootstrapDelete");
              *(_DWORD *)(a1 + 96) = 3;
              OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
              OobeEasyConnectTask::AttemptDeleteBootstrapProfile(a1, v36);
            }
            else
            {
              MBSettingUXLogging::Info(
                "OobeEasyConnectTask::OnAsyncOperationFinished",
                421,
                "Changing state to WaitingForCorrectStateForProfileEnable");
              *(_DWORD *)(a1 + 96) = 4;
              OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
              LOBYTE(v22) = v36;
              OobeEasyConnectTask::AttemptEnableDownloadedProfile(a1, v22, v23);
            }
          }
        }
      }
      else
      {
        MBSettingUXLogging::Warn("OobeEasyConnectTask::OnAsyncOperationFinished", 431, "Failed to Activate profile");
        if ( *(_DWORD *)(a1 + 96) == 4 )
        {
          MBSettingUXLogging::Info("OobeEasyConnectTask::OnAsyncOperationFinished", 434, "Changing state to Error");
          *(_DWORD *)(a1 + 96) = 7;
          OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
        }
      }
    }
    else
    {
      MBSettingUXLogging::BootstrapProfileDeletion(a5, a6);
    }
    goto LABEL_52;
  }
  v24 = a4 - 4;
  if ( !v24 )
  {
    MBSettingUXLogging::BootstrapProfileDeletion(a5, a6);
    goto LABEL_54;
  }
  v25 = v24 - 2;
  if ( !v25 )
  {
    std::wstring::operator=(a1 + 1160, a1 + 216);
    LOBYTE(v32) = v36;
    OobeEasyConnectTask::AttemptEnableDownloadedProfile(a1, v32, v33);
    v34 = ++*(_DWORD *)(a1 + 1200);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::operator->(
                             v10,
                             &v37)
              + 288LL) = v34;
LABEL_52:
    tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(&v37);
    goto LABEL_54;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    memset_0(v40, 0, 0x81u);
    TraceLoggingCorrelationVector::ToStringImpl(
      *(TraceLoggingCorrelationVector **)(a1 + 104),
      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 104) + 136LL), 0),
      v40);
    v27 = OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(a1);
    if ( *(_QWORD *)(a1 + 1176) )
    {
      v28 = (const wchar_t *)(a1 + 216);
      if ( *(_QWORD *)(a1 + 240) > 7u )
        v28 = *(const wchar_t **)v28;
    }
    else
    {
      v28 = L"00000000";
    }
    if ( *(_DWORD *)(a1 + 96) == 1 )
    {
      v29 = L"Discovery";
    }
    else
    {
      v29 = L"Downloading";
      if ( *(_DWORD *)(a1 + 96) != 2 )
        v29 = L"Other";
    }
    LOBYTE(v35) = *(_BYTE *)(a1 + 112);
    MBSettingUXLogging::OperatorDiscoveryCompleted(v40, v29, (unsigned int)a5, a6, a1 + 550, v35, v28, v27);
    goto LABEL_47;
  }
  if ( v26 == 3 )
  {
LABEL_47:
    MBSettingUXLogging::Info("OobeEasyConnectTask::OnAsyncOperationFinished", 482, "Discovery Complete/Cancelled");
    if ( (unsigned int)(*(_DWORD *)(a1 + 96) - 1) <= 2 )
    {
      if ( *(_BYTE *)(a1 + 168) )
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::OnAsyncOperationFinished",
          487,
          "Changing state to WaitingForCorrectStateForBootstrapDelete");
        *(_DWORD *)(a1 + 96) = 3;
        OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
        OobeEasyConnectTask::AttemptDeleteBootstrapProfile(a1, v36);
      }
      else
      {
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::OnAsyncOperationFinished",
          493,
          "Changing state to WaitingForCorrectStateForProfileEnable");
        *(_DWORD *)(a1 + 96) = 4;
        OobeEasyConnectTask::PublishCurrentTaskStateWnf(a1);
        LOBYTE(v30) = v36;
        OobeEasyConnectTask::AttemptEnableDownloadedProfile(a1, v30, v31);
      }
    }
  }
LABEL_54:
  tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(v39);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v38);
  return 0;
}

```

## disassembly

```asm
0x1800215a0  mov     [rsp+arg_8], rbx
0x1800215a5  push    rsi
0x1800215a6  push    rdi
0x1800215a7  push    r12
0x1800215a9  push    r14
0x1800215ab  push    r15
0x1800215ad  sub     rsp, 140h
0x1800215b4  mov     rax, cs:__security_cookie
0x1800215bb  xor     rax, rsp
0x1800215be  mov     [rsp+168h+var_38], rax
0x1800215c6  mov     edi, r9d
0x1800215c9  mov     rbx, rcx
0x1800215cc  mov     rax, [rcx+50h]
0x1800215d0  sub     rax, [rdx]
0x1800215d3  jnz     short loc_1800215DD
0x1800215d5  mov     rax, [rcx+58h]
0x1800215d9  sub     rax, [rdx+8]
0x1800215dd  test    rax, rax
0x1800215e0  jz      short loc_1800215E9
0x1800215e2  xor     eax, eax
0x1800215e4  jmp     loc_180021AD9
0x1800215e9  cmp     [rcx+74h], r8d
0x1800215ed  jz      short loc_180021611
0x1800215ef  mov     r9d, r8d
0x1800215f2  lea     r8, aDiscardingNoti; "Discarding notification for slot %d"
0x1800215f9  mov     edx, 168h; unsigned int
0x1800215fe  lea     rcx, aOobeeasyconnec_10; "OobeEasyConnectTask::OnAsyncOperationFi"...
0x180021605  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002160a  xor     eax, eax
0x18002160c  jmp     loc_180021AD9
0x180021611  lea     rdx, [rcx+18h]
0x180021615  lea     rcx, [rsp+168h+var_118]
0x18002161a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002161f  nop
0x180021620  mov     r14d, [rsp+168h+arg_28]
0x180021628  mov     [rsp+168h+var_140], r14d
0x18002162d  mov     r15d, [rsp+168h+arg_20]
0x180021635  mov     dword ptr [rsp+168h+var_148], r15d
0x18002163a  mov     r9d, edi
0x18002163d  lea     r8, aOperationDHres; "operation=%d, HRESULT=0x%x, errorDetail"...
0x180021644  mov     edx, 16Dh; unsigned int
0x180021649  lea     rsi, aOobeeasyconnec_10; "OobeEasyConnectTask::OnAsyncOperationFi"...
0x180021650  mov     rcx, rsi; char *
0x180021653  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021658  lea     r12, [rbx+4A8h]
0x18002165f  mov     rcx, r12
0x180021662  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(void)
0x180021667  mov     rdx, rax
0x18002166a  lea     rcx, [rsp+168h+var_108]
0x18002166f  call    ??0?$test_watcher@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy> &)
0x180021674  nop
0x180021675  lea     rdx, [rsp+168h+var_120]
0x18002167a  mov     rcx, r12
0x18002167d  call    ??C?$tip_test@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::operator->(void)
0x180021682  mov     rcx, [rax]
0x180021685  mov     [rcx+114h], r15d
0x18002168c  lea     rcx, [rsp+168h+var_120]
0x180021691  call    ??1?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(void)
0x180021696  test    r15d, r15d
0x180021699  jns     loc_1800218FD
0x18002169f  mov     rcx, r12
0x1800216a2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(void)
0x1800216a7  mov     rdx, rax
0x1800216aa  lea     rcx, [rsp+168h+var_120]
0x1800216af  call    ??0?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy> const &)
0x1800216b4  nop
0x1800216b5  mov     rax, [rsp+168h+var_120]
0x1800216ba  mov     [rax+118h], edi
0x1800216c0  mov     [rax+11Ch], r14d
0x1800216c7  lea     rcx, [rsp+168h+var_120]
0x1800216cc  call    ?close@?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::close(void)
0x1800216d1  sub     edi, 4
0x1800216d4  jz      loc_1800218EC
0x1800216da  sub     edi, 1
0x1800216dd  jz      loc_1800218AD
0x1800216e3  sub     edi, 1
0x1800216e6  jz      short loc_1800216F1
0x1800216e8  cmp     edi, 1
0x1800216eb  jnz     loc_1800218F8
0x1800216f1  mov     eax, [rbx+60h]
0x1800216f4  dec     eax
0x1800216f6  cmp     eax, 1
0x1800216f9  ja      loc_1800218F8
0x1800216ff  cmp     dword ptr [rbx+64h], 0
0x180021703  jbe     short loc_18002175E
0x180021705  lea     rcx, [rbx+0D8h]
0x18002170c  mov     qword ptr [rcx+10h], 0
0x180021714  cmp     qword ptr [rcx+18h], 7
0x180021719  jbe     short loc_18002171E
0x18002171b  mov     rcx, [rcx]
0x18002171e  xor     eax, eax
0x180021720  mov     [rcx], ax
0x180021723  mov     r9d, [rbx+64h]
0x180021727  lea     r8, aFailedToFinish; "Failed to finish Discovery, %d retries "...
0x18002172e  mov     edx, 185h; unsigned int
0x180021733  mov     rcx, rsi; char *
0x180021736  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18002173b  mov     dword ptr [rbx+60h], 0
0x180021742  mov     rcx, rbx
0x180021745  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x18002174a  dec     dword ptr [rbx+64h]
0x18002174d  mov     dl, [rsp+168h+var_128]
0x180021751  mov     rcx, rbx
0x180021754  call    ?AttemptDiscovery@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDiscovery(wil::write_lock_required)
0x180021759  jmp     loc_1800218AB
0x18002175e  xor     edx, edx; Val
0x180021760  mov     r8d, 81h; Size
0x180021766  lea     rcx, [rsp+168h+var_C8]; void *
0x18002176e  call    memset_0
0x180021773  mov     rcx, [rbx+68h]; this
0x180021777  xor     edx, edx
0x180021779  lock xadd [rcx+88h], rdx; unsigned __int64
0x180021782  lea     r8, [rsp+168h+var_C8]; char *
0x18002178a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002178f  mov     rcx, rbx
0x180021792  call    ?GetAvailableConnectivityTypesForTelemetry@OobeEasyConnectTask@@AEAA?AW4AvailableConnectivity@@Uwrite_lock_required@wil@@@Z; OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(wil::write_lock_required)
0x180021797  mov     r10d, eax
0x18002179a  lea     rdi, [rbx+0D8h]
0x1800217a1  cmp     qword ptr [rbx+498h], 0
0x1800217a9  jnz     short loc_1800217B4
0x1800217ab  lea     rcx, a00000000; "00000000"
0x1800217b2  jmp     short loc_1800217C3
0x1800217b4  cmp     qword ptr [rdi+18h], 7
0x1800217b9  jbe     short loc_1800217C0
0x1800217bb  mov     rcx, [rdi]
0x1800217be  jmp     short loc_1800217C3
0x1800217c0  mov     rcx, rdi
0x1800217c3  mov     r8b, [rbx+70h]
0x1800217c7  lea     r9, [rbx+226h]
0x1800217ce  cmp     dword ptr [rbx+60h], 1
0x1800217d2  jnz     short loc_1800217DD
0x1800217d4  lea     rdx, aDiscovery; "Discovery"
0x1800217db  jmp     short loc_1800217F3
0x1800217dd  lea     rdx, aDownloading; "Downloading"
0x1800217e4  lea     rax, aOther; "Other"
0x1800217eb  cmp     dword ptr [rbx+60h], 2
0x1800217ef  cmovnz  rdx, rax
0x1800217f3  mov     [rsp+168h+var_130], r10d
0x1800217f8  mov     [rsp+168h+var_138], rcx
0x1800217fd  mov     byte ptr [rsp+168h+var_140], r8b
0x180021802  mov     [rsp+168h+var_148], r9
0x180021807  mov     r9d, r14d
0x18002180a  mov     r8d, r15d
0x18002180d  lea     rcx, [rsp+168h+var_C8]
0x180021815  call    ?OperatorDiscoveryCompleted@MBSettingUXLogging@@SAXPEBDPEBGJK1_N1W4AvailableConnectivity@@@Z; MBSettingUXLogging::OperatorDiscoveryCompleted(char const *,ushort const *,long,ulong,ushort const *,bool,ushort const *,AvailableConnectivity)
0x18002181a  mov     qword ptr [rdi+10h], 0
0x180021822  cmp     qword ptr [rdi+18h], 7
0x180021827  jbe     short loc_18002182C
0x180021829  mov     rdi, [rdi]
0x18002182c  xor     eax, eax
0x18002182e  mov     [rdi], ax
0x180021831  lea     r8, aMaxNumberOfDis; "Max number of discovery attempts reache"...
0x180021838  mov     edx, 19Ch; unsigned int
0x18002183d  mov     rcx, rsi; char *
0x180021840  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180021845  mov     rcx, rsi; char *
0x180021848  cmp     byte ptr [rbx+0A8h], 0
0x18002184f  jz      short loc_18002187F
0x180021851  lea     r8, aChangingStateT_5; "Changing state to WaitingForCorrectStat"...
0x180021858  mov     edx, 19Fh; unsigned int
0x18002185d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021862  mov     dword ptr [rbx+60h], 3
0x180021869  mov     rcx, rbx
0x18002186c  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180021871  mov     dl, [rsp+168h+var_128]
0x180021875  mov     rcx, rbx
0x180021878  call    ?AttemptDeleteBootstrapProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDeleteBootstrapProfile(wil::write_lock_required)
0x18002187d  jmp     short loc_1800218AB
0x18002187f  lea     r8, aChangingStateT_0; "Changing state to WaitingForCorrectStat"...
0x180021886  mov     edx, 1A5h; unsigned int
0x18002188b  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021890  mov     dword ptr [rbx+60h], 4
0x180021897  mov     rcx, rbx
0x18002189a  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x18002189f  mov     dl, [rsp+168h+var_128]
0x1800218a3  mov     rcx, rbx
0x1800218a6  call    ?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)
0x1800218ab  jmp     short loc_1800218F8
0x1800218ad  lea     r8, aFailedToActiva; "Failed to Activate profile"
0x1800218b4  mov     edx, 1AFh; unsigned int
0x1800218b9  mov     rcx, rsi; char *
0x1800218bc  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x1800218c1  cmp     dword ptr [rbx+60h], 4
0x1800218c5  jnz     short loc_1800218F8
0x1800218c7  lea     r8, aChangingStateT_4; "Changing state to Error"
0x1800218ce  mov     edx, 1B2h; unsigned int
0x1800218d3  mov     rcx, rsi; char *
0x1800218d6  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800218db  mov     dword ptr [rbx+60h], 7
0x1800218e2  mov     rcx, rbx
0x1800218e5  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x1800218ea  jmp     short loc_1800218F8
0x1800218ec  mov     edx, r14d; unsigned int
0x1800218ef  mov     ecx, r15d; int
0x1800218f2  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x1800218f7  nop
0x1800218f8  jmp     loc_180021AA4
0x1800218fd  sub     edi, 4
0x180021900  jz      loc_180021AB0
0x180021906  sub     edi, 2
0x180021909  jz      loc_180021A63
0x18002190f  sub     edi, 1
0x180021912  jz      short loc_180021922
0x180021914  cmp     edi, 3
0x180021917  jnz     loc_180021ABC
0x18002191d  jmp     loc_1800219D9
0x180021922  xor     edx, edx; Val
0x180021924  mov     r8d, 81h; Size
0x18002192a  lea     rcx, [rsp+168h+var_C8]; void *
0x180021932  call    memset_0
0x180021937  mov     rcx, [rbx+68h]; this
0x18002193b  xor     edx, edx
0x18002193d  lock xadd [rcx+88h], rdx; unsigned __int64
0x180021946  lea     r8, [rsp+168h+var_C8]; char *
0x18002194e  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180021953  mov     rcx, rbx
0x180021956  call    ?GetAvailableConnectivityTypesForTelemetry@OobeEasyConnectTask@@AEAA?AW4AvailableConnectivity@@Uwrite_lock_required@wil@@@Z; OobeEasyConnectTask::GetAvailableConnectivityTypesForTelemetry(wil::write_lock_required)
0x18002195b  mov     r10d, eax
0x18002195e  cmp     qword ptr [rbx+498h], 0
0x180021966  jnz     short loc_180021971
0x180021968  lea     rcx, a00000000; "00000000"
0x18002196f  jmp     short loc_180021982
0x180021971  lea     rcx, [rbx+0D8h]
0x180021978  cmp     qword ptr [rcx+18h], 7
0x18002197d  jbe     short loc_180021982
0x18002197f  mov     rcx, [rcx]
0x180021982  mov     r8b, [rbx+70h]
0x180021986  lea     r9, [rbx+226h]
0x18002198d  cmp     dword ptr [rbx+60h], 1
0x180021991  jnz     short loc_18002199C
0x180021993  lea     rdx, aDiscovery; "Discovery"
0x18002199a  jmp     short loc_1800219B2
0x18002199c  lea     rdx, aDownloading; "Downloading"
0x1800219a3  lea     rax, aOther; "Other"
0x1800219aa  cmp     dword ptr [rbx+60h], 2
0x1800219ae  cmovnz  rdx, rax
0x1800219b2  mov     [rsp+168h+var_130], r10d
0x1800219b7  mov     [rsp+168h+var_138], rcx
0x1800219bc  mov     byte ptr [rsp+168h+var_140], r8b
0x1800219c1  mov     [rsp+168h+var_148], r9
0x1800219c6  mov     r9d, r14d
0x1800219c9  mov     r8d, r15d
0x1800219cc  lea     rcx, [rsp+168h+var_C8]
0x1800219d4  call    ?OperatorDiscoveryCompleted@MBSettingUXLogging@@SAXPEBDPEBGJK1_N1W4AvailableConnectivity@@@Z; MBSettingUXLogging::OperatorDiscoveryCompleted(char const *,ushort const *,long,ulong,ushort const *,bool,ushort const *,AvailableConnectivity)
0x1800219d9  lea     r8, aDiscoveryCompl; "Discovery Complete/Cancelled"
0x1800219e0  mov     edx, 1E2h; unsigned int
0x1800219e5  mov     rcx, rsi; char *
0x1800219e8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800219ed  mov     eax, [rbx+60h]
0x1800219f0  dec     eax
0x1800219f2  cmp     eax, 2
0x1800219f5  ja      loc_180021ABC
0x1800219fb  mov     rcx, rsi; char *
0x1800219fe  cmp     byte ptr [rbx+0A8h], 0
0x180021a05  jz      short loc_180021A35
0x180021a07  lea     r8, aChangingStateT_5; "Changing state to WaitingForCorrectStat"...
0x180021a0e  mov     edx, 1E7h; unsigned int
0x180021a13  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021a18  mov     dword ptr [rbx+60h], 3
0x180021a1f  mov     rcx, rbx
0x180021a22  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180021a27  mov     dl, [rsp+168h+var_128]
0x180021a2b  mov     rcx, rbx
0x180021a2e  call    ?AttemptDeleteBootstrapProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDeleteBootstrapProfile(wil::write_lock_required)
0x180021a33  jmp     short loc_180021A61
0x180021a35  lea     r8, aChangingStateT_0; "Changing state to WaitingForCorrectStat"...
0x180021a3c  mov     edx, 1EDh; unsigned int
0x180021a41  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021a46  mov     dword ptr [rbx+60h], 4
0x180021a4d  mov     rcx, rbx
0x180021a50  call    ?PublishCurrentTaskStateWnf@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::PublishCurrentTaskStateWnf(wil::write_lock_required)
0x180021a55  mov     dl, [rsp+168h+var_128]
0x180021a59  mov     rcx, rbx
0x180021a5c  call    ?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)
0x180021a61  jmp     short loc_180021ABC
0x180021a63  lea     rdx, [rbx+0D8h]
0x180021a6a  lea     rcx, [rbx+488h]
0x180021a71  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180021a76  mov     dl, [rsp+168h+var_128]
0x180021a7a  mov     rcx, rbx
0x180021a7d  call    ?AttemptEnableDownloadedProfile@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptEnableDownloadedProfile(wil::write_lock_required)
0x180021a82  inc     dword ptr [rbx+4B0h]
0x180021a88  mov     ebx, [rbx+4B0h]
0x180021a8e  lea     rdx, [rsp+168h+var_120]
0x180021a93  mov     rcx, r12
0x180021a96  call    ??C?$tip_test@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::operator->(void)
0x180021a9b  mov     rcx, [rax]
0x180021a9e  mov     [rcx+120h], ebx
0x180021aa4  lea     rcx, [rsp+168h+var_120]
0x180021aa9  call    ??1?$test_data_control@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_data_control<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(void)
0x180021aae  jmp     short loc_180021ABC
0x180021ab0  mov     edx, r14d; unsigned int
0x180021ab3  mov     ecx, r15d; int
0x180021ab6  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x180021abb  nop
0x180021abc  lea     rcx, [rsp+168h+var_108]
0x180021ac1  call    ??1?$test_watcher@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::~test_watcher<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>(void)
0x180021ac6  nop
0x180021ac7  lea     rcx, [rsp+168h+var_118]
0x180021acc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
  ... truncated ...
```
