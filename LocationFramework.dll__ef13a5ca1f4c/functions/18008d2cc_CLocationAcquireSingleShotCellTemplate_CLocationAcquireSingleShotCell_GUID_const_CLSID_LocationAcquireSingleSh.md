# CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::FinalConstruct(void)

- ea: `0x18008d2cc`
- end: `0x18008d35c`
- name: `?FinalConstruct@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008d184`
- `0x1800b4e24`

## callees

- `0x18008d2cc`
- `0x18009e2e4`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008d302`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008d323`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008d302`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008d323`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008d2e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008d2e3`

## pseudocode

```c
__int64 __fastcall CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::FinalConstruct(
        _QWORD *pv)
{
  HANDLE EventW; // rax
  PTP_WORK ThreadpoolWork; // rax
  int LastErrorAsHResult; // ebx
  PTP_WORK v5; // rax

  EventW = CreateEventW(0, 0, 0, 0);
  pv[22] = EventW;
  if ( !EventW
    || (ThreadpoolWork = CreateThreadpoolWork(
                           CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::ScanScheduler,
                           pv,
                           0),
        (pv[20] = ThreadpoolWork) == 0)
    || (LastErrorAsHResult = 0,
        v5 = CreateThreadpoolWork(
               CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::PositionListHandler,
               pv,
               0),
        (pv[24] = v5) == 0) )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    if ( LastErrorAsHResult < 0 )
      (*(void (__fastcall **)(_QWORD *))(*pv + 48LL))(pv);
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x18008d2cc  mov     [rsp+arg_0], rbx
0x18008d2d1  push    rdi
0x18008d2d2  sub     rsp, 20h
0x18008d2d6  mov     rdi, rcx
0x18008d2d9  xor     r9d, r9d; lpName
0x18008d2dc  xor     ecx, ecx; lpEventAttributes
0x18008d2de  xor     r8d, r8d; bInitialState
0x18008d2e1  xor     edx, edx; bManualReset
0x18008d2e3  call    cs:__imp_CreateEventW
0x18008d2e9  mov     [rdi+0B0h], rax
0x18008d2f0  test    rax, rax
0x18008d2f3  jz      short loc_18008D335
0x18008d2f5  xor     r8d, r8d; pcbe
0x18008d2f8  lea     rcx, ?ScanScheduler@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18008d2ff  mov     rdx, rdi; pv
0x18008d302  call    cs:__imp_CreateThreadpoolWork
0x18008d308  mov     [rdi+0A0h], rax
0x18008d30f  test    rax, rax
0x18008d312  jz      short loc_18008D335
0x18008d314  xor     r8d, r8d; pcbe
0x18008d317  lea     rcx, ?PositionListHandler@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18008d31e  mov     rdx, rdi; pv
0x18008d321  xor     ebx, ebx
0x18008d323  call    cs:__imp_CreateThreadpoolWork
0x18008d329  mov     [rdi+0C0h], rax
0x18008d330  test    rax, rax
0x18008d333  jnz     short loc_18008D34F
0x18008d335  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18008d33a  mov     ebx, eax
0x18008d33c  test    eax, eax
0x18008d33e  jns     short loc_18008D34F
0x18008d340  mov     rax, [rdi]
0x18008d343  mov     rcx, rdi
0x18008d346  mov     rax, [rax+30h]
0x18008d34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d34f  mov     eax, ebx
0x18008d351  mov     rbx, [rsp+28h+arg_0]
0x18008d356  add     rsp, 20h
0x18008d35a  pop     rdi
0x18008d35b  retn
```
