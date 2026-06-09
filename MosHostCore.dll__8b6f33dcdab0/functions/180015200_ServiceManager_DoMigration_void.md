# ServiceManager::DoMigration(void)

- ea: `0x180015200`
- end: `0x180015463`
- name: `?DoMigration@ServiceManager@@AEAAJXZ`
- size: `611`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009bb4`
- `0x180009c04`
- `0x18000b6f4`
- `0x18000bf38`
- `0x18000c350`
- `0x180012cf0`
- `0x180015200`
- `0x180015ed0`
- `0x18001ba6c`
- `0x18001d870`
- `0x1800228ec`
- `0x1800229b8`
- `0x1800229d4`
- `0x180022a00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015226`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015438`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015438`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800152c6`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800152c6`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001540a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001540a`

## string_xrefs

- `0x180015242`: `ServiceManager::DoMigration`

## pseudocode

```c
__int64 __fastcall ServiceManager::DoMigration(ServiceManager *this)
{
  char *v2; // rsi
  int v3; // ebx
  char v4; // r14
  int v5; // r8d
  int v6; // ecx
  int v7; // eax
  int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned __int64 v11; // rdx
  int v12; // ebx
  char HasClientsOf; // al
  int v14; // eax
  _BYTE v16[16]; // [rsp+30h] [rbp-20h] BYREF
  int *v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v18; // [rsp+48h] [rbp-8h]
  int v19; // [rsp+80h] [rbp+30h] BYREF
  int v20; // [rsp+84h] [rbp+34h]
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF

  v2 = (char *)this + 3400;
  v3 = *((_DWORD *)this + 854);
  if ( v3 == GetCurrentThreadId() )
    __int2c();
  v4 = 0;
  CriticalSectionWithConditionVariable::Lock(v2, v16);
  if ( *((_DWORD *)this + 882) != 5 )
  {
    v5 = 3636;
    v6 = -2147024875;
LABEL_23:
    v10 = ZTraceReportOrigination(v6, "ServiceManager::DoMigration", v5, this);
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 880) != 6 || *((_DWORD *)this + 881) != 10 )
  {
    v5 = 3637;
    v6 = -2147467260;
    goto LABEL_23;
  }
  v4 = 1;
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, 2) )
  {
    v7 = ServiceManager::AttachClient((__int64)this, 2u, 1, 0, 0);
    if ( v7 < 0 )
    {
      v8 = 3643;
LABEL_10:
      v9 = v7;
LABEL_11:
      v10 = ZTraceReportPropagation(v9, "ServiceManager::DoMigration", v8, this);
LABEL_24:
      v12 = v10;
      goto LABEL_25;
    }
  }
  *((_DWORD *)this + 883) = 0;
  *((_DWORD *)this + 880) = 6;
  *((_DWORD *)this + 881) = 9;
  *((_QWORD *)this + 442) = 10;
  ServiceManager::FireOdmlStateChange(this);
  v7 = ServiceManager::SerializeOperationState(this);
  if ( v7 < 0 )
  {
    v8 = 3652;
    goto LABEL_10;
  }
  RelockableGate::Unlock((RelockableGate *)v16);
  v12 = MigrationEngine::MigrateMapData((ServiceManager *)((char *)this + 8), v11);
  RelockableGate::Relock((RelockableGate *)v16);
  if ( v12 < 0 )
  {
    v19 = 0;
    v20 = 5;
    v17 = &v19;
    v18 = &v21;
    if ( !(unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, &v17) )
    {
      v8 = 3666;
      v9 = v12;
      goto LABEL_11;
    }
    v12 = 0;
  }
  v19 = 0;
  v20 = 5;
  v17 = &v19;
  v18 = &v21;
  HasClientsOf = ClientsTracker::HasClientsOf((char *)this + 3816, &v17);
  *((_DWORD *)this + 885) = 0;
  if ( HasClientsOf )
  {
    *((_DWORD *)this + 881) = 10;
    *((_DWORD *)this + 884) = 11;
    ServiceManager::FireOdmlStateChange(this);
  }
  else
  {
    *((_DWORD *)this + 884) = 12;
    ServiceManager::FireOdmlStateChange(this);
    ServiceManager::UninitializeService(this);
    v7 = MigrationEngine::CommitMigration((ServiceManager *)((char *)this + 8));
    if ( v7 < 0 )
    {
      v8 = 3673;
      goto LABEL_10;
    }
  }
LABEL_25:
  if ( v12 < 0 )
  {
    if ( v4 )
    {
      v14 = MigrationEngine::RollbackMigration((ServiceManager *)((char *)this + 8), v12);
      if ( v14 < 0 )
        ZTraceReportIgnore(v14, "ServiceManager::DoMigration", 3685, this);
    }
  }
  RelockableGate::~RelockableGate((RelockableGate *)v16);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180015200  mov     [rsp-28h+arg_8], rbx
0x180015205  mov     [rsp-28h+arg_10], rsi
0x18001520a  push    rbp
0x18001520b  push    rdi
0x18001520c  push    r13
0x18001520e  push    r14
0x180015210  push    r15
0x180015212  mov     rbp, rsp
0x180015215  sub     rsp, 50h
0x180015219  mov     rdi, rcx
0x18001521c  lea     rsi, [rcx+0D48h]
0x180015223  mov     ebx, [rsi+10h]
0x180015226  call    cs:__imp_GetCurrentThreadId
0x18001522c  cmp     ebx, eax
0x18001522e  jnz     short loc_180015232
0x180015230  int     2Ch; Windows NT - assertion failure
0x180015232  xor     r14b, r14b
0x180015235  lea     rdx, [rbp+var_20]
0x180015239  mov     rcx, rsi
0x18001523c  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180015241  nop
0x180015242  lea     r13, aServicemanager_85; "ServiceManager::DoMigration"
0x180015249  cmp     dword ptr [rdi+0DC8h], 5
0x180015250  jz      short loc_180015262
0x180015252  mov     r8d, 0E34h
0x180015258  mov     ecx, 80070015h
0x18001525d  jmp     loc_180015404
0x180015262  cmp     dword ptr [rdi+0DC0h], 6
0x180015269  jnz     loc_1800153F9
0x18001526f  cmp     dword ptr [rdi+0DC4h], 0Ah
0x180015276  jnz     loc_1800153F9
0x18001527c  mov     r14d, 1
0x180015282  lea     r15, [rdi+0EE8h]
0x180015289  lea     ebx, [r14+1]
0x18001528d  mov     edx, ebx
0x18001528f  mov     rcx, r15
0x180015292  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x180015297  test    al, al
0x180015299  jnz     short loc_1800152D1
0x18001529b  mov     [rsp+50h+var_30], 0
0x1800152a4  xor     r9d, r9d
0x1800152a7  mov     r8d, r14d
0x1800152aa  mov     edx, ebx
0x1800152ac  mov     rcx, rdi
0x1800152af  call    ?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z; ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)
0x1800152b4  test    eax, eax
0x1800152b6  jns     short loc_1800152D1
0x1800152b8  mov     r8d, 0E3Bh
0x1800152be  mov     ecx, eax
0x1800152c0  mov     r9, rdi
0x1800152c3  mov     rdx, r13
0x1800152c6  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800152cc  jmp     loc_180015410
0x1800152d1  mov     dword ptr [rdi+0DCCh], 0
0x1800152db  mov     dword ptr [rdi+0DC0h], 6
0x1800152e5  mov     dword ptr [rdi+0DC4h], 9
0x1800152ef  mov     qword ptr [rdi+0DD0h], 0Ah
0x1800152fa  mov     rcx, rdi; this
0x1800152fd  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180015302  mov     rcx, rdi; this
0x180015305  call    ?SerializeOperationState@ServiceManager@@AEAAJXZ; ServiceManager::SerializeOperationState(void)
0x18001530a  test    eax, eax
0x18001530c  jns     short loc_180015316
0x18001530e  mov     r8d, 0E44h
0x180015314  jmp     short loc_1800152BE
0x180015316  lea     rcx, [rbp+var_20]; this
0x18001531a  call    ?Unlock@RelockableGate@@QEAAXXZ; RelockableGate::Unlock(void)
0x18001531f  lea     rcx, [rdi+8]; this
0x180015323  call    ?MigrateMapData@MigrationEngine@@IEAAJXZ; MigrationEngine::MigrateMapData(void)
0x180015328  mov     ebx, eax
0x18001532a  lea     rcx, [rbp+var_20]; this
0x18001532e  call    ?Relock@RelockableGate@@QEAAXXZ; RelockableGate::Relock(void)
0x180015333  test    ebx, ebx
0x180015335  jns     short loc_180015367
0x180015337  mov     [rbp+arg_0], 0
0x18001533e  mov     [rbp+arg_4], 5
0x180015345  lea     rax, [rbp+arg_0]
0x180015349  mov     [rbp+var_10], rax
0x18001534d  lea     rax, [rbp+arg_8]
0x180015351  mov     [rbp+var_8], rax
0x180015355  lea     rdx, [rbp+var_10]
0x180015359  mov     rcx, r15
0x18001535c  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x180015361  test    al, al
0x180015363  jz      short loc_1800153D1
0x180015365  xor     ebx, ebx
0x180015367  mov     [rbp+arg_0], 0
0x18001536e  mov     [rbp+arg_4], 5
0x180015375  lea     rax, [rbp+arg_0]
0x180015379  mov     [rbp+var_10], rax
0x18001537d  lea     rax, [rbp+arg_8]
0x180015381  mov     [rbp+var_8], rax
0x180015385  lea     rdx, [rbp+var_10]
0x180015389  mov     rcx, r15
0x18001538c  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x180015391  mov     dword ptr [rdi+0DD4h], 0
0x18001539b  mov     rcx, rdi; this
0x18001539e  test    al, al
0x1800153a0  jnz     short loc_1800153DE
0x1800153a2  mov     dword ptr [rdi+0DD0h], 0Ch
0x1800153ac  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x1800153b1  mov     rcx, rdi; this
0x1800153b4  call    ?UninitializeService@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeService(void)
0x1800153b9  lea     rcx, [rdi+8]; this
0x1800153bd  call    ?CommitMigration@MigrationEngine@@IEAAJXZ; MigrationEngine::CommitMigration(void)
0x1800153c2  test    eax, eax
0x1800153c4  jns     short loc_180015412
0x1800153c6  mov     r8d, 0E59h
0x1800153cc  jmp     loc_1800152BE
0x1800153d1  mov     r8d, 0E52h
0x1800153d7  mov     ecx, ebx
0x1800153d9  jmp     loc_1800152C0
0x1800153de  mov     dword ptr [rdi+0DC4h], 0Ah
0x1800153e8  mov     dword ptr [rdi+0DD0h], 0Bh
0x1800153f2  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x1800153f7  jmp     short loc_180015412
0x1800153f9  mov     r8d, 0E35h
0x1800153ff  mov     ecx, 80004004h
0x180015404  mov     r9, rdi
0x180015407  mov     rdx, r13
0x18001540a  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180015410  mov     ebx, eax
0x180015412  test    ebx, ebx
0x180015414  jns     short loc_18001543F
0x180015416  test    r14b, r14b
0x180015419  jz      short loc_18001543F
0x18001541b  lea     rcx, [rdi+8]; this
0x18001541f  mov     edx, ebx; int
0x180015421  call    ?RollbackMigration@MigrationEngine@@IEAAJJ@Z; MigrationEngine::RollbackMigration(long)
0x180015426  test    eax, eax
0x180015428  jns     short loc_18001543F
0x18001542a  mov     r9, rdi
0x18001542d  mov     r8d, 0E65h
0x180015433  mov     rdx, r13
0x180015436  mov     ecx, eax
0x180015438  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001543e  nop
0x18001543f  lea     rcx, [rbp+var_20]; this
0x180015443  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015448  mov     eax, ebx
0x18001544a  lea     r11, [rsp+50h+var_s0]
0x18001544f  mov     rbx, [r11+38h]
0x180015453  mov     rsi, [r11+40h]
0x180015457  mov     rsp, r11
0x18001545a  pop     r15
0x18001545c  pop     r14
0x18001545e  pop     r13
0x180015460  pop     rdi
0x180015461  pop     rbp
0x180015462  retn
```
