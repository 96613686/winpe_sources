# tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::Release(void)

- ea: `0x180036eac`
- end: `0x180036ee4`
- name: `?Release@?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003448c`
- `0x18003997c`
- `0x18003a4ec`

## callees

- `0x1800344a8`
- `0x180036eac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ed1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ed1`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::~merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180036eac  mov     [rsp+arg_0], rbx
0x180036eb1  push    rdi
0x180036eb2  sub     rsp, 20h
0x180036eb6  mov     rdi, rcx
0x180036eb9  or      ebx, 0FFFFFFFFh
0x180036ebc  lock xadd [rcx+118h], ebx
0x180036ec4  sub     ebx, 1
0x180036ec7  jnz     short loc_180036ED7
0x180036ec9  call    ??1?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>::~merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>(void)
0x180036ece  mov     rcx, rdi; pv
0x180036ed1  call    cs:__imp_CoTaskMemFree
0x180036ed7  mov     eax, ebx
0x180036ed9  mov     rbx, [rsp+28h+arg_0]
0x180036ede  add     rsp, 20h
0x180036ee2  pop     rdi
0x180036ee3  retn
```
