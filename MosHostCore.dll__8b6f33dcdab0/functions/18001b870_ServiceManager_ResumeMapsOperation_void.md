# ServiceManager::ResumeMapsOperation(void)

- ea: `0x18001b870`
- end: `0x18001b970`
- name: `?ResumeMapsOperation@ServiceManager@@UEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180012cf0`
- `0x18001af8c`
- `0x18001b870`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b89e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b89e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8b0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b94a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b94a`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b8d9`
- `ZTrace_Maps!ZTraceHelper` at `0x18001b8d9`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b910`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b910`

## string_xrefs

- `0x18001b8cf`: `ServiceManager::ResumeMapsOperation`
- `0x18001b907`: `ServiceManager::ResumeMapsOperation`
- `0x18001b941`: `ServiceManager::ResumeMapsOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::ResumeMapsOperation(ServiceManager *this)
{
  int v2; // ebx
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int Operation; // eax
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock((struct _RTL_CRITICAL_SECTION *)this + 85, (__int64)v8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3816));
  v2 = *((_DWORD *)this + 980) + *((_DWORD *)this + 981) + *((_DWORD *)this + 982);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 3816));
  if ( v2 )
  {
    if ( !*((_DWORD *)this + 881) && *((_DWORD *)this + 882) == 5 )
    {
      Operation = ServiceManager::ProcessNextOperation(this);
      if ( Operation < 0 )
      {
        v4 = ZTraceReportPropagation(Operation, "ServiceManager::ResumeMapsOperation", 2346, this);
        goto LABEL_4;
      }
    }
LABEL_9:
    v5 = 0;
    goto LABEL_10;
  }
  ZTraceHelper(3, "ServiceManager::ResumeMapsOperation", 2332, this, "Resuming maps operation(s)");
  v3 = ServiceManager::AttachClient((__int64)this, 2u, 1, 0, 0);
  if ( v3 >= 0 )
    goto LABEL_9;
  v4 = ZTraceReportOrigination(v3, "ServiceManager::ResumeMapsOperation", 2340, this);
LABEL_4:
  v5 = v4;
LABEL_10:
  RelockableGate::~RelockableGate((RelockableGate *)v8);
  return v5;
}

```

## disassembly

```asm
0x18001b870  mov     [rsp+arg_0], rbx
0x18001b875  mov     [rsp+arg_8], rsi
0x18001b87a  push    rdi
0x18001b87b  sub     rsp, 40h
0x18001b87f  mov     rsi, rcx
0x18001b882  add     rcx, 0D48h
0x18001b889  lea     rdx, [rsp+48h+var_18]
0x18001b88e  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001b893  nop
0x18001b894  lea     rdi, [rsi+0EE8h]
0x18001b89b  mov     rcx, rdi; lpCriticalSection
0x18001b89e  call    cs:__imp_EnterCriticalSection
0x18001b8a4  mov     ebx, [rdi+70h]
0x18001b8a7  add     ebx, [rdi+6Ch]
0x18001b8aa  add     ebx, [rdi+68h]
0x18001b8ad  mov     rcx, rdi; lpCriticalSection
0x18001b8b0  call    cs:__imp_LeaveCriticalSection
0x18001b8b6  test    ebx, ebx
0x18001b8b8  jnz     short loc_18001B91A
0x18001b8ba  lea     rax, aResumingMapsOp; "Resuming maps operation(s)"
0x18001b8c1  mov     [rsp+48h+var_28], rax
0x18001b8c6  mov     r9, rsi
0x18001b8c9  mov     r8d, 91Ch
0x18001b8cf  lea     rdx, aServicemanager_44; "ServiceManager::ResumeMapsOperation"
0x18001b8d6  lea     ecx, [rbx+3]
0x18001b8d9  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001b8df  mov     [rsp+48h+var_28], 0
0x18001b8e8  xor     r9d, r9d
0x18001b8eb  lea     edx, [rbx+2]
0x18001b8ee  lea     r8d, [rbx+1]
0x18001b8f2  mov     rcx, rsi
0x18001b8f5  call    ?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z; ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)
0x18001b8fa  test    eax, eax
0x18001b8fc  jns     short loc_18001B952
0x18001b8fe  mov     r9, rsi
0x18001b901  mov     r8d, 924h
0x18001b907  lea     rdx, aServicemanager_44; "ServiceManager::ResumeMapsOperation"
0x18001b90e  mov     ecx, eax
0x18001b910  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001b916  mov     ebx, eax
0x18001b918  jmp     short loc_18001B954
0x18001b91a  cmp     dword ptr [rsi+0DC4h], 0
0x18001b921  jnz     short loc_18001B952
0x18001b923  cmp     dword ptr [rsi+0DC8h], 5
0x18001b92a  jnz     short loc_18001B952
0x18001b92c  mov     rcx, rsi; this
0x18001b92f  call    ?ProcessNextOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessNextOperation(void)
0x18001b934  test    eax, eax
0x18001b936  jns     short loc_18001B952
0x18001b938  mov     r9, rsi
0x18001b93b  mov     r8d, 92Ah
0x18001b941  lea     rdx, aServicemanager_44; "ServiceManager::ResumeMapsOperation"
0x18001b948  mov     ecx, eax
0x18001b94a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b950  jmp     short loc_18001B916
0x18001b952  xor     ebx, ebx
0x18001b954  lea     rcx, [rsp+48h+var_18]; this
0x18001b959  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001b95e  mov     eax, ebx
0x18001b960  mov     rbx, [rsp+48h+arg_0]
0x18001b965  mov     rsi, [rsp+48h+arg_8]
0x18001b96a  add     rsp, 40h
0x18001b96e  pop     rdi
0x18001b96f  retn
```
