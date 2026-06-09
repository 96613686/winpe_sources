# TaskSchedulerSignalFactory::RegisterTask(TimeSignal::Time const &,TimeSignal::Repeat,short,Microsoft::WRL::ComPtr<ITaskFolder>,_bstr_t const &)

- ea: `0x18002bfac`
- end: `0x18002c7f8`
- name: `?RegisterTask@TaskSchedulerSignalFactory@@AEAAJAEBUTime@TimeSignal@@W4Repeat@3@FV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV_bstr_t@@@Z`
- size: `2124`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned __int16, __int64 *, __int64 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029cf0`
- `0x18002a584`

## callees

- `0x18000a7d0`
- `0x180014e7c`
- `0x18001f634`
- `0x18002072c`
- `0x180029630`
- `0x180029958`
- `0x18002bd10`
- `0x18002be88`
- `0x18002bfac`
- `0x18002cafc`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002c681`
- `OLEAUT32!__imp_VariantInit` at `0x18002c695`
- `OLEAUT32!__imp_VariantInit` at `0x18002c681`
- `OLEAUT32!__imp_VariantInit` at `0x18002c695`
- `OLEAUT32!__imp_VariantClear` at `0x18002c72e`
- `OLEAUT32!__imp_VariantClear` at `0x18002c739`
- `OLEAUT32!__imp_VariantClear` at `0x18002c744`
- `OLEAUT32!__imp_VariantClear` at `0x18002c72e`
- `OLEAUT32!__imp_VariantClear` at `0x18002c739`
- `OLEAUT32!__imp_VariantClear` at `0x18002c744`

## string_xrefs

- `0x18002c0ff`: `taskService->NewTask(0, &task)`
- `0x18002c13e`: `task->get_Settings(&taskSettings)`
- `0x18002c166`: `taskSettings->put_Enabled(VARIANT_TRUE)`
- `0x18002c18b`: `taskSettings->put_DisallowStartIfOnBatteries(VARIANT_FALSE)`
- `0x18002c1b3`: `taskSettings->put_StopIfGoingOnBatteries(VARIANT_FALSE)`
- `0x18002c1db`: `taskSettings->put_RunOnlyIfIdle(VARIANT_FALSE)`
- `0x18002c207`: `taskSettings->put_MultipleInstances(TASK_INSTANCES_STOP_EXISTING)`
- `0x18002c22f`: `taskSettings->put_WakeToRun(VARIANT_FALSE)`
- `0x18002c257`: `taskSettings->put_StartWhenAvailable(VARIANT_TRUE)`
- `0x18002c28d`: `task->get_Triggers(&triggerCollection)`
- `0x18002c2d1`: `triggerCollection->Create(TASK_TRIGGER_WEEKLY, &trigger)`
- `0x18002c43d`: `triggerCollection->Create(TASK_TRIGGER_DAILY, &trigger)`
- `0x18002c517`: `trigger->put_Id(taskName)`
- `0x18002c579`: `task->get_Actions(&actionCollection)`
- `0x18002c5b7`: `actionCollection->Create(TASK_ACTION_COM_HANDLER, &action)`
- `0x18002c5f4`: `action->QueryInterface(IID_PPV_ARGS(&comAction))`
- `0x18002c61e`: `comAction->put_ClassId(_CRT_WIDE(NATURAL_AUTH_TIMER_COM_TASK_UUID))`
- `0x18002c653`: `comAction->put_Data(taskName)`
- `0x18002c750`: `folder->RegisterTaskDefinition( taskName, task.Get(), TASK_CREATE_OR_UPDATE, _variant_t(L"SYSTEM"), _variant_t(), TASK_LOGON_SERVICE_ACCOUNT, _variant_t(), &registeredTask)`

## pseudocode

```c
__int64 __fastcall TaskSchedulerSignalFactory::RegisterTask(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int16 a4,
        __int64 *a5,
        __int64 **a6)
{
  __int64 **v10; // rsi
  __int64 v11; // r9
  __int64 v12; // rbx
  int (__fastcall *v13)(__int64, __int64, __int64 *); // rdi
  __int64 v14; // rdx
  int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  int v18; // eax
  const char *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 ***); // rbx
  int v29; // eax
  const char *v30; // rcx
  __int64 *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 *v34; // rbx
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 *); // rbx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v47; // rdx
  __int64 v48; // rbx
  __int64 (__fastcall *v49)(__int64, __int64 *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rdi
  __int128 v50; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v52; // xmm8
  IRecordInfo *v53; // xmm9_8
  _variant_t *v54; // rax
  __int64 *v55; // rdx
  __int64 v57; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 ***); // [rsp+60h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v60; // [rsp+70h] [rbp-98h] BYREF
  __int64 v61; // [rsp+78h] [rbp-90h] BYREF
  __int64 v62; // [rsp+80h] [rbp-88h] BYREF
  __int64 v63; // [rsp+88h] [rbp-80h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-78h] BYREF
  __int64 v65; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v66[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v67[8]; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v68; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v70; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v71; // [rsp+F8h] [rbp-10h]
  __int128 v72; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v73; // [rsp+118h] [rbp+10h]
  __int128 v74; // [rsp+128h] [rbp+20h] BYREF
  __int64 v75; // [rsp+138h] [rbp+30h]
  VARIANTARG v76; // [rsp+148h] [rbp+40h] BYREF

  v60 = 0;
  v59 = 0;
  v63 = 0;
  v58 = 0;
  v65 = 0;
  v64 = 0;
  v62 = 0;
  v61 = 0;
  v57 = 0;
  v10 = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *a6 )
      v11 = **a6;
    else
      v11 = 0;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, v11);
  }
  v12 = *a5;
  v13 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a5 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  if ( *v10 )
    v14 = **v10;
  else
    v14 = 0;
  if ( v13(v12, v14, &v61) < 0 )
  {
    v16 = *(_QWORD *)(a1 + 8);
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    v18 = v17(v16, 0, &v59);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskService->NewTask(0, &task)";
      goto LABEL_17;
    }
    v21 = v59;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    v18 = v22(v21, &v57);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "task->get_Settings(&taskSettings)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 240LL))(v57, 0xFFFFFFFFLL);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_Enabled(VARIANT_TRUE)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 144LL))(v57, 0);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_DisallowStartIfOnBatteries(VARIANT_FALSE)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 128LL))(v57, 0);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_StopIfGoingOnBatteries(VARIANT_FALSE)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 336LL))(v57, 0);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_RunOnlyIfIdle(VARIANT_FALSE)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 112LL))(v57, 3);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_MultipleInstances(TASK_INSTANCES_STOP_EXISTING)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 352LL))(v57, 0);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_WakeToRun(VARIANT_FALSE)";
      goto LABEL_17;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 176LL))(v57, 0xFFFFFFFFLL);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "taskSettings->put_StartWhenAvailable(VARIANT_TRUE)";
      goto LABEL_17;
    }
    v23 = v59;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
    v18 = v24(v23, &v63);
    v15 = v18;
    if ( v18 < 0 )
    {
      v19 = "task->get_Triggers(&triggerCollection)";
      goto LABEL_17;
    }
    v25 = v63;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v63 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    if ( a3 == 1 )
    {
      v18 = v26(v25, 3, &v58);
      v15 = v18;
      if ( v18 < 0 )
      {
        v19 = "triggerCollection->Create(TASK_TRIGGER_WEEKLY, &trigger)";
        goto LABEL_17;
      }
      a6 = 0;
      v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v58;
      v28 = **v58;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a6);
      v29 = v28(v27, &GUID_5038fc98_82ff_436d_8728_a512a57c9dc1, &a6);
      v15 = v29;
      if ( v29 < 0 )
      {
        v30 = "trigger->QueryInterface(IID_PPV_ARGS(&weeklyTrigger))";
LABEL_42:
        LogOpFailure(v30, (unsigned int)v29);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a6);
        goto LABEL_96;
      }
      v29 = ((__int64 (__fastcall *)(__int64 **, _QWORD))(*a6)[21])(a6, a4);
      v15 = v29;
      if ( v29 < 0 )
      {
        v30 = "weeklyTrigger->put_DaysOfWeek(dayBit)";
        goto LABEL_42;
      }
      v29 = ((__int64 (__fastcall *)(__int64 **, __int64))(*a6)[23])(a6, 1);
      v15 = v29;
      if ( v29 < 0 )
      {
        v30 = "weeklyTrigger->put_WeeksInterval(1)";
        goto LABEL_42;
      }
      v31 = *(__int64 **)TaskSchedulerSignalFactory::GetWeeklyStartDay(v67, a4);
      if ( v31 )
        v32 = *v31;
      else
        v32 = 0;
      v33 = TaskSchedulerSignalFactory::Stringify(v31, v66, v32, a2);
      _bstr_t::operator=(&v60, v33);
      _bstr_t::_Free((_bstr_t *)v66);
      _bstr_t::_Free((_bstr_t *)v67);
      v34 = v60;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( v60 )
          v35 = *v60;
        else
          v35 = 0;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, v35);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&a6);
    }
    else
    {
      v18 = v26(v25, 2, &v58);
      v15 = v18;
      if ( v18 < 0 )
      {
        v19 = "triggerCollection->Create(TASK_TRIGGER_DAILY, &trigger)";
        goto LABEL_17;
      }
      v37 = TaskSchedulerSignalFactory::Stringify(v36, &a6, L"2000-01-01", a2);
      _bstr_t::operator=(&v60, v37);
      _bstr_t::_Free((_bstr_t *)&a6);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v34 = v60;
      }
      else
      {
        v34 = v60;
        if ( v60 )
          v38 = *v60;
        else
          v38 = 0;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, v38);
      }
    }
    if ( v34 )
      v39 = *v34;
    else
      v39 = 0;
    v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 ***), __int64))(*v58)[15])(v58, v39);
    v15 = v18;
    if ( v18 >= 0 )
    {
      if ( *v10 )
        v40 = **v10;
      else
        v40 = 0;
      v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 ***), __int64))(*v58)[9])(
              v58,
              v40);
      v15 = v18;
      if ( v18 >= 0 )
      {
        v18 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 ***), __int64))(*v58)[19])(
                v58,
                0xFFFFFFFFLL);
        v15 = v18;
        if ( v18 >= 0 )
        {
          v41 = v59;
          v42 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 136LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
          v18 = v42(v41, &v65);
          v15 = v18;
          if ( v18 >= 0 )
          {
            v43 = v65;
            v44 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v65 + 96LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
            v18 = v44(v43, 5, &v64);
            v15 = v18;
            if ( v18 >= 0 )
            {
              v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v64;
              v46 = **v64;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
              v18 = v46(v45, &GUID_6d2fd252_75c5_4f66_90ba_2a7d8cc3039f, &v62);
              v15 = v18;
              if ( v18 >= 0 )
              {
                v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v62 + 88LL))(
                        v62,
                        L"5BBEE68B-389E-4B6A-813D-BEBDAB09E6EE");
                v15 = v18;
                if ( v18 >= 0 )
                {
                  if ( *v10 )
                    v47 = **v10;
                  else
                    v47 = 0;
                  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 104LL))(v62, v47);
                  v15 = v18;
                  if ( v18 >= 0 )
                  {
                    v48 = *a5;
                    v49 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)*a5 + 136LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
                    VariantInit(&pvarg);
                    v50 = *(_OWORD *)&pvarg.vt;
                    pRecInfo = pvarg.pRecInfo;
                    VariantInit(&v68);
                    v52 = *(_OWORD *)&v68.vt;
                    v53 = v68.pRecInfo;
                    v54 = _variant_t::_variant_t((_variant_t *)&v76, L"SYSTEM");
                    v55 = *v10;
                    if ( *v10 )
                      v55 = (__int64 *)*v55;
                    v70 = v50;
                    v71 = pRecInfo;
                    v72 = v52;
                    v73 = v53;
                    v74 = *(_OWORD *)v54;
                    v75 = *((_QWORD *)v54 + 2);
                    v15 = v49(v48, v55, v59, 6, &v74, &v72, 5, &v70, &v61);
                    VariantClear(&v76);
                    VariantClear(&v68);
                    VariantClear(&pvarg);
                    if ( v15 >= 0 )
                    {
                      v15 = 0;
                      goto LABEL_96;
                    }
                    v20 = (unsigned int)v15;
                    v19 = "folder->RegisterTaskDefinition( taskName, task.Get(), TASK_CREATE_OR_UPDATE, _variant_t(L\"SYS"
                          "TEM\"), _variant_t(), TASK_LOGON_SERVICE_ACCOUNT, _variant_t(), &registeredTask)";
                    goto LABEL_18;
                  }
                  v19 = "comAction->put_Data(taskName)";
                }
                else
                {
                  v19 = "comAction->put_ClassId(_CRT_WIDE(NATURAL_AUTH_TIMER_COM_TASK_UUID))";
                }
              }
              else
              {
                v19 = "action->QueryInterface(IID_PPV_ARGS(&comAction))";
              }
            }
            else
            {
              v19 = "actionCollection->Create(TASK_ACTION_COM_HANDLER, &action)";
            }
          }
          else
          {
            v19 = "task->get_Actions(&actionCollection)";
          }
        }
        else
        {
          v19 = "trigger->put_Enabled(VARIANT_TRUE)";
        }
      }
      else
      {
        v19 = "trigger->put_Id(taskName)";
      }
    }
    else
    {
      v19 = "trigger->put_StartBoundary(dateString)";
    }
LABEL_17:
    v20 = (unsigned int)v18;
LABEL_18:
    LogOpFailure(v19, v20);
    goto LABEL_96;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids);
  v15 = -2147024844;
LABEL_96:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  _bstr_t::_Free((_bstr_t *)&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a5);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002bfac  mov     rax, rsp
0x18002bfaf  push    rbp
0x18002bfb0  push    rbx
0x18002bfb1  push    rsi
0x18002bfb2  push    rdi
0x18002bfb3  push    r12
0x18002bfb5  push    r13
0x18002bfb7  push    r14
0x18002bfb9  push    r15
0x18002bfbb  lea     rbp, [rax-0E8h]
0x18002bfc2  sub     rsp, 1A8h
0x18002bfc9  movaps  xmmword ptr [rax-58h], xmm6
0x18002bfcd  movaps  xmmword ptr [rax-68h], xmm7
0x18002bfd1  movaps  xmmword ptr [rax-78h], xmm8
0x18002bfd6  movaps  xmmword ptr [rax-88h], xmm9
0x18002bfde  movzx   r15d, r9w
0x18002bfe2  mov     r12d, r8d
0x18002bfe5  mov     r13, rdx
0x18002bfe8  mov     r14, rcx
0x18002bfeb  xor     edx, edx
0x18002bfed  mov     [rsp+1E0h+var_178], rdx
0x18002bff2  mov     [rsp+1E0h+var_180], rdx
0x18002bff7  mov     [rbp+0E0h+var_160], rdx
0x18002bffb  mov     [rsp+1E0h+var_188], rdx
0x18002c000  mov     [rbp+0E0h+var_150], rdx
0x18002c004  mov     [rbp+0E0h+var_158], rdx
0x18002c008  mov     [rsp+1E0h+var_168], rdx
0x18002c00d  mov     [rsp+1E0h+var_170], rdx
0x18002c012  mov     [rsp+1E0h+var_190], rdx
0x18002c017  lea     rax, WPP_GLOBAL_Control
0x18002c01e  mov     rsi, [rbp+0E0h+arg_28]
0x18002c025  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c02c  cmp     rcx, rax
0x18002c02f  jz      short loc_18002C05C
0x18002c031  test    byte ptr [rcx+1Ch], 4
0x18002c035  jz      short loc_18002C05C
0x18002c037  mov     rax, [rsi]
0x18002c03a  test    rax, rax
0x18002c03d  jz      short loc_18002C044
0x18002c03f  mov     r9, [rax]
0x18002c042  jmp     short loc_18002C047
0x18002c044  mov     r9, rdx
0x18002c047  mov     edx, 1Ch
0x18002c04c  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002c053  mov     rcx, [rcx+10h]
0x18002c057  call    WPP_SF_S
0x18002c05c  mov     rbx, [rbp+0E0h+arg_20]
0x18002c063  mov     rbx, [rbx]
0x18002c066  mov     rax, [rbx]
0x18002c069  mov     rdi, [rax+68h]
0x18002c06d  lea     rcx, [rsp+1E0h+var_170]
0x18002c072  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c077  mov     rax, [rsi]
0x18002c07a  test    rax, rax
0x18002c07d  jz      short loc_18002C084
0x18002c07f  mov     rdx, [rax]
0x18002c082  jmp     short loc_18002C086
0x18002c084  xor     edx, edx
0x18002c086  lea     r8, [rsp+1E0h+var_170]
0x18002c08b  mov     rcx, rbx
0x18002c08e  mov     rax, rdi
0x18002c091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c096  test    eax, eax
0x18002c098  js      short loc_18002C0D2
0x18002c09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0a1  lea     rax, WPP_GLOBAL_Control
0x18002c0a8  cmp     rcx, rax
0x18002c0ab  jz      short loc_18002C0C8
0x18002c0ad  test    byte ptr [rcx+1Ch], 1
0x18002c0b1  jz      short loc_18002C0C8
0x18002c0b3  mov     edx, 1Dh
0x18002c0b8  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002c0bf  mov     rcx, [rcx+10h]
0x18002c0c3  call    WPP_SF_
0x18002c0c8  mov     ebx, 80070034h
0x18002c0cd  jmp     loc_18002C75E
0x18002c0d2  mov     rdi, [r14+8]
0x18002c0d6  mov     rax, [rdi]
0x18002c0d9  mov     rbx, [rax+48h]
0x18002c0dd  lea     rcx, [rsp+1E0h+var_180]
0x18002c0e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c0e7  lea     r8, [rsp+1E0h+var_180]
0x18002c0ec  xor     edx, edx
0x18002c0ee  mov     rcx, rdi
0x18002c0f1  mov     rax, rbx
0x18002c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0f9  mov     ebx, eax
0x18002c0fb  test    eax, eax
0x18002c0fd  jns     short loc_18002C112
0x18002c0ff  lea     rcx, aTaskserviceNew; "taskService->NewTask(0, &task)"
0x18002c106  mov     edx, eax
0x18002c108  call    LogOpFailure
0x18002c10d  jmp     loc_18002C75E
0x18002c112  mov     rdi, [rsp+1E0h+var_180]
0x18002c117  mov     rax, [rdi]
0x18002c11a  mov     rbx, [rax+58h]
0x18002c11e  lea     rcx, [rsp+1E0h+var_190]
0x18002c123  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c128  lea     rdx, [rsp+1E0h+var_190]
0x18002c12d  mov     rcx, rdi
0x18002c130  mov     rax, rbx
0x18002c133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c138  mov     ebx, eax
0x18002c13a  test    eax, eax
0x18002c13c  jns     short loc_18002C147
0x18002c13e  lea     rcx, aTaskGetSetting; "task->get_Settings(&taskSettings)"
0x18002c145  jmp     short loc_18002C106
0x18002c147  mov     rcx, [rsp+1E0h+var_190]
0x18002c14c  mov     rax, [rcx]
0x18002c14f  or      edi, 0FFFFFFFFh
0x18002c152  mov     edx, edi
0x18002c154  mov     rax, [rax+0F0h]
0x18002c15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c160  mov     ebx, eax
0x18002c162  test    eax, eax
0x18002c164  jns     short loc_18002C16F
0x18002c166  lea     rcx, aTasksettingsPu_3; "taskSettings->put_Enabled(VARIANT_TRUE)"
0x18002c16d  jmp     short loc_18002C106
0x18002c16f  mov     rcx, [rsp+1E0h+var_190]
0x18002c174  mov     rax, [rcx]
0x18002c177  xor     edx, edx
0x18002c179  mov     rax, [rax+90h]
0x18002c180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c185  mov     ebx, eax
0x18002c187  test    eax, eax
0x18002c189  jns     short loc_18002C197
0x18002c18b  lea     rcx, aTasksettingsPu_4; "taskSettings->put_DisallowStartIfOnBatt"...
0x18002c192  jmp     loc_18002C106
0x18002c197  mov     rcx, [rsp+1E0h+var_190]
0x18002c19c  mov     rax, [rcx]
0x18002c19f  xor     edx, edx
0x18002c1a1  mov     rax, [rax+80h]
0x18002c1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ad  mov     ebx, eax
0x18002c1af  test    eax, eax
0x18002c1b1  jns     short loc_18002C1BF
0x18002c1b3  lea     rcx, aTasksettingsPu_0; "taskSettings->put_StopIfGoingOnBatterie"...
0x18002c1ba  jmp     loc_18002C106
0x18002c1bf  mov     rcx, [rsp+1E0h+var_190]
0x18002c1c4  mov     rax, [rcx]
0x18002c1c7  xor     edx, edx
0x18002c1c9  mov     rax, [rax+150h]
0x18002c1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1d5  mov     ebx, eax
0x18002c1d7  test    eax, eax
0x18002c1d9  jns     short loc_18002C1E7
0x18002c1db  lea     rcx, aTasksettingsPu_1; "taskSettings->put_RunOnlyIfIdle(VARIANT"...
0x18002c1e2  jmp     loc_18002C106
0x18002c1e7  mov     rcx, [rsp+1E0h+var_190]
0x18002c1ec  mov     rax, [rcx]
0x18002c1ef  mov     r14d, 3
0x18002c1f5  mov     edx, r14d
0x18002c1f8  mov     rax, [rax+70h]
0x18002c1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c201  mov     ebx, eax
0x18002c203  test    eax, eax
0x18002c205  jns     short loc_18002C213
0x18002c207  lea     rcx, aTasksettingsPu_2; "taskSettings->put_MultipleInstances(TAS"...
0x18002c20e  jmp     loc_18002C106
0x18002c213  mov     rcx, [rsp+1E0h+var_190]
0x18002c218  mov     rax, [rcx]
0x18002c21b  xor     edx, edx
0x18002c21d  mov     rax, [rax+160h]
0x18002c224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c229  mov     ebx, eax
0x18002c22b  test    eax, eax
0x18002c22d  jns     short loc_18002C23B
0x18002c22f  lea     rcx, aTasksettingsPu; "taskSettings->put_WakeToRun(VARIANT_FAL"...
0x18002c236  jmp     loc_18002C106
0x18002c23b  mov     rcx, [rsp+1E0h+var_190]
0x18002c240  mov     rax, [rcx]
0x18002c243  mov     edx, edi
0x18002c245  mov     rax, [rax+0B0h]
0x18002c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c251  mov     ebx, eax
0x18002c253  test    eax, eax
0x18002c255  jns     short loc_18002C263
0x18002c257  lea     rcx, aTasksettingsPu_5; "taskSettings->put_StartWhenAvailable(VA"...
0x18002c25e  jmp     loc_18002C106
0x18002c263  mov     rdi, [rsp+1E0h+var_180]
0x18002c268  mov     rax, [rdi]
0x18002c26b  mov     rbx, [rax+48h]
0x18002c26f  lea     rcx, [rbp+0E0h+var_160]
0x18002c273  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c278  lea     rdx, [rbp+0E0h+var_160]
0x18002c27c  mov     rcx, rdi
0x18002c27f  mov     rax, rbx
0x18002c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c287  mov     ebx, eax
0x18002c289  test    eax, eax
0x18002c28b  jns     short loc_18002C299
0x18002c28d  lea     rcx, aTaskGetTrigger; "task->get_Triggers(&triggerCollection)"
0x18002c294  jmp     loc_18002C106
0x18002c299  mov     rdi, [rbp+0E0h+var_160]
0x18002c29d  lea     rcx, [rsp+1E0h+var_188]
0x18002c2a2  mov     rax, [rdi]
0x18002c2a5  mov     rbx, [rax+50h]
0x18002c2a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c2ae  lea     r8, [rsp+1E0h+var_188]
0x18002c2b3  mov     rcx, rdi
0x18002c2b6  mov     rax, rbx
0x18002c2b9  cmp     r12d, 1
0x18002c2bd  jnz     loc_18002C42D
0x18002c2c3  mov     edx, r14d
0x18002c2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2cb  mov     ebx, eax
0x18002c2cd  test    eax, eax
0x18002c2cf  jns     short loc_18002C2DD
0x18002c2d1  lea     rcx, aTriggercollect; "triggerCollection->Create(TASK_TRIGGER_"...
0x18002c2d8  jmp     loc_18002C106
0x18002c2dd  mov     [rbp+0E0h+arg_28], 0
0x18002c2e8  mov     rdi, [rsp+1E0h+var_188]
0x18002c2ed  mov     rax, [rdi]
0x18002c2f0  mov     rbx, [rax]
0x18002c2f3  lea     rcx, [rbp+0E0h+arg_28]
0x18002c2fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c2ff  lea     r8, [rbp+0E0h+arg_28]
0x18002c306  lea     rdx, _GUID_5038fc98_82ff_436d_8728_a512a57c9dc1
0x18002c30d  mov     rcx, rdi
0x18002c310  mov     rax, rbx
0x18002c313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c318  mov     ebx, eax
0x18002c31a  test    eax, eax
0x18002c31c  jns     short loc_18002C33E
0x18002c31e  lea     rcx, aTriggerQueryin; "trigger->QueryInterface(IID_PPV_ARGS(&w"...
0x18002c325  mov     edx, eax
0x18002c327  call    LogOpFailure
0x18002c32c  nop
0x18002c32d  lea     rcx, [rbp+0E0h+arg_28]
0x18002c334  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c339  jmp     loc_18002C75E
0x18002c33e  mov     rcx, [rbp+0E0h+arg_28]
0x18002c345  mov     rax, [rcx]
0x18002c348  movzx   edx, r15w
0x18002c34c  mov     rax, [rax+0A8h]
0x18002c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c358  mov     ebx, eax
0x18002c35a  test    eax, eax
0x18002c35c  jns     short loc_18002C367
0x18002c35e  lea     rcx, aWeeklytriggerP; "weeklyTrigger->put_DaysOfWeek(dayBit)"
0x18002c365  jmp     short loc_18002C325
0x18002c367  mov     rcx, [rbp+0E0h+arg_28]
0x18002c36e  mov     rax, [rcx]
0x18002c371  mov     edx, 1
0x18002c376  mov     rax, [rax+0B8h]
0x18002c37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c382  mov     ebx, eax
0x18002c384  test    eax, eax
0x18002c386  jns     short loc_18002C391
0x18002c388  lea     rcx, aWeeklytriggerP_0; "weeklyTrigger->put_WeeksInterval(1)"
0x18002c38f  jmp     short loc_18002C325
0x18002c391  movzx   edx, r15w
0x18002c395  lea     rcx, [rbp+0E0h+var_140]
0x18002c399  call    ?GetWeeklyStartDay@TaskSchedulerSignalFactory@@CA?AV_bstr_t@@F@Z; TaskSchedulerSignalFactory::GetWeeklyStartDay(short)
0x18002c39e  nop
0x18002c39f  mov     rcx, [rax]
0x18002c3a2  test    rcx, rcx
0x18002c3a5  jz      short loc_18002C3AC
0x18002c3a7  mov     r8, [rcx]
0x18002c3aa  jmp     short loc_18002C3AF
0x18002c3ac  xor     r8d, r8d
0x18002c3af  mov     r9, r13
0x18002c3b2  lea     rdx, [rbp+0E0h+var_148]
0x18002c3b6  call    ?Stringify@TaskSchedulerSignalFactory@@AEAA?AV_bstr_t@@PEBGAEBUTime@TimeSignal@@@Z; TaskSchedulerSignalFactory::Stringify(ushort const *,TimeSignal::Time const &)
0x18002c3bb  mov     rdx, rax
0x18002c3be  lea     rcx, [rsp+1E0h+var_178]
0x18002c3c3  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18002c3c8  lea     rcx, [rbp+0E0h+var_148]; this
0x18002c3cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c3d1  nop
0x18002c3d2  lea     rcx, [rbp+0E0h+var_140]; this
0x18002c3d6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c3db  mov     rbx, [rsp+1E0h+var_178]
0x18002c3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3e7  lea     rax, WPP_GLOBAL_Control
0x18002c3ee  cmp     rcx, rax
0x18002c3f1  jz      short loc_18002C41C
0x18002c3f3  test    byte ptr [rcx+1Ch], 4
0x18002c3f7  jz      short loc_18002C41C
0x18002c3f9  test    rbx, rbx
0x18002c3fc  jz      short loc_18002C403
0x18002c3fe  mov     r9, [rbx]
0x18002c401  jmp     short loc_18002C406
0x18002c403  xor     r9d, r9d
0x18002c406  mov     edx, 1Eh
0x18002c40b  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002c412  mov     rcx, [rcx+10h]
0x18002c416  call    WPP_SF_S
0x18002c41b  nop
0x18002c41c  lea     rcx, [rbp+0E0h+arg_28]
0x18002c423  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c428  jmp     loc_18002C4BF
0x18002c42d  mov     edx, 2
0x18002c432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c437  mov     ebx, eax
0x18002c439  test    eax, eax
0x18002c43b  jns     short loc_18002C449
0x18002c43d  lea     rcx, aTriggercollect_0; "triggerCollection->Create(TASK_TRIGGER_"...
0x18002c444  jmp     loc_18002C106
0x18002c449  mov     r9, r13
  ... truncated ...
```
