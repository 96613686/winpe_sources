# ServiceManager::DeleteMapsStoreData(int,int)

- ea: `0x180014a90`
- end: `0x180014b33`
- name: `?DeleteMapsStoreData@ServiceManager@@UEAAJHH@Z`
- size: `163`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180014a90`
- `0x18001e454`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MapsStore!MapsStore_DeleteData` at `0x180014af9`
- `MapsStore!MapsStore_DeleteData` at `0x180014af9`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014ad7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014ad7`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014b15`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014b15`

## string_xrefs

- `0x180014ace`: `ServiceManager::DeleteMapsStoreData`
- `0x180014b0c`: `ServiceManager::DeleteMapsStoreData`

## pseudocode

```c
__int64 __fastcall ServiceManager::DeleteMapsStoreData(ServiceManager *this, int a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v10);
  v6 = ServiceManager::WaitForMOSAndBingInit(this);
  if ( v6 >= 0 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v10);
    v8 = MapsStore_DeleteData(a2, a3);
    if ( v8 >= 0 )
      return 0;
    else
      return (unsigned int)ZTraceReportOrigination(v8, "ServiceManager::DeleteMapsStoreData", 2863, this);
  }
  else
  {
    v7 = ZTraceReportPropagation(v6, "ServiceManager::DeleteMapsStoreData", 2860, this);
    RelockableGate::~RelockableGate((RelockableGate *)v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180014a90  mov     [rsp+arg_0], rbx
0x180014a95  mov     [rsp+arg_8], rsi
0x180014a9a  push    rdi
0x180014a9b  sub     rsp, 30h
0x180014a9f  mov     edi, r8d
0x180014aa2  mov     esi, edx
0x180014aa4  mov     rbx, rcx
0x180014aa7  add     rcx, 0D48h
0x180014aae  lea     rdx, [rsp+38h+var_18]
0x180014ab3  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180014ab8  nop
0x180014ab9  mov     rcx, rbx; this
0x180014abc  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x180014ac1  test    eax, eax
0x180014ac3  jns     short loc_180014AEB
0x180014ac5  mov     r9, rbx
0x180014ac8  mov     r8d, 0B2Ch
0x180014ace  lea     rdx, aServicemanager_75; "ServiceManager::DeleteMapsStoreData"
0x180014ad5  mov     ecx, eax
0x180014ad7  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180014add  mov     ebx, eax
0x180014adf  lea     rcx, [rsp+38h+var_18]; this
0x180014ae4  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180014ae9  jmp     short loc_180014B21
0x180014aeb  lea     rcx, [rsp+38h+var_18]; this
0x180014af0  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180014af5  mov     edx, edi
0x180014af7  mov     ecx, esi
0x180014af9  call    cs:__imp_?MapsStore_DeleteData@@YAJHH@Z; MapsStore_DeleteData(int,int)
0x180014aff  test    eax, eax
0x180014b01  jns     short loc_180014B1F
0x180014b03  mov     r9, rbx
0x180014b06  mov     r8d, 0B2Fh
0x180014b0c  lea     rdx, aServicemanager_75; "ServiceManager::DeleteMapsStoreData"
0x180014b13  mov     ecx, eax
0x180014b15  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180014b1b  mov     ebx, eax
0x180014b1d  jmp     short loc_180014B21
0x180014b1f  xor     ebx, ebx
0x180014b21  mov     eax, ebx
0x180014b23  mov     rbx, [rsp+38h+arg_0]
0x180014b28  mov     rsi, [rsp+38h+arg_8]
0x180014b2d  add     rsp, 30h
0x180014b31  pop     rdi
0x180014b32  retn
```
