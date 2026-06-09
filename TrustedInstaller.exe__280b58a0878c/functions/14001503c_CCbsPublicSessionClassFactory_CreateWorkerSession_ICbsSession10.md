# CCbsPublicSessionClassFactory::CreateWorkerSession(ICbsSession10 * *)

- ea: `0x14001503c`
- end: `0x140015243`
- name: `?CreateWorkerSession@CCbsPublicSessionClassFactory@@QEAAJPEAPEAUICbsSession10@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(CCbsPublicSessionClassFactory *__hidden this, struct ICbsSession10 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400106c4`
- `0x140010d00`

## callees

- `0x1400023e0`
- `0x140006344`
- `0x14000695c`
- `0x140007edc`
- `0x14000ca98`
- `0x140013fbc`
- `0x14001503c`
- `0x140015644`
- `0x140017658`
- `0x140020c84`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140015134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001517e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140015134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001517e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400151db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400151db`

## string_xrefs

- `0x14001510e`: `Failed to get client token.`
- `0x1400151a7`: `Failed to create a worker session`

## pseudocode

```c
__int64 __fastcall CCbsPublicSessionClassFactory::CreateWorkerSession(
        CCbsPublicSessionClassFactory *this,
        struct ICbsSession10 **a2)
{
  bool v4; // r8
  unsigned int v5; // ebx
  int WorkerProcess; // eax
  int ImpersonationToken; // eax
  char *v8; // rdi
  int (__fastcall *v9)(void *, _QWORD, _QWORD, char *, __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  int v11; // eax
  __int64 (__fastcall *v12)(void *, _QWORD, _QWORD, char *, __int64 *); // rbx
  DWORD v13; // eax
  int v14; // eax
  HANDLE hObject; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v18[24]; // [rsp+50h] [rbp-30h] BYREF
  void *v19; // [rsp+68h] [rbp-18h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h] BYREF

  v20 = 0;
  v19 = 0;
  hObject = 0;
  MakeSureStartupProcessingComplete(1);
  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v17, (struct MonitoredCritSec *)&vTiLock, 1);
  v17[0] = &TiCoreLocker::`vftable';
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v18,
    (CCbsPublicSessionClassFactory *)((char *)this + 32),
    v4);
  if ( !a2 )
  {
    v5 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "No session result specified");
    goto LABEL_17;
  }
  WorkerProcess = TiCoreGetWorkerProcess(1, &v19);
  v5 = WorkerProcess;
  if ( WorkerProcess < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)WorkerProcess, 1, "Failed to get worker process.");
    goto LABEL_17;
  }
  ImpersonationToken = ComGetImpersonationToken(&hObject);
  v8 = (char *)hObject;
  v5 = ImpersonationToken;
  if ( ImpersonationToken >= 0 )
  {
    v9 = *(int (__fastcall **)(void *, _QWORD, _QWORD, char *, __int64 *))(*(_QWORD *)v19 + 32LL);
    CurrentProcessId = GetCurrentProcessId();
    if ( v9(v19, 0, CurrentProcessId, v8, &v20) >= 0 )
      goto LABEL_14;
    v11 = ReboundTiWorkerIfNecessary(&v19);
    v5 = v11;
    if ( v11 < 0 )
    {
      CBSWdsLogLight(0x4000000, (unsigned int)v11, 1, "Failed to start TiWorker.");
      goto LABEL_15;
    }
    v12 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, char *, __int64 *))(*(_QWORD *)v19 + 32LL);
    v13 = GetCurrentProcessId();
    v14 = v12(v19, 0, v13, v8, &v20);
    v5 = v14;
    if ( v14 >= 0 )
LABEL_14:
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICbsSession10 **))v20)(
             v20,
             &GUID_f112757a_565b_4260_bd05_9fa34417349a,
             a2);
    else
      CBSWdsLogLight(0x4000000, (unsigned int)v14, 1, "Failed to create a worker session");
  }
  else
  {
    CBSWdsLogLight(0x4000000, (unsigned int)ImpersonationToken, 1, "Failed to get client token.");
  }
LABEL_15:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
LABEL_17:
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v19 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v18);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v17);
  return v5;
}

```

## disassembly

```asm
0x14001503c  mov     [rsp-18h+arg_0], rbx
0x140015041  mov     [rsp-18h+arg_10], rsi
0x140015046  push    rbp
0x140015047  push    rdi
0x140015048  push    r15
0x14001504a  mov     rbp, rsp
0x14001504d  sub     rsp, 80h
0x140015054  mov     rax, cs:__security_cookie
0x14001505b  xor     rax, rsp
0x14001505e  mov     [rbp+var_8], rax
0x140015062  mov     rbx, rcx
0x140015065  mov     [rbp+var_10], 0
0x14001506d  mov     r15d, 1
0x140015073  mov     [rbp+var_18], 0
0x14001507b  mov     cl, r15b; bool
0x14001507e  mov     [rbp+hObject], 0
0x140015086  mov     rsi, rdx
0x140015089  call    ?MakeSureStartupProcessingComplete@@YA_N_N@Z; MakeSureStartupProcessingComplete(bool)
0x14001508e  mov     r8b, r15b; bool
0x140015091  lea     rdx, vTiLock; struct MonitoredCritSec *
0x140015098  lea     rcx, [rbp+var_48]; this
0x14001509c  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x1400150a1  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x1400150a8  lea     rdx, [rbx+20h]; struct AutoMonitoredCritSec *
0x1400150ac  mov     [rbp+var_48], rax
0x1400150b0  lea     rcx, [rbp+var_30]; this
0x1400150b4  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x1400150b9  test    rsi, rsi
0x1400150bc  jnz     short loc_1400150DE
0x1400150be  mov     ebx, 80004003h
0x1400150c3  lea     r9, aNoSessionResul; "No session result specified"
0x1400150ca  mov     edx, ebx
0x1400150cc  mov     r8d, r15d
0x1400150cf  mov     ecx, 4000000h
0x1400150d4  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400150d9  jmp     loc_1400151E1
0x1400150de  lea     rdx, [rbp+var_18]
0x1400150e2  mov     cl, r15b
0x1400150e5  call    TiCoreGetWorkerProcess
0x1400150ea  mov     ebx, eax
0x1400150ec  test    eax, eax
0x1400150ee  jns     short loc_1400150FB
0x1400150f0  lea     r9, aFailedToGetWor_0; "Failed to get worker process."
0x1400150f7  mov     edx, eax
0x1400150f9  jmp     short loc_1400150CC
0x1400150fb  lea     rcx, [rbp+hObject]
0x1400150ff  call    ComGetImpersonationToken
0x140015104  mov     rdi, [rbp+hObject]
0x140015108  mov     ebx, eax
0x14001510a  test    eax, eax
0x14001510c  jns     short loc_140015129
0x14001510e  lea     r9, aFailedToGetCli; "Failed to get client token."
0x140015115  mov     r8d, r15d
0x140015118  mov     edx, eax
0x14001511a  mov     ecx, 4000000h
0x14001511f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015124  jmp     loc_1400151CE
0x140015129  mov     rax, [rbp+var_18]
0x14001512d  mov     rcx, [rax]
0x140015130  mov     rbx, [rcx+20h]
0x140015134  call    cs:__imp_GetCurrentProcessId
0x14001513a  lea     rcx, [rbp+var_10]
0x14001513e  mov     r9, rdi
0x140015141  mov     [rsp+80h+var_60], rcx
0x140015146  mov     r8d, eax
0x140015149  mov     rcx, [rbp+var_18]
0x14001514d  xor     edx, edx
0x14001514f  mov     rax, rbx
0x140015152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015157  test    eax, eax
0x140015159  jns     short loc_1400151B3
0x14001515b  lea     rcx, [rbp+var_18]
0x14001515f  call    ReboundTiWorkerIfNecessary
0x140015164  mov     ebx, eax
0x140015166  test    eax, eax
0x140015168  jns     short loc_140015173
0x14001516a  lea     r9, aFailedToStartT; "Failed to start TiWorker."
0x140015171  jmp     short loc_140015115
0x140015173  mov     rax, [rbp+var_18]
0x140015177  mov     rcx, [rax]
0x14001517a  mov     rbx, [rcx+20h]
0x14001517e  call    cs:__imp_GetCurrentProcessId
0x140015184  lea     rcx, [rbp+var_10]
0x140015188  mov     r9, rdi
0x14001518b  mov     [rsp+80h+var_60], rcx
0x140015190  mov     r8d, eax
0x140015193  mov     rcx, [rbp+var_18]
0x140015197  xor     edx, edx
0x140015199  mov     rax, rbx
0x14001519c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151a1  mov     ebx, eax
0x1400151a3  test    eax, eax
0x1400151a5  jns     short loc_1400151B3
0x1400151a7  lea     r9, aFailedToCreate_26; "Failed to create a worker session"
0x1400151ae  jmp     loc_140015115
0x1400151b3  mov     rcx, [rbp+var_10]
0x1400151b7  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x1400151be  mov     r8, rsi
0x1400151c1  mov     rax, [rcx]
0x1400151c4  mov     rax, [rax]
0x1400151c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151cc  mov     ebx, eax
0x1400151ce  lea     rax, [rdi-1]
0x1400151d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400151d6  ja      short loc_1400151E1
0x1400151d8  mov     rcx, rdi; hObject
0x1400151db  call    cs:__imp_CloseHandle
0x1400151e1  mov     rcx, [rbp+var_10]
0x1400151e5  test    rcx, rcx
0x1400151e8  jz      short loc_1400151F6
0x1400151ea  mov     rax, [rcx]
0x1400151ed  mov     rax, [rax+10h]
0x1400151f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151f6  mov     rcx, [rbp+var_18]
0x1400151fa  test    rcx, rcx
0x1400151fd  jz      short loc_14001520B
0x1400151ff  mov     rax, [rcx]
0x140015202  mov     rax, [rax+10h]
0x140015206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001520b  lea     rcx, [rbp+var_30]; this
0x14001520f  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140015214  lea     rcx, [rbp+var_48]; this
0x140015218  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14001521d  mov     eax, ebx
0x14001521f  mov     rcx, [rbp+var_8]
0x140015223  xor     rcx, rsp; StackCookie
0x140015226  call    __security_check_cookie
0x14001522b  lea     r11, [rsp+80h+var_s0]
0x140015233  mov     rbx, [r11+20h]
0x140015237  mov     rsi, [r11+30h]
0x14001523b  mov     rsp, r11
0x14001523e  pop     r15
0x140015240  pop     rdi
0x140015241  pop     rbp
0x140015242  retn
```
