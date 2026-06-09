# ServiceManager::GetMapsStoreData(int,int,int,bool,void *,std::function<void (MosHostGetDataAsyncResult const &)> &&)

- ea: `0x180016490`
- end: `0x18001655b`
- name: `?GetMapsStoreData@ServiceManager@@UEAAJHHH_NPEAX$$QEAV?$function@$$A6AXAEBUMosHostGetDataAsyncResult@@@Z@std@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(ServiceManager *this, unsigned int, unsigned int, unsigned int, char, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001400c`
- `0x180016490`
- `0x18001e454`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MapsStore!MapsStore_GetData` at `0x18001651b`
- `MapsStore!MapsStore_GetData` at `0x18001651b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800164d4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001654a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800164d4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001654a`

## string_xrefs

- `0x1800164cb`: `ServiceManager::GetMapsStoreData`
- `0x180016541`: `ServiceManager::GetMapsStoreData`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetMapsStoreData(
        ServiceManager *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        char a5,
        __int64 a6,
        __int64 a7)
{
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  int Data; // eax
  _BYTE v16[56]; // [rsp+30h] [rbp-38h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v16);
  v11 = ServiceManager::WaitForMOSAndBingInit(this);
  if ( v11 >= 0 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v16);
    LOBYTE(v13) = a5;
    Data = MapsStore_GetData(a2, a3, a4, v13, a6, a7);
    v12 = Data;
    if ( Data < 0 )
    {
      if ( Data != -2147023673 )
        ZTraceReportPropagation(Data, "ServiceManager::GetMapsStoreData", 2827, this);
    }
    else
    {
      ServiceManager::CollectUserProxyTelemetryAsync(this);
    }
  }
  else
  {
    v12 = ZTraceReportPropagation(v11, "ServiceManager::GetMapsStoreData", 2823, this);
    RelockableGate::~RelockableGate((RelockableGate *)v16);
  }
  return v12;
}

```

## disassembly

```asm
0x180016490  push    rbx
0x180016492  push    rbp
0x180016493  push    rsi
0x180016494  push    rdi
0x180016495  sub     rsp, 48h
0x180016499  mov     ebx, r9d
0x18001649c  mov     esi, r8d
0x18001649f  mov     ebp, edx
0x1800164a1  mov     rdi, rcx
0x1800164a4  add     rcx, 0D48h
0x1800164ab  lea     rdx, [rsp+68h+var_38]
0x1800164b0  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800164b5  nop
0x1800164b6  mov     rcx, rdi; this
0x1800164b9  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x1800164be  test    eax, eax
0x1800164c0  jns     short loc_1800164E8
0x1800164c2  mov     r9, rdi
0x1800164c5  mov     r8d, 0B07h
0x1800164cb  lea     rdx, aServicemanager_27; "ServiceManager::GetMapsStoreData"
0x1800164d2  mov     ecx, eax
0x1800164d4  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800164da  mov     ebx, eax
0x1800164dc  lea     rcx, [rsp+68h+var_38]; this
0x1800164e1  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800164e6  jmp     short loc_180016550
0x1800164e8  lea     rcx, [rsp+68h+var_38]; this
0x1800164ed  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800164f2  mov     rax, [rsp+68h+arg_30]
0x1800164fa  mov     [rsp+68h+var_40], rax
0x1800164ff  mov     rax, [rsp+68h+arg_28]
0x180016507  mov     [rsp+68h+var_48], rax
0x18001650c  mov     r9b, [rsp+68h+arg_20]
0x180016514  mov     r8d, ebx
0x180016517  mov     edx, esi
0x180016519  mov     ecx, ebp
0x18001651b  call    cs:__imp_?MapsStore_GetData@@YAJHHH_NPEAX$$QEAV?$function@$$A6AXAEBUMosHostGetDataAsyncResult@@@Z@std@@@Z; MapsStore_GetData(int,int,int,bool,void *,std::function<void (MosHostGetDataAsyncResult const &)> &&)
0x180016521  mov     ebx, eax
0x180016523  test    eax, eax
0x180016525  js      short loc_180016531
0x180016527  mov     rcx, rdi; this
0x18001652a  call    ?CollectUserProxyTelemetryAsync@ServiceManager@@AEAAXXZ; ServiceManager::CollectUserProxyTelemetryAsync(void)
0x18001652f  jmp     short loc_180016550
0x180016531  cmp     eax, 800704C7h
0x180016536  jz      short loc_180016550
0x180016538  mov     r9, rdi
0x18001653b  mov     r8d, 0B0Bh
0x180016541  lea     rdx, aServicemanager_27; "ServiceManager::GetMapsStoreData"
0x180016548  mov     ecx, eax
0x18001654a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016550  mov     eax, ebx
0x180016552  add     rsp, 48h
0x180016556  pop     rdi
0x180016557  pop     rsi
0x180016558  pop     rbp
0x180016559  pop     rbx
0x18001655a  retn
```
