# CCbsWorker::IdleScavenge(int,int *)

- ea: `0x14000b174`
- end: `0x14000b252`
- name: `?IdleScavenge@CCbsWorker@@UEAAJHPEAH@Z`
- size: `222`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400096d0`

## callees

- `0x140007eb8`
- `0x140008b30`
- `0x14000914c`
- `0x1400091d8`
- `0x14000b174`
- `0x14000caa0`
- `0x14000e328`
- `0x140016bd0`

## string_xrefs

- `0x14000b19d`: `No complete result specified`
- `0x14000b225`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::IdleScavenge(CCbsWorker *this, int a2, int *a3)
{
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  _BYTE v11[72]; // [rsp+30h] [rbp-48h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v11,
    (CCbsWorker *)((char *)this - 64),
    (bool)a3);
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = "No complete result specified";
    v8 = 2147500035LL;
LABEL_3:
    CBSWdsLog(0x4000000, v8, 1, v7);
    goto LABEL_12;
  }
  v6 = 0;
  *a3 = 0;
  if ( !vpCbsSessionClassFactory )
  {
    v9 = TiWorkerCoreInitialize(*((unsigned int *)this - 6), &vpCbsSessionClassFactory);
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = "Failed to initialize CBS class factory.";
LABEL_7:
      v8 = (unsigned int)v9;
      goto LABEL_3;
    }
  }
  MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v11);
  if ( a2 )
  {
    v9 = TiWorkerCoreServiceIdleProcessing(a3);
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = "Failed to run idle scavenge";
      goto LABEL_7;
    }
  }
  else
  {
    CCbsWorker::StopIdleProcessing();
  }
LABEL_12:
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::IdleScavenge");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v11);
  return v6;
}

```

## disassembly

```asm
0x14000b174  push    rbx
0x14000b176  push    rbp
0x14000b177  push    rsi
0x14000b178  push    rdi
0x14000b179  sub     rsp, 58h
0x14000b17d  mov     ebp, edx
0x14000b17f  mov     rsi, rcx
0x14000b182  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000b186  mov     rdi, r8
0x14000b189  lea     rcx, [rsp+78h+var_48]; this
0x14000b18e  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000b193  test    rdi, rdi
0x14000b196  jnz     short loc_14000B1B8
0x14000b198  mov     ebx, 80004003h
0x14000b19d  lea     r9, aNoCompleteResu; "No complete result specified"
0x14000b1a4  mov     edx, ebx
0x14000b1a6  mov     r8d, 1
0x14000b1ac  mov     ecx, 4000000h
0x14000b1b1  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b1b6  jmp     short loc_14000B20F
0x14000b1b8  xor     ebx, ebx
0x14000b1ba  mov     [rdi], ebx
0x14000b1bc  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, rbx; IClassFactory * vpCbsSessionClassFactory
0x14000b1c3  jnz     short loc_14000B1E5
0x14000b1c5  mov     ecx, [rsi-18h]
0x14000b1c8  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000b1cf  call    TiWorkerCoreInitialize
0x14000b1d4  mov     ebx, eax
0x14000b1d6  test    eax, eax
0x14000b1d8  jns     short loc_14000B1E5
0x14000b1da  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000b1e1  mov     edx, eax
0x14000b1e3  jmp     short loc_14000B1A6
0x14000b1e5  lea     rcx, [rsp+78h+var_48]; this
0x14000b1ea  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000b1ef  test    ebp, ebp
0x14000b1f1  jz      short loc_14000B20A
0x14000b1f3  mov     rcx, rdi
0x14000b1f6  call    TiWorkerCoreServiceIdleProcessing
0x14000b1fb  mov     ebx, eax
0x14000b1fd  test    eax, eax
0x14000b1ff  jns     short loc_14000B20F
0x14000b201  lea     r9, aFailedToRunIdl; "Failed to run idle scavenge"
0x14000b208  jmp     short loc_14000B1E1
0x14000b20a  call    ?StopIdleProcessing@CCbsWorker@@SAJXZ; CCbsWorker::StopIdleProcessing(void)
0x14000b20f  mov     eax, gs:179Ch
0x14000b217  test    eax, eax
0x14000b219  jz      short loc_14000B23D
0x14000b21b  lea     rax, aCcbsworkerIdle; "CCbsWorker::IdleScavenge"
0x14000b222  xor     r8d, r8d
0x14000b225  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000b22c  mov     [rsp+78h+var_58], rax
0x14000b231  xor     edx, edx
0x14000b233  mov     ecx, 4000000h
0x14000b238  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000b23d  lea     rcx, [rsp+78h+var_48]; this
0x14000b242  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000b247  mov     eax, ebx
0x14000b249  add     rsp, 58h
0x14000b24d  pop     rdi
0x14000b24e  pop     rsi
0x14000b24f  pop     rbp
0x14000b250  pop     rbx
0x14000b251  retn
```
