# ServiceManager::ProcessNextOperation(void)

- ea: `0x18001af8c`
- end: `0x18001b062`
- name: `?ProcessNextOperation@ServiceManager@@AEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x180012a40`
- `0x1800142c4`
- `0x180014c00`
- `0x18001b1a4`
- `0x18001b690`
- `0x18001b870`

## callees

- `0x18000bd00`
- `0x18000f84c`
- `0x18001af8c`
- `0x18001b068`
- `0x18001b848`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001aff3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001aff3`

## string_xrefs

- `0x18001afea`: `ServiceManager::ProcessNextOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::ProcessNextOperation(struct _RTL_CRITICAL_SECTION *this)
{
  int NextOperationData; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock(this + 85, (__int64)v6);
  if ( HIDWORD(this[88].DebugInfo) )
    goto LABEL_12;
  NextOperationData = PackageManager::GetNextOperationData(
                        &this[89].LockCount,
                        &this[86].SpinCount,
                        &this[87].OwningThread);
  if ( NextOperationData >= 0 )
  {
    if ( (PRTL_CRITICAL_SECTION_DEBUG)this[86].SpinCount == this[87].DebugInfo
      && this[87].OwningThread == this[87].LockSemaphore )
    {
      if ( MigrationEngine::IsMigrationPending((MigrationEngine *)&this->LockCount) )
      {
        NextOperationData = ServiceManager::ResumeMapDataMigration((ServiceManager *)this);
        if ( NextOperationData < 0 )
        {
          v3 = 1135;
          goto LABEL_4;
        }
      }
    }
    else
    {
      NextOperationData = ServiceManager::ProcessPackageOrUpdateOperation((ServiceManager *)this);
      if ( NextOperationData < 0 )
      {
        v3 = 1131;
        goto LABEL_4;
      }
    }
LABEL_12:
    v4 = 0;
    goto LABEL_13;
  }
  v3 = 1127;
LABEL_4:
  v4 = ZTraceReportPropagation(NextOperationData, "ServiceManager::ProcessNextOperation", v3, this);
LABEL_13:
  RelockableGate::~RelockableGate((RelockableGate *)v6);
  return v4;
}

```

## disassembly

```asm
0x18001af8c  mov     [rsp+arg_0], rbx
0x18001af91  mov     [rsp+arg_8], rsi
0x18001af96  push    rdi
0x18001af97  sub     rsp, 30h
0x18001af9b  mov     rbx, rcx
0x18001af9e  add     rcx, 0D48h
0x18001afa5  lea     rdx, [rsp+38h+var_18]
0x18001afaa  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001afaf  nop
0x18001afb0  cmp     dword ptr [rbx+0DC4h], 0
0x18001afb7  jnz     loc_18001B044
0x18001afbd  lea     rdi, [rbx+0DA8h]
0x18001afc4  lea     rsi, [rbx+0D90h]
0x18001afcb  lea     rcx, [rbx+0DF0h]
0x18001afd2  mov     r8, rdi
0x18001afd5  mov     rdx, rsi
0x18001afd8  call    ?GetNextOperationData@PackageManager@@QEAAJPEAV?$vector@IV?$allocator@I@std@@@std@@0@Z; PackageManager::GetNextOperationData(std::vector<uint> *,std::vector<uint> *)
0x18001afdd  test    eax, eax
0x18001afdf  jns     short loc_18001AFFD
0x18001afe1  mov     r8d, 467h
0x18001afe7  mov     r9, rbx
0x18001afea  lea     rdx, aServicemanager_69; "ServiceManager::ProcessNextOperation"
0x18001aff1  mov     ecx, eax
0x18001aff3  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001aff9  mov     ebx, eax
0x18001affb  jmp     short loc_18001B046
0x18001affd  mov     rax, [rsi+8]
0x18001b001  cmp     [rsi], rax
0x18001b004  jnz     short loc_18001B030
0x18001b006  mov     rax, [rdi+8]
0x18001b00a  cmp     [rdi], rax
0x18001b00d  jnz     short loc_18001B030
0x18001b00f  lea     rcx, [rbx+8]; this
0x18001b013  call    ?IsMigrationPending@MigrationEngine@@IEAA_NXZ; MigrationEngine::IsMigrationPending(void)
0x18001b018  test    al, al
0x18001b01a  jz      short loc_18001B044
0x18001b01c  mov     rcx, rbx; this
0x18001b01f  call    ?ResumeMapDataMigration@ServiceManager@@QEAAJXZ; ServiceManager::ResumeMapDataMigration(void)
0x18001b024  test    eax, eax
0x18001b026  jns     short loc_18001B044
0x18001b028  mov     r8d, 46Fh
0x18001b02e  jmp     short loc_18001AFE7
0x18001b030  mov     rcx, rbx; this
0x18001b033  call    ?ProcessPackageOrUpdateOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessPackageOrUpdateOperation(void)
0x18001b038  test    eax, eax
0x18001b03a  jns     short loc_18001B044
0x18001b03c  mov     r8d, 46Bh
0x18001b042  jmp     short loc_18001AFE7
0x18001b044  xor     ebx, ebx
0x18001b046  lea     rcx, [rsp+38h+var_18]; this
0x18001b04b  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001b050  mov     eax, ebx
0x18001b052  mov     rbx, [rsp+38h+arg_0]
0x18001b057  mov     rsi, [rsp+38h+arg_8]
0x18001b05c  add     rsp, 30h
0x18001b060  pop     rdi
0x18001b061  retn
```
