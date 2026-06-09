# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002acf0`
- end: `0x18002ad3b`
- name: `?s_PairingWorkerCallback@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `75`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18002a488`
- `0x18002ecb8`

## import_xrefs

- `BthTelemetry!BthProcessEventOccurrenceResultBthaddr` at `0x18002ad28`
- `BthTelemetry!BthProcessEventOccurrenceResultBthaddr` at `0x18002ad28`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002ad08`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002ad08`

## string_xrefs

- `0x18002acf9`: `BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED`
- `0x18002ad1b`: `BTH_TELEMETRYDATA_PREPAIRING_RESULT`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  int v4; // eax

  BthProcessEventOccurrenceBthaddr(
    "BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED",
    *(_QWORD *)(*((_QWORD *)Context + 11) + 48LL));
  v4 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(*((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice **)Context
                                                                                   + 11));
  BthProcessEventOccurrenceResultBthaddr(
    "BTH_TELEMETRYDATA_PREPAIRING_RESULT",
    v4,
    *(_QWORD *)(*((_QWORD *)Context + 11) + 48LL));
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)Context);
}

```

## disassembly

```asm
0x18002acf0  push    rbx
0x18002acf2  sub     rsp, 20h
0x18002acf6  mov     rbx, rdx
0x18002acf9  lea     rcx, aBthTelemetryda_1; "BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED"
0x18002ad00  mov     rdx, [rdx+58h]
0x18002ad04  mov     rdx, [rdx+30h]
0x18002ad08  call    cs:__imp_?BthProcessEventOccurrenceBthaddr@@YAXPEBD_K@Z; BthProcessEventOccurrenceBthaddr(char const *,unsigned __int64)
0x18002ad0e  mov     rcx, [rbx+58h]; this
0x18002ad12  call    ?Start@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(void)
0x18002ad17  mov     r8, [rbx+58h]
0x18002ad1b  lea     rcx, aBthTelemetryda_0; "BTH_TELEMETRYDATA_PREPAIRING_RESULT"
0x18002ad22  mov     edx, eax
0x18002ad24  mov     r8, [r8+30h]
0x18002ad28  call    cs:__imp_?BthProcessEventOccurrenceResultBthaddr@@YAXPEBDJ_K@Z; BthProcessEventOccurrenceResultBthaddr(char const *,long,unsigned __int64)
0x18002ad2e  mov     rcx, rbx; this
0x18002ad31  add     rsp, 20h
0x18002ad35  pop     rbx
0x18002ad36  jmp     ?ResetPairingState@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(void)
```
