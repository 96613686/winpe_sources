# TaskSchedulerSignalFactory::CreateWeekly(TimeSignal::Spec const &,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *)

- ea: `0x18002a978`
- end: `0x18002ae22`
- name: `?CreateWeekly@TaskSchedulerSignalFactory@@AEAAJAEBUSpec@TimeSignal@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@Z`
- size: `1194`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a400`

## callees

- `0x180011ea8`
- `0x180012b0c`
- `0x180014e7c`
- `0x180028a1c`
- `0x180029cf0`
- `0x18002a01c`
- `0x18002a978`
- `0x18002b17c`
- `0x18002bbac`
- `0x18002be88`
- `0x18002cda8`
- `0x180046010`

## string_xrefs

- `0x18002aa41`: `taskService->Connect({}, {}, {}, {})`
- `0x18002aa7b`: `GetTaskFolder(&folder)`
- `0x18002aaeb`: `AddWeeklyDay(taskId, folder, specification.weekly.sun, NA_TASK_SCHED_TASK_SUFFIX_SUN, TaskSchedulerSignal::SUNDAY_BIT, &taskNames)`
- `0x18002ab5c`: `AddWeeklyDay(taskId, folder, specification.weekly.mon, NA_TASK_SCHED_TASK_SUFFIX_MON, TaskSchedulerSignal::MONDAY_BIT, &taskNames)`
- `0x18002abcd`: `AddWeeklyDay(taskId, folder, specification.weekly.tue, NA_TASK_SCHED_TASK_SUFFIX_TUE, TaskSchedulerSignal::TUESDAY_BIT, &taskNames)`
- `0x18002ac3e`: `AddWeeklyDay(taskId, folder, specification.weekly.wed, NA_TASK_SCHED_TASK_SUFFIX_WED, TaskSchedulerSignal::WEDNESDAY_BIT, &taskNames)`
- `0x18002acb2`: `AddWeeklyDay(taskId, folder, specification.weekly.thu, NA_TASK_SCHED_TASK_SUFFIX_THU, TaskSchedulerSignal::THURSDAY_BIT, &taskNames)`
- `0x18002ad26`: `AddWeeklyDay(taskId, folder, specification.weekly.fri, NA_TASK_SCHED_TASK_SUFFIX_FRI, TaskSchedulerSignal::FRIDAY_BIT, &taskNames)`
- `0x18002ad9a`: `AddWeeklyDay(taskId, folder, specification.weekly.sat, NA_TASK_SCHED_TASK_SUFFIX_SAT, TaskSchedulerSignal::SATURDAY_BIT, &taskNames)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskSchedulerSignalFactory::CreateWeekly(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  int TaskFolder; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v23[4]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v24[5]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v25; // [rsp+98h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-60h]
  __int128 v27; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-40h]
  __int128 v29; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-20h]
  __int64 v31; // [rsp+148h] [rbp+40h] BYREF

  v31 = 0;
  std::vector<_bstr_t>::vector<_bstr_t>(v23);
  v23[3] = (__int64)v23;
  LOBYTE(v24[0]) = 1;
  v8 = *(_QWORD *)(a1 + 8);
  memset(&v24[1], 0, 24);
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *))(*(_QWORD *)v8 + 80LL))(
         v8,
         &v29,
         &v27,
         &v25,
         &v24[1]);
  v10 = v9;
  if ( v9 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    TaskFolder = TaskSchedulerSignalFactory::GetTaskFolder(a1, &v31);
    v10 = TaskFolder;
    if ( TaskFolder >= 0 )
    {
      v22 = v31;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      v12 = TaskSchedulerSignalFactory::AddWeeklyDay(a1, a3, (int)&v22, (int)a2 + 4, L"_0_Sun", 1, (__int64)v23);
      v10 = v12;
      if ( v12 >= 0 )
      {
        v22 = v31;
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
        v13 = TaskSchedulerSignalFactory::AddWeeklyDay(a1, a3, (int)&v22, (int)a2 + 44, L"_1_Mon", 2, (__int64)v23);
        v10 = v13;
        if ( v13 >= 0 )
        {
          v22 = v31;
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
          v14 = TaskSchedulerSignalFactory::AddWeeklyDay(a1, a3, (int)&v22, (int)a2 + 84, L"_2_Tue", 4, (__int64)v23);
          v10 = v14;
          if ( v14 >= 0 )
          {
            v22 = v31;
            if ( v31 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
            v15 = TaskSchedulerSignalFactory::AddWeeklyDay(a1, a3, (int)&v22, (int)a2 + 124, L"_3_Wed", 8, (__int64)v23);
            v10 = v15;
            if ( v15 >= 0 )
            {
              v22 = v31;
              if ( v31 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
              v16 = TaskSchedulerSignalFactory::AddWeeklyDay(
                      a1,
                      a3,
                      (int)&v22,
                      (int)a2 + 164,
                      L"_4_Thu",
                      16,
                      (__int64)v23);
              v10 = v16;
              if ( v16 >= 0 )
              {
                v22 = v31;
                if ( v31 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
                v17 = TaskSchedulerSignalFactory::AddWeeklyDay(
                        a1,
                        a3,
                        (int)&v22,
                        (int)a2 + 204,
                        L"_5_Fri",
                        32,
                        (__int64)v23);
                v10 = v17;
                if ( v17 >= 0 )
                {
                  v22 = v31;
                  if ( v31 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
                  v18 = TaskSchedulerSignalFactory::AddWeeklyDay(
                          a1,
                          a3,
                          (int)&v22,
                          (int)a2 + 244,
                          L"_6_Sat",
                          64,
                          (__int64)v23);
                  v10 = v18;
                  if ( v18 >= 0 )
                  {
                    v20 = TaskSchedulerSignalFactory::ConstructSignal(v19, &v22, a3, a2, v23);
                    std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(
                      a4,
                      v20);
                    std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v22);
                    v10 = 0;
                  }
                  else
                  {
                    LogOpFailure(
                      "AddWeeklyDay(taskId, folder, specification.weekly.sat, NA_TASK_SCHED_TASK_SUFFIX_SAT, TaskSchedule"
                      "rSignal::SATURDAY_BIT, &taskNames)",
                      (unsigned int)v18);
                    DeleteTasks((__int64 ***)v23);
                  }
                }
                else
                {
                  LogOpFailure(
                    "AddWeeklyDay(taskId, folder, specification.weekly.fri, NA_TASK_SCHED_TASK_SUFFIX_FRI, TaskSchedulerS"
                    "ignal::FRIDAY_BIT, &taskNames)",
                    (unsigned int)v17);
                  DeleteTasks((__int64 ***)v23);
                }
              }
              else
              {
                LogOpFailure(
                  "AddWeeklyDay(taskId, folder, specification.weekly.thu, NA_TASK_SCHED_TASK_SUFFIX_THU, TaskSchedulerSig"
                  "nal::THURSDAY_BIT, &taskNames)",
                  (unsigned int)v16);
                DeleteTasks((__int64 ***)v23);
              }
            }
            else
            {
              LogOpFailure(
                "AddWeeklyDay(taskId, folder, specification.weekly.wed, NA_TASK_SCHED_TASK_SUFFIX_WED, TaskSchedulerSigna"
                "l::WEDNESDAY_BIT, &taskNames)",
                (unsigned int)v15);
              DeleteTasks((__int64 ***)v23);
            }
          }
          else
          {
            LogOpFailure(
              "AddWeeklyDay(taskId, folder, specification.weekly.tue, NA_TASK_SCHED_TASK_SUFFIX_TUE, TaskSchedulerSignal:"
              ":TUESDAY_BIT, &taskNames)",
              (unsigned int)v14);
            DeleteTasks((__int64 ***)v23);
          }
        }
        else
        {
          LogOpFailure(
            "AddWeeklyDay(taskId, folder, specification.weekly.mon, NA_TASK_SCHED_TASK_SUFFIX_MON, TaskSchedulerSignal::M"
            "ONDAY_BIT, &taskNames)",
            (unsigned int)v13);
          DeleteTasks((__int64 ***)v23);
        }
      }
      else
      {
        LogOpFailure(
          "AddWeeklyDay(taskId, folder, specification.weekly.sun, NA_TASK_SCHED_TASK_SUFFIX_SUN, TaskSchedulerSignal::SUN"
          "DAY_BIT, &taskNames)",
          (unsigned int)v12);
        DeleteTasks((__int64 ***)v23);
      }
    }
    else
    {
      LogOpFailure("GetTaskFolder(&folder)", (unsigned int)TaskFolder);
      DeleteTasks((__int64 ***)v23);
    }
  }
  else
  {
    LogOpFailure("taskService->Connect({}, {}, {}, {})", (unsigned int)v9);
    DeleteTasks((__int64 ***)v23);
  }
  std::vector<_bstr_t>::_Tidy(v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return v10;
}

```

## disassembly

```asm
0x18002a978  mov     rax, rsp
0x18002a97b  mov     [rax+10h], rbx
0x18002a97f  mov     [rax+18h], rsi
0x18002a983  push    rbp
0x18002a984  push    rdi
0x18002a985  push    r12
0x18002a987  push    r14
0x18002a989  push    r15
0x18002a98b  lea     rbp, [rax-38h]
0x18002a98f  sub     rsp, 110h
0x18002a996  movaps  xmmword ptr [rax-38h], xmm6
0x18002a99a  movaps  xmmword ptr [rax-48h], xmm7
0x18002a99e  mov     r15, r9
0x18002a9a1  mov     rsi, r8
0x18002a9a4  mov     r14, rdx
0x18002a9a7  mov     rdi, rcx
0x18002a9aa  mov     [rbp+30h+arg_0], 0
0x18002a9b2  lea     rcx, [rsp+130h+var_E8]
0x18002a9b7  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18002a9bc  nop
0x18002a9bd  lea     rax, [rsp+130h+var_E8]
0x18002a9c2  mov     qword ptr [rsp+130h+var_D0], rax
0x18002a9c7  mov     r12d, 1
0x18002a9cd  mov     [rsp+130h+var_C8], r12b
0x18002a9d2  mov     rcx, [rdi+8]
0x18002a9d6  xorps   xmm7, xmm7
0x18002a9d9  xor     eax, eax
0x18002a9db  movq    xmm6, rax
0x18002a9e0  xorps   xmm5, xmm5
0x18002a9e3  movq    xmm4, rax
0x18002a9e8  xorps   xmm3, xmm3
0x18002a9eb  movq    xmm2, rax
0x18002a9f0  xorps   xmm1, xmm1
0x18002a9f3  movaps  xmmword ptr [rsp+130h+var_C8+8], xmm7
0x18002a9f8  movsd   [rbp+30h+var_B0], xmm6
0x18002a9fd  movaps  [rbp+30h+var_A0], xmm5
0x18002aa01  movsd   [rbp+30h+var_90], xmm4
0x18002aa06  movaps  [rbp+30h+var_80], xmm3
0x18002aa0a  movsd   [rbp+30h+var_70], xmm2
0x18002aa0f  movaps  [rbp+30h+var_60], xmm1
0x18002aa13  mov     [rbp+30h+var_50], rax
0x18002aa17  mov     rax, [rcx]
0x18002aa1a  lea     rdx, [rsp+130h+var_C8+8]
0x18002aa1f  mov     [rsp+130h+var_110], rdx
0x18002aa24  lea     r9, [rbp+30h+var_A0]
0x18002aa28  lea     r8, [rbp+30h+var_80]
0x18002aa2c  lea     rdx, [rbp+30h+var_60]
0x18002aa30  mov     rax, [rax+50h]
0x18002aa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa39  mov     ebx, eax
0x18002aa3b  test    eax, eax
0x18002aa3d  jns     short loc_18002AA5E
0x18002aa3f  mov     edx, eax
0x18002aa41  lea     rcx, aTaskserviceCon; "taskService->Connect({}, {}, {}, {})"
0x18002aa48  call    LogOpFailure
0x18002aa4d  nop
0x18002aa4e  lea     rcx, [rsp+130h+var_E8]
0x18002aa53  call    DeleteTasks
0x18002aa58  nop
0x18002aa59  jmp     loc_18002ADE6
0x18002aa5e  lea     rcx, [rbp+30h+arg_0]
0x18002aa62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002aa67  lea     rdx, [rbp+30h+arg_0]
0x18002aa6b  mov     rcx, rdi
0x18002aa6e  call    ?GetTaskFolder@TaskSchedulerSignalFactory@@AEAAJPEAV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@@Z; TaskSchedulerSignalFactory::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskFolder> *)
0x18002aa73  mov     ebx, eax
0x18002aa75  test    eax, eax
0x18002aa77  jns     short loc_18002AA98
0x18002aa79  mov     edx, eax
0x18002aa7b  lea     rcx, aGettaskfolderF; "GetTaskFolder(&folder)"
0x18002aa82  call    LogOpFailure
0x18002aa87  nop
0x18002aa88  lea     rcx, [rsp+130h+var_E8]
0x18002aa8d  call    DeleteTasks
0x18002aa92  nop
0x18002aa93  jmp     loc_18002ADE6
0x18002aa98  mov     rcx, [rbp+30h+arg_0]
0x18002aa9c  mov     [rsp+130h+var_F0], rcx
0x18002aaa1  test    rcx, rcx
0x18002aaa4  jz      short loc_18002AAB3
0x18002aaa6  mov     rax, [rcx]
0x18002aaa9  mov     rax, [rax+8]
0x18002aaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aab2  nop
0x18002aab3  lea     r9, [r14+4]; int
0x18002aab7  lea     rax, [rsp+130h+var_E8]
0x18002aabc  mov     [rsp+130h+var_100], rax; __int64
0x18002aac1  mov     [rsp+130h+var_108], r12w; __int16
0x18002aac7  lea     rax, a0Sun; "_0_Sun"
0x18002aace  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002aad3  lea     r8, [rsp+130h+var_F0]; int
0x18002aad8  mov     rdx, rsi; int
0x18002aadb  mov     rcx, rdi; int
0x18002aade  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002aae3  mov     ebx, eax
0x18002aae5  test    eax, eax
0x18002aae7  jns     short loc_18002AB08
0x18002aae9  mov     edx, eax
0x18002aaeb  lea     rcx, aAddweeklydayTa_5; "AddWeeklyDay(taskId, folder, specificat"...
0x18002aaf2  call    LogOpFailure
0x18002aaf7  nop
0x18002aaf8  lea     rcx, [rsp+130h+var_E8]
0x18002aafd  call    DeleteTasks
0x18002ab02  nop
0x18002ab03  jmp     loc_18002ADE6
0x18002ab08  mov     rcx, [rbp+30h+arg_0]
0x18002ab0c  mov     [rsp+130h+var_F0], rcx
0x18002ab11  test    rcx, rcx
0x18002ab14  jz      short loc_18002AB23
0x18002ab16  mov     rax, [rcx]
0x18002ab19  mov     rax, [rax+8]
0x18002ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab22  nop
0x18002ab23  lea     r9, [r14+2Ch]; int
0x18002ab27  lea     rax, [rsp+130h+var_E8]
0x18002ab2c  mov     [rsp+130h+var_100], rax; __int64
0x18002ab31  mov     [rsp+130h+var_108], 2; __int16
0x18002ab38  lea     rax, a1Mon; "_1_Mon"
0x18002ab3f  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002ab44  lea     r8, [rsp+130h+var_F0]; int
0x18002ab49  mov     rdx, rsi; int
0x18002ab4c  mov     rcx, rdi; int
0x18002ab4f  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002ab54  mov     ebx, eax
0x18002ab56  test    eax, eax
0x18002ab58  jns     short loc_18002AB79
0x18002ab5a  mov     edx, eax
0x18002ab5c  lea     rcx, aAddweeklydayTa_2; "AddWeeklyDay(taskId, folder, specificat"...
0x18002ab63  call    LogOpFailure
0x18002ab68  nop
0x18002ab69  lea     rcx, [rsp+130h+var_E8]
0x18002ab6e  call    DeleteTasks
0x18002ab73  nop
0x18002ab74  jmp     loc_18002ADE6
0x18002ab79  mov     rcx, [rbp+30h+arg_0]
0x18002ab7d  mov     [rsp+130h+var_F0], rcx
0x18002ab82  test    rcx, rcx
0x18002ab85  jz      short loc_18002AB94
0x18002ab87  mov     rax, [rcx]
0x18002ab8a  mov     rax, [rax+8]
0x18002ab8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab93  nop
0x18002ab94  lea     r9, [r14+54h]; int
0x18002ab98  lea     rax, [rsp+130h+var_E8]
0x18002ab9d  mov     [rsp+130h+var_100], rax; __int64
0x18002aba2  mov     [rsp+130h+var_108], 4; __int16
0x18002aba9  lea     rax, a2Tue; "_2_Tue"
0x18002abb0  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002abb5  lea     r8, [rsp+130h+var_F0]; int
0x18002abba  mov     rdx, rsi; int
0x18002abbd  mov     rcx, rdi; int
0x18002abc0  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002abc5  mov     ebx, eax
0x18002abc7  test    eax, eax
0x18002abc9  jns     short loc_18002ABEA
0x18002abcb  mov     edx, eax
0x18002abcd  lea     rcx, aAddweeklydayTa; "AddWeeklyDay(taskId, folder, specificat"...
0x18002abd4  call    LogOpFailure
0x18002abd9  nop
0x18002abda  lea     rcx, [rsp+130h+var_E8]
0x18002abdf  call    DeleteTasks
0x18002abe4  nop
0x18002abe5  jmp     loc_18002ADE6
0x18002abea  mov     rcx, [rbp+30h+arg_0]
0x18002abee  mov     [rsp+130h+var_F0], rcx
0x18002abf3  test    rcx, rcx
0x18002abf6  jz      short loc_18002AC05
0x18002abf8  mov     rax, [rcx]
0x18002abfb  mov     rax, [rax+8]
0x18002abff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac04  nop
0x18002ac05  lea     r9, [r14+7Ch]; int
0x18002ac09  lea     rax, [rsp+130h+var_E8]
0x18002ac0e  mov     [rsp+130h+var_100], rax; __int64
0x18002ac13  mov     [rsp+130h+var_108], 8; __int16
0x18002ac1a  lea     rax, a3Wed; "_3_Wed"
0x18002ac21  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002ac26  lea     r8, [rsp+130h+var_F0]; int
0x18002ac2b  mov     rdx, rsi; int
0x18002ac2e  mov     rcx, rdi; int
0x18002ac31  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002ac36  mov     ebx, eax
0x18002ac38  test    eax, eax
0x18002ac3a  jns     short loc_18002AC5B
0x18002ac3c  mov     edx, eax
0x18002ac3e  lea     rcx, aAddweeklydayTa_0; "AddWeeklyDay(taskId, folder, specificat"...
0x18002ac45  call    LogOpFailure
0x18002ac4a  nop
0x18002ac4b  lea     rcx, [rsp+130h+var_E8]
0x18002ac50  call    DeleteTasks
0x18002ac55  nop
0x18002ac56  jmp     loc_18002ADE6
0x18002ac5b  mov     rcx, [rbp+30h+arg_0]
0x18002ac5f  mov     [rsp+130h+var_F0], rcx
0x18002ac64  test    rcx, rcx
0x18002ac67  jz      short loc_18002AC76
0x18002ac69  mov     rax, [rcx]
0x18002ac6c  mov     rax, [rax+8]
0x18002ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac75  nop
0x18002ac76  lea     r9, [r14+0A4h]; int
0x18002ac7d  lea     rax, [rsp+130h+var_E8]
0x18002ac82  mov     [rsp+130h+var_100], rax; __int64
0x18002ac87  mov     [rsp+130h+var_108], 10h; __int16
0x18002ac8e  lea     rax, a4Thu; "_4_Thu"
0x18002ac95  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002ac9a  lea     r8, [rsp+130h+var_F0]; int
0x18002ac9f  mov     rdx, rsi; int
0x18002aca2  mov     rcx, rdi; int
0x18002aca5  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002acaa  mov     ebx, eax
0x18002acac  test    eax, eax
0x18002acae  jns     short loc_18002ACCF
0x18002acb0  mov     edx, eax
0x18002acb2  lea     rcx, aAddweeklydayTa_3; "AddWeeklyDay(taskId, folder, specificat"...
0x18002acb9  call    LogOpFailure
0x18002acbe  nop
0x18002acbf  lea     rcx, [rsp+130h+var_E8]
0x18002acc4  call    DeleteTasks
0x18002acc9  nop
0x18002acca  jmp     loc_18002ADE6
0x18002accf  mov     rcx, [rbp+30h+arg_0]
0x18002acd3  mov     [rsp+130h+var_F0], rcx
0x18002acd8  test    rcx, rcx
0x18002acdb  jz      short loc_18002ACEA
0x18002acdd  mov     rax, [rcx]
0x18002ace0  mov     rax, [rax+8]
0x18002ace4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ace9  nop
0x18002acea  lea     r9, [r14+0CCh]; int
0x18002acf1  lea     rax, [rsp+130h+var_E8]
0x18002acf6  mov     [rsp+130h+var_100], rax; __int64
0x18002acfb  mov     [rsp+130h+var_108], 20h ; ' '; __int16
0x18002ad02  lea     rax, a5Fri; "_5_Fri"
0x18002ad09  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002ad0e  lea     r8, [rsp+130h+var_F0]; int
0x18002ad13  mov     rdx, rsi; int
0x18002ad16  mov     rcx, rdi; int
0x18002ad19  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002ad1e  mov     ebx, eax
0x18002ad20  test    eax, eax
0x18002ad22  jns     short loc_18002AD43
0x18002ad24  mov     edx, eax
0x18002ad26  lea     rcx, aAddweeklydayTa_4; "AddWeeklyDay(taskId, folder, specificat"...
0x18002ad2d  call    LogOpFailure
0x18002ad32  nop
0x18002ad33  lea     rcx, [rsp+130h+var_E8]
0x18002ad38  call    DeleteTasks
0x18002ad3d  nop
0x18002ad3e  jmp     loc_18002ADE6
0x18002ad43  mov     rcx, [rbp+30h+arg_0]
0x18002ad47  mov     [rsp+130h+var_F0], rcx
0x18002ad4c  test    rcx, rcx
0x18002ad4f  jz      short loc_18002AD5E
0x18002ad51  mov     rax, [rcx]
0x18002ad54  mov     rax, [rax+8]
0x18002ad58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad5d  nop
0x18002ad5e  lea     r9, [r14+0F4h]; int
0x18002ad65  lea     rax, [rsp+130h+var_E8]
0x18002ad6a  mov     [rsp+130h+var_100], rax; __int64
0x18002ad6f  mov     [rsp+130h+var_108], 40h ; '@'; __int16
0x18002ad76  lea     rax, a6Sat; "_6_Sat"
0x18002ad7d  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18002ad82  lea     r8, [rsp+130h+var_F0]; int
0x18002ad87  mov     rdx, rsi; int
0x18002ad8a  mov     rcx, rdi; int
0x18002ad8d  call    ?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z; TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t> *)
0x18002ad92  mov     ebx, eax
0x18002ad94  test    eax, eax
0x18002ad96  jns     short loc_18002ADB4
0x18002ad98  mov     edx, eax
0x18002ad9a  lea     rcx, aAddweeklydayTa_1; "AddWeeklyDay(taskId, folder, specificat"...
0x18002ada1  call    LogOpFailure
0x18002ada6  nop
0x18002ada7  lea     rcx, [rsp+130h+var_E8]
0x18002adac  call    DeleteTasks
0x18002adb1  nop
0x18002adb2  jmp     short loc_18002ADE6
0x18002adb4  lea     rax, [rsp+130h+var_E8]
0x18002adb9  mov     [rsp+130h+var_110], rax
0x18002adbe  mov     r9, r14
0x18002adc1  mov     r8, rsi
0x18002adc4  lea     rdx, [rsp+130h+var_F0]
0x18002adc9  call    ?ConstructSignal@TaskSchedulerSignalFactory@@AEAA?AV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@std@@_JAEBUSpec@TimeSignal@@AEBV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@3@@Z; TaskSchedulerSignalFactory::ConstructSignal(__int64,TimeSignal::Spec const &,std::vector<_bstr_t> const &)
0x18002adce  mov     rdx, rax
0x18002add1  mov     rcx, r15
0x18002add4  call    ??$?4VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@$0A@@?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@1@@Z; std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(std::unique_ptr<TaskSchedulerSignal> &&)
0x18002add9  lea     rcx, [rsp+130h+var_F0]
0x18002adde  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18002ade3  nop
0x18002ade4  xor     ebx, ebx
0x18002ade6  lea     rcx, [rsp+130h+var_E8]
0x18002adeb  call    ?_Tidy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAXXZ; std::vector<_bstr_t>::_Tidy(void)
0x18002adf0  nop
0x18002adf1  lea     rcx, [rbp+30h+arg_0]
0x18002adf5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002adfa  mov     eax, ebx
0x18002adfc  lea     r11, [rsp+130h+var_20]
0x18002ae04  mov     rbx, [r11+38h]
  ... truncated ...
```
