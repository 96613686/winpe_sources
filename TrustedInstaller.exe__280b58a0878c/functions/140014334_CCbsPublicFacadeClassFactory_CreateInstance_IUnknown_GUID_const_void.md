# CCbsPublicFacadeClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140014334`
- end: `0x1400145bb`
- name: `?CreateInstance@CCbsPublicFacadeClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `647`
- prototype: `__int64 __fastcall(CCbsPublicFacadeClassFactory *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140014320`

## callees

- `0x1400023e0`
- `0x140006344`
- `0x14000695c`
- `0x140007edc`
- `0x14000ca98`
- `0x14000ee94`
- `0x140014334`
- `0x14001524c`
- `0x140015644`
- `0x140017658`
- `0x14001a7e4`
- `0x1400200b8`
- `0x14002a940`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400143b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400143b5`

## string_xrefs

- `0x140014534`: `Failed to get class factory for service: %u`
- `0x1400143c7`: `TI: Startup still running, not able to create object:%u`
- `0x14001442e`: `Caller that requires service %d does not have admin privilege.`

## pseudocode

```c
__int64 __fastcall CCbsPublicFacadeClassFactory::CreateInstance(
        CCbsPublicFacadeClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v8; // ebx
  unsigned __int64 i; // r14
  HKEY v10; // rcx
  __int64 v11; // r8
  int IsAdministrator; // eax
  struct IUnknown *v13; // rdx
  int GenValObjInterface; // eax
  int WorkerProcess; // eax
  int v16; // eax
  wchar_t *String1; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-38h] BYREF
  void *v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF

  v20 = 0;
  v21 = 0;
  String1 = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "No object result specified");
    goto LABEL_30;
  }
  v8 = 0;
  for ( i = 0; i < 0xA; ++i )
  {
    if ( MakeSureStartupProcessingComplete(0) )
      goto LABEL_9;
    v8 = -2146498302;
    Sleep(0x3E8u);
  }
  if ( v8 < 0 )
  {
    CBSWdsLogLight(
      0x4000000,
      (unsigned int)v8,
      1,
      "TI: Startup still running, not able to create object:%u",
      *((_DWORD *)this - 6));
    goto LABEL_30;
  }
LABEL_9:
  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v19, (struct MonitoredCritSec *)&vTiLock, 1);
  v19[0] = &TiCoreLocker::`vftable';
  if ( vbShuttingdown )
  {
    v8 = -2147023781;
  }
  else
  {
    if ( *((_DWORD *)this - 6) == 3 )
      goto LABEL_16;
    IsAdministrator = EnsureCallerIsAdministrator();
    v8 = IsAdministrator;
    if ( IsAdministrator < 0 )
    {
      CBSWdsLogLight(
        0x4000000,
        (unsigned int)IsAdministrator,
        1,
        "Caller that requires service %d does not have admin privilege.",
        *((_DWORD *)this - 6));
      goto LABEL_29;
    }
    if ( *((_DWORD *)this - 6) == 3 )
    {
LABEL_16:
      v8 = CbsRegQueryStringValue(v10, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", v11, L"EditionID", &String1);
      if ( v8 < 0 || wcscmp_0(String1, L"ServerAzureCor") )
      {
        GenValObjInterface = CCbsPublicFacadeClassFactory::GetGenValObjInterface(
                               (CCbsPublicFacadeClassFactory *)((char *)this - 48),
                               v13,
                               a3,
                               a4);
        v8 = GenValObjInterface;
        if ( GenValObjInterface < 0 )
          CBSWdsLogLight(0x4000000, (unsigned int)GenValObjInterface, 1, "Failed to get genvalobj interface");
      }
      goto LABEL_29;
    }
    WorkerProcess = TiCoreGetWorkerProcess(1, &v20);
    v8 = WorkerProcess;
    if ( WorkerProcess >= 0 )
    {
      if ( (*(int (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)v20 + 40LL))(
             v20,
             *((unsigned int *)this - 6),
             &v21) < 0 )
      {
        v16 = ReboundTiWorkerIfNecessary(&v20);
        v8 = v16;
        if ( v16 < 0 )
        {
          CBSWdsLogLight(0x4000000, (unsigned int)v16, 1, "Failed to start TiWorker.");
          goto LABEL_29;
        }
        v8 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)v20 + 40LL))(
               v20,
               *((unsigned int *)this - 6),
               &v21);
        if ( v8 < 0 )
        {
          CBSWdsLogLight(
            0x4000000,
            (unsigned int)v8,
            1,
            "Failed to get class factory for service: %u",
            *((_DWORD *)this - 6));
          goto LABEL_29;
        }
      }
      v8 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, const struct _GUID *, void **))(*(_QWORD *)v21 + 24LL))(
             v21,
             a2,
             a3,
             a4);
      goto LABEL_29;
    }
    CBSWdsLogLight(0x4000000, (unsigned int)WorkerProcess, 1, "Failed to get worker process.");
  }
LABEL_29:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v19);
LABEL_30:
  if ( v20 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&String1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140014334  push    rbp
0x140014336  push    rbx
0x140014337  push    rsi
0x140014338  push    r12
0x14001433a  push    r13
0x14001433c  push    r14
0x14001433e  push    r15
0x140014340  mov     rbp, rsp
0x140014343  sub     rsp, 70h
0x140014347  mov     rax, cs:__security_cookie
0x14001434e  xor     rax, rsp
0x140014351  mov     [rbp+var_10], rax
0x140014355  xor     eax, eax
0x140014357  mov     r15, r9
0x14001435a  mov     [rbp+var_20], rax
0x14001435e  mov     r12, r8
0x140014361  mov     [rbp+var_18], rax
0x140014365  mov     r13, rdx
0x140014368  mov     [rbp+String1], rax
0x14001436c  mov     rsi, rcx
0x14001436f  test    r9, r9
0x140014372  jnz     short loc_140014395
0x140014374  mov     ebx, 80004003h
0x140014379  lea     r9, aNoObjectResult; "No object result specified"
0x140014380  mov     edx, ebx
0x140014382  lea     r8d, [r15+1]
0x140014386  mov     ecx, 4000000h
0x14001438b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014390  jmp     loc_14001456A
0x140014395  mov     ebx, eax
0x140014397  mov     r14, rax
0x14001439a  cmp     r14, 0Ah
0x14001439e  jnb     short loc_1400143C0
0x1400143a0  xor     ecx, ecx; bool
0x1400143a2  call    ?MakeSureStartupProcessingComplete@@YA_N_N@Z; MakeSureStartupProcessingComplete(bool)
0x1400143a7  test    al, al
0x1400143a9  jnz     short loc_1400143E9
0x1400143ab  mov     ecx, 3E8h; dwMilliseconds
0x1400143b0  mov     ebx, 800F0902h
0x1400143b5  call    cs:__imp_Sleep
0x1400143bb  inc     r14
0x1400143be  jmp     short loc_14001439A
0x1400143c0  test    ebx, ebx
0x1400143c2  jns     short loc_1400143E9
0x1400143c4  mov     eax, [rsi-18h]
0x1400143c7  lea     r9, aTiStartupStill; "TI: Startup still running, not able to "...
0x1400143ce  mov     r8d, 1
0x1400143d4  mov     dword ptr [rsp+70h+var_50], eax
0x1400143d8  mov     edx, ebx
0x1400143da  mov     ecx, 4000000h
0x1400143df  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400143e4  jmp     loc_14001456A
0x1400143e9  mov     r8b, 1; bool
0x1400143ec  lea     rdx, vTiLock; struct MonitoredCritSec *
0x1400143f3  lea     rcx, [rbp+var_38]; this
0x1400143f7  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x1400143fc  cmp     cs:?vbShuttingdown@@3HA, 0; int vbShuttingdown
0x140014403  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x14001440a  mov     [rbp+var_38], rax
0x14001440e  jz      short loc_14001441A
0x140014410  mov     ebx, 8007045Bh
0x140014415  jmp     loc_140014561
0x14001441a  cmp     dword ptr [rsi-18h], 3
0x14001441e  jz      short loc_140014456
0x140014420  call    EnsureCallerIsAdministrator
0x140014425  mov     ebx, eax
0x140014427  test    eax, eax
0x140014429  jns     short loc_140014450
0x14001442b  mov     ecx, [rsi-18h]
0x14001442e  lea     r9, aCallerThatRequ; "Caller that requires service %d does no"...
0x140014435  mov     dword ptr [rsp+70h+var_50], ecx
0x140014439  mov     edx, eax
0x14001443b  mov     r8d, 1
0x140014441  mov     ecx, 4000000h
0x140014446  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001444b  jmp     loc_140014561
0x140014450  cmp     dword ptr [rsi-18h], 3
0x140014454  jnz     short loc_1400144C7
0x140014456  lea     rax, [rbp+String1]
0x14001445a  lea     r9, aEditionid; "EditionID"
0x140014461  mov     [rsp+70h+var_50], rax; wchar_t **
0x140014466  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001446d  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x140014472  mov     ebx, eax
0x140014474  test    eax, eax
0x140014476  js      short loc_140014490
0x140014478  mov     rcx, [rbp+String1]; String1
0x14001447c  lea     rdx, aServerazurecor; "ServerAzureCor"
0x140014483  call    wcscmp_0
0x140014488  test    eax, eax
0x14001448a  jz      loc_140014561
0x140014490  mov     r9, r15; void **
0x140014493  lea     rcx, [rsi-30h]; this
0x140014497  mov     r8, r12; struct _GUID *
0x14001449a  call    ?GetGenValObjInterface@CCbsPublicFacadeClassFactory@@AEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CCbsPublicFacadeClassFactory::GetGenValObjInterface(IUnknown *,_GUID const &,void * *)
0x14001449f  mov     ebx, eax
0x1400144a1  test    eax, eax
0x1400144a3  jns     loc_140014561
0x1400144a9  lea     r9, aFailedToGetGen_0; "Failed to get genvalobj interface"
0x1400144b0  mov     r8d, 1
0x1400144b6  mov     edx, eax
0x1400144b8  mov     ecx, 4000000h
0x1400144bd  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400144c2  jmp     loc_140014561
0x1400144c7  lea     rdx, [rbp+var_20]
0x1400144cb  mov     cl, 1
0x1400144cd  call    TiCoreGetWorkerProcess
0x1400144d2  mov     ebx, eax
0x1400144d4  test    eax, eax
0x1400144d6  jns     short loc_1400144E1
0x1400144d8  lea     r9, aFailedToGetWor_0; "Failed to get worker process."
0x1400144df  jmp     short loc_1400144B0
0x1400144e1  mov     rcx, [rbp+var_20]
0x1400144e5  lea     r8, [rbp+var_18]
0x1400144e9  mov     edx, [rsi-18h]
0x1400144ec  mov     rax, [rcx]
0x1400144ef  mov     rax, [rax+28h]
0x1400144f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144f8  test    eax, eax
0x1400144fa  jns     short loc_140014546
0x1400144fc  lea     rcx, [rbp+var_20]
0x140014500  call    ReboundTiWorkerIfNecessary
0x140014505  mov     ebx, eax
0x140014507  test    eax, eax
0x140014509  jns     short loc_140014514
0x14001450b  lea     r9, aFailedToStartT; "Failed to start TiWorker."
0x140014512  jmp     short loc_1400144B0
0x140014514  mov     rcx, [rbp+var_20]
0x140014518  lea     r8, [rbp+var_18]
0x14001451c  mov     edx, [rsi-18h]
0x14001451f  mov     rax, [rcx]
0x140014522  mov     rax, [rax+28h]
0x140014526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001452b  mov     ebx, eax
0x14001452d  test    eax, eax
0x14001452f  jns     short loc_140014546
0x140014531  mov     eax, [rsi-18h]
0x140014534  lea     r9, aFailedToGetCla; "Failed to get class factory for service"...
0x14001453b  mov     dword ptr [rsp+70h+var_50], eax
0x14001453f  mov     edx, ebx
0x140014541  jmp     loc_14001443B
0x140014546  mov     rcx, [rbp+var_18]
0x14001454a  mov     r9, r15
0x14001454d  mov     r8, r12
0x140014550  mov     rdx, r13
0x140014553  mov     rax, [rcx]
0x140014556  mov     rax, [rax+18h]
0x14001455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001455f  mov     ebx, eax
0x140014561  lea     rcx, [rbp+var_38]; this
0x140014565  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14001456a  mov     rcx, [rbp+var_20]
0x14001456e  test    rcx, rcx
0x140014571  jz      short loc_14001457F
0x140014573  mov     rax, [rcx]
0x140014576  mov     rax, [rax+10h]
0x14001457a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001457f  mov     rcx, [rbp+var_18]
0x140014583  test    rcx, rcx
0x140014586  jz      short loc_140014594
0x140014588  mov     rax, [rcx]
0x14001458b  mov     rax, [rax+10h]
0x14001458f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014594  lea     rcx, [rbp+String1]
0x140014598  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001459d  mov     eax, ebx
0x14001459f  mov     rcx, [rbp+var_10]
0x1400145a3  xor     rcx, rsp; StackCookie
0x1400145a6  call    __security_check_cookie
0x1400145ab  add     rsp, 70h
0x1400145af  pop     r15
0x1400145b1  pop     r14
0x1400145b3  pop     r13
0x1400145b5  pop     r12
0x1400145b7  pop     rsi
0x1400145b8  pop     rbx
0x1400145b9  pop     rbp
0x1400145ba  retn
```
