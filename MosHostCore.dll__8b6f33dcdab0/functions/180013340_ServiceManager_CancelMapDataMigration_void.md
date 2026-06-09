# ServiceManager::CancelMapDataMigration(void)

- ea: `0x180013340`
- end: `0x1800133fa`
- name: `?CancelMapDataMigration@ServiceManager@@UEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180009c04`
- `0x180013340`
- `0x180013400`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800133bf`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800133bf`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800133e0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800133e0`

## string_xrefs

- `0x1800133b6`: `ServiceManager::CancelMapDataMigration`
- `0x1800133d9`: `ServiceManager::CancelMapDataMigration`

## pseudocode

```c
__int64 __fastcall ServiceManager::CancelMapDataMigration(ServiceManager *this)
{
  int v2; // r8d
  int v3; // ecx
  int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v8);
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, 1) )
    __int2c();
  if ( *((_DWORD *)this + 882) != 5 )
  {
    v2 = 3616;
    v3 = -2147024875;
LABEL_11:
    v5 = ZTraceReportOrigination(v3, "ServiceManager::CancelMapDataMigration", v2, this);
    goto LABEL_12;
  }
  if ( *((_DWORD *)this + 880) != 6 || (unsigned int)(*((_DWORD *)this + 881) - 9) > 1 )
  {
    v2 = 3618;
    v3 = -2147019873;
    goto LABEL_11;
  }
  v4 = ServiceManager::CancelOperation(this, 0);
  if ( v4 < 0 )
  {
    v5 = ZTraceReportPropagation(v4, "ServiceManager::CancelMapDataMigration", 3620, this);
LABEL_12:
    v6 = v5;
    goto LABEL_13;
  }
  v6 = 0;
LABEL_13:
  RelockableGate::~RelockableGate((RelockableGate *)v8);
  return v6;
}

```

## disassembly

```asm
0x180013340  push    rbx
0x180013342  sub     rsp, 30h
0x180013346  mov     rbx, rcx
0x180013349  add     rcx, 0D48h
0x180013350  lea     rdx, [rsp+38h+var_18]
0x180013355  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001335a  nop
0x18001335b  lea     rcx, [rbx+0EE8h]
0x180013362  mov     edx, 1
0x180013367  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001336c  test    al, al
0x18001336e  jnz     short loc_180013372
0x180013370  int     2Ch; Windows NT - assertion failure
0x180013372  cmp     dword ptr [rbx+0DC8h], 5
0x180013379  jz      short loc_180013388
0x18001337b  mov     r8d, 0E20h
0x180013381  mov     ecx, 80070015h
0x180013386  jmp     short loc_1800133D6
0x180013388  cmp     dword ptr [rbx+0DC0h], 6
0x18001338f  jnz     short loc_1800133CB
0x180013391  mov     eax, [rbx+0DC4h]
0x180013397  sub     eax, 9
0x18001339a  cmp     eax, 1
0x18001339d  ja      short loc_1800133CB
0x18001339f  xor     edx, edx
0x1800133a1  mov     rcx, rbx
0x1800133a4  call    ?CancelOperation@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperation(ServiceManager::CANCELLATION_TYPE)
0x1800133a9  test    eax, eax
0x1800133ab  jns     short loc_1800133C7
0x1800133ad  mov     r9, rbx
0x1800133b0  mov     r8d, 0E24h
0x1800133b6  lea     rdx, aServicemanager_66; "ServiceManager::CancelMapDataMigration"
0x1800133bd  mov     ecx, eax
0x1800133bf  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800133c5  jmp     short loc_1800133E6
0x1800133c7  xor     ebx, ebx
0x1800133c9  jmp     short loc_1800133E8
0x1800133cb  mov     r8d, 0E22h
0x1800133d1  mov     ecx, 8007139Fh
0x1800133d6  mov     r9, rbx
0x1800133d9  lea     rdx, aServicemanager_66; "ServiceManager::CancelMapDataMigration"
0x1800133e0  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800133e6  mov     ebx, eax
0x1800133e8  lea     rcx, [rsp+38h+var_18]; this
0x1800133ed  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800133f2  mov     eax, ebx
0x1800133f4  add     rsp, 30h
0x1800133f8  pop     rbx
0x1800133f9  retn
```
