# ServiceManager::AttemptRepairMapDataAsync(void)

- ea: `0x180013174`
- end: `0x180013239`
- name: `?AttemptRepairMapDataAsync@ServiceManager@@AEAAXXZ`
- size: `197`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180015898`
- `0x180016b60`

## callees

- `0x180009b74`
- `0x18001189c`
- `0x180013174`
- `0x18001be24`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800131fd`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800131fd`

## string_xrefs

- `0x1800131ab`: `MapsRepairing`
- `0x1800131ee`: `ServiceManager::AttemptRepairMapDataAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceManager::AttemptRepairMapDataAsync(ServiceManager *this)
{
  int v2; // eax
  struct _TP_CALLBACK_ENVIRON_V3 *v3; // rcx
  __int128 v4; // [rsp+60h] [rbp-18h] BYREF

  *((_BYTE *)this + 4312) = 1;
  if ( ClientsTracker::HasClientsInForeground((LPCRITICAL_SECTION)((char *)this + 3816)) )
  {
    v2 = ServiceManager::ShowToast(
           this,
           0x6Cu,
           0x6Du,
           L"MapsRepairing",
           0,
           0,
           0,
           &dword_180027ABC,
           &dword_180027ABC,
           0,
           0);
    if ( v2 < 0 )
      ZTraceReportIgnore(v2, "ServiceManager::AttemptRepairMapDataAsync", 4031, this);
  }
  v3 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)this + 424);
  *(_QWORD *)&v4 = ServiceManager::AttemptRepairMapData;
  DWORD2(v4) = 0;
  Threadpool::QueueThis<ServiceManager>(v3, (__int64)this, &v4);
}

```

## disassembly

```asm
0x180013174  push    rbx
0x180013176  sub     rsp, 70h
0x18001317a  mov     rbx, rcx
0x18001317d  mov     byte ptr [rcx+10D8h], 1
0x180013184  add     rcx, 0EE8h; lpCriticalSection
0x18001318b  call    ?HasClientsInForeground@ClientsTracker@@QEAA_NXZ; ClientsTracker::HasClientsInForeground(void)
0x180013190  test    al, al
0x180013192  jz      short loc_180013203
0x180013194  mov     [rsp+78h+var_28], 0; unsigned int
0x18001319c  lea     rax, dword_180027ABC
0x1800131a3  mov     [rsp+78h+var_30], 0; unsigned int
0x1800131ab  lea     r9, aMapsrepairing; "MapsRepairing"
0x1800131b2  mov     [rsp+78h+var_38], rax; unsigned __int16 *
0x1800131b7  mov     edx, 6Ch ; 'l'; unsigned int
0x1800131bc  mov     [rsp+78h+var_40], rax; unsigned __int16 *
0x1800131c1  mov     rcx, rbx; this
0x1800131c4  mov     [rsp+78h+var_48], 0; int
0x1800131cc  mov     [rsp+78h+var_50], 0; unsigned __int64
0x1800131d5  lea     r8d, [rdx+1]; unsigned int
0x1800131d9  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x1800131e2  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x1800131e7  test    eax, eax
0x1800131e9  jns     short loc_180013203
0x1800131eb  mov     r9, rbx
0x1800131ee  lea     rdx, aServicemanager_13; "ServiceManager::AttemptRepairMapDataAsy"...
0x1800131f5  mov     r8d, 0FBFh
0x1800131fb  mov     ecx, eax
0x1800131fd  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180013203  mov     rcx, [rbx+0D40h]; pcbe
0x18001320a  lea     rax, ?AttemptRepairMapData@ServiceManager@@AEAAJXZ; ServiceManager::AttemptRepairMapData(void)
0x180013211  mov     [rsp+78h+var_18], rax
0x180013216  lea     r8, [rsp+78h+var_18]
0x18001321b  mov     eax, [rsp+78h+var_C]
0x18001321f  mov     rdx, rbx
0x180013222  mov     [rsp+78h+var_C], eax
0x180013226  mov     [rsp+78h+var_10], 0
0x18001322e  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x180013233  add     rsp, 70h
0x180013237  pop     rbx
0x180013238  retn
```
