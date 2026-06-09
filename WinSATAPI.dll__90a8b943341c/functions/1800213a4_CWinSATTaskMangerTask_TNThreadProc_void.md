# CWinSATTaskMangerTask::TNThreadProc(void)

- ea: `0x1800213a4`
- end: `0x18002179e`
- name: `?TNThreadProc@CWinSATTaskMangerTask@@AEAAKXZ`
- size: `1018`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800217b0`

## callees

- `0x18000f0e8`
- `0x18001b790`
- `0x18001d358`
- `0x1800209a8`
- `0x180020dd8`
- `0x180020fa0`
- `0x1800213a4`
- `0x1800217fc`
- `0x180021898`
- `0x1800219d4`
- `0x180021afc`
- `0x180021cc0`
- `0x180021d84`
- `0x180024248`
- `0x180025860`
- `0x18002d76c`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180021526`
- `OLEAUT32!__imp_SysFreeString` at `0x180021526`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800214ea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800214ea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002148d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002148d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214c3`
- `ntdll!ShipAssert` at `0x1800215a9`
- `ntdll!ShipAssert` at `0x1800215a9`

## string_xrefs

- `0x1800213d4`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x1800213c8`: `Starting task thread`
- `0x18002141f`: `Task     thread is running as ADMIN`
- `0x180021444`: `Task     thread is *NOT* running as ADMIN`
- `0x180021478`: `Starting task thread`
- `0x180021758`: `The TaskScheduler Task unexpectedly terminated on last run.  WinSAT has possibly bluescreened the machine.`
- `0x18002167d`: `cannot write %s to the registry`
- `0x18002169c`: `WinSAT was cancelled in the idle task`
- `0x1800216c6`: `WinSAT completed with an errror`
- `0x1800214fd`: `complted successfully`
- `0x18002150a`: `WinSAT Task Manger task  %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinSATTaskMangerTask::TNThreadProc(CWinSATTaskMangerTask *this)
{
  char v2; // r15
  void *v3; // rdx
  void (__fastcall *v4)(void *, __int64, __int64); // rax
  __int64 v5; // r8
  HRESULT v6; // eax
  CWinSATTaskMangerTask *v7; // rcx
  int ShouldTryRunWinSAT; // edi
  const char *v9; // r9
  unsigned int *v11; // r14
  CWinSATTaskMangerTask *v12; // rcx
  unsigned int v13; // edx
  bool v14; // r8
  CWinSATTaskMangerTask *v15; // rcx
  CWinSATTaskMangerTask *v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // eax
  CWinSATTaskMangerTask *v19; // rcx
  void (__fastcall *v20)(void *, __int64, __int64); // rax
  unsigned int v21; // edx
  bool updated; // cl
  int v23; // eax
  char v24; // cl
  void (__fastcall *v25)(void *, __int64, __int64); // rax
  bool v26; // [rsp+80h] [rbp+40h] BYREF
  bool v27; // [rsp+88h] [rbp+48h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 338, "Starting task thread");
  v26 = 0;
  if ( (unsigned int)IsUserAdmin(&v26, v3) )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 344, "Cannot determine if running as admin...");
    v4 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 0;
  }
  else if ( v26 )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 348, "Task     thread is running as ADMIN");
    v4 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 1;
  }
  else
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 351, "Task     thread is *NOT* running as ADMIN");
    v4 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 2;
  }
  v4(&unk_18004A8B0, 10268, v5);
LABEL_10:
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Starting task thread");
  v6 = CoInitializeEx(0, 0);
  ShouldTryRunWinSAT = v6;
  if ( v6 < 0 )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 360, "CoInitializeEx failed: %x\n", v6);
LABEL_12:
    ShouldTryRunWinSAT = -2147467259;
    goto LABEL_13;
  }
  v2 = 1;
  if ( !bstrString
    || (ShouldTryRunWinSAT = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR))(**((_QWORD **)this + 9) + 24LL))(
                               *((_QWORD *)this + 9),
                               0,
                               bstrString),
        ShouldTryRunWinSAT >= 0) )
  {
    ExitCode = 0;
    v26 = 0;
    v27 = 0;
    v11 = (unsigned int *)((char *)this + 108);
    if ( !CWinSATTaskMangerTask::ReadErrorCountRegKey(v7, (unsigned int *)this + 27) )
      goto LABEL_12;
    if ( *v11 != 4 )
    {
      v13 = *v11 + 1;
      *v11 = v13;
      if ( v13 > 3 )
        ShipAssert(96257);
      if ( !CWinSATTaskMangerTask::UpdateErrorCountRegKey(v12, 4u) )
        goto LABEL_12;
      ShouldTryRunWinSAT = CWinSATTaskMangerTask::NeedToRunWinSAT(this, &v26, v14);
      if ( ShouldTryRunWinSAT >= 0 )
      {
        if ( !v26 )
        {
          v26 = 0;
          if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v26) && !v26 )
            CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(this);
          goto LABEL_46;
        }
        ShouldTryRunWinSAT = CWinSATTaskMangerTask::ShouldTryRunWinSAT(v15, &v27);
        if ( ShouldTryRunWinSAT >= 0 )
        {
          if ( !v27 )
          {
LABEL_46:
            if ( *v11 )
              v21 = *v11 - 1;
            else
              v21 = 0;
            updated = CWinSATTaskMangerTask::UpdateErrorCountRegKey(v16, v21);
            v23 = ShouldTryRunWinSAT;
            if ( !updated )
              v23 = -2147467259;
            ShouldTryRunWinSAT = v23;
            goto LABEL_13;
          }
          ShouldTryRunWinSAT = CWinSATTaskMangerTask::DoRunWinSAT(this, &ExitCode);
          if ( ShouldTryRunWinSAT >= 0 )
          {
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 435, "WinSatExitValue = %u", ExitCode);
            v18 = RegHelper::WriteDWORDValue(v17, L"LastWinSATIdleRunExitValue", ExitCode);
            if ( v18 )
              Record_Win32Error_w(
                "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
                0x1BAu,
                v18,
                (char)L"LastWinSATIdleRunExitValue");
            if ( ExitCode == 3 )
            {
              Log_Text_F(
                "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
                449,
                "WinSAT was cancelled in the idle task");
              v26 = 0;
              CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v26);
LABEL_45:
              *v11 = 0;
              goto LABEL_46;
            }
            if ( !ExitCode )
            {
              CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(v19);
              goto LABEL_45;
            }
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 469, "WinSAT completed with an errror");
            v26 = 0;
            if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v26) && !v26 )
            {
              v20 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 20);
              if ( v20 )
                v20(&unk_18004A8B0, 6438, 1);
            }
            ShouldTryRunWinSAT = -2147467259;
          }
        }
      }
      CWinSATTaskMangerTask::CommitErrorCount(this);
      goto LABEL_13;
    }
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      390,
      "The TaskScheduler Task unexpectedly terminated on last run.  WinSAT has possibly bluescreened the machine.");
    EnableDisableWinSATTask(v24);
    v25 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
    if ( v25 )
      v25(&unk_18004A8B0, 10270, 1);
  }
LABEL_13:
  CloseHandle(*((HANDLE *)this + 14));
  *((_QWORD *)this + 14) = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
    *((_QWORD *)this + 9),
    (unsigned int)ShouldTryRunWinSAT);
  if ( v2 )
    CoUninitialize();
  v9 = "complted successfully";
  if ( ShouldTryRunWinSAT < 0 )
    v9 = "failed";
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 515, "WinSAT Task Manger task  %s", v9);
  SysFreeString(bstrString);
  return (unsigned int)ShouldTryRunWinSAT >> 31;
}

```

## disassembly

```asm
0x1800213a4  push    rbp
0x1800213a6  push    rsi
0x1800213a7  push    rdi
0x1800213a8  push    r12
0x1800213aa  push    r13
0x1800213ac  push    r14
0x1800213ae  push    r15
0x1800213b0  mov     rbp, rsp
0x1800213b3  sub     rsp, 40h
0x1800213b7  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800213bf  mov     rsi, rcx
0x1800213c2  xor     r12d, r12d
0x1800213c5  mov     r15b, r12b
0x1800213c8  lea     r8, aStartingTaskTh; "Starting task thread"
0x1800213cf  mov     edx, 152h
0x1800213d4  lea     r13, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800213db  mov     rcx, r13
0x1800213de  call    Log_Text_F
0x1800213e3  mov     [rbp+arg_0], r12b
0x1800213e7  lea     rcx, [rbp+arg_0]; bool *
0x1800213eb  call    ?IsUserAdmin@@YAKAEA_NPEAX@Z; IsUserAdmin(bool &,void *)
0x1800213f0  mov     rcx, r13
0x1800213f3  test    eax, eax
0x1800213f5  jz      short loc_180021419
0x1800213f7  lea     r8, aCannotDetermin_1; "Cannot determine if running as admin..."
0x1800213fe  mov     edx, 158h
0x180021403  call    Log_Text_F
0x180021408  mov     rax, [rsi+88h]
0x18002140f  test    rax, rax
0x180021412  jz      short loc_180021478
0x180021414  xor     r8d, r8d
0x180021417  jmp     short loc_180021467
0x180021419  cmp     [rbp+arg_0], r12b
0x18002141d  jz      short loc_180021444
0x18002141f  lea     r8, aTaskThreadIsRu; "Task     thread is running as ADMIN"
0x180021426  mov     edx, 15Ch
0x18002142b  call    Log_Text_F
0x180021430  mov     rax, [rsi+88h]
0x180021437  test    rax, rax
0x18002143a  jz      short loc_180021478
0x18002143c  mov     r8d, 1
0x180021442  jmp     short loc_180021467
0x180021444  lea     r8, aTaskThreadIsNo; "Task     thread is *NOT* running as ADM"...
0x18002144b  mov     edx, 15Fh
0x180021450  call    Log_Text_F
0x180021455  mov     rax, [rsi+88h]
0x18002145c  test    rax, rax
0x18002145f  jz      short loc_180021478
0x180021461  mov     r8d, 2
0x180021467  mov     edx, 281Ch
0x18002146c  lea     rcx, unk_18004A8B0
0x180021473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021478  lea     rdx, aStartingTaskTh_0; "Starting task thread"
0x18002147f  lea     rcx, [rbp+bstrString]; this
0x180021483  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180021488  nop
0x180021489  xor     edx, edx; dwCoInit
0x18002148b  xor     ecx, ecx; pvReserved
0x18002148d  call    cs:__imp_CoInitializeEx
0x180021494  nop     dword ptr [rax+rax+00h]
0x180021499  mov     edi, eax
0x18002149b  test    eax, eax
0x18002149d  jns     loc_180021545
0x1800214a3  mov     r9d, eax
0x1800214a6  lea     r8, aCoinitializeex; "CoInitializeEx failed: %x\n"
0x1800214ad  mov     edx, 168h
0x1800214b2  mov     rcx, r13
0x1800214b5  call    Log_Text_F
0x1800214ba  mov     edi, 80004005h
0x1800214bf  mov     rcx, [rsi+70h]; hObject
0x1800214c3  call    cs:__imp_CloseHandle
0x1800214ca  nop     dword ptr [rax+rax+00h]
0x1800214cf  mov     [rsi+70h], r12
0x1800214d3  mov     rcx, [rsi+48h]
0x1800214d7  mov     rax, [rcx]
0x1800214da  mov     edx, edi
0x1800214dc  mov     rax, [rax+20h]
0x1800214e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214e5  test    r15b, r15b
0x1800214e8  jz      short loc_1800214F6
0x1800214ea  call    cs:__imp_CoUninitialize
0x1800214f1  nop     dword ptr [rax+rax+00h]
0x1800214f6  lea     rax, aFailed; "failed"
0x1800214fd  lea     r9, aCompltedSucces; "complted successfully"
0x180021504  test    edi, edi
0x180021506  cmovs   r9, rax
0x18002150a  lea     r8, aWinsatTaskMang; "WinSAT Task Manger task  %s"
0x180021511  mov     edx, 203h
0x180021516  mov     rcx, r13
0x180021519  call    Log_Text_F
0x18002151e  nop
0x18002151f  shr     edi, 1Fh
0x180021522  mov     rcx, [rbp+bstrString]; bstrString
0x180021526  call    cs:__imp_SysFreeString
0x18002152d  nop     dword ptr [rax+rax+00h]
0x180021532  mov     eax, edi
0x180021534  add     rsp, 40h
0x180021538  pop     r15
0x18002153a  pop     r14
0x18002153c  pop     r13
0x18002153e  pop     r12
0x180021540  pop     rdi
0x180021541  pop     rsi
0x180021542  pop     rbp
0x180021543  retn
0x180021545  mov     r15b, 1
0x180021548  cmp     [rbp+bstrString], r12
0x18002154c  jz      short loc_18002156E
0x18002154e  mov     rcx, [rsi+48h]
0x180021552  mov     rax, [rcx]
0x180021555  xor     edx, edx
0x180021557  mov     r8, [rbp+bstrString]
0x18002155b  mov     rax, [rax+18h]
0x18002155f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021564  mov     edi, eax
0x180021566  test    eax, eax
0x180021568  js      loc_1800214BF
0x18002156e  mov     [rbp+ExitCode], r12d
0x180021572  mov     [rbp+arg_0], r12b
0x180021576  mov     [rbp+arg_8], r12b
0x18002157a  lea     r14, [rsi+6Ch]
0x18002157e  mov     rdx, r14; unsigned int *
0x180021581  call    ?ReadErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NAEAK@Z; CWinSATTaskMangerTask::ReadErrorCountRegKey(ulong &)
0x180021586  test    al, al
0x180021588  jz      loc_1800214BA
0x18002158e  mov     edx, [r14]
0x180021591  cmp     edx, 4
0x180021594  jz      loc_180021758
0x18002159a  inc     edx
0x18002159c  mov     [r14], edx
0x18002159f  cmp     edx, 3
0x1800215a2  jbe     short loc_1800215B5
0x1800215a4  mov     ecx, 17801h
0x1800215a9  call    cs:__imp_ShipAssert
0x1800215b0  nop     dword ptr [rax+rax+00h]
0x1800215b5  mov     edx, 4; unsigned int
0x1800215ba  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x1800215bf  test    al, al
0x1800215c1  jz      loc_1800214BA
0x1800215c7  lea     rdx, [rbp+arg_0]; bool *
0x1800215cb  mov     rcx, rsi; this
0x1800215ce  call    ?NeedToRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z; CWinSATTaskMangerTask::NeedToRunWinSAT(bool &)
0x1800215d3  mov     edi, eax
0x1800215d5  test    eax, eax
0x1800215d7  js      loc_18002171C
0x1800215dd  cmp     [rbp+arg_0], r12b
0x1800215e1  jnz     short loc_180021612
0x1800215e3  mov     [rbp+arg_0], r12b
0x1800215e7  lea     rdx, [rbp+arg_0]; bool *
0x1800215eb  mov     rcx, rsi; this
0x1800215ee  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800215f3  test    al, al
0x1800215f5  jz      loc_180021731
0x1800215fb  cmp     [rbp+arg_0], r12b
0x1800215ff  jnz     loc_180021731
0x180021605  mov     rcx, rsi; this
0x180021608  call    ?DoMarkAsCompleteOnDemdand@CWinSATTaskMangerTask@@AEAAXXZ; CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(void)
0x18002160d  jmp     loc_180021731
0x180021612  lea     rdx, [rbp+arg_8]; bool *
0x180021616  call    ?ShouldTryRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z; CWinSATTaskMangerTask::ShouldTryRunWinSAT(bool &)
0x18002161b  mov     edi, eax
0x18002161d  test    eax, eax
0x18002161f  js      loc_18002171C
0x180021625  cmp     [rbp+arg_8], r12b
0x180021629  jz      loc_180021731
0x18002162f  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180021633  mov     rcx, rsi; this
0x180021636  call    ?DoRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEAK@Z; CWinSATTaskMangerTask::DoRunWinSAT(ulong &)
0x18002163b  mov     edi, eax
0x18002163d  test    eax, eax
0x18002163f  js      loc_18002171C
0x180021645  mov     r9d, [rbp+ExitCode]
0x180021649  lea     r8, aWinsatexitvalu; "WinSatExitValue = %u"
0x180021650  mov     edx, 1B3h
0x180021655  mov     rcx, r13
0x180021658  call    Log_Text_F
0x18002165d  mov     r8d, [rbp+ExitCode]
0x180021661  lea     rdx, aLastwinsatidle; "LastWinSATIdleRunExitValue"
0x180021668  call    ?WriteDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGK@Z; RegHelper::WriteDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong)
0x18002166d  test    eax, eax
0x18002166f  jz      short loc_180021694
0x180021671  lea     rcx, aLastwinsatidle; "LastWinSATIdleRunExitValue"
0x180021678  mov     qword ptr [rsp+40h+var_20], rcx; char
0x18002167d  lea     r9, aCannotWriteSTo_0; "cannot write %s to the registry"
0x180021684  mov     r8d, eax; unsigned int
0x180021687  mov     edx, 1BAh; unsigned int
0x18002168c  mov     rcx, r13; char *
0x18002168f  call    Record_Win32Error_w
0x180021694  mov     eax, [rbp+ExitCode]
0x180021697  cmp     eax, 3
0x18002169a  jnz     short loc_1800216C2
0x18002169c  lea     r8, aWinsatWasCance; "WinSAT was cancelled in the idle task"
0x1800216a3  mov     edx, 1C1h
0x1800216a8  mov     rcx, r13
0x1800216ab  call    Log_Text_F
0x1800216b0  mov     [rbp+arg_0], r12b
0x1800216b4  lea     rdx, [rbp+arg_0]; bool *
0x1800216b8  mov     rcx, rsi; this
0x1800216bb  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800216c0  jmp     short loc_18002172E
0x1800216c2  test    eax, eax
0x1800216c4  jz      short loc_180021729
0x1800216c6  lea     r8, aWinsatComplete; "WinSAT completed with an errror"
0x1800216cd  mov     edx, 1D5h
0x1800216d2  mov     rcx, r13
0x1800216d5  call    Log_Text_F
0x1800216da  mov     [rbp+arg_0], r12b
0x1800216de  lea     rdx, [rbp+arg_0]; bool *
0x1800216e2  mov     rcx, rsi; this
0x1800216e5  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800216ea  test    al, al
0x1800216ec  jz      short loc_180021717
0x1800216ee  cmp     [rbp+arg_0], r12b
0x1800216f2  jnz     short loc_180021717
0x1800216f4  mov     rax, [rsi+0A0h]
0x1800216fb  test    rax, rax
0x1800216fe  jz      short loc_180021717
0x180021700  mov     edx, 1926h
0x180021705  mov     r8d, 1
0x18002170b  lea     rcx, unk_18004A8B0
0x180021712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021717  mov     edi, 80004005h
0x18002171c  mov     rcx, rsi; this
0x18002171f  call    ?CommitErrorCount@CWinSATTaskMangerTask@@AEAA_NXZ; CWinSATTaskMangerTask::CommitErrorCount(void)
0x180021724  jmp     loc_1800214BF
0x180021729  call    ?DoSuccesfulCompletionRegistryAndSQMWork@CWinSATTaskMangerTask@@AEAAXXZ; CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(void)
0x18002172e  mov     [r14], r12d
0x180021731  mov     edx, [r14]
0x180021734  test    edx, edx
0x180021736  jz      short loc_18002173C
0x180021738  dec     edx
0x18002173a  jmp     short loc_18002173E
0x18002173c  xor     edx, edx; unsigned int
0x18002173e  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x180021743  mov     cl, al
0x180021745  mov     eax, edi
0x180021747  mov     edi, 80004005h
0x18002174c  test    cl, cl
0x18002174e  cmovz   eax, edi
0x180021751  mov     edi, eax
0x180021753  jmp     loc_1800214BF
0x180021758  lea     r8, aTheTaskschedul; "The TaskScheduler Task unexpectedly ter"...
0x18002175f  mov     edx, 186h
0x180021764  mov     rcx, r13
0x180021767  call    Log_Text_F
0x18002176c  call    ?EnableDisableWinSATTask@@YAJ_N@Z; EnableDisableWinSATTask(bool)
0x180021771  mov     rax, [rsi+88h]
0x180021778  test    rax, rax
0x18002177b  jz      loc_1800214BF
0x180021781  mov     edx, 281Eh
0x180021786  mov     r8d, 1
0x18002178c  lea     rcx, unk_18004A8B0
0x180021793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021798  jmp     loc_1800214BF
```
