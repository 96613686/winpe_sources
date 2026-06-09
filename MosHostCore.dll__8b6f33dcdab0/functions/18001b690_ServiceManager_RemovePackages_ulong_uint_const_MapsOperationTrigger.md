# ServiceManager::RemovePackages(ulong,uint const *,MapsOperationTrigger)

- ea: `0x18001b690`
- end: `0x18001b796`
- name: `?RemovePackages@ServiceManager@@UEAAJKPEBIW4MapsOperationTrigger@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e57c`
- `0x18000e6a0`
- `0x180010338`
- `0x18001af8c`
- `0x18001b690`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b74b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b77b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b74b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b77b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b6d9`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001b6d9`

## string_xrefs

- `0x18001b6cd`: `ServiceManager::RemovePackages`
- `0x18001b742`: `ServiceManager::RemovePackages`
- `0x18001b772`: `ServiceManager::RemovePackages`

## pseudocode

```c
__int64 __fastcall ServiceManager::RemovePackages(_DWORD *a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  int v11; // ebx
  int Operation; // eax
  _BYTE v14[16]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v15[72]; // [rsp+40h] [rbp-48h] BYREF

  CriticalSectionWithConditionVariable::Lock(a1 + 850, v14);
  if ( a1[882] != 5 )
  {
    v8 = ZTraceReportOrigination(-2147024875, "ServiceManager::RemovePackages", 891, a1);
LABEL_3:
    v9 = v8;
    RelockableGate::~RelockableGate((RelockableGate *)v14);
    return v9;
  }
  v10 = 261;
  if ( a4 != 1 )
    v10 = 1;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v15, a1 + 892);
  v11 = PackageManager::QueuePackagesToOperateOn(a1 + 892, a2, a3, v10, a4);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v15);
  if ( v11 < 0 )
  {
    v8 = ZTraceReportPropagation(v11, "ServiceManager::RemovePackages", 893, a1);
    goto LABEL_3;
  }
  RelockableGate::~RelockableGate((RelockableGate *)v14);
  Operation = ServiceManager::ProcessNextOperation((ServiceManager *)a1);
  if ( Operation >= 0 )
    return 0;
  else
    return (unsigned int)ZTraceReportPropagation(Operation, "ServiceManager::RemovePackages", 896, a1);
}

```

## disassembly

```asm
0x18001b690  push    rbx
0x18001b692  push    rbp
0x18001b693  push    rsi
0x18001b694  push    rdi
0x18001b695  push    r14
0x18001b697  push    r15
0x18001b699  sub     rsp, 58h
0x18001b69d  mov     ebp, r9d
0x18001b6a0  mov     r14, r8
0x18001b6a3  mov     r15d, edx
0x18001b6a6  mov     rsi, rcx
0x18001b6a9  add     rcx, 0D48h
0x18001b6b0  lea     rdx, [rsp+88h+var_58]
0x18001b6b5  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001b6ba  nop
0x18001b6bb  cmp     dword ptr [rsi+0DC8h], 5
0x18001b6c2  jz      short loc_18001B6F0
0x18001b6c4  mov     r9, rsi
0x18001b6c7  mov     r8d, 37Bh
0x18001b6cd  lea     rdx, aServicemanager_65; "ServiceManager::RemovePackages"
0x18001b6d4  mov     ecx, 80070015h
0x18001b6d9  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001b6df  mov     ebx, eax
0x18001b6e1  lea     rcx, [rsp+88h+var_58]; this
0x18001b6e6  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001b6eb  jmp     loc_18001B787
0x18001b6f0  lea     rdi, [rsi+0DF0h]
0x18001b6f7  mov     ebx, 105h
0x18001b6fc  mov     eax, 1
0x18001b701  cmp     ebp, eax
0x18001b703  cmovnz  ebx, eax
0x18001b706  mov     rdx, rdi
0x18001b709  lea     rcx, [rsp+88h+var_48]
0x18001b70e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001b713  nop
0x18001b714  mov     [rsp+88h+var_68], ebp
0x18001b718  mov     r9d, ebx
0x18001b71b  mov     r8, r14
0x18001b71e  mov     edx, r15d
0x18001b721  mov     rcx, rdi
0x18001b724  call    ?QueuePackagesToOperateOn@PackageManager@@AEAAJKPEBIHW4MapsOperationTrigger@@@Z; PackageManager::QueuePackagesToOperateOn(ulong,uint const *,int,MapsOperationTrigger)
0x18001b729  mov     ebx, eax
0x18001b72b  lea     rcx, [rsp+88h+var_48]
0x18001b730  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18001b735  test    ebx, ebx
0x18001b737  jns     short loc_18001B753
0x18001b739  mov     r9, rsi
0x18001b73c  mov     r8d, 37Dh
0x18001b742  lea     rdx, aServicemanager_65; "ServiceManager::RemovePackages"
0x18001b749  mov     ecx, ebx
0x18001b74b  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b751  jmp     short loc_18001B6DF
0x18001b753  lea     rcx, [rsp+88h+var_58]; this
0x18001b758  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001b75d  mov     rcx, rsi; this
0x18001b760  call    ?ProcessNextOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessNextOperation(void)
0x18001b765  test    eax, eax
0x18001b767  jns     short loc_18001B785
0x18001b769  mov     r9, rsi
0x18001b76c  mov     r8d, 380h
0x18001b772  lea     rdx, aServicemanager_65; "ServiceManager::RemovePackages"
0x18001b779  mov     ecx, eax
0x18001b77b  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b781  mov     ebx, eax
0x18001b783  jmp     short loc_18001B787
0x18001b785  xor     ebx, ebx
0x18001b787  mov     eax, ebx
0x18001b789  add     rsp, 58h
0x18001b78d  pop     r15
0x18001b78f  pop     r14
0x18001b791  pop     rdi
0x18001b792  pop     rsi
0x18001b793  pop     rbp
0x18001b794  pop     rbx
0x18001b795  retn
```
