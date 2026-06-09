# CCbsPublicSessionClassFactory::CreateNonSessionObject(_GUID const &,void * *)

- ea: `0x140014d60`
- end: `0x140014efb`
- name: `?CreateNonSessionObject@CCbsPublicSessionClassFactory@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `411`
- prototype: `__int64 __fastcall(CCbsPublicSessionClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400108cc`

## callees

- `0x1400023e0`
- `0x140006344`
- `0x14000695c`
- `0x140007630`
- `0x140007edc`
- `0x14000ca98`
- `0x140014d60`
- `0x140015644`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x140014e6d`: `Failed to get class factory for service: %u`

## pseudocode

```c
__int64 __fastcall CCbsPublicSessionClassFactory::CreateNonSessionObject(
        CCbsPublicSessionClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  int v5; // ebx
  const char *v6; // r9
  __int64 v7; // rdx
  int WorkerProcess; // eax
  int (__fastcall *v9)(void *, _QWORD, __int64); // rbx
  __int64 InitPointer; // rax
  __int64 (__fastcall *v11)(void *, _QWORD, __int64); // rbx
  __int64 v12; // rax
  _QWORD v14[3]; // [rsp+30h] [rbp-30h] BYREF
  void *v15; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF

  v15 = 0;
  v16 = 0;
  MakeSureStartupProcessingComplete(1);
  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v14, (struct MonitoredCritSec *)&vTiLock, 1);
  v14[0] = &TiCoreLocker::`vftable';
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = "No object result specified";
    v7 = 2147500035LL;
LABEL_3:
    CBSWdsLogLight(0x4000000, v7, 1, v6);
    goto LABEL_13;
  }
  WorkerProcess = TiCoreGetWorkerProcess(1, &v15);
  v5 = WorkerProcess;
  if ( WorkerProcess < 0 )
  {
    v6 = "Failed to get worker process.";
LABEL_6:
    v7 = (unsigned int)WorkerProcess;
    goto LABEL_3;
  }
  v9 = *(int (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v15 + 40LL);
  InitPointer = Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v16);
  if ( v9(v15, *((unsigned int *)this + 6), InitPointer) >= 0 )
    goto LABEL_12;
  WorkerProcess = ReboundTiWorkerIfNecessary(&v15);
  v5 = WorkerProcess;
  if ( WorkerProcess < 0 )
  {
    v6 = "Failed to start TiWorker.";
    goto LABEL_6;
  }
  v11 = *(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v15 + 40LL);
  v12 = Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v16);
  v5 = v11(v15, *((unsigned int *)this + 6), v12);
  if ( v5 >= 0 )
LABEL_12:
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, void **))(*(_QWORD *)v16 + 24LL))(
           v16,
           0,
           &IID_ISxsStore,
           a3);
  else
    CBSWdsLogLight(0x4000000, (unsigned int)v5, 1, "Failed to get class factory for service: %u", *((_DWORD *)this + 6));
LABEL_13:
  if ( v15 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v14);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014d60  mov     [rsp-18h+arg_8], rbx
0x140014d65  push    rbp
0x140014d66  push    rsi
0x140014d67  push    rdi
0x140014d68  mov     rbp, rsp
0x140014d6b  sub     rsp, 60h
0x140014d6f  mov     rax, cs:__security_cookie
0x140014d76  xor     rax, rsp
0x140014d79  mov     [rbp+var_8], rax
0x140014d7d  mov     rdi, rcx
0x140014d80  mov     [rbp+var_18], 0
0x140014d88  mov     cl, 1; bool
0x140014d8a  mov     [rbp+var_10], 0
0x140014d92  mov     rsi, r8
0x140014d95  call    ?MakeSureStartupProcessingComplete@@YA_N_N@Z; MakeSureStartupProcessingComplete(bool)
0x140014d9a  mov     r8b, 1; bool
0x140014d9d  lea     rdx, vTiLock; struct MonitoredCritSec *
0x140014da4  lea     rcx, [rbp+var_30]; this
0x140014da8  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x140014dad  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x140014db4  mov     [rbp+var_30], rax
0x140014db8  test    rsi, rsi
0x140014dbb  jnz     short loc_140014DE0
0x140014dbd  mov     ebx, 80004003h
0x140014dc2  lea     r9, aNoObjectResult; "No object result specified"
0x140014dc9  mov     edx, ebx
0x140014dcb  mov     r8d, 1
0x140014dd1  mov     ecx, 4000000h
0x140014dd6  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014ddb  jmp     loc_140014EAA
0x140014de0  lea     rdx, [rbp+var_18]
0x140014de4  mov     cl, 1
0x140014de6  call    TiCoreGetWorkerProcess
0x140014deb  mov     ebx, eax
0x140014ded  test    eax, eax
0x140014def  jns     short loc_140014DFC
0x140014df1  lea     r9, aFailedToGetWor_0; "Failed to get worker process."
0x140014df8  mov     edx, eax
0x140014dfa  jmp     short loc_140014DCB
0x140014dfc  mov     rax, [rbp+var_18]
0x140014e00  mov     rcx, [rax]
0x140014e03  mov     rbx, [rcx+28h]
0x140014e07  lea     rcx, [rbp+var_10]
0x140014e0b  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140014e10  mov     edx, [rdi+18h]
0x140014e13  mov     r8, rax
0x140014e16  mov     rcx, [rbp+var_18]
0x140014e1a  mov     rax, rbx
0x140014e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e22  test    eax, eax
0x140014e24  jns     short loc_140014E8C
0x140014e26  lea     rcx, [rbp+var_18]
0x140014e2a  call    ReboundTiWorkerIfNecessary
0x140014e2f  mov     ebx, eax
0x140014e31  test    eax, eax
0x140014e33  jns     short loc_140014E3E
0x140014e35  lea     r9, aFailedToStartT; "Failed to start TiWorker."
0x140014e3c  jmp     short loc_140014DF8
0x140014e3e  mov     rax, [rbp+var_18]
0x140014e42  mov     rcx, [rax]
0x140014e45  mov     rbx, [rcx+28h]
0x140014e49  lea     rcx, [rbp+var_10]
0x140014e4d  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140014e52  mov     edx, [rdi+18h]
0x140014e55  mov     r8, rax
0x140014e58  mov     rcx, [rbp+var_18]
0x140014e5c  mov     rax, rbx
0x140014e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e64  mov     ebx, eax
0x140014e66  test    eax, eax
0x140014e68  jns     short loc_140014E8C
0x140014e6a  mov     eax, [rdi+18h]
0x140014e6d  lea     r9, aFailedToGetCla; "Failed to get class factory for service"...
0x140014e74  mov     r8d, 1
0x140014e7a  mov     [rsp+60h+var_40], eax
0x140014e7e  mov     edx, ebx
0x140014e80  mov     ecx, 4000000h
0x140014e85  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014e8a  jmp     short loc_140014EAA
0x140014e8c  mov     rcx, [rbp+var_10]
0x140014e90  lea     r8, IID_ISxsStore
0x140014e97  mov     r9, rsi
0x140014e9a  xor     edx, edx
0x140014e9c  mov     rax, [rcx]
0x140014e9f  mov     rax, [rax+18h]
0x140014ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ea8  mov     ebx, eax
0x140014eaa  mov     rcx, [rbp+var_18]
0x140014eae  test    rcx, rcx
0x140014eb1  jz      short loc_140014EBF
0x140014eb3  mov     rax, [rcx]
0x140014eb6  mov     rax, [rax+10h]
0x140014eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ebf  lea     rcx, [rbp+var_30]; this
0x140014ec3  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140014ec8  mov     rcx, [rbp+var_10]
0x140014ecc  test    rcx, rcx
0x140014ecf  jz      short loc_140014EDD
0x140014ed1  mov     rax, [rcx]
0x140014ed4  mov     rax, [rax+10h]
0x140014ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014edd  mov     eax, ebx
0x140014edf  mov     rcx, [rbp+var_8]
0x140014ee3  xor     rcx, rsp; StackCookie
0x140014ee6  call    __security_check_cookie
0x140014eeb  mov     rbx, [rsp+60h+arg_8]
0x140014ef3  add     rsp, 60h
0x140014ef7  pop     rdi
0x140014ef8  pop     rsi
0x140014ef9  pop     rbp
0x140014efa  retn
```
