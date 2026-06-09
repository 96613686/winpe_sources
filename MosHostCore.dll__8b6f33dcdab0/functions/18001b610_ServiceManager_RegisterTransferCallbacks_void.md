# ServiceManager::RegisterTransferCallbacks(void)

- ea: `0x18001b610`
- end: `0x18001b689`
- name: `?RegisterTransferCallbacks@ServiceManager@@AEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001405c`

## callees

- `0x18001b610`
- `0x1800207d0`

## import_xrefs

- `mapsbtsvc!MapsBackgroundTransferService_RegisterCallbacks` at `0x18001b66c`
- `mapsbtsvc!MapsBackgroundTransferService_RegisterCallbacks` at `0x18001b66c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b653`

## string_xrefs

- `0x18001b645`: `ServiceManager::RegisterTransferCallbacks`

## pseudocode

```c
int __fastcall ServiceManager::RegisterTransferCallbacks(ServiceManager *this)
{
  int MapsPersistedRegDword; // eax
  ServiceManager *v3; // r9
  int v4; // r8d
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  MapsPersistedRegDword = RegUtils::GetMapsPersistedRegDword(
                            (__int64)this,
                            L"BitsSustainedPauseMinimumInSeconds",
                            300,
                            &v6);
  v3 = this;
  if ( MapsPersistedRegDword < 0 )
  {
    v4 = 2144;
    return ZTraceReportPropagation(MapsPersistedRegDword, "ServiceManager::RegisterTransferCallbacks", v4, v3);
  }
  MapsPersistedRegDword = MapsBackgroundTransferService_RegisterCallbacks(
                            v6,
                            (void (__high *)(void *, enum MAPSBTSVC_JOB_TYPE, enum MAPSBTSVC_JOB_STATE_CHANGE, enum MAPSBTSVC_JOB_WAITING_REASON))ServiceManager::MapsbtsvcJobStateChangedCallback,
                            (void (__high *)(void *, enum MAPSBTSVC_TRANSFER_STATE, unsigned __int64))ServiceManager::MapsbtsvcTransferProgressCallback,
                            this);
  if ( MapsPersistedRegDword < 0 )
  {
    v3 = this;
    v4 = 2151;
    return ZTraceReportPropagation(MapsPersistedRegDword, "ServiceManager::RegisterTransferCallbacks", v4, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b610  push    rbx
0x18001b612  sub     rsp, 20h
0x18001b616  lea     r9, [rsp+28h+arg_8]
0x18001b61b  mov     [rsp+28h+arg_8], 0
0x18001b623  mov     r8d, 12Ch
0x18001b629  lea     rdx, aBitssustainedp; "BitsSustainedPauseMinimumInSeconds"
0x18001b630  mov     rbx, rcx
0x18001b633  call    ?GetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x18001b638  mov     r9, rbx
0x18001b63b  test    eax, eax
0x18001b63d  jns     short loc_18001B65A
0x18001b63f  mov     r8d, 860h
0x18001b645  lea     rdx, aServicemanager_36; "ServiceManager::RegisterTransferCallbac"...
0x18001b64c  mov     ecx, eax
0x18001b64e  add     rsp, 20h
0x18001b652  pop     rbx
0x18001b653  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b65a  mov     ecx, [rsp+28h+arg_8]
0x18001b65e  lea     r8, ?MapsbtsvcTransferProgressCallback@ServiceManager@@CAXPEAXW4MAPSBTSVC_TRANSFER_STATE@@_K@Z; ServiceManager::MapsbtsvcTransferProgressCallback(void *,MAPSBTSVC_TRANSFER_STATE,unsigned __int64)
0x18001b665  lea     rdx, ?MapsbtsvcJobStateChangedCallback@ServiceManager@@CAXPEAXW4MAPSBTSVC_JOB_TYPE@@W4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@Z; ServiceManager::MapsbtsvcJobStateChangedCallback(void *,MAPSBTSVC_JOB_TYPE,MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON)
0x18001b66c  call    cs:__imp_?MapsBackgroundTransferService_RegisterCallbacks@@YAJKP6AXPEAXW4MAPSBTSVC_JOB_TYPE@@W4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@ZP6AX0W4MAPSBTSVC_TRANSFER_STATE@@_K@Z0@Z; MapsBackgroundTransferService_RegisterCallbacks(ulong,void (*)(void *,MAPSBTSVC_JOB_TYPE,MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON),void (*)(void *,MAPSBTSVC_TRANSFER_STATE,unsigned __int64),void *)
0x18001b672  test    eax, eax
0x18001b674  jns     short loc_18001B681
0x18001b676  mov     r9, rbx
0x18001b679  mov     r8d, 867h
0x18001b67f  jmp     short loc_18001B645
0x18001b681  xor     eax, eax
0x18001b683  add     rsp, 20h
0x18001b687  pop     rbx
0x18001b688  retn
```
