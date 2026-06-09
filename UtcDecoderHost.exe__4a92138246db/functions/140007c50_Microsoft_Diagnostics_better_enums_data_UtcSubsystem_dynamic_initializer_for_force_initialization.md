# Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_dynamic_initializer_for___force_initialization__

- ea: `0x140007c50`
- end: `0x140007ce3`
- name: `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007c50`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007c95`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140007c95`

## string_xrefs

- `0x140007c7c`: `UserManager,SettingsManager,PiiScrubberManager,SystemStateManager,HeartBeat,ConnectivityHeartBeat,PrivacyKeyManager,EnterpriseData,EventMonitorManager,EventStore,Database,ThrottleMonitor,UsageAnalyzer,EventTranscriptManager,AsimovUploader,LatencyData,EscalationEngine,ScenarioStorage,ScenarioCacheLRU,ScenarioManager,OsEvents,MatchEngine,TriggerListener,TraceManager,MetadataEngine,TenantManager,UtcApiManager,TriggerAggregator,AggregatedEventManager,All,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x1E; ++i )
    {
      v2 = off_140019CA0[i];
      `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019CA0[i];
      `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007c50  mov     [rsp+arg_0], rbx
0x140007c55  mov     [rsp+arg_8], rdi
0x140007c5a  push    r14
0x140007c5c  sub     rsp, 20h
0x140007c60  cmp     cs:?value@?1??_initialized@_data_UtcSubsystem@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_initialized(void)'::`2'::value
0x140007c67  jnz     short loc_140007CD2
0x140007c69  xor     edi, edi
0x140007c6b  lea     r14, cs:140000000h
0x140007c72  xor     ebx, ebx
0x140007c74  mov     rcx, ds:rva off_140019CA0[r14+rbx*8]; Str
0x140007c7c  lea     rax, rva ?storage@?1??_name_storage@_data_UtcSubsystem@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "UserManager,SettingsManager,PiiScrubber"... ...
0x140007c83  add     rax, rdi
0x140007c86  lea     rdx, Control; "= \t\n"
0x140007c8d  mov     rva ?value@?1??_name_array@_data_UtcSubsystem@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_name_array(void)'::`2'::value ...
0x140007c95  call    cs:__imp_strcspn
0x140007c9b  mov     rcx, ds:rva off_140019CA0[r14+rbx*8]; "UserManager" ...
0x140007ca3  add     rax, rdi
0x140007ca6  mov     byte ptr [rax+r14+270B0h], 0
0x140007caf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007cb3  inc     rax
0x140007cb6  cmp     byte ptr [rcx+rax], 0
0x140007cba  jnz     short loc_140007CB3
0x140007cbc  inc     rdi
0x140007cbf  inc     rbx
0x140007cc2  add     rdi, rax
0x140007cc5  cmp     rbx, 1Eh
0x140007cc9  jb      short loc_140007C74
0x140007ccb  mov     cs:?value@?1??_initialized@_data_UtcSubsystem@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_UtcSubsystem::_initialized(void)'::`2'::value
0x140007cd2  mov     rbx, [rsp+28h+arg_0]
0x140007cd7  mov     rdi, [rsp+28h+arg_8]
0x140007cdc  add     rsp, 20h
0x140007ce0  pop     r14
0x140007ce2  retn
```
