# SystemSettings::WorkAccess::MDMHTMLReportSetting::Invoke(HWND__ *)

- ea: `0x180034480`
- end: `0x18003453f`
- name: `?Invoke@MDMHTMLReportSetting@WorkAccess@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(PVOID pv, HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180019dfc`
- `0x180034480`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034529`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034529`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003449b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003449b`

## string_xrefs

- `0x1800344c0`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkAccess::MDMHTMLReportSetting::Invoke(PTP_WORK *pv, HWND a2)
{
  PTP_WORK ThreadpoolWork; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v7; // [rsp+30h] [rbp+8h] BYREF
  int *v8; // [rsp+40h] [rbp+18h] BYREF
  int **v9; // [rsp+48h] [rbp+20h] BYREF

  BYTE1(v7) = 1;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)SystemSettings::WorkAccess::MDMHTMLReportSetting::s_DeviceManagementWorker,
                     pv,
                     0);
  pv[31] = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    BYTE1(v7) = 0;
    LODWORD(v8) = 1;
    v9 = &v8;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
      &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
      &v9);
    SubmitThreadpoolWork(pv[31]);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x867,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x80004005LL,
      v5);
    v7 = 0;
    v8 = &v7;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
      &SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton,
      &v8);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180034480  push    rbx; int
0x180034482  sub     rsp, 20h
0x180034486  mov     rbx, rcx
0x180034489  mov     [rsp+28h+arg_1], 1
0x18003448e  xor     r8d, r8d; pcbe
0x180034491  mov     rdx, rcx; pv
0x180034494  lea     rcx, ?s_DeviceManagementWorker@MDMHTMLReportSetting@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003449b  call    cs:__imp_CreateThreadpoolWork
0x1800344a2  nop     dword ptr [rax+rax+00h]
0x1800344a7  mov     [rbx+0F8h], rax
0x1800344ae  test    rax, rax
0x1800344b1  jnz     short loc_1800344FA
0x1800344b3  mov     rcx, [rsp+28h]; this
0x1800344b8  mov     ebx, 80004005h
0x1800344bd  mov     r9d, ebx; char *
0x1800344c0  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x1800344c7  mov     edx, 867h; void *
0x1800344cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800344d1  nop
0x1800344d2  mov     dword ptr [rsp+30h], 0
0x1800344da  lea     rcx, [rsp+28h+arg_0]
0x1800344df  mov     [rsp+28h+arg_10], rcx
0x1800344e4  lea     rdx, [rsp+28h+arg_10]
0x1800344e9  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x1800344f0  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x1800344f5  nop
0x1800344f6  mov     eax, ebx
0x1800344f8  jmp     short loc_180034538
0x1800344fa  mov     [rsp+28h+arg_1], 0
0x1800344ff  mov     dword ptr [rsp+28h+arg_10], 1
0x180034507  lea     rax, [rsp+28h+arg_10]
0x18003450c  mov     [rsp+28h+arg_18], rax
0x180034511  lea     rdx, [rsp+28h+arg_18]
0x180034516  lea     rcx, ?g_MDMHTMLReportSettingSingleton@MDMHTMLReportSettingSingleton@WorkAccess@SystemSettings@@0V123@A; SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton SystemSettings::WorkAccess::MDMHTMLReportSettingSingleton::g_MDMHTMLReportSettingSingleton
0x18003451d  call    ??$_Notify@V_lambda_7d9b1dafe109be445bee74074bc960ae_@@@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7d9b1dafe109be445bee74074bc960ae_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(_lambda_7d9b1dafe109be445bee74074bc960ae_ const &)
0x180034522  mov     rcx, [rbx+0F8h]; pwk
0x180034529  call    cs:__imp_SubmitThreadpoolWork
0x180034530  nop     dword ptr [rax+rax+00h]
0x180034535  nop
0x180034536  xor     eax, eax
0x180034538  add     rsp, 20h
0x18003453c  pop     rbx
0x18003453d  retn
```
