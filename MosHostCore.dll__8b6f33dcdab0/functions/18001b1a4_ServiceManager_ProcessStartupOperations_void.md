# ServiceManager::ProcessStartupOperations(void)

- ea: `0x18001b1a4`
- end: `0x18001b313`
- name: `?ProcessStartupOperations@ServiceManager@@AEAAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001405c`

## callees

- `0x18000bd00`
- `0x18000fd58`
- `0x180014b3c`
- `0x18001af8c`
- `0x18001b1a4`
- `0x18001b848`
- `0x18001ba6c`
- `0x18001cf60`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b1e2`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b1e2`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b245`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b2c1`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b245`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b2c1`

## string_xrefs

- `0x18001b1d9`: `ServiceManager::ProcessStartupOperations`
- `0x18001b23a`: `ServiceManager::ProcessStartupOperations`
- `0x18001b2b8`: `ServiceManager::ProcessStartupOperations`
- `0x18001b2a3`: `MapsBroker thinks there is a download or delete operation to perform but PackageManager has no maps restored.`

## pseudocode

```c
int __fastcall ServiceManager::ProcessStartupOperations(ServiceManager *this)
{
  int HasOperationOrRestoredData; // eax
  int v3; // r8d
  int v5; // esi
  bool v6; // [rsp+48h] [rbp+10h] BYREF
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  HasOperationOrRestoredData = ServiceManager::DeserializeOperationState(
                                 this,
                                 (enum IServiceManager::OPERATION_TYPE *)&v7);
  if ( HasOperationOrRestoredData < 0 )
  {
    v3 = 1180;
    return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
  }
  HasOperationOrRestoredData = PackageManager::HasOperationOrRestoredData((ServiceManager *)((char *)this + 3568), &v6);
  if ( HasOperationOrRestoredData < 0 )
  {
    v3 = 1182;
    return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
  }
  v5 = v7;
  if ( v6 )
    v5 = 1;
  if ( v5 )
    ZTraceHelper(
      3,
      "ServiceManager::ProcessStartupOperations",
      1193,
      this,
      "Processing startup operations result: OperationPending = %d",
      v5);
  if ( v5 == 3 )
  {
    HasOperationOrRestoredData = ServiceManager::StartInstallUpdate(this);
    if ( HasOperationOrRestoredData < 0 )
    {
      v3 = 1199;
      return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
    }
  }
  else if ( (unsigned int)(v5 - 1) <= 1 )
  {
    if ( v6 )
    {
      HasOperationOrRestoredData = ServiceManager::ProcessNextOperation(this);
      if ( HasOperationOrRestoredData < 0 )
      {
        v3 = 1215;
        return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
      }
    }
    else
    {
      ZTraceHelper(
        0,
        "ServiceManager::ProcessStartupOperations",
        1208,
        this,
        "MapsBroker thinks there is a download or delete operation to perform but PackageManager has no maps restored.");
      if ( *((_DWORD *)this + 880) )
        __int2c();
      HasOperationOrRestoredData = ServiceManager::SerializeOperationState(this);
      if ( HasOperationOrRestoredData < 0 )
      {
        v3 = 1211;
        return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
      }
    }
  }
  else if ( v5 == 6 || MigrationEngine::IsMigrationPending((ServiceManager *)((char *)this + 8)) )
  {
    HasOperationOrRestoredData = ServiceManager::ResumeMapDataMigration(this);
    if ( HasOperationOrRestoredData < 0 )
    {
      v3 = 1220;
      return ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::ProcessStartupOperations", v3, this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b1a4  mov     rax, rsp
0x18001b1a7  mov     [rax+8], rbx
0x18001b1ab  mov     [rax+20h], rsi
0x18001b1af  push    r15
0x18001b1b1  sub     rsp, 30h
0x18001b1b5  lea     rdx, [rax+18h]; enum IServiceManager::OPERATION_TYPE *
0x18001b1b9  mov     dword ptr [rax+18h], 0
0x18001b1c0  mov     rbx, rcx
0x18001b1c3  mov     byte ptr [rax+10h], 0
0x18001b1c7  call    ?DeserializeOperationState@ServiceManager@@AEAAJPEAW4OPERATION_TYPE@IServiceManager@@@Z; ServiceManager::DeserializeOperationState(IServiceManager::OPERATION_TYPE *)
0x18001b1cc  test    eax, eax
0x18001b1ce  jns     short loc_18001B1ED
0x18001b1d0  mov     r8d, 49Ch
0x18001b1d6  mov     r9, rbx
0x18001b1d9  lea     rdx, aServicemanager_38; "ServiceManager::ProcessStartupOperation"...
0x18001b1e0  mov     ecx, eax
0x18001b1e2  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b1e8  jmp     loc_18001B302
0x18001b1ed  lea     rcx, [rbx+0DF0h]; this
0x18001b1f4  lea     rdx, [rsp+38h+arg_8]; bool *
0x18001b1f9  call    ?HasOperationOrRestoredData@PackageManager@@QEAAJPEA_N@Z; PackageManager::HasOperationOrRestoredData(bool *)
0x18001b1fe  test    eax, eax
0x18001b200  jns     short loc_18001B20A
0x18001b202  mov     r8d, 49Eh
0x18001b208  jmp     short loc_18001B1D6
0x18001b20a  cmp     [rsp+38h+arg_8], 0
0x18001b20f  mov     r15d, 1
0x18001b215  mov     esi, [rsp+38h+arg_10]
0x18001b219  cmovnz  esi, r15d
0x18001b21d  test    esi, esi
0x18001b21f  jz      short loc_18001B24B
0x18001b221  lea     rax, aProcessingStar; "Processing startup operations result: O"...
0x18001b228  mov     [rsp+38h+var_10], esi
0x18001b22c  mov     r9, rbx
0x18001b22f  mov     [rsp+38h+var_18], rax
0x18001b234  mov     r8d, 4A9h
0x18001b23a  lea     rdx, aServicemanager_38; "ServiceManager::ProcessStartupOperation"...
0x18001b241  lea     ecx, [r15+2]
0x18001b245  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001b24b  cmp     esi, 3
0x18001b24e  jnz     short loc_18001B26B
0x18001b250  mov     rcx, rbx; this
0x18001b253  call    ?StartInstallUpdate@ServiceManager@@UEAAJXZ; ServiceManager::StartInstallUpdate(void)
0x18001b258  test    eax, eax
0x18001b25a  jns     loc_18001B300
0x18001b260  mov     r8d, 4AFh
0x18001b266  jmp     loc_18001B1D6
0x18001b26b  lea     eax, [rsi-1]
0x18001b26e  cmp     eax, r15d
0x18001b271  jbe     short loc_18001B29C
0x18001b273  cmp     esi, 6
0x18001b276  jz      short loc_18001B285
0x18001b278  lea     rcx, [rbx+8]; this
0x18001b27c  call    ?IsMigrationPending@MigrationEngine@@IEAA_NXZ; MigrationEngine::IsMigrationPending(void)
0x18001b281  test    al, al
0x18001b283  jz      short loc_18001B300
0x18001b285  mov     rcx, rbx; this
0x18001b288  call    ?ResumeMapDataMigration@ServiceManager@@QEAAJXZ; ServiceManager::ResumeMapDataMigration(void)
0x18001b28d  test    eax, eax
0x18001b28f  jns     short loc_18001B300
0x18001b291  mov     r8d, 4C4h
0x18001b297  jmp     loc_18001B1D6
0x18001b29c  cmp     [rsp+38h+arg_8], 0
0x18001b2a1  jnz     short loc_18001B2E9
0x18001b2a3  lea     rax, aMapsbrokerThin; "MapsBroker thinks there is a download o"...
0x18001b2aa  mov     r9, rbx
0x18001b2ad  mov     r8d, 4B8h
0x18001b2b3  mov     [rsp+38h+var_18], rax
0x18001b2b8  lea     rdx, aServicemanager_38; "ServiceManager::ProcessStartupOperation"...
0x18001b2bf  xor     ecx, ecx
0x18001b2c1  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001b2c7  cmp     dword ptr [rbx+0DC0h], 0
0x18001b2ce  jz      short loc_18001B2D2
0x18001b2d0  int     2Ch; Windows NT - assertion failure
0x18001b2d2  mov     rcx, rbx; this
0x18001b2d5  call    ?SerializeOperationState@ServiceManager@@AEAAJXZ; ServiceManager::SerializeOperationState(void)
0x18001b2da  test    eax, eax
0x18001b2dc  jns     short loc_18001B300
0x18001b2de  mov     r8d, 4BBh
0x18001b2e4  jmp     loc_18001B1D6
0x18001b2e9  mov     rcx, rbx; this
0x18001b2ec  call    ?ProcessNextOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessNextOperation(void)
0x18001b2f1  test    eax, eax
0x18001b2f3  jns     short loc_18001B300
0x18001b2f5  mov     r8d, 4BFh
0x18001b2fb  jmp     loc_18001B1D6
0x18001b300  xor     eax, eax
0x18001b302  mov     rbx, [rsp+38h+arg_0]
0x18001b307  mov     rsi, [rsp+38h+arg_18]
0x18001b30c  add     rsp, 30h
0x18001b310  pop     r15
0x18001b312  retn
```
