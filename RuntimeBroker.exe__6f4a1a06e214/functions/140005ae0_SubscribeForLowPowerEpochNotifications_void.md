# SubscribeForLowPowerEpochNotifications(void)

- ea: `0x140005ae0`
- end: `0x140005b41`
- name: `?SubscribeForLowPowerEpochNotifications@@YAKXZ`
- size: `97`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005770`

## callees

- `0x140005ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b39`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x140005b2e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x140005b2e`

## pseudocode

```c
DWORD SubscribeForLowPowerEpochNotifications(void)
{
  _QWORD Recipient[3]; // [rsp+20h] [rbp-18h] BYREF

  Recipient[1] = 0;
  Recipient[0] = RtbPowerEpochChangedCallback;
  g_hLowPowerEpoch = CreateEventW(0, 0, 1, 0);
  if ( g_hLowPowerEpoch )
    return PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, Recipient, &g_hPowerEpochStateNotification);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x140005ae0  sub     rsp, 38h
0x140005ae4  xor     r9d, r9d; lpName
0x140005ae7  mov     [rsp+38h+var_10], 0
0x140005af0  lea     rax, ?RtbPowerEpochChangedCallback@@YAKPEAXK0@Z; RtbPowerEpochChangedCallback(void *,ulong,void *)
0x140005af7  xor     edx, edx; bManualReset
0x140005af9  xor     ecx, ecx; lpEventAttributes
0x140005afb  mov     [rsp+38h+Recipient], rax
0x140005b00  lea     r8d, [r9+1]; bInitialState
0x140005b04  call    cs:__imp_CreateEventW
0x140005b0a  mov     cs:?g_hLowPowerEpoch@@3PEAXEA, rax; void * g_hLowPowerEpoch
0x140005b11  test    rax, rax
0x140005b14  jz      short loc_140005B39
0x140005b16  lea     r9, ?g_hPowerEpochStateNotification@@3PEAXEA; RegistrationHandle
0x140005b1d  mov     edx, 2; Flags
0x140005b22  lea     r8, [rsp+38h+Recipient]; Recipient
0x140005b27  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x140005b2e  call    cs:__imp_PowerSettingRegisterNotification
0x140005b34  add     rsp, 38h
0x140005b38  retn
0x140005b39  call    cs:__imp_GetLastError
0x140005b3f  jmp     short loc_140005B34
```
