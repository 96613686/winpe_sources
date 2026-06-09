# StartIdleScavenge(void *)

- ea: `0x140012540`
- end: `0x140012761`
- name: `?StartIdleScavenge@@YAKPEAX@Z`
- size: `545`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400023e0`
- `0x14000ca98`
- `0x140012540`
- `0x140017658`
- `0x14001a16c`
- `0x140020ffc`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140012639`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140012639`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140012739`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140012739`

## string_xrefs

- `0x140012645`: `Failed to initialize COM.`
- `0x1400125a7`: `Cannot run idle scavenging/repair, a reboot is pending`
- `0x1400125e1`: `AutoRepairNeeded`
- `0x1400125e8`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x140012601`: `Failed to read AutoRepairNeeded.`
- `0x140012693`: `Warning: Failed to execute idle scavenge/repair start. Error code: 0X%x`
- `0x1400126b4`: `Signaling IdleScavenge and/or repair complete.`
- `0x1400126df`: `Warning: Unable to mark idle scavenging/repair complete. Error code: 0X%x`

## pseudocode

```c
__int64 __fastcall StartIdleScavenge(char *Parameter)
{
  int v2; // r15d
  int v3; // ebx
  HKEY v4; // rcx
  HRESULT WorkerProcess; // eax
  const char *v6; // r9
  int v7; // eax
  int v8; // eax
  char *v9; // rcx
  unsigned int v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h] BYREF

  v12 = 0;
  v13 = 0;
  v11 = 0;
  if ( !Parameter || !*((_QWORD *)Parameter + 3) || !*((_QWORD *)Parameter + 4) )
    return 2147750667LL;
  v2 = 0;
  if ( vbRequireReboot )
  {
    v3 = 0;
    CBSWdsLogLight(0x4000000, 0, 0, "Cannot run idle scavenging/repair, a reboot is pending");
    v13 = 1;
    goto LABEL_20;
  }
  OnlineMaintenanceActionGet((unsigned int)Parameter, &v13);
  v3 = CbsRegQueryDWORDValue(
         v4,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
         1u,
         L"AutoRepairNeeded",
         &v11);
  if ( v3 < 0 )
  {
    v3 = 0;
    CBSWdsLogLight(0x4000000, 0, 0, "Failed to read AutoRepairNeeded.");
  }
  if ( v13 && !v11 )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "Maint: Nothing to do, so skipping");
    goto LABEL_18;
  }
  WorkerProcess = CoInitializeEx(0, 0);
  v3 = WorkerProcess;
  if ( WorkerProcess < 0 )
  {
    v6 = "Failed to initialize COM.";
LABEL_13:
    CBSWdsLogLight(0x4000000, (unsigned int)WorkerProcess, 1, v6);
    goto LABEL_18;
  }
  v2 = 1;
  WorkerProcess = TiCoreGetWorkerProcess(0, &v12);
  v3 = WorkerProcess;
  if ( WorkerProcess < 0 )
  {
    v6 = "Failed to get worker process.";
    goto LABEL_13;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v12 + 96LL))(v12, 1, &v13);
  v3 = v7;
  if ( v7 < 0 )
    CBSWdsLogLight(
      0x4000000,
      (unsigned int)v7,
      1,
      "Warning: Failed to execute idle scavenge/repair start. Error code: 0X%x",
      v7);
LABEL_18:
  if ( v13 || v3 < 0 )
  {
LABEL_20:
    CBSWdsLogLight(0x4000000, 0, 0, "Signaling IdleScavenge and/or repair complete.");
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 32LL))(
           *((_QWORD *)Parameter + 3),
           (unsigned int)v3);
    v3 = v8;
    if ( v8 < 0 )
      CBSWdsLogLight(
        0x4000000,
        (unsigned int)v8,
        1,
        "Warning: Unable to mark idle scavenging/repair complete. Error code: 0X%x",
        v8);
  }
  _InterlockedExchange((volatile __int32 *)Parameter + 10, 0);
  v9 = &Parameter[*(int *)(*((_QWORD *)Parameter + 1) + 4LL) + 8];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v2 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012540  push    rbp
0x140012542  push    rbx
0x140012543  push    rsi
0x140012544  push    rdi
0x140012545  push    r14
0x140012547  push    r15
0x140012549  mov     rbp, rsp
0x14001254c  sub     rsp, 58h
0x140012550  mov     rax, cs:__security_cookie
0x140012557  xor     rax, rsp
0x14001255a  mov     [rbp+var_10], rax
0x14001255e  mov     [rbp+var_20], 0
0x140012566  mov     r14, rcx
0x140012569  mov     [rbp+var_18], 0
0x140012570  mov     [rbp+var_28], 0
0x140012577  test    rcx, rcx
0x14001257a  jz      loc_140012743
0x140012580  cmp     qword ptr [rcx+18h], 0
0x140012585  jz      loc_140012743
0x14001258b  cmp     qword ptr [rcx+20h], 0
0x140012590  jz      loc_140012743
0x140012596  xor     r15d, r15d
0x140012599  cmp     cs:?vbRequireReboot@@3HA, r15d; int vbRequireReboot
0x1400125a0  jz      short loc_1400125C7
0x1400125a2  mov     esi, 4000000h
0x1400125a7  lea     r9, aCannotRunIdleS; "Cannot run idle scavenging/repair, a re"...
0x1400125ae  mov     ecx, esi
0x1400125b0  xor     ebx, ebx
0x1400125b2  xor     r8d, r8d
0x1400125b5  xor     edx, edx
0x1400125b7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400125bc  lea     edi, [rbx+1]
0x1400125bf  mov     [rbp+var_18], edi
0x1400125c2  jmp     loc_1400126B4
0x1400125c7  lea     rdx, [rbp+var_18]; int *
0x1400125cb  call    ?OnlineMaintenanceActionGet@@YAJKPEAH@Z; OnlineMaintenanceActionGet(ulong,int *)
0x1400125d0  lea     rax, [rbp+var_28]
0x1400125d4  mov     edi, 1
0x1400125d9  mov     r8d, edi; unsigned int
0x1400125dc  mov     [rsp+58h+var_38], rax; unsigned int *
0x1400125e1  lea     r9, aAutorepairneed; "AutoRepairNeeded"
0x1400125e8  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400125ef  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1400125f4  mov     ebx, eax
0x1400125f6  mov     esi, 4000000h
0x1400125fb  test    eax, eax
0x1400125fd  jns     short loc_140012614
0x1400125ff  xor     ebx, ebx
0x140012601  lea     r9, aFailedToReadAu; "Failed to read AutoRepairNeeded."
0x140012608  xor     r8d, r8d
0x14001260b  xor     edx, edx
0x14001260d  mov     ecx, esi
0x14001260f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012614  cmp     [rbp+var_18], r15d
0x140012618  jz      short loc_140012635
0x14001261a  cmp     [rbp+var_28], r15d
0x14001261e  jnz     short loc_140012635
0x140012620  lea     r9, aMaintNothingTo; "Maint: Nothing to do, so skipping"
0x140012627  xor     r8d, r8d
0x14001262a  xor     edx, edx
0x14001262c  mov     ecx, esi
0x14001262e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012633  jmp     short loc_1400126AA
0x140012635  xor     edx, edx; dwCoInit
0x140012637  xor     ecx, ecx; pvReserved
0x140012639  call    cs:__imp_CoInitializeEx
0x14001263f  mov     ebx, eax
0x140012641  test    eax, eax
0x140012643  jns     short loc_14001265A
0x140012645  lea     r9, aFailedToInitia; "Failed to initialize COM."
0x14001264c  mov     r8d, edi
0x14001264f  mov     edx, eax
0x140012651  mov     ecx, esi
0x140012653  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012658  jmp     short loc_1400126AA
0x14001265a  lea     rdx, [rbp+var_20]
0x14001265e  xor     ecx, ecx
0x140012660  mov     r15d, edi
0x140012663  call    TiCoreGetWorkerProcess
0x140012668  mov     ebx, eax
0x14001266a  test    eax, eax
0x14001266c  jns     short loc_140012677
0x14001266e  lea     r9, aFailedToGetWor_0; "Failed to get worker process."
0x140012675  jmp     short loc_14001264C
0x140012677  mov     rcx, [rbp+var_20]
0x14001267b  lea     r8, [rbp+var_18]
0x14001267f  mov     edx, edi
0x140012681  mov     rax, [rcx]
0x140012684  mov     rax, [rax+60h]
0x140012688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001268d  mov     ebx, eax
0x14001268f  test    eax, eax
0x140012691  jns     short loc_1400126AA
0x140012693  lea     r9, aWarningFailedT_0; "Warning: Failed to execute idle scaveng"...
0x14001269a  mov     dword ptr [rsp+58h+var_38], eax
0x14001269e  mov     r8d, edi
0x1400126a1  mov     edx, eax
0x1400126a3  mov     ecx, esi
0x1400126a5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400126aa  cmp     [rbp+var_18], 0
0x1400126ae  jnz     short loc_1400126B4
0x1400126b0  test    ebx, ebx
0x1400126b2  jns     short loc_1400126F6
0x1400126b4  lea     r9, aSignalingIdles_0; "Signaling IdleScavenge and/or repair co"...
0x1400126bb  xor     r8d, r8d
0x1400126be  xor     edx, edx
0x1400126c0  mov     ecx, esi
0x1400126c2  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400126c7  mov     rcx, [r14+18h]
0x1400126cb  mov     edx, ebx
0x1400126cd  mov     rax, [rcx]
0x1400126d0  mov     rax, [rax+20h]
0x1400126d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126d9  mov     ebx, eax
0x1400126db  test    eax, eax
0x1400126dd  jns     short loc_1400126F6
0x1400126df  lea     r9, aWarningUnableT_0; "Warning: Unable to mark idle scavenging"...
0x1400126e6  mov     dword ptr [rsp+58h+var_38], eax
0x1400126ea  mov     r8d, edi
0x1400126ed  mov     edx, eax
0x1400126ef  mov     ecx, esi
0x1400126f1  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400126f6  xor     eax, eax
0x1400126f8  xchg    eax, [r14+28h]
0x1400126fc  mov     rcx, [r14+8]
0x140012700  movsxd  rcx, dword ptr [rcx+4]
0x140012704  add     rcx, 8
0x140012708  add     rcx, r14
0x14001270b  mov     rax, [rcx]
0x14001270e  mov     rax, [rax+10h]
0x140012712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012717  mov     rcx, [rbp+var_20]
0x14001271b  test    rcx, rcx
0x14001271e  jz      short loc_140012734
0x140012720  mov     rax, [rcx]
0x140012723  mov     rax, [rax+10h]
0x140012727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001272c  mov     [rbp+var_20], 0
0x140012734  test    r15d, r15d
0x140012737  jz      short loc_14001273F
0x140012739  call    cs:__imp_CoUninitialize
0x14001273f  mov     eax, ebx
0x140012741  jmp     short loc_140012748
0x140012743  mov     eax, 8004130Bh
0x140012748  mov     rcx, [rbp+var_10]
0x14001274c  xor     rcx, rsp; StackCookie
0x14001274f  call    __security_check_cookie
0x140012754  add     rsp, 58h
0x140012758  pop     r15
0x14001275a  pop     r14
0x14001275c  pop     rdi
0x14001275d  pop     rsi
0x14001275e  pop     rbx
0x14001275f  pop     rbp
0x140012760  retn
```
