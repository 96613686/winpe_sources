# std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::~_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>(void)

- ea: `0x18002b0b4`
- end: `0x18002b101`
- name: `??1?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@UEAA@XZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b180`
- `0x18002bfb0`
- `0x1800575bc`

## callees

- `0x18002b0b4`
- `0x18002b4c4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b0ed`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b0ed`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002b0e0`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002b0e0`

## pseudocode

```c
__int64 __fastcall std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::~_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>(
        __int64 a1)
{
  bool v1; // zf

  v1 = *(_BYTE *)(a1 + 313) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::`vftable';
  if ( !v1 && !*(_DWORD *)(a1 + 308) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 152));
  __ExceptionPtrDestroy((void *)(a1 + 136));
  return std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>::~pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>(a1 + 16);
}

```

## disassembly

```asm
0x18002b0b4  push    rbx
0x18002b0b6  sub     rsp, 20h
0x18002b0ba  cmp     byte ptr [rcx+139h], 0
0x18002b0c1  lea     rax, ??_7?$_Associated_state@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@6B@; const std::_Associated_state<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>::`vftable'
0x18002b0c8  mov     [rcx], rax
0x18002b0cb  mov     rbx, rcx
0x18002b0ce  jz      short loc_18002B0E6
0x18002b0d0  cmp     dword ptr [rcx+134h], 0
0x18002b0d7  jnz     short loc_18002B0E6
0x18002b0d9  add     rcx, 98h; _Mtx_t
0x18002b0e0  call    cs:__imp__Cnd_unregister_at_thread_exit
0x18002b0e6  lea     rcx, [rbx+88h]
0x18002b0ed  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b0f3  lea     rcx, [rbx+10h]
0x18002b0f7  add     rsp, 20h
0x18002b0fb  pop     rbx
0x18002b0fc  jmp     ??1?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@QEAA@XZ; std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>::~pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>(void)
```
