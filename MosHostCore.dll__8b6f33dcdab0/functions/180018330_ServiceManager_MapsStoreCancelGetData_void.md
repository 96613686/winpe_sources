# ServiceManager::MapsStoreCancelGetData(void *)

- ea: `0x180018330`
- end: `0x1800183a6`
- name: `?MapsStoreCancelGetData@ServiceManager@@UEAAJPEAX@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180018330`
- `0x18001e454`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MapsStore!MapsStore_CancelGetData` at `0x180018393`
- `MapsStore!MapsStore_CancelGetData` at `0x180018393`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018370`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018370`

## string_xrefs

- `0x180018367`: `ServiceManager::MapsStoreCancelGetData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::MapsStoreCancelGetData(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock(this + 85, (__int64)v7);
  v4 = ServiceManager::WaitForMOSAndBingInit((ServiceManager *)this);
  if ( v4 >= 0 )
  {
    v5 = 0;
    RelockableGate::~RelockableGate((RelockableGate *)v7);
    MapsStore_CancelGetData(a2);
  }
  else
  {
    v5 = ZTraceReportPropagation(v4, "ServiceManager::MapsStoreCancelGetData", 2843, this);
    RelockableGate::~RelockableGate((RelockableGate *)v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180018330  mov     [rsp+arg_0], rbx
0x180018335  push    rdi
0x180018336  sub     rsp, 30h
0x18001833a  mov     rdi, rdx
0x18001833d  mov     rbx, rcx
0x180018340  add     rcx, 0D48h
0x180018347  lea     rdx, [rsp+38h+var_18]
0x18001834c  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180018351  nop
0x180018352  mov     rcx, rbx; this
0x180018355  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x18001835a  test    eax, eax
0x18001835c  jns     short loc_180018384
0x18001835e  mov     r9, rbx
0x180018361  mov     r8d, 0B1Bh
0x180018367  lea     rdx, aServicemanager_62; "ServiceManager::MapsStoreCancelGetData"
0x18001836e  mov     ecx, eax
0x180018370  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180018376  mov     ebx, eax
0x180018378  lea     rcx, [rsp+38h+var_18]; this
0x18001837d  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180018382  jmp     short loc_180018399
0x180018384  xor     ebx, ebx
0x180018386  lea     rcx, [rsp+38h+var_18]; this
0x18001838b  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180018390  mov     rcx, rdi
0x180018393  call    cs:__imp_?MapsStore_CancelGetData@@YAXPEAX@Z; MapsStore_CancelGetData(void *)
0x180018399  mov     eax, ebx
0x18001839b  mov     rbx, [rsp+38h+arg_0]
0x1800183a0  add     rsp, 30h
0x1800183a4  pop     rdi
0x1800183a5  retn
```
