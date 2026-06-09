# _UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$3

- ea: `0x140011b9f`
- end: `0x140011bab`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a204`

## pseudocode

```c
void __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::vector<AppUriHandlerRegistrationInfo>::~vector<AppUriHandlerRegistrationInfo>((AppUriHandlerRegistrationInfo **)(a2 + 128));
}

```

## disassembly

```asm
0x140011b9f  lea     rcx, [rdx+80h]
0x140011ba6  jmp     ??1?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ; std::vector<AppUriHandlerRegistrationInfo>::~vector<AppUriHandlerRegistrationInfo>(void)
```
